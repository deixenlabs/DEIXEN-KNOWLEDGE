**AEROBRIDGE — UNIFIED MASTER DESIGN AUDIT**

**DESIGN STATUS**  
**NEEDS TARGETED REVISION**

The prototype is a strong, distinctive Flight Deck Console foundation with a coherent learning loop and Terminal-first intent. It is not production-ready as a definitive UI reference and does not require foundational redesign or architecture reset. A focused, sequenced revision pass is required before it becomes the visual contract for the real engine.

---

### 1. EXECUTIVE VERDICT

**What is strong**  
- Distinctive, non-generic aviation-training identity (deep navy, Vector Blue, green/amber operational states, monospace command/readout language).  
- Terminal is treated as the primary workstation, not a dashboard card. Focus Mode, command history (↑/↓), sticky input, local-simulation labeling, and the Learn/Practice/Assessment mode structure are genuine assets.  
- End-to-end evidence loop is real within the prototype: Assessment → localStorage → Growth/Tracking, with context handoff into Practice from Progression, Scenarios, Growth, and Tracking.  
- Mobile composition is intentional (centered Train, sticky command input, safe-area awareness, dedicated 360/390 rules). Reduced-motion coverage is thorough.  
- Evidence-to-next-action language (“Practice the gap”, “Open recommended practice”, “Move the signal forward”) is pedagogically aligned.

**What is weak**  
- Trust and evidence integrity are compromised by silent empty-command → FQD, pre-submission fake FORMAT ERROR in Coach, hardcoded illustrative metrics presented without clear provenance, and multiple toast-only affordances that claim completed actions.  
- Typography system is declared but not provisioned; small text + low-contrast muted labels undermine long-session readability.  
- Terminal state language is incomplete despite a rich TypeScript taxonomy. Session orientation is fragmented and partially hidden on mobile.  
- Accessibility foundations (focus management for overlays, tab semantics, touch targets, contrast on critical elements, landmarks) are incomplete.  
- Arabic/RTL is a cosmetic toggle only, despite mission relevance.

**What matters most**  
Truthfulness of evidence and command interaction → Terminal hierarchy and state completeness → accessibility and typography baseline → honest labeling of prototype behavior → responsive verification at 320–430 px.

**What must change**  
Empty-command safety, Coach first-use state, evidence provenance labeling, stub controls, font loading, primary contrast, Terminal session orientation on mobile, non-color state markers, and focus/overlay semantics.

**What must not change**  
Flight Deck identity, Terminal-first composition, Focus Mode concept, mode structure (Learn/Practice/Assessment), local-simulation disclosure pattern, evidence-to-next-action loop, desktop sidebar + mobile bottom-rail model with Train elevated, reduced-motion foundation, or any command-matching/scoring/persistence logic.

**Overall design direction**  
Preserve the visual and structural foundation. Execute a controlled P0→P2 revision that makes the workstation more precise, more trustworthy, and more operable, without dashboardization, gamification, or invented engine semantics.  
**Ultimate rule retained:** The UI may interpret engine state; it must never invent engine truth.

---

### 2. SOURCE COVERAGE & EVIDENCE OVERVIEW

**Reviewed materials**  
- Full source: `Home.tsx` (entire product surface), `index.css` (tokens + all responsive/motion rules), `index.html`, `App.tsx`, `ErrorBoundary.tsx`, `NotFound.tsx`, supporting components.  
- Seven rendered mobile screenshots covering Progression, Practice (Terminal + Coach), Scenarios (list + detail), Growth Record (Record / History / Reports), Progress Tracking.  
- Nine independent audits (ChatGPT, DeepSeek consolidated, Gemini, Grok, Manus, v0.dev, Qwen, Kimi, Claude).  
- Prior design-ground-truth notes referenced inside audits.

**Artifact types**  
Source code (Tier 1), rendered screenshots (Tier 2), analytical audits (Tier 4–5). No live multi-device keyboard/screen-reader session or production data model was available.

**Coverage strengths**  
Command submission path, Coach default state, hardcoded metrics, navigation structure, token declarations, responsive breakpoints, reduced-motion, localStorage evidence flow, and visual hierarchy are all directly verifiable.

