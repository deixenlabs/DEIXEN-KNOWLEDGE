UNIVERSAL AI SESSION HANDOFF PROTOCOL

MASTER v4 — DEIXEN ALIGNED PROPOSED DRAFT — NOT YET CANONICAL

Alignment Note

This revision preserves the handoff protocol's original purpose as a loss-minimizing continuity and state-transfer mechanism while aligning its governance behavior and vocabulary with:

- "08 — DEIXEN AI Working Rules & Development Process"
- "DEIXEN Prompt Engineering & Governance"

This document does not replace either governance owner document.

It does not create a new authority hierarchy.

It does not define a competing decision taxonomy.

It does not turn the handoff into a project-truth source merely because it is newer.

Its purpose is to transfer the strongest truthful session state while preserving authority, provenance, uncertainty, currentness, scope, review status, and next action.

---

0. PURPOSE

This document is a loss-minimizing session handoff protocol.

Its purpose is to transfer the exact operational state of a previous session to another AI, model, agent, tool, developer, or future session without losing material context.

The handoff must preserve, where relevant:

- project state;
- phase and gate position;
- decisions;
- unresolved questions;
- evidence;
- provenance;
- negative findings;
- assumptions;
- rejected directions;
- version/currentness context;
- dependencies;
- ownership;
- pending reviews;
- blockers;
- artifact changes;
- authority boundaries;
- execution authorization;
- and the exact next action.

This is NOT merely a conversation summary.

It is a continuity and state-transfer artifact.

The goal is not to make the receiving system "feel" as though it remembers the previous session.

The goal is to make the receiving system capable of reconstructing the strongest truthful state of the project with minimal risk of misunderstanding.

The handoff is a state-transfer mechanism, not a source of authority by itself.

---

1. RECEIVING SYSTEM — NON-NEGOTIABLE RULES

The receiving system MUST reconstruct the previous session before performing substantive work.

Before acting, it must identify, where materially relevant:

- the current project phase;
- the current primary task;
- the work-task classification;
- the applicable execution-authorization mode;
- the currently assigned role;
- the role's authority boundary;
- whether independent review is required;
- whether a reviewer is distinct from the approver;
- and whether a recommendation in the handoff is merely consultative input or an actual decision already issued by the responsible authority.

Do NOT:

- restart the project from scratch;
- assume missing information is unimportant;
- silently invent missing information;
- silently infer facts and present them as facts;
- silently reconcile conflicting information;
- silently promote recommendations into decisions;
- silently promote session decisions into canonical truth;
- silently treat drafts as final;
- silently treat historical material as current;
- silently treat model agreement as evidence;
- silently revive superseded decisions;
- silently widen execution scope;
- silently convert a review request into an implementation request;
- silently convert an implementation request into permission to redesign;
- or claim work was completed when it was only discussed, proposed, or partially performed.

Do NOT reopen a protected/approved decision unless a valid reopening trigger exists under the project's applicable governance.

Do NOT use "common sense", generic domain knowledge, memory, or model intuition to fill a material knowledge gap when the project requires evidence.

When evidence is insufficient:

«Preserve the unknown.»

When sources genuinely conflict:

«Preserve the conflict until authority, context, version, scope, and evidence resolve it.»

When an inference is necessary:

«Label it explicitly as an inference.»

An inference must never silently become a verified fact.

1.1 Consultative Input Principle

A recommendation from Karim, ChatGPT, Sonnet, Opus, Claude, a reviewer, a developer, or any other participant is consultative input unless it is itself an explicit decision issued by the authority responsible for that decision.

The receiving system must independently evaluate consultative input against, as applicable:

- current evidence;
- authoritative project sources;
- current decisions;
- task scope;
- constraints;
- dependencies;
- project intent;
- current implementation state;
- relevant risks;
- and contradictory evidence.

The receiving system may:

- accept;
- refine;
- reject;
- defer;
- or escalate

the recommendation.

The purpose of independence is not reflexive disagreement.

The purpose is to prevent blind acceptance.

A strong recommendation should be accepted when independent evaluation supports it.

A recommendation should not be rejected merely because it came from another agent.

1.2 Required Governance Distinctions

Do not confuse:

- role with model;
- model with product surface;
- capability with authority;
- work-task classification with execution authorization;
- evidence with approval;
- current operating source with final canonical approval;
- reviewer with approver;
- recommendation with decision;
- decision with execution request;
- execution request with permission to redesign;
- implementation verification with domain validation;
- documentation with empirical proof;
- or handoff recency with project-truth authority.

---

2. SESSION-STATE AUTHORITY VS PROJECT-TRUTH AUTHORITY

This distinction is mandatory.

SESSION-STATE AUTHORITY

The handoff is authoritative for reporting:

- what happened in the previous session;
- what was discussed;
- what was attempted;
- what changed;
- what remained open;
- what was rejected;
- what is pending;
- what was inspected;
- what was not inspected;
- what the previous session concluded;
- and what the previous session believed or decided.

PROJECT-TRUTH AUTHORITY

Canonical project artifacts and appropriately verified evidence remain authoritative for actual project truth according to the project's declared authority model.

Therefore:

«A handoff is authoritative for session state but is NOT automatically authoritative for canonical project truth.»

A handoff does not override canonical knowledge merely because it is newer.

A new fact may justify updating canonical knowledge.

A new opinion does not.

A recommendation may be recorded as consultative input without creating project authority.

A new explicit decision may be recorded in the handoff, but it does not become canonical merely because the handoff is newer. Its canonical status remains governed by the project's actual canonicalization process.

A handoff therefore records the delta between session state and project state; it does not silently erase that distinction.

---

3. CONFLICT RESOLUTION PROTOCOL

When the handoff conflicts with a project artifact:

1. Identify the exact conflict.
2. Identify the conflicting claims, decisions, or instructions.
3. Identify the authority level of each source.
4. Check version, date, context, scope, and supersession.
5. Determine whether the handoff contains:
   - new evidence;
   - a new decision;
   - an interpretation;
   - a recommendation;
   - an execution result;
   - or unsupported opinion.
6. Determine whether the apparent conflict is actually a mismatch of classification rather than a true contradiction.
7. Apply the project's declared governance, including:
   - source authority;
   - decision authority;
   - role authority;
   - execution authorization;
   - and any required independent-review gate.
