---
name: DEIXEN Learning Experience Architecture
status: DRAFT AUTHORITY — NOT CANONICAL. FIRST BUILD + Phase 2
  synchronization (2026-09-24; see the reading rule below). Authored per
  "AEROBRIDGE — MASTER BUILD PROMPT: Learning Experience Architecture"
  against the canonical set, the Learning Design Specification (Revision 2),
  and the operating references. Reviewed by Claude in Execution Plan
  Phase 1; not yet approved by Karim.
owns: The architecture of the learner-facing EXPERIENCE — how DEIXEN's
  already-approved learning system (product structure, the Amadeus engine,
  curriculum, the Coach contract, the evidence/assessment contracts, and the
  Learning Design's skill-state and assistance mechanics) becomes one
  coherent, connected experience for a learner moving through the product.
  Experience hierarchy, learner journeys, entry/exit conditions, meaningful
  states and transitions, how practice/scenario/assessment/evidence/
  progression/reinforcement/transfer relate AS EXPERIENCED (not as evidence
  logic, which is already decided), Coach/support experience boundaries,
  continuity/resume, failure/recovery, and cross-system behavioral
  dependencies (stated, never specified as schemas or APIs).
does not own: Amadeus technical truth (file 05 + Decision 7's SME process);
  learning intent and mechanics (the Learning Design Specification); product
  identity and information architecture (file 03); current project decisions
  (files 07, 13); visual identity and final styling (the later Claude Design
  phase); production implementation (engineering); real learner
  effectiveness (cannot be established by architecture or documentation
  alone).
relationship to the canonical set: Strictly additive and translational.
  Files 00 and 03–08, 13, 14 remain authoritative in full per the Operating
  Constitution. The Learning Design Specification remains the sole authority
  on learning intent and mechanics; this document translates it into
  experience architecture and does not redecide anything it already
  settled. If any sentence below appears to disagree with a canonical file
  or with the Learning Design Specification, the upstream source is correct
  and the conflict is named explicitly in §22 (Open Items Register) — never
  silently resolved in either direction.
source basis: The nine canonical files, the Operating Constitution, the
  Master Execution Roadmap, the Learning Design Specification (Revision 2),
  the Universal AI Session Handoff Protocol, the Prompt Engineering &
  Governance standard, and this task's own governing document ("AEROBRIDGE
  — MASTER BUILD PROMPT: Learning Experience Architecture"), all read in
  full for this pass. This document was not given the DEIXEN repository/
  codebase; where it discusses engine or storage behavior it is citing file
  05's and file 03's already-established claims, not independently
  re-verifying them.
---

> **Synchronization note — Phase 2, 2026-09-24.** Working name: **DEIXEN**
> (provisional; see `DEIXEN_Operating_Constitution.md` §1). "AeroBridge" survives
> only inside historical filenames and provenance statements. Owner: **Karim** —
> earlier project records used the name "Malik" for the same person; those
> references now read "Karim". Current project state and every decision:
> `07_DEIXEN_Canonical_Decisions_and_Current_State.md`. Amadeus facts: only
> claims marked VERIFIED under 07 Decision 12 may be taught as fact.

> **Reading rule — Phase 2 synchronization, 2026-09-24 (applies to the whole
> document; where a sentence below conflicts with this box, this box wins).**
>
> 1. **Status.** Draft authority, not canonical. Reviewed by Claude (project
>    lead) in Execution Plan Phase 1; not yet approved by Karim. A separate
>    independent (Opus) review is no longer a required step (07 Decision 17).
>    Its slice-relevant content becomes binding only through the Phase 3
>    Slice Build Spec that Karim approves.
> 2. **Amadeus facts.** Wherever this document says "Decision 7", "SME",
>    "domain validation", or "domain/SME validation", read: the Amadeus
>    Verification Standard (07 Decision 12). Only VERIFIED claims may be
>    taught or simulated (Decision 13).
> 3. **File 05.** Tags such as VERIFIED FACT or IMPLEMENTATION-VERIFIED that
>    rest on file 05 describe the old engine, which is now historical and
>    unavailable (Decision 14) — they are not Amadeus truth and not
>    requirements for the new build.
> 4. **Old engine limits and Known Issues** (one seat per PNR, two segments,
>    adults-only fares, Egypt-only Timatic, `FQN`/`FQR`, ancillaries, Known
>    Issue #7, `XE` scope) are not carried into the new build. The
>    Simulator Scope Disclosure principle stands; its list will be rebuilt
>    from the new build's real scope. The Known Issue #7 mitigation question
>    becomes a requirement: element numbers shown during entry must match
>    the final PNR numbering.
> 5. **Skill-state rename.** The skill state formerly named VERIFIED is now
>    **CONSOLIDATED** (same definition), so it cannot be confused with the
>    source label VERIFIED. This closes the naming-collision open question;
>    historical review rows that discuss "the VERIFIED naming collision"
>    refer to this state.
> 6. **Queues.** `QE`/`QN`/`QD` are not taught (Decision 13) until verified.
> 7. **Still open:** the Event Log questions (timestamp granularity,
>    chain-sequence correlation) move to the Phase 3 evidence/state design.
>    Items assigned to a "Knowledge Recovery pass" now belong to curriculum
>    authoring (Execution Plan Phase 6); references to the Master Execution
>    Roadmap now mean `DEIXEN_Execution_Plan.md`.
> 8. **Roles and names.** Manus and ChatGPT have no project role. Owner:
>    Karim (earlier records: "Malik").

# DEIXEN — Learning Experience Architecture (DRAFT, FIRST BUILD)

> **Read this before anything else.** This document answers one question:
> *how does DEIXEN's approved learning system become one coherent
> learner experience across the product?* It is a translation layer, not a
> second Learning Design and not a restatement of one. Every claim below
> carries one of two kinds of tag: a **source-role tag**, showing which
> upstream authority a fact comes from, or an **open-item status**, using
> the exact five labels this document's governing brief requires. See §2 for
> the full legend. Nothing tagged `[EXPERIENCE ARCHITECTURE DECISION]` is
> canonical merely because it appears in a structured document with a
> confident tone — it is a proposal, exactly like the Learning Design
> Specification's own `LEARNING DESIGN DECISION` items, awaiting Opus review
> and then Karim's approval.

## Table of Contents
1. Executive Summary
2. Purpose, Scope, Authority, and Classification
3. Source Map, Upstream Ownership, and Non-Ownership
4. The Upstream Translation Method
5. The End-to-End Experience Model
6. Product Structure Preservation
7. Experience Coverage (A–O)
8. State Architecture
9. Transition Architecture
10. Practice Progression Ladder
11. Coach Experience Boundary
12. Evidence Integrity Framework
13. Progression Integrity
14. Scenario Integrity
15. Failure / Recovery Integrity
16. Continuity / Resume Architecture
17. Event / Storage Dependencies
18. Mobile / Desktop Experience Architecture
19. Visual Design Boundary
20. Minimum Justified Complexity Ledger
21. Cross-File Consistency Audit
22. Open Items Register
23. Adversarial Self-Review
24. Defect vs. Preference Ledger
25. Final Architecture Acceptance Test
26. Readiness Determination
27. Final Self-Check
28. Canonicalization Note & Change Discipline

---

## 1. Executive Summary

DEIXEN has an approved product structure (file 03), an approved design
posture (file 04), an engine whose documented behavior is
implementation-verified in file 05, an approved curriculum
and Coach contract (file 06), a closed decisions ledger (file 07/13), and —
as of Revision 2's closure determination — a learning system that is
internally coherent at the level of skill states, assistance tiers,
checklists, and evidence classes (the Learning Design Specification, "LDS"
below). What has not existed until this document is the layer connecting
those to an actual, walkable learner experience: which screen, which state,
which transition, in what order, with what the learner is told and when.

This document builds that layer for the frozen vertical slice (Decision 8A:
`AN → SS → FQD → FXP`, one scenario) and states, at the same rigor, what it
deliberately leaves for later. It adds no new product area, no new
evidence class, no new counter, and no new mastery claim. Where it
introduces a mechanism (a state, a transition, a constraint), it justifies
that mechanism against a real requirement named in files 03–08, 13, 14, or
the LDS — never against genericism or completeness for its own sake.

**One correction made during authoring, stated once, applied throughout
without further comment:** this document's own governing brief refers to
the core practice environment as "Reminal" in three places. File 08 (AI
Working Rules & Dev Process) explicitly and by name prohibits this exact
term ("never 'Reminal,' 'generic simulator,' or 'training screen'"). This is
treated as a typographical artifact in the brief, not a new instruction —
"Terminal" is used throughout this document, and the substitution is
recorded here rather than made silently, per the Operating Constitution's
closing rule.

---

## 2. Purpose, Scope, Authority, and Classification

**Purpose.** Define the learner-facing experience architecture that makes
DEIXEN's approved learning system walkable: what the learner sees,
when, in what state, moving through what transition, under what evidence
and progression rules — without inventing Amadeus facts, learning-design
mechanics, product scope, or visual identity this document has no authority
over.

**Scope.** This document governs experience architecture only: experience
hierarchy, learner journeys, states, transitions, the practice/scenario/
assessment/evidence/progression/reinforcement/transfer relationships as
lived by a learner, Coach/support experience boundaries, continuity/resume,
failure/recovery, and cross-system behavioral dependencies (named, not
specified as schemas, APIs, or storage engines). It does not touch product
identity or IA (file 03), visual design tokens (file 04), Amadeus command
behavior (file 05), curriculum lesson content or counts (file 06), the
decisions ledger itself (file 07/13), the multi-agent process (file 08), or
any of the Learning Design Specification's own skill-state, assistance,
checklist, or evidence-class mechanics — it consumes all of these as given.

**Authority this document has, and does not have.** This is a
translation-and-architecture deliverable, authored under the same delegated
technical authority the LDS was authored under (Operating Constitution §4:
technical agents decide ordinary implementation/architecture sequencing
that doesn't alter approved product/curriculum/evidence decisions). It is
not a decision. The governance chain: canonical knowledge + Learning Design
→ this architecture → this document's own adversarial self-review (§23) →
independent review (Opus) → human/product-owner review (Karim) → approval →
canonicalization. This document cannot promote itself past "proposed," and
per its own governing brief, the strongest status it may claim for itself
is **"READY FOR INDEPENDENT ADVERSARIAL REVIEW"** — never "Canonical,"
"Officially Approved," or "Fully Validated" (see §26).

**Classification legend.**

*Source-role tags* — every sourced claim below carries one of these, per
this document's own governing brief §4 and consistent with the Operating
Constitution §2's simpler CANONICAL / DECIDED-DELEGATED / OPEN / HISTORICAL
/ RECOMMENDATION vocabulary, which each tag below maps onto in parentheses:

| Tag | Meaning |
|---|---|
| `[PRODUCT/SYSTEM — CANONICAL]` | Stated as current in files 03, 04, or 08. (≈ CANONICAL) |
| `[DECISION — CANONICAL]` | Stated as closed, approved, or delegated in files 07 or 13. (≈ DECIDED/DELEGATED) |
| `[AMADEUS — IMPLEMENTATION-VERIFIED ONLY]` | From file 05. Establishes what the supplied code does, never real-world Amadeus/GDS truth. (≈ CANONICAL, domain-truth boundary applies) |
| `[LEARNING DESIGN SOURCE]` | From the LDS (Revision 2). This document translates these; it never redecides them. (≈ CANONICAL within its own draft-authority scope) |
| `[HISTORICAL]` | True of an earlier generation or a prior build; evidence, never a default. (≈ HISTORICAL) |
| `[EXPERIENCE ARCHITECTURE DECISION]` | This document's own new translation-level choice. A proposal, not a decision, exactly as LDS's `LEARNING DESIGN DECISION` tag works. (≈ RECOMMENDATION until reviewed/approved) |
| `[RECOMMENDATION]` | An optional proposal, explicitly not required. (≈ RECOMMENDATION) |

*Open-item statuses* — used verbatim, exactly as this document's governing
brief specifies, whenever a material question cannot be safely resolved
here:

`UNKNOWN` · `PENDING DECISION` · `REQUIRES DOMAIN VALIDATION` ·
`REQUIRES IMPLEMENTATION VERIFICATION` · `REQUIRES USER AUTHORITY`

No plausible assumption fills a gap that should carry one of these five
labels instead — consistent with file 08's No-Guessing Rule and the
Operating Constitution's Closing Rule.


---

## 3. Source Map, Upstream Ownership, and Non-Ownership

**Inputs confirmed read in full for this pass:** all nine canonical files
(00, 03–08, 13, 14), the Learning Design Specification (Revision 2), the
Universal AI Session Handoff Protocol, the Prompt Engineering & Governance
standard, the Master Execution Roadmap, and this task's own governing
document. No required input was missing or inaccessible.

**Inputs this document explicitly does not have, and does not pretend to
have:** the actual Claude/Manus arbitration record, the Domain/SME
Validation Brief and its SME-01…SME-10 claim register, the Scenario Bank
architecture decision review, and the DEIXEN repository/codebase
(neither the vanilla-JS artifact nor the claimed React/TypeScript
baseline). Every canonical file already tracks these as missing; this
document inherits that status rather than re-deriving it, and nothing below
depends on their contents being other than what's already recorded in files
00, 07, 13.

| File | Owns | Tag used when cited |
|---|---|---|
| 00 — Knowledge Consolidation Plan | Source inventory, methodology, how the other files relate | `[PRODUCT/SYSTEM — CANONICAL]` |
| 03 — Product & Architecture | Identity, target user, five-area IA, platform direction, persistence architecture, Terminal centrality | `[PRODUCT/SYSTEM — CANONICAL]` |
| 04 — Design System | Visual/UX principles, accessibility baseline, historical tokens, anti-patterns, Design Positioning (closed) vs. Execution (open) | `[PRODUCT/SYSTEM — CANONICAL]` |
| 05 — Amadeus Engine Reference | The full command set, RBD table, error taxonomy, engine constraints, Known Issues | `[AMADEUS — IMPLEMENTATION-VERIFIED ONLY]` |
| 06 — Curriculum & Coach | Lesson structure, both tracks, Ghost Mode, Speed Drills, the Coach behavioral contract | `[PRODUCT/SYSTEM — CANONICAL]` |
| 07 — Decisions & Current State | The living decisions ledger; evidence/assessment/scenario contracts | `[DECISION — CANONICAL]` |
| 08 — AI Working Rules & Dev Process | Multi-agent protocol, terminology discipline, development process | `[PRODUCT/SYSTEM — CANONICAL]` |
| 13 — Decision Resolution Register | Audited status of every known decision as of the last full review | `[DECISION — CANONICAL]` |
| 14 — Sufficiency Audit | Whether the canonical set is complete enough for the current phase | `[DECISION — CANONICAL]` |
| Learning Design Specification (Rev. 2) | Skill states, assistance ladder, checklists, evidence/assessment mechanics, retention/transfer definitions | `[LEARNING DESIGN SOURCE]` |
| Master Execution Roadmap | Phase sequencing, the mechanics-level pipeline cited in §5, current AI-role assignments | `[PRODUCT/SYSTEM — CANONICAL]` — cited for sequencing/pipeline facts only, never for learning-mechanics or product-architecture facts owned elsewhere |
| Prompt Engineering & Governance | How prompts (including this task's own governing brief) are constructed — process, not product truth | Referenced for method, never cited as a product/learning fact |
| Universal AI Session Handoff Protocol | Session-continuity mechanics for handing work between agents/sessions — process, not product truth | Referenced for method, never cited as a product/learning fact |

**What this document owns** (per its governing brief §9): experience
hierarchy; major learner journeys; entry/exit conditions; meaningful
learner/system states and their transitions; how practice, scenario,
assessment, evidence, progression, reinforcement, and transfer relate *as
lived experience*; feedback/correction relationships at the experience
level; Coach/support experience boundaries; continuity/resume; failure/
recovery; and necessary cross-system dependencies stated at the behavioral
level.

**What this document explicitly does not own** (per its governing brief
§10) — restated here because the boundary is load-bearing throughout:

- **Amadeus technical truth** — owned by file 05 for implementation truth,
  and by Decision 7's still-pending SME process for domain truth. This
  document never states what a command does beyond what file 05 already
  documents, and never resolves a domain question file 05/07/13 leave open.
- **Learning intent and mechanics** — owned entirely by the LDS. This
  document does not redefine a skill state, an assistance tier, a
  checklist rule, an evidence class, or a numeric default (PROVISIONAL or
  otherwise). Where the LDS already answers an experience-adjacent
  question (e.g., "does a Ghost Mode replay count as evidence?"), this
  document cites the answer rather than re-deriving it.
- **Product architecture** — owned by file 03. The five-area IA, platform
  direction, and persistence architecture are inputs here, not decisions
  this document can revisit.
- **Current project decisions** — owned by files 07 and 13. This document
  treats every Closed/Approved item there as fixed ground and every OPEN
  item there as still open — it does not close anything on Files 07/13's
  behalf.
- **Visual identity and final styling** — owned by the later Claude Design
  phase, gated on Karim's approval of Design Execution. This document
  defines hierarchy, purpose, interaction relationships, and constraints
  design must satisfy — never colors, type, or pixel layout.
- **Production implementation** — owned by engineering (Claude Code). This
  document names required behavioral dependencies; it does not specify
  schemas, APIs, or storage engines.
- **Real learner effectiveness** — cannot be established by architecture or
  documentation alone, exactly as the LDS's own closure determination
  states of itself. Nothing below is evidence that DEIXEN teaches
  well; it is evidence that the *system connecting* its already-approved
  parts is coherent.

**Terminology note (stated once, applied throughout without further
comment):** see §1's correction — "Terminal" is used exclusively below,
never "Reminal."

**Filename note:** this document's own governing brief refers to files
03–08 without the word "Canonical" in the filename (e.g.,
"03_DEIXEN_Canonical_Product_and_Architecture.md"). This is read as informal
shorthand for the same nine canonical files the Operating Constitution
names, not a distinct or superseding set — no file in this Project matches
the brief's shorthand names more literally than the canonical files cited
throughout this document.


---

## 4. The Upstream Translation Method

Every major Learning Design concept is passed through the same seven-step
transformation before it appears anywhere else in this document. This is
the one method used throughout — stated once here, applied silently
thereafter, rather than repeated at every occurrence:

| Step | Question |
|---|---|
| **Intent** | What is the learner supposed to achieve? (LDS's objective/principle language) |
| **Experience** | What does the learner actually see, read, or encounter? |
| **Interaction** | What do the learner and the system each do? |
| **State** | What meaningful condition exists because of that interaction? |
| **Evidence** | What can legitimately be observed and persisted (per file 07's evidence classes)? |
| **Progression** | What may legitimately happen next? |
| **Dependency** | What other system or artifact must support this, and is that support confirmed? |

This replaces copying LDS's educational prose into product architecture.
Where a Learning Design mechanic has no experience-level consequence beyond
what LDS already states (for example, the internal computation of the
independence flag), this document names the dependency once (§17) rather
than re-narrating the mechanic.

---

## 5. The End-to-End Experience Model

Two chains already exist in the canonical set, at two different
granularities, and they are not in conflict — but nothing before this
document has stated how they relate. Leaving that unstated risks a future
reader treating them as competing models.

**File 03's canonical chain (IA-area level, IMMUTABLE per Non-Negotiable
Product Rule #1)** `[PRODUCT/SYSTEM — CANONICAL]`:

> Learning → Terminal/Practice → Scenario → Assessment → Evidence →
> Growth/Readiness

**The Learning Design's / Master Execution Roadmap's pipeline (mechanics
level)** `[LEARNING DESIGN SOURCE]`:

> Learn → Retrieve → Practice → Feedback → Correction → Repeat →
> Independent Performance → Assessment → Evidence → Progression →
> Reinforcement → Transfer → (Readiness)

**`[EXPERIENCE ARCHITECTURE DECISION]` — the reconciliation:** the second
chain is the internal mechanics of the first chain's middle links, not a
rival five/six-area model. Concretely:

| File 03 node | Pipeline stages it contains | Where it is lived |
|---|---|---|
| Learning | Learn, Retrieve | Learning/Curriculum area, bridged via a Lesson's `practiceBridge` |
| Terminal/Practice | Practice, Feedback, Correction, Repeat, Independent Performance | Terminal/Practice area |
| Scenario | The scenario-context portion of Transfer | Scenario Bank area (Terminal reused underneath) |
| Assessment | Assessment | An internal state within the Learning/Practice journey (file 03 is explicit that Assessment is not a sixth area) |
| Evidence | Evidence | Persisted via the localStorage persistence architecture (file 03) |
| Growth/Readiness | Progression, Reinforcement, Transfer (as legible status), Readiness | Growth/Readiness area |

One subtlety worth stating explicitly because it affects §7.G and §7.M
below: **Transfer has two loci, not one.** The *doing* of a transfer
attempt happens inside a Scenario Session (Scenario Bank area); the
*legibility* of that attempt as a TRANSFERRED skill-state change is what
Growth/Readiness later reflects. A single Scenario interaction therefore
has consequences visible in two different IA areas at two different times
— this is not a contradiction, but it is worth naming so a future
implementer does not assume Transfer is a Growth/Readiness-only concept.

**`[EXPERIENCE ARCHITECTURE DECISION]`:** "Readiness," named as the
pipeline's final stage in this document's own governing brief, is read as
the explicit naming of what file 03 already calls the terminal node of the
whole chain (Growth/**Readiness**). It introduces no new stage beyond what
file 03 already authorizes, and — per Decision 8A — for the frozen slice it
resolves to exactly one bounded qualitative status, never a number.

---

## 6. Product Structure Preservation

The five approved areas (file 03) are the baseline for this entire
document. No sixth area is introduced, discussed as pending, or implied by
anything below — the Work Shift Simulator concept remains exactly as
scoped in file 03/13: real, preserved, not authorized.

**Terminal centrality is a hard constraint on this architecture, not a
section to satisfy once.** Of the eight experience states this document
catalogs (§8), five are Terminal-context states (Practice, Assessment, and
the Scenario state, which itself wraps Terminal, plus the two Terminal-
adjacent entry variants named in §8's notes). This ratio is intentional: it
reflects Non-Negotiable Product Rule #1 (file 03) and the Terminal Priority
decision (file 07), not an accident of how the catalog happened to come
out. Any future extension of this document that dilutes that ratio without
citing a specific evidence-based reason is a regression, not neutral
growth.

**`[EXPERIENCE ARCHITECTURE DECISION]` — explicit rejection of the
"lessons + quiz + dashboard" reduction** (named as a risk in this
document's own governing brief §8): this architecture treats Learning
content as preparation *for* Terminal action, never as a self-contained
quiz; treats Assessment as a state *within* the practice journey, never a
separate top-level test area; and treats Growth/Readiness as an evidence
report, never a gamified dashboard. Sections 7–9 enforce this by
construction — no state in §8 is a "quiz screen," and no transition in §9
terminates at a decorative summary.


---

## 7. Experience Coverage

Each area below is run through §4's seven-step translation. Coverage is
scoped to the frozen vertical slice (Decision 8A) unless stated otherwise;
where the slice doesn't reach far enough to answer a question, that is
stated as an open item rather than extrapolated.

### 7.A — Entry / Orientation

- **Intent:** the learner always knows where they are, what they're doing,
  why it matters, what success means, and what happens next.
- **Experience:** Flight Deck (file 03, area 1) is the single entry point
  that answers all five. It is not a marketing homepage and not a
  progress-percentage screen `[PRODUCT/SYSTEM — CANONICAL]`.
- **Interaction:** the learner reads a single "next recommended action"
  and either accepts it or navigates elsewhere via the five-area
  navigation.
- **State:** `ORIENTATION` (§8).
- **Evidence:** none is produced here; Flight Deck *reads* evidence
  already recorded elsewhere (file 03).
- **Progression:** the recommendation shown is itself the Progression
  mechanism's output (§7.K) — Orientation does not compute progression, it
  displays it.
- **Dependency:** the recommendation logic needs the same evidence
  aggregation §17 already flags as dependent on Event Log confirmation.

**`[EXPERIENCE ARCHITECTURE DECISION]`:** "why it matters" is satisfied by
the frozen slice's own framing (Saudi/Gulf job-readiness context, file 03)
appearing as context, not as a persuasive/marketing statement — consistent
with Design Positioning being closed as professional/operational (file 04).

### 7.B — Learning / Curriculum

- **Intent:** the learner acquires the conceptual and syntactic
  understanding a specific Terminal skill requires, before attempting it.
- **Experience:** a Lesson (file 03's schema: id/moduleId/title/objective/
  body/example/practiceBridge/prerequisiteLessonIds/completionRule)
  `[PRODUCT/SYSTEM — CANONICAL]`.
- **Interaction:** reading, and optionally replaying Ghost Mode (§7.C).
- **State:** `LEARNING` (§8).
- **Evidence:** Lesson `completionRule` satisfaction only — never counted
  toward any skill state (LDS Principle 4).
- **Progression:** completion enables, but does not require, the first
  Terminal attempt (LDS §10, "Lesson Completion").
- **Dependency:** none beyond the existing Lesson schema.

**`[EXPERIENCE ARCHITECTURE DECISION]`:** every Lesson's `practiceBridge`
is the single required exit from `LEARNING` into `TERMINAL_PRACTICE` — a
Lesson without one is incomplete per file 03's own schema note, and this
document adds nothing beyond enforcing that the experience never presents
a Lesson as a dead end.

**Two gaps in `LEARNING`'s coverage found during this document's own
adversarial self-review (§23), fixed in place here rather than only
listed:**

1. **Lesson 17 ("Evaluation Means")** carries an explicitly undefined
   completion rule, unresolved since early planning (file 06, file 13).
   This document does not invent one. `[EXPERIENCE ARCHITECTURE DECISION]`:
   until Knowledge Recovery resolves it, `LEARNING` must not present Lesson
   17 with a working, silently-assumed `completionRule` — it is either
   withheld from the visible curriculum list or shown honestly as
   incomplete, per the false-affordance rule below. `PENDING DECISION` —
   tracked in §22.
2. **Future-plan curriculum items** (the 8 of 11 Advanced-track lessons
   marked future-plan, and anything on file 06's Future Expansion Backlog)
   must never appear inside `LEARNING` as available Practice content — this
   is file 06's own gating rule (`[PRODUCT/SYSTEM — CANONICAL]`), restated
   here as a hard experience constraint because `LEARNING` is the one
   state where a learner could otherwise stumble into them.

**General rule these two gaps are instances of, stated once here and
applied everywhere in this document:** per file 07's Definition of Done
("no false affordance remains anywhere in the slice — every visible
control either works or is truthfully labeled planned/unavailable"), no
state cataloged in §8 may present a control, lesson, command, or Scenario
as available unless it truly is; anything not yet built is labeled
planned/unavailable rather than hidden through silence or shown as if
functional.

### 7.C — Retrieval

- **Intent:** prior exposure is intentionally activated by requiring
  production, not recognition, closing LDS Principle 1's gap.
- **Experience:** the learner's *first* Terminal attempt on a skill, typed
  from memory — no example visible, no Ghost Mode replay immediately
  preceding it in the same session.
- **Interaction:** a command submission with no assistance active.
- **State:** this is the entry condition into `TERMINAL_PRACTICE` (§8), not
  a separate state — Retrieval is a *quality* of an attempt (the first,
  unaided one), not a place the learner navigates to.
- **Evidence:** a Recorded event; whether it qualifies as independent
  follows LDS §7 Fix 2's exclusion rule exactly.
- **Progression:** a qualifying attempt reaches DEMONSTRATED_INDEPENDENT
  (LDS §7).
- **Dependency:** none beyond LDS's own exclusion-rule dependency (§17,
  §21 below).

**`[EXPERIENCE ARCHITECTURE DECISION]`:** Ghost Mode and a Lesson's
`example` field are recognition-level and must never be positioned, in any
surface, as "practice" — they sit only in `LEARNING`/`GHOST_MODE`, never
inside `TERMINAL_PRACTICE`'s own flow, so a learner cannot mistake watching
for retrieving.

### 7.D — Guided Practice

- **Intent:** support helps the learner move toward independent
  performance without the system ever crediting assisted success as
  independent (LDS Principle 2).
- **Experience:** the learner is inside `TERMINAL_PRACTICE`, has requested
  or received Nudge / Partial Reveal / Full Reveal content (LDS §15).
- **Interaction:** a learner-initiated assistance request (or, for
  repeated errors, an offered — never forced — escalation, LDS §13).
- **State:** still `TERMINAL_PRACTICE` — assistance level is an attribute
  of the attempt, not a separate state (§8's notes explain why this isn't
  cataloged separately).
- **Evidence:** the assistance counter increments (file 03's single
  counter, untouched per LDS §7 Fix 2); the *following* attempt's
  independence flag is set per the diagnostic/corrective split (LDS §13).
- **Progression:** repeated qualifying success still required before
  DEMONSTRATED_INDEPENDENT/CONSOLIDATED — guided success alone never
  progresses a skill state.
- **Dependency:** the Event Log's ability to compute hint/reveal-adjacency
  — already flagged OPEN by LDS (§21), inherited here unchanged.

### 7.E — Independent Practice

- **Intent:** support is reduced or absent once the Learning Design
  requires it, and the experience must make the *absence* of support
  legible to the learner, not just to the system.
- **Experience:** the same `TERMINAL_PRACTICE` state, no assistance active,
  no immediately-preceding answer-revealing content of any kind (LDS §7
  Fix 2 / §12).
- **Interaction:** an unaided command submission.
- **State:** `TERMINAL_PRACTICE`.
- **Evidence:** the qualifying event that can move a skill to
  DEMONSTRATED_INDEPENDENT or contribute to CONSOLIDATED's count.
- **Progression:** per LDS §7/§10 exactly.
- **Dependency:** same as 7.D.

**`[EXPERIENCE ARCHITECTURE DECISION]`:** once a skill reaches CONSOLIDATED,
the repeated-error escalation offer stops firing automatically for that
skill (LDS §15's Coach-fading fix) — the experience-level consequence is
that Independent Practice for an already-CONSOLIDATED skill should feel
noticeably quieter than the same skill's first Guided/Independent attempts.
This is a direct, visible symptom of an already-decided mechanic, not a new
one.

### 7.F — Terminal / Operational Practice

- **Intent:** Terminal is the value engine of the product (file 03) — the
  environment must read as an operational tool, never a game or quiz
  interface (file 04's anti-pattern list).
- **Experience:** the Terminal Behavioral Skeleton (file 03) governs every
  single command exchange within this state: Awaiting input → Command
  submitted → Valid/Invalid → (Hint requested) → Completion detected →
  Reset/retry. **This document does not restate or re-derive that
  skeleton — it is file 03's alone, and duplicating it here would violate
  this document's own non-duplication requirement (§10, §27).**
- **Interaction:** command entry; assistance requests; retries.
- **State:** `TERMINAL_PRACTICE` (§8) — the experience-level state that
  *contains* many file-03-owned exchange cycles.
- **Evidence:** per-attempt Recorded/Calculated evidence exactly as LDS
  §6/§7/§21 define it.
- **Progression:** feeds DEMONSTRATED_INDEPENDENT/CONSOLIDATED per skill.
- **Dependency:** §17.

**`[EXPERIENCE ARCHITECTURE DECISION]`:** `TERMINAL_PRACTICE` is the single
experience state that both ordinary drilling and workflow-level chained
practice (LDS §11) occupy — chaining does not warrant its own state, since
nothing about the learner's available actions changes; only the
evidence-interpretation of a sequence of attempts differs (LDS §11's own
still-open correlation question, inherited unchanged, §17).

**A gap found during this document's own adversarial self-review (§23),
fixed in place here:** an earlier draft of this document never gave Speed
Drills an experience home at all. `[EXPERIENCE ARCHITECTURE DECISION]`:
Speed Drills is a timed sub-mode *within* `TERMINAL_PRACTICE` (LDS §17
already calls it "a sub-mode inside Practice") — not a separate state. It
is available only for a skill already at CONSOLIDATED, uses the same command-
entry mechanics as ordinary practice, and differs only in what it computes
(a CPM value, excluded entirely rather than zeroed for a checklist-failing
rep, LDS §17) instead of contributing to skill-state evidence. Any surface
showing a Speed Drills CPM trend must co-display its exclusion rate in the
same view (LDS §17) — an experience-level, not merely a data, requirement.

**A second gap found the same way:** LDS's Simulator Scope Disclosure
(Principle 6.1 — a short reference listing DEIXEN-specific limitations:
one seat per PNR, no child/infant fares, the 2-segment/9-passenger ceiling,
Egypt-only Timatic, `FQN`/`FQR` non-functional, the ancillary family
currently unreachable) had no stated experience home either.
`[EXPERIENCE ARCHITECTURE DECISION]`: this content is reachable as an
on-demand reference from `LEARNING` and from Coach (not a new state) —
consistent with LDS's own description of it as low-cost and disclosure-
only. **This document preserves LDS's own classification of this item as a
`RECOMMENDATION`; giving it an experience home does not upgrade it to a
requirement.**

### 7.G — Scenarios

- **Intent:** scenarios provide operational context and connect isolated
  commands into a recognizable task, satisfying the Scenario
  Differentiation Contract (file 07).
- **Experience:** a bounded task wrapping Terminal, presenting an
  Objective, task Constraints, and scenario-aware Feedback that a plain
  drill does not show (file 07). **This document does not invent the one
  frozen scenario's actual objective, constraints, or narrative content —
  that is curriculum-authoring work, not yet done per file 13. What
  follows is the experience *contract* the content must satisfy, not the
  content itself.**
- **Interaction:** the same command-level interactions as `TERMINAL_
  PRACTICE`, framed by scenario context the learner can see throughout
  (objective statement, constraint reminders where relevant).
- **State:** `SCENARIO_SESSION` (§8) — deliberately distinct from
  `TERMINAL_PRACTICE` because the Scenario Differentiation Contract
  requires state integrity ("no hidden global mutation") and scenario-
  specific evidence linkage that a plain drill attempt does not carry.
- **Evidence:** Scenario-linked Recorded events; TRANSFERRED/CONSOLIDATED
  credit only for skills observably load-bearing to the scenario's
  differentiating condition **and** independent (LDS §7 Fix 4, §18).
- **Progression:** feeds Growth/Readiness's qualitative status, never a
  number, for the frozen slice.
- **Dependency:** the Scenario's own content (objective/constraints/
  acceptance criteria) — `PENDING DECISION` / curriculum-authoring, per
  file 13's own tracking. This document's architecture does not block on
  that content existing; it defines the shape the content must fill.

### 7.H — Assessment

- **Intent:** Assessment must be distinct from ordinary practice exactly
  where the Assessment State Contract (file 07) requires it, and nowhere
  else invented.
- **Experience:** the learner is told, explicitly, that they are now in an
  Assessment attempt — a baseline experiential requirement on its own.
  `[EXPERIENCE ARCHITECTURE DECISION]`: a learner must be able to tell,
  without inference, whether a given Terminal exchange is being scored as
  part of the one owned Assessment record. **This baseline, by itself, is
  not yet what file 07's own disclosure rule requires.** File 07's rule is
  narrower and conditional — "the UI must disclose current-session
  carry-over whenever it's present" — not a general "scoring is active"
  banner: it requires disclosing the carried-over content itself (an
  existing hint count or command history from before this attempt began),
  not only the fact that scoring has started. A session entering Assessment
  with no prior history or hints has nothing to disclose, per file 07's own
  carve-out, and the general "you are being scored" tell above is the only
  disclosure such a session needs.
- **Interaction:** identical command-level mechanics to `TERMINAL_
  PRACTICE`; the assistance ladder and hint-count disclosure remain fully
  active and fully honest (file 07's hint-honesty rule).
- **State:** `TERMINAL_ASSESSMENT` (§8).
- **Evidence:** the frozen slice's one owned Assessment record, evaluated
  under Kane's four-inference framework exactly as LDS §20 states it —
  strongest at Scoring, weak at Generalization, silent at Extrapolation,
  deliberately modest at Implications.
- **Progression:** feeds the one bounded qualitative Growth/Readiness
  status only.
- **Dependency:** whether an in-progress (not yet completed) Assessment
  attempt survives a browser/session close is genuinely unaddressed by
  file 07 or file 03 — flagged in §15/§22 as `REQUIRES IMPLEMENTATION
  VERIFICATION` / `PENDING DECISION`, not assumed either way here.

### 7.I — Feedback / Correction

- **Intent:** the official engine message is always shown verbatim,
  explained alongside, and never replaced (files 05/06, LDS §13).
- **Experience:** immediate, per file 03's Terminal skeleton timing; the
  explanation is authored diagnostic-by-default (names the problem) unless
  deliberately marked corrective (states the fix) — LDS §13's unified rule,
  which this document consumes as given.
- **Interaction:** the learner reads the message, self-corrects or
  requests assistance, and retries.
- **State:** occurs inside whichever state hosts the attempt
  (`TERMINAL_PRACTICE`, `TERMINAL_ASSESSMENT`, or `SCENARIO_SESSION`) —
  Feedback/Correction is not itself a navigable state.
- **Evidence:** corrective-tier feedback sets the independence flag's
  second input to false for the following attempt (LDS §7 Fix 2); it never
  touches the learner-requested-hint counter.
- **Progression:** none directly; it governs whether the *next* attempt
  can progress a skill state.
- **Dependency:** the diagnostic/corrective authoring discipline (LDS §30)
  — a content-authoring dependency, not an experience-architecture one.

**`[EXPERIENCE ARCHITECTURE DECISION]`:** all Coach-authored copy touching
an error, at any tier, in any state, describes what condition is currently
unmet — never framed as a mistake to feel bad about (LDS Principle 7). This
is an experience-level tone constraint this document adds on top of LDS's
content rule, not a new mechanic.

### 7.J — Evidence

- **Intent:** only Recorded and Calculated evidence (file 07's classes) may
  ever be shown as current performance; Illustrative and Planned/
  Unavailable must be labeled as such wherever they appear.
- **Experience:** the learner never sees a number, badge, or status that
  isn't traceable to one of these classes — see §12 for the full
  per-experience table.
- **Interaction:** none directly — Evidence is a consequence of other
  interactions, not itself an action the learner takes (with the one
  documented exception of a manual reset, §7.N).
- **State:** not a navigable state; a cross-cutting property of every
  other state's exit.
- **Evidence:** N/A (this row *is* the evidence layer).
- **Progression:** the direct input to Progression (§7.K).
- **Dependency:** the persistence architecture (file 03: localStorage,
  schema-version field, full reset on mismatch) and the Event Log's four
  fields (file 03) — both already established; this document adds no new
  field.

### 7.K — Progression

- **Intent:** progression reflects capability, never time-spent, clicks, or
  lesson-viewed status alone (file 03 Non-Negotiable Rule #4; LDS
  Principle 4).
- **Experience:** Flight Deck's "next recommended action" (§7.A) is the
  single surface where progression is read, not computed on-screen.
- **Interaction:** the learner accepts or ignores the recommendation;
  ignoring it has no evidence consequence (LDS §23, "Revisit").
- **State:** `ORIENTATION`.
- **Evidence:** a live, render-time projection of underlying evidence,
  never a separately-incremented counter that can drift (LDS §21's
  Evidence Truth vs. UI Progress separation, which this document treats as
  a hard experience-level constraint, not merely an implementation nicety:
  **no cached "progress" value may be displayed if it cannot be
  regenerated from current Recorded/Calculated evidence at query time.**)
- **Progression:** self-referential by definition; feeds Reinforcement
  (§7.L) and Transfer (§7.M) entry points.
- **Dependency:** §17.

### 7.L — Reinforcement / Retention

- **Intent:** previously-verified capability is checked, not assumed, and
  a lapse is distinguished from confirmed retention (LDS §10's three-way
  split: no-decay-observed / not-recently-re-observed / re-demonstrated).
- **Experience:** two distinct triggers with two distinct loci — corrected
  during this document's own adversarial self-review (§23) after an
  earlier draft wrongly described both as surfacing "through Flight
  Deck." (a) **Reactive:** a fresh error on an already-CONSOLIDATED/
  TRANSFERRED skill sets the NEEDS_REINFORCEMENT flag immediately, inside
  whatever state the error occurred in (typically `TERMINAL_PRACTICE`,
  possibly `SCENARIO_SESSION`) — the flag-setting is not routed through
  Flight Deck at all. `[EXPERIENCE ARCHITECTURE DECISION]`: the short
  re-practice prompt itself surfaces at the next natural opportunity —
  inline if the learner is still in ordinary `TERMINAL_PRACTICE`, or via
  Flight Deck's recommendation surface on next visit otherwise. **If the
  triggering error occurred inside `SCENARIO_SESSION` specifically, "next
  natural opportunity" always means the Flight Deck path, never an inline
  interruption of the scenario in progress** — surfacing the prompt
  mid-scenario would risk exactly the "hidden global mutation" the
  Scenario Differentiation Contract (file 07; §7.G, §14 below) exists to
  prevent, for a concern the scenario attempt itself isn't about. LDS
  specifies the flag and the eventual prompt, not this timing choice. (b) **Proactive:**
  an optional, expanding-interval "quick refresher" appears specifically
  via Flight Deck's existing recommendation mechanism once a skill is
  CONSOLIDATED and its interval has elapsed (LDS §24) — this one genuinely is
  Flight-Deck-originated. Declining (b) has no evidence consequence.
- **Interaction:** a short re-practice attempt, full checklist required to
  clear the flag or count as "retention re-demonstrated."
- **State:** re-enters `TERMINAL_PRACTICE` — see §8's note on why this is
  an entry variant, not a new state.
- **Evidence:** an ordinary Recorded event; engaging the prompt is never
  itself evidence of anything (LDS §10 — this document treats this as a
  strict experience-level rule: **the UI may never imply "retained" merely
  because a refresher was offered or opened.**)
- **Progression:** a successful re-attempt clears NEEDS_REINFORCEMENT
  without demotion; repeated failure demotes per LDS §7 Fix 3's graduated
  rule (TRANSFERRED→CONSOLIDATED→DEMONSTRATED_INDEPENDENT).
- **Dependency:** the spaced-retrieval interval remains PROVISIONAL (LDS
  §24, §36) — this document does not assign it a number.

### 7.M — Transfer

- **Intent:** a skill is shown to work in a realistic, changed context —
  restricted to skills the scenario's own acceptance criteria actually
  exercised, and only when independent (LDS §7 Fix 4, §18).
- **Experience:** lived entirely inside `SCENARIO_SESSION` (§7.G); its
  *evidentiary consequence* (a TRANSFERRED state change) is what
  Growth/Readiness later reflects — the dual-locus point already named in
  §5.
- **Interaction:** identical to any other Scenario command exchange; no
  separate "transfer mode" exists.
- **State:** `SCENARIO_SESSION`.
- **Evidence:** Scenario-linked, independent, load-bearing successes only.
- **Progression:** TRANSFERRED status; per Baldwin & Ford's own limitation
  (LDS §18), this can only ever speak to two of the three factors real
  transfer depends on — the real workplace is structurally outside this
  product's reach, and no UI copy may imply otherwise.
- **Dependency:** the one scenario's content (§7.G).

**`[EXPERIENCE ARCHITECTURE DECISION]`:** the transition "Reinforcement →
Transfer," named in this document's own governing brief, is **conditional,
not universal**, and this document does not force a stricter sequencing
than LDS actually supports: a learner can reach TRANSFERRED without ever
passing through NEEDS_REINFORCEMENT, and a reinforcement re-attempt does
not, by itself, unlock or require a Scenario attempt. Where the two do
connect experientially is narrower and stated precisely in §9's transition
catalog (Transition 7).

### 7.N — Failure / Recovery

Covered in full in §15, which distinguishes micro (per-attempt, already
owned by file 03 + LDS) from macro (session-level abandonment and
re-entry, this document's own contribution) failure/recovery — not
repeated here to avoid the exact "restate instead of translate" failure
mode this document's own governing brief warns against (§7).

### 7.O — Continuity / Resume

Covered in full in §16, for the same reason.


---

## 8. State Architecture

A state is cataloged here only if it changes something meaningful about
what the learner can do, what the system observes, or what evidence
becomes possible — per this document's own minimum-justified-complexity
rule (§20, §26). Eight states pass that test for the frozen slice. Four
candidate states were considered and deliberately **not** added; each
rejection is stated at the end of this section rather than left implicit,
because an unstated rejection looks identical to an oversight.

**Boundary note, stated once:** every state below operates one level above
file 03's own Terminal Behavioral Skeleton (Awaiting input → Command
submitted → Valid/Invalid → Hint requested → Completion detected →
Reset/retry). That skeleton governs the moment-to-moment exchange *inside*
`TERMINAL_PRACTICE`, `TERMINAL_ASSESSMENT`, and `SCENARIO_SESSION` alike; it
is not re-specified here, and no state below duplicates it.

### 8.1 `ORIENTATION` (Flight Deck)

| Field | Definition |
|---|---|
| Entry | Session start; return from any other state with no specific destination; explicit navigation. |
| Available Actions | Accept the recommended next action; navigate to any of the other four areas. |
| System Behavior | Reads current evidence and renders one recommendation (§7.K) — computes nothing new. |
| Evidence | None produced. |
| Exit | Accepting the recommendation, or explicit navigation elsewhere. |
| Failure / Recovery | N/A — this state cannot itself fail; if evidence is unavailable (fresh session), it recommends the first Lesson. |
| Dependencies | Evidence-aggregation logic (§17). |

### 8.2 `LEARNING` (Lesson)

| Field | Definition |
|---|---|
| Entry | From `ORIENTATION`'s recommendation, or explicit navigation to Learning/Curriculum. |
| Available Actions | Read; open `GHOST_MODE` if the Lesson includes one; follow `practiceBridge` into `TERMINAL_PRACTICE`. |
| System Behavior | Tracks `completionRule` satisfaction only. |
| Evidence | Lesson completion (not counted toward any skill state, LDS Principle 4). |
| Exit | `practiceBridge` taken (primary path); explicit navigation away (always allowed, LDS §23 "Revisit"). |
| Failure / Recovery | N/A. |
| Dependencies | The Lesson schema (file 03). |

### 8.3 `GHOST_MODE` (Recognition Demonstration)

| Field | Definition |
|---|---|
| Entry | Learner-initiated from `LEARNING`. |
| Available Actions | Play, pause, replay without limit (LDS §16). |
| System Behavior | Steps through the JSON schema (file 06); `reveal` steps pull the live engine's real output, never hand-authored content. |
| Evidence | None — explicitly non-evidentiary; can never advance a skill past INTRODUCED (LDS §7, §12). |
| Exit | Learner closes/returns to `LEARNING`. |
| Failure / Recovery | N/A. |
| Dependencies | None beyond the existing Ghost Mode schema. |

### 8.4 `TERMINAL_PRACTICE`

| Field | Definition |
|---|---|
| Entry | From `LEARNING`'s `practiceBridge` (first/Retrieval attempt, §7.C); from `ORIENTATION`'s recommendation (ordinary continued practice); from a Reinforcement trigger (§7.L, an annotated entry variant, not a separate state); self-corrected return after a `TERMINAL_ASSESSMENT` or `SCENARIO_SESSION` attempt that did not require the formal record. |
| Available Actions | Submit a command; request Nudge / Partial Reveal / Full Reveal (Tier-dependent, LDS §8/§15); retry; reset. |
| System Behavior | File 03's Terminal skeleton per exchange; LDS's checklist evaluation and independence-flag computation per attempt. |
| Evidence | Recorded event + Calculated independence flag + checklist-item satisfaction (LDS §6/§21). |
| Exit | Learner navigates away (always allowed); a Scenario is selected (→ `SCENARIO_SESSION`); a formal Assessment is entered (→ `TERMINAL_ASSESSMENT`). |
| Failure / Recovery | Per §15 (micro level) — file 03's Invalid path plus LDS's feedback/correction rules. |
| Dependencies | §17 (independence-flag and chain-continuity confirmation). |

### 8.5 `TERMINAL_ASSESSMENT`

| Field | Definition |
|---|---|
| Entry | Explicit entry into the frozen slice's one formal Assessment session — the experience must disclose this transition (§7.H); never a silent mode switch. |
| Available Actions | Same as `TERMINAL_PRACTICE`, with full assistance-ladder and hint-disclosure behavior intact. |
| System Behavior | Continuous current-session state (file 07): no history/hint-state wipe on entry; no cross-session score merging; carry-over disclosed whenever present. |
| Evidence | The one owned Assessment record, evaluated per Kane's framework (LDS §20). |
| Exit | Completion of the assessed path, or explicit exit (learner-initiated). |
| Failure / Recovery | Mid-record abandonment behavior — `REQUIRES IMPLEMENTATION VERIFICATION` / `PENDING DECISION` (§15, §22) — not resolved here. |
| Dependencies | Same as `TERMINAL_PRACTICE`, plus the abandonment question above. |

### 8.6 `SCENARIO_SESSION`

| Field | Definition |
|---|---|
| Entry | Explicit selection from Scenario Bank, typically recommended once relevant skills reach CONSOLIDATED. |
| Available Actions | Same command-level actions as `TERMINAL_PRACTICE`, framed by the scenario's Objective/Constraints (content `PENDING DECISION`, §7.G). |
| System Behavior | Scenario Differentiation Contract's state-integrity rule (no hidden global mutation); scenario-aware feedback, not generic command feedback. |
| Evidence | Scenario-linked Recorded events; TRANSFERRED/CONSOLIDATED credit gated by independence + load-bearing use (LDS §7 Fix 4). |
| Exit | Scenario completion (successful or not) or explicit exit. |
| Failure / Recovery | Per §15; a failed scenario attempt does not corrupt state integrity and may be retried per the contract. |
| Dependencies | The scenario's actual content (curriculum authoring, `PENDING DECISION`). |

### 8.7 `GROWTH_READINESS` (Review)

| Field | Definition |
|---|---|
| Entry | Explicit navigation, or a recommendation surfaced from `ORIENTATION` after a meaningful evidence event. |
| Available Actions | Read the one bounded qualitative status (Completed / In Progress / Needs More Practice) for the frozen slice; no drill-down into a numeric score exists (Decision 8A). |
| System Behavior | Reads aggregated Recorded/Calculated evidence via the persistence architecture; never displays Illustrative data as current performance (file 07). |
| Evidence | None produced; consumes evidence only. |
| Exit | Explicit navigation. |
| Failure / Recovery | If no qualifying evidence exists yet, displays that honestly rather than a default/placeholder score. |
| Dependencies | §17. |

### 8.8 `RESET_RECOVERY`

| Field | Definition |
|---|---|
| Entry | Explicit learner-initiated reset action (file 03: "a product requirement, not a developer convenience"). |
| Available Actions | Confirm or cancel the reset. |
| System Behavior | Returns the learner to a clean `ORIENTATION` state; on a persisted-schema-version mismatch, the same full-reset default applies automatically (file 03) rather than attempting a silent migration. |
| Evidence | All prior Recorded/Calculated evidence for this browser/session is cleared — this is the intended behavior, not a bug. |
| Exit | Confirmation → `ORIENTATION`; cancellation → the state the learner was in before. |
| Failure / Recovery | N/A — this state *is* the recovery mechanism for a corrupted or unwanted local state. |
| Dependencies | The persistence architecture's schema-version field (file 03). |

### States considered and rejected

Each is stated because an unstated rejection is indistinguishable from an
oversight (§20's discipline):

1. **A separate "Coach" state.** Rejected — Coach is a cross-cutting
   capability available *within* `LEARNING`, `TERMINAL_PRACTICE`,
   `TERMINAL_ASSESSMENT`, and `SCENARIO_SESSION` (per its five required
   touchpoints, file 06), not a place the learner navigates to. Modeling it
   as a state would imply the learner "enters Coach" and "leaves" it,
   which is not how any of the five touchpoints actually work. See §11.
2. **A separate "Reinforcement" state.** Rejected — both of LDS's
   reinforcement triggers re-enter `TERMINAL_PRACTICE` with an annotated
   entry condition (§7.L, §8.4). No available action, evidence rule, or
   exit condition differs from ordinary practice once inside it.
3. **A separate "Continuity/Resume" state.** Rejected — resuming is a
   property of *how* a learner re-enters any of the eight states above
   (with prior context restored), not a state itself. See §16.
4. **A Customer Service dialogue state machine.** Rejected for this
   document to invent — LDS explicitly scopes its own skill-state model as
   not applying to CS Lessons 1/2/4, and the CS retry/branch model is
   undocumented anywhere in the nine files (LDS §19, §36: `OPEN QUESTION`).
   Inventing one here would be exactly the kind of unsupported architecture
   this document's governing brief forbids (§20, §26). CS Lesson 5's
   technical half already lives inside `TERMINAL_PRACTICE`/`LEARNING`
   under the existing rules (LDS §19's two-event rule); the English-
   response half's own state mechanics are `PENDING DECISION`.


---

## 9. Transition Architecture

The eight transitions named in this document's governing brief (§15),
mapped onto the eight states in §8. Micro-level, within-exchange
transitions (Valid/Invalid/Hint/Reset) remain file 03's alone and are not
restated here.

### Transition 1 — Learning → Practice

| Field | Definition |
|---|---|
| From | `LEARNING` |
| Trigger | The Lesson's `practiceBridge` is taken. |
| Conditions | None beyond the Lesson being open — `practiceBridge` is mandatory on every Lesson (file 03). |
| To | `TERMINAL_PRACTICE`, as a Retrieval-quality (first, unaided) attempt. |
| Evidence Carried | None from `LEARNING` — Ghost Mode/Lesson content is non-evidentiary by design. |
| Learner Expectation | "I've read/watched; now I try it myself." |
| Failure Path | N/A — this transition cannot fail; the learner can always return to `LEARNING`. |

**Correction made this pass:** this transition previously listed
`GHOST_MODE` as an alternate direct source (`LEARNING` "or" `GHOST_MODE`),
which contradicted both §7.C's Retrieval definition (no Ghost Mode replay
immediately preceding the qualifying attempt) and §8.3's own stated exit
(`GHOST_MODE` returns only to `LEARNING`). `GHOST_MODE` is removed as a
direct source here; a learner who has just replayed it returns to
`LEARNING` first, and it is from there — never directly from
`GHOST_MODE` — that a Retrieval-quality attempt can begin. No state or
transition is added by this correction; it removes an edge §8.3 never
actually granted.

### Transition 2 — Practice → Scenario

| Field | Definition |
|---|---|
| From | `TERMINAL_PRACTICE` |
| Trigger | Explicit selection of the one available Scenario, typically recommended once the relevant skill(s) reach CONSOLIDATED. |
| Conditions | None hard-gated by this document; file 07 does not state a mandatory CONSOLIDATED prerequisite for Scenario entry, only that CONSOLIDATED is when it becomes *recommended* — attempting a Scenario earlier is not architecturally prevented, only less likely to succeed. `[EXPERIENCE ARCHITECTURE DECISION]`, flagged for confirmation rather than assumed as a hard gate. |
| To | `SCENARIO_SESSION` |
| Evidence Carried | Per-skill CONSOLIDATED/DEMONSTRATED_INDEPENDENT status (read, not consumed) — informs the recommendation, not a gate enforced by this transition itself. |
| Learner Expectation | "I'm applying what I practiced inside a realistic case now." |
| Failure Path | Learner exits without attempting → returns to `TERMINAL_PRACTICE` or `ORIENTATION`, no evidence consequence. |

### Transition 3 — Practice → Assessment

| Field | Definition |
|---|---|
| From | `TERMINAL_PRACTICE` |
| Trigger | Explicit entry into the frozen slice's one formal Assessment. |
| Conditions | None stated as mandatory by file 07 beyond the Assessment State Contract's own carry-over disclosure rule. |
| To | `TERMINAL_ASSESSMENT` |
| Evidence Carried | Current-session command history and hint state are **not** wiped on entry (file 07); prior sessions' persisted records are **never** merged into the current score. |
| Learner Expectation | Explicit disclosure that scoring is now active, per §7.H; when carry-over is present, its specific content is disclosed too, not only the fact that scoring started. |
| Failure Path | Learner exits before completion → §15/§22's open abandonment question applies. |

### Transition 4 — Assessment → Evidence

| Field | Definition |
|---|---|
| From | `TERMINAL_ASSESSMENT` |
| Trigger | Completion of the assessed path. |
| Conditions | Full-checklist evaluation per attempt, exactly as in ordinary practice. |
| To | Persisted evidence (not a navigable state) — the learner typically lands back in `ORIENTATION` or `GROWTH_READINESS`. |
| Evidence Carried | The one owned Assessment record, plus its Kane-framework interpretation limits (LDS §20). |
| Learner Expectation | Confirmation that the attempt was recorded; no overclaiming language ("mastered," "certified") per LDS Principle 6. |
| Failure Path | N/A at this point — evidence is recorded whether the attempt succeeded or not; the record's *content* reflects what happened, it doesn't fail to exist. |

### Transition 5 — Evidence → Progression

| Field | Definition |
|---|---|
| From | Persisted evidence |
| Trigger | Any new Recorded/Calculated evidence write. |
| Conditions | None — this is a live projection (§7.K), not a batch/scheduled process. |
| To | `ORIENTATION`'s recommendation output (read at next render). |
| Evidence Carried | Whatever was just written — no separate "progress" value is cached. |
| Learner Expectation | The next time Flight Deck is viewed, the recommendation reflects what just happened. |
| Failure Path | N/A. |

### Transition 6 — Progression → Reinforcement

**Split into two sub-transitions during this document's own adversarial
self-review (§23): an earlier draft gave both triggers a single "From:
`ORIENTATION`" row, which is only true of one of them.**

**6a — Reactive (in-place, does not pass through `ORIENTATION`):**

| Field | Definition |
|---|---|
| From | Whatever state the qualifying error occurred in — typically `TERMINAL_PRACTICE`, possibly `SCENARIO_SESSION`. |
| Trigger | A fresh error recurs on an already-CONSOLIDATED/TRANSFERRED skill. |
| Conditions | An actual failed attempt on that specific skill. |
| To | `TERMINAL_PRACTICE`, entered as a Reinforcement variant (§8.4, §7.L) — immediately, or at the next natural opportunity if the learner is mid-`SCENARIO_SESSION`. |
| Evidence Carried | The NEEDS_REINFORCEMENT flag. |
| Learner Expectation | A short, low-stakes re-practice framing — not a full lesson return, not punitive. |
| Failure Path | Repeated reinforcement failure → graduated demotion (LDS §7 Fix 3), still within `TERMINAL_PRACTICE`. |

**6b — Proactive (genuinely Flight-Deck-originated):**

| Field | Definition |
|---|---|
| From | `ORIENTATION` |
| Trigger | An expanding interval elapses since a CONSOLIDATED skill's last qualifying success (LDS §24). |
| Conditions | The interval itself is PROVISIONAL, not assigned a number by this document. |
| To | `TERMINAL_PRACTICE`, entered as a Reinforcement variant, only if the learner accepts the offer. |
| Evidence Carried | Nothing — declining has no evidence consequence. |
| Learner Expectation | An optional, low-stakes "quick refresher," clearly skippable. |
| Failure Path | Declining is not a failure path; a declined offer may recur at the next interval. |

### Transition 7 — Reinforcement → Transfer

| Field | Definition |
|---|---|
| From | `TERMINAL_PRACTICE` (Reinforcement variant) |
| Trigger | **Conditional, not automatic** (§7.M) — a successful reinforcement re-attempt does not itself unlock or require a Scenario attempt. This transition only applies when a learner, having just re-practiced, separately chooses to attempt the one available Scenario afterward. |
| Conditions | The Scenario's own acceptance criteria must actually exercise the reinforced skill, and that use must be independent (LDS §7 Fix 4). |
| To | `SCENARIO_SESSION` |
| Evidence Carried | The skill's current CONSOLIDATED status (a prerequisite for the credit, not for entry — see Transition 2). |
| Learner Expectation | None specific to having just reinforced — from the learner's point of view this is an ordinary Scenario attempt (Transition 2), not a distinct guided sequence. |
| Failure Path | Same as Transition 2. |

**Note on why Transition 7 is stated this way:** forcing a strict
Reinforcement-always-precedes-Transfer sequence would misrepresent LDS's
actual model, where a learner can reach TRANSFERRED having never entered
NEEDS_REINFORCEMENT at all. This document names the transition because its
governing brief asks for it, but does not manufacture a dependency LDS
does not support — consistent with the Operating Constitution's rule
against synthesizing structure evidence doesn't justify.

### Transition 8 — Failure → Recovery → Re-entry

Covered at both the micro level (file 03 + LDS, not restated) and the
macro level (§15) — see §15 for the full treatment, including the two
genuinely open sub-cases (mid-Assessment abandonment; `XE`'s unsupported-
element-type behavior).


---

## 10. Practice Progression Ladder

This document's governing brief names a generic five-step ladder (Guided →
Supported → Reduced Support → Independent → Assessment). **`[EXPERIENCE
ARCHITECTURE DECISION]`: this ladder is a presentation lens over LDS's
already-decided mechanics, not a second, competing progression model.**
Introducing new named stages here that don't map onto LDS's actual states
would be duplicated authority (a specific risk this document's own
governing brief names in §27). The mapping:

| Generic step | LDS mechanic it corresponds to | Notes |
|---|---|---|
| Guided | `GHOST_MODE` demonstration | Recognition-level; never evidentiary (LDS §12, §16). |
| Supported | Nudge active (LDS §15) | Names the general error category only; diagnostic, never disqualifies the *next* success from independence on its own. |
| Reduced Support | Partial Reveal active, for Tier 3 skills (LDS §8) | Names *which* checklist item is unmet without stating the fix — the graduated middle step LDS added to close its own P2-7 finding. |
| Independent | An unaided attempt satisfying the full checklist (LDS §7) | DEMONSTRATED_INDEPENDENT on first qualifying success; CONSOLIDATED at the interim default of 2. |
| Assessment | `TERMINAL_ASSESSMENT` (§8.5) | The formal, disclosed record — mechanically identical to an independent attempt, distinguished only by the disclosure and evidence-ownership rules of file 07. |

**Correction made this pass:** the table previously listed Partial Reveal
under both Supported and Reduced Support, which left it unclear whether
the two rows were meant to be the same rung or genuinely different ones.
They are different: Supported is Nudge only, Reduced Support is Partial
Reveal only, and the progression from one to the other is exactly the
fading step LDS §8/§15 describe.

**`[EXPERIENCE ARCHITECTURE DECISION]`:** the experience must never present
these five steps as a single linear checklist a learner "completes in
order" for a given skill — LDS's actual model allows re-entry (a CONSOLIDATED
skill can return to Guided-equivalent content via Ghost Mode replay without
penalty), and Full Reveal (not named as a separate rung above, since it is
the deepest content a learner can request from either Supported or Reduced
Support, not a further rung toward independence) remains available at any
point a learner requests it. The
ladder is a description of typical progression, not a gate sequence the
UI enforces mechanically.

**Do not create a permanent help loop (per this document's own governing
brief §16):** satisfied by two already-decided mechanics working together:
the exclusion rule (LDS §7 Fix 2) means repeatedly requesting Full Reveal
never produces a qualifying success, so a learner cannot "grind" toward
CONSOLIDATED via assistance; and the CONSOLIDATED-gated escalation suppression
(LDS §15) means the system stops *offering* the deeper help path once a
skill no longer needs it. This document adds no new anti-dependency
mechanism beyond citing these two.

---

## 11. Coach Experience Boundary

Coach is part of the learning experience but never a substitute for
learner performance (this document's governing brief §17, consistent with
file 06's behavioral contract).

| Question | Answer |
|---|---|
| When does it appear? | On request, at any of the five required touchpoints (Learning, Terminal/Practice, Scenario, Assessment, Growth/Readiness — file 06); automatically only for the repeated-error escalation *offer* (LDS §13), which is itself declinable and suppressed once a skill is CONSOLIDATED absent NEEDS_REINFORCEMENT (LDS §15). |
| When is it silent? | By default, at all other times — Coach is learner-initiated, never a constantly-visible panel (this document's governing brief §17's "when it is silent" requirement; consistent with file 04's anti-decoration principle). |
| What support is appropriate? | Content bound to the learner's actual state (file 06: actions, errors, hints used, assessment state, available evidence) — never a static generic help panel. |
| What can it reveal? | Nudge (category only), Partial Reveal (which checklist item, Tier 3 only), Full Reveal (the specific fix) — LDS §15's three tiers, one counter. Coach never shortens or omits the verbatim official error message at any tier (files 05/06). |
| How does support affect evidence? | Corrective-tier content (Full Reveal, or a corrective ordinary error explanation) sets the independence flag's second input to false for the following attempt; diagnostic-tier content (Nudge, Partial Reveal) does not (LDS §7 Fix 2, §13). |
| How does support fade? | One narrow, specific instance only: the repeated-error escalation offer stops firing automatically once a skill is CONSOLIDATED, absent NEEDS_REINFORCEMENT (LDS §15). LDS is explicit that *general* Coach-proactivity fading beyond this one instance remains unaddressed — this document does not invent a broader fading mechanism to make the architecture look more complete than LDS actually supports. |

**`[EXPERIENCE ARCHITECTURE DECISION]`:** Coach's layout — a persistent
global element versus a component embedded per page — is explicitly OPEN
(file 06/07), and this document does not resolve it. What this document
does add is the constraint that whichever layout is chosen must satisfy
every row in the table above; layout is free, behavior is not.

**No new assistance metric is introduced** (per this document's governing
brief §17's explicit caution) — the single canonical hint counter (file 03)
and the independence flag (LDS §7 Fix 2) are the only two mechanisms
referenced above; nothing here adds a third.

---

## 12. Evidence Integrity Framework

For every major evidence-producing experience, the same four questions
this document's governing brief requires (§18): what actually happened
(Observation), what can legitimately be stored or derived (Evidence), what
that evidence means (Interpretation), and what must not be inferred (Claim
Boundary).

| Experience | Observation | Evidence | Interpretation | Claim Boundary |
|---|---|---|---|---|
| `TERMINAL_PRACTICE` attempt, independent, full checklist | Learner submitted a command; checklist evaluated | Recorded event (type/command/result/timestamp) + Calculated independence flag + checklist-item satisfaction | Contributes toward DEMONSTRATED_INDEPENDENT / CONSOLIDATED's count | A single success ≠ competence; any assisted or answer-adjacent success is excluded from independence, regardless of how clean the resulting command looked |
| `TERMINAL_ASSESSMENT` record | The frozen slice's one owned attempt | Same mechanics as practice, plus file 07's disclosure/carry-over rules | Supported at Kane's Scoring inference (design-level, pending Event Log confirmation); weak at Generalization; silent at Extrapolation | Never "assessed" implies broad competence; never implies real-Amadeus performance |
| `SCENARIO_SESSION` attempt | The one frozen scenario, attempted | Scenario-linked Recorded event(s), Scenario Differentiation Contract fields | May credit TRANSFERRED/CONSOLIDATED only for skills observably load-bearing **and** independent | A scenario "passed" ≠ transfer credit for every skill incidentally used inside it; one scenario ≠ generalized transfer |
| `GHOST_MODE` completion | Learner watched/replayed a demonstration | None persisted as competence evidence | May inform INTRODUCED only | Never counted toward DEMONSTRATED_INDEPENDENT / CONSOLIDATED / TRANSFERRED; unlimited replay is evidence-safe but carries an open, unresolved confidence-reality-gap hypothesis (LDS §16) |
| Reinforcement re-attempt | A fresh attempt after a reactive or proactive trigger | An ordinary Recorded event, no special evidence category | A full-checklist success is "retention re-demonstrated" (LDS §10); engagement alone is not | The UI never implies retention merely because a refresher was offered or opened |
| Speed Drills rep | A timed attempt on an already-CONSOLIDATED skill | CPM value if checklist-passing; **excluded entirely** (not zeroed) if failing | A personal speed trend only | Never feeds Growth/Readiness or any competence/CONSOLIDATED determination; any CPM trend display must co-display its exclusion rate (LDS §17) |
| CS Anger Meter movement | A dialogue choice was made; the meter moved | An Event is logged | **Illustrative only** (file 07's own class) | Never shown as measured CS competence or proficiency; no choice-quality rubric currently exists (LDS §19) |

**`[EXPERIENCE ARCHITECTURE DECISION]`:** no surface anywhere in the
product may display mastery, readiness, retention, or transfer language
stronger than the row above supports for that specific experience — this
is the direct, table-form enforcement of this document's governing brief
§18's prohibition, and it is the single most load-bearing table in this
document, since every other integrity section (§13–§15) refers back to it
rather than re-deriving its own version.

---

## 13. Progression Integrity

Progression must represent meaningful development, never page completion,
clicks, time, activity counts, or superficial interaction (this document's
governing brief §19, restating file 03 Non-Negotiable Rule #4 and LDS
Principle 4 — cited together here because all three already agree, and
stating that agreement once is more useful than three separate
citations).

**`[EXPERIENCE ARCHITECTURE DECISION]`:** the experience-level consequence
of this rule is that `ORIENTATION`'s recommendation engine (§7.A, §7.K) may
read only from Recorded/Calculated evidence (§12's table) — never from a
Lesson-viewed flag, a page-visit count, or elapsed time. This document does
not introduce a new mastery framework to make the architecture look more
sophisticated (explicitly rejected by its own governing brief §19); it
reuses LDS's five-state skill model and file 07's evidence classes
exactly as they already stand.

**Where this document adds something LDS does not already state:** LDS
defines the *evidence logic*; this document adds the *display discipline*
that logic must be paired with — namely, that a progression surface
showing "Completed / In Progress / Needs More Practice" for the frozen
slice (Decision 8A) must never be rendered as a percentage, progress bar
proportional to lesson count, or numeric score, since none of those exist
as approved evidence for this slice. This is a UI-honesty constraint, not a
new evidence mechanism.

---

## 14. Scenario Integrity

Scenarios must be more than cosmetic wrappers (this document's governing
brief §20). The Scenario Differentiation Contract (file 07) already
requires an owned Objective, task Constraints, explicit Expected behavior/
acceptance criteria, scenario-aware Feedback, Assessment linkage, Evidence
linkage, and state integrity — this document does not restate that
contract, it defines the experience that must satisfy it:

| Contract element (file 07) | Experience-level requirement this document adds |
|---|---|
| Objective | Visible to the learner throughout the session, not only at entry — a learner mid-scenario must be able to re-check what they're solving for. |
| Constraints | Surfaced where relevant to the current step, not dumped as a wall of rules at entry. |
| Expected behavior / acceptance criteria | Never shown to the learner as an answer key — the learner experiences the *task*, not the grading rubric. |
| Scenario-aware Feedback | Must read differently from `TERMINAL_PRACTICE`'s generic command feedback (the contract's own requirement) — an experience-level tell that the learner is inside a realistic case, not a drill. |
| Assessment / Evidence linkage | Handled per §12's table; no separate scenario-specific evidence class is introduced. |
| State integrity | No action inside `SCENARIO_SESSION` may silently mutate evidence belonging to an unrelated skill or a different state. |

**This document does not invent the one frozen scenario's actual content**
(objective text, specific constraints, narrative framing) — per its
governing brief §20's explicit prohibition on inventing domain behavior to
enrich a scenario, and because that content is curriculum-authoring work
tracked as `PENDING DECISION` in file 13, not experience architecture. What
is architected here is the shape the content must arrive in, and the
experience rules it must obey once it exists.


---

## 15. Failure / Recovery Integrity

Treated at two levels, deliberately kept separate because they have
different owners and different degrees of resolution.

### 15.1 Micro-level (per-attempt) — already owned, cited not re-derived

Detection → Feedback → Understanding → Correction → Retry → Return toward
independent performance (this document's governing brief §21's own chain),
mapped onto already-established mechanics:

| Step | Owning mechanic |
|---|---|
| Detection | File 03's Terminal skeleton (Valid/Invalid dispatch). |
| Feedback | File 05/06's verbatim-message rule + LDS §13's diagnostic/corrective split. |
| Understanding | Coach's diagnostic content, framed as unmet-condition information, never as a mistake to feel bad about (LDS Principle 7). |
| Correction | The learner's own retry, or an assistance-ladder request (LDS §15). |
| Retry | File 03's Reset/retry Terminal state. |
| Return toward independent performance | LDS §7 Fix 2's exclusion rule — a corrected or assisted retry cannot wrongly count as independent. |

This document invents nothing new here; it confirms the chain is already
fully covered and cross-references rather than duplicating it.

**Two genuinely unresolved dependencies inherited, not invented, at this
level:**

1. **`XE` against an unsupported element type** — file 05 documents that
   `XE` cannot individually cancel SSR, mobile, email, remarks, OSI,
   tickets, or seat assignment, but not what the system actually *does*
   when attempted against one of these. LDS already flags this as
   `UNKNOWN` (§14, §36); this document does not guess an error-recovery
   experience for a behavior nobody has verified — `REQUIRES
   IMPLEMENTATION VERIFICATION`.
2. **Known Issue #7's mitigation choice** — LDS §14 defines two acceptable
   resolutions ((a) an implementation-confirmed accurate pre-completion
   numbering view, or (b) sequencing `XE` practice to occur only after
   `ER`/`ET` then `RT`) but does not choose between them. `[EXPERIENCE
   ARCHITECTURE DECISION]`: pending owner confirmation, this document uses
   (b) as a provisional, temporary sequencing fallback for any Tier 3
   practice referencing a PNR element by number, since (b) requires no
   unconfirmed capability and (a) does — **this is a safe placeholder while
   the question is open, not an adopted product/architecture decision**
   (§22 tracks it as `PENDING DECISION` for exactly this reason). If (a) is
   later confirmed available, the experience may show live numbering
   instead; this document does not pick a winner, it picks a provisional
   fallback that doesn't depend on an unconfirmed capability and carries no
   authority beyond that.

### 15.2 Macro-level (session/interruption) — this document's own contribution

Confusion, help requests, interruption, abandonment, and re-entry (this
document's governing brief §13.N) at the level of *leaving and returning*
to the product, not a single command exchange:

| Scenario | Recovery path |
|---|---|
| Learner closes the browser mid-`LEARNING` | Persisted Lesson-position data (if any) restores on return via `CONTINUITY` (§16); no evidence consequence either way, since Lesson viewing is non-evidentiary. |
| Learner closes the browser mid-`TERMINAL_PRACTICE` | Any completed attempts before closing are already Recorded; the in-progress (uncompleted) command line itself is not evidence and is not required to survive — the learner simply resumes at the same skill. |
| Learner closes the browser mid-`TERMINAL_ASSESSMENT` | **`REQUIRES IMPLEMENTATION VERIFICATION` / `PENDING DECISION` — genuinely open.** File 07's Assessment State Contract addresses continuous *current-session* state and cross-session merge prohibition, but does not state whether an in-progress, not-yet-completed Assessment attempt survives a same-device browser close (where localStorage would technically persist) or is discarded on return. This document does not assume either answer; both are defensible and the choice materially affects the learner's experience of what "current session" means. |
| Learner closes the browser mid-`SCENARIO_SESSION` | Per the Scenario Differentiation Contract's state-integrity rule, no partial mutation may corrupt other evidence; whether the scenario attempt itself resumes or restarts on return is the same class of question as the Assessment case above and is left open for the same reason — `PENDING DECISION`. |
| Learner abandons after repeated failure (frustration, not a technical interruption) | Handled by existing mechanics, not a new one: the escalation offer (LDS §13) is available before abandonment; on return, `ORIENTATION`'s recommendation reflects the unresolved skill honestly, never hiding that a skill is still short of DEMONSTRATED_INDEPENDENT. |

**`[EXPERIENCE ARCHITECTURE DECISION]`:** the two `PENDING DECISION` rows
above are named explicitly, rather than silently defaulted to "resumes
exactly where it left off" or "always restarts," because both defaults
carry real consequences (resuming risks stale carry-over disclosure being
wrong; restarting risks losing a learner's legitimate progress) and neither
is currently justified by an existing rule. This is exactly the kind of
gap this document's governing brief requires be preserved, not guessed
past (§28, §37).

---

## 16. Continuity / Resume Architecture

**`[HISTORICAL]` input, not a locked pattern:** file 04 records that an
earlier implementation actually built and had Karim approve a "continue
where you left off" resume card (badge, ring animation, level name, "N of
M" subtext, single Continue action). This is real prior art informing the
*functional* requirement below; it is not a visual specification this
document adopts, since Design Execution remains open (file 04/07).

**Functional requirement (`[EXPERIENCE ARCHITECTURE DECISION]`), independent
of visual form:** on return to the product, the following must be
restorable where they exist:

- Last Lesson position (`LEARNING`).
- Which skill was under active practice (`TERMINAL_PRACTICE`).
- Scenario state, in-progress or completed (`SCENARIO_SESSION`) — subject
  to §15's open in-progress question.
- Assessment state — subject to §15's open in-progress question.
- All Recorded/Calculated evidence and progression state (always restored;
  this is simply the persistence architecture already working as
  designed, file 03).
- Reinforcement scheduling (the spaced-retrieval interval's elapsed time,
  LDS §24).

**What this document does not invent:** any persistence mechanism beyond
what file 03 already establishes (localStorage, schema-version field, full
reset on mismatch, no login, no cross-device sync at this stage). A
"continue where you left off" experience is a **read** of already-persisted
state at `ORIENTATION`, not a new storage capability.

---

## 17. Event / Storage Dependencies

This document does not restate LDS §21/§29's full implementation-
dependency table — doing so would be duplicated authority (§27). What
follows are only the dependencies this experience architecture surfaces
*beyond* what LDS already tracks, plus explicit pointers to the ones it
inherits unchanged.

**Inherited unchanged from LDS (cited, not repeated in full):**

- Whether the Event Log's timestamp granularity supports the independence
  flag's two inputs (hint/reveal-adjacency and corrective-feedback-
  adjacency) — `REQUIRES IMPLEMENTATION VERIFICATION`, LDS §21's own
  highest-priority open item. This document's Feedback/Correction (§7.I)
  and Guided/Independent Practice (§7.D/E) experiences are directly
  contingent on this resolving favorably.
- Whether chain-sequence continuity for workflow-level practice is
  reconstructable from the existing four fields or needs a minimal
  correlation identifier — `REQUIRES IMPLEMENTATION VERIFICATION`, LDS §11.
  This document's treatment of chained practice as occurring inside the
  same `TERMINAL_PRACTICE` state (§7.F) does not depend on the answer, but
  whether the *evidence* produced is trustworthy does.

**New to this document, surfaced by the experience-level analysis in §15:**

1. **Session-boundary definition for Assessment/Scenario continuity.**
   Neither file 07 nor file 03 states whether "current session" (as used
   in the Assessment State Contract) means "since the browser was last
   opened," "since localStorage was last cleared," or something else. This
   matters experientially because it determines what a learner is told on
   return (§15.2). `PENDING DECISION` / `REQUIRES IMPLEMENTATION
   VERIFICATION`.
2. **Reinforcement interval timekeeping.** LDS's spaced-retrieval prompt
   (§24) requires knowing elapsed time since a skill's last qualifying
   success — this is computable from existing Event Log timestamps per
   LDS's own claim, and this document finds no reason to doubt that claim
   specifically (unlike the two adjacency questions above, which LDS
   itself already flags as unconfirmed). Stated here only to confirm no
   *new* dependency is being introduced by this document's treatment of
   Reinforcement as a Flight Deck-surfaced entry variant (§7.L).

**What this document explicitly does not do, per its own governing brief
§23:** no schema, API, storage engine, or database structure is proposed
anywhere above. Every dependency is stated as a required *behavior*, with
its resolution owner named, not designed.

---

## 18. Mobile / Desktop Experience Architecture

Respects the current mobile-first-but-not-desktop-secondary direction
(file 03) and the responsive density baseline (file 04: 320/360/390/430px
mobile, 768/1024/1280–1440px tablet/desktop). This document stays at
experience-architecture level throughout — no CSS, no pixel specification.

| Consideration | Experience implication |
|---|---|
| Terminal command input | On any viewport, Terminal's required workspace is never sacrificed for density elsewhere (file 04) — on mobile this means Terminal input must remain full-width and unobstructed by default. |
| Coach visibility | `[EXPERIENCE ARCHITECTURE DECISION]`: on mobile viewports, Coach content defaults to collapsed/on-demand rather than persistently visible, since a persistent panel would cost real Terminal workspace on a narrow screen — this constrains whichever layout choice file 06/07 eventually settles (global vs. per-page), it does not resolve that choice. |
| Desktop workspace | Desktop's extra width may support Terminal, Coach, and reference content side-by-side (file 04's "richer simultaneous context" allowance) — this document treats that as permitted, not required, since Coach layout itself remains open. |
| Touch vs. keyboard | Terminal is a command-line simulation; on touch devices the on-screen keyboard's occlusion of the Terminal history is a real interaction cost the design phase must account for, but this document does not specify a solution (that is visual/interaction design's job, §19). |
| Information density | Growth/Readiness and other dense surfaces should use desktop's extra width for genuine workspace density, not decoration (file 04) — mobile should be organized compactness, not a shrunk desktop layout. |
| Task sequencing | No experience state in §8 requires a different *sequence* of states on mobile versus desktop — the difference is in how much of a state's content is visible at once, not which states exist or how they connect. |

---

## 19. Visual Design Boundary

This document defines what the later design phase must be able to
consume, per its own governing brief §25 — hierarchy, purpose, interaction
relationships, information priority, state, transition, experience
responsibility, and constraints. It does not define, and explicitly
defers:

- Brand identity, final color palette, typography system — Design
  Execution, open per file 04/07, owned by the later Claude Design phase.
- Pixel-level layout, decorative styling, final visual treatment — same.
- Logo/wordmark/naming — explicitly open per file 03/13, Karim's to lead.

**What this document hands to that phase:** the eight-state catalog (§8)
as the set of experiences needing visual form; the transition catalog (§9)
as the navigation/flow model; §12's evidence table as the display-honesty
constraints any visual treatment must respect (no state may visually imply
more certainty than its Claim Boundary allows); §11's Coach table as the
behavioral contract any Coach visual treatment must satisfy regardless of
layout; and §18's mobile/desktop implications as functional (not
aesthetic) constraints.

Nothing above is "already locked by current canonical decisions" in the
sense that would exempt it from this deferral (this document's governing
brief §25's own exception clause) — Design Positioning (professional/
operational register) is closed, but this document does not rely on that
closure to make any visual claim; it only relies on it to justify keeping
scenario/error/Coach *tone* professional rather than playful (already
stated in §7.I, §14), which is a content/tone constraint, not a visual one.


---

## 20. Minimum Justified Complexity Ledger

Per this document's governing brief §26, every mechanism above was tested
against: is it required by Learning Design? by the product? by experience
coherence? is the problem real? is it justified by evidence or an explicit
decision? can the same goal be achieved more simply? Mechanisms that failed
this test are listed here as **rejected**, not silently omitted — an
absent mechanism and a considered-and-rejected one look identical unless
the rejection is recorded.

| Rejected mechanism | Why it was considered | Why it was rejected |
|---|---|---|
| A ninth or tenth experience state (e.g., separate states for "Nudge active," "Full Reveal active," or "chained practice") | Assistance depth and chaining are real, decided mechanics (LDS §8, §11, §15) | Each is an *attribute* of an attempt within `TERMINAL_PRACTICE`, not a different place the learner is — adding a state would duplicate LDS's own tiering without changing any available action, evidence rule, or exit condition |
| A dedicated "Coach" state | Coach has five required touchpoints and its own behavioral contract (file 06) | Coach is available *within* other states, never a destination — see §8's rejection list |
| A dedicated "Reinforcement" or "Continuity" state | Both are named coverage areas in this document's own governing brief (§13.L, §13.O) | Both are entry-condition variants or read-time restorations of existing states, not new places with new available actions |
| A CS dialogue state machine | Lesson 5 and the CS track exist and need *some* experience treatment | The retry/branch model is genuinely undocumented (LDS §19, §36); inventing one would be unsupported architecture, not translation |
| A composite "difficulty" or "readiness" score surfaced anywhere in this document | Would make the architecture look more complete | Directly contradicts the Evidence & Readiness Contract's ban on unapproved formulas (file 07) and LDS §10/§25's explicit rejection of the same |
| A new assistance metric beyond the single hint counter and the independence flag | Might seem to give the Coach section more to work with | This document's own governing brief §17 explicitly forbids this absent clear justification; none exists |
| An adaptive/algorithmic sequencing engine for Reinforcement intervals or Scenario recommendation | Could make Progression (§7.K) feel more sophisticated | Contradicts Platform Direction's anti-premature-infrastructure principle (file 03) and LDS's own rejection of the same (§11, §28) |
| A new persistence mechanism for cross-device continuity | Continuity/Resume (§16) might seem to want it | Explicitly out of scope per Platform Direction (file 03: no login, no cross-device sync at this stage) |
| Branching narrative states for the one frozen Scenario | Might make Scenario Integrity (§14) feel richer | The frozen slice authorizes one scenario, not a branching set (Decision 8A); content not yet authored regardless |

No mechanism above was rejected because it was "too complex" in the
abstract — each was rejected because a specific existing rule already
forbids it, or because a simpler existing mechanic already covers the same
need. This is the distinction this document's governing brief draws in
§31 (Defect vs. Preference) and §26 (Minimum Justified Complexity)
together, applied consistently.

---

## 21. Cross-File Consistency Audit

Explicit comparison against every file named in this document's own
governing brief §27, checking for conflicting scope, contradictory learner
flows, duplicated authority, inconsistent terminology, unsupported Amadeus
assumptions, accidental product redesign, inconsistent evidence logic,
conflicting Coach behavior, incorrect state assumptions, premature visual
commitments, and unnecessary architecture.

| File | Consistency check | Result |
|---|---|---|
| 00 — Knowledge Consolidation Plan | Does this document rely on anything the Plan flags as unsupplied/unverifiable? | No — §3 explicitly inherits the same "not supplied" status for the arbitration record, SME brief, Scenario Bank review, and the missing React codebase; nothing here assumes their contents. |
| 03 — Product & Architecture | Five-area IA preserved? Terminal centrality preserved? Persistence architecture respected? | Yes on all three — §6, §8, §16, §17. No sixth area introduced. No new persistence mechanism proposed. |
| 04 — Design System | Design Positioning respected? Design Execution left open? Accessibility baseline referenced where relevant? | Yes — §19 explicitly defers Execution; §18 references the responsive breakpoints without adding new ones; accessibility is not separately re-litigated here since no visual/interaction commitment is made that would trigger it. |
| 05 — Amadeus Engine Reference | Any invented command behavior? | No — §15 explicitly marks `XE`'s unsupported-element-type behavior `REQUIRES IMPLEMENTATION VERIFICATION` rather than guessing; Known Issue #7 is treated exactly as file 05/LDS already describe it. |
| 06 — Curriculum & Coach | Coach's five touchpoints preserved? Ghost Mode/Speed Drills mechanics preserved? CS track scope respected? | Yes — §11's table maps directly onto file 06's contract; §8.3 and §12's table preserve Ghost Mode's non-evidentiary status and Speed Drills' exclusion rule without alteration; §8's rejection list explicitly declines to invent CS state mechanics. |
| 07 — Decisions & Current State | Evidence classes, Assessment State Contract, Scenario Differentiation Contract all respected without modification? | Yes — §12's table uses the four evidence classes exactly as defined; §8.5/§9 Transition 3 use the Assessment State Contract's own language; §14 uses the Scenario Differentiation Contract's own required elements without adding or removing any. |
| 08 — AI Working Rules & Dev Process | Terminology discipline respected? | Corrected, not merely respected — see §1's stated fix of the governing brief's own "Reminal" usage. |
| 13 — Decision Resolution Register | Any item this register calls OPEN treated here as if it were closed? | No — Design Execution, Naming, Coach layout ownership, the CS rubric, the curriculum-structure question, and all SME/domain items remain exactly as open as file 13 leaves them; this document adds no premature closure. |
| 14 — Sufficiency Audit | Any historical/superseded material (the archived `UI_GUIDELINES.md`/`DESIGN_SYSTEM.md` content, the old phase numbering, the old fixed-screen-number references) reintroduced? | No — none of that material is referenced anywhere above. |
| Learning Design Specification | Any skill-state, assistance-tier, checklist, or evidence-class rule restated with a different meaning than LDS gives it? | No instance found on review — every LDS citation above (§7.C–M, §10–13, §17) uses LDS's own terms and numbers (including its PROVISIONAL defaults) without alteration. |
| Master Execution Roadmap | Does the pipeline cited in §5 still match the Roadmap's own Mission statement? Does §17's Event Log caveat still match the Roadmap's own gating? | Yes on both, re-checked against the Roadmap's current revision — the twelve-stage pipeline is unchanged from what §5 cites, and the Roadmap now names an explicit Evidence/State Confirmation Gate before implementation, which is the same unconfirmed dependency §17 and §21 (LDS row above) already treat as open. No update to this document was required by that revision. |

**No upstream file required a change as a result of authoring this
document.** Where a genuine gap was found (the mid-session-abandonment
questions, §15/§17/§22), it is recorded as an open item pointing at the
relevant file's silence — per this document's governing brief §27, this is
surfaced explicitly rather than "silently fixed" by editing file 03 or 07
directly, which this document is not authorized to do (§36).

---

## 22. Open Items Register

Every material item this document could not safely resolve, using the five
mandated statuses verbatim. Items already tracked in file 13 are cited by
reference, not re-argued; only their *experience-level* consequence is
restated here.

| # | Item | Status | Owner | Why it matters experientially |
|---|---|---|---|---|
| 1 | Whether an in-progress `TERMINAL_ASSESSMENT` attempt survives a browser/session close, or resets | `PENDING DECISION` / `REQUIRES IMPLEMENTATION VERIFICATION` | Product + engineering | Determines what §15.2/§9 Transition 3 tell the learner on return; two defensible answers exist, neither currently justified |
| 2 | Whether an in-progress `SCENARIO_SESSION` attempt survives the same interruption | `PENDING DECISION` / `REQUIRES IMPLEMENTATION VERIFICATION` | Product + engineering | Same class of gap as #1, applied to Scenario |
| 3 | Session-boundary definition underlying both of the above | `REQUIRES IMPLEMENTATION VERIFICATION` | Engineering | A prerequisite to resolving #1 and #2 coherently rather than independently |
| 4 | Event Log timestamp granularity for the independence flag's two inputs | `REQUIRES IMPLEMENTATION VERIFICATION` | Delegated evidence/schema pass (inherited from LDS §21) | Every Guided/Independent Practice and Feedback/Correction experience (§7.D/E/I) assumes this resolves favorably |
| 5 | Chain-sequence continuity reconstructability | `REQUIRES IMPLEMENTATION VERIFICATION` | Same as #4 (inherited from LDS §11) | Determines whether workflow-level chained practice's evidence (§7.F) is trustworthy as specified |
| 6 | `XE` behavior against an unsupported element type | `REQUIRES IMPLEMENTATION VERIFICATION` | Technical re-verification; SME if domain accuracy also matters (inherited from LDS §14/§36) | Blocks authoring a specific, honest Failure/Recovery experience for that case (§15.1) |
| 7 | Known Issue #7's mitigation choice — (a) accurate pre-completion numbering view, or (b) sequence `XE` after `ER`/`ET`/`RT` | `PENDING DECISION` | Whoever owns the already-tracked scoped discussion (file 13) | This document defaults to (b) as a safe interim sequencing (§15.1) but does not treat that default as the decision |
| 8 | Coach layout — persistent global element vs. per-page component | `PENDING DECISION` | Implementation, per file 06/07's own explicit deferral | §11/§18 define the behavioral contract either layout must satisfy; the choice itself is untouched |
| 9 | The one frozen Scenario's actual content (objective, constraints, narrative) | `PENDING DECISION` | Curriculum authoring (file 13) | §7.G/§14 define the contract the content must fill; this document cannot architect content that doesn't exist yet |
| 10 | The CS track's retry/branch model and choice-quality rubric | `PENDING DECISION` | CS-content domain expert; Decision 6's own pending contract (inherited from LDS §19/§36) | This document declines to invent CS experience mechanics beyond what LDS already scopes (§8's rejection list) |
| 11 | Whether attempting the one Scenario before relevant skills reach CONSOLIDATED should be hard-gated or merely un-recommended | `PENDING DECISION` | Product (Karim, if it affects experience/scope) | Affects Transition 2's Conditions field (§9); this document does not assume a hard gate exists where file 07 doesn't state one |
| 12 | Command-level Amadeus accuracy, whole-workflow validity, and engine-simplification acceptability | `REQUIRES DOMAIN VALIDATION` | SME (Decision 7, inherited from files 07/13/LDS) | Underlies every experience this document architects for the frozen slice; unaffected by anything in this pass |
| 13 | Design Execution (colors, typography, identity, imagery, motion) and Naming/Branding | `REQUIRES USER AUTHORITY` | Karim | §19 defers to it entirely; nothing above assumes an outcome |


### New Candidate — Terminal Screen Familiarization / Screen Literacy

**Status:** "PENDING DECISION" — NEW CANDIDATE — REQUIRES INDEPENDENT REVIEW

**Observation:** A first-time or low-familiarity learner may be able to learn a command conceptually yet still lack the ability to read and interpret the Terminal interface/output itself — for example, identifying where relevant airport, airline, flight, time, or other operational information appears and how to use that information when acting in the Terminal.

**Potential gap:** The current Learning / Ghost Mode / "TERMINAL_PRACTICE" / Coach architecture provides command learning, demonstration, guided practice, and assistance, but does not appear to explicitly establish a learner-facing Terminal Screen Familiarization / Screen Literacy layer.

**Hypothesis to evaluate:** The Terminal may benefit from a progressive familiarization model in which learners can first learn how to read the operational screen, then practice against the real Terminal with assistance, and eventually perform with reduced or no assistance.

**Important constraint:** The proposed “three Terminal sections/modes” is an initial hypothesis only, not a decision. Independent review must determine whether the gap is real, whether it is material, and what the minimum justified intervention should be — for example a mode, sub-mode, lesson component, Coach behavior, inline orientation mechanism, or another mechanism.

**Assessment note:** Do not assume that Assessment should be hint-free. The current Assessment contract explicitly preserves existing assistance/hint semantics. Any change to that behavior requires independent review and an explicit decision; it must not be inferred from this candidate.

**Required independent review:** Evaluate this candidate against:

- Learning Design Specification
- Learning Experience Architecture
- Product / Terminal architecture
- Curriculum / Coach contract
- current Decisions / State Contract

Classify the candidate as:

«MATERIAL / NON-MATERIAL / ALREADY COVERED»

If material, recommend the smallest justified intervention and identify which artifact(s) should own the resulting decision or mechanism.

No upstream modification is authorized by this candidate alone.


---

## 23. Adversarial Self-Review

Performed once the first complete draft existed, per this document's
governing brief §30 — genuinely trying to break it, not confirming it.
Five real defects were found and fixed in place (not merely listed) before
this document was considered a candidate for Opus review; they are
reported here rather than hidden, because a self-review that finds nothing
in a first build is far more likely to be incomplete than the build is to
be flawless.

### Defects found and fixed

| # | Defect | Category | Where fixed |
|---|---|---|---|
| 1 | `LEARNING`'s coverage said nothing about Lesson 17's undefined completion rule — a learner could reach it with no stated behavior. | Learning / Experience (dead end) | §7.B |
| 2 | Future-plan curriculum items (file 06's Future Expansion Backlog) had no explicit prohibition against appearing as available Practice content inside `LEARNING`. | Governance (an existing rule left unenforced by this architecture) | §7.B |
| 3 | Speed Drills — a real, decided mechanic (LDS §17) — had no experience home anywhere in this document's first draft. | Learning (an experience disconnected from an intended mechanic) | §7.F |
| 4 | The Simulator Scope Disclosure (LDS Principle 6.1) had no experience home either. | Learning (same category as #3) | §7.F |
| 5 | §7.L and Transition 6 both stated that the *reactive* NEEDS_REINFORCEMENT trigger surfaces "through Flight Deck," identically to the *proactive* spaced-retrieval trigger. On inspection, the reactive trigger sets its flag immediately, inside whatever state the error occurred in — it does not pass through Flight Deck at all. This is the most consequential finding of this pass: it had misrepresented where a real mechanic actually lives, not merely omitted something. | Experience (ambiguous/incorrect transition) | §7.L, §9 Transition 6 (split into 6a/6b) |

### Structured review against every category this document's governing brief names

**Learning.** Is any learning objective disconnected from an experience? —
Defects #1, #3, #4 above were exactly this; fixed. Does support undermine
independence? — No new finding beyond what §10/§11 already guard against;
the exclusion rule and CONSOLIDATED-gated escalation suppression are cited,
not weakened, anywhere in this document. Is assessment actually distinct?
— Yes, via the explicit-disclosure requirement in §7.H/§9 Transition 3;
this is this document's own inference beyond file 07's literal carry-over
wording, and is tagged `[EXPERIENCE ARCHITECTURE DECISION]` rather than
`[DECISION — CANONICAL]` precisely because it is an inference, not a
restatement.

**Experience.** Dead ends? — None found in the eight-state catalog after
fixing #1. Ambiguous transitions? — Defect #5 was exactly this; fixed.
Missing states? — Checked against §13's full A–O list; Speed Drills and
the Simulator Scope Disclosure were missing *homes*, not missing states in
their own right — fixed without adding new states (§20 would have flagged
new states as unjustified). Disconnected surfaces? — None found; every
state in §8 has at least one entry and one exit connecting it to another.

**Evidence.** Does the architecture claim evidence that cannot be
observed? — No instance found; §12's table was checked row by row against
LDS's actual evidence classes and no row asserts more than its Claim
Boundary allows. Is evidence overinterpreted? — Checked specifically for
the Assessment row (§7.H, §9 Transition 3) since this document's own
disclosure inference (above) is the one place it adds language beyond
file 07 — the inference is about *what the learner is told*, not about
upgrading what the evidence *proves*, so Kane's framework (LDS §20) is
left exactly as weak/strong as LDS states it. Is assistance contaminating
interpretation? — No; the independence-flag mechanics are cited, never
altered.

**Scenarios.** Merely decorative? — §14's table requires scenario-aware
feedback and visible objective/constraints throughout, not just at entry;
this was checked against the risk of a scenario being "a drill with a
theme" and the table's requirements specifically prevent that reduction.
Support real workflow competence? — Bounded honestly by the Baldwin & Ford
citation in §7.M; not overclaimed.

**Product.** Does the architecture preserve the approved product
structure? — Yes; no sixth area, no area redefinition. Is Terminal still
operationally central? — Yes, and quantified (§6). Has a generic LMS
pattern leaked in? — Checked specifically against the state catalog: no
state is a quiz screen, no transition terminates at a decorative summary,
and §6 states this rejection explicitly.

**Technical.** Are required dependencies explicit? — Yes (§17, §22).
Hidden state requirements? — None found beyond what LDS/file03 already
flag; this document introduces no new field. Is anything over-specified? —
One borderline case examined directly: §18's statement that Coach defaults
to collapsed/on-demand on mobile viewports. This sits close to the
visual-design boundary this document is supposed to respect (§19). See
§24 for why it was kept rather than removed.

**Governance.** Were any current decisions silently changed? — Checked
specifically at Transition 2 (Practice → Scenario): this document does not
assume a hard CONSOLIDATED-gate exists for Scenario entry where file 07 does
not state one, and flags the ambiguity explicitly (§9, §22 item 11) rather
than picking a plausible-sounding answer. Was historical content promoted?
— No; file 04's resume-card and token evidence remain tagged `[HISTORICAL]`
throughout. Were recommendations turned into requirements? — Checked
specifically for the Simulator Scope Disclosure (defect #4): giving it an
experience home in §7.F explicitly does not upgrade its LDS-assigned
`RECOMMENDATION` status, and §7.F says so directly. Were unresolved
matters falsely closed? — Thirteen items remain open in §22, none closed
here.

**Complexity.** Unnecessary states, counters, scoring, or orchestration? —
Re-checked against §20's ledger after fixing defects #1–5; none of the
five fixes added a new state, counter, or persistence mechanism — each
reused an existing mechanic and gave it a home, or corrected a
misstatement about where an existing mechanic actually lives.

### What was considered and not changed

Two things were examined and deliberately left as-is, because the review
found them sound rather than merely unexamined:

- **The eight-state catalog's shape.** Considered whether `GHOST_MODE`
  should merge into `LEARNING` (since both are non-evidentiary) or whether
  `TERMINAL_ASSESSMENT` should merge into `TERMINAL_PRACTICE` (since their
  command-level mechanics are identical). Rejected both merges: `GHOST_MODE`
  is learner-controlled playback of *engine* output, not reading, and LDS
  treats it as its own mechanism (§12, §16) with its own confidence-
  reality-gap hypothesis that only makes sense if it's tracked separately;
  `TERMINAL_ASSESSMENT` must be experientially distinguishable from
  practice per file 07's own disclosure requirement, which a merge would
  directly violate.
- **Reconciling the two learning-progression chains (§5).** Considered
  whether stating the reconciliation was in-scope at all, given file 03's
  chain is already canonical and unchangeable. Kept it, because the risk
  being addressed is a *reading* risk (a future implementer treating two
  chains as competing models), not a proposal to alter either chain — no
  authority is exercised over file 03 or the LDS/Roadmap pipeline by
  stating how they relate.

### External Correction Pass (this review)

A second, independent adversarial pass — genuinely separate from the
authoring pass above, not a re-run of its checklist — found four further
items, none large enough to touch this document's overall architecture,
all corrected in place:

| # | Finding | Severity | Where fixed |
|---|---|---|---|
| 6 | The assistance-ladder table (§10) listed Partial Reveal under both "Supported" and "Reduced Support," leaving it unclear whether these were the same rung or different ones. | Moderate | §10 — Supported is now Nudge only, Reduced Support is Partial Reveal only. |
| 7 | §7.H's Assessment disclosure translated file 07's conditional, content-specific carry-over rule into a general "scoring is active" tell — narrower/different from what file 07 actually requires. | Major | §7.H, §9 Transition 3 — disclosure now explicitly covers the carried-over content itself when carry-over is present, with file 07's own zero-carry-over carve-out restated. |
| 8 | The reactive reinforcement prompt's "inline" timing option (§7.L) was ambiguous about whether it could fire mid-scenario, risking the Scenario Differentiation Contract's state-integrity requirement. | Moderate | §7.L — inline surfacing is now restricted to ordinary `TERMINAL_PRACTICE`; a `SCENARIO_SESSION`-origin trigger always defers to the Flight Deck path. |
| 9 | The Master Execution Roadmap is a stated input (§3) and is substantively cited (§5), but had no row in either the source table (§3) or the consistency audit (§21). | Minor | §3, §21 — a row added to each; the audit row also confirms no conflict with the Roadmap's current revision. |

No new state, transition, counter, or persistence mechanism was added by
any of the four fixes — each corrected a translation-fidelity or
bookkeeping gap within a section that already existed. §26's readiness
status is updated accordingly.

---

## 24. Defect vs. Preference Ledger

Per this document's governing brief §31: a **defect** is a contradiction,
material omission, broken flow, unsupported claim, ambiguous requirement,
missing dependency, governance violation, or clear implementation/learning
risk. A **preference** is a stylistic choice among multiple valid
alternatives. This document does not manufacture revisions from
preferences.

| Item | Classification | Disposition |
|---|---|---|
| The five defects in §23 | Defect (each fits one of the named categories: omission, ambiguity, or a governance/accuracy risk) | Fixed |
| Coach defaulting to collapsed/on-demand on mobile (§18) | **Preference-adjacent, examined explicitly** | Kept — see reasoning below |
| Whether Reinforcement's reactive prompt appears inline vs. waits for the next Flight Deck visit (§7.L's own new decision) | Preference among two reasonable implementations | Stated as this document's own explicit choice, not left ambiguous, since *some* choice is needed for the experience to be walkable — but tagged `[EXPERIENCE ARCHITECTURE DECISION]`, not `[DECISION — CANONICAL]`, so it can be revisited without being a "reopening" of anything closed |
| Practice Progression's five-step generic labels (§10) vs. LDS's own state names | Preference in vocabulary only | Kept as a presentation lens, explicitly mapped to avoid duplicated authority (§10 itself states this) |

**Reasoning on the one item kept despite sitting close to the visual-design
boundary:** Coach defaulting to collapsed on mobile is derived directly
from two already-closed rules (Terminal workspace protection, file 04; and
mobile-first-not-desktop-secondary, file 03) rather than from a visual
preference of this document's own — removing it would leave a real,
citable conflict (a persistent Coach panel *would* cost Terminal workspace
on a narrow viewport) unaddressed rather than resolved. It is kept as an
experience-level constraint precisely because it is forced by existing
decisions, not chosen freely among alternatives — which is what
distinguishes it from a preference.

---

## 25. Final Architecture Acceptance Test

Confirming, per this document's governing brief §32, that a future design/
engineering/content team could use this document without rediscovering the
intended architecture from project history:

| Question | Where answered |
|---|---|
| What learner experiences exist, and why? | §7 (A–O), §8 |
| How do they connect? | §9, §5 |
| What states matter? | §8, including the four explicitly rejected |
| What transitions matter? | §9 |
| What evidence matters? | §12 |
| How does progression work? | §7.K, §13 |
| Where does support appear, and how does it fade? | §11, §10 |
| How do scenarios work? | §7.G, §14 |
| How does assessment differ? | §7.H, §9 Transition 3 |
| How do failures recover? | §15 |
| How does continuity work? | §16 |
| What dependencies exist? | §17, §22 |
| What remains unresolved? | §22 |
| What MUST NOT be assumed? | §22 (all thirteen items), §3's non-ownership list |

All fourteen questions this document's own acceptance test requires are
answered somewhere above with a specific pointer, not a general assurance.

---

## 26. Readiness Determination

Per this document's governing brief §33, this document does not call
itself Canonical, Officially Approved, or Fully Validated — no project
governance has granted any of those statuses, and claiming one would
misrepresent this document's actual authority (§2).

**Confirmed before issuing a readiness status:** the required current
corpus was read in full (§3); source classifications are applied
consistently (§2, throughout); Learning Design intent is preserved, not
redecided (checked explicitly in §21's audit row for the LDS); Product
Architecture is preserved (§6, §21); current decisions are respected, not
silently closed (§22, §21); Amadeus behavior is not invented (§15.1, §21);
major experience journeys are coherent (§23 found and fixed five defects in
the authoring pass and a further four in an external correction pass, both
re-verified); important states and transitions are represented (§8, §9);
evidence integrity is preserved (§12), and one place it was translated too
loosely (Assessment carry-over disclosure) has been corrected (§7.H, §23);
Coach support is compatible with independence (§10, §11); failure/recovery
is covered at both levels (§15); continuity is addressed (§16); Terminal's
role is protected (§6, quantified); implementation dependencies are
visible but not over-specified (§17); visual design remains appropriately
uncommitted (§19); cross-file contradictions are surfaced, not found in
substance (§21, now including a fresh check against the Roadmap's current
revision); unnecessary complexity was rejected with reasons (§20); and no
known material defect remains without an explicit status (§22, §23, §24).

> **STATUS: READY FOR OPUS FINAL REVIEW.**

This is a design-quality determination, not a governance approval. It
means this document has been pushed, through one authoring pass, one
internal adversarial self-review that found and fixed five defects, and a
further external correction pass that found and fixed four more, to the
point where every remaining gap is explicitly named, correctly classified
(§22's five statuses), and pointed at the party or evidence that can
actually close it. It does not mean the architecture is proven to produce
a good learner experience in practice — nothing in this document
substitutes for Opus's independent review, Karim's approval, real
implementation, or real learners actually using the product (Roadmap §17,
§18, §24). No known material defects remain within the currently available
evidence and project corpus; this is not a claim of perfection.


---

## 27. Final Self-Check

The exact checklist this document's governing brief requires (§34), each
item confirmed against a specific location rather than checked by
assertion alone.

- [x] I read all required current files. — §3.
- [x] I did not rely on memory instead of source files. — every source-role
  tag throughout points at a specific file/section.
- [x] I did not use historical material as current truth. — every
  `[HISTORICAL]` citation (file 04's tokens, resume card) is explicitly
  marked as evidence, not default, per its own tag (§4's design system
  section throughout).
- [x] I preserved canonical authority boundaries. — §2, §3's non-ownership
  list, applied throughout.
- [x] I preserved Learning Design intent. — §21's audit row; no LDS
  mechanic redefined, only translated.
- [x] I preserved Product Architecture. — §6, §21.
- [x] I preserved current decisions. — §22 treats every file-13 OPEN item
  as still open; §21's audit row confirms no premature closure.
- [x] I did not invent Amadeus behavior. — §15.1 explicitly marks `XE`'s
  unknown behavior `REQUIRES IMPLEMENTATION VERIFICATION` rather than
  guessing.
- [x] I did not invent learner evidence. — §12's table only cites evidence
  LDS/file 07 already authorize.
- [x] I did not invent mastery claims. — §12's Claim Boundary column; §13.
- [x] I did not create unnecessary mechanisms. — §20's ledger; §8's four
  rejected states.
- [x] Major learner journeys are represented. — §7 (A–O).
- [x] Important states are represented. — §8.
- [x] Important transitions are represented. — §9.
- [x] Feedback/correction logic is coherent. — §7.I, §15.1; re-verified
  during §23's review with no further finding.
- [x] Independence logic is protected. — §10, §11, cited not altered.
- [x] Assessment is appropriately distinct. — §7.H, §9 Transition 3.
- [x] Scenario architecture is meaningful. — §14; checked against
  "decorative wrapper" risk in §23.
- [x] Evidence flow is legitimate. — §12.
- [x] Progression logic is coherent. — §7.K, §13.
- [x] Reinforcement/retention is represented where required. — §7.L, §9
  Transitions 6a/6b (corrected during self-review, §23).
- [x] Transfer is represented where required. — §7.M, §9 Transition 7,
  with its conditional (not forced) relationship to Reinforcement stated
  explicitly.
- [x] Failure/recovery is represented. — §15, at both the micro and macro
  level.
- [x] Continuity/resume is represented. — §16.
- [x] Mobile implications are addressed where materially relevant. — §18.
- [x] Visual styling has not been prematurely locked. — §19; the one
  borderline case (Coach mobile default) is examined explicitly in §24
  rather than left unexamined.
- [x] Technical dependencies are explicit but not over-specified. — §17;
  no schema, API, or storage engine proposed anywhere.
- [x] Cross-file conflicts are surfaced. — §21; none found in substance,
  one terminology artifact corrected (§1).
- [x] Unknowns remain unknown. — §22's thirteen items, each carrying one
  of the five mandated statuses.
- [x] No material decision was silently changed. — §21's audit row; §22
  item 11 specifically confirms no assumed gate where file 07 states none.
- [x] No historical rule was silently promoted. — §4 (design system)
  citations throughout keep `[HISTORICAL]` tags intact.
- [x] No major document-level defect remains untracked. — §23's five
  defects were fixed, not merely tracked; §22 tracks everything that
  remains genuinely open and could not be fixed by this document alone.

---

## 28. Canonicalization Note & Change Discipline

This document remains **DRAFT AUTHORITY**, not canon, regardless of the
readiness status in §26. Per the Operating Constitution's classification
rules, nothing above may be treated as decided, delegated, or approved by
virtue of having been written down here, self-reviewed once, and found
internally consistent. The governance chain is unchanged from §2: current
canonical knowledge + Learning Design → this architecture → this
document's own adversarial self-review (complete) → Opus's independent
review (pending) → Karim's review and approval (pending) → canonicalization.
The first two steps are done. The remaining two are not this document's to
perform.

**Change discipline, per this document's governing brief §36:** only
`DEIXEN_Learning_Experience_Architecture.md` was created or modified
during the authoring pass, and only this same file was modified during the
subsequent external correction pass recorded in §23. No canonical file (00,
03–08, 13, 14) and no other draft-authority document (the Learning Design
Specification, the Prompt Engineering & Governance standard, the Session
Handoff Protocol, the Master Execution Roadmap) was touched by either pass
— the Roadmap's current revision was read and cross-checked (§21) for the
correction pass, not edited. Where this document's authoring surfaced
something that might eventually warrant an upstream change, that is stated
as a finding pointing at the relevant file, never applied to it:

- No upstream file was found to require a change as a direct result of
  this pass (§21's audit). The "Reminal"/"Terminal" correction (§1) applies
  only to this document's own text and to how it reads its governing
  brief — it does not alter file 08, which already states the rule
  correctly, and needs no restatement.
- The thirteen items in §22 name their owners precisely so that, if and
  when each is resolved, the resolution is recorded in the file that
  actually owns it (file 07's decisions ledger, file 13's register, or the
  LDS itself for anything learning-mechanics-specific) — never retrofitted
  into this document as if this document had the authority to close them.

Until Opus reviews this document and Karim approves it, every
`[EXPERIENCE ARCHITECTURE DECISION]` and `[RECOMMENDATION]` above remains a
proposal, every open-item status remains exactly as open as it is labeled,
and this document's own readiness claim in §26 is the strongest claim it
is entitled to make about itself.

