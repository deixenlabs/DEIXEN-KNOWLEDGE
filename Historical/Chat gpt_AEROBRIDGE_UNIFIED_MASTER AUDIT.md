# AEROBRIDGE — UNIFIED MASTER DESIGN AUDIT

**Role:** Principal Product Designer + UX Architect + UX Auditor + Design Systems Strategist + Interaction Designer + Accessibility Reviewer + Product Adjudicator + Evidence Analyst

**Design Status:** **NEEDS TARGETED REVISION**

**Decision posture:** Preserve the existing AeroBridge visual and product foundation. Do not redesign from scratch. The next revision must make the workstation more trustworthy, more explicit about evidence provenance, more state-complete, more accessible, and more robust on narrow devices without turning it into a dashboard, LMS, or gamified analytics product.

**Master principle:** **The UI may interpret engine state, but it must never invent engine truth.**

---

## 1. EXECUTIVE VERDICT

### What is already strong

AeroBridge already has the hardest thing to manufacture: a recognizable product identity that is aligned with its domain. The Flight Deck Console language—deep navy, Vector Blue interaction accents, green/amber/red operational semantics, monospace command/readout treatment, restrained atmospheric imagery, compact operational metadata, persistent desktop navigation, and a centered mobile Practice destination—reads as aviation training software rather than a generic SaaS dashboard.

The core learning loop is also real rather than decorative. Progression can open Practice with context, Scenarios can inject scenario context into Practice, Assessment can create persisted local records, Growth and Tracking can read those records, and those screens can return the trainee to targeted Practice. This is a genuine product spine and should be protected.

The Terminal is the product's most differentiated surface. It already contains command input, history recall, Learn/Practice/Assessment modes, Reference, Coach, Focus Mode, session readouts, assessment debrief, and a clearly stated local/illustrative response boundary. The Focus Mode and deliberate mobile command-input treatment are especially strong.

Growth Record also contains a high-value learning pattern: **read evidence → practice the gap → apply in scenario**. This is more educationally meaningful than generic achievement dashboards.

Progress Tracking contains another strong pattern: the visual chart has a real table alternative sourced from the same data, so accessible representation is not merely a separate hardcoded summary.

### What is weak

The dominant weakness is not aesthetics. It is **trust and operational truthfulness**.

The current prototype repeatedly presents things that look authoritative even when the underlying state is illustrative, hardcoded, partial, or not actually implemented. Examples include hardcoded scenario totals, stage totals, readiness-style language, a seeded session clock, a pre-command accuracy value, a hardcoded “Saudi readiness” value, and controls that announce actions which did not actually happen. The Terminal is especially sensitive because command behavior, coaching, scoring, hints, and evidence can influence a trainee's mental model of a real operational workflow.

The second weakness is **state incompleteness**. The source declares a richer state vocabulary than the visible UI consistently implements. The Terminal needs clearer handling for ready, processing, success, partial success, error, recovery, interruption, assessment-active, assessment-complete, and completed/persisted states. Other routes need honest empty/unavailable/locked/review states as well.

The third weakness is **accessibility and long-session readability**. The visual system relies heavily on very small metadata labels; some muted text fails measured or inferred contrast thresholds; tab-like controls do not consistently expose selection semantics; overlays lack complete focus management; and the current source architecture has no explicit main landmark or skip link.

The fourth weakness is **design-system drift**. `index.css` contains a strong token foundation, but later refinement passes add a second `--ab-*` token family, repeated overrides, special-case gradients, and multiple radius/spacing values. The current CSS still works, but it is becoming harder to maintain as the real curriculum is introduced.

The fifth weakness is **mixed-language readiness**. EN/AR exists visibly, but the current behavior is cosmetic. A true Arabic experience would require actual content/localization scope, document direction, mixed-direction rules, Arabic typography, and preservation of LTR command syntax. The interface must not imply that an Arabic switch exists operationally when it does not.

### What matters most

The product should be optimized around one idea:

> **Make the Terminal calm, truthful, state-complete, and easy to operate—then make every other screen explain what the trainee should do next.**

The product does **not** need more features to feel premium. It needs fewer misleading affordances, more explicit state semantics, stronger evidence provenance, better typography, and disciplined responsive behavior.

### What must change

1. Remove the fabricated first-use Terminal error.
2. Make empty command submission a true no-op with inline correction; it must never silently execute `FQD`.
3. Establish one evidence/provenance grammar for all local, calculated, illustrative, historical, and authoritative information.
4. Replace or honestly relabel controls that only fire toasts when they visually promise navigation, filtering, backup, language change, or sorting.
5. Define a canonical Terminal state model and visibly represent the states that matter.
6. Make Assessment mode behavior explicit, especially when prior command history or hints carry across modes.
7. Fix typography provisioning and readability; do not solve accessibility by making the entire workstation look like a consumer app.
8. Complete core accessibility semantics: selected state, progress indicators, landmarks, overlay focus, route focus, non-color state cues.
9. Consolidate the design-token system before more refinement passes accumulate.
10. Validate 320/360/390/430, 768/834/1024, laptop, and desktop behavior on real devices/browsers.

### What must not change

- Flight Deck Console identity.
- Terminal-first hierarchy.
- The five-area product shape.
- Progression → Practice context handoff.
- Scenario → Practice context handoff.
- Growth → targeted Practice pattern.
- Tracking → Practice connection.
- Learn / Practice / Assessment structure.
- Focus Mode concept.
- Monospace treatment for command/readout material.
- Green/amber/red operational language.
- Local/illustrative simulation disclosure.
- Existing command vocabulary and assessment scoring logic unless separately approved as an Engine/Data decision.

### Overall design direction

**More precise, not more decorative. More operational, not more dashboard-like. More trustworthy, not more “finished-looking.”**

---

## 2. SOURCE COVERAGE & EVIDENCE OVERVIEW

### 2.1 Materials reviewed

#### Audit set: 9 supplied audits

1. `chatgpt audit .md`
2. `Claude audit.md`
3. `deepseek audit.md`
4. `gimini audit.md`
5. `grok audit.md`
6. `kimi.md`
7. `Manus audit.md`
8. `qwen audit.md`
9. `v0.dev audit.md`

The audits were treated as **analytical evidence**, not as primary truth. Repetition was not counted as independent proof when the audits were evaluating the same source and screenshot set.

#### Prototype source set: 8 uploads, 7 unique files

The user supplied `const.ts` twice by mistake. The unique source set is:

- `Home.tsx`
- `index.css`
- `App.tsx`
- `Map.tsx`
- `index.ts`
- `ideas.md`
- `const.ts`

The duplicate `const.ts` upload adds no independent evidence.

#### Rendered evidence: 7 screenshots

The screenshot set visibly covers the major product surfaces and states:

- Progression
- Practice / Terminal
- Scenarios list and scenario detail
- Growth Record / Record
- Growth Record / History
- Growth Record / Reports
- Progress Tracking

The renders are especially valuable for mobile composition, hierarchy, card density, and the actual visual expression of the Terminal, Growth, Tracking, Scenario, and Progression states.

#### Supporting instruction/specification

`aduits prompt.md` was treated as the adjudication protocol. It explicitly requires evidence weighting, conflict resolution, source traceability, semantic de-duplication, preservation of minority insights when justified, responsive and accessibility synthesis, and implementation-ready decisions.

`ideas.md` is the design ground truth and explicitly states that this is a **reference-preservation project, not a redesign**; it requires preserving the Flight Deck Console, terminal-first surface, mobile command rail, existing product sequence, and local/mock visibility.

### 2.2 Evidence hierarchy used

- **E4 / Directly Verified:** current supplied source or rendered screenshot visibly proves the claim.
- **E3 / Independently Corroborated:** materially different evidence sources support the claim, such as source + screenshot or source + an independently derived static analysis.
- **E2 / Corroborated:** multiple audits or analyses support the claim, but the underlying evidence is substantially shared.
- **E1 / Repeated Claim:** multiple audits say the same thing, but it is not independently proven.
- **E0 / Single Claim:** a single unsupported or weakly supported claim.

Audit consensus is recorded separately from evidence strength. High repetition can increase confidence in **where to look**, but it cannot upgrade a claim beyond the quality of its underlying evidence.

### 2.3 Important evidence limitations

The currently supplied source set does **not** include `index.html`, `ErrorBoundary.tsx`, `NotFound.tsx`, or the actual asset files referenced through `/manus-storage/...`. Several audits inspected those artifacts in an earlier source package and reported findings from them. Those findings remain analytically useful, but they are not re-verified against the currently uploaded artifact set and are marked accordingly.

The current source also cannot prove physical-device behavior such as actual on-screen-keyboard overlap, real touch-target ergonomics, rendered font metrics, or actual screen-reader speech. Those require explicit device validation.

### 2.4 Source/artifact coverage judgment

Coverage is high for the current presentation layer: the main application shell, all five primary views, CSS, state logic, navigation, local persistence, the route/learning ground truth, and the rendered mobile states are all represented.

Coverage is incomplete for production integration boundaries: actual document-level font loading, actual i18n infrastructure, the real engine, authoritative curriculum data, production error/404 surfaces, and hosted asset behavior are not fully present in the current upload.

---

## 3. AUDIT CONSENSUS OVERVIEW

### Strongest consensus

Across the full source set, the following conclusions are strongly supported:

1. **The product should not be redesigned from scratch.**
2. **Terminal/Practice is the primary workstation and strongest part of the prototype.**
3. **The Flight Deck Console identity is a major product asset.**
4. **The learning loop is coherent and genuinely wired across core screens.**
5. **Prototype truthfulness is currently weaker than the visual maturity suggests.**
6. **Terminal state handling needs to become explicit and complete.**
7. **Mobile and narrow-width behavior deserves a dedicated validation pass rather than desktop-downscaling assumptions.**
8. **Accessibility semantics need a systemic pass, not isolated fixes.**
9. **The design-token system needs consolidation before more refinement.**
10. **The visual layer must remain separate from real engine/scoring/data semantics.**

### Conditional consensus

#### Mobile Coach behavior
The audits broadly agree that the Coach must remain subordinate to the Terminal on mobile. They differ on whether that should be a collapsed card, a bottom sheet, a FAB, or simply the current post-Terminal placement.

**Adjudication:** keep the current terminal-first ordering. Do not add a new FAB or bottom sheet unless usability testing proves that post-command coaching is being missed. That additional component would add interaction surface and cognitive load without direct evidence that it is necessary.

#### Arabic/RTL
The audits agree that the current EN/AR switch is not a real localization system. They differ on whether the toggle should be disabled, relabeled, or fully implemented immediately.

**Adjudication:** the product team must decide whether Arabic is in this release. If yes, implement it as a real localization/RTL system. If no, do not expose a fake operational switch; make its roadmap status explicit or remove the affordance. Do not ship a cosmetic language toggle.

#### Assessment Coach suppression
Some audits favor fully hiding Coach in Assessment; others favor a minimal visible state. 

**Adjudication:** in Assessment, Coach must not provide shortcuts or active coaching. Preserve a compact **Assessment Active / Hints Suppressed** state so the trainee still understands the support boundary. Full removal is not required unless validated by learning-design testing.

### Important minority insights retained

- The fabricated first-use Coach error is more serious than generic “terminal polish”: it creates contradictory state semantics at the exact moment of first use.
- The `--ab-*` token layer is not merely code cleanliness; it indicates that refinement is accumulating without being reconciled into a canonical design system.
- The current `ProgressRing`/chart semantics have good accessibility foundations that should be preserved rather than rewritten unnecessarily.
- The pre-seeded session clock (272 seconds) is a trust/continuity question because the UI does not distinguish “resumed session” from “fresh session.”
- Trend direction must not automatically equal good/bad color semantics. A “down” trend can be good or bad depending on what the metric means.
- Scenario titles are passed into Practice as context strings; this creates a real risk of losing scenario identity/provenance even though the basic handoff works.

### Strongest disagreements

1. **Bottom navigation four-column bug:** some audits reported it as a current defect. The current CSS contains later declarations setting five columns, including a mobile `!important` override. Therefore it is not accepted as a current rendered bug; it is accepted as **CSS-overwrite debt** and evidence of refinement accumulation.
2. **Mobile session readout hidden:** early/base CSS contains a mobile `display:none`, but later `.page-practice .terminal-session-readout` rules restore it. Therefore “session state is currently hidden on mobile” is not accepted as a current source truth. The real issue is **compression and visibility quality**, which still requires 320–430 validation.
3. **Chart library adoption:** there is no evidence that switching the current hand-built chart to Recharts is necessary. The existing chart has a real accessible data-table alternative. Adoption is deferred unless richer interaction requires it.
4. **Two-click Finish Session confirmation:** this is not accepted. It adds friction to a primary workflow without evidence of destructive ambiguity. Keep the current disabled-until-command behavior and use explicit completion/debrief semantics instead.
5. **Persistent global next-action widget:** not accepted as a mandatory feature. The product already contains next-action surfaces at the point of need. Adding a global sticky widget risks dashboardization.

