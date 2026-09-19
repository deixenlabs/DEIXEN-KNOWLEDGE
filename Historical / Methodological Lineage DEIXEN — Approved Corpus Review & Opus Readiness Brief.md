AeroBridge — Approved Corpus Review & Opus Readiness Brief

1. Purpose

Prepare the AeroBridge project corpus and operating environment for eventual handoff to Opus.

The objective is not merely to make the files look organized.

The objective is to produce a corpus that is:

- coherent,
- authoritative where appropriate,
- explicit about uncertainty,
- internally consistent,
- operationally usable,
- resistant to stale assumptions,
- and ready for high-level reasoning and execution.

The governing priority is:

Quality first. Efficiency second.

Additional reasoning, context, verification, or tooling should be used whenever they materially improve correctness, reliability, continuity, decision quality, or project value. Avoid resource use that does not provide meaningful benefit.

---

2. Governing Review Principles

All phases use the same foundational discipline:

- Evidence before opinion.
- Decision before execution.
- Canonical truth outranks suggestions, history, memory, and conversational context.
- Old does not mean wrong merely because it is old.
- New does not mean correct merely because it is new.
- Unsupported assumptions must not become authoritative.
- Unknown remains unknown.
- Do not invent missing information.
- Any file, instruction, assumption, or previous decision may contain an error, including user-provided material.
- Correct a defective path when doing so preserves the intended outcome and does not violate a higher-authority constraint.
- If correction would change the intended outcome, scope, authority model, or an already-approved decision, escalate for explicit human decision.
- No mechanism should be introduced merely because it is technically possible.
- Do not change architecture for cosmetic or unnecessary reasons.
- Review the process itself during execution; the review method is not exempt from correction.

Phase 0 standard is revisable

The review standard created in Phase 0 is itself subject to correction.

If a later phase reveals that the standard is incomplete or defective:

1. Correct the standard.
2. Determine whether completed phases are affected.
3. Re-flag or revisit only affected areas.
4. Continue only after the impact is understood.

---

3. Authority and Execution Boundary

The review process is advisory unless Karim explicitly authorizes execution.

The following distinction is mandatory:

«Findings and proposed corrections are advisory outputs for Karim's approval unless Karim has explicitly authorized execution of a specific category of change.»

Therefore, a Phase 5 or Phase 6 finding such as:

- keep,
- modify,
- split,
- merge,
- delete,
- reclassify,
- move,
- or replace

is a proposed disposition, not automatic permission to modify canonical project files.

No silent canonical-file changes are implied by the review plan.

Karim remains the final human authority for project decisions.

---

4. Source Selection and Current-State Discipline

When multiple representations of the same information exist across:

- Project Knowledge,
- conversation history,
- handoffs,
- working notes,
- other project files,
- or other contextual sources,

the process must explicitly determine which representation is current and authoritative before relying on it.

Historical conversation context does not become authoritative merely because it is visible in the current session.

For the Sixth Pass specifically:

The current version stored in AeroBridge Project Knowledge is the current authoritative reference version.

Earlier conversational wording is historical revision context, not a competing authoritative copy.

Document size is not, by itself, an authority rule.

---

5. Working-State Discipline

Each major phase or review group must have a lightweight current-state marker.

The purpose is not to create a full version-control bureaucracy.

The marker should simply make it explicit:

- which Rules state is current,
- which Prompt state is current,
- which Handoff state is current,
- which corpus state is being reviewed,
- and which approved changes have already entered the working corpus.

Example:

«“As of Phase N, work is being conducted under the currently approved Rules / Prompt / Handoff state.”»

This prevents stale-context review and accidental return to earlier versions.

---

6. Phase 0 — Establish the Review Standard

Before modifying or reviewing project files, establish the shared review standard defined above.

Confirm:

- authority model,
- truth categories,
- evidence discipline,
- uncertainty handling,
- execution boundary,
- correction rule,
- quality/efficiency principle,
- risk-sensitive review principle,
- and source-selection discipline.

Also establish the use of independent review accounts described in Section 12.

Output

