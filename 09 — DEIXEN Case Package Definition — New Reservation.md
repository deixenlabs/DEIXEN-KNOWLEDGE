---
document: DEIXEN Case Package Definition — First Integrated Reservation Task
id: CP-001
version: 0.1
prepared: 2026-11-07
status: WORKING CASE CANDIDATE — NOT APPROVED FOR PRODUCTION CONTENT OR IMPLEMENTATION
architecture_basis: Unified Experience & Runtime Architecture v0.3; First Integrated Professional Task Map v0.1
operational_reference: DEIXEN_Amadeus_Verified_Reference.md — current repository main snapshot SHA 4e52e99bd897e0088f7f1c8b4c4202a13165fd78 (third edition; V-01–V-18; amended through 2026-10-15)
owner_approval: Pending
practitioner_review: Pending
---

# DEIXEN — Case Package Definition: CP-001
## New reservation for one adult traveller — from customer request to filed and priced booking

## 0. Executive result

<badge>WORKING CASE CANDIDATE</badge>

**Purpose:** Pressure-test the proposed Scenario Bank → Task Runtime → Customer Interaction / Terminal → Assessment & Evidence → Growth architecture with one case whose customer facts, operational workflow, support rules, and evidence obligations are specific enough to inspect.

**Recommended final verdict: `تنجح مع تعديل` (Pass with modifications).**

The architecture can represent this task without giving Scenario Bank, Task Runtime, Terminal, Customer Interaction, Coach, and Evidence conflicting authority. However, this case is **not ready to be released as verified Amadeus training content** and is not proof that the architecture has been implemented. Two reference gaps block a clean operational approval (U-12 and U-14), a semantic task-validation gap is visible in the current app (`RF` accepts any non-empty text), and professional realism still needs practitioner review.

### Why this case was selected

It reuses the narrow new-booking workflow already represented in the current DEIXEN first slice: one adult, one segment, one booking class, one contact context, one ticketing arrangement, one Received From entry, end of transaction, and basic stored pricing. It adds a specific customer-discovery moment—the passenger contact detail—so the architecture must coordinate a customer conversation with the operational work.

This is an **architecture test candidate**, not a finding that new booking is the highest-priority job task in Saudi Arabia, Oman, or the UAE. Market and practitioner evidence must determine that separately.

### Scope that must not be implied

This case does not test or authorize live flight search/advice, fare comparison, ticket issuance, payment collection, exchange, cancellation, refund, reissue, disruption handling, multi-passenger handling, or a full work shift. The selected itinerary is a synthetic DEIXEN fixture. It is not a real airline schedule or an availability promise.

---

## 1. Case identity and learner-facing purpose

| Field | Definition |
|---|---|
| Case ID | `CP-001` |
| Case family | New reservation / one-way air booking |
| Intended learner | Beginner learning the verified first-slice booking workflow and how to connect customer facts to operational work |
| Scenario Bank category | Proposed work-domain family: **New reservations**. Taxonomy remains open pending market/practitioner research. |
| Primary objective | Complete the bounded reservation task in accordance with the customer's confirmed request and the case's authorized operational scope; verify the result; communicate accurately that pricing is not ticket issuance. |
| Customer count | One |
| Passenger count | One adult |
| Segments | One air segment |
| Fare context | One synthetic practice fare |
| Run purpose | Supported practice first; a structurally distinct assessment variant may later be authored separately under D97 |
| Complexity | Beginner foundation with one deliberate information-gathering decision and one task-level integrity check |

### Learner-facing task brief — draft

> A customer has already selected a particular one-way flight from Riyadh to Dubai for one adult traveller. Your responsibility is to confirm the details, collect any required information without making assumptions, create the reservation using the supported workflow, check that the resulting record matches the confirmed request, and explain the outcome accurately. This training case ends after the booking has been filed and priced. It does not issue a ticket.

This wording is a draft for owner/practitioner review. It must not be displayed as final instructional or Coach language until the applicable approval process is followed.

---

## 2. Customer and task facts

All names, numbers, airline identifiers, booking references, fares, and itinerary data below are **fictional DEIXEN practice data**. They are not a live customer record or a real airline offer.

### 2.1 Authoritative case facts

