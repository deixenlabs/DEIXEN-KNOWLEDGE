# AEROBRIDGE — MASTER SYNTHESIS AUDIT

**Document status:** Independent adjudication and implementation handoff  
**Review date:** 15 August 2026  
**Prepared by:** Manus AI  
**Overall direction:** **Preserve and Refine**  
**Design status:** **Needs targeted revision**  

> **Core principle:** The UI may interpret engine state, but it must never invent engine truth.

This document is an independent synthesis of the original product intent, the extracted prototype archive, seven rendered screenshots, the master audit protocol, and all nine supplied unified audits. It is not a vote and it is not a mechanical merger of recommendations. Direct source and screenshot evidence control the decisions; audit repetition is treated as a consensus signal only. Where the package cannot prove a claim, the decision is explicitly marked **NEEDS VALIDATION**.

---

## A. Executive Decision

AeroBridge should be **preserved and refined**, not redesigned, partially rebuilt, or converted into a more conventional dashboard. The prototype already contains a distinctive Flight Deck Console identity, a credible terminal-first learning workstation, a useful Progression → Practice → Assessment → Growth → Tracking → Scenarios loop, and a particularly strong evidence-to-next-action pattern in Growth Record. The original design-ground-truth file explicitly defines the project as reference preservation and prohibits adding backend, authentication, payment, real metrics, or engine architecture to the preview [1]. The supplied archive confirms that the current app is a React/TypeScript preview with a mounted `Home` shell, local illustrative responses, localStorage-backed assessment records, and no need for an architecture reset [2] [3] [4].

The current prototype is not ready to be treated as a trustworthy production reference because the visual maturity exceeds the truthfulness of several states. The most serious defect is source-verified: an empty command is coerced to `FQD`, added to history, and can contribute to assessment evidence [5]. A second source- and screenshot-verified defect is the first-use Coach contradiction: the terminal says it is awaiting a command while the Coach displays a red `FORMAT ERROR · CHECK ENTRY` and corrective text before the trainee has caused an error [6] [7]. The screenshots and source also show unreconciled illustrative counters such as `3 / 8 stages`, `23 / 40`, `LOG 04 / 12`, `86%` fresh-session accuracy, and `128 / 210` mastered commands [6] [8] [9] [10] [11].

The three most important decisions are therefore:

| Decision | Classification | Why it is decisive |
|---|---|---|
| Make blank submission a non-destructive no-op and remove the fabricated first-use error state. | **MUST FIX** | Protects training evidence, command semantics, first-use trust, and assessment integrity without changing the command evaluator. |
| Establish one visible provenance contract for every metric, state, and action confirmation. | **MUST FIX** | Prevents illustrative preview content from being mistaken for learner evidence or completed operations. |
| Preserve the terminal-first Flight Deck Console while hardening state semantics, accessibility, and mobile behavior through targeted changes. | **PRESERVE + SHOULD FIX** | Improves operability without violating the product’s stated identity, learning loop, or presentation-first boundary. |

The evidence is sufficient to proceed to the next design-refinement stage for the P0 and most P1 UI decisions. It is **not sufficient** to finalize physical keyboard behavior, desktop/tablet composition, real font loading in deployment, screen-reader output, exact contrast at rendered font metrics, touch-target success, or the release scope of Arabic/RTL. Those items remain **NEEDS VALIDATION** rather than assumed implementation facts.

### Evidence and adjudication method

The master prompt requires source priority over audit consensus, separation of evidence from opinion, explicit conflict resolution, the classifications **MUST FIX**, **SHOULD FIX**, **COULD IMPROVE**, **PRESERVE**, **REJECT**, and **NEEDS VALIDATION**, and an implementation-ready A–M report [12]. All nine audits were considered: Claude, ChatGPT, DeepSeek, Gemini, Grok, Kimi, Manus, Qwen, and v0.dev [13]–[21]. The original archive was extracted and checked directly; importantly, it contains `client/index.html`, `ErrorBoundary`/`NotFound`-related project files, the full `Home.tsx`, the full `index.css`, and the supporting configuration files. Claims based on an earlier or narrower source package were therefore downgraded when they conflicted with the extracted archive.

| Evidence class | Meaning in this report | Examples |
|---|---|---|
| **E4 — Directly verified** | Visible in the extracted source or rendered screenshot. | Blank `FQD` fallback, Coach fallback error, hardcoded counters, viewport metadata, toast-only handlers, screenshot text. |
| **E3 — Independently corroborated** | Supported by materially different evidence types. | Source behavior also visible in a screenshot; source plus an independently derived cascade observation. |
| **E2 — Corroborated analysis** | Multiple audits identify the same risk, but their underlying evidence is substantially shared. | Typography, contrast, mobile density, incomplete state language. |
| **NEEDS VALIDATION** | Not safely determinable from the package. | Screen-reader behavior, real keyboard overlap, production font loading, desktop/tablet layout. |

---

## B. Product and Design Principles to Preserve

### B.1 Flight Deck Console identity

Preserve the deep-navy foundation, Vector Blue route accents, restrained gradients, atmospheric route motifs, green/amber/red operational semantics, compact utility controls, and monospace treatment for command and readout material. This is not generic SaaS styling; it communicates a serious aviation-training workstation and is directly visible across all supplied renders [6]–[11]. Acceptable modification includes token consolidation, contrast correction, more consistent typography, and removal of decorative noise that does not communicate state. Do not replace the identity with a light consumer interface, a gamified badge system, or a generic analytics dashboard.

### B.2 Terminal-first workstation hierarchy

Preserve Practice/Terminal as the primary working surface. It contains command input, history recall, Learn/Practice/Assessment modes, Reference, Coach support, Focus Mode, local-simulation disclosure, and assessment closure. The terminal must remain a workstation rather than becoming a small dashboard card. Acceptable modification includes reclaiming mobile space, clarifying state, making the Coach subordinate, and adding semantic accessibility behavior. Do not add autocomplete, alter command matching, replace the terminal with a form-heavy wizard, or invent engine semantics.

### B.3 Evidence-to-next-action learning loop

Preserve the sequence **read evidence → practice the gap → apply in scenario**. Growth Record’s Record, History, and Reports views make performance actionable rather than merely displaying scores [9] [10] [11]. The recommended-practice CTA and scenario context handoff into Practice are high-value product behaviors. Acceptable modification includes attaching a stable scenario or skill identifier to the handoff and clarifying whether the evidence is local, illustrative, calculated, historical, or authoritative. Do not replace the loop with a global KPI dashboard or add a new route without evidence.

### B.4 Five-area product shape and navigation

Preserve the desktop sidebar concept, compact mobile bottom rail, and centered Train/Practice emphasis. The five-area shape is visible in the screenshots and is consistent with the product sequence in `ideas.md` [1] [6]–[11]. The extracted CSS contains a later five-column rule, so the historical “four columns for five items” claim is treated as cascade debt and a regression risk, not a confirmed current rendered defect [3] [22]. Navigation can be made more semantic and honest, but it should not be reorganized into a new information architecture.

### B.5 Local/illustrative boundary

Preserve the explicit `LOCAL TRAINING SIMULATION` and `ILLUSTRATIVE` disclosure. It correctly prevents the preview from pretending to be a live carrier or Amadeus system [5] [6]. The required refinement is consistency: every sample metric, seeded record, and simulated response must share the same provenance grammar. A local preview may show sample content; it may not style sample content as if it were verified trainee evidence.