A single, stable-but-revisable review standard governing all subsequent phases.

---

7. Phase 1 — Review the Operational Rules File

Review the Rules file at two levels.

A. Internal correctness

Check:

- authority clarity,
- definition of truth,
- distinction between decision, proposal, and execution,
- verification and escalation,
- user instructions,
- anti-fabrication behavior,
- execute vs. stop conditions,
- protection against incorrect instructions,
- contradictions,
- redundancy,
- and practical applicability.

B. Operational usability

Ask:

«If an agent reads this file without additional explanation, can it determine how to behave when a situation is unclear?»

Also establish the lightweight knowledge-navigation category structure here, if the final review confirms it belongs in Rules.

The routing structure should:

- identify where the agent should look first by category,
- never override the underlying authoritative source,
- never become a new source of truth,
- allow search expansion when the expected source is missing, ambiguous, contradictory, or insufficient,
- avoid brittle section-level references.

Output

A corrected operational Rules file and, if justified, the category-level knowledge-navigation structure.

---

8. Phase 2 — Review Prompt Engineering

Review how the Prompt system translates operational rules into usable instructions.

Check:

- task definition,
- intent,
- context,
- source selection,
- boundaries,
- requested behavior,
- verification,
- completion criteria,
- avoidance of unnecessary context repetition,
- conflict prevention with Rules,
- and protection against user instructions that contradict established truth.

Use the existing decision test rather than inventing a competing one:

- Rule when the requirement is stable and governance-level.
- Prompt when it is task-specific instruction.
- Skill when a repeated narrow procedure is sufficiently stable.
- Hook when deterministic enforcement is required.
- Plugin only when multiple related capabilities need to move together.

Do not force creation of any mechanism merely because the category exists.

Output

A practical Prompt system that is strong without duplicating the entire operating constitution.

---

9. Phase 3 — Review Handoff and Continuity

Review how work moves between sessions.

Determine:

- what must transfer,
- what should not transfer,
- what is current state,
- what is an approved decision,
- what is only historical context,
- what must be rechecked against the canonical corpus,
- how open questions are carried,
- how useful failed approaches are preserved,
- and how stale historical assumptions are prevented from becoming current truth.

Historical context should improve continuity without becoming a competing source of truth.

Output

A Handoff system that provides strong continuity with minimum necessary context.

---

10. Phase 4 — Integrate the Three Operational Files

Review Rules + Prompt + Handoff together.

Check:

Authority

Does one layer contradict another?

Ownership

Is responsibility for any rule duplicated?

Duplication

Is the same knowledge unnecessarily copied?

Contradiction

Could the same situation produce different answers?

Sequence

Does Handoff provide information that Prompt and Rules can actually use?

Execution

Do the Rules demand behavior the Prompt or actual environment cannot support?

Boundaries

Has a decision become a Prompt instruction?
Has something that requires deterministic enforcement been left as text?

Output

The three files must form:

«Three complementary layers of one operating system.»

---

10.1 Pilot Application Gate

Before proceeding to the full corpus review, apply the newly integrated Rules + Prompt + Handoff to one real corpus file.

The pilot file should be:

- sufficiently important,
- genuinely complex,
- and representative enough to expose weaknesses in the operating layer.

The current recommended pilot is File 07, because it combines high authority, multiple evidence/decision types, and meaningful cross-references.

The pilot is a practical test, not a full corpus review.

Gate

The operating layer must demonstrate that it can be used correctly in practice before the full corpus review proceeds.

If the pilot reveals a material weakness:

- pause,
- correct the affected operational layer,
- recheck the integrated triad,
- then continue.

---

11. Phase 4.5 — Establish the Corpus Review Sequence

Do not assume that the remaining corpus should be reviewed in file-name order or historical order.

Before Phase 5 execution begins, determine the best progressive review path based on:

- authority,
- dependency,
- downstream impact,
- ownership,
- error propagation risk,
- factual risk,
- and expected rework.

Determine:

- review order,
- grouping,
- dependency logic,
- intermediate audit points,
- transition gates,
- reordering conditions,
- and expected output of each group.

