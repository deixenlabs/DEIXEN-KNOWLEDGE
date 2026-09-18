UNIVERSAL AI SESSION HANDOFF PROTOCOL

MASTER v3 — FINAL

---

0. PURPOSE

This document is a loss-minimizing session handoff protocol.

Its purpose is to transfer the exact operational state of a previous session to another AI, model, agent, tool, developer, or future session without losing material context.

The handoff must preserve, where relevant:

- project state,
- phase and gate position,
- decisions,
- unresolved questions,
- evidence,
- provenance,
- negative findings,
- assumptions,
- rejected directions,
- version/currentness context,
- dependencies,
- ownership,
- pending reviews,
- blockers,
- artifact changes,
- and the exact next action.

This is NOT merely a conversation summary.

It is a continuity and state-transfer artifact.

The goal is not to make the receiving system "feel" as though it remembers the previous session.

The goal is to make the receiving system capable of reconstructing the strongest truthful state of the project with minimal risk of misunderstanding.

---

1. RECEIVING SYSTEM — NON-NEGOTIABLE RULES

The receiving system MUST reconstruct the previous session before performing substantive work.

Do NOT:

- restart the project from scratch,
- assume missing information is unimportant,
- silently invent missing information,
- silently infer facts and present them as facts,
- silently reconcile conflicting information,
- silently promote recommendations into decisions,
- silently promote session decisions into canonical truth,
- silently treat drafts as final,
- silently treat historical material as current,
- silently treat model agreement as evidence,
- silently revive superseded decisions,
- or claim work was completed when it was only discussed, proposed, or partially performed.

Do NOT reopen a decision explicitly marked "LOCKED" unless a valid reopening trigger exists.

Do NOT use "common sense", generic domain knowledge, memory, or model intuition to fill a material knowledge gap when the project requires evidence.

When evidence is insufficient:

«Preserve the unknown.»

When sources genuinely conflict:

«Preserve the conflict until authority, context, version, and evidence resolve it.»

When an inference is necessary:

«Label it explicitly as an inference.»

An inference must never silently become a verified fact.

---

2. SESSION-STATE AUTHORITY VS PROJECT-TRUTH AUTHORITY

This distinction is mandatory.

SESSION-STATE AUTHORITY

The handoff is authoritative for reporting:

- what happened in the previous session,
- what was discussed,
- what was attempted,
- what changed,
- what remained open,
- what was rejected,
- what is pending,
- and what the previous session believed or decided.

PROJECT-TRUTH AUTHORITY

Canonical project artifacts and appropriately verified evidence remain authoritative for the actual project truth according to the project's declared authority model.

Therefore:

«A handoff is authoritative for session state but is NOT automatically authoritative for canonical project truth.»

A handoff does not override canonical knowledge merely because it is newer.

A new fact may justify updating canonical knowledge.

A new opinion does not.

A new decision may be recorded in the handoff as a pending canonicalization delta until the project's governance makes it authoritative.

---

3. CONFLICT RESOLUTION PROTOCOL

When the handoff conflicts with a project artifact:

1. Identify the exact conflict.
2. Identify the conflicting claims or decisions.
3. Identify the authority level of each source.
4. Check version, date, context, scope, and supersession.
5. Determine whether the handoff contains:
   - new evidence,
   - a new decision,
   - an interpretation,
   - a recommendation,
   - or unsupported opinion.
6. Do not silently select one.
7. Apply the project's declared governance.
8. Record the conflict and required resolution.
9. Do not promote unresolved material into canonical truth.

When the project authority model itself is unclear:

«Do not invent a hierarchy. Flag the ambiguity.»

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
[ ] Authority model is identifiable.
[ ] Relevant source-of-truth artifacts are identifiable.
[ ] Open decisions are identifiable.
[ ] Pending reviews are identifiable.
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

---

6. PROJECT STATE — EXACT CURRENT POSITION

Use explicit status labels.

✅ COMPLETE

[WHAT IS ACTUALLY COMPLETE]

🟢 APPROVED / LOCKED

[WHAT IS SETTLED]

🟡 IN PROGRESS

[WHAT IS CURRENTLY BEING WORKED ON]

🟠 PENDING REVIEW

[WHAT IS WAITING FOR REVIEW]

🔴 BLOCKED

[WHAT CANNOT SAFELY PROCEED]

⚪ NOT STARTED

