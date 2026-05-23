# Week 0: Clinical Data Foundations

Week 0 introduces the foundation of clinical AI engineering: understanding messy healthcare data before trying to model it.

The work in this folder shows how I loaded an emergency triage dataset, inspected data quality issues, cleaned columns using clinical reasoning, visualized patient vital signs, and translated triage thinking into structured pseudocode.

## Week Theme

**From dirty triage data to explainable clinical insight.**

This week was not only about writing Python code. It was about learning how to ask better questions of healthcare data:

- What does each column mean clinically?
- Which values are impossible, unusual, or still valid?
- What should be cleaned, what should be kept, and why?
- How can a chart communicate risk clearly?
- How can clinical reasoning become structured decision logic?

## Skills Demonstrated

| Skill Area | Evidence |
| --- | --- |
| Data inspection | Used `head()`, `info()`, `describe()`, `unique()`, and `value_counts()` to understand the dataset before cleaning |
| Data cleaning | Standardized dirty category labels and converted clinical columns into usable numeric formats |
| Clinical validation | Used physiologic ranges for GCS, blood pressure, pulse, temperature, respiratory rate, and FiO2 |
| Missing-value handling | Replaced invalid values with `NaN` and used median imputation where appropriate |
| Visualization | Built charts that answer clinical questions and include reference lines or clinical thresholds |
| Communication | Wrote plain-language reports explaining vital signs, missing metrics, and triage logic |
| AI engineering thinking | Connected data cleaning and clinical rules to future decision-support systems |

## Assignment Map

| # | Assignment | Status | Submission File |
| --- | --- | --- | --- |
| 1 | Data Cleaning: Gender Column | Complete | [`assignments/Week0_Tutorial1_EnvSetup_and_Cleaning_Gender.ipynb`](assignments/Week0_Tutorial1_EnvSetup_and_Cleaning_Gender.ipynb) |
| 2 | Data Cleaning: Assigned Column | Complete | [`assignments/Week0_Tutorial2_Advanced_Cleaning.ipynb`](assignments/Week0_Tutorial2_Advanced_Cleaning.ipynb) |
| 3 | Data Visualization | Complete | [`assignments/Week0_Tutorial3_Visualisation.ipynb`](assignments/Week0_Tutorial3_Visualisation.ipynb) |
| 4 | Vital Sign Description | Complete | [`assignments/Assignment4_Vital_Sign_Description.md`](assignments/Assignment4_Vital_Sign_Description.md) |
| 5 | Unconsidered Metrics | Complete | [`assignments/Assignment5_Unconsidered_Metrics.md`](assignments/Assignment5_Unconsidered_Metrics.md) |
| 6 | Triage Pseudocode | Complete | [`assignments/Assignment6_Triage_Pseudocode.md`](assignments/Assignment6_Triage_Pseudocode.md) |
| 7 | Final Submission | Complete | [`assignments/Assignment7_Final_Submission.md`](assignments/Assignment7_Final_Submission.md) |

## Dataset

The Week 0 dataset contains **2,205 emergency triage records** with 11 fields:

`ID`, `Age`, `Gender`, `GCS`, `SBP`, `DBP`, `MAP`, `pulse`, `Temp`, `RR`, and `Fio2`.

The dataset is intentionally dirty for training. It includes inconsistent labels, wrong data types, non-numeric values, missing values, invalid physiologic values, and temperature unit issues.

Dataset file:

[`data/EmergencyTriageDataset_Reduced_Dirty.csv`](data/EmergencyTriageDataset_Reduced_Dirty.csv)

## Assignment Highlights

### Assignment 1: Gender Cleaning

I cleaned the `Gender` column by mapping six raw variants into one consistent encoding.

| Raw Values | Cleaned Value |
| --- | --- |
| `1`, `MALE`, `Male` | `1` |
| `0`, `FEMALE`, `Female` | `0` |

The key lesson was that even a simple column needs inspection, documentation, and verification.

### Assignment 2: Assigned Column Cleaning

My assigned column was `pulse`, representing heart rate in beats per minute.

Cleaning decisions:

- Converted the column to numeric with `pd.to_numeric(..., errors='coerce')`.
- Treated `20-250 bpm` as the valid clinical range for this training dataset.
- Replaced invalid values with `NaN`.
- Used median imputation because pulse data can contain extreme values.

This assignment helped me understand that clinical cleaning decisions should be based on physiology, not only on statistics.

### Assignment 3: Data Visualization

The visualization notebook creates charts that answer specific clinical questions.

Generated outputs:

- [`outputs/gender_distribution.png`](outputs/gender_distribution.png)
- [`outputs/gcs_histogram.png`](outputs/gcs_histogram.png)
- [`outputs/pulse_histogram.png`](outputs/pulse_histogram.png)
- [`outputs/sbp_vs_dbp.png`](outputs/sbp_vs_dbp.png)
- [`outputs/age_vs_pulse.png`](outputs/age_vs_pulse.png)
- [`outputs/vitals_boxplots.png`](outputs/vitals_boxplots.png)
- [`outputs/fio2_vs_pulse.png`](outputs/fio2_vs_pulse.png)

The strongest lesson here was that visualizations should include clinical context. A chart is more useful when it helps someone understand what a value means for patient care.

### Assignments 4-7: Written Clinical Reasoning

The written assignments explain the clinical meaning behind the code work:

- Pulse as a vital sign
- Important missing metrics such as oxygen saturation, chief complaint, pain score, and medical history
- Triage pseudocode for turning clinical reasoning into structured logic
- Final reflection on what Week 0 taught me about clinical AI engineering

## Folder Guide

| Folder | Purpose |
| --- | --- |
| `assignments/` | Completed notebooks and written reports |
| `data/` | Week 0 training dataset and data notes |
| `outputs/` | Plot images generated from the visualization notebook |

## Working In Anaconda/Jupyter

Open the notebooks from:

```text
week-0/assignments/
```

If any notebooks are already open from an older location, close those tabs and reopen them from this folder before saving.

## Reflection

Week 0 taught me that clinical AI starts before machine learning. The first job is to understand the data, clean it responsibly, and explain each decision clearly.

The most important idea I learned is this:

**A value can be statistically unusual and still be clinically valid.**

That means clinical AI engineers must combine technical skill with healthcare context. The code matters, but the reasoning behind the code matters just as much.
