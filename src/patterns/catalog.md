# Pattern Catalog

The Pattern Catalog is the master index of all VERA patterns. Patterns are reusable, documented solutions to recurring challenges in evidence management, reasoning construction, and verification practice. Every pattern in this catalog follows the canonical [Pattern Template](../foundations/pattern-template.md) and is itself a verified claim.

Use this catalog to find the right pattern for a situation you are facing. Browse by domain, maturity level, or use case.

---

## Complete Pattern Index

| ID | Name | Domain | Complexity | Min. Level | Status |
|----|------|--------|------------|------------|--------|
| [VERA-P-0001](#vera-p-0001) | Absence-of-Evidence Assessment | Evidence | Moderate | 2 | Verified |
| [VERA-P-0002](#vera-p-0002) | Conflicted Source Disclosure | Evidence | Moderate | 2 | Verified |
| [VERA-P-0003](#vera-p-0003) | AI-Generated Evidence Documentation | Evidence | Moderate | 2 | Verified |
| [VERA-P-0004](#vera-p-0004) | Source Collapse Detection and Remediation | Evidence | Simple | 2 | Verified |
| [VERA-P-0005](#vera-p-0005) | Time-Sensitive Evidence Management | Evidence | Moderate | 3 | Verified |
| [VERA-P-0006](#vera-p-0006) | Compound Claim Decomposition | Reasoning | Moderate | 2 | Verified |
| [VERA-P-0007](#vera-p-0007) | Hidden Assumption Excavation | Reasoning | Moderate | 2 | Verified |
| [VERA-P-0008](#vera-p-0008) | Contrary Evidence Integration | Reasoning | Moderate | 2 | Verified |
| [VERA-P-0009](#vera-p-0009) | Analogical Reasoning Validation | Reasoning | Complex | 3 | Verified |
| [VERA-P-0010](#vera-p-0010) | Self-Verification with Adversarial Stance | Verification | Moderate | 2 | Verified |
| [VERA-P-0011](#vera-p-0011) | Expert Verifier Onboarding | Verification | Complex | 3 | Verified |
| [VERA-P-0012](#vera-p-0012) | Cascading Claim Update | Verification | Complex | 3 | Verified |
| [VERA-P-0013](#vera-p-0013) | Claim Confidence Calibration | Verification | Complex | 4 | Verified |

---

## Patterns by Domain

### Evidence Domain
*Patterns for evidence identification, assembly, rating, and maintenance.*

- **[VERA-P-0001](./evidence.md#vera-p-0001)** — Absence-of-Evidence Assessment: How to assess the epistemic significance of evidence you expected to find but didn't.
- **[VERA-P-0002](./evidence.md#vera-p-0002)** — Conflicted Source Disclosure: How to handle evidence from sources with a financial or institutional stake in the claim's outcome.
- **[VERA-P-0003](./evidence.md#vera-p-0003)** — AI-Generated Evidence Documentation: How to document evidence that was retrieved, summarized, or synthesized by an AI system.
- **[VERA-P-0004](./evidence.md#vera-p-0004)** — Source Collapse Detection and Remediation: How to identify and correct evidence sets where multiple items trace to the same underlying source.
- **[VERA-P-0005](./evidence.md#vera-p-0005)** — Time-Sensitive Evidence Management: How to manage evidence in rapidly changing domains where evidence decays in reliability over time.

### Reasoning Domain
*Patterns for constructing, documenting, and evaluating reasoning chains.*

- **[VERA-P-0006](./reasoning.md#vera-p-0006)** — Compound Claim Decomposition: How to systematically break compound assertions into independently verifiable atomic claims.
- **[VERA-P-0007](./reasoning.md#vera-p-0007)** — Hidden Assumption Excavation: A systematic protocol for surfacing the assumptions embedded in a reasoning chain that the author doesn't realize they are making.
- **[VERA-P-0008](./reasoning.md#vera-p-0008)** — Contrary Evidence Integration: A decision framework for evaluating contrary evidence and selecting the appropriate response: outweigh, distinguish, qualify, or concede.
- **[VERA-P-0009](./reasoning.md#vera-p-0009)** — Analogical Reasoning Validation: How to document and evaluate analogical inferences rigorously, including similarity scoring and conclusion scope determination.

### Verification Domain
*Patterns for verification process design, execution, and governance.*

- **[VERA-P-0010](./verification.md#vera-p-0010)** — Self-Verification with Adversarial Stance: A structured protocol for self-verification that mitigates optimism bias when independent verifiers are unavailable.
- **[VERA-P-0011](./verification.md#vera-p-0011)** — Expert Verifier Onboarding: How to engage a domain expert as a VERA verifier when the expert lacks VERA process training.
- **[VERA-P-0012](./verification.md#vera-p-0012)** — Cascading Claim Update: How to identify and re-evaluate downstream claims when an upstream claim changes verification state.
- **[VERA-P-0013](./verification.md#vera-p-0013)** — Claim Confidence Calibration: A program for ensuring that confidence ratings assigned by different verifiers are consistent and predictive.

---

## Patterns by Maturity Level

The Maturity Level column in each pattern indicates the minimum VERA maturity level at which the pattern is typically applied. Practitioners at lower levels may encounter the pattern's problem but will not yet have the infrastructure to apply the solution consistently.

### Available at Level 2 (Exploring)

Practitioners beginning systematic VERA work will most often need these:

| Pattern | Why it's needed early |
|---------|----------------------|
| VERA-P-0001 Absence-of-Evidence Assessment | The most common Phase 2 gap; first evidence set review almost always reveals absent expected evidence |
| VERA-P-0002 Conflicted Source Disclosure | Industry-produced, advocacy-produced, and vendor-produced evidence is ubiquitous; handling it correctly is foundational |
| VERA-P-0003 AI-Generated Evidence Documentation | Most practitioners now use AI tools; the evidence chain-of-custody problem appears immediately |
| VERA-P-0004 Source Collapse Detection and Remediation | Source collapse is the most common Level 2 evidence error; early detection prevents it from compounding |
| VERA-P-0006 Compound Claim Decomposition | Virtually every significant assertion contains multiple claims; decomposition is needed in Phase 1 |
| VERA-P-0007 Hidden Assumption Excavation | Undocumented assumptions are the most common Level 2 reasoning failure |
| VERA-P-0008 Contrary Evidence Integration | Contrary evidence always appears; practitioners need a framework for addressing it before their first verification |
| VERA-P-0010 Self-Verification with Adversarial Stance | Independent verification is rarely available at Level 2; this pattern makes self-verification rigorous |

### Available at Level 3 (Practicing)

These patterns require systematic practice infrastructure before they are useful:

| Pattern | Why it's needed at Level 3 |
|---------|---------------------------|
| VERA-P-0005 Time-Sensitive Evidence Management | Review cadence infrastructure must exist before evidence expiry tracking is practical |
| VERA-P-0009 Analogical Reasoning Validation | Requires reasoning chain fluency; premature application produces mechanical similarity scoring without judgment |
| VERA-P-0011 Expert Verifier Onboarding | Requires a verification process mature enough to be explained to an expert; Level 2 verification is not |
| VERA-P-0012 Cascading Claim Update | Requires a populated claim registry with dependency tracking; not applicable without one |

### Available at Level 4 (Governing)

This pattern requires governance infrastructure and a multi-verifier pool:

| Pattern | Why it's needed at Level 4 |
|---------|---------------------------|
| VERA-P-0013 Claim Confidence Calibration | Requires multiple verifiers, historical data, and a governance function to manage the calibration program |

---

## Patterns by Use Case

Use these guides to find patterns for the situation you are facing right now.

### "I'm in Phase 2 and my evidence search has a problem."

| Situation | Pattern |
|-----------|---------|
| Expected evidence type not found | VERA-P-0001 |
| Evidence comes from a conflicted source | VERA-P-0002 |
| AI tool was used to find or summarize evidence | VERA-P-0003 |
| Multiple evidence items seem to come from the same source | VERA-P-0004 |
| Evidence is current but may become stale | VERA-P-0005 |
| Evidence supports the claim but is contradicted by other evidence | VERA-P-0008 |

### "I'm in Phase 3 and my reasoning chain has a problem."

| Situation | Pattern |
|-----------|---------|
| The claim is too complex to address as a single statement | VERA-P-0006 |
| I can't identify all the assumptions my reasoning is making | VERA-P-0007 |
| Some evidence contradicts my claim; I'm not sure how to handle it | VERA-P-0008 |
| My reasoning chain uses "this is like that other case" logic | VERA-P-0009 |

### "I'm in Phase 4 and my verification process has a problem."

| Situation | Pattern |
|-----------|---------|
| No independent verifier is available | VERA-P-0010 |
| The only available verifier has domain expertise but no VERA training | VERA-P-0011 |
| I'm verifying a claim that uses a recently-changed upstream claim | VERA-P-0012 |
| Confidence ratings across the team seem inconsistent | VERA-P-0013 |

### "I've discovered a problem after verification."

| Situation | Pattern |
|-----------|---------|
| A verified claim's evidence is now stale | VERA-P-0005 |
| A verified claim's upstream evidence source has changed state | VERA-P-0012 |
| Different verifiers are giving very different confidence ratings | VERA-P-0013 |

---

## Pattern Entries (Quick Reference)

The following gives the one-sentence summary for each pattern. Click the ID to go to the full pattern.

<a id="vera-p-0001"></a>
**VERA-P-0001 — Absence-of-Evidence Assessment** *(Evidence / Moderate / Level 2)*
Assessing the epistemic significance of evidence types expected but not found, and translating that significance into a calibrated materiality rating and confidence adjustment. Full pattern in [Evidence Patterns](./evidence.md#vera-p-0001) and as worked example in [Pattern Template](../foundations/pattern-template.md).

<a id="vera-p-0002"></a>
**VERA-P-0002 — Conflicted Source Disclosure** *(Evidence / Moderate / Level 2)*
A graded disclosure-and-corroboration framework for evidence from sources with a financial, institutional, or personal stake in the claim's outcome. Full pattern in [Evidence Patterns](./evidence.md#vera-p-0002).

<a id="vera-p-0003"></a>
**VERA-P-0003 — AI-Generated Evidence Documentation** *(Evidence / Moderate / Level 2)*
A three-tier handling protocol for evidence retrieved, summarized, or synthesized by AI systems, with chain-of-custody and quality-rating requirements for each tier. Full pattern in [Evidence Patterns](./evidence.md#vera-p-0003).

<a id="vera-p-0004"></a>
**VERA-P-0004 — Source Collapse Detection and Remediation** *(Evidence / Simple / Level 2)*
A backward-trace audit that reveals shared roots among evidence items and consolidates dependent items into an accurate count of independent sources. Full pattern in [Evidence Patterns](./evidence.md#vera-p-0004).

<a id="vera-p-0005"></a>
**VERA-P-0005 — Time-Sensitive Evidence Management** *(Evidence / Moderate / Level 3)*
An evidence-level expiry annotation system with three decay-rate categories and monitoring protocols linked to claim review triggers. Full pattern in [Evidence Patterns](./evidence.md#vera-p-0005).

<a id="vera-p-0006"></a>
**VERA-P-0006 — Compound Claim Decomposition** *(Reasoning / Moderate / Level 2)*
A three-test decomposition method (independence test, evidence test, verification test) applied recursively until each component is atomic and independently verifiable. Full pattern in [Reasoning Patterns](./reasoning.md#vera-p-0006).

<a id="vera-p-0007"></a>
**VERA-P-0007 — Hidden Assumption Excavation** *(Reasoning / Moderate / Level 2)*
A systematic interrogation of each reasoning step using three question types designed to surface assumptions that feel like facts. Full pattern in [Reasoning Patterns](./reasoning.md#vera-p-0007).

<a id="vera-p-0008"></a>
**VERA-P-0008 — Contrary Evidence Integration** *(Reasoning / Moderate / Level 2)*
A structured evaluation framework for contrary evidence based on quality tier, relevance, and independence, with a decision matrix for selecting the appropriate response. Full pattern in [Reasoning Patterns](./reasoning.md#vera-p-0008).

<a id="vera-p-0009"></a>
**VERA-P-0009 — Analogical Reasoning Validation** *(Reasoning / Complex / Level 3)*
Structured similarity-disanalogy analysis with a similarity scoring rubric that determines the permissible scope of an analogical conclusion. Full pattern in [Reasoning Patterns](./reasoning.md#vera-p-0009).

<a id="vera-p-0010"></a>
**VERA-P-0010 — Self-Verification with Adversarial Stance** *(Verification / Moderate / Level 2)*
A role-switch protocol with a mandatory time gap, adversarial criteria checklist, and explicit confidence penalty that makes self-verification meaningfully rigorous. Full pattern in [Verification Patterns](./verification.md#vera-p-0010).

<a id="vera-p-0011"></a>
**VERA-P-0011 — Expert Verifier Onboarding** *(Verification / Complex / Level 3)*
A structured briefing and interview protocol that translates VERA verification criteria into domain-specific language for an expert who has not been trained in VERA. Full pattern in [Verification Patterns](./verification.md#vera-p-0011).

<a id="vera-p-0012"></a>
**VERA-P-0012 — Cascading Claim Update** *(Verification / Complex / Level 3)*
A dependency-registration and impact-triage protocol that identifies downstream claims affected by an upstream claim's state change and prioritizes re-verification. Full pattern in [Verification Patterns](./verification.md#vera-p-0012).

<a id="vera-p-0013"></a>
**VERA-P-0013 — Claim Confidence Calibration** *(Verification / Complex / Level 4)*
An anchor-example calibration program with verifier consistency metrics and a confidence committee process for high-stakes claims. Full pattern in [Verification Patterns](./verification.md#vera-p-0013).

---

## How to Contribute a New Pattern

Patterns emerge from practice. If you have encountered a recurring challenge that is not addressed by an existing pattern, and you have resolved it in at least two distinct cases, you have the raw material for a new pattern.

See [Pattern Template: How to Propose a New Pattern](../foundations/pattern-template.md#how-to-propose-a-new-pattern) for the submission process.

Before proposing, search this catalog for existing patterns that might address your situation. A proposed pattern that duplicates an existing one — even partially — should be presented as a proposed revision or extension of the existing pattern, not as a new one.
