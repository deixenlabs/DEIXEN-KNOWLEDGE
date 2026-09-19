AEROBRIDGE — UNIFIED MASTER DESIGN AUDIT

DESIGN STATUS

NEEDS TARGETED REVISION

---

1. EXECUTIVE VERDICT

AeroBridge is a genuinely high-fidelity, well-crafted prototype with a strong, distinctive visual identity ("Flight Deck Console"). It successfully conveys an operational, professional aviation-training aesthetic and establishes a clear learning loop: Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action. The Terminal/Practice screen is correctly positioned as the core workstation, and the cross-screen context hand-offs (e.g., from a Scenario or Growth recommendation into Practice) are real and functional, not decorative.

However, the prototype is not yet ready to serve as the definitive production design system. It is held back by a set of focused, mostly UI-level issues that undermine its core promise of "precision, trust, and operational readiness."

The primary gaps are:

1. Terminal Interaction Safety: An empty command submission silently executes FQD, which can create a false training event and corrupt assessment evidence. (Source-verified: Home.tsx:273-275).
2. Trust and Evidence Integrity: Hardcoded, illustrative numbers (e.g., "3/8 stages", "23/40 scenarios", a pre-submission accuracy of 86%) are presented without clear distinction from the actual, localStorage-backed learner evidence. This creates a fundamental trust issue.
3. Accessibility and Readability: The typography is consistently too small (7–10px labels), and critical text contrasts (--text-faint against --navy-950) fall below WCAG AA standards, making long-session use uncomfortable and inaccessible. The visual foundation is strong, but the reading layer is fragile.
4. Prototype Honesty: Numerous controls (Search, Profile, "My route", "Filters", "Backup") present as functional but only produce generic toast notifications. This creates false affordances and erodes the "professional" feeling.
5. Design System Drift: While a solid token foundation exists, late overrides and a second, parallel token system (--ab-* tokens) have created inconsistencies that must be consolidated.
6. Arabic / RTL Readiness: The EN/AR toggle is fully cosmetic, which is a critical gap for a product explicitly targeted at the Saudi aviation market.

What Must Be Preserved:

· The Flight Deck Console visual identity: deep navy surfaces, Vector Blue accents, green/amber operational states, monospace command/readout typography.
· The Terminal-first composition and Focus Mode.
· The real, wired learning loop and context hand-offs between screens.
· The existing accessibility strengths: global :focus-visible styling, aria-live regions for dynamic content, the chart's <details> data-table alternative, and thorough prefers-reduced-motion coverage.

The Path Forward:
The prototype does not need a redesign or architectural reset. It needs a Targeted Revision Pass. The work is focused on cleaning up the UI/UX layer: correcting unsafe behaviors, labeling prototype artifacts honestly, improving readability and accessibility, and consolidating the design system. This work can proceed without touching the command logic, scoring engine, or data model, ensuring a clean separation between the visual layer and the future real engine.

---

2. SOURCE COVERAGE & EVIDENCE OVERVIEW

The following materials were reviewed and audited. They form the basis for all findings and decisions in this report.

Artifacts Inspected

· Primary Source Code:
  · client/src/pages/Home.tsx (363 lines): The entire application shell, state management, navigation, and all five primary views (Progression, Practice/Terminal, Scenarios, Growth, Tracking).
  · client/src/index.css (409 lines): The complete design system, tokens, layout, responsive breakpoints, motion, focus-mode, and component styling.
  · client/src/App.tsx: The application root, which renders only <Home />.
  · client/src/const.ts: OAuth URL generation logic (non-visual, noted for completeness).
  · client/src/Map.tsx: A Google Maps integration component. It is never imported or used in the current prototype and is treated as dead code.
  · server/index.ts: Express static file server (non-visual, noted for completeness).
· Supporting Documentation:
  · ideas.md: The "Design Ground Truth" note. Used as intent context, not as source-truth.
· Visual Evidence:
  · 7 rendered mobile screenshots (Progression, Practice, Scenarios, Growth Record: Record/History/Reports, Progress Tracking). Used as primary visual evidence for rendered layout, hierarchy, and state at the captured viewport (~360–430px).
· Analytical Evidence:
  · 8 independent Design/UX Audits (ChatGPT, Claude, DeepSeek, Gemini, Grok, Kimi, Manus, Qwen, v0.dev). Used as analytical evidence, not as primary truth.

Coverage & Limitations

· High Confidence: Source code (Home.tsx, index.css) and live runtime behavior (as verified by the Manus audit) provide the strongest evidence for functional and structural issues.
· Medium Confidence: Screenshots provide direct visual evidence of the rendered UI, but only at mobile widths and for the specific states captured.
· Low Confidence / Inferred: The exact loaded state of fonts (Space Grotesk, Cairo, IBM Plex Mono) is inferred from the source (index.html has a commented-out Google Fonts link) and requires live verification. Exact color contrast ratios are computed from the CSS variables but require on-screen validation.
· Unverifiable / Validation Required: Physical touch-target hit areas, exact screen-reader announcement behavior, rendering at exact 320px and 768px widths, and behavior on real iOS/Android virtual keyboards with dynamic viewport heights.

---

3. AUDIT CONSENSUS OVERVIEW

The 8 audits show a remarkably high degree of consensus on the product's core strengths and primary weaknesses.

Strongest Consensus (E3 – Independently Corroborated)

· Visual Identity: All audits agree the "Flight Deck Console" identity is strong, mature, and distinctive, avoiding generic SaaS or game-like aesthetics.
· Terminal Primacy: All audits agree the Terminal is correctly positioned as the primary workstation, and Focus Mode is the single strongest UX decision.
· Learning Loop: All audits agree the Progression → Practice → Assessment → Growth → Tracking → Scenarios loop is conceptually sound and genuinely wired end-to-end (e.g., saveAssessment persists to localStorage and surfaces in Growth/Tracking).
· Mobile Terminal Engineering: Several audits (Claude, Manus, Kimi) praise the mobile Terminal engineering: forcing 16px font on the input to prevent iOS zoom, position: sticky with safe-area-inset-bottom, and a code comment explaining the intent.
· Reduced Motion: All audits praise the prefers-reduced-motion implementation as being more thorough than most production apps, with a global !important catch-all layered with component-specific refinements.

Conditional Consensus (E2 – Corroborated)

