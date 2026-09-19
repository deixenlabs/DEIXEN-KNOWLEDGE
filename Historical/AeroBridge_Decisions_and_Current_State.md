AeroBridge — Decisions & Current State
1. Document Purpose
This document is the control document for AeroBridge decisions and project state.
Its purpose is to prevent:
Reopening closed decisions without evidence.
Losing project direction.
Jumping between phases.
Repeating previous discussions.
Introducing conflicting ideas.
This document defines:
Approved decisions.
Open questions.
Current project phase.
Completed work.
Restricted changes.
Allowed next actions.
2. Document Authority
Decision priority:
Explicitly approved decisions in this document.
Current approved architecture.
Evidence-based review outcomes.
New suggestions.
Historical discussions, old audits, and previous ideas are references only. They do not automatically override approved decisions.
This document is also the sole owner of any fact that identifies the current implementation baseline exactly — target path, source-tree hash, archive hash, and verification status. Other documents in this set describe what the baseline is *for*; only this document states what it currently *is*. This convention exists because it was violated once already: an earlier version of `AeroBridge_Product_Architecture_and_Rules.md` and `AeroBridge_Design_System_and_UX_Principles.md` each restated a specific baseline hash directly, the baseline was replaced a second time, this document was updated to reflect that, and the other two were not — so they went on citing a target this document had already marked unavailable. Both have been corrected to reference this document instead of restating the value. Anyone reading this document set should treat a hash or path appearing anywhere outside this document as suspect by default.
2A. Referenced Artifacts
This document and the decisions within it reference several supporting artifacts that are not themselves part of the five-document core knowledge baseline defined in Section 4. They are named here so their existence — and their absence from any given review's supplied materials — is visible rather than silent.
AeroBridge_Pre_Phase3_Arbitration_and_Scope.md
The canonical record of the Claude/Manus cross-review arbitration referenced throughout Sections 3, 6, and 14. This document summarizes its outcome; it does not reproduce its full content.
AeroBridge_Domain_SME_Validation_Brief.md
The validation brief governing the Domain/SME Validation Dependency (Decision 7). Defines the claim boundaries for the current command model and scenario semantics.
SME-01 through SME-10 claim register
The execution packet within the validation brief tracking individual domain claims through to SME verdict.
Any audit or review of this document set should independently verify these artifacts' content and currency before treating claims that depend on them — such as "Phase 3 gate state: CLOSED" — as fully self-contained facts of the five core documents alone.
3. Current Project Status
Current Phase
Phase: Prototype Entry / Visual Direction Stabilization
Current Objective
Execute the approved Prototype scope on the controlled baseline, using the approved product/UX behavior as the behavioral baseline and stabilizing the visual language through bounded design exploration and Terminal-first implementation.
The project must not enter uncontrolled product or architecture redesign. Visual design exploration is permitted inside the approved product direction when it does not change architecture, behavior contracts, or top-level structure.
Current Review State
The independent pre-Phase 3 review cycle is complete.
Manus: Independent implementation-aware review completed.
Claude: Independent review completed; treated as an audit snapshot, not as the definition of current Knowledge after subsequent updates.
Cross-review arbitration: completed against the five current knowledge documents and the evidence supplied by both reviews.
Phase 3 gate state: CLOSED for the bounded approved slice; full-scale Phase 3 remains out of scope.
The authoritative implementation baseline is now established as a controlled rebuild; bounded Phase 3 implementation is authorized within the frozen slice, with domain-sensitive claims retained as an explicit external validation dependency.
Arbitration must distinguish:
Confirmed current-state decisions.
Findings confirmed only in an archived/unverified implementation candidate.
Findings stale or resolved in the current Knowledge baseline.
Open product/architecture decisions.
Validation-gated items.
Recommendations that are not yet decisions.
Canonical arbitration record:
AeroBridge_Pre_Phase3_Arbitration_and_Scope.md
4. Completed Foundations
Product Identity
Completed:
AeroBridge positioning defined.
Product category clarified.
Target audience defined.
Difference from LMS/travel products established.
Saudi Market Readiness established as an important product outcome.
Product Architecture Baseline
Completed:
The approved five-area structure:
Home / Flight Deck
Learning / Curriculum
Terminal / Practice
Scenario Bank
Growth / Readiness
Core Product Principle
Completed:
Terminal is confirmed as the operational heart of AeroBridge.
The platform must preserve the core transformation:
Learning → Terminal / Practice → Scenario → Assessment → Evidence → Growth / Readiness
Assessment is an internal state within the learning/practice journey, not a separate top-level product area.
Knowledge Structure
Prepared:
Five core knowledge documents:
AeroBridge_Master_Context.md
AeroBridge_Product_Architecture_and_Rules.md
AeroBridge_Design_System_and_UX_Principles.md
AeroBridge_Decisions_and_Current_State.md
AeroBridge_AI_Working_Rules.md
These five documents form the current project knowledge baseline. See Section 2A for supporting artifacts referenced by, but not included in, this baseline.
5. Closed Decisions
Decision 1 — Product Positioning
Status: Closed
Decision:
AeroBridge is a professional aviation operations training platform.
It is not:
A travel application.
A generic LMS.
A content-only learning platform.
Decision 2 — Terminal Priority
Status: Closed
Decision:
Terminal is the core operational engine of AeroBridge.
Any future design or architecture proposal must protect this role.
Decision 3 — Top-Level Navigation
Status: Closed
Decision:
The product structure contains five primary areas only:
Home / Flight Deck
Learning / Curriculum
Terminal / Practice
Scenario Bank
Growth / Readiness
Adding additional top-level areas requires explicit review. This includes directions discussed but not architecturally placed, such as the Work Shift Simulator concept recorded as Future Vision in `AeroBridge_Master_Context.md` — it does not become a sixth area by default.
Decision 4 — Platform Direction
Status: Closed
Decision:
The direction is:
Responsive Web Application → Mobile-first architecture → PWA-ready foundation → PWA capabilities when justified
The product does not start as PWA-first.
Decision 5 — Design Positioning
Status: Closed
Decision:
The visual direction is:
Dark operational aviation environment
The product should feel like:
Professional simulation software.
Operations environment.
Aviation technology platform.
Not:
Generic education software.
Consumer application.
The interface must also maintain professional vitality: it should feel alive, authored, and visually engaging through purposeful imagery and visual storytelling where appropriate, without becoming a travel website, photo gallery, or generic AI-generated interface. The complete anti-pattern list this decision must avoid is maintained in `AeroBridge_Design_System_and_UX_Principles.md`.
Decision 6 — Responsive Density & Proportion
Status: Closed
Decision:
AeroBridge must maintain professional, balanced visual density across screen sizes.
Cards and UI elements must not be enlarged merely to fill space, nor reduced simply to fit more content. Layout dimensions, spacing, composition, and density must adapt to the viewport, the role of the element, and the importance of the content while preserving readability and touch usability.
On mobile, the goal is organized compactness:
Minimize unnecessary dead space.
Avoid excessive vertical stacking.
Avoid oversized cards.
Avoid overly small or compressed controls.
Preserve the Terminal's required operational workspace.
Validation must include at least:
320px
360px
390px
430px
Tablet and desktop breakpoints (768 / 1024 / 1280–1440px) carry the same density discipline — see `AeroBridge_Design_System_and_UX_Principles.md`, which now defines them explicitly alongside the mobile set.
Decision 7 — Vertical Slice Before Scale
Status: Approved Baseline Rule
The full principle is defined in `AeroBridge_Product_Architecture_and_Rules.md` §8, which is its canonical owner. This decision record confirms the principle is adopted: before expanding AeroBridge across large numbers of lessons, command families, scenarios, competencies, or readiness signals, at least one complete end-to-end vertical slice must be validated using real, internally consistent content and evidence. The specific frozen boundary for the current slice — workflow family, command set, scenario count, Coach touchpoints — is Decision 8A below, not this record.
6. Open Decisions
These items require future evidence, arbitration, or explicit approval. Most below are recorded as Closed because they are the log of decisions already made — the Open items proper are Decision 11 at the end of this section and the domain/SME dependency in Decision 7.
Open Decision 1 — Final Pre-Phase 3 Audit Verdict
Status: Closed — RED / NOT READY
Decision:
Claude's audit is complete and retained as an audit snapshot.
Manus's independent implementation-aware audit is complete.
Claim-by-claim arbitration is complete.
The product direction and five-area target architecture remain approved and are not reopened.
Bounded Prototype implementation is authorized within the frozen slice; full-scale expansion remains out of scope.
Visual language exploration/refinement is permitted as Prototype work, provided it preserves the approved product identity, behavior, architecture, and evidence contracts.
Reference:
AeroBridge_Pre_Phase3_Arbitration_and_Scope.md
Decision 2 — Implementation Target / Baseline Verification
Status: Closed — Replacement Controlled Baseline Approved
The historical controlled-rebuild baseline:
a94b6ef06a90c412f52c9efe0ed1f5db59accd5c598c1814d5e812cc353b883d
is formally recorded as APPROVED BUT UNAVAILABLE / NOT RECOVERABLE.
It was not reconstructed, renamed, or reinterpreted as the replacement.

