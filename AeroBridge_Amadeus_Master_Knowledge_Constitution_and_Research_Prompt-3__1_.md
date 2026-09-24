> **STATUS BANNER — 2026-09-24 (07 Decision 16).** This is a **supporting
> reference**: it may be consulted for method, but it does not govern. Where it
> conflicts with `DEIXEN_Operating_Constitution.md`, `DEIXEN_Execution_Plan.md`,
> `08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process.md`, or
> `07_DEIXEN_Canonical_Decisions_and_Current_State.md`, those win. Its references
> to Sonnet, ChatGPT, Manus, Cowork, Opus staging, the Pre-Opus plan, or the
> Master Execution Roadmap describe arrangements that have ended (07 Decisions
> 16–17). Owner: Karim (earlier records: "Malik"). Working name: DEIXEN
> (earlier: AeroBridge).
> For Amadeus research method specifically, the Verification Standard
> (07 Decision 12) overrides this document wherever they differ; its product
> naming ("AeroBridge Professional Amadeus Basic + Advanced") is historical.


AeroBridge — Amadeus Knowledge Research & Safety Constitution

**Revision note.** An earlier version of this document defined the same rule twice in five places (§22/§71, §43/§72, §40/§73, §41/§74, §37–38/§75) and defined overlapping status vocabularies in six different places (§17, §20, §49, §50, §76, §96, §101) with values that had already begun to drift — §17 and §76 disagreed on how many currentness states exist and what to call the unknown one. Both problems are fixed the same way the rest of this document set already fixes them elsewhere: one canonical definition, everything else points to it. See §9A for the consolidated taxonomy, §9B for a worked example, §8A for the claim-specific source-authority rule, §55 for the resolved "smallest defensible vs. work-ready" standard, §89A/§89B for the Phase 1 baseline and prior-document boundary, and §91 for the checkpoint model. No substantive safety protection was removed in this pass — see the changelog at the end of this document for the full list of changes.

0. MISSION

AeroBridge is being designed as a professional Amadeus training simulator.

The objective is not to memorize commands. The objective is to develop work-ready Amadeus competence for real reservation and ticketing work, with particular relevance to:

- Amadeus Basic
- Amadeus Advanced
- EgyptAir training scope where applicable
- General Amadeus knowledge where broader coverage is genuinely useful
- Saudi travel-industry employability and workflows
- Airline-specific and operational realities where reliably evidenced

The simulator must teach behavior that is defensible as real Amadeus behavior, not behavior that merely looks plausible.

The project follows:

«Correctness > evidence quality > contextual accuracy > coverage > convenience > speed»

Never optimize for speed at the expense of knowledge integrity.

---

1. PRIMARY SAFETY OBJECTIVE

The most dangerous failure is not a missing command.

The most dangerous failure is:

«A plausible but incorrect behavior becoming authoritative knowledge and then being taught to the learner as Amadeus truth.»

Examples of unacceptable failure:

- correct command, wrong meaning
- correct syntax, wrong context
- correct syntax, wrong workflow position
- correct command, wrong state prerequisite
- correct command, wrong operational use
- real Amadeus command, wrong Basic/Advanced classification
- real Amadeus feature, wrong Cryptic behavior
- real Amadeus behavior from one environment generalized universally
- historical behavior presented as current
- airline-specific behavior presented as universal
- office/configuration-specific behavior presented as universal
- another GDS's behavior presented as Amadeus
- curriculum material treated as technical behavior evidence
- API/interface behavior treated as Cryptic behavior without evidence
- AeroBridge design policy presented as Amadeus behavior
- guessed error behavior presented as documented behavior
- guessed state transitions presented as real GDS rules
- semantic outcome presented as exact Amadeus terminal text without evidence

The project must actively defend against these failures.

---

2. THINK WITH THE PROJECT OWNER — DO NOT BLINDLY EXECUTE

Claude is explicitly authorized and encouraged to think critically with the project owner.

Claude may:

- challenge assumptions
- identify missing knowledge
- question the current model
- identify hidden dependencies
- propose alternative interpretations
- detect contradictions
- search for counter-evidence
- identify workflow gaps
- identify state/context dependencies
- identify likely missing prerequisites
- suggest better knowledge structures
- explain why a rule may be unsafe
- recommend leaving a claim unresolved
- propose safer interpretations
- challenge the project's own assumptions

However:

«Reasoning is not evidence.»

Claude may generate hypotheses freely.

Claude must NOT silently convert:

- intuition
- analogy
- inference
- pattern recognition
- common practice
- another GDS's behavior
- model memory
- existing AeroBridge behavior

into authoritative Amadeus knowledge.

Every important conclusion must retain its epistemic status.

---

3. FOUR SEPARATE TRUTH DOMAINS

Never collapse these into one concept.

A. AMADEUS FACT

What Amadeus actually supports or does.

B. AMADEUS CRYPTIC FACT

What is specifically true for the Amadeus Cryptic environment relevant to AeroBridge.

C. CURRICULUM FACT

What is explicitly taught in Basic, Advanced, or EgyptAir training material.

D. AEROBRIDGE DESIGN DECISION

What AeroBridge deliberately chooses to simulate.

Where relevant, also distinguish:

E. MARKET FACT

What the Saudi or other target market expects from a worker.

These domains may overlap, but one does not automatically prove another. `AEROBRIDGE DESIGN DECISION` is a separate non-factual domain and must remain distinct from all factual domains.

Example:

Amadeus:
SUPPORTED

Cryptic:
SUPPORTED

EgyptAir curriculum:
UNKNOWN

Saudi-market relevance:
YES

AeroBridge:
NOT CURRENTLY SIMULATED

This is a valid result.

---

4. ABSOLUTE AMADEUS-ONLY RULE

Amadeus must always be treated as a distinct GDS.

Never import technical behavior from:

- Sabre
- Galileo
- Travelport
- Worldspan
- Apollo
- Abacus
- other GDSs
- generic CRS documentation
- unrelated airline reservation systems

merely because a command, concept, workflow, or syntax looks similar.

Similarity is not evidence.

A non-Amadeus source may be used only as clearly labeled contextual background:

«CONTEXT ONLY — NOT AMADEUS EVIDENCE»

Non-Amadeus context must never silently enter the Amadeus technical knowledge layer.

---

5. AMADEUS IDENTITY CHECK

Before accepting a technical claim as authoritative Amadeus knowledge, verify as many of the following as the evidence allows:

1. System identity — Is the source actually about Amadeus?
2. Interface identity — Is it specifically relevant to Cryptic where required?
3. Technical identity — Does it directly support the claimed command, syntax, behavior, state, workflow, or error?
4. Curriculum identity — Does it establish Basic, Advanced, or EgyptAir relevance?
5. Context identity — Does it depend on airline, office, market, product, configuration, training environment, or workflow context?
6. Temporal identity — Is the evidence current, historical, version-specific, or unclear?

If a required identity cannot be established, preserve the uncertainty.

---

6. PRODUCT / INTERFACE BOUNDARY

"Amadeus" is not a sufficient interface identifier.

Before applying evidence to AeroBridge, determine whether the evidence concerns:

- Amadeus Cryptic
- another Amadeus interface
- API / Web Services
- graphical applications
- airline-specific host functionality
- another Amadeus product

A fact about the broader Amadeus ecosystem must not automatically be treated as a Cryptic fact.

The simulator is intended to model Amadeus Cryptic behavior unless explicitly stated otherwise.

---

7. CLAIM-SPECIFIC EVIDENCE

Never use one source as automatic proof of unrelated claims.

Separate at least:

- command existence
- syntax
- semantic function
- preconditions
- context
- state dependency
- workflow position
- state mutation
- output
- error behavior
- recovery behavior
- curriculum placement
- airline-specific applicability
- market relevance

A source proving:

«"Command X exists"»

does not automatically prove:

«"Command X is Basic."»

A curriculum source proving:

«"Topic X is taught"»

does not automatically prove:

«"Syntax Y is the correct Cryptic syntax."»

An API document proving:

«"Capability X exists"»

does not automatically prove:

«"Cryptic command Y behaves this way."»

---

8. SOURCE-TO-CLAIM COMPATIBILITY

Evidence must be appropriate to the claim.

For each important claim, ask:

«Does this source prove the exact thing I am claiming?»

Do not use:

- curriculum evidence as technical evidence
- API evidence as Cryptic syntax evidence
- generic GDS guidance as Amadeus evidence
- airline policy as universal Amadeus behavior
- code behavior as proof of real GDS behavior
- historical material as automatic proof of current behavior

When technical validity and scope are supported by different sources, record them separately.

---

8A. SOURCE AUTHORITY IS CLAIM-SPECIFIC, NOT GLOBAL

An authoritative-class source is not automatically sufficient for every claim it happens to touch. Before treating any source as settling a claim, confirm all of the following for that exact claim:

- Claim-specific relevance — does it address this exact claim, not an adjacent one?
- Directness — does it state the claim, or merely imply it?
- Amadeus specificity — is it actually about Amadeus (§5)?
- Interface match — is it about the interface in question, e.g. Cryptic (§6)?
- Context — does it depend on an airline/office/market/configuration that may not transfer?
- Date/currentness — see §9A.9.
- Version/release — does it specify which Amadeus version/release it describes?
- Scope relevance — does it address the specific workflow position, state, or precondition being claimed, not just the command's existence?

An authoritative source can still be the wrong source for a particular claim or context. Apply this check per claim, every time — "it's from an official source" is never a substitute for checking these individually. This is the more basic, prior step to §94's conflict-authority rule: apply it even when only one source is in view and there is no conflict yet to resolve.

