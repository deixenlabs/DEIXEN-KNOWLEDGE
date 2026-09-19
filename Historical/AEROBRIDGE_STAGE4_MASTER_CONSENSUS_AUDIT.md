# AEROBRIDGE — MASTER SYNTHESIS AUDIT

**Document type:** Independent evidence-based adjudication and implementation handoff

**Overall direction: Preserve and Refine.** `ideas.md` states directly that this is *"a reference-preservation project, not a redesign"* and names the existing Flight Deck Console prototype as the ground-truth visual and interaction reference. Direct inspection of the actual source in this pass confirms the claim is earned, not aspirational: five screens genuinely share state and hand off context to one another (`setPracticeContext`), a real `localStorage` assessment record is written and immediately read back by Growth Record and Progress Tracking, and the visual system is coherent and domain-appropriate rather than a generic template. Every defect found below is concentrated, specific, and correctable without touching architecture, navigation structure, the command engine, or the scoring model — which is the evidentiary bar for "refine," not "revise" or "redesign."

**Design status: Needs targeted revision.** The product's central screen currently shows a fabricated error to every new user before they have done anything, an empty command submission is silently logged as a real one, and several headline numbers do not add up to the data rendering beneath them. These are trust-integrity defects on the primary surface of a product whose stated value proposition is trustworthy training evidence — serious enough to withhold a "production reference" rating, but narrow and cheap enough (conditional-render and copy-level changes, not architecture) that "not ready for reference" would overstate the distance to fixed.

---

## A. Executive Decision

AeroBridge's foundation is sound and should not be rebuilt. The Flight Deck Console identity is distinctive and consistently applied; the Terminal is a genuine workstation with real command history, arrow-key recall, and a purpose-built Focus Mode, not a decorative widget; the five-screen loop (Progression → Practice → Assessment → Growth → Tracking → Scenarios) is wired end to end through real state and real persistence, confirmed by direct reading of `Home.tsx` and not merely inferred from screenshots; and the Progress Tracking chart ships with a genuinely-wired accessible `<details>`/table fallback consuming the same data as the bars — the single strongest accessibility pattern anywhere in the codebase. These are the assets this revision must protect.

Set against that foundation, a small number of defects are serious enough to block a "production reference" verdict, and every one of them is independently confirmed against the actual source in this pass, not inherited from any prior audit's description. A trainee's first interaction with the Practice screen — the product's architectural center — is a fabricated `FORMAT ERROR · CHECK ENTRY` message rendered in the error-red token, before the trainee has typed anything (`Home.tsx`, the Coach panel's pre-command fallback). Submitting an empty command is silently coerced to `"FQD"` and logged as a real entry (`command.trim().toUpperCase() || "FQD"`). Switching from Learn or Practice into Assessment does not reset command history or hint count, and the Assessment tab's "No hints" label is static text keyed to session completion, not to the actual hint count — meaning the one score this product exists to produce with integrity can silently inherit unscored activity while the interface actively tells the trainee otherwise. Three headline counts (`3/8` stages, `23/40` scenarios, `LOG 04/12`) do not reconcile with the arrays and rendered rows behind them, visible directly in the supplied screenshots. And twelve-plus visible controls — including one inside the Coach panel that explicitly toasts "Reference opened: …" while never opening anything — perform no real action.

Three decisions matter more than the others. **First, trust and evidence integrity gate everything else**: the blank-command guard, the neutral first-use Coach state, and the count/action honesty sweep are cheap (conditional logic and copy, not architecture) and disproportionately damaging left alone, because they sit on the product's core screen and undermine the one thing a training tool must not compromise — whether the trainee can believe what it tells them. **Second, the Terminal's two verified integrity regressions need to be fixed without touching its architecture**: the mode-switch state bleed threatens the credibility of the Assessment score specifically, and a same-specificity CSS rule later in the cascade drops the mobile command input to 15px, silently undoing a 16px rule the same file shows was written deliberately to prevent iOS Safari's auto-zoom-on-focus. **Third, accessibility and design-token debt should be closed as one shared foundation, not five isolated patches**: the primary button's white-on-`#6f8fff` pairing measures 2.98:1 and `--text-faint` measures 3.18–3.66:1 against its actual surfaces (both independently recomputed in this pass via the WCAG relative-luminance formula against the exact token values, not merely repeated from prior claims), five tab-like control groups expose zero ARIA selection semantics, and two overlapping color-token systems coexist in the same stylesheet.

The evidence is sufficient to proceed directly to implementation for every finding classified MUST FIX or SHOULD FIX below: each rests on direct source citation, independently recomputed math, or a fully traced CSS cascade — not on how many of the five input audits repeated it. The evidence is **not** sufficient to close the file. No desktop or tablet screenshot exists anywhere in the seven supplied images, so every ≥740px composition claim in this report is CSS-derived, not visually confirmed. Native on-screen-keyboard behavior at 320–430px, actual screen-reader announcement behavior, and effective touch-target size have no runtime evidence in the supplied package. These remain explicitly validation-gated in §I and §L, and no recommendation below treats a CSS declaration, a repeated audit claim, or a premium-looking screenshot as a substitute for that validation.

---

## B. Evidence and Adjudication Method

**Evidence package available to this pass.** The complete extracted prototype archive (`AEROBRIDGE_SOURCE_CLEAN.zip` → `aerobridge-share-preview/`), read in full rather than sampled: `client/src/pages/Home.tsx` (363 lines — all five screens live in this one file), `client/src/index.css` (409 lines — the complete design system, traced as a full cascade rather than read as isolated declarations), `client/index.html`, `client/src/App.tsx`, `client/src/main.tsx`, `client/src/components/Map.tsx`, `client/src/components/ErrorBoundary.tsx`, `client/src/pages/NotFound.tsx`, `client/src/components/ManusDialog.tsx`, `client/src/contexts/ThemeContext.tsx`, `client/src/hooks/*`, `server/index.ts`, `package.json`, `.project-config.json`, `template.json`, and `ideas.md`. Every source-attributed claim in this report was independently re-derived in this pass by direct reading, `grep`, or manual CSS-cascade tracing — none is inherited from an audit's citation of it without separate confirmation. Two contrast ratios (primary-button text, `--text-faint`) were independently recomputed via the WCAG 2.x relative-luminance formula against the actual hex values in `index.css`, not taken on any audit's word. Seven rendered mobile screenshots (Progression, Practice/Learn mode, Scenarios, Growth Record × Record/History/Reports, Progress Tracking, all ~360–430px width on the live `manus.space` preview host) were used as rendered-evidence confirmation, cross-checked line-by-line against source where a claim depended on final visual output rather than markup alone — this cross-check is how the mobile nav-order/breadcrumb-numbering conflict (§J) was confirmed directly rather than taken from any audit. All five Stage 3 Unified Audits (ChatGPT, Claude, Grok, Manus, v0.dev) were read in full and used as analytical evidence, never as a voting bloc.

**Evidence hierarchy applied.** Direct source/runtime evidence outranks everything for implementation-behavior claims; `ideas.md` governs product-intent and scope-boundary claims and was treated as authoritative over any audit's design opinion; rendered screenshots confirm what actually paints, independent of what the markup implies it should paint; cross-audit agreement is treated strictly as a consensus *signal*, never as proof — several of the strongest-sounding claims in the corpus (the bottom-nav column count, the mobile session-readout visibility, the terminal-caret's reduced-motion coverage) were repeated across multiple audits while being demonstrably wrong once the *full* cascade was traced rather than the first matching rule found. Repetition and full-cascade tracing produced different answers often enough in this package that this report treats every "N audits agree" note as context, never as the reason a claim was accepted.

**How the five Unified Audits were treated.** As five independent analytical passes over a shared evidence base, not as ballots. Every classification below states its own evidence basis; where a claim's only support was "the audits say so," it is marked NEEDS VALIDATION or omitted rather than promoted to MUST FIX or SHOULD FIX. One useful meta-finding surfaced independently by two of the five audits (Manus, Claude) concerns a *sixth*, upstream audit not itself part of this five-file corpus (an earlier-stage "Kimi" pass, referenced by name inside the supplied files): both flag it as containing claims contradicted by source — invented color tokens, a claim that the Terminal and Scenarios screens are "missing or simplified" when they are in fact the most fully-built screens in the application, and an internally-inconsistent cross-audit scorecard. This report does not use any Kimi-attributed claim as evidence for anything; it is noted here only because two independent Stage 3 audits catching the same unreliable upstream source, for the same reasons, is itself a small positive data point about this corpus's evidence discipline.

**Notable evidence-access asymmetry, resolved directly.** v0.dev's Unified Audit states explicitly that its evidence package did not include `client/index.html`, and for that reason marks the font-provisioning and viewport-zoom findings as NEEDS VALIDATION rather than confirmed, while the other four audits (which did have `index.html`) mark both as confirmed defects. This pass has direct access to `index.html` and confirms both defects outright (§D, §G): the Google Fonts `<link>` block sits inside an HTML comment explicitly marked *"THIS IS THE START OF A COMMENT BLOCK, BLOCK TO BE DELETED"* (and, even if uncommented, references `Inter`, not any of the three families — Space Grotesk, IBM Plex Mono, Cairo — that `index.css` actually declares as tokens), and the viewport meta tag reads `content="width=device-width, initial-scale=1.0, maximum-scale=1"`. This is not a factual disagreement between audits; it is an evidence-access gap in one audit's package that this pass's direct file access closes.

**Conflict between current behavior and stated intent.** `ideas.md` documents deliberate mobile input engineering — a 16px command-input floor specifically to defeat iOS Safari's auto-zoom-on-focus. The current cascade does not honor its own stated intent: a later, identically-specific mobile rule sets the same selector to 15px, so the *shipped* behavior contradicts the *documented* intent on the product's single most-used input. This is reported as exactly that — a conflict between intended and actual behavior — rather than silently treating either the CSS comment's stated intent or the final computed value as the whole truth.

**What is explicitly not available to this pass.** No desktop or tablet screenshot exists in the seven supplied images — every ≥740px claim below is CSS-derived and labeled as such, never asserted as visually confirmed. No physical-device or emulated native-keyboard test exists for 320–430px. No screen-reader session (NVDA/VoiceOver/TalkBack) exists. No build-log or network trace confirms whether `/manus-storage/...` hosted assets (three atmospheric background images and the brand-mark logo itself) or the Umami analytics script (injected via `%VITE_ANALYTICS_ENDPOINT%`, pointing at `manus-analytics.com` per `.project-config.json`) actually resolve outside the live preview host — confirmed in source as *referenced*, not confirmed as *reachable*. None of these gaps block the MUST FIX/SHOULD FIX findings below, all of which rest on source or independently-computed evidence; they gate the items marked NEEDS VALIDATION throughout.

### Evidence classification table

| Class | Definition | Examples from this audit |
|---|---|---|
| **E4 / Direct** | Directly verified in this pass against supplied source, config, or a specific rendered screenshot. | Blank-command→`FQD` coercion (`Home.tsx`); Coach's pre-command `FORMAT ERROR` fallback; `maximum-scale=1` in `index.html`; commented-out font block; `.bottom-nav` grid-column cascade (base 4-col, three later rules to 5-col, one `!important`); mode-switch handler clears only `sessionComplete`; Coach panel's "Open reference" button calling only `toast.info` with no `setReferenceOpen` call; `.skill-hover-preview{display:none}` at ≤739px; `Map.tsx` unimported anywhere; primary-button and `--text-faint` contrast ratios (self-computed WCAG math). |
| **E3 / Strongly corroborated** | Supported by more than one materially different evidence type (e.g., source + screenshot, or independent re-derivation by more than one of the five audits using different methods). | Mobile terminal input 15px cascade regression (independently re-derived by this pass, by ChatGPT's Stage 3 audit, and by Claude's Stage 3 audit, via three separate cascade traces reaching the identical two rule citations); contrast ratios (independently computed by this pass and cross-confirmed by four of five Stage 3 audits computing the same ratio from the same hex codes); `3/8` and `23/40` count mismatches (source array length + direct screenshot confirmation). |
| **E2 / Cross-audit analysis** | Repeated or logically supported across the five audits, but ultimately dependent on the same underlying source citation or screenshot rather than independently re-derived evidence types. | The general pattern that toast-only controls erode trust cumulatively (five-way agreement, same handler citations); token-layer duplication being a maintainability concern rather than a user-facing defect. |
| **NEEDS VALIDATION** | Plausible or important, but not provable from the supplied package — depends on a screenshot, device, browser, screen reader, or product decision not available here. | Tablet (740–1099px) composition; native keyboard behavior at 320–430px; whether the hamburger drawer duplicates the bottom nav; whether 8/40/12/210 are future-curriculum totals or presentation literals; full Arabic/RTL scope. |
| **REJECTED** | Contradicted by stronger evidence, outside the product's stated scope, or built on an unsupported assumption. | Bottom-nav "4 columns" as a *current* defect (refuted by full cascade trace); mobile session-readout "simply hidden" (a later Practice-scoped rule addresses it — the residual issue is density, not absence); terminal-caret "ignores reduced motion" (the reduced-motion block explicitly names `.terminal-caret`); activating `MapView` because a "View map" label exists. |


---

## C. Product and Design Principles to Preserve

### C.1 Flight Deck Console visual identity

**Preserve:** the deep-navy foundation (`--navy-950:#050914` through `--navy-750:#16213c`), the restrained Vector Blue accent (`--blue:#6f8fff`), green/amber/red operational semantics, monospace command/readout typography, and atmospheric restraint over decorative flourish.

**Why it is successful:** it reads as purpose-built aviation-training software rather than a generic LMS or SaaS dashboard skinned dark. `ideas.md` names this identity as the explicit ground truth. Beyond brand fit, the console framing does UX work: monospace readouts and terminal chrome set an expectation of precision that matches the product's actual job (recall-based command training), and the restraint keeps attention on the Terminal rather than competing with it.

**Acceptable modification:** adjust specific token *values* — as required by the contrast fixes in §D — without changing the palette's identity, hue relationships, or the console framing itself.

**Must not change:** replacing the dark console with a lighter, generic consumer aesthetic; removing the operational color semantics; flattening the asymmetric composition into generic cards.

**Evidence:** `ideas.md` names this directly; confirmed as the actually-shipped system by direct `index.css` token read and cross-checked against all seven screenshots, not merely asserted.

### C.2 Terminal-first workstation

**Preserve:** the Terminal as the dominant, full-width primary work surface; the Learn/Practice/Assessment mode structure; real command entry and history; Arrow Up/Down history recall; Focus Mode; the Reference concept; the Coach as subordinate support; local-simulation disclosure language.

