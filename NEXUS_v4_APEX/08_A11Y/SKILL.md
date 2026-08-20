---
name: 08_A11Y
description: "Accessibility engine: WCAG 2.2, keyboard/focus, ARIA patterns, live regions, a11y CI guidance."
---

## L1

- Emit accessibility checklist and ARIA pattern contracts.

## L2 (Module 07 alignment: WCAG 2.2 + POUR + focus + ARIA)

- Target **WCAG 2.2 AA minimum** (AAA aspirational for text/contrast).
- Apply POUR principles (Perceivable/Operable/Understandable/Robust).
- Responsive accessibility (aligned with `06_LAYOUT` 8-tier viewports):
  - **1.4.10 Reflow:** usable at **320px** CSS width / 400% zoom; no two-axis scrolling for content
  - **2.5.8 Target Size (Minimum):** ≥ **24×24px** AA; recommend **44×44px** for primary controls
  - **1.3.4 Orientation:** content usable in both portrait and landscape (no orientation lock)
- Keyboard + focus management:
  - focus moves into modal on open
  - focus returns to trigger on close
  - skip-to-content link first focusable element on every page
  - design `:focus-visible` ring (2px + 2px offset), never `outline: none`
  - focus trap overlays using `inert` (not tabindex juggling)
- ARIA first rule: use native elements before ARIA roles.
- Loading/accessibility: `aria-live` region + `aria-busy` on loading containers.

## L3 (resources)

- `resources/pour.md`
- `resources/focus.md`
- `resources/aria.md`
- Contracts: `contracts/a11y-checklist.schema.json`, `contracts/focus-management.schema.json`, `contracts/aria-patterns.schema.json`

