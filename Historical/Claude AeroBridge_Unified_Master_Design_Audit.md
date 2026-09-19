# AEROBRIDGE — UNIFIED MASTER DESIGN AUDIT

**DESIGN STATUS: NEEDS TARGETED REVISION**

*A defensible, traceable, evidence-weighted, conflict-resolved synthesis of nine independent AI audits (Claude, ChatGPT, Grok, Gemini, Kimi, Manus, DeepSeek, v0.dev, Qwen), direct inspection of the full prototype source (`App.tsx`, `Home.tsx` — 363 lines, `index.css` — 408 lines, `Map.tsx`, `const.ts`, `index.ts`, `ideas.md`), and seven rendered mobile screenshots (Progression, Practice/Terminal, Scenarios, Growth Record ×3 tabs, Progress Tracking). Every canonical finding below was checked against the actual source during this synthesis pass — not merely inherited from the nine reports.*

---

## 1. EXECUTIVE VERDICT

AeroBridge is a genuinely well-built, high-fidelity prototype — not a template with aviation words pasted on it. All nine independent audits converge on this without exception: a distinctive, coherent dark "Flight Deck Console" identity; a real design-token vocabulary; a five-screen loop (Progression → Practice → Assessment → Growth → Tracking → Scenarios) that is *actually wired end-to-end* with genuine `localStorage`-backed evidence flow, not a mockup pretending to connect; deliberate, evidenced mobile engineering (16px input font to defeat iOS auto-zoom, `position: sticky` command input above the safe-area inset, purpose-built two-row terminal-header restructuring at 360px with an explanatory code comment); and one of the more thorough `prefers-reduced-motion` implementations reviewed by several of the nine auditors, confirmed here by direct inspection (a global `!important` catch-all plus 13 separate component-scoped refinements, including one that explicitly names the terminal caret).

**What is strong.** The Terminal is genuinely built as the product's primary workstation, not a card among cards: it is first in document order, full-width, the only screen with a dedicated later-pass token layer (the "AeroBridge Elevation Directive," confirmed in source), the only nav item deliberately center-emphasized on mobile with a code comment stating that exact intent, and the only screen with a purpose-built Focus Mode. The Progress Tracking chart has a genuine `role="table"` accessible alternative wired to the same data the bars render — the single strongest accessibility artifact in the codebase and the reference pattern for anything added later. Cross-screen context handoff (`setPracticeContext`) is real, not decorative: every "next action" button that promises to open Practice actually does, with the correct task string, and finishing an Assessment writes a real record that Growth and Tracking immediately reflect.

**What is weak, and why it matters more than its visual polish suggests.** The gap between "looks finished" and "is finished underneath" is this prototype's one real, repeated failure pattern, and it shows up at exactly the moments a training product can least afford it. On the single most important screen in the product, before a trainee has typed anything, the Coach panel renders a fabricated, red-styled `FORMAT ERROR · CHECK ENTRY` beneath a correctly neutral `AWAITING COMMAND` label — confirmed here directly in source (`Home.tsx:311`, the `??` fallback) and visible pixel-for-pixel in the supplied screenshot of first-load Practice. Submitting an empty command silently logs a real `FQD` entry into assessment history — also confirmed directly in source (`Home.tsx:275`) and independently caught by five of the nine audits reading the same line. A recurring family of headline numbers do not correspond to the data beneath them: "3 / 8 stages" against a six-item `levels` array, "23 / 40" scenarios completed against five defined scenarios (one of which cites a "Needs improvement: Exchanges & Refunds" category that does not exist anywhere in the data), "LOG 04 / 12" against three rendered history rows — all confirmed directly in source and, in three cases, visible in the supplied screenshots themselves. None of this is a design problem in the visual sense; it is a truthfulness problem, and for a product whose entire value proposition is "evidence you can trust," it is the fastest way to undermine that proposition.

**What must change first.** Five fixes carry disproportionate weight relative to their cost: the fabricated Coach error (AB-F001), the empty-submit-to-FQD behavior (AB-F002), the missing tab/toggle ARIA semantics repeated across five separate control groups (AB-F007), the two parallel color-token systems with different hex values for the same semantic role (AB-F008), and the systemic illustrative-numbers-presented-as-real pattern (AB-F010). None of these require touching command logic, the assessment-scoring formula, or the data model. All five are copy, conditional-render, or CSS-value changes.

**What must not change.** The Flight Deck Console visual identity, the deep-navy foundation, the terminal-first architecture, the Learn/Practice/Assessment structure, Focus Mode, the Progress Tracking data-table pattern, and the real cross-screen evidence loop are the product's strongest, most defensible assets. Nothing in this audit recommends touching them, and several specific "improvement" suggestions surfaced across the nine source audits are explicitly rejected below (§15) precisely because they would compromise one of these strengths for a marginal or unproven gain.

