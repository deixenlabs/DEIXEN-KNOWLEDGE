I now have the complete execution specification. To ground the audit in Tier 1 evidence (the actual prototype), I need to read the real source files, which were compressed out of context. Let me pull them in.

Let me read the critical Practice/terminal section of the prototype and the remaining source files.

Confirmed the core safety defect directly in source (line 275: empty submit silently becomes `"FQD"`). Let me finish the prototype tail and pull the CSS design tokens, then scan the audits for their distinctive findings.


I have now grounded the audit in Tier 1 evidence — I read the actual prototype (`Home.tsx`, `App.tsx`), the design tokens (`index.css`), the design ground-truth (`ideas.md`), the nine audits, and all seven screenshots. Below is the single adjudicated deliverable.

**Screenshot inventory (Tier 2 visual evidence):** (1) Growth Record → *History* tab, mobile — latest evidence EV-041, learning-loop 01/02/03, LOG 04/12 event list; (2) Practice, mobile — task 68%, Learn/Practice/Assessment tabs, terminal with a large empty band, command input, and the Coach panel below showing a red **FORMAT ERROR · CHECK ENTRY** plus a fare-family hint, footer "Accuracy 86% · Commands mastered 128/210"; (3) Scenarios, mobile — stat grid, filter tabs, scenario cards, detail panel with route motif + "Resume scenario"; (4) Progress Tracking, mobile — "REVIEW NEEDED", 78% ring, KPI tiles, bar chart with Overall/Accuracy/Sequencing toggle, "View data table", session log; (5) Growth Record → *Reports* tab — "Readiness is a pattern, not a single score", READOUT 72, reliable/recurs/next; (6) Growth Record → *Record* tab — 72% ring, Strengths (AN 92, SS 88), Needs attention (FQD 45, FXP 20, DE-ESC 60); (7) Progression, mobile — continue card 68% ring, learning path 3/8, track tabs, stage map.

---

# AEROBRIDGE — UNIFIED MASTER DESIGN AUDIT

## DESIGN STATUS: **NEEDS TARGETED REVISION**

The product identity, workflow architecture, and learning loop are genuinely strong and should be preserved. Revision is targeted — not a redesign — but it is **not optional**, because one defect (AB-F001) is a trust/evidence-integrity failure verified directly in source, and a cluster of P1 issues weaken trust, accessibility, and mobile ergonomics.

---

## 1. EXECUTIVE VERDICT

**What is strong.** AeroBridge reads as what `ideas.md` intends: a *Flight Deck Console* — a professional aviation training workstation, not a generic dashboard. The coherent product loop (Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action) is real in code, not decorative. The end-to-end evidence loop actually functions: an assessment computes a real score (`assessmentScore`, Home.tsx:48), persists to `localStorage` (Home.tsx:358), and resurfaces as evidence in Growth and Tracking. The terminal is a genuine work surface (command history, ArrowUp/Down recall, sequence/decision error taxonomy, focus mode), the design tokens are disciplined (deep navy, one Vector Blue accent, green/amber/red semantics, mono readouts), and closure artifacts (AssessmentReport, error key, "Next training move") are high quality.

**What is weak.** The product occasionally *manufactures evidence and success*. An empty command submit is silently coerced to `"FQD"` and recorded as an accepted command with a green "Evidence captured" toast (AB-F001). The Coach shows a red **FORMAT ERROR** with a specific correction *before the user types anything* (AB-F002). Several controls (Backup, Language→AR, Filters, Sort, Search, "See patterns") fire success/info toasts but perform no action (AB-F003, AB-F005, AB-F016). Illustrative constants (Accuracy 86%, 128/210, 23/40, streak) are presented with the same visual authority as computed evidence (AB-F004). Mobile terminal ergonomics waste vertical space (AB-F007), and there is a standard cluster of accessibility gaps (touch targets, small low-contrast mono labels, tablist semantics, color-only status).

**What matters most.** Trust and evidence integrity first (AB-F001, AB-F002, AB-F003, AB-F004), because in a *training* product a fake pass is worse than a missing feature. Then mobile terminal + accessibility (AB-F007, AB-F010–F013). Then honesty of AR and fonts (AB-F005, AB-F006).

**What must not change.** The Flight Deck identity, terminal-first Practice surface, the evidence loop, operational language, restrained palette, and the asymmetric console layout. Do not cardify the terminal, do not gamify, do not add metrics.

**Overall direction.** Controlled revision that makes every visible state *truthful*, hardens input safety, and adapts the workstation to mobile — while protecting the identity that already differentiates the product.

---

## 2. SOURCE COVERAGE & EVIDENCE OVERVIEW

**Reviewed (Tier 1 — direct artifact):** `App.tsx` (trivial shell), `pages/Home.tsx` (full product: routing, all five views, mock command engine, `assessmentScore`, seed data, `localStorage`), `index.css` (tokens, all component + responsive + focus-mode styles), `ideas.md` (design intent). `Map.tsx`, `const.ts`, `index.ts` were provided but `Map.tsx` is not imported by the running app (`App → Home` only) — treated as **not part of the shipped surface**.

**Reviewed (Tier 2 — rendered visual):** 7 mobile screenshots at ~411px covering all five screens plus all three Growth tabs. All are **mobile portrait, dark mode**. 

