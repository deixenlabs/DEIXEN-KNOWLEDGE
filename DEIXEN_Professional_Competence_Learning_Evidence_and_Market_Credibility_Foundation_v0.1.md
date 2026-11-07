# DEIXEN — Professional Competence, Learning Evidence & Market Credibility Foundation

**Working integration draft:** v0.1  
**Prepared:** 7 November 2026  
**Status:** `WORKING SYNTHESIS — NOT CANONICAL — NOT OWNER-APPROVED — NOT AN IMPLEMENTATION AUTHORIZATION`  
**Primary source:** `DEIXEN — مراجعة أدلة الكفاءة المهنية: من تعلّم Amadeus للأداء المستقل.md` (Claude, 5 November 2026)  
**Current-context comparison:** DEIXEN-KNOWLEDGE `main` at `52064e719ec485004845631a147054488718827c` (7 November 2026); DEIXEN-APP `main` at `dde546952b07b17d9bd43722e298a02a3755a706` (last known inspected app snapshot, 27 October 2026).

---

## 0. Why this document exists

This document extracts and reorganizes the most valuable research, criticism, design implications, validation methods, and open questions from Claude's 5 November competence-evidence review. It then tests those ideas against the substantially newer DEIXEN strategic, architectural, case, quality, commercial, and collaboration material added on 6–7 November.

It is intended to become a **structured input to the DEIXEN Knowledge foundation**, not a replacement for any canonical source. It must remain open to criticism, new evidence, practitioner disagreement, owner decisions, and future revision.

### 0.1 What this document is — and is not

It **is**:
- a synthesis of report-derived findings and their implications for the newer DEIXEN direction;
- a map from useful ideas to the knowledge domains that should eventually own them;
- a record of unresolved evidence questions and future validation work;
- a tool for strengthening the product's professional credibility, learning quality, assessment integrity, market relevance, and launch discipline;
- a basis for later cross-review by Karim, ChatGPT, Claude, Gemini, and relevant human practitioners.

It **is not**:
- a new canonical decision or an amendment to D1–D97, D92, D97, the Operating Constitution, or any other owner-approved rule;
- a declaration that all ideas in Claude's report are scientifically established;
- a claim that DEIXEN currently implements the proposed architecture, assessment, evidence, commercial model, or professional validation;
- a finished curriculum, job analysis, accreditation, certification, or market-readiness standard;
- permission to alter GitHub, local project files, application code, or repository governance.

### 0.2 Source labels to use throughout DEIXEN Knowledge

| Label | Meaning | Permitted use |
|---|---|---|
| `CANONICAL / APPROVED` | Explicitly approved by the appropriate project authority and recorded in the governing source. | Binding within its stated scope. |
| `OWNER REQUIREMENT` | A clear owner-stated objective or constraint not yet converted into every detailed standard. | Guides research and proposals; does not automatically approve implementation details. |
| `RECORDED — NOT IMPLEMENTATION-VERIFIED` | Present in a specification or project document, but not confirmed in the current app/runtime. | May guide inspection; cannot be described as implemented. |
| `RESEARCH-SUPPORTED — ADJACENT` | Supported by research from a related but non-identical field, population, or task. | Informs a hypothesis; never proves DEIXEN-specific effectiveness. |
| `DIRECT / DOMAIN-VERIFIED` | Directly confirmed for the exact Amadeus domain, task, market, or implementation under the relevant authority. | May support claims only within the verified scope. |
| `PRACTITIONER-REVIEWED` | Reviewed by a suitably experienced practitioner, with identity, experience, market, scope, and limitations recorded. | Supports professional realism in that scope; does not replace Amadeus fact verification. |
| `EMPIRICALLY-VALIDATED` | Tested with relevant learners/users or an appropriate study design, with method and limitations recorded. | Supports only the outcome and population actually tested. |
| `HYPOTHESIS` | Plausible proposal not yet sufficiently evidenced. | May be prototyped or researched; must not become a binding requirement by implication. |
| `OPEN / HOLD` | A material question cannot yet be answered responsibly. | Keep visible; do not silently pass, fail, or invent an answer. |
| `SUPERSEDED` | Kept for history but no longer authoritative. | Historical reference only. |

**Important:** Claude's own `[Verified]` label means that a page or abstract was opened within the scope of that review. It does not mean that the full paper, all underlying studies, current commercial terms, or applicability to DEIXEN have been independently re-audited by this synthesis.

---

## 1. Executive synthesis — the strategic conclusion

Claude's most useful contribution is not a list of features. It is the argument that DEIXEN's credibility depends on a defensible chain connecting **real professional requirements → observable work behaviours → learning design → independent performance → credible evidence → appropriately limited claims**.

The newer DEIXEN direction now provides a broader context for this argument. DEIXEN is being developed as a professional work competence and training system for travel operations, with a possible longer-term identity as a specialist professional training and vocational-development institution. Its intended value is not the number of lessons, commands, screens, sessions, or features. Its value must be demonstrated through what learners can actually do, under what conditions, with what support, and with what limitations.

### 1.1 Six conclusions worth carrying forward

1. **Start from work, not from a list of commands.** Establish what entry-level and progressively more advanced travel/reservation professionals actually do in the target markets; derive tasks, competencies, curriculum, cases, and assessment from that evidence.
2. **Make the Professional Work Task a central organising concept.** A task can connect the customer request, information gathering, professional judgement, operational execution, system interpretation, validation, recovery, communication, and closure. This does not create a new top-level product area or replace Terminal.
3. **Keep system truth, task correctness, professional judgement, customer experience, and evidence qualification separate.** A system can accept an entry while the entry conflicts with the customer's request. A correct final state does not prove how it was reached. A satisfied customer does not make an incorrect task correct.
4. **Treat independent competence as a claim requiring multiple kinds of evidence.** One successful familiar task is one observation, not proof of transfer, retention, consistency, or workplace readiness.
5. **Use learning science as a source of testable design hypotheses, not as a promise of results.** Guided examples, fading support, retrieval, spacing, progressive variation, feedback, and error-management are promising, but their suitability and sequence must be tested with DEIXEN learners and tasks.
6. **Build credibility before marketing claims.** Verified Amadeus facts, practitioner-reviewed task realism, learner usability, assessment integrity, evidence traceability, legal/privacy safeguards, transparent commercial terms, and appropriately scoped claims are all parts of launch quality.

### 1.2 What success should mean for DEIXEN

The long-term ambition remains to help a complete beginner progress toward independently performing relevant travel-operation work and to support continued professional development after entry into work. This ambition should not be weakened merely because the evidence is not yet complete.

At the same time, DEIXEN must distinguish:

- **Strategic ambition:** what DEIXEN is being built to help people achieve.
- **Product capability:** what the current release genuinely allows a learner to do.
- **Demonstrated learning outcome:** what a learner has shown under defined conditions.
- **Validated competence claim:** what the available evidence supports across relevant tasks and observations.
- **Workplace outcome:** what has been observed in a real workplace or under appropriately supervised professional conditions.
- **External recognition:** what an employer, awarding body, Amadeus, IATA, or another institution has explicitly accepted.

Do not turn the lack of current proof into a smaller ambition. Do not turn the ambition into an unsupported claim.

---

## 2. Strategic fit with the newer DEIXEN direction

### 2.1 Product identity and institutional ambition

The strategic brief describes DEIXEN as a Professional Work Competence and Training System for travel operations, not a generic LMS, travel app, or generic SaaS dashboard. The longer-term organisational direction is to explore a specialist professional training and vocational-development institution, with DEIXEN as its proprietary training system.

The user's personal goal of becoming eligible to approach Amadeus is part of the strategic context. However, these are separate milestones and must never be conflated:

1. being able to contact or apply to Amadeus;
2. meeting the eligibility requirements of a specific programme;
3. being accepted into that programme;
4. establishing a commercial or training partnership;
5. securing investment, which is a distinct arrangement.

No future acceptance or partnership is guaranteed. Eligibility, current programme requirements, fees, and partnership terms must be checked against current official information when DEIXEN is ready to act.

### 2.2 The connected journeys must remain conceptually distinct

The newer strategy and architecture distinguish connected but separate journeys. The knowledge base should preserve at least these three:

| Lifecycle | What it represents | What DEIXEN must understand |
|---|---|---|
| **Customer Journey** | The customer's request, needs, disclosures, decisions, changes, experience, and final communication. | The customer is not a scripted source of instructional hints; their information and reactions are part of the work context. |
| **Learner / Professional Journey** | The person's development from beginner through supported practice, independent performance, evidence, and continuing development. | Completion, confidence, subscription duration, and activity are not equivalent to competence. |
| **Professional Work-Task Lifecycle** | The work itself, from receiving a request through clarification, decision, execution, validation, recovery, communication, and closure. | The task has its own facts, rules, state, acceptance criteria, and possible legitimate outcomes. |

The continuing-professional-development proposal adds a longer-term relationship with working professionals. It should extend the learner/professional journey without collapsing it into a permanent subscription or making DEIXEN necessary for someone to do their job.

### 2.3 Preserve the five product areas; do not create extra top-level areas from this report

The ideas below should be mapped into the existing five-area structure, subject to the unresolved naming/governance status of the first area (Home / Flight Deck):

- **Home / Flight Deck:** orientation, relevant next action, professional context, and clear explanation of evidence and learning priorities.
- **Learning:** concepts, prerequisite knowledge, customer-service learning, worked examples, explanation, retrieval, and demonstration.
- **Terminal:** operational practice, scenario execution, and the protected independent assessment mode, under the current Terminal authority and transcript constraints.
- **Scenario Bank:** discovery, organisation, metadata, status, prerequisites, variation, case eligibility, and work-task libraries. Execution remains in Terminal under D92.
- **Growth:** an honest, interpretable evidence portfolio, limitations, next learning needs, and long-term development—not a numeric employability or readiness meter.

The report does not justify a sixth top-level area. Assessment, Customer Interaction, Task Runtime, evidence interpretation, and professional development are capabilities or lifecycle concepts whose exact placement and ownership must be governed by the existing architecture.

### 2.4 Current governance discrepancies to resolve during the foundation phase

The 7 November read-only repository review exposed important synchronization issues that must be treated as foundation work, not silently ignored:

