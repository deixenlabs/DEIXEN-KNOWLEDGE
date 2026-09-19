# AEROBRIDGE — MASTER SYNTHESIS AUDIT

**Document Type:** Independent Master Synthesis Audit  
**Date:** 2026-08-15  
**Status:** NEEDS TARGETED REVISION  
**Evidence Base:** Original prototype source (`Home.tsx` 363 lines, `index.css` 408 lines, `index.html`, `ideas.md`), 7 rendered mobile screenshots, 9 independent unified audits (Claude, ChatGPT, DeepSeek, Gemini, Grok, Kimi, Manus, Qwen, v0.dev)

**Master Principle (from design ground truth):**  
*The UI may interpret engine state, but it must never invent engine truth.*  
*This is a reference-preservation project, not a redesign.*

---

## A. Executive Decision

**Overall Direction: Preserve and Refine**

AeroBridge is a high-fidelity, distinctive Flight Deck Console prototype with a real end-to-end learning loop (Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action). The visual identity, Terminal-first architecture, Focus Mode, evidence-to-next-action language, reduced-motion handling, and accessible chart+table pattern are genuine strengths that must be protected.

The prototype is **not** production-ready as a definitive visual/contract reference because of a small set of high-impact trust and safety defects that undermine its core promise of precision and evidence integrity. These defects are directly verifiable in source and screenshots. They do not require a redesign or architecture reset.

**Three most important decisions:**

1. **Fix the two Terminal trust/safety defects immediately (P0):** empty command silently becomes FQD; Coach shows fabricated FORMAT ERROR before any user action. Both are source-verified and create false training events or false failure states.
2. **Establish an explicit Evidence Provenance contract (P0/P1):** every displayed metric or status must declare whether it is illustrative, local, calculated, or authoritative. Hardcoded numbers currently sit beside real localStorage records with identical visual weight.
3. **Preserve the Flight Deck identity, Terminal primacy, and learning-loop architecture without exception.** No recommendation that dashboardizes the Terminal, gamifies the product, invents engine semantics, or adds new top-level routes is accepted.

The work is a controlled, sequenced revision pass focused on truthfulness, Terminal ergonomics, accessibility baselines, and prototype honesty. Implementation effort is low-to-medium for the P0 set and does not touch command matching, scoring formula, or localStorage schema.

---

## B. Product and Design Principles to Preserve

### 1. Flight Deck Console Visual Identity
- **What:** Deep navy surfaces, Vector Blue accents, green/amber/red operational semantics, monospace command/readout treatment, restrained atmospheric route imagery, asymmetric desktop composition.
- **Why successful:** Creates immediate domain credibility and differentiates the product from generic SaaS/LMS dashboards. Confirmed across all screenshots and all nine audits.
- **Acceptable modification:** Token value adjustments for contrast/readability; minor radius/spacing consolidation.
- **Do not change:** Core palette hue relationships, monospace role for commands, overall cinematic but operational tone.

### 2. Terminal-First Practice Surface + Focus Mode
- **What:** Terminal is the primary workstation (not a card). Learn / Practice / Assessment modes live inside it. Focus Mode exists. Sticky mobile input with 16px floor intent. Command history via Arrow Up/Down. Explicit “LOCAL TRAINING SIMULATION / ILLUSTRATIVE” labeling.
- **Why successful:** Correctly positions the core skill (GDS command workflow) as the product’s center of gravity. Engineering details (safe-area, sticky input) show deliberate mobile intent.
- **Acceptable modification:** Neutral first-use state, empty-submit guard, mobile spacing refinement, Coach subordination, full Focus Mode keyboard contract.
- **Do not change:** Terminal primacy, mode structure, Focus Mode concept, local-simulation disclosure pattern, command vocabulary or scoring logic.

### 3. Evidence → Next-Action Learning Loop
- **What:** Assessment records persist to localStorage and surface in Growth/Tracking. Context handoffs (`setPracticeContext`) from Progression, Scenarios, Growth, and Tracking into Practice are real. Growth’s “Read evidence → Practice the gap → Apply in scenario” strip and Tracking’s chart + data-table alternative are high-value patterns.
- **Why successful:** Creates a coherent pedagogical spine rather than disconnected screens. Directly verifiable in source.
- **Acceptable modification:** Provenance labeling, honest empty/locked states, clearer mode/hint contracts.
- **Do not change:** The loop itself, context-handoff mechanism, localStorage shape, chart+table pairing.

