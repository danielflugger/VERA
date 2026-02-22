# Pattern Template

A VERA **pattern** is a reusable, documented solution to a recurring challenge in evidence management, reasoning construction, or verification practice. Patterns are not informal tips or best practices — they are structured knowledge objects that follow the canonical template defined in this chapter, and they are themselves subject to VERA verification.

This chapter defines the Pattern Template in full, explains each field, provides guidance on when and how to use existing patterns, and describes how new patterns are proposed, documented, and verified.

---

## Why Patterns

Every organization that systematically applies VERA will encounter the same recurring challenges: How do you handle evidence from a source that has a conflict of interest? How do you reason about absence of evidence? How do you construct a reasoning chain when the best available evidence is Testimonial-tier? How do you verify a claim when the domain expert and the claimant are the same person?

These challenges have been encountered before. In most cases, they have been worked through — imperfectly at first, then with increasing clarity — and the solutions are transferable. VERA patterns capture those solutions so that each team doesn't rediscover them from scratch.

Patterns also serve a normative function. When a VERA community agrees that a pattern represents the right way to handle a recurring situation, deviations from that pattern become visible and require explicit justification. This is not rigidity — it is accountability. If your context genuinely requires a different approach, document why.

---

## The Canonical Pattern Template

The following template is mandatory for all VERA patterns. Optional fields may be omitted if genuinely not applicable, but their absence must be intentional — not accidental.

---

### Field-by-Field Reference

#### Pattern Header

```
# Pattern: [Name]
```

The pattern name should be:
- Descriptive of the situation or solution, not abstractly titled
- Consistent with VERA naming conventions (Title Case, no jargon)
- Unique within the Patterns Library

Good names: "Conflicted Source Disclosure," "Absence of Evidence Assessment," "AI-Assisted Claim Documentation"
Poor names: "Pattern 7," "The Hard Case," "Evidence Thing"

---

#### Pattern ID

```
Pattern ID: VERA-P-[NNNN]
```

Assigned by the pattern registry upon submission. Format is `VERA-P-` followed by a four-digit sequential number. The ID is permanent and does not change if the pattern is revised.

---

#### Classification

```
Domain:            [Evidence | Reasoning | Verification | Governance | Sovereignty | Integration]
Applicability:     [Individual | Team | Organization | All]
Complexity:        [Simple | Moderate | Complex]
Maturity Level:    [1 | 2 | 3 | 4 | 5]
```

- **Domain**: The primary VERA domain this pattern addresses. A pattern may span domains; list the primary one.
- **Applicability**: Whether this pattern is most relevant to individual practitioners, teams, or organizational systems.
- **Complexity**: A rough guide to implementation effort. Simple = < 30 minutes to implement correctly. Moderate = requires planning. Complex = requires architectural decisions or significant tooling.
- **Maturity Level**: The minimum VERA maturity level at which this pattern is typically applied. A Level 2 pattern can be applied by a Level 2 or higher practitioner; it is unlikely to be useful at Level 1.

---

#### Context

```
## Context

[2–4 paragraphs describing the situation in which this pattern applies. Include:
- The type of claim or reasoning scenario
- The organizational or individual circumstances
- What makes this situation distinctive enough to warrant a documented pattern
- Any prerequisites (tools, practices, or prior VERA maturity) needed]
```

The context section is not a problem statement — it is a situation description. It answers: *When does someone find themselves needing this pattern?*

---

#### Problem

```
## Problem

[1–2 paragraphs stating the specific challenge the pattern addresses.
Use precise VERA language. Reference Lexicon terms by name.
State the problem as it actually appears — the symptom the practitioner notices —
not as the underlying theoretical issue.]
```

Example of a well-stated problem: "When a claim's most relevant evidence comes from a single source that also has a financial interest in the claim's truth, the verification criterion E3 (Independence Adequacy) cannot be met in the conventional sense. Verifiers are uncertain whether to return the claim as unverifiable or to proceed with an acknowledged limitation."

Example of a poorly stated problem: "Evidence quality is hard to assess when sources are biased."

---

#### Forces

```
## Forces

- [Force 1: a competing concern or constraint that the solution must navigate]
- [Force 2: ...]
- [Force 3: ...]
- [Force 4 (optional): ...]
```

Forces are the tensions that make this a genuine problem rather than a simple question with an obvious answer. They explain why the pattern is needed — if there were no competing concerns, the right answer would be obvious.

Example forces for the conflicted source problem:
- The evidence from the conflicted source may be the only available evidence of this type
- Discarding it entirely loses real information
- Using it without disclosure violates Evidence Primacy
- Flagging it too prominently may make the claim appear weaker than warranted

---

#### Solution