| Field | Case value | Visibility at task start | Source / status |
|---|---|---|---|
| Customer / requester | Mr Saad Alharbi | Disclosed | Existing DEIXEN main-task fixture; fictional |
| Passenger | Saad Alharbi, one adult, title `MR` | Disclosed | Existing DEIXEN main-task fixture; fictional |
| Relationship | Customer is the passenger and the person requesting the booking | Disclosed | Case-authored fact; practitioner review pending |
| Origin | RUH — Riyadh | Disclosed | Existing synthetic task fixture |
| Destination | DXB — Dubai | Disclosed | Existing synthetic task fixture |
| Journey | One-way, one segment | Disclosed | Case-authored scope; not a claim about a real itinerary |
| Travel date | `{TASK_DATE}`; runtime date token = execution date + 30 days, formatted DDMMM | Disclosed | Existing app data rule; dynamic value, not a fixed date |
| Selected flight | `6X 403` | Disclosed | Synthetic DEIXEN fixture; not a real airline/schedule |
| Booking class | `Y` | Disclosed | Existing task fixture; the case does not teach an unverified expansion/meaning for the class display |
| Availability line | `2` | Not an intrinsic case fact the customer must know; it is the line the learner should locate in the synthetic AN display | Existing app fixture; line number is specific to the DEIXEN display |
| Agency contact value | `966110000000` | Supplied by the case/work context, not the customer | Existing synthetic task fixture |
| Passenger mobile | `966500000001` | Withheld until the learner asks and the customer agrees | Existing synthetic task fixture; fictional |
| Ticketing arrangement for this task | `TKOK` | Task policy / profile context, not a customer preference | Existing synthetic task fixture; see V-09 qualification below |
| Person who requested the booking | `MR ALHARBI` | Disclosed as a case fact | Existing synthetic task fixture; aligns to customer=requester |
| Practice fare | SAR 900.00 base + SAR 150.00 synthetic tax line `YR` = SAR 1,050.00 total | Revealed only in the simulated pricing result | Existing app fixture; entirely fictional, not a market fare |
| Ticket issued? | No | Must be communicated accurately at close | Scope rule; pricing and ticket issuance are distinct |

### 2.2 Customer opening request — draft dialogue

> “I’d like a one-way reservation from Riyadh to Dubai for one adult on `{TASK_DATE}`. I have already selected flight 6X 403. The passenger name is Saad Alharbi.”

This opening is intentionally bounded. It does not ask the learner to search the market, compare fares, persuade the customer to choose a flight, or invent policy information. It tests whether the learner preserves the customer's selected itinerary and completes the supported reservation task accurately.

### 2.3 The withheld fact

The passenger's mobile number is not volunteered in the opening request. It is disclosed only after the learner makes an appropriate, understandable request for permission to pass a contact number to the airline for irregular-operations communication.

**Suggested customer reply after a suitable request (draft):**

> “Yes, you may pass my mobile number to the airline for contact about this trip. It is 966500000001.”

The exact wording, whether the request should be phrased as consent, notification, or another procedure, and what should happen if the customer declines must be approved by a practitioner and checked against applicable policy. V-13 establishes the contact SSR topic and gives a refusal path; it does not, by itself, supply a complete customer-conversation script or settle every jurisdictional/privacy rule.

### 2.4 What the customer does not know or control

The virtual customer should not know the learner's command syntax, the next required PNR element, the engine's internal validation rules, the learner's checklist, or the correct answer to an assessment. The customer can confirm only facts defined in the case package and can respond to reasonable customer-facing questions.

The customer must not reveal the mobile number just because the learner types an arbitrary command. The disclosure rule belongs to Customer Interaction and must be triggered by the meaning of the learner's request, within the boundaries of the case.

---

## 3. Selected itinerary and provenance

### 3.1 Synthetic practice itinerary

| Attribute | Value |
|---|---|
| Practice carrier code | `6X` |
| Practice carrier label | `PRACTICE AIRLINE` |
| Route | RUH → DXB |
| Flight | `6X 403` |
| Class | `Y` |
| Display line | `2` |
| Departure / arrival | 12:45 → 15:45 (synthetic fixture values) |
| Segment count | One |
| Date | `{TASK_DATE}` dynamic token |

The current `content/data/slice.json` in `deixenlabs/deixen-app` main contains this synthetic route/flight fixture and associates it with the main task. This is a DEIXEN-controlled deterministic practice dataset. It must not be described as a real carrier, current schedule, or live availability.

### 3.2 What the learner is expected to do with AN

The learner uses the supported availability display workflow to identify the case-specified line in the synthetic display. V-01 supports the AN availability request pattern and V-14 records the display layout. V-14 also explicitly says that some display values are not interpreted or taught; the case must not teach the meaning of the header number, the figure after each class letter, or `E0`.

The customer has already chosen the flight. The learner's task is not to make a commercial recommendation from this synthetic list. The purpose is to identify the specified flight and preserve the customer's confirmed choice.

### 3.3 Critical distinction

A synthetic availability row appearing in DEIXEN is not evidence that a real flight is operating, that seats are currently available in a live system, or that a customer could buy this itinerary. Case Package provenance must label it as `DEIXEN_SYNTHETIC_FIXTURE`.

---

## 4. Customer request, constraints, and task contract

### 4.1 Confirmed request snapshot

Before the operational booking phase begins, Task Runtime should hold a confirmed request snapshot containing:

- one adult passenger: Saad Alharbi;
- one-way RUH → DXB;
- travel date `{TASK_DATE}`;
- selected synthetic flight `6X 403`;
- booking class `Y` as specified by the case;
- one passenger / one segment;
- agency contact value supplied by the training task;
- whether passenger contact may be passed to the airline, and the customer-provided mobile if consent is given;
- requester identity: Mr Alharbi;
- case ticketing arrangement `TKOK`, subject to the training office-profile setting.

If any material fact changes, Runtime must create an explicit request-revision event and return the task to the appropriate clarification/confirmation point. It must not silently overwrite the original request snapshot.

### 4.2 Scope invariants

