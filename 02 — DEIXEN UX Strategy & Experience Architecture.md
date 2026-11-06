---
document: DEIXEN UX Strategy & Experience Architecture
version: 0.4
prepared: 2026-11-07
status: Working strategy aligned to Unified Experience & Runtime Architecture v0.3, First Integrated Professional Task Map v0.1, and Case Package CP-001 v0.1
authority: Companion UX strategy; detailed flows and layouts remain open
---

# DEIXEN — UX Strategy & Experience Architecture

## Status and purpose

This document defines the experience principles and relationships between DEIXEN's five product areas and its shared capabilities. It is aligned with `06 — DEIXEN Unified Experience & Runtime Architecture.md`.

The architecture proposal describes who owns each kind of information and activity. This UX document describes how the learner should understand and move through those activities. Neither document approves a final screen layout or authorizes implementation.

The goal is to help learners focus on meaningful professional decisions rather than interface confusion, without removing the ambiguity, judgment, responsibility, and recovery that belong to real work.

## 1. Core UX principles

1. **Task-first clarity:** the learner should understand what they are trying to accomplish, why it matters, and what the current task requires.
2. **One coherent journey, distinct responsibilities:** connect the learner's context across areas without forcing every activity onto one screen.
3. **Progressive complexity:** introduce knowledge, decisions, and task complexity in a sequence a beginner can build upon.
4. **Support that changes by mode:** explain first, guide during practice, reduce help as appropriate, and protect independent assessment from instructional assistance.
5. **Context before command:** whenever relevant, show why an operational action matters to the customer's request and professional task.
6. **Truthful feedback:** distinguish system acceptance, task completion, professional correctness, and qualifying evidence.
7. **Visible state, not hidden magic:** make the current task phase, relevant constraints, and available next actions understandable without exposing answers.
8. **Recovery matters:** teach learners to detect, diagnose, communicate, correct, pause, or escalate—not merely avoid mistakes.
9. **Separate sources of information:** customer dialogue, Coach, operational output, task context, and evidence must be visually and semantically distinguishable.
10. **Accessible and responsive:** support Arabic/English and relevant input methods; preserve Terminal's LTR operational behavior.

## 2. The five product areas

The current structure remains five areas. The first area is **Home / الرئيسية**; older references to Flight Deck are historical naming unless a specific implementation identifier is being discussed.

| Area | Learner question | UX responsibility | Boundary |
|---|---|---|---|
| **Home** | “Where am I, and what is the most useful next step?” | Orient the learner, explain a relevant recommendation, and show a concise view of the wider development journey. | Not a full catalogue, workbench, or detailed evidence report. |
| **Learning** | “What do I need to understand, and how does it apply to work?” | Support curriculum discovery and focused lessons, including demonstrations and links to practice. | Lesson completion is not competence evidence. |
| **Terminal** | “Can I perform this operational work correctly?” | Provide the operational work environment and the practice, scenario, and assessment modes that use it. | Not a customer chatbot or a place to mix Coach/customer content into the operational record. |
| **Scenario Bank** | “What professional situation should I practice or be assessed on?” | Organize and explain cases, purpose, prerequisites, variants, and relevant status/eligibility. | Not a second execution environment. Scenario execution remains in Terminal under D92. |
| **Growth** | “What does my evidence show, and what remains to develop?” | Present a clear evidence-based development view, including limits and untested capabilities. | Not a score, completion dashboard, or unsupported readiness claim. |

### Shared capabilities are not additional navigation areas

Coach, Ghost, Customer Interaction, Task Runtime, Assessment & Evidence, and verified-content controls support the five areas. They may appear in several experiences, but each must retain a distinct responsibility. Do not add a sixth top-level area merely to give one of these capabilities a home.

## 3. Three connected lifecycles

The experience connects three different lifecycles:

- **Customer Journey:** inquiry, discovery, clarification, advice, choice/consent, fulfillment, changes/problems, confirmation, closure, and after-sales.
- **Professional/Learner Journey:** onboarding, foundations, supported practice, growing responsibility, independent performance, and continued development.
- **Work Task Lifecycle:** the steps and outcome of one piece of work, from receiving the request through decisions, execution, validation, communication, and closure.

These lifecycles inform one another but must not be collapsed into one progress sequence. A learner can revisit Learning; a work task can branch or pause; and a customer journey can include multiple tasks.

## 4. The connected learner experience

A useful default path to design and validate is:

**Home → Learning → Ghost demonstration → Terminal practice → Scenario Bank case selection → Terminal scenario execution → Debrief → Independent assessment → Evidence → Growth → Home.**

This is a connected model, not a mandatory linear funnel. Learners may return to a lesson, repeat a demonstration, choose another practice case, or receive a different recommendation based on observed evidence.

### Home

Home should make the learner's current situation understandable. A recommendation should answer:

- What is the suggested next action?
- Why is it relevant now?
- Which learning objective, task, or evidence gap does it address?
- What is the next step after it?

Keep the wider professional journey visible as concise context, not a second dashboard competing with the next action.

### Learning

