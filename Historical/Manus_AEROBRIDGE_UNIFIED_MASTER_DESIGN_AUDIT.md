# AEROBRIDGE — UNIFIED MASTER DESIGN AUDIT

**Prepared by:** Manus AI  
**Scope:** Evidence-weighted design, UX, interaction, accessibility, responsive, learning-UX, and design-system audit. This document is an implementation-ready specification; it does not modify or redesign the supplied prototype.

> **DESIGN STATUS: NEEDS TARGETED REVISION**
>
> AeroBridge has the right product identity and a credible end-to-end learning loop. It does not need a visual redesign or architecture reset. It does require a controlled hardening pass before it can be treated as a trustworthy reference for a real aviation-training engine, because the current prototype combines strong local evidence flows with illustrative values, incomplete state coverage, and several actions that look authoritative without performing the promised operation.

---

## 1. EXECUTIVE VERDICT

AeroBridge is already recognizably a **Professional Aviation Training Workstation + Modern Learning Environment**, not a generic SaaS dashboard. The deep-navy Flight Deck Console language, Vector Blue route accents, green/amber/red operational semantics, monospace command readouts, terminal-first Practice surface, desktop side rail, compact mobile rail, and explicit `Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action` loop are the product’s strongest assets. The Terminal contains the correct ingredients for a serious workstation: Learn/Practice/Assessment modes, command entry, history navigation, coach guidance, reference support, focus mode, assessment debrief, and local persistence of records. These strengths are directly visible in the supplied renders and supported by `Home.tsx` and `index.css` [1] [2] [3].

The central weakness is not taste or surface polish. It is **operational truthfulness**. A blank command is transformed into `FQD`; the first-use Coach can present an error-like state before a command exists; hard-coded metrics coexist with locally persisted records; several counters do not reconcile with the arrays they appear to summarize; and controls such as Search, Backup, View map, Filters, Sort, and some section actions either toast or imply work that does not happen. In an aviation-training context, these are **trust, safety, and evidence-integrity defects**, not ordinary prototype roughness.

The second weakness is incomplete state and interaction semantics. The source declares a broad state taxonomy, but the rendered system does not provide a consistent contract for first-use, empty, loading, processing, interrupted, retry, partial success, completion, review, locked, and unavailable states across routes. The Terminal is visually primary, yet mode intent, session status, command status, next move, and feedback are distributed across too many places. The mobile layout is intentionally designed, but exact 320/360/390/430 keyboard behavior and long-session readability remain validation requirements.

The third weakness is accessibility and mixed-language readiness. Some foundations are genuinely strong: visible focus rules, live-region intent, reduced-motion support, `aria-current` navigation, labelled rings, and an accessible data-table fallback. However, progress bars use decorative `<i>` elements rather than progress semantics; transient drawers/popovers lack a complete focus/escape contract; small muted labels are difficult to read; tab/filter semantics are incomplete; and the EN/AR control is cosmetic in the supplied implementation. The Arabic requirement must not be “simulated” by changing a highlight. Either implement a real, bounded RTL/i18n contract or state honestly that Arabic is not active in this preview.

### What must change first

| Order | Decision | Why it matters |
|---|---|---|
| P0 | Stop blank submissions from creating `FQD` events and remove the first-use fabricated error presentation. | Protects evidence integrity and first-use trust in the core workstation. |
| P0 | Give every displayed metric an explicit provenance: illustrative, local, calculated, historical, or authoritative. Reconcile counts with actual arrays. | Prevents contradictory learner truth. |
| P1 | Define and implement the Terminal state/mode contract, including processing, invalid, recoverable error, interrupted, completed, and assessment closure. | Makes the workstation learnable and operationally credible. |
| P1 | Establish the shared accessibility/state foundation: progress semantics, tabs, focus management, non-colour state cues, contrast, landmarks, and reduced motion. | Raises the entire product rather than patching five screens independently. |
| P1 | Harden mobile Terminal hierarchy and keyboard behavior at explicit widths. | Mobile is a real workstation surface, not a compressed desktop. |
| P2 | Resolve or honestly downgrade every dead-end secondary affordance. | Keeps the evidence-first product promise intact. |

### What must not change

Do not remove the Flight Deck identity, turn the Terminal into a card, add dashboard metrics for their own sake, gamify readiness, replace operational language with generic SaaS copy, invent curriculum mappings, modify the command evaluator without evidence, or add backend architecture merely to make a preview look more complete. The correct direction is **calmer, clearer, more truthful, and more accessible without becoming less operational**.

---

## 2. SOURCE COVERAGE & EVIDENCE OVERVIEW

### Source inventory

| Source ID | Type | Artifact | What it verifies | Limits / coverage |
|---|---|---|---|---|
| S-01 | Specification | `aduitsprompt.md` | Required adjudication method, evidence hierarchy, canonical IDs, dispositions, output structure, validation rules, preservation and restraint principles. | Defines the audit; does not prove product behavior. |
| S-02 | Design ground truth | `ideas.md` | Identity, product boundary, intended loop, presentation-first constraint, prohibition on backend/auth/payment/real metrics. | Does not verify implementation. |
| S-03 | Source | `Home.tsx` | Route composition, seeded records, state taxonomy, terminal behavior, command scoring, persistence, navigation, action handlers, hard-coded values. | Static source; runtime/device behavior needs validation unless directly demonstrated elsewhere. |
| S-04 | Source | `index.css` | Tokens, typography declarations, responsive breakpoints, Terminal/mobile rules, focus and motion rules, bottom rail, duplicate token layer. | CSS declarations do not prove rendered font metrics or physical touch success. |
| S-05 | Source | `App.tsx` | Confirms `Home` is the mounted application shell. | No substantive UI behavior. |
| S-06 | Source | `const.ts` | Auth/login boundary only. | Outside current visual/UX scope. |
| S-07 | Source | `index.ts` | Static serving and SPA fallback/deep-link intent. | Does not prove deployed routing. |
| S-08 | Source | `Map.tsx` | Unused map integration/dead-code risk. | Not imported by current prototype; no basis for adding a map. |
| S-09–S-17 | Rendered evidence | `55514.jpg`, `55517.jpg`, `55519.jpg`, `55521.jpg`, `55523.jpg`, `55526.jpg`, `55528.jpg` | Visible mobile composition and states for Progression, Practice, Scenarios, Growth Record tabs, and Progress Tracking. | Exact viewport/device metrics, keyboard behavior, screen-reader behavior, desktop rendering, and hidden states are not fully verifiable. |
| S-18 | Analytical evidence | `chatgptaudit.md` | Broadest system/IA/accessibility/state coverage; identifies evidence-truth, font loading, state completeness, and action-integrity risks. | Some claims depend on an archive/runtime context not identical to this upload; source verification governs. |
| S-19 | Analytical evidence | `Claudeaudit.md` | Strongest detailed source/contrast/interaction findings, including critical blank-terminal error, cosmetic language toggle, button contrast, hard-coded counts, and terminal ergonomics. | Live behavior was not available to that audit; validation claims remain validation requirements. |
| S-20 | Analytical evidence | `deepseekaudit.md` | Strong Terminal, focus-mode, mobile coach, state-model, and learning-loop recommendations. | Some recommendations are target-state proposals rather than observed defects. |
| S-21 | Analytical evidence | `giminiaudit.md` | Mixed-language/bidi, ARIA progress semantics, keyboard/drawer concerns, and locked-state interaction insights. | CSS was not available in that audit, so visual/contrast claims are lower confidence. |
| S-22 | Analytical evidence | `grokaudit.md` | Density, next-action continuity, state semantics, terminal long-session comfort, and design-system token gaps. | Several desktop/mobile judgments require live validation. |
| S-23 | Analytical evidence | `kimi.md` | Mobile fragility, hard-coded accuracy/clock, dead-end utilities, service-track hollowness, and persistent next-action insight. | Some assertions conflict with the supplied CSS and are therefore conditional, not direct fact. |
| S-24 | Analytical evidence | `Manusaudit.md` | Strong source-traced finding register, evidence ownership, blank-command safety, coach competition, route contracts, and validated-runtime caveats. | Runtime observations are retained as audit evidence but are not independently re-run here. |
| S-25 | Analytical evidence | `qwenaudit.md` | Screenshot-grounded visual review, mobile Growth clipping risk, backup truth issue, dead MapView, and accessible chart fallback. | Stylesheet/runtime limitations reduce confidence in exact contrast/touch claims. |
| S-26 | Analytical evidence | `v0.devaudit.md` | Bottom-nav historical mismatch, small-type risk, state gaps, font/RTL risk, and route-by-route implementation notes. | Some findings are explicitly assumption-based where files were missing in that audit context. |

