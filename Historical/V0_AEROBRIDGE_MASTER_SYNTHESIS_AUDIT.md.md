# AEROBRIDGE — MASTER SYNTHESIS AUDIT

**Document type:** Independent, evidence-based adjudication deliverable
**Scope:** Design, UX, interaction, state, accessibility, responsive, learning-UX, and design-system decisions for the AeroBridge share-preview prototype
**Method:** Critical re-evaluation of the complete evidence package (prototype source, screenshots, design ground truth, and nine unified audits). This is **not** a summary of the nine audits and **not** a majority vote. Every high-stakes conclusion was checked against Tier-1 source before acceptance.
**Master principle carried from `ideas.md` and reinforced across audits:** *The UI may interpret engine state; it must never invent engine truth.*

---

## EVIDENCE-INTEGRITY NOTE ON THIS DOCUMENT

This audit distinguishes three evidence tiers and does not upgrade a claim on repetition alone:

- **Tier 1 (E4 — directly verified here):** confirmed by my own read of `Home.tsx`, `index.css`, `App.tsx`, `Map.tsx`, `ideas.md`.
- **Tier 2 (rendered):** the supplied screenshots (Progression, Scenarios, Growth Record ×3 tabs, Progress Tracking, and the Practice/Terminal capture referenced by the audits).
- **Tier 4/5 (analytical):** the nine audits (ChatGPT, Claude, DeepSeek, Gemini, Grok, Kimi, Manus, Qwen, v0). Treated as expert opinion, not truth.

Files I could **not** inspect in this pass, and therefore mark honestly: `index.html` (font `<link>`, viewport `maximum-scale`), `ErrorBoundary.tsx`, `NotFound.tsx`, and the hosted `/manus-storage/...` assets were not in the supplied set. Any claim depending on them is marked **NEEDS VALIDATION** rather than asserted. No live device, screen reader, or desktop/tablet screenshot was available; every physical-behavior and desktop-layout claim is likewise marked.

---

## A. EXECUTIVE DECISION

**Overall direction: PRESERVE AND REFINE.**

AeroBridge is a genuinely distinctive, coherent *Flight Deck Console* — a professional aviation-training workstation, not a generic SaaS dashboard with aviation words. The product identity, the terminal-first Practice surface, and the end-to-end learning loop (`Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action`) are real in code, not decorative: an assessment computes a score, persists to `localStorage`, and resurfaces as evidence in Growth and Tracking, and cross-screen `setPracticeContext` handoffs actually work. These are the hardest things to manufacture and they already exist. A redesign, an IA change, or an architecture reset is **not** justified by any evidence in the package — and would violate the stated reference-preservation intent.

However, the prototype is **not yet a trustworthy visual contract**, for one repeated reason that matters more in a *training* product than anywhere else: **it occasionally manufactures evidence and success.** This is not a taste problem; it is a truthfulness problem, and it is the fastest possible way to destroy the product's entire value proposition ("evidence you can trust").

**The three most important decisions:**

1. **Fix the empty-command → `FQD` coercion (AB-F001, P0).** Verified in source: `const nextCommand = command.trim().toUpperCase() || "FQD"` (`Home.tsx:275`) returns "FARE DISPLAY RETURNED", pushes a real history entry, and fires `toast.success("Command accepted. Evidence captured.")` (`L294`) — a fabricated pass with no user input. In Assessment it inflates the persisted score. This is the single blocking defect.
2. **Make every visible state truthful (AB-F002, AB-F003, AB-F004).** Neutralize the fabricated first-load Coach error; give every metric an explicit provenance (illustrative / local / calculated); and make every control either perform its action or honestly say it is a preview. Never `toast.success` a no-op.
3. **Establish the accessibility + readability baseline (AB-F006, AB-F010).** Raise informational text to a readable floor and to AA contrast, add tablist/landmark/focus-trap semantics, and confirm pinch-zoom is not disabled — without turning the dense workstation into a consumer app.

The evidence is **sufficient to proceed to the next design-refinement stage** for P0/P1. Font loading, pinch-zoom, real device/keyboard behavior, desktop/tablet layout, and Arabic scope remain genuine gaps that must be validated (§J) before they are closed.

---

## B. PRODUCT AND DESIGN PRINCIPLES TO PRESERVE

