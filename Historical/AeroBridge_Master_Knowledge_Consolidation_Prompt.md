AeroBridge — Master Knowledge Consolidation & Canonical Source-of-Truth Reconstruction
You are the AeroBridge Knowledge Consolidation Lead, Technical Architect, Historical Knowledge Reconciliation Lead, and Product Knowledge Architect.
This is a knowledge reconstruction and consolidation task, not a simple document comparison, summary, or file merge.
Your job is to reconstruct the strongest, most accurate, internally consistent, and future-proof single canonical knowledge system for AeroBridge from two historical states of the SAME project.
The goal is to eliminate the current fragmentation between the OLD and NEW project knowledge and produce one authoritative foundation from which AeroBridge can continue.
1. PROJECT CONTEXT
AeroBridge is one project that evolved over time.
I worked on an older version of AeroBridge, then I was away from the project for a period, and later I created/worked on a newer version.
Therefore:
OLD and NEW are not two competing products.
They are two historical snapshots of the same AeroBridge project.
Both may contain important knowledge.
Some valuable knowledge exists only in OLD.
Some valuable knowledge exists only in NEW.
Some exists in both but with different wording, architecture, assumptions, rules, or decisions.
Some historical decisions have been superseded.
Some current decisions intentionally replaced old decisions.
Some knowledge may have been accidentally lost during the transition from OLD to NEW.
Your responsibility is to recover the valuable knowledge across the project's history and consolidate it into one coherent CURRENT AeroBridge knowledge system.
The final mental model must become:
OLD PROJECT + NEW PROJECT → ONE CANONICAL AEROBRIDGE KNOWLEDGE BASE
I should no longer need to maintain two partially overlapping project histories just to understand AeroBridge.
2. SOURCE FILES
CURRENT / NEW PROJECT
These files belong to the newer project state.
They represent the current baseline and current direction, but being NEW does NOT automatically make every statement correct.
AeroBridge_Product_Architecture_and_Rules.md
AeroBridge_Master_Context.md
AeroBridge_Design_System_and_UX_Principles.md
The supplied filename may appear with a typo such as .3md; interpret it as the intended Markdown file if that is how it exists.
AeroBridge_Decisions_and_Current_State.md
AeroBridge_AI_Working_Rules.md
HISTORICAL / OLD PROJECT
These files belong to the older state of the same project.
PROJECT-20.md
SDD.md
AMADEUS_CURRICULUM.md
COMMAND_REFERENCE.md — IMPORTANT
PRODUCT_STRATEGY_UX_ARCHITECTURE-1.md
DESIGN_SYSTEM_UI_BLUEPRINT.md
DEVELOPMENT_RULES.md
There are 12 source files in total.
You must review all of them.
Do not skip a file because its filename looks redundant, outdated, similar, or unimportant.
A file may contain unique knowledge even when most of it duplicates another source.
CURRENT REPOSITORY SNAPSHOT — aerobridge-main.zip

In addition to the 12 OLD and NEW knowledge files listed above, I am providing the current AeroBridge repository as:

aerobridge-main.zip

This repository represents the actual current implementation state of AeroBridge at the time of this consolidation.

It is especially important because the current repository still contains implementation and/or layout work originating from the OLD project, while the NEW project contains a different and more current direction.

Therefore, you must inspect the repository as part of this consolidation.

However, there is a critical distinction:

The repository is evidence of implementation state, NOT an automatic Source of Truth for product decisions, technical decisions, visual decisions, or Amadeus behavior.

Code can contain:

• legacy implementation,

• incomplete implementation,

• temporary experiments,

• outdated architecture,

• accidental behavior,

• bugs,

• partially migrated features,

• undocumented functionality,

• or implementation that no longer reflects current decisions.

Never assume:

"It exists in the repository, therefore it is approved."

Likewise, never assume:

"It is not implemented in the repository, therefore it is not part of AeroBridge."

The repository must be treated as implementation evidence that must be reconciled with the knowledge sources.

1. REPOSITORY INSPECTION OBJECTIVE

Inspect aerobridge-main.zip to determine the actual current state of the project.

Your purpose is NOT to modify the repository.

Your purpose is to establish:

What AeroBridge actually contains today, what it appears to have inherited from OLD, what reflects NEW, what is incomplete, and where implementation diverges from the consolidated knowledge.

Use the repository to discover information that the documentation alone cannot reliably reveal.

2. WHAT TO INVESTIGATE

Inspect the repository for at least:

Architecture

Determine:

• actual framework and stack,

• actual project structure,

• component organization,

• routing,

• state management,

• persistence,

• data structures,

• engine organization,

• imports/dependencies,

• build configuration,

• PWA/offline behavior where applicable,

• and other meaningful architectural characteristics.

Pay particular attention to whether the current repository actually reflects the declared React architecture.

Product Structure

Determine:

• actual pages/routes,

• implemented screens,

• current navigation,

• major user flows,

• implemented features,

• partially implemented features,

• hidden or unused features,

• and functionality inherited from the OLD project.

Pay special attention to the known distinction between:

• OLD project: 3-page structure

• NEW project: 5-page structure

Do not automatically assume the repository currently follows the NEW 5-page structure.

Inspect what actually exists.

Visual / Layout Heritage

This is particularly important.

The repository is currently connected to layout/visual implementation originating from the OLD project.

Determine:

• which parts of the current UI appear to originate from OLD,

• which parts appear to originate from NEW,

• which parts are mixed,

• which visual structures are legacy,

• which visual structures are newer,

• and which design ideas are actually implemented rather than merely documented.

However:

Do NOT treat the currently implemented visual design as approved final design.

The future visual direction remains intentionally open and will later be explored with Claude Design and finalized by Malik.

Therefore, the repository's current visual implementation is evidence of history/current implementation, not a final visual authority.

3. KNOWLEDGE ↔ REPOSITORY RECONCILIATION

For important areas, compare:

DOCUMENTED KNOWLEDGE ↔ ACTUAL REPOSITORY IMPLEMENTATION

Identify at least these types of divergence:

KNOWLEDGE EXISTS, IMPLEMENTATION EXISTS

Documented and apparently implemented.

KNOWLEDGE EXISTS, IMPLEMENTATION MISSING

Documented requirement/behavior that has not yet been implemented.

IMPLEMENTATION EXISTS, KNOWLEDGE MISSING

Important behavior or functionality exists in code but is not adequately documented.

This category is extremely important because such knowledge may have been lost from the written documentation during the transition between project generations.

OLD KNOWLEDGE EXISTS, IMPLEMENTATION EXISTS

Potentially valuable historical functionality still surviving in the current repository.

OLD KNOWLEDGE EXISTS, IMPLEMENTATION MISSING

