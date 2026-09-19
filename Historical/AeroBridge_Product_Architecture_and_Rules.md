# AeroBridge — Product Architecture & Rules

## 1. Document Purpose

This document defines the current approved product architecture baseline for AeroBridge.

It describes:
- The primary product structure.
- The relationship between core areas.
- The rules that preserve product direction.
- The platform architecture principles.
- The minimum implementation conventions needed to build against that architecture without guessing.

This document is a baseline reference.

It is not:
- A final UX audit.
- A replacement for independent reviews.
- A complete implementation roadmap.
- Authorization to introduce new product directions.

Any future change must be evaluated against evidence and approved decisions.

## Current Implementation Baseline Status

The exact current implementation baseline — target path, source-tree hash, archive hash, source basis, and verification results — is owned exclusively by `AeroBridge_Decisions_and_Current_State.md` (§ Current Arbitration State and the implementation-target Decision within it). It is intentionally not restated here.

This is a correction, not just a convention. An earlier version of this document restated the hash directly; the baseline was subsequently replaced a second time, `AeroBridge_Decisions_and_Current_State.md` was updated to reflect that, and this document was not — so it went on citing a baseline that the control document had already marked unavailable. A single canonical owner for this specific fact is what prevents that from happening again. Before beginning any implementation work, confirm the current baseline identity directly in `AeroBridge_Decisions_and_Current_State.md`; do not carry a cached hash forward from this document, a prior conversation, or a prior implementation session.

## 2. AeroBridge Product Architecture Overview

AeroBridge is structured around one connected professional training journey:

**Learning → Terminal / Practice → Scenario → Assessment → Evidence → Growth / Readiness**

The platform is not organized as isolated pages. Each area exists to move the user toward operational capability.

The five primary top-level areas are:
- Home / Flight Deck
- Learning / Curriculum
- Terminal / Practice
- Scenario Bank
- Growth / Readiness

No additional top-level product areas should be introduced without strategic review. This includes directions discussed but not yet architecturally placed, such as the Work Shift Simulator concept described in `AeroBridge_Master_Context.md`'s Future Vision section — it is not a sixth area, and it is not in scope until an explicit decision says otherwise.

## 3. Core Navigation Architecture

### 1. Home / Flight Deck

#### Purpose

The operational command center of AeroBridge.

It provides:
- User orientation.
- Current status.
- Next recommended actions.
- Connection between learning, practice, and readiness.

#### Role in the journey

Flight Deck answers:

> "What should I do next to become more capable?"

It is not:
- A marketing homepage.
- A simple dashboard.
- A progress-only screen.

### 2. Learning / Curriculum

#### Purpose

Learning provides the knowledge foundation required for operational performance.

It covers:
- Concepts.
- Procedures.
- Rules.
- Systems understanding.
- Preparation before execution.

#### Role in the journey

Learning answers:

> "What do I need to understand?"

Learning supports practice. It is not the final destination.

Completion of learning content does not equal operational readiness.

### 3. Terminal / Practice

#### Purpose

Terminal is the central simulation environment.

It represents realistic airline reservation and ticketing operations.

It enables users to:
- Apply knowledge.
- Execute workflows.
- Make operational decisions.
- Practice realistic tasks.

#### Strategic Rule

Terminal is the core value engine of AeroBridge.

Any design or architecture decision that reduces Terminal's importance must be critically reviewed.

#### Role in the journey

Terminal answers:

> "Can I perform the work correctly?"

### 4. Scenario Bank

#### Purpose

Scenario Bank provides realistic operational situations.

It allows users to practice:
- Different cases.
- Decision-making.
- Problem solving.
- Workflow variation.

#### Role in the journey

Scenario Bank answers:

> "Can I handle different real-world situations?"

Scenarios should connect to operational practice, not exist as disconnected exercises.

### 5. Growth / Readiness

#### Purpose

Growth / Readiness communicates development toward professional capability.

It focuses on:
- Capability improvement.
- Evidence of performance.
- Operational confidence.

#### Role in the journey

Growth answers:

> "How ready am I?"

It is not only:
- Points.
- Badges.
- Completion percentages.

Readiness should reflect demonstrated capability.

## 4. Relationship Between Areas

The intended relationship is:

**Learning → Terminal / Practice → Scenario → Assessment → Evidence → Growth / Readiness**

Supporting relationship:

**Flight Deck → All Areas**

Flight Deck connects the complete journey and guides the next action.

Learning provides the knowledge foundation. Terminal converts knowledge into operational performance. Scenario Bank introduces variation and judgment. Assessment and performance generate evidence. Growth / Readiness uses that evidence to communicate capability development and readiness.

Assessment is an internal state within the learning/practice journey, not a separate top-level product area.