**Coverage limitations / gaps**  
- Exact contrast ratios under real font metrics (computed approximations only).  
- Physical touch-target hit areas and virtual-keyboard overlap on real devices.  
- Screen-reader announcement quality of `aria-live` regions.  
- Desktop/laptop multi-column behavior beyond CSS rules.  
- True RTL/Arabic rendering (toggle is non-functional).  
- Full 320 px pixel-level validation (min-width declared; dedicated rules are thinner than 360/390).

**Evidence hierarchy applied**  
Source + screenshots > audit observations grounded in those artifacts > audit interpretations. Repetition across audits is treated as consensus signal, not independent proof.

---

### 3. AUDIT CONSENSUS OVERVIEW

**Strongest consensus (high independence + direct verification)**  
- Empty submit silently becomes FQD → trust/safety defect.  
- Coach shows FORMAT ERROR before any command → first-use trust defect.  
- Fonts declared but not loaded.  
- Hardcoded metrics mixed with real local records without clear provenance.  
- Multiple toast-only controls that claim real actions.  
- Terminal must remain primary; coach subordinate.  
- Small text + faint contrast undermine readability.  
- Need complete Terminal state language and non-color state markers.  
- Preserve Flight Deck identity and Terminal-first intent.

**Conditional consensus**  
- Mobile Coach placement / FAB vs. collapsed panel (accept subordinate behavior; exact pattern needs mobile validation).  
- Growth tab disclosure (`display:none` vs. true progressive disclosure).  
- Exact depth of Assessment mode coach suppression.

**Important minority / high-value insights retained**  
- Bottom-nav 5-item / column-grid risk and dead `is-primary` styling (v0).  
- Primary-button contrast failure (Claude).  
- `maximum-scale=1` disables pinch-zoom (Claude).  
- Session readout intentionally hidden on mobile (multiple, confirmed in CSS).  
- Dual token layers (`--ab-*` overrides) and late CSS accumulation (Claude, Manus, DeepSeek).  
- Assessment mode switch history/hint bleed risk (v0, Claude).  
- Service-track content is hollow (Kimi).

**Strongest disagreements resolved later**  
- Scoring of Terminal maturity and Functional Safety (ranged 5.8–9).  
- Whether Assessment deserves its own top-level route (rejected; keep inside Terminal).  
- Degree of decorative reduction required.

**Major uncertainty areas**  
Exact 320 px behavior, real-device keyboard overlap, full ARIA live-region quality, authoritative readiness definition, and production Arabic scope.

---

### 4. CRITICAL DECISIONS

1. **Empty command must create no history, score, toast, or evidence event.** Inline correction only. (P0, Mixed/Engine-boundary safety)  
2. **Coach first-use state must be neutral READY, never error-styled.** (P0, UI-only)  
3. **Every displayed evidence value must declare its owner and provenance (local/illustrative vs. verified).** (P0, Data/Content + UI)  
4. **Terminal remains the unquestioned primary workspace; Coach is subordinate support.** (P0 design principle)  
5. **Stub controls are either implemented, explicitly labeled unavailable/illustrative, or removed.** No false affordances. (P0)  
6. **Declared fonts must be loaded or tokens corrected to the shipped stack.** (P1)  
7. **Typography floor and contrast of meaningful text must meet long-session and AA requirements.** (P1)  
8. **Arabic/RTL remains deferred until product scope is decided; toggle must not claim a completed switch.** (P1 scoping)  
9. **No change to command matching, scoring formula, localStorage schema, or route map.** (Regression safety)  
10. **Identity and Terminal-first posture are non-negotiable.**

---

### 5. CANONICAL FINDINGS

**AB-F001 — Empty command silently becomes FQD**  
Type: Behavioral / Safety  
Source Audits: Nearly all  
Source Artifacts: `Home.tsx` submitCommand (`|| "FQD"`), Practice screenshot  
Evidence Type: Direct source + visual  
Evidence Independence: E4  
Consensus: Strong  
Evidence Quality: Very Strong  
Observation: Blank or whitespace submit is converted to FQD and processed.  
Impact: Creates false command/evidence events; corrupts assessment integrity and trainee mental model.  
Risk: High (trust + learning safety)  
Dependency: Mixed (UI + interaction safety; touches submit path)  
Priority: P0  
Final Verdict: **ACCEPT**  
Decision: Empty/whitespace submit produces no history entry, no score change, no toast, and an inline “Enter a command” correction. Non-empty behavior remains byte-identical.  
Action: Guard in submit path; add visible empty state.  
Validation: Submit empty → no history growth, no score change, inline message present; AN/SS/FQD/FXP sequences still produce identical outputs.

