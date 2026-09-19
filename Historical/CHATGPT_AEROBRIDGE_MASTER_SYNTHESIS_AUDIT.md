Worked for 51s

AEROBRIDGE — MASTER SYNTHESIS AUDIT

Document type: Independent evidence-based adjudication and implementation handoff

Overall direction: Preserve and Refine

Design status: Needs targeted revision


---

A. Executive Decision

AeroBridge should be preserved and refined, not redesigned. The strongest evidence across the five Stage 3 audits is unusually consistent on the core product: the Flight Deck Console identity, terminal-first Practice workstation, Learn / Practice / Assessment structure, evidence-to-next-action loop, five-area navigation, Focus Mode, local-simulation disclosure, reduced-motion foundation, and chart-plus-accessible-table pattern are the parts worth protecting. The audits repeatedly reject dashboardization, new routes, gamification, autocomplete, speculative engine states, and other scope-expanding responses.

The highest-confidence defects sit at the trust boundary rather than in the visual concept. The empty command path is reported as converting whitespace into FQD, creating a real history/evidence event; the first-use Coach displays a red FORMAT ERROR before a trainee causes any error; headline values such as 3 / 8, 23 / 40, LOG 04 / 12, and fresh-session accuracy are presented without a sufficiently clear provenance contract; and multiple controls visually promise actions while only producing a toast. These are not cosmetic disagreements: they directly conflict with the product rule that the UI must not invent engine truth.

The three most important decisions are therefore: (1) eliminate false evidence and false failure states first; (2) establish a single provenance/state contract so every metric, action confirmation, and readiness statement has an identifiable owner; (3) harden accessibility, Terminal state semantics, and mobile behavior without changing the command evaluator, scoring formula, persistence model, route structure, or learning model. The audits consistently recommend deriving counts from real arrays where possible, relabeling deliberate sample content rather than deleting it, and keeping valid non-empty command behavior unchanged.

Implementation can proceed now on the confirmed P0 trust/evidence fixes and the source-backed P1 foundation. Final closure must remain validation-gated for native keyboard behavior, tablet/desktop composition, rendered typography, final contrast, screen-reader behavior, overlay focus behavior, and the product-owner decision on Arabic/RTL. The five audits repeatedly make the same distinction: these gaps do not block the hardening work; they block overclaiming that the work is finished.


---

B. Evidence and Adjudication Method

B.1 Evidence package

The Stage 4 corpus used for this adjudication consists of the five Stage 3 Unified Audits:

ChatGPT_AEROBRIDGE_MASTER_SYNTHESIS_AUDIT.md

Claude_AEROBRIDGE_MASTER_SYNTHESIS_AUDIT.md

GROK_AEROBRIDGE_MASTER_SYNTHESIS_AUDIT.md

MANUS_AEROBRIDGE_MASTER_SYNTHESIS_AUDIT.md

V0_AEROBRIDGE_MASTER_SYNTHESIS_AUDIT.md.md


Their supplied metadata shows distinct file sizes and the complete five-audit set.     

The five audits themselves describe a common underlying evidence package containing the prototype source, design ground truth, and seven mobile renders; their important methodological difference is not what they inspected, but how confidently they adjudicated what they found. The Stage 4 protocol requires source evidence to outrank audit repetition and explicitly forbids treating repeated claims as independent proof. 

B.2 Evidence hierarchy used

The hierarchy applied here is:

1. Direct prototype/source evidence cited by the audits


2. Original product/design intent as cited by the audits


3. Rendered evidence


4. Cross-audit agreement


5. UX/accessibility/learning interpretation



The governing rule is that direct implementation facts must not be overturned by repeated audit opinion, while product intent controls preservation/scope decisions unless there is explicit evidence that intent changed. 

B.3 How the five audits were treated

No majority vote was used. A finding was promoted when its underlying evidence survived cross-checking; a repeated claim without adequate proof was downgraded; a minority finding was retained when it exposed a defensible source-level issue; and recommendations that required new product capability were rejected when the evidence did not require them. This is particularly important for the stale CSS findings: the stronger audits explicitly traced the final cascade and rejected older claims about the bottom-nav column count, mobile session-readout visibility, and reduced-motion handling of the terminal caret.

B.4 Evidence classification

Class	Definition	Examples in this audit

E4 / Direct	A Stage 3 audit explicitly ties the claim to a concrete source file/line, rendered state, or source-level cascade finding and the claim is materially corroborated in the corpus.	Empty → FQD; first-use Coach error; count inconsistencies; toast-only controls; 15px mobile input override; absent tab semantics.
E3 / Strongly corroborated	The same conclusion is supported by materially different evidence types, such as source plus screenshot or source plus an independently traced cascade.	Empty-command path + visible Coach contradiction; mobile dead space + CSS spacing; contrast math + rendered visual risk.
E2 / Cross-audit analysis	Repeated analytical interpretation based on the same underlying evidence, without independent runtime proof.	Mobile keyboard concern, tablet composition, Coach placement preference, some readability judgments.
NEEDS VALIDATION	Important but not provable from the supplied corpus.	Native keyboard behavior, desktop/tablet composition, actual screen-reader output, exact production font rendering, Arabic scope.
REJECTED	Contradicted by stronger source/cascade evidence, conflicts with product ground truth, or expands scope without sufficient evidence.	Current “4-column nav bug,” “mobile readout is hidden,” “caret ignores reduced motion,” Growth/Tracking merge, speculative Map activation.


The Stage 4 protocol explicitly requires unavailable runtime/device evidence to be marked NEEDS VALIDATION, rather than upgraded by consensus. 

B.5 Important evidence conflict inside the corpus

One audit explicitly states that it could not independently inspect index.html, while other Stage 3 audits describe index.html as directly inspected and use it to support the font-loading and viewport conclusions. That is not a contradiction of the claim; it is a difference in inspection coverage. The final decision below therefore separates source-level presence of the defect as strongly supported from runtime deployment behavior as validation-gated.


---

C. Product and Design Principles to Preserve

C.1 Flight Deck Console identity — PRESERVE

Preserve: deep navy foundation, Vector Blue interaction language, green/amber/red operational semantics, monospace command/readout treatment, restrained atmospheric graphics, compact utility controls, and asymmetric workstation composition.

Why it succeeds: the audits consistently describe it as distinctive, operational, and domain-specific rather than generic LMS/SaaS styling. This identity also provides the visual grammar in which state, evidence, and workflow can be interpreted.

Acceptable modification: luminance/contrast changes, token consolidation, spacing cleanup, and reduction of ornament that does not communicate information.

Do not change: overall hue family, dark operational foundation, command/readout typography role, or console posture.

Evidence: all five audits preserve this principle and reject redesign/re-theming.

C.2 Terminal-first workstation — PRESERVE

Preserve: Terminal as the primary workstation; Learn / Practice / Assessment modes; command history; Focus Mode; Reference; Coach; sticky mobile command input; local-training disclosure.

Why it succeeds: it concentrates the actual training action at the center of the product and is the clearest differentiator between AeroBridge and a dashboard.

