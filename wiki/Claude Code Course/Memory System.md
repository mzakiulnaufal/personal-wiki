---
title: Memory System
created: 2026-09-05
updated: 2026-09-05
type: system
status: developing
tags: [claude-code, memory, system]
sources: [raw/sources/claude-code-course/doc_c1174f1e7873_Level 4 - cc course memory system.txt]
confidence: medium
---

# Memory System (Level 4)

A good memory system *solves the context problem.* If AI had infinite relevant context about you — your business, your projects, past conversations — it could advise better, build better software, and get you further ahead. Goal: **the system should never require you to be in a chat to work** — a brand-new chat performs at the same level as a long one.

## Three levels of memory

1. **Short-term (context)** — what you're doing *right now*: the active conversation + bare-bones hard-wired facts about you (stored in Claude settings "Instructions for Claude" / Antigravity global rules / Gemini.md / Codex equivalents). Claude also has an internal state of recent facts (trip plans, financial goals).
2. **Mid-term (project-level)** — organized into **5-8 top-level buckets** ("organize my life into 6-8 buckets" prompt). Each bucket = a folder on disk, spawned directly by Claude. Include a **`CLAUDE.md` project operating manual** per folder: what the folder is, its **north-star goal**, the **stack**, key **decisions**, a **memory map**, and **references** — so any build is held against the project's north star. Keep total ~200 words to protect context.
3. **Long-term (knowledge)** — **File-based / Karpathy-Obsidian** (mini databases, "Obsidian RAG") for reference knowledge, optionally supercharged with **Pinecone** for semantic retrieval. Also **NotebookLM** (Google's research platform) for deep, cross-source intelligence.

## Mid-term setup workflow

1. Prompt: *"Based on everything you know about me, organize my life into 6-8 buckets. Any project I'm working on goes in those buckets."*
2. Have Claude create the folders, then add the CLAUDE.md operating-manual template (Karpathy principles) to each.
3. Have Claude ask you per-project questions to fill each full brief.
4. Do all work **inside the right project folder** so the manual + memory map are always available. Keep a **Personal** folder with docs (address, W8, registration).

## Long-term tooling

- **NotebookLM** — Google's #1 research & intelligence platform; Grounded, cross-source Q&A over your documents. Integrating it via community plugins turns Hermes/Claude into a research superpower (see [[wiki/Claude Code Course/Hermes Agent|Hermes Agent]]).
- **Pinecone** — vector store option to add semantic search on top of Obsidian.
- **Granola** — meeting intelligence: sits in meetings, listens (without joining), and lets you ask questions about any past meeting ("what was the title of my last meeting? what actions came out of it?"). One option among many.

## Principles

- Goals/objectives change → keep them in **local mid-term** memory; keep stable reference knowledge in long-term.
- The memory OS (community dashboard) visualizes the whole system: sessions, message counts, models, skill usage, spend (see [[wiki/Claude Code Course/Hermes Agent|Hermes Agent#Pantheon-and-Claude-OS]]).
- **Never paste production keys into chat** — memory systems persist stored keys (see [[wiki/Claude Code Course/Compliance|Compliance]]).

---
^[raw/sources/claude-code-course/doc_c1174f1e7873_Level 4 - cc course memory system.txt]