**AB-F002 — Coach shows FORMAT ERROR before any command**  
Type: Behavioral / Trust  
Source Audits: Nearly all + Practice screenshot  
Source Artifacts: Practice screenshot (red “FORMAT ERROR · CHECK ENTRY”), `Home.tsx` coach default  
Evidence Type: Direct visual + source  
Evidence Independence: E4  
Consensus: Strong  
Evidence Quality: Very Strong  
Observation: Default coach state is error-styled with fabricated corrective text while session is READY.  
Impact: First-use trust defect on the core screen.  
Risk: High  
Dependency: UI-only  
Priority: P0  
Final Verdict: **ACCEPT**  
Decision: Zero history → neutral READY state (“AWAITING COMMAND” / workflow guidance). No error-colored string before first submission.  
Action: Conditional render on latestEntry.  
Validation: Fresh Practice session shows no red error styling in Coach.

**AB-F003 — Hardcoded / illustrative metrics presented as authoritative**  
Type: Content / Trust  
Source Audits: All major  
Source Artifacts: Screenshots (23/40, 3/8 stages, 86% pre-submit, 128/210, LOG 04/12 vs 3 rows), `Home.tsx` constants  
Evidence Type: Direct  
Evidence Independence: E4  
Consensus: Strong  
Evidence Quality: Very Strong  
Observation: Summary numbers do not derive from the arrays they purport to summarize; local records coexist with literals.  
Impact: Undermines precision positioning and evidence integrity.  
Risk: High  
Dependency: Data/Content + UI labeling  
Priority: P0  
Final Verdict: **ACCEPT**  
Decision: Every displayed evidence value has one declared owner, source label, and period. Illustrative values are marked or removed.  
Action: Derive from real arrays where possible; add compact provenance labels elsewhere.  
Validation: No unlabeled hard-coded trainee evidence remains.

**AB-F004 — Toast-only / false affordances**  
Type: Interaction / Trust  
Source Audits: All  
Source Artifacts: Source handlers for My route, View map, See all stages, Filters, Backup, Search, Language, etc.  
Evidence Type: Direct source  
Evidence Independence: E4  
Consensus: Strong  
Evidence Quality: Very Strong  
Observation: Multiple controls promise navigation or completed actions and only toast.  
Impact: Erodes professional trust.  
Risk: Medium–High  
Dependency: UI / Product decision  
Priority: P0  
Final Verdict: **ACCEPT**  
Decision: Implement, label “preview / unavailable”, or remove. No active-looking control may claim an action it does not perform.  
Action: Inventory + disposition per control.  
Validation: Click audit shows no false “completed” claims.

**AB-F005 — Declared fonts not loaded**  
Type: Systemic / Typography  
Source Audits: Claude, Manus, v0, ChatGPT, others  
Source Artifacts: `index.html` (Google Fonts block commented for deletion), CSS tokens  
Evidence Type: Direct  
Evidence Independence: E4  
Consensus: Strong  
Evidence Quality: Very Strong  
Observation: Space Grotesk, Cairo, IBM Plex Mono are tokenized but not provisioned.  
Impact: Design intent does not match rendered reality; Arabic readiness blocked.  
Risk: High for long-term reference  
Dependency: UI  
Priority: P1  
Final Verdict: **ACCEPT**  
Decision: Load the three families or revise tokens to the actual shipped stack.  
Action: Font provisioning first in visual pass.  
Validation: Computed font-family on heading, terminal line, and Arabic container matches intent.

**AB-F006 — Insufficient contrast on muted / faint text and primary button**  
Type: Accessibility / Visual  
Source Audits: Multiple + computed  
Source Artifacts: `--text-faint: #5d6a85` on navy, primary-button values, small sizes  
Evidence Type: Computed + source  
Evidence Independence: E3–E4  
Consensus: Strong  
Evidence Quality: Strong  
Observation: Faint text ≈ 3.3–3.6:1; primary button reported ~2.98:1 in one detailed analysis.  
Impact: Legibility of metadata and primary CTAs fails AA at rendered sizes.  
Risk: High  
Dependency: UI  
Priority: P1  
Final Verdict: **ACCEPT**  
Decision: Raise luminance of meaningful muted text and primary-button contrast to ≥4.5:1 (or approved large-text exception). Preserve palette hue.  
Action: Token adjustment.  
Validation: Automated + manual contrast check at final sizes.