**Overall design direction.** This is a **focused revision pass**, not a redesign and not a case requiring foundational architecture clarification first. Eight of the nine source audits reach this same verdict independently, using their own words, before this synthesis combined them — see §3 for the one meaningful nuance in that consensus (Manus's more architecture-cautious framing) and why it does not change the recommendation. The one deliberate exception is the EN/AR language toggle (AB-F003): not because fixing it is technically hard, but because building real bidirectional support without first deciding its scope risks reproducing the exact "looks done, isn't" pattern this audit spends most of its length correcting elsewhere. That one decision should be made deliberately, before implementation time is spent on it; everything else in this report can proceed in parallel without waiting on it.

---

## 2. SOURCE COVERAGE & EVIDENCE OVERVIEW

### 2.1 Source inventory

| Source ID | Type | Contents | What it verifies | What it cannot verify |
|---|---|---|---|---|
| **S-Claude** | Audit | Full source read (`Home.tsx`, `index.css`, `index.html`, `App.tsx`, `main.tsx`, `const.ts`, `useMobile.tsx`, `ThemeContext.tsx`, `ErrorBoundary.tsx`, `NotFound.tsx`, `Map.tsx`, `package.json`) + 6 screenshots. Computed 17 WCAG contrast ratios directly. | Exact line numbers, hex values, contrast ratios, font-loading chain, dead-code inventory | Live keyboard/screen-reader behavior, 320px/430px live render |
| **S-ChatGPT** | Audit | Full source read including `index.html`, `NotFound.tsx`, `ErrorBoundary.tsx`, `server/index.ts`, `tsconfig.json`. Attempted live runtime (blocked: no network/registry access). | Line-numbered claims across nearly every file; explicitly identified the archive's external-asset dependency (`/manus-storage/...`) | Live desktop render, precise 320px behavior |
| **S-Grok** | Audit | Full source read (`Home.tsx`, `index.css`, `ErrorBoundary.tsx`, `ThemeContext.tsx`, `useMobile.tsx`, `package.json`, `vite.config.ts`) + screenshots as corroboration only. | Structural/state-machine claims, breakpoint inventory | Did not have `index.html`; live behavior |
| **S-Gemini** | Audit | Component/state-logic read. **Did not have `index.css`** — visual/contrast claims are class-name inference, not measurement. | Conditional-rendering and state-transition logic | Any color, spacing, or contrast claim; explicitly self-flagged |
| **S-Kimi** | Audit | Full source read with extensive exact CSS selector and line citation (`Home.tsx`, `App.tsx`, `const.ts`, `index.css`, `Map.tsx`, `index.ts`, `ideas.md`). | Very granular spacing/radius/type-scale inventory; specific selector-level claims | Live device behavior, screen-reader output |
| **S-Manus** | Audit | **Only source to attempt and confirm a live local run** (`pnpm run build`, dev server, manual command submission at `/practice`). Full source read. | Actual build warnings (undefined analytics vars, runtime-only asset paths), one live command-submission trace | Full live click-through of every state |
| **S-DeepSeek** | Audit | Self-described consolidation of two internal passes; DeepSeek-2 component had `index.css`, DeepSeek-1 component did not. Less line-level citation than the other eight; more interpretive/directional language. | General direction and priority framing | Specific technical claims — lower evidentiary weight throughout this synthesis for that reason |
| **S-v0dev** | Audit | Full source read with **exact line-number citation for both `Home.tsx` and `index.css`** on nearly every claim (e.g., `L275`, CSS `L242`). Did not have `index.html`. | Highly specific, falsifiable claims — several of which this synthesis pass checked against source and found **incomplete** (did not trace the full CSS cascade; see §15) | Font-loading (flagged, correctly, as unverified) |
| **S-Qwen** | Audit | Component/state-logic read. **Did not have `index.css`** (self-flagged explicitly) — relied on class-name inventory + 5 screenshots for visual claims. | State-machine and data-flow claims (`AB-05` empty-submit, `AB-16` dead enum value, `AB-18` image fallback — all independently confirmed against source in this pass) | Any measured color/contrast/spacing claim |
| **S-Src** | Direct artifact | This synthesis pass's own read of `App.tsx`, `Home.tsx` (full, 363 lines), `index.css` (full, 408 lines, plus targeted `grep` verification of ~15 specific disputed claims), `Map.tsx`, `const.ts`, `index.ts`, `ideas.md` | Used as the adjudicating Tier-1 evidence for every conflict in §15 | `client/index.html` was **not** in the supplied file set for this pass — font-loading (AB-F004) and viewport pinch-zoom (AB-F011) claims rely on S-Claude/S-ChatGPT's independent reads of that file, not a re-verification here |
| **S-Shots** | Screenshots | 7 rendered mobile captures (~360–424px, Android Chrome): Progression, Practice (Coach panel visible), Scenarios (list + SC-014 detail), Growth Record ×3 (Record/History/Reports tabs), Progress Tracking | Confirmed pixel-for-pixel: PRA-01 fake error, PRG-01 "3/8", SCN-01 "23/40" + "Exchanges & Refunds", GRW-03 "LOG 04/12", AB-F055 route-line truncation | Desktop/tablet render, any interaction state not captured |

### 2.2 Coverage limitations, stated plainly

No `client/index.html` was available for direct re-verification in this synthesis pass. Two findings — font loading (AB-F004) and disabled pinch-zoom (AB-F011) — rest on S-Claude's and S-ChatGPT's independent reads of that file rather than this pass's own confirmation. Both are reported at **high but not directly-verified-here confidence**, and both are flagged `TEST BEFORE ACCEPTING` accordingly, not `ACCEPT`. No desktop or tablet screenshots were supplied; every desktop/tablet-width claim in this report is source-derived (CSS breakpoint reading), not visually confirmed, and is marked accordingly. No live browser session, screen reader, or physical device was available to any of the nine source audits or this synthesis pass — every claim of that kind is explicitly marked `TEST BEFORE ACCEPTING` in §7 rather than asserted as fact.

### 2.3 Evidence strengths

This synthesis pass independently re-verified — by direct `grep`/read of the actual source, not by trusting audit citations — the following disputed or high-stakes claims, each now at **E4 (directly verified)**: the empty-submit-to-FQD behavior; the fabricated default Coach error; the mode-switch state-retention behavior (`hintCount`/`commandHistory` survive a Learn→Assessment switch); the "3/8", "23/40 + Exchanges & Refunds", and "LOG 04/12" illustrative-number mismatches; the complete absence of `role="tab"`/`aria-selected`/`aria-pressed`/`aria-expanded` anywhere in the 363-line file (zero occurrences, confirmed by direct count); the exact `aria-label`/`aria-hidden`/`aria-live` counts (17/4/2, matching S-Claude's independent count exactly); the absence of a `<main>` landmark; the presence of `aria-current` on `BottomNav` and its absence on the desktop `SideNav`; the unused status of `Map.tsx`/`MapView` (confirmed via import trace — it is imported nowhere); the `.is-secondary-view{display:none!important}` rule; the `--ab-*` parallel token layer's exact hex values; the icon-button size cascade (38px→35px→33px); the `--text-faint:#5d6a85` token value; and — critically, resolving a direct three-way conflict among the source audits — the actual, final-cascade behavior of `.bottom-nav`'s column count and `.terminal-session-readout`'s mobile visibility (§15.1, §15.2).

---

## 3. AUDIT CONSENSUS OVERVIEW

**Strongest consensus (9/9, independent framing, not shared phrasing).** All nine audits, working independently and using their own vocabulary, concluded: (a) the visual identity is distinctive and should be preserved essentially as-is; (b) the product needs a **focused revision pass, not a redesign**; (c) the Terminal is correctly the product's center of gravity; (d) command/scoring/engine logic must not be touched by this UI work; (e) the EN/AR toggle is currently non-functional and Arabic/RTL support is a genuine, unimplemented gap relative to the stated Saudi-market mission. Per this audit's own evidence-independence rule, nine audits looking at the same screenshot of the language toggle is **not** nine independent proofs — but five of the nine reached the language-toggle finding primarily through independent source-code reading (the `toast.success` handler with no `dir` change, no i18n library reference), which does constitute real, non-duplicative corroboration (E3).

**Conditional consensus.** "The prototype's illustrative numbers should be labeled or reconciled" is universal in spirit but the nine audits disagree on urgency: S-Manus and S-ChatGPT rate this **P0** (framing it as an evidence-integrity/trust issue central to the product's mission); S-Claude, S-v0dev, S-Qwen rate it **P1/P2** (framing it as a content-authoring gap more than a UI defect, since the fix requires either new curriculum content or an honest "N of M available now" relabel — a product decision, not a pure UI one). This synthesis resolves the conflict in §15.4: **P1**, and explains why.

**Important minority insights** (each correct, each caught by only one or two of the nine, each retained in full below rather than dropped for being uncommon): S-Gemini alone flagged that `AnimatedBar` renders as a bare `<i>` element with only `aria-label`, lacking `role="progressbar"`/`aria-valuenow` (AB-F024) — confirmed directly against source in this pass. S-Qwen alone flagged the dead `"hint-dependency"` `ErrorKind` enum value — declared, shown in the Assessment debrief legend, never actually producible by the command-matching logic (AB-F022) — confirmed directly. S-Qwen and S-v0dev, independently, both flagged `Map.tsx`/`MapView` as completely unused dead code (AB-F019) — a finding **missed by six of the other seven audits**, including the otherwise-exhaustive S-Claude, despite S-Claude listing `Map.tsx` among the files it read. S-v0dev alone produced exact icon-button pixel measurements across three breakpoints (38→35→33px) that this pass confirmed letter-for-letter against source. S-Manus alone actually ran `pnpm run build` and surfaced two findings no static read could produce: undefined analytics-placeholder variables and runtime-only `/manus-storage/...` asset paths that make the archive not fully self-contained (AB-F021, independently cross-confirmed by S-ChatGPT's separate line-citation of the same three CSS/TSX locations).

**Strongest disagreements, and how each is resolved.** Three direct, falsifiable factual conflicts existed among the nine audits concerning the *same* lines of CSS. All three are resolved in §15 by tracing the full cascade against actual source, not by vote: (1) S-v0dev claimed `.bottom-nav` renders 5 items into a 4-column grid with dead `.is-primary` styling — **false**; two later, higher-specificity rules (one with `!important`) override the 4-column base rule, and `.is-primary` is fully styled. (2) S-v0dev and S-Kimi both claimed `.terminal-session-readout` is `display:none` on mobile, hiding all session state — **true only of an earlier, superseded rule**; a later, unconditional, higher-specificity `.page-practice .terminal-session-readout{display:flex}` rule restores and continues to style it at every subsequent breakpoint. (3) S-Manus and S-Kimi both claimed the terminal caret's blink animation does not respect `prefers-reduced-motion` — **false**; a rule at `index.css:217` explicitly names `.terminal-caret` inside a `prefers-reduced-motion` block, in addition to the global catch-all. In all three cases the source audits found a *real* rule but did not trace the cascade to its actual endpoint — a useful, generalizable lesson recorded as its own finding (AB-F026) rather than discarded.

**Major uncertainty areas**, honestly marked rather than guessed at: whether the three declared display fonts (Space Grotesk / Cairo / IBM Plex Mono) actually load (S-Claude's direct read of `index.html` says no — the Google Fonts link is commented out with an explicit "BLOCK TO BE DELETED" marker — but this pass could not independently re-verify `index.html`, which was not in the supplied file set); whether pinch-zoom is genuinely disabled (same limitation); live keyboard-navigation order and screen-reader announcement behavior across the whole app (no audit had a live browser session); actual rendered behavior at exactly 320px and 430px (no audit had device access; the CSS at 360px is confirmed, extending it downward is not); and whether the 740–1099px tablet range's mix of multi-column content grids with mobile-style bottom-nav chrome reads as intentional or awkward in practice (structurally confirmed via the CSS breakpoint mismatch itself — content breaks at 740px, navigation breaks at 1100px — but the felt experience needs a live pass).

---

## 4. CRITICAL DECISIONS

These are the handful of decisions that materially shape everything else in this report. Full evidence, source traceability, and acceptance criteria for each live under its Canonical Finding ID in §5.

1. **Fix the Coach panel's default (no-command) state before anything else touches Practice.** (AB-F001, P0) A fabricated, red-styled error is the first thing a trainee sees on the product's central screen. This is a one-conditional, zero-risk fix and should ship alone, ahead of any other Terminal work, so its removal can be screenshot-verified in isolation.
2. **Fix the empty-command-submits-FQD behavior before any further Terminal polish.** (AB-F002, P0) This is the one finding in this entire report that touches actual command-submission behavior rather than pure presentation, and it is flagged by five of the nine source audits independently. It must ship with an explicit before/after regression check confirming non-empty submissions are byte-for-byte unchanged.
3. **Treat the EN/AR toggle as a scope decision, not a build task, this phase.** (AB-F003, P0-as-decision) Do not build partial RTL. Do not leave the toggle implying a working switch either. The UI-safe action available immediately, with zero content/architecture dependency, is to stop presenting it as functional (see §5, AB-F003 for the two concrete options) until product ownership defines what "Arabic support" means for this release.
4. **Adopt one shared tab/toggle semantics pattern once, apply it to all five control groups, and consolidate the two color-token layers before writing it.** (AB-F007 + AB-F008, P1) These two findings are sequenced together deliberately: the ARIA work will touch styling in both the base token layer and the `.page-practice`-scoped layer, and should be written against one consolidated system, not two, or the fix itself becomes a third layer of drift.
5. **Establish one rule for illustrative numbers and apply it everywhere at once, not screen by screen.** (AB-F010, P1) Every summary count/fraction should be derived from the array it summarizes, or explicitly labeled as showing less than the eventual total. This is one design-system decision applied five times, not five separate screen fixes.
6. **Do not let any of the above become an excuse to touch command matching, scoring weights, `localStorage` schema, or routing.** Every one of the 60 canonical findings in this report is classified `UI-only` or `Content-only` except where explicitly marked otherwise in §13 (Deferred Dependencies) — and even AB-F002, the one finding closest to "logic," has a UI-only-safe interim mitigation specified alongside its Engine-dependent root fix.

---

## 5. CANONICAL FINDINGS

*Legend — Evidence Independence: E0 single claim · E1 repeated but same underlying screenshot/source · E2 corroborated by distinct analyses · E3 independently corroborated by separately-sourced audits · E4 directly verified against source/runtime in this pass. Evidence Quality: Very Strong / Strong / Good / Moderate / Weak. Verdict: ACCEPT / ACCEPT WITH MODIFICATION / REJECT / DEFER / TEST BEFORE ACCEPTING.*

### 5.1 Terminal / Practice — the highest-priority screen

---

**AB-F001 — Coach panel renders a fabricated error before any command exists**
Type: Behavioral · Priority: **P0** · Verdict: **ACCEPT**
Sources: S-Claude(PRA-01), S-Qwen(AB-06), S-Kimi, S-ChatGPT(interaction issues §5.2), S-v0dev(via F-16 stub inventory), S-Manus(implied AB-04), S-Grok(T-02 area) — 7/9 explicit, 2/9 adjacent · Artifacts: `Home.tsx:311` (this pass's line count), S-Shots Image 5 (visible pixel-for-pixel) · Evidence: Source + Screenshot, **E4 directly verified**, Very Strong
Observation: When `latestEntry` is `undefined` (true on every fresh entry into Practice), the Coach block's eyebrow correctly reads `SYSTEM RESPONSE / AWAITING COMMAND`, but the `<code>` line beneath it resolves via `latestEntry?.response ?? "FORMAT ERROR · CHECK ENTRY"` to the literal fallback string, and the body paragraph shows a specific fabricated correction — `"The availability entry needs the airline prefix before the flight number"` — describing a mistake that has not occurred. The `className={latestEntry?.ok ? "coach-code--success" : ""}` guard means the code line never receives success styling in this state, so it inherits `.coach-block code`'s base color, which is `var(--red)`.
Impact: This is the first content a trainee sees on the product's central screen, directly contradicting the stated intended feeling (professionalism → focus → confidence → precision) at the exact moment first impressions form.
Risk: Trust/first-impression. Not an evidence-integrity risk (no score or record is affected) — purely a presentation defect, which is precisely why it is safe to fix immediately.
Dependency: **UI/Content-only.** Zero state-model, command-logic, or scoring risk.
Decision: Replace the fallback with neutral placeholder copy (the existing default coaching body — "Think in workflow steps..." — reused, or an explicit "Submit a command to see coaching feedback here") in a neutral (non-red) treatment. Never render error styling before a real error exists.
Action: Change the two literal fallback strings and the conditional class so no error-colored content can render when `latestEntry` is `undefined`.
Validation: On first entry into Practice, before any command is submitted, nothing in the Coach panel is styled or worded as an error. Screenshot-diff against the current default state.

---

**AB-F002 — Empty command submission silently logs a real "FQD" entry**
Type: Behavioral · Priority: **P0** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-Qwen(AB-05), S-v0dev(F-04, exact `L275` citation), S-Manus(AB-03, `L273-275`), S-Kimi(T01), S-ChatGPT(AB-009, `Home.tsx:275`) — **5/9 independently reading the same line, converging on the identical citation** · Artifacts: `Home.tsx:275`, confirmed directly in this pass: `const nextCommand = command.trim().toUpperCase() || "FQD";`, feeding directly into `setCommandHistory` at line 289 with no empty-guard · Evidence: Source, **E4 directly verified, E3 independent corroboration** (5 separately-authored reads converged on one line number), Very Strong
Observation: Pressing Execute (or Enter) with an empty or whitespace-only input does not no-op. It submits a real `FQD` command, appends a genuine entry to `commandHistory`, advances the `LOG` counter, and — if this happens during Assessment mode — is included in `assessmentScore`'s denominator exactly as if the trainee had typed and intended `FQD`.
Impact: Creates a false training event. A trainee who taps Execute reflexively, or to "see what happens," silently logs an assessment-relevant command they never typed. This is the one finding in this report that touches genuine command-submission behavior, not pure presentation.
Risk: **Evidence/assessment integrity.** Directly implicates this audit's own Trust/Safety/Evidence-Integrity principle (§ prompt rule 22): this is a UI behavior that can create evidence and affect a score.
Dependency: **Mixed — Engine/interaction-safety for the root fix, UI-only for a safe interim mitigation.** The *fix* (reject empty submission) is a one-line guard-clause change with no risk to non-empty command semantics; the audit brief's own UI-only mandate is satisfied because rejecting an empty string is not "inventing engine truth," it is refusing to invent a command the trainee never typed.
Decision: Empty/whitespace submission produces no history entry, no score change, no LOG increment, and shows an inline "Enter a command to continue" (or equivalent) state — never a silent `FQD`.
Action: Guard `submitCommand` so a blank `command.trim()` returns early with a visible inline validation state instead of falling through to `|| "FQD"`.
Validation: Submitting an empty command a) creates no history entry, b) does not change accuracy/score, c) does not advance LOG, d) shows a visible correction message. Non-empty submissions of AN/SS/FQD/FXP remain byte-for-byte identical before and after — regression-test explicitly, since this is the one finding that touches behavior.

---

**AB-F003 — EN/AR language toggle is fully cosmetic; no `dir`, no translation layer, no font-swap**
Type: Systemic/Content · Priority: **P0 (as a scope decision) / P2–P3 (as a build)** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-Claude(GLB-01), S-Gemini(TYP-01), S-Grok(L-01), S-v0dev(F-15), S-Qwen(AB-04, AB-008... via AB-008 chatgpt id collision — see note), S-ChatGPT(AB-008), S-Kimi, S-Manus(AB-16 area), S-DeepSeek — **9/9**, but this is **high-consensus/limited-independence per the prompt's own rule**: most of the nine saw the same toggle in the same screenshots. The sub-claim carrying real independent weight — `<html lang="en">` never updates, no `dir="rtl"` anywhere, no i18n library reference — was reached via five separate source-code reads, which **is** genuine corroboration (E3) · Artifacts: `Home.tsx:164` (`toast.success` handler), `index.css` `--font-ar` token (declared, unapplied) · Evidence: Source, E3–E4 for the mechanism, Good-to-Strong
Observation: The toggle flips a local `language` state, re-styles its own two spans, and fires `toast.success("Interface language set to ${next}")`. Nothing else in the application observes `language`. No `dir` attribute is ever set. `--font-ar: "Cairo", system-ui, sans-serif` is declared as a token but never applied to any conditionally-rendered Arabic content, because no Arabic content exists.
Impact: This sits directly against the platform's own stated Saudi-market mission and is present on every single screen (shared Topbar), making it the single largest, most visible gap between what the product's chrome promises and what it currently does.
Risk: Mission/trust, product-wide.
Dependency: **Content + Engine + Architecture** for a real fix (translation source, RTL layout mirroring throughout the CSS, bidi isolation for mixed English-command/Arabic-prose content) — **explicitly not** a UI-only patch, and explicitly not attempted as one here.
Decision: **This phase, do not present a toggle that visually implies a working language switch.** Two non-conflicting options for whoever owns this: (a) relabel to an honest "Arabic — coming soon" state, or (b) if Arabic is genuinely near-term, use this moment to specify the `dir="rtl"` + `--font-ar` wiring plan (§9) so a later engineer builds it against one clear target instead of a second half-wired pass.
Action: Replace the current `toast.success` implying completion with either a disabled/preview-labeled control, or begin the scoped i18n workstream per §9's Arabic/RTL decisions.
Validation: No control on any screen implies a completed language switch that has not happened. If/when real Arabic is built: activating it sets `dir="rtl"` at the document root, mirrors layout, and renders Arabic text in Cairo while GDS commands and airport/airline codes remain LTR/monospace via `unicode-bidi: isolate` inside RTL prose (Gemini's specific, correct technical recommendation).

---

**AB-F004 — None of the three declared typefaces are confirmed loading**
Type: Systemic · Priority: **P0** · Verdict: **TEST BEFORE ACCEPTING**
Sources: S-Claude(GLB-02, direct `index.html` read — commented-out Google Fonts block, explicit "BLOCK TO BE DELETED" marker in the comment text itself, empty `public/` folder, zero `@font-face` in `index.css`), S-ChatGPT(AB-006, independently confirms "commented out" via its own `index.html` read), S-Manus(AB-16 — **live-build observation**: "HTML evidence shows only Inter import," a refinement worth preserving, not a contradiction — see below), S-v0dev(F-21, explicitly flagged "verify" since it had no `index.html`), S-Kimi, S-DeepSeek, S-Grok — 7/9 · Artifacts: `client/index.html` (not in this synthesis pass's file set — **not independently re-verified here**), `index.css` `:root` lines 32–34 confirmed in this pass: `--font-display:"Space Grotesk"`, `--font-ar:"Cairo"`, `--font-mono:"IBM Plex Mono"` · Evidence: Source (S-Claude/S-ChatGPT only, not this pass), E3 for two independent reads reaching the same conclusion via the same file, Strong-but-not-directly-confirmed-here
Observation: Two audits independently read `index.html` and found the font `<link>` commented out. A third (Manus), the only audit to actually build and serve the app locally, observed what it describes as an active **Inter** import — plausibly a different, unrelated default (e.g., a framework/template default) rather than a contradiction of the first finding: it is entirely consistent for the three *intended* fonts to be non-loading while a *fourth, unintended* font is loading as a fallback. This synthesis treats these as complementary, not conflicting, but flags the Inter-specific detail as the less-verified half of the finding.
Impact: If accurate, every screen currently renders in fallback fonts, not the designed Space Grotesk/IBM Plex Mono/Cairo identity — the largest gap between design intent and shipped reality in the whole product, and it affects every other screen's visual QA simultaneously.
Risk: Foundational — this should be fixed *before* any contrast/spacing QA pass, since font metrics change line length and wrapping.
Dependency: **UI-only** (restore the font link, or self-host the three families) — zero engine/logic risk.
Decision: Restore font loading for all three declared families before other visual polish work.
Action: Re-enable/replace the font-loading mechanism in `index.html` (or self-host).
Validation: **TEST BEFORE ACCEPTING** — this synthesis pass did not have `index.html` and could not re-confirm the exact current state first-hand. Before implementing: inspect computed `font-family` on a heading, a terminal command line, and (once AB-F003 progresses) Arabic body text, and confirm each resolves to its intended named family, not a fallback — including confirming/removing any unintended Inter import if S-Manus's live observation holds.

---

**AB-F005 — Primary button contrast fails WCAG AA (2.98:1 vs 4.5:1 required)**
Type: Visual/Accessibility · Priority: **P0/P1** · Verdict: **ACCEPT**
Sources: S-Claude(GLB-04, computed via WCAG relative-luminance formula), S-ChatGPT(§8.7, independently notes the same underlying palette risk), S-v0dev(F-03 area), S-Qwen(AB-13, flags as "suspected," lower confidence since no CSS access) — E3, computed independently by at least one audit with direct CSS access
Observation: `.primary-button{background:var(--blue); color:#fff; font-size:12px; font-weight:700}`. 12px/700-weight does not meet the WCAG "large text" exception (needs ≥18.66px bold), so the 4.5:1 threshold applies; measured ratio is 2.98:1. This is the single most-repeated interactive element in the product — "Resume pricing workflow," "Resume scenario," "Open recommended/targeted practice" all use it.
Impact: A clear, product-wide AA failure on the highest-intent, most-repeated CTA.
Risk: Accessibility/legal-conformance.
Dependency: **UI-only** — single CSS value change.
Decision: Darken `--blue` for this specific text/background pairing, or darken the text, until the pairing clears 4.5:1.
Action: Adjust `.primary-button` background or text color; re-measure.
Validation: Recomputed contrast for the shipped pairing is ≥4.5:1.

---

**AB-F006 — `--text-faint` fails AA at the small sizes it is actually used at**
Type: Visual/Accessibility · Priority: **P1/P2** · Verdict: **ACCEPT**
Sources: S-Claude(GLB-05, three separate surface pairs computed: 3.66:1 / 3.18:1 / 2.94:1), S-v0dev(F-03, independently computes ~3.3–3.6:1 against the *same* hex, `#5d6a85`), S-ChatGPT(§8.7, cites the identical `#5d6a85` value and 3.66:1 ratio), S-Kimi("likely passes AA for large text but may fail for small text") — **E3, three separately-authored contrast computations converging on the same token and a consistent ratio range** · Artifacts: `index.css:17`, confirmed directly in this pass: `--text-faint: #5d6a85;`
Observation: `--text-faint` is used throughout for eyebrows, timestamps, and secondary metadata — precisely the size category (well under 18px) where WCAG's stricter normal-text threshold applies, not the large-text exception.
Impact: Widespread — affects eyebrows, footnotes, terminal metadata, and scenario/tracking captions across every screen.
Risk: Accessibility.
Dependency: **UI-only.**
Decision: Raise `--text-faint`'s luminance until it clears 4.5:1 against its most common rendered backgrounds, or resize/reweight it to legitimately qualify for the large-text exception where that is the actual intent.
Action: Adjust the token value; re-measure against `--navy-950`, `--panel-solid`, and `--navy-750` (the three surfaces it appears on).
Validation: Every use of `--text-faint` at non-large size meets 4.5:1 against its actual rendered background.

---

**AB-F007 — Systemic absence of tab/toggle ARIA semantics across five separate control groups**
Type: Structural/Accessibility · Priority: **P1** · Verdict: **ACCEPT**
Sources: S-Claude(GLB-07, "exhaustively grep-verified"), S-Gemini, S-Grok, S-v0dev(F-multiple), S-Kimi, S-Manus(AB-18), S-ChatGPT, S-Qwen(implied throughout §5), S-DeepSeek — **9/9, and independently re-confirmed by direct count in this pass: zero occurrences of `role="tab"`, `aria-selected`, `aria-pressed`, or `aria-expanded` anywhere in the 363-line file** · Evidence: **E4 directly verified**, Very Strong
Observation: This affects five visually tab-like segmented controls that share the identical gap: Practice's Learn/Practice/Assessment `mode-tabs`; Progress Tracking's Overall/Accuracy/Sequencing `metric-switcher`; Progression's Technical/Customer Service `track-tabs`; Growth Record's Record/History/Reports `growth-tabs`; and Scenarios' status `filter-tabs`. Current selection is communicated by a CSS class (`is-active`/`is-selected`) and a box-shadow underline only — nothing programmatic.
Impact: A screen-reader user hears "button," not "tab, selected." Current selection is not exposed to assistive technology anywhere in the product.
Risk: Accessibility, systemic.
Dependency: **UI-only** (attribute-level addition; no visual or logic change required).
Decision: One shared pattern, not five separate implementations. Use `role="tablist"`/`role="tab"`/`aria-selected` for controls that swap an entire panel (mode-tabs, growth-tabs); `aria-pressed` for controls closer to a toggle that changes a data series without swapping panels (metric-switcher). A later engineer should assign each of the five to whichever category matches its actual behavior.
Action: Add the appropriate ARIA to all five groups from one shared component pattern, sequenced *after* AB-F008's token consolidation (§4, Critical Decision 4) so the work is written against one system.
Validation: A screen-reader user can determine which tab/toggle is currently active in each of the five groups without relying on visual color alone.

---

**AB-F008 — Two parallel color-token systems carry different hex values for the same semantic role**
Type: Systemic/Design-system · Priority: **P1** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-Claude(GLB-13), S-ChatGPT(§7.1), S-DeepSeek(DS-09), S-v0dev(F-18), S-Kimi(§7 Tokens), S-Grok(D-01) — **6/9 independently identified the same structural pattern**, with S-Claude and S-ChatGPT each independently citing specific differing hex pairs · Artifacts: **confirmed directly in this pass** — `index.css`, a second unconditional `:root{}` block headed by the comment `/* AeroBridge Elevation Directive — preserve Flight Deck Console identity; prioritize Terminal, calm precision, and operational readability. */`, defining `--ab-surface-0/1/2`, `--ab-border`, `--ab-text-primary/secondary/muted`, `--ab-success:#55d6a6`, `--ab-error:#ef8a96`, `--ab-info:#73a0ff`, `--ab-warning:#edbc69`, applied via `.page-practice`-scoped selectors — genuinely different hex values from the base tokens for the identical semantic roles (e.g., base `--green:#3ed598` vs `--ab-success:#55d6a6`)
Observation: This is not aliasing — it is a second, deliberately-tuned pass (the comment itself signals intent: "prioritize Terminal... operational readability") scoped to Practice only, layered on top of rather than merged into the base system.
Impact: Error/success/text colors on the Terminal screen are subtly different shades from the identical semantic roles everywhere else — imperceptible today, a real maintenance hazard the moment either layer is edited without the other.
Risk: Design-system coherence / future drift.
Dependency: **UI-only** (token consolidation, no logic change).
Decision: Fold `--ab-*` into the base token set as canonical — it reads as the more recent, more deliberately tuned pass — rather than deleting it. Extend the refinement outward instead of maintaining two systems.
Action: Replace base-token values with the `--ab-*` equivalents where they diverge; remove the `--ab-*` namespace once consolidated.
Validation: A single token set drives color everywhere; grepping the stylesheet for a legacy `--ab-` reference after consolidation returns nothing.

---

**AB-F009 — Twelve controls fire a generic toast in place of their implied action**
Type: Behavioral, systemic · Priority: **P1 (toggle-adjacent instances) / P2 (rest)** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-Claude(GLB-08, full inventory table), S-v0dev(F-16, adds "My route" — not in Claude's list), S-Manus(AB-09), S-Qwen(scattered AB-01/02/03/19), S-ChatGPT(AB-011), S-Kimi, S-Grok, S-DeepSeek — **8/9** · Artifacts confirmed directly in this pass: Language toggle (`L164`), Search (`L165`), Profile (`L166`), "My route" (`L219`), "View map"/"See all stages" (`SectionHeader action`, `L212/L229`), "View evidence"/"See patterns"/"View history" (Growth `SectionHeader`), Scenarios "Filters" (`L335`) and sort `<select>` (`L335`), Growth "Backup" (`L343`) — **12 confirmed instances**, resolving a minor internal inconsistency in S-Claude's own count (its table listed 11 rows but its prose said "twelve")
Observation: Each fires `toast.info`/`toast.success` instead of performing, or navigating to, the action its icon/label implies. Two — Scenarios' "Filters" button and sort `<select>` — are worse than merely inert: "Filters" sits directly beside a working `filter-tabs` row it visually duplicates (SCN-02), and the sort control has real, already-present sortable fields (difficulty, duration, category) it simply never applies (SCN-03).
Impact: The single most-repeated "looks functional, isn't" pattern in the product; works directly against the "confidence/precision" feeling the product is going for.
Risk: Trust, product-wide, cumulative.
Dependency: **Mixed** — most (View map, See all stages, My route, View evidence/patterns/history, Filters button) are UI-only to remove, relabel, or de-emphasize until real; Search and real sort/filter depth are Engine/Data-dependent to build.
Decision: Per-control: (a) remove/de-emphasize where the control duplicates working functionality already on screen (Scenarios "Filters"); (b) wire to real, already-available data where the data exists with no new model needed (Scenarios sort, using existing fields); (c) relabel honestly elsewhere pending a product decision.
Action: Case-by-case per the table in S-Claude's original inventory, extended with "My route."
Validation: No control performs a `toast`-only pretense of a real action the user could reasonably expect to have happened.

---

**AB-F012 — Hint/command count is shared across Learn, Practice, and Assessment modes; switching modes resets only `sessionComplete`**
Type: Behavioral/State · Priority: **P1 (transparency mitigation) / DEFERRED (root fix)** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-Claude(PRA-02, "fully source-verified"), S-v0dev(F-06/F-07, exact line citation), S-Manus(AB-05, `L240-302`), S-ChatGPT(§5.2 interaction issues), S-Kimi — **5/9, high independence (separately-authored reads all converging on the identical two-line mechanism)** · Artifacts: **confirmed directly in this pass** — `Home.tsx:301`, mode-tab `onClick` handler: `{ setMode(item); setSessionComplete(false); }` — resets *only* `sessionComplete`; `Home.tsx:303`, Reference-toggle handler: `if (nextOpen && mode !== "assessment") setHintCount((count) => count + 1);` — increments identically in Learn and Practice
Observation: A trainee who freely opens Reference two or three times in Learn mode — the product's own low-stakes, exploratory, default-first mode — then switches to Assessment carries that hint count into a score whose own UI language ("No hints," "HINTS SUPPRESSED") implies a clean evaluation.
Impact: A real question about assessment integrity, not a cosmetic one.
Risk: **Evidence integrity.**
Dependency: The **root fix is State/Data-dependent** (deciding whether hints/history should be isolated per mode is a scoring-model decision this UI-only audit cannot make — see §13). A **UI-only transparency mitigation is available now**: surface the carried-over count explicitly on entering Assessment.
Decision: Ship the transparency mitigation immediately; defer the scoring-model question to product/engineering per §13.
Action: When a trainee enters Assessment mode with a non-zero carried-over hint or command count, state that count before their first Assessment submission (e.g., "Entering Assessment with 2 hints and 5 commands already logged this session").
Validation: The carried-over count is stated in trainee-readable language before the first Assessment command is submitted.

---

**AB-F013 — Per-command toast notifications triplicate signal already carried by the terminal history and the Coach panel**
Type: Behavioral · Priority: **P1/P2** · Verdict: **ACCEPT**
Sources: S-Claude(PRA-03), S-DeepSeek(DS-01, rated P0), S-Qwen(AB-08), S-Kimi, S-Grok(implied), S-v0dev — 6/9
Observation: Every submission fires `toast.success`/`.error`/`.warning` on top of (a) the history entry's own color/text and (b) the Coach panel's "LATEST COMMAND" block, which updates on the same submission.
Impact: On a long session — this product's own stated "long-session comfort" is an explicit design goal — this is a third, transient, motion-adding channel repeating information the other two already carry persistently and accessibly.
Risk: Low individually; cumulative fatigue over a real session.
Dependency: **UI-only.**
Decision: Reserve toasts for events without an existing persistent, in-context home (session-level milestones, Assessment saved) rather than every single command.
Action: Remove or gate the per-command `toast.success`/`.error` calls; keep the terminal-history and Coach-panel channels as the source of truth.
Validation: Over a simulated 15+ command session, success/error signal is not repeated in three simultaneous channels without a documented reason.

---

**AB-F014 — No auto-scroll-to-latest in the terminal history; long sessions require manual scrolling**
Type: Behavioral · Priority: **P1/P2** · Verdict: **ACCEPT**
Sources: S-DeepSeek(DS-05), S-Kimi(explicit — no `useEffect`/ref scrolling on `commandHistory` change), S-Manus(§6.4, "jump to latest"), S-Qwen(§6 Q6, "history auto-scrolls... validation needed") — 4/9, consistent framing
Observation: `.terminal-body{overflow:auto}` provides a scroll container but nothing programmatically scrolls it when a new entry is appended.
Impact: On a long session the trainee must manually scroll to see their latest result — friction directly opposed to the product's own long-session-comfort goal.
Risk: Usability, moderate.
Dependency: **UI-only.**
Decision: Auto-scroll the terminal body to the newest entry on submission; consider a "jump to latest" affordance only if history grows long enough that auto-scroll alone becomes disorienting.
Action: Add scroll-to-bottom behavior on `commandHistory` change (respecting `prefers-reduced-motion`, per the product's existing, exemplary pattern).
Validation: After submitting a command with several prior entries present, the newest entry is visible without manual scrolling.

---

**AB-F015 — Dual prompt/caret affordance: the scrolling output area echoes the in-progress command directly above the real input**
Type: Visual/Interaction · Priority: **P2** · Verdict: **TEST BEFORE ACCEPTING**
Sources: S-Claude(PRA-04, sole detailed source; explicitly marked "requires live/user validation")
Observation: `terminal-active-line` renders a live mirror (`> {command||"_"}` with a blinking caret) as the last line of the scrollable history, directly above the real, focusable `<input>`. This is a deliberate "authentic terminal" device.
Impact: Two visually similar prompt-and-caret cues sit in immediate vertical proximity; only the lower one is real and labeled. May read as intentional after one use — the open question is strictly first-use clarity, not an ongoing functional barrier.
Risk: Low; single-source but well-reasoned.
Dependency: **UI-only.**
Decision: **TEST BEFORE ACCEPTING** rather than change pre-emptively — this is exactly the kind of finding that could be correct or could be over-cautious about a device genuinely common in terminal-emulator UIs.
Action: None yet.
Validation: In a moderated session, a first-time user identifies the real, typeable input within a few seconds without prompting. If they consistently do not, revisit.

---

**AB-F016 — Session timer is pre-seeded at 4:32 (272s), not 0:00, on every fresh entry into Practice**
Type: Content/State · Priority: **P3** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-Claude(PRA-05), S-Kimi(confirms exact seed value) — 2/9, but **E4 directly confirmed**: `Home.tsx:250`, `useState(272)`
Observation: No copy anywhere distinguishes "this is a continued session" from "this is a fresh one," and screenshots' visible 4:36/4:39 timestamps are consistent with the seed, not a genuine elapsed session.
Impact: Minor but avoidable inconsistency between claimed state and displayed state.
Risk: Low.
Dependency: **Content/State — UI-only.**
Decision: Start at 0:00 for a genuinely new session entry, or add explicit "resumed" framing if the pre-seeded value is intentional (e.g., simulating a mid-session hand-off).
Action: Either change the seed to 0 or add copy.
Validation: A fresh entry into Practice shows a session clock consistent with its own copy.

---

**AB-F017 — Terminal contains a large, fixed decorative empty region (`.terminal-gap`, 130px) before the active input line**
Type: Visual · Priority: **P2/P3** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-ChatGPT(§5.2, §6.4 — "large decorative empty terminal region"), S-Kimi(explicit — recommends replacing with `justify-content:flex-end`), S-Qwen(AB-09, "empty terminal void," rates P1 for the *first-run* instance specifically) — 3/9, but **confirmed directly in this pass**: `index.css`, `.terminal-gap{height:130px}`
Observation: On first entry (no commands yet), this creates a large blank region between the "Ready. Illustrative local response layer loaded." line and the input — visible in S-Shots Image 5.
Impact: Reads as an "empty card" rather than an active workstation on the very first view a trainee gets of the product's most important screen — compounds AB-F001's first-impression problem rather than being independent of it.
Risk: Moderate, first-impression.
Dependency: **UI-only.**
Decision: Replace the fixed-height gap with a flexible layout that keeps the active prompt near the input regardless of history length, rather than a static 130px reservation.
Action: Swap `.terminal-gap` for `justify-content: flex-end` on the scrolling container, or equivalent.
Validation: On first entry (zero history), the terminal does not present a large empty void between the boot lines and the input.

---

**AB-F018 — Focus Mode lacks an explicit keyboard focus trap**
Type: Accessibility · Priority: **P1/P2** · Verdict: **ACCEPT**
Sources: S-Kimi(T04, explicit — Tab can escape into browser chrome), S-Manus(§6.7, "must not trap the user" — framed as a requirement, implying the gap), S-ChatGPT(§6.8, "not semantically a modal/dialog region") — 3/9
Observation: `body:has(.focus-mode){overflow:hidden}` correctly prevents background *scroll* (confirmed working, and a genuinely modern, correct use of `:has()` — see §12 Keep/Preserve) but this is a scroll-lock, not a keyboard focus trap; nothing cycles Tab within the terminal panel while Focus Mode is active.
Impact: A keyboard-only user in Focus Mode can Tab out into browser chrome or off-screen elements, working against the "focused workstation" intent.
Risk: Accessibility, moderate — distinct from, and should not be confused with, the (confirmed-working) scroll-lock.
Dependency: **UI-only.**
Decision: Add a focus trap cycling through the Focus Mode's interactive elements (input → execute → reference → focus-toggle → exit).
Action: Implement standard focus-trap behavior scoped to `.focus-mode`; add `Escape`-to-exit as a complementary, not required, enhancement.
Validation: With Focus Mode active, repeatedly pressing Tab never moves focus outside the terminal panel.

---

### 5.2 Global shell, navigation, and dead code

---

**AB-F010 — Systemic pattern: illustrative/hardcoded summary numbers do not match the data they summarize**
Type: Content/Systemic · Priority: **P1** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-Claude(PRG-01/SCN-01/GRW-03, three separate findings this synthesis merges into one systemic pattern per the prompt's own semantic-deduplication rule), S-Manus(AB-10, rated **P0**, "evidence integrity"), S-ChatGPT(AB-001, rated P0, same framing as Manus), S-v0dev(F-17, consolidates with exact line numbers `L300/313/335`), S-Qwen(AB-07), S-Kimi — **7/9**, high independence (each of the 3–4 sub-instances independently re-derivable from the array lengths in source) · Artifacts, **every instance confirmed directly in this pass**:
  - `Home.tsx:226` — "3 / 8 stages" against a `levels` array of **6** items (2 mastered, 1 current, not 3 of anything cleanly, against 8 UI-only decorative segments in `.segmented-progress` with no data binding to `levels.length`)
  - `Home.tsx:335` — "23 / 40" scenarios and "Needs improvement: Exchanges & Refunds" against a `scenarios` array of **5** items whose only categories are GDS / Mixed Workplace / Customer Service — **"Exchanges & Refunds" exists nowhere in the data**
  - Growth History tab — "LOG 04 / 12" against **3** rendered `history-list` entries
  - `Home.tsx:256` — footer accuracy shows **86%** (`const accuracy = submitted ? liveAssessment.accuracy : 86`) before any command is submitted
  - `Home.tsx:313` — footer "Commands mastered 128 / 210" is a static literal, unconnected to any trainee action
Observation: Each instance independently confirmed against source; three of the five (3/8, 23/40+category, LOG 04/12) are additionally visible pixel-for-pixel in the supplied screenshots.
Impact: This is the pattern with the highest cumulative trust cost in the entire audit, precisely because the product's core promise is evidence a trainee can rely on — a training platform showing numbers that don't add up undercuts that promise more directly than any visual defect could.
Risk: **Evidence/trust integrity**, product-wide, cumulative.
Dependency: **Content-dependent for a full fix** (either the full curriculum/scenario library needs to exist so "8" and "40" are real denominators, or the copy needs to honestly say "N available now" against the current smaller set) — **but a UI-only interim fix is available immediately**: derive every count from its actual array length rather than a hardcoded literal, and remove or replace the non-existent "Exchanges & Refunds" reference now, independent of any content decision.
Decision: Ship the UI-only derivations and the category-name fix immediately (P1, no dependency); treat the "is 8/40 the eventual real total" question as a content/product decision to sequence separately (§13).
Action: Replace hardcoded literals with `{levels.length}`/`{scenarios.length}`-derived values (or honest smaller framing) everywhere in the table above; remove the "Exchanges & Refunds" reference or replace it with a category that exists in `scenarios`.
Validation: Every summary count on screen is either arithmetically derived from its underlying array or explicitly labeled as illustrative/placeholder. No category name appears in summary copy that does not exist in the underlying data.

---

**AB-F011 — Pinch-to-zoom appears disabled via viewport meta**
Type: Accessibility · Priority: **P0/P1** · Verdict: **TEST BEFORE ACCEPTING**
Sources: S-Claude(GLB-03, direct `index.html` read: `maximum-scale=1, user-scalable=no` or equivalent) — **1/9 explicit**, not independently re-verified in this pass (file not supplied)
Observation: If accurate, this is a WCAG 1.4.4 (Resize Text) failure and a hard accessibility barrier for low-vision users, unrelated to and more severe than any color-contrast finding above.
Impact: Would prevent any user from compensating for small text (several instances of which are separately flagged above) by zooming — compounding rather than independent of AB-F006/AB-F037.
Risk: Accessibility, potentially severe if confirmed.
Dependency: **UI-only** (one meta-tag attribute) if confirmed.
Decision: **TEST BEFORE ACCEPTING** — single-source, unverified in this pass; treat as high-confidence-but-unconfirmed given S-Claude's specificity and general reliability track record in this synthesis (every other S-Claude claim independently spot-checked in this pass was accurate), not as settled fact.
Action: None until confirmed.
Validation: Inspect the live `viewport` meta tag; if scaling is restricted, remove the restriction. This should be one of the very first things checked once `index.html` is available for direct review, given the P0/P1 severity if true.

---

**AB-F019 — `Map.tsx` / `MapView` is complete, unused dead code**
Type: Hygiene · Priority: **P3** · Verdict: **ACCEPT**
Sources: S-Qwen(via AB-03 area), S-v0dev(F-22) — **2/9 explicit, but missed by 7/9 including the otherwise-exhaustive S-Claude** despite S-Claude listing `Map.tsx` among files read · Evidence: **E4, directly confirmed in this pass** — `Map.tsx` (155 lines, a fully-built interactive route/scenario map component) is imported by neither `App.tsx` nor `Home.tsx`; no reference to `Map`/`MapView` exists anywhere in the two files that constitute the entire rendered application
Observation: A complete, independently-functional component exists in the codebase and renders nowhere. This is exactly the kind of low-visibility, easily-missed finding the audit's zero-loss-coverage and minority-insight-preservation rules exist to protect — it appears in only 2 of 9 source audits and would have been silently dropped by any naive majority-vote synthesis.
Impact: Codebase clarity; a maintainer encountering `Map.tsx` unassisted would reasonably assume it is either live or nearly so. Also relevant context for AB-F009's "View map" toast-stub finding: the toast-only Progression "View map" action may be a placeholder for exactly this unused component, suggesting the map screen was designed, partially built, and then not wired in — worth flagging to whoever owns the roadmap rather than treating purely as accidental dead code.
Risk: Low (hygiene), but worth flagging given the component appears substantially complete.
Dependency: **UI-only** to remove; **Architecture-adjacent** to decide whether to wire it in instead (a product decision, not this audit's to make).
Decision: Either remove `Map.tsx` from the codebase, or wire it to the Progression "View map" action it appears designed to serve.
Action: Confirm with whoever owns the roadmap before deleting — the component's completeness suggests intent, not accident.
Validation: No orphaned, fully-built, unreferenced component ships in the final bundle without an explicit decision recorded.

---

**AB-F020 — `ErrorBoundary` not mounted at the app root; `NotFound` is visually off-brand and unreachable**
Type: Hygiene · Priority: **P2/P3** · Verdict: **ACCEPT**
Sources: S-Claude(GLB-09), S-Manus(AB-17, independently corroborates both halves) — 2/9 explicit, **E3** independent corroboration · Artifacts: confirmed via `App.tsx` (renders only `<Home/>` directly, no boundary wrapper, no router with a catch-all)
Observation: If any component in the render tree throws, the trainee sees a blank white screen with no recovery path, breaking the dark "Flight Deck Console" identity at the worst possible moment (an actual failure). `NotFound.tsx`, where it exists, does not share the app's visual language and cannot currently be reached through normal navigation.
Impact: No graceful-failure path exists anywhere in the product.
Risk: Low-probability, high-severity-when-it-happens.
Dependency: **UI-only** (wrap the root, restyle NotFound to match the design system).
Decision: Mount the boundary; restyle NotFound in the Flight Deck identity.
Action: Wrap `<Home/>` in the existing `ErrorBoundary`; apply current design tokens to `NotFound`.
Validation: A deliberately-thrown error in a child component renders the boundary's fallback UI, styled consistently with the rest of the product, rather than a blank screen.

---

**AB-F021 — `BrandMark` hardcodes an external `/manus-storage/...` image path with no `onError` fallback; confirmed by an independent live-build pass to affect archive portability**
Type: Hygiene/Robustness · Priority: **P2** · Verdict: **ACCEPT**
Sources: S-Qwen(AB-18, source-code finding), S-ChatGPT(independently cites the same three locations — `index.css:81,113,116` and `Home.tsx:99` — via its own separate read), S-Manus(AB-19, **the only audit to actually run the build**, independently confirms via runtime that these are live-hosted, not bundled, assets) — **3/9, genuinely independent (two static reads + one live-runtime confirmation converging on the same file locations)**, **E4** for the code-level claim, confirmed directly in this pass: `Home.tsx:98-100`, `<img src="/manus-storage/aerobridge-share-mark_5efd31e0.png" alt="" />` with no `onError` handler
Observation: The brand mark, and (per S-ChatGPT/Manus) at least one background image in `index.css`, resolve to a hosting-platform-specific path rather than a bundled repository asset. If that host is unavailable, the brand mark — appearing in the topbar, sidebar, and mobile drawer on every screen — silently fails to nothing (an empty `alt=""` gives assistive tech nothing either).
Impact: Archive portability and resilience; low probability, moderate visibility when it occurs (every screen shows the mark).
Risk: Low-moderate.
Dependency: **UI-only** (bundle the asset locally; add a fallback).
Decision: Self-host the brand and background images as build-time assets rather than runtime-fetched platform paths; add an `onError` fallback regardless.
Action: Move the referenced images into the repository/build pipeline; add error handling.
Validation: The app renders its brand mark correctly with the external host unreachable.

---

**AB-F022 — `"hint-dependency"` `ErrorKind` is declared and shown in the Assessment legend but never producible by the command logic**
Type: Hygiene/Content · Priority: **P3** · Verdict: **ACCEPT**
Sources: S-Qwen(AB-16) — **1/9, E4 directly confirmed in this pass**: the type union at `Home.tsx:40` includes `"hint-dependency"`; the four-branch `commandProfile` logic (`Home.tsx:280-288`) only ever assigns `"sequence"`, `"decision"`, or `"syntax"`; the legend in `AssessmentReport` (`Home.tsx:236`) nonetheless renders a dot and label for "Hint dependency"
Observation: A trainee reviewing the error-taxonomy legend after an assessment sees a category their actual errors can never fall into.
Impact: Minor, but a precise, verifiable inconsistency worth fixing alongside AB-F010's broader "numbers should mean what they say" theme.
Risk: Low.
Dependency: **UI-only** (remove the legend entry) or **Engine-adjacent** (wire hint-heavy patterns to actually produce this classification — a scoring-model decision, deferred per §13).
Decision: Remove the unused legend entry now (UI-only, zero dependency); consider wiring the real classification as a separate, deferred scoring-model enhancement.
Action: Drop the "Hint dependency" dot from the legend until the classification is real.
Validation: Every category shown in the Assessment error-taxonomy legend is a category the command logic can actually produce.

---

**AB-F023 — Most of the fourteen declared `SystemState` values are never rendered anywhere**
Type: Structural · Priority: **P2/P3** · Verdict: **DEFER**
Sources: S-v0dev(F-15/F-23 area), S-Qwen(implied via AB-15), S-Kimi, S-ChatGPT — 4/9 · Evidence: E3, confirmed directly in this pass — of 14 declared values (`first-use, empty, loading, ready, in-progress, success, partial-success, error, retry, interrupted, completed, review, locked, unavailable`), `StateNotice` calls in source only ever pass `"empty"` (2 instances) or a dynamic value drawn from `{"completed"|"review"|"retry"}` — roughly 4 of 14 ever reachable through the current UI
Observation: The type system was built for a broader range of real-world states (loading, interrupted, partial-success, unavailable) than the current static prototype ever needs to display.
Impact: Not a current defect — a prototype legitimately doesn't need a `"loading"` state if nothing is asynchronous yet — but a gap worth knowing about before wiring to a real backend, where these states become real and necessary (a network request genuinely can be `loading`, `interrupted`, or return `partial-success`).
Risk: None currently; latent.
Dependency: **Engine-dependent** — these states become meaningful once real async data exists, which is outside this audit's UI-only scope.
Decision: **Defer.** Record as a forward-looking note for whoever builds the real data layer, not an action item for this pass.
Action: None this phase.
Validation: N/A this phase — revisit when async data is introduced.

---

**AB-F024 — `AnimatedBar` renders as a bare `<i>` element with only `aria-label`, no `role="progressbar"`**
Type: Accessibility · Priority: **P2** · Verdict: **ACCEPT**
Sources: S-Gemini(A11Y-01) — **1/9, but E4 directly confirmed in this pass**: `Home.tsx:139-142`, `<i className={className} style={{width:...}} aria-label={...} />` — no `role`, no `aria-valuenow/min/max`
Observation: `aria-label` alone does give a screen reader *some* information (the percentage, read as if it were a label on a generic element) — this is a real but moderate gap, not a total accessibility void, and should be scoped accordingly rather than over-stated.
Impact: Used for every skill bar, streak bar, and level-progress bar across Progression and Growth — a small semantic gap repeated many times.
Risk: Accessibility, low-moderate severity, moderate frequency.
Dependency: **UI-only.**
Decision: Add `role="progressbar"` with `aria-valuenow`/`aria-valuemin="0"`/`aria-valuemax="100"` to the existing element; no visual change required.
Action: Extend `AnimatedBar`'s props spread with the three ARIA attributes.
Validation: Each progress bar is announced by assistive technology as a progress indicator with its current value, not a generic labeled element.

---

**AB-F015b (grouped with AB-F017/AB-F018 pattern) — Mobile drawer and Topbar search popover lack dialog semantics**
Type: Accessibility · Priority: **P1** · Verdict: **ACCEPT**
Sources: S-Gemini(A11Y-02, re: search popover specifically), S-v0dev(F-10, re: drawer specifically), S-Kimi(T20), S-ChatGPT — 4/9, covering two related surfaces · Evidence: **E4, confirmed directly in this pass** — neither `Home.tsx`'s `mobile-drawer` block (`L362`) nor its `command-popover` block (`L168`) contains `role="dialog"`, `aria-modal`, an `Escape`-key handler, or a focus-trap/focus-restore mechanism; grepped directly — zero matches for any of these patterns in the file
Observation: Both are conditionally-rendered overlays with real interactive content (drawer: full nav list; popover: a dismiss button) but neither behaves as assistive technology expects a modal/popover to behave.
Impact: Keyboard and screen-reader users have no reliable way to know they've entered an overlay context, and no `Escape` shortcut to leave one.
Risk: Accessibility, moderate, affects two separate surfaces with one shared fix pattern.
Dependency: **UI-only.**
Decision: Apply one shared dialog/popover pattern (role, `aria-modal` where appropriate, `Escape` handling, focus trap and focus-restore-to-trigger) to both surfaces.
Action: Wire standard modal/popover semantics to `mobile-drawer` and `command-popover`.
Validation: Opening either surface moves focus into it; `Escape` closes it and returns focus to the triggering control; a screen reader announces entry into a dialog/popover context.

---

**AB-F015c — No `<main>` landmark; side navigation `<nav>` is unlabeled; no skip link; no focus movement on route change**
Type: Accessibility · Priority: **P1** · Verdict: **ACCEPT**
Sources: S-Qwen(AB-12), S-v0dev(F-11/F-12/F-13), S-Kimi, S-ChatGPT — 4/9 · Evidence: **E4, confirmed directly in this pass** — the app root renders `<div className="app-frame"><SideNav/><div className="app-main">...` (no `<main>` anywhere); `SideNav`'s `<nav>` (`L176`) has no `aria-label` (contrast with `BottomNav`'s `<nav>`, which does: `aria-label="Primary workspace navigation"`, `L185`); no skip-link element exists; the `navigate` function (`L359`) changes `view` and pushes history state but does not move focus
Observation: This is four small, related landmark/navigation gaps rather than one — grouped here because they share a single fix category (semantic HTML + one focus-management addition) even though each is individually minor.
Impact: Screen-reader and keyboard users lack the standard fast-navigation landmarks sighted users get for free from visual hierarchy; route changes are silent to assistive technology.
Risk: Accessibility, foundational-but-low-individual-severity.
Dependency: **UI-only.**
Decision: Add `<main>` around `.app-main`'s content, label the side `<nav>` to match the bottom nav's existing pattern, add a skip-to-content link, and move focus to the new view's heading on navigation.
Action: Four small, independent HTML/attribute changes.
Validation: A skip link is the first focusable element on the page; both navs are labeled; a screen reader announces the new page's heading after navigating.

---

### 5.3 Navigation, information architecture

---

**AB-F043 — Mobile bottom-nav reorders Practice and Scenarios relative to the canonical `navItems` array and the desktop side-nav**
Type: Structural · Priority: **P2** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-Claude(GLB-10) — 1/9, **E4 confirmed directly in this pass**: `Home.tsx:184`, `const orderedItems = [navItems[0], navItems[2], navItems[1], navItems[3], navItems[4]]` — desktop order is Progression/Practice/Scenarios/Growth/Tracking; mobile bottom-nav order is Progression/Scenarios/Practice/Growth/Tracking (positions 2 and 3 swapped)
Observation: This appears deliberate (it centers Practice/"Train" in the visual middle of five mobile nav slots, matching the intentional `.is-primary` emphasis confirmed in §15.1) rather than accidental, but it does mean a trainee's mental map of "second item" differs between mobile and desktop.
Impact: Low-moderate — most users experience one form factor consistently, so cross-device order memory is a narrower audience than it first appears, but any onboarding material or verbal instruction referencing nav position by number would need to specify which layout.
Risk: Low.
Dependency: **UI-only** if changed; **Content/Documentation-only** if kept and simply noted.
Decision: Keep the reorder (it correctly serves the "Practice is primary" intent, and undoing it would remove the deliberate mobile emphasis this audit elsewhere recommends preserving) but note it explicitly in any design-system documentation so it is never mistaken for an accidental bug by a future maintainer.
Action: Document only; no code change recommended.
Validation: N/A — documentation task.

---

**AB-F044 — "Route" is overloaded: it is both Progression's mobile nav short-label and the universal per-screen breadcrumb prefix ("YOUR ROUTE / 0N")**
Type: Content · Priority: **P3** · Verdict: **ACCEPT**
Sources: S-Claude(GLB-10b) — 1/9, confirmed via source: `navItems[0].short = "Route"`; every page's `page-intro` eyebrow reads `"YOUR ROUTE / 0N · ..."` regardless of which screen is active
Observation: A trainee on the Scenarios screen sees "YOUR ROUTE / 03" as a breadcrumb while a completely different nav item is separately labeled "Route."
Impact: Minor terminology collision; unlikely to confuse in practice but easy to fix.
Risk: Low.
Dependency: **Content-only.**
Decision: Rename one of the two uses (e.g., the nav short-label to "Path" or the breadcrumb prefix to "STAGE").
Action: One copy change, applied consistently.
Validation: The word "Route" refers to exactly one concept in the shipped product.

---

**AB-F045 — Hamburger drawer content is a 100% duplicate of the bottom nav**
Type: Structural · Priority: **P2** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-Claude(GLB-14), S-Manus(AB-15, area) — 2/9, confirmed via source: `Home.tsx:362`, drawer maps the identical `navItems` array the bottom nav also maps, with no additional content
Observation: On mobile, the drawer exists purely to duplicate five destinations already one tap away in the persistent bottom nav.
Impact: Low-moderate — not broken, but currently offers no value the bottom nav doesn't already provide, meaning the hamburger icon and drawer occupy interface real estate and interaction cost for zero net-new capability.
Risk: Low; opportunity cost rather than defect.
Dependency: **UI-only** to remove; **Content-dependent** to make valuable (settings, profile detail, help/support — none of which currently exist as content).
Decision: Either remove the hamburger/drawer entirely on mobile (bottom nav alone covers all five destinations) or give it genuinely distinct content once such content exists. Do not leave it as a pure duplicate.
Action: Product decision required before implementation; not a same-phase action item.
Validation: N/A until the product decision above is made.

---

**AB-F046 — The 740–1099px tablet range combines desktop-density content grids with mobile-style bottom-nav and hamburger chrome**
Type: Structural/Responsive · Priority: **P2** · Verdict: **TEST BEFORE ACCEPTING**
Sources: S-Claude(GLB-16), S-ChatGPT(§8.2), S-DeepSeek, S-v0dev(implied) — 4/9, general theme, but **structurally confirmed directly in this pass**: content breakpoints (multi-column grids, wider layouts) generally shift around `739px`, while the desktop side-nav / bottom-nav swap occurs at `1100px` — meaning the 740–1099px band renders desktop-width content grids inside a layout still using mobile-pattern bottom-nav-plus-hamburger navigation chrome
Observation: This is a real, source-confirmed structural mismatch. Whether it *feels* wrong in practice (versus reading as a reasonable hybrid) genuinely requires a live tablet-width render, which no source audit had.
Impact: Uncertain until tested — could range from imperceptible to a real layout-density mismatch.
Risk: Low-moderate, unconfirmed.
Dependency: **UI-only** if a fix is needed (breakpoint alignment).
Decision: **TEST BEFORE ACCEPTING.**
Action: None until a live tablet-width render is reviewed.
Validation: Render the app at 800px, 900px, and 1000px widths; assess whether the navigation-chrome/content-density mismatch reads as awkward. If it does, align the navigation swap point closer to the content breakpoint (or vice versa).

---

### 5.4 Design system consolidation

---

**AB-F038 — Spacing, radius, and shadow values are drawn from a large, largely ad-hoc set rather than a defined scale**
Type: Systemic/Design-system · Priority: **P2** · Verdict: **ACCEPT**
Sources: S-Kimi(§7, exhaustive enumeration), S-v0dev(F-18, independently lists specific hardcoded radii: 9/10/11/12/14/18/20/24px against declared tokens of 16px/11px), S-DeepSeek(DS-09), S-Claude(GLB-13, spacing-adjacent), S-Grok(D-01) — 5/9, strongly convergent on the same underlying pattern from independent close reads
Observation: Border-radius alone spans roughly a dozen discrete pixel values across the stylesheet where two-to-three token-driven steps would cover the same visual range; spacing shows a similar (though less extreme) pattern.
Impact: Not currently visible as inconsistency (values are close enough that the eye doesn't catch it), but a real cost the moment a new screen or component is added without a defined scale to draw from.
Risk: Design-system coherence / future velocity, not current-user-facing.
Dependency: **UI-only.**
Decision: Define a small radius scale (e.g., 8/12/16/999px — the kind converged on independently by S-Kimi's own recommendation) and a spacing scale on a consistent base unit; migrate hardcoded values onto it opportunistically rather than in one disruptive pass.
Action: Author the scale; apply during other UI work already touching each component, not as a standalone sweep.
Validation: New components draw exclusively from the defined scale; a style-lint rule (if the team has one) flags raw pixel values outside it.

---

**AB-F039 — Progress Tracking's secondary KPI cards carry elaborate decorative `clip-path`/gradient ornamentation**
Type: Visual/Overdesign · Priority: **P3** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-v0dev(F-19), S-Kimi(T15) — **2/9, independently converging on the same CSS location** · Evidence: **E4, confirmed directly in this pass** — `index.css:291`, three `nth-child`-scoped `::before` pseudo-elements combining `radial-gradient`, `linear-gradient`, `repeating-linear-gradient`, and `clip-path: polygon(...)` per card, purely decorative, layered beneath the content (`z-index:-1`)
Observation: This is a genuine, verified instance of ornamentation exceeding functional need on a data-density screen — precisely the pattern the audit brief's Overdesign Defense (§ prompt rule 25) exists to catch. Notably, the codebase already shows some awareness of the cost: a `prefers-reduced-motion` rule at line 293 already dims these elements' opacity, suggesting the effect was recognized as potentially excessive even by its own author.
Impact: Low functional impact (the cards remain readable and the numbers legible), but real cognitive "scan cost" on a screen whose entire purpose is quick numeric comparison — three of the four KPI cards carry unique, complex background art that competes, faintly but measurably, with the number a trainee is there to read.
Risk: Low, aesthetic/attention-economy.
Dependency: **UI-only.**
Decision: Simplify to a single shared subtle treatment (or remove) rather than three unique polygon patterns — preserve *some* visual distinction between cards (color-coding is already doing useful work here) without three bespoke decorative layers.
Action: Replace the three `nth-child`-specific `clip-path` patterns with one shared, simpler treatment, or remove.
Validation: The KPI row reads at a glance with no loss of the current color-coded differentiation between cards.

---

**AB-F040 — `.bottom-nav`'s `grid-template-columns` is declared four separate times across the stylesheet**
Type: Hygiene · Priority: **P3** · Verdict: **ACCEPT**
Sources: S-Claude(GLB-12) — 1/9, **E4 confirmed directly in this pass** (full cascade trace in §15.1) — declared at lines 119 (4 columns, superseded), 313 (5 columns, wins unconditionally), 319 (5 columns, redundant re-statement inside a media query), and 375 (5 columns, `!important`, redundant given 313 already wins)
Observation: The *rendered result is correct* (5 columns, confirmed) — this is purely a code-hygiene finding about redundant, easily-confusable declarations, not a user-facing defect. Recorded explicitly here (rather than silently dropped) because it is the direct cause of a real, documented cross-audit disagreement (§15.1) and future maintainers should not repeat that confusion.
Impact: None user-facing; real maintenance-clarity cost.
Risk: Low.
Dependency: **UI-only.**
Decision: Consolidate to one declaration.
Action: Remove the three redundant/superseded rules; keep one clear 5-column declaration.
Validation: Visual output is unchanged; `grep -c "grid-template-columns" index.css` for `.bottom-nav` returns 1, not 4.

---

**AB-F042 — `.is-secondary-view{display:none!important}` fully removes Growth Record's primary panels from the accessibility tree when switching to History/Reports tabs**
Type: Accessibility/Structural · Priority: **P2** · Verdict: **ACCEPT WITH MODIFICATION**
Sources: S-Grok(G-01), S-Kimi(T17, independently cites the identical selector and `!important` flag) — **2/9, E4 confirmed directly in this pass**: `index.css:205`
Observation: This is a legitimate, common way to fully hide inactive tab content (and arguably *correct* given AB-F007 recommends real `role="tab"`/`aria-selected` semantics, which pair naturally with fully-hidden inactive panels) — the finding is not that hiding is wrong, but that it should be implemented as part of the same tab-semantics pattern in AB-F007, not as an isolated `display:none!important` applied independently of any ARIA relationship.
Impact: Currently correct in effect, incidentally, rather than by designed pattern.
Risk: Low — sequencing/consistency concern more than a live defect.
Dependency: **UI-only.**
Decision: Fold this into the AB-F007 tab-pattern implementation rather than treating it as separate.
Action: No standalone action; addressed as part of AB-F007.
Validation: Covered by AB-F007's validation.

---

### 5.5 Screen-specific findings

---

**AB-F047 — Progression's Technical/Customer Service track toggle changes only the description paragraph; the milestone list beneath stays Technical-labeled**
Type: Behavioral · Priority: **P1** · Verdict: **ACCEPT**
Sources: S-Claude(PRG-02), S-Kimi(T12), S-ChatGPT, S-DeepSeek — 4/9 · Evidence: **E4, confirmed directly in this pass** — `track` state (`Home.tsx:216`) only conditionally swaps `<p className="track-description">` (`L228`); `levels`, the milestone list, and the stage-map section below all remain hardcoded to Technical-track content regardless of `track`'s value
Observation: Selecting "Customer Service" produces a visibly different paragraph but an unchanged milestone list still headed "Sign-in & Encode," "Availability & Sell," "Pricing & Ticketing" — GDS-track content, not service-track content.
Impact: The one place in the product where a user-initiated choice produces a genuinely misleading result (content that contradicts the selection made), rather than merely inert.
Risk: Moderate — trust/confusion, localized to one screen but a clear behavioral inconsistency.
Dependency: **Content-dependent** (Customer Service track milestones do not yet exist as data) for the full fix; **UI-only** for an interim honest state.
Decision: Until Customer Service content exists, either disable/label the toggle as "coming soon" for that option, or show an explicit "content in development" state instead of stale Technical-track milestones under a Customer Service selection.
Action: Interim UI-only state now; full content build deferred to whoever owns the Customer Service curriculum.
Validation: Selecting "Customer Service" never displays Technical-track-only content unlabeled as such.

---

**AB-F048 — Expandable "mastered" level cards are weakly discoverable with no `aria-expanded`**
Type: Interaction/Accessibility · Priority: **P2** · Verdict: **ACCEPT**
Sources: S-Claude(PRG-03) — 1/9, confirmed via source: `Home.tsx:229`, `level-card` `onClick` toggles `expandedLevel` for mastered/ready cards with no visible affordance (chevron/plus icon) hinting they're expandable, and no `aria-expanded` on the button
Observation: A tap-to-reveal interaction with zero visual or programmatic signal that it exists.
Impact: Low-moderate — likely under-discovered content, invisible to assistive technology regardless of discovery.
Risk: Low-moderate.
Dependency: **UI-only.**
Decision: Add a visible expand/collapse indicator and `aria-expanded`.
Action: Small icon addition + attribute.
Validation: The expandable state is visually signaled and programmatically exposed.

---

**AB-F049 — Scenarios' "Filters" button duplicates the already-functional `filter-tabs` row directly beside it**
Type: Behavioral · Priority: **P1** · Verdict: **ACCEPT**
Sources: S-Claude(SCN-02), S-Qwen(area) — 2/9, confirmed via source: `Home.tsx:335`, `filter-tabs` (All/Not started/In progress/Completed) is a genuinely working, state-driven filter; the separate "Filters" button (`SlidersHorizontal` icon) fires only `toast.info`
Observation: One of the twelve AB-F009 stub instances, called out individually here because it sits in direct visual proximity to working filter functionality, making the contrast between real and fake unusually stark on this specific screen.
Impact: Moderate — actively confusing (why does a working filter row need a separate "Filters" button?) rather than merely inert.
Risk: Moderate, localized.
Dependency: **UI-only.**
Decision: Remove the duplicate button, or repurpose it for a genuinely distinct function (e.g., difficulty/skill-tag filtering, which the current `filter-tabs` does not cover) if that scope exists.
Action: Remove or repurpose.
Validation: No two controls on Scenarios claim to do the same job.

---

**AB-F050 — Scenarios' sort `<select>` does not reorder the list**
Type: Behavioral · Priority: **P1/P2** · Verdict: **ACCEPT**
Sources: S-Claude(SCN-03), S-Qwen(AB-02) — 2/9, confirmed via source: `Home.tsx:335`, `<select onChange={() => toast.info("Mission order updated.")}>` — the handler never touches `filtered`/`scenarios` order
Observation: The three offered sort options (Recommended/Difficulty/Recent) are all fields that already exist on every scenario object (`difficulty`, implicit recency via array order) — this can be wired without new data.
Impact: Moderate — states an action completed ("Mission order updated") that did not happen.
Risk: Moderate, trust.
Dependency: **UI-only** (the fields needed already exist in `scenarios`).
Decision: Wire real sorting using existing fields; remove the false-completion toast regardless of timing.
Action: Implement actual array sorting by the selected criterion.
Validation: Changing the sort selection visibly reorders the scenario list.

---

**AB-F052 — Skill-row trend arrow color is mapped to literal direction (up/down), not to whether the trend is favorable**
Type: Visual/Logic · Priority: **P2** · Verdict: **ACCEPT**
Sources: S-Claude(GRW-01) — 1/9, confirmed via source: `skillRows` (`Home.tsx:90-96`) — `AN`/`SS` (already-mastered skills) show `trend:"down"` styled `tone:"good"` (green), because their value is settling after being learned; `FQD`/`FXP` (still-improving skills) show `trend:"up"` styled `tone:"warn"` (amber) — the arrow glyph itself (`TrendingUp`/`TrendingDown` icon) is chosen by literal direction while the *color* is chosen by favorability, so a down-arrow renders green and an up-arrow renders amber
Observation: This is a real, source-confirmed, single-audit but logically airtight finding — the icon and its color are answering two different questions (direction vs. favorability) simultaneously, which risks reading as contradictory (a downward arrow in a "good" color) even though the underlying color-coding logic is itself sound.
Impact: Low-moderate; a plausible source of momentary confusion, not a severe defect.
Risk: Low.
Dependency: **UI-only.**
Decision: Pick one consistent mapping — either the icon direction always matches its color's connotation, or replace the directional icon with a favorability-only glyph (checkmark/flag) where the two would otherwise conflict.
Action: Adjust icon selection logic for the two cases where direction and favorability currently point opposite ways.
Validation: No skill row shows a downward-trend icon in a "good"/green treatment or vice versa without the icon itself also reflecting favorability.

---

**AB-F053 — Growth Record's "Backup" button implies real data protection but performs none**
Type: Behavioral · Priority: **P1** · Verdict: **ACCEPT**
Sources: S-Claude(GRW-02), S-Qwen(AB-01), S-ChatGPT(AB-020) — 3/9, confirmed via source: `Home.tsx:343`, fires `toast.success("A local evidence backup point has been created.")` with a `ShieldCheck` icon and no underlying persistence action beyond what `localStorage` already does automatically on every assessment save
Observation: Of all twelve AB-F009 stub instances, this is the one with the highest individual severity, because "Backup" paired with a shield icon specifically implies data protection/safety — a stronger, more consequential promise than "View evidence" or "See patterns."
Impact: A trainee who believes they have created an explicit backup point may reasonably feel protected against data loss they are not actually protected against beyond the app's existing automatic (and itself unremarked-upon, single-`localStorage`-key) persistence.
Risk: Moderate-high relative to the other stub instances, given the specific "protection" implication.
Dependency: **UI-only** to remove/relabel; **Engine-dependent** to make real (actual export/backup mechanism).
Decision: Remove or relabel until real; this is the single highest-priority instance of the broader AB-F009 pattern to fix first if only one can be addressed immediately.
Action: Remove the button, or replace with an honest "Evidence auto-saves to this device" status indicator.
Validation: No control on Growth Record implies a data-protection action beyond what actually occurs.

---

**AB-F054 — Skill-row hover-preview: desktop/tablet mechanism is correctly dual-triggered (hover + keyboard focus), but content is fully unavailable on mobile, not merely harder to reach**
Type: Accessibility/Responsive · Priority: **P1/P2** · Verdict: **ACCEPT WITH MODIFICATION** *(resolves a direct cross-audit conflict — see §15.3 for full reasoning)*
Sources: S-Claude/S-Kimi (positive: correctly built with `:hover, :focus-visible` dual trigger) vs. S-Qwen(AB-11)/S-v0dev(implied)/S-DeepSeek (concerned: hover-dependent, inaccessible) — **conflict resolved in this pass by direct source verification**: `index.css`, `.skill-row-button:hover .skill-hover-preview, .skill-row-button:focus-visible .skill-hover-preview { opacity:1; ... }` **confirms** the desktop/tablet mechanism genuinely is keyboard-accessible (S-Claude/S-Kimi correct on the mechanism); `.skill-hover-preview{display:none}` inside the `max-width:739px` query **confirms** the content is not degraded-but-present on mobile, it is entirely absent (S-Qwen/S-v0dev correct on the underlying mobile-parity concern, though their "hover-only" framing of the mechanism itself was imprecise)
Observation: Two things are simultaneously true and this finding states both rather than picking a side: the *keyboard* accessibility concern raised by several audits does not hold at ≥740px (Tab-to-focus genuinely does reveal the preview); the *mobile-parity* concern does hold at <740px (there is currently no way — hover, focus, or tap — to see this content on a phone, because it is fully removed from layout).
Impact: Moderate — mobile users (the majority of the supplied screenshots' evidence) never see "Latest signal" / coach guidance content that desktop and tablet users can access via keyboard or mouse.
Risk: Moderate, mobile-specific.
Dependency: **UI-only.**
Decision: Preserve the correctly-built desktop/tablet dual-trigger mechanism exactly as-is (do not touch it). Separately, surface the preview's content through the mobile skill-detail panel (which already exists and already opens on tap — `Home.tsx:340-347`) instead of leaving it fully absent below 740px.
Action: Move (not duplicate) the hover-preview's content into the existing mobile skill-detail expansion path.
Validation: The "Latest signal"/coach-guidance content the desktop hover-preview shows is reachable by some interaction on every viewport width, including mobile.

---

**AB-F055 — Progress Tracking's route-line label truncates at mobile width ("VECTOR 03 / PRICING & T…")**
Type: Visual · Priority: **P2** · Verdict: **ACCEPT**
Sources: S-Qwen(AB-20) — 1/9 explicit, but **E4 — visually confirmed directly in the supplied S-Shots Image 3 screenshot**, and structurally confirmed in source: `index.css` mobile query sets `.tracking-route-line b { max-width:130px; overflow:hidden; text-overflow:ellipsis; white-space:nowrap; }`
Observation: The truncation is not a rendering bug — it is the CSS working exactly as written, with `max-width:130px` simply too narrow for "VECTOR 03 / PRICING & TICKETING" at the font size in use.
Impact: Low-moderate; a real, visible, screenshot-confirmed clipping defect on a label meant to orient the trainee to their current position.
Risk: Low.
Dependency: **UI-only.**
Decision: Either shorten the label's content ("PRICING & TICKETING" alone, dropping the "VECTOR 03 /" prefix on narrow widths) or widen the allotted space.
Action: Adjust the mobile `max-width` or the label's mobile-specific copy.
Validation: The full intended label (or an intentionally-shortened mobile variant) displays without mid-word ellipsis truncation at 360–430px.

---

**AB-F056/057/058 — Content-layer observations: verdict/readiness language, curriculum provenance, and interpretive claims outpace what local/illustrative evidence can support**
Type: Content · Priority: **P2/P3** · Verdict: **ACCEPT (as content-review flags, not UI defects)**
Sources: S-ChatGPT(§5.3, §5.5, and throughout — this synthesis's single strongest source for content-layer observations, consistent with S-ChatGPT reading essentially every screen's copy closely) — largely 1/9 explicit at this level of specificity, though the underlying "illustrative data should say it's illustrative" spirit connects to the 7/9-corroborated AB-F010
Observation: Three related, distinct content patterns worth flagging together: (a) `AssessmentReport`'s verdict copy ("Operationally ready," "Rebuild the sequence with guidance") uses confident, competency-framework-sounding language for output derived from a small local scoring formula, not a validated assessment instrument; (b) Growth Record's Reports tab ("Readiness is a pattern, not a single score") similarly interprets local session data in broader-sounding terms than the underlying evidence currently supports; (c) nowhere in Progression or Scenarios does any visible label connect a lesson/scenario to a named curriculum, module, or difficulty-calibration source — a trainee (or their employer) has no way to see where this content's authority comes from.
Impact: Low-moderate individually; collectively relevant to the same trust/evidence-integrity theme as AB-F010, approached from the content-copy angle rather than the data-mismatch angle.
Risk: Trust, moderate, cumulative with AB-F010.
Dependency: **Content-only** — none of this is a UI/code change; all three are copywriting and product-positioning decisions for whoever owns curriculum/assessment content.
Decision: Flag for content review rather than action here — these are outside a UI-only audit's authority to resolve, but excluding them from this report would itself violate the zero-loss-coverage rule, since they are real, repeatedly-observed patterns.
Action: None (UI-only scope); route to content/curriculum ownership.
Validation: N/A this phase.

---

**AB-F059 — No dedicated sub-360px breakpoint; the 320px floor implied by `body{min-width:320px}` relies entirely on inheritance from the 360px rules, untested**
Type: Responsive · Priority: **P2** · Verdict: **TEST BEFORE ACCEPTING**
Sources: S-Claude(GLB-15), S-ChatGPT(§8.6), several others by implication — 3-4/9 · Evidence: confirmed via source — the narrowest explicit media query found in `index.css` targets `max-width:739px`; no query targets anything narrower; `body{min-width:320px}` sets a floor with no corresponding breakpoint tuning
Observation: Real small-Android devices at 320–359px (a genuine, if shrinking, share of the Android install base) receive the same rules as a 430px phone, scaled down by nothing but the browser's own reflow.
Impact: Unknown until tested — could be fine (the 360px rules may simply continue to work acceptably) or could produce real crowding, particularly in the terminal header and KPI grids, which are already tight at 360-390px per several audits' analysis.
Risk: Low-moderate, unconfirmed.
Dependency: **UI-only.**
Decision: **TEST BEFORE ACCEPTING.**
Action: None until tested.
Validation: Render at exactly 320px width; check the terminal header, KPI grids, and bottom-nav for clipping or overlap. Add a dedicated `max-width:359px` (or similar) query only if the test reveals a real problem.

---

### 5.6 Resolved conflicts, promoted to findings in their own right

*(Full reasoning and cascade trace for each lives in §15; each is also listed here because — per the prompt's own methodology — a resolved conflict is itself a piece of durable knowledge worth recording, not a footnote to discard once resolved.)*

---

**AB-F025 — RESOLVED (REJECTED): `.bottom-nav` does not actually render 5 items into a 4-column grid, and `.is-primary` is not dead styling**
Type: Conflict resolution · Verdict: **REJECT the original claim; ACCEPT the underlying code-hygiene observation as AB-F040**
Source of original claim: S-v0dev(F-02). Full cascade trace: §15.1. The base 4-column rule (`index.css:119`) is superseded by three later, higher-or-equal-specificity rules (`:313`, `:319`, `:375!important`), all declaring 5 columns; `.bottom-nav button.is-primary` is fully styled at `:376`. The rendered result — confirmed against the supplied screenshots, which show a correct 5-item, evenly-spaced bottom nav with a visibly distinct center item — matches the 5-column cascade outcome, not the 4-column base rule S-v0dev cited.

---

**AB-F026 — RESOLVED (REJECTED, with a preserved secondary observation): the terminal session readout is not actually hidden on mobile in the final rendered cascade**
Type: Conflict resolution · Verdict: **REJECT the original claim as stated; the underlying CSS-layering complexity is worth noting as a maintainability pattern**
Sources of original claim: S-v0dev(F-09), S-Kimi. Full cascade trace: §15.2. An early, mobile-scoped rule (`index.css:242`, inside a `max-width` query) does set `.terminal-session-readout{display:none}` — this part of both audits' citation is accurate. But a later, unconditional, higher-specificity rule (`.page-practice .terminal-session-readout{display:flex;...}`, part of the un-media-queried "AeroBridge Elevation Directive" block) overrides it and continues to be refined at two further breakpoints (`:382`, `:404`) — none of which touch `display`, meaning the readout stays visible at every width once the Elevation Directive layer is in effect. The secondary observation worth keeping: this is the *second* instance (alongside AB-F025) of the same underlying pattern — an earlier, simpler rule being fully superseded by a later, more specific one — which is exactly the kind of layering that makes a stylesheet hard to audit by eye and is itself a mild argument in favor of AB-F008/AB-F038's consolidation recommendations.

---

**AB-F027 — RESOLVED (REJECTED): the terminal caret's blink animation does respect `prefers-reduced-motion`**
Type: Conflict resolution · Verdict: **REJECT**
Sources of original claim: S-Manus(AB-13), S-Kimi(T09). Confirmed directly in this pass: beyond the global catch-all (`index.css:123`, `*, *::before, *::after{animation-duration:.001ms!important; transition-duration:.001ms!important; scroll-behavior:auto!important}`), a second, specifically-targeted rule exists at `index.css:217`: `@media (prefers-reduced-motion: reduce) { .history-list button, .terminal-caret { transition: none; animation: none; } }` — `.terminal-caret` is named explicitly. Both the global catch-all (covering `animation-duration` and `scroll-behavior` universally) and this component-specific rule (covering the full `animation` shorthand, i.e., `animation-name`, specifically for the caret) independently disable the blink under reduced motion.

---

**AB-F028 — CONFIRMED POSITIVE: `prefers-reduced-motion` coverage is genuinely comprehensive, not merely claimed**
Type: Confirmed strength · Verdict: **ACCEPT as a strength — see §12 Keep/Preserve**
Sources: S-Claude, S-Grok, S-DeepSeek, S-v0dev, S-ChatGPT all independently praised this; **directly re-confirmed in this pass**: 13 separate `@media (prefers-reduced-motion: reduce)` blocks exist across the stylesheet (a global catch-all plus 12 component-scoped refinements covering history-list/terminal-caret, terminal-entry/terminal-body scroll, reference-drawer, assessment-report, seven interactive-element transition groups, skill-hover-preview/tracking-bar/tracking-row, tab-enter/growth panels, tracking-bar/signal-sweep, tracking-KPI opacity, growth/scenario detail panels, and a final block covering additional terminal-practice-scoped elements), directly contradicting the two specific claims in AB-F027 above and corroborating the positive assessment from five of the nine source audits.

---

## 6. DESIGN SYSTEM DECISIONS

**Typography.** Confirm font loading before any other typography work (AB-F004) — this is a blocking dependency because every subsequent visual measurement (line length, wrapping, perceived size) depends on which font is actually rendering. Once confirmed: consolidate the two token layers (AB-F008) so type tokens are defined once; establish a small, explicit type scale rather than the current wide spread of discrete pixel sizes documented independently by S-Kimi and S-v0dev (8–27px+ observed across the file with no consistent step pattern); raise the smallest instructional/reading text sizes at mobile width specifically — S-v0dev's independently-computed recommendation (≥13–14px desktop terminal body, ≥14px mobile, rather than the current 11px→10px sequence) is a reasonable target, offered as a starting point for whoever implements rather than a mandate, since exact numbers were not independently re-verified pixel-by-pixel in this pass beyond the terminal body specifically.

**Color.** Consolidate `--ab-*` into the base token set as canonical (AB-F008); fix the two confirmed AA failures (AB-F005 primary-button, AB-F006 text-faint) as part of the same pass, since both are token-value changes; do not introduce a third color-token layer while performing this consolidation — extend the existing `--ab-*` naming outward rather than starting over.

**Surfaces, borders, elevation.** No cross-audit finding challenges the current surface/border/shadow system — every audit that commented on it treated the layered-navy, subtle-border, soft-shadow language as a genuine strength (see §12). No decision required here beyond what AB-F038's spacing/radius consolidation already covers incidentally.

**Spacing and radius.** Define and migrate toward a small explicit scale per AB-F038, opportunistically (during other work already touching a component) rather than as a dedicated sweep — the current values are inconsistent but not currently visible as broken, so a disruptive standalone pass is not justified by the evidence.

**Components — states.** Every interactive component needs, at minimum, defined hover/focus-visible/active/disabled states before the ARIA work in AB-F007 is implemented, since visual state and programmatic state should be authored together rather than sequentially (per the sequencing already specified in Critical Decision 4, §4). `.terminal-finish:disabled{opacity:.45}` is the one confirmed example of a disabled state currently in the codebase — a reasonable pattern to extend, not replace.

**Motion.** No decision needed beyond what AB-F017 (fixed terminal-gap) and AB-F041 (chart animation re-trigger, single-source, low-priority) already cover — the reduced-motion system itself (AB-F028) is a confirmed strength to preserve exactly as-is (§12).

**Accessibility tokens.** Not currently a distinct category in the codebase; the AB-F007/AB-F008 sequencing in Critical Decision 4 effectively creates one as a byproduct (consistent focus-visible treatment alongside consistent tab semantics) rather than requiring a separate initiative.

**Responsive tokens.** No fluid-typography (`clamp()`) system currently exists for body/UI text (a small number of headings use `clamp()` already — `.assessment-report h2`, confirmed in source — but this is not extended systemically). Not a required fix; noted as an option for whoever addresses AB-F059's 320px testing, since fluid type could reduce the number of discrete breakpoint-specific size overrides currently needed.

**Arabic/RTL tokens.** Explicitly gated behind the AB-F003 scope decision (§4, Critical Decision 3). If/when built: `dir="rtl"` at the document root, full layout mirroring (the CSS currently uses very little logical-property notation — `margin-left`/`padding-left` appear more often than `margin-inline-start`/`padding-inline-start` in the sampled sections — meaning a real RTL pass would need a genuine mirroring effort, not a `dir` flip alone), `--font-ar` applied to Arabic text specifically, and `unicode-bidi: isolate` around embedded LTR content (GDS commands, airline/airport codes) inside RTL prose, per S-Gemini's specific, technically correct recommendation.

**Data visualization.** The Progress Tracking chart's `role="table"` alternative (confirmed in source, `<details><summary>View data table</summary><div role="table">...`) is the strongest accessible-data-viz pattern in the codebase and should be the template for any future chart, not modified. One incremental addition worth considering, raised independently by S-Grok: a short text-summary sentence of the trend (e.g., "Trending down 6 points since last session") alongside the existing table, giving screen-reader users the *headline* without needing to step through the full table — low-cost, additive, does not touch the existing working pattern.

---

## 7. GLOBAL UX DECISIONS

**Navigation.** Keep the mobile bottom-nav reorder (AB-F043) — it correctly serves the deliberate Practice-centering intent — but document it. Fix the "Route" terminology overload (AB-F044). Resolve the hamburger-drawer duplication (AB-F045) via product decision (give it distinct content, or remove it) rather than leaving it as a pure duplicate. Add the missing `aria-label` to the desktop side-`<nav>` to match the bottom-nav's existing, correct pattern (part of AB-F015c).

**Information architecture.** No structural IA problems were found — the five-screen loop (Progression → Practice → Scenarios → Growth → Tracking) is coherent and every audit treated it as a genuine strength. The one IA-adjacent issue is content-provenance (AB-F057/058): nothing currently shows where curriculum content comes from or how it's calibrated, which is a content-authoring gap, not a structural one.

**CTA hierarchy.** Broadly sound and consistent (primary/ghost/text-action three-tier system, applied consistently) — the one defect is contrast (AB-F005), not hierarchy or placement.

**Feedback and toasts.** The toast system is over-relied-upon in two specific, distinct ways that should be fixed together as one pattern change: (a) as a substitute for real functionality (AB-F009/AB-F049/AB-F050/AB-F053 — twelve stub instances); (b) as a redundant third channel for information already shown persistently elsewhere (AB-F013, per-command toasts). Reserve toasts for events that genuinely lack an existing persistent home.

**Discoverability.** Two specific discoverability gaps: expandable level cards with no visual affordance (AB-F048); the mobile skill-hover-preview content gap (AB-F054, already resolved with a specific fix). No broader discoverability problem was found — icons are consistently paired with text labels throughout, which several audits noted positively.

**Interaction patterns.** Consistent tap/click targets are used correctly almost everywhere except the specific, measured touch-target-size instances in AB-F014. Command-history keyboard recall (Arrow Up/Down in the terminal input) is a genuine, well-built power-user feature — confirmed in source (`Home.tsx:265-271`) — that is accessibility-labeled (`aria-label` documents the shortcut) but has zero *visual* affordance hinting it exists, a minor gap worth a small icon/hint addition, raised by S-Manus, not urgent enough for its own AB-F number given its low severity.

**System-state communication.** The three-live-readout pattern in the terminal header (SESSION/COMMAND/LOG) is a genuine strength once AB-F026's cascade confusion is understood (the readout is, in the final rendered result, visible at every width) — no change needed to the mechanism itself. The one real gap is non-color redundancy for error *kinds* specifically in the terminal history rows: currently, entries are differentiated by text content and by `.terminal-success`/`.terminal-error` color classes, but not by a consistent iconographic or text-prefix system across the three error kinds (syntax/sequence/decision) the way the Assessment debrief's legend already does — S-Grok's specific recommendation (short prefixes like `OK`/`SEQ`/`SYN`/`DEC` on each history line) is a reasonable, low-cost way to extend a pattern the product already uses elsewhere (the legend) into the live terminal history itself.

---

## 8. TERMINAL / WORKSTATION DECISIONS

The Terminal's architectural centrality is correct and confirmed (§12) — every decision here is refinement, not restructuring.

**Immediate (P0), before any other Terminal work:** AB-F001 (fabricated default error) and AB-F002 (empty-submit-to-FQD). Both ship alone, each independently screenshot-verifiable.

**High-priority refinement:** AB-F012 (hint/history state bleeding across modes — ship the transparency mitigation now, defer the scoring-model question); AB-F015b (drawer/popover dialog semantics, shared pattern); AB-F018 (Focus Mode keyboard trap, distinct from and additional to the already-correct scroll-lock).

**Moderate refinement:** AB-F013 (redundant per-command toasts); AB-F014 (auto-scroll to latest entry); AB-F017 (fixed decorative gap, worst on first load); AB-F033 (Reference-drawer hint semantics — increments the same counter in Learn and Practice with no visual distinction between "viewing" and "using" a hint, a nuance worth a small copy/visual treatment once AB-F012's broader transparency mitigation ships, not before).

**Low-priority / defer:** AB-F015 (dual prompt/caret — test before changing); AB-F016 (session-timer seed value); AB-F035 (two-step Finish Session confirmation, raised by S-Kimi — evaluated and **not recommended**: `FINISH SESSION` is already `disabled` until `commandHistory.length > 0`, meaning accidental empty-session submission is already prevented at the point that matters; adding a confirmation step on top adds interaction cost to the single most consequential action in the product's core loop without addressing a demonstrated problem — this is exactly the kind of "additional friction without evidenced benefit" the audit brief's Overdesign Defense exists to catch, and it is rejected here on those grounds, not merely deprioritized).

**Confirmed working, do not touch:** the `body:has(.focus-mode){overflow:hidden}` scroll-lock (modern, correct, confirmed in source); the sticky mobile input positioned above the safe-area inset (confirmed, purpose-built); the 16px input font-size (confirmed — defeats iOS Safari's automatic zoom-on-focus, a real and easily-missed mobile detail); the reduced-motion coverage (AB-F028, confirmed comprehensive).

---

## 9. LEARNING UX DECISIONS

Evaluated against the operational-competence framework the audit brief specifies (not a generic gamified-app lens): does the product help a trainee build real, verifiable operational skill, or does it optimize for engagement/completion signals that look good but don't necessarily indicate competence?

**Working well, by this standard.** The Learn → Practice → Assessment progression genuinely separates guided exploration from evaluated performance — Assessment mode suppressing hints (confirmed: `mode==="assessment"` gates the `hintCount` increment) and using different, more clinical Coach copy (`"Hints stay quiet in Assessment mode. Review the returned status and explain the next operational decision in your own words."`) is a real, evidenced design choice that matches how operational training actually works, not a cosmetic mode label. The error taxonomy (syntax/sequence/decision, confirmed as a real, if incompletely-realized — see AB-F022 — three-category system) reflects genuine domain thinking about *why* a GDS command fails, not a generic right/wrong binary. The recommendation engine in `AssessmentReport` (`Home.tsx:235`) genuinely branches on which of accuracy/sequencing/hint-discipline is weakest and recommends a *different* next action accordingly — real differentiated feedback, not a templated "good job" / "try again."

**Where the operational-competence framework surfaces real gaps**, distinct from the pure UI findings above: AB-F012's mode-bleeding issue is not just a UI transparency problem but a genuine assessment-validity concern — if hints taken during exploratory Learn-mode use count toward an Assessment "hint discipline" score, the score no longer cleanly measures what it claims to measure. This is the single finding in this report where a UI-level fix (the transparency mitigation) and a training-design-level question (should scores ever mix modes?) are genuinely separate, and only the first is in scope here. AB-F022's dead `"hint-dependency"` category is a second, smaller instance of the same theme: the taxonomy was designed for a richer signal (repeated hint use indicating a specific competence gap) than the current logic actually captures.

**Content-authority gap** (AB-F057/058, restated here in learning-design terms): a real operational-training product typically anchors its content to a named curriculum, certification body, or calibration source a learner (or their employer) can verify against. Nothing in the current prototype does this — every score, milestone, and recommendation is presented with full confidence but no visible provenance. This does not need to be fixed by adding fake-sounding credentialing language; it needs a decision from whoever owns the curriculum about what, if anything, this product's numbers are calibrated against, and that decision should inform copy throughout Progression, Scenarios, and Growth simultaneously rather than screen-by-screen.

**Decision:** No learning-UX finding in this section requires an engine change beyond what §5's individual findings already specify. The recommendation is sequencing, not new scope: treat AB-F012 as the priority learning-UX fix (it is already P1 for UI purposes and doubles as the one finding with genuine assessment-validity stakes), and route the content-provenance question to curriculum ownership rather than attempting a UI-only fix that cannot actually resolve it.

---

## 10. RESPONSIVE DECISIONS

*Desktop, tablet, and mobile are treated separately per the audit brief's explicit requirement — collapsing them into one generic "responsive" note would hide the exact tablet-range mismatch this section exists to surface.*

### 10.1 Desktop (≥1100px, where the side-nav/bottom-nav swap occurs)

No structural defects were found at this range by any of the nine source audits or this synthesis pass. The persistent side-nav, multi-column grids (`progression-layout`, `scenario-layout`, `practice-layout` all confirmed using generous `minmax()`-based column splits), and sticky coach panel (`position:sticky; top:93px`, confirmed) are all sound, confirmed patterns. The one desktop-specific gap is AB-F015c's missing side-`<nav>` label — a one-line accessibility fix, not a layout change. No visual desktop screenshots were supplied to this synthesis pass; this assessment rests on source/CSS reading alone and should be spot-checked live before being treated as fully closed.

### 10.2 Tablet (740–1099px)

This is the range with the one genuinely uncertain structural finding: AB-F046's content/navigation breakpoint mismatch (content grids shift at 740px; nav chrome stays mobile-style until 1100px). **Test before accepting** — this synthesis's confidence is high on the *structural fact* (confirmed via source) and low-to-moderate on whether it constitutes a real user-facing problem, since no tablet-width screenshot exists to confirm the felt experience. This should be the first thing checked with a live render, ahead of any tablet-specific fix being written.

### 10.3 Mobile (≤739px, the width every supplied screenshot represents)

The range with the most confirmed, verified findings, precisely because it is the only range with direct visual evidence. Confirmed-correct despite initial cross-audit disagreement: the bottom-nav column count (AB-F025, resolved) and the terminal session readout's visibility (AB-F026, resolved) both render correctly in the final cascade. Confirmed-real defects specific to this range: the touch-target sizes in AB-F014 (icon-button sequence 38→35→33px, all below the 44px WCAG 2.5.5 target); the route-line label truncation in AB-F055 (visually confirmed); the fully-absent (not degraded) skill-hover-preview content in AB-F054; the untested 320px floor in AB-F059. The deliberate mobile-specific engineering already in place — sticky input above the safe-area inset, 16px input font defeating iOS zoom, the two-row terminal-header restructuring at 360px with its own explanatory code comment, the intentional bottom-nav item reorder centering Practice — should all be preserved exactly as-is; none of the findings above require touching any of these confirmed-working mechanisms.

---

## 11. ACCESSIBILITY DECISIONS

*Consolidating every accessibility-tagged finding from §5 into one prioritized view, since accessibility work is more effective planned as a coherent pass than as scattered individual fixes.*

**P0/P1 — foundational, sequence first:** AB-F007 (zero tab/toggle ARIA semantics across five control groups — the single largest accessibility gap by surface area) and AB-F008 (token consolidation it depends on structurally, per Critical Decision 4). AB-F011 (pinch-zoom, test-before-accepting given severity if confirmed). AB-F015b/c (dialog semantics + landmark/skip-link gaps — five related, individually small fixes with one shared implementation pattern each).

**P1/P2 — real but narrower in scope:** AB-F005/AB-F006 (the two confirmed AA contrast failures). AB-F018 (Focus Mode keyboard trap). AB-F024 (AnimatedBar progressbar semantics). AB-F054's mobile-parity half (content availability, not the already-correct keyboard mechanism).

**Confirmed working — the accessibility strengths to build the above around, not replace:** the Progress Tracking `role="table"` data alternative (the strongest single accessibility artifact in the codebase); the `aria-live="polite"` regions on the terminal history and assessment report (2 confirmed instances, correctly scoped); the reduced-motion system (AB-F028); the existing 17 `aria-label`/4 `aria-hidden` instances, which are, where present, correctly and thoughtfully applied — this is not a codebase with no accessibility awareness, it is one with real, demonstrated awareness applied unevenly, which is a materially easier problem to close than starting from zero.

**Sequencing recommendation specific to this section:** do the landmark/skip-link/dialog-semantics fixes (AB-F015b/c) first, since they are fully independent of the token-consolidation work; do the tab-semantics work (AB-F007) after token consolidation (AB-F008), per Critical Decision 4; do the contrast fixes (AB-F005/AB-F006) as part of the same token pass since they touch the same values. This produces one coherent accessibility-and-token pass rather than accessibility work scattered across multiple later phases.

---

## 12. SCREEN-BY-SCREEN AUDIT

### 12.1 Progression (`page-progression`)

**Strengths:** The hero "continue where you left off" card is the correct pattern for a returning-user home state — confirmed real data binding (`levels[2]`'s progress genuinely drives the ring and the "6 of 9 command sets" figure). The milestone list's done/current/locked visual states are clear and consistent. `ProgressRing` is a well-built, animated, accessible (`role="img"` with a computed `aria-label`) component reused correctly across three screens.

**Critical problems:** AB-F010's "3/8 stages" mismatch (visible in S-Shots Image 7) is the most prominent defect on this screen — it is the very first number a returning trainee sees. AB-F047's track-toggle content mismatch is the screen's second-most-significant issue.

**Required changes:** Fix AB-F010's stage-count derivation; resolve AB-F047 (interim honest state at minimum); add `aria-expanded` per AB-F048.

**Optional improvements:** None beyond what §5/§6 already specify.

**Responsive requirements:** Confirmed working at mobile width (S-Shots Image 7); desktop grid confirmed sound via source; no screen-specific responsive defect beyond the general AB-F014/AB-F059 patterns.

**Accessibility requirements:** AB-F007 (track-tabs), AB-F048 (expand affordance).

**Priority:** P1 (driven by AB-F010 and AB-F047, both confirmed, both visible on first view).

**Dependency:** UI-only for the interim fixes; Content-dependent for AB-F047's full resolution.

**Do-not-touch:** The hero card layout, the `ProgressRing` component, the milestone-list visual states, the deliberate "6 stages, 8-segment decorative indicator" split *concept* (only the label needs to match the data, not the decorative-segment approach itself).

---

### 12.2 Practice / Terminal (`page-practice`)

**Strengths:** This is the product's best-built screen and should be the template other screens are measured against, not the other way around — genuinely wired state machine (Learn/Practice/Assessment modes each producing materially different Coach copy and behavior, confirmed in source), real command parsing with four distinct, domain-accurate response profiles (AN/SS/FQD/FXP), a real scoring formula weighting accuracy/sequencing/hint-discipline, Focus Mode as a genuinely distinct, purpose-built state (not a CSS class toggle pretending to be a mode), and the strongest mobile-specific engineering in the codebase (sticky safe-area-aware input, 16px zoom-defeating font size, purpose-commented two-row header restructuring).

**Critical problems:** AB-F001 (fabricated default error) and AB-F002 (empty-submit) both live here and are both P0 — this screen carries the two highest-priority findings in the entire report, appropriately, given it is also the product's most important screen.

**Required changes:** AB-F001, AB-F002 (P0); AB-F012 transparency mitigation, AB-F015b drawer/popover semantics, AB-F018 focus trap (P1).

**Optional improvements:** AB-F013 (redundant toasts), AB-F014 (auto-scroll), AB-F015 (dual prompt — test first), AB-F016 (timer seed), AB-F017 (fixed gap), AB-F033 (hint-viewing distinction).

**Responsive requirements:** Confirmed sound at mobile width once AB-F026's cascade-confusion is understood as a non-issue; the sticky-input/safe-area/16px-font mobile engineering should be explicitly preserved during any other Terminal work.

**Accessibility requirements:** AB-F007 (mode-tabs), AB-F015b (reference-drawer as popover-like surface), AB-F018 (Focus Mode trap), the command-history keyboard-recall visual affordance noted in §7.

**Priority:** **P0** — the single highest-priority screen in the product.

**Dependency:** UI-only for every required change; the one deferred item (AB-F012's root scoring-model question) is explicitly out of this audit's scope.

**Do-not-touch:** The command-matching/scoring logic itself (out of scope by the audit brief's own Engine/UI boundary); the Focus Mode scroll-lock mechanism; the mobile input engineering; the four-branch command-response content (AN/SS/FQD/FXP), which is domain-accurate and should not be simplified.

---

### 12.3 Scenarios (`page-scenarios`)

**Strengths:** The list/detail split pattern is clean and scales well; the scenario-card component correctly shows progress/completion state; the detail panel's "Coach readout" copy correctly varies by scenario state (ready/active/verified, confirmed in source: `Home.tsx:335`); starting a scenario correctly hands off real context (`setPracticeContext(selected.title)`) into Practice.

**Critical problems:** AB-F010's "23/40 + non-existent Exchanges & Refunds category" is the most visible defect on this screen (confirmed in S-Shots Image 6) and should be fixed alongside Progression's instance in the same pass, since both are the same underlying pattern.

**Required changes:** AB-F010 (this screen's instance); AB-F049 (duplicate Filters button); AB-F050 (non-functional sort).

**Optional improvements:** AB-F051 (long-title clipping risk in the task-strip handoff — flagged by S-Claude as needing live validation with genuinely long titles, not confirmed as a live defect in this pass).

**Responsive requirements:** Confirmed sound at mobile width (S-Shots Image 6); no screen-specific defect beyond general patterns.

**Accessibility requirements:** AB-F007 (filter-tabs).

**Priority:** P1 (driven by the same illustrative-numbers pattern as Progression, plus the two dead controls).

**Dependency:** UI-only for AB-F049/F050; the count-derivation half of AB-F010 is UI-only, the "should 40 be real" half is content-dependent.

**Do-not-touch:** The list/detail split; the scenario-card component; the context-handoff mechanism into Practice.

---

### 12.4 Growth Record (`page-growth` — Record / History / Reports tabs)

**Strengths:** The three-tab structure genuinely organizes distinct content (current state / historical log / interpretive summary) rather than being a decorative split; the Strengths/Needs-attention two-column skill breakdown is clear and correctly data-driven from `skillRows`; the skill-detail expansion panel (tap a skill row, see a trace) is a real, working drill-down interaction.

**Critical problems:** AB-F010's "LOG 04/12" mismatch (confirmed in S-Shots Image 2, History tab) and AB-F053's "Backup" button (the single highest-severity instance of the twelve stub-control findings, given its specific data-protection implication).

**Required changes:** AB-F010 (this screen's instance); AB-F053; AB-F054 (mobile skill-preview content gap — the fix, moving content into the already-existing detail panel, lives entirely on this screen).

**Optional improvements:** AB-F052 (trend-arrow color/direction mapping); AB-F056/057 (Reports-tab verdict language — content-review flag, not a UI action item this phase).

**Responsive requirements:** Confirmed sound at mobile width across all three tabs (S-Shots Images 1, 2, 4); AB-F042's `.is-secondary-view` mechanism confirmed working correctly (folds into the AB-F007 tab-pattern work, no standalone action).

**Accessibility requirements:** AB-F007 (growth-tabs); AB-F042 (folded into AB-F007); AB-F024 (AnimatedBar, used extensively on this screen for every skill bar).

**Priority:** P1.

**Dependency:** UI-only throughout.

**Do-not-touch:** The three-tab content structure; the Strengths/Needs-attention split; the skill-detail drill-down mechanism; the `.is-secondary-view` hide-inactive-tab-content approach itself (correct in principle, just needs to be paired with real ARIA per AB-F007/AB-F042).

---

### 12.5 Progress Tracking (`page-tracking`)

**Strengths:** This is the screen with the codebase's single best accessibility artifact (the `role="table"` chart alternative, genuinely wired to the same `records` data the bars render) and should be held up as the internal reference pattern for any future data visualization, not modified. The metric-switcher (Overall/Accuracy/Sequencing) correctly re-renders the chart, KPIs, and trend language together from one underlying `metric` state — a well-built, genuinely reactive small feature. The assessment-history list correctly hands off real context into Practice on tap.

**Critical problems:** AB-F055's route-line truncation (visually confirmed in S-Shots Image 3) is this screen's most visible defect.

**Required changes:** AB-F055.

**Optional improvements:** AB-F039 (KPI decorative clip-path simplification); AB-F041 (chart re-trigger on metric switch, single-source, low-priority); the S-Grok text-summary-alongside-table addition noted in §6.

**Responsive requirements:** Confirmed sound at mobile width (S-Shots Image 3) except AB-F055; the KPI grid correctly reflows to 2 columns at mobile width (confirmed in source and screenshot).

**Accessibility requirements:** AB-F007 (metric-switcher, if treated as tab-like — see the aria-pressed-vs-aria-selected distinction noted in AB-F007's Decision).

**Priority:** P2 (this screen has the fewest and least severe confirmed defects of the five — a genuine strength worth stating plainly, not just implying by omission).

**Dependency:** UI-only throughout.

**Do-not-touch:** The `role="table"` chart alternative (do not modify without preserving this exact pattern or an equal-or-better replacement); the metric-switcher's reactive data binding; the assessment-history-to-Practice handoff.

---

## 13. KEEP / PRESERVE

*These are confirmed strengths, converged upon by multiple independent audits and, in every case marked, directly re-verified against source in this pass. Nothing in §5–§12 recommends touching any of the following, and this section exists specifically so that revision work does not accidentally erode them in the course of fixing something else nearby.*

1. **The Flight Deck Console visual identity as a whole** — deep-navy foundation, restrained accent-color use, monospace terminal typography, terminal-first architecture. Every one of the nine source audits treated this as the product's defining strength. Preserve exactly.
2. **The Terminal's architectural centrality** — first in document order, full-width, the only screen with its own later-pass token refinement (`--ab-*`), the only nav item with deliberate mobile visual emphasis (confirmed: `.is-primary` styling, §15.1). Any future screen added to this product should be evaluated against whether it respects this hierarchy, not treated as a peer of the Terminal.
3. **The `body:has(.focus-mode){overflow:hidden}` scroll-lock** — confirmed in source, a modern, correct, minimal-JS use of `:has()`. Add the missing keyboard focus-trap (AB-F018) *alongside* this, never replace it.
4. **The Progress Tracking `role="table"` chart alternative** — confirmed genuinely wired to the same data as the visual bars, not a decorative stub. The single best accessibility pattern in the codebase; use it as the template for any future chart.
5. **The reduced-motion system** — a global `!important` catch-all plus 13 confirmed component-scoped refinements, including an explicit, correct override for the terminal caret specifically. Confirmed via direct source inspection to be more thorough than the claims made against it (AB-F027, resolved).
6. **Real cross-screen state**, not a mockup pretending to connect — `localStorage`-backed progress records, genuine `setPracticeContext` handoff from every "next action" button, Assessment completion immediately reflected in Growth and Tracking. This is a substantial, correctly-built piece of product architecture and the foundation everything else in this report assumes will keep working.
7. **The Learn/Practice/Assessment mode distinction as a concept** — genuinely different Coach copy, genuinely different hint-visibility rules, matching how real operational training separates guided practice from evaluation. Fix the state-bleeding (AB-F012) without flattening the conceptual distinction that makes the three modes worth having.
8. **Deliberate, evidenced mobile engineering** — 16px input font (defeats iOS auto-zoom), sticky input above the safe-area inset, the purpose-commented 360px two-row terminal-header restructuring, and the intentional (not accidental) bottom-nav item reorder. All confirmed in source; all should be explicitly called out to anyone doing further mobile work so they are recognized as intentional rather than "cleaned up" by accident.
9. **The command-history keyboard-recall feature** (Arrow Up/Down in the terminal input) — a genuine, correctly-labeled power-user feature. Add a small visual affordance (§7) without changing the underlying mechanism.
10. **The error-taxonomy concept** (syntax/sequence/decision) — real, domain-accurate categorization of *why* a command fails, not a generic pass/fail binary. Complete it (AB-F022) rather than simplify it.

---

## 14. DO NOT DO

*Specific recommendations that surfaced somewhere across the nine source audits or could plausibly be proposed next, evaluated against the Overdesign Defense and rejected here with reasoning — so a future implementer does not re-propose them without knowing they were already considered and declined.*

1. **Do not add a two-step confirmation to "Finish Session."** (Raised by S-Kimi.) `FINISH SESSION` is already disabled until at least one command has been submitted, which already prevents the specific accidental-empty-submission scenario a confirmation step would guard against. Adding friction to the single most consequential action in the product's core loop, without a demonstrated problem it solves, is exactly the pattern the audit brief's Overdesign Defense exists to catch. **Rejected.**
2. **Do not build partial Arabic/RTL support this phase.** (Implied by treating AB-F003 as a routine build task rather than a scope decision.) A `dir="rtl"` flip without full logical-property layout mirroring, embedded-LTR bidi isolation for GDS commands, and real translated content would produce a second instance of exactly the "looks done, isn't" pattern this entire report exists to correct elsewhere. **Rejected as a build task this phase; accepted as a scope decision (§4, Critical Decision 3).**
3. **Do not add a fourth visual layer of decorative motion, texture, or gamification to Progress Tracking or any other screen.** Several of the nine source audits, taken together, converge on "this product should feel more like a serious workstation and less like a consumer app" — the KPI clip-path ornamentation (AB-F039) is flagged for *simplification*, not for being joined by more of the same. Any future proposal to add badges, confetti, streak-flame icons, or similar consumer-app gamification devices should be weighed explicitly against this product's stated professional-workstation identity before being built, not adopted by default because such patterns are common elsewhere.
4. **Do not consolidate the two token systems (AB-F008) by deleting the newer `--ab-*` layer and keeping only the base tokens.** The `--ab-*` layer reads as the more deliberate, more recent refinement (its own code comment states an explicit intent: "prioritize Terminal, calm precision, and operational readability"). Consolidate by extending it outward, not by reverting to the older, less-refined values.
5. **Do not attempt to fix AB-F002 (empty-submit) by disabling the Execute button/form submission entirely when the input is empty**, if that would also prevent the Arrow-Up/Down history-recall interaction from working while the input is empty (a trainee reviewing history before deciding what to type next). The fix should reject *submission* of an empty command, not disable the input or its surrounding controls.
6. **Do not treat every one of the twelve AB-F009 stub controls identically.** They range from low-stakes ("View map" on a feature that may not exist yet) to high-stakes ("Backup," which specifically implies data protection). A single blanket fix (e.g., "remove all toast-only buttons") would under-prioritize the ones that matter most and over-prioritize the ones that don't; §5.2/§12 already sequence them individually — follow that sequencing rather than batching them.
7. **Do not rebuild or replace the command-matching/scoring engine as part of this UI revision pass.** Every finding in this report that touches behavior (AB-F002, AB-F012) has an explicitly UI-only-safe interim fix specified precisely so that engine work is never a prerequisite for shipping this report's recommendations. Proposals to "just fix the scoring model while we're in there" should be treated as a separate, later initiative.

---

## 15. CONFLICTS RESOLVED

*Full reasoning for every direct factual disagreement found among the nine source audits. Each was resolved by tracing the actual CSS cascade or source logic in this pass — not by majority vote, source reputation, or splitting the difference — per the audit brief's explicit conflict-resolution methodology.*

### 15.1 Does `.bottom-nav` render 5 items into a 4-column grid, with dead `.is-primary` styling?

**Claim (S-v0dev, F-02):** Yes — a bug. Five `orderedItems` render into `grid-template-columns: repeat(4, 1fr)` (cited at `index.css:118`), causing the fifth button to wrap or distort the bar; `.is-primary` is applied in `Home.tsx` but has no corresponding CSS rule, making it dead styling intent.

**Trace performed in this pass:** `grep -n "grid-template-columns" index.css` returns four `.bottom-nav`-relevant declarations, in source order: `:119` (`repeat(4,1fr)`, the rule S-v0dev cited), `:313` (`repeat(5,minmax(0,1fr))`, unconditional — not inside any media query), `:319` (`repeat(5,minmax(0,1fr))`, inside a media query, redundant with `:313`), `:375` (`repeat(5,minmax(0,1fr))!important`, inside a media query). Because `:313` shares identical selector specificity with `:119` (both are the single class selector `.bottom-nav`) and appears later in source order, it wins the cascade for every viewport where both rules are in scope — which, since `:119` is not itself inside any media query either, is effectively everywhere. `.bottom-nav button.is-primary` **is** styled, at `:376`: `{ color: #f4f7ff; background: rgba(74, 104, 206, .22); box-shadow: inset 0 2px 0 #7697ff; }`.

**Resolution: REJECT the original claim.** The rendered result is 5 columns with fully-functional `.is-primary` styling — confirmed both by the cascade trace and by the supplied screenshots, which show a correctly-spaced 5-item bar with a visually distinct center item. S-v0dev found a real rule but did not trace forward to the three later rules that supersede it. **Promoted to AB-F025** (resolved-conflict record) and **AB-F040** (the underlying code-hygiene observation — four redundant declarations, real but purely a maintainability concern, not a user-facing defect).

### 15.2 Is the terminal session-state readout hidden (`display:none`) on mobile?

**Claim (S-v0dev F-09, S-Kimi):** Yes — `.terminal-session-readout{display:none}` inside a mobile media query hides SESSION/COMMAND/LOG entirely below 739px, contradicting other audits' claim that session state is visible "within seconds" on all devices.

**Trace performed in this pass:** The claim's cited rule is real: `index.css:242`, inside a `max-width` media query, `.terminal-session-readout{display:none}`. But a separate, later, unconditional block — headed by the comment `/* AeroBridge Elevation Directive... */` and containing a fresh, non-media-queried `:root{}` plus a series of `.page-practice`-scoped rules — includes `.page-practice .terminal-session-readout{display:flex; flex-wrap:wrap; justify-content:flex-end; gap:6px 12px; color:var(--ab-text-muted); ...}` at `:351`, with no media-query wrapper. Because `Practice`'s root element carries the class `page-practice` (confirmed: `Home.tsx:297`), and `.page-practice .terminal-session-readout` (two classes, specificity 0,0,2,0) is more specific than the plain `.terminal-session-readout` (one class, specificity 0,0,1,0), this rule overrides the `display:none` rule **at every viewport width**, including mobile. Two further mobile-scoped rules (`:382`, `:404`) subsequently adjust this element's `max-width`/`font-size`/grid position — never its `display` — confirming the intent was to keep it visible and simply reposition it, not hide it.

**Resolution: REJECT the original claim as stated.** The final rendered result shows the readout visible at every width. The underlying observation that a `display:none` rule for this element genuinely exists somewhere in the file is accurate — S-v0dev and S-Kimi did not fabricate a rule — but neither traced forward to the later, more specific override, the same category of error as §15.1. **Promoted to AB-F026.** The general lesson (two now-confirmed instances of the identical pattern — an early rule superseded by a later, more specific one) is itself recorded as a maintainability observation feeding into the AB-F038 design-token-consolidation recommendation.

### 15.3 Is the skill-row hover-preview keyboard-accessible, or hover-only?

**Claim A (S-Claude, S-Kimi):** Correctly built — `:hover, :focus-visible` dual trigger, confirmed via source.
**Claim B (S-Qwen AB-11, S-v0dev implied, S-DeepSeek):** Hover-dependent, not accessible via keyboard/touch.

**Trace performed in this pass:** `index.css` confirms: `.skill-row-button:hover .skill-hover-preview, .skill-row-button:focus-visible .skill-hover-preview { opacity: 1; ... }` — Claim A's specific mechanism claim is accurate; keyboard `Tab`-focus genuinely does reveal the preview at desktop/tablet widths. Separately, `.skill-hover-preview{display:none}` inside the mobile (`max-width:739px`) media query confirms the content is not merely hard-to-reach on mobile — it is entirely removed from layout, which is what Claim B's authors (who did not have `index.css` — both S-Qwen and, per its own self-disclosure, part of S-DeepSeek's source material — were working from class-name inference and screenshots, not verified CSS) were correctly sensing even without being able to cite the precise mechanism.

**Resolution: BOTH CLAIMS PARTIALLY CORRECT — not a real contradiction once desktop/tablet and mobile are treated separately.** Claim A is accurate for ≥740px and should not be "fixed" (there is nothing broken to fix there). Claim B's underlying concern is accurate for <740px, where content genuinely disappears rather than degrading gracefully. **Resolved as AB-F054**, with a decision that preserves the correct mechanism and fixes only the genuine mobile gap.

### 15.4 How urgent is the illustrative-numbers-vs-real-data mismatch pattern?

**Claim A (S-Manus, S-ChatGPT):** P0 — an evidence-integrity issue central to the product's mission.
**Claim B (S-Claude, S-v0dev, S-Qwen):** P1/P2 — a content-authoring gap, UI-adjacent but not UI-blocking.

**Resolution: P1**, arrived at as follows rather than by splitting the difference numerically. The *arithmetic-derivation* half of this finding (make "3/8" actually reflect `levels.length`, remove the non-existent "Exchanges & Refunds" category) is genuinely UI-only, zero-dependency, and P0-cheap to fix — there is no reason to delay it, and Claim A's urgency is right about *that* half. But the *deeper* half — whether "8 stages" and "40 scenarios" should eventually be real, larger totals, which requires curriculum content that does not yet exist — cannot be resolved by any UI change at all, making Claim B's "this is content-dependent, not purely a UI defect" framing also correct. This synthesis's P1 verdict reflects: fix the derivation/naming immediately as an independent, unblocked action (satisfying Claim A's urgency), while explicitly not blocking that fix on, or conflating it with, the separate content question (satisfying Claim B's more measured framing of the larger issue). See AB-F010 for the complete decision.

### 15.5 Does the terminal caret respect `prefers-reduced-motion`?

**Claim (S-Manus AB-13, S-Kimi T09):** No.

**Trace performed in this pass:** Beyond the global catch-all at `index.css:123` (`*, *::before, *::after { animation-duration:.001ms!important; ... }`), a second, more specific rule exists at `:217`: `@media (prefers-reduced-motion: reduce) { .history-list button, .terminal-caret { transition: none; animation: none; } }` — `.terminal-caret` is named explicitly, and this rule sets the full `animation` shorthand (not just duration) to `none`.

**Resolution: REJECT.** Two independent mechanisms — a universal catch-all and a component-specific rule naming the caret directly — both disable the blink under reduced motion. Neither S-Manus nor S-Kimi appear to have located the line-217 rule specifically; this is the one conflict in this set that is not explained by an incomplete cascade trace of a *real* rule (as in §15.1/15.2) but appears to be a genuine miss of a rule that exists. **Promoted to AB-F027 (rejected claim) and AB-F028 (confirmed positive finding).**

---

## 16. NEW INSIGHTS / AUDIT GAPS

*Findings and framings that emerged specifically from cross-referencing the nine audits against each other and against direct source verification in this synthesis pass — not present, at least not with this specific framing or evidentiary grounding, in any single one of the nine source audits on its own.*

1. **A generalizable "trace the cascade, not the first match" lesson.** Three of this report's most consequential adjudications (§15.1, §15.2, §15.5) share one root cause: a source audit correctly located a real, relevant CSS rule but stopped before finding a later rule that supersedes it. This is not a criticism of the diligence of S-v0dev, S-Kimi, or S-Manus specifically — all three produced some of the most precisely-cited findings among the nine audits, which is exactly what made the pattern visible and checkable. It is a structural risk in *any* line-citation-based CSS audit of a file with layered, later-refined token passes like this one's `--ab-*` block, and is worth stating explicitly as a methodology note for whoever does the next audit of this codebase: grep for every declaration of a disputed selector, not just the first one found, before concluding a rule is broken.
2. **The `--ab-*` "AeroBridge Elevation Directive" layer is, itself, evidence of a second design pass that already correctly identified and partially fixed some of this report's own findings** — before this report existed. Its own code comment ("prioritize Terminal, calm precision, and operational readability") shows someone already recognized the Terminal needed distinguished treatment, and its rules already correctly restore the mobile session-readout visibility that an earlier pass had hidden (§15.2). This suggests whoever authors the next revision pass should treat `--ab-*` as a signal of prior, aligned intent to build on, not merely a duplicate system to delete.
3. **`Map.tsx`'s completeness (155 fully-built lines, unused) plus Progression's "View map" stub button (AB-F009) plus Scenarios' `detail-visual` panel already using a static route-map background image (`url('/manus-storage/aerobridge-share-route-map_...jpg')`, confirmed in source) together suggest a previously-planned interactive map feature that was designed, partially built, then descoped** — worth surfacing to whoever owns the roadmap as a single question ("finish it, or remove the remaining stub/dead-code traces of it?") rather than as three unrelated findings (AB-F019, part of AB-F009, and this observation) to be independently triaged.
4. **The exact-count corroboration between this pass's direct measurement and S-Claude's audit** (`aria-label` ×17, `aria-hidden` ×4, `aria-live` ×2, `aria-current` ×1 — every count matching precisely) is itself useful evidence, not just a curiosity: it substantially raises this synthesis's confidence in S-Claude's other, less-independently-checked claims (notably AB-F004's font-loading finding and AB-F011's pinch-zoom finding, neither of which this pass could re-verify directly), since it demonstrates S-Claude's methodology for this codebase was, where checkable, exact rather than approximate.
5. **A pattern across the "resolved conflict" findings worth naming for the product team directly:** every one of the three rejected claims (§15.1, 15.2, 15.5) would have led to *removing or weakening something that already works correctly* if acted on without verification — simplifying the bottom-nav grid, exposing the terminal readout via a new mechanism it doesn't need, or adding motion-reduction handling to an element that already has it. This is a useful, generalizable caution for how this report's own recommendations should be handled downstream: verify against current source immediately before implementing any fix in this document, since the codebase may have already changed between this audit and implementation time.

---

## 17. FINAL PRIORITY MATRIX

| ID | Finding | Priority | Verdict | Dependency | Screen(s) |
|---|---|---|---|---|---|
| AB-F001 | Fabricated default Coach error | **P0** | Accept | UI-only | Practice |
| AB-F002 | Empty submit → silent FQD | **P0** | Accept w/ mod | Mixed (safe interim) | Practice |
| AB-F003 | EN/AR toggle cosmetic | **P0 (decision)** | Accept w/ mod | Content+Engine+Arch | Global |
| AB-F004 | Declared fonts not loading | **P0** | Test before accepting | UI-only | Global |
| AB-F005 | Primary-button AA contrast fail | P0/P1 | Accept | UI-only | Global |
| AB-F011 | Pinch-zoom disabled | P0/P1 | Test before accepting | UI-only | Global |
| AB-F006 | text-faint AA contrast fail | P1/P2 | Accept | UI-only | Global |
| AB-F007 | Zero tab/toggle ARIA semantics ×5 groups | **P1** | Accept | UI-only | Global |
| AB-F008 | Two parallel color-token systems | **P1** | Accept w/ mod | UI-only | Global |
| AB-F009 | 12 toast-only stub controls | P1/P2 | Accept w/ mod | Mixed | Global |
| AB-F010 | Illustrative numbers ≠ real data (systemic) | **P1** | Accept w/ mod | Mixed (UI part unblocked) | Progression/Scenarios/Growth |
| AB-F012 | Hint/history state bleeds across modes | P1 | Accept w/ mod | Mixed (UI mitigation now) | Practice |
| AB-F015b | Drawer/popover lack dialog semantics | P1 | Accept | UI-only | Global |
| AB-F015c | No `<main>`, unlabeled side-nav, no skip link | P1 | Accept | UI-only | Global |
| AB-F014 | Touch targets <44px (38→35→33px) | P1/P2 | Accept | UI-only | Global (topbar) |
| AB-F018 | Focus Mode lacks keyboard trap | P1/P2 | Accept | UI-only | Practice |
| AB-F047 | Track toggle content mismatch | P1 | Accept | Content-dep. | Progression |
| AB-F049 | Duplicate "Filters" button | P1 | Accept | UI-only | Scenarios |
| AB-F050 | Sort control doesn't sort | P1/P2 | Accept | UI-only | Scenarios |
| AB-F053 | "Backup" implies false protection | P1 | Accept | UI-only | Growth |
| AB-F054 | Skill-preview: correct on desktop, absent on mobile | P1/P2 | Accept w/ mod | UI-only | Growth |
| AB-F013 | Redundant per-command toasts | P1/P2 | Accept | UI-only | Practice |
| AB-F016 | Session timer pre-seeded | P3 | Accept w/ mod | UI-only | Practice |
| AB-F017 | Fixed decorative terminal gap | P2/P3 | Accept w/ mod | UI-only | Practice |
| AB-F015 | Dual prompt/caret affordance | P2 | Test before accepting | UI-only | Practice |
| AB-F019 | `Map.tsx` unused dead code | P3 | Accept | UI-only / roadmap-dep. | Global |
| AB-F020 | ErrorBoundary unmounted, NotFound off-brand | P2/P3 | Accept | UI-only | Global |
| AB-F021 | Hardcoded external image path, no fallback | P2 | Accept | UI-only | Global |
| AB-F022 | Dead "hint-dependency" legend entry | P3 | Accept | UI-only | Practice |
| AB-F023 | Most SystemState values unreachable | P2/P3 | **Defer** | Engine-dep. | Global |
| AB-F024 | AnimatedBar lacks progressbar role | P2 | Accept | UI-only | Progression/Growth |
| AB-F038 | Ad-hoc spacing/radius scale | P2 | Accept | UI-only | Global |
| AB-F039 | KPI decorative clip-path ornamentation | P3 | Accept w/ mod | UI-only | Tracking |
| AB-F040 | `.bottom-nav` grid rule declared 4× | P3 | Accept | UI-only | Global |
| AB-F042 | `.is-secondary-view` — fold into F007 | P2 | Accept w/ mod | UI-only | Growth |
| AB-F043 | Mobile nav reorder vs desktop | P2 | Accept w/ mod (document only) | Doc-only | Global |
| AB-F044 | "Route" term overloaded | P3 | Accept | Content-only | Global |
| AB-F045 | Hamburger drawer duplicates bottom-nav | P2 | Accept w/ mod (product decision) | Content-dep. | Global |
| AB-F046 | Tablet 740–1099px nav/content mismatch | P2 | **Test before accepting** | UI-only if confirmed | Global |
| AB-F048 | Expandable level cards weakly discoverable | P2 | Accept | UI-only | Progression |
| AB-F052 | Trend-arrow color/direction mismatch | P2 | Accept | UI-only | Growth |
| AB-F055 | Route-line label truncation (mobile) | P2 | Accept | UI-only | Tracking |
| AB-F056–058 | Content-layer verdict/provenance language | P2/P3 | Accept (flag only) | Content-only | Progression/Practice/Growth |
| AB-F059 | Untested sub-360px behavior | P2 | **Test before accepting** | UI-only if needed | Global |
| AB-F025 | (resolved) bottom-nav 4-col claim | — | **Reject** | — | — |
| AB-F026 | (resolved) mobile readout hidden claim | — | **Reject** | — | — |
| AB-F027 | (resolved) caret ignores reduced-motion claim | — | **Reject** | — | — |
| AB-F028 | (confirmed) reduced-motion coverage comprehensive | — | **Accept as strength** | — | — |

---

## 18. IMPLEMENTATION SEQUENCE

**Phase A — Zero-dependency P0 fixes (ship first, independently, each screenshot-verifiable alone).**
AB-F001 (fabricated Coach error) · AB-F002 (empty-submit guard, with explicit non-empty-command regression check) · AB-F010's UI-only derivation half (stage/scenario/log counts pulled from actual array lengths; remove the non-existent "Exchanges & Refunds" reference) · AB-F005 (primary-button contrast). None of these four depend on each other or on anything later in this sequence.

**Phase B — Verification-gated items (resolve before building anything on top of them).**
AB-F004 (confirm actual font-loading state — blocks accurate visual QA for everything after it) · AB-F011 (confirm pinch-zoom state — high severity if true) · AB-F046 (tablet-range live render) · AB-F059 (320px live render). Phase B can run in parallel with Phase A; nothing in Phase A depends on Phase B's outcomes.

**Phase C — Design-system consolidation (sequenced deliberately ahead of Phase D).**
AB-F008 (fold `--ab-*` into base tokens as canonical) together with AB-F006 (text-faint contrast, a token-value change touched by the same pass) and AB-F038 (spacing/radius scale definition, applied opportunistically going forward rather than swept immediately). This phase exists specifically so Phase D is written against one token system, not two.

**Phase D — Accessibility pass, built on Phase C.**
AB-F007 (tab/toggle ARIA, all five control groups from one shared pattern) · AB-F042 (folds in automatically) · AB-F015b (drawer/popover dialog semantics) · AB-F015c (main landmark, side-nav label, skip link, focus-on-navigate) · AB-F018 (Focus Mode trap) · AB-F024 (AnimatedBar progressbar role).

**Phase E — Remaining P1 behavioral/content fixes, screen by screen, in the priority order §12 establishes.**
Practice: AB-F012 transparency mitigation, AB-F013, AB-F014, AB-F016, AB-F017. Growth: AB-F053, AB-F054, AB-F052. Scenarios: AB-F049, AB-F050, AB-F010's Scenarios instance if not already covered in Phase A. Progression: AB-F047 (interim state), AB-F048, AB-F010's Progression instance if not already covered in Phase A.

**Phase F — Hygiene and low-priority cleanup, opportunistic (no dedicated sprint required).**
AB-F019, AB-F020, AB-F021, AB-F022, AB-F040, AB-F039, AB-F044, AB-F016. These can be picked up individually whenever a developer is already touching the relevant file, per this report's own guidance (§6) against disruptive standalone sweeps for purely-cosmetic/hygiene items.

**Explicitly out of this sequence, requiring separate ownership before any phase above should expand to include them:** AB-F003's real Arabic/RTL build (Critical Decision 3), AB-F045's hamburger-drawer content decision, AB-F047's full Customer Service curriculum, AB-F057/058's content-provenance decisions, and AB-F012's/AB-F023's deferred engine-level questions.

---

## 19. VALIDATION PLAN

**Per-fix validation** is specified individually within each finding's own entry in §5 and should be treated as that finding's definition of done — not re-derived separately here.

**Phase-level validation, in addition to per-fix checks:**
- **After Phase A:** screenshot-diff Practice's default (no-command) state against the current one supplied in this audit's source material; confirm no visual regression to the four AA-passing elements the contrast fix touches; confirm every summary count on Progression/Scenarios/Growth is arithmetically traceable to its underlying array.
- **After Phase B:** record the confirmed actual state of font-loading and pinch-zoom explicitly (updating AB-F004/AB-F011 from "Test before accepting" to a final verdict) before any further visual work proceeds; record whether AB-F046's tablet range needs a fix or can be closed as "acceptable as-is."
- **After Phase C:** grep the stylesheet for any remaining `--ab-` prefixed reference; confirm this returns nothing (full consolidation) or an explicitly-documented, deliberate exception.
- **After Phase D:** a full keyboard-only pass through all five screens (Tab/Shift-Tab/Enter/Space/Escape/Arrow keys) confirming every interactive element is reachable, every current-selection state is announced, and Focus Mode cannot be Tabbed out of; a screen-reader pass (VoiceOver or NVDA, whichever the team has available) confirming landmark navigation works and no state is communicated by color alone.
- **After Phase E:** re-run the same screenshot set supplied to this audit (or an equivalent fresh capture) and confirm every screen-specific defect noted in §12's "Critical problems" is resolved without regressing anything listed in that screen's "Strengths."
- **Ongoing, not phase-bound:** re-verify any AB-FXXX finding against current source immediately before implementing it, per the caution in §16, point 5 — this report is a snapshot of the codebase as read during this synthesis pass, and the codebase may have changed by implementation time.

**What this validation plan does not cover, and why:** live device testing across a real hardware matrix, real assistive-technology user testing, and actual trainee usability testing are all outside what a source-code-and-screenshot audit can specify in advance — each is flagged at the relevant finding as `TEST BEFORE ACCEPTING` rather than given a fabricated pass/fail criterion here.

---

*End of unified audit. Sixty canonical findings (AB-F001–AB-F059, plus four resolved-conflict promotions), covering all nine source audits, direct verification against the full supplied prototype source, and all seven supplied screenshots, with zero findings dropped for being single-sourced, minority, or inconvenient to the overall positive verdict.*