### Major uncertainty areas

- Production Arabic scope and localization ownership.
- Production scoring and hint accounting semantics.
- Whether current mock counts are intentionally placeholders for future content or represent accidental inaccuracies.
- What “Saudi readiness” is actually supposed to mean.
- Whether “Backup” means export, cloud sync, local snapshot, or merely a prototype affordance.
- Real device behavior of sticky Terminal input under Android/iOS keyboards.
- Authoritative evidence rules for Growth and Tracking.

---

## 4. CRITICAL DECISIONS

### CD-01 — Preserve the product architecture; harden the presentation layer

**Decision:** Keep the five-area product model and current Terminal hub. Do not introduce a new route hierarchy or redesign the application architecture merely to solve presentation issues.

**Why:** The actual flow is already coherent and context-bearing. The highest-value problems are honesty, state clarity, accessibility, and system consolidation.

**Constraint:** New behavior must not bypass or redefine the engine boundary.

### CD-02 — Establish an AeroBridge Evidence Provenance Grammar

Every visible metric, status, score, trend, or readiness statement must belong to one of these explicit classes:

- **Illustrative** — seeded/sample prototype data.
- **Local** — generated by the local simulation or local persistence.
- **Calculated** — derived from an explicit local/data rule.
- **Historical** — persisted prior evidence.
- **Verified** — validated against a defined production source/rule.
- **Authoritative** — approved production evidence with known ownership.

**Decision:** the UI must make the boundary obvious without flooding every card with warnings. Practice can establish the pattern with a single strong “LOCAL TRAINING SIMULATION / ILLUSTRATIVE” disclosure; Growth and Tracking should adopt an equally disciplined but quieter provenance treatment.

### CD-03 — Neutral first-use Terminal state

No first-load state may contain an error, correction, warning, or fabricated learner mistake. First use is a **READY / AWAITING COMMAND** state.

### CD-04 — Empty command is a no-op

Submitting an empty string must never create an assessment entry, command history event, score change, toast claiming success/error, or `FQD` submission.

### CD-05 — Canonical Terminal state contract

The visual contract should cover, where relevant:

`first-use → ready → processing → success / partial-success / error → retry / recovery → interrupted → assessment-ready → assessment-active → assessment-complete → completed`

The UI may represent these states but must not invent the engine's semantics.

### CD-06 — Keep Assessment inside Practice

Assessment does not need to become a top-level route. It should remain inside the Terminal because that preserves command/workstation continuity. The transition must simply become explicit: **Practice → Assessment Active → Finish → Debrief → Next Action**.

### CD-07 — Protect workstation density without sacrificing readability

Do not simply enlarge every font or every target. Use a role-based type system and preserve compact metadata. Instructional prose, command/result text, and primary controls receive readability priority; decorative and low-value metadata may remain compact when contrast and semantics remain acceptable.

### CD-08 — Mobile Practice remains the central destination

Keep Practice visually central in the mobile rail. Do not remove the center-emphasis just to make the navigation sequence visually linear.

### CD-09 — True Arabic or explicit non-support

No cosmetic EN/AR state is acceptable. A release decision is required before implementation.

### CD-10 — No feature expansion before trust hardening

Do not add autocomplete, map experiences, trend overlays, sparklines, date filters, global next-action widgets, or additional KPI systems during the initial revision pass.

---

## 5. CANONICAL FINDINGS

> **Consensus notation:** C1 = isolated, C2 = repeated but not independently corroborated, C3 = corroborated by materially different analyses, C4 = strong cross-source agreement with direct artifact support, C5 = independently corroborated by separate evidence types. “Conditional” and “Disputed” are used where applicable.

### AB-F001 — Fabricated first-use error in Coach

**Type:** Behavioral / Trust / Local

**Source Audits:** Claude, ChatGPT, Qwen, Manus, DeepSeek, v0.dev, others as analytical corroboration.

**Source Artifacts:** `Home.tsx` Coach fallback; supplied Practice screenshot; `index.css` Terminal error styling.

**Evidence Type:** Source + screenshot.

**Evidence Independence:** **E3**

**Consensus:** **C5**

**Evidence Quality:** Very Strong

**Observation:** Before any command exists, the Coach block can render `FORMAT ERROR · CHECK ENTRY` plus a specific corrective instruction, while the header simultaneously states `AWAITING COMMAND`.

**Impact:** This is not aesthetic polish. It tells a new trainee that an error happened when no action occurred. That damages trust, creates a false mental model, and conflicts with the product's stated professionalism/precision positioning.

**Risk:** Critical first-use trust failure.

**Dependency:** UI-only / Content-only.

**Priority:** **P0**

**Final Verdict:** **ACCEPT**

**Decision:** First-use must be neutral. No error styling, error copy, or fabricated correction before a command is submitted.

**Action:** Render a neutral Coach state such as “Awaiting command / Submit a command to see workflow-specific coaching.” Reuse the existing pre-command guidance pattern where appropriate.

**Validation:** Fresh Practice entry at 320/360/390/430 and desktop. Expected: no error color, no corrective text, no alert semantics, no evidence event.

---

### AB-F002 — Empty submission silently becomes `FQD`

**Type:** Behavioral / Safety / Evidence Integrity

**Source Audits:** ChatGPT, Claude, DeepSeek, Gemini, Kimi, Manus, Qwen, v0.dev, others.

**Source Artifacts:** `Home.tsx` command submit logic.

**Evidence Type:** Direct source.

**Evidence Independence:** **E4**

**Consensus:** **C5**

**Evidence Quality:** Very Strong

**Observation:** `command.trim().toUpperCase() || "FQD"` means blank submission becomes an operational command.

**Impact:** A trainee can create a command history event and potentially affect future evidence by submitting nothing. In a training workstation this is a direct input-integrity problem.

**Risk:** High; becomes more serious when connected to real scoring/evidence.

**Dependency:** UI + Interaction + Engine boundary.

**Priority:** **P0**

**Final Verdict:** **ACCEPT**

**Decision:** Empty submission is a no-op.

**Action:** Block submit when trimmed input is empty; show concise inline guidance. Do not create a history entry or score change.

**Validation:** Enter/submit blank in Learn, Practice, and Assessment. Expected: no command event, no score change, no toast success/error, no history row.

---

### AB-F003 — Illustrative values are presented too close to authoritative learner evidence

**Type:** Systemic / Content / Evidence

**Source Audits:** ChatGPT, Claude, DeepSeek, Kimi, Manus, Qwen, v0.dev, Grok.

**Source Artifacts:** `Home.tsx` seeded records, hardcoded metrics, sidebar “Saudi readiness,” Practice footer, Growth reports, Scenario statistics; screenshots of Growth, Tracking, Progression, Scenarios.

**Evidence Type:** Source + screenshot + audit cross-corroboration.

**Evidence Independence:** **E3**

**Consensus:** **C5**

**Evidence Quality:** Very Strong

**Observation:** The prototype mixes genuinely persisted local assessment records with hardcoded summary values and broader readiness language. Examples include the hardcoded `24%` “Saudi readiness,” hardcoded current task `68%`, pre-command accuracy `86%`, `128 / 210` commands mastered, `3 / 8 stages`, `23 / 40 scenarios`, `LOG 04 / 12`, and “Operationally ready” thresholds.

**Impact:** Trainees cannot reliably distinguish what is calculated from real local state, what is sample copy, and what is a production competency judgment.

**Risk:** High trust/evidence-integrity risk.

**Dependency:** UI + Data + Content + Engine boundary.

**Priority:** **P0**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Do not remove informative prototype numbers wholesale. Instead, clearly classify their provenance and eliminate any wording that implies authoritative readiness unless the underlying production definition exists.

**Action:** Create one reusable provenance treatment for local/illustrative data and apply it consistently across Growth, Tracking, Progression, and Scenarios. Mark or remove unsupported readiness language.

**Validation:** Review every visible number on every route and answer: source, calculation rule, authority, and update mechanism. If any answer is unknown, the UI must not imply authority.

---

### AB-F004 — Non-functional controls overpromise completed actions

**Type:** Behavioral / UX / Trust

**Source Audits:** ChatGPT, Claude, DeepSeek, Kimi, Manus, Qwen, v0.dev, Grok, Gemini.

**Source Artifacts:** `Home.tsx` handlers for Search, Profile, Language, My route, View map, See all stages, Filters, Sort, Backup, and evidence actions.

**Evidence Type:** Direct source.

**Evidence Independence:** **E4**

**Consensus:** **C5**

**Evidence Quality:** Very Strong

**Observation:** Multiple controls visually promise navigation/action but only trigger toast messages.

**Impact:** A serious operational product should not say an action occurred when it merely displayed a message. The pattern also creates friction because real CTAs sit next to fake ones.

**Risk:** High trust and discoverability risk.

**Dependency:** UI-only for honest relabel/remove; Engine/Data/Content for true functionality.

**Priority:** **P0**

**Final Verdict:** **ACCEPT**

**Decision:** Every visible affordance must either perform the promised action, expose a real unavailable state, or stop looking actionable.

**Action:** For the first revision, prioritize honest removal/relabelling over building new features. Keep true implementation decisions out of the visual pass unless the product scope explicitly approves them.

**Validation:** Click every control with an action-like label. Expected: destination/action occurs, or the control clearly says unavailable/preview/roadmap. No success toast may claim an unperformed action.

---

### AB-F005 — Assessment mode can inherit prior command/hint state without an explicit contract

**Type:** Behavioral / Learning / Evidence

**Source Audits:** Claude, DeepSeek, Kimi, Qwen, v0.dev, Gemini.

**Source Artifacts:** `Home.tsx` mode switch, `commandHistory`, `hintCount`, assessment scoring function.

**Evidence Type:** Direct source + audit interpretation.

**Evidence Independence:** **E4** for the state behavior; E2 for the learning consequence.

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** Switching to Assessment resets `sessionComplete` but does not reset `commandHistory` or `hintCount`. Reference opens in Learn/Practice increment the same `hintCount` used in Assessment scoring.

**Impact:** Assessment may inherit activity that the UI visually frames as separate modes. The current “No hints” label can therefore be misleading.

**Risk:** High learning/evidence-integrity risk once scoring is treated as official.

**Dependency:** State/Data/Engine.

**Priority:** **P1**

**Final Verdict:** **TEST BEFORE ACCEPTING**

**Decision:** Do not silently change scoring logic in the UI pass. First determine whether modes are intentionally continuous or independently scored.

**Action:** Immediate safe UI mitigation: when entering Assessment, disclose carried-over command/hint state when non-zero. Then obtain an engine/learning-design decision on isolation vs continuity.

**Validation:** Test mode switching after 0, 1, and multiple commands; test Reference usage in Learn and Practice; verify whether displayed assessment rules match actual scoring inputs.

---

### AB-F006 — Terminal state model is richer in type declarations than in visible UI

**Type:** Systemic / Behavioral

**Source Audits:** ChatGPT, DeepSeek, Qwen, Kimi, Manus, v0.dev, Gemini.

**Source Artifacts:** `SystemState` and Terminal UI; visible state strings; screenshots.

**Evidence Type:** Source + screenshots.

**Evidence Independence:** **E3**

**Consensus:** **C5**

**Evidence Quality:** Strong

**Observation:** The code declares first-use, empty, loading, ready, in-progress, success, partial-success, error, retry, interrupted, completed, review, locked, unavailable, but not all have a distinct visual contract.

**Impact:** The real engine will eventually need to attach explicit state to the UI. If the presentation system is not ready, state meanings will drift or be inferred from color/copy.

**Risk:** High scalability risk.

**Dependency:** UI + State contract.

**Priority:** **P1**

**Final Verdict:** **ACCEPT**

**Decision:** Define a canonical state presentation system first; do not invent engine semantics.

**Action:** Specify state name, label, icon, tone, allowable actions, and announcement behavior for every state relevant to each screen.

**Validation:** Build a state inventory and prove every state has at least one visible non-color cue and an action/recovery rule where applicable.

---

### AB-F007 — Mobile command-input focus uses JS `scrollIntoView` in addition to sticky input

**Type:** Responsive / Interaction

**Source Audits:** Gemini, Claude, DeepSeek, Kimi, Qwen, v0.dev, Grok.

**Source Artifacts:** `Home.tsx` `focusCommandInput`; `index.css` sticky input/safe-area rules; Practice screenshots.

**Evidence Type:** Direct source + rendered evidence; physical-device behavior not yet verified.

**Evidence Independence:** **E3**

