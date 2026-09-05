---
title: Design Systems
created: 2026-09-05
updated: 2026-09-05
type: concept
status: developing
tags: [claude-code, design, design-system]
sources: [raw/sources/claude-code-course/doc_0763a8846cbb_Level 8 - cc course Design Systems.txt]
confidence: medium
---

# Design Systems (Level 8)

**Design is code.** Core premise: AI is inherently *bad* at design because it doesn't understand what great design is. So the art form is **codifying** what great design is, so you can reliably reproduce it.

## The shift: surface = code

- For 20+ years design lived in a separate app (Photoshop, Premiere Pro): you design in one place, engineers rebuild in another.
- Now **the surface is the code itself.** *Code design* is emerging, and AI builders are at the front end of it.

## Claude Design → Open Design

- **Claude Design** (Anthropic's) adds no new model capability — it's the same underlying model with integrated prompts/systems, and it **eats tokens**.
- **Open Design** is an **open-source replica of Claude Design**: a local UI / brand-system builder where you build design systems in one location, usable with any model (Claude, DeepSeek, ChatGPT, Grok). Clone the repo into your Claude session.
- Have Claude build slides/designs by feeding it the repo + a brief, and it matches the design language precisely.

## Power Design — the 20 universal design rules

Codified from deep research: the best AI-designed deliverables share ~**20 universal rules**. Relevant to presentations and, by extension, websites. Highlights:
- **Low cognitive load — System 1 thinking, not System 2.**
- **White space.** *"A slide should be glanceable in 3 seconds."*
- Consistent type hierarchy, strong contrast, clear focal point, simple grids, purposeful color, restrained animation, accessible text sizes, alignment to a clear message.

Use a "Power Design" repo as the design bible for any HTML slides/website build — install, clone, learn everything about it, then give brand examples to build against.

## Design tools & workflow

- Great designers have many colors on the paintbrush — combine **Open Design** (brand systems), **Power Design** (rules), Claude Design, and UI-sniping libraries (21st.dev / CodePen) from [[wiki/Claude Code Course/Website Building|Website Building#UI-sniping]].
- Open Design runs as its own **Electron app** with specific dependencies; have Claude install/run it.
- Choose the best tool per job (Open Design vs Claude Design vs pure Claude) rather than defaulting to one.
- "Design is the most underrated aspect — when you crack design you crack almost everything."

---
^[raw/sources/claude-code-course/doc_0763a8846cbb_Level 8 - cc course Design Systems.txt]