**AB-F007 — Terminal state language incomplete; session orientation fragmented / partially hidden on mobile**  
Type: Behavioral / Systemic  
Source Audits: All Terminal-focused  
Source Artifacts: `SystemState` taxonomy vs. rendered UI, CSS `display:none` on session readout ≤739 px, screenshots  
Evidence Type: Source + visual  
Evidence Independence: E4  
Consensus: Strong  
Evidence Quality: Very Strong  
Observation: Rich state taxonomy exists; many states are never rendered. Session readout is hidden on mobile. Coach and header compete for meaning.  
Impact: Slow orientation, missed errors, long-session friction.  
Risk: High  
Dependency: UI + state contract  
Priority: P0/P1  
Final Verdict: **ACCEPT**  
Decision: One dominant session-status summary (mode · context · session state · command state · next move). Non-color markers (text/icon) for success/error/syntax/sequence. Persistent mobile status line. Explicit processing / interrupted / empty states.  
Action: Header + history + mobile status bar work.  
Validation: Trainee can state mode, session state, and latest result within 3 s at 320–430 px.

**AB-F008 — Coach competes with Terminal (desktop column; mobile vertical distance)**  
Type: Visual / Hierarchy  
Source Audits: DeepSeek, Manus, ChatGPT, Grok, Kimi  
Source Artifacts: Practice layout CSS + screenshots  
Evidence Type: Visual + source  
Evidence Independence: E3  
Consensus: Strong  
Evidence Quality: Strong  
Observation: Desktop coach is near-equal column; mobile places it below, risking fold burial.  
Impact: Dilutes primary workstation.  
Risk: Medium–High  
Dependency: UI-only  
Priority: P1  
Final Verdict: **ACCEPT WITH MODIFICATION**  
Decision: Terminal ≥ ~2/3 width on desktop; coach collapsible/subordinate. On mobile, latest result + input stay above optional coach; consider collapsed-by-default or FAB + sheet after validation.  
Action: Layout + default-collapsed mobile behavior.  
Validation: Terminal remains first actionable area; coach never steals primary vertical space by default.

**AB-F009 — Arabic / EN-AR toggle is non-functional**  
Type: Content / Mission  
Source Audits: All  
Source Artifacts: Language button → toast only; no `dir`, no content  
Evidence Type: Direct  
Evidence Independence: E4  
Consensus: Strong  
Evidence Quality: Very Strong  
Observation: Toggle claims language change; nothing changes.  
Impact: Mission gap for Saudi market.  
Risk: High if left as-is  
Dependency: Content + Architecture  
Priority: P1 (scoping) / Deferred full build  
Final Verdict: **ACCEPT WITH MODIFICATION**  
Decision: Until real i18n/RTL scope is decided, toggle must not claim success. Label as roadmap or disable visually. Prepare `--font-ar` and bidi isolation for commands.  
Action: Honest interim labeling; no fake switch.  
Validation: Toggle never announces completed language change.

**AB-F010 — Accessibility gaps (focus management, tab semantics, landmarks, touch targets, zoom)**  
Type: Accessibility  
Source Audits: Claude, Manus, v0, Grok, others  
Source Artifacts: Missing `role="tab"`, drawer without trap/Escape, no `<main>`/skip link, `maximum-scale=1`, icon buttons <44 px  
Evidence Type: Source  
Evidence Independence: E3–E4  
Consensus: Strong  
Evidence Quality: Strong  
Observation: Good foundations (`focus-visible`, some aria-live, chart table, reduced-motion) exist alongside concrete gaps.  
Impact: Keyboard/AT and mobile usability risk.  
Risk: High  
Dependency: UI  
Priority: P1  
Final Verdict: **ACCEPT**  
Decision: Complete focus trap + Escape + restore for drawers/focus mode/search; tab semantics; `<main>` + skip link; remove `maximum-scale=1`; enforce ≥44×44 px (or approved equivalent) on frequent controls.  
Action: Shell + overlay pass.  
Validation: Keyboard-only path through Terminal, drawers, tabs; pinch-zoom works; targets meet size.