1. Do not change the selected route, date, flight, class, or passenger count without customer confirmation.
2. Do not invent missing customer data or substitute a fabricated number.
3. Keep the agency contact and passenger mobile distinct.
4. Do not use `AP` to claim that passenger contact has been transferred to the airline; V-13 explicitly separates `AP` from passenger-contact SSRs.
5. Do not continue through a missing/unclear operational requirement by guessing.
6. Do not describe an FXP/TST pricing result as a ticket issued.
7. Do not claim that a simulation result proves workplace readiness.

### 4.3 Customer and task completion are not identical

The customer may be satisfied with the communication while the task remains operationally incomplete. Conversely, the simulator may produce a filed/priced result while the professional task is wrong—for example, the `RF` text identifies someone other than the person who actually requested the booking. The task evaluator must check these dimensions separately.

---

## 5. Operational workflow and reference gate

**Important:** the following list separates (A) syntax/behavior already marked VERIFIED in the current DEIXEN reference, (B) task-specific data constraints from the current synthetic fixture, and (C) unresolved claims that must not be promoted into Amadeus facts.

| Step | Learner action / current slice example | Verified Reference basis | Case-specific rule | Release status |
|---|---|---|---|---|
| Availability | `AN{TASK_DATE}RUHDXB` | V-01; display layout V-14 | Use the synthetic RUH-DXB fixture and identify line 2 | Reuse only as the controlled DEIXEN exercise; not live availability |
| Sell selected segment | `SS1Y2` | V-03; response layout V-15 | One seat, class Y, line 2; the current DEIXEN engine checks that the selected line is the task's flight/class | Reuse within the existing one-segment slice |
| Passenger name | `NM1ALHARBI/SAAD MR` | V-07; PNR layout V-18 | One adult passenger and exact case name | Reuse within the existing first-slice scope |
| Basic PNR element framework | PRINT: Phone, Received from, Itinerary, Name, Ticketing | V-08 | Use as the high-level mandatory-element framework for this case | The reference does not, by itself, prove the exact AP mapping; keep U-14 open. |
| Agency contact | `AP966110000000` | V-11; PNR order/display context V-18 | Existing DEIXEN task expects the free-text AP value to include this fictional agency contact | **Conditional:** V-11 supports AP free text, but U-14 says the mapping from PRINT “Phone” to AP is not directly established. Do not teach that universal equivalence. |
| Passenger mobile SSR | Current app fixture expects `SRCTCM-966500000001` | V-13 supports `SRCTCM` and the mandatory dash; U-12 leaves the ending/suffix question unresolved; U-07/U-11 limit display claims | Customer provides this mobile only after the approved disclosure/consent exchange | **HOLD for operational release:** do not promote the bare-number entry as verified Amadeus syntax until U-12 is resolved under D12. A Case Package may carry the customer fact, but the operational command is not cleared by this document. |
| Ticketing arrangement | `TKOK` | V-09; display form V-18 | Current DEIXEN fixture sets `office.tkMandatory=true`; the case selects TKOK | Reuse only under this explicit training profile. V-09 says TK necessity depends on office profile; do not state universal mandatory status. |
| Received From | `RFMR ALHARBI` | V-08; V-10 | Must identify the actual requester, Mr Alharbi | Syntax is supported; semantic equality to requester is a task/professional validation, not a system response. |
| End transaction | `ER` | V-10; missing TK exact message V-09; contact SSR warning V-13; PNR layout V-18 | Must not bypass the V-13 warning if passenger contact has not been correctly handled | Reuse only with verified exact messages and current-slice conditions. Any other error text must be a labelled DEIXEN training message or omitted. |
| Stored pricing | `FXP` | V-05; single-fare response layout V-17 | Existing synthetic fare fixture for RUH-DXB-Y | Reuse in current scope. It creates a TST; it does **not** issue a ticket. |
| Fare display | `FQDRUHDXB` | V-04/V-16 | Optional, not required for the primary task | Optional/omit from CP-001 acceptance; no comparison or fare advice claim |

### 5.1 Current-reference snapshot and source authority

The live Knowledge repository `main` copy fetched for this task reports the Verified Reference as **third edition**, with V-01–V-18 and amendments through 2026-10-15 (07 D87). Its blob SHA at review time was:

`4e52e99bd897e0088f7f1c8b4c4202a13165fd78`

Source URL: `https://github.com/deixenlabs/DEIXEN-KNOWLEDGE/blob/main/DEIXEN_Amadeus_Verified_Reference.md`

The case uses only that live V-01–V-18 baseline and the open U-07/U-08/U-09/U-11/U-12/U-14 notes. A separate working implementation-spec document in the Library mentions a planned fourth edition / D80, but the current `main` file fetched in this review still identifies itself as the third edition. Do not treat that working file as authority or assume the fourth edition is merged.

### 5.2 Read-only current-app implementation evidence

The following source files were fetched read-only from `deixenlabs/deixen-app` branch `main` during this review. These identifiers are **Git blob SHAs for individual files**, not a repository commit SHA. They show what the inspected handlers currently do; they do not verify real Amadeus behavior.