**Consensus:** **C4 / TEST REQUIRED**

**Evidence Quality:** Strong for mechanism, Moderate for actual device impact.

**Observation:** The input is intentionally sticky and uses 16px mobile type, but focus also triggers a delayed smooth `scrollIntoView({ block: "center" })` call.

**Impact:** The combination can compete with native keyboard scrolling and potentially produce visible jumps or wrong scroll placement on iOS/Android.

**Risk:** Medium-High responsive risk.

**Dependency:** UI/Interaction.

**Priority:** **P1**

**Final Verdict:** **TEST BEFORE ACCEPTING**

**Decision:** Prefer native/sticky behavior if device testing proves the JS scroll unnecessary; do not remove it solely from static inference.

**Action:** Run real device tests before and after removing the timer/scroll intervention.

**Validation:** iOS Safari and Android Chrome at 320/360/390/430. Focus input with keyboard closed/open, rotate device, submit, reopen Reference. Failure = input hidden, viewport jumps, bottom rail overlaps, or terminal loses intended scroll position.

---

### AB-F008 — Coach must remain subordinate to the Terminal

**Type:** Systemic / Hierarchy / Responsive

**Source Audits:** All nine audits, with different solutions proposed.

**Source Artifacts:** `Home.tsx` Practice layout; `index.css` desktop two-column and mobile order; screenshots.

**Evidence Type:** Source + screenshots + cross-audit reasoning.

**Evidence Independence:** **E3**

**Consensus:** **C5 / CONDITIONAL**

**Evidence Quality:** Strong

**Observation:** Desktop uses a sticky Coach column beside the Terminal; mobile places Coach after the main Terminal.

**Impact:** Desktop Coach can compete for reading attention; mobile Coach can become too far below the latest result.

**Risk:** Medium-high cognitive-load risk.

**Dependency:** UI-only.

**Priority:** **P1**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Keep Coach as support, not a second workstation. Do not introduce a FAB/bottom-sheet by default.

**Action:** Desktop: constrain Coach width and hierarchy. Mobile: keep it below Terminal by default but provide a compact, clearly labeled “Coach / latest feedback” disclosure tied to the latest result only if usability testing shows that feedback is being missed.

**Validation:** Compare task completion with and without the mobile disclosure on 360/390/430. Failure = trainee cannot locate latest feedback after a command without scrolling excessively or primary Terminal focus is reduced.

---

### AB-F009 — Duplicate prompt/caret creates first-use ambiguity

**Type:** Visual / Interaction

**Source Audits:** Claude, DeepSeek, Kimi.

**Source Artifacts:** `Home.tsx` `terminal-active-line`; screenshot showing active terminal line plus real input.

**Evidence Type:** Source + screenshot.

**Evidence Independence:** **E3**

**Consensus:** **C3 / TEST REQUIRED**

**Evidence Quality:** Good

**Observation:** The scrollable Terminal body shows a live command echo/caret while the actual form input sits below it.

**Impact:** Advanced users may perceive this as authentic terminal behavior, but a first-time user could be unsure where typing occurs.

**Risk:** Low-Medium discoverability risk.

**Dependency:** UI-only.

**Priority:** **P2**

**Final Verdict:** **TEST BEFORE ACCEPTING**

**Decision:** Do not remove the authentic terminal affordance automatically; clarify ownership of the real input first.

**Action:** Make the actual input unmistakable through label, focus treatment, or subtle prompt differentiation.

**Validation:** First-time user test: ask “Where do you type?” without instruction. Success = correct target selected immediately.

---

### AB-F010 — Per-command toasts duplicate persistent Terminal feedback

**Type:** Interaction / Cognitive Load

**Source Audits:** Claude, DeepSeek, Kimi, v0.dev, Qwen.

**Source Artifacts:** `Home.tsx` submission toasts; terminal history; Coach panel.

**Evidence Type:** Direct source.

**Evidence Independence:** **E4**

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** A single command can communicate its result through history, Coach, and toast.

**Impact:** Adds transient motion and repeated signal during long sessions.

**Risk:** Medium cognitive noise.

**Dependency:** UI-only.

**Priority:** **P2**

**Final Verdict:** **ACCEPT**

**Decision:** Terminal owns command-level feedback. Use toasts for session-level or cross-context messages, not routine command outcomes.

**Action:** Remove routine command toasts while preserving global/system feedback where no local surface exists.

**Validation:** 20-command session. Success = no important information is lost and the interface feels quieter, not less informative.

---

### AB-F011 — Session state should be consolidated and trustworthy

**Type:** Hierarchy / Content / State

**Source Audits:** ChatGPT, Claude, DeepSeek, Kimi, Manus, Grok.

**Source Artifacts:** `Home.tsx` session readouts and clock; screenshots; later CSS refinements.

**Evidence Type:** Source + screenshots.

**Evidence Independence:** **E3**

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** Practice contains session status, command status, log count, footer timing, mode labels, and task context. The current timer is seeded at 272 seconds on entry.

**Impact:** Too many small state fragments can slow orientation, while a pre-seeded clock makes “new session” vs “continued session” unclear.

**Risk:** Medium orientation/trust risk.

**Dependency:** UI + State/Data.

**Priority:** **P1**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Use one dominant session summary: **Context → Mode → Session state → Command state → Log/next move**. Treat the clock as a separate utility, and only use a non-zero start time if the state genuinely represents a resumed session.

**Action:** Reconcile readouts and remove duplicate/low-value state fragments.

**Validation:** Fresh entry, resumed entry, mode switch, completed session. User should be able to answer “Where am I? What am I doing? What happened last? What do I do next?” in seconds.

---

### AB-F012 — Typography is both a provisioning problem and a scale problem

**Type:** Systemic / Typography / Accessibility

**Source Audits:** Claude, ChatGPT, DeepSeek, Kimi, Qwen, v0.dev, Grok.

**Source Artifacts:** `index.css` font tokens and pervasive small text; audit-reported `index.html` findings; screenshots.

**Evidence Type:** Source + screenshot + audit-reported external artifact.

**Evidence Independence:** **E3**

**Consensus:** **C5**, with provisioning caveat.

**Evidence Quality:** Strong

**Observation:** The current CSS declares Space Grotesk, Cairo, and IBM Plex Mono, but the supplied current upload does not include the document-level font-loading file. Multiple audits report the original package had the font import commented out. Independently, the current CSS contains many 7–10px labels and 10–11px body/readout sizes.

**Impact:** The intended visual identity may not be deterministic, Arabic typography is not proven, and long-session instructional readability is weaker than the product's role demands.

**Risk:** High systemic visual/accessibility risk.

**Dependency:** UI + Architecture for font provisioning; UI for scale.

**Priority:** **P1**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Re-verify actual font provisioning in the current integration, then establish role-based minimum readable sizes without flattening the workstation.

**Action:** Proportional headings remain expressive; instruction/body text should generally sit in a comfortable 14–16px range; command/output content should remain at a readable mono size; metadata may remain compact around 11–12px where contrast and importance justify it. Do not use 7–8px for meaningful instructions or primary status.

**Validation:** Computed font-family in production; Android/iOS visual comparison; 200–400% browser zoom; long-session reading test.

---

### AB-F013 — Muted/faint text has insufficient contrast in common small-text contexts

**Type:** Visual / Accessibility

**Source Audits:** Claude, ChatGPT, v0.dev, Kimi, Grok, others.

**Source Artifacts:** `index.css` token values; audit-computed contrast table.

**Evidence Type:** Static contrast calculation derived from source tokens.

**Evidence Independence:** **E4** for token math.

**Consensus:** **C4**

**Evidence Quality:** Very Strong

**Observation:** Audit-computed ratios report `--text-faint` at roughly 3.66:1 on the base background, 3.18:1 on panel surfaces, and ~2.94:1 on card surfaces; some placeholder/readout colors are similarly marginal.

**Impact:** Small metadata and supporting text can become difficult to perceive, especially on mobile and for low-vision users.

**Risk:** Accessibility and long-session fatigue.

**Dependency:** UI-only.

**Priority:** **P1**

**Final Verdict:** **ACCEPT**

**Decision:** Raise the luminance of muted/faint text where it is informational. Preserve low-emphasis appearance through size, weight, spacing, and surface hierarchy—not insufficient contrast.

**Action:** Define semantic text tiers with tested contrast rather than one faint color used everywhere.

**Validation:** WCAG contrast checks at actual combinations used in screenshots; test 200/400% zoom and low-vision simulation.

---

### AB-F014 — Primary CTA color pairing fails WCAG AA in the current token set

**Type:** Visual / Accessibility / Systemic

**Source Audits:** Claude and supporting audits.

**Source Artifacts:** `index.css` `.primary-button`; audit-computed ratio.

**Evidence Type:** Source + computed contrast.

**Evidence Independence:** **E4**

**Consensus:** **C3**

**Evidence Quality:** Very Strong

**Observation:** White text on `--blue: #6f8fff` is reported at ~2.98:1, below the applicable 4.5:1 threshold for this text size.

**Impact:** The highest-intent CTA across the product is not comfortably legible for all users.

**Risk:** High accessibility issue with low implementation risk.

**Dependency:** UI-only.

**Priority:** **P0**

**Final Verdict:** **ACCEPT**

**Decision:** Keep the Vector Blue identity but adjust either the CTA blue or text treatment until the shipped pairing clears the applicable contrast threshold.

**Action:** Use a darker semantic action-blue or another high-contrast text pairing; test all hover/active states separately.

**Validation:** Recompute contrast for normal, hover, focus, disabled, and high-contrast OS settings.

---

### AB-F015 — Tab-like controls do not consistently expose selection semantics

**Type:** Accessibility / Systemic

**Source Audits:** Claude, Gemini, Kimi, Qwen, v0.dev.

**Source Artifacts:** `Home.tsx` mode tabs, metric switcher, track tabs, Growth tabs, scenario filters.

**Evidence Type:** Direct source.

**Evidence Independence:** **E4**

**Consensus:** **C5**

**Evidence Quality:** Very Strong

**Observation:** The visual system contains multiple segmented controls, but the current file does not consistently use `role="tab"`, `aria-selected`, or `aria-pressed` to express selection state.

**Impact:** Screen-reader users may hear “button” without knowing which mode/filter/metric is active.

**Risk:** High systemic accessibility gap.

**Dependency:** UI-only.

**Priority:** **P1**

**Final Verdict:** **ACCEPT**

**Decision:** Create one shared semantic pattern and apply it consistently according to the control's actual behavior. Use tabs only where panels switch; use pressed state for independent toggles/filters where appropriate.

**Action:** Establish a component-level state contract rather than manually patching each screen.

**Validation:** Keyboard navigation + VoiceOver/TalkBack/NVDA; active state announced correctly for all five control groups.

---

### AB-F016 — Progress indicators need semantic progressbar semantics

**Type:** Accessibility / Systemic

**Source Audits:** Gemini, Claude, Qwen, v0.dev.

**Source Artifacts:** `Home.tsx` `AnimatedBar`, `ProgressRing`.

**Evidence Type:** Direct source.

**Evidence Independence:** **E4**

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** `AnimatedBar` uses an `<i>` element for visual width and an `aria-label`, rather than a progressbar semantic. `ProgressRing` uses `role="img"` with an accessible label and a decorative SVG.

**Impact:** The ring is acceptable as an image-like metric, but a progress indicator that is functionally a percentage should expose that relationship directly.

**Risk:** Medium accessibility semantics risk.

**Dependency:** UI-only.

**Priority:** **P1**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Refactor percentage progress visuals to a consistent semantic progressbar pattern where they represent progress, while keeping the ring's visual role where it is genuinely a visual readout.

**Action:** Define reusable progress semantics: min, max, current, label.

**Validation:** Screen reader announces “68%, progress bar” or equivalent meaningful phrasing; decorative SVG is not double-announced.

---

### AB-F017 — Overlays and focus mode need explicit focus ownership

**Type:** Accessibility / Interaction / Systemic

**Source Audits:** Claude, Gemini, Qwen, Kimi, v0.dev.

**Source Artifacts:** `Home.tsx` mobile drawer, search popover, Reference; CSS Focus Mode.

**Evidence Type:** Source + audit analysis.

**Evidence Independence:** **E4**

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** The mobile drawer and command/reference popovers do not show complete focus trapping, Escape handling, focus restoration, or dialog semantics. Focus Mode is a full-screen visual state but not necessarily a true modal dialog.

**Impact:** Keyboard and assistive-tech users can lose orientation or move focus behind an active overlay.

**Risk:** High accessibility risk.

**Dependency:** UI/Accessibility.

**Priority:** **P1**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Implement modal behavior only where the UI is genuinely modal. Treat Focus Mode as a workspace state with explicit focus entry/exit and focus restoration; treat drawer/search/reference as transient overlays with appropriate dialog/drawer semantics.