**Reviewed (Tier 4/5 — analytical):** nine audits (Qwen, Gemini, DeepSeek, ChatGPT, Manus, Grok, v0.dev, Claude, Kimi).

**Coverage limitations / evidence gaps.**
- **No desktop or tablet screenshots.** `.side-nav { display:none }` (index.css:46) is the mobile default; desktop/tablet layout, side-rail, and coach/terminal side-by-side composition are **UNKNOWN / VALIDATION REQUIRED** from visual evidence and inferred only from CSS.
- **Font loading is unverified.** CSS references Space Grotesk / IBM Plex Mono / Cairo (index.css:32–34) but no `@font-face`/link is present in the supplied files — actual rendering must be validated.
- Audits largely share the same screenshot set, so agreement is **high consensus, limited evidence independence** (see §10 principle) — I weighted source verification over audit repetition.

---

## 3. AUDIT CONSENSUS OVERVIEW

- **Strongest consensus (and source-verified, so promoted to E4):** the empty-submit/coerced-command safety defect; toast-only "fake success" controls; unloaded fonts; illustrative-vs-real data ambiguity; mobile terminal density; accessibility gaps (targets, contrast, color-only state); AR being cosmetic.
- **Conditional consensus:** "reduce terminal empty space on mobile" — accept, *conditioned on* preserving output room and not shrinking the work surface into a card.
- **Important minority insights (retained):** hint-accounting inconsistency between the two reference triggers (AB-F009); practice-mode never enforces sequence so out-of-order commands always "succeed" outside assessment (AB-F017); the session timer is decorative/pre-seeded (AB-F019).
- **Strongest disagreement:** whether the Coach's first-load "FORMAT ERROR" is a real defect or a screenshot artifact. **Resolved by source:** it is real (Home.tsx:311 fallback string). 
- **Major uncertainty:** all desktop/tablet behavior; real font rendering.

---

## 4. CRITICAL DECISIONS

1. **AB-F001 is P0 and blocks "production-ready".** Input coercion that fabricates evidence is a trust failure in a training product. **ACCEPT — fix required.**
2. **Truthful-state principle governs the revision.** Any control that implies success, changes state, or creates evidence must either *do the thing* or *clearly state it is a local/illustrative preview*. Governs AB-F002/003/004/005/016.
3. **Preserve the terminal as the primary work environment.** Reject any recommendation that turns it into a dashboard widget; mobile fixes reclaim space without shrinking the work surface.
4. **Mark illustrative data, do not delete it.** The preview is presentation-first (`ideas.md`); keep sample metrics but label them "illustrative / local" wherever they sit beside computed evidence.
5. **AR and fonts are honesty issues, not features to expand.** Either implement real RTL or relabel the toggle as a preview; load the declared fonts or update the token to the true fallback.

---

## 5. CANONICAL FINDINGS

**AB-F001 — Empty (or unknown) command is silently coerced to `FQD` and recorded as accepted evidence**
- Type: Behavioral / Systemic · Sources: Qwen, Gemini, DeepSeek, ChatGPT, Manus, Grok, v0.dev, Claude, Kimi · Artifacts: Home.tsx:275–296 · Evidence: source + runtime logic · Independence: **E4 (directly verified)** · Consensus: C5 · Quality: Very Strong
- Observation: `const nextCommand = command.trim().toUpperCase() || "FQD"` — an empty submit becomes `FQD`, returns "FARE DISPLAY RETURNED", sets `submitted=true`, pushes a history entry, and fires `toast.success("Command accepted. Evidence captured.")`. In assessment this counts toward the persisted score.
- Impact: Fabricated evidence; inflated scores; user learns nothing yet is told they succeeded. Risk: undermines the product's core promise. 
- Dependency: UI + Interaction (no engine change) · Priority: **P0** · Verdict: **ACCEPT**
- Action: Reject empty input (keep focus, inline "Enter a command" hint, no history write, no toast). Do not default unknown/empty entries to any real command. Unknown non-empty input should route to the existing `SYNTAX ERROR` branch, not `FQD`.
- Validation: On Practice, submit empty → expect no history row, no success toast, input retains focus. In Assessment, empty submits must not change score or command count.

**AB-F002 — Coach shows "FORMAT ERROR · CHECK ENTRY" and a specific correction on first load, before any command**
- Type: Behavioral / Content · Sources: Gemini, ChatGPT, Manus, Claude, Kimi (others implied) · Artifacts: Home.tsx:311; screenshot 2 · Evidence: source + rendered · Independence: **E4** · Consensus: C4 · Quality: Very Strong
- Observation: `{latestEntry?.response ?? "FORMAT ERROR · CHECK ENTRY"}` and body `"The availability entry needs the airline prefix..."` render as the *default* Coach state with no history. Screenshot 2 confirms the red error on a fresh session.
- Impact: Presents a failure the user never caused; contradicts the "Ready" terminal state; erodes trust in feedback. Dependency: UI/Content · Priority: **P1** · Verdict: **ACCEPT**
- Action: Default (no command yet) Coach = neutral orientation ("Awaiting your first command — start with availability"). Only show error styling/content after a real failed entry.
- Validation: Load Practice fresh → Coach shows neutral guidance, no red error; submit a bad command → error appears.