| File | Blob SHA | Relevant observed behavior |
|---|---|---|
| `src/engine/engine.ts` | `ca74e9379d9447126bd293e46b08f28baa688b85` | Routes recognized slice commands to dedicated handlers; restricts certain changes after filing. |
| `src/engine/commands/ss.ts` | `4c75540fffd3432ff003b12dcaf7809f2763f665` | Checks line existence, passenger count, and task-specific flight/class before accepting SS. Wrong selected flight/class is rejected by the current DEIXEN handler; do not use it as an example of an accepted-but-professionally-wrong flight. |
| `src/engine/commands/rf.ts` | `fa8a1af259f5f5e2e6a06180418d8b7857a2735e` | Accepts non-empty RF text; a second RF is out of scope. It does not compare the text with the task's expected requester. |
| `src/engine/commands/fxp.ts` | `24ff4fe9c4dc3ee4440fa48dbcc4f6c4bcced4e5` | Requires a name and segment; creates a TST; the handler's `completesTask` flag becomes true when the booking is filed and FXP is accepted. |
| `src/engine/commands/ctc.ts` | `010a7fee97663e0822b1bd3347e6592fd5167500` | Uses the task's expected mobile/refusal branch; accepts the current slice's CTCM pattern and does not validate a suffix beyond retaining an optional slash ending. This implementation behavior does not close Reference U-12. |
| `src/engine/commands/ap.ts` | `f07a6e2789f028aa1d1e5e9f0de1455735fff1d9` | Requires AP free text to include the synthetic `agencyPhone` value in this task context. This is a DEIXEN task check, not proof that AP universally equals PRINT Phone. |
| `src/engine/commands/tk.ts` | `0ee28d8edbd0b4c0d84d7fc121d7d0fd5457dc27` | Accepts TKOK or a date-form TKTL pattern and checks against the task's configured ticketing value. |

The source fetch did not establish a current repository commit SHA. No file was modified, no tests were run, and no implementation change is implied.

### 5.3 Exact-output rule

This case does not author new Amadeus response text. Use only response/display content already cleared by V-09, V-13, V-15, V-17, and V-18, within their stated limits. In particular:

- exact `NEED TICKETING ARRANGEMENT` is supported under V-09 in its documented missing-TK condition;
- exact `MISSING SSR CTCM MOBILE OR SSR CTCE EMAIL OR SSR CTCR NON-CONSENT` is supported under V-13 in its documented missing-contact condition;
- missing RF and unsupported input/error wording must not be invented as Amadeus output; use the existing clearly labelled DEIXEN training-message policy under D23, or show no terminal response;
- PNR redisplay after AP, CTCM, TK, or RF is not verified by U-11. If DEIXEN's current UI shows a derived PNR view, it must retain the correct unverified marker/disclosure; it must not be presented as an observed Amadeus response.

---

## 6. End-to-end stage design

### Stage 0 — Discover and select CP-001

| Responsibility | Definition |
|---|---|
| Customer information | None is disclosed to the learner merely by browsing the Bank. |
| Learner action | Opens the case details and chooses to start the supported-practice run. |
| Scenario Bank | Owns CP-001's version, purpose, prerequisites, case facts, operational source references, and current gate status. Viewing the case must not start a run. |
| Terminal | Not yet executing. The case may show a concise task summary, not a Terminal transcript. |
| Coach | No coaching is needed at the selection moment. It may explain case purpose only if this is ordinary orientation, not assessment. |
| Task Runtime | On explicit launch, creates a unique `TaskRunId`, binds the immutable Case Package version, mode=`supported_practice`, support policy, and a fresh Operational Session. |
| Evidence | Record launch/run metadata only if the project's event policy allows it; case viewing alone is not competence evidence. |

**Exit:** a new Task Run is initialized with a case snapshot and clean operational state.

### Stage 1 — Briefing and run initialization

| Responsibility | Definition |
|---|---|
| Customer information | No additional facts are disclosed. |
| Learner action | Reads the bounded task and understands that the itinerary is already selected and that this exercise ends at filed/priced—not ticketed. |
| Scenario Bank | Supplies the case brief, confirmed scope, and visible constraints. Hidden mobile remains hidden. |
| Terminal | Opens in scenario mode with an empty operational record; no customer text or Coach text appears as Amadeus output. |
| Coach | In supported practice, may explain the objective and what kind of professional responsibility is involved without revealing hidden facts or commands as an answer. |
| Task Runtime | Sets initial state `AWAITING_CUSTOMER_REQUEST`; initializes conversation/task/operational references and records the policy version. |
| Evidence | Case/run version, mode, support policy, initial state, timestamp; none of this by itself proves skill. |

**Exit:** learner is ready to receive the customer request.

### Stage 2 — Receive and understand the opening request

| Responsibility | Definition |
|---|---|
| Customer information | Discloses one-way RUH-DXB, one adult, selected flight 6X 403, date token, and passenger name Saad Alharbi. Does not volunteer mobile. |
| Learner action | Parses the request; identifies that the itinerary is preselected; checks whether material details are still unclear. |
| Scenario Bank | Defines exactly which opening facts are disclosed and which remain withheld. |
| Terminal | Shows the task context in a separate brief/conversation surface. No Amadeus command has yet been entered. |
| Coach | May prompt the learner to summarize the request, but not reveal the hidden mobile number. |
| Task Runtime | Records the opening customer utterance and maps only the case-defined facts into Conversation State; does not change Operational Session. |
| Evidence | Customer request received; facts identified; any learner restatement/questions; support exposure. Interpretation of communication quality requires a reviewed rubric. |

**Exit:** learner has a preliminary understanding; unresolved information moves to clarification.