Determine whether it was intentionally removed, accidentally lost, or simply not implemented yet.

NEW KNOWLEDGE EXISTS, IMPLEMENTATION DIFFERS

Determine whether the implementation is incomplete, outdated, or intentionally different.

IMPLEMENTATION CONFLICTS WITH CURRENT KNOWLEDGE

Identify the divergence explicitly.

Do NOT automatically change the knowledge to match the code.

Do NOT automatically treat the code as correct.

Determine which represents the actual intended current truth.

4. IMPLEMENTATION EVIDENCE MUST BE CLASSIFIED

When extracting information from the repository, classify it separately from normal project knowledge.

Use labels such as:

• IMPLEMENTED & DOCUMENTED

• IMPLEMENTED BUT UNDOCUMENTED

• PARTIALLY IMPLEMENTED

• DOCUMENTED BUT NOT IMPLEMENTED

• LEGACY IMPLEMENTATION

• CURRENT IMPLEMENTATION

• EXPERIMENTAL / UNCERTAIN

• IMPLEMENTATION CONFLICT

• REQUIRES REVIEW

Do not silently promote implementation details into canonical requirements.

5. RECOVER LOST KNOWLEDGE FROM THE REPOSITORY

One of the explicit purposes of inspecting aerobridge-main.zip is to detect valuable knowledge that may have disappeared from the written documentation.

For example, the repository may contain:

• a validation rule,

• a workflow,

• a terminal behavior,

• a state transition,

• a Coach rule,

• an error case,

• a product interaction,

• a data relationship,

• or another meaningful behavior

that exists in implementation but is absent or incomplete in the OLD and NEW documents.

If you discover such knowledge:

• identify it,

• understand it,

• determine whether it is intentional and still valuable,

• determine its historical origin if possible,

• compare it against OLD and NEW knowledge,

• classify it,

• and preserve it in the appropriate canonical location if it remains valid.

Do not lose valuable behavior merely because it was documented only in code.

6. DO NOT MISTAKE LEGACY CODE FOR CURRENT TRUTH

This is mandatory.

The fact that a behavior exists in the repository does NOT mean it should survive.

The behavior may be:

• legacy,

• accidental,

• technically obsolete,

• inconsistent with current architecture,

• inconsistent with current product direction,

• inconsistent with correct Amadeus behavior,

• or simply unfinished.

Therefore:

Repository presence is evidence, not approval.

When legacy code conflicts with current intended behavior, document the conflict and determine the correct final state.

7. DO NOT MISTAKE MISSING CODE FOR MISSING PRODUCT KNOWLEDGE

The inverse is equally important.

If a feature or rule is documented but not currently implemented, do NOT conclude that it was abandoned.

It may simply be:

• planned,

• partially implemented,

• lost during migration,

• waiting for integration,

• or not yet reached in the development sequence.

Use the knowledge sources to establish intent.

8. AMADEUS-SPECIFIC REPOSITORY SAFETY

Apply the strongest possible scrutiny to Amadeus-related code.

Inspect the repository for:

• command parsers,

• command definitions,

• validation logic,

• command handlers,

• state transitions,

• response generation,

• PNR behavior,

• availability/sell logic,

• passenger handling,

• ticketing logic,

• pricing,

• SSR/OSI,

• seats,

• meals,

• exchanges/refunds,

• and other Amadeus-related behavior that is actually present.

The repository may reveal implemented Amadeus behavior that is not fully described in the documents.

However:

Implemented code is NOT sufficient proof that an Amadeus behavior is correct.

If repository behavior conflicts with verified Amadeus knowledge, the verified Amadeus truth wins.

If the repository behavior is uncertain, mark it for verification.

Never allow the repository to become an unverified source of Amadeus truth.

9. COACH-SPECIFIC REPOSITORY INSPECTION

Because the Coach is the second-highest product priority, inspect the repository specifically for the actual Coach implementation.

Determine:

• how the Coach observes terminal activity,

• what state it receives,

• what triggers it,

• what errors it detects,

• how it selects hints,

• how it decides when to intervene,

• how it responds to repeated mistakes,

• how it determines next steps,

• what information it exposes,

• and what logic already exists.

Compare the actual implementation against:

• OLD Coach knowledge,

• NEW Coach knowledge,

• and the desired professional terminal-linked Coach concept.

Identify:

• implemented strengths,

• missing behavior,

• weak logic,

• inconsistent behavior,

• legacy logic,

• and opportunities for strengthening the Coach.

Do not rewrite the Coach during this task.

Document the findings for the later implementation phase.

10. CURRENT REPOSITORY STATUS REPORT

Create a dedicated section in:

AeroBridge_Knowledge_Consolidation_Plan.md

called:

CURRENT REPOSITORY REALITY

It should summarize:

• actual architecture,

• actual page structure,

• implemented major features,

• major legacy areas,

• major NEW areas,

• unfinished areas,

• important undocumented implementation,

• major knowledge ↔ code mismatches,

• major Amadeus implementation risks,

• and important visual/layout inheritance from OLD.

This section must be updated if deeper inspection changes earlier conclusions.

11. REPOSITORY AS A THIRD DIMENSION — NOT A THIRD PROJECT

Think of the consolidation as having three evidence dimensions:

OLD KNOWLEDGE

What AeroBridge historically knew and intended.

NEW KNOWLEDGE

What AeroBridge currently documents and intends.

CURRENT REPOSITORY

What AeroBridge actually implements today.

Your task is to reconcile all three without confusing their roles.

Conceptually:

OLD KNOWLEDGE + NEW KNOWLEDGE + CURRENT IMPLEMENTATION EVIDENCE

↓

RECONSTRUCT THE STRONGEST CURRENT AEROBRIDGE TRUTH

The repository does NOT compete with OLD and NEW as another "version" to choose from.

It provides implementation evidence that helps explain what happened between them and what is actually alive today.

12. REPOSITORY → CANONICAL KNOWLEDGE RULE

Important repository discoveries may be incorporated into the final canonical knowledge when they are:

• clearly intentional,

• still valid,

• consistent with current direction,

• and properly verified.

Do NOT automatically transfer every implementation detail into Knowledge.

Only promote implementation-derived information when it represents meaningful project knowledge.

Examples:

Worth promoting

• a previously undocumented business rule,

• a meaningful state model,

• a Coach interaction rule,

• an important workflow,

• a meaningful product behavior,

• or another durable project concept.

Usually NOT worth promoting

• arbitrary variable names,

• temporary component structure,

• incidental implementation details,

• obsolete technical hacks,

• generated files,

• irrelevant library configuration,

• or other details that do not represent durable project knowledge.

13. PRE-IMPLEMENTATION RISK RECONCILIATION

