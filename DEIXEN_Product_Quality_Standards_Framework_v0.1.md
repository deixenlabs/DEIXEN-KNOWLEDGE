# DEIXEN — Product Quality Standards Framework

**Version:** 0.1 — 7 November 2026  
**Status:** PROPOSED FRAMEWORK — NOT CANONICAL  
**Prepared for:** Owner review  
**Purpose:** Establish where DEIXEN's quality standards live, how they are developed, how evidence supports them, and how AI tools and human contributors must apply them.

---

## 1. Why DEIXEN needs a standards system

DEIXEN's quality cannot depend on whether the current AI tool happens to remember a preference, interpret an old chat correctly, or independently invent a good method. Important expectations must be explicit, findable, and connected to the work they govern.

The aim is not to create a checklist for every tiny action. It is to make sure that consequential and recurring parts of the product are judged consistently, with clear ownership and evidence.

A standard should exist when at least one of these is true:

- An error could teach a learner incorrect operational behavior or create a misleading competence claim.
- The same kind of work will be produced repeatedly by different people, tools, or sessions.
- Quality depends on a body of evidence, specialist judgment, or a repeatable review method.
- Inconsistent execution would damage learner understanding, professional realism, safety, trust, or the product's long-term coherence.

A one-off task may need clear acceptance criteria, but it does not automatically need a permanent standard.

## 2. The document structure: each source has one job

The standards library supplements the current DEIXEN knowledge system; it does not replace it.

| Source | Its job | It must not become |
|---|---|---|
| `07_DEIXEN_Canonical_Decisions_and_Current_State.md` | The formal record of owner decisions and current project state | A place for AI tools to create decisions by implication |
| `DEIXEN_Operating_Constitution.md` | Governs how project work, authority, evidence, sources, and changes are handled | A curriculum, Amadeus manual, or product-quality catalogue |
| `08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process.md` | Governs how AI tools work: roles, authority, evidence discipline, collaboration, review, and technical process | The full content of every specialist quality standard |
| `DEIXEN_Amadeus_Verified_Reference.md` + D12/D15 | The approved source for real Amadeus Cryptic facts and their verification status | A generic customer-service or learning-science reference |
| Canonical product, curriculum, UX, design, and engineering documents | Own the domain-specific decisions and contracts assigned to them | A competing standards registry that silently overrides other owners |
| `/standards/` | Holds cross-project quality standards, their status, evidence, owners, and reusable review methods | A second decision log or a source that can overrule canonical decisions |
| A task brief, case package, or build specification | States the acceptance criteria for that specific task or bounded release | A permanent project-wide standard unless deliberately adopted as one |

**The key distinction:** file 08 tells an AI *how to work responsibly*. A specialist standard tells the contributor *what quality means in a particular kind of work and how to evaluate it*. The domain's canonical reference still owns the facts.

## 3. Rules for authority and status

Every standard must make its status visible at the top. A polished document is not automatically approved.

Use the status terms in `standards/README.md`. In particular:

- **Approved** means the proper authority accepted it.
- **Adopted for scope** means it applies to a named and limited scope, not automatically to all future content.
- **Proposed** means it is a candidate, not a binding rule.
- **Research required**, **Practitioner validation required**, and **Empirical validation required** identify different evidence gaps; do not merge them into a generic "needs review" label.
- **Hold** means the reviewer cannot responsibly decide because necessary evidence is missing. It must never be silently treated as Pass or Fail.

No proposed standard in this package changes a decision in file 07, the Operating Constitution, file 08, the Verified Reference, or the canonical product architecture. Any material conflict must be surfaced and routed through the existing change-control process.

## 4. Evidence standards: use the right kind of proof for the claim

Not all questions can be answered by the same source.