### B.6 Accessibility foundations worth retaining

Preserve the visible `:focus-visible` treatment, the `aria-live` intention around terminal history and assessment reporting, reduced-motion coverage, labelled progress rings, and the same-data chart table alternative. The Progress Tracking chart’s `details`/table representation is a strong pattern and should become the reference for future data visualizations [5] [6] [24]. Improve its semantics rather than replacing it with a chart library merely for fashion.

---

## C. Critical Problems

The following table contains only high-impact problems supported by direct source/screenshot evidence or a strong evidence chain. Severity is not a popularity score; it reflects user impact, confidence, and proximity to the product’s trust boundary.

| ID | Problem | Evidence | User / Product Impact | Severity | Decision |
|---|---|---|---|---|---|
| **AB-M-01** | Blank or whitespace command silently becomes `FQD` and is recorded. | `Home.tsx` contains `command.trim().toUpperCase() || "FQD"`; the same handler pushes history and shows a success toast [5]. | Creates a false command event, can alter assessment evidence, and teaches the trainee that no input is a valid operational action. | Critical / P0 | **MUST FIX** |
| **AB-M-02** | Fresh Practice shows a fabricated error while the terminal is awaiting input. | `latestEntry?.response ?? "FORMAT ERROR · CHECK ENTRY"` and corrective text are source-visible; the red error is visible in `55519.jpg` [5] [6]. | Contradicts the system state at first use and damages trust before the trainee begins. | Critical / P0 | **MUST FIX** |
| **AB-M-03** | Illustrative and local metrics are presented with the authority of measured evidence. | `Home.tsx` contains seeded records and literals including `86`, `128 / 210`, `23 / 40`, `LOG 04 / 12`, and fixed report values; the same values appear in screenshots [5] [6] [8]–[11]. | Trainees cannot tell what they accomplished, what is sample content, and what is calculated from the current session. | Critical / P0 | **MUST FIX** |
| **AB-M-04** | Controls imply completed operations while only producing informational or success toasts. | Source handlers for language, Backup, Filters, section actions, Reference action, map/stage actions, and some scenario outcomes call toast without performing the promised operation [5]. | Creates false affordances and undermines professional trust. “Backup created” is particularly misleading if no artifact is created. | High / P0–P1 | **MUST FIX** |
| **AB-M-05** | Terminal state contract is incomplete and feedback ownership is fragmented. | Source declares more state concepts than the visible UI consistently distinguishes; session, command, history, Coach, and footer distribute status across several regions [5] [6] [13] [15]. | Slows orientation and makes ready, processing, invalid, recoverable error, completion, and assessment boundaries ambiguous. | High / P1 | **SHOULD FIX** |
| **AB-M-06** | Typography and muted metadata may be too small or low contrast for long sessions. | CSS uses 9px eyebrow text, 7px mode metadata, 10px labels, `--text-faint: #5d6a85`, and `--blue: #6f8fff`; audits report contrast risks [22] [13] [15]. Exact rendered ratios require runtime validation. | Reduces readability, especially on narrow devices and in bright environments. | High / P1 | **SHOULD FIX**, with final contrast **NEEDS VALIDATION** |
| **AB-M-07** | Viewport metadata restricts zoom and declared fonts are not provisioned in `index.html`. | Extracted `index.html` uses `maximum-scale=1`; font links are inside a deletion comment while CSS references Space Grotesk, Cairo, and IBM Plex Mono [23] [22]. | Restricts user zoom and makes the visual system non-deterministic. Font-loading severity remains deployment-dependent. | High / P1 | Zoom **MUST FIX**; fonts **NEEDS VALIDATION / SHOULD FIX if confirmed** |
| **AB-M-08** | Tab, segmented-control, progress-bar, and landmark semantics are incomplete. | Source scan shows no `role="tab"`, `aria-selected`, or `aria-pressed`; `AnimatedBar` renders an `<i>` with only `aria-label`; there is no `<main>` landmark in the mounted shell [5] [13] [15]. | Keyboard and assistive-technology users receive weak selection/state information; progress is not semantically exposed. | High / P1 | **MUST FIX** for semantics |
| **AB-M-09** | Overlay and drawer focus/escape behavior is not demonstrated or fully implemented. | Reference drawer, mobile menu, Coach collapse, and Focus Mode are interactive surfaces; source evidence does not establish a complete focus trap, return focus, `Escape`, or dialog contract [5] [13] [15]. | Keyboard users can lose context; mobile and desktop overlays may be difficult to dismiss or navigate. | High | **NEEDS VALIDATION**, then **SHOULD FIX** where absent |
| **AB-M-10** | Mobile Terminal density and keyboard behavior are not fully proven. | `55519.jpg` shows a large terminal gap and compact vertical stack; CSS includes mobile sticky-input rules, but no screenshot includes an open virtual keyboard [5] [6] [13] [20]. | The core workstation may become difficult to use on short viewports, but the exact failure mode is unproven. | High | **NEEDS VALIDATION** with targeted refinement |
| **AB-M-11** | EN/AR control is cosmetic rather than a real language switch. | Handler changes a local label and says “Interface language set”; no direction, translation, or document language change is shown [5] [13] [15]. | Implies a capability that does not exist and is especially problematic for the stated Saudi-market positioning. | High | **MUST FIX** honesty; full RTL is **NEEDS VALIDATION / product scope** |
| **AB-M-12** | Scenario context handoff appears title-based rather than trace-stable. | Source uses `setPracticeContext(selected.title)` and Growth uses strings such as `Pricing / PNR`; audits identify provenance loss risk [5] [13] [15]. | Practice may lose scenario identity, skill mapping, or evidence lineage even though the basic navigation works. | Medium–High | **SHOULD FIX** at UI contract level; engine mapping **NEEDS VALIDATION** |

---

## D. Master Decision Matrix

