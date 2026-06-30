# Risk Memo: Three Risks That Deserve Immediate Attention

**To:** Dr. De Fretias and the Saint Cedric Ministry of Health  
**From:** Nehemiah Monrose  
**Subject:** Highest-priority risks for an AI-assisted emergency department triage pilot

The proposed system should remain advisory. It should help a clinician notice risk, missing information, or a need for reassessment, but it should not independently decide a patient's triage category or clinical pathway.

## 1. Under-represented Patient Groups

If the training data contain very few children, rural patients, people with disabilities, or patients from particular ethnic or language groups, the model may work well for the average patient but poorly for the people it has rarely seen. A single overall accuracy score can hide this problem.

**Why this matters:** A missed high-risk patient can be delayed in the waiting room even though the system appears accurate overall.

**What I would do:** Check who is represented before training, report performance separately for clinically important groups, and refuse deployment for groups where the evidence is too small. Success means the worst-group sensitivity and false-negative rate remain within an agreed safety margin.

## 2. Distribution Shift Across Hospitals and Over Time

A model trained at one hospital learns that hospital's patients, equipment, documentation, and workflow. Another hospital may use different triage categories, measure vital signs differently, or serve a different population. Practice can also change after the model is launched.

**Why this matters:** A model can lose accuracy without visibly breaking. Staff may continue trusting a score that no longer reflects local reality.

**What I would do:** Validate the model at every intended site, start in shadow mode, monitor input and outcome drift, and keep a tested rollback process. Success means calibration and safety metrics remain within approved limits at each hospital and review period.

## 3. Automation Bias

When a computer presents a confident recommendation, busy clinicians may accept it even when their own assessment suggests something different. Over time, staff may stop checking the reasoning or feel that overriding the tool will be questioned.

**Why this matters:** Human oversight exists only on paper if the interface or workplace culture encourages automatic agreement.

**What I would do:** Keep the clinician's assessment primary, show missing data and uncertainty, make override easy, train staff using disagreement cases, and review agreement and override patterns without penalising appropriate judgement. Success means clinicians can explain when to disagree and high-risk disagreements receive review.

## Recommendation

Do not proceed directly to automated decision-making. Begin with retrospective validation, followed by a silent-mode pilot in which the model cannot change care. Progress only when subgroup performance, local calibration, workload, and clinician behaviour meet predefined thresholds. If a material safety or equity threshold is breached, pause the system rather than adjusting expectations after harm occurs.
