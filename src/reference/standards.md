# Appendix B: Standards Alignment

This appendix documents how VERA concepts and practices align with five major external frameworks. The mappings serve two purposes: they help practitioners in regulated or standards-oriented environments connect VERA work to existing compliance obligations, and they help organizations that already operate within these frameworks understand how VERA extends and operationalizes what those frameworks require.

None of the frameworks below require VERA specifically. VERA is designed to satisfy and in many cases exceed their epistemic quality requirements. Where VERA goes further than a framework, this is noted. Where a framework addresses something VERA does not, that gap is also noted.

---

## NIST AI Risk Management Framework (AI RMF)

### About the AI RMF

The NIST AI Risk Management Framework (NIST AI 100-1, released 2023) provides voluntary guidance for managing risks associated with AI systems across their development and deployment lifecycle. It organizes AI risk management around four functions: **GOVERN**, **MAP**, **MEASURE**, and **MANAGE**. Each function contains categories and subcategories addressed by specific actions and outcomes.

VERA is relevant to organizations implementing the AI RMF because AI-generated claims — conclusions, recommendations, predictions, and analyses produced by AI systems — are the epistemic objects at risk in AI-assisted decision making. VERA's verification and sovereignty requirements directly address the traceability, transparency, and human oversight gaps that the AI RMF aims to close.

### Mapping Table

| AI RMF Function & Category | AI RMF Requirement (summary) | VERA Mechanism |
|---|---|---|
| **GOVERN 1.1** | Policies, processes, and procedures for AI risk management established | VERA Governance domain (Level 3+): documented VERA policy, named ownership, significance threshold, training requirement |
| **GOVERN 1.2** | Accountability for AI risk established | VERA Governance domain: VERA owner role with formal accountability; Level 4: board-level epistemic quality reporting |
| **GOVERN 1.4** | Organizational culture supports responsible AI | VERA's sovereignty principles institutionalized at Level 3+; challenge process (S3) ensures culture permits disagreement |
| **GOVERN 2.2** | Risk management processes take scientific findings into account | VERA's Evidence Primacy principle; evidence quality tier system; Secondary and Primary evidence requirements |
| **GOVERN 4.1** | AI RMF integrated into enterprise risk management | VERA Integration domain (Level 4): VERA metrics in governance reporting; decision gates requiring verified claims |
| **MAP 1.5** | Organizational risk tolerance established | Significance threshold (which claims require VERA treatment) operationalizes risk tolerance for epistemic decisions |
| **MAP 2.1** | Scientific and research knowledge reviewed | VERA evidence assembly (Phase 2): prospective search plan, quality rating, independence assessment |
| **MAP 3.5** | AI system risks documented | VERA Claim records document the evidence and reasoning underlying AI-system risk assessments |
| **MAP 5.1** | Likelihood and impact of AI risks assessed | VERA confidence ratings (0.0–1.0) and verification state provide quantified epistemic risk assessment |
| **MEASURE 1.1** | AI risk measurement approaches identified | VERA Verification Protocol: explicit, versioned measurement criteria (E1–E5, R1–R5, F1–F3) |
| **MEASURE 2.2** | AI system trustworthiness characteristics evaluated | VERA reasoning chain transparency (Reasoning Sovereignty, S2): AI reasoning captured and independently evaluated |
| **MEASURE 2.5** | AI system performance evaluated | VERA verification of AI-generated claims (VERA-P-0003): Tier A/B/C handling with documented chain of custody |
| **MEASURE 2.8** | Risks associated with AI system use monitored | VERA review cadence, decay class system (VERA-P-0005), and cascading claim update (VERA-P-0012) |
| **MEASURE 4.1** | Measurement results documented | VERA Verification Records: immutable, per-criterion documentation of every verification event |
| **MANAGE 1.3** | Responses to AI risks prioritized | VERA impact triage (VERA-P-0012): High/Moderate/Low classification determines response urgency |
| **MANAGE 2.4** | AI risk treatment plans developed | VERA sovereignty assessment: documented gaps with owner accountability and remediation timelines |
| **MANAGE 4.2** | Residual AI risks tracked | VERA claim registry with verification state and confidence tracking; stale claim monitoring |

### Where VERA Exceeds AI RMF Requirements