8. Record the conflict and required resolution.
9. Do not promote unresolved material into canonical truth.
10. Do not treat a recommendation, review finding, execution request, or session conclusion as an approved decision merely because it appears in a newer handoff.

When the project authority model itself is unclear:

«Do not invent a hierarchy. Flag the ambiguity.»

When two sources are genuinely equal in authority and incompatible:

«Preserve the conflict and escalate to the appropriate authority.»

Never resolve conflict merely by:

- recency;
- model prestige;
- confidence;
- verbosity;
- repetition;
- or apparent sophistication.

---

4. RECEIVING SYSTEM PRE-FLIGHT

Before substantive work, verify:

Context Availability

[ ] Handoff is available.
[ ] Relevant project files are available.
[ ] Relevant repository/code is available, if required.
[ ] Relevant evidence sources are available, if required.
[ ] Required external inputs are available, if applicable.

Context Integrity

[ ] Current phase is identifiable.
[ ] Current task is identifiable.
[ ] Work-task classification is identifiable where relevant.
[ ] Execution-authorization mode is identifiable where relevant.
[ ] Assigned role is identifiable where relevant.
[ ] Authority boundary is identifiable.
[ ] Relevant source-of-truth artifacts are identifiable.
[ ] Open decisions are identifiable.
[ ] Pending reviews are identifiable.
[ ] Independent-review requirement is identifiable where applicable.
[ ] Reviewer and approver are distinguishable where material.
[ ] Material blockers are identifiable.
[ ] Material session deltas are identifiable.

If a required input is missing:

MISSING INPUT:
[WHAT]

IMPACT:
[WHAT CANNOT SAFELY BE DETERMINED]

REQUIRED SOURCE / ACTION:
[WHAT IS NEEDED]

Do not silently reconstruct missing material.

---

5. PROJECT IDENTITY

Project:
[PROJECT NAME]

Primary Objective:
[PRECISE OBJECTIVE]

Current Overall Mission:
[CURRENT MISSION]

Current Phase:
[PHASE]

Current Sub-Phase / Pass:
[SUB-PHASE]

Current Workstream:
[RESEARCH / KNOWLEDGE / DESIGN / ENGINE / CURRICULUM / AUDIT / IMPLEMENTATION / TESTING / OTHER]

Session Date:
[ABSOLUTE DATE]

Timezone / Relevant Temporal Context:
[TIMEZONE]

Previous Relevant Session:
[REFERENCE]

Handoff Version:
[VERSION]

Source Handoff Version:
[PREVIOUS HANDOFF VERSION, IF APPLICABLE]

Canonical Project Version / Revision:
[VERSION / COMMIT / DATE, IF APPLICABLE]

Note:

The handoff version identifies the continuity artifact.

It does not by itself establish the project version or canonical project state.

---

6. PROJECT STATE — EXACT CURRENT POSITION

Use explicit state labels.

✅ COMPLETE

[WHAT IS ACTUALLY COMPLETE]

🟢 APPROVED / CONFIRMED / PROTECTED

[WHAT IS SETTLED OR PROTECTED FROM REOPENING]

🟡 IN PROGRESS

[WHAT IS CURRENTLY BEING WORKED ON]

🟠 PENDING REVIEW

[WHAT IS WAITING FOR REVIEW OR APPROVAL]

🔴 BLOCKED

[WHAT CANNOT SAFELY PROCEED]

⚪ NOT STARTED

[WHAT HAS NOT BEGUN]

⛔ DO NOT START YET

[DOWNSTREAM WORK THAT MUST WAIT]

⛔ DO NOT REOPEN

[APPROVED / PROTECTED MATTERS THAT MUST REMAIN CLOSED UNLESS A VALID REOPENING TRIGGER EXISTS]

"LOCKED" may be used as operational shorthand for a protected matter in a handoff, but it is not a replacement for the shared decision-state vocabulary.

Use the actual decision state separately.

Never infer completion from:

- file existence;
- draft existence;
- discussion;
- prototype existence;
- model output;
- planned work;
- or intention.

Completion must be supported by the relevant project criteria.

---

7. PHASE / GATE POSITION

Master Sequence:
[PHASE A → PHASE B → PHASE C → ...]

Current Phase:
[CURRENT]

Entry Conditions:
[WHAT HAD TO BE TRUE]

Current Objective:
[WHAT THIS PHASE MUST ACHIEVE]

Exit Conditions:
[WHAT MUST BE TRUE]

Current Gate:
[OPEN / PASSED / PENDING / BLOCKED]

Gate Evidence:
[WHAT PROVES THE STATUS]

Gate Authority / Reviewer:
[WHO / ROLE]

Execution-Gating Requirement:
[IF ANY]

Do not declare a phase complete because work merely occurred.

Completion requires satisfaction of its actual exit conditions.

A review finding is not itself proof that a phase passed.

A model declaration is not itself proof that a gate passed.

---

8. AUTHORITY MODEL

State the project's actual authority model for the current task.

Do not force the model into one simple linear hierarchy when the project distinguishes different kinds of authority.

Keep separate, where relevant:

- source / claim authority;
- decision authority;
- role authority;
- execution authorization;
- review authority;
- domain authority;
- canonical-state authority;
- human-owner authority.

Relevant Roles

Where applicable:

Reviewer / Advisor
Evaluates, challenges, finds risks, and recommends. Does not become the decision-maker merely by making a recommendation.

Responsible Expert / Decision Partner
Independently evaluates material input against the owning domain's evidence, authority, constraints, and objective, then acts within delegated authority.

Human Product Owner
Retains authority over decisions explicitly reserved to human ownership.

Independent Final Reviewer
Performs a required independent review. Does not automatically become the approver.

Design Executor
Executes approved design direction within scope.

Implementation Executor
Implements approved technical direction within scope.

Role authority attaches to the role, not to a model name or product surface.

Authority by Domain

Amadeus / Domain:
[AUTHORITY]

Technical:
[AUTHORITY]

Product:
[AUTHORITY]

Learning / Curriculum:
[AUTHORITY]

Visual / Design:
[AUTHORITY]

Implementation:
[AUTHORITY]

User-Owned Decisions:
[AUTHORITY]

