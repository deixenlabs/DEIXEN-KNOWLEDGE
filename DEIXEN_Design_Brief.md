---
name: DEIXEN Design Brief
status: CURRENT — first edition, 2026-09-25 (Execution Plan 3.4); synchronized 2026-09-25 with 07 Decision 27 and Verified Reference §2A. Creation approved by Karim (07, Decisions of 2026-09-25). Content awaits Karim's approval at the Phase 3 gate.
owns: What Claude Design receives for Phase 4 — the brief only. Adds no decision; every rule below cites its owner.
does not own: design principles, accessibility, anti-patterns (file 04); product structure (file 03); learner states (LXA); Coach contract (file 06); decisions (file 07); Amadeus behavior (Verified Reference)
---

# DEIXEN — Design Brief (for Claude Design, Phase 4)

## 1. The job

Design the first build of DEIXEN: a training platform where a beginner
learns to work in the real Amadeus reservation system (Cryptic command line)
well enough to be hired by a Saudi/Gulf airline or travel company (07
Decision 18). The first build is one complete vertical slice (07 Decisions 8A,
20, 22, 24): the learner books and prices a real reservation with

`AN → SS → NM → AP → SRCTCM → TK → RF → ER → FXP` (`FQD` optional)

and goes through the whole chain once: Learning → Terminal practice →
Scenario → Assessment → Evidence → Growth/Readiness (file 03).

Phase 4 steps (Execution Plan §3): (1) propose **2–3 distinct visual
directions**; (2) Karim chooses one; (3) refine the chosen direction across
the slice's screens and breakpoints. Claude Design proposes; Karim decides
(Constitution §8–9; 07 Decision 17).

## 2. Frozen — do not change

| Rule | Owner |
|---|---|
| Professional aviation-operations software. Not a consumer app, travel app, classroom product, LMS, quiz tool, or game | 03 Product Rules 1–2; 04 Design Positioning |
| **Terminal is the heart of the product.** Nothing may make it look secondary, optional, or like a quiz/exercise screen | 03; 04 "Clarity over decoration"; 07 Restricted Areas |
| Five top-level areas, no sixth: Home/Flight Deck · Learning/Curriculum · Terminal/Practice · Scenario Bank · Growth/Readiness. Assessment is a mode inside practice, not an area | 03 IA |
| Arabic + English, RTL + LTR, switchable | 07 Decision 11 |
| Accessibility floor: WCAG 2.1 AA contrast; full keyboard use with visible focus (including Terminal input); real ARIA roles for segmented controls; touch targets ≥44px (≥24px for dense secondary controls); honour reduced motion | 04 Accessibility |
| Breakpoints to validate: 320 / 360 / 390 / 430 / 768 / 1024 / 1280–1440 px. Desktop is a real workstation, not stretched mobile. Terminal workspace is never sacrificed on mobile | 04; 03 Platform Direction |
| Anti-patterns to avoid: generic SaaS dashboards, card-grid overload, pill overload, fake KPIs or decorative charts, gamification, children's-app look, decorative glassmorphism, travel-app look, visibly AI-generated templates | 04 Anti-Pattern List |
| Coach appears at five touchpoints (Learning, Terminal, Scenario, Assessment, Growth), driven by the learner's real state, never a static help panel | 06 Coach contract; 07 Decision 9 |
| No false affordance: every visible control works or is truthfully labeled planned/unavailable | 07 Definition of Done |
| Progress shows capability, never points, streaks, or completion percentages. Growth shows one qualitative status: Completed / In Progress / Needs More Practice — no numeric readiness score | 03 Rule 4; 07 D8A; LXA §8.7 |

## 3. Screens the slice needs

The eight learner states in the LXA (§8) are the set of experiences needing
visual form. Transitions between them: LXA §9.

| State | What the screen must do |
|---|---|
| `ORIENTATION` — Flight Deck | Show current status and **one** recommended next action; reach the other four areas. Not a marketing page, not a progress-only page |
| `LEARNING` — Lesson | Readable lesson; a clear bridge into Terminal practice |
| `GHOST_MODE` | Play / pause / replay a demonstration of commands; clearly "watching", not practising |
| `TERMINAL_PRACTICE` | Command line + history + three hint levels (Nudge / Partial Reveal / Full Reveal); retry; reset |
| `TERMINAL_ASSESSMENT` | Same Terminal, but entry into assessment is **visibly announced** — never a silent switch; hint use stays visible |
| `SCENARIO_SESSION` | Terminal framed by the scenario's objective and constraints |
| `GROWTH_READINESS` | The one qualitative status, tied to evidence; an honest empty state when there is no evidence yet |
| `RESET_RECOVERY` | Confirm / cancel a full reset |

