# VERA: Verified Evidence & Reasoning Architecture

> *"A claim without evidence is an opinion. A chain of reasoning without verification is a story. VERA closes the gap between assertion and knowledge."*

---

## What Is VERA?

VERA — **Verified Evidence & Reasoning Architecture** — is a structured framework for ensuring that every significant claim is traceable to evidence, every conclusion is the product of explicit reasoning, and every individual or organization retains sovereignty over the knowledge they generate and depend upon.

VERA is not a software system, though it can be implemented in one. It is not a certification standard, though it enables meaningful certification. It is not an AI system, though it is designed to work alongside AI. VERA is an **architecture** — a principled way of organizing how claims are made, how evidence is managed, how reasoning is constructed, and how verification is conducted.

---

## Why VERA Exists

Three convergent forces make a framework like VERA necessary today.

**The evidence crisis.** Digital networks have made it trivially easy to circulate claims without evidence, to manufacture synthetic evidence, and to separate a conclusion from the chain of reasoning that produced it. Institutions that were once reliable filters — journalism, academia, government — are under structural pressure. The result is an epistemic environment in which it is genuinely difficult to know what to believe.

**The AI amplification problem.** Artificial intelligence systems can generate fluent, confident, detailed reasoning at massive scale. When that reasoning is correct, AI is transformative. When it is wrong — when it hallucinates, over-generalizes, or reflects training biases — the errors are just as fluent and just as confident. Without a framework for verification, AI-assisted reasoning is indistinguishable from AI-generated fiction.

**The sovereignty gap.** Individuals and organizations increasingly outsource their reasoning to opaque systems: search algorithms, recommendation engines, large language models, consultant reports. The conclusions they receive are disconnected from the evidence chains that would allow them to evaluate or challenge those conclusions. They become dependent on systems they cannot audit, reasoning they cannot trace, and evidence they cannot access.

VERA addresses all three forces. It provides the vocabulary, protocols, patterns, and maturity model needed to reason in a way that is verifiable, traceable, and sovereign.

---

## Core Concepts at a Glance

| Concept | Definition |
|---|---|
| **Claim** | A structured assertion with explicit provenance and verification status |
| **Evidence** | Primary source material that supports or refutes a claim |
| **Reasoning Chain** | The explicit logical steps connecting evidence to a conclusion |
| **Verification** | The process of confirming that a claim is supported by its stated evidence |
| **Pattern** | A reusable, documented solution to a recurring reasoning or verification challenge |
| **Domain** | One of the six capability areas measured by the VERA Maturity Model |
| **Sovereignty** | Maintained authority over one's data, reasoning processes, and conclusions |
| **Maturity Level** | One of five stages of VERA capability, from Aware to Sovereign |

---

## How to Use This Documentation

This documentation is organized into four major sections.

**[Foundations](./foundations/philosophy.md)** establishes the philosophical and terminological bedrock of VERA. Read this first — especially the [Lexicon](./foundations/lexicon.md), which defines terms precisely and prevents the drift in meaning that makes cross-team reasoning so difficult.

**[Maturity Model](./maturity-model/overview.md)** provides a five-level, six-domain model for assessing and growing VERA capability. Use it to assess your current state, set targets, and plan development work. The model is calibrated so that Level 3 (Practicing) represents a sustainable, high-value operating level for most teams.

**[Patterns Library](./patterns/catalog.md)** is a catalog of reusable solutions to recurring reasoning and verification challenges. Patterns are not abstract — each one includes implementation steps, evidence requirements, and verification criteria.

**[Implementation](./implementation/getting-started.md)** provides practical guidance for adopting VERA: starting small, building habits, scaling to teams, and integrating with existing tools and workflows.

---

## Design Principles

VERA was designed around several commitments that distinguish it from other epistemological frameworks.

**Precision over completeness.** VERA prefers a small number of precisely defined terms over a large vocabulary of loosely defined ones. The [Lexicon](./foundations/lexicon.md) is authoritative. When a term is defined there, it means exactly what the Lexicon says.

**Process over judgment.** Verification should be reproducible. Two people following the same VERA protocol on the same claim and evidence should reach the same verification state. Where judgment is required, VERA makes the judgment criteria explicit.

**Traceability over efficiency.** VERA asks you to slow down and document. This is a cost. The benefit is that you can audit any conclusion, return to it months or years later, update it when evidence changes, and hand it to someone else without losing the reasoning that produced it.

**Sovereignty over convenience.** VERA does not ask you to trust any external authority — including VERA itself. The framework is designed so that every protocol can be executed with tools you control, evidence you hold, and reasoning you can inspect and challenge.

---

## Relationship to Other Frameworks

VERA is not designed to replace existing frameworks. It is designed to interoperate with them:

- **Scientific method**: VERA formalizes the hypothesis-evidence-verification cycle into repeatable, documented patterns usable outside the scientific publishing context.
- **CMMI / ISO 9001**: VERA's maturity model follows the same five-level progression as CMMI. Organizations already operating at CMMI Level 3 will find the governance concepts familiar.
- **Argumentation theory / logic**: VERA is compatible with formal argumentation frameworks (Toulmin, IBIS) but does not require them. Its Reasoning Chain construct is simpler and more practical for organizational use.
- **AI governance frameworks (EU AI Act, NIST AI RMF)**: VERA's verification and sovereignty principles map naturally onto AI governance requirements. Chapter [Standards Alignment](./reference/standards.md) documents these mappings.

---

*Begin with [Philosophy & Principles](./foundations/philosophy.md) to understand the epistemic commitments that underlie every other VERA construct.*
