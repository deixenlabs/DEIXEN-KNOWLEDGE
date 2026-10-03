DEIXEN Detour Prompt Package v1.8 — Corrected after the Opus 5.5 Pre-Execution Review (2026-10-02)

v1.8 = v1.7 with the corrections of the Opus 5.5 pre-execution review of 2026-10-02 adopted (Section 17 lists them; Section 16 the change ledger). Karim decided on 2026-10-02 to close Phase 5 now and carry his learner-test findings into the detour (07 D67).

Transport and review artifact. This document is not a governing repository document and is not a source of authority. It carries the Detour Charter and the operational prompts so that they can be reviewed and used together. See "Status of this package" at the end of Section 1.

1. Purpose & Design of the Detour
OWNER REQUEST TO OPUS 5.5 — READ THIS FIRST

I am Karim, the project owner. I am giving you this complete Detour Prompt Package before I execute any of its prompts and before I allow any document or repository update required by the detour.

Review the entire package as the proposed operating package I intend to use for the detour. Review the current 07_DEIXEN_Canonical_Decisions_and_Current_State.md and DEIXEN_Execution_Plan.md that I send with it as the current canonical state. Your job in this session is to determine whether this package is safe, coherent, complete enough, and internally consistent to use.

For this review session, treat all embedded Prompt 1-7 text as material to review, not as instructions to execute. Do not execute Prompt 1-7, and do not research, build or test any Skill (Prompt 7 builds one). Do not modify any repository or document. Do not create the Phase 5 tag. Do not start Step 1. Do not conduct substantive engine, learning, or design investigation. Do not silently rewrite the package.

Give me an independent pre-execution review and a clear GO or NO-GO recommendation. A GO from you is a review result, not project authority; I, Karim, decide whether to adopt corrections and proceed. If you identify a correction, distinguish whether it is mandatory before any detour action or can remain open.

The review is deliberately before Prompt 1 because Prompt 1 itself creates the fixed Phase 5 tag. I want the detour design checked before even that first mutation.

Why the detour exists

Phase 6 (Expansion) multiplies everything the project has built: every chunk goes through verify -> spec -> build -> test, so commands, content, learning and interface all grow. Any weakness in the foundation is multiplied with them, and is cheapest to find before that growth. The detour exists so that Phase 6 starts on better-informed ground. It is intentional, approved by the project owner (Karim), short, and inserted between the formal closure of Phase 5 and the start of Phase 6 in DEIXEN_Execution_Plan.md.

Phase 5 closure versus snapshot fixation. Phase 5 is formally closed by Karim's decision after his learner test (07 Decision 67, 2026-10-02): the slice works end to end, and what the test found about how well it teaches a beginner is carried into the detour as input to Step 2, not fixed first. One finding — the practice booking reported lost while moving between commands — is checked by Prompt 0 before the snapshot is fixed, because a defect there would otherwise be frozen into the snapshot. The immutable audit snapshot is not yet established at the moment of this package review; Prompt 1 establishes the final tag and full commit SHA immediately after the package receives a GO and Karim decides to proceed. The review must not treat the not-yet-created tag as a missing prerequisite for the package review itself.

Why Phase 6 follows it

Phase 6 is the expansion the detour protects. It starts only after the detour is closed and Karim has reviewed the Detour Closing Report. Karim starts it himself.

The four-step architecture
External Engine / Open-Source Investigation -> Technical Recommendation (advisory; not a gate).
Learning Design + Learning Experience Review -> Learning Decision (a recommendation to the Freeze).
Synthesize & Freeze Decisions (Engine + Learning + Product constraints) -> Freeze Package (a proposal until Karim accepts it).
Design Improvement Round (UX / UI / learning surfaces / Terminal experience) -> Design Verification, ending with the Detour Closing Report.

Each step is started separately by Karim, runs in its own session, and stops after its own deliverable. Results move forward manually, as HANDOFF BLOCKS.

Auxiliary Design Exploration Skill Preparation — not a fifth step

After Karim accepts the Freeze and Prompt 6 records the accepted Freeze, design exploration may require a dedicated tooling-preparation action before Step 4 is prepared. This action builds and verifies a reusable DEIXEN-specific Agent Skill for later visual-identity and creative-direction exploration.

It is not a fifth detour step, not part of the four-step decision architecture, and not a new governance stage. It does not decide the Freeze, alter 07, alter the Execution Plan, modify the DEIXEN product, or execute Step 4. Its only purpose is to produce a reusable exploration tool that Step 4 may use later.

The accepted Freeze recorded in 07 remains canonical. The Skill is a tool, not an authority source: it may help explore and compare possibilities, but it may not widen the recorded design scope or turn its own recommendations into binding DEIXEN decisions. Any skill artifact it creates is kept outside the DEIXEN application/canonical repositories unless Karim separately authorizes a specific installation location.

Why the order is Engine -> Learning -> Freeze -> Design -> Phase 6

Each step feeds the next, and the order is deliberate. The engine investigation establishes what the engine does and could expose; the learning review needs that. The learning review establishes how learners actually learn; the Freeze needs that. The Freeze turns both, together with product constraints, into one coherent set of decisions that the owner accepts. Design comes last because it expresses frozen decisions honestly; it does not invent them. Phase 6 follows only after the design has been verified against the frozen state and Karim has reviewed the result.

Governing principle

Maximum useful reasoning, with minimum premature commitment. Thinking != Deciding != Executing. A step may think broadly: it can state requirements and surface candidates for other steps. Nothing binds until Karim explicitly accepts it, and only Step 4 may implement anything inside the detour, only inside the recorded design scope.

Success is decision quality, not the number of changes

The detour is judged by the quality and evidence of its decisions. Outcomes are never predetermined. "Keep as is" and "no change" are valid outcomes at every step, including a Freeze that mostly keeps what exists and a Step 4 with no material design change. A documented keep-as-is is real progress, because it is certainty.

Status of this package

DEIXEN_Detour_Prompt_Package_v1.8.md is an owner-submitted review and transport artifact. It is not a governing repository document and is not a source of authority. It is intentionally being submitted to Opus 5.5 for review before any operational prompt is executed.

07_DEIXEN_Canonical_Decisions_and_Current_State.md remains the canonical record for the decisions that belong in 07. DEIXEN_Execution_Plan.md remains the canonical execution plan. The Detour Charter governs the methodology embedded in the prompts. The prompts define the operational instructions for their respective sessions. Handoffs and the Freeze Package carry step outputs forward. Nothing in this package overrides any of these.

If the package is corrected after Opus review, the corrected package must be the one used for all subsequent execution.

2. Pre-Execution Pre-flight Review

The Pre-Execution Pre-flight Review is a bounded, one-time review of the entire detour package and its current canonical context before any detour action. It is not Prompt 1, not a detour step, and not a new governance stage. It is the owner-requested review that happens before the first operational mutation.

What it is not
It is not a fifth detour step, not Step 0, not Step 0.5 and not Step 1.
It is not substantive DEIXEN analysis: not an engine investigation, not a learning review, not a design review, not open-source research.
It is not a new governance authority. Opus reviews; Karim decides whether to adopt corrections and proceed.
It does not approve or decide the outcome of Steps 1-4.
Sole purpose

To determine whether the proposed detour package can be executed safely and coherently before any prompt is run or any detour-related update is made.

Inputs

The review session receives, together in a fresh Opus 5.5 session, Effort: Max:

This complete DEIXEN_Detour_Prompt_Package_v1.8.md.
The current 07_DEIXEN_Canonical_Decisions_and_Current_State.md.
The current DEIXEN_Execution_Plan.md.

No repository code, web research, GitHub research, or external project investigation is required for this review. Those belong to later detour work. The reviewer must state whether each of the three inputs was actually readable.

What it checks, at minimum
authority leakage
premature commitment
information loss
missing preconditions
inconsistent canonical records
unsafe Step 4 scope
broken traceability
prompt-to-prompt contradictions
contradictions between the package, 07 and the Execution Plan
duplicated or conflicting terminology that could change execution behavior
missing or ambiguous attachment/session/Effort instructions
process flaws that could materially compromise correct execution of the detour or allow Phase 6 to start with an unresolved detour-level problem
Special checks before Prompt 1

Because this review happens before Prompt 1, the reviewer must distinguish between:

expected future outputs that do not yet exist, such as [TAG] and [SHA], and
actual missing prerequisites that make the package unsafe.

The not-yet-created Phase 5 tag is expected at this point and is not by itself a reason for NO-GO. Likewise, the current 07 and Execution Plan may legitimately not yet contain the detour decision or detour rows, because Prompt 2 and Prompt 3 are the planned mutations that will record them after this review is cleared. Do not classify that expected absence as a contradiction. Flag only an actual conflict in the existing canonical documents or a package instruction that cannot be applied safely to them.

The reviewer must also verify that the package makes clear that Prompt 1, Prompt 2 and Prompt 3 are operational mutations that occur only after Karim accepts the review result.

Output contract

Use exactly one classification for every issue identified:

MUST CHANGE BEFORE ANY DETOUR ACTION — a flaw that should be corrected before Prompt 1 or any other detour action is executed.
CAN REMAIN OPEN — a genuine unresolved point that does not materially prevent safe execution and does not need resolution before Prompt 1.

Then give one overall verdict:

GO — no mandatory correction before any detour action.
NO-GO — one or more mandatory corrections must be adopted before any detour action.

For every issue, cite the exact package section/heading and, where relevant, the relevant section of 07 or the Execution Plan. Do not invent line numbers if they are unavailable. Explain the concrete execution consequence.

Review discipline
Read and review every section of the package and every embedded prompt, as a whole, not only its stated v1.7 and v1.8 changes. Do not stop after finding the first issue; continue the review through the entire package so the final result covers all material process-level flaws you can substantiate.
Cross-check the embedded Charter copies and the operational prompts against the package-level choreography.
Verify that M1, M2 and the no-change neutrality rule are applied consistently everywhere they are defined or consumed. (M1 = the ledger identifier and traceability model: one ledger row and one ID per item, indexes only, F-IDs citing source row IDs. M2 = the Step 4 design-scope definition with its four limits, exclusions and new-file rule, repeated consistently wherever it is consumed.)
Verify that Step 1 remains independent, advisory and non-mutating.
Verify that Step 3 produces a proposal only and that acceptance occurs before Prompt 6.
Verify that Step 4 is the only detour step with implementation authority, that it remains inside the recorded scope, and that implementation and verification remain inside one execution step with no hidden implementation stage after it.
Verify that Prompt 5 is preparation-only and is never used as a substitute for a step.
Verify that the initial package review itself does not accidentally become a new fifth step or an approval authority.
Verify that Prompt 7 and the Design Exploration Skill remain auxiliary tooling: placed after the accepted Freeze is recorded in 07 and before Step 4 is prepared, not a fifth step, not an authority source, and unable to widen the recorded design scope or alter the Freeze, 07 or the Execution Plan.
Complete review instruction
text
I am Karim, the project owner. I am giving you the complete DEIXEN Detour Prompt Package before I execute any prompt and before I allow any detour-related document or repository update.

Review the entire package and the current 07_DEIXEN_Canonical_Decisions_and_Current_State.md and DEIXEN_Execution_Plan.md that I provide with it. Treat the package as the proposed operating package I intend to use, not as an authority source.

Do not execute Prompt 1-7, and do not research, build or test any Skill (Prompt 7 builds one). Do not modify any file or repository. Do not create the Phase 5 tag. Do not perform substantive engine, learning, design, web, GitHub, or open-source investigation. Do not rewrite the package silently.

Check the package for process-level flaws that could materially compromise correct execution: authority leakage, premature commitment, information loss, missing preconditions, canonical inconsistencies, unsafe Step 4 scope, broken M1 traceability, contradictions between the prompts, and contradictions between the package and the current 07/Execution Plan. Check every place where M1, M2, the no-change rule, acceptance order, Step 4 authority, Prompt 5 preparation-only status, the Prompt 7 / Design Exploration Skill boundary, and the Return Path are defined or consumed. (M1 = the ledger identifier and traceability model; M2 = the Step 4 design-scope definition and its four limits as repeated across the Charter, Prompt 2, the Prompt 5 Briefing and Section 13.5.)

Because this review is before Prompt 1, distinguish expected future outputs such as TAG/SHA from real missing prerequisites. The absent tag is not a problem at this review stage; Prompt 1 is what will establish the fixed snapshot after this review is cleared.

For every issue, classify it exactly as either MUST CHANGE BEFORE ANY DETOUR ACTION or CAN REMAIN OPEN. Then give an overall GO or NO-GO. Cite the exact section/heading in the package and the relevant canonical document section when applicable. Explain the concrete consequence.

Do not decide the outcome of Steps 1-4. Do not make technical, learning, or design recommendations. This is a package/process review only.

At the end, stop. I will decide whether to adopt any correction and whether to proceed.

A GO from Opus does not itself authorize execution. Karim explicitly decides whether to proceed. If Karim adopts a correction to this package, the corrected package is the new working version and the review findings should be considered closed only to the extent of that correction. If a correction materially changes the package, re-review the affected package before any detour action.

3. Detour Charter v1.8

The complete Charter. The same text, word for word, is embedded at the top of Prompt 4 and Prompt 5. It lives inside prompts, not in a repository file.

text
DETOUR CHARTER v1.8

PURPOSE
Between Phase 5 and Phase 6, audit what Phases 1-5 built and, only where the
evidence justifies it, strengthen it, so Phase 6 multiplies strength, not
weakness. Four separate steps: engine, learning, freeze, design. Results are
pasted forward manually.

GOVERNING QUESTION
What, if not discovered now, will be expensive to fix after Phase 6?

PRINCIPLES
- Outcomes are never predetermined. "Keep as is" and "no change" are valid.
- A step may think beyond its own domain. It may state REQUIREMENTS for other
  steps (what must be true or exposed for them to do their job) and surface
  CANDIDATES (ideas, options, hypotheses that arise from its findings), each
  labeled non-binding and naming the step that would evaluate it. It never
  recommends or decides another step's outcome, and never plans or executes it.
- Design comes last and expresses frozen decisions; it does not invent.
- Existing decisions in 07 change only by the owner (governance, D29). A step
  that finds a case against one records it as an open item, never a decision.
- Lens, not conclusion: honesty with the learner. The learner can always tell
  what is verified Amadeus behavior, a DEIXEN training message, a hint, an
  attempt, feedback, progress, mastery, or system state. A step may find no
  issue here.
- Nothing is created in any repo, except what AUTHORITY allows Step 4. This
  charter lives inside prompts, not a file. Outputs are chat replies unless the
  step's prompt says otherwise.

AUTHORITY
- Steps 1 and 2 recommend within their own domain. Step 3 proposes the Freeze
  Package. Step 4 improves and verifies the design inside the scope below.
  Nothing produced by a step binds until the project owner explicitly accepts
  it. The accepted Freeze Package binds Step 4 and Phase 6. Its Freeze, design
  scope and landing times are then recorded in 07 as a decision by the owner;
  Step 4 is prepared and run only after that record exists.
- Steps 1, 2 and 3 modify nothing: no code, documents or decisions.
- Step 4, only after the Freeze Package is accepted and recorded, may implement
  design changes inside the design scope that package defines.
  Design scope = how existing engine and learning outputs are presented:
  layout, hierarchy, typography, color and semantic-state rendering (styling
  only), interaction patterns, Terminal presentation (styling and container
  only), and interface copy = text of the interface itself (navigation,
  controls, headings, empty and system states) that neither teaches nor
  carries Amadeus behavior.
  Limits that always apply:
  (1) engine output is rendered exactly as received: no reflow, trimming,
  re-alignment, truncation or rewording;
  (2) what the engine receives, and what counts as an attempt, hint, reveal or
  mastery, is unchanged;
  (3) when, whether and how much learning support appears (hints, Coach, Ghost
  Mode, Speed Drills, Scenarios, Assessment) is learning logic, not
  interaction design;
  (4) any text that teaches, instructs, hints, explains, assesses or gives
  feedback is learning content, not interface copy; if unsure, it is learning
  content.
  Excluded: engine behavior, learning logic and content, the wording of
  verified Amadeus output and training messages (how they are styled is
  semantic-state rendering, inside the scope), frozen files, governing
  documents and decisions.
  Step 4 may create a new file only if the recorded design scope explicitly
  names that file; otherwise it edits existing files only.
  The Freeze Package sets the exact scope inside this definition; only an
  explicit owner decision can widen it.
- Step 4 works in isolation and reversibly (for example a separate branch, per
  CLAUDE.md). Its changes are proposals in code form: they join the project
  only when the owner accepts the Closing Report.
- Anything outside a step's authority is never done silently: it goes through
  the RETURN PATH. All other accepted changes (engine, learning, documents) are
  implemented as separate tasks started by the owner through the project's
  normal pipeline, on the schedule the Freeze sets.

GAP TEST (deficiencies in DEIXEN)
A gap only if it (a) multiplies with Phase 6, (b) prevents actual learning, or
(c) contradicts a verified fact or frozen decision. Otherwise: deferrable
improvement. Opportunities (improvements that fix no deficiency, e.g. external
work saved, or a material gain in learning or in what Phase 6 inherits) are
judged by the step's own materiality definition and still get a ledger row.

EVIDENCE
Observed (seen in real code/docs, not README claims) / Inferred / Judgment
(labeled). A step's own classifications apply in addition.

LEARNER-BENEFIT TEST (learning-facing recommendations)
Which moment in the learner journey, what changes in learning, how we would
know, at what cost.

SHARED JOURNEY
AN -> FXP, plus two deviations: a wrong command, and a returning learner after
a break. Trace as far as the snapshot reaches; where it stops is itself a
finding.

DELIVERY
The full report may follow the step's own structure. It ends with a HANDOFF
BLOCK, the only part pasted forward. The block must be self-contained: a reader
with only this charter and the block can act on it, so claims, evidence
pointers and reasoning are written in it, never "see the report above".
In this order:
Summary (simple Egyptian Arabic, max 5 lines) / Inputs received (each by ID:
used, rejected with a reason, or passed on unchanged; none dropped silently) /
Preserve list / Ledger rows / Requirements for later steps (each names its
target step) / Open items + what would change my mind / Coverage (examined,
including how far the shared journey was traced; deliberately not examined,
with a reason) / Exit check.