[WHAT HAS NOT BEGUN]

⛔ DO NOT START YET

[DOWNSTREAM WORK THAT MUST WAIT]

⛔ DO NOT REOPEN

[LOCKED MATTERS THAT MUST REMAIN CLOSED]

Never infer completion from:

- file existence,
- draft existence,
- discussion,
- prototype existence,
- model output,
- or planned work.

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

Do not declare a phase complete because work merely occurred.

Completion requires satisfaction of its actual exit conditions.

---

8. AUTHORITY MODEL

State the project's actual authority hierarchy exactly.

Do not replace the project's real hierarchy with a generic default.

Where applicable, distinguish:

- primary official/domain evidence,
- canonical project knowledge,
- approved decisions,
- reviewed working artifacts,
- session handoffs,
- discussion,
- model inference.

Also record authority by domain when applicable:

Domain / Amadeus:
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

If no authority has been defined for a material decision type:

«Mark it as undefined rather than inventing one.»

---

9. SOURCE-OF-TRUTH INVENTORY

For EACH relevant artifact:

File / Artifact:
"filename"

Exact Path / Location:
[path]

Purpose / Role:
[WHAT IT CONTROLS]

Authority:
[CANONICAL / PRIMARY / REFERENCE / WORKING / OUTPUT / HISTORICAL / ARCHIVE]

Status:
[APPROVED / PENDING / DRAFT / FROZEN / SUPERSEDED / OBSOLETE]

Owner:
[PERSON / MODEL / TEAM]

Review Authority:
[WHO]

Version / Revision:
[VERSION / DATE]

Last Relevant Change:
[WHAT]

Can Be Edited Now?:
[YES / NO]

Can Override Other Artifacts?:
[YES / NO]

Supersedes:
[WHAT, IF ANY]

Superseded By:
[WHAT, IF ANY]

Known Conflicts:
[IF ANY]

Canonicalization Required?:
[YES / NO]

---

10. KNOWLEDGE STATUS TAXONOMY

Never collapse different epistemic states into a single "truth" category.

DOCUMENTED

Explicitly stated by an appropriate source.

OBSERVED

Actually observed in a specific environment, test, repository, execution, or artifact.

EVIDENCED INFERENCE

A conclusion strongly supported by evidence but not stated verbatim.

HYPOTHESIS

A proposed interpretation requiring validation.

AEROBRIDGE DESIGN DECISION

An intentional product/simulation decision.

RECOMMENDATION

A suggested action that has not been accepted as a decision.

USER DECISION

A decision explicitly made by the product owner.

UNKNOWN

Insufficient evidence to establish the claim.

REJECTED

Explicitly considered and rejected.

SUPERSEDED

Previously accepted but no longer active.

These categories must remain distinguishable.

---

11. CURRENTNESS / VERSION / CONTEXT SAFETY

For any version-sensitive, time-sensitive, market-sensitive, airline-sensitive, or environment-sensitive item:

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

- old and new syntax,
- old and new workflows,
- legacy and current behavior,
- different environments,
- different markets,
- different airline configurations,
- or different product versions.

When temporal or contextual conflict exists, explain it rather than averaging the sources.

---

12. SESSION DELTA — WHAT CHANGED?

This section is mandatory.

Record material changes relative to the previous known state.

For EACH:

Delta ID:
[Δ-XXX]

Previous State:
[OLD]

New State:
[NEW]

Change Type:
[FACT / DISCOVERY / CORRECTION / DECISION / RECOMMENDATION / REJECTION / ARTIFACT CHANGE]

Origin:
[WHERE THE CHANGE CAME FROM]

Evidence / Basis:
[WHAT SUPPORTS IT]

Authority:
[WHO / WHAT]

Canonicalized?:
[YES / NO]

Downstream Impact:
[WHAT CHANGES]

Follow-Up Required:
[YES / NO]

The delta section exists to prevent important changes from being lost in long conversations.

---

13. DECISION LINEAGE / PROVENANCE

For every material decision or change, preserve its lineage.

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

Reviewer / Model:
[WHO]

User Decision:
[IF APPLICABLE]

Resulting Decision:
[WHAT WAS DECIDED]

Resulting Change:
[WHAT CHANGED]

Canonical Target:
[FILE / NONE]

Current Status:
[CANONICAL / APPROVED PENDING CANONICALIZATION / PROPOSED / SUPERSEDED / REJECTED]