Acceptable modification: state clarity, hierarchy, spacing, accessibility semantics, mobile keyboard hardening, and Coach subordination.

Do not change: terminal primacy, command vocabulary, working command evaluator, or the three-mode learning concept.

The strongest audits explicitly describe the terminal as the architectural center and reject turning it into a small card or replacing it with a wizard.

C.3 Learn / Practice / Assessment — PRESERVE

Preserve: three-mode structure inside the Terminal, including different coaching/hint behavior where already supported.

Why it succeeds: it creates a meaningful progression from guided work to evaluation without introducing an additional route.

Acceptable modification: make the assessment boundary explicit and truthful about state carry-over.

Do not change: Assessment into a new top-level route, and do not alter scoring merely to solve presentation issues.

The audits reject the idea of a separate Assessment route and instead focus on the existing mode boundary.

C.4 Evidence → Practice → Apply loop — PRESERVE

Preserve: evidence interpretation followed by targeted practice and scenario application.

Why it succeeds: it transforms assessment into a next behavioral move rather than score accumulation.

Acceptable modification: strengthen evidence ownership, scenario identity, provenance, and CTA context.

Do not change: the loop into a global dashboard or generic “next action” widget.

The audits explicitly distinguish Growth as interpretation and Tracking as longitudinal signal, and reject merging them.

C.5 Local/illustrative simulation boundary — PRESERVE AND EXTEND

Preserve: existing explicit LOCAL TRAINING SIMULATION / ILLUSTRATIVE disclosure.

Why it succeeds: it correctly bounds the preview and tells the user that it is not a live production engine.

Acceptable modification: extend the same provenance discipline to numbers, records, readiness claims, and action confirmations.

Do not change: sample data into live-looking evidence without labeling.

The strongest recommendation across the corpus is derive first, label second, delete only if necessary.

C.6 Five-area navigation and Train priority — PRESERVE

Preserve: five-area model and centered Train/Practice priority.

Why it succeeds: it encodes the learning loop while giving the core workstation visual priority.

Acceptable modification: semantic navigation, route focus, touch targets, breadcrumb consistency, and CSS cleanup.

Do not change: the IA based on stale CSS interpretations.

The final-cascade adjudication explicitly rejects the historical “four columns for five items” claim.

C.7 Accessibility foundations — PRESERVE

Preserve: focus-visible behavior, reduced-motion support, chart/table fallback, existing live-region intent.

Why it succeeds: these are already stronger than many prototype implementations.

Acceptable modification: semantics, landmarks, progress semantics, focus containment, zoom, contrast, touch targets, and non-color state cues.

Do not replace: the chart/table pattern with a chart library without a real requirement.

The same-data table is repeatedly identified as a strength worth preserving.

C.8 Operational copy and evidence-to-next-action language — PRESERVE

Preserve: Start, Resume, Review, Retry, Practice, Evidence, Readout, targeted-practice wording.

Why it succeeds: it reinforces the product's operational character and keeps evidence tied to action.

Acceptable modification: scope readiness/certification language to what the local data can honestly prove.

Do not change: the product into generic SaaS copy.


---

D. Critical Problems

ID	Problem	Direct evidence	Impact	Severity	Confidence	Decision

AB-F01	Empty/whitespace submit becomes FQD, producing a genuine command/evidence path.	Home.tsx submit fallback is explicitly cited in multiple audits.	Fabricated training evidence; can alter score/history; violates core trust boundary.	Critical	Very High	MUST FIX
AB-F02	Fresh Practice shows red FORMAT ERROR · CHECK ENTRY before user error.	Source fallback plus screenshot evidence.	False first-use failure and immediate trust damage.	Critical	Very High	MUST FIX
AB-F03	Metrics/counters mix illustrative, seeded, and local values without a single provenance contract.	3/8, 23/40, LOG 04/12, fresh 86%, 128/210, readiness language.	Contradictory learner truth; user cannot tell sample from measured evidence.	Critical	Very High	MUST FIX
AB-F04	Controls visually imply actions while only showing success/info toasts.	Backup, Language, Search, View map, Filters, Sort, My route, section actions.	Repeated false affordances; especially serious for “backup”/completion claims.	High	Very High	MUST FIX for false success claims; SHOULD FIX for remaining stubs
AB-F05	Learn/Practice activity can carry into Assessment without a clear user-facing contract.	Shared commandHistory / hintCount, plus conflicting Reference/hint treatment.	Assessment credibility and learning validity.	High	High	SHOULD FIX + validation for final isolation/reset policy
AB-F06	Mobile command input resolves to 15px after cascade despite 16px intent.	Exact later-rule conflict documented by source trace.	Mobile ergonomics and potential focus-zoom risk.	High	Very High	MUST FIX
AB-F07	Primary CTA and meaningful muted text may fail AA at the actual rendered sizes.	Audits compute ~2.98:1 for primary button and ~3.18–3.66:1 for faint text.	Long-session readability and accessibility.	High	High	SHOULD FIX
AB-F08	Declared fonts are apparently not provisioned in the referenced index.html.	Multiple audits explicitly identify commented/absent font loading; one audit lacked direct index.html access.	Visual identity and layout metrics become deployment-dependent.	High	High	MUST FIX source-level; NEEDS VALIDATION at runtime
AB-F09	maximum-scale=1 is reported in viewport metadata.	Multiple audits explicitly cite the viewport setting.	Restricts user zoom.	High	High	MUST FIX
AB-F10	Tab/toggle/progress/landmark semantics are incomplete.	Missing tab semantics; bare progress primitive; absent main landmark reported by direct source audits.	Screen-reader and keyboard users cannot reliably perceive state.	High	High	SHOULD FIX
AB-F11	Mobile Terminal has a large pre-output work-surface gap; native keyboard behavior remains unproven.	Screenshot/CSS evidence plus explicit runtime gap.	Wastes constrained viewport and may hide useful output/input.	High	High for dead-space; Medium for keyboard failure	SHOULD FIX spacing; NEEDS VALIDATION keyboard
AB-F12	EN/AR appears cosmetic rather than a real language switch.	Toast/local-label behavior without demonstrated translation/RTL.	False feature promise; scope ambiguity.	High	High	MUST FIX honesty; full RTL NEEDS VALIDATION
AB-F13	Readiness/certification language can overstate the authority of local heuristics.	“Operationally ready” / “Saudi readiness” cited across audits.	User may interpret a preview heuristic as qualification evidence.	High	High	SHOULD FIX
AB-F14	Service Track structurally implies curriculum parity without equivalent curriculum evidence.	Technical milestones exposed under Service track.	Misrepresents available curriculum.	Medium–High	High	SHOULD FIX
AB-F15	Trend styling may map raw direction to good/bad rather than metric favorability.	Source-level finding cited by the stronger audits.	Learner can misread improvement/decline.	Medium	High	SHOULD FIX
AB-F16	Scenario handoff may pass a display title rather than stable identity.	Manus identifies setPracticeContext(selected.title) and provenance risk.	Potential loss of scenario/evidence lineage.	Medium–High	Medium–High	SHOULD FIX UI contract; engine mapping NEEDS VALIDATION
AB-F17	Fallback/404/error surfaces may break the Flight Deck identity.	ErrorBoundary/NotFound mounting/branding concerns are source-backed in the broader audits.	Failure states can damage trust or expose implementation detail.	Medium	Medium	SHOULD FIX
AB-F18	Desktop/tablet and native keyboard states are not actually demonstrated by supplied renders.	The audits explicitly identify no desktop/tablet captures and no open-keyboard screenshot.	Responsive decisions can otherwise become speculative.	High uncertainty	High	NEEDS VALIDATION



