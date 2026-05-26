# Phase 2: Polish & Differentiation - Context

**Gathered:** 2026-05-25
**Status:** Ready for planning

<domain>
## Phase Boundary

Add visual polish and differentiation to the GitHub profile README: a GitHub stats card, emphasis on shipped work, and a closing CTA. Only affects visual presentation — no content changes or structural additions. Phase 1 content is already applied and must remain intact.

</domain>

<decisions>
## Implementation Decisions

### GitHub Stats Card
- **D-01:** Use full profile card via `github-readme-stats` GitHub Actions wrapper (not public Vercel instance)
- **D-02:** Card placed after the About section, before the stack section
- **D-03:** Dark theme (`&theme=dark`)
- **D-04:** Show full metrics: stars, commits, PRs, repos, streak graph, top languages

### Shipped Work Emphasis
- **D-05:** Raise heading from `### things i've shipped` to `## things i've shipped`
- **D-06:** No other visual changes to the section (emoji bullets, descriptions remain)

### Closing CTA
- **D-07:** Keep existing tagline "building things that don't break under pressure" — no change needed
- **D-08:** No new link or call-to-action added

### OpenCode's Discretion
- Exact GitHub Actions workflow configuration (schedule, caching, output format)
- Stats card exact layout: side-by-side columns or stacked
- Whether to hide certain repos from stats (if any private repos)

</decisions>

<canonical_refs>
## Canonical References

### Source documents
- `README.md` — The file being modified (current state already includes Phase 1 updates)
- `.planning/PROJECT.md` — Project context and constraints
- `.planning/REQUIREMENTS.md` — Requirement definitions (POL-01 through POL-03)
- `.planning/research/SUMMARY.md` — Research findings: `github-readme-stats` via GH Actions, not public Vercel instance

### Phase 1 context
- `.planning/phases/01-content-refresh/01-CONTEXT.md` — Prior decisions that must remain intact

No external specs — requirements fully captured in decisions above.

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets
- `README.md` — Single markdown file to edit
- `.github/` directory — None exists yet, will need to be created for GH Actions workflow

### Established Patterns
- ATX headings with lowercase: `### about`, `### stack`
- Horizontal rules `---` between sections
- shields.io badges with `flat-square` style
- Code blocks with \`\`\`text specifiers
- Blog section references GitHub Actions automation as v2 (deferred)

### Integration Points
- After About section → insertion point for stats card markdown
- `.github/workflows/` — needs creation for GH Actions workflow to generate stats

</code_context>

<specifics>
## Specific Ideas

- Stats card should use `readme-tools/github-readme-stats-action@v1` or inline markdown with query params
- Dark theme aligns with GitHub dark mode default
- Full profile card typically uses two images side by side: stats card + top langs card
- The "things i've shipped" heading change from `###` to `##` will make it a top-level section alongside About and Stack

</specifics>

<deferred>
## Deferred Ideas

- Blog post RSS automation via GitHub Actions — Phase 2 (handled as v2 in requirements)
- Visitor counters and snake animations — explicitly out of scope per research

</deferred>

---

*Phase: 02-polish-differentiation*
*Context gathered: 2026-05-25*
