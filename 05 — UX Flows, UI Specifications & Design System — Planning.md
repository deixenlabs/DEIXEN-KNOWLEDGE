# DEIXEN — UX Flows, UI Specifications & Design System
## Planning Document

**Status:** Planning only. This is not a completed implementation specification or authorization to change the app.

## 1. Why this document exists

This is the future execution layer between the UX strategy/product design language and implementation. It should contain concrete, validated descriptions of flows, screens, components, and interaction behavior.

Do not fill it with speculative screens before the relevant workflows have been researched and tested.

This document also defines the working method for turning UX, UI, and brand exploration into comparable design proposals, validated specifications, and implementation-ready handoffs. It does not own the authority or final decisions of the Operating Constitution or Decision Register.

## 2. When to develop it

Create detailed specifications when:
- the relevant product task and intended outcome are sufficiently understood;
- the UX flow has been mapped;
- realistic content and edge cases are known;
- key usability questions have been tested or explicitly recorded;
- the design pattern is stable enough to specify.

Exploratory prototypes may be created earlier when they help resolve uncertainty. Clearly label them as experiments, not approved product specifications.

## 3. Planned contents

### UX flow specifications
- user goal and starting context;
- step-by-step flow;
- decisions and branching;
- information required at each step;
- support available and when it fades;
- error and recovery paths;
- completion conditions;
- assessment boundaries;
- evidence captured.

### Screen and interaction specifications
- screen purpose;
- information hierarchy;
- primary and secondary actions;
- component behavior and states;
- keyboard, pointer, and touch behavior;
- responsive behavior;
- accessibility requirements;
- empty, loading, error, and success states.

### Design system
- typography and hierarchy;
- spacing and layout rules;
- color roles and theme tokens;
- components and variants;
- interaction feedback;
- motion rules;
- iconography;
- Dark and Light theme behavior.

## 4. Example validation case: Terminal hint placement

A possible pattern is to connect hints contextually to the command-entry area. Before specifying it as a standard:
- test the learner's understanding;
- verify that it does not obstruct input;
- test narrow and wide layouts;
- confirm the hint is not confused with Amadeus output or the DEIXEN training line;
- confirm hints are unavailable in independent assessment where required.

## 5. Traceability

Every specification should link to:
- the relevant product requirement or strategic principle;
- the UX flow;
- the relevant design-language rule;
- any applicable canonical decision;
- test evidence and approval status.

## 6. Governance

Do not treat this planning file as authority to modify code, canonical decisions, or Amadeus behavior. Record unresolved questions and obtain explicit approval through the project process.

## 7. Multi-tool visual design collaboration

### 7.1 Current working environments

The current design workflow uses two complementary environments:

| Environment | Current model pairing | Working contribution |
|---|---|---|
| Google AI Studio | Gemini / Argon 4 | Independent visual exploration, design concepts, application prototypes, and iterative visual experimentation |
| Claude Design | Claude Opus 5.5 | Independent visual exploration, design concepts, interface directions, and iterative refinement |

Neither environment is designated as the sole design authority or presumed superior. Both should be given meaningful opportunities to solve the same design problem. The exact capabilities available in each environment should be checked at the time of the task; do not assume a feature exists merely because it existed in an earlier session.

The model/version pairings describe the current working setup and may change. The durable principle is complementary, independent exploration under shared project context.

### 7.2 Shared brief, independent first pass

Both environments should receive the same essential brief:
- the actual product/brand objective;
- relevant current project sources;
- target user and representative tasks;
- known constraints and open decisions;
- quality and evaluation criteria;
- required output and level of fidelity;
- what is read-only, what may be prototyped, and what is explicitly not authorized.

Allow each environment to explore independently before sharing the other environment's output. Do not force the same visual concept, prompt wording, layout, or number of alternatives. The shared brief aligns the objective, not the creative solution.

### 7.3 Cross-review and iterative synthesis

After the first independent proposals are available:
1. Preserve and document the original directions.
2. Compare visual outcomes against the same evaluation criteria.
3. Identify strengths, weaknesses, risks, and missing aspects in each.
4. Ask each environment to critique the other where that adds value.
5. Explore improvements and genuinely new alternatives.
6. Combine elements only when they strengthen the coherence and purpose of the result.
7. Keep distinct options alive when evidence does not justify premature convergence.

Do not average two designs, copy one tool's output into the other, or choose a winner based on model reputation. Cross-review should improve the work, not erase the value of independent exploration.

### 7.4 Owner decision and design status

All design outputs are proposals until the owner approves a direction. The owner retains final authority over brand identity and material visual direction.

Distinguish:
- exploration;
- candidate direction;
- refined proposal;
- owner-approved direction;
- validated specification;
- implemented design;
- implementation verified against the specification.

A design can be owner-approved and still require usability, accessibility, responsive, or implementation validation. Approval of a visual direction does not automatically authorize code or repository changes.

### 7.5 Evaluation

Evaluate proposals against the task and relevant design discipline, including:
- distinctiveness and originality;
- clarity of hierarchy and content relationships;
- usability for the intended user;
- realistic content density and edge cases;
- Arabic/English and RTL/LTR behavior where applicable;
- responsive behavior and relevant input methods;
- accessibility, contrast, focus, and reduced motion;
- consistency without forced uniformity;
- interaction quality and meaningful motion;
- feasibility, maintainability, and implementation fidelity.

Static visual appeal is not sufficient. Use realistic content, representative tasks, and interactive prototypes when they can answer meaningful questions.

## 8. Implementation handoff

After a direction and its required specifications are approved:
- Claude Code remains the primary implementation agent for approved software changes.
- Antigravity is a complementary development environment in the owner's workflow; its exact role in a task must be stated rather than assumed.
- The design handoff should include approved assets, typography and color decisions, tokens where applicable, layout rules, component behavior, interaction states, responsive behavior, accessibility requirements, source references, and unresolved items.
- The implementation team must not infer missing behavior from a screenshot.
- Any implementation deviation that changes the design intent, UX behavior, accessibility, or product contract must be surfaced.
- Verify the implemented result against the approved specification in the actual application.

Exploratory design environments must not modify the application repository or production code unless the owner separately authorizes that work.

## 9. Example handoff checklist

For each approved design package, record:
- the design objective and scope;
- the selected direction and why it was selected;
- the rejected or deferred alternatives and the material reasons;
- source files and approved references;
- assets and their formats;
- typography, color, spacing, and token decisions;
- component and interaction specifications;
- responsive and localization behavior;
- accessibility requirements;
- open questions and known limitations;
- owner approval status;
- implementation and validation status.

A package is not implementation-ready merely because it contains polished screenshots. It must communicate enough behavior and constraints for faithful implementation and verification.