· Empty Command FQD Default: 8 of 8 audits flag this as a critical P0 risk. It is a definitive UI/Engine boundary problem. Verdict: ACCEPT.
· Typography Too Small: 8 of 8 audits identify 7–10px labels and low-contrast --text-faint as a major accessibility and long-session usability blocker. Verdict: ACCEPT.
· Non-Functional Controls: 8 of 8 audits catalog numerous controls (Search, Profile, Backup, Filters, etc.) that are toast-only. This is recognized as a core trust issue. Verdict: ACCEPT.
· Hardcoded/Mock Metrics: 8 of 8 audits note that illustrative numbers (e.g., "3/8", "23/40", "86% accuracy") are presented without clear distinction from real learner data. Verdict: ACCEPT.
· Font Loading: 8 of 8 audits note that while Space Grotesk, Cairo, and IBM Plex Mono are declared, there is no evidence they are actually loaded, making the typography non-deterministic. Verdict: ACCEPT.
· Arabic/EN Toggle: 8 of 8 audits flag the language toggle as purely cosmetic (toast-only, no dir="rtl", no i18n). This is a critical gap for the Saudi-market mission. Verdict: ACCEPT.
· Focus Mode is Strong: 8 of 8 audits agree Focus Mode is excellent but note it needs a focus trap, Escape key handling, and modal semantics. Verdict: ACCEPT WITH MODIFICATION.

Important Minority Insights (E0 – Single Claim, Strong Evidence)

· DeepSeek: Noted the "overly generous" scoring of the v0.dev audit and correctly identified the tracking-kpi clip-path decorations as a maintenance burden and source of visual noise that doesn't communicate data. Verdict: ACCEPT.
· Kimi: Flagged the mobile drawer as having no focus trap and not being a proper dialog (role="dialog", aria-modal). This was missed by some other audits but is a critical accessibility issue. Verdict: ACCEPT.
· Claude: Detailed the exact CSS duplication issue in the .bottom-nav (grid-template-columns declared 4 times, 3 redundant). This is a key design-system hygiene issue. Verdict: ACCEPT.
· Manus: Correctly identified the session timer as starting at a pre-seeded value (272s) rather than 0:00. This is a prototype artifact that undermines trust. Verdict: ACCEPT.
· v0.dev: Flagged the bottom-nav bug (5 items in a 4-column grid). While index.css line 118 is corrected later, this points to a CSS accumulation issue. Verdict: ACCEPT WITH MODIFICATION.

Strongest Disagreements (Resolved below)

· The "Coach" Panel Default State: Several audits (Grok, Manus, Claude) noted that the coach panel defaults to a FORMAT ERROR message. Others noted it as a critical defect. Resolution: This is a confirmed source-verified defect. The default state must be neutral, not error-styled. Verdict: ACCEPT.
· Per-Command Toasts: Some audits (ChatGPT, Kimi) noted this as duplicate feedback. Others (Manus) focused on the empty-input FQD default. Resolution: The empty-input FQD is the critical safety issue. Per-command toasts are a secondary UX concern. Verdict: CONDITIONAL CONSENSUS (Accept only if toast volume is reduced for long sessions).

---

4. CRITICAL DECISIONS

These are the foundational decisions that will shape all subsequent work.

CD-01: Evidence Truth and Prototype Honesty
The prototype must establish a strict visual contract for evidence. All metrics, scores, and readiness language must be verifiably derived from a single source of truth (localStorage) or be explicitly labeled as "illustrative," "local," or "demo-only." Hardcoded numbers are unacceptable.

· Status: ACCEPT
· Rationale: This is the single fastest way to build or erode trust in a precision-oriented product.

CD-02: Terminal Safety Contract
The Terminal is the product's core. Submitting an empty command must not execute a command, alter the session state, or create an evidence event. It must provide a clear, non-destructive inline validation message.

· Status: ACCEPT
· Rationale: This is a functional safety and evidence-integrity issue, not cosmetic polish.

CD-03: Typography and Readability Standard
The product will adopt a documented type scale with a hard minimum size of 12px for all metadata and 14px for instructional/reading text. All text must meet WCAG AA contrast standards at its rendered size.

· Status: ACCEPT
· Rationale: This is a non-negotiable accessibility and long-session usability requirement for a professional workstation.

CD-04: Design System Consolidation
The design system will be consolidated into one canonical set of semantic tokens, eliminating the duplicate --ab-* layer and route-specific overrides. This ensures maintainability and visual consistency.

· Status: ACCEPT
· Rationale: Scalability and future maintainability depend on a single source of truth for design decisions.

CD-05: Arabic/RTL as a First-Class Requirement
The EN/AR toggle will be disabled or re-labeled as "Coming Soon" until a full i18n/RTL solution is implemented. The existing --font-ar: Cairo token will be wired to [dir="rtl"] content as a foundational step.

· Status: ACCEPT WITH MODIFICATION
· Rationale: The mission requires it, but the scope must be clearly defined before engineering time is spent.

---

5. CANONICAL FINDINGS

The following is a curated list of the most critical, evidence-backed findings. Each finding is a single, definitive problem.

AB-F001: Empty Command Executes FQD

Attribute Value
Type Behavioral / Functional Safety
Source Audits All 8
Source Artifacts Home.tsx:273-275
Evidence Type Directly Verified (E4)
Consensus Strongest Consensus (C5)
Evidence Quality Very Strong
Observation On form submission, an empty or whitespace-only input is transformed into FQD before execution: `const nextCommand = command.trim().toUpperCase()
Impact A trainee can unintentionally create a false command/evidence event, corrupting session state and assessment scoring. This fundamentally undermines trust in the training environment.
Risk Critical. Directly violates the "evidence-first" principle and the "UI must never invent engine truth" rule.
Dependency Mixed (UI/Behavior). The `
Priority P0
Final Verdict ACCEPT
Decision The fallback must be removed. An empty submit must trigger an inline validation message ("Enter a command before executing.") and must not advance history, score, or state.
Action Modify the submitCommand handler in Home.tsx to check for command.trim() === "" and handle it as a no-op with an inline feedback message.
Validation Verify that submitting an empty command (a) does not append to history, (b) does not change LOG, (c) does not trigger a toast, and (d) results in a visible inline instruction.

---

AB-F002: Hardcoded Illustrative Metrics Are Presented as Truth