Before the future implementation phase begins, use the repository findings to perform a final reconciliation between:

CANONICAL KNOWLEDGE ↔ CURRENT REPOSITORY REALITY

Identify anything that could create future implementation confusion.

In particular, identify:

• legacy structures that could accidentally be preserved,

• current code that contradicts the canonical architecture,

• old layout code that could accidentally constrain future design,

• undocumented behavior that needs a decision,

• incomplete features that may be mistaken for completed functionality,

• Amadeus logic that requires verification,

• Coach behavior that requires redesign,

• and technical debt that must be handled deliberately.

The goal is to ensure the future implementation starts from a known baseline rather than inheriting accidental history.

14. NO REPOSITORY MODIFICATION DURING THIS CONSOLIDATION

Do not modify aerobridge-main.zip or the repository during the knowledge-consolidation phase unless I explicitly ask you to do so.

This phase is for:

Inspect → Understand → Reconcile → Document

not:

Inspect → Automatically Rewrite

The repository will be addressed later by Claude Code after the canonical knowledge and approved design direction are established.

15. FINAL REPOSITORY COMPLETION CHECK

Before declaring consolidation complete, verify that you understand:

• what is actually implemented today,

• what is legacy,

• what is current,

• what is incomplete,

• what is undocumented,

• what is documented but absent,

• what came from OLD,

• what reflects NEW,

• what conflicts with canonical knowledge,

• what requires future implementation,

• what requires Amadeus verification,

• and what must not constrain future visual design.

Do not claim that the repository is fully understood merely because the source tree was listed.

You must understand the meaningful behavior and architecture represented by the repository.

The final goal is to prevent future AeroBridge work from accidentally rebuilding, preserving, or trusting the wrong historical implementation.


