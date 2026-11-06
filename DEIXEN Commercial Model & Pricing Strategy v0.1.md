# DEIXEN — Commercial Model & Pricing Strategy

**Version:** 0.1  
**Prepared:** 7 November 2026  
**Status:** Proposed commercial model for owner review and market validation. Not a final approved price list, launch authorization, revenue forecast, or implementation specification.

## 1. Commercial intent

DEIXEN should be positioned as a specialist professional-learning and development experience that offers materially greater value than a short command course, without trying to win by being the cheapest option.

The original customer promise remains important: help trainees spend less than they might spend on expensive traditional courses while receiving a deeper, more practical, better-connected learning experience. The commercial model must also support sustainable operation, content verification, scenario authoring, practitioner review, customer support, platform maintenance, payment fees, and future growth.

The intended balance is:

- **Accessible, not bargain-basement:** make the first meaningful experience affordable/free and price the full experience below or competitively against comparable professional training where justified.
- **Value-led, not feature-count-led:** price the integrated learning and professional-development outcome, not the number of pages or buttons.
- **Finite foundation, continuing relationship:** the core beginner-to-independent-practice learning path has a realistic expected duration; continuing professional development can be renewed later as needed.
- **Transparent and voluntary:** learners should understand exactly what is free, what is paid, how long access lasts, when renewal occurs, and how to cancel.

DEIXEN must not imply official Amadeus endorsement/certification, employer recognition, or a guaranteed job as a consequence of purchase.

## 2. Proposed access model

### 2.1 Explore — free, limited, genuine experience

Offer a small but real part of the product without payment details. The recommended starting point is one bounded basic-booking practice task using the learner-facing Terminal practice experience already present in the app, with a clear task brief and a controlled reset/retry policy.

The free experience should let a prospective learner:

- understand the learning environment and how the Terminal simulation behaves;
- enter the relevant learner commands for a limited, beginner-appropriate booking task;
- see the simulator's response and understand that this is a DEIXEN training simulation;
- experience enough of the product's interaction quality to decide whether the paid path may be useful.

The free entry is a product trial, not a free mini-course and not a disguised certificate.

**Important distinction from current implementation:** the app has a separate Ghost demonstration that plays a scripted sequence against a demo booking. That is not the same as a learner independently operating the Terminal practice task. Do not present Ghost as the free hands-on booking trial. The Explore experience should use a genuine learner-operated practice path, subject to product/design approval and any necessary isolation of practice state.

Explore must not:

- grant access to the full curriculum, full scenario library, or complete professional-development experience;
- create or advertise qualifying independent-assessment evidence;
- imply access to a live Amadeus production system, real office, or actual customer booking;
- reveal assessment answers or contaminate a later independent assessment;
- remove the learner's opportunity to understand what is included in the paid product.

The current app repository inspected for this proposal does not show an implemented account/subscription/paywall/entitlement/payment flow. Explore is therefore a proposed access experience, not an existing feature.

### 2.2 Full Access — one coherent paid learning experience

The paid product should unlock the complete intended individual learning experience rather than splitting the core promise into arbitrary add-ons. Subject to validated content and implementation, this includes:

- the full beginner curriculum and relevant learning tracks;
- demonstrations and progressively supported practice;
- learner-operated Terminal practice;
- the available and validated scenario collection;
- connected customer-interaction learning and practice where implemented;
- protected independent assessment where the assessment conditions are actually enforced;
- the learner's evidence and Growth experience;
- relevant content updates during the paid access period.

Do not charge separately for the core assessment/evidence principles that make DEIXEN distinct. Do not sell each scenario or each key feature as a separate micro-purchase at launch. The full experience should remain coherent.

A paid entitlement must not imply that content which is still unverified, unimplemented, or awaiting practitioner review is already available. The offer page must describe current included scope accurately.

### 2.3 Continuing Professional Membership — renew when it remains useful

