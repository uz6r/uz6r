# Codebase Structure

**Analysis Date:** 2026-05-25

## Directory Layout

```
uz6r/                           # GitHub profile repo root
├── .git/                       # Git version control (standard)
├── .planning/                  # Planning and analysis artifacts
│   └── codebase/               # Codebase analysis documents
│       ├── ARCHITECTURE.md     # This file — architecture analysis
│       └── STRUCTURE.md        # This file — structure analysis
├── tracepace/                  # TracePace project namespace (placeholder)
│   └── public/                 # Static assets (Next.js convention)
│       └── preview.png         # TracePace preview/screenshot image
├── .gitignore                  # (not present — no generated/ignored files exist yet)
└── README.md                   # GitHub profile README (single source)
```

## Directory Purposes

**Root (`/`):**
- Purpose: GitHub special profile repository (`uz6r/uz6r`) — the README renders as the developer's GitHub profile page
- Contains: Profile README, TracePace asset directory, planning artifacts
- Key files: `README.md`

**`tracepace/`:**
- Purpose: Namespace directory for TracePace project assets that need to be publicly accessible via GitHub's raw content serving
- Contains: `public/` subdirectory only
- Status: Placeholder structure — mirrors a Next.js project's `public/` directory convention even though no Next.js build system exists in this repo
- Key files: None beyond the image

**`tracepace/public/`:**
- Purpose: Static asset directory (convention from Next.js)
- Contains: Single image file (`preview.png`)
- Key files: `preview.png` — 598 KB PNG image showing a preview of the TracePace application
- Note: Named to match Next.js convention, likely so asset paths used in this repo can be transferred directly to the real TracePace Next.js app

**`.planning/`:**
- Purpose: Repository for planning, analysis, and workflow artifacts
- Contains: `codebase/` subdirectory with codebase analysis documents
- Status: Active — documents here are consumed by GSD (Guided Software Development) workflow commands

**`.planning/codebase/`:**
- Purpose: Codebase analysis documents written by `gsd-map-codebase` command
- Contains: ARCHITECTURE.md, STRUCTURE.md (+ future documents from other focus areas)
- Status: Active

## Key File Locations

**Profile Source:**
- `README.md`: The sole source file for the GitHub profile page. Contains all content including bio, badges, work history, side projects, and links.

**Project Asset:**
- `tracepace/public/preview.png`: Preview image for the TracePace GPS visualization platform, embedded in README via `![TracePace Preview](tracepace/public/preview.png)`.

**Analysis Documents:**
- `.planning/codebase/ARCHITECTURE.md`: Architecture analysis (this session)
- `.planning/codebase/STRUCTURE.md`: Structure analysis (this session)

## Naming Conventions

**Files:**
- `README.md` — GitHub-standard naming for profile repository README (UPPERCASE, no extension variant)
- `*.md` — Markdown files use UPPERCASE for root-level special files (`README.md`), lowercase with underscores for analysis documents (`ARCHITECTURE.md`, `STRUCTURE.md` under `.planning/`)
- `preview.png` — Lowercase descriptive name for image assets

**Directories:**
- `.planning/` — Dot-prefixed for "hidden"/metadata directory
- `tracepace/` — Lowercase project name
- `public/` — Lowercase, follows Next.js/static-web convention
- `codebase/` — Lowercase descriptive name

## Where to Add New Code

**New Profile Content:**
- Edit `README.md` — add new sections, update badges, revise bio

**New TracePace Assets:**
- Add to `tracepace/public/` — e.g., additional preview images, demo GIFs, screenshots
- Reference in `README.md` via relative Markdown image link

**New Analysis Documents:**
- Add to `.planning/codebase/` — named `CONVENTIONS.md`, `TESTING.md`, `STACK.md`, `INTEGRATIONS.md`, `CONCERNS.md` depending on focus area

**Future TracePace Source Code:**
- Will NOT be placed in this repository. The README states "repo is private & invitational" — TracePace lives in a separate, private repository.
- Based on the README description, the private monorepo structure is expected to contain:
  - `apps/web/` or `frontend/` — Next.js application with Framer Motion
  - `apps/api/` or `backend/` — Go GraphQL server
  - `pkg/parser/` — Custom Go binary parser for FIT/GPX files
  - `pkg/rdp/` — RDP path simplification implementation
  - `pkg/renderer/` — Poster theme rendering engine
  - `pkg/export/` — High-res PNG export with aspect ratio options

## Special Directories

**`.git/`:**
- Purpose: Standard Git version control data
- Generated: Yes (by `git init`)
- Committed: No (VCS metadata)

**`.planning/`:**
- Purpose: GSD workflow artifacts and codebase analysis
- Generated: Yes (by GSD commands like `gsd-map-codebase`)
- Committed: Yes — these documents are part of the project knowledge base and consumed by other GSD commands

**`tracepace/`:**
- Purpose: Public-facing asset staging for the TracePace project
- Generated: No (manually created)
- Committed: Yes — assets need to be available via GitHub's raw content serving
- Status: Placeholder — contains only a single preview image at this stage

---

*Structure analysis: 2026-05-25*
