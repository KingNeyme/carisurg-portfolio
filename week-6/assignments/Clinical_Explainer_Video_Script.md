# 1-Minute Clinical Explainer Video Script

## Recording Note

This is written for a 1-minute Loom or phone video to Dr. Reyes. The assignment asks us to avoid ML jargon, so the script does not use the words F1, precision, or recall.

## Script

Dr. Reyes, for this first triage model, I am not judging it mainly by how often it is right overall.

The safer question is this: when a patient truly needs immediate life-saving attention, does the model recognise that patient as immediate?

For example, imagine a patient arriving with airway compromise, severe shock, or a cardiac arrest-type presentation. If the model labels that patient as less urgent, the harm is not just a wrong label. It could mean delayed resuscitation, delayed senior review, or delayed movement to the right clinical space.

That is why I focused on the highest triage level first. In the test set, the logistic regression baseline correctly flagged 782 out of 1,054 actual highest-urgency cases. That is much better than the random baseline, but it still missed 272 of them, so I would not call this ready for clinical use.

My recommendation is to treat this as a safety baseline. It proves there is useful signal in the data, but the next step should be clinician review of the missed highest-urgency cases before anyone thinks about deployment.

## Short Discord Caption

> Week 6 Loom: I explained why the model should be judged first by whether it catches true ESI 1 patients, not by overall accuracy. The baseline is promising but not deployment-ready because missed highest-urgency cases still carry serious patient-safety risk.

