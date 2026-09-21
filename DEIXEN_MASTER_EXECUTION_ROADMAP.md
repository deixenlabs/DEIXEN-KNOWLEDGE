DEIXEN — MASTER EXECUTION ROADMAP

1. Mission

DEIXEN is being built as a professional learning platform for practical Amadeus/GDS skill development.

The goal is not merely to build:

- a simulator,
- a course library,
- a polished interface,
- or a feature-rich educational product.

The goal is to build a system that can genuinely help learners progress from initial knowledge toward accurate, independent, consistent, contextual, and transferable performance.

The intended learning progression is:

Learn → Retrieve → Practice → Feedback → Correction → Repeat → Independent Performance → Assessment → Evidence → Progression → Reinforcement → Transfer

The quality target is strong professional training quality: rigorous, practical, evidence-aware, and capable of producing meaningful skill development.

References to IATA or other strong professional training organizations are examples of quality ambition only. DEIXEN is not required to imitate their products, curricula, terminology, certifications, or structure.

The ambition is not merely to match existing training products.

The ambition is to build the strongest learning product that can be responsibly justified by available evidence, domain truth, and DEIXEN'S own requirements.

---

2. Current Strategic State

DEIXEN's overall lifecycle spans Pre-Opus foundation preparation, independent Opus review, foundation closure, design, implementation, verification, learner testing, and evidence-based improvement.

For the current Pre-Opus phase, the primary active execution and planning reference is `DEIXEN_MASTER_PRE_OPUS_FOUNDATION_PREPARATION_PLAN-1.md`. This Master Execution Roadmap remains the project's overall lifecycle roadmap; it is not the active execution authority for Pre-Opus work. Its post-Opus lifecycle becomes operational at the Handoff to Opus boundary.

The Pre-Opus foundation phase is governed by `DEIXEN_MASTER_PRE_OPUS_FOUNDATION_PREPARATION_PLAN-1.md`, which defines the active preparation work required before the Handoff to Opus.

The resulting foundation must be complete and independently reviewed before the project crosses the Opus handoff and downstream implementation lifecycle.

**Lifecycle responsibility model at and beyond the Opus boundary:**

- **Claude Sonnet** — finishing the specific foundation work already in flight: the remaining Amadeus Reference/Knowledge work, and any explicitly assigned remaining foundation-review tasks. The Learning Experience Architecture is already completed as a first-build foundation artifact (see Section 7) and is not part of Sonnet's remaining work. Sonnet is not the project's long-term strategic brain. This role concludes once the in-flight work is complete; no standing responsibility is invented merely to keep Sonnet in the workflow past that point.
- **Claude Opus 5** — the primary high-end reasoning and development model for the post-foundation phase: the final foundation review, difficult architecture and engineering reasoning, implementation guidance, debugging, high-risk analysis, and downstream strategic direction where appropriate. Opus does not become a source of truth. It remains subordinate to canonical project artifacts, verified domain evidence, approved project decisions, the project's working rules, and explicit project-owner authority, in all cases.
- **ChatGPT (GPT-5.6 Luna, Free plan)** — a limited, supportive role: independent second opinion, contradiction-spotting, critical review, prompt engineering and refinement, and governance reasoning. It is not the primary execution model, the primary file-authoring model, or the primary engineering model. Its actual Free-tier capabilities are not to be overstated or assumed to include paid-tier features.
- **Claude Design** — owns design execution once the foundation is closed.
- **Claude Code** — owns engineering implementation once design is approved.
- **Project owner** — final authority on scope, naming, visual direction, approval, and canonicalization. This authority does not shift regardless of which model is doing the reasoning.
- **External / domain validation** — remains necessary wherever project governance requires it (see Decision 7 in the canonical decisions ledger), independent of any AI's own assessment.

Opus's review does not replace Sonnet's own review. Sonnet must continuously check and improve its work before submitting the completed foundation for independent final review.

