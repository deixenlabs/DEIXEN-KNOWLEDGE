---
name: DEIXEN Canonical Curriculum & Coach
owns: Lesson structure, both curriculum tracks, Ghost Mode, Speed Drills, and the Coach behavioral contract
supersedes reading in isolation: AMADEUS_CURRICULUM.md, relevant sections of PRODUCT_STRATEGY_UX_ARCHITECTURE-1.md, and Decisions_and_Current_State.md Decision 9
---

> **Synchronization note — Phase 2, 2026-09-24.** Working name: **DEIXEN**
> (provisional; see `DEIXEN_Operating_Constitution.md` §1). "AeroBridge" survives
> only inside historical filenames and provenance statements. Owner: **Karim** —
> earlier project records used the name "Malik" for the same person; those
> references now read "Karim". Current project state and every decision:
> `07_DEIXEN_Canonical_Decisions_and_Current_State.md`. Amadeus facts: only
> claims marked VERIFIED under 07 Decision 12 may be taught as fact.


# DEIXEN — Canonical Curriculum & Coach

## Curriculum source and scope

**Goal (07 Decision 18):** DEIXEN teaches professional Amadeus — Basic and
Advanced — sized to what the Saudi/Gulf job market requires of a beginner,
with behavior matching real Amadeus. Only VERIFIED Amadeus behavior may be
taught as fact (Decisions 12–13). A separate, non-Amadeus Customer Service
track sits alongside the technical track.

**Historical baseline:** the lesson structure below (17 Basic, 11 Advanced)
came from the EgyptAir Training Center course structure and was mapped to
the old engine's commands (file 05). It is preserved as input for future
curriculum authoring — not as the target curriculum, and not as evidence of
Amadeus behavior. Curriculum authoring beyond the first-build slice happens
after the slice (Execution Plan), against the Verified Reference and sourced
market requirements.

### Technical Track — Basic Course (historical baseline: 17 lessons)

In the baseline, lessons were mapped one-to-one to old-engine commands in
`05_DEIXEN_Canonical_Amadeus_Engine_Reference.md`; a few (Discounts, Multiply
Fare, Sending Messages, certain Reissue steps) were marked future-plan.
Lesson 17 ("Evaluation Means") was never defined. In the new build, every
command a lesson teaches must first be VERIFIED.

Two historical command notes from the source material: fare quote was
written as `FQD` rather than "FQ"; and fare pricing was "corrected" to
`FXP`/`FXB` rather than `FXP`/`FXX`. `FXX` is now VERIFIED as a real Amadeus
entry that prices without storing (`DEIXEN_Amadeus_Verified_Reference.md`
V-06), so that "correction" was wrong and is withdrawn. The old engine
implemented only `FXP`/`FXB`; that is implementation history, not evidence
about Amadeus.

### Technical Track — Advanced Course (historical baseline: 11 lessons)

In the old engine, only two were usable: Non-Homogeneous PNR (partial —
adult groups via repeated `NM1`; no child/infant fare types) and ancillary
booking (`HA`/`HS`/`CA`/`CS`/`SR`, coded but not reachable with real data).
The other nine (Reissue, EMD, Revalidation and similar) were future-plan.
These were limits of old code, not of the curriculum goal (Decision 14).

### Customer Service Track (5 lessons)

Non-Amadeus, dialogue/scenario-based. The five lessons, recovered here in
full since the topics themselves carry real content value: (1) Passenger
Profiling & Types — VIP, angry passengers, first-time flyers, corporate
clients, families; (2) Professional English Scripts — ready-made language
for delays, rescheduling, extra baggage, and penalty situations; (3)
De-escalation & Conflict Resolution — calming an angry customer; (4)
Cross-selling & Upselling — presenting ancillaries and cabin upgrades
professionally; (5) Scenario-Based Simulations — **a real Terminal command
from the VERIFIED, implemented set, paired with an appropriate English response** —
this lesson is the track's one deliberate integration point with the
technical engine, not purely dialogue like the other four.

