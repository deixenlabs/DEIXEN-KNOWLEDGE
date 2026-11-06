# DEIXEN — UX Strategy & Experience Architecture

**Status:** Working strategy document. The integrated UX/UI/brand development principle is approved; detailed flows and specific placements remain open until validated.

## 1. Purpose

Define how a learner understands, navigates, and completes work in DEIXEN. UX must help the learner focus on meaningful professional decisions rather than waste effort understanding the interface.

The goal is not to remove professional thinking. The goal is to remove avoidable interface confusion while gradually teaching the learner to handle real ambiguity, judgment, and responsibility.

## 2. UX principles

1. **Task-first clarity:** At every point, the learner should understand what they are trying to accomplish and why it matters.
2. **Progressive complexity:** Introduce concepts and responsibilities in a sequence the learner can build on. Do not expose a beginner to every complexity at once.
3. **Support that fades:** Assistance is available during learning and practice, then deliberately reduced. Independent assessment must remain independent.
4. **Contextual help:** Place guidance near the activity it supports when this improves understanding and does not obstruct the task.
5. **One coherent journey:** Learning, demonstration, guided practice, independent practice, scenarios, assessment, evidence, and continued growth should connect meaningfully.
6. **Distinct responsibilities:** The five product areas remain distinct where their jobs differ. Shared context does not require identical screens.
7. **Explain consequential outcomes:** Distinguish a system-accepted action from an action that fulfills the customer's request or professional task.
8. **Recovery matters:** Help learners understand how to detect, diagnose, communicate, and correct errors, not merely avoid them.
9. **Honest evidence:** Never imply that lesson completion, assisted success, or one correct result proves independent competence.
10. **Accessible and responsive:** Design for readable content and usable controls across relevant screen sizes and input methods.

## 3. The five areas and their UX responsibilities

- **Flight Deck:** orientation, current learning context, and a clear next step.
- **Learning:** explanations, foundations, demonstrations, and structured practice preparation.
- **Terminal:** operational execution and the primary place where scenario work is performed, subject to existing governance.
- **Scenario Bank:** discovery and selection of professional cases; it is not a second execution surface.
- **Growth:** evidence of demonstrated capabilities, areas needing more practice, and development over time.

Preserve the existing distinction that scenario execution belongs inside Terminal, while Scenario Bank is the case/library and status experience, unless a formal evidence-backed governance change is approved.

## 4. Three connected journeys

Design should understand and connect, without collapsing, these lifecycles:

- **Customer Journey:** inquiry, discovery, clarification, advice, choice, fulfillment, changes/problems, closure, and after-sales.
- **Professional/Learner Journey:** onboarding, foundations, supported practice, increasing responsibility, independent performance, and continued development.
- **Work Task Lifecycle:** the steps and outcome of one concrete professional task.

The interface should show the right context at the right time. Avoid showing every lifecycle detail simultaneously.

## 5. Support and independence

Potential learning progression to design and validate:

- Supported learning and demonstration.
- Guided practice with clear help.
- Practice with reduced or more selective help.
- Integrated scenarios with realistic choices and complications.
- Independent assessment without instructional hints or corrective coaching.
- Feedback after the assessment result is secured.

The customer's ordinary answers and facts are part of the scenario, not instructional hints. The Coach is separate from the simulated customer and must not leak answers into independent assessment.

## 6. Contextual interaction example: Terminal hints

A hint control may be more understandable when visually and spatially connected to the command-entry area than when detached elsewhere on the screen. This is a useful UX hypothesis because the hint supports the immediate act of composing an entry.

Do not treat this example as a universal placement decision. Test:
- whether the relationship is immediately understood;
- whether the controls obstruct the entry area or keyboard;
- how it behaves on narrow screens and touch devices;
- whether hints remain distinct from the operational record;
- whether independent assessment correctly removes instructional help.

## 7. Scenario discovery and organization

Scenario Bank may contain work-related categories, each with multiple cases. Categories should reflect recognizable professional task families, not arbitrary content buckets. A case may include customer context, requirements, missing or conflicting information, operational work, events, outcomes, and assessment criteria.

Potential categories and case structures remain subject to job-task research and verified Amadeus references. Avoid implying that every proposed category is already implemented.

## 8. UX validation

Test representative end-to-end tasks with beginners and, where possible, practitioners. Observe:
- where learners hesitate or misunderstand;
- whether they can find relevant information;
- whether the interface creates avoidable cognitive load;
- whether support is available in practice but absent in assessment;
- whether learners understand the difference between system acceptance and task correctness;
- whether they can recover from mistakes;
- whether the experience works with realistic content density.

Do not approve a flow only because it looks elegant in a diagram.

## 9. Open questions

- Which end-to-end work task should be the first UX prototype?
- What customer interaction is essential for that task?
- Which parts of the customer context should persist across screens?
- How should the interface reveal task constraints without giving away assessment answers?
- What information belongs in Terminal versus separate panels?
- Which mobile/tablet behaviors are in scope?
- Which scenario categories are supported by actual job-task evidence?

## 10. Boundaries

This document does not authorize code changes, new top-level product areas, changes to D92/D97 or other canonical decisions, or unverified Amadeus behavior. Specific flows must be reviewed and approved through the project's governance process.