The sequence must remain adaptive.

New evidence may change the dependency structure or make another order more appropriate.

Do not continue with an outdated order merely because it was initially chosen.

---

12. Independent Review Accounts

The project may use the additional available Claude accounts as selective independent reviewers.

They are not parallel editors and do not create competing project copies.

The operating model is:

«One authoritative working corpus + selective independent review.»

The additional accounts must not:

- independently maintain parallel canonical copies,
- modify competing corpus versions,
- determine correctness by majority vote,
- or become alternate sources of truth.

When used, an independent reviewer must receive:

- the exact current state/version being reviewed,
- a clearly bounded artifact or question,
- the purpose of the review,
- and the relevant decision context.

Its role is to stress-test a defined target, not recreate the whole project independently.

Independent review should be used only where it provides meaningful additional value.

Designated high-value checkpoints

Current recommended checkpoints:

- Phase 4 — operational-layer integration,
- Phase 6 — corpus-wide coherence,
- Phase 8 — final closure.

These remain subject to the same quality-over-efficiency principle; they are not mandatory merely for repetition.

Agreement among multiple Claude accounts is not proof of correctness.

Evidence, reasoning, and source quality determine the decision.

---

13. Phase 5 — Deep Review of the Remaining Corpus

Execute the review sequence established in Phase 4.5.

Review each file as an independent entity first.

For each file examine:

A. Function

What is the file's real purpose?

B. Ownership

What knowledge does it own?

C. Boundaries

What should it not decide?

D. Truth status

Distinguish:

- decision,
- rule,
- proposal,
- history,
- hypothesis,
- unknown.

E. Currentness

Are any sections stale?

F. Quality

Look for:

- contradictions,
- unsupported claims,
- exaggeration,
- ambiguity,
- unusable instructions.

G. Agent usability

Can an agent actually use the file correctly?

H. Size and placement

Is the file too large?
Does any content belong elsewhere?

I. Impact

What other files could be affected if this file changes?

J. Proposed disposition

Possible outcomes include:

- retain,
- modify,
- split,
- merge,
- relocate content,
- retire historical material,
- classify as non-authoritative.

These are advisory proposals unless explicitly authorized for execution.

---

13.1 Risk-Weighted Review Depth

Do not apply identical depth mechanically to every file.

For each file/group consider:

- authority,
- downstream impact,
- dependency count,
- probability of error propagation,
- factual risk,
- scope,
- and consequence of being wrong.

Assign a qualitative review depth:

High / Medium / Low

Do not manufacture numerical precision unless a numerical system is demonstrably useful.

Higher-risk or higher-impact material receives deeper verification and, where justified, additional independent review.

---

14. External-Fact Verification

During corpus review, distinguish between:

Internal corpus claims

Claims that can be validated through internal consistency and approved project evidence.

External/platform-dependent claims

Claims that depend on:

- current platform behavior,
- tool capabilities,
- software behavior,
- current service rules,
- or other external realities.

Internal consistency alone is insufficient for the latter.

Such claims should be flagged for appropriate re-verification when required.

---

15. Intermediate Audits and Gates

Audits and gates are different.

Audit

An audit asks:

«Is there a problem or inconsistency?»

Gate

A gate asks:

«Is the current review group sufficiently stable to become the foundation for downstream work?»

A completed audit does not automatically authorize progression.

If a gate identifies material instability:

- pause,
- correct,
- reassess the affected area,
- and only then continue.

---

16. Impact-Based Rechecking

Whenever an approved change occurs, use this reusable procedure:

1. Identify what changed.
2. Identify direct and indirect dependencies.
3. Determine the smallest materially affected scope.
4. Recheck only that affected scope.
5. Continue once the affected scope is stable.

Do not automatically re-review the entire corpus.

Do not assume that nothing else is affected.

---

17. Recommended Progressive Corpus Sequence

The current recommended starting sequence is:

Group A — Authority Foundation

- Operating Constitution
- File 08
- File 07
- File 13

These are tightly coupled and establish authority/truth foundations for downstream work.

Gate 1

