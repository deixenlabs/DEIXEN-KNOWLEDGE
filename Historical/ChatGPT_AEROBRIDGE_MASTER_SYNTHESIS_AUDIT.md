# AEROBRIDGE — MASTER SYNTHESIS AUDIT

**Document type:** Independent Critical Re-evaluation, Synthesis & Prioritization

**Overall direction:** **Preserve and Refine**

**Design status:** **NEEDS TARGETED REVISION**

**Decision principle:** The UI may interpret engine state, but it must never invent engine truth.

**Evidence package reviewed:**
- Original AeroBridge prototype ZIP (`AEROBRIDGE_SOURCE_CLEAN.zip`)
- Original design ground truth (`ideas.md`)
- Seven rendered mobile screenshots covering Progression, Practice/Terminal, Scenarios, Growth Record ×3 tabs, and Progress Tracking
- Nine supplied Unified Audits: ChatGPT, Claude, DeepSeek, Gemini, Grok, Kimi, Manus, Qwen, v0.dev
- `MASTER SYNTHESIS AUDIT PROMPT.md`

**Adjudication posture:** Original intent + original requirements + actual source + rendered evidence outrank audit commentary. Repetition across audits is treated as a consensus signal, not independent proof. Conflicts are resolved by tracing the original artifacts and, where necessary, marking the decision **NEEDS VALIDATION**.

---

# A. Executive Decision

## A.1 Overall direction — **Preserve and Refine**

AeroBridge does **not** need a redesign, architecture reset, new information architecture, or replacement of the core visual system. The original design ground truth explicitly defines this as a reference-preservation project, requires the existing Flight Deck Console identity to remain the visual and interaction reference, and explicitly prohibits backend, authentication, payment, engine-architecture, and real-metric expansion. The existing source also contains a genuine five-area loop, local assessment persistence, context handoffs into Practice, a real terminal command history, an assessment debrief, and an accessible chart/table fallback.

The correct next stage is therefore a **controlled hardening pass**: remove false evidence and false confirmations, complete the most important state and accessibility semantics, make the Terminal more robust on narrow devices, establish a single semantic design-token contract, and make every prototype-only limitation honest.

The evidence is strong enough to proceed directly into implementation of the **confirmed P0 fixes** and most source-level P1 fixes. It is **not** sufficient to grant final design approval because live desktop/tablet behavior, native keyboard behavior at the declared device matrix, physical touch targets, screen-reader behavior, and full Arabic/RTL behavior have not been directly validated.

## A.2 The three most important decisions

### 1. **Trust and evidence integrity are the first gate. — MUST FIX**
The blank-command fallback is not a stylistic issue. `Home.tsx` converts empty input into `FQD`, records it, and allows it to influence assessment evidence. The first-use Coach simultaneously presents an error state that the trainee did not cause. Separately, seeded and hard-coded metrics are visually presented beside real local evidence without a sufficiently clear provenance contract. These defects conflict directly with the stated presentation-first requirement that mock/illustrative states remain clearly local and non-production.

**Implementation decision:** a blank input becomes an inline validation state and does nothing else; first-use Coach is neutral; every metric/action confirmation is either derived, explicitly local/illustrative, or removed/de-emphasized.

### 2. **Protect the Terminal as the primary workstation while hardening its state model and mobile behavior. — MUST FIX / SHOULD FIX / NEEDS VALIDATION by sub-issue**
The Terminal is the strongest product asset and must remain terminal-first. The source already contains deliberate mobile engineering: sticky input, safe-area treatment, 360px header restructuring, Focus Mode, command history, and a 16px intended command-input rule. The current cascade also introduces a later 15px mobile override, which means the normal mobile input resolves below the intended safety floor. The mobile screenshots additionally show excessive empty vertical space before the first useful response. However, the actual native-keyboard behavior is not available from the supplied screenshots and should not be “fixed” through a speculative redesign.

**Implementation decision:** preserve the current architecture; remove the 15px regression; reduce the fixed empty gap without shrinking the work surface; keep Coach subordinate; validate 320/360/390/430 with native keyboards before choosing any drawer/FAB pattern.

### 3. **Build one shared truth/state/accessibility foundation before cosmetic polish. — SHOULD FIX**
The source already contains a meaningful design system, but the stylesheet has accumulated a second semantic token layer, multiple late overrides, inconsistent small-type choices, missing tab/toggle semantics, incomplete overlay focus behavior, incomplete progress semantics, no explicit `<main>`/skip-link contract, and non-colour state cues that are inconsistent. These issues should be solved once at the shared primitive level rather than patched route-by-route.

**Implementation decision:** consolidate semantic tokens, establish the canonical state vocabulary and tab/button/overlay semantics, correct contrast/readability, then apply the same primitives to all five routes.

## A.3 What is not being recommended

This audit does **not** recommend:
- merging Growth and Progress Tracking into one analytics screen;
- adding a separate top-level Assessment route;
- adding autocomplete or new Amadeus commands;
- changing the scoring formula or `localStorage` schema;
- activating the unused MapView speculatively;
- adding a global persistent “Next Action” widget;
- adding a mobile Coach FAB/bottom sheet before user validation;
- adding a confirmation step to Finish Session;
- rebuilding the chart with a new library;
- introducing badges, streak gamification, leaderboards, confetti, or new vanity metrics;
- building a partial cosmetic Arabic/RTL implementation.

These recommendations would either contradict the original product intent, introduce unnecessary product surface, or solve an unproven problem at higher cost and risk than the evidence supports.

---

# B. Product and Design Principles to Preserve

## B.1 Flight Deck Console identity — **PRESERVE**

**What should be preserved**
- Deep navy operational foundation.
- Vector Blue interaction/route accent.
- Green / amber / red operational semantics.
- Monospace command/readout treatment.
- Restrained atmospheric/route imagery where it supports the task.
- Asymmetric console composition rather than generic SaaS cards.

**Why it is successful**
The visual language is highly differentiated and domain-appropriate. It reads as aviation training software rather than a generic LMS/dashboard. The original design ground truth explicitly identifies this as the reference to preserve.

**Acceptable modification**
Adjust luminance, token values, spacing, or contrast when accessibility or hierarchy requires it, provided the hue family and overall Flight Deck language remain recognizable.

**Do not change**
Do not replace the dark console with a lighter consumer-app aesthetic, remove the operational color semantics, or flatten the identity into generic cards.

## B.2 Terminal-first workstation — **PRESERVE**

**What should be preserved**
- Terminal as the primary workspace.
- Learn / Practice / Assessment mode structure.
- Command entry and history.
- Arrow Up/Down history recall.
- Focus Mode concept.
- Reference concept.
- Coach concept as subordinate support.
- Local/illustrative simulation disclosure.
- Assessment debrief and error taxonomy.

**Why it is successful**
The Terminal is the most differentiated interaction surface. It is a workstation, not a dashboard widget. The source contains actual command state, history, scoring, persistence, and contextual handoff behavior.

**Acceptable modification**
Improve state visibility, focus management, feedback placement, mobile density, and accessibility semantics.

**Do not change**
Do not cardify it, remove its work-surface dominance, or alter command matching/scoring merely to satisfy visual preference.

## B.3 End-to-end learning loop — **PRESERVE**

**Core loop:**
`Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action`

**What should be preserved**
- Progression provides orientation/resume context.
- Scenarios provide mission context and hand off into Practice.
- Assessment produces local evidence.
- Growth interprets evidence into patterns and targeted practice.
- Tracking exposes longitudinal signal.
- Contextual CTAs carry the learner back into Practice.

**Why it is successful**
This is a real product spine rather than disconnected pages. `setPracticeContext` handoffs and `localStorage` assessment records make the loop functionally meaningful.

**Acceptable modification**
Strengthen provenance and next-action explanations without adding global dashboards.

**Do not change**
Do not replace contextual handoffs with generic navigation, or merge all evidence into a single analytics destination.

## B.4 Evidence → Practice → Apply learning pattern — **PRESERVE**

The Growth Record pattern “Read evidence → Practice the gap → Apply in scenario” is one of the strongest pedagogical ideas in the prototype. It translates performance observation into behavior rather than rewarding score accumulation.

Acceptable changes are limited to making the evidence basis, period, and next behavior clearer. Do not turn Growth into an achievement dashboard.

## B.5 Mobile Practice engineering foundation — **PRESERVE**

Preserve the sticky command input, safe-area awareness, deliberate 360px header restructuring, centered Train priority in the bottom rail, and existing Focus Mode. These are confirmed design decisions, not accidental artifacts. The current source also contains a reduced-motion foundation that should not be stripped during refinement.

## B.6 Reduced-motion implementation — **PRESERVE**

The source contains a global reduced-motion catch-all plus multiple component-specific refinements, including explicit handling for the terminal caret. This is a genuine strength and should remain intact while other motion is reviewed.

## B.7 Progress Tracking chart + data-table fallback — **PRESERVE**

The chart is paired with a real text/table representation. This is the strongest reusable accessibility pattern in the current product. Do not replace it with a charting library merely for implementation fashion.

## B.8 Operational language and contextual verbs — **PRESERVE**

Words such as `Start`, `Resume`, `Review`, `Retry`, `Practice`, `Evidence`, `Readout`, `Route`, and `Next training move` fit the product. Some jargon needs light orientation for first-time users, but the identity should not be stripped out in favor of generic SaaS copy.