---

E. Master Decision Matrix

ID	Area / Owner	Specific decision	Classification	Evidence class	User impact	Design consistency	Technical feasibility	Confidence	Cost	Risk	Validation needed	What must remain unchanged

MD-01	Terminal / UI	Blank submit is a no-op with inline correction; remove fallback to FQD.	MUST FIX	E4	Very High	Strong	Very High	Very High	Low	Low	Automated + manual mode tests	Valid AN/SS/FQD/FXP matching; scoring; persistence
MD-02	Coach / UI	Fresh Coach is neutral; error styling requires a real failed entry.	MUST FIX	E3	Very High	Strong	Very High	Very High	Low	Low	Fresh-session render test	Coach interpretation after real responses
MD-03	Evidence / Content	Create one provenance grammar and reconcile visible counts.	MUST FIX	E3	Very High	Strong	High	Very High	Low–Med	Med	Content-owner review of future totals	Real local evidence and scoring formula
MD-04	Interaction / UI	Every action-looking control must act, become clearly preview/unavailable, or be removed.	MUST FIX for false success; SHOULD FIX otherwise	E3	High	Strong	High	Very High	Low–Med	Low–Med	Full click-through inventory	Working CTAs/handoffs
MD-05	Assessment / Learning UX	Make carry-over state explicit now; final reset/isolation rule requires product/learning validation.	SHOULD FIX	E3	High	Strong	Medium	High	Med	Med	Learn→Practice→Assessment test	Scoring formula and current modes
MD-06	Typography / UI	Restore intended font provisioning or explicitly define shipped fallback stack.	MUST FIX source-level; runtime NEEDS VALIDATION	E3	High	Strong	High	High	Low–Med	Low	Computed-font/browser test	Role separation and visual identity
MD-07	Accessibility / UI	Remove viewport zoom restriction.	MUST FIX	E3	High	Neutral	Very High	High	Low	Low	Real-device zoom test	Other viewport behavior
MD-08	Accessibility / UI	Correct tab/toggle/pressed/current semantics and progress semantics.	SHOULD FIX	E3	High	Strong	High	High	Low	Low	Keyboard + SR test	Visual tab grouping
MD-09	Accessibility / UI	Add main/skip/route-focus/focus-visible/focus-return contract.	SHOULD FIX	E3	Med–High	Strong	High	High	Low	Low	Keyboard + SR test	Existing focus-visible styling
MD-10	Accessibility / UI	Add non-color state cues and appropriate live-region urgency.	SHOULD FIX	E3	High	Strong	High	High	Low	Low	Screen-reader/grayscale test	Operational color language
MD-11	Terminal / CSS	Remove the later 15px mobile input override; preserve 16px.	MUST FIX	E4	High	Strong	Very High	Very High	Very Low	Low	Computed style + iOS/Android focus test	Sticky/safe-area architecture
MD-12	Terminal / Responsive	Reduce fixed dead-space without shrinking Terminal; keyboard behavior remains validation-gated.	SHOULD FIX + NEEDS VALIDATION	E3/E2	High	Strong	High	High	Low	Low–Med	320/360/390/430 keyboard-open	Terminal dominance
MD-13	Coach / Responsive	Keep Coach subordinate; do not introduce FAB/bottom-sheet as a default yet.	PRESERVE / NEEDS VALIDATION	E2/E3	Med	Strong	High	High	Low	Med	Post-fix task testing	In-flow Coach concept
MD-14	Content / UI	Readiness language must be explicitly local/preview unless backed by an authoritative definition.	SHOULD FIX	E3	High	Neutral	Very High	High	Low	Low	Product/content decision	Evidence-to-action copy
MD-15	Scenarios / UI	Reconcile Filters/Sort behavior; keep functional filter-tabs; wire only existing sortable fields.	SHOULD FIX	E3	Med	Strong	High	High	Low	Low	Click-through + data verification	Scenario list/mission flow
MD-16	Progression / Content	Replace false 3/8 framing with data-owned counts or explicitly future/illustrative copy.	MUST FIX	E3	High	Strong	Very High	Very High	Low	Low	Dataset/content check	Progression hierarchy
MD-17	Scenarios / Content	Replace or qualify 23/40 and unsupported category claims.	MUST FIX	E3	High	Strong	High	Very High	Low	Low	Dataset/content check	Existing scenarios
MD-18	Growth / Content	Derive LOG count; preserve Record/History/Reports separation.	SHOULD FIX	E3	Med–High	Strong	High	High	Low	Low	Evidence fixture sweep	Growth loop
MD-19	Navigation / IA	Keep Growth and Tracking separate.	PRESERVE	E3	High	Strong	Existing	Very High	None	Low	None unless task research changes	Five-area IA
MD-20	Map / Product	Do not activate unused MapView.	REJECT	E3	Low	Strong	N/A	Very High	None	Low	Roadmap decision only	Current scope
MD-21	Learning UX	Keep Assessment as a Terminal mode, not a new top-level route.	REJECT	E3	High	Strong	N/A	Very High	None	Low	None	Mode model
MD-22	Data viz / UI	Preserve chart + same-data table; no Recharts migration now.	PRESERVE / REJECT migration	E3	Med–High	Strong	Existing	Very High	None	Low	Only if new interaction needs emerge	Current chart semantics
MD-23	Learning UX	Do not add autocomplete or engine-level Pause/Resume.	REJECT	E3	High if implemented wrongly	Strong	N/A	Very High	None	High	Separate product/engine review only	Recall pedagogy; engine truth
MD-24	Design system / UI	Consolidate semantic tokens after P0/P1.	COULD IMPROVE	E3	Low direct	Strong	Medium	High	Med	Low	Visual regression after migration	Current hue/system
MD-25	Fallbacks / UI	Mount/style ErrorBoundary and Flight-Deck-aware NotFound when fallback paths are actually wired.	SHOULD FIX / validation-gated	E2/E3	Med	Strong	Medium	Medium	Low–Med	Low	Forced-error/404 test	Current visual identity
MD-26	Responsive / Runtime	Treat 740–1099px, 320px, and desktop as validation ranges, not assumed defects.	NEEDS VALIDATION	E2/E3	High uncertainty	Strong	Runtime	High	Low	Med	Full breakpoint matrix	IA and nav model



---

F. Required Changes by Priority