- The current `07_DEIXEN_Canonical_Decisions_and_Current_State.md` ends at D97. It does not contain D98 or D99.
- The `13_DEIXEN_Decision_Resolution_Register.md` is not synchronized to the newer D98 material.
- A Home/Learning insertion pack and a separate dual-tool design-role amendment both use or reference D98, creating a decision-number collision.
- The dual-tool design-role patches are proposed, not applied. D17/D93 authority must not be treated as amended by implication.
- Part XIX exists as a separate strategic addendum and has not been integrated into the main strategic document.
- The Product Quality Standards Framework is proposed, not canonical. Its README refers to `/standards/`, while the current inspected repository tree has files at the root and no `standards` directory.
- The repository's root `README.md` currently presents itself as a Standards Library README, while the directory structure and file paths do not yet reflect that proposed organisation.
- The product/experience index v0.4 references newer material and D98 status, while the canonical decision record remains at D97. This needs explicit reconciliation.

These discrepancies do not invalidate the new work. They show why the corpus needs an authoritative index, source ownership, document status, and synchronization rules before more additions are made.

---

## 3. The professional competence foundation

### 3.1 Begin with job/task analysis, not a pre-selected curriculum

The report correctly identifies a missing link in the older project model: historical levels or lesson slices cannot be assumed to represent the real requirements of a reservation/ticketing role.

A defensible chain should be:

**Target roles and markets → actual work activities → task analysis → required knowledge, skills, judgement and behaviours → observable performance criteria → learning and practice → independent assessment → evidence and limitations.**

The starting research must include Saudi Arabia, Oman, and the UAE in a balanced way. Do not let one country, one employer, one job advertisement, or one practitioner's habits define the full programme.

The job/task-analysis sample should distinguish, where evidence allows:

- airline, travel agency, corporate travel, travel management, and other relevant operating contexts;
- entry-level roles versus experienced or supervisory roles;
- reservation, ticketing, customer service, changes, cancellations, disruptions, and after-sales responsibilities;
- system-specific skills versus transferable professional skills;
- common tasks, high-risk tasks, rare tasks, and tasks where escalation is the correct outcome;
- employer-specific policies versus broader professional expectations.

Possible evidence inputs include current job advertisements, employer role descriptions, practitioner interviews, structured task walkthroughs, supervisor interviews, official operational guidance, sanitized SOP extracts where permission exists, and observed work where ethically and legally permissible.

**O*NET 43-4181.00 in Claude's report is an occupational-context reference only.** Its data is US-based; it describes tasks and work context rather than setting Gulf performance standards. The mention of “Amadeus Altea Reservation” also needs checking before anyone assumes it refers to the exact Amadeus environment taught by DEIXEN.

### 3.2 Candidate competence dimensions — retain as a research taxonomy, not a final standard

Claude proposed seven dimensions. The new strategy expands the context to whole professional work tasks. The following synthesis is a candidate taxonomy for research and practitioner validation:

| Candidate dimension | What it includes | Example of observable evidence | Main caution |
|---|---|---|---|
| 1. Operational accuracy | Correct commands, syntax, data elements, prerequisites, and system use. | Correct action and verified system result. | Command correctness alone does not establish task correctness. |
| 2. Workflow and sequence | Correct order, dependencies, required checks, and closure conditions. | Actions occur in a valid sequence and required steps are not skipped. | Do not judge by one memorised command sequence if more than one valid workflow exists. |
| 3. Interpretation of system information | Reading outputs, identifying relevant state, recognizing limits and unresolved conditions. | The next action is consistent with the output actually shown. | Do not invent or over-interpret Amadeus output. |
| 4. Customer understanding and discovery | Identifying goals, preferences, constraints, missing facts, ambiguity, and conflicts. | Appropriate question, confirmation, or clarification. | Customer dialogue is task information, not Coach assistance. |
| 5. Professional judgement and decision quality | Selecting, explaining, pausing, declining, or escalating based on the customer's request and valid options. | A defensible choice linked to stated needs and constraints. | Do not reward completion or sales at any cost. |
| 6. Communication and service | Clear explanation, expectation management, transparent conditions, consent, complaint handling, and professional closure. | Reviewed communication behaviour in context. | Customer satisfaction is not a substitute for a communication rubric. |
| 7. Verification and task consistency | Checking that the operational state matches the agreed request and case facts. | Explicit comparison of final state with task criteria. | A filed or priced booking does not by itself prove task acceptance. |
| 8. Error detection, recovery, and escalation | Recognising errors, understanding verified responses, correcting within authority, restarting, abandoning, or escalating. | Appropriate response after a known/verified error or conflict. | Never invent an Amadeus correction command or system error. |
| 9. Independence and support management | What help was available, requested, displayed, used, and relied upon. | Attempt-level support record and behaviour. | Exposure to a hint and actual use of a hint are different observations; current D97 rules remain authoritative. |
| 10. Consistency, retention, and transfer | Performance across cases, sessions, time intervals, and meaningfully different task contexts. | Comparable performance on protected variants over distinct occasions. | Exact counts and intervals must be empirically determined, not guessed. |

These dimensions should be reviewed for overlap, missing areas, and feasibility. They are not ten new scores, ten badges, or a final competency model.

### 3.3 Critical dimensions must not compensate for one another

Some requirements may be treated as critical conditions rather than averaged with other strengths. For example:

- accurate commands cannot compensate for booking the wrong customer request;
- a satisfied customer cannot compensate for unsafe, dishonest, or operationally incorrect work;
- excellent communication cannot compensate for an invalid operational outcome;
- a correct final state cannot compensate for prohibited assistance during an independent assessment;
- strong average performance cannot hide failure on an explicitly critical safety, integrity, or task-constraint requirement.

The exact list of critical criteria must come from job/task analysis and practitioner standard-setting, not from an arbitrary checklist invented by DEIXEN.

### 3.4 The task may legitimately end without completion

DEIXEN must not teach that every scenario should end in a completed booking or sale. A professionally correct outcome may be:

- ask for clarification;
- wait for missing information;
- present alternatives and obtain the customer's choice;
- explain that no available option meets the stated constraints;
- decline to promise or perform something that cannot be verified;
- pause, reset, abandon, or escalate within the declared task rules.

The correct professional result is the result that meets the task's actual acceptance conditions—not simply a completed workflow.

---

## 4. Professional Work Task and case architecture

### 4.1 The task as a connected work unit

The strategic direction moves from isolated commands/lessons/raw scenarios toward a connected Professional Work Task. Such a task can include:

1. receiving the customer's request;
2. understanding the real need, priorities, and constraints;
3. identifying missing, ambiguous, or conflicting information;
4. asking appropriate questions and confirming facts;
5. advising, comparing options, and explaining conditions or trade-offs;
6. confirming the customer's decision or consent where appropriate;
7. performing the verified operational workflow in Terminal;
8. interpreting the actual system response;
9. dealing with errors, changes, or unexpected conditions;
10. validating the operational result against the agreed request;
11. communicating the actual outcome accurately;
12. closing, following up, or escalating where required.

A scenario should be one coherent context. What the learner learns from the customer interaction changes what they should do operationally; what happens in Terminal influences what they should tell the customer next.

### 4.2 Do not collapse the actors or sources of truth

| Actor / layer | Owns | Must not do |
|---|---|---|
| Customer / virtual customer | Needs, facts, preferences, missing information, consent, objections, and reactions. | Teach commands, reveal hidden operational answers, or act as Coach. |
| Coach | Explanation, instructional hints, guided feedback, and post-attempt debrief within the permitted mode. | Impersonate the customer, alter Amadeus truth, or rescue an independent assessment attempt. |
| Amadeus simulation engine | Operational command acceptance, response, and system state within the verified simulation scope. | Decide whether the entire professional task matches the customer request. |
| Case / Task Runtime | Case facts, task context, allowed branches, task criteria, task-state validation, and coordination. | Become a second GDS engine or fabricate operational responses. |
| Assessment & Evidence | Interpret recorded events against support conditions, case criteria, provenance, and assessment rules. | Treat event capture, final-state success, or AI opinion as competence by itself. |
| Growth | Explain what the learner demonstrated, what remains untested, and what could be useful next. | Inflate evidence, create a numeric readiness meter, or conceal limitations. |

### 4.3 Separate the layers of correctness

The newer CP-001 stress test exposes an essential distinction:

1. **Operational state:** what the system accepted and what state it reached.
2. **Task consistency:** whether those accepted actions and resulting state match the case facts, customer request, and professional criteria.
3. **Professional judgement:** whether the learner made an appropriate decision under the conditions.
4. **Evidence qualification:** whether the attempt met the rules for the type of evidence being claimed.
5. **Customer experience:** how the customer experienced the process and outcome, recorded separately.

CP-001's RF finding is an example: the inspected RF handler accepts any non-empty text, while the case can require the actual requester identity. The engine can accept a value that is inconsistent with the case. The runtime should detect the task-level mismatch without falsifying the Amadeus response or inventing a command to correct it.

This is a core product-quality principle, not a one-off RF feature.

### 4.4 Reusable case-package blueprint

Every future case candidate should be authored against a common template. The following is proposed for the knowledge system, not a final schema:

| Field group | Required questions |
|---|---|
| Identity and status | Case ID, version, owner, status, markets, intended role/level, last review date. |
| Work purpose | What real task is represented? Why is it relevant? Is it common, high-risk, unusual, or advanced? |
| Customer context | Customer persona, goal, preferences, constraints, known facts, withheld facts, ambiguity, conflicts, consent rules. |
| Task boundary | What is in scope, excluded, assumed already selected/confirmed, and the legitimate stop/escalation outcomes? |
| Prerequisites | Which knowledge, skills, commands, and prior lessons are required? |
| Operational truth | Exact Verified Reference entries, command prerequisites, expected outputs, known errors, version/provenance, unresolved U-items. |
| Allowed paths | Valid actions, valid alternatives, prohibited actions, ambiguous paths requiring review. |
| Task acceptance | Final operational conditions, semantic consistency checks, customer-request alignment, critical conditions, closure criteria. |
| Branches | Customer change, missing fact, refusal, conflict, error, system acceptance of professionally wrong action, escalation, and recovery. |
| Support policy | Practice/assessment mode, allowed Coach behavior, hint levels, feedback timing, customer-information boundaries. |
| Evidence plan | Events, support exposure/use, run identity, task version, observations, assessor type, what can/cannot be inferred. |
| Validation | Amadeus verification, practitioner review, learner usability test, technical tests, accessibility/localization review. |
| Release gate | What must be resolved before use in practice, assessment, or production content? |