The matrix applies the required classification vocabulary and separates accepted changes from preserved assets, rejected ideas, and decisions requiring validation.

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Technical Feasibility | Impact | Confidence | Cost | Risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MD-01 | Terminal input | Reject empty/whitespace submit as a no-op with inline correction; never default to `FQD`. | **MUST FIX** | E4 source [5] | Very high | Strengthens operational honesty | Low; handler guard only | Very high | Very high | Low | Low | [5] [6] |
| MD-02 | Coach | Fresh session renders neutral `AWAITING COMMAND`; error styling only follows a real failed entry. | **MUST FIX** | E4 source + screenshot [5] [6] | Very high | Preserves calm console language | Low | Very high | Very high | Low | Low | [5] [6] |
| MD-03 | Evidence | Create a provenance grammar: local, illustrative, calculated, historical, authoritative; attach it to metrics and actions. | **MUST FIX** | E4 source + screenshots [5] [8]–[11] | Very high | Directly supports evidence-first identity | Medium; requires content/UI pass | Very high | Very high | Medium | Low–Medium | [1] [5] |
| MD-04 | Counts | Derive counts from the same arrays rendered in detail, or state “available now” and mark sample data. | **MUST FIX** | E4 source + screenshots [5] [8]–[10] | High | Improves precision without changing layout | Low–Medium | High | Very high | Low | Low | [5] |
| MD-05 | Toasts/actions | Implement, relabel as preview/unavailable, or remove every action that only toasts; never claim backup creation without an artifact. | **MUST FIX** | E4 source [5] | High | Makes controls match console professionalism | Medium | High | Very high | Low–High by action | Low–Medium | Medium | [5] [6] |
| MD-06 | Terminal state | Define visible ready, processing, success, partial, syntax error, recoverable error, interrupted, assessment active, complete, and empty states without inventing engine truth. | **SHOULD FIX** | E3/E4 source analysis [5] [13] [15] | High | Makes the workstation more operational | Medium | High | High | Medium | Medium | Medium | [5] [13] |
| MD-07 | Accessibility | Add main landmark, skip link, selected semantics, progressbar semantics, non-color status cues, and route/overlay focus behavior. | **MUST FIX** for confirmed semantics; **NEEDS VALIDATION** for runtime behavior | E4 source; runtime gaps [5] [13] [15] | High | Enhances rather than changes identity | Medium | High | High | Medium | Low–Medium | Low | [5] [22] |
| MD-08 | Viewport | Remove `maximum-scale=1`; preserve user zoom. | **MUST FIX** | E4 extracted `index.html` [23] | High for low-vision users | Invisible visual change | Very low | High | Very high | Low | Low | Low | [23] |
| MD-09 | Typography | Confirm actual font loading; provision declared fonts or revise tokens to the true shipped stack. | **NEEDS VALIDATION** then **SHOULD FIX** if absent | E4 file, but deployment behavior untested [22] [23] | Medium–High | Protects Flight Deck identity | Low–Medium | Medium–High | Medium | Low–Medium | Low | [22] [23] |
| MD-10 | Contrast/type scale | Raise meaningful muted text and CTA contrast; establish documented minimums without flattening the console aesthetic. | **SHOULD FIX** | CSS + audits; rendered ratio requires validation [22] [13] | High | Preserves palette hue | Low–Medium | High | Medium–High | Medium | Low–Medium | Low | [13] [22] |
| MD-11 | Mobile Terminal | Test 320/360/390/430px and keyboard-open states; refine gap and status compression only after observing actual failure. | **NEEDS VALIDATION** | Mobile screenshot + CSS [5] [6] [22] | High if confirmed | Preserves terminal-first hierarchy | Medium | High | Medium | Medium | Medium | Medium | [5] [6] |
| MD-12 | Arabic | Relabel as preview/roadmap until a bounded i18n/RTL contract exists; do not fake direction change. | **MUST FIX** for honesty; full implementation **NEEDS VALIDATION** | E4 source [5] | High for expectation management | Consistent with evidence-first identity | Low for relabel; high for full RTL | High | High | Low for relabel; high for RTL | Medium for RTL | [1] [5] |
| MD-13 | Growth structure | Preserve Record/History/Reports and the learning-loop strip; do not merge Progress Tracking without task evidence. | **PRESERVE** | Direct screenshots + intent [1] [9]–[11] | High | Strongly consistent | No new complexity | High | High | Low | Low | [1] [9]–[11] |
| MD-14 | Chart | Preserve same-data chart plus accessible table; defer Recharts migration. | **PRESERVE / REJECT migration** | Source + screenshot [5] [6] | Medium–High | Protects existing strength | Low | High | High | Low | Low | [5] [6] |
| MD-15 | Coach mobile | Keep terminal-first ordering; do not add a FAB or bottom sheet without evidence that post-command coaching is missed. | **PRESERVE / NEEDS VALIDATION** | Conflicting audits; screenshot [6] [13] [15] | Medium | Avoids unnecessary interaction surface | Low now | Medium | Medium | Low now | Medium if added | [6] [13] |
| MD-16 | Map | Do not activate unused `MapView` solely because a “View map” affordance exists. | **REJECT** | Import trace + design ground truth [1] [5] | Avoids distraction and unsupported scope | Strong | Low to remove/relabel | Medium | High | Low | Low | [1] [5] |
| MD-17 | Global dashboard | Do not merge Growth and Progress Tracking as a redesign response. | **REJECT** | Screens have distinct evidence and trend jobs [9]–[11]; no task evidence | Prevents information-architecture churn | Strong | Low to reject | Medium | Medium–High | Low | Low | [1] [9]–[11] |
| MD-18 | Autocomplete/pause | Do not add command autocomplete or engine-level Pause/Resume without pedagogical/engine evidence. | **REJECT** | Original boundary and audit conflicts [1] [13] [15] | Avoids undermining recall training or inventing engine state | Strong | Not justified | Medium | High | Low | Medium | [1] [13] |
| MD-19 | Interactive polish | Add restrained pressed/disabled/hover/focus states where absent, but do not add animation for its own sake. | **COULD IMPROVE** | Audit observations; source has some states [22] [17] | Medium | Compatible if restrained | Medium | Medium | Medium | Low–Medium | Low–Medium | Low | [17] [22] |

---

## E. Required Changes by Priority

### E.1 P0 — Blocking / Must Fix

#### P0-01 — Terminal input safety

**Objective:** Ensure that only an intentional non-empty command becomes a training event. The current problem is the `|| "FQD"` fallback, which creates history, score, and toast consequences from a blank submit. The exact change is to trim the input, check for an empty string before command matching, keep focus in the input, render an inline correction such as `NO ENTRY · TYPE A COMMAND`, and return without touching history, scoring, hints, or persistence. What must remain unchanged is the behavior of non-empty `AN`, `SS`, `FQD`, `FXP`, and unknown commands. The change is low-cost and low-risk because it is a guard at the UI/interaction boundary. Dependency: the inline validation state must have an accessible announcement. Risk: a generic form handler or keyboard shortcut could bypass the guard, so both submit and Enter paths must be tested.

**Priority:** P0. **Owner:** Practice/Terminal implementation. **Acceptance:** blank submit adds no history row, does not change `LOG`, score, or localStorage, creates no success toast, and leaves the input usable.

#### P0-02 — Honest first-use Coach state

**Objective:** Align the Coach with the actual session state. When `commandHistory.length === 0`, render neutral copy such as `SYSTEM RESPONSE / AWAITING COMMAND`, `No command has been submitted yet`, and a workflow-oriented next step. Only render red error copy when `latestEntry` exists and `latestEntry.ok === false`. Preserve the existing Coach layout, reference affordance, and “Guidance without shortcuts” positioning. Dependency: latest-entry state remains the owner of error styling. Risk: none beyond ensuring a completed session does not regress to the empty state.

**Priority:** P0. **Owner:** Coach/Terminal UI. **Acceptance:** a fresh Practice session has no red error, no fabricated correction, and a real syntax error still produces an error state.

#### P0-03 — Evidence provenance contract

**Objective:** Make every displayed metric explain what it is. Introduce a shared provenance treatment with four minimum fields: **owner**, **source**, **period**, and **status**. Recommended compact labels are `LOCAL`, `ILLUSTRATIVE`, `CALCULATED`, `HISTORICAL`, and `AUTHORITATIVE` only when backed by an actual authoritative source. Current hardcoded values must either be derived from rendered arrays or marked `ILLUSTRATIVE / LOCAL PREVIEW`. The `86%` fresh-session accuracy should become `—` or `Awaiting first command`; seeded records should be labeled as sample/local evidence; and `23 / 40`, `3 / 8`, and `LOG 04 / 12` should be computed or changed to “3 of 6 available in this preview” where that is the actual rendered dataset. Preserve the content hierarchy and visual restraint; do not add a dashboard of provenance badges.