### Stage 3 — Clarify passenger contact and obtain permission

| Responsibility | Definition |
|---|---|
| Customer information | Does not disclose the mobile number until the learner asks an appropriate question. If the request is clear and appropriate, confirms permission and supplies fictional number `966500000001`. |
| Learner action | Explains why a passenger contact may need to be passed to the airline for irregular-operations communication; asks clearly; records consent/refusal accurately; does not confuse passenger mobile with agency contact. |
| Scenario Bank | Defines the allowed disclosure trigger and exact fictional value. It also defines an alternative refusal branch, but that branch is **not part of the primary success path** and is not authorized as an additional CTCR training case here. |
| Terminal | Does not receive the customer's chat text. The mobile fact becomes a separate task-context datum only after disclosure/permission. |
| Coach | In supported practice, may explain why the distinction between AP agency contact and passenger CTCM data matters. It must not disclose the number before the learner asks. |
| Task Runtime | Stores disclosure/permission as a Conversation State event; binds the customer-provided value to the active run; does not create an SSR or modify PNR state. |
| Evidence | Whether the learner asked; appropriateness/clarity of wording; consent/refusal; value disclosed; whether the learner kept agency and passenger contact distinct; Coach exposure. |

**Exit:** permission and contact fact are resolved, or the task pauses/branches. **Operational hold:** the exact CTCM suffix/ending issue U-12 must be resolved before the primary success path can be promoted as verified Amadeus content.

### Stage 4 — Restate and confirm the request

| Responsibility | Definition |
|---|---|
| Customer information | Confirms or corrects the route, date, flight, passenger identity, and contact permission. |
| Learner action | Restates the request and obtains confirmation before operational booking. |
| Scenario Bank | Supplies canonical request constraints and permitted customer corrections. |
| Terminal | Shows a separate confirmed-request summary; it does not add dialogue to the operational record. |
| Coach | May ask the learner to self-check material constraints in supported practice; no answer leak in assessment. |
| Task Runtime | Creates a versioned `ConfirmedRequestSnapshot`; if the customer corrects a fact, emits `request_revised` and returns to clarification/confirmation. |
| Evidence | Details restated, corrections, confirmation, and whether execution began before confirmation. |

**Exit:** customer confirms the request version that the learner will execute.

### Stage 5 — Execute the operational reservation

| Responsibility | Definition |
|---|---|
| Customer information | The confirmed request and disclosed contact facts remain available as case context. No more facts are revealed unless a new question/event rule permits it. |
| Learner action | Uses the current supported sequence to identify the intended line and build the booking, while interpreting each response. |
| Scenario Bank | Supplies the intended route/flight/class/passenger constraints and source mappings. Does not run the commands. |
| Terminal | Runs the verified command handlers. The record shows learner entries, verified Amadeus outputs, and at most the one permitted labelled DEIXEN training line. Coach/customer text remains outside the record. |
| Coach | Supported practice only: explains meaningful verified changes and offers help within policy. A hint/corrective prompt is logged and may affect independence under F-07. |
| Task Runtime | Routes each entry to the operational engine; associates the exact result and state transition with the active Task Run; coordinates phase progression without mutating Amadeus state itself. |
| Evidence | Exact entry, command classification, source/reference mapping, engine result, state before/after, order, timestamp, validation outcome, hint/Coach exposure, retries. |

**Operational sequence candidate:** `AN` → `SS` → `NM` → `AP` → `[CTCM held pending U-12]` → `TKOK` → `RF` → `ER` → `FXP`.

The listed commands are not all equally cleared for new content. The U-12 hold and U-14 limitation in Section 5 are binding. Existing first-slice code/data is evidence of current app behavior, not a substitute for D12 source clearance.

### Stage 6 — Verify operational state and professional-task consistency

| Responsibility | Definition |
|---|---|
| Customer information | The confirmed request snapshot is the comparison baseline; customer satisfaction is not a substitute for comparing booking details. |
| Learner action | Checks the operational record against the confirmed request: passenger, itinerary, and case-defined contact/ticketing elements; identifies any discrepancy. |
| Scenario Bank | Provides explicit, versioned task acceptance criteria and expected requester identity. |
| Terminal | Displays actual engine state and verified output. It does not rewrite a result to make it match the case. |
| Coach | Supported practice: may ask the learner to compare the record to the confirmed request. Independent assessment: no corrective prompt. |
| Task Runtime | Runs deterministic task-level checks against the operational state and the case snapshot. It must separately report `engine_accepted` and `task_consistent`; it cannot infer competence by general impression. |
| Evidence | Which fields were checked, the comparison result, discrepancies detected, timing, support conditions, and criteria/reference version. |

**Critical stress test — wrong `RF` requester:** The current app's `rf.ts` accepts any non-empty free text; it does not compare that text to `task.requestedBy`. The current app's `fxp.ts` marks the operational task completion flag when the booking is filed (`state.filed !== null`) and FXP is accepted. Therefore, the proposed Task Runtime/assessment layer must independently compare the recorded RF text with the case's actual requester and must not let a filed/priced state alone satisfy professional task completion. This is a confirmed gap in the inspected implementation, not an Amadeus behavior claim.

