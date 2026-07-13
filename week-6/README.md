# Week 6: Building a Baseline Model

Week 6 completes the two-week triage modelling block. Week 5 asked whether the dataset was good enough to build on. Week 6 answers the next question: can a simple baseline model beat a stratified random guess, and can the results be explained to a clinical reviewer?

## One-Line Verdict

Yes. The logistic regression baseline beats the stratified random baseline and is the best first reference model, but it is not ready for clinical use without threshold tuning, subgroup checks, and clinician-led error review.

## Submission Map

| Deliverable | Location | Status |
| --- | --- | --- |
| Full modelling notebook | [`../notebooks/Week6_Baseline_Triage_Model.ipynb`](../notebooks/Week6_Baseline_Triage_Model.ipynb) | Complete |
| Week-specific notebook copy | [`assignments/Week6_Baseline_Triage_Model.ipynb`](assignments/Week6_Baseline_Triage_Model.ipynb) | Complete |
| Final model report | [`../docs/week-6-baseline-model-report.md`](../docs/week-6-baseline-model-report.md) | Complete |
| Model metrics table | [`assignments/week6_model_metrics.csv`](assignments/week6_model_metrics.csv) | Complete |
| Model summary table | [`assignments/week6_model_summary.csv`](assignments/week6_model_summary.csv) | Complete |
| Trained model artifacts | [`models/`](models/) | Complete |
| Confusion matrix images | [`outputs/`](outputs/) | Complete |
| 1-minute explainer script | [`assignments/Clinical_Explainer_Video_Script.md`](assignments/Clinical_Explainer_Video_Script.md) | Complete |
| Career challenge CV review | [`assignments/Career_Challenge_CV_Review.md`](assignments/Career_Challenge_CV_Review.md) | Complete |

## Reproducibility

| Setting | Value |
| --- | --- |
| Random seed | `42` |
| Split | 80/20 train-test |
| Stratification | ESI triage level |
| Decision tree max depth | `5` |
| Primary clinical metric | ESI Level 1 recall |
| Secondary summary metric | Macro F1 |

## Results

| Model | Accuracy | Macro F1 | Weighted F1 | ESI 1 Recall | ESI 2 Recall |
| --- | ---: | ---: | ---: | ---: | ---: |
| Stratified random baseline | 0.315 | 0.199 | 0.315 | 0.011 | 0.291 |
| Logistic regression | 0.457 | 0.382 | 0.503 | 0.742 | 0.480 |
| Decision tree | 0.252 | 0.200 | 0.263 | 0.766 | 0.434 |

## Why Recall For ESI 1?

ESI 1 patients are the rarest but highest-risk group. Overall accuracy can hide dangerous misses because most patients are not ESI 1. The first safety question for Dr. Reyes is: of the patients who truly needed immediate intervention, how many did the model catch?

The logistic regression model identified **782 of 1,054 actual ESI 1 cases** in the test set. That is not deployment-ready, but it is a meaningful baseline and much stronger than the stratified random model, which identified only **12 of 1,054 actual ESI 1 cases**.

## Discord Image

Use this image for the confusion matrix post:

[`outputs/logistic_regression_confusion_matrix.png`](outputs/logistic_regression_confusion_matrix.png)

Suggested caption:

> Week 6 baseline model: I trained a stratified random baseline, logistic regression, and a bounded decision tree. Logistic regression is my chosen reference model because it beats the random baseline and catches 74.2% of actual ESI 1 cases in the test set. I am using ESI 1 recall as the primary safety metric because missing the most urgent patients matters more than looking good on overall accuracy.

