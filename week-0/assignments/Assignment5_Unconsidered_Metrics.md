# Assignment 5: Unconsidered Metrics

## Overview

The Week 0 dataset includes important triage fields such as age, gender, GCS, blood pressure, pulse, temperature, respiratory rate, and FiO2. These are useful, but they do not capture the full clinical picture.

If this dataset were used for a real triage decision-support system, several additional metrics would be important.

## Metrics Not Included

### Oxygen Saturation

Oxygen saturation, often recorded as SpO2, shows how much oxygen is being carried in the blood. FiO2 tells us how much oxygen a patient is receiving, but SpO2 tells us how well the patient is oxygenating. A patient needing high FiO2 but still having low SpO2 would be high risk.

### Chief Complaint

The reason the patient came to the emergency department is essential. Chest pain, stroke symptoms, severe abdominal pain, trauma, shortness of breath, and fever in a newborn carry different levels of urgency even if some vital signs look similar.

### Pain Score

Pain level can affect triage priority and can also explain changes in heart rate, blood pressure, and respiratory rate. Severe pain may indicate serious injury, infection, or another urgent condition.

### Mental Status Beyond GCS

GCS is useful, but it does not capture every form of confusion, agitation, delirium, intoxication, or psychiatric distress. More detailed mental-status observations could improve clinical interpretation.

### Medical History

Conditions such as heart disease, diabetes, asthma, pregnancy, kidney disease, immunosuppression, and recent surgery can change the meaning of the same vital signs.

### Medication and Allergy Information

Some medications affect pulse and blood pressure. For example, beta blockers may prevent a patient from developing a high pulse even during serious illness. Allergy information is also important for safe treatment planning.

### Time-Based Metrics

Triage decisions often depend on how symptoms are changing. A blood pressure that is dropping over time may be more concerning than one isolated reading.

## Reflection

This exercise shows why clinical AI systems need more than raw numbers. Vital signs are important, but they become safer and more useful when combined with clinical context, patient history, symptoms, and time trends.
