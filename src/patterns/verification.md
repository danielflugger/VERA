# Verification Patterns

Verification Patterns address recurring challenges in the verification process itself: executing rigorous verification when ideal conditions don't hold, engaging domain experts who lack VERA training, managing the propagation of state changes through a claim registry, and calibrating confidence ratings across a team of verifiers.

All patterns follow the canonical [Pattern Template](../foundations/pattern-template.md). Verification states, independence levels, and verification criteria are defined in the [Lexicon](../foundations/lexicon.md) and the [Verification Protocol](../foundations/verification-protocol.md).

---

<a id="vera-p-0010"></a>
## VERA-P-0010 — Self-Verification with Adversarial Stance

**Pattern ID:** VERA-P-0010

| Field | Value |
|-------|-------|
| Domain | Verification |
| Applicability | All |
| Complexity | Moderate |
| Maturity Level | 2 |

---

### Context

The Verification Protocol specifies three independence levels for verifiers: Foundational (different person from the claimant), Peer (relevant domain competency, no stake in outcome), and Expert (recognized expertise, institutionally independent). Independent verification is always preferable. In practice — particularly at Maturity Levels 2 and early 3 — independent verifiers are frequently unavailable: the domain is too specialized, the team is too small, the timeline is too compressed, or the claim involves confidential information that limits who can review it.

When independent verification is unavailable, the Protocol permits self-verification. It does not specify *how* to conduct self-verification in a way that produces genuinely rigorous results rather than rationalizing the claim's conclusion.

---

### Problem

Self-verification has an inherent optimism bias. Research on human cognition consistently shows that people evaluating their own work apply less scrutiny than they apply to others'. This bias operates even when practitioners are genuinely trying to be adversarial. The problem is not intent — it is that the claimant and the verifier share the same reasoning history, the same implicit assumptions, and the same emotional investment in the claim. They cannot fully simulate the perspective of someone who comes to the claim without that history.

A self-verification that mimics the appearance of rigor without its substance — producing a Verification Record without genuine adversarial evaluation — is worse than no verification, because it creates a false confidence signal.

---

### Forces

- Independent verification is not always achievable, and blocking claims until it is available may be disproportionate for low-stakes claims.
- Self-verification that is honest about its limitations is more valuable than no verification, provided the limitations are documented.
- The optimism bias in self-verification is real but not uniform; structured adversarial protocols reduce but do not eliminate it.
- Self-verification at Foundational independence produces a lower confidence ceiling than peer or expert verification; this must be reflected in the confidence rating.
- The temptation to treat self-verification as equivalent to independent verification — to omit the independence level from the Verification Record — is significant and must be structurally prevented.

---

### Solution

Apply a **five-element self-verification protocol** that structurally mimics independence through role separation, time gap, and an adversarial checklist calibrated to catch the errors most likely to be missed by the claimant.

**Element 1 — Role Declaration**
Before beginning self-verification, write a brief Role Declaration: "I am now acting as a verifier, not as the claimant. My goal is to find reasons why this claim's verification should fail, not reasons why it should pass." This is not ceremonial — it is a documented commitment that creates accountability for the verification role.

**Element 2 — Mandatory Time Gap**
A minimum of 24 hours must elapse between completing Phase 3 (Reasoning Construction) and beginning Phase 4 (Verification Assessment) for self-verification. The gap allows working memory of the reasoning process to fade, reducing the tendency to evaluate the chain as familiar rather than as new. For high-stakes claims: 48 hours minimum.

**Element 3 — Adversarial Checklist**
Apply the standard Phase 4 verification criteria AND the following adversarial checklist — items specifically calibrated to catch errors that claimants systematically miss in self-review:

| # | Adversarial check |
|---|------------------|
| A1 | Read the claim statement aloud. Does it assert exactly what the evidence supports — not more, not less? |
| A2 | For each evidence item rated Primary or Secondary: Have you actually read the original source, or are you recalling your notes about it? |
| A3 | For each reasoning step: If a skeptic handed you this step and asked you to argue against it, what would you say? Document that argument and assess it. |
| A4 | Is there contrary evidence in the set that you have not addressed in the reasoning chain? (Re-scan the evidence set independently of the reasoning chain.) |
| A5 | Which assumption in your reasoning chain would you least want an adversary to notice? Have you documented it? |
| A6 | What is the weakest link in this chain? Have you applied more scrutiny to it, or less, than to the stronger links? |
| A7 | If this claim turns out to be wrong, what would the most likely cause be? Is that cause addressed anywhere in the documentation? |

