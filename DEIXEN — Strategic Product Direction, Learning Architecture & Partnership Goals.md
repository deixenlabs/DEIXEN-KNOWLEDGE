# DEIXEN — Strategic Product Direction, Learning Architecture & Partnership Goals

**Prepared for:** Any AI model, agent, or review tool (vendor-neutral)  
**Prepared:** 6 November 2026  
**Purpose:** Vendor-neutral master context brief for independent, critical, evidence-led audits by multiple AI models, agents, and tools. Use it alongside Claude/Gemini reports when available, but do not defer independent analysis to any single model.  
**Status:** Strategy and discussion record — **not an implementation authorization and not a set of newly approved architecture decisions.**

---

## 0. How any AI reviewer must use this document

This document consolidates the strategic direction, prior project context, governance constraints, ideas discussed across sessions, the older product-development consultation, Gemini's report, and the user's personal goals. It is intended to support independent reviews by multiple AI tools from different providers, reduce context loss, and prevent reviewers from treating an old decision as untouchable.

The reviewing AI tool is asked to:

1. **Critically evaluate, not agree by default.** Challenge every assumption, including ideas the user is enthusiastic about and decisions previously accepted in `07_DEIXEN_Canonical_Decisions_and_Current_State.md`.
2. **Inspect the current repositories and current `main` state before making claims about implementation.** Do not infer the current app from an old Build Spec, an old slice, an earlier report, or this brief. Identify exact commit SHAs, files, code paths, tests, and docs inspected.
3. **Use the pending Claude report and the Gemini report as inputs, not authorities.** Compare their claims against the current code, knowledge documents, verified Amadeus references, scientific evidence, market evidence, and the user's goals.
4. **Separate five categories explicitly:**
   - verified facts about the current product/repositories;
   - previously approved governance decisions;
   - strategic directions currently under consideration;
   - hypotheses needing research or user testing;
   - proposals that should be rejected or deferred, with reasons.
5. **Do not silently change or reinterpret project governance.** The user permits criticism of all entries in `07`, but any actual decision change must be explicit, evidence-backed, documented, and approved through the project's governance process.
6. **Do not implement or edit files during this review.** This is a read-only strategic and product-logic review unless the user separately authorizes work.
7. **Do not invent Amadeus behavior.** Distinguish verified real Amadeus behavior from DEIXEN-authored training behavior. Never invent commands, syntax, system responses, warnings, errors, prerequisites, state transitions, office-profile rules, or airline/business policies.
8. **Do not claim DEIXEN is superior, job-ready, certified, endorsed, or an Amadeus partner without appropriate evidence and authorization.** Identify what can be demonstrated now and what remains unproven.
9. **Explain complex findings in plain Egyptian Arabic for the user.** The reviewing tool may reason in English or produce technical details, but the user is not a developer and needs clear explanations, practical consequences, and a recommended next step.
10. If this brief is supplied to several tools, ask each to review independently first. Do not ask them to synthesize or agree before each has produced its own critique. Compare their disagreements explicitly afterwards.
11. End with a **decision-ready synthesis**: what should be preserved, what should be challenged, what evidence is missing, what should be researched/tested next, and what must not be implemented yet.

Claude's report is pending as of the preparation of this brief. When it arrives, compare it with Gemini's report and this document; do not treat any single model's report as authoritative.

---

# PROJECT CONTINUITY SNAPSHOT

## Known project context to verify before relying on it

- Repositories: `deixenlabs/DEIXEN-KNOWLEDGE` and `deixenlabs/deixen-app`.
- The prior governance record identifies Gemini 4 Argon as the DEIXEN Project Lead in Antigravity under Decision 93. Roles are task-based; do not assume Claude Code is the execution environment. Verify the current arrangement with the user/current project materials.
- The user has been working through Phase 6, with a consolidated execution mandate prepared for Gemini 4 Argon. The exact live execution status should be checked rather than assumed.
- D97 was recorded in the knowledge governance history and later merged to `main` in the prior project history. Verify the current main SHA and the present implementation before relying on any older commit or test count.
- A full product-reality / strategic reassessment is part of the user's current way of working: inspect the real repositories and evidence first, then plan. The user does not want broad shallow prompts or assumptions about what a model has inspected.
- The user is currently waiting for Claude's report on the learning-to-employment / product-development question. Gemini's report has already been shared in this conversation. The older consultation dated 24 October 2026 is also available and should be treated as a historical research input.

This snapshot is continuity context, not a claim that all listed execution details remain current. Every reviewing tool must verify status before making repository, implementation, or workflow claims.

---

# PART I — THE USER'S NON-NEGOTIABLE AMBITION AND PERSONAL GOALS

## 1. The primary ambition

The user's ambition is not merely to finish a software project or create another travel-training course. The goal is to build a highly credible, differentiated, evidence-based professional training and competency-development product for the travel and aviation operations sector.

The user does not want to settle for a product that is merely “good enough.” The ambition is to pursue the strongest product realistically possible in the market, challenge competitors, and continue researching and improving until DEIXEN's differentiation is supported by credible evidence.

The user explicitly does **not** want the team to defend current decisions merely because time was invested in them or because they were previously accepted. The contents of `07_DEIXEN_Canonical_Decisions_and_Current_State.md` are open to criticism whenever a decision materially limits product quality, learning effectiveness, UX, professional competence, or the ability to prove the product's goals.

This does **not** authorize silent changes. It means:

- every decision may be challenged;
- evidence and alternatives must be examined;
- if a better direction is proven, the relevant decision should be formally reconsidered;
- implementation and governance changes still require an explicit approval path.

## 2. Personal goal: become eligible to approach Amadeus

One of the user's most important personal goals is to develop DEIXEN into a mature, credible product and training operation that can approach **Amadeus** for an official partnership or suitable collaboration.

This goal must be remembered and considered in every major strategic discussion. The objective is not merely to submit an application; the objective is to make DEIXEN genuinely worthy of consideration.

The reviewing tool must distinguish:

- the ability to contact or apply to Amadeus;
- eligibility for a specific Amadeus program;
- acceptance into a program or partnership;
- a commercial partnership that creates value for both parties;
- investment by Amadeus, which is a different arrangement and may involve equity.

No acceptance is guaranteed. Current official requirements, eligibility, fees, and partnership models must be re-verified when the project is ready to act.

## 3. The user's intended organizational identity

The user's primary ambition is **not to become a software company whose main business is selling software licenses**.

The direction the user wants to explore is a **specialized professional training and vocational-development institution for travel, reservations, ticketing, and related service roles**, with DEIXEN as its proprietary training system and learning environment.

A possible future model:

- the institution is the primary operating/training organization;
- DEIXEN is the proprietary system, curriculum environment, simulation and evidence platform used by the institution;
- qualified trainers deliver or oversee training;
- learners complete structured programs and practical assessments;
- institutional/employer relationships provide workplace relevance and external validation;
- software licensing or third-party platform sales may be additional future models, but are not the user's core identity or primary goal.

Potential pathways discussed include:

- **Amadeus Learning Partners** as the closest educational/training route to investigate;
- working with an already licensed training center as an initial or lower-capital route, subject to legal confirmation;
- **Amadeus Partner Network** (e.g. Extend/Connect) only if a genuine technical/commercial complement exists;
- **Amadeus Ventures** as a separate potential investment route, not a training partnership and not guaranteed funding.

Any Egypt-specific licensing requirements, online-training permissions, trainer qualifications, center requirements, costs, and legal structure must be verified with current official authorities and Amadeus. Do not treat prior discussion of Egypt's training-center rules or fees as legal advice or as a completed compliance review.

---

# PART II — PRODUCT IDENTITY AND TARGET OUTCOME

## 4. What DEIXEN is trying to become

DEIXEN should be understood as a **Professional Work Competence and Training System for travel operations**, not a generic LMS, generic travel app, or generic SaaS dashboard.

The deeper target is to close the gap between:

- studying Amadeus commands or watching demonstrations;
- reaching a correct result in a guided or familiar simulator;
- independently performing complete work tasks under variable conditions;
- retaining and transferring the ability to new cases;
- performing responsibly in a real workplace.

The product's value should be demonstrated through what learners can actually do, not through the number of lessons, features, screens, sessions, badges, or time spent in the product.

## 5. Target learners and markets

The user's stated customer priority is:

1. trainees/beginners;
2. current employees seeking improvement;
3. companies and training organizations.

The primary target markets are Saudi Arabia, Oman, and the UAE. The curriculum and professional task model should be based on balanced, current evidence from those markets, not an overreliance on Saudi-only job advertisements or a few anecdotal examples.

The product should help a complete beginner progress toward independently verified reservation/ticketing and travel-operations work. The longer-term goal includes broader professional competency development, not merely command memorization.

## 6. The central learning/evidence principle

The project must preserve these distinctions:

- a valid command/action is not necessarily a qualifying action;
- a correct final PNR state is not by itself proof of competence;
- a completed lesson is not proof of competence;
- a guided or assisted task is not proof of independent competence;
- a correct result reached through hints, Ghost, or corrective coaching must not be misrepresented as independent performance;
- one successful attempt on one familiar case is not enough to claim reliable competence or transfer;
- simulator competence is not automatically equivalent to workplace readiness.

DEIXEN should describe evidence honestly: what the learner demonstrated, under what conditions, with what support, on what task variant, and when.

---

# PART III — CURRENT PRODUCT STRUCTURE AND GOVERNANCE CONTEXT

## 7. The five existing product areas

The current top-level product structure has exactly five areas:

1. **Flight Deck** — learner orientation and next-step direction based on the learner's state/evidence.
2. **Learning** — conceptual knowledge, command knowledge, worked examples, demonstrations, and structured instruction.
3. **Terminal** — the operational heart of the product, where the learner enters commands and sees Amadeus-like operational behavior as implemented and verified by DEIXEN.
4. **Scenario Bank** — a case library/status area, not a separate execution terminal.
5. **Growth** — evidence and competency development over time.

Do not create a sixth top-level area merely to accommodate a new idea. First examine whether it belongs within the current five areas. However, the five-area structure itself is not beyond criticism if strong evidence shows that it materially harms the product; any proposed change must be explicit and formally reviewed.

## 8. D92 — Scenario Bank and Scenario Mode

The established D92 distinction is:

- **Scenario Bank** is the separate page/library for cases and their status/details.
- **Scenario Mode** is a mode inside Terminal where a scenario is actually executed.

A new proposal should preserve this distinction unless a formal review demonstrates a better architecture.

The current strategic proposal is to make Scenario Bank much richer: a library of professional work scenarios rather than a list of raw command exercises. The execution of those cases still takes place through Scenario Mode in Terminal.

## 9. D97 — Cumulative Ghost Mode and isolated assessment

D97 accepted:

- native cumulative Ghost Mode;
- no state injection;
- Ghost scripts expose the commands according to F-07;
- independent workflow assessment is isolated from Ghost/demo contamination.