F.1 P0 — Blocking / Must Fix

P0-1 — Empty-command safety

Objective: No command event may exist without intentional user input.

Current behavior: whitespace is coerced into FQD.

Exact change: trim first; if empty, display inline validation, preserve focus, and return before command evaluation, history mutation, score mutation, hints, persistence, or success toast. Keep all non-empty commands unchanged.

Must remain unchanged: AN, SS, FQD, FXP, unknown-command behavior, scoring formula, localStorage structure, handoffs.

Dependencies: none.

Risks: low.

Acceptance criteria: blank/whitespace submit changes nothing except the visible validation state.

Regression tests: Learn, Practice, Assessment; mouse submit + Enter; verify history, score, hints, toast count, localStorage, and valid-command output.

P0-2 — Neutral first-use Coach

Objective: first use must not look like a user-caused failure.

Exact change: when there is no latest command entry, render neutral AWAITING COMMAND guidance. Error styling/content only when a real failed entry exists.

Must remain unchanged: post-error coaching and interpretation role.

Acceptance criteria: fresh session contains no red error/correction; a real invalid command still generates a real error state.

Regression tests: fresh render, valid command, invalid command, session completion.

P0-3 — Evidence provenance and count reconciliation

Objective: every number/status has a defensible owner.

Provenance vocabulary: LOCAL, ILLUSTRATIVE, CALCULATED, HISTORICAL, AUTHORITATIVE only when an actual authoritative source exists.

Exact change: derive counts from rendered arrays; otherwise qualify them as available-now/future/illustrative. Replace fresh-session fabricated 86% with —/No evidence yet; clarify seeded timer; remove or qualify unsupported readiness claims.

Must remain unchanged: real localStorage evidence, scoring formula, presentation-first sample content.

Dependencies: content owner for future curriculum totals and readiness definition.

Acceptance criteria: no hardcoded value visually reads as measured trainee evidence without provenance.

Regression tests: empty session, one-record session, seeded preview, multiple records; inspect every headline number.

P0-4 — False affordance and success-claim sweep

Objective: no control may imply an operation that did not happen.

Disposition per control: real action / clearly preview-unavailable-roadmap / remove.

Special rule: Backup may not claim a backup artifact unless one exists.

Must remain unchanged: primary working CTAs and context handoffs.

Acceptance criteria: every visible success toast corresponds to a verifiable state mutation or completed action.

Regression tests: click-through inventory across every screen and utility control.

P0-5 — Viewport zoom and font contract

Zoom: remove maximum-scale=1 if confirmed in final source.

Fonts: restore the declared families or revise tokens to the actual shipped stack.

Classification: source-level remediation is justified by the corpus; runtime rendered-font success remains validation-gated.

Regression tests: computed font family, network asset load, browser zoom 200%+, core reflow, iOS/Android zoom behavior.

P0-6 — Arabic honesty

Objective: stop claiming a language change that has not happened.

Exact change now: relabel/disable as Arabic — Roadmap / Preview, with neutral information feedback.

Do not do now: partial RTL, fake translation, mirrored-only layout, or pseudo-localization.

Dependencies: product scope decision for any real RTL/i18n program.

Acceptance criteria: activating AR never implies a successful language switch unless actual language/direction/content state changes.


---

F.2 P1 — High-value / Should Fix

P1-1 — Canonical state model

Define one shared UI state vocabulary:

first-use, empty, ready, processing only when a real trigger exists, success, partial/review, syntax error, sequence error, recoverable error, interrupted, assessment active, assessment complete, locked, unavailable, loading, no evidence yet, illustrative/sample.

The state model may describe only what the current local model can honestly expose.

P1-2 — Accessibility semantics

Add:

<main> and skip link

route heading focus

correct tab/pressed/current semantics according to actual control behavior

progressbar semantics

overlay focus entry/containment/escape/return

non-color state cues

accessible names for icon controls

appropriate live-region urgency


Do not blindly apply role="tab" to controls that are actually button groups.

P1-3 — Contrast and readable type floor

Target:

meaningful informational text ≥4.5:1 at final rendered size

primary CTA ≥4.5:1 unless it legitimately qualifies for a large-text exception

practical informational type floor around 12px

larger instructional reading text

preserve mono/display role separation


The exact final values must be validated after actual font provisioning because font metrics change rendering and wrapping.

P1-4 — Mobile Terminal hardening

Preserve sticky/safe-area architecture and 16px input. Remove the 15px regression. Reduce the fixed empty band without reducing Terminal dominance. Keep latest relevant output, active input, submit control, and session status reachable. Do not choose a Coach drawer/FAB pattern before runtime validation.

P1-5 — Coach hierarchy

Desktop: Terminal remains dominant, Coach subordinate.

Mobile: Coach remains in-flow/subordinate initially; collapse only if needed after validation. Do not introduce a FAB/bottom sheet simply because another audit suggested it. The corpus does not prove that trainees currently miss Coach guidance.

P1-6 — Assessment transparency

Before the first assessed command, show:

current mode = Assessment

hint policy

whether previous activity carries forward

whether switching modes changes the evidence boundary


Do not silently alter the scoring formula in this pass.

P1-7 — Scenario/data lineage

Where a handoff currently passes a title only, preserve the visible title but establish a stable UI-side context shape such as:

scenarioId / scenarioTitle / skillCode / sourceView / handoffReason

The mapping to authoritative curriculum semantics remains outside the current UI pass.

P1-8 — Service Track honesty

Show an honest unavailable/in-preparation state rather than presenting Technical-track milestones as if the Service curriculum exists.

P1-9 — Trend semantics

Color and tone must represent favorability, not simply numeric direction. A downward arrow should not look automatically positive.


---

F.3 P2 — Optional / Later

Only after P0/P1 are stable:

semantic token consolidation

documented spacing/radius/type scales

decorative KPI reduction where validated as noise

removal/documentation of dead MapView

Flight-Deck ErrorBoundary/NotFound polish

removal/justification of dead hint-dependency

minor pressed/disabled states and restrained motion refinement


These items are not blockers for trust, core usability, or evidence integrity.


---

G. Component-Level Specifications

G.1 Shared shell / Topbar

Current state: compact operational shell with language, search/profile-style controls.

Confirmed problem: some utility controls imply action they do not execute.

Decision: preserve composition; make every utility honest.

Typography: retain display/mono roles.

Interaction states: default, focus, unavailable/preview where necessary.

Accessibility: landmarks, names, current route state, keyboard reachability.

Provenance: actions themselves need truthful status language.

Preserve: identity, compactness.

Reject: utility expansion into new product surfaces.

G.2 Primary navigation / mobile rail

Current: five-item rail, Train centered.

Decision: preserve five-item model and Train emphasis.

Accessibility: aria-current, usable target area.

Important cascade adjudication: do not “fix” the stale 4-column claim; the stronger audits traced later rules that already establish five columns.

G.3 Primary buttons / operational CTAs

Problem: contrast and false-success messaging.

Decision: preserve operational verbs; fix contrast and state truth.