3. THE CORE PRINCIPLE
Your objective is NOT:
"Choose the NEW project."
Your objective is NOT:
"Merge the two projects evenly."
Your objective is:
Recover the strongest truthful version of AeroBridge from its full history, while preserving current decisions and current architecture where those are intentionally established.
Use this principle throughout the operation:
Optimize for the strongest truthful version of AeroBridge, not for the newest document.
And:
Optimize for useful authoritative knowledge, not for the smallest number of files.
4. NEW = CURRENT BASELINE, NOT AUTOMATIC TRUTH
The NEW project represents the current baseline and the current direction of AeroBridge.
Therefore, unless explicitly overridden by a stronger factual or intentional project decision:
React is the current technical direction.
The NEW project's 5-page structure is the current product structure.
The OLD 3-page structure is historical.
Current project architecture takes precedence over obsolete historical implementation architecture.
Current explicitly documented decisions should not be casually reopened.
However:
NEW does not automatically win every conflict.
If OLD contains a stronger:
business rule,
workflow,
functional behavior,
domain rule,
Amadeus fact,
training mechanic,
Coach rule,
product insight,
edge case,
or other valuable knowledge,
recover it and integrate it into the current system.
Likewise, NEW-only knowledge must be preserved when valid.
5. KNOWLEDGE, NOT IMPLEMENTATION, IS WHAT YOU ARE MERGING
Always distinguish:
A. KNOWLEDGE
Examples:
requirements,
business rules,
command behavior,
workflows,
product logic,
training logic,
edge cases,
learning principles,
Coach behavior,
UX principles,
technical principles.
B. IMPLEMENTATION
Examples:
Vanilla JavaScript structure,
React component structure,
exact file organization,
historical code patterns,
obsolete architectural patterns.
An old implementation may be obsolete while its underlying knowledge remains extremely valuable.
Do not discard valuable knowledge simply because its original implementation is no longer appropriate.
Instead:
Extract the underlying behavior, principle, rule, or requirement and reconstruct it correctly inside the current architecture.
Example:
OLD:
Vanilla implementation
NEW:
React implementation
FINAL:
React remains the architecture.
Valuable business/functional knowledge from OLD is recovered and represented correctly in the React-era system.
6. MANDATORY WORKFLOW
You must follow this workflow:
DISCOVER → INVENTORY → MAP → EXTRACT → RECONCILE → VERIFY → DECIDE → CONSOLIDATE → PRE-IMPLEMENTATION READINESS REVIEW → CROSS-AUDIT → FINALIZE
Do not jump directly from reading files to writing final documents.
Phase 1 — DISCOVER
Understand the whole source landscape.
Identify:
what each file is,
what each file is intended to contain,
what project era it belongs to,
what domains it covers,
what appears unique,
what appears duplicated.
Phase 2 — INVENTORY
Create the working inventory of all source files and major topics.
Phase 3 — MAP
Map:
OLD file → NEW file,
old concept → current concept,
old rule → new rule,
old workflow → new workflow,
old architecture → current architecture,
old Coach logic → current Coach concept,
old design knowledge → current design exploration.
Do not assume identical filenames mean identical scope.
Phase 4 — EXTRACT
Extract substantive knowledge before deciding whether it survives.
Phase 5 — RECONCILE
Compare and reconcile the extracted knowledge.
Phase 6 — VERIFY
Especially verify factual/high-risk knowledge such as Amadeus behavior.
Phase 7 — DECIDE
Classify each meaningful item into an explicit state.
Phase 8 — CONSOLIDATE
Build the final canonical files.
Phase 9 — CROSS-AUDIT
Check the final files against each other for contradictions, omissions, duplicated authority, and accidental historical leakage.
Phase 10 — FINALIZE
Only after all critical issues are handled should the process be declared complete.
7. LIVING CONSOLIDATION PLAN
Create and maintain:
AeroBridge_Knowledge_Consolidation_Plan.md
This is a living control document for the entire operation.
Do not create it once and abandon it.
Update it throughout the process.
It must track at minimum:
Source Inventory
All 13 source files.
File Mapping
Conceptual relationships between OLD and NEW files.
Topic Mapping
Where each major topic appears across the two project generations.
Reconciliation Status
Use explicit states such as:
PENDING
READ
MAPPED
EXTRACTED
RECONCILING
CONFLICT FOUND
VERIFICATION NEEDED
DECISION REQUIRED
RECONCILED
FINALIZED
Recovered Knowledge
Important knowledge recovered from OLD.
Current Knowledge
Important knowledge preserved from NEW.
Conflicts
Important contradictions and their resolutions.
Amadeus Verification Issues
Anything that must not be encoded as canonical until verified.
Open Decisions
Especially visual/product decisions requiring my approval.
Recommendations
Strong improvements discovered beyond the source material.
Final Canonical Files
Final authoritative files and completion status.
Final Verification
Evidence that the whole operation has been completed correctly.
8. FILE-LEVEL, SECTION-LEVEL, TOPIC-LEVEL, RULE-LEVEL ANALYSIS
Do not stop at high-level document comparison.
Analyze at multiple levels.
FILE LEVEL
What role does the document serve?
SECTION LEVEL
What unique information is contributed?
TOPIC LEVEL
What is the complete knowledge about this topic across OLD and NEW?
RULE LEVEL
What exactly does each rule say?
COMMAND LEVEL
What exactly does each Amadeus command or command family do?
DECISION LEVEL
Which decision is current, which is superseded, and why?
For high-value topics, compare at the finest useful level.
This is especially important for:
Amadeus commands,
business rules,
workflows,
curriculum,
Coach logic,
architecture,
product requirements,
state behavior,
validations,
and edge cases.
9. HARD RULE: NEVER SILENTLY DISCARD UNIQUE OLD KNOWLEDGE
This is mandatory.
If something meaningful exists in OLD and not in NEW, you must evaluate it before deciding its fate.
No unique historical knowledge may disappear silently.
Every meaningful unique OLD item must end in one of these classifications:
PRESERVE
MERGE
SUPERSEDE
OBSOLETE
VERIFY
RECOMMENDATION
Document the reason.
Likewise, meaningful NEW-only knowledge must be classified and preserved appropriately.
10. CLASSIFICATION SYSTEM
Use explicit classifications throughout the reconciliation:
CURRENT & VALID
RECOVERED FROM OLD
CURRENT NEW
MERGED
CORRECTED
SUPERSEDED
OBSOLETE
VERIFY
OPEN DECISION
NEW RECOMMENDATION
Never silently mix historical information, current truth, and recommendations.
11. AMADEUS ACCURACY — HIGHEST PRIORITY
This is the most important domain requirement in the entire project.
AeroBridge exists primarily to help learners learn correct Amadeus behavior.
The learner should be able to complete the application journey with a reliable understanding of Amadeus Basic and Advanced concepts and workflows and enough confidence to pursue real professional work.
Therefore:
Incorrect Amadeus behavior is a critical product failure.
The final knowledge must not teach incorrect GDS behavior.
12. ABSOLUTE AMADEUS RULES
NEVER invent Amadeus behavior.
NEVER guess an Amadeus command or syntax.
NEVER silently resolve conflicting Amadeus facts by intuition.
NEVER combine conflicting Amadeus descriptions into a newly invented "synthesis."
NEVER import another GDS system's behavior into AeroBridge.
Be extremely careful about contamination from:
Sabre,
Galileo,
Travelport,
Worldspan,
Apollo,
generic GDS examples,
generic airline reservation assumptions,
or AI-generated domain assumptions.
Similar concepts do NOT guarantee equivalent behavior.
13. AMADEUS SOURCE PRIORITY
When determining actual Amadeus behavior, use this hierarchy:
Highest:
Authoritative / verified Amadeus knowledge where available.
Next:
COMMAND_REFERENCE.md
This file is explicitly important and must receive special attention.
Next:
Other explicit, internally consistent AeroBridge Amadeus knowledge.
Last:
General domain knowledge, only as a hypothesis requiring verification.
Project files do NOT get to "vote" on factual Amadeus behavior.
If OLD says A and NEW says B:
identify the conflict,
determine whether reliable evidence exists,
verify where possible,
record the resolution,
otherwise mark it VERIFY.
Never convert an uncertain behavior into a canonical fact.
14. AMADEUS CONFLICT SAFETY RULE
This rule is absolute:
If Amadeus behavior cannot be confidently verified, do not create a new behavior by synthesizing conflicting sources.
Instead:
preserve the conflict,
document both claims,
identify the uncertainty,
mark it VERIFY,
and keep it out of canonical behavior until resolved.
An explicit unresolved Amadeus issue is safer than a confidently documented false rule.
15. COMMAND-BY-COMMAND RECONCILIATION
For important Amadeus commands, compare:
command,
purpose,
syntax,
prerequisites,
state requirements,
response behavior,
resulting state,
errors,
variants,
workflow position,
related commands,
edge cases,
training implications.
Do not reduce command knowledge to a list of command names.
The goal is correct operational understanding.
16. PRIORITY 1 — AMADEUS CORRECTNESS
Treat the following as the first product priority:
AeroBridge must teach correct Amadeus behavior.
Every other feature must ultimately support this purpose.
Do not allow:
visual improvements,
product ideas,
technical convenience,
simplification,
or feature scope
to justify incorrect Amadeus behavior.
17. PRIORITY 2 — PROFESSIONAL TERMINAL-LINKED COACH
The second major product priority is the AeroBridge Coach.
The Coach is NOT intended to be a real AI agent.
It is intended to be a highly professional, deterministic/programmed coaching system that is tightly connected to terminal interaction.
The Coach should reason from structured application state and learner behavior.
Recover all relevant Coach knowledge from OLD and NEW, including where it appears indirectly.
Look for:
hints,
intervention logic,
triggers,
state awareness,
terminal context,
mistake detection,
sequence awareness,
prerequisite awareness,
feedback,
explanations,
next-step guidance,
learning progression,
escalation,
repetition,
and coaching principles.
Do not merely copy historical Coach wording.
Reconstruct the strongest possible Coach model consistent with:
correct Amadeus behavior,
the current architecture,
effective learning,
professional workflow,
and the current product direction.
The Coach should help the learner learn to think and operate correctly, rather than merely give answers.
18. PRIORITY 3 — LEARNING OUTCOMES
The product must support a meaningful training journey:
Learn → Do → Receive Feedback → Correct → Repeat → Build Competence → Perform
Preserve and strengthen knowledge related to:
Basic Amadeus,
Advanced Amadeus,
progressive learning,
realistic workflows,
scenarios,
repetition,
assessments,
feedback,
correction,
confidence,
professional habits,
and prevention of false confidence.
Do not reduce AeroBridge to an isolated command playground.
19. PRODUCT QUALITY AND FUTURE COMMERCIAL POTENTIAL
AeroBridge is intended to become potentially more than a personal learning experiment.
The long-term goal may include becoming a serious standalone product with commercial potential, including subscription-based access.
This does NOT mean prematurely adding backend, billing, or infrastructure that is not currently required.
It DOES mean evaluating the product with professional product standards.
Think about:
learning value,
professional credibility,
product differentiation,
retention,
progression,
realism,
assessment,
Coach quality,
scalability of content,
long-term maintainability,
and the qualities that could make the product worth paying for.
You may propose stronger product concepts not present in the files.
Do not add random feature bloat.
Prefer high-impact improvements.
20. YOU ARE NOT LIMITED TO THE EXISTING DOCUMENTS
The source files are the project's historical knowledge.
They are not the ceiling of your reasoning.
You may identify strong ideas that neither OLD nor NEW contains.
For every such proposal, clearly label it:
NEW RECOMMENDATION
and explain:
what it is,
what problem it solves,
why it matters,
expected product value,
technical implications,
training implications,
Coach implications,
priority,
dependencies,
risks,
and whether my approval is required.
Do not silently turn recommendations into established facts.
21. VISUAL / UI KNOWLEDGE — DO NOT PREMATURELY FINALIZE
Visual design is intentionally NOT fully settled.
This includes areas such as:
colors,
typography,
fonts,
visual identity,
visual language,
spacing,
content presentation,
layout treatment,
component aesthetics,
exact visual hierarchy,
and other subjective visual decisions.
There may be valuable visual thinking in both OLD and NEW.
Recover it.
Analyze it.
Compare it.
Preserve strong principles.
But:
Do not arbitrarily select a final visual direction merely because one version looks newer or more coherent to you.
For unresolved visual matters, maintain explicit:
OPEN DESIGN / EXPLORATION KNOWLEDGE
22. DESIGN PHASE — IMPORTANT FUTURE DECISION MODEL
The future visual-design phase is NOT a continuation of the NEW project's visual direction by default.
The NEW visual system is source material and current historical context to be analyzed, not an approved visual baseline.
When AeroBridge enters the dedicated visual-design phase with Claude Design, the visual direction may be reconsidered substantially or rebuilt from first principles.
Claude Design must NOT assume that:
the NEW colors are approved,
the NEW typography is approved,
the NEW visual identity is approved,
the NEW layout approach is approved,
the NEW content presentation is approved,
or that the NEW design system represents the final visual destination.
The consolidated knowledge should preserve useful design knowledge, UX principles, visual reasoning, and lessons from both OLD and NEW, but the final visual direction remains an intentional future design decision.
I may reject the existing direction entirely.
For example, I currently do NOT want AeroBridge to default to a generic AI-looking aesthetic, including visual choices that make the product feel obviously AI-generated, such as overly bright/neon colors, generic navy-heavy SaaS styling, excessive visual effects, or other predictable "AI product" visual patterns.
I may instead explore directions such as:
black / near-black foundations,
restrained and sophisticated color usage,
premium visual character,
professional aviation/workstation credibility,
strong hierarchy,
deliberate typography,
controlled contrast,
high visual quality without unnecessary effects,
and an aesthetic that feels intentionally designed rather than obviously AI-generated.
These are exploration examples, not predetermined final specifications.
Claude Design must therefore treat the dedicated design phase as a serious design exploration and decision process, not as implementation of the existing NEW design system.
Claude Design's responsibility is to:
understand my visual goals, preferences, and constraints,
analyze the existing OLD and NEW visual knowledge,
identify what is genuinely valuable,
challenge weak, generic, derivative, or overly AI-looking directions,
propose multiple strong design directions where useful,
explain the reasoning and trade-offs,
distinguish subjective preference from objective UX principles,
recommend the strongest direction,
iterate with me through substantive discussion,
incorporate my approval or rejection,
and only then establish the final visual direction.
Do NOT simply agree with my visual preferences.
If a direction I propose creates significant UX, accessibility, hierarchy, readability, usability, performance, or product-positioning problems, tell me clearly and propose a better way to achieve the intended feeling without compromising the product.
Likewise, do not defend the NEW design merely because it already exists.
The goal is NOT to preserve the existing visual system.
The goal is to discover and establish the strongest final visual identity and interface direction for AeroBridge.
The final visual system becomes canonical only after my explicit approval.
Until then, it remains exploratory and must be treated as such.