Attribute Value
Type Structural / Content
Source Audits All 8
Source Artifacts Home.tsx:67-95 (seed data), 205-207 (KPI stats), 335 (scenario stats), 343 (growth stats)
Evidence Type Directly Verified (E4)
Consensus Strongest Consensus (C5)
Evidence Quality Very Strong
Observation Hardcoded illustrative numbers are displayed as if they were authoritative learner data: "3 / 8 stages" vs 6 defined levels; "23/40 completed" vs 5 defined scenarios; "Accuracy 86%" before any command is submitted; "LOG 04 / 12" in Growth History vs 3 rendered entries.
Impact This is the fastest way to erode trust. A trainee who explores the product will discover the product's own numbers don't add up, directly contradicting the "precision, trustworthy" positioning.
Risk High. Directly impacts product credibility and professional maturity.
Dependency Content/Data-dependent. The UI must either derive values from the real data set or explicitly label them as illustrative.
Priority P0
Final Verdict ACCEPT
Decision Every summary number or fraction shown must be computed from the same dataset its corresponding detail view renders. Where this is not possible (e.g., a larger dataset is planned), the UI must clearly state what is currently available (e.g., "3 of 6 available now").
Action Replace all hardcoded summary strings with derived values from their respective arrays (e.g., levels.length, scenarios.length). Add a visible "Illustrative" marker to any value that cannot be derived.
Validation Verify that 3 / 8 stages is replaced with 3 of ${levels.length} stages, and that 23 / 40 is replaced with a value derived from scenarios.length.

---

AB-F003: Typography is Too Small and Low-Contrast

