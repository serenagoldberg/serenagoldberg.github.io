# Design — Serena Goldberg

A locked design system for this site. Every page redesign reads this file before
emitting code. Do not regenerate per page — extend or amend this file when the
system needs to grow.

## Genre

editorial

## Macrostructure family

One base macrostructure for the whole site.

- All pages: **Long Document** — masthead, generous vertical rhythm, inline
  section heads, hairline rules. Pages differ only in what fills the column,
  never in shape.

## Theme

Custom · Yale-blue anchored · editorial minimalist.

- `--color-paper`      oklch(98.8% 0.003 258)   /* soft white, faint cool cast */
- `--color-paper-2`    oklch(96.5% 0.006 258)   /* subtle inset panel */
- `--color-ink`        oklch(20% 0.025 258)     /* near-black, blue-tinted */
- `--color-ink-2`      oklch(45% 0.028 258)     /* muted — co-authors, metadata */
- `--color-rule`       oklch(89% 0.008 258)     /* hairline dividers */
- `--color-accent`     oklch(31% 0.11 258)      /* Yale blue ≈ #00356B */
- `--color-accent-ink` oklch(98% 0.003 258)     /* text on accent surface */
- `--color-focus`      oklch(58% 0.16 258)      /* accessibility ring */

Section `<h2>` bottom rules and the masthead wordmark render in
`--color-accent`; body chrome (masthead border, footer border, paper dividers)
stays in `--color-rule` so the accent doesn't overrun.

## Typography

- Display: **IBM Plex Sans**, weight 500, style normal
- Body:    **IBM Plex Sans**, weight 400
- Mono:    **IBM Plex Mono**, weight 400 (citations / tabular content, optional)
- Display tracking: −0.01em
- Type scale anchor: `--text-display` = clamp(2rem, 4vw + 1rem, 3rem)

Same-family monoculture. Hierarchy comes from weight, size, and colour — not
from swapping typefaces.

## Spacing

4-point named scale in `tokens.css`. Pages must use named tokens
(`var(--space-md)`), never raw values.

## Motion

- Easings: `--ease-out: cubic-bezier(0.16, 1, 0.3, 1)`
- Only animate: link underlines, `:focus-visible` ring appearance is instant
- Reveal pattern: **none**. Editorial minimalism cuts motion.
- Reduced-motion fallback: nothing to fall back to — motion is already cut.

## Microinteractions stance

- Silent success. No toasts.
- Link underline transitions on hover (opacity/thickness only, ≤ 180 ms).
- `:focus-visible` ring appears instantly, ≥ 3:1 contrast.

## CTA voice

The site has no marketing CTAs. Links carry the actions.

- Primary link:   Yale-blue text + underline (default `text-decoration: underline`)
- Secondary link: muted ink + underline on hover only

## Per-page allowances

All pages typography-only. No enrichment archetypes. No illustrations.
Headshot on index.html is a real photograph when supplied — otherwise a
labelled empty frame.

## What pages MUST share

- The wordmark ("Serena Goldberg" set in IBM Plex Sans 500)
- The Yale-blue accent, used only for interactive elements
- The masthead: name left, nav right, hairline rule below
- The footer: copyright + last-updated, single line
- Section heading rhythm: eyebrow (optional, small caps, muted) → display heading

## What pages MAY differ on

- Content within the column — the shape stays constant.

## Exports

Drop-in formats for re-using this design system in other projects.

### tokens.css

Emitted as a separate file at the project root. See `tokens.css`.

### Tailwind v4 `@theme`

Not currently used — vanilla HTML project. Add if migrating to Tailwind.

### DTCG `tokens.json`

Not currently emitted. Add if this system is reused across projects.

### shadcn/ui CSS variables

Not currently used — no React/shadcn in this project.
