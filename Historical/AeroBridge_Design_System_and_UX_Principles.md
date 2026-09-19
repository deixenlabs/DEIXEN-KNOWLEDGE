# AeroBridge — Design System & UX Principles

## Document Purpose

This document defines the visual and UX principles that guide AeroBridge product design.

It establishes:
- The visual identity direction.
- The interface language.
- UX principles.
- Evaluation criteria for future designs.
- The complete anti-pattern list AeroBridge design must avoid — this document is the canonical owner of that list; other documents in this set reference it rather than restating it.

This document defines how AeroBridge should look, feel, and behave.

It is not:
- A page-by-page UI specification.
- A replacement for UX audits.
- A final implementation document.
- A collection of design trends.

All future design decisions must align with these principles.

## Design Identity

### Core Design Character

AeroBridge should feel:
- Professional.
- Precise.
- Intelligent.
- Calm under pressure.
- Operational.
- Trustworthy.
- Modern.
- Global.

The user should feel they are entering a professional aviation operations environment.

The experience should communicate:

> "Training for real operational responsibility."

### Positioning Rule

AeroBridge is not a traditional education platform.

The design must support the identity of:

**Aviation operations training platform.**

The complete list of visual languages and patterns to avoid is maintained in the Design Anti-Patterns section below, rather than restated in multiple places across this document.

## Visual Direction

### Dark Operational Interface

The primary visual direction is:

**A premium dark operational environment.**

The experience should resemble:
- Flight operations interfaces.
- Professional control systems.
- Mission environments.
- Advanced simulation software.

Not:
- Entertainment dashboards.
- Consumer apps.
- Generic SaaS templates.

### Color Language

The color system should communicate operational states.

#### Foundation

**Deep Navy / Dark Backgrounds**

Purpose:
- Create focus.
- Establish aviation professionalism.
- Reduce visual noise.

#### Functional Colors

**Electric Blue / Periwinkle**

Used for:
- Active states.
- Primary actions.
- Important navigation elements.

Meaning:
- Intelligence.
- Technology.
- Focus.

**Cyan**

Used for:
- Operational connections.
- Routes.
- Data relationships.
- System indicators.

Meaning:
- Flow.
- Connectivity.
- Information.

**Mint / Green**

Used for:
- Success states.
- Completed actions.
- Valid outcomes.

Meaning:
- Confidence.
- Confirmation.

**Amber**

Used for:
- Warnings.
- Attention states.
- Important notices.

Meaning:
- Awareness.
- Caution.

### Design Token Ownership

This document defines what each color and typographic choice *means*; it deliberately does not specify exact numeric values (hex codes, spacing scale, type scale, radii). Those are owned by the implementation's token file. A principles document and a token file that both claim to be the authoritative source for exact values will drift apart over time — one of them has to be canonical, and it should be the one the browser actually reads.

If an implementation review ever finds two parallel token systems in use at once (for example, a legacy set alongside a newer, differently-prefixed set covering only part of the interface), that is a defect to consolidate under the Targeted Hardening Gates below — it is not a reason to add a second token specification to this document.

## Interface Visual Principles

### Clarity Over Decoration

Every visual element should have a purpose.

Avoid:
- Decorative elements without function.
- Excessive animations.
- Visual complexity that reduces usability.

### Information Hierarchy

The interface should clearly communicate:
- What is happening?
- What is important?
- What action should happen next?

### Operational Density

AeroBridge should support professional workflows.

Information density should be:
- Rich enough for operational realism.
- Organized enough to avoid cognitive overload.

## Typography Principles

Typography should communicate:
- Precision.
- Confidence.
- Professionalism.

Requirements:
- Strong hierarchy.
- Clear distinction between headings, actions, data, and status.
- Excellent readability across desktop and mobile.

Avoid:
- Playful fonts.
- Decorative typography.
- Weak hierarchy.

Typography is a functional tool, not only visual styling.

## UX Principles

### Operational Realism

Every experience should feel connected to real aviation workflows.

Ask:

> "Would this make sense in a professional operational environment?"

### Action-Oriented Experience

The interface should guide the user toward meaningful action.

Avoid passive consumption.

The product should encourage:

**Learn → Practice → Decide → Execute → Improve**

### Reduce Cognitive Load

Complex aviation workflows should be presented clearly.

The interface should help users understand:
- Current state.
- Available options.
- Consequences of actions.

### Evidence-Based Progress

Progress should represent demonstrated ability.

Avoid relying only on:
- Completed lessons.
- Time spent.
- Simple points.

### Continuity

