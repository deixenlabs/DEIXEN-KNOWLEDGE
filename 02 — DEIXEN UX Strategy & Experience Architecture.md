# DEIXEN — UX Strategy & Experience Architecture

**Status:** Owner-approved direction for the Home and Learning experiences (Decision 98, 2026-11-06). The high-level direction is approved. Detailed flows, screen compositions, interaction patterns, visual treatments, exact curriculum taxonomy, and implementation specifications remain subject to their own research, design, validation, and approval.

## 1. Purpose

Define how a learner understands, navigates, and completes meaningful learning and professional work in DEIXEN. UX should help the learner focus on sound professional decisions rather than spend effort deciphering the interface.

The goal is not to remove professional thinking. It is to remove avoidable interface confusion while gradually helping the learner handle real ambiguity, judgment, and responsibility.

DEIXEN must connect learning to demonstrated performance without treating lesson completion, simulator exposure, assisted success, or a correct final state as proof of independent competence.

## 2. Core UX principles

1. **Task-first clarity:** At every point, the learner should understand what they are trying to accomplish and why it matters.
2. **Learner-first orientation:** Start from the learner's current situation and the most useful next action; show the wider journey as context rather than overwhelming the learner with it.
3. **Progressive complexity:** Introduce concepts and responsibilities in a sequence the learner can build on. Do not expose a beginner to every complexity at once.
4. **Support that fades:** Assistance is available during learning and practice, then deliberately reduced. Independent assessment must remain independent.
5. **Contextual help:** Place guidance near the activity it supports when this improves understanding and does not obstruct the task.
6. **One coherent journey:** Learning, demonstration, guided practice, independent practice, scenarios, assessment, evidence, and continued growth should connect meaningfully.
7. **Distinct responsibilities:** The five product areas remain distinct where their jobs differ. Shared context does not require identical screens.
8. **Professional truth:** Distinguish a system-accepted action from an action that fulfils the customer's request and professional task.
9. **Recovery matters:** Help learners understand how to detect, diagnose, communicate, and correct errors, not merely avoid them.
10. **Honest evidence:** Never imply that lesson completion, assisted success, or one correct result proves independent competence.
11. **Accessible and responsive:** Design for readable content and usable controls across relevant screen sizes and input methods.
12. **Distinctive through usefulness:** Do not introduce unusual navigation or visual treatment merely to look different. Distinction must make the experience clearer, more useful, or more memorable without harming task performance.

## 3. The five areas and their UX responsibilities

The five-area architecture remains unchanged. The approved current user-facing name of the first area is **Home** in English and **الرئيسية** in Arabic; it replaces **Flight Deck / قمرة القيادة** as the current area name.

- **Home:** Personalized orientation. Helps the learner understand their current learning situation, the most useful next action, why that action is recommended, and where it fits in the wider professional-development journey.
- **Learning:** Curriculum discovery and learning. Gives the learner an understandable way to explore learning paths and courses, then enter a focused lesson experience for explanation, demonstration, and preparation for practice.
- **Terminal:** Operational execution and the primary place where practice and scenario work are performed, subject to existing governance. It remains the operational heart of DEIXEN.
- **Scenario Bank:** Discovery and selection of professional cases. It is not a second execution surface; a scenario runs as a mode inside Terminal under the existing decision.
- **Growth:** The evidence-led view of demonstrated capabilities, areas needing more practice, and development over time. It must not duplicate Home's brief orientation summary.

Assessment remains a mode within the existing learning and operational journey, not a sixth top-level area.

## 4. Home — personalized orientation

### 4.1 Primary job

Home should answer, in this order:

1. **Where am I now?** Show the learner's relevant current context: what they are learning or practising, and the stage that matters now.
2. **What is the best next step for me?** Present one clear, useful next action based on the learner's actual state and the approved learning/work sequence.
3. **Why this step?** Explain briefly why it is recommended and what it will help the learner develop or resolve.
4. **What is my current focus?** Make the immediate learning or practice focus understandable without reproducing the full lesson or the full record of evidence.
5. **Where does this fit in my wider journey?** Offer a concise sense of the broader professional-development direction and the next meaningful milestone, without turning Home into a large curriculum map or a readiness dashboard.

The recommendation must reflect genuine learner state, available curriculum content, and the relevant professional task. Home must not invent progress, infer competence from exposure, or present an unsupported readiness conclusion.

### 4.2 A compact view of the wider journey

Home should give the learner enough context to understand that today's action contributes to a longer professional journey. This may include the current learning path or course and a restrained indication of what comes next.