**Validation:** Keyboard-only tests: open, Tab, Shift+Tab, Escape, close, confirm focus returns to launcher.

---

### AB-F018 — Shell lacks a first-class main landmark, skip link, and route-change focus strategy

**Type:** Accessibility / Navigation

**Source Audits:** Claude, Kimi, Qwen, v0.dev, Grok.

**Source Artifacts:** `Home.tsx` shell composition.

**Evidence Type:** Direct source.

**Evidence Independence:** **E4**

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** Content is wrapped in generic divs rather than a semantic `<main>`, a skip link is not implemented, and route changes do not move focus to a meaningful page heading.

**Impact:** Keyboard and screen-reader users must repeatedly traverse navigation and may not understand that a new view has loaded.

**Risk:** Medium-High accessibility efficiency risk.

**Dependency:** UI-only.

**Priority:** **P1**

**Final Verdict:** **ACCEPT**

**Action:** Add one main landmark, one skip-to-main link, and route-change focus management that lands on the page title or equivalent primary heading.

**Validation:** Keyboard-only navigation from top of document after every route transition; screen reader announces current page without requiring a manual search.

---

### AB-F019 — EN/AR toggle is cosmetic; mixed LTR/RTL command content has no production contract

**Type:** Systemic / Content / Accessibility

**Source Audits:** All nine audits, particularly Gemini, Claude, Kimi, ChatGPT, Qwen.

**Source Artifacts:** `Home.tsx` language switch; CSS font token; audit-reported document-level findings; design intent around Saudi-market readiness.

**Evidence Type:** Direct source + audit-reported external artifact + product documentation.

**Evidence Independence:** **E3**

**Consensus:** **C5 / CONDITIONAL**

**Evidence Quality:** Strong with scope limitation.

**Observation:** The EN/AR control changes local state and toast text but does not change page direction, translation, or content. The source has an Arabic font token but no current Arabic content pipeline.

**Impact:** Mixed-language operational interfaces can break visual order, code readability, and future accessibility if implemented as a superficial switch.

**Risk:** High if Saudi/Arabic support is a real release requirement.

**Dependency:** Content + Architecture + UI.

**Priority:** **P1/P2**, depending on product scope.

**Final Verdict:** **DEFER** pending product scope, with a required interim honesty fix.

**Decision:** If Arabic is in-release, implement full RTL/i18n including bidi isolation for Amadeus commands, airport/airline codes, dates, and numerical data. If not, remove or honestly relabel the cosmetic control.

**Validation:** Arabic screen set at 320/360/390/430; mixed Arabic narrative + LTR command; screen reader direction; mirrored navigation where intended; no command corruption.

---

### AB-F020 — Design system drift from layered tokens and patch-style overrides

**Type:** Systemic / Design System

**Source Audits:** Claude, ChatGPT, DeepSeek, Kimi, Qwen, v0.dev.

**Source Artifacts:** `index.css` base tokens, later `--ab-*` tokens, repeated `.bottom-nav` declarations, repeated media overrides.

**Evidence Type:** Direct source.

**Evidence Independence:** **E4**

**Consensus:** **C5**

**Evidence Quality:** Very Strong

**Observation:** The stylesheet contains a strong base token system followed by a later parallel `--ab-*` system with overlapping semantic roles and multiple repeated declarations for the same properties.

**Impact:** Future changes can diverge across screens and refinement passes can create accidental behavior.

**Risk:** Medium-High maintainability and consistency risk.

**Dependency:** UI-only.

**Priority:** **P1/P2**

**Final Verdict:** **ACCEPT**

**Decision:** Consolidate to one canonical semantic token vocabulary and retain only route-specific tokens that truly represent unique semantic roles.

**Action:** Normalize surfaces, borders, text, status, interaction, typography, and motion tokens. Preserve the strongest current values instead of flattening the visual identity.

**Validation:** One semantic change propagates to all intended surfaces; grep confirms no obsolete token layer remains.

---

### AB-F021 — Surface hierarchy risks dashboardization

**Type:** Visual / Information Architecture / Systemic

**Source Audits:** ChatGPT, DeepSeek, Grok, Kimi, Manus, Qwen.

**Source Artifacts:** screenshots; Growth/Tracking/Scenario card patterns; CSS panel system.

**Evidence Type:** Screenshot + source + audit reasoning.

**Evidence Independence:** **E3**

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** Cards, panels, score rings, KPI boxes, route motifs, micro-bars, and trend indicators are used extensively.

**Impact:** The product can drift toward “analytics dashboard” behavior even though its job is operational training. Visual elevation can flatten the hierarchy if every section becomes a card.

**Risk:** Medium product-identity/cognitive-load risk.

**Dependency:** UI-only.

**Priority:** **P2**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Keep the existing visual language but distinguish four surface roles: workstation, support/context, evidence, and secondary utility. Do not add more panels merely to fill space.

**Validation:** Five-second scan test on each route: the primary action and current state should be more visually dominant than secondary metrics.

---

### AB-F022 — Mobile navigation order and route numbering use competing concepts of sequence

**Type:** Navigation / Content / Mobile

**Source Audits:** Claude, ChatGPT, Grok, Qwen, v0.dev.

**Source Artifacts:** `Home.tsx` `navItems` and mobile reorder; screenshots showing Route / Apply / Train / Evidence / Trend.

**Evidence Type:** Direct source + screenshot.

**Evidence Independence:** **E4**

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** Mobile deliberately reorders the items to center Practice, while some persistent breadcrumb copy implies canonical step numbers.

**Impact:** A trainee can see “02”/“03” labels that do not match the visual order of the mobile rail.

**Risk:** Medium wayfinding confusion.

**Dependency:** UI/Content.

**Priority:** **P2**

**Final Verdict:** **ACCEPT**

**Decision:** Keep center-emphasis ordering; remove numeric breadcrumb semantics that imply the mobile rail order is the same as the desktop canonical array, or derive the sequence from the current display order.

**Validation:** Tap all five mobile items and confirm no screen can be read as “out of order.”

---

### AB-F023 — Progression stage counts are inconsistent with the actual defined stage set

**Type:** Content / Data / Trust

**Source Audits:** Claude, ChatGPT, DeepSeek, Kimi, Qwen, v0.dev.

**Source Artifacts:** `Home.tsx` six-item `levels` array versus hardcoded `3 / 8 stages` and segmented indicator.

**Evidence Type:** Direct source.

**Evidence Independence:** **E4**

**Consensus:** **C5**

**Evidence Quality:** Very Strong

**Observation:** The screen claims 3/8 stages while the current data defines six level objects.

**Impact:** Internal arithmetic inconsistency weakens trust immediately.

**Risk:** Medium-High.

**Dependency:** Content/Data.

**Priority:** **P1**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Do not assume whether two missing stages should exist. Make the displayed fraction derive from the actual stage set that is rendered, or explicitly label future/planned stages if they are approved content.

**Validation:** Fraction and segmented count must always be derived from the same source collection as the visible stage map.

---

### AB-F024 — Customer Service track is currently a hollow alternate description

**Type:** Learning / Content / IA

**Source Audits:** Claude, Kimi, ChatGPT, Qwen, v0.dev.

**Source Artifacts:** `Home.tsx` `track` state and single `levels` array; screenshots showing Technical/Customer Service tabs.

**Evidence Type:** Direct source.

**Evidence Independence:** **E4**

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** Selecting Customer Service changes the descriptive paragraph but leaves the same Technical milestone list and technical heading.

**Impact:** The UI implies two learning tracks without actually providing two learning maps.

**Risk:** Medium-High pedagogical and trust risk.

**Dependency:** Content/Data.

**Priority:** **P1/P2**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Until real Service-track curriculum data exists, the control should enter an honest unavailable/coming-soon state rather than showing Technical milestones under a Service label.

**Validation:** Selecting either track must never leave the user looking at a milestone list explicitly belonging to the other track.

---

### AB-F025 — Scenario summary metrics, filters, and sort controls exceed the actual data

**Type:** Content / Interaction / Trust

**Source Audits:** Claude, ChatGPT, Kimi, Qwen, Grok, v0.dev.

**Source Artifacts:** `Home.tsx` five scenario objects, hardcoded KPI row, Filters toast, Sort toast; screenshots.

**Evidence Type:** Direct source + screenshot.

**Evidence Independence:** **E4**

**Consensus:** **C5**

**Evidence Quality:** Very Strong

**Observation:** The UI claims `23 / 40` scenarios and a category “Exchanges & Refunds” that is not in the current scenario set. The visible Filters button does not open a filter surface and Sort does not actually sort.

**Impact:** A trainee is shown a world of content and capabilities that the UI cannot currently reach.

**Risk:** High trust/discoverability risk.

**Dependency:** UI + Content/Data.

**Priority:** **P1**

**Final Verdict:** **ACCEPT**

**Decision:** Make summary counts derive from current data or label them as future content; remove/relabel fake Filters/Sort until they perform a real action.

**Validation:** KPI numbers reconcile with the visible/available scenario set; sort order changes; filters reduce the list; zero-result state is defined.

---

### AB-F026 — Growth must distinguish evidence, interpretation, and readiness

**Type:** Learning / Content / Evidence

**Source Audits:** ChatGPT, Claude, DeepSeek, Kimi, Manus, Grok.

**Source Artifacts:** Growth Record Record/Reports screenshots; `Home.tsx` latest evidence, report language, hardcoded report metrics.

**Evidence Type:** Screenshot + source + learning-system reasoning.

**Evidence Independence:** **E3**

**Consensus:** **C5**

**Evidence Quality:** Strong

**Observation:** Growth mixes recent local evidence, summarized learner interpretation, and broad statements such as “Readiness is a pattern, not a single score” / “Operationally ready.”

**Impact:** Interpretation can be mistaken for competency certification.

**Risk:** High if used with real learners.

**Dependency:** Content/Data/Engine + UI.

**Priority:** **P1**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Keep the evidence-to-action language, but require provenance and scope on broader interpretation. “Operationally ready” must not be used as an authoritative state until a competency rubric and threshold are defined.

**Action:** Show evidence source, attempt/date, skill, evidence type, and local/verified status. Keep recommendations explicitly actionable rather than certification-like.

**Validation:** Every Growth statement can be traced to an evidence object or approved rule; no broad readiness claim appears without a defined authority.

---

### AB-F027 — Growth History and Backup imply more persistence than exists

**Type:** Content / Trust / Interaction

**Source Audits:** Claude, ChatGPT, Qwen, Kimi, v0.dev.

**Source Artifacts:** `Home.tsx` Growth History `LOG 04 / 12`; Backup toast; screenshots.

**Evidence Type:** Direct source + screenshot.

**Evidence Independence:** **E4**

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** History says `LOG 04 / 12` while only three entries are rendered. Backup claims a local backup point is created, but the current handler does not create a distinct backup artifact.

**Impact:** Users can infer missing history and protection mechanisms that do not exist.

**Risk:** Medium-high trust risk.

**Dependency:** Content/Data; real backup = Engine/Data.

**Priority:** **P2**

**Final Verdict:** **ACCEPT**

**Decision:** Reconcile the count with rendered/available history and do not confirm a backup until a real backup mechanism exists.

**Validation:** History count equals accessible history; Backup produces verifiable output or is clearly marked preview/unavailable.

---

### AB-F028 — Skill trend color must encode semantic meaning, not raw direction

**Type:** Data semantics / Visual

**Source Audits:** Claude; supporting audits.

**Source Artifacts:** `index.css` `.skill-trend--up/down`; `Home.tsx` `skillRows` with `tone` and `trend`.

**Evidence Type:** Direct source + scenario reasoning.

**Evidence Independence:** **E4** for mechanism; E2 for future risk.

**Consensus:** **C2 / CONDITIONAL**

**Evidence Quality:** Good

**Observation:** Up arrows are amber and down arrows are green regardless of whether the trend is favorable for that skill.

**Impact:** This is semantically unsafe once real varied data arrives. Some skills improve when their numeric value goes down; others worsen when it goes down.

**Risk:** Medium semantic communication risk.

**Dependency:** Data semantics + UI.

**Priority:** **P2**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Color must come from **direction-of-desirability**, not raw mathematical direction.

**Validation:** Test at least four hypothetical combinations: strong skill improving, strong skill regressing, weak skill improving, weak skill regressing.

---

### AB-F029 — Progress Tracking should remain an operational evidence view, not become an analytics product

**Type:** IA / Visual / Learning

**Source Audits:** ChatGPT, DeepSeek, Grok, Kimi, Qwen.

**Source Artifacts:** Tracking screenshot, KPI hierarchy, chart/table structure, next-action panel.

**Evidence Type:** Screenshot + source + product-fit reasoning.

