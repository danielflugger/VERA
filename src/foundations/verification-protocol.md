# Verification Protocol

The Verification Protocol is VERA's procedural core. It specifies, step by step, how a raw assertion becomes a documented claim, moves through verification, and reaches a final epistemic state. Following the protocol produces reproducible results: two verifiers working independently on the same claim and evidence should reach the same verification state.

This document describes VERA Verification Protocol version 1.0. The version is significant — claims record the protocol version under which they were verified, so that verification standards can evolve without retroactively changing the status of existing records.

---

## Protocol Overview

The protocol comprises five phases executed in sequence. Each phase has defined inputs, required activities, and outputs. A phase cannot be marked complete until its outputs satisfy the stated requirements.

```
Phase 1: Claim Formulation
        │
        ▼
Phase 2: Evidence Assembly
        │
        ▼
Phase 3: Reasoning Construction
        │
        ▼
Phase 4: Verification Assessment
        │
        ▼
Phase 5: Documentation & Publication
```

Phases 1–3 are the claimant's responsibility. Phase 4 is the verifier's responsibility. Phase 5 is shared. For self-verification, a single person or team executes all five phases, but must treat Phase 4 as a deliberate change of role — actively looking for weaknesses rather than defending the claim.

---

## Phase 1: Claim Formulation

**Input**: A raw assertion — something believed to be true and worth documenting.

**Objective**: Transform the assertion into a precisely stated, uniquely identified claim ready for evidence assembly.

### Step 1.1 — State the Assertion Precisely

Write the assertion in a single declarative sentence. Vague, compound, or hedged assertions must be decomposed before proceeding.

*Test*: Could two people read this statement and disagree on what would count as evidence for or against it? If yes, the statement is not yet precise enough.

**Common problems at this step:**
- **Compound assertions**: "Our process is efficient and our output quality is high" contains two claims. Separate them.
- **Weasel words**: "Generally," "usually," "often," and similar hedges embed ambiguity into the claim itself. State the actual scope: "In 87% of cases observed between January and June 2025."
- **Tautologies**: "AI systems that produce inaccurate outputs are unreliable" is not a claim about the world — it is a definitional statement. Remove it from the VERA pipeline.

### Step 1.2 — Decompose Compound Claims

If the assertion cannot be stated in a single precise sentence without losing essential meaning, decompose it into multiple claims. Each claim proceeds through the protocol independently. Compound conclusions are reconstructed in Phase 3 by using the verified sub-claims as evidence items.

### Step 1.3 — Assign a Claim Identifier

Every claim receives a unique identifier before proceeding: `VERA-C-[YYYY]-[NNNN]`, where YYYY is the four-digit year and NNNN is a sequential number within that year. For individual practitioners without an organizational registry, use initials as a prefix: `VERA-C-DJF-2025-0001`.

The identifier is permanent. If the claim is revised, the revision is documented as a new version of the same claim (e.g., `VERA-C-2025-0001 v2`), not as a new claim, so that downstream claims that cite this one can identify the version they used.

### Step 1.4 — Record Claim Context

Document:
- **Claimant**: Individual or team making the claim
- **Date initiated**: When Phase 1 was begun
- **Purpose**: Why this claim is being documented (what decision it informs, what argument it supports)
- **Scope**: The conditions under which the claim is intended to hold (domain, time period, population, geography, etc.)
- **Prior art**: Related prior claims in the VERA registry that this claim extends, contradicts, or supersedes

**Output**: A Claim Record stub containing the claim identifier, precise statement, and context metadata. Verification state is set to **Unverified** (○).

---

## Phase 2: Evidence Assembly

**Input**: The Claim Record stub from Phase 1.

**Objective**: Identify, locate, document, and rate all relevant evidence — including evidence that complicates or contradicts the claim.

### Step 2.1 — Identify Evidence Sources

Before retrieving evidence, list the types of evidence that would be relevant to evaluating the claim. This prospective list is the foundation of the evidence search strategy. It must be documented — a search strategy recorded only after evidence has been found is vulnerable to unconscious selectivity.

For each evidence type on the list, note:
- What form would this evidence take? (dataset, document, experiment, testimony, etc.)
- Where is this evidence likely to exist?
- What would it mean for the claim if this evidence is absent?