| # | Preserve | Why it is successful (evidence) | Acceptable modification | Do not change |
|---|---|---|---|---|
| B1 | **Flight Deck Console identity** — deep navy surfaces, single Vector Blue accent, green/amber/red operational semantics, monospace readouts | Distinctive and domain-aligned across all 7 renders and `index.css` tokens; 9/9 audits independently praise it | Contrast/luminance tuning of tokens (§F) | Hue family, dark-mode foundation, restrained palette |
| B2 | **Terminal-first Practice surface** | First in document order, full-width, dedicated Focus Mode, command history recall (`ArrowUp/Down`, `Home.tsx:265-272`) — it is the product's true center of gravity | Mobile spacing/hierarchy hardening | Do **not** cardify or shrink it into a widget |
| B3 | **The wired evidence loop** (`assessmentScore` → `localStorage` → Growth/Tracking; `setPracticeContext` handoffs) | Directly verified in source; genuinely functional, not mock | Add provenance labels around it | Command-matching, scoring formula, persistence schema, route map |
| B4 | **Learn / Practice / Assessment mode structure + Focus Mode** | Pedagogically coherent; Focus Mode is the most-praised single UX decision | Add focus trap + `Escape` (§F) | The three-mode model; Assessment staying inside the Terminal |
| B5 | **Progress Tracking chart with a real `role="table"` data-table alternative** (`Home.tsx:206`) | Strongest accessibility artifact in the codebase; sourced from the same data the bars render | Use as the template for any future data-viz | Do not replace with a chart library for its own sake |
| B6 | **Honest local-simulation disclosure** ("LOCAL TRAINING SIMULATION", "ILLUSTRATIVE · VERIFY WITH YOUR COURSE MATERIAL", `L304`) | Correctly frames the engine boundary | Extend the same discipline to Growth/Tracking metrics | The disclosure pattern itself |
| B7 | **Reduced-motion coverage** (global catch-all + component refinements incl. the terminal caret) | More thorough than most production apps; verified as handled | — | Keep; do not regress |
| B8 | **Evidence-to-next-action language** ("Practice the gap", "Move the signal forward", "Open targeted practice") | Turns metrics into an operational next move — the product's pedagogical spine | — | Do not replace with generic SaaS copy or gamification |

---

## C. CRITICAL PROBLEMS

| ID | Problem | Evidence | User / Product Impact | Severity | Decision |
|---|---|---|---|---|---|
| AB-F001 | Empty/whitespace submit is coerced to `FQD`, recorded as an accepted command, and celebrated with a success toast | **E4** `Home.tsx:275` (`|| "FQD"`), `L294` `toast.success(...)`; corroborated by 5+ audits reading the same line | Fabricated evidence; inflated Assessment score; trainee is told they succeeded having done nothing — destroys the core "trustworthy evidence" promise | **Critical** | **MUST FIX (P0)** |
| AB-F002 | Coach panel renders a red `FORMAT ERROR · CHECK ENTRY` with a specific correction **before any command is typed** | Screenshot (fresh Practice) + audit source cite (`Home.tsx:311` `?? "FORMAT ERROR · CHECK ENTRY"`); contradicts the neutral `AWAITING COMMAND` header | First-use trust defect on the most important screen; implies a failure the user never caused | **High** | **MUST FIX (P0)** |
| AB-F003 | Hardcoded/illustrative numbers presented with the authority of computed evidence | **E4**: "3 / 8 stages" (`L226`) vs a 6-item `levels` array; "6 of 9 command sets" (`L223`); pre-submit `accuracy = ... : 86` (`L256`); seeded session clock `useState(272)` (`L250`); Scenarios "23 / 40" vs 5 defined scenarios | Trainee cannot tell sample data from their own result; the product's own numbers do not reconcile, contradicting a precision positioning | **High** | **MUST FIX (P0/P1)** |
| AB-F004 | Multiple controls fire `toast.success/info` while performing no action ("Backup" claims a backup point was created; "My route", "View map", "See all stages", Filters, Search, Language) | **E4** `Home.tsx:164, 168, 212, 219, 226(action), 229`; "Backup" success language | Same class of trust erosion as AB-F001 — "looks functional, isn't" — concentrated on high-visibility controls | **High** | **SHOULD FIX (P1)** |
| AB-F006 | Informational text below comfortable size and AA contrast | **E4** `--text-faint:#5d6a85` on `--navy-950:#050914` (~3.66:1 computed); 9px `.eyebrow`; primary button white on `--blue:#6f8fff` (~2.98:1 reported) | Long-session unreadability and AA failure in a product meant for hours of training | **High** | **SHOULD FIX (P1)** |

---

## D. MASTER DECISION MATRIX

