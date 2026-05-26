# uz6r Profile README

## What This Is

GitHub profile README for uzair zahari — a full stack engineer showcasing their portfolio, skills, shipped work, side projects, and writing. Serves as a professional landing page on GitHub.

## Core Value

Present an authentic, up-to-date snapshot of who I am, what I build, and what I care about as an engineer.

## Current State

**v1.0.0 — Shipped 2026-05-26**

The profile README has been fully refreshed:
- About section reflects digital bank transition with no courtsite references
- Currently section shows incoming software engineer role, "open to" removed
- TracePace promoted from beta to launched (v1.0.0) with tracepace.app URL
- Blog posts updated with current article, old post removed
- Emergency Reschedule Request added to shipped work
- GitHub stats cards embedded after About section (stats, languages, streak)
- Shipped-work heading promoted for visual emphasis
- Closing tagline retained as implicit CTA

## Requirements

### Validated

- ✓ **About section** — transition statement: "between roles, soon joining one of malaysia's leading digital banks" — v1.0.0
- ✓ **Currently section** — "software engineer (incoming) @ digital bank", "open to" removed — v1.0.0
- ✓ **TracePace** — launched, v1.0.0, tracepace.app URL, repo note preserved — v1.0.0
- ✓ **Blog posts** — "i train in blocks" added, "playing the long game" removed — v1.0.0
- ✓ **Emergency Reschedule Request** — added to shipped work — v1.0.0
- ✓ **GitHub stats cards** — 3-card embed (stats, languages, streak) via GH Actions — v1.0.0
- ✓ **Shipped heading** — promoted from `###` to `##` — v1.0.0
- ✓ **Closing CTA** — existing tagline serves as implicit call-to-action — v1.0.0

### Active

(None — all v1 requirements shipped)

### Next Milestone Goals

- **AUTO-01**: Automate blog posts via Medium RSS + GitHub Actions
- **AUTO-02**: Automate stats card regeneration via GitHub Actions

### Out of Scope

| Feature | Reason |
|---------|--------|
| Visitor counters | Anti-pattern per 2026 recruiter consensus |
| Animated snake / typing SVGs | Flashy gimmicks inconsistent with profile voice |
| Stack overhaul | Current stack section is accurate and well-organized |
| Named employer | Privacy preference — keep digital bank description generic |

## Context

Shipped v1.0.0 with 293 lines added to deliverable files across 2 phases.
Tech stack: Markdown, YAML (GitHub Actions), github-readme-stats.
This README was refreshed from a stale courtsite-era artifact.

Since initialization:
- Left courtsite for a role at one of Malaysia's most recognized digital banking/fintech companies
- Shipped Emergency Reschedule Request feature for courtsite
- TracePace launched publicly at v1.0.0
- Published new Medium article: "i train in blocks, i build the same way"
- Created GitHub Actions workflow for daily stats card regeneration

## Constraints

- **Voice**: Keep the tone authentic and understated — no hype language
- **Style**: Match existing README formatting (badges, concise bullet points)
- **Privacy**: Don't name the new employer publicly — describe as Malaysia's digital banking/fintech space

## Key Decisions

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| Keep employer vague | Privacy preference — signal the industry without naming the company | ✓ Good |
| Keep TracePace repo note | Repo remains private/invitational | ✓ Good |
| Remove "open to" line | No longer needed in current section | ✓ Good |
| Use GH Actions for stats (not Vercel) | More reliable; no external service dependency | ✓ Good |
| Dark theme on all cards | Consistent with profile visual style | ✓ Good |
| Tagline serves as implicit CTA | No new link needed | ✓ Good |

---

*Last updated: 2026-05-26 after v1.0.0 milestone*