Attribute Value
Type Visual / Accessibility
Source Audits All 8
Source Artifacts index.css: global rules, --text-faint token, .terminal-body font-size
Evidence Type Directly Verified (E4)
Consensus Strongest Consensus (C5)
Evidence Quality Very Strong
Observation Pervasive use of 7–10px labels (eyebrows, metadata, terminal state labels). The --text-faint token (#5d6a85) against the --navy-950 background (#050914) has a computed contrast ratio of approximately 3.66:1, which is insufficient for normal-size body text under WCAG AA.
Impact The product is visually impressive at a glance, but long-session reading is uncomfortable and may be impossible for users with low vision. This is a critical accessibility failure.
Risk High. This is the single largest gap between "looks premium" and "is usable for hours of training."
Dependency UI-only. This is a pure design-system and CSS change.
Priority P0/P1
Final Verdict ACCEPT
Decision A documented type scale must be introduced. Metadata/eyebrow floor must be raised to 12px (or 11px with proper contrast). Reading/command/output text must be ≥14px on mobile and ≥13px on desktop. The --text-faint color must be adjusted to meet WCAG AA (≥4.5:1) against its actual background.
Action Define a new type scale in index.css. Replace all ad-hoc font-size literals with tokens from this new scale. Adjust --text-faint to a higher-luminance value.
Validation Re-compute contrast ratios for all text on all screens. Verify no reading text is below the new minimum font sizes.

---

AB-F004: Non-Functional Controls Create False Affordances

Attribute Value
Type Interaction / UX
Source Audits All 8
Source Artifacts Home.tsx:164, 166, 168, 219, 226, 229, 335, 343
Evidence Type Directly Verified (E4)
Consensus Strongest Consensus (C5)
Evidence Quality Very Strong
Observation A systemic pattern of visible controls (Search, Profile, "My route", "View map", "See all stages", "Filters", "Backup", etc.) that produce only a generic toast.info or toast.success instead of performing the implied action.
Impact This directly contradicts the "Confidence/Precision" feeling the product aims for. It creates a "looks functional, isn't" pattern that erodes trust, especially on the most important screens.
Risk Medium-High. This is the single most repeated source of "prototype theater."
Dependency Mixed. Most are UI-only to remove/relabel. Some (e.g., Search, real Filtering/Sorting) are legitimately Content/Engine-dependent.
Priority P1/P2
Final Verdict ACCEPT WITH MODIFICATION
Decision Every control must meet one of three outcomes: (1) Perform its implied action, (2) Be explicitly labeled as "coming soon" or "preview" and visually de-emphasized, or (3) Be removed from the UI. No control may pretend to perform an action it does not.
Action For each identified control, make a product decision (wire/relabel/remove) and implement it.
Validation Conduct a full UI walkthrough; no control that appears actionable may produce only a generic toast.

---

AB-F005: Declared Fonts Are Not Loaded/Provisioned

Attribute Value
Type Typography / Design System
Source Audits All 8
Source Artifacts index.css:32-34, client/index.html
Evidence Type Directly Verified (E4)
Consensus Strongest Consensus (C5)
Evidence Quality Very Strong
Observation The CSS declares --font-display: "Space Grotesk", --font-ar: "Cairo", and --font-mono: "IBM Plex Mono". However, the Google Fonts <link> block in index.html is explicitly commented out, and no local font files exist. The product currently renders in browser/OS fallback fonts.
Impact The entire typographic identity is theoretical. The product does not render as designed. Furthermore, the Arabic font role is completely unused, which is a critical gap for the Saudi-market mission.
Risk Critical. This is the single largest gap between design intent and shipped reality.
Dependency UI-only. This is a straightforward font-loading fix.
Priority P0
Final Verdict ACCEPT
Decision All three declared typefaces must be deterministically loaded and render on their respective roles. The mechanism (Google Fonts <link> or self-hosting) is an implementation detail.
Action Uncomment the Google Fonts <link> in index.html or implement a self-hosting strategy. Ensure --font-ar is wired to apply to [dir="rtl"] content.
Validation Inspect the computed font-family on a heading, a terminal command, and Arabic body text. Each must resolve to the intended named family, not a fallback.

---

AB-F006: Arabic/RTL Language Toggle is Fully Cosmetic

Attribute Value
Type Content / Architecture
Source Audits All 8
Source Artifacts Home.tsx:164, client/index.html, index.css
Evidence Type Directly Verified (E4)
Consensus Strongest Consensus (C5)
Evidence Quality Very Strong
Observation The EN/AR toggle in the topbar only updates a local state to change a highlight and fires a toast.success. There is no dir="rtl" injection, no translation layer, no content change, and no typography switch.
Impact Given the product's explicit mission (Saudi-market readiness, mixed English/Arabic operational content), this is the single largest gap between stated purpose and shipped behavior. The UI promises a feature that does not exist.
Risk Critical.
Dependency Content + Engine + Architecture. A real fix requires a translation layer, RTL layout mirroring throughout the CSS, and the already-defined-but-unloaded --font-ar wired to [dir="rtl"] content.
Priority P0 (as a scoping decision); P2–P3 (as a build-out).
Final Verdict ACCEPT WITH MODIFICATION
Decision Until full i18n/RTL exists, the toggle must not visually imply a working language switch. It should be disabled and labeled "Coming soon," or hidden. The foundational work (wiring --font-ar to [dir="rtl"]) should be specified as a separate, preparatory task.
Action Disable or hide the EN/AR toggle. Add a [dir="rtl"] specification to the design system for when the feature is built.
Validation The toggle is no longer interactive or visually implies a working feature. The [dir="rtl"] specification is documented.

---

AB-F007: Coach Panel Defaults to a Fabricated Error

Attribute Value
Type Behavioral / UX
Source Audits Manus, Claude, Qwen, Kimi
Source Artifacts Home.tsx:311, index.css (.coach-block code { color: var(--red) })
Evidence Type Directly Verified (E4)
Consensus Conditional Consensus (C2)
Evidence Quality Very Strong
Observation Before any command is submitted, the Coach panel renders FORMAT ERROR · CHECK ENTRY styled in red, along with a fabricated corrective instruction ("The availability entry needs the airline prefix..."). This happens immediately below a neutral "AWAITING COMMAND" label.
Impact This is a first-run trust defect on the single most important screen in the product. It creates a contradictory state (READY vs ERROR) and misleadingly implies the user has already made a mistake.
Risk Critical. Directly contradicts the "calm, precise, professional workstation" goal at the first moment of use.
Dependency UI/Content-only. This is a conditional-rendering and copy fix.
Priority P0
Final Verdict ACCEPT
Decision The default/no-entry Coach state must show neutral placeholder guidance. Nothing in the Coach panel may be styled or worded as an error before a command is submitted.
Action Modify the conditional rendering in the Coach panel to display a neutral message (e.g., "Submit a command to see coaching feedback here") when latestEntry is undefined. Ensure the default styling is not var(--red).
Validation On first entry into Practice, before any command is submitted, the Coach panel contains no error-styled content.

---

AB-F008: Focus Mode Lacks Focus Trap and Modal Semantics

Attribute Value
Type Interaction / Accessibility
Source Audits Kimi, Qwen, v0.dev
Source Artifacts index.css:193-200 (.focus-mode rules), Home.tsx:309 (toggle logic)
Evidence Type Directly Verified (E4)
Consensus Conditional Consensus (C2)
Evidence Quality Very Strong
Observation Focus Mode is a strong idea and currently uses CSS to create a full-screen overlay. However, it lacks a focus trap (keyboard users can Tab out of the terminal into the browser chrome), has no Escape key handler, and is not semantically a modal/dialog region.
Impact Keyboard and assistive technology users lose predictable, contained navigation within the workstation.
Risk Medium-High. Affects accessibility and professional workstation feel.
Dependency UI-only. This is an interaction and accessibility fix.
Priority P1
Final Verdict ACCEPT
Decision Focus Mode must be a true modal region: it must trap keyboard focus, cycle focus through its interactive elements, and exit predictably on Escape.
Action Implement a focus trap around the focus mode region. Add role="dialog" and aria-modal="true" semantics. Add an Escape key handler that exits focus mode.
Validation With a keyboard, enter focus mode and verify that Tab cycles through the interactive elements and does not leave the terminal panel. Press Escape and verify it exits focus mode.

---

AB-F009: Missing "Skip to Main Content" Link and <main> Landmark

Attribute Value
Type Accessibility
Source Audits Kimi, Qwen, v0.dev
Source Artifacts Home.tsx:362 (div.app-main)
Evidence Type Directly Verified (E4)
Consensus Strong Consensus (C3)
Evidence Quality Very Strong
Observation The main content is wrapped in a generic div.app-main. There is no <main> landmark and no "Skip to main content" link.
Impact Keyboard users and screen-reader users must navigate through the entire topbar, sidebar, and bottom navigation on every page load before reaching the main content. This is a significant efficiency and accessibility barrier.
Risk Medium-High. Affects accessibility.
Dependency UI-only.
Priority P1
Final Verdict ACCEPT
Decision Add a <main> landmark around the page content and a visually hidden "Skip to main content" link as the first focusable element.
Action Wrap {content} in <main id="main-content">. Add <a href="#main-content" className="skip-link">Skip to main content</a> as the first element in the app-frame. Style .skip-link to be visible only on focus.
Validation Tab from the address bar and verify the "Skip to main content" link is the first focusable element. Activating it moves focus to the <main> landmark.

---

AB-F010: Design System Token Duplication and CSS Accumulation

Attribute Value
Type Design System / Structural
Source Audits Claude, DeepSeek, v0.dev
Source Artifacts index.css: :root (lines 7–35) and later :root block (lines 329–335, --ab-* tokens)
Evidence Type Directly Verified (E4)
Consensus Strong Consensus (C3)
Evidence Quality Very Strong
Observation The CSS file contains two :root blocks with overlapping semantic token layers. The --ab-* tokens (e.g., --ab-error: #ef8a96) have subtly different values from the base tokens (e.g., --red: #f27076). Furthermore, .bottom-nav grid-template-columns is declared 4 times, with 3 redundant declarations.
Impact This indicates refinement accumulation and creates a maintenance hazard. A future color change made in one token layer won't reach the other. The duplicated CSS increases complexity and risk.
Risk Medium (maintainability) / Low (user-facing).
Dependency UI-only.
Priority P1
Final Verdict ACCEPT
Decision Consolidate the design system into one canonical set of semantic tokens. Ensure --ab-* values (which appear to be the more recent, more deliberate pass) are promoted to the global token set. Remove all duplicate CSS declarations.
Action Fold the --ab-* tokens into the base :root token set. Remove the duplicate .bottom-nav grid declarations. Audit the rest of the CSS for similar redundant overrides and consolidate them.
Validation Grepping the stylesheet for a legacy --ab- reference returns nothing. The .bottom-nav grid is declared only once.

---

6. DESIGN SYSTEM DECISIONS

These decisions formalize the visual and interaction language of the product.

DS-01: Typography

Attribute Value
Decision Adopt a documented type scale with a minimum size of 12px for metadata and 14px for body/instructional text. Ensure all three declared font families (Space Grotesk, Cairo, IBM Plex Mono) are deterministically loaded. Cairo must be applied to [dir="rtl"] content.
Why To ensure long-session readability, meet accessibility standards, and fulfill the Saudi-market mission's typographic requirements.
Scope Global.
Priority P0/P1
Dependency UI-only.
Validation Inspect computed font sizes and contrast ratios on all screens.

---

DS-02: Color and Contrast

Attribute Value
Decision Consolidate all color tokens into a single, canonical set. Adjust the --text-faint token so it meets WCAG AA (≥4.5:1) against its intended backgrounds. Ensure the .primary-button text/background pairing meets ≥4.5:1.
Why To ensure accessibility and maintain design consistency.
Scope Global.
Priority P0/P1
Dependency UI-only.
Validation Recompute contrast ratios for all core color pairs.

---

DS-03: Surfaces and Elevation

Attribute Value
Decision Establish three distinct surface levels (--surface-base, --surface-elevated, --surface-overlay) and one primary workstation surface (--surface-terminal). Remove decorative clip-paths and route-map guilloché patterns from KPI cards.
Why To create a clear visual hierarchy and reduce unnecessary visual noise.
Scope Global.
Priority P2/P3
Dependency UI-only.
Validation Visual inspection confirms a clear hierarchy of surfaces.

---

DS-04: Borders and Radius

Attribute Value
Decision Consolidate all border-radius values into a small, documented scale (e.g., --radius-sm: 8px, --radius: 12px, --radius-lg: 16px, --radius-pill: 999px). Replace all ad-hoc values with tokens from this scale.
Why To ensure visual consistency and simplify future maintenance.
Scope Global.
Priority P1/P2
Dependency UI-only.
Validation A full CSS audit confirms no hardcoded border-radius values outside the defined scale.

---

DS-05: Spacing

Attribute Value
Decision Adopt a 4px-based spacing scale. Replace all ad-hoc padding, gap, and margin values with tokens from this scale.
Why To create a consistent vertical and horizontal rhythm across the product.
Scope Global.
Priority P2
Dependency UI-only.
Validation A full CSS audit confirms no ad-hoc spacing values outside the defined scale.

---

DS-06: State System

Attribute Value
Decision Define a formal state system where every operational state (SystemState) has a visual treatment consisting of: color + text + icon (where critical). No state may rely on color alone.
Why To ensure accessibility and unambiguous state communication.
Scope Global.
Priority P1
Dependency UI-only.
Validation A visual audit confirms that no state is communicated solely through color.

---

DS-07: Motion

Attribute Value
Decision Preserve the existing prefers-reduced-motion implementation, which is exemplary. Document a motion budget (enter ≤240ms, number count ≤800ms) to prevent over-animation. Ensure the terminal caret also respects reduced motion.
Why To maintain the calm, precise workstation feel and ensure accessibility for motion-sensitive users.
Scope Global.
Priority P2
Dependency UI-only.
Validation Activating system reduced-motion preferences disables all non-essential animation, including the caret blink.

---

7. GLOBAL UX DECISIONS

These decisions define the broader interaction and information architecture patterns.

UX-01: Navigation and Orientation

Attribute Value
Decision Resolve the desktop/mobile navigation order mismatch. The mobile bottom nav reorders to center "Train" (Practice), but the "YOUR ROUTE / 0N" breadcrumb is based on the desktop order. Either compute the breadcrumb based on the current nav order, or remove the numeric indicator. Rename either the Progression tab's short label ("Route") or the umbrella breadcrumb term to avoid confusion.
Why A mobile user should never see a screen's breadcrumb contradict its position in the navigation bar.
Scope Global shell.
Priority P2
Dependency UI/Content.
Validation Tapping each bottom-nav icon in order produces a breadcrumb that matches that icon's position.

---

UX-02: Next-Action Visibility

Attribute Value
Decision Every primary screen must end with an explicit, unambiguous "Next Action" CTA. This CTA must always route to Practice with the correct context pre-loaded.
Why To ensure the learning loop is never broken and the user is always guided to the next useful step.
Scope All screens.
Priority P1
Dependency UI-only.
Validation From any screen, the primary CTA opens Practice with the correct context.

---

8. TERMINAL / WORKSTATION DECISIONS

These decisions are specific to the Practice/Terminal screen, the product's core.

T-01: Session State Visibility

Attribute Value
Decision Ensure the SESSION / COMMAND / LOG readout is visible on all viewports, including mobile. On mobile, it may be restructured into a compact bar but must never be hidden.
Why A trainee must be able to understand their session state within seconds on any device.
Scope Practice/Terminal.
Priority P0/P1
Dependency UI-only.
Validation On a mobile viewport, the session readout is visible and readable.

---

T-02: Command History Auto-Scroll

Attribute Value
Decision The Terminal body must auto-scroll to show the latest entry when a new command is submitted. This is a standard interaction in any command-line interface.
Why To reduce friction and ensure the trainee always sees the result of their latest action.
Scope Practice/Terminal.
Priority P1
Dependency UI-only.
Validation Submitting a new command results in the terminal body automatically scrolling to the bottom to reveal the new entry.

---

T-03: Coach Panel Behavior on Mobile

Attribute Value
Decision On mobile, convert the coach panel from a block below the fold to a floating action button (FAB) or a collapsible bottom sheet. This keeps coaching one tap away without consuming vertical workspace.
Why To preserve the Terminal's vertical space for output and input while ensuring coaching remains accessible.
Scope Practice/Terminal.
Priority P1
Dependency UI-only.
Validation On mobile, the coach panel is not a large block below the terminal. It is accessible via a FAB or bottom sheet.

---

T-04: Assessment Mode "No Hints" Visual

Attribute Value
Decision Ensure the "No hints" state in Assessment mode is a live reflection of the session's hint usage. A trainee who used hints in Learn/Practice mode before switching to Assessment must see a warning that hints have been used, not a static "No hints" label.
Why To prevent a trainee from mistakenly believing an assessment is clean when it is not.
Scope Practice/Terminal.
Priority P1/P2
Dependency Mixed (UI + State).
Validation Switching to Assessment mode with a non-zero hint count displays a warning that hints have been used.

---

9. LEARNING UX DECISIONS

These decisions ensure the product's educational integrity.

L-01: Mode Switch Integrity

Attribute Value
Decision Switching between Learn, Practice, and Assessment modes must be deterministic and transparent. The UI must communicate what is preserved, what is reset, and whether the current session remains valid. The current behavior (reset sessionComplete but retain history) is confusing and must be addressed.
Why To prevent evidence bleed and ensure the trainee understands the contract of each mode.
Scope Practice/Terminal.
Priority P1
Dependency State/Data-dependent.
Validation Switching modes results in a clear, predictable change to the session state.

---

L-02: Scenario Recommendation and Filter Honesty

Attribute Value
Decision The Scenario "Filters" and "Sort" controls must perform their implied action using data already present on each scenario object. If this is not possible, they must be marked as "Coming soon." The filter tabs are functional and sufficient.
Why To maintain trust and provide a functional mission discovery experience.
Scope Scenarios.
Priority P2
Dependency UI-only (wiring existing data) / Content (if new data is needed).
Validation Clicking "Filters" does not produce a toast; it opens a functional filter panel (or the button is removed). The sort <select> actually sorts the scenario list.

---

10. RESPONSIVE DECISIONS

These decisions define the product's behavior across different viewports.

R-01: Desktop (≥1100px)

Attribute Value
Decision Preserve the current desktop layout: persistent sidebar, terminal-focused Practice with sticky coach. Ensure the Terminal is the unquestioned center of gravity.
Why The desktop layout is strong and functional.
Priority P3 (Preservation/Polish)
Validation Practice remains a split-panel layout with the Terminal dominating.

---

R-02: Laptop / Tablet (740–1099px)

Attribute Value
Decision Maintain the current behavior where content grids go multi-column at 740px, but navigation remains the mobile bottom-nav until 1100px. This is an acceptable pattern, but it should be validated on actual devices to ensure it doesn't feel awkward.
Why To provide a consistent experience on a common device class.
Priority P2
Dependency UI-only.
Validation Render the shell at 768px, 834px, and 1024px and confirm the navigation chrome and content density feel coherent.

---

R-03: Mobile (≤739px)

Attribute Value
Decision Extend the existing 360px Terminal header grid restructure down to 320px, the declared design floor. Ensure the command input, session state, and bottom navigation are usable at all widths.
Why To ensure the product is fully functional on the narrowest supported devices.
Priority P1/P2
Dependency UI-only.
Validation Render the Terminal header at exactly 320px and confirm no element is clipped or overlaps.

---

11. ACCESSIBILITY DECISIONS

These decisions ensure the product is usable by everyone, in line with professional standards.

A-01: Keyboard and Focus Management

Attribute Value
Decision Implement a complete focus management strategy. This includes: a skip link, focus traps for all overlays (drawers, modals, focus mode), logical tab order, visible :focus-visible styling on all interactive elements, and focus restoration after overlay closure.
Why To ensure full keyboard accessibility.
Scope Global.
Priority P0/P1
Dependency UI/Interaction.
Validation Keyboard-only navigation is possible through all core flows. Focus is managed predictably in all overlays.

---

A-02: Touch Target Sizing

Attribute Value
Decision Ensure all interactive elements (icon buttons, text actions, filter tabs, navigation items) have a minimum touch target of 44×44px on mobile viewports.
Why To meet WCAG 2.5.5 (Target Size) and ensure usability on touch devices.
Scope Global.
Priority P1/P2
Dependency UI-only.
Validation Inspect all interactive elements on a 390px viewport. Elements smaller than 44×44px must have adequate padding to be effectively targetable.

---

A-03: Non-Color State Communication

Attribute Value
Decision Every state (success, error, warning, etc.) must be communicated through a combination of color + text + icon. Color may never be the sole indicator.
Why To ensure accessibility for users with color vision deficiencies.
Scope Global.
Priority P1
Dependency UI-only.
Validation A grayscale or accessibility audit confirms that every state is understandable without color.

---

A-04: Chart Accessibility

Attribute Value
Decision Preserve the existing <details> data-table alternative. Enhance it by ensuring the chart's aria-label provides a meaningful description, and that the table is the authoritative accessible representation.
Why The existing pattern is strong and should be protected.
Scope Progress Tracking.
Priority P1/P2
Dependency UI-only.
Validation A screen reader can access the data table and understand the chart's data.

---

12. SCREEN-BY-SCREEN AUDIT

This section maps the canonical findings and design decisions to each screen.

Shell (Topbar, SideNav, BottomNav, Mobile Drawer)

Attribute Value
Current Strengths Real URL sync, deliberate center-emphasis on mobile "Train" button, color-scheme: dark, global :focus-visible.
Critical Problems Bottom-nav 4-col/5-item bug (AB-F010), no <main> landmark/skip link (AB-F009), mobile drawer lacks focus trap/modal semantics, aria-current missing on side-nav, search/language/profile are toast-only.
Required Changes Fix bottom-nav CSS, add <main>/skip link, make drawer a proper modal, add aria-current to side-nav, resolve/defer all toast-only controls.
Priority P0/P1/P2
Dependency UI-only (for layout/semantics), Mixed (for toast-only controls).

---

Progression

Attribute Value
Current Strengths Strong hero card with single CTA, clear "locked/current/mastered" states, track tabs (Technical/Service).
Critical Problems "3/8 stages" vs 6 defined levels (AB-F002), "View map" and "See all stages" are toast-only, Service track swaps description but not content.
Required Changes Derive 3/8 from levels.length, wire or remove toast-only actions, add an explicit empty state for the Service track.
Priority P1/P2
Dependency Content/Data-dependent.

---

Practice / Terminal

Attribute Value
Current Strengths Terminal-first composition, mode tabs, command history, Focus Mode, coach, reference, assessment closure.
Critical Problems Empty command executes FQD (AB-F001), Coach panel defaults to error (AB-F007), session readout hidden on mobile, typography too small (AB-F003), session timer starts at 4:32 (prototype artifact).
Required Changes Fix empty-submit behavior, fix Coach default state, ensure session state visible on mobile, fix typography, start timer at 0.
Priority P0/P1
Dependency Mixed (AB-F001, AB-F007 are UI/Behavior fixes; timer is UI-only).

---

Scenarios

Attribute Value
Current Strengths Mission-file framing, filter tabs are functional, detail panel is well-structured.
Critical Problems KPI stats are hardcoded and reference a non-existent category ("Exchanges & Refunds") (AB-F002), "Filters" button duplicates working tabs, Sort control doesn't sort.
Required Changes Derive stats from scenarios.length, remove/relabel "Filters" button, make sort control functional or mark as coming soon.
Priority P1/P2
Dependency Content/Data-dependent (stats), UI-only (filters/sort).

---

Growth Record

Attribute Value
Current Strengths Three-tab structure, learning-loop-strip, strengths/needs-attention panels, skill rows with hover preview (which is itself a strength on desktop).
Critical Problems "Backup" is toast-only (AB-F004), History claims "LOG 04/12" vs 3 rendered entries (AB-F002), trend-arrow color maps to literal direction, not favorability (a risk with real data).
Required Changes Remove/relabel "Backup", derive LOG count from data, fix trend-arrow color logic to be based on favorability, move hover-preview content into the selected skill panel for mobile parity.
Priority P1/P2
Dependency Mixed (Content/Data for counts, UI-only for trend/hover behavior).

---

Progress Tracking

Attribute Value
Current Strengths Metric switcher, accessible <details> data-table alternative, non-color trend labels, real data drives the chart.
Critical Problems KPI decorative clip-paths add complexity without value, chart re-animates on every metric switch (distracting), route-line label truncates on mobile.
Required Changes Remove decorative clip-paths, replace keyframe animation with CSS transitions for metric switching, handle label truncation gracefully.
Priority P2
Dependency UI-only.

---

13. KEEP / PRESERVE

These elements are the product's strengths and must survive the revision pass.

· Flight Deck Console visual identity: Deep navy, Vector Blue accents, green/amber/red operational states.
· Terminal-first Practice composition: The Terminal is the heart of the product.
· Focus Mode: An excellent, immersive workstation pattern.
· The five-screen learning loop: Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action.
· Real context hand-offs: setPracticeContext makes the loop feel connected.
· prefers-reduced-motion implementation: The global !important catch-all and component-specific refinements are more thorough than most production apps.
· Accessibility foundations: Global :focus-visible, aria-live regions, role="table" chart alternative, StateNotice role="alert"/role="status" pairing.
· Explicit local simulation labeling: "LOCAL TRAINING SIMULATION" and "RESPONSE MODEL / ILLUSTRATIVE" labels are exactly the right instinct.
· Mobile input engineering: Forcing 16px font to prevent iOS zoom, position: sticky with safe-area-inset-bottom.

---

14. DO NOT DO

These changes must be avoided to preserve the product's identity and integrity.

· Do not redesign the visual identity unnecessarily. The Flight Deck Console is strong.
· Do not add decorative features without purpose. More visual noise is not the solution.
· Do not add metrics without meaning. Every metric must answer a concrete operational question.
· Do not invent engine semantics. The UI may interpret engine state, but it must never invent it.
· Do not fake unavailable functionality. Controls that don't work should be disabled or marked "Coming soon."
· Do not turn prototype metrics into authoritative evidence. Hardcoded illustrative numbers must be labeled as such.
· Do not turn the Terminal into a dashboard card. The Terminal is the primary workstation.
· Do not over-gamify the product. Aviation training should feel measured, not gamified.
· Do not rely on color alone for state. Always pair color with text or icon.
· Do not change the architecture without evidence. The single-component architecture is legible and works.
· Do not add features simply because one Audit suggested them. All changes must be evidence-based and product-fit tested.
· Do not solve architecture problems through styling alone.
· Do not create a second source of truth for engine state. The UI must remain a presentation layer.

---

15. CONFLICTS RESOLVED

Conflict: Per-Command Toasts vs. Terminal Feedback

Attribute Value
Conflict Some audits (ChatGPT, Kimi) recommend removing per-command toasts entirely as they duplicate Terminal feedback. Others (Manus) focus on the empty-input FQD default as the primary safety issue.
Relevant Sources All 8 audits.
Evidence The Terminal already provides persistent feedback via the command history. Toasts are transient and can become noisy over a long session.
Competing Positions Position A: Toasts should be reserved for system-level events (e.g., session finished, assessment saved). Position B: Toasts are fine as an additional signal for command success/error.
Resolution ACCEPT POSITION A. Command-level feedback is best kept in the Terminal. The volume of toasts is a secondary UX concern. The primary P0 concern (empty-input FQD) must be fixed.
Decision Toasts are reserved for session-level events. Per-command feedback is handled exclusively in the Terminal.
Validation A 15+ command session produces only system-level toasts, not a toast for every command.

---

Conflict: Arabic/RTL Implementation Priority

Attribute Value
Conflict The EN/AR toggle is a critical gap for the Saudi-market mission, but implementing full i18n/RTL is a substantial architectural and content effort.
Relevant Sources All 8 audits.
Evidence The toggle is currently a toast stub. index.html has lang="en" and no dir="rtl". The product's mission explicitly calls for Saudi-market readiness.
Competing Positions Position A: This is a P0/P1 issue that must be addressed immediately. Position B: This is a major engineering effort; the UI should not "fake" it and should defer it to a later phase.
Resolution CONDITIONAL CONSENSUS. The current fake toggle is unacceptable and must be addressed now. The full build-out is a Phase P2/P3 item.
Decision The toggle will be disabled and labeled "Coming soon" as a P0 scoping decision. The foundational work (wiring --font-ar to [dir="rtl"]) will be specified, but the full implementation is deferred.
Validation The language toggle is no longer interactive or visually implies a working feature. The [dir="rtl"] specification is documented in the design system.

---

16. NEW INSIGHTS / AUDIT GAPS

The following new insights were identified during the synthesis that were not explicitly called out in a single audit, but are derived from the combined evidence and product context.

NI-01: Mobile Coach as a Floating Action Button (FAB)

Observation: The coach panel on mobile is currently a block below the Terminal fold. This is an awkward placement that either consumes valuable vertical space or pushes critical guidance far away from the command input. A FAB or bottom sheet pattern would preserve terminal space while keeping coaching one tap away.

Evidence: All audits agree the coach is subordinate to the Terminal, but its placement on mobile is a point of friction. The order: 2 CSS rule moves it below the fold, which is correct for hierarchy but poor for discoverability and feedback timing.

Why it matters: The coach is a primary learning tool. On mobile, a trainee should not have to scroll past the entire command history to read the guidance.

Confidence: High (derived from UX principles and the mobile constraints).
Recommendation: Convert the mobile coach to a FAB or bottom sheet. This is a UI-only change that keeps the coach accessible without reducing terminal workspace.
Priority: P1
Dependency: UI-only.

---

NI-02: Assessment Mode "Finish Session" Confirmation

Observation: The "Finish Session" button currently executes the assessment closure on a single click. In a professional training environment, a confirmation step (or a two-click "Are you sure?" action) is standard to prevent accidental completion and data loss.

Evidence: Home.tsx:306 shows the terminal-finish button. While disabled={!commandHistory.length} prevents empty submissions, there is no confirmation dialog.

Why it matters: This adds a layer of safety and intent to a high-stakes action (finalizing an assessment score).
Confidence: High.
Recommendation: Add a two-step confirmation: the first click changes the button label to "Confirm finish", the second click executes the action.
Priority: P1
Dependency: UI-only.

---

NI-03: Assessment Debrief "Next Action" Variants

Observation: The assessment debrief provides a strong "Next Training Move" recommendation. However, the available actions are limited to "Retry assessment." The report should offer a more contextual set of next actions based on the score, such as "Open targeted practice" (if score is low), "Move to a scenario" (if score is high), or "Review evidence" (if score is borderline).

Evidence: Home.tsx:233-236 shows the AssessmentReport component. The current recommendation string is text-only and the only CTA is onRestart.

Why it matters: Closing the learning loop is a core UX goal. The debrief is the perfect place to guide the trainee to the next useful step.
Confidence: Medium-High.
Recommendation: The debrief should offer 1-2 context-aware CTAs. A low score should offer "Retry assessment" and "Open targeted practice". A high score should offer "Move to a scenario" and "View evidence". The existing AssessmentRecord data can be used to drive this.
Priority: P2
Dependency: Mixed (UI + Data).

---

17. FINAL PRIORITY MATRIX

Finding ID Issue / Decision Sources Evidence Independence Consensus Evidence Quality Impact Risk Dependency Priority Verdict
AB-F001 Empty command executes FQD All 8 Home.tsx:273-275 E4 C5 Very Strong Critical Critical Mixed P0 ACCEPT
AB-F002 Hardcoded metrics presented as truth All 8 Home.tsx:67-95, etc. E4 C5 Very Strong Critical High Content/Data P0 ACCEPT
AB-F005 Declared fonts are not loaded All 8 index.css, index.html E4 C5 Very Strong Critical High UI-only P0 ACCEPT
AB-F006 Arabic/RTL toggle is cosmetic All 8 Home.tsx:164 E4 C5 Very Strong Critical High Mixed P0 (Scope) ACCEPT WITH MOD
AB-F007 Coach panel defaults to error 4 audits Home.tsx:311, CSS E4 C2 Very Strong Critical High UI/Content P0 ACCEPT
AB-F003 Typography too small/low-contrast All 8 index.css, Screenshots E4 C5 Very Strong High High UI-only P1 ACCEPT
AB-F004 Non-functional controls create false affordances All 8 Home.tsx toast calls E4 C5 Very Strong High High Mixed P1/P2 ACCEPT WITH MOD
AB-F009 Missing skip link / <main> landmark 3 audits Home.tsx:362 E4 C3 Very Strong Medium Medium UI-only P1 ACCEPT
AB-F008 Focus Mode lacks focus trap 3 audits index.css, Home.tsx E4 C2 Very Strong Medium Medium UI/Interaction P1 ACCEPT
AB-F010 Design system token duplication 3 audits index.css E4 C3 Very Strong Medium Low-Med UI-only P1 ACCEPT
NI-01 Mobile coach as FAB Synthesis UX Principles E2 N/A High Medium Medium UI-only P1 ACCEPT
NI-02 Assessment finish confirmation Synthesis UX Principles E2 N/A High Medium Low UI-only P1 ACCEPT
UX-01 Nav order mismatch/Route naming 3 audits Home.tsx:176-185 E4 C3 Strong Medium Low Content+UI P2 ACCEPT
NI-03 Assessment debrief next actions Synthesis UX Principles E2 N/A Medium Medium Low Mixed P2 ACCEPT

---

18. IMPLEMENTATION SEQUENCE

The work should proceed in controlled phases, not a massive redesign.

Phase A — Design System Foundations (P0/P1)

· Goal: Establish the visual and technical foundation for all subsequent work.
· Work:
  · Load the three declared font families (AB-F005).
  · Consolidate the token system, removing duplicate --ab-* tokens (AB-F010).
  · Define and enforce a new type scale, raising minimum font sizes and adjusting contrast (AB-F003).
  · Formalize the state system (color + text + icon).

Phase B — Core Workstation / Terminal Safety (P0/P1)

· Goal: Fix the Terminal's critical interaction safety issues.
· Work:
  · Fix empty-submit behavior: no FQD, no state change, just inline validation (AB-F001).
  · Fix the Coach default state: replace the fabricated error with neutral guidance (AB-F007).
  · Ensure the session readout (SESSION / COMMAND / LOG) is visible on all viewports (T-01).
  · Add the mobile Coach FAB or bottom sheet (NI-01).
  · Add a two-step confirmation for "Finish Session" (NI-02).

Phase C — Trust & Evidence Integrity (P0/P1)

· Goal: Eliminate prototype artifacts that undermine trust.
· Work:
  · Derive all summary numbers (e.g., "3/8", "23/40") from their respective data arrays (AB-F002).
  · Disable/relabel the EN/AR toggle until real i18n exists (AB-F006).
  · Resolve all toast-only controls: wire, relabel, or remove (AB-F004).
  · Fix the hardcoded session timer (start at 0:00).

Phase D — Primary Learning / Progression (P1/P2)

· Goal: Refine the core learning loop and supporting screens.
· Work:
  · Resolve the navigation order mismatch and "Route" naming conflict (UX-01).
  · Implement context-aware next actions in the Assessment debrief (NI-03).
  · Add explicit empty states to Scenarios filters and Progress Tracking charts.
  · Add the Service track empty state in Progression.

Phase E — Accessibility & Responsive Hardening (P1/P2)

· Goal: Ensure the product is usable by everyone on all devices.
· Work:
  · Add a <main> landmark and "Skip to main content" link (AB-F009).
  · Add focus traps and modal semantics to mobile drawer, focus mode, and reference drawer (AB-F008).
  · Ensure all interactive elements meet 44×44px touch targets on mobile.
  · Extend the 360px Terminal header grid restructure down to the 320px floor.
  · Validate and harden the 320px, 360px, 390px, and 768px layouts.

Phase F — Polish & Final Hardening (P2/P3)

· Goal: Add polish and address remaining low-priority items.
· Work:
  · Remove decorative clip-paths from Tracking KPIs.
  · Add aria-current to the desktop side-nav.
  · Clean up duplicate CSS declarations in .bottom-nav.
  · Harden the reduced-motion implementation (ensure caret blink is disabled).
  · Documentation of all design system decisions.

---

19. VALIDATION PLAN

The following validations are required to ensure the success of the revision.

AB-F001: Empty Command FQD Default

· What to test: Submitting an empty command.
· Where: Practice/Terminal screen.
· Device/Viewport: All.
· Expected behavior: (a) No command is appended to history, (b) LOG does not increment, (c) no toast is triggered, (d) an inline message ("Enter a command to continue.") is displayed.
· Failure condition: Any state change or evidence event occurs.

AB-F003: Typography and Contrast

· What to test: Font sizes and contrast ratios.
· Where: Global.
· Device/Viewport: All.
· Expected behavior: No reading text is below 12px on mobile or 13px on desktop. All text meets WCAG AA (≥4.5:1) contrast against its background.
· Failure condition: Text below the minimum size or contrast ratio failing AA.

AB-F007: Coach Default State

· What to test: The initial state of the Coach panel.
· Where: Practice/Terminal.
· Device/Viewport: All.
· Expected behavior: The Coach panel shows neutral guidance (e.g., "Submit a command to see coaching feedback here.") and contains no red (--red or --ab-error) error-styled content.
· Failure condition: The panel shows a fabricated error message or error styling.

AB-F008: Focus Mode Focus Trap

· What to test: Keyboard navigation in Focus Mode.
· Where: Practice/Terminal.
· Device/Viewport: All, with a keyboard.
· Expected behavior: Tabbing cycles through the interactive elements within the terminal panel and does not leave the region. Escape exits Focus Mode.
· Failure condition: Tab focus leaves the terminal panel.

AB-F006: Arabic/RTL Toggle

· What to test: The EN/AR toggle.
· Where: Topbar.
· Device/Viewport: All.
· Expected behavior: The toggle is disabled, non-interactive, or hidden. It does not imply a working language switch.
· Failure condition: The toggle is active and produces a toast claiming the language was switched.

---

AEROBRIDGE — UNIFIED MASTER DESIGN AUDIT

END OF DOCUMENT