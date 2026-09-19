AEROBRIDGE — STAGE 4 MASTER CONSENSUS AUDIT PROMPT

Purpose

You are participating in Stage 4: Master Consensus Generation of a multi-stage audit pipeline for the AeroBridge prototype.

The pipeline is:

"9 independent audits → 9 consolidated drafts → 5 unified audits → 3 independent Master Audits → 1 Final Consensus Audit"

Your task is to examine the five Stage 3 Unified Audits attached below or supplied as attachments and produce one independent, evidence-disciplined Master Audit of the AeroBridge prototype.

You are not being asked to summarize, rank, vote on, or mechanically merge the five documents. You must adjudicate them critically, identify which claims are supported, resolve disagreements, reject weak or speculative recommendations, and produce an implementation-ready Master Audit.

The same prompt and the exact same five Stage 3 Unified Audit files, in full and without alteration, will be supplied independently to Claude, Manus, and ChatGPT. Therefore, all three runs must operate on the same evidence corpus and the same instructions. The output must be self-contained, auditable, technically specific, and structured identically across all three runs.

Important: “Master Consensus” describes the pipeline stage, not a requirement to reach consensus with the other models. Claude, Manus, and ChatGPT must each produce an independent adjudication of the same five-file evidence corpus.

---

1. Evidence hierarchy

Use the following hierarchy when evaluating claims:

1. Direct prototype evidence: actual source code, configuration, rendered output, screenshots, runtime behavior, or files explicitly supplied in the evidence package.
2. Original product/design ground truth: "ideas.md", original requirements, stated product boundaries, learning model, and reference-preservation constraints.
3. Rendered visual evidence: supplied screenshots or recordings.
4. Cross-audit agreement: repeated findings across the five Unified Audits. This is a consensus signal only, not independent proof, because the audits may share the same source and screenshots.
5. Design and UX interpretation: expert analysis, heuristics, accessibility reasoning, learning-UX reasoning, and implementation judgment.

Apply source authority according to the type of claim:

- For current implementation facts, actual behavior, technical behavior, and defects, direct source and runtime evidence outrank audit commentary.
- For product intent, learning principles, scope boundaries, and preservation decisions, the original product/design ground truth governs unless the product owner explicitly states that the intent has changed.
- When current source behavior conflicts with intended product behavior, report the conflict explicitly. Do not silently treat either current behavior or intended behavior as the final truth.
- A design or UX interpretation may recommend a change, but it must not override direct evidence or product ground truth without stating the reasoning and uncertainty.

Do not treat repetition as verification. A claim repeated by all five audits is still unverified if none of them provides adequate source or rendered evidence.

When a claim depends on a file, screenshot, runtime state, device, browser, screen reader, deployment configuration, or product-owner decision that is not actually available, classify it as NEEDS VALIDATION rather than presenting it as fact.

Distinguish clearly between:

- Confirmed: directly verified by supplied source, screenshot, or runtime evidence.
- Strongly supported: supported by more than one materially different evidence type.
- Corroborated analysis: repeated or logically supported, but dependent on shared evidence.
- Needs validation: plausible or important, but not provable from the supplied package.
- Rejected: contradicted by stronger evidence, outside scope, or based on an unsupported product assumption.

---

2. Non-negotiable product principles

Treat the following as governing constraints unless direct evidence proves that the current product intent has changed:

«The UI may interpret engine state, but it must never invent engine truth.»

«AeroBridge is a reference-preservation and targeted-hardening project, not a redesign or architecture-reset project.»

Preserve the product’s demonstrated strengths where evidence supports them, including as applicable:

- Flight Deck Console visual identity.
- Terminal-first Practice workstation.
- Learn / Practice / Assessment mode structure.
- Focus Mode and command history where actually implemented.
- Progression → Practice → Assessment → Growth → Tracking → Scenarios learning loop.
- Evidence-to-next-action learning pattern.
- Local/illustrative simulation disclosure.
- Reduced-motion support.
- Same-data chart plus accessible data-table fallback.
- Five-area navigation model and Train/Practice priority, unless the supplied source proves otherwise.

Do not recommend redesign, generic dashboardization, gamification, new top-level routes, new engine commands, scoring changes, backend expansion, authentication, payment, live production integrations, or speculative features unless the supplied evidence and product ground truth explicitly require them.

---

3. Required analytical posture

For every significant finding, answer the following questions:

1. What exactly is the claim?
2. What evidence supports it?
3. Is the evidence direct, rendered, cross-audit, analytical, or missing?
4. What is the user, learning, accessibility, trust, or product impact?
5. How confident are you?
6. Is the recommendation a real defect correction, a design improvement, a product decision, or a speculative feature request?
7. What is the smallest safe intervention that solves the problem without changing the engine, scoring model, information architecture, or learning model unnecessarily?
8. What must remain unchanged?
9. What validation would confirm or overturn the recommendation?

Do not reward a finding merely because it sounds sophisticated. Prefer accurate, scoped, source-traceable findings over impressive but speculative breadth.

Do not convert every visual inconsistency into a P0 issue. Prioritize based on:

"Impact × Confidence × Feasibility × Scope Risk"

A high-impact but unverified claim must not be labeled as a confirmed defect. A low-impact but certain defect should not outrank a confirmed trust or safety defect.

---

4. Mandatory conflict-resolution procedure

Before writing the final recommendations, perform an explicit conflict-resolution pass.

For every material disagreement among the five Unified Audits:

- State the conflicting claims.
- Identify which audit(s) made each claim.
- Trace each claim to the strongest available evidence.
- Determine whether one claim is source-refuted, screenshot-refuted, outdated, or merely unverified.
- Decide: ACCEPT, MODIFY, DEFER FOR VALIDATION, or REJECT.
- Explain the decision in one concise paragraph.

At minimum, check whether the supplied audits disagree about:

- Current versus historical CSS cascade behavior.
- Whether mobile elements are hidden or merely compressed.
- Whether reduced-motion behavior covers the terminal caret and other motion.
- Whether fonts are actually provisioned and rendered.
- Whether viewport zoom is restricted.
- Whether the Coach should be removed, collapsed, converted to a drawer/FAB, or simply made subordinate.
- Whether Assessment should be a route or remain a Terminal mode.
- Whether Growth and Tracking should remain separate.
- Whether MapView should be activated or removed.
- Whether Arabic/RTL is in current scope.
- Whether any proposed state is real engine state or invented UI state.
- Whether numeric values are wrong, future curriculum values, seeded preview values, or merely unlabeled.

Do not silently choose one side of a disagreement.

---

5. Required evaluation dimensions

Your Master Audit must evaluate all five Unified Audits against the following dimensions, even if some dimensions receive a conclusion of “not enough evidence”:

| Dimension | Required questions |
|---|---|
| Evidence verification | Are claims tied to actual files, lines, screenshots, or runtime evidence? |
| Accuracy | Does the audit avoid stale, contradicted, or overgeneralized findings? |
| UX/UI depth | Does it analyze hierarchy, workflows, information architecture, task continuity, and interaction costs? |
| Learning UX | Does it protect recall, assessment validity, evidence interpretation, and next-action behavior? |
| State and interaction analysis | Does it define first-use, empty, ready, processing, success, error, recovery, assessment, locked, unavailable, and loading behavior without inventing engine truth? |
| Accessibility | Does it cover semantics, keyboard, focus, Escape, focus restoration, screen readers, live regions, zoom, contrast, target size, reduced motion, and non-color cues? |
| Responsive behavior | Does it distinguish source-inferred behavior from actual device/keyboard validation? |
| Design system | Does it analyze semantic tokens, typography, color roles, spacing, radii, component states, provenance, and consistency? |
| Prioritization | Are P0/P1/P2 decisions proportionate to impact, evidence, cost, and risk? |
| Uncertainty handling | Are assumptions and validation gaps explicit and operationally useful? |
| Implementation quality | Are recommendations specific, minimal, regression-safe, and testable? |

Do not judge any audit by length alone. A shorter finding with direct evidence may be stronger than a long speculative section.

---

6. Required Master Audit output

Use the following exact structure and section titles.

AEROBRIDGE — MASTER SYNTHESIS AUDIT

Document type: Independent evidence-based adjudication and implementation handoff

Overall direction: Preserve and Refine / Revise / Redesign — select one and justify it.

Design status: Production reference / Needs targeted revision / Not ready for reference — select one and justify it.

A. Executive Decision

State the overall decision in no more than five paragraphs. Include:

- The core product strengths that should be preserved.
- The highest-confidence critical defects.
- The three most important decisions.
- What can proceed now.
- What must remain validation-gated.

B. Evidence and Adjudication Method

Describe:

- The evidence package actually available to you.
- The evidence hierarchy used.
- How the five Unified Audits were treated.
- The difference between direct verification and consensus signal.
- Any files, screenshots, runtime states, devices, or product decisions not available.
- Any conflict between current implementation behavior and intended product/design ground truth.

Include an evidence classification table:

| Class | Definition | Examples from this audit |
|---|---|---|
E4 / Direct| | 
E3 / Strongly corroborated| | 
E2 / Cross-audit analysis| | 
NEEDS VALIDATION| | 
REJECTED| | 

C. Product and Design Principles to Preserve

For each principle, explain:

- What should be preserved.
- Why it is successful.
- What modification is acceptable.
- What must not be changed.
- What evidence supports the conclusion.

Do not merely praise the visual design. Explain its UX, product, learning, and system value.

D. Critical Problems

Create a table with only material problems:

| ID | Problem | Direct evidence | Impact | Severity | Confidence | Decision |
|---|---|---|---|---|---|---|

Use these decision labels precisely:

- MUST FIX
- SHOULD FIX
- COULD IMPROVE
- PRESERVE
- REJECT
- NEEDS VALIDATION

Do not classify a claim as MUST FIX solely because several audits repeat it.

E. Master Decision Matrix

Create a detailed matrix:

| ID | Area | Specific decision | Classification | Evidence class | User impact | Design consistency | Technical feasibility | Confidence | Cost | Risk | Validation needed | What must remain unchanged |
|---|---|---|---|---|---|---|---|---|---|---|---|---|

Every decision must have a clear owner: UI, content, accessibility, product scope, engine, or runtime validation.

F. Required Changes by Priority

F.1 P0 — Blocking / Must Fix

For every P0 item specify:

- Objective.
- Current behavior.
- Exact proposed change.
- What must remain unchanged.
- Dependencies.
- Risks.
- Acceptance criteria.
- Regression tests.

F.2 P1 — High-value / Should Fix

Use the same structure, but keep the scope proportional.

F.3 P2 — Optional / Later

Include only improvements that are not required for trust, core usability, accessibility baseline, or evidence integrity.

G. Component-Level Specifications

Cover the relevant components, including where applicable:

- Shared shell and topbar.
- Primary navigation and mobile rail.
- Primary buttons and operational CTAs.
- Tabs and segmented controls.
- Terminal and command input.
- Terminal history and response output.
- Coach panel.
- Reference drawer and Focus Mode.
- Progress and chart primitives.
- Evidence and metric cards.
- Scenario list and mission detail.
- Growth Record.
- Progress Tracking.
- Language control.
- ErrorBoundary and NotFound/fallback surfaces.

For each component specify:

- Current state.
- Confirmed problem.
- Decision.
- Layout and hierarchy.
- Typography.
- Color and non-color state cues.
- Interaction states.
- Responsive behavior.
- Accessibility behavior.
- Provenance or data ownership where relevant.
- What to preserve.
- What to reject.

Do not prescribe a new component pattern merely because it is fashionable. If the exact pattern is unproven, mark it NEEDS VALIDATION.

H. Screen and Flow Changes

Analyze each major route or product surface:

- Progression.
- Practice / Terminal.
- Assessment as a mode or route.
- Scenarios.
- Growth Record.
- Progress Tracking.
- Shared shell and navigation.
- Cross-screen handoffs.

For each, state:

- Current issue.
- Decision.
- Information hierarchy.
- Interaction behavior.
- Empty, loading, error, locked, and unavailable states.
- Responsive requirements.
- Accessibility requirements.
- Data/provenance requirements.
- What must remain unchanged.

Protect the complete learning loop and identify any risk of breaking context handoffs, local persistence, or assessment evidence.

I. Responsive, Accessibility, and State Requirements

I.1 Responsive requirements

Separate:

- Directly observed behavior.
- CSS/source-inferred behavior.
- Unverified runtime behavior.

Specify a validation matrix for:

- 320px.
- 360px.
- 390px.
- 430px.
- 768px.
- 834px.
- 1024px.
- 1280px or wider.

Include native keyboard testing where relevant. Do not claim that a layout is broken without runtime or rendered evidence.

I.2 Accessibility requirements

Cover, where applicable:

- Landmarks and skip link.
- Heading hierarchy and route-change focus.
- Tab, toggle, pressed, current, and selected semantics.
- Keyboard navigation and roving focus.
- Focus-visible treatment.
- Focus containment, Escape, and focus restoration.
- Accessible names for icon controls.
- Live-region scope and announcement urgency.
- Progressbar and table semantics.
- Contrast and final rendered type size.
- Touch-target size.
- Zoom and text scaling.
- Reduced motion.
- Non-color state communication.
- Screen-reader validation.