**AB-F011 — Assessment mode switch and hint accounting lack explicit contract**  
Type: Behavioral / Learning integrity  
Source Audits: v0, Claude, Manus, DeepSeek  
Source Artifacts: Mode change retains history; Reference open increments hintCount  
Evidence Type: Source  
Evidence Independence: E3  
Consensus: Conditional  
Evidence Quality: Good  
Observation: Mode switch and Reference behavior can bleed evidence across modes without transparent communication.  
Impact: Assessment integrity risk.  
Risk: Medium–High  
Dependency: Mixed (state contract)  
Priority: P1  
Final Verdict: **ACCEPT WITH MODIFICATION**  
Decision: Explicit mode contract (what is preserved/reset/recorded). Surface carried hint/command count on entering Assessment. Learn-mode Reference policy clarified (product decision).  
Action: UI transparency + product confirmation of scoring boundary.  
Validation: Switching modes cannot silently inflate Assessment score without trainee visibility.

**AB-F012 — Design-system drift (tokens, radii, spacing, dual layers)**  
Type: Systemic  
Source Audits: Claude, Manus, DeepSeek, v0, Grok  
Source Artifacts: Late overrides, magic numbers, `--ab-*` parallel tokens  
Evidence Type: Source  
Evidence Independence: E3  
Consensus: Strong  
Evidence Quality: Strong  
Observation: Good foundation eroded by accumulation.  
Impact: Maintainability and consistency when scaling curriculum.  
Risk: Medium  
Dependency: UI  
Priority: P2  
Final Verdict: **ACCEPT**  
Decision: One canonical semantic token layer (surfaces, text, status, interaction, type, motion). Radius/spacing/type scales documented and enforced.  
Action: Consolidation pass after P0 safety.  
Validation: No unexplained dual-token or magic-value proliferation.

**AB-F013 — 320 px and intermediate widths under-validated**  
Type: Responsive  
Source Audits: Multiple  
Source Artifacts: `min-width: 320px`; dedicated rules strongest at 360/390  
Evidence Type: Source  
Evidence Independence: E2–E3  
Consensus: Strong  
Evidence Quality: Moderate–Strong  
Observation: Intentional narrow rules exist; 320 px lacks dedicated verification.  
Impact: Risk of collision or unusable input at true floor.  
Risk: Medium  
Dependency: UI  
Priority: P2  
Final Verdict: **ACCEPT**  
Decision: Dedicated visual + keyboard pass at 320/360/390/430 + tablet/desktop.  
Action: Screenshot + interaction matrix.  
Validation: No horizontal scroll; Terminal input and bottom nav remain operable.

**AB-F014 — Decorative / metric overload risk on Tracking & Growth**  
Type: Visual / Hierarchy  
Source Audits: ChatGPT, v0, Claude, Manus  
Source Artifacts: Screenshots (KPI clip-paths, guilloché, multiple rings)  
Evidence Type: Visual  
Evidence Independence: E2  
Consensus: Moderate–Strong  
Evidence Quality: Good  
Observation: Some surfaces tip from instrument toward ornament.  
Impact: Cognitive load; identity drift toward dashboard.  
Risk: Medium  
Dependency: UI  
Priority: P2  
Final Verdict: **ACCEPT WITH MODIFICATION**  
Decision: Progress visualization only when it answers a concrete operational question. Reduce pure decoration. Keep pattern-interpretation language.  
Action: KPI simplification.  
Validation: Primary readout remains instrument-like under grayscale and dense-view tests.

**AB-F015 — ErrorBoundary / NotFound not integrated; generic fallbacks**  
Type: Architecture / Identity  
Source Audits: ChatGPT, Manus, Claude  
Source Artifacts: Components exist; App mounts only Home  
Evidence Type: Source  
Evidence Independence: E4  
Consensus: Moderate  
Evidence Quality: Strong  
Observation: Fallbacks would break identity if activated.  
Impact: Trust on failure.  
Risk: Medium  
Dependency: Architecture/UI  
Priority: P2–P3  
Final Verdict: **ACCEPT**  
Decision: Integrate AeroBridge-styled recovery; never expose raw stacks.  
Action: Mount + restyle when production paths are wired.  
Validation: Forced error and 404 still look like AeroBridge.

---

### 6. DESIGN SYSTEM DECISIONS

