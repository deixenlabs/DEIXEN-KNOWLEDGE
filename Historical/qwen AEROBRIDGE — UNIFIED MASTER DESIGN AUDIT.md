تم استلام الأمر. بصفتي **Principal Product Designer & UX Adjudicator**، قمت بتنفيذ البروتوكول متعدد المراحل (24 Passes) لتحليل جميع المصادر (الكود المصدري، الصور، وتقارير التدقيق التسعة). 

تم رفض أي توصيات تهدف إلى "إعادة التصميم" أو "اختراع متطلبات المحرك"، وتم دمج الرؤى العميقة من كل تقرير لإنتاج **المصدر الوحيد للحقيقة (SSOT)** لتصميم وتطبيق AeroBridge.

إليك التقرير الموحد والنهائي:

***

# ✈️ AEROBRIDGE — UNIFIED MASTER DESIGN AUDIT
**Document Status:** Authoritative Implementation Specification  
**Target Identity:** Professional Aviation Training Workstation (Flight Deck Console)  
**Core Principle:** *The UI may interpret engine state, but it must never invent engine truth.*

---

## 1. DESIGN STATUS
**NEEDS TARGETED REVISION**  
The prototype possesses a world-class visual identity and a structurally sound learning loop. It does **not** need a redesign. It requires a rigorous, evidence-based revision pass focused on **Trust, Terminal Ergonomics, Accessibility, and Prototype Honesty** before it can serve as the visual contract for the real Amadeus/GDS engine.

---

## 2. EXECUTIVE VERDICT
**What is strong:** The "Flight Deck Console" identity is highly defensible. The Terminal is correctly positioned as the primary workstation. The cross-screen evidence loop (Practice → LocalStorage → Growth/Tracking) is genuinely wired and structurally sound. Reduced-motion and mobile-input engineering (16px iOS zoom prevention) are exemplary.

**What is weak:** The prototype suffers from "Trust Defects." It presents fabricated errors on first load, executes silent default commands, displays hardcoded metrics as authoritative learner evidence, and features multiple "fake" controls that promise functionality but only fire toasts. Furthermore, foundational typography is declared in CSS but never loaded in the DOM.

**What must change:** Terminal first-run states, evidence truth boundaries, ARIA semantics, contrast ratios, and font loading.

**What must not change:** The 5-route architecture, the command evaluation logic (AN/SS/FQD/FXP), the scoring algorithm, the `localStorage` schema, and the dark navy/Vector Blue visual language.

---

## 3. SOURCE COVERAGE & EVIDENCE OVERVIEW
- **Artifacts Inspected:** `Home.tsx` (364 lines, entire UI/State), `index.css` (409 lines, Design System), `App.tsx`, `index.ts`, `Map.tsx`, `const.ts`, `ideas.md`.
- **Visual Evidence:** 5 rendered mobile screenshots (Progression, Scenarios, Practice, Growth, Tracking).
- **Analytical Evidence:** 9 independent AI UX Audits (v0.dev, Grok, DeepSeek, Kimi, Gemini, Qwen, ChatGPT, Manus, Claude).
- **Evidence Gaps:** Live runtime browser testing (focus traps, screen-reader announcements, exact 320px pixel-collisions) requires manual QA validation. Desktop layouts were inferred from CSS breakpoints.

---

## 4. AUDIT CONSENSUS OVERVIEW
- **Strongest Consensus (E4 - Directly Verified):** The Terminal is the heart of the product. Empty-submit executing `FQD` is a critical safety defect. The Coach panel's default "FORMAT ERROR" is a critical trust defect.
- **Conditional Consensus:** Token consolidation is needed, but the `.page-practice` scoped `--ab-*` tokens represent a *more mature* refinement pass and should become the canonical base, rather than being deleted.
- **Strongest Disagreements Resolved:** Some audits suggested adding "Command Autocomplete" or "Pause/Resume". **Adjudication:** REJECTED. Autocomplete violates the "recall-based learning" pedagogy. Pause/Resume is an Engine/State dependency that the UI must not invent.
- **Major Uncertainty:** The exact pedagogical definition of "Saudi Readiness" and whether Learn-mode hints should penalize Assessment scores. These are deferred to Product/Content owners.

