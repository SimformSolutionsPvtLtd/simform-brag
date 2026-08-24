---
version: alpha
name: Simform Bento — Frame (video / frame layer)
description: >
  Full Simform brand takeover for every /simform-brag video, regardless of the project being bragged
  about. The unit is the frame (1920×1080). Atoms are identical and sacred — Simform's real
  coral (#EF5366, gradient to #D71E23) + violet (#6740BA, with lighter #A077F8) dual accent on a
  white / pale-lavender bento-tile grid, Manrope (display + body) + JetBrains Mono (labels /
  data / eyebrows), 20–28px tile radii, soft violet-tinted ambient shadows or hairline borders
  (no hard offset, no skeuomorphism), and the Simform diamond-mark + wordmark lockup. Composition
  is free — how many tiles, which treatment, what content — but every piece of CHROME (background,
  tile fill, title, highlight tile, transition) renders in these tokens. The one exception: a
  literal product screenshot mounted inside a `screenshot-frame` keeps its own native colors.
  Motion mechanics are out of scope beyond a WHAT/WHY entrance-intent note; exact timing/easing
  defers to hyperframes-animation.
unit: the frame — 1920×1080 primary; 9:16 and 1:1 documented
principle: atoms are sacred · composition is free · numbers come from the script · only a screenshot's own pixels escape the palette

colors:
  white: "#FFFFFF"
  ink: "#1A1A1A"
  ink-body: "#212121"
  ink-muted: "#32373C"
  coral: "#EF5366"
  coral-deep: "#D71E23"
  violet: "#6740BA"
  violet-light: "#A077F8"
  lavender-100: "#ECE0FC"
  lavender-200: "#D9C3FF"
  violet-06: "rgba(103,64,186,0.06)"   # derived tint — tile fill
  violet-20: "rgba(103,64,186,0.2)"    # derived tint — hairline border
  violet-35: "rgba(160,119,248,0.35)"  # literal site pattern — icon-chip fill (verified on simform.com)
  coral-08: "rgba(239,83,102,0.08)"    # derived tint — rare 4th tile fill, sparing use only
  ink-08: "rgba(26,26,26,0.08)"        # derived tint — neutral hairline / shadow source
  positive: "#059669"                  # utility, not brand — directional deltas only
  negative: "#dc2626"                  # utility, not brand — directional deltas only

radii:
  tile-hero: "28px"
  tile-lg: "24px"
  tile-md: "20px"
  tile-sm: "20px"
  chip: "12px"     # scaled up from simform.com's literal icon-tile rx≈5 for video legibility
  pill: "100px"
  circle: "50%"

borders:
  hairline: "1.5px solid {colors.violet-20}"
  hairline-ink: "1px solid {colors.ink-08}"
  none: "none"

shadows:
  tile: "0 1px 2px rgba(26,26,26,0.05), 0 16px 40px rgba(103,64,186,0.10)"
  tile-raised: "0 2px 6px rgba(26,26,26,0.06), 0 28px 64px rgba(103,64,186,0.14)"
  none: "none"

gradients:
  brand: "135deg, {colors.coral} 0%, {colors.coral-deep} 100%"   # logo mark; rare hero/outro accent only

typography:
  body:        { fontFamily: "Manrope", cqw: 0.95, weight: 400, lineHeight: 1.6, color: "ink-body" }
  body-strong: { fontFamily: "Manrope", cqw: 0.95, weight: 600, lineHeight: 1.5, color: "ink" }
  eyebrow:     { fontFamily: "JetBrains Mono", px: 14, weight: 500, tracking: "0.1em", upper: true, color: "violet" }
  tile-label:  { fontFamily: "JetBrains Mono", px: 12, weight: 500, tracking: "0.06em", upper: true, color: "ink-muted" }
  tag-pill:    { fontFamily: "JetBrains Mono", px: 12, weight: 500, tracking: "0.04em", color: "violet" }
  attribution: { fontFamily: "JetBrains Mono", px: 13, weight: 500, tracking: "0.05em", upper: true, color: "ink-muted" }
  tile-title:      { fontFamily: "Manrope", cqw: 1.5, weight: 700, lineHeight: 1.2, tracking: "-0.01em", color: "ink" }
  quote:           { fontFamily: "Manrope", cqw: 2.2, weight: 500, lineHeight: 1.35, color: "ink" }
  section-headline:{ fontFamily: "Manrope", cqw: 2.6, weight: 700, lineHeight: 1.08, tracking: "-0.015em", color: "ink" }
  logo-wordmark:   { fontFamily: "Manrope", cqw: 1.7, weight: 800, tracking: "-0.01em", color: "coral" }
  stat-num:        { fontFamily: "Manrope", cqw: 3.2, weight: 800, lineHeight: 1.0, color: "coral", numeric: "tabular-nums" }
  hero-title:      { fontFamily: "Manrope", cqw: 4.6, weight: 800, lineHeight: 1.02, tracking: "-0.02em", color: "ink" }
  tagline:         { fontFamily: "Manrope", cqw: 1.1, weight: 500, lineHeight: 1.4, color: "ink-muted" }

spacing:
  pad-x: "5cqw"
  pad-y: "5cqw"
  gap-bento: "1.6cqw"
  tile-pad-lg: "2.6cqw"
  tile-pad-sm: "1.8cqw"
  chip-gap: "1cqw"
  accent-bar: "48px × 4px, 2px radius"

components:
  tile:
    backgroundColor: "{colors.white} | {colors.lavender-100} | {colors.violet-06} | {colors.coral-08} (rare, ≤1 per scene)"
    border: "{borders.hairline} (small/medium tiles) or none (large tiles carrying {shadows.tile})"
    rounded: "{radii.tile-hero}/{radii.tile-lg}/{radii.tile-md}/{radii.tile-sm} by footprint"
    shadow: "{shadows.tile} or none — never both a shadow AND a hairline at full strength on one tile"
    description: "The universal bento surface. Fills rotate across a scene; no two adjacent tiles share a fill; never a fifth, uninvited color."
  hero-tile:
    backgroundColor: "{colors.white}, rarely {colors.ink} for a dark hero (≤1 per video)"
    rounded: "{radii.tile-hero}"
    shadow: "{shadows.tile-raised}"
    typography: "{typography.hero-title} + {typography.tagline}, optional {colors.violet} {typography.eyebrow} above"
    description: "The single largest, most dominant tile on screen. Exactly one per scene. Carries the hook line, the primary claim, or (in the Reveal treatment) the screenshot-frame itself."
  highlight-tile:
    sizes: "{radii.tile-lg} / {radii.tile-md} / {radii.tile-sm} — 2-4 of these per Highlight Bento Grid scene, at DIFFERENT footprints, never a uniform grid"
    typography: "{components.icon-chip} + {typography.tile-label} + {typography.tile-title} + optional 1-line {typography.body}"
    description: "The supporting cast. Rotates fill per `tile`; each anchored by its own icon-chip so no two look interchangeable."
  stat-tile:
    typography: "{typography.stat-num} (coral — the one deliberate coral spotlight in this treatment) + {typography.tile-label}"
    description: "One dominant metric callout. Numeral is always tabular-nums and always a script-supplied figure or an explicit placeholder — never fabricated."
  quote-tile:
    backgroundColor: "{colors.lavender-100}"
    typography: "{typography.quote} + {typography.attribution}"
    description: "Wide single tile, generously padded, echoing simform.com's testimonial cards."
  screenshot-frame:
    backgroundColor: "{colors.white}"
    border: "{borders.hairline-ink}"
    rounded: "the host tile's radius minus a 6–8px inset"
    content: "a literal product screenshot / UI capture at its own NATIVE colors, unmodified"
    description: "THE ONLY place a non-Simform hex is allowed. Optional 3-dot muted-gray window chrome, top-left, purely decorative. Everything outside this inset — the host tile, its label, its chip — stays in Simform tokens. Never recolor the screenshot; never substitute the bragged project's own logo for Simform's anywhere outside this frame."
  icon-chip:
    size: "3.2cqw square (≈64px at 1920)"
    backgroundColor: "{colors.violet-35}"
    border: "1px solid {colors.violet-20}"
    rounded: "{radii.chip}"
    glyphColor: "{colors.ink} (default, 12.1:1 contrast) or {colors.violet} (4.85:1, passes AA normal)"
    description: "Direct callback to simform.com's own icon-tile pattern (A077F8 @ 35% fill, native rx≈5), scaled to {radii.chip} for video legibility."
  arrow-chip:
    size: "2.4cqw circle"
    backgroundColor: "{colors.ink}, or {colors.coral} in the Sign-off treatment only"
    textColor: "{colors.white}"
    rounded: "{radii.circle}"
    description: "The site's circular arrow-CTA affordance, reused as a decorative highlight-tile corner accent or the outro's single closing mark. Never more than one per scene."
  tag-pill:
    backgroundColor: "{colors.violet-06}"
    textColor: "{colors.violet}"
    rounded: "{radii.pill}"
    typography: "{typography.tag-pill}"
    description: "Category/status pill (echoes the site's case-study category tags), top-right of a tile."
  accent-bar:
    backgroundColor: "{colors.violet}, or the {gradients.brand} in the Hero Cover / Sign-off treatments only"
    size: "{spacing.accent-bar}"
    description: "Sub-headline rule above a hero-title or beneath an eyebrow. Coral gradient version is rationed to the two bookend treatments."
  logo-lockup:
    asset: "assets/simform-logo.svg (vendored, real Simform mark — render as an image/inline SVG, do not approximate)"
    layout: "the vendored SVG lockup (diamond mark + 'Simform' wordmark), ~162:34 aspect, scaled to fit"
    placement: "full-color lockup on the Hero Bento Cover and Sign-off Bento treatments only, at the largest size it appears anywhere in the video"
    watermark: "on every scene in between, the diamond-mark portion of the SVG alone (crop/mask out the wordmark), {colors.ink} at 8–12% opacity (via CSS filter/opacity, not a re-colored asset), bottom-right, inside the {spacing.pad-x}/{spacing.pad-y} safe margin — never overlapping tile content, omit entirely if it would crowd the frame"
    description: "Simform's own brand mark, present regardless of which project is being bragged about. Never substitute the bragged project's own logo here — that logo, if it appears at all, only appears natively inside a {components.screenshot-frame}."
---

# Simform Bento — Frame (video / frame layer)

## Overview

Simform Bento is a **full brand takeover**: every frame renders on Simform's own coral + violet
system, arranged as **varying-size, rounded-rectangle tiles** — the Apple product-page / keynote
grid, not a uniform feature-card row. One dominant tile carries the idea; two-to-three smaller
tiles support it at different footprints; generous whitespace and soft, tinted depth do the rest.

The voice is **Manrope** (display + body, real weight contrast 400→800) for everything a viewer
reads as a sentence or a claim, and **JetBrains Mono** (uppercase, tracked) for everything that
reads as a label, tag, or data point — a small nod to Simform being an engineering company, not a
decorative flourish. Coral (`#EF5366`→`#D71E23` gradient) is the **rare spotlight** — the logo, one
numeral, one tile-title, at most once per scene. Violet (`#6740BA`, with lighter `#A077F8`) is the
**everyday accent** — every label, border, icon stroke, and chip, exactly mirroring how
simform.com actually splits these two colors (coral in the wordmark, violet sitewide for
accents/text/icon strokes).

**Key characteristics at frame scale:**

- **White canvas, bento tiles** — tiles fill `{colors.white}` / `{colors.lavender-100}` /
  `{colors.violet-06}`, rotating fill, never uniform, never a fourth color save a rare coral-08 tint.
- **Varying footprints, one dominant tile** — hero/lockup tile at 1.8–2.5× its nearest neighbor;
  never a uniform grid of same-size tiles (that's a dashboard, not a bento).
- **Coral is rare, violet is constant** — coral fires once per scene (logo, one numeral, one
  tile-title); violet carries every label, border, icon stroke, chip.
- **Manrope + JetBrains Mono**, extreme weight contrast on display, uppercase tracked mono for
  every label/eyebrow/tag.
- **Soft depth only** — a large, low-opacity, violet-tinted ambient shadow OR a 1.5px hairline
  border; never both maxed, never a hard offset, never a bevel.
- **20–28px tile radii**, scaled to footprint; a 12px icon-chip (the site's own rx≈5 pattern,
  scaled up for video); nothing square, nothing pill-shaped save chips/pills/circles.
- **Literal screenshots keep their own colors** — the one sanctioned exception, always inside a
  `screenshot-frame`.

### Frame Craft Bar

Three eyeball tests gate every frame before any structural check:

- **Squint** — the hero/lockup tile reads **1.8–2.5×** its nearest neighbor's visual weight —
  dominant, not a solo; a bento is a chorus with one lead voice, not one giant tile and scraps.
- **Silence** — tiles fill **~65–75%** of the safe area; the rest is `gap-bento` + margin, never a
  blank quadrant and never edge-to-edge crowding. Internal tile padding does the breathing, not
  frame emptiness.
- **Restraint** — coral fires **once per scene at most** (logo, one numeral, one tile-title);
  violet is the only color allowed to repeat across a frame; never let both fire at full
  saturation in the same tile.
- **Reference** — aim at an **Apple product-page bento comparison / keynote feature slide**;
  failure looks like a **generic SaaS 3-up feature-icon row** or a **uniform metric dashboard**.

## The Frame

- **Primary:** 1920×1080 (16:9). Display sizes authored in **`cqw`** (`px ÷ 1920 × 100 = cqw`).
- **Vertical:** 1080×1920 (9:16). **Square:** 1080×1080 (1:1).
- **Safe area:** `{spacing.pad-x}` / `{spacing.pad-y}` (5cqw) on every edge.

**The container law (load-bearing).** Every frame ground sets `container-type: size`; ALL
frame-relative units are `cqw`/`cqh` resolved against it — **never `vw`.** Tile radii and chip
sizes stay `px` (20–28px tiles, 12px chip); borders stay 1–1.5px.

## Colors

`{colors.white}` is the universal canvas. `{colors.violet}` is the **workhorse accent** — every
eyebrow, label, tag-pill, icon stroke, hairline border, and watermark. `{colors.coral}` is the
**spotlight**, not the default — the logo wordmark, one numeral (`stat-num`), or one tile-title per
scene, never the everyday chip/border/label color. `{colors.coral-deep}` is coral's small-text-safe
substitute (see Contrast, below) and the gradient's dark stop. Tiles rotate fill among
`{colors.white}` / `{colors.lavender-100}` / `{colors.violet-06}`, with `{colors.coral-08}` as a
rare fourth option (at most one tile, at most once per video). `{colors.ink}` /
`{colors.ink-body}` / `{colors.ink-muted}` are the safe default text color on every surface in this
system — reach for one of them whenever coral or violet fails contrast (see below).

## Typography

Two voices in fixed roles. **Manrope** carries every headline, tile-title, numeral, quote, and body
line — weight is the whole hierarchy (`hero-title` 800 → `body` 400, always with real contrast,
never adjacent weights). **JetBrains Mono**, uppercase and tracked (0.04–0.1em), carries every
label, eyebrow, tag, and attribution — the "engineering precision" register against Manrope's
"product claim" register.

- **Legibility floor:** any single load-bearing headline line ≥ **1.4cqw**; mono chrome (labels,
  tags) is colophon-scale by design.
- **Fit-to-measure:** ≤3 words → `hero-title`; 4–6 → `section-headline`; a tile-sized claim →
  `tile-title`. Numerals are always `tabular-nums`.
- **Color defaults:** headlines/tile-titles ink; numerals coral (the spotlight); labels/eyebrows
  violet; body ink-body. Never a coral headline at body size, never a violet numeral.

## Depth & Surface

Soft, tinted, and quiet — the opposite of skeuomorphism. A tile uses **at most one** of:

- **Soft ambient shadow** — `{shadows.tile}` (a whisper-close ink shadow plus a large, very soft,
  violet-tinted blur) lifts a tile without a visible light source or offset. The hero/lockup tile
  may step up to `{shadows.tile-raised}`.
- **Hairline border** — `{borders.hairline}` (1.5px violet@20%) reads as "defined" without a
  shadow at all; prefer this on smaller supporting tiles so a frame never stacks three visible
  shadows.

**Ceiling:** no hard offset shadow, no bevel/emboss, no glass/blur panel, no gradient background
wash. `{gradients.brand}` is reserved for the logo mark and, at most once per video, a hero-tile
`accent-bar` or the outro `arrow-chip`.

## Shapes

- **28/24/20px** — tile radii by footprint (hero → small); nothing dips below 20px or exceeds 28px.
- **12px** — the icon-chip (scaled up from simform.com's own rx≈5 icon-tile).
- **100px** — tag-pill edge. **50%** — arrow-chip circle, circular icon containers.
- **0** — never used on a content surface; this system has no square corners.

## Components

- **tile / hero-tile / highlight-tile** — the bento surfaces; one dominant, 2–4 varying-footprint
  supporters, rotating fill, one radius-and-depth rule.
- **stat-tile / quote-tile** — single-focus callouts (metric spotlight, testimonial).
- **screenshot-frame** — the one sanctioned exception to the whole palette; literal product UI at
  native colors, masked inside Simform chrome.
- **icon-chip / arrow-chip / tag-pill / accent-bar** — the site's own real chip, CTA-arrow, and
  category-tag affordances, ported into the tile system.
- **logo-lockup** — Simform's own vendored mark, full-presence at open/close, watermark-or-absent
  between.

For the **Highlight Bento Grid** and **Metric Spotlight** treatments specifically, a denser
"stat wall" variant of these components (tight 6px gaps rather than `gap-bento`, seven concrete
card recipes) is available at
[references/bento-grid-technique.md](references/bento-grid-technique.md) — use it when a scene
calls for a dense multi-metric moment rather than the standard airy bento composition.

## Frame Treatments

> Recipe per plate: ground · container · composes · focal · chrome · accent · silence · Fixed/Free · density.

### 1 · Hero Bento Cover (identity · move: dominant hero tile + corner tiles · left)

**Ground** white, `pad-x`/`pad-y`. **Composes** hero-tile (~62% width, full column) + 1–2
highlight-tile-sm in the remaining column. **Focal** a 2–3 word `hero-title` in ink inside the
hero tile, an `accent-bar` above it, an `eyebrow` above that. **Chrome** `logo-lockup` (full) in
the hero tile's corner or just outside it in the safe margin. **Accent** the `accent-bar` may use
`{gradients.brand}`; nothing else fires coral. **Silence** generous `tile-pad-lg` inside the hero
tile around the title block. **Fixed** hero tile always the largest shape on screen. **Free** title
copy, corner-tile count/content. **Density** standard.

### 2 · Reveal Frame (product reveal · move: full-bleed screenshot-frame · centered)

**Ground** white, `pad-x`. **Composes** one large `screenshot-frame` (~74% width) + an `eyebrow`
above it + optionally one `highlight-tile-sm` beside it. **Focal** the screenshot itself, native
colors. **Chrome** `hairline-ink` border + `{shadows.tile}`. **Accent** violet eyebrow only — no
coral in this treatment; the product's own colors already carry the weight. **Silence** generous
white mat inside the frame around the screenshot. **Fixed** screenshot always native, frame chrome
always Simform tokens. **Free** screenshot content/aspect, optional side tile. **Density** standard.

### 3 · Highlight Bento Grid (features · move: 3–4 tile asymmetric grid · the core frame)

**Ground** white, `pad-x`/`pad-y`. **Composes** one `highlight-tile` at `tile-lg` (2×1 footprint) +
two at `tile-md`/`tile-sm`, at DIFFERENT footprints — never a uniform 3-up. Each tile: `icon-chip` +
`tile-label` + `tile-title` + optional 1-line `body`. **Focal** none singular — 2–4 elements share
attention, each anchored by its own icon-chip. **Chrome** an `eyebrow` above the grid. **Accent** at
most ONE tile may use `coral-08` fill or a coral `tile-title`/numeral; the rest stay
white/lavender/violet-06. **Silence** `gap-bento` between every tile, `tile-pad-sm` inside each.
**Fixed** varying footprints, rotating fills, never two adjacent tiles share a fill. **Free** tile
count (2–4), which tile is large, copy, glyphs. **Density** the one frame allowed to feel fuller —
when the moment calls for 5+ small metrics at once, switch to the zero-gap "stat wall" variant in
[references/bento-grid-technique.md](references/bento-grid-technique.md) instead of stretching this
treatment's 2–4 tile composition thin.

### 4 · Metric Spotlight (data · move: one dominant stat-tile · left)

**Ground** white, `pad-x`. **Composes** one large `stat-tile` + 1–2 small `highlight-tile-sm` for
context/comparison. **Focal** the coral `stat-num` — the one frame where coral is deliberately
dominant. **Chrome** an `eyebrow` above. **Accent** the numeral is the ONLY coral in the frame.
**Silence** the stat-tile interior is mostly empty around the giant numeral. **Fixed** numeral
always `tabular-nums`, always script-supplied or an explicit placeholder. **Free** numeral,
comparison-tile content. **Density** sparse — for a denser multi-metric spotlight (several stats
at once rather than one dominant number), use the zero-gap "stat wall" variant in
[references/bento-grid-technique.md](references/bento-grid-technique.md) instead.

### 5 · Quote Tile (quote · move: single wide tinted tile · centered)

**Ground** white, `pad-x`, centered. **Composes** one `quote-tile` (lavender-100, ~70–80% width) +
an `attribution` beneath. **Focal** a 1–2 line `quote` in ink. **Chrome** a small violet glyph or
`icon-chip` beside the attribution. **Accent** violet only. **Silence** ~50% of the tile is
whitespace around the (short) quote. **Fixed** ink quote text, lavender tile, mono attribution.
**Free** quote copy, attribution, glyph. **Density** sparse.

### 6 · Sign-off Bento (closer · move: centered lockup + tagline + arrow-chip · centered)

**Ground** white, centered. **Composes** `logo-lockup` (full, largest anywhere in the video) +
`tagline` beneath + one `arrow-chip` as the closing mark; optionally 1–2 tiny
`highlight-tile-sm` flanking, bookending the Hero Cover. **Focal** the lockup — the one frame where
the wordmark is largest. **Chrome** none extra. **Accent** coral (wordmark + gradient) is allowed
at full presence — the one frame where coral is the SUBJECT, not an accent. **Silence** ~55–60%
empty around the centered lockup. **Fixed** centered lockup, one tagline line, one arrow-chip.
**Free** tagline copy (project-specific vs. generic Simform sign-off), flanking tiles or not.
**Density** sparse.

## Entrance & Transition Intent (what & why — not mechanics)

Tiles should feel like they're settling into a grid that was always there, not flying in from
off-screen — a small scale-and-fade "arrival," not a slide or wipe. **What:** each tile starts
slightly smaller and lower than its resting position, at zero opacity, and settles up-and-in to
full size/position/opacity. The hero tile (or the lockup, in Sign-off) leads; supporting tiles
cascade in shortly after, in reading order (largest-to-smallest, or left-to-right/top-to-bottom),
never all at once. **Why:** a synchronized "pop" reads as a slide deck; a led-then-cascaded settle
reads as a considered system — the entire premise of a bento layout is one dominant idea with
supporting ones arriving to confirm it.

Between scenes, prefer a soft crossfade or a tile-level reflow (outgoing tiles fade+settle down
slightly as incoming tiles arrive) over a hard cut, wipe, or flash — this system's register is
Simform's confident B2B engineering voice ("Agile in mind, spirit, and speed"), not a joke and not
chaos. A `chaotic`/`yc-parody` `/simform-brag` tone may run this faster and punchier, but should keep the
same scale+fade grammar rather than switching to glitch/flash mechanics that break the brand
register. Exact stagger intervals, easing curves, and runtime (GSAP/CSS/WAAPI) belong to
`hyperframes-animation`, not here.

## Composition Rules

### Do

- Start every frame on white; let **violet carry the everyday accent** (labels, borders, icon
  strokes, chips) and let **coral fire once per scene at most** (a numeral, the wordmark, or a
  single tile-title) — never both fully saturated at once.
- Vary tile footprints within a scene — at least one large + one-to-three smaller; never a uniform
  grid of equal tiles.
- Rotate tile fills among white / lavender-100 / violet-06 (+ coral-08, once per video max); never
  repeat a fill on two adjacent tiles.
- Keep every tile radius 20–28px, scaled to footprint; depth from `{shadows.tile}` OR
  `{borders.hairline}`, never a hard offset, never both maxed on one tile.
- Render Manrope with real weight contrast (400 body / 700–800 display) and JetBrains Mono
  uppercase-tracked for every label/eyebrow/tag.
- Mount every literal product screenshot inside a `screenshot-frame`; keep it at native colors;
  keep everything outside that inset in Simform tokens.
- Place the vendored `logo-lockup` SVG at full presence on the opening and closing tiles;
  watermark-or-absent everywhere between.

### Don't

- Don't let coral become the default accent — it's the rare spotlight, not the everyday
  chip/border/label color; use violet for those.
- Don't put coral or coral-deep body/label-size text directly on a lavender tile fill — verified
  contrast fails or lands borderline (see Contrast section); use ink or white there instead.
- Don't build a uniform 3-up or 4-up grid of same-size, same-fill tiles — that's a dashboard
  pattern, not this system.
- Don't add a hard 3D bevel, a heavy drop shadow, a gradient background wash, or a second display
  font.
- Don't recolor a product screenshot's own UI to match Simform tokens, and don't substitute the
  bragged project's logo for Simform's in the lockup slot.
- Don't fabricate a metric, client name, or testimonial — every numeral/quote traces to the script
  or the source project, else a placeholder.

## Contrast & Accessibility (WCAG 2.1)

Computed via standard relative-luminance math:

- **Coral `#EF5366` on white/near-white** — 3.44:1. **Fails AA-normal (4.5), passes AA-large
  (3.0).** Coral text/numerals must be large/bold (≥24px, or ≥19px at 700+) — never body copy.
- **Coral-deep `#D71E23` on white** — 5.13:1. **Passes AA-normal.** Use this instead of coral
  whenever a coral-family color must render at label/body size on a light surface.
- **Violet `#6740BA` on white** — 6.96:1, and **white on solid violet fill** — 6.96:1. Both **pass
  AA-normal**, close to AAA — safe for body-size labels and for white headline text on a solid
  violet tile at any size.
- **Violet on lavender-100** — 5.51:1, **passes AA-normal**. **Violet on lavender-200** — 4.37:1,
  **borderline fails AA-normal** — treat violet-on-lavender-200 as large-text-only, or prefer
  ink/white text on lavender-200 fills.
- **Coral on lavender-100** — 2.73:1, **fails even AA-large.** **Coral-deep on lavender-100** —
  4.06:1, **passes AA-large only.** Never place coral/coral-deep body text on a lavender tile.
- **Ink (`#1A1A1A`/`#212121`/`#32373C`) on white, lavender-100, or lavender-200** — 13.8:1 /
  13.8:1 / 10.9:1 — comfortably **AAA** on every surface in this system. Default to ink whenever a
  color choice is contrast-uncertain.
- **White on solid coral fill** — 3.44:1, same large-text-only rule as coral-on-white.

Re-verify with `hyperframes-creative/scripts/contrast-report.mjs` after composing — it samples
actual rendered pixels, not just declared tokens.

## Aspect-Ratio Behavior

| Treatment | 16:9 | 9:16 | 1:1 |
|---|---|---|---|
| Hero Bento Cover | hero left ~62%, corner tiles stacked right | hero top ~65% height, corners stacked below | hero upper-left 2×2, corners lower row |
| Reveal Frame | screenshot ~74% width, side tile right | screenshot full width, claim tile below | screenshot centered, claim tile below |
| Highlight Bento Grid | 1 wide + 2 stacked right, asymmetric | 1 tall top + 2 stacked below | 2×2 with one tile spanning 2 cells |
| Metric Spotlight | stat-tile left, 1–2 small right | stat-tile top, small tiles below | stat-tile large corner, small tile opposite |
| Quote Tile | centered wide tile | centered, taller tile | centered, near-square tile |
| Sign-off Bento | centered lockup, tiles flank | centered lockup, tiles stacked below | centered lockup, tiles at corners |

`pad-x`/`pad-y` hold on the short edge; re-check the 20–28px radius floor and the contrast table
above at reduced tile footprints.

## Approved Entities

Simform's own vendored wordmark + diamond mark (`assets/simform-logo.svg`) is the one integral
brand asset this system is built around — render per `components.logo-lockup`. No other real
customer, vendor, or partner logo is defined — a client-logo strip (echoing simform.com's
Clutch/G2/Google-Partner row) may be recreated as placeholder chips only if the storyboard
explicitly calls for a proof/trust beat, and never with fabricated ratings or client names. The
**bragged project's own logo/brand**, if visible in a source screenshot, renders natively and
unmodified inside a `screenshot-frame` only — never recolored into Simform tokens, and never
substituted for Simform's own mark in the lockup slot.

## Numerals & Claims (hard rule)

Never invent figures, stats, dates, or client names at frame scale — neither Simform's own (e.g.
headcount, satisfaction %) nor the bragged project's. Render slots as `— figure —`, `{metric}`,
`N×` until the script or the source project supplies a real value. The `stat-tile` and any
sequential highlight numerals especially carry placeholders, not fabricated ones.

## Pre-Render Self-Audit

- **Squint** — hero/lockup tile reads 1.8–2.5× its nearest neighbor; no two tiles compete for
  dominance.
- **Coral discipline** — coral/coral-deep appears at most once per scene as a spotlight; never the
  default border/label/chip color.
- **Fills** — tile fills rotate among white/lavender-100/violet-06 (+ rare coral-08); no two
  adjacent tiles share a fill.
- **Radius** — every tile 20–28px, scaled to footprint; no square corners outside chip/circle
  exceptions.
- **Depth** — soft violet-tinted shadow OR 1.5px hairline, never a hard offset, never both maxed.
- **Type** — Manrope display 700–800 / body 400–600 with real contrast; JetBrains Mono
  uppercase-tracked labels; ≥1.4cqw floor on any single load-bearing headline.
- **Screenshot integrity** — every literal screenshot keeps native colors inside its
  `screenshot-frame`; nothing outside that inset uses a non-Simform hex.
- **Logo** — vendored Simform lockup present (full at open/close, watermark-or-absent
  mid-video); never replaced by the bragged project's own mark.
- **Fabrication** — every numeral, quote, and client name traces to the script/source project,
  else a placeholder.

## Known Gaps

- **Motion mechanics intentionally out of scope** beyond the WHAT/WHY note above; exact
  stagger/easing/runtime belongs to `hyperframes-animation`.
- **Manrope via Google Fonts, not vendored yet.** JetBrains Mono is pre-bundled (offline-safe).
  Manrope auto-fetches from Google Fonts at build time — fine locally, fail-closed on
  offline/cloud renders. Fast-follow: vendor Manrope 400/500/700/800 as local `woff2` under a
  `fonts/` folder in this preset directory, the way `frame-presets/code-editorial/` does.
- **No real Simform brand font confirmed** — Manrope is this plan's substitute, not a confirmed
  Simform typeface. Swap the `typography` block's `fontFamily` values if/when Simform supplies
  one.
- **Dense "stat wall" scenes** (5+ small metrics in one scene) use a separate, zero-gap technique
  adapted from a third-party skill — see
  [references/bento-grid-technique.md](references/bento-grid-technique.md) — rather than stretching
  the Highlight Bento Grid / Metric Spotlight treatments' own looser spacing.
