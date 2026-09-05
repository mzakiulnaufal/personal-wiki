# Wiki Schema

## Domain
ACCA Financial Accounting (FA) exam preparation. Covers IFRS, IAS standards, financial statements, and accounting principles.

## Conventions
- File names: lowercase with hyphens (e.g., `ias-1.md`). Use underscores only for tags.
- Every wiki page starts with YAML frontmatter.
- Use `[[wikilinks]]` to link between pages (minimum 2 outbound links per page).
- When updating a page, bump `updated` date.
- Every new page must be added to `index.md` under the correct section.
- Every action must be appended to `log.md`.

## Frontmatter
```yaml
---
title: Page Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: concept | entity | standard | comparison | glossary
tags: [from taxonomy below]
confidence: high | medium | low
---
```

## Tag Taxonomy
- Standards: `ias`, `ifrs`, `framework`
- Financial Statements: `statement-of-financial-position`, `statement-of-profit-or-loss`, `cash-flow`
- Concepts: `accrual`, `going-concern`, `materiality`, `substance-over-form`
- Calculations: `depreciation`, `impairment`, `lease`, `revenue-recognition`
- Entities: `iasb`, `ifrs-foundation`
- Meta: `comparison`, `timeline`, `fa-exam`

Add new tags to this taxonomy before use.

## Page Types
- **Concept:** fundamental accounting concept or principle (e.g., Accrual Basis, Going Concern)
- **Standard:** full IFRS/IAS standard summary (e.g., IAS 1, IAS 16)
- **Comparison:** side-by-side analysis (e.g., IAS 17 vs IFRS 16)
- **Glossary:** term definitions (e.g., "Equity")
- **Entity:** organization (e.g., IASB)

## Page Thresholds
- Create a page when a concept/standard appears in 2+ sources or is central to the exam syllabus.
- Add to existing page when new information enriches it.
- Split pages exceeding ~200 lines.

## Update Policy
- New information from official IFRS/IAS updates supersedes older.
- Note both views if conflicting, with dates and sources.
- Mark contradictions in frontmatter.

## Index & Log
- Maintain `index.md` with all pages listed by type.
- Append to `log.md` with format `## [YYYY-MM-DD] action | Title`.
- Allowed actions: `setup`, `ingest`, `query`, `lint`, `compile`, `maintenance`.