- **Typography**: Load or correct to Space Grotesk (UI/display), IBM Plex Mono (commands/readouts/tabular nums), Cairo (Arabic). Floor: reading/command text ≥13–14 px; metadata ≥12 px. Tabular nums for metrics.  
- **Color**: Preserve navy / Vector Blue / green / amber / red. Raise faint text and primary-button contrast. Status = color + text + icon.  
- **Surfaces**: Three elevation tiers; brightest reserved for active workstation and primary action.  
- **Borders / Radius / Spacing**: Quiet / standard / strong / focus / status. Constrain radius to small documented scale. 4/8 spacing scale.  
- **Components**: Primary / ghost / text / icon / destructive. Consistent disabled/loading. Command input remains the most important input.  
- **States**: Canonical matrix for first-use, empty, loading, ready, processing, success, partial-success, error (syntax/sequence/decision), retry, interrupted, completed, review, locked, unavailable.  
- **Motion**: Keep purposeful; full reduced-motion contract including caret and smooth-scroll.  
- **Arabic/RTL**: Deferred full build; prepare isolation for LTR commands inside RTL prose.  
- **Data viz**: Chart always paired with accessible table (already present — protect).  

All decisions: Priority P1–P2, Dependency UI (except Arabic Content/Architecture).

---

### 7. GLOBAL UX DECISIONS

- Navigation: Keep 5-route model; Train elevated on mobile; desktop sidebar persistent. Fix any column/item mismatch. Add landmarks and skip link.  
- Hierarchy: Workstation → Evidence → Next action → Context → Historical detail.  
- CTA: One dominant operational action per screen.  
- Feedback: Command-level feedback lives in Terminal + Coach; toasts reserved for session-level events.  
- Orientation: Persistent “you are here + next move” without dashboard clutter.  
- System states: Explicit, non-color-only, consistent vocabulary.

---

### 8. TERMINAL / WORKSTATION DECISIONS

- Primary column dominance; Coach subordinate.  
- Single session-status summary always visible (including mobile).  
- Empty submit safe (AB-F001).  
- History: auto-scroll to latest; non-color status prefixes; semantic list.  
- Input: persistent focus affordance, processing lock, ≥16 px mobile, ≥44 px target.  
- Reference and Coach open the same coherent support surface or are explicitly limited in Assessment.  
- Focus Mode: true head-down, focus-trapped, Escape, session identity retained.  
- Assessment: clear Ready → Active → Result → Interpretation → Next Action; score secondary to what failed and what to practice.  
- No decorative empty void that harms long-session density.

---

### 9. LEARNING UX DECISIONS

- Preserve Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action loop.  
- Assessment remains inside Terminal workflow (no new top-level route).  
- Growth stays interpretation layer (“what is reliable / what recurs / what next”), not achievement system.  
- Scenarios keep mission-file framing and context handoff into Practice.  
- Next-action language is mandatory and must actually navigate with context.  
- Hint and mode contracts made explicit and transparent.

---

### 10. RESPONSIVE DECISIONS

- **Desktop (≥1100 px)**: Sidebar + Terminal/Coach split; Terminal primary.  
- **Tablet (740–1099)**: Validate coach does not overwhelm; decide intentional nav identity.  
- **Mobile (≤739)**: Bottom rail; Train centered; Coach collapsed/subordinate; sticky input above safe area.  
- Explicit validation matrix: 320 / 360 / 390 / 430 / 768 / 1024 / 1280 / 1440.  
- No horizontal scroll; Terminal input and critical feedback never obscured.

---

### 11. ACCESSIBILITY DECISIONS

- Contrast ≥ AA for meaningful text at rendered size.  
- Touch targets ≥44×44 px (or approved spacing equivalent) for frequent actions.  
- Full focus management for all overlays and Focus Mode.  
- Tab / selected / current semantics.  
- Landmarks + skip link.  
- Live regions used with urgency-appropriate politeness.  
- Charts retain data-table alternative.  
- Reduced-motion preserved and extended.  
- Non-color state communication mandatory for operational states.  
- Pinch-zoom enabled.

---

### 12. SCREEN-BY-SCREEN AUDIT

**Progression**  
Strengths: Clear resume CTA, track switch, stage language, current-vector framing.  
Critical: Toast-only map/route actions; “3/8” vs actual levels; Service track hollow.  
Required: Honest counts; implement/label/remove stubs; inline locked explanation; stronger next-action strip.  
Do not touch: Hero + primary resume pattern, Technical/Service split concept.

**Practice / Terminal**  
Strengths: Terminal-first, modes, Focus Mode, history, local labeling, sticky input.  
Critical: AB-F001, AB-F002, fragmented state, mobile orientation, Coach competition.  
Required: All Terminal decisions in §8.  
Do not touch: Command semantics, scoring, localStorage shape, Focus Mode concept, simulation disclosure.

