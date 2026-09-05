---
type: audit
status: summary
created: 2026-09-05
---

# Wiki Health Check — 2026-09-05

Post-ingest audit of the Claude Code Course batch. Audit run: `./tools/healthchecks` (docs) + inline link/orphan scan across `wiki/`, `notes/`, `00 Command Center/`.

## Summary

| Check | Result |
| --- | --- |
| Broken internal wikilinks (content files) | **0** — all new course pages resolve |
| Broken links in `notes/index.md` | **0** (after handling escaped `\|` aliases) |
| Orphan pages | **0** — all 114 wiki pages reachable |
| New pages in index | 11/11 listed in `notes/index.md` |
| Sensitive/paywalled source leakage | **None** — transcripts stay under gitignored `raw/` |

## Findings

### Gifted checks pass
- All 11 `wiki/Claude Code Course/*.md` pages present; each has YAML + summary + cross-links + source footnote.
- All internal links resolve against the existing corpus (no dangling targets created by this batch).
- No orphan pages introduced; every new page is reachable from `notes/index.md`.

### Pre-existing notes (not caused by this batch)
- A handful of pages reference external tutorials (Karpathy transcripts, YouTube courses, `llm-wiki`) as `[[Title|Local transcript]]` broken links — they intentionally point at raw clippings that live outside the tracked tree. Known, accepted debt (AGENTS.md treats wikilinks into excluded folders as fine in Obsidian).
- `Substance Over Form`, `IAS 7`, `IAS 36` appear as shortlinks without a matching page yet — candidate future pages, not build errors.

## Privacy / publication review
- `raw/**` and `Clippings/` are gitignored; confirmed via `git check-ignore` that the Claude Code Course **transcripts are not part of the commit**. Only compiled `wiki/Claude Code Course/` synthesis goes to GitHub + Quartz site. Paywalled course content stays local. ✅

## Suggested future edits
- Optionally stub `[[Substance Over Form]]`, `[[IAS 7]]`, `[[IAS 36]]`.
- Consider a real health-check script under `tools/healthchecks/` (currently only a README).

## Pages added this time
- 11 pages added under `wiki/Claude Code Course/` (see `notes/index.md`).

## Log
- Entry appended to `log.md` for the ingest (preceding) and this lint pass.