- **Reasoning chain explicitness:** The AI RMF requires transparency; VERA specifies a step-by-step structure for reasoning chains that goes beyond general transparency requirements.
- **Evidence independence assessment:** VERA's source collapse detection (VERA-P-0004) has no direct AI RMF equivalent; it addresses an evidence quality failure mode the AI RMF does not name.
- **Sovereignty as a binding constraint:** VERA's five sovereignty principles are stronger than the AI RMF's accountability and transparency requirements, which do not explicitly address the ability of affected parties to challenge conclusions.

### Where AI RMF Addresses More Than VERA

- **Technical AI risk categories** (bias, robustness, security, privacy): The AI RMF addresses the full range of AI-specific technical risks. VERA addresses the epistemic quality of claims about those risks, not the risks themselves.
- **AI system lifecycle governance:** The AI RMF addresses procurement, deployment, monitoring, and decommissioning of AI systems. VERA addresses the claims made about and by those systems.

---

## EU AI Act

### About the EU AI Act

The EU AI Act (Regulation 2024/1689, fully applicable from August 2026) establishes a tiered regulatory regime for AI systems based on risk level. High-risk AI systems — those with significant impacts on health, safety, fundamental rights, or critical infrastructure — face mandatory requirements including technical documentation, transparency, human oversight, and accuracy standards. General-purpose AI model providers also face specific obligations.

VERA is particularly relevant to organizations developing or deploying high-risk AI systems, for whom claims about AI system performance, risk, and fitness for purpose must be documented to a standard that supports regulatory review.

### Mapping Table: High-Risk AI System Requirements

| EU AI Act Article | Requirement | VERA Mechanism |
|---|---|---|
| **Art. 9 — Risk Management** | Risk management system identifying, analyzing, estimating, and evaluating risks throughout the lifecycle | VERA claim registry: documented, verified claims about risk levels; VERA-P-0012 for lifecycle monitoring |
| **Art. 10 — Data Governance** | Training, validation, and testing data practices; data quality criteria | VERA evidence quality framework applied to data quality claims: Primary-tier evidence required for data governance assertions |
| **Art. 11 — Technical Documentation** | Documentation enabling assessment of system compliance before market placement | VERA claim records serve as the epistemic component of technical documentation; each claim traceable to evidence and reasoning |
| **Art. 12 — Record-Keeping** | Automatic logging of system operation; records retained for review | VERA Verification Records: immutable documentation of verification events; claim registry audit trail |
| **Art. 13 — Transparency** | AI system information disclosed to deployers; operation understandable to users | VERA Reasoning Sovereignty (S2): reasoning chains made visible to affected parties; VERA-P-0003 for AI-generated claim documentation |
| **Art. 14 — Human Oversight** | Measures enabling human monitoring, interpretation, and override of AI outputs | VERA Conclusion Sovereignty (S3): challenge process for verified claims; human verifier requirement in Phase 4 |
| **Art. 15 — Accuracy, Robustness, Cybersecurity** | Performance levels documented; system behavior predictable and resistant to manipulation | VERA confidence ratings document performance epistemic uncertainty; VERA-P-0013 calibration ensures confidence ratings are meaningful |
| **Art. 50 — Transparency for Certain AI** | AI-generated content disclosed; interaction with AI disclosed | VERA-P-0003: mandatory AI provenance documentation for all AI-contributed evidence |
| **Art. 53 — General-Purpose AI Model Providers** | Technical documentation, training data summary, copyright policy | VERA evidence documentation practices applicable to training data claims and capability claims |

### Where VERA Exceeds EU AI Act Requirements

- **Evidence chain-of-custody:** VERA requires documented chain of custody for every evidence item. The EU AI Act requires technical documentation but does not specify evidence provenance standards at the item level.
- **Independent verification:** VERA requires that verification be conducted by someone other than the claimant (at Peer or Expert independence level for significant claims). The EU AI Act does not specify who must conduct conformity assessment for internal quality systems.
- **Reasoning chain explicitness:** Art. 13 requires transparency at the system output level; VERA requires step-by-step reasoning chain documentation for any claim about the system.

### Where the EU AI Act Addresses More Than VERA