A case may be accepted for architecture testing while remaining on hold for real learning or assessment content. CP-001 is currently such a working candidate, not a production-approved professional case.

### 4.5 Build case families from work analysis, not only from one reservation slice

The strategy already identifies future work families such as new booking, changes, cancellations, disruptions/problems, and after-sales support. These should not be added merely because they are familiar travel topics. Prioritize them only after job analysis shows their relevance and the Verified Reference and practitioner evidence support their operational content.

Within each family, meaningful variation should change the work situation, not only names and dates. Possible variation dimensions include:

- missing or conflicting information;
- customer priorities and restrictions;
- choice between superficially plausible options;
- a change during the task;
- an error or unexpected verified system response;
- different but valid procedural routes;
- need to pause, decline, or escalate;
- different customer communication requirements.

A dedicated case type for **system-accepted but professionally/task-incorrect actions** is worth retaining. It should not falsify the system or invent errors. The case/runtime should reveal the inconsistency through task criteria, not by changing the engine's factual behavior.

---

## 5. Learning-design implications worth preserving

The research reviewed by Claude suggests several promising methods. Nearly all are adjacent-domain evidence, not direct evidence on GDS beginners. Their value is to guide careful design and testing.

### 5.1 Guided learning for true beginners

For a complete beginner, test a sequence such as:

- explain the purpose and meaning before demanding command production;
- show a complete worked example and explain meaningful outputs;
- practise a small number of related operations with strong support;
- gradually hide or fade parts of the example;
- ask the learner to retrieve or produce the next action without choosing from a visible list;
- increase task integration only after prerequisite understanding is demonstrated.

Claude's report points to Alfieri et al. (2011) and Lazonder & Harmsen (2016) for the value of guidance, worked examples, feedback, and scaffolding over unsupported discovery. The evidence is educational/general, not Amadeus-specific. The older Phase 5 finding that the lessons and Ghost were difficult for a beginner is a useful warning, but it was not a controlled learner study.

### 5.2 Retrieval practice, not just re-exposure

Reading or watching a command is not the same as being able to recall and produce it. A useful hypothesis is to ask learners to produce an action from the task description, then interpret the actual system output.

Rowland (2014) supports free recall over recognition for retention. Pan & Rickard (2018) report a moderate transfer effect in their meta-analysis, but note moderators and publication-bias concerns; transfer can disappear when important conditions are absent. Therefore:

- use retrieval prompts as a learning method;
- do not assume retrieval automatically transfers to unfamiliar multi-step workflows;
- vary prompt format and task context when evaluating transfer;
- preserve the distinction between retrieval checks during learning and protected assessment tasks.

### 5.3 Spacing and retention

Cepeda et al. (2006, 2008) support the general idea that useful review intervals depend on the desired retention interval. Their findings are not an Amadeus workflow schedule.

DEIXEN should eventually ask: **How long does the learner need to retain this skill before a realistic work task, refresher, or later task is expected?** The interval should be justified by the intended use and measured in learner evidence—not chosen as a convenient 24-hour or 48-hour product rule.

Track declarative knowledge and procedural skill separately where feasible. Taylor et al. (2005), as summarized in Claude's report, notes that knowledge and work behaviours can decay or persist differently.

### 5.4 Blocked practice before appropriate variation

For beginners, first allow practice on a small, coherent set of related operations. Then introduce meaningful variation and interleaving when the learner has the prerequisites to benefit.

Brunmair & Richter (2019) found that interleaving effects depend on material similarity and task characteristics; some categories favoured blocked practice. Wulf & Shea (2002) caution that principles for simple skills do not necessarily generalize to complex skills and that excessive load can hinder learning.

Thus, progressive variation is a hypothesis, not an unconditional rule. Do not introduce every difficulty dimension at once.

### 5.5 Error-management and recovery

Keith & Frese (2008) found benefits for error-management training in a meta-analysis, including transfer effects in their reviewed settings. This supports investigating deliberate error/recovery practice, but not exposing a true beginner to unbounded failure from the first lesson.

The likely design question is how to progress from:

1. clear instruction and safe demonstration;
2. guided practice with common mistakes explained;
3. bounded error recognition and recovery;
4. unfamiliar but verified problem situations;
5. independent assessment of appropriate recovery or escalation.

The sequence is a hypothesis and needs learner/practitioner testing. Only Amadeus errors and responses supported by the current Verified Reference may be shown as real system output.

### 5.6 Feedback and debriefing

Feedback should identify the relevant gap and help the learner reason about it. A generic “wrong” message or revealing the final answer may create activity without useful learning.

Test feedback that is:
- specific to the observed behaviour or output;
- linked to the task's criteria and the learner's current level;
- clear about whether the issue is system syntax, sequence, interpretation, task judgement, communication, or recovery;
- given at the right time for the learning mode;
- withheld during independent assessment until the attempt is closed and its evidence snapshot secured.

Wisniewski et al. (2020), Cook et al. (2013), and Cheng et al. (2014) are adjacent research references in Claude's source review. Their effect estimates should not be copied into DEIXEN specifications as predicted outcomes.

### 5.7 Adaptation and diagnosis must be evidence-led

An event log records what happened; it does not establish why it happened. An `errorCategory` or one failed attempt is not causal diagnosis.

A defensible future pattern is:

**Observed event → provisional diagnostic hypothesis → discriminating probe → appropriately selected support → later test on a different case and/or after an interval.**

Candidate error classes worth investigating include:
- prerequisite/knowledge gap;
- syntax or data-entry error;
- sequence/dependency error;
- system-output interpretation error;
- professional decision error;
- customer communication gap;
- failure to recover or escalate appropriately.

The system should not let an unvalidated automated diagnosis decide a high-impact learner pathway or competence judgement. Compare automated classifications with trained human reviewers first. Diagnostic labels guide support; they do not themselves prove competence.

A future adaptive-practice capability should be **deferred pending DEIXEN data, not declared scientifically impossible**. Start with transparent, explainable rules if and when the evidence supports them. Keep them separate from protected assessment selection so that adaptation does not reveal answers or contaminate test cases.

### 5.8 Speed comes after accuracy and judgement

Time may eventually be a useful contextual observation, especially where real work involves time pressure. But no fixed speed threshold should be invented before understanding:
- what task is being timed;
- whether the learner is thinking, reading, typing, or waiting for the system;
- whether the time measure is fair across language and device conditions;
- what the job actually requires;
- whether speed worsens accuracy or professional decisions.

The first objective should be accurate, appropriate, independent task performance. Speed is a later dimension to study, not an early gamification target.

---

## 6. Independence, transfer, retention, and evidence architecture

### 6.1 A ladder of claims — do not skip levels

Claude's report offers a useful ladder. The following version preserves its logic while aligning it with the new architecture:

| Level | What may be claimed | Minimum conceptual condition | What it does not prove |
|---|---|---|---|
| 1. Recorded activity | An event or attempt occurred. | A task/session event was captured. | Correctness or independence. |
| 2. Independent attempt | The attempt met the applicable no-help conditions. | Support exposure/use and assessment mode are recorded; the governing D97 rules are satisfied. | That the attempt was correct or competent. |
| 3. Qualified performance on one task | The learner independently met task-specific criteria. | Required critical criteria, process conditions, and final task checks are met. | Consistency across cases. |
| 4. Repeated performance | The learner met the criteria on meaningfully different cases and occasions. | Distinct cases/sessions with comparable reviewed standards. | Transfer to a new task structure. |
| 5. Near transfer | The learner succeeded on protected, unfamiliar but valid variants or structurally changed tasks. | Case equivalence and task differences are reviewed; alternatives are accepted where professionally valid. | Far transfer or real workplace performance. |
| 6. Recovery capability | The learner detected and responded appropriately to a verified problem or error. | Observable diagnosis, action, recovery/stop/escalation, and outcome. | Performance under real-world pressure unless separately tested. |
| 7. Retention | The learner reproduced required performance after a meaningful interval. | Delayed attempt without intervening answer exposure, using a suitable comparable variant. | Retention beyond the measured interval. |
| 8. Consistency across conditions | Performance remains within criteria across tasks, occasions, and relevant evaluators. | Adequate observations and reliability/generalizability evidence. | Workplace readiness by itself. |
| 9. External/practitioner corroboration | An appropriate external party reviewed the performance or its relation to work. | Qualified reviewer, clear scope, method, and traceable record. | Official certification or employer recognition unless explicitly granted. |
| 10. Workplace evidence | Performance has been observed in an actual or properly supervised workplace context. | Employer/practitioner-defined conditions and evidence, with consent and safeguards. | Universal ability across employers, tasks, or markets. |

These are conceptual claim levels, not new learner-facing statuses. Preserve existing qualitative Growth status vocabulary unless formally reconsidered.

### 6.2 Independence is not the same as success

A learner may complete a step without help after having made several unsuccessful attempts. That can be recorded as an independent entry or action under a narrow event definition, but the process quality and task result must remain visible.

The evidence model should distinguish at least:
- first-attempt correctness;
- number and type of attempts;
- hints available, displayed, requested, and actually used;
- Ghost exposure and whether the relevant answer was already revealed;
- corrective feedback exposure;
- learner action after an error;
- final operational state;
- task consistency against the case;
- assessment qualification under the applicable rules.

Do not let a binary independence flag hide the quality of the path to success. Do not rewrite the already-governed hint rules informally; this is a proposal to make process evidence more informative while respecting the current authority.

### 6.3 Protected independent assessment

The new strategic and architecture proposals correctly treat assessment as a professional work scenario sourced/organised through Scenario Bank and executed in Terminal under a separate independent-assessment mode.

A qualifying independent attempt should be able to establish, as applicable:
- a fresh, isolated assessment run/session identity;
- a clean operational state;
- a distinct, unpractised task or sufficiently distinct protected variant;
- no Ghost exposure in the assessment session;
- no instructional Coach hints, answer-revealing feedback, or rescue during the attempt;
- customer responses remain ordinary task information, not instructional help;
- required task steps and evidence belong to the same assessment chain;
- the case/version, variant, support policy, run identity, and relevant events are preserved;
- feedback is released only after the attempt is closed and the evidence snapshot is secured.