### 4. Mobile Navigation Model
- **What:** Five-item bottom rail with Train (Practice) deliberately center-emphasized; desktop persistent sidebar.
- **Why successful:** Reinforces Terminal primacy on the most common training device. Source contains explicit intent comments.
- **Acceptable modification:** Touch-target sizing, aria-current consistency, CSS cascade cleanup.
- **Do not change:** Five-item model or Train elevation.

### 5. Accessibility Foundations Already Present
- **What:** Global `:focus-visible`, some `aria-live`, Progress Tracking data-table alternative, thorough `prefers-reduced-motion` (global catch-all + component-specific rules including caret).
- **Why successful:** Stronger than average for a prototype of this fidelity.
- **Acceptable modification:** Complete tab semantics, focus traps, landmarks, contrast floor, non-color state markers.
- **Do not change:** Existing reduced-motion contract or chart table pattern.

---

## C. Critical Problems

| ID | Problem | Evidence | User / Product Impact | Severity | Decision |
|----|---------|----------|-----------------------|----------|----------|
| CP-01 | Empty / whitespace command is silently coerced to `FQD` and recorded as evidence | `Home.tsx` submit handler: `command.trim().toUpperCase() \|\| "FQD"`; confirmed by multiple source audits | Creates false training events and corrupts assessment integrity; trainee can “succeed” without acting | Critical | MUST FIX |
| CP-02 | Coach panel renders red “FORMAT ERROR · CHECK ENTRY” + fabricated correction before any command exists | `Home.tsx` fallback `latestEntry?.response ?? "FORMAT ERROR · CHECK ENTRY"` + body text; visible in Practice screenshot | First-use trust failure on the core screen; contradicts READY state | Critical | MUST FIX |
| CP-03 | Hardcoded / illustrative metrics presented with the same authority as real local records (86% accuracy pre-submit, 128/210, 3/8 stages vs 6 levels, 23/40 scenarios, LOG 04/12 vs 3 rows, etc.) | Source constants + seed data vs rendered arrays; visible in multiple screenshots | Undermines “evidence you can trust” positioning; trainee discovers numbers do not reconcile | High | MUST FIX (provenance) |
| CP-04 | Multiple controls fire success/info toasts while performing no action (Backup, Language, View map, Filters, Sort, Search, See all stages, etc.) | Direct `toast.success` / `toast.info` handlers in `Home.tsx` | False affordances erode professional trust | High | MUST FIX / SHOULD FIX |
| CP-05 | Declared fonts (Space Grotesk, IBM Plex Mono, Cairo) are not loaded; Google Fonts block is commented for deletion | `index.html` explicit comment block; CSS tokens reference the families | Typography identity is theoretical; Arabic readiness blocked | High | MUST FIX |
| CP-06 | Viewport meta contains `maximum-scale=1` | `index.html` | Disables pinch-zoom (WCAG 1.4.4) | High | MUST FIX |
| CP-07 | Primary button and faint text contrast fall below or near AA thresholds at rendered sizes | CSS tokens (`--text-faint: #5d6a85`, primary blue values); computed ratios in detailed audits | Long-session readability and CTA accessibility suffer | High | SHOULD FIX |
| CP-08 | Tab / toggle groups lack `role="tablist"` / `aria-selected` / `aria-pressed` semantics across five control sets | Zero occurrences of these attributes in `Home.tsx` (verified by audits and source) | Keyboard and screen-reader users cannot determine selection state | High | SHOULD FIX |
| CP-09 | EN/AR toggle is purely cosmetic (toast only; no `dir`, no translation, no font switch) | `Home.tsx` language handler | Claims a mission-critical feature that does not exist | High (mission) | MUST FIX (honesty) |

---

