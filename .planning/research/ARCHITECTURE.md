# Architecture: GitHub Profile README Structure

**Project:** uz6r GitHub Profile README
**Researched:** 2026-05-25
**Mode:** Ecosystem (Architecture dimension)
**Confidence:** HIGH — consensus across 10+ sources (Codeboards.io, GitHub official docs, DEV, techinterview.org, multiple profile template repos)

---

## Recommended Architecture

The uz6r README already follows the industry-validated architecture — the task is content refresh, not structural rewrite. Below documents the current layout pattern, the rationale for each block, and the component boundaries that make the template maintainable.

### Section Organization & Flow

```
┌─────────────────────────────────────────┐
│           HERO BLOCK                    │
│  name · title · tagline (one-liner)     │
│  social badges (portfolio, linkedin,    │
│  medium, email, buymeacoffee)           │
├─────────────────────────────────────────┤
│           ABOUT SECTION                 │
│  2-3 sentence professional intro        │
│  current role, what i build, values     │
├─────────────────────────────────────────┤
│           STACK SECTION                 │
│  languages, frontend, backend & apis,   │
│  data & infra, auth & observability,    │
│  testing (shields.io badges by group)   │
├─────────────────────────────────────────┤
│           SHIPPED WORK                  │
│  bullet-point achievements with         │
│  impact metrics and tech context        │
├─────────────────────────────────────────┤
│           SIDE PROJECTS                 │
│  TracePace — featured project with      │
│  preview, status block, feature list    │
├─────────────────────────────────────────┤
│           WRITING                       │
│  blog posts with links and dates        │
├─────────────────────────────────────────┤
│           CURRENTLY BLOCK               │
│  location, role, exploring, training    │
├─────────────────────────────────────────┤
│           FOOTER                        │
│  closing tagline (centered)             │
└─────────────────────────────────────────┘
```

### Flow Rationale

| Section | Why This Position | What It Signals |
|---------|------------------|-----------------|
| **Hero** (top) | First 3 seconds — recruiters scan here first. Name + badges must be above the fold. | Identity, credibility, reachability |
| **About** (2nd) | After identity, answer "who is this person?" before showing tools. | Human context, current focus |
| **Stack** (3rd) | Tools validate the about section. Show breadth after establishing role. | Technical competence, breadth |
| **Shipped Work** (4th) | Concrete proof after tools. Impact metrics with tech context. | Delivery capability, scale |
| **Side Projects** (5th) | Personal initiative, separates day-job from passion. | Ownership, curiosity |
| **Writing** (6th) | Thought leadership, communication skills. Lower priority than code. | Communication, depth |
| **Currently** (7th) | Forward-looking signal. What they're into *now*. | Momentum, direction |
| **Footer** (bottom) | Memorable closer. Sticks after scrolling away. | Personality, values |

**Key principle:** The README tells a story: *who → what tools → what shipped → what's next*.

---

## Visual Structure Patterns

### Layout Primitives

The README uses three layout primitives:

| Pattern | Markdown | When |
|---------|----------|------|
| **Centered block** | `<div align="center">` | Hero, footer — needs visual isolation |
| **Section divider** | `---` (horizontal rule) | Between every major section for scannability |
| **Left-aligned flow** | Plain markdown sections with `###` headings | Body sections — hierarchy without decoration |

### Badge System

```markdown
[![Label](https://img.shields.io/badge/label-color?style=flat-square&logo=name&logoColor=white)](url)
```

- **Style**: `flat-square` (consistent across all badges)
- **Color**: Brand color for each service (LinkedIn blue, Gmail red, Medium black)
- **Logo**: First-party icon via `logo=` parameter
- **Groupings**: Stack is organized by category subheadings, not separated visually

### Typography Hierarchy

```
# H1 — Name (only in Hero)
### H3 — Section headings (about, stack, shipped, projects, writing, currently)
#### H4 — Sub-sections (TracePace, individual blog posts)
**bold** — Role title, emphasis
*italic* — Tagline, footer
```