Decision Authority for Current Task:
[WHO / ROLE]

Execution Authorization for Current Task:
[MODE / ROLE / SCOPE]

Review Authority:
[WHO / ROLE]

Required Independent Review:
[YES / NO / WHO / WHY]

Execution-Gating Authority, If Any:
[WHO / ROLE]

If no authority has been defined for a material decision type:

«Mark it as undefined rather than inventing one.»

---

9. SOURCE-OF-TRUTH INVENTORY

For each relevant artifact:

File / Artifact:
"filename"

Exact Path / Location:
[path]

Purpose / Role:
[WHAT IT CONTROLS]

Authority:
[CANONICAL / PRIMARY / OPERATING SOURCE / REFERENCE / WORKING / OUTPUT / HISTORICAL / ARCHIVE]

Status:
[APPROVED / PENDING / DRAFT / FROZEN / SUPERSEDED / OBSOLETE]

Owner:
[PERSON / ROLE / TEAM]

Review Authority:
[WHO / ROLE]

Version / Revision:
[VERSION / DATE / COMMIT]

Last Relevant Change:
[WHAT]

May Be Modified Under Current Authorization?:
[YES / NO / AUTHORIZATION CONDITION]

Can Override Other Artifacts?:
[YES / NO / ONLY WITH DECLARED AUTHORITY]

Supersedes:
[WHAT, IF ANY]

Superseded By:
[WHAT, IF ANY]

Known Conflicts:
[IF ANY]

Canonicalization Required?:
[YES / NO]

Important:

A handoff may identify an artifact as the current operating source without thereby declaring it permanently canonical.

Likewise, an artifact may be canonical without being the operative source for every task.

---

10. CLAIM, DECISION, AUTHORITY, VALIDATION, AND CURRENTNESS STATUS

Do not collapse independent classification axes into one status label.

Use only the dimensions needed to prevent materially misleading interpretation.

10.1 Epistemic / Claim Status

Where relevant:

- "FACT / OBSERVED"
- "SUPPORTED / DOCUMENTED"
- "EVIDENCED INFERENCE"
- "HYPOTHESIS"
- "UNKNOWN"

10.2 Decision / Lifecycle Status

Use the shared vocabulary owned by the AI Working Rules:

- "CONFIRMED"
- "APPROVED"
- "OPEN"
- "NEEDS VALIDATION"
- "PROPOSED"
- "PLANNED"
- "DEFERRED"
- "REJECTED"

Do not invent a competing decision-state taxonomy for the handoff.

10.3 Output-Type Status

Where useful:

- "FACT / CANONICAL"
- "OPEN QUESTION"
- "REVIEW FINDING"
- "RECOMMENDATION"
- "EXECUTION REQUEST"
- "EXECUTED CHANGE"

Output type does not create decision authority.

10.4 Authority / Ownership

Record:

- who owns the claim;
- who owns the decision;
- who owns review authority;
- who owns execution authority.

10.5 Validation Status

Where material:

- implementation verification;
- Amadeus/domain/SME validation;
- external validation;
- real-learner validation;
- or another explicitly defined validation path.

10.6 Currentness / Lifecycle

Record whether information is:

- current;
- historical;
- version-specific;
- superseded;
- context-bounded;
- or unknown.

Do not let:

"APPROVED"

"CURRENT"

"REJECTED"

or

"HISTORICAL"

masquerade as proof of epistemic truth.

Likewise:

"IMPLEMENTED"

does not automatically mean:

"DOMAIN VALIDATED"

and:

"DESIGNED"

does not automatically mean:

"EFFECTIVE"

---

11. CURRENTNESS / VERSION / CONTEXT SAFETY

For any version-sensitive, time-sensitive, market-sensitive, airline-sensitive, environment-sensitive, or product-sensitive item:

Claim:
[CLAIM]

Applicable Version / Release:
[VERSION]

Date / Period:
[DATE / PERIOD]

Environment:
[ENVIRONMENT]

Market / Geography:
[MARKET]

Airline / Carrier Context:
[AIRLINE, IF APPLICABLE]

Current / Historical / Unknown:
[STATUS]

Supersedes:
[WHAT]

Superseded By:
[WHAT]

Scope:
[WHERE IT APPLIES]

Do not silently merge:

- old and new syntax;
- old and new workflows;
- legacy and current behavior;
- different environments;
- different markets;
- different airline configurations;
- different product versions;
- different repository revisions;
- or different project phases.

When temporal or contextual conflict exists, explain it rather than averaging the sources.

---

12. SESSION DELTA — WHAT CHANGED?

This section is mandatory.

Record material changes relative to the previous known state.

For each:

Delta ID:
[Δ-XXX]

Previous State:
[OLD]

New State:
[NEW]

Change Type:
[FACT / DISCOVERY / CORRECTION / DECISION / RECOMMENDATION / REJECTION / ARTIFACT CHANGE / EXECUTION RESULT]

Epistemic Status:
[STATUS, IF APPLICABLE]

Decision Status:
[STATUS, IF APPLICABLE]

Origin:
[WHERE THE CHANGE CAME FROM]

Evidence / Basis:
[WHAT SUPPORTS IT]

Authority:
[WHO / ROLE]

Execution Authorization:
[IF APPLICABLE]

Canonicalized?:
[YES / NO]

Validation Status:
[STATUS, IF APPLICABLE]

Downstream Impact:
[WHAT CHANGES]

Follow-Up Required:
[YES / NO]

The delta section exists to prevent important changes from being lost in long conversations.

A delta records change.

It does not by itself establish approval, canonicalization, or validation.

---

13. DECISION LINEAGE / PROVENANCE

For every material decision or change, preserve its lineage.

Keep the following separate:

- epistemic status;
- decision status;
- authority;
- execution authorization;
- validation status;
- canonicalization status.

Provenance records process and history.

It does not itself prove correctness or create authority.

For each:

Lineage ID:
[L-XXX]

Originating Session / Source:
[WHERE IT STARTED]

Source Artifact:
[FILE / CODE / REVIEW / RESEARCH]

Finding / Issue ID:
[ID, IF ANY]

Evidence ID:
[E-XXX, IF ANY]

Reviewer / Model / Role:
[WHO / ROLE]