**Model-selection note (historical, non-active):** a candidate primary-intelligence model (Fable 5.1) was evaluated for this role in a prior review and was not adopted for the current phase — the decision was driven by the project's budget for this phase, not by a capability finding against it. It carries no active role and no planned dependency in this roadmap. It is recorded here only so the evaluation is not silently lost to history; see the AeroBridge Roadmap & AI Role Architecture Review for the underlying evidence.

**Operating objective given a one-month project budget:** extract the strongest practical result from Opus through stronger source material, tighter task decomposition, precise prompting, high-effort reasoning where the task justifies it, adversarial review, verification, testing, and disciplined iteration — rather than assuming that model capability alone substitutes for that discipline. This is an efficiency principle, not a rigor reduction. It does not authorize skipping verification, review, or evidence discipline anywhere else in this roadmap.

---

3. Project Documentation Landscape

The project documentation landscape includes a 14-file baseline set, divided into two functionally distinct groups. This inventory is a documentation-management view of the project and is not the active Pre-Opus execution corpus or review authority. The active Pre-Opus preparation, corpus inventory, status map, authority map, and handoff scope are governed by `DEIXEN_MASTER_PRE_OPUS_FOUNDATION_PREPARATION_PLAN-1.md`.

**A. Core project/foundation artifacts — 11 files.** These define or preserve project knowledge, architecture, design system, Amadeus/learning foundations, decisions, and related authoritative project content:

1. "00_DEIXEN_Knowledge_Consolidation_Plan.md"
2. "03_DEIXEN_Canonical_Product_and_Architecture.md"
3. "04_DEIXEN_Canonical_Design_System.md"
4. "05_DEIXEN_Canonical_Amadeus_Engine_Reference.md"
5. "06_DEIXEN_Canonical_Curriculum_and_Coach.md"
6. "07_DEIXEN_Canonical_Decisions_and_Current_State.md"
7. "08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process_UNIFIED_PROPOSED.md"
8. "13_DEIXEN_Decision_Resolution_Register.md"
9. "14_DEIXEN_Source_vs_Output_Sufficiency_Audit.md"
10. "DEIXEN_Learning_Experience_Architecture.md"
11. "DEIXEN_Learning_Design_Specification.md"

Files 2–6 above are the canonical project/foundation artifacts. File 7 is the proposed unified AI Working Rules document and is explicitly NOT YET CANONICAL. Files 1, 8–9 are supporting consolidation, decision-resolution, and audit artifacts; they record project state, evidence, findings, or process status but do not become canonical domain/project truth merely by appearing in this landscape. Files 10–11 — the Learning Foundation artifacts — are completed first-build foundation artifacts, not yet canonical; their active status, review sequence, and final handoff treatment are governed by the Pre-Opus preparation plan. Grouping all eleven together as "core" is a documentation-management convenience; it does not equalize their authority status.

**B. Project-operation / session-support artifacts — 3 files.** These support project/session operation, coordination, governance, and execution. They are important project artifacts but are not interchangeable with domain/foundation knowledge:

12. "UNIVERSAL_AI_SESSION_HANDOFF_PROTOCOL.md"
13. "DEIXEN_Prompt_Engineering_and_Governance_UNIFIED_PROPOSED.md"
14. "DEIXEN_MASTER_EXECUTION_ROADMAP.md" (this document)

These 14 files constitute the project's baseline managed documentation set — 14 files, not 14 files of the same kind. This baseline must not be confused with the active Pre-Opus Corpus handed to Opus, whose final inventory is established by the Pre-Opus preparation plan.

Additional Amadeus Reference/Knowledge files may form part of the prepared Opus Corpus. Their production, intake, evidence classification, authority treatment, and final corpus inclusion are governed by `DEIXEN_MASTER_PRE_OPUS_FOUNDATION_PREPARATION_PLAN-1.md`, not by this landscape inventory. Their final number is not fixed in this roadmap and must not be inferred from this baseline inventory.

This is one integrated project knowledge corpus, not a replacement of an "old" project by a "new" one. An artifact being older does not, by itself, make its content historical or superseded — only a specific decision, state, or claim that evidence shows has actually been replaced is superseded. "Historical" or "superseded" is not applied as a blanket label to an entire file merely because of when it was produced.