**Why it is successful:** confirmed in source, this is the only screen with its own later-pass token-refinement layer (the `--ab-*` "AeroBridge Elevation Directive" rules scoped to `.page-practice`), the only nav item with deliberate mobile visual emphasis (`.is-primary`, visible in every mobile screenshot's bottom rail), and the only screen with a purpose-built immersive mode. It is a genuine workstation with real state (`commandHistory`, `hintCount`, `sessionSeconds`), not a dashboard widget wearing terminal styling.

**Acceptable modification:** improve state visibility, focus management, and mobile density (§F, §G) without altering command matching, scoring, or the terminal's work-surface dominance.

**Must not change:** do not cardify the Terminal, do not reduce its width/prominence relative to the Coach panel, do not alter command matching or the scoring formula to solve a presentation problem.

**Evidence:** direct source read of `Home.tsx`'s `Practice` component and `index.css`'s `--ab-*` block; confirmed visually in the Practice screenshot (Image 5).

### C.3 The five-stage learning loop and its real cross-screen handoffs

**Preserve:** `ideas.md` names the exact sequence — *"Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action."* Confirmed in source: `setPracticeContext` genuinely carries context from Progression, Scenarios, Growth, and Tracking into Practice, and finishing an Assessment writes a real record that Growth and Tracking immediately reflect. This is the product's most substantial working architecture, not a set of disconnected pages linked by a nav bar.

**Why it is successful:** it is a real product spine. A trainee's evidence genuinely flows: complete an assessment → the record appears in Growth's latest-evidence notice and Progress Tracking's session log → the recommended-practice CTA carries a real context string back into the Terminal.

**Acceptable modification:** strengthen provenance and next-action explanations (§D, §F) without adding a global dashboard or merging distinct loop stages.

**Must not change:** do not merge Growth Record and Progress Tracking into one analytics screen — `ideas.md` names them as two distinct loop stages, and they genuinely operate at different evidence grains (skill-level mastery vs. session-level trend); reducing the surface-level metric *redundancy* between them is a legitimate smaller change (§G.6), but removing either as a distinct destination is not supported by the evidence. Do not replace contextual handoffs with generic navigation.

**Evidence:** `ideas.md` direct quote; `setPracticeContext` call sites and `localStorage` read/write confirmed by direct source read across `Home.tsx`'s five screen components.

### C.4 Learn / Practice / Assessment as a pedagogical structure

**Preserve:** genuinely different Coach copy and hint-visibility rules per mode (Reference examples hidden in Assessment; hint-count increment suppressed in Assessment), matching how real operational training separates guided practice from evaluation.

**Why it is successful:** it is a real pedagogical distinction with real code behind it, not three tabs sharing one behavior.

**Acceptable modification:** fix the state-bleed between modes (§D, §F — MC-004) without flattening the three-mode distinction that makes them worth having separately.

**Must not change:** do not merge the three modes or remove the distinction between guided and evaluated practice.

**Evidence:** direct source read of the `mode`-conditional branches throughout the `Practice` component.

### C.5 Focus Mode

**Preserve:** the deliberate, CSS-driven immersive state (`body:has(.focus-mode){overflow:hidden}`) that hides non-essential chrome around the Terminal.

**Why it is successful:** it is a genuine, purpose-built feature — not an accidental side effect of some other rule — and it directly serves the Terminal-first principle by removing everything that competes with it during focused practice.

**Acceptable modification:** add the missing keyboard focus-trap and Escape handling (§D, §F — MC-017) *additively*, alongside the existing scroll-lock mechanism, not as a replacement for it.

**Must not change:** the existing `:has()`-based scroll-lock mechanism or Focus Mode's visual behavior.

**Evidence:** direct source read of `.focus-mode` and the `body:has()` selector in `index.css`.

### C.6 Reduced-motion implementation

**Preserve exactly, unmodified.** Confirmed in source to be more thorough than a literal reading of any single rule in isolation would suggest: a global `@media (prefers-reduced-motion: reduce)` catch-all using `!important` on `animation-duration`, `transition-duration`, and `scroll-behavior`, *plus* multiple component-scoped refinements — including a rule that explicitly names `.skill-hover-preview`, `.tracking-bar`, and `.tracking-row`, and the JS-side `useAnimatedNumber`/`useAnimatedBar` hooks that check `window.matchMedia("(prefers-reduced-motion: reduce)")` directly and skip the counting animation entirely rather than merely shortening it. The terminal caret's blink animation is covered by the universal `*` selector in the global catch-all, meaning the caret **does** already respect reduced motion — a claim that two of the five Stage 3 audits' upstream sources made to the contrary does not survive tracing the full cascade (§J).

**Why it is successful:** this is an above-average accessibility implementation for a prototype at this stage — most products get the global catch-all and stop there; this one also handles JS-driven number/bar animations at the hook level, which the CSS catch-all cannot reach.

**Acceptable modification:** none identified as needed.

**Must not change:** do not strip or simplify this system while fixing anything adjacent to it; do not add new decorative motion elsewhere in the product that this system would then need to cover.

**Evidence:** direct source read of the `@media (prefers-reduced-motion: reduce)` block in `index.css` and the `useAnimatedNumber`/`useAnimatedBar` hook bodies in `Home.tsx`.

### C.7 Progress Tracking chart + accessible table fallback

**Preserve:** the `<details><summary>View data table</summary><div role="table">…</div></details>` pattern, confirmed genuinely wired to the same records driving the visual bars — not a decorative stub with different or stale numbers.

**Why it is successful:** it is the single strongest, most fully-realized accessibility pattern anywhere in the codebase, and it should be the template for any future data visualization the product adds, not replaced by a charting library merely because `recharts` happens to be an installed dependency — no evidence in this package shows the current hand-built pattern is insufficient for its one job.

**Acceptable modification:** none identified as needed to the pattern itself; only the metric-provenance labeling around it (§D, §G.6).

**Must not change:** do not migrate to a charting library as a "modernization" task absent a proven requirement the current pattern cannot meet.

**Evidence:** direct source read of the `TrackingChart`/data-table markup in `Home.tsx`, confirmed sharing the same `points`/`series` values as the bar rendering.

### C.8 Deliberate, evidenced mobile input engineering

**Preserve the intent and the mechanism**, even though one execution detail regresses it (§D — MC-011): `position: sticky` command input pinned above `env(safe-area-inset-bottom)`, a purpose-commented two-row terminal-header restructuring at the 360px breakpoint, and a 16px input-font rule specifically written to defeat iOS Safari's auto-zoom-on-focus.

**Why it is successful:** this is careful, intentional engineering, confirmed by the CSS's own comments naming the specific problem being solved — a future contributor should recognize it as deliberate work to preserve, not "clean up" by accident while fixing the regression that currently undermines it.

**Acceptable modification:** fix the 15px override (§D, §F) so the *shipped* behavior matches the *documented* intent; no other change to the mechanism.

**Must not change:** the sticky positioning, the safe-area handling, or the 360px header restructuring.

**Evidence:** direct source read plus the CSS's own inline comments naming the intent.

### C.9 Contextual, domain-specific copy voice

**Preserve:** `ideas.md` states directly — *"Prefer contextual labels such as Start, Resume, Review, and Retry over generic SaaS wording."* Confirmed as the current pattern throughout (`Resume scenario`, `Review result`, `Retry assessment`, `Resume pricing workflow`).

**Why it is successful:** it reinforces the operational, professional-training positioning at the copy level, not just the visual level.

**Acceptable modification:** extend the same voice to any new honesty-disclosure copy this revision adds (§D, §F); do not genericize existing copy while fixing evidence-honesty issues elsewhere.

**Must not change:** the existing verb choices and their consistent application.

**Evidence:** `ideas.md` direct quote, cross-checked against copy throughout `Home.tsx`.

### C.10 Command-history keyboard recall

**Preserve:** Arrow Up/Down history recall in the Terminal input — a genuine, correctly-implemented feature serving actual command-line users' expectations.

**Why it is successful:** it is real, working, power-user-appropriate functionality, not a cosmetic nod to "terminal aesthetics."

**Acceptable modification:** none required; a small discoverability affordance is optional polish (§F.3), not a change to the mechanism.

**Must not change:** the recall mechanism itself.

**Evidence:** direct source read of the history-navigation key handler in the Terminal input.

### C.11 The honesty-disclosure instinct, where it already exists

**Preserve and extend, do not replace with a different pattern.** The Terminal's `"LOCAL TRAINING SIMULATION"` / `"RESPONSE MODEL / ILLUSTRATIVE · VERIFY WITH YOUR COURSE MATERIAL"` labeling (visible in the Practice screenshot) is exactly the right instinct — local/illustrative content is disclosed as such, in-context, in the product's own voice. It is simply not yet applied consistently to every surface that needs it (§D — MC-005, MC-006).

**Why it is successful:** it proves the product already knows how to disclose illustrative content honestly without breaking its own voice; the fix for the undisclosed surfaces is to extend this exact pattern, not invent a new one.

**Acceptable modification:** apply the same disclosure pattern to Progression's stage count, Scenarios' totals, Growth's `LOG` count, and the Practice footer's pre-submission metrics.

**Must not change:** the pattern's existing wording style and placement logic.

**Evidence:** direct source read, confirmed visually in the Practice screenshot.


---

## D. Critical Problems

Material problems only, each independently verified against source in this pass.

| ID | Problem | Direct evidence | Impact | Severity | Confidence | Decision |
|---|---|---|---|---|---|---|
| MC-001 | Empty/whitespace command is silently coerced to `"FQD"` and logged as a real command | `Home.tsx`: `const nextCommand = command.trim().toUpperCase() \|\| "FQD"` — the resulting entry enters `commandHistory` and is reported via a success toast | A trainee can generate a false command/evidence event by submitting nothing; in Assessment this can affect the score | Critical | Confirmed (E4) | **MUST FIX** |
| MC-002 | Coach panel's default, pre-command state renders a fabricated `FORMAT ERROR · CHECK ENTRY` in the error-red token beneath a correctly neutral "AWAITING COMMAND" label | `Home.tsx`: `latestEntry?.response ?? "FORMAT ERROR · CHECK ENTRY"` fallback, `<code className={latestEntry?.ok ? "coach-code--success" : ""}>`; confirmed pixel-for-pixel in the supplied first-load Practice screenshot (Image 5) | A new trainee's first impression of the product's central screen is an error they did not cause | Critical | Confirmed (E4) | **MUST FIX** |
| MC-003 | Headline counts do not reconcile with the data rendering beneath them: `3/8 stages` vs. a 6-item `levels` array; `23/40 scenarios` vs. a 5-item `scenarios` array, one of whose displayed categories ("Exchanges & Refunds") exists nowhere in that array; `LOG 04/12` vs. 3 rendered history rows | `Home.tsx` array literals cross-checked against the hardcoded strings; all three visible directly in Images 4, 6, and 1/2 | A trainee who checks closely finds the product's own numbers don't add up — direct damage to a product whose value is trustworthy evidence | Critical | Confirmed (E4) | **MUST FIX** (derivation) / content decision on real future totals is **NEEDS VALIDATION** |
| MC-004 | Learn/Practice/Assessment modes share `commandHistory` and `hintCount` with no reset or isolation on mode switch, and the Assessment tab's "No hints" label is static text (`sessionComplete ? "Report ready" : "No hints"`) that does **not** reference `hintCount` at all | `Home.tsx`: the entire mode-switch handler is `setMode(item); setSessionComplete(false);`; `assessmentScore(commandHistory, hintCount)` runs over the full shared history regardless of origin; label confirmed by direct read to ignore `hintCount` | An Assessment score can silently include unscored Learn/Practice activity and hint usage while the UI actively displays "No hints" | Critical | Confirmed (E4) | **MUST FIX** |
| MC-005 | Fresh, pre-submission Practice-footer metrics (`Accuracy 86%`, `Commands mastered 128/210`, `Task progress 68%`) and a pre-seeded `4:32` session timer (`useState(272)`) render with the same visual authority as real local evidence before any command has been entered | `Home.tsx`: `const accuracy = submitted ? liveAssessment.accuracy : 86`; static `128`/`210` and `68` literals; `useState(272)`; all confirmed matching the fresh-session Practice screenshot (Image 5) exactly | A trainee cannot tell seeded/illustrative numbers from their own real evidence at a glance | High | Confirmed (E4) | **MUST FIX** |
| MC-006 | 12+ visible controls perform no real action beyond a generic toast, including one — the Coach panel's own "Open reference" link — whose toast text explicitly claims `"Reference opened: …"` while `referenceOpen` state is never touched and the drawer never opens | `Home.tsx`: every listed handler calls only `toast.success/info/warning(...)`; Coach's "Open reference" `onClick` is `() => toast.info(\`Reference opened: ${coachState.next}.\`)`, confirmed by direct read to call neither `setReferenceOpen` nor any other state mutation | The most-repeated "looks functional, isn't" pattern in the product; the Coach instance is worse than the average case because its own confirmation message asserts a completed action that never happened | High | Confirmed (E4) | **SHOULD FIX** (tiered — see §F) |
| MC-007 | The three declared display/mono/Arabic fonts (Space Grotesk, IBM Plex Mono, Cairo) are not loaded by any mechanism in the supplied source | `client/index.html`: the only font-loading markup sits inside an HTML comment explicitly marked "THIS IS THE START OF A COMMENT BLOCK, BLOCK TO BE DELETED", and that dead block references `Inter`, not any of the three declared families; zero `@font-face` rules exist in `index.css`; zero font packages in `package.json` | The product's entire distinctive typography silently renders in generic system-UI fallback fonts in every real browser, on every screen simultaneously | High | Confirmed (E4) | **MUST FIX** |
| MC-008 | Viewport meta restricts user zoom | `client/index.html`: `content="width=device-width, initial-scale=1.0, maximum-scale=1"` | Disables/limits pinch-to-zoom, compounding the small-metadata-text contrast issue below | High | Confirmed (E4) | **MUST FIX** |
| MC-009 | The EN/AR language toggle claims a completed language switch it does not perform | `Home.tsx`: handler only sets a local `language` state used for pill styling and fires `toast.success("Interface language set to…")`; no `dir` attribute change, no translation lookup, `--font-ar` token defined but never applied, `lang="en"` hardcoded in `index.html` | Directly relevant to the product's stated Saudi-market positioning; a false "success" on a market-relevant feature is higher-stakes than an average toast-only control | High | Confirmed (E4) | **MUST FIX** (interim relabel/disable) — full RTL build is **NEEDS VALIDATION** (product scope decision) |
| MC-010 | "Operationally ready" and similar certification-grade wording appears in Assessment/Growth copy without any authoritative competency definition behind it | `Home.tsx` copy strings; no rubric, authority, or external validation source anywhere in the supplied source or `ideas.md` | A trainee (or an employer relying on the output) may mistake a local heuristic score for a qualification judgment | High | Confirmed (E4) | **MUST FIX** (copy scope only) |
| MC-011 | Mobile Terminal command input resolves to 15px in Normal mode, not the intended 16px | `index.css`: an unconditional rule sets `.page-practice .terminal-input input{font-size:16px}`; a later rule of **identical selector specificity**, inside `@media(max-width:739px)`, sets the same selector to `15px` — same-specificity ties resolve by source order, so the later (15px) rule wins; independently re-derived in this pass and cross-confirmed by two of the five Stage 3 audits tracing the identical two rules | 15px sits below the well-established 16px threshold that prevents iOS Safari from auto-zooming on input focus, on the product's single most-used input, on its dominant device class | High | Strongly corroborated (E3) | **MUST FIX** |
| MC-012 | Primary-button text/background contrast measures 2.98:1; `--text-faint` measures 3.18:1–3.66:1 against its two primary surfaces — both fail the 4.5:1 WCAG AA threshold for normal text | Self-computed via the WCAG relative-luminance formula against the exact token values (`#ffffff` on `#6f8fff`; `#5d6a85` on `#050914` and `#111a31`); independently cross-confirmed by four of five Stage 3 audits computing the same ratios from the same hex codes | The highest-intent CTA on every screen, and metadata text used throughout the product, are illegible to a meaningful fraction of users | High | Strongly corroborated (E3) | **MUST FIX** |
| MC-013 | Zero `role="tab"`/`aria-selected`/`aria-pressed` across five visually tab-like control groups (mode-tabs, growth-tabs, track-tabs, filter-tabs, metric-switcher) | Direct source read confirms zero occurrences of these attributes anywhere in `Home.tsx` | Screen-reader users cannot perceive which option is currently selected in any of the five groups | High | Confirmed (E4) | **SHOULD FIX** |
| MC-014 | `.is-secondary-view{display:none!important}` removes Growth Record's inactive tab panels from the accessibility tree entirely, not merely from view, whenever History or Reports is the active tab | `index.css` line confirmed; `Home.tsx` confirms the class is applied to the Record-tab panels (`growth-overview`, `growth-grid`, `activity-section`) whenever `growthTab !== "record"` | Assistive-technology users lose access to Record-tab content structurally, not just visually, while on another tab | Medium | Confirmed (E4) | **SHOULD FIX** (fold into MC-013's fix) |
| MC-015 | `AnimatedBar` renders as a bare `<i>` with only a CSS width and an `aria-label`, not `role="progressbar"` with value semantics | Direct source read of the `AnimatedBar` component | Assistive technology cannot programmatically read the represented value as progress | Medium | Confirmed (E4) | **SHOULD FIX** |
| MC-016 | No `<main>` landmark or skip link anywhere in the shell; desktop side-nav items lack `aria-current` (the mobile bottom-nav correctly sets it) | Direct source read of the shell markup | Keyboard/screen-reader users cannot bypass repeated navigation or perceive current-page state on desktop | Medium | Confirmed (E4) | **SHOULD FIX** |
| MC-017 | Focus Mode, the Reference drawer, and the mobile hamburger menu have no confirmed keyboard focus-trap, Escape handler, or return-focus behavior | Direct source read finds no `keydown`/Escape handling or focus-management code around any of the three surfaces | Keyboard/AT users may be unable to reliably exit these states or could tab into obscured background content | Medium–High | Confirmed gap (E4) | **SHOULD FIX** |
| MC-018 | Skill-trend arrow direction/color maps to raw numeric direction, not favorability: mastered, high-scoring skills (92%, 88%) render a down-arrow in green; weak, attention-needed skills (45%, 20%) render an up-arrow in amber — while the accompanying hover text says "up" = *Improving* and (implicitly) "down" = *Stable* | Direct source read of `skillRows` data, the `SkillRow` trend-icon ternary, `.skill-trend--down{color:var(--green)}` / `.skill-trend--up{color:var(--amber)}`, and the hover-preview copy | A skill's trend indicator reads backwards at a glance; the color and the hover-text framing actively contradict each other for the "up" case | Medium | Confirmed (E4) | **SHOULD FIX** |
| MC-019 | `.skill-hover-preview{display:none}` inside the `@media(max-width:739px)` block removes Growth's skill-coaching preview content from layout entirely below 740px — not merely making it harder to trigger | Direct source read; the desktop/tablet `:hover`/`:focus-visible` dual-trigger mechanism is confirmed correctly built and keyboard-accessible above 740px | Mobile/touch learners — the product's primary device class per the screenshot set — lose this coaching content entirely, with no touch-equivalent affordance | Medium | Confirmed (E4) | **SHOULD FIX** |
| MC-020 | Two parallel semantic color-token systems coexist: the base `:root` tokens (e.g. `--navy-950`) and a second `--ab-*` layer (e.g. `--ab-surface-0`) with different hex values for overlapping roles, the latter scoped only to `.page-practice` | Direct source read of both `:root` blocks in `index.css` | Design-system maintainability risk; no direct user-facing defect today, but increases the chance of future inconsistency | Low (user) / Medium (maintainability) | Confirmed (E4) | **SHOULD FIX** |
| MC-021 | Selecting the "Customer Service" track changes only the description paragraph; the milestone list beneath stays populated with Technical-track content and labeling regardless of selection | Direct source read of the track-toggle handler and the `levels` rendering, which is not conditioned on the selected track | Misrepresents curriculum depth to a trainee evaluating which track to pursue | Medium–High | Confirmed (E4) | **SHOULD FIX** |
| MC-022 | Scenarios' "Filters" button duplicates the adjacent, already-functional `filter-tabs` row; the "Sort" `<select>` does not reorder the list despite the scenario objects already carrying sortable fields (difficulty, duration, category) | Direct source read of both controls' handlers | Confusing duplicate control; a cheap, real fix is available since the data already supports it | Medium | Confirmed (E4) | **SHOULD FIX** |
| MC-023 | The mobile bottom-nav's visual tap order (Progression, Scenarios, Practice-center, Growth, Tracking) does not match the "YOUR ROUTE / 0N" breadcrumb numbering shown once a screen loads, which is derived from the canonical (desktop) array order instead | Direct source read of `orderedItems` vs. the canonical `navItems` array; independently confirmed against the seven screenshots — tapping the 2nd bottom-nav icon (Scenarios) lands on a screen reading "YOUR ROUTE / 03"; tapping the 3rd/center icon (Practice) lands on "YOUR ROUTE / 02" | A trainee who taps left-to-right sees breadcrumb numbers that don't follow their tap order — a wayfinding inconsistency | Medium | Confirmed (E4) | **SHOULD FIX** |
| MC-024 | A fixed, unconditional `.terminal-gap{height:130px}` spacer consumes a large share of the mobile Terminal viewport, worst on a first/empty session | Direct source read; confirmed as an oversized empty band in the Practice screenshot | Pushes the active input and the latest useful response lower on an already-constrained mobile screen | Medium | Confirmed (E4) | **SHOULD FIX** |
| MC-025 | Per-command toasts duplicate the persistent Terminal-history feedback for the same event | Direct source read of the submit handler, which both appends to `commandHistory` and fires a toast for the same action | Redundant, fatiguing feedback over a longer session | Low–Medium | Confirmed (E4) | **COULD IMPROVE** |
| MC-026 | Several interactive elements fall below the 44×44px platform convention (icon-buttons shrink to 35px/33px across breakpoints; mode-tabs measure 34px), though all still clear WCAG 2.2 AA's 24×24px minimum | Direct source read of computed dimensions in `index.css` | Minor tap-precision cost on mobile; not a WCAG failure at the AA-minimum level | Low | Confirmed (E4) | **COULD IMPROVE** |
| MC-027 | The `"hint-dependency"` entry in the Assessment error-taxonomy legend is never producible by the actual command-matching/error-assignment logic (only `syntax`, `sequence`, and `decision` are ever assigned) | Direct source read of the legend markup vs. every `errorKind` assignment site in the submit handler | A legend category a trainee can never actually see triggered; minor taxonomy/trust inconsistency, not a functional defect | Low | Confirmed (E4) | **COULD IMPROVE** |
| MC-028 | `ErrorBoundary.tsx` and `NotFound.tsx` exist as complete components but neither is mounted — `App.tsx` renders only `<Home/>` with no router, error boundary, or toast container | Direct source read of `App.tsx`, `main.tsx`; confirmed no `<ErrorBoundary>`, `<Router>`, `<Switch>`, or `<Toaster>` anywhere in the render tree | An unhandled runtime error in `Home.tsx` has no fallback UI and will show a blank page rather than the built (if unpolished) `ErrorBoundary` screen; `NotFound` is unreachable dead code; **separately**, since no `<Toaster/>` is mounted anywhere, none of the 19 `toast.*()` calls in `Home.tsx` (imported directly from `sonner`, not the app's own `ui/sonner.tsx` wrapper) have a confirmed rendering surface — meaning the toast-only controls in MC-006 may not even produce a *visible* toast, which would be a materially worse version of the "false affordance" problem than "click and get a toast with no state change" | Medium–High | Confirmed absence of a mount point (E4); the resulting runtime consequence (whether toasts silently no-op) is **NEEDS VALIDATION** in a live browser | **SHOULD FIX** (mount ErrorBoundary and a Toaster; do not expose raw stack traces) |
| MC-029 | `Map.tsx` (155 lines, a fully built map-style visual component) is not imported by any file in the application; the "View map" control cannot and does not open it | Direct `grep` across `Home.tsx` and `App.tsx` confirms zero references to `Map.tsx` outside its own file | None today (dead code has no runtime effect); relevant only to the "View map" honesty fix in MC-006 and to codebase hygiene | Low | Confirmed (E4) | **COULD IMPROVE** (document as intentionally out of loop; do not activate speculatively — see §K) |
| MC-030 | `index.css` references three `/manus-storage/...` hosted image URLs (hero background, route-map background, terminal-atmosphere background) and one hosted brand-mark logo PNG; none has a local copy anywhere in the supplied archive | Direct source `grep` plus confirmation that no image file of any kind exists in the extracted archive | A standalone/portable build of this codebase (outside the live preview host) would show every atmospheric background **and the logo itself** as broken images, with zero fallback | Medium | Confirmed (E4) | **COULD IMPROVE** (document dependency or bundle assets before handoff) |
| MC-031 | An Umami analytics script is injected via host-specific environment variables (`%VITE_ANALYTICS_ENDPOINT%/umami`, `%VITE_ANALYTICS_WEBSITE_ID%`), pointing at `manus-analytics.com` per `.project-config.json` | Direct source read of `client/index.html` and `.project-config.json` | Deployment-host-coupled; invisible/non-functional if this codebase is ever run outside the current Manus-hosted preview environment | Low | Confirmed (E4) | **COULD IMPROVE** (document for handoff) |
| MC-032 | No processing/loading state exists between command submission and the (synchronous, instant) response | Direct source read — the submit handler computes and renders the result in the same tick | Minor realism gap only; the current local simulation has no real latency to represent | Low | Confirmed (E4) | **COULD IMPROVE** |
| MC-033 | Progress Tracking's KPI cards use decorative `clip-path`/gradient ornamentation that carries no data meaning | Direct source/CSS read, confirmed in the Progress Tracking screenshot | Minor visual noise; does not obscure data | Low | Confirmed (E4) | **COULD IMPROVE** |


---

## E. Master Decision Matrix

*Impact × Confidence × Feasibility × Scope Risk drives ordering, not repetition count. Owner: **UI** = component/markup/state change only; **Content** = copy/labeling decision; **A11y** = accessibility-semantics change; **Product** = requires a product/content-owner decision this audit cannot make; **Engine** = would touch command matching, scoring, or persistence (none of the MUST FIX/SHOULD FIX items below require this); **Runtime** = requires device/browser/screen-reader validation before further action.*

| ID | Area | Specific decision | Classification | Evidence class | User impact | Design consistency | Tech. feasibility | Confidence | Cost | Risk | Validation needed | What must remain unchanged | Owner |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MC-001 | Terminal safety | Blank/whitespace submit must be a no-op with inline validation, never coerced to a command | MUST FIX | E4 | Critical | Strengthens stated identity | High — one conditional guard | Very High | Low | Low | Regression test AN/SS/FQD/FXP after the fix | Command matching, scoring formula | UI |
| MC-002 | Terminal/Coach trust | Coach default state must be neutral before any command exists; error styling only after a real failed command | MUST FIX | E4 | Critical | Strengthens stated identity | High — conditional-render only | Very High | Low | Low | None | Existing real-error styling and copy | UI |
| MC-003 | Evidence honesty | Derive `3/8`, `23/40`, `LOG 04/12` from the arrays/rows they summarize, or explicitly label as illustrative/future | MUST FIX (derivation) | E4 | Critical | Strengthens stated identity | High for derivation; content-dependent for real larger totals | High | Low (derivation) / Medium (content) | Low | Product decision on whether 8/40 are real future totals (§N) | The illustrative nature of underlying sample data itself | UI + Product |
| MC-004 | Assessment integrity | Disclose carried-over history/hints on entering Assessment; make the "No hints" label derive from actual `hintCount` | MUST FIX (UI-safe interim) | E4 | Critical | Strengthens the mode concept | Medium — state-management change, UI-only | High | Medium | Low | Product/learning decision on whether modes should isolate history (§N) | Scoring formula; `localStorage` record shape | UI + Product |
| MC-005 | Evidence honesty | Fresh-session Practice-footer metrics and session timer must read neutral/zero, not seeded values with full visual authority | MUST FIX | E4 | High | Strengthens stated identity | High | High | Low | Low | None | Real post-submission metrics once they exist | UI |
| MC-006 | Interaction trust | Every toast-only control performs its action, is honestly labeled unavailable, or is removed — triaged individually, Coach's "Open reference" and "Backup" first | SHOULD FIX (P0-adjacent for Coach instance) | E4 | High | Strengthens stated identity | Mixed — most UI-only | High | Low–Med | Low | Product decision per control (real feature vs. permanent relabel) | Controls that already work correctly nearby (e.g. Scenarios' `filter-tabs`) | UI + Product |
| MC-007 | Typography | Provision the three declared fonts or change tokens to the actual shipped stack | MUST FIX | E4 | High | Restores stated intent | High | High | Medium | Medium (external asset in a share-preview host) | Confirm computed `font-family` post-fix | Display/mono/Arabic role separation | UI + Runtime |
| MC-008 | Accessibility | Remove `maximum-scale=1` | MUST FIX | E4 | High | Strengthens stated identity | Very High | Very High | Low | Low | Verify no primary flow breaks at 200–400% zoom | Mobile layout strategy; 16px input floor | UI |
| MC-009 | Content honesty | EN/AR toggle must stop implying a working switch — interim disable/relabel | MUST FIX (interim) | E4 | High | Neutral | High | High | Low | Low | Product scope decision on real RTL build (§N) | Nothing else in the topbar | Content + Product |
| MC-010 | Content honesty | Scope "Operationally ready"/readiness language to what a local heuristic supports | MUST FIX | E4 | High (if used with real learners) | Neutral | High | Med–High | Low | Low | None | Debrief's existing category structure | Content |
| MC-011 | Terminal / mobile | Delete the later 15px override; final mobile Normal-mode input font-size must compute to ≥16px | MUST FIX | E3 | High | Restores stated intent | High — delete one declaration | High | Low | Low | iOS Safari + Android Chrome check at 320/360/390/430px post-fix | Every other property in that rule block; Focus Mode's separate, already-correct value | UI + Runtime |
| MC-012 | Color/contrast | Primary-button and `--text-faint` pairings must reach ≥4.5:1 at actual rendered size | MUST FIX | E3 | High | Preserves palette, adjusts values | High | High | Low | Low | Re-measure hover/active/focus/disabled states separately | Vector Blue identity; the token's low-emphasis role via size/weight, not just contrast | UI |
| MC-013 | Accessibility | Add `role="tab"`/`aria-selected` (panel-switching) or `aria-pressed` (filter/toggle) per group, by actual behavior | SHOULD FIX | E4 | High | Additive only | High | High | Low | Low | None | Visual styling of all five groups | A11y |
| MC-014 | Accessibility | Fold Growth's `.is-secondary-view` accessibility-tree removal into the MC-013 tab fix | SHOULD FIX | E4 | Medium | Additive | High | High | Low | Low | None | Visual hide/show behavior | A11y |
| MC-015 | Accessibility | `AnimatedBar` needs `role="progressbar"` + value semantics where it represents real progress | SHOULD FIX | E4 | Medium | Additive | Med–High | High | Low | Low | None | Visual bar rendering | A11y |
| MC-016 | Accessibility | Add `<main>`, skip link, and `aria-current` on desktop side-nav | SHOULD FIX | E4 | Medium | Additive | High | High | Low | Low | None | Existing bottom-nav `aria-current` | A11y |
| MC-017 | Accessibility | Add focus-trap, Escape, and return-focus to Focus Mode, Reference drawer, mobile menu | SHOULD FIX | E4 | Med–High | Additive | Medium | High | Medium | Medium | Keyboard-only test before shipping | Existing scroll-lock/visual mechanisms | A11y + Runtime |
| MC-018 | Data semantics | Map skill-trend icon/color to favorability, not raw numeric direction | SHOULD FIX | E4 | Medium | Neutral | Medium | Medium | Low | Low | None | Underlying `tone`/`trend` data fields; hover-tooltip text | UI |
| MC-019 | Accessibility / mobile | Surface skill-hover-preview content via a tap/selected-state interaction below 740px | SHOULD FIX | E4 | Medium | Preserves working desktop pattern | Medium | High | Low | Low | None | Desktop/tablet hover + `:focus-visible` mechanism | UI |
| MC-020 | Design tokens | Consolidate `--ab-*` and base token layers into one canonical set | SHOULD FIX | E4 | Low (direct) / Medium (maintainability) | Strengthens system coherence | Medium | High | Medium | Low | Grep for stray `--ab-` references post-consolidation | Current visual output | UI |
| MC-021 | Content / IA | Customer Service track shows an honest "not yet available" state instead of Technical content under a Service label | SHOULD FIX | E4 | High | Neutral | Medium (content-dependent for the real fix) | Med–High | Low (empty state) | Low | Content decision on real Service curriculum | Technical track's existing content | UI + Product |
| MC-022 | Interaction | Remove/merge redundant Filters button; wire Sort to existing scenario fields | SHOULD FIX | E4 | Medium | Neutral | High (data already present) | High | Low | Low | None | Working `filter-tabs` row | UI |
| MC-023 | Navigation | Derive breadcrumb number from actual display order, or drop the numeric component | SHOULD FIX | E4 | Medium | Preserves deliberate Practice-centering | High | High | Low | Low | None | Practice-centering itself | UI |
| MC-024 | Mobile layout | Remove/reduce the fixed 130px terminal-gap spacer | SHOULD FIX | E4 | Med–High | Neutral | High | High | Low | Low | Re-check terminal appearance at 0/1/many history entries | Flex-column structure; bottom-anchored active line | UI |
| MC-025 | Feedback | Reserve toasts for session-level events; let Terminal history own per-command feedback | COULD IMPROVE | E4 | Low–Medium | Neutral | High | Medium | Low | Low | None | Terminal history's existing role | UI |
| MC-026 | Touch targets | Raise sub-44px targets toward 44×44 where layout allows | COULD IMPROVE | E4 | Low–Med | Minor sizing only | Medium | Medium | Low | Low | Watch for crowding at narrow widths | Compact operational density elsewhere | UI |
| MC-027 | Taxonomy hygiene | Remove or wire the unreachable `"hint-dependency"` legend entry | COULD IMPROVE | E4 | Low | Neutral | High | Medium | Low | Low | None | Remaining taxonomy | UI |
| MC-028 | Resilience | Mount a styled ErrorBoundary and a `<Toaster/>`; do not expose raw stack traces; style/retire `NotFound` | SHOULD FIX | E4 | Med–High | Aligned if styled to match Flight Deck | Medium | High | Low–Med | Low | Forced-error and 404 test post-mount | Main-flow architecture; no router change required | UI + Runtime |
| MC-029 | Dead code | Document `Map.tsx` as intentionally out of loop pending a roadmap decision | COULD IMPROVE / DEFER | E4 | Low | N/A | High (documentation only) | High | Low | Low | Roadmap-owner decision (§N) | Current unused-but-present state | Product |
| MC-030 | Portability | Document or bundle `/manus-storage/...` image dependencies (including the brand mark) before standalone handoff | COULD IMPROVE | E4 | Low (handoff risk only) | N/A | Medium | Medium | Low | Low | Confirm asset resolution in a clean build environment | Visual result once assets are present | Runtime |
| MC-031 | Portability | Document the host-coupled analytics script for handoff | COULD IMPROVE | E4 | Low | N/A | High | Medium | Low | Low | None | Analytics behavior on the current host | Product |
| MC-032 | Terminal state | Add a brief processing indicator only if desired for realism | COULD IMPROVE | E4 | Low | Neutral | Medium | Low | Low | Low | None | Instant local-simulation logic | UI |
| MC-033 | Visual polish | Simplify decorative KPI-card ornamentation on Tracking | COULD IMPROVE | E4 | Low | Simplifies, doesn't weaken | Medium | Medium | Low | Low | None | KPI data and hierarchy | UI |
| MC-P01 | Visual identity | Flight Deck Console system (§C.1) | PRESERVE | E4 + `ideas.md` | Critical | Is the standard | N/A | High | — | — | — | Entire system as documented in §C.1 | Product |
| MC-P02 | Architecture | Five-screen loop + real cross-screen handoffs (§C.3) | PRESERVE | E4 + `ideas.md` | Critical | Is the standard | N/A | High | — | — | — | `setPracticeContext`, `localStorage` schema, route model | Product |
| MC-P03 | Terminal | Terminal-first architecture, Learn/Practice/Assessment structure, Focus Mode, history recall (§C.2, C.4, C.5, C.10) | PRESERVE | E4 | Critical | Is the standard | N/A | High | — | — | — | Command matching; scoring formula; work-surface dominance | Product |
| MC-P04 | Accessibility | Reduced-motion implementation (§C.6) | PRESERVE | E4 | High | Is the standard | N/A | High | — | — | — | Every rule in the reduced-motion block | A11y |
| MC-P05 | Data viz | Chart + accessible table fallback (§C.7) | PRESERVE | E4 | High | Is the standard | N/A | High | — | — | — | The pattern itself; no library migration | UI |
| MC-R01 | Scope | Redesign, architecture reset, or new information architecture | REJECT | `ideas.md` + E4 | — | Contradicts stated intent | — | High | — | High if attempted | — | — | Product |
| MC-R02 | IA | Merge Growth Record and Progress Tracking into one screen | REJECT | `ideas.md` + E4 | — | Contradicts distinct-loop-stage intent | — | High | — | Medium | Only if future user-task evidence shows trainees cannot locate evidence | — | Product |
| MC-R03 | Navigation | Add a separate top-level Assessment route | REJECT | `ideas.md` + E4 | — | Assessment is a mode, not a destination | — | High | — | Low | — | — | Product |
| MC-R04 | Terminal | Add command autocomplete or alter command matching/scoring | REJECT | `ideas.md` (engine boundary) | — | Conflicts with recall-based training | — | High | — | High if attempted | Only with pedagogical + engine-owner evidence | — | Product |
| MC-R05 | Feature scope | Activate `MapView` because a "View map" label exists | REJECT | E4 (import trace) | — | Unused component proves residue, not need | — | High | — | Low | Only if a curriculum owner defines a map-dependent task | — | Product |
| MC-R06 | Mobile Coach | Add a Coach FAB/bottom-sheet by default | REJECT (this pass) | E4 (no runtime evidence of failure) | — | Adds surface competing with Terminal | — | Medium | — | Medium | Native-keyboard test first (§L) | Current subordinate, in-flow placement | Runtime |
| MC-R07 | CSS claim | Bottom-nav renders as 4 columns (current defect) | REJECT | E4 (full cascade trace) | — | N/A | — | Very High | — | — | — | — | UI |
| MC-R08 | CSS claim | Mobile session-readout is simply hidden | REJECT (as stated) | E4 (full cascade trace) | — | N/A | — | Very High | — | — | Density/legibility validation at narrow widths | — | UI + Runtime |
| MC-R09 | CSS claim | Terminal caret ignores reduced motion | REJECT | E4 (reduced-motion block names it explicitly) | — | N/A | — | Very High | — | — | — | — | UI |
| MC-N01 | Responsive | Tablet (740–1099px) composition | NEEDS VALIDATION | No screenshot; CSS-inferred only | Unknown | N/A pending test | N/A | Low | — | — | Render at 768/834/1024px, task walkthrough | — | Runtime |
| MC-N02 | Responsive | Native on-screen-keyboard behavior at 320–430px | NEEDS VALIDATION | No device evidence | Unknown | N/A pending test | N/A | Low | — | — | Physical/emulated device test | Current sticky/safe-area architecture unless proven insufficient | Runtime |
| MC-N03 | Navigation | Whether the hamburger drawer duplicates the bottom/side nav | NEEDS VALIDATION | Not independently re-verified in this pass | Low–Medium | N/A pending confirmation | N/A | Low | — | — | Direct inspection of drawer contents | — | Runtime |
| MC-N04 | Learning UX | Whether Practice/Learn should enforce command sequence the way Assessment does | NEEDS VALIDATION | E4 source (current behavior); no pedagogy brief supplied | Medium | N/A pending decision | N/A | Medium | — | — | Learning-design/product input | Current behavior unless changed | Product |
| MC-N05 | Content/i18n | Full Arabic/RTL scope for this release | NEEDS VALIDATION | `ideas.md` prohibits new architecture; no translation content supplied | High if in scope | Extends system properly if built | Low this phase | Medium | — | Med–High if rushed | Product scope + translation-resource decision | — | Product |