**Exit:** every task criterion is met, or a discrepancy is handled through recovery/pause/reset/escalation. A system-accepted action can remain system-accepted while the task result is not accepted by DEIXEN.

### Stage 7 — Recovery, pause, or stop

| Responsibility | Definition |
|---|---|
| Customer information | Customer may confirm a correction, maintain their decision, decline consent, or ask to stop. They cannot approve a false operational record. |
| Learner action | Identifies whether to correct, pause for information, restart, explain a limitation, or escalate. Never invents a fix. |
| Scenario Bank | Defines permitted branches and their preconditions. The refusal path is a separate variant/case requiring its own source/professional review. |
| Terminal | Shows only supported engine behavior. A failed/unsupported response is not replaced with fabricated Amadeus text. |
| Coach | In practice, supports diagnosis and safe next-step reasoning. It does not provide a made-up command or unverified policy. |
| Task Runtime | Records the failure/recovery branch and prevents success state until its acceptance criteria are satisfied. If the current engine cannot amend an already-added element, a reset/restart or abandon path may be required; do not invent modification commands. |
| Evidence | Error type, detection, diagnosis, recovery choice, restart/abandon, effect of support, and whether task integrity was restored. |

**Current RF recovery limitation:** `rf.ts` rejects a second RF as out-of-scope. The inspected engine also prevents certain changes after a booking is filed. CP-001 must therefore define a safe reset/restart path for an incorrect requester value; it must not teach an unverified in-place RF replacement. A future recovery capability needs separate reference and product validation.

### Stage 8 — Close the customer interaction accurately

| Responsibility | Definition |
|---|---|
| Customer information | Customer receives only the result actually supported by the simulation state. |
| Learner action | Communicates that the reservation was filed and priced in the training task, if those states were reached; explains clearly that no ticket was issued in this exercise. |
| Scenario Bank | Supplies the allowed outcome language and prevents claims beyond the case's scope. |
| Terminal | Keeps the operational record unchanged. Customer-facing outcome is shown in the separate interaction surface. |
| Coach | In practice, may review whether the learner's statement was transparent and not misleading. |
| Task Runtime | Closes the customer-interaction phase only after the outcome is consistent with operational state and case criteria. |
| Evidence | Outcome communicated, accuracy of statement, clarity, expectation management, and whether the learner claimed a ticket or live fare that did not exist. |

**Prohibited close-out claim:** “Your ticket has been issued.” The case ends after FXP stored pricing; no ticket-issuance workflow is included.

### Stage 9 — Debrief, evidence interpretation, and Growth

| Responsibility | Definition |
|---|---|
| Customer information | No new customer facts are required. Customer reaction, if modeled, is an outcome dimension, not a competence score. |
| Learner action | Reviews the attempt, explains key decisions, and identifies what remains uncertain or needs practice. |
| Scenario Bank | Retains case/version and authoring provenance. It does not own learner evidence. |
| Terminal | Shows the operational record for review without changing it. |
| Coach | May provide corrective teaching after the attempt is secured. Debrief must not retroactively turn assisted success into independent evidence. |
| Task Runtime | Closes the run and hands off immutable events/context to assessment/evidence interpretation. It does not assign a skill level. |
| Assessment & Evidence | Applies the versioned rubric and support/independence rules to events; qualifies only supported claims. |
| Growth | Displays the resulting evidence summary and limits; it does not reconstruct or invent source evidence. |

**Exit:** the run is closed; the evidence record is traceable; the learner-facing status is bounded by what the run can prove.

---

## 7. Branch and failure catalogue

| Branch | Trigger | Correct system/task behavior | Evidence | Status |
|---|---|---|---|---|
| Missing contact SSR at ER | Learner reaches ER without any one of the V-13 contact SSR alternatives | Use the exact V-13 warning only in its verified condition; do not bypass it as correct completion | Warning; prior consent/disclosure; correction or bypass; outcome | Supported by V-13; bypass is not qualifying success |
| Customer refuses mobile | Customer declines | Pause or use a separately reviewed refusal branch. Do not invent a mobile. `SRCTCR` is referenced in V-13, but its display and association limits remain; not part of CP-001 primary success path. | Refusal; respectful response; correct stop/branch | Separate case/variant; professional review pending |
| TK absent | Current training office-profile setting requires TK and element is missing | Exact V-09 message `NEED TICKETING ARRANGEMENT` may be used only in that documented condition. Do not generalize across all offices. | Missing condition; prompt/retry; TK decision | Supported with profile qualifier |
| Wrong RF person | `RF` text is non-empty but differs from actual requester | Keep genuine system acceptance if engine accepts it; flag task mismatch in DEIXEN task/evidence layer. Current app cannot replace a second RF; reset/restart/abandon rather than inventing an edit. | Exact RF text; requester case fact; mismatch; recovery | Confirmed current app gap / key architecture test |
| Wrong flight or class at SS | Learner selects wrong line/class | Current DEIXEN engine compares line/flight/class with the task and rejects mismatches; do not claim it creates an accepted wrong flight. | Entry; engine result; correction | Verified current app behavior from `ss.ts`; not a positive accepted-wrong example |
| Wrong passenger name | Learner enters a different name | Current DEIXEN handler validates name/count against task fixture. No unsupported system error should be invented. | Entry; task-level mismatch; engine result | Current app task-specific validation |
| AP vs passenger contact confusion | Learner uses agency phone in place of passenger mobile/SSR | Keep the two data objects separate; V-13 says AP does not satisfy the passenger contact SSR warning. | Field source; data object; learner decision | Supported by V-13; AP=PRINT Phone remains U-14 |
| U-12 suffix unresolved | Learner reaches CTCM step | Do not release the exact bare-number command as verified until reference gate is resolved. Stop the operational authoring path or mark it held; do not improvise `/US`, `/SA`, `/P1`, or another suffix. | U-12 gate and source needed | Blocking content gate |
| Pricing vs ticketing confusion | Learner says ticket is issued after FXP | DEIXEN corrects through a clearly labelled training explanation outside Amadeus output; do not invent ticket state | FXP/TST result; learner statement; correction | V-05/V-17 support pricing, not ticket issue |
| Unsupported command or response | Learner attempts command outside case scope | Keep the engine truthful; do not substitute an invented valid command or output. Use approved labelled DEIXEN training behavior where authorized. | Exact input, classification, support, attempt outcome | D12/D13/D23 boundary |
| Customer changes a material detail after confirmation | Customer changes date/route/name/flight | Emit request revision; reconfirm; re-evaluate any operational changes. Changes after filing are outside CP-001 and require separate verified procedures. | Request revision, confirmation, state, stop | Case branch limited; no unverified amendments |

