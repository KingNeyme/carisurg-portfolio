# Week 0 Data

## File

`EmergencyTriageDataset_Reduced_Dirty.csv`

This dataset contains 2,205 emergency triage records used for the Week 0 CariSurg assignments.

## Columns

- `ID`
- `Age`
- `Gender`
- `GCS`
- `SBP`
- `DBP`
- `MAP`
- `pulse`
- `Temp`
- `RR`
- `Fio2`

## Data Quality Issues

The dataset is intentionally dirty for training. It includes:

- inconsistent gender labels
- numeric columns stored as text
- non-numeric error values
- missing values
- physiologically invalid values
- temperature unit inconsistencies

The cleaning decisions are documented in the Week 0 assignment notebooks.