---

## 5. CRITICAL DECISIONS
1. **The Engine Boundary:** The UI will strictly present state. It will not calculate fares, validate real PNRs, or invent Amadeus responses beyond the 4 hardcoded prefixes.
2. **Evidence Truth:** Hardcoded numbers (e.g., "23/40 Scenarios") must be replaced with dynamic array lengths or explicitly labeled as `Illustrative / Local Simulation`.
3. **Typography Reality:** The declared fonts (Space Grotesk, IBM Plex Mono, Cairo) must be physically loaded via `index.html` or `@font-face`. Fallback system fonts are unacceptable for a premium workstation.
4. **Arabic/RTL Scope:** The EN/AR toggle is currently a false affordance. It must be disabled/labeled "Roadmap" until a real i18n/RTL architecture is built.

---

## 6. CANONICAL FINDINGS

### AB-F001: Silent Empty Command Execution (The "FQD" Fallback)
- **Type:** Behavioral / Functional Safety
- **Sources:** `Home.tsx` (Line ~275: `command.trim().toUpperCase() || "FQD"`)
- **Evidence:** E4 (Source-Verified) | **Consensus:** Unanimous
- **Observation:** Pressing "Execute" with an empty input silently logs an `FQD` command, corrupting assessment evidence and training the user that empty inputs are valid operations.
- **Final Verdict:** **ACCEPT (Must Fix)**
- **Action:** Empty submit must yield an inline `NO ENTRY · TYPE A COMMAND` validation state. It must not alter history, score, or state.
- **Priority:** **P0 (Critical)**

### AB-F002: First-Run Fabricated Error in Coach Panel
- **Type:** Visual / Trust
- **Sources:** `Home.tsx` (Coach block fallback), `index.css` (`.coach-block code { color: var(--red) }`)
- **Evidence:** E4 (Source + Screenshot Verified) | **Consensus:** Unanimous
- **Observation:** Before any command is typed, the Coach panel displays a red-styled "FORMAT ERROR · CHECK ENTRY" alongside fabricated corrective text.
- **Final Verdict:** **ACCEPT (Must Fix)**
- **Action:** Default state must show a neutral "AWAITING COMMAND" readout. Red styling and error copy must only render when `latestEntry?.ok === false`.
- **Priority:** **P0 (Critical)**

### AB-F003: Unloaded Typography Stack
- **Type:** Design System / Foundational
- **Sources:** `index.css` (`:root` tokens), `index.html` (Commented out font links)
- **Evidence:** E4 (Source-Verified) | **Consensus:** High
- **Observation:** Space Grotesk, IBM Plex Mono, and Cairo are declared but never loaded. The UI renders in generic system fallbacks, breaking the aviation aesthetic and Arabic readiness.
- **Final Verdict:** **ACCEPT (Must Fix)**
- **Action:** Restore Google Fonts `<link>` or implement local `@font-face` hosting.
- **Priority:** **P0 (Critical)**

### AB-F004: Viewport Pinch-Zoom Restriction
- **Type:** Accessibility (WCAG 1.4.4)
- **Sources:** `index.html` (`<meta name="viewport" ... maximum-scale=1">`)
- **Evidence:** E4 (Source-Verified) | **Consensus:** Unanimous
- **Final Verdict:** **ACCEPT (Must Fix)**
- **Action:** Remove `maximum-scale=1` and `user-scalable=no`.
- **Priority:** **P0 (Critical)**

### AB-F005: Primary Button Contrast Failure
- **Type:** Accessibility (WCAG AA)
- **Sources:** `index.css` (`.primary-button` white text on `--blue #6f8fff`)
- **Evidence:** E4 (Computed Ratio: 2.98:1) | **Consensus:** High
- **Final Verdict:** **ACCEPT (Must Fix)**
- **Action:** Darken `--blue` or change text color to clear 4.5:1 for normal text.
- **Priority:** **P1 (High)**