After the foundation period, the learner should be able to continue monthly or purchase a 3- or 6-month access period as needed. This is not a compulsory career subscription. It is a voluntary way to keep using DEIXEN for recurring professional development.

Candidate continuing value includes:

- refresh and retention practice;
- difficult, uncommon, and structurally varied cases;
- advanced verified work domains as they are added;
- current validated system/procedure learning;
- professional judgment and customer-service practice;
- role-relevant development and additional evidence opportunities.

A former learner who gets a job should have a credible reason to stay: DEIXEN continues to help them maintain and extend professional capability. They must not be made dependent on DEIXEN to perform their job, and non-renewal after reaching a goal is not a learning failure.

## 3. Duration should be justified by learner-hours

Do not select 3 months or 6 months merely because those are common subscription periods. First estimate the actual workload of the validated curriculum and representative practice journey.

Calculate the expected learner effort across:

1. lesson reading, explanation, and retrieval checks;
2. demonstration/Ghost viewing and reflection;
3. supported command and workflow practice;
4. guided-to-independent practice with fading assistance;
5. customer-interaction learning and case dialogue where included;
6. scenario execution and meaningful task variations;
7. feedback, correction, recovery, and repeat attempts;
8. independent assessment attempts and post-attempt review;
9. delayed retrieval/retention and transfer probes where part of the program.

For each unit, record an expected active-learning time range, not just video/runtime length. Add realistic time for pauses, mistakes, reflection, and re-attempts. Estimate more than one learner profile (for example, a learner with fewer hours available per week and one with a more intensive study schedule).

Then:

- **3 months** may be the standard foundation access period if the calculated workload and realistic weekly availability support it.
- **6 months** may be the extended option for learners with lower weekly availability, more retries, or a need for additional practice/transfer time.
- If measured learner-hours show that 3 months is unrealistic for the target beginner, change the program design or period. Do not force the learning to fit the price page.
- Access duration is not a deadline for competence. Completing the paid period does not establish competence; a learner may need additional practice or may not yet meet assessment criteria.

The current repository's narrow slice and one detailed CP-001 booking case are not sufficient to calculate the final program duration. A full curriculum inventory and pilot timing data are required.

## 4. Proposed test prices

The following are commercial hypotheses to test, not approved launch prices. They are based on the model discussed with the owner on 7 November 2026 and should be revisited after learner-hour estimates, cost modeling, and customer price testing.

### 4.1 Egypt — initial local test anchors

| Access option | Proposed test price | Intended role |
|---|---:|---|
| Explore | Free | A limited, genuine, learner-operated booking practice experience |
| Full Access — 1 month | EGP 1,299 | Flexible monthly access for a learner who cannot commit to a multi-month period |
| Full Access — 3 months | EGP 3,699 | Candidate standard foundation path if curriculum workload supports approximately 3 months |
| Full Access — 6 months | EGP 6,499 | Extended access for lower weekly study time and additional practice |

The 3- and 6-month options are prepaid access periods. Unless the payment terms explicitly state otherwise and the customer opts in, prepaid bundles should not silently auto-renew. The monthly plan should renew only with clear consent and a visible cancellation method.

### 4.2 International reference

**USD 25/month** is the proposed international reference for the **Continuing Professional Membership** after the foundation learning path. It is a pricing hypothesis, not a universal conversion rule. The initial foundation path should be priced and tested according to its own curriculum workload and the market in which it is sold. Local continuing-membership prices should reflect purchasing power, payment methods, taxes, processing costs, support costs, and competitor alternatives. Do not simply convert USD 25 into every local currency and assume the result is commercially appropriate.

Egypt's EGP 1,299 monthly figure is a local Full Access test anchor and a candidate local reference for monthly continuation, but the two offers should be validated separately. It is not a promise to maintain a fixed FX peg. Review local pricing when costs, exchange rates, or market conditions materially change.

### 4.3 Pricing rules