Learning has two connected experiences:

1. **Discovery:** paths/tracks, courses, modules, and lessons, with taxonomy and prerequisites validated by curriculum evidence.
2. **Focused lesson:** a clear objective, explanation, relevant example, demonstration, and a meaningful bridge into practice.

Customer Service remains a distinct but connected learning track. It teaches transferable communication and service behaviors that can later be observed in integrated scenarios; not every lesson must become a full customer simulation.

## 5. Ghost UX: a progressive narrated demonstration

Ghost should feel like a knowledgeable instructor guiding the learner through a live demonstration—not like a static command list or an ordinary prerecorded video.

The learner sees the command/entry and system response unfold progressively. At meaningful points, a separate Coach narration explains:

- what just happened;
- what changed in the operational state;
- why this step matters now;
- what field, response, or detail deserves attention;
- what the learner should carry into practice.

For beginners, explanation should generally come before a prediction request. Use occasional self-explanation or “what do you expect next?” prompts at consequential decision points, not as a continuous quiz.

Ghost uses the actual simulation engine for operational responses. Authored explanation must be grounded in verified references. Coach text and annotations remain outside the Terminal record. Ghost exposure is learning exposure, not independent evidence; preserve D97's cumulative behavior and no-state-injection rule.

Text narration is sufficient for the initial experience. Audio/voice is a separate future hypothesis.

## 6. Scenario Bank and Terminal UX relationship

Scenario Bank and Terminal must be designed together at the learner-experience level while remaining different places with different jobs.

### Scenario Bank: understand and select the case

The learner should be able to understand the work purpose, expected outcome, major constraints, prerequisites, intended practice/assessment role, and relevant case status before launch. The Bank should not expose hidden customer facts or assessment answers.

Work-domain sections may eventually organize cases by recognizable professional activity. Cross-cutting tags may identify recurring challenge patterns. For example, a “system accepted it, but it was wrong for the task” collection could be generated from tagged cases rather than maintained as duplicate copies. Final taxonomy and terminology require user/practitioner testing.

### Terminal: perform the case

Selecting a case hands its versioned context to Terminal's Scenario Mode. Terminal runs the case through the shared task runtime and operational engine; it does not reproduce Scenario Bank's library or case-authoring logic.

The task may move between customer interaction and operational activity. The learner should understand why they are switching and what information carries forward. The two channels must remain separate:

- customer dialogue is not Amadeus output;
- Coach is not the customer;
- scenario instructions are not operational responses;
- the operational record remains restricted to learner entries, Amadeus output, and the one allowed labelled DEIXEN training line.

Some scenarios may be dialogue-heavy or may not require a GDS command. Preserve D92 while testing how such cases can run in Terminal Scenario Mode without forcing irrelevant command-entry UI or inventing operational actions.

## 7. Customer Interaction and Coach

The virtual customer and Coach are separate roles.

**Customer Interaction** supplies case facts, reveals information when appropriately asked, expresses needs/preferences/concerns, responds to choices, and reacts plausibly to the learner's behavior. The customer is not an instructor and should not know every hidden system rule.

**Coach** provides explanations, hints, prompts, error diagnosis support, and learning feedback according to the current mode. A deterministic, bounded customer-dialogue model is the first prototype hypothesis; its natural-language coverage, authoring cost, and learner experience must be tested before commitment.

### Support policy by state

| Experience state | Coach/help behavior |
|---|---|
| Lesson | Teach and explain. |
| Ghost | Narrate and focus attention on meaningful changes. |
| Supported practice | Offer contextual help and corrective feedback as allowed. |
| Reduced-support practice | Encourage reasoning and self-checking; reveal less. |
| Scenario practice | Follow the case's declared support policy; never impersonate the customer. |
| Independent assessment | No instructional Coach, answer hints, or corrective rescue during the attempt. |
| Post-attempt review | Explain performance only after the attempt/evidence state is secured. |

Ordinary customer facts disclosed in response to the learner's questions are part of the task, not instructional help.

## 8. Assessment and evidence UX

Assessment should feel like a substantial professional task, not a small quiz detached from real work. Scenario Bank may organize eligible case families/variants; execution remains in Terminal in an isolated assessment mode.

The learner should understand that this is an independent attempt and what rules apply, without being shown answers. A qualifying attempt must be distinguishable from a completed-but-assisted attempt. The design must support D97's fresh session identity, clean operational state, distinct unpractised task/variant, absence of Ghost exposure in the assessment session, absence of instructional hints, and evidence captured within the same assessment chain.

If an attempt is completed but fails a qualification condition, record it honestly without calling it independent evidence. A correct final state alone is not proof.

Customer satisfaction, operational accuracy, professional judgment, communication, recovery, independence, and transfer remain distinct evidence dimensions. Satisfaction must neither excuse incorrect work nor automatically penalize the learner for a legitimate constraint.

## 9. Debrief and Growth

Debrief comes after the relevant attempt and explains the task outcome, important decisions, mismatches, errors, recovery, and evidence limitations. For independent assessment, debrief content appears only after the attempt is closed and the evidence snapshot is secured.