An activity may be recorded even when the qualifying conditions are not met. It must not be mislabelled as qualifying independent evidence.

**Implementation caution:** D97 is a canonical decision, but the November architecture review found that the inspected app snapshot did not yet enforce all of the intended independent-assessment conditions. A governance decision and an implemented runtime rule are separate facts.

### 6.4 Assessment content separation: protect the case, not the skill domain

R2 from Claude is important but should not be oversimplified. Teaching and assessment will naturally involve the same professional competencies. A learner can learn the skill of creating a reservation and later be assessed on a new reservation task.

What must be protected is the **specific assessment case, answer path, task variant, and relevant structural challenge**. Repeating the same customer facts and workflow may reward memory of the case rather than transfer of the skill.

Future assessment design should therefore define:
- a case bank with practice/assessment eligibility metadata;
- protected assessment variants not exposed through practice or Ghost;
- meaningful variation, not cosmetic name/date swaps alone;
- equivalence review by qualified practitioners for tasks intended to be comparable;
- exposure/leakage controls and retirement rules for compromised items;
- separate records for task familiarity and structural difference.

### 6.5 Valid alternative solutions

Do not assess by exact command-string matching alone when more than one operational route may be valid. Where applicable, judge the resulting state and task constraints, and compare the path against approved alternatives.

A solution outside the currently approved set should not automatically be treated as wrong if the engine accepts it. It should be flagged for review by a suitably qualified reviewer. The Verified Reference remains authoritative for Amadeus facts; professional review cannot invent system behaviour.

### 6.6 Evidence strength should be descriptive, not collapsed into one score

For each material evidence claim, preserve a profile of:
1. number of relevant occasions;
2. diversity/structural difference of cases;
3. interval between observations;
4. support conditions (availability, exposure, use);
5. evaluator type (automated rule, practitioner, blinded evaluator, employer); and
6. record strength/provenance (local activity record, authenticated server record, supervised observation, externally verified evidence).

Do not create a composite percentage or readiness index from these dimensions. The user-facing Growth vocabulary and the Constitution's existing restrictions remain in force unless explicitly reconsidered.

### 6.7 Evidence integrity, privacy, and provenance

The report correctly notes that a browser `localStorage` record can be changed by the user and is not authenticated external evidence. It remains useful for early personal practice and local prototypes; it must not be presented as secure proof to an employer or partner.

A future evidence architecture should examine:
- event identity and sequence;
- account/user authentication;
- task/case version and content provenance;
- tamper-evident or auditable records where needed;
- assessor identity and review history;
- export and verification methods;
- learner consent, access, correction, retention, and deletion rights;
- minimization of personal/customer data;
- separation of payment credentials from learning evidence;
- safeguards against sharing real customer data or confidential employer procedures.

This is a future evidence and privacy design requirement. It is not an instruction to implement a backend now. Temporary local storage remains a prototype choice and must be labelled honestly.

---

## 7. Customer communication, customer experience, and language

### 7.1 Customer service is a work competency, not a decorative dialogue

The report highlights the importance of customer interaction and the absence of a validated rubric in the older learning design. The new architecture now separates the Customer from Coach and places Customer Interaction inside the same work-task context.

The eventual standard should cover, where job analysis supports it:
- understanding needs and priorities;
- active listening and question selection;
- clarifying missing or conflicting information;
- confirmation and expectation management;
- explaining options, restrictions, conditions, costs, and uncertainty;
- consent and transparent disclosure;
- handling objection, frustration, complaint, and change;
- explaining limitations without overpromising;
- closing and follow-up;
- pause, decline, or escalation when appropriate.

The CP-001 practitioner review is an initial bounded review, not validation of every customer-service skill or every target market. One practitioner response can surface issues; it cannot establish a universal service standard.

### 7.2 Three separate outcomes

Always distinguish:

1. **Operational performance:** whether the system-level work was executed correctly.
2. **Professional performance:** whether the learner acted appropriately, transparently, and in accordance with the customer's request and relevant criteria.
3. **Customer experience/satisfaction:** how the customer experienced the interaction and outcome, and why.

A customer can be dissatisfied despite proper professional conduct when no option meets their needs. A customer can be pleased even though the employee overpromised or performed an incorrect action. Neither satisfaction nor dissatisfaction alone establishes competence.

### 7.3 English voice interaction is a separate capability to validate

The newer strategic brief raises English spoken interaction and voice practice. The competence-evidence foundation should preserve the following safeguards:
- spoken English practice may support intelligibility and professional communication;
- language coaching must be separated from operational competence assessment;
- speech-recognition failure must not be mistaken for poor professional competence;
- accent must not be treated as a defect to erase; the goal is understandable and effective communication;
- do not equate fluency, accent, or microphone quality with job performance;
- Arabic/English and RTL/LTR conditions require their own usability and accessibility checks;
- voice privacy, recording, consent, retention, and deletion rules must be defined before collection.

The report's research appendix does not establish DEIXEN voice effectiveness. This remains a separate hypothesis and validation stream.

---

## 8. Market relevance and competitive credibility

### 8.1 Build market evidence for three markets, not one proxy market

Target markets are Saudi Arabia, Oman, and the UAE. The current product scope should not be represented as validated for all three until the job/task analysis and practitioner evidence are balanced across them.

The research should capture:
- role titles and entry requirements;
- actual daily and occasional work tasks;
- required GDS/system familiarity and exact platform variants;
- customer-facing expectations and language needs;
- ticketing/reservation duties and role boundaries;
- operational policies that differ by employer or country;
- common mistakes, difficult cases, escalation expectations;
- hiring expectations and what employers treat as evidence of ability;
- differences between airline, agency, corporate travel, and other relevant settings.

Record the source, date, employer/market context, role level, and whether the evidence is an advertised requirement, practitioner opinion, official rule, or observed workflow. Do not allow a job advertisement to define actual competency standards by itself.

### 8.2 Competitive positioning — hypotheses until independently tested

Claude's report suggests possible differentiation through:
- integrated professional work tasks rather than command memorization alone;
- protected independent performance assessment rather than knowledge checks alone;
- evidence transparency (conditions, support, case variation, time interval, reviewer, provenance);
- targeted diagnosis and recovery practice;
- Arabic/bilingual learning where actual market demand is established;
- customer interaction integrated with operational work;
- retention and continuing professional development after the foundation path.

These are **differentiation hypotheses**, not verified competitive advantages. Competitors may offer features not described on the pages reviewed. A page's silence does not prove the absence of a capability.

A future competitor matrix should compare, at minimum:
- exact audience and entry prerequisites;
- platform and GDS coverage;
- real environment versus emulator/simulation;
- curriculum/work-task coverage;
- learning support and practice structure;
- assessment method (knowledge test, practical task, supervised assessment, or mixed);
- certificate/credential issuer and scope;
- language and accessibility;
- practitioner involvement;
- continuing development;
- access duration, pricing, and commercial terms;
- disclosed limitations and evidence of outcomes.

Use dated source captures and mark missing information as `NOT DISCLOSED IN SOURCE`, not `NOT OFFERED`.

### 8.3 Amadeus/IATA relationship and claims

Official certification and partnership authority belong to the issuing organisation. DEIXEN must not imply endorsement, accreditation, certification, or employer recognition without explicit authorization.

Keep distinct:
- DEIXEN's own learning/evidence record;
- an official Amadeus-issued certificate or badge;
- an IATA course/certificate;
- an Amadeus Learning Partner status held by an institution;
- an employer's own assessment or recognition.

The November 5 report's course prices, exam format, access terms, and badge details are a dated market snapshot. Do not use them for a launch decision without checking the current official pages and eligibility conditions again.

### 8.4 Honest launch language

Until stronger evidence exists, appropriate claims should describe the actual product and actual learner evidence, for example:

- “structured practice in a DEIXEN Amadeus training simulation”;
- “the learner completed a defined task under the stated support conditions”;
- “the learner independently met the published criteria on these specified simulation cases” — only when the qualification rules were actually met;
- “practitioner-reviewed case” — only for the exact case, scope, reviewer, and version reviewed.

Avoid claims such as:
- job guaranteed;
- job-ready or employer-ready as a general status;
- official Amadeus training/certification/endorsement without authorization;
- recognized by employers without evidence;
- better than IATA/Amadeus without a fair comparative study;
- “scientifically proven” based only on general learning research.

Keep workplace readiness as a long-term objective while making every public claim specific, dated, and supported.

---

## 9. Commercial and continuing-development foundations

The commercial material added on 7 November proposes an `Explore → Full Access → Continuing Professional Membership` model. It remains a hypothesis, not an approved launch offer.

### 9.1 Explore

A free, limited, genuine learner-operated experience should let a prospective learner understand the product and operate a bounded beginner task. It must not be confused with watching a scripted Ghost demonstration, access to the full curriculum, live Amadeus use, or qualifying independent assessment evidence.

### 9.2 Full Access

The paid foundation experience should be coherent rather than fragmented into arbitrary micro-purchases. The offer must include only content and capabilities that are actually verified, implemented, and available. Do not sell protected assessment/evidence principles as decorative add-ons while claiming those principles are DEIXEN's differentiator.

### 9.3 Continuing Professional Membership

The value proposition should be recurring professional value: refreshers, difficult/rare cases, advanced validated domains, changing procedures, customer service, and professional development. It should be voluntary. A learner must not become dependent on an active DEIXEN subscription to perform their job.

### 9.4 Learning outcomes and commercial outcomes must remain separate

Do not use subscription duration, screen time, renewal, payment, feature use, or time spent in DEIXEN as a proxy for competence.

Track separately:
- **Learning/professional outcomes:** independent performance, errors/recovery, retention, transfer, practitioner observations, limits, and workplace feedback where available.
- **Commercial/customer outcomes:** Explore activation, conversion, purchase, price acceptance, refunds, renewal, cancellation reasons, support cost, content maintenance, and contribution margin.

A learner who achieves the goal and does not renew may represent a successful learning outcome. A paying or renewing learner may still not have demonstrated competence.

### 9.5 Pricing is not approved by inclusion in a document