- **Legal obligations and enforcement:** The EU AI Act is binding law with penalties. VERA is a voluntary framework. VERA evidence and reasoning documentation can support compliance demonstrations but does not itself constitute legal compliance.
- **Conformity assessment procedures:** Specific third-party assessment requirements for some high-risk AI categories have no VERA equivalent.
- **AI system registration and market surveillance:** Regulatory infrastructure requirements are outside VERA's scope.

---

## ISO/IEC 42001 — AI Management Systems

### About ISO/IEC 42001

ISO/IEC 42001 (2023) specifies requirements for an Artificial Intelligence Management System (AIMS) — a framework for responsibly developing, providing, or using AI systems. It follows the standard ISO high-level structure used by ISO 9001 (quality management) and ISO 27001 (information security), making it familiar to organizations already certified to those standards.

VERA is most relevant to ISO 42001's **operational** (Clause 8) and **performance evaluation** (Clause 9) requirements, where claims about AI system quality, risk, and impact must be documented and assessed.

### Mapping Table

| ISO 42001 Clause | Requirement | VERA Mechanism |
|---|---|---|
| **4.1 — Context** | Understanding internal and external factors affecting AIMS | VERA sovereignty assessment (S1–S5): identifies epistemic dependencies on external tools and systems |
| **4.2 — Interested Parties** | Needs and expectations of interested parties | VERA Conclusion Sovereignty (S3) and Reasoning Sovereignty (S2): interested parties retain ability to access and challenge claims |
| **5.2 — AI Policy** | Top management establishes AI policy including objectives | VERA Governance domain (Level 3): documented VERA policy with named ownership; Level 4: leadership accountability for epistemic quality |
| **5.3 — Roles and Responsibilities** | Responsibilities for AIMS defined and communicated | VERA VERA owner role, claim ownership, verifier pool management |
| **6.1 — Risk Assessment** | AI risks identified, analyzed, and evaluated | VERA maturity assessment as structured risk identification; verification criteria (E1–E5, R1–R5) as risk evaluation criteria |
| **6.2 — Objectives** | AI management objectives established and measurable | Level 4 VERA metrics: first-pass verification rate, confidence distribution, sovereignty assessment scores |
| **7.2 — Competence** | Competence of persons affecting AI system performance | VERA training requirements (onboarding), calibration exercises (VERA-P-0013), verifier qualification |
| **7.5 — Documented Information** | Required documentation maintained | VERA claim registry, evidence sets, verification records, sovereignty assessment: comprehensive documented information |
| **8.2 — AI Risk Treatment** | AI risks treated per risk treatment plan | VERA impact triage (VERA-P-0012), sovereignty remediation plans with owner accountability |
| **8.3 — Operational Controls** | Controls for AI system operation documented | VERA Verification Protocol: explicit, versioned operational procedure for claims about AI systems |
| **9.1 — Monitoring and Measurement** | Performance monitored against objectives | Level 4: verification quality metrics reviewed on governance cadence; confidence calibration (VERA-P-0013) |
| **9.2 — Internal Audit** | Internal audits of AIMS | Level 5: governance function applies VERA methods to its own conclusions; verification records are audit-ready |
| **9.3 — Management Review** | Top management reviews AIMS performance | Level 4 governance reporting: VERA quality metrics in leadership reporting |
| **10.1 — Continual Improvement** | AIMS continually improved | VERA pattern development: recurring challenges documented as patterns; protocol improvements proposed through community governance |

### Where VERA Complements ISO 42001

ISO 42001 specifies *what* must be documented and governed but leaves significant discretion on *how*. VERA provides the how: the specific evidence quality standards, reasoning chain structure, verification criteria, and sovereignty requirements that give ISO 42001's requirements operational content in the epistemic quality domain.

An organization implementing ISO 42001 that adopts VERA for its claims about AI systems will have more rigorous documentation than ISO 42001 minimally requires, and that documentation will be structured to survive audit.

### Where ISO 42001 Addresses More Than VERA

- **AI system design and testing:** ISO 42001 addresses technical requirements for AI systems themselves (Annex A). VERA addresses claims about those systems, not system design.
- **Supply chain and third-party requirements:** ISO 42001 includes requirements for AI supply chain management. VERA addresses the evidence and reasoning documentation practices that support supply chain assessments.

---

## CMMI v2.0

### About CMMI v2.0