**Evidence Independence:** **E3**

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** Tracking already has a good chart/table pair and next-action panel, but the KPI layer can become the visually dominant story.

**Impact:** The trainee may focus on number movement rather than what the number means for behavior.

**Risk:** Medium dashboardization/learning dilution risk.

**Dependency:** UI + Data meaning.

**Priority:** **P2**

**Final Verdict:** **ACCEPT**

**Decision:** Primary order should be **skill → behavior → trend → next action**. Keep the table and chart, but reduce KPI competition.

**Validation:** A user should be able to explain the next training action from the page without needing to interpret the chart alone.

---

### AB-F030 — Tablet range needs a deliberate navigation/composition decision

**Type:** Responsive / Navigation

**Source Audits:** Claude, DeepSeek, Kimi, v0.dev, Grok.

**Source Artifacts:** `index.css` breakpoints at 740 and 1100; layout rules.

**Evidence Type:** Direct source.

**Evidence Independence:** **E4**

**Consensus:** **C3 / TEST REQUIRED**

**Evidence Quality:** Good

**Observation:** At 740–1099px the content becomes multi-column while the desktop sidebar is still hidden, leaving mobile-style navigation chrome alongside desktop-density content.

**Impact:** This may be coherent, but the evidence is insufficient to decide whether the combination reads as intentional or transitional.

**Risk:** Medium responsive identity risk.

**Dependency:** UI-only.

**Priority:** **P2**

**Final Verdict:** **TEST BEFORE ACCEPTING**

**Decision:** Do not invent a new tablet navigation system yet. Validate the existing model at 768, 834, and 1024. Change only if the composition fails the workstation hierarchy test.

**Validation:** Real render at 768/834/1024 with Terminal, Scenarios, Growth, and Tracking. Failure = navigation chrome and content density feel like unrelated breakpoint modes or primary task width becomes constrained.

---

### AB-F031 — Long scenario context can strain the Practice task strip

**Type:** Responsive / Content

**Source Audits:** Claude, Kimi, Qwen.

**Source Artifacts:** `Home.tsx` scenario titles and `practiceContext`; `index.css` task-strip truncation rules.

**Evidence Type:** Source.

**Evidence Independence:** **E4** for the data flow; rendered behavior requires validation.

**Consensus:** **C3 / TEST REQUIRED**

**Evidence Quality:** Good

**Observation:** Practice uses a fixed task-strip structure while Scenario → Practice passes the full scenario title, including long names such as “Rebooking due to schedule change.”

**Impact:** Long titles can crowd the percentage badge or reduce readability at 320–430px.

**Risk:** Medium responsive risk.

**Dependency:** UI-only.

**Priority:** **P2**

**Final Verdict:** **TEST BEFORE ACCEPTING**

**Decision:** Keep full scenario context accessible, but constrain visible label length and preserve an explicit scenario identifier when needed.

**Validation:** Longest current scenario titles at 320/360/390/430; no overlap, clipping, or primary-action compression.

---

### AB-F032 — Hardcoded milestone/report language can overstate readiness

**Type:** Content / Learning / Evidence

**Source Audits:** ChatGPT, Claude, Kimi, Qwen, Manus.

**Source Artifacts:** `Home.tsx` `AssessmentReport` and Growth report copy.

**Evidence Type:** Direct source + product-meaning analysis.

**Evidence Independence:** **E4** for the wording; E2 for the product-risk interpretation.

**Consensus:** **C4**

**Evidence Quality:** Strong

**Observation:** The assessment report uses “Operationally ready” at a local score threshold of 85+, and other report copy uses broad readiness framing.

**Impact:** A local heuristic can be mistaken for a production competency decision.

**Risk:** High if learner-facing outside prototype context.

**Dependency:** Content/Data/Engine.

**Priority:** **P1**

**Final Verdict:** **ACCEPT WITH MODIFICATION**

**Decision:** Retain the useful debrief structure but use scope-limited language until production competency thresholds are defined.

**Action:** Preferred prototype vocabulary: “Strong result,” “Review one workflow pass,” “Rebuild the sequence,” or “Local session signal.” Reserve “Operationally ready” for an approved production rule.

**Validation:** Every debrief verdict must identify the scope of the assessment and whether it is local/illustrative or authoritative.

---

### AB-F033 — Current screenshot/source asset dependencies are not self-contained

**Type:** Implementation / Deployment / Visual Integrity

**Source Audits:** ChatGPT, Manus, Kimi, Claude.

**Source Artifacts:** CSS URLs to `/manus-storage/...`; current upload missing those image assets; audit reports of hosted rendering.

**Evidence Type:** Source + screenshot comparison.

**Evidence Independence:** **E3**

**Consensus:** **C3**

**Evidence Quality:** Strong

**Observation:** Screenshots show imagery loaded from `/manus-storage/...`, while the current supplied source set does not include those image assets.

**Impact:** The visual design reference is not fully portable to the eventual GitHub/vanilla implementation without documenting the asset contract.

**Risk:** Medium visual regression/integration risk.

**Dependency:** Architecture/Deployment/UI.

**Priority:** **P2**

**Final Verdict:** **ACCEPT**

**Decision:** Treat asset provenance as part of the implementation package. The design reference is not complete until required imagery, fonts, and fallback behavior are documented.

**Validation:** Build from the handoff package in a clean environment. Failure = missing visual assets or layout depending on unavailable hosted resources.

---

### AB-F034 — Unused Map component and unintegrated fallback surfaces are not reasons to redesign, but require handoff hygiene

**Type:** Implementation / System

**Source Audits:** ChatGPT, Claude, Kimi, Qwen, v0.dev.

**Source Artifacts:** `Map.tsx`, `App.tsx`; audit-reported `ErrorBoundary` / `NotFound` surfaces.

**Evidence Type:** Direct current source for Map/App; audit-reported external artifact for fallbacks.

**Evidence Independence:** **E3**

**Consensus:** **C3**

**Evidence Quality:** Moderate-Strong

**Observation:** `App.tsx` currently renders `Home`; `Map.tsx` is not part of the visible loop. Audits also report that ErrorBoundary/NotFound components exist elsewhere in the source package but are not integrated.

**Impact:** Unused capabilities and fallback surfaces can confuse implementation scope and create identity breaks when later integrated.

**Risk:** Low-Medium implementation hygiene risk.

**Dependency:** Architecture / UI.

**Priority:** **P3**

**Final Verdict:** **DEFER**

**Decision:** Do not delete or implement anything during the design revision. Document what is intentionally out of the current product loop and ensure any future fallback surface follows AeroBridge visual language.

**Validation:** Handoff package explicitly labels unused/inactive components and future integration dependencies.

---

### AB-F035 — Normal mobile Terminal input resolves to 15px, contradicting the intended mobile command-input safety floor

**Type:** Responsive / Accessibility / Systemic

**Source Audits:** Claude, Gemini, Kimi, ChatGPT, DeepSeek, Grok, Manus, Qwen, v0.dev (all discussed mobile command-entry safety, but none of the audit-level claims should override direct current-source cascade evidence).

**Source Artifacts:** `client/src/index.css` current rule order; specifically the later `.page-practice .terminal-input input { font-size: 15px; }` mobile override after the earlier 16px Practice rule.

**Evidence Type:** Direct source / cascade adjudication.

**Evidence Independence:** **E4**

**Consensus:** **Conditional consensus** — the audits correctly identified mobile input as safety-critical, but several reports treated 16px as the current resolved value. Current source-order inspection shows a regression in the normal mobile state.

**Evidence Quality:** Very Strong

**Observation:** The Practice input is set to 16px in a later scoped refinement, but a still-later `@media (max-width: 739px)` rule explicitly sets the same selector to 15px. Because the later declaration has equal selector specificity, normal mobile Practice resolves to 15px. Focus Mode is a separate higher-specificity case and retains its larger value.

**Impact:** The current normal mobile command field is below the deliberate 16px threshold commonly used to prevent iOS Safari focus auto-zoom. This contradicts the design intent documented by multiple audits and makes the command-entry safety contract inconsistent between Normal and Focus modes.

**Risk:** High on iOS/mobile interaction if the 15px field triggers zoom or viewport movement; Medium otherwise. Exact device behavior still requires validation.

**Dependency:** UI / Responsive / Accessibility

**Priority:** **P1**

**Final Verdict:** **ACCEPT**

**Decision:** Treat 16px as the minimum normal mobile command-input floor. Remove the later 15px regression rather than adding another compensating override. Preserve the existing sticky/safe-area strategy.

**Action:** Consolidate the mobile Practice input rule so the final computed `font-size` is at least 16px at 320–739px in Normal mode. Keep Focus Mode at its intentionally larger value.

**Validation:** Test at 320, 360, 390, and 430 CSS px on iOS Safari and Android Chrome with the native keyboard open. Success = no unwanted auto-zoom, no command-input occlusion, no horizontal overflow, and no loss of the execute affordance.

## 6. DESIGN SYSTEM DECISIONS

### DS-01 — Typography

**Decision:** Three role families remain conceptually correct: proportional UI/prose, Arabic UI, monospace commands/readouts.

**Why:** The product genuinely mixes human-readable training instruction with command syntax and operational readouts.

**Scope:** Global.

**Priority:** P1.

**Dependency:** UI + font provisioning + localization.

**Implementation rule:**
- Headings: expressive but not oversized at the expense of scan speed.
- Instructional body: typically 14–16px.
- Command/result text: readable monospace, typically 13–15px or larger when dense lines require it.
- Metadata: 11–12px minimum where informational; 7–9px should not carry essential meaning.
- Metrics: tabular numerals.
- Arabic: dedicated tested font if Arabic is in scope.

**Validation:** font loading, zoom, long-session reading, mixed EN/AR, real-device screenshots.

### DS-02 — Color

**Decision:** Preserve the existing semantic palette; fix luminance where contrast fails rather than replacing the identity.

**Scope:** Global.

**Priority:** P0/P1.

**Dependency:** UI-only.

**Rules:**
- Blue = action/active/information.
- Green = successful/healthy/favorable.
- Amber = caution/review.
- Red = error/blocking.
- Cyan = focus/reference/information.
- Violet may remain scenario-specific, but its meaning must be documented.

Every state must also have a label/icon/structural cue.

### DS-03 — Surfaces and elevation

**Decision:** Consolidate to semantic tiers rather than making every region an equally elevated card.

**Scope:** Global.

**Priority:** P2.

**Dependency:** UI-only.

**Rules:**
1. Workstation surface.
2. Support/context surface.
3. Evidence surface.
4. Secondary utility/historical surface.

The Terminal is allowed to be visually heavier than secondary cards because it is the primary work area.

### DS-04 — Borders and focus

**Decision:** Define semantic quiet, standard, strong, status, and focus borders.

**Scope:** Global.

**Priority:** P1/P2.

**Dependency:** UI-only.

**Rules:** The focus state must be a dedicated, high-contrast semantic treatment, not an accidental reuse of the active blue border.

### DS-05 — Spacing and density

**Decision:** Consolidate around a 4/8-based rhythm while preserving current compactness where the content is genuinely operational.

**Scope:** Global.

**Priority:** P2.

**Dependency:** UI-only.

**Rules:** Do not globally increase every gap. Use larger spacing around primary actions and section boundaries; keep compact metadata inside terminal/history rows.

### DS-06 — Buttons

**Decision:** Define four clear classes: operational primary, navigation, utility, destructive/restart.

**Priority:** P1.

**Rules:**
- Mobile interactive hit area: target at least 44×44 CSS px where feasible.
- Visual button height can remain compact on desktop, but the hit area must not become inaccessible.
- `text-action` must receive a real hit area, not zero padding.
- Primary CTA contrast must pass.

### DS-07 — Inputs

**Decision:** Command input remains the most prominent input in the system.

**Rules:** preserve 16px mobile command font, sticky behavior, clear focus-within state, and keyboard-safe layout. Do not add autocomplete without a demonstrated learning requirement.

### DS-08 — Tabs and toggles

**Decision:** Use semantics based on behavior, not appearance.

**Rules:**
- Mode/tab panels: `role=tablist` / `role=tab` / `aria-selected`.
- Toggle/filter groups: `aria-pressed` or another appropriate state.
- Do not call every two-state control a tab.

### DS-09 — States

Create one state vocabulary used consistently across screens:

- first-use
- empty
- ready
- loading/processing
- in-progress
- success
- partial-success
- warning/review
- error
- retry/recovery
- interrupted
- completed
- locked
- unavailable

Every state requires:

- label
- icon/shape
- color/tone
- allowable actions
- accessibility announcement policy

### DS-10 — Motion

**Decision:** Preserve the existing reduced-motion foundation.

**Why:** The current `prefers-reduced-motion` handling is a genuine product strength.

