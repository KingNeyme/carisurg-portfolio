# Assignment 6: Triage Pseudocode

## Goal

Create basic triage logic that uses vital signs and clinical context to identify patients who may need urgent attention.

This pseudocode is not a medical device. It is a training exercise to show how clinical rules can be translated into structured logic.

## Inputs

- Age
- GCS
- SBP
- DBP
- MAP
- Pulse
- Temperature
- Respiratory rate
- FiO2
- Chief complaint, if available
- Oxygen saturation, if available

## Pseudocode

```text
START

Receive patient triage record

Check for missing or invalid values
If a required value is missing:
    Flag record for human review

Set risk_level = "Lower priority"
Set reasons = empty list

If airway, breathing, or circulation concern is present:
    risk_level = "Critical"
    Add "ABC concern" to reasons

If GCS <= 8:
    risk_level = "Critical"
    Add "Severely reduced consciousness" to reasons
Else if GCS <= 14:
    Upgrade risk_level to at least "Urgent"
    Add "Altered consciousness" to reasons

If SBP < 90:
    Upgrade risk_level to at least "Critical"
    Add "Low systolic blood pressure" to reasons
Else if SBP > 180:
    Upgrade risk_level to at least "Urgent"
    Add "Severely elevated systolic blood pressure" to reasons

If pulse < 50 or pulse > 130:
    Upgrade risk_level to at least "Urgent"
    Add "Abnormal heart rate" to reasons

If respiratory_rate < 8 or respiratory_rate > 30:
    Upgrade risk_level to at least "Urgent"
    Add "Abnormal respiratory rate" to reasons

If temperature >= 39.0:
    Upgrade risk_level to at least "Urgent"
    Add "High fever" to reasons

If FiO2 > 21:
    Add "Requires supplemental oxygen" to reasons
    If oxygen saturation is low or respiratory rate is abnormal:
        Upgrade risk_level to at least "Critical"

If patient age is very young or elderly:
    Consider upgrading risk_level by one category
    Add "Age-related risk" to reasons

Return risk_level and reasons

END
```

## Reflection

Good triage logic should provide reasons, not just a score. In healthcare AI, explainability matters because clinicians need to understand why a patient was flagged.

The safest version of this system would support clinicians rather than replace them. It should highlight risk, show the clinical reasons, and allow human review.