The EGP and USD figures in the commercial file are test anchors only. The 3-/6-month periods must be justified by actual curriculum learner-hours and pilot data, not chosen first and forced onto the curriculum. Unit economics, payment fees, taxes, legal entity, consumer law, privacy, refunds, cancellation, renewal, and evidence retention need market-specific review.

---

## 10. Scientific validation programme — retain the logic, integrate with the new architecture

Claude's V0–V7 sequence is valuable because it asks what the weakest link in the evidence argument is before making a larger claim. It should be preserved as a **proposed validation programme**, not a delivery roadmap or a precondition that blocks all early prototyping.

| Stage | Question | Proposed method | Acceptable output | Key dependency |
|---|---|---|---|---|
| V0 — Job/task analysis | Do the tasks and criteria represent relevant work in Saudi Arabia, Oman, and the UAE? | Balanced practitioner interviews, work/task walkthroughs, role documents, job evidence, expert panel. | Reviewed task map, scope, and performance criteria with market context. | Before finalizing competency and curriculum requirements. |
| V1 — Scoring and reviewer agreement | Do assessments reflect observed performance, and do reviewers agree? | Double-score a suitable sample; blind where feasible; report ICC/kappa and confidence intervals. | Transparent agreement evidence and limitations. | Clear rubrics, trained reviewers, task definitions. |
| V2 — Generalizability | How many tasks, occasions, and reviewers are needed for a stable decision? | Generalizability study (persons × tasks × occasions × reviewers) and decision study. | Observation requirements derived from data, not invented counts. | V1 and a suitable task/assessment sample. |
| V3 — External beginner usability/feasibility | Can genuine beginners understand and use the experience? Where do they fail? | Formative pilot with learners outside the project team/family; observation, think-aloud, event records. | Usability/feasibility findings, not an effectiveness claim. | A stable enough prototype and safe test tasks. |
| V4 — Comparative effectiveness / transfer | Does DEIXEN improve delayed independent performance on unseen tasks relative to a fair comparator? | Preregistered design where appropriate; protected tasks; blinded reviewers; sample-size planning; suitable comparison. | Predefined outcome and analysis with limitations. | Valid measurement and acceptable reliability/generalization evidence first. |
| V5 — External criterion relationship | Does simulated performance relate to an external professional indicator? | Compare with an official credential, practitioner/supervisor assessment, or supervised work evidence where valid and accessible. | Relationship/validity evidence with effect and uncertainty. | Access to an appropriate external criterion and consent. |
| V6 — Consequences and fairness | Are learner decisions fair and are some groups disadvantaged? | Examine language, prior experience, accessibility, demographic/context groups where lawful and ethical; review decision consequences. | Documented fairness, limitations, and correction route. | Adequate sample and lawful data governance. |
| V7 — Revalidation | Do claims remain valid after domain, task, market, or product changes? | Change-triggered review and targeted revalidation. | Traceable updates and recheck records. | Change monitoring and source ownership. |

### 10.1 Do not manufacture statistical thresholds

Do not invent sample sizes, success counts, cut scores, retention intervals, ICC cut-offs, equivalence margins, or speed thresholds because they appear reasonable. Derive them from the intended claim, task risk, pilot estimates, qualified standard-setting, and suitable statistical design.

The values quoted in the report from medical simulation or educational research must not be imported as DEIXEN performance targets.

### 10.2 Separate formative testing from effectiveness claims

A usability pilot can identify confusion, friction, poor wording, excessive cognitive load, or technical failure. It does not prove that DEIXEN improves competence.

An internal owner/family trial can provide early observations. It does not replace learners outside the project team or independent evaluators.

A single practitioner review can improve the case. It does not establish universal professional validity for every market or task family.

### 10.3 Use the right reviewer for the right question

- Amadeus syntax/output: current D12-approved verification and the Verified Reference.
- Task realism: relevant reservation/ticketing practitioners and supervisors.
- Market relevance: evidence from the target country, role, and employer context.
- Learning usability/effectiveness: actual learners and suitable study designs.
- Scoring reliability: trained evaluators and appropriate reliability analysis.
- Software behaviour: current code, tests, and observed runtime.
- Legal, privacy, IP, consumer and payment matters: qualified legal/payment review in the applicable markets.
- Commercial willingness to pay: actual market tests, not model opinion or expressions of interest alone.

No single reviewer, AI model, study, or source answers all these questions.

---

## 11. Evidence and source quality — what Claude's research can and cannot support

### 11.1 What to preserve from the research review

Keep these evidence clusters in the research library, each with its applicability boundary:

| Research cluster | Sources highlighted in Claude's report | Useful implication | Boundary |
|---|---|---|---|
| Competency-based assessment | IATA Competency Assessment and Evaluation Guidance; Kane/Cook validity argument; Norcini standard-setting. | Observable behaviour + conditions + standard; multiple observations; trained evaluators; explicit validity reasoning. | IATA guide was written for pilots/instructors/evaluators, not reservation agents. |
| Occupational context | O*NET 43-4181.00. | Useful preliminary map of reservation/ticketing work and customer-facing context. | US data; not Gulf job standards or a validated task standard. |
| Guided instruction | Alfieri et al. (2011); Lazonder & Harmsen (2016). | Guidance, examples, feedback, and scaffolding are worth testing for true beginners. | General education evidence; exact GDS transfer unproven. |
| Retrieval practice | Rowland (2014); Pan & Rickard (2018). | Active recall may be more useful than passive re-exposure; vary tasks to test transfer. | Transfer is conditional; much research is academic/verbally based. |
| Spacing and retention | Cepeda et al. (2006, 2008); Taylor et al. (2005). | Set intervals around intended retention; measure knowledge and skill separately. | No validated GDS interval is supplied. |
| Interleaving and complexity | Brunmair & Richter (2019); Wulf & Shea (2002). | Interleaving/variation can help in some conditions; cognitive load must be managed. | Effects depend on task/material; not a universal beginner rule. |
| Simulation and fidelity | Cook et al. (2011, 2013); Norman et al. (2012); Hamstra et al. (2014). | Functional task alignment matters; visual realism alone is not sufficient justification. | Predominantly medical simulation; not a GDS experiment. |
| Error management | Keith & Frese (2008). | Bounded, supported error exploration may help adaptive transfer. | Task/population details and GDS applicability are not established in the report. |
| Assessment reliability | Brannick et al. (2011); Crossley et al. (2011); Weller et al. (2014); Koo & Li (2016); Bloch & Norman (2012). | Evaluator agreement and task sampling matter; use appropriate reliability methods. | Mainly medical/clinical assessment; exact reservation-assessment design remains to be tested. |
| Bias and retesting | Hróbjartsson et al. (2013); Hausknecht et al. (2007); Davis et al. (2006). | Blind reviewers where appropriate; avoid same-form practice effects; do not trust self-confidence as competence evidence. | Findings come from other fields and assessment types. |
| Programmatic assessment | van der Vleuten et al. (2012); Schut et al. (2021). | Triangulate evidence carefully; avoid information overload and rigid cut-offs without validation. | Conceptual/health-professions context; not a ready-made DEIXEN model. |
| Direct/near domain evidence | Yong (2013, Galileo CRS survey); Murthy et al. (2008, call-centre simulation). | Useful leads for further research on GDS-adjacent and service-agent training. | Study details are limited in the pages/abstracts reviewed; neither proves Amadeus training effectiveness. |

### 11.2 Research audit limitations must travel with every claim

Claude explicitly states that the review was directed rather than systematic; there was no preregistered search protocol, formal inclusion/exclusion criteria, independent second reviewer, or full risk-of-bias appraisal of the studies inside the meta-analyses. Many effect sizes were taken from abstracts only. Some references were candidates not opened; some bibliographic details marked with `†` were not verified from the opened source. Two references in the annex were bibliographic leads only and no findings from them were used.

Therefore the evidence library should not simply copy all numerical estimates into a standard. It should:
- preserve Claude's complete original report unchanged as a historical research artifact;
- create an independently checked source register before any research-derived rule is adopted;
- separate abstract-only findings from full-text review;
- record source type, population, task, comparator, outcome, effect estimate, uncertainty, risk of bias, and applicability;
- mark unverified bibliographic details and inaccessible full text;
- preserve contrary findings and moderators rather than selecting only supportive results.

### 11.3 Important interpretations not to lose

- A large effect against no intervention does not prove superiority over a credible alternative.
- Deliberate practice intervention effects and the proportion of variance explained by practice are different questions; they cannot be used to contradict one another without context.
- Retrieval practice does not automatically transfer to structurally different professional tasks.
- High-fidelity visual simulation is not automatically more educationally effective than a simpler, functionally aligned simulation.
- A single aggregate transfer effect may hide important dimensions of transfer.
- A more demanding assessment can reduce pass rates without necessarily being more valid; standards require qualified judgement.
- A non-blinded evaluator may be biased; a blinded evaluator still needs a clear rubric and training.
- Self-confidence and self-assessment must not replace observed performance.

---

## 12. Critical review of Claude's 12 recommendations

All twelve items below remain **recommendations from Claude's report**, not approved DEIXEN decisions. Their disposition is updated for the 6–7 November strategy and architecture.