### Evidence model

The original source files and visible renders are treated as primary evidence for implementation and visual claims. The audits are analytical evidence, not truth. Repetition across audits is recorded as **consensus**, not as independent proof, because most audits inspected the same source and screenshots. Evidence independence uses E0–E4: E0 single claim, E1 repeated but non-independent claim, E2 corroborated analyses, E3 independently corroborated sources, E4 directly verified artifact/runtime.

The strongest evidence in this review is E4 for source-visible behaviors such as blank-command fallback, toast-only handlers, hard-coded seeded values, localStorage persistence, the declared state union, and the CSS token/responsive rules. Screenshot claims are E4 for what is visibly rendered in the supplied captures but not for hidden or interactive behavior. Claims about physical keyboards, actual screen readers, font loading in a deployed host, desktop composition, and exact touch targets are **TEST BEFORE ACCEPTING**.

---

## 3. AUDIT CONSENSUS OVERVIEW

### Strongest consensus, accepted after source verification

The audits converge on the following valid conclusions: the Flight Deck visual language is distinctive and should be preserved; the Terminal is the primary product territory; the main learning loop is conceptually and partially functionally coherent; context handoffs into Practice are valuable; Growth’s “Read evidence → Practice the gap → Apply in scenario” loop is unusually strong; reduced-motion and chart-table foundations are better than average; and the next revision should be targeted rather than a redesign.

### Conditional consensus

There is conditional consensus that the mobile Terminal needs hardening. The source contains sticky-input and narrow-width rules, so it is not correct to call the mobile approach fundamentally broken. The correct decision is: **accept the need for explicit validation and targeted refinement, not a wholesale replacement**. Likewise, the audits agree that typography and contrast require attention, but exact ratios and loaded-font behavior must be verified in the actual runtime. The EN/AR control is clearly incomplete; whether it should be implemented now or honestly disabled is a product-release decision, not a reason to invent partial translation.

### Important minority insights retained

The following single- or low-repetition insights survive because they are product-specific and well reasoned: service-track content currently changes description more than curriculum data; scenario context should carry an ID or trace, not only a title; opening Reference may affect hint accounting and therefore needs an explicit assessment contract; assessment mode should suppress or lock coaching rather than merely change copy; a true persistent last-debrief surface may be useful but is deferred because the ground truth prohibits unnecessary architecture; and the unused MapView should not be activated merely because “View map” exists.

### Strongest disagreements and resolution

| Dispute | Resolution |
|---|---|
| Whether the prototype is near production ready versus only a strong prototype | **Needs targeted revision.** Visual maturity is high, but P0 evidence/safety defects prevent a production-ready verdict. |
| Whether the mobile Terminal is broken | **Accept with modification.** Its architecture is directionally correct; device-specific keyboard and 320–430px behavior require hardening and testing. |
| Whether the font system is definitely missing | **Test before accepting as a runtime defect; accept the implementation risk.** CSS declares the families, but the supplied artifact set does not establish a reliable local font asset/loading contract. |
| Whether to add a real map | **Reject.** The unused `Map.tsx` does not prove that a map has instructional value; relabel or implement a stage-map surface only if the curriculum requires it. |
| Whether to add persistent global Next Action | **Accept with modification.** Strengthen contextual next-action visibility within each screen first; defer a global widget to avoid dashboardization. |
| Whether to hide Coach entirely in Assessment | **Accept with modification.** Suppress shortcut content and show a calm “Assessment active / hints unavailable” state; preserve session orientation and access to required status. |
| Whether the 5-item bottom rail is a 4-column bug | **Reject as current fact.** The supplied `index.css` contains a later five-column rule. Keep the historical risk in regression validation, not as a present defect. |

---

## 4. CRITICAL DECISIONS

1. **Evidence truth is a first-class design requirement.** Every metric, status, action confirmation, and assessment result must declare whether it is illustrative, local, calculated, historical, or authoritative. The UI may interpret engine state; it must never invent engine truth.
2. **The Terminal remains the unquestioned center of gravity.** Supporting surfaces must be subordinate to command entry, output, recovery, and assessment closure.
3. **Blank input is not a command.** It must produce no history entry, no score change, no toast success, and no evidence record.
4. **Secondary affordances must be load-bearing or honest.** Implement them, make them visibly preview/unavailable, or remove them. A toast is not a substitute for an action that appears to navigate, save, filter, sort, or change language.
5. **Arabic is a release contract, not a cosmetic toggle.** If AR is not implemented in this preview, the control must state that honestly. If it is implemented, it requires document direction, translation coverage, font verification, bidi isolation, and mixed-content testing.
6. **State semantics are systemic.** Build one state matrix and shared primitives rather than repairing each screen independently.
7. **No engine or architecture rewrite is justified by the supplied evidence.** UI-only and interaction changes should preserve the command sequence, scoring formula, localStorage shape, and context handoffs until an engine requirement is established.

---

## 5. CANONICAL FINDINGS

### AB-F001 — Blank submission creates a false command event

| Field | Decision |
|---|---|
| Type | Behavioral / Safety-critical |
| Source audits | S-18, S-19, S-21, S-23, S-24, S-26 |
| Source artifacts | `Home.tsx` Practice submit logic; supplied Practice render S-10 |
| Evidence type | Direct source; screenshot corroboration of Terminal context |
| Independence | E4 direct artifact; E2 analytical corroboration |
| Consensus | C5 / strongest consensus |
| Evidence quality | Very Strong |
| Observation | The submit path converts trimmed empty input to `FQD` before evaluation. |
| Impact | A trainee can create a command, response, score change, and potentially evidence event without entering a command. |
| Risk | Evidence corruption, false learning feedback, later engine incompatibility, loss of workstation trust. |
| Dependency | UI + Interaction; engine boundary must remain unchanged unless required by the existing function contract. |
| Priority | P0 |
| Final verdict | ACCEPT |
| Decision | Empty input is validation failure, not command input. |
| Action | Return an inline `ENTER A COMMAND` state; keep history, scores, hints, and persistence unchanged; do not toast-success or submit. Preserve existing valid command matching. |
| Validation | Submit blank and whitespace-only values in Learn, Practice, and Assessment; confirm no history row, score delta, hint delta, localStorage write, or completion change. |

### AB-F002 — First-use Terminal presents an apparent error before user action

| Field | Decision |
|---|---|
| Type | Behavioral / Visual / Trust |
| Source audits | S-18, S-19, S-20, S-22, S-24, S-25 |
| Source artifacts | `Home.tsx` coach-state logic and Practice render S-10 |
| Evidence type | Direct source and screenshot-visible first-use state |
| Independence | E4 |
| Consensus | C5 |
| Evidence quality | Very Strong |
| Observation | The empty-session Coach can display red error-like copy while the terminal itself is awaiting a command. |
| Impact | New trainees may infer that they already failed or that the simulator is malfunctioning. |
| Risk | First-use anxiety, false evidence impression, reduced learning confidence. |
| Dependency | UI-only / Interaction |
| Priority | P0 |
| Final verdict | ACCEPT |
| Decision | First-use must be neutral and action-oriented. |
| Action | Replace pre-command error styling with `READY · AWAITING COMMAND`, a concise instruction, and an optional reference invitation. Error styling appears only after an actual invalid response. |
| Validation | Fresh local session with no history; expected neutral state. Enter invalid command; expected error state only after submission. |

### AB-F003 — Illustrative and local evidence are not visibly separated or reconciled

