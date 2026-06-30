# Risk Register: AI-Assisted Emergency Department Triage

**Project:** Lightweight clinical decision-support for emergency department triage  
**Purpose:** Identify risks that could affect patient safety, staff workload, trust, privacy, or equitable access before any pilot or deployment.  
**Rating scale:** Likelihood and impact are rated Low (L), Medium (M), or High (H).

This register treats the proposed model as an advisory tool. It must not independently assign a triage category, route a patient, or make an admission or discharge decision.

| # | Risk Name | Category | Likelihood | Impact | Mitigation | Signal of Success |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Under-represented patient groups | AI-technical / Equity | H | H | Measure training-data coverage by age, sex, ethnicity, language, location, disability, and presentation type. Validate sensitivity, specificity, calibration, and false-negative rates for each clinically relevant subgroup. Do not deploy where evidence is inadequate. | No clinically important performance gap between monitored groups; subgroup sample-size requirements are met before use. |
| 2 | Distribution shift between hospitals or over time | AI-technical | H | H | Validate on data from different hospitals and time periods. Monitor input and outcome drift, re-check calibration, and maintain a tested rollback process. | Performance and calibration remain inside agreed limits at every site and review period; drift alerts are investigated on time. |
| 3 | Missing, stale, or incorrect input data | AI-technical / Operational | H | H | Check completeness, units, timestamps, and physiological plausibility. Display missing fields clearly and withhold a confident recommendation when critical inputs are absent. | Fewer incomplete or implausible records reach scoring; all withheld scores state the missing requirement. |
| 4 | False reassurance from a miscalibrated score | AI-technical | M | H | Calibrate predicted risk, display uncertainty, use conservative escalation thresholds, and audit critical false negatives. Require normal clinical reassessment even after a low-risk output. | Critical false-negative rate stays below the approved safety threshold and calibration error remains within limits. |
| 5 | Unsupported or misleading explanation | AI-technical / Ethical | M | H | Use short, evidence-linked explanations based only on model inputs. Never generate clinical facts that were not recorded. Test whether clinicians understand the explanation and can identify missing information. | Explanation audits find no invented facts; clinicians correctly interpret the recommendation and its limitations in usability testing. |
| 6 | Alert fatigue and clinician overload | Operational | H | H | Limit alerts to actionable, high-priority events; suppress duplicates; test thresholds with triage nurses; and review alert burden by shift. | Useful-alert and acknowledgement rates improve while alerts per patient and ignored-alert rates stay within agreed limits. |
| 7 | Poor workflow or EHR integration | Operational | M | H | Co-design with frontline staff, reuse existing data, pilot in shadow mode, measure added time, and provide a downtime workflow. | Median triage time does not materially increase; system uptime and task-completion rates meet the pilot target. |
| 8 | Automation bias and loss of independent judgement | Ethical / Operational | H | H | Require the nurse to record an initial assessment before viewing the recommendation where practical. Keep human override simple, train staff on model limits, and audit agreement and override patterns without punishing appropriate overrides. | Appropriate override remains common enough to demonstrate active judgement; discordant high-risk cases receive review. |
| 9 | Inadequate patient notice and ability to question use | Ethical | M | M | Provide plain-language notice that AI supports, but does not replace, the clinical team. Explain data use, human accountability, and the route for questions or complaints. | Patient understanding improves in short surveys; complaints are acknowledged and resolved within the published timeframe. |
| 10 | Privacy or security breach | Ethical / Operational | M | H | Minimise collected data, apply role-based access, encryption, audit logs, retention limits, staff training, and a tested incident-response plan. | No unauthorised access incidents; access reviews and incident drills are completed and corrective actions close on time. |
| 11 | Language, disability, rural, or digital exclusion | Equity | H | H | Use accessible interfaces, translated materials, interpreter workflows, and representative testing. Do not lower urgency because a patient has sparse prior records or cannot use a digital channel. | Completion, missing-data, and escalation rates show no clinically important disadvantage for monitored access groups. |
| 12 | Harmful feedback loop in resource allocation | Equity / Ethical | M | H | Predict clinical need rather than cost or service use. Audit who receives priority, referral, and follow-up; include patient representatives in impact review; and stop use if inequity increases. | Referral and enrolment rates align with measured clinical need across groups, with no widening outcome disparity after deployment. |

## Governance and Review

- **Owner:** Clinical AI pilot lead, with named clinical safety, data protection, and equity reviewers.
- **Before pilot:** Approve intended use, thresholds, subgroup requirements, downtime process, and stop criteria.
- **During pilot:** Begin in silent or shadow mode. Review safety signals weekly and serious incidents immediately.
- **After pilot:** Compare outcomes, workload, subgroup performance, and unintended effects with the pre-pilot baseline.
- **Stop rule:** Pause the system when a safety threshold is breached, data drift invalidates the model, or the team cannot explain a material disparity.

## Interpretation

A mitigation is not considered complete because a policy exists. Each control is paired with an observable signal so the team can determine whether it is working in practice.
