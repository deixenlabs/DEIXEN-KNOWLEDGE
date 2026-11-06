# DEIXEN — Product Experience & Design Framework
## Document Index and Working Rules

**Purpose:** Explain how product strategy, UX, UI/product design language, and brand identity work together while remaining separately documented. This index also identifies where design collaboration methods and tool responsibilities are governed.

## The document set

1. **01 — Product Strategy, Learning Architecture & Partnership Goals**  
   The master source for DEIXEN's purpose, target users, learning model, professional work tasks, assessment philosophy, Growth evidence, strategic hypotheses, partnership ambitions, and integrated development philosophy.

2. **02 — UX Strategy & Experience Architecture**  
   Defines how learners move through DEIXEN, understand tasks, use support, practice, complete scenarios, and demonstrate independent performance.

3. **03 — Product Design Language**  
   Defines the visual and interactive language of the product: hierarchy, composition, typography, spacing, components, states, motion, depth, and Dark/Light themes.

4. **04 — Brand Strategy & Visual Identity**  
   Defines the brand's purpose, positioning, personality, logo system, wordmark, typography, color identity, visual exploration requirements, and brand applications.

5. **05 — UX Flows, UI Specifications & Design System**  
   The planning and execution-oriented layer for validated flows, screens, components, interactions, multi-tool visual exploration, design evaluation, and handoff to implementation. It should not be prematurely treated as a completed implementation specification.

## How the documents relate

The documents are separate by responsibility, not separate by vision.

- Product Strategy answers: **What are we building, for whom, and why?**
- UX answers: **How should people use it to achieve the intended outcomes?**
- Product Design Language answers: **How should those experiences look, feel, and behave?**
- Brand Identity answers: **What distinctive character does DEIXEN express?**
- UX/UI Specifications answer: **What exactly should be built and how should it behave?**

Tool and contributor authority is governed by `DEIXEN_Operating_Constitution.md` and the current `DEIXEN_Execution_Plan.md`. The detailed collaborative design workflow belongs in **05**; brand-specific exploration criteria belong in **04**. Do not duplicate the full role matrix or workflow across every design document.

A decision in one document may affect another. Record the dependency and update the relevant companion document rather than duplicating large sections or silently changing another document's scope.

## Status vocabulary

- **Approved principle:** explicitly accepted by the user.
- **Current reference direction:** a source of inspiration, not a design to copy.
- **Open:** no final decision has been made.
- **Hypothesis:** plausible direction that requires research, prototyping, or testing.
- **Deferred:** intentionally not being decided or built yet.
- **Implementation status unknown:** do not claim it exists in the app without current repository evidence.

## Current approved integrated principle

Develop product logic, UX, UI/product design language, and brand identity as connected disciplines. Do not treat visual design as decoration added after implementation. Let real tasks and learner needs shape UX; let UX and UI inform each other; test design against representative workflows; and maintain a coherent product without forcing identical layouts everywhere.

This principle does not approve a final logo, color, screen, layout, or feature.

## Reference direction currently recorded

- **Microsoft:** composition, information organization, clarity, and hierarchy.
- **Samsung:** modernity, detail, depth, layers, motion, and interactions.
- **Higgsfield:** visual presence, content/tool presentation, and distinctive accent-color strategy.

These references are not templates. The DEIXEN accent color remains open. Fluorescent green is not approved.

## Collaborative design approach

DEIXEN may use more than one AI design environment to explore brand identity and product visuals. The current working pairing is Google AI Studio with Gemini/Argon 4 and Claude Design with Claude Opus 5.5. Neither is presumed superior or given final design authority.

The detailed method—shared brief, independent first-pass exploration, cross-critique, iterative synthesis, evaluation, owner approval, and implementation handoff—is defined in **05**. This is a current working arrangement, not a permanent dependency on particular vendors or model versions.

## Governance

The master strategy and the project's canonical decision log remain authoritative for their respective scopes. The Operating Constitution governs working methods and tool authority; the Execution Plan governs current work sequence and task assignments. Companion design files must not silently amend decisions in `07` or imply implementation authorization. Record disagreements and propose formal review instead of overwriting accepted governance.

## Suggested work sequence

1. Confirm product purpose and representative end-to-end tasks.
2. Map UX for those tasks and test the flow.
3. Explore UI and product design language using realistic content.
4. Develop brand identity in parallel where useful, using the collaborative exploration method in **05**, and validate it against the actual product context.
5. Convert validated patterns into detailed specifications and implementation tasks.
6. Iterate based on usability, learning, operational, and visual-quality evidence.
