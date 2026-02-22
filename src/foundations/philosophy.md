# Philosophy & Principles

> *"We do not reason to find truth so much as to find reasons. VERA is the discipline of closing the gap between the two."*

---

## The Epistemic Problem VERA Addresses

Every decision — personal, organizational, scientific, political — rests on claims about the world. Those claims are supported, to varying degrees, by evidence. The reasoning connecting evidence to claim is often invisible, implicit, or absent altogether.

This is not a new problem. Epistemologists have grappled with it for millennia. But three developments have made it a practical crisis:

**Scale.** A single person can now broadcast a claim to millions. A single AI system can generate millions of claims in minutes. The volume of reasoning that flows through the world has outpaced any individual's ability to evaluate it.

**Opacity.** The reasoning chains inside AI systems, institutional processes, and expert recommendations are typically not exposed to the people who depend on them. You receive the conclusion. The evidence and reasoning are invisible.

**Decoupling.** Claims travel far from their origins. An assertion that was hedged, contextualized, and conditional at the source arrives stripped of those qualifications. Verification status does not travel with claims; conclusions do.

VERA's design philosophy holds that these problems are structural, not behavioral. You cannot fix them by asking people to be more careful. You fix them by building a structure in which claims, evidence, reasoning, and verification are bound together and cannot be separated.

---

## Foundational Commitments

VERA rests on three philosophical commitments. They are not provable axioms — they are reasoned choices about how to structure a practical epistemology. Adopting VERA means accepting them as working principles.

### Commitment 1: Epistemic Humility

No claim is beyond question. No source is beyond error. No reasoning chain, however elegant, is immune to revision when new evidence arrives.

This does not mean all claims are equally uncertain. It means that certainty is a gradient, not a binary — and that the appropriate response to a claim's uncertainty is to document it explicitly rather than round it to "true" or "false."

