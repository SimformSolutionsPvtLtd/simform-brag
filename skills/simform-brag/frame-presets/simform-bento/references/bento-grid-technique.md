# Bento Grid Technique — Zero-Gap Card Wall

Adapted from [apple-bento-grid](https://github.com/hubeiqiao/apple-bento-grid) (MIT License,
© Joe Hu) — a skill for generating Apple-style stat-card bento grids. Retextured here with
Simform Bento's own tokens (never Apple's `#f5f5f7` background, blue/cyan/red/green accents, or
Sora + DM Sans fonts). If `hubeiqiao/apple-bento-grid` happens to be installed
(`/plugin marketplace add hubeiqiao/apple-bento-grid`), Step 3 may read its fuller
`design-system.md` directly for more depth — this file is the self-contained, Simform-branded
subset `/simform-brag` needs either way, so no teammate has to install a third-party plugin just to run
`/simform-brag`.

**Use this technique only for the dense, multi-tile moments** — a "stat wall" variant of the
Highlight Bento Grid and Metric Spotlight treatments in [`../FRAME.md`](../FRAME.md), when a
scene needs 5+ small metrics at once. The Hero Bento Cover, Reveal Frame, Quote Tile, and
Sign-off Bento treatments keep FRAME.md's own generous `gap-bento`/`tile-pad` spacing — don't
zero-gap those; they're deliberately airy bookend moments, not a stat wall.

The wall sits on the same fixed `{colors.violet}` ground as every other treatment in
`FRAME.md` — it is not a white page. Each card is a white or lavender-100 (or, for the one
rationed quote card, ink) surface floating on that violet ground; the 6px gaps between cards show
a thin sliver of the violet ground through them, which is exactly what should happen — the wall
is dense, not gapless-onto-nothing.

## The five zero-gap rules (verbatim from the source technique)

1. Cards **fill** their grid cell — default `align-items: stretch`. Never set `align-items: start`.
2. The grid container has a **locked shape** — `aspect-ratio` on the 16:9 frame (omit on 9:16/1:1;
   let height flow from content instead).
3. Rows use `1fr` (16:9, proportional) or `auto` (9:16/1:1, content-driven).
4. Gap is **6px** — deliberately tighter than `spacing.gap-bento` used everywhere else in this
   system; that contrast is exactly what makes a "wall" scene read as dense and precise against
   the airier scenes around it.
5. **Every grid cell is occupied** — span a card across cells rather than leaving one empty.

```css
.bento-wall {
  display: grid;
  gap: 6px;
  grid-template-columns: repeat(4, 1fr);   /* 3 or 2 columns also valid; use 2 for a 9:16 frame */
  grid-template-rows: repeat(3, 1fr);
  grid-template-areas:
    "hero  stat1 stat2 chart"
    "hero  stat3 stat4 chart"
    "cat   cat   badge quote";
  aspect-ratio: 16 / 9;                     /* omit for 9:16 / 1:1 */
}
.bento-wall .card {
  border-radius: 20px;      /* {radii.tile-sm} — every wall card uses the small radius */
  overflow: hidden;
  position: relative;
}
```

## Card recipes, retextured to Simform tokens

Same seven card shapes as the source technique, restyled with Simform Bento's own tokens
(`FRAME.md` frontmatter) instead of Apple's:

