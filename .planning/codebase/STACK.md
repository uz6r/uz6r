# Technology Stack

**Analysis Date:** 2026-05-25

## Overview

This repository is a personal profile / portfolio README (`README.md`) belonging to **uzair zahari** (uz6r). It describes the developer's technology stack and projects. The key project referenced but **not hosted here** is **TracePace** — a GPS activity visualization platform (described as a "private & invitational" repo at v0.5.0-alpha).

The `.planning/codebase/` directory exists for GSD mapping output. `tracepace/public/preview.png` is a single preview image asset.

## Languages

**Declared in README (not detected as source files in this repo):**
- **TypeScript** — Primary language for frontend/backend
- **Python** — Backend API (with SQLAlchemy, GraphQL Strawberry)
- **Go** — TracePace backend (custom .fit/.gpx binary parser, RDP algorithm)
- **JavaScript** — General web development
- **Bash** — Scripting

**Detected in this repository:**
- None (no source code files present)

## Runtime

**Declared:**
- Node.js (via Next.js) — inferred from the Next.js/TypeScript frontend stack
- Python 3.x — inferred from SQLAlchemy/pytest usage

**Package Managers:**
- **npm** or **yarn** — inferred from Next.js/TypeScript usage
- **pip** or **poetry** — inferred from Python/SQLAlchemy usage
- **go mod** — inferred from Go usage in TracePace

**No lockfiles or package manifests detected** in this repository.

## Frameworks

**Frontend (declared in README):**
- **Next.js** — React meta-framework (primary frontend for both courtsite work and TracePace)
- **React** — UI library
- **Vue.js** — Secondary/prior experience
- **Nuxt.js** — Vue meta-framework, secondary experience
- **Tailwind CSS** — Utility-first CSS framework
- **Vite** — Build tool/dev server
- **framer-motion** — Animation library for TracePace

**Backend (declared in README):**
- **GraphQL** — API layer (with **Strawberry** Python GraphQL library for courtsite)
- **SQLAlchemy** — Python ORM (courtsite backend)
- **REST APIs** — General backend experience
- **Go standard library** — For TracePace custom binary parser

**Workflow Engine:**
- **Temporal** — Workflow orchestration (Go + Temporal for booking workflows)

## Data & Infrastructure

**Declared in README:**
- **PostgreSQL** — Primary database
- **Redis** — Caching/message broker
- **Docker** — Containerization
- **Temporal** — Durable execution engine
- **GitHub Actions** — CI/CD
- **Cloudflare** — CDN, Turnstile, DNS

## Auth & Observability

**Declared in README:**
- **JWT** — JSON Web Token auth
- **OAuth** — OAuth 2.0 (Google provider inferred)
- **Sentry** — Error tracking/observability

## Testing

**Declared in README:**
- **Jest** — JavaScript/TypeScript testing
- **Pytest** — Python testing

**Detected in this repository:**
- None (no test files present)

## Configuration Files

**Detected in this repository:**
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

**Inferred from README:**
- **Development:** Node.js runtime, Python runtime, Go toolchain, Docker
- **Production:** Cloudflare (CDN/Turnstile), PostgreSQL, Redis, Temporal Server, Vercel or similar Next.js hosting

## Version Information

**Explicitly stated:**
- TracePace: **v0.5.0-alpha** (public beta incoming)

**Not specified (all inferred from README badges):**
- Next.js, React, Python, Go versions — not declared

---

*Stack analysis: 2026-05-25 — Based solely on `README.md` declarations and repository inspection. No actual source code, configuration files, or dependency manifests exist in this repository. All stack information is self-reported via README badges and text.*
