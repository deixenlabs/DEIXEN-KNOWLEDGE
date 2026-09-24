---
name: DEIXEN — Prompt Engineering & Governance
status: PROPOSED ALIGNED DRAFT — NOT YET CANONICAL
purpose: Governing standard for constructing, reviewing, delivering, and revising prompts used in DEIXEN work.
owner_scope: Prompt construction methodology and prompt-level context, authority, task, output, verification, and clean-review controls.
consumes: DEIXEN — Unified AI Working Rules & Development Process (proposed 08); current project decisions/state; domain-owning artifacts; current roadmap; Universal AI Session Handoff Protocol.
does_not_own: AI role architecture, root decision vocabulary, permanent project decisions, Amadeus/domain truth, product architecture, curriculum truth, design-system truth, session-handoff mechanics, or engineering truth owned elsewhere.
---

> **STATUS BANNER — 2026-09-24 (07 Decision 16).** This is a **supporting
> reference**: it may be consulted for method, but it does not govern. Where it
> conflicts with `DEIXEN_Operating_Constitution.md`, `DEIXEN_Execution_Plan.md`,
> `08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process.md`, or
> `07_DEIXEN_Canonical_Decisions_and_Current_State.md`, those win. Its references
> to Sonnet, ChatGPT, Manus, Cowork, Opus staging, the Pre-Opus plan, or the
> Master Execution Roadmap describe arrangements that have ended (07 Decisions
> 16–17). Owner: Karim (earlier records: "Malik"). Working name: DEIXEN
> (earlier: AeroBridge).


# DEIXEN — Prompt Engineering & Governance

## 0. Purpose and Operating Boundary

This document governs **how DEIXEN prompts are constructed, reviewed, delivered, and revised**.

It is an operating method for turning:

- the user's actual objective,
- the current project state,
- the current roadmap phase,
- the relevant authority structure,
- the relevant source artifacts,
- the target model/tool,
- the requested action mode,
- and the required evidence/verification standard

into a prompt that is precise, bounded, usable, and resistant to material misunderstanding.

This document does **not** become an alternate source of truth for DEIXEN itself.

The foundational governance rules are owned by the project's AI Working Rules document. In particular, the AI Working Rules document owns:

- role definitions and authority boundaries;
- the root decision/lifecycle vocabulary;
- the foundational distinction between authority, evidence, approval, validation, and implementation truth;
- consultative-input behavior at the governance level;
- execution authorization;
- independent-review requirements and triggers;
- conflict-arbitration authority;
- engineering verification/process discipline;
- learner-effectiveness claim boundaries;
- and other global AI-working rules.

This document **consumes and operationalizes those rules for prompt construction**. It must not silently redefine them.

### Prompt Engineering ownership

This document owns prompt-specific mechanisms including:

- prompt composition;
- task-purpose classification;
- prompt-level authority/applicability analysis;
- context selection and contamination control;
- source-routing instructions;
- tool/model adaptation;
- prompt scope and protected-boundary construction;
- output and acceptance contracts;
- prompt-level verification and stop conditions;
- clean-review prompt construction;
- reusable prompt templates;
- prompt QA;
- prompt versioning;
- prompt failure modes;
- prompt complexity and length control;
- and prompt revision methodology.

Where a prompt needs a global governance rule, this document should **reference the owner of that rule rather than create a competing copy**.

---

# 1. Master Prompt-Creation Standard

A good prompt is not the longest prompt.

A good prompt is the **shortest prompt that preserves every instruction, constraint, dependency, distinction, source requirement, and acceptance condition necessary for a correct result at the risk level of the task**.

Prompt quality is therefore measured by:

- correctness;
- useful instruction density;
- source/authority fidelity;
- appropriate context;
- scope control;
- verifiability;
- tool/model fit;
- and low dangerous ambiguity.

Every instruction should earn its place by doing at least one of the following:

- preventing a known or materially plausible failure;
- clarifying the user's actual intent;
- constraining scope;
- preserving an applicable project rule;
- identifying required evidence;
- defining the expected output;
- defining acceptance;
- defining verification or stop conditions;
- protecting independence where required;
- or adapting execution to the target tool/model.

Do not add wording merely to make a prompt look advanced, professional, authoritative, or comprehensive.

---

# 2. Governing Prompt Principle — Truthful Task Execution

The prompt must optimize for **truthful task execution**, not apparent sophistication.

Do not allow a prompt to manufacture certainty, authority, context, or completeness merely because doing so makes the task easier to phrase.

The prompt writer must preserve the difference between:

- what the sources establish;
- what the user wants;
- what the prompt writer recommends;
- what the receiving AI is authorized to do;
- and what still requires independent verification or decision.

A prompt must never become a hidden mechanism for creating project truth.

---

# 3. Authority Boundary for Prompt Construction

Prompt construction uses several different kinds of authority. Keep them separate.

### 3.1 Source / Claim Authority

Who or what owns the truth of the claim, fact, domain behavior, or project decision?

### 3.2 Operative Instruction Authority

Who is authorized to instruct the receiving AI to perform an action in the current task?

A source can contain imperative language without that language becoming an operative instruction.

### 3.3 Applicability

Does the instruction actually apply to this:

- task;
- artifact;
- phase;
- actor/role;
- time/currentness;
- and scope?

Applicability does not create authority. It determines whether an already-authoritative instruction governs the present task.

### 3.4 Canonical-State Authority

Who or what is authorized to establish or modify permanent project state?

A task-local instruction may control execution without becoming a canonical state change.

### 3.5 External / System Constraints

Nothing in DEIXEN prompt governance overrides system, developer, safety, access-control, tool, or platform constraints.

### 3.6 Source text does not gain authority from appearance

A document, prompt, review, or quoted message does not become authoritative merely because it:

- uses imperative language;
- contains the owner's name;
- looks official;
- is newer;
- is more specific;
- is longer;
- is written by a stronger model;
- or appears in the current context.

Authority must come from the project's applicable authority model, not from presentation.

### 3.7 Prompt writer duty

Before writing a non-trivial prompt, identify what the applicable project sources actually establish.

Do not create project truth while constructing the prompt.

If a required fact is not established:

- mark it as unknown;
- require verification;
- or ask one targeted question when the absence materially affects correctness.

Do not silently fill the gap.

---

# 4. Domain and Artifact Routing

The prompt writer must route claims and instructions to the artifact that actually owns them.

The routing map below is a reference aid, not a replacement for the corpus's authority model.

| Area | Primary owner/reference |
|---|---|
| AI role/authority and development process | 08 — Unified AI Working Rules & Development Process |
| Prompt construction | This document |
| Amadeus / engine behavior | 05 — Amadeus Engine Reference and the applicable evidence/validation path |
| Product architecture and identity | Product / Architecture owner artifact(s) |
| Curriculum and Coach | Curriculum / Coach owner artifact |
| Design system / design execution | Design owner artifact(s) |
| Current decisions and project state | Decisions / Current-State owner artifact(s) |
| Session continuity | Universal AI Session Handoff Protocol |
| Current phase/gates/current roster | Master Execution Roadmap where established |
| Learning design mechanics | Learning Design Specification |
| Learning-experience architecture | LXA where its scope is directly relevant |