**Scenarios**  
Strengths: Mission-file detail, skills, next operational move, filter tabs (partially real).  
Critical: Hardcoded 23/40 & 82%; Filters/Sort stubs; empty-filter state missing.  
Required: Truthful filter/sort or label; empty state; provenance on stats.  
Do not touch: Mission framing and Practice context handoff.

**Growth Record**  
Strengths: Learning-loop strip, strengths/needs-attention, evidence → practice CTA.  
Critical: Mixed evidence levels; Backup false claim; LOG count mismatch; hover-only coaching on mobile.  
Required: Provenance; honest Backup; tab context preservation; coaching parity.  
Do not touch: Pattern-interpretation language and next-practice orientation.

**Progress Tracking**  
Strengths: Metric switcher, chart + data-table alternative, next-readout, real record history.  
Critical: Decorative KPI noise; some hardcoded framing.  
Required: Simplify ornament; keep table; clear metric definitions.  
Do not touch: Data-table alternative and next-action CTA.

**Shared Shell**  
Strengths: Real URL sync, intentional Train emphasis, topbar context.  
Critical: Stub search/language/profile; missing landmarks/skip; drawer semantics; possible bottom-nav grid issue.  
Required: AB-F004, AB-F010 shell items.  
Do not touch: Train elevation intent and overall 5-item model.

---

### 13. KEEP / PRESERVE

- Flight Deck Console identity and deep navy foundation.  
- Restrained blue/cyan/green/amber/red operational language.  
- Terminal-first Practice composition and Focus Mode.  
- Learn / Practice / Assessment structure.  
- Explicit “LOCAL TRAINING SIMULATION” / illustrative labeling pattern.  
- Evidence → next-action loop and context handoffs into Practice.  
- Desktop sidebar + mobile bottom rail with Train elevated.  
- Chart data-table alternative.  
- Thorough reduced-motion handling.  
- Command history ↑/↓ and sticky mobile input engineering.  
- Mission-file scenario framing.  
- Strengths / needs-attention + learning-loop strip in Growth.

---

### 14. DO NOT DO

- Do not redesign the visual identity or turn the product into a generic LMS/dashboard.  
- Do not turn the Terminal into a card among many.  
- Do not invent engine semantics, new commands, scoring changes, or fake carrier data.  
- Do not present illustrative metrics as authoritative trainee evidence.  
- Do not leave false affordances that claim completed actions.  
- Do not rely on color alone for operational state.  
- Do not over-gamify or add decorative metrics.  
- Do not solve architecture or content problems through styling alone.  
- Do not implement full Arabic/RTL as a cosmetic toggle.  
- Do not change route URLs, localStorage schema, or assessment scoring without separate approval.  
- Do not prioritize polish before P0 safety and Terminal hierarchy.

---

### 15. CONFLICTS RESOLVED

- **Assessment as separate route vs. inside Practice**: Keep inside Terminal (preserves workstation primacy).  
- **Mobile Coach: always visible vs. collapsed/FAB**: Subordinate + collapsed-by-default or validated FAB/sheet; Terminal vertical priority wins.  
- **Scoring of Terminal maturity**: Calibrated to “strong foundation, incomplete state/safety” rather than either extreme.  
- **Service track**: Show explicit “in preparation” empty state rather than technical content under both tabs.  
- **Decorative reduction**: Reduce pure ornament; keep identity motifs that do not compete with operational content.

---

### 16. NEW INSIGHTS / AUDIT GAPS

- Bottom-nav item count vs. grid-template risk and dead `is-primary` class (source-confirmed; high mobile impact).  
- `maximum-scale=1` actively disables pinch-zoom (accessibility regression).  
- Primary-button contrast failure is narrower and more actionable than general faint-text complaints.  
- Dual token layers create future maintenance debt when curriculum expands.  
These are absorbed into canonical findings above; no unsupported invention added.

---

### 17. FINAL PRIORITY MATRIX

