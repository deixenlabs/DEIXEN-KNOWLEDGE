---
name: DEIXEN Canonical Design System & UX Principles
owns: Visual/UX principles, accessibility baseline, anti-patterns, historical token evidence
supersedes reading in isolation: AeroBridge_Design_System_and_UX_Principles.md, DESIGN_SYSTEM_UI_BLUEPRINT.md
---

> **Synchronization note — Phase 2, 2026-09-24.** Working name: **DEIXEN**
> (provisional; see `DEIXEN_Operating_Constitution.md` §1). "AeroBridge" survives
> only inside historical filenames and provenance statements. Owner: **Karim** —
> earlier project records used the name "Malik" for the same person; those
> references now read "Karim". Current project state and every decision:
> `07_DEIXEN_Canonical_Decisions_and_Current_State.md`. Amadeus facts: only
> claims marked VERIFIED under 07 Decision 12 may be taught as fact.


# DEIXEN — Canonical Design System & UX Principles

## Design Positioning vs. Design Execution — read this before anything else in this file

These are two different decisions, deliberately kept separate:

**Design Positioning — CLOSED.** DEIXEN should read as professional,
operational, serious aviation-operations software. It should not drift
toward a consumer app, classroom product, generic LMS, entertainment
dashboard, or similar positioning. This is a foundational product/design
decision, it is not being reopened by this consolidation, and nothing below
should be read as unsettling it — this is the same commitment already stated
as Non-Negotiable Product Rule #2 in
`03_DEIXEN_Canonical_Product_and_Architecture.md`.

> **Update 2026-09-25 (07 Decision 31).** Karim chose direction A "Margin"
> in Phase 4: light-led, with tokens structured so a dark theme can be added
> later.
>
> **Update 2026-09-26 (07 Decision 42) — Design Execution CLOSED for the
> slice.** Karim approved the refined direction A at the Phase 4 gate: the
> Claude Design canvas (version and boards in 07 D42 and Build Spec §2), the
> typefaces (IBM Plex Mono; Public Sans + IBM Plex Sans Arabic; Literata +
> Noto Naskh Arabic), header lockup B, and `tokens.css` as the one token file
> in the code repository. Exact values now live only in that file — this
> document keeps principles, accessibility, breakpoints and anti-patterns,
> which the approved design must still meet. The name and identity stay
> provisional (Constitution §1); a dark theme is not designed. The rest of
> this section is the pre-choice framing, kept for context.

**Design Execution — OPEN (pre-choice framing; closed for the slice by 07 D42).** Exact colors and token values, typography/font
choices, logo/wordmark, visual identity, composition and layout language,
imagery, visual effects, detailed visual hierarchy, and overall visual
expression are all genuinely reopened for the next dedicated design phase.
This is what the rest of this document actually describes: NEW's abstract
principles below (what colors/typography/motion should *mean and do*) and
OLD's real, previously-built tokens further below are both **inputs to that
open exploration**, not settled outcomes.

**Explicit non-interpretation:** none of this should be read as approving
the earlier dark-navy/blue execution, nor as rejecting it. It is preserved
purely as historical evidence and design input, with equal standing to any
fresh direction the next design phase considers.

*For context, not as something to resolve here:* NEW's own internal
"Pre-Phase 3 Design Arbitration Outcome" concluded that its five-area
architecture, Terminal centrality, and overall visual direction should be
preserved rather than reopened. The architecture/Terminal-centrality part of
that conclusion is unrelated to design and remains correctly closed per
`03_DEIXEN_Canonical_Product_and_Architecture.md`. The visual-direction
part of that same conclusion is the part superseded by the Design Execution
reopening above — not because the arbitration was wrong, but because a newer,
more specific instruction says this question gets a fresh look.

## Design Identity (principle level — durable regardless of final visual outcome)

DEIXEN should feel professional, precise, intelligent, calm under
pressure, operational, trustworthy, modern, and global — closer to flight
operations interfaces, professional control systems, and advanced simulation
software than to entertainment dashboards, consumer apps, or generic SaaS
templates. The experience should communicate: *"Training for real operational
responsibility."*