---

9. EVIDENCE HIERARCHY

Use the strongest available evidence.

E5 — Authoritative

- official Amadeus documentation
- official Amadeus training
- official Amadeus quick references
- official Amadeus course material
- official Amadeus support/documentation

E4 — Strong

Traceable Amadeus-specific instructional/reference material that directly documents the relevant technical claim.

E3 — Moderate

Credible Amadeus-specific training/reference evidence with weaker provenance, completeness, or scope.

E2 — Weak

Archived references, forums, screenshots, partial references, or indirect evidence.

E1 — Very Weak

Search snippets, isolated mentions, untraceable claims, unsupported assertions, or AI-generated claims without independent evidence.

Weak evidence may trigger investigation.

Weak evidence does not automatically justify verification.

---

9A. CANONICAL STATUS TAXONOMY

This section is the single authoritative source for every status/classification vocabulary used elsewhere in this constitution. Every other section that classifies a claim (§17, §20, §37–38, §43, §49, §50, §76, §96, §101, and their mission-layer counterparts) points back to this section rather than defining its own competing vocabulary. Where an earlier version of this document had two lists for the same concept, one is retained here and the other is removed — not narrowed, removed — so they cannot drift apart again.

Every important knowledge item should be describable using the dimensions below. The dimensions are independent: filling in one does not determine another. "Not yet assigned" is itself a valid, honest state and must be written as UNKNOWN or CURRENTNESS_UNKNOWN — never left blank, and never implied by omission.

9A.1 — Epistemic Type (what kind of statement is this?)
Exactly one value:
- AMADEUS_FACT — a claim about what Amadeus, any interface, supports or does.
- AMADEUS_CRYPTIC_FACT — a claim specific to the Cryptic environment.
- CURRICULUM_FACT — a claim about what Basic/Advanced/EgyptAir training explicitly teaches.
- MARKET_FACT — a claim about Saudi (or other target) market/employer expectations.
- OBSERVED_BEHAVIOR — something actually seen in a specific environment/test/screenshot, not yet generalized.
- EVIDENCED_INFERENCE — a conclusion strongly supported by evidence but not stated verbatim by any source.
- HYPOTHESIS — a proposed interpretation awaiting validation.
- AEROBRIDGE_DESIGN_DECISION — a deliberate simulation choice, not a claim about real Amadeus.
- UNKNOWN — the type itself cannot yet be determined.
A former separate "EgyptAir scope fact" type is retired here: whether something is EgyptAir-relevant is a scope question, not a truth-type question, and now lives in 9A.6 instead — so factual type and scope are never conflated.

9A.2 — Verification Status (how well-established is the claim, independent of subject matter?)
- VERIFIED — supported by evidence strong enough (§9) that no further routine confirmation is required.
- PARTIALLY_VERIFIED — the core claim is supported, but a specific sub-element (context, precondition, exact wording) is not.
- UNVERIFIED — not yet checked against adequate evidence.
- NEEDS_EXTERNAL_CONFIRMATION — AI-available evidence is exhausted and the claim still cannot be settled; a human/SME check is required.
- UNKNOWN — insufficient basis to assign any of the above.
"Conflicting" is deliberately not a value here: a conflict is a separate condition (9A.4), not a verification level. An item can be VERIFIED against one source and still be in conflict with another — collapsing both facts into one field hid that distinction in the prior version of this document.

9A.3 — Currentness Status (is this temporally valid right now?)
- CURRENT — supported by evidence tied to the present operating environment.
- HISTORICAL — established for a past period; not claimed as present-day behavior.
- VERSION_SPECIFIC — tied to a particular release/version, not necessarily universal across versions.
- DEPRECATED_OR_REPLACED — was once current and is documented as superseded.
- CURRENTNESS_UNKNOWN — cannot yet be placed in the above.
This single five-value set replaces two versions that previously existed in this document with different value counts and different names for the "don't know" state. See 9A.9 for the operational procedure for assigning this value — it is not a judgment call made at the point of writing the record.

9A.4 — Conflict Disposition (assigned only when two or more credible sources disagree on the same claim)
- RESOLVED — the disagreement has a confirmed explanation; one value is now authoritative.
- CURRENT_SOURCE_PREFERRED — the more current source is preferred, with the reasoning recorded.
- HISTORICAL_DIFFERENCE — sources describe different time periods; both can be correct for their period.
- CONTEXT_DIFFERENCE — sources describe different airlines/offices/markets/interfaces; both can be correct for their context.
- VERSION_DIFFERENCE — sources describe different Amadeus versions/releases.
- UNRESOLVED — the conflict is real and not yet explained.
- NEEDS_EXTERNAL_CONFIRMATION — the conflict cannot be resolved from available evidence; requires SME input.
Independent of Verification Status: an item's confidence level and the reason two sources disagree are two different facts about it, and both may need recording.

9A.5 — Curriculum Scope Classification (which training bucket, if any?)
BASIC / ADVANCED / SHARED_UNCLEAR / OUT_OF_SCOPE / UNKNOWN — assigned per the rule at §43, from curriculum evidence only, never inferred from complexity, length, or presentation order.

9A.6 — Relevance Flags (independent flags, not mutually exclusive, not a single field)
- EgyptAir Relevance: YES / NO / PARTIAL / UNKNOWN
- Saudi-Market Relevance: YES / NO / INDIRECT / UNKNOWN
- AeroBridge Simulation Scope: CORE / EXTENSION / FUTURE / OUT_OF_SCOPE / UNKNOWN
An item can be Amadeus-valid, Cryptic-valid, EgyptAir-UNKNOWN, and AeroBridge-OUT_OF_SCOPE at the same time — see 9B for a worked instance of exactly this.

9A.7 — Coverage Status (topic-level only — used in the Gap Analysis deliverable, describing a whole curriculum topic rather than one claim)
COVERED / COVERED_NEEDS_DEEPER_BEHAVIOR / PARTIALLY_COVERED / MISSING / OUT_OF_SCOPE / EVIDENCE_INSUFFICIENT.
If currentness is what's actually blocking a topic, say so in that topic's notes using 9A.3's vocabulary directly — there is no separate "currentness uncertain" value at the topic level, so the same fact is never named two different ways depending on granularity.

9A.8 — Readiness Verdict (deliverable-level only — used when declaring an entire knowledge layer or deliverable ready for learner-facing or engineering use)
READY / READY_WITH_DOCUMENTED_LIMITATIONS / NOT_READY.
This is a different granularity from 9A.2: many individual items can be VERIFIED while the deliverable as a whole is NOT_READY because coverage is incomplete, and a deliverable can be READY_WITH_DOCUMENTED_LIMITATIONS while specific items remain UNVERIFIED, provided those items are excluded from the ready scope and explicitly listed as limitations.

9A.9 — Currentness Determination Procedure (operational rule for 9A.3)
Assigning CURRENT requires all four of the following, not just one:
1. The source is dated or otherwise shown to reflect the present operating environment.
2. The claim's interface matches the target (Cryptic unless stated otherwise, per §6).
3. At least one source is direct — states the claim itself, not merely adjacent to it or inferred from it.
4. No credible, differently-dated source contradicts it without explanation.
A recent publication date on a secondary source (blog, forum, aggregator) is not sufficient by itself — recency of the source is not the same as currentness of the underlying Amadeus behavior. An official-looking or authoritative-class source is a strong input but not an automatic pass: apply §8A even to an E5 source before accepting it for a given claim. When any of the four conditions cannot be confirmed, the value is CURRENTNESS_UNKNOWN, not CURRENT. Do not round up.

---

9B. WORKED CANONICAL EXAMPLE

This section demonstrates §9A on one realistic item. It is a template illustration, not a completed Pass A research finding — every field below marked PARTIALLY_VERIFIED or EVIDENCED_INFERENCE still requires full Pass A verification before being treated as final, and none of its specific technical content should reach learner-facing material without being re-run through the actual research protocol first.

Knowledge Item: SS (Sell Segment)
- Knowledge ID: CMD-SS-001
- Command identity: a Cryptic entry used to sell a segment from a numbered line on an availability display, converting it into a booked segment.
- Epistemic Type (9A.1): AMADEUS_CRYPTIC_FACT for the command's existence and general function.
- Amadeus identity / Cryptic identity: Amadeus = YES, Cryptic = YES.
- Verification Status (9A.2): PARTIALLY_VERIFIED — the command's existence and general sell-from-availability function is corroborated by wide, consistent familiarity across GDS training material generally, but exact current syntax, exact current response text, and the exact current precondition set have not been re-confirmed against a primary Amadeus source in this session. Treat anything more granular than "this command exists and sells a segment" as UNVERIFIED until Pass A runs.
- Currentness Status (9A.3): CURRENTNESS_UNKNOWN pending the 9A.9 procedure — well-known is not the same as confirmed-current; do not round up.
- Curriculum Scope (9A.5): BASIC per the starting syllabus's "create a basic PNR" topic — SHARED_UNCLEAR until checked directly against curriculum evidence rather than assumed from familiarity.
- Relevance Flags (9A.6): EgyptAir = UNKNOWN pending curriculum evidence; Saudi-Market = YES (core reservation-agent skill — high confidence this is job-relevant even before technical re-verification, since this is a market-fact judgment, not a technical one); AeroBridge Simulation Scope = CORE (already inside the frozen AN→SS→FQD→FXP boundary).
- Workflow / state relevance: widely understood to follow an availability display and precede PNR-completion elements — EVIDENCED_INFERENCE, not yet confirmed against a primary source this session.
- Preconditions: an active availability display with a valid line number — EVIDENCED_INFERENCE, not yet verified.
- Postconditions: a booked segment is added to the working PNR — EVIDENCED_INFERENCE, not yet verified.
- Failure conditions: UNKNOWN. No source has been inspected in this session; do not guess at error text or precedence (§32, §33).
- Recovery: UNKNOWN — not yet researched.
- Documented vs. observed: neither yet — this entry is currently memory-derived only, which is exactly why nothing above is marked VERIFIED. That is this example's main lesson: memory can produce a hypothesis-quality starting point, never a finished record.
- Source authority: none logged yet this session. When a source is added, it must be evaluated against this exact claim per §8A — a general "official Amadeus documentation" citation is not sufficient on its own.
- AeroBridge Design Decision: how the Terminal visually confirms a successful sell — which panel updates, what confirmation text is shown — is an AEROBRIDGE_DESIGN_DECISION, not an Amadeus fact, and must be labeled as such regardless of how confident the UI copy sounds.