This section preserves the chain:

«source → finding → review → decision → change → canonicalization»

---

14. LOCKED DECISIONS

For EACH:

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
[WHO]

Status:
LOCKED

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

A locked decision must not be reopened merely because another AI proposes an alternative.

---

15. OPEN DECISIONS

For EACH:

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
[OPTIONAL]

What Is Unknown:
[EXACT GAP]

Required Evidence:
[WHAT WOULD RESOLVE IT]

Decision Authority:
[WHO]

Status:
OPEN

OPEN means unresolved.

Do not choose a winner simply because one option seems more convenient.

---

16. USER-OWNED DECISIONS

Record decisions reserved for explicit user authority.

Decision / Question:
[WHAT]

Why User Authority Is Required:
[WHY]

Current Status:
[PENDING USER DECISION]

Options:
[OPTIONS]

Recommendation, If Any:
[RECOMMENDATION — NOT A DECISION]

Never convert a recommendation into user approval.

---

17. NEW INFORMATION INTRODUCED THIS SESSION

Separate all new material.

A. VERIFIED FACTS

[FACTS]

B. OBSERVATIONS

[OBSERVATIONS]

C. STRONGLY SUPPORTED FINDINGS

[FINDINGS]

D. EVIDENCED INFERENCES

[INFERENCES]

E. HYPOTHESES

[HYPOTHESES]

F. DESIGN DECISIONS

[DECISIONS]

G. RECOMMENDATIONS

[RECOMMENDATIONS]

H. UNKNOWN / NOT ESTABLISHED

[UNKNOWN]

Never merge these categories.

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

Repeated agreement between AI systems is NOT independent evidence.

---

19. NEGATIVE KNOWLEDGE

Preserve meaningful negative findings.

Record items that were:

- searched for and not found,
- investigated and unsupported,
- explicitly rejected,
- disproven,
- superseded,
- historical only,
- outside project scope,
- cross-domain contamination,
- or not established as current.

For EACH:

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

---

20. ARTIFACT CHANGES

For EACH changed artifact:

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

Approved By:
[WHO]

Verification Performed?:
[YES / NO]

Canonicalized?:
[YES / NO]

Remaining Migration:
[WHAT]

---

21. WORK COMPLETED THIS SESSION

Record only work that was actually completed.

For EACH:

Action:
[WHAT WAS DONE]

Result:
[OUTCOME]

Artifact Affected:
[WHAT]

Evidence of Completion:
[WHAT PROVES IT]

Status:
COMPLETE

Do not classify any of the following as completed:

- ideas,
- intentions,
- drafts,
- proposed changes,
- discussions,
- or partially executed tasks.

---

22. WORK ATTEMPTED BUT NOT COMPLETED

For EACH:

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

---

23. REJECTED PROPOSALS / FAILED DIRECTIONS

For EACH:

Proposal:
[WHAT]

Rejected Because:
[WHY]

Evidence / Reasoning:
[BASIS]

Status:
REJECTED

Can Be Reconsidered?:
[YES / NO]

Valid Reconsideration Trigger:
[WHAT]

Never re-propose a rejected direction without addressing the original rejection reason.

---

24. OPEN ISSUES / RISKS / BLOCKERS

For EACH:

Issue ID:
[I-XXX]

Problem:
[WHAT]

Impact:
[WHY IT MATTERS]

Severity:
[P0 / P1 / P2 / P3]

Evidence:
[BASIS]

Current Status:
[OPEN / INVESTIGATING / BLOCKED / PENDING REVIEW]

Owner:
[WHO]

Next Action:
[EXACT ACTION]

Blocking Downstream Work?:
[YES / NO]

---

25. PENDING REVIEWS / APPROVALS

For EACH:

Artifact / Decision:
[WHAT]

Reviewer:
[WHO / MODEL]

Review Type:
[ADVERSARIAL / TECHNICAL / FACTUAL / CURRICULUM / DESIGN / LEARNING / OTHER]

Status:
PENDING

Exact Review Question:
[QUESTION]

Required Inputs:
[WHAT]

Acceptance Criteria:
[CRITERIA]

What Happens After Review:
[NEXT GATE]

---

26. TEMPORARY ASSUMPTIONS

For EACH:

Assumption ID:
[A-XXX]

Assumption:
[WHAT]

Why Needed:
[WHY]

Verified?:
NO