**Element 4 — Confidence Ceiling**
Self-verification produces a Foundational independence level, which caps the achievable confidence rating at **0.72**. No self-verified claim may be assigned a confidence rating above 0.72, regardless of how strong the evidence appears to the claimant-verifier. This ceiling is documented in the Verification Record.

**Element 5 — Independence Documentation**
The Verification Record for a self-verified claim must clearly state: "Verification conducted by claimant. Independence level: Foundational. Confidence ceiling applied: 0.72. Independent verification recommended for claims above [stakes threshold]."

---

### Implementation

1. **Complete the claim through Phase 3.** The full reasoning chain must be written before self-verification begins.

2. **Write the Role Declaration.** Date and sign it. File it with the Verification Record.

3. **Observe the time gap.** Do not begin Phase 4 work until the minimum gap has elapsed. For claims assembled under time pressure, document the reason if the gap cannot be met and flag the Verification Record accordingly.

4. **Apply Phase 4 criteria.** Work through all criteria in Phase 4, Step 4.2. Document findings for each criterion.

5. **Apply the adversarial checklist.** Work through A1–A7 in sequence. For each item, document: what you found, what argument you constructed against the claim, and how you assessed it. The checklist is not complete until all seven items are documented.

6. **Assign verification state.** Apply the same criteria as standard verification. The state is determined by criteria findings, not by the confidence ceiling.

7. **Assign confidence rating.** Apply the Foundational confidence ceiling (0.72). The confidence is capped at this value regardless of the evidence quality assessment.

8. **Complete the Verification Record.** Include all standard fields plus: independence level, confidence ceiling, Role Declaration reference, and a recommendation for independent verification if the claim will be used for high-stakes decisions.

---

### Evidence Requirements

- The Role Declaration (dated, signed or attributed)
- Completed adversarial checklist with documented responses to each item
- Documentation of the time gap between Phase 3 completion and Phase 4 commencement

---

### Verification Criteria

- The Verification Record explicitly states self-verification and Foundational independence level
- The adversarial checklist is complete with documented responses to all seven items
- The confidence rating does not exceed 0.72
- The Verification Record recommends independent verification for high-stakes applications

---

### Consequences

**Benefits:**
- Provides a rigorous self-verification process that is meaningfully better than informal self-review.
- The confidence ceiling and independence documentation ensure that self-verification is never mistaken for independent verification.
- The adversarial checklist surfaces the specific failure modes most likely in self-review.

**Liabilities:**
- The time gap requirement may conflict with fast-moving work contexts.
- The confidence ceiling (0.72) means that some high-quality self-verified claims carry lower formal confidence than their evidence warrants.
- The adversarial stance requires sustained effort to maintain; practitioners under time or social pressure tend to revert to advocacy mode.

---

### Known Uses

- **Solo researcher, independent think tank (2024):** Applied as a standard practice for all claims, accepting the 0.72 ceiling as a documentation of epistemic position and flagging high-stakes claims for eventual peer review. The adversarial checklist in item A5 ("assumption you least want an adversary to notice") surfaced a load-bearing assumption on three separate occasions that was not otherwise documented.
- **Small team, early-stage technology company (2025):** Implemented as team policy after an important product claim was challenged during due diligence; the challenge identified a reasoning gap that the team's informal self-review had missed. The time gap requirement was implemented as a 48-hour calendar block.

---

### Related Patterns

