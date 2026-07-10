# Data

This folder is the class-required data entry point.

The Week 0 training dataset currently lives in the week-specific folder:

[`../week-0/data/EmergencyTriageDataset_Reduced_Dirty.csv`](../week-0/data/EmergencyTriageDataset_Reduced_Dirty.csv)

That file is a training dataset used for clinical data cleaning and visualisation exercises. It is intentionally dirty and includes inconsistent labels, wrong data types, missing values, and physiologically invalid values.

No real patient data or credentials should be committed to this repository.

## Week 5 Data

The Week 5 ED triage dataset is stored locally but ignored by Git:

- Raw dataset: `data/raw/full_data.parquet`
- Cleaned dataset: `data/processed/week5_triage_cleaned.parquet`

These files are intentionally excluded from commits because they are large patient-level clinical datasets, even though the training source is de-identified.

The tracked Week 5 data summaries live in:

[`../week-5/assignments/`](../week-5/assignments/)