Confirm the group is internally coherent before downstream review.

---

Group B — Domain Foundation

- File 03
- File 05
- File 00

These provide foundational project/domain context used widely downstream.

Gate 2

Confirm Group B does not contradict Group A.

Recheck relevant conclusions from File 14 where applicable.

---

Group C — Dependent Content

- File 06
- File 04
- Roadmap

Gate 3

Perform an explicit Roadmap freshness/consistency check because the Roadmap has previously become stale.

---

Group D — Learning Foundation

Review sequentially:

Learning Design Specification → Learning Experience Architecture

Do not treat these as entirely independent because LEA translates the foundation established by LDS.

Gate 4

Confirm the learning pair does not silently conflict with the evidence/decision contracts established upstream.

---

Group E — Visual Design Input

- Visual Design Execution Brief

This remains later in the sequence because its downstream dependency/ripple risk is currently lower than the authority and knowledge foundations.

---

Group F — Operating-Environment / Sixth Pass Chain

This is a separate track.

It has already undergone extensive preparation and should not simply be re-derived as if it were an untouched corpus file.

Instead:

- verify relevant external/platform facts for freshness,
- maintain the current Project Knowledge reference,
- and cross-check its conclusions against the stabilized corpus during later integration/readiness review.

---

18. Reordering Rule

The sequence is adaptive.

If a discovery in an upstream group materially changes a decision or dependency:

- identify the affected downstream scope,
- pause only the affected path,
- update the relevant working state,
- perform impact-based rechecking,
- and resume when the affected foundation is stable.

Do not restart the entire corpus review by default.

---

19. Phase 6 — Corpus-Wide Coherence Review

After the progressive file review, evaluate the corpus as a single knowledge system.

Review:

1. Sources of truth.
2. Contradictions.
3. Knowledge ownership.
4. Duplication.
5. Broken references.
6. Stale material.
7. Knowledge gaps.
8. Authority leakage.
9. File-boundary violations.
10. Effects of approved changes.
11. Effects of Rules/Prompt/Handoff on corpus behavior.
12. Continuity and historical-context behavior.
13. Operational duplication across Rules, Prompt, Skills, Hooks, and canonical material.
14. Knowledge-navigation/source-routing freshness, if routing guidance exists.

The objective is not merely to confirm that every file is individually acceptable.

It is to confirm that the corpus works as one coherent system.

Independent review checkpoint

Use an additional Claude account selectively here to stress-test the stabilized corpus from an independent context.

The account receives the exact state under review and a bounded coherence question.

No majority vote is used.

---

20. Knowledge Navigation / Source Routing

If the final Rules review confirms the need, maintain a lightweight category-level source-routing structure.

Its purpose:

«tell the agent where to look first.»

It must not:

- duplicate the underlying knowledge,
- override the authoritative source,
- become authoritative itself,
- or prevent broader searching.

When the expected source is:

- missing,
- ambiguous,
- contradictory,
- or insufficient,

the agent must broaden the search.

The routing structure should remain category-level rather than pointing to fragile individual sections.

Lifecycle

Do not create a separate routing-maintenance system.

Instead, routing guidance is checked as part of existing corpus audits, especially broken references and ownership changes.

If a knowledge owner or source changes, the routing guidance is corrected as part of that existing review.

---

21. Phase 7 — Final Opus Readiness Review

Change perspective.

Assume:

«Opus enters now and inherits the project.»

Ask:

- Does Opus know its role?
- Are authority boundaries clear?
- Does it know where truth lives?
- Does it know what it may trust?
- Does it know when to doubt?
- Does it know when to say UNKNOWN / VERIFY / ESCALATE?
- Does it know what to do when files disagree?
- Can it recognize that the user's requested path may itself be wrong?
- Can it correct a defective path without changing the intended outcome silently?
- Does it know how to continue from prior sessions?
- Can it distinguish historical context from current truth?
- Does it know when to use Rule, Prompt, Skill, Hook, Plugin, or Subagent?
- Does it know when not to use them?
- Does it know when additional resources are justified?
- Can it enter the corpus without rediscovering the operating system?

