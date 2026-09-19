# AEROBRIDGE — MASTER SYNTHESIS AUDIT

**Status:** Independent, evidence-adjudicated synthesis of the complete AeroBridge evidence package.
**Prepared as:** A critical re-evaluation and prioritization — not a summary — of 9 independent AI audits, cross-checked against the original prototype source, the design-intent document, and 7 rendered screenshots.

**Design Status: NEEDS TARGETED REVISION**

---

## Evidence Package and Coverage Statement

This synthesis independently inspected, in full:

- **Prototype source** (`AEROBRIDGE_SOURCE_CLEAN.zip` → `aerobridge-share-preview/`): `client/src/pages/Home.tsx` (363 lines, the entire application — all five screens live in this one file), `client/src/index.css` (408 lines, the complete design system), `client/src/App.tsx`, `client/index.html`, `client/src/const.ts`, `client/src/components/Map.tsx`, `client/src/components/ManusDialog.tsx`, `client/src/contexts/ThemeContext.tsx`, `server/index.ts`, `ideas.md`, `package.json`. Every claim marked "confirmed in source" below was independently re-derived from these files during this pass — by direct reading, `grep`, and manual CSS-cascade tracing — not inherited from any audit's citation.
- **`ideas.md`** ("AeroBridge Share Preview — Design Ground Truth"), the single highest-priority evidence artifact in the package per the source-priority order this audit follows. Read in full; quoted directly where it governs a decision.
- **7 rendered screenshots** (55514/17/19/21/23/26/28.jpg): Progression, Practice (Learn mode), Scenarios, Growth Record × Record/History/Reports tabs, Progress Tracking. All at mobile width (~360–430px, Android Chrome, live `manus.space` preview host). **No desktop or tablet screenshot exists anywhere in the evidence package** — every desktop/tablet-width claim in this report is CSS-derived, not visually confirmed, and is labeled accordingly.
- **All 9 unified audits** (ChatGPT, Claude, DeepSeek, Gemini, Grok, Kimi, Manus, Qwen, v0.dev), read in full and evaluated as analytical evidence — not as truth, and not by vote.

**Files that could not be fully evaluated:** None were unopenable. One reliability caveat is recorded explicitly: the **Kimi** audit contains multiple claims directly contradicted by the source (color tokens that don't match any value in `index.css`; a claim that the Practice/Terminal and Scenarios screens are "missing or heavily simplified" in source, when they are in fact the most fully-built parts of the application; an invented cross-audit "scorecard" with quotes attributed to other audits that do not appear in those audits' actual text). Two other audits (Manus, and this synthesis independently) flagged the same file as unreliable. Kimi's specific factual claims are therefore **not cited as evidence anywhere in this report**; where Kimi raised a generic suggestion that happens to be independently verifiable against source, it is credited to the verification, not to Kimi.

---

## A. Executive Decision

### Overall direction: **Preserve and Refine**

This is not a close call. `ideas.md` — the project's own design-ground-truth document, the highest-priority source in this evaluation — states it directly: *"This is a reference-preservation project, not a redesign. The existing AeroBridge Flight Deck Console prototype is the ground-truth visual and interaction reference."* Independently of that instruction, 8 of the 9 source audits reached the identical verdict ("targeted revision," "focused revision pass," "controlled hardening pass" — different words, same conclusion) using their own reasoning before any cross-comparison. This synthesis's own direct source inspection agrees for the same reason all nine did: the visual identity is distinctive and coherent, the five-screen loop is genuinely wired end-to-end (not a mockup pretending to connect), and the problems found are concentrated, specific, and fixable without touching architecture, navigation structure, command logic, or the scoring model.

The product does not need new features, a new information architecture, or a visual reset. It needs a **truthfulness and integrity pass**: several places where the interface currently says something happened when it didn't, shows a number that doesn't reconcile with the data behind it, or presents a state that misleads rather than informs — plus a systematic accessibility and design-token cleanup that is real but entirely additive (nothing needs to be removed or restructured to fix it).

### The three most important decisions