The user journey should feel connected.

Learning, practice, scenarios, and readiness should not feel like separate products.

### Professional Confidence

The design should help users develop confidence through realistic practice.

The goal is not only engagement.

The goal is capability.

## Terminal Design Principle

Terminal is the core operational experience.

Design decisions must protect its importance.

The simulator should feel:
- Realistic.
- Focused.
- Professional.
- Purpose-built.

Avoid making it look like:
- A game.
- A quiz interface.
- A simple exercise screen.

## Mobile and Desktop UX Principles

### Mobile Experience

Mobile is a primary design consideration.

Requirements:
- Intentional mobile layouts.
- Touch-friendly interactions.
- Clear prioritization.
- No simple shrinking of desktop screens.

### Desktop Experience

Desktop supports professional operational workflows.

Requirements:
- Efficient workspace.
- Rich information presentation.
- Complex task handling.
- Simulation-friendly layouts.

## Animation and Interaction Principles

Animations should:
- Explain change.
- Confirm actions.
- Improve understanding.

Avoid:
- Decorative motion.
- Distracting effects.
- Animations that slow workflows.

Motion should feel operational, not entertainment-focused, and must respect the user's reduced-motion preference where the platform exposes one — this is a direct extension of the same principle, not a separate accessibility carve-out.

## Accessibility Baseline

No prior version of this document set a concrete accessibility bar. This section sets one at the level appropriate for a professional operational tool: a baseline, not a maximalist overhaul, consistent with this document's existing emphasis on operational density over decoration.

- **Contrast:** body text and primary actions must meet WCAG 2.1 AA — 4.5:1 for normal text, 3:1 for large text and UI components — against their background. This is a floor, not grounds to lighten the dark operational palette; where the approved color language and this floor conflict in a specific implementation, the fix is adjusting that instance's shade within the approved palette, not the palette itself.
- **Keyboard and focus:** every interactive element must be reachable and operable by keyboard, with a visible focus state. This includes Terminal's command input and any tab-like segmented control (mode switches, filters).
- **Semantic structure:** tab-like segmented controls must use appropriate ARIA roles and states (for example, `role="tab"` and `aria-selected`) rather than relying on visual styling alone to convey which option is active.
- **Touch targets:** primary actions should target at least 44×44px, consistent with common platform convention for a professional tool people will use repeatedly. Secondary or dense controls may use the WCAG 2.2 AA minimum of 24×24px where the approved Operational Density principle genuinely requires tighter spacing — density and accessibility are not automatically in conflict, and this document's existing density principle already asks for exactly this kind of judgment call.
- **Reduced motion:** see Animation and Interaction Principles above.

Whether AeroBridge requires Arabic-language and right-to-left layout support is not decided by this document, or by any document in this set — see the open question recorded in `AeroBridge_Decisions_and_Current_State.md`. No RTL-specific requirement is stated here because there is currently no evidence either way that it belongs in scope.

## Design Evaluation Framework

Any future design should be evaluated using these questions:

### Brand Alignment
Does it feel like professional aviation operations software?

### Product Alignment
Does it support AeroBridge's mission?

### Operational Realism
Does it resemble real workflows?

### User Clarity
Can users understand what is happening and what to do next?

### Terminal Support
Does it strengthen the simulation experience?

### Professional Readiness
Does it move users closer to job confidence?

## Design Anti-Patterns

This is the complete, canonical list. `AeroBridge_Master_Context.md` and `AeroBridge_Decisions_and_Current_State.md` reference this section rather than maintaining their own copies.

Avoid:
- Generic SaaS dashboard templates.
- Classroom software and children's learning-application aesthetics.
- Gamified education platforms and over-gamification generally.
- Content-library visual language.
- Excessive cards without purpose, or card-grid repetition without purpose.
- Excessive pill-based UI.
- Repetitive hero sections.
- Fake KPIs or meaningless decorative charts.
- Decorative glassmorphism without functional need.
- Consumer or travel-app aesthetics.
- Visual complexity for its own sake, without operational value.
- Template-based, visibly AI-generated design patterns.

## Pre-Phase 3 Design Arbitration Outcome

**Status: Approved — Preserve + Targeted Harden**

The independent Claude and Manus reviews do not justify reopening AeroBridge's approved visual direction, five-area architecture, Terminal centrality, or overall interaction identity. Design work before Phase 3 implementation should therefore be limited to evidence-backed hardening on the verified implementation target.

### Current verified implementation baseline