## D. Master Decision Matrix

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Technical Feasibility | Impact | Confidence | Cost | Risk | Source |
|----|------|-------------------|---------------|----------|-------------|--------------------|-----------------------|--------|------------|------|------|--------|
| MD-01 | Terminal Safety | Empty submit → no history, no score, no toast; inline “Enter a command” only | MUST FIX | Source E4 | Critical trust/safety | Strengthens honesty | High (1-line guard) | Very High | Very High | Low | Low | Source + all audits |
| MD-02 | Terminal Trust | Coach default = neutral READY / AWAITING COMMAND; error styling only after real failure | MUST FIX | Source + screenshot E4 | Critical first-use trust | Strengthens consistency | High | Very High | Very High | Low | Low | Source + screenshots |
| MD-03 | Evidence Truth | Every metric declares provenance (ILLUSTRATIVE / LOCAL / CALCULATED); derive counts from arrays where possible | MUST FIX | Source + screenshots | High credibility | Strengthens system | Medium | High | Very High | Low-Med | Low | Source + consensus |
| MD-04 | False Affordances | Inventory every toast-only control: implement, label “Preview / Roadmap”, or remove | MUST FIX | Source E4 | High trust | Strengthens honesty | Medium | High | Very High | Med | Low | Source + consensus |
| MD-05 | Typography Loading | Load declared fonts or correct tokens to actual shipped stack | MUST FIX | index.html E4 | Identity + Arabic readiness | Restores intent | High | High | High | Low | Low | Source |
| MD-06 | Pinch Zoom | Remove `maximum-scale=1` | MUST FIX | index.html E4 | A11y compliance | Neutral | High | High | High | Low | Low | Source |
| MD-07 | Contrast | Raise meaningful muted text and primary-button contrast to ≥4.5:1 (or approved large-text exception) while preserving hue | SHOULD FIX | CSS + computed | Readability / AA | Strengthens system | High | High | High | Low | Low | Multiple audits + CSS |
| MD-08 | Tab Semantics | Apply shared `role="tablist"` / `aria-selected` pattern to all five segmented controls | SHOULD FIX | Source (zero occurrences) | Keyboard / SR | Strengthens a11y | High | High | High | Low-Med | Low | Source |
| MD-09 | AR Honesty | Disable or relabel EN/AR toggle as “Arabic — Roadmap” until real i18n/RTL scope is decided | MUST FIX (scoping) | Source | Mission honesty | Strengthens trust | High | High | Very High | Low | Low | Source + mission |
| MD-10 | Terminal State Language | One dominant session-status summary always visible (incl. mobile); non-color markers for success/error | SHOULD FIX | Source taxonomy vs UI | Orientation | Strengthens workstation | Medium | High | High | Med | Low | Source + audits |
| MD-11 | Coach Hierarchy | Terminal ≥ ~2/3; Coach subordinate / collapsible on mobile; never steals primary vertical space by default | SHOULD FIX | Layout + screenshots | Hierarchy | Protects Terminal primacy | Medium | Med-High | High | Med | Low | Multiple |
| MD-12 | Focus Mode A11y | Add focus trap, Escape, restore focus, dialog semantics | SHOULD FIX | Source | Keyboard users | Strengthens a11y | Medium | High | High | Med | Low | Audits + source |
| MD-13 | Landmarks / Skip | Add `<main>`, skip link, route-focus to heading | SHOULD FIX | Source | A11y | Neutral | High | Med-High | High | Low | Low | Source |
| MD-14 | Touch Targets | Enforce ≥44×44 px (or approved equivalent) on frequent mobile controls | SHOULD FIX | CSS cascade (38→35→33 px) | Mobile usability | Neutral | High | Med-High | High | Low | Low | CSS |
| MD-15 | Token Consolidation | Fold `--ab-*` layer into one canonical semantic token set after P0 safety | COULD IMPROVE | CSS dual layers | Maintainability | Strengthens system | Medium | Med | High | Med | Low | Source |
| MD-16 | Decorative KPI Reduction | Reduce pure ornament on Tracking/Growth that does not answer an operational question | COULD IMPROVE | Screenshots | Cognitive load | Protects instrument feel | Medium | Med | Med | Low | Low | Visual |
| MD-17 | Service Track Honesty | Explicit “in preparation” empty state instead of technical content under both tabs | SHOULD FIX | Source | Content honesty | Strengthens trust | High | Med | High | Low | Low | Source |
| MD-18 | Assessment Mode Contract | Explicitly surface what is preserved/reset and any carried hint count when entering Assessment | SHOULD FIX | Source mode behavior | Learning integrity | Strengthens contract | Medium | Med-High | High | Med | Low | Source |
| MD-19 | Bottom-nav 4-col claim | Reject as current defect (later cascade rules set 5 columns) | REJECT | Full cascade trace | N/A | Avoids unnecessary change | N/A | Low | High | — | — | Source cascade |
| MD-20 | Mobile session readout “hidden” claim | Reject as current defect (later `.page-practice` rule restores it) | REJECT | Full cascade trace | N/A | Avoids unnecessary change | N/A | Low | High | — | — | Source cascade |
| MD-21 | Two-click Finish Session | Reject (button already disabled until history exists; adds friction without demonstrated need) | REJECT | Source + reasoning | Avoids friction | Protects flow | N/A | Low | High | — | — | Reasoning |
| MD-22 | Global Next-Action widget | Reject (risk of dashboardization; contextual CTAs already exist) | REJECT | Product intent | Avoids dilution | Protects Terminal | N/A | Med | High | — | — | Intent |
| MD-23 | Command autocomplete | Reject (violates recall-based pedagogy) | REJECT | Pedagogy + intent | Protects learning model | Neutral | N/A | High | High | — | — | Intent |
| MD-24 | Activate unused Map.tsx | Reject (no curriculum evidence of value; external asset risk) | REJECT | Source (unused) | Avoids scope drift | Neutral | N/A | Med | High | — | — | Source |
| MD-25 | Full Arabic/RTL build now | NEEDS VALIDATION / DEFER (scope decision required first) | NEEDS VALIDATION | Mission vs effort | Mission critical if in scope | Architecture | High if scoped | High | Med | High | High | Mission |
| MD-26 | Exact 320 px + real keyboard behavior | NEEDS VALIDATION | CSS rules exist; physical device untested | Mobile operability | Neutral | Medium | High | Med | Med | Med | Device gap |
| MD-27 | Desktop/tablet composition | NEEDS VALIDATION | No desktop screenshots; CSS breakpoints only | Layout coherence | Neutral | Medium | Med | Med | Med | Med | Evidence gap |