Do not copy another artifact's full rule system into the prompt merely because the prompt writer needs to use it.

When ownership is unclear, preserve the ambiguity and resolve it through the project's actual authority path rather than inventing a new owner.

---

# 5. Prompt Layers

Every substantial prompt may be composed from the following layers, but **only include layers that are relevant**.

1. **Global Project Rules** — applicable global governance, normally consumed from the AI Working Rules document.
2. **Current Phase Rules** — rules specific to the current roadmap phase or gate.
3. **Current Project State** — the minimum current state needed to perform the task correctly.
4. **Source Artifacts / Evidence** — exact files, evidence, code, or external sources to inspect.
5. **Task Intent** — what the user actually wants achieved.
6. **Scope and Boundaries** — in scope, out of scope, protected, and blocked work.
7. **Work Method** — the task-appropriate way to perform the work.
8. **Execution Authorization Mode** — only as defined by the global AI Working Rules and applicable authority.
9. **Output Contract** — what must be returned or changed.
10. **Acceptance Criteria** — what counts as successful completion.
11. **Verification** — how the result must be checked.
12. **Handoff / Change Logging** — only when continuity or artifact change makes it necessary.

Do not mechanically include every layer.

Do not reproduce the entire governance corpus inside a prompt.

---

# 6. Intent First

Before writing a prompt, reconstruct the user's actual goal.

Separate:

- explicit request;
- clearly implied objective;
- requirements necessary for success;
- material uncertainties;
- and assumptions introduced by the prompt writer.

Do not confuse the user's wording with the user's objective.

Example:

User says:

> "Make me a powerful prompt for Claude."

The actual objective may be:

> "Create a prompt that causes Claude to audit a specific artifact against the current DEIXEN baseline and return evidence-backed findings without implementing them."

The prompt should target the actual objective, not merely repeat the user's words.

---

# 7. Understanding Check Before Prompt Generation

Before writing a non-trivial prompt, verify internally:

- What is being done?
- Why is it being done?
- What phase is this?
- What artifact/system is affected?
- What must remain unchanged?
- What sources are authoritative?
- What evidence is available?
- What remains unknown?
- What is the task-purpose classification?
- What execution authorization applies?
- Who owns decisions in this task?
- What output is needed?
- What would count as failure?
- What would make the task unsafe to improvise?

Do not ask the user for information already established in the project context.

Ask only when missing information materially affects correctness or could cause costly or irreversible error.

---

# 8. Clarification Rule

When clarification is genuinely necessary, ask one focused question.

Use:

> **One focused question:** [question]

Where useful, also state:

> **If you prefer not to specify, I will use:** [safe assumption]

Do not ask a questionnaire when one question closes the material ambiguity.

Do not ask the user to choose between options already determined by project governance.

Do not ask when a safe, explicit assumption can be made without materially affecting correctness.

---

# 9. No-Invention Rule

Never invent in a prompt:

- project decisions;
- domain behavior;
- implementation facts;
- tool capabilities;
- file contents;
- repository state;
- review outcomes;
- approvals;
- evidence;
- user preferences not actually established;
- currentness/version applicability;
- or completion/readiness status.

When a material point is unknown, prefer explicit markers such as:

- `UNKNOWN — VERIFY`
- `NOT PROVIDED`
- `PENDING USER INPUT`
- `MUST INSPECT SOURCE`
- `REQUIRES DOMAIN VALIDATION`

Never hide uncertainty inside confident imperative language.

---

# 10. Evidence and Source Use

When the prompt concerns facts, technical behavior, specialized domain behavior, currentness, or existing project state:

1. prefer primary/authoritative sources;
2. prefer actual project artifacts over summaries;
3. prefer observed/tested behavior when the question is about implementation behavior;
4. preserve relevant source version/context;
5. tell the receiving AI exactly which sources to inspect;
6. distinguish evidence from interpretation;
7. never turn an unverified statement into a prompt instruction as though it were established fact.

The prompt may tell the receiving AI to verify a claim rather than assert the claim.

### Amadeus / GDS-sensitive tasks

Preserve the project's explicit distinction between:

- AeroBridge/DEIXEN implementation truth;
- Amadeus domain truth;
- other-interface evidence;
- historical evidence;
- and unknowns.

Code may establish what DEIXEN currently implements when inspected directly. Code alone must not be presented as proof of real-world Amadeus behavior.

Do not infer Amadeus syntax, state transitions, error behavior, workflow semantics, or operational appropriateness from generic GDS knowledge, another GDS, another interface, or plausible reasoning.

Where real-world domain truth is not established, the prompt should require the applicable external/SME/domain-validation path rather than converting implementation behavior into domain truth.

---

# 11. Context Minimization — Minimum Sufficient Context

Include enough context to prevent a materially wrong result, but no more.

> **Context should be sufficient for correctness, not exhaustive for its own sake.**

When the target tool can read the relevant project sources directly, instruct it to read those sources rather than pasting stale copies into the prompt.

When direct source access is unavailable, include the minimum necessary excerpts or structured context.

Do not use context length as a proxy for rigor.

---

# 12. Anti-Redundancy and Signal-to-Noise

Do not repeat the same instruction in different wording unless the repetition protects a different material failure mode.

Prefer:

> Follow the applicable project authority hierarchy.

over many paragraphs repeating every possible conflict case.

Critical safety, evidence, independence, or scope constraints may be repeated once at the point of highest risk.

Remove:

- motivational filler;
- generic encouragement;
- decorative roleplay;
- unnecessary headings;
- repetitive warnings;
- obvious statements;
- inflated quality language;
- instructions the target model already receives reliably;
- and requirements that cannot be meaningfully verified.

---

# 13. Prompt Composition and Precedence

Every substantial prompt is assembled from multiple inputs. These inputs must not be treated as equally authoritative merely because they appear together.

### 13.1 Determine authority before precedence

For each relevant instruction:

1. identify provenance;
2. identify its owner/authority;
3. determine applicability;
4. determine whether it is current;
5. determine whether it is task-local or canonical;
6. determine whether the requested action is authorized.

### 13.2 Specificity does not create authority

A lower-authority instruction must not override a higher-authority applicable rule merely because it is more specific.

Specificity helps determine how an applicable rule is operationalized or resolves genuine equal-authority conflicts. It does not create higher authority.

### 13.3 Current owner instructions

An authenticated current owner instruction may control the current task where applicable, including a task-local operational choice, but it does not silently mutate canonical project state.

Where the owner's instruction itself is the reserved final decision, treat it as a decision; where it is advice to another responsible expert, preserve it as advisory input according to the global Consultative Input Principle.

