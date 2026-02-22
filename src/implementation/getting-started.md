# Getting Started

This chapter is for practitioners who have read the Foundations section and are ready to apply VERA to a real claim for the first time. It walks through the complete Verification Protocol on a concrete example, explains what to expect at each step, and describes what to do after the first claim is complete.

Read the [Lexicon](../foundations/lexicon.md) and [Verification Protocol](../foundations/verification-protocol.md) before proceeding. You do not need to have memorized them — but you need to have read them once, so that the terminology in this chapter is familiar.

---

## Before You Begin

### What You Need

VERA requires no specialized software. To complete your first claim, you need:

- A place to write that is searchable and persistent (a text editor, a document, a notes application)
- Access to the evidence you expect to use
- Two to four hours for the first claim (subsequent claims take less time as the format becomes familiar)
- If possible: one other person willing to serve as your verifier — someone who can read your claim record and evaluate it with some distance from the argument

If no independent verifier is available, you will use [VERA-P-0010 (Self-Verification with Adversarial Stance)](../patterns/verification.md#vera-p-0010). That is acceptable for a first claim.

### Choosing Your First Claim

Do not choose a trivial claim. The investment required by VERA is only justified by claims with real epistemic stakes — claims that actually inform decisions, guide actions, or appear in communications that matter.

Do not choose the most complex claim you face. A compound, multi-domain claim with conflicting evidence is not the right starting point. The learning happens fastest on a claim that is significant but tractable.

**Criteria for a good first claim:**
- It is a single assertion (not multiple assertions bundled together)
- It is something you believe to be true but have not formally documented
- Evidence for it exists and is retrievable in a few hours
- The claim matters — it informs a real decision, supports a real position, or will appear in real communications
- You have some genuine uncertainty about it — you are not starting from certainty

**Common good first claims:**
- A claim about the effectiveness of a process, tool, or intervention your team uses
- A claim about conditions in a market, domain, or environment you work in
- A claim that you regularly make in presentations or documents that you have never formally documented

**Claims to avoid for your first attempt:**
- Historical claims about events that cannot be re-investigated
- Normative claims ("X is the right approach") — these require special handling for value assumptions
- Claims where you are personally very invested in a specific conclusion — verification bias will be hardest to manage

### Setting Expectations

Your first VERA claim will take longer than you expect and reveal more problems than you expect. This is not a failure — it is the framework doing what it is supposed to do. Every gap you find in your evidence, every assumption you excavate, every piece of contrary evidence you have to address represents an epistemic problem that existed before VERA made it visible.

The goal of the first claim is not to produce a perfect VERA artifact. The goal is to complete the process — all five phases, all the way through to a Verification Record — so that you understand what the framework requires in practice rather than in theory.

---

## A Worked Walkthrough

The following example traces a complete first claim through all five phases. The claim is fictional but realistic. Use it as a reference as you work through your own claim alongside it.

**The assertion to be documented:** *"Adopting automated code review reduced our team's production defect rate by 35% in the six months following implementation."*

---

### Phase 1: Claim Formulation

**Step 1.1 — State the assertion precisely**

Read the assertion carefully. Is it one claim or several?

This assertion contains:
- A causal claim (adoption *caused* a reduction)
- A quantitative claim (35% reduction)
- A scope claim (our team, production defects only)
- A temporal claim (six months following implementation)

That is four claim components. Test each against the Step 1.2 decomposition tests: Can each component be true while the others are false? Yes — the defect rate could have dropped 35% for reasons other than the code review adoption; the causal claim could be false while the quantitative claim is true.

**Decomposition decision:** The quantitative scope-and-time claim ("defect rate dropped 35% in six months") can be documented and verified as one claim. The causal claim ("adoption caused the reduction") is a separate claim that depends on the first being true plus additional evidence. For a first claim, address the quantitative component and treat causation as a stated assumption with documented uncertainty.

**Revised claim statement:** *"Our team's production defect rate, as measured in our incident tracking system, was 35% lower in the six-month period following automated code review adoption than in the equivalent six-month period preceding it."*

This is more precise, testable, and modest. It does not assert causation.

**Step 1.3 — Assign a claim identifier**

If you are an individual practitioner: `VERA-C-DJF-2026-0001` (initials + year + sequential number).

If you are part of a team with a registry: use your organization's format and register the claim.

**Step 1.4 — Record claim context**

Document:
- **Claimant:** [Your name / team name]
- **Date initiated:** [Today's date]
- **Purpose:** Supporting the case for continued investment in automated code review tooling
- **Scope:** Production defects only; excludes test-environment defects; our team (not the wider engineering organization)
- **Prior art:** No prior VERA claims on this topic in the registry

**Phase 1 output:** A claim stub with ID, precise statement, and context metadata. Verification state: **Unverified** (○).

---

### Phase 2: Evidence Assembly

**Step 2.1 — Write the prospective search plan**

Before retrieving a single piece of evidence, write down what evidence you expect to exist and where you expect to find it.

For this claim:
- *Defect rate data before adoption:* incident tracking system, six months preceding the adoption date
- *Defect rate data after adoption:* incident tracking system, six months following the adoption date
- *Adoption date documentation:* project management system or release notes confirming when automated code review was activated
- *Defect count methodology:* how are "production defects" defined in the tracking system? Is the definition stable across both periods?
- *Potential confounds (evidence of other changes):* were there other significant process, team composition, or codebase changes in the same period that might have affected defect rates?

Write this list before you open the incident tracking system.

**Step 2.2 — Retrieve and document evidence**

Retrieve each item on the list. For items not found, note that they are not found.

In this example:
- E1: Defect data export, pre-adoption period. Incident tracking system, exported [date]. **Primary** tier.
- E2: Defect data export, post-adoption period. Incident tracking system, exported [date]. **Primary** tier.
- E3: Deployment log confirming adoption date. Release management system, accessed [date]. **Primary** tier.
- E4: Defect classification documentation. Engineering wiki, version history checked. **Secondary** tier (editorial documentation of Primary methodology).
- E5: No documentation found of other significant process changes in the period. Prospective plan item: not found. → Proceed to Step 2.5.

**Step 2.3 — Rate evidence quality**

All data exports from your own systems are Primary tier — they are direct measurements without interpretation intermediary. The methodology documentation is Secondary. Rate each item.

**Step 2.4 — Assess evidence independence**

E1 and E2 both come from the same incident tracking system. They are not independent in origin — they share a system — but they measure different time periods and are not derived from each other. Classify as **Correlated** (same system, different measurements). Note this in the evidence set.

**Step 2.5 — Document absent evidence**

The prospective plan included "evidence of other changes" and none was found. Apply VERA-P-0001 (Absence-of-Evidence Assessment):
- **Expected?** Yes — it would be normal for other process changes to exist and be documented.
- **Substitutable?** Partially — you can ask team members, but that is Testimonial tier.
- **Directionality?** If other improvement initiatives existed, their absence from documentation is ambiguous (they may exist but be undocumented, or may not exist). Rate as **Moderate** materiality. Document in the claim: "No documentation of concurrent process changes was found. The causal interpretation of the defect rate drop therefore rests on an assumption of minimal concurrent change, which is noted as an unverified assumption."

**Phase 2 output:** Evidence set with five items (four found, one not found with documented absence). Verification state remains **Unverified** (○).

---

### Phase 3: Reasoning Construction

**Step 3.1 — Map evidence to claim components**

The claim asserts: defect rate was 35% lower in period B than period A.
- E1 (pre-adoption data) supports: the baseline defect count
- E2 (post-adoption data) supports: the post-adoption defect count
- E3 (adoption date) supports: the period boundary
- E4 (methodology documentation) supports: that "production defect" means the same thing in both periods

**Step 3.2 — Identify the logical structure**

The inference type is **inductive**: we generalize from two specific six-month measurements to a claim about the effect of the intervention. This is the appropriate type for comparative measurement claims.

**Step 3.3 — Write the reasoning chain**

```
Step 1:
  Premises:     E1 (pre-adoption defect data), E4 (methodology documentation)
  Inference:    Deductive
  Reasoning:    The incident tracking system recorded N1 production defects
                in the six months before the adoption date (per E3). The
                definition of "production defect" was stable across both
                periods (per E4). Therefore, N1 represents the pre-adoption
                production defect count under a consistent methodology.
  Conclusion:   Pre-adoption production defect count = N1.
  Confidence:   0.91

Step 2:
  Premises:     E2 (post-adoption defect data), E4 (methodology documentation)
  Inference:    Deductive
  Reasoning:    The same system recorded N2 production defects in the six
                months following the adoption date. Methodology consistent
                per E4.
  Conclusion:   Post-adoption production defect count = N2.
  Confidence:   0.91

Step 3:
  Premises:     Step 1 conclusion (N1), Step 2 conclusion (N2)
  Inference:    Deductive
  Reasoning:    Percentage reduction = (N1 - N2) / N1 × 100.
                [Insert calculated value.]
  Conclusion:   Production defect rate decreased by [X]% from period A to
                period B.
  Confidence:   0.91 (inherits from premises; arithmetic is certain)

Step 4:
  Premises:     Step 3 conclusion
  Inference:    Inductive
  Reasoning:    The measured decrease of [X]% is the basis for the claim
                that the defect rate was approximately 35% lower in period B.
                The claim uses 35% as the rounded reported value; the precise
                calculated value is documented in Step 3.
  Conclusion:   Production defect rate was approximately 35% lower in the
                six-month post-adoption period than in the equivalent
                pre-adoption period.
  Confidence:   0.88 (small reduction for rounding and measurement uncertainty)
```

**Step 3.4 — Identify and document assumptions**

Using VERA-P-0007 (Hidden Assumption Excavation):

Apply Question 1 (Necessary Conditions) to Step 3:
- *The incident tracking system was used consistently across both periods* — a Background assumption; document briefly.
- *Production defects are the relevant metric for the claim's purpose* — a Domain assumption; note that this assumes defects not captured in the tracking system are not material.

Apply Question 1 to Step 4:
- *No other significant changes occurred concurrently that explain the drop* — a **Contested** assumption. This is the causal gap identified in Phase 2. Document prominently.

Apply Question 2 (Variance) across all steps:
- Team composition, codebase complexity, and deployment frequency could all vary across periods and affect defect rates. These are noted as uncontrolled variables.

All assumptions are documented in the reasoning chain as an "Assumptions" section following the steps.

**Step 3.5 — Address contrary evidence**

The absent evidence (no documentation of concurrent changes) was assessed at Moderate materiality in Phase 2. In the reasoning chain, this is addressed with a Qualify response: the claim does not assert causation; the absence of documented concurrent changes is noted but not treated as conclusive evidence of their absence.

**Phase 3 output:** Complete reasoning chain with four steps, documented assumptions, and contrary evidence addressed. Verification state updated to **Pending** (◐).

---

### Phase 4: Verification Assessment

If an independent verifier is available, share the claim record and ask them to work through the Phase 4 criteria (Verification Protocol, Steps 4.1–4.5). Provide them the criteria table from the Protocol — do not summarize it for them.

If you are self-verifying, apply VERA-P-0010 (Self-Verification with Adversarial Stance):
1. Write the Role Declaration. Date it.
2. Wait 24 hours.
3. Work through Phase 4 criteria and the adversarial checklist (A1–A7).

**Working through the criteria for this example:**

- E1 (Completeness): The prospective search plan listed five evidence types; four were found; one absence was documented with materiality assessment. ✓ Met.
- E2 (Quality Adequacy): Two Primary-tier data exports and one Primary methodology anchor. For a measurement claim, Primary evidence is appropriate. ✓ Met.
- E3 (Independence): E1 and E2 are Correlated (same system, different periods). Independence limitation is documented. ✓ Met with notation.
- E4 (Contrary Evidence): The concurrent-change assumption is Contested and addressed with a Qualify response in the reasoning chain. ✓ Met.
- E5 (Chain of Custody): All evidence items include source, access date, and export method. ✓ Met.
- R1 (Validity): Steps 1–3 are deductive calculations; Step 4 is appropriately inductive. ✓ Met.
- R2 (Relevance): All evidence items address the claim components they are cited for. ✓ Met.
- R3 (Completeness): Assumptions documented including the Contested concurrent-change assumption. ✓ Met.
- R4 (Proportionality): The claim is scoped to measurement only, not causation. Modest and appropriate. ✓ Met.
- R5 (Assumption Disclosure): All assumptions documented, Contested assumption flagged. ✓ Met.
- F1 (Precision): Claim statement is precise: specific metric, specific system, specific time period. ✓ Met.
- F2 (Identifier): Claim ID assigned. ✓ Met.
- F3 (Scope Defined): Production defects only; this team; six-month comparison periods. ✓ Met.

All criteria met. Assign verification state: **Verified** (●).

**Confidence rating:** Evidence is Primary-tier, reasoning is sound, assumption documentation is complete. Independence limitation noted. Confidence: **0.79** (strong evidence but Correlated independence and a load-bearing Contested assumption reduce ceiling; self-verification cap of 0.72 applies if self-verified).

**Phase 4 output:** Verification Record `VERA-V-[NNNN]` with all criteria findings and confidence rating.

---

### Phase 5: Documentation and Publication

Register the claim in whatever serves as your claim registry (a table in a shared document is fine for a first claim). The entry should be findable by anyone who wants to know whether this topic has been investigated.

Set a review cadence. This claim uses Primary-tier data from internal systems. Evidence decay class: Drifting (metrics may shift as team or codebase changes). Review in 12 months.

**Phase 5 output:** The claim is registered, linked to its Verification Record, and scheduled for review.

---

## After the First Claim

### What You Have Learned

By completing a first claim, you have learned things that cannot be learned by reading:
- How long each phase actually takes in your context
- Where your existing work process produces evidence and where it does not
- Which assumptions in your ordinary reasoning are load-bearing and undocumented
- What "explicit reasoning chain" means when you have to write one out rather than imagine one

### What to Do Next

**In the next week:** Identify two or three more claims that matter in your current work. Do not document them yet. Just identify them and note which ones would be good candidates.

**In the next month:** Document one more claim — this time, a claim where the evidence situation is more complex (missing evidence, a conflicted source, or a genuine contrary evidence challenge). The second claim is where the patterns in the Patterns Library become essential.

**When you have five claims documented:** Conduct your first maturity assessment. Read the [Maturity Model Overview](../maturity-model/overview.md) and the [Level 2 chapter](../maturity-model/level-2.md). Assess yourself honestly against the checklist.

**The instinct to suppress:** At some point in your first few claims, you will encounter evidence that is weak, an assumption that is contested, or a contrary evidence item that resists clean resolution. The instinct is to quietly omit these problems from the claim record and proceed. Resist it. The value of VERA is precisely that it makes these problems visible. An imperfect, honest claim record is far more valuable than a clean, dishonest one.

---

## Common Early Mistakes

**Starting with the evidence, not the search plan.** Practitioners who skip the prospective search plan reliably miss absent evidence and unconsciously practice selective citation. The plan takes ten minutes. Do not skip it.

**Writing conclusions instead of reasoning chains.** A reasoning chain that reads "Given the evidence above, we conclude that X" is not a reasoning chain — it is a conclusion with evidence attached. Each step must state its premises, its inference type, and its intermediate conclusion explicitly.

**Treating Phase 4 as a formality.** The most common Level 2 failure is treating verification as a step that confirms rather than evaluates. If you complete Phase 4 and find no problems, you are either verifying an exceptionally clean claim or not looking hard enough. Expect to find something.

**Over-scoping the first claim.** A claim that asserts too much requires a proportionally large evidence set and complex reasoning chain. Narrow the claim to something you can complete in two to four hours. You can always build on it later.

**Under-documenting assumptions.** Practitioners document the assumptions they consciously make. They miss the assumptions they make without noticing. Apply VERA-P-0007 systematically to every reasoning step — it will find things a conscious scan will not.

---

## Minimum Viable VERA

For practitioners under significant time constraints, the following is the minimum set of documentation that constitutes genuine VERA practice (rather than VERA-shaped compliance):

1. **Claim statement:** One precise declarative sentence with explicit scope.
2. **Claim ID:** Assigned and logged.
3. **Prospective search plan:** Written before evidence retrieval begins. Even a bulleted list of three to five expected evidence types counts.
4. **Evidence set:** Source, access date, quality tier rating, and relevance statement for each item. Absent evidence noted.
5. **Reasoning chain:** At minimum, two to three explicit steps connecting evidence to conclusion. Labeled inference type. One documented assumption.
6. **Verification record:** Per-criterion findings (even brief), confidence rating with justification, independence level.

This minimum set is not as good as the full Protocol. But it is genuinely VERA, and it is dramatically better than no documentation. As practice develops, the minimum set expands toward the full Protocol naturally — not because of external pressure, but because practitioners discover what the missing elements reveal.

---

*Proceed to [Adoption Roadmap](./adoption-roadmap.md) for a sequenced plan for building VERA practice beyond the first claim.*