### AB-F006: Misleading Prototype Metrics & False Affordances
- **Type:** Trust / UX
- **Sources:** `Home.tsx` (Hardcoded "23/40", "3/8 stages", "Backup" toast, "View Map" toast)
- **Evidence:** E3 (Corroborated) | **Consensus:** High
- **Final Verdict:** **ACCEPT WITH MODIFICATION**
- **Action:** Derive all counts from actual array lengths (`.length`). Convert dead-end buttons (View Map, Backup) to explicit "Preview / Roadmap" labels or remove the affordance.
- **Priority:** **P1 (High)**

### AB-F007: Missing ARIA Tab/Switcher Semantics
- **Type:** Accessibility
- **Sources:** `Home.tsx` (Zero occurrences of `aria-pressed`, `aria-selected`, or `role="tab"`)
- **Evidence:** E4 (Exhaustive Grep) | **Consensus:** High
- **Final Verdict:** **ACCEPT (Must Fix)**
- **Action:** Apply `role="tablist"` / `aria-selected` to all 5 segmented controls (Mode tabs, Metric switcher, Track tabs, Growth tabs, Scenario filters).
- **Priority:** **P1 (High)**

### AB-F008: Incomplete Terminal State Language
- **Type:** State System
- **Sources:** `Home.tsx` (`SystemState` type defines 14 states, UI renders ~6)
- **Evidence:** E2 (Source Analysis) | **Consensus:** Medium
- **Final Verdict:** **ACCEPT**
- **Action:** Define visual treatments for `processing`, `interrupted`, and `empty` states. Add non-color markers (glyphs/text) for success/error history rows.
- **Priority:** **P1 (High)**

### AB-F009: Mobile Terminal Ergonomics (Hidden Session Readout)
- **Type:** Responsive / UX
- **Sources:** `index.css` (`@media max-width: 739px { .terminal-session-readout { display: none; } }`)
- **Evidence:** E4 (Source-Verified) | **Consensus:** High
- **Final Verdict:** **ACCEPT (Must Fix)**
- **Action:** Mobile must retain a 1-line persistent status bar (Session / Command / Log) inside the terminal body to maintain workstation orientation.
- **Priority:** **P1 (High)**

### AB-F010: Design System Token Drift
- **Type:** Design System
- **Sources:** `index.css` (Base `:root` vs `.page-practice` scoped `--ab-*` tokens)
- **Evidence:** E4 (Source-Verified) | **Consensus:** High
- **Final Verdict:** **ACCEPT (Consolidate)**
- **Action:** Merge the superior `--ab-*` semantic tokens into the global `:root` to eliminate parallel color systems.
- **Priority:** **P2 (Medium)**

### AB-F011: EN/AR Language Toggle False Affordance
- **Type:** Trust / Mission
- **Sources:** `Home.tsx` (Fires toast, no `dir="rtl"`, no translation)
- **Evidence:** E4 (Source-Verified) | **Consensus:** Unanimous
- **Final Verdict:** **DEFER (Product Decision)**
- **Action:** Disable the toggle or label it "Arabic Roadmap" until real i18n/RTL architecture is funded. Do not fake RTL.
- **Priority:** **P2 (Medium)**

---

## 7. DESIGN SYSTEM DECISIONS
- **Typography:** 3 distinct roles enforced. Display (Space Grotesk), Mono (IBM Plex Mono for commands/data), Arabic (Cairo). Minimum readable size: 11px (Interface), 10px (Mono metadata).
- **Color:** One canonical semantic token layer. Status must *never* rely on color alone (e.g., Error = Red + "SYNTAX ERROR" text + Icon).
- **Surfaces:** 3 tiers. `--surface-terminal` (Deepest, highest contrast), `--surface-elevated` (Cards/Panels), `--surface-base` (App background).
- **Motion:** Global `prefers-reduced-motion` catch-all is **KEEP**. Add missing overrides for the Terminal caret blink and smooth-scrolling.
- **Radius:** Consolidate to 3 tokens: `--radius-sm` (8px), `--radius` (12px), `--radius-lg` (16px). Eliminate hardcoded magic numbers (9px, 11px, 14px).

