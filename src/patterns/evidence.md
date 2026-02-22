# Evidence Patterns

Evidence Patterns address recurring challenges in the Evidence domain: identifying what evidence to look for, retrieving and rating it, assessing the independence of evidence items, handling evidence from problematic sources, and managing evidence whose reliability changes over time.

All patterns in this chapter follow the canonical [Pattern Template](../foundations/pattern-template.md). Evidence quality tier ratings (Primary, Secondary, Tertiary, Testimonial) and evidence independence classifications (Independent, Correlated, Dependent) are defined in the [Lexicon](../foundations/lexicon.md).

---

<a id="vera-p-0001"></a>
## VERA-P-0001 — Absence-of-Evidence Assessment

**Pattern ID:** VERA-P-0001

| Field | Value |
|-------|-------|
| Domain | Evidence |
| Applicability | All |
| Complexity | Moderate |
| Maturity Level | 2 |

The full text of this pattern appears in [Pattern Template: A Worked Example](../foundations/pattern-template.md#a-worked-example-the-absence-of-evidence-pattern), where it serves as the canonical worked example of the pattern format. The summary below is provided for catalog completeness.

**Problem in brief:** When a category of evidence listed in the prospective search plan yields no results, its absence may be non-material, moderately significant, or highly significant to the claim's confidence — but there is no standard method for assessing which.

**Solution in brief:** Assess each absent evidence item on three dimensions — whether it was expected versus unexpected, whether it is substitutable by a different evidence type, and what direction it would likely point if it existed — and assign a materiality rating (Non-material / Moderate / Significant) with corresponding documentation and confidence adjustment requirements.

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0001 |
| Confidence | 0.88 |

---

<a id="vera-p-0002"></a>
## VERA-P-0002 — Conflicted Source Disclosure

**Pattern ID:** VERA-P-0002

| Field | Value |
|-------|-------|
| Domain | Evidence |
| Applicability | All |
| Complexity | Moderate |
| Maturity Level | 2 |

---

### Context

Practitioners regularly encounter evidence from sources that have a financial, institutional, or personal stake in the claim's outcome. Industry-funded clinical studies, vendor-produced benchmark reports, advocacy group research, regulatory submissions by regulated entities, and expert testimony from retained consultants are all examples. This situation is not unusual — in many domains, the parties with the most relevant data are also parties with the most interest in how it is interpreted.

The standard VERA Evidence criteria require that evidence items be quality-rated (E2) and that their independence be assessed (E3). Neither criterion directly addresses conflict of interest as a distinct category. Conflict of interest reduces — but does not eliminate — an evidence item's epistemic value. An industry-funded study is not automatically wrong; a regulatory submission is not automatically self-serving. But the conflict changes how the evidence should be weighted and documented.

---

### Problem

When the most relevant available evidence for a claim component comes from a source with a stake in the claim's outcome, practitioners face a genuine dilemma: treating the evidence as equivalent to unconflicted evidence understates the epistemic risk; discarding all conflicted evidence may leave a claim without support for an important component. Neither extreme is correct. The framework needs a middle path.

---

### Forces

- Conflicted sources often produce the most thorough and current evidence in a domain, because they have the most investment in understanding it.
- Discarding all conflicted evidence may constitute selective citation — if the conflicted evidence points against the claim, discarding it is a violation of Evidence Primacy.
- The degree of conflict varies enormously: minor institutional affiliation is not equivalent to direct financial stake in the claim's outcome.
- Disclosure without corroboration is insufficient for high-conflict sources; corroboration without disclosure obscures a legitimate epistemic concern.
- Requiring corroboration for all conflicted evidence creates a research burden disproportionate to the conflict's significance in some cases.

---

### Solution

Apply a **conflict severity rating** to each evidence item identified as coming from a conflicted source. Then apply the corresponding disclosure and corroboration requirements for that severity level.

**Conflict Severity Scale:**

| Severity | Description | Examples |
|----------|-------------|---------|
| **Low** | Institutional connection without financial stake in claim outcome | Author is affiliated with an organization that advocates related positions; publication is associated with a think tank with a general ideological orientation |
| **Moderate** | Indirect financial or reputational stake | Organization that funded the study would benefit from the claim being true; author has consulting relationship with an industry the claim concerns |
| **High** | Direct financial stake in the specific claim's outcome | Study funded by company whose product is the subject of the claim; evidence produced by a party in a dispute about the claim's subject matter |

**Requirements by Severity Level:**

| Severity | Disclosure | Corroboration | Confidence Impact |
|----------|-----------|---------------|------------------|
| Low | Note affiliation in evidence item record | None required | ≤ 0.05 reduction |
| Moderate | Note conflict and nature of interest in evidence item record | Attempt to identify at least one unconflicted corroborating source; if none found, document the search | 0.05–0.10 reduction |
| High | Note conflict prominently in evidence item record and in reasoning chain | Corroboration from unconflicted source required for any evidence item at this severity level; if unavailable, claim confidence reduced and limitation disclosed in claim statement | 0.10–0.20 reduction |

For High severity evidence with no available unconflicted corroboration: the evidence may still be used, but the reasoning chain must explicitly argue why the conflicted source's evidence is credible despite the conflict (e.g., the evidence is verifiable through independent means, the conflict is disclosed in the source's own methodology, the claim is against the source's interest).

---

### Implementation

1. **Identify the source's relationship to the claim.** For each evidence item, research whether the source organization or author has a financial, institutional, or reputational stake in whether the claim is true. Document the relationship or its absence.

2. **Rate conflict severity.** Apply the three-point scale. When uncertain between two levels, apply the higher level.

3. **Document in the evidence item record.** Add a "Conflict" field to the evidence item record with: severity rating, description of the conflict, and the basis for the rating.

4. **Apply corroboration requirements.** For Moderate severity: conduct a targeted search for unconflicted corroboration. Document the search and its outcome. For High severity: corroboration is required; if not found, initiate the confidence reduction and limitation documentation requirements.

5. **Adjust confidence.** Apply the confidence reduction for the severity level. The reduction applies to the claim component supported by the conflicted evidence, not to the whole claim unless the conflict is pervasive.

6. **Document in the reasoning chain.** For Moderate and High conflicts, include a step in the reasoning chain that explicitly acknowledges the conflict and explains why the evidence was used despite it.

---

### Evidence Requirements

- Documentation of the source's conflict, including the nature and severity of the relationship
- For Moderate: documentation of corroboration search and its outcome
- For High: corroboration from an unconflicted source, or explicit documentation of why the conflicted evidence is credible despite the conflict

---

### Verification Criteria

- Every evidence item from a source with any conflict has a documented conflict severity rating in the evidence item record
- For Moderate and High severity items, the corroboration requirement has been met or explicitly documented as unmet with explanation
- The confidence rating reflects adjustments for conflict severity as specified
- High-severity conflicts are disclosed in the claim statement, not only in the evidence item record

---

### Consequences

**Benefits:**
- Evidence from conflicted sources is not discarded, preserving information that may be accurate and valuable.
- Conflicts are visible to downstream users and verifiers, enabling informed judgment about their significance.
- The graded approach prevents both dismissal and uncritical acceptance of conflicted evidence.

**Liabilities:**
- Conflict severity rating involves judgment; the same source may be rated differently by different practitioners.
- The corroboration requirement for High-severity evidence can be resource-intensive when unconflicted sources are scarce.
- Disclosing conflicts prominently may make a claim appear weaker than it is when the conflicted evidence is actually accurate.

---

### Known Uses

- **Policy research team, public health agency (2025):** Applied to a claim about a pharmaceutical intervention where all available clinical trials were industry-funded. Three trials were rated High severity; one was rated Moderate. The team documented the conflict for all four, conducted a systematic search for unconflicted corroboration (none found), applied the confidence reduction, and disclosed the limitation in the claim statement. The disclosure was cited favorably in subsequent regulatory review as evidence of epistemic integrity.
- **Competitive intelligence function, technology firm (2025):** Applied to benchmark evidence produced by a competitor. Rated High severity; corroborated with independent testing. The independent test results agreed with the competitor's benchmark on three of five dimensions, providing partial corroboration with documented scope.

---

### Related Patterns

- [VERA-P-0001](./evidence.md#vera-p-0001) — Absence-of-Evidence Assessment: Use when corroboration search (Step 4) finds no unconflicted sources; the absence of corroboration has its own materiality that must be assessed.
- [VERA-P-0004](./evidence.md#vera-p-0004) — Source Collapse Detection: Use alongside P-0002 when multiple conflicted sources are suspected to derive from the same underlying data.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0002 |
| Confidence | 0.84 |

---

<a id="vera-p-0003"></a>
## VERA-P-0003 — AI-Generated Evidence Documentation

**Pattern ID:** VERA-P-0003

| Field | Value |
|-------|-------|
| Domain | Evidence |
| Applicability | All |
| Complexity | Moderate |
| Maturity Level | 2 |

---

### Context

Practitioners increasingly use AI systems — large language models, AI-powered search tools, document summarization systems, and analysis platforms — at every stage of evidence work: to identify relevant sources, to summarize large bodies of literature, to extract key claims from documents, and to synthesize evidence across multiple sources. AI tools can dramatically accelerate evidence work. They also introduce chain-of-custody and quality-rating challenges that the standard evidence framework does not directly address.

The core problem is that AI output is a transformation of sources, not a source itself. When an AI system produces a summary of ten studies, that summary is not a Secondary-tier evidence item — it is a machine-generated interpretation of Secondary sources. When an AI retrieves what it describes as a quotation from a document, that quotation may or may not accurately reflect the original. The chain between AI output and primary source is opaque by default.

This pattern applies whenever an AI system has meaningfully shaped the evidence in a VERA claim — whether by finding it, summarizing it, synthesizing it, or generating it.

---

### Problem

Evidence retrieved, summarized, or synthesized by AI systems cannot be quality-rated using the standard four-tier scale without modification. The AI output is not Primary evidence (it is not firsthand observation or original data), not Secondary (it is not peer-reviewed expert interpretation), not Tertiary (it is not an editorially curated synthesis), and not precisely Testimonial (the AI is not a human expert). Yet practitioners frequently cite AI outputs as if they were one of these types, or — more problematically — cite them without noting the AI provenance at all.

---

### Forces

- AI tools genuinely accelerate evidence discovery and synthesis; prohibiting their use would impose disproportionate costs.
- Citing "the AI said" as an evidence item violates chain-of-custody requirements; the AI is not a source.
- The underlying sources an AI references often exist and can be retrieved — but doing so for every AI-mediated evidence item is costly.
- AI systems can hallucinate sources, misattribute quotations, and misrepresent the findings of real studies. Human verification of AI claims is not optional.
- Different AI systems have different reliability characteristics; the system identity and version are relevant to the chain-of-custody assessment.
- The prompter's framing influences what the AI finds and how it summarizes; the prompt is part of the chain of custody.

---

### Solution

Apply a **three-tier handling protocol** based on whether the underlying primary source can be retrieved and independently verified.

**Tier A: Source Retrieved and Verified**

The AI identified the evidence; the practitioner retrieved and directly examined the original source.

- Create the evidence item record for the **original source**, not the AI output.
- Note in the chain-of-custody field: "Source identified by [AI system, version, date]. Original source retrieved and verified by [practitioner] on [date]."
- Apply the standard quality tier rating to the original source.
- The AI's role is discovery assistance; it does not affect the quality tier of the original source.

**Tier B: Source Identified but Not Retrievable**

The AI cited a source that the practitioner attempted but failed to retrieve (paywalled, deleted, or possibly hallucinated).

- Create an evidence item record for the AI output with the following fields:
  - **Type:** AI-Mediated (Unverified) — not a standard quality tier
  - **AI System:** [Name, version, date]
  - **Prompt:** [Verbatim or summarized prompt that produced this output]
  - **Output:** [Verbatim AI output]
  - **Retrieval attempt:** [What was done to locate the original source, and why it failed]
- Apply a **mandatory confidence penalty** of 0.15 to any claim component supported only by Tier B evidence.
- Tier B evidence cannot be used as the sole support for a claim component at Verification criteria E2 (Evidence Quality Adequacy).

**Tier C: AI-Synthesized Analysis (No Specific Source)**

The AI generated analytical content — synthesis, interpretation, pattern identification — that does not correspond to a specific retrievable source.

- Treat as **Testimonial tier** with the AI system as the "expert."
- Document: AI system, version, date, prompt (verbatim), and the complete output used.
- Note in the evidence item record that the "expert" is an AI system, with its known limitations.
- Apply all Testimonial-tier evidence requirements.
- AI Testimonial evidence carries an inherent independence limitation: the same AI system queried multiple times about the same topic is not independent.

---

### Implementation

1. **Inventory AI involvement.** Before finalizing the evidence set, identify every evidence item where AI played a role in discovery, retrieval, summarization, or synthesis.

2. **Classify each AI-involved item.** For each item, determine whether it is Tier A (source retrieved), Tier B (source identified but not retrievable), or Tier C (AI synthesis without specific source).

3. **Document AI provenance.** For all three tiers, record: AI system name, version or model identifier, date of query, and the verbatim prompt (or, if the prompt is long, a summary that would allow reconstruction of the query).

4. **Retrieve original sources (Tier A work).** For all Tier B items, make at least one genuine attempt to retrieve the underlying source before accepting Tier B status. Document the attempt.

5. **Apply quality ratings.** Tier A: use the original source's quality tier. Tier B: document as AI-Mediated (Unverified). Tier C: document as Testimonial (AI).

6. **Apply confidence adjustments.** Tier B items trigger the 0.15 confidence penalty per claim component. Tier C items are subject to standard Testimonial-tier confidence assessment.

7. **Flag in the reasoning chain.** For Tier B and Tier C evidence items, include an explicit note in the reasoning chain step that uses them, identifying the AI provenance and the epistemic limitation it creates.

---

### Evidence Requirements

- AI system identity, version, and query date for all AI-involved evidence items
- Verbatim prompts for all Tier B and Tier C items; verbatim prompts or reconstruction-sufficient summaries for Tier A items
- Documentation of retrieval attempts for all Tier B items
- Complete verbatim AI output for all Tier B and Tier C items used as evidence

---

### Verification Criteria

- No evidence item in the claim's evidence set is cited as Primary, Secondary, or Tertiary when the practitioner did not directly access the original source — AI-mediated discovery alone does not constitute direct access.
- All Tier B and Tier C evidence items are documented with AI provenance fields.
- The confidence rating reflects the 0.15 penalty for Tier B evidence and the Testimonial-tier calibration for Tier C evidence.
- No Tier B evidence item is the sole support for a claim component (criterion E2 violation).

---

### Consequences

**Benefits:**
- AI tools can be used without compromising chain-of-custody requirements.
- The three-tier system preserves the value of AI discovery work while requiring human verification of AI claims.
- Downstream users and verifiers can assess the epistemic weight of AI-mediated evidence.

**Liabilities:**
- Tier A retrieval for all AI-discovered evidence is time-intensive; the acceleration benefit of AI discovery is partly offset by verification costs.
- The prompt-capture requirement adds documentation overhead to AI-assisted research workflows.
- AI system versioning is inconsistent; identifying the model and version used may not be possible in all tools.

---

### Known Uses

- **Research team, management consulting firm (2025):** Developed an internal prompt logging tool after applying this pattern; Tier B rates dropped from ~40% to ~12% as practitioners built habits of clicking through to original sources before closing AI sessions.
- **Policy analyst, government research office (2025):** Applied Tier C to AI-generated synthesis of legislative history; noted that three queries to the same AI produced partially inconsistent syntheses, confirming the independence limitation; used the inconsistency itself as a Tier B evidence item about the claim's uncertainty.

---

### Related Patterns

- [VERA-P-0002](./evidence.md#vera-p-0002) — Conflicted Source Disclosure: AI systems trained on biased corpora may exhibit systematic conflicts; applies when AI provenance suggests directional bias.
- [VERA-P-0007](./reasoning.md#vera-p-0007) — Hidden Assumption Excavation: AI-generated reasoning chains typically contain hidden assumptions; apply P-0007 to any AI-generated reasoning used in a VERA claim.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0003 |
| Confidence | 0.86 |

---

<a id="vera-p-0004"></a>
## VERA-P-0004 — Source Collapse Detection and Remediation

**Pattern ID:** VERA-P-0004

| Field | Value |
|-------|-------|
| Domain | Evidence |
| Applicability | All |
| Complexity | Simple |
| Maturity Level | 2 |

---

### Context

Evidence sets assembled from multiple sources frequently contain items that appear independent but ultimately derive from the same underlying source. This is especially common in domains dominated by a small number of authoritative primary sources — a single landmark study that spawned many secondary analyses, a single regulatory document that multiple organizations reference, a single dataset that multiple publications draw from.

The [Lexicon](../foundations/lexicon.md#evidence-independence) defines this error as **source collapse** and defines the Independence assessment as a required part of evidence set assembly (Verification Protocol Step 2.4). This pattern specifies *how* to conduct that assessment systematically, and how to remediate collapse when it is found.

---

### Problem

When multiple evidence items in a set trace to the same underlying source, the evidence set overstates the degree of independent support for the claim. A practitioner who assembles five evidence items all derived from the same original study believes they have built a robust multi-source case; they have built a single-source case with decorative citations. Verification criterion E3 (Independence Adequacy) will catch this — but only if the verifier knows to look for it and has a method for detecting it.

---

### Forces

- Source collapse often occurs innocuously: different publications genuinely cite the same study as the best available evidence, making independent citation count unreliable as an independence signal.
- Detecting source collapse requires backward-tracing each evidence item through its citation chain, which is time-consuming.
- Consolidated evidence sets have fewer items, which may superficially appear weaker even when the consolidation more accurately represents the independent support.
- True independence is sometimes impossible to achieve in domains where a single primary source exists; this must be documented rather than hidden.

---

### Solution

Conduct an **evidence source tree** for any evidence set containing four or more items, or when any subset of items appears to address the same claim component from what may be related sources.

The source tree maps each evidence item backward to its ultimate origin: the original dataset, study, document, or observation. Items that share an ultimate origin are **source-collapsed** and must be consolidated.

---

### Implementation

1. **Trigger assessment.** Apply this pattern whenever: (a) the evidence set has four or more items, (b) two or more items reference the same study or dataset, or (c) verification criterion E3 is flagged during review.

2. **Build the source tree.** For each evidence item, trace its citations backward:
   - What does this item cite as its primary source?
   - What does *that* source cite?
   - Continue until you reach an item with no further citations — a direct observation, original dataset, or primary document.
   - Record the ultimate source for each evidence item.

3. **Identify shared roots.** Group evidence items that share the same ultimate source.

4. **Apply the independence classification.** Within each group:
   - If items independently transform or interpret the shared source in meaningfully different ways, classify as **Correlated** (keep all items, note the shared root).
   - If items are essentially transmissions of the same content from the same source, classify as **Dependent** (consolidate into one item).

5. **Consolidate Dependent items.** Replace the group of dependent items with a single evidence item representing the underlying source, with a note: "N items in the original evidence set were consolidated; all derived from [source]."

6. **Recount independent sources.** After consolidation, record the true count of independent evidence items and the count of correlated items. This true count is used in the confidence assessment.

7. **Document in the evidence set.** Record the source tree as an appendix to the evidence set documentation. Any verifier can then reproduce the independence assessment without repeating the full trace.

---

### Evidence Requirements

- The citation chain for each evidence item, traced to its ultimate source
- Documentation of the independence classification for each item
- The consolidation record showing which items were merged and why

---

### Verification Criteria

- A source tree exists for evidence sets of four or more items
- All evidence items have an ultimate source identified
- No evidence item is classified as Independent when its ultimate source is shared with another item in the set
- The confidence rating is calculated from the consolidated (true) independent source count, not the raw item count

---

### Consequences

**Benefits:**
- Eliminates a systematic form of confidence inflation.
- Makes the true evidential basis of a claim visible and auditable.
- Reduces evidence sets to their genuine information content, making reasoning chains cleaner.

**Liabilities:**
- Source tracing is time-intensive for evidence items with long citation chains.
- Consolidation visibly reduces evidence set size, which can create internal resistance if practitioners believe "more sources = stronger claim."
- In some domains, consolidation reveals that a widely-held claim rests on a single primary source — a finding that is uncomfortable but epistemically important.

---

### Known Uses

- **Internal audit team, financial institution (2025):** Applied to a claim about regulatory compliance that cited eight secondary sources; source tree revealed all eight derived from two primary regulatory interpretations; consolidated to two items and revised confidence downward, prompting additional primary-source research.
- **Academic researcher, social sciences (2024):** Applied during systematic review construction; identified that a meta-analysis included fifteen papers drawing from the same longitudinal dataset, counted as fifteen independent data points in the original review's analysis.

---

### Related Patterns

- [VERA-P-0001](./evidence.md#vera-p-0001) — Absence-of-Evidence Assessment: Use when source collapse remediation reveals that a claim component has fewer independent sources than expected; the reduced count may reach the threshold for Significant absence.
- [VERA-P-0002](./evidence.md#vera-p-0002) — Conflicted Source Disclosure: Source collapse and conflict of interest frequently co-occur when an industry produces or funds the dominant primary sources in a domain.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0004 |
| Confidence | 0.91 |

---

<a id="vera-p-0005"></a>
## VERA-P-0005 — Time-Sensitive Evidence Management

**Pattern ID:** VERA-P-0005

| Field | Value |
|-------|-------|
| Domain | Evidence |
| Applicability | All |
| Complexity | Moderate |
| Maturity Level | 3 |

---

### Context

Claims in many domains are supported by evidence that changes in reliability over time. Regulatory approval status changes. Market data becomes stale. Living clinical guidelines are updated. Organizational policies are superseded. Technology benchmarks are invalidated by new releases. An evidence item that was Primary-tier and current at time of assembly may be Secondary-tier or effectively misleading six months later.

The Verification Protocol establishes review cadences at the **claim level** (Phase 5, Step 5.4), specifying how frequently the whole claim should be reviewed. This claim-level cadence is insufficient when different evidence items within the same claim decay at different rates: a claim about market conditions might have some evidence (a regulatory ruling) that is stable for years and other evidence (a pricing dataset) that becomes stale in weeks.

---

### Problem

Standard claim-level review cadences do not account for evidence-level decay. A claim reviewed on schedule may still be supporting decisions with stale evidence if some items in its evidence set have become unreliable between reviews. Conversely, practitioners who flag all evidence as time-sensitive create review burdens disproportionate to actual epistemic risk.

---

### Forces

- Evidence decay rates vary by source type and domain; one-size-fits-all cadences either over-burden or under-protect.
- Notifying downstream claims when upstream evidence becomes stale requires active monitoring infrastructure not available at all maturity levels.
- The boundary between "stale" and "superseded" is not always clear; stale evidence may still be directionally correct.
- Practitioners in rapidly changing domains face continuous evidence churn; alert fatigue is a real risk if the system triggers too frequently.

---

### Solution

Annotate each evidence item with an **evidence decay class** and associated **expiry date** at the time of evidence set assembly. Link evidence expiry to automatic claim review triggers.

**Evidence Decay Classes:**

| Class | Description | Default expiry window | Examples |
|-------|-------------|----------------------|---------|
| **Stable** | Evidence is not expected to change materially | 36 months | Historical records, mathematical proofs, long-established scientific consensus, statutory text |
| **Drifting** | Evidence may change gradually; periodic verification needed | 12 months | Policy documents, organizational standards, expert consensus guidelines, established market structures |
| **Volatile** | Evidence changes frequently; continuous monitoring required | 3 months | Market prices, regulatory approval status, software version specifics, living guidelines, survey data |

Practitioners may override the default expiry window with a documented rationale. The override must be conservative (shorter, not longer) unless there is specific justification for extending it.

---

### Implementation

1. **Assign decay class at assembly.** For each evidence item, assign a decay class (Stable / Drifting / Volatile) and calculate the expiry date (assembly date + default window, or override date with rationale).

2. **Record expiry in evidence item documentation.** Add an "Expiry" field to each evidence item record: decay class, expiry date, and monitoring method.

3. **Set monitoring for Volatile items.** For each Volatile evidence item, establish an active monitoring method: a saved search, a regulatory alert subscription, a calendar reminder for manual check-in. Document the method.

4. **Link expiry to claim review triggers.** The claim's effective review date is the earliest expiry date across all evidence items with a decay class of Volatile or Drifting. This may be earlier than the claim-level review cadence established in Verification Protocol Phase 5.

5. **Handle expiry events.** When an evidence item reaches its expiry date:
   - Check whether the source has changed.
   - If unchanged: update the expiry date for the next window; note the reconfirmation in the evidence item record.
   - If changed: assess the impact on the claim. Update the evidence item or replace it. Reassess verification state. Notify downstream claims via [VERA-P-0012](./verification.md#vera-p-0012).

6. **Mark stale items.** An evidence item that has passed its expiry date without a reconfirmation check is marked **Stale**. Claims with Stale evidence items are marked **Stale** and should not be used in reasoning chains without re-verification.

---

### Evidence Requirements

- Decay class assignment for each evidence item, with documented rationale for any override of the default window
- Monitoring method documented for all Volatile evidence items
- Reconfirmation records for evidence items that have been refreshed at least once

---

### Verification Criteria

- Every evidence item in the set has an assigned decay class and expiry date
- No evidence item is Stale (past expiry without reconfirmation) at the time of verification
- The claim's effective review trigger reflects the earliest expiry date in the evidence set, not only the claim-level cadence
- Monitoring methods for Volatile items are documented and plausibly executable

---

### Consequences

**Benefits:**
- Evidence-level tracking prevents claims from becoming supported by stale evidence between claim-level reviews.
- The decay class system calibrates monitoring effort to actual risk, reducing alert fatigue.
- Expiry tracking provides an automatic early-warning system for downstream claims.

**Liabilities:**
- Adds annotation work at evidence assembly time.
- Volatile evidence monitoring requires active infrastructure (alerts, saved searches) that must be maintained.
- Determining the correct decay class for novel evidence types involves judgment; practitioners may systematically underestimate volatility in unfamiliar domains.

---

### Known Uses

- **Research function, global consulting firm (2025):** Implemented evidence expiry as part of their claim registry tooling after discovering three active claims were being cited in client deliverables with market data that was 18 months old. The tooling flagged 23 evidence items as Stale in the first month of implementation.
- **Regulatory affairs team, pharmaceutical company (2025):** Applied to a claim about competitor approval status; Volatile classification with 3-month expiry triggered a reconfirmation check that caught a label modification, allowing a filing to be updated before submission.

---

### Related Patterns

- [VERA-P-0001](./evidence.md#vera-p-0001) — Absence-of-Evidence Assessment: When evidence becomes stale and no current replacement is found, treat the absent current evidence using P-0001 materiality assessment.
- [VERA-P-0012](./verification.md#vera-p-0012) — Cascading Claim Update: Use to notify and re-evaluate downstream claims when Volatile evidence changes force a claim to a new verification state.

---

**Verification Status:**

| Field | Value |
|-------|-------|
| State | Verified |
| Verifier | VERA Founding Review |
| Verified on | 2026-02-21 |
| Record | VERA-V-0005 |
| Confidence | 0.82 |