Any future assessment integration with Scenario Bank must preserve the substance of D97. The assessment case can be selected/organized as a Scenario Bank case, while execution occurs in a clean, isolated assessment run. The learner's previous assisted practice, Ghost exposure, hints, and corrective support must not be silently combined into independent assessment evidence.

The assessment must be evaluated against the actual implemented D97 conditions, not just the existence of a design document describing isolation.

## 10. Other product rules and constraints to verify in the current repo

The following are known project constraints from prior governance and product discussions. The reviewing tool must verify them against current documents/code before asserting implementation status:

- Terminal is the operational heart.
- Terminal record remains LTR and monospace; it is not mirrored for Arabic.
- Terminal record contains only learner entries, Amadeus outputs, and **one** clearly labeled DEIXEN training line.
- Coach, hints, explanations, and feedback belong in a separate panel, not inside the Terminal record.
- Current learner-facing qualitative statuses are only: **Completed / In progress / Needs more practice**.
- No numeric readiness score, percentages, leaderboard, points, or streaks that imply competence.
- Amadeus truth must come from verified references, not model memory or behavior borrowed from other GDSs.
- Known command behavior, outputs, errors, warnings, prerequisites, and PNR transitions must not be invented.
- Wrong-entry behavior and state preservation should follow the approved command-specific rules, including relevant D33 provisions, after current verification.
- Arabic/English support and RTL/LTR behavior are required, but Terminal itself remains LTR.
- New Arabic curriculum/content is subject to the established Arabic review gate or explicit waiver; do not invent a new gate or assume an old gate still applies without checking the decision log.
- No unapproved expansion of frozen slice scope (including D8A) without explicit scope amendment.
- localStorage is currently temporary storage, not a permanent architectural commitment to avoid a future backend. Backend work is not automatically part of this strategic audit.

## 11. Governance is reviewable, not sacred

The user expressly requires that **every item in `07_DEIXEN_Canonical_Decisions_and_Current_State.md` be open to critique if it affects product development or evidence of the product's goals**.

The reviewing tool must not assume that "accepted" means "never question again." At the same time, the reviewing AI tool must not silently overwrite or bypass accepted decisions. It should:

1. identify the decision and its original rationale;
2. explain the current concern;
3. cite evidence or a clearly labeled hypothesis;
4. compare alternatives and consequences;
5. recommend whether to preserve, revise, retire, or investigate;
6. identify what formal decision/approval would be required.

---

# PART IV — THE NEW STRATEGIC DIRECTION DEVELOPED IN THIS SESSION

## 12. Core shift: from command/lesson/scenario to Professional Work Task

The user's emerging idea is that the primary unit of training and assessment may need to be a **Professional Work Task** rather than an isolated lesson, command, or raw scenario.

A Professional Work Task represents an end-to-end piece of work similar to what a travel-agency or airline-office employee is responsible for.

It may include:

1. receiving a customer request;
2. understanding the customer's real need and priorities;
3. detecting missing, ambiguous, or conflicting information;
4. asking appropriate questions and collecting required data;
5. advising the customer and comparing suitable options;
6. explaining conditions, restrictions, costs, and trade-offs transparently;
7. obtaining or confirming the customer's decision/consent where appropriate;
8. carrying out the relevant operational workflow in Terminal;
9. interpreting actual/verified system responses;
10. handling errors, disruptions, changes, or unexpected conditions;
11. validating that the operational result matches the agreed task;
12. returning to the customer, explaining the outcome, and closing the interaction;
13. where relevant, providing follow-up or after-sales service.

This is a conceptual direction to test, not yet a formally approved architecture change.

## 13. Expand Scenario Bank from raw cases to connected work scenarios

The user's first major product-development idea was to evolve raw scenarios into rich professional cases.

A rich scenario may define:

- customer identity/persona and communication style;
- customer goal and priorities;
- information initially disclosed;
- information not disclosed until the learner asks an appropriate question;
- missing, ambiguous, or conflicting details;
- constraints and decision conditions;
- operational task and required workflow;
- allowed verified Amadeus behaviors and responses;
- possible customer changes, objections, or follow-up events;
- expected operational result;
- professional behavior criteria;
- customer-experience/satisfaction criteria;
- assessment evidence and support conditions.

The scenario should be one coherent context. What the learner learns from the customer interaction affects the operational choices; what happens in Terminal affects the next customer interaction. The scenario should not be a customer chatbot disconnected from the booking task.

Do not limit the case library to new bookings or sales. It should eventually cover relevant operational/customer journeys such as booking, changes, cancellations, disruptions/problems, and after-sales support, based on real job-task analysis and verified operational references.

## 14. Connect Customer Service Track to actual work scenarios

The current direction is **not** to delete the Customer Service track.

Instead:

- **Customer Service within Learning:** teaches the knowledge and skills (customer discovery, question selection, listening, expectation management, explaining options, handling objections, transparency, service recovery, communication, escalation, and relevant sales/service behaviors).
- **Scenario Bank:** provides realistic work cases in which these skills must be applied together with operational skills.
- **Terminal:** handles the operational booking/GDS execution within the same task context.
- **Growth:** records evidence of what the learner demonstrated in customer-facing behavior separately from operational competence.

A course lesson or knowledge check alone does not establish professional communication competence. Practical evidence should come from observed behavior in scenarios using rubrics reviewed by practitioners.

The Customer Service track's existing content and rubrics require a current repo audit. An older consultation noted that several of its five historical lessons may not have valid skill/checklist rubrics; this is a historical claim to verify, not assume.

## 15. Customer satisfaction is a separate outcome, not a competence score

The user extended the idea to include customer satisfaction with the service/sales process.

The scenario may model customer response/satisfaction based on what happened during the task, with explicit reasons (e.g. needs understood, suitable choice offered, conditions explained honestly, expectations managed, operational outcome delivered, follow-up quality).

**Three separate dimensions must remain distinct:**

1. **Professional performance:** whether the learner behaved appropriately and responsibly.
2. **Operational performance:** whether the operational task was executed correctly and the result validated.
3. **Customer experience/satisfaction:** how the customer experienced the interaction and outcome, and why.

Important fairness and ethics rules:

- Customer satisfaction does not compensate for unsafe, dishonest, or operationally incorrect performance.
- A dissatisfied customer does not automatically mean the employee performed poorly; legitimate constraints may prevent the preferred outcome.
- A happy customer does not prove the employee acted professionally; the employee may have hidden restrictions or overpromised.
- Do not reward closing a sale at any cost. The correct professional outcome can be to explain that no available option fits, decline to promise something unverifiable, ask for more information, or escalate.
- Do not collapse all dimensions into one score or numeric readiness index.

## 16. Customer conversation without an LLM: deterministic first version

The user asked whether this connected conversation can exist without a real AI model. The strategic answer explored is **yes**.

A deterministic conversation/scenario engine can use:

- predefined customer facts and hidden facts;
- scenario state and permitted disclosures;
- recognized intent/question categories;
- a controlled set of paraphrases and synonyms;
- conditional response rules;
- branch/state transitions;
- fallback responses when the learner asks outside the scenario's supported scope.

The learner can type messages, while DEIXEN matches the meaning to bounded intents and returns a response grounded in scenario data. It is more constrained than a fully open LLM conversation, but it can still be stateful and adaptive within its designed scope.

A potential division of responsibilities:

- **Scenario Engine:** owns the authoritative facts, constraints, task state, and possible events.
- **Conversation Engine:** interprets the learner's customer-facing questions within the scenario and returns allowed customer responses.
- **Operational/Terminal Engine:** controls simulated GDS behavior and booking state based only on verified/approved behavior.
- **Assessment Engine:** evaluates observable actions/evidence using explicit criteria.

The virtual customer is **not** the Coach. The customer provides information, expresses preferences, and responds as a customer would. The Coach teaches or supports the learner. The two roles must not be confused, especially during assessment.

An LLM may be explored later to improve linguistic flexibility, but it must not:

- invent Amadeus commands, system outputs, policy, fares, availability, airline rules, or booking state;
- alter the authoritative scenario facts or operational state;
- coach the learner during an independent assessment;
- provide the final competence judgment by ungrounded impression.

The deterministic-first proposal itself must be prototyped and tested. Do not claim it is effortless: authoring and validating many dialogue branches may be costly. Measure authoring burden, coverage of natural phrasing, learner frustration, and reliability.

## 17. Assessment must become a stronger scenario-based experience

The user specifically raised that Assessment currently feels like a separate, possibly underpowered or marginalized activity inside Terminal. The user wants it linked to Scenario Bank so it becomes a substantial, meaningful part of the product rather than a small add-on.

The current conceptual direction is:

**Assessment is not an unrelated quiz/extra task; it is a professional work scenario specifically designed to measure independent competence.**

Potential relationship:

- Scenario Bank contains/organizes assessment-eligible cases alongside learning and practice cases, with clear purpose/type/eligibility metadata.
- The learner may encounter or be assigned an assessment scenario through the Scenario Bank/learning journey.
- Execution still happens in Terminal through an isolated Independent Assessment mode/session, preserving D92 and D97.
- The assessment task should be an integrated customer/work task where appropriate, not merely a list of commands or an arbitrary terminal exercise.
- The case is selected or generated with a different structural variant from the learner's guided practice, to reduce memorization and test transfer.
- The clean assessment state, absence of Ghost/hints/Coach/corrective intervention, and assessment-specific evidence rules remain intact.
- Customer information disclosed in response to the learner's natural questions is part of the task, not prohibited assistance.
- Feedback/review may be shown after the assessment is closed and the result/evidence is secured.
- Assessment outcomes feed Growth as evidence, but aided practice evidence must not be misrepresented as independent assessment evidence.

**Critical architectural distinction:** link Assessment to Scenario Bank as a case source, lifecycle, and experience; do not casually relocate execution out of Terminal or mix its data with prior practice. The exact UX/navigation model is still open for exploration.

The reviewing tool must inspect D97 and current code to determine what is already implemented, what is only specified, and what the proposal would actually change. It must not assume that describing the assessment as isolated means every isolation check is already enforced in evidence calculations.

## 18. Progressive scenario difficulty and learner support

Scenarios should not be presented as a random set of equally difficult cases. They should progressively reflect what the learner has actually learned and demonstrated.

A possible progression (illustrative, not approved levels):

1. **Simple request:** clear customer request, most information available, a small number of known operational skills.
2. **Information gathering:** missing or ambiguous information; learner must ask the right questions.
3. **Multi-skill task:** several previously taught skills need to be integrated.
4. **Changing customer conditions:** preference changes, objection, new requirement, or conflicting priorities.
5. **Operational problem and recovery:** a verified operational problem or state change must be interpreted and handled.
6. **Complex professional task:** multiple constraints, decisions, customer interaction, operational workflow, recovery, and close-out.

Difficulty should grow through meaningful dimensions, not merely more commands:

- ambiguity and missing information;
- conflicting customer needs or constraints;
- more than one valid-looking path, only some appropriate;
- a change in conditions during execution;
- the need to interpret a system response;
- error diagnosis and recovery;
- communication and expectation management;
- multiple linked tasks/events.

Do not increase every difficulty dimension at once for beginners. Use worked examples and guided practice first, then gradually fade support as competence grows.

A proposed support progression:

- **Supported Practice:** Coach, hints, examples, and feedback are available; goal is learning.
- **Guided-to-Independent Practice:** support fades; learner makes more decisions independently, with assistance only as needed.
- **Independent Assessment:** no Coach, hints, Ghost, or directive help during the attempt; customer dialogue remains part of the task; review and feedback occur after closure.

This progression should be checked against existing project rules, not substituted for them without formal review.

## 19. Growth as an evidence portfolio, not merely a progress screen

Growth should explain what the learner has actually demonstrated and what remains untested or needs practice.

Possible evidence dimensions (not a new numeric score system):

- customer understanding and information gathering;
- customer communication;
- consultative selling/advice and transparent option presentation;
- operational execution;
- interpretation of system responses;
- error detection, diagnosis, and recovery;
- task completion and verification;
- customer experience/satisfaction and its reasons;
- independence and conditions of performance;
- retention over time and transfer to structurally different tasks.

These dimensions must remain interpretable and evidence-backed. They are not automatically nine new displayed badges or numeric sub-scores. Preserve existing qualitative Growth statuses unless formally reconsidered.

The report should avoid making a learner's Growth page look like an overwhelming dashboard. Evidence should be concise, understandable, navigable, and useful to the learner and potentially an employer, while stating limitations clearly.

## 20. Retention, transfer, and adaptive practice

The old consultation proposed conditions-tagged evidence and delayed probes. These remain valuable research directions:

- record whether evidence was independent or assisted;
- record the timing/interval between observations;
- identify whether the scenario was familiar or structurally varied;
- use a delayed retrieval/probe with a different structural variant;
- distinguish a failure on a familiar variant from a failure on a new variant where possible;
- select future practice based on observed weaknesses, not simply completed lesson count.

Do **not** impose a fixed 24- or 48-hour rule without evidence. Spacing and retention intervals depend on task and intended retention. For GDS workflows, the exact optimal interval is unknown and must be tested.

Do not claim that success on a nearby variant proves far transfer. Classify task differences honestly (e.g. surface change, constraint change, decision change, substantially different context).

Adaptive practice is a hypothesis to explore: if the learner struggles with customer discovery, assign suitable scenarios; if they struggle with response interpretation, select cases that test that skill. But ensure that adaptation does not expose the answer, create assessment leakage, or replace an independent assessment with accumulated assisted evidence.

## 21. Work Shift Simulation / full workday simulation

The older consultation recommends not building a full Work Shift Simulation immediately. That caution remains reasonable.

However, distinguish:

- **Integrated single-customer/single-task scenario:** a full end-to-end professional work task; this is an early strategic direction to explore.
- **Multi-task/workday/shift simulation:** several customers/tasks, interruptions, priority changes, queues or competing demands; this is a later and much larger hypothesis.

Before building a full workday simulator, gather practitioner evidence that task switching, interruptions, queue handling, and prioritization are important sources of beginner failure. Test smaller integrated cases first. Do not assume that maximum realism automatically produces better learning.

---

# PART V — THE OLDER PRODUCT-DEVELOPMENT CONSULTATION

## 22. Status and value of the file from 24 October 2026

The user uploaded a prior document titled:

`DEIXEN — استشارة تطوّر المنتج بعد الاكتمال.md`

Dated 24 October 2026. It is a valuable research/advisory reference, but **not an approved roadmap or implementation authorization**.

Its author described a limited read-only review at commit `c85cf73`, focused on Build Spec, LDS, verified reference, and CLAUDE.md, without reading all files or design files. Many product-state observations were explicitly described as inferred and needing confirmation against the completed version.

Therefore, its technical description is historical and must be revalidated against current repos before being treated as current implementation truth.

## 23. Key ideas from the older consultation worth preserving

It emphasized:

- evidence conditions matter more than raw progress;
- independent performance must be distinguished from training performance;
- retention must not be inferred from immediate success;
- transfer requires structural task variation, not cosmetic changes;
- diagnosing an error before correcting it may support deeper recovery;
- performance time is descriptive only unless external standards justify thresholds;
- no universal booking-time benchmark should be invented;
- Growth should present a qualitative evidence record, not a percentage or confidence score;
- simulator competence must not be equated with total workplace readiness;
- verified-real behavior must remain distinct from DEIXEN-authored simulation;
- the product should be tested in small experiments before major feature investment;
- practitioner/job-market research is required.

## 24. Older recommendations that must be reconsidered, not copied

The older consultation recommended deferring a full Customer Conversation Simulation, using embedded decision points first, and delaying full Work Shift Simulation. It also described a full customer conversation simulator as something not to build yet.

That Customer Conversation recommendation is now **open for reconsideration** because the user has since developed a richer deterministic-first idea: structured but typed dialogue that is connected to an end-to-end customer work task and operational Terminal state. It is not merely an open-ended AI chatbot.

The older consultation's caution about assessment quality and missing communication rubrics remains important. The response should be to define and validate a practitioner-reviewed rubric and test a bounded prototype, not automatically abandon conversation simulation.

The older consultation's proposed order of building a delayed probe before substantial scenario expansion may also need reconsideration. The new professional-work-task model may change the priority and design of what counts as an appropriate probe. Evidence integrity remains a prerequisite, but the learning unit and assessment experience may need broader redesign.

## 25. Key insight from the older consultation to preserve for UX

The file states:

**"The right integration is a shared evidence language, not necessarily merged screens."**

This is a strong design principle for the new direction. A connected work task does not require putting every function into one crowded interface.

Possible distinct surfaces:

- customer conversation area;
- Terminal operational record;
- Coach/help area;
- assessment state/controls;
- Growth evidence view.

The scenario context, learner state, events, transitions, and evidence should connect these surfaces. The UI must make the experience feel continuous and coherent without mixing responsibilities or confusing the learner.

---

# PART VI — GEMINI REPORT AND COMPETITIVE CONTEXT

## 26. Gemini report: useful claims and limitations

The user provided a Gemini report titled:

`DEIXEN — Evidence-Based Professional Competence & Learning-to-Employment Research`

It argued that professional competence includes independent execution, interpretation/adaptation, recovery, transfer, and operational realism. It referenced cognitive load/guidance fading, desirable difficulties, deliberate practice, and ICAO CBTA.

Useful parts to retain and test:

- complete professional competence is more than syntax or final PNR state;
- guidance should fade progressively;
- practice should combine focused subskill work and integrated/varied cases;
- recovery, transfer, retention, and observable behavior matter;
- compare training outcomes on a different/realistic external environment where legally and safely authorized;
- assess with blind human assessors and clear performance criteria.

Limitations and incorrect or unsupported assertions identified in the discussion:

- Gemini did not provide exact commit SHA, repo files, code references, or tests; therefore it did not establish that it had inspected the current repo.
- It described DEIXEN recovery as if recovery logic did not exist, while prior repo/spec review identified an existing limited ER-related recovery practice. The real question is breadth and verification of recovery cases, not whether recovery is absent.
- It referred to an "actual engine parser" supporting unscripted mistakes, but the current known engine is a bounded DEIXEN simulator/classifier, not an actual Amadeus engine or unrestricted Amadeus parser. Current implementation must be rechecked.
- Its claim that Scenario Bank should become the main spaced-retrieval area must respect D92: the Bank is a case/status library and execution remains in Terminal Scenario Mode.
- Its 24–48 hour delayed-assessment recommendation was not scientifically established as a universal threshold. Do not adopt a fixed delay without product-specific evidence.
- Its claim that competitors typically use only click paths, MCQs, or linear emulators was not sufficiently substantiated.
- Its cryptographic transcript proposal does not itself prove identity, validity, or competence; cryptography can support integrity/authenticity but cannot validate assessment quality.
- A production Amadeus terminal should not be used for tests that could affect live bookings or customer data. Prefer authorized training/test environments and appropriate approvals.

Gemini report is an input for critique, not an implementation specification.

## 27. Competitive landscape explored in prior discussion

Public research identified products/services with partial conceptual overlap:

- **TTEC College of Travel:** publicly describes travel-advisor training with a conversational bot simulating scenarios within GDS sandboxes. It is the closest public example identified so far. Public material did not establish that its customer conversation is linked to the same evolving PNR/task state through one continuous end-to-end workflow, but absence of public evidence is not proof that it lacks the feature.
- **Mundus GDS Training Solution:** publicly describes computer-based learning, GDS simulation, role play, tests, and case studies. Published information did not establish a live/free-form customer interaction integrated with the same operational booking state.
- **GDS LAB:** offers GDS education/simulation and scenario/test features; published materials did not establish the exact connected customer-lifecycle experience proposed here.
- **Amadeus Learning Partners:** has authentic Amadeus training-environment access, digital lessons, learning paths, and training/certification opportunities. It has strong authority and system-context advantages.

Therefore, DEIXEN must **not** claim that customer simulation + GDS training is globally unprecedented. The possible differentiation is the depth and quality of integration:

- one connected customer/work task from discovery to operational execution to closure/follow-up;
- deterministic or tightly controlled customer behavior tied to scenario state;
- separate and valid evidence for customer service, operational correctness, judgment, independence, recovery, retention, and transfer;
- structured progressive difficulty and fading support;
- employer-readable evidence without overclaiming job readiness.

This differentiation remains a hypothesis until named competitors are tested on common tasks, with comparable learner groups, time-on-task, and blind evaluation.

---

# PART VII — UX, UI, SCIENTIFIC VALIDATION, AND PRODUCT QUALITY

## 28. Scientific evidence standards

The user requires the strongest available scientific basis for training, independence, retention, transfer, feedback, and workplace preparation.

The reviewing tool must:

- prioritize systematic reviews, meta-analyses, robust experimental studies, and authoritative standards;
- distinguish direct evidence from adjacent-domain extrapolation (e.g. medical simulation, aviation CBTA, classroom learning);
- verify original research rather than relying on secondary summaries where possible;
- explain population, task type, outcome, effect, moderators, and limitations;
- avoid converting a general research result into an unsupported Amadeus-specific rule;
- identify evidence gaps and design DEIXEN-specific experiments.

Research areas relevant to the strategy include:

- worked examples and guidance fading / expertise reversal;
- cognitive load for novices;
- retrieval practice and spacing;
- interleaving and task variation;
- deliberate practice and mastery learning;
- error management and recovery;
- feedback effectiveness and help-seeking;
- transfer of training;
- simulation fidelity versus functional/task fidelity;
- assessment validity, multiple observations, and sampling across contexts;
- workplace transfer conditions and supervisor/employer evaluation;
- human-computer interaction and cognitive load in complex interfaces.

