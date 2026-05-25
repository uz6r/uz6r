<!-- GSD:project-start source:PROJECT.md -->
## Project

**uz6r Profile README**

GitHub profile README for uzair zahari — a full stack engineer showcasing their portfolio, skills, shipped work, side projects, and writing. Serves as a professional landing page on GitHub.

**Core Value:** Present an authentic, up-to-date snapshot of who I am, what I build, and what I care about as an engineer.

### Constraints

- **Voice**: Keep the tone authentic and understated — no hype language
- **Style**: Match existing README formatting (badges, concise bullet points)
- **Privacy**: Don't name the new employer publicly — describe as Malaysia's digital banking/fintech space
<!-- GSD:project-end -->

<!-- GSD:stack-start source:codebase/STACK.md -->
## Technology Stack

## Overview
## Languages
- **TypeScript** — Primary language for frontend/backend
- **Python** — Backend API (with SQLAlchemy, GraphQL Strawberry)
- **Go** — TracePace backend (custom .fit/.gpx binary parser, RDP algorithm)
- **JavaScript** — General web development
- **Bash** — Scripting
- None (no source code files present)
## Runtime
- Node.js (via Next.js) — inferred from the Next.js/TypeScript frontend stack
- Python 3.x — inferred from SQLAlchemy/pytest usage
- **npm** or **yarn** — inferred from Next.js/TypeScript usage
- **pip** or **poetry** — inferred from Python/SQLAlchemy usage
- **go mod** — inferred from Go usage in TracePace
## Frameworks
- **Next.js** — React meta-framework (primary frontend for both courtsite work and TracePace)
- **React** — UI library
- **Vue.js** — Secondary/prior experience
- **Nuxt.js** — Vue meta-framework, secondary experience
- **Tailwind CSS** — Utility-first CSS framework
- **Vite** — Build tool/dev server
- **framer-motion** — Animation library for TracePace
- **GraphQL** — API layer (with **Strawberry** Python GraphQL library for courtsite)
- **SQLAlchemy** — Python ORM (courtsite backend)
- **REST APIs** — General backend experience
- **Go standard library** — For TracePace custom binary parser
- **Temporal** — Workflow orchestration (Go + Temporal for booking workflows)
## Data & Infrastructure
- **PostgreSQL** — Primary database
- **Redis** — Caching/message broker
- **Docker** — Containerization
- **Temporal** — Durable execution engine
- **GitHub Actions** — CI/CD
- **Cloudflare** — CDN, Turnstile, DNS
## Auth & Observability
- **JWT** — JSON Web Token auth
- **OAuth** — OAuth 2.0 (Google provider inferred)
- **Sentry** — Error tracking/observability
## Testing
- **Jest** — JavaScript/TypeScript testing
- **Pytest** — Python testing
- None (no test files present)
## Configuration Files
| File | Status |
|------|--------|
| `README.md` | Present — profile README |
| `tracepace/public/preview.png` | Present — preview image (1600×1280 PNG) |
| `.planning/` | Present — GSD planning directory |
| `package.json` | Not detected |
| `go.mod` / `go.sum` | Not detected |
| `requirements.txt` / `pyproject.toml` | Not detected |
| `Dockerfile` / `docker-compose.yml` | Not detected |
| `.env` / `.env.*` | Not detected |
| `.eslintrc*` / `.prettierrc*` | Not detected |
| `jest.config.*` / `vitest.config.*` | Not detected |
| `tsconfig.json` | Not detected |
## Platform Requirements
- **Development:** Node.js runtime, Python runtime, Go toolchain, Docker
- **Production:** Cloudflare (CDN/Turnstile), PostgreSQL, Redis, Temporal Server, Vercel or similar Next.js hosting
## Version Information
- TracePace: **v0.5.0-alpha** (public beta incoming)
- Next.js, React, Python, Go versions — not declared
<!-- GSD:stack-end -->

<!-- GSD:conventions-start source:CONVENTIONS.md -->
## Conventions