The Capability Maturity Model Integration (CMMI) v2.0 is a process improvement framework that describes five levels of capability maturity and a set of practice areas covering the full software and product development lifecycle. CMMI is widely used in defense, government, and commercial software development. Its five-level maturity progression is the direct inspiration for VERA's own five-level model.

### Level Correspondence

| CMMI Level | CMMI Name | Defining characteristic | VERA Level | VERA Name | Correspondence |
|---|---|---|---|---|---|
| 1 | Initial | Unpredictable, reactive, ad hoc | 1 | Aware | Understanding exists; no systematic practice |
| 2 | Managed | Basic project management applied | 2 | Exploring | VERA applied to selected claims; not yet institutionalized |
| 3 | Defined | Organization-wide standard processes | 3 | Practicing | VERA is organizational policy; all significant claims covered |
| 4 | Quantitatively Managed | Measurement and statistical control | 4 | Governing | VERA quality measured; improvement program active |
| 5 | Optimizing | Continuous improvement and innovation | 5 | Sovereign | Self-referential VERA application; community contribution |

The correspondence is strong enough that organizations already at CMMI Level 3 will find the governance concepts in VERA Level 3 familiar, and organizations targeting CMMI Level 4 will find VERA Level 4 metrics directly analogous to CMMI's quantitative management requirements.

### Practice Area Mapping

| CMMI Practice Area | CMMI Requirement (summary) | VERA Mechanism |
|---|---|---|
| **DAR — Decision Analysis and Resolution** | Alternatives analyzed against criteria before significant decisions | VERA Verification Protocol: explicit criteria (Phase 4) applied before claims are accepted as verified |
| **REQM — Requirements Management** | Requirements managed; changes tracked and communicated | VERA claim formulation (Phase 1): precise scoped statements; claim versioning; dependency notification (VERA-P-0012) |
| **PPQA — Process and Product Quality Assurance** | Processes and work products objectively evaluated | VERA verification independence requirement: evaluator distinct from creator; per-criterion findings documented |
| **CAR — Causal Analysis and Resolution** | Causes of defects analyzed; corrective actions taken | VERA contested claim process: challenges trigger structured re-evaluation; refuted claims traced to error source |
| **MA — Measurement and Analysis** | Measurement needs identified; measurement data analyzed | VERA Level 4 metrics: first-pass rate, rework rate, confidence distribution, contested claim rate; reviewed on governance cadence |
| **OPF — Organizational Process Focus** | Process strengths and weaknesses identified; improvement plans | VERA reasoning error taxonomy (Level 4): common failures tracked; training updated based on taxonomy |
| **OT — Organizational Training** | Training needs identified and met | VERA competency in onboarding; calibration exercises; VERA mentor assignment for new practitioners |
| **RDM — Requirements Development and Management** | Requirements elicited, developed, and verified | VERA claim decomposition (VERA-P-0006): compound assertions broken into independently verifiable components |

### Where VERA Differs from CMMI

CMMI addresses the full software and product development lifecycle across practice areas including technical solution, supplier management, and service delivery. VERA addresses only the epistemic quality of claims — a narrower but more precise scope. An organization implementing both applies VERA as the epistemic quality layer within CMMI's broader process framework.

CMMI's maturity levels apply to the organization's capability across all practice areas. VERA's maturity levels apply to epistemic practice specifically. An organization can be at CMMI Level 3 overall while being at VERA Level 1 in the Evidence domain — the two assessments measure different things.

---

## Toulmin Argumentation Model

### About the Toulmin Model

The Toulmin Model of Argumentation, developed by philosopher Stephen Toulmin in *The Uses of Argument* (1958), describes the structure of practical arguments using six elements: Claim, Data, Warrant, Backing, Qualifier, and Rebuttal. It is widely taught in rhetoric, philosophy, and writing instruction, and has influenced formal argumentation frameworks in AI and law.

VERA's reasoning constructs are compatible with the Toulmin Model. The primary relationship is that VERA operationalizes the Toulmin Model for organizational practice — making the elements explicit, versioned, and subject to systematic verification.

### Element Mapping

