# Tooling & Integration

VERA does not require specialized software. It requires that whatever tools you use can satisfy a small set of structural requirements derived from the framework's sovereignty principles. This chapter describes those requirements, maps them to common tool categories, and gives concrete guidance for building a VERA workspace in the tools most practitioners already use.

---

## What VERA Requires of Tools

Before evaluating any specific tool, establish the requirements. These are derived directly from the [Sovereignty Principles](../foundations/sovereignty-principles.md) and the practical needs of the Verification Protocol.

### Non-Negotiable Requirements (All Maturity Levels)

**R1 — Writeable and searchable.** You must be able to create structured documents, add fields, and search across your claim records. A tool that only allows reading or that provides no search is inadequate.

**R2 — Exportable.** You must be able to export all your claim records, evidence documentation, and verification records in a non-proprietary format (plain text, Markdown, CSV, or similar). If you cannot export your data, you do not own it. This requirement flows directly from S1 (Data Sovereignty).

**R3 — Linkable.** Claims reference evidence items, evidence items reference sources, verification records reference claims. Your tooling must support this linking — at minimum by allowing you to include a reference ID or URL in a field.

**R4 — Durable.** Your claim records must persist. A tool that deletes data after inactivity, that regularly loses history, or whose longevity is uncertain is not appropriate for VERA's registry function.

**R5 — Accessible to stakeholders.** Claim records and verification records must be accessible to the people affected by the claims they document. A tool that only the claimant can access violates S2 (Reasoning Sovereignty).

### Requirements at Level 3 and Above

**R6 — Registry capable.** At Level 3, the claim registry must support: filtering by verification state, sorting by date, searching by claim content, and indicating ownership and review dates. A flat file cannot do this; a structured table or database can.

**R7 — Dependency trackable.** At Level 3, upstream claim dependencies must be registered at claim creation. Your tooling must be able to represent a "this claim uses Claim X as evidence" relationship.

**R8 — Auditable history.** At Level 4 and above, verification records and claim state changes must have an auditable history — who changed what, when. Version history in a wiki or document system meets this requirement.

### What to Avoid

**Proprietary-only formats.** If your claim records can only be read in one vendor's application, you have a Data Sovereignty problem. Accept proprietary tooling only when export to a non-proprietary format is available and tested.

**Single-point-of-failure storage.** Claims stored only in a local application on one device, or only in an account with no recovery path, are at risk. Mirror important claims in at least two locations.

**Reasoning-opaque tools.** Tools that produce conclusions — summaries, recommendations, classifications — without exposing the reasoning that produced them violate R3 (Reasoning Sovereignty) when that reasoning is incorporated into VERA claims without documentation. This includes AI tools used in a black-box mode.

---

## The Minimum Viable Toolkit

You need exactly three capabilities to begin VERA practice:

1. **A writing environment** where you can create and edit structured documents
2. **A claim registry** where you can list all documented claims with their key fields
3. **A file or folder system** where you can store evidence item references and verification records

These three capabilities can be satisfied by a single folder of plain text files, a spreadsheet, or any modern note-taking application. The choice of tool is less important than the discipline of using it consistently.

The minimum viable toolkit for a solo practitioner:
- **Writing:** Any text editor or word processor (including Markdown editors, Google Docs, Microsoft Word)
- **Registry:** A single table with columns: Claim ID, Statement, Verification State, Confidence, Owner, Review Date
- **Evidence storage:** A folder (local or cloud) named by claim ID, containing evidence documents and the verification record

This toolkit meets R1 through R5. It does not fully meet R6 through R8, which is appropriate — those requirements are for Level 3 and above.

---

## The Claim Registry in Depth

The claim registry is the most important piece of VERA infrastructure. Get it right early; it is difficult to restructure a large registry later.

### Registry Fields

The minimum fields for a functional registry:

| Field | Format | Notes |
|-------|--------|-------|
| Claim ID | `VERA-C-[YYYY]-[NNNN]` or org format | Permanent; never changes |
| Statement | One precise declarative sentence | The claim itself, not a title |
| Domain / Topic | Free text or controlled vocabulary | For filtering |
| Verification State | ○ ◐ ◑ ● ◈ ✗ | Current state |
| Confidence | 0.0–1.0 | Current rating |
| Owner | Name or role | Who maintains this claim |
| Created | Date | Phase 1 initiation date |
| Verified | Date | When verification completed |
| Review Due | Date | From Phase 5 cadence setting |
| Verification Record | ID or link | `VERA-V-[NNNN]` or URL |
| Notes | Free text | Stale flags, contestation notes, etc. |

