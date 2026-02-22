# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

VERA (Verified Evidence & Reasoning Architecture) is a documentation project published as an [mdBook](https://rust-lang.github.io/mdBook/). All content lives in `src/` as Markdown files; `book.toml` configures the build.

## Commands

```bash
# Install mdBook (once)
cargo install mdbook

# Build the book
mdbook build

# Serve locally with live reload
mdbook serve --open

# Build and check for broken links
mdbook build && mdbook test
```

## Structure

```
book.toml          # mdBook configuration
src/
  SUMMARY.md       # Table of contents — controls navigation and build
  introduction.md  # Book landing page
  foundations/     # Core concepts (Philosophy, Lexicon, Verification Protocol, Pattern Template, Sovereignty)
  maturity-model/  # Five-level × six-domain capability model (overview + level-1 through level-5)
  patterns/        # Reusable pattern catalog and domain-specific pattern collections
  implementation/  # Getting started, adoption roadmap, tooling
  reference/       # Glossary, standards alignment, changelog
book/              # Build output (git-ignored)
```

## Key Conventions

**SUMMARY.md is authoritative.** Every file referenced in `src/SUMMARY.md` must exist. Adding a new chapter requires both creating the `.md` file and adding it to `SUMMARY.md` in the correct location. The build will fail on missing files.

**Lexicon terms are precise.** `src/foundations/lexicon.md` defines all VERA terminology canonically. When writing or editing content, use terms exactly as defined there — don't introduce synonyms or paraphrase definitions.

**Pattern IDs are permanent.** Patterns use stable identifiers (`VERA-P-NNNN`). Never renumber or reuse an ID. Deprecated patterns keep their IDs and are marked Deprecated.

**Claim IDs follow the format** `VERA-C-[YYYY]-[NNNN]`. Verification records use `VERA-V-[NNNN]`.

**Verification Protocol version** must be noted in claim records and the changelog when the protocol is updated.

**In-progress chapters** use the stub header:
```markdown
> *This chapter is in progress. Full content will be added in a subsequent release.*
```

## Content Status

| Section | Status |
|---------|--------|
| Foundations (all 5 chapters) | Complete |
| Maturity Model (all 6 chapters) | Complete |
| Patterns Library (all 4 chapters) | Complete — 13 patterns |
| Implementation (all 3 chapters) | Complete |
| Reference (all 3 chapters) | Complete |
