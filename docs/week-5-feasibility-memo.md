# Week 5 Feasibility Memo: ED Triage Dataset

**To:** Dr. De Fretias and ED Board  
**From:** Nehemiah Monrose  
**Project:** AI-Assisted Triage Data Exploration, Part 1 of 2  
**Date:** July 2026  

## One-Sentence Verdict

This dataset is strong enough to proceed to a Week 6 baseline triage model, but it should be used with caveats because missingness is concentrated in many laboratory and specialised test fields, the data appears single-site, and demographic fields must be handled carefully to avoid embedding unfairness into the model.

## Dataset Summary

The Week 5 dataset contains **560,486 emergency department encounters** and **972 columns**. The target variable is `esi`, which represents Emergency Severity Index triage level. In this scale, **ESI 1 is the most urgent** and **ESI 5 is the least urgent**. I created an `acuity_score` where higher values mean higher urgency so that correlations would be easier to interpret.

The dataset is clinically rich. It includes encounter context, patient demographics, arrival mode, prior disposition, previous ED use and admissions, triage vital signs, later vital signs, laboratory summaries, urinalysis, imaging counts, medication groups, surgery history, diagnosis/history indicators, and around **200 chief complaint indicators**. This gives the project enough clinical breadth to test whether a baseline model can recognise patterns associated with triage urgency.

The ESI distribution is usable but imbalanced. ESI 3 is the largest group at **42.1%**, followed by ESI 2 at **29.2%**, ESI 4 at **22.3%**, ESI 5 at **5.0%**, and ESI 1 at **0.9%**. This means a baseline model may learn the middle-acuity cases more easily than the rare highest-acuity cases. Week 6 evaluation should therefore report performance by ESI level, not just overall accuracy.

Supporting plots:

- [Missingness dashboard](../week-5/outputs/missingness_top25.png)
- [ESI distribution](../week-5/outputs/esi_distribution.png)
- [Race and ethnicity distribution](../week-5/outputs/race_ethnicity_distribution.png)
- [Chief complaint distribution](../week-5/outputs/chief_complaints_top20.png)
- [Vital signs by ESI](../week-5/outputs/vitals_by_esi.png)
- [Feature-acuity correlations](../week-5/outputs/feature_acuity_correlations.png)

## Top 3 Quality Concerns

**1. Missingness is high in many clinical test fields.**  
Overall missingness is **29.7%**, but that average hides a sharper issue: **354 columns have more than 50% missingness**, and **120 columns have more than 90% missingness**. Many of the most incomplete fields are specialised tests such as toxicology, epithelial cells, acetone, troponin, D-dimer, BNP, and other laboratory measurements. This does not automatically mean the dataset is poor. In emergency care, many tests are only ordered when clinically indicated. However, it means missingness may reflect the clinical workflow, not random absence. For modelling, we should avoid treating all missing values as simple data errors.

**2. Some vital signs need validation before modelling.**  
The core triage vital signs are mostly present for about half to two-thirds of encounters, which is helpful. However, there are a small number of physiologically implausible values. For example, systolic blood pressure ranges from **45 to 312**, diastolic blood pressure reaches **214**, and heart rate reaches **280**. I flagged values outside clinically plausible ranges and set them to missing in the cleaned local dataset. The counts were small, but the cleaning decision should still be documented because vital signs are likely to be important model inputs.

**3. Demographic and site-specific bias must be managed.**  
The dataset contains race, ethnicity, language, religion, marital status, employment status, and insurance status. These features can help identify population-level gaps, but they can also encode inequity if used carelessly. The race/ethnicity dashboard should be reviewed before model training, and any Week 6 model should be checked for performance differences across demographic groups. Since the data comes from a specific source context, it may not transfer directly to a Caribbean ED without local validation.

## Top 3 Reasons To Proceed