Optional fields for Level 3+ registries:

| Field | Purpose |
|-------|---------|
| Upstream Dependencies | Comma-separated Claim IDs this claim uses as evidence |
| Downstream Dependents | Claim IDs that use this claim as evidence (auto-populated if tooling supports) |
| Evidence Set Link | URL or folder path |
| Protocol Version | The Verification Protocol version used |
| Tags | For filtering by topic, domain, project |

### Registry Implementation Options

**Spreadsheet (Google Sheets, Excel, LibreOffice Calc)**

Suitable for: Individual practitioners and small teams at Levels 1–3.

Setup: One sheet per registry. Columns as above. Use data validation for Verification State column (restrict to the six valid states). Freeze the header row. Add conditional formatting to highlight Stale claims (Review Due date passed).

Limitations: No dependency graph, no version history at the cell level (Google Sheets has basic version history), no relational links. Adequate to Level 3; starts showing constraints at Level 4.

**Notion**

Suitable for: Individual practitioners and teams at Levels 2–4.

Setup: Create a database for claims with properties corresponding to registry fields. Use Select property for Verification State. Use Relation property for Upstream Dependencies (relates to the same database). Use Date property for Review Due with reminders. Create views: one for All Claims, one filtered to In Progress (state = Pending or Partial), one sorted by Review Due date (Stale claims first).

Evidence sets: Create a second database for Evidence Items, related to Claims.

Strengths: Relation property natively supports dependency tracking (R7). Filtering and sorting meet R6. Export to Markdown or CSV meets R2.

Limitations: Notion stores data on Notion's infrastructure; verify export works regularly (R2 test). The vendor dependency is a monitored Data Sovereignty risk.

**Obsidian**

Suitable for: Individual practitioners and small teams at Levels 1–4, especially those who prefer local-first, Markdown-native tools.

Setup: Create a Vault with a `claims/` folder. Each claim is a Markdown file named by Claim ID. Use YAML frontmatter for structured fields:

```yaml
---
claim_id: VERA-C-2026-0001
statement: "Production defect rate was 35% lower in the six-month post-adoption period than in the equivalent pre-adoption period."
state: verified
confidence: 0.79
owner: DJF
created: 2026-02-21
verified: 2026-03-01
review_due: 2027-03-01
verification_record: VERA-V-0001
upstream_deps: []
---
```

Use the Dataview plugin to generate registry views from frontmatter. Example Dataview query:

````
```dataview
TABLE statement, state, confidence, review_due
FROM "claims"
WHERE state != "refuted"
SORT review_due ASC
```
````

Strengths: All data is local plain text files — maximum Data Sovereignty. No vendor dependency. Export is trivially a file copy. Markdown links support R3.

Limitations: No built-in access control for stakeholder sharing (R5 requires a separate sharing solution). Team use requires a shared sync solution (Git, Syncthing, or a cloud folder).

**Confluence (Atlassian)**

Suitable for: Teams and organizations at Levels 3–5.

Setup: Create a VERA space. Use a Confluence database (or a structured page template with properties) for the claim registry. Use page templates for claim records and verification records.

Strengths: Native to organizational knowledge management infrastructure; stakeholder access (R5) is managed through existing Confluence permissions. Audit history (R8) is built in.

Limitations: Export (R2) requires deliberate configuration; verify that page exports include structured data in a portable format, not just HTML. Confluence licensing costs may be a governance consideration.

**Plain Markdown Files with Git**

Suitable for: Technical teams at Levels 2–5 who are comfortable with version control.

Setup: A Git repository with a `/claims/` directory. Each claim is a Markdown file with YAML frontmatter (same structure as Obsidian above). Verification records live in `/verification-records/`. Evidence sets referenced by folder path or URL.

Strengths: Version history at the line level (R8) via Git log. Export is a clone. Stakeholder access via repository permissions. Dependency tracking via frontmatter fields. The entire VERA knowledge base can be reviewed, diffed, and audited using standard Git tooling.

Limitations: Requires Git literacy. No GUI registry view without additional tooling (a static site generator like mdBook can build a browsable version from the Markdown — suitable for teams already using mdBook for other documentation).

---

## Evidence Management

Evidence items need to be stored, organized, and retrievable. The core requirement is chain-of-custody: for each evidence item, you need to be able to locate the original source, trace the path from source to your documentation, and confirm that the item was what you say it was when you accessed it.

### Evidence Folder Structure