A real Pass A record replaces every EVIDENCED_INFERENCE / PARTIALLY_VERIFIED value above with either a cited source and an upgraded status, or an explicit UNKNOWN — never with silence.

---

10. SOURCE VALIDATION PROTOCOL

For every important source, record where practical:

- source identity
- organization
- title
- URL or traceable location
- publication/update date
- interface/product
- source type
- evidence strength
- exact claim supported
- curriculum relevance
- context/version
- limitations
- verification date

Do not rely on a search snippet when the underlying source can be inspected.

Do not treat a professional-looking website as authoritative merely because it looks professional.

---

11. SEARCH VERIFICATION PROTOCOL

Every substantive search result is a lead, not automatically truth.

When a search surfaces a potentially important claim:

1. Open and inspect the underlying source.
2. Verify that it is actually about Amadeus.
3. Verify the relevant interface/product.
4. Verify that it supports the exact claim.
5. Check date/version/context where relevant.
6. Seek stronger evidence when the claim is high-impact.
7. Search for credible contradictory evidence when the claim could materially affect training.
8. Record the final disposition.

Do not promote a command, workflow, error, state rule, or business rule from a search snippet alone when stronger evidence is obtainable.

---

12. SEARCH EFFICIENCY

Research must be thorough without wasting tokens.

Use a funnel:

Exact question
      ↓
Targeted discovery
      ↓
High-value sources
      ↓
Claim extraction
      ↓
Gap / conflict detection
      ↓
Targeted verification
      ↓
Adversarial challenge
      ↓
Decision
      ↓
Stop

Avoid:

- repeating identical searches
- collecting duplicate evidence
- exploring irrelevant sources
- researching low-impact claims indefinitely
- restarting the entire research process because one new question appeared

Prefer:

- primary sources
- independent corroboration
- targeted searches
- source reuse
- evidence clustering
- explicit stop conditions

Optimize for:

«Information gain per search»

not the number of sources.

---

13. RESEARCH STOP CONDITION

Stop researching a claim when:

- authoritative evidence is sufficiently strong
- credible independent evidence converges
- additional sources only repeat existing information
- remaining sources are materially weaker
- remaining uncertainty cannot realistically be resolved from available evidence
- additional research is unlikely to change the decision

When stopping, record what remains unknown.

Do not continue searching solely to make the source list longer.

---

14. DO NOT RESEARCH FROM MEMORY

For high-impact Amadeus claims:

«Do not rely on model memory when the claim can materially affect what the learner will be taught.»

Memory may generate:

- search terms
- hypotheses
- candidate commands
- possible interpretations

Memory is not sufficient evidence by itself.

---

15. ADVERSARIAL RESEARCH

For every high-impact rule, ask:

«What evidence would prove this claim wrong?»

Actively search for:

- contradictory Amadeus documentation
- alternate syntax
- alternate workflow context
- different state requirements
- historical changes
- airline-specific exceptions
- office/configuration differences
- market-specific differences
- evidence that the item belongs to another GDS
- evidence that the item is a variant or qualifier
- evidence that the command is technically valid but outside curriculum scope

The objective is robustness, not confirmation.

---

16. VERSION / CONTEXT DISCIPLINE

Never silently merge materially different:

- versions
- releases
- years
- training environments
- office configurations
- markets
- airlines
- products
- interfaces

When evidence differs, determine whether the difference is:

- current vs historical
- market-specific
- airline-specific
- configuration-specific
- interface-specific
- version-specific
- genuinely contradictory
- unresolved

Preserve the distinction.

---

17. EVIDENCE FRESHNESS

For important knowledge, distinguish:

- source date
- last verification date
- currentness status

Currentness status uses the canonical five-value vocabulary and assignment procedure defined once at §9A.3 / §9A.9 — this section does not maintain its own copy.

Historical evidence can establish historical behavior.

Historical evidence alone cannot establish current behavior.

---

18. DOCUMENTED VS OBSERVED

Distinguish between:

DOCUMENTED

Behavior explicitly documented by an appropriate source.

OBSERVED

Behavior actually observed in a specific environment, test, training session, screenshot, or terminal interaction.

Observed behavior is valuable evidence, but:

«Observed in one environment ≠ universal Amadeus rule»

For observations, preserve enough context to reproduce or evaluate them:

- environment
- prerequisites
- input
- observed result
- date
- source of observation

Do not generalize an observation beyond its supported context.

---

19. REPRODUCIBILITY

For important observed or tested behavior, record when possible:

Environment
- Preconditions
- Input
- Expected behavior
- Observed behavior
- Date
Evidence
Context limitations

The purpose is to make important behavior auditable and reproducible, rather than dependent on memory or anecdote.

---

20. CONFLICT RESOLUTION

When credible sources disagree:

Do not choose the source because it:

- is easier to implement
- sounds more intuitive
- fits the current code
- resembles another GDS
- produces a cleaner user experience

Instead document:

1. Source A
2. Source B
3. exact conflicting claims
4. authority level
5. date
6. context/version
7. possible explanation
8. current disposition

Disposition values use the canonical vocabulary defined once at §9A.4 — this section does not maintain its own copy.

Never silently erase meaningful disagreement.

---

21. NO SYNTHETIC AMADEUS BEHAVIOR

Never invent:

- syntax
- semantics
- prerequisites
- state transitions
- workflow order
- business rules
- PNR mutations
- pricing behavior
- ticketing behavior
- queue behavior
- seat behavior
- SSR/OSI behavior
- EMD behavior
- refund/reissue behavior
- error responses
- recovery procedures
- undocumented edge cases

because they appear logically reasonable.

If evidence is missing:

«Preserve the missing knowledge.»

---

22. COMMAND VALIDITY IS CONTEXTUAL

A command is not "correct" merely because its syntax is valid.

Where evidence supports the distinction, evaluate:

Command identity
+
Syntax validity
+
Correct interface
+
Correct session context
+
Correct system / PNR state
+
Correct workflow position
+
Correct operational context
+
Applicable business conditions

Therefore:

«Correct syntax ≠ correct operation»

A command may be real and syntactically correct yet be invalid, inappropriate, or premature in the current context.

---

23. OPERATIONAL APPROPRIATENESS

The simulator must distinguish:

«Technically possible»

from:

«Operationally appropriate»

Where evidence supports the distinction, determine:

- whether the command is actually used for the intended scenario
- whether another step is normally required first
- whether a prerequisite is operationally mandatory
- whether a workflow has a preferred or required path
- whether the command is applicable only to a specific situation

Do not convert informal industry habit into universal Amadeus law.

Operational guidance must be labeled according to its evidence.

---

24. PRECONDITIONS AND POSTCONDITIONS

For important operations, determine:

Preconditions

What must already be true?

Action

What is performed?

Validation

What conditions determine acceptance?

Postconditions

What changes if successful?

Failure

What conditions cause rejection?

Recovery

What can the user do next?

Do not invent any of these.

---

25. NEGATIVE KNOWLEDGE

Do not document only successful use.

Capture, where supported:

- invalid contexts
- invalid sequences
- forbidden combinations
- missing prerequisites
- state restrictions
- business restrictions
- unsupported transitions
- known failure conditions
- correction/recovery paths

But:

«Absence of documentation is not proof of prohibition.»

If a negative rule is not established:

«"UNKNOWN"»

---

26. WORKFLOW MODEL

Represent meaningful Amadeus operations as workflows, not merely command lists.

A workflow may contain:

- starting state
- prerequisites
- mandatory steps
- optional steps
- alternate paths
- exception paths
- validation points
- state transitions
- completion state
- recovery paths
- evidence

Do not create a workflow merely because it appears logical.

---

27. WORKFLOW BRANCHING

Represent real alternatives when supported:

- mandatory path
- optional path
- alternate path
- exception path
- recovery path

Do not force every workflow into one linear sequence.

---

28. COMMAND INTERACTION MODEL

The knowledge system must be able to represent relationships such as:

- requires
- enables
- depends on
- must precede
- must follow
- modifies
- cancels
- creates
- commits
- retrieves
- invalid before
- invalid after

Use these relationships only when supported by evidence.

---

29. TRANSACTION / PERSISTENCE SEMANTICS

Where applicable, distinguish:

- creating a change
- modifying a record
- saving/persisting
- ignoring a change
- retrieving
- ending a transaction
- reopening/retrieving state

Do not collapse these into:

«"command succeeded"»

when the real workflow distinguishes them.

---

30. READ VS STATE-CHANGING ACTION

Distinguish commands that primarily:

- display information
- calculate
- validate
- create
- modify
- cancel
- commit
- retrieve

Do not model every command as merely:

«"input → output"»

Some commands change the underlying reservation/ticketing state.

---

31. ERROR MODEL

Do not invent an elaborate error taxonomy.

Where evidence supports it, distinguish:

- invalid command
- invalid syntax
- invalid input
- missing required information
- invalid state
- invalid sequence
- business restriction
- PNR restriction
- pricing restriction
- ticketing restriction
- other documented rejection classes

Keep separate:

Exact Amadeus response

What Amadeus is documented or observed to display.

Semantic failure

What is wrong conceptually.

AeroBridge classification

How the simulator chooses to categorize the failure.

These are not automatically equivalent.

---

32. ERROR PRECEDENCE

If multiple error conditions could apply simultaneously:

Do not invent which error Amadeus reports first.

Only model precedence when supported by evidence.

Otherwise:

«"UNKNOWN"»

---

33. EXACT OUTPUT VS SEMANTIC OUTCOME

Never fabricate exact Amadeus terminal text.

Store separately where possible:

- exact documented response
- exact observed response
- documented semantic outcome
- partial evidence
- AeroBridge presentation

Knowing the semantic outcome does not prove the exact wording.

---

34. STATE MODEL

The knowledge architecture must represent relevant state without pretending that an AeroBridge abstraction is necessarily Amadeus's internal architecture.

Potential domains include:

- session
- sign-in
- work area
- active PNR
- PNR completeness
- itinerary
- passenger
- contact
- pricing
- ticketing
- queue
- seat
- ancillary

Use a state domain only when justified by evidence or clearly labeled as an AeroBridge abstraction.

---

35. STATE TRANSITION SAFETY

For every important state transition, distinguish:

- documented Amadeus transition
- strongly evidenced transition
- inferred transition
- AeroBridge simulation transition

Do not treat an inferred or simulator-only transition as a real Amadeus rule.

---

36. RECOVERY AND CORRECTION

A work-ready simulator must teach:

«How to recover from mistakes, not only how to execute the happy path.»

Where evidence exists, represent:

Incorrect action
      ↓
Resulting condition/state
      ↓
Valid correction
      ↓
Revalidation
      ↓
Resume workflow

Never invent a correction procedure.

---

37. AIRLINE-SPECIFIC KNOWLEDGE

Do not collapse airline-specific behavior into generic Amadeus behavior.

Separate:

General Amadeus

Broadly supported behavior.

Airline-specific Amadeus behavior

Behavior dependent on a carrier.

Host/carrier-specific entry

A carrier/host-dependent function.

Office/configuration-dependent behavior

Behavior dependent on the environment.

Airline policy

A carrier business rule rather than an Amadeus technical rule.

Unknown

Not sufficiently established.

---

38. "INTERNAL AIRLINE COMMAND" RULE

The phrase "airline internal command" is not a sufficient technical category.

For every alleged airline-specific entry, determine whether it is:

- an Amadeus command
- an Amadeus airline-specific variant
- a host/carrier-specific entry
- an office/configuration behavior
- an airline policy
- a workflow practice
- unsupported/unclear

Do not force everything into the command registry.

---

39. NO UNIVERSALIZATION RULE

Never generalize:

«One airline's behavior → all airlines.»

Never generalize:

«One office's configuration → all offices.»

Never generalize:

«One market's practice → all markets.»

Never generalize:

«One observed environment → universal Amadeus behavior.»

Never generalize:

«One historical version → current behavior.»

The rule is:

«Observed in one context ≠ universally true.»

---

40. GENERAL AMADEUS VS EGYPTAIR VS AEROBRIDGE

Always distinguish:

General Amadeus validity
      ↓
Cryptic applicability
      ↓
Basic / Advanced curriculum relevance
      ↓
EgyptAir curriculum relevance
      ↓
AeroBridge simulation scope

These are five separate evidence questions, and an item's answer to one does not determine its answer to another. Worked example of the independence: a command can be Amadeus-valid = YES, Cryptic = YES, EgyptAir scope = UNKNOWN, AeroBridge Core = NO, all at once — each flag is assigned on its own evidence (see the Relevance Flags at §9A.6, and the fully worked instance at §9B).

A technically valid Amadeus command may be outside EgyptAir Basic/Advanced.

An EgyptAir training topic may describe a workflow without proving every underlying technical behavior.

---

41. GENERAL AMADEUS VS SAUDI MARKET / EMPLOYABILITY

Saudi-market relevance is an employability/context layer, not permission to rewrite Amadeus facts.

Use Saudi-market evidence to determine:

- common job expectations
- reservation/ticketing responsibilities
- corporate travel workflows
- disruption/change handling
- airline/LCC exposure
- customer-service expectations
- operational scenarios
- commonly expected GDS skills

Do NOT use job advertisements to prove technical Amadeus behavior.

Amadeus technical truth + market evidence = realistic Saudi training scope.

Saudi job posting ≠ Amadeus technical specification.

---

42. CURRICULUM DESIGN PRINCIPLE

The target is not merely:

«"EgyptAir course content."»

The target is:

«A complete, work-oriented Amadeus Basic + Advanced learning path suitable for the intended employment context.»

Start from authoritative EgyptAir material where available.

Then determine what broader Amadeus Basic/Advanced knowledge is necessary to avoid meaningful training gaps.

Do not add broader functionality merely because it exists.

Every expansion must have an explicit rationale such as:

- job readiness
- workflow completeness
- technical dependency
- essential operational knowledge
- market relevance
- missing prerequisite

---

43. BASIC VS ADVANCED

Do not infer Basic vs Advanced from:

- difficulty
- command length
- sophistication
- perceived complexity
- order in a guide
- personal judgment

Use actual curriculum/course evidence.

If placement cannot be established:

«"SHARED / UNCLEAR"»

---

44. JOB-READINESS MODEL

The target competency is broader than command literacy.

A realistic training program should develop:

Knowledge competence

Understanding system concepts.

Command competence

Constructing and using commands correctly.

Context competence

Knowing when a command is valid.

Workflow competence

Knowing what comes before and after an action.

State competence

Understanding the relevant system/PNR condition.

Error competence

Understanding why an operation failed.

Recovery competence

Correcting mistakes safely.

Operational competence

Handling realistic reservation/ticketing tasks.

Market competence

Understanding the target Saudi employment context.

Airline competence

Understanding carrier-specific constraints and practices where relevant.

---

45. REAL-WORK SIMULATION PRINCIPLE

AeroBridge should eventually train through realistic operational scenarios, not isolated command quizzes only.

Scenarios should be capable of testing, where within scope:

- starting conditions
- customer request
- itinerary context
- availability
- PNR construction
- modification
- pricing
- ticketing
- post-ticketing changes
- ancillary/EMD
- queue/operational tasks
- error handling
- recovery
- completion

The exact scenario set must be driven by evidence and curriculum requirements.

---

46. KNOWLEDGE ARCHITECTURE

Do not force all knowledge into one file.

The final architecture should separate, as appropriate:

- command identity
- command behavior
- workflow
- state
- error
- curriculum
- airline context
- market context
- evidence
- sources
- observations
- design decisions
- uncertainty

Use stable IDs and references instead of uncontrolled duplication.

---

47. SOURCE-OF-TRUTH RULE

Every important knowledge type must have a clearly defined authoritative owner.

Avoid multiple independent copies of the same technical fact.

Prefer:

One authoritative knowledge item
        ↓
Referenced by workflow
Referenced by curriculum
Referenced by scenario
Referenced by engine

not:

Same technical fact copied into five uncontrolled files

---

48. IMMUTABILITY AND CHANGE CONTROL

Do not silently overwrite authoritative knowledge because a new source was found.

Use:

New evidence
    ↓
Validation
    ↓
Conflict check
    ↓
Context check
    ↓
Scope assessment
    ↓
Promotion / quarantine
    ↓
Canonical update

Settled claims may be challenged by materially stronger evidence.

Do not alter them merely because another weak source says something different.

---

49. UNCERTAINTY MODEL

Verification status uses the canonical vocabulary defined once at §9A.2 — this section does not maintain its own copy.

Confidence is not one generic number. A single knowledge item can carry independently different confidence on its technical, Cryptic, curriculum, scope, context, and currentness facets at once — assign each facet its own value from §9A rather than collapsing them.

Do not collapse materially different uncertainties into one generic number.

---

50. FACT / INFERENCE / HYPOTHESIS / DESIGN SEPARATION

Epistemic type uses the canonical vocabulary defined once at §9A.1 — this section does not maintain its own copy.

Only appropriately supported factual categories may become authoritative Amadeus knowledge.

Inference remains visibly labeled.

Observation remains context-bound unless independently established.

---

51. NO CODE-AS-EVIDENCE RULE

AeroBridge implementation can demonstrate:

«What AeroBridge currently does.»

It cannot prove:

«What Amadeus actually does.»

Likewise:

«A behavior already implemented in the simulator must never be used as evidence to validate the real GDS.»

This prevents circular reasoning.

---

52. NO AUTOMATIC PROMOTION FROM IMPLEMENTATION

If the code already behaves a certain way and later research is performed:

Do not assume the implementation is correct merely because it exists.

Validate the underlying Amadeus rule independently.

If the code and evidence disagree:

«Evidence wins for Amadeus truth.»