States: default, hover, active, disabled, focus-visible, completed, unavailable, preview.

Reject: changing the CTA language into generic SaaS copy.

G.4 Tabs / segmented controls

Current: visually tab-like groups.

Problem: missing programmatic selection semantics.

Decision: semantic pattern according to actual behavior.

Accessibility: tablist/tab where truly tabs; aria-pressed for toggle buttons; roving focus only where appropriate.

Reject: forcing a single ARIA pattern indiscriminately.

G.5 Terminal and command input

Current: full workstation, command history, sticky mobile input.

Confirmed problems: empty → FQD; 15px mobile override; fragmented state language.

Decision: non-destructive blank-input guard; 16px final mobile input; persistent status; preserve history recall.

Color: status uses color + text/glyph.

Interaction: Enter and button share the same validation path.

Reject: autocomplete and invented engine states.

G.6 Terminal history / response output

Preserve: history as the primary evidence trail.

Change: success/error language stays in history; Coach interprets rather than duplicates.

Accessibility: polite announcements for routine responses, stronger urgency for actual errors.

Regression: valid command transcripts must remain unchanged.

G.7 Coach panel

Current: interpretation/support surface.

Problem: fabricated first-use error and duplicated system response.

Decision: neutral first-use; real-error gating; subordinate hierarchy; compact assessment state.

Reject: default FAB/sheet until user/device validation demonstrates a need.

G.8 Reference drawer / Focus Mode

Preserve: current Focus Mode concept and Reference capability.

Change: verify accessible naming, focus entry, Escape, focus containment/restore as applicable.

State rule: do not invent “processing” or “paused” engine states merely to make Focus Mode feel more complete.

G.9 Progress rings / bars / chart

Current strength: same-data chart plus table fallback.

Decision: preserve.

Change: make data-bearing progress visuals semantically exposed.

Reject: chart-library migration without a new evidence-backed requirement.

G.10 Evidence / metric cards

Problem: sample and measured values share visual authority.

Decision: provenance becomes part of the component contract, not an afterthought.

Minimum provenance model: owner / source / period / status.

Preserve: card hierarchy and concise instrumentation.

G.11 Scenario list / mission detail

Problem: counters and action stubs may not reconcile.

Decision: derive counts from data; keep mission detail; wire only existing sortable/filterable fields; preserve contextual Practice handoff.

Validation: longest titles at 320–430px.

G.12 Growth Record

Preserve: Record / History / Reports separation and Read evidence → Practice the gap → Apply in scenario.

Change: reconcile history counts, provenance, Backup semantics, trend meaning.

Reject: merging into Tracking.

G.13 Progress Tracking

Preserve: longitudinal role and same-data chart/table pairing.

Change: provenance, trend semantics, route-line truncation only if confirmed, restrained ornament.

Reject: replacing it with generic analytics/dashboard architecture.

G.14 Language control

Current: cosmetic.

Decision: honest roadmap/preview state now; bounded real RTL only after scope approval.

Reject: pseudo-RTL or partial translation.

G.15 ErrorBoundary / NotFound

Current concern: possible off-brand or raw-error fallback.

Decision: validate mounted production path, then style within Flight Deck language and suppress raw stack exposure.

Classification: SHOULD FIX, but only once the actual fallback mounting path is confirmed.


---

H. Screen and Flow Changes

H.1 Progression

Current issue: progress framing can overstate curriculum scope.

Decision: derive current totals from actual data; use explicit future/illustrative language when larger curriculum totals are intentional.

Information hierarchy: current vector → active stage → evidence/next action.

Empty/locked: unavailable stages must say why.

Responsive: preserve current vertical composition; validate narrow widths.

Accessibility: current stage and progress semantics must be announced.

Preserve: route orientation and resume CTA.

H.2 Practice / Terminal

Current issues: empty-command mutation, false first-use Coach, mode-state ambiguity, mobile dead space, 15px input cascade, fragmented state messaging.

Decision: this is the primary hardening target.

Hierarchy: task context → mode → Terminal → input → subordinate Coach.

Empty: neutral and actionable.

Success: real command only.

Error: only after a real failed entry.

Assessment: explicit boundary.

Responsive: keyboard-open validation mandatory.

Preserve: command evaluator, history, Focus Mode, local disclosure.

H.3 Assessment

Decision: remain a Terminal mode.

Current issue: hidden state carry-over.

Required contract: show what is preserved, what is scored, hint status, and whether prior commands belong to the current assessed evidence.

Do not: move scoring or persistence architecture in this revision.

H.4 Scenarios

Current issues: false totals, duplicate Filters affordance, possibly weak context lineage.

Decision: use actual data, keep mission detail, wire existing fields, preserve Practice context.

Unavailable: unsupported filters/sort/navigation should not claim completion.

H.5 Growth Record

Current issue: metric/provenance ambiguity.

Decision: preserve Record / History / Reports; tighten evidence ownership; keep targeted practice CTA.

H.6 Progress Tracking

Current issue: metric meaning and decorative hierarchy.

Decision: preserve longitudinal trend role; make evidence ownership clearer; keep chart/table.

H.7 Shared shell/navigation

Decision: preserve five-area IA and centered Train. Fix semantics, focus, action honesty, and stale route-number language only where supported.

H.8 Cross-screen handoffs

The full loop must remain:

Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action

Regression must prove that contextual entry points remain intact. The audits explicitly warn against solving local UI problems by breaking this loop.


---

I. Responsive, Accessibility, and State Requirements

I.1 Responsive requirements

Directly observed / rendered

The supplied evidence is dominated by mobile renders. The audits specifically identify the visible mobile Terminal dead-space problem and the absence of desktop/tablet screenshots.

CSS/source-inferred

The audits identify:

16px intended mobile input overridden to 15px.

fixed Terminal gap contributing to empty work surface.

740–1099px hybrid navigation/content transition.

inherited 360px rules below 360px.

later CSS restoring five-column bottom nav and mobile session-readout visibility.


Unverified runtime behavior

Native keyboard occlusion, exact touch-target success, screen-reader behavior, final computed fonts, and desktop/tablet composition remain unverified.

Required validation matrix

Width	Required checks

320px	No horizontal scroll, input/Execute reachable, no header collision, meaningful output discoverable
360px	Header reflow, mode controls, status, input, Coach hierarchy
390px	Standard Android/iOS mobile composition and keyboard-open state
430px	Largest mobile composition, long-title scenario context
768px	Tablet navigation/content coherence
834px	Tablet hierarchy and Terminal/Coach proportions
1024px	Hybrid breakpoint behavior
1280px+	Desktop side rail, Terminal dominance, Coach rail, utility controls


This validation matrix aligns with the strongest audit recommendations.

I.2 Accessibility requirements

Landmarks: <main id="main-content">, skip link, route-focus to heading.

Selection semantics: tabs/toggles must match actual interaction behavior.

Keyboard: full Terminal path, nav, tabs, drawers, Reference, Focus Mode.

Focus: containment/return where surfaces are modal-like; Escape where applicable.