**1. The target variable is present and clinically meaningful.**  
The ESI target is available for almost all records, with only about **0.4% missing**. That gives the Week 6 modelling task a clear supervised learning target. The distribution is not perfectly balanced, but it is realistic for ED triage and can be handled with stratified evaluation.

**2. The dataset includes the core information triage staff actually use.**  
The most important early inputs are present: age, arrival mode, triage vital signs, and chief complaints. The common complaints also make clinical sense. The top complaints include abdominal pain, chest pain, shortness of breath, back pain, falls, dizziness, cough, alcohol intoxication, and motor vehicle crash. These are common ED presentations and should support useful baseline modelling.

**3. Early feature signals are clinically plausible.**  
Simple correlations with acuity show sensible patterns. Ambulance or helicopter arrival has the strongest association with higher acuity. Age is also associated with higher acuity. Lower oxygen saturation, higher heart rate, respiratory distress complaints, chest pain, and altered mental status all show signal. These findings do not prove model performance, but they suggest the data contains meaningful clinical structure rather than noise only.

## Top-10 Feature Shortlist

| Rank | Feature | Correlation with acuity | Reasoning |
| --- | --- | ---: | --- |
| 1 | `triage_vital_sbp` | 0.038 | Blood pressure helps identify shock, bleeding, sepsis, and other unstable states. |
| 2 | `triage_vital_hr` | 0.137 | Heart rate rises with pain, fever, dehydration, hypoxia, arrhythmia, and stress. |
| 3 | `triage_vital_rr` | 0.097 | Respiratory rate often changes early in sepsis, respiratory failure, and deterioration. |
| 4 | `triage_vital_o2` | -0.188 | Lower oxygen saturation is directly linked to respiratory compromise and urgency. |
| 5 | `triage_vital_temp` | 0.013 | Temperature supports infection, fever, heat illness, and sepsis screening. |
| 6 | `age` | 0.277 | Age changes baseline risk and affects how illness presents. |
| 7 | `arrivalmode_ambulance_or_helicopter` | 0.389 | Emergency transport can act as a proxy for pre-hospital severity. |
| 8 | `cc_chestpain` | 0.155 | Chest pain can represent time-sensitive cardiac, vascular, or respiratory emergencies. |
| 9 | `cc_shortnessofbreath` | 0.140 | Shortness of breath is tied to hypoxia, heart failure, asthma, COPD, pneumonia, and pulmonary embolism. |
| 10 | `cc_alteredmentalstatus` | 0.123 | Altered mental status may signal stroke, sepsis, hypoglycaemia, intoxication, trauma, or neurological emergency. |

The correlations are simple screening signals, not final proof of usefulness. I kept the shortlist grounded in both clinical reasoning and measurable association with acuity. Some features with stronger correlations were not automatically selected because they may occur after triage, may be ordered only for selected patients, or may create leakage if they reflect downstream care rather than information available at triage.

## Caveats And Week 6 Modelling Conditions

The Week 6 baseline model should start with features that are realistically available at triage: age, arrival mode, chief complaints, and triage vital signs. Laboratory, medication, imaging, and later vital-sign fields should be handled carefully because some may be collected after the triage decision. Including those fields too early could inflate performance and make the model look better than it would be in real triage practice.

Missingness should be treated as a clinical signal where appropriate. For example, a missing troponin may mean the test was not ordered, not that the value was forgotten. For baseline modelling, I would compare a simple triage-available feature set against a broader feature set and clearly label the difference.

The model should be evaluated by ESI level and demographic subgroup. Because ESI 1 is rare, a model could perform well overall while still missing the most urgent patients. That would be clinically unacceptable. The baseline should therefore include confusion matrices, recall for ESI 1 and ESI 2, and subgroup checks by race, ethnicity, age band, and arrival mode.

My recommendation is to **proceed with caveats**. The data is large, clinically relevant, and contains meaningful early signals. The main risk is not that the dataset is unusable; the main risk is building too quickly without respecting missingness, workflow timing, and fairness.