---

## 8. GLOBAL UX DECISIONS
- **Navigation:** Desktop Sidebar and Mobile Bottom Rail are **KEEP**. The central emphasis on "Train" (Practice) in the mobile rail is a strong product decision and must be preserved.
- **Information Hierarchy:** Workstation → Evidence → Next Action → Context. KPI cards must not visually overpower the Terminal or the primary CTA.
- **Feedback Budget:** Eliminate per-command Toast notifications. Terminal history and Coach panel are the sole owners of command feedback. Toasts are reserved for session-level events (e.g., "Assessment Saved").

---

## 9. TERMINAL / WORKSTATION DECISIONS
*The Terminal is the Primary Work Environment. It is not a card.*
1. **Input Contract:** Empty submit = Inline validation error. No silent execution.
2. **History:** Auto-scroll to latest entry on submit. Add visible `↑/↓` affordance when history exists.
3. **Focus Mode:** **KEEP**. Must implement a proper Focus Trap (keyboard cycling) and `Escape` to exit.
4. **Coach Panel:** Desktop = Subordinate sticky rail. Mobile = Collapsible bottom sheet or FAB. Must never compete with the command input.
5. **Reference:** Opening Reference in Learn/Practice counts as a hint *only if* the engine defines it. UI must transparently state "Hint recorded" when opened.

---

## 10. LEARNING UX DECISIONS
- **Assessment Integrity:** Switching modes (Learn → Practice → Assessment) must clearly state what is preserved and what is reset. (UI mitigation: Display "Entering Assessment with X hints carried over" if state is shared).
- **Evidence Interpretation:** Growth Record focuses on *patterns* ("What recurs?"), not vanity metrics.
- **Curriculum Traceability:** UI must reserve metadata slots for `Course → Module → Skill`. Actual mapping is **Content Dependent**.

---

## 11. RESPONSIVE DECISIONS
- **Desktop (≥1100px):** Persistent Sidebar. Terminal and Coach in 2-column grid.
- **Tablet (740px–1099px):** **VALIDATION REQUIRED**. Currently mixes multi-column content with mobile bottom-nav. Needs a dedicated navigation identity or acceptance of the hybrid state.
- **Mobile (≤739px):** Bottom Rail. Terminal input `sticky` with `16px` font (iOS zoom prevention).
- **Narrow Mobile (360px/320px):** The 360px CSS grid restructure for the Terminal header is **KEEP**. Must be explicitly validated and extended down to the 320px hard floor.

---

## 12. ACCESSIBILITY DECISIONS
- **Landmarks:** Wrap routed content in `<main id="main-content">`. Add a visually hidden "Skip to Main" link.
- **Focus Management:** Route changes must move focus to the page `<h1>`. Drawers (Reference, Mobile Menu) must trap focus and close on `Escape`.
- **Chart Alternatives:** The `<details><summary>View data table</summary>` pattern in Progress Tracking is **World-Class**. **KEEP** and use as the template for any future data viz.

---

## 13. SCREEN-BY-SCREEN AUDIT

| Screen | Critical Problems | Required Changes | Do Not Touch |
| :--- | :--- | :--- | :--- |
| **Progression** | "3/8 stages" math mismatch. Track toggle doesn't change content. | Derive counts from `.length`. Add "Coming Soon" to Service track. | Hero Route card, Resume CTA, Stage Map visual. |
| **Practice** | Fake Coach error, FQD fallback, Toast noise. | Fix AB-F001, AB-F002, AB-F008. Remove per-command toasts. | Command matching logic, Focus Mode, Local Sim disclaimer. |
| **Scenarios** | "23/40" fake stats. Sort/Filters are dead-ends. | Wire counts to array. Remove or wire Sort/Filter controls. | Mission File detail panel, Start/Resume/Review logic. |
| **Growth** | "Backup" lies. Trend arrows map to direction, not favorability. | Relabel Backup. Fix `skill-trend` color logic. | Record/History/Reports tabs, Learning Loop strip. |
| **Tracking** | KPI decorative clip-paths add noise. | Simplify KPI backgrounds. Keep Data Table. | Metric switcher, Route Line, Trend Readout. |