---

## E. Required Changes by Priority

### P0 — Blocking / Must Fix (before treating prototype as visual contract)

**P0-1 Empty Command Safety**  
- **Objective:** Prevent false evidence events.  
- **Current problem:** `|| "FQD"` coerces blank input into a real command.  
- **Exact change:** Guard `if (!command.trim()) { show inline message; return; }`. No history, score, toast, or localStorage write.  
- **Must remain unchanged:** Non-empty command matching, scoring, sequence logic.  
- **Reason:** Direct evidence-integrity and training-safety defect.  
- **Dependencies:** None.  
- **Risks:** Low (isolated).  
- **Priority:** P0.

**P0-2 Neutral Coach First-Use State**  
- **Objective:** Remove fabricated failure on first entry.  
- **Current problem:** Fallback string + red styling before any command.  
- **Exact change:** When `!latestEntry`, render neutral “AWAITING COMMAND / Submit a command to receive coaching” with non-error styling. Error path only after real `ok === false`.  
- **Must remain unchanged:** Coach content model after real responses.  
- **Reason:** First-use trust failure on core screen.  
- **Dependencies:** None.  
- **Risks:** Low.  
- **Priority:** P0.

**P0-3 Evidence Provenance Contract**  
- **Objective:** Make every number’s owner visible.  
- **Current problem:** Hardcoded values share visual authority with real records.  
- **Exact change:** (a) Derive stage/scenario/log counts from actual array lengths where the array exists; (b) add compact, consistent “LOCAL / ILLUSTRATIVE” markers for remaining seed values; (c) replace pre-submit 86% with neutral placeholder (“—” or “No evidence yet”).  
- **Must remain unchanged:** Real localStorage-backed records and calculation formulas.  
- **Reason:** Core product positioning depends on trustworthy evidence.  
- **Dependencies:** None for derivation; content decision for future totals.  
- **Risks:** Low.  
- **Priority:** P0.

**P0-4 Font Loading**  
- **Objective:** Make declared typography real.  
- **Exact change:** Uncomment / restore font loading for Space Grotesk, IBM Plex Mono, Cairo (or self-host) and wire `--font-ar` for future RTL.  
- **Must remain unchanged:** Token role definitions.  
- **Reason:** Identity is currently theoretical.  
- **Dependencies:** None.  
- **Risks:** Low.  
- **Priority:** P0.

**P0-5 Pinch-Zoom**  
- **Objective:** Restore WCAG 1.4.4 compliance.  
- **Exact change:** Remove `maximum-scale=1` from viewport meta.  
- **Must remain unchanged:** Other viewport settings.  
- **Reason:** Accessibility regression.  
- **Dependencies:** None.  
- **Risks:** Low.  
- **Priority:** P0.

