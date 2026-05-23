# Assignment 4: Vital Sign Description

## Selected Vital Sign

Pulse, also called heart rate, measures how many times the heart beats per minute.

## Plain-Language Description

Pulse is one of the fastest ways to understand how hard the body is working. A normal adult resting pulse is often around 60 to 100 beats per minute, but emergency department patients may fall outside that range because of pain, fear, infection, blood loss, dehydration, heart problems, fever, medication effects, or physical stress.

In a triage setting, pulse helps clinicians decide how urgently a patient may need attention. A very fast pulse can suggest shock, sepsis, bleeding, fever, anxiety, or cardiac strain. A very slow pulse can also be dangerous, especially if the patient is dizzy, confused, weak, or has low blood pressure.

## Why It Matters For Clinical AI
Pulse should not be interpreted by itself. A pulse of 120 bpm may be less concerning in a nervous young adult with normal blood pressure than in an older patient with fever, low blood pressure, and confusion. For an AI system, pulse becomes more meaningful when combined with other measurements such as blood pressure, temperature, respiratory rate, oxygen needs, age, and Glasgow Coma Scale.

## Data Cleaning Considerations

For this Week 0 dataset, I treated `20-250 bpm` as the valid range for pulse. Values outside that range were treated as invalid for the training exercise and replaced with missing values before imputation. I used the median for imputation because vital-sign data can contain extreme values, and the median is less affected by those extremes than the mean.
