# Phase 1: Content Refresh - Context

**Gathered:** 2026-05-25
**Status:** Ready for planning

<domain>
## Phase Boundary

Update 5 content sections of the GitHub profile README to eliminate stale references and present accurate, current professional information. No structural changes, no new sections. Stack/skills section stays unchanged.

</domain>

<decisions>
## Implementation Decisions

### About Section
- **D-01:** Convey being in transition — "between roles, soon joining one of Malaysia's leading digital banks"
- **D-02:** Keep the tone authentic and understated, no hype language

### Currently Section
- **D-03:** Include role as "software engineer (incoming) @ digital bank"
- **D-04:** Remove "open to" line entirely
- **D-05:** Keep location (Petaling Jaya), exploring interests (systems design, distributed workflows, iot), and training (marathons, lifting, hyrox) unchanged

### TracePace Section
- **D-06:** Update status block within the code fence
- **D-07:** Status changes from "public beta incoming" to "launched"
- **D-08:** Version changes from "v0.5.0-alpha" to "v1.0.0"
- **D-09:** Add `url: tracepace.app` line to the code block
- **D-10:** Keep "repo is private & invitational" note as-is

### Blog Posts
- **D-11:** Remove "playing the long game in a sprint-obsessed industry" (nov 2025)
- **D-12:** Add "i train in blocks, i build the same way" as newest post
- **D-13:** Order: newest first (training article, then "i don't know enough yet to keep it simple")

### Things Shipped
- **D-14:** Add Emergency Reschedule Request as a concise one-liner: "emergency reschedule requests — structured workflow when self-service is unavailable, with partner centre review and email notifications"

### OpenCode's Discretion
- Exact formatting details (alignment, bullet style) — match existing README conventions
- Shipped item placement within the list (top, bottom, or contextually grouped)
- Transition phrasing in About section

</decisions>

<canonical_refs>
## Canonical References

### Source documents
- `README.md` — The file being modified
- `.planning/PROJECT.md` — Project context and constraints
- `.planning/REQUIREMENTS.md` — Requirement definitions (CONT-01 through CONT-05)

No external specs — requirements are fully captured in decisions above.

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets
- `README.md` — Single markdown file, all edits are text replacements
- `tracepace/public/preview.png` — Preview image, no changes needed

### Established Patterns
- Badges via shields.io with `flat-square` style
- ATX headings with lowercase: `### about`
- Horizontal rules `---` between sections
- Code blocks with language specifiers: \`\`\`text

### Integration Points
- No integration points — this is a standalone markdown file

</code_context>

<specifics>
## Specific Ideas

- "i train in blocks, i build the same way" article URL: https://medium.com/@uz6r/i-train-in-blocks-i-build-the-same-way-e1c496e0863b
- tracepace.app should be a clickable link in the code block
- The "things i've shipped" section uses emoji bullets — match existing style

</specifics>

<deferred>
## Deferred Ideas

None — phase scope covers all content refresh needs.

</deferred>

---

*Phase: 01-content-refresh*
*Context gathered: 2026-05-25*