**P0-6 AR Toggle Honesty**  
- **Objective:** Stop claiming a non-existent feature.  
- **Exact change:** Disable interaction or label “Arabic — Roadmap / Coming soon”; never fire success toast that implies language changed.  
- **Must remain unchanged:** Future real i18n architecture (out of scope).  
- **Reason:** Mission honesty.  
- **Dependencies:** Product scope decision for full Arabic.  
- **Risks:** Low.  
- **Priority:** P0 (scoping).

**P0-7 False-Affordance Inventory (core set)**  
- **Objective:** Eliminate success claims for no-ops.  
- **Exact change:** For Backup, Language (already covered), View map, See all stages, Filters (if duplicate), Sort, Search, Profile: either wire real behavior, mark “Preview”, or remove. Prefer “Preview / unavailable” over silent toast.success.  
- **Must remain unchanged:** Working primary CTAs and context handoffs.  
- **Reason:** Professional trust.  
- **Dependencies:** Product decisions per control.  
- **Risks:** Low.  
- **Priority:** P0 for success-claiming toasts; P1 for remaining stubs.

### P1 — High-Value Improvements

- Contrast floor for meaningful muted text and primary button (preserve hue).  
- Shared tab/toggle ARIA pattern applied to all five groups.  
- Terminal session-status summary always visible on mobile; non-color state markers.  
- Coach subordination on mobile (collapsed by default or validated sheet; Terminal vertical priority wins).  
- Focus Mode + drawer focus trap / Escape / restore.  
- `<main>` + skip link + route focus.  
- Touch targets ≥44×44 px on frequent controls.  
- Assessment mode contract transparency (carried hints / preserved history).  
- Service track explicit empty / “in preparation” state.  
- Honest Backup and remaining secondary controls.

### P2 — Optional / Later

- Full token consolidation (`--ab-*` into canonical layer).  
- Decorative KPI reduction on Tracking.  
- 320 px dedicated visual + keyboard matrix.  
- ErrorBoundary / NotFound AeroBridge styling (when production paths wired).  
- Micro-copy and motion polish only after A–D stable.

---

## F. Component-Level Specifications

### Terminal / Command Input
- **Current:** Sticky, 16px intent, history ↑/↓, empty → FQD.  
- **Decision:** Empty = inline validation only; processing lock while evaluating; keep sticky + safe-area.  
- **Typography:** Mono for commands; ≥16 px mobile input.  
- **States:** empty (inline message), ready, processing, success, error (syntax/sequence), interrupted.  
- **A11y:** Persistent focus affordance; live region for new responses (polite) / errors (assertive when urgent).  
- **Preserve:** History recall, sticky behavior, local-simulation labeling.  
- **Reject:** Autocomplete, defaulting to any real command.

### Coach Panel
- **Current:** Defaults to red FORMAT ERROR; desktop near-equal column; mobile below fold.  
- **Decision:** Neutral first-use; subordinate (≤1/3 desktop, collapsed/default-hidden or sheet on mobile after validation); remove duplicated system-response echo.  
- **States:** awaiting, guidance, error (only post-failure), assessment-locked.  
- **Preserve:** Interpretation role, “Guidance without shortcuts” framing.  
- **Reject:** Permanent equal-weight competition with Terminal.

### Primary Button / CTAs
- **Current:** Contrast reported ~2.98:1 in detailed analysis.  
- **Decision:** Adjust luminance or text color to meet AA at rendered size; keep Vector Blue family.  
- **States:** default, hover, active, disabled, loading.  
- **Preserve:** Operational verbs (Resume, Open targeted practice, etc.).

### Bottom Navigation
- **Current:** 5 items, Train centered; cascade contains historical 4-col rule superseded by later 5-col rules.  
- **Decision:** Keep 5-item + Train elevation; clean redundant declarations opportunistically.  
- **A11y:** `aria-current`, ≥44 px targets.  
- **Preserve:** Model and emphasis.  
- **Reject:** Any claim that current render is 4-column.

### Tab / Segmented Controls (Mode, Growth, Track, Metric, Filter)
- **Current:** Plain buttons; zero tab semantics.  
- **Decision:** Shared pattern: `role="tablist"`, `role="tab"`, `aria-selected`, keyboard arrows where appropriate.  
- **Preserve:** Visual style and order.

