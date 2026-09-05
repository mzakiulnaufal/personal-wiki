---
title: Website Building
created: 2026-09-05
updated: 2026-09-05
type: workflow
status: developing
tags: [claude-code, website, workflow]
sources: [raw/sources/claude-code-course/doc_aa11f9b09c10_Level 2 - cc course website masterclass.txt]
confidence: medium
---

# Website Building (Level 2)

Zero → deployed website using a repeatable 3-step system built on competitive intelligence.

## 3-Step Website System

1. **Competitive intelligence** — scrape competitors to find what works.
2. **Structure brief** — compile findings into a design brief.
3. **Deploy** — push live to a real URL (Vercel).

## Why competitive intelligence

Don't reinvent the wheel. Find what's *already working* for top performers, extract those principles, then build with them. Power law across everything — identify what works, do more of it. Jack's first text article did 50k unique visitors/month largely because he started from what works.

## Workflow

1. **Pick a niche example.** E.g. a website design agency serving "high-margin sexy niches" (pool cleaners, waste management, etc.).
2. **Send a competitive-intel prompt to Claude** using **Firecrawl**: find the top 5 best consultancy/website-builder sites, build a judging matrix (Google reviews, SEO ranking, etc.), deliver a report, then analyze what the best 5 do **in common** that the worst 5 don't.
   - The prompt teaches Claude to ask clarifying questions (target customer, angle). Give it a specific avatar + transformation angle (e.g. *"we're all about delivering customers"*).
3. **Compile the research** into a `best-principles.md` file (drop all findings into the file).
4. **Build the website with Claude** referencing that brief. Ask Claude to build a *website design agency* site using the best resources/libraries for beauty & interactivity. Prefer **less-prescriptive** prompts.

## The "three flavors" hack — parallel agents

Give the **same** brief to 3 parallel agents, each with a **different** source of design inspiration, and pick the winner:
1. **Pure Claude** — just the best-principles brief.
2. **Versus/Vercel-inspired** — feed Claude the downloaded HTML of a gorgeous site (e.g. via a website HTML viewer → "view source" → download) as inspiration.
3. **Awesome-Designs GitHub repo** — feed the Framer design system repo as inspiration.

>> *"You give it the same prompt 10 times you get 10 completely different websites."* Keep designs in separate folders (`one/`, `two/`, `three/`).

Pick the best, delete the rest, iterate on the winner.

## UI sniping

Steal the best UI components from curated libraries and integrate them:
- **21st.dev** — components like liquid cursor, testimonial sections. Copy the prompt or the code; tell Claude to integrate the component *under the H1* (or where it makes sense), changing text to fit the site.
- **CodePen** — animated/custom visuals (e.g. expanding flex cards).
- Use **OpenAI image gen (gpt-image)** to generate custom imagery: give Claude a stored API key and ask it to generate relevant images for the sections being implemented.
- Realistic rule on components: *"All people want is faces so it looks real and authentic."*

## SEO + Accessibility polish

- **UI/UX skill** (from classroom): ruthless application of best principles — contrast, button sizes, touch interactions, typography, layout/navigation, accessibility checklists (~50-60 mini criteria baked in).
- **Claude SEO skill** (GitHub repo): keyword strategy balancing attention vs conversion vs SEO ranking, schema markup, on-page optimization.
- Run two agents in parallel — one on UI/UX, one on SEO — since SEO may change copy.
- Ask for a detailed list with green tick marks of every improvement before pushing live.

## Validation: check Claude's work

Act as a **critically challenging reviewer**: *"go through the website and find inconsistencies, copy that doesn't make sense, design flaws; return a list of critical/high/medium/low ideas."* Bring in any relevant GitHub repos needed.

## Deployment (Vercel)

- GitHub is where code lives → Vercel connects to GitHub and hosts.
- Connect `gh` CLI → create a GitHub repo → push → (optional) make public.
- `vercel CLI` → authorize → **"publish this on Vercel."**
- Speed insights & analytics: install with code, manage via Claude.
- **Custom domain**: buy via Vercel → connect to project → 301 permanent redirect for a nicer domain. *"A custom domain really lifts perceived quality."* (Noted: this course uses Vercel consistently; the wiki's own [[wiki/Claude Code Course/Setup and Foundations|Setup]] prefers CLI where possible.)

---
^[raw/sources/claude-code-course/doc_aa11f9b09c10_Level 2 - cc course website masterclass.txt]