---

# C. Critical Problems

| ID | Problem | Evidence | User / Product Impact | Severity | Decision |
|---|---|---|---|---|---|
| AB-MS-001 | Empty/whitespace command becomes `FQD` and is recorded | `Home.tsx:275` submit path; assessment scoring uses command history; corroborated across multiple audits | Creates a false command/evidence event and can affect assessment integrity | Critical | **MUST FIX** |
| AB-MS-002 | Coach presents `FORMAT ERROR` before any command exists | `Home.tsx:311` fallback; visible in Practice screenshot | User is shown a failure they did not cause on the product’s primary screen | Critical | **MUST FIX** |
| AB-MS-003 | Illustrative/seeded metrics are visually mixed with real local evidence | `3/8`, `23/40`, fresh `86%`, `128/210`, seeded records, `Saudi readiness 24%`, streak language; source + screenshots | Breaks the distinction between demonstration data and trainee evidence | Critical | **MUST FIX** |
| AB-MS-004 | Actionable-looking controls claim actions that do not happen | Language, Profile, Search, My route, View map, Filters, Sort, Backup, etc. | Creates repeated false-affordance/false-confirmation behavior | High/Critical | **MUST FIX** |
| AB-MS-005 | Declared fonts are not provisioned in `index.html` | `client/index.html:10–14` contains only a commented font block; CSS references Space Grotesk/Cairo/IBM Plex Mono | The visual system is not deterministic; all typography QA is affected | High | **MUST FIX** |
| AB-MS-006 | Viewport restricts scaling with `maximum-scale=1` | `client/index.html:7–8` | Prevents/limits user zoom and compounds small-text accessibility risk | High | **MUST FIX** |
| AB-MS-007 | Mobile command input resolves to 15px in the final cascade | `index.css:363` declares 16px, later `index.css:384` overrides it to 15px | Regresses the deliberate mobile input safety rule and may trigger unwanted focus zoom | High | **SHOULD FIX** + device validation |
| AB-MS-008 | Tab/toggle semantics are not programmatically exposed | No `role=tab`, `aria-selected`, `aria-pressed`, `aria-expanded` in `Home.tsx`; multiple segmented controls | Screen-reader users cannot reliably identify selection state | High | **SHOULD FIX** |
| AB-MS-009 | Primary CTA and faint metadata contrast are below safe AA targets in audited values | `--blue #6f8fff` → white ≈ 2.98:1; `--text-faint #5d6a85` ≈ 3.18–3.66:1 across key dark surfaces | Repeated CTA and informational text may fail normal-text contrast | High | **SHOULD FIX** |
| AB-MS-010 | Terminal state model is richer in TypeScript than in the visible UI | `SystemState` has 14 states, but only a subset is clearly surfaced | Processing, recovery, interruption, completion, and assessment boundaries are ambiguous | High | **SHOULD FIX** |
| AB-MS-011 | Assessment mode can inherit prior history/hint state without a clear user-facing contract | mode switch resets `sessionComplete` only; history/hints persist; hint policy differs by reference entry point | Can create ambiguity about what exactly Assessment is measuring | High | **NEEDS VALIDATION** with immediate transparency mitigation |
| AB-MS-012 | Desktop/tablet runtime behavior is not visually validated | No supplied desktop/tablet screenshots; 740–1099 breakpoint behavior is inferred | Potential breakpoint mismatch cannot be adjudicated from source alone | High uncertainty | **NEEDS VALIDATION** |
| AB-MS-013 | “Operational readiness”/readiness-style language can overstate local heuristic meaning | Assessment/Growth wording and “Saudi readiness” framing; no authoritative competency definition in source | Learner may interpret local preview heuristics as qualification evidence | High | **MUST FIX** |
| AB-MS-014 | Service Track is structurally exposed without equivalent curriculum content | `levels` is technical; track toggle changes description more than curriculum | Implies curriculum parity that is not supported | Medium/High | **SHOULD FIX** |
| AB-MS-015 | Fallback surfaces are not part of the mounted shell and current 404 is visually unrelated | `App.tsx` mounts only `Home`; `ErrorBoundary.tsx` and `pages/NotFound.tsx` exist separately; ErrorBoundary exposes stack | Failure states can break product identity and may expose technical detail | Medium | **SHOULD FIX** |
| AB-MS-016 | Mobile Practice contains a large pre-output empty region | Practice screenshot + CSS `terminal-body`/spacing rules | Pushes the active input and latest useful result lower on a small screen | Medium/High | **SHOULD FIX** |

---

# D. Master Decision Matrix

