---
name: DEIXEN Learning Design Specification
status: DRAFT AUTHORITY — NOT CANONICAL. REVISION 2 + Phase 2 synchronization
  (2026-09-24; see the reading rule below). Revision 2 was produced in response
  to `AeroBridge_Learning_Design_Adversarial_Review.md` (an external review,
  now absent) and a self-directed adversarial pass (§38). Reviewed by Claude in
  Execution Plan Phase 1; not yet approved by Karim.
owns: A proposed system for how DEIXEN teaches, practices, assesses, and
  evidences a skill — skill states, assistance rules, evidence-interpretation
  rules, practice/retention architecture, and a reusable skill-authoring
  template. It does NOT own, restate, or silently amend product identity,
  Amadeus command behavior, curriculum content/lesson counts, design tokens,
  or any decision already closed in the canonical set. Where this document
  touches any of those, it is citing them, not deciding them.
relationship to the canonical set: Strictly additive. Files 00 and 03–08, 13,
  14 remain authoritative in full per the Operating Constitution. If any
  sentence below appears to disagree with a canonical file, the canonical
  file is correct and the conflict is named explicitly in §36 (Open
  Questions) — never silently resolved in either direction.
source basis: Built from the nine canonical files, the Operating
  Constitution, this task's governing brief, Revision 1 of this document,
  and `AeroBridge_Learning_Design_Adversarial_Review.md`, all read in full
  for this pass. Also draws on external learning-science and
  professional/aviation-training-assessment research, used strictly as
  described in §3 and tagged per §2 — never as a source of Amadeus/GDS
  domain facts, which come only from file 05. This document was not given
  the DEIXEN repository/codebase itself; where it discusses "the engine"
  or "the code," it is citing file 05's already-established claims, not
  independently re-verifying them.
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
>    becomes a requirement (wording of 07 Decision 27, 2026-09-25): every
>    element number shown is the element's number in the PNR as it stands
>    at that moment, computed by the same function as the final display.
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

# DEIXEN — Learning Design Specification (DRAFT, REVISION 2)

> **Read this before anything else.** Everything below is one of **eight**
> kinds of claim, tagged inline: **VERIFIED FACT**, **CURRENT PRODUCT
> DECISION**, **RESEARCH-SUPPORTED PRINCIPLE** *(new in this revision — see
> §2)*, **LEARNING DESIGN DECISION**, **RECOMMENDATION**, **VALIDATION
> HYPOTHESIS**, **OPEN QUESTION**, or **REJECTED/DEFERRED**. None of the
> LEARNING DESIGN DECISION or RECOMMENDATION items are canonical merely
> because they appear in a structured document with a confident tone. See §2
> for the full classification rules.
>
> **What changed in Revision 2, in one paragraph:** an independent
> adversarial review found four P1 and eleven P2 issues — none fatal, all
> real. This revision fixes the ones that needed fixing, narrows one that was
> broader than necessary, and is explicit about the handful that remain
> genuinely open pending evidence this document cannot manufacture. It also
> grounds the principles that were previously "well-supported generally" in
> named research, distinguishing what that research actually shows from what
> DEIXEN still has to confirm for itself. Every disposition is traceable
> in §35's expanded Decision Register. This revision does not relitigate
> anything the adversarial review confirmed was already sound (§2 of that
> review) — that material is carried forward without churn.

## Table of Contents
1. Executive Summary
2. Purpose, Scope, and Authority
3. Source Map & Research Basis
4. Current Learning Model Diagnosis
5. Learning Design Principles
6. Learning Objective Model
7. Skill Model
8. Skill-Specific Learning Paths & Tiering
9. Core Learning Loop
10. Completion / Competence / Mastery / Transfer / Retention — Definitions
11. Practice Architecture
12. Retrieval vs. Recognition
13. Feedback Architecture
14. Error & Recovery Architecture
15. Coach / Assistance Architecture
16. Ghost Mode
17. Speed Drills
18. Scenario / Transfer Architecture
19. Customer Service Learning
20. Assessment Architecture, Validity & Sampling
21. Evidence Architecture
22. Longitudinal Learner State (Conceptual Only)
23. Progression Rules
24. Retention / Reinforcement
25. Difficulty / Fading
26. Cognitive Load / Human Factors
27. False Mastery & Gameability Audit
28. Learning Efficiency & Minimum Viable Learning System
29. Implementation Contract
30. Reusable Skill Authoring Standard
31. Curriculum Integration
32. Vertical Slice Validation (Learning-Design Sense)
33. Learning Claims Audit
34. Validation Strategy
35. Decision Register
36. Open Questions
37. Rejected / Deferred Ideas
38. Adversarial Review Response & Second Self-Attack
39. Final Decision & Design-Readiness Determination
40. Final Learning Design Principles
41. Canonicalization Note
42. Final Closure Determination

---

## 1. Executive Summary

Revision 1 established that DEIXEN's evidence philosophy (four evidence
classes, no-fabrication rules, hint-honesty — all **CURRENT PRODUCT
DECISION**, file 07) was sound but had no learning-mechanics layer making it
enforceable at the moment a learner is typing a command. That diagnosis
stands. Revision 1 then built that layer; an independent adversarial review
tested it and found it fundamentally sound but not yet tight enough in four
specific places, plus eleven smaller gaps. This revision closes those gaps
and, independently of the review, found two more of its own (see §38).

**What actually changed, not just what was reviewed:**

- **The independence-exclusion rule had a hole**, and it was the hole that
  mattered most: ordinary, always-on error feedback (not just Coach's hint
  ladder) could hand a learner the fix without ever being counted, so a
  "success only counts as independent if nothing helped it along" (§40)
  wasn't actually true as specified. §13 and §15 now define one rule that
  covers both channels.
- **"CONSOLIDATED" no longer means "succeeded some PROVISIONAL number of
  times."** It means "met this skill's own explicit correctness checklist,
  independently, more than once" — a checklist derived directly from file
  05's documented behavior, not invented. This is a direct application of
  simulation-based mastery learning practice from professional/technical
  training (McGaghie et al., 2014 — see §5, §7), and it resolves the
  bootstrapping problem the review identified: a checklist can exist and be
  used from day one, even while the exact repeat-count stays provisional.
- **The assistance ladder gained one content tier** — a "Partial Reveal"
  between Nudge and Full Reveal — grounded in cognitive-load research on
  fading worked examples (Renkl & Atkinson, 2010), directly answering
  whether two tiers were enough for commands with several simultaneous
  preconditions. It is still one counter, per the canonical rule that has
  never changed.
- **Lesson 5's hybrid Terminal-plus-English evaluation, previously
  undefined, now has an explicit rule**: two separate evidentiary events,
  no cross-compensation between the technical and Customer Service
  components. This was a real gap with no design behind it at all in
  Revision 1.
- **The frozen slice's assessment claim is now stated with a validity
  framework behind it** (Kane, 1992/2013 — see §20), so what it can and
  cannot support is precise rather than implied.
- **A retention mechanism was added that requires no invented threshold**:
  an optional, expanding-interval retrieval prompt, justified by the spacing
  effect (one of the most replicated findings in learning research — Cepeda
  et al., 2006) — alongside, not instead of, the existing error-recurrence
  trigger, which stays the primary mechanism.

**What did not change:** the five-state skill model's shape, the four
evidence classes, the practice/assessment functional split, the rejection
list (adaptive difficulty, composite scores, a second counter), Decision 8A's
frozen boundary, and the conservative mastery-language rule. The adversarial
review confirmed these were sound, and nothing found since gives a reason to
touch them.

**What remains honestly open, and will stay open after this revision:**
whether the Event Log's actual timestamp granularity supports the mechanisms
this design now depends on even more precisely than before; whether
retrieval-over-exposure produces its expected effect for this specific
audience; the exact value of every PROVISIONAL number, even the new interim
defaults this revision assigns them; and everything already correctly gated
behind Decision 6 (Customer Service) and Decision 7 (Amadeus/GDS domain
validation). See §38 and §39 for the full, honest accounting.

---

## 2. Purpose, Scope, and Authority

**Purpose.** Define how a learner moves from not knowing an DEIXEN skill
to being able to perform it independently, and define what evidence is
allowed to say that happened — without inventing Amadeus facts, empirical
thresholds, or product scope this session has no authority over.

**Scope.** Unchanged from Revision 1: this document governs learning
mechanics only — skill states, practice sequencing, assistance/feedback
rules, evidence interpretation, and a reusable authoring template. It does
not touch product identity or IA (file 03), visual design (file 04), Amadeus
command behavior or the error taxonomy's content (file 05), curriculum
lesson content or lesson counts (file 06), the decisions ledger itself (file
07), or the multi-agent process (file 08).

**Authority this document has, and does not have.** Unchanged from Revision
1: this is a **RECOMMENDATION-class deliverable**, authored under delegated
technical authority, not a decision. The governance chain remains: canonical
knowledge → this analysis → adversarial review (now completed once,
externally) → human/product-owner review → approval → canonicalization.
This document still cannot promote itself past "proposed."

**Classification legend**, now eight tags (one new):

