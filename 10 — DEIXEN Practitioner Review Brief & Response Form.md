---
document: DEIXEN Practitioner Review Brief & Response Form
id: PR-CP-001
version: 0.1
prepared: 2026-11-07
status: READY TO SEND — REVIEW NOT YET PERFORMED
related_case: CP-001
---

# DEIXEN — Practitioner Review Brief & Response Form
## CP-001: New reservation for one adult traveller

## 1. Purpose of this review

We are asking an experienced reservation/ticketing practitioner to assess whether CP-001 represents a credible beginner-level professional work task and whether its customer interaction, decisions, and recovery logic are realistic.

This is a **professional-practice review**, not a request to certify Amadeus syntax or response text. DEIXEN's current Amadeus Verified Reference remains the only source of Amadeus operational truth under its project rules. A practitioner's familiarity with a command is valuable input, but it does not automatically make an unverified command, output, error, or system transition VERIFIED.

The review should challenge the case. Please identify missing steps, unrealistic assumptions, confusing customer wording, and any requirement that depends on airline, agency, office-profile, or market policy.

## 2. Case summary

A customer, Mr Saad Alharbi, requests a one-way synthetic practice reservation from Riyadh (RUH) to Dubai (DXB) for one adult. The customer has already selected the synthetic DEIXEN fixture flight `6X 403`, class `Y`, on `{TASK_DATE}`. The passenger is the customer and requester. The customer initially supplies their name but does not volunteer a mobile number. The learner must ask a suitable question about passenger contact for airline irregular-operations communication. The customer consents and supplies fictional mobile number `966500000001`.

The learner then confirms the request, builds the supported reservation, verifies it against the request, and communicates that the exercise ends after booking/filed state and stored pricing. **No ticket is issued in this case.** The synthetic fixture includes an agency contact value `966110000000`, which must remain distinct from the passenger's mobile.

Scope is limited to one adult, one passenger, one air segment and one synthetic fare context in the current first-slice range. The case does not assess live shopping/availability, fare comparison, ticket issue, payment, exchange, cancellation, refund, or full work-shift operations.

## 3. What the reviewer is being asked to judge

Please assess:

- professional realism and sequence of the task;
- what a beginner should clarify before acting;
- whether the customer's selected itinerary should be treated as fixed or reconfirmed;
- whether the passenger-contact request is properly explained and handled;
- whether the distinction between agency contact and passenger contact is realistic;
- whether the requester identity represented in `RF` should be checked against the person who actually authorized/requested the reservation;
- whether `TKOK` is a plausible case-specific arrangement and what office/agency policy controls it;
- whether “reservation filed and priced, not ticketed” is an honest and understandable close-out;
- what stop, pause, correction, restart, or escalation branches are missing;
- whether the case is an appropriate first integrated beginner-task candidate.

## 4. Review questions

For each question, select one disposition and provide a reason or evidence. “Unable to judge” is acceptable; please do not guess.