- Keep the included paid feature set coherent across 1-, 3-, and 6-month durations; the difference is access length, not artificial feature deprivation.
- The 3-month option should provide a clear saving compared with three monthly payments; the 6-month option should provide a further but sustainable saving.
- Avoid lifetime access at launch because verified content, scenario maintenance, infrastructure, and support create ongoing costs.
- Avoid a large permanent discount. A limited founding-cohort offer may be tested separately, with transparent eligibility, end date/quantity, and renewal price.
- Do not announce a future price increase as certain until it is actually approved and communicated.
- The working professional should be able to renew monthly or choose a 3-/6-month period according to actual use, rather than being pushed into an annual renewal by default.

## 5. Billing and customer-access rules

Any eventual billing implementation should make the following rules explicit before a user pays:

| Area | Required behavior |
|---|---|
| Offer clarity | State the exact included content/features, access duration, limitations, and whether the access is a DEIXEN simulation or third-party/official environment. |
| Price display | Show the final payable amount, currency, tax/fee treatment, and renewal terms before confirmation. |
| Monthly renewal | Use explicit opt-in consent; show renewal cadence and next charge information; provide cancellation in the account. |
| Prepaid 3-/6-month access | State the start/end dates. Do not silently convert a prepaid period into recurring billing. |
| Failed payment | Define a reasonable, disclosed retry/grace process that does not destroy the learner's historical record. |
| Cancellation | Make cancellation straightforward; explain whether access remains until the end of the paid period. |
| Expiration | Stop paid content/practice entitlements according to the disclosed policy, but preserve legitimate historical learner evidence subject to privacy, deletion, and legal requirements. |
| Refunds and disputes | Publish clear terms consistent with applicable consumer law and payment-provider requirements. |
| Receipts and tax | Provide legally appropriate receipts/invoices and tax treatment for each selling entity/market. |
| Data and privacy | Collect only information needed for account, payment, support, learning, and consented outcome research; separate payment credentials from learning evidence where appropriate. |

The exact billing provider, Merchant of Record structure, legal entity, taxes, invoicing, and consumer-law duties must be reviewed for the country where DEIXEN is established and the countries where it sells. They are not settled by this pricing proposal.

## 6. What should remain available after a paid period ends?

A learner should not lose the fact that they learned or demonstrated something merely because access expires.

Subject to approved privacy and retention rules, design for a distinction between:

- **Historical record access:** the learner can review past learning/evidence records and understand their provenance and limitations.
- **Paid active access:** the learner can continue lessons, practice, scenario execution, new content, and continuing-development activities for the paid period.

Do not silently erase the Growth/evidence history on expiration. Also do not promise indefinite data retention until an approved retention and deletion policy exists.

## 7. Unit economics before confirming the price

A price is not sustainable just because it undercuts a short course. Before confirming any test or launch price, calculate:

- hosting, database, storage, observability, and infrastructure cost per active learner;
- simulation/runtime costs and any future language, speech, or AI service cost;
- content authoring, reference verification, review, and scenario maintenance;
- practitioner review, human assessment, coaching, or customer support if included;
- payment-provider fees, currency conversion, chargebacks, refunds, taxes, and failed-payment loss;
- acquisition costs, promotions, and affiliate/partner fees where applicable;
- founder/team labor and a reasonable contribution to ongoing product development.

Estimate gross margin and contribution margin for monthly, 3-month, and 6-month access separately. Check sensitivity to heavy usage, unusually long learner periods, and high support needs. If the product includes unlimited use, the price must withstand realistic high-usage scenarios or the terms must disclose fair-use limits without undermining the learning promise.

Do not calculate a final break-even or profit claim until these inputs are known.

## 8. Validation plan before treating prices as approved

Use a small, measurable test rather than relying on expressions of interest alone.