**Dependencies:** product/content owner must confirm whether sample values are intentionally part of the preview. **Risk:** changing numbers without confirming dataset semantics can create new contradictions; derive first, relabel second, and remove only when required.

#### P0-04 — Remove false affordances

**Objective:** Audit every active-looking control and choose exactly one disposition: perform the action, visibly label it as preview/unavailable/roadmap, or remove it. This includes Language, Backup, Filters, Search, My route, View map, See all stages, section actions, Coach “Open reference,” and scenario result actions. `Backup` must not say a backup point was created unless a real backup artifact exists. Toasts are appropriate for session-level events that actually occurred, not as substitutes for navigation or data mutation. Preserve compact utility controls when they are honest. Dependency: action inventory and product owner disposition. Risk: removing too many controls can reduce discoverability; relabeling is preferred where the control communicates a useful future boundary.

### E.2 P1 — High-Value Improvements

#### P1-01 — Canonical Terminal state model

Define one UI state matrix with explicit representations for `empty`, `ready`, `processing`, `success`, `partial success`, `syntax error`, `recoverable error`, `interrupted`, `assessment active`, `assessment complete`, `review`, and `locked/unavailable`. The UI may display these states only when supplied by the current local model; it must not invent a processing or engine result that the model cannot produce. A concise status line should identify mode, session state, command state, and next useful move. In Assessment, display `ASSESSMENT ACTIVE · HINTS SUPPRESSED` and keep Coach in a compact boundary state rather than providing shortcuts. Preserve the existing command evaluator and scoring formula.

#### P1-02 — Accessibility semantics and landmarks

Add a skip link and a `<main id="main-content">` landmark around routed content. Move focus to the page heading on route changes where this can be done without disrupting command entry. Convert mode tabs, metric switchers, Growth tabs, scenario filters, and track selectors into semantically correct tablist or button-group patterns according to their actual behavior; do not add `role="tab"` to controls that are not tabs. Expose selected state through `aria-selected` or `aria-pressed` as appropriate. Convert `AnimatedBar` from a decorative `<i>` with an aria label into a real progress representation with `role="progressbar"`, `aria-valuemin`, `aria-valuemax`, and `aria-valuenow`, or pair it with an accessible text value. Add textual state labels alongside color. Preserve the chart’s existing same-data table.

#### P1-03 — Contrast, typography, and zoom

Remove `maximum-scale=1` from the viewport metadata. Confirm that Space Grotesk, IBM Plex Mono, and Cairo actually load in the deployed preview; if they do not, either provision them through local assets or revise the tokens to the actual shipped stack. Establish a type scale with a practical floor of 12px for meaningful metadata and 14px for instructional reading text; a smaller mono label may remain only where it is genuinely supplementary and remains readable after validation. Raise `--text-faint` and/or adjust semantic surfaces so meaningful text reaches WCAG AA at its actual rendered size. Darken the primary button or change its text treatment if the final contrast check fails. Preserve the deep palette and hierarchy rather than applying a blanket brightness increase.

#### P1-04 — Mobile Terminal validation and refinement

Validate 320, 360, 390, and 430 CSS pixels with the virtual keyboard open on at least one Android and one iOS device or equivalent device emulation. Measure whether the last system response, active input, submit control, and status line remain visible and operable. The current CSS’s 16px input and safe-area-aware sticky input are valuable and should be retained. If the fixed terminal gap is responsible for lost work surface, reduce the gap or make it flexible; do not shrink the Terminal into a dashboard card. Keep the Coach below or subordinate to the terminal until testing proves that another pattern is required.

#### P1-05 — Stable context and evidence lineage

Pass a stable context object or identifier into Practice, not only a display title. At minimum, the UI contract should distinguish `scenarioId`, `scenarioTitle`, `skillCode`, `sourceView`, and `handoffReason`; the actual mapping to curriculum remains a content/engine decision. The visible copy may still show the title. This preserves the existing handoff while preventing loss of scenario identity and future evidence provenance.

### E.3 P2 — Optional / Later Improvements

P2 work should follow the P0/P1 hardening rather than becoming a new redesign pass. It may include consolidating radius and spacing tokens, removing dead MapView code or explicitly documenting it as out of scope, reducing decorative clip-path noise in KPI cards if user testing shows distraction, improving pressed/disabled states on secondary controls, and adding restrained transitions for tab changes. Custom scrollbars, bottom-sheet dragging, FABs, counting animations, and richer micro-interactions are not automatically approved; they require evidence of a concrete usability problem and must respect reduced-motion behavior.

---

## F. Component-Level Specifications

### F.1 Terminal input rail

**Current state:** A form with a text input, prompt marker, submit button, 16px-oriented mobile intent, and command history interaction. **Problem:** blank input executes `FQD`. **Decision:** non-empty guard with inline validation. **Layout and dimensions:** preserve the current terminal rail and submit affordance; maintain a minimum 44×44px interactive area for the submit button and visible focus. **Typography:** preserve mono command treatment; input text must remain at least 16px on mobile to prevent unwanted zoom. **Color:** use neutral/amber validation semantics for empty input, not red engine failure. **Interaction:** Enter and submit button share the same guard; valid non-empty behavior remains unchanged. **Responsive:** sticky/safe-area behavior remains; validate with keyboard. **States:** empty, focused, invalid-empty, valid-ready, processing only if supported, success, syntax error. **Accessibility:** explicit label, live inline correction, no success announcement for a no-op. **Preserve:** terminal-first composition and command vocabulary. **Reject:** silent defaults and autocomplete unless separately approved.

### F.2 Coach panel

**Current state:** Persistent panel with guidance, current system response, next move, and collapse control. **Problem:** fabricated first-use error and possible competition with terminal context. **Decision:** neutral zero-history state; subordinate support; assessment boundary state. **Layout:** desktop may remain a rail beside the Terminal only if the Terminal retains primary visual weight; mobile remains below or collapsible after validation. **Spacing:** use a compact message stack and avoid covering terminal output. **Typography/color:** error color only for a real failed entry; neutral ready state uses standard muted/green operational text. **Interaction:** collapse must be keyboard reachable; if a drawer or dialog pattern is adopted, add focus management and Escape. **States:** awaiting command, guidance available, latest success, latest error, assessment hints suppressed, unavailable. **Preserve:** “Guidance without shortcuts” and the next useful move. **Reject:** a new FAB or bottom sheet without evidence that the current subordinate pattern fails.

### F.3 Terminal header and status line

**Current state:** Header shows emulator title, session/command/log readout, Reference, and Focus. **Problem:** status is distributed and some mobile visibility/cascade claims conflict. **Decision:** retain one concise, persistent status summary in the Terminal body or header on mobile. **Layout:** preserve compact top header; do not overload it with every metric. **Content:** mode, session state, command state, log count, and next move should be available within one scan. **Accessibility:** status text cannot rely on color only. **Validation:** confirm final cascade and real mobile render rather than trusting an isolated CSS declaration.

### F.4 Mode tabs and segmented controls

