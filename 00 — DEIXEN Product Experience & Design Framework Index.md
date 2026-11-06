# DEIXEN — Product Experience & Design Framework
## Document Index and Working Rules

**Package version:** 0.3 — 7 November 2026  
**Purpose:** Keep product strategy, unified experience/runtime architecture, UX, product design language, brand identity, eventual UI specifications, and cross-project quality standards connected while preserving their separate responsibilities.

## The document set

1. **Master Strategic Product Direction, Learning Architecture & Partnership Goals**  
   The master strategic context: DEIXEN's ambition, users, learning model, professional work-task direction, customer journey, evidence principles, market questions, and institutional goals. The filename is retained as supplied; it is the strategic master brief, not implementation authorization.

2. **02 — DEIXEN UX Strategy & Experience Architecture**  
   Defines how learners move through the five areas and how task context, customer dialogue, support, practice, assessment, and evidence should be experienced.

3. **03 — DEIXEN Product Design Language**  
   Defines the visual and interactive language: hierarchy, composition, typography, spacing, components, states, motion, depth, and Dark/Light themes. It does not lock the visual identity.

4. **04 — DEIXEN Brand Strategy & Visual Identity**  
   Defines the brand strategy and visual exploration criteria. All final logo, wordmark, symbol, color, and identity decisions remain open unless separately confirmed.

5. **05 — UX Flows, UI Specifications & Design System — Planning**  
   The execution-oriented specification framework. Detailed screens and flows should be developed only after representative tasks and UX patterns are validated.

6. **06 — Unified Experience & Runtime Architecture**  
   The working architecture proposal connecting Home, Learning, Ghost, Terminal, Scenario Bank, Customer Interaction, Coach, the professional task lifecycle, Assessment, Evidence, and Growth. It is not canonical and does not authorize implementation.

7. **07 — Architecture Alignment & Change Log**  
   Explains the cross-document changes, documents intentionally left unchanged, remaining governance checks, and the limits of this package.

8. **08 — DEIXEN First Integrated Professional Task Map**  
   Applies the proposed architecture to one bounded new-booking task, stage by stage, including ownership, support, state transitions, evidence events, branches, assessment isolation, and validation criteria.

9. **09 — DEIXEN Case Package Definition — New Reservation**  
   The detailed CP-001 case definition and its current validation limits.

10. **10 — DEIXEN Practitioner Review Brief & Response Form**  
    A review brief and response form for an experienced reservations/ticketing practitioner. The external review remains pending until a practitioner responds.

11. **standards/ — DEIXEN Standards Library (proposed)**  
    A cross-project home for quality standards, status, evidence, and reusable review methods. The standards library does not replace canonical product decisions, the Amadeus Verified Reference, or file 08. See [`standards/README.md`](standards/README.md) and [`standards/DEIXEN_Product_Quality_Standards_Framework_v0.1.md`](standards/DEIXEN_Product_Quality_Standards_Framework_v0.1.md). This library is proposed and is not yet canonical.

12. **README**  
    Package contents, scope, and handling instructions.

## How the documents relate

The documents are separate by responsibility, not separate by vision.

- **Master strategy:** What are we building, for whom, and why?
- **Unified architecture:** Which capabilities own each responsibility, and how do they exchange context without conflicting?
- **UX strategy:** How should people understand and use the product to achieve the intended outcomes?
- **Product Design Language:** How should those experiences look, feel, and behave?
- **Brand Identity:** What distinctive character does DEIXEN express?
- **UX/UI Specifications:** What exactly should be designed, tested, and eventually built?
- **Standards Library:** What quality is expected in recurring areas of work, what evidence supports it, who owns it, and what its current status is?

A decision in one document may affect another. Update the affected companion documents and record the dependency. Do not duplicate large sections or silently change the scope of a canonical source.

## Status vocabulary

- **Approved principle:** explicitly accepted by the user.
- **Canonical decision:** recorded through the project's formal governance process; verify the current decision log.
- **Working architecture proposal:** a reasoned model for review; not a decision.
- **Current reference direction:** inspiration for qualities, not a design to copy.
- **Hypothesis:** plausible direction requiring research, prototyping, or testing.
- **Proposed standard:** candidate wording; not binding until approved.
- **Adopted for scope:** approved for a named body of work; do not generalize automatically.
- **Open:** no final decision has been made.
- **Deferred:** intentionally not decided or built yet.
- **Implementation status unknown:** do not claim it exists in the app without current repository evidence.

## Current integrated principle

Develop product logic, UX, UI/product design language, and brand identity as connected disciplines. Let real work tasks and learner needs shape the experience. Use the unified architecture and first-task map to preserve responsibility boundaries; use UX/UI prototypes to test how the learner experiences those boundaries. Do not treat visual design as decoration added after implementation.

This principle does not approve a final logo, palette, screen, feature, data schema, or implementation.

## Current area naming and governance note

The current canonical Product & Architecture source records the first area as **Home / الرئيسية** (D98) and retains five areas: Home, Learning, Terminal, Scenario Bank, and Growth. Older references to Flight Deck are historical unless they describe a legacy implementation identifier or historical decision. Before synchronizing governance files outside this package, confirm that D98 has been applied to the canonical decision log and decision-resolution register; this package does not edit those records.

D92 and D97 remain governing constraints in this proposal. No change to either decision is made here.

## Reference directions currently recorded

- **Microsoft:** composition, information organization, clarity, and hierarchy.
- **Samsung:** modernity, detail, layers, motion, and interactions.
- **Higgsfield:** visual presence, content/tool presentation, and distinctive accent-color strategy.

These references are not templates. Do not treat a reference's colors or layouts as automatically approved DEIXEN identity decisions. Follow the latest explicit owner direction for visual exploration; where that direction reopens earlier identity choices, use the current owner instruction rather than historical closed language in an older companion document.

## Suggested work sequence

1. Review the pending independent product-development report against current project sources and the work completed since the report author's last context.
2. Review the CP-001 practitioner response and separate practitioner evidence from Amadeus domain verification.
3. Reconcile findings with the current canonical decisions and Verified Reference.
4. Decide which proposed specialist standards need research, revision, practitioner input, learner validation, or formal adoption.
5. Validate representative end-to-end tasks and their customer/Terminal/Coach/evidence hand-offs.
6. Mature recurring UX/UI patterns and the shared design language.
7. Only then prepare implementation specifications and separately authorize code work.

## v0.3 case-validation and standards additions

- `09 — DEIXEN Case Package Definition — New Reservation.md` is the detailed CP-001 definition; its earlier verdict was `تنجح مع تعديل`, not production approval.
- `10 — DEIXEN Practitioner Review Brief & Response Form.md` is a review request template; practitioner feedback remains pending.
- The current live Verified Reference fetched from Knowledge `main` is third edition, V-01–V-18, with U-12/U-14 and other limitations still requiring care. Use the live file, not stale copies.
- CP-001 is architecture-valid with modifications, but not cleared for Amadeus content release or implementation.
- The proposed Standards Library creates a home and status register for quality standards. It does not approve new domain requirements, amend D95–D97, or authorize implementation.

## Governance boundary

The master strategy and canonical decision log remain authoritative for their scopes. Companion files and the proposed standards library must not silently amend `07`, the Operating Constitution, file `08`, the Amadeus Verified Reference, or canonical product architecture. Record disagreements and propose formal review instead of overwriting accepted governance.