Identifiers. Every finding, requirement, candidate, preserved item and open
item is ONE ledger row with its own ID. IDs use the producing step's prefix and
a sequential number: S1-01, S1-02, S2-01, S2-02, S3-01, S4-01. A later step
never renumbers or reuses an earlier step's IDs, and never assigns a new ID to
an earlier step's item merely because it discusses it. The sections Preserve
list, Requirements for later steps and Open items are indexes of existing
ledger rows only; they never introduce an item that is not a row. No second
identifier system exists.
Ledger row: ID | type (gap, opportunity, risk, doc-code conflict, strength, open-item,
requirement, candidate) | claim (one plain sentence) | evidence: level + pointer |
journey point and learner-facing state, if any | Phase 6 impact | status
(confirmed, preserve, open, deferred, rejected) | relates to (IDs), if any.
A candidate is its own row, explicitly labeled non-binding, and names the step
that would evaluate it. A requirement is its own row and names its target step.
A preserved item is its own row (normally type strength, status preserve). An open item is its own row (type open-item when it is an unresolved item without a more specific substantive type; otherwise use the most specific substantive type and status open).
Locked decisions in the Freeze use IDs F-01, F-02, F-03 and so on; each cites
the source ledger row IDs from which it was derived.

RETURN PATH
Before the Freeze, shortfalls travel forward as requirements to Step 3. After
the Freeze (Step 4): if the design needs something outside its authority or
something the Freeze lacks, write a change request (must pass the gap test),
mark the affected item blocked, and do not fake or work around it. Continue
only with items that do not depend on it; if none can continue, stop. Owner
decides. One round, affected item only.

EXIT CONDITION
Every in-scope item has a final status; preserve list and requirements for the
next step written; open items named. (Or a precondition failure reported as the
step's prompt requires.)

CLOSING
Step 4 ends the detour with a Detour Closing Report, which is also its HANDOFF
BLOCK. It is built from the Freeze Package and Step 4's own results: readiness
statement for Phase 6, frozen decisions, design changes made and verified (with
their branch/commit references and the scope-audit result against the recorded
design scope), other accepted changes by landing time, preserved items,
coverage ledger, and up to 3 likeliest unverified risks to Phase 6, or none
identified. It is traceable: each decision cites its source row IDs, each
design change cites the F-ID or requirement row it serves, each verification
result cites what it verified.

FREEZE = locked decisions + explicitly listed open items + how to change them.
FREEZE PACKAGE = Step 3's HANDOFF BLOCK. It carries the Freeze and everything
Step 4 and the Closing Report need from Steps 1-3 that the Freeze alone does
not: the design scope (stated in full: the definition, the four limits, the
exclusions and any file it names); when each accepted change must land (before
Step 4 / before Phase 6 / with Phase 6 / deferred); the consolidated ledger
(open and design-relevant rows in full, closed rows one line each); the
requirements and candidates Step 4 must evaluate, in full; the preserve list;
and the cumulative coverage of Steps 1-3. Each locked decision (F-ID) cites the
ledger row IDs it came from.
Step 4's input is the accepted Freeze Package. Its Freeze, design scope and
landing times are already recorded in 07: the package is the working copy and
07 is the canonical copy of those parts.
4. Prompt Roles, Purpose, Effort and Attachments

Terms: a preparation session produces a prompt and nothing else; an execution session carries out a prompt. "Fresh" means a new session that has not been used for any other task of this package.

Prompt 0 — Phase 5 practice-run check (before the tag; not a detour step)
Purpose: find out whether the practice booking is ever lost where the Build Spec says the run continues (Karim's learner test, 07 D67), so that the fixed snapshot does not carry a defect nobody looked at.
Where it sits: after Karim decides to proceed with the package; before Prompt 1. It belongs to Phase 5, not to the detour.
Type: execution, read-only (a throwaway test file deleted afterwards is allowed; nothing is committed).
Model / Effort: Claude Code, Opus 5.5, High — it must read the run rules exactly and try every path.
Attachments / input: a Claude Code session on deixen-app (CLAUDE.md and ../DEIXEN-KNOWLEDGE available). No fill-ins.
Prohibited: fixing anything; committing; tagging.
After it: if it reports (a) a defect, the fix goes through the usual Phase 5 loop (prompt -> report -> check), Karim re-tests that part, and Prompt 1 then tags the fixed commit. If (b) or (c), Prompt 1 follows; (b) becomes an input to Step 2 with the learner-test record.
Prompt 1 — Phase 5 tag + SHA verification
Purpose: obtain and verify the final Phase 5 tag and its full commit SHA, so the detour examines one fixed snapshot.
Where it sits: the first operational task after the owner has reviewed the complete package with Opus 5.5 and decided to proceed; before Prompt 2. It is not a detour step.
Type: execution (a repository action limited to creating the tag locally; deixen-app has no remote, so nothing is pushed).
Effort: Low.
Attachments / input: a Claude Code session on the deixen-app repository (CLAUDE.md available). No fill-ins. Its reply supplies [TAG] and [SHA] for Prompts 2 and 4.
Clean session: a single stand-alone task; it needs only the repository.
Prohibited: modifying any code or file; creating a tag unless every check passes; adding a remote or pushing anything; doing anything else.
Prompt 2 — Record the detour governance decision in 07
Purpose: record the detour as one decision by Karim in 07_DEIXEN_Canonical_Decisions_and_Current_State.md.
Where it sits: after the owner reviews Prompt 1's tag/SHA result; before Prompt 3.
Type: execution; the only mutation is 07.
Effort: Medium.
Attachments / input: Prompt 2 with [TAG] and [SHA] filled from Prompt 1's reply; 07; DEIXEN_Execution_Plan.md; the files its impact check reads (file 00 §A10 dependency lines, Operating Constitution §15).
Clean session: no special requirement beyond access to the documents; a fresh session is fine.
Prohibited: modifying any file other than 07; applying the updates its impact check finds (it only reports them); recording the decision "by delegation"; silently choosing when it judges something wrong.
Prompt 3 — Update DEIXEN_Execution_Plan.md after Decision N
Purpose: prepare the Execution Plan updates (and only what the decision requires elsewhere) after the decision is recorded.
Where it sits: after the owner reviews Prompt 2's result; after the package-level Pre-Execution Pre-flight Review has already been cleared; before Step 1.
Type: execution; mutations are limited to DEIXEN_Execution_Plan.md and files flagged by Prompt 2's impact check.
Effort: Medium.
Attachments / input: Prompt 3 with [N] (the decision number) and [DATE] (Phase 5 closure date) filled; the updated 07; DEIXEN_Execution_Plan.md; the other files flagged by the impact check.
Clean session: no special requirement; it must be able to see Prompt 2's impact-check reply.
Prohibited: rewriting, reordering or "improving" anything else; changing any existing decision, role or gate; creating a new file; inventing a gate (it writes "none stated" where the decision states none).
Prompt 4 — Step 1: External Engine / Open-Source Investigation
Purpose: an independent engineering investigation of the engine at the fixed snapshot and of the open-source ecosystem, ending in a Technical Recommendation and a self-contained HANDOFF BLOCK.
Where it sits: Step 1 of the detour; after Prompt 1-3 have completed and the owner has already cleared the package-level Pre-Execution Review.
Type: execution (analysis and consultation only).
Effort: Max.
Attachments / input: Prompt 4 with [TAG] and [SHA] filled, in ONE message, with: read-only access to the deixen-app folder on Karim's computer (link the computer and connect the folder; the repository has no GitHub remote), at the tagged commit; the updated DEIXEN_Execution_Plan.md and 07; the reference documents named in the prompt (DEIXEN_Amadeus_Verified_Reference.md, DEIXEN_Slice_Build_Spec.md, CLAUDE.md, and as needed DEIXEN_Operating_Constitution.md, 03, 05, 08). Prompt 5 is NOT included. It needs web and GitHub access (its precondition).
Clean session: required.
Prohibited: modifying anything; creating or modifying any file in any repository; copying code, committing, pushing or opening a PR; performing, deciding or planning Steps 2-4; entering any finding into DEIXEN_Amadeus_Verified_Reference.md; deciding adoption of external code; acting as a gate.
Prompt 5 — Detour Briefing (persistent orientation / prompt-writing layer)
Purpose: give Opus the mental model of the whole detour so it can write the prompt for ONE of Steps 2, 3 or 4 correctly.
Where it sits: before each of Step 2, Step 3 and Step 4, after the package-level pre-execution review has been cleared. It is never before or during Step 1. It is not a step.
Type: preparation only. It produces no findings, makes no decisions and is never an execution step.
Effort: High.
Attachments / input (fresh session each time): Prompt 5 (it embeds the Charter); the current DEIXEN_Execution_Plan.md and 07; and the input for that step: for Step 2, the Step 1 HANDOFF BLOCK and Karim's Phase 5 learner-test record (07 Decision 67 and the learner-test document it names); for Step 3, the Step 1 and Step 2 HANDOFF BLOCKS; for Step 4, the accepted Freeze Package (already recorded in 07) and only that from earlier steps, plus the accepted Design Exploration Skill artifact as a tooling input; then the request line "Write the prompt for Step N."
Clean session: required (fresh session each time).
Prohibited: executing any step; creating or modifying any file; overriding 07 or the governing Charter; silently changing the Charter; preparing Step 4 before the Freeze record exists in 07.
Prompt 6 — Record the accepted Freeze in 07
Purpose: record, verbatim, the accepted Freeze, the design scope and the landing times in 07 as a decision by Karim.
Where it sits: after Karim accepts (or modifies and accepts) the Freeze Package; before Step 4 is prepared.
Type: execution; the only mutation is 07.
Effort: Medium.
Attachments / input: Prompt 6 with [DATE] (acceptance date), [N] (the detour decision number) and the pasted Freeze section, design scope and landing times; 07; DEIXEN_Execution_Plan.md.
Clean session: no special requirement beyond access to the documents.
Prohibited: paraphrasing, merging, reordering, softening or dropping any item; resolving a conflict silently; recording the rest of the package (ledger, coverage, requirements, candidates, preserve list); modifying any other file; applying the updates its impact check finds.
Prompt 7 — Build the DEIXEN Design Exploration Skill (Auxiliary Tooling Preparation — not a Detour Step)
Purpose: research, design, build, and structurally test a reusable Agent Skill specialized for DEIXEN visual-identity and creative-direction exploration. It is a tooling task only; it does not design DEIXEN and does not run an exploration cycle.
Where it sits: after the accepted Freeze has been recorded in 07 and after any Freeze-scheduled work that must land before Step 4 is complete; before the Prompt 5 preparation session that writes the Step 4 prompt.
Type: auxiliary tooling preparation, not a detour step. It may create or update only the Skill artifact in an isolated skill workspace; it does not modify the DEIXEN application repository, 07, the Execution Plan, the existing design system, or any other canonical DEIXEN document.
Effort: Max.
Attachments / input: Prompt 7; the current 07 including the accepted Freeze, design scope and landing times; the current DEIXEN_Execution_Plan.md; the DEIXEN product/design sources needed by the prompt; and access to the target Agent Skill / Claude Design environment when available. Web access is required by the prompt for current verification and research.
Clean session: required. Use a fresh Opus 5.5 session.
Authority: the Skill is a tool, not a source of authority. It cannot change the accepted Freeze, widen Step 4 scope, alter canonical decisions, or execute Step 4.
Prohibited: applying the new Skill to DEIXEN; producing or selecting a DEIXEN visual direction; modifying the DEIXEN product or canonical documents; creating a new detour step; changing Step 4 authority; silently installing the Skill into a DEIXEN repository. If the available environment requires such a mutation to install the Skill, stop and provide the complete install-ready Skill files instead.
5A. Prompt 0 — COMPLETE

Claude Code, Opus 5.5, Effort: High. Execute after Karim decides to proceed with the package and before Prompt 1. No fill-ins.

text
One specific task: find out whether the practice booking is lost when it should not be. Do not fix, commit, delete or tag anything.

My learner test (07 Decision 67) found this: while practising, after entering one command after another without going back to the Flight Deck, the booking started again from empty and my work was gone. I cannot say exactly what I clicked.

Build Spec §7A item 1 and §7B item 12 say when a practice run continues and when a new one starts: a run lives for the app load; leaving the Terminal and coming back shows the same run; a lesson's practice button or Ghost Mode's "Practise this yourself" starts a new run only when the current task is complete or the lesson's skill already has a valid entry in the run; Reset task starts again; a reload starts empty (the booking is not stored); after an assessment or the scenario has ended, returning to practice starts a new run.

1. Read those rules first. Then, on the built app (the same build the browser tests use), try every way a learner can move while practising: entries typed one after another; Learning -> the next lesson -> its practice button, in order and out of order (including a lesson whose step is already done); Ghost Mode -> "Practise this yourself"; the Flight Deck action; the Terminal area link; the escalation offer's lesson link and back; the language switch; the phone menu and the DEIXEN drawer; a hint request; Reset task; a reload. The browser-test helpers may be used; a throwaway test file deleted afterwards is fine.
2. For each path report: the booking before and after, and whether a new run started.
3. Classify the result: (a) a defect: the booking was lost where the spec says the run continues; (b) as the spec says, but a learner cannot tell why it started again (for example a practice button that starts a new run without saying so); (c) no loss found on any path.
4. If (a): do not fix it. Give the exact steps, the code path, and the test that would catch it, then stop.
5. At the end, confirm that git status is clean and HEAD is unchanged.

In your reply give me the table of paths, the classification, and nothing else.
5. Prompt 1 — COMPLETE

Claude Code, Effort: Low. Execute only after the package-level Pre-Execution Review has received a GO and Karim has decided to proceed. No fill-ins.

text
One specific task: create the final tag for Phase 5 in the deixen-app repo. Do not modify any code or file.

1. Run git status and record the full SHA of HEAD (git rev-parse HEAD). Confirm the working tree is clean and HEAD is on main. This repository has no remote: do not add one and do not push. If there are uncommitted changes, stop and tell me. Do not create a tag.

2. Run the verification steps written in CLAUDE.md (including the verification loop it references from 08 §26) and report the results. If any of them fail, stop and tell me. Do not create a tag.

3. After the verification, run git status again and check HEAD again. Confirm HEAD is still the same SHA you recorded in step 1 and that the working tree is still clean (git status shows no modified or new files left by the verification). If anything changed, stop and tell me exactly what changed. Do not create a tag.

4. Show me the current branch, the last 5 commits, and the existing tags (so we follow the same naming pattern, such as step-2b-engine and step-3-bridge). The build I tested as a learner is main at 3fdb342 (tag step-7-pass, 07 D65), unless a fix found by Prompt 0 has since been merged and re-tested by me (then it is that merge commit, named in 07). If HEAD is neither, stop and ask me.

5. If everything above is fine: create an annotated tag named phase-5-final on the exact SHA you recorded in step 1 (or the name that best fits the existing naming pattern, and tell me which name you chose), locally. Do not push: the repository has no remote.

6. At the end, give me exactly: the tag name, the full commit SHA, the commit date, and the output of git show --no-patch for the tag.

Do nothing else.
6. Prompt 2 — COMPLETE v1.8

Opus, Effort: Medium. Execute only after the package-level review has been cleared and Prompt 1 has returned a valid tag/SHA. Fill [TAG] and [SHA] from Prompt 1's reply. Updated for consistency with Charter v1.8 (M1 identifiers, M2 Step 4 scope).

text
One specific task: record a new decision in 07_DEIXEN_Canonical_Decisions_and_Current_State.md.

The decision (by meaning; write it in the same style and format as the previous decisions in the file. The one exception is the design-scope definition, the four limits, the exclusions and the new-file rule in the Step 4 bullet below: record those word for word, and show me any wording change the file's format forces):

- After Phase 5 is closed and before Phase 6 (Expansion) starts, a deliberate four-step detour is inserted into DEIXEN_Execution_Plan.md. It is intentional, approved by Karim, short, and exists so that Phase 6 starts on better-informed ground:
  1) External Engine / Open-Source Investigation -> Technical Recommendation
  2) Learning Design + Learning Experience Review -> Learning Decision
  3) Synthesize & Freeze Decisions (Engine + Learning + Product constraints)
  4) Design Improvement Round (UX / UI / learning surfaces / Terminal experience) -> Design Verification
  Then Phase 6 (Expansion).
