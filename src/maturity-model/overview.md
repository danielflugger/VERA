# Overview: Five Levels × Six Domains

The VERA Maturity Model is a structured framework for assessing and developing an organization's or individual's capability to apply VERA practices systematically. It answers two questions: *Where are we now?* and *What does meaningful progress look like?*

The model is organized as a grid: five levels of capability on one axis, six domains of practice on the other. Every cell in the grid describes observable, concrete indicators — not aspirations, not general principles, but the specific things that are present or absent at a given level in a given domain.

---

## Why This Structure

### Five Levels, Not More or Fewer

Three-level models (basic / intermediate / advanced) are too coarse to guide development. They map onto each other easily in conversation but provide no traction when you ask: "What exactly do we need to do to move from intermediate to advanced?"

Seven- or ten-level models provide granularity at the cost of usability. Most organizations cannot meaningfully distinguish between adjacent levels, and the cognitive overhead of the model begins to compete with the practice it describes.

Five levels is the calibration point where each level is genuinely distinct, the transitions between levels are actionable, and the model is small enough to hold in working memory. VERA's five levels draw directly from this reasoning and from the track record of CMMI, which settled on the same number for the same reasons.

### Six Domains, Not One

A single overall maturity score conceals more than it reveals. Organizations routinely develop sophisticated Evidence practices while their Governance domain remains informal. Excellent Verification processes coexist with Sovereignty gaps that undermine the value of that verification. A composite score averaging across these domains would suggest moderate overall maturity while hiding the specific strengths and vulnerabilities that actually determine outcomes.

The six domains were chosen to cover the full VERA lifecycle — from raw evidence to governed, sovereign practice — with minimal overlap and maximal diagnostic value.

---

## The Six Domains

### 1. Evidence

The Evidence domain measures how well an organization identifies, retrieves, rates, documents, and maintains the evidence items that underlie its claims. It covers the entire evidence lifecycle: prospective search planning, quality rating, independence assessment, chain-of-custody documentation, absent-evidence recording, and long-term accessibility.

The Evidence domain is foundational. Weaknesses here propagate forward into every other domain — you cannot reason well from undocumented evidence, you cannot verify claims whose evidence is inaccessible, and you cannot be sovereign over knowledge you cannot audit.

### 2. Reasoning

The Reasoning domain measures how explicitly and rigorously an organization constructs the logical connection between evidence and conclusion. It covers reasoning chain documentation, inference type labeling, assumption disclosure, completeness, and the organizational practices (review, training, peer critique) that maintain reasoning quality over time.

Reasoning quality is the most cognitively demanding domain to develop. Most organizations have strong intuitions about what "good reasoning" looks like but significant difficulty making those intuitions explicit enough to be taught, reviewed, and improved systematically.

### 3. Verification

The Verification domain measures how consistently and rigorously claims are evaluated against the Verification Protocol, how well the verification process maintains independence, how records are kept, and how contested and refuted claims are managed. It also covers the feedback loop from verification back into claim and reasoning quality.

Verification is where VERA's epistemic commitments meet organizational reality most directly. A team that documents claims carefully but never verifies them has built good habits that produce unreliable results. Verification closes the loop.

### 4. Governance

The Governance domain measures whether and how VERA practice is institutionalized — mandated, resourced, trained, audited, and improved at an organizational level. Governance is the difference between VERA as a personal practice of a few motivated individuals and VERA as an organizational capability that persists through personnel changes and competing priorities.

Governance typically lags the other domains by one or two levels. Organizations often reach Level 3 Practice in Evidence, Reasoning, and Verification through the efforts of motivated champions, only to find that the practices don't scale or survive when those champions move on. The Governance domain explicitly tracks this lag.

### 5. Sovereignty

The Sovereignty domain measures how fully the five [Sovereignty Principles](../foundations/sovereignty-principles.md) are implemented in practice. It covers data accessibility and exportability, reasoning chain traceability and challengeability, conclusion sovereignty, process auditability, and temporal sovereignty.

Sovereignty is the most distinctive VERA domain — it has no direct equivalent in most organizational capability frameworks. It explicitly asks: does your VERA implementation preserve the epistemic authority of the people whose decisions depend on it, or does it create new dependencies while eliminating old ones?

### 6. Integration

The Integration domain measures how fully VERA practices are embedded in the organization's existing workflows, tools, and processes — rather than sitting alongside them as a parallel overhead. Integration measures whether VERA is something people do instead of their work, or something that shapes how they do their work.

