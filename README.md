# VERA: Verified Evidence & Reasoning Architecture

A framework for structured claim verification, traceable reasoning, and epistemic sovereignty.

**Read the book:** [danielflugger.github.io/VERA](https://danielflugger.github.io/VERA/)

---

## What is VERA?

VERA is a documentation framework for anyone who needs to make, evaluate, or act on claims that matter. It provides:

- A **Verification Protocol** — a five-phase process for moving a claim from assertion to verified record
- A **Maturity Model** — five levels across six domains for assessing and improving epistemic practice
- A **Patterns Library** — 13 reusable patterns for common evidence and reasoning challenges
- **Implementation guidance** — getting started, adoption roadmap, and tooling integration
- **Sovereignty principles** — design constraints ensuring you retain ownership of your reasoning

## Structure

```
src/
  foundations/      # Philosophy, Lexicon, Verification Protocol, Pattern Template, Sovereignty
  maturity-model/   # Five-level × six-domain capability model
  patterns/         # 13 patterns across Evidence, Reasoning, and Verification domains
  implementation/   # Getting started, adoption roadmap, tooling
  reference/        # Glossary, standards alignment, changelog
```

## Building locally

Requires [mdBook](https://rust-lang.github.io/mdBook/).

```bash
# Install (via Homebrew)
brew install mdbook

# Serve with live reload
mdbook serve --open

# Build static output
mdbook build
```

Built output goes to `docs/`.

## Version

Current release: **v1.0.0** — all sections complete.
Verification Protocol version: **1.0**
Pattern library: **VERA-P-0001 through VERA-P-0013**