**AB-F003 — Toast-only "fake success" actions (impression of success without action)**
- Type: Behavioral / Systemic · Sources: all nine · Artifacts: Home.tsx:164 (Language), 166 (Profile), 212 (section actions), 219/229/311/321/335 (map/stages/filters/reference), 343 (Backup "backup point created") · Independence: **E4** · Consensus: C5 · Quality: Very Strong
- Observation: Multiple controls fire `toast.success/info` with no state change; "Backup" claims a backup point was created.
- Impact: Trust erosion; "success" language for no-ops is the same class of problem as AB-F001. Dependency: UI/Content · Priority: **P1** · Verdict: **ACCEPT WITH MODIFICATION**
- Action: For preview-only controls use *honest* copy ("Search is a preview in this build") and neutral `toast.info`, never `toast.success`. Never claim an artifact ("backup point") was created unless it was. Where cheap, make it real (Filters/Sort already have working logic elsewhere — wire them).
- Validation: Audit every `toast.success` call; each must correspond to a real state change or be downgraded/relabeled.

**AB-F004 — Illustrative metrics rendered with the authority of computed evidence**
- Type: Content / Systemic · Sources: Qwen, DeepSeek, ChatGPT, Grok, Kimi · Artifacts: Home.tsx:256 (`accuracy = submitted ? … : 86`), 300 (task 68%), 313 (128/210), 335 (23/40, 82%, +6%), 178–179 (24%, 7-day streak) · Independence: **E4** · Consensus: C4 · Quality: Strong
- Observation: Hardcoded constants sit beside genuinely computed values with identical styling; the footer shows "Accuracy 86%" on a fresh session (screenshot 2).
- Impact: Violates evidence integrity (prompt §22, §24); user can't tell local sample from their own result. Dependency: Content/UI · Priority: **P1** · Verdict: **ACCEPT WITH MODIFICATION** (do **not** delete — preview is presentation-first)
- Action: Add a consistent, quiet "illustrative / local" marker on sample metrics; for the live footer accuracy, show a neutral placeholder ("—") until a real submit rather than a fake 86%.
- Validation: Fresh session → no metric implies real performance; after one real assessment → live values are visibly distinguished from seed samples.

**AB-F005 — Arabic (AR) is cosmetic: no RTL, no translation, Cairo not applied**
- Type: Behavioral / Systemic · Sources: Gemini, ChatGPT, Manus, Claude, Kimi · Artifacts: Home.tsx:164; index.css:33 (Cairo declared, never applied); no `dir`/`lang` anywhere · Independence: **E4** · Consensus: C4 · Quality: Strong
- Observation: Toggling AR sets a label and toasts "language set to AR"; nothing flips direction, font, or copy.
- Impact: For a Saudi-market training product (the sidebar even advertises "Saudi readiness"), this is a meaningful honesty gap. Dependency: Content/UI (+Engine if full i18n) · Priority: **P1** · Verdict: **ACCEPT WITH MODIFICATION**
- Action: Minimum honest fix — relabel as an EN/AR *preview* with `toast.info`, or implement at least `dir="rtl"` + Cairo on `<html>` and mirror layout. Do not claim a language was "set" if nothing changes.
- Validation: Select AR → either real RTL/Cairo applies, or copy states it is a preview.

**AB-F006 — Declared display/mono fonts likely not loaded (Flight Deck identity depends on them)**
- Type: Visual / Systemic · Sources: Qwen, Gemini, DeepSeek, v0.dev, Kimi · Artifacts: index.css:32–34; no font import in supplied files · Independence: E3 · Consensus: C4 · Quality: Moderate → **TEST BEFORE ACCEPTING**
- Observation: Space Grotesk / IBM Plex Mono / Cairo are referenced with system fallbacks; if not loaded, headings and mono readouts degrade to system-ui, softening the console character.
- Impact: Identity dilution across every screen. Dependency: UI · Priority: **P1** (if confirmed) · Verdict: **TEST BEFORE ACCEPTING**
- Action: Confirm loading; if missing, load the three families (with `font-display: swap`) or update tokens to the intended real fallback.
- Validation: Inspect computed `font-family` on `h1` and `.terminal-body` in the running preview; expect the declared families, not system-ui.

**AB-F007 — Mobile terminal wastes vertical space; work surface poorly adapted to small screens**
- Type: Responsive · Sources: all nine · Artifacts: index.css:110 (`.terminal-body min-height:280px`, `.terminal-gap height:130px`); screenshot 2 · Independence: E4 (CSS) + E2 (visual) · Consensus: C5 · Quality: Strong
- Observation: A fixed 130px gap plus a 280px min body creates a large empty band on mobile before any output; input and coach are pushed far down.
- Impact: Long-session discomfort; the primary work surface feels hollow on the device most likely used. Dependency: UI/Responsive · Priority: **P1** · Verdict: **ACCEPT WITH MODIFICATION** (shrink the *gap*, not the work surface)
- Action: On mobile, replace the fixed gap with flexible spacing, cap empty pre-output height, keep the input reachable (sticky within panel), and let history grow. Do not reduce the terminal to a card (counter-argument test passes: keeps terminal-first identity).
- Validation: Mobile 360–414px, fresh Practice → no empty band > ~1 line; after 4 commands → history visible without excessive scroll; input reachable without scrolling past the coach.