| Field | Decision |
|---|---|
| Type | Systemic / Content / Data-trust |
| Source audits | S-18–S-26, especially S-19, S-23, S-24, S-25 |
| Source artifacts | `Home.tsx` seed records, Progression/Scenarios/Growth/Tracking values; S-09, S-11, S-12, S-13, S-14 |
| Evidence type | Direct source plus screenshot verification |
| Independence | E4; E3 across source and renders |
| Consensus | C5 |
| Evidence quality | Very Strong |
| Observation | Seeded/local records coexist with hard-coded headline counts and values. Examples include seed records versus Scenario `23 / 40`, Progression `3 / 8` against six defined levels, and Growth history readout counts that do not necessarily match rendered rows. |
| Impact | Users cannot tell what is calculated from their session, what is sample content, and what is authoritative. |
| Risk | Contradictory learner truth and unsafe future integration. |
| Dependency | UI + Data/Content; production ownership is engine/data dependent. |
| Priority | P0 |
| Final verdict | ACCEPT |
| Decision | Adopt a provenance contract before adding more metrics. |
| Action | Label each value as `ILLUSTRATIVE`, `LOCAL EVIDENCE`, `CALCULATED`, `HISTORICAL`, or `AUTHORITATIVE`; derive counts from their actual arrays where appropriate; remove or relabel values that have no owner; add a local-preview banner outside Practice if the same distinction is not obvious. |
| Validation | Compare every displayed count with its source array and persisted records; empty, one-record, and multi-record states must reconcile without copy changes. |

### AB-F004 — Secondary controls imply actions that do not occur

| Field | Decision |
|---|---|
| Type | Behavioral / IA |
| Source audits | S-18, S-19, S-20, S-22–S-26 |
| Source artifacts | `Home.tsx` handlers for Search, My route, View map, See all stages, Filters, Sort, Backup, View history/evidence/patterns |
| Evidence type | Direct source |
| Independence | E4 |
| Consensus | C5 |
| Evidence quality | Very Strong |
| Observation | Multiple visually actionable controls resolve to generic toast messages or static popovers rather than the implied surface/action. |
| Impact | Working primary CTAs become indistinguishable from non-working affordances. |
| Risk | False success, interaction fatigue, loss of professional credibility. |
| Dependency | UI + Interaction; some features are Content/Data dependent. |
| Priority | P1 |
| Final verdict | ACCEPT WITH MODIFICATION |
| Decision | Every secondary control must be load-bearing or explicitly preview/unavailable. |
| Action | Remove duplicate Filters if filter tabs are the real control; make View map scroll to a real stage section or relabel it; make Backup say `Preview only — no file written` or remove it; mark Search/Sort unavailable until functional; connect evidence/history actions to real destinations. |
| Validation | Create an interaction inventory and verify that every button either changes route/state, opens a real surface, or has visibly honest unavailable/preview copy. |

### AB-F005 — Terminal mode and session-state contract is implicit and fragmented

| Field | Decision |
|---|---|
| Type | Structural / Systemic |
| Source audits | S-18–S-26 |
| Source artifacts | `Home.tsx` Practice mode/state logic; S-10 |
| Evidence type | Direct source and rendered evidence |
| Independence | E3 |
| Consensus | C5 |
| Evidence quality | Strong |
| Observation | Mode, context, session state, command state, coach state, hints, and next move are distributed across header, body, coach, footnote, and footer. Mode changes retain history without a clear user-facing contract. |
| Impact | Learners cannot quickly answer what mode they are in, what counts, what is recorded, and what to do next. |
| Risk | Cognitive load and invalid assessment interpretation. |
| Dependency | UI + Interaction; assessment semantics partly Engine/Data dependent. |
| Priority | P1 |
| Final verdict | ACCEPT |
| Decision | Establish a single dominant session summary: identity → workflow state → command state → next move. |
| Action | Add explicit mode descriptions and preserve/reset rules; expose `READY`, `PROCESSING`, `SUCCESS`, `INVALID`, `REVIEW`, `ASSESSMENT ACTIVE`, and `COMPLETED` in a consistent location; keep the Terminal hierarchy intact. |
| Validation | Switch modes before and after commands; verify history, hints, score, and completion behavior match the written contract. |

### AB-F006 — Terminal lacks a complete recoverable state system

| Field | Decision |
|---|---|
| Type | Systemic / Behavioral |
| Source audits | S-18–S-26 |
| Source artifacts | `SystemState` union in `Home.tsx`; `StateNotice`; Practice rendering; `index.css` state styles |
| Evidence type | Direct source |
| Independence | E4 |
| Consensus | C4 |
| Evidence quality | Strong |
| Observation | The type union includes many states, but the UI does not consistently render first-use, empty, loading/processing, partial success, retry, interrupted, unavailable, and assessment-ready states. |
| Impact | The workstation cannot explain what is happening or how to recover. |
| Risk | Dead ends, ambiguous evidence, accessibility announcement failures. |
| Dependency | UI + Interaction; some processing semantics Engine dependent. |
| Priority | P1 |
| Final verdict | ACCEPT |
| Decision | Define a route-wide state matrix and implement the subset needed by the preview without inventing engine behavior. |
| Action | For every state specify visual marker, text, role, recovery action, and whether it changes score/evidence. Use shared `StateNotice`/status primitives. |
| Validation | Exercise each state with deterministic mock triggers; confirm recovery and screen-reader announcement expectations. |

### AB-F007 — Mobile Terminal needs targeted keyboard, density, and feedback hardening

| Field | Decision |
|---|---|
| Type | Responsive / Workstation |
| Source audits | S-18–S-26 |
| Source artifacts | `index.css` mobile rules; Practice render S-10; all narrow renders |
| Evidence type | CSS/source plus screenshots; device behavior unverified |
| Independence | E3 |
| Consensus | Conditional consensus |
| Evidence quality | Strong for layout intent; Moderate for actual device behavior |
| Observation | Sticky input and 16px input sizing are good foundations, but narrow header/readout density, coach distance, terminal empty-space behavior, and native keyboard overlap require device checks. |
| Impact | A mobile trainee may lose session orientation or the active prompt while the keyboard is open. |
| Risk | Failed command entry, hidden feedback, long-session fatigue. |
| Dependency | UI + Interaction |
| Priority | P1 |
| Final verdict | TEST BEFORE ACCEPTING |
| Decision | Keep the sticky-input architecture unless device tests disprove it; refine hierarchy rather than replace it with JavaScript scrolling. |
| Action | Preserve input above safe-area inset; keep one-line session status visible at ≤390px; keep Coach subordinate/collapsed on mobile; remove unnecessary empty terminal height where it hides latest feedback; avoid `scrollIntoView` hacks if present in the active branch. |
| Validation | Android Chrome and iOS Safari at 320, 360, 390, and 430 CSS px with virtual keyboard open, long command, invalid command, and latest response; failure is any obscured input, jump, clipped action, or inaccessible latest result. |

### AB-F008 — Typography and contrast contract is not sufficiently dependable

| Field | Decision |
|---|---|
| Type | Systemic / Accessibility |
| Source audits | S-18–S-26 |
| Source artifacts | `index.css` font tokens and small-type rules; `index.html` availability must be checked; renders S-09–S-17 |
| Evidence type | Direct CSS; screenshot; runtime loading/contrast validation required |
| Independence | E3 |
| Consensus | C4 / conditional |
| Evidence quality | Strong for declared risk; Moderate for deployed result |
| Observation | Space Grotesk, Cairo, and IBM Plex Mono are declared as roles, but a complete reliable loading contract is not established in the supplied materials; many labels are 7–11px and muted tokens are intentionally low salience. |
| Impact | Long-session readability, Arabic rendering, command distinction, and WCAG conformance may fail. |
| Risk | Fatigue, missed states, inconsistent brand hierarchy, RTL clipping. |
| Dependency | UI + Content/Deployment |
| Priority | P1 |
| Final verdict | TEST BEFORE ACCEPTING |
| Decision | Verify first, then load/provision the intended fonts and raise instructional minimums without enlarging operational metadata indiscriminately. |
| Action | Use proportional display font for UI, mono only for commands/readouts, Arabic font for Arabic copy, tabular figures for metrics; establish minimum readable body/instruction sizes and contrast tokens. |
| Validation | Inspect computed fonts and contrast at runtime; test English, Arabic, mixed Arabic narrative plus LTR commands at 320–430px and desktop. |