- Each step is started separately by Karim and stops after its own deliverable. A step may state requirements it needs from other steps and surface labeled, non-binding candidates for them, but it never recommends, decides, or plans the execution of another step's outcome.
- Authority: steps 1 and 2 recommend within their own domain; step 3 proposes the Freeze Package; step 4 improves and verifies the design inside the scope below. Nothing produced by a step binds until Karim explicitly accepts it. Steps 1, 2 and 3 modify nothing (no code, documents or decisions).
- The Freeze Package is step 3's handoff. It carries the Freeze (locked decisions + explicitly listed open items + the procedure for changing them) and everything step 4 and the closing report need from steps 1-3: the design scope (stated in full: the definition, the four limits, the exclusions and any file it names), when each accepted change must land (before step 4 / before Phase 6 / with Phase 6 / deferred), the consolidated ledger, the requirements and candidates step 4 must evaluate, the preserve list, and the cumulative coverage. Items are tracked as ledger rows with one ID each (S1-01, S2-01, S3-01, ...), never renumbered by a later step; locked decisions are identified F-01, F-02, ... and each cites the ledger row IDs it came from. The accepted Freeze Package is the only input step 4 takes from the earlier steps, and it binds step 4 and Phase 6. Its Freeze, design scope and landing times are then recorded in 07 as a decision by Karim, and step 4 is prepared and run only after that record exists; the package is the working copy and 07 is the canonical copy of those parts.
- Step 4, only after the Freeze Package is accepted and recorded, may implement design changes inside the design scope defined by that package. Design scope = how existing engine and learning outputs are presented: layout, hierarchy, typography, color and semantic-state rendering (styling only), interaction patterns, Terminal presentation (styling and container only), and interface copy = text of the interface itself (navigation, controls, headings, empty and system states) that neither teaches nor carries Amadeus behavior. Limits that always apply: (1) engine output is rendered exactly as received: no reflow, trimming, re-alignment, truncation or rewording; (2) what the engine receives, and what counts as an attempt, hint, reveal or mastery, is unchanged; (3) when, whether and how much learning support appears (hints, Coach, Ghost Mode, Speed Drills, Scenarios, Assessment) is learning logic, not interaction design; (4) any text that teaches, instructs, hints, explains, assesses or gives feedback is learning content, not interface copy; if unsure, it is learning content. Excluded: engine behavior, learning logic and content, the wording of verified Amadeus output and training messages (how they are styled is semantic-state rendering, inside the scope), frozen files, governing documents and decisions. Step 4 may create a new file only if the recorded design scope explicitly names that file; otherwise it edits existing files only. Step 4 works in isolation and reversibly (for example a separate branch), then verifies the resulting state; "no material design change" is a valid result. Its changes are proposals in code form and join the project only when Karim accepts the Detour Closing Report. Anything outside its authority goes through the return path. All other accepted changes (engine, learning, documents) are implemented as separate tasks started by Karim through the project's normal pipeline, on the schedule the Freeze sets.
- The four steps run under a shared Detour Charter (v1.8), embedded as a block at the top of each step's prompt. It is not a repository file.
- Return path: after the Freeze, if step 4 needs something outside its authority or something the Freeze lacks, it writes a change request, marks the affected item blocked, does not fake or work around it, and continues only with items that do not depend on it (or stops if none can continue). Karim decides. One round, affected item only.
- Step 4 ends the whole detour with a Detour Closing Report built from the Freeze Package and step 4's own results: a readiness statement for Phase 6, the frozen decisions, the design changes made and verified, the other accepted changes (grouped by when they must land) and what was deliberately preserved, and a coverage ledger (what was examined, what came out, what was deliberately left out and why). It is traceable from evidence to decision to change to verification. Karim reviews it, accepts or rejects the design changes, schedules the remaining implementation tasks, and starts Phase 6 himself.
- Step 1 is an independent investigation run by Opus 5.5 in a clean session. It asks whether any open-source implementation, architectural idea, dataset, or evidence deserves to affect the engine or the way it is expanded in Phase 6. It also includes a short "Design-facing requirements" section describing what the engine, progress system, and messaging layer would need to expose so that a later UI can present learner feedback honestly. That section is a secondary lens only and is not a selection criterion.
- Target code for step 1: tag [TAG] at commit [SHA] in the deixen-app repo.
- Step 1 output is delivered in the chat reply only, with no new files and no modification to any repo or document.
- Step 1 result is an advisory recommendation, not a gate, and is not treated as a formal independent review.
- Any Amadeus behavior that surfaces from step 1 does not enter DEIXEN_Amadeus_Verified_Reference.md; it goes through the verify -> spec -> build -> test path.
- The decision to adopt any external code is reserved to Karim (money/legal, D29).

What I need:
1. Read the file and find the last decision number and the format used. Record this as ONE decision under a new sequential number in the same format. Because it changes the work sequence of the governing Execution Plan, write it as a decision by Karim (governance change reserved under D29), not "by delegation". If you judge that this is wrong, say why instead of silently choosing.
2. If you can edit the file directly, do it. If not, give me the decision text ready to copy and paste, and state the exact place in the file where it goes.
3. Do not modify any other file. Run an impact check (Constitution §15, using the dependency lines in file 00 §A10) and tell me which files need an update because of this decision. Tell me only; do not apply any update.
4. Before doing item 1, check whether the closure of Phase 5 (Karim's learner test of the slice, 07 D29 item 5) is recorded in 07. If it is not, stop before editing anything and tell me; do not record the detour decision until I tell you how the closure is to be recorded.

In your reply give me: the decision number, the final text, the list of files that need updating, and any warning.
7. Prompt 3 — COMPLETE

Opus, Effort: Medium. Execute only after the package-level review has been cleared and Karim has reviewed Prompt 2's result. Send after Prompt 2's result is reviewed and the decision is recorded. Fill [N] and [DATE]. Unchanged from the latest agreed text.

text
One specific task: prepare the updates that the new detour decision requires, based on the impact check you just reported. The decision is now recorded in 07 as Decision [N].

Scope, strictly:
1. DEIXEN_Execution_Plan.md:
   - In the §3 phases table, set Phase 5 to Done with the date [DATE] and insert the four detour steps between Phase 5 and Phase 6 with their outputs and gates, following the same table format. Take outputs and gates only from Decision [N]; if it states no gate for a step, write "none stated" instead of inventing one. Step 1 is advisory (not a gate); Step 3's output is a Freeze Package proposal that binds only after Karim's explicit acceptance, after which its Freeze, design scope and landing times are recorded in 07, and step 4 starts only after that record exists; Step 4's output is its verified design changes (isolated until accepted) plus the Detour Closing Report, which Karim accepts.
   - Update §7 Current Phase so it reflects that Phase 5 is closed and the detour is under way, referencing 07 Decision [N].
   - Add the Decision reference to the file's metadata where appropriate.
2. Any other file you flagged in the impact check (for example the dependency or status lines in 00_DEIXEN_Knowledge_Consolidation_Plan.md). Only what the decision actually requires.

Rules:
- Minimal edits. Do not rewrite, reorder, or "improve" anything else.
- Do not change any existing decision, role, or gate.
- Create no new file (Execution Plan §5).
- In the detour rows, add one line (no new section) saying the steps run under the shared Detour Charter embedded in each step's prompt (not a file).
- If you can edit the files directly, do it. If not, give me each change as: file, exact location, old text, new text, ready to copy and paste.

In your reply, list every file you changed or propose to change, and anything you noticed that looks stale or contradictory but that you did not touch.
8. Prompt 4 — COMPLETE v1.8

Opus, Effort: Max, fresh clean session, sent alone (Prompt 5 is not included). Fill [TAG] and [SHA]. The complete Charter v1.8 comes first, then the Step 1 task.

text
DETOUR CHARTER v1.8

PURPOSE
Between Phase 5 and Phase 6, audit what Phases 1-5 built and, only where the
evidence justifies it, strengthen it, so Phase 6 multiplies strength, not
weakness. Four separate steps: engine, learning, freeze, design. Results are
pasted forward manually.

GOVERNING QUESTION
What, if not discovered now, will be expensive to fix after Phase 6?

PRINCIPLES
- Outcomes are never predetermined. "Keep as is" and "no change" are valid.
- A step may think beyond its own domain. It may state REQUIREMENTS for other
  steps (what must be true or exposed for them to do their job) and surface
  CANDIDATES (ideas, options, hypotheses that arise from its findings), each
  labeled non-binding and naming the step that would evaluate it. It never
  recommends or decides another step's outcome, and never plans or executes it.
- Design comes last and expresses frozen decisions; it does not invent.
- Existing decisions in 07 change only by the owner (governance, D29). A step
  that finds a case against one records it as an open item, never a decision.
- Lens, not conclusion: honesty with the learner. The learner can always tell
  what is verified Amadeus behavior, a DEIXEN training message, a hint, an
  attempt, feedback, progress, mastery, or system state. A step may find no
  issue here.
- Nothing is created in any repo, except what AUTHORITY allows Step 4. This
  charter lives inside prompts, not a file. Outputs are chat replies unless the
  step's prompt says otherwise.

AUTHORITY
- Steps 1 and 2 recommend within their own domain. Step 3 proposes the Freeze
  Package. Step 4 improves and verifies the design inside the scope below.
  Nothing produced by a step binds until the project owner explicitly accepts
  it. The accepted Freeze Package binds Step 4 and Phase 6. Its Freeze, design
  scope and landing times are then recorded in 07 as a decision by the owner;
  Step 4 is prepared and run only after that record exists.
- Steps 1, 2 and 3 modify nothing: no code, documents or decisions.
- Step 4, only after the Freeze Package is accepted and recorded, may implement
  design changes inside the design scope that package defines.
  Design scope = how existing engine and learning outputs are presented:
  layout, hierarchy, typography, color and semantic-state rendering (styling
  only), interaction patterns, Terminal presentation (styling and container
  only), and interface copy = text of the interface itself (navigation,
  controls, headings, empty and system states) that neither teaches nor
  carries Amadeus behavior.
  Limits that always apply:
  (1) engine output is rendered exactly as received: no reflow, trimming,
  re-alignment, truncation or rewording;
  (2) what the engine receives, and what counts as an attempt, hint, reveal or
  mastery, is unchanged;
  (3) when, whether and how much learning support appears (hints, Coach, Ghost
  Mode, Speed Drills, Scenarios, Assessment) is learning logic, not
  interaction design;
  (4) any text that teaches, instructs, hints, explains, assesses or gives
  feedback is learning content, not interface copy; if unsure, it is learning
  content.
  Excluded: engine behavior, learning logic and content, the wording of
  verified Amadeus output and training messages (how they are styled is
  semantic-state rendering, inside the scope), frozen files, governing
  documents and decisions.
  Step 4 may create a new file only if the recorded design scope explicitly
  names that file; otherwise it edits existing files only.
  The Freeze Package sets the exact scope inside this definition; only an
  explicit owner decision can widen it.
- Step 4 works in isolation and reversibly (for example a separate branch, per
  CLAUDE.md). Its changes are proposals in code form: they join the project
  only when the owner accepts the Closing Report.
- Anything outside a step's authority is never done silently: it goes through
  the RETURN PATH. All other accepted changes (engine, learning, documents) are
  implemented as separate tasks started by the owner through the project's
  normal pipeline, on the schedule the Freeze sets.

GAP TEST (deficiencies in DEIXEN)
A gap only if it (a) multiplies with Phase 6, (b) prevents actual learning, or
(c) contradicts a verified fact or frozen decision. Otherwise: deferrable
improvement. Opportunities (improvements that fix no deficiency, e.g. external
work saved, or a material gain in learning or in what Phase 6 inherits) are
judged by the step's own materiality definition and still get a ledger row.

EVIDENCE
Observed (seen in real code/docs, not README claims) / Inferred / Judgment
(labeled). A step's own classifications apply in addition.

LEARNER-BENEFIT TEST (learning-facing recommendations)
Which moment in the learner journey, what changes in learning, how we would
know, at what cost.

SHARED JOURNEY
AN -> FXP, plus two deviations: a wrong command, and a returning learner after
a break. Trace as far as the snapshot reaches; where it stops is itself a
finding.

DELIVERY
The full report may follow the step's own structure. It ends with a HANDOFF
BLOCK, the only part pasted forward. The block must be self-contained: a reader
with only this charter and the block can act on it, so claims, evidence
pointers and reasoning are written in it, never "see the report above".
In this order:
Summary (simple Egyptian Arabic, max 5 lines) / Inputs received (each by ID:
used, rejected with a reason, or passed on unchanged; none dropped silently) /
Preserve list / Ledger rows / Requirements for later steps (each names its
target step) / Open items + what would change my mind / Coverage (examined,
including how far the shared journey was traced; deliberately not examined,
with a reason) / Exit check.

Identifiers. Every finding, requirement, candidate, preserved item and open
item is ONE ledger row with its own ID. IDs use the producing step's prefix and
a sequential number: S1-01, S1-02, S2-01, S2-02, S3-01, S4-01. A later step
never renumbers or reuses an earlier step's IDs, and never assigns a new ID to
an earlier step's item merely because it discusses it. The sections Preserve
list, Requirements for later steps and Open items are indexes of existing
ledger rows only; they never introduce an item that is not a row. No second
identifier system exists.
Ledger row: ID | type (gap, opportunity, risk, doc-code conflict, strength, open-item,
requirement, candidate) | claim (one plain sentence) | evidence: level + pointer |
journey point and learner-facing state, if any | Phase 6 impact | status
(confirmed, preserve, open, deferred, rejected) | relates to (IDs), if any.
A candidate is its own row, explicitly labeled non-binding, and names the step
that would evaluate it. A requirement is its own row and names its target step.
A preserved item is its own row (normally type strength, status preserve). An open item is its own row (type open-item when it is an unresolved item without a more specific substantive type; otherwise use the most specific substantive type and status open).
Locked decisions in the Freeze use IDs F-01, F-02, F-03 and so on; each cites
the source ledger row IDs from which it was derived.

RETURN PATH
Before the Freeze, shortfalls travel forward as requirements to Step 3. After
the Freeze (Step 4): if the design needs something outside its authority or
something the Freeze lacks, write a change request (must pass the gap test),
mark the affected item blocked, and do not fake or work around it. Continue
only with items that do not depend on it; if none can continue, stop. Owner
decides. One round, affected item only.

EXIT CONDITION
Every in-scope item has a final status; preserve list and requirements for the
next step written; open items named. (Or a precondition failure reported as the
step's prompt requires.)

CLOSING
Step 4 ends the detour with a Detour Closing Report, which is also its HANDOFF
BLOCK. It is built from the Freeze Package and Step 4's own results: readiness
statement for Phase 6, frozen decisions, design changes made and verified (with
their branch/commit references and the scope-audit result against the recorded
design scope), other accepted changes by landing time, preserved items,
coverage ledger, and up to 3 likeliest unverified risks to Phase 6, or none
identified. It is traceable: each decision cites its source row IDs, each
design change cites the F-ID or requirement row it serves, each verification
result cites what it verified.

FREEZE = locked decisions + explicitly listed open items + how to change them.
FREEZE PACKAGE = Step 3's HANDOFF BLOCK. It carries the Freeze and everything
Step 4 and the Closing Report need from Steps 1-3 that the Freeze alone does
not: the design scope (stated in full: the definition, the four limits, the
exclusions and any file it names); when each accepted change must land (before
Step 4 / before Phase 6 / with Phase 6 / deferred); the consolidated ledger
(open and design-relevant rows in full, closed rows one line each); the
requirements and candidates Step 4 must evaluate, in full; the preserve list;
and the cumulative coverage of Steps 1-3. Each locked decision (F-ID) cites the
ledger row IDs it came from.
Step 4's input is the accepted Freeze Package. Its Freeze, design scope and
landing times are already recorded in 07: the package is the working copy and
07 is the canonical copy of those parts.

=====================================================================

External Engine / Open-Source Investigation

PLAN CONTEXT (read this first)

This task is Step 1 of a deliberate detour, approved by the project owner, inserted between the formal closure of Phase 5 and the start of Phase 6 (Expansion) in DEIXEN_Execution_Plan.md. The detour is intentional and does not violate the plan. It is short, and it exists so that Phase 6 starts on better-informed ground.

Detour sequence:
1) External Engine / Open-Source Investigation -> Technical Recommendation     <- YOUR TASK NOW
2) Learning Design + Learning Experience Review -> Learning Decision
3) Synthesize & Freeze Decisions (Engine + Learning + Product constraints)
4) Design Improvement Round (UX / UI / learning surfaces / Terminal experience) -> Design Verification
-> then Phase 6 (Expansion)

How to treat this sequence:
- Only Step 1 is your task. Steps 2-4 are CONTEXT ONLY. Do not perform them, decide them, or plan them. You may state requirements they will need from the engine and surface labeled candidates for them, as the charter defines; you never recommend or decide their outcomes.
- Everything in the task below still applies as written: it is analysis and consultation only, not a formal review, not a gate, and nothing may be modified.
- Why you are seeing the later steps: your Technical Recommendation will feed the Freeze in Step 3, and the design round in Step 4 must express frozen engine and learning decisions honestly instead of faking them. That is the only reason it is useful for you to know what comes after you.

ONE ADDITIONAL DELIVERABLE (secondary lens, not a selection criterion)
Do not let this change which external projects you examine or how you judge them. Judge everything by the criteria in the task. After your Decision, add a short final section titled "Design-facing requirements" (keep it under about 300 words): what the engine, progress system, and messaging layer would need to be able to expose so that a later UI can present learner feedback honestly, based on what you actually found in the DEIXEN code. Examples of the kind of thing (verify each against the real code, do not assume any exists): a per-behavior verification level, the origin or authority of each message (real Amadeus behavior vs DEIXEN training message), hint and reveal counts, attempt history, sequence data behind mastery. For each item state:
- whether the code already exposes it, partially exposes it, or does not
- whether it could be added additively without touching frozen engine files
- what a UI would otherwise be forced to fake
- which learner-facing state it serves (verified behavior / training message / hint / attempt / feedback / progress / mastery / system state); if it fits none, say so
Do not design any UI or produce visuals. Ideas that arise naturally from your findings belong in the ledger as labeled candidates (charter), not in this section.

STOP CONDITION
After delivering the report (including the Design-facing requirements section and the Handoff Block), stop. Do not start Step 2, do not draft learning or design proposals (labeled candidates in the ledger are allowed, as the charter defines), and do not continue the detour on your own. The project owner will start each step separately.

---

I want you to run an independent engineering investigation of the current engine in DEIXEN, to determine whether any external implementations, architectural ideas, data, or evidence deserve to affect the engine or the way it is expanded in Phase 6.

This task is analysis and consultation only. It is not a formal review under the Execution Plan and it is not a gate.

Do not modify any file, fix bugs, refactor, migrate, copy code, commit, push, open a PR, or create or modify any file inside any repository.

Deliver the result in your reply only.

---

1. Context and goal

While DEIXEN was being built, someone told me that instead of building our own simulator of Amadeus/GDS behavior, it might be better to find open-source code close to the idea and then use it or build on it.

I do not assume this suggestion is right, and I do not assume it is wrong.

I want you to verify the idea from scratch, then examine the open-source ecosystem yourself, then compare what you find with the current DEIXEN.

DEIXEN

DEIXEN is an educational platform that trains a beginner on Amadeus Basic and then Advanced, at the level targeted by the Saudi/Gulf job market.

DEIXEN is not an attempt to rebuild Amadeus in full, and it is not a complete GDS.

The success criterion is educational and behavioral accuracy and provability within the scope DEIXEN has defined, not the number of commands or the completeness of all GDS functions.

Terminal behavior must match real Amadeus where it has been verified according to DEIXEN's Verification Standard, and Claude Code does not assume or invent Amadeus behavior.

Project state at the time of this task

When this investigation is run, Phase 5 has been formally closed after the project owner tested the slice as a learner, and the next phase is Phase 6 (Expansion), where every chunk goes through verify -> spec -> build -> test.

The code to investigate is a fixed, specific snapshot:

tag [TAG] at commit [SHA] in the deixen-app repo.

Analyze this snapshot specifically, not a later version.

The main references for understanding DEIXEN's goal and constraints (documentation is in the DEIXEN-KNOWLEDGE repo and/or the project files; CLAUDE.md is in deixen-app):