---

## 14. KEEP / PRESERVE (The Strongest Assets)
1. **Flight Deck Identity:** Deep navy, Vector Blue accents, monospace readouts.
2. **The Evidence Loop:** `setPracticeContext` handoffs between screens.
3. **Terminal Mobile Engineering:** `16px` input, `sticky` positioning, safe-area insets.
4. **Reduced Motion:** Global and component-level `prefers-reduced-motion` overrides.
5. **Honest Disclaimers:** "LOCAL TRAINING SIMULATION" and "ILLUSTRATIVE" labels.
6. **Data Table Fallback:** Accessible chart alternative.

---

## 15. DO NOT DO (Anti-Patterns & Constraints)
- **DO NOT** redesign the visual identity or turn it into a generic SaaS dashboard.
- **DO NOT** add command autocomplete (violates recall-based pedagogy).
- **DO NOT** invent new Amadeus commands or scoring logic in the UI layer.
- **DO NOT** add gamification (streaks, badges, confetti) that undermines professional maturity.
- **DO NOT** fake Arabic/RTL translation.
- **DO NOT** allow decorative elements (route motifs, KPI guilloché) to compete with operational data.

---

## 16. CONFLICTS RESOLVED

| Conflict | Competing Views | Resolution & Final Decision |
| :--- | :--- | :--- |
| **Token Drift** | Delete `.page-practice` `--ab-*` tokens vs. Keep them. | **Merge Up.** The `--ab-*` tokens represent a more mature, semantic refinement. They should replace the base tokens globally. |
| **Growth vs. Tracking** | Merge into one "Analytics" screen vs. Keep separate. | **Keep Separate.** Tracking is longitudinal signal (Trend). Growth is immediate pedagogical interpretation (Next Action). Merging dilutes the learning loop. |
| **Empty States** | Invent fake data to fill screens vs. Show empty states. | **Show Empty States.** The UI must honestly reflect the `localStorage` reality. If a user clears data, the UI must gracefully show "No evidence yet" with a CTA to Practice. |
| **Focus Mode Coach** | Hide Coach completely vs. Keep a peek affordance. | **Hide Completely (Conditional).** In "Deliberate Practice/Assessment", removing support is pedagogically valid. Keep as-is, but ensure keyboard trap exists. |

---

## 17. NEW INSIGHTS / AUDIT GAPS
- **New Insight (The "Echo" Cursor):** The Terminal body renders an "active line" (`> _`) that mirrors the actual `<input>` field below it. While authentic to retro terminals, on mobile this creates two competing cursors. **Recommendation:** Validate first-use clarity; ensure the real `<input>` is unmistakably the primary focus target.
- **Audit Gap (Tablet Navigation):** The 740px–1099px range lacks a verified navigation identity. It inherits mobile chrome but desktop content density. Requires manual device QA.
- **Audit Gap (Error Boundary):** `ErrorBoundary.tsx` exists but is unmounted in `App.tsx`. A crash will result in a white screen, breaking the Flight Deck identity. Must be mounted and styled to match the console.

---

## 18. FINAL PRIORITY MATRIX