Consultative Input Received?:
[YES / NO]

Responsible Expert / Decision Partner:
[WHO / ROLE]

User Decision:
[IF APPLICABLE]

Resulting Decision:
[WHAT WAS DECIDED]

Decision Status:
[CONFIRMED / APPROVED / OPEN / NEEDS VALIDATION / PROPOSED / PLANNED / DEFERRED / REJECTED]

Resulting Change:
[WHAT CHANGED]

Execution Authorization:
[IF APPLICABLE]

Canonical Target:
[FILE / NONE]

Canonicalization Status:
[CANONICAL / PENDING CANONICALIZATION / NOT APPLICABLE]

Validation Status:
[STATUS]

This section preserves the chain:

«source → evidence/finding → independent evaluation → decision authority → decision → authorized execution → verification → canonicalization»

Not every item will contain every stage.

---

14. APPROVED / PROTECTED DECISIONS

This section preserves decisions that the receiving system should treat as closed/protected against casual reopening.

"Protected" is an operational handoff property.

It is not a replacement for the project's shared decision-state vocabulary.

For each:

Decision ID:
[D-XXX]

Exact Decision:
[PRECISE STATEMENT]

Decision Type:
[DOMAIN / TECHNICAL / PRODUCT / VISUAL / LEARNING / OTHER]

Reason:
[WHY]

Evidence / Basis:
[SUPPORT]

Authority:
[WHO / ROLE]

Decision Status:
[CONFIRMED / APPROVED]

Protected From Reopening?:
[YES / NO]

Date:
[DATE]

Canonicalized?:
[YES / NO]

Canonical Location:
[FILE / SECTION]

Supersedes:
[PREVIOUS DECISION, IF ANY]

Superseded By:
[NONE / DECISION ID]

Reopening Allowed?:
[YES / NO]

Valid Reopening Trigger:
[WHAT WOULD JUSTIFY REOPENING]

A protected decision must not be reopened merely because another AI proposes an alternative.

A valid reopening trigger must come from the project's applicable governance, not from the existence of a new model output alone.

---

15. OPEN DECISIONS

For each unresolved material decision:

Issue ID:
[U-XXX]

Exact Question:
[QUESTION]

Known Options:
[OPTIONS]

Arguments For:
[SUMMARY]

Arguments Against:
[SUMMARY]

Current Leaning:
[OPTIONAL — CONSULTATIVE ONLY]

What Is Unknown:
[EXACT GAP]

Required Evidence:
[WHAT WOULD RESOLVE IT]

Decision Authority:
[WHO / ROLE]

Required Independent Review?:
[YES / NO]

Execution-Gating Requirement?:
[YES / NO]

Status:
"OPEN"

"OPEN" means unresolved.

Do not choose a winner merely because one option is more convenient.

A model's confidence does not close an open decision.

---

16. USER-OWNED DECISIONS

Record decisions reserved for explicit human authority.

Decision / Question:
[WHAT]

Why User Authority Is Required:
[WHY]

Current Status:
[PENDING USER DECISION]

Options:
[OPTIONS]

Recommendation, If Any:
[RECOMMENDATION — CONSULTATIVE INPUT ONLY]

User Decision:
[EXPLICIT DECISION, IF ACTUALLY ISSUED]

Execution Authorization:
[IF APPLICABLE]

Never convert a recommendation into user approval.

Never treat a user's suggestion as an explicit final decision on a human-owned matter unless the user actually issued that decision.

Conversely, when Karim explicitly makes a decision in a domain reserved to human-owner authority, that decision is a decision—not merely a recommendation.

Faithful execution of such a decision still remains subject to:

- scope;
- safety;
- factual constraints;
- technical feasibility;
- and any separately required gate.

---

17. NEW INFORMATION INTRODUCED THIS SESSION

Separate all new material.

A. FACTS / OBSERVED

[FACTS]

B. DOCUMENTED / SUPPORTED CLAIMS

[CLAIMS]

C. INTERPRETATIONS / ANALYSIS

[INTERPRETATIONS]

D. EVIDENCED INFERENCES

[INFERENCES]

E. HYPOTHESES

[HYPOTHESES]

F. RECOMMENDATIONS / CONSULTATIVE INPUT

[RECOMMENDATIONS]

G. DECISIONS

[DECISIONS]

H. REJECTIONS

[REJECTIONS]

I. UNKNOWN / NOT ESTABLISHED

[UNKNOWN]

Never merge these categories.

A recommendation does not become a decision merely because it appears in a "new information" section.

---

18. EVIDENCE REGISTER

For each material claim:

Evidence ID:
[E-XXX]

Claim:
[CLAIM]

Evidence Source:
[OFFICIAL DOC / FILE / CODE / TEST / SCREENSHOT / OBSERVATION / RESEARCH / OTHER]

Exact Reference:
[PATH / SECTION / LOCATION]

Evidence Type:
[DOCUMENTED / OBSERVED / OTHER]

Version / Context:
[VERSION / MARKET / AIRLINE / ENVIRONMENT]

Evidence Strength:
[HIGH / MEDIUM / LOW]

Independent Corroboration?:
[YES / NO]

Known Conflicts:
[IF ANY]

Current Status:
[VERIFIED / PARTIAL / UNVERIFIED / CONFLICTED]

Validation Requirement Remaining:
[IF ANY]

Repeated agreement between AI systems is NOT independent evidence.

A review conclusion is not automatically independent evidence.

A document's existence is not automatically evidence that its claims are true.

---

19. NEGATIVE KNOWLEDGE

Preserve meaningful negative findings.

Record items that were:

- searched for and not found;
- investigated and unsupported;
- explicitly rejected;
- disproven;
- superseded;
- historical only;
- outside project scope;
- cross-domain contamination;
- not established as current;
- or inaccessible despite attempts to inspect them.

For each:

Negative Finding ID:
[N-XXX]

Question / Claim:
[WHAT WAS INVESTIGATED]

Sources Checked:
[SOURCES]

Result:
[NOT FOUND / UNSUPPORTED / REJECTED / OBSOLETE / UNKNOWN / OUT OF SCOPE / CONFLICTED]

Confidence:
[HIGH / MEDIUM / LOW]

Implication:
[WHAT FUTURE SYSTEMS MUST NOT ASSUME]

