---
name: DEIXEN Canonical Product & Architecture
owns: Product identity, vision, personas, information architecture, platform direction
supersedes reading in isolation: AeroBridge_Master_Context.md, AeroBridge_Product_Architecture_and_Rules.md, PROJECT-20.md, PRODUCT_STRATEGY_UX_ARCHITECTURE-1.md
---

> **Synchronization note — Phase 2, 2026-09-24.** Working name: **DEIXEN**
> (provisional; see `DEIXEN_Operating_Constitution.md` §1). "AeroBridge" survives
> only inside historical filenames and provenance statements. Owner: **Karim** —
> earlier project records used the name "Malik" for the same person; those
> references now read "Karim". Current project state and every decision:
> `07_DEIXEN_Canonical_Decisions_and_Current_State.md`. Amadeus facts: only
> claims marked VERIFIED under 07 Decision 12 may be taught as fact.


# DEIXEN — Canonical Product & Architecture

## Product Identity

DEIXEN is a professional aviation operations training platform. It moves
learners from theoretical knowledge to confident, measurable, job-ready
performance in airline reservation and ticketing workflows through a realistic
operational simulation. It is explicitly **not** a travel app, an airline
booking product, a generic LMS, a classroom replacement, or a video/quiz
collection.

**Core transformation** (the organizing chain referenced by every other
canonical document — this is its one authoritative statement):

> Learning → Terminal/Practice → Scenario → Assessment → Evidence →
> Growth/Readiness

**Terminal is the operational heart of the product.** Any decision that
reduces it to a secondary or optional feature must be critically reviewed
before proceeding.

## Who this is actually for

The first real learners and validation users are Karim and his brother — a
deliberate **validation strategy**, not a permanent restriction on the
product's eventual audience. The immediate real-world training target is
Saudi/Gulf aviation reservation and ticketing work (named historical context:
Almosafer/Seera, Flynas, Flyadeal, Saudia GSAs — high-pressure call-center
environments) because that's the market the project is being built first to
prepare for — this is the **current primary training context**, not an
irreversible commercial positioning decision. The named employers remain
useful, concrete context for grounding realism; they are not a permanent
strategic commitment unless explicitly decided as one. Success in this
current phase is not lesson completion or visual polish — it is whether the
owner/primary learner enters a real interview with genuine practical
familiarity and a credible chance of performing.

**Job-readiness levels, recovered from earlier planning (this is
specification detail, not a redesign):** the technical progression's L1–L9
levels were explicitly mapped to reference job levels, each with concrete
associated skills —

| Reference job level | Roadmap levels | Skills covered |
|---|---|---|
| Junior Reservation Agent | L1–L3 | Basic PNR creation, availability inquiry, indicative pricing |
| Call Center Agent | L4–L6 | Actual pricing, ancillary services, professional customer communication |
| Ticketing & Operations Specialist | L7–L9 | Queues, seating, crisis scenarios, and specialized Saudi-market content |

*(Historical mapping from earlier planning; to be re-aligned to sourced market
requirements during curriculum authoring — 07 Decision 18.)* This is
explicitly **a guidance framework, not an official certificate or an
employment promise** — that qualifier is load-bearing and should travel with
the table anywhere it's used, not just live here. It is the concrete
mechanism that makes "job readiness" a checkable claim rather than an
aspiration, and it should inform the future curriculum/Skill Graph work
rather than being reinvented from scratch.

This personal-first, Saudi/Gulf-first framing coexists with, and does not
contradict, a broader long-term product category: adults preparing for
aviation operations careers generally, and organizations needing realistic
workforce preparation. Read the current framing as this stage's validation
strategy, not the product's ceiling.

**Naming:** "DEIXEN" is the current working name (provisional — see
`DEIXEN_Operating_Constitution.md` §1); the earlier working name was
"AeroBridge". Neither is a final product name. Logo, wordmark, and brand
identity remain open alongside Design Execution (see
`04_DEIXEN_Canonical_Design_System.md`) — historical branding is context,
not a locked-in decision.

## Information Architecture — Five Areas (current, approved)

1. **Home / Flight Deck** — operational command center; orientation, current
   status, next recommended action. Answers: *"What should I do next to
   become more capable?"* Not a marketing homepage or a progress-only screen.
