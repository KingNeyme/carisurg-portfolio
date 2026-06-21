# Preliminary Proposal: AI-Assisted Emergency Department Triage

> Source: Google Drive file `Preliminary Proposal.pdf`
>
> This working proposal began in Week 1 and was refined in Weeks 2 and 3. Its bibliography was generated from Zotero in Vancouver style and now contains 10 references.

## 1. Literature Review

### Paper 1: Tyler et al. (2024) — Use of Artificial Intelligence in Triage in Hospital Emergency Departments: A Scoping Review

This paper investigated how artificial intelligence is currently being used within emergency department triage systems. The authors conducted a scoping review examining existing research on machine learning and AI-assisted triage approaches. The review found that AI systems show potential for improving triage accuracy, reducing waiting times, and supporting patient prioritisation. However, the authors noted limitations including limited external validation, retrospective study designs, and uncertainty surrounding real-world implementation.

### Paper 2: Da'Costa et al. (2025) — AI-Driven Triage in Emergency Departments: A Review of Benefits, Challenges, and Future Directions

This review explored the advantages and challenges associated with implementing AI-assisted triage systems within emergency departments. The authors reviewed evidence relating to emergency overcrowding, resource allocation, and decision support. Results suggested that AI may improve operational efficiency and prioritisation accuracy while supporting faster decision-making. However, challenges identified included algorithmic bias, ethical concerns, explainability problems, and insufficient clinical validation.

### Paper 3: Araouchi & Adda (2024) — TriageIntelli: AI-Assisted Multimodal Triage System for Health Centers

This study proposed a multimodal AI-assisted triage system known as TriageIntelli designed to support patient classification using multiple forms of healthcare information. The researchers developed a system combining various inputs to assist healthcare staff with triage decisions. Their findings suggested that multimodal systems may improve patient prioritisation and decision-support capabilities. Limitations included limited real-world deployment and uncertainty regarding large-scale implementation performance.

### Paper 4: Porto (2024) — Improving Triage Performance Using Machine Learning and Natural Language Processing: A Systematic Review

This systematic review examined machine learning and natural language processing methods used to improve emergency department triage performance. The review found that multiple machine learning approaches, including gradient boosting, neural networks, and natural language processing, demonstrated promising predictive performance. Results suggested that these approaches may outperform conventional triage methods under certain conditions. The authors highlighted concerns regarding bias, inconsistent evaluation methods, and limited explainability.

### Paper 5: Feretzakis et al. (2024) — Machine Learning Predictive Models for Emergency Department Disposition

This study investigated machine learning models designed to predict emergency department outcomes using early triage information. The researchers used automated machine learning techniques and structured emergency department data. Results showed that predictive models may assist clinicians in making earlier disposition decisions and prioritising higher-risk patients. Limitations included dependence on retrospective datasets and reduced generalisability across healthcare environments.

### Paper 6: De Freitas et al. (2020) — Qualitative Exploration of Patient Flow in a Caribbean Emergency Department

This paper is directly relevant to the Caribbean clinical context of the proposed project. De Freitas and colleagues explored patient flow in a Caribbean emergency department and highlighted operational pressures that affect emergency care delivery. This source helps ground the proposal in regional healthcare realities rather than relying only on studies from larger or better-resourced health systems. It supports the argument that any AI-assisted triage tool should be designed with local workflow, staffing, and patient-flow constraints in mind.

### Paper 7: Xie et al. (2021) — Benchmarking Emergency Department Triage Prediction Models with Machine Learning and Large Public Electronic Health Records

This study developed benchmark emergency department triage prediction models using large public electronic health records. It is useful because it shows how structured emergency department data can support reproducible model development and comparison across outcomes such as hospitalisation and critical events. The paper also helps address the proposal's need for a practical modelling direction by showing how public or de-identified emergency department datasets can be used for benchmarking before any real-world deployment.

### Paper 8: Kelly et al. (2019) — Key Challenges for Delivering Clinical Impact with Artificial Intelligence

Kelly and colleagues explain why strong model performance is not enough to produce clinical impact. They identify challenges involving data quality, generalisability, regulation, workflow integration, and evaluation in real clinical settings. This paper supports the proposal's focus on a lightweight decision-support tool that must be tested for usability and workflow fit rather than judged only by predictive accuracy.

### Paper 9: Greenhalgh et al. (2017) — The NASSS Framework for Health Technology Adoption

The NASSS framework examines nonadoption, abandonment, scale-up, spread, and sustainability of health technologies. It shows that adoption depends on the clinical condition, the technology, the value proposition, the people using it, the organisation, and the wider system. This framework strengthens the systems-thinking section by showing why an AI tool must fit existing roles, resources, workflows, and organisational capacity.

### Paper 10: Shortliffe and Sepulveda (2018) — Clinical Decision Support in the Era of Artificial Intelligence

This paper discusses how artificial intelligence changes clinical decision support while reinforcing the need for trustworthy integration into care. It is relevant to the proposed system because the model is intended to support, not replace, triage judgement. The paper helps justify requirements for explanation, clinician override, and careful evaluation of how recommendations are presented.

## 2. Gap Analysis

### Gap 1: Limited Real-World Validation

Many AI-assisted triage studies demonstrate promising results using retrospective datasets or controlled research environments. However, relatively few studies evaluate how these systems perform during actual emergency department workflows. This creates uncertainty regarding whether strong research performance translates into practical clinical benefits.