When sources conflict, determine whether the difference is caused by:

- supersession,
- version,
- scope,
- historical status,
- or a genuine unresolved contradiction.

Do not silently resolve conflicts.

---

4. Amadeus Reference Layer

The Amadeus Reference Layer establishes the evidence base used to represent Amadeus commands, behavior, prerequisites, constraints, outputs, workflows, error behavior, and other relevant domain behavior.

The production, intake, evidence classification, authority treatment, and final inclusion of Amadeus Reference/Knowledge artifacts in the prepared Opus Corpus are governed by `DEIXEN_MASTER_PRE_OPUS_FOUNDATION_PREPARATION_PLAN-1.md`.

This roadmap does not independently assign those artifacts an active Pre-Opus execution status or final corpus inclusion.

The governing rule is:

Never guess Amadeus behavior.

General GDS knowledge, intuition, plausibility, or assumptions must not be converted into Amadeus truth.

External research may be used to verify domain facts when appropriate, but important Amadeus claims must remain traceable to appropriate evidence.

---

5. Learning Design Layer

The primary learning-design artifact is:

"DEIXEN_Learning_Design_Specification.md"

**Current status:** COMPLETED as a first-build foundation artifact and not yet formally closed; its review and closure are governed by the Pre-Opus preparation plan, the Opus adversarial review, and the subsequent closure process.

The document is not considered formally closed yet; final closure depends on the complete foundation review, resolution of valid findings, and closure verification.

This document defines how DEIXEN should actually teach.

It must provide an explicit and coherent learning system covering:

- initial learning,
- retrieval,
- practice,
- feedback,
- error correction,
- repetition,
- assistance,
- fading of assistance,
- independent performance,
- assessment,
- evidence,
- progression,
- reinforcement,
- retention,
- transfer,
- and recovery from later performance decline.

The design must preserve the distinctions between:

- exposure and learning,
- completion and competence,
- assisted success and independent performance,
- competence and mastery,
- simulator performance and workplace transfer,
- confidence and ability,
- measurement and valid evidence.

The Learning Design must be evidence-informed, professionally rigorous, practical, and implementation-useful.

It must not become an academic document for its own sake.

The Learning Design must be actively challenged during the applicable review process rather than merely preserved as previously written.

The objective is not to make the document look better.

The objective is to produce the strongest justified learning design for DEIXEN.

---

6. Learning Science and External Research

During Learning Design work, external research may be used whenever it can materially improve the design.

Relevant areas include:

- retrieval practice,
- deliberate practice,
- feedback,
- scaffolding and fading,
- mastery learning,
- assessment validity,
- transfer,
- cognitive load,
- error-based learning,
- retention and spacing,
- simulation-based learning,
- vocational training,
- professional training,
- aviation training and assessment.

Research should be used selectively and critically.

The purpose of research is to determine how DEIXEN should teach effectively.

Research must never be used to invent what Amadeus does.

External evidence must remain distinguishable from:

- established evidence,
- DEIXEN-specific design decisions,
- DEIXEN-specific inferences,
- hypotheses,
- and validation requirements.

---

7. Learning Experience Architecture

The learner-experience-architecture artifact is:

"DEIXEN_Learning_Experience_Architecture.md"

**Current status:** COMPLETED as a first-build foundation artifact and not yet canonical. Its review, validation, and closure sequence are governed by the Pre-Opus preparation plan and the subsequent independent review and foundation-closure process. It is not to be treated as in-progress or unfinished merely because final approval is still pending.

This document translates the Learning Design into the logic of the learner's experience inside the product.

The Learning Design and Learning Experience Architecture are related artifacts and must remain synchronized. Any change to one that materially affects the other must be reflected in both before Foundation closure, not only before initial submission.

It defines, where necessary:

- what the learner sees,
- when it appears,
- what precedes practice,
- when explanation appears,
- when assistance appears,
- how assistance fades,
- when assessment appears,
- how learning connects to Terminal practice,
- how scenarios connect to practice,
- how assessment connects to evidence,
- how evidence affects progression,
- how reinforcement is presented,
- how the learner understands why they are repeating or progressing,
- and which states belong within the same experience versus a distinct product state.

This document is the bridge between:

Learning Design ↔ Product / Experience Design

It does not define final visual identity.

It does not finalize:

- colors,
- typography,
- icons,
- visual styling,
- final screen composition,
- or aesthetic direction.

Those decisions belong to the later Claude Design phase.

---

8. Additional Pre-Design System or Engineering Documents

A new document must not be created merely because it appears useful, convenient, or cleaner, or merely to increase documentation volume.

An additional document may be introduced only when all of the following hold:

- a real responsibility or dependency exists that is not already covered,
- that responsibility cannot be safely and clearly owned by an existing artifact,
- the new artifact has a clearly defined, non-overlapping scope and authority,
- its relationship to the existing knowledge set is made explicit,
- its creation is explicitly approved by the project owner,
- and the project documentation landscape (Section 3) is updated accordingly.

This is not an open-ended permission for any model or agent to expand the documentation system on its own judgment. The objective is a complete and maintainable foundation, not a large number of files.

---

8A. Foundation Artifact Review / Freeze Pattern

Foundation review should not jump directly from artifact existence to the independent Opus review. Artifacts are reviewed sequentially and cumulatively, with the active review sequence and execution status governed by `DEIXEN_MASTER_PRE_OPUS_FOUNDATION_PREPARATION_PLAN-1.md`.

For every artifact:

**AUDIT → IDENTIFY DEFECTS → CORRECT → RE-REVIEW → CROSS-DOCUMENT REGRESSION CHECK → FREEZE**

The active Pre-Opus review corpus, artifact order, inclusion rules, and review status are governed by `DEIXEN_MASTER_PRE_OPUS_FOUNDATION_PREPARATION_PLAN-1.md`.

This roadmap does not independently define a fixed Pre-Opus corpus count or active artifact inventory.

Additional Amadeus Reference/Knowledge artifacts enter the review corpus only through the intake, evidence, authority, and corpus rules defined by the Pre-Opus preparation plan.

A frozen artifact is a stable baseline, not immutable truth. It may be reopened only when later evidence reveals a genuine defect, contradiction, dependency, or supersession that materially affects it.

---

9. Pre-Opus Consolidation and Challenge Pattern

The active Pre-Opus consolidation, synchronization, adversarial review, unresolved-item handling, readiness checks, and final preparation sequence are governed by `DEIXEN_MASTER_PRE_OPUS_FOUNDATION_PREPARATION_PLAN-1.md`.

This roadmap retains the following as a lifecycle reference pattern rather than an independent Pre-Opus execution stage:

- cross-document consistency and dependency review,
- authority and source-boundary checks,
- contradiction and stale-reference detection,
- Amadeus truth-boundary protection,
- learning and experience coherence,
- evidence validity,
- identification of unresolved questions,
- and explicit carry-forward of matters that require later validation or judgment.

The roadmap does not independently assign these activities to Sonnet or any other model, nor does it define a separate Pre-Opus review sequence outside the active preparation plan.

---

10. Evidence / State Confirmation Gate Pattern

Before downstream work relies on learning-system mechanisms whose evidence or state prerequisites have not yet been confirmed, the relevant foundation must establish that the evidence/state architecture can support what those approved mechanisms require.

The active confirmation scope, current status, ownership, open dependencies, and resolution sequence are governed by the applicable Pre-Opus preparation, decision, evidence, and architecture artifacts. This roadmap does not independently define those details.

The gate should confirm, where relevant:

- that evidence claimed by an approved mechanism is actually recordable and interpretable,
- that required state transitions and assistance/independence conditions can be represented,
- that required workflow or sequence continuity can be reconstructed where the approved rule depends on it,
- and that any genuine architectural gap is explicitly recorded before the affected mechanism is treated as implementation-ready.

