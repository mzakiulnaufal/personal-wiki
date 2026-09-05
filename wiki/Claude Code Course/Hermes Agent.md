---
title: Hermes Agent
created: 2026-09-05
updated: 2026-09-05
type: tool
status: developing
tags: [hermes, claude-code, personal-assistant]
sources: [raw/sources/claude-code-course/doc_fa46ba4865b1_Level 5 - cc course hermes agent.txt]
confidence: medium
---

# Hermes Agent (Level 5)

Hermes Agent is positioned as the **AI chief of staff / personal assistant** — a companion to Claude Code. The thesis: AI spans two layers.

- **Desktop work (Claude Code layer)**: you at the computer in an IDE. Scoped to a **repo**.
- **Mobile/personal layer (Hermes)**: always on, lives across your whole life, reachable from your phone. Scoped to **you**.

> "Coding AI is scoped to repo. Hermes is scoped to you."

## Why Hermes

- **Fastest zero-to-one** of the "personal AI" systems (versus Open Claw, Claw Claw, Gravity Claw) and unbelievably easy to install. The course treats AI personal assistants as the next big wave (Siri never quite hit the mark; expect this to blow up).
- **Reachable from anywhere**: Telegram, WhatsApp, SMS.
- **Remembers across sessions** (memory) and **acts, not just answers**: draft emails, book calls, save notes, ship cron jobs.
- Runs **without you asking** — e.g. a 7am daily digest of the last 5 things that happened in your world.
- Connects every tool you already have (GitHub, Firecrawl, Slack, Gmail, Stripe).

## Install options

- **Fastest / $0 / safest**: on your own computer with one command (`curl …`), interactive setup.
- **Container (Docker)**: isolated from your filesystem — for people who don't want it touching personal folders. Docker = "a self-contained bedroom." **Image = recipe/frozen ingredients; container = the pizza you bake.** Stop = container vanquished. Give it access to specific files as needed.
- The real transcript also frames **VPS/container** deployment as an option for "most people shouldn't run it touching my folders" scenarios; personal install preferred for asking it "what was that thing on my desktop?"

## Setup walkthrough

1. Install (local or Docker).
2. **Model**: set OpenAI **Codex** (uses your $20 ChatGPT sub; OpenRouter as the second big option). (Note: the wiki operator runs Hermes on a VPS via OpenRouter/other providers — see [[wiki/Claude Code Course/Setup and Foundations|Setup]].)
3. **Telegram gateway**: create a bot via **BotFather** (`/newbot`), paste the token; **whitelist your user ID** so only you can message it (secure without VPS fiddling).
4. Optionally point it at an **Obsidian vault** → it can answer questions from your notes ("tell me an insight about intros using the vault").

## Claude Code Operating System (Claude OS)

A community-exclusive dashboard loaded as a zip → Claude "runs everything in this file for me." Overview of:
- Spend across models, skill usage/savings, utilization (e.g. "you're not using your full Max allowance").
- All your skills, memory integrations, Obsidian, Pinecone, Open Router usage tracking, web search, dreaming frequency, and your **value of time**.
- Backed up to a **private GitHub** daily (version control = survive a dead laptop).

## Pantheon (personas/skills)

- Create **personas** (the "Pantheon") — unique characters/roles, each with job, description, system prompt, and model. The dashboard gives a *visual* interface to assign a persona to a task ("use scribe to do X").
- **Soul.md** — a persona-defining document (personality, character, key facts, rhythm) you give to Hermes so it truly understands you.
- Add new skills by copying the description into a persona (e.g. the **NotebookLM / scribe** research skill).

## NotebookLM integration (research superpower)

- Connect **NotebookLM** (unofficial Google plugin) via a browser cookie.
- Add it as a skill/persona (e.g. "scribe") in the Pantheon.
- Result: ask Hermes in plain chat to *"go find this research / create a new notebook on X"* → NotebookLM produces deep, cross-source research and infographics **for $0**. (The transcript example autodetects your last notebook/infographic and creates a new one on command.)

## Relation to this wiki

Hermes Agent IS the system this wiki operator runs. The course's framing of Hermes (memory, skills, cron, multi-platform) matches the operator's [[wiki/Claude Code Course/Memory System|memory system]] setup and personal assistant workflows.

---
^[raw/sources/claude-code-course/doc_fa46ba4865b1_Level 5 - cc course hermes agent.txt]