- [VERA-P-0011](./verification.md#vera-p-0011) — Expert Verifier Onboarding: Use when an expert is available to conduct independent verification; P-0010 is the fallback when P-0011 is not feasible.
- [VERA-P-0013](./verification.md#vera-p-0013) — Claim Confidence Calibration: In organizations with multiple practitioners conducting self-verification, calibration is needed to ensure the 0.72 ceiling is applied consistently.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0010 |
| Confidence | 0.86 |

---

<a id="vera-p-0011"></a>
## VERA-P-0011 — Expert Verifier Onboarding

**Pattern ID:** VERA-P-0011

| Field | Value |
|-------|-------|
| Domain | Verification |
| Applicability | All |
| Complexity | Complex |
| Maturity Level | 3 |

---

### Context

VERA verification requires two distinct competencies: domain knowledge (understanding what the claim asserts and whether the evidence and reasoning are sound within the domain) and VERA process knowledge (understanding what the verification criteria require and how to apply them). The ideal verifier has both. In practice, these competencies are rarely found together in the same person.

Domain experts who have not been trained in VERA can assess whether a claim is factually sound in their domain. They cannot reliably apply the VERA criteria (E1–E5, R1–R5, F1–F3) as stated, because those criteria use VERA-specific vocabulary and concepts that require background knowledge to apply correctly. Conversely, VERA-trained practitioners may lack the domain knowledge needed to evaluate whether the evidence truly supports the claim.

---

### Problem

Engaging an expert as a VERA verifier without preparing them produces one of two outcomes: the expert reviews the claim for substantive accuracy (valuable but not VERA verification) or the expert attempts to apply VERA criteria without understanding them (producing a Verification Record that has the right format but reflects domain review rather than VERA verification). Both outcomes are misleading if the Verification Record represents the event as VERA verification.

---

### Forces

- Expert time is expensive; consuming it with process overhead that could have been prepared in advance is wasteful.
- Brief VERA training for domain experts risks producing over-confident mis-application of incompletely understood criteria.
- The practitioner who produced the claim has the most VERA knowledge but the least independence; the expert has independence but not VERA knowledge.
- Splitting verification responsibilities (expert assesses domain substance; practitioner assesses formal VERA criteria) introduces coordination complexity and may miss the interaction between domain substance and formal criteria.
- The expert's domain authority is valuable precisely because it is independent; involving them too heavily in the documentation process may compromise that independence.

---

### Solution

Apply a **structured briefing and joint record protocol** in which the VERA practitioner performs three roles: (1) translating VERA criteria into domain-specific language the expert can apply, (2) managing the verification process and documentation, and (3) ensuring the expert's domain judgment is accurately captured in the Verification Record.

The expert performs one role: providing independent domain judgment on the substance of the claim.

**Phase A: Criteria Translation**

Before the expert engagement, the practitioner prepares a **Criteria Translation Worksheet**: for each of the thirteen verification criteria (E1–E5, R1–R5, F1–F3), the practitioner writes a domain-specific version of the criterion that the expert can apply without VERA vocabulary. Example:

| Standard criterion | Domain translation (clinical research context) |
|-------------------|----------------------------------------------|
| E1 — Evidence Set Completeness | "Are there major types of studies — randomized trials, observational data, meta-analyses — that you would expect to see here that are missing?" |
| R1 — Logical Validity | "Does each inferential step follow from the studies it cites? Are there logical leaps?" |
| R3 — Completeness | "What is this analysis assuming that it doesn't state? Are those assumptions reasonable in this domain?" |

Not all criteria require domain knowledge to assess. F1 (Claim Precision), F2 (Identifier Present), and F3 (Scope Defined) are procedural and can be assessed by the practitioner without the expert. Mark these on the worksheet as "Practitioner-assessed."

**Phase B: Pre-Review Briefing**

The practitioner conducts a 20–30 minute briefing with the expert covering:
1. The purpose and boundaries of the review ("You are being asked to verify, not endorse")
2. The independence requirement ("Your role is to find problems, not to confirm the claim")
3. The translated criteria (walk through the worksheet)
4. The review format (structured interview, not free-form reading)

**Phase C: Structured Review Interview**

The expert reviews the claim record in advance. The practitioner then conducts a structured interview:
- For each translated criterion: "What did you find for criterion [X]?"
- The practitioner records the expert's responses verbatim in the draft Verification Record.
- For any criterion the expert finds unclear, the practitioner clarifies using the standard VERA definition — but does not suggest how the criterion should be assessed.

**Phase D: Joint Record Production**

The practitioner drafts the Verification Record from the interview notes. The expert reviews and approves the record before it is finalized. The record must accurately reflect the expert's judgments, not the practitioner's interpretation of them.

---

### Implementation

1. **Assess expert independence.** Confirm the expert meets VERA independence requirements for Peer or Expert level. Document the basis for the independence assessment.

2. **Prepare the Criteria Translation Worksheet.** For each criterion: write the domain translation, mark practitioner-assessed criteria.

3. **Assess practitioner-assessed criteria independently.** Complete F1, F2, F3 and any other criteria that do not require domain knowledge before the expert engagement.

4. **Brief the expert.** Conduct the pre-review briefing. Ensure the expert understands the adversarial nature of verification before they begin reviewing the claim.

5. **Conduct the structured review interview.** Work through the translated criteria. Record responses verbatim or in close paraphrase. Do not editorialize.

6. **Draft and share the Verification Record.** Send the draft to the expert for review. Invite corrections to how their judgment is represented.

7. **Finalize the record.** Incorporate the expert's corrections. Both the practitioner and the expert sign or attribute the completed record.

8. **Document the process.** The Verification Record should note: that an Expert Verifier Onboarding protocol was used, the expert's identity and relevant qualifications, the independence assessment, and whether the expert reviewed and approved the record.

---

### Evidence Requirements

- Criteria Translation Worksheet (completed)
- Documentation of the expert's independence assessment
- Interview notes or transcript supporting the Verification Record entries
- Expert's review and approval of the final Verification Record

---

### Verification Criteria

- The Verification Record accurately reflects the expert's domain judgments (confirmed by expert approval)
- The independence assessment for the expert is documented at Peer or Expert level
- Practitioner-assessed criteria are distinguished from expert-assessed criteria in the record
- The process documentation is sufficient for a third party to understand how the verification was conducted

---

### Consequences

**Benefits:**
- Expert domain knowledge is captured in a VERA-compliant verification, rather than in an informal review that cannot be cited as VERA verification.
- The division of labor prevents practitioner VERA knowledge from substituting for expert domain judgment.
- The translated criteria enable experts to apply VERA standards without learning the full framework.

**Liabilities:**
- Criteria translation requires significant preparation effort from the practitioner.
- The structured interview format may feel unfamiliar or constraining to experts accustomed to free-form consultation.
- The joint record production step adds timeline; it cannot be completed until the expert has reviewed the draft.

---

### Known Uses

- **Medical affairs team, biotechnology firm (2025):** Applied when verifying a clinical claim for a regulatory submission; the medical director served as expert verifier using a translated criteria worksheet. The structured interview format surfaced a concern about evidence set completeness (a key trial type was missing) that the medical director had not mentioned in initial discussions.
- **Risk management function, insurance firm (2024):** Applied to verify an actuarial claim where the VERA-trained analyst lacked actuarial credentials; the credentialed actuary served as expert verifier. The joint record production required two revision rounds before the actuary was satisfied with the representation of their judgment.

---

### Related Patterns

- [VERA-P-0010](./verification.md#vera-p-0010) — Self-Verification with Adversarial Stance: Use when expert verifier engagement is not feasible; P-0010 is the fallback.
- [VERA-P-0013](./verification.md#vera-p-0013) — Claim Confidence Calibration: Expert verifiers who are new to VERA may calibrate confidence differently from experienced VERA verifiers; calibration exercises help.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0011 |
| Confidence | 0.81 |

---

<a id="vera-p-0012"></a>
## VERA-P-0012 — Cascading Claim Update

**Pattern ID:** VERA-P-0012

| Field | Value |
|-------|-------|
| Domain | Verification |
| Applicability | Team, Organization |
| Complexity | Complex |
| Maturity Level | 3 |

---

### Context

In a functioning VERA claim registry, verified claims are cited as evidence in other claims, creating a dependency graph. Claim A is used as evidence for Claim B; Claim B is used as evidence for Claim C. When Claim A changes verification state — new evidence refutes it, it is successfully contested, a reasoning gap is discovered — the epistemic status of Claims B and C is affected.

The Verification Protocol does not specify how to manage these downstream effects. Without a protocol, the most common outcome is that downstream claims remain Verified while their evidential basis has changed, creating a registry where the documented verification states no longer reflect the actual epistemic situation.

---

### Problem

Claim state changes do not automatically propagate to downstream claims. A claim that was Verified when it used Claim A as evidence remains Verified after Claim A is Refuted — unless someone identifies the dependency and triggers re-evaluation. In large registries, this problem compounds: Claim A's refutation may have been registered months ago, while Claim C (which depends on B which depends on A) continues to be cited in active decisions.

---

### Forces

- Not all upstream claim changes have the same downstream impact; mass re-verification is expensive and often unnecessary.
- The dependency graph may not be documented at lower maturity levels; this pattern requires dependency tracking infrastructure that must be established.
- Downstream claim maintainers may not be aware of upstream changes, especially in large organizations with distributed claim ownership.
- Re-verification of downstream claims requires the same resources as original verification; triggering it prematurely (for minor upstream changes) wastes those resources.
- Leaving downstream claims un-updated after significant upstream changes creates an epistemic integrity problem that compounds over time.

---

### Solution

Apply a **three-phase cascade protocol**: (1) register dependencies at claim creation, (2) triage impact when an upstream claim changes, (3) selectively re-verify based on triage results.

**Phase A: Dependency Registration**

At claim creation time (Verification Protocol Phase 1, Step 1.4), register every upstream claim used as evidence in the evidence set:
- Record the upstream claim's ID and current verification state
- Record which component of the new claim the upstream claim supports
- Register the new claim as a downstream dependent of the upstream claim in the registry

This registration creates a bidirectional link: the upstream claim record knows its downstream dependents; the downstream claim record knows its upstream dependencies.

**Phase B: Impact Triage**

When an upstream claim changes state, the registry system (or, in manual registries, the claim owner) identifies all registered downstream dependents and conducts an **impact triage** for each:

For each downstream claim:

1. **Identify the component supported by the changed upstream claim.** Which part of the downstream claim's evidence set does this affect?

2. **Assess the impact of the state change.** Use this matrix:

| Upstream change | Component support | Impact level |
|----------------|------------------|--------------|
| Verified → Partial | Single evidence item for this component | Moderate |
| Verified → Partial | One of multiple independent items for this component | Low |
| Verified → Contested | Any role | Moderate (pending resolution) |
| Verified → Refuted | Single evidence item for component | High |
| Verified → Refuted | One of multiple independent items | Moderate |
| Confidence drops ≥ 0.15 | Any role | Moderate |
| Confidence drops < 0.15 | Any role | Low |

3. **Assign a downstream action:**
   - **High impact**: Immediately update downstream claim state to Pending; initiate re-verification.
   - **Moderate impact**: Flag downstream claim for expedited review; notify claim owner; schedule re-verification within 30 days.
   - **Low impact**: Note the upstream change in the downstream claim's record; include in next scheduled review.

**Phase C: Selective Re-verification**

Re-verification of downstream claims proceeds according to the Verification Protocol, with two modifications:
- The Phase 2 evidence update step explicitly addresses the changed upstream claim (replace, supplement, or maintain with documented rationale).
- The Verification Record for the re-verification must reference the upstream change that triggered it.

---

### Implementation

1. **Establish dependency registration.** As part of the claim registry design (Integration domain, Level 3), create a mechanism for recording upstream dependencies at claim creation. In manual registries, a "Dependencies" column in the registry table is sufficient.

2. **Register dependencies for all new claims.** From the point of implementation, every new claim registers its upstream dependencies at creation time.

3. **Backfill existing claims.** For claims already in the registry, identify and register upstream dependencies retroactively. Prioritize high-stakes and frequently-cited claims.

4. **Establish a change notification process.** When a claim changes state, the change triggers identification of registered downstream dependents. In manual registries, this is a search of the dependency records; in automated registries, it is a query or alert.

5. **Conduct impact triage.** For each downstream dependent, apply the triage matrix and assign a downstream action (High / Moderate / Low impact).

6. **Execute downstream actions.** For High impact: immediately update claim state and initiate re-verification. For Moderate: notify owner and schedule. For Low: annotate the claim record.

7. **Complete re-verification.** For claims requiring re-verification, proceed through Phase 4 with the two modifications noted above.

---

### Evidence Requirements

- Dependency registration records for all claims whose evidence set includes upstream VERA claims
- Impact triage records for each downstream dependent of the changed upstream claim
- Re-verification records for all claims whose downstream action was High impact

---

### Verification Criteria

- All claims in the registry that use upstream VERA claims as evidence have registered dependencies
- Impact triage is conducted within 5 business days of an upstream claim state change
- High-impact downstream claims are updated to Pending state within 24 hours of triage
- Re-verification records reference the upstream change that triggered them

---

### Consequences

**Benefits:**
- Maintains the epistemic integrity of the claim registry over time.
- Prevents the compounding of undetected errors through the dependency graph.
- The triage protocol prevents unnecessary mass re-verification while ensuring significant changes are addressed.

**Liabilities:**
- Dependency registration adds Phase 1 work for every claim that cites upstream claims.
- Backfilling existing registries is time-intensive.
- Impact triage requires judgment; practitioners may consistently under- or over-estimate impact, requiring calibration.

---

### Known Uses

- **Knowledge management function, professional services firm (2025):** Implemented following discovery that a refuted market size claim had remained as evidence in seven active claims for four months without triggering review. Dependency registration was added to the claim template; the first cascade update identified two High-impact and three Moderate-impact downstream claims requiring action.
- **Research team, public policy organization (2025):** Applied after a key empirical claim about program effectiveness was successfully contested. Impact triage identified four downstream policy recommendation claims; two required immediate re-verification and revision, changing the organization's policy positions on two issues.

---

### Related Patterns

- [VERA-P-0005](./evidence.md#vera-p-0005) — Time-Sensitive Evidence Management: Stale upstream evidence items trigger P-0012 when the evidence's state change affects a claim's verification; the two patterns work together in registries with volatile evidence.
- [VERA-P-0010](./verification.md#vera-p-0010) — Self-Verification with Adversarial Stance: When a downstream claim requires re-verification and no independent verifier is available, P-0010 applies.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0012 |
| Confidence | 0.83 |

---

<a id="vera-p-0013"></a>
## VERA-P-0013 — Claim Confidence Calibration

**Pattern ID:** VERA-P-0013

| Field | Value |
|-------|-------|
| Domain | Verification |
| Applicability | Team, Organization |
| Complexity | Complex |
| Maturity Level | 4 |

---

### Context

Confidence ratings assigned by verifiers are only meaningful if they are consistent across verifiers and predictive of actual epistemic reliability. A confidence rating of 0.75 should mean the same thing regardless of which verifier assigned it, and the population of claims rated at 0.75 should be right approximately 75% of the time they are tested against outcomes.

In practice, different verifiers develop different implicit confidence scales. One verifier's 0.80 is another's 0.65. Some verifiers are systematically overconfident (assigning high confidence to claims that are subsequently contested or revised); others are systematically underconfident (assigning low confidence to claims that are never successfully challenged). Without calibration, the confidence distribution in a registry reflects verifier personality as much as epistemic quality.

---

### Problem

Inconsistent confidence calibration across verifiers undermines the confidence rating's value as a signal. Claims at similar evidential quality receive different ratings depending on who verified them. Downstream users who weight claims by confidence receive a noisy signal that mixes epistemic information with verifier variation. Organizations that track confidence distributions as a quality metric cannot distinguish genuine quality changes from verifier composition changes.

---

### Forces

- Calibration requires historical data (claims with known outcomes against which to check ratings) that is not available at lower maturity levels.
- Over-calibration — requiring verifiers to apply anchor examples mechanically — produces ratings that are consistent but insensitive to genuine variation in the current claim.
- Confidence calibration is a probabilistic concept; many practitioners find it unintuitive, and training in it requires investment.
- High-stakes claims need especially reliable confidence ratings; a confidence committee process for these claims adds overhead but reduces the risk of single-verifier mis-calibration.
- Public acknowledgment of calibration variability across verifiers requires organizational trust and psychological safety.

---

### Solution

Apply a three-component calibration program: **anchor examples** that establish a shared scale, **consistency tracking** that identifies verifier-level calibration gaps, and a **confidence committee** process for high-stakes claims.

**Component 1: Anchor Example Library**

Develop a library of claims with known outcomes, rated against the confidence scale by experienced verifiers who have reviewed the evidence and reasoning in detail. The library should include:

- At least three claims per confidence band (High 0.85+, Moderate 0.65–0.84, Low 0.40–0.64, Speculative below 0.40)
- Claims drawn from the organization's actual domains of work
- A documented rationale for each anchor rating, explaining which features of the evidence and reasoning justify the band
- Known outcomes for each claim (what subsequently happened; was the claim revised, contested, confirmed?)

Anchor examples are used in calibration exercises: verifiers rate the anchor claims before seeing the established ratings, then compare their ratings to the anchors and review the rationale for any gaps above 0.10.

**Component 2: Consistency Tracking**

The governance function tracks, for each active verifier:
- Mean confidence assigned over the trailing 12 months
- Standard deviation of confidence assigned
- Frequency of confidence ratings that are subsequently revised (indicator of mis-calibration)
- Frequency of claims verified that are subsequently contested (indicator of overconfidence)

Verifiers whose mean confidence is more than 0.10 above or below the registry mean, or whose subsequent revision or contest rates are substantially higher than peers, are flagged for calibration review. The review is conducted using anchor exercises, not as a disciplinary process.

**Component 3: Confidence Committee for High-Stakes Claims**

Claims above a defined stakes threshold — those informing board-level decisions, regulatory submissions, significant capital allocations, or public communications — are assigned confidence ratings by a **Confidence Committee** of three verifiers rather than a single verifier. The process:

1. Each committee member rates the claim independently, without discussion.
2. Ratings are shared simultaneously.
3. If all three ratings are within a 0.10 band: the final rating is the mean.
4. If any rating is outside the 0.10 band: a structured discussion identifies the source of disagreement. Each member reconsiders and re-rates independently. If consensus within 0.10 is still not achieved, the final rating is the lowest individual rating (conservative), with a note explaining the disagreement.

---

### Implementation

1. **Establish the anchor library.** Select 12–20 historical claims from the registry with known outcomes. Have at least two experienced verifiers rate each anchor independently. Where ratings agree within 0.10, adopt the mean as the anchor rating. Document the rationale.

2. **Conduct initial calibration exercises.** Have all active verifiers rate the anchor claims before seeing established ratings. Compare to anchors. Debrief individually on gaps larger than 0.10.

3. **Establish consistency tracking.** Implement tracking of the three verifier-level metrics in the governance function's regular reporting.

4. **Set the high-stakes threshold.** Define the criteria for Confidence Committee review. Document the threshold as part of the governance policy.

5. **Implement Confidence Committee process.** Designate a committee roster with at least five eligible verifiers (to allow committees of three who haven't been involved in the specific claim).

6. **Conduct regular calibration exercises.** Schedule biannual calibration exercises for all active verifiers, using updated anchor examples. Calibration exercises are part of verifier professional development, not performance evaluation.

7. **Review and update anchors.** The anchor library ages; outcomes accumulate; domains shift. Review anchors annually and add new examples from recent high-quality verifications.

---

### Evidence Requirements

- The anchor example library with documented ratings and rationales
- Calibration exercise results for each active verifier
- Consistency tracking metrics reviewed by the governance function
- For Confidence Committee claims: the individual ratings before discussion, the discussion record, and the final rating with rationale

---

### Verification Criteria

- The anchor library contains at least three claims per confidence band
- All active verifiers have completed at least one calibration exercise in the trailing 12 months
- Consistency tracking is reviewed by the governance function at each meeting
- All claims above the high-stakes threshold have Confidence Committee records

---

### Consequences

**Benefits:**
- Confidence ratings become meaningful signals rather than idiosyncratic verifier judgments.
- Systematic overconfidence or underconfidence is detected and addressed before it compounds.
- High-stakes claims receive more reliable confidence assessments through the committee process.

**Liabilities:**
- The anchor library requires significant investment to develop and maintain.
- Calibration exercises require verifier time as a scheduled activity.
- The Confidence Committee process adds timeline for high-stakes claims.
- Surfacing calibration variability across verifiers requires psychological safety that may not exist in all organizations.

---

### Known Uses

- **Research function, financial services firm (2025):** Implemented after discovering that confidence ratings from two senior analysts differed systematically by ~0.15 on equivalent claims. Anchor exercises identified that one analyst applied confidence to evidence quality (strong evidence = high confidence) while the other applied it to claim outcome predictability (high-uncertainty domains = low confidence regardless of evidence). The conceptual alignment achieved through calibration exercises resolved the discrepancy.
- **Risk management function, infrastructure company (2024):** Implemented the Confidence Committee for all claims informing capital allocation decisions above $50M. In the first year, committee discussions identified material confidence gaps in four high-stakes claims that single-verifier review had not surfaced.

---

### Related Patterns

- [VERA-P-0010](./verification.md#vera-p-0010) — Self-Verification with Adversarial Stance: The 0.72 confidence ceiling for self-verification is itself a calibration rule; P-0013 ensures that ceiling is applied consistently across all self-verifications.
- [VERA-P-0011](./verification.md#vera-p-0011) — Expert Verifier Onboarding: Expert verifiers new to VERA will not be calibrated; include them in calibration exercises before they rate high-stakes claims.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0013 |
| Confidence | 0.79 |