> **Impact × Confidence × Feasibility** is the prioritization rule. Confidence is based on evidence quality/independence, not audit count alone.

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Technical Feasibility | Impact | Confidence | Cost | Risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MS-001 | Terminal | Reject blank/whitespace submit; never coerce to a command | MUST FIX | E4 source; E3 corroboration | False evidence | Strongly aligned | Very high | High | Very high | Low | Low | `Home.tsx:275–289`; audits |
| MS-002 | Terminal/Coach | Neutral first-use Coach; error only after real failed command | MUST FIX | E4 source + screenshot | False failure/trust damage | Strongly aligned | Very high | High | Very high | Low | Low | `Home.tsx:311`; Practice screenshot |
| MS-003 | Evidence | Establish provenance grammar and reconcile counts | MUST FIX | E4 source + screenshots | Contradictory learner truth | Strongly aligned | High | High | Very high | Medium | Medium | `Home.tsx` static + seed data |
| MS-004 | Interaction | Every actionable-looking control must act, be preview/unavailable, or be removed | MUST FIX | E4 handlers | False affordances | Strongly aligned | High | High | Very high | Low–Med | Low | `Home.tsx` handlers |
| MS-005 | Typography | Provision intended fonts or replace tokens with actual shipped stack | MUST FIX | E4 current `index.html` | Systemic identity/readability | Strongly aligned | High | High | High | Medium | Medium | `index.html:10–14`; `index.css:32–34` |
| MS-006 | Accessibility | Remove viewport scaling restriction | MUST FIX | E4 current `index.html` | Zoom accessibility | Strongly aligned | Very high | High | Very high | Low | Low | `index.html:7–8` |
| MS-007 | Typography | Raise meaningful metadata/readout minimums without destroying density | SHOULD FIX | E3/E4 token + screenshot review | Long-session readability | Aligned | High | High | High | Medium | Low–Med | `index.css`; contrast computations |
| MS-008 | Color | Fix primary CTA contrast and meaningful muted-text contrast | SHOULD FIX | E3 computed ratios | CTA/readability accessibility | Aligned | Very high | High | High | Low | Low | `--blue`, `--text-faint` |
| MS-009 | Tabs | Apply shared tab/toggle semantics according to behavior | SHOULD FIX | E4 zero semantic attributes | Screen-reader clarity | Strongly aligned | High | High | Very high | Low | Low | `Home.tsx` |
| MS-010 | Overlays | Add Escape, focus containment, focus restore, labelled semantics | SHOULD FIX | E3/E4 source gap | Keyboard/accessibility | Aligned | High | High | High | Medium | Medium | Shell/Focus/Reference |
| MS-011 | Progress | Give true progress visualizations progress semantics | SHOULD FIX | E4 `AnimatedBar` is `<i>` + label | Assistive understanding | Aligned | High | Med/High | High | Low | Low | `Home.tsx:139–142` |
| MS-012 | State | Define shared state matrix for first-use/empty/ready/processing/success/error/retry/interrupted/completed/review/locked/unavailable | SHOULD FIX | E4 `SystemState` vs render | Operational clarity | Strongly aligned | High | High | High | Medium | Medium | `Home.tsx:39` |
| MS-013 | Assessment | Surface mode/history/hint carry-over before first assessed command; defer scoring rule | NEEDS VALIDATION | E4 source + learning-UX analysis | Assessment validity | Aligned if transparent | High for UI mitigation; low for scoring decision | High | High | Low | Low | `Home.tsx:301–303`; assessment flow |
| MS-014 | Mobile Terminal | Keep sticky/safe-area architecture; remove 15px regression; reduce fixed empty gap | SHOULD FIX | E4 CSS + screenshots | Keyboard usability/scroll economy | Strongly aligned | High | High | High | Low–Med | Low | `index.css:350–405`; Practice screenshot |
| MS-015 | Mobile Terminal | Validate 320/360/390/430 with native keyboard before choosing Coach drawer/FAB | NEEDS VALIDATION | No physical-device evidence | Potential input/feedback loss | Aligned | Needs runtime | High | Medium | Low | Medium | Prompt/audits |
| MS-016 | Coach | Keep Coach; make it subordinate and remove duplicated system-response echo | SHOULD FIX | E3 source+visual reasoning | Clarity | Strongly aligned | High | Med/High | High | Medium | Low | Practice source/screens |
| MS-017 | Feedback | Remove routine per-command toast duplication; reserve toast for session-level events | SHOULD FIX | E3/E4 handlers + workflow reasoning | Cognitive fatigue | Strongly aligned | Very high | Medium | High | Low | Low | Practice submit path |
| MS-018 | Evidence | Fresh-session accuracy/readiness metrics should be neutral until real evidence exists | MUST FIX | E4 source + screenshots | False personal-performance signal | Strongly aligned | High | High | High | Very high | Low | Low | `Home.tsx:255–256` |
| MS-019 | Progression | Change `3/8` to data-owned count or clearly label future/sample status | MUST FIX | E4 source (`levels` has 6) + screenshot | Confusing progress truth | Strongly aligned | Very high | High | Very high | Low | Low | `Home.tsx:73–80,226` |
| MS-020 | Scenarios | Reconcile `23/40` and nonexistent “Exchanges & Refunds” framing | MUST FIX | E4 source + screenshot | False curriculum/status | Strongly aligned | Very high | High | Very high | Low | Low | `Home.tsx:82–88`, scenario UI |
| MS-021 | Growth | Reconcile `LOG 04/12`; derive shown counts from data | SHOULD FIX | E4 screenshot/source | Evidence confusion | Strongly aligned | Very high | Medium | High | Low | Low | Growth source |
| MS-022 | Growth/Tracking | Keep as separate views; clarify distinct jobs | REJECT | Product intent + IA + evidence | Preserves role clarity | Strongly aligned | High | Medium | High | Low | Low | `ideas.md` + route model |
| MS-023 | Service Track | Honest preparation/unavailable state until curriculum exists | SHOULD FIX | E3 source + screen | Prevents curriculum misrepresentation | Aligned | High | Medium | High | Low–Med | Low | `levels` + track switch |
| MS-024 | Arabic | Stop claiming completed language switch; defer full i18n/RTL to explicit scope decision | MUST FIX | E4 handler + no `dir`/i18n | Product honesty | Strongly aligned | High for interim; low for full build | High | Very high | Low | Low | `Home.tsx:164`, `index.html` |
| MS-025 | Navigation | Keep five-workspace model and centered Train priority | PRESERVE | Ground truth + source | Maintains orientation | Strongly aligned | Existing | High | Very high | Low | Low | `ideas.md`; `Home.tsx:59–65,183–185` |
| MS-026 | Navigation | Do not treat historical 4-column bottom-nav claim as a current defect | REJECT | Full CSS cascade | Prevents unnecessary fix | Strongly aligned | N/A | Low | Very high | None | None | `index.css:313–325,375` |
| MS-027 | Mobile session state | Do not call session readout “hidden” in final cascade; validate density and readability instead | REJECT | Full CSS cascade | Avoids fixing a non-defect | Aligned | High | Medium | High | Low | Low | `index.css:351,382,404` |
| MS-028 | Design system | Promote strongest `--ab-*` semantic values into canonical global tokens; remove duplicate namespace after migration | SHOULD FIX | E4 CSS | Maintains consistency | Strongly aligned | High | Medium | High | Medium | Medium | `index.css:328–343` |
| MS-029 | Responsive | Treat tablet 740–1099 as NEEDS VALIDATION, not as automatically broken | NEEDS VALIDATION | E4 breakpoints; no screenshots | Unknown | Aligned | Needs runtime | Medium/High | Medium | Low | Medium | `index.css`; screenshots missing |
| MS-030 | Responsive | Validate long Scenario → Practice titles at narrow widths | NEEDS VALIDATION | E4 context flow + narrow layout | Potential clipping | Aligned | High | Medium | High | Low | Low | `Home.tsx` scenario data + task strip |
| MS-031 | Learning UX | Do not enforce sequencing in Practice until content/product owner confirms intended pedagogy | NEEDS VALIDATION | E4 source; C2 insight | Could alter learning model | Must preserve current modes | Medium | Medium | High | Medium | Low | `sequenceError` condition |
| MS-032 | Learning UX | Keep existing assessment scoring formula unless product/engine review separately changes it | PRESERVE | E4 score implementation + ground truth | Protects regression safety | Strongly aligned | Existing | High | Very high | Low | Low | `assessmentScore` |
| MS-033 | Learning UX | Clarify “Operationally ready”/readiness wording as local unless authoritative rule exists | MUST FIX | E4 copy + no authority definition | Overstates competency | Strongly aligned | High | High | High | Low | Low | Assessment/Growth copy |
| MS-034 | Motion | Preserve reduced-motion foundation; do not add new decorative motion | PRESERVE | Direct source + multiple audits | Accessibility/comfort | Strongly aligned | Existing | Medium | Very high | None | Low | `index.css` reduced-motion blocks |
| MS-035 | Data viz | Preserve chart + native table fallback | PRESERVE | Direct source | Accessibility and meaning | Strongly aligned | Existing | High | Very high | None | None | Tracking view |
| MS-036 | Map | Do not activate unused MapView without product evidence | REJECT | E4 import trace + no curriculum need | Avoids scope/architecture drift | Strongly aligned | Low | Medium | Very high | None | Low | `Map.tsx`, `App.tsx`, `Home.tsx` |
| MS-037 | Architecture | Do not rewrite routing, localStorage, or engine architecture as part of this revision | REJECT | Ground truth + source | Regression containment | Strongly aligned | Existing | High | Very high | None | Low | `ideas.md`, `Home.tsx` |
| MS-038 | Error recovery | Mount/style AeroBridge-aware ErrorBoundary before production handoff, but do not expose raw stack traces | SHOULD FIX | Current `ErrorBoundary.tsx`; not mounted | Failure trust | Aligned | High | Medium | High | Low–Med | Low | `App.tsx`, ErrorBoundary |
| MS-039 | 404 | Do not import generic light-themed NotFound into the current visual system without redesigning it to Flight Deck language | SHOULD FIX | Current `pages/NotFound.tsx` | Identity break on fallback | Strongly aligned | High | Medium | High | Medium | Low | `pages/NotFound.tsx` |
| MS-040 | Dead code | Document/clean unused MapView only after roadmap owner decides whether it is intentionally retained | COULD IMPROVE | E4 import trace | Maintainer clarity | Aligned | High | Low | High | Low | Low | `Map.tsx` |
| MS-041 | Session timer | Start fresh local session at 0:00 or explicitly mark seeded/demo time | SHOULD FIX | E4 `useState(272)` + screenshot/audits | False session duration | Strongly aligned | Very high | Medium | High | Low | Low | Practice source |
| MS-042 | Error taxonomy | Remove/resolve dead `hint-dependency` category only after deciding whether richer hint evidence is actually intended | COULD IMPROVE | E4 enum vs assignment logic | Minor taxonomy mismatch | Aligned | Medium | Low | Medium | Low | Low | `ErrorKind`, Assessment debrief |

### Matrix adjudication notes

1. **No decision is accepted because “most audits said so.”** The highest-confidence decisions are those independently verified in the original source or directly visible in the supplied screenshots.
2. **Several audit claims were explicitly downgraded after cascade tracing.** In particular, the current bottom rail is five columns; the current Practice session readout is restored by a later higher-specificity rule; the terminal caret is covered by the reduced-motion rules. Those stale claims are not carried forward as active defects.
3. **Kimi’s numerical scorecard is not used as a product verdict.** The score is an audit opinion, and some of its architecture framing does not map cleanly to the supplied source package. Source-level claims are retained only where directly corroborated.

---

# E. Required Changes by Priority

## E.1 P0 — Blocking / Must Fix

### P0-1 — Empty command safety

**Objective**
Prevent the UI from creating a command or evidence event that the trainee did not enter.

**Current problem**
`command.trim().toUpperCase() || "FQD"` turns blank input into a legitimate command path.

**Exact change**
- Guard `submitCommand` immediately after trim.
- If empty/whitespace: do not call command evaluation, do not append to history, do not increment score/log, do not persist evidence, do not emit success toast.
- Show inline validation in the terminal input region: e.g. `NO ENTRY · TYPE A COMMAND`.
- Preserve focus in the input.

**Must remain unchanged**
- AN / SS / FQD / FXP matching.
- Existing command responses.
- Assessment scoring formula.
- `localStorage` structure.
- Context handoffs.

**Reason**
This is the highest-confidence, highest-impact defect in the package and is directly verified in source.

**Dependencies**
None for the safety guard; regression testing required.

**Risks**
Low. The guard affects only blank/whitespace input.

**Priority**
P0 / MUST FIX.

### P0-2 — Neutral first-use Coach

**Objective**
The first screen state must not show an error the user has not caused.

**Exact change**
- Replace the `latestEntry` fallback `FORMAT ERROR · CHECK ENTRY` with a neutral state.
- Use neutral styling; do not inherit the red error token.
- Keep the existing guidance concept, but make it orientation/action focused.
- Render error styling only when a real failed command exists.

**Must remain unchanged**
- Error taxonomy.
- Real failed-command feedback.
- Coach concept.

**Reason**
It is a pure trust defect on the primary surface with almost no implementation risk.

**Dependencies**
None.

**Risks**
Low.

**Priority**
P0 / MUST FIX.

### P0-3 — Evidence provenance and count reconciliation

**Objective**
Every visible metric and readiness statement must have a traceable owner.

**Exact change**
Adopt a compact provenance vocabulary:
- `ILLUSTRATIVE` — static preview/sample value.
- `LOCAL EVIDENCE` — persisted in the local preview session.
- `CALCULATED` — derived from currently loaded local data.
- `HISTORICAL` — explicitly historical/local record.
- `AUTHORITATIVE` — reserved for a future source that is actually authoritative.

For every current metric:
- derive it from the data it claims to summarize; or
- mark it as illustrative/local; or
- remove it if there is no defensible owner.