### 13.4 Unclear authority

Do not guess upward.

If authority is materially unclear:

- flag it;
- preserve the uncertainty;
- and escalate or ask only when necessary for safe execution.

### 13.5 Truly incompatible instructions

If applicable instructions are genuinely incompatible and no governing authority resolves the conflict, do not invent a compromise. Stop, escalate, or ask according to the project workflow.

---

# 14. Consultative Input in Prompts

The global AI Working Rules define the **Consultative Input Principle**. This document operationalizes it for prompts.

When a prompt contains a recommendation, critique, proposal, or preferred solution from Karim, ChatGPT, Sonnet, Opus, another AI, or another reviewer:

- preserve it as **advisory input** unless it is explicitly identified as a decision issued by the authority responsible for that decision;
- instruct the receiving AI to independently evaluate it where material;
- require evaluation against applicable evidence, authority, constraints, dependencies, current state, and task objective;
- permit acceptance, refinement, rejection, or deferral;
- do not require blind compliance;
- do not require reflexive disagreement merely to demonstrate independence.

The intended behavior is:

> **Consult → Verify → Evaluate → Accept / Refine / Reject / Defer → Execute only when authorized.**

This protects against two symmetric failures:

1. the receiving AI blindly obeys a plausible but wrong recommendation;
2. the receiving AI rejects a correct recommendation merely because it came from someone else.

### Important distinction

`Recommendation from Karim` and `explicit final owner decision from Karim` are not the same thing.

A prompt writer must identify which one is actually present.

---

# 15. Work Task Classification vs. Execution Authorization

These are separate dimensions and must not be conflated.

### 15.1 Work Task Classification

This document classifies what kind of work is being requested, for example:

- research;
- extraction;
- comparison;
- synthesis;
- curriculum design;
- learning design;
- product decision analysis;
- UX critique;
- visual exploration;
- implementation;
- debugging;
- testing;
- audit;
- adversarial review;
- decision arbitration;
- canonicalization preparation;
- documentation;
- handoff.

This answers:

> **What kind of work is this?**

### 15.2 Execution Authorization

The applicable AI Working Rules determine the authorization mode, such as:

- Discussion / Recommendation;
- Review / Audit;
- Recommendation + Conditional Execution;
- Execution;
- or another explicitly defined mode.

This answers:

> **What is the receiving AI authorized to do?**

Do not use "task type" to answer an authorization question, or "execution mode" to describe the purpose of the work.

---

# 16. Tool / Model Adaptation

A strong prompt is adapted to the actual target system.

Before writing it, identify when material:

**Target:**
[MODEL / TOOL / AGENT]

**Access:**
[CHAT / PROJECT FILES / REPOSITORY / WEB / CONNECTORS / OTHER]

**Action capability:**
[ANALYZE / WRITE / EDIT / EXECUTE / REVIEW]

**Relevant strengths:**
[STRENGTHS]

**Known constraints:**
[LIMITATIONS]

Do not instruct a tool to perform an action it cannot perform.

Do not assume that every model has the same memory, context window, file access, web access, connector access, or execution capability.

Do not compensate for uncertainty about tool capability by pretending the capability exists.

---

# 17. Role Targeting Without Role Redefinition

Role architecture is owned by the AI Working Rules document.

This document only determines which role properties a prompt needs to invoke.

A prompt may state:

> Act in the capacity of an independent adversarial reviewer for this task.

or:

> Evaluate the recommendation as the responsible expert before deciding whether it should be executed.

But the prompt must not redefine the role's authority in a way that conflicts with the global role architecture.

A role is assigned by the current task/workflow. The receiving agent must not self-create broader authority merely by naming itself a role.

---

# 18. Tool-Access Rule

If the target system can inspect the real sources, prefer:

> Read the following files directly before acting.

Do not paste a possibly outdated copy unless necessary.

If the target cannot access the sources:

> Include the minimum required excerpts or structured context.

Never imply that the target inspected a source it could not access.

Never claim a repository, file, webpage, or tool state was inspected unless the target actually had access to it.

---

# 19. Scope Contract

Every non-trivial prompt must make scope clear.

Use as appropriate:

**In scope:**
[WHAT]

**Out of scope:**
[WHAT]

**Protected / locked:**
[WHAT MUST NOT CHANGE]

**Do not start yet:**
[BLOCKED DOWNSTREAM WORK]

**Optional / future:**
[WHAT SHOULD NOT ENTER THE CURRENT TASK]

Scope boundaries must prevent both underperformance and scope creep.

Do not add prohibitions that are irrelevant to the task.

---

# 20. Read-Before-Act Rule

When the task depends on existing project truth, the prompt should require inspection before proposal or mutation.

Preferred sequences:

### Analysis

> Read → Verify → Analyze → Report.

### Research

> Define question → Gather evidence → Assess evidence → Compare → Record uncertainty → Conclude.

### Implementation

> Read → Verify → Inspect actual state → Plan minimal change → Implement → Test → Verify.

### Review

> Read → Establish review object → Verify evidence → Analyze → Report.

The exact sequence may change by task; the underlying rule does not:

> **Do not act on a system you have not first understood to the degree required by the task risk.**

---

# 21. No Premature Solutioning

Do not force a solution before the problem is established.

Bad:

> Implement the new architecture that fixes X.

when X has not been independently established.

Better:

> Verify whether X is actually a defect against the current approved baseline. If confirmed, recommend the smallest compliant correction before execution.

A prompt must allow the receiving AI to discover that the initial premise may be wrong.

---

# 22. Preserve Locked Decisions

When relevant, explicitly state:

**Locked decisions to preserve:**
[LIST]

**Valid reopening triggers:**
[NEW MATERIAL EVIDENCE / CONTRADICTION / MATERIAL SCOPE CHANGE / EXPLICIT REOPENING / OTHER GOVERNED TRIGGER]

Do not use language such as:

> Feel free to improve anything.

when the project contains protected decisions.

The prompt should protect settled decisions while still allowing legitimate reopening when the governing trigger exists.

---

# 23. Assumption Control

A prompt may contain an assumption only when it is:

1. necessary;
2. explicitly recognizable as an assumption;
3. safe enough for the task;
4. non-authoritative;
5. and reversible when practical.

Use:

**Working assumption:** [X]

**Status:** NOT CANONICAL

**Validate if material:** [HOW]

Never hide a consequential assumption inside an imperative.

---

# 24. Output Contract

Every substantial prompt should define what must be returned or changed.

Specify where relevant:

- format;
- structure;
- level of detail;
- evidence expectations;
- status labels;
- artifact/file targets;
- whether implementation is allowed;
- whether recommendations are expected;
- what must be omitted;
- and what should be surfaced separately.

The output contract should eliminate ambiguity without dictating unnecessary prose.

---

# 25. Acceptance Criteria

A strong prompt defines what "done" means.

Prefer observable criteria such as:

- all relevant sources inspected;
- every material claim traceable;
- no locked decision reopened without a valid trigger;
- no unsupported domain claim presented as fact;
- required tests actually run;
- only approved files changed;
- acceptance conditions satisfied;
- remaining uncertainty explicitly classified.

Avoid vague requirements such as:

> Make it amazing.

Acceptance criteria should be proportionate to task risk.

---

# 26. Verification Contract

Do not stop at generation when the task requires verification.

The prompt may require:

- source cross-check;
- contradiction check;
- file diff review;
- test execution;
- rendering check;
- acceptance checklist;
- edge-case review;
- currentness/version check;
- implementation inspection;
- or adversarial self-review.

Verification must match the actual risk.

Do not require elaborate self-audit for trivial tasks merely to appear rigorous.

---

# 27. Self-Critique Rule

Use self-critique when it reduces material risk.

Preferred:

> Before finalizing, check for unsupported assumptions, scope creep, missed constraints, contradictions, and unmet acceptance criteria.

Avoid:

> Spend a long time thinking about every possible issue.

The objective is better verification, not verbosity or theatrical reasoning.

Never request private chain-of-thought.

Ask instead for observable reasoning artifacts such as:

- evidence tables;
- decision matrices;
- assumption lists;
- verification checklists;
- reproduction steps;
- or concise rationale.

---

# 28. Adversarial Mode

For review/audit tasks, explicitly define what failure should be searched for.

Examples:

- unsupported assumptions;
- contradictions;
- missing safeguards;
- missing evidence;
- hidden prerequisites;
- wrong scope;
- state inconsistencies;
- currentness errors;
- authority drift;
- implementation/domain leakage;
- learner-effectiveness overclaims;
- or unverified recovery behavior.

Do not tell an auditor to find as many issues as possible without an evidence standard. That creates nitpicking rather than useful review.

---

# 29. Claim and Classification Handling in Prompts

When a task produces claims, findings, or decisions, preserve independent dimensions.

At minimum, distinguish as relevant:

### Epistemic / claim status

Examples:

- `FACT / OBSERVED`
- `SUPPORTED / DOCUMENTED`
- `EVIDENCED INFERENCE`
- `HYPOTHESIS`
- `UNKNOWN`

### Decision / lifecycle status

Use the shared vocabulary owned by 08 rather than inventing a competing list.

Examples include:

- `CONFIRMED`
- `PROPOSED`
- `APPROVED`
- `OPEN`
- `NEEDS VALIDATION`
- `PLANNED`
- `DEFERRED`
- `REJECTED`

### Authority / ownership

Who owns the claim or decision.

### Validation status

Whether it still requires implementation verification, domain/SME validation, external validation, or real-learner validation.

### Currentness / lifecycle

Whether the information is current, historical, version-specific, superseded, or otherwise bounded.

Do not make every prompt carry every dimension. Use only the dimensions needed to avoid materially misleading interpretation.

Do not let:

`APPROVED`

`CURRENT`

`REJECTED`

or

`HISTORICAL`

masquerade as proof of epistemic truth.

---

# 30. Currentness and Version Safety

When relevant, prompt the receiving AI to establish:

- applicable version;
- date/period;
- environment;
- market/geography;
- airline/carrier context;
- repository revision;
- product phase;
- or source status.

Do not allow a prompt to silently combine historical and current information.

When currentness is not material, do not add unnecessary version bureaucracy.

Artifact identity is not established by filename or recency alone. Where multiple copies, drafts, exports, review states, or revisions exist, use content, status, ownership, and explicit supersession where available.

Older does not automatically mean obsolete. Newer does not automatically mean authoritative.

If currentness/identity cannot be established and it materially affects the task:

- do not guess;
- flag the ambiguity;
- determine whether the task is blocked;
- and use a provisional treatment only when it cannot create silent canonical state.

---

# 31. Negative Knowledge

When the task involves research, verification, audit, or comparison, meaningful negative findings are first-class information.

Prompt the receiving AI to report when it:

- searched and found nothing;
- could not verify a claim;
- found only historical evidence;
- found contradictory evidence;
- rejected a proposed direction;
- or lacks sufficient evidence to conclude.

Absence of a finding must not be silently converted into evidence of non-existence.

---

# 32. Decision Authority in Prompts

Every prompt involving a decision should identify who or what has authority to:

- establish truth;
- approve;
- reject;
- defer;
- or execute.

A text string such as:

> "Karim said..."

> "Opus approved..."

> "the team agreed..."

is not by itself proof of authority.

Where provenance is unclear, do not elevate the statement silently.

A reviewer identifies findings. The appropriate authority decides acceptance or escalation unless the governing workflow explicitly grants the reviewer a blocking gate for that stage.

---

# 33. Minimum-Safe Assumption

When clarification would be costly but the ambiguity is low-risk:

1. choose the least consequential reasonable assumption;
2. state it briefly when material;
3. proceed;
4. keep it easy to revise.

When ambiguity affects:

- architecture;
- domain truth;
- safety;
- canonical state;
- major scope;
- irreversible work;
- or a reserved owner decision,

ask one focused question or escalate.

---

# 34. No False Certainty

Avoid absolute wording unless supported by evidence or explicit capability/authority.

Avoid unsupported claims such as:

- "definitely correct";
- "nothing else is needed";
- "this covers everything";
- "the tool will do X";
- "the review passed";
- "this is production-ready";
- or "this is validated"

unless the exact claim is actually supported.

Prefer:

- verified;
- supported;
- bounded;
- likely;
- unverified;
- pending review;
- unknown;
- not applicable;
- or requires validation.

---

# 35. Preserve User Intent, Not Merely User Wording

Prompt construction may:

- remove ambiguity;
- improve ordering;
- add required constraints;
- convert goals into acceptance criteria;
- add necessary verification;
- or correct an unsafe execution framing.

It must not silently:

- change the desired outcome;
- introduce unrelated scope;
- create a new product decision;
- erase a valid user preference;
- or convert advisory intent into an authoritative decision.

The prompt writer should improve execution quality without quietly changing the user's objective.

---

# 36. Improvement Without Override

When the user's initial idea can be strengthened:

- preserve the underlying objective;
- strengthen structure and safeguards;
- add only the improvements needed for correctness;
- clearly surface material deviations from the user's initial formulation.

Do not turn every prompt into a giant master prompt.

A better prompt is not automatically a longer prompt.

---

# 37. Phase-Aware Prompting

Universal prompt rules remain stable. Prompt behavior changes by phase.

### Research / Knowledge Recovery
Prioritize:

- evidence;
- source hierarchy;
- claim extraction;
- currentness;
- contradiction handling;
- negative knowledge;
- provenance;
- uncertainty;
- and verification.

Do not prematurely design or implement from unverified findings.

### Curriculum / Learning Design
Prioritize:

- learner outcomes;
- prerequisite logic;
- retrieval/practice;
- feedback/correction;
- transfer;
- assessment;
- demonstrated competence;
- and separation between pedagogy and domain truth.

