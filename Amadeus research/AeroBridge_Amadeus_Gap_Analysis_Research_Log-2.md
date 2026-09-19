# AeroBridge — Amadeus Gap Analysis Research Log

**Status: NOT_READY (§9A.8) overall, but substantially improved this update — see `AeroBridge_PassC_Reconciliation_Report.md`.** The four Phase 1 artifacts were supplied and inspected this session; Pass C moved from entirely BLOCKED to **COMPLETE_WITH_DOCUMENTED_LIMITATIONS**. Major results: D6 (FXX), D18 (direct-sell), and B2 (Split/Claim PNR) are now RESOLVED; **B5 ("Amadeus Offers") is SUBSTANTIALLY RESOLVED as the Cryptic `OFS` family, pending product-owner acknowledgment** — this closes the project's longest-standing escalation; D21 (queue command family) is now strongly confirmed at the domain-truth level and escalated for engineering/Decision-7 review, since it appears to diverge from AeroBridge's own existing engine-reference documentation. B3 (waitlist/passive/ghost/open/ARNK) remains unverified, now as a convergent negative finding rather than an under-researched one. Pass D remains CLOSED WITH BOUNDED CARRY-FORWARD (unchanged). Pass E remains blocked on EG-1 (the raw EgyptAir curriculum document itself, as opposed to Phase 1's citation of it). Pass G and Pass H have each had one targeted session (see the Final Deliverables document) but not a full run. Voiding (A4/D3) and Seat/SSR workflow depth (Domain 7) remain the two largest genuine content gaps, unaffected by this Pass C session. Every item below is logged per the canonical taxonomy at `AeroBridge_Amadeus_Master_Knowledge_Constitution_and_Research_Prompt.md` §9A. Nothing here is authorized for learner-facing use yet.

Baseline compared against: the 27-item starting syllabus at §69 of the constitution (17 Basic + 10 Advanced), which is itself explicitly "input, not final truth."

---

## PASS A — BASIC: Findings

### A1. PNR Optional Elements (SSRs, seat requests, frequent-flyer number, remarks/OSI)
- Epistemic Type: AMADEUS_CRYPTIC_FACT (module-level) / EVIDENCED_INFERENCE (command-level detail)
- Verification Status: PARTIALLY_VERIFIED — confirmed as a named module in Amadeus's own official training catalogue; exact Cryptic entry syntax not yet inspected this session.
- Currentness: CURRENTNESS_UNKNOWN pending §9A.9 (source is a live current course listing, but I have not confirmed a dated revision).
- Curriculum Scope: SHARED_UNCLEAR (not yet checked against actual EgyptAir curriculum evidence — only against the starting syllabus list).
- Relevance Flags: EgyptAir = UNKNOWN, Saudi-Market = YES (implied by real-world PNR handling), AeroBridge Scope = UNKNOWN (not yet a product-owner decision).
- Evidence: Amadeus's own "Reservations in Amadeus" course listing (learn.amadeus.com) names PNR Optional Elements — SSRs, seat requests, frequent flyer numbers, remarks/OSI — as core content.
- Gap: no explicit entry in the EgyptAir Basic starting list.

### A2. Amadeus Queues (placement, monitoring)
- Epistemic Type: AMADEUS_CRYPTIC_FACT (module-level)
- Verification Status: PARTIALLY_VERIFIED, and cross-corroborated by two independent evidence types — see below.
- Currentness: CURRENTNESS_UNKNOWN pending full §9A.9 check.
- Curriculum Scope: SHARED_UNCLEAR.
- Relevance Flags: EgyptAir = UNKNOWN, Saudi-Market = YES, AeroBridge Scope = UNKNOWN.
- Evidence: (1) AMADEUS_CRYPTIC_FACT — Amadeus's own official "Amadeus Reservation and Ticketing Cryptic" certification course lists "Introduction to Amadeus Queues" as core, required content, not an elective. (2) MARKET_FACT — a Riyadh ticketing-officer posting independently named daily queue monitoring as a duty, tied to avoiding auto-cancellation on ticketing time limits. Two independently-typed sources agreeing is stronger than either alone, but they are still not a primary Amadeus technical source for exact command syntax.
- Gap: no explicit entry in the EgyptAir Basic starting list.

### A3. TST (Trip/Transitional Stored Ticket) display
- Epistemic Type: AMADEUS_CRYPTIC_FACT
- Verification Status: PARTIALLY_VERIFIED.
- Currentness: CURRENTNESS_UNKNOWN.
- Curriculum Scope: SHARED_UNCLEAR.
- Relevance Flags: EgyptAir = UNKNOWN, Saudi-Market = INDIRECT, AeroBridge Scope = UNKNOWN.
- Evidence: Amadeus's own "Ticketing in Amadeus (Cryptic)" e-learning course explicitly teaches "how to display and read a TST" as a named step between pricing and ticket issuance.
- Gap: the starting syllabus has fare-quote and pricing entries but no explicit TST-display step connecting pricing to ticketing.

### A4. Voiding a ticket
- Epistemic Type: MARKET_FACT (strong) / AMADEUS_CRYPTIC_FACT (weak, single mention)
- Verification Status: UNVERIFIED at official-source level — do not treat as confirmed yet.
- Evidence: named explicitly in a Saudi ticketing-agent job posting ("Issue, reissue, void, and refund"); also appeared in one third-party lesson-plan title ("Voiding Tickets") that I have not corroborated against an official Amadeus source this session.
- Honest caveat: this is weaker evidence than A1–A3. Logged as a candidate, not a finding, pending an official-source check.

---

## PASS B — ADVANCED: Findings (partial — started, not complete)

### B1. Non-Homogeneous PNR — CONFIRMS existing syllabus item
- The starting syllabus already lists this. A third-party Advanced course outline independently uses the identical term ("Non-Homogeneous PNRs") under its own Advanced module. Treat as corroboration, not a gap: Verification Status upgraded from whatever it previously held to PARTIALLY_VERIFIED (still not an official-source confirmation).

### B2. Split PNR ("Split a Party"), "Claim a PNR" — **RESOLVED AT PASS C (see `AeroBridge_PassC_Reconciliation_Report.md`)**

**Update:** Phase 1's canonical registry confirms `SP` (Split PNR: `SP[p#]` / `SP[p1],[p2],[element].0/.1`) at evidence strength **E5** — the highest tier in the registry, three convergent sources (servicehub.amadeus.com ×2, Tourism School Guide, Complete Amadeus Manual). Phase 1's audit file separately confirms `RO` ("Claim a PNR created in another office/by an airline"), sourced from amadeus.com's official "PNR Claim" product page. **Verification Status: RESOLVED — CANONICAL (Split) and RESOLVED (Claim).** Original finding preserved below for provenance.

- Epistemic Type: EVIDENCED_INFERENCE
- Verification Status: UNVERIFIED — single third-party (non-official) source only. Explicitly flagged NEEDS_EXTERNAL_CONFIRMATION before being treated as a real gap, per §9's evidence hierarchy (one secondary source is not enough for a curriculum-shaping claim).
- Evidence: a single reseller's detailed Advanced lesson list, under "Advanced Changes and Cancellations," alongside Non-Homogeneous PNRs.
- Gap candidate only, not yet a finding.

### B3. Priority Waitlist, Passive Segments, Ghost Segments, Open Segments, ARNK Segments — **CONVERGENT NEGATIVE FINDING AT PASS C**

**Update:** none of these terms appear anywhere in Phase 1's canonical registry (88 records) or audit file (42 entries) — checked directly. This *strengthens* rather than resolves the UNVERIFIED status: two independent research efforts (this project's own web research, and the separate Phase 1 registry build) both failed to substantiate these as real Cryptic commands. Status remains UNVERIFIED, now with higher confidence that this reflects a genuine evidence gap rather than insufficient search effort.

- Same single-source caveat as B2 originally had. These are plausible, commonly-named GDS concepts, but plausibility from general familiarity is explicitly not evidence under this constitution's own §14 — logged as UNVERIFIED / NEEDS_EXTERNAL_CONFIRMATION, not as confirmed gaps, until an official or second independent source is checked.

### B4. Amadeus Mini Rules (fare rules / conditions display)
- Epistemic Type: AMADEUS_FACT
- Verification Status: PARTIALLY_VERIFIED — official amadeus.com product page, current (live page, not just an archived PDF), consistent across multiple language mirrors of the same official page.
- Currentness: CURRENT — meets §9A.9: dated/live official source, direct statement of the feature, no contradicting source found.
- Relevance Flags: EgyptAir = UNKNOWN, Saudi-Market = YES (multiple job postings independently required "strong understanding of airline fare rules"), AeroBridge Scope = UNKNOWN.
- Gap: no fare-rules-display step appears anywhere in the starting syllabus, Basic or Advanced, despite fare quote and pricing both being present.