Specific corrections:
- Progression `3 / 8` → derive from `levels.length` or clearly mark the number as a future curriculum concept backed by explicit content ownership. The current source only defines six levels.
- Scenarios `23 / 40` → do not present as current scenario completion evidence; reconcile with the five defined scenarios and actual local scenario state.
- Growth `LOG 04 / 12` → derive from actual rendered/persisted history or change copy to an honest count.
- Fresh Practice `Accuracy 86%` → show `—` until a real local submission produces a score.
- `128 / 210`, `24% Saudi readiness`, streaks, and similar preview values → mark as illustrative or remove unsupported readiness language.

**Must remain unchanged**
- Presentation-first preview intent.
- Existing useful sample visuals.
- Real localStorage evidence.

**Reason**
The product is allowed to use mock data; it is not allowed to make mock data look like authoritative trainee evidence.

**Dependencies**
Product/content owners for any claim that requires an authority definition.

**Risks**
Low–Medium: some copy changes may change what a screenshot looks like; preserve hierarchy, not misleading numbers.

**Priority**
P0 / MUST FIX.

### P0-4 — False affordance and action-confirmation sweep

**Objective**
Make every active-looking control truthful.

**Exact change**
For every secondary control, make one of three decisions:
1. perform the promised action;
2. explicitly state `Preview`, `Unavailable`, or `Coming soon` and use neutral feedback;
3. remove/de-emphasize the control.

Specific current decisions:
- EN/AR → honest roadmap/preview until full scope exists.
- Search → preview/unavailable or real scoped search; do not claim search completed.
- Profile → non-actionable identity display if no profile workspace exists.
- My route → real navigation or remove/de-emphasize.
- View map → anchor to the existing stage section or remove; do not activate external map architecture speculatively.
- See all stages → only keep if it meaningfully expands/collapses content.
- Scenarios Filters → remove duplicate action if the visible filter tabs are the actual control.
- Sort → wire to existing sort fields or label unavailable.
- Backup → never say a backup was created unless bytes/state were actually written to a backup destination.
- View history/evidence/patterns → route/select the real available evidence surface or remove.

**Must remain unchanged**
- Navigation model.
- Real contextual CTAs.
- Presentation-first boundary.

**Reason**
False confirmations compound trust loss more than any single visual defect.

**Dependencies**
Case-by-case product decisions for unsupported capabilities.

**Risks**
Low if de-emphasized honestly; medium if real functionality is added without product scope.

**Priority**
P0 / MUST FIX.

### P0-5 — Typography provisioning

**Objective**
Make the declared typography system deterministic.

**Current problem**
`index.css` declares Space Grotesk, Cairo, and IBM Plex Mono, but `client/index.html` contains only a commented font-loading example. No local `@font-face` contract is present in the supplied source.

**Exact change**
Choose one supported provisioning path:
- self-host approved font files in the project; or
- use an approved external font-loading path that the share-preview deployment explicitly permits; or
- change CSS tokens to the actual shipped fallback stack if the product intentionally does not ship those fonts.

Do not silently leave the declared names unresolved.

**Must remain unchanged**
- Display/mono role separation.
- Arabic font role if Arabic becomes active.

**Reason**
Typography affects layout metrics, visual fidelity, contrast perception, and long-session readability.

**Dependencies**
Deployment/asset ownership.

**Risks**
Medium if external assets are introduced into a share-preview environment; low if self-hosted and tested.

**Priority**
P0 / MUST FIX.

### P0-6 — Remove viewport scaling restriction

**Objective**
Restore user zoom ability.

**Exact change**
Remove `maximum-scale=1` from the viewport definition. Do not add a replacement restriction.

**Must remain unchanged**
Mobile layout strategy and 16px command-input floor.

**Reason**
Current source explicitly restricts scaling and the product already has small metadata text.

**Dependencies**
None.

**Risks**
Low; verify no primary workflow becomes unusable at 200–400% zoom.

**Priority**
P0 / MUST FIX.

---

## E.2 P1 — High-Value Improvements

### P1-1 — Shared accessibility semantics

**Objective**
Make the shell and reusable controls understandable without visual styling.

**Exact change**
- Add `<main id="main-content">`.
- Add a skip-to-main link.
- Add route-change heading/status focus.
- Add `aria-current` to the desktop side navigation.
- Implement tab semantics for panel-switching groups: `role=tablist`, `role=tab`, `aria-selected`, `aria-controls` and associated panels.
- Use `aria-pressed` for toggle/filter groups where the behavior is toggle-like rather than panel switching.
- Add accessible semantics to `AnimatedBar` when it represents actual progress.
- Add dialog/drawer naming, Escape, focus containment, and return-focus behavior.

**Must remain unchanged**
Visual tab styling and route architecture.

**Reason**
Solve semantics once and reuse them.

**Dependencies**
Shared component primitives.

**Risks**
Medium if tab behavior is implemented as a visually identical but semantically incorrect pattern. Select semantics based on actual behavior.

**Priority**
P1.

### P1-2 — Contrast and readable type floor

**Objective**
Maintain operational density while removing inaccessible text/CTA combinations.

**Exact change**
- Recalculate contrast using final computed colors and final font sizes.
- Raise primary CTA contrast to at least 4.5:1 for its actual rendered text size.
- Raise meaningful `--text-faint` uses to at least 4.5:1 against the actual surfaces when the text is normal-size information.
- Establish a documented minimum: instructional body generally ≥14px; functional metadata generally ≥11–12px; command/result text generally ≥13–15px depending on density.
- Do not enlarge purely decorative micro-labels if they are not carrying information.

**Must remain unchanged**
Dense operational metadata where it is truly auxiliary.

**Reason**
The problem is not “the UI is too small” in general; it is that informative text currently depends on sizes/contrast that are too weak.

**Dependencies**
Font provisioning first.

**Risks**
Medium if sizes are globally increased. Use semantic roles, not blanket scaling.

**Priority**
P1.

### P1-3 — Terminal state contract

**Objective**
Make the Terminal explain what is happening and what the trainee can do next.

**Canonical state vocabulary**
- `FIRST USE`
- `EMPTY`
- `READY`
- `PROCESSING`
- `SUCCESS`
- `PARTIAL / REVIEW`
- `INVALID / SYNTAX ERROR`
- `SEQUENCE ERROR`
- `RECOVERABLE ERROR`
- `INTERRUPTED`
- `ASSESSMENT ACTIVE`
- `COMPLETED`
- `LOCKED`
- `UNAVAILABLE`

For every rendered state, define:
- label;
- text/icon/shape cue;
- colour/tone;
- allowable action;
- whether it changes evidence/score;
- accessibility announcement policy.

**Do not invent processing behavior** if the current engine has no processing state. Use the state matrix to define the presentation contract once the underlying trigger exists.

**Priority**
P1.

### P1-4 — Mobile Terminal hardening

**Objective**
Keep the Terminal usable while preserving workstation identity.

**Exact change**
- Remove the later 15px mobile input override; final normal mobile font-size should be ≥16px.
- Keep sticky input and safe-area positioning.
- Replace the fixed empty terminal gap with flexible/capped spacing.
- Keep the latest result and command input accessible before the optional Coach.
- Retain one-line session orientation at narrow widths.
- Preserve 360px header stacking.
- Do not replace the architecture with JavaScript-driven viewport manipulation unless physical tests show the current model fails.

**Priority**
P1.

### P1-5 — Coach hierarchy

**Objective**
Make Terminal output the source of truth and Coach the interpretation layer.

**Exact change**
- Terminal owns the response.
- Coach explains why it matters and what to do next.
- Remove duplicated system-response echo from the Coach where it exactly repeats Terminal output.
- On mobile, Coach may be collapsed/subordinate, but do not introduce a new FAB/sheet pattern until the native-keyboard workflow is tested.
- In Assessment, suppress shortcut content but retain necessary orientation/status.

**Priority**
P1.

### P1-6 — Assessment mode transparency

**Objective**
Prevent hidden state carry-over from being mistaken for a clean assessment boundary.

**Exact change now**
Before the first Assessment command after a mode switch, state what carries over, especially any existing hint count or command history.

**Deferred product decision**
Whether scoring should isolate history/hints by mode is a learning/data-model decision and is not resolved by this visual audit.

**Priority**
P1 UI mitigation; underlying scoring rule = NEEDS VALIDATION.

### P1-7 — Feedback budget

**Objective**
Prevent routine command feedback from appearing in three places.

**Exact change**
- Keep command result in Terminal history.
- Keep interpretation in Coach.
- Reserve toast for session-level events, e.g. Assessment saved.
- Downgrade no-op messages from `success` to neutral informational copy, or remove them.

**Priority**
P1.

### P1-8 — Honest readiness language

**Objective**
Prevent local heuristic scores from reading like qualification decisions.

**Exact change**
Replace or scope “Operationally ready”, “Saudi readiness”, and similar statements unless Product/Content provides a real competency definition and authority.

Prototype-safe alternatives are evidence-scoped language such as `Strong result`, `Review one workflow pass`, `Local session signal`, or similarly bounded wording — but only where the existing source meaning supports it.

**Priority**
P1.

---

## E.3 P2 — Optional / Later Improvements

### P2-1 — Design token consolidation