| Toulmin Element | Definition | VERA Equivalent | VERA Enhancement |
|---|---|---|---|
| **Claim** | The assertion being argued for | → Statement (within a VERA Claim) | VERA adds: identifier, provenance, scope definition, verification state |
| **Data** | The facts, evidence, or grounds cited in support | → Evidence Set | VERA adds: quality tier rating, independence assessment, chain of custody, absent evidence documentation, decay class |
| **Warrant** | The principle connecting data to claim — the reasoning bridge | → Reasoning Chain | VERA makes the warrant fully explicit: each step documented with premises, inference type, intermediate conclusion, and confidence |
| **Backing** | Support for the warrant — evidence that the warrant holds | → Evidence quality tier documentation and source credibility assessment | VERA formalizes backing into the four-tier quality system and chain-of-custody requirements |
| **Qualifier** | The modal strength of the claim (certainly, presumably, probably) | → Epistemic confidence (0.0–1.0) + → Verification State (○/◐/◑/●/◈/✗) | VERA replaces natural-language qualifiers with a calibrated numerical scale and a formal state machine |
| **Rebuttal** | Exceptions, counter-arguments, or conditions under which the claim does not hold | → Contrary evidence documentation + four response types (outweigh, distinguish, qualify, concede) | VERA requires documented assessment of every rebuttal and a formal response selection; rebuttal cannot be omitted |

### Key Differences

**Explicitness of the warrant.** In the Toulmin Model, warrants are often implicit — the connection between data and claim is unstated and assumed to be understood. VERA requires that the reasoning chain be written out step by step. This is the most significant practical difference: VERA's reasoning chain is the Toulmin warrant made fully explicit and independently evaluable.

**Verification as a separate phase.** The Toulmin Model describes argument structure; it does not specify a process for evaluating arguments. VERA adds Phase 4 (Verification Assessment) as a formal, criteria-driven evaluation by an independent party. This is absent from Toulmin.

**Versioning and state.** The Toulmin Model describes arguments as static structures. VERA adds verification state (which changes over time), confidence ratings (which can be revised), and version management (which allows claims to be updated when evidence changes). VERA claims are living epistemic objects; Toulmin arguments are static descriptions.

**Independence assessment.** VERA's evidence independence assessment (source collapse detection, VERA-P-0004) has no Toulmin equivalent. Toulmin's "data" encompasses multiple evidence items without assessing their independence.

**Sovereignty.** The Toulmin Model has no epistemic sovereignty concept. VERA's five sovereignty principles are VERA-specific commitments about who retains authority over the epistemic process — not present in any classical argumentation theory.

### When to Use the Toulmin Model Alongside VERA

The Toulmin Model is most useful as a **teaching tool** for practitioners who are learning to identify the elements of an argument before they are ready to document them in full VERA format. Walking through "what is the claim? what is the data? what is the warrant?" in Toulmin terms is a good preparation for writing a VERA reasoning chain.

In organizational contexts where VERA is not yet implemented, Toulmin-style analysis of key arguments (before they are formally documented as VERA claims) can reveal warrant and rebuttal gaps that otherwise remain invisible. This is a useful bridge practice at Level 1 (Aware) as practitioners develop the habit of explicit reasoning before they implement the full protocol.

---

## Cross-Framework Summary

The following table shows at a glance which aspects of VERA address which frameworks' requirements.

| VERA Mechanism | NIST AI RMF | EU AI Act | ISO 42001 | CMMI | Toulmin |
|---|---|---|---|---|---|
| Evidence quality tiers | MAP 2.1 | Art. 10 | 7.5 | RDM | Data |
| Reasoning chain documentation | MEASURE 2.2 | Art. 13 | 8.3 | DAR | Warrant |
| Verification Protocol (Phase 4) | MEASURE 1.1 | Art. 15 | 9.1 | PPQA | — |
| Claim registry + records | MEASURE 4.1 | Art. 12 | 7.5 | REQM | — |
| Challenge process | MANAGE 1.3 | Art. 14 | 10.1 | CAR | Rebuttal |
| Sovereignty principles (S1–S5) | GOVERN 4.1 | Art. 14 | 4.2 | — | — |
| Maturity model | GOVERN 1.1 | — | 9.3 | All levels | — |
| Quality metrics (Level 4) | MANAGE 4.2 | Art. 9 | 9.1 | MA | — |
| AI evidence documentation (P-0003) | MEASURE 2.5 | Art. 50 | 8.2 | — | — |
| Pattern library | MANAGE 2.4 | — | 10.1 | OPF | — |
| Training and calibration | GOVERN 1.4 | — | 7.2 | OT | — |