---

## F. Required Changes by Priority

### F.1 — P0 — Blocking / Must Fix

**MC-001 — Reject blank/whitespace command submission**
- *Objective:* No command, history entry, score, toast, or persisted evidence can be created by submitting nothing.
- *Current behavior:* `command.trim().toUpperCase() || "FQD"` — a blank or whitespace-only submission is coerced to `"FQD"` and processed exactly like a real command.
- *Exact change:* Guard `submitCommand` immediately after `trim()`. If the result is empty, do not call command evaluation, do not append to `commandHistory`, do not touch score/log/hint state, do not persist evidence, do not fire a success toast. Show inline validation in the terminal input region (e.g., `NO ENTRY · TYPE A COMMAND`) and keep focus in the input.
- *Must remain unchanged:* AN/SS/FQD/FXP matching and their existing responses; the assessment scoring formula; `localStorage` structure; context handoffs.
- *Dependencies:* None.
- *Risks:* Low — the guard affects only blank/whitespace input; confirm no existing test or flow relies on blank-submit-as-FQD.
- *Acceptance criteria:* Submitting empty/whitespace input in Learn, Practice, and Assessment produces zero history/score/log/toast change and a visible inline validation message; the four real commands are unaffected.
- *Regression tests:* AN → SS → FQD → FXP sequence still produces identical responses and scores to the pre-fix baseline; Assessment score is unaffected by any number of blank submissions before or between real commands.

**MC-002 — Neutral first-use Coach state**
- *Objective:* The Coach panel never shows an error the trainee did not cause.
- *Current behavior:* `latestEntry?.response ?? "FORMAT ERROR · CHECK ENTRY"`, styled in the error-red `<code>` treatment, renders before any command exists.
- *Exact change:* Replace the pre-command fallback with neutral copy and neutral styling (no `--red` token, no error-implying icon). Render the existing error treatment only when a real failed command exists (`latestEntry?.ok === false`).
- *Must remain unchanged:* The existing error taxonomy and styling for genuine post-submission failures; the Coach concept and its subordinate placement.
- *Dependencies:* None.
- *Risks:* Low.
- *Acceptance criteria:* A freshly loaded Practice screen (cleared session) shows no red/error-styled content in the Coach panel until a real command has been submitted and failed.
- *Regression tests:* Submit a genuinely invalid command after the fix and confirm the real error path still renders with correct styling and copy.

**MC-003 — Evidence provenance and count reconciliation**
- *Objective:* Every headline count is either true of the array/rows it summarizes, or explicitly labeled illustrative/future.
- *Current behavior:* `3/8 stages` against a 6-item `levels` array; `23/40 scenarios` against a 5-item `scenarios` array (one displayed category, "Exchanges & Refunds," has no matching entry in that array); `LOG 04/12` against 3 rendered history rows.
- *Exact change:* Replace each hardcoded fraction with a value derived from its real source (`levels.length`, `scenarios.length`, actual rendered-row count), **or**, where a larger number is a genuine planned-future-content decision rather than a bug, keep it but add an explicit qualifier so both numbers coexist honestly (e.g., "6 available now / 8 planned"). Remove or correct the "Exchanges & Refunds" category label so it matches an entry that actually exists in `scenarios`.
- *Must remain unchanged:* The illustrative/local nature of the underlying sample data itself — this is a request for internal consistency, not for fabricating real content to match a number.
- *Dependencies:* A content/product decision (§N) on whether 8/40 represent real planned totals.
- *Risks:* None for the derivation fix itself.
- *Acceptance criteria:* Every displayed count matches its source array length or rendered-row count, or carries an explicit "planned/illustrative" qualifier; no scenario category label appears that has zero matching entries in the `scenarios` array.
- *Regression tests:* Adding or removing an item from `levels`/`scenarios` correctly updates the displayed count without a separate manual edit.

**MC-004 — Terminate mode-switch state bleed and fix the static "No hints" label**
- *Objective:* An Assessment score and its accompanying hint disclosure can be trusted to reflect only what actually happened during that Assessment.
- *Current behavior:* `setMode(item); setSessionComplete(false);` is the entire mode-switch handler — `commandHistory` and `hintCount` are never reset or isolated. `assessmentScore(commandHistory, hintCount)` scores the full shared history regardless of which mode produced each entry. The Assessment tab's hint indicator is `sessionComplete ? "Report ready" : "No hints"` — it reads `sessionComplete`, never `hintCount`, so it can display "No hints" while hints were, in fact, used earlier in the same session.
- *Exact change (UI-safe interim, no engine change required):* On entering Assessment, if `commandHistory.length > 0` or `hintCount > 0`, show an explicit disclosure ("N prior commands / N hints carried into this session") instead of a silently clean state. Change the tab label to derive from the actual `hintCount` (e.g., `hintCount === 0 ? "No hints" : `${hintCount} hint${hintCount === 1 ? "" : "s"}``), not from `sessionComplete`.
- *Must remain unchanged:* The scoring formula and `localStorage` record shape — whether modes should be fully isolated by design is a separate, larger product/learning-design decision (§N), not resolved by this fix.
- *Dependencies:* None for the interim disclosure; the isolation-vs-continuous product decision is separate.
- *Risks:* Low if scoped exactly as above.
- *Acceptance criteria:* Switching into Assessment with nonzero prior history/hints shows an explicit, accurate disclosure; the tab label always reflects the true current `hintCount`.
- *Regression tests:* A session with zero prior activity entering Assessment shows no disclosure and "No hints"; a session with prior hints shows both the disclosure and a label matching the real count.