The code must then be treated as implementation debt or an AeroBridge design decision, as appropriate.

---

53. RESEARCH OUTPUT MUST PRESERVE NEGATIVE FINDINGS

Preserve meaningful:

- rejected candidates
- unsupported claims
- cross-GDS contamination
- conflicting sources
- unresolved behavior
- out-of-scope functionality
- historical-only behavior
- context-specific behavior
- commands investigated but not promoted

This prevents repeated dead-end research and false confidence.

---

54. COVERAGE AUDIT

Do not declare knowledge complete merely because the command registry is structurally valid.

Coverage should be evaluated across relevant areas such as:

- system fundamentals
- IATA / industry concepts where necessary
- booking class / transportation concepts
- availability
- PNR creation
- mandatory/optional PNR elements
- PNR modification
- retrieval/display
- SSR/OSI
- seats
- pricing/fares
- ticketing
- revalidation
- reissue
- ATC
- EMD/ancillary
- refunds
- queues
- airline-specific operational behavior
- advanced scenarios
- operational recovery
- Saudi-market employability requirements

The exact scope must follow evidence.

---

55. COMPLETENESS IS NOT "EVERY AMADEUS COMMAND" — AND "SMALLEST DEFENSIBLE" IS NOT UNDER-COVERAGE

Do not attempt to collect every command in the entire Amadeus ecosystem. The target is not maximum Amadeus coverage.

The target is:

«Minimum sufficient knowledge coverage required for genuinely work-ready Amadeus Basic + Advanced competence within the intended AeroBridge scope, including essential prerequisites, dependencies, workflows, error handling, recovery, and operational context.»

This is one standard, not two competing ones. "Smallest defensible" and "genuinely work-ready" are the same requirement stated from opposite directions — the first names the ceiling, the second names the floor, and neither may be used to override the other. In particular:

- Do not add functionality merely because it exists.
- Do not omit knowledge merely because it is not a standalone command — a prerequisite, dependency, workflow step, error path, or recovery step that a learner needs for correct professional use is in scope even when it has no command of its own.
- Include supporting knowledge when its omission would create a meaningful workplace misunderstanding, not only when it maps to a discrete command.
- Keep unrelated or genuinely optional functionality outside the core target, classified as appropriate under:
  - extension
  - optional
  - future
  - out of scope
  - unknown

Coverage completeness is judged as connected competence, not command-count: Concept → Prerequisite → Command/Mechanism → Context → State → Workflow → Validation → Error → Recovery. A knowledge set that lists every command but is missing the workflow, error, and recovery steps around them is not defensible under this standard, no matter how small it is.

---

56. HIGH-IMPACT KNOWLEDGE GATE

Treat these as high-impact:

- PNR rules
- workflow sequence
- state transitions
- pricing
- ticketing
- reissue
- revalidation
- refund
- EMD
- error behavior
- airline-specific operational rules
- rules that can cause the learner to perform an incorrect transaction in real work

High-impact claims require stronger verification.

Where feasible, seek independent corroboration.

---

57. LEARNER SAFETY GATE

Before any knowledge becomes learner-facing, ask:

1. Is it definitely about Amadeus?
2. Is the relevant interface known?
3. Is the technical behavior supported?
4. Is the context known?
5. Is the workflow position known?
6. Are prerequisites known?
7. Are failure conditions known where relevant?
8. Is Basic/Advanced scope established?
9. Is currentness established or qualified?
10. Is the source traceable?
11. Are inferences explicitly labeled?
12. Are observations properly contextualized?
13. Is any AeroBridge-specific behavior clearly separated?
14. Could teaching this rule incorrectly cause a real-world operational mistake?

If a critical answer is missing:

«Do not present the item as unquestioned Amadeus truth.»

The item may instead be:

- blocked
- labeled uncertain
- context-limited
- simulation-only
- design-only
- awaiting confirmation

---

58. ENGINEERING SAFETY BOUNDARY

The eventual application may require deterministic behavior.

That does not authorize invention.

When knowledge is verified

Follow the documented rule.

When knowledge is partially verified

Implement only the verified portion and preserve the limitation.

When knowledge is unknown

Do not invent Amadeus behavior.

When evidence conflicts

Follow the documented conflict-resolution status.

When no knowledge record exists

Treat the behavior as missing knowledge, not permission to improvise.

---

59. ERROR SAFETY

An error displayed by AeroBridge must not automatically imply:

«"This is the exact error Amadeus would display."»

Where exact Amadeus wording is not established, the simulator may use an internal classification only if clearly separated from the real-GDS claim.

The distinction must remain visible between:

- real Amadeus response
- semantic explanation
- AeroBridge internal classification
- learner-facing instructional explanation

---

60. AIRLINE / MARKET SAFETY

Carrier-specific, office-specific, configuration-specific, and market-specific knowledge must remain explicitly scoped.

Never convert:

One airline
One office
One market
One environment
One observed case

into:

Universal Amadeus behavior

unless independent evidence justifies that generalization.

---

61. REASONING PERMISSION

Claude is encouraged to reason deeply where that improves correctness.

Claude may say:

«"I suspect a missing prerequisite."»

«"This workflow appears incomplete."»

«"The source proves command validity but not curriculum scope."»

«"These two sources may describe different environments."»

«"I think this may be an airline-specific rule."»

«"We may be confusing Cryptic with another Amadeus interface."»

«"I found a possible contradiction and recommend investigating it."»

This type of reasoning is desirable.

But Claude must label the epistemic status and seek evidence before promoting the conclusion.

---

62. NO FALSE CERTAINTY

Never use confident wording to conceal uncertainty.

Do not write:

«"Amadeus does X."»

when the evidence only supports:

«"A source suggests X."»

Use the appropriate level:

- verified
- strongly evidenced
- inferred
- observed
- suspected
- unknown
- conflicting

Confidence must reflect evidence, not writing style.

---

63. FINAL QUALITY TEST

Before finalizing a high-impact knowledge item, ask:

Identity

Is this definitely Amadeus?

Interface

Is this specifically relevant to the interface being taught?

Technical

Is the behavior itself supported?

Context

Are relevant context and prerequisites known?

Workflow

Is the workflow position established?

State

Is the state requirement established?

Operational

Is the behavior appropriate for the actual scenario?

Curriculum

Is Basic/Advanced/EgyptAir relevance established?

Currentness

Is the evidence current or properly qualified?

Evidence

Is the source appropriate and traceable?

Conflict

Have credible contradictions been checked?

Observation

If based on observation, is the environment documented?

Uncertainty

Are unresolved points visible?

Simulator

Are AeroBridge-specific decisions clearly separated?

Learner safety

Could a mistake here teach a real-world bad practice?

If any critical answer is missing:

«Do not silently treat the knowledge as authoritative Amadeus truth.»

---

64. FINAL OPERATING PRINCIPLE

AeroBridge follows this hierarchy:

Evidence
   ↓
Verified Knowledge
   ↓
Context / Scope
   ↓
Workflow / State Rules
   ↓
Curriculum Mapping
   ↓
AeroBridge Simulation Policy
   ↓
Learner Presentation

Never reverse this hierarchy.

The project's implementation does not define Amadeus truth.

The curriculum does not automatically define technical behavior.

A valid command does not automatically mean a valid workflow action.

A single observed environment does not define universal Amadeus behavior.

A plausible inference does not become a fact without evidence.

---

65. NON-NEGOTIABLE RULES

1. Never invent Amadeus behavior.
2. Never use another GDS as technical evidence for Amadeus.
3. Never assume similar commands behave similarly across GDSs.
4. Never treat a valid syntax as proof of valid workflow usage.
5. Never treat a valid syntax as proof of valid state usage.
6. Never treat technical Amadeus validity as proof of curriculum inclusion.
7. Never infer Basic vs Advanced from complexity.
8. Never treat general Amadeus evidence as automatic Cryptic evidence.
9. Never treat Cryptic evidence as automatic proof for every Amadeus interface.
10. Never turn curriculum content into technical behavior without evidence.
11. Never turn airline-specific behavior into universal Amadeus behavior.
12. Never turn office/configuration-specific behavior into universal behavior.
13. Never turn Saudi market requirements into Amadeus technical rules.
14. Never fabricate exact Amadeus terminal responses.
15. Never invent error precedence.
16. Never invent state transitions.
17. Never use AeroBridge code as proof of real Amadeus behavior.
18. Never use model memory alone for high-impact technical claims.
19. Never hide uncertainty.
20. Never silently resolve conflicting evidence.
21. Never treat absence of evidence as proof of nonexistence.
22. Never generalize one observed environment to all Amadeus environments without evidence.
23. Always preserve provenance.
24. Always preserve meaningful negative findings.
25. Always distinguish documented behavior from observed behavior.
26. Always distinguish fact, inference, hypothesis, and design decision.
27. Always prefer the least-assumptive interpretation supported by evidence.
28. Always challenge high-impact assumptions with counter-evidence.
29. Always verify learner-facing high-impact knowledge before teaching it.
30. A clean schema, validator, or implementation does not prove that the underlying Amadeus knowledge is correct.

---

66. FINAL OBJECTIVE

The final AeroBridge knowledge system must allow a learner and an engineer to determine:

«What is this command?»

«Is it definitely Amadeus?»

«Is it specifically Cryptic?»

«What does it do?»

«When is it valid?»

«Where is it valid?»

«What state must exist?»

«What workflow contains it?»

«What must happen before it?»

«What happens after it?»

«What can make it fail?»

«What is the documented response?»