**Color language — historical input, not binding.** The paragraph below is
the earlier generation's color language, written around the dark-navy/blue
execution. Exact palette: the approved `tokens.css` (07 D42); light-led direction
(07 D31); what stays durable is the principle that color carries meaning
(focus, primary action, relationships, success, warning) rather than
decoration. Earlier wording: deep navy/dark backgrounds for
focus and reduced visual noise; a confident accent color (electric
blue/periwinkle in NEW's language) for active states and primary actions;
cyan-family tones for connections/routes/data relationships; a mint/green
family for success and valid outcomes; amber for warnings and attention
states. Exact numeric values belong to whichever token file the eventual
implementation actually reads — a principles document and a token file that
both claim to be authoritative will drift apart, so only one may be.

**Typography:** communicates precision, confidence, professionalism; strong
hierarchy distinguishing headings/actions/data/status; excellent readability
on desktop and mobile; never playful or decorative; a functional tool, not
only visual styling.

**Clarity over decoration:** every visual element needs a purpose. Avoid
decorative elements without function, excessive animation, or complexity that
reduces usability. Terminal specifically must never look like a game, a quiz
interface, or a simple exercise screen — design decisions must protect its
importance.

## Historical implementation evidence (OLD) — preserved, not pre-approved

The earlier implementation actually built the following exact tokens (dark
theme), with project documentation recording Karim's approval of them on a
real screen:

| Token | Value |
|---|---|
| `--color-bg` | `#0B0E1A` |
| `--color-surface` | `#121627` |
| `--color-surface-2` | `#1A2035` |
| `--color-border` / `--color-border-2` | `#23293E` / `#2E3856` |
| `--color-text` / `-2` / `-3` | `#DFE6F5` / `#8290AA` / `#44526A` |
| `--color-accent` | `#4F7BF5` (chosen over an original amber-primary plan after a direct side-by-side comparison) |
| `--color-success` | `#3BAA84` |
| `--color-amber` | `#C49040` (demoted to a minor highlight, not primary) |

A parallel light-theme token set also exists in the actual repository CSS
(`--color-bg: #F4F6FB`, `--color-accent: #3A63D8`, etc.) that was never
tabulated in the original design document. Terminal-specific tokens
(`--term-bg: #050A12`, `--term-command: #4EA1F3`, etc.) were defined but not
yet build-verified at the time they were written. Typography: Plus Jakarta
Sans (Latin), Cairo (Arabic, re-confirmed over an earlier Manrope/Alexandria
plan after seeing it live), JetBrains Mono for the terminal. Spacing scale
4/8/12/16/24/32/48px; card radius 8px, button/input radius 6px; linear icons
at 1.5px stroke, deliberately almost absent inside the terminal itself for
realism.

These values are real and tested, with documented historical Karim approval
— and are presented here purely as evidence for the next design phase, per
the
governing instruction in the box above.

## Accessibility Baseline (current, formal — an improvement over prior looser language)

- **Contrast:** WCAG 2.1 AA — 4.5:1 for normal text, 3:1 for large text/UI
  components. This is a floor: if the approved color language conflicts with
  it in a specific instance, adjust that instance's shade, not the palette.
- **Keyboard & focus:** every interactive element reachable and operable by
  keyboard with a visible focus state, including Terminal's command input and
  any tab-like segmented control.
- **Semantic structure:** segmented controls (mode switches, filters) use
  real ARIA roles/states (`role="tab"`, `aria-selected`), not styling alone.
- **Touch targets:** primary actions ≥44×44px; secondary/dense controls may
  use the WCAG 2.2 AA minimum of 24×24px where density genuinely requires it.
- **Reduced motion:** motion must explain change, confirm actions, or improve
  understanding — never decorative — and must respect the platform's
  reduced-motion preference where exposed.

## Responsive Density & Breakpoints

Professional, balanced visual density across sizes — cards must not be
enlarged merely to fill space or shrunk merely to fit more content. On
mobile, the goal is organized compactness: minimal dead space, no excessive
vertical stacking, no oversized or overcompressed controls, and Terminal's
required workspace must never be sacrificed for density elsewhere. Validate
at minimum: **320 / 360 / 390 / 430px** (mobile) and **768 / 1024 /
1280–1440px** (tablet/desktop) — desktop is not "mobile stretched wide";
Terminal and dense surfaces like Growth/Readiness should use the extra width
for genuine workspace density (side-by-side panels, richer simultaneous
context).

## Design Anti-Pattern List (canonical, complete)

Avoid: generic SaaS dashboard templates; classroom/children's-app aesthetics;
over-gamification; content-library visual language; excessive or purposeless
cards/card-grids; excessive pill-based UI; repetitive hero sections; fake
KPIs or meaningless decorative charts; decorative glassmorphism without
functional need; consumer or travel-app aesthetics; visual complexity for its
own sake; template-based, visibly AI-generated design patterns.

## Visual Vitality

DEIXEN should feel professional without feeling sterile. Selective,
high-quality imagery may add atmosphere or human presence where it supports
the product narrative — a strong hero image or scenario visual can give a
screen identity while the surrounding UI stays structured and restrained.
Never become a photo gallery, travel-style site, or stock-image collection.
Visual references (whenever design work resumes) are inspiration for
composition, rhythm, and atmosphere only — never to be copied literally or
allowed to redefine DEIXEN's identity.

## Localization / RTL — status CLOSED (07 Decision 11)

DEIXEN supports Arabic + English with RTL + LTR — a closed product decision
(07 Decision 11). How it is built (string handling, per-component RTL
behavior, libraries) is an ordinary implementation choice. Historical
evidence: the earlier implementation shipped a working Arabic-default, RTL,
dark-default interface with a live language/theme toggle, confirmed at the
time in its code and approved by Karim; it is proof of feasibility, not a
template to copy.

## Design Evaluation Framework (for whatever comes next)

Brand Alignment (does it feel like professional aviation operations
software?) · Product Alignment (does it support the mission?) · Operational
Realism (does it resemble real workflows?) · User Clarity (do people
understand what's happening and what to do next?) · Terminal Support (does it
strengthen the simulation?) · Professional Readiness (does it move users
closer to job confidence?)