| What we are trying to establish | Evidence that can support it | What does not establish it by itself |
|---|---|---|
| Exact Amadeus Cryptic syntax, behavior, prerequisite, response, display, or error | D12-approved verification and a corresponding entry in the current Verified Reference | AI memory, another GDS, simulator code, an unverified blog, or a plausible workflow |
| What DEIXEN's current application actually does | Current code inspection, automated tests, and observed runtime behavior appropriate to the claim | A plan, screenshot, old test result, or code that was not inspected in the current version |
| Whether a professional workflow is realistic | Relevant practitioner input, current industry guidance, official operational material where available, and corroboration | A single AI-generated scenario or one person's unqualified opinion |
| Whether a learning method is supported by research | Suitable research, especially systematic reviews/meta-analyses and high-quality primary studies, interpreted in context | A citation name without reading/applicability checks, a popular blog, or a claim that "science proves" a design |
| Whether DEIXEN actually improves learning | DEIXEN-specific learner evaluation and appropriate outcome evidence | General learning science, a well-written lesson, user satisfaction, or successful completion in a simulator |
| Whether learners are independently competent or workplace-ready | Evidence meeting the applicable assessment and professional-validation requirements | Lesson completion, assisted practice, one correct final state, a score, or an AI judgment |

### 4.1 Required source record

For material external claims, record enough information for another reviewer to inspect the evidence:

- The exact claim being supported.
- Source title, organization/author, publication date, and URL or repository location.
- Source type: official/primary, peer-reviewed study, systematic review/meta-analysis, professional/industry guidance, practitioner testimony, learner observation, or implementation test.
- The relevant passage or finding, not just the source's general topic.
- Why the source applies to the DEIXEN question and where it may not apply.
- Limitations, conflicts, freshness concerns, and the confidence/status assigned to the claim.

Do not treat multiple pages repeating the same original source as independent corroboration. For domain-sensitive claims, establish that the source concerns the exact system, interface, market, and task being discussed.

### 4.2 Evidence does not transfer automatically between domains

A practitioner can challenge the realism of a booking task, but does not thereby establish undocumented Amadeus syntax. An Amadeus manual can establish a command behavior, but does not prove that a particular customer conversation is professionally appropriate. Learning research can inform instructional design, but does not demonstrate that DEIXEN's current design works for its learners.

Keep each claim within the boundaries of the evidence that supports it.

## 5. Initial owner requirements to preserve while standards are developed

The requirements below express the quality direction the owner has stated. They are **initial owner requirements for framework development**, not a claim that every detailed rule has already been researched, approved, or tested.

### 5.1 Amadeus factual accuracy and transparent uncertainty

1. Every Amadeus command, syntax pattern, response, display, message, prerequisite, status, and behavior taught or simulated must be traceable to the current Verified Reference and the verification status that covers the exact claim.
2. A `V-ID` must cover the actual wording and level of detail. Do not extend a verified general statement into an unverified absolute rule.
3. Anything not verified remains explicitly unresolved (`U`, `Hold`, or the exact status defined by the owning reference). Never complete a knowledge gap from model memory or intuition.
4. Clearly distinguish real Amadeus output from DEIXEN-authored teaching text. A fictional or constructed example must never be presented as an official Amadeus response.
5. If the reference changes, re-check affected lessons, cases, simulator behavior, and tests. Do not silently preserve stale claims.
6. If the simulator behaves differently from the verified domain reference, record the discrepancy and route it to the right owner. Do not redefine Amadeus truth to match the code.

**Authority remains:** D12/D15 and `DEIXEN_Amadeus_Verified_Reference.md`. This framework does not create a second Amadeus verification process.

### 5.2 True-beginner clarity

The intended beginner cannot be assumed to know Amadeus, GDS concepts, command syntax, cryptic abbreviations, status codes, or aviation-industry terminology merely because they have enrolled in a course.

A lesson intended for a first encounter should:

- Explain what the learner is looking at and what the action is for, in plain language.
- Introduce each essential unfamiliar term before relying on it. Do not define one unknown term using another unknown term.
- Explain a new command in a way that makes its purpose and place in the task understandable, not just provide a string to copy.
- Show the learner what matters in a relevant example and how to interpret the result when interpretation is part of the objective.
- Avoid dumping a glossary, explaining every advanced detail too early, or making the learner memorize terminology before it is useful.
- Use language suitable for an adult beginner: direct, respectful, clear, and not childish or patronizing.

The exact baseline of what a DEIXEN beginner may be assumed to know must remain governed by the adopted lesson criteria and owner-approved curriculum definitions. Do not silently convert an older report's temporary baseline into a canonical assumption.

### 5.3 Explanation that develops with the learner

The owner wants DEIXEN to recognize that the learner develops. The product should not explain every familiar command from the beginning on every later encounter, nor should it abruptly abandon a learner who still needs help.

The intended direction is:

- On a learner's first meaningful encounter with a command, concept, or important output, provide a clear, plain-language explanation appropriate to a beginner.
- As the learner demonstrates understanding, reduce unnecessary repetition. The learner can increasingly work with the established term, a concise reminder, or the command name without receiving the full introductory explanation each time.
- Do not equate "lesson completed" or "seen before" with understanding. The decision to reduce explanation should rely on the evidence and progression rules that DEIXEN adopts.
- When the learner struggles, makes a meaningful error, meets a new variation, or applies the concept in a new context, make the fuller explanation or targeted support available again where the learning mode permits it.
- Support must be context-aware and must never leak answers or instructional help into an independent assessment.

This is a **proposed product requirement**, not an approved adaptation algorithm. How understanding is recognized, when support fades, when it returns, and how this affects evidence must be researched and specified without contradicting F-07, D97, or the existing Coach/assessment contracts.

### 5.4 Curriculum continuity and meaningful connections

DEIXEN lessons are parts of one connected learning program, not unrelated articles or command cards.

The desired standard direction is:

- The curriculum has a deliberate sequence. Prerequisites and dependencies are visible to the curriculum owner and reflected in the learner experience where useful.
- Each lesson builds on relevant prior learning and prepares the learner for a meaningful next step.
- A lesson makes necessary handoffs explicit: what has just been learned, where it will be used, and what later lesson or practice will build on it.
- Previously learned knowledge is revisited at useful points, rather than either disappearing after one lesson or being needlessly re-taught in full every time.
- The curriculum connects lessons to realistic work tasks and practice, while preserving the distinction between learning content, demonstration, supported practice, scenarios, independent assessment, and evidence.
- Do not force every lesson into the same format merely to create a sense of consistency. Coherence comes from meaningful dependencies and progression, not a repeated template.

Ownership is split deliberately: the curriculum map owns course-level order, prerequisites, coverage, and cross-lesson revisits; a lesson owns its own explanation, examples, and local handoff; practice/assessment own their separate support and evidence rules.

### 5.5 Evidence-informed learning experience

Learning experience decisions should be informed by credible research into how people acquire, retain, retrieve, apply, and transfer knowledge and skills. The chosen evidence must fit the actual task and learner population.

For each consequential learning-design choice:

1. State the learning problem or learner failure mode being addressed.
2. Identify the relevant evidence and its strength, context, and limitations.
3. Explain the design implication for DEIXEN; do not copy a research technique just because it is popular.
4. Identify possible trade-offs, including cognitive load, time, motivation, accessibility, and the danger of revealing answers.
5. Define how the design will be evaluated with actual DEIXEN learners and what observation would count against the hypothesis.
6. Keep immediate practice success separate from retention, transfer, independent performance, and workplace readiness.

A research-supported design is a justified design hypothesis. It is not proof that DEIXEN achieves the outcome. The product's effectiveness requires appropriate learner validation and outcome evidence.

### 5.6 Customer interaction and professional service

The customer experience in DEIXEN should be credible for the travel/reservations context, not generic customer-service dialogue added for decoration.