Risk If Wrong:
[IMPACT]

Validation Method:
[HOW]

Expiry / Review Trigger:
[WHEN]

Temporary assumptions must never silently become canonical facts.

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

This prevents terminology drift between sessions, models, and tools.

---

28. CONSTRAINTS

Classify each constraint as one of:

🔒 NON-NEGOTIABLE

Must be respected unless formally changed.

🟡 CURRENT PREFERENCE

Can change if evidence or a better decision justifies it.

🟠 TEMPORARY

Applies only to the current phase, review, or task.

For EACH:

Constraint:
[WHAT]

Type:
[TYPE]

Reason:
[WHY]

Authority:
[WHO]

Scope:
[WHERE IT APPLIES]

Do not convert a preference into a hard rule without explicit authority.

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

Evidence
→ Knowledge
→ Decision
→ Curriculum / Learning Design
→ Experience Architecture
→ Design
→ Implementation

Do not perform downstream work while a required upstream gate remains unresolved.

---

30. CURRENT PRIMARY TASK

There must be ONE primary task.

Supporting verification or sub-tasks may exist, but they must not obscure the primary objective.

Primary Task:
[EXACT TASK]

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

---

31. SUPPORTING TASKS

For each supporting task:

Task:
[WHAT]

Relationship to Primary Task:
[WHY IT SUPPORTS IT]

Status:
[STATUS]

Dependency:
[WHAT IT DEPENDS ON]

Supporting tasks must not become an excuse to expand scope unnecessarily.

---

32. NEXT ACTION QUEUE

NEXT 1

[EXACT ACTION]

NEXT 2

[EXACT ACTION]

NEXT 3

[EXACT ACTION]

Only include actions justified by the current state.

Do not insert speculative work merely because it might be useful later.

---

33. NEXT GATE

Gate:
[NAME]

Entry Requirements:
[WHAT MUST BE TRUE]

Exit Requirements:
[WHAT MUST BE TRUE]

Reviewer / Authority:
[WHO]

Failure Condition:
[WHAT SENDS WORK BACK]

Artifacts Produced:
[WHAT]

---

34. CROSS-AI / CROSS-TOOL RECORD

For every other AI or tool involved:

Tool / Model:
[NAME]

Task Given:
[TASK]

Output / Conclusion:
[RESULT]

Accepted:
[WHAT]

Rejected:
[WHAT]

Unverified:
[WHAT]

Authority Level:
[RECOMMENDATION / EVIDENCE / DECISION / OTHER]

Effect on Project State:
[WHAT CHANGED]

Never treat output as authoritative merely because the tool or model is different, stronger, or independent.

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

Tool Limitations Encountered:
[WHAT]

Do not claim to have inspected or changed an artifact that was not actually accessible.

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

Never represent inaccessible material as reviewed.

---

37. CRITICAL DO-NOT-INVENT RULE

For specialized or high-risk domains, do not invent:

- domain behavior,
- command behavior,
- workflow order,
- prerequisites,
- state transitions,
- errors,
- recovery procedures,
- outputs,
- version applicability,
- airline-specific behavior,
- market-specific rules,
- or technical capabilities.

If not established:

«"UNKNOWN — REQUIRES VERIFICATION"»

For AeroBridge, learning design, product recommendations, and implementation logic must not silently become sources of Amadeus technical truth.

---

38. SAFETY / RISK PRIORITIZATION

Prioritize unresolved issues that could create:

- incorrect domain training,
- false learner confidence,
- unsafe or incorrect workflow behavior,
- broken terminal logic,
- broken Coach behavior,
- contradictory state,
- major architectural rework,
- major UX/product rework,
- corrupted learner evidence,
- or loss of critical knowledge.

The verification burden should increase with the consequence of being wrong.

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

A superseded item must not be treated as active merely because it appears in an older handoff, archived document, or previous discussion.

---

40. CANONICALIZATION QUEUE

Record important changes that should eventually enter canonical project knowledge.

For EACH:

Change:
[WHAT]

Target Canonical File / Artifact:
[WHERE]

Reason:
[WHY]

Required Verification:
[WHAT]

Authority Needed:
[WHO]

Status:
PENDING CANONICALIZATION

Do not describe a change as canonical until it has actually become canonical according to project governance.

---

41. SESSION-ONLY INFORMATION

Record information that is intentionally useful for continuity but is NOT intended to become canonical project knowledge.