Merge the stronger `--ab-*` values into one canonical semantic token system. Do not delete the newer values simply because they have a different namespace. Promote the deliberate refinement into the canonical layer, then remove duplicate namespace usage.

### P2-2 — Route/shell orientation cleanup

Add persistent but restrained “where you are / what you are doing / what next” orientation. Do not create a new global dashboard widget.

### P2-3 — Service-track preparation state

Add a clear `Customer Service track — content in preparation` state rather than displaying technical milestones under both track labels.

### P2-4 — Growth mobile parity

Move essential hover-only insight into a selected/touchable detail state. Hover can remain an enhancement on pointer devices.

### P2-5 — Progress visualization restraint

Reduce purely decorative KPI clip-path/ornament where it competes with the operational readout. Keep route motifs and meaningful visual identity.

### P2-6 — Session timer honesty

Start a new local session at 0:00 or label the timer as part of seeded/demo preview data. Do not show a fresh-session timer that looks like elapsed user activity.

### P2-7 — Assessment taxonomy cleanup

Resolve the unused `hint-dependency` error kind only after deciding whether richer hint evidence is actually intended. Do not add engine logic solely to make the legend look complete.

### P2-8 — Fallback identity

Mount/style the ErrorBoundary and update the 404 surface before production handoff so failure states remain in the AeroBridge visual language and do not expose raw stacks. This is not required to redesign the main workflow.

---

# F. Component-Level Specifications

## F.1 Shared Topbar

**Current state**
Brand, route context, EN/AR toggle, search, profile.

**Problem**
Several controls are cosmetic or informational while visually presenting as functional.

**Decision**
Preserve topbar structure; correct utility truthfulness.

**Layout**
Keep existing horizontal compact composition. Do not add another row.

**Spacing**
Preserve current tight utility spacing; ensure icon hit areas are accessible even when the visual icon remains compact.

**Typography**
Readable route title; utility labels can remain compact if nonessential. Do not use unreadable metadata for actionable controls.

**Color**
Keep Flight Deck tokens. Active language should not use “success” semantic unless the language actually changed.

**Dimensions**
Interactive hit areas should be at least 44×44px on mobile where feasible, even if the visible glyph is smaller.

**Interaction**
- Language: roadmap/preview until actual i18n exists.
- Search: real or honest preview.
- Profile: informational identity or real profile.
- Menu: real drawer interaction with focus management.

**Responsive**
At ≤390px, preserve the current compact layout; avoid squeezing the Terminal context out of the viewport.

**Accessibility**
Accessible names, visible focus, drawer semantics, Escape, focus return.

**Preserve**
Brand lockup, route context, compact console language.

**Reject**
Adding extra top-level navigation or a large global search/dashboard surface.

## F.2 Primary / Operational Button

**Current state**
Blue CTA with white text.

**Problem**
Reported contrast ≈2.98:1 for normal-size button text.

**Decision**
Adjust background/value contrast until final pair passes 4.5:1 at rendered text size.

**Layout / Dimensions**
Preserve current compact visual height; use adequate hit area padding on mobile.

**Interaction states**
Default / hover / active / disabled / loading must all be distinguishable without relying only on colour.

**Preserve**
Vector Blue family and luminous operational quality.

**Reject**
Oversized consumer-style CTA redesign.

## F.3 Tabs / Segmented Controls

**Current state**
Plain buttons with active CSS classes.

**Problem**
No programmatic selected state.

**Decision**
Implement semantics based on behavior:
- Mode and panel-switching controls: tab pattern.
- Metric switch/filter controls: toggle/pressed semantics where appropriate.

**Interaction**
Support keyboard movement appropriate to the chosen semantic pattern; selected state announced.

**Responsive**
Preserve horizontal compactness and allow overflow where the current design already intends it, without clipping active states.

**Reject**
A one-size-fits-all “all buttons are tabs” implementation.

## F.4 Terminal Panel

**Current state**
Deep workstation surface, history, input, footnote, Focus Mode.

**Decision**
Preserve structure and deepen the state contract.

**Layout**
Terminal receives the dominant width. Coach remains subordinate.

**Spacing**
Remove fixed empty pre-output void that wastes mobile height. Preserve enough output room for meaningful responses.

**Typography**
Commands/readouts mono; input ≥16px on mobile.

**Interaction**
Submit → processing (only if real trigger exists) → result → next move. Empty submission → inline validation only.

**States**
READY, EMPTY, SUCCESS, ERROR, REVIEW, ASSESSMENT ACTIVE, COMPLETED, plus validation-required processing/interrupted states.

**Accessibility**
Semantic history, appropriately scoped live announcements, input label, focus state, Focus Mode entry/exit.

**Preserve**
Arrow Up/Down recall, Focus Mode, local simulation disclosure, terminal-first identity.

**Reject**
Autocomplete, extra dashboards inside the Terminal, changing command semantics as a cosmetic fix.

## F.5 Command Input

**Current state**
Sticky mobile input, 16px intended font, compact Execute button.

**Decision**
Make 16px the true final mobile floor; retain sticky/safe-area behavior.

**Interaction**
- Blank = no-op + inline validation.
- Valid = existing command evaluation.
- Invalid non-empty = existing syntax/error path.
- Prevent duplicate submission if/when a processing state exists.

**Accessibility**
Clear label, visible focus, keyboard operation, sufficient target size.

**What to preserve**
Input prominence and command recall.

## F.6 Coach Panel

**Current state**
Callout + “system response” style output.

**Problem**
First-use fabricated error and duplication of Terminal truth.

**Decision**
Coach = interpretation + next operational move.

**Layout**
Desktop: subordinate adjacent panel. Mobile: subordinate/collapsed after latest result. Exact drawer/FAB pattern = NEEDS VALIDATION.

**Interaction**
Coach updates from latest meaningful state, not from the absence of state.

**Assessment**
No shortcut hints; retain orientation.

**Accessibility**
If collapsible, real disclosure semantics and focus behavior.

**Reject**
Full removal of Coach from the product.

## F.7 Progress / Data Visualization Primitive

**Current state**
`AnimatedBar` renders as an `<i>` with an accessible label but no progressbar role.

**Decision**
Where a bar semantically represents progress, expose `role="progressbar"` plus min/max/current and a meaningful name.

**Preserve**
Chart + table fallback pattern.

## F.8 Evidence / Metric Cards

**Current state**
Mixture of computed local values and static preview values.

**Decision**
Add quiet provenance ownership to every meaningful metric.

**Layout**
Do not add a new panel per provenance label. Use compact microcopy near the value or in an evidence context header.

**Interaction**
A metric that is a real action trigger should navigate to the evidence/behavior that owns it.

**Reject**
Adding more KPI tiles to demonstrate completeness.

## F.9 Drawers / Reference / Focus Mode

**Current state**
Visual/interaction patterns exist; full focus contract is incomplete.

**Decision**
Add Escape, focus containment when appropriate, trigger-focus restoration, accessible naming, and clear exit.

**Do not assume** Focus Mode is a modal dialog if it is actually a workspace state. Implement the semantics appropriate to the behavior.

## F.10 ErrorBoundary / NotFound

**Current state**
ErrorBoundary exists but is not mounted by `App.tsx`; it displays a generic light UI and raw stack. `NotFound` is a generic light UI.

**Decision**
Treat these as P2 production-hardening surfaces. Keep out of the current main-flow redesign scope, but style them in the Flight Deck language before production handoff.

**Reject**
Exposing raw stacks or switching the main product to generic fallback aesthetics.

---

# G. Screen and Flow Changes

## G.1 Shared Shell

**Current issue**
Strong shell but utility false affordances and incomplete accessibility landmarks.

**Decision**
Keep five workspaces, desktop sidebar, mobile bottom rail, centered Train priority.

**Hierarchy change**
`Current route → current task → supporting evidence → next action → secondary utilities`.

**Layout**
No new global dashboard region.

**Content priority**
Route identity first; utility actions second.

**Interaction**
All utility controls are real or honestly unavailable.

**Navigation**
Keep current route model; improve `aria-current`, focus, deep-link and browser-history behavior.

**Responsive**
Desktop side-rail; mobile rail; tablet = validate, do not invent.

## G.2 Progression

**Current issues**
- `3/8` conflicts with six defined `levels`.
- View map/My route/See all stages are not all meaningfully load-bearing.
- Service track does not have equivalent curriculum content.

**Decision**
Preserve Resume-first hero and stage map.

**Hierarchy**
Current vector → current evidence → Resume → upcoming stage → longer-range map.

**Content priority**
Current stage and its action outrank total stage count.

**Interaction**
Locked stages explain unlock rule inline; current stage opens targeted Practice.

**Navigation**
Resume and current vector remain the main transition into Practice.

**Flow**
Stage totals derive from current data or are explicitly labeled as preview/future.

**Responsive**
At 320/360, prevent stage list from visually overpowering current task.

## G.3 Practice / Terminal

**Current issues**
Blank-command FQD, fabricated Coach error, state fragmentation, mobile density/keyboard uncertainty, duplicate toasts, mode/hint ambiguity.

**Decision**
Primary P0/P1 workstream.

**Hierarchy**
Session identity → task/mode → state → output → input → next move → Coach/reference support.

**Layout**
Do not shrink Terminal into a card. Coach remains subordinate.

**Interaction**
Empty no-op, valid command path unchanged, mode boundaries explicit.

