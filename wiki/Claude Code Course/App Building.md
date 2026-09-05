---
title: App Building
created: 2026-09-05
updated: 2026-09-05
type: workflow
status: developing
tags: [claude-code, apps, workflow]
sources: [raw/sources/claude-code-course/doc_f63c108bd367_Level 6 - cc course apps.txt]
confidence: medium
---

# App Building (Level 6)

Build functional apps (with auth, databases, payments, emails) in minutes — "if you can imagine it, you can build it." Framed as the natural upgrade of the website work in [[wiki/Claude Code Course/Website Building|Website Building]].

## Architecture view

Components: **front-end** (site), **back-end** (logic/database), **automations**, **integrations**. Uses the BLAST framework (brief → loop → architect → ship) for any app.

Key mindset: LLMs are **probabilistic** (same question 100x = 100 different answers). In 构建 apps, aim for **deterministic** behavior in the parts you control.

## Email capture pipeline

1. Add a **multi-step CTA** to the site: name → email → (e.g.) money range → biggest problem.
2. **Supabase** acts as the point of record (Excel "hit by adderall" — a Postgres database + free API/MCP). Connect via the pre-authorized connector. Each form submission lands in a `leads` table.
3. **Front-end can't call services directly** (would expose API keys). So the flow is: form → **Supabase** → Supabase scripts/automations forward to **BeHive** (email database/CRM). Same pattern works for GoHighLevel, Brevo, etc.
4. **Double opt-in** when lead quality is questionable → protects deliverability (lose ~30% but keep a healthy email garden). "What good is an email list if nobody reads it."
5. Publish changes to GitHub → live on Vercel (see [[wiki/Claude Code Course/Website Building|Website Building#Deployment-Vercel]]).

## Authentication & dashboard

- Add **signup/login** authenticated and managed via **Supabase**.
- During testing, **disable confirm-email** under Authentication → Sign-in providers (re-enable before going live to stop spammers).
- Recommend **sign in with Google** (one-click, standard).
- Behind the login: a beautiful **dashboard** that scrapes the user's site + runs SEO analysis (pull in GitHub repos for that analysis) — a teardown product.
- **Magic link** auth works; for richer flows require a real password at signup.
- Iterate on feedback (design, confetti animation, image height, etc.); use `/fork` to split workstreams off the main project while keeping context.

## Payments (Stripe)

- Create a **Stripe** account; always test in **Sandbox** mode with fake/test keys.
- Model the offer: e.g. **Standard** (free) vs **Premium / website max (£10/month, recurring)**.
- Create a **product** in Stripe (product ID), pass it to Claude, have it wire up the checkout subscription tied to the dashboard.
- Add **Open Router API key** for AI features: use a good model (sonnet) for first 10 msgs/day, then drop to a cheaper model; **implement rate limits** to prevent abuse and watch credit spend.

## Emails (Resend)

- **Resend** for transactional/onboarding emails ('reset code' emails, onboarding welcome).
- Create API key + verify a domain (or use `onboarding@resend.dev` quick-send).
- Claude sends a **test email** to prove the integration; then iterate on the copy/design until gorgeous.
- Same pattern generalizes to any email provider.

## Workflow patterns

- Just **yap instructions** to Claude and let it act — no need to hand-hold every step.
- **Push back on Claude**: proactively *"can you just do this for me?"* and use the Supabase CLI to action DB changes directly (login yourself, it applies).
- **Parallel sub-agents**: spin up a cohort for e.g. deep research on best-converting copy for this kind of site; synthesize their inputs (see [[wiki/Claude Code Course/Power Features|Power Features#Sub-agents-and-parallelization]]).

---
^[raw/sources/claude-code-course/doc_f63c108bd367_Level 6 - cc course apps.txt]