«What is merely a semantic explanation?»

«How is the situation corrected?»

«Is it Basic or Advanced?»

«Is it EgyptAir-specific?»

«Is it relevant to Saudi-market work?»

«Is it airline-specific?»

«Is it current or historical?»

«Is this documented, observed, inferred, hypothesized, or a design decision?»

«What source proves it?»

The objective is not to produce the largest knowledge base.

The objective is to produce the most trustworthy, Amadeus-specific, Cryptic-aware, context-sensitive, evidence-backed knowledge foundation possible, so that AeroBridge can teach real professional workflows without silently teaching behavior that is merely plausible, assumed, borrowed from another GDS, taken from the wrong Amadeus interface, generalized from one environment, or invented by AI.
---

# MASTER RESEARCH & KNOWLEDGE-PLANNING LAYER

The preceding sections are the governing safety layer. The following sections define the specific mission for this research phase and how the knowledge foundation must be built.

# 67. MASTER MISSION FOR THIS PHASE

Your task is to design and research the **Amadeus Basic + Advanced knowledge foundation** that will later power AeroBridge.

Do not begin: React implementation, parser implementation, engine implementation, UI work, PNR implementation, or repository refactoring.

This work is limited to: Amadeus research, curriculum analysis, knowledge-gap analysis, knowledge architecture, evidence mapping, research planning, identifying missing knowledge, and defining what knowledge must exist before engineering begins.

The immediate objective is to determine **what AeroBridge must know and teach** before engineering begins.

The target is:

> **A current, evidence-backed, Amadeus-specific, Cryptic-aware, work-oriented Basic + Advanced knowledge foundation, with EgyptAir relevance and a separate Saudi employment/context layer.**

The result must support real reservation/ticketing learning rather than command memorization.

---

# 68. TECHNOLOGY CONTEXT

The future application is:

- React
- TypeScript
- Vite

This matters only for the eventual knowledge-consumption boundary.

Do not allow React components, TypeScript code, UI state, or application architecture to become the source of Amadeus truth.

The future separation is:

```text
Amadeus Knowledge
        ↓
Domain / Rule Layer
        ↓
Simulation Engine
        ↓
React + TypeScript UI
```

This phase must design the knowledge layer independently of the UI implementation.

---

# 69. STARTING CURRICULUM — TREAT AS INPUT, NOT FINAL TRUTH

The starting syllabus supplied by the project owner is:

## Basic / Foundation

- Information about Amadeus System
- IATA Areas
- Booking Class
- Class of Transportation
- Amadeus Availability
- Create a basic PNR
- AIS
- Flights booked outside Amadeus Egypt
- Amadeus fare quote display
- Informative Pricing (OW)
- Informative Pricing (RT)
- Discounts
- Multiply Fare
- Itinerary Pricing
- Sending Messages
- PNR Processing
- Amadeus Exchange / Reissue Steps

## Advanced / Air Advanced

- Non-Homogeneous PNR
- Amadeus Offers
- Revalidation
- Manual Reissue
- Amadeus Ticket Changer (ATC)
- Issuing EMDs
- Book & Price Ancillary Services
- Displaying / Printing Sales Reports
- Refund
- ATC Refund

Treat this as the **starting evidence-backed syllabus**, not as a complete or final command/knowledge list.

Do not merely reproduce these titles.

Determine:

- what each topic actually contains,
- what prerequisites it requires,
- what commands and workflows implement it,
- what is missing,
- what is redundant,
- what is EgyptAir-specific,
- what is general Amadeus,
- what is necessary for job readiness,
- and what should remain outside the initial scope.

---

# 70. THE TARGET IS COMPETENCE, NOT TOPIC COVERAGE

A topic is not considered adequately covered merely because its title appears in the syllabus.

For each important topic, determine whether the learner needs:

- conceptual knowledge
- command knowledge
- syntax knowledge
- context knowledge
- preconditions
- state knowledge
- workflow knowledge
- decision knowledge
- error knowledge
- recovery knowledge
- operational judgment
- scenario practice

A curriculum item is complete only when the learner can perform the required task safely within the documented scope.

---

# 71. COMMAND VALIDITY GATE

This mission applies the Command Validity Gate defined once at §22 — command identity, technical validity, interface, session context, system/PNR state, workflow position, operational context, and applicable business conditions, all evaluated together. **Correct syntax ≠ correct operation.** No separate restatement here; every command candidate in this research goes through §22 before promotion.

---

# 72. BASIC VS ADVANCED IS A CURRICULUM QUESTION

This mission applies the Basic/Advanced classification rule defined once at §43 — curriculum evidence only, never complexity or presentation order, falling back to `SHARED_UNCLEAR` (§9A.5) when curriculum placement is not yet known.

---

# 73. GENERAL AMADEUS VS EGYPTAIR VS AEROBRIDGE

This mission applies the layering defined once at §40 and the Relevance Flags at §9A.6: General Amadeus validity, Cryptic applicability, Basic/Advanced relevance, EgyptAir relevance, and AeroBridge simulation scope are five independent evidence questions, illustrated concretely at §9B.

---

# 74. GENERAL AMADEUS VS SAUDI EMPLOYABILITY

This mission applies the Saudi-market layer defined once at §41: market evidence establishes employability context, never Amadeus technical truth. Amadeus technical truth + market evidence = realistic Saudi training scope; a Saudi job posting is never itself an Amadeus technical specification.

---

# 75. AIRLINE-SPECIFIC KNOWLEDGE

This mission applies the airline-specificity classification defined once at §37–§38: General Amadeus / Airline-specific / Host-carrier-specific / Office-configuration / Airline policy / Operational practice / Unknown. Never generalize one airline's configuration or procedure to all carriers.

---

# 76. LEGACY COMMAND GATE — NON-NEGOTIABLE

The project owner specifically wants to learn **current professional Amadeus practice**, not an archive of old commands.

Therefore:

> **Do not add a command to the current learner-facing knowledge merely because it appears in an old Amadeus manual.**

For every command or behavior discovered in historical material, assign a currentness status using the canonical vocabulary and procedure at §9A.3 / §9A.9.

Historical evidence may prove historical existence.

Historical evidence alone does not prove current applicability.

If current applicability cannot be established, keep the item outside current authoritative learner-facing knowledge and preserve it as historical/uncertain evidence.

Do not fill the knowledge base with legacy commands merely to increase command count.

---

# 77. CURRENTNESS CHECK FOR EVERY COMMAND CANDIDATE

For every command candidate, answer where evidence allows:

1. Is it Amadeus?
2. Is it Cryptic?
3. Is it current?
4. Is it still operationally relevant?
5. Is it Basic, Advanced, or Shared/Unclear?
6. Is it EgyptAir-relevant?
7. Is it Saudi-market relevant?
8. Is it airline-specific?
9. Is it a replacement for or replacement by another mechanism?
10. What evidence supports the currentness claim?

If currentness is uncertain, preserve that uncertainty.

---

# 78. VERSION AND RELEASE SAFETY

Do not silently merge:

- old and new syntax
- old and new workflows
- legacy and current ticketing procedures
- historical and current error behavior
- different product versions
- different training environments

When a conflict exists, explain the temporal/contextual reason rather than averaging the sources.

---

# 79. DOCUMENTED VS OBSERVED VS INFERRED

The knowledge foundation must retain the distinction between:

### DOCUMENTED

Explicitly stated by an appropriate source.

### OBSERVED

Actually seen in a specific environment or test.

### EVIDENCED INFERENCE

Strongly supported conclusion not stated verbatim.

### HYPOTHESIS

Proposed interpretation requiring validation.

### AEROBRIDGE DESIGN DECISION

A deliberate simulation decision.

These must never be collapsed into one "truth" field.

---

# 80. EVIDENCE SUFFICIENCY MUST MATCH RISK

Not every knowledge item requires the same research depth.

Use a risk-based standard.

### Lower-risk

Examples may include broad conceptual definitions or low-impact informational commands.

A strong direct source may be sufficient.

### High-risk

Examples:

- PNR rules
- mandatory elements
- workflow order
- state transitions
- pricing
- ticketing
- reissue
- revalidation
- refund
- EMD
- error handling
- recovery
- airline-specific operational rules

For high-risk claims, seek the strongest available source and independent corroboration where feasible.

The higher the real-world consequence of being wrong, the higher the verification bar.

---

# 81. OPERATIONAL TRUTH VS TECHNICAL POSSIBILITY

Always distinguish:

> **Can the system technically accept this?**

from:

> **Is this the correct professional action in this situation?**

The curriculum must teach operational judgment where the evidence supports it.

Do not turn informal workplace habit into universal Amadeus law.

---

# 82. MISTAKE / RECOVERY COVERAGE

A work-ready curriculum must include realistic mistakes.

For important workflows, research:

```text
User goal
    ↓
Action
    ↓
Possible mistake
    ↓
System result
    ↓
Diagnosis
    ↓
Correction
    ↓
Resume workflow
```

Do not invent recovery behavior.

If the recovery procedure is unknown, mark it unknown and identify the missing evidence.

---

# 83. PNR KNOWLEDGE MUST BE RELATIONAL

Do not treat the PNR as a list of unrelated commands.

The knowledge model should be able to represent relationships between:

- itinerary
- passenger
- contact
- SSR/OSI
- seats
- remarks
- frequent-flyer information
- pricing
- ticketing
- EMD/ancillary elements
- queues
- PNR lifecycle

Where evidence supports it, capture dependencies and valid transitions.

---