2. **Learning / Curriculum** — the knowledge foundation. Answers: *"What do I
   need to understand?"* Supports practice; completing it is not readiness.
3. **Terminal / Practice** — the core simulation environment; the value
   engine of the whole product. Answers: *"Can I perform the work correctly?"*
4. **Scenario Bank** — realistic operational cases that train judgment and
   expose workflow variation. Answers: *"Can I handle different real-world
   situations?"* Scenarios must connect to operational practice, not stand
   alone.
5. **Growth / Readiness** — communicates capability development through
   evidence, not points or completion percentages. Answers: *"How ready am
   I?"*

No sixth top-level area may be added without explicit strategic review — this
includes the "Work Shift Simulator" concept (a possible future evolution
combining realistic task flow, priorities, interruptions, and time pressure
into one continuous session). It is real, discussed, preserved thinking, but
it is **not scoped**: whether it would extend Terminal/Practice, extend
Scenario Bank, or need its own review is an open question, and no
implementation work on it is authorized until that question is answered.

**Historical mapping, for continuity:** the product's earlier 3-domain model
(Progression / Practice / Growth Record) maps onto the current 5 areas as
follows — Progression's content splits across Learning/Curriculum and part of
Home/Flight Deck; Practice maps directly onto Terminal/Practice; Growth
Record maps directly onto Growth/Readiness; Scenario Bank is new — the
earlier model folded scenario content into Practice rather than separating
it. The earlier model's actually-built Progression screen (real visual work
with documented historical Karim approval — see
`04_DEIXEN_Canonical_Design_System.md`) is legitimate prior work toward
this structure, not orphaned effort.

Assessment is an internal state within the Learning/Practice journey, not a
separate top-level area — consistent with the earlier model's own "one
practice environment, different modes (Learn/Practice/Assessment)" design.

## Relationship between areas

Flight Deck connects to all areas and guides the next action. Learning
provides the knowledge foundation; Terminal converts it into operational
performance; Scenario Bank introduces variation and judgment; Assessment and
performance generate evidence; Growth/Readiness communicates what that
evidence supports.

## Platform Direction

**Confirmed direction:** the current stage is not optimized around
PWA-first, offline-first, backend-first, accounts, sync, or commercial
infrastructure. The near-term objective is an excellent learning product
that genuinely teaches correctly and can prove its value through real use —
not infrastructure built ahead of evidence it's needed.

**Explicitly not a rejection:** backend, accounts, synchronization, PWA
capabilities, and broader commercial infrastructure remain real future
possibilities, to be introduced later based on evidence and sound technical
judgment once the product proves valuable. Where preserving a clean
architectural seam toward that future costs little now, it should be
preserved — but the current stage should not be prematurely architected
against infrastructure it doesn't yet need.

*Historical note, kept for context:* the product's earlier system design had
mandated full PWA support (manifest, service worker, offline-first caching)
as a fixed, day-one requirement. Neither that requirement nor the current
sequencing has actually been built yet in the supplied implementation
evidence — there is no sunk engineering cost either way.

**Mobile-first principle:** mobile is a primary consideration — interfaces
adapt naturally, core workflows stay usable on small screens, and the mobile
experience should feel intentional, not compressed. Mobile-first does not
mean desktop is secondary.


**Desktop workstation principle:** desktop remains important because
DEIXEN represents professional operational work — it should support
focused workflows, complex tasks, and a genuine professional workspace feel,
not "mobile stretched wide." Concrete breakpoints are owned by
`04_DEIXEN_Canonical_Design_System.md`.

## Terminal Behavioral Skeleton (implementation convention)

This defines interaction states only — not command syntax or response
content, which remain governed by the frozen slice boundary
(`07_DEIXEN_Canonical_Decisions_and_Current_State.md` Decision 8A) and by the
Amadeus Verification Standard (07 Decision 12).