### AB-F009 — EN/AR control is cosmetic without a real language contract

| Field | Decision |
|---|---|
| Type | Behavioral / Content / RTL |
| Source audits | S-18–S-26 |
| Source artifacts | `Home.tsx` `language` state and toast; `index.css` font declarations; shell renders |
| Evidence type | Direct source |
| Independence | E4 |
| Consensus | C5 |
| Evidence quality | Very Strong |
| Observation | The toggle changes local highlight/toast state but does not establish translation coverage, `lang`, `dir`, or bidi isolation. |
| Impact | The interface promises Arabic readiness without delivering it. |
| Risk | Overlapping mixed-direction content and product-market misrepresentation. |
| Dependency | Content + UI; mixed/architecture dependent for full i18n |
| Priority | P1 |
| Final verdict | ACCEPT WITH MODIFICATION |
| Decision | Choose one honest release contract: implement bounded RTL/i18n, or label Arabic as roadmap/unavailable rather than claiming it is active. |
| Action | If implemented, update document language/direction, use `unicode-bidi: isolate`/directional wrappers for commands and IDs, test mirrored layout and source content. If deferred, remove the false success toast and use explicit preview copy. |
| Validation | Toggle AR on every route; test headings, buttons, mixed commands, numbers, progress charts, drawer, Terminal, and focus order. |

### AB-F010 — Accessibility semantics are incomplete in shared primitives

| Field | Decision |
|---|---|
| Type | Systemic / Accessibility |
| Source audits | S-18–S-26 |
| Source artifacts | `Home.tsx` AnimatedBar, ProgressRing, chart details/table, tabs, drawers/popover; `index.css` focus rules |
| Evidence type | Direct source |
| Independence | E3 |
| Consensus | C4 |
| Evidence quality | Strong |
| Observation | AnimatedBar is an `<i>` with `aria-label` rather than a progressbar; custom tabs/filter controls lack complete tab/pressed semantics; popovers/drawers lack a demonstrated focus trap/escape/return contract; a main landmark/skip link is not established in the supplied shell. |
| Impact | Screen readers, keyboard users, and low-vision users may not understand progress, current view, or transient surfaces. |
| Risk | WCAG failure and inaccessible assessment feedback. |
| Dependency | UI-only |
| Priority | P1 |
| Final verdict | ACCEPT |
| Decision | Fix shared semantics once, then reuse them everywhere. |
| Action | Use `role="progressbar"` with min/max/now and accessible name; use native button/tab patterns with `aria-selected`/`aria-pressed` as appropriate; add `<main>`, skip link, dialog/drawer semantics, Escape dismissal, focus trap and return. Keep the chart table fallback. |
| Validation | Keyboard-only and NVDA/VoiceOver/TalkBack checks for navigation, tabs, charts, drawers, search, reference, and dynamic Terminal output. |

### AB-F011 — Non-colour status communication and state tokens need consolidation

| Field | Decision |
|---|---|
| Type | Systemic / Visual |
| Source audits | S-18–S-26 |
| Source artifacts | `index.css` semantic colors; Terminal history; AssessmentReport; scenario/status renders |
| Evidence type | Source plus screenshots |
| Independence | E3 |
| Consensus | C4 |
| Evidence quality | Good |
| Observation | Green/amber/red/blue semantics are coherent, but some micro-states depend primarily on colour and the CSS contains parallel base and `--ab-*` token layers. |
| Impact | State scanning becomes fragile and maintenance drift grows. |
| Risk | Colour-blind ambiguity, inconsistent future screens, token divergence. |
| Dependency | UI-only |
| Priority | P2 |
| Final verdict | ACCEPT |
| Decision | Consolidate semantic state tokens and pair colour with text/icon/shape. |
| Action | Define success/warning/error/info/disabled/focus background, border, text, icon, and announcement tokens; add explicit state labels to history and cards; remove duplicate semantic values where safe. |
| Validation | Token inventory and contrast test; inspect every state without colour perception. |

### AB-F012 — Route and navigation orientation needs a coherent contract

| Field | Decision |
|---|---|
| Type | Structural / IA |
| Source audits | S-18, S-19, S-20, S-22–S-26 |
| Source artifacts | `Home.tsx` routing, SideNav, BottomNav, mobile drawer; `index.ts` fallback |
| Evidence type | Direct source; screenshots |
| Independence | E3 |
| Consensus | C4 |
| Evidence quality | Strong |
| Observation | Manual `pushState`/`popstate` routing works directionally; desktop labels and mobile short labels intentionally differ; route numbers and mobile ordering can make “Route 02/03” context less obvious. Focus restoration and drawer semantics are not complete. |
| Impact | Users may lose location or return from a secondary surface without context. |
| Risk | Navigation error, accessibility friction, fragile future route integration. |
| Dependency | UI + Interaction; architecture only if future engine requires it |
| Priority | P2 |
| Final verdict | ACCEPT WITH MODIFICATION |
| Decision | Keep the five-area model and centered Train rail; document it as intentional and strengthen orientation. |
| Action | Add `<main>` and skip link, route-change heading focus, `aria-current`, drawer backdrop/escape/return focus, and a concise persistent route/workflow context. Do not replace routing architecture without evidence. |
| Validation | Deep-link each path, browser back/forward, drawer open/close, keyboard route switching, and mobile rail order. |

### AB-F013 — Growth, Tracking, and Scenario evidence interpretation is strong but needs provenance and closure

| Field | Decision |
|---|---|
| Type | Learning / IA / Content |
| Source audits | S-18–S-26 |
| Source artifacts | Growth/Tracking/Scenarios components and renders S-09, S-11–S-14 |
| Evidence type | Direct source plus screenshots |
| Independence | E3 |
| Consensus | C4 |
| Evidence quality | Strong |
| Observation | “Practice the gap,” “Move the signal forward,” history handoffs, and scenario context are valuable; however, reports, counts, and recommendations are not uniformly tied to a declared record or curriculum provenance. |
| Impact | The learning loop is understandable but can feel like a dashboard interpretation rather than evidence-based coaching. |
| Risk | Learner follows a recommendation whose basis is unclear. |
| Dependency | UI + Data/Content |
| Priority | P1 |
| Final verdict | ACCEPT WITH MODIFICATION |
| Decision | Keep the learning loop and make the evidence-to-action link explicit. |
| Action | For each recommendation show source evidence, period, interpretation, and next behavior; carry scenario ID/context into Practice; surface completed scenario evidence without inventing curriculum or Saudi-readiness calculations. |
| Validation | Complete assessment, inspect Growth and Tracking, launch targeted practice, start/resume scenario, and verify context/provenance continuity. |

### AB-F014 — Service track and curriculum provenance are incomplete

| Field | Decision |
|---|---|
| Type | Content / Structural |
| Source audits | S-18, S-19, S-20, S-23, S-26 |
| Source artifacts | `levels` array and Progression track switch in `Home.tsx`; S-14 |
| Evidence type | Direct source and screenshot |
| Independence | E3 |
| Consensus | C3 |
| Evidence quality | Strong |
| Observation | Technical and Customer Service descriptions differ, while milestone data is primarily technical; explicit Basic/Advanced/module provenance is not present. |
| Impact | The learner may believe both tracks have equivalent curriculum depth when they do not. |
| Risk | Curriculum misrepresentation. |
| Dependency | Content/Data dependent |
| Priority | P2 |
| Final verdict | ACCEPT WITH MODIFICATION |
| Decision | Do not invent curriculum. Show an honest preparation/empty state for unavailable service-track content and add provenance only when supplied by Content. |
| Action | Add a content-owned mapping slot such as course/module/lesson/competency; do not hard-code EgyptAir/Saudi relevance beyond the supplied ground truth. |
| Validation | Switch tracks with and without content fixtures; confirm no technical milestones appear under an unavailable service track. |