Negative knowledge is first-class project context.

Do not store only successful findings.

"Not found" does not necessarily mean "does not exist."

It means only what the evidence actually supports.

---

20. ARTIFACT CHANGES

For each changed artifact:

Artifact:
[FILE / CODE / DESIGN / RULE]

Previous Version / State:
[OLD]

New Version / State:
[NEW]

Reason:
[WHY]

Evidence / Basis:
[BASIS]

Decision / Authorization Basis:
[APPROVED DECISION / CONDITIONAL ACCEPTANCE / OTHER]

Decision Authority:
[WHO / ROLE]

Execution Authorization:
[MODE / ROLE / SCOPE]

Verification Performed?:
[YES / NO]

Validation Status:
[STATUS, IF MATERIAL]

Canonicalized?:
[YES / NO]

Remaining Migration:
[WHAT]

An artifact change does not automatically prove:

- decision approval;
- domain correctness;
- canonical status;
- or learning effectiveness.

---

21. WORK COMPLETED THIS SESSION

Record only work that was actually completed.

For each:

Action:
[WHAT WAS DONE]

Result:
[OUTCOME]

Artifact Affected:
[WHAT]

Evidence of Completion:
[WHAT PROVES IT]

Verification Performed:
[WHAT]

Status:
"COMPLETE"

Do not classify any of the following as completed:

- ideas;
- intentions;
- drafts;
- proposed changes;
- discussions;
- recommendations;
- partial edits;
- or tasks awaiting verification.

"Implemented" may be recorded as an artifact result without implying that the underlying decision or domain behavior is validated.

---

22. WORK ATTEMPTED BUT NOT COMPLETED

For each:

Task:
[WHAT]

Partial Result:
[WHAT WAS ACHIEVED]

Why Incomplete:
[REASON]

Remaining Work:
[WHAT]

Risk / Impact:
[IMPACT]

Current Decision Status:
[STATUS, IF APPLICABLE]

Execution Authorization Remaining:
[IF APPLICABLE]

---

23. REJECTED PROPOSALS / FAILED DIRECTIONS

For each:

Proposal:
[WHAT]

Rejected Because:
[WHY]

Evidence / Reasoning:
[BASIS]

Decision Status:
"REJECTED"

Can Be Reconsidered?:
[YES / NO]

Valid Reconsideration Trigger:
[WHAT]

Never re-propose a rejected direction without addressing the original rejection reason.

A renamed or cosmetically altered version of a rejected idea remains rejected unless a valid reopening trigger exists.

---

24. OPEN ISSUES / RISKS / BLOCKERS

For each:

Issue ID:
[I-XXX]

Problem:
[WHAT]

Impact:
[WHY IT MATTERS]

Severity:
[P0 / P1 / P2 / P3]

Epistemic Status:
[FACT / INFERENCE / HYPOTHESIS / UNKNOWN]

Evidence:
[BASIS]

Current Status:
[OPEN / INVESTIGATING / BLOCKED / PENDING REVIEW / NEEDS VALIDATION]

Owner:
[WHO / ROLE]

Decision Authority:
[WHO / ROLE]

Next Action:
[EXACT ACTION]

Blocking Downstream Work?:
[YES / NO]

Independent Review Required?:
[YES / NO]

---

25. PENDING REVIEWS / APPROVALS

For each:

Artifact / Decision:
[WHAT]

Reviewer Role / Person / Model:
[WHO / ROLE]

Assigned Role:
[ROLE]

Review Type:
[ADVERSARIAL / TECHNICAL / FACTUAL / CURRICULUM / DESIGN / LEARNING / OTHER]

Independent Review Required?:
[YES / NO]

Independent Reviewer Assigned By:
[WHO / WORKFLOW]

Decision Authority / Approver:
[WHO / ROLE]

Execution-Gating Authority, If Any:
[WHO / ROLE]

Status:
"PENDING"

Exact Review Question:
[QUESTION]

Review Object:
[WHAT MUST BE EVALUATED]

Required Inputs:
[WHAT]

Acceptance Criteria:
[CRITERIA]

Clean-Review Requirement:
[YES / NO / CONDITIONS]

What Happens After Review:
[NEXT GATE]

Reviewer status does not automatically confer approval authority.

A reviewer's finding may block progression when the governing workflow defines the review as execution-gating.

That does not make the reviewer the universal source of truth.

---

26. TEMPORARY ASSUMPTIONS

For each:

Assumption ID:
[A-XXX]

Assumption:
[WHAT]

Why Needed:
[WHY]

Verified?:
"NO"

Epistemic Status:
"HYPOTHESIS / UNKNOWN"

Risk If Wrong:
[IMPACT]

Validation Method:
[HOW]

Expiry / Review Trigger:
[WHEN]

Temporary assumptions must never silently become canonical facts.

An assumption used for execution must remain visibly distinguishable from a verified project decision.

---

27. TERMINOLOGY CONTROL

For each important project-specific term:

Term:
[TERM]

Exact Project Meaning:
[DEFINITION]

Do Not Interpret As:
[WRONG INTERPRETATION]

Canonical Location:
[FILE]

Owning Artifact:
[FILE / SOURCE]

Currentness:
[CURRENT / HISTORICAL / VERSION-SPECIFIC]

This prevents terminology drift between sessions, models, and tools.

Do not introduce a local synonym for a governed term when doing so could create authority or semantic ambiguity.

---

28. CONSTRAINTS

Classify each constraint as one of:

🔒 NON-NEGOTIABLE

Must be respected unless formally changed.

🟡 CURRENT PREFERENCE

Can change if evidence or a better decision justifies it.

🟠 TEMPORARY

Applies only to the current phase, review, or task.

For each:

Constraint:
[WHAT]

Type:
[TYPE]

Reason:
[WHY]

Authority:
[WHO / ROLE]

Scope:
[WHERE IT APPLIES]

Do not convert a preference into a hard rule without explicit authority.

Do not convert a temporary phase constraint into a permanent architecture rule.

---

29. DEPENDENCY MAP

For every material dependency:

Upstream:
[X]

Downstream:
[Y]

Blocked Until:
[CONDITION]

Example:

«Evidence
→ Knowledge
→ Decision
→ Curriculum / Learning Design
→ Experience Architecture
→ Design
→ Implementation
→ Verification»