| # | Question | Reviewer disposition | Reason / evidence / recommendation |
|---|---|---|---|
| 1 | Is the opening customer request realistic and understandable for a beginner task? | Accept / Revise / Unable to judge | |
| 2 | Is a customer who has already selected a flight a useful bounded first task, or does this omit an essential beginner responsibility? | Accept / Revise / Unable to judge | |
| 3 | Are the initial facts and the withheld mobile detail plausible? What should the customer volunteer, and what should only be disclosed after an appropriate question? | Accept / Revise / Unable to judge | |
| 4 | Is the proposed wording for asking permission to pass contact details to the airline professionally appropriate? Please suggest better wording and explain any policy caveats. | Accept / Revise / Unable to judge | |
| 5 | If the customer refuses to provide a mobile/email, what should a professional employee do next? What should be explained, recorded, or escalated? | Accept / Revise / Unable to judge | |
| 6 | Is it realistic to keep the agency contact (`AP` task value) separate from passenger contact for airline irregular-operations communication? | Accept / Revise / Unable to judge | |
| 7 | Should the `RF` requester value be checked against the actual person who requested/authorized the booking? What professional risk arises if it is wrong? | Accept / Revise / Unable to judge | |
| 8 | Is `TKOK` a plausible arrangement for this specific case? Which agency/office-profile/company policy determines whether a ticketing arrangement is required or which value is appropriate? | Accept / Revise / Unable to judge | |
| 9 | Is the end-of-task wording accurate when the booking is filed and priced but no ticket is issued? What exact customer-facing distinction should be taught? | Accept / Revise / Unable to judge | |
| 10 | What are the most important errors, pauses, recovery situations, or escalation branches missing from CP-001? | Accept / Revise / Unable to judge | |
| 11 | Are the task acceptance criteria observable, fair, and appropriate for a beginner? Which are missing or too strict? | Accept / Revise / Unable to judge | |
| 12 | Is this task sufficiently representative to pressure-test a first integrated DEIXEN experience? What alternative would you choose and why? | Accept / Revise / Unable to judge | |

## 5. Operational and governance boundaries for the review

Please do not:

- invent or reconstruct Amadeus commands or exact terminal outputs from memory;
- infer that an action is system-accepted simply because it seems familiar;
- assume an office-profile rule is universal across agencies or markets;
- treat pricing as ticket issuance;
- treat a customer being satisfied as proof that the work was professionally correct;
- infer competence from task completion alone.

The following issues are already marked unresolved in the current DEIXEN Verified Reference and must remain visible until the project resolves them through its own Verification Standard:

- **U-12:** what must follow the number/text in a passenger contact SSR, whether an ending is required, and what it contains;
- **U-14:** whether the PRINT “Phone” element is the `AP` element;
- **U-07/U-08/U-11:** limits on some SSR/RF/PNR displays and responses.

A practitioner may flag source leads or identify where an official/authorized environment should be consulted. That does not by itself close these Amadeus verification gates.

## 6. Additional professional-practice questions

Please add any context-specific guidance for Saudi Arabia, Oman, or the UAE if you have current experience there. Distinguish general agency practice from requirements that vary by airline, agency, office profile, contract, customer consent, privacy policy, or local law. Please identify the country/market and date of your experience where relevant.

### Suggested reviewer background (for the person sending this brief to complete)

- Reviewer name: ______________________________
- Current/recent role: __________________________
- Reservation/ticketing experience: _______________
- Relevant GDS / Amadeus experience: ____________
- Market(s): Saudi Arabia / Oman / UAE / Other: ___
- Date of review: _______________________________
- Any conflict/relationship with DEIXEN: __________

## 7. Overall practitioner recommendation

Select one:

- [ ] Accept the professional case as written.
- [ ] Accept with specified changes.
- [ ] Do not use this as the first integrated task; propose an alternative.
- [ ] Unable to judge from the information supplied.

### Required reasons and changes

____________________________________________________________________

____________________________________________________________________

____________________________________________________________________

### Missing professional steps or policy dependencies

____________________________________________________________________

____________________________________________________________________

### Suggested customer wording

____________________________________________________________________

____________________________________________________________________

### Sources, policy documents, or practitioner evidence that may help

Please provide titles, organization, URLs or document names, dates, and the exact claims supported where possible. Do not provide confidential customer data.

____________________________________________________________________

## 8. How DEIXEN will use this review

1. Treat the review as professional-practice evidence with provenance, reviewer background, date, and stated limitations.
2. Compare it with the case facts, current Verified Reference, and product architecture.
3. Revise the Case Package where justified and record what changed.
4. Route any Amadeus command/response claim through the formal Verified Reference process separately.
5. Keep the result as `PROPOSED` until the owner approves it through the project's governance process.

**Review status at package preparation:** not yet sent to or completed by an external practitioner. No practitioner endorsement is claimed.