### B5. "Amadeus Offers" — **SUBSTANTIALLY RESOLVED AT PASS C, PENDING PRODUCT-OWNER ACKNOWLEDGMENT** (was: ESCALATION FLAG)

**PASS C UPDATE (see `AeroBridge_PassC_Reconciliation_Report.md` for full reasoning — summarized here):** the Phase 1 canonical registry contains a full "Amadeus Offers" command family — `OFS` (create an air offer), `RTOF`, `TQQ`, `OFN`, `OFV`, `OFK` — sourced from an official Amadeus quick-card (`amadeus-offers.pdf`). Phase 1's own registry notes state this family's inclusion is justified because **the user's own stated 25-topic curriculum list explicitly names "Amadeus Offers,"** and the registry's top-level scope metadata separately cites `training.egyptair.com/crm/Catalog/9200` (course AM-AG-20) as the confirming source for its overall EgyptAir-curriculum scope.

**What this changes:** the general-industry NDC evidence below is not wrong — NDC/Offer & Order genuinely is what "Amadeus Offers" commonly means industry-wide. But Phase 1's evidence indicates the **EgyptAir curriculum's specific use of the term refers to this Cryptic command family**, not NDC. **New status: PARTIALLY_VERIFIED → SUBSTANTIALLY_RESOLVED (CRYPTIC), with the resolution's provenance being Phase 1's citation of the curriculum list, not this session's own direct inspection of that list.** This session has not independently re-verified the underlying `training.egyptair.com` catalog page or the "25-topic list" itself — the resolution is reported at the confidence level its actual evidence supports, not inflated to "confirmed firsthand."

**Original finding, preserved in full below, unchanged:**

**STATUS AS OF THE ORIGINAL ESCALATION: HELD. Do not resolve, infer, or narrow this further without the actual EgyptAir curriculum source.** The product owner has explicitly confirmed this stays CONFLICT_UNRESOLVED and escalated — no inference about what "Offers" means in the EgyptAir syllabus is authorized until the actual curriculum document is supplied.

- Epistemic Type: AMADEUS_FACT, with a direct conflict risk against product architecture.
- Verification Status: PARTIALLY_VERIFIED on what the industry term commonly means; CONFLICT_UNRESOLVED (§9A.4) on whether that is what the EgyptAir syllabus line item intends.
- Evidence: multiple official amadeus.com and learn.amadeus.com sources consistently describe "Offers" as NDC (New Distribution Capability) / Offer & Order Management — an XML/API-based retailing layer, associated with Amadeus Selling Platform Connect, Amadeus Travel API, and SoapUI-based technical training. No source found ties "Offers" to Cryptic command entry.
- **Why this escalates rather than just logs as a gap:** AeroBridge's frozen command boundary (Decision 8A) is Cryptic-only (`AN→SS→FQD→FXP`). If the syllabus's "Amadeus Offers" line item genuinely means NDC/Offer-Order, it may describe a different interface family than the one this constitution's §6 scopes the mission to, not merely a missing command. Per the checkpoint template's escalation criteria (§91.0), a finding that could touch the frozen command boundary goes to the product owner rather than being silently resolved either way.
- **Resolution path — now substantially fulfilled per the Pass C update above.** Full independent confirmation still awaits direct sight of the curriculum list itself.

---

## EVIDENCE GAPS — EXPLICITLY NAMED, NOT ROUTINE "UNKNOWNS"

Per the product owner's direction, the absence of a needed source is logged here as its own tracked item, not left as silent guesswork or folded into an ordinary UNKNOWN tag.

### EG-1. EgyptAir Basic + Advanced curriculum document — STILL NOT DIRECTLY SUPPLIED (status refined at the Evidence/State Confirmation Gate)
- What's missing: the actual EgyptAir training curriculum/syllabus document. Everything compared against so far is the 27-item **starting syllabus reference** at constitution §69, which that section itself labels "input, not final truth" — a summary list, not the curriculum itself.
- What depends on it: **B5's full independent resolution** — Pass C substantially resolved B5 via Phase 1's own citation of "the user's own stated 25-topic list" and a `training.egyptair.com` catalog reference (see `AeroBridge_PassC_Reconciliation_Report.md`), but this project has still never directly inspected that list itself; every EgyptAir-Relevance flag not touched by Pass C remains UNKNOWN; all of Pass E (Airline/EgyptAir Layer)'s own defining purpose, which still cannot meaningfully run without this project independently holding the source.
- **New at this gate — CF-3, an explicitly unresolved discrepancy, not silently merged:** the constitution's "27-item starting syllabus" and Phase 1's referenced "25-topic list" have never been confirmed to be the same list. Both numbers are real and directly sourced from artifacts this project holds; whether they describe one document or two has simply never been checked. Recorded here rather than assumed either way.
- What is NOT authorized: inferring curriculum intent from the starting-syllabus list's wording, from general EgyptAir-training reputation, or from adjacent Egyptian/regional training material found via search. None of those are the source itself.
- Status: OPEN, blocking Pass E's own defining purpose and B5's *full* (as opposed to substantial) resolution. Not blocking Pass A/B/D/F/G work that doesn't depend on EgyptAir-specific curriculum intent.

### EG-2. Phase 1 Command Registry artifacts — **RESOLVED: SUPPLIED AND INSPECTED (Pass C)**
- The four artifacts (`aerobridge-final-canonical-registry.json`, `aerobridge-command-audit.json`, `aerobridge-out-of-scope-modules.json`, `aerobridge-final-registry-lock-report.md`) were supplied and directly inspected. See `AeroBridge_PassC_Reconciliation_Report.md` for the full reconciliation this enabled.
- Status: CLOSED. Pass C is now COMPLETE_WITH_DOCUMENTED_LIMITATIONS, not blocked.

---

## PASS D — WORKFLOW / STATE / ERROR / RECOVERY: Findings

### D1. Ticketing Time Limit (TTL) as a state/deadline concept, and its Amadeus-specific element names
- Epistemic Type: AMADEUS_FACT
- Verification Status: PARTIALLY_VERIFIED — TTL's existence and function as an Amadeus-managed deadline is confirmed by an official Amadeus product sheet; the exact Amadeus-specific element names are confirmed by a second, independent, high-authority but non-Amadeus source (see below) that happens to specify them precisely.
- Currentness: CURRENT (live official Amadeus Robotics product material).
- Evidence: (1) Amadeus's own "Amadeus Robotics" sales sheet (amadeus.com, official PDF) confirms "Auto-Ticketing Time Limit" as a real product function that calculates the TTL per PNR and notifies the agent, alongside related workflow-cleanup functions named "Auto-Queue 1 Cleaner," "Auto-HX Cleaner," and "Auto-PNR Finder" — the existence of an "Auto-HX Cleaner" feature is itself confirmation that HX (cancelled-by-carrier/auto-cancel status) is a real Amadeus-recognized status. (2) A Finnair trade-desk notice, precise and dated, explicitly distinguishes Amadeus-specific element names from other-GDS ones: **OPW** (warning) and **OPC** (cancellation/last-day-to-issue) for Amadeus agents, versus **SSR ADTK** for non-Amadeus agents. This is exactly the kind of source that does the Amadeus-vs-cross-GDS separation for me rather than me having to infer it (§8A, §4). (3) A likely Amadeus-authored "GTL/ATL" product presentation (third-party-hosted, so not itself an official Amadeus URL, weaker tier) corroborates OPW/OPC and references a "TL transaction" and "1A bookings" (1A being Amadeus's own IATA system code) — consistent with, not contradicting, source (2).
- **Explicitly excluded from this finding, per §4:** ADTK — multiple sources (Finnair, Cathay Pacific) confirm this is the *non-Amadeus* GDS equivalent. It must not be taught as an Amadeus element.
- Curriculum Scope: SHARED_UNCLEAR. Relevance Flags: EgyptAir = UNKNOWN, Saudi-Market = YES (TTL/queue discipline was independently named in Pass F job-posting evidence), AeroBridge Scope = UNKNOWN.
- Gap: the starting syllabus has no explicit TTL / time-limit / auto-cancellation entry anywhere, despite this being a core operational risk every ticketing agent manages daily.