In VERA, the [Verification State](./lexicon.md#verification-state) construct operationalizes this commitment. A claim is not "verified" or "unverified" in a binary sense. It exists in one of six states, each of which carries specific implications for how the claim may be used in further reasoning.

### Commitment 2: Traceability as a First-Order Value

If you cannot trace a conclusion to the evidence and reasoning that produced it, you cannot evaluate it, update it, or responsibly act on it.

Traceability is costly. It requires documentation discipline, structured formats, and time. VERA accepts this cost and asks practitioners to accept it as well. The cost of traceability is paid once, when a claim is documented. The cost of its absence is paid repeatedly — every time someone needs to evaluate the claim and cannot, every time the claim is updated without propagating the change, every time an error propagates because no one can trace it back to its source.

### Commitment 3: Sovereignty as Non-Negotiable

The person or organization whose decisions are affected by a claim must retain the ability to evaluate, challenge, and reject that claim. This is not merely a legal or political right — it is an epistemic requirement. A conclusion you cannot evaluate is, for practical purposes, a belief imposed from outside.

This commitment has radical implications. It means VERA cannot be implemented in a way that makes verification dependent on opaque external authorities. It means AI tools used within VERA must expose their reasoning, not just their conclusions. It means organizational VERA implementations must ensure that the people making decisions have access to the evidence and reasoning that inform them.

---

## The VERA Ontology

VERA works with a small set of precisely defined objects. Understanding their relationships is essential to understanding the framework.

```
Evidence ──── supports ──→ Claim
   │                          │
   │                          │
   ▼                          ▼
Evidence               Reasoning Chain
 Quality                    │
                            │
                            ▼
                    Verification State
                            │
                            │
                            ▼
                   Verified Conclusion
```

**Evidence** is the raw material. It is always external to the claim — a document, a measurement, an observation, a prior verified claim. Evidence has quality (rated on a four-tier scale) and provenance (a chain of custody from source to application).

**Claims** are structured assertions. They reference their supporting evidence, document the reasoning chain connecting evidence to conclusion, and carry a verification state. A claim without these elements is an *assertion* — a weaker epistemic object that VERA treats with appropriate caution.

**Reasoning Chains** are the explicit logical steps connecting evidence to a claim. They are not summaries or conclusions. They are step-by-step arguments: "Evidence E1 establishes X. Evidence E2 establishes Y. X and Y together, by principle P, imply claim C." The quality of a reasoning chain is evaluated on four dimensions: validity (the logic is sound), relevance (the evidence addresses the claim), completeness (no crucial premise is hidden), and independence (the evidence items are not all proxies for the same underlying source).

**Verification** is the process of evaluating whether the stated evidence and reasoning actually support the claim. It is separate from the act of making a claim — ideally performed by someone other than the claimant.

**Verification State** is the current status of a claim in the verification process. It changes as evidence is gathered, reasoning is scrutinized, and review is performed.

---

## The Six Principles of VERA

These six principles constitute the operational philosophy of VERA. They are ordered by priority: when principles conflict, earlier principles take precedence.

### Principle 1: Evidence Primacy

*Every claim that matters must be traceable to evidence.*

"Matters" here means: informs a decision, guides an action, supports another claim, or is communicated beyond its originator. Personal beliefs and casual assertions are outside VERA's scope. Claims with practical stakes are not.

Evidence Primacy does not require that all evidence be primary-source empirical data. Testimony, expert judgment, and prior verified claims are all valid evidence types — but they must be documented, sourced, and quality-rated. "Because I said so" and "everyone knows" are not evidence.

Evidence Primacy also requires documentation of the *absence* of expected evidence. If a claim would be strengthened by evidence type X, and evidence type X is absent, that absence must be noted and explained. Selective citation — mentioning only supporting evidence — violates Evidence Primacy.

### Principle 2: Reasoning Transparency

*The reasoning connecting evidence to conclusion must be made explicit.*

Implicit reasoning is the most common source of reasoning error. Conclusions that feel obvious usually conceal a chain of reasoning that, when made explicit, reveals assumptions, gaps, or logical leaps. VERA requires that reasoning chains be documented in full — not summarized, not paraphrased, but step by step.

Reasoning Transparency extends to AI-assisted reasoning. When a claim is generated or substantially shaped by an AI system, the reasoning that system provided must be included in the claim's documentation. "The AI said so" is not a reasoning chain. The AI's stated reasoning — with its assumptions, its evidence references, and its caveats — must be captured and evaluated.

### Principle 3: Verification Independence

*Verification is more reliable when conducted by someone other than the claimant.*

This principle does not prohibit self-verification. In early stages of VERA adoption, and for low-stakes claims, self-verification is acceptable. But the framework explicitly grades verification based on independence: a claim verified by its author carries less epistemic weight than one verified by a peer, which carries less weight than one verified by an expert in the relevant domain.

Verification Independence also means that the verification process must be capable of producing a negative result. A verification regime that never fails to verify is not verification — it is endorsement. VERA verification must be conducted against explicit criteria that can be failed.

### Principle 4: Sovereignty Preservation

*Individuals and organizations must retain ultimate authority over their reasoning and conclusions.*

VERA is a tool for reasoning better. It is not a mechanism for transferring epistemic authority to external validators. When an organization adopts VERA, it does not outsource its judgment — it structures its judgment so that it is more defensible and auditable.

Sovereignty Preservation has implications for how VERA is implemented. Verification processes must be designed so that the people whose decisions depend on a claim can access its evidence and reasoning. Tooling must be open enough to be audited. Verification authorities must be accountable to the communities they serve.

### Principle 5: Progressive Maturity

*VERA capability grows incrementally, and incomplete adoption is better than no adoption.*

The Maturity Model documents five levels of VERA capability. It is not a pass/fail system. An organization operating at Level 2 (Exploring) is doing something valuable. An organization at Level 1 (Aware) that is moving toward Level 2 is doing something even more valuable.

Progressive Maturity also means that VERA is applied selectively at first. Not every claim needs full VERA treatment. Starting with the claims that matter most — the ones informing significant decisions — builds the habit and the infrastructure that eventually support broader application.

### Principle 6: Pattern Reusability

*Solutions to recurring reasoning challenges should be documented as reusable patterns.*

Inventing the wheel is costly. Every organization that tries to document evidence systematically rediscovers the same problems: how to rate evidence quality, how to handle conflicting evidence, how to document negative results, how to version claims when evidence changes. VERA's Patterns Library captures solutions to these problems so they do not need to be rediscovered each time.

Pattern Reusability also serves as a check against local rationalization. A pattern that works in one context but cannot be generalized is a warning sign. A pattern that has been applied in multiple organizations and contexts, and documented each time, accumulates a kind of empirical verification that single-use solutions cannot achieve.

---

## What VERA Is Not

Clarifying boundaries prevents misapplication.

**VERA is not a fact-checking service.** Fact-checking evaluates specific claims against available evidence. VERA is a framework for *how* to evaluate claims — the process, standards, and documentation that make any evaluation reproducible and trustworthy. A fact-checking service might use VERA. VERA is not that service.

**VERA is not an AI system.** AI tools can implement VERA protocols, assist with evidence collection, structure reasoning chains, and flag potential verification failures. But VERA's commitments — especially Sovereignty Preservation — require that no single AI system be the authoritative arbiter of VERA compliance.

**VERA is not a substitute for domain expertise.** Evaluating whether evidence supports a claim in molecular biology requires expertise in molecular biology. VERA provides the *structure* for that evaluation, not the substance. Domain knowledge remains essential; VERA ensures that domain knowledge is documented and applied systematically.

**VERA is not a certification program (in the credentialing sense).** Organizations and individuals can be described as operating at a given Maturity Level. That description is a diagnostic tool, not a credential. It has value only to the extent that the maturity assessment is honest and rigorous.

---

## The Relationship Between VERA and Truth

VERA does not claim to be a truth-finding machine. Evidence is imperfect. Reasoning is fallible. Verification is conducted by humans. A claim can pass full VERA verification and still be wrong.

What VERA provides is not truth — it provides *epistemic accountability*. When a verified VERA claim turns out to be wrong, the error is traceable. The evidence that was cited can be re-examined. The reasoning that connected evidence to conclusion can be scrutinized. The verification process that passed the claim can be audited. This traceability is the foundation of learning from error rather than merely being hurt by it.

The goal of VERA is not a world without false beliefs. It is a world where false beliefs are harder to propagate, easier to detect, and possible to correct.

---

*Proceed to [Lexicon: Canonical Definitions](./lexicon.md) to establish the precise vocabulary that makes VERA's protocols unambiguous.*

---

*VERA is authored by Daniel Flügger and licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Free to use, share, and build on — attribution required. [danielflugger.com](https://danielflugger.com)*
