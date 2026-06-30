# Peer Engagement Drafts

These are publication-ready starting points. The three replies must be adapted to the specific risk each classmate posts before sending.

## Discord Post: High-Priority Risk

One of my highest-priority risks is **distribution shift**. A triage model trained at one hospital may learn that site's patient population, documentation habits, equipment, and thresholds. If it is moved to another hospital, or if practice changes over time, the model may keep producing confident scores even after its performance has declined.

My proposed mitigation is site-specific validation, a silent-mode pilot, continuous monitoring of input drift and clinical outcomes, and a tested rollback process. The signal I would monitor is whether subgroup sensitivity and calibration remain inside agreed limits at each hospital and review period.

The question I am still testing is: what should the automatic stop threshold be when the overall model looks stable but one patient group's false-negative rate worsens?

## Peer Response 1: Support With Evidence

I agree that **[peer's risk]** deserves a high priority. The WHO ethics guidance is useful here because it treats safety, accountability, and equity as governance responsibilities, not only technical checks. One measurable signal you could add is **[specific metric]**, reviewed separately for **[relevant patient group or clinical setting]**. That would make it easier to tell whether the mitigation is working rather than only documenting that it exists.

## Peer Response 2: Challenge With a Counter-Scenario

Your mitigation makes sense under normal conditions, but I wonder how it performs during **[downtime, overcrowding, missing-data, or night-shift scenario]**. For example, if **[counter-scenario]**, could the control fail or increase staff workload? A fallback process and a stop threshold might strengthen the risk response.

## Peer Response 3: Test Human Oversight

I like that you kept a human in the loop. I would still test whether the person has enough time, information, and authority to disagree with the model. Could you measure override rate, review high-risk disagreements, and ask staff to explain the model's limits during usability testing? That would show whether oversight is active in practice rather than only present in the policy.

## Evidence Link for a Reply

Wiens and colleagues argue that responsible healthcare machine learning requires engaged stakeholders and a systematic process from problem definition through deployment. This supports testing the clinical workflow and governance around a model, not only its accuracy.

Wiens J, Saria S, Sendak M, et al. Do no harm: a roadmap for responsible machine learning for health care. Nature Medicine. 2019;25:1337-1340. doi:10.1038/s41591-019-0548-6