A new explicitly controlled rebound baseline was created from the verified R1 archive and is now the current implementation baseline.

Current implementation baseline:
Identity: AeroBridge Rebound Baseline — Replacement Controlled State
Replacement source-tree SHA-256: 5ac247872c628b900afc5abf2d090a94ed5f764f8b3d44f7764b3d5c1fa595aa
Replacement archive SHA-256: 7ca3beb812ce54c1fb670096db9ab129fb6b67c6475d182f085334b7db53635d
Source file count: 85
Source basis: R1 controlled source tree / replacement controlled state
Changed paths: client/src/pages/Home.tsx, client/src/index.css only
Verification: pnpm run check PASS; pnpm run build PASS; focused regression matrix PASS; protected-behavior verification PASS; mobile/desktop no-horizontal-overflow validation PASS; archive extraction and source-tree SHA re-verification PASS.
Persistent recovery location:
 /home/ubuntu/projects/aerobridge-934d8fe2/replacement-controlled-state/AeroBridge_Rebound_Baseline_Replacement_Controlled_State.zip

This decision does not claim byte-for-byte recovery of the unavailable historical baseline. The 5ac247... replacement hash is the authoritative implementation baseline for subsequent work.
Correction of record: `AeroBridge_Product_Architecture_and_Rules.md` and `AeroBridge_Design_System_and_UX_Principles.md` had each independently restated the now-unavailable a94b6ef0...883d hash as if it were current, because they were not updated when this replacement decision was recorded. Both have been corrected in the 2026-08-24 Foundation Audit rewrite to reference this Decision instead of duplicating the value — see Section 2 above.
Decision 3 — Evidence and Readiness Contract
Status: Closed — Approved Contract
A learner-facing metric may be presented as personal evidence only when its source, ownership, calculation, scope, and qualification are explicitly defined and traceable.
Approved evidence classes:
Recorded: directly produced by learner action and persisted in the existing evidence record.
Calculated: deterministically derived from owned recorded evidence.
Illustrative: static/contextual/prototype value; must be explicitly labeled and is not learner proof.
Planned / Unavailable: future or unsupported measurement; must be labeled and not presented as current performance.
Current binding rules:
Assessment evidence comes from the learner's actual session/command actions and the existing assessment record.
Growth/Tracking aggregates may use only the existing persisted aerobridge-progress-records records and deterministic aggregations of those records, using the persistence architecture defined in `AeroBridge_Product_Architecture_and_Rules.md` §7.
Skill values remain illustrative until a real aggregation formula and evidence owner are approved.
Streaks remain non-trust-bearing until a dated-session continuity rule is approved.
Scenario performance/competency claims require scenario-specific learner evidence; navigation or labels are not evidence.
Customer Service remains a separate global competency and is not inferred as Saudi-specific by default.
Saudi Market Readiness remains the approved market-specific outcome composed conceptually of Technical Competency + Global Professional Customer Service + Saudi-Specific Operational/Market Context + Saudi-Context Scenario Performance + Assessed Workplace Decisions. No readiness percentage, weighting, threshold, or pass/fail claim is authorized until its component evidence owners and calculation rule are separately validated/approved.
For the first vertical slice, the evidence chain must be traceable as:
learner action → evidence record → deterministic calculation → displayed metric → explicit scope/qualification
This closes the governance contract without inventing unsupported formulas or readiness claims.
For the frozen slice specifically, the single Growth/Readiness output this contract authorizes is a qualitative, evidence-backed status (for example: Completed / In Progress / Needs More Practice, derived directly from the one scenario's recorded outcome) — not a numeric score or percentage, which remains unauthorized until a formula is separately approved.
Decision 4 — Assessment State Contract
Status: Closed — Approved Contract
Assessment is defined as a continuous current-session assessment state, not a historically isolated state. Entering Assessment does not silently reset the current command history or hint state. However, prior persisted/localStorage evidence records are never merged into the current assessment score.
Binding rules:
Commands already entered in the current live session may remain visible and may be included in the assessment readout.
Persisted records from previous assessment sessions are not merged into the current score.
The Assessment UI must disclose the current-session handoff whenever prior current-session commands or hints are present.
The Assessment hint label must be derived from actual hintCount; it must never claim No hints when hints were used.
A zero-history / zero-hint Assessment has no carry-over disclosure because there is nothing to disclose.
This contract does not authorize a clean-reset redesign, scoring change, persistence-schema change, or new Assessment route.
The existing scoring formula and record schema remain unchanged unless a separately approved decision changes them.
Evidence basis: the controlled replacement baseline implements this bounded state/disclosure behavior and its focused regression matrix passed for zero-history, carry-over, hint-label, scoring, and persistence checks. This closes the semantic contract without asserting that Assessment is a separate clean session.
Decision 5 — Scenario Differentiation Contract
Status: Closed — Approved Contract
Scenario Bank entries are not considered behaviorally distinct merely because they have different titles, categories, badges, imagery, or context labels. A scenario is differentiated only when its definition changes at least one meaningful operational condition that the learner must respond to and that can be observed in the resulting assessment/evidence.
Binding rules for every implemented scenario:
Objective: one explicit operational objective owned by the scenario.
Constraints: one or more scenario-owned task constraints that materially affect what the learner must do, decide, sequence, or avoid.
Expected behavior: explicit scenario acceptance criteria that can be evaluated from learner actions/state.
Feedback: scenario-aware feedback must reference the scenario objective/constraint/outcome; generic command feedback alone does not satisfy differentiation.
Assessment linkage: the assessment reads the scenario definition and evaluates the scenario-owned expectations; a scenario label must never masquerade as scenario evidence.
Evidence linkage: any scenario performance claim must trace to an actual learner action/result captured in the evidence record.
State integrity: scenario context may affect behavior and scoring only through owned state/data; no hidden global mutation or presentation-only branching.
Domain validation: operational/GDS semantics used by a scenario remain validation-gated until the required domain/SME review is assigned and completed.
Truthful availability: a scenario may be shown as planned/unavailable when its behavioral contract is not implemented; it must not be represented as completed competency.
Minimum Vertical Slice requirement: One scenario must demonstrate a behaviorally meaningful difference from generic Terminal practice, with the difference visible in task constraints, expected behavior, assessment, or feedback and traceable into evidence. The first slice does not require a full Scenario Bank or pressure/exception system.
Protected boundary: This contract does not authorize invention of aviation/GDS behavior, a broad scenario taxonomy, a new assessment route, a new scoring formula, or expansion of the top-level navigation. Those remain separately governed.
Acceptance evidence: the controlled replacement baseline establishes the preserved pre-Phase-3 state and the review arbitration established the need for behavioral differentiation; Phase 3 implementation must prove the contract with one real differentiated scenario before Scenario Bank scale-up.
Decision 6 — Customer Service Curriculum Contract
Status: Closed — Approved Scope Boundary
Customer Service is approved as a separate global professional competency, distinct from Saudi-specific market readiness. It must not be presented as a fully realized curriculum until its content model, competency structure, assessment logic, and evidence pathway are explicitly defined and supported.
Approved Phase 3 boundary:
Customer Service curriculum authoring is not part of the initial vertical slice.
No Customer Service proficiency, completion, or readiness metric may be presented as measured learner evidence before its evidence pathway is defined.
Any existing Customer Service navigation or preview surface must remain truthful; it must not display Technical milestones as if they were Customer Service curriculum.
Customer Service may remain discoverable as a future/global competency, but an unavailable or in-preparation state is the required representation until its curriculum contract is implemented.
Customer Service evidence may contribute to the future Saudi Market Readiness outcome only through an explicitly approved competency mapping; it is not Saudi-specific by default.
Required future contract fields before full Customer Service implementation:
Content model and progression structure.
Global Customer Service competency model.
Assessment logic and observable performance criteria.
Evidence record ownership and calculation rules.
Domain/SME validation requirements.
Reason: Bound Phase 3 to one real vertical slice without pretending that Customer Service already has a supported curriculum, while preserving the approved global competency and Saudi-market separation.
Status: Approved for scope control; full Customer Service curriculum remains deferred and validation-gated.
Decision 7 — Domain / SME Validation Dependency
Status: Closed — Explicit External Validation Dependency
The domain/SME validation workstream is formally assigned for the Phase 3 vertical slice. It covers the current command model (AN / SS / FQD / FXP) and the operational semantics of the selected scenario.
Validation artifact: AeroBridge_Domain_SME_Validation_Brief.md
Execution packet: SME-01 through SME-10 claim register for the frozen vertical slice.
Current dependency: SME verdicts/source basis are still required for any domain-sensitive claim. Their absence no longer blocks non-domain-dependent implementation inside the frozen Phase 3 slice. No authoritative aviation/GDS behavior is being promoted from AI inference.
Ownership:
Product owner: scope, claim boundaries, and final acceptance.
Aviation/GDS domain SME: operational truth and workflow validation.
Implementation/QA: deterministic verification against the validated contract.
Expanded command families, curriculum content, scenarios, and operational claims require appropriate domain validation before they are presented as authoritative training behavior. Unknown or unvalidated aviation/GDS behavior remains explicitly validation-gated.
Domain validation pipeline: every domain-sensitive claim moves through the same sequence — Source → Review → Approval → Structured content → Implementation → QA. It never moves through AI generation → implementation → assumed truth. A claim that has not completed this pipeline is not authoritative regardless of how confidently it reads.
Decision 8A — Vertical Slice Implementation Boundary
Status: Closed — Frozen / Domain-Validation-Pending
The initial Phase 3 vertical slice is frozen to prevent scope drift while the remaining domain evidence is completed.
Frozen slice:
Path: Learning → Terminal / Practice → Scenario → Assessment → Evidence → Growth / Readiness
Workflow family: Pricing & Ticketing
Terminal command boundary: AN → SS → FQD → FXP only.
Scenario count: 1 behaviorally differentiated scenario.
Evidence: 1 owned assessment record generated from real learner actions.
Growth/Readiness: 1 bounded slice-level output derived from that evidence; no unsupported Saudi Market Readiness percentage/threshold.
Coach: Core Guided Learning Layer spanning the end-to-end slice, with required touchpoints in Learning, Terminal / Practice, Scenario, Assessment, and Growth / Readiness.
Coach behavior must be state-bound to actual learner actions, errors, hints, assessment state, and available evidence; it must not be implemented as a static generic help panel.
Deferred: full curriculum authoring, full Scenario Bank expansion, Customer Service curriculum, new GDS/aviation semantics, broad Saudi readiness scoring, backend/auth/PWA expansion, new routes/top-level areas, scoring/persistence redesign, and full visual rebrand that discards the approved AeroBridge identity.
Boundary rule: any change to the workflow family, command set, scenario count, assessment semantics, evidence type, Growth/Readiness output, or Coach role/touchpoints requires an explicit decision update with evidence.
Current status: the boundary is frozen and implementation-ready in scope, but authoritative aviation/GDS semantics remain domain-validation-gated until the SME validation record closes.
Decision 9 — Coach Core Guided Learning Layer
Status: Closed — Approved
Decision:
The Coach is a core guided-learning layer, not a decorative or Terminal-only UI element. It must support the learner across the end-to-end journey and appear at the key moments where guidance materially improves learning or correction.
Required touchpoints:
Learning / Curriculum: orientation, explanation, and next-step guidance.
Terminal / Practice: interpret learner actions, identify mistakes, explain the error, and provide the next useful move.
Scenario: contextual guidance when the learner is stuck or makes a meaningful mistake.
Assessment: feedback and explanation consistent with assessment state and hint semantics.
Growth / Readiness: explain meaningful outcomes and connect them back to evidence without inventing performance data.
State binding:
Coach behavior must be driven by actual learner state, actions, errors, hints, assessment state, and available evidence. It must not behave as a static generic help panel.
Boundary:
Coach guidance must remain truthful to the current product state and validated domain semantics. Domain-sensitive aviation/GDS guidance remains validation-gated until SME validation.
Phase 3 status:
The Coach is part of the frozen Phase 3 vertical slice and must not be deferred as a later enhancement.
IA placement note: this contract defines Coach's required behavior and touchpoints, not its layout ownership (a global element versus a component embedded per page). That placement choice is Open — Manus may resolve it within the Frozen/Directional/Open model in `AeroBridge_AI_Working_Rules.md`, consistent with the approved anti-pattern list's caution against decorative overlays without functional need.
Decision 10A — Manus Collaboration Protocol
Status: Closed — Approved Operating Rule
Decision:
The Manus Collaboration Protocol is adopted as the standard operating protocol for Manus-assisted AeroBridge design and implementation work. The protocol is maintained inside `AeroBridge_AI_Working_Rules.md` and separates Creative Exploration, Decision, Execution, Rejection / Correction, Iteration, Reference-Driven Design, and Drift Recovery.
Reason:
Repeated design iterations showed that combining exploration and execution caused safe local refinement, implementation inertia, and weak reference interpretation. The protocol creates an explicit contract between creative freedom and execution commitment.
Evidence:
Manus's documented guidance states that complex tasks benefit from explicit planning/alignment before execution, and the project observed repeated drift toward the existing codebase when large redesign requests were combined with preservation constraints.
Impact:
Future Manus tasks should declare the applicable mode when ambiguity is likely. Approved decisions become binding for execution; rejected decisions become invalid; references are treated as directional visual evidence; Frozen / Directional / Open boundaries must be explicit for significant tasks.
Status: Approved

Decision 10 — Cross-Review Arbitration Outcome
Status: Closed — Approved Outcome
The Claude and Manus reviews are accepted as two independent review legs, not as competing sources of truth.
Arbitration outcome:
The five-area architecture remains approved.
Terminal centrality remains approved.
The product/architecture design direction remains approved and is not being reopened. Prototype work may refine and strengthen the visual language within that approved direction; this is visual execution, not product/architecture redesign.
Claude findings are treated as an audit snapshot; findings are not promoted to current-state defects unless current evidence supports them.
Manus runtime findings from the archived candidate are treated as direct evidence of that candidate only unless verified against the authoritative target.
Findings that are confirmed in both reviews are retained as high-confidence issues, but their current-state status is still target-dependent when the implementation target is unavailable.
No audit score is promoted to a product metric.
Canonical record:
AeroBridge_Pre_Phase3_Arbitration_and_Scope.md
Decision 11 — Localization / RTL Scope
Status: OPEN
No document in this set states whether AeroBridge requires Arabic-language interface support or right-to-left layout. Saudi Market Readiness (Decision, `AeroBridge_Master_Context.md`) is defined as a content and competency outcome, not explicitly as a localization requirement — but a product with a named Saudi-market outcome leaving this unstated is a gap worth closing deliberately. This is not resolved by this rewrite: there is no evidence in the current corpus pointing either way, and inventing an RTL requirement without evidence would violate the same discipline this document applies to domain claims. One explicit sentence from the product owner closes this; until then, no RTL-specific implementation work is authorized or blocked by this decision — it is simply unscoped.
7. Restricted Areas
The following must not be changed without explicit review.
Product Core
Do not:
Turn AeroBridge into a content-first platform.
Reduce Terminal importance.
Add unnecessary product sections.
Replace evidence-based readiness with decorative metrics.
Architecture
Do not:
Replace the five-area structure casually.
Add features because they are common in other products.
Copy generic SaaS patterns.
Introduce new top-level areas without strategic review.
Design
Do not, without explicit review:
Move toward classroom aesthetics or any pattern in the canonical anti-pattern list maintained in `AeroBridge_Design_System_and_UX_Principles.md`.
Prioritize visual trends over operational realism.
Make the interface visually sterile merely in pursuit of operational seriousness.
Add imagery only for decoration; visual richness must have contextual or experiential purpose.
Coach
Do not:
Treat Coach as decorative microcopy or a generic static help panel.
Limit Coach to Terminal-only usage.
Provide correction that is disconnected from actual learner actions/state.
Present unsupported domain guidance as authoritative.
Use Coach feedback to invent evidence, scores, readiness, or mastery.
Evidence & State
Do not:
Present illustrative data as real user evidence.
Show success when the action did not occur.
Present readiness claims without a defensible evidence owner.
Treat a UI surface as implemented when its underlying behavior is not supported.
Silently substitute an archived implementation candidate for the authoritative target.
8. Current Review Process State
The project follows:
Raw Inputs → Corpus Verification → Candidate Reviews → Independent Reviews → Arbitration → Final Approved Direction → Implementation Planning
Rules:
Reviews must remain independent until arbitration.
Conclusions require evidence.
Incomplete reviews must not be treated as final.
No implementation changes outside an authorized scope; required domain/SME validation remains mandatory for domain-sensitive aviation/GDS claims before those claims are treated as authoritative.
New findings must be classified against existing decisions.
Already-settled decisions should not be reopened without new material evidence.
9. Pre-Phase 3 Gate
Bounded Prototype / Phase 3 implementation may proceed within the approved frozen slice because the required gate controls are closed for that bounded scope. Domain-sensitive aviation/GDS claims remain separately validation-gated:
The authoritative implementation target is verified — MET via approved Replacement Controlled Baseline.
Critical evidence/provenance issues are resolved or explicitly gated — MET for the approved Replacement Controlled Baseline and closed Evidence & Readiness Contract.
Assessment state semantics are defined — MET via the closed Assessment State Contract.
The vertical-slice pattern is agreed, validated through the accepted slice baseline, and is the behavioral baseline for Prototype work.
High-impact product and architecture contradictions are resolved. This includes the baseline-hash contradiction between documents identified and corrected in the 2026-08-24 Foundation Audit — see Section 2.
Domain validation requirements are identified and assigned — CLOSED as a dependency-control decision; execution/evidence remains pending and claim-gated.
Coach role and end-to-end touchpoints are explicitly controlled by an approved decision and incorporated into the frozen slice.
The final Phase 3 scope is explicit.
Newly approved features have clear purpose, behavior, and evidence contracts.
The gate does not require the entire future product to be implemented before Phase 3. It requires the foundations and contracts needed to implement Phase 3 safely.
10. Next Allowed Actions
Allowed now:
Work against the verified Replacement Controlled Baseline at the recorded target/hash in Decision 2.
Close the remaining Customer Service and Domain/SME contracts.
Update the five knowledge documents only when a decision is explicitly approved.
Finalize the Customer Service Curriculum Contract before representing it as implemented.
Assign and execute required domain/SME validation.
Proceed with Prototype implementation on the verified target, beginning with Terminal-first visual execution and preserving the frozen behavioral slice, approved Coach layer, and required state/evidence bindings without expanding the slice boundary.
Execute the assigned Domain/SME validation for the frozen scenario and command semantics.
Not yet allowed:
Large-scale Phase 3 implementation beyond the frozen slice.
Using the unavailable historical baseline hash as an acceptance target for the replacement baseline.
10A. Phase 3 Scope Boundary — Approved for Implementation
Phase 3 is limited to implementing and validating the approved product direction, not redesigning the product or expanding every future capability at once.
In scope
Verified target restoration and baseline replay.
Evidence/provenance and truthful-state hardening.
Assessment-state semantics and disclosure implementation after decision closure.
Minimum viable Scenario Differentiation behavior required for the vertical slice.
Learning/Curriculum surface sufficient to support one real end-to-end learning path, using the minimal content schema defined in `AeroBridge_Product_Architecture_and_Rules.md` §6.
Terminal/Practice behavior required for that slice, using the state skeleton defined in `AeroBridge_Product_Architecture_and_Rules.md` §5.
Coach behavior sufficient to provide guided learning, correction, next-step guidance, and contextual feedback across the approved vertical-slice touchpoints, using actual learner state/actions/errors/hints/assessment/evidence.
Evidence generation and Growth/Readiness output for that slice, using the persistence architecture defined in `AeroBridge_Product_Architecture_and_Rules.md` §7.
Targeted responsive/mobile/accessibility validation required by the approved design system, including the Accessibility Baseline and tablet/desktop breakpoints in `AeroBridge_Design_System_and_UX_Principles.md`.
Systemic false-affordance cleanup where current-target evidence confirms the behavior.
Explicitly deferred from Phase 3 entry
Full-scale curriculum authoring across all command families.
Full Scenario Bank expansion.
Broad Customer Service curriculum implementation before its contract is closed.
New GDS/aviation semantics without domain validation.
Backend/auth/PWA expansion unless separately justified by evidence.
Architecture redesign, new top-level areas, or a full visual rebrand that discards the approved AeroBridge identity.
Work Shift Simulator implementation, pending the open architectural-placement question in `AeroBridge_Master_Context.md`.
Entry condition
Phase 3 bounded implementation begins on the verified Replacement Controlled Baseline. Domain-sensitive semantics remain quarantined until SME evidence closes the relevant claim register entries. No unvalidated aviation/GDS behavior may be published as authoritative training behavior.
10B. Definition of Done
This section did not exist as a single checklist in prior versions of this document; the criteria were scattered across the Pre-Phase 3 Gate, Restricted Areas, and Vertical Slice sections above. It is assembled here so "done" has one unambiguous meaning rather than drifting toward either "the screenshot looks finished" or "an unnecessarily large backend got built."
The Phase 3 vertical slice is done when all of the following hold:
Implementation is verified against the exact current baseline recorded in Decision 2 above — not a stale hash.
A learner can complete the one real Pricing & Ticketing learning path end to end, using real content, not placeholder labels.
Terminal supports the frozen AN → SS → FQD → FXP boundary with working valid/invalid input handling, hints, and completion detection, per the state skeleton in `AeroBridge_Product_Architecture_and_Rules.md` §5.
The one scenario is behaviorally distinct per Decision 5 — different constraints and expected behavior, not just a different title.
Assessment behaves per Decision 4: accurate hint labeling, correct carryover disclosure, no cross-session score merging.
Evidence persists and traces correctly per Decision 3's chain, using the persistence architecture in `AeroBridge_Product_Architecture_and_Rules.md` §7.
Growth/Readiness shows the one bounded, evidence-backed qualitative output described in Decision 3 — no invented percentage or threshold.
Coach behaves correctly at all five required touchpoints from Decision 9, state-bound to real learner actions, not a static panel.
No false affordance remains anywhere in the slice: every visible control either works or is truthfully labeled planned/unavailable.
Responsive validation passes at 320/360/390/430px and at the tablet/desktop breakpoints defined in `AeroBridge_Design_System_and_UX_Principles.md`.
The Accessibility Baseline in `AeroBridge_Design_System_and_UX_Principles.md` is met for the slice surfaces.
A reset/seed mechanism exists per `AeroBridge_Product_Architecture_and_Rules.md` §7 and produces a clean training state on demand.
Domain-sensitive claims actually used within the slice are SME-validated per Decision 7, not merely implemented.
Explicitly not required for this Done: full curriculum authoring, full Scenario Bank, Customer Service implementation, backend/auth, PWA-first behavior, or any Saudi Readiness scoring formula. All remain correctly out of scope per Decision 8A.
Every future phase is done by the same underlying test, applied to its own scope: its Feature Behavior & Evidence Contract (`AeroBridge_AI_Working_Rules.md`) is closed, its responsive and accessibility validation has passed, and any domain-sensitive content within it is SME-validated.
11. Not Allowed Currently
Not allowed:
Starting a new product or architecture redesign direction without explicit review.
Rebuilding the architecture based on opinions alone.
Adding features without strategic justification.
Skipping review stages.
Treating AI suggestions as approved decisions.
Expanding beyond the frozen Phase 3 slice without an explicit decision update.
Treating pending SME-dependent claims as authoritative.
Promoting an unverified or historical implementation tree to the official baseline.
12. Decision Update Rules
Any new decision must include:
Decision
What was decided?
Reason
Why was it decided?
Evidence
What supports it?
Impact
What changes because of it?
Status
Open / Approved / Rejected / Validation-Gated
No major decision should be treated as final without enough evidence to support its scope and consequences.
13. Current North Star
Every decision must support:
AeroBridge helps users become operationally ready for real airline reservation and ticketing work through realistic practice and measurable capability.
The product must pursue genuine job readiness, including the intended Saudi-market outcome, without overstating what its evidence can prove.
If a decision does not strengthen this goal, it requires review.
14. Current Arbitration State
As of 2026-08-22, corrected 2026-08-24:
Review cycle: Complete
Claude status: Completed audit snapshot
Manus status: Completed independent implementation-aware audit
Arbitration: Complete
Product/architecture redesign authorization: No
Phase 3 implementation authorization: Approved — bounded frozen-slice implementation; domain-sensitive claims remain validation-gated
Vertical slice implementation boundary: Frozen — Pricing & Ticketing / AN→SS→FQD→FXP / 1 differentiated scenario / Coach included across approved touchpoints
Authoritative implementation target: Verified Replacement Controlled Baseline (see Decision 2 — the sole current record of its exact hash/path)
Historical baseline: a94b6ef06a90c412f52c9efe0ed1f5db59accd5c598c1814d5e812cc353b883d — APPROVED BUT UNAVAILABLE / NOT RECOVERABLE
Current replacement source-tree hash: 5ac247872c628b900afc5abf2d090a94ed5f764f8b3d44f7764b3d5c1fa595aa
Current replacement archive hash: 7ca3beb812ce54c1fb670096db9ab129fb6b67c6475d182f085334b7db53635d
Protected baseline replay: PASS for the documented check/build + focused regression matrix
Vertical slice contract: Approved and boundary frozen; Vertical Slice implementation accepted/closed per current project state.
Coach contract: Approved and included in the frozen vertical slice; integrated in the accepted slice baseline.
Localization/RTL scope: OPEN — see Decision 11.
Document corpus consistency: the baseline-hash contradiction between this document and `AeroBridge_Product_Architecture_and_Rules.md` / `AeroBridge_Design_System_and_UX_Principles.md` identified by the 2026-08-24 Foundation Audit is resolved — both now reference this document rather than restating the hash.
Current work: Prototype execution, beginning with visual-language stabilization and Terminal-first implementation.
The current state is therefore YELLOW / Controlled Prototype State: bounded execution is authorized within the frozen slice, while domain-sensitive aviation/GDS claims remain explicitly validation-gated.