Organize evidence by claim, not by topic. Each claim has its own evidence folder:

```
evidence/
  VERA-C-2026-0001/
    E1-defect-data-pre-adoption.csv
    E2-defect-data-post-adoption.csv
    E3-deployment-log.pdf
    E4-methodology-doc.md
    evidence-set.md          ← Evidence item records with ratings and chain of custody
```

The `evidence-set.md` file is the master document for that claim's evidence, containing one Evidence Item Record per item.

### Evidence Item Record Format

```markdown
## E1: Pre-Adoption Defect Data

- **Source:** Internal incident tracking system (Jira)
- **Type:** Export
- **Quality Tier:** Primary
- **Access Date:** 2026-02-21
- **Accessed By:** DJF
- **Chain of Custody:** Exported directly from Jira filter "project = PROD AND type = Bug AND created >= 2025-05-01 AND created <= 2025-10-31" on 2026-02-21. File saved to /evidence/VERA-C-2026-0001/E1-defect-data-pre-adoption.csv.
- **Relevance:** Provides pre-adoption production defect count for Step 1 of reasoning chain.
- **Independence Classification:** Correlated with E2 (same system, different period)
- **Decay Class:** Drifting (12-month expiry: 2027-02-21)
- **Conflict:** None
```

### Handling Non-Retrievable Sources

Some evidence sources cannot be stored as local files: paywalled academic papers, licensed datasets, confidential internal documents, proprietary systems. For these, the chain-of-custody record replaces the stored file:

- Document how access was obtained (subscription, license, internal access rights)
- Describe the access method in enough detail that the same access could be repeated
- Note any risk to future access (subscription renewal, license expiration, internal system changes)

If the source is a website that may change or disappear, capture a dated archive (WebCite, archive.org, or a local PDF of the page). This is especially important for Volatile evidence items.

---

## AI Tool Integration

AI tools create specific tooling requirements beyond the general VERA requirements. These are derived from VERA-P-0003 (AI-Generated Evidence Documentation) and the Sovereignty Principles.

### Prompt Logging

Any AI interaction that produces evidence used in a VERA claim requires:
- The name and version of the AI model used
- The exact prompt (or a reconstruction-sufficient summary)
- The complete verbatim output used as evidence
- The date and time of the interaction

Most AI tools do not provide automatic logging that meets these requirements. Solutions:

**Manual logging:** Copy prompts and outputs into your evidence item records immediately after each AI session. This is the minimum viable approach.

