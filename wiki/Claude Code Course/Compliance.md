---
title: Compliance and Maintenance
created: 2026-09-05
updated: 2026-09-05
type: concept
status: developing
tags: [claude-code, compliance, security]
sources: [raw/sources/claude-code-course/doc_695393b9ee40_Level 9 - cc course Compliance & Maintenance.txt]
confidence: medium
---

# Compliance & Maintenance (Level 9)

Risk appetite for shipping AI-built systems into the wild. "Second you release something into the wild or it needs to work for an organization, if you don't set this up it can fall apart like a $2 suitcase." Derived from Jack's own paid-for experience.

## Where the biggest leaks are

**It's always the database.** Either no right encryption levels (hackable), or a dropped API key letting someone call your service for free / grab everything. "If they get the wrong API keys, they effectively get the keys to the kingdom." The second leak: general API keys exposed on the internet.

## Behavioral checkpoints (abuse prevention)

When building a shared system (e.g. aiwithjack.com), build in **behavioral checkpoints** that detect non-human usage:
- Extreme message volume (obviously a bot) → drop from premier model to a basic model (grace period), then **hard limits** at the back.
- Goal: legit users keep top quality; bots get ratcheted down.

## The 12 compliance rules

1. **Don't paste production keys into the chat** — they may be stored forever (esp. Hermes/Open Core). Best practice: have Claude generate a terminal command to update the key; enter it yourself in the terminal so Claude never sees it. (Some latitude in Claude; never in Hermes.)
2. **Never commit `.env`** — environmental variables hold API keys; pull them via `.gitignore`. AI already does this well, but verify.
3. **Treat Supabase service keys like a nuclear key.**
4. **Enable row-level security (RLS) on every public table.** Most Supabase breaches aren't clever — tables with RLS off, anon key reading everything.
5. **Production ≠ preview ≠ dev.** Every Vercel preview URL is public unless protection is on; a leaked preview with production DB creds = leaked production database.
6. **Turn on 2FA / multi-factor everywhere** — Supabase, Stripe, GitHub, Anthropic, everything.
7. **Pin and order your dependencies.** (14 typo-squatted npm packages stole AWS creds in 4 hours — May 28.)
8. **Vet every MCP before installing** — MCPs can carry malicious code. Read what they do before adding.
9. **Never hardcode secrets in code** — always use environment variables / secret managers.
10. **Keep client data minimal and access-scoped** — only the data the system actually needs.
11. **Regularly rotate / review API keys** — don't leave old keys active.
12. **Design for failure** — think about what could break and build in look-around-corner safeguards early, not after a breach.

## Maintenance philosophy

- Build safeguards and systems, then **look around corners** — anticipate what goes wrong before it does.
- Compliance isn't "sexy, but super important" — it separates a hobby build from something you can ship to customers/organizations.
- See also principle of **minimal access** in [[wiki/Claude Code Course/Power Features|Power Features#Routines-scheduled-triggered-agents]].

---
^[raw/sources/claude-code-course/doc_695393b9ee40_Level 9 - cc course Compliance & Maintenance.txt]