Scoring key: Impact / Confidence / Cost / Risk each Low·Med·High. "Source" lists whether the finding is source-verified (E4), rendered (E2), or analytical only.

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Tech Feasibility | Impact | Confidence | Cost | Risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| AB-F001 | Terminal / Safety | Empty/whitespace submit = inline "Enter a command" no-op; no history, no score, no toast. Unknown non-empty routes to existing SYNTAX ERROR branch, never `FQD` | **MUST FIX** | E4 `L275/294` | Prevents fabricated evidence | Neutral (behavioral) | High (guard in submit path) | High | High | Low | Low | E4 |
| AB-F002 | Terminal / Trust | First-use Coach = neutral `READY / AWAITING COMMAND`; error styling only after a real failed entry | **MUST FIX** | E4 + screenshot | Removes false failure | Strengthens | High (conditional render) | High | High | Low | Low | E4+E2 |
| AB-F003 | Content / Trust | Derive counts from array lengths where possible; mark remaining sample values "ILLUSTRATIVE / LOCAL"; replace pre-submit `86` with a neutral placeholder; start clock at `00:00` unless a resumed session is real | **MUST FIX** | E4 `L226/256/250` | Restores evidence integrity | Neutral | High | High | High | Low–Med | Low | E4 |
| AB-F004 | Interaction / Trust | Every control: perform the action, OR label "preview / unavailable" with `toast.info`, OR remove. Never claim an artifact ("backup point") was created | **SHOULD FIX** | E4 handlers | Removes false affordances | Strengthens | High | Med–High | High | Low | Low | E4 |
| AB-F005 | Typography | Confirm the three declared families load; if not, load them (`font-display: swap`) or correct the token to the true shipped stack | **NEEDS VALIDATION** → then **SHOULD FIX** | `index.html` not in set | Identity fidelity | Strengthens | High | Med | Med (needs check) | Low | Low | Analytical |
| AB-F006 | Accessibility / Visual | Raise informational text to ≥12px (≥11px only with proven contrast); lift `--text-faint` and primary-button contrast to ≥4.5:1 (≥3:1 large). Preserve hue and density | **SHOULD FIX** | E4 tokens + computed | Legibility / AA | Preserves palette | High (token edit) | High | High | Low | Low–Med | E3/E4 |
| AB-F007 | Terminal / State | Render the already-declared states that matter (processing, interrupted, empty, partial); one dominant session status line; keep a persistent, non-truncated mobile status readout | **SHOULD FIX** | E4 `SystemState` taxonomy vs rendered UI | Orientation/error-catching | Strengthens | Med | High | Med | Med | Low | E4 |
| AB-F008 | Layout / Hierarchy | Terminal ≥ ~2/3 on desktop; Coach subordinate/collapsible; on mobile keep latest-result + input above an optional collapsed Coach; remove the duplicated "SYSTEM RESPONSE" echo | **SHOULD FIX (w/ modification)** | E2 + source | Protects primary workstation | Strengthens | Med | High | Med | Med | Med | E2/E4 |
| AB-F009 | Content / Mission | Do not claim a language switch that does not happen. Either implement real `dir="rtl"` + Cairo, or relabel EN/AR as a preview/roadmap with `toast.info` | **NEEDS VALIDATION** (scope) → **SHOULD FIX** (honesty now) | E4 `L164` | Saudi-market honesty | Neutral | High (relabel) / High-cost (full i18n) | High | High | Low (relabel) | Low | E4 |
| AB-F010 | Accessibility | Add `role="tablist"/tab/aria-selected` to all 5 segmented controls; `<main>` + skip link; focus trap + `Escape` on drawers/Focus Mode/search; ≥44px frequent targets; verify `maximum-scale` is not disabling zoom | **MUST FIX** (semantics) + **NEEDS VALIDATION** (viewport) | E4 (zero `role="tab"` in source; `.icon-button` 38→35→33px); `index.html` unverified | Keyboard/AT + mobile usability | Strengthens | High | High | High | Low–Med | Low | E4 (+ analytical for html) |
| AB-F011 | Learning integrity | Make the mode contract explicit (what is preserved/reset/recorded); surface carried hints/commands on entering Assessment; unify the two Reference triggers' hint policy | **SHOULD FIX (w/ modification)** | E4 (`hintCount`/`history` survive mode switch; `L303` counts a hint, coach reference does not) | Assessment credibility | Neutral | Med | High | Med | Med | Med | E4 |
| AB-F012 | Design system | Consolidate the parallel `--ab-*` token layer into one canonical semantic set; document radius/spacing/type scales | **COULD IMPROVE** | E4 (dual token layers) | Maintainability | Strengthens | Med | High | Med | High | Med | E4 |
| AB-F013 | Responsive | Dedicated visual + keyboard pass at 320/360/390/430 + tablet/desktop | **NEEDS VALIDATION** | E2/E3 (`min-width:320px`; strongest rules at 360/390) | Prevents narrow-width collapse | Neutral | Med | High | Med | Low | Low | Analytical |
| AB-F014 | Visual / Hierarchy | Simplify decorative KPI clip-paths/guilloché on Tracking & Growth so they never compete with data | **COULD IMPROVE** | E2 screenshots | Scannability | Strengthens | Low | High | Low–Med | Med | Low | E2 |
| AB-F015 | Tech hygiene | Remove unused `Map.tsx`/`MapView` (imported nowhere; `App → Home` only) | **SHOULD FIX** | E4 import trace | Dead-code/bundle | Neutral | Low | High | Low | Low | Low | E4 |
| AB-F016 | Resilience | Mount and style `ErrorBoundary` so a crash keeps the console identity, not a white screen | **NEEDS VALIDATION** → **SHOULD FIX** | Analytical (`ErrorBoundary.tsx` not in set) | Failure-state trust | Strengthens | Med | High | Low | Low–Med | Low | Analytical |
| AB-F017 | Learning integrity | The `hint-dependency` `ErrorKind` appears in the Assessment legend (`L236`) but is never producible by the matcher | **COULD IMPROVE** | E4 | Minor confusion | Neutral | High | High | Low | Low | Low | E4 |
| AB-F018 | Content / Semantics | `skillRows` trend "down" is styled tone "good"/"warn" by direction, not favorability — a falling score can wrongly read positive | **SHOULD FIX** | E4 `L90-96` | Misreads performance | Strengthens | High | High | Med | Low | Low | E4 |