---

## 8. Case acceptance criteria

CP-001 is professionally complete only when all applicable criteria are satisfied. A terminal success flag is insufficient.

### 8.1 Customer/task criteria

- [ ] Opening request correctly understood.
- [ ] Customer's preselected itinerary preserved; no silent substitution.
- [ ] Material request details restated and confirmed before operational execution.
- [ ] Customer mobile is not invented or disclosed before an appropriate question and permitted disclosure.
- [ ] Agency contact is kept distinct from passenger contact.
- [ ] Actual requester identity is correctly represented in the RF task check.
- [ ] Customer is told only what the simulated state supports; no ticket-issuance claim.

### 8.2 Operational/reference criteria

- [ ] Each command and taught behavior maps to a current VERIFIED reference entry.
- [ ] The AN and SS steps remain within the synthetic fixture and one-segment scope.
- [ ] Passenger count/name remain one adult within V-07 and current slice boundary.
- [ ] AP use does not make the unsupported AP=PRINT Phone equation.
- [ ] CTCM suffix/ending issue U-12 is resolved before operational content release.
- [ ] TKOK is tied to the declared training office-profile setting, not presented as universally mandatory.
- [ ] ER uses exact verified responses only; unsupported responses are not invented.
- [ ] FXP is reported as stored pricing/TST, not ticket issuance.
- [ ] Any unverified display detail remains labelled/disclosed and is not taught as fact.

### 8.3 Runtime and evidence criteria

- [ ] Case Package is versioned and immutable for the run.
- [ ] Each learner attempt has a distinct Task Run and clean operational session.
- [ ] Customer conversation state and operational session state remain separate.
- [ ] The learner's exact entry and exact engine result are recorded.
- [ ] Engine acceptance and case/task correctness are evaluated separately.
- [ ] Wrong non-empty RF is detected by task-level validation even if engine accepts it.
- [ ] Completion/FXP state does not by itself set professional task success or independent evidence.
- [ ] Assistance and hint exposure are captured and applied under F-07.
- [ ] Customer experience is kept separate from professional/operational correctness.
- [ ] Evidence does not overclaim retention, transfer, or workplace readiness.

---

## 9. Proposed minimum case data contract (authoring model, not schema approval)

The following fields are proposed to make the case auditable. They are not an approved database schema and do not authorize implementation.

| Group | Required fields for CP-001 |
|---|---|
| Identity/version | caseId, version, status, workDomain, targetRole, locale, author, reviewer(s), review date |
| Purpose | task objective, intended learner level, what this case tests, what it explicitly does not test |
| Customer facts | customer/requester identity, passenger identity, initial disclosures, hidden/disclosable facts, source/provenance, fictional-data flag |
| Request contract | route, date token, direction, selected itinerary, booking class, passenger count, constraints, confirmation status |
| Dialogue rules | allowed intents, disclosure triggers, customer knowledge boundary, consent/refusal branch, unsupported-question fallback |
| Operational scope | command/workflow IDs, Verified Reference IDs, current status, prerequisites, synthetic fixture IDs, unsupported behavior exclusions |
| Task criteria | task-level acceptance checks, professional criteria, stop/pause/escalate criteria, recovery rules |
| Run policy | mode, support policy, Coach availability, hint availability, reset/restart rules |
| Evidence policy | required events, provenance, source version, support metadata, separation of engine result vs task result |
| Assessment variants | family link, exposure constraints, distinct variant definition, D97 conditions |
| UX disclosure | what is visible to learner, what is held back, language/RTL notes, accessibility considerations |
| Review gates | Amadeus verification gate, practitioner review gate, owner approval, implementation authorization |

---

## 10. What this case reveals about the architecture

### 10.1 The architecture can represent the task

The responsibilities remain coherent:

- Scenario Bank owns the immutable case definition and its source/professional criteria.
- Task Runtime owns the active Task Run, state transitions, event correlation, and coordination.
- Customer Interaction owns dialogue behavior and controlled disclosure from case facts.
- Operational Engine owns Amadeus-like booking state and authentic verified responses.
- Terminal presents operational entry/output while keeping non-operational content separate.
- Coach provides mode-appropriate instruction and debrief, not customer or system truth.
- Assessment & Evidence interprets recorded events against explicit criteria and support rules.
- Growth presents bounded conclusions from evidence.

No extra top-level product area or second Terminal is needed to describe CP-001.

### 10.2 A case-level validator is necessary, not optional

The current engine validates some task facts directly (for example, the selected segment and passenger name), but it does not validate all semantic work facts. The RF handler currently accepts any non-empty text. The case/runtime layer therefore needs a deterministic check that compares the entered RF text with the Case Package's actual requester. This is not a request to make Amadeus reject the entry. The true engine acceptance must remain true; the DEIXEN task outcome can still be incorrect.

The terminal's operational `completed` state and the professional task's `accepted` state should be separate. In this current app, FXP sets its task completion signal when the booking has been filed; the architecture must not treat that signal alone as proof that the full customer task is correct.

### 10.3 Content verification blocks a clean release

- **U-12:** exact passenger contact SSR ending/suffix requirements remain unresolved. The current practice fixture uses a bare-number `SRCTCM` entry, but that implementation fact is not the same as D12 source verification. No extra suffix should be guessed.
- **U-14:** the connection between PRINT's “Phone” element and AP remains unproven. The current case can use the AP free-text contact field as a DEIXEN task requirement, but must not teach universal equivalence.
- **U-11/U-07/U-08:** displays/responses after AP/CTC/TK/RF and some element displays remain limited; use only verified displays or marked/disclosed renderings.

### 10.4 Practitioner review is a separate gate

Reference verification cannot determine whether the customer conversation, workplace procedure, consent wording, task sequencing, and recovery policy are professionally realistic across the target markets. A current reservation/ticketing practitioner must review those aspects. The reviewer must not be treated as a replacement Amadeus source under D12.

### 10.5 The case is not yet an assessment blueprint

CP-001 is a supported-practice case candidate. A later independent assessment variant must be sufficiently distinct from what the learner has rehearsed, and run under D97's fresh-session, clean-booking, no-prior-Ghost, no-instructional-help constraints. Do not reuse the exact same customer values and itinerary as a claimed independent variant.

---

## 11. Review and release checklist

### A. Before practitioner review

- [x] Customer and synthetic task facts are defined.
- [x] The preselected itinerary is clearly marked synthetic.
- [x] The first slice's boundaries are explicit.
- [x] Verified and unverified operational claims are separated.
- [x] The task-level RF mismatch is surfaced as a runtime gap.
- [ ] U-12 is resolved in the current Verified Reference under D12.
- [ ] U-14 is resolved or the AP/PRINT equivalence is explicitly excluded from teaching.

### B. Before case approval

- [ ] Practitioner review completed and recorded.
- [ ] Owner approves the final customer request and dialogue wording.
- [ ] Case acceptance criteria and stop/recovery branches are approved.
- [ ] Amadeus operational content is rechecked against the then-current Verified Reference, not this snapshot alone.
- [ ] Case and assessment variants have separate exposure rules.

### C. Before implementation specification

- [ ] Task Runtime requirements include run/session IDs, versioned state, and event ownership.
- [ ] Runtime task validator checks semantic consistency (especially requester/RF).
- [ ] Operational completion is decoupled from professional-task acceptance.
- [ ] Recovery behavior for an already-added wrong RF is designed without unsupported commands.
- [ ] Customer/Coach/Terminal channel boundaries are prototyped.
- [ ] D97 assessment isolation can be demonstrated in the proposed attempt flow.

---

## 12. Final verdict

# **تنجح مع تعديل**

**Meaning:** the proposed architecture passes this case as a conceptual responsibility model, but the case does not yet pass operational content release or implementation readiness.

**Why it passes:** Scenario Bank, Task Runtime, Customer Interaction, Terminal, Coach, Assessment & Evidence, and Growth can each own a distinct responsibility while sharing one versioned case/run context. The case exposes a real need for a task-level validator beyond command acceptance, which the architecture can accommodate without falsifying Amadeus output.

**Why it needs modification:**

1. Resolve `U-12` before using the current bare-number `SRCTCM` entry as verified training content.
2. Resolve or explicitly quarantine `U-14`; do not teach that AP automatically satisfies the PRINT Phone element.
3. Add a deterministic professional/task consistency validation stage for RF/requester identity and any other case facts not checked by the operational engine.
4. Separate `operational booking filed/priced` from `professional task accepted` and from `qualifying independent evidence`.
5. Define safe recovery/reset behavior when a wrong RF has been entered; do not invent a correction command.
6. Obtain practitioner review of the dialogue, consent/disclosure, agency-vs-passenger contact distinction, close-out wording, and task representativeness.

**Current status:** architecture model = passes with modifications; Case Package content release = HOLD; practitioner validation = pending; implementation = not inspected as complete and not authorized by this document.

No canonical decision is changed by this verdict. Owner approval and the normal governance path remain required.

**Final verdict: تنجح مع تعديل.**