**MC-005 — Fresh-session metric honesty**
- *Objective:* No number implying real personal performance appears before real evidence exists.
- *Current behavior:* `const accuracy = submitted ? liveAssessment.accuracy : 86` and static `128`/`210`/`68` literals render in the Practice footer before any command is submitted; the session timer is seeded via `useState(272)` (4:32) rather than starting at 0:00.
- *Exact change:* Show a neutral placeholder (e.g., `—`) for accuracy/commands-mastered/task-progress until a real local value exists; start a new local session's timer at `0:00`, or explicitly label it as seeded/demo time if a pre-seeded feel is intentionally desired.
- *Must remain unchanged:* The metrics' real behavior once genuine local evidence exists.
- *Dependencies:* Product input (§N) on whether the seeded timer is intentional scene-setting or should default to zero.
- *Risks:* Low–Medium; some screenshots will look different pre-submission — this is the intended effect, not a side effect to avoid.
- *Acceptance criteria:* A freshly cleared session shows no fabricated-looking accuracy/mastery/progress numbers and either a `0:00` timer or an explicitly labeled seeded one.
- *Regression tests:* Submitting a real command still updates these values correctly from that point forward.

**MC-006 (Coach + Backup instances only, P0-adjacent) — Fix the two highest-stakes false confirmations**
- *Objective:* No control claims a completed action it did not perform, prioritizing the two instances with the highest trust cost.
- *Current behavior:* The Coach panel's "Open reference" button calls only `toast.info(\`Reference opened: ${coachState.next}.\`)` — it never calls `setReferenceOpen` or opens anything, while its own copy asserts the drawer opened. "Backup" calls only `toast.success("A local evidence backup point has been created.")` with no file, export, or storage write of any kind.
- *Exact change:* Wire Coach's "Open reference" to the same `setReferenceOpen(true)` (and consistent hint-count behavior) as the Terminal-head Reference toggle, so the two entry points behave identically. Relabel "Backup" to something honest ("Local preview — no backup file is written") unless a real local export (e.g., a JSON download of the current `localStorage` evidence) is implemented instead.
- *Must remain unchanged:* The Terminal-head Reference button's existing hint-count behavior, which is correct and should be the single source of truth both entry points share.
- *Dependencies:* A product decision (§N) on whether Backup becomes a real export or a permanent relabel.
- *Risks:* Low.
- *Acceptance criteria:* Clicking Coach's "Open reference" produces the identical drawer state as clicking the Terminal-head Reference button; "Backup" either performs a real, verifiable write or never claims one.
- *Regression tests:* Hint-count increments identically regardless of which of the two Reference entry points is used.

**MC-007 — Provision the declared typography**
- *Objective:* The product renders in its designed typefaces deterministically, not in silent fallback fonts.
- *Current behavior:* The only font-loading markup in `index.html` sits inside a comment explicitly marked for deletion, and even that dead block references `Inter` — a fourth family, not any of the three (`Space Grotesk`, `IBM Plex Mono`, `Cairo`) that `index.css` actually declares as design tokens. Zero `@font-face` rules exist anywhere.
- *Exact change:* Choose one deterministic path — self-host the three correct families as local font files with `@font-face` rules, or use an approved external font-loading path the deployment explicitly permits — and load exactly the families the CSS tokens declare, not `Inter`. If the product intentionally will not ship these fonts, change the CSS tokens to the actual shipped fallback stack instead of leaving the declared names unresolved.
- *Must remain unchanged:* The display/mono/Arabic role separation the tokens already define.
- *Dependencies:* Deployment/asset ownership for the chosen provisioning path.
- *Risks:* Medium if external assets are introduced into a share-preview environment untested for that; low if self-hosted and verified.
- *Acceptance criteria:* Computed `font-family` in DevTools on a heading, a terminal command line, and (once/if Arabic activates) Arabic body text matches the intended family, not a system fallback.
- *Regression tests:* Line-length/wrapping across all five screens is re-checked after the fix, since font metrics change layout math.

**MC-008 — Remove the viewport scaling restriction**
- *Objective:* Restore user pinch/browser zoom.
- *Current behavior:* `maximum-scale=1` in the viewport meta tag.
- *Exact change:* Remove `maximum-scale=1`; do not add a replacement restriction.
- *Must remain unchanged:* The mobile layout strategy and the 16px input floor (MC-011), which together should make zoom unnecessary for normal use even though it must remain available.
- *Dependencies:* None.
- *Risks:* Low; verify no primary workflow becomes unusable at 200–400% zoom.
- *Acceptance criteria:* Pinch and browser zoom function normally on a real mobile browser at every screen.
- *Regression tests:* None beyond the zoom check itself.

**MC-009 — Stop the language toggle from implying a working feature**
- *Objective:* The interface never promises a capability it does not have, especially one tied to the product's stated Saudi-market relevance.
- *Current behavior:* The toggle changes only a local highlight pill and fires `toast.success("Interface language set to…")`; no `dir` attribute change, no translation, no font switch to `--font-ar`, `lang="en"` hardcoded.
- *Exact change:* Until the full-scope decision in §N is made, disable the toggle or relabel it clearly (e.g., "Arabic — coming soon") rather than completing a false "success" interaction.
- *Must remain unchanged:* Nothing else in the topbar.
- *Dependencies:* None for the interim fix; full implementation is a separate, larger decision.
- *Risks:* None for the interim fix.
- *Acceptance criteria:* The toggle no longer fires a success confirmation implying a completed language switch.
- *Regression tests:* None.

**MC-010 — Scope readiness/certification language**
- *Objective:* "Operationally ready" and similar phrases are never mistaken for a production competency judgment.
- *Current behavior:* Assessment/Growth copy uses readiness framing at a local score threshold with no defined authority behind it.
- *Exact change:* Replace with scope-limited prototype vocabulary ("Strong local result," "Local session signal," "Review recommended") until a real competency rubric and authority exist; keep the debrief's existing category structure.
- *Must remain unchanged:* The debrief's category structure and error taxonomy — this is a wording change, not a redesign.
- *Dependencies:* Content-only.
- *Risks:* None.
- *Acceptance criteria:* No copy anywhere in the product implies an authoritative competency judgment without a stated authority behind it.
- *Regression tests:* None.

**MC-011 — Fix the mobile Terminal input font-size cascade regression**
- *Objective:* Restore the product's own documented iOS auto-zoom prevention.
- *Current behavior:* `.page-practice .terminal-input input{font-size:16px}` (unconditional) is overridden by an identically-specific later rule of the same selector inside `@media(max-width:739px)` setting `font-size:15px` — same-specificity cascade order makes 15px the final computed value.
- *Exact change:* Delete the `font-size:15px` declaration (or change it to `16px`) inside that media-query block, under the "Center the primary workspace" comment section, so the computed value is ≥16px at every width in Normal mode. Focus Mode's separate, higher-specificity rule already correctly sets a larger value and needs no change.
- *Must remain unchanged:* Every other property in that rule block (`min-width:0`, button sizing).
- *Dependencies:* None — a single CSS value.
- *Risks:* None; validate at 320/360/390/430px on iOS Safari and Android Chrome post-fix.
- *Acceptance criteria:* Computed `font-size` on the Terminal input is ≥16px at every tested width in Normal mode.
- *Regression tests:* Focus Mode's input size is unchanged; no layout shift at any of the four widths.

**MC-012 — Fix primary-button and `--text-faint` contrast**
- *Objective:* The product's highest-intent CTA and its pervasive metadata text are legible to all users.
- *Current behavior:* White text on `--blue:#6f8fff` (12px/700-weight, which does not qualify for the WCAG large-text exception) measures 2.98:1. `--text-faint:#5d6a85` measures 3.66:1 against `--navy-950` and 3.18:1 against `--panel-solid` — both self-computed via the WCAG relative-luminance formula in this pass.
- *Exact change:* Darken `--blue` for the button pairing (or lighten the button text) until ≥4.5:1 is reached; raise `--text-faint`'s luminance until it clears 4.5:1 against its two most common rendered surfaces. Preserve each token's intended visual role (dominant CTA; quiet/secondary text) through value adjustment, not through a hierarchy or role change.
- *Must remain unchanged:* The Vector Blue identity and the button's role as the single dominant per-screen CTA; `--text-faint`'s low-emphasis role relative to `--text`/`--text-soft`, expressed via size/weight/letter-spacing rather than insufficient contrast.
- *Dependencies:* None — token-value changes only.
- *Risks:* None; re-measure hover/active/focus/disabled states separately after any adjustment, since a passing default state does not guarantee a passing hover state.
- *Acceptance criteria:* Both pairings measure ≥4.5:1 at their actual rendered sizes in every interaction state.
- *Regression tests:* Re-run the WCAG computation against the final shipped hex values for all three surface combinations (`--navy-950`, `--panel-solid`, `--navy-750`), not just one.

### F.2 — P1 — High-Value Improvements

*Same structure as P0, kept proportional. None require engine, scoring, or architecture changes.*

