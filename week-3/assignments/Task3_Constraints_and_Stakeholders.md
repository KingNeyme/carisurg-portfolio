# Task 3: Constraints and Stakeholders

## Three Major Workflow Constraints

### Constraint 1: Limited Nurse Time and Interruption-Driven Work

Triage nurses must assess patients quickly while responding to interruptions, questions, deteriorating patients, phone calls, and handoffs. An AI tool that requires extra screens, repeated data entry, or lengthy explanations could slow the workflow rather than improve it.

Design mitigation:

- use information already captured during triage
- return a short risk signal with the main contributing factors
- require no more than one confirmation or override action

Pilot measurement:

- median time added to each triage assessment
- alert acknowledgement/override rate
- nurse-reported usefulness

### Constraint 2: Delayed, Missing, or Inconsistent Clinical Data

Vital signs and chief-complaint information may be captured on paper, entered later, measured with unavailable equipment, or recorded inconsistently. A model cannot safely score a patient when required inputs are missing or stale.

Design mitigation:

- show data completeness and timestamp
- refuse to produce a confident score when critical fields are missing
- flag physiologically implausible values for recheck

Pilot measurement:

- percentage of triage records with complete required fields
- time between measurement and electronic entry
- number of values corrected after validation prompts

### Constraint 3: Capacity and Queue Constraints

An AI system may correctly identify urgency but cannot create treatment spaces, staff, diagnostics, transport, or inpatient beds. If the system raises priority without considering available resources, it may move the bottleneck rather than improve patient flow.

Design mitigation:

- keep the model focused on decision support, not automatic routing
- display queue and capacity context separately from clinical risk
- preserve nurse/clinician authority over final priority and placement

Pilot measurement:

- time from triage to clinician assessment by acuity
- number of priority changes
- waiting-room deterioration events
- staff reports of alert overload or queue disruption

## Five Clinical Stakeholders

| Stakeholder | Role in workflow | Top concern |
| --- | --- | --- |
| Triage nurse | Collects observations, assesses urgency, assigns priority, and initiates routing | The tool must be fast, explainable, and easy to override without adding documentation burden |
| ED consultant/physician | Reviews the patient, makes diagnostic/treatment decisions, and accepts clinical responsibility | The risk signal must be clinically credible and must not hide missing data or create false reassurance |
| Registration/admin staff | Creates the patient record and captures identity/demographic information | The system must avoid duplicate records and must not make administrative delays block emergency care |
| Porter/bed-flow coordinator | Moves patients and supports transfer to diagnostics, wards, or other destinations | Routing recommendations must reflect real destination and transport availability |
| Patient advocate/patient representative | Protects patient understanding, fairness, dignity, and access | The system must not disadvantage patients because of language, disability, ethnicity, age, gender, or incomplete records |

## Proposed AI Plug-In Points

| Workflow point | AI function | Guardrail |
| --- | --- | --- |
| Registration | Detect possible duplicates and missing demographic fields | Must never delay emergency clinical care |
| Vital-sign capture | Flag missing, stale, or physiologically implausible values | Prompt recheck; do not silently correct clinical data |
| Triage assessment | Provide an explainable urgency/risk estimate | Nurse makes the final triage decision and records override reason |
| Waiting/reassessment | Identify patients due for reassessment or showing possible deterioration | Alert thresholds must be configurable to avoid alarm fatigue |
| Disposition/flow planning | Estimate admission or resource needs to support planning | Prediction must not become an automatic admission/discharge decision |

## Responsible AI Position

The proposed system is a decision-support tool. It should not replace triage judgement, automatically change acuity, or independently route a patient. Clinicians must be able to understand the main factors behind a score, reject the recommendation, and continue safely during downtime.