- DEIXEN_Execution_Plan.md
- 07_DEIXEN_Canonical_Decisions_and_Current_State.md
- DEIXEN_Amadeus_Verified_Reference.md
- DEIXEN_Slice_Build_Spec.md
- CLAUDE.md

Additional context, to read as needed:

- DEIXEN_Operating_Constitution.md
- 03_DEIXEN_Canonical_Product_and_Architecture.md
- 05_DEIXEN_Canonical_Amadeus_Engine_Reference.md
- 08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process.md

Use these documents to understand scope, authority, and standards, but when judging the current implementation, rely on the actual code in the target snapshot.

If you find a conflict between the documentation and the implementation, state it clearly and do not assume the documentation describes the code accurately.

---

2. Precondition

Before drawing any conclusion, confirm that you can actually:

1. Read the DEIXEN code in the specified snapshot (deixen-app). The repository has no remote: read it through Karim's connected folder, read-only, and confirm from .git/refs/tags and .git/HEAD that [TAG] and HEAD both point to [SHA]. If HEAD has moved past [SHA], stop and tell me.
2. Read the reference documents listed above.
3. Browse the web, GitHub, and public sources.
4. Read the actual code of the external projects you choose to examine.

If any of these is unavailable, tell me in your first reply and stop. Do not compensate with memory or with a README alone.

---

3. Understand DEIXEN first

Before searching externally, examine DEIXEN itself.

Where possible, trace the real execution paths from command input to the final result. Use the charter's shared journey (AN -> FXP, plus a wrong command and a returning learner after a break) as one of the traced paths. If the snapshot does not reach FXP, trace as far as it goes and state where it stops.

Determine the current architecture from the code itself, including what actually exists in: command parsing and dispatch, domain logic, state, PNR, and state transitions, validation, availability, inventory, and sell, SSR and seat maps, pricing, fare rules, and ticketing, queues, persistence, error handling, output/result representation, rendering/UI boundaries, fixtures, datasets, and tests.

Do not assume an abstraction, layer, or pattern exists just because the documentation mentions it.

Distinguish what is actually implemented from what is only a specification or intended architecture.

---

4. Examine the open-source ecosystem yourself

Search for relevant public projects yourself.

Do not rely on a predefined list, and do not assume any particular project is the best point of comparison.

Explore, as you see fit, areas such as: Amadeus simulators, Cryptic simulators, and console emulators; GDS/CRS simulators; airline reservation engines; PNR and inventory systems; airline training simulators; terminal-based reservation systems; educational reservation systems; and relevant datasets or fixtures.

These are examples of the search space, not mandatory boundaries.

Decide yourself what deserves examination and what does not, and why.

Someone mentioned the GitHub user RaheesAhmed as having an Amadeus simulator project. Use it as a discovery lead only, not as an assumed reference. Find the exact repository yourself.

A note on other GDS (Sabre / Galileo / Travelport):
Start with Amadeus-specific projects. Move to other GDS only if the Amadeus projects are limited or weak.
Treat anything from them as an architectural pattern, data-model idea, or test idea only.
Do not treat it as evidence of Amadeus behavior, do not count their agreement as cross-project evidence for Amadeus behavior, and do not import syntax or output format from them.

Do not stop at the first results. Follow links, forks, and alternatives.

Stop searching when the last several distinct searches or leads surfaced no new relevant project, architectural idea, dataset, or test pattern (saturation). In the report, state the search trail briefly (leads followed, candidates found, what was excluded and why) and a saturation statement. If you stopped for any other reason (access, time, rate limits), say so and mark the affected conclusions as limited or undetermined.

I do not want a long list for the sake of length. Choose at most 3-5 projects for deep code examination, when the evidence indicates they are relevant, then record the other projects you examined briefly, with a short reason for excluding each.

---

5. Examine the actual implementation and the evidence

For each project you choose to examine in depth, examine the actual code, not only the README.

Focus on: core engine, parser, dispatcher, command handlers, state model, PNR model, and state transitions, preconditions and validation, availability, inventory, sell, SSR, seat maps, pricing, fare rules, ticketing, and queues, persistence, errors, result/output model, separation between engine and UI, fixtures, datasets, and tests, license, and activity and commit history.

Do not treat a feature's presence in a README as evidence of a real implementation, and do not treat the presence of a command as evidence of correctness or depth.

Always separate:

Amadeus truth
What can be supported by a reliable source according to DEIXEN's Verification Standard.

Third-party implementation
What the external project chose to implement.

Architectural pattern
An engineering idea that is useful regardless of Amadeus fidelity.

Evidence / hypothesis
A clue or hypothesis worth investigating but not Amadeus truth.

Do not elevate a single implementation to the level of truth.

And do not automatically elevate the agreement of several independent projects to verified behavior.

---

6. Compare, then look for what could change the decision

After understanding both sides, compare DEIXEN with the external projects.

Look with the same candor for:

- Something external that improves DEIXEN or exposes a gap in it
- A behavior or edge case we did not notice
- A useful test case, fixture, or dataset
- A better parser/state pattern or architecture in a specific subsystem
- Something in DEIXEN that is stronger and should not be replaced
- Or the absence of anything material worth changing

Do not look for confirmation of the current plan. Look for any evidence that could change the decision.

If you find a point where an external project is better, say so clearly. If you find that DEIXEN is stronger on a point, say that too. If you find the external projects are weaker than they look, say so.

---

7. Licensing and reusability

For each relevant project:

- License type, and is it clear?
- Does it permit code reuse according to its text?
- Is it better to use the idea or the test pattern instead of copying code?
- Are there restrictions that need human review before any adoption?

This is a preliminary engineering and licensing assessment, not legal advice.

Do not make a binding decision about adopting external code. Any final decision belongs to the project owner.

---

8. Recommendation and deliverables

Do not use a predefined decision framework. Decide yourself, based on the evidence, what the right recommendation for DEIXEN is. It may be: continue as is, limited improvements, adopt specific patterns, add fixtures/datasets/tests, redesign a subsystem, replace a part, or something else.

Do not assume a change is needed, and do not assume that no change means the research failed.

Start with an Executive Summary of about 300-400 words that includes: the direct answer, the strongest evidence, the most important external finding, the most important gap if any, and whether there is a material impact on Phase 6.

Then the details, which must include at minimum:

Ecosystem Findings: the main projects and what makes each one relevant or not relevant.

DEIXEN Assessment: what you actually found in the current implementation.

Comparative Findings: the meaningful differences.

Gaps / Opportunities: the real gaps or opportunities.

Reusable Knowledge: classify what can be leveraged as code / architecture pattern / parser pattern / state-model idea / dataset / fixture / test case / workflow / command inventory / documentation reference.

Risks: risks of adoption, borrowing, or redesign, including regression, maintenance, and licensing.

Decision: what you recommend and why.

Then the "Design-facing requirements" section described in the PLAN CONTEXT.

Link every important conclusion to a repository/file/code path or an appropriate source. If verification is not possible, say explicitly that the result is undetermined.

Finish with the HANDOFF BLOCK defined in the charter. It must be self-contained and must follow the charter's identifier model: every finding, requirement, candidate, preserved item and open item is ONE ledger row with an S1- ID, and the Preserve list, Requirements for later steps and Open items sections only index those row IDs. Findings = rows for your gaps, opportunities, risks, and documentation-vs-code conflicts. Preserved items = rows with status preserve, for what is stronger in DEIXEN (section 6). Requirements = rows (type requirement), each naming its target step: what Step 2 and Step 3 need from the engine, plus the Design-facing requirements condensed and targeted at Step 4 (for each: exposed / partial / not, additive or not, what a UI would otherwise fake, and the learner-facing state it serves). Candidates = rows (type candidate) for any ideas your findings suggest for other steps, each labeled non-binding and naming the step that would evaluate it. Coverage = what you examined and what you deliberately did not, with a reason for each, plus your search trail and saturation statement and how far the shared journey was traced. Only this block will be pasted into Step 2.

---

Definition of "material impact"

Consider a finding material only if at least one of the following holds:

1. It could change a decision in the design or ordering of Phase 6.
2. It reveals a real risk to the correctness or scalability of the current engine.
3. It saves a substantial amount of build or verification work, with evidence that can be examined.
4. It reveals an important behavior or edge case that deserves to enter the formal verification path.

Small differences, cosmetic improvements, or a higher command count alone are not material unless you explain why they actually affect DEIXEN.

---

Independence rules

Do not assume in advance that RaheesAhmed or any other project is the best, that DEIXEN is better, that it needs a change, or that it does not.

You decide that from the evidence.

And do not make command count an independent criterion. Separate: command presence, functional behavior, stateful behavior, behavioral fidelity, testability, and maintainability. 40 commands that are deeper, more consistent, and more provable may outperform 500, and at the same time do not discount the value of breadth if it is within DEIXEN's scope.

---

Important rule about Amadeus behavior

Any information you discover during this investigation from an external simulator or repository does not become Amadeus truth as a result of this investigation.

Do not enter any result into DEIXEN_Amadeus_Verified_Reference.md, and do not treat it as verified behavior.

Any new behavior that appears as a candidate later goes through DEIXEN's usual path: verify -> spec -> build -> test.

---

Final question

After completing the investigation, answer clearly:

Did the search of the open-source ecosystem reveal any implementation, architectural idea, dataset, test pattern, or evidence that deserves to materially affect the DEIXEN engine or the way it is expanded in Phase 6?

If yes, specify exactly what it is, what the evidence is, and how it could affect it.

If no, explain why not, based on what you examined.

---

Language

Write the Executive Summary in simple Egyptian Arabic, keeping technical terms in English. Write the detailed sections in English. The Handoff Block's summary is also in simple Egyptian Arabic (max 5 lines); the rest of the block is in English.
9. Prompt 5 — COMPLETE v1.8

Opus, Effort: High, preparation sessions for Steps 2-4 only. The complete Charter v1.8 comes first, then the Briefing.

text
DETOUR CHARTER v1.8

PURPOSE
Between Phase 5 and Phase 6, audit what Phases 1-5 built and, only where the
evidence justifies it, strengthen it, so Phase 6 multiplies strength, not
weakness. Four separate steps: engine, learning, freeze, design. Results are
pasted forward manually.

GOVERNING QUESTION
What, if not discovered now, will be expensive to fix after Phase 6?

PRINCIPLES
- Outcomes are never predetermined. "Keep as is" and "no change" are valid.
- A step may think beyond its own domain. It may state REQUIREMENTS for other
  steps (what must be true or exposed for them to do their job) and surface
  CANDIDATES (ideas, options, hypotheses that arise from its findings), each
  labeled non-binding and naming the step that would evaluate it. It never
  recommends or decides another step's outcome, and never plans or executes it.
- Design comes last and expresses frozen decisions; it does not invent.
- Existing decisions in 07 change only by the owner (governance, D29). A step
  that finds a case against one records it as an open item, never a decision.
- Lens, not conclusion: honesty with the learner. The learner can always tell
  what is verified Amadeus behavior, a DEIXEN training message, a hint, an
  attempt, feedback, progress, mastery, or system state. A step may find no
  issue here.
- Nothing is created in any repo, except what AUTHORITY allows Step 4. This
  charter lives inside prompts, not a file. Outputs are chat replies unless the
  step's prompt says otherwise.

AUTHORITY
- Steps 1 and 2 recommend within their own domain. Step 3 proposes the Freeze
  Package. Step 4 improves and verifies the design inside the scope below.
  Nothing produced by a step binds until the project owner explicitly accepts
  it. The accepted Freeze Package binds Step 4 and Phase 6. Its Freeze, design
  scope and landing times are then recorded in 07 as a decision by the owner;
  Step 4 is prepared and run only after that record exists.
- Steps 1, 2 and 3 modify nothing: no code, documents or decisions.
- Step 4, only after the Freeze Package is accepted and recorded, may implement
  design changes inside the design scope that package defines.
  Design scope = how existing engine and learning outputs are presented:
  layout, hierarchy, typography, color and semantic-state rendering (styling
  only), interaction patterns, Terminal presentation (styling and container
  only), and interface copy = text of the interface itself (navigation,
  controls, headings, empty and system states) that neither teaches nor
  carries Amadeus behavior.
  Limits that always apply:
  (1) engine output is rendered exactly as received: no reflow, trimming,
  re-alignment, truncation or rewording;
  (2) what the engine receives, and what counts as an attempt, hint, reveal or
  mastery, is unchanged;
  (3) when, whether and how much learning support appears (hints, Coach, Ghost
  Mode, Speed Drills, Scenarios, Assessment) is learning logic, not
  interaction design;
  (4) any text that teaches, instructs, hints, explains, assesses or gives
  feedback is learning content, not interface copy; if unsure, it is learning
  content.
  Excluded: engine behavior, learning logic and content, the wording of
  verified Amadeus output and training messages (how they are styled is
  semantic-state rendering, inside the scope), frozen files, governing
  documents and decisions.
  Step 4 may create a new file only if the recorded design scope explicitly
  names that file; otherwise it edits existing files only.
  The Freeze Package sets the exact scope inside this definition; only an
  explicit owner decision can widen it.
- Step 4 works in isolation and reversibly (for example a separate branch, per
  CLAUDE.md). Its changes are proposals in code form: they join the project
  only when the owner accepts the Closing Report.
- Anything outside a step's authority is never done silently: it goes through
  the RETURN PATH. All other accepted changes (engine, learning, documents) are
  implemented as separate tasks started by the owner through the project's
  normal pipeline, on the schedule the Freeze sets.

GAP TEST (deficiencies in DEIXEN)
A gap only if it (a) multiplies with Phase 6, (b) prevents actual learning, or
(c) contradicts a verified fact or frozen decision. Otherwise: deferrable
improvement. Opportunities (improvements that fix no deficiency, e.g. external
work saved, or a material gain in learning or in what Phase 6 inherits) are
judged by the step's own materiality definition and still get a ledger row.

EVIDENCE
Observed (seen in real code/docs, not README claims) / Inferred / Judgment
(labeled). A step's own classifications apply in addition.

LEARNER-BENEFIT TEST (learning-facing recommendations)
Which moment in the learner journey, what changes in learning, how we would
know, at what cost.

SHARED JOURNEY
AN -> FXP, plus two deviations: a wrong command, and a returning learner after
a break. Trace as far as the snapshot reaches; where it stops is itself a
finding.

DELIVERY
The full report may follow the step's own structure. It ends with a HANDOFF
BLOCK, the only part pasted forward. The block must be self-contained: a reader
with only this charter and the block can act on it, so claims, evidence
pointers and reasoning are written in it, never "see the report above".
In this order:
Summary (simple Egyptian Arabic, max 5 lines) / Inputs received (each by ID:
used, rejected with a reason, or passed on unchanged; none dropped silently) /
Preserve list / Ledger rows / Requirements for later steps (each names its
target step) / Open items + what would change my mind / Coverage (examined,
including how far the shared journey was traced; deliberately not examined,
with a reason) / Exit check.

Identifiers. Every finding, requirement, candidate, preserved item and open
item is ONE ledger row with its own ID. IDs use the producing step's prefix and
a sequential number: S1-01, S1-02, S2-01, S2-02, S3-01, S4-01. A later step
never renumbers or reuses an earlier step's IDs, and never assigns a new ID to
an earlier step's item merely because it discusses it. The sections Preserve
list, Requirements for later steps and Open items are indexes of existing
ledger rows only; they never introduce an item that is not a row. No second
identifier system exists.
Ledger row: ID | type (gap, opportunity, risk, doc-code conflict, strength, open-item,
requirement, candidate) | claim (one plain sentence) | evidence: level + pointer |
journey point and learner-facing state, if any | Phase 6 impact | status
(confirmed, preserve, open, deferred, rejected) | relates to (IDs), if any.
A candidate is its own row, explicitly labeled non-binding, and names the step
that would evaluate it. A requirement is its own row and names its target step.
A preserved item is its own row (normally type strength, status preserve). An open item is its own row (type open-item when it is an unresolved item without a more specific substantive type; otherwise use the most specific substantive type and status open).
Locked decisions in the Freeze use IDs F-01, F-02, F-03 and so on; each cites
the source ledger row IDs from which it was derived.

RETURN PATH
Before the Freeze, shortfalls travel forward as requirements to Step 3. After
the Freeze (Step 4): if the design needs something outside its authority or
something the Freeze lacks, write a change request (must pass the gap test),
mark the affected item blocked, and do not fake or work around it. Continue
only with items that do not depend on it; if none can continue, stop. Owner
decides. One round, affected item only.

EXIT CONDITION
Every in-scope item has a final status; preserve list and requirements for the
next step written; open items named. (Or a precondition failure reported as the
step's prompt requires.)

CLOSING
Step 4 ends the detour with a Detour Closing Report, which is also its HANDOFF
BLOCK. It is built from the Freeze Package and Step 4's own results: readiness
statement for Phase 6, frozen decisions, design changes made and verified (with
their branch/commit references and the scope-audit result against the recorded
design scope), other accepted changes by landing time, preserved items,
coverage ledger, and up to 3 likeliest unverified risks to Phase 6, or none
identified. It is traceable: each decision cites its source row IDs, each
design change cites the F-ID or requirement row it serves, each verification
result cites what it verified.

FREEZE = locked decisions + explicitly listed open items + how to change them.
FREEZE PACKAGE = Step 3's HANDOFF BLOCK. It carries the Freeze and everything
Step 4 and the Closing Report need from Steps 1-3 that the Freeze alone does
not: the design scope (stated in full: the definition, the four limits, the
exclusions and any file it names); when each accepted change must land (before
Step 4 / before Phase 6 / with Phase 6 / deferred); the consolidated ledger
(open and design-relevant rows in full, closed rows one line each); the
requirements and candidates Step 4 must evaluate, in full; the preserve list;
and the cumulative coverage of Steps 1-3. Each locked decision (F-ID) cites the
ledger row IDs it came from.
Step 4's input is the accepted Freeze Package. Its Freeze, design scope and
landing times are already recorded in 07: the package is the working copy and
07 is the canonical copy of those parts.

=====================================================================

DETOUR BRIEFING FOR THE PROMPT-WRITER

STATUS
A persistent orientation layer, not a step. It produces no findings and makes
no decisions. It is used only in sessions that prepare the prompt for Step 2,
3 or 4, never in a session that executes a step.

ROLE
You will help the project owner write the prompt for ONE detour step at a time
(Step 2, 3 or 4). You write prompts; you do not execute the steps. Nothing is
created or modified in any repo or file. Talk to the owner in simple Egyptian
Arabic (technical terms in English). The step prompts themselves are written in
English.

READ FIRST
DEIXEN_Execution_Plan.md (the detour rows in §3 and §7), 07_DEIXEN_Canonical_
Decisions_and_Current_State.md (the detour decision and, once it exists, the
recorded Freeze), and this brief. If they conflict with each other, with the
charter, or with the handoff the owner pastes, say so; do not silently choose.

WHAT THE DETOUR IS
Phases 1-5 built and validated a slice. Phase 6 will multiply everything, so any
weakness in the foundation will be multiplied with it. The four steps are an
audit of what already exists and, where the evidence justifies it, decisions to
strengthen it. They are not feature phases. Steps 1-3 implement nothing; Step 4
may implement design changes, only inside the design scope the accepted and
recorded Freeze Package defines (charter: AUTHORITY). Each step looks at the
same product through a different lens:
1) Engine: does the engine (and any external work) support what Phase 6 needs?
2) Learning: how do learners actually learn here?
3) Synthesis & Freeze: one coherent set of decisions, proposed for the owner.
4) Design: an honest, distinctive expression of what was frozen.
The order is deliberate: Engine -> Learning -> Freeze -> Design -> Phase 6.
Design is last because it expresses frozen decisions; it does not invent them.