Integration is typically the last domain to mature, and appropriately so. It doesn't make sense to integrate VERA into organizational workflows before those workflows are mature enough to sustain it. But at Level 4 and 5, insufficient Integration becomes a significant drag: sophisticated VERA practice that is disconnected from decision-making processes, reporting structures, and tool ecosystems produces knowledge that doesn't reach the people who need it.

---

## The Five Levels

### Level 1 — Aware

VERA concepts are understood. Practitioners can describe the difference between an assertion and a claim, explain why evidence quality matters, and articulate the purpose of verification. What does not yet exist is systematic practice: no claims are formally documented, no evidence sets are assembled, no verification records are kept.

Awareness is not a trivial achievement. Many organizations operate at Level 0 — below Aware — where VERA concepts are entirely unknown and epistemic quality is managed (or not) through informal organizational culture. Level 1 represents genuine understanding; the gap to Level 2 is one of habit and process, not comprehension.

### Level 2 — Exploring

VERA is being applied to selected claims, inconsistently and without institutional mandate. Practice depends on motivated individuals. The quality of VERA work at Level 2 varies significantly — a practitioner who has internalized the Verification Protocol produces genuinely useful documented claims; a practitioner who has only skimmed the framework produces documentation that has VERA's form without its substance.

Level 2 is valuable and should not be skipped. The experience of applying VERA to real claims — discovering what "prospective search plan" actually means in practice, encountering genuine evidence quality dilemmas, struggling with the first reasoning chain — is irreplaceable preparation for Level 3. Teams that try to jump directly to Level 3 institutionalization without Level 2 experience tend to institutionalize the wrong things.

### Level 3 — Practicing

VERA is applied systematically to all significant claims. The practice is reproducible — it does not depend on which practitioner is working on a given claim — and results are auditable. Anyone in the organization can locate a claim, find its evidence set and reasoning chain, and understand the verification state and confidence rating. Level 3 is the **primary target for most organizations**. It delivers the core VERA value proposition — traceable, verifiable reasoning — without the organizational investment that Levels 4 and 5 require.

### Level 4 — Governing

VERA practices are institutionalized, measured, and subject to continuous improvement. A governance function exists that takes responsibility for VERA quality across the organization. Metrics are tracked, trends are analyzed, and the quality of VERA work is treated as a managed organizational capability — like code quality or security posture — rather than an individual responsibility.

Level 4 is appropriate for organizations for whom epistemic quality is strategically important: research institutions, policy-making bodies, organizations in regulated industries, and those whose reputation depends on the quality of their public claims.

### Level 5 — Sovereign

Full epistemic sovereignty is achieved across all five Sovereignty Principles. The VERA framework itself is subject to VERA-style review. The organization actively contributes to the broader VERA knowledge commons. Level 5 is both an organizational achievement and a responsibility: organizations at this level have the capability and the obligation to improve the framework for others.

---

## The 5×6 Grid

The following grid summarizes the state of each domain at each level. Individual level chapters provide the full detail behind each cell.

| Domain | L1: Aware | L2: Exploring | L3: Practicing | L4: Governing | L5: Sovereign |
|--------|-----------|---------------|----------------|---------------|---------------|
| **Evidence** | Quality tiers understood conceptually; no ratings applied | Evidence rated for selected claims; informal search plans; inconsistent documentation | All significant claims have rated evidence sets; prospective search plans documented before search; absent evidence recorded | Evidence quality metrics tracked; trusted source library maintained; quality trends reviewed | Full data sovereignty: all evidence accessible, exportable, with documented chain of custody; evidence infrastructure audited |
| **Reasoning** | Distinction between assertion and reasoning chain is understood | Reasoning chains written for some claims; informal format; inference types not labeled | All significant claims have step-by-step reasoning chains; inference types labeled; assumptions documented | Reasoning quality assessed against criteria; common gaps tracked; peer reasoning review is routine | Reasoning chains institutionally owned and auditable; AI-assisted reasoning systematically documented; reasoning quality measured in aggregate |
| **Verification** | Verification concept understood; not distinguished from agreement | Ad hoc verification; verifier often the claimant; informal criteria | Verification Protocol applied consistently; independence assessed; verification records created for all significant claims | Verification quality measured (pass rates, contested rate, time-to-verify); verifier pool managed; criteria reviewed | Verification process auditable externally; criteria publicly documented; challenge process active and produces changed outcomes |
| **Governance** | VERA known to key staff; no mandate or structure | Informal champion; no budget, policy, or formal mandate | VERA is policy for significant claims; ownership clear; documentation requirements enforced | Governance committee or equivalent; metrics reviewed on cadence; budget allocated; VERA in onboarding | Governance function evaluates itself using VERA methods; organization contributes to community; VERA is leadership-level accountability |
| **Sovereignty** | Sovereignty concept understood; no assessment conducted | Informal awareness of gaps; S1 partially addressed for highest-priority claims | Full sovereignty assessment complete; all five principles rated; gaps documented with remediation plan | Sovereignty gaps remediated on schedule; vendor dependencies managed; AI tool sovereignty assessed | All five principles fully met; sovereignty assessment is continuous; sovereignty is board-level accountability |
| **Integration** | VERA seen as separate from existing work | VERA applied alongside existing tools as personal practice; not embedded in workflows | VERA notation in common tools; claims registry accessible and used; VERA visible in knowledge artifacts | VERA integrated into decision gates, reporting, and project management; VERA metrics in governance reporting | VERA is the epistemic layer of the organization; all significant knowledge work is VERA-native |