**Navigation**
No new Assessment route.

**Flow**
Assessment remains a mode within Practice.

**Responsive**
320/360/390/430 native keyboard tests required before choosing any new mobile Coach pattern.

## G.4 Scenarios

**Current issues**
Hard-coded totals, nonexistent summary category, duplicate Filters control, non-working Sort, narrow-width title risk.

**Decision**
Keep Mission File framing and Scenario → Practice handoff.

**Hierarchy**
Scenario identity → state → skills/difficulty/time → mission action → supporting details.

**Interaction**
Filters and Sort are real or honest preview/unavailable. Provide zero-result state.

**Flow**
Scenario ID/context should survive into Practice where supported by the current data flow.

## G.5 Growth Record

**Current issues**
Evidence provenance, LOG mismatch, Backup overclaim, hover-dependent detail.

**Decision**
Keep Record / History / Reports and the learning-loop strip.

**Hierarchy**
Evidence → pattern → gap → practice action.

**Interaction**
Tabs use real semantics. Essential insights are accessible without hover.

**Navigation**
Practice CTA carries the relevant context.

**Responsive**
Prevent KPI clipping and long-scroll loss of the next action.

## G.6 Progress Tracking

**Current strengths**
Real local-record computation, chart + table, metric switcher, next action.

**Decision**
Keep it separate from Growth.

**Reason**
Growth is immediate pedagogical interpretation; Tracking is longitudinal evidence/trend. Combining them would remove the distinction instead of solving it.

**Hierarchy**
Skill meaning → behavioral implication → trend → next action.

**Interaction**
Metric switcher semantics; table remains accessible fallback.

**Responsive**
Validate chart/labels at 320–430 and table access.

## G.7 Assessment Flow

**Current issue**
Assessment is a mode, not a route, but the user-facing boundary is too implicit when state carries over.

**Decision**
Keep Assessment inside Terminal. Add an explicit entry contract.

**Content**
State what is preserved/reset, what hints are permitted, and what is being evaluated.

**Important boundary**
Do not change scoring logic in this revision. Any scoring-model change requires a separate product/engine decision.

## G.8 Cross-Screen Evidence Loop

**Decision**
Protect this as a regression-critical transition contract:
- Progression → Practice context remains correct.
- Scenario → Practice preserves scenario context.
- Growth/Tracking → Practice opens the relevant targeted context.
- Assessment → local evidence → Growth/Tracking remains intact.

Any visual refactor that breaks these handoffs is a regression even if the screen looks better in isolation.

---

# H. Responsive, Accessibility, and State Requirements

## H.1 Responsive requirements

### Desktop — ≥1100px
- Persistent sidebar remains.
- Terminal is the primary work area.
- Coach is subordinate and does not consume more visual weight than the Terminal.
- Secondary metrics remain secondary to the task.
- Focus Mode preserves session identity and clear exit.

### Tablet — 740–1099px — **NEEDS VALIDATION**
- Render at 768, 834, and 1024.
- Do not invent a third navigation system before observing failure.
- Check whether mobile rail + denser content still reads as one coherent workstation.
- If Terminal becomes too narrow, reduce Coach breadth before reducing command readability.

### Mobile — ≤739px
- Five-item rail remains intact.
- Train remains centered and visually primary without gamification.
- Sticky command input stays above the safe-area inset.
- Command font final computed size ≥16px.
- Critical state never disappears solely because the width is narrow.
- Coach remains subordinate.
- Avoid fixed empty Terminal gaps that push the latest result off-screen.

### 390 / 360px
- Preserve the current header reflow pattern.
- Keep session/readout state visible.
- Ensure mode controls, input, execute, and Focus Mode remain operable.

### 320px
- Treat as a first-class test target.
- No horizontal scroll.
- No clipped command field or execute action.
- No overlapping header controls.
- Latest meaningful output remains discoverable.

## H.2 Accessibility requirements

- `<main id="main-content">` plus skip link.
- Correct `aria-current` in all primary navigation.
- Correct tab/toggle semantics based on behavior.
- Progress visuals expose progress semantics.
- Focus-visible state remains high-contrast.
- Drawers/reference/focus surfaces have accessible names and appropriate Escape/focus return behavior.
- Every operational state uses **color + text and/or icon/shape**.
- Informational text meets AA contrast at final rendered size.
- Frequent mobile controls have ≥44×44px effective target area where feasible.
- Chart always has accessible text/table fallback.
- Terminal errors are announced with appropriate urgency; routine successes do not spam assertive announcements.
- Reduced-motion support remains intact.
- Zoom remains available.

## H.3 State requirements

### First-use
- Neutral.
- No error styling.
- Shows task/mode and next action.

### Empty input
- Inline validation.
- No history change.
- No score change.
- No persistence change.
- No success toast.

### Ready
- Explicit `READY` semantics.
- Input discoverable.

### Processing
- Only display when a real processing trigger exists.
- Duplicate submission prevented while processing if the engine can be processing.

### Success
- Result visible in history.
- Text/icon success label.
- Coach interprets, not duplicates.

### Invalid / Error
- Error type visible.
- What happened + why + next action.
- Recovery action clear.

### Review / Partial success
- Do not imply pass/fail binary if the engine exposes partial evidence.
- Keep status and next move explicit.

### Interrupted
- Preserve context if the existing state model supports it.
- Recovery path explicit.

### Assessment active
- State that assessment is active.
- State hint policy.
- State whether prior session activity carries forward.

### Completed
- Score/result and next move.
- Evidence provenance clear.

### Locked / Unavailable
- Tell user why.
- Do not claim the missing capability exists behind the control unless it actually does.

---

# I. Explicit Rejection List

| ID | Rejected Recommendation | Source | Reason for Rejection | Future Validation Needed? |
|---|---|---|---|---|
| RJ-01 | Merge Growth Record and Progress Tracking into one analytics screen | Gemini and related IA suggestions | Changes role distinction; Growth = pedagogical interpretation, Tracking = longitudinal trend; original five-area model is intentional | No immediate validation; keep separate |
| RJ-02 | Add a separate top-level Assessment route | Several audit proposals/alternatives | Assessment is already a mode inside the Terminal; a new route would weaken workstation continuity | No |
| RJ-03 | Add command autocomplete | Qwen conflict-resolution section | Conflicts with recall-based learning and would change pedagogy without evidence | Only if Product/Content changes the learning model |
| RJ-04 | Add Pause/Resume engine semantics | Qwen conflict-resolution section / some audit ideas | Requires engine/state truth not present in the supplied product boundary | Only with engine decision |
| RJ-05 | Activate the unused MapView because “View map” exists | Various map observations | An unused component proves implementation residue, not learning value; activation adds dependencies and scope | Only if curriculum/product owner approves map learning value |
| RJ-06 | Add a global persistent Next Action widget | Kimi/Qwen-style suggestions | Duplicates contextual next actions and risks dashboardization; current CTAs already carry context | Yes, only if contextual CTA tests show continuity failure |
| RJ-07 | Add a mobile Coach FAB/bottom sheet immediately | Gemini/DeepSeek/Qwen-style suggestions | Adds a new interaction surface before the actual native-keyboard flow is tested | Yes — validate the current subordinate flow first |
| RJ-08 | Remove Coach entirely in Assessment | Some conflict proposals | Assessment needs support suppression, not loss of orientation/status; removing it entirely is broader than the evidence supports | No; use compact locked/support state |
| RJ-09 | Add two-click Finish Session confirmation | Kimi-style safety suggestion | Finish Session already has preconditions; no demonstrated destructive-action problem justifying extra friction | No |
| RJ-10 | Replace hand-built chart with a chart library | General polish recommendations | Existing chart already works and has an accessible data-table alternative; library migration is not a current blocker | Only if future interaction requirements exceed current implementation |
| RJ-11 | Add badges, streak gamification, confetti, leaderboards, or engagement metrics | General UI polish suggestions | Contradicts professional workstation identity and original ground truth; no evidence they improve competence | No |
| RJ-12 | Build the Customer Service curriculum now | Multiple audit content suggestions | Curriculum/content authority is not supplied; UI cannot invent it | Yes — only after content owner provides curriculum |
| RJ-13 | Change scoring weights/formula to “fix” visual/state problems | Scattered audit ideas | Violates engine boundary and regression safety | Only in separate product/engine review |
| RJ-14 | Treat current five-item bottom rail as a 4-column production defect | v0/Kimi-style historical claim | Later cascade rules establish five columns; treating it as current fact would fix a stale rule rather than the final rendered state | Regression check only |
| RJ-15 | Treat session readout as simply hidden on mobile | Several stale audit claims | Later Practice-scoped rule restores display; actual issue is density/readability, not simple absence | Responsive validation at narrow widths |
| RJ-16 | Add more decorative motion because the product should feel “premium” | Visual-polish suggestions | Reduced-motion and operational identity favor purposeful rather than decorative animation | No |

---

# J. Validation Plan