| ID | Issue / Decision | Evidence | Consensus | Impact | Dependency | Priority | Verdict |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **AB-F001** | Empty Submit FQD Fallback | Source | Unanimous | Trust/Safety | UI/Engine | **P0** | **Fix** |
| **AB-F002** | Fake Coach Error | Source+Visual | Unanimous | Trust | UI | **P0** | **Fix** |
| **AB-F003** | Unloaded Fonts | Source | High | Identity | UI | **P0** | **Fix** |
| **AB-F004** | Pinch-Zoom Disabled | Source | Unanimous | A11y | UI | **P0** | **Fix** |
| **AB-F005** | Primary Button Contrast | Computed | High | A11y | UI | **P1** | **Fix** |
| **AB-F006** | Misleading Metrics/Toasts | Source | High | Trust | UI/Data | **P1** | **Fix** |
| **AB-F007** | Missing ARIA Tabs | Source | High | A11y | UI | **P1** | **Fix** |
| **AB-F008** | Terminal State Language | Source | Medium | UX | UI | **P1** | **Fix** |
| **AB-F009** | Mobile Session Readout | Source | High | Mobile UX | UI | **P1** | **Fix** |
| **AB-F010** | Token Consolidation | Source | High | System | UI | **P2** | **Fix** |
| **AB-F011** | EN/AR Toggle Reality | Source | Unanimous | Mission | Content | **P2** | **Defer/Label** |
| **AB-F012** | Hint/History Mode Bleed | Source | Medium | Integrity | State/Data | **P2** | **Mitigate** |

---

## 19. IMPLEMENTATION SEQUENCE

### Phase A: Foundations & Safety (P0)
*Goal: Remove trust defects and establish baseline accessibility. Zero engine logic changes.*
1. Restore Font Loading (`index.html`).
2. Remove Viewport Zoom Restriction (`index.html`).
3. Fix Empty Command Fallback (`Home.tsx`).
4. Fix Coach First-Run State (`Home.tsx`).
5. Fix Primary Button Contrast (`index.css`).

### Phase B: Terminal & Core Workstation (P1)
*Goal: Perfect the primary workstation across all viewports.*
1. Implement ARIA Tab/Switcher semantics globally.
2. Redesign Mobile Terminal Header (Restore Session Readout).
3. Complete Terminal State Language (Processing, Interrupted, Empty).
4. Eliminate per-command Toast noise.
5. Mount and style `ErrorBoundary`.

### Phase C: Evidence Honesty & Shared System (P2)
*Goal: Align UI claims with data reality and consolidate the design system.*
1. Derive all metrics from actual array lengths (Fix "23/40", "3/8").
2. Relabel/Remove dead-end controls (Backup, View Map, Sort).
3. Consolidate `--ab-*` tokens into global `:root`.
4. Label EN/AR toggle as "Roadmap" or disable.
5. Implement Focus Traps for Drawers/Modals.

### Phase D: Polish & Content (P3)
*Goal: Refinement and curriculum integration.*
1. Tablet navigation QA and refinement.
2. Decorative KPI noise reduction.
3. Integration of real EgyptAir Basic/Advanced curriculum metadata (Content Dependent).

---

## 20. VALIDATION PLAN

| What to Test | Where / Device | Expected Behavior | Failure Condition |
| :--- | :--- | :--- | :--- |
| **Empty Submit** | Terminal Input (All Viewports) | Inline error appears. No history logged. No toast. | `FQD` executes or history increments. |
| **Font Loading** | Browser DevTools (Computed) | Headings = Space Grotesk, Terminal = IBM Plex Mono. | Fallback to `system-ui` or `sans-serif`. |
| **Zoom A11y** | Mobile Device (iOS/Android) | Pinch-to-zoom expands UI up to 400%. | Viewport locks at 100%. |
| **Screen Reader** | NVDA / VoiceOver | Tab switches announce "Selected". Terminal history announces new entries politely. | Reads "Button" instead of "Tab". |
| **Keyboard Trap** | Focus Mode / Reference Drawer | `Tab` cycles inside. `Escape` closes and restores focus. | Focus escapes to browser chrome. |
| **Evidence Truth** | LocalStorage Cleared | UI shows "No evidence" empty states. No hardcoded "86%" or "23/40". | UI displays fake numbers from hardcoded literals. |
| **Regression** | Assessment Flow | AN → SS → FQD → FXP yields identical score to pre-audit build. | Scoring weights or sequence logic altered. |

***
**END OF UNIFIED MASTER AUDIT.** 
*This document is now the binding contract for all UI/UX engineering on the AeroBridge prototype.*