### AB-F015 — Growth tabs and hover-only coaching need mobile/assistive parity

| Field | Decision |
|---|---|
| Type | Responsive / Accessibility / Interaction |
| Source audits | S-18, S-20, S-22–S-26 |
| Source artifacts | Growth tab panels, skill rows, hover preview CSS; S-11, S-12, S-13 |
| Evidence type | Direct source and screenshots |
| Independence | E3 |
| Consensus | C3 |
| Evidence quality | Good |
| Observation | Secondary panels are hidden through CSS and skill coaching can be hover-only; mobile renders show long vertical content where the next action is still present but secondary detail is dense. |
| Impact | Touch and keyboard users may miss coaching or lose context while changing tabs. |
| Risk | Unequal learning support and excess scroll. |
| Dependency | UI-only |
| Priority | P2 |
| Final verdict | ACCEPT |
| Decision | Every insight must have a click/focus/touch path; tabs should use real panel semantics. |
| Action | Move essential hover content into selected skill detail; retain hover as enhancement only; make tabs announce selection and preserve a contextual heading. |
| Validation | Touch, keyboard, and screen-reader interaction across all Growth tabs at 320–430px. |

### AB-F016 — Motion and long-session comfort require a final hardening pass

| Field | Decision |
|---|---|
| Type | Systemic / Accessibility |
| Source audits | S-18, S-20, S-22–S-26 |
| Source artifacts | `useAnimatedNumber`, CSS motion/reduced-motion blocks, Terminal caret, smooth scrolling |
| Evidence type | Direct source; runtime validation needed |
| Independence | E3 |
| Consensus | C3 |
| Evidence quality | Good |
| Observation | Reduced-motion support is a genuine strength, but not every movement source is proven disabled; repeated number/bar/ring animations may add fatigue during repeated training. |
| Impact | Motion-sensitive users may experience avoidable movement; long sessions may feel decorative rather than operational. |
| Risk | Accessibility and workstation comfort degradation. |
| Dependency | UI-only |
| Priority | P2 |
| Final verdict | TEST BEFORE ACCEPTING |
| Decision | Keep purposeful feedback motion; remove or disable nonessential motion under reduced-motion and avoid adding new animated KPI decoration. |
| Action | Explicitly gate caret blink, smooth scroll, number animation, and panel transitions; respect the product’s restrained identity. |
| Validation | Compare normal and reduced-motion settings on all routes, including focus mode and command submission. |

### AB-F017 — Unused MapView must not become a speculative feature

| Field | Decision |
|---|---|
| Type | Structural / Scope |
| Source audits | S-18, S-22, S-25, S-26 |
| Source artifacts | `Map.tsx` not imported by `App.tsx`/`Home.tsx`; `View map` toast |
| Evidence type | Direct source |
| Independence | E4 |
| Consensus | C3 |
| Evidence quality | Very Strong |
| Observation | A map integration helper exists but is unused and depends on unrelated environment variables; the visible “View map” action does not open it. |
| Impact | Activating it would add infrastructure and visual complexity without proving learning value. |
| Risk | Architecture drift, external dependency, dashboardization. |
| Dependency | Architecture/Data dependent |
| Priority | P3 |
| Final verdict | REJECT |
| Decision | Do not activate the map for this revision. |
| Action | Make “View map” a real stage-map anchor or remove the action; retain `Map.tsx` only as dead-code cleanup candidate. |
| Validation | Confirm no route claims a map destination unless a content-approved instructional surface exists. |

---

## 6. DESIGN SYSTEM DECISIONS

| Domain | Decision → Why | Scope / Priority / Dependency | Validation |
|---|---|---|---|
| Typography | Keep Space Grotesk-style proportional UI, IBM Plex Mono for commands/readouts, Cairo for Arabic; increase instructional readability without enlarging all metadata. This protects identity and long-session comfort. | Global; P1; UI/Content/Deployment. | Computed fonts, line-height, 320–430px mixed-language render. |
| Color | Preserve navy/blue/cyan/green/amber/red palette. Add semantic state tokens and ensure primary button text contrast is measured rather than assumed. | Global; P1–P2; UI. | Automated contrast matrix for text, buttons, focus, status, muted labels. |
| Surfaces | Keep a restrained hierarchy: page background, panel, terminal, support panel, active/focus. Do not add more card layers. | Global; P2; UI. | Visual review for hierarchy and terminal dominance. |
| Borders | Use quiet, standard, strong, status, and focus borders; pair status colour with icon/text. | Global; P2; UI/A11y. | Colour-independent review. |
| Spacing | Consolidate to a small 4/8-based rhythm, retaining dense operational metadata only where useful. | Global; P2; UI. | Compare routes at desktop/mobile; no new vertical bloat. |
| Components | Standardize buttons, inputs, tabs, status notices, progress bars, drawers, dialogs, and evidence rows. | Global; P1; UI. | Component inventory and interaction parity. |
| States | State matrix must map `first-use`, `empty`, `ready`, `processing`, `success`, `partial`, `invalid`, `error`, `retry`, `interrupted`, `completed`, `review`, `locked`, `unavailable`, and assessment states to text, icon, role, recovery, and evidence impact. | Global/Terminal; P1; UI + Interaction. | Fixture-driven state walkthrough. |
| Motion | Preserve meaningful progress feedback and reduced-motion foundation; disable decorative and caret/smooth-scroll motion where required. | Global; P2; UI/A11y. | OS reduced-motion test. |
| Accessibility | Add main landmark, skip link, focus-visible, focus management, progressbar semantics, tab/dialog semantics, live-region discipline, and non-colour state cues. | Global; P1; UI-only. | Keyboard + screen reader test matrix. |
| Responsive | Design desktop, tablet, and mobile as separate workstation states, not one scaled composition. | Global; P1; UI. | 320/360/390/430, 768, 1024, 1280, 1440. |
| Arabic/RTL | Either implement true bounded RTL/i18n or label AR as unavailable/roadmap; isolate LTR commands, IDs, codes, and numbers. | Global; P1; Content/Architecture mixed. | AR route-by-route bidi test. |
| Data visualization | Keep chart plus native details/table fallback; make metric definitions and empty state explicit. | Tracking; P2; UI/Data. | Screen-reader table and no-record fixtures. |

---

## 7. GLOBAL UX DECISIONS

The five-route model should remain. Progression is orientation and resume; Practice is execution and feedback; Assessment is a mode with explicit closure; Growth interprets evidence; Tracking shows trend; Scenarios apply skills under pressure. The mobile bottom rail may keep Train centered because that is a valid workstation-priority choice, but the elevated styling must communicate focus, not reward or gamification.

CTA hierarchy should be one dominant operational action per screen. Progression: Resume. Practice: command entry/Execute, then Finish only when valid. Growth: Practice the gap. Tracking: Run another assessment or targeted practice. Scenarios: Start/Resume/Review. Secondary links must not look equivalent to those actions unless they work.

Feedback should be local to the event. Command results belong in Terminal history and Coach; global toasts are reserved for system-level confirmations that do not change evidence. Search, profile, sort, backup, and filters must either become real or be visibly preview/unavailable. “Created,” “updated,” “saved,” “language set,” and “completed” are reserved for operations that actually occurred.

Every route needs an orientation line that answers where the learner is, which workflow is active, what evidence is being shown, and what the next useful move is. Avoid adding a persistent global widget until contextual orientation is repaired; a global widget could compete with the Terminal.

---

## 8. TERMINAL / WORKSTATION DECISIONS

The Terminal is **PRIMARY WORK ENVIRONMENT**, not a dashboard card. Preserve its darker surface, mono language, session header, input, history, reference, Coach, and Focus Mode. Improve its hierarchy in this order: session identity → workflow/context → mode → command state → output → next move.