Accessible names: all icon-only controls.

Live regions: errors announced urgently only where warranted; routine success should not become assertive noise.

Progress: use real progress semantics on data-bearing progress.

Contrast: final rendered validation, not token-only assumption.

Touch targets: target ≥44×44 for frequent mobile actions where feasible.

Zoom: user zoom must remain available.

Reduced motion: preserve the already-strong contract; do not reintroduce decorative motion dependency.

Non-color cues: success/error/review/locked states need text/glyph/shape in addition to color.

Screen reader: full runtime validation required before closure.

The audits consistently preserve reduced-motion and chart/table strengths while asking for semantic completion around them.

I.3 Canonical state matrix

State	Trigger	Visible contract	Allowed action	Evidence/score effect	Accessibility announcement	Status

First use	Fresh session	Neutral AWAITING COMMAND	Enter command	None	Polite orientation	Confirmed target
Empty input	Blank submit	Inline validation; no engine error	Correct input	None	Inline/live message	Confirmed target
Ready	Input available	Explicit ready state	Submit valid/non-empty command	None	Discoverable input	Confirmed target
Processing	Only if actual trigger exists	Processing indicator	Prevent duplicate submit if real processing exists	No premature score	Polite	Validation-gated
Success	Real accepted command	Result + success cue	Continue workflow	Real evidence only	Polite	Confirmed model
Partial/review	Only if current model supports it	Review/partial interpretation	Continue/retry	Preserve actual evidence	Clear status	Validation-gated
Syntax error	Real invalid command	Error type + next step	Correct/retry	No success evidence	Assertive if appropriate	Confirmed model
Sequence error	Existing Assessment logic	Sequence-specific guidance	Retry/correct sequence	Respect scoring model	Clear error	Confirmed model
Recoverable error	Real model condition only	Error + recovery	Retry/recover	No invented result	Clear recovery	Validation-gated
Interrupted	Only if current model exposes it	Context-preserving interruption	Resume/recover only if real	No invented score	Clear status	Validation-gated
Assessment active	Assessment mode entered	Explicit assessment boundary	Command / documented reference behavior	Only according to existing model	Announce mode/hint policy	Confirmed need; final policy validation
Assessment complete	Existing completion path	Result + next action	Review/continue	Persist real evidence	Result announced	Confirmed model
Locked	Existing lock state	Why locked	Allowed navigation only	No evidence mutation	Explain reason	Confirmed concept
Unavailable	Feature out of current scope	Preview/Roadmap/Unavailable	No false success	None	Clear reason	Confirmed target
Loading	Actual async/resource trigger	Loading only if real	Wait/cancel if supported	No score mutation	Polite	Validation-gated
No evidence yet	No local evidence	Honest empty evidence state	Practice/record	None	Clear empty state	Confirmed target
Illustrative/sample	Seeded preview data	Explicit sample/local marker	No action interpreted as real evidence	None	Explain source	Confirmed target


The Stage 4 protocol explicitly requires a state table while forbidding invented engine behavior; this matrix therefore intentionally leaves unsupported runtime states validation-gated. 


---

J. Conflict Resolution Log

Conflict ID	Conflicting claims	Strongest evidence	Decision	Rationale	Follow-up validation

CR-01	Bottom rail is currently 4-column vs final cascade is 5-column.	Full-cascade tracing in strongest audits.	REJECT stale claim	Later rules win; five columns are the current rendered contract.	Regression screenshot only.
CR-02	Mobile session readout is hidden vs restored.	Later .page-practice rule + visible mobile render.	REJECT stale claim; retain density concern	Absence is not the final state; readability/compression remains a valid issue.	Narrow-device validation.
CR-03	Terminal caret ignores reduced motion vs explicit reduced-motion rule.	Component-specific reduced-motion rule.	REJECT stale claim	Source explicitly handles the caret.	Reduced-motion regression test only.
CR-04	Coach is an overlapping drawer vs normal in-flow/subordinate surface.	Source-derived layout characterization in stronger audits.	REJECT overlap claim; ACCEPT hierarchy concern	The underlying issue is scroll/density, not overlay occlusion.	Task test after dead-space fix.
CR-05	Coach should be removed or converted to FAB/bottom sheet vs kept subordinate.	Screenshots + absence of evidence that current Coach is missed.	ACCEPT subordinate; DEFER new pattern	New surface is a hypothesis, not a defect.	Mobile task test after P1.
CR-06	Assessment should become a route vs remain a Terminal mode.	Product loop + current implementation.	REJECT route	Route would weaken workstation continuity without solving evidence boundary.	None unless IA requirements change.
CR-07	Growth and Tracking should merge vs remain distinct.	Product loop + distinct jobs.	REJECT merge	Growth = interpretation; Tracking = longitudinal trend.	Only future task research could overturn.
CR-08	MapView should be activated vs treated as implementation residue.	Import/route evidence + lack of curriculum requirement.	REJECT activation	Feature presence is not evidence of product need.	Roadmap owner decision only.
CR-09	Arabic is ready/current vs cosmetic/unscoped.	No demonstrated translation/RTL behavior; product scope not supplied.	MODIFY now, DEFER full scope	Honest relabel now; full RTL only with product decision.	Product/content scope decision.
CR-10	Fonts are definitely broken vs not independently inspected by one audit.	Multiple audits explicitly inspect/report absent provisioning; one audit marks it unavailable.	ACCEPT source-level finding; VALIDATE runtime	Inability to inspect does not refute direct observations by the other audits.	Computed-font/network test.
CR-11	Zoom restriction exists vs one audit could not inspect index.html.	Multiple direct-source claims.	ACCEPT remediation; VALIDATE deployment	The claim is strongly supported but runtime zoom behavior still requires device testing.	index.html + device zoom.
CR-12	Illustrative metrics should be deleted vs retained.	Presentation-first boundary.	REJECT deletion; ACCEPT relabel/derive	Mock content is intentional; misleading authority is the defect.	Content-owner fixture review.
CR-13	Assessment history/hints should reset vs carry continuously.	Shared-state source finding; no product learning brief resolving policy.	MODIFY immediately for transparency; DEFER final policy	Silent bleed is the defect; reset-vs-continuous is the product decision.	Learning-design test + stakeholder decision.
CR-14	Mobile content is hidden vs merely compressed in other surfaces.	Source/visual distinctions vary by component.	NEEDS VALIDATION per component	Do not generalize one cascade finding to all mobile surfaces.	320/360/390/430 render matrix.
CR-15	Practice sequence enforcement is clearly broken vs intentionally Assessment-only.	Source indicates Assessment-only enforcement; learning intent is not fully specified.	DEFER FOR VALIDATION	Changing pedagogy without authority is unsafe.	Product/learning-design test.
CR-16	Numeric denominators are simply wrong vs future curriculum placeholders.	Current arrays vs UI literals; product content ownership absent.	ACCEPT derivation; DEFER future-denominator intent	Present UI must be truthful now; future totals require explicit ownership.	Curriculum-owner confirmation.



---

