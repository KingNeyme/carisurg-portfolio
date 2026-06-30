# LinkedIn Draft: AI Should Strengthen Clinical Judgement, Not Quietly Replace It

As I continue my CariSurg Healthcare AI training, one question keeps coming up: should AI augment clinical work, or should it replace parts of it?

My current position is that AI should support high-stakes clinical judgement, while carefully defined, lower-risk tasks may be automated. That difference matters because a hospital is not a controlled spreadsheet. Patients arrive with incomplete histories, changing symptoms, language barriers, and needs that may not fit neatly into a model's training data.

Take emergency triage as one example. An AI system could check whether vital signs are missing, entered in the wrong unit, too old to rely on, or physiologically implausible. It could quietly catch a blood pressure value that was mistyped or remind the team that a waiting patient's observations are due for reassessment. This is useful augmentation because it reduces avoidable data-quality errors without pretending to understand the whole patient.

A second scenario is an urgency prediction. A model could combine recorded vital signs, age, presenting complaint, and triage information to flag a patient who may need faster review. However, I would not want the model to assign the final triage category on its own. A nurse may notice confusion, difficulty breathing, pain behaviour, or a rapid change that is not fully represented in the structured data. The AI recommendation should be explainable, should show missing information and uncertainty, and should be easy to override.

This is also where automation bias becomes important. A human being "in the loop" is not enough if staff are too busy to question the score, if overrides are discouraged, or if the screen presents the model as more certain than it is. Real oversight requires time, training, authority, and a workflow that expects thoughtful disagreement.

The same caution applies to fairness. A model trained mostly on older adults from one urban hospital may be less reliable for children or rural communities. Reporting one overall accuracy score would not reveal that. I would want to see performance by relevant patient group, evidence from each intended hospital, and a clear rule for pausing the system if a disparity appears.

The World Health Organization's guidance on AI for health strengthened my view that safety, transparency, accountability, autonomy, and equity have to be designed into the system from the beginning. They cannot be added after a model is already influencing care.

I do believe some tasks can become more automated. Duplicate-record checks, routine completeness checks, administrative coding support, and queue reminders may be reasonable candidates when they are well tested and have a safe fallback. My uncertainty is where that boundary will sit in the future. Better evidence and stronger monitoring may justify more automation for narrow tasks. I am less certain that broad clinical decisions, especially triage, can be safely separated from context and professional judgement.

For now, my standard is simple: automate where failure is visible and recoverable; augment where decisions are high stakes; and keep a qualified person accountable for the patient.

#HealthcareAI #ClinicalAI #AIEngineering #PatientSafety #ResponsibleAI #CariSurg

**Approximate word count:** 500
