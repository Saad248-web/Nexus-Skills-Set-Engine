## Viewport units (Module 04)

- `vw/vh`: avoid `vh` for mobile height
- `dvh`: dynamic viewport; can reflow on scroll—test
- `svh`: safe minimum height (chrome visible) — good for min-height
- `lvh`: large viewport (chrome hidden)
- `cqw/cqh`: container query width/height — **component** breakpoints (not page chrome)
- `rem`: global spacing tokens
- `em`: component-internal spacing that scales with type size

**Reconciliation:** page/layout tiers use the canonical 8 device breakpoints (`resources/breakpoints.md`). Component-internal reflow uses `cqw` / `@container`.
