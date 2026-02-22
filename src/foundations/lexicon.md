# Lexicon: Canonical Definitions

This lexicon defines terms as they are used in VERA. When a term appears in VERA documentation, it carries the meaning given here — not a colloquial meaning, not a discipline-specific meaning from outside VERA, and not a meaning imported from another framework without explicit annotation.

Definitions are listed in dependency order: terms that appear in a definition are defined earlier in the list.

---

## Core Objects

### Assertion

An **assertion** is a statement made by an agent without formal evidence attachment, reasoning chain, or verification status. Assertions are the raw material of claims. They are not inherently invalid — they are epistemically unprocessed.

VERA does not prohibit assertions. It distinguishes them clearly from claims and tracks them separately in documentation. Assertions used as evidence in a reasoning chain must be flagged as such, and their use degrades the quality rating of that evidence chain accordingly.

*Compare: [Claim](#claim).*

---

### Claim

A **claim** is a structured epistemic object consisting of:

1. A **statement** — the proposition asserted
2. A **claim identifier** — a unique, stable reference (format: `VERA-C-[YYYY]-[NNNN]`)
3. A **provenance record** — who made the claim, when, and in what context
4. An **evidence set** — one or more [Evidence Items](#evidence-item) cited in support
5. A **reasoning chain** — the explicit logical steps connecting the evidence set to the statement
6. A **verification state** — the current status of the claim in the verification process
7. A **confidence rating** — a quantified assessment of epistemic confidence given the evidence and verification state

A claim that lacks items 4, 5, or 6 is an [Assertion](#assertion), not a claim, regardless of how its originator characterizes it.

*Claims are the primary unit of VERA. All VERA protocols operate on claims.*

---

### Evidence Item

An **evidence item** is a discrete piece of source material cited in support of a claim. Each evidence item has:

- **Source reference**: A citation sufficient to locate the original material (URL with access date, document ID, physical location, etc.)
- **Evidence type**: One of Primary, Secondary, Tertiary, or Testimonial (see [Evidence Quality](#evidence-quality))
- **Relevance statement**: An explicit description of what aspect of the claim this evidence supports
- **Chain of custody**: How the evidence passed from its original source to the claimant
- **Access date**: When the claimant accessed the evidence (important for time-sensitive material)

Evidence items are not arguments. They do not, by themselves, support a claim. They are the raw material that a [Reasoning Chain](#reasoning-chain) processes into a conclusion.

---

### Evidence Quality

**Evidence quality** is a four-tier rating applied to each evidence item, assessing its reliability as a basis for claims.

| Tier | Label | Definition |
|------|-------|------------|
| 1 | **Primary** | Original source: direct observation, raw data, original document, firsthand testimony from the event described |
| 2 | **Secondary** | Derived from primary sources: synthesis, analysis, peer-reviewed interpretation of primary data |
| 3 | **Tertiary** | Derived from secondary sources: textbooks, encyclopedias, review articles, journalism interpreting secondary sources |
| 4 | **Testimonial** | Assertion by a domain expert or credible witness, where the underlying evidence is not directly accessible |

Evidence quality is not a judgment of the evidence's relevance or accuracy — it is a structural rating of how close the evidence is to its original source. A Tier 1 evidence item can be wrong. A Tier 4 evidence item can be accurate.

When multiple evidence items of different quality tiers support the same claim element, the reasoning chain must note the variation and justify reliance on lower-tier evidence when higher-tier evidence is unavailable.

---

### Evidence Set

An **evidence set** is the complete collection of [Evidence Items](#evidence-item) cited in a claim. A well-formed evidence set:

- Includes all evidence consulted, not only evidence that supports the conclusion (see [Selective Citation](#selective-citation))
- Identifies conflicting evidence explicitly and explains how it was weighed
- Notes the absence of expected evidence types when that absence is material
- Rates each item by [Evidence Quality](#evidence-quality)

The quality of an evidence set is calculated from the quality distribution of its items and the degree of independence among them (see [Evidence Independence](#evidence-independence)).

---

### Evidence Independence

**Evidence independence** measures the degree to which items in an evidence set derive from genuinely separate sources rather than from a single underlying source that appears multiple times.

Three news articles all citing the same press release are not three independent pieces of evidence — they are one. A reasoning chain that treats them as three independent items is exhibiting a form of reasoning error VERA calls **source collapse**.

Independence is assessed on a three-point scale:

- **Independent**: Items trace to demonstrably separate primary sources
- **Correlated**: Items share a common upstream source but add independent interpretation or transformation
- **Dependent**: Items are proxies for the same underlying source

A claim whose evidence set contains only dependent items is treated as resting on a single evidence item, regardless of how many items are cited.

---

### Reasoning Chain

A **reasoning chain** is the explicit, step-by-step argument connecting an evidence set to a claim's statement. Each step in the reasoning chain consists of:

1. **Premises**: Evidence items or prior conclusions accepted as inputs
2. **Inference rule**: The logical principle applied (deductive, inductive, abductive, or analogical)
3. **Intermediate conclusion**: The output of this step, which may serve as a premise for the next

A reasoning chain is complete when its final conclusion is identical to the claim's statement, and every premise is either a referenced evidence item or a prior step's intermediate conclusion.

**Reasoning chain quality** is evaluated on four dimensions:

| Dimension | Definition |
|-----------|------------|
| **Validity** | The logical structure is sound — the conclusion follows from the premises |
| **Relevance** | The evidence items address the claim and not merely adjacent topics |
| **Completeness** | No material premise is hidden or assumed without acknowledgment |
| **Independence** | The evidence items are not all proxies for the same underlying source |

A reasoning chain that fails on any dimension is noted in the verification record, and the claim's verification state is downgraded accordingly.

---

### Verification

**Verification** is the process of evaluating whether a claim's evidence set and reasoning chain adequately support its statement. Verification:

- Is conducted against explicit, pre-stated criteria (the Verification Protocol)
- Is performed by a designated verifier, who may or may not be the claimant
- Produces a verification record documenting what was assessed and how
- Results in an updated [Verification State](#verification-state)
- Is time-stamped and attributed — "verified" is not a permanent status

Verification is not proof. A verified claim is one that has been evaluated by the VERA process and found to meet the specified criteria. It may still be wrong. Verification establishes epistemic accountability, not truth.

---

### Verification State

**Verification state** is the current status of a claim in the VERA verification lifecycle. There are six defined states:

| State | Symbol | Meaning |
|-------|--------|---------|
| **Unverified** | ○ | Claim has not entered the verification process |
| **Pending** | ◐ | Verification has been initiated; evidence review is in progress |
| **Partial** | ◑ | Verification of some claim components is complete; others remain pending |
| **Verified** | ● | All claim components have been verified against stated criteria |
| **Contested** | ◈ | Verification has been challenged; the claim is under active dispute |
| **Refuted** | ✗ | Verification has concluded that the evidence does not support the claim |

State transitions require explicit triggers and documentation. A Verified claim does not become Contested automatically when new evidence appears — the challenge must be formally lodged through the VERA dispute process, which initiates re-evaluation.

Claims in Contested state may continue to be used in reasoning, but must be marked as Contested in any downstream reasoning chain. Refuted claims must not be used as supporting evidence.

---

### Verification Record

A **verification record** is the documentation produced by a verification event. It contains:

- **Claim identifier** being verified
- **Verifier identity** (individual or team) and their relevant qualifications
- **Verification date** and the version of the claim verified
- **Criteria applied** (reference to Verification Protocol version)
- **Findings** for each criterion: met, not met, or not applicable
- **Resulting verification state**
- **Notes** on marginal cases, interpretation decisions, or concerns
- **Confidence rating** (see [Epistemic Confidence](#epistemic-confidence)) assigned by the verifier

Verification records are immutable once completed. If re-verification is needed, a new record is created and linked to the previous one.

---

### Epistemic Confidence

**Epistemic confidence** is a numerical rating, from 0.0 to 1.0, representing the verifier's assessment of how strongly the available evidence supports the claim, independent of the claim's formal verification state.

Confidence is not probability. It is an explicit declaration of uncertainty that travels with the claim. A claim may be Verified (state) with a confidence of 0.65 — meaning it has passed the verification criteria, but the verifier judges the evidence to be only moderately strong.

The confidence rating is used to weight claims when they appear as evidence items in subsequent reasoning chains. A chain of high-confidence verified claims supports a stronger conclusion than a chain of low-confidence verified claims.

Standard confidence bands:

| Band | Range | Interpretation |
|------|-------|----------------|
| High | 0.85 – 1.0 | Strong evidence, well-formed reasoning, independent verification |
| Moderate | 0.65 – 0.84 | Adequate evidence, sound reasoning, some gaps acknowledged |
| Low | 0.40 – 0.64 | Limited evidence, reasoning has notable gaps, use with caution |
| Speculative | 0.00 – 0.39 | Evidence is thin or circumstantial; claim requires further investigation |

---

## Structural Concepts

### Pattern

A **pattern** is a reusable, documented solution to a recurring reasoning or verification challenge. Patterns in VERA follow the canonical [Pattern Template](./pattern-template.md) and must themselves be verified claims — not informal recommendations.

Patterns are not prescriptions. They document what has worked in identified contexts. Applying a pattern without verifying that the current context matches the pattern's context is a reasoning error.

---

### Domain

A **domain** is one of the six capability areas measured by the [VERA Maturity Model](../maturity-model/overview.md). The six domains are:

| Domain | Description |
|--------|-------------|
| **Evidence** | How evidence is identified, collected, classified, and maintained |
| **Reasoning** | How reasoning chains are constructed, documented, and evaluated |
| **Verification** | How claims are submitted to, processed through, and resolved by verification |
| **Governance** | How VERA practices are mandated, resourced, audited, and improved |
| **Sovereignty** | How authority over data, reasoning, and conclusions is maintained |
| **Integration** | How VERA practices connect to existing systems, workflows, and tools |

An organization's VERA maturity level may differ by domain. It is common — and expected — for Governance and Integration to lag behind Evidence and Reasoning during early adoption.

---

### Maturity Level

**Maturity level** is one of five stages in the VERA Maturity Model, representing increasing sophistication in VERA practice:

| Level | Name | Defining characteristic |
|-------|------|------------------------|
| 1 | **Aware** | VERA concepts are understood; no systematic practice exists |
| 2 | **Exploring** | VERA is applied to selected claims; practice is inconsistent |
| 3 | **Practicing** | VERA is applied systematically to all significant claims; results are auditable |
| 4 | **Governing** | VERA practices are institutionalized, measured, and continuously improved |
| 5 | **Sovereign** | VERA enables full epistemic sovereignty; the framework itself is subject to VERA review |

Maturity levels are assessed per domain and per organization (or individual). A single number cannot fully characterize a complex organization's VERA maturity.

---

### Sovereignty

**Sovereignty** in VERA means the state in which an individual or organization retains ultimate authority over:

- The **data** they rely on (they can access, audit, and export it)
- The **reasoning** they use (it is explicit, documented, and challengeable)
- The **conclusions** they reach (they are not imposed by opaque external systems)
- The **verification processes** they trust (they can audit those processes)

Sovereignty is not isolation. A sovereign VERA practitioner can and should use external evidence, expert testimony, and AI-assisted reasoning. What they cannot do — while maintaining sovereignty — is accept conclusions without access to the evidence and reasoning that produced them.

---

## Error Taxonomy

### Selective Citation

**Selective citation** is the practice of including only evidence that supports a claim while omitting evidence that complicates or contradicts it. It is a violation of Evidence Primacy and renders a claim's evidence set invalid.

Selective citation includes: cherry-picking favorable studies while omitting unfavorable ones; citing the summary of a document while omitting its caveats; referencing a prior claim's conclusion while omitting its uncertainty rating.

---

### Source Collapse

**Source collapse** is the reasoning error of treating multiple evidence items as independent when they derive from the same underlying source. It inflates apparent confidence by counting one piece of evidence multiple times.

*See also: [Evidence Independence](#evidence-independence).*

---

### Reasoning Gap

A **reasoning gap** is a logical step in a reasoning chain that is assumed without documentation. Reasoning gaps are often the location of an argument's most consequential assumptions. VERA's Verification Protocol requires that all reasoning gaps be identified and either filled (with a documented reasoning step) or flagged (as an acknowledged assumption).

---

### Chain Laundering

**Chain laundering** is the practice of using a weakly supported or unverified claim as if it were well-supported evidence in a subsequent reasoning chain. It is the epistemic equivalent of money laundering — the weak evidence is obscured by being embedded in a chain that appears solid.

Chain laundering occurs when a Testimonial-quality assertion is cited as Secondary evidence; when an Unverified claim is used as a premise in a reasoning chain without disclosure; or when a Contested claim is cited without noting its contested status.

---

### Verification Capture

**Verification capture** occurs when the verification process is structurally unable to produce a negative result — when the verifier is too close to the claimant, too dependent on the claim being true, or operating under criteria calibrated to pass rather than evaluate. A captured verification process produces compliance theater rather than epistemic accountability.

---

## Notation Conventions

| Symbol | Meaning |
|--------|---------|
| `VERA-C-[YYYY]-[NNNN]` | Claim identifier |
| `VERA-P-[NNNN]` | Pattern identifier |
| `VERA-V-[NNNN]` | Verification record identifier |
| ○ ◐ ◑ ● ◈ ✗ | Verification states (Unverified, Pending, Partial, Verified, Contested, Refuted) |
| E1, E2, … | Evidence item references within a reasoning chain |
| C1 → C2 | Claim C2 uses verified Claim C1 as evidence |
| [conf: 0.78] | Inline confidence rating |

---

*Proceed to [Verification Protocol](./verification-protocol.md) to understand how claims move through the VERA lifecycle.*
