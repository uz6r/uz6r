# Architecture

**Analysis Date:** 2026-05-25

## Pattern Overview

**Overall:** GitHub Profile Repository (Special `{username}/{username}` repo) + Side-Project Asset Staging

This repository serves two distinct but related purposes:
1. **Personal GitHub profile README** — The `README.md` at root renders on the developer's GitHub profile page (`github.com/uz6r`).
2. **TracePace public asset host** — The `tracepace/` directory holds a preview image referenced in the README, acting as a lightweight CDN/staging area for the private TracePace monorepo's public-facing assets.

**Key Characteristics:**
- **Single-page profile repo** — The root `README.md` is the sole deliverable for the profile purpose.
- **Side-project staging** — `tracepace/public/` stores a single preview image (`preview.png`) that the README embeds via a relative path.
- **Private monorepo described (not present)** — The README describes TracePace as a "go + next.js monorepo" but that codebase lives in a separate private repository.
- **Planning directory** — `.planning/codebase/` exists for codebase analysis documents (this file and STRUCTURE.md).

## Layers

**Profile Layer:**
- Purpose: Personal portfolio/profile display on GitHub
- Location: `/README.md`
- Contains: Bio, tech stack badges, shipped projects, side projects, writing links, current status
- Depends on: External badge services (shields.io), relative image path
- Used by: GitHub profile page viewer

**Asset Staging Layer:**
- Purpose: Store public-facing assets for TracePace project
- Location: `tracepace/`
- Contains: `public/preview.png` — a preview/screenshot of the TracePace application
- Depends on: Nothing
- Used by: README.md (via relative Markdown image link)

**(Planned) TracePace Monorepo** — described in README but NOT present in this repository:
- Architecture: Go + Next.js monorepo
- Contains: GPS activity visualization platform
- Key components described:
  - Custom Go binary parser for `.fit`/`.gpx` files
  - RDP (Ramer-Douglas-Peucker) path simplification algorithm
  - GraphQL API layer
  - Next.js frontend with Framer Motion animations
  - Multiple poster theme rendering engine
  - High-res PNG export (3:4, 1:1, 16:9 aspect ratios)

## Data Flow

**README Display Flow:**

1. GitHub renders `README.md` as HTML on profile page
2. Badge images fetched from `img.shields.io` (external CDN)
3. TracePace preview image served from `tracepace/public/preview.png` via GitHub's raw content CDN
4. External links (portfolio, LinkedIn, Medium, email, Buy Me a Coffee) open in new tabs

**(Described) TracePace Data Flow** (from README):

1. User uploads `.fit` or `.gpx` GPS activity file
2. Custom Go binary parser reads and normalizes the GPS data
3. RDP algorithm simplifies path to clean vector traces
4. Server applies selected poster theme (e.g., World Marathon Majors, local races)
5. Elevation chart and weather integration data overlaid
6. Final poster exported as high-res PNG in chosen aspect ratio

## Key Abstractions

**Profile README (`README.md`):**
- Purpose: Single source of identity/portfolio for the developer
- Sections: `about`, `stack`, `things i've shipped`, `side projects`, `writing`, `currently`
- Pattern: Flat Markdown file with HTML divs for layout, badge image links for tech display

**`tracepace/` Directory:**
- Purpose: Namespace for TracePace-related content within this repo
- Contains: `public/` subdirectory with static assets
- Pattern: Follows Next.js conventions (public/ for static assets) even though Next.js is not configured in this repo

## Entry Points

**Repository Entry:**
- Location: `/README.md`
- Triggers: GitHub profile page load
- Responsibilities: Present developer identity, skills, shipped work, side projects, and current status

## (Inferred) TracePace Architecture — from README description

Though the TracePace codebase is private, the README reveals its architecture:

**Tech Stack Declared:**
- Golang — GPS file parsing, RDP simplification, API logic
- GraphQL — API layer (likely using gqlgen or similar Go GraphQL library)
- Next.js — Frontend framework
- Framer Motion — Animation library for poster rendering/UI transitions

**Data Pipeline:**
```
GPX/.fit File Upload
    → Go Binary Parser (custom parser)
    → RDP Path Simplification
    → Theme Application
    → Elevation + Weather Data Enrichment
    → PNG Export (3:4, 1:1, 16:9)
```

**Features Described:**
- Multiple poster themes (World Marathon Majors + local races)
- High-res PNG export
- Public beta incoming (version v0.5.0-alpha)
- Repository is private & invitational

## Error Handling

**Strategy:** Not applicable — this repository has no executable code.

The README describes the developer's experience with error handling patterns in shipped work:
- Payment integrations with error handling, retry logic, transaction monitoring
- Temporal Go workflows for booking management

## Cross-Cutting Concerns

**Logging:** Present in described work (Sentry badge listed in stack), but not configured in this repo.
**Validation:** Not present in this repo.
**Authentication:** Not present in this repo — JWT and OAuth badges appear in the stack section indicating developer proficiency.

---

*Architecture analysis: 2026-05-25*