The wider journey is supporting context, not the main content of the page. It must not compete with the immediate next action or reproduce Learning's catalogue and Growth's evidence review.

Do not turn this into a decorative progress meter, percentage, streak, leaderboard, or generic dashboard grid.

### 4.3 Adapt to the learner's situation

The orientation should be useful across materially different learner states, including:

- **First visit / beginner:** make the starting point and first useful action clear; do not expose the entire product or curriculum at once.
- **Returning learner:** restore continuity and make the next action understandable without forcing the learner to rediscover where they were.
- **Learner needing reinforcement:** surface an appropriate opportunity to revisit or practise a weak area rather than automatically pushing new content.
- **After a practice, scenario, or assessment event:** reflect only what the event and the existing evidence rules actually establish, then guide the next step.
- **No suitable next action available:** say so honestly and provide a meaningful route to explore Learning or review Growth; do not manufacture an action or display a false affordance.

These are experience requirements, not approval of a particular recommendation algorithm or visual layout.

### 4.4 Boundaries

Home is not:

- a marketing homepage;
- a conventional dashboard that places many unrelated cards and metrics on one screen;
- a full curriculum catalogue;
- the detailed Growth/evidence report;
- a replacement for Terminal or a place to perform operational work;
- a claim that the learner is job-ready merely because a path, lesson, or task is complete.

## 5. Learning — discovery first, focused learning second

Learning should support two connected experiences: **Learning Overview / Discovery** and the **focused Lesson Experience**. The overview helps the learner understand and choose what to learn; the lesson helps the learner concentrate on one learning objective at a time.

### 5.1 Learning Overview / Discovery

The first Learning experience should make the learning offer understandable before asking the learner to open an individual lesson. It should help answer:

- What learning paths and courses are available?
- What will I learn, and why does it matter in professional work?
- What knowledge or skill does this learning develop?
- What should I understand before starting it?
- How does it connect to relevant Terminal practice, scenarios, and later evidence?
- What is available now, what is planned, and what is not yet part of the current learning offer?

Use clear groupings and progressive disclosure. Do not present every lesson, command, and detail at once, and do not replace the overview with an enormous map that is difficult to scan.

### 5.2 Curriculum organization

At the experience level, the intended discovery hierarchy is:

**Learning paths / tracks → courses → modules → lessons.**

This is the approved direction for making the curriculum discoverable. The precise curriculum model, naming, grouping, prerequisite relationships, order, and content remain owned by evidence-based curriculum design and the relevant canonical curriculum sources. This UX decision does not create new curriculum content, settle competency-versus-command ordering, or authorize future content to appear as currently available.

The interface should communicate relationships and dependencies clearly, but must not invent prerequisite locks or access restrictions. Existing curriculum and lesson rules remain controlling until formally changed.

### 5.3 Focused Lesson Experience

After choosing a lesson, the learner should enter a focused experience built around that lesson's objective. It should support, as appropriate to the lesson:

- a clear statement of what the learner is expected to understand;
- plain-language explanation and necessary context;
- a worked example or demonstration;
- attention to important distinctions, likely misunderstandings, and professional consequences;
- a clear relationship to the relevant work task;
- a meaningful transition into the appropriate Terminal practice when the lesson's contract provides one;
- an understandable way to continue, revisit, or return to the Learning Overview.

Keep the learner focused on the current lesson. Do not make a long horizontal strip of every lesson or command the primary way to understand the curriculum. Navigation between lessons may remain available, but it should not overwhelm the teaching content or imply that moving through a list proves competence.

### 5.4 Learning does not equal competence

Completing or reading a lesson means the learner has completed that learning activity according to its rule. It does not, by itself, prove independent task execution, professional judgment, transfer to unfamiliar cases, or workplace readiness.

The experience must preserve the progression from learning and demonstration through guided practice, independent practice, scenarios, independent assessment, evidence, and continued development. The detailed learning mechanics and evidence rules remain owned by their existing canonical sources.

## 6. Three connected journeys

Design should understand and connect, without collapsing, these lifecycles:

- **Customer Journey:** inquiry, discovery, clarification, advice, choice, fulfilment, changes/problems, closure, and after-sales.
- **Professional / Learner Journey:** onboarding, foundations, supported practice, increasing responsibility, independent performance, and continued development.
- **Work Task Lifecycle:** the steps, decisions, branches, and outcome of one concrete professional task.

Home primarily orients the learner within the Professional / Learner Journey and the immediate next action. Learning organizes and teaches the knowledge and skills needed along that journey. Terminal handles operational execution. Scenario Bank exposes the learner to cases and variation. Growth communicates what the evidence supports.