**Rules:** Formalize motion durations and reduce animation where it duplicates information. The Terminal caret must stop animating under reduced-motion; smooth scrolling should also be disabled.

### DS-11 — Accessibility semantics

**Decision:** Build accessibility into shared components rather than patching screens.

**Scope:** Global.

**Priority:** P1.

**Components:** Tabs, buttons, progress, navigation, drawers, charts, state notices.

### DS-12 — Responsive contract

Breakpoints should be treated as deliberate product states:

- **Desktop:** persistent sidebar, full workstation composition.
- **Laptop:** sidebar + Terminal/Coach split if width permits.
- **Tablet:** validate current bottom-nav architecture and density; do not invent a new navigation system without evidence.
- **Mobile:** Terminal-first, safe-area-aware command input, compact navigation rail, subordinate Coach, readable status.

### DS-13 — Arabic / RTL

If release scope includes Arabic:

- root direction changes to RTL where appropriate;
- command strings, airport/airline codes, dates, and numerical readouts use explicit LTR isolation;
- line-height and font metrics are tested;
- navigation mirroring is deliberate, not automatic everywhere;
- mixed-language screen-reader behavior is validated.

### DS-14 — Data visualization

Keep the current chart + table pattern.

Do not replace the hand-built chart merely because a charting library exists. The current data-table fallback is an asset. Add chart complexity only when the learning use-case requires it.

---

## 7. GLOBAL UX DECISIONS

### Navigation

Keep five primary workspaces. Desktop and mobile may use different ordering if the reason is clear; mobile centrality for Practice is justified because Practice is the workstation.

### IA

The loop remains:

**Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action**

Assessment is a Practice mode, not a sixth navigation item.

### Information hierarchy

Each route should read as:

**Current task/state → supporting evidence → next action → secondary context/history.**

### CTA hierarchy

There must be only one dominant action per view. Secondary actions must look and behave as secondary actions.

### Feedback

Use the nearest meaningful surface for information:

- command feedback → Terminal history;
- coaching → Coach;
- session/system messages → toast or notice;
- route/state change → page/heading context.

### Discoverability

Do not use “authentic terminal ambiguity” as an excuse for unclear controls. Realism is valuable only when it does not hide the primary task.

### Orientation

The trainee must be able to answer:

- where am I?
- what am I practicing?
- what mode am I in?
- what just happened?
- what should I do next?

without scanning the whole page.

### System states

States must be explicit and recoverable. Avoid silent transitions.

---

## 8. TERMINAL / WORKSTATION DECISIONS

### 8.1 Primary-workstation verdict

**Yes, the Terminal is already the primary workstation—but it must be protected from decorative and feedback competition.**

### 8.2 Target hierarchy

1. Session identity/context.
2. Mode and current state.
3. Command history/result.
4. Command input.
5. Next operational move.
6. Reference/Coach as support.

### 8.3 Ready state

First load should show:

- local-simulation notice,
- current task,
- active mode,
- neutral Coach/readout,
- input focus affordance.

No error should exist without an actual error event.

### 8.4 Processing

The Execute control must have a processing state that prevents duplicate submission and makes the wait visible.

### 8.5 Success

A successful response should be visible in history with a clear success label/icon and next move.

### 8.6 Error

An error must state:

- what kind of error it is;
- what was received;
- what the trainee should do next.

Do not force every error into red-only styling.

### 8.7 Recovery

After error, the trainee should know whether to:

- correct and retry;
- restore the previous step;
- use Reference;
- resume an interrupted session.

### 8.8 History

Keep Arrow Up/Down. Add visible discoverability without turning the Terminal into a tutorial widget. History entries should have semantic command/result/status grouping.

### 8.9 Reference

Reference remains secondary. Opening it can legitimately affect hint state, but that contract belongs to the assessment model. The visual layer must distinguish “reference opened” from “hint consumed” if the underlying engine can distinguish them.

### 8.10 Coach

Coach is contextual support, not a second result feed. It should respond to the latest meaningful Terminal state.

### 8.11 Assessment

The Assessment view must visibly state:

- assessment active;
- whether hints are permitted;
- whether prior activity carries into this mode;
- what command sequence/context is being evaluated;
- what counts as completion.

### 8.12 Focus Mode

Focus Mode should:

- remove non-essential navigation;
- preserve session identity;
- preserve command input;
- preserve a clear exit path;
- manage focus on entry/exit;
- respect reduced motion;
- never allow background scroll to steal interaction.

Do not force a dialog role if Focus Mode is actually an application workspace state rather than a modal dialog.

### 8.13 Long-session comfort

The Terminal should support repeated commands without visual exhaustion. Avoid flashing toasts, oversized decorative gaps, excessive animation, and extremely small instruction text.

---

## 9. LEARNING UX DECISIONS

### Learning

Learn mode should explain workflow logic, not merely show commands.

### Practice

Practice should shift responsibility toward independent recall while retaining optional support.

### Assessment

Assessment should be visibly distinct in constraint, not merely in tab color. The trainee should know when support is suppressed and what state will be recorded.

### Feedback

Feedback should answer:

**What happened → why → what matters → what to do next.**

### Coaching

Coach language should never imply an error that has not occurred.

### Scenarios

Scenario detail already has a good mission-file structure. Preserve it.

A completed scenario should hand meaningful evidence back into Growth or another existing evidence surface rather than creating a disconnected result screen.

### Progression

Progression is orientation. It should prioritize:

**current vector → current evidence → resume action → upcoming stage → long-range map.**

### Skill gaps

Growth should express specific behavioral gaps, such as a fare-display-to-pricing handoff issue, rather than generic “score lower” language.

### Repetition

Recommendations should promote repeat practice with a concrete variation—fewer hints, stronger sequencing, scenario pressure—only when the underlying rule supports that recommendation.

### Next action

The next action should always be relevant to the evidence just shown. Avoid generic “continue” actions without learning meaning.

---

## 10. RESPONSIVE DECISIONS

### Desktop

**Primary rule:** Terminal dominance.

- Persistent sidebar.
- Terminal gets the largest work area.
- Coach remains clearly subordinate.
- Metadata never competes with command/output.
- Primary CTA remains visually dominant without becoming oversized.

### Laptop

**Primary rule:** preserve Terminal readability over Coach breadth.

If two-column layout causes the command surface to become too narrow, collapse the Coach before shrinking Terminal text.

### Tablet (740–1099)

Do not assume the current layout is wrong. Validate it first.

Target rule:
- 740–899: prioritize Terminal width; consider single-column Coach below if two-column makes the Terminal cramped.
- 900–1099: two-column may remain if Terminal retains operational width and session header stays legible.
- Bottom navigation can remain if it passes the orientation test; do not create a third navigation system without evidence.

### Mobile (≤739)

Priority order:

1. Terminal header/context.
2. Terminal output/history.
3. Command input + Execute.
4. latest feedback/Coach.
5. bottom navigation.

Rules:
- keep 16px command input;
- preserve safe-area handling;
- do not allow bottom nav to cover the command action;
- keep session state visible in a compact form;
- keep Coach subordinate;
- avoid large empty Terminal gaps;
- do not hide essential state merely to make the header prettier.

### 390 / 360

Preserve the existing dedicated header restructuring and treat it as successful refinement. Test it rather than replacing it.

### 320

Treat 320 as a first-class test, not a theoretical floor. Ensure no horizontal scroll, command truncation, or overlapping topbar/Terminal controls.

### Screenshot validation matrix

At minimum: 320, 360, 390, 430, 768, 834, 1024, 1280, 1440/1450+.

---

## 11. ACCESSIBILITY DECISIONS

1. Preserve the current strong `prefers-reduced-motion` foundation.
2. Remove viewport restrictions that prevent browser/pinch zoom, subject to verification in the supplied build.
3. Add `<main>` landmark and skip-to-main link.
4. Move focus to the new page heading on route change.
5. Complete semantic tab/toggle states.
6. Add progressbar semantics where the visual is truly progress.
7. Give transient overlays proper Escape/focus trapping/restoration.
8. Keep command history as a semantic live region with appropriate urgency; do not mark every routine update as assertive.
9. Use icon + label + structure + color for state communication.
10. Ensure all primary mobile actions have accessible hit areas.
11. Preserve accessible chart table and make it the canonical non-visual representation.
12. Test Arabic mixed-direction behavior with commands/codes.

---

## 12. SCREEN-BY-SCREEN AUDIT

### 12.1 Shared Shell

**Current Strengths**
- Strong brand lockup.
- Persistent desktop navigation.
- Compact mobile rail.
- Contextual topbar.
- Real history-based route switching.

**Critical Problems**
- False/partial controls in topbar.
- Missing main landmark/skip/focus strategy.
- Cosmetic language switch.
- Drawer focus semantics incomplete.
- Mobile order vs numbered breadcrumb ambiguity.

**Required Changes**
- Fix shell semantics.
- Resolve language truthfulness.
- Remove/relax false controls.
- Keep Practice center emphasis.

**Optional Improvements**
- Add unique utility content to the drawer only if product scope later requires it.

**Responsive**
- Validate tablet navigation composition.
- Verify mobile rail at 320/360.

**Accessibility**
- Main landmark, skip link, focus restoration, active state.

**Priority:** P1

**Dependency:** UI / Content / Architecture for localization.

**Do Not Touch**
- Brand identity, sidebar concept, mobile rail concept.

---

### 12.2 Progression

**Strengths**
- Excellent resume-first hero.
- Current vector is understandable.
- Locked/mastered/current language is useful.
- Technical vs Service concept is strategically strong.

**Critical Problems**
- `3 / 8` conflicts with six currently defined levels.
- Service track does not change the stage map.
- Some section actions are non-functional.
- Lower page sections risk competing with current task.

**Required Changes**
- Derive stage totals from actual data or mark future content.
- Make Service track honest until content exists.
- Make “View map / See all stages / My route” real, unavailable, or non-interactive.
- Keep current vector visually dominant.

**Optional Improvements**
- Add curriculum provenance once real mapping exists.

**Responsive**
- Reduce visual weight after current-stage section on narrow screens.
- Confirm no excessive vertical elongation at 320/360.

**Accessibility**
- `aria-current` for current stage where applicable; `aria-expanded` for mastered cards.

**Priority:** P1

**Dependency:** Content/Data + UI.

**Do Not Touch**
- Resume-first structure.

---

### 12.3 Practice / Terminal

**Strengths**
- Strongest screen.
- Terminal-first composition.
- Genuine command history.
- Focus Mode.
- Learn/Practice/Assessment.
- Reference and Coach concepts.
- Local simulation disclosure.
- Assessment debrief.

**Critical Problems**
- Fake first-use error.
- Empty→FQD fallback.
- Cross-mode state/hint ambiguity.
- Terminal state model incomplete.
- Potential mobile keyboard/focus fragility.
- Repeated command toasts.
- Dual prompt/caret ambiguity.

**Required Changes**
- Fix neutral first-use.
- Empty submit no-op.
- Canonical state contract.
- Make assessment boundary explicit.
- Reduce command toast duplication.
- Validate keyboard interaction.
- Strengthen session-state hierarchy.

**Optional Improvements**
- Visible Arrow Up/Down hint.
- Compact Coach disclosure after testing.

**Responsive**
- Terminal gets priority at all widths.
- At mobile, Coach is subordinate and input stays visible.

**Accessibility**
- Live-region semantics, progress/state labels, focus management, input label, semantic history.

**Priority:** P0/P1

**Dependency:** UI + Interaction + State/Data for assessment semantics.

**Do Not Touch**
- command vocabulary, command-order logic, current scoring weights, local persistence unless separately approved.

---

### 12.4 Scenarios

**Strengths**
- Mission-file framing.
- Strong detail panel.
- Difficulty/time/category/skills.
- State-specific operational next move.
- Real Scenario→Practice handoff.

**Critical Problems**
- Hardcoded headline counts.
- Nonexistent “Exchanges & Refunds” summary category.
- Filters button and Sort are misleading.
- Long scenario titles need narrow-width validation.

**Required Changes**
- Reconcile KPI data.
- Make filters/sort real or remove their action affordance.
- Preserve state-specific mission language.
- Add zero-result state.

**Optional Improvements**
- Recommended scenario cue if real recommendation rules exist.

**Responsive**
- Keep mission context and CTA reachable.

**Accessibility**
- Selected/filter semantics; detail heading structure.

**Priority:** P1/P2

**Dependency:** UI + Content/Data.

**Do Not Touch**
- Mission-file visual identity.

---

### 12.5 Growth Record — Record

**Strengths**
- Excellent evidence-to-next-action concept.
- Strengths vs Needs Attention split.
- Skill rows and targeted practice.
- Learning loop strip.

