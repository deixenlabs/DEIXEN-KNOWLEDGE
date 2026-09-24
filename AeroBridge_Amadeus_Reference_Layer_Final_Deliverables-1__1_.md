> **STATUS BANNER — 2026-09-24.** **Historical Amadeus evidence — research
> leads only.** Every finding in this file is **UNVERIFIED** under the Amadeus
> Verification Standard (07 Decision 12): sources are named by site or
> description, without URL and access date. Its statuses ("RESOLVED",
> "SUFFICIENT FOR TRAINING", "Canonical", readiness verdicts, "for Opus")
> describe the ended pre-Opus phase. Findings are re-checked one by one in
> Execution Plan Phase 3 and, if they pass, recorded in
> `DEIXEN_Amadeus_Verified_Reference.md`. Working name now DEIXEN (earlier:
> AeroBridge); owner: Karim (earlier records: "Malik"). Nothing here may be
> taught as fact (07 Decision 13).
> **Superseded version:** this is the earlier edition of
> `AeroBridge_Amadeus_Reference_Layer_Final_Deliverables-2.md`; read that file
> instead.


# AeroBridge — Amadeus Reference Layer: Final Deliverables

Master Curriculum & Knowledge Gap Analysis · Recommended Knowledge Architecture · Knowledge Build Plan · Prioritized Research Backlog · Acceptance Criteria

**Source basis:** `AeroBridge_Amadeus_Gap_Analysis_Research_Log.md` (findings A1–A4, B1–B5, D1–D21, Pass F observations) and `AeroBridge_PassD_Final_Closure_Report.md`, both already delivered and not restated here in full — this document synthesizes and structures their content into the five required deliverables rather than re-deriving it. One additional targeted search was performed this session (Seat/SSR, Domain 7) with limited yield, logged below rather than treated as a completed pass.

**Product/curriculum boundary applied throughout, per explicit instruction:** EgyptAir material is internal reference/baseline evidence only. The learner-facing identity is **AeroBridge Professional Amadeus Basic + Advanced** — no "EgyptAir Basic," "EgyptAir Layer," or "EgyptAir → Saudi → Job Readiness" framing appears anywhere below. Where a finding originated from EgyptAir-adjacent curriculum comparison, it is described by what it evidences (general Amadeus content, Basic/Advanced placement, a gap), not by carrier label.

---

## PASS STATUS — FULL RECONSTRUCTION, NOT ASSUMED