| Validation ID | Decision Being Tested | Objective | Validation Method | What to Measure | Success Criteria | What Would Change the Recommendation |
|---|---|---|---|---|---|---|
| V-01 | Blank input must be a no-op | Prove evidence cannot be fabricated from empty input | Prototype test in Learn/Practice/Assessment | History length, score, hint count, localStorage, toast count, focus | No state/evidence mutation; inline validation shown | Any legitimate engine contract requiring blank commands would require a separate engine decision |
| V-02 | First-use Coach must be neutral | Remove false first-use failure | Fresh session render | Error color/copy before input | No error-styled or error-worded Coach content before a real failed command | If a product owner proves a seeded “diagnostic error” is intentional, it must be renamed and explicitly labeled as seeded, not user-caused |
| V-03 | Evidence provenance grammar | Reconcile all numbers | Fixture sweep: empty, one-record, seed, multi-record | Every number/status/source owner | No unexplained authoritative-looking value | A metric may remain illustrative only if its purpose and owner are explicitly documented |
| V-04 | Primary CTA contrast | Meet final AA | Automated contrast calculation + visual inspection | Ratios at actual rendered size | ≥4.5:1 for normal text | Only a legitimate large-text treatment can alter threshold |
| V-05 | Faint text contrast/type floor | Preserve density without inaccessible labels | CSS audit + rendered screenshot pass | Font sizes, ratios, line wrapping | Meaningful informational text meets approved floor and contrast | If user testing demonstrates a documented different density requirement, adjust role-specific scale rather than lowering accessibility below AA |
| V-06 | Font provisioning | Confirm declared fonts actually render | Browser DevTools + network/build inspection | Computed `font-family`, loaded assets | Space Grotesk / IBM Plex Mono / Cairo resolve when in scope | If deployment constraints prohibit the fonts, update design tokens to the actual supported stack rather than pretending |
| V-07 | Zoom accessibility | Restore user zoom | Real iOS/Android + browser zoom | Pinch/zoom behavior, 200/400% | Zoom works without loss of core workflow | If a specific browser proves a hard conflict, redesign only the affected responsive component, not zoom restriction |
| V-08 | Tab/toggle semantics | Screen-reader and keyboard selection | NVDA / VoiceOver / TalkBack + keyboard | Announced role, selected state, keyboard navigation | User can identify selected control and activate every group | If a control does not behave as a tab, use pressed/toggle semantics instead |
| V-09 | Overlay focus behavior | Prevent focus loss | Keyboard + screen reader | Focus entry, trap, Escape, return | No focus escape while modal-like surface is open; focus returns | If Focus Mode is confirmed as a non-modal workspace, use workspace semantics rather than dialog trap |
| V-10 | Mobile Terminal keyboard behavior | Prove current architecture or expose failure | Android Chrome + iOS Safari at 320/360/390/430 | Input reachability, viewport jump, output visibility, Execute reachability | No clipping/jump/occlusion; latest result remains understandable | If current architecture fails, then consider a tested drawer/sheet or viewport-specific change |
| V-11 | Mobile dead-space reduction | Reclaim useful work area without shrinking Terminal | Compare fresh + 4-command Practice renders | Empty gap height, latest result visibility, scroll distance | No large dead band; Terminal still reads as workstation | If removing the gap harms output comprehension, restore only the minimum needed output floor |
| V-12 | Assessment carry-over | Determine whether mode switch affects validity | Controlled session: Learn → Practice → Assessment | Prior commands, hints, score, completion | User sees exactly what carries over before first assessed command | If Product/Engine defines mode-isolated records, then state model may be changed in a separate approved engine pass |
| V-13 | Practice sequencing | Decide whether sequence guidance belongs in Practice | User test with deliberate out-of-order commands | Error comprehension, recall quality, frustration | Decision based on learning outcome, not visual consistency | If Practice users benefit from soft coaching, add non-scored guidance only |
| V-14 | Tablet layout | Confirm breakpoint behavior | 768 / 834 / 1024 live captures + task walkthrough | Navigation identity, Terminal width, hierarchy | No transitional “mobile chrome + desktop density” confusion | If failure is systematic, refine breakpoint composition without adding a third navigation architecture |
| V-15 | Long Scenario context | Prevent task-strip collision | 320/360/390/430 with longest titles | Wrapping, truncation, CTA collision | Title remains understandable and context/ID is preserved | Only the title presentation changes; routing/context contract stays |
| V-16 | Growth/Tracking closure | Confirm evidence-to-action continuity | Complete assessment → Growth → Tracking → Practice | Record identity, source evidence, CTA context | Same record/context remains coherent end-to-end | If mismatch occurs, fix data/context ownership, not visual duplication |
| V-17 | Arabic/RTL scope | Decide release contract | Product/content decision + real Arabic fixture if enabled | `lang`, `dir`, font, bidi, command/code isolation | Either genuine bounded RTL works or AR is honestly unavailable/roadmap | Full implementation only after Content/Architecture scope is approved |
| V-18 | Reduced motion | Preserve existing strength | OS reduced motion on/off | Caret, smooth scroll, number animations, panels | No meaningful training information depends on motion; unnecessary motion is removed | Only fix offending animation; do not remove useful static state cues |
| V-19 | Fallback identity | Keep errors inside product language | Forced ErrorBoundary + 404 test | Visual identity, stack exposure, recovery | No raw stack shown; fallback remains Flight Deck | If production routing architecture changes, fallback integration can be revisited |
| V-20 | Clean handoff portability | Verify asset dependencies | Fresh clone/build with no hosted runtime context | Fonts, `/manus-storage` images, analytics script, map deps | Design renders without silent missing asset regressions | External asset paths must be replaced/documented before handoff |

---

# K. Implementation Handoff

## K.1 Engineering sequence

### Phase 0 — Freeze the contract
1. Freeze command vocabulary, scoring formula, `localStorage` shape, route model, and valid context handoffs.
2. Record the baseline AN → SS → FQD → FXP regression behavior.
3. Record the current screenshots as regression references.

### Phase 1 — P0 truth and safety
1. Guard empty command.
2. Neutralize first-use Coach.
3. Reconcile/label evidence values.
4. Sweep false action confirmations.
5. Remove `maximum-scale=1`.
6. Provision intended fonts or explicitly redefine the shipped stack.
7. Remove unsupported readiness wording.

### Phase 2 — P1 shared semantics
1. Establish shared type/contrast tokens.
2. Implement tab/toggle semantics.
3. Add main/skip/route focus.
4. Add overlay focus/Escape/restore semantics.
5. Add progressbar semantics.
6. Add non-colour state markers.

### Phase 3 — P1 Terminal
1. Remove mobile 15px input regression.
2. Reduce fixed empty gap without reducing the work surface.
3. Implement state matrix.
4. Clarify Assessment boundary.
5. Reduce per-command toasts.
6. Subordinate Coach.
7. Validate Focus Mode and keyboard behavior.

### Phase 4 — P1/P2 evidence and screen honesty
1. Progression count/data ownership.
2. Scenarios count/filter/sort honesty.
3. Growth history/provenance/Backup.
4. Tracking metric definitions and table semantics.
5. Service track preparation state.
6. Readiness language scope.

### Phase 5 — Validation-gated responsive pass
1. 320 / 360 / 390 / 430 mobile.
2. 768 / 834 / 1024 tablet.
3. 1280 / 1440+ desktop.
4. Native keyboard tests.
5. Screen reader tests.
6. RTL fixture if Arabic is approved.

### Phase 6 — Low-risk polish
Only after P0/P1 are stable:
- token cleanup;
- decorative reduction where it competes with data;
- hover/touch parity;
- minor spacing/radius normalization;
- taxonomy/hygiene cleanup.

## K.2 Regression rules

Every change must preserve:
- command responses for existing valid commands;
- assessment scoring outputs;
- localStorage record shape;
- route transitions;
- `setPracticeContext` behavior;
- Growth/Tracking read-through from stored records;
- the five-workspace navigation model;
- Focus Mode concept;
- chart/table relationship.

## K.3 Source-control discipline

Do not mix P0 truth/safety changes with broad decorative redesign. Keep changes reviewable by concern:
- truth/safety;
- accessibility/state;
- responsive Terminal;
- evidence screens;
- low-priority polish.

## K.4 Asset / deployment handoff

The current source references hosted `/manus-storage/...` assets and an analytics placeholder script. Before the prototype becomes a portable reference implementation, document or replace those dependencies. A clean handoff should not silently depend on a preview-host runtime to preserve the appearance.

---

# L. Open Questions and Assumptions

| ID | Question / Assumption | Why It Matters | Decisions Affected | What Is Needed |
|---|---|---|---|---|
| OQ-01 | Is “Saudi readiness” an actual defined product competency or only preview language? | Current UI gives it authoritative tone without a definition | Readiness copy, metrics, Growth/Progression | Product/Content definition or remove the claim |
| OQ-02 | Are seeded metrics intended as permanent preview fixtures? | Determines whether to label or derive them | Progression, Scenarios, Growth, Practice footer | Explicit content/data ownership |
| OQ-03 | Should Assessment isolate hints/history from Learn/Practice? | Affects assessment validity | Hint score and session state | Product + engine decision |
| OQ-04 | Is Reference-open the same thing as consuming a hint? | Current handlers differ | Hint accounting | Product/learning rule |
| OQ-05 | Should Practice teach sequencing or only Assessment evaluate it? | Can materially change pedagogy | `sequenceError` behavior outside Assessment | User/learning test |
| OQ-06 | What is the release scope for Arabic? | Full RTL/i18n is architecture/content work | EN/AR control, font/Cairo, bidi | Product/content/engineering scope decision |
| OQ-07 | Is the unused MapView intentionally retained for a later curriculum surface? | Determines remove vs retain dead code | View map action, component hygiene | Roadmap owner decision |
| OQ-08 | Are the `/manus-storage/...` image assets guaranteed in the target handoff environment? | Missing assets change the visual reference | Atmosphere/route imagery | Deployment/asset contract |
| OQ-09 | Should the session timer represent actual local elapsed time? | Current fresh-session 4:32 looks like prior activity | Practice trust | Product UX decision; default should be 0 unless explicitly seeded |
| OQ-10 | What is the intended authoritative source for curriculum stages and skill mappings? | Prevents UI from inventing curriculum | Progression/Scenarios/Growth | Content-owned curriculum source |
| OQ-11 | Is the current `NotFound` surface actually reachable under production routing? | It is generic and light-themed if it becomes reachable | Failure-state visual identity | Routing/QA validation |
| OQ-12 | Should ErrorBoundary suppress raw stack traces in all environments or only production? | Current component exposes the stack | Error UX and privacy/trust | Environment policy; production should not show raw stack |

