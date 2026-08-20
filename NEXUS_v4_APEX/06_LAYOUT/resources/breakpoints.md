## Canonical 8-tier device breakpoints (Module 04)

[conf: DEFINITIVE]

Mobile-first page layout uses `min-width` media queries. Component internals still use container queries (`cqw` / `@container`) — see `resources/container-queries.md`.

### Tier table

| Token | min-width | Target devices | Container max | Grid cols | Margin / gutter |
|-------|-----------|----------------|---------------|-----------|-----------------|
| `xs` | 320px (base) | Small mobile, iPhone SE, budget phones | 100% fluid | 4 | 16px margins |
| `sm` | 360px | Standard mobile (iPhone 14/15/16, Pixel, base Galaxy) | 100% | 4 | 16px |
| `md` | 414px | Large mobile / phablet (Pro Max, Galaxy Ultra) | 100% | 4 | 20px |
| `lg` | 768px | Tablet portrait (iPad, Android tablets, Kindle Fire) | 720px | 8 | 24px gutters |
| `xl` | 1024px | Tablet landscape, iPad Pro / Air horizontal | 960px | 12 | 24px |
| `2xl` | 1366px | Laptops & small desktops (MacBook, 1366–1440 office monitors) | 1280px | 12 | 24–32px |
| `3xl` | 1920px | Full-HD desktop monitors | 1536px | 12 | 32px |
| `4xl` | 2560px | 4K / ultrawide / large iMacs | ~1728px capped + centered | 12 | 32–48px side gutters |

### Golden rules

1. **Mobile-first CSS.** Author the `xs` (320px) base. Expand with `min-width` — never shrink with `max-width` cascades.
2. **No horizontal scroll at 320px.** Any overflow on the smallest tier is a bug. Test every layout at `xs`.
3. **Cap and center on large screens.** At `3xl` / `4xl`, lock content to `--container-*` max-widths and center with generous gutters so 4K never looks empty or stretched.
4. **Page tier ≠ component tier.** Use these 8 device breakpoints for page chrome, section grids, and nav. Use `@container` + `cqw` for component-internal reflow.
5. **Test every tier.** Validate at 320, 360, 414, 768, 1024, 1366, 1920, and 2560 before shipping.
6. **1440px sits in `2xl`.** Do not invent a ninth token; 1440 uses the 1366+ rules with the same 1280px container cap.

### Token names (CSS custom properties)

```css
--bp-xs: 320px;
--bp-sm: 360px;
--bp-md: 414px;
--bp-lg: 768px;
--bp-xl: 1024px;
--bp-2xl: 1366px;
--bp-3xl: 1920px;
--bp-4xl: 2560px;
```

See `templates/breakpoints.css` for the full exemplar (container caps, grid columns, media-query scaffolds).