A principle can be well-supported generally while its application to GDS reservation workflows remains untested. Label that distinction.

## 29. Product-specific evidence and validation

Possible validation layers:

1. **Professional task analysis:** job ads, interviews with reservation/ticketing professionals, trainers, supervisors, and employers in Saudi Arabia, Oman, and the UAE.
2. **Content/operational validity:** each Amadeus behavior and response verified from authoritative references or authorized environments; scenario reviewed by an experienced practitioner.
3. **Usability/UX:** beginners can understand what to do, how to get help, how to switch between customer and Terminal contexts, and how to interpret their evidence without confusion.
4. **Formative learning tests:** observe novice learning, error patterns, confusion, help usage, and completion barriers.
5. **Learning effectiveness:** compare pre/post performance with appropriate measures, not satisfaction alone.
6. **Retention:** delayed independent observations at intervals selected for the task and intended retention, without assuming a fixed universal interval.
7. **Transfer:** structurally novel cases, not just new names/dates.
8. **Independent assessment:** clean, isolated, task-level evidence and blind human review where feasible.
9. **Workplace relevance:** supervised practice, employer feedback, and work samples where partnerships and legal access permit.
10. **Competitive benchmarking:** compare DEIXEN with named alternatives on the same tasks, time, and learner profile, with blind assessors.

Avoid claims such as "job-ready" or "better than Amadeus" until the study design and evidence justify the exact claim.

## 30. UX and UI are both strategic priorities

The user has repeatedly stated that a technically sound UX flow is not enough if the visual UI feels weak, generic, or like a colored document rather than a real professional application.

The product must combine:

- strong learning architecture;
- clear navigation and next-step guidance;
- low unnecessary cognitive friction;
- understandable support/hints/feedback;
- coherent movement between learning, customer interaction, Terminal, scenario, assessment, and Growth;
- polished, distinctive, mature visual language and interactions;
- consistency across the five areas;
- Arabic/English and RTL/LTR usability while preserving Terminal's LTR behavior.

The customer-work scenario is especially complex: the UI must show the customer conversation and Terminal operations as separate but connected workspaces, preserve the Terminal transcript rules, and expose the learner's progress through the task without revealing the answer or overwhelming them.

**Do not confuse functional integration with putting everything on one screen.** Explore the information architecture and interaction model. The user expects UX and UI quality together, not a tradeoff where one excuses the other.

Current visual identity/design decisions may have their own user-specific scope and governance. Do not reopen or change design tokens/identity solely because this document discusses new workflow UX; check current instructions and explicit authority.

---

# PART VIII — IMPORTANT DISTINCTIONS AND OPEN QUESTIONS

## 31. Keep these concepts separate

| Concept | What it means | What it does not prove by itself |
|---|---|---|
| Practice success | Learner performed an activity correctly in training | Independent competence |
| Independence | Performance without prohibited help in that attempt | Retention or transfer |
| Retention | Ability remains after a meaningful interval | Transfer to unfamiliar tasks |
| Near transfer | Ability on a changed but related task | Far transfer or workplace performance |
| Operational accuracy | Correct system/task result | Good customer service or judgment |
| Customer satisfaction | Customer's perceived experience | Professional correctness |
| Simulator competence | Demonstrated performance in specified simulated conditions | Full job readiness in all workplaces |
| Workplace readiness | Broader ability evidenced in real work contexts | Automatically guaranteed by a simulator certificate |
| Assessment scenario | A scenario deliberately designed to measure competence | It is not an excuse to mix assisted practice into assessment evidence |
| Partner eligibility | Meets stated criteria to apply or be considered | Guaranteed approval or funding |

## 32. Open questions for any AI reviewer to investigate

1. What should the canonical data model for a Professional Work Task contain?
2. How should customer facts, hidden information, dialogue intents, decisions, operational state, events, and assessment rubrics be represented so they remain consistent?
3. Can a deterministic text conversation cover sufficient natural learner phrasing without creating excessive authoring cost or frustration? What prototype would test this?
4. How should Customer Service skills be defined and assessed by observable behavior? Which rubrics require practitioner input?
5. Should each integrated scenario have one or multiple phases (pre-booking, booking, disruption, after-sales)? How should task complexity be controlled?
6. How does Assessment appear in Scenario Bank, how is an assessment-eligible scenario selected, and how is it launched as an isolated Terminal assessment under D97?
7. What exact conditions must be recorded to distinguish independent, delayed, familiar, and transfer evidence?
8. How can Growth show a concise, honest evidence portfolio without scores or misleading readiness claims?
9. How should customer satisfaction be modeled without allowing it to distort competence evaluation or reward unethical selling?
10. How can scenarios be adaptive to learner weaknesses without leaking answers or contaminating independent assessment?
11. What is the minimum validated integrated scenario set that would meaningfully test the idea before a full work-shift simulation?
12. What real job tasks and beginner failure patterns are most important in Saudi Arabia, Oman, and the UAE?
13. What evidence would demonstrate meaningful differentiation from TTEC, Mundus, GDS LAB, Amadeus Learning Partners, and other relevant providers?
14. Which current `07` decisions should remain, which deserve formal reconsideration, and what evidence would justify changing them?
15. What product capabilities, legal structure, business model, customer traction, quality evidence, and technical/operational maturity would DEIXEN need before approaching Amadeus Learning Partners, APN, or Ventures?
16. What UX model can make this multi-dimensional experience feel simple and coherent to a beginner without flattening the professional task?

---

# PART IX — REQUIRED OUTPUT FROM ANY AI REVIEWER

## 33. Expected review deliverable

The reviewing tool should produce a rigorous, evidence-led review with the following structure:

### A. Repository reality check

- exact repo names, branches, current main commit SHAs;
- documents and code inspected;
- verified implemented capabilities versus documented/planned capabilities;
- gaps between current app, Build Spec, LDS, decisions in `07`, Gemini's report, Claude's report, and this brief.

### B. Strategic diagnosis

- Is the Professional Work Task direction conceptually sound?
- Is it actually differentiated, or does it overlap with existing competitors?
- What value does the connected customer lifecycle add beyond conventional GDS simulation and role play?
- What are the largest risks and hidden assumptions?

### C. Learning architecture

- evaluate the full sequence: learning → customer-service learning → supported practice → integrated work scenario → fading support → isolated assessment scenario → delayed retention/transfer → Growth evidence;
- recommend a more evidence-supported sequence if better;
- distinguish subskill training from whole-task integrated practice;
- define the right role of Coach, hints, customer persona, and post-attempt feedback.

### D. Scenario Bank and Assessment architecture

- propose how raw cases become structured work scenarios;
- explicitly explain how Assessment should be linked to Scenario Bank;
- preserve execution through Terminal Scenario Mode if D92 remains justified;
- preserve D97 isolation and specify how to prove the isolation in code and evidence calculation;
- propose scenario taxonomy, progressive difficulty, structural variation, and eligibility rules;
- evaluate organizing Scenario Bank into recognizable day-to-day work sections, with multiple realistic cases in each section;
- assess whether system-accepted-but-professionally-wrong cases should be a dedicated collection, cross-cutting tags, or both;
- distinguish learning, guided practice, integrated practice, assessment, retention, and transfer cases without multiplying redundant UI areas.

### E. Customer Service and customer satisfaction

- propose observable communication/sales/service behaviors;
- identify what requires practitioner-reviewed rubrics;
- propose deterministic conversation architecture and test scope;
- assess whether an LLM is necessary at all, and under what hard boundaries it could be introduced later;
- keep professional performance, operational performance, and customer satisfaction separate;
- include ethical selling, transparent constraints, appropriate escalation, and customer outcome fairness.

### F. Growth and evidence model

- propose evidence dimensions and metadata;
- ensure evidence is conditions-tagged (support, timing, task structure, context, errors/recovery);
- avoid numeric readiness scores and unsupported certification language;
- define how Growth communicates limitations clearly and how employer-facing evidence could be made useful without overclaiming.

### G. Scientific and market evidence

- verify primary scientific sources and limitations;
- identify evidence directly relevant to workplace/aviation/technical procedural skills versus adjacent fields;
- research Saudi, Oman, UAE job tasks and beginner expectations methodically;
- interview practitioner requirements or propose a realistic interview protocol;
- benchmark named competitor products without unsupported generalizations.

### H. UX/UI implications

- propose an interaction model that connects customer conversation and Terminal while preserving their distinct roles;
- show how the next action, task state, and support level remain clear;
- ensure accessibility, bilingual/RTL considerations, and no false affordances;
- identify cognitive-load and screen-complexity risks.

### I. Amadeus institutional/partnership path

- clarify what makes DEIXEN primarily a training institution with a proprietary training system, not necessarily a software vendor;
- compare relevant Amadeus Learning Partners, APN, and Ventures paths;
- list current evidence gaps and requirements to verify directly with Amadeus and Egyptian authorities;
- do not invent prices, thresholds, approvals, or requirements.

### J. Prioritized recommendations

For each recommendation provide:

- problem addressed;
- supporting evidence and its strength;
- direct versus indirect evidence;
- expected learner/employer value;
- current repo impact;
- risks/tradeoffs;
- smallest useful validation experiment;
- acceptance criteria;
- decision needed (preserve / revise / investigate / reject / defer).

### K. Simulated workplace and English voice interaction

- assess the three linked lifecycles (customer journey, learner/professional journey, work-task lifecycle);
- distinguish an individual integrated work task from connected customer cases and full workday simulation;
- determine whether a simulated workplace improves learning/transfer or merely adds narrative complexity;
- evaluate typed deterministic conversation and English voice input as separate interaction options;
- propose an ASR → transcript/uncertainty → deterministic conversation/state engine → optional TTS architecture if justified;
- assess accent fairness, intelligibility, pronunciation coaching, transcript correction, retry, and text fallback;
- separate ASR error from learner performance and English communication competence;
- address privacy, consent, audio retention, cost, latency, browser/device compatibility, and accessibility;
- specify the smallest prototype and measurable criteria that would justify or reject voice interaction.

### L. Final critical verdict

Answer plainly:

- What is the strongest part of the current direction?
- What is the biggest strategic mistake or missing capability?
- What should be tested first?
- What should explicitly not be built yet?
- What would make DEIXEN meaningfully more valuable than the competitors?
- What is the realistic path toward becoming a credible candidate for Amadeus collaboration?

Do not simply restate this brief. Improve it, challenge it, and show what evidence would change your conclusions.

---

# PART X — CURRENT WORKING CONCLUSION

## 34. The current strategic hypothesis (not approved architecture)

The strongest current hypothesis is that DEIXEN should evolve toward a connected **Professional Work Competence System** in which the learner is trained and assessed through realistic, progressively complex work tasks.

