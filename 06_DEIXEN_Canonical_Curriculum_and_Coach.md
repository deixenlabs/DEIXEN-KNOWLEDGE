---
name: DEIXEN Canonical Curriculum & Coach
owns: Lesson structure, both curriculum tracks, Ghost Mode, Speed Drills, and the Coach behavioral contract
supersedes reading in isolation: AMADEUS_CURRICULUM.md, relevant sections of PRODUCT_STRATEGY_UX_ARCHITECTURE-1.md, and Decisions_and_Current_State.md Decision 9
---

# DEIXEN — Canonical Curriculum & Coach

## Curriculum source and scope

Based on the EgyptAir Training Center course structure, plus a separate,
non-Amadeus Customer Service track. Nothing in the newer knowledge documents
disputes this content — they simply haven't restated it yet, since current
build effort is focused on one narrow vertical slice first (see
`07_DEIXEN_Canonical_Decisions_and_Current_State.md`). Treat everything
below as the target curriculum.

### Technical Track — Basic Course (17 lessons)

Mapped one-to-one to specific commands from
`05_DEIXEN_Canonical_Amadeus_Engine_Reference.md`. Most are implementable
today against the current engine; a few (Discounts, Multiply Fare, Sending
Messages, certain Reissue steps) are flagged future-plan, pending engine
expansion. Lesson 17 ("Evaluation Means") has an undefined gap carried over
from earlier planning and still needs definition.

The curriculum contains two historical command corrections from its
source material. The first — fare quote as `FQD` rather than "FQ" — remains
consistent with the current engine's implementation. The second — the prior
claim that fare pricing should be `FXP`/`FXB` rather than `FXP/FXX` — is now
**superseded as a domain-level assumption** by the completed Amadeus evidence
package, which resolved `FXX` as a real Amadeus command. The current engine
still implements only `FXP`/`FXB`; that is implementation truth and must not be
used as proof that `FXX` is invalid in real Amadeus. The prior curriculum
wording must therefore not be propagated as current Amadeus fact until the
formal documentation-retraction decision is completed.

### Technical Track — Advanced Course (11 lessons)

Only two are usable against the current engine: Non-Homogenous PNR (partial —
adult groups via repeated `NM1` entries work; child/infant fare types do not,
since the engine has no such fare type) and ancillary booking (`HA`/`HS`/`CA`/
`CS`/`SR` — though see the engine reference's Known Issue #8: this command
family is currently unreachable with real data in the supplied build, so
"usable" here means code-correct, not currently live). The remaining 8 of 11
lessons are future-plan only, pending curriculum content the engine doesn't
support yet (Reissue, EMD, Revalidation, and similar).

### Customer Service Track (5 lessons)

Non-Amadeus, dialogue/scenario-based. The five lessons, recovered here in
full since the topics themselves carry real content value: (1) Passenger
Profiling & Types — VIP, angry passengers, first-time flyers, corporate
clients, families; (2) Professional English Scripts — ready-made language
for delays, rescheduling, extra baggage, and penalty situations; (3)
De-escalation & Conflict Resolution — calming an angry customer; (4)
Cross-selling & Upselling — presenting ancillaries and cabin upgrades
professionally; (5) Scenario-Based Simulations — **a real Terminal command
from the implementable set, paired with an appropriate English response** —
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

Built entirely from already-implemented commands — no new engine work
required: `RT → XE → SS/AN → ER` for irregular-operations handling, `TI` for
Timatic (Egypt-passport-only limitation applies), repeated `NM1` entries for
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
validated domain semantics — domain-sensitive aviation/GDS guidance remains
gated behind SME validation until that validation closes (see
`07_DEIXEN_Canonical_Decisions_and_Current_State.md` Decision 7). Coach
must never be limited to Terminal-only use, treated as decorative microcopy,
or used to invent evidence, scores, readiness, or mastery.

**Layout ownership is explicitly open:** whether Coach is a persistent global
element or a component embedded per page is not yet decided — an
implementation detail left open within the approved behavioral boundary
above, to be resolved during actual design/build work, not here.
