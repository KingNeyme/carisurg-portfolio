# Real-World AI Harm Case Study

## Racial Bias in a Population Health Management Algorithm

### What Happened

Obermeyer and colleagues examined a commercial algorithm used by health systems to identify patients who should receive additional support through high-risk care-management programmes. The system affected millions of patients. At the same algorithmic risk score, Black patients were substantially sicker than White patients, based on measures of uncontrolled illness. This meant that many Black patients with greater health needs were less likely to be selected for extra care. The researchers estimated that correcting the disparity would have increased the proportion of Black patients receiving additional help from 17.7% to 46.5% [1].

The harm was not a dramatic single failure such as an incorrect diagnosis displayed on a screen. It was a quieter allocation harm repeated across a population: an automated score influenced who received scarce support, while systematically underestimating the needs of one racial group.

### Root Cause

The central technical error was the choice of prediction target. The algorithm predicted future healthcare cost and treated cost as a proxy for health need. That choice may appear reasonable because patients with more illness often require more care. However, spending is also shaped by access, affordability, trust, geography, and unequal treatment. Black patients with the same level of illness historically generated lower healthcare spending, so the model learned that lower spending meant lower need. Its predictions could therefore look accurate against the selected target while remaining unfair and clinically misleading.

The deeper failure was sociotechnical. The development and governance process did not sufficiently challenge whether cost represented the clinical concept the programme actually cared about. Overall performance measures also concealed the difference between racial groups. A technically convenient label was allowed to stand in for a value-laden decision about who deserved additional resources.

### What the System Failed to Anticipate

The system failed to anticipate that historical utilisation data reflect barriers and inequities, not only illness. It also failed to treat resource allocation as a high-impact clinical decision requiring subgroup analysis, patient-centred outcomes, and ongoing oversight. The problem was not simply that race appeared in the data. Bias entered through the outcome definition and through the assumption that past spending was a neutral measure of future need.

### What Could Have Caught It

Four controls could have exposed the problem earlier. First, the target should have been defined as clinical need using measures such as disease burden, physiological risk, or preventable deterioration rather than cost alone. Second, validation should have compared illness severity, false-negative rates, calibration, and programme enrolment across racial groups. Third, clinicians, health-equity specialists, and patient representatives should have reviewed the proposed target and challenged its assumptions before deployment. Fourth, post-deployment monitoring should have examined who received support and whether outcomes improved equitably.

For the proposed triage project, the lesson is direct: a model can be statistically successful and still fail the clinical objective. Every target, proxy, threshold, and subgroup result must be justified in terms of patient need.

**Word count:** 511

## Source

1. Obermeyer Z, Powers B, Vogeli C, Mullainathan S. Dissecting racial bias in an algorithm used to manage the health of populations. Science. 2019;366(6464):447-453. doi:10.1126/science.aax2342
