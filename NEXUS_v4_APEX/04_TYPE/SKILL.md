---
name: 04_TYPE
description: "Design tokens (type): modular scale, fluid type (320–2560px bounded), font pairing, loading/perf, readability/kerning."
---

## L1

- Emit typography tokens and font loading plan as contracts.

## L2 (Module 03 alignment: modular scale + clamp + units)

- Typography is a system: define scale, roles (display/body/mono), and reading comfort.
- Use **fluid type with `clamp()`** for every scale step; avoid breakpoint-only sizing.
- Bound fluid type to the layout viewport range: **min at 320px**, reach **max by ~1920px**, and **cap growth beyond 2560px** so 4K does not oversize type.
- Use typography-relative units intentionally (`rem`, `em`, `ch`) and avoid raw `px` for type sizes.
- Font loading: preload key fonts, `font-display: swap`, define robust fallbacks.

## L3 (resources)

- `resources/fluid-clamp.md`
- `resources/type-scale.md`
- `resources/font-loading.md`
- Contracts: `contracts/type-tokens.schema.json`, `contracts/font-loading.schema.json`
