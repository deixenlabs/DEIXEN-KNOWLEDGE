AeroBridge — Master Context Document

Project Identity

Product Name: AeroBridge
Category: Professional aviation operations training platform.

Core Purpose: AeroBridge is designed to move users from theoretical knowledge to confident, measurable, job-ready operational performance in airline ticketing and reservation workflows.

It is not:
- A travel application.
- An airline booking product.
- A generic LMS.
- A classroom replacement.
- A collection of videos and quizzes.

It is a realistic operational training environment that simulates the pressure, decisions, and workflows of real airline reservation operations.

Product Vision

AeroBridge exists to close the gap between learning and professional readiness. The full architectural chain — used consistently everywhere this document set refers to "the core transformation" — is:

**Learning → Terminal / Practice → Scenario → Assessment → Evidence → Growth / Readiness**

The product promise:

"Give learners the operational confidence required to perform real airline reservation and ticketing tasks correctly under realistic conditions."

The success metric is not:
- Number of lessons completed.
- Time spent learning.
- Content consumption.

The success metric is:

Can the user perform correctly when facing realistic operational scenarios?

Core Product Differentiator

Terminal

Terminal is the operational heart of AeroBridge.

It is not an additional feature.
It is the main engine that transforms knowledge into ability — the "Terminal / Practice" and "Scenario" links in the core transformation above are where that happens in practice.

Any suggestion that reduces Terminal into a secondary tool, optional simulator, or simple practice screen must be critically reviewed.

Target User

AeroBridge is built for:
- Adults preparing for aviation operations careers.
- Professionals seeking operational confidence.
- Job seekers targeting airline reservation/ticketing roles.
- Organizations needing realistic workforce preparation.

The user is not treated as a student in a classroom.
The user is treated as a future aviation operations professional.

Core Experience Architecture

AeroBridge has five primary top-level areas only:

Home / Flight Deck

The operational command center.

Purpose:
- Show current readiness.
- Surface active missions.
- Provide orientation.
- Connect the user to next actions.

Learning / Curriculum

Purpose:
- Build required knowledge.
- Explain concepts.
- Prepare users before operational execution.

Learning exists to support performance.
It is not the final destination.

Terminal / Practice

Purpose:
- Realistic reservation and ticketing simulation.
- Operational practice.
- Decision-making under realistic conditions.

This is the core experience.

Scenario Bank

Purpose:
- Provide realistic cases.
- Train judgment.
- Expose users to operational variation.

Scenarios must feel connected to real aviation workflows.

Growth / Readiness

Purpose:
- Show development over time.
- Display capability growth.
- Communicate professional readiness.

Growth is different from simple progress tracking.

Future Vision — Not Yet Scoped

The material in this section describes a direction the project has discussed but has not yet reconciled with the five-area architecture above. It is preserved here — rather than deleted — because the underlying thinking has real value, but it is explicitly not current scope, not part of the frozen Phase 3 vertical slice, and not authorization for a sixth top-level area.

Work Shift Simulator

The idea: practice inside AeroBridge could eventually be organized around a "work shift" — a session that combines realistic task flow, priorities, interruptions, routine and irregular work, customer situations, and time pressure into one continuous block, rather than isolated exercises. The intent is for the learner to feel they are practicing the job, not studying a representation of it.

If this direction is pursued, it should follow one governing rule for time and pressure: a timer or countdown must represent a real operational window, workload, priority, or deadline — never a decorative countdown. Pressure should come from the combination of time constraints, task priority, interruptions, and decision consequences, not from punishing the learner for taking longer on a task with no defined time expectation. Any implementation of shift timing must be domain-validated and tested for learning value before being treated as evidence of professional readiness.

**Open question, not resolved by this document:** is the Work Shift Simulator a future evolution of Terminal / Practice, a future evolution of Scenario Bank, or a distinct mode that would require architectural review under the five-area rule? This must be answered by an explicit product decision before any implementation work begins on it. Until that decision exists, Work Shift Simulator work is out of scope for Phase 3 and every phase currently defined in `AeroBridge_Decisions_and_Current_State.md`.

Product Philosophy

Personal Job-Readiness Mission

AeroBridge is being built first as a serious personal training environment for its owner, before it is treated as a commercial product.

The primary success condition is not completing lessons, accumulating points, producing polished UI, increasing feature count, or achieving a visually impressive simulator.

The primary success condition is:

"After using AeroBridge seriously and completing the required training path, the learner should enter a real job interview with meaningful practical familiarity, a correct operational mental model, and enough hands-on experience to have a credible chance of performing and answering role-related questions."