Do not perform downstream work while a required upstream gate remains unresolved.

Do not infer that a dependency is resolved merely because work downstream has already begun.

---

30. CURRENT PRIMARY TASK

There must be ONE primary task.

Supporting verification or sub-tasks may exist, but they must not obscure the primary objective.

The handoff must distinguish what the work is from what the receiving system is authorized to do with it.

Primary Task:
[EXACT TASK]

Work-Task Classification:
[RESEARCH / EXTRACTION / COMPARISON / SYNTHESIS / CURRICULUM / LEARNING DESIGN / PRODUCT DECISION ANALYSIS / UX CRITIQUE / VISUAL EXPLORATION / IMPLEMENTATION / DEBUGGING / TESTING / AUDIT / ADVERSARIAL REVIEW / DECISION ARBITRATION / CANONICALIZATION PREPARATION / DOCUMENTATION / HANDOFF / OTHER]

Execution-Authorization Mode:
[DISCUSSION / RECOMMENDATION / REVIEW / AUDIT / RECOMMENDATION + CONDITIONAL EXECUTION / EXECUTION / OTHER]

Assigned Role:
[ROLE]

Objective:
[DESIRED RESULT]

Inputs:
[FILES / SOURCES / CODE]

Required Output:
[DELIVERABLE]

Success Criteria:
[MEASURABLE CONDITIONS]

Evidence Required:
[WHAT MUST SUPPORT THE RESULT]

Explicit Boundaries:
[DO NOT DO]

Independent Review Requirement:
[YES / NO / DETAILS]

A work-task classification answers:

«What kind of work is this?»

An execution-authorization mode answers:

«What is the receiving system actually permitted to do?»

Do not use one as a substitute for the other.

---

31. SUPPORTING TASKS

For each supporting task:

Task:
[WHAT]

Relationship to Primary Task:
[WHY IT SUPPORTS IT]

Work-Task Classification:
[TYPE]

Execution-Authorization Mode:
[MODE]

Status:
[STATUS]

Dependency:
[WHAT IT DEPENDS ON]

Supporting tasks must not become an excuse to expand scope unnecessarily.

Future ideas do not belong in the primary execution contract unless explicitly brought into scope.

---

32. NEXT ACTION QUEUE

Only include actions justified by the current state.

NEXT 1

[EXACT ACTION]

NEXT 2

[EXACT ACTION]

NEXT 3

[EXACT ACTION]

Each action should be:

- grounded in current state;
- within current scope;
- consistent with current authority;
- and executable under current authorization.

Do not insert speculative work merely because it might be useful later.

When only one action is genuinely justified, list one action rather than manufacturing a larger queue.

---

33. NEXT GATE

Gate:
[NAME]

Entry Requirements:
[WHAT MUST BE TRUE]

Exit Requirements:
[WHAT MUST BE TRUE]

Reviewer Role / Person / Model:
[WHO / ROLE]

Decision Authority / Approver:
[WHO / ROLE]

Execution-Gating Authority, If Any:
[WHO / ROLE]

Failure Condition:
[WHAT SENDS WORK BACK]

Artifacts Produced:
[WHAT]

Independent Review Required?:
[YES / NO]

Do not describe a gate as passed unless its actual entry/exit requirements have been satisfied.

---

34. CROSS-AI / CROSS-TOOL RECORD

For every other AI or tool involved:

Tool / Model / Surface:
[NAME]

Assigned Role:
[ROLE]

Role Authority:
[AUTHORITY BOUNDARY]

Work-Task Classification:
[WHAT KIND OF WORK]

Execution-Authorization Mode:
[DISCUSSION / RECOMMENDATION / REVIEW / AUDIT / RECOMMENDATION + CONDITIONAL EXECUTION / EXECUTION / OTHER]

Task Given:
[TASK]

Input Type:
[EVIDENCE / RECOMMENDATION / DECISION / REVIEW REQUEST / EXECUTION REQUEST / OTHER]

Output / Conclusion:
[RESULT]

Accepted:
[WHAT]

Modified:
[WHAT]

Rejected:
[WHAT]

Deferred / Escalated:
[WHAT]

Unverified:
[WHAT]

Independent Evaluation Performed By Receiving Role?:
[YES / NO / NOT REQUIRED]

Independent Review Performed?:
[YES / NO / NOT REQUIRED]

Decision / Authority Status:
[CONSULTATIVE INPUT / APPROVED DECISION / CONFIRMED / EVIDENCE / REVIEW FINDING / EXECUTION RESULT / OTHER]

Effect on Project State:
[WHAT CHANGED]

Never treat output as authoritative merely because the tool or model is:

- different;
- stronger;
- newer;
- more expensive;
- or independently branded.

A recommendation remains consultative unless the responsible authority explicitly accepts it as a decision.

A reviewer remains a reviewer unless the governing process separately grants decision authority.

---

35. ENVIRONMENT / TOOL STATE

Where relevant:

Repository:
[REPOSITORY]

Branch:
[BRANCH]

Commit / Revision:
[COMMIT]

Prototype Version:
[VERSION]

Files Created:
[LIST]

Files Modified:
[LIST]

Files Deleted:
[LIST]

Files Expected but Missing:
[LIST]

Tools Used:
[TOOLS]

Tools Actually Available:
[TOOLS]

Tool Limitations Encountered:
[WHAT]

Access / Permission Limitations:
[WHAT]

Do not claim to have inspected, executed, verified, or changed an artifact that was not actually accessible.

---

36. UNVERIFIED / ACCESS-LIMITED MATERIAL

For every important artifact or source that could not be inspected:

Artifact / Source:
[WHAT]

Why Not Inspected:
[REASON]

What Is Actually Known About It:
[KNOWN CONTEXT ONLY]

What Is NOT Known:
[UNCERTAINTY]

Impact:
[WHAT REMAINS UNCERTAIN]

Required Action:
[WHAT WOULD RESOLVE IT]

Never represent inaccessible material as reviewed.

Do not treat metadata, filename, or description as a substitute for actual inspection unless the project explicitly permits that evidence level.

---

37. CRITICAL DO-NOT-INVENT AND AUTHORITY-PRESERVATION RULE