```
## Solution

[3–6 paragraphs describing the solution. The solution must be specific enough
to implement without judgment calls that are not themselves documented.
It should address each Force listed above, explaining how the solution
navigates the tension.]
```

The solution section is the pattern's core. It should read as clear, implementable guidance — not general advice. If the solution requires making a judgment call, it must specify what the judgment criteria are.

---

#### Implementation Steps

```
## Implementation

1. [Step 1 — specific action with clear completion criterion]
2. [Step 2]
3. [...]
```

Implementation steps are numbered and sequential. Each step has a completion criterion — something observable that tells you the step is done. Steps should be atomic enough that they can be delegated and checked.

---

#### Evidence Requirements

```
## Evidence Requirements

[What evidence must be assembled before or during application of this pattern.
Specify quality tier minimums where applicable.
Note any evidence types that are specifically required or specifically prohibited.]
```

This section distinguishes VERA patterns from general methodology: every pattern specifies what evidence standards it requires.

---

#### Verification Criteria

```
## Verification Criteria

[How to verify that the pattern has been correctly applied.
List observable outcomes — not activities. "The verifier reviewed the claim"
is an activity. "The Verification Record contains a documented independence
assessment for each evidence item" is an observable outcome.]
```

---

#### Consequences

```
## Consequences

**Benefits:**
- [Benefit 1]
- [Benefit 2]

**Liabilities:**
- [Liability 1]
- [Liability 2]
```

Patterns have costs as well as benefits. Documenting liabilities is not a weakness — it is what distinguishes an honest pattern from marketing. A pattern with no liabilities is either trivial or poorly analyzed.

---

#### Known Uses

```
## Known Uses

- [Organization/context 1]: [Brief description of how pattern was applied and what was learned]
- [Organization/context 2]: [...]
```

Known uses are the empirical foundation of a pattern. A pattern documented without any known uses is a proposal, not a pattern. During review, the absence of known uses is noted; upon accumulation of two or more documented uses, the pattern is upgraded to Verified status.

---

#### Related Patterns

```
## Related Patterns

- [VERA-P-NNNN — Pattern Name]: [How this pattern relates]
- [...]
```

---

#### Verification Status

```
## Verification Status

State:        [Proposed | Under Review | Verified | Deprecated]
Verifier:     [Name / Team]
Verified on:  [Date]
Record:       [VERA-V-NNNN]
Confidence:   [0.0–1.0]
```

Patterns, like claims, carry verification status. A **Proposed** pattern has been submitted but not reviewed. **Under Review** means active evaluation is in progress. **Verified** means the pattern has met VERA verification criteria and has at least two documented Known Uses. **Deprecated** means the pattern has been superseded or found to be ineffective.

---

## Complete Template (Copy-Ready)

```markdown
# Pattern: [Name]

**Pattern ID:** VERA-P-[NNNN]

| Field | Value |
|-------|-------|
| Domain | [Evidence / Reasoning / Verification / Governance / Sovereignty / Integration] |
| Applicability | [Individual / Team / Organization / All] |
| Complexity | [Simple / Moderate / Complex] |
| Maturity Level | [1–5] |

---

## Context

[Describe the situation in which this pattern applies.]

## Problem

[State the specific challenge.]

## Forces

- [Force 1]
- [Force 2]
- [Force 3]

## Solution

[Describe the solution in detail.]

## Implementation

1. [Step 1]
2. [Step 2]
3. [Step 3]

## Evidence Requirements

[Specify evidence standards required.]

## Verification Criteria

[List observable outcomes that confirm correct application.]

## Consequences

**Benefits:**
- [Benefit 1]

**Liabilities:**
- [Liability 1]

## Known Uses

- [Context 1]: [Description]

## Related Patterns

- [VERA-P-NNNN — Name]: [Relationship]

---

## Verification Status

| Field | Value |
|-------|-------|
| State | [Proposed / Under Review / Verified / Deprecated] |
| Verifier | [Name] |
| Verified on | [Date] |
| Record | [VERA-V-NNNN] |
| Confidence | [0.0–1.0] |
```

---

## A Worked Example: The Absence-of-Evidence Pattern

To illustrate the template in use, the following is a partial example of a real VERA pattern.

---

### Pattern: Absence-of-Evidence Assessment

**Pattern ID:** VERA-P-0001

| Field | Value |
|-------|-------|
| Domain | Evidence |
| Applicability | All |
| Complexity | Moderate |
| Maturity Level | 2 |

---

#### Context

In the course of assembling an evidence set (Verification Protocol Phase 2), practitioners regularly encounter a situation where evidence of an expected type is absent. This might mean the expected evidence genuinely does not exist, that it exists but was not found, or that it was found and selectively omitted.

The VERA requirement to document absent evidence (Step 2.5) creates a documentation obligation but does not specify how to reason about the significance of that absence. This pattern addresses the analytical work required at Step 2.5.