**AB-F008 — Coach vs Reference vs terminal-output relationship is ambiguous (esp. mobile)**
- Type: Structural / Responsive · Sources: Gemini, ChatGPT, Manus, v0.dev, Claude · Artifacts: Home.tsx:303/307/311; screenshot 2 · Independence: E2 · Consensus: C3 · Quality: Good · Priority: **P2** · Verdict: **ACCEPT WITH MODIFICATION**
- Observation: Coach echoes a "SYSTEM RESPONSE" block that duplicates the terminal's latest response; on mobile the coach stacks below the terminal and competes for attention; there are two different "reference" affordances behaving differently.
- Action: Define one clear division of labor — terminal = truth/output, Coach = interpretation/next move, Reference = examples. Remove the duplicated system-response echo in the Coach. On mobile, make the Coach a collapsible drawer anchored to the terminal.
- Validation: After a command, the response text appears once (terminal), Coach shows interpretation only.

**AB-F009 — Inconsistent hint accounting between the two reference triggers**
- Type: Behavioral (minority insight, retained) · Sources: ChatGPT, Kimi · Artifacts: Home.tsx:303 (terminal Reference `setHintCount(count+1)`) vs 311 (coach "Open reference" → toast only) · Independence: E4 · Consensus: C2 · Quality: Good · Priority: **P2** · Verdict: **ACCEPT**
- Observation: Opening the terminal Reference counts as a hint (affecting `hintScore`), but the Coach's "Open reference" does not; also, opening reference in *Learn* mode counts as a hint though Learn is the guided mode.
- Action: Define a single hint policy: what counts, in which modes. Make both triggers consistent; likely don't count reference opens as hints in Learn.
- Validation: Open each reference affordance in each mode; confirm `hints` changes only per the defined policy.

**AB-F010 — Status conveyed by color alone in several places**
- Type: Accessibility / Systemic · Sources: Qwen, Gemini, DeepSeek, ChatGPT, Claude · Artifacts: Home.tsx:189 (`state-notice-mark`), 206 (legend dots), 347 (`skill-orb--tone`); index.css status colors · Independence: E2/E4 · Consensus: C4 · Quality: Strong · Priority: **P1** · Verdict: **ACCEPT**
- Action: Pair every status color with text and/or icon (pass/review/retry already have text in some rows — extend to notice marks, legend dots, skill tone orbs). 
- Validation: Grayscale the UI; all states remain distinguishable.

**AB-F011 — Small, low-contrast mono/label text below comfortable AA thresholds**
- Type: Accessibility / Visual · Sources: Qwen, DeepSeek, ChatGPT, Grok, Kimi · Artifacts: index.css:68 (`.eyebrow` 9px, `--text-faint #5d6a85`), 8–10px `small` labels throughout · Independence: E3 · Consensus: C4 · Quality: Moderate→Strong · Priority: **P1** · Verdict: **ACCEPT WITH MODIFICATION** (balance with workstation density, prompt §28)
- Action: Raise the smallest label sizes (floor ~11px for meaningful text), and lift `--text-faint` contrast where it carries information (not merely decorative eyebrows). Keep density; don't inflate everything.
- Validation: Contrast-check informational text against navy for ≥4.5:1 (or ≥3:1 for large); confirm no functional label < 11px.

**AB-F012 — Tabs lack tablist semantics; error/live-region coverage partial**
- Type: Accessibility · Sources: Gemini, ChatGPT, Claude, v0.dev · Artifacts: Home.tsx mode-tabs:301, growth-tabs:339, filter-tabs:326, metric-switcher:206 (plain buttons); `aria-live` present at 236/304 · Independence: E4 · Consensus: C3 · Quality: Good · Priority: **P2** · Verdict: **ACCEPT**
- Action: Give tab groups `role="tablist"`/`tab`/`aria-selected` and arrow-key navigation; ensure terminal errors announce (role="alert" or assertive live region for failures, polite for success).
- Validation: Screen-reader pass; keyboard arrow navigation across tabs; failed command is announced.

**AB-F013 — Touch targets below 44px on mobile**
- Type: Accessibility / Responsive · Sources: Qwen, Gemini, ChatGPT, Manus, Kimi · Artifacts: index.css:54 (`.icon-button 38px`), 113 (`.filter-tabs` 7–9px padding), 57–59 (language spans) · Independence: E4 · Consensus: C4 · Quality: Strong · Priority: **P1** · Verdict: **ACCEPT WITH MODIFICATION**
- Action: Ensure ≥44×44px hit areas on mobile for icon buttons, filter chips, language, bottom-nav; can keep compact visuals with padded hit areas.
- Validation: Mobile audit — every interactive control ≥44px touch area.

**AB-F014 — Assessment closure & error taxonomy are strong; per-entry error mapping missing**
- Type: Learning (positive + refinement) · Sources: DeepSeek, ChatGPT, Manus, Claude · Artifacts: Home.tsx:233–237 (AssessmentReport), 236 (error key legend) · Independence: E4 · Consensus: C3 · Quality: Strong · Priority: **P2** · Verdict: **ACCEPT (enhance, preserve)**
- Action: Keep the report and taxonomy. Map the legend to individual history entries (each entry already has `errorKind`) so learners see *which* command had *which* error type.
- Validation: After a mixed assessment, each errored entry shows its taxonomy color+label.

