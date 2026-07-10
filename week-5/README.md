# Week 5: AI-Assisted Triage Data Exploration

Week 5 begins the two-week modelling block for the emergency department triage project. The goal this week was not to build a model yet; it was to decide whether the dataset is strong enough to support one.

## One-Line Verdict

The dataset is good enough to move into Week 6 baseline modelling, but only with clear caveats around missing laboratory data, single-site generalisability, and careful governance of demographic features.

## Submission Map

| Deliverable | Location | Status |
| --- | --- | --- |
| Full exploration notebook | [`../notebooks/Week5_AI_Assisted_Triage_Data_Exploration.ipynb`](../notebooks/Week5_AI_Assisted_Triage_Data_Exploration.ipynb) | Complete |
| Week-specific notebook copy | [`assignments/Week5_AI_Assisted_Triage_Data_Exploration.ipynb`](assignments/Week5_AI_Assisted_Triage_Data_Exploration.ipynb) | Complete |
| Feasibility memo | [`../docs/week-5-feasibility-memo.md`](../docs/week-5-feasibility-memo.md) | Complete |
| Career roadmap challenge | [`assignments/Career_Challenge_10_Year_Roadmap.md`](assignments/Career_Challenge_10_Year_Roadmap.md) | Complete |
| Data-quality dashboard images | [`outputs/`](outputs/) | Complete |
| Missingness table | [`assignments/week5_missingness_table.csv`](assignments/week5_missingness_table.csv) | Complete |
| Top-10 feature shortlist | [`assignments/week5_top10_feature_shortlist.csv`](assignments/week5_top10_feature_shortlist.csv) | Complete |
| Cleaned local dataset | `../data/processed/week5_triage_cleaned.parquet` | Generated locally and intentionally ignored by Git |

## Dataset Notes

The assignment brief names `yaleemmlc_admissionprediction_triage.csv`. The available public teaching dataset used here is the Hugging Face re-hosted Yale ED admission prediction dataset, provided as `full_data.parquet`.

Local dataset paths:

- Raw local dataset: `data/raw/full_data.parquet`
- Cleaned local dataset: `data/processed/week5_triage_cleaned.parquet`

Both folders are intentionally ignored in `.gitignore` because patient-level clinical datasets should not be committed to a public portfolio repo.

## Key Profile Results

| Metric | Result |
| --- | --- |
| Encounters | 560,486 |
| Columns | 972 |
| Target | `esi` triage level |
| Chief complaint indicators | 200 |
| Overall missingness | 29.7% |
| Columns with more than 50% missing | 354 |
| Columns with more than 90% missing | 120 |

## Dashboard

| Plot | Purpose |
| --- | --- |
| [`outputs/missingness_top25.png`](outputs/missingness_top25.png) | Discord-ready data-quality image showing the most incomplete fields |
| [`outputs/esi_distribution.png`](outputs/esi_distribution.png) | Shows target distribution across ESI triage levels |
| [`outputs/race_ethnicity_distribution.png`](outputs/race_ethnicity_distribution.png) | Checks demographic representation |
| [`outputs/chief_complaints_top20.png`](outputs/chief_complaints_top20.png) | Shows common presenting complaints |
| [`outputs/vitals_by_esi.png`](outputs/vitals_by_esi.png) | Summarises vital signs across triage levels |
| [`outputs/feature_acuity_correlations.png`](outputs/feature_acuity_correlations.png) | Shows features most associated with acuity score |

## Top-10 Feature Shortlist

| Rank | Feature | Why it matters |
| --- | --- | --- |
| 1 | `triage_vital_sbp` | Helps identify shock, bleeding, sepsis, and other unstable states. |
| 2 | `triage_vital_hr` | Rises with pain, fever, dehydration, arrhythmia, and physiological stress. |
| 3 | `triage_vital_rr` | Often changes early in sepsis, respiratory failure, and deterioration. |
| 4 | `triage_vital_o2` | Low oxygen saturation is a direct warning sign for respiratory compromise. |
| 5 | `triage_vital_temp` | Supports infection, fever, heat illness, and sepsis screening. |
| 6 | `age` | Strong baseline risk factor, especially for older adults and very young patients. |
| 7 | `arrivalmode_ambulance_or_helicopter` | Proxy for pre-hospital severity and urgent transport. |
| 8 | `cc_chestpain` | Can indicate time-sensitive cardiac, vascular, or respiratory emergencies. |
| 9 | `cc_shortnessofbreath` | Connected to hypoxia, heart failure, asthma, COPD, pneumonia, and pulmonary embolism. |
| 10 | `cc_alteredmentalstatus` | May signal stroke, sepsis, hypoglycaemia, intoxication, trauma, or neurological emergency. |

## Discord Image

For the interim Discord submission, use:

[`outputs/missingness_top25.png`](outputs/missingness_top25.png)

Suggested caption:

> Week 5 interim EDA: I profiled the ED triage dataset and found that missingness is concentrated in specific lab/urine/toxicology fields, while core fields like ESI, age, demographics, arrival mode, chief complaints, and triage vitals are much more usable for baseline modelling. My current verdict is proceed with caveats.