This is an architectural confirmation, not a license to invent domain behavior, redefine approved rules, or prescribe an implementation schema. Document existence alone does not satisfy the gate; the required evidence or architectural question must actually be confirmed and its status recorded in the appropriate governing artifact.

---

11. Final Independent Adversarial Review — Opus

Only after Sonnet has completed and consolidated the full pre-design foundation, and the Evidence/State Confirmation Gate above has been addressed, should the final independent review occur.

**Scope clarification:** the current managed project documentation set contains the 14 files defined in Section 3. The substantive pre-design foundation review is centered on the 11 core project/foundation artifacts defined there, together with the Amadeus Reference/Knowledge files once they are produced and formally included. The three project-operation/session-support artifacts are not treated as domain/foundation knowledge, but their governance, authority, status, sequencing, ownership, and dependency implications remain within the corpus-level review scope. They must be considered wherever they can materially affect the foundation or the consistency of the project documentation system.

Opus reviews the complete relevant foundation set together:

- all 9 existing canonical files,
- all new Amadeus reference files,
- "DEIXEN_Learning_Design_Specification.md",
- "DEIXEN_Learning_Experience_Architecture.md",
- and any additional approved pre-design system or engineering documents.

The three project-operation/session-support artifacts are also checked for material governance, authority, status, sequencing, ownership, and cross-document implications rather than being treated as interchangeable with the foundation files.

This is one comprehensive final adversarial review, not a series of isolated reviews, and not a ceremonial approval pass. Its value depends specifically on surfacing what an earlier, less independent pass could not — including defects that survived Sonnet's own self-review precisely because they were invisible to the same reasoning process that produced them.

The review must actively search for:

- defects that survived prior self-review,
- cross-document contradictions,
- authority-boundary failures,
- unsupported assumptions,
- evidence/implementation mismatches,
- hidden dependencies,
- scope drift,
- and dangerous simplifications.

Where relevant, the review must also examine:

- Amadeus/domain accuracy,
- source authority,
- duplicated or competing truth,
- product coherence,
- learning validity,
- assessment validity,
- evidence validity,
- learner progression,
- assistance and Coach behavior,
- retention,
- transfer,
- learner-experience logic,
- implementation clarity,
- and engineering boundaries.

Opus must actively search for important weaknesses that Sonnet missed, not re-confirm a checklist Sonnet's own self-review already ran. Opus's recommendations are not automatically accepted. Each finding must be evaluated against the source evidence before it becomes a project decision.

---

12. Resolve Review Findings and Close the Foundation

After the Opus review:

- valid findings are resolved,
- invalid findings are rejected with reasoning,
- premature recommendations are deferred,
- implementation dependencies are recorded,
- empirical questions remain explicitly identified,
- and approved changes are incorporated into the relevant files.

After these changes are made, perform a final closure verification of the resulting foundation.

This closure verification is not a replacement for the Opus adversarial review and does not require another full Opus review. Its purpose is to confirm that the approved changes did not introduce new contradictions, authority conflicts, scope problems, or unintended inconsistencies across the affected files.

The result should be:

A complete, coherent, evidence-grounded, implementation-ready Knowledge + Learning Foundation.

This closure is preceded by an explicit **Evidence / State Confirmation Gate** verifying that the dependent foundation artifacts, evidence status, unresolved validation requirements, ownership, and sequencing are current and mutually consistent.

No downstream phase may treat a dependency as ready solely because a document exists; its recorded status and required evidence must also be confirmed.

The foundation is considered closed only after the final review findings that genuinely require changes have been resolved, the resulting files are internally consistent, and the closure verification confirms that the approved changes did not introduce material new conflicts.

At this point, the project should not need to restart Learning Design or Amadeus research from the beginning during implementation.

Later changes should be driven by:

- new evidence,
- domain validation,
- implementation findings,
- or learner-testing evidence.

Closed decisions must not be reopened casually.

---

13. Claude Design

Only after the Knowledge + Learning Foundation has been closed should Claude Design begin.

Claude Design receives the approved foundation and explores how it should become the actual product experience.