- **`.card--hero`** (spans 2 cells, the wall's one dominant claim) — `background: {colors.white}`;
  a 4px top accent bar in `{colors.violet}` (or `{gradients.brand}`, once per video max); content
  is a 2-line `{typography.tile-title}` claim + a small `{typography.tile-label}` context line.
- **`.card--stat`** — `background: {colors.white}` or `{colors.lavender-100}`; one
  `{typography.stat-num}` in coral for the single most important number in the wall (coral fires
  once per wall, same rule as everywhere else in this system), with every *other* stat numeral in
  the same wall styled in `{colors.violet}` at `{typography.tile-title}` weight instead + a
  `{typography.tile-label}` caption.
- **`.card--category`** — `background: {colors.lavender-100}` (not `violet-06` — that token is an
  opacity tint calibrated for a white ground and is retired as a tile/card fill now the ground is
  violet; see `FRAME.md`'s Colors section); a `{typography.eyebrow}` label in `{colors.violet}` +
  a `{typography.tile-title}` focus line + a row of `tag-pill` components (already defined in
  `FRAME.md`) — the wall's direct use of the `tag-pill` component.
- **`.card--chart`** — `background: {colors.white}`; header row (`{typography.tile-label}` title +
  a small badge number in whichever of coral/violet wasn't already spent this wall); bars sized
  `height = (value / maxValue) * maxBarHeight`, gradient
  `linear-gradient(180deg, {colors.violet-light}, {colors.violet})` for a growth bar, or
  `linear-gradient(180deg, {colors.coral}, {colors.coral-deep})` only if this chart is the wall's
  coral moment and no stat card already spent it. Bar value labels use `{typography.tile-label}`.
- **`.card--badge`** — reuses the `icon-chip` component (violet-35 fill, 12px radius) + one
  `{typography.tile-title}` number beneath + a `{typography.tile-label}` caption — the direct
  analog of the source technique's Badge card, built from FRAME.md's own icon-chip instead of a
  new component.
- **`.card--quote`** (at most one per wall, the wall's single dark card — matches the source
  technique's own "quote is always the dark card" pattern) — `background: {colors.ink}` with
  `{borders.hairline}` (ink and the violet ground are close enough in lightness — 2.5:1 — that a
  hairline keeps the card's edge from reading as a soft blend into the ground); a
  `{typography.quote}` line in white, with the emphasized phrase in `{colors.violet-light}` (never
  coral here — coral is reserved for whichever stat/chart/badge already claimed it this wall).
- **`.card--highlight`** — `background: {gradients.brand}` (coral→coral-deep) — the wall's coral
  tile when the moment calls for one big multiplier (e.g. "3×", "10×") rather than a numeric stat;
  white text, large and bold enough to clear the AA-large contrast floor (see `FRAME.md`'s
  Contrast section — coral/white pairings need ≥24px, or ≥19px at 700+ weight). Counts as the
  wall's one coral spend; don't also color a stat or chart coral in the same wall.

**Coral discipline inside a wall:** exactly one of `.card--stat`'s numeral, `.card--chart`'s
badge, or `.card--highlight` may use coral in a given wall — never more than one, matching
`FRAME.md`'s existing "coral fires once per scene" rule. Every other numeral/accent in the same
wall uses violet.

## What changed from the source technique

- Page background: Apple's `#f5f5f7` → Simform's `{colors.violet}` ground, with white/lavender-100
  cards floating on top (matching `FRAME.md`'s full-composition rule — see its Colors section).
- Accent palette: Apple's blue/cyan/red/green → Simform's violet (workhorse) + coral (rare
  spotlight), per the same discipline used throughout `FRAME.md`.
- Fonts: Sora + DM Sans → Manrope + JetBrains Mono (`FRAME.md`'s own typography tokens).
- Card radius: Apple's 18px (light) / 20px (dark) → `{radii.tile-sm}` (20px), matching every
  other small tile in this system.
- The dark "quote card is always dark" pattern is kept, but it's now the wall's single ink-colored
  card (an intentional, rationed exception) rather than a fixed theme choice.
- Internal card content follows `FRAME.md`'s Content Rhythm rule (even `{spacing.content-gap}`
  between stacked elements) rather than the source technique's own ad-hoc per-card spacing.

## Attribution

This grid mechanic (the 5 rules) and the seven card shapes are adapted from
[hubeiqiao/apple-bento-grid](https://github.com/hubeiqiao/apple-bento-grid) (MIT License,
© Joe Hu). Colors, fonts, and radii are Simform's own — nothing from the source palette
(`#f5f5f7`, `#0071e3`, Sora, DM Sans) is reused.