## 5. Terminal Behavioral Skeleton (Implementation Convention)

**Status: Implementation Convention.** This section supplies the interaction-level state machine Terminal needs to be built without guessing. It defines states and transitions only — it does not define command syntax, response content, or any other domain-specific behavior, which remain governed by the frozen command boundary below and by the Domain/SME Validation dependency in `AeroBridge_Decisions_and_Current_State.md`. Nothing here may be used to imply that aviation/GDS semantics have been validated.

| State | Caused by | Data owner | What is displayed | After reload | Learner's next action |
|---|---|---|---|---|---|
| Awaiting input | Terminal opened, or previous cycle completed | Session state (not persisted) | An empty, neutral input — never response content, error text, or evaluative language. Nothing has happened yet, so nothing should look like it has. | Returns to awaiting input; command history behavior on reload is owned by the Assessment State Contract, not redefined here | Enter a command |
| Command submitted | Learner submits non-empty input | Session state | Transitions immediately to either Valid or Invalid below — no state where a command is silently substituted for another | — | Wait for response |
| Valid command recognized | Input matches the frozen command boundary's syntax | Terminal engine (domain content validation-gated) | A response — content is domain-gated and out of scope here | Recorded per the Assessment State Contract | Continue, request a hint, or move to the next step |
| Invalid or out-of-boundary input | Input is empty, malformed, or outside AN/SS/FQD/FXP | Terminal engine | A specific, honest message distinguishing "not recognized" from "not yet covered by this training slice" — never a silent substitution for a different valid command | Not treated as a successful command for evidence purposes | Correct the input or request a hint |
| Hint requested | Learner requests a hint | Single hint counter, incremented in exactly one place | The hint content | Hint count persists per the Assessment State Contract | Retry the command |
| Completion detected | Learning/Scenario/Assessment-owned completion criteria are met | Owning area (Learning, Scenario, or Assessment — not Terminal itself) | Confirmation, and the next recommended action | Reflected in Growth/Readiness per the Evidence & Readiness Contract | Proceed to the next step in the journey |
| Reset / retry | Explicit learner action | Session state | Clean awaiting-input state | N/A — explicit reset, not a reload | Begin again |

Binding rule: empty or unrecognized input must never be silently coerced into a different valid command for evidence or scoring purposes. If a default or fallback value is used for any internal convenience, it must not be recorded as if the learner had entered it.

## 6. Content Schemas (Implementation Convention)

**Status: Implementation Convention.** These define field shapes only, so Learning content and Manus's implementation share one structure instead of every screen hardcoding its own. They do not define curriculum content — the actual lesson bodies, examples, and operational claims remain subject to the Domain/SME Validation dependency wherever they touch aviation/GDS facts.

**Lesson**
- `id`
- `moduleId`
- `title`
- `objective` — one sentence: what the learner should be able to do after this lesson
- `body` — explanation content
- `example` — a worked example
- `practiceBridge` — an explicit reference to the Terminal task this lesson prepares the learner for; a lesson without one is incomplete, not optional
- `prerequisiteLessonIds` — may be empty
- `completionRule` — what marks the lesson complete (viewed, practiced, or another rule); the field must exist even before content design finalizes its value

**Module**
- `id`
- `title`
- `lessons` — an ordered list of Lesson ids

This is deliberately minimal. It is sized to support one real end-to-end learning path, per the Vertical Slice rule below — not a full curriculum content system, which remains explicitly deferred.

## 7. Persistence Architecture (Implementation Convention)

**Status: Implementation Convention.** AeroBridge is approved as frontend-first with localStorage persistence, and three governing contracts in `AeroBridge_Decisions_and_Current_State.md` — Evidence & Readiness, Assessment State, and Scenario Differentiation — depend on that persistence behaving predictably. None of the current documents defined how, beyond one incidental reference to an existing `aerobridge-progress-records` key in the Evidence & Readiness Contract. This section closes that gap at the minimum level the current contracts require.

- **What is persisted:** only Recorded and Calculated evidence, per the evidence classes defined in the Evidence & Readiness Contract. Illustrative and static content is never written to localStorage — it lives in application content, not learner state, because persisting it would blur exactly the line that contract exists to protect.
- **Schema versioning:** the persisted record includes a schema version field. On a version mismatch, the safe default is to reset the local record rather than attempt a silent migration. This is a deliberate simplicity choice: migration logic adds real complexity for a frontend-only prototype whose persisted data is training progress, not irreplaceable user content, and a mismatch is expected to be rare during active development. Revisit only if real evidence shows learners losing meaningful progress across schema changes — do not build migration machinery pre-emptively.
- **Reset mechanism:** a reset action must exist that clears all persisted evidence records and returns the learner to a clean training state. This is a product requirement, not a developer convenience — a training environment that cannot be honestly reset cannot be honestly used for repeated practice, and the Vertical Slice validation itself depends on being able to produce a clean state.
- **Session model:** a session is the browser plus its localStorage. There is no login, no account, and no cross-device sync at this stage, consistent with the approved no-backend-unless-proven-necessary direction. If cross-device continuity becomes a real requirement, that is a backend decision requiring the same evidence-based justification any architecture change requires under Change Control below — it is not authorized by this section.