The command input must expose a true processing state and prevent duplicate submission while processing. Empty input must validate inline. History should distinguish command, response, coaching, success, invalid, and error with text/icon labels, not only borders or colour. When output grows, latest-entry visibility and a deliberate “jump to latest” control may be added only if it does not compete with the prompt.

Coach is subordinate support. On desktop it may remain adjacent, but the Terminal must visually dominate. On mobile it should be collapsed or placed after the latest Terminal response, with an explicit state when Assessment is active. Reference should open the same contextual surface from all entry points and must state whether opening it affects hint evidence; do not silently change scoring semantics.

Focus Mode should hide non-essential chrome, retain session identity and a clear exit, preserve keyboard reachability, support Escape where appropriate, restore focus on exit, and respect reduced motion. The assessment debrief must distinguish a local illustrative training record from an authoritative operational qualification.

---

## 9. LEARNING UX DECISIONS

Learn should teach workflow steps and allow guidance. Practice should allow repetition with contextual feedback. Assessment should test recall under a clearly stated hint policy. Feedback should identify what happened, why it matters, and the next operational behavior. Correction should be recoverable, not punitive. Repetition should be visible in history and next-action language.

The existing `Read evidence → Practice the gap → Apply in scenario` pattern should be retained as the central pedagogical loop. A skill gap recommendation must show its evidence basis, not only a score. A scenario must carry a stable context/ID into Practice where possible, and completed scenario results should link back to evidence without inventing a production-grade curriculum model.

Progression should answer “where am I and what do I do next?” before showing the full map. Keep current/mastered/ready/locked language, but state unlock rules inline rather than via toast alone. Service track should not display technical milestones as if they were service curriculum. Curriculum labels, Basic/Advanced mapping, and job-role relevance are Content-dependent and must not be invented.

---

## 10. RESPONSIVE DECISIONS

| Mode | Explicit rules |
|---|---|
| Desktop ≥1100px | Persistent sidebar; Terminal is the primary column; Coach is supportive and visually subordinate; secondary metrics remain below the main action; navigation and focus mode retain route/session context. |
| Tablet 740–1099px | Collapse to mobile/drawer navigation according to tested breakpoint; preserve Terminal width and input reachability; avoid forcing a desktop three-column density; keep scenario master/detail readable. |
| Mobile 430px and below | Five-item rail remains usable with safe-area padding; keep Train primary but not game-like; use one-line route/session orientation; no critical state may be hidden only because width is narrow. |
| 390px and below | Stack Terminal header intentionally; keep session state readable; collapse Coach by default; prevent text clipping; test all mode tabs and action buttons. |
| 360px and 320px | Test with native keyboard; input and Execute remain visible and reachable; no JS-induced layout jump; preserve latest response visibility; labels may be compact but instructional text must remain readable. |
| All widths | Charts have a text/table alternative; cards do not become equally weighted endless stacks; focus order follows learning order. |

---

## 11. ACCESSIBILITY DECISIONS

Use semantic landmarks (`header`, `nav`, `main`, `aside` where appropriate), a skip link, and route-change focus to the primary heading or status. Keep visible `:focus-visible` styling with adequate contrast. Use native buttons and inputs whenever possible.

Progress bars must expose role, current value, min, max, and accessible name. Rings should avoid double announcements by placing the accessible name on one semantic element. Tabs and filter controls must expose selected/pressed state. Dialogs, drawers, search, and Reference need labelled semantics, Escape dismissal, focus containment while open, and focus return to the trigger.

Terminal output should use a carefully scoped polite live region for new responses, while errors use assertive announcement only when urgency warrants it. Do not announce animated intermediate numbers. Every state must have a text/icon marker in addition to colour. Keep the chart table fallback available and keyboard reachable.

Arabic/LTR content must be isolated: commands, booking codes, IDs, and numeric readouts should render LTR inside Arabic narrative. Validate line-height, wrapping, focus order, button labels, and progress descriptions with a real Arabic fixture, not only the AR toggle.

---

## 12. SCREEN-BY-SCREEN AUDIT

| Screen | Current strengths | Critical problems | Required changes | Optional improvements | Responsive / A11y | Priority / Dependency | Do not touch |
|---|---|---|---|---|---|---|---|
| Shared shell | Strong brand lockup, topbar, desktop sidebar, five-item mobile rail, active navigation. | Cosmetic language toggle; dead search/profile; incomplete drawer/focus/landmark contract. | Add main/skip/focus management; honest utility states; preserve route context. | Functional quick-find later. | Test drawer, Escape, focus return, safe-area, 320–430px. | P1–P2 / UI + Content. | Brand identity, centered Train intent. |
| Progression | Hero route, current vector, progress ring, milestones, Resume CTA, track choice. | Counts can conflict with actual levels; My route/View map/See all stages are toast-like; service curriculum is incomplete. | Derive/relabel counts; inline locked rule; honest service empty state; stage provenance slot. | Real stage-map anchor if useful. | 320px compression; `aria-current`/expanded details; target ≥44px. | P1–P2 / UI + Content. | Hero, route motif, current/mastered/locked language. |
| Practice / Terminal | Strongest screen; modes, input, history, Coach, Reference, Focus Mode, local simulation disclaimer. | Blank→FQD; first-use apparent error; fragmented state; mobile keyboard/coach risks; ambiguous hints/assessment contract. | Fix blank input; state matrix; mode contract; subordinate Coach; accessible output; explicit assessment closure. | Visible history ↑/↓ cue; jump-to-latest after long output. | 320/360/390/430 native keyboard tests; screen reader live region; focus mode Escape/return. | P0–P1 / UI + Interaction + mixed engine boundary. | Command evaluator, sequence, score formula, Terminal-first identity. |
| Scenarios | Mission cards, filters, detail, skills, difficulty/time, Start/Resume/Review language. | Filters/Sort mismatch; empty filtered state; provenance and scenario context weak. | Remove duplicate Filters or make real; empty state; context ID; recommendation basis. | Result link to evidence. | Keyboard selection should reveal/announce detail; filters semantic. | P1–P2 / UI + Data/Content. | Operational mission-card language. |
| Growth Record | Evidence banner, Record/History/Reports, learning-loop strip, strengths/needs, next action. | Backup overclaims persistence; hard-coded history/summary; hover-only coaching; long mobile scroll. | Honest Backup preview/removal; provenance; real tab semantics; move essential hover content into selected detail. | Persisted last debrief later, if required. | Touch/keyboard parity; no clipped KPI; preserve next action. | P1–P2 / UI + Data/Content. | Read → Practice → Apply loop. |
| Progress Tracking | Strong 78%/trend hierarchy in render, chart, data-table fallback, history, targeted CTA. | Metric definitions and provenance can be unclear; hard-coded/seed numbers may appear authoritative; chart semantics need refinement. | Label local evidence; define metrics; preserve table; ensure empty/insufficient evidence state. | Screen-reader trend summary. | Test chart at 320–430px; table keyboard access; no KPI clipping. | P1–P2 / UI + Data. | Evidence-over-time concept and targeted-practice CTA. |
| Assessment debrief | Clear score categories, recommendation, error taxonomy, local-training disclaimer. | Local report boundary and hint policy need stronger closure; partial/interrupted paths missing. | Add explicit local status, incomplete/retry/interrupted states, evidence provenance, next action. | Link to exact history entries. | Announce result once; keyboard order follows verdict → metrics → next move. | P1 / UI + Interaction + Data. | Existing scoring formula unless engine evidence requires change. |

---

## 13. KEEP / PRESERVE

Preserve the deep navy Flight Deck Console foundation, restrained atmospheric route imagery, Vector Blue accent, operational green/amber/red semantics, mono command/readout treatment, compact utility controls, asymmetric desktop composition, mobile command rail, centered Train priority, and contextual verbs such as Start, Resume, Review, Retry, and Practice.

Preserve the Terminal as the core workstation, Focus Mode, command history via Arrow Up/Down, Reference concept, Coach concept, local simulation disclosure, Assessment mode, debrief categories, reduced-motion foundation, visible focus intent, `aria-current` navigation, and chart data-table fallback.