AeroBridge must therefore optimize for real capability, not perceived capability. This must be validated on the owner/primary learner first — its training quality is judged by whether it materially improves real-world interview and job performance, not by how complete the product looks.

Real-World Learning Principle

Every major learning experience should answer: does this help the learner perform the real job better?

At the level of individual learning experiences (as opposed to the top-level product transformation defined above), AeroBridge should prioritize this sequence:

Knowledge → Procedure → Practice → Decision → Consequence → Feedback → Repetition → Competence → Job Readiness

Training should resemble real operational work wherever realism materially improves learning. The system must not create false confidence through superficial realism, decorative terminal interfaces, fake scores, generic scenarios, scripted success paths, or oversimplified workflows that teach incorrect habits.

Capability Over Completion

Completion is not evidence of competence. A learner should only be considered meaningfully ready when they can demonstrate the required capability through performance. The product should distinguish between: knowledge acquired, procedure understood, procedure practiced, task completed with guidance, task completed independently, task completed under pressure, task transferred to a new situation, and competency demonstrated consistently.

Transfer-to-Real-Work Requirement

For every major competency, ask: what will the learner be expected to do in the real workplace? Then ensure the product prepares the learner to recognize the situation, understand the context, choose the correct action, execute the procedure, recover from mistakes, explain the decision, and repeat the performance reliably. A training feature that cannot plausibly contribute to this transfer should be challenged before implementation.

Domain Correctness Above Visual Realism

When realism and visual polish conflict with operational correctness, operational correctness wins. Never invent aviation/GDS behavior to make a simulation feel complete. Every domain-sensitive claim must be clearly one of: known domain behavior, educational simplification, or unknown / requires validation. When domain certainty is unavailable, the correct move is to mark the behavior as needing validation, not to silently invent it.

Evidence Before Confidence

Do not represent a learner as "job-ready" merely because they completed the curriculum, received a high local score, used the simulator successfully once, or because the UI displays a readiness percentage. Readiness claims must be grounded in meaningful evidence — prefer repeated performance, independent execution, varied scenarios, error patterns, decision quality, timing consistency, and transfer performance over any single success.

Keep the Product Honest

Never allow the interface to claim more than the underlying system can prove. Do not display authoritative readiness from a weak heuristic, show success when the action did not actually occur, present illustrative data as real evidence, imply real-world certification where none exists, or imply that simulation behavior is identical to a live airline/GDS environment unless validated.

No Feature for Appearance Alone

Any feature must have a clear learning, operational, assessment, or readiness purpose. Visual polish alone is not sufficient justification. Prefer realism with controlled simplification: when exact real-world behavior is too complex to reproduce, simplify the implementation, not the underlying professional reasoning or workflow.

Do not optimize for the learner feeling ready; optimize for the learner being ready. The system should deliberately expose the learner to mistakes, unfamiliar situations, pressure, and consequences rather than continuously making the learner feel successful.

Direct Communication for a Beginner Learner

The primary learner/user currently has no professional experience in airline reservation and ticketing operations. Explanations must be direct, clear, practical, beginner-friendly, and free of unnecessary jargon. When introducing a professional term, system, command, workflow, or concept: explain what it is in simple language, explain why it matters, show how it is used in practice, then introduce the professional terminology. Do not assume prior industry knowledge, and do not explain concepts abstractly or academically when a practical explanation is clearer. The goal is genuine understanding of what the learner is doing and why, not just correct information delivered.

Equal Priority: Learning Quality and Design Quality

AeroBridge must achieve both high-fidelity professional training and real job readiness, and premium, professional, coherent visual and UX quality. Neither is secondary. Do not sacrifice learning quality for visual polish, and do not sacrifice design quality merely because the product is a training simulator. The goal is operational realism plus a premium product experience — when possible, resolve conflicts by finding a solution that strengthens both rather than treating them as opposing priorities.

North-Star Question

Before major product, learning, UX, simulation, or architecture decisions, ask: will this make the learner more capable of performing the real job correctly? If yes, strengthen it. If no, simplify, defer, or reject it.

Product Experience Principles

Every decision should be evaluated against:

Operational Realism
Does this feel closer to a real aviation workplace?

Professional Confidence
Does this help the user feel capable?

Decision Quality
Does this improve judgment and execution?

Evidence-Based Growth
Can progress be demonstrated through performance?

Continuity
Does the product feel like one connected operational journey?

Design Direction

AeroBridge visual identity:

Dark aviation operations environment

Characteristics:
- Premium.
- Calm under pressure.
- Precise.
- Professional.
- Intelligent.
- Global.
- Operational.