| ID | Original recommendation | Updated disposition | What to carry forward |
|---|---|---|---|
| R1 | Define `CONSOLIDATED` and `TRANSFERRED` by conditions rather than success counters. | **Keep open; high priority.** The current competence model and the new strategy need stronger evidence semantics. No arbitrary count or interval should be set. | Revisit the skill-state definitions against distinct cases, occasions, retention and transfer evidence; use data to set requirements. |
| R2 | Separate assessment content from training content. | **Keep as a critical validity requirement, with more precise wording.** Shared competencies are normal; the exact case/variant and assessment answer path must be protected. | Protected unpractised, meaningfully varied assessment tasks, leakage controls, and equivalence review. |
| R3 | Make delayed reassessment part of retention evidence. | **Keep as a strategic research requirement.** Do not fix the interval yet. | Retention interval tied to intended professional use and tested with new but comparable tasks. |
| R4 | Treat customer communication as a distinct, non-compensatory evidence dimension, initially illustrative. | **Strengthened by the new Customer Interaction architecture.** Still requires validated rubrics and market-specific review. | Keep separate from operational accuracy and customer satisfaction. |
| R5 | Remove `job-ready` and `Saudi Market Readiness` wording until validated. | **Revise the recommendation.** Retain professional readiness as a strategic objective; restrict public claims and displayed conclusions to what is proven. | Claim ladder: aspiration → product capability → simulation evidence → practitioner/external validation → workplace evidence. Do not delete the ambition. |
| R6 | Conduct job/task analysis with actual practitioners before fixing competence standards. | **Critical priority.** The new integrated task model makes this more important, not less. | Balanced task analysis across Saudi Arabia, Oman and the UAE; role and employer context recorded. |
| R7 | Authenticate evidence; local editable records are not external proof. | **Keep.** Local records may support practice but not verified external claims. | Design evidence provenance, authentication, export, privacy, and audit requirements later; do not implement a backend as part of this review. |
| R8 | Record process quality: first attempt, retries, and error types. | **Keep as a candidate evidence requirement.** | Capture attempt-level process data without inventing thresholds or automatically converting it into a score. Respect existing independence rules. |
| R9 | Test a human entrustment-like independence rating. | **Hold as a hypothesis.** | Develop and validate scenario-specific rubric options with practitioners; do not import a clinical scale as-is. |
| R10 | Defer, rather than reject, adaptive difficulty/interleaving until data exists. | **Keep.** | Explore transparent rules after sufficient learner/task data; protect assessment content from adaptive leakage. |
| R11 | Conduct a preregistered external evaluation with blinded assessors and a comparator. | **Keep as a later validation milestone, not a precondition for all early development.** | Design after task analysis, rubric quality, and reliability/generalization questions are sufficiently resolved. |
| R12 | Preserve evidence honesty and Verified Reference discipline. | **Keep as a non-negotiable existing principle.** | Maintain D12/Verified Reference authority for Amadeus truth; keep implementation, practitioner, learning, and market evidence in their own lanes. |

### 12.1 Strongest recommendations to prioritize in knowledge work

1. **R6 — Job/task analysis:** without it, DEIXEN risks building a sophisticated system around an unvalidated view of the job.
2. **R2 — Assessment protection:** without it, apparent competence may partly reflect memory of practice cases.
3. **R1/R3 — Evidence definitions and retention:** without them, labels can outstate the observations.
4. **R4 — Communication criteria:** without them, the customer lifecycle is more realistic but its professional quality remains underdefined.
5. **R7/R8/R12 — Evidence integrity and honesty:** without them, the system may confuse activity, correctness, independence, and externally trustworthy evidence.
6. **R11 — Independent external validation:** critical for stronger claims and market credibility, but properly sequenced after earlier measurement foundations.

---

## 13. Risk register — risks that must remain visible

| Risk ID | Risk | Why it matters | Control / future evidence |
|---|---|---|---|
| K-01 | Competence model built from historical lessons rather than real job tasks. | DEIXEN may teach what it already contains rather than what jobs require. | V0 task analysis and balanced practitioner panel. |
| K-02 | One country/employer dominates the requirements. | Product may be misrepresented as suitable across all target markets. | Market-stratified evidence and scope labels. |
| K-03 | Familiar practice case contaminates independent assessment. | Scores reflect memory rather than transfer. | Protected variants, exposure history, leakage controls. |
| K-04 | System acceptance is treated as professional correctness. | A wrong customer outcome can be marked complete. | Separate operational state, task consistency, and evidence qualification. |
| K-05 | Final PNR state is treated as proof of competence. | The path, support used, and decision quality remain unknown. | Attempt-level event evidence and task criteria. |
| K-06 | Browser-local record is presented as authenticated evidence. | External parties cannot rely on a user-editable record. | Clearly scoped local evidence; future provenance/authentication design. |
| K-07 | Customer satisfaction is used as a competence score. | Unfair results and incentives to overpromise or sell at any cost. | Separate customer experience from professional and operational performance. |
| K-08 | AI-generated customer or Coach text changes case truth. | Contradictions and invented operational facts enter the task. | Case-grounded deterministic boundaries; versioned content; review. |
| K-09 | Unverified Amadeus syntax or output is taught. | Learner may internalize wrong real-world procedures. | D12/Verified Reference gate; U-items block dependent content. |
| K-10 | Unsupported correction command or system error is invented. | Simulation teaches false recovery procedures. | Only verified outputs; task-level mismatch is not a fabricated GDS error. |
| K-11 | Rubric is unreliable or evaluator bias is high. | Competence decisions differ by assessor or expectation. | Reviewer training, double scoring, blind review where possible, reliability study. |
| K-12 | Research from medicine/education is overgeneralized. | DEIXEN rules appear scientific without direct support. | Label adjacent evidence and run DEIXEN-specific validation. |
| K-13 | Same assessment task is repeated or exposed. | Retest gains may be practice effects. | Item/variant protection, versioning, exposure logs, retirement criteria. |
| K-14 | Premature adaptive difficulty. | Learner gets unpredictable difficulty or answer leakage. | Defer until sufficient data; transparent and reversible rules. |
| K-15 | Speed pressure precedes accuracy. | Beginners may learn rushed, unsafe habits. | Measure time separately; introduce only after accuracy and job relevance are established. |
| K-16 | English/voice recognition errors are misread as incompetence. | Accent, device, and ASR limitations create unfair judgments. | Separate language coaching, speech recognition and professional assessment. |
| K-17 | Overclaiming job readiness, certification or endorsement. | Trust, legal, reputational and learner harm. | Claim ladder, legal review, external validation, accurate disclosures. |
| K-18 | Commercial renewal is optimized over learner success. | Artificial dependence and poor trust. | Separate learning and commercial metrics; voluntary continuation. |
| K-19 | Price/access periods are chosen before learner workload and costs are known. | Offer may be unsustainable or inaccessible. | Learner-hour estimates, price tests, unit economics. |
| K-20 | Single practitioner review is treated as universal approval. | One expert may not represent the full role or markets. | Record scope and conflicts; multiple reviewers for standards. |
| K-21 | Conflicting docs silently become canonical. | AI agents and contributors follow different sources. | Source ownership, status, index, change log, canonicalization gates. |
| K-22 | AI collaboration protocol grants authority by technical capability. | Tools may edit or decide beyond their authorized role. | Reconcile D17/D93/D98; capability does not equal authority; read-only default. |

---

## 14. Launch credibility framework — what must be true before making stronger claims

Launch readiness is not a single score. It is a set of evidence-backed gates. Each release can have a narrower scope than the long-term DEIXEN vision, but its public claims must match the actual release.

| Gate | Question | Evidence required before stronger launch claim |
|---|---|---|
| G1 — Domain truth | Are all included Amadeus facts, commands, outputs, prerequisites, and errors verified? | D12-linked Reference entries, resolved blockers or explicit exclusions, versioned source trail. |
| G2 — Job relevance | Does the included task represent a real and appropriately scoped professional task? | V0 evidence, task map, market/role applicability, practitioner review. |
| G3 — Task correctness | Can the runtime detect when a system-accepted action conflicts with the case/customer request? | Case acceptance rules, deterministic semantic validation, tests for mismatch and alternative paths. |
| G4 — Learning usability | Can genuine beginners understand and use the experience? | Formative learner testing, observed failure modes, clear beginner language, accessibility and localization checks. |
| G5 — Learning design | Are support, examples, retrieval, feedback, variation and recovery intentionally designed? | Rationale, source applicability, instructional acceptance criteria, learner testing. |
| G6 — Assessment integrity | Are independent assessment conditions actually enforced? | Fresh run identity, protected variant, support isolation, event chain, exposure controls, runtime tests. |
| G7 — Evidence interpretation | Do labels and displays accurately state what each observation proves? | Evidence definitions, no unsupported composite score, transparent limitations, version and condition history. |
| G8 — Evidence security/privacy | Is the evidence appropriate for the claims and handled lawfully? | Provenance/security design, privacy notices, consent, retention/deletion, data minimization. |
| G9 — Professional review | Have relevant practitioners reviewed the actual scope? | Dated reviewer details, role/market expertise, comments, disposition, unresolved disagreements. |
| G10 — Localization/accessibility | Does the release work for its declared language, script, device, and accessibility scope? | RTL/LTR and Arabic/English checks; accessibility tests; voice/ASR fairness where relevant. |
| G11 — Product reliability | Does the implemented release behave as specified? | Current repository/code inspection, clean tests, runtime evidence, failure/recovery checks. |
| G12 — Commercial transparency | Are price, content scope, access, renewal, cancellation, refunds, and limitations clear? | Approved offer, market-specific legal/payment review, cost model, observed offer comprehension. |
| G13 — Claim integrity | Do website/app/sales claims match evidence and authorization? | Claim-to-evidence register, legal review as appropriate, official partner/certificate permissions. |
| G14 — Support and maintenance | Can DEIXEN maintain verified content, cases, learner support, and correction processes? | Ownership, update triggers, practitioner review capacity, operational support process and sustainable costs. |

A first launch need not claim G1–G14 at the highest maturity level for every future market and task. It must clearly state the exact scope that has passed and avoid implying that all future capabilities are already available.

---

## 15. Knowledge-base integration map — where this material should eventually live

Do not paste this entire synthesis into every existing document. Each domain needs one owner and a clear boundary. The following is a proposed ownership map for the later corpus redesign.