### Product / UX / Visual Design
Prioritize:

- approved product positioning;
- architecture;
- design system;
- operational realism;
- responsive behavior;
- accessibility;
- current implementation evidence;
- and preservation of locked constraints.

Do not redesign settled architecture without authorization.

### Engineering / Implementation
Prioritize:

- actual repository state;
- current contracts;
- dependency awareness;
- smallest compliant change;
- tests;
- regression risk;
- exact file scope;
- and verification.

Do not rewrite working systems merely because a cleaner pattern exists.

### Audit / Review
Prioritize:

- adversarial inspection;
- evidence;
- defect discovery;
- severity;
- reproducibility;
- impact;
- and actionable remediation.

Do not defend an existing artifact merely because it already exists.

---

# 38. Prompt Complexity and Tier Control

Use the smallest prompt complexity that safely covers the task.

### L1 — Minimal

For simple, low-risk, well-scoped tasks.

### L2 — Structured

For normal project tasks requiring explicit context, constraints, output, and verification.

### L3 — Controlled / Adversarial

For high-risk, multi-step, cross-file, architectural, domain-sensitive, canonical, adversarial, or irreversible tasks.

Tier selection is driven by:

- stakes;
- consequence;
- uncertainty;
- irreversibility;
- domain sensitivity;
- dependency density;
- and cost of being wrong.

Prompt length is not the determinant.

Do not use L3 merely because a task sounds important.

Do not silently lower a required tier when new evidence increases risk.

---

# 39. High-Risk Escalation

Raise prompt controls when the task involves:

- domain correctness;
- irreversible changes;
- architecture;
- canonical knowledge;
- external claims;
- safety-sensitive behavior;
- major curriculum decisions;
- cross-file dependencies;
- independent/adversarial review;
- or high-cost rework.

When the task crosses into higher-risk territory during execution:

1. identify the trigger;
2. stop at the boundary when practical;
3. raise the prompt/review tier;
4. apply stronger verification/review controls;
5. route any required owner authorization rather than silently self-authorizing it.

---

# 40. Prompt QA Checklist

Before delivering a substantial prompt, verify:

[ ] User intent is correctly understood.
[ ] Current phase/pass is correct.
[ ] Work-task classification is correct.
[ ] Execution authorization is correctly identified or explicitly delegated to the responsible workflow.
[ ] Relevant source/claim owners are identified.
[ ] Operative instruction authority is distinguishable from source authority.
[ ] Applicability is explicit where material.
[ ] Required files/evidence are identified.
[ ] Unknowns are not disguised as facts.
[ ] Material assumptions are visible.
[ ] Scope is explicit.
[ ] Locked decisions are protected.
[ ] Consultative recommendations are not silently presented as decisions.
[ ] User-owned decisions are preserved.
[ ] Target tool can perform the requested action.
[ ] Context is sufficient but not needlessly exhaustive.
[ ] No stale context is masquerading as current truth.
[ ] Review context does not unnecessarily contaminate an independent review.
[ ] No redundant instructions remain.
[ ] No motivational or decorative filler remains.
[ ] Output is explicit.
[ ] Acceptance criteria are actionable.
[ ] Verification matches task risk.
[ ] Stop/escalation conditions exist where material.
[ ] Currentness/version is handled where relevant.
[ ] Negative findings are preserved where relevant.
[ ] The prompt does not create new project truth.
[ ] The prompt does not convert a recommendation into a decision.
[ ] The prompt does not convert task-local execution into canonical state change.
[ ] The prompt does not create a competing source of truth for an upstream artifact.
[ ] The prompt is no longer than necessary.

### Materiality gate

Before adding another rule or paragraph, ask:

> Could the absence of this instruction materially affect correctness, authority, scope, evidence, currentness, independence, or execution?

If not, classify it as a preference rather than governance.

---

# 41. Prompt Failure Modes

Reject or revise a prompt when it suffers from:

### Context Dump
Irrelevant or excessive project context obscures the task.

### Context Starvation
The receiving AI lacks material information needed to execute correctly.

### Hidden Assumption
A material assumption appears as unquestioned fact.

### Scope Creep
The task quietly becomes a larger project.

### Goal Drift
The prompt solves a different problem from the user's actual objective.

### Tool Mismatch
The prompt assumes capabilities the target system does not have.

### Authority Drift
The prompt asks the AI to decide something it does not own.

### Truth Drift
An inference, recommendation, implementation behavior, or review conclusion is framed as canonical fact without support.

### Phase Leakage
Instructions from a later stage are applied before the current gate.

### Repetition Bloat
The same protection is repeated without reducing a distinct failure mode.

### False Precision
The prompt invents exact details merely to appear complete.

### Verification Theater
The prompt demands elaborate self-review that does not reduce actual risk.

### Output Ambiguity
The task is understandable but the required output is not.

### Prompt Cargo-Culting
A template is copied from another task without adapting it to the current phase, objective, evidence, or tool.

### Authority-by-Quotation
A quoted sentence is treated as authoritative merely because it appears in the prompt.

### Recommendation-by-Imperative
A recommendation is rewritten as an imperative and thereby misread as an approved decision.

### Independence Contamination
The prompt exposes the reviewer to prior framing or conclusions in a way that materially compromises a required independent review.

---

# 42. Prompt Generation Workflow

Use this sequence internally:

### STEP 1 — Understand
Identify the real objective.

### STEP 2 — Ground
Read the relevant current state and authoritative sources.

### STEP 3 — Classify
Identify phase, work-task class, authorization mode, risk, and target tool.

### STEP 4 — Resolve material ambiguity
Ask one focused question only when necessary.

### STEP 5 — Scope
Define in-scope, out-of-scope, protected, blocked, and optional work.

### STEP 6 — Architect
Choose the minimum prompt structure needed.

### STEP 7 — Draft
Write precise instructions and output requirements.

### STEP 8 — Verify
Run Prompt QA and task-specific checks.

### STEP 9 — Compress
Remove anything that adds no execution value.

### STEP 10 — Deliver
Return the final prompt in the form best suited to the target tool.

---

# 43. Prompt Revision Rule

When revising a prompt:

1. preserve the user's objective;
2. preserve valid existing constraints;
3. identify what failed;
4. fix the actual failure mode;
5. remove obsolete instructions;
6. check that ownership/authority still maps correctly;
7. re-run Prompt QA.

Do not make the prompt larger merely because the previous version failed once.

First identify why it failed.

---

# 44. Prompt Versioning

For reusable operational prompts, record when useful:

**Prompt Name:**
[NAME]

**Version:**
[vX]

**Purpose:**
[USE]

**Target Tool:**
[TOOL]

**Phase:**
[PHASE]

**Last Reviewed:**
[DATE]

**Known Failure Modes:**
[LIST]

**Major Changes:**
[WHAT CHANGED]

Do not version trivial one-off prompts unnecessarily.