K. Explicit Rejection List

ID	Rejected recommendation	Why rejected	Evidence/boundary	Future validation needed?

RJ-01	Redesign/re-theme AeroBridge into generic SaaS/LMS	Destroys strongest differentiated asset and violates preservation intent.	Product/design ground truth + five-audit agreement.	No
RJ-02	Turn Assessment into a separate top-level route	Weakens Terminal continuity.	Existing mode model.	No
RJ-03	Merge Growth and Tracking	Removes distinction between interpretation and longitudinal trend.	Product loop.	No
RJ-04	Add command autocomplete	Conflicts with recall-based pedagogy.	Terminal learning purpose.	Only with explicit learning-model change.
RJ-05	Add Pause/Resume engine state	Would invent engine truth.	Engine boundary.	Only with engine spec.
RJ-06	Add persistent global Next Action widget	Contextual CTAs already perform that job; global widget risks dashboardization.	Current IA.	Only if task research proves continuity failure.
RJ-07	Activate MapView because “View map” exists	File presence is not learning evidence.	Product scope + import trace.	Roadmap decision only.
RJ-08	Move Coach to FAB/bottom sheet immediately	New interaction pattern is unproven.	No evidence that current Coach is missed.	Yes, after current-flow testing.
RJ-09	Remove Coach entirely during Assessment	Support suppression is sufficient; total removal is broader than evidence requires.	Assessment orientation needs.	No.
RJ-10	Replace hand-built chart with Recharts	Existing chart/table pattern already meets the identified need.	Accessibility strength.	Only if richer interaction is truly required.
RJ-11	Add gamification, badges, streaks, confetti, leaderboards	Incompatible with professional console identity and unsupported by evidence.	Product intent.	No.
RJ-12	Delete all illustrative/mock data	Mock content is intentional; the issue is provenance.	Presentation-first boundary.	No.
RJ-13	Change scoring weights/formula to fix UI problems	Engine change is unnecessary and risky.	Learning/engine boundary.	Separate engine review only.
RJ-14	Treat bottom-nav 4-column state as current bug	Refuted by final cascade.	Direct cascade tracing.	Regression check only.
RJ-15	Treat mobile session readout as simply hidden	Refuted by later CSS rule and rendered evidence.	Final cascade + screenshot.	Density testing only.
RJ-16	Treat terminal caret as reduced-motion failure	Explicit reduced-motion handling exists.	Source trace.	Regression test only.
RJ-17	Fake Arabic/RTL by changing selected state only	Repeats the exact trust problem this audit is fixing.	Product honesty principle.	Product scope first.
RJ-18	Add extra confirmation to Finish Session	Existing preconditions already reduce accidental completion; added friction is unsupported.	Current interaction constraints.	No.
RJ-19	Expand Customer Service curriculum inside this revision	Curriculum authority is unavailable.	Content-owner boundary.	Yes — content delivery.
RJ-20	Add decorative motion to make the prototype feel more premium	Adds noise and can conflict with reduced-motion/accessibility goals.	Product/Accessibility principles.	No.


These rejections align particularly strongly with the rejection logic shared by Claude, Grok, Manus, and v0.dev.


---

L. Validation Plan

Validation ID	Decision under test	Method	Measure	Success criteria	Result that would change the recommendation	Owner

V-01	Empty submit	Automated + manual in Learn/Practice/Assessment	History, score, hints, localStorage, toast	Zero mutation; inline correction; valid commands unchanged	Any mutation reopens P0	UI/QA
V-02	First-use Coach	Fresh session render + screenshot	Error styling/copy	No error before real failure	Intentional seeded diagnostic state would require product redefinition	UI/Product
V-03	Provenance	Static numeric inventory + fixture runs	Owner/source/period/status	Zero unlabeled authoritative-looking sample values	Approved curriculum dataset can justify future denominators	Content
V-04	False affordances	Full click-through	Action, mutation, navigation, persistence	Every success claim corresponds to real action	Product owner may approve preview state with neutral copy	UI/Product
V-05	Assessment state carry-over	Learn → Practice → Assessment	Prior commands, hints, score	User can see exactly what carries forward	Product/learning owner defines true isolation model	Learning/Product
V-06	15px → 16px	Computed CSS + real mobile browsers	Final computed font-size	16px at all mobile widths	Browser-specific behavior may require limited complementary fix	UI/Runtime
V-07	Font provisioning	DevTools/network/build	Computed family, asset load	Intended families or approved shipped fallback	Existing runtime loader proves current source finding obsolete	Deployment/UI
V-08	Zoom	iOS/Android/browser	200%+ zoom/reflow	User zoom available and core workflow remains operable	Browser-specific component redesign only	Accessibility/Runtime
V-09	Contrast	Automated + manual rendered-size audit	Ratios across surfaces/states	≥4.5:1 meaningful normal text	Approved large-text treatment or alternate role may alter threshold	Accessibility/UI
V-10	Tab/toggle semantics	Keyboard + NVDA/VoiceOver/TalkBack	Roles, selected state, key commands	Correct semantic state and operation	A control behaving as button-group should use button semantics instead	Accessibility
V-11	Progress semantics	Screen reader + DOM audit	Progress role/value	Correct announced value and bounds	Alternate accessible value may substitute if visually unchanged	Accessibility
V-12	Focus/overlay behavior	Keyboard-only + SR	Entry, containment, Escape, restore	No focus loss; reliable dismissal	Non-modal workspace semantics may replace dialog trapping	Accessibility/UI
V-13	Mobile keyboard	Physical Android/iOS at 320/360/390/430	Input reachability, output visibility, viewport jump	No occlusion/clipping; latest result usable	If current architecture fails, compare tested flexible/collapsible patterns	Runtime
V-14	Mobile dead-space	Before/after render, fresh + multi-command	Empty-band height, scroll distance	Dead band minimized without reducing work surface	Restore minimum output floor if removing gap hurts comprehension	UI/UX
V-15	Tablet	768/834/1024	Nav identity, Terminal width, hierarchy	Coherent single composition	Dedicated tablet navigation only if evidence shows failure	Runtime/UX
V-16	Desktop	1280+	Side rail, Terminal/Coach ratio, utility controls	Terminal remains dominant, no clipping	Breakpoint adjustment only where concrete failure exists	Runtime/UX
V-17	Scenario context	Longest titles at 320–430	Wrapping, CTA collision, preserved identity	Context remains understandable	Presentation-only adjustment, not route-model change	UI
V-18	Growth/Tracking handoff	Assessment → Growth → Tracking → Practice	Record ID, evidence, CTA context	Same evidence context survives end-to-end	Fix ownership/data lineage if mismatch	UI/Data
V-19	Reduced motion	OS reduced motion on/off	Caret, scroll, panels, number transitions	No training-critical information depends on motion	Fix offending animation only	Accessibility/UI
V-20	Fallback identity	Forced error + 404	Branding, raw stack exposure, recovery	Flight Deck identity, no raw implementation detail	Revisit only if production routing architecture changes	Runtime
V-21	Arabic scope	Product decision + bounded prototype fixture	Scope, translation, bidi, direction	Either genuine bounded RTL or honest roadmap state	Full i18n program if scope is approved	Product/Content
V-22	Sample/seed ownership	Fresh-session persistence test	Seed source, session clock, historical labeling	Every seed clearly labeled/owned	Retain seed if explicit preview purpose is approved	Content/Product