The task begins with a customer need and proceeds through inquiry, judgment, advice/sales, operational execution, interpretation, recovery, customer communication, and closure/follow-up. Customer Service remains a taught track in Learning and becomes observable in applied scenarios. Scenario Bank becomes a rich library of work cases. Terminal remains the operational execution environment. Assessment is linked to assessment-eligible scenarios but runs in a clean independent mode. Growth preserves distinct evidence about professional behavior, operational performance, customer experience, independence, retention, and transfer.

The first version of customer interaction can be deterministic and bounded, with no LLM required. More advanced conversation generation may be explored later under strict truth and assessment controls.

The scenario pathway should progress from simple, supported tasks to integrated and increasingly variable tasks, while support fades. Delayed probes and structural transfer cases should test what remains and what generalizes. Full work-shift simulation is a later hypothesis, not an immediate requirement.

The ambition is to create a specialized training institution and a proprietary training system that can demonstrate genuine value to learners and employers, and eventually become a credible candidate for a suitable Amadeus partnership or collaboration.

## 35. What is not decided yet

The following are **not** approved implementation decisions:

- redefining the canonical product unit as Professional Work Task;
- converting Scenario Bank into a complete work-scenario library;
- the exact customer conversation engine, even though deterministic-first is the preferred starting hypothesis;
- the exact customer satisfaction model or display;
- the new relationship/navigation between Assessment and Scenario Bank;
- the exact assessment case taxonomy and launch flow;
- the final Scenario Bank section structure, including which daily-work domains deserve top-level sections and which are cross-cutting collections/tags;
- the full learning/scenario progression and adaptation algorithm;
- the revised Growth evidence schema;
- a full Work Shift Simulation;
- introducing LLM into customer simulation;
- changes to any `07` decision;
- any changes to current code, docs, architecture, or scope.

All are to be evaluated after the Claude report and independent AI critical reviews, then taken through formal decision-making.


---

# PART XI — EXPANDED STRATEGIC IDEA: THE SIMULATED WORKPLACE AND TWO CONNECTED JOURNEYS

## 36. A simulated workplace, not merely a collection of simulations

The user has proposed a broader concept that should be evaluated as a strategic product direction:

**The learner experiences both the customer's journey and the employee's professional journey inside one coherent simulated travel-business environment.**

This is broader than adding customer chat to a GDS exercise. The learner is placed in a credible simulated workplace and develops from a beginner toward independently performing professional responsibilities. Customers arrive with needs, questions, constraints, objections, changes, and after-sales issues. The learner receives tasks, learns relevant skills, practices them, handles the operational work, and gradually demonstrates the ability to take on more complex responsibilities.

The concept may be described as:

**Learner-to-Professional Journey within a Simulated Workplace**

Do not interpret "employee lifecycle" as HR software or an imitation of hiring, payroll, leave, promotion administration, or termination. The intended focus is the learner's development within a professional role: onboarding to the role, foundational learning, supported work, increasing responsibility, independent performance, and continuing professional development.

This is a strategic hypothesis, not an approved architecture or a decision to build a fictional company-management game.

## 37. Keep three lifecycles conceptually distinct, then connect them

The emerging model contains three related but distinct lifecycles:

1. **Customer Journey:** inquiry, discovery, clarification, advice, selection, sale/service decision, fulfillment, changes/problems, confirmation, and after-sales follow-up.
2. **Professional Journey:** onboarding to the role, learning, supported practice, gradually increasing responsibility, independent performance, and further development based on evidence.
3. **Work Task Lifecycle:** the start-to-finish steps and outcome of one concrete professional task.

The product should connect these lifecycles through scenario context, task state, learner support, operational state, events, and evidence. Do not collapse them into one vague progress journey. Identify what belongs to each and how each informs the others.

## 38. Possible layers of simulated workplace experience

A potential progression to investigate:

- **Individual Work Task:** one customer and one complete task, from first contact to closure/follow-up.
- **Connected Customer Cases:** multiple interactions with the same customer, a returning customer, a change after partial execution, or several linked tasks.
- **Simulated Work Environment / Workday:** several customers and tasks, interruptions, competing priorities, task switching, and changing workload.

The first layer is an early strategic direction to prototype. The second may follow as evidence and authoring capability mature. The third is a larger future hypothesis and should not be built merely because it feels more realistic. Practitioner research must establish whether task switching, interruptions, queues, and prioritization are meaningful sources of beginner failure and whether a workday simulation improves learning beyond integrated individual tasks.

The environment must not become a gamified life simulator. Avoid fictional badges, points, streaks, promotions, and narrative decoration that do not improve professional learning or evidence. The simulated workplace exists to provide coherent professional context, not to turn DEIXEN into a game.

## 39. How the five product areas may support the simulated workplace

Do not add a sixth top-level area by default. Explore how the five current areas can support this model:

- **Flight Deck:** explains the next learning/practice/work task based on demonstrated evidence and current development needs.
- **Learning:** teaches the knowledge and subskills needed for the learner's current and upcoming responsibilities.
- **Terminal:** remains the operational place where relevant GDS work is executed.
- **Scenario Bank:** becomes a structured library of customer cases and professional work tasks, with purpose, prerequisites, complexity, variants, verification status, and evidence criteria.
- **Growth:** presents the learner's demonstrated capabilities and gaps without becoming an HR profile or unsupported job-readiness score.

Connection does not require every activity to appear on one screen. Preserve the principle: **shared context and evidence, distinct interfaces for distinct responsibilities.**

## 40. How this could improve learning — and what must be proven

Potential value to test:

- knowledge is learned in relation to why and when a professional uses it;
- customer-service learning becomes applied behavior rather than only lesson completion;
- operational commands are situated in meaningful decisions and customer outcomes;
- learners experience responsibility for completing and verifying a task, not just entering commands;
- skills recur in new contexts, supporting retrieval, integration, and transfer;
- the learner's development is visible through evidence rather than fictional career progression.

Risks to test:

- contextual story and multiple information streams may overload beginners;
- a persistent fictional workplace may increase authoring and maintenance costs;
- too much narrative may distract from task learning;
- a false sense of realism may hide inaccurate operational behavior;
- the learner may mistake simulated responsibility for actual authorization or job readiness.

The correct outcome is not maximum immersion. It is better independent professional performance, retention, transfer, judgment, and usability compared with a simpler alternative.

---

# PART XII — NEW EXPLORATORY IDEA: ENGLISH VOICE CONVERSATION AND SPOKEN COMMUNICATION PRACTICE

## 41. The user's new idea

The user proposes adding an optional microphone/voice interaction mode for customer conversations, instead of relying only on typing. The proposed scope is **English-language customer interaction only**. Arabic customer interaction remains text-based because the initial educational purpose is to help learners practice professional spoken English in travel/customer-service contexts.

Potential learner behavior:

- the learner presses a microphone control and speaks to the simulated customer in English;
- the system converts speech to text and interprets the recognized utterance within the scenario's bounded conversation rules;
- if the utterance is understood and fits the scenario context, the appropriate customer response is delivered;
- if the speech is not reliably understood, the virtual customer may say a natural repair phrase such as "Sorry, I didn't catch that. Could you repeat that?";
- the learner may repeat, rephrase, inspect/correct the recognized transcript, or switch to typing;
- the core text interaction remains available as a fallback and accessibility option.

This is an exploratory feature hypothesis, not an approved requirement or an implementation commitment.

## 42. Voice interaction is technically feasible without making the scenario LLM-driven

A bounded voice workflow can use a pipeline such as:

1. microphone permission and explicit user activation;
2. audio capture;
3. automatic speech recognition (ASR / speech-to-text);
4. transcript plus uncertainty/recognition metadata;
5. deterministic intent and meaning recognition within the scenario's allowed conversation scope;
6. scenario-state validation;
7. a response selected from verified scenario facts and dialogue rules;
8. optional text-to-speech (TTS) to speak the virtual customer's response.

Therefore, voice input does not require a free-form LLM. The existing deterministic-first conversation concept can remain the source of truth. ASR converts the learner's spoken English into candidate text; the Conversation Engine then processes it under the same bounded rules used for typed input.

The virtual customer's spoken response is a separate optional layer. A first prototype could accept voice from the learner and return text, then add TTS if tests show that spoken replies materially improve the experience. Do not assume voice-to-voice is necessary in the first experiment.

Keep the GDS Terminal command-entry workflow separate. This idea concerns spoken customer communication, not dictating Amadeus commands into the operational terminal unless that is separately researched and approved.

## 43. Recognition failure must not be confused with learner incompetence or accent quality

A critical fairness rule:

**If ASR cannot confidently recognize the learner's speech, DEIXEN must not automatically conclude that the learner's English, accent, or customer-service performance is poor.**

Recognition can fail because of microphone quality, noise, clipping, speed, overlapping speech, vocabulary, model limitations, connectivity, or accent-related bias. A recognition failure is initially a system/input uncertainty, not proof of a learner error.

Possible behavior:

- high-confidence, context-compatible transcript: proceed to scenario interpretation;
- uncertain transcript: show what the system heard and ask for confirmation or repetition;
- clear recognition failure: customer-style repair request, then retry;
- repeated failure: offer typed input without penalty and preserve task continuity;
- transcript materially different from what the learner said: allow correction before it affects scenario state.

The system must not blame the learner's accent by default. It should say it did not catch the utterance, not assert that the learner has a bad accent. Evaluate the recognition layer separately from the learner's speaking performance.

## 44. English improvement must prioritize intelligibility and professional communication, not accent erasure

The user's goal includes helping learners improve spoken English and pronunciation. This is worthwhile, but the educational standard must be carefully defined.

Do not treat an Egyptian or other non-native accent as inherently incorrect. An accent is not equivalent to unintelligibility. Research supports prioritizing intelligibility and comprehensibility over sounding native-like; a 2025 meta-analysis found intelligibility and accentedness are related but distinct, and that having an accent does not mean speech is unintelligible. A 2021 meta-analysis found pronunciation instruction produced larger gains in comprehensibility than in native-likeness. See the evidence links in Section 49.

For a travel-service employee, the useful goals are:

- the customer can understand the employee's message;
- dates, names, destinations, times, prices, conditions, and restrictions are spoken clearly;
- the learner uses appropriate professional language and tone;
- the learner can ask clarifying questions and confirm critical details;
- the learner can repair a misunderstanding politely;
- the learner can listen to and understand common customer responses;
- the learner can communicate transparently without overpromising.

Pronunciation coaching may address specific sounds, stress, rhythm, pace, and intonation when they affect intelligibility. It must not impose one native accent as the only acceptable target.

## 45. Separate English language coaching from professional competence assessment

The system should avoid collapsing three separate things:

1. **Customer-service/professional communication:** Did the learner ask the right question, understand the need, explain options, manage expectations, and communicate responsibly?
2. **English communication effectiveness:** Was the spoken message understandable and professionally appropriate for the task?
3. **ASR/system recognition quality:** Did the speech-recognition service correctly capture what the learner said?

A fourth optional layer may provide pronunciation/fluency coaching. It should be developmental feedback, not an automatic barrier to proving operational competence.