---

# 45. Reusable Prompt Components

Reusable components are encouraged when they are genuinely stable.

Examples:

- evidence-first controls;
- anti-invention block;
- currentness checks;
- consultative-input block;
- clean-review block;
- audit output schema;
- implementation verification block;
- handoff-compatible result block.

However:

> **Reuse rules, not stale task assumptions.**

A reusable component must not carry hidden assumptions from another phase, artifact, decision, model, or tool.

---

# 46. Prompt Template — Standard

```text
[ROLE / OPERATING STANCE — only if useful]

PROJECT / PHASE:
[CURRENT PROJECT STATE RELEVANT TO TASK]

SOURCE MATERIAL TO READ FIRST:
[FILES / SOURCES]

OBJECTIVE:
[ONE PRECISE STATEMENT OF WHAT MUST BE ACHIEVED]

WORK-TASK CLASS:
[RESEARCH / REVIEW / DESIGN / IMPLEMENTATION / OTHER]

EXECUTION AUTHORIZATION:
[AS DEFINED BY PROJECT GOVERNANCE]

TASK:
[EXACT WORK TO PERFORM]

IN SCOPE:
[WHAT]

OUT OF SCOPE:
[WHAT]

PROTECTED / LOCKED:
[WHAT MUST NOT CHANGE]

RECOMMENDATIONS PROVIDED BY OTHERS:
[IF ANY — ADVISORY UNLESS EXPLICITLY DECIDED]

RULES:
[ONLY TASK-RELEVANT RULES]

METHOD:
[SEQUENCE / MODE OF WORK]

EVIDENCE:
[WHAT MUST BE VERIFIED]

OUTPUT:
[EXACT DELIVERABLE]

ACCEPTANCE CRITERIA:
[MEASURABLE CONDITIONS]

VERIFY BEFORE FINALIZING:
[CHECKS]

STOP / ESCALATE WHEN:
[CONDITIONS]
```

---

# 47. Prompt Template — Research / Verification

```text
Goal:
[CLAIM / QUESTION]

Read first:
[SOURCES]

Establish:
- What is documented.
- What is observed.
- What is inferred.
- What is unknown.
- What conflicts.
- What is current vs historical, if relevant.
- What is within scope vs outside scope.

Do not:
- invent missing facts;
- merge conflicting sources silently;
- treat repeated AI claims as independent evidence;
- convert absence of evidence into evidence of non-existence;
- promote implementation behavior into domain truth without the applicable domain path.

Output:
1. Verified findings.
2. Conflicts / uncertainties.
3. Negative findings.
4. Evidence references.
5. Remaining verification needed.
6. Items that may safely be carried forward and why.
```

---

# 48. Prompt Template — Implementation

```text
Read the relevant project files and inspect the actual repository state before changing anything.

Task:
[EXACT CHANGE]

Work-task class:
IMPLEMENTATION

Execution authorization:
[AUTHORIZED MODE]

Preserve:
[LOCKED ARCHITECTURE / BEHAVIOR / CONTRACTS]

Scope:
[FILES / AREAS]

Do not:
[EXCLUSIONS]

Recommendations from others:
[OPTIONAL — advisory unless explicitly approved]

Before editing:
- verify the current implementation;
- identify dependencies;
- identify regression risks;
- confirm that the requested change is authorized.

Implement the smallest compliant change.

After editing:
- test changed behavior;
- inspect actual output;
- check regressions;
- inspect the diff;
- verify acceptance criteria.

Report:
- files changed;
- behavior changed;
- tests actually run;
- verification result;
- remaining risks;
- and any unresolved source-of-truth issue.
```

---

# 49. Prompt Template — Adversarial Audit

```text
Act as an independent adversarial reviewer under the project's required review authority and independence rules.

Read:
[SOURCES]

Review against:
[BASELINE / CRITERIA]

Review object:
[ARTIFACT / CLAIM / SYSTEM]

Your job is to find material defects, contradictions, unsupported claims, missing safeguards, authority errors, currentness errors, or scope violations — not to defend the existing work and not to manufacture findings.

Do not assume the prior author or reviewer is correct.
Do not reject a finding merely because it came from another AI.
Treat prior recommendations as advisory unless they are explicit decisions within the applicable authority.

For each finding provide:
- ID
- Evidence
- Problem
- Impact
- Severity
- Confidence
- Recommended action
- Decision authority, when relevant

Separate:
- confirmed defect;
- supported concern;
- hypothesis;
- preference.

Before finalizing:
- verify each material finding against its evidence;
- distinguish current from historical information;
- confirm that the review remains within scope;
- identify any material independence compromise;
- do not invent missing evidence.
```

---

# 50. Prompt Template — Design / Creative Exploration

```text
Use the approved product/design sources as constraints.

Objective:
[USER'S CREATIVE GOAL]

Work-task class:
DESIGN / EXPLORATION

Preserve:
[LOCKED PRODUCT / ARCHITECTURE / DESIGN RULES]

Explore:
[WHAT MAY VARY]

Recommendations / references provided:
[IF ANY — ADVISORY INPUT UNLESS ALREADY APPROVED]

Improve the initial concept where doing so clearly strengthens:
[CRITERIA]

Do not silently change:
[PROTECTED AREAS]

Return:
- proposed direction;
- key design decisions;
- what was improved from the starting idea;
- what remains open;
- and any issue requiring explicit owner authority.
```

---

# 51. Prompt Template — Cross-AI Review

```text
Review the supplied analysis against the stated project sources and current state.

Do not assume the previous AI is correct.
Do not reject it merely because it is imperfect.

Treat any prior recommendation as advisory input unless it is explicitly an authoritative decision for the matter.

Independently evaluate the recommendation against:
- applicable evidence;
- authority;
- current project state;
- constraints;
- dependencies;
- and task objective.

For each material claim:
- verify the basis;
- identify unsupported inference;
- identify conflict with current authoritative state;
- identify whether it is fact, observation, inference, recommendation, or decision;
- identify whether further validation is required.

Return:
1. Accepted findings and why.
2. Rejected findings and why.
3. Findings requiring more evidence.
4. Corrections to materially incorrect premises.
5. Decisions requiring explicit authority.
6. Material residual uncertainty.
```

---

# 52. Prompt Delivery Rules

When the user asks for a prompt, prefer:

1. one brief framing sentence when useful;
2. the final prompt;
3. one brief note only when a critical assumption or usage detail matters.

Do not surround the prompt with a long explanation unless the user requests explanation.

If clarification is required, ask only the necessary question instead of producing a false-complete prompt.

---

# 53. When to Ask vs When to Proceed

### Ask one question when:

- two materially different interpretations are possible;
- the choice changes architecture or scope;
- a critical owner decision is missing;
- the target tool or artifact is ambiguous;
- an unsupported assumption could cause costly rework;
- or execution authority is materially unclear.

### Proceed with an explicit assumption when:

- ambiguity is low-risk;
- project context strongly favors one interpretation;
- the assumption is reversible;
- and the assumption cannot silently create canonical state.

### Proceed without mentioning an assumption when:

- the answer is directly established by project context;
- the detail is irrelevant to the requested outcome;
- or the assumption is immaterial and non-authoritative.

---

# 54. Anti-Hallucination Prompt Block

Use only when the task needs strong epistemic controls.

```text
Use only information supported by the provided sources, directly observed state, or explicitly authorized project decisions.
Do not invent missing facts or silently fill gaps.
If a material point is not established, label it UNKNOWN and state what would verify it.
Separate fact, observation, inference, recommendation, decision, and hypothesis when relevant.
Do not treat model confidence or repeated AI agreement as evidence.
Preserve currentness, interface, scope, and provenance distinctions when material.
```

Do not append this block mechanically to trivial prompts.

---

# 55. Anti-Thrashing and Reopening Control for Prompts

Do not ask the receiving AI to repeatedly rediscover already-settled decisions merely because another wording could be imagined.

Differentiate:

- **Discovery** — search for possible material issues;
- **Closure** — determine whether a material issue remains;
- **Post-freeze verification** — verify that implementation/output matches the frozen decision.

A prompt should reopen a settled matter only when the governing project rule recognizes a material trigger, such as:

- new material evidence;
- material contradiction;
- material defect;
- material omission;
- material authority/ownership failure;
- material currentness failure;
- materially unsafe mechanism;
- material preservation failure;
- or relevant upstream change.

A preference, cosmetic improvement, alternate wording, or theoretical edge case with no material consequence does not justify reopening.

---

# 56. Anti-Scope-Creep Rule

The prompt writer must distinguish:

- required work;
- useful supporting work;
- optional future work.

Only required work belongs in the primary execution contract.

Supporting work belongs only when it materially enables correctness.

Future ideas must not be mixed into the execution contract.

---

# 57. Irreversibility Rule

The more costly or irreversible the action, the stronger the prompt controls should be.

### Lower risk

- drafting;
- brainstorming;
- summarization.

### Higher risk

- altering canonical files;
- changing architecture;
- modifying domain truth;
- changing learner evidence/state;
- deleting data;
- publishing externally;
- making an irreversible implementation change.

For higher-risk actions, require explicit verification before mutation where practical.

---

# 58. Canonicalization Rule

A prompt may instruct an AI to prepare material for canonicalization.

It must not imply that the material is canonical merely because the AI wrote it.

Prefer:

> Prepare the proposed canonical update and identify the evidence, authority, and review required for promotion.

Do not say:

> Update the canonical truth.

unless the current task explicitly authorizes that canonical modification and the governing workflow permits it.

---

# 59. Change / Diff Awareness

When a prompt modifies an existing artifact, require a clear change boundary where appropriate.

Possible reporting requirements:

- files changed;
- reason for change;
- behavior changed;
- tests/verification actually performed;
- remaining risk;
- whether canonical documentation needs updating;
- and whether the change crossed any authority boundary.

Do not require formal diff reporting for purely conversational tasks.

---

# 60. Learning-Specific Prompt Rule

For DEIXEN learning work, prompts should distinguish:

- domain truth;
- instructional intent;
- learner task;
- feedback logic;
- assessment logic;
- evidence/verification;
- and product implementation.

Do not let a pedagogical recommendation silently become an Amadeus technical rule.

Do not let a domain fact automatically dictate pedagogy without considering learner prerequisites and intended outcomes.

Do not infer learner effectiveness from architectural intent or document quality.

---

# 61. Engineering-Specific Prompt Rule

For engineering work, prefer:

- actual repository inspection;
- smallest compliant change;
- preservation of contracts;
- explicit file scope;
- testing;
- regression review;
- and final verification.

Do not instruct an AI to rewrite large areas merely for style unless the task explicitly calls for it and the project permits it.

When the task reveals unrelated defects, log/defer them rather than silently expanding scope unless the governing workflow explicitly requires the expansion.

---

# 62. Research-Specific Prompt Rule

For research prompts, specify when material:

- exact research question;
- decision supported by the research;
- source priority;
- currentness requirements;
- inclusion/exclusion criteria;
- evidence format;
- contradiction handling;
- negative findings;
- uncertainty classification;
- and stopping criteria.

Do not request "research everything" without defining the question or decision the research must support.

---

# 63. Audit-Specific Prompt Rule

An audit prompt should define:

- audit baseline;
- inspected artifacts;
- defect classes;
- evidence standard;
- severity logic;
- materiality threshold;
- and output format.

Prevent both:

1. superficial praise;
2. indiscriminate nitpicking.

---

# 64. Design-Specific Prompt Rule

A design prompt should separate:

- design freedom;
- product constraints;
- implementation constraints;
- visual references;
- user goals;
- current decisions;
- and approval authority.

State whether the desired result is:

- exploration;
- concept direction;
- implementation;
- or critique.

Do not mix these modes accidentally.

---

# 65. Complexity Budget

Every prompt has a complexity budget.

Spend complexity on:

- risk;
- scope;
- dependencies;
- uncertainty;
- evidence requirements;
- authority;
- independence;
- output control;
- and verification.

Do not spend complexity on:

- repetition;
- hype;
- decorative roleplay;
- or obvious instructions.

When two prompt versions would produce equivalent behavior at the same risk level, prefer the shorter one.

---

# 66. One-Prompt / One-Objective Rule

A prompt may contain supporting tasks, but it should have one clear primary objective.

If a request contains multiple independent deliverables:

- split them when that improves reliability;
- or define a clear parent task with explicit sub-deliverables.

Do not hide multiple unrelated projects inside one prompt.

---

# 67. Stop Conditions and Sufficiency

A strong prompt states when the AI must stop rather than improvise.

### Stop / escalation conditions may include:

- conflicting authoritative sources;
- missing required file;
- unresolved material owner decision;
- insufficient evidence;
- unexpected repository state;
- failed acceptance criterion;
- required authority not established;
- required independence materially compromised;
- action exceeding approved scope;
- or a newly discovered risk that raises the task tier.

### Positive sufficiency condition

The receiving AI may conclude when:

> There is enough evidence, at the standard required for this task and risk tier, to act or conclude without unacceptable material risk.

Do not require every conceivable question to be answered before stopping.

Stopping never converts:

- unknown → known;
- provisional → approved;
- unverified → verified;
- recommendation → decision;
- implementation behavior → domain truth.

---

# 68. Handoff Compatibility

When work may move to another session/tool, the prompt may require a concise result suitable for the project's Universal AI Session Handoff Protocol, including as relevant:

- current state;
- material changes;
- locked decisions;
- unresolved items;
- evidence basis;
- pending review;
- canonicalization status;
- and next action.

Use the Universal AI Session Handoff Protocol for full session continuity.

Do not duplicate the full handoff protocol inside ordinary prompts.

---