#### Problem

The practitioner has completed an evidence search and finds that a category of evidence listed in the prospective search plan (Step 2.1) yielded no results. The claim's verification status depends partly on how materially the absent evidence weakens the claim — but there is no standard method for assessing materiality.

Without guidance, practitioners tend toward one of two errors: dismissing the absence as unimportant (understating the evidential gap) or treating any absence as fatal to the claim (overstating it). Neither produces calibrated epistemic confidence.

#### Forces

- The absence of evidence genuinely varies in significance: absent safety records for a medical device are more significant than absent sales records for the same period.
- The claim's scope may be adjustable to exclude the area the absent evidence would have addressed.
- Documenting absent evidence as "neutral" when it is actually significant constitutes a form of selective citation.
- Marking every absence as "significantly weakening" would make most claims unverifiable.

#### Solution

Assess the significance of each absent evidence item on three dimensions:

**1. Expected vs. unexpected.** Evidence that should exist given the claim's scope, and whose absence is therefore unexplained, is more significant than evidence that might exist but whose absence is explicable.

**2. Substitutability.** Can the absent evidence be replaced by a different evidence type that addresses the same claim component? If yes, the absence is less significant — provided the substitute is assembled. If no, the absence leaves a genuine gap.

**3. Directionality.** If the absent evidence existed, would it more likely support or contradict the claim? When the absent evidence would likely support the claim and it is still absent, the gap is moderate. When the absent evidence would likely contradict the claim (the "file drawer problem") and is absent, the gap is serious — and warrants explicit notation.

For each absent evidence item, apply this assessment and assign one of three materiality ratings:

- **Non-material**: Absence is explainable and substitutable; confidence impact < 0.05
- **Moderate**: Absence represents a genuine gap; note in reasoning chain; confidence impact 0.05–0.15
- **Significant**: Absence leaves a material claim component unsupported; must be acknowledged in the claim statement or the claim scope must be revised

#### Implementation

1. List every evidence type on the prospective plan that was not found.
2. For each, answer the three assessment questions (Expected? Substitutable? Directionality?).
3. Assign a materiality rating (Non-material / Moderate / Significant).
4. For Moderate absences: document in the reasoning chain as an acknowledged limitation.
5. For Significant absences: either (a) revise the claim's scope to exclude the unsupported component, or (b) downgrade the confidence rating by at least 0.15 and document the absence prominently in the claim record.
6. Record the complete absence assessment in the Evidence Set documentation.

#### Verification Criteria

- The Verification Record confirms that the verifier reviewed the evidence search plan, not only the evidence collected.
- Each absent evidence item from the prospective plan appears in the Claim Record with an assigned materiality rating.
- No evidence type rated Significant is absent from the claim record's limitations section.
- The confidence rating reflects adjustments for Moderate and Significant absences.

#### Consequences

**Benefits:**
- Prevents selective citation by making the absence assessment explicit and auditable.
- Provides a calibrated method for adjusting confidence that avoids both dismissal and over-reaction.
- Creates a clear record for downstream verifiers and claim users.

**Liabilities:**
- Adds analytical time to Phase 2.
- Directionality assessment (step 3) requires domain judgment; practitioners without domain expertise may need consultation.

#### Known Uses

- **Internal policy team, financial services firm (2024)**: Applied this pattern to regulatory impact assessments; identified two Significant absences that led to scope revisions, preventing two subsequent claims from being challenged during regulatory review.
- **Research team, academic institution (2025)**: Used during systematic review to distinguish non-publication bias (absent studies likely neutral) from selective non-reporting (absent data likely directional).

---

## How to Propose a New Pattern

Patterns emerge from practice. If you encounter a recurring challenge that is not addressed by an existing pattern:

1. **Document the first occurrence** using the evidence and reasoning of the situation itself — the claim record for the challenging situation becomes data for the eventual pattern.
2. **Look for recurrence**: before proposing a pattern, verify that you've encountered the same challenge at least twice in distinct contexts.
3. **Draft the pattern** using the full template. Mark it as **Proposed** with no verifier.
4. **Submit to the Patterns Library** with your draft. The submission triggers a review process in which at least two experienced VERA practitioners evaluate the pattern against the template requirements.
5. **Accumulate Known Uses**: as the proposed pattern is applied (with appropriate documentation) in real situations, those uses are added to the Known Uses section.
6. **Verification**: once the pattern has two documented Known Uses and passes template review, it is moved to **Verified** status.

Patterns are living documents. A Verified pattern that proves ineffective in practice is flagged, documented, and eventually **Deprecated** — with documentation of why it failed, which is itself valuable knowledge.

---

*Proceed to [Sovereignty Principles](./sovereignty-principles.md) to understand the commitments that constrain how VERA is implemented and governed.*
