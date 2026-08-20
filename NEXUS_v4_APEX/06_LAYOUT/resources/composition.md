## Impressive & balanced composition (Module 04)

[conf: RECOMMENDED]

Engine-neutral rules for layouts that feel premium, balanced, and intentional at every viewport tier. Pair with `resources/breakpoints.md`.

### Visual balance & symmetry

- Align to a **12 / 8 / 4 column grid** (desktop / tablet / mobile) so columns and gutters stay optically even.
- Prefer **asymmetric balance** (weighted Z) for heroes; **symmetric balance** for content sections and footers.
- Squint test: if groups are unclear, spacing or alignment is wrong — fix rhythm before decoration.

### Content & container caps

- Body / prose: `max-width: 65ch` (never stretch past ~75ch).
- Section content: use `--container-*` from the breakpoint tier (720 → 960 → 1280 → 1536 → 1728).
- On `3xl` / `4xl`: center the capped container; do not let full-bleed content fill 2560px unless it is intentionally edge-to-edge media.

### Whitespace & vertical rhythm

- Base spacing on a **4px grid**; prefer `rem` tokens and `clamp()` for section padding.
- **Intra-group** gaps (4–12px) ≤ ~50% of **inter-group** gaps (24–48px). Target **≥ 1:2.5** intra:inter ratio.
- Section padding fluid: e.g. `clamp(2.5rem, 8vw, 5rem)` so mobile breathes and desktop stays luxurious.
- Vertical rhythm: heading → content → space → heading — consistent drumbeat down the page.

### Density (60-30-10)

- ~60% surface / negative space, ~30% content mass, ~10% accent / CTA / highlight.
- Luxury and “impressive” UIs err toward **more** whitespace, not denser packing.

### Hierarchy & scanning

- Heroes: **Z-pattern** (logo → nav → headline → CTA).
- Content sections: **F-pattern** (heading → lead → left-edge scan → subheads).
- **One primary CTA per viewport** at any scroll position.
- Headings stay left- or center-aligned consistently within a page — never mix without intent.

### Hero & full-bleed

- Cap mobile landscape heroes (e.g. `max-height: 85dvh`); use `svh` / `dvh` not raw `vh`.
- Text over images: gradient / scrim / card backdrop for contrast — no naked overlay text.

### Balance across the 8 tiers

| Tier | Composition focus |
|------|-------------------|
| `xs`–`md` | Single column; stack; generous intra padding; no overflow; thumb-zone primary actions |
| `lg` | Introduce 2-col / 8-col grids; side-by-side when content pairs naturally |
| `xl`–`2xl` | Full 12-col grids; hover affordances; nav expands |
| `3xl`–`4xl` | Cap width, center, increase side gutters; keep type and gaps from overscaling |

### Pre-ship composition checks

- [ ] No horizontal scroll at 320px
- [ ] Container capped and centered at 1920+ / 2560+
- [ ] Intra:inter spacing ≥ 1:2.5
- [ ] One primary CTA visible per viewport
- [ ] Prose ≤ 65ch
- [ ] Touch targets ≥ 44×44px (invoke `08_A11Y` for formal a11y)