Claude Design investigates:

- product identity,
- visual language,
- screen architecture,
- interaction design,
- learning-state presentation,
- Terminal experience,
- Coach presentation,
- Reference behavior,
- scenarios,
- assessments,
- evidence and growth,
- responsive behavior,
- motion and interaction,
- cognitive load,
- accessibility,
- and overall professional character.

Claude Design is expected to:

- challenge weak assumptions,
- identify UX risks,
- propose alternatives,
- explore multiple directions where useful,
- and improve the initial concept.

Claude Design is not required to preserve a predetermined visual solution.

The user remains the final authority for the visual direction, subject to the approved canonical product decisions and Learning Design requirements.

---

14. Final Design Approval

After Claude Design exploration:

The user selects and approves the final product direction.

Only approved design decisions become implementation requirements.

---

15. Implementation — Claude Code

After approval of:

- the current knowledge foundation,
- Amadeus reference,
- Learning Design,
- Learning Experience Architecture,
- approved pre-design system or engineering requirements,
- and final visual direction,

Claude Code implements the product.

The implementation must follow the approved foundation.

If implementation difficulty appears, first determine whether the issue is:

1. a technical implementation problem,
2. a genuine design constraint,
3. or a decision that requires revision.

Do not weaken the learning design merely because a technically convenient implementation would be easier.

---

16. Implementation Verification

After implementation, verify that the product matches the approved:

- Amadeus behavior,
- Learning Design,
- learner-experience logic,
- engineering/system requirements,
- and visual design.

Verify, where relevant:

- states,
- events,
- evidence,
- assessment,
- progression,
- assistance,
- feedback,
- error recovery,
- repetition,
- scenarios,
- persistence,
- responsive behavior,
- accessibility,
- and cross-screen consistency.

This verification confirms that the software behaves as coded. That is a distinct question from whether the coded behavior is consistent with verified Amadeus/domain evidence. Domain-sensitive Amadeus claims actually used within the frozen implementation slice must be supported by the project's required domain/SME validation process (Decision 7 in the canonical decisions ledger) before they are treated as authoritative training content — passing implementation tests does not substitute for that validation, and this verification stage does not weaken or replace that authority.

Any deviation must be identified and classified before it is corrected.

---

17. Self-Testing as a Learner

Once a meaningful working product exists, the user personally uses DEIXEN as a learner.

This is not merely a software QA pass.

The purpose is to test:

Does DEIXEN actually teach me?

The user should experience real learning paths from:

Learning → Practice → Error → Feedback → Correction → Retry → Independent Performance → Assessment → Progression → Reinforcement → Transfer

Record:

- confusion,
- unclear explanations,
- insufficient or excessive help,
- false confidence,
- weak feedback,
- useless repetition,
- unfair assessment,
- unclear progression,
- cognitive overload,
- and any difference between the approved Learning Design and the actual experience.

---

18. Real Learner Testing

After major issues discovered during self-testing have been addressed, test DEIXEN with real learners.

Evaluate:

- actual learning,
- independent performance,
- memorization versus understanding,
- Coach dependency,
- assessment validity,
- transfer,
- retention,
- confidence versus competence,
- progression quality,
- and learner friction.

This is the stage at which empirical learning effectiveness can begin to be evaluated.

Documentation and design review alone cannot prove empirical learning effectiveness.

---

19. Evidence-Based Improvement

All later improvement follows:

Evidence → Diagnosis → Correct Authority → Change → Verification → Re-test

Every discovered issue must be assigned to the correct layer:

- domain truth,
- knowledge,
- Learning Design,
- learner experience,
- visual design,
- content,
- implementation,
- measurement,
- or product behavior.

Do not redesign the entire system because of an isolated observation.

Do not add a feature without a justified problem.

Do not reopen a closed decision without new evidence.

---

20. Phase Closure Rule

Whenever a phase is genuinely completed, update this roadmap.

Record:

- what was completed,
- which files became final,
- which decisions were approved,
- which questions remain open,
- which validation dependencies remain,
- what changed from the previous roadmap,
- and what the next phase is.

