# Dev Log

## Current task: match sunilpai.dev editorial look (2026-09-20)

Reference: https://sunilpai.dev/posts/the-senior-engineer-death-spiral/

### What changed (this pass)

| Area | Change |
|---|---|
| Fonts | Dropped Inter + JetBrains Mono. Body now uses the system-ui stack and `Roboto Mono` for dates/metadata — exactly what the reference loads. |
| Navbar | No longer a fixed glass bar with a dashed border. Now a static, transparent header inside the 48rem content column; accent-colored nav links with dotted separators; `body.nav-fixed` top padding neutralized. |
| Post layout | `body.fullcontent #quarto-content` constrained to 48rem (single centered column). Removed `toc: true` from the 4 posts that had it — the reference post page has no TOC sidebar. |
| Title block | Reordered via flex (`display: contents` on `.quarto-title`) to reference order: title → mono date → accent-bordered summary. Author + "Author/Published" headings hidden. No dashed divider under the hero. |
| Prose | 1.0625rem body text; `#` markers in accent color hanging left of h2–h4; inline code wrapped in backticks with dotted border; `strong` pure black/white; `hr` dashed with 3em margins. |
| Dates | `date-format: "D MMMM YYYY"` (moment tokens — `d` is day-of-week!) in `_quarto.yml` and the listing in `index.qmd` → "19 May 2026", matching the reference. |
| Footer | Plain small system-font text, no border, no mono. |

### Known deltas vs. reference (deliberate)

- No prev/next post links at page bottom (Quarto has no built-in; skipped).
- Category pills still shown on posts (they're content, not chrome).
- GitHub/LinkedIn icons kept in navbar (user's links).

### Verification

`python3` check (see git history / run inline): 12 structural assertions over
`docs/styles.css` and a rendered post — static navbar, `#` markers, backticks,
font stacks, 48rem column, date format, no TOC. All pass.

### History

- 2026-09-20: pass described above.
- Earlier: initial minimalist editorial theme (palette, glow, listing restyle).
