---
title: First Principles and Lead Scraping
created: 2026-09-05
updated: 2026-09-05
type: concept
status: developing
tags: [claude-code, first-principles, business]
sources: [raw/sources/claude-code-course/doc_17c6d6981c93_Level 7 - cc course Build Anything.txt]
confidence: medium
---

# First Principles & System Design (Level 7)

Frame for **building anything** — "probably the most important lesson in the whole course." The only real limits when building with Claude Code are physics, not convention.

## First-principles thinking

- **Core premise**: *Every problem worth solving is a stack of assumptions on top of atoms. Strip the assumptions, count the atoms, rebuild.*
- Not from Elon — a **2,000-year-old unbroken thread**: Aristotle (350 BC, "knowledge must terminate in premises that are true, primary, immediate, explanatory"), Descartes (doubt everything, build up from what cannot be doubted), then Musk.
- **"Only physics is load-bearing; everything that feels fixed (price, timeline, headcount, the way it's done) is a recommendation in disguise."**

Example: 2012 battery costs were "a hard floor" of $600/kWh. Break the battery into raw constituents and price them on the London Metal Exchange → $80/kWh. First principles drives a different number.

## The 5-step engineering protocol (canonized by Walter Isaacson, used by Musk a decade)

*Order matters — skip a step and you optimize something that shouldn't exist. The biggest automation mistake is automating something that clearly never should have existed.*

1. **Question every requirement** — each must carry a person's name, never "the legal team will expect."
2. **Delete the part/process.** If you don't add at least 10% back later, you didn't delete enough. (Jack notes Skool removes features silently, only re-adding on uproar.)
3. **Simplify & optimize** — only AFTER deletion.
4. **Accelerate cycle time** — speed up every loop, but only once 1-3 are done.
5. **Automate** — so it "runs the game."

> *Reduce until the essential question is naked. State the problem until it's boring, then code.*

## High agency

- Read the **High Agency** article. Provocative test: *you're jailed in a third-world country with ONE phone call, worst conditions imaginable; the person you call will answer. Who do you call?*
- High-agency mindset = take nothing on authority; verify yourself; reason from first principles.

## Applying to lead generation

- Use first-principles system design to build a **lead scraping flow**: find the biggest constraint, do more of what works, automate the loop.
- Avoid derivative thinking and derivative content — don't just copy; strip to fundamentals and reason up.
- Tools like **Apify** (scraper platform) + Claude give repeatable lead content on a schedule (weekly refresh), as shown in [[wiki/Claude Code Course/Monetization|Monetization]] with the IG outliers system.

---
^[raw/sources/claude-code-course/doc_17c6d6981c93_Level 7 - cc course Build Anything.txt]