WHAT THE OWNER NEEDS
Assurance that the work was done properly: every task given its due, everything
logical considered, and no big surprise waiting after Phase 6 starts. He wants a
foundation that is strong methodologically and visually, with an identity of its
own, and real progress wherever the evidence shows room for it. Where it does
not, a documented keep-as-is is real progress too, because it is certainty. He
is satisfied by all three together: (a) a short list of frozen decisions,
(b) for each of engine, learning and design, a clear account of what changes
and what stays, each backed by evidence, (c) confidence that no large surprise
is coming. Success is measured by the quality and evidence of the decisions,
never by the number of changes. "Strongest result" does not mean "biggest
change"; limited change, no change, and keeping what exists are legitimate
outcomes when the evidence supports them.

WHAT EACH STEP MUST GET RIGHT (intent only; never predetermine findings)
Step 1 is already written and runs in its own session. Do not rewrite it. Its
handoff block feeds Step 2.

Step 2 - Learning Design + Learning Experience Review -> Learning Decision.
Not only WHAT is taught but HOW it is learned: sequencing; Guided -> Independent
Practice; the relation between the learning layer and the Terminal; feedback
quality; turning errors into learning; Coach timing; Ghost Mode; Speed Drills;
Scenarios; Assessment; evidence; growth/readiness; excess cognitive load;
repetition; gaps. Do not assume the current system is right or wrong. It
examines the real implementation and spec, traces the shared journey starting
from Step 1's trace, and states requirements for Step 3 and Step 4. It also
receives Karim's Phase 5 learner-test record (07 Decision 67 and the test
document): real evidence from a real beginner. Each note in it becomes ONE S2
ledger row (evidence: Observed, learner test, with the test step it came from)
and is confirmed, rejected with a reason, or passed on; none is dropped. A note
may be an engine, learning or design matter: Step 2 places it, it does not
decide another step's outcome. Lessons or explanations that would teach new
Amadeus facts need the Verified Reference first (07 D12, D13). Its
"Learning Decision" is a recommendation to the Freeze, not a binding decision.
Any new item it raises is a ledger row with an S2- ID.

Step 3 - Synthesize & Freeze Decisions (Engine + Learning + Product constraints).
Merges the earlier handoffs into ONE coherent proposal for the owner: the
FREEZE PACKAGE defined in the charter. It resolves conflicts; places EVERY
received ledger row ID (requirements and candidates are rows too) exactly once
with a status and a reason, so that nothing is dropped silently, and its exit
check states how many IDs it received and how many it placed; proposes the
locked decisions as F-01, F-02 and so on, each self-contained and citing the
source row IDs it came from; lists open items explicitly (as rows, indexed by
ID); defines how a frozen decision can be changed; states when each accepted
change must land (before Step 4 / before Phase 6 / with Phase 6 / deferred),
including which engine or learning changes Step 4 depends on; and defines the
design scope Step 4 may change, inside the charter's definition, stated in full
(the definition, the four limits that always apply, the exclusions, and any new
file it explicitly names). The Freeze, the design scope and the landing times
form one clearly labeled section, written so that it can be recorded in 07
verbatim. Requirements and candidates aimed at Step 4 are passed on in full for
Step 4 to evaluate: Step 3 may constrain them but does not decide them. Any new
item Step 3 raises is a ledger row with an S3- ID. It carries the cumulative
coverage of Steps 1-3. The package binds only after the owner explicitly
accepts it; that labeled section is then recorded in 07 before Step 4 is
prepared (charter: AUTHORITY). Its output must be readable in a fresh session
with no context.

Step 4 - Design Improvement Round -> Design Verification.
Its input is the accepted Freeze Package, whose Freeze, design scope and landing
times are already recorded in 07. It is the only step allowed to change
anything, only inside the design scope. In order: (1) inspect the current design
against the Freeze Package, including the requirements and candidates aimed at
it; (2) decide what actually deserves to change, per area ("no material design
change" is a valid result, and verification still runs on the current state);
(3) implement the justified changes inside the design scope, in isolation and
reversibly; anything outside the scope, or anything the Freeze lacks, goes
through the return path; (4) verify the resulting state: a scope audit of the
diff against the recorded design scope (only design-scope files changed; no new
file unless the recorded scope names it; the four limits hold: engine output is
rendered as received, engine input and attempt/hint/reveal/mastery logic are
unchanged, learning-support timing is unchanged, no learning content is
altered), the project's verification loop (no regression), a trace of each
frozen learner-facing state to its real source (nothing faked), the shared
journey on the resulting state, and a short list of what only the owner can
judge (look and feel). Any new item Step 4 raises is a ledger row with an S4-
ID.
Design is an honest expression of what was frozen, not "a prettier UI". The goal
is an identity specific to DEIXEN: not AI-looking, not dated; balancing
distinctiveness, modernity, professional credibility, operational character and
instructional clarity. The identity must come from information presentation,
hierarchy, layout, interaction logic, semantic states (error, success, hint,
verified, attempt, feedback, progress, system state), content treatment, the
Terminal experience, and the meaning of color, not from color alone.
Step 4 also closes the whole detour with the Detour Closing Report defined in
the charter; group the other accepted changes by when they must land so the
owner can schedule the separate implementation tasks.

HOW TO WRITE EACH STEP PROMPT
1. One step at a time, only after the owner pastes its input and the package-level pre-execution review has already been cleared: Step 2 gets the
   Step 1 handoff block and Karim's Phase 5 learner-test record (07 D67 and
   the test document); Step 3 gets the Step 1 and Step 2 handoff blocks;
   Step 4 gets the accepted Freeze Package, already recorded in 07, and only
   that (the raw earlier handoffs would invite re-deciding the Freeze).
2. Structure: charter v1.8 verbatim first; then PLAN CONTEXT (where this step
   sits, the sequence, what is context-only and why); then the task; then a
   precondition check (confirm access to code, docs and inputs, otherwise stop
   and report); then the deliverable; then the HANDOFF BLOCK requirement; then
   the stop condition. If the owner pastes the Step 1 prompt, use it as a
   structural model.
3. Never lead the executor to a conclusion. Frame each lens as a question the
   executor may answer with "no issue". Require evidence levels, the
   learner-benefit test for learning-facing claims, a preserve list, and a
   "what would change my mind" list.
4. Let labeled candidates surface as the charter defines, and forbid
   recommending, deciding or planning another step's outcome. Inputs from
   earlier steps (ledger rows, including requirements and candidates) are
   claims to be used, rejected with a reason, or passed on unchanged, never
   truths. Require the handoff to follow the charter's identifier model: one
   ledger row per item, the Preserve list, Requirements and Open items sections
   only index row IDs, and earlier IDs are never renumbered.
5. Point the executor to the real code and spec, and require doc-versus-code
   conflicts to be reported. Require the same shared journey, starting from the
   previous handoff's trace, with a journey point on each ledger row.
6. For Steps 2 and 4, define what makes an opportunity material: the
   learner-benefit test shows a meaningful effect on learning, or on what
   Phase 6 will inherit (content structure, patterns, components). Polish that
   does neither is deferred but still gets a ledger row.
7. Steps 2 and 3 modify nothing. Step 4's prompt must state: the Freeze record
   (its decision number in 07) and a precondition that it exists and matches
   the pasted package, otherwise stop and report; the design scope (allowed and
   forbidden, taken from the recorded Freeze, with the charter's four limits and
   the new-file rule stated explicitly); the base snapshot (tag/SHA, after any
   changes the Freeze schedules before Step 4); the isolation method (for
   example a separate branch, per CLAUDE.md); the verification loop to run,
   including a scope audit of the diff against the recorded design scope; and
   that anything outside the scope goes through the return path. If the owner
   supplies an accepted Design Exploration Skill as a tooling input, the Step 4
   prompt may name it as an optional tool only, and states that the Skill is
   not an authority source, cannot widen the recorded design scope or change
   the Freeze, and that anything it surfaces outside the scope is non-binding
   and goes through the return path. No new documents without the owner's
   explicit approval; reports are delivered in chat.
8. Where a step depends on open-ended research, include a saturation rule: stop
   when the last several distinct leads add nothing new, and report the trail
   and why it stopped.
9. Keep each prompt as short as the task allows. Length is not quality.
10. Above each prompt, add a short note (outside the prompt) with: recommended
    Effort, exact attachments to send, and that it runs in a clean session. For
    Step 4, also the environment it needs: one with access to the repo that can
    run the verification loop.
11. If you believe the charter, the chain or this brief is missing something
    needed for the strongest result, say so in a short note before the prompt.
    Do not silently change the charter.
12. Self-check before delivering: charter v1.8 embedded verbatim; step role
    respected; no outcome predetermined; materiality defined (Steps 2 and 4);
    handoff block and stop condition present; identifier model followed
    (step-prefixed row IDs, F-IDs, indexes only); earlier inputs consumed
    correctly; authority matches the charter (Steps 2 and 3 modify nothing;
    Step 4 changes only the recorded design scope, and only after the Freeze is
    recorded); the Step 4 scope text is identical in substance to the charter's.

OUTPUT FOR EACH REQUEST
Reply, in this order, then stop:
(1) A preparation note in simple Egyptian Arabic, max 8 lines: any conflict you
    see between this brief, the charter, the Execution Plan, 07 and the pasted
    handoff, and anything missing for the strongest result; for Step 4, whether
    07 records the Freeze and matches the pasted package. If a conflict makes
    the prompt unsafe to write (for Step 4: no Freeze record in 07), stop after
    this note and ask ONE question.
(2) The short note from item 10.
(3) The step prompt, in English.
10. Prompt 6 — COMPLETE

Opus, Effort: Medium. Send after Karim accepts the Freeze Package and before Step 4 is prepared. Fill [DATE] and [N], and paste the Freeze section, design scope and landing times in the marked place.

text
One specific task: record the accepted Freeze of the detour in 07_DEIXEN_Canonical_Decisions_and_Current_State.md.

Karim reviewed the Freeze Package produced by detour step 3 and explicitly accepted it on [DATE]. If he changed anything while reviewing, the text below already includes his changes. Below is the part of the package that must be recorded: the Freeze (locked decisions, explicitly listed open items, and the procedure for changing frozen decisions), the design scope that step 4 may change, and when each accepted change must land. Record exactly this, nothing more and nothing less. The rest of the package (consolidated ledger, coverage, requirements and candidates, preserve list) stays in the package and is not recorded.

[PASTE HERE: the Freeze section, the design scope, and the landing times from the accepted Freeze Package]

What I need:
1. Read 07, including the detour decision recorded as Decision [N]. Record the pasted text as a decision by Karim (governance, reserved under D29), not "by delegation", in the same style and format as the previous decisions in the file. Use ONE decision that contains every pasted item with its own F-ID (F-01, F-02, ...), or consecutive numbered decisions if the file's convention requires one decision per item; in both cases keep each item's F-ID. Tell me which you chose and why.
2. Verbatim: do not paraphrase, merge, reorder, soften or drop any item, and keep the F-IDs and the ledger row IDs (S1-, S2-, S3-) that each locked decision cites. If the file's format forces any change in wording, show me each such change.
3. Check the pasted text against the existing decisions in 07, including Decision [N]. If any item conflicts with an existing decision, stop before editing and tell me. Do not resolve it silently. Also check that the pasted design scope states the definition, the four limits that always apply, the exclusions, and any file it explicitly names, as defined in Decision [N] (which records the design-scope text from the Detour Charter v1.8 AUTHORITY), and that nothing in it widens them. If anything is missing or wider, stop before editing and tell me; do not add, fix or narrow it yourself.
4. If you can edit the file directly, do it. If not, give me the text ready to copy and paste, and state the exact place in the file where it goes.
5. Do not modify any other file. Run an impact check (Constitution §15, using the dependency lines in file 00 §A10) and tell me which files need an update because of this record (for example the status of step 3 and the next step in DEIXEN_Execution_Plan.md). Tell me only; do not apply any update.

In your reply give me: the decision number(s), the final text, a fidelity check (how many items I pasted, how many appear in the record, listed by F-ID), any conflict or warning, and the list of files that need updating.
11. Prompt 7 — COMPLETE — DEIXEN Design Exploration Skill Build

Opus, Effort: Max, fresh clean session. Execute only after Karim has accepted the Freeze, Prompt 6 has recorded the accepted Freeze in 07, and any Freeze-scheduled work required before Step 4 has landed. This is an auxiliary tooling-preparation action, not a Detour Step and not a fifth stage. The Skill is a tool, not authority.

Exact attachments / inputs

Send this Prompt 7 text in a fresh Opus 5.5 session together with:

the current 07_DEIXEN_Canonical_Decisions_and_Current_State.md, including the recorded Freeze;
the current DEIXEN_Execution_Plan.md;
the DEIXEN product/design sources available in the project that the prompt needs;
access to the target Agent Skill / Claude Design environment, when available;
web access for current verification and research.

Do not send the earlier Step 1 / Step 2 handoffs as a substitute for the current canonical state. The Skill build is not a decision-reopening exercise.

Operational boundary

This task is intentionally placed between Freeze registration and Step 4 prompt preparation. It may create or update the Skill artifact only in an isolated skill workspace. It must not modify the DEIXEN application repository, 07, DEIXEN_Execution_Plan.md, the current design system, or any other canonical DEIXEN document.

The accepted Freeze in 07 remains canonical. The Skill must be designed as a reusable exploration tool that operates later under the recorded DEIXEN constraints; it is not allowed to widen those constraints. The Skill must not be applied to DEIXEN during this build task.

text
أريد منك أن تعمل أولًا كباحث واستراتيجي تصميم، وليس كمصمم ينفذ واجهة، وأن تبني لنا مهارة (Agent Skill) متخصصة لاستكشاف الهوية البصرية والاتجاه الإبداعي لـ DEIXEN.

هذه المهمة ليست لتصميم DEIXEN الآن، وليست لتنفيذ واجهات المنتج، وليست لتطبيق المهارة على DEIXEN أثناء بنائها.

المهمة هي: البحث عن أفضل المناهج والأدوات والمهارات المتعلقة باكتشاف الاتجاه البصري، واستكشاف الهوية، واستخراج المراجع البصرية، وبناء اتجاهات متعددة، والمقارنة بينها، ثم استخدام ما تتعلمه لبناء مهارة قوية ومخصصة لـ DEIXEN يمكن استخدامها لاحقًا داخل Claude Design في دورات استكشاف حقيقية.

الناتج النهائي المطلوب هو Skill فعلية قابلة للاستخدام وفق مواصفة Agent Skills الحالية، وليس وثيقة نظرية تشرح كيف يمكن بناء مهارة.

اعمل من الصفر في البحث. لا تعتبر أي بحث سابق أجراه مساعد آخر حقيقة أو قائمة نهائية. أي أمثلة أو أسماء وصلتك مسبقًا هي إشارات بداية يجب أن تتحقق منها بنفسك، وليست مصادر ملزمة.

أولًا: افهم DEIXEN قبل أن تصمم طريقة البحث

اقرأ مصادر DEIXEN المتاحة في المشروع قبل اقتراح المهارة، وبالأخص الوثائق التي تحدد ماهية المنتج، أهدافه، حالته الحالية، والقرارات التصميمية الموجودة.

ميّز بوضوح تام بين:

حقيقة المنتج وما يجب أن يبقى صحيحًا.

القيود والمتطلبات غير القابلة للتفاوض (مثل الوصول، RTL/LTR، الاستجابة، الواقعية المهنية، معنى الألوان الوظيفي).

مبادئ التصميم الأساسية التي يجب احترامها.

القرارات الحالية.

التنفيذ البصري الحالي.

الافتراضات البصرية التي يمكن إعادة التفكير فيها.

الأشياء التي لم تُحسم بعد.

التنفيذ البصري الحالي هو "اتجاه قائم يجب اختباره"، وليس حقيقة لا يجوز تحديها، طالما أن الاستكشاف الجديد مصرح به. لا تفترض أنه الإجابة الصحيحة لمجرد أنه موجود.

لكن تحدي التنفيذ البصري لا يعني إذنًا بتغيير حقيقة المنتج أو القيود غير القابلة للتفاوض. التغيير مسموح في التعبير البصري فقط. ولا تعيد تعريف المنتج نفسه من خلال التصميم.

إذا كانت وثائق DEIXEN المطلوبة غير موجودة، أو ناقصة، أو متعارضة، أو كان هناك اختلاف في الاسم بين AeroBridge وDEIXEN، فلا تخمّن ولا تخلق حقيقة من عندك. حدد المشكلة، وفرّق بين المعروف والمفترض، وأوقف الجزء الذي يعتمد على المعلومة المفقودة إذا كان استمرارك قد يؤدي إلى نتيجة خاطئة، واطلب التوضيح فقط عندما يكون ذلك ضروريًا فعلًا. لا تستخدم معلومة غير مؤكدة كأساس لقرار تصميمي جوهري.

