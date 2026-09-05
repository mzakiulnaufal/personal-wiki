---
title: Setup and Foundations
created: 2026-09-05
updated: 2026-09-05
type: workflow
status: developing
tags: [claude-code, setup, workflow]
sources: [raw/sources/claude-code-course/doc_7b62d1a721ce_Level 1 - cc course.txt]
confidence: medium
---

# Setup and Foundations (Level 0-1)

How to install Claude Code, choose an environment, and set up a working AI-dev foundation.

## Core idea: Environment = Iron Man suit

Claude Code is the *model* (Tony Stark); the **environment** is the suit you pick to run it in. Many suits exist sharing the same underlying VS Code substrate:
- **Claude desktop app** — chat / co-work / code modes
- **Antigravity** (Google's IDE) — Jack's daily driver
- **VS Code** terminal

You can chat to the IDE agent and it will install Claude Code itself ("install Claude Code on my computer and install any dependencies").

## Three Claude usage modes

- **Chat** — regular conversation, like the web app, on desktop.
- **Co-work** — code with training wheels; user-friendly for business owners, but **limited**.
- **Code** — the unlimited version. *"If you can use co-work, you can use code."* Prefer code.

## Plans & economics

- **Pro ($20)** = the floor needed for Claude Code; start here.
- **Max** = the step up; way more usage. Jack is on Max 20x.
- Reframe: an AI assistant is *the cheapest AI employee you'll ever find*, not a Netflix subscription.
- Model shopping via Open Router / DeepSeek gets ~95-98% of performance for a fraction of cost (see [[wiki/Claude Code Course/Power Features|Power Features]]).

## Permissions (three levels)

1. **Ask first** — approves every file edit + every shell command; best for unfamiliar repos.
2. **Accept edits** — edits happen freely, other shell commands still ask. Default daily driver.
3. **Bypass permissions** – "hinge mode": zero prompts, runs riot. Use with discretion in trusted environments.

## Key concepts

- **Context window**: "a 200-IQ individual with amnesia." Claude Code limit ~1M tokens (~750k words / ~4 Harry Potter books).
- **Context rot**: performance degrades as conversation grows. Counter with `/compact` (ruthless summarize) or `/clear` (wipe). *One task = one window.*
- **Hallucination**: models are confidently incorrect 1-10% of the time — verify.

## Slash commands for daily use

- `/context` — show context window usage & breakdown
- `/compact` — squeeze conversation into a summary
- `/clear` — wipe context, fresh slate
- `/model` — switch models
- `/cost` — live token/cost tracking
- `/init` — become familiar with a codebase
- `/memory`, `/plans` — manage CLAUDE.md and plans

## The one-shot principle

The **first prompt is the most important prompt.** Give the full objective up front; never iterate toward a point ("actually I meant…"). If you need 4-5 clarifying prompts, ask for a self-contained prompt back and restart in a fresh window. Closer your first prompt is to the objective, the better the whole run.

## Connecting the world

- **Connectors** (Claude built-ins): Gmail, Google Drive, GitHub, Canvas, Firecrawl, Granola, Notion, Zapier, Supabase, etc.
- **Custom MCP** when a connector isn't built-in — Claude fetches the MCP URL itself (see [[wiki/Claude Code Course/Power Features|Power Features#MCP vs API vs CLI]]).
- **CLI (preferred)**: token-efficient direct connections, e.g. `gh` for GitHub. *"Wherever possible, prefer CLI over everything else."*
- **API keys**: for specific services (e.g. YouTube v3) when you need raw data/transcripts.

## Project infrastructure

- Organize work into **5-8 top-level projects/folders** (no more than 8 — simplify).
- Each project folder gets a **`CLAUDE.md` project operating manual** (~max 200 words to protect context): what it is, its goal (north star), the stack, key decisions, references/memory map.
- Feed the "Ballast" / behavior block to Claude for every build: brief → loop → architect → ship; think before coding, simplicity first, surgical changes, goal-driven execution.
- GitHub = version control = backup + revert. *"It acts as a game save state."* Repos private by default.

---
^[raw/sources/claude-code-course/doc_7b62d1a721ce_Level 1 - cc course.txt]