Areas outside the slice (e.g. most of Scenario Bank, Customer Service)
appear only as truthfully labeled unavailable — never as working-looking
screens.

## 4. Terminal — design requirements

- **Three kinds of text must look different** (07 Decision 23; 06
  error-message discipline):
  1. **Amadeus output** — reproduced from verified official examples,
     monospace, realistic.
  2. **Training message** — shown when no verified Amadeus text exists (e.g.
     the exact error for a wrong entry). It must be visibly marked as a
     training message and never styled to pass as real Amadeus text.
  3. **Coach explanation** — plain language, placed *alongside* the output,
     never replacing a real Amadeus message.
- **The "Layout detail not fully verified" marker** (07 Decision 27): a
  small, visible label attached to an Amadeus display whose layout official
  examples show only in part (Build Spec §5). It labels the display — it is
  not a fourth kind of message — and must stay noticeable without making the
  Terminal look broken or alarming. Arabic: «تفصيل في الشكل غير موثَّق بالكامل».
- **Element numbers change as the booking grows** (07 Decision 27): e.g.
  the sold flight is line 1, then line 2 once a name exists. The design must
  let the learner follow a number changing between screens.
- Behavior states come from file 03's Terminal Behavioral Skeleton
  (Awaiting input → Submitted → Valid / Invalid → Hint → Completion →
  Reset). "Not recognized" and "not covered in this slice" are different
  messages.
- Terminal content stays in Latin monospace and left-to-right even when the
  interface is Arabic/RTL. *(Design question, not a decision — confirm with
  Karim in Phase 4.)*
- Mobile: input stays full-width and unobstructed; the on-screen keyboard
  covering history is a real problem to solve (LXA §18). Coach on mobile
  defaults to collapsed / on-demand (LXA §18).
- Desktop: Terminal, Coach, and reference may sit side by side (permitted,
  not required — LXA §18).

**Content rule for mockups.** Any Amadeus screen shown in a mockup must be
taken from a "DEIXEN rendering" in `DEIXEN_Amadeus_Verified_Reference.md`
§2A (V-14–V-18) — the verified layouts filled with DEIXEN's fictional data;
official screens themselves are not copied. Do not invent Amadeus screens, codes, or messages to
fill a mockup; if nothing verified fits, use an obviously generic placeholder
(Constitution §7; 07 Decision 13).

## 5. Directional — inputs, not requirements

- Personality (04): precise, calm under pressure, operational, trustworthy,
  modern, global — closer to flight-operations and control-system software
  than to dashboards. Color carries meaning (focus, primary action, data
  relationships, success, warning), not decoration.
- Typography (04): precise and highly readable, strong hierarchy between
  headings, actions, data, and status; never playful.
- Imagery (04 Visual Vitality): selective, high-quality, purposeful; never a
  photo gallery or stock collection.
- **Historical execution (04):** a dark navy/blue theme with specific tokens,
  Plus Jakarta Sans + Cairo + JetBrains Mono, 4/8 px spacing — built and
  approved by Karim in an earlier generation. It is evidence with equal
  standing to a fresh direction, neither approved nor rejected. At least one
  proposed direction should be genuinely different from it.

## 6. Open — to be decided in Phase 4

| Item | Decided by |
|---|---|
| Color palette; light vs. dark (or both) | Karim, after Claude Design's proposals |
| Typefaces (Latin, Arabic, monospace) | Karim |
| Logo / wordmark / identity. DEIXEN is a **provisional** name (Constitution §1) — identity work must not assume it is final | Karim |
| Flight Deck concept — Karim's stated requirement: distinctive, not AI-generic | Karim |
| Coach layout: one global element vs. per-page component | Delegated to Design/Code within 06's contract (07 Decision 9) |
| Keyboard-occlusion solution on mobile Terminal | Claude Design |

## 7. How each direction is judged

04's Design Evaluation Framework: brand alignment, product alignment,
operational realism, user clarity, Terminal support, professional readiness.
Each proposed direction states in a few lines how it meets each one and what
it risks.

## 8. What Claude Design delivers

1. 2–3 directions, each shown on at least the Flight Deck and the Terminal
   (mobile 390 px and desktop 1440 px), in both Arabic and English.
2. After Karim chooses: the eight states of §3 at the listed breakpoints,
   with tokens (color, type, spacing) defined in **one** place — the future
   token file is the single source of those values (04).
3. A short list of anything in this brief that turned out unclear or
   contradictory, instead of silently choosing (Constitution §18).