## 8. Vertical Slice Before Scale Rule

Before expanding AeroBridge across large numbers of lessons, command families, scenarios, competencies, or readiness signals, the product must validate at least one **complete end-to-end vertical slice** using real, internally consistent content and evidence.

The vertical slice should demonstrate the complete intended learning-to-readiness chain:

**Learning → Terminal / Practice → Scenario → Assessment → Evidence → Growth / Readiness**

The slice must use:
- Real content rather than placeholder labels.
- Real practice behavior rather than representational UI only.
- Meaningfully differentiated scenario behavior where scenario differentiation is claimed.
- Real assessment logic within the supported scope.
- Traceable evidence generated from actual learner actions.
- Growth / Readiness outputs derived from owned evidence rather than static or invented values.

The purpose of this rule is to validate the product architecture, content model, behavioral contracts, evidence model, and UX continuity before scaling the same pattern across the broader curriculum.

A successful vertical slice does not require the entire future product to be implemented first. It is proof that the chosen structure can scale safely.

Do not author or implement large volumes of Phase 3 content until the vertical slice has demonstrated that the underlying pattern is coherent, useful, measurable, and technically supportable.

This document is the canonical owner of this rule. `AeroBridge_AI_Working_Rules.md` references it rather than restating it, so the two copies cannot drift out of sync the way an earlier version of the corpus did.

The current frozen boundary for this slice — the specific workflow family, command set, scenario count, and Coach touchpoints — is a Decision, not an architecture principle, and is owned by `AeroBridge_Decisions_and_Current_State.md`.

## 9. Non-Negotiable Product Rules

### Rule 1 — Terminal Centrality

Terminal remains the operational heart of AeroBridge.

Do not reposition AeroBridge as:
- A content-first platform.
- A generic learning management system.
- A quiz-based education product.

### Rule 2 — Professional Positioning

AeroBridge must maintain the identity of:

**Professional aviation operations training.**

Avoid:
- Classroom-style experience.
- Child-oriented gamification.
- Generic education patterns.

### Rule 3 — Realistic Workflow

Experience decisions should prioritize:

**Operational realism over visual trends.**

The platform should feel connected to real airline operations environments.

### Rule 4 — Evidence-Based Progress

Progress should represent:
- Capability.
- Performance.
- Improvement.

Not only:
- Time spent.
- Lessons completed.

## 10. Platform Architecture Direction

### Responsive Web Application First

The approved direction:

**Responsive Web Application → Mobile-first architecture → PWA-ready foundation → PWA capabilities when justified**

## 11. Mobile-First Principle

Mobile is a primary experience consideration.

Requirements:
- Interfaces must adapt naturally to mobile.
- Core workflows should remain usable on smaller screens.
- Mobile experience should feel intentional, not compressed.
- Mobile-first does not mean ignoring desktop.

## 12. Desktop Workstation Principle

Desktop remains important because AeroBridge represents professional operational work.

Desktop should support:
- Focused workflows.
- Complex tasks.
- Simulation environments.
- Professional workspace experience.

The concrete breakpoints and validation requirements for desktop and tablet, alongside the existing mobile set, are defined in `AeroBridge_Design_System_and_UX_Principles.md`.

## 13. PWA Readiness Principle

AeroBridge should be architected so PWA capabilities can be introduced when valuable.

The current priority is:

**High-quality responsive web application.**

Not:
- PWA-first development.

Potential future capabilities:
- Install experience.
- Offline strategies where appropriate.
- Performance improvements.

These should be activated based on real product needs.

## 14. Change Control

Any proposed architecture change must answer:
- What problem does this solve?
- Why is the current architecture insufficient?
- What evidence supports the change?
- What impact does it have on the product strategy?

No structural changes should be made based only on:
- Trends.
- Personal preference.
- Visual appeal.
- Implementation convenience.

## Document Status

Current status:

**Approved Architecture Baseline**, extended with implementation conventions (Sections 5–7) that fill gaps identified in the 2026-08-24 Foundation Audit. The conventions do not change product scope or reopen any closed decision; they specify mechanics for directions already approved elsewhere in this document set.

Future changes require review and explicit approval.