**MC-006 (remaining instances) — Triage the rest of the toast-only controls**
- *Objective:* Every remaining visible affordance performs its action, is honestly marked unavailable, or is removed.
- *Current behavior:* Search, Profile, "My route," "View map," "See all stages," Growth's "View evidence"/"See patterns"/"View history," and Scenarios' "Filters" (also addressed structurally in MC-022) all fire a generic toast with no state change.
- *Exact change:* Case by case — implement real behavior where cheap (Scenarios' Sort, MC-022), relabel as preview/roadmap where a real destination doesn't yet exist, or remove where the control adds no value in its current form.
- *Must remain unchanged:* Controls that already work correctly nearby.
- *Dependencies:* Product decisions per control.
- *Risks:* Low if de-emphasized honestly.
- *Acceptance criteria:* No remaining control both looks actionable and does nothing on click without disclosure.
- *Regression tests:* None.

**MC-013/014 — Shared tab/toggle accessibility semantics**
- *Objective:* Assistive-technology users can perceive selection state across all five tab-like groups and Growth's tab panels.
- *Current behavior:* Zero `role="tab"`/`aria-selected"`/`aria-pressed` anywhere; `.is-secondary-view{display:none!important}` removes inactive Growth panels from the accessibility tree.
- *Exact change:* Build one shared pattern applied by actual behavior: `role="tablist"`/`role="tab"`/`aria-selected`/`role="tabpanel"` for controls that swap an entire panel (mode-tabs, growth-tabs); `aria-pressed` for controls that filter/toggle without swapping a full panel (metric-switcher, filter-tabs, track-tabs — evaluate each individually).
- *Must remain unchanged:* Current visual appearance of all five groups — attributes-only.
- *Dependencies:* None.
- *Risks:* Medium if a visually-tab-like control is given tab semantics despite behaving as a toggle — select semantics by actual behavior, not by appearance.
- *Acceptance criteria:* A screen-reader user can identify the selected option in every group and operate it with standard tab/toggle keyboard conventions.
- *Regression tests:* Visual regression check confirms zero styling change.

**MC-015 — Progress semantics for `AnimatedBar`**
- *Objective:* Assistive technology can read bar values as progress, not decoration.
- *Current behavior:* Bare `<i>` with a CSS width and `aria-label`, no `role="progressbar"`.
- *Exact change:* Add `role="progressbar"` with `aria-valuenow`/`aria-valuemin`/`aria-valuemax` and a meaningful accessible name wherever the bar represents genuine progress.
- *Must remain unchanged:* Visual rendering.
- *Dependencies:* None. *Risks:* None.
- *Acceptance criteria:* Screen reader announces current value and range for every progress bar.
- *Regression tests:* None.

**MC-016 — Landmarks and `aria-current`**
- *Objective:* Keyboard/AT users can bypass repeated navigation and perceive current-page state on desktop.
- *Current behavior:* No `<main>`/skip link; desktop side-nav lacks `aria-current` (mobile bottom-nav has it).
- *Exact change:* Add `<main id="main-content">`, a skip-to-main link, and `aria-current="page"` on the active desktop side-nav item.
- *Must remain unchanged:* Visual layout. *Dependencies:* None. *Risks:* None.
- *Acceptance criteria:* Skip link is the first focusable element and jumps past navigation; screen reader announces current page on desktop.
- *Regression tests:* None.

**MC-017 — Overlay focus behavior**
- *Objective:* Keyboard/AT users cannot tab out of Focus Mode into background chrome and can always exit predictably; the same applies to the Reference drawer and mobile menu.
- *Current behavior:* No confirmed focus-trap, Escape handler, or return-focus behavior around any of the three.
- *Exact change:* Add a focus trap scoped to each surface while active, an Escape handler that exits it and returns focus to the triggering control, and `role="dialog"`/`aria-modal="true"` where the surface is genuinely modal.
- *Must remain unchanged:* Existing scroll-lock/visual mechanisms — additive, not a replacement.
- *Dependencies:* None. *Risks:* An incomplete trap is worse than none — test thoroughly with keyboard-only navigation before shipping.
- *Acceptance criteria:* Keyboard-only user can enter, use, and exit all three surfaces without escaping to unintended background content or losing their place.
- *Regression tests:* Full keyboard-only pass across all three surfaces post-implementation.

**MC-018 — Fix skill-trend semantics**
- *Objective:* A skill's trend indicator reads correctly at a glance and agrees with its own hover text.
- *Current behavior:* Icon/color keyed to raw numeric direction, not favorability; mastered/high skills show green-down, weak/attention skills show amber-up, contradicting the hover copy's "up = Improving" framing.
- *Exact change:* Map icon direction and color to whether the trend is favorable for that specific skill, not to the sign of the underlying number.
- *Must remain unchanged:* Underlying `tone`/`trend` data fields and hover-tooltip text, which already state the intended meaning correctly.
- *Dependencies:* None. *Risks:* None.
- *Acceptance criteria:* Icon/color direction agrees with the hover text's stated meaning for every skill row.
- *Regression tests:* None.

**MC-019 — Mobile skill-coaching parity**
- *Objective:* Coaching content available via hover/focus on desktop is also available on touch devices.
- *Current behavior:* `.skill-hover-preview{display:none}` at ≤739px removes the content from layout entirely.
- *Exact change:* On mobile, surface the equivalent content via a tap/selected-state detail panel rather than only via hover.
- *Must remain unchanged:* Desktop/tablet hover + `:focus-visible` mechanism, already correct.
- *Dependencies:* None. *Risks:* Low.
- *Acceptance criteria:* Content is reachable by tap on a touch device below 740px.
- *Regression tests:* Desktop hover behavior unchanged.

**MC-020 — Design-token consolidation**
- *Objective:* One canonical semantic token system, not two.
- *Current behavior:* Base `:root` tokens and a separate `--ab-*` layer with different hex values for overlapping roles, scoped only to `.page-practice`.
- *Exact change:* Promote the stronger `--ab-*` refinements into the canonical layer; remove the duplicate namespace after migration.
- *Must remain unchanged:* Current visual output — this is a token-organization change, not a visual one.
- *Dependencies:* None. *Risks:* Low if values are preserved exactly during the merge.
- *Acceptance criteria:* Zero remaining `--ab-` references after consolidation; no visual diff.
- *Regression tests:* Full visual comparison of the Practice screen pre/post consolidation.

**MC-021 — Honest Customer Service empty state**
- *Objective:* Selecting a track never shows the other track's curriculum content.
- *Current behavior:* Toggle changes only description text; milestone list stays Technical-labeled regardless of selection.
- *Exact change:* Show an honest "not yet available" state for the milestone list when Customer Service is selected, until real Service curriculum data exists.
- *Must remain unchanged:* Technical track's existing content and the toggle mechanism.
- *Dependencies:* Content-dependent for the eventual real fix; UI-only for the interim honest empty state. *Risks:* None.
- *Acceptance criteria:* Selecting Customer Service never displays Technical-track milestone content under a Service label.
- *Regression tests:* None.

**MC-022 — Scenarios' Filters and Sort**
- *Objective:* Every visible Scenarios control does what it appears to do.
- *Current behavior:* "Filters" duplicates the adjacent working `filter-tabs`; Sort doesn't reorder despite sortable fields already existing on the scenario objects.
- *Exact change:* Remove or merge the redundant Filters button; wire Sort to the existing difficulty/duration/category fields.
- *Must remain unchanged:* The working `filter-tabs` row. *Dependencies:* None. *Risks:* None.
- *Acceptance criteria:* Sort visibly reorders the list; no duplicate filter entry point remains.
- *Regression tests:* None.

**MC-023 — Reconcile mobile nav order with breadcrumb numbering**
- *Objective:* A trainee never sees a breadcrumb number that contradicts the bottom-nav tap position they just used.
- *Current behavior:* Bottom-nav visually reorders to keep Practice centered; "YOUR ROUTE / 0N" is numbered from the canonical (desktop) array order instead, so the 2nd visual icon shows "03" and the 3rd/center icon shows "02."
- *Exact change:* Derive the breadcrumb number from the actual mobile display order, or drop the numeric component and keep only descriptive text.
- *Must remain unchanged:* The deliberate Practice-centering itself.
- *Dependencies:* None. *Risks:* None.
- *Acceptance criteria:* Breadcrumb numbering (if retained) matches the order a mobile user actually taps through.
- *Regression tests:* Desktop side-nav numbering (already canonical-order-correct there) remains unchanged.

**MC-024 — Reduce mobile Terminal dead-space**
- *Objective:* The constrained mobile Terminal viewport is used for content, not fixed empty space, especially on a first/empty session.
- *Current behavior:* `.terminal-gap{height:130px}` is a single, unconditional, never-overridden spacer.
- *Exact change:* Remove or substantially reduce the fixed height; the existing `.terminal-active-line{margin-top:auto}` rule already anchors the input to the bottom of the flex container and can do this job without an additional fixed spacer.
- *Must remain unchanged:* The scrollable flex-column structure and bottom-anchored active line.
- *Dependencies:* None. *Risks:* Low; re-check appearance at 0, 1, and many history entries.
- *Acceptance criteria:* No large empty band on a fresh mobile session; input and latest response remain reachable without excess scroll.
- *Regression tests:* Terminal layout at 1 and 10+ history entries is unaffected.

**MC-028 — Mount resilience surfaces**
- *Objective:* An unhandled runtime error shows a Flight-Deck-styled fallback, not a blank page; toast confirmations have a confirmed rendering surface.
- *Current behavior:* `App.tsx` renders only `<Home/>` — no `ErrorBoundary`, `Router`, or `<Toaster/>` is mounted anywhere; `ErrorBoundary.tsx` exposes a raw stack trace; `NotFound.tsx` is generic light-themed and unreachable.
- *Exact change:* Mount a styled `ErrorBoundary` around the app root that does not expose raw stack traces to the end user; mount a `<Toaster/>` so existing `toast.*()` calls have a confirmed rendering surface; restyle or retire `NotFound` to match the Flight Deck identity if it ever becomes reachable.
- *Must remain unchanged:* Main-flow architecture — no router is required for this fix.
- *Dependencies:* None. *Risks:* Low; verify no other layout assumes the absence of a mounted `Toaster`.
- *Acceptance criteria:* A forced runtime error renders the styled fallback, not a blank screen; a triggered toast call visibly renders.
- *Regression tests:* Full toast-trigger sweep (all 19 call sites) confirms visible rendering post-mount.

### F.3 — P2 — Optional / Later Improvements

*Not required for trust, core usability, the accessibility baseline, or evidence integrity — may be scheduled at team discretion.*

| ID | Change | Reason it's P2, not higher |
|---|---|---|
| MC-025 | Reserve toasts for session-level events; let Terminal history own per-command feedback | Redundant but not misleading — a lower-priority polish, not a trust defect |
| MC-026 | Raise sub-44px touch targets toward 44×44 where layout allows | Already clears WCAG 2.2 AA's 24×24 minimum; this is the stricter platform convention |
| MC-027 | Remove or wire the unreachable `"hint-dependency"` legend entry | Minor taxonomy mismatch with no functional effect |
| MC-029 | Document `Map.tsx` as intentionally out of loop | Zero current user impact; a roadmap-owner decision, not a design defect |
| MC-030 | Document or bundle `/manus-storage/...` image dependencies | Handoff-portability risk only; no effect on the current hosted preview |
| MC-031 | Document the host-coupled analytics script | Deployment hygiene, not a user-facing issue |
| MC-032 | Add a brief processing indicator between submit and response | Minor realism gain; current instant response has no real latency to represent |
| MC-033 | Simplify decorative KPI-card ornamentation on Tracking | Visual noise only; does not obscure data |


---

## G. Component-Level Specifications

*Only components with a confirmed, evidenced change are detailed with a full field set; components with no defect confirmed in this pass are noted briefly under "current state/decision" only, to avoid inventing work.*

### G.1 Shared Shell and Topbar

- **Current state:** Brand mark, route-context text, EN/AR toggle, search icon, profile chip — compact horizontal composition, sticky.
- **Confirmed problem:** Search, Profile, and the language toggle are toast-only or purely cosmetic (MC-006, MC-009).
- **Decision:** Preserve structure; correct utility truthfulness only.
- **Layout/hierarchy:** Unchanged — no new row, no new global search/dashboard surface.
- **Typography:** Route title stays readable; utility labels may remain compact if non-essential, but must never be unreadable *and* actionable at once.
- **Color/non-color cues:** Active-language pill must not use success/confirmation styling unless a real switch occurred (MC-009).
- **Interaction states:** Language — interim disable/relabel (MC-009); Search — real or honest preview; Profile — informational identity or real profile workspace; Menu — real drawer with focus management (MC-017).
- **Responsive behavior:** At ≤390px, preserve the current compact layout; do not let utility icons crowd out route-context text.
- **Accessibility:** Accessible names on all icon controls; visible focus; drawer semantics per MC-017.
- **Provenance:** N/A.
- **Preserve:** Brand lockup, route-context placement, compact console density.
- **Reject:** Adding a large global search/dashboard surface or extra top-level navigation.

### G.2 Primary Navigation and Mobile Rail

- **Current state:** Fixed desktop side-nav (≥1100px) / fixed mobile bottom-nav (<1100px), five items, Practice ("Train") visually centered and emphasized on mobile via `.is-primary`.
- **Confirmed problem:** None in the *rendered* nav itself — the CSS-cascade claim that it renders as 4 columns is refuted by full cascade trace (§J, MC-R07). The real issue is the **breadcrumb numbering mismatch** with the mobile tap order (MC-023), which lives in the receiving screens, not the nav component itself; desktop side-nav also lacks `aria-current` (MC-016).
- **Decision:** Preserve the five-item model and Practice-centering; fix `aria-current` and the breadcrumb-derivation issue.
- **Layout/hierarchy:** Unchanged.
- **Typography:** Unchanged.
- **Color/non-color cues:** Active state already uses both color and position/weight change — acceptable non-color redundancy.
- **Interaction states:** Unchanged.
- **Responsive behavior:** Desktop side-nav visible ≥1100px; mobile bottom-nav visible <1100px — confirmed via full cascade trace, not merely the first matching rule (§J).
- **Accessibility:** Add `aria-current="page"` to desktop side-nav items (mobile bottom-nav already has it) — MC-016.
- **Provenance:** N/A.
- **Preserve:** Five-item structure, Practice/Train centering and visual emphasis on mobile.
- **Reject:** Redesigning the nav model or removing the deliberate centering to "fix" the breadcrumb numbering — fix the numbering derivation instead (MC-023).

### G.3 Primary / Operational Buttons

- **Current state:** `background:var(--blue)`, `color:#fff`, `font-size:12px`, `font-weight:700` — the single dominant CTA per screen ("Resume pricing workflow," "Open recommended practice," etc.).
- **Confirmed problem:** 2.98:1 contrast, fails WCAG AA 4.5:1 for non-large text (MC-012).
- **Decision:** Adjust color value until ≥4.5:1; no other change.
- **Layout/hierarchy:** Unchanged compact height/padding.
- **Typography:** Unchanged unless the contrast fix requires a secondary size/weight adjustment.
- **Color/non-color cues:** The value requiring change; darken `--blue` for this pairing specifically, or use a dedicated darker action-blue token for button backgrounds while preserving `--blue` elsewhere for accents.
- **Interaction states:** Hover/active/focus/disabled must each be independently re-measured — a passing default does not guarantee a passing hover state.
- **Responsive behavior:** No responsive-specific issue found; confirm the fix holds at all breakpoints.
- **Accessibility:** ≥4.5:1 in every state; confirm existing `:focus-visible` treatment survives the color change.
- **Provenance:** N/A.
- **Preserve:** Role as the single dominant per-screen CTA; Vector Blue brand association.
- **Reject:** Reducing this button's visual prominence or replacing it with a lower-contrast "quieter" treatment as a workaround — the fix is a value change, not a hierarchy change.

### G.4 Tabs / Segmented Controls

- **Current state:** Five groups (mode-tabs, growth-tabs, track-tabs, filter-tabs, metric-switcher), each a set of plain `<button>`s with only an `is-active` CSS class marking selection.
- **Confirmed problem:** Zero ARIA selection semantics anywhere (MC-013); Growth's inactive panels are additionally removed from the accessibility tree via `!important` (MC-014).
- **Decision:** Implement one shared pattern, applied by actual behavior, not by appearance.
- **Layout/hierarchy/typography/color:** Unchanged — attributes-only fix.
- **Interaction states:** Panel-swapping groups (mode-tabs, growth-tabs) get `role="tablist"`/`role="tab"`/`aria-selected`/`role="tabpanel"`; filter/toggle groups that don't swap a full panel (metric-switcher, filter-tabs, track-tabs) get `aria-pressed` — evaluate each individually rather than applying one pattern to all five uniformly.
- **Responsive behavior:** Preserve existing horizontal compactness/overflow behavior.
- **Accessibility:** Keyboard operation appropriate to the chosen pattern; selected state announced; Growth's `display:none!important` panels folded into this same fix (MC-014).
- **Provenance:** N/A.
- **Preserve:** Current visual styling of all five groups.
- **Reject:** A one-size-fits-all "every button group is a tablist" implementation regardless of actual behavior.

### G.5 Terminal and Command Input

- **Current state:** Sticky-positioned (`position:sticky; bottom:env(safe-area-inset-bottom)`) input, part of the Practice screen's core loop, with Arrow Up/Down history recall.
- **Confirmed problem:** Blank submission is coerced to a real command (MC-001); mobile Normal-mode font-size resolves to 15px, not the intended 16px (MC-011).
- **Decision:** Preserve architecture; fix both defects as isolated, minimal changes.
- **Layout:** Unchanged — sticky positioning above the safe-area inset is correct.
- **Typography:** `font-size:16px` at every width in Normal mode (MC-011); Focus Mode's separate, already-correct larger value is untouched.
- **Color/non-color cues:** N/A beyond existing caret/prompt styling.
- **Interaction states:** Blank = no-op + inline validation (MC-001); valid = existing evaluation unchanged; invalid non-empty = existing syntax-error path unchanged.
- **Responsive behavior:** Verify 16px holds at 320/360/390/430/739px post-fix, and at the Focus Mode breakpoint.
- **Accessibility:** Clear label (already present); visible focus; 16px is itself an accessibility-relevant fix (prevents involuntary zoom).
- **Provenance:** N/A.
- **Preserve:** Sticky positioning, safe-area handling, Arrow Up/Down recall, the 360px header-restructuring pattern.
- **Reject:** Replacing the sticky/CSS-only approach with a JavaScript viewport-management library absent a failing-device test — no evidence in this package shows the current mechanism, once the font-size bug is fixed, is insufficient.

### G.6 Terminal History and Response Output

- **Current state:** `aria-live="polite"` region rendering command/response pairs in order, with success/error color coding.
- **Confirmed problem:** None distinct from MC-001 (which affects what enters this history) and MC-024 (the fixed empty-space spacer above the active line).
- **Decision:** Preserve the live-region pattern; apply MC-001 and MC-024.
- **Layout:** Remove the fixed 130px pre-output gap (MC-024); no other structural change.
- **Typography/Color:** Unchanged — mono command text, success/error color coding already present.
- **Interaction states:** Unchanged.
- **Responsive behavior:** MC-024 is mobile-specific.
- **Accessibility:** Confirm the existing `aria-live="polite"` scope is appropriate — routine successes should not be announced with the same urgency as errors; consider `aria-live="assertive"` only for genuine errors if testing shows the current single-region approach under-announces them.
- **Provenance:** Every history entry is real local evidence once MC-001 is fixed.
- **Preserve:** The live-region pattern, success/error color coding, chronological ordering.
- **Reject:** N/A.

### G.7 Coach Panel

- **Current state:** Renders in normal document flow below the Terminal on mobile (`order:2`, confirmed **not** an overlay or drawer) and beside it on desktop; shows `latestEntry?.response`, falling back to hardcoded text when no entry exists.
- **Confirmed problem:** Fabricated pre-command error (MC-002); a fake "Open reference" confirmation (MC-006).
- **Decision:** Coach = interpretation + next move, never a duplicate error source or a fake action trigger.
- **Layout:** Unchanged — the existing in-flow (not overlay) placement is confirmed correct on both mobile and desktop and should not be replaced with a FAB or bottom-sheet absent usability evidence the current placement is being missed (§K, MC-R06).
- **Typography/spacing:** Unchanged.
- **Color/non-color cues:** Pre-command state must use neutral/default text color, not the red error treatment (MC-002); genuine post-submission errors keep their existing red treatment.
- **Interaction states:** "Open reference" must produce the identical drawer state as the Terminal-head Reference toggle (MC-006).
- **Responsive behavior:** Mobile in-flow, post-Terminal placement is confirmed correct in the screenshots; do not convert to a FAB/sheet without native-keyboard validation evidence it's needed.
- **Accessibility:** Neutral pre-command state should use `aria-live="polite"` if not already covered, so a genuine post-submission update is announced; the fabricated error state must not carry `role="alert"` semantics, since it was never a real error.
- **Provenance:** N/A.
- **Preserve:** Subordinate position relative to the Terminal; genuine post-submission error/success behavior.
- **Reject:** Converting Coach into a floating action button or bottom sheet by default (§K).

### G.8 Reference Drawer and Focus Mode

- **Current state:** Reference is a toggleable inline drawer beneath the Terminal input; Focus Mode is a CSS-driven immersive state hiding surrounding chrome.
- **Confirmed problem:** No confirmed focus-trap/Escape/return-focus on either surface (MC-017).
- **Decision:** Add the missing keyboard semantics additively; do not assume Focus Mode is a modal dialog if it is genuinely a workspace state — implement the semantics that match its actual behavior.
- **Layout:** Unchanged.
- **Typography/Color:** Unchanged.
- **Interaction states:** Escape exits both; focus returns to the triggering control on exit.
- **Responsive behavior:** No distinct issue beyond MC-017 itself.
- **Accessibility:** Focus-trap while active (if genuinely modal), Escape handling, accessible naming, return-focus (MC-017).
- **Provenance:** N/A.
- **Preserve:** Existing visual/interaction patterns and the `:has()`-based scroll-lock for Focus Mode.
- **Reject:** Treating Focus Mode as a full dialog if usage testing shows it behaves as a workspace state instead — match semantics to actual behavior, not to the most familiar pattern.

### G.9 Progress and Chart Primitives

- **Current state:** `AnimatedBar` (bare `<i>` + `aria-label`); Progress Tracking's hand-built chart with a genuinely-wired `<details>`/table fallback.
- **Confirmed problem:** `AnimatedBar` lacks progress semantics (MC-015).
- **Decision:** Add `role="progressbar"` where a bar represents real progress; preserve the chart+table pattern unmodified.
- **Layout/Typography/Color:** Unchanged.
- **Interaction states:** N/A.
- **Responsive behavior:** No distinct issue.
- **Accessibility:** `role="progressbar"` + value semantics (MC-015); chart's table fallback already correctly accessible — no change needed.
- **Provenance:** N/A.
- **Preserve:** Chart + table fallback pattern in its entirety (§C.7); do not migrate to a charting library.
- **Reject:** Any recommendation to replace the hand-built chart with `recharts` (installed but unused) absent a proven interaction requirement the current pattern cannot meet.

### G.10 Evidence and Metric Cards

- **Current state:** Mixture of computed local values (real once MC-001/004 are fixed) and static preview values, presented with identical visual weight.
- **Confirmed problem:** MC-003, MC-005 — provenance is not currently distinguishable at a glance.
- **Decision:** Add quiet provenance ownership near the value or in an evidence-context header; do not add a new panel per label.
- **Layout:** Compact microcopy addition only.
- **Typography/Color:** Minor, low-emphasis treatment for the provenance label itself.
- **Interaction states:** A metric that is a real action trigger should navigate to the evidence/behavior that owns it.
- **Responsive behavior:** No distinct issue.
- **Accessibility:** Provenance label should be programmatically associated with its value (e.g., via `aria-describedby`), not conveyed by proximity alone.
- **Provenance:** This *is* the fix — see MC-003/005.
- **Preserve:** Existing card layout and visual hierarchy.
- **Reject:** Adding more KPI tiles to demonstrate completeness.

### G.11 Scenario List and Mission Detail

- **Current state:** Filterable list + detail panel with mission framing (`SC-0NN` IDs, difficulty/duration/skills, Resume/Start CTA).
- **Confirmed problem:** Redundant Filters control and non-functional Sort (MC-022); count mismatch (part of MC-003).
- **Decision:** Preserve Mission File framing and the Scenario→Practice handoff; fix the two interaction defects and the count.
- **Layout/hierarchy:** Unchanged.
- **Typography/Color:** Unchanged.
- **Interaction states:** Filters and Sort become real or are honestly removed/relabeled (MC-022); zero-result state should exist if not already present — **NEEDS VALIDATION**, not independently confirmed present or absent in this pass.
- **Responsive behavior:** Long scenario titles crowding the receiving Practice task-strip badge at narrow widths — **NEEDS VALIDATION** (no rendered evidence at the longest actual title in the dataset).
- **Accessibility:** No distinct issue beyond the shared tab/filter semantics fix (MC-013).
- **Provenance:** Scenario ID/context should survive into Practice unchanged — already confirmed working via `setPracticeContext`.
- **Preserve:** Mission File framing, the working `filter-tabs` row, the Scenario→Practice handoff.
- **Reject:** N/A.

### G.12 Growth Record

- **Current state:** Record / History / Reports tabs; skill rows with trend indicators and a hover-preview detail.
- **Confirmed problem:** Fabricated "Backup" (MC-006); accessibility-tree removal via `.is-secondary-view` (MC-014); trend-icon semantics read backwards (MC-018); hover-preview content vanishes below 740px (MC-019); `LOG 04/12` mismatch (part of MC-003).
- **Decision:** Preserve Record/History/Reports as three tabs of one screen — do **not** split into three destinations or merge with Progress Tracking (§C.3, §K). Apply MC-006/014/018/019/003 as specified.
- **Layout/hierarchy:** Unchanged structurally.
- **Typography/Color:** Trend-arrow color remapping only (MC-018).
- **Interaction states:** Tab panels gain proper ARIA association; skill rows gain a mobile-accessible detail interaction; trend arrows remapped.
- **Responsive behavior:** MC-019 is specifically a <740px gap — the ≥740px mechanism is confirmed correct and untouched.
- **Accessibility:** MC-013/014 (tabs), MC-019 (mobile parity).
- **Provenance:** MC-003, MC-005 apply to this screen's counts.
- **Preserve:** Record/History/Reports as three tabs of one destination; the "Read evidence → Practice the gap → Apply in scenario" learning-loop strip (§C.3).
- **Reject:** Splitting Growth into separate routes or merging it with Progress Tracking.

### G.13 Progress Tracking

- **Current state:** Real local-record computation, chart + table, metric switcher, contextual next-action CTA.
- **Confirmed problem:** Decorative KPI-card ornamentation (MC-033); no distinct trust defect confirmed on this screen beyond the shared count-honesty pattern.
- **Decision:** Keep separate from Growth Record (§C.3, §K) — session-level trend is a genuinely different evidence grain from Growth's skill-level interpretation, and `ideas.md` names both as distinct loop stages.
- **Layout/hierarchy:** Unchanged.
- **Typography/Color:** Simplify decorative `clip-path`/gradient ornamentation only (MC-033).
- **Interaction states:** Metric-switcher semantics fold into MC-013.
- **Responsive behavior:** No distinct confirmed issue beyond the shared chart-table pattern, which is confirmed working in the supplied mobile screenshot.
- **Accessibility:** Chart+table fallback (§C.7) is already correct and requires no change.
- **Provenance:** Records displayed here are the same real local evidence Growth reads — confirmed via shared `localStorage` source.
- **Preserve:** This screen as a distinct destination; the chart+table pattern.
- **Reject:** Merging with Growth Record.

### G.14 Language Control

- **Current state:** EN/AR pill toggle in the topbar.
- **Confirmed problem:** Claims a completed language switch with none performed (MC-009).
- **Decision:** Interim disable/relabel pending a scope decision on full RTL (§N).
- **Layout/Typography/Color:** Unchanged for the interim fix.
- **Interaction states:** No longer completes a false "success" toast.
- **Responsive behavior:** N/A.
- **Accessibility:** If full RTL is later approved, `lang`/`dir` attributes, `--font-ar` activation, and bidi handling for mixed LTR command strings all become required — none of that is in scope for the interim fix.
- **Provenance:** N/A.
- **Preserve:** The toggle's visual position and mechanism, ready to become real once RTL scope is approved.
- **Reject:** A partial/cosmetic RTL implementation that changes some but not all of `lang`, `dir`, translation, and font — ship either the honest interim state or a complete, tested implementation, not something in between.

### G.15 ErrorBoundary and NotFound / Fallback Surfaces

- **Current state:** `ErrorBoundary.tsx` and `NotFound.tsx` both exist as complete components; neither is mounted (MC-028). `ErrorBoundary` exposes a raw stack trace; `NotFound` uses a generic light theme inconsistent with the Flight Deck Console.
- **Confirmed problem:** No fallback exists for an unhandled runtime error in the actually-shipped app; `NotFound` is unreachable dead code as currently wired, and would break visual identity if it ever became reachable.
- **Decision:** Mount a styled `ErrorBoundary`; retire or restyle `NotFound` to match the Flight Deck identity before it is ever exposed (MC-028).
- **Layout:** New fallback layout should echo the console's panel/typography language, not the current generic light theme.
- **Typography/Color:** Dark-navy/monospace-consistent, matching §C.1.
- **Interaction states:** Reload/retry action preserved from the existing `ErrorBoundary` implementation.
- **Responsive behavior:** Should be tested at the same breakpoints as the main product once restyled.
- **Accessibility:** No raw stack trace shown to the end user in any environment; reload action must be keyboard-operable.
- **Provenance:** N/A.
- **Preserve:** The existing reload mechanism in `ErrorBoundary`.
- **Reject:** Shipping the raw-stack-trace view to end users in any environment, including staging.


---

## H. Screen and Flow Changes

*No new screens or flows are proposed anywhere in this section — every change operates within the existing five-screen structure, per `ideas.md`'s explicit preservation instruction.*

### H.1 Progression

- **Current issue:** `3/8` stages conflicts with the 6-item `levels` array and only 4 rendered milestones (MC-003); Customer Service track shows Technical content under a Service label (MC-021); "My route"/"See all stages" are toast-only (part of MC-006); expandable "mastered" cards lack `aria-expanded` (folds into MC-013).
- **Decision:** Preserve the "resume where you left off" hero and stage map; derive the stage count from real data; add an honest Service-track empty state.
- **Information hierarchy:** Unchanged — current vector → current evidence → Resume action → upcoming stage → longer-range map is sound.
- **Interaction behavior:** Locked stages should explain their unlock rule inline (already present); current-stage card opens targeted Practice (already present, confirmed working).
- **Empty/loading/error/locked/unavailable states:** Locked-stage treatment is already present and confirmed reasonable; Service-track "not yet available" state is the one addition (MC-021).
- **Responsive requirements:** At 320/360px, prevent the stage list from visually overpowering the current-task card — no rendered evidence of a current problem here; flag as a general check, not a confirmed defect.
- **Accessibility requirements:** `aria-expanded` on expandable level cards (folds into MC-013); progress-bar semantics on the stage-progress indicator (MC-015).
- **Data/provenance requirements:** Stage totals derive from `levels.length` or are explicitly labeled future/planned content (MC-003).
- **Must remain unchanged:** "Resume pricing workflow" routing into Practice with context, confirmed working via `setPracticeContext`.

### H.2 Practice / Terminal

- **Current issue:** The single most consequential screen, carrying the majority of MUST FIX findings: fabricated Coach error (MC-002), blank-submit-to-FQD (MC-001), mode/hint state bleed (MC-004), mobile input font-size regression (MC-011), fixed terminal dead-space (MC-024), Focus Mode's missing focus-trap (MC-017), fresh-session metric honesty (MC-005), a fake Coach "Open reference" confirmation (MC-006), redundant per-command toasts (MC-025).
- **Decision:** Apply MC-001/002/004/005/006/011/017/024/025 as specified in §F. Leave whether Practice/Learn should enforce command sequencing the way Assessment does as an open product/learning-design question (§N, MC-N04) rather than assuming an answer either way.
- **Information hierarchy:** Unchanged — session identity → task/mode → state → output → input → next move → Coach/reference support is confirmed sound.
- **Interaction behavior:** Empty submit becomes a no-op with inline messaging (MC-001); mode switching discloses carried-over state (MC-004); Coach's "Open reference" becomes real (MC-006).
- **Empty/loading/error/locked/unavailable states:** First-use state must be neutral, not error-styled (MC-002); no genuine "processing" state currently exists and none should be invented without a real trigger (§I.3) — MC-032 (adding one) is optional P2 realism, not a requirement.
- **Responsive requirements:** MC-011 (font-size) and MC-024 (terminal-gap) are mobile-specific; native-keyboard behavior at 320–430px is **NEEDS VALIDATION** (MC-N02) — no device evidence exists in this package.
- **Accessibility requirements:** MC-013 (mode-tab semantics), MC-017 (Focus Mode focus-trap), existing `aria-live="polite"` on terminal history is confirmed present and correct.
- **Data/provenance requirements:** MC-005 (fresh-session metrics); MC-004 (hint-count disclosure).
- **Must remain unchanged:** Terminal-first, Coach-subordinate-and-below-on-mobile hierarchy; command matching; scoring formula; Focus Mode's core mechanism.

### H.3 Assessment (as a mode within Practice)

- **Current issue:** Assessment is correctly implemented as a Terminal *mode*, not a route — but the mode boundary is too implicit when `commandHistory`/`hintCount` carry over silently (MC-004), and the "No hints" label doesn't reflect reality.
- **Decision:** Keep Assessment inside the Terminal (§K rejects a separate route). Add the explicit entry-contract disclosure specified in MC-004.
- **Information hierarchy:** Unchanged — Assessment remains a mode selector alongside Learn/Practice.
- **Interaction behavior:** State what carries over before the first assessed command (MC-004); hints remain suppressed from the Reference-drawer increment logic in Assessment mode, confirmed already correctly implemented (`if (nextOpen && mode !== "assessment") setHintCount(...)`).
- **Empty/loading/error/locked/unavailable states:** "Report ready" vs. "No hints" label must derive from real state (MC-004); the debrief (`AssessmentReport`) itself is confirmed to compute genuinely from `commandHistory`/`hintCount` — no fabrication found in the scoring path itself, only in the disclosure around it.
- **Responsive requirements:** No distinct issue beyond the shared Practice-screen items in H.2.
- **Accessibility requirements:** No distinct issue beyond the shared Practice-screen items in H.2.
- **Data/provenance requirements:** The Assessment record written to `localStorage` on "Finish Session" is confirmed real and immediately reflected in Growth/Tracking — this pipeline must not be altered by the MC-004 fix, only the disclosure and label around it.
- **Must remain unchanged:** Scoring formula (`assessmentScore`); `localStorage` record shape; Assessment remaining a Terminal mode, not a route (§K).

### H.4 Scenarios

- **Current issue:** Hard-coded totals and a nonexistent category don't reconcile with the actual 5-scenario dataset (MC-003); redundant Filters control and non-functional Sort (MC-022).
- **Decision:** Preserve Mission File framing and the Scenario→Practice handoff; apply MC-003 and MC-022.
- **Information hierarchy:** Unchanged — scenario identity → state → skills/difficulty/time → mission action → supporting detail is sound.
- **Interaction behavior:** Filters and Sort become real or honestly unavailable; a zero-result filtered state should exist — **NEEDS VALIDATION**, not confirmed present in this pass.
- **Empty/loading/error/locked/unavailable states:** No confirmed gap beyond the zero-result-state question above.
- **Responsive requirements:** Long scenario titles crowding the receiving Practice task-strip badge — **NEEDS VALIDATION**, no rendered evidence at the longest actual title.
- **Accessibility requirements:** Shared tab/filter semantics (MC-013).
- **Data/provenance requirements:** MC-003.
- **Must remain unchanged:** "Resume scenario"/"Start scenario" continuing to hand off into Practice with context exactly as today, confirmed working via `setPracticeContext`.

### H.5 Growth Record

- **Current issue:** Fabricated Backup confirmation (MC-006); accessibility-tree removal of inactive tab panels (MC-014); backwards trend-arrow semantics (MC-018); mobile hover-preview content loss (MC-019); `LOG 04/12` mismatch (MC-003).
- **Decision:** Preserve Record/History/Reports as three tabs of one screen (§C.3, §K — do not split or merge with Tracking). Apply MC-006/014/018/019/003.
- **Information hierarchy:** Unchanged — evidence → pattern → gap → practice action.
- **Interaction behavior:** Tab panels gain proper ARIA association; skill rows gain a mobile-accessible detail interaction; trend arrows remapped to favorability.
- **Empty/loading/error/locked/unavailable states:** The "No evidence recorded" empty state is confirmed already present and correctly triggered when `records` is empty — no change needed there.
- **Responsive requirements:** MC-019 is specifically <740px; the ≥740px mechanism is confirmed correct.
- **Accessibility requirements:** MC-013/014 (tabs), MC-019 (mobile parity), MC-015 (progress semantics on skill bars).
- **Data/provenance requirements:** MC-003 (LOG count), MC-006 (Backup honesty).
- **Must remain unchanged:** "Open recommended/targeted practice" continuing to hand off into Practice with context exactly as today; the "Read evidence → Practice the gap → Apply in scenario" learning-loop strip.

### H.6 Progress Tracking

- **Current issue:** Decorative KPI-card ornamentation carries no data meaning (MC-033); a proposal in the upstream corpus to merge this screen with Growth Record was evaluated and is **rejected** (§K) given `ideas.md`'s explicit naming of both as distinct loop stages operating at different evidence grains.
- **Decision:** Keep as a distinct screen; simplify KPI-card decoration only.
- **Information hierarchy:** Unchanged — skill meaning → behavioral implication → trend → next action.
- **Interaction behavior:** Metric-switcher semantics fold into MC-013.
- **Empty/loading/error/locked/unavailable states:** The "No assessment evidence yet" empty state is confirmed already present and correctly triggered — no change needed.
- **Responsive requirements:** No confirmed issue beyond general validation at 320–430px; the chart+table pattern is confirmed working at the tested screenshot width.
- **Accessibility requirements:** Chart+table fallback (§C.7) is already correct.
- **Data/provenance requirements:** Records displayed are the same real local evidence Growth reads, confirmed via shared `localStorage` source — this pipeline must not be altered.
- **Must remain unchanged:** This screen as a distinct destination from Growth Record; "Open targeted practice" continuing to hand off into Practice with context.

### H.7 Shared Shell and Navigation

- **Current issue:** Language toggle is a false affordance (MC-009); Search/Profile are toast-only (part of MC-006); desktop side-nav lacks `aria-current` and the shell lacks a `<main>` landmark/skip link (MC-016); mobile bottom-nav breadcrumb-numbering mismatch (MC-023); hamburger drawer possibly duplicates the bottom/side nav — **NEEDS VALIDATION** (MC-N03), not independently re-verified against actual drawer contents in this pass.
- **Decision:** Interim-disable/relabel the language toggle; triage Search/Profile per MC-006's tiering; add missing landmarks/attributes; fix breadcrumb derivation; validate the hamburger-drawer redundancy claim before acting on it.
- **Information hierarchy:** Unchanged — the shell's structure (topbar + bottom-nav-or-side-nav depending on width) is confirmed sound.
- **Interaction behavior:** Only as specified above; nav switching and Focus-Mode entry are otherwise unchanged.
- **Empty/loading/error/locked/unavailable states:** N/A at the shell level.
- **Responsive requirements:** Confirm whether the 740–1099px tablet range's continued use of mobile-style nav chrome (rather than a tablet-specific pattern) is deliberate — **NEEDS VALIDATION** (MC-N01), no screenshot evidence either way.
- **Accessibility requirements:** MC-016 (landmarks), MC-017 (mobile-drawer focus behavior).
- **Data/provenance requirements:** N/A.
- **Must remain unchanged:** The five-item nav structure and its order; Practice/Train's mobile-centered emphasis.

### H.8 Cross-Screen Evidence Loop

- **Decision:** Protect this as a regression-critical transition contract, confirmed genuinely working in the current source and not to be broken by any change above:
  - Progression → Practice context handoff (`setPracticeContext`) remains correct.
  - Scenario → Practice preserves scenario context.
  - Growth/Tracking → Practice opens the relevant targeted context.
  - Assessment "Finish Session" → real `localStorage` write → Growth/Tracking immediately reflects it.
- **Must remain unchanged:** Any visual refactor that breaks one of these four handoffs is a regression even if the affected screen looks better in isolation — this is the product's single most substantial piece of working architecture (§C.3) and the primary regression gate for this entire revision (§M).


---

## I. Responsive, Accessibility, and State Requirements

### I.1 Responsive Requirements

Every item below is labeled by evidence type. **Directly observed** = confirmed against one of the seven supplied screenshots. **CSS/source-inferred** = traced through the actual cascade in this pass but not visually confirmed at that width. **Unverified runtime** = no evidence of any kind exists in the supplied package; treat as an open question, not a defect, until tested.

| Width | Status | What is known |
|---|---|---|
| **320px** | CSS/source-inferred | `body{min-width:320px}` is the explicit floor; no dedicated sub-360px rule set exists — 320px inherits entirely from the 360px breakpoint's rules. Not confirmed broken; not confirmed correct. **Test:** render all five screens at exactly 320px; confirm no horizontal scroll, no clipped command field/Execute action, no overlapping header controls. |
| **360px** | Directly observed (screenshots are ~360–430px) | Header restructuring, mode-tabs, and Terminal layout are confirmed rendering correctly at this general width band. |
| **390px** | Directly observed (within screenshot range) | No confirmed issue. |
| **430px** | Directly observed (within screenshot range) | No confirmed issue. |
| **≤739px generally** | Directly observed + CSS-confirmed | Bottom-nav renders as 5 equal columns (confirmed via full cascade trace, §J); session readout is present via a later Practice-scoped rule (§J); `.skill-hover-preview` is confirmed `display:none` at this range (MC-019). |
| **740–1099px (tablet)** | **Unverified runtime — NEEDS VALIDATION** | CSS shows multi-column content grids beginning at 740px while navigation stays mobile-style (bottom-nav/hamburger) until 1100px. No screenshot exists at this width. **Test:** render Progression, Practice, Scenarios, Growth, Tracking at 768/834/1024px; confirm content grids display at intended column counts, confirm whether the mobile-nav-plus-desktop-grid combination reads as a deliberate "large mobile" experience or an unreviewed gap, and confirm whether Practice's `.is-primary` mobile emphasis (currently scoped only to ≤739px) needs to extend into this range. |
| **1100px+ / 1280px+ (desktop)** | **Unverified runtime — NEEDS VALIDATION** | Side-nav is confirmed present via cascade trace (`display:flex` at ≥1100px); Terminal/Coach split-width layout is defined in CSS but never visually confirmed. **Test:** capture the current desktop render at 1280/1440px and compare against the CSS-derived expectations in §G/§H before treating any desktop-only claim elsewhere in this report as more than CSS-derived. |
| **Native on-screen keyboard (320–430px)** | **Unverified runtime — NEEDS VALIDATION** | No physical-device or emulated native-keyboard evidence exists anywhere in the supplied package. **Test:** on real iOS Safari and Android Chrome, focus the command input with prior history present; confirm the most recent 2–3 history entries remain visible above the keyboard or that the page scrolls to keep them visible, and confirm the sticky input and Execute button remain reachable. |

Do not treat the absence of a desktop/tablet screenshot as proof of a responsive failure — no claim above is asserted as a defect without either a screenshot or a full CSS-cascade trace behind it.

### I.2 Accessibility Requirements

| Requirement | Status | Detail |
|---|---|---|
| Landmarks and skip link | **Source-confirmed gap** | No `<main>` or skip link anywhere in the shell (MC-016). |
| Heading hierarchy and route-change focus | **Source-confirmed, partial** | `<h1>`/`<h2>` structure is present and generally sound per screen; no confirmed route-change focus management (focus does not appear to move to a heading or landmark on navigation) — folds into MC-016's fix scope. |
| Tab/toggle/pressed/current/selected semantics | **Source-confirmed gap** | Zero `role="tab"`/`aria-selected`/`aria-pressed` across five groups (MC-013); mobile bottom-nav correctly uses `aria-current`, desktop side-nav does not (MC-016). |
| Keyboard navigation and roving focus | **Source-confirmed, partial** | Standard tab order exists via native `<button>`/`<input>` elements; no roving-tabindex pattern is needed unless the tab-semantics fix (MC-013) introduces a `role="tablist"` pattern that would conventionally use one — implement per the chosen ARIA pattern. |
| Focus-visible treatment | **Source-confirmed present** | `:focus-visible{outline:2px solid var(--cyan)}` global rule confirmed in `index.css` — a genuine strength, not a gap. |
| Focus containment, Escape, focus restoration | **Source-confirmed gap** | No confirmed focus-trap/Escape/return-focus on Focus Mode, Reference drawer, or mobile menu (MC-017). |
| Accessible names for icon controls | **Source-confirmed, partial** | Several icon-only buttons carry `aria-label` (confirmed present on multiple controls); not exhaustively verified across every icon control in this pass — spot-check during MC-013/016/017 implementation. |
| Live-region scope and announcement urgency | **Source-confirmed, partial** | Terminal history uses `aria-live="polite"` (confirmed, correct for routine updates); the Coach panel's dynamic updates are not confirmed to carry an equivalent live region — recommend `aria-live="polite"` there too as part of MC-002's fix, and reserve any `assertive` urgency for confirmed genuine errors only. |
| Progressbar and table semantics | **Source-confirmed gap (progressbar) / present (table)** | `AnimatedBar` lacks `role="progressbar"` (MC-015); the Tracking `<details><div role="table">` pattern is confirmed correctly implemented with `role="row"`/`role="columnheader"`/`role="cell"`. |
| Contrast and final rendered type size | **Self-computed, confirmed failing** | Primary-button 2.98:1, `--text-faint` 3.18–3.66:1, both against the actual token hex values (MC-012). |
| Touch-target size | **Source-confirmed, sub-optimal but not WCAG-failing** | Icon-buttons shrink to 35px/33px across breakpoints, mode-tabs measure 34px — all clear WCAG 2.2 AA's 24×24px minimum but fall short of the 44×44px platform convention (MC-026). |
| Zoom and text scaling | **Source-confirmed failing** | `maximum-scale=1` restricts pinch/zoom (MC-008). |
| Reduced motion | **Source-confirmed strength** | Global catch-all plus component-scoped refinements, confirmed covering the terminal caret explicitly and the JS-driven counting animations via a `matchMedia` check in the hooks themselves (§C.6) — no gap found. |
| Non-color state communication | **Source-confirmed, mostly present** | Most states pair color with text/icon (e.g., `state-notice-mark` + heading text); the skill-trend arrows are the one confirmed exception where color and icon direction actively work against comprehension rather than reinforcing it (MC-018). |
| Screen-reader validation | **Unverified runtime — NEEDS VALIDATION** | No NVDA/VoiceOver/TalkBack session exists in the supplied package; every ARIA-semantics fix above should be validated with a real screen reader before being considered closed, not merely implemented to spec. |

### I.3 Canonical State Matrix

*This table defines the honest UI contract for each state actually reachable in the current implementation. It does not invent processing, retry, or interruption behavior the engine does not expose — where no real trigger exists, the "Confirmed or validation-gated" column says so explicitly rather than presenting an invented state as real.*

| State | Trigger | Visible contract | Allowed action | Evidence/score effect | Accessibility announcement | Confirmed or validation-gated |
|---|---|---|---|---|---|---|
| First use | Practice loaded with no prior commands this session | Neutral "AWAITING COMMAND" copy, no error styling (post-MC-002 fix) | Type/submit a command | None | `aria-live="polite"` on state change | **Confirmed** — current behavior violates this contract today (MC-002); fix defined in §F |
| Empty input | Submit with blank/whitespace-only field | Inline validation message, terminal state unchanged | Retry with real input | None whatsoever (post-MC-001 fix) | Inline text is programmatically associated with the input | **Confirmed** — current behavior violates this contract today (MC-001); fix defined in §F |
| Ready | Terminal idle, awaiting next command, history may be non-empty | `SESSION / READY` readout (confirmed existing pattern) | Submit next command | None | N/A (static state) | **Confirmed present and correct** |
| Processing | *No real trigger exists in the current implementation* — response is synchronous | N/A | N/A | N/A | N/A | **Not real engine state; do not invent it.** An optional cosmetic delay (MC-032) is P2 realism only, not a state to be "fixed" |
| Success | Valid command matched, response `ok:true` | Green success styling + response text in history | Submit next command | Appended to `commandHistory`; may raise score in Assessment | `aria-live="polite"` (confirmed present) | **Confirmed present and correct** |
| Partial / review | Sequence-valid command submitted out of expected Assessment order | `SEQUENCE ERROR · EXPECTED WORKFLOW STEP differs` (confirmed existing copy) | Continue or correct sequence | Recorded as non-`ok`; affects sequencing score | `aria-live="polite"` (confirmed present) | **Confirmed present and correct** |
| Syntax error | Unrecognized command string | `SYNTAX ERROR · CHECK ENTRY FORMAT` (confirmed existing copy) | Retry | Recorded as non-`ok` | `aria-live="polite"` (confirmed present) | **Confirmed present and correct** |
| Sequence error | Valid command, wrong Assessment-mode order | Same as Partial/review row above | Retry in order | Recorded as non-`ok`; affects sequencing score | `aria-live="polite"` | **Confirmed present and correct** |
| Recoverable error | Any non-`ok` response above | Coach's "Next useful move" copy points to a corrective action (confirmed existing pattern) | Follow suggested next step | None beyond the originating error | Covered by the same live region | **Confirmed present and correct** |
| Interrupted | *No real trigger exists* — no network calls, no async operations to interrupt | N/A | N/A | N/A | N/A | **Not real engine state; do not invent it** |
| Assessment active | Mode = "assessment" | Hints suppressed in footnote copy (confirmed); hint-count label must derive from real `hintCount` post-MC-004 fix | Submit commands under evaluation | Full scoring applies | Mode-change should be announced (folds into MC-013's tab semantics) | **Partially confirmed** — mode-suppression logic is correct; the hint-disclosure label is not (MC-004) |
| Assessment complete | "Finish Session" clicked with ≥1 command in history | `AssessmentReport` renders with real computed score (confirmed genuine, not fabricated) | Retry assessment (resets history/hints) or navigate away | Real `localStorage` write, confirmed immediately reflected in Growth/Tracking | `aria-live="polite"` on the report region (confirmed present via `aria-live="polite"` on `.assessment-report`) | **Confirmed present and correct** |
| Locked | Progression stage beyond current unlock point | Explains unlock rule inline via toast (confirmed present, though delivered only as a toast — see MC-006 tiering for whether this specific instance needs a persistent inline alternative) | None (by design) | None | Should not rely on toast alone if MC-028's Toaster-mount question resolves unfavorably — **NEEDS VALIDATION** | **Confirmed present; delivery mechanism (toast-only) is a secondary honesty question, not a fabrication** |
| Unavailable | Customer Service track selected (no curriculum data) | Currently: Technical content mislabeled as Service (defect, MC-021); Target: explicit "not yet available" state | None until real content exists | None | State-notice pattern (confirmed reusable component exists — `StateNotice`) should be used here | **Confirmed defect; fix defined in MC-021** |
| Loading | *No real trigger exists* for command submission; Growth/Tracking's own empty-state loading (if any async fetch existed) is not present either — this is a fully local/synchronous product | N/A | N/A | N/A | N/A | **Not real engine state; do not invent it** |
| No evidence yet | Growth/Tracking with zero `localStorage` records | `StateNotice state="empty"` pattern (confirmed present and correctly triggered on both screens) | CTA to start an assessment | None | Confirmed using the existing `state-notice` component with appropriate `role` | **Confirmed present and correct** |
| Illustrative/sample data | Seed records (`seedProgress`), fresh pre-submission Practice-footer metrics, Progression/Scenarios/Growth headline counts | Currently indistinguishable from real evidence (MC-003, MC-005); target: explicit "illustrative/local" labeling extending the pattern already used correctly in the Terminal ("LOCAL TRAINING SIMULATION") | N/A | None — must never silently influence a real score | Provenance label should be programmatically associated with the value it describes | **Confirmed defect; fix defined in MC-003/005, pattern to extend defined in §C.11** |


---

## J. Conflict Resolution Log

*Every conflict below was traced to the strongest available evidence in this pass, not resolved by counting how many of the five Unified Audits took each side.*

| Conflict ID | Conflicting claims | Strongest evidence | Decision | Rationale | Follow-up validation |
|---|---|---|---|---|---|
| CR-01 | Bottom-nav renders as 4 columns (a stale claim traceable to an upstream source that cited `.bottom-nav{grid-template-columns:repeat(4,1fr)}` in isolation) vs. it renders as 5 (multiple Stage 3 audits, after full cascade tracing) | Direct cascade trace in this pass: the base rule (4 columns) is overridden by three later rules — one unconditional, one inside a media query, and one carrying `!important` — all setting 5 equal columns; confirmed against every screenshot showing a single-row, 5-icon rail | **REJECT** the 4-column claim as a current defect | CSS declarations are not proof of final computed behavior without cascade analysis (governing rule, §8 of the prompt). The 4-column rule exists in the file but is never the winning rule at any width once the full file is read in source order. This is the clearest example in the corpus of why repetition across audits — even when several independently cite the same line — is not the same as verification. | None; the rendered behavior is already correct. Optional CSS hygiene: delete the 3 redundant reinforcing declarations and keep one canonical 5-column rule (MC list, P2-tier — folded into general token/CSS cleanup, not separately numbered as it has zero user-facing effect). |
| CR-02 | Mobile Practice session-readout is "hidden" on mobile (stale claim) vs. it is present via a later, Practice-scoped rule (multiple Stage 3 audits) | Direct cascade trace: an early, generic rule hides `.terminal-session-readout` at ≤739px; a later `.page-practice`-scoped rule restores/repositions it | **REJECT** "simply hidden" as the current state; **MODIFY** to "present but density/legibility should be validated" | The generic hiding rule is real but not final — a more specific, later rule brings it back for the Practice screen specifically. Treating this as "fixed, ignore" would be as wrong as treating it as "broken, fix urgently" — the honest position is that visibility is confirmed, but whether it reads comfortably at 320–360px alongside the rest of the compact terminal header has no rendered evidence and should be checked, not assumed either way. | Render Practice at 320/360px and visually confirm the readout is legible, not merely present in the DOM. |
| CR-03 | Terminal caret ignores `prefers-reduced-motion` (claim traceable to at least two upstream sources referenced within the Stage 3 corpus) vs. it is covered (multiple Stage 3 audits, this pass) | Direct source read: the global reduced-motion block uses a universal `*` selector on `animation-duration`, which covers `.terminal-caret`'s blink animation without needing to name it specifically; a separate later block additionally names other motion-bearing classes explicitly | **REJECT** the "ignores reduced motion" claim | The universal selector is easy to miss if only the component-specific reduced-motion rules are checked — the caret is covered by the *global* catch-all, not a component-specific one, so a search for `.terminal-caret` inside `@media(prefers-reduced-motion)` blocks alone would (incorrectly) come up empty. This is confirmed by reading the full block, not a targeted string search. | None; already correct. |
| CR-04 | Fonts are confirmed not loaded (four of five Stage 3 audits, with direct `index.html` access) vs. font-provisioning is unverifiable / NEEDS VALIDATION (v0.dev's Stage 3 audit, which explicitly states its evidence package did not include `index.html`) | Direct `index.html` read in this pass: the only font-loading markup sits inside a comment marked for deletion, and even that dead markup references the wrong family (`Inter`, not the three declared tokens) | **ACCEPT** "not loaded" as confirmed | This is not a factual disagreement between the audits — it is an evidence-access gap in one audit's supplied package, which this pass's direct file access closes. v0.dev's own epistemic caution (marking it NEEDS VALIDATION rather than guessing) was the *correct* response given what it had; the correct response given what this pass has is to confirm it outright. | None; confirmed via direct file read, independently reproducible by anyone with the same archive. |
| CR-05 | Viewport zoom is restricted (four of five audits, direct access) vs. NEEDS VALIDATION (v0.dev, same access gap as CR-04) | Direct `index.html` read: `maximum-scale=1` is present in the viewport meta tag | **ACCEPT** as confirmed | Same evidence-access-gap pattern as CR-04, resolved the same way. | None. |
| CR-06 | Whether the Coach should be removed, collapsed by default, converted to a drawer/FAB, or simply made subordinate (proposals for a mobile FAB/bottom-sheet pattern appear in the upstream corpus referenced within the Stage 3 audits; all five Stage 3 audits themselves converge on "keep subordinate") | Direct source read confirms Coach already renders in normal document flow, below the Terminal on mobile (`order:2`), not as an overlay; no screenshot or device evidence shows the current placement failing | **REJECT** the FAB/bottom-sheet proposals for this revision; **ACCEPT** "keep subordinate, fix its two content defects (MC-002, MC-006)" | Converting a working, in-flow, already-subordinate component into a new interaction surface (FAB/drawer) would add product surface and interaction cost to solve a problem — poor mobile discoverability — that has no supporting evidence in this package. The current placement is confirmed rendering correctly in the mobile screenshot. If native-keyboard testing (MC-N02) later shows real evidence the current placement is missed or obstructive, this decision should be revisited with that evidence — not before. | Native-keyboard/device testing at 320–430px (MC-N02); only revisit if that testing produces evidence of a real discoverability or occlusion problem. |
| CR-07 | Whether Assessment should be a separate top-level route vs. remain a Terminal mode (a new-route proposal appears in the upstream corpus; all five Stage 3 audits converge on "remain a mode") | `ideas.md`'s stated loop names Assessment as a stage in the learning sequence, not as one of the product's named top-level destinations; direct source confirms Assessment is fully implemented as a `mode` value alongside `learn`/`practice`, sharing the Terminal's state | **REJECT** a separate route; **ACCEPT** "remain a mode," fix the state-bleed problem within that model (MC-004) | A new route would fragment the Terminal's continuity (history, hints, Focus Mode) across a navigation boundary for no evidenced benefit, and directly contradicts the reference-preservation constraint in `ideas.md`. The actual problem with Assessment (MC-004) is a state-isolation bug, not a navigation-architecture problem — a new route would not even fix it. | None; this is a scope decision with clear evidence behind it, not a runtime question. |
| CR-08 | Whether Growth Record and Progress Tracking should merge into one analytics screen (a merge proposal appears in the upstream corpus; all five Stage 3 audits converge on "keep separate") | `ideas.md` names both as distinct stages of the same canonical loop (`"Growth → Tracking"` as two separate steps); direct source confirms they read different grains of the same underlying evidence — Growth interprets skill-level mastery patterns, Tracking exposes session-level longitudinal trend | **REJECT** the merge; **ACCEPT** "keep separate," reduce surface-level metric redundancy between them if it becomes confusing in practice | Two screens serving genuinely different questions ("what am I good/weak at" vs. "am I improving over time") is a defensible information-architecture choice with explicit product-intent backing, not accidental duplication. Merging them would remove a real distinction to solve a redundancy concern that has a smaller, safer fix available. | Only reopen if future user-task evidence specifically shows trainees cannot locate the evidence they're looking for under the current split. |
| CR-09 | Whether `MapView`/`Map.tsx` should be activated (because a "View map" label exists) or removed (as dead code) (both proposals appear in the upstream corpus; all five Stage 3 audits converge on "neither — leave documented, decide later") | Direct `grep` confirms `Map.tsx` is not imported by any file in the application; `ideas.md` does not require geographic mapping as a product capability | **REJECT** speculative activation; **DEFER** removal pending a roadmap-owner decision | The mere presence of a matching label ("View map") and a matching unused component is not evidence the feature is needed — it is evidence of prior scaffolding. Activating it would add scope and a new dependency (Google Maps proxy, per the component's own header comment) with no product requirement behind it. Removing it outright is also not urgent, since unused code has zero runtime effect; a roadmap owner should decide whether it represents planned future work before it is deleted. | Roadmap-owner decision on whether a map-dependent learning task is planned (§N). |
| CR-10 | Whether Arabic/RTL is in current scope (the language toggle's own copy implies "yes, and it already works"; all five Stage 3 audits converge on "no, not as currently implemented") | Direct source read: no `dir` attribute logic, no translation lookup, `--font-ar` token defined but never applied anywhere, `lang="en"` hardcoded in `index.html`; `ideas.md` prohibits new architecture for the current preview phase | **ACCEPT** "not in current scope as implemented"; interim fix is the toggle's honesty (MC-009), **NOT** a full RTL build | The toggle's own success-toast copy ("Interface language set to…") is the *only* evidence anything happened, and it is contradicted by every other piece of source evidence. A full RTL build is real architecture and content work `ideas.md` does not authorize without a separate scope decision — the two questions (should the toggle stop lying today vs. should full RTL ship eventually) have different urgency and different owners and must not be conflated into one decision. | Product/content scope decision on whether and when full RTL ships (§N, MC-N05). |
| CR-11 | Whether any proposed "processing," "interrupted," or richer state (of the 14 values the `SystemState` type declares) reflects real engine behavior or would be invented UI state (a general tension present across the upstream corpus's state-related suggestions; the five Stage 3 audits vary in how explicitly they flag this) | Direct source read: command submission is synchronous — there is no network call, no async boundary, and therefore no real "processing" or "interrupted" moment to represent; 11 of the 14 declared `SystemState` values have no distinct CSS treatment anywhere in `index.css` | **REJECT** inventing visual treatment for states with no real trigger; **ACCEPT** documenting the type as broader than the current UI needs, or narrowing it to match reality | This is the clearest instance of the prompt's own governing principle — *"the UI may interpret engine state, but it must never invent engine truth"* — applying directly to a concrete implementation choice. A state table (§I.3) that invented a "processing" visual contract for a synchronous product would itself be a small instance of the exact defect this whole audit exists to catch elsewhere (fabricated states presented as real). | Only add real visual treatment for a `SystemState` value if and when a real trigger for it is added to the engine — do not build the UI ahead of the state it would represent. |
| CR-12 | Whether numeric values (`8` stages, `40` scenarios, `12` log entries, `210` commands) are simply wrong, are future-curriculum totals, are seeded preview values, or are merely unlabeled (all five Stage 3 audits raise this; none resolves it definitively, and this pass does not either) | Direct source read confirms only that these numbers do not match the arrays/rows currently rendered; no content brief, curriculum plan, or product-owner statement exists anywhere in the supplied package to say which explanation is correct | **DEFER FOR VALIDATION** — this is the one central ambiguity in the entire evidence package that cannot be resolved from UI evidence alone | The *derivation mismatch itself* is confirmed and MUST FIX regardless of which explanation turns out to be correct (MC-003) — a number should never contradict the data it claims to summarize, whether the ultimate content answer is "6 is correct, fix the label" or "8 is correct, the content just isn't built yet." But *which* of those two fixes is the right permanent one is a content/product decision this audit cannot make, and asserting one over the other without that input would be inventing a product decision, not reporting evidence. | Product/content-owner statement on whether 8/40/12/210 represent real planned totals (§N, OQ-style entries). |
| CR-13 | Whether the Coach panel's second "Open reference" control and the Terminal-head "Reference" toggle are the same mechanism (an implicit assumption in at least one upstream source, since both are labeled "Reference") vs. two independent, inconsistently-wired controls (flagged as a distinct, higher-stakes finding by one of the five Stage 3 audits) | Direct source read in this pass confirms they are governed by two entirely separate handlers: the Terminal-head button calls `setReferenceOpen` and correctly increments `hintCount`; the Coach panel's button calls only `toast.info(...)` and touches neither piece of state | **ACCEPT** "two independent, inconsistently-wired controls" as confirmed, and elevate it within MC-006's tiering | This was independently re-verified line-by-line in this pass specifically because the two controls sharing a label made it easy to assume — incorrectly — that they shared behavior. They do not. The Coach instance is worse than an average toast-only control because its confirmation copy explicitly asserts a state change ("Reference opened: …") that never occurs. | None; confirmed by direct code read, reproducible by grepping both `onClick` handlers. |
| CR-14 | Reliability of claims traced back to an upstream ("Kimi") source referenced within the Stage 3 corpus but not itself one of the five files supplied to this pass | Two of the five Stage 3 audits (Manus, Claude) independently flag the same upstream source as containing claims contradicted by direct source inspection — invented color-token values, a claim the Terminal and Scenarios screens are "missing or simplified" when they are the most fully-built screens in the application, and an internally-inconsistent cross-audit scorecard | **REJECT** any claim in the five-file corpus whose only support traces back to that source | This is not a claim about the AeroBridge product — it is a note on evidence discipline. No finding in this Master Audit relies on that source; it is logged here because two independent Stage 3 passes catching the same unreliable evidence, for documented reasons, is itself useful information about how much weight "cross-audit agreement" should carry elsewhere in this corpus (governing principle, §B). | None; no action item results from this row — it is a methodology note, not a product finding. |


---

## K. Explicit Rejection List

| ID | Rejected recommendation | Why rejected | Evidence or boundary | Future validation needed? |
|---|---|---|---|---|
| RJ-01 | Redesign AeroBridge from scratch, reset its architecture, or replace the Flight Deck Console identity | Contradicts `ideas.md`'s explicit reference-preservation instruction; discards a coherent, working visual and interaction system to solve problems that are concentrated, specific, and fixable in place | `ideas.md` direct quote; §C findings | No |
| RJ-02 | Merge Growth Record and Progress Tracking into one analytics screen | `ideas.md` names both as distinct loop stages operating at different evidence grains; no evidence trainees cannot locate what they need under the current split | §C.3, §H.6, CR-08 | Only if future task-based user evidence shows evidence-location failure |
| RJ-03 | Add a separate top-level Assessment route | Assessment is fully implemented and functions correctly as a Terminal mode; a route would fragment shared Terminal state for no evidenced benefit and would not fix the actual defect found (MC-004) | §H.3, CR-07 | No |
| RJ-04 | Add command autocomplete, or change command matching/scoring to solve a presentation problem | Conflicts with recall-based training and the explicit engine boundary (`ideas.md`; governing principle "never invent engine truth") | `ideas.md`; §B | Only with explicit pedagogical + engine-owner authority |
| RJ-05 | Activate the unused `MapView`/`Map.tsx` because a "View map" label exists | An unused, unimported component and a matching label are evidence of prior scaffolding, not of a proven learning need; activating it adds a new external dependency (a Google Maps proxy, per the component's own header) with no product requirement behind it | §G, MC-029, MC-R05, CR-09 | Only if a curriculum owner defines a genuinely map-dependent training task |
| RJ-06 | Add a mobile Coach FAB or bottom-sheet by default | The current in-flow, subordinate placement is confirmed correctly rendering in the mobile screenshot; no device or usability evidence shows it failing; converting it would add interaction surface to solve an unproven problem | §G.7, MC-R06, CR-06 | Yes — only after native-keyboard/device testing (MC-N02) produces evidence the current placement is missed or obstructive |
| RJ-07 | Migrate the Progress Tracking chart to a charting library (e.g., `recharts`, installed but unused) purely for implementation polish | The existing hand-built chart has a genuinely-wired, fully accessible `<details>`/table fallback — the strongest accessibility pattern in the codebase; no evidence the current pattern is functionally insufficient | §C.7, §G.9 | Only if a future, specifically evidenced interaction requirement exceeds what the current pattern supports |
| RJ-08 | Add badges, streaks, leaderboards, confetti, or other gamification/engagement-metric layers | Contradicts the product's professional aviation-training positioning; no evidence such elements would improve learning outcomes, and they would add visual and cognitive noise to a Terminal-first product | `ideas.md` (professional positioning intent); §C.1–C.2 | No |
| RJ-09 | Add a global, persistent "Next Action" dashboard widget | Duplicates the contextual next-action CTAs already present and working on every screen (confirmed via `setPracticeContext` handoffs); risks dashboardizing a product whose strength is per-screen, in-context guidance | §C.3, §H.8 | Only if evidence emerges that trainees cannot find their next action from within a screen |
| RJ-10 | Implement a partial, cosmetic Arabic/RTL experience (e.g., translate some strings without `dir="rtl"`, or flip layout without translating content) | A half-implementation would be worse than the current honest-once-fixed toggle — it would create new inconsistencies (mixed-direction text, untranslated fragments) without solving the underlying scope question | §G.14, MC-009, CR-10 | Full scope decision required first (§N, MC-N05); implement completely or not at all |
| RJ-11 | Treat the current five-item bottom rail as rendering 4 columns and "fix" it | Refuted by full CSS-cascade trace: three later rules, one with `!important`, already set 5 columns; the rendered output in every supplied screenshot is already correct | §J, CR-01, MC-R07 | No — this would be fixing a rule that isn't the one actually winning |
| RJ-12 | Treat the mobile Practice session-readout as simply hidden and needing to be un-hidden | Refuted by full cascade trace: a later, Practice-scoped rule already restores/positions it; the real open question is density/legibility at the narrowest widths, not presence | §J, CR-02, MC-R08 | Responsive validation at 320–360px (MC-N01/N02 family) — a legibility check, not a visibility fix |
| RJ-13 | Treat the terminal caret as ignoring `prefers-reduced-motion` and needing a component-specific fix | Refuted by direct source read: the caret is covered by the existing global `*`-selector reduced-motion catch-all | §J, CR-03, MC-R09 | No |
| RJ-14 | Add a two-step confirmation to "Finish Session" | No evidence of an accidental-completion problem in the supplied package; adds friction to a working flow without a demonstrated need | General evidence-discipline principle (§8 of the governing prompt: do not add product surface to compensate for an unverified concern) | No |
| RJ-15 | Treat every repeated claim across the five Stage 3 audits as independently proven | Violates the evidence hierarchy this audit is required to follow; the five audits substantially share the same source archive and the same seven screenshots, so agreement among them is a consensus signal, not independent confirmation | §B (evidence hierarchy); CR-01 through CR-03 as concrete demonstrations of repeated-but-wrong claims | No |


---

## L. Validation Plan

| Validation ID | Decision under test | Method | Measure | Success criteria | Result that would change the recommendation | Owner |
|---|---|---|---|---|---|---|
| V-01 | Blank input is a true no-op (MC-001) | Automated component test + manual Learn/Practice/Assessment runs | History length, score, hint count, `localStorage` writes, toast count, focus retention | All remain unchanged except the visible inline correction | A product decision explicitly defining blank submission as valid input (would conflict with the current command vocabulary and require separate engine authority) | UI/QA |
| V-02 | First-use Coach is neutral (MC-002) | Fresh session (cleared `localStorage`), screenshot comparison, one invalid command afterward | Rendered copy, color/state token, focus | Neutral pre-command state; real error only after a genuine failed command | Evidence that a preloaded diagnostic error is intentional (none currently exists) | UI/QA |
| V-03 | Every headline count reconciles with its source (MC-003) | Static sweep of every numeric literal in UI copy against its source array/rows | Numerator/denominator equality, illustrative labeling | No unlabeled, unreconciled count anywhere in the product | Content-owner authority for a larger real curriculum total, with an explicit "N available now" qualifier retained | UI + Product |
| V-04 | Assessment mode/hint disclosure is accurate (MC-004) | Controlled session: Learn → Practice → Assessment with deliberate prior activity | Disclosed count vs. actual `commandHistory`/`hintCount`; label accuracy | Trainee sees exactly what carried over before the first assessed command | Learning-design decision that modes should be fully isolated (would change the fix's final shape, not its urgency) | UI + Product |
| V-05 | Fresh-session metrics are honest (MC-005) | Load Practice with a cleared session | Accuracy/commands-mastered/task-progress/timer values pre-submission | No fabricated-looking number renders before real evidence exists | Product decision that a seeded/demo feel is intentional (then require explicit labeling instead of removal) | UI + Product |
| V-06 | Toast-only controls are individually resolved (MC-006) | Click-through inventory of all 12+ flagged controls | Real action performed, honest unavailable label, or removal | Every control does what it visibly claims | Product approval of a specific preview-only action with explicit copy | UI + Product |
| V-07 | Declared fonts actually render (MC-007) | Browser DevTools computed-style + network inspection on the deployed build | Computed `font-family`, loaded asset list | Space Grotesk / IBM Plex Mono / (Cairo once activated) resolve, not system fallback | Deployment constraint proven to prohibit self-hosting (then tokens should change to the real shipped stack instead) | Runtime |
| V-08 | Zoom is restored (MC-008) | Real iOS/Android device + browser zoom to 200–400% | Pinch/zoom behavior, content/functionality loss | Zoom works without breaking any core workflow | A specific, reproducible hard conflict discovered at extreme zoom (then fix the affected component, not reintroduce the restriction) | Runtime |
| V-09 | Contrast fixes hold in every state (MC-012) | Automated contrast check at final computed colors/sizes, all interaction states | Ratios for default/hover/active/focus/disabled | ≥4.5:1 for normal text in every state | None identified — this is closed-form math, not subject to reversal | UI/QA |
| V-10 | Mobile input reaches 16px (MC-011) | Inspect computed `font-size` on a real device, not DevTools emulation alone | `.terminal-input input` computed value at 320/360/390/430/739px | ≥16px at every width in Normal mode | None identified | Runtime |
| V-11 | Tab/toggle semantics are perceivable (MC-013) | NVDA/VoiceOver/TalkBack + keyboard-only pass | Announced role, selected state, keyboard operability | User can identify and operate every one of the five groups without a pointer | A control's real behavior turns out to differ from its assumed pattern (then use the matching ARIA pattern instead) | Runtime |
| V-12 | Overlay focus behavior is correct (MC-017) | Keyboard-only + screen-reader pass on Focus Mode, Reference drawer, mobile menu | Focus entry, containment, Escape, return | No focus escape while active; focus returns to trigger on exit | Focus Mode confirmed as a non-modal workspace rather than a dialog (then use workspace semantics, not a trap) | Runtime |
| V-13 | Mode/hint carry-over disclosure changes behavior appropriately (MC-004, deeper) | Product/learning-design review of whether modes should isolate state | — | A documented decision exists either way | — | Product |
| V-14 | Tablet (740–1099px) composition is coherent (MC-N01) | Render at 768/834/1024px, task walkthrough | Navigation identity, content-grid columns, Terminal/Coach ratio, `.is-primary` scope | No mobile-chrome/desktop-density confusion; Terminal remains primary | Systematic failure at this range (then refine breakpoint composition, not add a third nav architecture) | Runtime |
| V-15 | Native keyboard behavior is sound (MC-N02) | Real iOS Safari + Android Chrome at 320/360/390/430px | Input reachability, viewport jump, output occlusion, Execute reachability | No clipping/jump/occlusion; latest result stays understandable | Confirmed failure (then evaluate a tested drawer/sheet pattern, still not by default per RJ-06) | Runtime |
| V-16 | Hamburger drawer is or isn't redundant with bottom/side nav (MC-N03) | Direct inspection of drawer contents at implementation time | Content overlap with existing nav | Distinct purpose confirmed, or redundancy confirmed | Confirmed redundant (then remove or repurpose, e.g. settings/help, rather than leaving two identical entry points) | UI/QA |
| V-17 | Long scenario titles don't collide with the Practice task-strip badge | Render with the longest actual title in the `scenarios` dataset at 320/360/390/430px | Wrapping/truncation/CTA collision | Title remains legible; context/ID preserved | Collision confirmed (then adjust title presentation only, not the context-passing contract) | UI/QA |
| V-18 | Growth/Tracking cross-screen closure remains intact after all other fixes | Complete an assessment → check Growth → check Tracking → return to Practice | Record identity, evidence source, CTA context | Same record/context remains coherent end-to-end | Any mismatch (then fix data/context ownership, not visual presentation) | UI/QA |
| V-19 | Arabic/RTL release scope decision | Product/content decision + a bounded prototype test if scope is approved | `lang`/`dir`, font switch, bidi integrity for mixed LTR command strings, layout mirroring | Either a genuine bounded RTL implementation passes, or AR is honestly labeled roadmap/unavailable | Product funds and scopes full translation/RTL work | Product |
| V-20 | Reduced motion remains intact after all other changes | Toggle OS-level reduced-motion on/off post-implementation | Caret, counting animations, panel transitions | No training-relevant information depends on motion; the existing catch-all and hook-level checks still function | Only fix an offending *new* animation if one is introduced; do not touch the existing mechanism | UI/QA |
| V-21 | ErrorBoundary/Toaster mount resolves cleanly (MC-028) | Forced runtime error + full toast-trigger sweep post-mount | Fallback UI renders; all 19 toast call sites visibly render | Styled fallback appears, no raw stack shown; every toast is visible | None identified | Runtime |
| V-22 | `/manus-storage/...` assets and the analytics script behave predictably outside the current host (MC-030, MC-031) | Fresh clone/build in a non-Manus-hosted environment | Image resolution, analytics script load | Either assets/script resolve, or the gap is explicitly documented for handoff | External-path replacement required before any standalone handoff | Runtime |


---

## M. Implementation Handoff

### Ordered execution plan

**1. P0 trust, safety, and evidence-integrity fixes** (§F.1 — MC-001 through MC-012)
Freeze the contract first: record the current AN→SS→FQD→FXP baseline responses, the current scoring output for a known command sequence, and the current `localStorage` schema before touching anything, so every subsequent step has a known-good comparison point. Then, in any order (all are independent, none depends on another): guard blank/whitespace submission (MC-001); neutralize the first-use Coach state (MC-002); reconcile or label every headline count (MC-003); disclose Assessment mode/hint carry-over and fix the static label (MC-004); neutralize fresh-session metrics (MC-005); fix the Coach's fake "Open reference" confirmation and relabel/implement Backup (MC-006, highest-stakes instances); provision the declared fonts (MC-007); remove the viewport zoom restriction (MC-008); interim-disable the language toggle (MC-009); scope readiness language (MC-010); delete the 15px mobile-input override (MC-011); fix primary-button and `--text-faint` contrast (MC-012). Sequence MC-007 (fonts) early within this tier regardless of exact order, since it changes rendered text metrics that affect every subsequent visual check.

**2. P1 accessibility and core interaction-state fixes** (§F.2 — MC-013 through MC-019, MC-006 remaining instances)
Build the shared tab/toggle semantics pattern once (MC-013, folding in MC-014); add progressbar semantics (MC-015); add landmarks/skip-link/`aria-current` (MC-016); add overlay focus-trap/Escape/return-focus to Focus Mode, Reference drawer, and mobile menu (MC-017); fix skill-trend icon/color semantics (MC-018); bring skill-hover-preview content to mobile (MC-019); finish triaging the remaining toast-only controls (MC-006).

**3. P1 responsive and Terminal-hierarchy fixes** (§F.2 remainder — MC-020 through MC-024, MC-028)
Consolidate the `--ab-*` and base token layers (MC-020); build the honest Customer Service empty state (MC-021); fix Scenarios' Filters/Sort (MC-022); reconcile mobile-nav breadcrumb numbering (MC-023); reduce the fixed terminal-gap spacer (MC-024); mount a styled ErrorBoundary and a `<Toaster/>` (MC-028).

**4. P2 design-system and resilience cleanup** (§F.3 — MC-025 through MC-033)
Schedule at team discretion; none of these block trust, core usability, the accessibility baseline, or evidence integrity.

**5. Final regression and accessibility validation** (§I, §L)
Run the full validation plan (§L) before declaring this revision complete: native-keyboard testing at 320–430px, tablet composition at 768/834/1024px, desktop capture at 1280/1440px, a real screen-reader pass (NVDA/VoiceOver/TalkBack), and a final contrast re-check against the actually-shipped hex values, not the pre-fix ones used for the initial computation in this report.

### Regression gates

Every change in every tier above must preserve, unless a specific finding above explicitly authorizes a change to it:

- **Valid commands:** AN/SS/FQD/FXP produce identical response text, `ok`/`errorKind` values, and Coach copy to the pre-revision baseline.
- **Scoring:** `assessmentScore()`'s formula (accuracy 50% + sequencing 35% + hint-score 15%) and its output for a fixed input sequence are unchanged.
- **Local persistence:** `localStorage` record shape, the 8-record cap, and the read/write contract between Practice, Growth, and Tracking are unchanged.
- **Route map:** All five routes (`/`, `/practice`, `/scenarios`, `/growth`, `/tracking`) continue resolving correctly via `pathToView`/`window.history.pushState`.
- **Context handoffs:** `setPracticeContext` calls from Progression, Scenarios, Growth, and Tracking continue landing on the correct Practice context string.
- **Chart/table equivalence:** The Progress Tracking `<details>`/table fallback continues rendering the identical values as the visual bars for every metric (`overall`/`accuracy`/`sequencing`).
- **Reduced motion:** The global catch-all, the component-scoped refinements, and the `matchMedia` checks inside `useAnimatedNumber`/`useAnimatedBar` all remain intact and untouched by any P1/P2 visual change.

Any change that breaks one of these gates is a regression, even if the screen it appears on looks improved in isolation — re-verify against this list before merging any individual fix from §F.

---

## N. Open Questions, Assumptions, and Evidence Gaps

### Product-owner decisions

| ID | Question | Why it matters | Decisions affected |
|---|---|---|---|
| OQ-01 | Are `8` stages, `40` scenarios, and `12` log entries real planned future totals, or should displayed totals simply match what's genuinely built (`6`/`5`/`3`)? | Determines whether MC-003's fix is a pure derivation correction or should retain a larger number with an honest "N available now" qualifier | MC-003, CR-12 |
| OQ-02 | Should "Backup" become a real local export (e.g., a JSON download of the `localStorage` evidence record), or be permanently relabeled as unavailable? | Substantially changes MC-006's cost for this one control — relabeling is trivial, real export is a small but real feature | MC-006 |
| OQ-03 | Should Arabic/RTL be built for a near-term release, or does the product remain EN-only for the foreseeable future? | Determines whether MC-009 is the whole fix or only an interim step before a genuine architecture/content/translation effort | MC-009, CR-10, MC-N05 |
| OQ-04 | Is a future interactive map a planned feature, explaining why `Map.tsx` and the "View map" stub exist, or should the remaining dead-code trace be removed? | Determines MC-029's disposition | MC-029, CR-09 |
| OQ-05 | Is the current level of pre-seeded "realism" (the 4:32 session timer, for instance) an intentional part of making the local simulation feel authentic, or should such elements start from a genuine zero/empty state? | Low-stakes but affects whether the timer half of MC-005 needs any effort at all | MC-005 |

### Content/curriculum decisions

| ID | Question | Why it matters | Decisions affected |
|---|---|---|---|
| OQ-06 | What is the authoritative definition (if any) behind "Saudi readiness" and similar readiness-style scoring language? | Prevents the product from implying a competency judgment it cannot actually support | MC-010 |
| OQ-07 | What real curriculum content exists (or is planned) for the Customer Service track? | Determines the permanent fix for MC-021, beyond the interim honest empty state | MC-021 |

### Engine/state decisions

| ID | Question | Why it matters | Decisions affected |
|---|---|---|---|
| OQ-08 | Should Learn/Practice/Assessment modes be fully isolated (history/hints reset on switch) or remain continuous with honest disclosure of carried-over activity? | The interim disclosure fix in MC-004 is safe either way, but the long-term intended behavior needs a decision from whoever owns the assessment model | MC-004 |
| OQ-09 | Should Practice/Learn modes enforce command sequence order the way Assessment does, or is out-of-order exploration intentionally allowed in those modes? | Determines whether the current Assessment-only sequence check is a deliberate pedagogical choice or an inconsistency | MC-N04 |
| OQ-10 | Does opening the Reference drawer correctly count as a hint in every mode it's reachable from, once MC-006 makes both Reference entry points consistent? | Affects displayed hint-discipline accuracy | MC-004, MC-006 |

### Runtime/device validation

All items in §I.1 (tablet 740–1099px, desktop ≥1100px, native keyboard behavior) and §I.2's screen-reader validation row remain open pending the tests specified in §L. None of these gate the P0/P1 fixes in §F, all of which rest on source or independently-computed evidence; they gate only the items explicitly marked NEEDS VALIDATION throughout this report.

### Deployment/configuration validation

| ID | Question | Why it matters |
|---|---|---|
| OQ-11 | Do the `/manus-storage/...` hosted assets (three atmospheric images plus the brand-mark logo) and the Umami analytics script actually resolve outside the current live preview host? | Affects whether a standalone/portable build of this codebase is silently broken (missing images, including the logo) outside the current hosting environment |
| OQ-12 | Is the current 740–1099px behavior (mobile-style nav persisting alongside desktop-density content grids) a deliberate "large mobile" design choice, or an unreviewed gap? | Determines whether §I.1's tablet-range item requires a fix or only documentation confirming intent |

### Audit disagreements that remain unresolved

None. Every material conflict identified across the five Stage 3 audits was traced to a decision in §J — including the one (CR-12, the numeric-values question) that could not be resolved from UI evidence alone and is correctly logged as DEFER FOR VALIDATION rather than forced to a false resolution.

### Assumptions used in this synthesis, stated explicitly rather than hidden inside a recommendation

- **A1:** The current five-screen/workspace model in `Home.tsx` is the intended product information architecture, because it is explicitly supported by `ideas.md` and matches the actual navigation structure.
- **A2:** The local assessment model is a prototype simulation, not an authoritative airline-qualification engine, because `ideas.md` explicitly states the preview is presentation-first and prohibits real-metric/backend expansion.
- **A3:** Where the source does not expose a real engine state (processing, interruption), the UI should not invent one merely to make the state table feel complete (§I.3, CR-11).
- **A4:** "Illustrative/local" labeling is acceptable product language, because `ideas.md` explicitly requires mock/illustrative states to remain clearly disclosed as local and non-production rather than requiring their removal.
- **A5:** The absence of any desktop/tablet screenshot in the seven supplied images means no such capture exists, not merely that it was omitted from this handoff. If additional screenshots exist but were not shared, several NEEDS VALIDATION items in §I could be resolved immediately rather than requiring new capture work — this should be confirmed before commissioning new testing.

---

## O. Final Recommendation

### Implement now

The complete P0 set (§F.1): reject blank/whitespace command submission; neutralize the first-use Coach state; reconcile or honestly label every headline count; disclose Assessment mode/hint carry-over and fix the static "No hints" label; neutralize fresh-session Practice-footer metrics and the seeded timer; fix the Coach's fake "Open reference" confirmation and resolve Backup's honesty; provision the three declared fonts; remove the viewport zoom restriction; interim-disable the language toggle; scope readiness language to what a local heuristic supports; delete the mobile-input 15px cascade regression; fix primary-button and `--text-faint` contrast. Followed by the full P1 set (§F.2): the systemic tab/toggle/progress/landmark/overlay accessibility pass; the remaining toast-only-control triage; token consolidation; the mobile skill-preview gap; the Customer-Service-track honest empty state; Scenarios' Filters/Sort; nav-order/breadcrumb reconciliation; the terminal dead-space reduction; and mounting a styled ErrorBoundary and Toaster. P2 items (§F.3) may follow at the team's discretion. Every item in both tiers is UI-only, copy-only, or a contained state-management change — none requires touching the command engine, the scoring formula, or the information architecture.

### Preserve

The Flight Deck Console visual identity in its entirety (§C.1); the Terminal's architectural centrality and the Learn/Practice/Assessment structure (§C.2, C.4); the five-screen loop and its genuine, source-confirmed cross-screen `setPracticeContext` handoffs (§C.3, §H.8); Focus Mode's core scroll-lock mechanism (§C.5); the `prefers-reduced-motion` implementation, confirmed more thorough than a surface reading would suggest (§C.6); the Progress Tracking chart's accessible table alternative (§C.7); the deliberate mobile input engineering — sticky positioning, safe-area handling, 360px header restructuring (§C.8); the contextual copy voice (§C.9); and command-history keyboard recall (§C.10). All eleven items are detailed with explicit acceptable-modification boundaries in §C — implementation should treat that section as binding, not aspirational.

### Defer

Full Arabic/RTL implementation (MC-009's long-term half), pending the product scope decision in OQ-03/MC-N05. Whether `8`/`40`/`12` should become real, larger curriculum totals or simply be corrected to match current content, pending OQ-01. Whether `Map.tsx` is finished, retained for a future roadmap item, or removed, pending OQ-04. Whether "Backup" becomes a real local export or a permanent relabel, pending OQ-02. Most P2/COULD IMPROVE items (§F.3) may be scheduled at team discretion without blocking this revision's completion. Tablet (740–1099px) and native-keyboard validation (§I.1, §L) — not because they are low priority, but because they require runtime evidence this audit does not have, not further design analysis.

### Reject

All entries in §K in full: redesign or architecture reset; merging Growth Record and Progress Tracking; a separate Assessment route; command autocomplete or scoring changes to solve a presentation problem; speculative `MapView` activation; a default mobile Coach FAB/bottom-sheet absent device evidence; a charting-library migration; gamification/badges/streaks; a global persistent "Next Action" widget; a partial/cosmetic Arabic implementation; and — specifically because they are contradicted by direct cascade tracing, not because they are low-value — treating the bottom-nav column count, the mobile session-readout visibility, or the terminal caret's reduced-motion coverage as current defects requiring a fix.

### Final decision

**AeroBridge should be preserved and refined, not revised more substantially and not redesigned.** The evidence in this pass — direct source reading, independently recomputed contrast math, a fully traced CSS cascade, and cross-checking against all seven supplied screenshots — supports a foundation that is genuinely sound: a coherent, distinctive visual identity; a Terminal that is a real workstation, not a themed shell; and a five-screen loop wired through real state and real persistence, not implied by navigation alone. Set against that foundation, every defect this report classifies MUST FIX or SHOULD FIX is narrow, specific, and independently confirmed — a fabricated error message, a silently-coerced blank input, numbers that don't add up, controls that lie about what they did, fonts that were never wired up, and one CSS rule quietly undoing another. None of these require touching the command engine, the scoring model, the route structure, or the visual system's identity to fix. That is precisely the profile of a targeted hardening pass, not a revision or a redesign: the problems are real and some are serious, but they are trust and integrity problems sitting on top of a sound foundation, not evidence the foundation itself is wrong.