**AB-F015 — Declared system states mostly unsurfaced; no real loading states**
- Type: Systemic / Content · Sources: DeepSeek, v0.dev, Kimi · Artifacts: Home.tsx:39 (13 `SystemState`s) vs actual usage (`empty`, `review` surfaced; `loading/retry/interrupted/unavailable` largely unused) · Independence: E4 · Consensus: C3 · Quality: Good · Priority: **P2** · Verdict: **ACCEPT WITH MODIFICATION**
- Action: Either surface the states that matter (interrupted/resume, retry) consistently or trim the type to what the preview truly represents. Empty states on Growth/Tracking are good — preserve.
- Validation: Enumerate each state; confirm it has a real trigger and rendering or is removed.

**AB-F016 — Search is a non-functional popover**
- Type: Behavioral · Sources: Qwen, ChatGPT, v0.dev · Artifacts: Home.tsx:165,168 · Independence: E4 · Consensus: C3 · Quality: Good · Priority: **P2/P3** · Verdict: **ACCEPT WITH MODIFICATION**
- Action: Either implement scoped search over views/scenarios/skills, or present the popover honestly as a preview affordance.

**AB-F017 — Sequence/decision correctness enforced only in Assessment; Practice always "succeeds"**
- Type: Learning (minority insight, retained) · Sources: ChatGPT, Kimi · Artifacts: Home.tsx:279 (`sequenceError = knownCommand && mode === "assessment" && …`) · Independence: E4 · Consensus: C2 · Quality: Good · Priority: **P2** · Verdict: **TEST BEFORE ACCEPTING**
- Observation: In Learn/Practice, valid commands out of order always return success, so practice gives no ordering feedback — the skill the product teaches is only tested at grade time.
- Counter-argument: Practice may intentionally be low-stakes exploration. → **TEST**: decide product intent before changing.
- Validation: Product decision needed; if practice should coach ordering, extend `sequenceError` to practice with softer (non-scored) feedback.

**AB-F018 — Operational terminology is a strength but risks first-run opacity**
- Type: Content / Learning · Sources: Gemini, Grok, Manus · Artifacts: eyebrows "VECTOR 03", "READOUT 72", "EVIDENCE CONSISTENCY / STABLE", "LOG 01" · Independence: E2 · Consensus: C3 · Quality: Moderate · Priority: **P2/P3** · Verdict: **ACCEPT WITH MODIFICATION** (preserve identity; add light first-run orientation) — do **not** strip the language (that would erase identity, §29).

**AB-F019 — Session timer is pre-seeded and decorative**
- Type: Behavioral (minority) · Sources: Kimi, v0.dev · Artifacts: Home.tsx:250 (`useState(272)`), counts up regardless of activity · Independence: E4 · Consensus: C2 · Quality: Good · Priority: **P3** · Verdict: **ACCEPT WITH MODIFICATION** — start at 0 for a real local session or label as illustrative.

**AB-F020 — Desktop/tablet layout (side-rail, coach/terminal composition) unverified**
- Type: Responsive · Sources: (gap) · Artifacts: index.css:46 (`.side-nav{display:none}` base) · Independence: E4 (code) / **no visual evidence** · Consensus: n/a · Quality: n/a · Priority: **P1 to validate** · Verdict: **UNKNOWN / VALIDATION REQUIRED** — do not assert desktop findings without a desktop capture.

---

## 6. DESIGN SYSTEM DECISIONS

- **Typography** — *Decision:* confirm/actually load Space Grotesk (display), IBM Plex Mono (readouts), Cairo (AR); raise functional label floor to ~11px; keep mono for codes/eyebrows. *Why:* identity + legibility (AB-F006, AB-F011). *Scope:* global · *Priority:* P1 · *Dependency:* UI · *Validation:* computed-font check + contrast.
- **Color** — *Decision:* keep the 3–5-color system (navy surfaces, Vector Blue accent, green/amber/red semantics); never encode state in color alone. *Why:* AB-F010, §29. *Scope:* global · P1 · UI.
- **Surfaces/Elevation** — *Decision:* preserve panel gradients + terminal's darker `#040a14` distinct elevation (it signals "work surface"). *Scope:* global · P3 · keep.
- **Borders** — quiet/standard/strong/focus tokens exist (`--line`, `--line-strong`, cyan focus) — keep; ensure focus ring on all custom controls.
- **Spacing** — introduce mobile-flexible terminal spacing (AB-F007); keep dense rhythm elsewhere.
- **Components** — tabs need real tablist semantics (AB-F012); toasts must never say "success" for no-ops (AB-F003); status chips must carry text+icon.
- **States** — reconcile declared vs used `SystemState`s (AB-F015); add a true input-rejection state (AB-F001) and neutral first-run coach state (AB-F002).
- **Motion** — animated numbers/rings respect `prefers-reduced-motion` (Home.tsx:110) — **preserve**; don't add new motion.
- **Accessibility** — targets ≥44px, contrast ≥4.5:1 for info text, non-color status, live regions (AB-F010–F013).
- **Arabic / RTL** — implement real `dir`/Cairo or label as preview (AB-F005).
- **Data visualization** — Tracking chart already ships a `<details>` data table and value labels — **preserve**; add per-bar accessible labels and ensure axis contrast.