For specialized or high-risk domains, do not invent:

- domain behavior;
- command behavior;
- workflow order;
- prerequisites;
- state transitions;
- errors;
- recovery procedures;
- outputs;
- version applicability;
- airline-specific behavior;
- market-specific rules;
- technical capabilities;
- implementation capabilities;
- or learner outcomes.

If not established:

«UNKNOWN — REQUIRES VERIFICATION»

For DEIXEN:

- learning design must not silently become Amadeus technical truth;
- product recommendations must not silently become approved product decisions;
- implementation logic must not silently become domain truth;
- documentation must not silently become empirical proof;
- a handoff must not silently become canonical project truth;
- a prior-session conclusion must not silently become current authority;
- and a model recommendation must not silently become a project decision.

A handoff preserves state.

It does not manufacture authority.

---

38. SAFETY / RISK PRIORITIZATION

Prioritize unresolved issues that could create:

- incorrect domain training;
- false learner confidence;
- unsafe or incorrect workflow behavior;
- broken terminal logic;
- broken Coach behavior;
- contradictory state;
- major architectural rework;
- major UX/product rework;
- corrupted learner evidence;
- loss of critical knowledge;
- unauthorized implementation;
- invalid canonicalization;
- or misleading claims of readiness.

The verification burden should increase with the consequence of being wrong.

High-risk uncertainty must not be hidden merely to keep the handoff compact.

---

39. SUPERSESSION CONTROL

For every superseded decision, artifact, rule, or recommendation:

Superseded Item:
[WHAT]

Superseded By:
[WHAT]

Reason for Supersession:
[WHY]

Effective Date / Version:
[WHEN]

Still Useful as Historical Context?:
[YES / NO]

Current Status:
"SUPERSEDED"

A superseded item must not be treated as active merely because it appears in:

- an older handoff;
- archived documentation;
- previous discussion;
- old code;
- or a historical model response.

Historical value does not restore operational authority.

---

40. CANONICALIZATION QUEUE

Record important changes that should eventually enter canonical project knowledge.

For each:

Change:
[WHAT]

Target Canonical File / Artifact:
[WHERE]

Reason:
[WHY]

Required Verification:
[WHAT]

Required Review:
[WHAT]

Authority Needed:
[WHO / ROLE]

Decision Status:
[STATUS]

Canonicalization Status:
"PENDING CANONICALIZATION"

Do not describe a change as canonical until it has actually become canonical according to project governance.

A handoff entry saying "canonicalization pending" must remain pending even if multiple agents agree that the change is good.

---

41. SESSION-ONLY INFORMATION

Record information that is intentionally useful for continuity but is NOT intended to become canonical project knowledge.

Examples:

- temporary tactical notes;
- working interpretations;
- conversation-specific context;
- discarded wording;
- temporary task sequencing;
- transient tool state;
- temporary prompts;
- one-off operational workarounds;
- non-canonical drafts.

For each:

Item:
[WHAT]

Why It Is Session-Only:
[WHY]

Expiration Condition:
[WHEN]

This prevents temporary context from leaking into permanent project truth.

---

42. HANDOFF INTEGRITY AUDIT

Before finalizing the handoff, verify every applicable item:

[ ] Current phase is explicit.
[ ] Current sub-phase is explicit.
[ ] Current task is explicit.
[ ] Work-task classification is explicit where relevant.
[ ] Execution-authorization mode is explicit where relevant.
[ ] Assigned role is explicit where relevant.
[ ] Current gate is explicit.
[ ] Authority model is explicit or marked undefined.
[ ] Canonical artifacts are identified.
[ ] Operating sources are distinguished from canonical approval where relevant.
[ ] Canonical state and session state are separated.
[ ] Version/currentness context is preserved.
[ ] Scope/context is preserved.
[ ] Completed work is separated from planned work.
[ ] Open decisions are separated from approved/protected decisions.
[ ] User-owned decisions are identified.
[ ] Claims are separated from interpretations and hypotheses.
[ ] Epistemic status is separated from decision/lifecycle status.
[ ] Validation status is kept separate where material.
[ ] Currentness/supersession is kept separate where material.
[ ] Recommendations/consultative input are separated from decisions.
[ ] Output type is separated from execution authorization.
[ ] Negative knowledge is preserved.
[ ] Evidence is traceable.
[ ] Provenance is traceable for material decisions.
[ ] Unverified information remains unverified.
[ ] Rejected proposals are recorded.
[ ] Superseded items are recorded.
[ ] Temporary assumptions are recorded.
[ ] Terminology is preserved.
[ ] Constraints are identified.
[ ] Dependencies are identified.
[ ] Pending reviews are identified.
[ ] Reviewer and approver are distinguished.
[ ] Independent-review requirements are identified where applicable.
[ ] Execution-gating authority is identified where applicable.
[ ] Blockers are identified.
[ ] Session deltas are recorded.
[ ] Artifact changes are recorded.
[ ] Incomplete work is recorded.
[ ] Missing inputs are recorded.
[ ] Tool/environment state is recorded where relevant.
[ ] Canonicalization queue is recorded.
[ ] Session-only information is separated.
[ ] No material decision was silently omitted.
[ ] No unresolved issue was falsely marked complete.
[ ] No unsupported domain behavior was invented.
[ ] No historical information was silently promoted to current truth.
[ ] No model opinion was represented as evidence.
[ ] No recommendation was represented as an approved decision.
[ ] No reviewer was represented as an approver without authority.
[ ] No execution authorization was widened implicitly.
[ ] No execution result was represented as automatic approval.
[ ] No superseded decision is presented as active.
[ ] The next action is unambiguous.
[ ] The next gate is unambiguous.

---

43. FINAL STATE SNAPSHOT

End the handoff with this compact state representation:

PROJECT:
[NAME]

DATE:
[DATE]

HANDOFF VERSION:
[VERSION]

PHASE:
[CURRENT]

SUB-PHASE:
[CURRENT]

STATUS:
[✅ / 🟢 / 🟡 / 🟠 / 🔴]

CURRENT GATE:
[GATE]

PRIMARY TASK:
[ONE TASK]

WORK-TASK CLASSIFICATION:
[TYPE]

EXECUTION-AUTHORIZATION MODE:
[MODE]