1. **Curriculum workload:** inventory the intended foundation path and estimate/measure active learner-hours.
2. **Offer comprehension:** test whether beginners understand the difference between free Explore, paid Full Access, and continuing membership.
3. **Price test:** present clearly described offers at the proposed prices to suitable learners in Egypt; record actual purchase behavior when possible, not only stated willingness to pay.
4. **Cohort trial:** observe whether free users can complete the trial task without confusion and whether the task gives a fair impression of the product.
5. **Learning outcomes:** measure independent task performance, error detection/recovery, retention, and transfer separately from satisfaction or completion.
6. **Continuation research:** interview learners who find work and current employees about the recurring problems for which they would return and pay.
7. **Renewal behavior:** record paid renewal, pause, cancellation, and reasons; distinguish reaching the learner's goal from dissatisfaction or lack of value.
8. **Cost and margin:** compare actual usage and service costs with the test prices.

A price should be reconsidered if it blocks the intended trainee audience, fails to cover sustainable delivery costs, or cannot be supported by the actual product scope and outcomes.

## 9. Metrics — two separate scorecards, no competence shortcut

**Learning / professional-development measures** may include:

- completion of the planned learning path, with reasons for non-completion;
- independent performance under defined assessment conditions;
- ability to detect and recover from errors;
- delayed retention and transfer to structurally distinct cases;
- practitioner review and later workplace feedback where available;
- learner understanding of what the evidence does and does not prove.

**Commercial / customer measures** may include:

- Explore activation and completion;
- Explore-to-paid conversion;
- purchase by duration and market;
- refund, chargeback, failed-payment, and cancellation rates;
- course/path completion time compared with predicted learner-hours;
- renewal/continuation after the foundation path;
- reasons for renewal and non-renewal;
- professional-member activity and perceived usefulness;
- support load, content-maintenance cost, gross margin, and contribution margin.

Never use payment, renewal, subscription length, screen time, or feature usage as a proxy for competence or workplace readiness. A learner may succeed educationally and choose not to renew; that should not be misclassified as product failure.

## 10. Current implementation boundary

Read-only inspection for this package used:

- Knowledge repository `deixenlabs/DEIXEN-KNOWLEDGE`, `main` at `a302a90563a8cf78bbcfaea64ed2e1acb59f0bd9`.
- App repository `deixenlabs/deixen-app`, `main` at `dde546952b07b17d9bd43722e298a02a3755a706`.
- Relevant app files included `src/ui/ScenarioBank.tsx`, `src/ui/TerminalPractice.tsx`, `src/ui/Ghost.tsx`, and `content/data/slice.json`.

The app contains a learner-facing Terminal practice path and a separate scripted Ghost demonstration using a demo booking. Scenario Bank opens a scenario inside Terminal. The inspected app tree did not contain account, subscription, billing, checkout, payment, paywall, or entitlement files. This is a read-only repository finding at the stated commit, not a claim about an uninspected deployment or future branch.

Therefore this document defines a proposed commercial model only. It does not claim that a free trial gate, paid entitlements, checkout, payment processing, renewal, cancellation, or continuing membership already exists.

## 11. Decisions required before implementation

Before any implementation ticket is authorized, the owner should decide or commission evidence for:

1. Whether the proposed Explore → Full Access → Continuing Professional Membership model is accepted in principle.
2. The exact task and limits included in Explore, and the rule preventing trial activity from becoming independent evidence.
3. The actual curriculum inventory and expected learner-hours that justify 3- and 6-month access periods.
4. Whether the 1,299 / 3,699 / 6,499 EGP and USD 25/month figures should be tested, revised, or rejected.
5. What continuing value is genuinely available after employment and what is only a future roadmap hypothesis.
6. Legal entity, selling countries, payment provider/Merchant of Record, taxes, receipts, refunds, privacy, and data-retention arrangements.
7. The operational rules for renewals, cancellation, grace periods, and evidence availability after expiration.
8. The unit-economics floor and acceptable promotion/discount boundaries.

**Recommendation:** adopt this document as a working commercial hypothesis for research and validation, not as a final price decision or a direction to build Billing immediately.