---

## E. REQUIRED CHANGES BY PRIORITY

### P0 — Blocking / Must Fix (before the enhanced prototype can be approved)

**P0-1 · Empty-command safety (AB-F001)**
- **Objective:** No command event may exist without user input.
- **Current problem:** `command.trim().toUpperCase() || "FQD"` fabricates a passing `FQD` with a success toast.
- **Exact change:** In `submitCommand`, if `command.trim() === ""` → keep input focus, show inline "Enter a command before executing.", `return` before any history/score/toast/state mutation. Remove the `|| "FQD"` fallback. Unknown non-empty input already resolves to the SYNTAX ERROR branch — keep that.
- **Must remain unchanged:** All valid command outputs (AN/SS/FQD/FXP), the scoring formula, `localStorage` shape.
- **Reason:** Evidence integrity is the product's core promise.
- **Dependencies:** None. **Risks:** Low (isolated guard). **Priority:** P0.

**P0-2 · Neutral first-use Coach (AB-F002)**
- **Objective:** First use is calm and error-free.
- **Current problem:** Coach defaults to red `FORMAT ERROR · CHECK ENTRY` before any entry.
- **Exact change:** Render error styling/content only when `latestEntry?.ok === false`. With no history, show a neutral "AWAITING COMMAND — start with availability (AN)."
- **Must remain unchanged:** Post-failure error presentation.
- **Reason:** Removes a fabricated failure at the moment of first impression. **Risk:** Low.

**P0-3 · Evidence provenance + reconcile counts (AB-F003)**
- **Objective:** Every number is either derived or labeled.
- **Exact change:** `3 / 8 stages` → derive from `levels.length`; `23 / 40` → derive from `scenarios.length` (or "N of M available now"); pre-submit accuracy `86` → neutral `—`; session clock → start `00:00` unless a resumed session is genuinely restored; add a quiet `ILLUSTRATIVE / LOCAL` marker to remaining sample values.
- **Must remain unchanged:** Real computed values from `assessmentScore`; the presentation-first sample content is **relabeled, not deleted**.
- **Reason:** Prevents contradictory learner truth. **Risk:** Low–Med (content decisions).

**P0-4 · Confirm pinch-zoom + fonts are not silently broken (AB-F005, AB-F010 viewport)**
- **Objective:** Close the two unverifiable-but-high-impact gaps before sign-off.
- **Exact change:** Verify `index.html`; if `maximum-scale=1`/`user-scalable=no` present, remove; if the three font families are not loaded, load them or fix the token. (See §J — these are validation-gated, not assumed.)

### P1 — High-Value Improvements