### Progress / KPI Rings & Bars
- **Current:** Some decorative clip-paths; AnimatedBar as bare `<i>`.  
- **Decision:** Keep data-driven rings; add proper progressbar semantics where missing; reduce pure ornament.  
- **Preserve:** Chart + data-table alternative on Tracking (exemplary).

### Language Toggle
- **Current:** Cosmetic success toast.  
- **Decision:** Disabled or “Roadmap” label; no success claim.  
- **Preserve:** Future slot for real i18n.

---

## G. Screen and Flow Changes

### Practice / Terminal (highest priority)
- **Issues:** CP-01, CP-02, fragmented orientation, Coach competition, mobile density.  
- **Decision:** Apply all P0 Terminal fixes; add persistent status line; subordinate Coach; complete Focus Mode a11y; remove per-command success toasts (keep session-level only).  
- **Hierarchy:** Terminal output + input first; Coach secondary; footer metrics honest.  
- **Do not touch:** Command engine, scoring, mode structure, Focus Mode concept, local disclosure.

### Progression
- **Issues:** 3/8 vs actual levels length; toast-only map/route actions; Service track hollow.  
- **Decision:** Derive counts; honest empty/prep state for Service; implement or label stubs.  
- **Preserve:** Hero + Resume CTA, Technical/Service split concept, stage language.

### Scenarios
- **Issues:** 23/40 + non-existent category; Filters/Sort stubs.  
- **Decision:** Derive or label stats; wire or mark Filters/Sort; keep mission-file framing and Practice handoff.  
- **Preserve:** Detail panel, skills, Start/Resume/Review language.

### Growth Record
- **Issues:** Backup false claim; LOG count mismatch; hover-only coaching on mobile.  
- **Decision:** Honest Backup; derive LOG; move essential coaching into selected detail for mobile parity.  
- **Preserve:** Learning-loop strip, strengths/needs-attention, pattern language, next-practice CTA.

### Progress Tracking
- **Issues:** Decorative KPI noise; some framing hardcoded.  
- **Decision:** Simplify ornament; keep table + metric switcher + next-action CTA; clear metric definitions.  
- **Preserve:** Data-table alternative, real record history, trend concept.

### Shared Shell
- **Issues:** Missing landmarks, incomplete drawer semantics, stub search/profile.  
- **Decision:** Add main/skip; complete focus management; honest utility states.  
- **Preserve:** URL sync, Train emphasis, overall 5-route model.

---

## H. Responsive, Accessibility, and State Requirements

### Responsive
- **Desktop ≥1100 px:** Sidebar persistent; Terminal primary column; Coach subordinate.  
- **Tablet 740–1099 px:** Validate hybrid (multi-column content + mobile-style nav); decide intentional identity or adjust. **NEEDS VALIDATION**.  
- **Mobile ≤739 px:** Bottom rail; Train centered; sticky input; Coach collapsed/subordinate by default; status line visible.  
- **Narrow floor:** Explicit validation matrix at 320 / 360 / 390 / 430 px with native keyboard. No horizontal scroll; input and latest result never permanently obscured.  
- **All widths:** Charts retain table alternative.

### Accessibility (testable)
- Contrast ≥4.5:1 for meaningful text at final size (or documented large-text exception).  
- Touch targets ≥44×44 px (or spacing equivalent) for frequent actions.  
- Full focus trap + Escape + restore for Focus Mode, drawers, search.  
- Tab / selected / current semantics on all segmented controls.  
- Landmarks + skip link; route change moves focus to primary heading or status.  
- Non-color state communication mandatory for operational states (text + icon + color).  
- Live regions: polite for new Terminal responses; assertive only when urgency warrants.  
- Pinch-zoom enabled.  
- Reduced-motion contract preserved and extended to any new motion.

### Required States (canonical matrix)
first-use / empty / ready / processing / success / partial-success / error (syntax / sequence / decision) / retry / interrupted / assessment-active / assessment-complete / review / locked / unavailable / loading.

Each state must be reachable and visually/semantically distinct without relying on color alone.

---

## I. Explicit Rejection List

