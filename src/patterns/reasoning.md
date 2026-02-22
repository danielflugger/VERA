# Reasoning Patterns

Reasoning Patterns address recurring challenges in constructing and evaluating the logical connection between evidence and conclusions. They cover claim decomposition, assumption identification, contrary evidence handling, and the documentation of analogical arguments — the most common places where reasoning chains break down in practice.

All patterns follow the canonical [Pattern Template](../foundations/pattern-template.md). Inference types (deductive, inductive, abductive, analogical), reasoning chain structure, and quality dimensions are defined in the [Lexicon](../foundations/lexicon.md).

---

<a id="vera-p-0006"></a>
## VERA-P-0006 — Compound Claim Decomposition

**Pattern ID:** VERA-P-0006

| Field | Value |
|-------|-------|
| Domain | Reasoning |
| Applicability | All |
| Complexity | Moderate |
| Maturity Level | 2 |

---

### Context

Virtually every significant assertion made in organizational contexts is a compound claim: it asserts multiple things simultaneously, often with different levels of evidential support for each component. "Our AI system is accurate, efficient, and ready for production deployment" is not one claim — it is at least three. "This market strategy will capture significant share in the next two years" asserts both the strategic mechanism and the time horizon, which may have very different evidence bases.

Verification Protocol Phase 1, Step 1.2 requires decomposing compound claims before proceeding. This pattern specifies *how* to decompose effectively, addressing the most common failure mode: under-decomposition, where practitioners split the most obvious compound but stop before reaching independently verifiable atomic claims.

---

### Problem

Practitioners under-decompose for two reasons. First, it is not obvious where decomposition is complete — there is no clear signal that an atomic claim has been reached. Second, the work of tracking multiple sub-claims and their dependencies is more complex than tracking one compound, so there is incentive to stop decomposing before the components are truly independent.

The consequence of under-decomposition is that claims are verified as units when their components have very different evidential strength. A compound claim with one well-supported and one poorly-supported component receives an averaged verification judgment that obscures the weak component.

---

### Forces

- Over-decomposition produces too many micro-claims with complex dependency trees that are harder to navigate than the original compound.
- Under-decomposition hides differential evidential support across components.
- Some claims genuinely cannot be decomposed without losing their meaning (the conjunction is the claim).
- Sub-claim dependencies must be tracked and managed; if Sub-claim B is true only if Sub-claim A is true, this dependency must be explicit.
- The decomposition must be complete before evidence assembly begins; decomposing after evidence is gathered risks reverse-engineering the decomposition to fit the evidence found.

---

### Solution

Apply three tests to each claim component during decomposition. A component passes all three tests only when it has reached an appropriate level of atomicity.

**Test 1 — Independence Test:** Can this component be true while the other components are false? If yes, it is independent enough to stand as a separate claim. If no, the components are logically entangled and must be treated as a conjunction claim.

**Test 2 — Evidence Test:** Can you identify a distinct type of evidence that would specifically address this component — evidence that would not be relevant to the other components? If yes, the component has a distinct evidential basis and should be separated. If no, the components share an evidential basis and may appropriately remain together.

**Test 3 — Verification Test:** If this component were false, would the parent claim's overall verification state change? If yes, it is significant enough to track separately. If no, it may be a subordinate qualification rather than a component.

Apply these three tests iteratively. After each round of decomposition, apply the tests again to each new component. Stop when all components pass all three tests or when further decomposition would produce components too small to be meaningful.

---

### Implementation

1. **State the compound claim precisely.** Write out the full assertion. Underline every conjunction (and, but, while, as well as), every implicit comparison, and every embedded causal or temporal claim.

2. **Draft candidate components.** Separate the underlined elements into candidate atomic claims. Write each as a complete declarative sentence.

3. **Apply the three tests to each candidate.** For each candidate component, work through the Independence, Evidence, and Verification tests. Document the result of each test.

4. **Separate independent components.** Components that pass all three tests become distinct VERA claims, each receiving its own Claim ID and proceeding through the Protocol independently.

