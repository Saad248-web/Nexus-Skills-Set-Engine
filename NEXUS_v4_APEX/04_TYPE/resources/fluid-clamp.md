## Fluid type with clamp() (Module 03)

All type sizes are expressed with `clamp(min, fluid, max)` to scale between mobile and desktop.

Rule:

- Define min (mobile) + max (desktop) per token.
- Keep ratios consistent across the scale.
- **Viewport bounds (aligned with `06_LAYOUT` 8-tier system):**
  - **min** = size at **320px** (`xs`)
  - **max** reached by ~**1920px** (`3xl`)
  - Beyond **2560px** (`4xl`): do not keep growing — max is already capped inside `clamp()`

Bounded example (body):

```css
/* min at 320px → preferred scales with vw → max locked by ~1920px / 4K */
--text-base: clamp(1rem, 0.92rem + 0.35vw, 1.125rem);
```

Preferred formula sketch: choose `min` for 320px readability, set `max` for comfortable reading at Full-HD, let the middle term interpolate; 4K inherits the same `max`.
