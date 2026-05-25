# Coding Conventions

**Analysis Date:** 2026-05-25

## Project Context

This is a personal GitHub profile README repository. No source code files are present in the repo itself. The developer's stated stack (from `README.md`) spans TypeScript, Python, Go, JavaScript, Bash, Next.js, React, Vue, GraphQL, and PostgreSQL. The following conventions are inferred from:
- Commit history (3 commits on `main`)
- README formatting and content structure
- Developer's stated professional experience and tooling choices

## Naming Patterns

**Files:**
- `README.md` — uppercase `README` per GitHub convention
- Image paths follow lowercase-with-hyphens: `tracepace/public/preview.png`
- No source code files present yet; based on stack (Next.js/TypeScript), expected file patterns are:
  - `*.ts`, `*.tsx` for TypeScript source
  - `*.py` for Python source
  - `*.go` for Go source

**Git Branches:**
- Only `main` branch exists
- No feature/bugfix branch naming convention detected

**Commits:**
- Imperative mood, lowercase: `init`, `Initial commit`, `refactor code structure for improved readability and maintainability`
- Author name: `Uzair` (local) / `uzair` (GitHub)
- Email: `uzairzahari@yahoo.com` / `62239643+uz6r@users.noreply.github.com`

## Commit Message Conventions

**Detected pattern (from git log):**
```
<type(optional)> <short description>
```

Examples from history:
| Commit | Message |
|--------|---------|
| `cf28f41` | `Initial commit` |
| `97faf29` | `init` |
| `9ea8798` | `refactor code structure for improved readability and maintainability` |

**Inferred convention:**
- Lowercase, imperative mood, present tense
- Descriptive but concise (under 72 characters for subject line)
- One commit uses a `refactor` prefix — suggests a conventional commits style may be emerging
- No commit body / multi-line messages observed

**Recommended convention (align with professional experience):**
```
<type>: <imperative description>

<optional body>
```

Where `type` is one of: `feat`, `fix`, `refactor`, `chore`, `docs`, `test`, `style`, `perf`, `ci`.

Matches common patterns in the developer's stated stack (GitHub Actions CI, professional full-stack work).

## Code Style

**Linting/Formatting:**
- No linting config files found (`.eslintrc*`, `.prettierrc*`, `.editorconfig`, etc.)
- No `tsconfig.json`, `package.json`, `pyproject.toml`, `go.mod` — this repo has no application code
- No `.gitignore` or `.gitattributes` present

**Expected formatting conventions (based on stated stack):**
- **TypeScript/JavaScript:** ESLint + Prettier (standard Next.js/React ecosystem)
- **Python:** Pylint/Black/flake8 (common with SQLAlchemy/GraphQL projects)
- **Go:** `gofmt` / `go vet` (Go standard tooling)
- **CSS/Tailwind:** Tailwind CSS class ordering conventions

## README / Documentation Style

**Markdown conventions observed in `README.md`:**
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

**Tone:** Professional, concise, personal-brand focused.
**Structure pattern:** About → Stack → Experience → Projects → Writing → Currently

## Import Organization

**No import statements exist in the repo.** When code is added, the following conventions are expected based on the developer's stack:

- **TypeScript:** Group imports: (1) external packages, (2) internal modules, (3) relative imports. Use path aliases (common in Next.js with `@/` prefix)
- **Python:** Standard library → third-party → local; common in SQLAlchemy/GraphQL Strawberry projects
- **Go:** Standard `goimports` organization

## Error Handling

**No error handling code found.** Expected patterns based on stated experience:

- **TypeScript:** Try/catch with typed errors; Sentry integration for observability
- **Python:** Exception hierarchy with structured logging; SQLAlchemy session management
- **Go:** Idiomatic `if err != nil` pattern; Temporal workflow error handling

## Logging

**No logging implementation found.** Expected framework based on stated stack/experience:
- **TypeScript:** `pino` or `winston` (common in Next.js backends)
- **Python:** `structlog` or standard `logging` (common with SQLAlchemy)
- **Go:** Standard `log` or `zerolog`
- **Observability:** Sentry explicitly mentioned in `README.md` stack section

## Module / Function Design

**Will be established when source code is added.** Recommendations based on stack:

- **TypeScript:** Named exports preferred; single-responsibility functions; async/await for async operations
- **Python:** Module-level functions; SQLAlchemy repository pattern for data access
- **Go:** Interface-based design; explicit error returns; avoid panics

## Recommended Conventions to Establish

Given this is a starter / profile repo with no source code yet, the following conventions should be codified when code is added:

1. **Conventional Commits** for commit messages (aligns with `refactor:` prefix already used)
2. **ESLint + Prettier** config for TypeScript/JavaScript (consistent with Next.js ecosystem)
3. **TypeScript strict mode** — `strict: true` in tsconfig
4. **Pre-commit hooks** via husky/lint-staged (common in professional Next.js projects)
5. **Python type hints** — mypy or pyright for type checking (matches `sqlalchemy` + `graphql` usage)
6. **Go** — standard `gofmt`, `go vet`, `golangci-lint`
7. **Environment variable management** via `.env.local` pattern (Next.js convention) or `.env.example` for Python projects
8. **`README.md` conventions** should serve as the documentation template for all sub-projects: lowercase headings, consistent badge style, sectioned layout

---

*Convention analysis: 2026-05-25*