ثانيًا: افهم ذوقي ومتطلبات الاتجاه المطلوب

هذه تفضيلاتي الحالية، وتعامل معها كإشارات قوية وليست كقالب يجب إجبار كل نتيجة عليه:

أميل إلى: تقني، دقيق، أرشيفي، مستقبلي، كلاسيكي حديث.

لكن هذه الكلمات لا تعني أنني أريد الشكل المعتاد الذي ينتج عندما نقول للذكاء الاصطناعي "اجعل التصميم تقنيًا أو مستقبليًا". كما أن "أرشيفي" و"كلاسيكي حديث" لا تعني الوصفة الجاهزة التي أصبحت متكررة في مخرجات الذكاء الاصطناعي (مثل الورق الكريمي مع serif وmono وخطوط رفيعة).

المشكلة التي أريدك أن تحلها تحديدًا:

عندما نقول للذكاء الاصطناعي "ابتعد عن الكليشيهات"، قد ينتج تصميمًا احترافيًا لكنه يبدو قديمًا وتقليديًا جدًا.

وعندما نقول له "اجعله مودرن أو تقنيًا أو مستقبليًا"، قد ينتج تصميمًا جميلًا لكنه يشبه عددًا لا يحصى من التصميمات التي يصنعها الذكاء الاصطناعي حاليًا.

أريد منطقة مختلفة بين الاثنين: تصميم حديث فعلًا، له شخصية واضحة، وليس قديمًا، وليس نسخة من الأسلوب البصري الشائع الذي ينتجه الذكاء الاصطناعي.

ثالثًا: المبدأ الجمالي الأهم

قوة التصميم يجب ألا تأتي من الزينة وحدها. أريد علاقة تبادلية بين المحتوى والتصميم:

المحتوى القوي يجعل التصميم أقوى.

وطريقة تنظيم المحتوى وعرضه تجعل المحتوى نفسه يبدو أكثر قوة وقيمة.

والتصميم يساعد المستخدم على فهم قيمة المحتوى والتفاعل معه.

لا أريد واجهة يمكن وصفها بأنها: "خلفية جميلة + خط جميل + ألوان جميلة + نصوص فوقها." أريد إحساسًا بأن المستخدم دخل منتجًا حقيقيًا له منطق وشخصية ونظام خاص به.

رابعًا: الإحساس المطلوب من المنتج

عند دخول DEIXEN، أريد المستخدم أن يشعر بأنه دخل منتجًا قويًا وله هوية واضحة تخصه، وأن ما يحدث داخله جاد وحقيقي، وليس تجربة ترفيهية أو درسًا بسيطًا.

Amadeus في DEIXEN ليس مجرد موضوع تعليمي عادي. المستخدم يتعلم نظامًا مهنيًا حقيقيًا، وعمق التعلّم يشبه تعلم البرمجة: أوامر، قواعد، تسلسل، دقة، حالات، أخطاء، نتائج، وتراكم في القدرة. التصميم يجب أن يساعد هذا المعنى على الظهور بصريًا.

خامسًا: التوازن

الجمال البصري مهم جدًا بالنسبة لي، لكنه لا يجوز أن يفسد أي شيء آخر. أريد موازنة حقيقية بين: الجمال، الوضوح، الوظيفة، الواقعية المهنية، سهولة الفهم، الهرمية، الكثافة المناسبة، هوية المنتج، والقابلية للتوسع.

كل عنصر في المنتج يجب أن يأخذ حقه بصريًا بحسب وظيفته، وليس لأننا نريد أن نُظهر التصميم فقط.

سادسًا: معنى الألوان الوظيفي

هناك حالات لا يجوز التعامل معها كاختيار جمالي حر. نتائج Amadeus يجب أن تحافظ قدر الإمكان على منطق الألوان المعروف في النظام الحقيقي. الخطأ يجب أن يكون واضحًا كخطأ (الأحمر عندما يكون مناسبًا)، والنجاح أو الصحة أو التصحيح يمكن أن يستخدم له الأخضر عندما يكون مناسبًا، وهكذا.

لذلك يجب أن تفرّق المهارة بين الألوان التي تبني الهوية البصرية والألوان التي تحمل معنى وظيفيًا يجب احترامه. لا تجعل "هوية البراند" سببًا لتدمير المعنى الوظيفي.

سابعًا: نطاق الهوية

نطاق الاستكشاف هو هوية DEIXEN الكاملة، بطريقة منضبطة. المقصود هنا:

الهوية البصرية.

التجربة البصرية والتفاعلية.

اللغة البصرية.

طريقة التعبير عن المعلومات داخل المنتج وعبر العلامة.

أي أن الاستكشاف يمكن أن يصل إلى: شخصية العلامة، اللغة البصرية، الألوان، الخطوط، التكوين، المواد والأسطح، الصور والرسوم، أسلوب الأيقونات، أسلوب الحركة، طريقة تقديم المعلومات، المبادئ البصرية، والقواعد التي يمكن أن تتحول لاحقًا إلى نظام بصري ونظام واجهات.

ولا يعني ذلك فتح مشروع منفصل لإعادة بناء استراتيجية العلامة، أو الاسم، أو التموضع التجاري، أو الرسائل التسويقية، أو استراتيجية التسويق. ولا تفتح مسارًا للهوية اللفظية أو Brand Voice. يمكن دراسة طريقة التعبير عن المعلومات والنصوص داخل المنتج عندما تكون ضرورية لفهم التجربة البصرية، لكن لا تجعل اللغة اللفظية مجالًا مستقلًا. وأي أمر من هذه الأمور يُتناول فقط عندما يكون ضروريًا لفهم أو بناء الاتجاه البصري.

بخصوص الشعار والـwordmark: يجب أن توضح المهارة هل يدخل ضمن الاستكشاف: الـwordmark، الشعار، الرمز، النظام الطباعي، والعناصر الأساسية للهوية. اجعلها قادرة على استكشاف هذه الأشياء عندما يكون ذلك مناسبًا، لكن لا تجعلها تنجرف تلقائيًا إلى إعادة تصميم الشعار إذا كان السؤال المطروح يخص لغة بصرية أوسع.

المنتج نفسه هو أهم ساحة لاختبار الهوية. يجب اختبار الاتجاهات على الشاشات والسياقات الحقيقية في DEIXEN: Terminal، Learning، Scenario، Growth / Readiness، وحالات الخطأ والنجاح والسجلات والمعلومات التشغيلية.

ثامنًا: ما الذي يمكن أن يميز DEIXEN؟

لا أريد أن يكون البحث عن "ما أجمل ستايلات التصميم؟". ولا أريد تحليلًا للمنافسة التجارية أو حجم الشركات أو الحصة السوقية. السؤال الأعمق هو:

ما الذي يمكن أن يجعل DEIXEN مميزًا بصريًا وتجريبيًا وفي طريقة عرض المعلومات مقارنة بما يحيط به، بدون افتعال الاختلاف؟

قبل الحديث عن التميز، عرّف "الجوار" في مستويين:

1. الجوار المباشر: تدريب GDS، تعليم الطيران، منصات التدريب المهني ذات الصلة.

2. الجوار البنيوي: منصات تعلم البرمجة، الـterminals، الأدوات المهنية، أنظمة العمل الكثيفة بالمعلومات، والمحاكاة.

افهم ما هو متوقع بصريًا في هذه البيئات، ثم ابحث عن مساحة تميز حقيقية لـDEIXEN. وإن ظهر بحث تنافسي أثناء ذلك فليخدم فهم الجوار البصري والتجريبي فقط.

ابحث عن أمثلة حقيقية ومناهج قوية من صناعات مختلفة، وليس الطيران فقط: الأنظمة المهنية، المحاكاة، البرمجيات المتقدمة، الأدوات الصناعية، الأنظمة التشغيلية، الهندسة، البيانات، الماليات، التدريب المتخصص، الأرشفة، الأدوات الإبداعية، والصناعات غير المتوقعة التي يمكن أن تقدم أفكارًا مفيدة.

لا تنسخ مظهر أي منتج. استخرج المبادئ وراء ما تراه.

تاسعًا: ابحث عن أفضل المناهج والمهارات الموجودة حاليًا

ابحث بنفسك على الويب وGitHub، ولا تحصر البحث في مستودعات أو Skills مفتوحة المصدر. ابحث أيضًا عن: المناهج المنشورة، دراسات الحالة، طرق التفكير في الهوية البصرية، أساليب النقد، منهجيات البحث المرجعي، ممارسات art direction، والطرق العملية التي يمكن استخلاصها وتحويلها إلى workflow.

المواضيع المطلوبة تشمل: اكتشاف الاتجاه البصري، البحث عن المراجع، استكشاف عدة اتجاهات، التفكير في الهوية البصرية، استخراج "لغة التصميم" من المراجع الحقيقية، المقارنة بين الاتجاهات، النقد البصري، دورات المراجعة، واستخدام النماذج الذكية في عملية الاستكشاف الإبداعي.

كن مستقلًا في البحث. يمكنك أن تجد مصادر أفضل أو أسوأ مما ذُكر لك. وجود repository لا يعني أن المنهج قوي، وعدد النجوم والشهرة ليسا معيارًا وحيدًا. قيّم المنهج نفسه، ولكل مصدر قوي افحص:

ماذا يفعل فعلًا؟ ولماذا هو مفيد؟

ما الجزء القابل لإعادة الاستخدام؟

ما الذي لا يناسب DEIXEN؟

هل هو عملي أم كلام نظري؟ وهل ينتج نتائج مفيدة فعلًا؟

هل يمكن تحويله إلى خطوات قابلة للتنفيذ داخل مهارة؟

ما عمقه وحداثته وارتباطه بالمشكلة؟

إذا وجدت مصادر أقوى من الأمثلة التي وصلتك مسبقًا، استخدم الأقوى.

عاشرًا: متى تتوقف عن البحث

لا أريد بحثًا لا نهائيًا ولا إهدارًا للتوكنز. وفي الوقت نفسه لا تتوقف لمجرد إحساسك بالكفاية.

ابدأ باستكشاف واسع بما يكفي لاكتشاف المنهجيات القوية، ثم ضيّق البحث تدريجيًا.

تتبّع عائلات أو فئات المنهجيات التي غطيتها.

توقف عندما تبدأ النتائج الجديدة في تكرار نفس المبادئ والآليات بدل تقديم زوايا أو مناهج جديدة ذات قيمة. انتبه إلى أن تكرار النتائج قد يكون سببه تشابه صياغة استعلاماتك، فنوّع الاستعلامات قبل أن تحكم بالتشبع.

قبل التوقف، تأكد أن الـcorpus متنوع في نوع المنهجيات والسياقات البصرية والصناعية، وليس مجموعة مصادر متشابهة تعيد الفكرة نفسها.

لا تستخدم عددًا ثابتًا للمصادر كشرط نجاح.

في نهاية البحث، وثّق ما غطيته (العائلات والسياقات)، وما أضافته كل عائلة، وما علامات التشبع التي جعلتك تتوقف.

حادي عشر: تحقق من واقع Agent Skills وClaude Design

لا تفترض قدرات المنتجات الحالية من الذاكرة. تحقق من المصادر الرسمية الحالية قبل تصميم البنية النهائية للمهارة، فيما يتعلق بـ:

مواصفة Agent Skills: ملف SKILL.md، بنية المجلد، frontmatter الصحيح وقيود حقوله الحالية (name وdescription، صيغتها وطولها، وأي قيود أخرى في بيئة الاستخدام المستهدفة) كما تظهر في المصدر الرسمي لا من الذاكرة، الملفات المرجعية والموارد، ما يُحمَّل دائمًا وما يُحمَّل عند الطلب.

Claude Design: الـArtifacts أو النماذج الأولية، وإمكانية استخدام المهارات في السياق المقصود، وحدود البحث أو الوصول إلى المراجع.

إذا وجدت قيدًا عمليًا يمنع خطوة معينة، فلا تتجاهله. صمّم المهارة بخطة بديلة واضحة. مثال: إن لم يكن الوصول إلى مرجع بصري خارجي متاحًا في سياق الاستخدام، فيجب أن يوجد مسار يسمح لي برفع المرجع أو لقطة الشاشة أو المادة المطلوبة. لكن لا تجعل القيود الحالية سببًا لتسطيح المنهج.

اكتب وصف (description) المهارة ضمن هذه القيود، بحيث يُفعّلها فقط في سياق استكشاف الهوية والاتجاه البصري، لا في أي تعديل عادي على الواجهة. ولا تحوّل هذا إلى درس نظري عن Agent Skills؛ المطلوب مهارة حقيقية جاهزة.

ثاني عشر: بعد البحث، صمّم مهارة DEIXEN نفسها

لا تكتب مجرد تجميع للنصوص التي وجدتها. ابنِ مهارة جديدة مصممة خصيصًا لـDEIXEN، بالبنية التي يقتضيها التحقق في القسم السابق، مع ملفات مرجعية أو موارد إضافية فقط عندما تكون ضرورية. افصل بوضوح بين التعليمات التي يجب أن تكون متاحة دائمًا (SKILL.md) والمعرفة التي يمكن تحميلها عند الحاجة. استخدم progressive disclosure ولا تحوّل SKILL.md إلى مستند ضخم بلا داعٍ.

يجب أن تساعد المهارة على دورة مثل:

فهم المنتج → تحديد سؤال الاستكشاف → بحث عن مراجع حقيقية → تحليل لماذا تعمل هذه المراجع → توليد عدة اتجاهات مختلفة فعلًا → بناء نماذج أولية قابلة للمشاهدة → مقارنة الاتجاهات → الحصول على ملاحظاتي → تعديل الاتجاهات → جولة ثانية أو ثالثة عند الحاجة → تجميع ما تم تعلمه → صياغة اتجاه بصري مرشح للهوية → التوقف قبل اعتماده نهائيًا.

هذه الدورة تصف كيف ستعمل المهارة لاحقًا، وليس ما يجب عليك تطبيقه الآن.

المهارة لا يجب أن تفترض من البداية أن الاتجاه الحالي أفضل من البدائل، ولا أن ترفضه لمجرد الرغبة في التجديد.

متطلبات بنية المهارة:

1. كل خطوة قابلة للتنفيذ. لا تسمح للمهارة بأن تكون مجموعة نصائح عامة. لكل خطوة مهمة يجب أن يكون واضحًا: ما المدخل؟ ماذا تفعل المهارة؟ ما المخرج؟ متى تُعتبر الخطوة مكتملة؟ ما الذي يجب التحقق منه؟ وماذا يحدث إذا فشلت أو لم تتوفر بيانات كافية؟

2. مرحلتان للدقة عندما يكون ذلك مناسبًا. المرحلة الأولى: استكشاف واسع ومنخفض الدقة لعدد من الاتجاهات، بحيث يظهر منطق كل اتجاه بسرعة وبتكلفة معقولة. المرحلة الثانية: بعد ظهور الاتجاهات الأكثر إثارة للاهتمام، تطوير عدد أقل منها بدقة أعلى واختبارها بعمق. ليست قاعدة جامدة إذا تطلب السياق غير ذلك. المبدأ: لا تنفق تكلفة عالية على اتجاه قبل أن تثبت الفكرة نفسها أنها تستحق الاستكشاف.

3. حلقة ملاحظات سهلة لي. لا تفترض أنني مصمم ولا أنني أستخدم مصطلحات تصميم. صمّم الحلقة بحيث أعبّر بسهولة: أيهما أقرب لي؟ ما الذي لا يعجبني؟ ما الذي أشعر أنه مصطنع؟ ما الذي يبدو قديمًا؟ ما الذي يبدو قويًا؟ ما الذي أشعر أنه خاص بـDEIXEN؟ ما الذي يجب الاحتفاظ به وما الذي يجب التخلص منه؟ ثم تحوّل المهارة كلامي البسيط إلى استنتاجات قابلة للاستخدام في الجولة التالية.

4. ذاكرة للاستكشاف. طريقة بسيطة لحفظ: ما تم استكشافه، ما تم رفضه ولماذا، ما تم الاحتفاظ به، وما تم تعلمه. حتى لا تبدأ كل دورة من الصفر ولا تعيد إنتاج نفس الاتجاهات أو المراجع.

5. التعامل مع نقص المعلومات. يجب أن تتصرف المهارة عند نقص أو تعارض وثائق DEIXEN بالطريقة نفسها الموضحة في القسم الأول.

6. اختبار المهارة بعد بنائها. بعد إنشاء المهارة، اختبر بنيتها وصحة SKILL.md وفق المواصفة الحالية، باستخدام أداة التحقق الرسمية أو المناسبة إن كانت متاحة في بيئتك. وإن لم تتوفر أداة، فتحقق يدويًا من المواصفة وقل صراحة أن التحقق كان يدويًا. أصلح أي أخطاء قبل عرض النسخة النهائية. هذا اختبار لبنية المهارة وصحتها فقط، وليس تشغيلًا لها على DEIXEN ولا بدء دورة استكشاف.

فاصل مهم قبل الأقسام التالية

الأقسام من الثالث عشر إلى الثامن عشر تصف السلوك الذي يجب أن تبنيه المهارة لاحقًا، وليست أوامر تنفذها الآن. أنت الآن تبني "الأداة والمنهج". لا تستخدم الأداة لاختيار اتجاه DEIXEN، ولا تنفذ دورة الاستكشاف، ولا تنتج اتجاهات أو نماذج فعلية، ولا تقدم توصية باتجاه. أي توصية تُذكر في هذه الأقسام هي سلوك تفرضه المهارة على نفسها حين تُستخدم لاحقًا.

ثالث عشر: اختلاف حقيقي بين الاتجاهات

يجب أن تُلزم المهارة بأن تنتج اتجاهات متعددة، وألا تعتبر تغيير اللون فقط، أو الخط فقط، أو الخلفية فقط اتجاهًا جديدًا. يجب أن تختلف الاتجاهات في المنطق نفسه، مثل: طريقة ترتيب المعلومات، العلاقة بين المحتوى والفراغ، الهرمية، الكثافة، العلاقة بين العناصر، طريقة استخدام الخط، شكل الأسطح، طريقة بناء الهوية، طريقة إبراز حالات النظام، أو طريقة ربط الهوية بالوظيفة.

