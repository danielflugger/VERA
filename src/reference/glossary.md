# Appendix A: Glossary

This glossary provides quick-reference definitions for all terms used across the VERA documentation. Definitions here are concise; the canonical definition for foundational terms lives in the [Lexicon](../foundations/lexicon.md), which should be consulted when precision matters. Cross-references use → to indicate related terms.

Terms are listed alphabetically. For the formal error taxonomy, see [Lexicon § Error Taxonomy](../foundations/lexicon.md#error-taxonomy).

---

## A

**Abductive inference**
An inference type in which the conclusion is presented as the best available explanation of the evidence, rather than as a logical necessity or statistical generalization. One of VERA's four labeled inference types. Moderate strength; requires ruling out alternative explanations. *See also:* → Inference type.

**Absent evidence**
An evidence type that was expected given a claim's scope and prospective search plan but was not found during the evidence search. Distinct from evidence that was not searched for. Must be documented and assessed for materiality using → VERA-P-0001 (Absence-of-Evidence Assessment). Three materiality ratings: Non-material, Moderate, Significant.

**Adversarial checklist**
In → VERA-P-0010, a seven-item checklist applied during self-verification, calibrated to surface the errors most likely to be missed by a claimant reviewing their own work. Includes prompts such as "What is the weakest link in this chain?" and "Which assumption would you least want an adversary to notice?"

**AI-Generated Evidence Documentation**
→ VERA-P-0003. A three-tier handling protocol for evidence retrieved, summarized, or synthesized by AI systems, with distinct chain-of-custody and quality-rating requirements for each tier: Tier A (source retrieved and verified), Tier B (source identified but not retrievable), and Tier C (AI-synthesized analysis without specific source).

**Analogical inference**
An inference type in which a conclusion is drawn by reasoning from similarity to a reference case: "this is like that; what was true there is likely true here." The weakest of VERA's four inference types because its validity depends entirely on the strength of the similarity claim. Requires structured similarity scoring per → VERA-P-0009.

**Analogical Reasoning Validation**
→ VERA-P-0009. A structured similarity-disanalogy analysis that produces a Similarity Score (0.0–1.0) and determines the permissible scope of an analogical conclusion. *See also:* → Similarity Score.

**Anchor example**
In → VERA-P-0013, a historical claim with a known outcome and a documented confidence rating and rationale, used in calibration exercises to align verifiers' confidence scales. Anchor libraries should contain at least three examples per confidence band.

**Assertion**
A statement made by an agent without formal evidence attachment, reasoning chain, or verification status. Assertions are the raw material of → Claims; they are not inherently invalid, but they are epistemically unprocessed. VERA tracks assertions separately from claims and flags their use as evidence in reasoning chains. *Canonical definition:* [Lexicon § Assertion](../foundations/lexicon.md#assertion).

---

## B

**Backing**
In the → Toulmin Argumentation Model, the support for the warrant — evidence for why the warrant holds. Maps to VERA's → Evidence Quality tier ratings and → Chain of custody documentation. *See:* [Appendix B § Toulmin](./standards.md#toulmin-argumentation-model).

---

## C

**Cascading Claim Update**
→ VERA-P-0012. A three-phase protocol for managing downstream effects when an upstream claim changes verification state: (1) dependency registration at claim creation, (2) impact triage using a standardized matrix, (3) selective re-verification based on triage results.

**Chain laundering**
An error in which a weakly supported or unverified claim is used as if it were well-supported evidence in a subsequent reasoning chain, obscuring the weak evidentiary basis by embedding it in an apparently solid chain. *Canonical definition:* [Lexicon § Chain Laundering](../foundations/lexicon.md#chain-laundering).

**Chain of custody**
The documented provenance of an evidence item from its original source to its use in a claim record. Required fields: how access was obtained, what transformation (if any) was applied, and by whom and when. *See:* → Data Sovereignty (S1).

**Claim**
A structured epistemic object — the primary unit of VERA — consisting of: a precise statement, a → Claim identifier, a provenance record, an → Evidence set, a → Reasoning chain, a → Verification state, and an → Epistemic confidence rating. A claim without an evidence set, reasoning chain, or verification state is an → Assertion. *Canonical definition:* [Lexicon § Claim](../foundations/lexicon.md#claim).

**Claim Confidence Calibration**
→ VERA-P-0013. A calibration program ensuring that confidence ratings assigned by different verifiers are consistent and predictive. Components: anchor example library, consistency tracking metrics, and a → Confidence Committee process for high-stakes claims. Available at Level 4.

**Claim identifier**
A unique, permanent reference assigned to every VERA claim before evidence assembly begins. Format: `VERA-C-[YYYY]-[NNNN]`. Individual practitioners without an organizational registry use initials as a prefix: `VERA-C-DJF-2026-0001`. Identifiers never change; revised claims carry the same ID with a version suffix (e.g., `v2`).

**Claim record**
The complete document containing all elements of a VERA claim: statement, identifier, context metadata, → Evidence set, → Reasoning chain, and links to → Verification records.

**Claim registry**
A centralized, searchable catalog of all documented VERA claims, maintained by an individual, team, or organization. Minimum required fields at Level 3: Claim ID, statement, verification state, confidence, owner, created date, verified date, review due date, and verification record link. *See:* [Tooling & Integration](../implementation/tooling.md).

**Compliance surface**
A failure mode in which VERA documentation has the correct formal structure — all required fields are present — but lacks epistemic substance. Evidence items are listed without genuine quality assessment; reasoning chains restate the evidence rather than argue from it; verification records record a state without documenting per-criterion findings. *See:* [Level 3 § Anti-Patterns](../maturity-model/level-3.md#the-compliance-surface).

**Compound Claim Decomposition**
→ VERA-P-0006. A three-test decomposition method (Independence Test, Evidence Test, Verification Test) applied recursively until each component is atomic and independently verifiable. Includes dependency mapping for cases where sub-claims are logically prerequisite to each other.

**Conclusion Sovereignty**
S3; one of VERA's five → Sovereignty Principles. The right of the person or organization whose decisions are affected by a claim to reach their own conclusion — including one that differs from a verified claim. Prohibits institutional structures that make disagreement impossible, though it does not eliminate consequences for minority positions in legitimate governance processes. *See:* [Sovereignty Principles § S3](../foundations/sovereignty-principles.md#principle-s3-conclusion-sovereignty).

**Confidence band**
A range on the 0.0–1.0 → Epistemic confidence scale associated with a qualitative assessment. Four bands: High (0.85–1.0), Moderate (0.65–0.84), Low (0.40–0.64), Speculative (0.00–0.39). Used in → Anchor examples for calibration exercises.

**Confidence ceiling**
An upper bound on the → Epistemic confidence rating achievable under specific verification conditions. The self-verification ceiling (→ VERA-P-0010) is 0.72. The ceiling for analogical inference (→ VERA-P-0009) varies by → Similarity Score.

**Confidence Committee**
In → VERA-P-0013, a group of three verifiers who independently assign confidence ratings to high-stakes claims and converge through structured discussion. Used when a single verifier's calibration is insufficient for the stakes of the claim.

**Contrary Evidence Integration**
→ VERA-P-0008. A structured framework for evaluating contrary evidence on three dimensions (quality tier, relevance scope, independence) and selecting an appropriate response from four options: outweigh, distinguish, qualify, or concede.

**Contrary evidence**
Evidence items assembled during Phase 2 that complicate or contradict the claim. Must be addressed in the → Reasoning chain using one of four documented responses. Contrary evidence that is not addressed violates verification criterion E4.

**Correlated (independence classification)**
One of three → Evidence independence classifications. Items that share a common upstream source but add independent interpretation or transformation. Intermediate between Independent and Dependent. Must be noted in the evidence set and reflected in the confidence rating.

---

## D

**Data Sovereignty**
S1; the first of VERA's five → Sovereignty Principles. The requirement that every evidence item underlying a claim is accessible, auditable, and exportable independently of vendor systems, licenses, or third-party controls. *See:* [Sovereignty Principles § S1](../foundations/sovereignty-principles.md#principle-s1-data-sovereignty).

**Decay class**
A classification applied to each → Evidence item indicating how rapidly its reliability decreases over time. Three classes: Stable (36-month default review window), Drifting (12-month), Volatile (3-month). Applied using → VERA-P-0005.

**Deductive inference**
An inference type in which the conclusion follows necessarily from the premises — if the premises are true, the conclusion cannot be false. The strongest of VERA's four inference types, but requires premises to be certain rather than probable. *See also:* → Inference type.

**Dependent (independence classification)**
One of three → Evidence independence classifications. Items that are proxies for the same underlying source, providing no additional independent support. Dependent items must be consolidated using → VERA-P-0004.

**Dependency registration**
The act of recording, at claim creation time (Phase 1, Step 1.4), which upstream verified claims are used as evidence in the new claim's evidence set. Creates the bidirectional links required for → VERA-P-0012 (Cascading Claim Update).

**Domain**
One of six capability areas measured by the → VERA Maturity Model: Evidence, Reasoning, Verification, Governance, Sovereignty, and Integration. An organization's maturity level may differ across domains; a single composite score obscures meaningful variation. *Canonical definition:* [Lexicon § Domain](../foundations/lexicon.md#domain).

---

## E

**Epistemic confidence**
A numerical rating from 0.0 to 1.0 representing a verifier's assessment of how strongly available evidence supports a claim. Not a probability; an explicit declaration of epistemic position. Travels with the claim and is used to weight claims when they appear as evidence in downstream reasoning chains. *Canonical definition:* [Lexicon § Epistemic Confidence](../foundations/lexicon.md#epistemic-confidence).

**Epistemic sovereignty**
The condition of having genuine authority over the knowledge one acts on: the ability to access evidence, inspect reasoning, challenge conclusions, and reach independent judgments. VERA operationalizes epistemic sovereignty through the five → Sovereignty Principles. *See:* [Sovereignty Principles](../foundations/sovereignty-principles.md).

**Evidence decay**
The reduction in the reliability or currency of an → Evidence item over time, particularly in domains where conditions change frequently. Managed through → Decay classes and expiry dates per → VERA-P-0005.

**Evidence domain**
One of the six → Domain areas in the VERA Maturity Model. Measures how well an organization identifies, retrieves, rates, documents, and maintains evidence items across the claim lifecycle.

**Evidence independence**
The degree to which items in an evidence set derive from genuinely separate sources. Three classifications: Independent, Correlated, Dependent. Source collapse — treating Dependent items as Independent — inflates apparent confidence. *Canonical definition:* [Lexicon § Evidence Independence](../foundations/lexicon.md#evidence-independence).

**Evidence Item**
A discrete piece of source material cited in support of a claim. Each item requires: source reference, evidence type (quality tier), relevance statement, chain of custody, and access date. *Canonical definition:* [Lexicon § Evidence Item](../foundations/lexicon.md#evidence-item).

**Evidence Item Record**
The structured document containing all required fields for a single evidence item. Stored in the claim's evidence folder and aggregated into the → Evidence set documentation.

**Evidence quality**
A four-tier rating system applied to each evidence item: Primary (Tier 1 — original source), Secondary (Tier 2 — peer-reviewed interpretation), Tertiary (Tier 3 — textbook or encyclopedic synthesis), Testimonial (Tier 4 — expert assertion without direct evidence access). Rates structural proximity to original source, not accuracy. *Canonical definition:* [Lexicon § Evidence Quality](../foundations/lexicon.md#evidence-quality).

**Evidence set**
The complete collection of → Evidence items cited in a claim, including supporting evidence, contrary evidence, and documentation of absent expected evidence types. *Canonical definition:* [Lexicon § Evidence Set](../foundations/lexicon.md#evidence-set).

**Expert independence**
The highest of VERA's three verifier → Independence levels. The verifier has recognized expertise in the claim's domain and is institutionally independent from the claimant.

**Expert Verifier Onboarding**
→ VERA-P-0011. A structured briefing and joint record protocol for engaging a domain expert as a VERA verifier when the expert has not been trained in VERA. Components: Criteria Translation Worksheet, pre-review briefing, structured interview, and joint Verification Record production.

---

## F

**First-pass verification rate**
The percentage of claims submitted for verification that are verified on the first submission without being returned for revision. Tracked as a quality metric at Level 4. A rate above ~90% suggests criteria are too permissive; below ~60% suggests claims are submitted before preparation is complete.

**Foundational independence**
The lowest of VERA's three verifier → Independence levels. The verifier is a different person from the claimant but has no specific domain competency or institutional independence requirement. Caps achievable → Epistemic confidence at 0.72.

---

## G

**Governance domain**
One of the six → Domain areas in the VERA Maturity Model. Measures whether and how VERA practice is mandated, resourced, audited, and improved at an organizational level. Typically lags other domains during early adoption because governance infrastructure requires demonstrated value before investment.

**Ground truth**
The most reliable available evidence for a given claim — the closest available approximation to direct observation of the phenomenon the claim describes. Not an absolute standard; ground truth in VERA is always domain-relative and rated by → Evidence quality tier.

---

## H

**Hidden Assumption Excavation**
→ VERA-P-0007. A systematic protocol for surfacing assumptions embedded in reasoning steps that the claimant does not realize they are making. Applies three interrogation questions to each step: Necessary Conditions ("What would need to be true for this to follow?"), Variance ("What am I treating as fixed that could vary?"), and Values and Framing ("Where is this reasoning sensitive to normative choices?").

---

## I

**Impact triage**
In → VERA-P-0012, the structured assessment of how much each downstream claim is affected by an upstream claim's state change. Produces three downstream action categories: High (immediate re-verification), Moderate (expedited review within 30 days), Low (annotation at next scheduled review).

**Independent (independence classification)**
One of three → Evidence independence classifications. Items that demonstrably trace to separate primary sources. Full independent support is the strongest evidence basis for a claim.

**Inductive inference**
An inference type in which the conclusion generalizes from observed instances to a broader pattern. Strong when instances are numerous, representative, and well-documented. One of VERA's four labeled inference types. *See also:* → Inference type.

**Inference type**
One of four labeled categories for the logical connection between premises and conclusion in a → Reasoning chain step: Deductive (conclusion necessarily follows), Inductive (conclusion generalizes from instances), Abductive (conclusion is the best explanation), Analogical (conclusion inferred from similarity to another case). Each step in a reasoning chain must label its inference type.

**Integration domain**
One of the six → Domain areas in the VERA Maturity Model. Measures how fully VERA practices are embedded in existing workflows, tools, and processes rather than existing as a parallel overhead system.

---

## L

**Lexicon**
The VERA chapter providing canonical definitions for all core framework terms. When a term appears in VERA documentation, it carries the meaning given in the Lexicon — not a colloquial meaning or a meaning from outside the framework. *See:* [Foundations § Lexicon](../foundations/lexicon.md).

---

## M

**Maturity Level**
One of five stages in the → VERA Maturity Model: 1 — Aware, 2 — Exploring, 3 — Practicing, 4 — Governing, 5 — Sovereign. Levels are assessed per → Domain; a single composite level obscures meaningful variation. *Canonical definition:* [Lexicon § Maturity Level](../foundations/lexicon.md#maturity-level).

**Maturity Model**
VERA's five-level, six-domain framework for assessing and developing VERA capability. Levels describe increasing systematization from initial awareness to full epistemic sovereignty. Domains cover the full VERA practice lifecycle. *See:* [Maturity Model Overview](../maturity-model/overview.md).

**Minimum Viable VERA**
The six-element floor of VERA documentation that constitutes genuine VERA practice rather than → Compliance surface: (1) a precise claim statement, (2) an assigned claim identifier, (3) a prospective search plan written before evidence collection, (4) a rated evidence set with absent evidence noted, (5) an explicit reasoning chain with at least one documented assumption, and (6) a verification record with per-criterion findings and a confidence rating. *See:* [Getting Started § Minimum Viable VERA](../implementation/getting-started.md#minimum-viable-vera).

---

## P

**Pattern**
A reusable, documented solution to a recurring challenge in evidence management, reasoning construction, or verification practice. Follows the → Pattern Template and is itself a verified VERA claim. *Canonical definition:* [Lexicon § Pattern](../foundations/lexicon.md#pattern).

**Pattern ID**
A unique, permanent identifier for a VERA pattern in the format `VERA-P-[NNNN]`. Assigned by the pattern registry upon submission. IDs never change; deprecated patterns retain their IDs marked Deprecated.

**Pattern Template**
The canonical format for all VERA patterns, specifying fourteen required fields: Pattern ID, Classification, Context, Problem, Forces, Solution, Implementation, Evidence Requirements, Verification Criteria, Consequences, Known Uses, Related Patterns, and Verification Status. *See:* [Foundations § Pattern Template](../foundations/pattern-template.md).

**Peer independence**
The middle of VERA's three verifier → Independence levels. The verifier has relevant domain competency and no stake in the claim's outcome. Provides stronger epistemic grounding than → Foundational independence.

**Primary evidence**
→ Evidence quality Tier 1. Original source material: direct observation, raw datasets, original documents, firsthand testimony from the event described. The closest available evidence to ground truth.

**Process Sovereignty**
S4; one of VERA's five → Sovereignty Principles. The requirement that the verification process is auditable and is structurally capable of producing negative results. A verification process controlled entirely by those who want a claim verified, or one that never produces a failed verification, violates this principle. *See:* [Sovereignty Principles § S4](../foundations/sovereignty-principles.md#principle-s4-process-sovereignty).

**Prospective search plan**
A documented list of evidence types expected to exist for a claim, written before evidence collection begins (Phase 2, Step 2.1). The prospective plan — not just the evidence found — is what allows → Absent evidence to be detected and documented. A search conducted without a prior plan cannot reliably identify what is missing.

**Protocol version**
The version of the Verification Protocol used when verifying a claim. Recorded in the → Verification Record. Claims record the protocol version so that as the protocol evolves, the standards under which existing claims were verified remain auditable.

---

## Q

**Qualifier**
In the → Toulmin Argumentation Model, the modal strength of the claim (certainly, probably, presumably, etc.). Maps to VERA's → Epistemic confidence rating and → Verification state, which together express how strongly the claim is held and at what stage of evaluation.

---

## R

**Reasoning Chain**
The explicit, step-by-step argument connecting an → Evidence set to a claim's statement. Each step states its premises (evidence items or prior step conclusions), its → Inference type, intermediate conclusion, and confidence. *Canonical definition:* [Lexicon § Reasoning Chain](../foundations/lexicon.md#reasoning-chain).

**Reasoning domain**
One of the six → Domain areas in the VERA Maturity Model. Measures how explicitly and rigorously reasoning chains are constructed, documented, and evaluated. The most cognitively demanding domain to develop; strong intuition about "good reasoning" rarely translates immediately to explicit reasoning chain documentation.

**Reasoning Gap**
An undocumented logical step in a → Reasoning chain — a premise that appears without sourcing. The most common location of consequential reasoning errors. VERA requires all gaps to be either filled with a documented step or flagged as an acknowledged assumption. *Canonical definition:* [Lexicon § Reasoning Gap](../foundations/lexicon.md#reasoning-gap).

**Reasoning Sovereignty**
S2; one of VERA's five → Sovereignty Principles. The requirement that every step in a reasoning chain that informs someone's decisions is made visible and challengeable to that person. Violated when AI-generated conclusions are used without exposing the AI's reasoning, or when complex reasoning is summarized rather than documented step by step. *See:* [Sovereignty Principles § S2](../foundations/sovereignty-principles.md#principle-s2-reasoning-sovereignty).

**Rebuttal**
In the → Toulmin Argumentation Model, exceptions or counter-arguments to the claim. Maps to VERA's → Contrary evidence documentation and the four response types (outweigh, distinguish, qualify, concede) in the → Reasoning chain.

**Registry Graveyard**
An anti-pattern at Level 3 in which a → Claim registry is maintained but not actively reviewed, accumulating stale, superseded, or out-of-scope claims that give a false impression of epistemic coverage. *See:* [Level 3 § Anti-Patterns](../maturity-model/level-3.md#the-registry-graveyard).

**Review cadence**
A documented schedule for re-evaluating claims and their evidence, established in Phase 5 of the Verification Protocol (Step 5.4). Recommended intervals: 6 months (high-sensitivity domains such as medical, financial, regulatory), 12–18 months (organizational policy, technical standards), 36 months (historical, conceptual). Linked to → Decay class expiry dates.

---

## S

**Secondary evidence**
→ Evidence quality Tier 2. Derived from primary sources through peer-reviewed expert interpretation, synthesis, or analysis. Reliable for most VERA claims; preferred when Primary evidence is not directly accessible.

**Selective citation**
The practice of including only evidence that supports a claim while omitting evidence that complicates or contradicts it. A violation of → Evidence Primacy (VERA's first principle). Includes cherry-picking, citing a document's conclusions while omitting its caveats, and omitting → Absent evidence documentation. *Canonical definition:* [Lexicon § Selective Citation](../foundations/lexicon.md#selective-citation).

**Self-Verification with Adversarial Stance**
→ VERA-P-0010. A structured self-verification protocol using role declaration, a mandatory 24-hour time gap, the → Adversarial checklist, and a → Confidence ceiling of 0.72.

**Significance threshold**
The organizational definition of which claims require VERA treatment. Must be specific enough that any practitioner can apply it to any given claim without deliberation. Example: "Claims that will appear in external communications, inform decisions with irreversible consequences, or support capital allocations above $X." *See:* [Adoption Roadmap § Phase 3](../implementation/adoption-roadmap.md#phase-3-reaching-level-3).

**Similarity Score**
In → VERA-P-0009, the aggregate score from per-dimension similarity ratings, calculated as the sum of individual scores divided by (3 × number of dimensions). Score ranges map to permissible conclusion scope: 0.85–1.0 (strong analogical inference), 0.65–0.84 (moderate, with acknowledged differences), 0.40–0.64 (weak, conclusion scoped to areas of similarity), below 0.40 (analogy insufficient).

**Source Collapse Detection and Remediation**
→ VERA-P-0004. An evidence source tree audit that reveals shared roots among evidence items and consolidates Dependent items into an accurate count of independent sources.

**Source collapse**
The reasoning error of treating multiple → Evidence items as independent when they derive from the same underlying source. Inflates apparent evidential support. *Canonical definition:* [Lexicon § Source Collapse](../foundations/lexicon.md#source-collapse).

**Sovereignty**
In VERA, the state in which an individual or organization retains ultimate authority over their evidence, reasoning, conclusions, and verification processes. Operationalized through the five → Sovereignty Principles (S1–S5). *Canonical definition:* [Lexicon § Sovereignty](../foundations/lexicon.md#sovereignty).

**Sovereignty domain**
One of the six → Domain areas in the VERA Maturity Model. Measures how fully the five → Sovereignty Principles are implemented in practice.

**Sovereignty Principles**
VERA's five binding design constraints that prevent epistemic sovereignty erosion: S1 Data Sovereignty, S2 Reasoning Sovereignty, S3 Conclusion Sovereignty, S4 Process Sovereignty, S5 Temporal Sovereignty. Any VERA implementation that violates them is not VERA-compliant regardless of how faithfully it follows the rest of the framework. *See:* [Foundations § Sovereignty Principles](../foundations/sovereignty-principles.md).

**Stale claim**
A claim whose evidence items have passed their → Review cadence date or → Decay class expiry date without a reconfirmation check. Must be flagged and not used in new reasoning chains without re-verification.

**Statement**
The precise declarative sentence that constitutes a → Claim's core assertion. Must be testable (two people could agree on what evidence would support or contradict it), scoped (conditions under which it holds are specified), and free of vague language (hedges are quantified or eliminated).

---

## T

**Temporal Sovereignty**
S5; one of VERA's five → Sovereignty Principles. Authority over when claims are verified, reviewed, and retired, without non-epistemic pressure to accelerate or delay these processes. *See:* [Sovereignty Principles § S5](../foundations/sovereignty-principles.md#principle-s5-temporal-sovereignty).

**Tertiary evidence**
→ Evidence quality Tier 3. Derived from secondary sources through textbook, encyclopedic, or journalistic synthesis. Acceptable for background context; insufficient as primary support for significant claims.

**Testimonial evidence**
→ Evidence quality Tier 4. An expert's assertion or firsthand account where the underlying evidence is not directly accessible. Valid in VERA but carries the lowest quality rating; requires explicit documentation of the expert's identity and basis for their testimony.

**Time-Sensitive Evidence Management**
→ VERA-P-0005. An evidence-level expiry annotation system with three → Decay class categories and monitoring protocols linked to claim review triggers.

**Toulmin Argumentation Model**
A classical model of argument structure (claim, data, warrant, backing, qualifier, rebuttal) developed by philosopher Stephen Toulmin. VERA's reasoning constructs are compatible with the Toulmin model; the Lexicon and Reasoning Chain are more operationally specific and add elements Toulmin does not include (inference type labeling, independence assessment, verification state). *See:* [Appendix B § Toulmin](./standards.md#toulmin-argumentation-model).

---

## U

**Upstream dependency**
A verified → Claim used as an → Evidence item in another claim's evidence set. Must be registered at claim creation time. State changes in upstream claims trigger → VERA-P-0012.

**Urgent verification**
A modified verification path permitted when time constraints prevent the standard five-phase protocol. Applies a minimum viable criteria set (E1, R1, R2, F1) and publishes the claim as Partial-Urgent state. Full verification must complete within 72 hours. *See:* [Verification Protocol § Special Situations](../foundations/verification-protocol.md#urgent-verification).

---

## V

**VERA**
Verified Evidence and Reasoning Architecture. A structured framework for ensuring that claims are traceable to evidence, conclusions are the product of explicit reasoning, and individuals and organizations retain sovereignty over the knowledge they generate and depend upon. Not a software system, certification program, or AI product; an architecture for organizing epistemic practice.

**VERA-C-[YYYY]-[NNNN]**
The canonical format for → Claim identifiers. YYYY is the four-digit year of claim initiation; NNNN is a sequential number within that year.

**VERA-P-[NNNN]**
The canonical format for → Pattern IDs. Assigned by the pattern registry upon submission. Permanent and never reused.

**VERA-V-[NNNN]**
The canonical format for → Verification Record identifiers.

**Verification**
The process of evaluating whether a claim's → Evidence set and → Reasoning chain adequately support its statement. Conducted by a designated → Verifier against explicit criteria (the Verification Protocol Phase 4 criteria), producing a → Verification Record. Not proof; epistemic accountability. *Canonical definition:* [Lexicon § Verification](../foundations/lexicon.md#verification).

**Verification Capture**
The failure mode in which the verification process is structurally unable to produce a negative result. A captured process endorses rather than evaluates. *Canonical definition:* [Lexicon § Verification Capture](../foundations/lexicon.md#verification-capture).

**Verification domain**
One of the six → Domain areas in the VERA Maturity Model. Measures how consistently and rigorously claims are submitted, evaluated, and resolved through the Verification Protocol.

**Verification Protocol**
VERA's five-phase procedural framework for producing verified claims: Phase 1 (Claim Formulation), Phase 2 (Evidence Assembly), Phase 3 (Reasoning Construction), Phase 4 (Verification Assessment), Phase 5 (Documentation and Publication). A versioned document; the current version is 1.0. *See:* [Foundations § Verification Protocol](../foundations/verification-protocol.md).

**Verification Record**
The immutable documentation produced by a verification event. Required contents: claim identifier, verifier identity and qualifications, verification date, protocol version, per-criterion findings, resulting verification state, confidence rating with justification, and notes. *Canonical definition:* [Lexicon § Verification Record](../foundations/lexicon.md#verification-record).

**Verification State**
The current status of a claim in the VERA verification lifecycle. Six states: Unverified (○), Pending (◐), Partial (◑), Verified (●), Contested (◈), Refuted (✗). State transitions require explicit triggers and documentation. *Canonical definition:* [Lexicon § Verification State](../foundations/lexicon.md#verification-state).

**Verifier**
The individual or team responsible for Phase 4 of the Verification Protocol. Ideally independent from the claimant. Three independence levels recognized: → Foundational, → Peer, → Expert.

**Verifier pool**
The set of practitioners qualified to conduct VERA verifications within a team or organization. Actively managed at Level 4: tracked for calibration consistency, assessed for independence, and developed through training and calibration exercises.

---

## W

**Warrant**
In the → Toulmin Argumentation Model, the reasoning connecting data to the claim — the bridge between evidence and conclusion. Maps directly to VERA's → Reasoning chain, which makes the warrant explicit and step-by-step rather than leaving it implicit.
