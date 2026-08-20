## Container queries (Module 04)

Components should define their own breakpoints based on content, not device classes.

- Use `@container` rules with `cqw` where supported
- Identify the exact pixel range where content breaks, then codify it as a component breakpoint

**Reconciliation:** the 8 device breakpoints (`resources/breakpoints.md`) govern **page chrome**, section grids, and nav. Container queries govern **component internals** — do not replace one with the other.