A learner should not fail a customer-service task solely because the ASR engine misheard them. Nor should a favorable ASR transcript be treated as proof of strong spoken communication if the learner did not understand the customer's reply or could not communicate effectively.

For a fair assessment, consider human review or carefully validated measures for spoken communication. Automated pronunciation scores should be shown with limitations and must not become a disguised employability score.

## 46. English-only voice policy and Arabic handling

The proposed initial scope is:

- **English:** optional microphone-based conversation and spoken English practice; typed fallback always available.
- **Arabic:** retain text interaction in the initial product scope; no Arabic voice-pronunciation training is proposed at this stage.

This is a scope hypothesis, not a statement that Arabic speech recognition is technically impossible. The reason is product intent: the learner is a native/Arabic-speaking user who needs English customer-service practice. Revisit only if market research shows a real need for Arabic voice input, bilingual workplace simulation, or accessibility.

The interface should clearly label when the scenario is in English voice mode. It must not force voice; some users may have speech disabilities, noisy environments, privacy concerns, or simply prefer typing.

## 47. Voice privacy, UX, and technical risks

Before any voice prototype or production implementation, assess:

- explicit microphone permission and clear active-recording indicator;
- when recording starts/stops and how the learner can cancel;
- whether audio is processed on-device or sent to a provider/server;
- audio and transcript retention, deletion, consent, and data minimization;
- data-processing terms and applicable privacy laws in target markets;
- latency and connectivity requirements;
- supported browsers/devices and fallback behavior;
- performance on Egyptian-accented English and other likely learner accents;
- performance with travel-specific vocabulary, names, city names, dates, codes, and numbers;
- noise, microphone quality, speech speed, hesitation, and self-correction;
- cost per interaction if a paid speech API is used;
- keyboard, touch, and accessibility alternatives.

A simple browser API should not be assumed to be production-ready across all devices. Browser speech recognition support is limited/inconsistent, and some implementations send audio to a server for recognition. On-device recognition options also have compatibility and language-pack constraints. An external ASR service may offer more control, but introduces provider cost, privacy, latency, retention, and language/accent performance questions. Provider and architecture choice must follow a prototype and privacy review.

## 48. Suggested validation sequence for voice interaction

Do not build a full voice simulator immediately. Test the uncertainty in stages:

1. **ASR feasibility test:** collect consented test utterances from representative learners speaking English with Egyptian and other relevant accents. Use travel/customer-service vocabulary. Measure recognition errors by word type and task impact, not only aggregate accuracy.
2. **Deterministic dialogue test:** feed transcripts into the bounded Conversation Engine and test whether intent/state matching returns the right customer response. Include paraphrases, incomplete phrases, repairs, and unsupported questions.
3. **Fallback usability test:** test repeat, rephrase, transcript correction, and switch-to-text flows. Ensure failures do not punish learners or corrupt scenario state.
4. **Voice versus text learning study:** compare whether optional speaking practice improves the target outcomes beyond typed conversation, accounting for time-on-task and prior English ability.
5. **Pronunciation coaching test:** evaluate intelligibility and communicative success with human listeners and transparent criteria. Keep accent similarity/native-likeness separate from intelligibility.
6. **Privacy/cost/latency review:** only after the educational value and recognition quality are demonstrated should a production architecture be chosen.

The first experiment should be narrow: a few high-frequency customer-service exchanges (asking dates, passenger count, preferences, flexibility, spelling names, confirming details, explaining a restriction, and repairing misunderstandings), not an unrestricted conversation engine.

## 49. Sources for voice feasibility and pronunciation principles

These sources support technical possibility and the caution around accent evaluation; they do not prove that a particular provider will perform well for DEIXEN learners:

- MDN, Web Speech API overview: speech recognition and speech synthesis are separate browser capabilities; recognition receives audio and returns recognized text. Some implementations use server-side recognition; on-device recognition may be possible subject to browser/platform support. https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API
- MDN, SpeechRecognition: currently marked limited availability and not supported consistently across widely used browsers. https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition
- Google Cloud Speech-to-Text documentation: recognition confidence may be returned but is not guaranteed for every result and should not be treated as a definitive measure of correctness. https://docs.cloud.google.com/speech-to-text/docs/v1/speech-to-text-requests
- Microsoft Foundry/Azure Speech pronunciation assessment documentation: describes scripted and unscripted pronunciation assessment, with measures such as accuracy, fluency, completeness, prosody, and word/phoneme-level feedback. This is one possible provider capability, not a recommendation or provider selection. https://learn.microsoft.com/en-us/azure/ai-services/speech-service/how-to-pronunciation-assessment
- Chau & Huensch (2025), meta-analysis of relationships among L2 fluency, intelligibility, comprehensibility, and accentedness: supports the distinction between accent and intelligibility, and prioritizing understandable speech over accent reduction. https://doi.org/10.1017/S0272263125000014
- Saito et al. (2021), meta-analyses on comprehensible and native-like L2 pronunciation: pronunciation instruction produced larger gains in comprehensibility than in nativelikeness. https://doi.org/10.1002/tesq.3027
- Feng et al. (2024), “Towards inclusive automatic speech recognition”: documents recognition bias across regional and non-native accents, and notes that pronunciation differences explain only part of the bias. https://doi.org/10.1016/j.csl.2023.101567

## 50. Questions for every AI reviewer about the simulated workplace and voice idea

- Does the three-lifecycle model (customer, professional development, work task) create a real learning advantage, or unnecessary narrative complexity?
- What should be persistent across customer interactions, and what should reset between scenarios or independent assessments?
- How can the product show professional progression without gamification, fictional promotion, or readiness scores?
- Which elements of a simulated workplace are supported by task analysis and practitioner evidence, and which are merely atmospheric?
- What is the smallest meaningful prototype of an integrated work task before attempting multi-customer or full-shift simulation?
- Should customer conversation initially be typed, voice-enabled, or offer both? Which outcomes would justify voice?
- Can an ASR transcript safely feed the deterministic scenario engine without creating false customer responses or accidental state changes?
- How should uncertain recognition, misrecognition, accent variation, and fallback be represented in learner evidence?
- What pronunciation/English feedback is valid and useful for reservation staff, and what should remain outside competence scoring?
- How can English-only voice practice be implemented accessibly while preserving Arabic text interaction and user choice?
- What privacy, consent, retention, cost, latency, and browser/device constraints would affect feasibility?
- Does optional voice improve learner outcomes enough to justify its cost and UX complexity compared with text-only interaction?


---

# PART XIII — NEW EXPLORATORY IDEA: SYSTEM-ACCEPTED BUT PROFESSIONALLY INCORRECT ACTIONS

## 51. The distinction introduced by the user

The user identified an important class of professional errors that can be missed by a simulator focused only on command syntax or whether the GDS accepts an action:

**An action may be accepted by the system and still be wrong for the customer's request, the source documents, the task context, or the applicable professional/business rules.**

This extends the earlier example in which a task is completed operationally but the learner's underlying decision is wrong. The learner may proceed through several technically accepted steps, while the resulting booking or service outcome is not what the customer asked for or is based on incorrect information.

Example raised by the user: a booking may appear complete and the learner may proceed through pricing and ticket issuance, but the passenger's name may have been transcribed incorrectly or inconsistently with the supplied passport/travel document (for example, confusing `Ahmed` and `Ahmad`). This is an illustrative training case, **not** a claim that every such spelling difference is accepted by every Amadeus workflow, airline, market, or ticketing policy. Exact system acceptance, correction options, downstream effects, fees, and travel consequences must be researched and verified for each case before DEIXEN models them.

## 52. Four layers that must not be confused

Every relevant scenario should distinguish, where applicable:

1. **Command/input validity:** Was the command or entry syntactically valid?
2. **System acceptance and operational state:** Did the actual system accept it, reject it, or accept it subject to a condition? What state did it really create?
3. **Task/customer correctness:** Does the resulting state match the customer's request, confirmed choices, constraints, and source documents?
4. **Professional/business correctness:** Was the learner's judgment and handling appropriate under verified operating procedures, airline rules, office context, and applicable policy?

Passing one layer does not prove the next. In particular, a successful system response or a technically complete PNR/ticket must not automatically count as successful completion of the professional work task.

## 53. Scenario categories to support

Scenario authors and reviewers should consider at least these distinct cases:

- **System-rejected error:** the real system refuses the action and returns a verified response. The learner must interpret and recover from it.
- **System-accepted, task-incompatible action:** the system accepts the action, but it conflicts with the customer's stated need, selected option, constraints, or source information. The simulator should not fabricate an Amadeus error or block the action merely because DEIXEN knows it is wrong.
- **Accepted action with a latent/downstream defect:** the action is accepted at the time, but the mismatch is discovered at a later checkpoint or event, when the consequences become operationally relevant.
- **Correct operational action with weak professional handling:** the system outcome may be correct, but the learner failed to clarify, explain, confirm, disclose a limitation, or communicate appropriately. This is a separate professional-performance issue, not a GDS error.

These cases should be designed as realistic variants of Professional Work Tasks and may be useful in Customer Service learning, Scenario Bank practice, recovery training, and isolated assessment. They are not a proposal to create another product area or move scenario execution out of Terminal.

## 54. Do not let the training layer falsify the system

DEIXEN must preserve the difference between the real system's response and the training evaluator's knowledge:

- If verified system behavior rejects an action, show the authentic verified response and state change.
- If verified system behavior accepts it, let it proceed in the simulation; do not insert a fake Amadeus rejection or pretend the command failed.
- The scenario/task model should separately retain the authoritative customer request, confirmed choices, supplied source data, constraints, and expected outcome. It can therefore detect a mismatch even when the GDS does not.
- The assessment evaluator may record that the action was accepted operationally but was inconsistent with the task. It must not rewrite the Amadeus transcript or mislabel a DEIXEN training observation as an Amadeus message.
- In supported practice, Coach feedback may identify the mismatch at a pedagogically appropriate time. In independent assessment, no instructional warning should reveal the hidden defect before the learner has had a fair opportunity to detect it; feedback follows the secured attempt/result.
- Do not silently auto-correct the learner's entry, repair the PNR, or convert a wrong action into a correct one. If a recovery path exists, it must be grounded in verified rules and must remain the learner's action.

This preserves the existing doctrine: the operational record contains only authentic/verified system output, learner entries, and the explicitly labeled DEIXEN training line; coaching and assessment interpretation remain separate.

## 55. Customer awareness and customer satisfaction must be modeled fairly

The customer persona should not magically know every hidden system/data defect. If the customer has no realistic way to notice a name mismatch during the current conversation, the persona should not instantly announce that the learner made a typo merely to expose the error. The scenario can instead reveal it through a credible later checkpoint, document comparison, customer follow-up, or downstream event—only where the sequence and consequences are verified.

Likewise, customer satisfaction must not be mechanically reduced whenever the hidden evaluator detects an error. Separate:

- the correctness and safety of the professional/operational result;
- what the customer actually experiences or can reasonably perceive at that point;
- any later customer impact once the defect becomes visible; and
- the learner's communication and recovery after discovery.

A customer may initially appear satisfied while an important latent defect remains. That does not make the task professionally successful. Conversely, the simulated customer should not be made dissatisfied without a plausible customer-facing cause. Scripted customer reaction remains simulated experience, not empirical real-world CSAT.

## 56. Why this matters for learning and assessment

This scenario family can teach and assess capabilities that command-success exercises can miss:

- comparing entered details against an authoritative customer document or source record;
- checking that selected options match the customer's confirmed choice and constraints;
- recognizing when a plausible/accepted action is nevertheless inappropriate;
- distinguishing system acceptance from professional verification;
- checking the complete outcome before communicating completion;
- anticipating relevant downstream consequences without inventing them; and
- diagnosing, disclosing, escalating, and recovering from a defect through verified procedures.

Assessment should include cases in which the learner has to detect a discrepancy before finalizing, and other cases in which the defect is only revealed later. The task rubric must define what the learner could reasonably know at each point, what checks were expected, and whether the learner had an opportunity to prevent or recover from the problem.

A system-accepted action that violates a required customer or document detail may therefore be a critical task failure even if the GDS workflow itself completed. Conversely, an error that is outside the learner's control or that could not reasonably be detected under the supplied information must not automatically be treated as learner incompetence. These judgments require practitioner-reviewed criteria and validated scenario facts.

## 57. Evidence and implementation guardrails

Before any case enters the authoritative scenario library or independent assessment pool, DEIXEN should document and verify:

- the exact customer request and ground-truth source data;
- the exact learner action and the relevant task context;
- the real system's accepted/rejected behavior and resulting state, from authorized and verified references/environment;
- whether the error is immediately observable or latent, and who can reasonably detect it;
- verified recovery options, prerequisites, restrictions, and downstream consequences;
- the point at which the customer becomes aware, if at all, and the plausible customer impact;
- the professional criterion being taught or assessed; and
- whether the assessment gives away the answer or contaminates independence.

Do not generalize one spelling example into a universal Amadeus rule. Names, document matching, ticket issuance, correction, and airline acceptance may depend on the specific carrier, market, workflow, and policy. If the behavior or consequence has not been verified, keep the case as a research hypothesis or omit it from high-stakes assessment.

## 58. Questions for reviewers and future validation

Every AI reviewer and practitioner reviewer should assess:

- Does the current product distinguish GDS command success from customer/task correctness and professional correctness? Show exact repository evidence or state that this is unverified.
- Which system-accepted mismatches occur in real reservation/ticketing work, and which are merely hypothetical? Gather evidence from job-task analysis, experienced agents, authorized training environments, and verified airline/GDS rules.
- Which errors should be caught before finalization, which may only surface later, and what checks are professionally expected?
- How can scenarios preserve authentic system behavior while allowing the independent evaluator to know that an accepted action was wrong for the task?
- How can practice provide useful feedback without turning every realistic error into an immediate warning, and how can assessment remain free from instructional leakage?
- How should delayed discovery, customer awareness, customer impact, and recovery be modeled without artificial dissatisfaction or invented consequences?
- What is the smallest set of verified cases that proves the learning value of this scenario family over command-only exercises?

## 59. Current status of this idea

**Status: strategic proposal / exploratory scenario-design direction; not an approved implementation decision.** The user considers this idea valuable for increasing realism and improving Customer Service, Scenario Bank, and assessment quality. It should be included in the pending Claude review and the comparative review with Gemini and the prior consultation. It does not authorize code changes, changes to the canonical decision log, or changes to D92/D97. The proposed Scenario Bank organization is developed separately in Part XIV and remains equally exploratory.

Its central principle is:

**A system can accept an action that is professionally wrong. DEIXEN must be able to teach and assess that distinction without falsifying the system's behavior.**

---

**End of brief.**

---

# PART XIV — EXPLORATORY SCENARIO BANK ORGANIZATION: PROFESSIONAL WORK SECTIONS AND MULTIPLE DAILY-WORK CASES

## 60. The user's proposed organization

The user proposes that Scenario Bank should not feel like a flat list of unrelated simulations. Instead, it should be organized into **clear sections representing recognizable areas of day-to-day reservation, ticketing, and travel-service work**, with multiple cases inside each section.

The intention is that a learner can understand what kind of professional work an area represents, then encounter different cases that exercise the relevant knowledge and skills. Cases should feel like situations a reservation or travel-service employee may genuinely meet—not arbitrary command puzzles written only to test syntax.

This is a product-organization hypothesis to evaluate, not a final taxonomy or authorization to create new screens. The final section names and boundaries must follow evidence from job-task analysis, target-market research (Saudi Arabia, Oman, and the UAE), employer role descriptions, practitioner interviews, and verified operational references. Similar job titles do not necessarily mean identical responsibilities across employers or markets.

## 61. Illustrative professional-work sections

The following is a **starting map for research and critique**, not a claim that every employer requires all of these duties or that this is the final navigation structure:

1. **Customer inquiry and needs discovery** — understanding the request, identifying missing information, clarifying ambiguity, reconciling conflicting preferences, and confirming priorities or constraints.
2. **Search, options, and professional advice** — exploring suitable alternatives, comparing relevant differences, explaining trade-offs, and ensuring the recommendation matches the customer's stated needs.
3. **New reservation and booking quality** — creating and reviewing a reservation against the customer's confirmed choices, with attention to completeness and accuracy.
4. **Passenger information and travel-document accuracy** — entering and checking passenger details against the authoritative information supplied for the case. The exact data fields and rules must be validated for the relevant workflow and market.
5. **Fare quotation, conditions, and confirmation** — explaining the verified price and applicable conditions, clarifying restrictions or trade-offs, and obtaining informed customer confirmation before proceeding where required.
6. **Ticketing, issuance, and final verification** — carrying out the relevant authorized process and checking the resulting record and documents against the task requirements. The exact workflow and prerequisites must come from verified references.
7. **Changes and reservation servicing** — handling customer-requested changes and related decisions, subject to verified availability, fare conditions, carrier rules, and office procedures.
8. **Cancellation, refunds, and related cases** — understanding the customer's request, checking the relevant policy and conditions, explaining verified options, and following the applicable process. Do not invent refund/void rules or deadlines.
9. **Additional services and special requests** — handling relevant requests such as seats, baggage, meals, assistance, or other services only where the target role and verified system/policy scope support them.
10. **Disruption, exceptions, and service recovery** — responding to changed circumstances or service problems, clarifying what is known, identifying valid options, communicating limitations, and escalating when required.
11. **After-sales and customer follow-up** — confirming what has actually been completed, answering follow-up questions, handling unresolved matters, and closing the task responsibly.

These sections may later be combined, renamed, split, or removed. For example, a specific employer may combine quotation and ticketing responsibilities, while another may assign them to different roles. The purpose is not to force one universal travel-agency workflow onto every learner; it is to discover a useful, evidence-based structure that fits the intended job pathways.

## 62. A dedicated collection for “system accepted, professionally wrong” cases

The user specifically suggests that the cases discussed in Part XIII may deserve a visible section/collection of their own. This deserves serious consideration.

A strong candidate is a dedicated Scenario Bank collection with a working title such as **“Accepted by the System — Wrong for the Task”** or **“When System Success Is Not Task Success.”** The final wording should be chosen only after testing whether beginners understand it immediately.

This collection should contain multiple cases in which:

- the learner's action is accepted by the operational system as verified for that specific case;
- the action nevertheless conflicts with the customer's confirmed request, the source information, a task constraint, or a verified professional procedure;
- the simulator allows the actual system behavior to occur rather than fabricating a rejection;
- the scenario/evaluation layer independently recognizes the mismatch;
- the defect is revealed at a plausible time, based on who could reasonably notice it and what information is available; and
- the learner must prevent, detect, explain, recover from, or escalate the issue as appropriate to the case.

This should not become an isolated silo. The same failure pattern should also appear, where valid, **inside the relevant day-to-day work sections**. For example, a passenger-data case may include a source-document mismatch; a search/advice case may include an option that is technically selectable but inconsistent with a confirmed customer constraint; and a change or after-sales case may include an accepted action that does not achieve the customer's intended outcome. Each example must be individually verified rather than assumed to work this way in Amadeus.

Therefore, a promising organization is a combination of:

- **work-domain sections** that show what area of the job the case belongs to; and
- **cross-cutting case collections/tags** that show what kind of professional challenge or failure pattern the learner is facing.

The dedicated “accepted but professionally wrong” collection can make this important skill family discoverable, while tags allow the same design principle to be applied across multiple work domains without duplicating the same case or creating artificial boundaries.

## 63. Multiple cases within each section: vary the work situation, not just the names

Each professional-work section should eventually contain multiple genuinely different cases. Merely changing passenger names, dates, destinations, or numbers while keeping the same reasoning and action sequence does not create meaningful transfer.

Illustrative case variations may include:

- a clear, complete, routine request;
- a request with missing information that must be clarified;
- ambiguity or conflicting details that should not be guessed;
- multiple customer priorities requiring a reasoned comparison;
- a customer changing a requirement partway through the task;
- a selected option that conflicts with an earlier stated constraint;
- a system-rejected action with an authentic, verified response and a recovery path;
- a system-accepted action that is inconsistent with the customer's request or source information;
- a defect that should be caught at a pre-completion check;
- a latent discrepancy that is revealed later through a plausible checkpoint;
- a service problem requiring explanation, recovery, or escalation; and
- a case in which the professionally correct action is to pause, ask, verify, or decline to proceed until a material uncertainty is resolved.

Not every section needs every variation. The scenario author should select variations that actually occur in that work domain and are supported by evidence. A case should not be made harder by adding unrelated obstacles simply to increase difficulty.

## 64. A consistent case blueprint across the Bank

To make sections coherent without making all cases feel identical, each case could use a common authoring/review blueprint:

- **Work domain:** the section to which the case belongs.
- **Task purpose and expected outcome:** what the employee is responsible for accomplishing.
- **Customer/context profile:** the role-relevant information the customer has and what they can reasonably know.
- **Source of truth:** the customer's confirmed request, documents, constraints, and any authoritative operational reference.
- **Known, missing, ambiguous, and conflicting information:** what the learner can see, what must be asked, and what must not be guessed.
- **Operational scope:** which actions the simulated GDS workflow supports, and which outputs/state transitions are verified.
- **Professional decision points:** where the learner must clarify, compare, advise, confirm, pause, verify, or escalate.
- **Possible action outcomes:** authentic system rejection, verified system acceptance, or an unresolved/unsupported action that must not be simulated as fact.
- **Error and discovery design:** whether a mismatch is visible immediately, detectable through an expected check, or latent until a plausible later event.
- **Customer experience:** what the customer perceives and how they plausibly respond; never make the customer omniscient.
- **Recovery and escalation:** only the actions and consequences supported by verified procedures.
- **Evidence criteria:** the observable behaviors and task outcomes the case is intended to teach or assess.
- **Support/assessment eligibility:** whether the case is a demonstration, supported practice, integrated practice, independent assessment, or a delayed/transfer variant.
- **Prerequisites and complexity:** what the learner should already have learned and what makes this case more demanding.
- **Verification provenance:** the reference, authorized environment, practitioner review, and date/version supporting each operational claim.