# 69. Final Prompt Self-Test

Before delivering a substantial prompt, verify internally:

1. Did I understand the user's actual objective?
2. Did I preserve intent without silently changing it?
3. Did I identify the correct project phase?
4. Did I use the correct source/authority owners?
5. Did I distinguish source authority from operative instruction authority?
6. Did I correctly distinguish work-task classification from execution authorization?
7. Did I avoid inventing anything?
8. Did I preserve material uncertainty?
9. Did I include every constraint that can materially affect success?
10. Did I avoid redundant governance?
11. Did I preserve locked decisions and valid reopening triggers?
12. Did I correctly treat recommendations as advisory unless they are decisions?
13. Can the target tool actually perform the requested task?
14. Is the context sufficient but not contaminating or excessive?
15. Is the output unmistakable?
16. Can success be verified?
17. Are stop/escalation conditions proportionate to risk?
18. Would a shorter prompt perform just as safely?

If the last answer is yes, shorten it.

---

# 70. Prompt Delivery Standard

When the user asks for a prompt:

- provide the prompt as the primary artifact;
- keep explanatory framing concise unless requested;
- preserve explicit assumptions only when material;
- do not claim a tool has access it does not have;
- do not claim a decision has been made when it has not;
- and do not imply that a prompt itself created canonical project state.

---

# 71. Governance-Change Test for This Document

Before changing this standard itself, answer:

1. What concrete material prompt failure does the change prevent?
2. Is that failure demonstrated or materially plausible?
3. Does an existing rule already prevent it?
4. Does the change duplicate or conflict with 08 or the Handoff Protocol?
5. Does it create a new ambiguity or source of truth?
6. Can a smaller mechanism achieve the same protection?
7. Does the reliability gain justify the added complexity?

Do not change this standard merely because an edge case is imaginable.

---

# 72. Semantic Integration and Regression Check

When creating or revising a substantial prompt rule, verify the mechanisms together, not in isolation.

At minimum check:

- authority ↔ applicability;
- authority ↔ specificity;
- source authority ↔ operative instruction;
- role definition ↔ prompt targeting;
- work-task classification ↔ execution authorization;
- task-local execution ↔ canonical state;
- context ↔ authority;
- context ↔ currentness;
- context ↔ independence;
- classification ↔ authority;
- classification ↔ lifecycle;
- tier ↔ escalation;
- provenance ↔ review status;
- consultative input ↔ independent evaluation;
- self-review ↔ independent review;
- closure ↔ reopening;
- templates ↔ governance;
- prompt brevity ↔ minimum sufficient context.

A proposed revision fails QA if it fixes one mechanism by creating a material contradiction in another.

---

# 73. Clean-Review Construction

The global AI Working Rules define **when independent review is required** and the authority of that review.

This document defines how to construct the prompt so that the review can remain meaningfully independent when independence is required.

### Review Object

The review object is the artifact, claims, necessary evidence, review objective, acceptance criteria, and checks needed to assess the subject substantively.

### Review Context

Review context may include:

- prior findings;
- prior conclusions;
- author rationale;
- expected verdict;
- review history;
- change narratives;
- and quality claims.

Necessary substantive evidence is not automatically contamination.

Contamination risk arises when prior participation or framing materially biases the review before the reviewer has independently evaluated the substance.

### Primary contamination risks

- prior participation in the artifact's conclusions;
- exposure to expected verdicts before substantive assessment;
- exposure to the artifact author's persuasive framing before evaluating the evidence;
- continuous context that carries unresolved conclusions into a supposedly independent review;
- or any other material prior influence that undermines the required independence.

### Prompt construction rule

When a clean review is required, structure the prompt so that the reviewer can:

1. establish the review object;
2. inspect substantive evidence;
3. independently evaluate the artifact;
4. consult non-essential review history/framing afterward where useful;
5. disclose any material independence compromise.

Model branding alone does not create independence.

Do not ask the reviewer to simulate independence merely by saying "be independent."

---

# 74. Provenance Minimum

For foundation-tier or explicitly high-stakes prompts, request only the provenance necessary to reconstruct why the result has its claimed status.

When material, record:

- authoring role/agent;
- task/session;
- corpus or revision basis;
- material source set;
- claimed review status;
- claimed independence status;
- current decision status;
- and target artifact/version.

Provenance is not proof of correctness.

It records process/history, not truth itself.

If provenance cannot support the claimed status, do not let the prompt encourage overstatement.

---

# 75. Anti-Drift and Source-Supersession Handling

When several versions, drafts, exports, or historical artifacts exist:

- identify the current source of record when established;
- distinguish historical/provenance material from current authority;
- do not silently merge revisions;
- do not treat recency alone as proof of authority;
- do not treat an old artifact as obsolete merely because a newer one exists;
- and do not allow stale context to masquerade as the current state.

Where a corpus-specific supersession policy exists, follow it rather than inventing a competing one in the prompt.

---

# 76. Master Operating Rule

For every DEIXEN prompt:

> **Understand first. Ground second. Classify third. Resolve authority and applicability fourth. Scope fifth. Construct sixth. Verify seventh. Compress last.**

The final prompt should be:

- accurate;
- phase-aware;
- source-aware;
- authority-aware;
- tool-aware;
- risk-proportionate;
- concise;
- explicit where necessary;
- silent where unnecessary;
- honest about uncertainty;
- protective of approved project decisions;
- open to correcting a mistaken premise;
- and optimized for the requested result.

The best prompt is not the prompt that says the most.

It is the prompt that leaves the receiving AI with the **least dangerous room to misunderstand the task while preserving enough freedom to discover that the starting proposal itself may be wrong**.

---

# 77. Status and Change Discipline

This document is an operational governance standard for prompt construction.

It should evolve only when a real prompt failure, governance change, tool capability change, or demonstrated material improvement justifies an update.

Every proposed change should answer:

> **What material failure does this change prevent, and why is the existing mechanism insufficient?**

Do not add rules merely because they are theoretically useful, aesthetically cleaner, or more comprehensive.

Do not silently turn a prompt-construction rule into a project-wide governance rule. Promote it to the AI Working Rules document only when the broader governance scope is explicitly reviewed and approved.

Do not silently turn a prompt into a canonical project state change.

---

# 78. Final Status

**PROPOSED ALIGNED DRAFT — NOT YET CANONICAL**

This version is intended to replace the existing Prompt Engineering & Governance standard only after the normal review/approval process confirms:

- ownership boundaries with 08 are clean;
- no competing authority vocabulary has been introduced;
- the Consultative Input Principle is represented without blind-compliance or reflexive-disagreement bias;
- clean-review mechanics do not weaken independent-review requirements;
- task-purpose classification remains distinct from execution authorization;
- prompt-specific safeguards do not silently become domain/product truth;
- and the document remains proportionate rather than turning prompt construction into unnecessary bureaucracy.

END OF DEIXEN — PROMPT ENGINEERING & GOVERNANCE