**Current state:** Learn, Practice, Assessment; metric switcher; Growth tabs; scenario filters; track selectors. **Problem:** visual selection is not consistently exposed semantically. **Decision:** choose semantics based on control behavior: true tabs use tablist/tab/tabpanel; mutually exclusive view switches may use `aria-pressed` toggle buttons or a radio group. **Layout:** preserve existing compact segmented visuals. **Interaction:** keyboard arrow behavior should be added only for true tabs; selection must be announced. **States:** default, selected, focus, disabled, unavailable. **Preserve:** compact console appearance. **Reject:** adding ARIA roles without matching keyboard behavior.

### F.5 Progress indicators and rings

**Current state:** SVG progress rings have labelled image semantics; tiny bars use decorative elements. **Problem:** small bars are not exposed as progress semantics and some totals may be hardcoded. **Decision:** preserve rings and chart/table pattern; add semantic progress where a bar represents a measurable value. **Content:** derive maximum and current values from the same dataset or mark illustrative. **Accessibility:** expose value in text and semantics; do not rely on color. **Risk:** over-annotating decorative bars can create noise, so only data-bearing bars receive progress roles.

### F.6 Buttons, toasts, and action controls

**Current state:** compact Ghost, Primary, text, icon, and toast-backed controls. **Problem:** some buttons imply navigation, filtering, backup, or language change while performing only a toast. **Decision:** action inventory with implement/relabel/remove disposition. **Dimensions:** preserve the visual scale but validate 44×44px touch areas for icon-only controls; the visual glyph may remain smaller inside the hit area. **Feedback:** successful toast only after a real operation; informational preview message for unavailable features. **Accessibility:** accessible name, focus-visible outline, disabled state when unavailable, no color-only result. **Preserve:** compact utility language. **Reject:** “success” messages for no-ops.

### F.7 Growth Record surfaces

**Current state:** Record, History, and Reports tabs; latest evidence notice; learning-loop strip; pattern report; targeted Practice CTA. **Problem:** provenance and count mismatches; Backup false affordance. **Decision:** preserve all three views and their hierarchy, fix numbers and action honesty. **Layout:** keep latest evidence and next action above secondary detail. **Interaction:** History rows should either open a real related view or be labeled informational. **Accessibility:** tabs expose selection; readout values have text alternatives; learning-loop step state is not color-only. **Preserve:** pattern-oriented “what is reliable / what recurs / what next?” structure. **Reject:** merging the whole surface into a single KPI dashboard.

### F.8 Progress Tracking chart and history

**Current state:** KPI readouts, metric switcher, bars, data table, session history, targeted practice CTA. **Decision:** preserve the same-data chart/table architecture. **Problem:** metric ownership and trend desirability can be ambiguous. **Interaction:** metric switcher updates both chart and table; selected state is semantic. **Accessibility:** table remains available without requiring chart interpretation; trend arrow is accompanied by text such as “up, which is favorable for this metric” only when the metric definition supports that conclusion. **Preserve:** accessible data-table fallback. **Reject:** chart-library migration without a requirement.

### F.9 Scenario list and mission detail

**Current state:** summary metrics, filter tabs, sort select, scenario cards, selected mission detail, Resume/Start/Review CTA. **Problem:** summary metrics do not reconcile with visible dataset; sort may toast without changing order; scenario-to-Practice handoff is title-based. **Decision:** derive or label metrics; wire sort if retained; pass stable scenario context. **Layout:** preserve selected detail and mission-file structure. **Accessibility:** filter state and selected card must be announced; cards must have a logical button/name structure. **Preserve:** difficulty, duration, type, skills, next operational move, and Coach readout. **Reject:** adding map functionality solely to satisfy “View map.”

### F.10 Navigation shell and overlays

**Current state:** mobile top bar, bottom rail, desktop-intended side nav, menu/search/profile utilities. **Problem:** missing landmark/skip semantics and unproven overlay focus contract. **Decision:** add main landmark and skip link; validate or implement focus trap, Escape, return focus, and dialog semantics for actual overlays. **Preserve:** five-area shape and central Train emphasis. **Reject:** IA consolidation based only on metric similarity.

---

## G. Screen and Flow Changes

### G.1 Progression

**Current issue:** `3 / 8 stages` conflicts with the six visible level entries and the screenshot’s stage map; My route and See all stages may be toast-only. **Decision:** derive the numerator/denominator from the actual curriculum array or state “3 of 6 available in this preview”; mark future curriculum separately if a larger total is planned. The hierarchy remains hero route → learning path → track choice → stage map. Track selection must either change content or be labelled preview/roadmap. The Resume CTA continues to open Practice with context. At 320–430px, keep the current route card and stage-map scan order.

### G.2 Practice / Terminal

**Current issue:** empty submit, fabricated first-use error, sample accuracy/footer metrics, fragmented status, and unproven keyboard behavior. **Decision:** apply P0 safety and Coach fixes first, then implement the state matrix and validate mobile. Keep Learn/Practice/Assessment, local-simulation disclosure, Focus Mode concept, command history, and scoring. In Assessment, preserve a compact `HINTS SUPPRESSED` boundary and a clear Finish Session state. Do not add a new route or alter command semantics.

### G.3 Scenarios

**Current issue:** `23 / 40` and `Exchanges & Refunds` may not match the five visible scenarios or the source data; Filters and Sort need action truth. **Decision:** derive from the scenario array and category data, or clearly mark sample preview values. Keep filter tabs if they change the list; if Sort is a no-op, relabel or remove it. The selected mission detail remains the central task explanation, and Resume/Start/Review continues to hand off to Practice with stable context.

### G.4 Growth Record

**Current issue:** Backup claims a created backup point; History shows `LOG 04 / 12` while three rows render; reports and record values may be seeded. **Decision:** preserve Record/History/Reports, the latest evidence notice, and learning-loop strip. Derive `LOG` from actual event count or state that it is a preview sample. Make Backup read `Local preview — backup unavailable` unless a real artifact exists. Keep the next-action CTA and make its evidence source explicit.

### G.5 Progress Tracking

**Current issue:** strong chart/table structure, but KPI provenance, trend desirability, and semantic switch state need hardening. **Decision:** preserve the screen and its data-table alternative. Ensure chart and table consume the same records. Derive session count and average from records; distinguish sample seed records from live local records. Keep the targeted Practice CTA. Do not merge the screen into Growth without user-task evidence.

### G.6 Cross-screen learning flow

The current handoffs are among the prototype’s most valuable behaviors. Preserve Progression → Practice, Scenario → Practice, Growth → Practice, and Tracking → Practice. Add a stable handoff object rather than a bare title, and display a short provenance line such as `OPENED FROM / SC-014 · GROUP BOOKING` or `RECOMMENDED FROM / EV-041`. This is a UI traceability improvement, not a new feature. The actual curriculum and engine mapping remain outside this audit’s authority.

---

## H. Responsive, Accessibility, and State Requirements

### H.1 Responsive requirements

| Surface | Required behavior | Test |
|---|---|---|
| Desktop, ≥1100px | Preserve sidebar, terminal-first primary column, and subordinate Coach rail. No dashboardization. | Visual comparison at 1280 and 1440px; inspect reading order and focus order. |
| Tablet, 740–1099px | Determine whether hybrid sidebar/bottom-rail behavior is intentional and legible. Do not assume CSS inference is sufficient. | Render at 768, 834, and 1024px; record navigation identity, column widths, and overflow. **NEEDS VALIDATION.** |
| Mobile, 390/430px | Preserve top bar, bottom rail, sticky command input, safe-area spacing, and visible terminal status. | Physical or emulated keyboard-open test; last response and submit control remain visible. |
| Narrow mobile, 320/360px | Preserve terminal header restructure and avoid clipped title, status, or input. | Screenshot and interaction test at both widths; no horizontal scroll. |
| Reduced motion | Preserve global and component-specific reduced-motion behavior, including terminal caret and smooth scrolling. | `prefers-reduced-motion: reduce` test with focus, tab changes, and terminal history. |

