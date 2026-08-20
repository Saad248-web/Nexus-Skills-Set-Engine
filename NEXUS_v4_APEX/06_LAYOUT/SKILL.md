---
name: 06_LAYOUT
description: "Layout engine: 8-tier responsive breakpoints (320–2560px+), balanced composition, viewport units, print, foldables, density."
---

## L1

- Emit layout zones, **8-tier breakpoint token set**, responsive grid, and balanced-composition contracts.

## L2 (Module 04 alignment: breakpoints + composition + viewport units + container queries + print)

- Apply the **canonical 8-tier mobile-first breakpoints** (`xs` 320 → `sm` 360 → `md` 414 → `lg` 768 → `xl` 1024 → `2xl` 1366 → `3xl` 1920 → `4xl` 2560):
  - author base styles at 320px; expand with `min-width` only
  - assign container caps + grid columns per tier (4 / 8 / 12 cols); cap and center content at `3xl`/`4xl`
  - never allow horizontal overflow at 320px; test every tier before ship
- Apply **balanced composition** rules: 12/8/4 grid alignment, prose ≤ 65ch, ≥ 1:2.5 intra:inter spacing, fluid section padding via `clamp()`, 60-30-10 density, one primary CTA per viewport, F/Z hierarchy
- Apply viewport unit rules:
  - avoid `vh` for mobile height; use `svh/dvh/lvh` appropriately
  - use `cqw/cqh` for **component** responsiveness (container queries) — page chrome uses the 8 device tiers
  - use `rem` for global spacing tokens, `em` for component-internal spacing that scales with type
- Add mobile landscape constraints (hero cap; modal scrolling).
- Always ship a print stylesheet plan (hide nav/hero media/fixed; print link URLs; page break rules).

## L3 (resources)

- `resources/breakpoints.md`
- `resources/composition.md`
- `resources/viewport-units.md`
- `resources/container-queries.md`
- `resources/print.md`
- Templates: `templates/breakpoints.css`, `templates/print.css`
- Contracts: `contracts/viewport-units.schema.json`, `contracts/zones.schema.json`, `contracts/print.schema.json`