### D2. Ghost segments (GK/GL/GN) and passive segments (PK) — still single-sourced
- Epistemic Type: EVIDENCED_INFERENCE
- Verification Status: UNVERIFIED / NEEDS_EXTERNAL_CONFIRMATION — unchanged from Pass B. Two additional searches this session specifically tried to corroborate these against an official or second independent source and did not find one; the only source remains the same single third-party FAQ site as before.
- **Logged as negative knowledge (§89 of the constitution):** searched twice, no second source found this session. This is recorded so a future pass doesn't repeat the same search expecting a different result — the next step, if this matters, is checking an official Amadeus help-page reference (the source itself points to "HE FXF" and similar Amadeus internal help-page codes, which suggests the real answer lives inside Amadeus's own in-system help, not the open web).
- Not promoted to a finding. Still a candidate only.

### D3. Voiding a ticket — one additional weak corroboration
- Still UNVERIFIED at official-source level (unchanged from A4). One additional independent mention found (a travel-tech vendor's description of ticket-voiding integration with "Amadeus bookings," including a "void queue" concept) — this is a second source, but neither source is Amadeus itself, so this stays below PARTIALLY_VERIFIED. Noted for completeness, not upgraded.

---

## PASS D — CHECKPOINT (first session — preserved as historical; superseded by the continuation checkpoint below, not deleted)

1. **Finished:** TTL/auto-cancellation workflow (D1) reasonably well-sourced, including the important Amadeus-vs-cross-GDS element-name distinction (OPW/OPC vs. ADTK).
2. **Unresolved:** D2 (ghost/passive segment codes) and D3 (voiding) remain single- or non-official-sourced; not promoted to confirmed findings.
3. **Evidence collected:** one official Amadeus product sheet, one airline trade-desk notice (high-precision, non-Amadeus-authored but claim-specific and reliable), one likely-Amadeus-authored but third-party-hosted presentation, one travel-tech vendor mention.
4. **Conflicts discovered:** none new. The ADTK-vs-OPW/OPC distinction is a clarification, not a conflict — sources agreed once the Amadeus/non-Amadeus split was made explicit.
5. **Before next stage:** D2 needs either an official Amadeus source or an explicit decision to leave it as a documented open candidate rather than keep searching. Pass D itself is not complete — this covered time-limit/cancellation workflow only; PNR history/audit trail, error-message text, and recovery procedures after a failed command have not been researched yet.
6. **Allowed to proceed:** yes.

---

## PASS D — CONTINUATION: PNR Construction, History, Pricing-Family, and Reissue Preconditions

Priority order followed: (1) PNR construction/completion, (2) PNR retrieval, (3) availability→sell progression, (4) pricing, (5) ticketing/reissue preconditions — per the priority order given for this continuation. Full structured fields used for high-impact items; compact form for lower-priority/candidate items, per the instruction to prioritize decision-grade coverage over exhaustive cataloguing.

### D4. PNR Mandatory Elements — count discrepancy across interfaces (HIGH IMPACT)

- **Topic:** PNR construction/completion — what must exist before a PNR can be saved/completed.
- **Claim/question:** How many, and which, elements are system-mandatory for a PNR?
- **Epistemic Type:** AMADEUS_FACT (existence of a mandatory-element concept) / CONFLICT_UNRESOLVED (exact count/interface).
- **Interface:** Cryptic claims **5 mandatory elements** (per an official Cryptic-training course title); API (PoweredPNR) documentation states **3 system-mandatory elements**: Name, Phone (Contact), Ticketing.
- **Verification Status:** PARTIALLY_VERIFIED that a mandatory-element concept exists and that Name/Phone(AP)/Ticketing(TK) are among them (consistent with AeroBridge's own already-code-verified `NM`, `AP`, `TK` commands per `05_...Amadeus_Engine_Reference.md`). **UNVERIFIED** on the exact count and full list for Cryptic specifically — the official course names "5" but the fragment retrieved did not enumerate all 5 (it did show the course *covers* names, seats, open segments, and AP/RF/TK, which is at least 4 distinct concepts: Name, [seat is likely NOT mandatory — see Limitations], AP, RF, TK).
- **Currentness:** CURRENT (live official Amadeus training course).
- **Evidence Strength:** E4–E5 for the Cryptic course's existence (official learn.amadeus.com, appearing under two course titles: "Reservations in Amadeus" and "Amadeus Reservations (Cryptic)"); E3 for the API guide (official Amadeus API documentation, but explicitly the wrong interface per this project's own rule that API evidence ≠ Cryptic evidence).
- **Source / exact location:** `learn.amadeus.com/OnlineCourse-1-module-4.en.htm` and `...-1513851695-module-24...`; API: `api.dev.amadeus.net/.../UG_PoweredPNR_main.htm`.
- **Context:** Cryptic training-catalogue naming vs. Powered-PNR API user guide — different interfaces, not directly comparable without more evidence.
- **Contradictions:** the "5" (Cryptic course title) and "3" (API guide, explicit text) are not necessarily the same claim — per this project's own rule, API evidence must not be treated as Cryptic evidence, so this is not logged as a resolved contradiction, only an unresolved count.
- **Limitations:** the Cryptic course's own enumerated "5" was not retrieved verbatim this session — only the module's topic list, which is not the same as its claimed count.
- **Open questions:** what are the exact 5 (Cryptic) vs. how RF (Received From, already code-verified as a real AeroBridge/Amadeus element) fits into either count — RF appears in AeroBridge's engine reference as a distinct required element, which would make at least 4 (Name/AP/TK/RF) before counting anything itinerary-related.
- **Impact/Priority:** HIGH — this is foundational to "PNR construction/completion," priority #1.
- **Phase 1 reconciliation flag:** YES — the exact mandatory-element count and identity should be checked against the Phase 1 registry once available; this session's finding should not be treated as final.

### D5. PNR History (RH command family)

- **Topic:** transaction/persistence semantics; audit trail.
- **Claim:** Amadeus records PNR history (creation + all additions/changes/cancellations/deletions), updated at every EOT (End Of Transaction); displayed via `RH`; partial history via `RH` + element-type code (e.g. `RHA` = flight segments only); combinable codes (e.g. `RHN,J,R` for name/phone/remarks). Sub-codes additionally reported (single, non-official source): `RHM` (MCO/EMD/XSB element history), `RHFA` (ticket-number history).
- **Epistemic Type:** AMADEUS_CRYPTIC_FACT.
- **Verification Status:** PARTIALLY_VERIFIED — the core `RH` mechanism and EOT-triggered update rule are from an **official Amadeus blog post** (amadeus.com/de/blog, E4–E5). The specific sub-codes (`RHA`, `RHN,J,R`, `RHM`, `RHFA`) are corroborated only by a single non-official third-party FAQ site — same status as this log's pre-existing D2 items, not independently verified.
- **Currentness:** CURRENT (official blog, undated in the retrieved fragment but describing live functionality consistent with other current sources).
- **Negative-knowledge note, genuinely useful:** **ARNK segments are explicitly excluded from PNR history** — confirmed by the same official source. Worth preserving so a future pass doesn't assume ARNK behaves like other segments for audit purposes.
- **Source:** `amadeus.com/de/blog/artikel/amadeus-tipp-display-the-pnr-historie` (official); sub-codes from `wandernundmehr.at` (third-party, same site already used for D2/B2/B3, not independent corroboration).
- **Impact/Priority:** HIGH — directly closes the "PNR history" gap this project already flagged as unresearched.
- **Phase 1 reconciliation flag:** YES — `RH` does not appear in AeroBridge's current 37-command engine reference; flag for Phase 1/Pass C comparison as a candidate addition.

### D6. FXX — **RESOLVED AT PASS C** (was: real, distinct command, or superseded terminology? CONFLICT — flagged, not resolved)

**PASS C UPDATE:** Phase 1's canonical registry independently confirms `FXX` (family "Itinerary Pricing" — price an itinerary for the class booked, without storing a TST, view-only), sourced from a TAP Portugal training manual and a Tourism School Guide — two sources entirely independent of this session's own two. **Four independent sources now agree** (this session's two, plus Phase 1's two) that `FXX` is real and functions exactly as this session originally found: price-without-saving, contrasted with `FXP`'s price-and-save. **Verification Status: RESOLVED.** The prior "historical correction" in the canonical curriculum documentation claiming the command was mistakenly written as "FXX" and should read "FXP/FXB" appears, on this evidence, to itself have been the error — recommended for product-owner review, not silently corrected in the curriculum documentation from this log.

- **Topic:** pricing-family command identity — directly touches something the existing canonical corpus treats as already settled.
- **Claim in tension:** AeroBridge's canonical curriculum documentation (`06_AeroBridge_Canonical_Curriculum_and_Coach.md`) states a "historical correction" that the fare-pricing commands are `FXP`/`FXB`, **not** "FXP/FXX," and the code-verified engine reference confirms the dispatch table has no `FXX` handler. **This session's research found two independent, non-official but mutually-consistent sources describing `FXX` as a real, currently-taught, functionally distinct Amadeus pricing command** — "calculates the price of an itinerary without saving the response" (contrasted explicitly with `FXP`, which saves to a TST) — appearing both in a third-party FAQ and in an unrelated training-aggregator's course syllabus (which lists `FXL, FXX, FXR, FXP, FXB, TQT` together as one pricing-family session).
- **Epistemic Type:** EVIDENCED_INFERENCE leaning toward AMADEUS_CRYPTIC_FACT, in direct tension with the project's own prior documented correction.
- **Verification Status:** CONFLICT_UNRESOLVED. Neither side is officially sourced this session — the canonical corpus's "not FXX" correction is itself sourced from curriculum material (per that document's own account) and code behavior (which only proves AeroBridge's own implementation, not real Amadeus); the new evidence is two non-official third-party sources.
- **Conflict Disposition:** UNRESOLVED — genuinely could be HISTORICAL_DIFFERENCE (FXX deprecated at some point, curriculum correction reflects that) or the curriculum correction could itself be the error (FXX misremembered as wrong when it's a real, separate, no-save pricing entry). Cannot be settled from what's available this session.
- **Currentness:** UNKNOWN for FXX specifically — one of the two new sources is undated/low-quality (SEO training-ad aggregator), reducing confidence further.
- **Do NOT resolve this — explicitly flagged per this project's own discipline, same treatment as B5.** This is logged as a live conflict between this session's new findings and prior project documentation, not silently decided in either direction.
- **Impact/Priority:** HIGH — touches the FX-command family already partially implemented and already the subject of one "historical correction" in the canonical corpus; getting this wrong in either direction has real curriculum consequences.
- **Phase 1 reconciliation flag:** YES, explicitly — this is exactly the kind of "materially stronger evidence concerning an existing command" this session's own instructions said to flag for Phase 1 reconciliation rather than resolve alone.

### D7. Amadeus Ticket Changer (ATC) — reissue-count precondition

- **Topic:** exchange/reissue preconditions (priority area #7).
- **Claim:** an unused e-ticket can be reissued via ATC an unlimited number of times (subject to carrier rules); **a ticket can only be reissued once if the itinerary has flown segments.**
- **Epistemic Type:** AMADEUS_FACT.
- **Verification Status:** PARTIALLY_VERIFIED — sourced from an "Amadeus Learning Services" user guide hosted on an airline-industry clearinghouse site (arccorp.com), formatted and branded consistently with genuine Amadeus training material, dated 2016 (currentness caveat below).
- **Currentness:** VERSION_SPECIFIC/dated — 2016 source; not confirmed still current. Flagged for the currentness sweep (Pass G) before being taught as current.
- **Additional context captured:** ATC can reissue e-tickets originally issued in Amadeus *or* in another GDS (Sabre/Worldspan/Galileo named) — the reissue mechanism's reach crosses GDS-of-origin even though the reissue transaction itself is Amadeus-native; a nominal charge applies per use of any of "the four Ticket Changer entries" (count confirmed, not all four individually confirmed this session); informative pricing is the recommended pre-check step before a confirmed pricing entry, given the per-use charge.
- **Impact/Priority:** HIGH — a precondition this specific (a hard "once only" rule after travel begins) is exactly the kind of decision-grade, safety-relevant knowledge Pass D exists to find; getting this wrong could teach a learner to attempt an invalid reissue.
- **Phase 1 reconciliation flag:** YES.

### D8. Manual TST creation (TTC) — precondition

- **Claim:** before a manual TST can be created, the PNR must already contain an itinerary and a passenger name. `TTC` creates one TST per matching PNR-elements/fare-discount-code combination (e.g., separate TSTs for adults vs. infants where fare codes differ).
- **Epistemic Type:** AMADEUS_CRYPTIC_FACT. **Verification Status:** UNVERIFIED at official-source level — single third-party source (same FAQ site as several other findings in this log; not independent corroboration).
- **Impact/Priority:** MEDIUM — directly extends existing finding A3 (TST display) with a genuine precondition, but not officially confirmed.
- **Phase 1 reconciliation flag:** YES (candidate — `TTC` not in the current 37-command set).

### D9. PDR (Past Date Record) — PNR lifecycle / persistence

- **Claim:** a PNR is automatically deleted from the live system 4 days after the start date of its last segment, regardless of whether that segment was cancelled (4 days after departure for a flight segment; 4 days after check-in for a hotel segment).
- **Epistemic Type:** AMADEUS_FACT. **Verification Status:** UNVERIFIED — single third-party source.
- **Impact/Priority:** MEDIUM — genuinely relevant to "transaction/persistence semantics" (priority area D), and to Recovery (a PDR context changes what recovery is even possible), but not officially confirmed.
- **Phase 1 reconciliation flag:** YES.

### D10. Candidate pricing-family commands beyond the current 37 — scope question, not yet a gap

`FXY` (upsell transaction — returns lowest fare plus 6 upsell propositions across fare families; has a follow-up form `FXY1`; combinable with fare-family filtering via `/FF-`) is the best-evidenced of these: **two official-looking Amadeus product/training PDFs** (one hosted via an airline partner site, one via a regional reseller — neither is amadeus.com directly, but both are branded and formatted as genuine Amadeus material, dated 2014–2015) independently describe it consistently. `FXL`, `TQT`, `TTE` appear only in one low-authority aggregator's course-session title and are **not independently corroborated** this session.

- **Epistemic Type:** AMADEUS_CRYPTIC_FACT (FXY) / UNVERIFIED (FXL/TQT/TTE).
- **Scope note, per this session's own instruction not to auto-promote new capabilities into curriculum gaps:** none of these are logged as confirmed curriculum gaps. They are logged as **existence candidates** requiring a separate scope decision — are they relevant to AeroBridge's Basic+Advanced target, or genuinely adjacent/optional functionality? That question is not answered here.
- **Currentness:** dated sources (2014–2015) for FXY specifically — needs a currentness re-check (Pass G) before being taught as current, not just as historically real.
- **Phase 1 reconciliation flag:** YES for all — none of FXY/FXL/TQT/TTE/FQF (fare-family description display, also newly surfaced) are in the current 37-command set.

### D11. XE sibling entries (XI, XD) — very low confidence, noted for completeness only

A third-party open-source SDK's code comments (not Amadeus-authored, describing a wrapped API) associate cancel "entry types" `E`/`I`/`D` with `XE`/`XI`/`XD` respectively. This is weak, indirect, reverse-engineered evidence — logged as a HYPOTHESIS only. AeroBridge's own already-code-verified `XE` behavior (§05 engine reference: covers passengers/segments/AP/TK/RF/hotel/car only) remains the authoritative statement of AeroBridge's own implementation; this finding, if real, would only matter for real-Amadeus scope beyond what AeroBridge currently implements. Not actioned further this session.

---

## PASS D — CONTINUATION 1 CHECKPOINT (historical — superseded by Continuation 2 below, preserved not deleted)

1. **What did we finish?** PNR-construction (D4), PNR-history (D5), a pricing-family conflict requiring escalation (D6), an exchange/reissue precondition (D7), a TST-creation precondition (D8), and a PNR-lifecycle/persistence finding (D9) — covering priority areas #1 (PNR construction), #2 (retrieval, partially, via D5/history), #5 (ticketing, via D8), #7 (exchange/reissue, via D7), and #12 (transaction/persistence, via D9 and D5). Priority areas #3 (availability→sell state dependency), #4 (pricing prerequisites beyond D8), #6 (post-ticketing state), #8 (refund), #9 (EMD/ancillary), #10 (queue workflows beyond A2), and #11 (seat/SSR) were **not reached** this pass.
2. **What remains unresolved?** D2/D3 (carried from the first Pass D session, still open); D6 (FXX — new, high-impact conflict, explicitly not resolved); D10's four-to-five candidate commands (existence plausible, scope undetermined); D4's exact Cryptic mandatory-element count (5 named, not enumerated).
3. **What evidence was collected?** Two additional official/near-official Amadeus sources this pass (the PNR-history blog, the ATC user guide) at E4–E5; several E2–E3 third-party sources, appropriately hedged; one API-interface source explicitly excluded from Cryptic conclusions per this project's own interface-applicability rule.
4. **What conflicts were discovered?** One material conflict (D6, FXX) between this session's new findings and the existing canonical corpus's own prior "historical correction." This is the single most important output of this continuation pass — flagged, not resolved, per explicit standing instruction.
5. **What must happen before the next stage?** D6 needs either an official Amadeus source or explicit product-owner input on how to treat the conflict against the canonical corpus's prior correction. B2/B3/B5 remain untouched, as instructed. Priority areas #3, #4 (beyond D8), #6, #8, #9, #10, #11 remain for a further Pass D session before the pass can be called complete.
6. **Are we allowed to proceed?** Yes, to further Pass D work or to other non-blocked passes (G, H). Not yet to Pass C (still EG-2-blocked) or to any curriculum/design/implementation stage.

**VERDICT: GO WITH CARRY-FORWARD.** Pass D's objective — decision-grade operational knowledge, not exhaustive enumeration — was meaningfully advanced on five of twelve priority areas, and the one high-impact conflict found (D6) is exactly the kind of finding this pass exists to surface. It is not a full GO because seven priority areas remain untouched and D6 is a named, unresolved, carry-forward item with real curriculum consequences. It is not a NO-GO because nothing found this pass blocks continued research — B5 stays escalated, EG-1/EG-2 stay open exactly as before, and D6 is bounded (one specific command family) rather than casting doubt on the research method itself.

---

## PASS F — SAUDI MARKET LAYER: Light touch only (not a full pass)

Evidence source: six current Saudi/regional ticketing-agent and reservations-agent job postings (Riyadh, Sakaka), reviewed as MARKET_FACT only — none of this is Amadeus technical evidence, per §41.

- Queue monitoring is explicitly named as a daily duty in at least one posting — corroborates A2 from the market side.
- Fare-rules literacy is explicitly named in multiple postings — corroborates B4 from the market side.
- Recurring non-Amadeus-technical expectations that don't belong in Amadeus knowledge but are worth the product owner having visibility on: visa/documentation assistance, multi-GDS familiarity (Sabre/Galileo alongside Amadeus — explicitly not imported as Amadeus evidence, per §4), LCC booking-platform familiarity, and general IATA-regulation literacy. These look like Customer-Service/market-context competency territory, not Terminal/Cryptic command territory — consistent with the existing AeroBridge corpus keeping Customer Service as a separate, currently-deferred competency.

---

## CHECKPOINT REPORT (per §91.0 — this session's Pass A / partial B / light F)

1. **What did we finish?** A preliminary sweep: 7 searches against official Amadeus training sources (learn.amadeus.com, amadeus.com product pages), third-party training providers, and real Saudi job postings, compared against the 27-item starting syllabus.
2. **What remains unresolved?** Passes C, D, E, G, H have not started. B2/B3 need a second, ideally official, source before being treated as real gaps rather than candidates. A4 needs an official-source check.
3. **What evidence was collected?** Logged above per item, with source type and verification status — official Amadeus sources (learn.amadeus.com, amadeus.com) carried the most weight; third-party resellers and job postings were used as corroboration or market evidence only, never as sole technical authority.
4. **What conflicts were discovered?** One, and it's the important one: B5 (Amadeus Offers / NDC) — a potential interface-boundary conflict, not just a coverage gap.
5. **What must happen before the next stage?** Product-owner input on B5 specifically; a second source for B2/B3; then continue into full Pass B, plus Pass D (workflow/error/recovery, which hasn't been touched at all yet) and Pass E (EgyptAir-specific layering, which needs the actual EgyptAir curriculum documents, not just the starting syllabus list).
6. **Are we allowed to proceed?** Yes for continuing research. B5 is flagged for your input but does not block continuing other passes in parallel.

---

## PASS D — CONTINUATION 2: Refund, EMD/Ancillary, Queue-Module Confirmation, Availability-Sell (weak)

Priority order followed as instructed: 1 (Availability→Sell), 4 (Refund), 5 (EMD/Ancillary), 6 (Queue) received substantive attention; 2 (Pricing prerequisites), 3 (Post-ticketing state), 7 (Seat/SSR) received only incidental coverage via findings that surfaced while researching other domains. This is disclosed honestly in the per-domain classification below rather than implied to be complete.

### D12. Refund (TRF family) — Priority 4, SUFFICIENTLY_COVERED

- **Topic:** refund workflow, kept explicitly distinct from exchange/reissue/void per this session's own instruction.
- **Claim:** refund is initiated via `TRF` + carrier code + ticket number + `/ATC` (by ticket number), or `TRF/L[line]/ATC` (by PNR line number of the FA/FH element), or `TRF/I-[number]/ATC` (from a query report). Follow-up entries: `TRFU` (update the refund record), `TRF` alone (redisplay), `TRFP` (process/commit — **this is the action that persists the refund and registers it in the sales report**), `TRFIG` (ignore/discard). Refund records display in "cryptic mode" only — panel/graphical mode is explicitly not supported for this.
- **Epistemic Type:** AMADEUS_CRYPTIC_FACT.
- **Verification Status:** PARTIALLY_VERIFIED — the `TRF` family syntax is corroborated across multiple amadeus.com blog/regional-mirror pages (same underlying content, not independent sources, but genuinely official/E4-E5).
- **Currentness:** CURRENT (live official blog content).
- **Precondition / validation finding:** refund guarantee is governed by ATPCO Category 33 filing. A "Data Source Value" of `C` (Category 33 filing, no update) or `N` (Category 33 filing, update limited to Commission/Misc Fees/Form of Payment/Net Fare/Domestic-International indicator) both preserve the Amadeus Fare Guarantee; editing a field outside that list is not confirmed one way or the other this session (**open question**, not guessed at).
- **Voluntary vs. involuntary distinction (explicitly requested by this task):** **ATC voluntary refund is covered by the Amadeus Fare Guarantee Policy. ATC *involuntary* refund is explicitly NOT covered**, because involuntary processing is not based on airline fare-filing. This is a genuine, material, evidence-backed distinction.
- **Postcondition / calculation logic:** an unused ticket is refunded in full (fare + taxes); a partially-flown ticket is refunded only for the unused portion (fare + taxes for unused segments only).
- **Source / exact location:** `amadeus.com/en/blog` and regional mirrors (`/de/`), each titled around "ATC Refund" / refund guarantee.
- **Limitations:** exact response text for a failed/rejected `TRF` was not found this session — `Exact Amadeus Response = UNKNOWN` for refund failure cases specifically.
- **Impact/Priority:** HIGH.
- **Phase 1 reconciliation flag:** YES — the `TRF`/`TRFU`/`TRFP`/`TRFIG` family is not in AeroBridge's current 37-command set.

### D13. FXI — Involuntary Reissue (extends D7, Exchange/Reissue)

- **Claim:** `FXI` is a dedicated Cryptic entry for involuntary reissue, usable for e-tickets regardless of original GDS-of-issue (Amadeus or otherwise), since it does not depend on airline fare-filing — processed without penalty, additional collection, or residual value. Workflow: retrieve PNR → enter `FXI` → reissue. Generates a TST carrying the new booking, original fare/taxes, original fare calculation, an automated endorsement, the original exchange document reference, and original form of payment. Follow-up entries: `TQM/M5` (display penalty/residual TSM), `TQT`/`TQT/T4` (display reissue TST), `TQR` (display ATC Reissue Panel), `TTP`/`TTP/P1` (issue new ticket), `TTM` (issue penalty/residual TSMs); EMD issuance specifically requires the combined `TTP/TTM` form.
- **Epistemic Type:** AMADEUS_CRYPTIC_FACT. **Verification Status:** PARTIALLY_VERIFIED — official amadeus.com-hosted PDF, but dated (2013–2014) — flagged for Pass G currentness re-check, not assumed still current without that check.
- **Impact/Priority:** HIGH — this is exactly the kind of "distinct domain, not merged with voluntary reissue" content this task explicitly asked for.
- **Phase 1 reconciliation flag:** YES.

### D14. EMD-S vs. EMD-A — precondition with exact error text

- **Claim:** two EMD types exist — standalone (EMD-S: services not tied to a flight coupon, e.g. lounge access, name-correction fee) and associated (EMD-A: tied to an e-ticket coupon, e.g. chargeable seat, extra bag). **EMD-A must be issued at the same time as, or after, the e-ticket — never before.** Attempting it before ticket issuance produces the system response: **`MISSING OR INVALID ISSUED IN CONNECTION WITH`**. Coupon status is synchronized between the e-ticket and its associated EMD-A (using the ticket coupon updates the EMD-A coupon's status too).
- **Epistemic Type:** AMADEUS_CRYPTIC_FACT. **Verification Status:** PARTIALLY_VERIFIED. **Source:** a detailed third-party-hosted operational distribution guide (not amadeus.com directly, but internally consistent, detailed, and stylistically matching genuine Amadeus system-message conventions already established elsewhere in this project — e.g. `RECORD LOCATOR NOT FOUND`); corroborated at the concept level (EMD-S/EMD-A split, never-before-ticket rule) by an airline's own official agent-facing portal (easy.finnair.com).
- **This is a genuine "Exact Amadeus Response" finding** — logged with the precondition, the exact failure text, and the semantic meaning kept as separate fields, per this task's own required discipline.
- **Impact/Priority:** HIGH — a precondition this specific, with exact wording, is directly decision-grade.
- **Phase 1 reconciliation flag:** YES.

### D15. FXG — candidate command (EMD pricing / TSM-P creation)

Single-sourced (same operational guide as D14): `FXG` is described as the entry used for automatic pricing and TSM-P (EMD mask) creation for chargeable SSR-based ancillary services. **Epistemic Type:** HYPOTHESIS (single non-official source). Logged as an existence candidate only, consistent with this session's own instruction not to auto-promote new capabilities into confirmed gaps. **Phase 1 reconciliation flag:** YES.

### D16. Queue and "Modifying a PNR" — official module structure confirmed, command-level detail already established elsewhere

- The full official **"Amadeus Reservations (Cryptic)"** course structure was confirmed this session: Getting Started → Amadeus Air → **PNR Mandatory Elements** → **PNR Optional Elements** → **Modifying a PNR** → **Pricing and Fares** → **Amadeus Queues**. This is the closest thing found so far to an actual official syllabus for exactly what AeroBridge's Basic tier is trying to teach.
- **"Modifying a PNR" enumerated in full:** retrieve a PNR *or a PDR* (single combined lesson — connects directly to D9's PDR finding); modify the name element; modify an itinerary; **associate and disassociate PNR elements** (a genuinely new finding — directly relevant to Priority 7's "passenger association / segment association" question, not previously captured); cancel elements in a PNR; copy and print a PNR (upgrades a previously weak, single-source-quiz-derived note to official-source confidence).
- **Queue workflow specifically:** confirmed as its own official module ("What are queues?" / "How to work with queues"), reinforcing A2 — but this session did not find new *command-level* workflow detail beyond what AeroBridge's own already-code-verified engine reference already documents (`QT`/`QC`/`QS`/`QN`/`QI`/`QE`/`QD`). The **Amadeus Robotics Auto-Queue-Sorting** sales sheet (official) adds real operational context — PNRs are algorithmically routed to queues based on PNR remarks and agent-sign data, up to 8 runs/day — but this describes an *automation layer on top of* manual queueing, not manual queue command semantics themselves, and should not be conflated with them.
- **Epistemic Type:** AMADEUS_CRYPTIC_FACT (module structure, official); command-level queue semantics remain largely as previously established via the existing canonical engine reference, not newly re-verified this session.
- **Impact/Priority:** MEDIUM-HIGH for the "associate/disassociate" and PDR-retrieval findings; LOW incremental value for queue command mechanics specifically, since that ground was already covered by existing project knowledge.
- **Phase 1 reconciliation flag:** NO for queue commands (already in the 37-command set); YES for "associate/disassociate PNR elements" as a workflow concept, since it is not explicitly named anywhere in the current engine reference.

### D17. Availability → Sell state dependency — weak, largely unresolved

- Only weak, interface-ambiguous evidence found: a real (API-context) error pattern, **`NEED ITINERARY`**, confirmed to stop firing once air segments exist in the PNR — consistent with, but not direct proof of, a Cryptic-side dependency between prior availability/sell actions and later PNR completion. Also found `NEED RECEIVED FROM` and `NEED TICKETING ARRANGEMENT` as real EOT-time validation error patterns (API-sourced), circumstantially consistent with D4's mandatory-element findings but not confirmed for Cryptic specifically.
- **Epistemic Type:** EVIDENCED_INFERENCE at best. **Verification Status:** UNVERIFIED for the Cryptic-specific claim — the source is API-interface documentation (GitHub-hosted SDK issue discussions quoting real API response bodies), explicitly excluded from Cryptic conclusions per this project's own interface-applicability rule.
- **This domain is the weakest of the seven this session** — logged honestly as such rather than padded with the API evidence dressed up as Cryptic confirmation.
- **Impact/Priority:** HIGH priority per the task's own ordering, but LOW evidence yield this session — a genuine gap, not a covered domain.
- **Phase 1 reconciliation flag:** YES if and when Cryptic-specific evidence is found.

---

## PASS D — CONTINUATION 2: REQUIRED SEVEN-DOMAIN CLASSIFICATION

| # | Domain | Classification | Reason |
|---|---|---|---|
| 1 | Availability → Sell state dependency | **UNRESOLVED** | Only API-sourced, interface-ambiguous evidence found (D17); no direct Cryptic confirmation of SS-without-AN behavior or resulting state |
| 2 | Pricing prerequisites / pricing state | **PARTIALLY_COVERED** | D8 (TTC precondition, from the prior session) plus incidental FXI/FXG findings this session touch pricing-adjacent ground; the core "what PNR conditions FQD/FXP require" question was not directly targeted this session |
| 3 | Post-ticketing state | **UNRESOLVED** | No material new evidence found this session; carried forward unchanged |
| 4 | Refund workflow | **SUFFICIENTLY_COVERED**, with named limitations | D12: mechanism, guarantee rule, voluntary/involuntary distinction, and used/unused calculation are all evidence-backed; exact failure-response text remains UNKNOWN |
| 5 | EMD / ancillary workflow | **SUFFICIENTLY_COVERED**, with named limitations | D14: a genuine precondition with exact error text; D15's FXG stays a candidate, not confirmed |
| 6 | Queue workflow | **PARTIALLY_COVERED** | Command-level mechanics already established via the existing canonical engine reference (not re-earned this session); module-level and adjacent-workflow context (D16) strengthened, but queue-specific state/failure semantics remain unresearched |
| 7 | Seat / SSR / optional-element workflow | **PARTIALLY_COVERED** | D16's "associate/disassociate PNR elements" and D14's chargeable-SSR/EMD connection are genuine, newly-surfaced, relevant findings, but prerequisite/timing/validation detail specific to SSR workflow was not directly targeted |

**No domain is classified SUFFICIENTLY_COVERED without a named limitation, per this task's own standard that a domain is not sufficiently covered merely because a command or module exists.**

---

## PASS D — CONTINUATION 2: REQUIRED FINAL CHECKPOINT

**1. What did we finish?** See the seven-domain table above. In short: Refund (4) and EMD/Ancillary (5) reached SUFFICIENTLY_COVERED with named limitations; Pricing prerequisites (2), Queue workflow (6), and Seat/SSR (7) reached PARTIALLY_COVERED; Availability→Sell (1) and Post-ticketing state (3) remain UNRESOLVED.

**2. What remains unresolved?**
- *Material conflicts:* D6 (FXX) — untouched this session, still open, no new evidence bears on it.
- *Evidence gaps:* Domain 1 (Availability→Sell) and Domain 3 (Post-ticketing state) essentially unaddressed; exact refund-failure response text (D12); FXG's status as a real command (D15).
- *Scope questions:* none newly raised this session beyond D10's existing candidates.
- *Currentness limitations:* D13 (FXI) is 2013–2014-sourced and needs a Pass G check before being taught as current; D12's core `TRF` mechanism is corroborated by live/current pages, lower currentness risk.

**3. What evidence was collected?**
- **`amadeus.com` blog/regional pages (official, E4–E5):** established the full `TRF`/`TRFU`/`TRFP`/`TRFIG` refund entry family, the refund-guarantee rule tied to ATPCO Category 33, and the voluntary-vs-involuntary guarantee distinction (D12).
- **Official Amadeus PDF, dated (E4, currentness-limited):** established `FXI` involuntary reissue's full workflow and generated-document contents (D13).
- **`learn.amadeus.com` official course pages (E4–E5, repeated across multiple modules):** established the full "Amadeus Reservations (Cryptic)" course structure and the complete "Modifying a PNR" lesson list, including the new "associate/disassociate PNR elements" finding (D16).
- **A detailed third-party-hosted EMD operational guide (E2–E3, but internally consistent and stylistically authentic):** established the EMD-A precondition and its exact failure text (D14), plus the `FXG` candidate (D15).
- **An airline's own official agent portal, Finnair (E3–E4, airline-official though not Amadeus-official):** corroborated the EMD-S/EMD-A conceptual split.
- **GitHub-hosted API/SDK issue discussions (E2, explicitly wrong interface):** supplied `NEED ITINERARY`/`NEED RECEIVED FROM`/`NEED TICKETING ARRANGEMENT` as real API-level validation messages — used only as weak, interface-flagged circumstantial context (D17), not as Cryptic evidence.

**4. What conflicts were discovered?** None this session. (D6 remains the one standing conflict, carried forward unchanged from Continuation 1 — not rediscovered or re-examined this session, per the instruction not to revisit it without materially new evidence.)

**5. What must happen before the next stage?**
- Remaining Pass D work: a further session should directly target Domain 1 (Availability→Sell, with Cryptic-specific sources) and Domain 3 (Post-ticketing state), both essentially untouched.
- Carry-forward items, unchanged: D2, D3, D4 (exact mandatory-element count), D6 (FXX), D10 (FXY/FXL/TQT/TTE/FQF), now also D15 (FXG) joins this list.
- B2, B3, B5 — untouched, exactly as instructed.
- EG-1, EG-2 — unchanged, still blocking Pass C and the EgyptAir-specific half of Pass E.
- Phase 1 reconciliation requirements: D5, D7 (from Continuation 1), plus D12, D13, D14, D15, and D16's "associate/disassociate" concept all now carry `Phase 1 Reconciliation Flag = YES` — a growing list that Pass C will need to work through once the four artifacts are supplied.

**6. Are we allowed to proceed?**

**VERDICT: GO WITH CARRY-FORWARD.**

Two of seven priority domains reached sufficiently-covered status with honestly named limitations; three reached partial coverage with genuine new findings; two remain materially unresolved and are named as the top priority for the next Pass D session rather than left ambiguous. No critical evidence gap was found that prevents continued research — B5 stays escalated exactly as before, EG-1/EG-2 stay open exactly as before, D6 remains a bounded, single-command-family conflict rather than a method-wide problem. This is not a full GO because two of seven domains (including the highest-priority one, Availability→Sell) are still UNRESOLVED, and Pass D's own completion standard explicitly forbids declaring it closed while that is true.

---

## PASS D — FINAL CLOSURE ATTEMPT: Findings

Priority order followed exactly as instructed: A (Availability→Sell), B (Post-ticketing state), then incidental strengthening of C/D/E (Pricing, Queue, Seat/SSR) where evidence surfaced naturally.

### D18. Availability → Sell — **RESOLVED AT PASS C** (was: line-number dependency confirmed; direct-sell design-vs-fact question open)

**PASS C UPDATE:** Phase 1's canonical registry confirms a second `SS` form — `SS[airline][flight][class][date][route][status][seats]` — explicitly documented as a "long sell," used specifically **as an alternative to selling directly from an `AN` availability line**. This resolves the open question: real Amadeus supports both the from-display sell and a standalone "long/direct sell" with no prior availability display required. AeroBridge's own existing engine-reference description ("sell from a displayed availability line, OR direct sell") was accurate all along. **Verification Status: RESOLVED — both mechanisms are confirmed AMADEUS_CRYPTIC_FACT, not an AeroBridge-only design decision.**

- **Claim:** `SS1Y3` = sell one seat, class Y, **from line 3 of the current display** — the line number explicitly references a prior availability (or similar) display. Source: a document consistently branded "© Amadeus Training" (Scribd-hosted, so authenticity not independently confirmable, but internally consistent and structurally matching this project's other confirmed findings — e.g. its own listed topics include "SPLIT PNR," corroborating B2 from a second source for the first time).
- **Epistemic Type:** AMADEUS_CRYPTIC_FACT (moderate confidence). **Verification Status:** PARTIALLY_VERIFIED — real, specific syntax showing the line-number mechanism, but not an official amadeus.com/learn.amadeus.com source.
- **Adversarial finding, genuinely important:** every source found this session that shows real `SS` usage does so **from a display line**. None confirmed a freestanding "direct sell" (flight/class/date specified directly with no prior display) in real Amadeus. **AeroBridge's own already-code-verified engine reference states `SS` supports "sell from a displayed availability line, OR direct sell."** This session did not find evidence either confirming or refuting that a real-Amadeus "direct sell" mode exists — logged explicitly as an open question rather than assumed either way. **If no such evidence is ever found, AeroBridge's "direct sell" support should be examined as a possible `AEROBRIDGE_DESIGN_DECISION` (a simulator convenience) rather than an established `AMADEUS_FACT`** — this is exactly the kind of self-check this project's own rules require, and it is flagged here rather than resolved unilaterally.
- **Still unresolved:** exact failure text/behavior for an invalid line reference or a sell attempted with no prior display. `Exact Amadeus Response = UNKNOWN` for this case.
- **Impact/Priority:** HIGH. **Phase 1 reconciliation flag:** YES — both for the line-referencing mechanism and for the direct-sell design-vs-fact question.

### D19. Post-ticketing segment-status shift and a real exact-error finding — heavily interface-caveated

- **Claim:** a segment can shift from status `HK` to a new status `TK` when the operating airline changes the flight's scheduled departure/arrival time before departure. Attempting to issue a ticket against a segment in `TK` status produces the response **`VERIFY ITINERARY`** — e-tickets cannot be issued against that status. A described system change re-sets the status from `TK` back to `HK` before issuance to avoid the error.
- **Epistemic Type:** AMADEUS_FACT — **but with a major, explicit interface/scope caveat.**
- **Verification Status:** PARTIALLY_VERIFIED for the underlying mechanism; **NOT verified for Cryptic specifically.** Source: a British Airways NDC-helpdesk release-notes wiki, describing "OrderCreate & AirDocIssue" — explicitly NDC/API message types, and airline-specific (British Airways) release documentation, not general Amadeus Cryptic documentation.
- **Why this is logged despite the caveat:** segment status codes like `HK` are typically part of the shared underlying inventory data model rather than an NDC-only construct, so this is plausibly relevant to Cryptic too — but "plausibly relevant" is exactly the kind of claim this project's rules forbid promoting without direct confirmation. **This finding must not be taught as confirmed Cryptic behavior on this evidence alone.** It is exactly the kind of "Amadeus product evidence ≠ Amadeus Cryptic evidence" case this session's own governing instructions specifically warned about.
- **Impact/Priority:** HIGH if it does transfer to Cryptic (a real, safety-relevant, exact-text finding); currently blocked from full promotion by the interface caveat.
- **Phase 1 reconciliation flag:** YES, explicitly, with the interface caveat carried forward.

### D20. FXQ — voluntary ATC reissue (distinct from FXI, extends D7/D13)

- Official amadeus.com campaign page confirms a 4-step voluntary reissue flow — specify change → reprice → update PNR → reissue — with key commands `FXQ` and `TTP/TTM`. This is now the third distinct FX-family reissue/pricing entry confirmed this session (alongside `FXI` involuntary and the still-conflicted `FXX`), plus `FQNATC/CXR` to check ATC-eligible airlines. Category 31 (reissue) vs. Category 33 (refund) guarantee scope independently reconfirmed, cleanly sourced.
- **Epistemic Type:** AMADEUS_CRYPTIC_FACT. **Verification Status:** PARTIALLY_VERIFIED (official source, but a marketing/campaign page rather than a technical training document — command names given, not full syntax).
- **Phase 1 reconciliation flag:** YES.

### D21. Queue command family (`QE`/`QN`/`QD`) — **CONFIRMED AND ESCALATED AT PASS C** (was: two-source, mutually-reinforcing domain-truth finding, unresolved)

**PASS C UPDATE:** Phase 1's canonical registry independently confirms the exact same functions this session found: `QE` = place PNR on a queue; `QN` = remove current item from queue, show next; `QD` = delay/requeue current item, show next. Phase 1's own audit file shows it had already investigated and resolved a closely related notation question (slash-formatted `QE/nn` vs. space-formatted `QE nn`) using the same two source types this session independently found (an official amadeus.com blog and a Travelport cross-GDS comparison table) — a striking independent methodological convergence.

**This still diverges from AeroBridge's own existing, code-verified engine-reference documentation**, which describes `QE`/`QD` as "exit queue mode" and `QN` as "next within an active browse session." With three independent lineages (this session, Phase 1, and Phase 1's own prior audit work) now agreeing on the domain-truth side, **this is escalated, not further researched** — see `AeroBridge_PassC_Reconciliation_Report.md` §H. Whether AeroBridge's actual implementation code matches its own documentation, and whether either matches this now-strong domain-truth consensus, requires direct code re-inspection and a product/engineering decision, not more web research. **Verification Status: PARTIALLY_VERIFIED → domain truth now well-confirmed; implementation-truth reconciliation still pending.**

**Updated during the Pass D Final Closure Report (see `AeroBridge_PassD_Final_Closure_Report.md` for full reasoning; summarized here).**

- Two new, independent-of-each-other sources were found: (1) an **official amadeus.com blog post** ("How to display and process queues") describing the real workflow — `QT` (display active queues) → `QS[queue]C[category]` (start processing) → `QD` (redisplay: requeue current, show next) / `QN` (**remove current from queue**, show next) / `QI` (ignore changes and **leave the queue**); (2) a **Travelport-hosted cross-GDS format-comparison table** whose Amadeus-specific column independently states "Place PNR on queue" = `QE[number]` and "Queue remove" = `QN`.
- **These two sources converge with each other** and both diverge from AeroBridge's own already-code-verified engine reference, which documents `QN`/`QI` as "next/ignore within an active queue-browse session" and `QE`/`QD` as "exit queue mode / delete PNR from queue."
- **Framing, not a verdict:** this is implementation truth (AeroBridge's own verified code) vs. domain truth (what real Amadeus does) — per this project's own framework, a difference between them is not automatically an error on either side. This is precisely the kind of item Decision 7's domain/SME validation dependency exists to examine.
- **Verification Status:** PARTIALLY_VERIFIED (domain-truth side, now two converging sources) / CONFLICTING with AeroBridge's implementation truth. Still not resolved — no attempt was made to decide which is "right."
- **Impact/Priority:** HIGH — this now touches an already-implemented AeroBridge command family, not merely a prospective curriculum topic.
- **Phase 1 reconciliation flag:** YES — explicitly named as a priority item for Pass C, and specifically for whatever Domain/SME validation work (Decision 7) eventually executes for the queue command family.

### Minor confirmations (compact form)

- **AIS resolved:** "Amadeus Information Pages," accessed via `HE AIS` — closes a previously-open terminology question (§ of the constitution had flagged this as undefined jargon).
- **B2 (Split PNR) strengthened:** now corroborated by a second, differently-sourced document (the "©Amadeus Training"-branded quick reference) in addition to the original single third-party FAQ — still not officially confirmed, but no longer single-sourced.
- **TWD, `HE ETT xx`, MSC tag:** reconfirmed (same recurring third-party source as before — not new independent corroboration, just consistency).
- **TTP/ITR** (combined ticket-issuance + itinerary-receipt-print entry) and **TTH** (display deleted TSTs from the TST index) — new, single-sourced, minor-value findings.
- **Course-sequence confirmation:** the official "Reservations in Amadeus" course confirms "Itinerary and invoice" as its own module positioned between "Modifying a PNR" and "Pricing and Fares" — a genuine, if module-level rather than command-level, workflow-sequence data point for Priority 2.

---

## PASS D — FINAL CLOSURE TEST: Seven-Domain Table

| Domain | Final Status | Material Limitation | Blocking? |
|---|---|---|---|
| 1. Availability → Sell | **PARTIALLY_COVERED** *(upgraded from UNRESOLVED)* | Line-number sell mechanism now evidenced (moderate source); failure-mode text and the real-vs-simulator status of "direct sell" remain open | NO |
| 2. Pricing prerequisites/state | PARTIALLY_COVERED *(unchanged)* | Module sequence strengthened; core PNR-condition prerequisites for FQD/FXP not directly targeted this session | NO |
| 3. Post-ticketing state | **PARTIALLY_COVERED** *(upgraded from UNRESOLVED)* | D19 is a real, high-value, exact-text finding, but is NDC/airline-specific-sourced and not confirmed for Cryptic | NO |
| 4. Refund | SUFFICIENTLY_COVERED *(unchanged, reconfirmed)* | Exact failure-response text still UNKNOWN | NO |
| 5. EMD / Ancillary | SUFFICIENTLY_COVERED *(unchanged, reconfirmed)* | FXG remains an unconfirmed candidate | NO |
| 6. Queue workflow | PARTIALLY_COVERED *(unchanged, but a new conflict candidate — D21 — now attached)* | Command-level mechanics partly established, partly in tension with existing documentation (D21) | NO |
| 7. Seat / SSR / Optional | PARTIALLY_COVERED *(unchanged)* | No new SSR-specific workflow research this session; associate/disassociate reconfirmed but not investigated further | NO |

No domain is BLOCKED. No domain is classified SUFFICIENTLY_COVERED without a named limitation.

---

## PASS D — FINAL CLOSURE CHECKPOINT

**1. What did we finish?** Both previously-UNRESOLVED domains (Availability→Sell, Post-ticketing state) were meaningfully advanced to PARTIALLY_COVERED with real new evidence. Refund and EMD/Ancillary remain SUFFICIENTLY_COVERED on reconfirmation. Pricing, Queue, and Seat/SSR received incidental strengthening but stay PARTIALLY_COVERED.

**2. What remains unresolved?**
- *Technical uncertainty:* D18's direct-sell question; D19's interface applicability; D21's QE conflict.
- *Scope uncertainty:* D20 (FXQ), D15 (FXG) remain existence candidates only.
- *Currentness uncertainty:* several sources this session were very old (2000, 2002) and were explicitly excluded from confident conclusions rather than blended in as if current.
- *Evidence weakness:* D2/D3/D4 carried forward unchanged, no new evidence this session.
- *Phase 1 reconciliation:* the list has grown materially this pass (D18, D19, D20, D21 all added) — Pass C's eventual workload is larger than it looked two sessions ago, which is itself useful information, not a problem to hide.
- *EgyptAir curriculum dependency:* EG-1 unchanged; B5 untouched.

**3. What evidence was collected?** See D18–D21 above, each with source, source type, applicability caveat, and what it actually established — not merely listed by URL.

**4. What conflicts were discovered?**
- *True candidate contradiction:* D21 (QE) — third-party claim directly conflicts with AeroBridge's own existing code-verified documentation. Not yet a "true contradiction" in the confirmed sense (single weak source vs. established AeroBridge behavior), but structurally the same kind of issue as D6.
- *Interface difference, not a contradiction:* D19 (HK→TK / VERIFY ITINERARY) — NDC-sourced, not shown to contradict anything Cryptic-side, simply not yet confirmed for it.
- *No currentness/version contradictions found this session* beyond the general caution already applied to old sources.

**5. What must happen before the next stage?**
- Remaining Pass D work, if resumed: direct Cryptic-specific confirmation for D18 (failure mode) and D19 (interface applicability); dedicated SSR-workflow research (Domain 7 was never directly targeted, only touched incidentally across three sessions).
- Carry-forward, updated list: D2, D3, D4, D6, D10, D15, D18 (direct-sell question), D19 (interface caveat), D20, D21 (QE conflict), B2 (now two-sourced but still not official), B3, B5.
- EG-1, EG-2 — unchanged.
- Phase 1 reconciliation requirements: materially larger list than at the start of this session — D5, D7, D12–D21 collectively.

**6. Are we allowed to proceed?**

**VERDICT: GO WITH CARRY-FORWARD.**

This is not a forced closure and not a full GO. Genuine, real progress was made on exactly the two domains this session was told to prioritize — both moved from UNRESOLVED to PARTIALLY_COVERED with defensible new evidence, including one exact-error-text finding (D19, appropriately caveated) and one genuine self-critical finding about AeroBridge's own implementation (D18's direct-sell question). But five of seven domains remain short of SUFFICIENTLY_COVERED, and this session surfaced two new candidate conflicts (D19's interface applicability, D21's QE collision) rather than resolving existing ones — which is a sign of honest research working correctly, not a sign of insufficient rigor, but it does mean the GO bar ("no material workflow/state safety question remains hidden") is not yet met. Nothing found this session blocks further work: B5 stays exactly as escalated, EG-1/EG-2 stay exactly as open, and every new conflict is bounded to a specific, named command or claim rather than casting doubt on the research method itself. A further, dedicated session targeting Domain 7 directly (never yet researched head-on) and the D19/D21 interface questions would be the highest-value next Pass D work, should Pass D be resumed rather than the mission moving to other non-blocked passes (G, H) first.