Examples:

- temporary tactical notes,
- working interpretations,
- conversation-specific context,
- discarded wording,
- temporary task sequencing,
- transient tool state.

For EACH:

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
[ ] Current gate is explicit.
[ ] Authority hierarchy is explicit or marked undefined.
[ ] Canonical artifacts are identified.
[ ] Canonical vs session state is separated.
[ ] Version/currentness context is preserved.
[ ] Scope/context is preserved.
[ ] Completed work is separated from planned work.
[ ] Open decisions are separated from locked decisions.
[ ] User-owned decisions are identified.
[ ] Facts are separated from observations.
[ ] Inferences are separated from hypotheses.
[ ] Recommendations are separated from decisions.
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
[ ] No superseded decision is presented as active.
[ ] The next action is unambiguous.

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

COMPLETED:
[TOP MATERIAL ITEMS]

LOCKED:
[TOP LOCKED DECISIONS]

OPEN:
[TOP OPEN ISSUES]

PENDING REVIEW:
[TOP PENDING ITEMS]

BLOCKED:
[TOP BLOCKERS]

SESSION DELTA:
[WHAT CHANGED]

DO NOT REOPEN:
[CRITICAL LOCKED ITEMS]

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

---

44. RECEIVING AI VALIDATION BEHAVIOR

Interactive Chat Mode

Before substantive work, return a concise acknowledgment containing:

1. Current phase.
2. Current primary task.
3. Three most important locked facts/decisions.
4. Three most important open issues.
5. Any detected contradiction, ambiguity, or missing input.
6. The sources that will be treated as authoritative.

Then begin the task.

Do not unnecessarily rewrite the entire handoff.

Autonomous / Tool / Agent Mode

Do not create an unnecessary conversational round-trip.

Instead:

1. Validate the handoff internally.
2. Detect contradictions and missing inputs.
3. Apply the authority model.
4. Preserve uncertainty.
5. Proceed only when the task is sufficiently grounded.
6. Stop or enter verification mode when a stop condition is reached.

---

45. HANDOFF STOP CONDITIONS

The receiving system must stop or switch to verification mode when:

- two authoritative sources genuinely conflict,
- a high-risk factual claim lacks adequate evidence,
- current version or context cannot be established,
- a required source is missing,
- a user-owned decision is required,
- a major project gate appears skipped,
- the task depends on a materially unknown state,
- proceeding would require invention,
- or an apparently superseded rule may still be active and cannot be resolved.

Stopping is preferable to manufacturing continuity.

---

46. INFORMATION PRESERVATION PRINCIPLE

Compress wording when useful.

Do NOT compress away:

- decisions,
- reasons,
- evidence,
- provenance,
- uncertainty,
- contradictions,
- negative findings,
- rejected directions,
- currentness,
- dependencies,
- ownership,
- pending gates,
- supersession,
- or canonicalization status.

A shorter handoff that loses one material decision is worse than a longer handoff that preserves it.

---

47. HANDOFF QUALITY STANDARD

A successful handoff must allow the receiving system to answer:

1. Where exactly are we?
2. What has actually been completed?
3. What is canonical?
4. What changed?
5. Why did it change?
6. Who or what caused the change?
7. What is locked?
8. What is unresolved?
9. What evidence supports important claims?
10. What remains unknown?
11. What was rejected?
12. What was superseded?
13. What is blocked?
14. Who owns each material decision type?
15. What must not be reopened?
16. What must not happen yet?
17. What is session-only?
18. What must eventually be canonicalized?
19. What exactly should happen next?
20. What gate follows that action?

If the handoff cannot answer these questions, it is incomplete.

---

48. FINAL MASTER PRINCIPLE

The handoff must preserve the strongest truthful state of the project, not merely the latest conversation.

The goal is not:

«"Make the next AI remember the conversation."»

The goal is:

«Make the next AI unable to easily misunderstand what is known, what was observed, what was inferred, what was decided, what is canonical, what changed, what remains unknown, what was rejected, what was superseded, what is pending, and what must happen next.»

The handoff is a continuity mechanism.

Canonical project knowledge remains the project's operational truth.

Evidence remains the basis for factual claims.

Decisions remain governed by their legitimate authority.

Unknowns remain unknown until resolved.

END OF UNIVERSAL AI SESSION HANDOFF PROTOCOL — MASTER v3 FINAL