### Step 2.2 — Conduct the Evidence Search

Retrieve evidence using the pre-documented search strategy. For each item found:

1. Create an **Evidence Item Record** with source reference, access date, and a brief description
2. Note whether this item was on the prospective list (anticipated evidence) or discovered during search (unanticipated evidence)
3. Note the relevance of the item: does it support, complicate, or contradict the claim?

**Do not filter at this stage.** Contradicting evidence is recorded identically to supporting evidence. Filtering happens in Phase 3.

### Step 2.3 — Rate Evidence Quality

Apply the four-tier quality rating to each evidence item:

| Tier | Questions to ask |
|------|-----------------|
| **Primary (Tier 1)** | Is this the original source? Did the claimant directly observe or measure this? Is this an original document rather than a copy or summary? |
| **Secondary (Tier 2)** | Has this been interpreted by a domain expert? Is it a synthesis of primary sources? Has it been peer-reviewed or editorially reviewed? |
| **Tertiary (Tier 3)** | Is this a textbook, encyclopedia, or journalistic account? Does it reference secondary sources? |
| **Testimonial (Tier 4)** | Is this an expert's assertion without underlying data? Is this firsthand account where the underlying evidence is inaccessible? |

When evidence spans multiple tiers (e.g., a peer-reviewed meta-analysis that includes some original data), rate it at the tier that describes its dominant character.

### Step 2.4 — Assess Evidence Independence