The exact current implementation baseline is owned exclusively by `AeroBridge_Decisions_and_Current_State.md` and is not restated here, for the same reason given in `AeroBridge_Product_Architecture_and_Rules.md`: this document previously restated a specific hash directly, the baseline was replaced again, and this document was not updated — so it continued pointing at a target the control document had already marked unavailable. Confirm the current baseline directly in `AeroBridge_Decisions_and_Current_State.md` before treating any archived finding as current. Archived-candidate findings remain snapshot evidence until reverified on the current target.

### Preserve
- Dark operational Flight Deck identity.
- Terminal-first workspace and visual hierarchy.
- Operational state semantics and typography system.
- Professional vitality and purposeful imagery.
- Responsive Web App / mobile-first direction.

### Targeted hardening gates
- Verify current-target evidence before treating archived visual/runtime findings as current defects.
- Validate density and vertical stacking in Growth / Readiness and related metric-heavy surfaces.
- Validate Terminal input visibility and usable workspace at 320 / 360 / 390 / 430px, including native-keyboard conditions.
- Validate touch targets, focus behavior, accessibility semantics, and contrast on the verified target against the Accessibility Baseline above.
- Remove or truthfully label any control whose behavior is not implemented.
- Do not add decorative KPI geometry unless its visual treatment reinforces a clear learning, operational, assessment, or readiness purpose.

These are hardening and validation requirements, not authorization for redesign.

## Design North Star

Every design decision should reinforce:

**AeroBridge is where aviation knowledge becomes operational capability.**

The interface should make users feel:

> "I am training for the real environment, not studying a course."

## Responsive Density, Proportion & Breakpoint Rule

AeroBridge interfaces must maintain a professional, balanced visual density across different screen sizes. Cards and UI elements must not be enlarged merely to fill available space, nor reduced simply to fit more content. Padding, gaps, element heights, column counts, and section arrangements should adapt to the viewport width, the role of the element, and the importance of the content, while preserving readability and touch usability.

On mobile, the goal is **organized compactness**: clear content that can be scanned quickly, with deliberate and proportional breathing room. Unnecessary dead space and excessive vertical stacking should be minimized. The interface must not become a long sequence of oversized rectangles, nor a crowded layout of elements that are too small or compressed to remain clear and usable.

These principles must be validated across at least **320 / 360 / 390 / 430px** viewport widths at the mobile end. Appropriate dimensions and density should be determined by the role, content, and context of each element — not by the breakpoint alone.

The mobile set above was the only one explicitly defined in prior versions of this document, which left a real gap given that `AeroBridge_Product_Architecture_and_Rules.md` names Desktop Workstation as a first-class experience. The same density discipline now extends explicitly to **768px (tablet portrait), 1024px (tablet landscape / small desktop), and 1280–1440px (desktop workstation)**. Desktop is not "mobile stretched wide": validate that Terminal and dense operational surfaces such as Growth/Readiness use the additional width for genuine workspace density — side-by-side panels, richer simultaneous context — rather than simply enlarging mobile-proportioned cards.

The Terminal must not be reduced as a solution to density or page-length issues at any breakpoint. It must retain the workspace required for its role as a practical operational environment.

This principle should remain a standalone Knowledge Rule because it defines a clear, enforceable, and testable responsive design standard.

Terminal-specific constraints, as well as requirements related to dead-space reduction, long-scroll loss, and KPI clipping, should remain documented in `AeroBridge_Decisions_and_Current_State.md` as implementation requirements and current-state decisions. The design audit treats these areas as validation requirements rather than purely visual preferences.

## Visual Vitality & Purposeful Imagery

AeroBridge should feel professional and operational without feeling visually sterile or lifeless. High-quality imagery, environmental visuals, and carefully selected visual moments may be used where they add atmosphere, context, human presence, or emotional depth to the experience.

Imagery should support the product narrative rather than merely decorate the interface. It must feel intentional, cohesive, premium, and relevant to the user's context.

Use visual richness selectively: a strong hero image, environmental backdrop, scenario imagery, or contextual visual can give a screen life and identity, while the surrounding UI remains structured, restrained, and highly readable.

Avoid turning AeroBridge into a photo gallery, travel-style website, stock-image collection, or image-heavy marketing interface. The product must remain a professional operational training environment first.

The goal is **professional vitality**: a balance between structured software UI and carefully selected visual storytelling. The interface should feel alive, human, and deliberately authored by a skilled product designer — not sterile, generic, or visibly AI-generated.

Visual references are inspiration for composition, rhythm, atmosphere, and visual storytelling only. They must never be copied literally or allowed to redefine AeroBridge's product identity.