No H2 used — the current H3 pattern is correct for the profile README context, as it avoids competing with pinned repo H1s.

### Divider Pattern

```
---
```

Single `<hr>` between every major section. No decorative dividers, no ASCII art, no extra spacing. Consistent, minimal, fast to scan.

---

## Component Boundaries

### Component: Hero Block

| Property | Value |
|----------|-------|
| **Responsibility** | Identity + links above the fold |
| **Contains** | Name (H1), role/tagline, up to 6 social badges |
| **Rendered in** | `<div align="center">` |
| **Update frequency** | Rare — only when role or contact info changes |
| **Known constraint** | Badge count should stay ≤6 to avoid horizontal overflow on mobile |

### Component: About Block

| Property | Value |
|----------|-------|
| **Responsibility** | 2-3 sentence professional introduction |
| **Contains** | Role description, current company, what I build |
| **Rendered in** | Plain markdown under `### about` |
| **Update frequency** | On role/company change, or project pivot |
| **Known constraint** | Employer name is intentionally vague per privacy preference |

### Component: Stack Block

| Property | Value |
|----------|-------|
| **Responsibility** | Show technical breadth organized by category |
| **Contains** | 6 sub-groups (languages, frontend, backend, data/infra, auth/observability, testing) |
| **Rendered in** | Plain markdown with subheadings, shield badges inline |
| **Update frequency** | Low — out of scope per PROJECT.md constraints |
| **Known constraint** | Badge wall problem — mitigated by group categorization |

### Component: Shipped Work Block

| Property | Value |
|----------|-------|
| **Responsibility** | Concrete proof of delivery — impact metrics + tech |
| **Contains** | Bullet-point achievements, each with: scale metric, technology used, business context |
| **Rendered in** | Plain markdown bullet list under `### things i've shipped` |
| **Update frequency** | Medium — add items when new features ship |

### Component: Side Projects Block

| Property | Value |
|----------|-------|
| **Responsibility** | Show personal initiative and ownership outside day job |
| **Contains** | Project name, tagline, description, preview image, status block, feature list, repo note |
| **Rendered in** | Plain markdown with `####` subheading, fenced text block for metadata |
| **Update frequency** | Medium — update versions, add projects |
| **Known constraint** | TracePace repo is private — must clearly communicate invitational access |

### Component: Writing Block

| Property | Value |
|----------|-------|
| **Responsibility** | Demonstrate communication skills, thought leadership |
| **Contains** | Intro sentence, linked article list with date |
| **Rendered in** | Plain markdown list under `### writing` |
| **Update frequency** | Medium — add when new articles publish, remove stale ones |
| **Known constraint** | Dates are publication dates — keep them current, remove old articles if list grows too long |

### Component: Currently Block

| Property | Value |
|----------|-------|
| **Responsibility** | Forward-looking signal — current role, interests, training |
| **Contains** | Location, role, exploring interests, training regimen |
| **Rendered in** | Fenced code block (monospace for scannability) |
| **Update frequency** | Medium — update interests, training goals |
| **Known constraint** | Must remove "open to" line per PROJECT.md |

### Component: Footer

| Property | Value |
|----------|-------|
| **Responsibility** | Memorable closer — sticks after scrolling |
| **Contains** | Italic tagline, centered |
| **Rendered in** | `<div align="center">` with `*italic*` |
| **Update frequency** | Very low — evergreen |

---

## Data Flow

```
PROJECT.md (requirements)
    │
    ▼
README.md (rendered output)
    │
    ├── Static content (most sections)
    │     └── Updated manually via edit commits
    │
    ├── Badge links
    │     └── shields.io URLs, parameters hardcoded
    │
    └── Preview image (TracePace)
          └── Local path: tracepace/public/preview.png
```