The full anti-pattern list this identity must avoid is maintained in `AeroBridge_Design_System_and_UX_Principles.md`, which is the canonical owner of that list. In short: AeroBridge does not read as a generic SaaS dashboard, a classroom or gamified education interface, or a template-based AI design.

The visual language should feel closer to:
- Flight operations.
- Mission control.
- Professional simulation environments.

Platform Direction

The architecture direction:

Responsive Web Application → Mobile-first architecture → PWA-ready foundation → PWA capabilities activated when justified.

Rules:
- Do not build PWA-first.
- Build a high-quality web application first.
- Mobile experience is a real priority.
- Desktop workstation experience must remain strong.

Decision Philosophy

Any AeroBridge decision, proposal, or feature request is evaluated against the same five criteria used throughout this document set:

- **Product Strategy** — Does it strengthen AeroBridge's purpose and align with the approved direction?
- **User Value** — Does it improve the user's actual ability to perform the job?
- **Operational Realism** — Does it reflect real aviation operations, or at minimum avoid contradicting them?
- **Architecture & Long-Term Scalability** — Does it respect the approved five-area structure and remain viable as the product grows?
- **Implementation Quality & Complexity** — Is it maintainable, or does it introduce unnecessary complexity for the value it provides?

The newest idea is not automatically better. A visually attractive idea that weakens the product strategy should be rejected.

AI Collaboration Rules
Any AI working on AeroBridge must:
- Preserve the complete context.
- Challenge assumptions.
- Avoid automatic agreement.
- Ask only when information is genuinely missing or materially ambiguous.
- Never invent missing requirements.
- Separate facts from opinions.
- Avoid repeating previous outputs without meaningful improvement.
- Respect locked decisions.

Operational AI Standard
`AeroBridge_AI_Working_Rules.md` is the operative AI behavior standard when more specific AI operating instructions are required. It governs evidence handling, decision discipline, phase control, the Manus Collaboration Protocol, and the working contracts for Claude and ChatGPT. This document remains the product-context and North-Star authority. When the two documents differ in specificity, apply the more specific AI operating rule while preserving the product principles defined here.

Manus Collaboration
Manus-assisted work should explicitly distinguish creative exploration, decision, execution, rejection/correction, iteration, reference-driven design, and drift recovery. An approved user decision is binding for execution unless a concrete risk involving frozen behavior, accessibility, data integrity, implementation safety, or direct contradiction requires escalation. Visual references are directional evidence and quality benchmarks; they do not override product architecture, evidence contracts, or approved decisions.

Review Standard

Any review must be:
- Critical, evidence-based, and actionable.

A valid review contains:
- Observation.
- Impact.
- Reasoning.
- Recommendation.
- Expected outcome.

Avoid:
- Generic praise.
- Empty criticism.
- Trend-based suggestions.
- Personal preference presented as fact.

Final Product North Star

AeroBridge succeeds when a user can say:

"I did not only study airline operations. I practiced them, proved my ability, and became ready for the job."

Concretely, that means entering a real interview able to say: "I have already worked through realistic booking, ticketing, pricing, rebooking, irregular-operation, and customer-service situations, and I understand how the workflow behaves." This principle guides all product, UX, design, and engineering decisions, and the product must continuously move toward making it increasingly true.

Saudi Market Readiness — Product Outcome

AeroBridge is ultimately intended to prepare learners for credible entry into real aviation operations roles, with Saudi-market job readiness as an important target outcome of the product.

Saudi Market Readiness must be treated as a measurable product outcome, not as a decorative feature, isolated percentage, gamification mechanic, or standalone dashboard metric.

The product should progressively develop and demonstrate the capabilities required for this outcome through:

Technical Competency + Global Professional Customer Service + Saudi-Specific Operational/Market Context + Saudi-Context Scenario Performance + Assessed Workplace Decisions → Saudi Market Readiness

This outcome must be earned through demonstrated capability and traceable evidence. AeroBridge must not present a readiness claim, score, or percentage unless its evidence owner, calculation logic, scope, and qualification are explicitly defined and supported.

Saudi readiness must remain distinct from the global Customer Service competency. Customer Service is a transferable professional competency; Saudi Market Readiness is the market-specific outcome that may consume Customer Service evidence alongside technical, operational, scenario, and workplace-decision evidence.

The product must prioritize genuine job-readiness over the appearance of readiness.

Whether AeroBridge's interface must support Arabic and right-to-left layout as part of this outcome is not yet decided anywhere in this document set. Saudi Market Readiness is defined above as a content and competency outcome, not explicitly as a localization requirement — but the silence is worth closing deliberately rather than leaving open by omission. This is tracked as an open question in `AeroBridge_Decisions_and_Current_State.md` rather than resolved here, since it has no supporting evidence either way in the current corpus.