| ID | Issue / Decision | Evidence | Indep. | Consensus | Quality | Impact | Risk | Dep. | Pri | Verdict |
|----|------------------|----------|--------|-----------|---------|--------|------|------|-----|---------|
| AB-F001 | Empty → FQD | Source | E4 | Strong | VS | High | High | Mixed | P0 | ACCEPT |
| AB-F002 | Coach fake error | Source+SS | E4 | Strong | VS | High | High | UI | P0 | ACCEPT |
| AB-F003 | Hardcoded evidence | Source+SS | E4 | Strong | VS | High | High | Data/UI | P0 | ACCEPT |
| AB-F004 | False affordances | Source | E4 | Strong | VS | Med-High | Med-High | UI | P0 | ACCEPT |
| AB-F007 | Terminal state/orientation | Source+SS | E4 | Strong | VS | High | High | UI | P0/P1 | ACCEPT |
| AB-F005 | Fonts not loaded | Source | E4 | Strong | VS | High | Med | UI | P1 | ACCEPT |
| AB-F006 | Contrast | Computed | E3-4 | Strong | Strong | High | High | UI | P1 | ACCEPT |
| AB-F008 | Coach hierarchy | Visual | E3 | Strong | Strong | Med-High | Med | UI | P1 | ACCEPT MOD |
| AB-F009 | AR toggle | Source | E4 | Strong | VS | High | High | Cont/Arch | P1 | ACCEPT MOD |
| AB-F010 | A11y shell/overlays | Source | E3-4 | Strong | Strong | High | High | UI | P1 | ACCEPT |
| AB-F011 | Mode/hint contract | Source | E3 | Cond. | Good | Med-High | Med-High | Mixed | P1 | ACCEPT MOD |
| AB-F012 | Token drift | Source | E3 | Strong | Strong | Med | Med | UI | P2 | ACCEPT |
| AB-F013 | 320 px validation | Source | E2-3 | Strong | Mod-Strong | Med | Med | UI | P2 | ACCEPT |
| AB-F014 | Decorative overload | Visual | E2 | Mod-Strong | Good | Med | Med | UI | P2 | ACCEPT MOD |
| AB-F015 | Fallback identity | Source | E4 | Mod | Strong | Med | Med | Arch/UI | P2-3 | ACCEPT |

---

### 18. IMPLEMENTATION SEQUENCE

**Phase A — Foundations & Safety (P0)**  
AB-F001, AB-F002, AB-F003, AB-F004, core of AB-F007 (session summary + empty/processing states). Regression lock on command/scoring/persistence.

**Phase B — Core Workstation / Terminal (P1)**  
Full Terminal hierarchy, mobile orientation, Coach subordination, history markers, Focus Mode a11y, mode/hint transparency (AB-F007 remainder, AB-F008, AB-F011).

**Phase C — Typography, Contrast, Shell A11y (P1)**  
Fonts (AB-F005), contrast (AB-F006), landmarks/skip/focus traps/targets/zoom (AB-F010), AR toggle honesty (AB-F009).

**Phase D — Shared System & Remaining Screens (P2)**  
Token consolidation (AB-F012), Growth/Tracking/Scenarios/Progression honesty and hierarchy (AB-F014), responsive matrix (AB-F013), fallbacks (AB-F015).

**Phase E — Polish**  
Motion refinement, micro-copy, optional visual reduction only after A–D stable.

No phase may alter engine semantics.

---

### 19. VALIDATION PLAN

- **Empty command**: Empty submit at all viewports → no history/score/toast; inline message; non-empty sequences identical.  
- **Coach first-use**: Fresh session → zero error styling.  
- **Evidence provenance**: Every metric either derived or labeled; no unlabeled authoritative claims.  
- **Stub controls**: Full click audit.  
- **Terminal orientation**: 320/360/390/430 → mode + session + latest result readable in ≤3 s; input never obscured by keyboard.  
- **Contrast & type**: Automated AA + manual long-session reading test.  
- **Focus/keyboard**: Tab order through Terminal, drawers, Focus Mode, tabs; Escape and restore work.  
- **Responsive matrix**: Screenshots + interaction at listed widths; no horizontal scroll; bottom nav operable.  
- **Regression**: AN/SS/FQD/FXP transcripts, assessmentScore outputs, localStorage shape, route map unchanged.  
- **Failure conditions**: Any false evidence event, any error-styled Coach before input, any primary CTA below contrast, any unusable Terminal input at 320 px → fail phase.

---

**Final quality gate**  
Every meaningful finding from the nine audits and the source/screenshots received a disposition. Strong existing design is protected. Minority high-value insights were retained. No engine truth was invented. No majority vote substituted for evidence. The result is one coherent, implementation-ready design authority for AeroBridge.

**The UI may interpret engine state, but it must never invent engine truth.**