أريد اتجاهات يمكنني أن أقول عنها: "هذه فلسفة تصميم مختلفة عن هذه"، وليس "هذه نفس الفكرة بلون آخر."

رابع عشر: لا تقع في فخ "المستقبلي = AI"

هذه نقطة أساسية جدًا. يجب ألا تستخدم المهارة كلمة "مستقبلي" كاختصار لـ: زجاج، وهج، تدرجات، نيون، عناصر عائمة، واجهات خيال علمي، أو أي شكل أصبح مرتبطًا تلقائيًا بتصميمات الذكاء الاصطناعي.

ولا يكفي ذلك. يجب أن تتحقق المهارة من أنها لا تستبدل هذه الكليشيهات بكليشيهات أخرى: "أرشيفي" أو "تحريري تقني" أو "كلاسيكي فاخر" أصبحت هي نفسها وصفات جاهزة متكررة في مخرجات الذكاء الاصطناعي.

وفي الوقت نفسه، لا تقع في الخطأ المقابل: "حتى لا يبدو AI، فلنجعله تقليديًا." المطلوب هو اكتشاف حداثة حقيقية مبنية على شخصية DEIXEN.

بدل الاعتماد على قائمة ممنوعات فقط (فهي تشيخ وتدفع إلى بدائل نمطية)، يجب أن تستخدم المهارة اختبارات حقيقية على كل اتجاه:

هل يمكن نقل هذا الاتجاه إلى منتج آخر فقط بتغيير الكلمات والمحتوى؟

هل يعتمد تميزه على مؤثرات سطحية أم على منطق بصري حقيقي؟

هل يمكن تفسيره من خلال طبيعة DEIXEN ومحتواه؟

هل هو مشتق من بنية المنتج وطريقة استخدامه، أم من كلمات مزاج مثل "تقني" و"مستقبلي"؟

هل يبقى حديثًا إذا أزلنا المؤثرات الرائجة؟

What specific product truth generated this visual decision?

Could this visual direction plausibly belong to another product if the content were replaced?

خامس عشر: التميز نظام وليس gimmick

يجب أن تسأل المهارة عن كل اتجاه: ما الذي يجعل الشخص يستطيع التعرف على DEIXEN من شاشة واحدة حتى لو اختفى الشعار؟

لا تعتبر "الحركة المميزة" أو "التفصيلة اللافتة" نجاحًا بحد ذاتها. يجب أن يكون التميز جزءًا من نظام بصري:

قابل للتعرف.

مرتبط بطبيعة DEIXEN ومحتواه وطريقة استخدامه.

قابل للتطبيق على أكثر من شاشة.

قابل للتطور إلى نظام تصميم.

السؤال ليس "ما الشيء الغريب الذي يمكن أن نفعله؟" بل "ما النظام البصري الذي يجعل DEIXEN قابلًا للتعرف عليه دون الاعتماد على شعار أو gimmick واحدة؟" ولا تخترع حركة شكلية لمجرد أن تكون مختلفة.

سادس عشر: المقارنة والتوصية دون الاختيار نيابة عني

يجب أن تعرض المهارة البدائل بوضوح، ولكل اتجاه: نقاط القوة، نقاط الضعف، المخاطر، ما الذي يكسبه، ما الذي يخسره، ولماذا قد يناسب DEIXEN.

ويجب أن تقدم توصية مع توضيح منطقها والأدلة التي تعتمد عليها، دون إعطاء انطباع بوجود "أفضل اتجاه" بلا سبب معروف. التوصية ليست قرارًا نهائيًا، والقرار النهائي لي. لا تستخدم scoring رقميًا أو ترتيبًا شكليًا بديلًا عن التحليل، إلا إذا كان هناك سبب واضح ومبرر. أريد تحليلًا مفيدًا وليس مسابقة تصميم.

سابع عشر: لا تجمّل الاتجاه الحالي

الهدف من الاستكشاف ليس جعل الاتجاه الحالي "أكثر احترافية"، بل معرفة: هل توجد لغة بصرية أقوى أصلًا؟ لذلك يجب أن تعطي المهارة البدائل فرصة حقيقية، وإذا كان هناك اتجاه جديد أقوى من الحالي فيجب أن يكون قادرًا على الظهور. لا تضع البدائل عمدًا في شكل أضعف من الشكل الحالي.

ثامن عشر: اختبار الاتجاهات على DEIXEN الحقيقي

عند مرحلة النماذج، يجب أن تستخدم المهارة محتوى DEIXEN الحقيقي قدر الإمكان، لا صفحات وهمية ولا نصوصًا عامة. يجب أن تختبر قدرة كل اتجاه على التعامل مع: Terminal، أوامر Amadeus، نتائج النظام، الحالات، الأخطاء، التصحيح، التعلم، السيناريوهات، السجلات، وGrowth / Readiness.

العربية والإنجليزية وRTL/LTR جزء حقيقي من اختبار كل اتجاه، وليست قائمة تحقق في النهاية. يجب أن تختبر المهارة كل اتجاه مع: نص عربي، نص إنجليزي، أوامر Amadeus اللاتينية داخل بيئة عربية، الانتقال بين RTL وLTR، والشاشات الصغيرة. أي اتجاه يفشل فقط لأنه صُمم عمليًا لعالم LTR يجب أن تظهر هذه المشكلة بوضوح.

يجب أن يكشف النموذج عن قوة الاتجاه ونقاط ضعفه، لا أن يخفيها وراء mockup جميل.

تاسع عشر: ما أريده منك في نهاية هذه المهمة

أريد إخراجًا منظمًا بهذا التسلسل:

أولًا: ملخص البحث الذي أجريته، مع أفضل المصادر التي وجدتها ولماذا اخترتها، وتوثيق التغطية والتشبع كما في القسم العاشر.

ثانيًا: الدروس والمبادئ التي تستحق دمجها في DEIXEN.

ثالثًا: ما الذي قررت عدم استخدامه ولماذا.

رابعًا: قرارات بنية المهارة بإيجاز: لماذا اخترت هذه الملفات، وما الذي يُحمَّل دائمًا وما الذي يُحمَّل عند الحاجة، وما الذي تحققت منه في مواصفة Agent Skills وClaude Design، وما القيود والخطط البديلة. لا تكرر هنا محتوى الملفات نفسه.

خامسًا: مراجعة نقدية للمهارة نفسها: أين قد تفشل؟ أين قد تدفع Claude إلى حلول نمطية؟ أين يمكن أن تجعل الاستكشاف مكلفًا أو بطيئًا؟ كيف تمنع premature convergence؟ كيف تمنع الوقوع في تصميمات AI الشائعة؟ كيف تمنع العودة إلى تصميم تقليدي قديم؟

سادسًا: النسخة النهائية من المهارة جاهزة للاستخدام، مع نتيجة اختبار بنيتها (ما الأداة التي استُخدمت أو أن التحقق كان يدويًا، وما الأخطاء التي أُصلحت). ملفاتها الكاملة (SKILL.md والملفات المرجعية إن وجدت) تُكتب كملفات إن أمكن في بيئتك، وإلا تُعرض كل ملف في كتلة مستقلة مع مساره. هذه هي المرة الوحيدة التي يظهر فيها نص المهارة كاملًا.

شرط مهم جدًا

لا تنفذ تصميم DEIXEN خلال هذه المهمة. لا تطبق المهارة التي أنشأتها على DEIXEN. لا تبدأ دورة استكشاف فعلية. لا تقترح اتجاهات بصرية لـDEIXEN باعتبارها نتيجة لهذه المهمة. لا تعتبر أي اتجاه تم ذكره أثناء بناء المهارة اتجاهًا معتمدًا. ولا تعدل النظام التصميمي الحالي أو القرارات canonical دون تصريح منفصل.

هذه المهمة تنتهي عند: "امتلاكنا مهارة قوية لاستكشاف هوية واتجاه DEIXEN البصري." وليست عند اختيار التصميم النهائي.

المعيار النهائي للنجاح

المهارة الناتجة يجب أن تساعدني على اكتشاف إجابة قوية لهذا السؤال:

"ما الشخصية البصرية التي يمكن أن تجعل DEIXEN يبدو كمنتج حقيقي قوي ومميز وحديث، وتكون هذه الشخصية نابعة من طبيعة المنتج ومحتواه، وليست مجرد جلد بصري يمكن وضعه فوق أي موقع؟"

وأريد أن تكون قادرة على الوصول إلى إجابات مختلفة فعلًا قبل أن تبدأ في تضييقها.

لا تفترض أن الجمال هو مجرد زخرفة. في DEIXEN، أريد أن تصبح المعلومة، والنظام، والتفاعل، والهوية، وطريقة العرض أجزاء من شيء بصري واحد متماسك.

ابدأ بقراءة مصادر DEIXEN، ثم البحث، ثم التحليل، ثم هندسة المهارة، ثم نقدها، ثم أخرج النسخة النهائية.

IMPORTANT OPERATIONAL BOUNDARY

This is an auxiliary tooling-preparation action after Karim has accepted the Freeze and after Prompt 6 has recorded it in 07, and before Step 4 is prepared. It is NOT a fifth detour step, NOT a new governance stage, and NOT a source of authority.

The accepted Freeze recorded in 07 is canonical. The Skill you build is a tool for later exploration; it must not change, reinterpret, weaken, or widen the Freeze or the recorded Step 4 design scope. Its recommendations are non-binding until Karim decides otherwise through the normal DEIXEN process.

Do not apply the Skill to DEIXEN during this task. Do not choose a DEIXEN visual direction, produce design alternatives for DEIXEN, modify the DEIXEN product, or modify 07, DEIXEN_Execution_Plan.md, or any other canonical DEIXEN document.

Create or update only the Skill artifact in an isolated Skill workspace. If the available environment would require installing or storing the Skill inside a DEIXEN repository or modifying a canonical DEIXEN file, stop and provide the complete install-ready Skill files and the exact intended paths instead of making that mutation.

At the end of this task, stop. Karim will review the Skill artifact and its structural test results separately before the Step 4 preparation session begins.
Karim's STOP after Prompt 7

Review the actual Skill files, its structure, the reported specification test, and the research summary. Confirm that the Skill is reusable, genuinely exploratory, not a hidden design decision, and does not create a second authority system.

Do not proceed to Step 4 preparation until Karim accepts the Skill as a usable tooling artifact.

12. Final Usage Order

The complete workflow from Phase 5 closure through Phase 6. This section maps the artifacts above; it adds no gate and no authority. The one-time package-level review happens before Prompt 1 and before any detour action. The auxiliary Design Exploration Skill build happens after the accepted Freeze is recorded and before Step 4 is prepared, and is not a fifth detour step.

Legend: OWNER = a decision or review by Karim. PREPARATION = a session that only writes a prompt. EXECUTION = a session that carries out a prompt. REVIEW = the one-time bounded Pre-Execution Pre-flight Review (outside the four steps). TOOLING = the auxiliary Skill-build action (outside the four steps). MUTATION = a repository, document, or authorized tooling artifact is changed.