Reachability requirement

Do not ask only:

«Does the required knowledge exist?»

Also ask:

«Can Opus reach the required knowledge through its normal operating path without hidden prior context, tribal knowledge, or undocumented assumptions?»

This applies to:

- operating rules,
- authority,
- decisions,
- verification logic,
- continuity,
- and knowledge-navigation guidance.

---

22. Plan Change vs. Goal Change

Throughout all phases, distinguish between:

Method correction

Changing how the work is performed while preserving the intended outcome.

This may be corrected during execution when justified.

Goal or authority change

Changing:

- project objective,
- scope,
- authority model,
- or an already-approved decision.

This requires explicit human decision.

An agent must not silently transform one into the other.

---

23. Phase 8 — Final Closure Gate

At the end, exactly three outcomes are permitted.

State 1 — Ready for Opus

No material issue remains that can reasonably be solved before handoff.

State 2 — Material Gap

A real unresolved issue remains.

Action:

- correct it,
- determine the affected scope,
- recheck only that scope,
- then return to closure.

State 3 — Intentionally Unresolved

The question cannot be responsibly settled without:

- Opus,
- actual implementation,
- external verification,
- or another genuinely unavailable authority.

Mark it explicitly as:

Opus-dependent / Project-dependent / Evidence-dependent

and stop.

Do not invent an answer simply to close the file.

Final independent review

Use the designated independent-review checkpoint here as a final adversarial dress rehearsal, provided it materially improves confidence.

It reviews the exact current closure state and does not modify the authoritative corpus.

---

24. Final Operating Sequence

Phase 0 — Review Standard
↓
Phase 1 — Rules
↓
Phase 2 — Prompt
↓
Phase 3 — Handoff
↓
Phase 4 — Integration + Pilot + Independent Review
↓
Phase 4.5 — Corpus Review Sequence
↓
Phase 5 — Risk-Weighted Progressive Corpus Review
↓
Intermediate Audits + Gates + Impact-Based Rechecking
↓
Phase 6 — Corpus-Wide Coherence + Independent Review
↓
Phase 7 — Opus Readiness + Reachability
↓
Phase 8 — Final Closure + Independent Review
↓
Handoff to Opus

---

25. Non-Negotiable Operating Constraints

Throughout the entire process:

- One authoritative working corpus.
- No parallel editing of competing corpus copies.
- Additional Claude accounts are advisory reviewers only.
- No correctness-by-majority voting.
- Findings are not execution authority.
- Evidence outranks confidence.
- Unknown remains unknown.
- Historical context does not become authority.
- Source-routing guidance does not become a source of truth.
- Review depth follows risk and impact.
- Audits do not automatically authorize progression; gates do.
- Approved changes trigger impact-based rechecking.
- Do not repeat full reviews when only a bounded affected area changed.
- Do not introduce mechanisms without a justified problem.
- Quality takes priority over arbitrary token/time savings.
- Efficiency means eliminating unnecessary work, not eliminating necessary verification.
- If the method itself proves defective, correct the method before continuing.
- If a proposed correction changes the intended outcome or approved authority, escalate to Karim.

---

26. Definition of Done

The preparation is complete only when:

1. The operational layer is internally coherent.
2. The operating layer has been practically sanity-tested.
3. The remaining corpus has been reviewed in a deliberate dependency/authority-aware sequence.
4. Review depth has been proportionate to risk and impact.
5. Intermediate audits and gates have been passed where required.
6. Approved changes have received impact-based rechecking.
7. Corpus-wide contradictions, ownership problems, stale references, and authority leakage have been addressed or explicitly classified.
8. Knowledge-navigation guidance, if used, is current and non-authoritative.
9. Opus can reach essential knowledge through the normal operating path.
10. Remaining uncertainty is explicit rather than hidden.
11. No material issue remains that can reasonably be resolved before handoff.
12. Any intentionally unresolved issue is clearly marked as Opus-dependent, project-dependent, or evidence-dependent.

At that point:

Stop.

Do not continue refining the preparation process merely because further refinement is possible.