The interface should show the right context at the right time. Avoid showing every lifecycle detail simultaneously.

## 7. Support, practice, assessment, and evidence

Potential experience progression, subject to the existing Learning Design and canonical contracts:

- Supported learning and demonstration.
- Guided practice with clear help.
- Practice with reduced or more selective help.
- Integrated scenarios with realistic choices and complications.
- Independent assessment without instructional hints or corrective coaching.
- Feedback after the assessment result is secured.
- Evidence-led review and an appropriate next development action.

The simulated customer's ordinary answers and facts are part of the scenario, not instructional hints. The Coach is separate from the simulated customer and must not leak answers into independent assessment.

Customer reaction or satisfaction must remain distinct from operational accuracy and professional judgment. An unhappy customer is not automatically evidence of learner failure, and simulated satisfaction cannot compensate for operational failure.

## 8. Booking Chain and task route

The Booking Chain / route representation describes the steps of a **specific operational work task**. It is not the curriculum map, the complete skill model, or the learner's entire professional journey.

Keep task workflow, curriculum structure, competency relationships, and learner evidence conceptually distinct:

- **Curriculum structure:** what the learner is meant to learn and in what learning grouping.
- **Competency / skill model:** what the learner can demonstrate, including where a skill is reused across lessons or work tasks.
- **Work-task workflow:** the operational sequence and branches for one task.
- **Learner evidence and development:** what has actually been demonstrated, under what conditions and with what degree of independence.

The Booking Chain's task logic and evidence meaning are not changed by this UX direction. Whether, where, and how its visual representation appears on Home or Learning is a detailed design question to be settled through realistic prototypes and testing. It must not be expanded into a crowded map of all curriculum content.

## 9. Scenario discovery and organization

Scenario Bank may contain work-related categories, each with multiple cases. Categories should reflect recognizable professional task families, not arbitrary content buckets. A case may include customer context, requirements, missing or conflicting information, operational work, events, outcomes, and assessment criteria.

Scenario execution remains inside Terminal under the current approved architecture. Scenario Bank remains a case-discovery and selection experience, not a parallel execution environment.

Potential categories and case structures remain subject to job-task research and verified Amadeus references. Avoid implying that every proposed category is already implemented.

## 10. Responsive, accessible, and coherent experience

Home and Learning must work across mobile, tablet, and desktop without assuming that the same composition is optimal at every size. Prioritize clear information hierarchy, realistic content density, readable Arabic and English, RTL/LTR correctness, keyboard and touch usability, and assistive-technology clarity.

Shared design foundations may be consistent across areas, but Home, Learning, Terminal, Scenario Bank, and Growth do not need identical page compositions. Visual identity, typography, color, motion, components, and final screen layouts remain governed by their relevant design sources and future design approval.

## 11. UX validation

Validate the experience with representative beginners and, where possible, working practitioners. Test at least these tasks:

- a first-time learner finding the correct starting point;
- a returning learner resuming after an interruption;
- a learner deciding what to study and understanding why it matters;
- a learner finding a lesson from a path or course;
- a learner completing a lesson and moving into the intended practice;
- a learner who needs reinforcement finding a meaningful next action;
- a learner reviewing evidence without mistaking lesson completion for competence.

Observe whether learners can explain where they are, what they should do next, why it matters, how the lesson connects to work, and where they can see what has actually been demonstrated. Also observe hesitation, misinterpretation, cognitive load, false affordances, responsive behavior, and accessibility.

Do not approve a flow only because it looks elegant in a diagram or static mockup. Use realistic content and end-to-end tasks.

## 12. Authority, status, and boundaries

This document records the approved high-level Home and Learning direction under Decision 98. It does **not**:

- add or remove a top-level product area;
- change Terminal's central operational role;
- move scenario execution out of Terminal or change Scenario Bank's role;
- change Growth's evidence responsibility;
- change the Learning Design's skill states, assistance rules, curriculum content, or evidence contracts;
- change the Amadeus Verification Standard or authorize unverified system behavior;
- change the Booking Chain's workflow or evidence semantics;
- approve a final visual identity, screen composition, component, or interaction design;
- authorize application-code changes or claim that the new experience has been implemented.

The current application still contains the earlier Flight Deck implementation and the existing single-lesson Learning experience. The code, translations, tests, and internal identifiers require a separate implementation task after the relevant detailed UX specifications are prepared and approved.

The exact curriculum hierarchy and detailed Home/Learning flows should be developed from real learner needs, job-task evidence, and usability testing. Where this document does not settle a detail, record it as open rather than filling the gap by assumption.