# 84. PRICING / TICKETING MUST BE WORKFLOW KNOWLEDGE

Do not treat pricing and ticketing as isolated commands.

The knowledge plan must distinguish, where relevant:

- fare display
- informative pricing
- itinerary pricing
- pricing conditions
- ticketing preparation
- TST-related behavior
- ticket issuance
- revalidation
- reissue
- ATC
- manual reissue
- refund
- ATC refund
- EMD
- ancillary workflows

The exact boundaries must be evidence-driven.

---

# 85. ADVANCED MEANS SCENARIO COMPETENCE

Do not define Advanced simply as "more commands".

Advanced competence may require understanding complex operations and decisions, such as:

- non-homogeneous PNR situations
- revalidation vs reissue decisions
- manual reissue scenarios
- ATC workflows
- additional collection
- residual value
- penalty handling
- EMD workflows
- ancillary processing
- refund scenarios
- advanced operational cases

Only include specific scenarios when evidence supports them.

---

# 86. KNOWLEDGE ARCHITECTURE DECISION

Do not assume that one Markdown file or one JSON file is the correct final architecture.

Evaluate whether the safest architecture is:

- structured JSON
- Markdown documentation
- multiple structured files
- Markdown + structured data
- another hybrid approach

Choose based on:

- deterministic engine consumption
- traceability
- maintainability
- human readability
- schema validation
- relationships
- evidence preservation
- uncertainty preservation
- token efficiency
- resistance to hallucinated behavior

The goal is not minimum file count.

The goal is **maximum trustworthy reuse**.

---

# 87. AUTHORITATIVE KNOWLEDGE LAYERS

Recommend a clear ownership model.

At minimum consider separating:

```text
Commands
Behaviors
Workflows
States
Errors
Curriculum
Airline Context
Market Context
Evidence
Sources
Observations
Design Decisions
Uncertainty
```

Avoid duplicated technical facts with multiple conflicting owners.

---

# 88. TRACEABILITY REQUIREMENT

Every important learner-facing rule should be traceable through:

```text
Knowledge ID
   ↓
Evidence ID
   ↓
Source
   ↓
Exact claim
   ↓
Context / version
   ↓
Scope
   ↓
Status / confidence
```

An engineer or learner should be able to answer:

> **Why does AeroBridge teach or simulate this behavior?**

---

# 89. NEGATIVE KNOWLEDGE IS FIRST-CLASS KNOWLEDGE

Preserve meaningful negative findings:

- not valid in this context
- not established as current
- not established as Basic/Advanced
- cross-GDS contamination
- hotel/car extension
- historical only
- unsupported
- conflicting
- investigated and rejected

Do not store only successful candidates.

Negative findings prevent repeated research and future accidental promotion.

---

# 89A. PHASE 1 BASELINE — SUPPLIED AND INSPECTED DURING PASS C (updated at the Evidence/State Confirmation Gate; originally written as "reported history, not inspected evidence")

**Update, Evidence/State Confirmation Gate:** the four artifacts named below were subsequently supplied and directly inspected during Pass C. See `AeroBridge_PassC_Reconciliation_Report.md` for the full reconciliation this enabled. The section below is preserved exactly as originally written, because it was an accurate description of the state at the time — do not read it as describing the current state.

**Original section, preserved as historical context:**

Phase 1 (Amadeus Command Registry, Audit, Extensions, and lock-validation) was completed and frozen in a previous session. Its reported result:

- 88 Core commands
- 84 CANONICAL
- 4 SCOPED
- 29 command families
- 12/12 deliberate mutation self-tests passing

Its artifacts are:

- `aerobridge-final-canonical-registry.json`
- `aerobridge-command-audit.json`
- `aerobridge-out-of-scope-modules.json`
- `aerobridge-final-registry-lock-report.md`

These figures were treated as **reported project history for continuity** at the time this section was written, not as artifacts inspected in that session. ~~The underlying JSON/MD files are not assumed to be present.~~ **(No longer applicable — the files were subsequently supplied; see the update note above.)** Do not reconstruct their contents from memory where they have not actually been inspected. Do not casually reopen the frozen registry outside a proper reconciliation pass.

Proceed with current research independently of these artifacts where they have not been supplied to a given session, using this constitution and independently verified evidence — but treat the Phase 1 baseline's existence and reported scale as known project context. If a command, variant, qualifier, workflow identity, or classification is encountered that may overlap with Phase 1 territory:

1. Do not automatically accept what memory suggests the old result might be.
2. Do not automatically reject the possibility of overlap.
3. Do not invent a replacement classification to fill the gap.
4. Flag it explicitly as a Phase 1 comparison/reconciliation point (Pass C, §91.C).
5. Evaluate current evidence independently on its own merits.
6. Preserve the conflict/overlap for later reconciliation once the Phase 1 artifacts are supplied and inspected — as they now have been for Pass C specifically.

Goal: independent current research without accidental inheritance of unsupported historical assumptions, while remaining reconcilable against the authoritative Phase 1 baseline. **This goal was achieved for the material reconciled in Pass C; any future session working with these artifacts for the first time should still follow the original discipline above until it has itself directly inspected them.**

---

# 89B. PRIOR PROJECT DOCUMENT BOUNDARY

`Domain_SME_Validation_Brief.md`, the SME-01 through SME-10 claim register, Decision 7, Decision 8A, and other prior AeroBridge project documents are project-context artifacts, not Amadeus technical evidence. They may be used to understand project scope, constraints, existing decisions, and how the project is organized. They must not automatically become authoritative Amadeus technical evidence, and must not be treated as substitutes for the Phase 1 Command Registry, unless the product owner explicitly designates one of them as authoritative for a specific named Amadeus claim. For Amadeus technical truth, this constitution and properly evaluated Amadeus evidence (§5–§9A) govern.

---

# 90. DO NOT REOPEN THE FROZEN COMMAND REGISTRY WITHOUT CAUSE

The existing Command Registry is the Phase 1 baseline described at §89A.

Do not rebuild it from scratch.

Do not repeatedly re-prove settled identities merely because a new search result uses different wording.

Reopen a settled command identity only when there is:

> **new, materially stronger, Amadeus-specific evidence that could change the conclusion.**

Phase 2 may identify a genuine missing command or scope problem.

That does not mean the whole registry should be re-researched from zero.

---

# 91. RESEARCH PHASES FOR THIS MISSION — CHECKPOINT MODEL

Use the following research sequence unless evidence shows a better order. Every pass follows the canonical checkpoint template at §91.0, applied to that pass's own objective and scope — the template is defined once and is not restated under each pass.

## 91.0 — Canonical Checkpoint Template (applies to every pass below)

Each pass is defined by:
1. **Objective** — what this pass exists to establish (stated once per pass below).
2. **Scope boundary** — what is explicitly in and out for this pass.
3. **Required inputs** — what must already exist before this pass can start.
4. **Evidence recorded** — every claim touched, logged with Epistemic Type (§9A.1), Verification Status (§9A.2), Currentness Status (§9A.3), Evidence Strength (§9), and source.
5. **Findings surfaced** — new gaps, conflicts (with Conflict Disposition, §9A.4), and any Phase 1 comparison/reconciliation points (§89A).
6. **Progression criteria** — the pass may be considered complete when its stated objective is met and no unresolved high-impact (§56) item remains unlabeled.
7. **Escalation criteria** — a finding goes to the product owner rather than being silently resolved when it would change the frozen command boundary, contradicts the Phase 1 baseline, or is a §56 high-impact item with an UNRESOLVED conflict disposition.
8. **Pause conditions** — stop mid-pass, before continuing, if an escalation-criteria event occurs.
9. **Stop criteria (pass-level)** — this pass's own work is done; distinct from §102's mission-level stop rule, which governs when the entire mission is done, not any one pass.

At the end of every pass, answer explicitly, in writing: *What did we finish? What remains unresolved? What evidence was collected? What conflicts were discovered? What must happen before the next stage? Are we allowed to proceed?* A pass is not complete until all six are answered.

## 91.A — Pass A: Basic Foundations

Objective: establish the content and command/workflow coverage required for Basic.

## 91.B — Pass B: Advanced Air

Objective: establish Advanced content, especially complex PNR, pricing, ticketing, reissue, revalidation, EMD, ancillary, refunds, and operational reporting where relevant.

## 91.C — Pass C: Coverage Comparison

Objective: compare discovered knowledge against the Phase 1 Command Registry, Audit, and Extensions once their artifacts are supplied (§89A). Until then, record candidate Phase 1 comparison points rather than treating this pass as complete.

## 91.D — Pass D: Workflow / State / Error Gap Analysis

Objective: find missing context, sequence, state, negative, error, and recovery knowledge.

## 91.E — Pass E: Airline / EgyptAir Layer

Objective: separate carrier-specific realities from general Amadeus (§37–38, §75).

## 91.F — Pass F: Saudi Market Layer

Objective: identify market-relevant competence requirements (§41, §74).

## 91.G — Pass G: Currentness / Legacy Sweep

Objective: apply §9A.9 to every command/behavior candidate; quarantine unsupported old material.

## 91.H — Pass H: Adversarial Completeness Review

Objective: actively attempt to disprove the resulting knowledge coverage (§15, §95).

---

# 92. SEARCH PLAN

For each research topic:

1. Define the exact claim/question.
2. Search for the strongest primary Amadeus evidence.
3. Inspect the underlying source.
4. Extract only claim-relevant evidence.
5. Check interface and context.
6. Check currentness.
7. Check curriculum relevance separately.
8. Search for material contradiction if high-impact.
9. Classify the result.
10. Record the evidence and stop when sufficiently established.