Before a detailed customer-service standard is approved, it should draw on:

- Relevant professional and academic literature on service communication, needs clarification, expectation-setting, confirmation, complaint/recovery, and customer interaction.
- Current, credible travel-agency, airline, reservations, and ticketing guidance where accessible.
- Practitioner review from people with direct experience in reservation/ticketing/customer-service work, preferably including the markets DEIXEN intends to serve over time.
- Learner testing to see whether the interaction is understandable and supports the intended professional task.

The following boundaries should be preserved during that work:

- The customer supplies needs, facts, preferences, missing information, objections, and reactions; the Coach teaches; the Amadeus system returns operational output. These are different sources and roles.
- Asking a customer a necessary question is part of the professional task, not instructional help.
- A customer reaction or satisfaction outcome is not the same as operational correctness or professional judgment. A customer may be dissatisfied for reasons outside the learner's control; a satisfied customer does not make an incorrect booking correct.
- Do not use real customer personal data or confidential employer procedures in training cases.

No final, detailed customer-service behavior rubric is declared by this framework. CP-001 and the prepared practitioner review are an initial validation exercise, not the final standard.

## 6. Domain standards: current scope and next work

The authoritative status and owner for each domain are listed in `standards/README.md`. The first domains to mature are:

1. Amadeus domain accuracy — already governed by D12/D15 and the Verified Reference; maintain rather than duplicate.
2. Lesson content quality — preserve D95/D96. Recover the exact v1.5 standard before revising or extending it.
3. Curriculum continuity and adaptive explanation — define a cross-lesson standard and learning-state policy, informed by research and learner evaluation.
4. Learning practice and assessment — evaluate methods against relevant learning research while preserving F-07/D97 and existing evidence contracts.
5. Customer interaction/service — combine travel-specific literature, practitioner feedback, and learner evaluation.
6. Professional work-task realism — validate representative tasks against practitioners, industry evidence, and the target markets.
7. UX/UI/product design — continue to use the dedicated product/design documents and current owner-approved direction.
8. Evidence and readiness claims — preserve the canonical evidence model and avoid overclaiming what simulation evidence means.
9. Arabic/English, localization, RTL/LTR, and accessibility — keep content quality separate from rendering/technical checks, but review both.
10. Technical implementation and verification — use file 08, `CLAUDE.md`, specifications, tests, and observed runtime behavior.

## 7. How a specialist standard should be created

A permanent standard should pass through a deliberate sequence:

1. **Name the failure mode.** What bad or inconsistent outcome would the standard prevent?
2. **Define its scope.** Which activities, users, markets, lesson types, or product modes are covered? What is explicitly excluded?
3. **Identify the owning authority.** Which existing canonical document, role, specialist, or owner decision has authority over the subject?
4. **Gather appropriate evidence.** Use the evidence type that can actually answer the question. Record disagreement and missing evidence.
5. **Separate requirement from rationale.** State the rule clearly; explain why it exists and what evidence supports it.
6. **Write testable criteria.** Prefer observable indicators and explicit examples over vague goals such as "high quality" or "professional feel".
7. **Check interactions.** Confirm that the proposed standard does not contradict neighboring standards, product decisions, or evidence boundaries.
8. **Review representative examples.** Apply it to more than one appropriate case where feasible; record where it fails or is too rigid.
9. **Validate outcomes.** Use practitioners, learners, implementation tests, or other evidence as appropriate to the domain.
10. **Approve and synchronize.** Record formal approval where required, update indexes and affected documents, and preserve version history.

### 7.1 Requirement language

Use consistent words:

- **MUST** — required for acceptance; a documented exception needs explicit justification and approval from the relevant owner.
- **SHOULD** — normally expected; a departure is allowed when the reason is recorded.
- **MAY** — permitted option, not a requirement.
- **MUST NOT** — prohibited.