---

## 7. GLOBAL UX DECISIONS

- **Navigation:** keep dual model (desktop side-rail + mobile bottom nav with centered "Train" primary) — strong; verify desktop rail (AB-F020). Bottom-nav order intentionally centers Train (Home.tsx:184) — keep.
- **Information hierarchy / IA:** the loop ordering is a genuine asset — preserve. 
- **CTA hierarchy:** one primary per view (Resume/Start/Open practice) — good; ensure preview-only CTAs read honestly (AB-F003).
- **Feedback:** success only on real success; failures announced; first-run neutral (AB-F001/002/012).
- **Orientation:** add light first-run affordance for operational jargon (AB-F018).
- **System states:** consistent empty/interrupted/retry language (AB-F015).

---

## 8. TERMINAL / WORKSTATION DECISIONS

- **Input safety (P0):** reject empty/whitespace; never coerce to a real command; unknown → syntax-error branch (AB-F001).
- **First-run state:** terminal "Ready" + Coach neutral must agree; no phantom errors (AB-F002).
- **Output vs coaching:** terminal owns truth; Coach owns interpretation; remove duplicate echo (AB-F008).
- **Hints policy:** single consistent rule across both reference triggers and across modes (AB-F009).
- **Mobile:** flexible spacing, reachable input, growable history, no dead band (AB-F007).
- **Preserve:** command history + ArrowUp/Down recall, focus mode, session readout line, error taxonomy, "LOCAL TRAINING SIMULATION / ILLUSTRATIVE" disclaimers (these are exactly the evidence-integrity markers §24 wants — keep and extend).

---

## 9. LEARNING UX DECISIONS

- **Learn/Practice/Assessment** modes are well-modeled — preserve. Decide whether Practice should coach sequencing (AB-F017, TEST).
- **Assessment closure:** keep AssessmentReport; map error taxonomy to entries (AB-F014).
- **Feedback/coaching:** neutral first-run; interpretation not duplication.
- **Scenarios/Progression/Growth/Tracking:** the "next useful move" pattern across screens is strong and consistent — preserve; ensure the CTAs actually route (most already do via `setView`/`setPracticeContext`).
- **Repetition:** "one fewer hint, then reassess" guidance is excellent and evidence-led — preserve.

---

## 10. RESPONSIVE DECISIONS

- **Desktop:** side-rail + terminal-dominant with Coach as a side companion — **VALIDATION REQUIRED** (no capture). Verify `.side-nav` reveal breakpoint and that the terminal, not the coach, dominates.
- **Tablet:** define an explicit transition (rail → top or collapsible; coach as drawer); do not assume desktop-scaled.
- **Mobile (verified):** bottom nav + collapsible coach drawer; terminal flexible height with reachable input (AB-F007); ≥44px targets (AB-F013); horizontal-scroll filter tabs are acceptable but need larger hit areas; charts keep value labels + data table.

---

## 11. ACCESSIBILITY DECISIONS

Concrete: (a) ≥44×44px touch targets on all mobile controls; (b) info text ≥4.5:1 contrast, functional labels ≥11px; (c) status = color **+** text/icon everywhere; (d) tablist roles + arrow-key nav on all tab groups; (e) terminal failures announced (assertive), successes polite; (f) preserve `prefers-reduced-motion` handling; (g) real `dir="rtl"` + Cairo if AR is implemented; (h) ensure the command input's helpful `aria-label` (history hint) is retained.

---

## 12. SCREEN-BY-SCREEN AUDIT

**Progression** (screenshot 7). *Strengths:* clear "continue" hero + 68% ring, learning path 3/8, track tabs, stage map with mastered/current/locked. *Critical:* none P0; locked-card toast is fine (informative). *Required:* honest copy on "My route"/"View map"/"See all stages" (AB-F003); font/contrast (AB-F006/011). *Optional:* first-run jargon hint (AB-F018). *Responsive:* verify desktop rail. *A11y:* targets, tablist on track tabs. *Priority:* P2. *Do not touch:* hero identity, ring, milestone semantics.

**Practice / Terminal** (screenshot 2). *Strengths:* real terminal, modes, error taxonomy, focus mode, disclaimers. *Critical:* **AB-F001 (P0)**, AB-F002 (P1), AB-F007 (P1). *Required:* input safety, neutral first-run coach, mobile spacing, hint policy (AB-F009), footer accuracy honesty (AB-F004). *Optional:* practice-mode sequencing (AB-F017, TEST). *A11y:* targets, live-region on failures, tablist on mode tabs. *Priority:* **P0**. *Do not touch:* terminal-first layout, history recall, focus mode, illustrative disclaimers.

**Scenarios** (screenshot 3). *Strengths:* mission-file framing, filter/detail composition, contextual status ("Resume when ready"). *Critical:* none P0. *Required:* wire Filters/Sort or label as preview (AB-F003/016); non-color status on stat trends. *Responsive:* 2-col stat grid ok. *A11y:* filter chip targets, tablist. *Priority:* P2. *Do not touch:* card/detail composition, route motif.