| ID | Rejected Recommendation | Source | Reason for Rejection | Future Validation Needed? |
|----|-------------------------|--------|----------------------|---------------------------|
| R-01 | Redesign visual identity or turn into generic LMS/dashboard | Multiple style suggestions | Contradicts design ground truth and strongest asset | No |
| R-02 | Make Assessment a top-level route | Minority | Breaks Terminal primacy and workstation continuity | No |
| R-03 | Add command autocomplete | Some proposals | Violates recall-based pedagogy central to training | No |
| R-04 | Two-click Finish Session confirmation | Some implementation plans | Button already gated; adds friction without demonstrated destructive ambiguity | No |
| R-05 | Persistent global Next-Action widget | Minority | Risks dashboardization; contextual CTAs already exist | No |
| R-06 | Activate / finish unused Map.tsx | Presence of file + stub button | No curriculum evidence of instructional value; external asset risk | Only if product later requires stage-map |
| R-07 | Bottom-nav is currently 4-column / dead is-primary | v0.dev (and echoes) | Cascade trace shows later 5-col + styled is-primary rules win | No (treat as historical debt only) |
| R-08 | Mobile session readout is currently hidden | v0.dev / Kimi | Later higher-specificity `.page-practice` rule restores it | No |
| R-09 | Terminal caret ignores reduced-motion | Manus / Kimi | Explicit rule at index.css names `.terminal-caret` inside reduced-motion block | No |
| R-10 | Full Arabic/RTL implementation in this revision pass | Mission pressure | Scope decision required first; partial fake is worse than honest deferral | Yes — product scope |
| R-11 | Merge Growth + Tracking into one Analytics screen | Minority | Dilutes distinct pedagogical roles (interpretation vs longitudinal signal) | No |
| R-12 | Add gamification (badges, streaks, confetti) | Occasional suggestions | Undermines professional aviation-training maturity | No |
| R-13 | Invent new engine commands, scoring changes, or carrier data | Various | Violates “UI must never invent engine truth” | No |
| R-14 | Replace hand-built chart with library solely for modernity | Minority | Existing chart already has accessible table alternative | Only if richer interaction required |

---

## J. Validation Plan

| Decision | Objective | Method | Measure | Success Criteria | What would change recommendation |
|----------|-----------|--------|---------|------------------|----------------------------------|
| Empty command | No false evidence | Manual + automated submit tests on all modes/viewports | History length, score, toast, localStorage | Zero mutation on blank/whitespace | Any mutation → re-open as P0 |
| Coach first-use | Neutral state | Fresh session screenshot + SR check | Presence of error styling/copy | No red error or corrective text before first submit | Residual error styling → fix incomplete |
| Provenance | Every number owned | Full metric inventory vs source arrays | Unlabeled authoritative claims | Zero unlabeled hard-coded trainee evidence | Remaining claims → extend labeling |
| Fonts | Declared families load | Computed style inspection | font-family on heading, terminal, Arabic container | Matches intent, not system fallback | Still fallback → self-host or token correction |
| Pinch-zoom | Enabled | Device test | Ability to zoom to 200%+ | Zoom works | Still locked → meta not updated |
| 320–430 + keyboard | Terminal operable | Physical devices (iOS Safari, Android Chrome) | Input reachable, latest result visible, no jump | Input + result usable under keyboard | Persistent occlusion → Focus Mode / layout change |
| Tablet 740–1099 | Coherent hybrid | Device or emulator | Nav + content density feel intentional | Team accepts or adjusts | Awkward → dedicated tablet nav identity |
| Focus/keyboard | Full operability | Keyboard-only + SR (VoiceOver/NVDA) | Tab order, trap, Escape, announcements | All core flows completable without pointer | Trap failure → complete semantics |
| Contrast | AA at final size | Automated + manual | Ratios at rendered px | Meaningful text ≥4.5:1 (or documented exception) | Failures → token adjustment |
| Assessment contract | Transparent carry-over | Mode-switch tests with hints | Visible statement of carried state | Trainee can state what is preserved | Silent bleed → stronger UI disclosure |
| AR scope | Product decision | Stakeholder confirmation | Whether Arabic is in this release | Explicit yes (with plan) or honest roadmap | Scope change moves MD-25 |

---

## K. Implementation Handoff

**Implement only the approved decisions in this document.**