- **P1-1 · Honest controls (AB-F004):** audit every `toast.success`; each must map to a real state change or be downgraded to `toast.info` "preview", or the control removed. Never claim a "backup point".
- **P1-2 · Readability & contrast baseline (AB-F006):** documented type scale, ≥12px informational floor, `--text-faint` and primary-button ≥4.5:1. Keep density and palette hue.
- **P1-3 · Accessibility semantics (AB-F010):** tablist semantics on all 5 segmented groups; `<main>` + skip link; focus trap + `Escape` + focus-restore on drawers/Focus Mode/search; ≥44px frequent targets.
- **P1-4 · Terminal state completeness + mobile status (AB-F007):** render processing/interrupted/empty/partial; one dominant session status; persistent, non-truncated mobile status line.
- **P1-5 · Terminal/Coach hierarchy (AB-F008):** Terminal ≥2/3 desktop; Coach subordinate/collapsible; remove the duplicated system-response echo.
- **P1-6 · Trend semantics (AB-F018):** decouple arrow direction from good/bad; color by favorability of the metric, not direction.
- **P1-7 · AR honesty (AB-F009):** relabel as preview now (zero-cost); full RTL deferred to scope decision.

### P2 — Optional / Later

- **P2-1 · Token consolidation (AB-F012)** — merge `--ab-*` into `:root`.
- **P2-2 · Decorative reduction on Tracking/Growth (AB-F014).**
- **P2-3 · Remove dead `Map.tsx` (AB-F015); mount `ErrorBoundary` (AB-F016).**
- **P2-4 · Assessment mode contract transparency (AB-F011); remove/justify `hint-dependency` legend entry (AB-F017).**

---

## F. COMPONENT-LEVEL SPECIFICATIONS

### F1 · Terminal (Practice) — the primary workstation
- **Current state:** Full-width panel, mode tabs, command input with history recall, Coach block, Reference drawer, Focus Mode, session readout.
- **Problems:** AB-F001 (empty→FQD), AB-F002 (fake error), AB-F007 (incomplete states), AB-F008 (Coach competition + duplicated echo), AB-F011 (mode bleed).
- **Decision:** Preserve structure; fix truthfulness and state completeness.
- **Layout:** Desktop — Terminal ≥2/3, Coach a subordinate sticky rail. Mobile — order = task strip → mode tabs → terminal (output + active line) → sticky input → optional collapsed Coach.
- **Spacing:** Replace the fixed `terminal-gap: 130px` + `min-height: 280px` empty band on mobile with flexible spacing capped so no pre-output empty region exceeds ~1 line; let history grow.
- **Typography:** Keep IBM Plex Mono for command/readout; input stays 16px (iOS zoom prevention — preserve).
- **Color:** Status never by color alone — pair with text/glyph (SUCCESS / SYNTAX ERROR / SEQUENCE ERROR).
- **Dimensions:** Input row and Execute button ≥44px touch height.
- **Interaction:** Empty submit = inline no-op; `ArrowUp/Down` recall preserved; Focus Mode gains a focus trap + `Escape`.
- **States (render these):** `first-use/ready` (neutral), `processing`, `success`, `partial-success`, `error` (only post-failure), `interrupted`, `assessment-active`, `assessment-complete`, `empty`.
- **Responsive:** Persistent one-line status at ≤739px; validate 320–430px.
- **Accessibility:** `role="tablist"` on mode tabs; failed command announced via assertive live region; success polite.
- **Preserve:** command engine, Focus Mode, local-sim disclosure, history recall.
- **Reject:** command autocomplete; cardifying the terminal; per-command success toasts.

### F2 · Coach panel
- **Problem:** Fabricated default error; echoes the terminal's response.
- **Decision:** Neutral first-use; interpretation/next-move only (not a duplicate of terminal output). Desktop subordinate rail; mobile collapsible drawer with focus management. Error content strictly gated on `latestEntry?.ok === false`.

### F3 · KPI / metric cards (Tracking, Growth, Scenarios)
- **Problem:** Illustrative values styled identically to computed evidence; decorative clip-paths add noise (AB-F003, AB-F014).
- **Decision:** Derive-or-label provenance; simplify decorative backgrounds; keep the accessible data-table pattern as the reference for any data-viz.

### F4 · Segmented controls (mode tabs, metric switcher, track tabs, growth tabs, scenario filters)
- **Problem:** Plain buttons; zero `role="tab"`/`aria-selected` in source.
- **Decision:** One shared tablist pattern — `role="tablist"/tab`, `aria-selected`, roving arrow-key focus — applied to all five. Consolidate tokens (§F7) before writing it once.

### F5 · Buttons
- **Problem:** Primary button contrast ~2.98:1; several buttons are toast-only.
- **Decision:** Darken `--blue` or lighten text to ≥4.5:1; ensure `:hover/:focus-visible/:active/:disabled` are all defined; honest labels for preview controls.