| Pass | Status | Basis |
|---|---|---|
| A — Basic Foundations | PARTIALLY COMPLETE, mature in places | A1–A4 plus incidental Basic-tier findings across D-series (D4, D5, D18) |
| B — Advanced Air | PARTIALLY COMPLETE | B1–B5 (B5 escalated/held) plus D6, D10, D13, D15, D20 |
| C — Phase 1 Reconciliation | **BLOCKED — 0% possible** | EG-2: four Phase 1 artifacts not supplied |
| D — Workflow/State/Error/Recovery | **CLOSED WITH BOUNDED CARRY-FORWARD** | Per the dedicated closure report; not reopened here |
| E — Carrier/Airline Context | **BLOCKED — 0% possible** for its EgyptAir-specific half | EG-1: actual curriculum document not supplied. The general-vs-carrier-specific *classification exercise* itself (§37/38 of the constitution) has been applied incidentally wherever findings were logged (e.g., D1's OPW/OPC-vs-ADTK split), but a dedicated Pass E has not run |
| F — Market/Employability Context | LIGHT TOUCH, sufficient for its declared purpose | Six Saudi job postings; used only as MARKET_FACT, never blended into technical claims |
| G — Currentness/Legacy Sweep | **PERFORMED THIS SESSION** — see below | New synthesis, not new search |
| H — Adversarial Completeness Review | **PERFORMED THIS SESSION** — see below | New synthesis, not new search |

**This session's one new research action:** a targeted search for Seat/SSR (Domain 7) Cryptic-specific workflow detail. Yield was low and mostly interface-contaminated (Web Services API/SDK documentation) — the one genuine finding: real Cryptic syntax `SR CTCE-BA HK1/[data]` (email contact via SSR), corroborating AeroBridge's own already-code-verified `SR` command at the syntax-example level, and a further confirmation of the `HE [topic]` in-system-help convention. This does not upgrade Domain 7 beyond its existing PARTIALLY_COVERED status — logged as an attempt with limited yield, not a completed pass, consistent with the standing negative-knowledge discipline.

---

## PASS G — CURRENTNESS / LEGACY SWEEP (performed this session)

A targeted sweep, not a re-search, applying the constitution's §9A.9 procedure to every source already on record whose date is known or suspiciously old.

| Source | Date | Classification | What depends on it |
|---|---|---|---|
| "Amadeus Clue Card" (Scribd) | Issued 2002 | **HISTORICAL — do not teach as current without independent modern confirmation** | Only used for `HE AN`, a help-page reference pattern stable enough that its age is lower-risk, but still flagged |
| Dennis L Foster training material | Copyright 2000 | **HISTORICAL — excluded from all conclusions this project has drawn.** Shown older availability-syntax variants (e.g. `ACR10MAY1700`) that were explicitly *not* promoted anywhere in the log | Nothing current depends on this source; it was correctly quarantined at the point of discovery |
| ATC user guide (arccorp.com-hosted) | Dated 2016 | **DATED / PLAUSIBLY APPLICABLE** — the reissue-once-if-flown precondition (D7) and the four-Ticket-Changer-entries count rest partly on this | Should be the first item re-verified if/when a currentness-specific pass runs against an official source |
| FXI involuntary reissue PDF | Dated 2013–2014 | **DATED / PLAUSIBLY APPLICABLE** | D13's full FXI workflow |
| Fare Families / FXY sales sheets | Dated 2014–2015 | **DATED / PLAUSIBLY APPLICABLE** | D10's FXY finding |
| amadeus.com blog posts (PNR history, queue processing, ATC/refund) | Undated in the retrieved fragments, but live current pages | **CURRENT** — these are the strongest-currentness sources in the whole log, precisely because they are live pages rather than archived PDFs | D5, D12, D21 |
| Amadeus Mini Rules product page | Live current page (with a 2013 PDF as separate historical corroboration) | **CURRENT**, per the explicit §9A.9 reasoning already applied in B4 | B4 |
| British Airways NDC release notes | Dated 2018 | **CURRENT for NDC**, but this is an *interface* limitation, not a *currentness* one — D19's caveat is about interface applicability, not age | D19 |
| Turkish university course catalogs, Quizalize quiz | Undated / low-authority | **CURRENTNESS_UNKNOWN**, and low authority regardless of date | Only ever used as weak corroboration, never as primary evidence |

**Pass G conclusion:** no finding currently promoted as a real gap or a real curriculum candidate rests on a source classified HISTORICAL. Two DATED clusters (the 2013–2016 ATC/reissue material) carry the largest currentness risk of anything actually in active use and are named as the top priority if a dedicated currentness-focused pass is ever run. This does not constitute a full Pass G in the sense of exhaustively re-checking every claim against a live source — it is the targeted sweep the governing instructions call for, sufficient to prevent stale material from being silently treated as current.

---

## PASS H — ADVERSARIAL COMPLETENESS REVIEW (performed this session)

For each class of existing finding: what evidence would prove it wrong, and does that evidence exist or is its absence itself informative?

| Finding class | Adversarial question | Result |
|---|---|---|
| B4 (Mini Rules), D12 (Refund), D14 (EMD precondition) — the strongest-sourced findings | Is there a contradicting official source? | None found across four Pass D sessions of active searching; these remain the most defensible items in the whole log |
| D1 (OPW/OPC vs. ADTK) | Could ADTK actually be Amadeus-valid in some configuration, making the exclusion too strong? | Two independent sources (Finnair, Cathay Pacific) both state ADTK is specifically the *non*-Amadeus format — this is an unusually well-corroborated negative finding, not a weak one |
| D6 (FXX) | Could the "historical correction" itself be the error rather than the new evidence? | **Genuinely cannot be determined from available evidence — this is exactly why it stays CONFLICT_UNRESOLVED rather than being adversarially "won" by either side.** Both directions remain live possibilities |
| D18 (direct-sell) | Could AeroBridge's own implementation be right and this session's research simply incomplete? | Yes, entirely possible — the correct conclusion is not "AeroBridge is wrong," it is "unconfirmed either way," which is exactly how it is currently logged |
| D21 (queue family) | Could the two new sources both be wrong, or describing a different Amadeus configuration/era than AeroBridge's code was built against? | Plausible — this is precisely why the finding is framed as implementation-truth-vs-domain-truth rather than a correction, and routed to Decision 7's validation process rather than resolved here |
| A1–A3 (PNR optional elements, Queues, TST) | Could these already be implemented in AeroBridge and simply missing from the engine reference documentation, rather than genuine gaps? | **Checked directly:** none of `RH`, the full `SR` optional-element set, or `AIS` appear in the 37-command engine reference's command table — genuine gaps, not documentation gaps |
| Pass F findings | Could "queue monitoring" and "fare-rules literacy" job-posting evidence be generic travel-industry boilerplate rather than genuinely Amadeus-specific signal? | A fair challenge — these are MARKET_FACT, explicitly not technical evidence, and this report does not treat them as anything stronger than corroborating context, consistent with how they were always logged |
| The whole four-session Pass D effort | Is there a systemic bias toward finding "gaps" because that's what the task kept asking for, at the expense of confirming what's already correct? | **Partially fair.** B1 (Non-Homogeneous PNR, confirming an existing syllabus item) is the clearest counter-example — not every session's output was a new gap. But the log is honestly weighted toward gap-finding because that was each session's explicit brief; this is named here as a structural note for whoever next assesses the log's balance, not corrected retroactively |

**Pass H conclusion:** no existing finding was overturned by this adversarial pass. Two findings (D6, D21) were already correctly held as unresolved rather than falsely resolved — the adversarial review confirms that caution was warranted, not excessive. One structural bias (gap-finding emphasis) is named honestly rather than hidden.

---

## DELIVERABLE 1 — MASTER CURRICULUM & KNOWLEDGE GAP ANALYSIS

### 1.1 Basic requirements — coverage status

| Topic area | Coverage | Evidence | Gap/Note |
|---|---|---|---|
| Availability display | COVERED | Existing engine reference (`AN`/`SN`, code-verified) + this session's official course confirmation | — |
| Sell segment | COVERED_NEEDS_DEEPER_BEHAVIOR | `SS` line-reference mechanism evidenced (D18); failure mode and "direct sell" status unconfirmed | Direct-sell should be reviewed as possible `AEROBRIDGE_DESIGN_DECISION` |
| PNR mandatory elements | PARTIALLY_COVERED | Name/AP/TK/RF pattern well-evidenced; exact Cryptic count (cited as "5" three times, never enumerated) unresolved | D4 carry-forward |
| PNR optional elements (SSR, seat, FF, remarks/OSI) | PARTIALLY_COVERED | Official module confirmed (A1); one real syntax example (`SR CTCE`); workflow-level detail thin | Genuine, named gap — MISSING at the workflow-prerequisite level despite module confirmation |
| PNR retrieval / modification / cancellation | COVERED_NEEDS_DEEPER_BEHAVIOR | Official "Modifying a PNR" module fully enumerated (D16): retrieve PNR-or-PDR, modify name/itinerary, associate/disassociate elements, cancel elements, copy/print | "Associate/disassociate" itself is a newly-surfaced concept with no command-level detail yet |
| PNR history | COVERED | D5, official source, including the ARNK-exclusion negative-knowledge note | — |
| Pricing / fare quote | COVERED_NEEDS_DEEPER_BEHAVIOR | `FQD` confirmed via existing reference; official module sequence (Itinerary/Invoice → Pricing) confirmed; PNR-condition prerequisites for pricing not directly targeted | MISSING: exact FQD/FXP prerequisite conditions |
| Ticketing / TST | COVERED | A3, D8 (TTC precondition), official TST-then-issue sequence confirmed | — |
| Voiding | MISSING/UNVERIFIED | A4/D3 — weak, non-official sourcing only across three attempts | Genuine gap, explicitly not promoted |
| Queues | COVERED_NEEDS_DEEPER_BEHAVIOR | A2, D16 module-level; D21 command-family in tension with AeroBridge's own implementation | Escalated, not a simple gap |
| Ticketing Time Limit / auto-cancellation | COVERED | D1 — one of the best-evidenced findings in the whole log | — |
| Help/information system (`HE`, AIS) | COVERED | Resolved this pass — `HE [topic]` pattern and AIS ("Amadeus Information Pages") both confirmed | — |
| Basic error interpretation | PARTIALLY_COVERED | Existing 34-message error taxonomy (engine reference) plus D1/D14/D19's exact-text findings; no dedicated Basic-tier error sweep performed | — |

### 1.2 Advanced requirements — coverage status

| Topic area | Coverage | Evidence | Gap/Note |
|---|---|---|---|
| Non-Homogeneous PNR | COVERED | B1, confirms existing syllabus item | — |
| Split / Claim PNR | PARTIALLY_COVERED | B2, now two-sourced (D18's closure-session finding) but neither official | Candidate, not confirmed |
| Fare rules (Mini Rules) | MISSING from syllabus, COVERED as a finding | B4 — one of the strongest findings in the log, absent from the starting syllabus entirely | Recommend explicit inclusion |
| Pricing-family variants (FXX/FXY/FXL/TQT/TTE/FQF/FXG/FXQ/FXI) | MIXED | FXQ/FXI reasonably well-evidenced (D13, D20); FXX conflicted (D6); FXY moderately evidenced (D10); FXL/TQT/TTE/FQF/FXG weakly evidenced or single-sourced | Scope decision needed — see §1.4 |
| Reissue (voluntary/involuntary) | COVERED | D7, D13, D20 — genuinely strong, distinct treatment of voluntary vs. involuntary as instructed | — |
| Refund | SUFFICIENTLY_COVERED | D12 | Exact failure text still unknown |
| EMD / Ancillary | SUFFICIENTLY_COVERED | D14, D15 | FXG unconfirmed |
| Amadeus Offers | **CONFLICT_UNRESOLVED / ESCALATED — B5, unchanged** | — | Blocked on EG-1 |
| Waitlist / Passive / Ghost / Open / ARNK segments | UNVERIFIED | B3/D2 — investigated across three sessions, never reached a second official source | Genuine, well-documented negative finding |
| Seat / SSR workflow (beyond module existence) | LARGELY UNRESEARCHED | Domain 7 — never received a dedicated session; this session's targeted attempt yielded little | The single largest remaining research gap in the whole Reference Layer |

### 1.3 Workflow/state/error/recovery gaps

Summarized from the Pass D closure report, not re-derived: Availability→Sell and Pricing (the two domains material to the frozen slice) are PARTIALLY_COVERED with named open questions; Post-ticketing, Queue, and Seat/SSR remain the weakest domains overall.

### 1.4 Professional work-readiness gaps

Cross-referencing Pass F's market evidence against the coverage table above: queue monitoring (job-posting-confirmed as a daily duty) and fare-rules literacy (job-posting-confirmed as an expectation) are both **already covered** technically (A2/D21 and B4 respectively) — the market evidence and the technical coverage line up well for these two. Voiding remains a real risk: it is explicitly named in Saudi job postings ("issue, reissue, void, and refund") but remains technically unverified in this project. **This is the clearest case of a market-confirmed, technically-unconfirmed gap in the entire analysis** and should be prioritized accordingly.

### 1.5 General vs. Cryptic-specific vs. carrier-specific vs. market-context — explicit separation

- **General Amadeus / Cryptic-confirmed:** availability, sell, PNR core, pricing, ticketing, TTL, refund, EMD, PNR history.
- **Interface-uncertain (Amadeus-general or NDC, not confirmed Cryptic):** D19 (post-ticketing schedule-change behavior).
- **Carrier-specific evidence used only as such, never generalized:** the Finnair/Cathay Pacific OPW-OPC-vs-ADTK sourcing (used to establish the Amadeus/non-Amadeus split, not as universal carrier policy); the British Airways NDC release notes (D19, explicitly bounded to that airline's NDC configuration).
- **Market context, never blended into technical claims:** all Pass F findings.
- **Historical/legacy, explicitly quarantined:** the 2000 and 2002-dated sources (Pass G above).

### 1.6 Unresolved knowledge

D2, D3, D4, D6, D10, D15, D18, D19, D21, B2, B3, B5 — the full carry-forward list, unchanged in substance from the Pass D closure report, reproduced here only as an index (full detail lives in the research log).

### 1.7 The smallest defensible professional scope — recommendation, not yet a decision

Applying constitution §55's standard (minimum sufficient coverage for genuinely work-ready competence, including prerequisites/workflow/error/recovery, not merely command count): the **core** — availability, sell, PNR construction/modification/history, pricing, ticketing/TST, TTL, refund, EMD, and queues — is reasonably defensible today, with named limitations. **Voiding and Seat/SSR workflow detail are the two areas where the current evidence base would not yet support confident professional training content**, and are recommended as the highest-priority items for any further research investment, ranked above the pricing-family command variants (FXX/FXY/etc.), which are lower-impact scope questions rather than core-competence gaps.

---

## DELIVERABLE 2 — RECOMMENDED KNOWLEDGE ARCHITECTURE

A proposed ownership structure ensuring every important knowledge type has exactly one authoritative home, consistent with the constitution's own §47 source-of-truth discipline (the same principle that governed the constitution's own revision earlier this project).

| Layer | Owns | Current authoritative artifact | Status |
|---|---|---|---|
| **Commands** | Identity, syntax, dispatch behavior as *implemented* | `05_AeroBridge_Canonical_Amadeus_Engine_Reference.md` (37 commands, code-verified) | CANONICAL for implementation truth only |
| **Behaviors (domain truth)** | What real Amadeus actually does, independent of AeroBridge's implementation | **Does not yet exist as a dedicated artifact** — currently distributed across the research log's per-finding fields | GAP — see Build Plan §3.2 |
| **Workflows** | Sequence/prerequisite/state relationships between commands | Research log (D-series) plus this document's §1.3 synthesis | WORKING, not yet consolidated into its own artifact |
| **States** | PNR/segment/pricing/ticketing state model | Partially in the engine reference (implementation), partially in D-series findings (domain) — **not yet reconciled into one state model** | GAP |
| **Errors** | Taxonomy + exact text where evidenced | Engine reference (34-message taxonomy, implementation) + D1/D14/D19 (domain, partial) | Two sources, correctly kept separate per the implementation-vs-domain distinction, not yet cross-indexed |
| **Curriculum** | What is taught, in what order, Basic vs. Advanced | This document's §1.1/1.2, sourced from the (internal-only) starting syllabus and official Amadeus course structures | WORKING — the learner-facing curriculum itself has not been authored, only its evidence base |
| **Carrier Context** | What's carrier-specific vs. general | This document's §1.5 | Thin — Pass E proper has not run (EG-1-blocked) |
| **Market Context** | Employability/job-readiness evidence | Pass F findings, explicitly firewalled from technical claims | Sufficient for its declared light-touch purpose |
| **Evidence / Sources** | Provenance, source type, authority per claim | Embedded per-finding in the research log (§9A fields) | WORKING — no separate evidence registry exists yet; each finding carries its own |
| **Observations** | Directly-observed (not merely documented) behavior | **None recorded this project** — every finding to date is DOCUMENTED, not OBSERVED, since no live Amadeus terminal access has been used | Explicit gap, worth naming: this Reference Layer has no `OBSERVED_BEHAVIOR`-tagged entries at all |
| **Design Decisions** | AeroBridge-specific simulation choices | Scattered — D18 (direct-sell) is the clearest named instance; the engine reference's own "documented design constraints" (e.g. `XE` scope, one-seat-per-PNR) are others | Recommend consolidating into a single `AeroBridge Design Decisions Register`, currently implicit rather than explicit |
| **Uncertainty** | What's UNKNOWN and why | Distributed per-finding | WORKING, consistent with the constitution's own explicit-UNKNOWN discipline |
| **Currentness** | Source date, verification date, currentness status | Distributed per-finding; consolidated once, this session, in Pass G above | WORKING |

**Single recommendation flowing from this table:** the **Behaviors (domain truth)** and **States** layers are the two genuine architectural gaps — everything else has at least a working home, even if not yet a dedicated file. Creating two new files for these now would violate the "do not create files merely to increase count" instruction while the underlying evidence is still this thin; the recommendation is to let them mature inside the research log until Pass C/E unblock and there is enough material to justify dedicated ownership, per the Build Plan below.

---

## DELIVERABLE 3 — KNOWLEDGE BUILD PLAN

**Authoritative layers and dependency order** (extends the dependency map already established in the Session Handoff, not restated in full):

```
Amadeus domain evidence (Passes A/B/D/F, this session's synthesis)
   ↓
Phase 1 implementation-truth reconciliation (Pass C — BLOCKED on EG-2)
   ↓
Carrier-context separation (Pass E — BLOCKED on EG-1)
   ↓
Currentness confirmation (Pass G — targeted sweep done; full sweep pending)
   ↓
Adversarial validation (Pass H — targeted pass done; full review pending broader Pass A/B/E maturity)
   ↓
Domain/SME validation execution (Decision 7 — not this project's to perform)
   ↓
Curriculum authoring (explicitly out of scope for this Reference Layer)
   ↓
Learning Design / Learning Experience Architecture integration (separate artifacts, per the roadmap)
   ↓
Engineering consumption
```

**Validation checkpoints:** each finding promoted beyond PARTIALLY_VERIFIED requires either (a) a second independent, ideally official, source, or (b) explicit product-owner acceptance of a single strong source for a specific, named claim — consistent with how B4/D12/D14 already reached SUFFICIENTLY_COVERED status.

**Promotion gates:** no finding may be presented as learner-facing authoritative content until it passes the Final Learner-Safety Check (below) — this is a gate this document itself applies, not merely recommends.

**Engineering-consumption boundary:** nothing in this Reference Layer authorizes engine changes. Where a finding (D21 specifically) bears on already-implemented behavior, it is routed to Decision 7's validation process, not directly to engineering.

**Maintenance / change control:** when EG-1 or EG-2 are eventually supplied, this document's §1 (Gap Analysis) and the research log's Phase-1-reconciliation-flagged items should be revisited together, in one pass, rather than piecemeal — both depend on the same two missing artifacts and re-litigating them separately risks drift.

**No additional files created beyond what this task requires** — this document consolidates all five deliverables in one artifact rather than five, consistent with §20's own instruction not to inflate document count.

---

## DELIVERABLE 4 — PRIORITIZED RESEARCH BACKLOG

Prioritized by **learner risk × operational importance × evidence gap**, per the governing instruction. HIGH/HIGH/HIGH items lead.

| ID | Exact question | Status | Evidence available | Evidence gap | Learner risk | Operational importance | Currentness concern | Next action | Owner/pass | Blocking? |
|---|---|---|---|---|---|---|---|---|---|---|
| EG-1 | What does the actual EgyptAir Basic+Advanced curriculum document establish? | OPEN | None — only the starting-syllabus summary | Total — the source itself is missing | N/A directly, but gates B5 and Pass E | HIGH (gates curriculum-completeness confidence) | N/A | Product owner supplies the document | Pass E / B5 | YES, for those specifically |
| EG-2 | What do the four Phase 1 artifacts actually contain? | OPEN | None | Total | N/A directly, but gates Pass C | HIGH (gates all command-identity reconciliation) | N/A | Product owner supplies the artifacts | Pass C | YES, for that specifically |
| Voiding (A4/D3) | What is the real Amadeus voiding command/precondition/exact response? | OPEN, UNVERIFIED | Weak/indirect only | Large | **HIGH — job-market-confirmed as a real duty, technically unconfirmed** | HIGH | Unknown | Targeted official-source search | Pass A resumption | NO, but highest-priority non-blocking item |
| Seat/SSR workflow (Domain 7) | Prerequisites, sequencing, validation, persistence for SSR/seat entries | LARGELY UNRESEARCHED | Module-level only, one syntax fragment | Large | MEDIUM-HIGH | HIGH (named curriculum topic) | Unknown | Dedicated session, ideally with access to Amadeus's own `HE SR`-style help content if ever available | Pass D resumption / Pass B | NO |
| D21 | Real function of `QE`/`QN`/`QD` vs. AeroBridge's implementation | Substantially clarified, unresolved | Two converging domain-truth sources vs. implementation truth | Medium (framing gap, not evidence gap) | MEDIUM (affects an already-shipped command family) | MEDIUM | Low | Route to Decision 7 validation | Pass C / Decision 7 | NO for research; YES for eventual engine-reference confidence |
| D6 | FXX identity | CONFLICT_UNRESOLVED | Two non-official sources vs. prior project correction | Medium | LOW (not in frozen slice) | MEDIUM | Medium | Official-source check when convenient | Pass C | NO |
| D4 | Exact Cryptic mandatory-element count | UNKNOWN | "5" cited three times, never enumerated | Medium | LOW-MEDIUM | MEDIUM | Low | One targeted search for the actual enumerated list | Pass A resumption | NO |
| D18 | Does real Amadeus support "direct sell" for `SS`? | UNKNOWN | Only negative evidence (no confirming example found) | Medium | LOW (affects Terminal fidelity, not safety) | MEDIUM | Low | Targeted official-source search, or accept as design decision | Pass A resumption / design review | NO |
| D19 | Does the HK→TK/`VERIFY ITINERARY` finding apply to Cryptic? | UNKNOWN (NDC-confirmed only) | One airline-specific NDC source | Large (wrong interface) | LOW currently (post-ticketing outside frozen slice) | Rises to HIGH once post-ticketing becomes in-scope | Low | Cryptic-specific search when Post-ticketing becomes material | Pass D resumption | NO |
| B2/B3 | Split/Claim PNR; Waitlist/Passive/Ghost/Open/ARNK | UNVERIFIED | 1–2 non-official sources | Medium | LOW-MEDIUM | MEDIUM | Low | Seek a second/official source | Pass B resumption | NO |
| D10/D15/D20 | FXY/FXL/TQT/TTE/FQF/FXG scope | Existence candidates only | Mixed, mostly weak-moderate | Medium | LOW | LOW-MEDIUM (scope question, not safety) | Medium (2014–2015 sources) | Scope decision more than research | Pass B / product owner | NO |
| Observations layer | Zero `OBSERVED_BEHAVIOR`-tagged findings exist project-wide | Structural gap | N/A | Total (no live-terminal access used at any point) | N/A | Affects overall evidence-strength ceiling | N/A | Would require actual Amadeus terminal access — outside this project's current tools | Future, if/when available | NO |

---

## DELIVERABLE 5 — ACCEPTANCE CRITERIA

Promotion gates, by target use:

### 5.1 Canonical knowledge (entering a `0X_Canonical_*`-equivalent status)
Requires: Amadeus identity confirmed · Cryptic applicability confirmed or explicitly scoped otherwise · at least PARTIALLY_VERIFIED status with either a second source or explicit product-owner acceptance · currentness classified (not left CURRENTNESS_UNKNOWN) · provenance traceable to a named source · no unresolved contradiction touching the same claim.

### 5.2 Learner-facing knowledge
All of 5.1, **plus**: workflow position known or explicitly marked UNKNOWN (never omitted silently) · failure/recovery behavior evidenced or explicitly labeled unverified · Basic/Advanced placement evidenced from curriculum comparison, not inferred from complexity · scope (core vs. extension vs. out-of-scope) explicitly assigned · **no item currently flagged UNVERIFIED, CONFLICT_UNRESOLVED, or NEEDS_EXTERNAL_CONFIRMATION may be presented as settled** — this bars D6, D18 (as fact rather than design-question), D19 (as Cryptic fact), D21 (as either side "winning"), B2, B3, B5, and the voiding gap from learner-facing promotion today.

### 5.3 Engineering-consumable knowledge
All of 5.1, plus explicit separation from AeroBridge's own existing implementation truth — a finding may inform an engineering discussion (as D21 now does) without being treated as an instruction to change code. No finding in this Reference Layer is engineering-ready by itself; all require the Decision 7 validation step first, per the project's own standing rule that AI-generated research must never move directly to implementation.

### 5.4 Scenario/assessment knowledge
All of 5.2, plus: the finding must be load-bearing to a specific, named scenario or assessment item (per the Scenario Differentiation Contract already governing the product corpus) — not merely generically true.

### 5.5 Current knowledge specifically
CURRENT or DATED/PLAUSIBLY_APPLICABLE only; HISTORICAL material may never be promoted to any of the above without independent current re-confirmation, regardless of how well-documented the historical claim is.

**Standing rule, restated because it is the single most important sentence in this deliverable:** high-impact learner-facing knowledge must not be promoted while critical evidence gaps remain. By this criterion alone, **B5, D6, D18 (as fact), D19 (as Cryptic fact), D21 (as either resolved direction), voiding, and Seat/SSR workflow detail are all currently barred from learner-facing promotion** — this is not a defect in the research, it is the acceptance-criteria system working as designed.

---

## CROSS-DOCUMENT CONSISTENCY AUDIT

Compared: the research log, the Pass D closure report, this document, and (for boundary-checking only, not re-litigation) the constitution and the product-governance corpus's Decision 8A.

| Check | Result |
|---|---|
| Contradictory claims across documents | None found. D6 and D21 are internally consistent — held open the same way in every document that mentions them |
| Duplicate authority | None — this document explicitly defers to the research log and closure report as the evidentiary base rather than re-asserting findings independently |
| Hidden assumptions | One surfaced and corrected during drafting: an earlier internal draft of §1.7 nearly implied voiding was "probably fine to teach informally" — removed; it is correctly barred under §5.2 |
| Historical leakage | None — Pass G's classifications are respected throughout; the 2000/2002 sources appear only in the Pass G table itself, never as support for a current claim |
| API/NDC leakage | None — D19 is consistently caveated everywhere it appears (research log, closure report, this document) |
| Cross-GDS contamination | None — no Travelport/Sabre/Galileo-sourced claim appears anywhere in this document as Amadeus fact; the Travelport comparison table (D21) is cited only as evidence *about* Amadeus's column, never as GDS-general behavior |
| Inconsistent Basic/Advanced classification | None found, but this is partly because so few items have a confirmed Cryptic-curriculum-sourced placement — most remain SHARED_UNCLEAR, which is itself consistent (not contradictory) across documents |
| Unsupported commands/workflows/prerequisites/state transitions/error text | None promoted — every UNKNOWN remains UNKNOWN in this document exactly as in its source |
| Missing negative knowledge | None — D2/D3's negative-knowledge status, and the new "zero OBSERVED_BEHAVIOR entries" structural finding, are both carried through |
| Missing provenance | None found in material claims |
| Carrier-specific leakage | None — the EgyptAir-internal-only boundary is respected throughout this document; no learner-facing "EgyptAir" framing appears |
| Market-to-technical leakage | None — Pass F findings are never cited as technical support anywhere above |
| Learner-facing exposure of internal source identities | Not applicable yet — no learner-facing content has been authored; this document itself is an internal artifact |

**No deliverable silently contradicts another.**

---

## FINAL LEARNER-SAFETY CHECK

Applied to the four findings closest to learner-facing promotion (B4 Mini Rules, D1 TTL, D12 Refund, D14 EMD precondition) as a representative sample, since running all thirteen questions against every one of forty-plus findings would not add decision value beyond what the acceptance criteria (§5) already establish structurally:

| # | Question | B4 (Mini Rules) | D1 (TTL) | D12 (Refund) | D14 (EMD) |
|---|---|---|---|---|---|
| 1 | Definitely about Amadeus? | YES | YES | YES | YES |
| 2 | Interface known? | Yes — product-level, Cryptic explicitly listed among supported interfaces | YES, Cryptic (OPW/OPC) | YES, Cryptic (`TRF` family) | Partial — EMD-A precondition sourced from an operational guide without explicit interface confirmation |
| 3 | Technical behavior supported? | YES | YES | YES | YES |
| 4 | Context known? | YES | YES | YES | YES |
| 5 | Prerequisites known? | Partial | YES | Partial (Category 33 edge cases open) | YES — this is the finding's whole point |
| 6 | Workflow position known? | Partial | YES | YES | YES |
| 7 | Failure conditions known? | UNKNOWN | UNKNOWN | UNKNOWN (exact text) | **YES — the one finding with exact evidenced failure text** |
| 8 | Currentness established? | YES (CURRENT) | YES (CURRENT) | YES (CURRENT) | Partial — source not independently dated |
| 9 | Provenance traceable? | YES | YES | YES | YES |
| 10 | Inferences labeled? | YES | YES | YES | YES |
| 11 | Observations contextualized? | N/A — none of these are OBSERVED_BEHAVIOR type | | | |
| 12 | AeroBridge-specific behavior separated? | YES | YES | YES | YES |
| 13 | Could incorrect teaching cause a real mistake? | Moderate — a learner who doesn't know fare rules exist could misquote a fare | **High — this is exactly why D1 is flagged as a genuine, currently-missing gap** | Moderate | **High if the precondition were taught backwards** — correctly captured, not backwards |

**None of the four sample findings fails a critical question outright**, which is consistent with them being the strongest four in the log — but all four (like every other finding) remain below the bar for canonical status per §5.1 until a second source or explicit product-owner acceptance closes the remaining partial answers. **No item in this Reference Layer is being represented as unquestioned Amadeus truth.**

---

## FINAL READINESS DECISION

**Updated at the Evidence/State Confirmation Gate, following Pass C's completion.** The verdict below is re-affirmed, not mechanically carried over — see the updated reasoning immediately following, then the original reasoning preserved as historical context.

## **NOT_READY** (unchanged verdict; substantially changed reasoning)

**What changed since this verdict was first issued:** Pass C is now COMPLETE_WITH_DOCUMENTED_LIMITATIONS (was: entirely blocked, 0%). D6 (FXX) is RESOLVED. D18 (direct-sell) is RESOLVED. B2 (Split/Claim PNR) is RESOLVED. B5 ("Amadeus Offers") is SUBSTANTIALLY RESOLVED pending product-owner acknowledgment. D21 is no longer an unresolved conflict — it is a confirmed domain-truth finding, escalated for an implementation-side decision. Of the original three reasons below, reason 1 is fully resolved and reason 3 is substantially resolved (FXX) or reframed as a bounded, non-blocking escalation (D21) rather than a live conflict.

**Why the verdict does not flip to READY or READY_WITH_DOCUMENTED_LIMITATIONS despite this:** **reason 2 stands entirely unchanged and is sufficient on its own.** Pass E remains a whole pass at zero progress for its defining purpose — EG-1, the actual EgyptAir curriculum document, has still never been directly supplied to any session (Phase 1's registry cites it; this project has not itself inspected it). This project's own original reasoning explicitly held that "two whole passes at zero progress is a different situation from 'some bounded limitations remain'" — with Pass C now resolved, that reasoning applies with full force to Pass E alone, which is reason enough by itself.

**Original three-reason justification, preserved as historical context — reasons 1 and 3 no longer reflect current state, reason 2 does:**

This verdict applies to the full declared scope — **AeroBridge Professional Amadeus Basic + Advanced**, both tiers, as a complete Reference Layer. It is not a judgment that the work done is weak; a great deal of it (B4, D1, D12, D14 especially) is genuinely strong. The verdict is driven by three specific, material, currently-unresolvable-by-more-research facts:

1. ~~**Pass C is entirely blocked (0%).**~~ **RESOLVED — see the update above.** No command-identity reconciliation against the frozen Phase 1 baseline has been possible at all. Every "new" command candidate surfaced this project (`RH`, `SR`'s full scope, `TRF` family, `FXI`/`FXQ`/`FXY`/`FXG`/`FXX`, the `QE`/`QN`/`QD` question) remains unreconciled against that baseline. This is not a small residual gap — it is a structurally complete pass with zero progress possible until EG-2 is supplied.
2. **Pass E is entirely blocked for its defining purpose. — STILL TRUE, now the sole standing reason.** The carrier-context separation exercise cannot meaningfully run without the actual curriculum source (EG-1), and B5 — a real, product-architecture-relevant open question about whether "Amadeus Offers" implies content outside the frozen Cryptic boundary — stays open as a direct consequence. *(Update: B5 is now substantially resolved via Phase 1's own citation of the curriculum list — but this is Phase 1's citation, not this project's own direct inspection, so Pass E's own defining purpose — this project independently separating carrier-specific from general content — still cannot run.)*
3. ~~**Two live, named technical conflicts remain genuinely unresolved**~~ **(D6, D21) — D6 RESOLVED; D21 reframed as a bounded, non-blocking escalation, not a live conflict.** one of which (D21) now touches already-implemented AeroBridge behavior, not merely prospective content.

None of these three can be closed by further web research — they require the product owner to supply specific, named artifacts (EG-1, EG-2) or make a specific decision (B5's resolution path, or how urgently D6/D21 need engineering-side attention). *(Update: EG-2 has since been supplied and used. EG-1 has not.)* Declaring READY or even READY_WITH_DOCUMENTED_LIMITATIONS would understate this: two whole passes at zero progress is a different situation from "some bounded limitations remain," and the acceptance criteria in Deliverable 5 already correctly bar the affected items from promotion — so a more positive top-line verdict would contradict the very gates this document just set. *(This reasoning now applies to Pass E alone, which is sufficient by itself to sustain NOT_READY.)*

**What IS defensible, stated precisely so the NOT_READY verdict is not mistaken for "nothing works":** the evidence gathered for the domains material to the currently-frozen implementation slice (`AN→SS→FQD→FXP`) — availability, sell, pricing fundamentals, PNR construction — is mature enough to responsibly inform continued work on that slice specifically, with the named open questions (D18's direct-sell status, now itself resolved) tracked rather than ignored. **If a narrower question were asked — "is the evidence sufficient to keep building the already-authorized frozen slice" — the answer would be closer to READY_WITH_DOCUMENTED_LIMITATIONS**, and is now closer still given Pass C's resolution. That is a different, narrower question than the one this deliverable set was actually asked to answer, which is the full Basic+Advanced Reference Layer's readiness — and this document answers the question it was actually given, not the easier adjacent one.

---

## MANDATORY FINAL CHECKPOINT

1. **What did we finish?** A targeted Seat/SSR research attempt (limited yield, honestly reported); a full Pass G currentness sweep; a full Pass H adversarial review; all five required deliverables; a cross-document consistency audit; a final learner-safety check on a representative sample; a final readiness verdict. *(Since updated: Pass C completed; see the Pass C Reconciliation Report and the update above.)*
2. **What remains unresolved?** EG-1 (still not supplied — structural, blocking Pass E specifically, and B5's full independent confirmation); D19, voiding, Seat/SSR workflow detail (the two highest-priority genuine content gaps, per the backlog's own risk × importance × gap ranking); D21 (escalated, non-blocking). *(EG-2, D6, D18, B2 are resolved. B5 is substantially resolved.)*
3. **What evidence was collected?** No new primary evidence this session beyond the one limited Seat/SSR search — this session's work was synthesis, currentness classification, and adversarial review of the existing four-session evidence base, which is what the task actually called for at this stage.
4. **What conflicts were discovered?** None new at the time of original writing. *(Since updated: Pass C found zero genuine conflicts between this project's research and Phase 1 — the prior D6/D21 items were resolved or reframed, not confirmed as conflicts.)*
5. **What must happen before the next stage?** *(Updated)* EG-1 must be supplied before Pass E or B5's full independent confirmation can proceed. Absent that, the highest-value next research action is the voiding gap (backlog-ranked highest for learner risk × operational importance). A product-owner decision is needed on how the D21 (queue) finding should be handled relative to the already-shipped engine code — independent of EG-1.
6. **Are we allowed to proceed?** **Allowed to continue research and planning work — yes.** Allowed to treat the Amadeus Reference Layer as closed/ready for the next roadmap stage (Sonnet self-review across the full Knowledge + Learning Foundation, then Opus review) — **not yet, per the NOT_READY verdict above.** This is a scope-specific answer, not a blanket stop: nothing here prevents continued work on Pass A/B/D/F/G/H refinement, or on the frozen slice specifically, while EG-1/EG-2 remain outstanding.