### Gap 2: Limited Explainability and Clinical Integration

Most studies primarily focus on predictive accuracy and performance metrics rather than clinician usability. Emergency healthcare professionals require systems that are understandable, explainable, and compatible with existing workflows. Limited attention has been given to designing systems that clinicians can realistically trust and adopt.

## 3. Preliminary Proposal

### Problem Statement

Emergency departments experience increasing pressure from overcrowding, inconsistent patient prioritisation, and limited clinical resources. Existing research suggests that AI-assisted triage systems may improve prioritisation performance; however, many systems lack sufficient real-world validation and practical clinical integration. This project proposes investigating whether a lightweight machine learning decision-support system using structured emergency department triage data could assist clinicians in identifying higher-risk patients while supporting faster, more consistent prioritisation without replacing clinical judgement.

### Proposed Solution

The proposed pilot will investigate a lightweight AI-assisted triage decision-support system using structured patient intake information including demographics, vital signs, presenting complaint, and triage variables. The model would predict patient urgency or risk level and provide decision-support recommendations to assist healthcare professionals during triage rather than replacing human judgement.

## 4. Workflow and Systems Thinking

### Current ED Triage Workflow

The first-pass workflow follows the patient from arrival through registration, vital-sign capture, triage nurse assessment, priority assignment, waiting/reassessment, clinician assessment, treatment, and disposition.

![Mercer ED triage workflow](../week-3/diagrams/mercer-ed-triage-workflow.svg)

The diagram identifies five possible AI plug-in points:

1. Detect possible duplicate records and missing registration fields.
2. Check vital-sign completeness, timestamps, and physiologic plausibility.
3. Provide an explainable urgency/risk estimate during nurse assessment.
4. Flag patients due for reassessment or at risk of deterioration while waiting.
5. Estimate admission or resource demand to support flow planning.

The AI functions remain advisory. They do not independently assign triage level, route a patient, or make admission/discharge decisions.

### Constraints and Stakeholders

#### Constraint 1: Limited Nurse Time

Triage work is interruption-driven. Any AI tool must use information already captured, respond quickly, and avoid adding duplicate documentation.

#### Constraint 2: Missing or Delayed Data

The model must show when vital signs are missing, stale, or implausible. It should not provide a confident score when critical inputs are unavailable.

#### Constraint 3: Capacity and Queue Limits

An urgency prediction cannot create staff, beds, diagnostics, or transport. The tool must support clinical prioritisation without presenting capacity problems as modelling failures.

| Stakeholder | Primary concern |
| --- | --- |
| Triage nurse | Fast, explainable support that is easy to override |
| ED consultant/physician | Clinically credible recommendations with visible missing data |
| Registration/admin staff | Accurate patient identity without delaying urgent care |
| Porter/bed-flow coordinator | Routing recommendations that reflect real destination capacity |
| Patient advocate/patient representative | Fairness, dignity, accessibility, privacy, and protection from bias |

### Summary of Previous Work

Previous research demonstrates growing interest in AI-assisted emergency department triage. Studies consistently show that machine learning approaches may improve prioritisation accuracy, operational efficiency, and risk prediction. However, existing literature also demonstrates challenges relating to validation, explainability, bias, and workflow integration. These findings suggest opportunities for investigating practical decision-support systems that remain clinically usable.

## References

1. Da'Costa A. AI-Driven Triage in Emergency Departments: A Review of Benefits, Challenges, and Future Directions. 2025.
2. Xie F, Zhou J, Lee JW, Tan M, Li S, Rajnthern LS, et al. Benchmarking emergency department triage prediction models with machine learning and large public electronic health records [Internet]. 2021. Available from: https://arxiv.org/abs/2111.11017
3. Greenhalgh T, Wherton J, Papoutsi C, Lynch J, Hughes G, A'Court C, et al. Beyond Adoption: A New Framework for Theorizing and Evaluating Nonadoption, Abandonment, and Challenges to the Scale-Up, Spread, and Sustainability of Health and Care Technologies. Journal of Medical Internet Research. 2017;19(11):e367. doi:10.2196/jmir.8775
4. Shortliffe EH, Sepulveda MJ. Clinical Decision Support in the Era of Artificial Intelligence. JAMA. 2018;320(21):2199-2200. doi:10.1001/jama.2018.17163
5. Porto BM. Improving Triage Performance Using Machine Learning and Natural Language Processing: A Systematic Review. 2024.
6. Kelly CJ, Karthikesalingam A, Suleyman M, Corrado G, King D. Key challenges for delivering clinical impact with artificial intelligence. BMC Medicine. 2019;17:195. doi:10.1186/s12916-019-1426-2
7. Feretzakis G. Machine Learning Predictive Models for Emergency Department Disposition. 2024.
8. De Freitas L, Goodacre S, O'Hara R, Thokala P, Hariharan S. Qualitative exploration of patient flow in a Caribbean emergency department. BMJ Open. 2020;10(12):e041422. doi:10.1136/bmjopen-2020-041422
9. Araouchi Z, Adda M. TriageIntelli: AI-Assisted Multimodal Triage System for Health Centers. 2024.
10. Tyler S. Use of Artificial Intelligence in Triage in Hospital Emergency Departments: A Scoping Review. 2024.