### H.2 Interaction-state requirements

Every interactive control must have a visible and semantic default, hover where applicable, focus, active/pressed, disabled/unavailable, and error/success response. A no-op must not be represented as success. A transient toast cannot be the only evidence of a state change. State meaning must be conveyed by text, icon, structure, or a combination; color is supplemental.

### H.3 Terminal state requirements

| State | Required visible contract |
|---|---|
| Empty / first use | Awaiting command; no error; no false accuracy; no history event. |
| Focused | Input focus visible; Focus Mode status exposed; Escape behavior defined if modal-style focus is used. |
| Processing | Only show if the local model actually has a processing state; do not simulate engine latency solely for realism. |
| Success | Command, response, and next useful move; success text and non-color marker. |
| Syntax error | Error belongs to the submitted command; show corrective guidance without inventing a real engine response. |
| Recoverable error | Explain recovery path and preserve user context; no silent reset. |
| Assessment active | Hints boundary explicit; score not shown as final until closure; Finish Session state clear. |
| Assessment complete | Persist only an intentional completed session; show local evidence provenance and next action. |
| Interrupted / unavailable | State what is unavailable and whether retry is safe; do not claim completion. |

### H.4 Loading, empty, and error requirements for other screens

Growth and Tracking must show an honest no-evidence state when no local records exist. Scenarios must show an empty filtered state if a filter produces no results. Chart and history views must distinguish “no data” from “data unavailable” and from “illustrative sample.” Route and stage views must distinguish locked because of curriculum state from unavailable because the preview lacks data. These states should use the existing console language rather than generic consumer-app skeletons unless loading behavior is actually required.

### H.5 Accessibility requirements

The enhanced prototype must include a skip link, a main landmark, semantic selection state for segmented controls, progress semantics for data-bearing bars, visible focus, logical keyboard order, accessible names for icon controls, and non-color state cues. Drawers, dialogs, and mobile menus require focus entry, focus containment where appropriate, Escape dismissal, and focus return. Route changes should expose the new page heading to assistive technology without stealing focus from active command entry. Zoom must remain available. Final contrast, touch-target, and screen-reader behavior are **NEEDS VALIDATION** in a real or accurately emulated runtime.

### H.6 Provenance requirements

Every value shown as performance, readiness, completion, average, trend, or evidence must identify its data owner. A minimal visual grammar is:

| Provenance | Meaning | Example treatment |
|---|---|---|
| `LOCAL` | Stored in this browser/session. | `LOCAL · 3 READOUTS` |
| `CALCULATED` | Derived from current local records or arrays. | `CALCULATED FROM SESSION LOG` |
| `ILLUSTRATIVE` | Sample content supplied for the preview. | `ILLUSTRATIVE · LOCAL PREVIEW` |
| `HISTORICAL` | A prior record with a stated date/period. | `HISTORICAL · 2 DAYS AGO` |
| `AUTHORITATIVE` | Only when backed by a defined external/engine source. | Do not use in current preview without a source. |

---

## I. Explicit Rejection List

| ID | Rejected Recommendation | Source | Reason for Rejection | Future Validation Needed? |
|---|---|---|---|---|
| RJ-01 | Redesign AeroBridge from scratch or replace the Flight Deck Console. | Some broad polish recommendations across audits [13]–[21] | Contradicts `ideas.md`, discards the strongest product asset, and is unsupported by the evidence. | No. |
| RJ-02 | Merge Growth Record and Progress Tracking into one new analytics route. | Gemini and related IA suggestions [16] | Similar metrics do not prove identical user jobs; merging would damage the evidence-to-action and trend distinctions. | Yes, only if task research later shows users cannot locate evidence. |
| RJ-03 | Add a map or activate `MapView` because “View map” exists. | Kimi, DeepSeek, Qwen discussions [15] [17] [20] | The extracted import trace shows no running map surface, and the product intent does not require geographic mapping. | Only if curriculum owners define a map-dependent learning task. |
| RJ-04 | Add command autocomplete or alter command evaluator/scoring logic. | Suggestions appearing in audit discussions [13] [15] | Conflicts with recall-based training and the explicit boundary against inventing engine behavior. | Only with pedagogical and engine-owner evidence. |
| RJ-05 | Add Pause/Resume as an engine-level state. | Audit proposals [15] [17] | UI cannot invent a state the local model does not define. Scenario Resume is different and already exists. | Requires engine/state specification. |
| RJ-06 | Add a mobile FAB or bottom sheet for Coach immediately. | Conflicting audit recommendations [13] [15] [16] | It adds interaction surface and may compete with the terminal; current evidence supports subordinate Coach, not a specific replacement. | Yes: compare current, collapsed, and sheet patterns with task testing. |
| RJ-07 | Migrate the current chart to Recharts solely for polish. | Audit disagreement summarized in [13] [14] | Existing chart has a same-data accessible table; no richer interaction requirement is proven. | Only if future chart requirements exceed the current implementation. |
| RJ-08 | Add gamification, badges, streaks, or consumer-style achievement layers. | Against the original intent [1] | Conflicts with professional aviation-training positioning and would increase noise. | No. |
| RJ-09 | Treat every repeated audit claim as independently proven. | Master prompt [12] | Violates the evidence hierarchy; the audits largely share the same source and screenshots. | No. |
| RJ-10 | Change visual state to “production-ready” after cosmetic polish only. | Implied by high visual scores in Kimi [15] | P0 trust defects remain even when screenshots look premium. | No; fix evidence and safety first. |

---

## J. Validation Plan

### J.1 Blank-command safety and assessment integrity

**Decision being tested:** empty submission is a no-op. **Objective:** prove that a blank or whitespace-only entry cannot create evidence. **Method:** automated component test plus manual Practice and Assessment runs. **Measure:** history length, command count, `LOG`, score, localStorage writes, toast events, focus retention, and inline announcement. **Success criteria:** all remain unchanged except the visible correction. **Recommendation changes if:** the product owner explicitly defines blank submission as a valid command, which would conflict with the current command vocabulary and must be documented as an engine decision rather than assumed.

### J.2 First-use Coach state

**Decision being tested:** no red error before a real failed command. **Objective:** align Coach and Terminal state. **Method:** fresh browser session, screenshot comparison, keyboard navigation, and one invalid command afterward. **Measure:** rendered copy, semantic state, color/state marker, and focus. **Success criteria:** neutral awaiting state on first use; real syntax error appears only after invalid entry. **Recommendation changes if:** the local training model intentionally defines a preloaded error scenario; no evidence currently supports that assumption.

### J.3 Provenance and metric reconciliation

