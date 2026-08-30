# AI for CFO — The Finance Build Day

Landing page for AM Consulting's one-day AI build workshop for finance teams.

**Live:** https://ai-for-cfo.amconsultingai.com

## What this is

A single self-contained `index.html`. No build step, no dependencies to install —
fonts come from Google Fonts, everything else (logos, photography, the workshop
brand assets) is inlined as base64 or inline SVG.

## Editing

Open `index.html` and edit in place.

- **Copy** lives in the `T` object near the bottom of the file, with an `en` and a
  `he` block. Every string is keyed; elements pick theirs up via `data-t="key"`.
  Both blocks must define the same keys — the page renders whichever the visitor
  selects, and remembers the choice in `localStorage`.
- **Workflows** are the `wf` array inside each language block. Each entry declares
  its source systems, the short prompts that ride the beams, and a `mock` object
  describing the artifact that draws itself (`kind` is `table` or `dashboard`).
  The English and Hebrew entries must stay structurally identical — same order,
  same `kind`, same row and column counts.
- **Logos** are the `LOGO` map: real brand marks as inline SVG. Gradient ids are
  namespaced per brand (`xl_`, `gs_`, `pb_`) so they cannot collide. Keep that
  convention when adding one.
- **Brand tokens** (colour, type) are the CSS custom properties in `:root`, taken
  from the AM Consulting brand guide.

## Assets

`assets/` holds the full-resolution source image used in the hero, so it can be
recropped without hunting for the original.

## Deployment

GitHub Pages serves `main` from the repository root. Push to `main` and the site
updates. `CNAME` pins the custom domain.