Phase 5 closes. OWNER (Karim's learner test of the slice; closure recorded as 07 D67, 2026-10-02).
The complete v1.8 package, current 07, and current Execution Plan are given to a fresh Opus 5.5 session for the package-level Pre-Execution Pre-flight Review. REVIEW. No mutation, no detour execution.
Karim reviews Opus's review and decides whether to adopt any MUST CHANGE corrections and whether to proceed. OWNER. If the package is materially corrected, the corrected package is the one used thereafter and the affected review point is rechecked before any action. 3a. Prompt 0 checks the practice-run finding of the learner test. EXECUTION (Claude Code, Opus, High). No mutation. If it finds a defect, the fix goes through the usual Phase 5 loop and Karim re-tests that part before Prompt 1. Phase 5 work, not a detour step.
If Karim proceeds, Prompt 1 obtains and verifies the final Phase 5 tag and full SHA. EXECUTION (Claude Code, Effort: Low). MUTATION: the tag is created locally, nothing else.
Karim reviews Prompt 1's tag/SHA result. OWNER. If the final snapshot is not the tested Phase 5 state, stop.
Prompt 2 records the detour governance decision in 07, with [TAG] and [SHA] filled. EXECUTION (Opus, Medium). MUTATION: 07 only. It first checks that Phase 5's closure is recorded in 07 and stops if it is not.
Karim reviews the Prompt 2 result. OWNER. STOP before Prompt 3 if the decision text, decision number, or impact check is not correct.
Prompt 3 updates DEIXEN_Execution_Plan.md (and only what the impact check actually requires), with [N] and [DATE] filled. EXECUTION (Opus, Medium). MUTATION: the Execution Plan and any explicitly flagged files only.
Karim reviews the Prompt 3 diff/result. OWNER. STOP if anything outside the decision's required update was changed.
Step 1 runs in a fresh clean session using Prompt 4 alone and its specified inputs (code at the tag, updated Execution Plan and 07, reference documents). EXECUTION (Opus, Max). No mutation. Output: the Step 1 HANDOFF BLOCK.
Karim reviews the Step 1 HANDOFF BLOCK for completeness, evidence quality, independence, and M1 traceability. OWNER. STOP before Step 2 preparation if the handoff is incomplete or unsafe.
Step 2 is prepared in a fresh preparation session: Prompt 5 + the Step 1 HANDOFF BLOCK + Karim's Phase 5 learner-test record (07 D67 and the test document) + the current Execution Plan and 07 + "Write the prompt for Step 2." PREPARATION (Opus, High). Output: the Step 2 prompt and its preparation note.
Karim reviews the generated Step 2 prompt. OWNER. It must stay inside the Charter before it is sent to the execution session.
Step 2 runs in a fresh execution session using the prepared prompt. EXECUTION (Max). No mutation. Output: the Step 2 HANDOFF BLOCK.
Karim reviews the Step 2 HANDOFF BLOCK. OWNER. STOP before Step 3 preparation if the handoff is incomplete or unsafe.
Step 3 is prepared in a fresh preparation session: Prompt 5 + the Step 1 and Step 2 HANDOFF BLOCKS + the current Execution Plan and 07 + "Write the prompt for Step 3." PREPARATION (High).
Karim reviews the generated Step 3 prompt. OWNER.
Step 3 runs in a fresh execution session using the prepared prompt. EXECUTION (Max). No mutation. Output: the proposed Freeze Package.
Karim reviews the proposed Freeze Package. OWNER. This is the substantive owner review of what may become binding.
Karim explicitly accepts, rejects, or modifies the Freeze Package. OWNER. Nothing binds before this acceptance.
After acceptance, Prompt 6 records the accepted Freeze, design scope and landing times in 07, with [DATE] and [N] filled and the accepted text pasted. EXECUTION (Opus, Medium). MUTATION: 07 only.
Karim verifies that the recorded Freeze, design scope, and landing times in 07 match the accepted Freeze Package. OWNER. STOP if they do not match.
Any changes the Freeze schedules before Step 4 are performed as separate tasks started by Karim. OWNER-started EXECUTION; MUTATION. Step 4 and the Skill build use the resulting current state.
Prompt 7 — Design Exploration Skill Build runs in a fresh Opus 5.5 session. TOOLING (Effort: Max). It researches current methods and Agent Skill / Claude Design constraints, builds the reusable DEIXEN Skill, structurally tests it, and does not apply it to DEIXEN or modify the DEIXEN product/canonical documents.
Karim reviews the Skill artifact and its test/research result. OWNER. STOP before Step 4 preparation if the Skill is incomplete, structurally invalid, improperly scoped, or would create a second authority system.
Step 4 is prepared in a fresh preparation session: Prompt 5 + the accepted Freeze Package (and only that from earlier step outputs) + the updated canonical 07 and Execution Plan + the accepted Skill artifact as a tooling input + "Write the prompt for Step 4." PREPARATION (High).
Karim reviews the generated Step 4 prompt. OWNER. It must explicitly bind itself to the recorded Freeze and its exact design scope, and treat the Skill only as a tool.
Step 4 runs in a fresh execution session with repository access and the ability to run the verification loop. EXECUTION (Opus, Max). MUTATION: isolated and reversible, inside the recorded design scope only.
Within that one Step 4 execution session: inspect -> decide -> implement -> verify -> close. No hidden implementation stage exists after Step 4.
Step 4 produces the Detour Closing Report, which is also its HANDOFF BLOCK.
Karim reviews and accepts or rejects the design changes. OWNER. Accepted design changes join the project by his action.
Remaining accepted engine, learning, or document changes are scheduled as separate implementation tasks according to the Freeze, each started by Karim. OWNER-started EXECUTION; MUTATION.
Karim starts Phase 6. OWNER.

Every prompt produced in a preparation session (items 12, 16, 26) is reviewed by Karim before it is sent to its own fresh execution session. Prompt 7 is reviewed as a tooling artifact, not as a detour step.

If at any point an execution discovers a contradiction or missing prerequisite that the current prompt cannot resolve without changing authority or scope, it stops and reports rather than silently redesigning the process.

13. Preconditions / Gates / Authority

One consolidated view. It restates the Charter and the prompts; it adds no gate and no authority except to describe the owner-authorized auxiliary tooling preparation action for Prompt 7.

13.1 What must exist before each stage
Package-level Pre-Execution Pre-flight Review: the complete package, current 07 and current Execution Plan are available; the review runs before Prompt 1 and before any detour action.
Prompt 0: Phase 5 closure recorded in 07 (Decision 67) and Karim has decided to proceed after the package review.
Prompt 1: Phase 5 closed (07 D67); Prompt 0 reported (b) or (c), or its (a) defect is fixed, merged and re-tested by Karim; Karim has decided to proceed after the package review.
Prompt 2: the tag name and full SHA from Prompt 1, and 07 recording the closure of Phase 5 (Prompt 2 checks this first and stops if it is not recorded).
Prompt 3: the detour decision recorded in 07 as Decision N, Karim's review of Prompt 2's result, and the package-level review already cleared.
Step 1: Prompt 1-3 complete, package review cleared, tag/SHA filled in, updated Execution Plan and 07, and a fresh clean session with code access and web/GitHub access.
Step 2 / Step 3 preparation: the previous HANDOFF BLOCK(S) (Step 2 needs Step 1's, plus Karim's Phase 5 learner-test record, 07 D67; Step 3 needs Step 1's and Step 2's). Execution follows in its own fresh session.
Prompt 6: Karim's explicit acceptance of the Freeze Package (with his changes, if any, in the pasted text).
Prompt 7: the accepted Freeze Package is recorded in 07; any Freeze-scheduled changes required before Step 4 are complete; current 07/Execution Plan and DEIXEN design/product sources are accessible; the target Skill/Claude Design environment is accessible when available; fresh Opus session. If installing the Skill would require mutation of a DEIXEN repo or canonical document, the task stops and returns install-ready files instead.
Step 4 preparation: the canonical Freeze record exists in 07, the pasted accepted Freeze Package matches it, and Karim has accepted the Prompt 7 tooling artifact.
Step 4 execution: the prepared prompt; any change the Freeze schedules before Step 4 already done; the accepted Skill artifact if the prepared prompt uses it; a fresh session with repository access and the ability to run the verification loop.
Phase 6: Karim has reviewed the Detour Closing Report and starts Phase 6 himself.
13.2 Owner authority and step/tool authority
Owner authority. Existing decisions in 07 change only by the owner (governance, D29). The owner starts every step, accepts or rejects what binds, schedules the remaining implementation tasks, accepts the Prompt 7 tooling artifact, and starts Phase 6. The decision to adopt any external code is reserved to the owner.
Steps 1 and 2 recommend within their own domain. Step 3 proposes the Freeze Package. Steps 1, 2 and 3 modify nothing (no code, documents or decisions).
Prompt 7 is an owner-authorized auxiliary tooling preparation action, not a detour step. It may create or update only the reusable Skill artifact in an isolated Skill workspace. It must not modify the DEIXEN application, 07, the Execution Plan, or any canonical DEIXEN decision/design document. Its output is a tool, not authority.
Step 4 improves and verifies the design inside the recorded design scope. It is the only detour step that may implement anything in the DEIXEN product.
Thinking is free; deciding and executing are not. Any step may state requirements and surface non-binding candidates for other steps. It never recommends or decides another step's outcome, and never plans or executes it. Prompt 7 may research and build tooling, but it cannot turn its recommendations into DEIXEN decisions.
Step 1 is advisory. Its Technical Recommendation is not a gate and not a formal independent review.
13.3 What becomes binding, and when
Nothing produced by a detour step binds until Karim explicitly accepts it.
The accepted Freeze Package binds Step 4 and Phase 6.
Its Freeze, design scope and landing times are then recorded in 07 as a decision by Karim. Acceptance and recording are two explicit actions: acceptance is Karim's judgment on the content, recording (Prompt 6) is a verbatim transfer of it.
Prompt 7 does not alter the accepted Freeze and does not create binding design decisions. Karim's acceptance of the Skill means only that the tooling artifact may be used as a preparation aid in Step 4.
Step 4 is prepared and run only after the Freeze record exists in 07 and the Skill artifact has been accepted.
Step 4's design changes are proposals in code form; they join the project only when Karim accepts the Detour Closing Report.
13.4 What is canonical and what is a working copy
Item	Role
07_DEIXEN_Canonical_Decisions_and_Current_State.md	Canonical record of the decisions that belong in 07, including the detour decision and the recorded Freeze, design scope and landing times
DEIXEN_Execution_Plan.md	Canonical execution plan
Detour Charter	Governs the methodology embedded in the prompts; lives inside prompts, not in a repository file
Prompts 1-6	Operational instructions for their respective sessions
Prompt 7 / Design Exploration Skill	Auxiliary tooling preparation; the prompt builds a reusable tool. Neither the prompt nor the Skill is authority
HANDOFF BLOCKS	Carry step outputs forward; working copies
Freeze Package	Step 3's HANDOFF BLOCK; the working copy of the Freeze, design scope and landing times, the canonical copy of which is in 07; it also carries the ledger, requirements, candidates, preserve list and coverage, which are not recorded in 07
This package	Review and transport artifact; no authority
13.5 Step 4 scope and exclusions

Step 4, only after the Freeze Package is accepted and recorded, may implement design changes inside the design scope that package defines.

Design scope = how existing engine and learning outputs are presented: layout, hierarchy, typography, color and semantic-state rendering (styling only), interaction patterns, Terminal presentation (styling and container only), and interface copy = text of the interface itself (navigation, controls, headings, empty and system states) that neither teaches nor carries Amadeus behavior.

Limits that always apply: (1) engine output is rendered exactly as received: no reflow, trimming, re-alignment, truncation or rewording; (2) what the engine receives, and what counts as an attempt, hint, reveal or mastery, is unchanged; (3) when, whether and how much learning support appears (hints, Coach, Ghost Mode, Speed Drills, Scenarios, Assessment) is learning logic, not interaction design; (4) any text that teaches, instructs, hints, explains, assesses or gives feedback is learning content, not interface copy; if unsure, it is learning content.

Excluded: engine behavior, learning logic and content, the wording of verified Amadeus output and training messages (how they are styled is semantic-state rendering, inside the scope), frozen files, governing documents and decisions.

Step 4 may create a new file only if the recorded design scope explicitly names that file; otherwise it edits existing files only. The Freeze Package sets the exact scope inside this definition; only an explicit owner decision can widen it.

The Design Exploration Skill does not widen this scope. Any idea it produces that falls outside the recorded Freeze/design scope remains non-binding and must travel through the Return Path or the normal owner-started pipeline.

13.6 Isolation, reversibility and verification
Step 4 works in isolation and reversibly (for example a separate branch, per CLAUDE.md).
Inside its single execution session Step 4 performs: inspect the current design against the Freeze Package; decide what deserves to change ("no material design change" is a valid result); implement inside the scope; verify the resulting state; close.
Verification runs in every case, including no change: a scope audit of the diff against the recorded design scope, the project's verification loop, a trace of each frozen learner-facing state to its real source, the shared journey on the resulting state, and a short list of what only the owner can judge.
Prompt 7's Skill build is verified separately as tooling: current Skill specification/structure, required files and fields, loading/disclosure behavior as applicable, and any available structural validation. This verification does not substitute for Step 4's product verification.
There is no hidden implementation step after Step 4. Remaining accepted engine, learning and document changes are separate tasks started by Karim on the schedule the Freeze sets.
13.7 Return Path

After the Freeze, if Step 4 needs something outside its authority or something the Freeze lacks, it writes a change request (which must pass the gap test), marks the affected item blocked, and does not fake or work around it. It continues only with items that do not depend on it, or stops if none can continue. Karim decides. One round, affected item only. Before the Freeze, shortfalls travel forward as requirements to Step 3.

If the Design Exploration Skill surfaces a potentially useful idea outside the recorded scope, that does not change the scope. It remains a non-binding tooling output and follows the same owner-controlled return/normal-pipeline path.

13.8 Closing Report requirement

Step 4 ends the detour with a Detour Closing Report, which is also its HANDOFF BLOCK: readiness statement for Phase 6, frozen decisions, design changes made and verified (with branch/commit references and the scope-audit result against the recorded design scope), other accepted changes by landing time, preserved items, coverage ledger, and up to 3 likeliest unverified risks to Phase 6, or none identified. It is traceable from evidence to decision to change to verification. Karim accepts or rejects the design changes, schedules the remaining work, and starts Phase 6.

13.9 Package verification status

This package was constructed from the latest agreed detour design plus the owner-requested auxiliary Design Exploration Skill task. The current DEIXEN_Execution_Plan.md and 07 were not accessible when this package was originally built and must be supplied to the package-level review. No claim of repository-level conformity is made in advance. The package-level review is the place to detect and report any mismatch before any detour action.

14. Known Open Points

Genuinely unresolved and non-blocking at package level. None is intended to stop the package-level review; Opus may independently identify additional issues.

Acceptance of the Closing Report is not recorded in 07 by any prompt. Whether Karim's acceptance of the Detour Closing Report is itself recorded in 07 before Phase 6 remains deliberately deferred. No prompt exists for it; it may follow the same owner-decision pattern later if required.
Operational archiving of HANDOFF BLOCKS and the Freeze Package is not governed. Recorded Freeze decisions cite ledger row IDs that live in the package, not in 07. Any new archive file needs the owner's explicit approval.
07 governance density. Whether Prompt 2 puts too much operational detail into 07, and which of 07 and the Charter prevails if they ever diverge, remains an open governance question; no new precedence rule is introduced here.
Plan status updates. Status updates in DEIXEN_Execution_Plan.md after individual detour stages are routine work unless the actual current plan requires a specific change; no extra governance stage is created for them.
Preparation-session details. Some operational details are deliberately handled when the Step 3 and Step 4 prompts are prepared rather than in the Charter itself: which accepted changes count as "before Step 4"; how the isolated design branch is merged as an owner task; that the readiness statement names any "before Phase 6" change not yet landed; how Step 3 may constrain requirements aimed at Step 4 without deciding them; and that status "confirmed" means evidence-supported, not locked.
Return Path outcome. If a change request leads Karim to change the Freeze, recording that change will require a corresponding owner-reviewed update to the recorded Freeze before Step 4 continues.
Skill storage location. The package deliberately does not hard-code a repository path for the Design Exploration Skill. Prompt 7 must use the target Skill/Claude Design environment when available, or return complete install-ready files rather than mutating a DEIXEN repository.
The approved design and the content files inside Step 4's scope (added in v1.8). tokens.css and the boards are Karim's approved design (07 D42); interface words live in the same content files as the lessons, and those files are byte-identical copies of the knowledge files (07 D28). The Freeze must say explicitly whether Step 4 may change tokens.css, and that any interface-copy change is made in the knowledge copy and the app copy together. Step 3 settles both; until then Step 4 treats both as frozen.
Parts of the learner test not tried (added in v1.8). Karim did not try the hard assessment, the phone widths, reduced motion or the optional checks (07 D67). Step 2 and Step 4 treat them as not covered by learner evidence, not as passed.
Who ran this review (added in v1.8). The package asked for a fresh Opus 5.5 session at Effort Max. The review was run in the project chat that had prepared the learner test (not fresh); it read all three inputs from their current sources. Karim may re-run the review in a fresh session if he wants that independence.
15. What Was Deliberately Preserved from v1.6

Purpose of v1.7: add the owner-authorized Design Exploration Skill preparation action in the correct place after Freeze registration and before Step 4 preparation, without creating a fifth detour step or a second authority system.

Preserved from v1.6 unless explicitly changed below:

Four-step sequence: Engine -> Learning -> Freeze -> Design -> Phase 6.
Pre-execution package review is outside the four steps: it is one bounded package/process review before Prompt 1 and before any detour action, not Step 0, Step 0.5, or a fifth step.
Step 1 independence: no Learning or Design conclusions anchor it; its Design-facing requirements remain a secondary lens only; it is advisory and not a gate; it modifies nothing; Prompt 5 is excluded from its session.
Step 2 and Step 3 have no modification authority.
Freeze Package semantics: Step 3's HANDOFF BLOCK; it carries the Freeze plus what Step 4 and the Closing Report need; Step 4's only earlier-step input is the accepted Freeze Package.
Accepted Freeze + 07 registration before Step 4: Karim accepts; the Freeze, design scope and landing times are recorded in 07; only then is Step 4 prepared and run; the package is the working copy and 07 the canonical copy of those recorded parts.
Step 4 actual implementation + verification inside its single execution session: inspect, decide, implement, verify, close.
Isolation and reversibility of Step 4's work; its changes join the project only when Karim accepts the Closing Report.
No-change neutrality: "Keep as is" and "no change" remain valid at every step.
Candidate freedom: steps may state requirements and surface labeled, non-binding candidates.
Return Path: unchanged in substance.
Canonical 07 versus working package: unchanged.
Prompt 5 remains preparation-only, one step at a time, with no authority to override 07 or the governing Charter.
Prompt 1 and Prompt 3 task text: preserved except for package-level timing notes outside the embedded operational text.
Closing-neutrality wording: "up to 3 likeliest unverified risks, or none identified" is preserved.
M1: preserved and strengthened.
M2: preserved and repeated consistently wherever Step 4 scope is operationally consumed.

Deliberate v1.7 additions:

The complete package now explicitly contains an auxiliary Design Exploration Skill preparation action after the accepted Freeze is recorded and before Step 4 is prepared.
The new action is explicitly not a fifth detour step, not governance authority, and not a source of binding decisions.
Prompt 7 carries the user's full Skill-building prompt, with a narrow operational boundary preventing application of the Skill to DEIXEN during its build and preventing it from widening the recorded Freeze/design scope.
Prompt 7 is isolated, fresh-session, Effort Max tooling work whose only allowed mutation is the Skill artifact in an isolated Skill workspace; it cannot modify DEIXEN's application/canonical repositories.
The Final Usage Order now places Prompt 7 after Freeze registration and any required pre-Step-4 landing work, then requires Karim to review the Skill before Step 4 preparation.
The authority/canonical sections now distinguish the Skill as tooling from the Freeze as authority and Step 4 as the only DEIXEN-product implementation step.
16. Change Ledger
File / section	changed?	exact reason	v1.7 basis
Package title / status	changed	v1.6 -> v1.7; owner-submitted package now includes the auxiliary Design Exploration Skill preparation action	Versioning / process clarity
Section 1 — architecture	changed	explicitly adds the auxiliary Design Exploration Skill preparation action after Freeze registration and before Step 4 preparation, while preserving the four-step architecture	Auxiliary tooling addition
Section 4 — Prompt Roles	changed	adds Prompt 7 with purpose, placement, authority, Effort, attachments, clean-session requirement, and prohibitions	Auxiliary tooling addition
Section 11 — Prompt 7	new	embeds the full owner-supplied Design Exploration Skill-building prompt and adds the narrow tooling/authority boundary required for safe integration	Auxiliary tooling addition
Section 12 — Final Usage Order	changed	places Prompt 7 after accepted Freeze registration and before Step 4 preparation; adds owner review of the Skill artifact	Auxiliary tooling ordering
Section 13 — Preconditions / Gates / Authority	changed	records Prompt 7 as owner-authorized tooling only; keeps Freeze canonical and Step 4 as the only DEIXEN-product implementation step; documents Skill isolation and non-authority	Authority / scope consistency
Section 14 — Known Open Points	changed	records the deliberately unspecified Skill installation location without allowing DEIXEN repository mutation	Operational clarity
Section 15 — Preserved / deliberate changes	changed	records what v1.6 remains intact and what v1.7 adds	Revision traceability
Section 16 — Change Ledger	changed	records v1.7 edits	Revision traceability
Detour Charter	unchanged in substance	the four-step methodology, authority, M1, M2, Return Path, and Closing requirements remain intact; Prompt 7 is explicitly outside the four-step detour	Preserve architecture
Prompts 1-6	unchanged in operational substance	Prompt 7 is added without rewriting the existing step logic; only package-level timing/role notes identify the new ordering	Preserve existing operations
Pre-review corrections (owner-requested, before the Opus 5.5 review)	changed	Sections 1 and 2: shield and review checks now cover Prompt 7; M1/M2 glossed. Section 4 (Prompt 5 attachments), Prompt 5 Briefing item 7: Skill input and tool-only handling for Step 4. Prompt 2: Phase 5 closure check is an explicit stop; Step 4 scope text recorded word for word. Prompt 6 item 3: scope check references Decision [N]. Sections 12.6 and 13.1: Phase 5 closure precondition. No change to the Charter, the four-step architecture, or any authority rule	Package consistency
v1.8 — Opus 5.5 pre-execution review (2026-10-02)	changed	the six corrections of Section 17 (C1–C6) adopted; three open points added to Section 14	Pre-execution review
17. Corrections in v1.8 (from the Opus 5.5 pre-execution review, 2026-10-02)

Verdict on v1.7: NO-GO as written, GO with these six corrections (C1–C6). All six are applied above; nothing else in the method, the four steps, M1, the no-change rule, the acceptance order, Step 4's authority, Prompt 5's preparation-only status, the Prompt 7 boundary or the Return Path was changed.

#	Where (v1.7)	Problem	Consequence if left	Correction (v1.8)
C1	§1 "Phase 5 closure versus snapshot fixation"; §12 item 1; §13.1; Prompt 2 item 4	The package treats Phase 5 as closed, but no record of the closure existed: Karim's learner-test verdict was "works, but fix first", and no prompt records the closure	Prompt 2 stops at its own item 4 with nothing that can unblock it, or the detour starts on an unrecorded gate	Karim decided to close Phase 5 now and carry the findings into the detour; recorded as 07 D67; §1, §12, §13.1 updated
C2	Missing	One finding (the practice booking reported lost) may be a defect, and Prompt 1 would freeze it into the snapshot all four steps examine	Step 1 and Step 2 analyse a known-suspect build, or a defect reaches Phase 6	New Prompt 0 (Phase 5 work, read-only check) before Prompt 1; a defect is fixed and re-tested before the tag
C3	Prompt 1; §4 Prompt 1; §12 item 4	deixen-app has no remote (.git/config has no [remote]), but Prompt 1 requires "all commits pushed" and pushes the tag; and it did not name which commit Karim tested	Prompt 1 stops at step 1 every time, or a session adds a remote to make it pass	Tag created locally; no push; the tested commit named (3fdb342, step-7-pass, 07 D65, or a re-tested Prompt 0 fix)
C4	§4 Prompt 4 attachments; Prompt 4 precondition 1	"the deixen-app code at that tag" cannot be attached from GitHub; access is only through Karim's linked computer	Step 1's precondition fails or it reads a later state than [SHA]	Read-only through the connected folder; the session confirms tag and HEAD point to [SHA], else stops
C5	Charter AUTHORITY "Excluded" (three copies), Prompt 2, §13.5	"Excluded: … verified Amadeus output and training messages" reads as excluding their styling too, while the scope includes "semantic-state rendering"	Karim's main design finding (a correct RF entry looked like an error because training lines look alike) could not be addressed by Step 4	Clarified everywhere M2 appears: their wording is excluded; how they are styled is semantic-state rendering, in scope
C6	§4 Prompt 5 attachments; Briefing Step 2 and "How to write" item 1; §12 item 12; §13.1	Karim's learner-test findings — the only evidence from a real beginner — had no way into the detour	The most important evidence for Step 2 is lost (information loss), or enters as a second ID system	Step 2 receives the learner-test record (07 D67 and the test document); each note becomes one S2 row; no new identifier system