### F6 · Language switch (EN/AR)
- **Problem:** Cosmetic; claims a switch that does not happen.
- **Decision:** Relabel as preview now; full `dir="rtl"` + Cairo + translation deferred to scope decision. Never `toast.success` a language change that did not occur.

### F7 · Design tokens
- **Problem:** Parallel `--ab-*` layer + magic radii (9/11/14px).
- **Decision:** One canonical semantic layer (surface tiers, text, status, interaction, type, motion); radius scale `--radius-sm 8/ --radius 12 / --radius-lg 16`; document spacing/type. Do after P0 safety.

---

## G. SCREEN AND FLOW CHANGES

| Screen | Current issue | Decision | Key changes | Preserve |
|---|---|---|---|---|
| **Progression** | "3/8 stages" & "6 of 9 command sets" do not reconcile with data; track toggle only swaps description text | Fix counts; add honest "coming soon" to the hollow Customer Service track | Derive from `levels.length`; label sample metadata | Hero route card, Resume CTA, stage map, ring |
| **Practice** | AB-F001/F002/F007/F008/F011; per-command toasts | Truthful + state-complete workstation | See §F1/F2; remove per-command success toasts (keep session-level "Assessment saved") | Command logic, Focus Mode, disclosures |
| **Scenarios** | "23/40" and "82% / +6%" illustrative; Filters/Sort are dead-ends; "Exchanges & Refunds" category not present in data | Reconcile or label; wire or relabel Filters/Sort | Derive counts; honest controls | Mission-file detail panel, Start/Resume/Review logic |
| **Growth Record** | "Backup" claims a backup point; trend arrows map to direction not favorability | Relabel Backup; fix trend tone logic (AB-F018) | Provenance labels; quieter decoration | Record/History/Reports tabs, "read → practice → apply" strip |
| **Progress Tracking** | Decorative KPI clip-paths add noise; metrics illustrative | Simplify KPI backgrounds; label provenance | Keep data-table alternative as the template | Metric switcher, route line, trend readout, chart |

**No new screens or flows are introduced.** The five-area IA and the loop are preserved exactly. **ASSUMPTION** (flagged): the Customer Service track is intended to hold real curriculum later — until confirmed, present it as "coming soon" rather than swapping copy on the same data.

---

## H. RESPONSIVE, ACCESSIBILITY, AND STATE REQUIREMENTS (testable)

**Responsive**
- **Mobile (≤739px):** No pre-output empty band > ~1 line in the terminal; sticky 16px input reachable without scrolling past the Coach; persistent one-line session status visible; no horizontal scroll at 320/360/390/430px.
- **Tablet (740–1099px):** Resolve the hybrid (multi-column content + mobile bottom rail) — either commit to it deliberately or give it a dedicated nav identity. **NEEDS VALIDATION.**
- **Desktop (≥1100px):** Persistent side rail; Terminal ≥2/3 with subordinate Coach column.

**Accessibility (testable)**
- Grayscale test: every status distinguishable without color.
- Keyboard-only path through Terminal, drawers, and all tab groups; arrow-key tab navigation; `Escape` closes overlays and restores focus.
- No informational text < 12px; informational contrast ≥4.5:1 (≥3:1 large); primary button ≥4.5:1.
- All frequent controls ≥44×44px.
- `<main id="main-content">` + skip link present; route change moves focus to `<h1>`.
- Pinch-zoom works (viewport does not disable scaling). **NEEDS VALIDATION** against `index.html`.

**States**
- **Loading/processing:** visible terminal processing indicator (the taxonomy already declares it).
- **Empty:** Growth/Tracking with no records show an honest "No evidence yet" + CTA to Practice (already partly implemented — keep).
- **Error:** only after a real failed entry; announced assertively.
- **Success:** session-level only (e.g., "Assessment saved"); no per-command success spam.

---

## I. EXPLICIT REJECTION LIST

