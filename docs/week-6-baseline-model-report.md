# Week 6 Baseline Model Report: ED Triage Prediction

**Student:** Nehemiah Monrose  
**Programme:** CariSurg MedTech Pathways Programme  
**Project:** AI-Assisted Triage, Part 2 of 2  
**Random seed:** 42  

## One-Sentence Result

The logistic regression baseline is the stronger first model because it beats the stratified random baseline across accuracy, macro F1, weighted F1, and ESI Level 1 recall, while still keeping the modelling approach simple enough to explain to a clinical reviewer.

## Modelling Setup

I used the cleaned Week 5 ED triage dataset and filtered the target to valid ESI levels 1-5. The final modelling table contained **558,029 valid encounters** after excluding missing/non-valid ESI labels; the test set contained **111,606 encounters** after an **80/20 stratified train-test split**. The full valid modelling table contained **5,271 ESI Level 1 cases**; the **1,054 ESI Level 1 cases** reported below are the held-out test-set support after the stratified split, not the total dataset count.

The feature set was intentionally conservative. I used early triage information: age, previous ED visits/admissions, triage vital signs, arrival mode, time context, previous disposition, and selected chief complaint indicators. I did not use race/ethnicity or downstream laboratory/imaging fields in this first baseline because the aim is to estimate what a model could do with information available around triage, not information collected later in the patient journey.

Models trained:

- **Stratified random baseline:** `DummyClassifier(strategy="stratified")`
- **Logistic regression:** class-balanced multinomial baseline
- **Decision tree:** `max_depth=5`, `min_samples_leaf=100`, class-balanced

I bounded the decision tree at depth 5 because this is a first clinical baseline, not a leaderboard model. A shallow tree is easier to explain and less likely to overfit noise while still allowing meaningful branching across age, arrival mode, vitals, and chief complaints.

## Results Summary

| Model | Accuracy | Macro F1 | Weighted F1 | ESI 1 Recall | ESI 2 Recall |
| --- | ---: | ---: | ---: | ---: | ---: |
| Stratified random baseline | 0.315 | 0.199 | 0.315 | 0.011 | 0.291 |
| Logistic regression | 0.457 | 0.382 | 0.503 | 0.742 | 0.480 |
| Decision tree | 0.252 | 0.200 | 0.263 | 0.766 | 0.434 |

The logistic regression model is the most balanced baseline. It correctly identified **782 of 1,054 actual ESI 1 cases** in the held-out test set, giving an ESI 1 recall of **74.2%**. The decision tree had slightly higher ESI 1 recall at **76.6%**, but its overall accuracy and weighted F1 were much worse. In plain terms, the tree was more aggressive about calling cases urgent, but it also confused many lower-acuity patients.

Supporting outputs:

- [Logistic regression confusion matrix](../week-6/outputs/logistic_regression_confusion_matrix.png)
- [Decision tree confusion matrix](../week-6/outputs/decision_tree_confusion_matrix.png)
- [Random baseline confusion matrix](../week-6/outputs/dummy_stratified_confusion_matrix.png)
- [Model comparison image](../week-6/outputs/model_comparison_summary.png)

## Primary Metric

My primary metric is **recall for ESI Level 1**, supported by macro F1 as a secondary summary metric. In this triage context, the first safety question is not "how often is the model right overall?" The first safety question is: **of the patients who truly needed the highest urgency level, how many did the model actually catch?** ESI 1 patients are rare, so a model can look acceptable by overall accuracy while still missing the most dangerous cases. Missing an ESI 1 patient could mean delayed resuscitation, delayed senior review, delayed airway/breathing/circulation support, or delayed escalation for a patient who needed immediate attention.

## Macro F1 vs Weighted F1

Macro F1 gives each ESI class equal weight, so rare classes like ESI 1 matter just as much as common classes like ESI 3. Weighted F1 gives more influence to common classes because it weights each class by how many examples are in the test set. In this dataset, weighted F1 is useful for understanding overall performance, but macro F1 is important because it makes poor performance on rare high-risk classes harder to hide.

This is why accuracy alone is not enough. The stratified random baseline had **31.5% accuracy**, but only **1.1% recall for ESI 1**. A model like that could appear to make some correct predictions overall while almost never catching the most urgent patients.

## Failure-Mode Reflection

The failure mode I am most worried about is **under-triage of ESI 1 patients**, meaning a truly immediate patient is predicted as ESI 2, 3, 4, or 5. The logistic regression model missed **272 of 1,054 actual ESI 1 cases** by predicting them as less urgent. Most of those misses were predicted as ESI 2, which is still high acuity, but any ESI 1 miss matters because these are patients who may need immediate life-saving intervention.

The second concern is over-triage. The logistic regression model predicted some ESI 2-5 patients as ESI 1. Clinically, over-triage can strain staff, resuscitation spaces, and attention. However, for this first safety baseline, I would rather tolerate some over-triage than accept a model that quietly misses critical patients. The next model iteration should aim to improve ESI 1 recall while reducing unnecessary ESI 1 predictions through calibration, thresholding, and clinician review.

## Recommendation

Proceed with the logistic regression baseline as the Week 6 reference model. It is simple, reproducible, and clearly beats the stratified random baseline. The model is not ready for clinical deployment, but it is good enough to justify Phase 3 work: better feature review, leakage checks, threshold tuning, subgroup evaluation, and clinician-led error analysis.