---

## How to Self-Assess

Self-assessment using the Maturity Model produces a **profile** — a level rating for each domain — rather than a single score. The profile reveals both strengths and gaps.

### Assessment Process

**Step 1: Domain-by-domain review.** For each of the six domains, read the level descriptions in the individual level chapters and identify the highest level at which *all* indicators are present. A domain is at Level N only if Level N indicators are met; partial Level N means Level N-1.

**Step 2: Evidence before judgment.** The self-assessment must be grounded in evidence — specific, recent examples of actual practice — not general impressions or aspirations. "We generally try to document evidence" is not evidence of Level 3 Evidence practice. A specific claim record showing a prospective search plan, rated evidence items, and documented absent evidence is.

**Step 3: Independent review.** Self-assessment has an inherent optimism bias. At minimum, have someone outside the immediate team review the evidence you're using to justify each level. At Level 4, external review is expected.

**Step 4: Document the assessment.** The assessment itself is a VERA claim: it should have an evidence set (the specific practice examples) and a reasoning chain (how those examples justify each level rating). An assessment that cannot be substantiated with specific examples is an aspiration, not an assessment.

### Common Assessment Errors

**Averaging across team members.** If some practitioners in a team are at Level 3 and others are at Level 1, the team is at Level 1. Domain levels describe the *floor* of consistent practice, not the average.

**Conflating understanding with practice.** Knowing what good Evidence practice looks like, being able to describe the Verification Protocol, or having attended VERA training are Level 1 indicators. They do not constitute Level 2 or 3 practice, however fluently they can be articulated.

**Selecting best examples.** The evidence for a level assessment must be representative, not cherry-picked. If your best claim record shows Level 3 Evidence practice but 80% of your claims have no evidence ratings at all, you are at Level 2.

---

## Common Trajectories

Different types of organizations tend to follow recognizable patterns across the domain profile:

**Research-first trajectory**: Evidence and Reasoning develop quickly; Governance and Integration lag. Common in academic and analytical contexts where epistemic quality is culturally valued but institutional formality is resisted.

**Compliance-first trajectory**: Governance and Verification develop before Evidence and Reasoning, because documentation requirements precede the substance that documentation should capture. Common in regulated industries. Results in formal VERA compliance without epistemic depth; requires deliberate remediation of the substance gaps.

**Champion-then-scale trajectory**: Evidence, Reasoning, and Verification reach Level 3 through the efforts of motivated individuals; Governance remains at Level 2. The organization then faces a scale problem: the practices exist but are fragile. Governance investment is needed but feels unnecessary when everything is working.

**Sovereignty-delayed trajectory**: All domains reach Level 3 while Sovereignty remains at Level 1 or 2. Common when VERA is implemented using hosted tools or proprietary platforms without auditing the sovereignty implications. A sovereignty gap at Level 3 is relatively easy to remediate; at Level 4, dependencies have typically deepened.

---

## Domain Interdependencies

Some domain transitions depend on progress in other domains:

- **Governance (L3) requires** at least Evidence and Reasoning at L2, so there is something substantive to mandate.
- **Sovereignty (L3) requires** Evidence at L3, because the sovereignty assessment cannot be meaningful if evidence documentation is incomplete.
- **Integration (L3) requires** Verification at L2, because integrating unverified claims into organizational workflows propagates uncontrolled assertions.
- **Level 4 in any domain requires** Governance at L3, because measurement and improvement at the domain level cannot be sustained without organizational mandate.
- **Level 5 in any domain requires** Sovereignty at L4, because an organization that has not achieved operational sovereignty cannot credibly claim epistemic sovereignty in any specific domain.

These dependencies do not prevent development from happening in parallel. They mean that certain level transitions will be blocked until prerequisite conditions are met.

---

*Read the individual level chapters for full detail on what each level looks like in practice, what moves you to the next level, and how to self-assess against observable indicators.*
