# Preliminary Proposal: AI-Assisted Emergency Department Triage

> Source: Google Drive file `Preliminary Proposal.pdf`
>
> This working proposal began in Week 1 and was refined through Week 4. It now combines the literature review, proposed solution, workflow analysis, stakeholder constraints, and a measurable safety and equity risk analysis. The bibliography contains 15 references.

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

### Paper 11: Obermeyer et al. (2019) — Racial Bias in a Population Health Algorithm

Obermeyer and colleagues showed that a widely used population health algorithm produced substantial racial bias because it predicted healthcare cost rather than illness. At the same score, Black patients were sicker than White patients, yet were less likely to receive additional care-management support. This case demonstrates why a convenient proxy can reproduce structural inequity even when the model performs well against its selected target. It directly informs the proposed system's requirement to define urgency using clinical need and to audit false negatives and outcomes by subgroup.

### Paper 12: World Health Organization (2021) — Ethics and Governance of Artificial Intelligence for Health

The WHO guidance places ethics and human rights at the centre of health AI design, deployment, and governance. Its principles cover autonomy, safety and public benefit, transparency, accountability, inclusiveness and equity, and responsive sustainability. This source provides the ethical framework for keeping the triage model advisory, informing patients appropriately, assigning clear accountability, and monitoring whether benefits and harms are distributed fairly.

### Paper 13: Wiens et al. (2019) — Do No Harm: A Roadmap for Responsible Machine Learning for Health Care

Wiens and colleagues argue that translation from model development to patient care requires engaged stakeholders and a systematic process from problem formulation through deployment. The paper supports staged validation, clinician involvement, prospective testing, and post-deployment monitoring. These recommendations strengthen the proposal's plan to start in retrospective and shadow modes before allowing the model to influence workflow.

### Paper 14: Amann et al. (2020) — Explainability for Artificial Intelligence in Healthcare

This multidisciplinary analysis examines explainability from technical, medical, legal, and ethical perspectives. It emphasises that explanations can help clinicians evaluate recommendations and investigate disagreement with a system. For the proposed tool, this means presenting a concise reason for an urgency estimate, showing missing inputs and uncertainty, and testing whether clinicians interpret the explanation correctly rather than assuming that any explanation creates trust.

### Paper 15: Vokinger et al. (2021) — Mitigating Bias in Machine Learning for Medicine

Vokinger and colleagues describe how bias can enter during data collection, preparation, model development, evaluation, and deployment. They recommend mitigation across the full lifecycle rather than relying on a single fairness metric. This supports representative data review, independent subgroup evaluation, site-specific validation, and monitoring after deployment.

## 2. Gap Analysis

### Gap 1: Limited Real-World Validation

Many AI-assisted triage studies demonstrate promising results using retrospective datasets or controlled research environments. However, relatively few studies evaluate how these systems perform during actual emergency department workflows. This creates uncertainty regarding whether strong research performance translates into practical clinical benefits.

### Gap 2: Limited Explainability and Clinical Integration

Most studies primarily focus on predictive accuracy and performance metrics rather than clinician usability. Emergency healthcare professionals require systems that are understandable, explainable, and compatible with existing workflows. Limited attention has been given to designing systems that clinicians can realistically trust and adopt.

### Gap 3: Limited Equity and Post-Deployment Evidence

Published performance can conceal clinically important differences between patient groups and hospitals. Few studies show how triage tools will be monitored for subgroup false negatives, distribution shift, automation bias, or inequitable resource allocation after deployment. This proposal therefore treats subgroup evaluation and post-deployment monitoring as core safety requirements rather than optional future work.

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

## 5. Risk Analysis

The proposed system is a high-stakes decision-support tool. Its risks therefore include more than prediction error. Harm could arise from unrepresentative data, a change in the patient population, missing inputs, poor workflow integration, over-trust in the recommendation, privacy failures, or an unequal effect on patients with limited access to care.

### Risk Register