The validation plan intentionally includes source tests, visual tests, device tests, keyboard tests, screen-reader tests, contrast tests, and product/content decisions, matching the Stage 4 protocol. 


---

M. Implementation Handoff

Phase 0 — Freeze the contract

Freeze before touching UI:

valid command vocabulary

assessmentScore behavior

localStorage record shape

five-area route map

working context handoffs

current valid command transcripts

chart/table data equivalence

reduced-motion baseline


Phase 1 — P0 trust and evidence

Implement in this order:

1. Empty-command guard


2. Neutral first-use Coach


3. Evidence/provenance reconciliation


4. False-success affordance cleanup


5. Zoom/font-source correction


6. Arabic honesty


7. Unsupported readiness-language cleanup



Each of the first two Terminal fixes should be independently screenshot-verifiable before broader polish. The audits repeatedly recommend isolating those changes and protecting valid command behavior.

Phase 2 — P1 shared accessibility/state foundation

Implement:

canonical semantic tokens

tab/toggle/pressed/current semantics

main/skip/route focus

progress semantics

non-color state cues

live-region scope

overlay focus/Escape/restore behavior


Do not change visual identity while making these additions.

Phase 3 — P1 Terminal hardening

Implement:

16px mobile input correction

flexible dead-space reduction

canonical Terminal state presentation

explicit Assessment state disclosure

per-command toast reduction

Coach subordination

context lineage hardening where source supports it


Phase 4 — P1 screen/content honesty

Implement:

Progression count reconciliation

Scenario count/category reconciliation

Filter/Sort honesty

Growth history count reconciliation

readiness-language scoping

Service-track honest state

trend semantic correction


Phase 5 — Validation and release gate

Run V-01 through V-22 where applicable.

No item may be marked “fixed” solely because source code looks correct. Runtime-bound decisions require runtime evidence.

Regression gates

Every phase must preserve:

AN → SS → FQD → FXP valid command behavior

unknown-command syntax handling

assessment scoring behavior

localStorage schema

session completion/persistence

Growth/Tracking update behavior

Scenario → Practice handoff

Growth/Tracking → Practice handoff

navigation order and route map

Focus Mode

Reference behavior

reduced-motion behavior

chart/table equivalence

no false success toasts


This regression discipline is explicitly reinforced by the stronger Stage 3 audits.


---

N. Open Questions, Assumptions, and Evidence Gaps

N.1 Product-owner decisions

Question	Why it matters

Is Arabic/RTL actually in the current release scope?	Determines whether AR stays roadmap or enters a real i18n program.
Is Backup intended as export, local snapshot, cloud backup, or preview-only?	Determines honest control disposition.
Is Assessment intended to start with fresh evidence or intentionally carry prior activity?	Determines final mode-state behavior.
Is the Service track actually funded/content-ready?	Determines whether an “in preparation” state is truthful.


N.2 Content/curriculum decisions

Question	Why it matters

Are 8 stages, 40 scenarios, 12 logs, 210 commands future curriculum totals or accidental literals?	Determines derive-vs-qualify behavior.
What does “Saudi readiness” actually measure?	Determines whether readiness language can remain at all.
What is the official meaning of Reference in each mode?	Determines hint accounting.
Should Practice enforce sequence or remain exploratory?	This is a learning-design decision, not a cosmetic fix.


N.3 Engine/state decisions

Question	Why it matters

Does the local model expose genuine processing/interrupted/retry states?	Prevents UI invention.
Should Assessment history/hints isolate or carry continuously?	Determines final state-management policy.
Should context handoffs ultimately map to stable scenario/skill IDs?	Determines future evidence lineage quality.


N.4 Runtime/device validation

Required before final approval:

320/360/390/430 with native keyboards

768/834/1024 tablet composition

1280+ desktop composition

keyboard-only

VoiceOver/NVDA/TalkBack

final rendered contrast

computed font loading

browser zoom/reflow

focus containment/restore


N.5 Deployment/configuration validation

Still to confirm in the actual target environment:

font asset delivery

viewport metadata in final deployment

externally referenced assets

error fallback mounting

404 behavior

production build/runtime differences


N.6 Audit disagreements that remain genuinely unresolved

The material unresolved set is now narrow:

final Assessment isolation vs continuity policy

Arabic release scope

future curriculum denominators

actual device keyboard behavior

desktop/tablet composition

precise runtime font delivery

whether the drawer has truly redundant navigation content

whether mobile coaching is missed after the dead-space fix


Everything else material has been adjudicated sufficiently to define implementation.


---

O. Final Recommendation

Implement now

Empty-command safety

Neutral first-use Coach

Evidence provenance and count reconciliation

False-success/false-affordance cleanup

Readiness-language honesty

16px mobile input correction

Zoom correction

Accessibility semantics foundation

Contrast/readability correction

Assessment transparency

Mobile Terminal dead-space refinement

Service-track honesty

Scenario/Growth provenance cleanup

Trend semantic correction


Preserve

Flight Deck Console visual identity

Terminal-first Practice

Learn / Practice / Assessment inside Terminal

Focus Mode

command-history recall

five-area navigation with Train priority

end-to-end evidence loop

Growth Record separation from Tracking

evidence → practice → scenario pattern

local/illustrative disclosure

chart + same-data table fallback

reduced-motion foundation

current command evaluator

scoring formula

localStorage schema

existing contextual handoffs


Defer

Full Arabic/RTL implementation

Tablet-specific navigation redesign

Coach FAB/bottom-sheet replacement

Map activation

token consolidation beyond safe hardening

dead-code cleanup where roadmap intent is unknown

decorative polish

any new global analytics/dashboard layer

any new engine state or command


Reject

Redesign/re-theme

Dashboardization

Growth/Tracking merger

Assessment route

autocomplete

engine Pause/Resume

gamification

global Next Action widget

chart-library migration for its own sake

speculative MapView activation

partial/fake Arabic

stale bottom-nav/readout/reduced-motion “bug” fixes already disproved by final cascade


Final decision

AeroBridge should be preserved and refined. The evidence does not justify redesign or architectural reset. It does justify a disciplined hardening pass centered on evidence integrity, truthful state, assessment credibility, accessibility semantics, and mobile Terminal ergonomics. The strongest move is not to add more product; it is to make the existing product tell the truth about what happened, what is measured, what is illustrative, what is available, and what the trainee should do next. The P0/P1 implementation path is sufficiently supported to begin now, while native runtime behavior, desktop/tablet composition, final typography, screen-reader behavior, and Arabic scope remain explicitly validation-gated. This is the lowest-risk path that materially increases trust without sacrificing the qualities that make AeroBridge distinctive.