**Anger Meter mechanic, recovered in full (not just "tied to the Event
Log"):** each dialogue scenario links the learner's response choices to a
visual calm-to-angry indicator that moves based on the quality of the
choice — direct reinforcement of lesson 3 specifically, and every movement
is logged as its own Event. This is a specific, concrete mechanic, not just
a general evidence-linkage statement.

Per `07_DEIXEN_Canonical_Decisions_and_Current_State.md` Decision 6, this
track is formally a separate global competency from Saudi-specific readiness,
is explicitly out of the initial vertical slice, and needs its own content
model, assessment logic, and evidence pathway defined before any proficiency
claim can be shown for it. That said, earlier planning framed the technical
and Customer Service tracks as feeding into **one shared growth record** —
dual competency (technical + communication) as one goal, not two separate
ones. Decision 6's caution about not showing unearned CS metrics yet
refines this vision with necessary evidence-integrity guardrails; it doesn't
abandon it.

### L9 Specialization Unit (Timatic / IROPS / Saudi market)

Historical design (old engine): `RT → XE → SS/AN → ER` for
irregular-operations handling, `TI` for Timatic (the old engine supported
Egyptian passports only), repeated `NM1` entries for
group/Umrah-style bookings. Accompanying informational content (no commands
involved) covers operational specifics for named Saudi carriers — Saudia
(`SV`), flynas (`XY`), flyadeal (`F3`) — and performance-under-time-pressure
scenarios. That last idea was originally tied to a named "Time-Pressure Tag"
mechanic in a design document that was never supplied to any consolidation
pass and may no longer be current — the specific mechanic can't responsibly
be reconstructed, but the underlying idea (measuring performance under
realistic time pressure, especially for Saudi-market scenarios) is worth
preserving as a curriculum direction even without the original spec.

### Ghost Mode (scripted demonstration format)

JSON-defined steps of type `type` / `pause` / `reveal`, recovered here at the
schema level since a future implementer would otherwise have to reinvent
field names from the concept alone:

```json
{
  "lessonId": "L2-availability-an",
  "steps": [
    { "type": "type", "text": "AN15JULCAIDXB", "charDelayMs": 60 },
    { "type": "pause", "durationMs": 400 },
    { "type": "reveal", "source": "COMMAND_REFERENCE.md#AN" }
  ]
}
```

`type` steps type character-by-character at `charDelayMs` speed — fully
textual, deliberately with no audio. Critically, `reveal` pulls the **live
engine's real output** rather than a hand-authored response — this is what
keeps Ghost Mode automatically in sync with the actual engine reference
above rather than drifting into its own invented version of what a command
does.

### Speed Drills

A sub-mode inside Practice that repeats an already-implemented command and
computes characters-per-minute from existing Event Log timestamps — no new
engine logic, just aggregation and display. **Explicit rule, still binding:**
no absolute CPM threshold (e.g., "X CPM = job-ready") may be set without a
real, documented external source (actual contact with booking offices/call
centers). Until such a source exists, the metric must stay relative
(self-improvement over time) — the same "no fabrication" discipline applied
to Amadeus behavior applies equally to invented market benchmarks.

### Future Expansion Backlog

An explicit list of curriculum items not yet implementable, deliberately
gated and not to be shown to the learner as available "Practice" content
until they're actually built.

## The Coach — behavioral contract

**Coach is a core guided-learning layer, not decorative UI.** It must appear
at the key moments where guidance materially improves learning or correction,
across the entire journey — not just inside Terminal.

**Required touchpoints:**
- **Learning/Curriculum** — orientation, explanation, next-step guidance.
- **Terminal/Practice** — interpret the learner's actions, identify mistakes,
  explain the error, suggest the next useful move.
- **Scenario** — contextual guidance when the learner is stuck or makes a
  meaningful mistake.
- **Assessment** — feedback consistent with assessment state and hint
  semantics (see the Assessment State Contract in
  `07_DEIXEN_Canonical_Decisions_and_Current_State.md`).
- **Growth/Readiness** — explain meaningful outcomes and connect them to
  evidence, without inventing performance data.

**State binding:** Coach behavior must be driven by the learner's actual
state — actions, errors, hints used, assessment state, available evidence —
never a static generic help panel.

**Error-message discipline (non-negotiable, carried from the earliest
product strategy and never contradicted since):** the official engine error
message is always shown verbatim. A plain-language explanation is placed
alongside it. The official message is never replaced by a "friendlier"
substitute — doing so breaks the realism the entire training environment
depends on. Not every error category needs the same depth of response:
format/data-reference errors usually need only a direct correction, while
sequence/logical errors may benefit from a deeper link back to a related
lesson. A full per-category response matrix is deliberately deferred until
real usage data exists to design it against, rather than guessed now.

**Boundary:** Coach guidance must stay truthful to current product state and
verified domain semantics — Coach may present Amadeus behavior as fact only
when it is VERIFIED under
`07_DEIXEN_Canonical_Decisions_and_Current_State.md` Decisions 12–13. Coach
must never be limited to Terminal-only use, treated as decorative microcopy,
or used to invent evidence, scores, readiness, or mastery.

**Layout ownership is explicitly open:** whether Coach is a persistent global
element or a component embedded per page is not yet decided — an
implementation detail left open within the approved behavioral boundary
above, to be resolved during actual design/build work, not here.