No dynamic/content automation (GitHub Actions, blog auto-fetch, etc.) — all content is static markdown. This is correct for this profile's scope.

---

## Patterns to Follow

### Pattern 1: Category-Grouped Badges
**What:** Organize tech stack badges into labeled sub-groups (languages, frontend, backend, etc.) rather than one flat list.
**Why:** Prevents "badge wall" — recruiters can scan by domain of interest.
**Current implementation:** 6 groups with clear subheadings — already correct.

### Pattern 2: Impact-First Bullet Points
**What:** Each achievement starts with an impact signal (metric, user scale, business outcome), followed by the tech used.
**Why:** Recruiters scan for scale and results before technology.
**Format:** `⚡ [impact] with [context] using [tech]`
**Current implementation:** Already follows this pattern (e.g., "scaled from 97k → 700k+").

### Pattern 3: Project Status Block
**What:** A fenced text block with key-value pairs for project metadata.
**Why:** Quick reference — version, status, tech, features — without narrative prose.
**Format:**
```text
status    : public beta incoming
version   : v0.5.0-alpha
tech      : golang · graphql · next.js · framer-motion
```
**Current implementation:** Used for TracePace — pattern to replicate for future projects.

### Pattern 4: Monospace Currently Block
**What:** Use a fenced code block for the "currently" section.
**Why:** Visually distinct from narrative sections; monospace reads as structured data.
**Current implementation:** Already used — keep this pattern.

---

## Anti-Patterns to Avoid

### Anti-Pattern 1: Stats Widgets Without Context
**What:** Raw GitHub stats cards (commits, streaks, language pie) without explanation.
**Why bad:** Numbers without narrative are noise. They show activity, not impact.
**Instead:** The "things i've shipped" section provides *meaningful* metrics with business context. No stats widgets needed.

### Anti-Pattern 2: Typing Animation / Banner GIFs
**What:** ASCII typing text, animated banners, or capsule-render SVG headers.
**Why bad:** Visual noise. Animated elements don't contribute to recruiter signal. Read as junior (per techinterview.org 2026 research).
**Instead:** Clean, static hero block with bold text hierarchy. Current implementation already avoids this — keep it that way.

### Anti-Pattern 3: Visitor Counters
**What:** "Profile views" counters.
**Why bad:** Useless vanity metric. Doesn't tell anyone anything useful.
**Instead:** Don't add.

### Anti-Pattern 4: Wall of Badges (Uncategorized)
**What:** 40+ badges in a single row/block with no grouping.
**Why bad:** Overwhelming to scan, implies inability to prioritize. Recruiters want to know your *core* stack.
**Instead:** Category groupings (current implementation is correct).

### Anti-Pattern 5: Stale/Generic Template Sections
**What:** "🔭 I'm currently working on", "🌱 I'm currently learning", "💬 Ask me about" with empty or default content.
**Why bad:** Reads as a template that wasn't customized. Signals inactive profile.
**Instead:** The current "currently" code block with specific content — keep it custom and specific.

---

## Scalability Considerations

| Concern | Current State (1 page) | Near Future (6-12 months) | Guidance |
|---------|----------------------|--------------------------|----------|
| **Section count** | 8 blocks | 8-10 blocks | Keep ≤10. If growing, consolidate (e.g., merge writing + speaking). |
| **Badge count** | ~40 badges across 6 groups | ~50 across same groups | Add by filling gaps in existing groups, not creating new groups. |
| **Shipped items** | 8 bullets | 10-12 bullets | Cap at 10-12. Archive oldest items when adding new ones. |
| **Writing items** | 2 articles | 3-5 articles | Cap at 5 articles, keep most recent. Archive older to a blog. |
| **Side projects** | 1 (TracePace) | 1-3 | Feature max 2-3. Each gets a status block + image. |

**Sizing rule:** A profile README should be scannable in ≤30 seconds (per Codeboards.io 2026). Current README is ~135 lines of markdown — this is the upper bound. Keep it tight.