| State | Trigger | What's shown | Learner's next move |
|---|---|---|---|
| Awaiting input | Terminal opened / prior cycle done | Empty, neutral input — never response or evaluative text | Enter a command |
| Command submitted | Non-empty input | Transitions immediately to Valid or Invalid — never a silent substitution | Wait for response |
| Valid command recognized | Input matches the frozen boundary's syntax | A real response (content is domain-gated) | Continue, hint, or next step |
| Invalid / out-of-boundary | Empty, malformed, or outside the current command boundary | A specific, honest message distinguishing "not recognized" from "not yet covered by this slice" | Correct or request a hint |
| Hint requested | Learner asks | Hint content; a single hint counter incremented in exactly one place | Retry |
| Completion detected | Owning area's criteria met (not Terminal itself) | Confirmation + next recommended action | Proceed |
| Reset / retry | Explicit learner action | Clean awaiting-input state | Begin again |

**Binding rule:** empty or unrecognized input must never be silently coerced
into a different valid command for scoring/evidence purposes.

## Content Schemas (implementation convention)

Minimal, deliberately sized for one real end-to-end learning path (see the
Vertical Slice rule below), not a full content system:

- **Lesson:** `id`, `moduleId`, `title`, `objective` (one sentence), `body`,
  `example`, `practiceBridge` (explicit link to the Terminal task it prepares
  for — a lesson without one is incomplete, not optional),
  `prerequisiteLessonIds`, `completionRule`.
- **Module:** `id`, `title`, `lessons` (ordered list of Lesson ids).

## Persistence Architecture (implementation convention)

Frontend-first with `localStorage`. Only **Recorded** and **Calculated**
evidence is persisted (see `07_DEIXEN_Canonical_Decisions_and_Current_State.md`
for the evidence classes) — illustrative/static content is never written to
storage, to protect the line between real evidence and decoration. The
persisted record carries a schema-version field; on a mismatch, the safe
default is a full reset rather than a silent migration (deliberate simplicity
choice — revisit only if real evidence shows learners losing meaningful
progress). A manual reset action returning the learner to a clean state is a
product requirement, not a developer convenience. A session is the browser
plus its `localStorage` — no login, no account, no cross-device sync at this
stage; adding those is a backend decision requiring the same evidence-based
justification as any other architecture change.

**Event Log, recovered as historical schema precedent (not a final schema —
input for the still-pending evidence/state schema design work):** the
earlier architecture's Event Log recorded exactly four fields per event —
event type, the command entered, the result, and a timestamp. Every engine
call passed through a thin bridge layer whose only job was to call the right
function, take the result, and log it this way — the pure engine modules
themselves never had any awareness that an Event Log existed. This is a
proven, minimal starting shape worth treating as a baseline for the concrete
schema rather than re-deriving from nothing.

## Vertical Slice Before Scale (the governing methodology rule)

Before expanding across large numbers of lessons, command families,
scenarios, or readiness signals, at least one **complete end-to-end vertical
slice** — using real content, not placeholders — must be validated all the
way through Learning → Terminal/Practice → Scenario → Assessment → Evidence →
Growth/Readiness. This proves the pattern can scale; it does not require the
whole future product built first. The specific current frozen slice boundary
(which commands, which scenario, which Coach touchpoints) is a Decision, not
an architecture principle — it lives in
`07_DEIXEN_Canonical_Decisions_and_Current_State.md` so this rule and its
current instance can't drift apart.

## Non-Negotiable Product Rules

1. **Terminal Centrality** — never reposition DEIXEN as content-first, a
   generic LMS, or quiz-based.
2. **Professional Positioning** — avoid classroom-style experience,
   child-oriented gamification, generic education patterns.
3. **Realistic Workflow** — operational realism over visual trends.
4. **Evidence-Based Progress** — progress represents capability and
   performance, not time spent or lessons completed.

## Change Control

Any proposed architecture change must answer: what problem does this solve,
why is the current architecture insufficient, what evidence supports the
change, and what does it do to product strategy. No structural change on
trend, preference, visual appeal, or implementation convenience alone.

## Saudi Market Readiness

An important, explicitly-named target outcome — not a decoration, isolated
percentage, or gamification mechanic. Composed conceptually of: Technical
Competency + Global Professional Customer Service + Saudi-Specific
Operational/Market Context + Saudi-Context Scenario Performance + Assessed
Workplace Decisions. Must be earned through demonstrated, traceable evidence;
no readiness claim, score, or percentage is authorized until its evidence
owner, calculation logic, and scope are explicitly defined and approved.
Customer Service is a separate, transferable global competency — it feeds
Saudi Market Readiness only through an explicitly approved mapping, never by
default.