1. Execute P0 items first and independently (each is screenshot-verifiable in isolation).  
2. Lock regression on: command matching (AN/SS/FQD/FXP), assessmentScore formula, localStorage schema, route map, context handoffs.  
3. Preserve Flight Deck identity, Terminal primacy, Focus Mode concept, learning-loop language, chart+table pattern, reduced-motion contract, Train elevation.  
4. Do not introduce new routes, new engine semantics, gamification, global widgets, or map activation.  
5. Treat every remaining toast-only control as a product decision (wire / preview label / remove); never leave success language on a no-op.  
6. After P0, proceed to P1 accessibility and Terminal hierarchy; then P2 system hygiene.  
7. Any conflict with current source that is not listed here must be documented and validated, not solved by invention.  
8. When in doubt, prefer honesty (label illustrative) over deletion of useful prototype content.

**Regression gate before any phase closes:**  
AN → SS → FQD → FXP transcripts, assessmentScore outputs, localStorage shape, and all context handoffs remain byte-identical for non-empty valid paths.

---

## L. Open Questions and Assumptions

| Question / Assumption | Why it matters | Decisions affected | Information needed |
|-----------------------|----------------|--------------------|--------------------|
| Is Arabic/RTL in the next release scope? | Determines whether MD-09 is permanent honesty fix or interim only | MD-09, MD-25, font wiring | Product owner decision |
| Are the larger totals (8 stages, 40 scenarios) intentional future curriculum or accidental? | Affects how aggressively we derive vs label | MD-03, Progression/Scenarios counts | Content/curriculum owner |
| What is the authoritative definition of “Saudi readiness”? | Currently appears as hardcoded heuristic | Any readiness language | Product / content |
| Should Practice mode coach sequence errors (currently only Assessment enforces)? | Affects learning model | AB-F017-style behavior | Learning design decision |
| Exact physical keyboard + 320 px behavior | Mobile is primary workstation surface | MD-26, Coach placement, Focus Mode | Device lab pass |
| Desktop/tablet visual composition | No screenshots supplied | MD-27 | Desktop captures or live review |
| Production ErrorBoundary / NotFound visual language | Currently unmounted or off-brand risk | Fallback identity | When production paths are wired |

**ASSUMPTION (explicit):** Until the product owner states otherwise, Arabic is out of scope for the immediate revision; the toggle must therefore be honest about that fact.

---

## M. Final Recommendation

**Implement**  
- P0 safety and trust set (empty command, Coach first-use, provenance labeling, font loading, pinch-zoom, AR honesty, core false-affordance cleanup).  
- P1 accessibility and Terminal hierarchy (contrast, tab semantics, session orientation, Coach subordination, focus management, landmarks, touch targets, Assessment contract transparency, Service track honesty).

**Preserve**  
- Flight Deck Console identity and palette relationships.  
- Terminal-first architecture, Focus Mode concept, Learn/Practice/Assessment structure.  
- End-to-end evidence loop and context handoffs.  
- Chart + data-table alternative.  
- Reduced-motion contract.  
- Five-route model with Train elevated on mobile.  
- Operational language and local-simulation disclosure pattern.  
- Command matching, scoring formula, localStorage schema.

**Defer**  
- Full Arabic/RTL implementation (pending scope decision).  
- Token consolidation and decorative reduction (P2).  
- Any new features, routes, or engine changes.  
- Map activation.  
- Global Next-Action widget or gamification.

**Reject**  
- Redesign, dashboardization of Terminal, Assessment as top-level route, autocomplete, two-click finish, false 4-column or hidden-readout claims as current defects, invention of engine truth, and all other items in Section I.

**Validate**  
- 320/360/390/430 + native keyboard.  
- Tablet hybrid range.  
- Desktop composition (no screenshots).  
- Real font loading after restore.  
- Assessment mode carry-over policy with stakeholders.  
- Arabic scope.

**Sufficiency of evidence:**  
The current evidence package (source + screenshots + nine audits + design ground truth) is **sufficient to proceed** with the P0 and P1 revision pass. The remaining gaps are narrowly scoped (device keyboard matrix, desktop captures, product scope for Arabic and curriculum totals) and do not block the safety and honesty work.

**Final quality statement:**  
This Master Synthesis Audit independently re-verified the highest-stakes claims against the actual prototype source and screenshots. It does not majority-vote the nine audits. It preserves the product’s strongest assets, fixes only evidence-backed high-impact defects, rejects recommendations that conflict with design ground truth or introduce unnecessary risk, and clearly marks every item that still requires validation. The result is an implementation-ready decision document for the next controlled refinement of AeroBridge.

---

**End of Master Synthesis Audit**  
*The UI may interpret engine state, but it must never invent engine truth.*