| Knowledge domain | Source that should own it (subject to full corpus audit) | What to integrate from Claude's report / this synthesis |
|---|---|---|
| Project authority and formal decisions | `07_DEIXEN_Canonical_Decisions_and_Current_State.md`, Constitution, resolution register `13` | Only approved decisions; R1–R12 remain review items until formally resolved. Resolve D98 collision and update register consistently. |
| Strategic ambition and organisational direction | Main Strategic Product Direction document, with Part XIX considered for controlled integration | Keep professional competence, long-term growth, Amadeus approach ambition, and honest claim boundaries. Merge Part XIX only after owner review. |
| Product scope and five areas | `03_DEIXEN_Canonical_Product_and_Architecture.md` | Map capabilities into the existing five areas; reconcile Home/Flight Deck naming and D98 status. |
| Unified experience/runtime | `06 — DEIXEN Unified Experience & Runtime Architecture.md` (working proposal) | Actor boundaries, three correctness layers, customer/Coach/system separation, task-level validation, assessment/evidence boundaries. |
| Professional task map | `08 — DEIXEN First Integrated Professional Task Map.md` (working map) | Reusable task structure, events, process evidence, task outcome and assessment relation. Avoid confusion with canonical AI Working Rules file also prefixed 08. |
| Case package | `09 — DEIXEN Case Package Definition — New Reservation.md` | Case blueprint, CP-001 limitations, U-12/U-14 and other open gates, semantic validation and practitioner questions. |
| Practitioner validation | `10 — DEIXEN Practitioner Review Brief & Response Form.md` | Obtain review, record exact scope and comments; do not treat one response as universal certification. |
| Amadeus operational truth | `DEIXEN_Amadeus_Verified_Reference.md` under D12/D15 authority | All domain syntax/output claims and unresolved U-items; do not duplicate factual authority in standards. |
| Curriculum and learning design | `06_DEIXEN_Canonical_Curriculum_and_Coach.md`, LDS, LEA, exact approved standards | Guided beginner learning, retrieval, spacing, variation, feedback, error-management, diagnosis; verify existing criteria and recover exact D95/D96 lesson standard before altering. |
| Quality standards system | `DEIXEN_Product_Quality_Standards_Framework_v0.1.md` (proposed) plus eventual standards registry | Evidence-type boundaries, case quality, beginner clarity, feedback, customer interaction, evidence/claim quality. Do not make proposed standards binding without approval. |
| Competence/evidence/assessment | A dedicated specialist standard or set of linked standards (location to be decided) | Competency taxonomy, evidence ladder, assessment protection, reliability, retention/transfer and claim limitations. |
| Market and job analysis | A dedicated market/job-task research repository (location to be decided) | GCC task evidence, role definitions, employer variation, practitioner findings, competitive comparison. |
| Research sources | A dedicated evidence/source register (location to be decided) | Complete bibliographic records, source type, full-text status, evidence strength, domain applicability, dissent/limits. |
| Commercial strategy | `DEIXEN Commercial Model & Pricing Strategy v0.1.md` (hypothesis) | Access model, learner-hours, pricing hypotheses, cost model, separate learning vs commercial metrics, launch disclosures. |
| Continuing development | Part XIX addendum until owner-approved integration | Research recurring professional needs; validate willingness to pay and value; protect voluntary continuation. |
| AI collaboration | `DEIXEN_AI_Collaboration_Handoff_and_Orchestration_Protocol_v0.2_PROPOSED.md` and governance source | Common task briefs, source provenance, cross-review, permissions, agent capability routing; no new authority before D17/D93/D98 reconciliation. |

### 15.1 Corpus design principles

The future DEIXEN Knowledge structure should make it easy for any of the four working participants—Karim, ChatGPT, Claude, Gemini—to answer:

1. What is the current authoritative source for this question?
2. Is this statement a decision, requirement, proposal, hypothesis, research finding, or historical record?
3. Who owns the domain and who may approve changes?
4. What other documents depend on it?
5. What source evidence supports it, and what are its limits?
6. What is implemented and verified versus only specified?
7. What remains open, blocked, or pending external review?
8. What changed since the source was last read?
9. What would falsify or materially change this conclusion?
10. How can another session/tool reproduce the review without relying on hidden chat memory?

### 15.2 Avoid duplicated authority

The research register should own the detailed source record. A professional competence standard should own its approved definitions and criteria. The strategy document should own the ambition and product direction. The decision record should own formal decisions. The Verified Reference should own Amadeus facts. The app specifications/code/tests should own implementation truth.

Other files should link to the owner source and summarize only what is necessary for their domain.

---

## 16. Research and validation backlog — priority sequence

This is a work backlog for the **Knowledge foundation phase**, not an app implementation roadmap.

### Priority A — must be clarified before the knowledge base is declared complete

1. Re-read Claude's report limitations and wait for the separate Claude report/comments that were not delivered because of the usage limit.
2. Reconcile R1–R12 against D1–D97 and newer strategic/architecture materials; review the old 07 reservations in the new context.
3. Resolve the D98 numbering and Home/Flight Deck synchronization issue; do not assume the insertion pack is canonical.
4. Reconcile Part XIX with the main strategic document and resolve its status.
5. Inventory all 45 current Knowledge root files, local project files, app repo files, Library duplicates, archives and missing references; record hashes/versions and source-of-truth status.
6. Redesign the corpus map, document ownership, folder layout, index, naming, status vocabulary, dependencies, change history, archival policy and link validation.
7. Recover missing supporting documents referenced by legacy governance if still needed; do not recreate from memory.
8. Recover the exact D95/D96 lesson standard v1.5 file before changing or reproducing its criteria.
9. Reconcile the standards README/path mismatch and proposed `/standards/` directory before treating the standards library as a functioning location.
10. Establish evidence/source-register schema and source-quality rules.

### Priority B — foundational research before fixing curriculum and task requirements

11. Build balanced job/task-analysis method for Saudi Arabia, Oman and UAE.
12. Identify actual entry-level role families and relevant adjacent professional roles.
13. Review a representative sample of current role descriptions and job advertisements by country and role; record date and provenance.
14. Obtain practitioner input from people with direct, current reservation/ticketing/customer-service experience in the target markets.
15. Validate CP-001 with the prepared practitioner brief; resolve comments or record disagreements.
16. Decide which work-task families deserve priority based on job evidence, not intuition or the narrow slice already built.
17. Build a candidate competence map from tasks and observable behaviours; examine critical/non-compensatory criteria.
18. Define the relationship between task validity, operational state, case consistency, professional judgement, customer experience, and evidence qualification.

### Priority C — learning, assessment and evidence foundations

19. Map existing lessons/skills to job-task requirements and identify gaps/duplication/outdated slices.
20. Review true-beginner clarity and prerequisites using learners outside the project team.
21. Design the learning progression (worked examples → guided practice → fading support → varied practice → protected independent assessment) as a testable model.
22. Define candidate learning measures for retrieval, error diagnosis, recovery, retention, and transfer.
23. Design protected assessment case/variant management and leakage controls.
24. Define task-level semantic validation requirements and alternate-valid-solution review.
25. Define attempt-level event requirements (first attempt, retries, hints, Ghost, feedback, time, task/version provenance).
26. Design reliability and generalizability studies only after tasks and rubrics are sufficiently defined.
27. Define evidence strength and claim wording without introducing unsupported numeric scores.

### Priority D — market, trust, launch and long-term development

28. Refresh the competitor and official training landscape with dated primary sources.
29. Verify current Amadeus/IATA programmes, credentials, eligibility, terms and possible partner routes when needed; distinguish official facts from marketing claims.
30. Validate the free Explore task and paid offer comprehension with prospective learners.
31. Calculate learner-hours from the validated curriculum; test pricing hypotheses in actual markets.
32. Define the legal/IP/privacy/customer data review required for each launch market.
33. Define a realistic quality, content-verification, case-maintenance and customer-support operating model.
34. Validate the continuing-professional-development problems and willingness to pay with working professionals.
35. Revisit the launch gates and public claims for the exact first-release scope.

---

## 17. Future criticism protocol — keep every important claim challengeable

Every material claim or standard should carry a record with these fields:

| Field | Required content |
|---|---|
| Claim ID | Stable unique ID. |
| Exact claim | One testable statement, not a broad aspiration. |
| Claim type | Owner requirement, operational fact, research claim, market claim, practitioner judgement, implementation fact, learning outcome, or commercial hypothesis. |
| Owner source | The one document or authority that owns the statement. |
| Evidence sources | Exact source, date, passage, URL/commit/version, and source type. |
| Population/context | Country, role, learner level, task, platform, and conditions to which it applies. |
| Evidence quality | Direct/adjacent/general/hypothesis; abstract/full text; method and limitations. |
| Counterevidence | What disagrees, what is uncertain, and what was not investigated. |
| Decision dependency | Which canonical decision, design, standard, case, or claim depends on it. |
| Status and owner | Proposed status, accountable owner, reviewer, and approval route. |
| Falsification test | What new evidence would change or reject this claim? |
| Review trigger | Date, source update, new market evidence, app change, practitioner objection, or learner outcome. |

### 17.1 Required questions for any AI or human review

- What is the strongest argument against this proposal?
- What evidence would prove it wrong?
- Are we confusing a feature with the professional outcome it is supposed to support?
- Are we applying research from another field beyond its legitimate scope?
- Does the same result have another valid path?
- Is the learner being assessed on skill or on familiarity with the same example?
- What is the cost and operational burden of maintaining this standard?
- Who is disadvantaged by the rule, assessment, language, device, or access model?
- Is an unresolved fact being hidden by polished wording?
- Would a real practitioner recognize the task and accept the decision criteria?
- Can another independent reviewer reproduce the reasoning from the files alone?

### 17.2 Re-review triggers

Review a claim when:
- the Amadeus Verified Reference changes or a material U-item is resolved;
- a task family, learner population, role, target market, language or product mode changes;
- a practitioner identifies a material mismatch;
- learner data contradicts a learning-design assumption;
- an assessment variant is exposed or its difficulty/equivalence is challenged;
- code/runtime changes alter evidence capture or assessment isolation;
- legal, privacy, official credential, commercial, or partner requirements change;
- a new high-quality study or contradictory source materially changes the research basis.

---

## 18. Research references — priority for independent re-verification

This list is a shortlist for future evidence-register work, not a declaration that the full texts have been independently audited. The full 61-entry bibliography and its caveats remain in Claude's original report and should be preserved unchanged as the source artifact.

### 18.1 Highest-priority research/method references