**Session export:** Some AI platforms (including Claude's web interface) provide conversation export. Export conversations immediately after any session that produced evidence; include the export in the evidence folder.

**Prompt management tools:** Tools like Promptbase, PromptLayer, or custom prompt registries can log prompts and responses automatically for API-based AI use. If your AI use is API-based, prompt logging infrastructure is strongly recommended.

### AI Sovereignty Assessment

For each AI tool used in VERA work, assess:

1. **Reasoning transparency:** When the AI produces reasoning (not just retrieval), can you capture that reasoning in full? If the tool only shows conclusions, it is not suitable for VERA reasoning chain contribution without the Tier C (AI synthesis) handling from VERA-P-0003.

2. **Data sovereignty:** Do your prompts and the AI's responses leave your control? If they are stored on the AI provider's servers, that is a data sovereignty consideration. Evaluate whether the data contains confidential claim content that should not leave organizational control.

3. **Model identity:** Can you identify the specific model version used? Confidence in an AI's output is tied to knowing what model produced it. Tools that use unversioned or frequently updated models without notification create chain-of-custody problems.

4. **Exit path:** If you stop using the tool, can you retrieve all prompts and outputs? Test this before the tool becomes a significant part of your evidence workflow.

### AI Tools in the VERA Workflow

AI tools are most valuable — and most compatible with VERA sovereignty requirements — in these specific roles:

**Evidence discovery (Tier A work):** AI can identify sources, suggest search terms, and surface relevant literature. VERA-P-0003 Tier A applies: AI identifies; you retrieve and verify the original source.

**Claim formulation assistance:** AI can help identify compound claim structures, suggest precision improvements to claim statements, and flag potentially hidden assumptions. These outputs are practitioner inputs, not evidence — they improve Phase 1 quality without creating evidence chain-of-custody issues.

**Reasoning chain review:** AI can serve as a preliminary adversarial reviewer — attempting to identify gaps and weaknesses in a reasoning chain before formal verification. This is not VERA verification; it is a preparation tool. The practitioner evaluates the AI's critique independently.

**Registry queries:** AI with access to structured claim registry data can help practitioners find related claims, identify upstream dependencies, and surface review-due items.

AI tools are least appropriate — and require the most careful sovereignty management — when:

- They are generating conclusions that are incorporated into reasoning chains without capturing their reasoning
- They are summarizing evidence without traceability to the underlying sources
- Their outputs are cited as Secondary evidence without verification of the underlying sources

---

## Integrating VERA with Existing Workflows

### Decision Documents

The highest-value VERA integration for most organizations is making VERA verification status visible in decision documents. A decision document that supports each key factual assertion with a VERA Claim ID — rather than a verbal summary — allows decision reviewers to assess the epistemic basis of the decision without requiring them to be present for all the upstream research.

Implementation: Add a "Evidence and Verification" section to decision document templates. For each significant factual assertion in the document, include the Claim ID and current verification state. Decision reviewers who want to examine the reasoning can retrieve the full claim record from the registry.

### Meeting Notes and Action Items

Decisions made in meetings often rest on claims asserted verbally — the most epistemically fragile form of claim. The VERA integration that addresses this is simple: when a significant claim is asserted verbally in a meeting and accepted as a basis for a decision or action, someone records it as a VERA claim stub (Claim ID, statement, context) as part of the meeting notes. The stub moves into the Verification Protocol pipeline, and the action or decision is not finalized until the claim reaches at least Partial verification.

This integration is high-friction and requires team discipline. It is appropriate for high-stakes decisions; it would be disproportionate for every meeting. Define the threshold (what types of meeting decisions warrant this treatment) explicitly.

### Research and Analysis Outputs

Reports, analyses, and research documents typically contain multiple significant claims in their conclusions and recommendations sections. The VERA integration here: claim records for all significant claims in a report are produced before the report is finalized. The report document links to Claim IDs. Readers who want to evaluate the claims can access the full records; readers who trust the verification can proceed on the basis of the verification state and confidence rating.

For organizations at Level 4, this integration is standard. For organizations at Level 2, a simplified version is sufficient: list the most important three to five claims from a report in a registry entry, even if full verification records are not yet complete.

### Onboarding and Training

VERA is most effectively integrated into onboarding not as a standalone training module but as the framework through which new practitioners learn to work with claims in their specific domain. When a new practitioner joins a Level 3 organization, their first substantive work should involve completing a VERA claim (with mentoring) in their actual work area, using the organization's calibration examples and patterns library. This is more effective than completing a practice claim and then separately learning how the organization's actual work is structured.

---

## Tooling at Each Maturity Level

| Maturity Level | Claim Registry | Evidence Storage | Verification Records | Integration Points |
|---------------|---------------|-----------------|---------------------|-------------------|
| L1: Aware | None required | None required | None required | None |
| L2: Exploring | Spreadsheet or flat file table | Named folder per claim | Document per record, stored with claim | None required |
| L3: Practicing | Searchable database (Notion, Confluence, Obsidian + Dataview, or equivalent) | Structured evidence folders with Evidence Item Records | Complete records with per-criterion findings; linked to claim registry | Decision documents link to Claim IDs |
| L4: Governing | Registry with dependency tracking, state history, and review cadence alerts | Evidence items linked to reference management system; chain-of-custody auditable | Versioned records; verifier identity tracked | Decision gates, project management, governance reporting |
| L5: Sovereign | Registry is fully exported and sovereign; no undocumented vendor dependencies | All evidence accessible and exportable independently of vendor tools | Records are externally auditable; criteria publicly documented | All significant knowledge work is VERA-native |

---

## Testing Your Tooling for Sovereignty

Before committing to a tool stack, run this five-minute export test:

1. Create a complete claim record in your chosen tool, including evidence item records and a verification record.
2. Export everything to plain text or CSV.
3. Delete the application or log out.
4. Verify that you can reconstruct the complete claim record from the exported data alone — without the application.
5. Verify that someone else could read and understand the exported data without any context from the application.

If you cannot complete steps 4 and 5, you have a Data Sovereignty gap. Either fix the export process or choose a different tool before you accumulate a registry that depends on it.

Run this test annually as part of the sovereignty assessment required by S1 (Data Sovereignty). Tools change. Exports that worked last year may not work this year.

---

*The Implementation section is complete. Return to the [Pattern Catalog](../patterns/catalog.md) if you encounter recurring challenges that patterns might address, or proceed to the [Reference section](../reference/glossary.md) for the glossary, standards alignment, and changelog.*