PRODUCT NAME, LOGO & BRAND IDENTITY ARE NOT YET FINAL

The current name "AeroBridge" is the working/project name used throughout the current documentation, repository, and historical project material.

It must NOT be treated as the final commercial product name.

The final:

- product name,
- logo,
- wordmark,
- visual identity,
- brand language,
- and overall brand expression

are intentionally deferred to the dedicated future design/brand phase.

Therefore:

«"AeroBridge" is currently a working project identifier, not a permanently approved product identity.»

Do NOT build future product decisions around the assumption that the name "AeroBridge" is final.

Do NOT treat any existing logo, wordmark, naming concept, or brand treatment found in OLD or NEW materials as automatically approved.

Historical naming and branding material should be preserved as useful context and explored later, but it must remain clearly classified as:

"HISTORICAL / EXPLORATORY BRANDING"

unless explicitly approved.

During the future design phase, Claude Design may evaluate the current name and explore whether:

- AeroBridge should remain,
- the name should be modified,
- a completely different name should be chosen,
- or a different naming/brand strategy would better serve the product.

The same applies to the logo and visual identity.

Claude Design should not assume that the existing branding must be preserved.

The branding discussion should consider, where relevant:

- product positioning,
- professional aviation credibility,
- memorability,
- differentiation,
- scalability,
- commercial potential,
- international usability,
- pronunciation and clarity,
- relationship to the product's educational purpose,
- and whether the resulting brand feels intentionally designed rather than generic or obviously AI-generated.

However, none of these considerations should force a predetermined outcome.

The final product name and brand identity require my explicit approval.

Until that happens:

«AeroBridge = working project name only.»

«Existing logo/branding = historical or exploratory material only.»