**Critical Problems**
- Evidence provenance is not explicit enough.
- Broad readiness language can overstate evidence.
- Tiny text density.
- Trend color semantics can become misleading.

**Required Changes**
- Add provenance treatment.
- Separate evidence from interpretation.
- Ensure trend color reflects semantic desirability.

**Optional Improvements**
- More explicit scenario links if approved by content model.

**Responsive**
- Preserve score-ring readability and prevent KPI clipping.

**Accessibility**
- Tab semantics, readable labels, keyboard skill selection.

**Priority:** P1/P2

**Dependency:** UI + Data/Content.

**Do Not Touch**
- Read evidence → practice gap → apply in scenario pattern.

---

### 12.6 Growth Record — History

**Strengths**
- Useful chronological layer.
- Clear evidence/event framing.

**Critical Problems**
- `LOG 04 / 12` mismatch.
- Some history items are toast-only.
- Current tab implementation hides other panels via `display:none` rather than a robust semantic tab/panel system.

**Required Changes**
- Reconcile history count.
- Make history rows either actionable or clearly informational.
- Add semantic tab/panel relationships.

**Optional Improvements**
- Persistent last-debrief surface only if product research proves it necessary.

**Responsive**
- Preserve row readability and large enough hit areas.

**Accessibility**
- Tabs/rows/heading semantics.

**Priority:** P2

**Dependency:** UI/Data.

**Do Not Touch**
- Chronological evidence framing.

---

### 12.7 Growth Record — Reports

**Strengths**
- “What is reliable / what recurs / what next?” is a strong interpretation framework.

**Critical Problems**
- Readiness language can exceed evidence authority.
- Hardcoded report values.

**Required Changes**
- Add provenance and scope.
- Use approved competency language only.

**Optional Improvements**
- None until content/data rules exist.

**Responsive**
- Preserve single-column readability on narrow screens.

**Accessibility**
- Report announced as a status update only when appropriate.

**Priority:** P1

**Dependency:** Content/Data/Engine.

**Do Not Touch**
- Three-question interpretation pattern.

---

### 12.8 Progress Tracking

**Strengths**
- Real persisted local record usage.
- Useful next-action panel.
- Chart + data-table pairing.
- Trend comparison logic.

**Critical Problems**
- Risk of KPI/dashboard dominance.
- Trend definitions are not always explained.
- Metric controls need semantic selected state.

**Required Changes**
- Make “what this metric means” clearer.
- Keep data table authoritative.
- Reduce KPI competition.

**Optional Improvements**
- Text trend summary, if it remains concise.

**Responsive**
- Validate chart/table and KPI clipping at 320–430.

**Accessibility**
- Metric switcher semantics, chart table, decorative gridlines hidden from AT.

**Priority:** P2

**Dependency:** UI + Data semantics.

**Do Not Touch**
- Data-table alternative.

---

### 12.9 Error / 404 / Fallback Surfaces

**Verification status:** **UNKNOWN / NOT ENOUGH CURRENT ARTIFACT EVIDENCE**

Several audits report that an ErrorBoundary and NotFound implementation exist in the broader project and may not be integrated or may use a visual language inconsistent with AeroBridge. Those source files are not part of the current uploaded unique source set.

**Decision:** Do not change based on speculation. When the actual fallback files are included in the production handoff, validate that they preserve the same Flight Deck Console visual/interaction language and do not expose raw stack traces to end users.

**Priority:** P3 pending artifact availability.

---

## 13. KEEP / PRESERVE

### Visual

- Flight Deck Console identity.
- Deep navy foundation.
- Restrained Vector Blue accents.
- Green/amber/red operational semantics.
- Monospace command/readout treatment.
- Atmospheric route imagery when it supports, rather than competes with, the task.
- Asymmetric desktop composition.
- Compact operational utility controls.

### UX

- Progression → Practice orientation.
- Context-carrying next-action buttons.
- Practice-the-gap language.
- Scenario mission-file framing.
- Evidence-first Growth.
- Next-useful-readout Tracking.

### Terminal

- Terminal-first composition.
- Learn / Practice / Assessment modes.
- Arrow Up/Down command history.
- Reference.
- Coach.
- Focus Mode.
- Sticky command input.
- Safe-area handling.
- Local simulation labeling.
- Assessment report.

### Accessibility

- Reduced-motion foundation.
- Visible focus treatment.
- `aria-live="polite"` where appropriate.
- Progress Tracking table alternative.
- Text + icon/state language in many existing components.

### Data/flow

- `setPracticeContext` pattern.
- `localStorage` persistence for local assessment evidence.
- Real route synchronization via `pushState`/`popstate`.

---

## 14. DO NOT DO

1. Do not redesign the visual identity.
2. Do not turn AeroBridge into a generic LMS.
3. Do not turn the Terminal into a card in a dashboard.
4. Do not add metrics merely because empty space exists.
5. Do not increase gamification.
6. Do not add global streaks, leaderboards, badges, or engagement mechanics without explicit learning evidence.
7. Do not invent engine behavior through UI.
8. Do not alter scoring math as a visual fix.
9. Do not assume “Saudi readiness” semantics.
10. Do not ship a cosmetic Arabic toggle.
11. Do not silently change content totals to match the mock without deciding curriculum truth.
12. Do not add a mobile Coach FAB/bottom sheet before user-testing the current subordinate flow.
13. Do not add two-click Finish Session confirmation without a demonstrated destructive-action problem.
14. Do not replace the chart library merely because one is installed.
15. Do not add a persistent global next-action widget merely to make the app feel more “complete.”
16. Do not rely on color alone for status.
17. Do not use 7–9px instructional text.
18. Do not change architecture without evidence.
19. Do not treat every audit repetition as independent proof.
20. Do not erase subtle minority insights just because they are less common.

---

## 15. CONFLICTS RESOLVED

### CR-01 — “Bottom-nav 4-column bug” vs current CSS

**Relevant sources:** several audits; current `index.css`.

**Evidence:** early `.bottom-nav` rule uses four columns, but later global/mobile declarations set five columns and the latest mobile rule uses `!important`.

**Competing positions:** Some audits reported a current five-items-in-four-columns defect; others recognized later overrides.

**Resolution:** The rendered state is **not treated as currently broken**. The canonical finding is CSS debt/patch layering (AB-F020).

**Final Decision:** **REJECT** the claim as a current user-facing defect; **ACCEPT** the underlying maintainability problem.

**Validation:** Clean stylesheet audit after consolidation.

### CR-02 — “Session readout hidden on mobile” vs later Practice-scoped override

**Relevant sources:** Claude, Kimi, v0.dev, current `index.css`.

**Evidence:** base mobile rule sets `.terminal-session-readout { display:none }`, but later `.page-practice .terminal-session-readout` restores display and explicitly refines the 390/360 layout.

**Resolution:** The current state is not classified as simply “hidden.” The actual issue is **density and visibility quality**, especially below 360.

**Final Decision:** **REJECT** the stale claim; **ACCEPT WITH MODIFICATION** as a responsive validation issue (AB-F011).

### CR-03 — “Remove Coach in Assessment” vs “keep a compact locked state”

**Relevant sources:** Gemini, DeepSeek, Kimi, Claude.

**Resolution:** Full removal is unnecessary. Assessment must suppress shortcuts, not orientation.

**Final Decision:** **ACCEPT WITH MODIFICATION**.

### CR-04 — “Add mobile Coach FAB / bottom sheet”

**Relevant sources:** DeepSeek/Qwen-style recommendations vs other audits emphasizing simplicity.

**Resolution:** This adds a new interaction surface without direct evidence that the current flow fails.

**Final Decision:** **DEFER / TEST BEFORE ACCEPTING**.

### CR-05 — “Two-click Finish Session confirmation”

**Relevant sources:** some implementation plans.

**Resolution:** The button is already disabled until command history exists. A second confirmation adds friction but does not solve a demonstrated safety issue.

**Final Decision:** **REJECT**.

### CR-06 — “Use chart library instead of hand-built chart”

**Relevant sources:** Claude and other audits.

**Resolution:** Existing hand-built visualization already works and has a genuine table alternative. Library choice is not a UX blocker.

**Final Decision:** **DEFER** unless richer chart interaction is required.

### CR-07 — “Fonts are definitely not loaded”

**Relevant sources:** Claude and audits that inspected a broader package; current upload.

**Resolution:** The current upload lacks `index.html`, so the claim is not directly re-verifiable from the current artifact set. The font tokens are definitely declared. The original-package audit evidence is strong enough to treat provisioning as a required verification item, not as an unsupported certainty.

**Final Decision:** **ACCEPT WITH MODIFICATION** — verify current shipped loading before treating it as a closed issue.

### CR-08 — “Build the Customer Service track now”

**Relevant sources:** multiple audits.

**Resolution:** The UI cannot invent curriculum content.

**Final Decision:** **DEFER** content creation; implement an honest unavailable/coming-soon state until approved curriculum data exists.

### CR-09 — “Add a persistent next-action widget everywhere”

**Relevant sources:** Kimi/Qwen-style recommendations.

**Resolution:** Existing screens already place next-action guidance near relevant evidence. A global widget risks dashboardization and duplicate hierarchy.

**Final Decision:** **REJECT AS MANDATORY FEATURE**; optimize existing contextual CTAs instead.

---

## 16. NEW INSIGHTS / AUDIT GAPS

### NEW INSIGHT NI-01 — AeroBridge needs a single “Truth Surface” pattern

**Evidence:** The Practice screen explicitly labels local simulation/illustrative output; Growth, Tracking, Progression, and Scenarios are less consistent. Hardcoded numbers and broader readiness language recur across several screens.

**Why it matters:** The problem is not only “hardcoded numbers.” It is the absence of a unified UI grammar for answering **Where did this number/status come from?**

**Why existing audits may have missed the systemic formulation:** Individual audits mostly flagged each hardcoded number separately. The more important product-level decision is to make provenance a reusable component/state contract.

**Confidence:** High.

**Priority:** P0/P1.

**Dependency:** UI + Data + Content.

**Recommendation:** Define a subtle provenance treatment such as `LOCAL`, `CALCULATED`, `HISTORICAL`, or `VERIFIED` where useful. Do not put verbose disclaimers everywhere; use the minimum signal needed to prevent a false authority impression.

### NEW INSIGHT NI-02 — Scenario identity should survive the handoff as an identity, not only a title

**Evidence:** `practiceContext` is a string; scenarios pass the full scenario title. The terminal task strip shows the context but not the scenario ID.

**Why it matters:** When the real scenario system becomes richer, title-only context will be ambiguous and makes evidence traceability harder.

**Why existing audits may have missed it:** Most audits focused on overflow or the existence of the handoff, not the future traceability requirement.

**Confidence:** High.

**Priority:** P1/P2.

**Dependency:** Data + UI.

**Recommendation:** Keep the current visible title but pair it with a stable contextual identity when the real data contract exists, e.g. `SC-014 / Group booking for a corporate client`.

### NEW INSIGHT NI-03 — The current visual refinement history is itself a design-system signal

**Evidence:** repeated CSS declarations, later Practice-specific token layer, later mobile rail fixes, later narrow-header overrides.

**Why it matters:** The design is not suffering from lack of intent; it is suffering from **accumulated successful patches that were never normalized**.

**Why existing audits may have missed it:** Individual audits identified token drift, but the systemic interpretation is more important: future designers should treat every refinement as a change to a canonical system, not as another local override.

**Confidence:** Very High.

**Priority:** P1/P2.

**Dependency:** UI/System.

**Recommendation:** After the current revision, require every new token and breakpoint rule to declare its semantic reason.

---

### NEW INSIGHT NI-04 — The mobile Terminal safety contract has regressed through cascade order, not design intent

**Evidence:** The stylesheet contains a deliberate 16px Practice input rule followed by a max-739px rule that lowers the same selector to 15px. This is a source-order conflict between successive refinement passes.

**Why it matters:** The prototype’s strongest mobile Terminal engineering is undermined by an implementation-level regression that is invisible at the design-token level and easy to miss when reading the stylesheet by semantic sections instead of final cascade resolution.

**Why existing audits may have missed it:** Several audits correctly recognized the importance of the 16px rule, but relied on the earlier declaration without resolving the later same-specificity override.

**Confidence:** Very High.

**Priority:** P1.

**Dependency:** UI/System/Accessibility.

**Recommendation:** Treat final computed styles, not intended declarations, as the source of truth during responsive QA. Add a small regression check for the command input at supported mobile widths.

## 17. FINAL PRIORITY MATRIX