This roadmap is the project's current execution map.

It is not a replacement for the authoritative project files.

---

21. Non-Negotiable Rules

1. Never invent Amadeus behavior.
2. Never use the old repository as authority for the new Learning Design.
3. Never weaken the learning target merely to accommodate an old implementation.
4. Never equate completion with competence.
5. Never equate assisted success with independent competence.
6. Never make mastery or readiness claims stronger than their evidence.
7. Never treat general learning research as proof that DEIXEN itself is effective.
8. Never treat design documentation as proof of learning effectiveness.
9. Never silently override current canonical decisions.
10. Never turn every learning problem into a feature.
11. Use minimum justified complexity.
12. Preserve uncertainty where evidence is insufficient.
13. Keep domain truth, design decisions, implementation dependencies, and hypotheses distinct.
14. Sonnet must self-review before the final Opus review.
15. Opus must independently adversarially review the complete pre-design foundation before it is closed.
16. Real learner testing is required to evaluate actual learning effectiveness.
17. Keep this roadmap updated when a phase is genuinely closed.
18. Model capability does not confer decision authority — Opus, or any model used on this project, remains subordinate to canonical project artifacts, verified domain evidence, approved decisions, and explicit project-owner authority, regardless of how capable that model is.

---

22. Current Execution Sequence

Existing Canonical Knowledge
↓
Amadeus Reference Files — Sonnet [IN PROGRESS]
↓
Learning Design — Sonnet [COMPLETED / READY FOR FINAL REVIEW]
↓
Learning Experience Architecture — Sonnet [COMPLETED / READY FOR FINAL REVIEW]
↓
Any genuinely required pre-design system/engineering documents — Sonnet [ONLY IF REQUIRED]
↓
Sonnet Self-Review & Consolidation
↓
Evidence/State Confirmation Gate
↓
Final Comprehensive Adversarial Review — Opus 5
↓
Resolve Findings + Final Closure Verification
↓
Close Knowledge + Learning Foundation
↓
Claude Design
↓
User Approval of Final Design
↓
Claude Code Implementation
↓
Implementation Verification (including the domain/SME validation check)
↓
Self-Testing as a Learner
↓
Real Learner Testing
↓
Evidence-Based Improvement

---

23. Current State

Active Phase:

Sonnet is completing the remaining Amadeus Reference Layer work. The Learning Design Specification and the Learning Experience Architecture are both now completed as first-build foundation artifacts, awaiting the Evidence/State Confirmation Gate and the final independent adversarial review — neither is canonical yet.

Current objective:

Finish the remaining Amadeus reference work, then consolidate the entire pre-design foundation for review.

Next major gate:

The Evidence/State Confirmation Gate, followed by Opus 5's final comprehensive adversarial review of the completed foundation.

After that review:

Resolve the findings that genuinely require action, perform the final closure verification, and formally close the Knowledge + Learning Foundation.

After successful closure:

Claude Design begins, directed within the approved foundation and informed by Opus's strategic reasoning where useful, always subject to the project owner's final approval.

Implementation does not begin before the Knowledge + Learning Foundation and final visual direction are approved.

This phase operates under a one-month project budget. The operating objective is the strongest practical result achievable through disciplined use of Opus 5 — stronger sourcing, tighter task decomposition, precise prompting, and adversarial review — not the maximum theoretical model capability available at any cost.

---

24. Definition of Success

DEIXEN is not considered successful merely because it:

- looks professional,
- contains many Amadeus commands,
- has progress tracking,
- has a Coach,
- contains scenarios,
- or resembles a training product.

The real success criterion is whether evidence from actual use shows that learners can develop the intended skills and progress toward independent, accurate, useful performance without being given false confidence.

Professional appearance, product quality, technical correctness, domain accuracy, and strong learning design all matter.

None of them alone proves learning effectiveness.

The ultimate standard is not how convincing DEIXEN looks.

It is whether DEIXEN genuinely helps people become better at the skills it claims to teach.