5. **Handle entangled components.** Components that fail the Independence Test (cannot be true independently) should be analyzed: Is the entanglement conceptual (the claim is genuinely conjunctive) or definitional (one term is being used to mean both)? Conceptually conjunctive claims are kept together with a note. Definitional entanglements require rephrasing.

6. **Map sub-claim dependencies.** Where Sub-claim B is true only if Sub-claim A is true, document this dependency explicitly. The verification of B depends on A being Verified; if A is Contested or Refuted, B must be re-evaluated.

7. **Reconstruct the parent claim.** Document how the atomic sub-claims combine to produce the original compound assertion. This reconstruction step is verified at Phase 4 to ensure no meaning was lost or added during decomposition.

---

### Evidence Requirements

- The original compound assertion documented verbatim
- Test results for each candidate component
- Dependency map showing which sub-claims are prerequisites for others
- Reconstruction record showing how sub-claims combine to the parent

---

### Verification Criteria

- Every sub-claim passes all three tests at its current level of decomposition
- Sub-claim dependencies are documented and are consistent with the logical structure of the parent claim
- The reconstruction is complete: all elements of the original assertion are accounted for in the sub-claims
- No sub-claim asserts more than the evidence for it specifically supports

---

### Consequences

**Benefits:**
- Differential evidential strength across claim components is made visible rather than averaged.
- Weak components are identified and can be researched independently or acknowledged as limitations.
- Sub-claim reuse becomes possible: a well-supported atomic claim can serve as evidence in multiple parent claims.

**Liabilities:**
- Decomposition adds Phase 1 work before evidence assembly begins.
- Dependency tracking adds complexity to the claim registry, especially for multi-level decompositions.
- Sub-claims with low evidential support may, when isolated, cause practitioners to abandon claims that would have survived as compounds — which is not always the wrong outcome, but can feel like a loss.

---

### Known Uses

- **Strategy team, global technology company (2024):** Applied to a strategic recommendation that asserted three distinct market conditions plus a causal mechanism. Decomposition into five sub-claims revealed that one (the causal mechanism) had no supporting evidence and was an assumption. The assumption was documented, and the parent claim was revised to acknowledge it explicitly.
- **Research analyst, public policy institute (2025):** Applied during systematic review of a government program; identified that the program's "success" claim contained four components with different evidence bases, two of which were not supported by available evidence. The decomposed version was more useful for policy recommendations than the aggregate claim.

---

### Related Patterns