| Tag | Meaning | Constitution equivalent |
|---|---|---|
| **VERIFIED FACT** | Explicitly stated in a canonical file (00, 03–08, 13, 14) | CANONICAL |
| **CURRENT PRODUCT DECISION** | A closed/approved decision this document builds on without changing | CANONICAL or DECIDED/DELEGATED |
| **RESEARCH-SUPPORTED PRINCIPLE** *(new)* | An external, citable research finding, stated as that research actually states it — not yet an DEIXEN decision by itself | Evidence input to a RECOMMENDATION, not a tag the Constitution has an exact equivalent for |
| **LEARNING DESIGN DECISION** | A new rule this document introduces to make canon enforceable, which may be *informed by* a RESEARCH-SUPPORTED PRINCIPLE but is always a distinct, DEIXEN-specific choice | RECOMMENDATION (until approved) |
| **RECOMMENDATION** | A proposed improvement, explicitly optional | RECOMMENDATION |
| **VALIDATION HYPOTHESIS** | A design assumption that needs real learner testing, not just document review or external citation | a sub-flavor of OPEN |
| **OPEN QUESTION** | Cannot responsibly be resolved from current knowledge | OPEN |
| **REJECTED / DEFERRED** | Considered and explicitly not adopted here | — (recorded so it doesn't quietly return) |

**Why the new tag exists, and its exact discipline (per this task's
governing brief's Research Standard):** citing a well-known finding and
building it into a REJECTED, an approved-sounding design is not the same
thing as that design being validated for DEIXEN. Every time this
revision cites external research, it does five things, in order: (1) states
the actual proposition the research supports — no stronger; (2) does not
overgeneralize beyond what the cited work actually measured (e.g., a
classroom-vocabulary spacing study is evidence about spacing, not about
DEIXEN's specific learners); (3) explains the specific mechanism by
which it applies to an Amadeus-command-practice context; (4) names the
distinct DEIXEN design decision the research *informs*, tagged
separately as LEARNING DESIGN DECISION; and (5) states what remains a
VALIDATION HYPOTHESIS regardless of how strong the external evidence is. A
RESEARCH-SUPPORTED PRINCIPLE never appears alone as a justification for
something the canonical files forbid, and never substitutes for Amadeus/GDS
domain evidence, which always comes only from file 05 and, for real-world
accuracy, Decision 7's SME process.

File 08's process vocabulary (`CONFIRMED`/`APPROVED`/`OPEN`/`NEEDS
VALIDATION`/`PROPOSED`/`PLANNED`/`DEFERRED`/`REJECTED`) and Fact Separation
Framework remain the governing cross-agent vocabulary; this document's tags
are a finer-grained overlay for learning-design content specifically, as in
Revision 1.

---

## 3. Source Map & Research Basis

**Inspected directly, in full, for this pass, beyond Revision 1's sources:**
`AeroBridge_Learning_Design_Adversarial_Review.md` in its entirety, and this
task's own governing revision brief.

**Everything Revision 1 already established about scope, constraints, and
what's deliberately not treated as current** (the frozen-slice boundary, the
four-field Event Log, the single hint counter, the four evidence classes,
Decision 6's wall, Decision 7's split, and the OLD-era material that stays
historical) is unchanged and is not restated in full here — see Revision 1's
§3, which this section supplements rather than replaces.

**One correction to how this document treats its own prior output:** per
this task's explicit instruction, Revision 1's text is evidence about what
this document previously proposed, not automatic authority for what it
should say now. Every claim carried forward below was re-examined against
the adversarial review and against the research basis below, not copied
because it was already there.

### External Research Sources Consulted

Used exactly as described in §2 — to inform *how* an already-scoped
DEIXEN skill should be taught, never to supply *what* Amadeus does. Each
entry states the actual finding, not an inflated version of it.

| Area | Source(s) | What it actually establishes | What it does not establish |
|---|---|---|---|
| Retrieval practice / testing effect | Roediger & Karpicke (2006); Rowland (2014) meta-analysis; Adesope, Trevisan & Sundararajan (2017) meta-analysis | Practice testing produces medium-to-large, well-replicated gains in retention *and* transfer versus restudy; benefits are larger when feedback follows retrieval. | Does not establish the specific effect size for DEIXEN's learners, content, or Terminal interface. |
| Spacing effect | Cepeda, Pashler, Vul, Wixted & Rohrer (2006) meta-analysis; Cepeda et al. (2008) | Distributed practice outperforms massed practice; the *optimal* gap between reviews scales with how long retention needs to last, not a fixed universal number. | Does not specify what that gap should be for a GDS command skill specifically. |
| Feedback | Hattie & Timperley (2007); Wisniewski, Zierer & Hattie (2019) replication meta-analysis (k=994) | Feedback has a real, medium average effect (d≈0.48) on learning, but effectiveness depends heavily on *content*: task/process/self-regulation-level feedback outperforms praise-only ("self") feedback. | Does not establish DEIXEN's specific feedback copy will land at the effective end of that range — that is a content-authoring and testing question. |
| Mastery learning (general) | Kulik & Kulik (1987); Kulik, Kulik & Bangert-Drowns (1990) meta-analyses | Criterion-referenced mastery testing improves outcomes, especially for weaker students, and effect size depends on the *stringency* of the criterion used, not primarily on how many attempts are allowed. Slavin's (1987) narrower-sample re-analysis found much smaller effects — a genuine, unresolved controversy in this literature, noted rather than hidden. | Does not resolve the controversy, and does not specify DEIXEN's criterion. |
| Simulation-based mastery learning (professional/technical training) | McGaghie, Issenberg, Barsuk & Wayne (2014) critical review | A seven-component model (objectives; a checklist-based minimum passing standard; baseline test; deliberate practice with feedback; post-test; continued practice until standard met; advance only once met) is associated with real, measured downstream (translational) performance improvements in procedural skill training, not just simulator scores. | Medical/procedural-skill evidence base; DEIXEN is cognitive/software-procedural, not physical-motor — the structural pattern transfers more confidently than any specific number does. |
| Cognitive load / fading | Sweller & Cooper (1985); Renkl & Atkinson (2010); Renkl (2014) | Worked examples reduce cognitive load and aid novices; the benefit reverses for learners with more expertise ("expertise reversal effect"); progressively fading a worked example's steps is a well-established way to move a novice toward independent performance. | Does not specify how many fading steps DEIXEN needs — that is a content-design choice this revision makes explicitly (§8, §15) and flags for confirmation. |
| Error management training | Keith & Frese (2008) meta-analysis (24 studies, N=2,183) | Training that encourages errors with explicit "errors are informative" framing shows a real average effect (d=0.44), larger for post-training transfer (d=0.56) than in-training performance, and largest for *adaptive* transfer to structurally different tasks (d=0.80) — explicit error-framing instructions were the active ingredient, not error exposure alone. | Does not establish the exact effect for DEIXEN's Tier 3 commands specifically. |
| Transfer of training | Baldwin & Ford (1988) review | Transfer depends on three factors: trainee characteristics, training design, *and* work environment — and self-report is an insufficient transfer measure; verifiable criteria are needed. | DEIXEN can only ever influence the first two factors; the third (the real workplace) is structurally outside this product's control, a limitation this revision now states explicitly (§18). |
| Assessment validity | Kane (1992; 2013) argument-based validity framework | Validity claims decompose into four inferences — Scoring, Generalization, Extrapolation, Implications — and evidence should focus on the weakest link in that chain. | Does not itself supply DEIXEN's evidence for any of the four inferences; it supplies the structure for stating honestly which ones are, and aren't, currently supported (§20). |
| Deliberate practice | Ericsson, Krampe & Tesch-Römer (1993); critiqued by Macnamara, Hambrick & Oswald and others | Structured practice targeting a specific, identified weakness with immediate feedback and a qualified "coach" designing the exercise is a well-defined, useful construct. The strong claim that it is *sufficient* to explain expert performance is contested and not treated as settled here. | Does not license treating "more repetition" as automatically equivalent to deliberate practice — targeting matters, per the critique. |
| Aviation/professional training structure (benchmark only, not domain content) | ICAO Doc 9868 (PANS-TRG) Competency-Based Training and Assessment (CBTA) framework, as described in IATA/ICAO public guidance | Professional aviation training increasingly assesses observable behaviors against a defined competency framework, prioritizes performance criteria over time-on-task, and formally incorporates structured exposure to fault/error conditions as part of competency assessment, not an afterthought. | **This is a structural rigor benchmark only** (per this task's own explicit instruction) — it says nothing about GDS reservation-agent training specifically, is not a source of Amadeus content, and is not a certification DEIXEN is claiming to follow. |

Full citation detail (journal, volume, page) is intentionally omitted from
this internal design document; each entry above is specific enough
(author, year, sample size where relevant) to be located and checked by
anyone reviewing this revision.

---

## 4. Current Learning Model Diagnosis

Unchanged from Revision 1 in substance — the adversarial review did not
dispute this section, and re-examining it against the research basis above
did not surface a misstatement. Carried forward in full:

**What the current model already does well** (all **VERIFIED FACT**): a
real evidence-integrity discipline predates any learning-mechanics layer —
four evidence classes with mandatory labeling, a ban on fabricating CPM
thresholds or Saudi Readiness percentages, a hint-honesty requirement (file
07); Terminal's interaction-state skeleton for one exchange (file 03); the
error-message discipline (files 05, 06), independently well-founded — it
forces reading authentic system output, which real-terminal transfer
requires (this is now also directly supported by Baldwin & Ford's
finding that training fidelity to the real task matters for transfer, §3);
Ghost Mode's `reveal` pulling live engine output rather than hand-authored
content (file 06); Speed Drills' refusal to invent a CPM threshold (file
06).

**What it failed to specify, and what this revision closes vs. what
remains genuinely open** — restated with disposition, not just repeated:

| Gap named in Revision 1 | Status after this revision |
|---|---|
| No skill-progression model | **Closed by design** (§7) — refined, not reopened, by this revision. |
| No definition of completion/competence/mastery | **Closed by design** (§10) — refined via the correctness-checklist concept. |
| No retrieval-vs-recognition rule | **Closed by design** (§12), now with a fading mechanism, not just a binary rule. |
| No defined assistance ladder | **Closed by design** (§15) — now three content depths, still one counter. |
| No sampling rule for the assessment record | **Closed by design, with an explicit validity framework** (§20) — previously a real gap the adversarial review named as under-addressed (its P2-1). |
| Lesson 17 / `cleanRunsNeeded` content gaps | **Still open** — Knowledge Recovery's job, not this document's, unchanged. |
| No Speed Drills / accuracy relationship | **Closed by design** (§17). |
| No content-level countermeasure for Known Issue #7 | **Partially closed** — the mitigation requirement is now more specific (§14), but still depends on a technical confirmation this document cannot perform. |
| No evidence definition for the Anger Meter | **Closed by design** (Illustrative reclassification, §19) — the *feedback* gap alongside it (why a choice was rated as it was) is newly named this revision, not yet closed (§19, §38). |

**Two gaps this revision found that Revision 1 did not name at all**
(surfaced by the adversarial review, confirmed independently):

- **The feedback/hint boundary was undefined.** Ordinary, always-on error
  correction and Coach's counted hint ladder were two different channels
  with no stated relationship, which meant answer-revealing content could
  reach a learner through the uncounted channel. **Closed by design** (§13,
  §15).
- **Lesson 5's hybrid evaluation had no rule at all**, not even an
  incomplete one. **Closed by design** (§19).

---

## 5. Learning Design Principles

Nine principles (seven carried forward and refined, two new), each with
rationale, evidence basis, product implication, risk, and validation status.
Every principle is included only because a specific gap in §4 required it —
per Principle 9 below, which governs this whole document and has not
changed.

| # | Principle | Rationale | Evidence basis | Product implication | Risk | Validation status |
|---|---|---|---|---|---|---|
| 1 | **Retrieval over passive exposure.** Watching (Ghost Mode) or reading never satisfies a Terminal practice requirement. | Closes the Ghost-Mode-as-mastery gap. | **RESEARCH-SUPPORTED PRINCIPLE**: the testing effect shows medium-to-large, well-replicated retention *and* transfer gains from retrieval versus restudy (Rowland 2014; Adesope et al. 2017) — see §3. | Ghost Mode and worked examples can never advance a skill past INTRODUCED (§7). | Retrieval only helps when it's genuinely effortful — over-scaffolding the retrieval attempt (too much Nudge content) undercuts the exact mechanism this principle relies on. This is now an explicit design constraint on §15, not just a citation. | Principle: well-supported generally. Its DEIXEN-specific effect size: **VALIDATION HYPOTHESIS**, unchanged. |
| 2 | **Progressive independence, with graduated fading rather than a binary switch.** Evidence must distinguish assisted from unaided success; assistance should be removed in graduated steps, not all at once. | Closes the no-assistance-ladder gap; **revised this pass** — the review found the original binary ladder (Nudge/Full hint) too coarse for compound-precondition commands (its P2-7). | **RESEARCH-SUPPORTED PRINCIPLE**: worked-example fading — progressively removing steps from a worked example as expertise grows — is well-established in cognitive load research (Sweller & Cooper 1985; Renkl & Atkinson 2010) as a way to move a novice toward independence without an abrupt jump. | Directly motivates the new three-content-depth ladder (§8, §15): Nudge → Partial Reveal → Full Reveal, still one counter. | Could still be miscalibrated per skill; the *number* of tiers is now research-grounded, the *content* of each tier per skill is still author judgment. | Structure: well-supported. Per-skill calibration: **VALIDATION HYPOTHESIS**. |
| 3 | **Authentic error signal is preserved, never simplified away.** | Formalizes the existing error-message discipline. | **CURRENT PRODUCT DECISION** (files 05, 06) — unchanged. | Coach must never shorten or omit the verbatim message, at any assistance level. | None beyond what already exists. | Not applicable — already canonical. |
| 4 | **Evidence over activity.** No progression signal from time-spent, clicks, or lesson-viewed alone. | Extends the Evidence & Readiness Contract. | **CURRENT PRODUCT DECISION** (file 07), extended into Progression Rules (§23). | Forbids "lesson viewed" or "attempt count" from advancing any skill state. | None. | Not applicable — already canonical. |
| 5 | **Contextual variation before transfer claims.** A skill shown once, in one context, is not general capability. | Closes the single-success-as-mastery gap. | **RESEARCH-SUPPORTED PRINCIPLE**: Baldwin & Ford (1988) — transfer requires generalization across conditions, not just retention of the trained instance; a single training instance predicts training performance far better than it predicts transfer. | Distinguishes "the pipeline works" (Decision 8A's one scenario) from "the learner is broadly competent" (never claimed). | None to current scope; load-bearing once Scenario Bank expands. | **VALIDATION HYPOTHESIS**, mostly post-slice. |
| 6 | **The domain-truth boundary extends into learner-facing language.** No copy may claim more real-world Amadeus correctness than Decision 7 has confirmed. | Extends Operating Constitution §3 and Decision 7 into UI/Coach copy. | **CURRENT PRODUCT DECISION** (the boundary); the language extension is this document's. | "Correct DEIXEN syntax," never "mastered Amadeus AN," until Decision 7 executes. | Could read as hedging — a wording problem, not a substance one. | RECOMMENDATION, low validation burden. |
| 6.1 | **Simulator Scope Disclosure.** Learners are told which limitations are DEIXEN-specific, not real Amadeus (one seat/PNR, no child/infant fares, 2-segment/9-passenger ceiling, Egypt-only Timatic, `FQN`/`FQR` non-functional, the ancillary family currently unreachable). | Prevents a learner forming an incorrect belief about real GDS scope. | Built entirely from Known Issues #5/#6/#8 and structural facts (file 05) — invents nothing. | A short, honest reference, accessible from Learning or Coach. | Minimal. | RECOMMENDATION; disclosure only, low implementation cost. |
| 7 | **Errors are diagnostic events, not failure events — in system design and in Coach's tone.** *(new this revision)* | Names, explicitly, a principle that was previously implicit in the error-message discipline but never stated as a design rule Coach's *language* must follow. | **RESEARCH-SUPPORTED PRINCIPLE**: error management training research (Keith & Frese 2008) found explicit "errors are informative" framing was the *active ingredient* separating effective error-based training from merely letting errors happen — effects were largest for transfer to structurally different (adaptive) tasks, exactly the profile Tier 3 skills need. | Coach copy for any error, at any tier, should frame the error as information about a specific unmet condition, never as a mistake needing an apology or implying deficiency. Directly strengthens the rationale for Tier 3's mandatory Error-Recovery Practice (§8) with a real effect size, not just intuition. | Framing-only; no functional change, no new counted state. | Structure: well-supported by a specific, sizeable meta-analytic effect. DEIXEN-specific wording: content-authoring work, needs review once written. |
| 8 | **A checklist-based minimum passing standard, not a bare repeat-count, is what "correct" should mean.** *(new this revision)* | Directly resolves the bootstrapping problem the adversarial review identified in the PROVISIONAL repeat-count (its P2-3): a checklist can exist and be used from day one; a repeat-count needs data that doesn't exist until the system is already running. | **RESEARCH-SUPPORTED PRINCIPLE**: simulation-based mastery learning in professional/technical training defines "passing" via an explicit, checklist-based minimum passing standard (MPS) rather than a bare count, and this structure is associated with real downstream performance gains (McGaghie et al. 2014). Kulik & Kulik (1987) separately found that mastery-testing effects depend more on the *stringency of the criterion* than on the number of attempts allowed. | Every skill's "acceptable performance" (§6, §7, §30) is now an explicit, file-05-derived checklist, not a vague "success." CONSOLIDATED's repeat-count question becomes "how many times must the full checklist be met," a narrower and more tractable question than before. | None beyond the authoring effort of writing each skill's checklist — bounded by file 05's own already-documented behavior, so nothing is invented. | Structure: strong. Checklist completeness per skill: needs author + review confirmation once written, same discipline as any other content. |
| 9 | **Minimum justified complexity.** Add a state, field, or mechanic only when a specific risk from §4 or §27 requires it. | Meta-principle governing every choice in this document. | — | Governs every REJECTED item in §28/§37, and this revision's own restraint (two new principles, not ten). | Could under-build if applied too aggressively — every rejection states its specific reasoning so it can be challenged. | Self-applied; §38 checks it honestly. |

---

## 6. Learning Objective Model

Template unchanged in shape; the "Acceptable performance" stage is now
explicitly defined as a **correctness checklist** (Principle 8) rather than a
single bar, and the worked instance below is updated to show one.

**OBJECTIVE → OBSERVABLE PERFORMANCE → ACCEPTABLE PERFORMANCE (CHECKLIST) →
EVIDENCE → VERIFICATION → PROGRESSION**

| Stage | Definition |
|---|---|
| Objective | A single observable capability, never phrased as "know," "understand," or "learn." |
| Observable performance | The specific learner action that would count as demonstrating it. |
| Acceptable performance | **A checklist of discrete, file-05-sourced correctness items** — never a single vague "did it work?" bar. Each item traces to something file 05 already documents; nothing is invented here. |
| Evidence | Which Event Log fields (event type, command, result, timestamp) and which **Calculated** derivation this performance produces, including which checklist items it satisfied. |
| Verification | Whether this needs only Recorded evidence, or an owned Assessment record (file 07's Assessment State Contract). |
| Progression | What this unlocks or recommends next (Flight Deck's existing role — file 03). |

**Worked instance — `AN`, updated (VERIFIED FACT for syntax/behavior, cited
to file 05; everything else LEARNING DESIGN DECISION):**

- *Objective:* Learner can retrieve availability for a valid city pair and
  date using `AN`, unaided.
- *Observable performance:* A syntactically complete `AN` command is
  submitted in Terminal with no assistance active for that attempt (Nudge,
  Partial Reveal, or Full Reveal — §15), and not immediately following a
  Ghost Mode `reveal` of `AN` in the same session, **and not immediately
  following any feedback content on this skill that revealed part or all of
  the correct form** (§13's now-unified answer-revealing rule closes the
  gap Revision 1 left open here).
- *Acceptable performance, as an explicit checklist* (Principle 8), sourced
  only from file 05:
  1. Command matches the documented format (2-digit day + 3-letter month +
     origin + destination).
  2. Day-range validation is satisfied.
  3. Airport existence is satisfied on both sides.
  4. Origin ≠ destination is satisfied.
  5. Flight existence is satisfied.
  6. The result is available for a later `SS` reference (file 05's stated
     behavior).
  A successful attempt is one that satisfies **all six** items independently
  — this is what "correct" now concretely means for this skill, replacing
  the earlier vague "success."
- *Evidence:* A Recorded event (type, command literal, result, timestamp)
  plus a **Calculated** independence flag and, new this revision, which
  checklist items the attempt satisfied — both still flagged in §29 as
  implementation-contract dependencies, not assumed-available.
- *Verification:* Unchanged — feeds the frozen slice's one owned Assessment
  record; outside the slice, Recorded evidence alone suffices.
- *Progression:* Recommends `SS` next, per Decision 8A's frozen order.

This template, with its checklist stage, is reusable for any of the 37
documented commands; this document instantiates one worked example plus the
tiering illustration in §8, as in Revision 1.

---

## 7. Skill Model

**Unchanged foundational distinction:** file 03's Terminal Behavioral
Skeleton describes one interaction, not a learner's progress over time. This
section defines the second, separate model, as in Revision 1.

**The five-state-plus-modifier shape is unchanged.** The adversarial review
confirmed it as sound (its §2, §14) and this revision found no reason to
add, remove, or merge a state. What changed is what counts as a qualifying
success within that shape, and how the model handles two gaps the review
found in its enforcement.

| State | Entry criteria | Learner experience | Evidence | Exit criteria | Failure handling | Reversible? |
|---|---|---|---|---|---|---|
| **NOT_STARTED** | Default. | No engagement yet. | None. | First Lesson engagement. | — | — |
| **INTRODUCED** | Learner engaged the Lesson whose `practiceBridge` points to this skill. | Reads/watches; may replay Ghost Mode freely. | Lesson `completionRule` met. | First Terminal attempt. | N/A | Yes, freely. |
| **DEMONSTRATED_INDEPENDENT** | ≥1 attempt independently satisfies **every item** of the skill's correctness checklist (Principle 8), per the exclusion rule below. | First real Terminal success without help, meeting the full checklist. | One Recorded event flagged independent, with its satisfied checklist items. | Enters on first qualifying success. | A failed attempt does not remove INTRODUCED. | In principle yes — see NEEDS_REINFORCEMENT. |
| **CONSOLIDATED** | **≥2 qualifying independent successes on record, in any context** (interim default: **2**, explicitly PROVISIONAL — see below). A success "qualifies" if it is full-checklist and independent per Fix 2's exclusion rule; a Scenario-linked success additionally qualifying under TRANSFERRED's own restriction (below) counts here exactly as a drill success does — **revised this pass, see Fix 4.** | The "sufficient evidence, not just observed once" bar. | ≥2 qualifying independent Recorded events, drawn from any mix of drill and Scenario contexts. | — | A fresh error on this skill after CONSOLIDATED sets NEEDS_REINFORCEMENT. | Effectively yes, via the flag. |
| **TRANSFERRED** | Full-checklist **independent** success (per Fix 2's exclusion rule — **revised this pass to close a gap, see Fix 4**) inside a Scenario context specifically, per the Scenario Differentiation Contract, and only where this skill was observably necessary to that scenario's differentiating condition (§18). | Applied the skill inside a realistic case, unaided. | Scenario-linked Recorded evidence, full checklist satisfied, independence confirmed exactly as for any other qualifying success. | — | Same as CONSOLIDATED. | Same as CONSOLIDATED. |
| *(modifier)* **NEEDS_REINFORCEMENT** | A fresh error recurs on a skill at CONSOLIDATED or TRANSFERRED. Not a dormancy timer (§24). | A short re-practice prompt. | The triggering error event. | A quick, correct re-attempt (full checklist) clears the flag without demoting the state. | **Revised this pass** — see graduated demotion rule below. | Yes, by design. |

**Fix 1 — the interim default for CONSOLIDATED's repeat-count (closes the
review's P2-3, the bootstrapping problem).** Revision 1 left this number
entirely open, which meant it could not actually be implemented without
either inventing a number outside this document or stalling. This revision
sets an explicit **interim default of 2**, justified two ways: (a) it is the
smallest number that distinguishes "did it once" from "does it reliably,"
the exact distinction CONSOLIDATED exists to make; (b) Kulik & Kulik's (1987)
finding that mastery-testing effects depend more on criterion *stringency*
than on attempt count means the checklist itself (Principle 8) is doing more
of the real evidentiary work than the count — a small, honestly-labeled
default count on top of a rigorous checklist is a defensible starting point
in a way a small count on top of a vague "success" was not. **This default
is still PROVISIONAL / TO BE VALIDATED** — it is a stated starting point for
implementation, not a validated final number, and must be revisited once
real usage data exists (§34).

**Fix 2 — the independence-exclusion rule now covers feedback, not only
hints (closes the review's P1-2, the single most material finding it
raised) — mechanism corrected this pass (closes this task's Concern E; see
§13 for the full reasoning).** A success is flagged independent only if,
for that attempt: no Nudge, Partial Reveal, or Full Reveal was active
(§15); it did not immediately follow a same-command Ghost Mode reveal
in-session; **and it did not immediately follow any feedback on this skill
— delivered through any channel, including the ordinarily-uncounted
"direct correction" for FORMAT/DATA_REFERENCE errors — that stated or
clearly implied the specific correct value for a checklist item the
learner then satisfied.** Concretely: feedback content is now authored as
either **diagnostic** (names which checklist item failed and why, without
stating the fix) or **corrective** (states or strongly implies the fix).
**Correction made this pass:** this document previously said corrective
feedback should increment the *canonical hint counter* to achieve this
exclusion. On closer examination, that was the wrong mechanism — file 03's
counter has one specific, narrow, pre-existing trigger ("Hint requested |
Learner asks"), and an ordinary error the learner did not ask anything
about is not that trigger, however similar its evidentiary effect. Routing
it through the counter anyway would have silently changed what the
canonical counter *means* — from "hints the learner requested" to
"assistance events of any kind" — a real semantic drift, not a neutral
implementation detail, and exactly the kind of thing that would make the
learner-facing hint-count disclosure (file 07's hint-honesty rule) report a
non-zero count to a learner who never once clicked anything. **The
corrected mechanism:** the independence flag — already a Calculated field,
already the thing every downstream rule in this document actually reads —
is computed from *two independent inputs*: whether an assistance event
(Nudge/Partial Reveal/Full Reveal) was active, **and, separately**, whether
the immediately preceding feedback on this skill was corrective. The
canonical hint counter is untouched, keeps its original single meaning,
and is not read by this rule at all. This is one flag with two inputs, not
a second counter, and it removes rather than creates an interpretive
question for whoever owns file 03 — see §36, where the question this
correction makes moot is removed accordingly. See §13 for the authoring
discipline the diagnostic/corrective split still requires.

**Fix 3 — graduated demotion, not a flat drop (closes the review's P2-5).**
Revision 1's rule sent a skill at either CONSOLIDATED *or* TRANSFERRED down to
DEMONSTRATED_INDEPENDENT on repeated reinforcement failure, discarding
scenario-transfer evidence exactly as completely as plain repeat-success
evidence. This revision adopts a graduated rule instead: a skill at
TRANSFERRED that fails reinforcement repeatedly demotes to **CONSOLIDATED**
first (not past it) — it keeps credit for having once worked inside a real
scenario, which is stronger evidence than repeat-practice success alone and
should not be discarded by the same trigger that would demote plain
CONSOLIDATED. A skill at CONSOLIDATED that fails reinforcement repeatedly still
demotes to DEMONSTRATED_INDEPENDENT, unchanged. **The count for "repeated
failure"** is, like the CONSOLIDATED repeat-count, given an explicit interim
default of **2** consecutive failed reinforcement attempts, and is added to
§36's PROVISIONAL numbers list — Revision 1 had left this specific number
out of that list entirely, which the review correctly flagged (its P2-4) as
an inconsistent application of this document's own stated discipline.

**Fix 4 — TRANSFERRED must require independence, and CONSOLIDATED's alternate
path must carry the same anti-halo-crediting restriction TRANSFERRED
already has (new this pass, closes this task's Concern A and Concern B).**
Revision 2's original wording let TRANSFERRED's entry criteria be satisfied
by a Scenario success that never explicitly excluded assisted performance —
a real gap: the single highest state in this model could have been reached
with a hint active, which contradicts the model's own first principle
(§40, Principle #1) more seriously than any other single wording error in
the whole document, precisely because TRANSFERRED is the *strongest* claim
this design makes. Separately, CONSOLIDATED's alternate path ("1 independent +
1 Scenario pass") never applied the "observably necessary to the
scenario's differentiating condition" restriction (§18) that TRANSFERRED
does — meaning a skill used only incidentally inside the scenario could
have counted toward CONSOLIDATED through a route that bypassed the exact
halo-crediting protection §18 exists to provide. **Both are fixed the same
way, deliberately, so the two states cannot drift apart again:** a
Scenario-linked success now "qualifies" for either state only if it is
independent (Fix 2) and observably necessary to the scenario's
differentiating condition (§18) — the identical bar. A qualifying
Scenario-linked success is, by definition, both one of CONSOLIDATED's ≥2
required successes *and* TRANSFERRED's own entry evidence — which is why
CONSOLIDATED is now defined purely by *counting* qualifying successes
(drill or Scenario, mixed freely) rather than by describing two
separately-worded paths that had to be kept in sync by hand. **This is a
simplification, not an addition** — it removes duplicated language that had
already diverged once and could have diverged again, rather than
introducing a new mechanism. **Why this does not risk destroying useful
transfer evidence** (the concern's own explicit caution): the restriction
applies only to the specific skill actually being evaluated for
TRANSFERRED/CONSOLIDATED credit inside that scenario attempt — a learner who
needed help with a *different* command during the same scenario attempt
loses nothing for the skill that was performed unaided. Independence is,
and has always been, evaluated per skill per attempt everywhere else in
this document; this fix only makes TRANSFERRED and CONSOLIDATED's alternate
path consistent with a rule the rest of the model already follows, rather
than inventing a new, stricter one. **A note on why "demotes to CONSOLIDATED"
in Fix 3 still means something coherent after this change, since it would
otherwise risk circularity:** CONSOLIDATED's bar is defined by a *count* of
historical qualifying successes on record, not by whether the skill is
*currently* trusted at the TRANSFERRED tier. A skill demoted from
TRANSFERRED after failing reinforcement still has its original ≥2
historical qualifying successes on record — that count does not retroactively
un-happen — so it still satisfies CONSOLIDATED's bar on CONSOLIDATED's own,
count-based terms, independent of its current TRANSFERRED status. Nothing
in this model asks "is this skill currently TRANSFERRED?" to determine
whether it is CONSOLIDATED; it only asks "does the historical record show ≥2
qualifying successes?" — which is what keeps Fix 3's demotion rule
non-circular.

**Explicitly rejected as separate persisted states, unchanged from Revision
1:** `EXPLAINED` (redundant with INTRODUCED); `GUIDED`/`PRACTICED`/
`CORRECTED` (attributes of an attempt, not durable states); `MASTERED` (a
*read* over CONSOLIDATED + TRANSFERRED + no active flag, defined in §10, not a
stored state).

---

## 8. Skill-Specific Learning Paths & Tiering

Tiering factors and the three-tier structure are unchanged from Revision 1
— the review did not dispute the tiers themselves, only whether Tier 3 had
enough assistance granularity once inside them (its P2-7). That gap is
closed here.

| Tier | Definition | Required path | Worked example(s), with cited complexity |
|---|---|---|---|
| **1 — Simple/low-consequence** | Deterministic syntax, no preconditions, low stakes if momentarily wrong. | Introduction → independent attempt → done. | `DAC`/`DNA` decode (file 05: single-purpose lookup, no preconditions). |
| **2 — Core procedural** | Sequential dependency on other commands; central to the core chain. | Introduction → (optional Ghost Mode) → assisted attempt(s) → independent attempt(s) → CONSOLIDATED (repeat/vary) → Scenario/Transfer where available. | `AN → SS → FQD → FXP` (Decision 8A). |
| **3 — High-consequence/judgment** | Multiple documented preconditions, and/or documented destructive or narrowly-scoped behavior. | Full Tier 2 path **plus mandatory Error-Recovery Practice** exposing at least one documented failure precondition before CONSOLIDATED is reachable. **Revised this pass:** the Nudge tier for Tier-3 skills must name *which* unmet checklist item (Principle 8) is the issue, not only the general error category — see the Partial Reveal fix below. | `ER`/`ET` (three simultaneous preconditions). `XE` (cannot individually cancel SSR, mobile, email, remarks, OSI, tickets, seat assignment). |

**Checklist proportionality across tiers, added during this document's own
second self-attack (§38):** Principle 8's checklist requirement applies at
every tier, but is not the same size at every tier — a Tier 1 command like
`DAC` may have a checklist of one or two items, matching its genuinely
simple, precondition-free behavior; this is proportionate, not a shortcut.
The checklist concept should never be skipped for being "too simple to
bother," since skipping it is exactly how a vague "did it work?" bar would
quietly creep back in — but it should also never be padded with items file
05 doesn't actually document, just to look thorough.

**Fix — Partial Reveal closes the review's P2-7 (the two-level ladder was
too coarse for compound-precondition commands).** A Nudge that only names
"this looks like a MANDATORY_MISSING issue" for `ER`/`ET` doesn't tell the
learner *which* of three simultaneous preconditions is unmet, forcing an
unnecessary jump straight to a full answer. Grounded in the guidance-fading
research cited in Principle 2 (§5) — worked-example support should reduce
in graduated steps, not all at once — this revision adds one content
depth between Nudge and Full Reveal, formalized in §15:

- **Nudge** (unchanged): names the general error category only.
- **Partial Reveal** *(new)*: for Tier 3 skills specifically, names **which
  checklist item** (Principle 8) is unmet, without stating the fix for it —
  e.g., "two of the three requirements for `ET` are met; the passenger count
  doesn't yet match the sold-seat count" names the *which*, not the *what to
  type*.
- **Full Reveal** (renamed from "Full hint" for symmetry with the checklist
  language; unchanged in function): states the specific correction.

This is one counter with three content depths, not two counters — it does
not reopen the canonical single-hint-counter rule (file 03), and Partial
Reveal is diagnostic under §7's Fix 2 (does not trigger exclusion on its
own), while Full Reveal remains corrective (does).

**LEARNING DESIGN DECISION, PROPOSED, unchanged:** full tiering of all 37
commands remains deferred to per-lesson curriculum authoring; this document
supplies the rubric, not the assignment.

---

## 9. Core Learning Loop

**Restructured this revision** around the twelve-stage pipeline this task's
governing brief specifies, mapped explicitly onto DEIXEN's actual
mechanisms rather than left as a Revision-1-style single paragraph. Nothing
in this restructuring adds a new product area, screen, or evidence class —
every stage below already exists in some form in files 03–07 or in this
document's other sections; this section is the connective tissue, made
explicit end to end.

| Stage | DEIXEN mechanism | Owning section |
|---|---|---|
| **LEARN** | Lesson content via its `practiceBridge` link; optional Ghost Mode demonstration (recognition-level, non-evidentiary). | §6, §12, §16 |
| **RETRIEVE** | First Terminal attempt requiring the learner to produce, not recognize, the command — the mechanism Principle 1 exists to require. | §12 |
| **PRACTICE** | Repeated attempts, varied per Tier 2/3's repeat/context requirement. | §11 |
| **FEEDBACK** | Verbatim official message plus diagnostic-or-corrective explanation, per the unified rule in §13. | §13 |
| **CORRECTION** | Learner self-corrects, or accepts Coach assistance at the appropriate content depth (§15). | §13, §15 |
| **REPEAT** | Retry; no state regression on a single failure (§23). | §23 |
| **INDEPENDENT PERFORMANCE** | Full-checklist success with no active assistance and no immediately-preceding answer-revealing content, of any kind (§7 Fix 2) — DEMONSTRATED_INDEPENDENT. | §7 |
| **ASSESSMENT** | Either the informal practice-embedded check or the formal Assessment session, per the Assessment State Contract; for the frozen slice, feeds the one owned record, evaluated per Kane's validity framework (§20). | §20 |
| **EVIDENCE** | Recorded via the four-field Event Log plus Calculated derivations (independence flag, checklist-item satisfaction, chain correlation where applicable) — each flagged in §29 as an implementation dependency, not assumed. | §21 |
| **PROGRESSION** | Flight Deck's existing "next recommended action" role, evidence-linked only (§23). | §23 |
| **REINFORCEMENT** | A fresh error on an already-CONSOLIDATED/TRANSFERRED skill sets NEEDS_REINFORCEMENT (§7); new this revision, an optional spaced retrieval prompt runs alongside this as a proactive complement (§24). | §7, §24 |
| **TRANSFER** | Success inside the one available Scenario, restricted to skills the scenario's own acceptance criteria actually exercised (§18) — TRANSFERRED. | §18 |

---

## 10. Completion / Competence / Mastery / Transfer / Retention — Definitions

All **LEARNING DESIGN DECISION**, built on §7. Updated to reference the
correctness checklist (Principle 8) wherever "success" previously appeared
unqualified.

| Term | Meaning | Evidence required | Insufficient evidence | Relationship to progression |
|---|---|---|---|---|
| **Lesson Completion** | The Lesson's own `completionRule` is satisfied. | Whatever that rule specifies. | Opening a lesson without meeting its rule. | Enables, does not require, the first Terminal attempt. |
| **Skill Completion** | First reach of DEMONSTRATED_INDEPENDENT: the learner has met the skill's **full correctness checklist**, unaided, at least once. | One qualifying independent Recorded event, checklist-complete. | Any assisted success; any success immediately following answer-revealing content of any kind (§7 Fix 2). | Recommends repeat/variation toward CONSOLIDATED for Tier 2/3. |
| **Competence** | CONSOLIDATED: **≥2 qualifying independent successes on record** (interim default 2, PROVISIONAL), counted from any mix of drill and Scenario contexts — a Scenario-linked success only qualifies under the same independence and anti-halo-crediting terms as Transfer, below (§7 Fix 4). | ≥2 qualifying independent Recorded events. | A single success, however clean — even a checklist-complete one; an assisted success in any context, drill or Scenario. | Recommends Scenario/Transfer where available. |
| **Mastery** | **Not a stored state.** A *read*: CONSOLIDATED **and** TRANSFERRED **and** no active NEEDS_REINFORCEMENT flag. **RECOMMENDATION, unchanged:** avoid the word "mastery" in learner-facing copy for any Amadeus-domain skill until Decision 7's SME validation executes (Principle 6) — say "consistently correct in DEIXEN." | Union of CONSOLIDATED and TRANSFERRED evidence. | Either alone. | Not a gate to anything further within the frozen slice. |
| **Transfer** | TRANSFERRED — checklist-complete **independent** success inside the one available Scenario, restricted to skills its acceptance criteria actually exercised (§18) — **revised this pass (§7 Fix 4): an assisted success inside the Scenario no longer qualifies, closing a real gap where the model's highest state could previously have been reached with a hint active.** | Scenario-linked Recorded evidence, independence confirmed exactly as for any other qualifying success. | Scenario "passed" without this specific skill being load-bearing to it; any assisted success, however clean the eventual command syntax looked. | — |
| **Retention** | **Revised this pass (closes this task's Concern C) — three states, not one, so that "nothing observed" and "confirmed fine" stop reading identically:** (1) **No decay observed** — no NEEDS_REINFORCEMENT flag has fired since the last qualifying success; this is the current definition's entire prior scope, kept but renamed for precision. (2) **Not recently re-observed** — a qualitative flag, not a numeric threshold: whenever a UI/Coach surface would otherwise imply "retained," it must instead show or be computable from the last qualifying event's own timestamp (already-logged Event Log data), so the reader can judge recency themselves rather than the system asserting a binary "retained: yes." (3) **Retention re-demonstrated** — a *new*, genuinely positive data point: a checklist-complete independent success occurring after a gap, whether the gap ended via an ordinary return to practice or via the optional spaced-retrieval prompt (§24) succeeding. Only (3) is positive evidence; (1) is merely an absence of contrary evidence; (2) is a reminder that (1) can describe a skill touched yesterday and a skill untouched for months identically, and no downstream surface may treat them as the same claim. | For (1): no qualifying error-recurrence since the last success. For (3): a fresh qualifying independent success after a genuine gap. | Time passing alone, with no observation either way, is (2) — never silently upgraded to (1) or (3). Engaging the optional spaced-retrieval prompt (§24) is never itself evidence of any of the three — only a subsequent checklist-complete success is, and that success is (3), an ordinary Recorded event, not a stronger or separately-weighted kind of proof. This distinction matters because a feature that *exists to support* retention is an easy thing to mistake for a feature that *proves* it. | Feeds §24's reinforcement loop; (3) specifically is what a spaced-retrieval engagement is meant to eventually produce. |

No numeric threshold above is asserted as *validated* — the two counts that
now exist (CONSOLIDATED's repeat-count, the reinforcement-failure count) are
explicit interim defaults, both carried as **PROVISIONAL / TO BE VALIDATED**
in §7, §20, §35, and §36.

---

## 11. Practice Architecture

Evaluated against the same candidate list as Revision 1; adopted only where
a specific §4 gap justifies it (Principle 9). Two items are revised this
pass.

**Adopted, unchanged:**

- **Retrieval practice** — the independent-attempt requirement in §7 *is*
  this mechanism.
- **Varied repetition** for Tier 2/3 — CONSOLIDATED requires more than one
  qualifying success.
- **Fading support** — see the three-content-depth ladder in §15.
- **Error-Recovery Practice** for Tier 3, mandatory; recommended for Tier 2
  — now with the error-management-training rationale in Principle 7 (§5).
- **Timed practice (Speed Drills)** — see §17.

**Fix — workflow-level chained practice, honesty about its evidentiary
requirement (closes the review's P1-3).** Revision 1 recommended that,
after each of the frozen slice's four commands independently reaches
DEMONSTRATED_INDEPENDENT, the learner also complete `AN → SS → FQD → FXP`
as one continuous, unaided sequence — and asserted this needs "no new
canonical field required." The review correctly identified this as
inconsistent: proving four specific events form one continuous,
gap-free, non-interleaved sequence from a four-field, non-session-
correlated Event Log is at least as demanding as the single-event
hint-adjacency question (§7's Fix 2), which this document has always
treated as an open dependency. **This revision withdraws the "no new field
required" claim and replaces it with the same honesty already applied
there:** reconstructing chain continuity from the existing four fields
alone is **OPEN, not assumed** — plausible if strict same-session temporal
adjacency with no intervening event of a different command family proves
sufficient, but this has not been confirmed, and a minimal correlation
identifier (e.g., a shared attempt-group value) may turn out to be
genuinely necessary. Either resolution is acceptable; asserting one without
checking is not. This is now stated identically in §21 and §29 so the
dependency is visible everywhere it matters, per this task's instruction to
preserve a learning requirement and mark the implementation dependency
rather than assume capability that hasn't been established.

**Fix — self-corrected errors within the chain do not void "continuous,
unaided" status (closes the review's P2-8).** Revision 1 left this
unspecified. This revision decides it directly, with reasoning: the purpose
of workflow-level practice is to test whether the learner can complete the
real task relying on their own judgment, not whether they type every
character perfectly on the first pass. A learner who notices and fixes
their own slip — with no Nudge, Partial Reveal, Full Reveal, or answer-
revealing feedback involved — has demonstrated exactly the judgment this
practice exists to test. **LEARNING DESIGN DECISION:** a self-corrected
error, with zero assistance of any kind, does not void the chain's
"continuous, unaided" status; any assistance at any point does.

**Deferred, unchanged:**

- **Interleaving** — no second skill exists to interleave with yet.
  **REJECTED/DEFERRED — not applicable yet.**
- **An adaptive/algorithmic difficulty engine** — contradicts Platform
  Direction's anti-premature-infrastructure principle. **REJECTED** for the
  current phase.

---

## 12. Retrieval vs. Recognition

Ghost Mode and a Lesson's `example` field remain **recognition-level**: the
learner observes, they do not produce. This is valuable for initial
exposure and is **explicitly not evidence** of anything beyond INTRODUCED
(§7) — unchanged from Revision 1.

**LEARNING DESIGN DECISION, unchanged:** Ghost Mode completion can never by
itself move a skill past INTRODUCED, and may therefore be replayed on
request without limit.

**Extended this revision, grounded in Principle 2 (§5):** the assistance
ladder's new **Partial Reveal** tier (§8, §15) sits deliberately between
pure recognition (Full Reveal, Ghost Mode) and pure retrieval (an unaided
attempt) — it is a *faded* worked example, showing the learner which part
of the task is wrong without showing the solution, which is exactly the
guidance-fading pattern Renkl & Atkinson's (2010) research describes as the
bridge between the two. A success following a Partial Reveal is **not**
retrieval-adjacent in the same disqualifying sense as one following a Full
Reveal (§7 Fix 2) — the learner still had to retrieve the actual fix
themselves, only the location of the problem was named. This is why Partial
Reveal is diagnostic, not corrective, under §13's rule below.

The same unified rule now applies across all three channels — Ghost Mode,
the assistance ladder, and ordinary feedback: any content that states or
clearly implies the specific correct value disqualifies the immediately
following success from independent evidence; content that only narrows
*where* the problem is does not. This is stated once here and applied
consistently in §13 and §15.

---

## 13. Feedback Architecture

Builds on the already-**CURRENT PRODUCT DECISION** error-message discipline
(files 05, 06) — verbatim official message always shown, plain explanation
alongside, never a replacement — and the category-depth principle
(format/data-reference get a direct correction; sequence/logical may link
back to a lesson, file 06). This document still does not fill in file 06's
own deliberately deferred full per-category response matrix.

**The central fix this revision makes (closes the review's P1-2, its most
material finding):** Revision 1 drew a line between "hints" (Coach-
initiated, counted) and "feedback" (canonical, always-on, uncounted) as if
they were different kinds of thing for evidence purposes. They are not —
both can equally reveal the answer, and only one of them was being tracked.
This revision replaces that line with a content-based one that applies to
*both* channels identically:

- **Diagnostic feedback/assistance**: names the error category, or (for
  Tier 3, via Partial Reveal) names which specific checklist item (Principle
  8) failed — **without** stating or clearly implying the correct value.
  Never affects independence.
- **Corrective feedback/assistance**: states or clearly implies the
  specific correct value — whether delivered as a Coach-initiated Full
  Reveal *or* as an ordinarily-uncounted "direct correction" for a FORMAT
  or DATA_REFERENCE error. **Always sets the independence flag to false for
  the immediately following attempt on this skill (§7 Fix 2), regardless of
  which channel delivered it.**

**Mechanism correction made this pass:** the flag above is a *separate*
Calculated field, not the canonical hint counter (file 03). The counter
keeps its original, single meaning — a count of learner-*requested*
Nudge/Partial Reveal/Full Reveal events — and is never incremented by
ordinary error feedback, which the learner did not ask for. See §7 Fix 2
for why this correction matters and what it changes.

**An operational test for the diagnostic/corrective line, added this pass
because "does it name the problem without stating the fix" still leaves
real judgment calls at the boundary:** ask whether the content, combined
with the checklist item it references, lets the learner produce the
correct command without further trial-and-error of their own. If yes, it
is corrective, however gently worded. If the learner would still have to
work out the specific fix themselves, it is diagnostic, however precisely
it names the problem. This is a sharper test than "does it feel like an
answer," but it remains a judgment call in genuinely borderline cases — see
§30's second-reviewer recommendation and §38's honest acknowledgment that
this line is not, and may never be, perfectly crisp.

**What this means for content authoring, stated plainly because it is the
whole point of the fix:** a FORMAT-error explanation like "the month should
be a 3-letter code" is corrective (it states the fix) and must be authored
and reviewed as such; "the month portion of your command doesn't match the
expected format" is diagnostic (it names the problem, not the fix) and does
not affect independence. This is a real, non-trivial authoring discipline —
Coach content for FORMAT/DATA_REFERENCE errors, previously assumed to be
low-stakes "just tell them," now needs the same diagnostic-vs-corrective
review any hint content gets. This is also independently supported by
Hattie & Timperley's (2007) feedback research: diagnostic, process-level
guidance ("what's wrong and how to think about it") is consistently found
more effective for learning than feedback that simply hands over the
correct answer — the fix that closes the evidence-integrity gap and the
fix that the general feedback-effectiveness literature would recommend
happen to be the same fix here, which is a genuine point in its favor, not
merely a coincidence this document is claiming credit for.

**Unchanged from Revision 1:**

- **Timing:** feedback on command validity is immediate, matching
  Terminal's existing skeleton.
- **Repeated-error escalation:** if the same error category recurs on the
  same skill more than a small number of times within one session, Coach
  escalates from direct correction to the deeper lesson-link treatment. The
  count remains **PROVISIONAL / TO BE VALIDATED** — illustratively 3.

---

## 14. Error & Recovery Architecture

Uses the existing 8-category taxonomy verbatim (file 05) — nothing here
creates a competing taxonomy. Same two depth-clusters as Revision 1:

| Cluster | Categories | Detection → Explanation → Correction → Re-attempt → Assistance | Evidence impact | Remediation |
|---|---|---|---|---|---|
| **Lighter-touch** | `FORMAT`, `DATA_REFERENCE`, `AVAILABILITY`, `GENERAL` | Immediate; verbatim message + a **diagnostic-by-default** plain-language note (§13) — authored to name the problem, not the fix, unless the author deliberately marks it corrective. | Diagnostic: no impact. Corrective: counted exactly like a Full Reveal (§13). | None beyond retry, unless repeated (§13 escalation). |
| **Deeper-touch** | `SEQUENCE`, `MANDATORY_MISSING`, `DUPLICATE_CONFLICT`, `LOGICAL` | Immediate; verbatim message + explanation linking to the relevant lesson, framed diagnostically per Principle 7 (§5) — as information about which condition is unmet, not as a failure. | Same rule as above. | Repeated same-category errors trigger escalation sooner, since these more often reflect a conceptual gap than a typo. |

**Error framing, new this revision (Principle 7, §5):** all Coach copy
touching an error — at either cluster, at any assistance tier — is authored
to describe *what condition is currently unmet*, never to imply the learner
made a mistake they should feel bad about. This is a direct, low-cost
application of error management training's finding that explicit
"errors are informative" framing was the active ingredient in its measured
transfer benefits (Keith & Frese, 2008) — not a generic tone preference.

**Special case — Known Issue #7, refined this revision (extends the
review's P2-9).** The live per-command echo hardcodes the wrong element
number for `AP`, `TK`/`TKTL`, and `RF` regardless of true position, while
the final PNR's real numbering (via `formatPnrLines()`) is computed
correctly (file 05). Revision 1 flagged that a disclaimer or Coach warning
was needed; the review correctly pointed out that a warning not to trust
the live number is incomplete without telling the learner where the
*correct* number can be found. **This revision adds that missing half as an
explicit requirement, not just a warning:** before any Tier 3 practice that
requires referencing a PNR element by number (most directly `XE`), either
(a) an implementation-confirmed, accurate pre-completion numbering view
must be identified and used as the authoritative source in lesson/Coach
content, or (b) if none exists, `XE` practice must be sequenced to occur
only after the PNR is ended/retrieved (`ER`/`ET` then `RT`), where the
correctly-computed numbering is confirmed available — **not** taught as a
mid-build action until the underlying bug is fixed. **OPEN QUESTION,
unchanged in substance, sharpened in requirement:** which of (a) or (b)
applies is a technical confirmation this document cannot perform (see §36).

---

## 15. Coach / Assistance Architecture

Same starting constraint as Revision 1: canon establishes a **single** hint
counter "incremented in exactly one place" (file 03). Multiplying content
*depth* without multiplying the *counter* stays inside that rule; adding a
second counter would not.

**Adopted — three content depths under the one existing counter, revised
this pass (closes the review's P2-7 and formalizes §8's Partial Reveal):**

1. **Nudge** — names the general error category without revealing the fix.
   Diagnostic (§13). Increments the counter (unchanged from Revision 1 —
   Nudge was always counted, even though it never disqualifies the next
   success on its own, since a category name isn't an answer).
2. **Partial Reveal** *(new)* — for Tier 3 skills, names **which checklist
   item** (Principle 8) is unmet, without stating the fix. Diagnostic
   (§13). Increments the counter. Does not, on its own, disqualify the
   immediately-following success from independent evidence, for the same
   reason a Nudge doesn't — naming the location of a problem is not the
   same as handing over the solution (§12).
3. **Full Reveal** (renamed from "Full hint") — states the specific
   correction. Corrective (§13). Increments the counter. A success
   immediately following it **is** excluded from independent evidence
   (§7 Fix 2), as in Revision 1.

**Note on the relationship between this counter and independence, stated
precisely this pass to avoid the two being conflated:** the counter above
tracks *learner-requested* assistance only, and keeps file 03's original
meaning unchanged. Whether a given attempt counts as independent is a
separate, Calculated determination (§7 Fix 2) that considers both this
counter's activity *and*, independently, whether the preceding ordinary
error feedback was corrective — the two inputs are combined only at the
point of computing independence, never by making one mechanism stand in
for the other.

**Explicitly rejected, unchanged:** `Conceptual Guidance`, `Structural
Guidance`, `Demonstration`, `Reveal` as additional distinct Terminal-
assistance levels beyond the three above — "Demonstration" already exists
as Ghost Mode, and the review did not find a case for reopening this
rejection.

**When assistance appears:** learner-initiated by default, unchanged. The
one exception is §13's repeated-error escalation, an offer, not a forced
interruption.

**Fix — one narrow, well-grounded step on Coach dependency (partially
closes the "Coach-as-crutch, honestly unresolved" gap named in both
Revision 1's §38 and the review's Special Question 3).** Revision 1
proposed no Coach-proactivity fading at all. This revision does not invent
a general fading algorithm — no usage data exists to calibrate one, and
inventing one would violate Principle 9. It does adopt one specific,
low-cost, well-grounded instance: **once a skill reaches CONSOLIDATED, the
repeated-error escalation offer (§13) no longer fires automatically for
that specific skill** unless the NEEDS_REINFORCEMENT flag is active for it.
Rationale: the learner has already demonstrated they don't need the
escalation path for this skill; continuing to offer it anyway is exactly
the kind of support the cognitive-load "expertise reversal effect" (Sweller
& Cooper 1985, cited in Principle 2) predicts becomes unhelpful, or mildly
counterproductive, once a learner has moved past the novice stage for that
specific skill. This is narrow by design — it fades one specific,
already-earned behavior for one specific skill, not Coach's general
proactivity — and is tagged **LEARNING DESIGN DECISION** on structure,
**VALIDATION HYPOTHESIS** on whether learners actually notice or benefit
from it. **What remains genuinely, honestly unsolved:** whether Coach's
*general* eagerness to offer help (not just this one escalation path)
should fade as a learner's overall CONSOLIDATED count grows. This document
still does not propose that broader mechanism — see §38.

**The direct test this document must always answer honestly — can a
learner pass without understanding?** Yes, still possible, for the same
reason stated in Revision 1: this design stops the *system* from crediting
assisted or recognition-level success as independent; it cannot force
genuine understanding, and does not claim to. The P1-2 fix (§13) closes one
specific route by which the system itself could be fooled; it does not, and
cannot, close the human possibility of a learner disengaging from genuine
effort while still technically satisfying the checklist.

---

## 16. Ghost Mode

Respects the verified JSON schema in full (file 06) — nothing here changes
it. Ghost Mode completion never advances a skill past INTRODUCED, and
remains safe to replay without limit, unchanged from Revision 1.

**New this revision — an honest, low-severity note the review raised
(its P3-3), not a design change:** unlimited free replay is correctly safe
from an *evidence* standpoint. It is a distinct, open question whether heavy
reliance on it creates a confidence-reality gap — a learner who replays a
demonstration many times may feel more prepared than their first unaided
attempt then shows. This is plausible given the cognitive-load "expertise
reversal effect" (a worked example that helped early can stop helping, or
even mislead, once a learner should be moving toward independent practice —
Sweller & Cooper 1985) but is not established for DEIXEN specifically.
**VALIDATION HYPOTHESIS**, added to §34 — worth watching once real learners
exist, not worth restricting Ghost Mode over in the absence of evidence it's
actually a problem.

---

## 17. Speed Drills

Respects the existing mechanic in full (file 06). Unchanged: the
CONSOLIDATED-prerequisite gate, and the CPM-threshold no-fabrication rule.

**Fix — the handling of a wrong rep is now a specified mechanism, not just a
stated principle (closes the review's P3-4).** Revision 1 said a fast,
wrong rep "should not be a positive data point" without saying how.
**LEARNING DESIGN DECISION:** a Speed Drills rep that fails the skill's
correctness checklist (Principle 8) is **excluded entirely** from the CPM
calculation — not counted as a zero, not counted as a slow attempt, simply
not included in the trend. This is the cleanest of the three options
considered (exclude / count as zero / count as a qualifying-but-slow
attempt): counting a wrong rep as zero would visually crater a trend line
over something that isn't a speed problem at all, and counting it as a slow
correct attempt would misrepresent what happened. Exclusion keeps the CPM
trend meaning exactly what it claims to mean — speed, among attempts that
were actually correct.

**Unchanged:** accuracy-must-be-correct-to-count as the underlying rule;
explicit exclusion from Growth/Readiness evidence — Speed Drills data feeds
only the learner's own personal trend, never a competence or CONSOLIDATED
determination.

**Re-examined this pass (this task's Concern G) and confirmed, with one
addition.** Exclusion remains the cleanest rule for the CPM number itself —
nothing found this pass changes that. A separate risk was found, though:
pure exclusion is susceptible to a survivorship effect — a learner who
rushes and fails often, but is fast on the attempts that happen to succeed,
would show the same or a better CPM trend than a careful learner who is
usually right but slightly slower, because the failures simply vanish from
the number rather than costing anything visible. Left alone, this could let
a rising CPM trend read as "getting better" when accuracy-under-time-
pressure is actually degrading. **The fix is an interpretation boundary,
not a new metric** — per this task's own explicit instruction not to build
composite measurement machinery: any surface displaying the CPM trend must
display, alongside it, the exclusion count or rate for the same window.
This requires no new logic — a rep's pass/fail against the checklist is
already computed to decide exclusion; this only requires that already-
computed fact to be shown, not swallowed. This directly targets the
concern's named risk ("high speed = high competence") without adding a
composite index, a threshold, or a second metric.

---

## 18. Scenario / Transfer Architecture

Uses the Scenario Differentiation Contract verbatim (file 07) — nothing
here restates its substance. TRANSFERRED status still attaches only to
skills the scenario's own acceptance criteria actually required, unchanged
from Revision 1. **Confirmed this pass:** this restriction now travels
together with an explicit independence requirement (§7 Fix 4) — a skill's
use inside the Scenario counts toward TRANSFERRED only if that specific
use was both load-bearing to the scenario's differentiating condition
*and* unaided; the two restrictions are applied together, not as
alternatives.

**Extended this revision, grounded in Baldwin & Ford (1988), cited in
Principle 5 (§5):** transfer of training depends on three factors — trainee
characteristics, training design, and work environment — and training
design's effect on real transfer is itself indirect, mediated through
learning and retention, not guaranteed by good design alone. Stated plainly
because it bears directly on what this document can and cannot claim: **the
one available Scenario, however well it is built, can only ever exercise
the first two of Baldwin and Ford's three factors.** The third — the real
Saudi/Gulf call-center work environment itself — is structurally outside
this product's reach, and no amount of learning-design rigor changes that.
This is not a new limitation this revision invents; it is the same
domain-truth boundary (Operating Constitution §3, Decision 7) restated in
transfer-of-training terms, made explicit here so it travels with any
future TRANSFERRED-status reporting rather than being implicit.

**Stated plainly, unchanged in substance from Revision 1:** the frozen
slice has exactly one scenario. TRANSFERRED status for its four commands
currently means "shown to work in the one available context," not "shown to
generalize" — this is what Decision 8A was scoped to prove, and this
document remains explicit about the difference.

---

## 19. Customer Service Learning

Respects the existing five-lesson structure in full (file 06) — no lesson is
added, removed, or reordered. Objective character per lesson, unchanged
from Revision 1:

| Lesson | Objective character |
|---|---|
| 1. Passenger Profiling & Types | Recognition — identifying passenger type/need from a description. |
| 2. Professional English Scripts | Recall/application — selecting and adapting language in the moment. |
| 3. De-escalation & Conflict Resolution | Applied decision-making under simulated pressure; the Anger Meter's home lesson. |
| 4. Cross-selling & Upselling | Applied communication with a business-outcome dimension. |
| 5. Scenario-Based Simulations | The track's transfer point — a real Terminal command paired with an English response. |

**Fix — an explicit scope statement for the skill-state model (closes the
review's P2-2).** Revision 1's §7–§24 apparatus is designed and evidenced
almost entirely in Amadeus/Terminal terms, and this was never stated
outright. **Stated explicitly now: the five-state skill model (§7), the
correctness-checklist concept (Principle 8), and the assistance ladder
(§15) do not currently apply to Customer Service Lessons 1, 2, and 4.**
"Success" for a CS dialogue choice is undefined absent the choice-quality
rubric named as missing below, and no skill-state machinery can
meaningfully run on an undefined success criterion. This is not a new
restriction — it is a direct, honest consequence of Decision 6 (file 07)
already requiring CS to have its own content model, assessment logic, and
evidence pathway before any proficiency claim can be shown. Lesson 5 is the
one exception, addressed below, because its technical half genuinely is an
Amadeus-command skill.

**Critical evaluation of the Anger Meter, unchanged conclusion from
Revision 1:** the meter moves based on response-choice quality and every
movement is logged as its own Event (file 06, **VERIFIED FACT**) — but an
Event being logged only establishes that a choice was made, not that the
choice was competent, absent a documented rubric, which does not exist in
the nine canonical files. **LEARNING DESIGN DECISION, unchanged:** the
Anger Meter is classified as **Illustrative** evidence (file 07's own
class) until a documented choice-quality rubric exists.

**New gap named this revision, not previously identified in Revision 1
(closes the review's P2-11):** the CS track has no documented feedback or
explanation mechanism at all — unlike Amadeus's rigorous verbatim-message-
plus-explanation discipline, nothing states whether a poor dialogue choice
comes with any explanation of *why* it was rated as it was, beyond the
meter moving. This risks "error → meter moves → retry" without an
"understand" step ever being confirmed to exist, which Hattie & Timperley's
(2007) feedback research (§3) would predict is close to the least effective
feedback pattern available — task-level-only feedback with no process
guidance. **This document does not author the missing rubric or feedback
content** — that remains CS-domain-expert work, correctly gated behind
Decision 6's own pending contract, exactly as Revision 1 already
established for the rubric itself. What this revision adds is a
**RECOMMENDATION** naming the specific principle that content should follow
once authored: at minimum, a dialogue choice's feedback should state which
aspect of the response was weaker (tone, information, timing — a diagnostic
statement), not only move a meter — the same diagnostic-over-corrective
discipline already adopted for Amadeus feedback in §13, extended in
principle, not in content, to CS. **OPEN QUESTION, also newly named:**
whether a learner can retry the same dialogue choice point with a better
response, or whether the scenario branches irreversibly, is undocumented
anywhere in the nine files — this affects whether "retry" means the same
thing for CS as it does for Terminal, and is content-architecture work this
document does not resolve (§36).

**Fix — Lesson 5's hybrid evaluation rule, previously entirely undefined
(closes the review's P1-4, the fourth of its major findings).** File 06
names Lesson 5 as combining "a real Terminal command from the implementable
set" with "an appropriate English response" — the track's one deliberate
technical/CS integration point — but neither Revision 1 nor any canonical
file stated how the two halves are evaluated. Attempting to walk this
lesson through a learner journey (as the external review did) stalls
immediately for exactly this reason. **LEARNING DESIGN DECISION, closing
the gap:** the Terminal-command half and the English-response half of a
single Lesson 5 interaction produce **two separate evidentiary events**,
each governed entirely by its own track's rules — the command half feeds
the normal Amadeus skill-state model (§7) for that specific command; the
English-response half feeds only the CS track's own (still-pending)
evidence pathway under Decision 6. **Neither half may compensate for the
other**: a correct command with a poor English response does not inflate
the CS-side record, and a strong English response with an incorrect command
does not credit the command as independently performed. This is the
smallest rule that prevents Decision 6's wall from being breached by
accident the first time this lesson is actually built, and it requires no
new evidence class or Event Log field — it is a scoring-time rule about how
to interpret two events that already exist separately in the model.

This is consistent with, and directly enforces, Decision 6's existing rule
that no CS proficiency/readiness metric may be shown as measured evidence
until CS's own contract is defined.

---

## 20. Assessment Architecture, Validity & Sampling

Uses the Assessment State Contract verbatim (file 07) — continuous
current-session state, no history-wipe on entry, no cross-session merging,
accurate hint-count disclosure. Unchanged. The same two-function collapse as
Revision 1 (practice-embedded check vs. formal Assessment session) stands —
the review did not dispute it.

**Fix — an explicit validity framework replaces an implied one (closes the
review's P2-1, the assessment-content-reuse concern).** Revision 1's
sampling table stated the frozen slice's evidence is "bounded to the one
available Scenario's one context" without a structure for saying precisely
what that does and doesn't support. This revision applies Kane's (1992;
2013) argument-based validity framework (§3) — four inferences, evaluated
honestly rather than assumed:

| Inference | Question it asks | DEIXEN's current status |
|---|---|---|
| **Scoring** | Does the method for turning an observed attempt into a recorded result actually capture what happened? | **Reasonably supported at the design level only — corrected this pass to say so explicitly.** The correctness checklist (Principle 8) plus the diagnostic/corrective feedback split (§13) give scoring real structure on paper; whether it is *actually* captured correctly depends entirely on the same Event Log confirmation already flagged as this document's single highest-priority open dependency (§21) — Scoring strength should be read as conditional on that confirmation, not as independently established. |
| **Generalization** | Does the specific assessed task represent the wider universe of conditions the skill covers? | **Weak, and honestly so — reworded this pass for technical precision.** The universe of real conditions a command like `AN` could appear under (city pairs, dates, passenger counts) is not itself small; what is small is the *sample* DEIXEN currently draws from it — exactly one scenario, one task instance. Generalization evidence would require assessing performance across a meaningfully varied sample of that universe; repeating the same single instance, however many times, does not enlarge the sample. This is the precise, technical version of the review's concern: the formal "Assessment session" necessarily reuses the same commands and scenario the learner already practiced with. |
| **Extrapolation** | Does assessment performance predict real-world (real Amadeus, real call-center) performance? | **Not claimed, correctly.** This is exactly Decision 7's own open item — no document-level design substitutes for SME validation, and this revision does not pretend Generalization or Scoring strength implies Extrapolation strength. |
| **Implications** | Are the consequences drawn from the assessment appropriate to its actual strength? | **Deliberately modest, and correctly so** — the frozen slice authorizes only one bounded qualitative Growth/Readiness status (file 07), never a number, precisely because the chain above is only strong at its first link. |

**What this table changes in practice:** the frozen slice's "1 owned
assessment record" (Decision 8A) should be described, in any future
reporting, as evidence that **the pipeline works end-to-end for one learner
on one occasion with one task instance** — not as a general competence
claim, and not merely as "assessed," a word that on its own implies more
of Kane's chain is supported than currently is. This is not a new
restriction on Decision 8A's scope (file 07's own "proves the pattern can
scale" framing already said this); it gives that existing restriction a
named, checkable structure instead of an implicit one, which is what the
review's P2-1 finding was actually asking for.

Sampling/validity terms, unchanged from Revision 1 and now compatible with
the table above:

| Term | Definition | What it does NOT establish |
|---|---|---|
| **Observed success** | Any single successful attempt, at any assistance level. | Not evidence of reliability, independence, or transfer. |
| **Sufficient evidence for a credible claim** | ≥2 qualifying independent successes on record (§7's CONSOLIDATED bar, drill or Scenario, mixed freely under the same independence and anti-halo-crediting terms — §7 Fix 4). | Sufficient for a credible claim of competence at this skill in this slice — not for Generalization or Extrapolation, per the table above. |

---

## 21. Evidence Architecture

The Event Log's four fields (event type, command, result, timestamp — file
03) remain fixed. **No additional canonical field is invented in this
document**, and this revision is more precise than Revision 1 about what
that restraint actually costs.

**Elevated this revision — the single most consequential open item in this
entire design, stated with that priority explicitly, not left to be
inferred (responds to the review's P1-1, which formally classified this as
its top validation dependency).** Every skill-state transition (§7),
including the correctness-checklist mechanism this revision adds, depends
on the Event Log supporting: (a) computing the independence flag for a
single attempt — which now depends on two things, whether a Nudge/Partial
Reveal/Full Reveal was active (the counter) *and, separately*, whether the
immediately preceding feedback was corrective (§7 Fix 2, corrected this
pass) — and (b) — as of this revision's honesty fix in §11 — multi-attempt
sequence continuity for chained practice. Neither is confirmed. **If either
resolves unfavorably, every downstream skill-state, CONSOLIDATED, and
TRANSFERRED determination in this document inherits the same
unreliability, silently, unless someone checks first.** This document
recommends, as its single highest-priority pre-implementation action, that
the delegated evidence/state schema pass (file 13) confirm both questions
before any of the mechanisms described above are built as specified — not
after, and not incidentally alongside other schema work.

**Unchanged:** what **Calculated** evidence (file 07's class) may
legitimately derive from the four fields — the independence flag (now
explicitly two-input, per the correction above, but still one Calculated
field, not a second counter), the learner-requested-hint count, CPM
(already canonical), the error-recurrence signal — plus, new this
revision, checklist-item satisfaction per attempt and (pending the above
confirmation) chain-sequence correlation. None of these are asserted as
already implemented.

**Evidence Truth vs. UI Progress separation, unchanged, RECOMMENDATION:** a
progress indicator must always be a live projection of underlying evidence,
computed at render/query time, never a separately incremented counter that
can drift.

---

## 22. Longitudinal Learner State (Conceptual Only)

Unchanged from Revision 1 — no new learner database is proposed. The
minimal conceptual inputs needed to reason about a skill over time: recency
of last independent success, independent-vs-assisted history (now including
which content depth — Nudge, Partial Reveal, or Full Reveal — was
involved), which contexts it's been shown in, consecutive same-category
errors, whether NEEDS_REINFORCEMENT is active, and, new this revision,
whether an optional spaced-retrieval prompt (§24) has been offered and
engaged. These remain reasoning inputs for this design, not a mandate —
actual persistence decisions stay owned by the delegated evidence/state
schema work (file 13).

---

## 23. Progression Rules

All evidence-linked, per Principle 4 — never lesson-viewed, button-clicked,
time-spent, attempt-count, single success, or a decorative score, alone.
Unchanged from Revision 1 except where a rule's trigger now references the
correctness checklist explicitly.

| Rule | Trigger | Effect |
|---|---|---|
| **Advance** | Skill reaches DEMONSTRATED_INDEPENDENT (full checklist, §7). | Flight Deck's "next recommended action" may surface the next skill in the frozen sequence. |
| **Repeat** | An attempt fails any checklist item. | Terminal shows Invalid per its existing skeleton; learner retries the same skill; no state regression. |
| **Remediate** | Repeated same-category errors (§13). | Coach offers (does not force) the relevant lesson link — suppressed for skills already at CONSOLIDATED per §15's Coach-fading fix, unless NEEDS_REINFORCEMENT is active. |
| **Reassess** | NEEDS_REINFORCEMENT flag active (§7, §24). | A fresh, full-checklist attempt is required before the skill is re-counted as CONSOLIDATED/TRANSFERRED. |
| **Reinforce** | Same trigger as Reassess. | A short re-practice prompt, distinct from a full lesson return. |
| **Revisit** | Learner-initiated return to earlier content, any time. | Always allowed; never evidence-negative. |

---

## 24. Retention / Reinforcement

Per this document's continuing no-fabrication discipline, no mathematical
forgetting model is invented. Revision 1 considered two triggers for
NEEDS_REINFORCEMENT and adopted error-recurrence over a dormancy window,
specifically to avoid an invented number. That choice stands. **This
revision adds one proactive, non-punitive mechanism alongside it, closing a
real gap the review implicitly pointed at (its Special Question 6 area) but
did not name outright: error-recurrence is reactive by construction — it
only detects decay after decay has already caused a visible failure.**

**New — an optional, expanding-interval spaced-retrieval prompt, LEARNING
DESIGN DECISION, grounded in Principle: the spacing effect (Cepeda et al.
2006) is among the most replicated findings in learning research, and its
key structural insight — that the useful gap between reviews should expand
as retention demands grow, rather than stay fixed — is what this design
adopts, not a specific universal number.** Concretely: once a skill reaches
CONSOLIDATED, Flight Deck's existing "next recommended action" mechanism (file
03) may, at increasing intervals, surface an optional, low-stakes
"quick refresher" prompt for that skill — declining it has no evidence
consequence, and engaging it produces ordinary Recorded practice evidence,
not a special category. **A successful engagement is specifically what
§10's revised Retention definition calls "retention re-demonstrated"** —
genuinely positive evidence, distinct from the mere absence-of-decay
reading the rest of this mechanism's data would otherwise default to; an
unsuccessful or declined engagement is neither. **The specific starting
interval and its growth
rate are explicitly PROVISIONAL / TO BE VALIDATED**, added to §36 — this
document commits to the *structure* (expanding intervals, optional,
non-punitive) on strong general evidence, and explicitly does not commit to
a number no DEIXEN usage data yet supports, which is exactly the
discipline Principle 9 requires. This mechanism adds no new UI concept (it
reuses Flight Deck's existing recommendation surface) and no new evidence
class (a declined or completed prompt is ordinary Recorded/no-evidence
data) — it is a scheduling policy layered on an existing mechanism, not new
infrastructure, and is explicitly a **USEFUL ENHANCEMENT** (§28), not a
MUST HAVE for the frozen slice's current Definition of Done.

**REINFORCEMENT vs. RE-MASTERY, revised this pass (§7 Fix 3):** a quick,
successful reinforcement attempt clears the flag without demoting the
underlying state, unchanged. If reinforcement fails repeatedly (interim
default: **2** consecutive failures, PROVISIONAL, newly added to §36's
tracked numbers per the review's P2-4), the skill regresses — to CONSOLIDATED
if it was at TRANSFERRED, to DEMONSTRATED_INDEPENDENT if it was at CONSOLIDATED
— and must re-earn the lost ground through the normal requirement
("RE-MASTERY"), never silently retaining evidence the learner's current
performance no longer supports.

---

## 25. Difficulty / Fading

Difficulty remains **several dimensions**, not one arbitrary number, per
Revision 1's structure. The Guidance-level dimension is substantially
strengthened this revision; the others are unchanged.

| Dimension | Current fading mechanism |
|---|---|
| Guidance level | **Now three content depths** (Nudge → Partial Reveal → Full Reveal, §15), directly implementing the worked-example-fading research cited in Principle 2 (§5) rather than an intuitively-chosen two-point scale. |
| Number of steps | Isolated command → chained workflow (§11) → the one Scenario. |
| Variation / novelty | Cannot meaningfully fade yet — only one Scenario and one command chain exist by design (Decision 8A). A consequence of current scope, not a flaw. |
| Pressure | Speed Drills' timing dimension (gated behind CONSOLIDATED, §17); the CS track's Anger Meter, kept Illustrative pending its own rubric (§19). |

No dimension is collapsed into a single composite "difficulty score" —
unchanged, and still directly prevented by the REJECTED numeric-composite
item in §28.

---

## 26. Cognitive Load / Human Factors

**Necessary complexity to preserve, not simplify away** — unchanged from
Revision 1: authentic command syntax, the unsimplified official error
message, realistic multi-step preconditions. This is now explicitly framed
against **cognitive load theory** (Sweller & Cooper 1985, §3): the goal is
to manage *extraneous* load (unnecessary UI complexity, sprawling
explanations) without reducing *intrinsic* load (the genuine complexity of
the real task) — reducing the latter would be exactly the realism-eroding
simplification Non-Negotiable Rule #3 (file 03) forbids.

**Unnecessary load to avoid, unchanged:** UI complexity beyond what the
real task requires; Coach information displayed constantly rather than on
request; assistance content staying concise at every tier, including the
new Partial Reveal tier, which names one specific unmet condition, not a
restatement of all three.

---

## 27. False Mastery & Gameability Audit

The same twelve risks as Revision 1, re-examined against this revision's
fixes, plus one new risk this pass's independent discovery surfaced (not
found by the external review either). "Fully addressed" still means this
document's countermeasures close the gap for *evidence-crediting* purposes
only — none can force genuine learning.

| # | Risk | Status after this revision |
|---|---|---|
| 1 | Memorization without understanding | Unchanged mechanism (chained practice + mandatory Tier 3 Error-Recovery), now with a real effect-size rationale from error management training (Principle 7, §5) rather than intuition alone. |
| 2 | Copying Coach | **Strengthened.** Revision 1's hint-adjacent exclusion had a hole — corrective feedback delivered outside the counted hint ladder wasn't excluded. §13's Fix closes this: any corrective content, from any channel, now triggers exclusion. Residual risk unchanged: a learner can still copy-then-retry; the system can only stop crediting it, not stop the behavior. |
| 3 | Predictable scenarios | Unchanged — one scenario by design; the real fix is Scenario Bank expansion, out of scope. |
| 4 | Random trial-and-error | Unchanged mechanism (§13 escalation), now suppressed post-CONSOLIDATED per §15's Coach-fading fix, which slightly reduces its own reach for skills that no longer need it — a positive side effect, not the mechanism's main purpose. |
| 5 | Fixed-pattern overfitting | Unchanged — same root cause as #3. |
| 6 | Recognition replacing recall | Unchanged, still the most fully addressed risk (§12) — now with an explicit intermediate step (Partial Reveal) that preserves the recall requirement while adding graduated support, rather than a blunt binary. |
| 7 | Hint dependence | **Partially strengthened.** The exclusion side is stronger (see #2). Coach's *general* proactivity fading remains unaddressed beyond the one narrow, CONSOLIDATED-gated instance in §15 — named honestly, not fixed in full, in §38. |
| 8 | Familiar-context dependence | Unchanged — same root cause as #3/#5. |
| 9 | Speed mistaken for competence | Unchanged, fully addressed (§17), now with an explicit, specified mechanism for excluding wrong reps rather than a stated-but-unspecified principle. |
| 10 | Completion mistaken for mastery | Unchanged, structurally addressed (§7/§10/§21), strengthened by the correctness checklist giving "completion" itself a precise, checkable meaning it lacked before. |
| 11 | Technical correctness mistaken for judgment | Unchanged — genuinely SME/domain territory this document cannot manufacture. |
| 12 | Simulator success mistaken for workplace readiness | Unchanged mechanism (Principle 6, 6.1), now reinforced by Baldwin & Ford's transfer-of-training finding (§18) that DEIXEN structurally cannot reach the "work environment" factor no matter how good its own design gets. |
| 13 *(new this pass)* | **Assessment content identical to practice content.** Because the frozen slice has exactly one scenario, the formal "Assessment session" necessarily reuses the same commands and context the learner already practiced with — a distinct risk from #3 (predictable scenarios generally): this one is specifically about whether *assessment* can be meaningfully independent of *practice* when they share identical content. | Named and given a precise structure via Kane's validity framework (§20) — the Generalization inference is honestly rated weak. Not fixable within the current one-scenario scope; the fix is either Scenario Bank expansion or explicit acceptance that the frozen slice's assessment claim stays narrow ("this pipeline, this instance") until then. **OPEN QUESTION**, tracked in §36. |

Risks #3, #5, #8, #11, and #13 remain the ones this document cannot fully
close — each requires either Scenario Bank expansion, SME involvement, or
both, none of which are within this document's authority to manufacture.

---

## 28. Learning Efficiency & Minimum Viable Learning System

| Bucket | Items | Why |
|---|---|---|
| **MUST HAVE** | Skill state model with the correctness checklist (§7); the unified diagnostic/corrective exclusion rule spanning hints and feedback (§13, §15); Evidence Truth vs. UI Progress separation (§21); conservative mastery-language rule (§10, Principle 6); workflow-level chained practice, now with honest correlation-dependency framing (§11); Simulator Scope Disclosure (Principle 6.1); Lesson 5's two-separate-events rule (§19); error/feedback depth rules (§13/§14). | Each closes a gap that would otherwise let the frozen slice's evidence be read as stronger than it is — the last two are new this revision, added because the review found them missing entirely, not merely under-specified. |
| **USEFUL ENHANCEMENT** | Speed Drills CONSOLIDATED-gate + specified wrong-rep exclusion (§17); repeated-error escalation with CONSOLIDATED-gated suppression (§13, §15); error-recurrence retention trigger plus the new optional spaced-retrieval prompt (§24); Partial Reveal content tier (§8, §15). | Real improvements, but the frozen slice's Definition of Done (file 07) does not depend on them. |
| **OPTIONAL FUTURE** | Interleaving (§11); multiple Ghost Mode examples per skill; full 37-command tiering and checklist authoring (§8); the general (not skill-specific) Coach-proactivity fading question (§15, §38). | Genuinely not actionable inside a one-scenario, four-command slice, or genuinely dependent on usage data that doesn't exist yet. |
| **REJECTED / NOT JUSTIFIED** | A second hint-type counter (§15); a numeric mastery score/composite index (§10, §25); an adaptive/algorithmic difficulty engine (§11, §26); a CS choice-quality rubric authored by this document (§19); any fixed CPM/dormancy/spacing-interval threshold asserted as a real, validated number (throughout). | Each either contradicts an already-canonical rule or exceeds this document's authority/scope — unchanged reasoning from Revision 1. |

---

## 29. Implementation Contract

Uses file 08's existing Feature Behavior & Evidence Contract fields
(Purpose / Behavior / State / Data-Evidence Owner / Truthful UI
Representation / Acceptance Criteria / Regression Boundary), unchanged.
Items 2 and 5 were corrected in Revision 2; item 2 is corrected again this
pass; items 8–9 were new in Revision 2; items 10–12 are new this pass.

| # | Item | Purpose | Behavior | Data/Evidence Owner | Acceptance Criteria | Regression Boundary |
|---|---|---|---|---|---|---|
| 1 | Skill state model + correctness checklists | Stop progression/Growth-Readiness from overclaiming. | 5 states + 1 flag (§7), each transition gated by a per-skill checklist (Principle 8), computed from evidence, not stored as separate truth. | Derived from Event Log entries; checklist authoring is content work bounded by file 05. | A learner at DEMONSTRATED_INDEPENDENT has satisfied every checklist item for that skill on record. | Does not touch Decision 8A's scope, the five-area IA, or the four evidence classes. |
| 2 | Independence flag, two-input, separate from the learner-requested-hint counter — **corrected this pass** | Prevent any answer-revealing content, from any channel, from being credited as independent, without silently redefining the canonical counter. | A success is flagged independent only if no Nudge/Partial Reveal/Full Reveal was active (the canonical counter, untouched), no same-command Ghost Mode reveal immediately preceded it, and no corrective-tier feedback (§13) immediately preceded it — the last of these read from a *separate* Calculated field, never from the counter itself. | **Requires confirming the Event Log's timestamp granularity supports this determination across both inputs — OPEN, not assumed** (§21, §32, §36; this dependency's priority is elevated this revision, see §21). | A hint-adjacent or corrective-feedback-adjacent success does not move a skill to DEMONSTRATED_INDEPENDENT; the learner-facing hint count still reports only learner-requested events. | Does not change the single-hint-counter rule's original meaning, and does not authorize a scoring/schema redesign. |
| 3 | Evidence Truth vs. UI Progress separation | Prevent displayed progress from drifting from underlying evidence. | Progress displays compute from evidence at render/query time. | Same Event Log fields. | Displayed progress always matches a fresh query. | Implementation detail only. |
| 4 | Conservative mastery-language rule | Keep learner copy within Decision 7's confirmed scope. | Amadeus-domain copy uses "correct in DEIXEN," not "mastered," until Decision 7 executes. | N/A — a copy rule. | No surface uses "mastered" language while Decision 7 execution is Pending. | Copy only. |
| 5 | Workflow-level chained practice, correlation honestly flagged | Produce evidence relevant to file 07's open whole-workflow-validity question. | After all four slice commands independently reach DEMONSTRATED_INDEPENDENT, the learner completes the full chain unaided once; a self-corrected error does not void this (§11). | **Whether "one continuous, unaided sequence" is reconstructable from the existing four fields alone, or needs a minimal correlation identifier, is OPEN — not assumed either way** (revised this pass; previously asserted without this caveat). | Chain-level evidence exists and is separately queryable from per-command evidence, once the above is resolved. | Does not add a fifth slice command or move Decision 8A's boundary. |
| 6 | Simulator Scope Disclosure | Prevent false beliefs about real GDS scope from DEIXEN-only simplifications. | A short reference listing Known Issues #5/#6/#8 and structural facts (file 05). | N/A — static content. | Content exists, is accurate, and is reachable in-flow. | Content only. |
| 7 | Error/feedback depth rules, extended to cover the diagnostic/corrective split | Already canonical (files 05/06) for message discipline; the diagnostic/corrective split (§13) is this document's addition. | FORMAT/DATA_REFERENCE feedback is authored and reviewed as diagnostic or corrective; corrective content sets the independence flag's second input to false (item 2) — it does not touch the hint counter. | Content-authoring discipline; no new field. | No corrective-tier feedback content is missed by the independence determination. | Does not change the taxonomy, the verbatim-message rule, or the counter's meaning. |
| 8 | Lesson 5 two-event evaluation rule | Prevent Decision 6's technical/CS wall from being breached inside one hybrid interaction. | The Terminal-command and English-response halves of one Lesson 5 interaction produce two separate evidentiary events; neither compensates for the other (§19). | Bounded by existing skill-state (technical half) and Decision 6's pending contract (CS half) — no new evidence class. | No implementation of Lesson 5 lets one half's outcome alter the other half's recorded result. | Does not authorize any CS proficiency claim ahead of Decision 6's own contract. |
| 9 | Optional spaced-retrieval prompt | Provide a proactive, non-punitive complement to the reactive error-recurrence reinforcement trigger. | Flight Deck's existing recommendation surface offers an optional refresher at an expanding, PROVISIONAL interval once a skill is CONSOLIDATED (§24). | No new evidence class — declined/completed prompts produce ordinary no-evidence/Recorded data. | Declining has no evidence consequence; engaging produces standard Recorded evidence. | Does not add a new UI concept or a punitive consequence for non-engagement. |
| 10 *(new)* | TRANSFERRED/CONSOLIDATED independence and anti-halo-crediting consistency | Prevent the model's highest state from being reachable with assistance active, and prevent incidental (non-load-bearing) Scenario use from counting toward either state. | A Scenario-linked success qualifies for CONSOLIDATED or TRANSFERRED only if it is independent (item 2) and observably necessary to the scenario's differentiating condition (§18, file 07). | Same Event Log/independence dependency as item 2, applied to Scenario-linked events specifically. | No TRANSFERRED or CONSOLIDATED-via-Scenario record exists where either condition was not met. | Does not change the Scenario Differentiation Contract's own text (file 07) — only how this document's states read it. |
| 11 *(new)* | Speed Drills exclusion-rate co-display | Prevent a rising CPM trend from being misread as rising competence. | Any surface showing the CPM trend also shows the exclusion count/rate for the same window, using data already computed to decide exclusion. | No new computation — a display requirement on already-Calculated data. | The CPM trend never appears without its exclusion context somewhere in the same view. | Does not introduce a composite score or a new threshold. |
| 12 *(new)* | Three-way retention labeling | Prevent "no decay observed" and "recently confirmed" from being displayed as the same claim. | Any retention-related surface distinguishes no-decay-observed, not-recently-re-observed, and retention-re-demonstrated (§10), using existing timestamps and event data — no new field. | Same Event Log fields, read differently. | No surface asserts "retained" using only the absence of a NEEDS_REINFORCEMENT flag, without also surfacing recency. | Does not invent a numeric staleness threshold. |

---

## 30. Reusable Skill Authoring Standard

Same trimmed field list as Revision 1, with one field updated to reflect
Principle 8.

| Field | Purpose | Source of truth |
|---|---|---|
| Skill ID / Skill Name | Identity. | Author-assigned. |
| Tier (1/2/3) | Determines required learning path (§8). | This document's rubric, applied by the author. |
| Learning Objective (objective / observable / **acceptable performance checklist**) | The §6 template, instantiated once per skill, **now requiring an explicit itemized checklist, not a single bar**. | File 05 for any Amadeus-behavior content; author for phrasing. |
| Prerequisites | Existing Lesson schema field (`prerequisiteLessonIds`). | File 03. |
| Practice Bridge | Existing Lesson schema field (`practiceBridge`). | File 03. |
| Assistance Notes | Skill-specific content for all three tiers (Nudge / Partial Reveal / Full Reveal) — the ladder itself is global. | Author. |
| Error Classes Relevant | Which of the 8 canonical categories apply, tagged diagnostic or corrective per anticipated content (§13). | File 05, author. |
| Scenario/Transfer Requirement | Yes/no, per Tier. | This document's rubric. |
| Reinforcement Trigger | Error-recurrence, per §24 — not re-authored per skill unless genuinely different. | §24. |
| Validation Status (per skill) | Tracks Decision 7 SME sign-off individually. | File 07, applied per skill. |

**Two authoring-review steps added during this document's own second
self-attack (§38), both cheap and both closing a real precision risk this
revision's own additions created:**

1. **Checklist completeness review.** A skill's checklist (Principle 8) is
   reviewed against file 05's *complete* documented behavior for that
   command before being treated as final — not just authored once and
   trusted. An incomplete checklist is a more dangerous kind of gap than
   Revision 1's vague "success" bar was, precisely because "checklist-
   complete" now sounds, and is meant to be, more authoritative; that
   authority is only earned if the checklist is actually complete.
2. **Diagnostic/corrective classification review.** Every piece of
   FORMAT/DATA_REFERENCE feedback content (§13) is explicitly reviewed and
   labeled diagnostic or corrective before it ships — this is a real,
   non-trivial new authoring step this revision introduces, not a free
   consequence of stating the rule. The classification will have genuine
   borderline cases; a second reviewer's judgment call, not only the
   original author's, is recommended for anything ambiguous.

**Explicitly not retained as separate per-skill fields, unchanged:**
Conceptual Understanding, Recognition, Recall, Demonstration, Guided
Practice, Independent Practice, and Mastery — each governed once, globally.

---

## 31. Curriculum Integration

Mapping, not rewriting — unchanged from Revision 1 in substance.

- **Technical Track — Basic (17 lessons, file 06):** mostly Tier 1/2.
- **Technical Track — Advanced (11 lessons, 2 currently usable, file 06):**
  skews Tier 3. The 8 future-plan lessons remain **OPEN — KNOWLEDGE
  RECOVERY** per file 13.
- **Customer Service Track (5 lessons, file 06):** uses its own objective
  mapping (§19); Lessons 1/2/4 explicitly fall outside the §7 skill-state
  model per this revision's new scope statement; Lesson 5's evaluation now
  has an explicit two-event rule (§19).
- **Lesson 17 ("Evaluation Means"):** unchanged acknowledged gap; not
  invented here.
- **Restated, unchanged:** §8's tiering answers *how much rigor*; file 13's
  curriculum-sequencing question (competency-ordered vs.
  engine-implementation-ordered) is a different question this document does
  not take a position on.

---

## 32. Vertical Slice Validation (Learning-Design Sense)

Distinct from Decision 8A's own product-level Definition of Done (file 07),
which this section supplements. Updated this revision to reflect the fixes
above.

1. At least one learner reaches DEMONSTRATED_INDEPENDENT on all four slice
   commands via genuinely independent attempts, each satisfying its full
   correctness checklist (Principle 8).
2. **Both halves of the independent-evidence exclusion rule are confirmed
   implementable** against real Event Log data: single-attempt
   hint/reveal-adjacency (as in Revision 1), **and, new this revision,
   corrective-feedback-adjacency across the previously-uncounted channel**
   (§13). This document states plainly that both are currently unconfirmed
   (§21, §29, §36).
3. At least one hint-adjacent success, one corrective-feedback-adjacent
   success, and one Error-Recovery Practice instance are actually observed
   and correctly excluded/handled.
4. **Chain-sequence continuity for workflow-level practice is confirmed
   reconstructable** from either the existing four fields or a minimal
   correlation addition — whichever proves necessary (§11's honesty fix).
5. The one scenario produces TRANSFERRED status only for skills its own
   acceptance criteria actually exercised **and** where that specific use
   was independent — both conditions checked together, not either alone
   (§7 Fix 4).
6. Lesson 5, if and when built, produces two separate evidentiary events
   with no observed cross-compensation (§19).
7. Growth/Readiness displays only the one qualitative status the frozen
   slice authorizes — never a number.

---

## 33. Learning Claims Audit

Eight of this document's most load-bearing claims (two new this revision),
audited against their own basis rather than asserted as settled.

| Claim | Basis | Evidence strength | Assumption | Validation requirement |
|---|---|---|---|---|
| Independent success (per the exclusion rule) proves the skill was performed unaided. | LEARNING DESIGN DECISION (§7/§13/§15). | **Stronger than Revision 1** — the rule now covers both hints and feedback, closing the specific hole the review found. Still only as strong as its actual coverage; doesn't catch a hint memorized in an earlier session. | Hint- and corrective-feedback-adjacency are both computable from Event Log data. | Implementation confirmation + real learner testing. |
| CONSOLIDATED status indicates the skill isn't due to luck. | LEARNING DESIGN DECISION (§7/§20), now backed by a correctness checklist. | **Stronger than Revision 1** — "success" now means "met an explicit, file-05-derived checklist," not a vague pass; the repeat-count remains a PROVISIONAL interim default of 2. | Repeated checklist-complete success under similar conditions is a meaningful signal for this specific product/audience. | Real usage data to validate the interim default. |
| A single Assessment record supports a claim of general competence. | Never claimed — explicitly rejected. | N/A by design. | N/A. | N/A — this is what Kane's framework (§20) exists to prevent overclaiming. |
| Retrieval practice produces more durable learning than passive exposure here. | **RESEARCH-SUPPORTED PRINCIPLE** (§3) — not DEIXEN-specific research. | Well-supported generally; not independently confirmed for DEIXEN's population/context. | The general finding transfers to this simulator and audience. | **VALIDATION HYPOTHESIS** — real learner testing, not citation alone. |
| Workflow-level chained practice produces evidence relevant to whether `AN→SS→FQD→FXP` is a coherent real task. | RECOMMENDATION (§11). | Reasonable as a design choice; does not answer the SME question itself. | The chain-correlation mechanism is actually buildable — **now explicitly flagged OPEN, not assumed** (§11 Fix). | Decision 7's actual SME execution, plus the Event Log confirmation above. |
| The Anger Meter should be classified as Illustrative evidence. | LEARNING DESIGN DECISION (§19), applying file 07's own rules. | Strong — a direct application of an already-canonical rule. | No undisclosed rubric exists in the actual codebase. | Confirm against real implementation; CS-domain expert input on the rubric itself. |
| Lesson 5's two components can be evaluated without breaching Decision 6. | LEARNING DESIGN DECISION (§19), new this revision. | Reasonable and minimal, but genuinely untested — no implementation of Lesson 5 exists yet to check the rule against. | The "two separate events, no compensation" rule is sufficient and doesn't need further refinement once real content is authored. | Content-authoring review once Lesson 5 is actually built. |
| No learner-facing claim should imply real Amadeus mastery until Decision 7 executes. | Direct extension of Operating Constitution §3 and Decision 7. | As strong as the canonical boundary itself. | None beyond what's already established. | Not applicable — inherited, not proposed. |

---

## 34. Validation Strategy

| Method | What it can establish | What it cannot establish |
|---|---|---|
| **Document validation** (this pass and the prior adversarial review) | Internal consistency with the nine canonical files, with the research basis in §3, and with itself. | That learners actually learn better this way. |
| **External research citation** *(new this revision)* | That a principle is well-supported *in the contexts those studies actually tested* — often professional/technical training, sometimes DEIXEN-adjacent (aviation CBTA structure), sometimes not (classroom vocabulary spacing studies). | That the principle transfers with the same effect size, or at all, to DEIXEN's specific learners, content, and interface. |
| **Implementation validation** (once built) | That the mechanics behave as specified — the exclusion rule fires correctly across both channels, the checklist is enforced, chain correlation works. | Pedagogical effectiveness. |
| **Self-testing** (Karim and his brother — file 03's own stated strategy) | Obvious usability/friction issues; whether the realism feels right; whether the new Partial Reveal tier feels like a genuine middle ground or an awkward extra step. | Statistically reliable learning-outcome claims — the sample is two people, informally. |
| **Real learner testing** (future) | The actual answer to every VALIDATION HYPOTHESIS in this document, including the ones added this revision (Partial Reveal's calibration, the spaced-retrieval interval, whether the Coach-fading instance in §15 is even noticed). | Nothing is claimed as "effective learning" from documentation or citation review alone anywhere in this document. |

---

## 35. Decision Register

Every substantive proposal from Revision 1, carried forward with its status
updated where this revision changed it, plus every new decision this
revision introduces, plus — new this revision — an explicit disposition for
every finding in the external adversarial review, so no finding is only
"closed" by assertion.

### Part A — Original decisions (Revision 1), status updated where changed

| # | Decision | Type | Rationale / Evidence | Risk | Status |
|---|---|---|---|---|---|
| 1 | Five-state skill model + 1 modifier flag | ADD | Closes the no-progression-model gap (§7) | Confirmed sound by external review | **PROPOSED, REVIEW-CONFIRMED** |
| 2 | Independent-evidence exclusion rule | ADD | Closes the false-credit gap | **Revised this pass** — now spans hints and feedback (§13/§15 Fix); Event Log dependency remains open | PROPOSED — REQUIRES VALIDATION |
| 3 | Terminal assistance ladder, one shared counter | ADD | Content depth without a second counter | **Revised this pass** — now three tiers (§8/§15), not two | PROPOSED |
| 4 | Reject additional assistance levels beyond the ladder | REJECT | Duplicates Ghost Mode without new evidentiary purpose | Review did not dispute | REJECTED (confirmed) |
| 5 | Skill-complexity tiering framework | ADD | Prevents under/over-designed paths | Full 37-command assignment not performed | PROPOSED |
| 6 | Workflow-level chained practice before scenario | ADD | Feeds file 07's open whole-workflow-validity question | **Revised this pass** — correlation-mechanism honesty added (§11) | PROPOSED — REQUIRES VALIDATION |
| 7 | Mandatory Error-Recovery Practice for Tier 3 | ADD | Prevents clean success without understanding preconditions | Now grounded in Keith & Frese (2008), Principle 7 | PROPOSED, STRENGTHENED |
| 8 | Speed Drills CONSOLIDATED-prerequisite gate | ADD | Prevents unverified-accuracy speed credit | Low | PROPOSED |
| 9 | Speed Drills accuracy-must-count rule | ADD | Prevents fast-but-wrong reps counting | **Revised this pass** — exclusion mechanism now specified (§17) | PROPOSED, SPECIFIED |
| 10 | Speed Drills excluded from Growth/Readiness | CLARIFY | Formalizes existing canon | None | CLARIFICATION of CURRENT PRODUCT DECISION |
| 11 | Repeated-error escalation rule | ADD | Prevents unguided try/fail looping | **Revised this pass** — suppressed post-CONSOLIDATED (§15) | PROPOSED + VALIDATION HYPOTHESIS |
| 12 | Known Issue #7 flagged as active false-mastery risk | ESCALATE | A currently-true defect | **Revised this pass** — mitigation requirement sharpened (§14) | OPEN — owner: technical + Coach-content coordination |
| 13 | Conservative mastery-language rule | ADD | Keeps claims within Decision 7's scope | May read as less motivating — wording only | PROPOSED |
| 14 | Evidence Truth vs. UI Progress separation | ADD | Prevents progress-display drift | None | PROPOSED |
| 15 | Anger Meter reclassified as Illustrative | ESCALATE | Applies file 07's evidence-class rules | **Extended this pass** — feedback/explanation gap named alongside (§19) | OPEN — owner: CS-content authority + Decision 6 |
| 16 | Recognize "communication-domain validation" as a category | ADD | Extends Amadeus-validation logic to CS | Governance/process change | RECOMMENDATION |
| 17 | Retention trigger: error-recurrence, not dormancy-window | ADD | Requires no invented number | **Extended this pass, not replaced** — spaced-retrieval prompt added alongside (§24) | PROPOSED |
| 18 | Dormancy-window reinforcement | DEFER | Needs real usage data | Superseded in framing by the spaced-retrieval prompt's expanding-interval structure, still PROVISIONAL | DEFERRED, illustrative placeholder only |
| 19 | Interleaving | DEFER | No second skill exists yet | — | DEFERRED, revisit post-slice |
| 20 | Adaptive/algorithmic difficulty engine | REJECT | Conflicts with Platform Direction | — | REJECTED (confirmed) |
| 21 | Numeric mastery score / composite index | REJECT | Conflicts with Evidence & Readiness Contract | — | REJECTED (confirmed) |
| 22 | Second hint-type counter | REJECT | Conflicts with single-hint-counter rule | — | REJECTED (confirmed) |
| 23 | Reusable Skill Authoring Template | ADD | Prevents per-lesson reinvention | **Revised this pass** — checklist field added (§30) | PROPOSED |
| 24 | Scenario-to-skill transfer credit, observably-exercised only | ADD | Prevents halo-crediting | **Revised this pass** — now explicitly paired with an independence requirement so assisted Scenario success cannot qualify either (§7 Fix 4) | PROPOSED |
| 25 | Completion/Competence/Mastery/Transfer/Retention definitions | ADD | Closes the terminology gap | **Revised this pass** — checklist-referenced (§10) | PROPOSED |
| 26 | Assessment category collapse to two functional types | ADD/CLARIFY | Avoids label proliferation | Review did not dispute | PROPOSED, REVIEW-CONFIRMED |
| 27 | "Sufficient evidence" bar vs. "observed success" | ADD | Closes the one-success-as-mastery gap | **Revised this pass** — Kane's validity framework applied (§20) | PROPOSED, STRENGTHENED |
| 28 | Vertical-Slice-for-Learning-Validity acceptance criteria | ADD | Supplements Decision 8A's Definition of Done | Updated this pass (§32) | RECOMMENDATION |
| 29 | Event Log's ability to support hint/reveal-adjacency timing | ESCALATE | A load-bearing, unconfirmed assumption | **Elevated this pass to the single highest-priority open item** (§21) | OPEN — owner: delegated evidence/schema pass |
| 30 | Per-skill Validation Status field | ADD | Lets Decision 7 be tracked per-skill | Low | PROPOSED |
| 31 | Simulator Scope Disclosure content requirement | ADD | Prevents false beliefs about real GDS scope | Low — disclosure only | PROPOSED |

### Part B — New decisions introduced in Revision 2

| # | Decision | Type | Rationale / Evidence | Risk | Status |
|---|---|---|---|---|---|
| 32 | Checklist-based minimum passing standard (Principle 8) replaces vague "success" everywhere in the skill model | ADD | Resolves the PROVISIONAL repeat-count's bootstrapping problem; grounded in simulation-based mastery learning research (McGaghie et al. 2014) | Authoring burden per skill — bounded by file 05, so nothing invented | PROPOSED |
| 33 | Interim default of 2 for CONSOLIDATED's repeat-count | ADD | Smallest number distinguishing "once" from "reliably"; checklist stringency does more of the real work per Kulik & Kulik (1987) | Still PROVISIONAL — needs real usage data | PROPOSED + VALIDATION HYPOTHESIS |
| 34 | Unified diagnostic/corrective feedback rule spanning hints and ordinary error feedback | ADD | Closes the review's P1-2 — the single most material finding | Real content-authoring discipline required for FORMAT/DATA_REFERENCE copy | PROPOSED |
| 35 | Partial Reveal, a third assistance content depth | ADD | Closes the review's P2-7; grounded in worked-example fading research (Renkl & Atkinson 2010) | Still one counter — no canonical rule touched | PROPOSED |
| 36 | Graduated NEEDS_REINFORCEMENT demotion (TRANSFERRED → CONSOLIDATED → DEMONSTRATED_INDEPENDENT) | ADD | Closes the review's P2-5 — preserves proportional evidentiary value | Adds one more state transition to implement and test | PROPOSED |
| 37 | Interim default of 2 for reinforcement-failure count, added to the PROVISIONAL list | ADD | Closes the review's P2-4 — an inconsistency in this document's own discipline | Still PROVISIONAL | PROPOSED + VALIDATION HYPOTHESIS |
| 38 | Lesson 5 two-event, no-compensation evaluation rule | ADD | Closes the review's P1-4 — previously no rule existed at all | Untested against real content | PROPOSED |
| 39 | Kane's four-inference validity framework applied to the frozen slice's Assessment record | ADD | Closes the review's P2-1 with a precise, checkable structure rather than an implied limitation | None — a framing/documentation change | PROPOSED |
| 40 | Optional, expanding-interval spaced-retrieval prompt | ADD | Adds a proactive complement to the reactive error-recurrence trigger; grounded in the spacing effect (Cepeda et al. 2006) | Interval PROVISIONAL; no new UI concept or evidence class | PROPOSED |
| 41 | Coach-fading instance: suppress escalation offers for CONSOLIDATED skills absent NEEDS_REINFORCEMENT | ADD | Partial, narrow answer to the "Coach-as-crutch" gap; grounded in the expertise-reversal effect (Sweller & Cooper 1985) | Deliberately narrow — general Coach-proactivity fading remains unaddressed | PROPOSED + VALIDATION HYPOTHESIS |
| 42 | Explicit non-applicability of the §7 skill-state model to CS Lessons 1/2/4 | CLARIFY | Closes the review's P2-2 — makes an already-true consequence of Decision 6 explicit rather than inferred | None — a scope clarification | PROPOSED |
| 43 | Rename "Full hint" to "Full Reveal" for symmetry with the checklist/tiering language | CLARIFY | Minor terminology cleanup accompanying the three-tier ladder | None | PROPOSED |
| 44 *(this pass)* | Independence flag corrected to be a separate, two-input Calculated field rather than an extension of the canonical hint counter | MODIFY of #34 | The original mechanism would have silently redefined what file 03's counter means — a real semantic-drift risk found under this pass's Concern E, not merely a stylistic preference | Removes an open question rather than adding one; no new counter | PROPOSED |
| 45 *(this pass)* | TRANSFERRED requires independence explicitly | ADD | Closes a gap where the model's highest state could have been reached with assistance active — found under this pass's Concern A | None — applies a rule the rest of the model already follows | PROPOSED |
| 46 *(this pass)* | CONSOLIDATED redefined as a count of qualifying independent successes (drill or Scenario, mixed), rather than two separately-worded paths | SIMPLIFY | Removes language that had already diverged from TRANSFERRED's own wording once and applies the same anti-halo-crediting restriction to both — found under this pass's Concern B | None — a simplification, not new machinery | PROPOSED |
| 47 *(this pass)* | Retention split into three explicit, non-numeric labels (no decay observed / not recently re-observed / re-demonstrated) | ADD | Prevents a stale, untouched skill from reading identically to a freshly-confirmed one — found under this pass's Concern C | Some display/authoring discipline; no new field or threshold | PROPOSED |
| 48 *(this pass)* | Kane's Generalization and Scoring rows reworded for technical precision (universe vs. sample; design-level vs. implementation-confirmed) | CLARIFY | The original wording technically misapplied Kane's own terminology — found under this pass's Concern D | None — a wording correction | PROPOSED |
| 49 *(this pass)* | Speed Drills CPM trend must co-display its exclusion count/rate | ADD | Prevents a survivorship-biased CPM trend from reading as rising competence — found under this pass's Concern G | None — surfaces already-computed data | PROPOSED |
| 50 *(this pass)* | An operational test for the diagnostic/corrective boundary ("would the learner still need to work out the fix themselves?") | CLARIFY | The category labels alone left real judgment calls at the boundary — found during this pass's full coherence sweep | None — a sharper definition, not a new mechanism | PROPOSED |
| 51 *(this pass)* | §39's determination re-labeled to avoid the word "APPROVED" | CLARIFY | File 08 reserves "APPROVED" for explicit owner sign-off; using it here risked exactly that misreading — found under this pass's Concern F | None — a labeling fix; see §39 and §42 | PROPOSED |

### Part C — Adversarial review disposition register

Every finding from `AeroBridge_Learning_Design_Adversarial_Review.md`,
dispositioned per this task's own required categories. "Where fixed" points
to the section carrying the actual change — this table is a ledger, not a
restatement of the review or a second copy of the fix.

| Finding | Disposition | Where fixed / addressed |
|---|---|---|
| P1-1 — Event Log granularity dependency for independence detection | **Accept — implementation-dependent.** The finding is correct; this document cannot resolve it, only elevate its priority. | §21 (elevated to the top pre-implementation priority) |
| P1-2 — Ordinary feedback can function as an unlogged hint | **Accept.** The review's most material finding; fixed directly, not narrowed. **Mechanism corrected in this task's closure pass — see Part D, Concern E** — the exclusion is now computed via a separate independence flag, not by extending the canonical hint counter. | §13, §15, §7 Fix 2 |
| P1-3 — Chained-workflow correlation overconfidence | **Accept.** The "no new field required" claim is withdrawn and replaced with honest OPEN framing. | §11, §21, §29 |
| P1-4 — Lesson 5 hybrid evaluation undefined | **Accept.** A minimal rule now exists where none did. | §19 |
| P2-1 — Assessment content-reuse validity gap | **Accept — narrowed to a precise structure.** Rather than a general caveat, this revision applies Kane's four-inference framework, which states exactly which inference is weak and why. | §20 |
| P2-2 — §7 model's Customer Service scope unstated | **Accept.** | §19 |
| P2-3 — No interim default for PROVISIONAL numbers | **Accept.** Interim defaults now exist for both numeric thresholds this document introduces (CONSOLIDATED repeat-count, reinforcement-failure count); the underlying checklist concept (Principle 8) also independently reduces how much weight any single number has to carry. | §7, §24 |
| P2-4 — Reinforcement-failure count not flagged PROVISIONAL | **Accept.** | §7 Fix 3, §24, §36 |
| P2-5 — Non-graduated demotion | **Accept.** The review offered this as an option to consider, not a mandate; this revision adopts it because the reasoning (preserve proportional evidentiary value) held up under scrutiny and the cost is low. | §7 Fix 3 |
| P2-6 — CONSOLIDATED / Code-verified naming collision | **Accept — narrowed.** Renaming the *skill state* itself (CONSOLIDATED) would touch every section of this document and every reference in the external review; this revision instead renames the assistance-tier term ("Full hint" → "Full Reveal") to reduce collision surface, and explicitly flags the larger CONSOLIDATED-vs-Code-verified naming question as a decision for whoever next touches learner-facing terminology broadly, since renaming a skill state is a bigger change than this revision's stated purpose (fixing what the review found, not restructuring vocabulary) justifies on its own. | §15 (partial); §36 (remainder, newly OPEN) |
| P2-7 — Assistance ladder too coarse for Tier 3 | **Accept.** | §8, §12, §15 |
| P2-8 — Chain self-correction ambiguity | **Accept.** | §11 |
| P2-9 — Known Issue #7 mitigation may be insufficient without a specified accurate-number source | **Accept.** | §14 |
| P2-10 — Tier 3 mandatory Error-Recovery Practice lacks documented failure-mode behavior for `XE` | **Accept — implementation/domain-dependent.** This document names the requirement precisely; it cannot supply the missing code-verified behavior itself. | §14, §36 |
| P2-11 — Customer Service dialogue lessons lack a feedback/explanation mechanism | **Accept — narrowed, and correctly deferred.** A principle is stated; the content itself is not authored here, per Decision 6. | §19 |
| P3-1 — Hint-counter phrase interpretation | **Accept — resolved differently than first attempted.** Revision 2 initially resolved this by extending the counter's own meaning; this task's closure pass (Part D, Concern E) found that approach itself created a new semantic-drift risk and corrected it: the counter now keeps its original, single, unextended meaning, and a separate flag governs exclusion. This closes the interpretive question by removing its premise, not by picking a reading of it. | §13, §7 Fix 2 |
| P3-2 — CS retry/branch model undocumented | **Defer**, correctly — content-authoring work outside this document's authority. | §19 (named as OPEN QUESTION) |
| P3-3 — Ghost Mode confidence-reality gap | **Accept — as a named VALIDATION HYPOTHESIS**, not a design change absent evidence it's a real problem. | §16, §34 |
| P3-4 — Speed Drills wrong-rep handling mechanism unspecified | **Accept.** | §17 |
| P3-5 — NEEDS_REINFORCEMENT ignores error severity | **Reject, with reason.** Weighting reinforcement triggers by error severity would require a severity taxonomy this document has no evidence base to construct responsibly, and would reintroduce exactly the kind of invented judgment call Principle 9 warns against. The existing low-cost consequence (a short re-practice prompt, not a full reset) already substantially mitigates the concern the review raised; this revision keeps the simpler rule and accepts the small residual risk explicitly, rather than building machinery to remove it. | Unchanged from Revision 1 (§7); reasoning for keeping it made explicit here for the first time |

### Part D — Closure-pass concern register (this task's Concerns A–G)

Each concern below was investigated per the seven-step method the governing
brief for this pass required — restate, test presence, argue both sides,
decide, and only then intervene. None was assumed correct in advance; §38
documents the reasoning for each in full.

| Concern | Genuinely present? | Verdict | Disposition | Where fixed |
|---|---|---|---|---|
| A — Can assisted Scenario success count as TRANSFERRED? | **Yes.** TRANSFERRED's wording never excluded assisted success. | Real defect — the model's highest state was reachable with a hint active. | **Fix.** | §7 Fix 4, §10, §18, §32 |
| B — Are "≥2 independent" and "1 independent + 1 Scenario" interchangeable evidence? | **Partially.** They measure different things (reliability vs. generalization), but the alternate path also lacked TRANSFERRED's own halo-crediting restriction. | Real gap, but the fix is a halo-crediting/independence correction and a wording simplification — not a case for eliminating the alternate path, which remains legitimate. | **Fix (narrower than a full restructure).** | §7 Fix 4, §10, §20 |
| C — Does Retention conflate absence-of-failure, absence-of-observation, and re-demonstrated success? | **Yes.** A skill untouched for months and one confirmed yesterday read identically. | Real overclaiming risk, closable without any numeric threshold. | **Fix.** | §10, §24 |
| D — Does the Kane-framework wording misstate "universe" as size one? | **Yes**, a genuine technical imprecision in how Kane's own terms were applied; Scoring's design-vs-implementation status was also under-qualified. | Real, low-cost precision defect. | **Fix.** | §20 |
| E — Does the counter extension change canonical semantics? | **Yes.** It would have redefined a "learner asks" trigger to include events the learner never asked for. | Real defect, and the most consequential finding of this entire closure pass, since it touches a canonical mechanism's meaning, not just this document's own prior text. | **Fix — mechanism replaced, not merely clarified.** | §7 Fix 2, §13, §15, §21, §29 |
| F — Could "APPROVED" in §39 be misread as canonical approval? | **Yes.** File 08 reserves that exact word for explicit owner sign-off. | Real labeling collision, directly analogous to the already-fixed CONSOLIDATED/Code-verified issue. | **Fix.** | §39, §42 |
| G — Is CPM exclusion still the cleanest rule, and could speed read as competence? | **Exclusion: still cleanest, confirmed, no change.** **Interpretation risk: yes, via survivorship bias in what gets excluded.** | Existing rule adequate; a real, separate interpretation risk needed a boundary, not a new metric. | **Confirm existing rule; add a co-display requirement.** | §17 |



---

## 36. Open Questions

Carried forward from Revision 1 where still open, with new items added this
revision (marked *new*) and closed items removed to §35 Part C rather than
left here as clutter. **This pass removed one further item** — whether
extending the hint counter's meaning needed file 03's owner to confirm —
because Concern E's fix (§35 Part D) resolved it by removing its premise
rather than by answering it; see §7 Fix 2 and §13.

| Question | Why unresolved | Evidence missing | Who resolves | What depends on it |
|---|---|---|---|---|
| What is the Anger Meter's actual choice-quality rubric? | No rubric documented in any of the 9 files. | The rubric itself; Decision 6's still-pending CS contract. | CS-content domain expert; Karim on scope. | Any future CS proficiency claim. |
| *(new)* What should the CS dialogue feedback/explanation content actually say once the rubric exists? | Named this revision (§19); content-authoring work with no rubric to build from yet. | The rubric above, first. | Same as above. | Whether CS feedback avoids the "meter moves, nothing explained" pattern. |
| *(new)* Can a learner retry a CS dialogue choice point, or does it branch irreversibly? | Undocumented in any of the 9 files. | A content-architecture decision. | CS-content authoring. | Whether "retry" means the same thing for CS as for Terminal. |
| How should Known Issue #7's live-echo bug be mitigated in the meantime? | This document can specify the requirement, not implement or decide feasibility. | An engineering decision, sharpened this revision to a specific choice between two options (§14). | Whoever picks up the already-tracked scoped discussion. | Whether Terminal practice on `AP`/`TK`/`RF`/`XE` numbering is safe to teach from as-is. |
| *(new)* What is the actual system behavior when `XE` is attempted against an unsupported element type? | File 05 documents the constraint, not the resulting behavior. | Direct code inspection, outside this pass's reach. | Technical re-verification; SME if domain accuracy also matters. | Whether Tier 3's mandatory Error-Recovery Practice can be authored for `XE` specifically. |
| Does the current 4-field Event Log's timestamp granularity support hint/reveal-adjacency computation — **now for two channels, not one**? | This document assumes it does, for design purposes, without codebase access to confirm. | Actual schema/implementation inspection — the single highest-priority item in this document (§21). | The delegated evidence/state schema design pass. | Whether §7/§13/§15's exclusion rule is buildable as specified. |
| *(new)* Can chain-sequence continuity be reconstructed from the existing four fields, or does it need a minimal correlation identifier? | Previously assumed resolved; this revision withdraws that assumption (§11). | Same schema/implementation inspection as above. | Same owner. | Whether workflow-level chained practice can produce the evidence it's designed to produce. |
| What should Lesson 17 ("Evaluation Means") actually contain? | Explicitly undefined gap carried from earlier planning. | Whatever OLD material might resolve it, if it exists. | Knowledge Recovery pass. | The Basic track's completion definition for that lesson. |
| How should the remaining 33 commands be tiered, and their checklists authored? | This document supplies the rubric and template only. | None needed beyond the rubric — authoring effort, not missing evidence. | Whoever does per-lesson curriculum authoring. | Applying §8/§30 beyond the frozen slice. |
| Should "communication-domain validation" become a formally tracked category? | A governance/process question, not a learning-design one. | N/A — a process decision. | Karim. | How future CS evidence claims are handled. |
| What are the correct values for every number flagged PROVISIONAL (escalation count §13; CONSOLIDATED's repeat-count and reinforcement-failure count §7/§24; the spaced-retrieval interval §24)? | No real usage data exists yet. | Actual learner usage data. | Whoever runs real learner testing (§34). | Precise implementation of §7, §13, §24. |
| *(new)* Should the CONSOLIDATED skill-state term itself be renamed to avoid collision with file 05's "Code-verified" and file 08's "CONFIRMED"? | This revision narrowed its response to P2-6 (§35 Part C) rather than resolving it — a full rename is a larger terminology change than this revision's stated purpose covers. | A decision on whether the collision risk justifies touching every reference to CONSOLIDATED across this document and any future implementation. | Whoever next does a terminology pass across learner-facing and internal vocabulary. | Learner-facing UI copy once built; internal cross-document clarity. |
| Competency-ordered vs. engine-implementation-ordered curriculum sequencing? | Already **OPEN — KNOWLEDGE RECOVERY** in file 13. | OLD's actual curriculum design rationale. | Knowledge Recovery pass. | How §8's tiering interacts with lesson order (§31). |

---

## 37. Rejected / Deferred Ideas

Pulled forward and updated so nothing quietly returns without its reason
attached.

- **A second hint-type counter** — contradicts the canonical single-counter
  rule. Confirmed correct by external review.
- **A numeric mastery score or composite index** — contradicts the Evidence
  & Readiness Contract's ban on unapproved formulas.
- **An adaptive/algorithmic difficulty engine** — contradicts Platform
  Direction's anti-premature-infrastructure principle.
- **A fourth assistance content tier beyond Nudge/Partial Reveal/Full
  Reveal** — considered this revision while adding Partial Reveal, and
  rejected for the same reason Revision 1 rejected the brief's original
  seven-level ladder: no specific §4/§27 gap points to needing a fourth
  distinction, and Principle 9 governs additions, not just the original
  set.
- **A CS choice-quality rubric authored by this document** — domain-expert
  content work, not generic learning architecture.
- **Any fixed CPM, dormancy-window, or spacing-interval number asserted as
  real** — no real usage data exists yet for any of them.
- **Interleaving** — no second skill exists to interleave with inside the
  current slice.
- **Severity-weighted NEEDS_REINFORCEMENT triggers** *(new this pass,
  responding to the review's P3-5)* — would require an invented severity
  taxonomy with no evidence base; the existing low-cost, uniform trigger is
  kept deliberately, with the reasoning stated explicitly for the first
  time in §35 Part C.
- **A full rename of the CONSOLIDATED skill state** *(new this pass, responding
  to the review's P2-6)* — a larger terminology change than this revision's
  scope justifies; narrowed instead to renaming the one term (Full hint →
  Full Reveal) actually touched by this revision's other changes, with the
  larger question left open in §36.
- **Filling in file 06's own deferred full per-category Coach response
  matrix** — that deferral is deliberate, waiting on real usage data file
  06 itself says to wait for.
- **Full tiering and checklist authoring of all 37 commands** — the rubric
  and template are supplied; the assignment is curriculum-authoring work.

---

## 38. Adversarial Review Response & Second Self-Attack

**Part A — how the external review was used.** Every finding in
`AeroBridge_Learning_Design_Adversarial_Review.md` was dispositioned in §35
Part C: eighteen accepted (several narrowed with stated reasoning), one
deferred correctly to content authors, one rejected with reasoning (P3-5).
This document did not treat the review as automatic truth — the P3-5
rejection and the P2-6 narrowing are both places this revision disagreed
with the review's implied remedy while agreeing with its underlying
observation, and both say why. Separately, this pass asked whether the
review itself missed anything — it did: the review did not examine whether
its own recommended fixes might introduce new risks. That question is
exactly what Part B below is for.

**Part B — an independent second adversarial pass against this revision
itself, per this task's explicit requirement, performed honestly and not
merely reflexively confirming the work above is fine.**

| Self-attack question | Honest answer |
|---|---|
| 1. Could a learner still complete the system without becoming meaningfully competent? | **Yes, unavoidably.** The checklist and unified exclusion rule make it harder for the *system* to be fooled; neither can force genuine engagement. Unchanged in substance from Revision 1. |
| 2. Could the system still falsely classify a learner as competent or non-competent? | **Yes, in a slightly different way than before.** The interim-default numbers (2 and 2) could be wrong once real data exists — expected and already flagged PROVISIONAL. More interesting: **an incomplete checklist is now a more dangerous gap than Revision 1's vague "success" bar was**, because "checklist-complete" carries more apparent authority than a plain "it worked" — if an author misses a real file-05-documented condition, the gap is now dressed up as rigor. **Fixed in place this pass**: §30 now requires an explicit completeness review against file 05, not just one-time authoring. |
| 3. Could help still create dependency? | **Yes, and this revision may have introduced a new, subtle version of the risk while fixing the old one.** A softer middle option (Partial Reveal) could lower the perceived cost of asking for help — a learner might reach for "just tell me which one" more readily than they'd have reached for a full answer, even though each instance is now tracked more precisely than before. This is a genuine, non-obvious tension between better *measurement* of assistance and possibly higher *frequency* of assistance-seeking. **Not fixed — named honestly as a new VALIDATION HYPOTHESIS** (§34); resolving it needs real usage data on assistance-seeking frequency before and after the three-tier ladder, which does not exist. |
| 4. Could practice still reward memorization over skill? | **Yes**, for the same structural reason as Revision 1 — one scenario, limited context variety. Unaddressed by this revision by design; the fix is Scenario Bank expansion, out of scope. |
| 5. Could assessment still be contaminated by prior practice? | **Yes, explicitly and by name now** — Kane's Generalization inference (§20) is rated weak on the record, not implied. Naming it precisely is progress; it does not remove the underlying limitation, which only Scenario Bank expansion can. |
| 6. Could transfer still be weak? | **Yes** — Baldwin & Ford's "work environment" factor (§18) is structurally outside this product's reach regardless of design quality. |
| 7. Could retention still be overstated? | **Almost, and this pass caught it.** The optional spaced-retrieval prompt (§24) exists to *support* retention; a first draft of §10's definition risked reading as if *engaging* it were evidence *of* retention. **Fixed in place this pass** — §10 now states explicitly that only a subsequent checklist-complete success counts as evidence, and engagement alone does not. |
| 8. Could evidence still be weaker than the claim? | Addressed more precisely than Revision 1 via Kane's framework (§20), but the underlying answer is still yes for Generalization and Extrapolation, by design and by honest labeling, not by accident. |
| 9. Is any essential learning mechanism missing? | Two candidates were found and handled differently. **Tier 1's checklist proportionality** was genuinely underspecified (did Principle 8 apply the same way to a one-precondition command as a three-precondition one?) — **fixed in place this pass** (§8). **A curriculum-authoring cost estimate for scaling the checklist/diagnostic-corrective/three-tier system to all 37 commands** is a real gap this revision does not close — it is a future scope and resourcing question, honestly named here rather than quietly ignored, not something a learning-design document can responsibly estimate without curriculum-authoring input. |
| 10. Is any mechanism unnecessary? | The graduated demotion rule (§7 Fix 3) will affect very few learners while only one scenario exists — its practical impact right now is small. It is kept anyway because the principle it encodes (proportional evidentiary treatment) is cheap to build correctly now and expensive to retrofit once TRANSFERRED skills become common post-Scenario-Bank-expansion. This is a judgment call, stated as one, not a certainty. |
| 11. Did any revision create avoidable complexity? | The diagnostic/corrective feedback split (§13) is the single largest new authoring burden this revision introduces — every FORMAT/DATA_REFERENCE message now needs classification. It is not judged avoidable, because it is the direct fix for the review's most material finding (P1-2), but it should not be presented as a free improvement — **fixed in place this pass** by adding an explicit review step for it (§30), rather than leaving the burden implicit. |
| 12. Did any revision conflict with canonical DEIXEN decisions? | No addition touches Decision 8A's command scope, Decision 6's wall (Lesson 5's rule reinforces it), the four evidence classes, or the four-field Event Log. **One genuine interpretive question was found here and, at the time, not resolved** — whether routing corrective feedback through the existing hint counter was a legitimate extension of file 03's rule or an unintended reinterpretation of it. **This was fully resolved in a later closure pass, not merely flagged**: see §38 Part C (Concern E) and §7 Fix 2 — the corrective-feedback signal was moved off the counter entirely onto a separate flag, which removes the interpretive question rather than answering it either way. |
| 13. Did any revision introduce unsupported Amadeus/domain claims? | No. Every checklist item traces to file 05's existing documented behavior; `XE`'s unknown failure-mode behavior (§14) is stated as unknown, not guessed at; the CBTA reference (§3) is explicitly scoped as a structural benchmark, never domain content. |
| 14. Did any revision create ambiguity for implementation or curriculum authoring? | Yes, in one place worth naming rather than glossing over: the diagnostic/corrective line, while a real improvement over having no line at all, will have genuine borderline cases in practice (a "diagnostic" note specific enough to feel corrective). **Partially fixed this pass** via the second-reviewer recommendation added to §30; fully resolving it requires actual authored content to test the line against, which does not exist yet. |

**What this second pass changed, concretely, listed once for auditability:**
four small, targeted fixes were made directly to §8, §10, §30 (twice), and
one new entry was added to §36 — all during the writing of this section,
not after it, per this task's explicit instruction to fix what can be
responsibly fixed rather than merely list it. Nothing found in this pass
was large enough to require reopening §7's skill-state shape, §13's central
fix, or any canonical anchor.

**Part C — the final closure pass's seven-concern investigation, in full.**
Per that pass's governing brief, each concern below was investigated by
restating it, testing whether it was genuinely present, arguing both sides,
deciding, and only then intervening. The compact ledger is §35 Part D; the
reasoning is here.

*Concern A — TRANSFERRED and independence.* Restated: could a Scenario
success involving assistance still count as transfer evidence? Genuinely
present: yes — TRANSFERRED's Revision 2 wording said "full-checklist
success inside a Scenario context," never "independent," unlike
DEMONSTRATED_INDEPENDENT's explicit wording. Strongest case *for* it being
a defect: the model's own first principle (§40) says independence is what
everything else follows from; an unstated exception in the single highest
state is a serious gap, not a small one. Strongest case *against*: a
scenario is a longer, more complex task than a single command, and
real-world transfer sometimes does involve incidental lookups — perhaps
requiring zero assistance across an entire multi-step scenario is an
unreasonably strict bar. Deciding between them: the second argument
dissolves once independence is scoped correctly — *per skill, per
attempt*, exactly as it already works everywhere else in this model, not
*per entire scenario*. A learner who needed help with a different command
during the same scenario attempt loses nothing for the skill performed
unaided. Once scoped this way, there is no real cost to requiring
independence, and a real cost to not requiring it. **Verdict: genuine
defect, fixed** (§7 Fix 4).

*Concern B — CONSOLIDATED's two paths.* Restated: are "≥2 independent drill
successes" and "1 independent + 1 Scenario pass" measuring the same thing,
and if not, should they still both count toward CONSOLIDATED? Genuinely
present, but not in the form first suspected: the two paths measure
different things (repetition/reliability vs. cross-context
generalization), but this is a feature, not a bug — Kulik & Kulik's (1987)
finding that criterion stringency matters more than repeat count (§3)
supports treating a demanding single Scenario success as comparable
evidence to a second drill success, not inferior to it. The actual defect
found was narrower: the Scenario-path alternative never carried the same
anti-halo-crediting restriction (§18) that TRANSFERRED does, which is a
real gap regardless of how the reliability-vs-generalization question is
answered. Strongest case for changing the structure entirely (requiring 2
drill successes always): none survived scrutiny — it would discard a
legitimately strong form of evidence for no stated evidentiary gain, which
is exactly the "added restriction not justified by validity gain" this
pass's brief warns against. **Verdict: the two-path structure is
internally coherent and is kept; the halo-crediting gap is a genuine
defect and is fixed**, via the same mechanism as Concern A, which also
happens to simplify the wording rather than complicate it (§7 Fix 4).

*Concern C — Retention.* Restated: does "no active NEEDS_REINFORCEMENT
flag" get read as one thing when it actually covers two very different
situations — a skill confirmed fine yesterday, and a skill nobody has
touched in months? Genuinely present: yes, on inspection the single
definition covered both without distinction. Strongest case it's not a
real problem: the existing "time passing alone is insufficient evidence"
line already gestures at the distinction. Strongest case it is: a gesture
is not a rule a UI implementer can act on, and "insufficient evidence for
what, exactly" was never specified. Deciding: the distinction is cheap to
make explicit using data already logged (timestamps, event occurrence),
requires no numeric threshold, and closes a real overclaiming risk.
**Verdict: genuine gap, fixed with a three-way, non-numeric distinction**
(§10).

*Concern D — Assessment validity wording.* Restated: does describing the
frozen slice's "universe" as size one confuse the sampled instance with the
universe those instances are drawn from? Genuinely present: yes — this is
a real misuse of Kane's own terminology, not merely inelegant phrasing;
the universe of real Amadeus conditions is large, the *current sample from
it* is what is small. Also checked and confirmed accurate: the Extrapolation
row already correctly says "not claimed." Also found: the Scoring row's
"reasonably supported" needed an explicit tie to the same
implementation-verification dependency already named elsewhere, since
design-level support and confirmed support are not the same claim.
**Verdict: two genuine precision defects, both low-cost, both fixed**
(§20).

*Concern E — Hint counter semantics.* Restated: after Revision 2's fix,
does the shared counter still mean what file 03 says it means, or did
extending it to cover corrective feedback quietly redefine it? Genuinely
present, and the most serious finding of this entire pass: file 03's
counter has one specific trigger, "Hint requested | Learner asks." An
ordinary FORMAT error the learner never asked about does not meet that
trigger, however similar its evidentiary effect on independence. Two
future implementers absolutely could read Revision 2's text differently —
one treating the counter as "hints requested" (and missing corrective
feedback from the exclusion computation), another treating it as
"assistance events broadly" (and reporting a non-zero hint count to a
learner who never clicked anything, breaching file 07's hint-honesty
rule in spirit even while technically following its letter). Strongest
case it wasn't a defect: the *purpose* of tracking corrective feedback for
exclusion is legitimate and the review's own P1-2 finding demanded it.
Strongest case it was: purpose does not justify redefining a *named,
specifically-triggered canonical mechanism* to serve it, when a separate
mechanism can serve the same purpose without touching the canonical one at
all. Deciding: the second argument wins outright, and the fix is not a
clarification of the existing approach but a replacement of it — the
independence flag becomes its own two-input Calculated field, the counter
reverts to its original, single, untouched meaning. **This task's
instruction not to create a second counter is honored**: nothing here is a
counter; it is a boolean-valued flag with two boolean inputs. **Verdict:
genuine and serious defect; mechanism corrected, not merely clarified**
(§7 Fix 2, §13, §15, §21, §29).

*Concern F — "APPROVED" in §39.* Restated: could the word "APPROVED,"
displayed prominently as this document's own verdict, be mistaken for
Karim's actual sign-off? Genuinely present: yes, unambiguously — file 08's
Decision States vocabulary defines APPROVED as "the owner explicitly
signed off," a specific, reserved, cross-agent term, and §39 used the exact
same word in a large bolded callout for a self-issued, document-level
determination. This is not a hypothetical misreading risk; it is a direct
collision with an existing reserved term, structurally identical to the
CONSOLIDATED/Code-verified collision already fixed elsewhere in this document.
**Verdict: genuine defect, fixed** — §39's determination is relabeled
below, without changing its substantive content.

*Concern G — Speed Drills.* Restated: is excluding wrong reps from CPM
still right, and could a learner (not just the system) misread rising
speed as rising competence? On the first half: re-examined and confirmed —
excluding remains cleaner than counting a wrong rep as zero (which would
misrepresent a speed problem that didn't happen) or as a slow correct
attempt (which misrepresents what happened entirely). On the second half:
genuinely present and previously unexamined — pure exclusion is
susceptible to a survivorship effect, where a learner who fails often but
is fast when right could show a *better* CPM trend than a careful,
slightly-slower learner, because the failures are invisible to the number
rather than costing anything visible. This task's brief explicitly forbids
solving this with a composite score; the fix instead surfaces the already-
computed exclusion count/rate alongside the CPM trend, so the missing
context is visible without inventing a new metric. **Verdict: existing
rule confirmed sound; a real, separate interpretation risk found and
closed with a display requirement, not new measurement machinery** (§17).

**Part D — full coherence sweep, beyond the seven named concerns.** Walking
Independent, Correct, DEMONSTRATED_INDEPENDENT, CONSOLIDATED, TRANSFERRED,
NEEDS_REINFORCEMENT, Retention, Assessment, Evidence, and Progression
against each other, with particular attention to the eight failure modes
this pass's brief named:

- *Circular definitions:* none found. The dependency chain runs one
  direction (attempt → independence flag → DEMONSTRATED_INDEPENDENT →
  count → CONSOLIDATED → Scenario-linked and independent → TRANSFERRED), with
  exactly one deliberate backward transition (demotion, §7 Fix 3), which is
  a feedback loop, not a circularity. §7 Fix 4's own text now states
  explicitly why demotion doesn't create a circular dependency between
  CONSOLIDATED and TRANSFERRED — this was checked specifically, not assumed.
- *Evidence justifying a state that determines the evidence's own
  validity:* none found beyond Concerns A/B/E, all now fixed.
- *Assisted evidence becoming independent evidence:* this was Concerns A
  and E exactly; both fixed.
- *Stronger learner-facing language than the evidence supports:* checked
  against Principle 6 and its extensions throughout; no new violation
  found beyond Concern F's labeling issue, fixed.
- *Individually reasonable definitions that conflict combined:* this was
  Concern B exactly (CONSOLIDATED's alternate path vs. TRANSFERRED's
  restriction, each reasonable alone, diverging together); fixed by
  unifying them.
- *Implementation requirements the Event Log may not support:* already
  tracked (§21, §29); Concern E's fix arguably *eases* this rather than
  worsening it, since independence no longer requires the counter's
  write-path to be touched by a second trigger condition — only the
  read-time computation needs to consider a second input.
- *A "diagnostic" rule that still functions as a corrective:* re-examined;
  not eliminated (it cannot be, from documentation alone) but given a
  sharper operational test (§13) than "does it feel like an answer."
- *A retention or transfer claim stronger than its observation basis:*
  this was Concern C (retention) and Concern A (transfer) exactly; both
  fixed.

**Part E — second-order attack on this closure pass's own fixes,** asking
whether any of A–G's remedies created a new problem, per this pass's own
explicit instruction to test rather than assume:

- Does requiring independence for TRANSFERRED (Fix A) make transfer
  evidence too hard to obtain, given only one scenario exists? Tested in
  Concern A's own reasoning above — no, because the restriction is
  per-skill, not per-scenario-attempt; a learner is not blocked from ever
  reaching TRANSFERRED merely because they needed help with something
  else.
- Does collapsing CONSOLIDATED's alternate path into a general count (Fix B)
  quietly make CONSOLIDATED *easier* to reach than intended, since a Scenario
  success now needs to meet the same bar as a drill success rather than
  being treated as inherently stronger? No — the two were never meant to
  be ranked against each other, only required to meet the same minimum
  qualifying bar (independent, checklist-complete, and — for Scenario
  successes — load-bearing); nothing about difficulty was loosened.
- Does the three-way retention split (Fix C) create new authoring or
  display burden disproportionate to the risk it closes? Modest burden,
  proportionate: no new field, no new computation, only a requirement that
  existing timestamp data not be hidden behind a binary label.
- Does moving the independence signal off the counter (Fix E) make the
  independence flag itself harder to reason about, now that it has two
  inputs instead of reading one existing field? Slightly more inputs to
  track, but each input is simpler and cleanly separable — this is judged
  a net reduction in risk, not an increase, because it removes a semantic
  ambiguity that would otherwise have had to be resolved by someone with
  standing this document doesn't have.
- Does the CPM co-display requirement (Fix G) risk being read as a
  disguised composite score? No — the two numbers (CPM, exclusion
  rate/count) are shown side by side, never combined into one value; this
  was a deliberate choice specifically to avoid that risk.

No second-order problem large enough to warrant its own further fix was
found; where a residual, smaller consideration exists (e.g., the modest
new authoring burden from Fix C), it is named above rather than ignored.

**Part F — minimum justified complexity test, applied to every change made
in this pass.** For each: what concrete problem does it solve, and does it
duplicate, over-build, or pre-build relative to that problem?

| Change | Concrete problem solved | Duplicates or over-builds? |
|---|---|---|
| TRANSFERRED requires independence (Fix A) | Model's highest state reachable with assistance active | No — reuses the existing exclusion concept |
| CONSOLIDATED redefined as a qualifying-success count (Fix B) | Halo-crediting gap in the alternate path; divergent wording | No — a simplification |
| Three-way retention (Fix C) | Stale and fresh evidence reading identically | No — no new field, no new number |
| Kane wording precision (Fix D) | Misapplied "universe" terminology; unqualified Scoring claim | No — wording only |
| Independence flag replaces counter-extension (Fix E) | Canonical mechanism's meaning silently changing | No — removes a mechanism (the counter extension) rather than adding one |
| §39 relabeled (Fix F) | Reserved-term collision with file 08 | No — labeling only |
| CPM co-display (Fix G) | Survivorship-biased speed trend misread as competence | No — no composite score, reuses already-computed data |

Every change in this pass solves a concrete, named problem and adds no
infrastructure beyond what closing that specific problem required. Nothing
proposed during this pass's investigation was rejected for being *too
complex* — each concern's strongest remedy turned out to be a small one.

---

## 39. Final Decision & Design-Readiness Determination

Per this task's governing brief, six questions are answered explicitly
before any judgment is issued.

**A. What is established by strong evidence.** The testing/retrieval
effect (medium-to-large, extensively replicated); the spacing effect (one
of the most replicated findings in learning research); Hattie &
Timperley's finding that feedback content-level matters more than feedback
presence; Kane's four-inference structure as the accepted way to state
assessment-validity claims honestly; error management training's specific,
sizeable transfer effects; and, at the DEIXEN level specifically, file
05's code-verified engine behavior and file 07's evidence-integrity
discipline (four classes, no-fabrication rules, hint-honesty).

**B. What is a deliberate DEIXEN design decision**, informed by but
distinct from the evidence in A: the five-state skill model's exact shape;
the checklist-based minimum passing standard as this project's specific
implementation of the general SBML pattern; the three-tier assistance
ladder under one counter; the diagnostic/corrective feedback split; the
graduated demotion rule; Lesson 5's two-event evaluation rule; the specific
integration of the spaced-retrieval prompt into Flight Deck; and the
interim numeric defaults (2 and 2).

**C. What is strongly supported by reasoning but still unvalidated:** that
the checklist approach scales cleanly to all 37 commands; that the
diagnostic/corrective line holds up against real authored content, not just
the one worked example in this document; that Partial Reveal's precision
benefit isn't offset by an increase in assistance-seeking frequency; that
an interim default of 2 is closer to right than 1 or 3; that the graduated
demotion rule's complexity is worth its currently-small practical footprint.

**D. What requires implementation verification:** whether the Event Log's
timestamp granularity supports the independence flag's two inputs —
hint/reveal-adjacency *and* corrective-feedback-adjacency — and chain-
sequence continuity; `XE`'s actual system behavior against unsupported
element types; and whether an accurate, pre-completion PNR numbering view
exists for Known Issue #7's mitigation.

**E. What requires real learner testing or longitudinal evidence:** every
PROVISIONAL number in this document (CONSOLIDATED's repeat-count, the
reinforcement-failure count, the escalation count, the spaced-retrieval
interval); whether the unified exclusion rule feels fair rather than
punitive; whether retrieval-over-exposure produces its expected effect for
DEIXEN's specific audience; whether the three-tier ladder changes
assistance-seeking frequency; whether the Coach-fading instance in §15 is
noticed or valued; whether Ghost Mode's unlimited replay creates a
confidence-reality gap.

**F. What is intentionally deferred, and why:** full 37-command tiering
and checklist authoring (curriculum-authoring work, outside this
document's scope); the Customer Service choice-quality rubric and feedback
content (Decision 6's own pending contract, domain-expert work); general
Coach-proactivity fading beyond the one narrow instance adopted (no usage
data to calibrate it responsibly); every Scenario-Bank-dependent risk
(#3/#5/#8/#13 in §27, explicitly out of Decision 8A's current scope); any
SME/domain validation of Amadeus claims (Decision 7's own separate,
still-pending process, which no amount of learning-design work
substitutes for); a full rename of the CONSOLIDATED skill state to resolve its
naming collision (larger than this revision's stated purpose); and an
authoring-cost estimate for scaling this system to all 37 commands (not a
question this document has the standing or the information to answer
alone).

### Determination

The second adversarial pass (§38 Parts A–B) found nine issues and fixed
four directly. A later, separate closure pass (§38 Parts C–F) investigated
seven further concerns and, after arguing both sides of each rather than
assuming any were valid, fixed six of them — including correcting, not
merely clarifying, a place where this document had drifted into silently
redefining a canonical mechanism's meaning (Concern E). That correction
also resolved one of the five items originally left open here (the
counter-interpretation question); it no longer needs anyone's confirmation,
because the design no longer does the thing that needed confirming.

What remains open after both passes — assistance-seeking frequency under
the three-tier ladder, the curriculum-authoring cost question, borderline
diagnostic/corrective cases in real (not yet authored) content, and the
graduated-demotion rule's practical value at current one-scenario scale —
each still requires either real usage data, real content that doesn't
exist yet, or a scope/resourcing judgment outside a learning-design
document's authority. None can be responsibly resolved by further
document-level reasoning without inventing an assumption this document has
no basis for, which is precisely the condition this task's stopping
criterion describes.

> **DESIGN-READINESS DETERMINATION: this document has reached the
> strongest learning design currently justifiable from the available
> evidence and current DEIXEN constraints.**

This is a design-quality determination, not a governance approval — it is
not the "the owner explicitly signed off" APPROVED that file 08's shared
decision-state vocabulary reserves for Karim, and should not be read as
that. It means the documented design has been pushed, through one external
adversarial review, one internal self-attack, and one further closure
pass, to the point where every remaining gap is explicitly named, correctly
categorized (B through F above), and pointed at the specific party or
evidence that can actually close it — not smoothed over, and not left for
someone else to discover the hard way. It does **not** mean real learner
effectiveness has been proven; nothing in this document, however carefully
reasoned or however well the citations in §3 replicate elsewhere,
substitutes for real DEIXEN learners actually using this design.

---

## 40. Final Learning Design Principles

If only a handful of things from this document survive review, they should
be these — the first is unchanged from Revision 1 because nothing found
since gave a reason to touch it; the rest are refined by what this revision
actually had to fix:

1. **A success only counts as independent if nothing helped it along in
   that attempt — and "helped it along" now means through *any* channel,
   not only a Coach-initiated hint.** Everything else in the skill model
   follows from that one line; Revision 1 stated the line but didn't fully
   enforce it, and closing that gap was this revision's single most
   important piece of work.
2. **"Correct" means meeting an explicit, file-05-derived checklist, not a
   feeling of success.** A vague bar cannot be audited; a checklist can be,
   and can be checked for completeness the way any other claim in this
   project already has to be.
3. **Evidence must always be a live read of what actually happened, never
   a separately maintained number that can drift from it** — unchanged,
   and now extended to cover checklist-item satisfaction and chain
   continuity, not only the independence flag.
4. **No learner-facing sentence may claim more about real Amadeus than
   Decision 7 has actually confirmed** — unchanged, because this boundary,
   not any amount of instructional design, is what ultimately decides
   whether DEIXEN's training claims are honest.
5. **A design document can close gaps in its own enforcement; it cannot
   close gaps that only real learners, real implementation, or real domain
   experts can close** — stated as its own principle this revision,
   because §39's approval determination depends on this distinction being
   taken seriously rather than treated as a disclaimer.

---

## 41. Canonicalization Note

This document remains a **DRAFT AUTHORITY**, not canon, regardless of the
determination in §39 or the closure status in §42. Per the Operating
Constitution's classification rules, nothing above may be treated as
decided, delegated, or approved by virtue of having been written down
here, revised once, reviewed once externally, self-attacked once more, and
closed out once further. The intended path is unchanged: current canonical
knowledge → this analysis → external adversarial review (complete) → this
revision and its own second self-attack (complete) → a further closure
pass re-testing seven specific concerns (complete) → human/product-owner
review → approval → canonicalization. The first five steps are now done.
The last two are Karim's, not this document's, to perform. Until they
happen, every **LEARNING DESIGN DECISION** and **RECOMMENDATION** above
remains a proposal, every **OPEN QUESTION** remains open, and every
**REJECTED/DEFERRED** item stays exactly that unless someone with standing
explicitly revisits it with new evidence — consistent with the Operating
Constitution's Change Discipline (§6): not because revisiting would be
hard, but because that is the only way "closed" and "proposed" keep
meaning anything in this project.

---

## 42. Final Closure Determination

**What changed in this pass.** Seven concerns (A–G) were investigated using
the seven-step method their governing brief required — restate, test for
genuine presence, argue both sides, decide, and only then intervene, never
assuming the concern was correct in advance. Six resulted in a real,
targeted fix: TRANSFERRED now explicitly requires independence, scoped per
skill so it cannot destroy evidence about anything else in the same
scenario attempt (§7 Fix 4); CONSOLIDATED's alternate path was found to lack
TRANSFERRED's own anti-halo-crediting restriction and was unified with it,
which simplified the wording rather than adding to it (§7 Fix 4, §10);
Retention was split into three explicit, non-numeric labels so a stale
skill stops reading identically to a freshly-confirmed one (§10, §24);
Kane's validity-framework wording was corrected where it had technically
misapplied the term "universe," and Scoring's design-level status was made
explicit (§20); Speed Drills' CPM trend now requires its exclusion
rate/count to be shown alongside it, closing a survivorship-bias
interpretation risk without a composite score (§17); and §39's determination
was relabeled to stop colliding with file 08's reserved use of "APPROVED"
(§39). The seventh and most consequential finding was that Revision 2's
own fix for the external review's P1-2 finding had a defect of its own:
routing corrective feedback through the canonical hint counter would have
silently redefined what that counter means, and two future implementers
could reasonably have built it two different ways. That mechanism was
replaced, not merely clarified — independence is now a separate,
two-input Calculated flag, and the canonical counter keeps its original,
untouched, single meaning (§7 Fix 2, §13, §15, §21, §29). A full coherence
sweep across ten core terms and a second-order attack on this pass's own
seven fixes (§38 Parts D–E) found no further defect large enough to act on,
and a minimum-justified-complexity check (§38 Part F) confirmed every fix
made solves a stated, concrete problem without duplicating an existing
mechanism or pre-building infrastructure ahead of need.

**What was deliberately left unchanged**, because the sweep re-examined it
and found no defect: the five-state skill model's basic shape; the
correctness-checklist concept itself (only its diagnostic/corrective
boundary was given a sharper operational test, not redesigned); the
practice/assessment functional collapse; Decision 8A's frozen scope; the
full REJECTED list from Revision 1 and Revision 2; the decision to exclude
(not zero-out) failed Speed Drills reps from CPM; and the graduated
demotion rule, whose practical impact is currently small but whose
underlying principle — proportional evidentiary treatment — was confirmed
worth keeping now rather than retrofitting later.

**Which concerns were rejected, and why.** No concern was rejected as "not
a real issue" — all seven surfaced something genuine. Within several,
though, a more drastic remedy was considered and explicitly rejected in
favor of a smaller one: requiring zero assistance across an *entire*
scenario attempt, rather than per-skill (Concern A) — rejected as
destroying evidence the concern's own caution warned against losing;
eliminating CONSOLIDATED's Scenario-linked path entirely (Concern B) —
rejected as an unjustified restriction once the actual gap (halo-crediting)
was identified and fixed directly; inventing a numeric staleness threshold
for retention (Concern C) — rejected because the qualitative three-way
split closes the same gap without a fabricated number; a second, dedicated
counter for corrective feedback (Concern E) — rejected exactly as this
pass's brief instructed, in favor of a flag that isn't a counter at all;
and a composite speed-accuracy index (Concern G) — rejected in favor of
plain co-display. Separately, and unchanged from the prior pass: Revision
2's own rejection of severity-weighted NEEDS_REINFORCEMENT triggers (the
external review's P3-5) still stands, for the same reason it did then — no
evidence base exists to construct a severity taxonomy responsibly.

**Which concerns were accepted and fixed:** all seven, A through G, each
with the smallest intervention that closed the actual gap found — detailed
above and in §35 Part D, §38 Parts C–F.

**What remains open, and why.** Nothing that remains open does so because
it was overlooked. Each item below requires evidence, access, or authority
this document does not have.

1. **Implementation verification** — whether the Event Log's timestamp
   granularity supports the independence flag's two inputs
   (hint/reveal-adjacency and corrective-feedback-adjacency, §7 Fix 2,
   §21); whether chain-sequence continuity for workflow-level practice is
   reconstructable from the existing four fields or needs a minimal
   correlation addition (§11, §21); `XE`'s actual system behavior against
   an unsupported element type (§14); whether an accurate, pre-completion
   PNR numbering view exists to mitigate Known Issue #7 (§14).
2. **Canonical / governance confirmation** — whether the CONSOLIDATED
   skill-state term should eventually be renamed to fully resolve its
   naming collision with file 05's "Code-verified" (§36); this pass
   *removed* one item that used to sit in this category (whether the
   counter's meaning could legitimately be extended) by correcting the
   design so the question no longer arises.
3. **Domain / SME validation** — command-level Amadeus accuracy for
   `AN`/`SS`/`FQD`/`FXP` and, eventually, the other 33 documented commands;
   whole-workflow validity of the frozen slice; the acceptability of the
   engine's built-in simplifications for the job-readiness goal — all
   Decision 7's own separate, still-pending process, unaffected by this
   pass.
4. **Curriculum authoring** — full tiering and checklist authoring beyond
   the four frozen-slice commands (§8, §30); the Customer Service
   choice-quality rubric and feedback content (§19, gated by Decision 6's
   own pending contract); Lesson 17's undefined content and the 8
   future-plan Advanced lessons (file 13's existing Knowledge Recovery
   items, untouched by this pass).
5. **Real learner validation** — every PROVISIONAL number in this document
   (CONSOLIDATED's repeat-count, the reinforcement-failure count, the
   escalation count, the spaced-retrieval interval); whether the unified
   exclusion rule feels fair rather than punitive; whether Partial Reveal
   changes assistance-seeking frequency (§38 Part E); whether the
   diagnostic/corrective boundary holds against real, not yet authored,
   content; whether retrieval-over-exposure produces its expected effect
   for DEIXEN's specific audience; whether the Coach-fading instance in
   §15 is noticed or valued; whether Ghost Mode's unlimited replay creates
   a confidence-reality gap.

### Closure Status

> **CLOSED WITH EXPLICIT DEPENDENCIES.**

The architecture is coherent — the full coherence sweep and second-order
attack in §38 Parts D–E found nothing further to fix — but the five
categories above are real, and none of them can be closed by more document
review. This is not the unconditional status: a document with this many
live dependencies on implementation access, domain expertise, curriculum
authoring, and real learners has not earned a claim that nothing further
is needed at any level, only that nothing further is needed *at the
document level*.

«This document does not establish real learner effectiveness. That
requires implementation and empirical testing.»

No unresolved document-level learning-design defect remains that can be
responsibly fixed from the currently available evidence without inventing
assumptions, violating canonical constraints, or adding unjustified
complexity.

This document is not canonical. It remains DRAFT AUTHORITY, per §41 above,
until Karim reviews it and the canonical governance chain explicitly
promotes it. No further broad redesign is warranted by anything found in
this pass — every fix made was targeted, and the coherence sweep found no
genuine defect large enough to require one.