**Decision being tested:** each metric has a single owner and visible provenance. **Objective:** eliminate contradictions between summary numbers and detail arrays. **Method:** static audit of every numeric literal in UI copy plus seeded/localStorage data-flow test. **Measure:** numerator/denominator equality, current-session behavior, seed labeling, and date/period. **Success criteria:** no unlabeled hardcoded trainee evidence; every count either equals its source array or explicitly says illustrative/available-now. **Recommendation changes if:** content owners provide an authoritative larger curriculum dataset that explains the denominators and the UI can bind to it.

### J.4 Toast and affordance audit

**Decision being tested:** every success claim corresponds to a real action. **Objective:** remove false affordances. **Method:** click-through inventory of all buttons, links, selects, and icon controls; compare intended label, state mutation, navigation, and persistence. **Measure:** action completion, destination, mutation, and announcement. **Success criteria:** real operation, honest unavailable label, or removed control for every item. **Recommendation changes if:** a product owner approves a preview-only action with explicit copy and neutral feedback.

### J.5 Mobile Terminal and keyboard behavior

**Decision being tested:** the Terminal remains operable at 320/360/390/430px with the keyboard open. **Objective:** keep the active command, latest response, submit control, and status visible. **Method:** physical Android/iOS testing or equivalent device emulation with default keyboards, portrait orientation, and reduced-height viewport. **Measure:** visible work surface height, occlusion, scroll position, tap success, input focus, safe-area spacing, and ability to recover from errors. **Success criteria:** no horizontal scroll; command input and submit remain reachable; latest relevant response can be read without losing the active entry. **Recommendation changes if:** testing proves the current arrangement fails consistently; then compare flexible gap, compact status, and a tested collapsible Coach pattern.

### J.6 Typography, contrast, and zoom

**Decision being tested:** the declared fonts load and meaningful text meets readability requirements. **Objective:** preserve console identity while supporting long sessions and low-vision users. **Method:** inspect network/computed styles in the hosted preview, run automated contrast checks at final rendered sizes, and test browser zoom to 200%. **Measure:** loaded font family, fallback occurrence, contrast ratio, text clipping, and reflow. **Success criteria:** declared families or documented shipped fallback; meaningful text passes the chosen WCAG target; zoom does not remove content or functionality. **Recommendation changes if:** final metrics show the current palette passes at actual sizes; then retain tokens and limit changes to the failing elements.

### J.7 Keyboard, screen reader, and overlay semantics

**Decision being tested:** selected states, landmarks, progress, dialogs, and route changes are operable. **Objective:** ensure the console is not only visually accessible. **Method:** keyboard-only pass, NVDA/VoiceOver/TalkBack equivalent, and automated accessibility scan. **Measure:** landmark discovery, skip link, tab selection, progress announcement, focus entry/return, Escape dismissal, live-region clarity, and no focus loss. **Success criteria:** all primary flows complete without a pointer and state meaning is announced. **Recommendation changes if:** a tested platform exposes an equivalent semantic pattern with lower implementation risk; document the deviation.

### J.8 Desktop/tablet composition

**Decision being tested:** the inferred sidebar, Coach rail, and hybrid tablet state are coherent. **Objective:** prevent mobile-first screenshots from hiding desktop structural problems. **Method:** render at 768, 834, 1024, 1280, and 1440px, then perform task walkthroughs. **Measure:** navigation identity, terminal/Coach ratio, content width, overflow, reading order, and action discoverability. **Success criteria:** Terminal remains primary, Coach subordinate, no clipped route or utility controls, and all five areas remain understandable. **Recommendation changes if:** tablet hybrid navigation creates confusion; then choose a single tested tablet navigation identity rather than adding another route.

### J.9 Arabic/RTL release scope

**Decision being tested:** whether Arabic is active in the next release. **Objective:** prevent a cosmetic language promise. **Method:** product decision plus bounded prototype test covering `dir="rtl"`, Cairo, mixed LTR command strings, dates, numbers, icons, and navigation. **Measure:** translation coverage, bidi integrity, focus order, layout mirroring, and command readability. **Success criteria:** either a real bounded RTL contract passes, or the UI clearly labels AR as roadmap/preview and does not claim that language has been set. **Recommendation changes if:** product ownership funds and supplies translation/content scope.

---

## K. Implementation Handoff

The implementation team should begin with the four P0 changes and treat them as a trust hardening release, not a visual refresh. First, guard the Terminal submit path. Second, make the Coach state conditional on real history. Third, reconcile or label every metric. Fourth, inventory and disposition every action that currently relies on a toast. These changes should be implemented without changing command prefixes, command matching, scoring formula, localStorage record shape, route sequence, or the visual identity.

Next, implement the shared accessibility and state foundation. Add the main landmark and skip link, correct selection semantics, add progress semantics only to data-bearing indicators, preserve the chart table, improve non-color state cues, and define overlay focus behavior. The implementation should use the actual behavior of each control rather than copying one ARIA pattern to every segmented control.

Then validate typography, contrast, viewport zoom, and mobile behavior. Do not make final claims about fonts, keyboard overlap, exact touch targets, or screen readers from static CSS alone. Record test results as evidence and update the open-question register before promoting the prototype to the next approval state.

The handoff must include a regression checklist covering: blank submit, valid command sequences, unknown command syntax error, Learn→Practice→Assessment transitions, hints in and out of Assessment, Finish Session persistence, Growth/Tracking update, Scenario→Practice context, route navigation, mobile menu, Reference drawer, Focus Mode, reduced motion, browser zoom, and no false success toast. Any change outside this approved scope should be documented as a new decision rather than smuggled into the hardening pass.

---

## L. Open Questions and Assumptions

| ID | Question / Assumption | Why it matters | Decisions affected | Information or validation needed |
|---|---|---|---|---|
| OQ-01 | Are the larger denominators (`8`, `40`, `12`, `210`) intended future curriculum totals or accidental presentation literals? | Determines whether to derive, relabel as available-now, or bind to a real dataset. | MD-03, MD-04, P0-03 | Product/content owner statement and dataset inventory. |
| OQ-02 | Are seeded records intended to represent a local demo baseline or the current trainee’s evidence? | Controls whether scores are shown as sample, historical, or live local. | MD-03, Growth, Tracking | Persistence contract and fresh-session behavior test. |
| OQ-03 | Should Arabic be released in this milestone? | Determines whether AR is a real i18n/RTL feature or roadmap copy. | MD-12, P1-03, J-9 | Release scope, translation resources, bidi requirements. |
| OQ-04 | What is the authoritative definition of “Saudi readiness”? | Prevents unsupported readiness claims. | Provenance, Progression, Reports | Product/content definition and evidence owner. |
| OQ-05 | Does opening Reference count as a hint in every mode? | Affects assessment fairness and displayed hint discipline. | Terminal state, scoring disclosure, P1-01 | Engine/content contract and mode tests. |
| OQ-06 | Should Practice mode enforce command sequence or only Assessment? | Affects whether a successful local response means format correctness or workflow correctness. | State semantics, scoring explanation | Pedagogical decision and command-model specification. |
| OQ-07 | What is the intended behavior for processing, interruption, and retry? | The UI must not invent states the local model cannot support. | P1-01, H.3 | Engine boundary specification or explicit preview limitation. |
| OQ-08 | Is the pre-seeded session timer a resumed local session or decorative sample content? | Affects continuity and trust. | Practice footer provenance | Fresh/resumed session behavior and persistence contract. |
| OQ-09 | Which overlay surfaces are true dialogs/drawers versus inline panels? | Determines focus trap, Escape, and return-focus requirements. | MD-09, F.2, F.10 | Interaction inventory and keyboard test. |
| OQ-10 | Does the hosted environment actually serve the referenced `/manus-storage/...` assets and analytics variables? | Affects self-contained behavior and build/runtime reliability. | Visual fidelity, deployment handoff | Hosted smoke test and build log. |
| OQ-11 | Is the current tablet hybrid navigation intentional? | Mobile screenshots do not establish 740–1099px behavior. | H.1, J.8 | Render and task test at 768/834/1024px. |
| OQ-12 | Are all current screenshot values expected to remain for presentation purposes? | Prevents a UI-only fix from deleting required preview storytelling. | P0-03, Growth, Tracking | Content-owner review of sample-data policy. |