ASSIGNED ROLE:
[ROLE]

DECISION AUTHORITY:
[WHO / ROLE]

INDEPENDENT REVIEW REQUIRED:
[YES / NO]

COMPLETED:
[TOP MATERIAL ITEMS]

APPROVED / PROTECTED:
[TOP APPROVED / PROTECTED DECISIONS]

OPEN:
[TOP OPEN ISSUES]

PENDING REVIEW:
[TOP PENDING ITEMS]

BLOCKED:
[TOP BLOCKERS]

SESSION DELTA:
[WHAT CHANGED]

DO NOT REOPEN:
[CRITICAL PROTECTED ITEMS]

REQUIRES VERIFICATION:
[CRITICAL UNKNOWN / UNVERIFIED CLAIMS]

PENDING CANONICALIZATION:
[CHANGES]

SUPERSEDED:
[IMPORTANT SUPERSEDED ITEMS]

NEXT ACTION:
[ONE ACTION]

NEXT GATE:
[ONE GATE]

This snapshot is a compression of the detailed handoff.

It does not replace the detailed records above.

---

44. RECEIVING AI VALIDATION BEHAVIOR

Interactive Chat Mode

Before substantive work, return a concise acknowledgment containing:

1. Current phase.
2. Current primary task.
3. Work-task classification.
4. Applicable execution-authorization mode, when relevant.
5. Assigned role, when relevant.
6. Three most important approved/protected facts or decisions.
7. Three most important open issues.
8. Any detected contradiction, ambiguity, missing input, or authority gap.
9. The sources and authority owners that will govern the task.

Then proceed only within the stated scope and authorization.

Do not unnecessarily rewrite the entire handoff.

Do not treat a consultative recommendation in the handoff as an execution instruction or approved decision.

Do not ask for clarification merely because multiple safe choices exist.

Ask or escalate only when the missing distinction materially affects:

- correctness;
- authority;
- scope;
- safety;
- gate status;
- or the requested outcome.

Autonomous / Tool / Agent Mode

Do not create an unnecessary conversational round-trip.

Instead:

1. Validate the handoff internally.
2. Identify the work-task classification.
3. Identify the execution-authorization mode.
4. Identify the assigned role and authority boundary.
5. Detect contradictions, missing inputs, and authority gaps.
6. Apply the authority model and current decision states.
7. Preserve uncertainty.
8. Distinguish consultative input from actual decisions.
9. Confirm any required independent-review gate before treating the work as cleared.
10. Proceed only when the task is sufficiently grounded and authorized.
11. Stop or enter verification mode when a stop condition is reached.

---

45. HANDOFF STOP CONDITIONS

The receiving system must stop or switch to verification mode when:

- two authoritative sources genuinely conflict;
- a high-risk factual claim lacks adequate evidence;
- current version or context cannot be established;
- a required source is missing;
- a user-owned decision is required;
- a major project gate appears skipped;
- required independent review has not occurred;
- reviewer and approver responsibilities are unclear where material;
- execution authorization is missing;
- execution authorization conflicts with project authority;
- execution would exceed approved scope;
- the task depends on a materially unknown state;
- proceeding would require invention;
- an advisory recommendation is being treated as an approved decision;
- implementation behavior is being used as domain proof without the required validation;
- or an apparently superseded rule may still be active and cannot be resolved.

Stopping is preferable to manufacturing continuity.

A stop condition is a control mechanism, not a project failure.

---

46. INFORMATION PRESERVATION PRINCIPLE

Compress wording when useful.

Do NOT compress away:

- decisions;
- reasons;
- evidence;
- provenance;
- uncertainty;
- contradictions;
- negative findings;
- rejected directions;
- currentness;
- dependencies;
- ownership;
- authority;
- execution boundaries;
- pending gates;
- supersession;
- validation status;
- canonicalization status;
- or next action.

A shorter handoff that loses one material decision is worse than a longer handoff that preserves it.

However, verbosity alone is not quality.

The objective is:

«Minimum sufficient continuity with maximum preservation of material truth.»

---

47. HANDOFF QUALITY STANDARD

A successful handoff must allow the receiving system to answer:

1. Where exactly are we?
2. What has actually been completed?
3. What is canonical?
4. What is merely the current operating source?
5. What changed?
6. Why did it change?
7. Who or what caused the change?
8. What is approved or protected?
9. What is unresolved?
10. What evidence supports important claims?
11. What remains unknown?
12. What was rejected?
13. What was superseded?
14. What is blocked?
15. Who owns each material decision type?
16. Who is authorized to execute?
17. Is independent review required?
18. Who is the reviewer?
19. Who is the approver?
20. What must not be reopened?
21. What must not happen yet?
22. What is session-only?
23. What must eventually be canonicalized?
24. What exactly should happen next?
25. What gate follows that action?

If the handoff cannot answer these questions, it is incomplete.

---

48. FINAL MASTER PRINCIPLE

The handoff must preserve the strongest truthful state of the project, not merely the latest conversation.

The goal is not:

«"Make the next AI remember the conversation."»

The goal is:

«"Make the next AI unable to easily misunderstand what is known, what was observed, what was inferred, what was recommended, what was decided, what is canonical, what is merely operational, what changed, what remains unknown, what was rejected, what was superseded, what is pending, who has authority, what is authorized, what requires independent review, and what must happen next."»

The handoff is a continuity mechanism.

Canonical project knowledge remains the project's operational truth.

Evidence remains the basis for factual claims.

Decisions remain governed by their legitimate authority.

Recommendations remain consultative until accepted by the responsible authority.

Reviewer status does not automatically confer approval authority.

Execution remains bounded by explicit authorization and scope.

Execution does not authorize redesign unless redesign is separately authorized.

Required independent review remains distinct from approval.

Implementation verification remains distinct from domain validation.

Documentation remains distinct from empirical proof.

Unknowns remain unknown until resolved.

A newer handoff does not automatically supersede canonical project truth.

A more capable model does not automatically gain more authority.

A more confident answer does not automatically become more correct.

The handoff preserves continuity.

It does not manufacture certainty.

It does not manufacture authority.

It does not manufacture approval.

It does not manufacture validation.

---

END OF UNIVERSAL AI SESSION HANDOFF PROTOCOL — MASTER v4