- Cook, D. A. et al. (2011), technology-enhanced simulation in health-professions education, systematic review/meta-analysis. DOI: `10.1001/jama.2011.1234`.
- Cook, D. A. et al. (2013), comparative effectiveness of instructional-design features in simulation-based education. DOI: `10.3109/0142159X.2012.714886`.
- Cook, D. A. et al. (2013), mastery learning using technology-enhanced simulation. DOI: `10.1097/ACM.0b013e31829a365d`.
- Keith, N. & Frese, M. (2008), effectiveness of error-management training: meta-analysis. DOI: `10.1037/0021-9010.93.1.59`.
- Pan, S. C. & Rickard, T. C. (2018), transfer of test-enhanced learning: meta-analytic review. DOI: `10.1037/bul0000151`.
- Cepeda, N. J. et al. (2006), distributed practice in verbal recall tasks. DOI: `10.1037/0033-2909.132.3.354`.
- Cepeda, N. J. et al. (2008), spacing effects in learning. DOI: `10.1111/j.1467-9280.2008.02209.x`.
- Rowland, C. A. (2014), testing versus restudy and retention. DOI: `10.1037/a0037559`.
- Brunmair, M. & Richter, T. (2019), similarity and interleaved learning. DOI: `10.1037/bul0000209`.
- Wulf, G. & Shea, C. H. (2002), limits of generalizing simple-skill principles to complex-skill learning. DOI: `10.3758/bf03196276`.
- Norman, G., Dore, K. & Grierson, L. (2012), simulation fidelity and transfer. DOI: `10.1111/j.1365-2923.2012.04243.x`.
- Hamstra, S. J. et al. (2014), reconsidering fidelity in simulation-based training. DOI: `10.1097/ACM.0000000000000130`.
- Barnett, S. M. & Ceci, S. J. (2002), taxonomy for far transfer. DOI: `10.1037/0033-2909.128.4.612`.
- Hausknecht, J. P. et al. (2007), retesting, coaching and practice effects. DOI: `10.1037/0021-9010.92.2.373`.
- Hróbjartsson, A. et al. (2013), observer bias in trials with blinded and nonblinded assessors. DOI: `10.1503/cmaj.120744`.
- Brannick, M. T. et al. (2011), generalizability/reliability across assessment stations (verify exact bibliographic record in the source register).
- Bloch, R. & Norman, G. (2012), generalizability theory practical guide. DOI: `10.3109/0142159X.2012.703791`.
- Cook, D. A. et al. (2015), validity arguments and Kane's framework. DOI: `10.1111/medu.12678`.
- Koo, T. K. & Li, M. Y. (2016), selecting and reporting ICCs. DOI: `10.1016/j.jcm.2016.02.012`.

### 18.2 Professional/market sources to re-check

- IATA, *Competency Assessment and Evaluation for Pilots, Instructors and Evaluators — Guidance Material*. Useful as a competency-assessment framework by analogy; not a reservation-agent standard.
- O*NET occupation 43-4181.00. US occupational context only; not Gulf market proof.
- Yong (2013) on CRS training/transfer with Galileo users. Treat as a limited adjacent-domain lead, not Amadeus evidence.
- Murthy et al. (2008) on simulation training for call-centre agents. Treat as service-agent adjacent evidence.
- Current IATA/Amadeus official training and credential pages. All details in Claude's 5 November snapshot must be refreshed before commercial or competitive use.

### 18.3 Sources to keep visibly unverified

Claude's report lists several candidates not opened or not used for findings (including expertise reversal, broad training-transfer models, older simulation references, and ICAO documents not accessed). Keep them as research leads only. Do not quote or build a binding rule from a title alone.

---

## 19. Repository/source snapshot and known limitations

### 19.1 Claude's review snapshot

Claude states that the repository review was performed against `deixenlabs/deixen-knowledge` `main` at commit `41d94ff9278332ecf6b933ba17c4607d3b6b6829`, dated 29 October 2026. The report read some core files fully, other files only in ranges or by grep, did not read several LDS sections and decisions in detail, and did not inspect `deixen-app` code.

Thus statements about what was built or missing in the old report primarily describe the documents at that older point and should not be treated as current implementation findings.

### 19.2 Newer Knowledge repository material inspected for this synthesis

The 7 November read-only snapshot included:
- current HEAD `52064e719ec485004845631a147054488718827c`;
- unified experience/runtime proposal `06 — DEIXEN Unified Experience & Runtime Architecture.md` (blob `47765c897418c890afb15046ec6a6e7047829fcd`);
- first integrated task map `08 — DEIXEN First Integrated Professional Task Map.md` (blob `8484433d122d807834130520a26424c45dd5b04c`);
- CP-001 case candidate `09 — DEIXEN Case Package Definition — New Reservation.md` (blob `9294ac60dc51792c31d0b4c2334aabffa5936019`);
- practitioner review brief `10 — DEIXEN Practitioner Review Brief & Response Form.md` (blob `7bd6b47493ccad4909a06aefc5342c11e1256d22`);
- Product Quality Standards Framework v0.1 (proposed; blob `3e5de59be259a9f3d75f7c1ca711e771de3b8ed0`);
- Part XIX professional lifecycle addendum (blob `f52f226ad3357092a80b4b4134ca0e0f945251d8`);
- Commercial Model & Pricing Strategy v0.1 (proposal; blob `574e8ef4410f134965a022d400c6865d55d8e574`);
- AI collaboration/orchestration protocol v0.2 (proposed; blob `f0c17c7cab7d68293fe3142d9d64f026e7d2a114`).

### 19.3 App implementation boundary

The app repository was last known at `dde546952b07b17d9bd43722e298a02a3755a706` (27 October). The CP-001 review made a read-only inspection of selected current app files for the RF/FXP stress test, but a full current-app conformance audit has not been completed as part of this synthesis. Do not assume the proposed architecture is implemented merely because the documents describe it.

### 19.4 No repository or project-file mutation

This synthesis was prepared as a separate local working document. It does not change the user's GitHub repositories, local project folders, canonical documents, application code, or Library. It should be reviewed alongside Claude's forthcoming separate comments before deciding where and how to integrate it.

---

## 20. Completion criteria for the DEIXEN Knowledge foundation

DEIXEN Knowledge should not be declared complete just because files have been renamed, folders created, or documents uploaded. A stronger completion definition should require the following:

1. **Corpus inventory:** every material file in Knowledge, app, local folders, relevant Library sources, and archives has an identified version, owner, purpose, status, and relationship to the project.
2. **Single-source ownership:** each important fact or rule has one authoritative source; derivative documents link to it instead of copying it.
3. **Governance consistency:** decision numbering, decision registry, Constitution, execution plan, AI working rules, indexes, and status language are synchronized; collisions and missing references are resolved or explicitly held.
4. **Strategic completeness:** the main strategy reflects the approved ambition, connected journeys, simulated workplace, product direction, continuing development, and personal Amadeus approach goal without treating proposals as decisions.
5. **Professional foundation:** job/task analysis method, candidate competence taxonomy, task lifecycle, task acceptance logic, and market evidence plan are clear and open to validation.
6. **Amadeus truth protection:** Verified Reference authority, U-item gates, and content provenance are connected to case authoring and quality review.
7. **Learning foundation:** learning methods, beginner progression, support/fading, retrieval, spacing, feedback, variation, recovery, and adaptation have evidence labels and validation questions.
8. **Assessment/evidence foundation:** independence, task correctness, evidence qualification, assessment protection, reliability, retention, transfer, and limits are unambiguously distinguished.
9. **Quality standards system:** standards have a consistent template, owner, scope, status, evidence, review route, and change trigger; proposed standards cannot silently become canonical.
10. **Market/competitive foundation:** Saudi, Oman, and UAE evidence is not confused with US proxy sources; competitor claims are current, dated, and source-backed.
11. **Commercial foundation:** access model, curriculum learner-hours, pricing tests, cost model, customer rights, legal/payment obligations, and separate business metrics are understood before launch commitments.
12. **Trust and claims:** public claims, certificates, partnerships, learner evidence, privacy, accessibility, and external review are bounded by what can actually be demonstrated.
13. **AI team continuity:** Karim, ChatGPT, Claude, and Gemini can independently locate source-of-truth documents, identify status/authority, resume a task, preserve provenance, and return traceable work.
14. **Recovery and preservation:** local and GitHub copies are reconciled safely, backups/hashes/history are verified, duplicates and legacy files are classified, and nothing valuable is lost.
15. **Independent corpus audit:** at least one adversarial review challenges the reorganized corpus and verifies that a fresh session can understand it without relying on hidden chat history.

Only after these conditions are met—or explicitly accepted as bounded open items—should the Knowledge foundation be declared ready for a broader implementation roadmap.

---

## 21. Immediate next sequence

The safe order, consistent with the user's current plan, is:

1. Review Claude's forthcoming separate report/comments and merge any relevant corrections into this synthesis.
2. Complete the old reservation/objection review against D1–D97 in the context of the new strategy, without defending old decisions by default.
3. Complete the full cross-repository and local-file inventory; this must include product, UX/UI, brand, curriculum, Amadeus, architecture, quality, commercial, AI collaboration, and application files—not governance only.
4. Resolve source ownership, status, numbering, missing files, and index inconsistencies.
5. Approve the knowledge corpus architecture and migration map.
6. Prepare a safe migration plan for local and GitHub files, including backups, hashes, history preservation, and explicit write approvals.
7. Validate the four-person AI collaboration workflow through read-only tasks and cross-review first; resolve authority before any controlled write workflow.
8. Run a fresh-session retrieval test and adversarial audit.
9. Declare the DEIXEN Knowledge foundation complete only when its completion criteria are met.
10. Then move into the next authorized product-development phase.

**No app-development work is authorized by this document.** Its purpose is to make the knowledge base strong enough that later product decisions and implementation are based on coherent, traceable, challengeable knowledge.

---

## Appendix A — report-to-foundation traceability

| Claude report area | Preserved in this synthesis |
|---|---|
| Executive findings / professional competence definition | Sections 1–3 |
| Seven competence dimensions | Section 3.2, expanded cautiously for the new work-task model |
| O*NET and missing job analysis | Sections 3.1 and 8.1 |
| Adjacent learning research and conflicting evidence | Sections 5 and 11 |
| Critique of older DEIXEN independence/assessment/evidence | Section 6 and R1–R12 disposition |
| Learning architecture and beginner/advanced progression | Section 5 |
| Independence, transfer, retention and evidence | Section 6 |
| Diagnostic/adaptive support | Section 5.7 |
| Customer communication | Section 7 |
| Competitor and official training comparison | Section 8 |
| V0–V7 scientific validation | Section 10 |
| Risks and open questions | Sections 13, 16 and 17 |
| All 12 recommendations | Section 12 and CSV backlog |
| Full bibliography and source limitations | Section 11 and 18; full original retained unchanged |

## Appendix B — current status in one sentence

**The November strategy and architecture have moved DEIXEN beyond the narrow command-training framing that Claude reviewed, while his strongest warnings about job relevance, assessment leakage, evidence validity, independent performance, customer-service assessment, transfer, retention, and honest claims remain essential and should now be integrated into the Knowledge foundation—not treated as already solved.**