Preserve the genuine context handoffs: Progression, Scenarios, Growth, and Tracking can converge on Practice with context; Assessment records can flow into Growth/Tracking through local persistence; Growth’s learning-loop strip and next-action language should remain central. Preserve the separation between a presentation-first preview and a future real engine.

---

## 14. DO NOT DO

Do not redesign for novelty, add decorative features without learning purpose, add metrics without a defined meaning and owner, invent engine semantics, invent curriculum or Saudi-readiness requirements, fake unavailable functionality, convert illustrative values into authoritative evidence, turn the Terminal into a dashboard card, over-gamify streak/readiness language, rely on colour alone, rewrite architecture without evidence, activate the unused map speculatively, add a global Next Action widget before contextual next actions are repaired, or change command matching/scoring merely to satisfy a visual preference.

Do not solve accessibility by destroying workstation density. Do not replace a valid sticky input with fragile JavaScript scrolling without a failing device test. Do not hide Assessment support in a way that removes necessary orientation. Do not remove the strong visual identity in pursuit of generic WCAG-looking surfaces.

---

## 15. CONFLICTS RESOLVED

| Conflict | Evidence and competing views | Resolution |
|---|---|---|
| Visual score ranged from roughly 7 to 9.2 | Renders and source consistently show a distinctive, coherent system; score differences reflect calibration, not different product truth. | Do not average scores. Qualitative verdict: visual foundation is strong; typography/runtime/accessibility keep it from production-ready. |
| “Fonts missing” versus “fonts declared” | CSS declares role tokens; source set does not establish a dependable loaded/local font contract. | Record as a verified implementation risk and runtime test, not an unconditional rendered-font fact. |
| Mobile Terminal “fragile” versus “well engineered” | CSS has sticky input, 16px mobile input, safe-area intent, and narrow breakpoints; physical keyboard behavior is unverified. | Conditional consensus: keep architecture, test and harden. |
| Coach should be removed versus preserved | Terminal support and learning guidance are valuable, but initial error and mobile competition are harmful. | Preserve Coach; subordinate/collapse it, neutralize first-use state, lock shortcuts in Assessment. |
| Add a persistent global Next Action versus avoid more chrome | Persistent continuity is useful, but a global widget risks dashboardization and Terminal dilution. | First repair contextual next actions; defer global widget. |
| Add a map versus remove map affordance | `Map.tsx` is unused and has external/deployment implications; no evidence of curriculum value. | Do not add map. Use an anchor to existing stage content or remove affordance. |
| Disable AR versus implement RTL now | Mission intent supports Arabic, but no translation/direction layer exists. | Conditional: implement only with bounded content/engineering ownership; otherwise honest roadmap/unavailable state. |
| Bottom rail 4-column bug versus later 5-column fix | Earlier audit context reported a mismatch; supplied CSS includes later `repeat(5)` rules. | Treat as regression test, not current defect. |

---

## 16. NEW INSIGHTS / AUDIT GAPS

### AB-N001 — Provenance must be attached to actions, not only metrics

**Evidence:** The UI contains action confirmations such as Backup created, language set, route/map available, and mission order updated while the corresponding operations are not always performed.  
**Why it matters:** Evidence integrity is affected by the user’s belief that an action occurred, even when no number changed.  
**Why existing audits may have underweighted it:** Most audits grouped these under “toast stubs,” but the product’s central promise makes action provenance a trust concern.  
**Confidence / priority / dependency:** High / P1 / UI + Interaction.  
**Recommendation:** Define confirmation copy by operation class: completed, preview, unavailable, or failed; never use completed language for a no-op.

### AB-N002 — The strongest product asset is the transition contract, not the individual screen

**Evidence:** Progression, Scenario, Growth, and Tracking all set Practice context; Assessment persists records that feed Growth/Tracking.  
**Why it matters:** A redesign that beautifies screens but breaks context continuity would reduce learning value.  
**Why existing audits may have underweighted it:** Screen-by-screen audits naturally foreground local defects.  
**Confidence / priority / dependency:** Very high / P0 preservation constraint / UI + Interaction.  
**Recommendation:** Add regression tests for context, record, route, and browser-history continuity before any visual refactor.

### AB-N003 — “Local preview” needs a shell-level disclosure, not only a Terminal disclosure

**Evidence:** Practice visibly says local/illustrative, while Growth, Tracking, Progression, and Scenarios present seeded/readiness values with less prominent provenance.  
**Why it matters:** Users encounter evidence outside the Terminal and may not carry the disclaimer with them.  
**Confidence / priority / dependency:** High / P1 / UI + Content.  
**Recommendation:** Add a restrained, persistent preview/provenance cue at the shell or evidence surfaces, without adding a large warning banner that disrupts the workstation.

---

## 17. FINAL PRIORITY MATRIX

| Finding ID | Issue / Decision | Sources | Evidence | Independence | Consensus | Evidence quality | Impact | Risk | Dependency | Priority | Verdict |
|---|---|---|---|---|---|---|---|---|---|---|---|
| AB-F001 | Blank input must not become FQD | S-03, S-18–S-26 | Source | E4 | C5 | Very Strong | High | Evidence corruption | UI/Interaction | P0 | ACCEPT |
| AB-F002 | Neutral first-use Terminal state | S-03, S-09–S-26 | Source + render | E4 | C5 | Very Strong | High | False failure | UI | P0 | ACCEPT |
| AB-F003 | Evidence provenance/reconciliation | S-03, S-09–S-17 | Source + render | E4 | C5 | Very Strong | High | Contradictory truth | UI/Data | P0 | ACCEPT |
| AB-F004 | No misleading secondary actions | S-03, S-18–S-26 | Source | E4 | C5 | Very Strong | Med/High | False success | UI/Interaction | P1 | ACCEPT WITH MODIFICATION |
| AB-F005 | Terminal state/mode contract | S-03, S-09–S-26 | Source + render | E3/E4 | C5 | Strong | High | Assessment ambiguity | UI/Mixed | P1 | ACCEPT |
| AB-F006 | Complete recoverable states | S-03, S-18–S-26 | Source | E4 | C4 | Strong | High | Dead ends | UI/Interaction | P1 | ACCEPT |
| AB-F007 | Mobile keyboard/workstation hardening | S-04, S-09–S-17 | CSS + render | E3 | Conditional | Strong/Moderate | High | Input/feedback loss | UI | P1 | TEST BEFORE ACCEPTING |
| AB-F008 | Font/contrast/readability contract | S-04, S-09–S-17 | CSS + render | E3 | Conditional | Strong/Moderate | High | Fatigue/A11y | UI/Content | P1 | TEST BEFORE ACCEPTING |
| AB-F009 | Honest EN/AR contract | S-03–S-04 | Source | E4 | C5 | Very Strong | High | RTL misrepresentation | Mixed | P1 | ACCEPT WITH MODIFICATION |
| AB-F010 | Shared accessibility semantics | S-03–S-04 | Source | E3/E4 | C4 | Strong | High | WCAG barriers | UI | P1 | ACCEPT |
| AB-F011 | Semantic state-token consolidation | S-04 | CSS | E4 | C4 | Good | Med | Drift/colour reliance | UI | P2 | ACCEPT |
| AB-F012 | Navigation orientation/focus | S-03–S-07, renders | Source + render | E3 | C4 | Strong | Med/High | Context loss | UI/Interaction | P2 | ACCEPT WITH MODIFICATION |
| AB-F013 | Evidence-to-action closure | S-03, renders | Source + render | E3 | C4 | Strong | High | Misguided practice | UI/Data | P1 | ACCEPT WITH MODIFICATION |
| AB-F014 | Curriculum/service provenance | S-03, S-14 | Source + render | E3 | C3 | Strong | Med/High | Curriculum misrepresentation | Content/Data | P2 | ACCEPT WITH MODIFICATION |
| AB-F015 | Mobile/touch parity for Growth coaching | S-03–S-04, S-11 | Source + render | E3 | C3 | Good | Med | Unequal learning support | UI | P2 | ACCEPT |
| AB-F016 | Reduced-motion/long-session hardening | S-03–S-04 | Source | E3 | C3 | Good | Med | Fatigue/A11y | UI | P2 | TEST BEFORE ACCEPTING |
| AB-F017 | Do not activate speculative MapView | S-03, S-05, S-08 | Source | E4 | C3 | Very Strong | Low/Med | Scope drift | Architecture | P3 | REJECT |
| AB-N001 | Action provenance | S-03, S-18–S-26 | Source | E4/E3 | C4 | Strong | High | False confirmation | UI/Interaction | P1 | ACCEPT |
| AB-N002 | Preserve transition contracts | S-03, S-18–S-26 | Source | E4 | C4 | Very Strong | High | Learning-loop break | UI/Interaction | P0 | ACCEPT |
| AB-N003 | Shell-level local-preview disclosure | S-03, renders | Source + render | E3 | C3 | Strong | High | Evidence confusion | UI/Content | P1 | ACCEPT |