**Assumptions used in this audit:** The extracted ZIP is the authoritative prototype artifact for this review; the seven supplied screenshots represent intended visual reference states; the project remains presentation-first; no backend or real engine should be introduced by this pass. These assumptions are explicitly bounded by the original `ideas.md` and the master prompt [1] [12].

---

## M. Final Recommendation

### Implement

Implement blank-submit safety, the neutral first-use Coach state, a coherent provenance contract, count reconciliation, honest affordance handling, viewport zoom restoration, semantic landmarks and selection state, progress semantics, non-color state cues, and a canonical Terminal state contract that does not invent engine truth. Preserve local simulation disclosure and ensure assessment persistence occurs only after intentional completion.

### Preserve

Preserve the Flight Deck Console identity, deep-navy/Vector Blue palette, operational color language, monospace command/readout treatment, terminal-first Practice hierarchy, Learn/Practice/Assessment structure, Focus Mode concept, five-area navigation, Progression → Practice and Scenario/Growth/Tracking handoffs, Growth’s learning-loop pattern, Progress Tracking’s same-data chart/table alternative, reduced-motion support, and presentation-first local preview boundary.

### Defer

Defer full Arabic/RTL implementation until release scope, translation coverage, bidi behavior, and testing are available. Defer new global analytics/dashboard architecture, Coach FAB/bottom-sheet replacement, Recharts migration, custom scrollbar work, animation expansion, map activation, and any engine-level state invention. These may be revisited only with new evidence.

### Reject

Reject redesign from scratch, gamification, command autocomplete, unsupported Pause/Resume engine semantics, map activation solely because of a dead affordance, automatic Growth/Tracking merger, and any recommendation that changes command evaluation, scoring, localStorage schema, or product identity without a separate approved decision.

### Validate

Validate keyboard-open mobile behavior at 320/360/390/430px, desktop/tablet composition, actual font loading, contrast at rendered sizes, browser zoom/reflow, touch targets, screen-reader output, overlay focus contracts, the processing/interruption model, hint accounting, seeded-data ownership, and Arabic/RTL scope. These are not reasons to delay the P0 fixes; they are reasons not to overclaim completion.

**Final stage decision:** The current evidence is sufficient to move into the next design-refinement stage with the P0 and confirmed P1 implementation work. The product should not be approved as production-ready until the trust fixes are implemented and the validation items above are documented. The correct posture is therefore **Preserve and Refine — Implement the evidence/safety hardening, preserve the identity and learning loop, defer unsupported expansion, reject redesign, and validate the runtime boundaries before final approval.**

---

## References

[1]: file:///home/ubuntu/aerobridge_source/aerobridge-share-preview/ideas.md "AeroBridge Design Ground Truth"
[2]: file:///home/ubuntu/aerobridge_source/aerobridge-share-preview/client/src/App.tsx "AeroBridge App.tsx"
[3]: file:///home/ubuntu/aerobridge_source/aerobridge-share-preview/client/src/index.css "AeroBridge index.css"
[4]: file:///home/ubuntu/aerobridge_source/aerobridge-share-preview/client/src/pages/Home.tsx "AeroBridge Home.tsx"
[5]: file:///home/ubuntu/aerobridge_evidence_ledger.txt "Direct source evidence ledger"
[6]: file:///home/ubuntu/upload/55519.jpg "Practice / Terminal screenshot"
[7]: file:///home/ubuntu/upload/55517.jpg "Scenarios screenshot"
[8]: file:///home/ubuntu/upload/55514.jpg "Progression screenshot"
[9]: file:///home/ubuntu/upload/55521.jpg "Growth Record / Record screenshot"
[10]: file:///home/ubuntu/upload/55526.jpg "Growth Record / History screenshot"
[11]: file:///home/ubuntu/upload/55528.jpg "Growth Record / Reports screenshot"
[12]: file:///home/ubuntu/upload/MASTERSYNTHESISAUDITPROMPT.md "Master Synthesis Audit Prompt"
[13]: file:///home/ubuntu/upload/ClaudeAeroBridge_Unified_Master_Design_Audit.md "Claude Unified Master Design Audit"
[14]: file:///home/ubuntu/upload/Chatgpt_AEROBRIDGE_UNIFIED_MASTERAUDIT.md "ChatGPT Unified Master Design Audit"
[15]: file:///home/ubuntu/upload/DEEPSEEKAEROBRIDGE—UNIFIEDMASTERDESIGNAUDIT.md "DeepSeek Unified Master Design Audit"
[16]: file:///home/ubuntu/upload/GeminiAEROBRIDGE—UNIFIEDMASTERDESIGNAUDIT.md "Gemini Unified Master Design Audit"
[17]: file:///home/ubuntu/upload/GrokAEROBRIDGE—UNIFIEDMASTERDESIGNAUDIT.md "Grok Unified Master Design Audit"
[18]: file:///home/ubuntu/upload/kimiAEROBRIDGE—UNIFIEDMASTERDESIGNAUDIT.md "Kimi Unified Master Design Audit"
[19]: file:///home/ubuntu/upload/Manus_AEROBRIDGE_UNIFIED_MASTER_DESIGN_AUDIT.md "Manus Unified Master Design Audit"
[20]: file:///home/ubuntu/upload/qwenAEROBRIDGE—UNIFIEDMASTERDESIGNAUDIT.md "Qwen Unified Master Design Audit"
[21]: file:///home/ubuntu/upload/v0AEROBRIDGE—UNIFIEDMASTERDESIGNAUDIT.md "v0.dev Unified Master Design Audit"
[22]: file:///home/ubuntu/aerobridge_css_evidence.txt "Extracted CSS evidence excerpt"
[23]: file:///home/ubuntu/aerobridge_source/aerobridge-share-preview/client/index.html "AeroBridge index.html"
[24]: file:///home/ubuntu/upload/55523.jpg "Progress Tracking screenshot"

---

## Final quality checklist

| Requirement | Status |
|---|---|
| Original prototype and screenshots evaluated | Complete |
| All 9 Unified Audits considered | Complete |
| Agreements and disagreements identified | Complete |
| No majority voting used | Complete |
| Every MUST FIX has evidence and reason | Complete |
| Preservation decisions explicit | Complete |
| Rejections documented | Complete |
| Confirmed decisions separated from validation | Complete |
| Component, screen, state, responsive, and accessibility implications addressed | Complete |
| Unsupported functionality not invented | Complete |
| Technical feasibility, cost, risk, and confidence considered | Complete |
| Unavailable/uncertain evidence identified | Complete |
| Required A–M structure present | Complete |