| # | Risk | Category | L | I | Primary Mitigation | Signal of Success |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Under-represented patient groups | Technical / Equity | H | H | Subgroup coverage and performance testing; no deployment where evidence is inadequate | No clinically important gap in sensitivity or false negatives |
| 2 | Distribution shift | Technical | H | H | Site and time validation, drift monitoring, rollback | Calibration and safety metrics remain inside limits by site |
| 3 | Missing, stale, or incorrect inputs | Technical / Operational | H | H | Unit, timestamp, completeness, and plausibility checks | Fewer invalid records reach scoring; unsafe scores are withheld |
| 4 | False reassurance from miscalibration | Technical | M | H | Calibrated probabilities, visible uncertainty, critical false-negative audit | Calibration and false-negative rates meet safety thresholds |
| 5 | Misleading explanation | Technical / Ethical | M | H | Input-grounded explanations and clinician comprehension testing | No invented facts; limitations are interpreted correctly |
| 6 | Alert fatigue | Operational | H | H | Actionable alerts, duplicate suppression, nurse-led threshold review | Useful-alert rate improves and ignored alerts decline |
| 7 | Poor workflow or EHR integration | Operational | M | H | Co-design, shadow mode, added-time measurement, downtime plan | Triage time does not materially increase; uptime meets target |
| 8 | Automation bias | Ethical / Operational | H | H | Independent assessment, simple override, training, disagreement audit | Appropriate overrides occur and high-risk disagreements are reviewed |
| 9 | Inadequate patient notice | Ethical | M | M | Plain-language notice, accountability, and complaint route | Patient understanding and complaint-resolution targets are met |
| 10 | Privacy or security breach | Ethical / Operational | M | H | Data minimisation, access control, encryption, logs, response plan | No unauthorised access; reviews and drills close actions on time |
| 11 | Access-related exclusion | Equity | H | H | Accessible and translated workflows; no penalty for sparse records | No material disadvantage in completion or escalation rates |
| 12 | Harmful resource-allocation feedback loop | Equity / Ethical | M | H | Predict clinical need, audit decisions and outcomes, stop on disparity | Referral and enrolment align with clinical need across groups |

The detailed register, ownership model, review frequency, and stop rule are maintained in [`risk-register.md`](risk-register.md).

### Risk Memo: Top Three

**Under-represented patient groups.** A model can look accurate overall while missing high-risk patients from groups that appeared rarely in the training data. Before any deployment, performance must be reported separately for clinically important groups, and the tool must not be used where evidence is inadequate.

**Distribution shift.** A model trained at one hospital may not transfer safely to another hospital with different patients, equipment, documentation, or workflow. Every site requires local validation, a silent-mode pilot, drift monitoring, and a tested rollback process.

**Automation bias.** A human in the loop does not guarantee real oversight. Busy clinicians may accept a confident recommendation unless the workflow supports independent assessment, makes uncertainty visible, and protects appropriate override. Disagreement cases should be reviewed as learning and safety evidence.

### Safety Position and Deployment Gate

The system should begin with retrospective evaluation, then progress to silent or shadow-mode testing in which recommendations cannot alter patient care. A clinical governance group should approve intended use, subgroup requirements, thresholds, downtime procedures, and stop criteria before any live pilot. Deployment should pause when a safety threshold is breached, drift invalidates performance, or a material disparity cannot be explained and corrected.

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
11. Obermeyer Z, Powers B, Vogeli C, Mullainathan S. Dissecting racial bias in an algorithm used to manage the health of populations. Science. 2019;366(6464):447-453. doi:10.1126/science.aax2342
12. World Health Organization. Ethics and governance of artificial intelligence for health. Geneva: World Health Organization; 2021. ISBN: 9789240029200.
13. Wiens J, Saria S, Sendak M, Ghassemi M, Liu VX, Doshi-Velez F, et al. Do no harm: a roadmap for responsible machine learning for health care. Nature Medicine. 2019;25:1337-1340. doi:10.1038/s41591-019-0548-6
14. Amann J, Blasimme A, Vayena E, Frey D, Madai VI. Explainability for artificial intelligence in healthcare: a multidisciplinary perspective. BMC Medical Informatics and Decision Making. 2020;20:310. doi:10.1186/s12911-020-01332-6
15. Vokinger KN, Feuerriegel S, Kesselheim AS. Mitigating bias in machine learning for medicine. Communications Medicine. 2021;1:25. doi:10.1038/s43856-021-00028-w