«Final name/logo/brand identity = OPEN DECISION.»
23. VISUAL AUTHORITY
I retain final authority over AeroBridge's visual direction.
Claude Design is my design partner and advisor, not the final decision-maker.
Claude Design should:
investigate,
challenge,
critique,
compare,
recommend,
propose alternatives,
explain trade-offs,
and help me reach a high-quality final decision.
I decide whether a proposed visual direction is accepted, rejected, or revised.
Do not silently convert a recommendation into canonical visual truth.
A visual decision becomes final only after explicit approval from me.
24. TECHNICAL AUTHORITY MODEL
You are the technical authority for AeroBridge.
I am intentionally delegating technical decision-making to you because I do not have enough technical depth to reliably arbitrate implementation-level choices.
Therefore you should make technically sound decisions regarding:
React architecture,
code organization,
state management,
data models,
abstractions,
technical patterns,
maintainability,
integration,
implementation strategy,
consistency,
scalability,
technical constraints,
and other technical matters.
Do not unnecessarily return technical decisions to me for micromanagement.
Document major technical decisions and their rationale.
However:
Technical authority does NOT override factual Amadeus truth.
The technical system must implement correct Amadeus behavior, not redefine it.
25. FUTURE TOOL / WORKFLOW OWNERSHIP
Keep the future responsibility model clear:
Claude Design
Handles the visual/design exploration process.
Its role is to:
propose,
critique,
explore,
compare visual directions,
and work with me to reach approved visual decisions.
Claude Code
Handles repository and implementation work.
Its role is to:
implement approved product and technical decisions,
modify the repository,
integrate functionality,
preserve the canonical rules,
and verify implementation consistency.
Do not blur these roles.
At this consolidation stage, however, you are consolidating the KNOWLEDGE that both future workflows should rely on.
The transition to Claude Code implementation should occur only after the pre-implementation readiness review has addressed major foreseeable failures and the canonical knowledge is sufficiently mature.
26. THREE CLASSES OF KNOWLEDGE
Maintain a strict distinction between:
A. CANONICAL / SETTLED KNOWLEDGE
Authoritative information that future project work should follow.
Examples:
confirmed Amadeus behavior,
accepted business rules,
current architecture,
current functional behavior,
current workflows,
accepted product requirements,
accepted curriculum,
approved technical decisions.
B. OPEN / UNRESOLVED KNOWLEDGE
Important but intentionally undecided information.
Examples:
unresolved visual direction,
unresolved UX alternatives,
product choices requiring my judgment,
factual matters requiring verification.
C. HISTORICAL / SUPERSEDED KNOWLEDGE
Past decisions or implementations that are no longer current but may be useful for history, rationale, or avoiding future confusion.
Never let superseded knowledge masquerade as current truth.
27. PRODUCT VS VISUAL VS TECHNICAL VS FACTUAL DECISIONS
When evaluating a conflict, first identify its type.
Factual / Domain Conflict
Especially Amadeus: verify; do not guess.
Technical Conflict
Use technical judgment and current architecture.
Product Conflict
Use current product direction and explicit current decisions; surface important unresolved strategic choices.
Visual Conflict
Do not finalize without my approval.
Do not treat all conflicts as the same type of problem.
28. ONE CONCEPT → ONE AUTHORITATIVE HOME
The final knowledge system should not become another pile of duplicated documents.
Whenever practical:
One concept → one authoritative home
If multiple source files contain the same concept, consolidate it into the best canonical location.
Use cross-references when appropriate.
Avoid multiple competing "master" documents with overlapping authority.
29. DO NOT OVER-COMPRESS
Consolidation does NOT mean reducing everything into shallow summaries.
Final files must remain operationally useful.
A future implementation agent should be able to understand:
what AeroBridge is,
what it is trying to teach,
how it should behave,
what Amadeus behavior is required,
how the Coach should behave,
what the technical foundation is,
what is canonical,
and what remains open.
Do not delete useful detail merely to reduce file count.
30. FINAL CANONICAL FILE STRUCTURE
Do not assume the existing filenames are the final structure.
Based on the actual content you discover, determine the best final set of authoritative Markdown files.
You may:
rewrite existing files,
merge files,
rename files,
split overloaded files,
create new files,
remove redundant structures.
Do not optimize for a fixed number of files.
Optimize for:
Clear authority, complete knowledge, minimal duplication, and long-term maintainability.
Each final file must have a clear purpose.
There must be no ambiguity about which file is authoritative for a given concept.
31. FINAL FILE METADATA
For every final canonical file, clearly establish where practical:
purpose,
scope,
authority level,
source material,
major reconciliations,
important assumptions,
unresolved issues,
and relationship to other canonical files.
32. HUMAN DECISION GATES
Create a clear section:
DECISIONS REQUIRING MALIK APPROVAL
Use it for decisions genuinely belonging to me, especially:
visual direction,
subjective visual choices,
important product strategy choices that are not already settled,
significant unresolved user experience choices.
Do NOT use this as an excuse to avoid technical decision-making.
For technical architecture and implementation-level decisions, use your technical authority.
For Amadeus factual uncertainty, verification is required rather than approval-based guessing.
33. PRE-IMPLEMENTATION READINESS & FAILURE-MODE REVIEW
Before any repository implementation begins, perform a dedicated pre-implementation review whose purpose is to make the design, product logic, technical model, Amadeus behavior, Coach behavior, and learning journeys as mature as reasonably possible BEFORE I begin real-world testing.
This phase exists because testing should not be the first place where we discover obvious, structural, or avoidable product decisions.
The goal is NOT to eliminate the need for real testing. That is impossible and undesirable. The goal is to ensure that real testing is focused primarily on genuine emergent issues and fine-grained improvements rather than preventable gaps that could have been identified through careful reasoning beforehand.
The desired outcome is:
Think deeply first → identify likely failures early → resolve major issues before implementation → implement a mature design → use real testing to discover what reasoning alone could not reveal.
33.1 PURPOSE
Before implementation, challenge the consolidated AeroBridge specification as if you were trying to break it.
Ask:
What important decision is still missing?
What requirement is ambiguous?
Where could two valid-looking rules conflict?
Where could the learner become confused?
Where could the system teach the wrong behavior?
Where could the Coach intervene incorrectly?
Where could a technically correct implementation produce a poor learning experience?
What could force expensive architectural rework later?
What edge cases have not been considered?
What assumptions are being made without evidence?
Which problems are likely to appear during real usage?
Do not wait for me to discover these during testing if they can reasonably be discovered now.
33.2 FULL-SYSTEM PREVIEW
Review the intended AeroBridge experience end-to-end before implementation.
Walk through the major learner journey mentally and, where possible, as a structured scenario model:
learner enters the product,
learner understands what to do,
learner enters a command,
the system interprets the command,
Amadeus state changes correctly,
the terminal displays the correct result,
the Coach reacts appropriately,
the learner receives the right amount of guidance,
the learner makes mistakes,
the system handles those mistakes correctly,
the learner corrects the mistake,
the learner progresses through the workflow,
the scenario reaches a meaningful completion state,
the learner understands what was learned,
progression/assessment state is persisted correctly.
Repeat this reasoning across representative Basic and Advanced workflows.
33.3 AMADEUS FAILURE-MODE REVIEW
Because Amadeus correctness is Priority #1, explicitly search for failure modes before implementation.
Review whether:
commands are interpreted in the correct context,
prerequisites are enforced,
state transitions are logically correct,
invalid commands fail correctly,
incomplete inputs are handled safely,
command sequencing is realistic,
errors do not accidentally teach incorrect behavior,
one command cannot accidentally behave like another GDS command,
historical knowledge has not been transformed into unsupported behavior,
and no convenience rule has been allowed to override domain accuracy.
Pay special attention to any rule that could create false training evidence, false success, or false confidence.
If a behavior is uncertain, do not design around the uncertainty as though it were fact. Keep it explicitly unresolved or verify it first.
33.4 COACH FAILURE-MODE REVIEW
Before implementation, challenge the Coach as a learner-facing system.
Evaluate scenarios such as:
learner enters the correct command,
learner enters an invalid command,
learner enters a technically valid command at the wrong workflow stage,
learner repeats the same mistake,
learner skips a prerequisite,
learner appears stuck,
learner partially completes a step,
learner succeeds without understanding,
learner needs a hint but not a solution,
learner ignores the Coach,
learner rapidly improves and needs less intervention,
learner reaches advanced material with weak fundamentals.
For each case, determine whether the Coach knows:
what happened,
why it happened,
what the learner likely needs,
when to intervene,
how strongly to intervene,
what information to reveal,
what not to reveal,
and when to step back.
The Coach should support learning rather than becoming an answer-dispenser.
33.5 LEARNING / PEDAGOGICAL FAILURE-MODE REVIEW
Challenge the learning system, not only the software.
Ask:
Can a learner succeed without understanding the underlying workflow?
Can the UI accidentally reward guessing?
Can hints become a shortcut instead of a learning aid?
Can the learner reach Advanced content without sufficient Basic competence?
Can incorrect behavior accidentally look successful?
Are mistakes followed by meaningful correction?
Does repetition reinforce the correct mental model?
Are scenarios realistic enough to create professional confidence rather than game-only familiarity?
Does assessment measure actual understanding and execution rather than superficial completion?
Any structural pedagogical weakness that can be resolved before implementation should be resolved before implementation.
33.6 PRODUCT / UX FAILURE-MODE REVIEW
Review the intended product experience before implementation from the learner's point of view.
Challenge:
information hierarchy,
navigation,
task clarity,
terminal focus,
Coach placement and timing,
feedback clarity,
progression visibility,
error recovery,
cognitive load,
unnecessary complexity,
mobile/desktop behavior,
accessibility implications,
and consistency between different screens and workflows.
Do not allow visual polish to hide workflow problems.
Do not allow technical convenience to dictate poor UX.
33.7 TECHNICAL FAILURE-MODE REVIEW
Before implementation, evaluate whether the proposed technical model is likely to create avoidable rework.
Review at minimum:
state ownership,
persistence,
local storage behavior,
synchronization between terminal and Coach,
source-of-truth boundaries,
component/data responsibilities,
extensibility for additional commands and workflows,
error handling,
testability,
maintainability,
and the ability to extend Basic into Advanced functionality without architectural collapse.
Look for places where two systems may accidentally maintain contradictory state.
Look for hard-coded assumptions that should instead be represented as explicit rules or data.
Look for designs that work for the first few scenarios but become fragile when the curriculum expands.
Use your technical authority to resolve these issues before implementation whenever reasonably possible.
33.8 STATE / EDGE-CASE MATRIX
Build or reason through a meaningful matrix of important states and edge cases before coding.
This should cover, where applicable:
empty input,
malformed input,
valid input,
valid-but-contextually-wrong input,
repeated input,
correction after error,
incomplete workflow,
completed workflow,
reset/restart,
persistence/reload,
interrupted scenario,
Coach unavailable/irrelevant state,
assessment state,
progression boundaries,
and unusual but realistic learner behavior.
The exact matrix should be driven by the actual AeroBridge architecture and curriculum rather than by an arbitrary checklist.
33.9 PRE-IMPLEMENTATION DECISION REGISTER
Before implementation, identify every remaining decision whose late discovery could cause meaningful rework.
Classify each as:
RESOLVED BEFORE IMPLEMENTATION
MALIK APPROVAL REQUIRED
TECHNICAL DECISION — CLAUDE
AMADEUS VERIFICATION REQUIRED
DELIBERATELY OPEN
Do not allow major unresolved issues to remain hidden simply because they can technically be decided later.
If an issue is intentionally left open, explain why leaving it open is safe and what its impact is.
33.10 PRE-IMPLEMENTATION RISK REGISTER
Create a concise risk register covering the highest-impact foreseeable failures.
For each high-risk item record:
risk,
probability or confidence level where useful,
impact,
affected area,
evidence/reasoning,
mitigation,
whether it must be resolved before implementation,
and how it will later be tested.
Prioritize risks that can cause:
incorrect Amadeus training,
false learner confidence,
broken terminal workflows,
broken Coach logic,
contradictory application state,
major UX redesign,
architectural rework,
or loss/corruption of learner progress.
33.11 PRE-IMPLEMENTATION QUALITY GATE
Do not proceed to repository implementation until the major issues discovered during this review have been handled appropriately.
A problem may be handled by:
resolving it,
verifying it,
redesigning the affected rule/flow,
explicitly assigning it to a later low-risk refinement,
or documenting it as a deliberate open decision.
Do NOT postpone a major foreseeable problem to real-world testing simply because testing will eventually reveal it.
The quality gate should conclude with a clear statement of:
what is ready,
what was deliberately left open,
what still requires verification,
what risks remain,
and why implementation can now proceed responsibly.
33.12 IMPORTANT LIMITATION
This review is a prevention and readiness pass, not a replacement for real user testing.
Do not claim that because a workflow was reasoned through successfully it is therefore guaranteed to work in real usage.
Real testing remains mandatory later.
The purpose of this stage is to make the first real testing cycle significantly more focused, efficient, and informative by removing avoidable design, logic, and architecture problems beforehand.
34. NO CODE IMPLEMENTATION DURING CONSOLIDATION
This operation is first and foremost:
Knowledge Consolidation / Source-of-Truth Reconstruction
Do not modify the repository merely because you discover something that should eventually change.
At this stage:
Understand → Reconcile → Verify → Document → Finalize
Implementation happens after the canonical knowledge foundation exists.
Document implementation implications when useful, but do not confuse them with actual code changes.
35. CROSS-DOCUMENT CONSISTENCY AUDIT
Before completion, audit the final canonical files against each other.
Look specifically for:
React vs Vanilla contradictions,
3-page vs 5-page contradictions,
conflicting command definitions,
contradictory rules,
conflicting workflows,
conflicting curriculum expectations,
inconsistent terminology,
contradictory Coach behavior,
conflicting state definitions,
superseded information presented as current,
unresolved design decisions presented as final,
and duplicated concepts with different authority.
The final canonical knowledge must tell one coherent story.
36. FINAL KNOWLEDGE MUST BE OPERATIONAL
The final Knowledge should be usable by future AeroBridge development sessions without requiring them to repeatedly consult the old and new project histories.
The canonical files become the operational project reference.
Future project work should normally follow:
CANONICAL KNOWLEDGE → IMPLEMENTATION / DESIGN
not:
OLD + NEW + scattered notes → reinterpret the project again.
37. HISTORICAL SOURCE STATUS AFTER CONSOLIDATION
Once the consolidation has been completed and accepted:
The OLD and NEW source collections should be treated as historical source material, not as competing operational sources of truth.
The canonical files become the primary operational Knowledge for continuing AeroBridge.
Historical files may remain preserved for audit/history/reference, but future implementation work should not depend on searching both project generations for the current truth.
38. FUTURE VALIDATION, REAL LEARNING, AND ITERATION HANDOFF
The consolidation task ends before repository implementation, but the canonical knowledge must be structured so it can support the full downstream product lifecycle.
After canonical knowledge is finalized, the intended future sequence is:
Canonical Knowledge → Amadeus Accuracy Audit → Visual Direction with Claude Design + Malik Approval → Claude Code Implementation → Implementation Verification → Real Learner Testing → Targeted Correction → Re-testing → Iterative Product Improvement
Real learner testing is not a substitute for the pre-implementation readiness review. It is the next layer of evidence.
The purpose of real testing is to discover issues that cannot be reliably predicted from documents alone, including:
confusing learning flows,
unexpected terminal behavior in practice,
Coach timing or guidance problems,
learner misunderstanding,
usability friction,
progression issues,
edge cases revealed by actual usage,
and opportunities to improve learning effectiveness.
When real testing reveals a problem, the future improvement loop should be:
Observe → Diagnose → Determine whether the problem is factual, technical, product, UX, Coach, or pedagogical → Correct at the appropriate authority level → Implement → Verify → Re-test.
Do not treat every observation as a reason for broad redesign. Prefer targeted, evidence-based iteration unless the evidence shows that a foundational decision is wrong.
The consolidation process should therefore leave future teams with enough traceability to understand which canonical rule, decision, workflow, or technical principle is affected when later testing reveals a problem.
39. FINAL COMPLETION CRITERIA
Do NOT declare the task complete merely because final files were written.
You must verify:
SOURCE COVERAGE
All 13 source files were reviewed.
KNOWLEDGE RECOVERY
Important OLD-only knowledge was identified and handled.
CURRENT KNOWLEDGE
Important NEW-only knowledge was preserved.
CONFLICT RESOLUTION
Important contradictions were explicitly addressed.
AMADEUS SAFETY
Amadeus-specific claims were handled with high scrutiny.
COMMAND COVERAGE
Important command knowledge, especially from COMMAND_REFERENCE.md, was properly incorporated.
GDS CONTAMINATION SAFETY
No unsupported behavior from another GDS was silently imported.
TRAINING QUALITY
The knowledge supports Basic → Advanced learning appropriately.
COACH QUALITY
Coach concepts from both generations were recovered and strengthened.
DESIGN SAFETY
Unresolved visual decisions remain explicitly unresolved.
TECHNICAL CONSISTENCY
The current technical direction is coherent.
PRODUCT QUALITY
Important high-value product recommendations have been surfaced separately.
KNOWLEDGE LOSS CHECK
No meaningful unique knowledge was silently discarded.
CROSS-FILE CONSISTENCY
Canonical files do not contradict each other.
AUTHORITY CLARITY
It is obvious where each major concept should be sourced from.
PRE-IMPLEMENTATION READINESS
A dedicated pre-implementation failure-mode and readiness review was completed, major foreseeable issues were addressed, and remaining risks/open decisions are explicitly documented.
COMPLETION PLAN
The consolidation plan accurately reflects completed and remaining work.
40. REQUIRED FINAL OUTPUTS
At the end of the operation, produce the following.
A. COMPLETED CONSOLIDATION PLAN
AeroBridge_Knowledge_Consolidation_Plan.md
This must reflect the actual state of the completed reconciliation.
B. SOURCE RECONCILIATION REPORT
Explain:
what OLD contributed,
what NEW contributed,
what was recovered,
what was superseded,
major conflicts,
major Amadeus verification issues,
important omissions discovered,
and major conclusions.
C. FINAL CANONICAL SOURCE-OF-TRUTH FILES
Actually produce the final Markdown files.
Do not merely recommend their names.
Create their actual content.
D. DECISIONS REQUIRING MALIK APPROVAL
Separate the unresolved decisions that genuinely require my input.
E. NEW PRODUCT / SYSTEM RECOMMENDATIONS
Provide the strongest meaningful improvements you identified beyond the existing source material.
Keep recommendations clearly separated from canonical facts.
F. FINAL CONSISTENCY / COMPLETION AUDIT
Perform and document the final audit proving that the canonical knowledge system is coherent.
G. PRE-IMPLEMENTATION READINESS REVIEW
Document the major foreseeable failure modes discovered before implementation, the decisions resolved before implementation, the risks intentionally retained, and the reasoning that supports moving into repository implementation.
41. FINAL OPERATING PRINCIPLES
Throughout the entire operation, follow these rules:
NEW is the current baseline, not automatic truth.
OLD is historical, not automatically obsolete.
Never silently discard unique valuable knowledge.
Do not confuse implementation history with underlying knowledge.
Do not guess Amadeus behavior.
Do not contaminate Amadeus knowledge with other GDS behavior.
Do not synthesize conflicting Amadeus facts into an invented rule.
Amadeus correctness is Priority #1.
The professional terminal-linked Coach is Priority #2.
Learning outcomes and professional readiness are core product objectives.
You own technical decisions.
I own final visual decisions.
Claude Design proposes and explores visual direction with me.
Claude Code implements repository changes based on approved/current canonical knowledge.
Unresolved visual decisions remain OPEN.
Recommendations are not automatically facts.
The final Knowledge must be internally consistent.
The canonical files become the operational Source of Truth for future AeroBridge work.
The pre-implementation readiness review must reduce foreseeable failures before repository work begins, while real learner testing must remain the evidence-driven mechanism for discovering and correcting problems that could not reasonably be predicted in advance.
Before implementation, perform a serious failure-mode and readiness review instead of relying on real testing to discover foreseeable structural problems.
Real-world testing remains mandatory; pre-implementation reasoning reduces avoidable surprises but does not eliminate the need for testing.
Do not defer major foreseeable problems to the testing phase merely because they can be discovered later.
Above all:
Do not optimize for the newest project state. Reconstruct the strongest truthful and useful version of the entire AeroBridge project history, then make that reconstructed knowledge the foundation for the future.
The goal is to finish with one mature, coherent AeroBridge knowledge system in which the valuable knowledge from both project generations has been recovered, reconciled, verified, organized, and preserved.
I should be able to continue AeroBridge from that point without feeling that important history was lost, without maintaining two competing knowledge bases, and without risking that the simulator teaches me incorrect Amadeus behavior.
Begin with the full source inventory and the living consolidation plan.
Do not skip files.
Do not prematurely finalize unresolved decisions.
Do not declare completion until the final verification criteria have been satisfied.