Growth should present:

- what has been demonstrated;
- on which task/case variants;
- under what support and independence conditions;
- whether errors were detected/recovered;
- what remains untested or needs practice;
- what the evidence does not yet justify claiming.

Do not turn the dimensions into a wall of badges or numeric sub-scores. Preserve the currently governed qualitative status vocabulary unless formally changed.

## 10. UX architecture: shared context, distinct surfaces

An integrated work task may coordinate objective, task phase, case facts, customer dialogue, Terminal activity, support, and checkpoints. It does **not** follow that all elements should be visible at once or placed in one fixed layout.

Test whether the learner benefits from simultaneous adjacent workspaces, progressive transitions, focused phases, or a hybrid. The best composition may differ between mobile and desktop. Avoid forcing one identical screen template across Learning, Ghost, Scenario Bank, Terminal, and Growth.

Terminal's operational record remains LTR and monospace. Customer dialogue, Coach, case context, and feedback stay outside it. Arabic/English and RTL/LTR support should not reverse the operational Terminal record.

## 11. Validation requirements

Use `08 — DEIXEN First Integrated Professional Task Map.md` as the current bounded architecture-test candidate. It begins with a pre-selected, customer-confirmed itinerary and deliberately excludes unverified availability search, fare comparison, ticketing, and payment. This makes it possible to test the dialogue-to-operation hand-off without overstating the current operational scope. The task is a prototype candidate, not a final market-priority decision.

Test representative complete tasks with beginners and, where possible, practitioners. Observe:

- whether learners understand the purpose and next step;
- whether customer facts and operational requirements are easy to distinguish;
- whether they can move between customer dialogue and Terminal without losing context;
- whether Coach helps without overloading or revealing answers;
- whether Ghost explanations clarify consequential outputs;
- whether the case's support level is understood;
- whether errors, pauses, recovery, and escalation are understandable;
- whether independent assessment remains visibly and functionally distinct;
- whether evidence wording is honest and understandable;
- whether the experience works with realistic content density on mobile and desktop.

Do not approve a flow only because a diagram or attractive static mockup looks coherent.

## 12. Open questions

- Is the bounded new-booking task in `08` sufficiently representative and valuable as the first integrated prototype across Saudi Arabia, Oman, and the UAE, or should practitioner/job-task research select a different first task?
- Which case fields are required for a useful first version, and which should remain internal authoring metadata?
- How should dialogue-heavy/customer-service-only cases appear in Terminal Scenario Mode?
- Which work domains deserve Scenario Bank sections, and which should remain filters/tags?
- How much Ghost narration is helpful before becoming overly verbose?
- How should learners see task phase and context without revealing hidden information?
- Which support actions disqualify an attempt from independent evidence?
- What is the smallest integrated experience that can validate learning, usability, and evidence integrity?

## 13. Governance boundaries

The bounded new-booking task in `08 — DEIXEN First Integrated Professional Task Map.md` is the current architecture-test candidate. It starts from a pre-selected, customer-confirmed itinerary so the first prototype does not assume unverified availability search, fare comparison, ticketing, or payment capability. Its detailed stage map is a working design artifact, not a confirmed market-priority decision.

This document does not authorize code changes, a sixth area, a final case taxonomy/schema, changes to D92/D97, new Amadeus behavior, a final screen layout, or a new evidence model. Detailed UX flows and UI specifications belong in `05 — UX Flows, UI Specifications & Design System — Planning.md` only after the task and its variants are researched and validated. The companion architecture proposal is a working model; any change to canonical governance must go through the formal decision process.

## 14. Applied case stress test: CP-001

`09 — DEIXEN Case Package Definition — New Reservation.md` applies the UX model to one bounded customer-to-reservation task. The case candidate requires the learner to receive a preselected synthetic itinerary, clarify passenger contact, confirm the request, execute a limited booking workflow in Terminal, verify the record, and explain that pricing is not ticket issuance.

UX implications:

- The customer request, customer replies, and customer disclosures must be visibly distinct from the Terminal operational record.
- The agency contact value and passenger contact value must be represented as different data objects; the learner must not mistake one for the other.
- The selected itinerary and confirmed request should remain available as task context without being inserted into the Amadeus transcript.
- The passenger mobile remains hidden until an appropriate question is asked and the case's disclosure rule is satisfied. Scenario Bank owns the disclosure rule; Customer Interaction applies it; Task Runtime records it.
- Coach may explain the reason for a question in supported practice but must not reveal the customer's hidden value. Independent assessment must not receive this instructional prompt.
- The final communication must distinguish a filed/priced reservation from a ticket that has actually been issued.
- The case's `RF` requester mismatch demonstrates why an operational result may need a separate task-correctness check. The UX must communicate the professional/task mismatch without falsifying or relabelling the engine's accepted response.

The case is a working architecture-test candidate, not a validated UX flow. The exact mobile-collection wording, customer-consent framing, and work-practice expectations require a practitioner review. Operational content release also remains blocked by Verified Reference U-12 and U-14; see CP-001.
