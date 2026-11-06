# DEIXEN — Standards Library

**Package:** Standards Library  
**Version:** 0.1 — 7 November 2026  
**Status:** Proposed organization and register — not yet canonical  
**Owner:** Karim  
**Repository location proposed:** `/standards/`

## Purpose

This folder is the home for cross-project quality standards that need to be understood and applied consistently by people and AI tools working on DEIXEN.

It is not a second decision log, not a replacement for the Amadeus Verified Reference, and not permission to implement a feature. A standard defines how a class of work should be judged; the relevant canonical source still owns the actual product decision or domain truth.

## Start here

1. [`DEIXEN_Product_Quality_Standards_Framework_v0.1.md`](DEIXEN_Product_Quality_Standards_Framework_v0.1.md) — the framework, principles, evidence rules, standard lifecycle, domain register, and initial owner requirements.
2. [`DEIXEN_AI_Standards_Application_Addendum_Proposal.md`](DEIXEN_AI_Standards_Application_Addendum_Proposal.md) — proposed wording to connect AI Working Rules (file 08) to this library. It is a proposal only and does not become operative until accepted and synchronized through governance.
3. [`DEIXEN_Standard_Template.md`](DEIXEN_Standard_Template.md) — reusable structure for future specialist standards.

## Standards register

| Domain | Current authority / reference | Current status in this library | What an AI or contributor must do now |
|---|---|---|---|
| Amadeus commands, responses, displays, prerequisites, and behavior | D12/D15; `DEIXEN_Amadeus_Verified_Reference.md` | **Existing canonical domain authority**; no duplicate standard is created here | Use only applicable `V-IDs` as Amadeus truth. Preserve `U-IDs` as unresolved. Never invent syntax, messages, outputs, prerequisites, or recovery behavior. |
| Lesson content authoring | D95 and D96; the adopted v1.5 criteria file is named in D95/D96 | **Adopted for F-08 scope**; the exact v1.5 criteria file is not present in the current `main` tree inspected on 7 Nov 2026 | Respect D95/D96. Recover the exact adopted v1.5 document before reproducing, revising, or extending its 13 criteria. Do not substitute the older v1.0 preparation report. |
| Curriculum continuity and learner progression | D06 canonical Curriculum & Coach; 02 UX; canonical product architecture | Existing principles plus **owner requirements proposed for further definition** | Design lessons as a connected curriculum with prerequisites, progression, meaningful handoffs, and planned revisits. The curriculum map owns course-level sequencing; an individual lesson owns its local explanation and handoff. |
| Adaptive explanation and fading support | 02 UX; D06 Coach contract; F-07/D97 boundaries | **Proposed owner requirement; needs research and learner validation** | Explain a concept or command clearly when it is new to the learner. Reduce repetition only when understanding is supported by evidence; do not infer understanding from lesson count or elapsed time. Re-explain when the concept is new, misunderstood, or needed in a changed context. Never leak instructional help into independent assessment. |
| Learning science, practice, retention, and transfer | 02 UX; D06; F-07 and D97; learning research | **Research and validation required** | Use suitable scientific evidence to inform design choices. Report source quality, context, applicability, and limits. Research does not prove DEIXEN itself is effective; learner outcomes require DEIXEN-specific evaluation. |
| Customer interaction and service behavior | Customer Service curriculum direction in D06; 02 UX; case-specific practitioner review | **Proposed; practitioner and literature review required** | Combine field-specific research with practitioner review. Keep customer dialogue separate from Coach guidance and operational output. Do not mistake customer satisfaction/reaction for proof of operational correctness. |
| Professional task realism and workplace practice | CP-001 (files 09/10); 02 UX; strategic product direction | **Case-specific candidate; not yet validated for production** | Validate task flow, customer facts, decisions, controls, recovery, close-out, and local market relevance with practitioners and reliable sources. One practitioner's response is input, not universal proof. |
| Assessment, evidence, independence, and readiness claims | F-07, D97, 07 decisions, canonical product architecture | **Existing canonical rules** | Preserve support/independence boundaries. A completed attempt, a correct final state, or a successful simulation alone must not be overstated as independent competence or workplace readiness. |
| UX, UI, product design, and brand | 02, 03, 04, 05, 06, canonical decisions | **Owned in specialist product/design documents; visual identity remains open per latest owner direction** | Apply the current owner-approved direction and relevant design specifications. Do not promote a proposal, mockup, or reference into an approved visual rule. |
| Arabic/English quality, localization, RTL/LTR, and accessibility | D11 and relevant canonical design/product specifications | **Existing requirements; detailed checks belong to owning specs** | Preserve meaning and operational accuracy across languages. Review natural language and mixed-direction text; validate rendered behavior in the product instead of assuming translated text proves RTL correctness. |
| Software implementation and technical verification | File 08 §26; `CLAUDE.md`; relevant build specifications and tests | **Existing process authority** | Inspect current code and test actual behavior when claiming implementation truth. Code behavior does not establish real-world domain truth. |

## Status meanings

- **Canonical / approved:** authority is explicitly approved and recorded through the project's governing process.
- **Adopted for a named scope:** a decision applies to a bounded body of work; do not silently generalize it to every future domain or lesson.
- **Existing principles:** an owning canonical document already contains the rule; this library points to it rather than copying it.
- **Proposed:** a candidate that still requires owner review or formal decision.
- **Research required:** reliable sources and their applicability have not yet been adequately examined.
- **Practitioner validation required:** professional reality must be checked with people who have direct, relevant experience.
- **Empirical validation required:** the effect must be tested with actual learners or users.
- **Not established / Hold:** evidence is missing or insufficient. This is neither approval nor proof of failure.
- **Superseded:** retained for history only; never used as current authority.

## Important reading rule

A file being present in this folder does not automatically make it canonical. Always inspect its status, scope, version, and authority before applying it. When two documents disagree, use the project's governing decisions and the domain's approved source; surface the conflict instead of silently reconciling it.

## Change control

A new specialist standard should be added only when it governs recurring, consequential, cross-task quality or prevents a clearly identified failure. A one-off task can have acceptance criteria without needing a permanent standard.

When a standard is accepted and materially changes a project rule, record the required owner decision and synchronize the appropriate canonical files. Do not treat this proposed library as having amended file 07, the Operating Constitution, file 08, or any domain authority.