Do not search randomly.

---

# 93. SEARCH TOKEN DISCIPLINE

Claude must minimize context waste without reducing verification quality.

Use:

- one precise question per search cluster
- strong-source prioritization
- evidence reuse
- targeted follow-ups
- source clustering
- concise evidence extraction
- explicit stop decisions

Do not repeatedly rediscover facts already verified.

Do not paste entire long sources into the working context when only a small claim is relevant.

Preserve enough source detail for traceability.

---

# 94. SOURCE AUTHORITY CONFLICT RULE

When sources disagree, authority is NOT determined by:

- source count
- website popularity
- convenience
- implementation simplicity
- recency alone
- how confidently the source is written

Evaluate:

- source type
- directness
- Amadeus specificity
- interface match
- technical relevance
- curriculum relevance
- currentness
- context
- provenance

A current authoritative Amadeus source may outweigh many older secondary sources.

An older authoritative source may still be essential for historical analysis.

Never silently convert source quantity into authority.

---

# 95. CRITICAL CLAIM REVIEW

Before accepting a high-impact claim, perform a second-pass challenge:

> **Could this be true but only in another context?**

> **Could this be historical rather than current?**

> **Could this be another Amadeus interface?**

> **Could this be airline-specific?**

> **Could this actually belong to another GDS?**

> **Could this be a workflow or qualifier rather than a command?**

> **Could the source prove existence but not behavior?**

> **Could the source prove curriculum placement but not technical validity?**

If yes, investigate before promotion.

---

# 96. MASTER CURRICULUM GAP ANALYSIS

At the end of research, produce a curriculum gap analysis that categorizes each important knowledge area using the topic-level Coverage Status vocabulary defined once at §9A.7. Where currentness is the actual blocking issue for a topic, name it using §9A.3's vocabulary directly in that topic's notes, rather than a separate category.

Do not declare completeness based on topic names alone.

---

# 97. JOB-READY ACCEPTANCE STANDARD

The final learning foundation should be sufficient for a learner to practice realistic work tasks without relying on memorized happy-path commands.

The learner should progressively demonstrate:

1. system understanding
2. command understanding
3. contextual correctness
4. PNR competence
5. pricing competence
6. ticketing competence
7. advanced change competence
8. error diagnosis
9. recovery
10. airline/context awareness
11. realistic scenario handling
12. professional operational judgment within the documented scope

This is the target competency model, not a claim that the simulator replaces real-company experience.

---

# 98. KNOWLEDGE BUILD PLAN

Do not immediately create dozens of files.

First determine the minimum coherent set of authoritative knowledge layers.

Then sequence the build to minimize duplication and rework.

The recommended decision process is:

```text
Existing evidence
      ↓
Coverage / gap analysis
      ↓
Knowledge model
      ↓
File architecture
      ↓
Priority order
      ↓
Evidence extraction
      ↓
Canonical knowledge
      ↓
Final audit
```

Improve this sequence if evidence shows a safer alternative.

---

# 99. REQUIRED MASTER DELIVERABLES

For this planning phase, produce:

## A. Master Curriculum & Knowledge Gap Analysis

Explain:

- what the supplied syllabus covers
- what it misses
- what broader Amadeus knowledge is essential
- what is EgyptAir-specific
- what is general Amadeus
- what is Saudi-market relevant
- what is airline-specific
- what is optional/extension
- what is historical/legacy
- what remains unknown

## B. Recommended Knowledge Architecture

Specify:

- knowledge layers
- entity types
- file types
- ownership
- IDs
- references
- authority
- evidence
- uncertainty
- currentness
- change control

## C. Knowledge Build Plan

Provide a prioritized sequence for building the actual knowledge files.

## D. Research Backlog

Prioritize unresolved questions by:

> **learner risk × operational importance × evidence gap**

## E. Acceptance Criteria

Define what must be true before each knowledge layer becomes learner-facing and before Engineering may consume it.

---

# 100. FINAL DECISION QUESTIONS

The analysis must answer explicitly:

1. Is the supplied EgyptAir Basic + Advanced syllabus sufficient by itself?
2. What critical Amadeus knowledge is missing?
3. What general Amadeus content should be added?
4. What Saudi-market knowledge should be added?
5. What airline-specific knowledge deserves a separate layer?
6. What historical/obsolete material must be excluded from current learning?
7. Which commands/behaviors require stronger verification?
8. Which workflows must be mastered rather than memorized?
9. What state/error/recovery knowledge is essential?
10. What knowledge architecture best prevents AI-generated behavior from becoming false Amadeus truth?
11. What remains genuinely unknown?
12. What is the safest stopping point before knowledge-building begins?
13. What criteria justify saying the knowledge is safe enough for learner-facing use?

---

# 101. FINAL DECISION STANDARD

Do not say:

> "We have enough because the syllabus looks comprehensive."

Do not say:

> "We have enough because the command registry is clean."

Do not say:

> "We have enough because many websites mention the same thing."

Instead conclude only using the Readiness Verdict defined once at §9A.8 — READY / READY_WITH_DOCUMENTED_LIMITATIONS / NOT_READY — and only when the evidence itself supports it, not the tidiness of the writeup.

---

# 102. MASTER STOP RULE

Once the required knowledge coverage is sufficiently established, stop expanding the scope merely to make the knowledge base larger.

Do not turn the project into an attempt to document every Amadeus product, every historical command, or every airline configuration.

The stopping criterion is:

> **The learner can be trained on the intended professional scope without the knowledge foundation silently teaching unsupported Amadeus behavior.**

Anything beyond that belongs in a separate extension or future research track.

---

# 103. FINAL MASTER PRINCIPLE

The research process must behave like a careful professional knowledge team, not like an autocomplete system.

Think broadly.

Verify narrowly.

Challenge aggressively.

Separate systems.

Separate interfaces.

Separate current from historical.

Separate technical truth from curriculum.

Separate curriculum from market requirements.

Separate airline-specific behavior from universal rules.

Separate documented behavior from observation and inference.

Separate real Amadeus behavior from AeroBridge design.

Preserve uncertainty.

Preserve negative findings.

Do not inflate command counts.

Do not invent missing behavior.

Do not promote legacy material into current learning without evidence.

Do not allow code to validate itself.

Do not allow source count to replace source authority.

Do not let token efficiency reduce verification quality.

When evidence is strong, commit to it.

When evidence is weak, quarantine it.

When evidence conflicts, preserve and resolve it explicitly.

When knowledge is missing, mark it missing.

The final purpose is simple:

> **AeroBridge should teach the learner what a competent Amadeus reservations/ticketing professional should actually know and do within the declared scope — and nothing that merely sounds like Amadeus.**

---

# REVISION CHANGELOG

This pass addressed five identified structural issues without weakening, removing, or simplifying any substantive safety protection.

1. **Duplication removed.** §71, §72, §73, §74, §75 were full restatements of §22, §43, §40, §41, §37–38 respectively; each is now a short pointer. Unique content in the removed duplicates (the five-step validity chain and worked YES/NO/UNKNOWN example from former §73; the "disruption/change handling" bullet and equation-form rule from former §74) was folded into the Part 1 originals at §40/§41 rather than lost.
2. **Taxonomy unified.** New §9A consolidates what were six separately-defined, partially-overlapping status systems (§17, §20, §49, §50, §76, §96, §101) into one taxonomy with explicitly independent dimensions: Epistemic Type, Verification Status, Currentness Status, Conflict Disposition, Curriculum Scope, Relevance Flags, Coverage Status, and Readiness Verdict. The former §17/§76 disagreement (four currentness values vs. five, "UNKNOWN" vs. "CURRENTNESS_UNKNOWN") is resolved in favor of the five-value set with CURRENTNESS_UNKNOWN as the single name for the unknown state. §17, §20, §49, §50, §76, §96, and §101 now point to §9A instead of each defining their own vocabulary; each retains whatever behavioral instruction was not pure vocabulary (e.g. §76's legacy-gate rule, §101's "do not say" guardrails).
3. **Worked example added.** New §9B walks one realistic item (SS) through every dimension in §9A, deliberately modeling an honest, mostly-unverified state rather than asserting confidence the current session hasn't earned — this is itself the example's point.
4. **Checkpoint structure added.** §91 now opens with a canonical checkpoint template (§91.0: objective, scope, inputs, evidence, findings, progression/escalation/pause/stop criteria, and six mandatory end-of-pass questions), applied once per pass (§91.A–H) instead of being silently absent.
5. **Scope boundary resolved.** §55 now states the owner-approved single standard — "minimum sufficient knowledge coverage required for genuinely work-ready competence" — replacing the earlier wording that could be read as two competing targets, with explicit operational bullets on when to include vs. exclude supporting (non-command) knowledge.

Additional changes made at the same time, at the product owner's explicit direction:

- New §8A (source authority is claim-specific, not global), extending §8's source-to-claim compatibility rule to cover single-source (non-conflict) evaluation, per §9A.9.
- New §89A (Phase 1 baseline: reported history, not inspected evidence) and §89B (prior AeroBridge project documents are context, not Amadeus technical evidence).
- §67's task boundary expanded to explicitly exclude PNR implementation alongside the previously-listed exclusions, and to state the positive scope list.

Nothing in §0–§66's substantive rules (truth-domain separation, evidence hierarchy, source validation, adversarial research, the four/five-domain model, code-as-evidence prohibition, and all other protections not named above) was altered.