### Assumptions used in this synthesis

**ASSUMPTION A1 —** The current five-route/workspace model in `Home.tsx` is the intended product information architecture because it is explicitly supported by `ideas.md` and the source navigation structure.

**ASSUMPTION A2 —** The current local assessment model is a prototype simulation, not an authoritative airline qualification engine, because the design ground truth explicitly says the preview is presentation-first and prohibits real metrics.

**ASSUMPTION A3 —** When the source does not provide a real engine state, the UI should not create one merely to make the prototype feel complete.

**ASSUMPTION A4 —** “Illustrative / local” labels are acceptable product language because the original ground truth explicitly requires mock and illustrative states to remain clearly local and non-production.

---

# M. Final Recommendation

## Implement

The following should definitely be changed in the next revision:

1. Reject blank/whitespace command submission.
2. Remove fabricated first-use Coach error state.
3. Establish evidence provenance and reconcile hard-coded counts/metrics.
4. Remove false success/created/completed claims from non-functional controls.
5. Remove viewport scaling restriction.
6. Provision the declared fonts or change the design tokens to the actual shipped stack.
7. Remove the 15px mobile command-input regression and keep the intended ≥16px mobile floor.
8. Fix primary CTA and meaningful muted-text contrast.
9. Implement shared tab/toggle, progress, landmark, focus, and overlay accessibility semantics.
10. Establish and implement the Terminal state contract.
11. Clarify readiness language and keep it local/illustrative unless an authority exists.
12. Make Progression / Scenarios / Growth counts derive from owned data or explicitly local/illustrative fixtures.
13. Keep the mobile Terminal architecture while removing unnecessary fixed empty space.

## Preserve

Do not change:
- Flight Deck Console identity.
- Terminal-first hierarchy.
- Learn / Practice / Assessment mode structure.
- Command vocabulary and current valid command matching.
- Assessment scoring formula unless separately approved.
- `localStorage` evidence structure unless separately approved.
- Five-workspace navigation model.
- Context handoffs into Practice.
- Growth learning-loop pattern.
- Mission-file scenario framing.
- Progress Tracking chart + data-table fallback.
- Focus Mode concept.
- Command history recall.
- Safe-area-aware mobile input architecture.
- Reduced-motion foundation.
- Local/illustrative disclosure pattern.

## Defer

Postpone until the appropriate product/content owner decides:
- full Arabic/RTL implementation;
- Customer Service curriculum depth;
- Practice-mode sequencing feedback;
- hint-policy/scoring isolation across modes;
- MapView integration;
- new search/profile/backup capabilities;
- global Next Action widget;
- new scenario recommendation logic;
- broader curriculum provenance/calibration claims.

## Reject

Do not implement:
- redesign from scratch;
- merge Growth and Tracking into one analytics dashboard;
- separate Assessment route;
- command autocomplete;
- speculative map feature activation;
- gamification expansion;
- extra metrics without meaning/owner;
- confirmation friction on Finish Session without evidence;
- chart-library migration as a polish task;
- cosmetic Arabic toggle;
- architecture rewrite to solve UI issues;
- scoring changes to repair visual/state defects.

## Validate

The following must remain explicitly validation-gated:
- native keyboard behavior at 320/360/390/430;
- tablet composition at 768/834/1024;
- desktop render at ≥1100;
- screen-reader semantics and announcements;
- effective touch target size;
- Focus Mode entry/exit and overlay focus behavior;
- exact final font rendering;
- Arabic mixed-direction behavior if Arabic enters release scope;
- Assessment carry-over semantics;
- whether Practice should surface non-scored sequencing feedback;
- long Scenario → Practice context at narrow widths;
- clean handoff of hosted image/font assets.

## Is the evidence sufficient to proceed?

**Yes — sufficient to proceed to the next design-review / implementation stage for the confirmed P0 and source-verifiable P1 corrections.**

**No — not sufficient for final approval of the enhanced prototype.** Important runtime gaps remain: native keyboards, 320/360/390/430 behavior in real browsers, tablet and desktop visual composition, screen-reader behavior, effective touch targets, and any real Arabic/RTL release behavior.

The correct decision is therefore:

> **Proceed with targeted implementation of confirmed truth, safety, accessibility, typography, and state fixes. Do not expand product scope. Gate the next design approval on the validation matrix.**

---

# Evidence Adjudication Notes

## Source priority used

1. `ideas.md` — product intent and constraints.
2. Original prototype source and actual `client/index.html`.
3. Supplied rendered screenshots.
4. Existing technical behavior and implementation.
5. Nine Unified Audits as analytical evidence.

## Confirmed high-confidence source facts used in this audit

- `Home.tsx` defines five product views.
- `Home.tsx` defines six current `levels` but Progression renders `3 / 8 stages`.
- `Home.tsx` defines five scenarios while the Scenarios interface uses larger hard-coded totals.
- `assessmentScore()` derives accuracy, sequencing, hint score, and overall score from command history.
- Empty submission is converted to `FQD`.
- Practice first-use Coach falls back to error copy.
- The current `index.html` contains `maximum-scale=1`.
- The current `index.html` does not actually load the declared Space Grotesk / Cairo / IBM Plex Mono fonts.
- `ErrorBoundary.tsx` exists but `App.tsx` renders only `Home`.
- `NotFound.tsx` exists as a generic light-themed fallback.
- `Map.tsx` exists but is not imported into the current rendered application.
- The final CSS cascade contains five bottom-nav columns.
- The final CSS cascade restores the Practice session readout after the earlier mobile hide rule.
- The final CSS explicitly includes reduced-motion handling for the Terminal and other motion systems.
- The normal mobile Practice input has a later 15px declaration that overrides the earlier 16px rule.

## Audit conflicts intentionally resolved rather than merged

- **Bottom-nav “4 columns / 5 items”** → rejected as a current defect after full cascade tracing.
- **Session readout “hidden on mobile”** → rejected as a simple current defect; later Practice-scoped CSS restores it. Remaining issue is density/readability.
- **Caret ignores reduced motion** → rejected; source contains explicit reduced-motion handling.
- **Growth + Tracking must merge** → rejected; distinct user jobs and original five-area structure outweigh the consolidation suggestion.
- **Coach must be removed on Assessment** → rejected as excessive; suppress shortcuts, retain orientation.
- **Mobile Coach FAB/sheet must be added immediately** → deferred pending physical-device validation.
- **Illustrative metrics must all be deleted** → rejected; original ground truth permits presentation-first mock states. They must instead be honestly labeled or derived.
- **Fonts are definitely a rendered-runtime failure** → current source now proves the intended fonts are not linked in `index.html`; deployment runtime still needs a final computed-font check after provisioning.

## Why this audit is not a nine-report average

The nine reports were treated as evidence sources. Strong conclusions were promoted when they were independently supported by the actual prototype or screenshots. Minority findings were retained when they exposed a real source-level issue. Repeated claims that depended on the same stale selector or screenshot were not treated as independent proof. Unsupported suggestions were rejected rather than included for completeness.

---

# Final Quality Gate

- Original prototype reviewed: **YES**
- Original screenshots reviewed: **YES**
- Original design ground truth reviewed: **YES**
- All nine Unified Audits considered: **YES**
- Majority voting used: **NO**
- Confirmed problems separated from opinions: **YES**
- Six required decision classifications used: **YES**
- P0/P1/P2 prioritization included: **YES**
- Component-level guidance included: **YES**
- Screen/flow guidance included: **YES**
- Responsive requirements included: **YES**
- Accessibility requirements included: **YES**
- State requirements included: **YES**
- Rejection list included: **YES**
- Validation plan included: **YES**
- Open questions/assumptions included: **YES**
- Technical feasibility/cost/risk considered: **YES**
- Unsupported functionality invented: **NO**
- Redesign recommended without evidence: **NO**
- Remaining validation gaps explicitly identified: **YES**

# Final Master Principle

> **AeroBridge should become calmer, clearer, safer, and more truthful — not broader.**
>
> **The product already has the right identity and the right spine. The next version should harden what is real, expose what is local, remove what is fake, and validate what is still unknown.**
>
> **Evidence quality beats consensus. Independent corroboration beats repetition. One root problem gets one canonical decision. Preserve what works unless evidence clearly justifies change.**