**Growth Record** (screenshots 1,5,6). *Strengths:* tri-tab (Record/History/Reports), evidence StateNotice tied to latest real record, learning-loop strip, "Readiness is a pattern" framing, strengths/needs with trends. *Critical:* "Backup" fake-success (AB-F003). *Required:* honest backup copy; illustrative markers on sample skill values (AB-F004); non-color skill tone (AB-F010). *A11y:* growth-tabs tablist. *Priority:* P1 (backup copy) else P2. *Do not touch:* evidence-first layout, loop strip.

**Progress Tracking** (screenshot 4). *Strengths:* real computed trend from records, metric switcher (overall/accuracy/sequencing), value labels, `<details>` data table, empty state, "next useful readout". *Critical:* none P0. *Required:* chart axis/label contrast; ensure "Run another assessment" routes (it does); non-color legend (AB-F010). *A11y:* metric-switcher tablist, chart bar labels. *Priority:* P2. *Do not touch:* chart + data-table pattern (exemplary), empty state.

**Desktop/Tablet of every screen:** **UNKNOWN / NOT ENOUGH EVIDENCE** — validate with captures before asserting.

---

## 13. KEEP / PRESERVE

Flight Deck identity (deep navy, Vector Blue, green/amber/red semantics, mono readouts); asymmetric console layout; terminal-first Practice with history recall, focus mode, and "LOCAL / ILLUSTRATIVE" disclaimers; the end-to-end evidence loop (compute → persist → resurface); `assessmentScore` model and AssessmentReport + error taxonomy; empty states on Growth/Tracking; the Tracking chart + data-table + metric switcher; contextual CTA language (Start/Resume/Review/Retry); `prefers-reduced-motion` handling; dual navigation (side-rail + centered-Train bottom nav); "next useful move" guidance pattern.

---

## 14. DO NOT DO

Do not turn the terminal into a card or dashboard widget; do not gamify or add streaks/points as motivators; do not add metrics without meaning; do not delete illustrative data (relabel instead); do not strip operational language to "look friendlier"; do not encode state in color alone; do not use `toast.success` for no-ops; do not claim artifacts (backups) were created; do not invent engine semantics or real carrier behavior; do not add backend/auth/payments (out of scope per `ideas.md`); do not assume mobile == scaled desktop; do not assert desktop findings without a desktop capture.

---

## 15. CONFLICTS RESOLVED

- **Coach "FORMAT ERROR" — real defect or screenshot artifact?** Sources split. Evidence: Home.tsx:311 default fallback string + screenshot 2. **Resolution:** real defect. **Decision:** AB-F002 ACCEPT.
- **"Reduce terminal empty space" vs "preserve work surface."** Competing: density-reduction vs terminal-first identity. **Resolution:** shrink the *fixed gap*, keep/grow the work surface (AB-F007). Conditional consensus.
- **"Delete illustrative metrics" vs "preview is presentation-first."** `ideas.md` mandates visible mock interactions. **Resolution:** mark, don't delete (AB-F004).
- **Severity of AR toggle.** Some rated cosmetic/low, others high for the Saudi market. **Resolution:** P1 honesty issue, minimal fix acceptable (AB-F005).
- **Priority calibration across audits.** Rejected majority-vote severity; re-derived from evidence + impact (§15/§34). AB-F001 promoted to P0 on source verification regardless of any audit's lower rating.

---

## 16. NEW INSIGHTS / AUDIT GAPS

- **NEW — Hint-accounting inconsistency (AB-F009):** two reference affordances treat hints differently and Learn-mode reference opens count as hints; distorts `hintScore`. Evidence: Home.tsx:303 vs 311. Why missed: requires reading both handlers, not just screenshots. Confidence: high (E4). Priority P2.
- **NEW — Practice never enforces sequencing (AB-F017):** the taught skill is only graded, never coached in practice. Evidence: Home.tsx:279. Confidence: high (E4). Priority P2, TEST intent first.
- **GAP — No desktop/tablet evidence (AB-F020):** every desktop claim in the source audits is inferential; flagged as VALIDATION REQUIRED rather than accepted.

---

## 17. FINAL PRIORITY MATRIX

