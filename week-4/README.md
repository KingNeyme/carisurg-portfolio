# Week 4: Ethics, Safety and Risk Awareness

Week 4 asks a harder question than whether an AI model can make a useful prediction: **what could go wrong, who could be harmed, and how would we know whether our safeguards are actually working?**

The work applies ethics and safety analysis to the proposed AI-assisted emergency department triage system. The system remains decision support. A clinician keeps responsibility for assessment, prioritisation, and escalation.

## Week Theme

**Responsible clinical AI requires measurable safeguards, not good intentions.**

## Objectives

- Identify 8-12 technical, operational, ethical, and equity risks.
- Rate each risk by likelihood and impact.
- Pair every mitigation with a measurable signal of success.
- Explain the three highest-priority risks in plain language.
- Analyse one documented case of healthcare AI harm.
- Add a risk analysis section and 15+ references to the proposal.
- State a personal position on AI augmentation versus replacement.
- Prepare the required Discord and LinkedIn engagement drafts.

## Assignment Map

| Task | Status | Evidence |
| --- | --- | --- |
| Risk register with 12 named risks | Complete | [`../docs/risk-register.md`](../docs/risk-register.md) |
| Top-three risk memo | Complete | [`assignments/Risk_Memo_Top_3.md`](assignments/Risk_Memo_Top_3.md) |
| AI harm case study, 400-600 words | Complete | [`../docs/week-4-ai-harm-case-study.md`](../docs/week-4-ai-harm-case-study.md) |
| Proposal risk analysis | Complete | [`../docs/week-1-preliminary-proposal.md`](../docs/week-1-preliminary-proposal.md) |
| Literature expanded to 15 sources | Complete | [`../docs/week-1-bibliography.md`](../docs/week-1-bibliography.md) |
| Zotero import pack for five new sources | Complete | [`assignments/week-4-zotero-import.ris`](assignments/week-4-zotero-import.ris) |
| Discord post and three peer responses | Drafts ready to personalise and publish | [`assignments/Peer_Engagement_Drafts.md`](assignments/Peer_Engagement_Drafts.md) |
| Career article summary and personal position | Complete | [`assignments/Career_Challenge_Ethics_Reflection.md`](assignments/Career_Challenge_Ethics_Reflection.md) |
| 500-word LinkedIn stance post | Draft ready to publish | [`assignments/LinkedIn_AI_Augmentation_vs_Replacement.md`](assignments/LinkedIn_AI_Augmentation_vs_Replacement.md) |

## Main Findings

The three highest-priority risks are under-representation in the training data, distribution shift across hospitals, and automation bias. All three can make a system appear useful while quietly producing unsafe decisions. The proposed controls therefore combine subgroup evaluation, site-specific validation, drift monitoring, visible uncertainty, clinician override, and explicit stop rules.

The real-world harm case reinforces the same lesson. An algorithm may perform well against its chosen label and still fail patients when the label is only a proxy for clinical need.

## Final Deliverables

- [Google Drive PDF for platform submission](https://drive.google.com/file/d/1MwKcn3iNJNRxPhTuPe1oPpNPx6qebhG4/view?usp=drivesdk)
- [Editable Google Docs report](https://docs.google.com/document/d/1F0EwK1_MvyBlQf_A1gXN8yIDVPs0qqCIU8-qk5pR1DE/edit?usp=drivesdk)
- [GitHub portfolio repository](https://github.com/KingNeyme/carisurg-portfolio)

## Submission Checklist

- [x] Risk register committed as Markdown
- [x] Top-three risk memo completed
- [x] Documented harm case completed with a verified source
- [x] Proposal refined with workflow, stakeholders, constraints, and risk analysis
- [x] Literature expanded to 15 sources
- [x] Final report prepared for PDF submission
- [ ] Publish the Discord risk post
- [ ] Respond to three classmates with specific, evidence-based comments
- [ ] Publish the LinkedIn post
- [ ] Submit the public Google Drive PDF link on the learning platform

## Reflection

This week changed how I think about model quality. Accuracy is not enough. A safe clinical AI system needs the right target, representative evidence, a place in the real workflow, clear human accountability, and monitoring that can reveal harm after launch. The strongest design decision in this project is keeping the tool advisory and making uncertainty visible instead of allowing a score to look more certain than the evidence supports.
