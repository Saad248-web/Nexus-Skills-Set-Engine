---
name: 07_COMPONENTS
description: "Component system: anatomy, slots, states, loading/error designs, token integration, cross-viewport reflow."
---

## L1

- Emit component inventory and state model contracts.

## L2 (Module 05 alignment: token tiers + slots + states + state management)

- Enforce **3-tier tokens**: primitive → semantic → component. Components reference component tokens only.
- Component layers: base → hover → active → focus-visible → disabled → loading.
- Slot architecture: default / icon-left / icon-right / label (avoid prop explosion).
- State model rules:
  - Local state: inside a single component
  - Lifted state: shared across siblings
  - Context state: global-ish (theme/auth/locale/toasts)
  - **Server state**: never via `useState+useEffect`; use TanStack Query or SWR
- Size limit: no component file over 250 lines (split into subcomponents/hooks).
- **Cross-viewport reflow** (invoke `06_LAYOUT` for the 8-tier page system):
  - Declare how the component behaves across page tiers (`xs`–`4xl`) when placed in page chrome
  - Use **container queries** for component-internal reflow (`cqw` / `@container`)
  - Touch targets ≥ **44×44px**; no horizontal overflow at **320px**
  - Keep internal spacing balanced (intra ≤ ~50% of inter; prefer tokenized gaps)

## L3 (resources)

- `resources/token-tiers.md`
- `resources/slot-architecture.md`
- `resources/state-model.md`
- Contracts: `contracts/component-architecture.schema.json`, `contracts/state-model.schema.json`, `contracts/state-matrices.schema.json`