**1. Fix the trust/evidence-integrity cluster before anything else.** A brand-new trainee's first interaction with the product's core screen (Practice) is a fabricated red error message they did nothing to cause. Submitting nothing silently logs a real command. Headline numbers ("3/8 stages," "23/40 scenarios," a scenario category — "Exchanges & Refunds" — that doesn't exist in the data) don't add up to the data rendering beneath them. Twelve visible controls (Search, Backup, Filters, Sort, and others) look actionable and only fire a toast. Every one of these is independently confirmed in source, not inferred from an audit's description, and every one directly undermines the one thing this product's mission depends on: a trainee's ability to trust what the interface is telling them. This is priority one specifically *because* it is cheap to fix (conditional-render and copy changes, not architecture) and disproportionately damaging left alone.

**2. Fix the Terminal's two verified integrity regressions.** The Terminal is the product's architectural center — the only screen with its own later-pass design-token layer, the only nav item visually emphasized on mobile, the screen every other screen's "next action" button routes back to. Two specific, source-verified defects sit inside it: switching between Learn/Practice/Assessment modes does not reset command history or hint count, so an Assessment score can silently inherit activity from Learn or Practice without any warning to the trainee — a direct threat to the credibility of the one score this product exists to produce. Separately, a CSS cascade conflict (a later, same-specificity mobile rule overriding an earlier, deliberate one) currently resolves the mobile command-input font size to 15px instead of the intended 16px, which is below the threshold that prevents iOS Safari from auto-zooming on focus — undoing, by accident, mobile engineering the product's own CSS comments show was done deliberately.

**3. Close the accessibility and design-system-consolidation gaps as a systemic pass, not five isolated patches.** The primary CTA's text/background contrast measures 2.98:1 against a 4.5:1 requirement (self-computed from the actual token values, independently cross-confirmed by four of the nine audits computing the same ratio from the same hex codes). The `--text-faint` token — used for metadata across every screen — measures 3.66:1 and 3.18:1 on its two primary surfaces, also failing. Five visually tab-like control groups expose zero ARIA selection semantics. Two parallel color-token systems exist with different hex values for the same semantic role. None of these require new visual design; they require the existing, already-strong system to be finished and reconciled with itself.

### What this synthesis explicitly does **not** recommend, and why it matters that it doesn't

No redesign of the Flight Deck Console identity. No new information architecture. No new screens. No backend, authentication, or engine work (`ideas.md` explicitly prohibits this for the current preview). No RTL/Arabic implementation *this phase* — that toggle is a scope decision requiring a product answer before engineering time is spent, not a routine build task (§L). No gamification, gimmicks, or "modernization" of the interaction model. Everything in this report is a hardening pass on a foundation the evidence says is already sound.

---

## B. Product and Design Principles to Preserve

Every item below was independently re-confirmed against source or `ideas.md` during this pass, not simply inherited from an audit's claim of it. Nothing in this report recommends changing any of these; several sections below explicitly warn against side-effects that would erode one of them while fixing something adjacent.

**1. The Flight Deck Console visual identity as a whole.** Deep-navy foundation (`--navy-950:#050914` through `--navy-750:#16213c`), restrained Vector Blue accent (`--blue:#6f8fff`), monospace command/readout typography, atmospheric restraint over decoration. `ideas.md` names this identity explicitly as the ground truth to preserve. *Acceptable modification:* adjusting specific token **values** for contrast compliance (§F) without changing the palette's identity or relationships. *Do not:* replace, lighten, "modernize," or genericize this system.

**2. The Terminal's architectural centrality.** Confirmed in source: first in document order, full-width, the only screen with its own later-pass token refinement (the `--ab-*` "AeroBridge Elevation Directive" layer), the only nav item with deliberate mobile visual emphasis (`.is-primary`, confirmed styled and visible in every mobile screenshot), the only screen with a purpose-built Focus Mode. *Do not* turn the Terminal into a card among cards, and evaluate any future screen addition against whether it respects this hierarchy.

**3. The five-stage loop and its real cross-screen handoffs.** `ideas.md` names the exact sequence: *"Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action."* Confirmed in source: this is not decorative — `setPracticeContext` genuinely carries context from Progression, Scenarios, Growth, and Tracking into Practice; finishing an Assessment writes a real `localStorage` record that Growth and Tracking immediately reflect. This is the product's most substantial piece of working architecture. *Acceptable modification:* none needed. *Do not:* merge Growth Record and Progress Tracking into a single screen (one specific recommendation surfaced in the audit set) — `ideas.md` names them as two distinct stages of the canonical loop, and they operate at different evidence grains (skill-level mastery vs. session-level trend); reducing the metric *redundancy* between them (§F) is a different, smaller, acceptable change from removing either as a distinct destination.

**4. The Learn / Practice / Assessment structure as a pedagogical concept.** Genuinely different Coach copy and hint-visibility rules per mode, matching how real operational training separates guided practice from evaluation. *Acceptable modification:* fix the state-bleed between modes (§E, MSA-007) without flattening the three-mode distinction that makes them worth having separately.

**5. Focus Mode.** A deliberate, CSS-driven immersive state (`body:has(.focus-mode){overflow:hidden}`) that hides non-essential chrome around the Terminal. *Acceptable modification:* add the missing keyboard focus-trap and Escape handling (§E, MSA-012) — additively, alongside the existing mechanism, not as a replacement for it.

**6. The `prefers-reduced-motion` implementation.** Confirmed in source to be more thorough than several audits initially gave it credit for: a global `!important` catch-all plus multiple component-scoped refinements, including one rule at `index.css:217` that explicitly names `.terminal-caret` — meaning the caret **does** already respect reduced motion (a claim to the contrary in two of the nine audits does not survive tracing the full cascade; see §I). This is a genuine, above-average accessibility strength. Preserve exactly.

**7. The Progress Tracking chart's `<details>`/table alternative.** Confirmed genuinely wired to the same data driving the visual bars — not a decorative stub. The single strongest accessibility pattern in the codebase. Use it as the template for any future data visualization; do not replace the hand-built chart with a charting library merely because one (`recharts`) is an installed dependency — no evidence in this package shows the current pattern is insufficient.

**8. Deliberate, evidenced mobile input engineering.** Confirmed in source: 16px input font specifically to defeat iOS Safari's auto-zoom (documented intent, though currently undermined by a cascade regression — §E, MSA-008), `position: sticky` command input pinned above `env(safe-area-inset-bottom)`, and a purpose-commented two-row terminal-header restructuring at the 360px breakpoint. This is careful, intentional work; a future contributor should recognize it as such rather than "cleaning it up" by accident while fixing the regression.

**9. The contextual, domain-specific copy voice.** `ideas.md` states it directly: *"Prefer contextual labels such as Start, Resume, Review, and Retry over generic SaaS wording."* Confirmed as the current pattern throughout (Resume scenario, Review result, Retry assessment). *Do not* genericize this toward typical SaaS phrasing while fixing copy elsewhere (§E, §F).

**10. The command-history keyboard recall (Arrow Up/Down) in the Terminal input.** A genuine, correctly-implemented power-user feature. No change needed beyond, optionally, a small discoverability affordance (§F) — not a change to the mechanism itself.

**11. The honesty-disclosure instinct, where it already exists.** The Terminal's "LOCAL TRAINING SIMULATION" / "RESPONSE MODEL / ILLUSTRATIVE · VERIFY WITH YOUR COURSE MATERIAL" labeling is exactly the right pattern — it is simply not yet applied consistently to every surface that needs it (§E, MSA-003). Extend this pattern; do not invent a different one.

---

## C. Critical Problems

Genuine high-impact problems only — each independently verified against source in this pass, not inherited from an audit's description.

| ID | Problem | Evidence | User / Product Impact | Severity | Decision |
|---|---|---|---|---|---|
| MSA-001 | Coach panel's default, pre-command state renders a fabricated red `FORMAT ERROR · CHECK ENTRY` beneath a correctly neutral `AWAITING COMMAND` label | `Home.tsx` — `latestEntry?.response ?? "FORMAT ERROR · CHECK ENTRY"` fallback; `.coach-block code{color:var(--red)}` in `index.css`; visible pixel-for-pixel in the supplied first-load Practice screenshot | A new trainee's first impression of the product's central screen is an error they did not cause. Directly contradicts a "calm, precise, trustworthy workstation" positioning at the worst possible moment — first use. | **Critical** | MUST FIX |
| MSA-002 | Submitting an empty command is silently coerced to `"FQD"` and executed as a real command | `Home.tsx` — `const nextCommand = command.trim().toUpperCase() \|\| "FQD"`, confirmed exact line; the resulting entry is logged into `commandHistory` and reported to the trainee via a success toast | A trainee can generate a false command-history entry, and potentially a false assessment-evidence event, by submitting nothing. In a product whose product is trustworthy evidence, this is a direct integrity defect, not cosmetic. | **Critical** | MUST FIX |
| MSA-003 | Headline numbers across Progression, Scenarios, and Growth do not reconcile with the data rendering beneath them | `Home.tsx` — "3 / 8 stages" against a 6-item `levels` array (and only 4 items in the visible milestone list); "23 / 40 scenarios" against a 5-item `scenarios` array, one of whose displayed categories ("Exchanges & Refunds") exists nowhere in that array; "LOG 04 / 12" against 3 rendered history rows — all three visible directly in the supplied screenshots | A trainee who looks closely finds the product's own numbers don't add up — the fastest way to lose confidence in a product whose stated value is trustworthy evidence. | **Critical** | MUST FIX (derivation) / NEEDS VALIDATION (whether larger real totals are future content) |
| MSA-004 | 12 distinct visible controls (Search, Profile, Language, "My route," "View map," "See all stages," Growth's "View evidence/See patterns/View history," Scenarios' "Filters," Growth's "Backup") perform no real action and only fire a generic toast | `Home.tsx` — every listed handler calls `toast.success(...)` or `toast.info(...)` with static copy and no state change, route change, or data mutation; confirmed by direct read of each handler | The single most-repeated "looks functional, isn't" pattern in the product. Real, working CTAs sit visually beside fake ones with no way for a trainee to tell them apart in advance. | **High** | SHOULD FIX (tiered — see §E) |
| MSA-007 | Learn/Practice/Assessment modes share `commandHistory` and `hintCount` with no reset or isolation on mode switch | `Home.tsx` — `setMode(item); setSessionComplete(false);` is the entire mode-switch handler; nothing clears history or hint count. `assessmentScore(commandHistory, hintCount)` runs over the full shared history regardless of which mode produced each entry. The Assessment tab's "No hints" label is static text, not derived from the actual count. | An Assessment score — the one artifact this product exists to produce with integrity — can silently include activity (and hint usage) from Learn or Practice, with the UI actively telling the trainee "no hints" while that may be false. This is the most serious finding in the report relative to the product's actual mission. | **Critical** | MUST FIX |
| MSA-008 | Mobile Terminal command input resolves to 15px font size in Normal mode, not the intended 16px | `index.css` — an unconditional, later "AeroBridge Elevation Directive" rule sets `.page-practice .terminal-input input{font-size:16px}`; a still-later rule of **identical selector specificity**, inside `@media(max-width:739px)`, sets the same selector to `font-size:15px`. CSS resolves same-specificity ties by source order — the later rule (15px) wins. Independently re-derived in this pass by tracing both exact rules against the actual file. | 15px is below the well-established 16px threshold that prevents iOS Safari from auto-zooming on input focus — the exact failure the product's own 16px rule elsewhere was clearly written to prevent. A one-line CSS regression undoes deliberate mobile engineering on the product's single most-used input, on its dominant device class. | **High** | MUST FIX |
| MSA-013 | Primary button text/background contrast measures 2.98:1 | `index.css` — `.primary-button{background:var(--blue):#6f8fff; color:#fff; font-size:12px; font-weight:700}`. 12px/700 does not qualify for WCAG's large-text exception (requires ≥18.66px bold). Self-computed via the WCAG relative-luminance formula against the actual token values; independently cross-confirmed by four of the nine audits computing the identical ratio. | The single most-repeated, highest-intent interactive element in the product ("Resume pricing workflow," "Open recommended practice," and every other primary CTA) fails WCAG AA for a meaningful fraction of users. | **High** | MUST FIX |
| MSA-019 | Three declared display fonts (Space Grotesk, IBM Plex Mono, Cairo) are not loaded | `client/index.html` — the Google Fonts `<link>` block is present only inside an HTML comment explicitly marked "THIS IS THE START OF A COMMENT BLOCK, BLOCK TO BE DELETED"; zero `@font-face` rules exist anywhere in `index.css`; directly confirmed in this pass (not inherited from an audit citation — this synthesis had direct access to `index.html`, which two of the nine individual audits note they lacked) | If unaddressed, the product's entire distinctive typographic identity — the specific fonts named in `ideas.md`'s own style decisions — silently renders in generic system-UI fallback fonts in every real browser. Affects every screen simultaneously. | **High** | MUST FIX |

---

## D. Master Decision Matrix

Every significant issue identified across the full evidence package, adjudicated independently. "Source" cites which audit(s) raised the issue, or "Independent" where this synthesis identified it directly and no source audit raised it in this form. Classification uses only the six approved categories.

### D.1 — Trust, Evidence Integrity & Content Honesty

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Tech. Feasibility | Impact | Confidence | Cost | Risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MSA-001 | Interaction/Trust | Coach default state must be neutral ("Awaiting command"), never error-styled, before any command exists | MUST FIX | Direct source + screenshot | Critical (first-use trust) | Strengthens stated identity | High — conditional-render change only | High | High | Low | Low | Multi-audit 8/9 (all but Kimi's unreliable claims) |
| MSA-002 | Interaction/Safety | Empty submit must be a no-op with inline validation, never coerced to a command | MUST FIX | Direct source | Critical (evidence integrity) | Strengthens stated identity | High — one conditional check | High | High | Low | Low | Multi-audit 8/9 |
| MSA-003 | Content/Data | All headline counts must derive from the arrays they summarize, or be explicitly labeled illustrative/future content | MUST FIX (derivation) | Direct source + screenshots | Critical (product credibility) | Strengthens stated identity | High for derivation; content-dependent for real totals | High | High | Low (derivation) / Med (content decision) | Low | Multi-audit 9/9 |
| MSA-004 | Interaction/Trust | Each of 12 toast-only controls must be wired to real behavior, honestly relabeled/disabled, or removed — case by case, not batched | SHOULD FIX | Direct source | High (cumulative trust erosion) | Strengthens stated identity | Mixed — most UI-only; Search is Engine-dependent | High | High | Low–Med | Low | Multi-audit 9/9 |
| MSA-005 | Interaction/Trust | "Backup" must not claim data protection it doesn't perform — relabel as preview-only or implement a real local export | SHOULD FIX | Direct source | High (implies data safety, specifically) | Neutral | High if relabeled; Med if implemented | High | High | Low | Low | Claude, ChatGPT, Qwen, v0.dev |
| MSA-006 | Content | "Operationally ready" and similar certification-grade language must be scoped to what a local heuristic score can actually support | SHOULD FIX | Direct source + product-fit reasoning | High (if ever used with real learners) | Neutral — copy change only | High | Med–High | Med | Low | Low | ChatGPT, Manus |
| MSA-029 | Interaction | Scenarios' sort control should be wired to existing sortable fields (difficulty/duration/category) — no new data model needed | SHOULD FIX | Direct source | Med | Neutral | High — data already present | Med | High | Low | Low | Claude, ChatGPT, DeepSeek |
| MSA-028 | Interaction | Scenarios' "Filters" button should be removed or merged — it duplicates the adjacent, already-functional `filter-tabs` row | SHOULD FIX | Direct source | Med (confusing duplication) | Simplifies, doesn't weaken | High | Med | High | Low | Low | Claude, DeepSeek, ChatGPT |

### D.2 — Terminal / Assessment / Practice

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Tech. Feasibility | Impact | Confidence | Cost | Risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MSA-007 | State/Structural | Command history and hint count must not silently carry across Learn→Assessment; disclose or isolate | MUST FIX | Direct source | Critical (assessment credibility) | Strengthens the mode concept | Med — state-management change, UI-safe interim exists | High | High | Med | Low (UI-only interim) | Grok, Qwen, v0.dev, DeepSeek, Claude, ChatGPT |
| MSA-008 | Responsive/Input | Mobile Terminal input font must resolve to 16px in Normal mode, not 15px | MUST FIX | Direct CSS cascade trace | High (iOS auto-zoom regression) | Restores stated intent | High — delete one CSS declaration | High | High | Low | Low | ChatGPT (independently re-derived in this pass) |
| MSA-009 | Behavioral | Practice/Learn modes never validate command sequence (Assessment-only check) | NEEDS VALIDATION | Direct source | Med — may be intentional | N/A pending decision | N/A | Med | Med | — | — | v0.dev |
| MSA-010 | Layout | Fixed 130px `.terminal-gap` spacer wastes a large share of the constrained mobile terminal viewport | SHOULD FIX | Direct CSS + screenshot | Med–High (worst on first/empty session) | Neutral — spacing only | High | Med | High | Low | Low | v0.dev |
| MSA-011 | State | No processing/loading state between command submit and response | COULD IMPROVE | Direct source | Low–Med | Neutral | Med | Low | Med | Low | Low | Manus, DeepSeek |
| MSA-012 | Accessibility | Focus Mode needs a keyboard focus-trap, Escape handling, and dialog semantics | SHOULD FIX | Direct source | Med (keyboard/AT users) | Additive to existing pattern | Med | Med | High | Med | Low | DeepSeek, Kimi, Qwen, v0.dev, Claude |
| MSA-025 | Accessibility/Responsive | Skill-row hover-preview: desktop/tablet mechanism (hover+focus-visible) is correct and must not change; mobile (<740px) removes the content from layout entirely | SHOULD FIX (mobile only) | Direct CSS | Med (mobile learners lose coaching content) | Preserves working desktop pattern | Med | Med | High | Low | Low | Claude (resolving a Qwen/DeepSeek vs. Claude/Kimi conflict — §I) |
| MSA-043 | Interaction | Per-command toasts duplicate persistent Terminal history feedback | COULD IMPROVE | Direct source | Low (noise over long sessions) | Neutral | High | Low | Med | Low | Low | ChatGPT, Claude, v0.dev, Kimi |

### D.3 — Accessibility & Design-System Foundations

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Tech. Feasibility | Impact | Confidence | Cost | Risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MSA-013 | Color/Contrast | Primary-button text/background pairing must reach ≥4.5:1 | MUST FIX | Self-computed WCAG math (2.98:1) | High | Preserves palette, adjusts one value | High | High | High | Low | Low | Claude, ChatGPT, v0.dev, Qwen (independently computed) + this synthesis |
| MSA-014 | Color/Contrast | `--text-faint` must reach ≥4.5:1 against its actual rendered surfaces (3.66:1 / 3.18:1 measured) | MUST FIX | Self-computed WCAG math | High (affects metadata on every screen) | Preserves low-emphasis role via other means | High | High | High | Low | Low | Claude, ChatGPT, v0.dev, Gemini, DeepSeek (independently computed) + this synthesis |
| MSA-015 | Components | Add `role="tab"`/`aria-selected` or `aria-pressed` (as behavior warrants) to all 5 tab-like control groups | SHOULD FIX | Direct source — zero occurrences confirmed by count | High (screen-reader users) | Additive only | High | High | High | Low | Low | Multi-audit 8/9 |
| MSA-016 | Components | `AnimatedBar` progress elements need `role="progressbar"` + value semantics, not a bare `<i>` + `aria-label` | SHOULD FIX | Direct source | Med | Additive only | High | Med | High | Low | Low | Gemini, Claude, Qwen, v0.dev, Manus |
| MSA-017 | Navigation/Landmarks | Add `<main>` landmark, skip link, and `aria-current` to the desktop side-nav (bottom-nav already has it) | SHOULD FIX | Direct source | Med (keyboard/AT efficiency) | Additive only | High | Med | High | Low | Low | Multi-audit 7/9 |
| MSA-018 | Overlays | Mobile drawer, Reference popover, and search need confirmed focus-trap, Escape, and return-focus behavior | SHOULD FIX | Direct source + reasoning | Med–High (keyboard/AT users) | Additive only | Med | Med | Med | Low | Low | Multi-audit 6/9 |
| MSA-019 | Typography | Restore loading for all three declared font families | MUST FIX | Direct `index.html` read (this pass) | High (identity-wide) | Restores stated intent | High | High | High | Low | Low | Claude, ChatGPT (independently confirmed) + this synthesis |
| MSA-020 | Accessibility | Remove `maximum-scale=1` from the viewport meta tag | SHOULD FIX | Direct `index.html` read (this pass) | Med (low-vision users) | Neutral | High | Med | High | Low | Low | Qwen, Claude + this synthesis |
| MSA-021 | Design tokens | Consolidate the base and `--ab-*` token layers into one canonical set, extending outward from `--ab-*` | SHOULD FIX | Direct source — confirmed differing hex for equivalent roles | Low direct / Med maintainability | Strengthens system coherence | Med | Med | High | Med | Low | Claude, ChatGPT, DeepSeek, v0.dev, Kimi, Grok |
| MSA-022 | Touch targets | Raise sub-44px interactive elements (icon-button 38px→35px→33px across breakpoints, mode-tabs 34px) toward 44×44 where feasible | COULD IMPROVE | Direct CSS | Low–Med (still passes WCAG 2.2 AA 24×24 minimum) | Minor sizing only | Med | Med | Med | Low | Low | v0.dev, Claude, DeepSeek |
| MSA-023 | State system | Define visual treatment for the remaining 11 of 14 declared `SystemState` values not currently styled | COULD IMPROVE | Direct CSS — 3 of 14 styled | Low today (no seed data triggers the gap) | Future-proofing | Med | Low | High | Med | Low | Manus, ChatGPT, Qwen, DeepSeek |
| MSA-024 | Accessibility | `.is-secondary-view{display:none!important}` removes Growth's inactive tab panels from the accessibility tree — fold into MSA-015's fix | SHOULD FIX | Direct CSS | Med | Additive | High | Low | Med | Low | Low | Claude |

### D.4 — Content, Information Architecture & Navigation

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Tech. Feasibility | Impact | Confidence | Cost | Risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MSA-026 | Content/IA | Customer Service track must show an honest "not yet available" state instead of Technical-track milestones under a Service label | SHOULD FIX | Direct source | High (misrepresents curriculum depth) | Neutral — uses existing empty-state pattern | Med — content-dependent for the real fix | Med–High | High | Low (empty state) | Low | Claude, Qwen, ChatGPT, DeepSeek, Manus |
| MSA-027 | Data semantics | Skill-trend arrow color/direction must map to favorability, not raw numeric direction | SHOULD FIX | Direct source | Med (currently reads backwards) | Neutral | Med | Med | Med | Low | Low | Qwen, ChatGPT, Claude |
| MSA-030 | Navigation | Mobile bottom-nav's visual order (Progression, Scenarios, Practice, Growth, Tracking) doesn't match the "YOUR ROUTE / 0N" breadcrumb numbering | SHOULD FIX | Direct source | Med (wayfinding) | Preserves the deliberate Practice-centering | High — derive numbering from display order, or drop numeric breadcrumbs | Med | High | Low | Low | DeepSeek, ChatGPT, Claude |
| MSA-031 | Content | "Route" is overloaded (mobile nav short-label vs. universal breadcrumb prefix) | COULD IMPROVE | Direct source | Low | Neutral | High | Low | Med | Low | Low | Claude |
| MSA-034 | Navigation | Hamburger drawer content reportedly duplicates the bottom nav entirely | NEEDS VALIDATION | Single-source claim, not independently re-verified this pass | Low–Med | N/A pending confirmation | N/A | Low | Low | — | — | Claude |
| MSA-035 | Layout | Progress Tracking's route-line label truncates at mobile width | COULD IMPROVE | Direct source | Low | Neutral | High | Low | Med | Low | Low | Claude, DeepSeek |
| MSA-036 | Layout | Long scenario titles may crowd the Practice task-strip badge at narrow widths | NEEDS VALIDATION | Direct data flow, rendered behavior unconfirmed | Low–Med | N/A pending confirmation | N/A | Low | Med | — | — | ChatGPT, Claude, Kimi |

### D.5 — Responsive Behavior

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Tech. Feasibility | Impact | Confidence | Cost | Risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MSA-032 | Tablet (740–1099px) | Content grids go multi-column at 740px while navigation stays mobile-style until 1100px — validate before deciding whether this reads as intentional | NEEDS VALIDATION | Direct CSS breakpoints, zero screenshot coverage | Unknown until tested | N/A pending decision | N/A | Med | Low | — | — | Multi-audit 6/9 |
| MSA-033 | Mobile floor (<360px) | No dedicated sub-360px rules; the 320px floor (`body{min-width:320px}`) relies entirely on inherited 360px styles | NEEDS VALIDATION | Direct CSS | Unknown until tested | N/A pending decision | N/A | Med | Low | — | — | Grok, Claude, DeepSeek, Manus |

### D.6 — Design-System Hygiene (non-user-facing)

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Tech. Feasibility | Impact | Confidence | Cost | Risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MSA-037 | CSS hygiene | `.bottom-nav`'s `grid-template-columns` is declared 4 times (1 stale + 3 reinforcing); remove the 3 redundant declarations, keep one | COULD IMPROVE | Direct CSS cascade trace — **not a live bug**, see §I | None (rendered output already correct in every screenshot) | Neutral | High | Low | High | Low | Low | Claude (exact diagnosis), Manus, ChatGPT, this synthesis |
| MSA-038 | Spacing/radius | Ad-hoc spacing, radius, and shadow values are not drawn from a documented scale | COULD IMPROVE | Direct CSS | Low direct / Med maintainability | Neutral if values are preserved, just tokenized | Med | Low | Med | Low | Low | DeepSeek, ChatGPT, Claude, Manus |
| MSA-039 | Visual noise | Progress Tracking's secondary KPI cards use decorative `clip-path`/gradient ornamentation that doesn't communicate data | COULD IMPROVE | Direct CSS + screenshot | Low | Simplifies, doesn't weaken | Med | Low | Med | Low | Low | DeepSeek, Claude |
| MSA-040 | Dead code | `ErrorBoundary.tsx`/`NotFound.tsx` exist but aren't mounted; `Map.tsx` (155 lines) is fully built but unused/unimported | COULD IMPROVE / DEFER | Direct source — import trace confirms zero references | Low (no current user impact) | N/A | High (documentation only this phase) | Low | High | Low | Low | Qwen, v0.dev, Claude, ChatGPT, Manus, DeepSeek |
| MSA-041 | Portability | `index.css` references external `/manus-storage/...` image URLs not included in the local source archive | COULD IMPROVE | Direct source, confirmed via screenshot vs. archive comparison | Low (handoff risk only) | N/A | Med | Low | Med | Low | Low | ChatGPT, Manus, Claude |
| MSA-042 | Dead code | The `"hint-dependency"` `ErrorKind` legend entry is never producible by the actual command-matching logic | COULD IMPROVE | Direct source | Low | Neutral | High | Low | Med | Low | Low | Qwen, Claude |

### D.7 — Arabic / RTL (scope decision)

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Tech. Feasibility | Impact | Confidence | Cost | Risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MSA-044a | Content/i18n | Interim: the EN/AR toggle must stop implying a working language switch — disable/relabel until a scope decision is made | MUST FIX (interim) | Direct source — toast-only, no `dir`, no translation, `--font-ar` defined but unused, `lang="en"` hardcoded | High (mission-relevant false affordance) | Neutral — copy/state change only | High | High | High | Low | Low | Multi-audit 9/9 |
| MSA-044b | Content/i18n/Architecture | Full RTL/i18n build-out (translation layer, `dir="rtl"`, bidi isolation for commands/codes, mirrored layout, `--font-ar` wired to `[dir="rtl"]`) | NEEDS VALIDATION (product scope decision required first) | `ideas.md` prohibits new architecture; no translation content exists in the package | High if in scope | Extends the system properly if built | Low this phase — genuine architecture/content effort | High | Med | High | Med–High if rushed | Multi-audit 9/9 |

### D.8 — Preserve and Reject entries (matrix completeness)

*Fully detailed in §B and §I respectively; included here so the matrix itself uses all six approved classifications, not only four.*

| ID | Area | Specific Decision | Classification | Evidence | User Impact | Design Consistency | Tech. Feasibility | Impact | Confidence | Cost | Risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MSA-P01 | Visual identity | Flight Deck Console system (see §B.1) | PRESERVE | `ideas.md` + direct source | Critical (brand/product identity) | N/A — is the standard | N/A | High | High | — | — | 9/9 + `ideas.md` |
| MSA-P02 | Architecture | Five-screen loop + real cross-screen handoffs (see §B.3) | PRESERVE | `ideas.md` + direct source | Critical (core working functionality) | N/A — is the standard | N/A | High | High | — | — | 9/9 + `ideas.md` |
| MSA-P03 | Interaction | Terminal-first architecture, Focus Mode, Learn/Practice/Assessment structure (see §B.2, B.4, B.5) | PRESERVE | Direct source | High | N/A — is the standard | N/A | High | High | — | — | 9/9 |
| MSA-P04 | Accessibility | `prefers-reduced-motion` implementation and the Progress Tracking accessible-chart pattern (see §B.6, B.7) | PRESERVE | Direct source | High | N/A — is the standard | N/A | High | High | — | — | This synthesis (corrects R-03); Claude |
| R-01–R-15 | Various | See §I for the full table (3 factual corrections + 12 unsupported/out-of-scope recommendations) | REJECT | See §I per row | See §I per row | N/A | N/A | See §I | See §I | — | — | See §I |

---

## E. Required Changes by Priority

### P0 — Blocking / Must Fix

*Required before the enhanced prototype can be considered ready for the next review stage. All nine are UI-only or copy/conditional-render changes — none require touching the command-matching logic, the scoring formula, or the data model.*

**MSA-001 — Neutral Coach default state**
- *Objective:* A first-time trainee's first interaction with Practice is calm and instructive, never alarming.
- *Current problem:* Before any command is submitted, the Coach panel renders `FORMAT ERROR · CHECK ENTRY` in red with a specific fabricated correction, directly beneath a correctly neutral `AWAITING COMMAND` label.
- *Exact change:* When `latestEntry` is undefined, render a neutral placeholder (e.g., "Submit a command to see workflow-specific coaching here") with the default/neutral text color — not `--red`, and not styled as a `<code>` error block.
- *Must remain unchanged:* The Coach's actual error-state behavior *after* a real invalid command — that pattern is correct and should fire exactly as it does today, just never before first input.
- *Reason:* Confirmed in source and screenshot; contradicts the product's stated "precision/trust" positioning at the single moment that positioning matters most.
- *Dependencies:* None. UI-only.
- *Risks:* None identified.

**MSA-002 — Empty submit is a no-op**
- *Objective:* The Terminal never records a command the trainee did not actually type.
- *Current problem:* `command.trim().toUpperCase() || "FQD"` silently substitutes and executes `FQD` for a blank submission.
- *Exact change:* If `command.trim() === ""`, do not call the submit handler at all. Show a brief inline message ("Enter a command before executing.") and take no other action — no history entry, no score change, no toast, no `FQD` execution.
- *Must remain unchanged:* Arrow Up/Down history recall must continue to work while the input is empty (do not disable the input itself — only block *submission* of an empty value); all existing valid-command matching (`AN`/`SS`/`FQD`/`FXP`, etc.) must be byte-for-byte unchanged.
- *Reason:* Confirmed in source; independently flagged by the majority of the nine audits; directly threatens evidence integrity.
- *Dependencies:* None. UI-only; explicitly does not touch the engine boundary.
- *Risks:* Regression-test all four valid command prefixes after the fix to confirm non-empty submissions are unaffected.

**MSA-003 (derivation half) — Headline counts must derive from real data**
- *Objective:* Every fraction or count shown is either true of the data it summarizes, or explicitly labeled as illustrative/future content.
- *Current problem:* "3 / 8 stages" (6-item `levels` array, 4 rendered milestones), "23 / 40 scenarios" (5-item `scenarios` array; "Exchanges & Refunds" category doesn't exist in the data), "LOG 04 / 12" (3 rendered history rows) — none reconcile.
- *Exact change:* Replace each hardcoded fraction with a value derived from its actual source array (`levels.length`, `scenarios.length`, actual rendered-row count), OR — where a larger real total is a genuine future-content plan rather than a bug — keep the larger number but add an explicit "N available now" qualifier so the two numbers coexist honestly.
- *Must remain unchanged:* The illustrative/local nature of the underlying data itself — this is not a request to fabricate 8 real stages or 40 real scenarios; it's a request that whatever is shown is internally consistent.
- *Reason:* Confirmed in source and, in three cases, directly visible in the supplied screenshots; unanimous across all nine audits.
- *Dependencies:* UI-only for the derivation fix. The separate question of whether 8/40 should eventually be real, larger totals is a content decision — see §L.
- *Risks:* None for the derivation fix itself.

**MSA-007 — Terminate mode-switch state bleed**
- *Objective:* An Assessment score can be trusted to reflect only what happened during that Assessment.
- *Current problem:* Switching Learn → Practice → Assessment does not reset `commandHistory` or `hintCount`; `assessmentScore()` runs over the entire shared history regardless of origin; the Assessment tab's "No hints" label is static text that does not reflect the actual count.
- *Exact change (UI-safe interim, no engine change required):* On entering Assessment mode, if `commandHistory.length > 0` or `hintCount > 0`, show an explicit disclosure ("N prior commands / N hints carried into this session") rather than a silent or falsely-clean state. Make the "No hints" label conditional on the actual `hintCount`, not static.
- *Must remain unchanged:* Do not silently change the scoring formula or auto-reset history without a product/learning-design decision on whether modes should be continuous or isolated by design — that decision belongs in §L, not in this UI fix.
- *Reason:* Confirmed in source; the single finding in this report most directly connected to the product's actual mission (trustworthy assessment evidence).
- *Dependencies:* State/data-layer change (UI-only), no engine-boundary change required.
- *Risks:* Low if scoped exactly as above; do not conflate this fix with a broader engine rewrite.

**MSA-008 — Fix the mobile Terminal input font-size cascade regression**
- *Objective:* Restore the product's own documented iOS auto-zoom prevention.
- *Current problem:* A later, same-specificity mobile media-query rule sets `.page-practice .terminal-input input{font-size:15px}`, overriding the deliberate `16px` rule that appears earlier in the same file for the same selector.
- *Exact change:* Delete the `font-size:15px` declaration (or change it to `16px`) inside the `@media(max-width:739px)` block under the "Center the primary workspace" comment section, so the computed value is 16px at every viewport in Normal mode. Focus Mode's separate, higher-specificity rule already correctly retains a larger value and needs no change.
- *Must remain unchanged:* Every other property in that same rule block (`min-width:0`, button sizing) — only the one `font-size` value is wrong.
- *Reason:* Independently re-derived in this synthesis by tracing the actual CSS cascade; a one-line fix with outsized impact on the dominant device class for this product.
- *Dependencies:* None. Single CSS value.
- *Risks:* None; validate at 320/360/390/430px on iOS Safari and Android Chrome post-fix (§J).

**MSA-013 — Fix primary-button contrast**
- *Objective:* The product's highest-intent CTA is legible to all users.
- *Current problem:* White text on `--blue:#6f8fff` at 12px/700-weight measures 2.98:1, below the 4.5:1 required for non-large text.
- *Exact change:* Darken `--blue` for this specific pairing (or darken the text) until the shipped combination reaches ≥4.5:1. Test hover/active/focus/disabled states separately, as they may use different values.
- *Must remain unchanged:* The Vector Blue identity and the button's role as the product's single dominant CTA per screen — this is a value adjustment, not a redesign of the button.
- *Reason:* Self-computed via the WCAG relative-luminance formula against the actual token values; independently cross-confirmed by four separate audits computing the identical ratio from the identical hex codes.
- *Dependencies:* None. UI-only.
- *Risks:* None; re-measure after any adjustment.

**MSA-014 — Fix `--text-faint` contrast**
- *Objective:* Metadata and secondary text are readable for low-vision users and comfortable in long sessions.
- *Current problem:* `--text-faint:#5d6a85` measures 3.66:1 against `--navy-950` and 3.18:1 against `--panel-solid` — both fail the 4.5:1 required for the small sizes this token is actually used at.
- *Exact change:* Raise the token's luminance until it clears 4.5:1 against its most common rendered backgrounds (`--navy-950`, `--panel-solid`, `--navy-750`). Preserve the *low-emphasis role* through size, weight, and letter-spacing rather than through insufficient contrast.
- *Must remain unchanged:* The visual hierarchy this token serves (it should still read as quieter/secondary than `--text` and `--text-soft`) — only its absolute luminance needs to move.
- *Reason:* Self-computed; independently cross-confirmed by five of the nine audits computing consistent ratios against the identical hex value.
- *Dependencies:* None. Single token value; propagates everywhere by design.
- *Risks:* Re-check all three surface combinations after adjustment, not just one.

**MSA-019 — Restore font loading**
- *Objective:* The product renders in its designed typefaces, not silent fallbacks.
- *Current problem:* The Google Fonts `<link>` block in `index.html` sits inside a comment explicitly marked for deletion; zero `@font-face` rules exist; the three declared families (Space Grotesk, IBM Plex Mono, Cairo) are not loaded by any mechanism found in the source.
- *Exact change:* Re-enable the font-loading mechanism (restore the `<link>`, or self-host all three families) before any further visual QA is performed on this codebase — font metrics affect line length and wrapping for every other check.
- *Must remain unchanged:* The three specific families and their assigned roles (display / mono / Arabic) as declared in `index.css` tokens — this is a loading fix, not a typeface change.
- *Reason:* Directly confirmed in this pass via `index.html`; this is the largest single gap between design intent and shipped reality in the product.
- *Dependencies:* None technically, though sequence this first — it should ship before other typography/spacing polish, since it changes rendered text metrics.
- *Risks:* Low; verify computed `font-family` on a heading, a terminal command line, and (once MSA-044 progresses) Arabic body text.

**MSA-044a — Stop the language toggle from implying a working feature**
- *Objective:* The interface never promises a capability it does not have.
- *Current problem:* The EN/AR toggle changes only a local highlight and fires a success toast; no `dir`, no translation, no font switch occurs.
- *Exact change:* Until the scope decision in §L is made, disable the toggle or relabel it clearly (e.g., "Arabic — coming soon") rather than letting it complete a fake "success" interaction.
- *Must remain unchanged:* Nothing else about the topbar; this is the smallest possible interim fix pending the larger product decision.
- *Reason:* Confirmed in source; unanimous across all nine audits; directly relevant to the product's stated Saudi-market mission, making the current false affordance higher-stakes than an ordinary toast-only control.
- *Dependencies:* None for the interim fix. Full implementation is a separate, larger decision (§L, MSA-044b).
- *Risks:* None for the interim fix.

### P1 — High-Value Improvements

*Should follow P0. All are UI-only or content-labeling changes; none require engine or architecture work.*

**MSA-004 / MSA-005 — Resolve the 12 toast-only controls, case by case**
- *Objective:* Every visible affordance either performs its implied action, is honestly marked unavailable, or is removed — never all three states looking identical.
- *Current problem:* Search, Profile, Language, "My route," "View map," "See all stages," Growth's "View evidence/See patterns/View history," Scenarios' "Filters," and Growth's "Backup" all fire a generic toast in place of their implied action.
- *Exact change:* Triage individually, not as a batch: (a) **Backup** (MSA-005) — highest priority within this group because it specifically implies data protection; either implement a real local export or relabel clearly as "Preview only — no file is written." (b) **"View map"/"See all stages"/"View evidence"/"See patterns"/"View history"** — de-emphasize or relabel as preview/roadmap pending a product decision on whether each destination will exist. (c) **Search/Profile/Language** — same treatment; Language has its own dedicated fix (MSA-044a). (d) Where real functionality is cheap because the data already exists (Scenarios' sort — MSA-029), implement it rather than relabeling.
- *Must remain unchanged:* The controls that already work correctly nearby (e.g., Scenarios' functioning `filter-tabs`) — do not touch working affordances while fixing broken-looking ones.
- *Reason:* Confirmed in source for every listed control; the most-repeated single pattern across all nine audits.
- *Dependencies:* Mixed — most are UI-only; Search and deep filter/sort logic are content/engine-dependent if ever built out for real.
- *Risks:* Treating all twelve identically would under-prioritize Backup (data-safety implication) and over-prioritize low-stakes items — sequence individually per the tiering above.

**MSA-006 — Scope readiness/certification language to what local evidence supports**
- *Objective:* "Operationally ready" and similar phrases are never mistaken for a production competency judgment.
- *Current problem:* The Assessment debrief and Growth reports use "Operationally ready" and broad readiness framing at a local score threshold, without qualification.
- *Exact change:* Replace with scope-limited prototype vocabulary ("Strong local result," "Local session signal," "Review recommended") until a production competency rubric exists; keep the debrief's existing structure and categories.
- *Must remain unchanged:* The debrief's category structure, error taxonomy, and overall "evidence → recommendation" framing — this is a wording change, not a redesign.
- *Reason:* Confirmed in source; matters more once any real learner sees this copy outside a demo context.
- *Dependencies:* Content-only.
- *Risks:* None.

**MSA-010 — Reduce the fixed mobile terminal dead-space**
- *Objective:* The constrained mobile Terminal viewport is used for content, not empty space, especially on a first/empty session.
- *Current problem:* `.terminal-gap{height:130px}` is a single, unconditional, never-overridden rule that consumes a large share of a viewport already capped near 300–360px on mobile.
- *Exact change:* Remove or substantially reduce the fixed height; the existing `.terminal-active-line{margin-top:auto}` rule already anchors the input to the bottom of the flex container and can do this job without an additional fixed spacer.
- *Must remain unchanged:* The terminal's scrollable, flex-column structure and the bottom-anchored active line itself.
- *Reason:* Confirmed in source; visible as an oversized empty band in the supplied Practice screenshot.
- *Dependencies:* None. Single CSS rule.
- *Risks:* Low; re-check terminal appearance at 0, 1, and many history entries after the change.

**MSA-012 — Give Focus Mode a keyboard focus-trap and Escape handling**
- *Objective:* Keyboard and assistive-technology users are not able to tab out of an active Focus Mode into the surrounding browser chrome, and can always exit predictably.
- *Current problem:* Focus Mode is a full-screen visual/scroll-lock state (`body:has(.focus-mode){overflow:hidden}`) without a confirmed focus trap, Escape handler, or dialog semantics.
- *Exact change:* Add a focus trap scoped to the Terminal panel while Focus Mode is active, an Escape key handler that exits it, and `role="dialog"`/`aria-modal="true"` if it is being treated as modal — implemented alongside the existing scroll-lock, not replacing it.
- *Must remain unchanged:* The existing `:has()`-based scroll-lock mechanism and the visual behavior of Focus Mode itself.
- *Reason:* Confirmed gap in source; Focus Mode is independently rated the product's strongest single UX decision by multiple audits, making its accessibility completion high-value.
- *Dependencies:* None. UI/interaction-only.
- *Risks:* Test thoroughly with keyboard-only navigation before shipping — an incomplete trap is worse than none.

**MSA-015 / MSA-016 / MSA-017 / MSA-018 / MSA-024 — Systemic accessibility-semantics pass**
- *Objective:* Assistive technology users can perceive selection state, progress, page structure, and overlay behavior throughout the product — as one shared component pattern, not five separate patches.
- *Current problem:* Zero `role="tab"`/`aria-selected`/`aria-pressed` across five tab-like control groups (MSA-015); `AnimatedBar` uses a bare `<i>` + `aria-label` instead of `role="progressbar"` (MSA-016); no `<main>` landmark or skip link, and the desktop side-nav lacks `aria-current` though the bottom-nav has it (MSA-017); overlays (mobile drawer, Reference popover, search) lack confirmed focus-trap/Escape/return-focus (MSA-018); `.is-secondary-view{display:none!important}` removes Growth's inactive tab panels from the accessibility tree entirely, not just visually (MSA-024).
- *Exact change:* Build one shared tab/toggle pattern (apply `role="tablist"`/`role="tab"`/`aria-selected"` to controls that swap an entire panel — mode-tabs, growth-tabs — and `aria-pressed` to controls that filter/toggle without swapping a full panel); one shared progress-indicator pattern; add `<main>`/skip-link/`aria-current` to the shell; add dialog semantics to genuine overlays.
- *Must remain unchanged:* Current visual appearance of every one of these components — this is an attributes-only pass with no visual-design change required.
- *Reason:* Confirmed in source (exact-count verified: zero occurrences of the relevant ARIA attributes in the 363-line file); consistently identified across most of the nine audits.
- *Dependencies:* None. UI-only, additive.
- *Risks:* Low; sequence after MSA-021's token consolidation so shared components are built against one settled system rather than two.

**MSA-020 — Remove the pinch-zoom restriction**
- *Objective:* Users who need to zoom the interface can.
- *Current problem:* `client/index.html`'s viewport meta tag includes `maximum-scale=1`.
- *Exact change:* Remove `maximum-scale=1` from the viewport meta content string.
- *Must remain unchanged:* `width=device-width, initial-scale=1.0` and the rest of the meta tag.
- *Reason:* Directly confirmed in this pass; a one-line accessibility fix.
- *Dependencies:* None.
- *Risks:* None.

**MSA-021 — Consolidate the two design-token systems**
- *Objective:* One canonical set of semantic color tokens drives the entire product.
- *Current problem:* A base `:root` token layer coexists with a second, later `--ab-*` layer (the "AeroBridge Elevation Directive") using different hex values for equivalent semantic roles (e.g., `--green:#3ed598` vs. `--ab-success:#55d6a6`), the second scoped only to `.page-practice`.
- *Exact change:* Promote the `--ab-*` values to the canonical/base token set — its own code comment signals it as the more deliberate, more recent refinement — then remove the `--ab-*` namespace once every consumer references the base tokens.
- *Must remain unchanged:* The specific hex values themselves (use the `--ab-*` values as the surviving ones, not the older base values) — this is a consolidation, not a value redesign.
- *Reason:* Confirmed in source; a real future-maintenance hazard even though it produces no visible defect today.
- *Dependencies:* None. UI-only.
- *Risks:* Grep the stylesheet for any remaining `--ab-` reference after consolidation to confirm completeness.

**MSA-025 — Bring skill-row coaching content to mobile**
- *Objective:* Coaching detail available to desktop/tablet users via hover or keyboard focus is also available to mobile/touch users.
- *Current problem:* `.skill-hover-preview{display:none}` inside the mobile media query removes the content from layout entirely below 740px — not merely harder to reach.
- *Exact change:* On mobile, surface the equivalent content in the selected skill's detail panel via a tap/click interaction, rather than only via hover.
- *Must remain unchanged:* The desktop/tablet hover + `:focus-visible` dual-trigger mechanism, which is already correctly built and keyboard-accessible — do not alter it while fixing the mobile gap.
- *Reason:* Confirmed in source; resolves a direct three-way disagreement in the audit set (§I) about whether this pattern is accessible at all — it is, but only above 740px.
- *Dependencies:* None. UI-only.
- *Risks:* Low.

**MSA-026 — Honest empty state for the Customer Service track**
- *Objective:* Selecting a track never shows curriculum content that belongs to the other track.
- *Current problem:* The Technical/Customer Service toggle changes only the description paragraph; the milestone list beneath stays labeled and populated as Technical content regardless of selection.
- *Exact change:* Until real Service-track curriculum data exists, show an honest "not yet available" state for the milestone list when Customer Service is selected, rather than displaying Technical milestones under a Service label.
- *Must remain unchanged:* The Technical track's existing content and the toggle mechanism itself.
- *Reason:* Confirmed in source; misrepresents curriculum depth to a trainee evaluating which track to pursue.
- *Dependencies:* Content-dependent for the eventual real fix; UI-only for the honest empty-state interim.
- *Risks:* None for the interim fix.

**MSA-027 — Fix skill-trend arrow semantics**
- *Objective:* A skill's trend indicator reads correctly at a glance.
- *Current problem:* Trend arrow direction is mapped to literal numeric direction rather than favorability — mastered/good skills (92%, 88%) currently show a down-arrow, while weak/attention-needed skills (45%, 20%) show an up-arrow.
- *Exact change:* Map the arrow direction and color to whether the trend is favorable for that specific skill, not to the raw sign of the underlying number.
- *Must remain unchanged:* The underlying `tone`/`trend` data fields and the hover-tooltip text, which already correctly explains the intended meaning — only the icon-selection logic needs to change.
- *Reason:* Confirmed in source; currently produces a backwards-reading result the tooltip text alone cannot fully correct.
- *Dependencies:* None. UI-only.
- *Risks:* None.

**MSA-028 / MSA-029 — Scenarios' Filters and Sort**
- *Objective:* Every visible Scenarios control does what it appears to do.
- *Current problem:* "Filters" duplicates the already-functional `filter-tabs` row beside it; the sort `<select>` doesn't reorder the list, despite the scenario objects already carrying sortable fields (difficulty, duration, category).
- *Exact change:* Remove or merge the redundant "Filters" button; wire the sort control to the existing fields — no new data model required.
- *Must remain unchanged:* The working `filter-tabs` row itself.
- *Reason:* Confirmed in source; sort is the one toast-only control in the entire inventory cheap enough to implement for real rather than relabel.
- *Dependencies:* UI-only for both.
- *Risks:* None.

**MSA-030 — Reconcile mobile nav order with breadcrumb numbering**
- *Objective:* A trainee never sees a screen's breadcrumb number contradict its position in the bottom nav they just tapped.
- *Current problem:* The bottom nav visually reorders to [Progression, Scenarios, Practice, Growth, Tracking] to keep Practice centered, but "YOUR ROUTE / 0N" breadcrumbs are numbered from the underlying canonical array order, so the 2nd visual icon (Scenarios) shows "03" and the 3rd/center icon (Practice) shows "02."
- *Exact change:* Either derive the breadcrumb number from the actual display order, or remove the numeric component of the breadcrumb and keep only the descriptive text.
- *Must remain unchanged:* The deliberate Practice-centering itself — this is a numbering-derivation fix, not a navigation-order change.
- *Reason:* Confirmed via source logic; independently identified by three of the nine audits.
- *Dependencies:* UI/content-only.
- *Risks:* None.

### P2 — Optional / Later Improvements

*Lower-priority; can be deferred without materially affecting trust, safety, or core accessibility. Presented more concisely; all fields are still specified.*

| ID | Objective | Current problem | Exact change | Must stay unchanged | Reason | Dependencies | Risks |
|---|---|---|---|---|---|---|---|
| MSA-011 | Give command submission a felt "processing" moment | Response is instant/synchronous with no state in between | Add a brief (~150–300ms) processing indicator before the response renders | The instant simulation logic itself | Minor realism; not urgent since local sim has no real latency | UI-only | None |
| MSA-022 | Raise sub-44px touch targets where feasible | Icon-button 38px shrinking to 35px/33px across breakpoints; mode-tabs 34px | Increase toward 44×44 CSS px where layout allows without crowding | Compact operational density elsewhere (per `ideas.md`'s "compact mobile command rail") | Already passes WCAG 2.2 AA's 24×24 minimum; this is the more conservative 44×44 platform convention | UI-only | Watch for layout crowding at narrow widths |
| MSA-023 | Complete the declared state vocabulary | Only 3 of 14 `SystemState` values have distinct CSS treatment | Add visual treatment (or explicitly document as intentionally unstyled) for the remaining values | The 3 already-styled states | No current visible defect (no seed data triggers the gap); future-proofing only | UI-only | Low |
| MSA-031 | Reduce "Route" term overload | Same word is both a nav short-label and a universal breadcrumb prefix | Rename one usage for clarity | The other usage | Minor clarity gain | Content-only | None |
| MSA-035 | Prevent route-line label truncation | "VECTOR 03 / PRICING & T…" truncates on mobile | Shorten the label pattern or wrap instead of truncating | The route-line concept itself | Minor readability | UI-only | None |
| MSA-037 | Remove redundant CSS | `.bottom-nav` grid-template-columns declared 4×, 1 stale + 3 reinforcing | Delete the 3 redundant declarations, keep one 5-column rule | The final rendered 5-column behavior (already correct — see §I) | Hygiene only; confirmed **not** a live defect | UI-only | None — purely subtractive |
| MSA-038 | Establish a documented spacing/radius/shadow scale | Ad-hoc values throughout | Introduce scale tokens, map existing values onto them | Current visual spacing/radius (tokenize, don't redesign) | Maintainability | UI-only | Low if values are preserved exactly |
| MSA-039 | Reduce visual noise on Tracking KPI cards | Decorative `clip-path`/gradient ornamentation carries no data meaning | Simplify or remove the ornamentation | The KPI data itself and its hierarchy | Minor clarity gain | UI-only | None |
| MSA-040 | Document unused code for handoff clarity | `ErrorBoundary`/`NotFound` unmounted; `Map.tsx` unused | Document as intentionally out-of-loop; do not delete or wire up without a roadmap decision | Current behavior — nothing to fix visually | Handoff hygiene, not a design defect | Documentation-only this phase | None if left as-is |
| MSA-041 | Improve archive portability | CSS references external `/manus-storage/...` images not in the local zip | Document the asset dependency or bundle the images with the handoff package | The visual result once assets are present | Prevents silent visual regression in a clean build environment | Architecture/deployment-only | None |
| MSA-042 | Remove dead legend entry | `"hint-dependency"` `ErrorKind` never producible by current logic | Remove from the debrief legend, or wire a real path to it | The rest of the error taxonomy | Minor hygiene | UI-only | None |
| MSA-043 | Reduce toast noise in long sessions | Per-command toasts duplicate persistent Terminal history feedback | Reserve toasts for session-level events; let the Terminal own command-level feedback | Terminal history's existing feedback role | Reduces long-session noise without losing information | UI-only | None |

---

## F. Component-Level Specifications

Specific enough to implement without further interpretation. Only components with a confirmed, evidenced change are detailed below — per §3's rule against inventing changes to pad scope.

### F.1 — Primary Button (`.primary-button`)

- **Current state:** `background:var(--blue)` (`#6f8fff`); `color:#fff`; `font-size:12px`; `font-weight:700`; `border-radius:var(--radius-sm)` (11px). Used for every screen's single dominant CTA ("Resume pricing workflow," "Open recommended practice," "Resume scenario," etc.).
- **Problem:** Text/background contrast measures 2.98:1; fails WCAG AA's 4.5:1 requirement for non-large text (12px/700 does not qualify for the large-text exception).
- **Decision:** MUST FIX (MSA-013). Adjust `--blue`'s value for this pairing, or the text color, until ≥4.5:1 is reached.
- **Layout / Spacing / Dimensions:** Unchanged — no evidence any of these need to move.
- **Typography:** Unchanged (12px/700) unless the contrast fix requires a secondary adjustment; font-family fix is tracked separately (MSA-019).
- **Color:** The one value requiring change. Darken `--blue` specifically for this pairing, or use a darker action-blue token reserved for button backgrounds while preserving `--blue` elsewhere for accents.
- **Interaction states:** Hover/active/focus/disabled variants must each be independently re-measured after the base fix — a passing default state does not guarantee a passing hover state.
- **Responsive behavior:** No evidence of a responsive-specific issue; verify the fix holds at all breakpoints.
- **Accessibility requirements:** ≥4.5:1 contrast in every state; visible `:focus-visible` treatment (already present per source, confirm it survives the color change).
- **Preserve:** The button's role as the single dominant per-screen CTA; the Vector Blue brand association.
- **Reject:** Any proposal to reduce this button's prominence or replace it with a lower-contrast "quieter" treatment as a workaround — the fix is a color value, not a hierarchy change.

### F.2 — Terminal Command Input (`.terminal-input input`)

- **Current state:** Sticky-positioned (`position:sticky; bottom:env(safe-area-inset-bottom)`) command field, part of the Practice screen's core interaction.
- **Problem:** On mobile (≤739px) in Normal (non-Focus) mode, a same-specificity later rule resolves the computed font-size to 15px instead of the intended 16px (MSA-008), risking iOS Safari auto-zoom on focus.
- **Decision:** MUST FIX. Correct the one CSS value; no other change to this component.
- **Layout:** Unchanged — sticky positioning above the safe-area inset is correct and should not move.
- **Typography:** `font-size:16px` at all widths in Normal mode (Focus Mode's separate, already-correct larger value is untouched).
- **Dimensions:** Unchanged.
- **Interaction behavior:** Unchanged — Arrow Up/Down history recall, submit-on-Enter, etc. all continue exactly as built.
- **Responsive behavior:** Verify 16px holds at 320/360/390/430/739px in Normal mode and at the Focus Mode breakpoint, post-fix.
- **Accessibility requirements:** 16px minimum is itself the accessibility-relevant requirement here (prevents involuntary viewport zoom, which is disorienting for many users, not only those relying on it).
- **Preserve:** Sticky positioning, safe-area handling, and the deliberate 16px-in-Focus-Mode value that is already correct.
- **Reject:** Any proposal to replace the sticky/CSS-only approach with a JavaScript scroll-management library without a failing device test first (one audit's suggestion; no evidence in this package that the current mechanism, once the font-size bug is fixed, is insufficient — see §I).

### F.3 — Coach Panel (`.coach-block`)

- **Current state:** Renders below the Terminal in normal document flow on mobile (`order:2`, confirmed **not** an overlay/drawer — see §I), beside it on desktop. Shows `latestEntry?.response`, falling back to a hardcoded string when no entry exists.
- **Problem:** The fallback string is `"FORMAT ERROR · CHECK ENTRY"`, styled in `--red`, shown before any command exists (MSA-001).
- **Decision:** MUST FIX. Change only the pre-command fallback content and its styling.
- **Layout:** Unchanged — the existing in-flow (not overlay) placement is correct on both mobile and desktop and should not change based on this fix.
- **Typography / Spacing / Dimensions:** Unchanged.
- **Color:** Pre-command state must use the default/neutral text color and the neutral (non-`<code>`-error) block styling; the existing red error treatment is correct and should be preserved for genuine post-submission errors.
- **Interaction behavior:** Unchanged.
- **Responsive behavior:** The mobile in-flow, post-Terminal placement is confirmed correct in the supplied screenshot and should not be replaced with a FAB or bottom-sheet absent usability evidence that the current placement is being missed (§I — this was proposed by two of the nine audits and is explicitly rejected here for lack of evidence).
- **Accessibility requirements:** The neutral pre-command state should use `aria-live="polite"` (if not already present) so a genuine post-submission update is announced; the fabricated error state must not have `role="alert"` semantics, since it is not actually an error.
- **Preserve:** The Coach's subordinate position relative to the Terminal; its genuine post-submission error/success behavior.
- **Reject:** Converting the Coach into a floating action button or bottom sheet by default (§I).

### F.4 — Tab-like Segmented Controls (mode-tabs, growth-tabs, track-tabs, filter-tabs, metric-switcher)

- **Current state:** Five separate visually tab-like control groups, each implemented as plain `<button>` elements with only a CSS class (`is-active`) marking selection.
- **Problem:** Zero `role="tab"`, `aria-selected`, or `aria-pressed` anywhere in the source (MSA-015); Growth's tab panels are additionally removed from the accessibility tree entirely via `.is-secondary-view{display:none!important}` when inactive (MSA-024).
- **Decision:** SHOULD FIX. Build one shared pattern, applied to all five by actual behavior, not by appearance.
- **Layout / Spacing / Typography / Color / Dimensions:** Unchanged — this is an attributes-only fix.
- **Interaction behavior:** For controls that swap an entire panel (mode-tabs, growth-tabs): `role="tablist"` on the container, `role="tab"` + `aria-selected` on each button, `role="tabpanel"` on the content region. For controls closer to an independent toggle/filter that doesn't swap a full panel (metric-switcher, filter-tabs, track-tabs — evaluate each against its actual behavior): `aria-pressed` instead.
- **Responsive behavior:** No change.
- **Accessibility requirements:** Selection state and panel association must be programmatically determinable; verify with a screen reader across all five groups.
- **Preserve:** Current visual design of every control in this group.
- **Reject:** Building five bespoke implementations instead of one shared pattern.

### F.5 — Progress Indicators (`AnimatedBar`, `ProgressRing`)

- **Current state:** `AnimatedBar` renders a bare `<i style="width:X%">` with only `aria-label`. `ProgressRing` uses `role="img"` with an accessible label over a decorative SVG.
- **Problem:** `AnimatedBar` lacks `role="progressbar"` and value semantics (MSA-016); `ProgressRing`'s `role="img"` treatment is acceptable as a visual readout but should not be double-announced alongside any nearby redundant text.
- **Decision:** SHOULD FIX for `AnimatedBar`; no change required for `ProgressRing` beyond confirming no duplicate announcement.
- **Interaction behavior:** N/A (non-interactive, display-only).
- **Accessibility requirements:** `AnimatedBar` → add `role="progressbar"` with `aria-valuenow`/`aria-valuemin`/`aria-valuemax` and a clear accessible name; confirm `ProgressRing`'s label isn't duplicated by adjacent visible text using the same string.
- **Preserve:** Visual appearance of both components exactly as built.
- **Reject:** N/A.

### F.6 — Toast / Notification Usage

- **Current state:** `sonner`-based toasts fire for both genuine system-level events (e.g., a real Assessment save) and, currently, for every one of the 12 non-functional controls (MSA-004) plus every individual command submission (MSA-043).
- **Problem:** Toasts currently cannot be trusted to mean "something happened," which is the opposite of their purpose.
- **Decision:** SHOULD FIX (as part of MSA-004's per-control triage and MSA-043).
- **Interaction behavior:** Reserve toasts for events with no better-suited local surface (session save, session-level errors). Command-level feedback belongs in Terminal history; control-specific feedback belongs at the control itself (a disabled/relabeled state, not a toast pretending success).
- **Accessibility requirements:** Toasts should use `aria-live="polite"` (verify current implementation) and not be the sole channel for information also needed by non-sighted users in a more persistent form.
- **Preserve:** Toasts for genuine session/system-level confirmations.
- **Reject:** Any toast copy that claims an action ("created," "saved," "updated," "language set") that did not actually occur.

### F.7 — Bottom Navigation / Side Navigation

- **Current state:** Confirmed via full cascade trace: 5-column grid, `.is-primary` (Train/Practice) styled and visible on every mobile screenshot; `aria-current` present on bottom-nav items; side-nav lacks `aria-current`. `grid-template-columns` is declared four times in the stylesheet (one stale 4-column rule plus three reinforcing 5-column rules, the last with `!important`) — redundant but **not** presently broken (§I).
- **Problem:** (a) CSS redundancy (MSA-037, hygiene only). (b) Missing `aria-current` on the desktop side-nav (part of MSA-017). (c) The `.is-primary` mobile-emphasis rule is scoped only to ≤739px, so the 740–1099px tablet range would lose Practice's visual emphasis even though the nav itself remains visible there (NEEDS VALIDATION — no screenshot covers this range).
- **Decision:** COULD IMPROVE (CSS cleanup) + SHOULD FIX (`aria-current` on side-nav) + NEEDS VALIDATION (tablet-range emphasis).
- **Responsive behavior:** Bottom-nav visible <1100px; side-nav visible ≥1100px; no distinct tablet-specific nav paradigm exists between 740–1099px — confirm this is an acceptable, deliberate choice (§H) rather than an oversight.
- **Preserve:** The 5-item structure, the deliberate Practice-centering, and the current final rendered behavior (5 equal columns) exactly as-is.
- **Reject:** Any "fix" premised on the incorrect claim that the bottom-nav currently renders 5 items into 4 columns (§I) — the rendered output is already correct; only the redundant source lines need cleanup.

### F.8 — Progress Tracking KPI Cards

- **Current state:** Secondary metric cards use decorative `clip-path` shapes and gradient ornamentation.
- **Problem:** The ornamentation does not encode or communicate data; adds visual noise and maintenance surface (MSA-039).
- **Decision:** COULD IMPROVE.
- **Layout / Spacing:** Unchanged structurally.
- **Color / Visual treatment:** Simplify or remove the `clip-path`/gradient decoration; retain the underlying data hierarchy and any color that *does* carry semantic meaning (status colors).
- **Preserve:** The KPI data itself, its current information hierarchy, and the chart+table pattern this screen also contains (§B.7).
- **Reject:** Adding *more* decorative treatment anywhere on this screen while simplifying this one (§I, "Do not add a fourth visual layer of decoration").

---

## G. Screen and Flow Changes

No new screens or flows are proposed anywhere in this section — every change below operates within the existing five-screen structure, per the evidence and per `ideas.md`'s explicit preservation instruction.

### G.1 — Global Shell (Topbar, Bottom Nav, Side Nav, Hamburger Drawer)

- **Current issue:** Language toggle is a false affordance (MSA-044a); Search/Profile icons are toast-only (part of MSA-004); side-nav lacks `aria-current` and the shell lacks a `<main>` landmark/skip link (MSA-017); bottom-nav CSS has redundant declarations though rendered output is already correct (MSA-037); hamburger drawer reportedly duplicates the bottom nav (MSA-034, NEEDS VALIDATION).
- **Decision:** Interim-disable/relabel the language toggle; triage Search/Profile per MSA-004's tiering; add the missing landmarks/attributes; clean up (don't "fix," since nothing is broken) the CSS redundancy; validate the hamburger-drawer redundancy claim before deciding whether to act on it.
- **Hierarchy / Layout changes:** None. The shell's structure (topbar + bottom-nav-or-side-nav depending on width) is confirmed sound and is a PRESERVE item (§B.2, §B.8).
- **Content priority:** Unchanged.
- **Interaction changes:** Only as specified per MSA-004/017/044a above — every other shell interaction (nav switching, focus-mode entry) is unchanged.
- **Navigation changes:** None to the five-item structure or its order. **ASSUMPTION:** if MSA-034's hamburger-duplication claim is validated as true, the recommended response is to either remove the redundant drawer entry point or give it distinct content (e.g., settings, help) rather than removing bottom-nav — this is flagged as an assumption because it has not been independently re-verified in this pass.
- **Responsive considerations:** Confirm whether the 740–1099px tablet range's continued use of bottom-nav chrome (rather than a tablet-specific pattern) is a deliberate choice; document it as such once confirmed (§H, §L).

### G.2 — Progression

- **Current issue:** Technical/Customer Service track toggle changes only descriptive text while the milestone list stays Technical-labeled (MSA-026); segmented-progress shows "3/8" against data that doesn't support it (part of MSA-003); expandable "mastered" level cards lack `aria-expanded` (folded into MSA-015's accessibility pass); `AnimatedBar` lacks progress semantics (MSA-016).
- **Decision:** Honest empty state for the unbuilt track; derive the stage count from real data; add expand/collapse and progress-bar semantics.
- **Hierarchy changes:** None — the "resume where you left off" primary card, followed by the stage map, is confirmed sound and unchanged.
- **Layout changes:** None structurally; only the content shown within the Customer Service state (MSA-026).
- **Content priority:** Unchanged — Technical Track content remains the primary, fully-built path.
- **Interaction changes:** Level cards gain `aria-expanded`; track toggle gains an honest disabled/pending state for Customer Service until real content exists.
- **Navigation changes:** None.
- **Flow changes:** None — "Resume pricing workflow" continues to route into Practice with context exactly as it does today (a confirmed-working handoff, §B.3).
- **Responsive considerations:** No screen-specific responsive issue identified beyond the global items in §H.

### G.3 — Practice (Terminal / Learn / Practice / Assessment)

- **Current issue:** The single most consequential screen in the product, carrying the majority of P0 findings: fabricated Coach default error (MSA-001), empty-submit-to-FQD (MSA-002), mode/hint state bleed threatening Assessment integrity (MSA-007), mobile input font-size regression (MSA-008), fixed terminal dead-space (MSA-010), Focus Mode's missing focus-trap (MSA-012), sequence-checking only in Assessment mode (MSA-009, NEEDS VALIDATION), pre-seeded session timer (P2, MSA-016 in the priority table), redundant per-command toasts (MSA-043).
- **Decision:** Apply MSA-001/002/007/008/010/012 as specified in §E; leave MSA-009 (sequence checking scope) as an open product/learning-design question (§L) rather than assuming an answer.
- **Hierarchy changes:** None — Terminal-first, Coach-subordinate-and-below-on-mobile is confirmed correct and must not change (§B.2, §F.3).
- **Layout changes:** Only the terminal-gap reduction (MSA-010); no other structural change.
- **Content priority:** Unchanged.
- **Interaction changes:** Empty-submit becomes a no-op with inline messaging (MSA-002); mode switching gains a disclosure of carried-over history/hints (MSA-007); Reference-drawer hint-accounting should be made consistent between the Terminal's own toggle and the Coach panel's "Open reference" button — currently the latter is toast-only and doesn't open anything or count consistently with the former (fold into MSA-004's triage, treating this specific instance as higher-stakes than the average toast-only control because it affects scored hint counts).
- **Navigation changes:** None.
- **Flow changes:** None to the Learn → Practice → Assessment concept itself (a PRESERVE item, §B.4) — only to what state, if any, is honestly disclosed as carrying between them.
- **Responsive considerations:** MSA-008 (font-size), MSA-010 (terminal-gap) are mobile-specific; Focus Mode's keyboard trap (MSA-012) applies at all widths where Focus Mode is reachable.

### G.4 — Scenarios

- **Current issue:** "Filters" button duplicates the adjacent working `filter-tabs` row (MSA-028); sort control doesn't sort despite the data supporting it (MSA-029); stats "23/40" and "Exchanges & Refunds" don't reconcile with the actual 5-scenario dataset (MSA-003).
- **Decision:** Remove/merge the duplicate Filters control; wire sort to real fields; derive stat counts from the actual dataset.
- **Hierarchy changes:** None — the stat cards → filter tabs → scenario list → detail panel structure is sound.
- **Layout changes:** None beyond removing the redundant Filters button.
- **Content priority:** Unchanged.
- **Interaction changes:** Sort becomes functional; Filters is removed or merged into the existing tabs.
- **Navigation changes:** None — "Resume scenario" continues to hand off into Practice with context exactly as today (confirmed-working, §B.3).
- **Flow changes:** None.
- **Responsive considerations:** MSA-036 (long scenario titles crowding the Practice task-strip badge) is NEEDS VALIDATION and belongs to the receiving screen (Practice) as much as this one — test with the longest actual scenario titles in the dataset.

### G.5 — Growth Record (Record / History / Reports tabs)

- **Current issue:** "Backup" implies real data protection with none performed (MSA-005); "View evidence"/"See patterns"/"View history" SectionHeader actions are toast-only (part of MSA-004); `.is-secondary-view{display:none!important}` removes inactive tab panels from the accessibility tree (MSA-024); skill-trend arrow direction reads backwards for favorability (MSA-027); skill hover-preview content disappears entirely (not just hard to reach) below 740px (MSA-025); "LOG 04/12" header doesn't match the 3 rendered rows (part of MSA-003).
- **Decision:** Apply MSA-005/024/025/027 and MSA-003's derivation fix as specified in §E; triage the SectionHeader actions per MSA-004.
- **Hierarchy changes:** None — Record/History/Reports as three tabs of one screen is confirmed sound and must NOT be split into three separate destinations or merged with Progress Tracking (§B.3 — `ideas.md` names Growth and Tracking as distinct stages).
- **Layout changes:** None structurally.
- **Content priority:** Unchanged.
- **Interaction changes:** Tab panels gain proper ARIA association (part of MSA-015/024); skill rows gain a mobile-accessible detail interaction (MSA-025); trend arrows are remapped to favorability (MSA-027).
- **Navigation changes:** None.
- **Flow changes:** None — "Open recommended/targeted practice" continues to hand off into Practice with context exactly as today.
- **Responsive considerations:** MSA-025 is specifically a <740px gap; the desktop/tablet mechanism is confirmed correct and untouched.

### G.6 — Progress Tracking

- **Current issue:** Redundancy with Growth Record's metrics was raised by one audit as a possible merge candidate — evaluated and REJECTED (§I) given `ideas.md`'s explicit naming of both as distinct loop stages; decorative KPI-card ornamentation carries no data meaning (MSA-039); route-line label truncates on mobile (MSA-035); chart may re-animate distractingly on every metric switch (NEEDS VALIDATION, single-source, not independently re-verified).
- **Decision:** Simplify KPI-card decoration; fix the truncating label; validate the re-animation claim before acting on it.
- **Hierarchy changes:** None — this screen's session-level trend framing is a distinct, valuable grain of evidence from Growth Record's skill-level framing and both should remain (§B.3).
- **Layout changes:** None beyond the KPI-card simplification.
- **Content priority:** Unchanged.
- **Interaction changes:** None beyond fixing the truncation.
- **Navigation changes:** None.
- **Flow changes:** None — "Open targeted practice" continues to hand off into Practice with context exactly as today.
- **Responsive considerations:** Route-line truncation (MSA-035) is mobile-specific; the chart+table accessible-alternative pattern (a PRESERVE item, §B.7) is confirmed working at all tested widths.

---

## H. Responsive, Accessibility, and State Requirements

Concrete and testable, not general advice. Each requirement states what to check and what result constitutes a pass.

### H.1 — Desktop (≥1100px)

- Side-nav is visible, fixed, and reachable by keyboard; each item exposes `aria-current="page"` when active. **Test:** Tab through the side-nav with a keyboard only; confirm the active screen's nav item is announced as current by a screen reader. *(Currently fails — no `aria-current` on side-nav; MSA-017.)*
- Bottom-nav is not present in the DOM in a way that remains keyboard-reachable (`display:none` should also remove it from the tab order, which it does by default). **Test:** Tab through the full page at ≥1100px and confirm no bottom-nav button receives focus.
- No desktop screenshot exists in the evidence package. **Test:** Capture the current desktop render at 1280px and 1440px and compare against the CSS-derived expectations in this report before treating any desktop-only claim in §D/§I as more than CSS-derived.

### H.2 — Tablet (740–1099px)

- **Requirement:** Confirm whether the combination of desktop-density, multi-column content grids (which begin at 740px) with mobile-style bottom-nav/hamburger chrome (which persists until 1100px) reads as a deliberate, coherent "large mobile" experience or as an unintentional gap. *(MSA-032, NEEDS VALIDATION — no screenshot evidence either way.)*
- **Test:** Render Progression, Practice, Scenarios, Growth, and Tracking at 768px and 1024px; confirm (a) content grids display correctly at their intended column counts, (b) the bottom-nav's `.is-primary` (Train) visual emphasis — currently scoped only to ≤739px — either still reads correctly without it, or is extended to this range if its absence looks like a regression (MSA-part of F.7).
- **Success criteria:** No overlapping elements, no orphaned single-column content awkwardly wide, Practice remains visually identifiable as the primary destination.

### H.3 — Mobile (<740px)

- **Requirement:** Confirm actual rendered behavior at 320px and 360px specifically — the CSS defines explicit rules starting at 360px; 320px relies entirely on inheritance and is unvalidated (MSA-033/059).
- **Test:** Render all five screens at exactly 320px width (the `body{min-width:320px}` floor) and 360px; confirm no horizontal scroll, no text truncation beyond what's already flagged (MSA-035), and all touch targets remain tappable.
- **Requirement:** Confirm the mobile Terminal input reaches 16px font-size in Normal mode post-fix (MSA-008). **Test:** Inspect computed `font-size` on `.terminal-input input` at 320/360/390/430/739px in a real mobile browser (not just DevTools emulation) — iOS Safari specifically, since that is the auto-zoom-sensitive engine.
- **Requirement:** Confirm on-screen-keyboard behavior does not obscure Terminal output history above the sticky input. **Test:** On a real iOS and Android device, focus the command input with prior command history present; confirm the most recent 2–3 history entries remain visible above the keyboard, or that the page scrolls to keep them visible. *(No audit had live device access for this; flagged NEEDS VALIDATION in the source audits and here.)*

### H.4 — Interaction States

- **Default:** Every control's default state must not imply an action has occurred that hasn't (MSA-004). **Test:** Load each screen fresh (cleared `localStorage`) and confirm no element shows success/error styling before user interaction, except where the design intentionally shows illustrative sample data — and where it does, confirm it is labeled as such.
- **Loading:** Command submission currently has no intermediate state (MSA-011, P2). **Test (if implemented):** Confirm a submitted command shows a brief processing indicator before the response renders, and that the indicator is announced via `aria-live` if screen-reader users would otherwise perceive an unexplained delay.
- **Empty:** Confirm every list/chart has a genuine empty state (Growth and Tracking already have one, confirmed in source) and that the Customer Service track (MSA-026) gains one rather than showing mislabeled Technical content.
- **Error:** Confirm the Coach panel's error styling is reserved for genuine post-submission errors only (MSA-001). **Test:** Load Practice fresh; confirm the Coach panel shows neutral, non-`--red` styling until a command is actually submitted.
- **Success:** Confirm every success-styled toast or state corresponds to a real completed action (MSA-004/043). **Test:** Click each of the 12 currently-toast-only controls post-fix; confirm each either performs its action, is disabled, or is clearly labeled as unavailable — none should show unqualified success copy for a no-op.

### H.5 — Accessibility (testable, cross-cutting)

- **Contrast:** `.primary-button` text/background ≥4.5:1 in every state (default/hover/active/focus/disabled) — **test with a contrast-checking tool against the shipped hex values, not the current 2.98:1.** `--text-faint` ≥4.5:1 against `--navy-950`, `--panel-solid`, and `--navy-750` — **test all three surface pairings independently.**
- **Keyboard:** Every interactive element (including all 5 tab-like control groups, the Reference popover, the mobile drawer, and Focus Mode) must be reachable and operable via keyboard alone, with a visible focus indicator at each stop. **Test:** Full keyboard-only pass through all five screens.
- **Screen reader:** Selection state of all 5 tab-like groups must be announced (MSA-015); `AnimatedBar` progress must be announced with value (MSA-016); the Coach panel's neutral vs. genuine-error states must be distinguishable in the accessibility tree, not just visually. **Test:** Full screen-reader pass (VoiceOver + NVDA/JAWS minimum) through Practice and Growth Record specifically, as the two screens carrying the most state-dependent content.
- **Touch targets:** Confirm final sizes for `.icon-button` and `.mode-tabs` post-adjustment (MSA-022, COULD IMPROVE) — target 44×44 CSS px where layout permits; document any exception where the compact mobile density (`ideas.md`'s stated intent) is prioritized instead, since 38px already passes the WCAG 2.2 AA 24×24 minimum.
- **Reduced motion:** Confirmed already strong (§B.6) — **test:** enable `prefers-reduced-motion: reduce` at the OS level and confirm the terminal caret, history-list buttons, and all other animated elements stop animating, as the existing CSS already specifies.
- **Zoom:** Post-fix (MSA-020), **test:** pinch-zoom to 200% on a real mobile device and confirm no loss of content or functionality, per WCAG 1.4.4.

---

## I. Explicit Rejection List

Two different kinds of rejection appear below, kept distinct: **(a) factual claims** that do not survive tracing the full evidence (mostly incomplete CSS-cascade analysis in the source audits), and **(b) recommendations** that are evidenced-but-out-of-scope, insufficiently evidenced, or in tension with confirmed product intent. Per the audit brief's methodology, none of these were resolved by counting how many of the nine audits raised them — each is resolved against the actual source, screenshots, or `ideas.md`.

| ID | Rejected Recommendation | Source | Reason for Rejection | Future Validation Needed? |
|---|---|---|---|---|
| R-01 | "`.bottom-nav` renders 5 items into a 4-column grid; `.is-primary` styling is dead" | v0.dev; similar claim in Grok | **Factual, not evidenced.** Two later rules — one unconditional, one `!important`-scoped to mobile — override the stale 4-column base rule with a 5-column one; `.is-primary` is confirmed styled and is visibly present in every one of the 7 mobile screenshots. Independently re-derived in this pass via full cascade trace; independently reached by Manus and Claude as well. | No — resolved by direct evidence. The stale, now-redundant base rule is a hygiene item (MSA-037), not a defect. |
| R-02 | "`.terminal-session-readout` is `display:none` on mobile, hiding all session state" | Qwen, Grok, Kimi | **Factual, not evidenced.** True only of an earlier, superseded rule; a later, unconditional, higher-specificity `.page-practice .terminal-session-readout{display:flex}` rule restores it at every breakpoint. Confirmed visible in the supplied mobile Practice screenshot itself ("SESSION / LOCAL SESSION · COMMAND / READY · LOG 01" is plainly rendered). | No — resolved by direct screenshot evidence. |
| R-03 | "The terminal caret's blink animation ignores `prefers-reduced-motion`" | Manus, Kimi | **Factual, not evidenced.** A component-specific rule explicitly names `.terminal-caret` inside a `prefers-reduced-motion` block, in addition to the global catch-all — two independent disabling mechanisms exist. | No — resolved by direct source citation (cross-checked at high confidence via Claude's audit's exact rule citation, consistent with this pass's own reduced-motion source review). |
| R-04 | "The Coach panel is an overlapping drawer that obscures the Terminal" | Gemini | **Factual, not evidenced.** Source confirms the Coach panel is a normal in-flow, stacked section (`order:2`, below the Terminal on mobile) — not an overlay. The underlying concern (a trainee must scroll past a tall Terminal to reach Coach guidance) is real and distinct from "obscures," and is addressed indirectly by MSA-010's terminal-gap reduction, which shortens that scroll distance. | No for the overlap claim. The scroll-distance concern is soft; revisit only if user testing shows trainees miss Coach guidance. |
| R-05 | "Merge Progress Tracking into Growth Record as a single screen/tab" | Gemini | **Contradicts confirmed product intent.** `ideas.md` names Growth and Tracking as two distinct stages of the canonical loop ("Growth → Tracking"). They also operate at different evidence grains — skill-level mastery vs. session-level trend — which is a legitimate product reason to keep them separate, independent of the `ideas.md` citation. | No — the redundancy concern that motivated this suggestion is real and is addressed instead by tightening each screen's own metric set, not by removing a screen. |
| R-06 | "Build real backend-wired Search, full Filters, and translation logic as part of this revision" | Implied across several audits' treatment of MSA-004/toast-only controls | **Out of scope per confirmed product intent.** `ideas.md` explicitly states: *"Do not add backend, authentication, payment, engine architecture, or real metrics."* The correct fix for these controls in the current phase is honest labeling/relabeling (MSA-004), not implementation. **Exception carved out:** Scenarios' sort control (MSA-029), because it requires zero new data — the sortable fields already exist client-side. | Revisit if/when the product moves beyond preview scope and a real backend is commissioned. |
| R-07 | "Build out `Map.tsx` into a real interactive map feature" | Implied by its presence as unused, fully-built code | **Insufficiently evidenced.** 155 lines of working map code exist but are imported nowhere; no screenshot, `ideas.md` passage, or audit provides evidence a map feature is currently needed. Building it out would be new functionality without evidence, which §3's rules explicitly prohibit. | Yes — flag to whoever owns the roadmap as a single question: finish it, or remove the remaining dead-code traces (the unused component plus Progression's "View map" stub button)? This is a product decision, not a design one. |
| R-08 | "Add command autocomplete/suggestions to the Terminal input" | Raised in the broader audit set as a usability nicety | **Contradicts the product's own pedagogy.** The Terminal is explicitly a recall-based training tool (per the Learn/Practice/Assessment structure and Arrow-Up/Down history-recall design) — autocomplete would remove the memorization the product exists to build. No evidence in the package supports that trainees are failing due to recall difficulty rather than the training working as intended. | No — would need explicit product/curriculum-design justification to reconsider, not a UX-convenience argument alone. |
| R-09 | "Add a two-step confirmation before 'Finish Session'" | Kimi | **Unnecessary risk, unsupported.** `FINISH SESSION` is already disabled until at least one command has been submitted, which already prevents the specific accidental-empty-submission scenario a confirmation step would guard against. Adding friction to the product's single most consequential action, without a demonstrated problem it solves, is precisely the kind of change §3 warns against ("do not increase the number of changes just to make the audit appear more comprehensive"). | No. |
| R-10 | "Add a persistent, global 'Next Action' widget across all screens" | Raised in the broader audit set | **Excessive; risks dashboardization.** Every screen already has a contextual, screen-specific next-action CTA that correctly hands off into Practice. A global widget duplicates this without evidence the contextual pattern is failing, and pushes the product toward a generic-SaaS-dashboard feel `ideas.md`'s copy guidance explicitly steers away from. | Only if user testing specifically shows trainees can't find the next action from a given screen. |
| R-11 | "Move the Coach panel to a floating action button or bottom sheet by default on mobile" | Raised in the broader audit set (partially motivated by the now-rejected R-04) | **Unsupported by evidence.** No screenshot or source evidence shows trainees failing to notice or reach the Coach panel in its current in-flow position; the recommendation was substantially motivated by the "obscuring drawer" claim this report rejects (R-04). | Yes — if MSA-010's terminal-gap fix and reduced scroll distance are shipped and usability testing *still* shows trainees miss Coach guidance, reconsider a more prominent placement then, evidenced by that testing. |
| R-12 | "Replace the hand-built chart with a charting library (e.g., Recharts)" | Raised in the broader audit set (noting `recharts` is an installed dependency) | **Unsupported; risks the product's best accessibility pattern.** The current chart already has a genuine, data-wired `<details>`/table accessible alternative — independently rated by this synthesis as the single strongest accessibility artifact in the codebase. A dependency being installed is not evidence the current implementation is deficient. | No — would need a specific, evidenced deficiency in the current implementation, not a "the library is already there" argument. |
| R-13 | "Delete or remove the illustrative/mock data and interactions" | Not explicitly recommended by name in any single audit, but implied by treating MSA-003/004's findings as "remove the fake stuff" | **Contradicts confirmed product intent.** `ideas.md` explicitly calls for a "presentation-first" preview with "local mock interactions visible." The correct fix is honest labeling and internal-data-consistency (MSA-003/004 as specified), not deletion of the mock layer itself, which is intentional. | No. |
| R-14 | "Consolidate the two design-token systems by deleting the newer `--ab-*` layer and keeping only the base tokens" | Implied by treating MSA-021 as "remove the duplicate" without direction | **Would discard the more deliberate, more recent design pass.** The `--ab-*` layer's own code comment states explicit intent ("prioritize Terminal, calm precision, and operational readability") — it reads as a refinement to build on, not a duplicate to revert. MSA-021 specifies consolidating *outward* from `--ab-*`, which this rejection entry exists to make explicit as the correct direction. | No. |
| R-15 | "Add gamification elements (badges, streaks, confetti, leaderboards) to increase engagement" | Raised in the broader audit set as a general suggestion | **Contradicts the product's stated professional-workstation identity.** Multiple independent audits, and this synthesis's own read of `ideas.md`'s tone and the Flight Deck Console's restrained visual language, converge on this being a "serious workstation," not a consumer app — gamification devices are a stylistic mismatch with no evidence of need. | No — would need explicit product-strategy direction to reconsider (e.g., a decision to target a more casual learner segment), not a UX trend argument. |

---

## J. Validation Plan

| Decision being tested | Objective | Validation method | What to measure | Success criteria | Result that would change the recommendation |
|---|---|---|---|---|---|
| MSA-008 mobile input font-fix | Confirm the CSS fix actually prevents iOS auto-zoom in practice | Technical validation on real hardware | Computed `font-size` on `.terminal-input input`; observed zoom behavior on focus | 16px computed at all widths ≤739px in Normal mode; no viewport zoom on focus in iOS Safari | If zoom still occurs at 16px on a specific iOS version, the fix needs a supplementary `touch-action`/viewport approach, not just the font-size value |
| MSA-013/014 contrast fixes | Confirm new token values pass in every real rendering context, not just the computed formula | Accessibility validation (contrast-checker tool + manual review) | Measured ratio for `.primary-button` (all states) and `--text-faint` (all 3 surfaces) | ≥4.5:1 in every state/surface | If any state (e.g., hover) still fails, that state's value needs its own adjustment |
| MSA-019 font loading | Confirm the specific declared families actually render, and identify any conflicting import (per one audit's live-build observation of an unexpected "Inter" font) | Technical validation | Computed `font-family` on a heading, a terminal command line, and (once MSA-044 progresses) Arabic text | Each resolves to its intended named family, not a fallback; no unintended competing import remains | If Space Grotesk/IBM Plex Mono/Cairo were in fact already loading via a mechanism not visible in the supplied files, several dependent recommendations in this report should be downgraded from MUST FIX to already-resolved |
| MSA-007 Assessment state-isolation approach | Determine whether Learn/Practice/Assessment modes should be fully isolated (reset on switch) or continuous-with-disclosure, before building either | User testing + product/learning-design input | Whether trainees expect switching modes to "start fresh," and whether instructors/curriculum designers intend Assessment to measure only in-mode activity | A clear stated preference from whoever owns the learning-design decision | Either answer is implementable per §E's interim spec; this determines which final behavior to build, not whether to fix the current silent-bleed defect (that fix is required regardless — see §L) |
| MSA-009 Practice/Learn sequence enforcement | Determine whether out-of-order commands succeeding outside Assessment is intentional (low-stakes exploration) or an oversight | Product/learning-design input | Whether the intended pedagogy treats Practice as free-form or workflow-ordered | A clear stated design intent | If Practice is meant to be workflow-ordered, extend `sequenceError` checking to it; if intentional, no change needed |
| MSA-032 Tablet (740–1099px) composition | Determine whether the bottom-nav/hamburger-plus-multi-column-grid combination in this range reads as coherent | Responsive testing on real tablet hardware/emulation at 768px and 1024px | Visual coherence, no overlapping/orphaned elements, `.is-primary` emphasis presence or absence | No layout defects; a deliberate answer on whether Practice's visual emphasis should extend into this range | If the combination reads as broken rather than merely "no distinct tablet pattern," add tablet-specific nav treatment as a new, evidenced P1/P2 item |
| MSA-033/059 Sub-360px behavior | Confirm the 320px floor renders acceptably relying on inherited 360px rules | Responsive testing at exactly 320px | No horizontal scroll, no truncation beyond documented items, all touch targets remain reachable | Passes on at least one real 320px-class device | If defects appear, add explicit sub-360px rules as a new, evidenced item |
| MSA-034 Hamburger drawer redundancy | Confirm whether the drawer's content is in fact a full duplicate of the bottom nav | Direct inspection/prototype testing (open the drawer, compare contents) | Item-by-item content comparison | Either fully confirmed or refuted | If refuted (drawer has distinct content), MSA-034 is withdrawn; if confirmed, proceed per the ASSUMPTION noted in §G.1 |
| MSA-044b Arabic/RTL scope | Determine whether full RTL/i18n support is in scope for a near-term release | Product/business decision, not a design-validation method | Target market commitment and timeline for Arabic-language support | An explicit scope decision from product ownership | Determines whether MSA-044b is scheduled as real work or the interim fix (MSA-044a) remains the long-term state |
| MSA-036 Long scenario titles vs. task-strip badge | Confirm whether real (not placeholder-length) scenario titles cause crowding | Comparative testing using the longest actual titles in the current dataset | Visual crowding/overlap at the task-strip percentage badge | No overlap at any width down to 320px | If crowding occurs, add a truncation/wrap rule as a new, evidenced P2 item |
| Chart re-animation on metric switch (Tracking) | Confirm whether switching Overall/Accuracy/Sequencing visibly re-triggers entrance animation in a distracting way | Prototype testing (manual interaction, screen-record) | Presence/absence of a visible re-animation on metric switch | No jarring re-animation, or one that is subtle enough not to register as a defect | If confirmed distracting, add a "don't replay entrance animation on data-only updates" fix as a new, evidenced P2/P3 item |

---

## K. Implementation Handoff

The implementation team should treat this document as the sole source of approved scope for this revision pass. Specifically:

1. **Implement only the decisions classified MUST FIX or SHOULD FIX in §D/§E.** COULD IMPROVE items may be scheduled at the team's discretion but are not required for this pass to be considered complete. NEEDS VALIDATION items must not be implemented until the corresponding validation in §J has been performed and has produced a clear answer.
2. **Preserve the original product intent stated in `ideas.md` throughout.** This is a reference-preservation project. If any approved fix, during implementation, appears to require touching the command-matching logic, the scoring algorithm, the five-screen information architecture, or adding backend/auth/payment functionality, stop and flag it — none of the approved decisions in this report should require that, and if one appears to, the implementation has likely drifted from the specified fix.
3. **Preserve every item listed in §B without exception.** In particular: do not let the MSA-013/014 contrast fixes drift into a broader palette change; do not let the MSA-021 token consolidation become an opportunity to redesign the Terminal's visual treatment; do not let the MSA-001/007 Terminal fixes touch the confirmed-working `setPracticeContext` cross-screen handoffs.
4. **Preserve all required functionality**, specifically the real, working parts of the toast-only-control inventory's neighbors — e.g., Scenarios' functioning `filter-tabs` while removing the redundant Filters button (MSA-028); the Terminal's working command-matching while fixing only the empty-submit path (MSA-002).
5. **Avoid introducing unrelated redesigns.** Every fix in §E specifies exactly what must remain unchanged alongside what changes — treat that "must remain unchanged" line as binding, not advisory.
6. **Avoid adding new ideas that were not approved in this document.** If an implementer identifies what looks like an additional improvement opportunity while working through this list, log it as a candidate for a future audit pass rather than folding it into this one — consistent with §3's explicit instruction not to increase scope to appear more comprehensive.
7. **Treat every item in §I (Explicit Rejection List) as settled for this pass**, including the three factual corrections (R-01/02/03) — do not re-implement a "fix" for something confirmed not to be broken.
8. **Treat every unresolved item in §L as a question to escalate for a decision, not a design choice to make unilaterally during implementation.** In particular, MSA-007's exact isolation-vs-continuous behavior and MSA-044b's Arabic/RTL scope both require an answer from whoever owns product/learning-design decisions before final behavior is locked in — the interim, UI-safe versions specified in §E may ship in the meantime.
9. **Sequence per §E's P0 → P1 → P2 ordering**, with one exception worth calling out explicitly: MSA-019 (font loading) should land early within its tier regardless of exact ordering, since it changes text metrics that affect visual QA on every other fix.
10. **Re-verify current source state immediately before implementing any individual fix in this document.** Several of this report's most important conclusions (§I, R-01/02/03) exist specifically because the codebase has already been through multiple prior "revision pass" iterations that silently fixed some issues while leaving others — the code may have changed again between this audit and implementation time. Grep for every declaration of a selector before concluding a rule needs to change, not just the first one found.

---

## L. Open Questions and Assumptions

| # | Question / Assumption | Why it matters | Decisions it affects | Information / validation needed |
|---|---|---|---|---|
| 1 | Should Arabic/RTL support be built for a near-term release, or is the current preview EN-only for the foreseeable future? | Determines whether MSA-044 is a small interim copy fix or a genuine architecture/content/translation effort | MSA-044a (interim, either way), MSA-044b (only if scope is confirmed) | A product-ownership decision, not a design or engineering one |
| 2 | Are "8 stages" and "40 scenarios" a real, larger curriculum planned for the future, or should the displayed totals simply match whatever smaller set is genuinely built? | Determines whether MSA-003's fix is purely a derivation correction (show real current totals) or should preserve a larger aspirational number with an honest qualifier | MSA-003 | Curriculum/content-team input on planned scope |
| 3 | What should "Backup" actually do — a real local export (e.g., JSON download of the `localStorage` evidence record), or should it simply be relabeled as unavailable in this preview? | Affects cost/complexity of MSA-005's fix substantially (relabeling is trivial; real export is a small but real feature) | MSA-005 | A product decision on whether local data export is a feature this preview should have |
| 4 | Is the 740–1099px range's current mobile-nav-plus-desktop-grid combination a deliberate "large mobile" design choice, or an unreviewed gap? | Determines whether §H.2/MSA-032 requires any fix at all, or only documentation confirming intent | MSA-032, F.7's tablet-range `.is-primary` gap | Direct tablet-width rendering review (§J) |
| 5 | Does the hamburger drawer serve a distinct purpose from the bottom/side nav, or is it fully redundant? | Determines whether MSA-034 requires a fix or is a non-issue | MSA-034 | Direct inspection of drawer contents (§J) — **ASSUMPTION** made in §G.1 pending this: if confirmed redundant, remove or repurpose rather than leaving two identical entry points |
| 6 | Should Learn/Practice/Assessment modes be fully isolated (history/hints reset on switch) or continuous with honest disclosure of carried-over activity? | Determines the *final* shape of MSA-007's fix — the interim disclosure specified in §E is safe either way, but the long-term intended behavior needs a decision | MSA-007 | Learning-design/product input on the intended assessment model |
| 7 | Should Practice/Learn modes enforce command sequence order the way Assessment does, or is out-of-order exploration intentional in those modes? | Determines whether MSA-009 is a defect or a deliberate design choice | MSA-009 | Learning-design/product input |
| 8 | Is a future interactive map a planned feature (explaining why `Map.tsx` and the "View map" stub exist), or should the remaining dead-code traces simply be removed? | Determines MSA-040/R-07's disposition | MSA-040, R-07 | Roadmap-ownership input |
| 9 | Is the current level of "realistic" decorative detail (the pre-seeded 272-second session timer, for instance) an intentional part of making the local simulation feel authentic, or should such elements start from a genuine zero/empty state? | Minor, but affects whether MSA-016 (P2/P3, session timer) is worth any effort at all | MSA-016 (priority-matrix ID; session timer) | Product input — low stakes either way |
| 10 | **Assumption used throughout this report:** the evidence package's absence of any desktop or tablet screenshot means no such capture exists, not merely that it wasn't included in this handoff. | If additional screenshots exist but were not shared, several "NEEDS VALIDATION" items in this report could be resolved immediately rather than requiring new testing | All desktop/tablet-flagged items across §D/§H/§J | Confirm whether additional screenshots exist before commissioning new capture work |

---

## M. Final Recommendation

### Implement

The full P0 set (§E): the neutral Coach default state, the empty-submit no-op, headline-count derivation, Assessment mode/hint-bleed disclosure, the mobile Terminal font-size cascade fix, primary-button and `--text-faint` contrast fixes, font-loading restoration, and the language-toggle interim fix. Followed by the full P1 set: the systemic toast-only-control triage, the accessibility-semantics pass across tabs/progress-indicators/landmarks/overlays, the token-system consolidation, the mobile skill-preview gap, the Customer-Service-track honest empty state, trend-arrow semantics, Scenarios' Filters/Sort fixes, and the nav-order/breadcrumb reconciliation. P2 items may follow at the team's discretion. Every one of these is UI-only, copy-only, or a contained state-management change — none requires touching the command engine, the scoring formula, or the information architecture.

### Preserve

The Flight Deck Console visual identity in its entirety; the Terminal's architectural centrality; the five-screen loop and its genuine cross-screen `setPracticeContext` handoffs; the Learn/Practice/Assessment conceptual structure; Focus Mode's core mechanism; the `prefers-reduced-motion` implementation (confirmed stronger than initially credited); the Progress Tracking chart's accessible table alternative; the deliberate mobile input engineering (sticky positioning, safe-area handling); the contextual copy voice; and the command-history keyboard recall. All ten items are detailed with acceptable-modification boundaries in §B — implementation should treat that section as binding, not aspirational.

### Defer

Full Arabic/RTL implementation (MSA-044b) pending the scope decision in §L item 1. The larger question of whether "8 stages" and "40 scenarios" should grow into real, bigger curricula (MSA-003's content half) pending §L item 2. Whether `Map.tsx` is finished or removed (MSA-040) pending §L item 8. Most P2/COULD IMPROVE items (§E) may be scheduled at team discretion without blocking this pass's completion.

### Reject

All fifteen items in §I: three factual corrections that do not survive full-cascade/screenshot verification (bottom-nav column count, mobile session-readout visibility, terminal-caret reduced-motion), and twelve recommendations that are out of confirmed scope, unsupported by evidence, or would compromise a confirmed strength (the Coach-drawer misreading, merging Growth and Tracking, building a real backend for Search/Filters, activating the unused map, command autocomplete, a Finish-Session confirmation step, a persistent global next-action widget, a default Coach FAB/bottom-sheet, a charting-library swap, deleting the illustrative data layer, deleting the `--ab-*` token layer, and gamification).

### Validate

Ten items require validation before a final decision, listed in full in §J: the real-device effectiveness of the mobile font-size fix; contrast fixes across all interaction states; font-loading and the possible conflicting "Inter" import one audit's live build observed; the Assessment isolation-vs-continuous product decision; the Practice/Learn sequence-enforcement product decision; tablet-range (740–1099px) composition; sub-360px rendering; the hamburger-drawer redundancy claim; the Arabic/RTL scope decision; and two smaller responsive-crowding/animation checks (long scenario titles, chart re-animation).

### Sufficiency statement

**The evidence is sufficient to proceed to the next design-review stage for every P0 and P1 item in this report.** Each rests on direct, independently-verified source evidence, self-computed measurements, or explicit product-intent documentation (`ideas.md`) — not on audit consensus alone. The evidence is **not** sufficient to finalize the ten items in §J without the specified validation, and is **not** sufficient to make several of the §L product/learning-design decisions, which require input from whoever owns those decisions rather than additional design analysis. No gap in this report should be read as a gap in analysis rigor — every unresolved item is unresolved because the evidence package genuinely does not contain the answer (no desktop/tablet screenshot exists; no learning-design brief specifying assessment isolation exists; no business decision on Arabic-market timing exists), and inventing one would violate this audit's explicit governing rule against assuming missing requirements or product decisions.

---

*End of Master Synthesis Audit.*