| ID | Issue / Decision | Sources | Evidence | Indep. | Consensus | Quality | Impact | Risk | Dependency | Priority | Verdict |
|----|------------------|---------|----------|--------|-----------|---------|--------|------|------------|----------|---------|
| AB-F001 | Empty→FQD fabricated evidence | all 9 | src+runtime | E4 | C5 | V.Strong | Very High | High | UI/Interaction | **P0** | ACCEPT |
| AB-F002 | Coach false FORMAT ERROR first-load | 5+ | src+render | E4 | C4 | V.Strong | High | Med | UI/Content | P1 | ACCEPT |
| AB-F003 | Toast-only fake success | all 9 | src | E4 | C5 | V.Strong | High | Med | UI/Content | P1 | ACCEPT-MOD |
| AB-F004 | Illustrative shown as real | 5 | src | E4 | C4 | Strong | High | Med | Content/UI | P1 | ACCEPT-MOD |
| AB-F005 | AR cosmetic | 5 | src | E4 | C4 | Strong | Med-High | Med | Content/UI | P1 | ACCEPT-MOD |
| AB-F006 | Fonts not loaded | 5 | src | E3 | C4 | Moderate | High | Med | UI | P1 | TEST |
| AB-F007 | Mobile terminal dead space | all 9 | css+visual | E4 | C5 | Strong | High | Low | UI/Resp | P1 | ACCEPT-MOD |
| AB-F013 | Touch targets <44px | 5 | css | E4 | C4 | Strong | High | Low | UI/Resp | P1 | ACCEPT-MOD |
| AB-F010 | Color-only status | 5 | src+css | E4 | C4 | Strong | Med-High | Low | UI | P1 | ACCEPT |
| AB-F011 | Small/low-contrast text | 5 | css | E3 | C4 | Strong | Med-High | Low | UI | P1 | ACCEPT-MOD |
| AB-F008 | Coach/Reference/output ambiguity | 5 | src+visual | E2 | C3 | Good | Med | Med | UI/Resp | P2 | ACCEPT-MOD |
| AB-F009 | Hint accounting inconsistent | 2 | src | E4 | C2 | Good | Med | Low | UI | P2 | ACCEPT |
| AB-F012 | Tablist semantics / live regions | 4 | src | E4 | C3 | Good | Med | Low | UI | P2 | ACCEPT |
| AB-F014 | Assessment closure (enhance) | 4 | src | E4 | C3 | Strong | Med | Low | UI | P2 | ACCEPT |
| AB-F015 | Unsurfaced states | 3 | src | E4 | C3 | Good | Med | Low | UI/Content | P2 | ACCEPT-MOD |
| AB-F016 | Search non-functional | 3 | src | E4 | C3 | Good | Low-Med | Low | UI | P2/P3 | ACCEPT-MOD |
| AB-F017 | Practice no sequencing | 2 | src | E4 | C2 | Good | Med | Med | Interaction | P2 | TEST |
| AB-F018 | Jargon first-run opacity | 3 | visual | E2 | C3 | Moderate | Low-Med | Low | Content | P2/P3 | ACCEPT-MOD |
| AB-F019 | Decorative timer | 2 | src | E4 | C2 | Good | Low | Low | UI | P3 | ACCEPT-MOD |
| AB-F020 | Desktop/tablet unverified | gap | code-only | — | — | — | Unknown | — | Resp | P1(val) | VALIDATION REQUIRED |

---

## 18. IMPLEMENTATION SEQUENCE

- **Phase A — Design System Foundations:** load/confirm fonts (AB-F006); label floor + contrast (AB-F011); non-color status tokens (AB-F010); tablist + focus + live-region primitives (AB-F012); touch-target rule (AB-F013).
- **Phase B — Core Workstation / Terminal:** input safety P0 (AB-F001); neutral first-run coach (AB-F002); coach/output/reference division + remove echo (AB-F008); hint policy (AB-F009); mobile terminal spacing (AB-F007).
- **Phase C — Primary Learning / Progression:** honest metrics + footer placeholder (AB-F004); per-entry error mapping (AB-F014); state reconciliation (AB-F015); decide practice sequencing (AB-F017).
- **Phase D — Supporting Workflow Screens:** honest/real Backup, Search, Filters, Sort, section actions (AB-F003/F016); AR minimum-honest fix (AB-F005); timer honesty (AB-F019); jargon orientation (AB-F018).
- **Phase E — Responsive Refinement:** validate + tune desktop/tablet (AB-F020), then mobile polish.
- **Phase F — Polish + Accessibility Hardening:** full SR/keyboard pass, reduced-motion re-check, RTL parity if implemented.

---

## 19. VALIDATION PLAN

- **AB-F001:** Practice, mobile+desktop. Empty/whitespace submit → no history row, no success toast, focus retained; Assessment score/count unchanged. *Fail:* any FQD/history entry from empty input.
- **AB-F002:** Fresh Practice load → Coach neutral, no red error; bad command → error appears. *Fail:* FORMAT ERROR before any input.
- **AB-F003:** Every `toast.success` maps to a real state change; preview controls use info+honest copy. *Fail:* "success"/"created" for a no-op.
- **AB-F004:** Fresh session shows no metric implying real performance (footer "—"); post-assessment values visibly distinct from seed. *Fail:* static 86% on fresh load.
- **AB-F005:** AR → real RTL/Cairo, or copy states "preview". *Fail:* claims language "set" with no change.
- **AB-F006:** Computed `font-family` on `h1`/`.terminal-body` = declared families. *Fail:* system-ui.
- **AB-F007:** Mobile 360–414px: no empty band > ~1 line; input reachable; history grows. *Fail:* >200px dead space pre-output.
- **AB-F010–F013:** grayscale (status survives), contrast ≥4.5:1 info text, ≥44px targets, arrow-key tabs + SR announcements. *Fail:* any indistinguishable state / <44px control / silent failure.
- **AB-F020:** capture desktop + tablet; confirm side-rail reveal and terminal dominance. *Fail:* no rail / coach dominates / mobile-scaled layout.

---

**Coverage note (Zero-Loss gate):** every meaningful finding surfaced across the nine audits received a disposition here (accepted, accepted-with-modification, test-before-accepting, or validation-required); none were dropped for being single-source, and none were promoted merely for repetition. The single P0 (AB-F001) and the P1 trust/honesty cluster (AB-F002–F007, F010–F013) are the gate between the current build and "near production ready." Identity and the evidence loop are explicitly protected. Where I lacked evidence — all desktop/tablet behavior and true font rendering — I marked it **UNKNOWN / VALIDATION REQUIRED** rather than inventing a conclusion.