| ID | Rejected recommendation | Source | Reason for rejection | Future validation? |
|---|---|---|---|---|
| R1 | Redesign / re-theme into a modern SaaS dashboard | implied across some audits | Violates reference-preservation intent; identity is the strongest asset | No |
| R2 | Merge Growth Record and Progress Tracking into one "Analytics" screen | Manus (finding), others | They serve different loop functions: Tracking = longitudinal signal, Growth = immediate pedagogical interpretation. Merging dilutes the learning loop | No |
| R3 | Add command autocomplete | DeepSeek/others (feature ideas) | Violates recall-based training pedagogy | No |
| R4 | Add Pause/Resume, global sticky next-action widget, trend overlays/sparklines, or activate a map | multiple | Engine/state inventions or dashboardization with no evidence of need; next-action already exists at point of need | No |
| R5 | Switch the hand-built chart to Recharts | some audits | The existing chart already has an accessible data-table alternative; no interaction requirement justifies the swap | Only if richer interaction is later required |
| R6 | Two-click "Finish Session" confirmation | one audit | Adds friction to a primary flow with no destructive-ambiguity evidence | No |
| R7 | Treat the 5-item bottom nav as a live "4-column grid bug" | v0 | **Source-refuted:** later higher-specificity rules (one `!important`) set 5 columns and `.is-primary` is fully styled. Keep only as a CSS-debt regression note | Regression check only |
| R8 | Treat mobile session readout as "hidden (`display:none`)" | v0, Kimi | **Source-refuted:** `.page-practice .terminal-session-readout` restores it. Real issue is *compression*, handled under AB-F007 | No |
| R9 | Treat the terminal caret blink as ignoring reduced-motion | Manus, Kimi | **Source-refuted:** explicitly named inside a `prefers-reduced-motion` block | No |
| R10 | Over-gamify (streaks/badges/confetti) | anti-pattern flagged by several | Undermines professional maturity for aviation professionals | No |
| R11 | Simulate Arabic by flipping a highlight / partial RTL without scope | all (as anti-pattern) | Reproduces the exact "looks done, isn't" defect this audit corrects; do real i18n or honestly relabel | Yes — scope decision |

---

## J. VALIDATION PLAN

| # | Decision under test | Objective | Method | Measure | Success criteria | Result that would change the recommendation |
|---|---|---|---|---|---|---|
| V1 | Font loading (AB-F005) | Confirm the three declared families render | Inspect computed `font-family` on `h1`, `.terminal-body`, and an Arabic container in the running preview | Rendered family | Declared families, not `system-ui` | If already loaded → downgrade to "no action"; if unloadable → correct token to true fallback |
| V2 | Pinch-zoom (AB-F010 viewport) | Confirm scaling is not disabled | Read `index.html` viewport meta + device pinch test | `maximum-scale`/`user-scalable` values | Pinch-zoom works | If not disabled → close the finding |
| V3 | Empty-submit fix (AB-F001) | Prove no fabricated evidence | Submit empty/whitespace in Learn/Practice/Assessment | history rows, score delta, toast, localStorage writes | Zero of each; inline hint shown; valid commands byte-identical | Any history/score change → fix incomplete |
| V4 | Mobile terminal ergonomics (AB-F007) | Prove no hollow work surface | 320/360/390/430px, fresh + after 4 commands, keyboard open | empty-band height, input reachability | No band > ~1 line; input reachable; status line visible | Persistent large empty band → revisit spacing |
| V5 | Contrast/readability (AB-F006) | Meet AA at rendered sizes | Automated + manual contrast on all screens | contrast ratios, min font sizes | ≥4.5:1 informational; no informational text <12px | Any informational failure → adjust token/size |
| V6 | Accessibility semantics (AB-F010) | Keyboard/AT operability | Screen-reader + keyboard-only pass | tab semantics, focus trap, landmarks, announcements | Full keyboard path; overlays trap/restore; errors announced | Any trap/announcement gap → extend fix |
| V7 | Tablet identity (AB-F013) | Resolve hybrid nav | 740/834/1024px live | layout coherence | Deliberate, non-awkward nav | Awkward → give tablet a dedicated nav identity |
| V8 | Arabic scope (AB-F009) | Release decision | Product/content review | in-scope? | Decision made before any RTL build | In-scope → full i18n/RTL/bidi program |

---

## K. IMPLEMENTATION HANDOFF

1. **Implement approved decisions only.** P0 first (AB-F001, F002, F003, and the V1/V2 validations), then P1, then P2. Do not bundle unrelated redesigns.
2. **Do not touch** command matching, the `assessmentScore` formula, the `localStorage` schema, `setPracticeContext` handoffs, or the route map. All accepted changes are UI/content/interaction only.
3. **Sequence within Practice:** ship AB-F001 and AB-F002 as isolated, screenshot-verifiable commits (each is a single guard/conditional) before any further terminal polish, with an explicit before/after regression check confirming non-empty command outputs are unchanged.
4. **Preserve** everything in §B. When in doubt, keep the Flight Deck identity and terminal-first posture.
5. **Truthful-state rule governs all UI copy:** no control may imply success, navigation, or an artifact it did not produce; no metric may imply real performance unless computed. Relabel illustrative data — do not delete it (the preview is presentation-first).
6. **Treat unresolved conflicts (§L) as documented open questions**, not as license to invent engine semantics, curriculum data, or new screens.
7. **Validate (§J) before closing** AB-F005, AB-F009, AB-F010 (viewport), AB-F013, AB-F016 — they depend on files/devices not available in this pass.

