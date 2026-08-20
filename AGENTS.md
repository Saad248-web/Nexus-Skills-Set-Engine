# Jade_ReVamp — NEXUS APEX v4.0 Agent Orchestrator

> **AI:** This is the project agent memory for **Jade_ReVamp** (Jade Retreats marketing + booking site). On every user prompt, run the **Engine Loop** below before writing code. Engine skills live under `NEXUS_v4_APEX/<ENGINE>/SKILL.md`.

## Project context (always honor)

| Area | Detail |
|------|--------|
| **Product** | Luxury villa retreats — browse villas, enquire, book, pay (Razorpay), weddings/corporate/experiences |
| **Stack** | Next.js **14** App Router, TypeScript, Tailwind, GSAP / Framer Motion / Lenis, PostgreSQL (`pg`), Vitest + Playwright |
| **App code** | `src/app/*`, `src/components/*`, `src/lib/*`, `src/data/*` |
| **APIs** | `src/app/api/*` — bookings, leads, payments, webhooks, IndexNow |
| **Media** | Large `public/` tree; manifest via `scripts/generate_media_manifest.mjs` |
| **SEO / GEO** | `public/llms.txt`, JSON-LD, villa layouts, sitemap — treat as first-class |
| **Audits** | `audit-report.md`, `WEBDEV-Audit.md` for backlog and API inventory |
| **Quality gate** | From `NEXUS_v4_APEX/`: `npm run gate` when changing contracts or engines |

**Stack note:** NEXUS `09_BUILD` targets Next.js 15; this repo is **14** — follow existing patterns in `src/` and `next.config.mjs`, not generic v15-only guidance.

---

## THE ENGINE LOOP (mandatory)

Do **not** jump straight to code. For each prompt:

### Step 1 — Analyze intent (brief)

- Read the prompt; name target domains (UI, API, DB, SEO, security, CI, etc.).
- Reply with a **1–2 sentence** intent summary (can be inline, not a long preamble).

### Step 2 — Select engine & load skills

- Map intent using the **Routing matrix** below.
- **Read** `NEXUS_v4_APEX/<ENGINE>/SKILL.md` for every selected engine (use the Read tool).
- For structural or cross-cutting work, also read:
  - `NEXUS_v4_APEX/ENGINE_CHEATSHEET.md`
  - `NEXUS_v4_APEX/CONVENTIONS.md`
- For project-specific continuity, read `NEXUS_v4_APEX/90_MEMORY/SKILL.md` when scope spans sessions or architecture.
- Do not implement until L1/L2 rules from those files are applied.

### Step 3 — Execute & contract

- Implement using ingested engine rules only (no cross-engine rule mixing).
- **Contract-first:** typed, validated outputs where the framework requires schemas.
- Before finishing, apply **`0A_ANTISLOP`** guardrails (quality, security, no hand-waving).

---

## Routing matrix

### META (routing & guardrails — load when unsure)

| Engine | Use when |
|--------|----------|
| `00_CORE` | Orchestration, contracts, verify-work |
| `0A_ANTISLOP` | **Always** before finalize — guardrails, reviewer rules |
| `0H_HERMES` | Proposals, audits, self-improvement with approval |
| `0P_PLUGINS` | Optional plugin adapters |
| `01_FORGE` | IA, PRD, acceptance criteria, navigation |
| `02_INSIGHT` | Analytics, experiments, measurement |
| `90_MEMORY` | Session handoff, project state, long-running context |

### Jade — common task → engine map

| User intent | Engines to read first |
|-------------|------------------------|
| Hero, scroll sections, carousels, motion | `05_MOTION`, `06_LAYOUT`, `07_COMPONENTS` |
| Responsive / balanced layouts (320–2560px+) | `06_LAYOUT`, `04_TYPE`, `07_COMPONENTS`, `08_A11Y` |
| Villa cards, amenities, overlays, forms UI | `07_COMPONENTS`, `08_A11Y`, `03_PALETTE`, `04_TYPE` |
| Booking flow, availability, admin | `10_API`, `11_DATA`, `15_SECURE`, `09_BUILD` |
| Leads, careers multipart, webhooks | `10_API`, `15_SECURE`, `11_DATA` |
| Razorpay, payments | `10_API`, `15_SECURE`, `12_SYNC` |
| SEO, sitemap, JSON-LD, metadata | `21_SEO`, `22_GEO`, `09_BUILD` |
| `llms.txt`, AI crawlers, entity SEO | `22_GEO`, `21_SEO` |
| Images, LCP, bundle, Lenis/GSAP perf | `16_PERFORM`, `09_BUILD` |
| Vitest, Playwright, CI | `18_TEST`, `19_SHIP` |
| Middleware, CSP, rate limits | `15_SECURE`, `17_GOVERN` |
| Deploy, secrets, GitHub Actions | `19_SHIP`, `20_OBSERVE` |

### Full engine index

**Meta & memory:** `00_CORE` · `0A_ANTISLOP` · `0H_HERMES` · `0P_PLUGINS` · `01_FORGE` · `02_INSIGHT` · `90_MEMORY`

**Design:** `03_PALETTE` · `04_TYPE` (fluid 320–2560) · `05_MOTION` · `06_LAYOUT` (8-tier + balanced) · `07_COMPONENTS` · `08_A11Y`  

**Implementation:** `09_BUILD` · `10_API` · `11_DATA` · `12_SYNC` · `13_AI` · `14_EVAL`  

**Hardening & delivery:** `15_SECURE` · `16_PERFORM` · `17_GOVERN` · `18_TEST` · `19_SHIP` · `20_OBSERVE`  

**Growth:** `21_SEO` · `22_GEO`  

**Operator:** `91_PORTFOLIO` · `92_FREELANCE` · `93_MOBILE`

---

## Critical rules

1. **Never bypass the matrix** — e.g. new API route → read `10_API` first; new section UI → read `07_COMPONENTS` (+ `05_MOTION` if animated).
2. **Progressive disclosure** — L1/L2 from each `SKILL.md`; L3 examples only when needed.
3. **Engines interact via contracts only** — do not blend internal rules across engines.
4. **Scope to Jade** — prefer extending `src/` patterns over new abstractions; check audits before large refactors.

*(Jade_ReVamp + NEXUS APEX v4.0 — ready)*