| Finding ID | Issue / Decision | Sources | Evidence | Independence | Consensus | Evidence Quality | Impact | Risk | Dependency | Priority | Verdict |
|---|---|---|---|---|---|---|---|---|---|---|---|
| AB-F001 | Fabricated first-use Coach error | Multi-audit | Source + screenshot | E3 | C5 | Very Strong | Critical | Critical | UI/Content | P0 | ACCEPT |
| AB-F002 | Empty submit becomes FQD | Multi-audit | Direct source | E4 | C5 | Very Strong | Critical | High | UI/Engine boundary | P0 | ACCEPT |
| AB-F003 | Evidence/provenance ambiguity | Multi-audit | Source + screenshots | E3 | C5 | Very Strong | Critical | High | Mixed | P0 | ACCEPT WITH MODIFICATION |
| AB-F004 | Fake/toast-only action affordances | Multi-audit | Direct source | E4 | C5 | Very Strong | High | High | UI/Mixed | P0 | ACCEPT |
| AB-F014 | Primary CTA contrast failure | Audits + source | Computed source colors | E4 | C3 | Very Strong | High | High | UI | P0 | ACCEPT |
| AB-F005 | Cross-mode command/hint state bleed | Multi-audit | Direct source | E4 | C4 | Strong | High | High | State/Data | P1 | TEST BEFORE ACCEPTING |
| AB-F006 | Incomplete visible state contract | Multi-audit | Source + screenshots | E3 | C5 | Strong | High | High | UI/State | P1 | ACCEPT |
| AB-F007 | JS focus scroll may fight mobile keyboard | Multi-audit | Source + device-dependent behavior | E3 | C4 | Strong | High | Medium-High | UI | P1 | TEST BEFORE ACCEPTING |
| AB-F008 | Coach hierarchy | Multi-audit | Source + screenshots | E3 | C5 | Strong | High | Medium | UI | P1 | ACCEPT WITH MODIFICATION |
| AB-F011 | Session orientation/seeded clock | Multi-audit | Source + screenshots | E3 | C4 | Strong | High | Medium | UI/State | P1 | ACCEPT WITH MODIFICATION |
| AB-F012 | Font provisioning + type scale | Multi-audit | Source + screenshots + audit package evidence | E3 | C5 | Strong | High | High | UI/Architecture | P1 | ACCEPT WITH MODIFICATION |
| AB-F013 | Muted text contrast | Multi-audit | Computed source colors | E4 | C4 | Very Strong | High | High | UI | P1 | ACCEPT |
| AB-F015 | Missing tab/toggle semantics | Multi-audit | Direct source | E4 | C5 | Very Strong | High | High | UI | P1 | ACCEPT |
| AB-F017 | Overlay/focus management | Multi-audit | Direct source | E4 | C4 | Strong | High | High | UI/A11y | P1 | ACCEPT WITH MODIFICATION |
| AB-F018 | Main landmark/skip/route focus | Multi-audit | Direct source | E4 | C4 | Strong | High | Medium | UI | P1 | ACCEPT |
| AB-F019 | Cosmetic EN/AR | Multi-audit | Source + product docs | E3 | C5 | Strong | High | High | Mixed | P1/P2 | DEFER + interim fix |
| AB-F023 | Progression stage count mismatch | Multi-audit | Direct source | E4 | C5 | Very Strong | Med-High | Medium-High | Content/Data | P1 | ACCEPT WITH MODIFICATION |
| AB-F024 | Hollow Service track | Multi-audit | Direct source | E4 | C4 | Strong | High | Medium-High | Content/Data | P1/P2 | ACCEPT WITH MODIFICATION |
| AB-F025 | Scenario KPI/filter/sort mismatch | Multi-audit | Direct source | E4 | C5 | Very Strong | High | High | UI/Data | P1 | ACCEPT |
| AB-F026 | Growth evidence vs readiness | Multi-audit | Source + screenshots | E3 | C5 | Strong | High | High | Mixed | P1 | ACCEPT WITH MODIFICATION |
| AB-F032 | Readiness wording overstates heuristic | Multi-audit | Direct source + product fit | E4 | C4 | Strong | High | High | Content/Data | P1 | ACCEPT WITH MODIFICATION |
| AB-F021 | Dashboardization risk | Multi-audit | Screens + source | E3 | C4 | Strong | Med-High | Medium | UI | P2 | ACCEPT WITH MODIFICATION |
| AB-F022 | Mobile route/order semantics | Multi-audit | Source + screenshot | E4 | C4 | Strong | Medium | Medium | UI/Content | P2 | ACCEPT |
| AB-F027 | Growth history/backup mismatch | Multi-audit | Direct source + screenshot | E4 | C4 | Strong | Medium | Medium-High | Data/UI | P2 | ACCEPT |
| AB-F028 | Trend color semantic risk | Claude + others | Direct source | E4 | C2 | Good | Medium | Medium | Data/UI | P2 | ACCEPT WITH MODIFICATION |
| AB-F029 | Tracking should remain operational | Multi-audit | Source + screenshot | E3 | C4 | Strong | Medium | Medium | UI/Data | P2 | ACCEPT |
| AB-F030 | Tablet breakpoint composition | Multi-audit | Direct source | E4 | C3 | Good | Medium | Medium | UI | P2 | TEST BEFORE ACCEPTING |
| AB-F031 | Long scenario context overflow | Multi-audit | Direct source | E4 | C3 | Good | Medium | Medium | UI | P2 | TEST BEFORE ACCEPTING |
| AB-F033 | Asset self-containment | Multi-audit | Source + screenshot comparison | E3 | C3 | Strong | Medium | Medium | Architecture/UI | P2 | ACCEPT |
| AB-F034 | Unused Map/fallback hygiene | Multi-audit | Current source + audit report | E3 | C3 | Moderate-Strong | Low | Low-Medium | Architecture/UI | P3 | DEFER |
| AB-F035 | Normal mobile Terminal input resolves to 15px | Multi-audit + current CSS cascade | Direct current source | E4 | Conditional | Very Strong | High | High on iOS | UI/Responsive/A11y | P1 | ACCEPT |

---

## 18. IMPLEMENTATION SEQUENCE

### Phase A — Design System Foundations

**Objective:** Establish truth, semantic consistency, and accessibility primitives before visual refinement spreads further.

1. Canonicalize semantic tokens.
2. Verify actual font provisioning.
3. Define readable type roles and minimums.
4. Correct CTA contrast.
5. Define state/tone/icon contracts.
6. Add main landmark and skip link.
7. Define tab/toggle semantics.
8. Define progress semantics.
9. Establish the evidence/provenance treatment.

**Regression boundary:** do not modify command semantics, scoring, persistence, or route destinations.

### Phase B — Core Workstation / Terminal

1. Neutral first-use Coach.
2. Empty submit no-op.
3. Explicit processing state.
4. Explicit error/recovery states.
5. Clarify session-state hierarchy.
6. Remove routine command toasts.
7. Make actual command input unmistakable.
8. Preserve Reference and Arrow-history behavior.
9. Clarify Assessment entry/closure.
10. Validate Focus Mode entry/exit and focus restoration.

**Regression boundary:** command vocabulary and assessment scoring unchanged unless separately approved.

### Phase C — Primary Learning / Progression

1. Reconcile stage counts.
2. Honest Customer Service track state.
3. Refine current-vector hierarchy.
4. Explicit next-action line only if grounded in real state.
5. Remove or correct fake route/stage affordances.
6. Clarify Assessment debrief scope and readiness language.

### Phase D — Supporting Workflow Screens

#### Scenarios
- reconcile summary values;
- real or honest filter/sort controls;
- long-title resilience;
- zero-result state.

#### Growth
- provenance;
- evidence vs interpretation;
- history count;
- backup honesty;
- trend semantics.

#### Tracking
- reduce KPI dominance;
- metric definitions;
- preserve chart/table pairing;
- text trend summary if useful.

### Phase E — Responsive Refinement

Test and adjust:

- 320
- 360
- 390
- 430
- 768
- 834
- 1024
- desktop

Prioritize Terminal over secondary content when width pressure occurs.

### Phase F — Polish + Accessibility Hardening

Only after the above:

- motion refinement;
- subtle hover/focus refinements;
- visual cleanup of decorative layers;
- drawer polish;
- final screen-reader tuning;
- final cross-route consistency pass.

---

## 19. VALIDATION PLAN

### V-01 — First-use Terminal trust test

**What:** Open Practice with zero prior commands.

**Where:** `/practice`.

**Devices/Viewports:** 320, 360, 390, 430, desktop.

**Expected:** neutral awaiting state; no error styling; no corrective message.

**Failure:** any red/error/corrective signal before a user action.

**Success criterion:** first-time user identifies the Terminal as ready and knows where to type.

### V-02 — Empty-command integrity

**What:** Submit whitespace/empty input.

**Expected:** no command event, no score change, no history row, no success/error toast.

**Failure:** any evidence or command mutation.

**Success criterion:** empty submission is a true no-op with concise inline correction.

### V-03 — Assessment state boundary

**What:** Use Reference in Learn and Practice, then switch to Assessment.

**Expected:** visible statement of carried state if the model intentionally persists it; or clean isolation if the engine contract says modes are independent.

**Failure:** UI says “No hints” while hidden state says otherwise, or score changes because of silent cross-mode bleed.

**Success criterion:** visible behavior matches approved assessment contract.

### V-04 — Terminal keyboard behavior

**Devices:** iOS Safari + Android Chrome.

**Viewports:** 320/360/390/430.

**Test:** focus input, type, open keyboard, rotate, submit, reopen, scroll history.

**Failure:** input hidden, layout jumps, bottom rail covers action, focus lost.

### V-05 — Command history

**Test:** several commands, Arrow Up/Down, edit recalled command, resubmit.

**Expected:** predictable history behavior; current command not announced as submitted evidence before submission.

### V-06 — Coach hierarchy

**Test:** command execution on desktop and mobile.

**Expected:** Terminal remains primary; latest result and Coach relationship is clear.

**Failure:** Coach competes with command entry or latest response.

### V-07 — Accessibility semantics

**Tools:** keyboard-only + NVDA/VoiceOver/TalkBack as available.

**Expected:** active tab/filter announced, progress meaningful, dialogs/drawers trap/restore focus, route change announces current page.

### V-08 — Contrast

**What:** Recompute all token pairings used by buttons, muted text, placeholders, state text, focus rings.

**Expected:** applicable WCAG contrast thresholds satisfied at actual rendered text size.

### V-09 — Typography and zoom

**Test:** 100%, 200%, 400% browser zoom where supported; Android text scaling where possible.

**Expected:** no loss of primary workflow and no clipping of Terminal command/input.

### V-10 — Tablet breakpoint validation

**Viewports:** 768, 834, 1024.

**Expected:** navigation chrome and content density read as one coherent responsive mode.

### V-11 — Scenario context resilience

**Test:** longest current scenario titles entering Practice.

**Expected:** title remains comprehensible, identifier is preserved if added, percentage does not collide.

### V-12 — Evidence provenance sweep

**Test:** inventory every number, status, readiness statement, trend label, and report statement in every route.

**Expected:** source and authority are known for every item.

**Failure:** unknown value presented as authoritative.

### V-13 — Data consistency sweep

**Test:** scenario totals, level totals, history counts, readouts, KPI labels.

**Expected:** all visible counts reconcile with data rendered or are explicitly labeled future/planned/local.

### V-14 — Reduced motion

**Test:** system reduced-motion enabled.

**Expected:** no important interaction depends on animation; caret, number, route, panel and smooth-scroll effects are reduced appropriately.

### V-15 — Arabic/RTL release test (only if Arabic is in scope)

**Test content:** Arabic narrative + English Amadeus command + airport/airline code + number/date.

**Expected:** Arabic layout direction is correct; command stays LTR; no bidi corruption; accessible reading order is logical.

---

## FINAL MASTER JUDGMENT

AeroBridge is already **visually distinctive, structurally promising, and unusually close to a professional aviation training workstation**. Its core advantage is not the number of screens or metrics. It is the combination of a believable operational identity with a real learning loop and a Terminal that is designed as a workstation rather than a decorative dashboard component.

The correct next move is therefore not reinvention.

It is controlled hardening:

**truthfulness → Terminal safety → state completeness → accessibility → typography → evidence provenance → content honesty → responsive validation → polish**

The strongest existing design should survive.

The unnecessary should be removed.

The uncertain should be tested.

The engine boundary should remain explicit.

The final AeroBridge target is:

> **Premium airline training workstation that happens to use a modern interface — not a dashboard that happens to contain aviation content.**

And the final implementation rule remains:

> **Evidence quality beats consensus.**
>
> **Independent corroboration beats repetition.**
>
> **One root problem = one canonical finding.**
>
> **Preserve what is strong unless there is a clear evidence-based reason to change it.**
>
> **When evidence is insufficient, say UNKNOWN / VALIDATION REQUIRED.**

**Design Status: NEEDS TARGETED REVISION.**