This blueprint is a proposed authoring standard for research. It is not a requirement to show every field to the learner or place all case information on one screen.

## 65. How case sections connect to the five DEIXEN areas

The proposed Bank organization must preserve the current area responsibilities unless formal evidence and governance review justify a change:

- **Learning** teaches the underlying knowledge and subskills, including Customer Service skills. It may point learners toward relevant work domains without turning every lesson into a full scenario.
- **Scenario Bank** organizes the cases, their work-domain section, status, purpose, prerequisites, variants, verification state, and evidence intent. It is the library/discovery layer, not a second operational terminal.
- **Terminal** remains where relevant GDS work is executed, including Scenario Mode under D92. Customer conversation and professional decisions may surround the operational steps, but this proposal does not move execution out of Terminal.
- **Assessment** may draw from assessment-eligible case families in the Bank, but an independent attempt must retain the isolation required by D97. The assessed variant should not simply be a familiar case whose answer has already been rehearsed.
- **Growth** records what the learner demonstrated across work domains and conditions, including independence, prevention, detection, verification, recovery, and transfer. It must not turn section completion into a claim of job readiness.

The same professional-work family may support learning and practice through one set of cases and independent assessment through a protected, sufficiently distinct variant. Reuse must be designed carefully so prior exposure does not contaminate the evidence of independent performance.

## 66. Progression within and across sections

The learner should not be sent into every section or case at once. A possible progression to test is:

1. **Foundations:** understand the purpose and vocabulary of one work domain; observe a clear worked example.
2. **Supported case:** complete a routine case with explicit guidance and verified feedback.
3. **Variation:** handle a structurally different case involving missing details, a changed preference, or a relevant decision.
4. **Integrated case:** connect Customer Service behavior with the appropriate operational work and final verification.
5. **Reduced-support case:** receive less prompting and demonstrate more self-checking and diagnosis.
6. **Independent case:** handle a protected case variant without Coach, hints, Ghost, or instructional rescue.
7. **Delayed/transfer case:** return later to a structurally different example to test retention and transfer.

This sequence is illustrative. Actual prerequisites and progression should be determined by what the learner has been taught and the evidence they have demonstrated—not by simply marking a lesson complete or unlocking the next section through a game-like level system.

## 67. Questions for Claude, Gemini, and practitioner reviewers

Reviewers should explicitly evaluate:

- Is organizing the Bank around recognizable day-to-day professional work domains clearer and more useful than a flat list, a command taxonomy, or a lesson-based catalogue?
- Which proposed sections reflect genuine recurring tasks in entry-level roles in Saudi Arabia, Oman, and the UAE? Which are too broad, too narrow, role-dependent, or unsupported?
- Should “system accepted, professionally wrong” be a dedicated collection, a cross-cutting tag, or both? What is the simplest discoverable UX without creating duplicate cases?
- What are the highest-frequency and highest-consequence cases in each verified work domain, and which are suitable for beginners?
- Which cases require real/authorized Amadeus training-environment verification, airline policy evidence, or practitioner validation before inclusion?
- How can the Bank provide multiple meaningful cases without generating superficial variations or an unmanageable authoring burden?
- How should a single case family create supported practice, a structurally distinct independent assessment variant, and delayed transfer evidence while preserving D97?
- Does this organization help the learner understand professional growth, or does it risk overwhelming beginners with a large catalogue? What should be progressively revealed?

## 68. Current status of the Scenario Bank organization proposal

**Status: strategic proposal / taxonomy hypothesis; not an approved information architecture, product-area change, or implementation decision.** The user wants multiple sections based on recognizable daily work, each containing several cases, and considers a dedicated collection for system-accepted-but-professionally-wrong cases potentially valuable. The proposal should be included in the pending Claude report comparison and reviewed against Gemini, the prior consultation, current repositories, verified references, and practitioner evidence.

Do not implement the section map, rename Scenario Bank, add a sixth top-level area, change D92/D97, or modify code/governance based only on this discussion. First validate the work domains, case frequency, learner value, terminology, complexity, and navigation through research and prototype testing.

The guiding principle is:

**Scenario Bank should organize the learner's practice around recognizable professional work—not merely around commands—and give each work domain multiple verified cases that reveal whether the learner can handle the task correctly, not just whether the system accepts an entry.**

---

**End of brief.**


---

# PART XIII — INTEGRATED PRODUCT, UX/UI & BRAND DEVELOPMENT PHILOSOPHY

**Status:** Approved strategic working principle as of 6 November 2026. This section records the user's approval to organize the work through one connected vision and specialized companion documents. It does not approve a specific visual identity, color, logo, screen design, or unvalidated product feature.

## 43. One connected product, developed through connected disciplines

DEIXEN's product logic, user experience (UX), interface design (UI), product design language, and brand identity must not be treated as isolated projects or as a sequence in which visual design is added only after implementation is complete.

They are distinct disciplines with explicit responsibilities, but they must inform and improve one another throughout product development.

- **Product logic and learning architecture** define what DEIXEN is intended to help the learner do, why each capability exists, and what professional outcome it supports.
- **UX strategy and experience architecture** define how learners understand, navigate, and complete those activities, including the relationship between areas, tasks, information, assistance, practice, and assessment.
- **UI and product design language** define how those experiences are expressed visually and interactively: hierarchy, layout, typography, spacing, components, states, motion, themes, and content presentation.
- **Brand strategy and visual identity** establish the distinctive character of DEIXEN and the principles that make its expression recognizable and coherent.

The disciplines are separate in scope and documentation, but connected in discovery, design, validation, and iteration.

## 44. Design from real product needs, not generic prompts or visual trends

Do not begin by asking an AI system or designer to invent a generic "modern professional dashboard" or an abstract identity without sufficient product context. Such prompts tend to reproduce familiar templates and generic logo conventions.

Start from:
1. The real purpose and constraints of the product.
2. The learner's actual tasks and decisions.
3. The information needed at each point.
4. The user's context, skill level, and likely errors.
5. The intended outcome and evidence of successful use.
6. Relevant visual and interaction references, analyzed for the qualities that make them effective.

References are benchmarks for design quality and specific qualities—not templates to copy. Each reference must be decomposed into transferable principles (for example, content organization, typography, visual hierarchy, motion, depth, color use, or component behavior). The resulting DEIXEN solution must remain original and fit its own workflows.

## 45. UX decisions can shape visual quality

A better interaction model can produce a better visual composition, not merely a more usable one.

For example, placing Terminal hints in a contextually connected position near the command-entry area may make their relationship to the learner's immediate task clearer and create a more coherent interface than placing them in a detached area. This is an illustrative design observation, not a blanket rule that hints must always be placed there; the solution must be tested across screen sizes, input methods, and learning states.

Therefore, UI should not be treated as decoration applied to a finished UX. Interaction, information hierarchy, layout, and visual expression should be explored together. A UX improvement may change the layout; a UI prototype may reveal a usability problem; a usability test may reveal a gap in product logic.

## 46. Product maturity and design timing

Avoid locking the full UI or visual identity while major product logic, task flows, or planned capabilities remain unclear. Premature design can create rework when the product's actual information needs and interactions become visible.

However, do not wait for the entire product to be implemented before doing UX/UI work. Design is also a discovery and validation tool.

Preferred approach:
- Establish sufficient clarity about the product purpose, users, core tasks, and key workflows.
- Explore UX and UI in parallel using representative end-to-end workflows and realistic content.
- Prototype and test early enough to discover problems before implementation becomes expensive.
- Mature the shared design language as recurring patterns become clear.
- Finalize identity and system-wide visual decisions only after testing them against the real product's needs, including both Dark and Light themes.
- Continue iterating as new product capabilities are validated.

## 47. Reference direction for product design exploration

The user has identified three important product-design references, each for different qualities. These are reference directions, not decisions to copy their interfaces.

- **Microsoft:** information organization, composition, clarity, hierarchy, and handling of broad product functionality.
- **Samsung:** contemporary visual sophistication, detail, depth/layers, motion, and interaction quality.
- **Higgsfield:** distinctive visual presence, strong content/tool presentation, and the use of a recognizable accent color to create product character.

The intended approach is to learn from the different strengths and combine them into an original DEIXEN design language. Do not assume the references should contribute equally to every screen or discipline.

The accent color remains **open**. Higgsfield's fluorescent accent is an example of a distinctive color strategy, not a DEIXEN color selection. Do not record fluorescent green or any other accent as approved without a separate exploration and approval. Dark and Light themes must both be considered as first-class experiences.

## 48. Coherence without uniformity

DEIXEN should feel like one coherent product, but not every area should use the same screen composition or interaction pattern.

The five product areas have different responsibilities. Their interfaces should reflect those responsibilities while sharing appropriate foundations such as typography, spacing logic, component behavior, color semantics, motion principles, and accessibility standards.

Connect the underlying context, task progression, and evidence where useful; do not force every responsibility onto one screen. A shared design language is not the same as identical layouts.

## 49. Validation and quality controls

Do not accept a design because it looks attractive in a static mockup or because its concept sounds intelligent.

Evaluate it against:
- task completion and clarity for beginners;
- cognitive load and information prioritization;
- discoverability and consistency;
- error prevention, recovery, and feedback;
- keyboard, pointer, touch, and responsive behavior as applicable;
- readability and accessibility in Dark and Light themes;
- visual distinctiveness and craft;
- consistency across the five product areas without forced uniformity;
- behavior with realistic, dense, and changing content;
- maintainability as the product grows.

AI-generated proposals must be critically reviewed for generic patterns, superficial decoration, inconsistent details, and unsupported assumptions. References should guide quality, not excuse imitation.

## 50. Documentation and decision boundaries

This integrated philosophy is a strategic working principle. It does not itself approve:
- a final logo, icon, wordmark, typeface, or brand color;
- a final Dark or Light theme palette;
- a complete navigation model or screen layout;
- a specific Terminal hint placement;
- implementation of any unvalidated workflow or feature;
- changes to existing canonical governance decisions in `07`.

Detailed work belongs in the companion documents:
- `02 — UX Strategy & Experience Architecture`
- `03 — Product Design Language`
- `04 — Brand Strategy & Visual Identity`
- `05 — UX Flows, UI Specifications & Design System` (to be developed when workflows and patterns are sufficiently mature)

The master product strategy remains the source for product purpose and learning architecture. Companion documents must link back to it and clearly identify dependencies, approved decisions, open questions, and hypotheses. They must not silently override it.

---