Group the evidence items and assess which ones share upstream sources. Mark items as Independent, Correlated, or Dependent (see [Lexicon: Evidence Independence](./lexicon.md#evidence-independence)).

Dependent items are not discarded — they are consolidated into a single item with a note explaining why they are treated as one. The consolidation is documented so that the verifier can evaluate it.

### Step 2.5 — Document Absent Evidence

Return to the prospective list from Step 2.1. For each evidence type that was listed but not found:

- Note that it was not found
- Assess what this absence implies for the claim: neutral, weakening, or significantly weakening
- If significantly weakening: note this explicitly in the Claim Record

**Output**: A complete Evidence Set — all items rated, independence assessed, and absent evidence noted. The evidence set is attached to the Claim Record. Verification state remains **Unverified** (○).

---

## Phase 3: Reasoning Construction

**Input**: The Claim Record with attached Evidence Set.

**Objective**: Build an explicit reasoning chain connecting the evidence set to the claim's statement.

### Step 3.1 — Map Evidence to Claim Components

Decompose the claim's statement into its constituent logical components. For each component, identify which evidence items are relevant to it. The mapping does not need to be one-to-one: multiple evidence items may support one component, and one evidence item may support multiple components.

This mapping reveals:
- Components that are well-supported (multiple independent evidence items)
- Components that are weakly supported (single evidence item, or only low-quality items)
- Components that are unsupported (no evidence items address them)

Unsupported components require one of three responses: gather additional evidence (return to Phase 2), reduce the scope of the claim to exclude the unsupported component, or explicitly flag the unsupported component as an assumption.

### Step 3.2 — Identify the Logical Structure

Determine how the evidence connects to the conclusion. VERA recognizes four inference types:

| Type | Description | Strength |
|------|-------------|---------|
| **Deductive** | Conclusion follows necessarily from premises | Strongest, but requires premises to be certain |
| **Inductive** | Conclusion generalizes from observed instances | Strong when instances are numerous and representative |
| **Abductive** | Conclusion is the best explanation of the evidence | Moderate; requires ruling out alternative explanations |
| **Analogical** | Conclusion infers from similarity to another case | Weakest; requires strong, well-documented similarity |

Most real-world reasoning chains combine inference types. The chain must document which type is used at each step.

### Step 3.3 — Write the Reasoning Chain

Write the chain step by step, using this format for each step:

```
Step N:
  Premises:     [E1, E2] / [Step N-1 conclusion]
  Inference:    [Deductive / Inductive / Abductive / Analogical]
  Reasoning:    [The argument in plain language]
  Conclusion:   [The intermediate conclusion this step produces]
  Confidence:   [0.0–1.0, with explanation]
```

The chain is complete when its final conclusion matches the claim's statement exactly. If the final conclusion is stronger or weaker than the stated claim, revise the claim statement (returning to Phase 1, Step 1.1) or revise the reasoning chain until they match.

### Step 3.4 — Identify and Document Assumptions

Every reasoning chain rests on assumptions — things taken as true without direct evidence. Identify all assumptions explicit in the chain and any hidden assumptions that the chain requires.

For each assumption:
- State the assumption precisely
- Assess whether it is: *widely accepted* (minimal documentation needed), *domain-specific* (cite authority), or *contested* (must be flagged prominently)
- If contested, consider whether the claim should be scoped to conditions under which the assumption holds

### Step 3.5 — Address Contradicting Evidence

Return to the evidence items marked as complicating or contradicting. The reasoning chain must address each one. Valid responses include:

- **Outweigh**: The contradicting evidence is weaker (lower tier, less independent) than the supporting evidence; explain why
- **Distinguish**: The contradicting evidence applies to a different scope than the claim; explain the distinction
- **Qualify**: The claim is revised to acknowledge the contradiction as a genuine limitation
- **Concede**: The contradicting evidence is decisive; the claim cannot be maintained

Any response other than "Concede" must be argued, not asserted.

**Output**: A complete Reasoning Chain attached to the Claim Record. Verification state is updated to **Pending** (◐).

---

## Phase 4: Verification Assessment

**Input**: The complete Claim Record (statement, evidence set, reasoning chain) in Pending state.

**Objective**: Evaluate whether the evidence set and reasoning chain meet VERA verification criteria. Produce a Verification Record.

This phase is executed by the **verifier** — an individual or team distinct from the Phase 1–3 claimant. For self-verification, the practitioner must adopt a genuinely adversarial stance toward the claim, actively seeking to refute it.

### Step 4.1 — Independence Check

Verify that the verifier meets the independence requirements for this claim:

| Verification level | Independence requirement |
|-------------------|--------------------------|
| **Foundational** | Verifier is different from claimant |
| **Peer** | Verifier has relevant domain competency but no stake in the claim's outcome |
| **Expert** | Verifier has recognized expertise in the claim's domain and is institutionally independent |

The independence level achieved is recorded in the Verification Record. It affects the claim's epistemic weight.

### Step 4.2 — Apply Verification Criteria

Evaluate the claim against each criterion. For each criterion, record: **Met**, **Not Met**, or **Not Applicable** with supporting notes.

**Evidence Criteria:**

| # | Criterion | Met if… |
|---|-----------|---------|
| E1 | Evidence Set Completeness | No significant evidence types from the prospective list are absent without explanation |
| E2 | Evidence Quality Adequacy | The claim's conclusion is supported by evidence at the appropriate quality tier for the stakes involved |
| E3 | Independence Adequacy | Supporting evidence is not all dependent on the same underlying source |
| E4 | Contrary Evidence Addressed | All identified contrary evidence is explicitly addressed in the reasoning chain |
| E5 | Chain of Custody | Source references are sufficient to locate the original evidence |

**Reasoning Criteria:**

| # | Criterion | Met if… |
|---|-----------|---------|
| R1 | Logical Validity | Each reasoning step's conclusion follows from its premises under the stated inference type |
| R2 | Relevance | Evidence items cited in each step actually address the component they are claimed to support |
| R3 | Completeness | No material premise is hidden or assumed without documentation |
| R4 | Proportionality | The strength of the conclusion does not exceed what the evidence supports |
| R5 | Assumption Disclosure | All significant assumptions are identified and their status assessed |

**Formal Criteria:**

| # | Criterion | Met if… |
|---|-----------|---------|
| F1 | Claim Precision | The claim statement is free of vague language that makes it untestable |
| F2 | Identifier Present | A valid VERA claim identifier is assigned |
| F3 | Scope Defined | The conditions under which the claim holds are documented |

### Step 4.3 — Assess Overall Verification State

Based on the criteria assessment:

- All criteria Met → **Verified** (●) [or Partial if some N/A items]
- Any Evidence or Reasoning criterion Not Met → **Partial** (◑) if the deficiency is minor, or document specific findings for re-submission
- Multiple significant criteria Not Met → claim returns to claimant with findings; state remains **Pending** (◐) pending revision
- Evidence or reasoning is actively contradicted → **Refuted** (✗) with full documentation

### Step 4.4 — Assign Epistemic Confidence

Assign a confidence rating (0.0–1.0) with a written justification. The confidence rating reflects:

- Quality distribution of the evidence set
- Independence of evidence items
- Strength of the reasoning chain's inference types
- Presence and significance of unresolved assumptions
- Independence level of the verification

### Step 4.5 — Complete the Verification Record

Create a Verification Record (`VERA-V-[NNNN]`) containing all findings from Steps 4.1–4.4. The record is signed (digitally or physically) by the verifier and dated. It is immutable once completed.

**Output**: A completed Verification Record. The Claim Record is updated with the resulting Verification State and confidence rating. The Verification Record is linked to the Claim Record.

---

## Phase 5: Documentation & Publication

**Input**: Verified (or otherwise resolved) Claim Record and Verification Record.

**Objective**: Ensure the claim is recorded in a durable, accessible, and auditable form.

### Step 5.1 — Format the Claim Record

Complete the Claim Record in the canonical VERA format (see [Pattern Template](./pattern-template.md) for the full template). Ensure all mandatory fields are populated and all linked documents (evidence items, verification record) are accessible via their references.

### Step 5.2 — Register the Claim

Enter the claim in the applicable claim registry — organizational, team, or personal. The registry provides:

- A searchable catalog of existing claims (prevents duplicate effort)
- A mechanism for downstream claims to reference upstream claims
- An audit trail of the claim's version history

### Step 5.3 — Notify Downstream Claims

If this claim has already been cited as evidence in other claims, notify the maintainers of those downstream claims. A change in verification state, confidence rating, or claim scope may require re-evaluation of downstream claims.

### Step 5.4 — Establish Review Cadence

Not all claims remain valid indefinitely. For time-sensitive domains, establish a review schedule:

| Domain sensitivity | Recommended review interval |
|-------------------|----------------------------|
| High (regulatory, medical, financial) | 6 months or upon material change |
| Moderate (organizational policy, technical standards) | 12–18 months |
| Low (historical, conceptual) | 36 months or upon challenge |

A claim that has not been reviewed within its cadence is flagged as **Stale** — not Refuted, but requiring attention before use in new reasoning.

**Output**: The claim is registered, formatted, linked to its verification record, and scheduled for review. The claim is now available for use as evidence in other claims.

---

## Special Situations

### AI-Assisted Claims

When a large language model or other AI system contributes substantially to claim formulation, evidence identification, or reasoning chain construction, the involvement must be documented:

- **Model and version** used
- **Prompts issued** (or a representative summary)
- **Outputs used** verbatim versus interpreted
- **Human review** performed on each AI output before incorporation

AI-assisted claims are subject to the same verification criteria as human-generated claims. AI involvement does not add to or subtract from evidence quality ratings, but the reasoning chain must document where human judgment verified AI-generated reasoning steps.

### Contested Claims

When a Verified claim is formally challenged:

1. The challenge is logged in the Verification Record, with the challenger's identity and the basis for the challenge
2. The claim transitions to **Contested** (◈) state
3. An independent verifier is assigned to re-evaluate the specific points of challenge
4. The re-evaluation produces a new Verification Record linked to the original
5. Based on re-evaluation: the claim returns to Verified, or is downgraded to Partial or Refuted

Challenges must be substantive — they must identify specific criteria that the original verification failed to assess correctly. A challenge that merely asserts disagreement without identifying a verification failure is recorded but does not trigger re-evaluation.

### Urgent Verification

In time-sensitive situations, a modified verification path is permitted:

1. The claim is marked **Pending-Urgent** (◐!) with a documented rationale for urgency
2. Verification criteria E1, R1, R2, and F1 are assessed immediately (the minimum viable set)
3. The claim is published with verification state **Partial-Urgent** (◑!) and a confidence rating calculated only from criteria assessed
4. Full verification proceeds concurrently
5. The claim is updated to its full verification state within 72 hours, or escalated to the team's governance process if this is not possible

Urgent verification must not become routine. A registry showing more than 15% of claims in Urgent status indicates a governance problem, not a verification problem.

---

*Proceed to [Pattern Template](./pattern-template.md) to learn how verified claims and reasoning are packaged into reusable patterns.*