## Project Context
- Commit history (3 commits on `main`)
- README formatting and content structure
- Developer's stated professional experience and tooling choices
## Naming Patterns
- `README.md` — uppercase `README` per GitHub convention
- Image paths follow lowercase-with-hyphens: `tracepace/public/preview.png`
- No source code files present yet; based on stack (Next.js/TypeScript), expected file patterns are:
- Only `main` branch exists
- No feature/bugfix branch naming convention detected
- Imperative mood, lowercase: `init`, `Initial commit`, `refactor code structure for improved readability and maintainability`
- Author name: `Uzair` (local) / `uzair` (GitHub)
- Email: `uzairzahari@yahoo.com` / `62239643+uz6r@users.noreply.github.com`
## Commit Message Conventions
| Commit | Message |
|--------|---------|
| `cf28f41` | `Initial commit` |
| `97faf29` | `init` |
| `9ea8798` | `refactor code structure for improved readability and maintainability` |
- Lowercase, imperative mood, present tense
- Descriptive but concise (under 72 characters for subject line)
- One commit uses a `refactor` prefix — suggests a conventional commits style may be emerging
- No commit body / multi-line messages observed
## Code Style
- No linting config files found (`.eslintrc*`, `.prettierrc*`, `.editorconfig`, etc.)
- No `tsconfig.json`, `package.json`, `pyproject.toml`, `go.mod` — this repo has no application code
- No `.gitignore` or `.gitattributes` present
- **TypeScript/JavaScript:** ESLint + Prettier (standard Next.js/React ecosystem)
- **Python:** Pylint/Black/flake8 (common with SQLAlchemy/GraphQL projects)
- **Go:** `gofmt` / `go vet` (Go standard tooling)
- **CSS/Tailwind:** Tailwind CSS class ordering conventions
## README / Documentation Style
- ATX-style headings with space after `#`: `### about`, `### stack`
- Lowercase section headings (no title case): `### about` not `### About`
- No trailing punctuation on headings
- Horizontal rules `---` between major sections
- Code blocks with language specifiers: ```text, ```bash
- Badge-style links via `shields.io` with consistent parameters
- Div alignment with `<div align="center">` HTML tags
- Bullet lists with `- ` (hyphen + space)
- Italics for taglines: `*building things that don't break under pressure.*`
- Blockquotes `>` for featured descriptions
- Tables not used; content uses lists and sections
## Import Organization
- **TypeScript:** Group imports: (1) external packages, (2) internal modules, (3) relative imports. Use path aliases (common in Next.js with `@/` prefix)
- **Python:** Standard library → third-party → local; common in SQLAlchemy/GraphQL Strawberry projects
- **Go:** Standard `goimports` organization
## Error Handling
- **TypeScript:** Try/catch with typed errors; Sentry integration for observability
- **Python:** Exception hierarchy with structured logging; SQLAlchemy session management
- **Go:** Idiomatic `if err != nil` pattern; Temporal workflow error handling
## Logging
- **TypeScript:** `pino` or `winston` (common in Next.js backends)
- **Python:** `structlog` or standard `logging` (common with SQLAlchemy)
- **Go:** Standard `log` or `zerolog`
- **Observability:** Sentry explicitly mentioned in `README.md` stack section
## Module / Function Design
- **TypeScript:** Named exports preferred; single-responsibility functions; async/await for async operations
- **Python:** Module-level functions; SQLAlchemy repository pattern for data access
- **Go:** Interface-based design; explicit error returns; avoid panics
## Recommended Conventions to Establish
<!-- GSD:conventions-end -->

<!-- GSD:architecture-start source:ARCHITECTURE.md -->
## Architecture

## Pattern Overview
- **Single-page profile repo** — The root `README.md` is the sole deliverable for the profile purpose.
- **Side-project staging** — `tracepace/public/` stores a single preview image (`preview.png`) that the README embeds via a relative path.
- **Private monorepo described (not present)** — The README describes TracePace as a "go + next.js monorepo" but that codebase lives in a separate private repository.
- **Planning directory** — `.planning/codebase/` exists for codebase analysis documents (this file and STRUCTURE.md).
## Layers
- Purpose: Personal portfolio/profile display on GitHub
- Location: `/README.md`
- Contains: Bio, tech stack badges, shipped projects, side projects, writing links, current status
- Depends on: External badge services (shields.io), relative image path
- Used by: GitHub profile page viewer
- Purpose: Store public-facing assets for TracePace project
- Location: `tracepace/`
- Contains: `public/preview.png` — a preview/screenshot of the TracePace application
- Depends on: Nothing
- Used by: README.md (via relative Markdown image link)
- Architecture: Go + Next.js monorepo
- Contains: GPS activity visualization platform
- Key components described:
## Data Flow
## Key Abstractions
- Purpose: Single source of identity/portfolio for the developer
- Sections: `about`, `stack`, `things i've shipped`, `side projects`, `writing`, `currently`
- Pattern: Flat Markdown file with HTML divs for layout, badge image links for tech display
- Purpose: Namespace for TracePace-related content within this repo
- Contains: `public/` subdirectory with static assets
- Pattern: Follows Next.js conventions (public/ for static assets) even though Next.js is not configured in this repo
## Entry Points
- Location: `/README.md`
- Triggers: GitHub profile page load
- Responsibilities: Present developer identity, skills, shipped work, side projects, and current status
## (Inferred) TracePace Architecture — from README description
- Golang — GPS file parsing, RDP simplification, API logic
- GraphQL — API layer (likely using gqlgen or similar Go GraphQL library)
- Next.js — Frontend framework
- Framer Motion — Animation library for poster rendering/UI transitions
```
```
- Multiple poster themes (World Marathon Majors + local races)
- High-res PNG export
- Public beta incoming (version v0.5.0-alpha)
- Repository is private & invitational
## Error Handling
- Payment integrations with error handling, retry logic, transaction monitoring
- Temporal Go workflows for booking management
## Cross-Cutting Concerns
<!-- GSD:architecture-end -->

<!-- GSD:skills-start source:skills/ -->
## Project Skills

No project skills found. Add skills to any of: `.OpenCode/skills/`, `.agents/skills/`, `.cursor/skills/`, or `.github/skills/` with a `SKILL.md` index file.
<!-- GSD:skills-end -->

<!-- GSD:workflow-start source:GSD defaults -->
## GSD Workflow Enforcement

Before using edit, write, or other file-changing tools, start work through a GSD command so planning artifacts and execution context stay in sync.

Use these entry points:
- `/gsd-quick` for small fixes, doc updates, and ad-hoc tasks
- `/gsd-debug` for investigation and bug fixing
- `/gsd-execute-phase` for planned phase work

Do not make direct repo edits outside a GSD workflow unless the user explicitly asks to bypass it.
<!-- GSD:workflow-end -->



<!-- GSD:profile-start -->
## Developer Profile

> Profile not yet configured. Run `/gsd-profile-user` to generate your developer profile.
> This section is managed by `generate-OpenCode-profile` -- do not edit manually.
<!-- GSD:profile-end -->