---

## 18. IMPLEMENTATION SEQUENCE

### Phase A — Design-system foundations

Create the state/provenance vocabulary, semantic tokens, typography loading contract, readable type minimums, progressbar primitive, button disabled/loading variants, landmark/skip-link primitives, and dialog/drawer focus behavior. Do not alter the visual identity.

### Phase B — Core workstation / Terminal

Fix AB-F001 and AB-F002 first. Then implement the session summary, mode contract, recoverable state matrix, command/response semantics, Coach hierarchy, Reference contract, assessment lock/closure, and focus-mode focus management. Preserve valid command evaluation and scoring.

### Phase C — Primary learning / Progression

Reconcile Progression values, make current action dominant, expose inline locked rules, add curriculum provenance slots, and provide an honest service-track empty/preparation state. Preserve hero, route motif, milestones, and Resume CTA.

### Phase D — Supporting workflow screens

Repair Scenario filters/sort/empty states and context IDs; repair Growth tab/hover parity, Backup honesty, evidence provenance, and next-action explanations; repair Tracking metric definitions, empty/insufficient evidence, and table semantics.

### Phase E — Responsive refinement

Run the explicit desktop/tablet/mobile matrix. Harden Terminal at 320/360/390/430px with native keyboards, check Growth/Tracking clipping and scroll, and verify mobile drawer/rail behavior.

### Phase F — Polish and accessibility hardening

Run screen-reader and keyboard tests, contrast audit, reduced-motion audit, Arabic/LTR fixture test if AR is enabled, animation restraint review, and regression tests for AN → SS → FQD → FXP, context handoffs, localStorage persistence, browser history, and assessment closure.

---

## 19. VALIDATION PLAN

| Test | Where / device | Expected result | Failure condition / owner |
|---|---|---|---|
| Blank command safety | Practice Learn/Practice/Assessment; desktop + 360px mobile | No event, score, hint, toast success, or persistence write; inline correction appears. | Any history/score/evidence mutation; owner: interaction engineer. |
| First-use neutrality | Fresh storage, `/practice`; 320–430px and desktop | Neutral ready state, no red error before input. | Error styling/copy before command; owner: UX/UI. |
| Valid sequence regression | Practice; desktop and mobile | AN, SS, FQD, FXP still produce existing simulated responses and assessment behavior. | Response/scoring regression; owner: engine-boundary reviewer. |
| Assessment contract | Practice mode switching and Finish Session | Mode copy, hint policy, history retention/reset, completion, and debrief match documented contract. | Ambiguous or contradictory record; owner: product + engineering. |
| Provenance reconciliation | All routes; empty, one-record, seed, multiple-record fixtures | Labels and counts match source; illustrative/local distinctions visible. | Any unexplained number or completed-action claim; owner: data/UI. |
| Keyboard navigation | All routes; desktop keyboard, NVDA/VoiceOver/TalkBack | Route, tabs, charts, drawers, Reference, search, Terminal, and dynamic states are discoverable and announced once. | Trap, lost focus, double announcement, missing role; owner: accessibility reviewer. |
| Mobile keyboard | Practice at 320, 360, 390, 430px on Android Chrome and iOS Safari | Input and Execute remain reachable; latest result remains understandable; no jump/clipping. | Obscured input/result or layout jump; owner: frontend + QA. |
| RTL/mixed content | Every route with Arabic fixture; 360/430px and desktop | Arabic layout direction works; commands, IDs, numbers, and codes remain isolated LTR; no overlap/clipping. | Cosmetic toggle only or bidi collision; owner: content/i18n owner. |
| Scenario context | Scenarios start/resume/review → Practice | Stable scenario context/ID is visible and recommendation/evidence path remains coherent. | Generic Pricing context replaces scenario; owner: product/UI. |
| Growth/Tracking closure | Complete assessment → Growth/Tracking → targeted Practice | Latest record appears, recommendation explains basis, CTA carries context, table and chart agree. | Stale/mismatched record or unexplained recommendation; owner: data/UI. |
| Reduced motion | All routes with OS reduced-motion enabled | No nonessential animation, caret blink, smooth-scroll jump, or animated intermediate announcement. | Persistent motion/announcement; owner: accessibility reviewer. |
| Deep links/history | `/`, `/practice`, `/scenarios`, `/growth`, `/tracking`; back/forward | Correct route and context survive direct load and browser navigation. | Blank route or lost orientation; owner: frontend. |

---

## FINAL QUALITY GATE

**Completeness:** all supplied artifact classes were inventoried: specification, design ground truth, seven source files, seven screenshots, and nine audits.  
**Coverage:** meaningful findings were accepted, modified, rejected, deferred through validation, or explicitly marked dependency/unknown; audit repetition was not counted as independent proof.  
**Traceability:** canonical findings map observations to source artifacts, evidence strength, decision, action, and validation.  
**Restraint:** the recommended work is a controlled hardening pass, not a redesign or architecture rewrite.  
**Preservation:** the Flight Deck identity, Terminal-first intent, learning loop, focus mode, evidence language, and strong local context handoffs are protected.  
**Uncertainty:** runtime fonts, exact contrast, physical touch targets, actual screen-reader output, desktop captures, and native keyboard behavior are marked for validation rather than guessed.

> **Final master principle:** The next version should feel like a premium airline-training workstation that happens to use a modern interface—not a dashboard that happens to contain aviation content. The UI may interpret engine state, but it must never invent engine truth.

---

## References

[1]: /home/ubuntu/upload/Home.tsx "AeroBridge main application source"
[2]: /home/ubuntu/upload/index.css "AeroBridge design system and responsive styles"
[3]: /home/ubuntu/upload/ideas.md "AeroBridge design ground truth"
[4]: /home/ubuntu/upload/aduitsprompt.md "AeroBridge master audit protocol"
[5]: /home/ubuntu/upload/55523.jpg "Progress Tracking rendered reference"
[6]: /home/ubuntu/upload/55521.jpg "Growth Record rendered reference"
[7]: /home/ubuntu/upload/55519.jpg "Practice rendered reference"
[8]: /home/ubuntu/upload/55517.jpg "Scenarios rendered reference"
[9]: /home/ubuntu/upload/55514.jpg "Progression rendered reference"
[10]: /home/ubuntu/upload/55526.jpg "Growth History rendered reference"
[11]: /home/ubuntu/upload/55528.jpg "Growth Reports rendered reference"
[12]: /home/ubuntu/upload/chatgptaudit.md "Supplied analytical audit"
[13]: /home/ubuntu/upload/Claudeaudit.md "Supplied analytical audit"
[14]: /home/ubuntu/upload/deepseekaudit.md "Supplied analytical audit"
[15]: /home/ubuntu/upload/giminiaudit.md "Supplied analytical audit"
[16]: /home/ubuntu/upload/grokaudit.md "Supplied analytical audit"
[17]: /home/ubuntu/upload/kimi.md "Supplied analytical audit"
[18]: /home/ubuntu/upload/Manusaudit.md "Supplied analytical audit"
[19]: /home/ubuntu/upload/qwenaudit.md "Supplied analytical audit"
[20]: /home/ubuntu/upload/v0.devaudit.md "Supplied analytical audit"