Clearly label what is source-confirmed and what needs runtime validation.

I.3 Canonical state matrix

Create a table covering:

| State | Trigger | Visible contract | Allowed action | Evidence/score effect | Accessibility announcement | Confirmed or validation-gated |
|---|---|---|---|---|---|---|

Include at least:

- First use.
- Empty input.
- Ready.
- Processing, only if a real trigger exists.
- Success.
- Partial/review.
- Syntax error.
- Sequence error.
- Recoverable error.
- Interrupted.
- Assessment active.
- Assessment complete.
- Locked.
- Unavailable.
- Loading.
- No evidence yet.
- Illustrative/sample data.

Do not invent engine behavior to fill a state table. If the engine does not expose a state, define only the honest UI contract or mark it validation-gated.

J. Conflict Resolution Log

Provide a table:

| Conflict ID | Conflicting claims | Strongest evidence | Decision: accept/modify/defer/reject | Rationale | Follow-up validation |
|---|---|---|---|---|---|

Include all material conflicts, not only the ones that are easy to resolve.

K. Explicit Rejection List

List recommendations that should not be implemented in this revision, with:

| ID | Rejected recommendation | Why rejected | Evidence or boundary | Future validation needed? |
|---|---|---|---|---|

At minimum consider redesign, dashboardization, new routes, autocomplete, scoring changes, speculative engine states, gamification, global widgets, MapView activation, premature mobile Coach FAB/bottom sheet, forced Arabic/RTL implementation without scope approval, and any stale CSS claims disproved by the final cascade.

L. Validation Plan

Create a testable validation table:

| Validation ID | Decision under test | Method | Measure | Success criteria | Result that would change the recommendation | Owner |
|---|---|---|---|---|---|---|

Include source tests, visual tests, keyboard tests, screen-reader tests, contrast tests, device tests, and product/content decisions where applicable.

M. Implementation Handoff

Provide an ordered execution plan:

1. P0 trust, safety, and evidence-integrity fixes.
2. P1 accessibility and core interaction-state fixes.
3. P1 responsive and Terminal hierarchy fixes.
4. P2 design-system and resilience cleanup.
5. Final regression and accessibility validation.

Define regression gates for valid commands, scoring, local persistence, route map, context handoffs, chart/table equivalence, and reduced-motion behavior.

N. Open Questions, Assumptions, and Evidence Gaps

List every unresolved question that could change a recommendation. Separate:

- Product-owner decisions.
- Content/curriculum decisions.
- Engine/state decisions.
- Runtime/device validation.
- Deployment/configuration validation.
- Audit disagreements that remain unresolved.

Do not hide assumptions inside recommendations.

O. Final Recommendation

End with four short subsections:

Implement now

Preserve

Defer

Reject

Then provide a final one-paragraph decision stating whether AeroBridge should be preserved and refined, revised more substantially, or redesigned, and why.

---

7. Specific evidence-integrity checks

Regardless of what the five audits say, explicitly investigate the following classes of defects if the underlying evidence is supplied:

- Empty or whitespace input creating a real command, history event, score, toast, or persisted evidence.
- First-use error states that appear before the user causes an error.
- Seeded, hard-coded, illustrative, local, calculated, historical, and authoritative values shown with indistinguishable visual authority.
- Counts and denominators that do not reconcile with source arrays or visible records.
- Controls that show success or completion without performing the claimed action.
- Language controls that claim translation or direction changes without implementing them.
- Readiness or qualification language that exceeds the authority of a local heuristic.
- Assessment mode inheriting history, hints, or score state without a clear contract.
- Context handoffs that pass unstable titles instead of stable identifiers or evidence lineage.
- State labels, error taxonomies, or progress visuals that do not correspond to real triggers or data.

For each confirmed issue, specify the smallest safe fix and the regression guard.

---

8. Rules against weak or speculative recommendations

Do not:

- Treat consensus as proof.
- Treat a screenshot as proof of hidden runtime behavior.
- Treat CSS declarations as proof of final computed behavior without cascade analysis.
- Treat source presence as proof that a feature should be activated.
- Treat a missing screenshot as proof of a responsive failure.
- Treat visual premium-ness as evidence of production readiness.
- Add product features to compensate for an unverified UX concern.
- Change engine semantics to solve a presentation problem.
- Change scoring or persistence without explicit engine/product authority.
- Recommend a new interaction pattern without identifying the evidence that requires it.
- Use “must” when the correct classification is “validate.”

