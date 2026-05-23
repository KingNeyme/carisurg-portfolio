# Assignment 7: Final Submission

## Week 0 Submission Package

This Week 0 folder contains all seven required assignments.

## Submission Checklist

- [x] Assignment 1: Data Cleaning, Gender Column
- [x] Assignment 2: Data Cleaning, Assigned Column
- [x] Assignment 3: Data Visualization
- [x] Assignment 4: Vital Sign Description
- [x] Assignment 5: Unconsidered Metrics
- [x] Assignment 6: Triage Pseudocode
- [x] Assignment 7: Final Submission

## What I Completed

In Week 0, I practiced the full early workflow of a clinical AI project:

1. Loaded and inspected an emergency triage dataset.
2. Cleaned inconsistent categorical values in the `Gender` column.
3. Cleaned my assigned vital-sign column, `pulse`, using clinical valid ranges.
4. Created visualizations that answer clinical questions.
5. Wrote a plain-language explanation of pulse as a vital sign.
6. Identified important missing clinical metrics that would matter in real triage.
7. Drafted triage pseudocode that connects clinical rules to AI decision-support logic.

## How I Understand The Code Work

The main coding skill I practiced was using Python and pandas to move from raw clinical data to cleaner, more useful information.

For Assignment 1, I used inspection commands such as `unique()` and `value_counts()` to understand the dirty `Gender` column before changing it. I then used a mapping dictionary to convert several versions of the same category into one consistent encoding. I verified the result by checking for missing values after mapping.

For Assignment 2, I learned that clinical columns often need type conversion before analysis. I used `pd.to_numeric(..., errors='coerce')` so values that could not be converted became `NaN`. I then used clinical valid ranges to decide which values were physiologically invalid. For my assigned `pulse` column, I cleaned values outside `20-250 bpm` and used median imputation because the median is safer when data may contain extreme values.

For Assignment 3, I used matplotlib to create charts that answer clinical questions. I used bar charts for categories, histograms for distributions, scatter plots for relationships, and box plots for checking spread and possible outliers. I also added clinical reference lines, such as GCS thresholds and tachycardia thresholds, because healthcare plots should explain what the values mean.

The biggest lesson is that code alone is not enough in clinical AI. I need to understand what each column means, what values are clinically possible, and why a cleaning decision is appropriate before building any model or decision-support tool.

## Portfolio Reflection

Week 0 taught me that clinical AI engineering starts before machine learning. The first responsibility is to understand the data, question whether values are clinically possible, document each cleaning decision, and communicate findings clearly.

This work also reinforced that Caribbean healthcare technology should be practical, explainable, and grounded in the realities of real clinical environments.
