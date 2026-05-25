# Technology Stack — GitHub Profile README

**Project:** uz6r/uz6r (GitHub Profile README)
**Researched:** 2026-05-25
**Mode:** Ecosystem (Stack dimension)
**Overall confidence:** HIGH

---

## Executive Summary

The GitHub profile README stack in 2026 is minimal and stable. There are no frameworks to install. The "stack" consists of markdown, a badge service, optional dynamic stat cards, and optional GitHub Actions automation. The key recommendation is **shields.io for badges** (de facto standard, 26k+ stars, 1.6B images/month) with **Simple Icons** for brand logos, and **github-readme-stats via GitHub Actions** for dynamic stats (the public Vercel instance is now officially documented as unreliable). For blog post automation, **gautamkrishnar/blog-post-workflow** pulls RSS feeds into the README via scheduled Actions.

The 2026 consensus from recruiters is clear: **clean and scannable beats flashy**. Visitor counters, snake animations, typing SVGs, and animated GIF banners are explicitly called out as detrimental by multiple hiring-focused guides. The existing uz6r README already follows most best practices — the stack recommendations here are primarily about what *not* to add, and where selective automation adds real value.

---

## Recommended Stack

### Badge Service (Core)
| Technology | Version | Purpose | Why |
|------------|---------|---------|-----|
| [Shields.io](https://shields.io/) | N/A (cloud service) | Static & dynamic badges | De facto standard. 26k+ GitHub stars, 1.6B images/month. Powers the vast majority of profile README badges. Used by VS Code, Vue.js, Bootstrap. |
| [Simple Icons](https://simpleicons.org/) | v16.21.0 (May 2026) | Brand icon set for badge logos | 3300+ brand SVG icons. Shields.io sources its `logo` parameter from here. Also available as standalone CDN at `cdn.simpleicons.org/[SLUG]`. |

**How to use shields.io for profile badges:**

```markdown
<!-- Static badge: https://img.shields.io/badge/LABEL-MESSAGE-COLOR -->
[![LinkedIn](https://img.shields.io/badge/linkedin-uzairzahari-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/uzairzahari)

<!-- With Simple Icons logo -->
![TypeScript](https://img.shields.io/badge/typescript-3178C6?style=flat-square&logo=typescript&logoColor=white)
```

**Style choice:** `flat-square` — matches the current README. Consistent, professional, minimal visual weight. Do NOT use `for-the-badge` (too bulky for profile READMEs).

### Dynamic Stats Cards (Optional, Recommended)
| Technology | Version | Purpose | Why |
|------------|---------|---------|-----|
| [github-readme-stats](https://github.com/anuraghazra/github-readme-stats) | Latest (79k stars) | GitHub stats & language cards | Most popular stats card generator. Supports themes, layouts, per-card customization. |
| [readme-tools/github-readme-stats-action](https://github.com/readme-tools/github-readme-stats-action) | v1 | GitHub Actions wrapper | **Officially recommended** deployment method as of Jan 2026. Generates static SVGs in-repo, avoiding public API rate limits. |

**Important:** The public Vercel instance at `https://github-readme-stats.vercel.app/api` is **officially documented as unreliable** due to rate limits and traffic spikes (see [issue #1471](https://github.com/anuraghazra/github-readme-stats/issues/1471)). The project maintainers now recommend:
1. **GitHub Actions (simplest)** — generates static SVGs committed to repo, updated on schedule
2. **Self-hosted Vercel** — more work, fresher stats, needs PAT

**For uz6r, use the GitHub Actions approach:**

Create `.github/workflows/update-stats.yml` in the profile repo:

```yaml
name: Update GitHub Stats Cards

on:
  schedule:
    - cron: "0 3 * * *"   # Daily at 3am UTC
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Generate stats card
        uses: readme-tools/github-readme-stats-action@v1
        with:
          card: stats
          options: username=uz6r&show_icons=true&theme=default&hide_title=true
          path: profile/stats.svg
          token: ${{ secrets.GITHUB_TOKEN }}

      - name: Generate top languages card
        uses: readme-tools/github-readme-stats-action@v1
        with:
          card: top-langs
          options: username=uz6r&layout=compact&hide=html,css
          path: profile/top-langs.svg
          token: ${{ secrets.GITHUB_TOKEN }}

      - name: Commit cards
        run: |
          git config user.name "github-actions[bot]"
          git config user.email "github-actions[bot]@users.noreply.github.com"
          git add profile/*.svg
          git commit -m "chore: update GitHub stats cards" || exit 0
          git push
```

Then embed in README.md:

```markdown
![GitHub Stats](./profile/stats.svg)
![Top Languages](./profile/top-langs.svg)
```

### Blog Post Automation (Optional, Recommended for uz6r)
| Technology | Version | Purpose | Why |
|------------|---------|---------|-----|
| [gautamkrishnar/blog-post-workflow](https://github.com/gautamkrishnar/blog-post-workflow) | v1 | RSS feed → README | Most popular blog-to-README action. Works with Medium RSS. Uses HTML comment markers. 5k+ stars. |

**Why this fits uz6r:** The README already has a "writing" section with manually listed Medium posts. Automating this removes a maintenance task and keeps the profile fresh without manual edits. Medium's RSS feed is `https://medium.com/feed/@uz6r`.

Workflow (`.github/workflows/update-blog-posts.yml`):

```yaml
name: Update Blog Posts

on:
  schedule:
    - cron: "0 6 * * 1"   # Weekly on Monday at 6am UTC
  workflow_dispatch:

permissions:
  contents: write

jobs:
  update-readme-with-blog:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: gautamkrishnar/blog-post-workflow@v1
        with:
          feed_list: "https://medium.com/feed/@uz6r"
          max_post_count: 5
          template: "- [$title]($url) · $date"
          date_format: "mmm yyyy"
```

In README.md, replace the blog list with:

```markdown
<!-- BLOG-POST-LIST:START -->
<!-- BLOG-POST-LIST:END -->
```

### Formatting / Markdown
| Technology | Purpose | Why |
|------------|---------|------|
| Native GitHub Markdown + HTML | Content formatting | GitHub renders markdown with HTML support. No preprocessor needed. The existing README uses `<div align="center">` which is correct. |
| [Prettier](https://prettier.io/) (optional) | Markdown formatting | If automation is added, pin a `.prettierrc` for markdown to keep formatting consistent. Not essential — the README is manually edited. |

---

## Alternatives Considered & Rejected

| Category | Recommended | Alternative | Why Not |
|----------|-------------|-------------|---------|
| **Stats cards** | github-readme-stats (GH Actions) | Public Vercel instance | Officially unreliable. Rate limits cause broken images. |
| **Stats cards** | github-readme-stats | [lowlighter/metrics](https://github.com/lowlighter/metrics) | More feature-rich but significantly more complex. Overkill for a profile README. 16k+ vs 79k stars. |
| **Stats cards** | github-readme-stats | [Codeboards.io badge](https://codeboards.io/) | Newer service, less established. Vendor lock-in. Not open source. |
| **Badges** | shields.io | Badges4-README (Ileriayo/markdown-badges) | Pre-made badge collection, but shields.io gives full control over colors and logos. Badges4-README is just a curated list of shields.io URLs. |
| **Badges** | shields.io | [Aveek-Saha/GitHub-Profile-Badges](https://home.aveek.io/GitHub-Profile-Badges/) | Nice curated collection with consistent styling, but adds a dependency on an external site for badge URLs. Shields.io is more direct. |
| **Animated header** | None (reject) | [capsule-render](https://github.com/kyechan99/capsule-render) | Animated gradient headers are flashy and unserious. Explicitly called out as a negative signal by 2026 recruiting guides. |
| **Typing animation** | None (reject) | [readme-typing-svg](https://github.com/DenverCoder1/readme-typing-svg) | Animated typing text distracts from content. Seen as "MySpace-era" design. |
| **Snake animation** | None (reject) | [Platane/snk](https://github.com/Platane/snk) | Contribution snake GIF is a gimmick. Adds zero informational value. |
| **Visitor counter** | None (reject) | [komarev/ghpvc](https://github.com/antonkomarev/github-profile-views-counter) | Multiple 2026 recruiting sources explicitly call visitor counters a negative signal — "insecure, not successful." |
| **README generator** | None (manual) | [rahuldkjain/gh-profile-readme-generator](https://rahuldkjain.github.io/gh-profile-readme-generator/) | Generates generic, template-y profiles. The existing README is well-written and authentic. A generator would homogenize it. |

---

## Complete Recommended Setup for uz6r

### What to keep from current README
- **shields.io badges** for links and tech stack — already correct
- **flat-square style** — clean, consistent
- **Category grouping** (languages, frontend, backend, etc.) — good scannability
- **"things i've shipped"** section with real metrics — high signal
- **Side projects section** with TracePace details — shows active building
- **Writing section** (just needs automation)
- **Currently section** (just needs content updates per PROJECT.md)

### What to add
1. **GitHub Actions workflow** for weekly stats card generation (low effort, high signal)
2. **GitHub Actions workflow** for Medium blog post auto-updates (eliminates manual list maintenance)
3. **Stats card SVGs** embedded in README (shows activity, languages)

### What NOT to add
- Visitor counter ❌
- Snake animation ❌
- Typing SVG animation ❌
- Animated header banner ❌
- Rainbow of badges ❌
- Codeboards or other third-party stats services ❌

### GitHub Secrets needed (if automation is added)
| Secret | Source | Purpose |
|--------|--------|---------|
| `GITHUB_TOKEN` | Auto-provided by GitHub Actions | Stats card generation |
| No additional secrets needed | — | blog-post-workflow uses the Medium RSS feed (public, no auth) |

### Workflow summary
| Workflow | Schedule | Purpose |
|----------|----------|---------|
| `update-stats.yml` | Daily at 3am UTC | Regenerate GitHub stats SVGs |
| `update-blog-posts.yml` | Weekly on Monday | Pull latest Medium posts into README |

---

## Sources

1. **Shields.io** — 26k+ stars, 1.6B images/month. Source: [GitHub](https://github.com/badges/shields/) and [shields.io](https://shields.io/). Confidence: **HIGH**
2. **Simple Icons** — v16.21.0 (May 24, 2026). Source: [npm](https://registry.npmjs.org/simple-icons). Confidence: **HIGH**
3. **github-readme-stats** — 79k stars. Public instance unreliable; GH Actions recommended. Source: [GitHub README](https://github.com/anuraghazra/github-readme-stats#github-actions-recommended). Confidence: **HIGH**
4. **github-readme-stats-action** — v1, recommended deployment method. Source: [commit 5df91f9](https://github.com/anuraghazra/github-readme-stats/commit/5df91f9bfa89c356a55cbb3c2bbc164fdbf94a86). Confidence: **HIGH**
5. **blog-post-workflow** — v1, Medium RSS feed support. Source: [GitHub README](https://github.com/gautamkrishnar/blog-post-workflow). Confidence: **HIGH**
6. **Recruiter expectations 2026** — Multiple sources: [Codeboards.io](https://codeboards.io/blog/github-profile-readme-guide), [techinterview.org](https://www.techinterview.org/post/3233474626/github-profile-engineers/), [xeito.ai](https://xeito.ai/en/blog/github-profile-remote-developer-jobs-2026/), [gittohire.com](https://gittohire.com/blog/optimize-github-profile-job-hunting-2026). All agree on clean > flashy. Confidence: **HIGH**

---

## Confidence Assessment

| Area | Confidence | Notes |
|------|------------|-------|
| Badge service (shields.io) | **HIGH** | De facto standard, verified via official docs and GitHub stats |
| Stats cards (github-readme-stats) | **HIGH** | 79k stars, verified via official docs; public instance reliability warning confirmed |
| GitHub Actions approach | **HIGH** | Documented in project README as recommended method as of Jan 2026 |
| Blog automation (blog-post-workflow) | **HIGH** | 5k+ stars, active maintenance, verified Medium RSS support |
| What to avoid (visitor counters, animations) | **HIGH** | Consistent across 4+ recruiting-focused 2026 guides |
| Rejected alternatives | **MEDIUM** | Some based on star counts and community consensus rather than personal testing |