---

## Suggested Build Order (Content Update)

This architecture reflects an *update* pass, not a greenfield build. The section ordering is fixed; the content within specific blocks changes.

### Phase 1: Content Refresh (Addressing PROJECT.md Active Items)

| Order | Block | Change | Complexity |
|-------|-------|--------|------------|
| 1 | About | Update employer: "courtsite" → "a leading Malaysian digital bank/fintech" | Low |
| 2 | Currently | Remove "open to" line, update role to "software engineer @ digital bank" | Low |
| 3 | Shipped Work | Add "Emergency Reschedule Request" item | Low |
| 4 | Side Projects | Update TracePace status to "launched", version to "v1.0.0", add tracepace.app link | Low |
| 5 | Writing | Remove "playing the long game", add "i train in blocks, i build the same way" | Low |

### Phase 2: Polish

| Order | Block | Change | Complexity |
|-------|-------|--------|------------|
| 6 | About | Update TracePace description from present-to-build to present-as-shipped | Low |
| 7 | Stack | (Out of scope per PROJECT.md — skip) | — |

### Phase 3: Future

| Order | Block | Change | Complexity |
|-------|-------|--------|------------|
| 8 | Shipped Work | Add new items as they ship (ongoing) | Low |
| 9 | Writing | Cycle articles as new posts publish (ongoing) | Low |
| 10 | Side Projects | Add/update projects as they launch | Low |

---

## Sources

- [Codeboards.io — GitHub Profile README Guide (2026)](https://codeboards.io/blog/github-profile-readme-guide) — HIGH confidence: current, comprehensive, confirms section ordering
- [GitHub Official Docs — Using your profile to enhance your resume](https://github.com/github/docs/blob/main/content/account-and-profile/tutorials/using-your-github-profile-to-enhance-your-resume.md) — HIGH confidence: authoritative source from GitHub itself
- [techinterview.org — What Recruiters Click On (2026)](https://www.techinterview.org/post/3233474626/github-profile-engineers/) — MEDIUM confidence: aligns with official docs, adds recruiter-side perspective
- [ButHonestly.io — README That Feels Like You (2026)](https://buthonestly.io/web/how-to-build-a-github-profile-readme-that-feels-like-you/) — MEDIUM confidence: validates modular section approach
- [Xeito — GitHub Profile for Remote Jobs (2026)](https://xeito.ai/en/blog/github-profile-remote-developer-jobs-2026/) — MEDIUM confidence: validates opening hook and impact metrics
- [Git to Hire Blog — Optimize Profile for Job Hunting (2026)](https://gittohire.com/blog/optimize-github-profile-job-hunting-2026) — MEDIUM confidence: mirrors consensus structure
- [flyingsquirrel0419/awesome-git-profile](https://github.com/flyingsquirrel0419/awesome-git-profile) — MEDIUM confidence: template marketplace with 50+ tools, confirms structural patterns
- [Awesome GitHub README](https://github.com/yerdaulet-damir/awesome-github-readme) — MEDIUM confidence: curated collection, validates layout patterns
- Current README.md at `/home/uzer/uz6r/uz6r/README.md` — HIGH confidence: baseline context
- PROJECT.md at `/home/uzer/uz6r/uz6r/.planning/PROJECT.md` — HIGH confidence: requirements source

---

## Confidence Assessment

| Area | Confidence | Notes |
|------|------------|-------|
| Section organization | HIGH | Consensus across 10+ independent sources, consistent with GitHub's own docs |
| Visual patterns | HIGH | Markdown primitives are well-documented; current implementation aligns |
| Flow rationale | HIGH | "Who → tools → proof → what's next" is the dominant industry pattern |
| Component boundaries | MEDIUM | Components are logical sections, not code — boundaries are defined by content scope |
| Build order | MEDIUM | Logical dependency ordering based on what changes first (content freshness) vs what stays (structure) |