When a recommendation is uncertain, state what evidence would change your mind.

---

9. Required final quality gate

Before submitting, verify that your Master Audit:

- Uses all five Unified Audits but does not mechanically merge them.
- Separates source evidence, screenshot evidence, cross-audit evidence, and interpretation.
- Explicitly resolves material conflicts.
- Identifies false, stale, redundant, or speculative claims.
- Preserves the original product intent and learning model.
- Does not invent engine truth.
- Covers UX/UI, learning UX, state, interaction, accessibility, responsive behavior, and design system.
- Provides prioritized, implementation-ready changes.
- Includes acceptance criteria and validation methods.
- Separates confirmed decisions from NEEDS VALIDATION.
- Defines regression gates for existing valid behavior.
- Does not judge findings by audit length.
- Ends with Implement now / Preserve / Defer / Reject.
- Confirms that the same five-file evidence corpus was used for this analysis.
- Confirms that no missing, truncated, substituted, or mismatched Stage 3 audit was silently used.

---

10. Input files and corpus integrity

The following five attached files are the complete Stage 3 input set and constitute the entire evidence corpus for Stage 4.

No other audit, model output, external assumption, prior conversation result, or outside analysis may be treated as part of the evidence corpus unless it is explicitly identified and supplied as part of these five Stage 3 files or as an explicitly authorized evidence source.

All five files must be supplied in full, unaltered, and identically to Claude, Manus, and ChatGPT. Do not omit sections, truncate files, substitute excerpts, change file contents between runs, or provide different versions of the evidence corpus to different models.

Each model must receive the same five Stage 3 Unified Audits and the same Stage 4 prompt.

The five files are the five Stage 3 Unified Audit attachments accompanying this prompt. Use the exact filenames shown by the attachment interface and preserve the attachment order identically across Claude, Manus, and ChatGPT. Do not invent, substitute, or rename any attachment.

The attachment filenames, ordering, and file contents must be identical across all three runs.

Corpus integrity check

Before analysis, perform a corpus integrity check covering:

- Exact filename of each file.
- Whether each file was received in full.
- Approximate line count or file size where available.
- Whether each file appears to be a Stage 3 Unified Audit rather than a prompt, draft, unrelated file, or duplicate.
- Any apparent truncation, corruption, missing section, or duplicate content.
- Whether the five files appear to constitute the intended complete Stage 3 corpus.

Treat this check as an internal precondition to analysis. Do not include routine corpus-check details in the final Master Audit. Report them only if a corpus integrity problem is found or if the integrity of the evidence materially affects the analysis.

Where technically available outside the prompt, the orchestrator may additionally provide a manifest containing exact filenames and SHA-256 hashes to verify that Claude, Manus, and ChatGPT received byte-identical files. Such a manifest is a corpus-integrity safeguard, not an additional audit source.

Do not treat line-ending differences, attachment rendering differences, parser/display differences, or unavailable byte-level metadata as evidence that files differ. Treat a file as mismatched only when its content, sections, identity, or substantive text differs.

Before beginning analysis, verify that all five files are actually present and readable in full.

If one or more files are missing, incomplete, corrupted, inaccessible, materially truncated, or different from the expected Stage 3 corpus, do not begin the Master Audit.

Corpus Integrity Failure Exception

If the corpus integrity check fails, do not produce the Master Audit.

Produce only a concise Corpus Integrity Failure Notice identifying:

- The affected file(s).
- The specific integrity problem.
- Whether the file is missing, unreadable, truncated, corrupted, duplicated, or mismatched.
- Why a valid Master Audit cannot be produced from the incomplete or altered corpus.

Do not reconstruct, infer, replace, or fabricate missing sections from the other four audits.

---

Final instruction

Produce only the complete Master Audit in the required structure.

Exception: If the corpus integrity check fails, follow the Corpus Integrity Failure Exception above instead and do not produce a Master Audit.

Do not discuss your model identity, do not rank yourself against the other models, and do not describe this prompt. Your output will be compared with two other independent Master Audits and later supplied to Claude for Stage 5 Final Synthesis.

The quality standard is not maximum volume. The quality standard is maximum defensibility, accuracy, evidence discipline, decision clarity, and implementation usefulness.