Do not use these words casually. A research suggestion or an unvalidated proposal is not a MUST.

### 7.2 Review outcomes

Where appropriate, use `Pass`, `Fail`, `Revise`, `N/A` (with a reason), and `Hold` (evidence unavailable). A standard may define more precise states for its own review. No average score should conceal failure of a critical gate.

## 8. How AI tools and contributors should consume this library

For any material task, an AI tool or contributor should:

1. Identify the current repository/source and relevant project state before making claims about what is current.
2. Identify the standards that actually apply to the task and open the owning source, not merely this index.
3. Check each source's status, scope, and version. A draft is not a binding rule; a scoped standard must not be generalized.
4. Separate domain facts, implementation facts, research findings, practitioner observations, product decisions, and personal recommendations.
5. Cite or identify the evidence for material claims and state what remains unverified.
6. If no relevant standard exists, propose task-specific acceptance criteria and label any proposed lasting rule as a proposal. Do not quietly invent policy.
7. Surface contradictions and missing evidence rather than silently selecting the easiest interpretation.
8. Avoid duplicating a standard into file 08 or unrelated files. Link to its owner.
9. State what was actually inspected, researched, tested, or observed. Never imply work was done when it was not.
10. Stop at the authorized scope. A standard does not authorize code changes, publishing, merging, deployment, or changes to owner-reserved decisions.

## 9. Reusable standard structure

Every specialist standard should contain at least:

- Title, identifier, version, owner, status, approval authority, and date.
- Purpose and the failure mode it is designed to prevent.
- Scope, exclusions, intended users, and relevant product modes.
- Relationship to canonical decisions and other domain documents.
- Requirements expressed as MUST / SHOULD / MAY / MUST NOT.
- Rationale and evidence for each consequential requirement.
- Examples and counterexamples where they improve interpretation.
- Review method, acceptance criteria, and required evidence.
- Known limitations, conflicts, open questions, and exception process.
- Change history and supersession record.

Use `DEIXEN_Standard_Template.md` as the starting point, not as a forced format for every document.

## 10. Known gaps and explicit stop conditions (7 November 2026)

- The exact file `DEIXEN_Lesson_Rewrite_Preparation_Criteria_Standards_v1.5_reviewed.md`, named by D95/D96, is not present in the recursive tree of `DEIXEN-KNOWLEDGE/main` inspected at commit `1d2cd93a73951df48fd4e345f69e2b24bd6d4776`. Recover the exact adopted file before reproducing or changing its 13 criteria. The older v1.0 preparation report is not a substitute.
- The current Amadeus Verified Reference inspected in `main` is third edition with V-01–V-18 and U-01–U-16. CP-001 has unresolved items including U-12/U-14; its content remains on hold wherever those items matter.
- The CP-001 practitioner review is pending. One response can reveal important problems but cannot validate every job market or every travel-agency practice.
- The learning-science and travel-specific customer-service literature review has not been carried out as part of this framework package.
- The proposed adaptive-explanation requirement has not been translated into a validated learner-state model or tested with learners.
- This framework does not approve a new curriculum, new lesson rubric, customer-service feature, assessment rule, evidence schema, or implementation.
- The Claude product-development report is pending. Review that report before turning any proposed architecture or quality standard into a formal implementation roadmap.

## 11. Immediate next step

Pause new product expansion and detailed standards authoring until the pending inputs arrive:

1. Read and independently assess Claude's product-development report against current DEIXEN sources and work completed since Claude's last context.
2. Review the Amadeus-experienced practitioner's response to CP-001.
3. Reconcile both inputs with the current canonical decisions and Verified Reference.
4. Only then decide which specialist standards should be researched, revised, formally adopted, or left open.

**Current verdict:** the proposed standards-library structure is suitable as a starting point. Its domain requirements are intentionally mixed in status: some already have canonical authority, some are owner-stated design intentions, and several require research or validation before they can become binding standards.
