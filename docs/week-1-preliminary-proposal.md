# Preliminary Proposal: AI-Assisted Emergency Department Triage

> Source: Google Drive file `Preliminary Proposal.pdf`
>
> Week 2 note: this document is the repo copy of the Week 1 proposal. The bibliography was regenerated from Zotero in Vancouver style and expanded to 7 references.

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

### Summary of Previous Work

Previous research demonstrates growing interest in AI-assisted emergency department triage. Studies consistently show that machine learning approaches may improve prioritisation accuracy, operational efficiency, and risk prediction. However, existing literature also demonstrates challenges relating to validation, explainability, bias, and workflow integration. These findings suggest opportunities for investigating practical decision-support systems that remain clinically usable.

## References

1. Da'Costa A. AI-Driven Triage in Emergency Departments: A Review of Benefits, Challenges, and Future Directions. 2025.
2. Xie F, Zhou J, Lee JW, Tan M, Li S, Rajnthern LS, et al. Benchmarking emergency department triage prediction models with machine learning and large public electronic health records [Internet]. 2021. Available from: https://arxiv.org/abs/2111.11017
3. Porto BM. Improving Triage Performance Using Machine Learning and Natural Language Processing: A Systematic Review. 2024.
4. Feretzakis G. Machine Learning Predictive Models for Emergency Department Disposition. 2024.
5. De Freitas L, Goodacre S, O'Hara R, Thokala P, Hariharan S. Qualitative exploration of patient flow in a Caribbean emergency department. BMJ Open. 2020;10(12):e041422. doi:10.1136/bmjopen-2020-041422
6. Araouchi Z, Adda M. TriageIntelli: AI-Assisted Multimodal Triage System for Health Centers. 2024.
7. Tyler S. Use of Artificial Intelligence in Triage in Hospital Emergency Departments: A Scoping Review. 2024.