- [VERA-P-0007](./reasoning.md#vera-p-0007) — Hidden Assumption Excavation: Apply after decomposition; each sub-claim has its own assumption set that must be excavated.
- [VERA-P-0012](./verification.md#vera-p-0012) — Cascading Claim Update: When sub-claims are treated as upstream evidence for a parent claim, sub-claim state changes trigger the cascading update protocol.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0006 |
| Confidence | 0.87 |

---

<a id="vera-p-0007"></a>
## VERA-P-0007 — Hidden Assumption Excavation

**Pattern ID:** VERA-P-0007

| Field | Value |
|-------|-------|
| Domain | Reasoning |
| Applicability | All |
| Complexity | Moderate |
| Maturity Level | 2 |

---

### Context

All reasoning chains contain assumptions — premises taken as true without direct evidence. The Verification Protocol (Phase 3, Step 3.4) requires practitioners to identify and document assumptions. The practical problem is that the most consequential assumptions are typically the ones the practitioner doesn't notice they're making, because they feel like facts rather than choices.

The assumptions that destroy reasoning chains under scrutiny are rarely the ones the author flagged. They are the ones that felt so obviously true — so much like background reality rather than premise — that they were never examined.

---

### Problem

Asking "what am I assuming?" is insufficient for identifying hidden assumptions. The question is self-defeating: if you knew what you were assuming, it wouldn't be hidden. Practitioners who apply Step 3.4 conscientiously document the assumptions they are *aware* of. The remaining hidden assumptions still determine whether the reasoning chain holds.

This is not a problem of dishonesty or carelessness. It is a structural problem in human reasoning: things that feel like facts are processed differently from things that feel like premises. The solution requires a systematic interrogation method that bypasses this processing difference.

---

### Forces

- You cannot directly inspect your own invisible assumptions; indirect interrogation methods are required.
- Some assumptions are so widely shared in a context that documenting them adds noise without epistemic value.
- Other assumptions are technically visible (practitioners know them) but not documented because they are taken as given.
- Contested assumptions — premises that are genuinely disputed in the relevant community — are the highest-priority category; they must be documented and their contestedness acknowledged.
- The same reasoning chain applied in a different context may have entirely different assumption sets; context-sensitivity is a critical dimension.

---

### Solution

Apply a **three-question interrogation** to every step in the reasoning chain. The three questions are designed to approach the same space of hidden assumptions from different angles, increasing the probability of surfacing any given assumption.

**Question 1: Necessary Conditions**
*"What would need to be true for this conclusion to follow from these premises?"*

List everything that must hold — beyond what is stated in the premises — for the inference to be valid. This surfaces assumptions about continuity ("what was true yesterday is true today"), scope ("the pattern observed in this sample holds for the whole population"), mechanism ("A causes B through mechanism M"), and completeness ("the factors listed here are the relevant ones").

**Question 2: Variance**
*"What am I treating as fixed that could vary?"*

Identify every quantity, relationship, or category in the reasoning step that you are treating as constant. Consider: What if it varied? Would the conclusion change? If yes, the constancy is an assumption that must be documented. This question surfaces assumptions about measurement invariance, definitional stability, contextual consistency, and the absence of moderating variables.

**Question 3: Values and Framing**
*"Where is this reasoning sensitive to value choices or framing decisions?"*

Identify where the reasoning chain encodes choices that are presented as factual but are actually normative or framing-dependent: the choice of comparison baseline, the definition of "significant" or "successful," the selection of which effects to count and which to ignore. This question surfaces normative assumptions that are particularly likely to be contested by people who share the evidence but not the values.

---

### Implementation

1. **Write out the reasoning chain in full** before beginning excavation. The interrogation cannot be applied to a chain that doesn't yet exist. Complete Phase 3, Step 3.3 first.

2. **Apply Question 1 to each step.** For each step in the chain, ask: What would need to be true, beyond the stated premises, for this conclusion to follow? List every condition. Write them as declarative statements.

3. **Apply Question 2 to each step.** For each step, identify every variable that is treated as fixed. Consider: time, location, population, definition, measurement methodology, causal pathway. List all.

4. **Apply Question 3 to each step.** Identify any normative or framing-sensitive elements. List them explicitly.

5. **Classify each identified assumption.** For each item surfaced:
   - **Background assumption**: Widely shared, stable, low contestedness — document briefly.
   - **Domain assumption**: Specific to the domain, likely shared by domain experts — document with reference to authority.
   - **Contested assumption**: Genuinely disputed in the relevant community — document prominently, note the dispute, assess whether the claim should be scoped to conditions under which the assumption holds.
   - **Novel assumption**: Not standard in the domain, introduced by the claimant — document thoroughly, treat as requiring evidence or explicit justification.

6. **Add assumptions to the reasoning chain.** All Domain, Contested, and Novel assumptions are added as documented elements of the reasoning chain — either as explicit premises in the step where they operate, or as a separate "Assumptions" section linked to the relevant steps.

7. **Reassess claim scope.** If any Contested assumptions are load-bearing (the conclusion fails if the assumption fails), consider scoping the claim to the conditions under which the assumption holds, rather than presenting the claim as unconditionally true.

---

### Evidence Requirements

- The complete reasoning chain before excavation begins
- The list of items surfaced by each of the three questions, for each step
- The classification of each surfaced item
- For Contested and Novel assumptions: documentation of the dispute or novelty

---

### Verification Criteria

- All three questions have been applied to all steps in the reasoning chain
- Every Contested and Novel assumption is documented prominently in the claim record
- The confidence rating reflects any Contested assumptions that are load-bearing
- The claim's scope statement accounts for conditions under which load-bearing Contested assumptions fail

---

### Consequences

**Benefits:**
- Surfaces the most dangerous class of reasoning errors: invisible premises.
- Forces explicit engagement with contestedness, preventing the claim from being presented as more settled than it is.
- The documented assumption set becomes a valuable resource for downstream users who may be in contexts where the assumptions don't hold.

**Liabilities:**
- The three-question interrogation takes time and requires sustained adversarial focus.
- Extensive assumption documentation can make reasoning chains appear more uncertain than practitioners are comfortable with.
- Distinguishing background from contested assumptions requires domain knowledge; practitioners without deep domain expertise may mis-classify.

---

### Known Uses

- **Product team, enterprise software firm (2024):** Applied during a business case review; Question 2 (Variance) surfaced an assumption that customer acquisition cost would remain constant as the sales team scaled — an assumption that was false and that invalidated the unit economics claim. The business case was revised before board presentation.
- **Academic researcher, political science (2025):** Applied to a comparative politics claim using analogical inference; Question 3 (Values and Framing) revealed that the comparison baseline was implicitly encoding a normative preference that was contested in the literature. The framing assumption was disclosed and the paper's scope was narrowed accordingly.

---

### Related Patterns

- [VERA-P-0006](./reasoning.md#vera-p-0006) — Compound Claim Decomposition: Apply P-0006 before P-0007; each sub-claim has its own assumption set.
- [VERA-P-0009](./reasoning.md#vera-p-0009) — Analogical Reasoning Validation: Analogical reasoning is particularly prone to hidden similarity assumptions; apply both patterns when inference type is analogical.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0007 |
| Confidence | 0.85 |

---

<a id="vera-p-0008"></a>
## VERA-P-0008 — Contrary Evidence Integration

**Pattern ID:** VERA-P-0008

| Field | Value |
|-------|-------|
| Domain | Reasoning |
| Applicability | All |
| Complexity | Moderate |
| Maturity Level | 2 |

---

### Context

Evidence assembly following a proper prospective search plan (Verification Protocol Phase 2) will routinely produce evidence items that complicate or contradict the claim. This is not a failure of the research process — it is the expected outcome of honest evidence gathering. The question is what to do with contrary evidence once found.

Verification Protocol Phase 3, Step 3.5 specifies four valid responses to contrary evidence: **outweigh** (supporting evidence is stronger), **distinguish** (contrary evidence applies to a different scope), **qualify** (revise the claim to acknowledge the contradiction), or **concede** (the contrary evidence is decisive). But it does not provide a framework for determining which response is appropriate. Left without guidance, practitioners default to "outweigh" — a choice that frequently rationalizes rather than responds to contrary evidence.

---

### Problem

The four responses (outweigh, distinguish, qualify, concede) are not interchangeable. Each is appropriate in specific conditions, and applying the wrong one produces either an overconfident claim (outweigh when distinguish or qualify is correct) or an artificially weakened claim (qualify or concede when the contrary evidence is genuinely less weighty). The current Protocol provides vocabulary but not decision criteria.

---

### Forces

- "Outweigh" is easy to assert and hard to disprove; it is structurally available as a rationalization for any contrary evidence.
- "Distinguish" can be used to scope-away relevant contrary evidence by drawing a distinction that does not reflect the claim's actual applicability.
- "Qualify" reduces the claim's practical utility; practitioners may resist it even when it is the epistemically correct response.
- "Concede" is professionally uncomfortable; there is institutional pressure against abandoning claims that have been asserted.
- The quality and independence of contrary evidence must be assessed using the same standards as supporting evidence.

---

### Solution

Before selecting a response, evaluate the contrary evidence on three dimensions using the same criteria applied to supporting evidence. The evaluation produces a **contrary evidence profile** that determines which responses are available.

**Dimension 1: Quality Tier**
Rate the contrary evidence using the standard four-tier scale. Higher-tier contrary evidence requires a stronger response.

**Dimension 2: Relevance Scope**
Assess whether the contrary evidence applies to exactly the same claim scope as the assertion, or to a related but distinct scope. Document the scope match precisely.

- **Full overlap**: Contrary evidence directly addresses the claim as stated.
- **Partial overlap**: Contrary evidence addresses a subset or superset of the claim's scope.
- **Adjacent**: Contrary evidence addresses a closely related claim, but not this one.

**Dimension 3: Independence**
Assess whether the contrary evidence is independent of the supporting evidence — does it derive from a different primary source? Apply the same source tree analysis as VERA-P-0004.

**Response Selection Matrix:**

| Quality | Scope | Independence | Available responses |
|---------|-------|--------------|---------------------|
| Primary/Secondary | Full overlap | Independent | Qualify or Concede only |
| Primary/Secondary | Partial overlap | Independent | Distinguish (if honest), Qualify |
| Primary/Secondary | Full overlap | Dependent | Outweigh possible, with documented argument |
| Tertiary/Testimonial | Full overlap | Independent | Outweigh possible, Qualify preferred |
| Tertiary/Testimonial | Any | Dependent | Outweigh with argument |
| Any | Adjacent | Any | Distinguish (document the distinction precisely) |

Note: "Outweigh possible" means the response is available but must be argued — the reasoning chain must explain specifically why the supporting evidence outweighs the contrary, not merely assert that it does.

---

### Implementation

1. **Compile contrary evidence items.** From the Phase 2 evidence set, identify all items marked as complicating or contradicting the claim.

2. **Evaluate each item on three dimensions.** For each contrary item: assign quality tier, assess scope overlap, assess independence from supporting evidence.

3. **Apply the response matrix.** Identify which responses are available for each item. If no response other than Qualify or Concede is available, proceed directly to Step 6.

4. **For Outweigh responses: build the argument.** Write the explicit comparison: why does the supporting evidence (identified by item) outweigh the contrary evidence (identified by item)? The argument must reference quality tier, scope, and independence — not just assert that the balance favors the claim.

5. **For Distinguish responses: state the distinction precisely.** Write the exact boundary between what the contrary evidence addresses and what the claim asserts. The distinction must be genuine: it cannot be drawn post hoc purely to exclude the contrary evidence.

6. **For Qualify responses: revise the claim.** Return to Phase 1 and revise the claim statement to incorporate the qualification. The qualification must be substantive — not a hedge that preserves the original meaning while appearing to respond to the contrary evidence.

7. **For Concede responses: document the concession.** Record that the contrary evidence was decisive for the claim as stated. The claim may be revised to a narrower version that the evidence does support, or retired.

8. **Document all responses in the reasoning chain.** Each contrary evidence item and its response must appear as a step in the reasoning chain. Contrary evidence addressed only in footnotes or appendices is not transparent reasoning — it is disclosure theater.

---

### Evidence Requirements

- Quality tier assessment for each contrary evidence item
- Scope overlap assessment with documentation of the boundary
- Independence assessment (source tree) for each contrary evidence item
- For Outweigh: the explicit comparative argument
- For Distinguish: the precisely stated scope distinction

---

### Verification Criteria

- Every contrary evidence item identified in Phase 2 appears in the reasoning chain with a documented response
- For Outweigh responses: the argument references quality tier, scope, and independence; it does not merely assert the balance favors the claim
- For Distinguish responses: the stated distinction is verifiable and not drawn solely to exclude the contrary evidence
- Qualify and Concede responses result in documented claim revisions
- The confidence rating reflects the weight and quality of contrary evidence that was addressed by Outweigh or Distinguish responses (not assumed to be neutralized by the response)

---

### Consequences

**Benefits:**
- Prevents "outweigh" from functioning as a rationalization by requiring it to be argued.
- Makes the actual treatment of contrary evidence visible and auditable.
- Forces genuine engagement with evidence that contradicts the claim rather than gestural acknowledgment.

**Liabilities:**
- The three-dimension evaluation adds analysis work for each contrary evidence item.
- The response matrix constrains available responses in ways that may feel limiting when the practitioner has strong conviction in the claim.
- Qualify and Concede responses require revising work already done, which creates resistance.

---

### Known Uses

- **Legal research team, corporate law firm (2025):** Applied during preparation of a legal memorandum with conflicting precedents; the response matrix revealed that two "distinguishable" cases were in fact full-overlap contrary evidence, requiring a Qualify response that changed the memorandum's conclusion.
- **Environmental assessment team, infrastructure firm (2024):** Applied to an environmental impact claim; identified that the strongest contrary evidence (a Primary-tier independent study) required a Concede response on one of three claim components, leading to a scope revision that survived regulatory scrutiny where the original would not have.

---

### Related Patterns

- [VERA-P-0001](./evidence.md#vera-p-0001) — Absence-of-Evidence Assessment: When no contrary evidence is found despite an anticipated type, use P-0001 to assess the materiality of its absence.
- [VERA-P-0002](./evidence.md#vera-p-0002) — Conflicted Source Disclosure: When contrary evidence comes from a conflicted source, the conflict affects the quality-tier assessment but does not eliminate the contrary evidence.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0008 |
| Confidence | 0.83 |

---

<a id="vera-p-0009"></a>
## VERA-P-0009 — Analogical Reasoning Validation

**Pattern ID:** VERA-P-0009

| Field | Value |
|-------|-------|
| Domain | Reasoning |
| Applicability | All |
| Complexity | Complex |
| Maturity Level | 3 |

---

### Context

Analogical reasoning — "this case is like that other case; what was true there is likely true here" — is ubiquitous in organizational and policy decision-making. Case studies, precedent reasoning, benchmarking, and "best practices" transfer all rely on analogy. VERA's Lexicon designates analogical inference as the weakest of the four inference types, because its validity depends entirely on the strength of the similarity being claimed — a dependency that is almost never assessed rigorously.

Practitioners who use analogical reasoning typically document it as: "This is similar to [reference case], which achieved [outcome], therefore [conclusion]." What is missing is any assessment of *how similar* the cases are, on *which dimensions* the similarity holds, and what the *disanalogies* imply for the scope of the conclusion.

---

### Problem

Analogical reasoning is accepted in most reasoning chains without examination of the similarity claim that underlies it. The similarity is asserted, not demonstrated. Yet the entire inference rests on it. An analogy where the reference case and the current case are similar on three dimensions but differ on the two dimensions that determine the outcome is not just weak — it is actively misleading.

---

### Forces

- Requiring rigorous similarity analysis for all analogical reasoning would burden a widely-used and often valuable inference form.
- The relevant similarity dimensions are domain-specific; no domain-agnostic similarity metric exists.
- Disanalogies are often harder to articulate than similarities, because the analyst is motivated by the analogical connection.
- Analogical conclusions should be scoped to what the similarity actually supports, which may be narrower than what the practitioner wants to conclude.
- High-stakes decisions frequently rely on analogical reasoning from historical cases; this is where the rigor investment is most justified.

---

### Solution

Apply a structured **similarity-disanalogy analysis** that produces a **similarity score** and determines the permissible scope of the analogical conclusion.

**Phase A: Dimension Identification**

Identify the dimensions on which the reference case and current case could be similar or different. Dimensions should be:
- Causally relevant: they plausibly affect the outcome being analogized
- Independently assessable: each dimension can be evaluated without assuming the conclusion
- Specific: not "general context" but the specific contextual factors that might matter

Generate dimensions by asking: *What features of the reference case might explain its outcome? What features of the current case might affect the outcome? Where do these feature sets overlap?*

**Phase B: Similarity Scoring**

For each identified dimension, assess the degree of similarity between the reference case and the current case on a four-point scale:

| Score | Meaning |
|-------|---------|
| 3 | Substantially identical on this dimension |
| 2 | Similar with noted differences |
| 1 | Related but materially different |
| 0 | Disanalogous — cases differ significantly on this dimension |

Calculate the **Similarity Score**: sum of scores divided by (3 × number of dimensions). A score of 1.0 is perfect similarity; 0.0 is complete disanalogy.

**Phase C: Disanalogy Assessment**

For any dimension scored 0 or 1, conduct a specific assessment: does the disanalogy on this dimension affect the outcome being claimed? If a dimension is disanalogous but outcome-irrelevant, the disanalogy does not weaken the inference. If a dimension is disanalogous and outcome-relevant, the disanalogy directly limits the conclusion's scope.

**Conclusion Scope Determination:**

| Similarity Score | Permissible conclusion scope |
|-----------------|------------------------------|
| 0.85 – 1.0 | Strong analogical inference; conclusion scope matches reference case |
| 0.65 – 0.84 | Moderate analogical inference; conclusion must acknowledge material differences |
| 0.40 – 0.64 | Weak analogical inference; conclusion must be qualified to the dimensions of similarity; outcome-relevant disanalogies limit the conclusion explicitly |
| Below 0.40 | Analogy is not sufficient to support the inference; either find a closer reference case or change inference type |

---

### Implementation

1. **State the reference case.** Document the specific case being used as the analogical basis. Retrieve at least one evidence item (Tier 1 or 2 preferred) that documents the reference case's relevant features and outcome.

2. **Identify causally relevant dimensions.** List the dimensions on which similarity matters for the claimed outcome. If domain expertise is needed to identify these dimensions, obtain it before proceeding.

3. **Score each dimension.** For each dimension, assess and document the similarity score with a brief justification.

4. **Compute the Similarity Score.** Calculate and record the aggregate score.

5. **Conduct disanalogy assessment for low-scored dimensions.** For each dimension scored 0 or 1, assess outcome-relevance. Document the assessment.

6. **Determine permissible conclusion scope.** Apply the scope table to the Similarity Score. Revise the claim statement if the permissible scope is narrower than what was originally asserted.

7. **Document in the reasoning chain.** The analogy step in the reasoning chain must reference: the reference case, the Similarity Score, the outcome-relevant disanalogies, and the scoped conclusion.

8. **Assign confidence.** Analogical inference starts at a lower confidence ceiling than deductive or inductive inference. Map the Similarity Score to a confidence ceiling: Score 0.85+ → ceiling 0.80; Score 0.65–0.84 → ceiling 0.70; Score 0.40–0.64 → ceiling 0.55.

---

### Evidence Requirements

- At least one Tier 1 or Tier 2 evidence item documenting the reference case's features and outcome
- Documented dimension identification process (not just the list; the reasoning for including each dimension)
- Per-dimension similarity scores with justifications
- Disanalogy assessments for all dimensions scored 0 or 1

---

### Verification Criteria

- A reference case is documented with Tier 1 or Tier 2 evidence (not "the well-known case of..." without citation)
- Similarity dimensions are identified and are genuinely causally relevant — not selected to maximize the score
- The Similarity Score is calculated correctly from individual dimension scores
- The claim's scope matches the permissible scope for the achieved Similarity Score
- The confidence ceiling for the Similarity Score is applied in the confidence rating

---

### Consequences

**Benefits:**
- Makes the similarity claim — the actual basis of analogical inference — explicit and challengeable.
- Forces acknowledgment of disanalogies and their implications, producing more honest conclusions.
- The Similarity Score provides a communicable summary of analogical strength.

**Liabilities:**
- The dimension identification step requires domain knowledge; incorrect dimensions produce misleading scores.
- The four-point scoring scale involves judgment; different analysts may score the same dimension differently.
- The conclusion scope constraints may produce claims narrower than practitioners want, creating pressure to inflate dimension scores.

---

### Known Uses

- **Strategy team, consumer goods company (2025):** Applied to a market entry strategy that analogized from a successful entry in a different geography. Similarity Score of 0.61 — below the threshold for strong inference — revealed significant disanalogies in regulatory environment and distribution infrastructure. The strategy was modified to address the disanalogous dimensions before proceeding.
- **Policy research institute (2024):** Applied to a policy proposal drawing on an international precedent. Identified that three of eight dimensions were outcome-relevant disanalogies; the claim was revised from "Policy X will achieve Outcome Y" to "Policy X may achieve Outcome Y under conditions A, B, and C, which differ from the reference case in the following ways."

---

### Related Patterns

- [VERA-P-0007](./reasoning.md#vera-p-0007) — Hidden Assumption Excavation: Analogical reasoning is particularly prone to hidden similarity assumptions; the two patterns are complementary and should be applied together.
- [VERA-P-0008](./reasoning.md#vera-p-0008) — Contrary Evidence Integration: Cases where the analogy has been tested and found wanting (a prior attempt to apply the same analogy that failed) are contrary evidence; integrate them using P-0008.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0009 |
| Confidence | 0.80 |