---

## L. OPEN QUESTIONS AND ASSUMPTIONS

| Question / Assumption | Why it matters | Decisions affected | What is needed |
|---|---|---|---|
| Is Arabic in this release? | Determines build vs. honest relabel | AB-F009 | Product/content scope decision |
| What does "Saudi readiness (24%)" actually measure? | It is presented as authoritative but is hardcoded | AB-F003 | Definition + data source |
| What does "Backup" mean (export / cloud / local snapshot / prototype-only)? | Currently claims a success it cannot deliver | AB-F004 | Product definition |
| Are the illustrative counts (23/40, 3/8) placeholders for future content or accidental? | Changes derive-vs-relabel choice | AB-F003 | Content ownership confirmation |
| **ASSUMPTION:** Customer Service track will hold real curriculum later | Justifies "coming soon" instead of copy-swap | Progression screen | Curriculum confirmation |
| Do the three declared fonts load in the deployed host? | Identity fidelity + Arabic readiness | AB-F005 | `index.html`/runtime check (V1) |
| Is pinch-zoom disabled? | WCAG 1.4.4 | AB-F010 | `index.html` check (V2) |
| Real device keyboard/screen-reader behavior | Mobile workstation usability + AT | AB-F007, AB-F010 | Device/AT session (V4, V6) |
| Should opening Reference in Learn mode count as a hint? | Assessment scoring integrity | AB-F011 | Learning-design decision |

---

## M. FINAL RECOMMENDATION

**Implement (now):**
- AB-F001 empty-command safety (P0), AB-F002 neutral first-use Coach (P0), AB-F003 provenance + reconciled counts (P0), AB-F004 honest controls (P1), AB-F006 readability/contrast (P1), AB-F010 accessibility semantics (P1), AB-F007 terminal state + mobile status (P1), AB-F008 Coach hierarchy (P1), AB-F018 trend semantics (P1), AB-F009 AR relabel-for-honesty (P1).

**Preserve:**
- The Flight Deck identity, terminal-first Practice, the wired evidence loop, Learn/Practice/Assessment + Focus Mode, the accessible chart data-table, reduced-motion coverage, local-simulation disclosures, and evidence-to-next-action language (§B).

**Defer:**
- Token consolidation (AB-F012), decorative reduction (AB-F014), dead-code removal + ErrorBoundary mounting (AB-F015/F016), assessment-mode contract transparency (AB-F011), full Arabic/RTL implementation (pending scope), tablet nav identity (pending validation).

**Reject:**
- Full redesign, Growth/Tracking merge, autocomplete, Pause/Resume, global next-action widget, chart-library swap, two-click Finish, gamification, simulated/partial Arabic, and the three source-refuted "bugs" (bottom-nav 4-col, hidden mobile readout, caret reduced-motion) — see §I.

**Validate before closing:**
- Font loading, pinch-zoom, empty-submit behavior, mobile terminal ergonomics, contrast, AT/keyboard semantics, tablet identity, Arabic scope (§J).

**Readiness verdict:** The evidence is **sufficient to proceed to the next design-refinement stage.** The direction is settled (Preserve and Refine), the P0 defects are specific, source-verified, and low-risk to fix, and the accepted P1 set is well-supported. The remaining gaps are explicitly enumerated as **NEEDS VALIDATION** rather than left as hidden assumptions — they gate the *closure* of specific findings, not the start of the work.

---

### FINAL QUALITY CHECK (self-verification against the protocol)
- Evaluated the actual prototype and screenshots, not just the audits — **yes** (source-verified `Home.tsx:275/294/256/250/226`, `index.css` tokens, import trace for `Map.tsx`).
- Considered all nine audits; recorded agreements **and** disagreements; **no majority voting** — resolved three factual CSS conflicts against source (§I R7–R9) *against* the more numerous claim.
- Every MUST FIX has evidence + reason; preservation set is explicit; rejections recorded; validation separated from confirmed decisions.
- No invented functionality, screens, or requirements; feasibility and existing functionality respected; no unnecessary redesign.
- Prioritized by impact × confidence × feasibility with cost/risk; unavailable files (`index.html`, `ErrorBoundary.tsx`, `NotFound.tsx`, hosted assets) explicitly declared and not claimed as evaluated.
