---
title: Power Features
created: 2026-09-05
updated: 2026-09-05
type: concept
status: developing
tags: [claude-code, power-features, ai-coding-agent]
sources: [raw/sources/claude-code-course/doc_34f7e8609ca9_Level 3 - cc course Power features.txt]
confidence: medium
---

# Power Features (Level 3)

The capabilities that take a Claude user from "decent" to "superhuman." Skills, token management, routines, MCP/API/CLI, sub-agents, and critic loops.

## Skills

- **Skills are the difference between a joe and a pro** (minor vs major leagues). They turn a generic agent into consistent output.
- A skill = markdown file with **name, description, body**. Claude reads the description, decides if it applies, then runs the body.
- **Skill sources**: community/classroom, `vault-agent`, `Obra superpowers`, `sk1l.dev`, and **skills directory** (searchable, e.g. "SEO").
- **Safety note**: GitHub stars ≠ safety. Star counts can be gamed. Vet MCPs/skills before installing.
- **Install**: clone the repo via Claude, `/skill <name>` to invoke.
- **Build your own**: describe the process + required connections (e.g. Bitly API key). Test it, then amend to your circumstances. **Battle-tested > paper-thin.**
- **Export/portability**: ask Claude to save all your skills to a folder so you can carry them across environments.

## Token management & context rot

- **Context rot**: performance declines as conversation lengthens (models hallucinate 1-10%). Protect the window.
- `/context` shows usage breakdown (messages, MCP tools, system prompt). MCP tools can quietly erode context.
- `/compact` summarizes to a kernel; `/clear` wipes. **One task = one window.**
- **One-shot your first prompt.** Don't iterate toward a point; if unsure, get a self-contained prompt back and restart fresh. *"Why burn a crazy amount of tokens to get a worse version?"*

## Routines (scheduled/triggered agents)

- **Routine** = schedule an agent to act repeatedly. Two kinds:
  - **Local**: acts on your computer (needs machine on), e.g. "organize my desktop daily."
  - **Remote**: like n8n/Make, agent runs cloud-side, e.g. daily "draft replies to unread emails."
- Add **connectors** per routine. Apply **principle of minimal access** — give the routine only the tools it needs (e.g. just Gmail), nothing more.
- **API trigger**: inbound trigger — a website form fires the routine, which drafts a reply + books a call. Guarded rule: *"you are unable to reply to the API call; you must only action it."* Routines can partially replace Make.com / n8n for inbound flows.

## MCP vs API vs CLI

- **CLI (command-line interface)** — direct; token-efficient; holds your auth (e.g. `gh`). Gold standard where possible. Program runs locally, manual, no automation.
- **API (application programming interface)** — what humans wrote so machines talk to machines; program-to-program over network; set, rigid responses (e.g. YouTube Data API v3).
- **MCP (Model Context Protocol)** — what Anthropic wrote so *models* talk to APIs without you writing glue. "A universal remote control." A wrapper that organizes a raw API and only exposes what the model needs → saves tokens, behaves predictably, persists context, bundlessubtools. Can be hosted (Railway, PipeDream) so a team shares an API key via the MCP without exposing it.

Why MCP beats raw API call: one hop, no endpoint memorization, plain-English use, results persist, transcriptions bundled, local/private, stacks with other tools.

## Sub-agents & parallelization

- **Delegation**: spawn 2nd/3rd/4th agents, each with its own complete context window, to run tasks concurrently. Big speedup vs step-by-step.
- Example: research "best place to live" with 3 sub-agents (financial/tax, longevity/health, social/community), then a parent synthesizes.
- **Rule of relevance**: sub-agents should be on the *same topic* doing it faster — different topics (e.g. community search vs YouTube chat) belong in separate conversations.
- This is the "parallel agent pattern" used to build the website winners in [[wiki/Claude Code Course/Website Building|Website Building]].

## Autonomous critic loop

- **Claude grades Claude's work** — creating is one thing, reviewing is another.
- Bring in **different models** for fresh eyes (Gemini CLI, ChatGPT CLI / Codex, DeepSeek): *"create a critique agent, review it yourself, then bring in a tag and codex with fresh perspective."*
- **Never ship code without external review** — an absolute standard. Use autonomous loops on high-stakes builds, and verify what agents claim (see [[wiki/Concepts/Agentic Engineering|Agentic Engineering]]).

## Plugins

- A plugin = series of skills + instructions bundled together (e.g. a YouTube plugin with ideation, scripting, intros, hooks).
- **Portable/shareable** with a team to standardize workflows. Jack's take: prefers to *snipe* skills rather than rely heavily on plugins.

---
^[raw/sources/claude-code-course/doc_34f7e8609ca9_Level 3 - cc course Power features.txt]