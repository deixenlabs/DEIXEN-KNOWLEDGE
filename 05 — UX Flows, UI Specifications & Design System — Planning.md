---
document: DEIXEN UX Flows, UI Specifications & Design System — Planning
version: 0.3
prepared: 2026-11-06
status: Planning only; aligned to Unified Experience & Runtime Architecture v0.2 and First Integrated Professional Task Map v0.1
authority: No implementation specification or authorization
---

# DEIXEN — UX Flows, UI Specifications & Design System
## Planning Document

## 1. Why this document exists

This is the future execution layer between product strategy, the unified experience/runtime architecture, UX strategy, product design language, and implementation.

It should contain concrete, validated descriptions of flows, screens, components, interaction behavior, content states, and acceptance criteria. It must not become a speculative screen catalogue before the relevant professional tasks have been researched.

## 2. Required inputs before a flow can be specified

A specification may begin when the team can identify:

- the professional task and intended outcome;
- the learner profile and relevant prerequisites;
- the case/package and any meaningful variants;
- the source of truth for customer facts and operational behavior;
- the relevant skills and observable behaviors;
- the task phases, branches, stop/pause/escalation conditions;
- the support policy for the intended mode;
- what evidence is captured and what it may legitimately support;
- realistic content and edge cases;
- relevant canonical decisions and their current status.

Unknowns should be labelled. Do not silently fill them with model-generated Amadeus behavior or assumptions about professional practice.

## 3. Planned specification layers

### A. End-to-end learner flow

For each flow, record:

- entry point and learner context;
- learner goal and task outcome;
- sequence and branching;
- how Home, Learning, Terminal, Scenario Bank, and Growth are involved;
- relevant shared capabilities (Ghost, Coach, Customer Interaction, Task Runtime, Assessment/Evidence);
- what context carries between stages;
- where the learner can pause, retry, return, or leave;
- how the flow concludes and what the next useful action is.

### B. Case-to-run contract

Record the case family, package/variant version, task objective, visible and hidden facts, disclosure rules, operational scope, verified references, support policy, task-run identity, session requirements, event triggers, completion/stop criteria, and assessment eligibility.

The case package is a definition; a scenario instance is one instantiated case; a task run is one learner attempt. Do not treat these as interchangeable.

### C. Screen and interaction specifications

For each screen/workspace, record:

- purpose and responsible capability;
- information hierarchy and authoritative source for every displayed value;
- primary/secondary actions and state transitions;
- interaction behavior for keyboard, pointer, and touch;
- loading, empty, invalid, error, interruption, recovery, and completion states;
- responsive behavior across mobile, tablet, and desktop;
- accessibility, bilingual, RTL/LTR, and reduced-motion requirements;
- how user input and system output remain distinguishable.

### D. Mode and support policy

Specify differences among lesson, Ghost, supported practice, reduced-support practice, scenario practice, and independent assessment. State exactly what Coach/hints/customer dialogue may do in each mode and what affects evidence qualification.

### E. Assessment and evidence specification

Specify:

- fresh session/run and clean operational-state requirements;
- how distinct/unpractised case variants are selected;
- what exposure or assistance invalidates qualification;
- which observed events map to criteria;
- which evidence is recorded versus calculated;
- how completed-but-nonqualifying attempts are represented;
- when feedback can be shown;
- how Growth summarizes evidence without scores or unsupported claims.

### F. Design system

Define typography, spacing, layout rules, semantic color roles, components and variants, state feedback, iconography, motion, and Dark/Light theme behavior only after recurring interaction patterns have been tested.

## 4. Cross-workspace integrity rules

- Scenario Bank selects/defines the case; Terminal executes the active run.
- Task Runtime coordinates context; it must not duplicate operational truth.
- Customer Interaction, Coach, Terminal/System, Assessment, and Growth retain distinct semantic roles.
- The Terminal operational record remains LTR/monospace and contains only learner entries, Amadeus output, and the one permitted labelled DEIXEN training line.
- Customer dialogue, case narrative, Coach explanations, hints, and debriefs remain outside the operational record.
- Assessment debrief is withheld until the attempt is closed and the evidence snapshot secured.
- No UI pattern may imply that a completed or assisted activity proves independent competence.

## 5. Example validation case: Terminal hint placement

A possible pattern is to connect hints contextually to the command-entry area. Before standardizing it:

- test whether the relationship is immediately understood;
- verify that it does not obstruct input or keyboard use;
- test narrow and wide layouts;
- confirm that the hint is not confused with Amadeus output or the DEIXEN training line;
- verify that independent assessment removes instructional help as required.

This is an example, not a predetermined layout rule.

## 6. Architecture validation cases to prototype

At minimum, before implementing a broad new experience, validate:

1. a Ghost demonstration in which narration explains meaningful output without contaminating the Terminal record;
2. a Scenario Bank case launch into Terminal scenario mode with context preserved and no duplicated case truth;
3. a case that moves between customer dialogue and operational execution;
4. a scenario that does not require a GDS command, to test D92 presentation without artificial operations;
5. an independent-assessment run that proves the isolation and qualification rules;
6. a Growth view that clearly distinguishes demonstrated evidence from untested areas.

These are validation cases, not a mandate to build all six immediately. Prioritize the smallest set that resolves the highest-risk architectural questions.

## 7. Traceability and acceptance

Every specification should link to:

- master strategic requirement;
- unified architecture capability and boundary;
- UX flow and learner goal;
- case package/variant and source-of-truth owner;
- related skill/competency and observable behavior;
- relevant canonical decision (including D92/D97 where applicable);
- support and evidence rules;
- design-language rule;
- usability/learning test evidence;
- owner approval and specification version.

Acceptance criteria should test behavior, not only appearance. Include negative tests for truth leakage, duplicated state, unsupported responses, help during assessment, and false evidence qualification.

## 8. When detailed specifications are ready

Create detailed specs when the task model, case data, relevant operational scope, UX flow, and major edge cases are understood. A prototype can be used to discover those things; it need not wait for every future product area to be complete.

Do not design the entire future product at once. Use one validated vertical slice to reveal recurring patterns, then expand based on evidence.

## 9. First integrated task map as the pre-specification test

Use `08 — DEIXEN First Integrated Professional Task Map.md` as the first end-to-end architecture test. It is deliberately a bounded reservation task for one adult traveller, one passenger, one segment, and one fare context within the currently verified scope. The itinerary is supplied and customer-confirmed before operational booking; the exact missing customer fact and required operational fields must be selected only after Verified Reference and practitioner review.

Before turning this map into screen specifications:

- validate the actual operational steps and every command/response/state transition against the current approved Verified Reference;
- have a reservation/ticketing practitioner review the case and its stop/recovery branches;
- prototype customer disclosure and clarification with representative beginner language;
- demonstrate the case-to-run hand-off and separation of Case Package, Task Run, Conversation State, and Operational Session;
- test system acceptance versus task correctness;
- record Coach availability/exposure and prove that it cannot contaminate independent assessment;
- inspect the event sequence to determine exactly which observations support which evidence claims;
- test the learner flow on mobile and desktop without deciding that all workspaces must be visible simultaneously.

The task map is not a final content specification, a fixed data schema, or implementation authorization. Search/advice, live availability, ticket issuance, payment, exchange, cancellation, and broader service workflows remain outside its first bounded test unless separately verified and approved.

## 10. Governance

This planning file and the companion architecture proposal do not authorize code changes, canonical decision changes, new Amadeus behavior, a sixth product area, backend work, or a full work-shift simulator. Record unresolved questions and obtain explicit approval through the project process. Implementation work requires a separate authorized task and acceptance criteria.
