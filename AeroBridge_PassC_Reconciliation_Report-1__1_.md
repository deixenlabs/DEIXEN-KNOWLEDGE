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


# AeroBridge — Pass C Reconciliation Report

Controlled Reconciliation: Reference Layer Research vs. the Frozen Phase 1 Baseline

**Inputs actually inspected this session** (per the required input-verification rule): `aerobridge-final-canonical-registry.json` (88 records, 29 families), `aerobridge-command-audit.json` (42 audit entries across 6 dispositions), `aerobridge-out-of-scope-modules.json` (18 Hotel/Car extension records), `aerobridge-final-registry-lock-report.md`, cross-referenced against the existing `AeroBridge_Amadeus_Gap_Analysis_Research_Log.md` and `AeroBridge_PassD_Final_Closure_Report.md` (both already fully available from this session's own prior work, not re-uploaded). No "pasted content.txt" file was found among the uploads — noted for completeness, not treated as a missing required input, since none of the actual required inputs named in the governing prompt depend on it.

---

## A. EXECUTIVE RESULT

**Pass C status: substantially reconciled, not blocked.** This is a major change from every prior session, all of which reported Pass C as entirely blocked (EG-2). With the four artifacts now supplied, the reconciliation surface has been built from the artifacts themselves (per the governing instruction), not merely from the pre-listed candidates — though the pre-listed candidates are all covered within it.

**Reconciliation coverage:** all 88 canonical/scoped records were scanned; all 42 audit entries were inspected; the full out-of-scope module list was inspected. Every material Reference Layer finding with a plausible Phase 1 relationship (D4, D6, D18, D19, D21, B2, B3, B5, plus the FX-family and queue-family research) was checked against the actual artifacts, not assumed.

**Major agreements:** the large majority of this session's well-evidenced findings are independently confirmed by Phase 1, often via entirely different source lineages — this is a strong, convergent result, not a coincidence of citing the same sources twice. See §C.

**Major conflicts:** one genuine, unresolved technical question remains open after reconciliation (D19 — not addressed by Phase 1's scope at all, so reconciliation cannot close it). No conflict between this session's findings and Phase 1 survived scrutiny as a *true* contradiction — see §E for the one borderline case (FXG) and why it is classified as a difference, not a conflict.

**Major blockers:** none remain for Pass C's own reconciliation scope. B3 (waitlist/passive/ghost/open/ARNK) remains unverified — but this is now a *convergent* negative finding (this session and Phase 1 both failed to substantiate it), not a blocker.

**Is the Phase 1 baseline usable as a baseline?** Yes, and more than usable — the artifacts demonstrate real methodological rigor (explicit source-quality grading, an already-discovered SEO/mirror-site contamination network, a self-corrected scope decision on FQC, an explicitly documented single-source labeling error on ET/ER) that this session's own research independently corroborates rather than contradicts.

**Escalation required:** **yes, for one item — D21 (queue command family) — see §H.** This is an implementation-impacting discrepancy, not a resolvable-by-more-research question, and per the governing escalation rule it is paused for a decision, not resolved here.

---

## SPECIAL NOTICE — A FINDING BEARING DIRECTLY ON B5

This report was not asked to resolve B5, and does not declare it resolved unilaterally. But the reconciliation surface-building exercise (§5 of the governing prompt: build the complete surface from the artifacts themselves, not from a preselected list) surfaced something that bears directly on it, and the standing instruction across this entire project has been: *"Once the actual EgyptAir curriculum source is available, use it to determine whether 'Offers' refers to Cryptic training, NDC/Offer & Order, or another scoped meaning."* This may be exactly that moment, and it would be a disservice to bury it in a reconciliation-matrix row.

**What the registry states, verbatim in substance:** the Phase 1 registry contains a full "Amadeus Offers" family — `OFS` (create an air offer), `RTOF` (retrieve/display an offer), `TQQ`, `OFN`, `OFV`, `OFK` — sourced from an official Amadeus quick-card document (`amadeus-offers.pdf`). The registry's own scope note for this family states its inclusion is justified because **the user's own stated 25-topic curriculum list explicitly names "Amadeus Offers."** The registry's top-level metadata separately states its overall scope was "confirmed via `training.egyptair.com/crm/Catalog/9200`" (course AM-AG-20 and its companion Advanced course).

**What this does and does not establish, precisely:**
- It establishes, with strong evidence (an official Amadeus command-reference document), that a real, current, **Cryptic** "Amadeus Offers" command family exists — `OFS`/`RTOF`/`TQQ`/`OFN`/`OFV`/`OFK` — entirely distinct from NDC/Offer & Order Management.
- It establishes that Phase 1's own research treated this Cryptic family as the correct referent for the curriculum's "Amadeus Offers" line item, and did so by citing the actual topic list, not by inference from the command name alone.
- **It does not constitute this session independently re-inspecting the EgyptAir curriculum document itself** — the underlying "25-topic list" and the `training.egyptair.com` catalog page are cited by Phase 1, not re-verified firsthand in this Pass C session. This is Phase 1's own evidentiary claim, being reported accurately, not re-authenticated from scratch.

**Disposition:** B5 moves from `CONFLICT_UNRESOLVED / ESCALATED` to **`SUBSTANTIALLY RESOLVED — CRYPTIC (OFS family), sourced from Phase 1's citation of the curriculum topic list.`** This is not the same confidence level as this session independently holding the curriculum document — it is reported as strong, specific, Phase-1-sourced resolution evidence, with its exact provenance stated so the product owner can judge it accurately rather than receiving a bare "resolved." **This is the single most important outcome of this Pass C session and is not something Pass C alone has the authority to make canonical** — per the governing instruction, this is recorded and routed for decision, not silently promoted. See the Research Log update in the Carry-Forward Register (§I) and the Required Next Stage in the final block.

---

## B. RECONCILIATION MATRIX

| Candidate / Finding | Phase 1 Record(s) | Reference Layer Finding | Reconciliation Outcome | Evidence / Provenance | Currentness | Scope Effect | Required Action | Impact |
|---|---|---|---|---|---|---|---|---|
| FXX (D6) | CANONICAL, family "Itinerary Pricing" — price without storing a TST | Two non-official sources, same function description, in tension with prior curriculum "historical correction" | **MATCHED — resolves the conflict in favor of this session's finding** | Phase 1: TAP Portugal training manual + Tourism School Guide (E5). This session: two independent non-official sources | Not flagged stale by Phase 1 | None — confirms an existing candidate as real | Update the curriculum documentation's "historical correction" — it appears to be the actual error | HIGH |
| RH (D5) | CANONICAL, "PNR History" family: `RH`, `RHA`, `RHG`, `RHS[#]`, `RH/ALL` | Official amadeus.com blog: `RH`, `RHA`, `RHN,J,R`, `RHM`, `RHFA` | **MATCHED_WITH_DIFFERENCE** — base command and purpose agree; specific sub-codes only partially overlap (`RHA` in both; others differ) | Phase 1: Tourism School Guide. This session: amadeus.com/de (official) | Both current | None | Treat both sub-code lists as partial; neither is complete alone — combine as candidate detail, not as a contradiction | MEDIUM |
| QE / QN / QD (D21) | CANONICAL: QE = "Place PNR on a queue"; QN = "Remove current item from queue, display next"; QD = "Delay/requeue current item, display next" | This session (official amadeus.com blog + Travelport comparison table): same functions | **MATCHED — and both diverge from AeroBridge's existing engine-reference documentation**, which describes `QE`/`QD` as "exit queue mode" and `QN` as "next within browse" | Phase 1 explicitly audited this exact tension already (see audit `excluded[]` entry on slash-notation) and reached the same functional conclusion independently | Current | **Implementation-impacting — see §H** | Escalate; do not modify code from this report | HIGH |
| SR (Seat/SSR, Domain 7) | CANONICAL: `SR CTCM [airline] HK1 [#]`, `SR CTCE-[airline] HK1/[encoded]` | This session: `SR CTCE-BA HK1/[data]` (GitHub-sourced example) | **MATCHED, exactly** | Independent source lineages converging on identical syntax | Current | None | None — already well-confirmed | MEDIUM |
| SS "direct sell" (D18) | CANONICAL: `SS[#][class][line]` (from-display) **and** `SS[airline][flight][class][date][route][status][seats]`, explicitly noted as a "long sell... as opposed to selling directly from an AN availability line" | This session found only from-display examples; explicitly logged "direct sell" as UNCONFIRMED, candidate `AEROBRIDGE_DESIGN_DECISION` | **RESOLVED — Phase 1 confirms both modes are real Amadeus behavior.** AeroBridge's existing engine-reference description ("sell from a displayed line, OR direct sell") was accurate all along | Phase 1 registry (E5-tier per lock report methodology) | Current | None | Update D18 in the Research Log from "unresolved design-decision question" to "confirmed Amadeus fact" | HIGH |
| TKTL / TKXL | CANONICAL, variants of base `TK` (`TKOK` strongest-evidenced; TKTL/TKXL on one non-primary source, kept as variants not separate records) | Not independently researched this session by name | **MATCHED / extends existing knowledge** — no new information from this session, but no conflict either | Phase 1 only | — | None | None | LOW |
| TTP_EXCH | CANONICAL, SCOPED — ARC-agents-only variant of `TTP`; BSP equivalent is plain `TTP` | Not independently researched this session by name | **MATCHED / extends existing knowledge** | Phase 1 only | — | Confirms a market/office-context scope boundary (ARC vs. BSP) | None | LOW |
| FXE / FXO / FXI | CANONICAL, SCOPED to Best-Pricer/ATC context. FXI = involuntary reissue pricing (airline-initiated schedule change/disruption) | D13 (FXI — full workflow, official-source-adjacent, 2013–2014-dated) | **MATCHED** — Phase 1's FXI function description matches this session's D13 finding precisely | Phase 1: independent sourcing. This session: official amadeus.com PDF | Phase 1 doesn't flag currentness concern; this session flagged D13 as dated | None | None — D13's currentness caveat stands independently | MEDIUM |
| TRF | CANONICAL — `TRF[ticket#]`, `TRF/L[#]`, `TRF.../FULL`, `TRF.../ATC` | D12 — `TRF`+ticket+`/ATC`, `TRF/L[line]/ATC`, `TRF/I-[#]/ATC`, plus follow-ups `TRFU`/`TRFP`/`TRFIG` | **MATCHED_WITH_EXTENSION** — base command confirmed by both; this session's follow-up entries (`TRFU`/`TRFP`/`TRFIG`) and the query-report form (`/I-`) are not in the Phase 1 record as extracted | Phase 1 + this session, independent lineages | Both current | This session's research **extends** the Phase 1 baseline | Recommend Phase 1 registry note the TRFU/TRFP/TRFIG follow-ups as a candidate addition (see §F) | MEDIUM |
| FXQ | CANONICAL — voluntary reissue | D20 — matches exactly | **MATCHED** | Phase 1: servicehub.amadeus.com + official ATC guide. This session: official campaign page | Current | None | None | MEDIUM |
| FXY | CANONICAL — upsell, `FXY1` follow-up | D10 — matches exactly | **MATCHED**, and Phase 1's sourcing (two official quick cards, 2015/2017) is stronger than this session's (2014–2015 product sheets) | Phase 1 sourcing supersedes this session's for currentness confidence | Phase 1's 2017 source is more current than this session's 2014–2015 sources | None | Prefer Phase 1's sourcing going forward | LOW |
| FXG | CANONICAL — **"Price a chargeable/paid seat... follow-up after `ST`"** | D15 — logged as "automatic pricing and TSM-P (EMD mask) creation for chargeable SSR-based ancillary services," single non-official source | **MATCHED_WITH_DIFFERENCE, not a conflict — see §D** | Phase 1: presumably a focused, higher-confidence source (seat-specific). This session: a broader EMD operational guide | Phase 1 not flagged stale | Narrows D15's scope | Adopt Phase 1's more specific (seat-focused) scope; retain this session's broader claim only as an unconfirmed possibility | MEDIUM |
| Split PNR (B2) | CANONICAL, `SP[p#]` / `SP[p1],[p2],[element].0/.1` — evidence strength **E5**, three convergent sources | UNVERIFIED, single non-official source | **RESOLVED — Phase 1 confirms with the strongest evidence tier in the whole registry** | Phase 1: servicehub.amadeus.com (2 articles) + Tourism School Guide + Complete Amadeus Manual | Current | None | Update B2 (split component) from UNVERIFIED to CANONICAL | HIGH |
| Claim PNR (B2) | Audit entry: `RO` — "Claim a PNR created in another office/by an airline," sourced from amadeus.com's official "PNR Claim" product page | UNVERIFIED, single non-official source | **RESOLVED** | Phase 1 official source | Current | None | Update B2 (claim component) accordingly | HIGH |
| Waitlist / Passive / Ghost / Open segments (B3) | **Not present anywhere in the canonical registry or the audit file** | UNVERIFIED / NEEDS_EXTERNAL_CONFIRMATION, single non-official source, investigated across three sessions | **CONVERGENT NEGATIVE FINDING** — neither this project's own web research nor Phase 1's dedicated registry effort substantiated these | Absence checked directly in both files (see verification commands in this session's own working notes) | — | None — properly stays out of Core | Keep B3 exactly as UNVERIFIED; the convergence *strengthens* confidence that this is a genuine gap, not a research-effort gap | MEDIUM |
| "Amadeus Offers" (B5) | CANONICAL family, `OFS`/`RTOF`/`TQQ`/`OFN`/`OFV`/`OFK`, explicitly tied to the actual 25-topic curriculum list per Phase 1's own notes | CONFLICT_UNRESOLVED / ESCALATED — general-industry evidence pointed to NDC | **SUBSTANTIALLY RESOLVED — see the Special Notice above** | Phase 1: official `amadeus-offers.pdf` quick card + curriculum-list citation | Current | **Major — see the Special Notice** | Route to product-owner confirmation before full canonical promotion | **CRITICAL** |
| Post-ticketing HK→TK / `VERIFY ITINERARY` (D19) | **Not present in the canonical registry, audit file, or out-of-scope file** | PARTIALLY_VERIFIED, NDC/British-Airways-specific source only | **NOT ADDRESSED BY PHASE 1 — reconciliation cannot close this** | Neither source | D19 unresolved | None | Stays exactly as logged; Pass C simply has nothing to compare it against | LOW (not frozen-slice-material) |
| Mandatory element count (D4) | `NM`, `AP`/`APE`/`APM`, `TK`, `RF` all CANONICAL, individually confirmed; no single record states "exactly 5" | UNKNOWN exact count, "5" cited three times without enumeration | **PARTIALLY_MATCHED** — the *components* are now all confirmed; the *exact count/list* is still not stated anywhere as a single enumerated "5" | Phase 1 confirms 4 distinct element types (Name, 3 contact sub-types, Ticketing, Received From) — arguably 4 or 5 depending on how contact sub-types are counted | Current | None | Treat as effectively resolved at the component level; the "exactly 5" phrasing itself may simply be counting Name+Phone+Ticketing+RF+Itinerary, which is plausible but not confirmed by a single source | MEDIUM |


---

## C. CONFIRMED AGREEMENTS

Genuine agreement, not mere co-mention: FXX's identity and function; RH's base identity; QE/QN/QD's real functions (agreeing with each other while both diverging from AeroBridge's existing documentation, itself a form of agreement between this session and Phase 1); SR's exact syntax; SS's direct-sell mode; FXQ, FXY, FXI's identities and functions; Split PNR (`SP`) and Claim PNR (`RO`); the core PNR-element commands (`NM`, `AP`/`APE`/`APM`, `TK`, `RF`, `ET`/`ER`, `RT`, `IG`, `XE`) — all independently corroborate AeroBridge's own existing (code-verified) engine reference with no discrepancy found. The **methodological convergence** is itself worth naming as an agreement: Phase 1 independently identified and excluded the exact same SEO/mirror-site contamination network (mambu.com, curvyyoga.com, chyronhego.com, studyabroadfoundation.org) that this session's own D18 research treated with explicit caution — two independent efforts reached the same skepticism about the same bad sources.

---

## D. DIFFERENCES WITHOUT GENUINE CONFLICT

- **RH sub-codes (D5):** Phase 1 (`RHA`/`RHG`/`RHS[#]`/`RH/ALL`) and this session (`RHA`/`RHN,J,R`/`RHM`/`RHFA`) list *partially different* sub-code sets. This is a **coverage difference**, not a contradiction — both sets share `RHA` and neither claims the other's codes don't exist. Two partial lists from different sources naturally don't fully overlap; combining them is additive, not reconciliatory-in-the-conflict sense.
- **FXG scope (D15 vs. Phase 1):** Phase 1 scopes `FXG` specifically to seat pricing (follow-up after `ST`); this session's source described it more broadly as chargeable-ancillary/EMD pricing generally. This is a **scope-precision difference** — a seat is one category of chargeable ancillary, so the two descriptions are not mutually exclusive, but Phase 1's is more specific and better-sourced. Classified as a difference to note, not a conflict to escalate.
- **TRF follow-up entries (D12 vs. Phase 1):** this session's research is more granular (includes `TRFU`/`TRFP`/`TRFIG`) than the Phase 1 record as extracted. This is **this session extending the baseline**, not disagreeing with it.
- **QD's exact wording** ("delay/requeue current, show next" per Phase 1 vs. this session's "redisplay: requeue current, show next" per the amadeus.com blog): these are the same underlying function described in slightly different words by two people summarizing the same source family — **terminology difference, not a conflict.**
- **ET/ER labeling (Phase 1's own internal note, surfaced here for completeness):** Phase 1 itself already identified and correctly dismissed a single source that swapped ET/ER's meanings — this is not a difference between this session and Phase 1, but worth noting as evidence of the baseline's own internal quality control.

---

## E. GENUINE CONFLICTS

**None found that survive scrutiny as true contradictions between this session's findings and the Phase 1 baseline.** This is a notable result in itself — after four Pass D sessions producing more than twenty findings, and a fresh comparison against 88 canonical/scoped records plus 42 audit entries, zero genuine head-on contradictions emerged. The closest candidates (FXG's scope, RH's sub-codes) were examined above and classified as differences, not conflicts, with reasoning shown per the governing instruction not to hide behind a generic "conflict" label.

**D6 (FXX) is explicitly not counted as a conflict between this session and Phase 1** — the two agree with each other; the conflict, now resolved in favor of both, was between this session+Phase 1 jointly on one side and the prior canonical curriculum documentation's "historical correction" on the other. See §F for how this is routed.

**The one item this report treats with conflict-level seriousness is procedural, not evidentiary: D21.** It is not a disagreement between this session and Phase 1 (they agree). It is a disagreement between the *converged domain-truth finding* (this session + Phase 1, independently) and *AeroBridge's own existing engine-reference documentation*. This is escalated in §H, not listed here, because it is implementation-impacting rather than a research-evidence conflict.

---

## F. LEGITIMATE CANDIDATE ADDITIONS

**Sufficiently supported, recommend for consideration:**
- The `TRFU`/`TRFP`/`TRFIG` refund follow-up entries and the `TRF/I-[#]/ATC` query-report form (extends the existing `TRF` record with this session's D12 detail).
- Reconsidering the canonical curriculum documentation's "historical correction" regarding FXX, given now-quadruple-sourced evidence (2 this session + 2 Phase 1) that it is real and distinct from FXP.

**Scope-dependent, requires a product-owner scope call, not an automatic add:**
- Whether `FXL`/`TQT`/`TTE`/`FQF` (D10, weakly single-sourced this session, not found in the Phase 1 registry at all) merit further investigation, given the much stronger FXY/FXQ/FXI/FXG results from the same general research direction.

**Decision-dependent — the single most consequential item in this whole report:**
- **The `OFS`/`RTOF`/`TQQ`/`OFN`/`OFV`/`OFK` "Amadeus Offers" family and its bearing on B5.** Already CANONICAL in Phase 1 — this is not actually a "candidate addition" to Phase 1 (it's already there), but it is a candidate resolution for B5, and that resolution requires product-owner acknowledgment before this project's other documents (the research log, and eventually any learner-facing material) stop treating B5 as open. See the Special Notice.

**Insufficiently supported, not recommended:** nothing new from this session meets even a candidate-addition bar beyond what's listed above — the FXL/TQT/TTE/FQF group is the only remaining unresolved candidate cluster, and it is explicitly marked scope-dependent rather than promoted.

---

## G. OUT-OF-SCOPE / REJECTED / DUPLICATE FINDINGS

- **Hotel/Car `OFS/Hx`, `OFS/Cx` variants:** confirmed real (per the out-of-scope-modules artifact) but correctly excluded from the air-scoped Core registry and from this project's frozen-slice-relevant work. Negative knowledge preserved: these exist, they are simply out of AeroBridge's current declared scope, not disproven.
- **`TKT` (claimed "check ticket status") and `FT` (claimed "retrieve fare details"):** Phase 1's audit found NO_EVIDENCE_OF_EXISTENCE for both, tracing the claims to the same SEO/mirror-site contamination network this session independently treated with caution. **This session's own D18 research cited one page from that same network** (`partnernews.mambu.com`) for lower-stakes corroboration (`AN`/`SS`/`NM`/`AP`/`TK`/`TTP` naming) — those specific citations were never promoted to findings on that source alone and remain fine, but the network itself should now be treated as actively untrustworthy for any future research, not merely "low-moderate authority." Recorded here as negative knowledge with real teeth, not a routine footnote.
- **Waitlist/Passive/Ghost/Open segments (B3):** see §B/§C — convergent negative finding, correctly not promoted by either this session or Phase 1.

---

## H. IMPLEMENTATION-IMPACTING DISCREPANCIES

**`QE` / `QN` / `QD` (D21) — the one item this report escalates rather than resolves.**

1. **What the Phase 1 baseline states:** `QE` = place a PNR on a queue; `QN` = remove the current item from a queue being browsed, show next; `QD` = delay/requeue the current item, show next.
2. **What the Reference Layer states (this session, independently, before Phase 1 was available):** the same three functions, via an official amadeus.com blog post and an independent Travelport-hosted cross-GDS comparison table.
3. **What external evidence states:** two independent lineages (Phase 1's own sourcing, and this session's two sources) now converge on the same functional description.
4. **Whether an AeroBridge implementation behavior is implicated:** **yes.** AeroBridge's own `05_AeroBridge_Canonical_Amadeus_Engine_Reference.md` — itself verified against actual supplied code — describes `QE`/`QD` as "exit queue mode / delete PNR from queue" and `QN` as "next within an active browse session." This is a different functional description than what both Phase 1 and this session's domain-truth research now converge on.
5. **Whether the discrepancy is domain truth, implementation truth, scope, or a combination:** **domain truth (now well-converged) appears to differ from the engine reference document's functional description.** This could mean the underlying AeroBridge code behaves differently than its own documentation claims, or that the documentation was written imprecisely relative to what the code actually does, or (least likely, given the convergence) that all the external sources are wrong. **This report does not decide between these possibilities** — that requires either re-inspecting the actual AeroBridge source code (not available in this session) or a deliberate product/engineering decision.

**No code was modified. No implementation behavior was changed. This is recorded and routed, per the escalation rule, not resolved.**


---

## I. CARRY-FORWARD REGISTER

| ID | Exact question | Status | Why unresolved | Evidence available | Evidence still needed | Impact | Blocking? | Owner/stage | Next valid action |
|---|---|---|---|---|---|---|---|---|---|
| B5 | Does "Amadeus Offers" resolve to the `OFS` Cryptic family? | SUBSTANTIALLY RESOLVED, pending product-owner acknowledgment | Resolution is Phase-1-sourced, not independently re-verified against the raw curriculum document by this session | Strong — official quick card + Phase 1's curriculum-list citation | Product-owner confirmation; ideally, eventual direct sight of the actual curriculum list | CRITICAL | NO longer blocking further research; still awaiting formal acknowledgment before full canonical promotion | Product owner | Acknowledge or request the underlying curriculum list directly |
| D21 | Do `QE`/`QN`/`QD` need an engine-reference (or code) correction? | ESCALATED, unresolved | Requires either code re-inspection or a product/engineering decision, not more research | Strong convergent domain-truth evidence | Actual AeroBridge source code re-inspection | HIGH | YES, for engine-reference accuracy specifically; NO for continued Amadeus research | Engineering / Decision 7 | Re-inspect the actual queue-handling code when next available |
| D19 | Does the HK→TK / `VERIFY ITINERARY` finding apply to Cryptic? | UNRESOLVED, unchanged | Phase 1 doesn't address post-ticketing schedule-change behavior at all | One NDC/airline-specific source only | A Cryptic-specific source | LOW (outside frozen slice) | NO | Future Pass D resumption | Targeted search when Post-ticketing becomes material |
| Voiding (A4/D3) | Real Amadeus void command/precondition/response? | UNVERIFIED, unchanged | Not addressed in the Phase 1 registry, audit, or out-of-scope file at all | Weak, non-official only | An official source | HIGH (job-market-confirmed duty, still technically unconfirmed) | NO | Future Pass A resumption | Highest-priority remaining research item — unaffected by this Pass C session, still open |
| FXL/TQT/TTE/FQF | Are these real, in-scope commands? | Existence candidates, unchanged | Single weak source; absent from Phase 1 entirely | Weak | A second source, or explicit scope exclusion | LOW-MEDIUM | NO | Product owner (scope call) | Decide whether further investigation is worth it given the much stronger sibling results (FXY/FXQ/FXG) |
| Seat/SSR workflow detail (Domain 7, beyond `SR`'s base syntax) | Prerequisites, sequencing, validation for the full SSR/seat workflow | LARGELY UNRESEARCHED, unchanged | Phase 1's `SR` record confirms syntax but not workflow-level detail (prerequisites, timing, persistence) | Base syntax only | Dedicated workflow research | MEDIUM-HIGH | NO | Future Pass D resumption | Still the single largest research gap in the project |
| D4 | Exact enumerated Cryptic mandatory-element list | Effectively resolved at component level, exact "5" enumeration still not single-sourced | No Phase 1 record states "these exact 5" as one list | Strong at the component level (4 distinct element types confirmed) | A single source explicitly enumerating 5 | LOW | NO | — | Treat as low-priority; components are well-confirmed regardless of the exact count phrasing |

---

## J. PHASE C CHECKPOINT — MANDATORY SIX ANSWERS

1. **What did we finish?** Full inspection of all four supplied Phase 1 artifacts; a complete reconciliation surface built from the artifacts themselves (not only the pre-listed candidates); resolution or substantial clarification of six previously-open items (FXX/D6, direct-sell/D18, Split-Claim/B2, and — pending acknowledgment — B5); one item escalated for a non-research decision (D21); one previously-untrustworthy source network independently confirmed as untrustworthy by a second, unrelated effort.
2. **What remains unresolved?** D19 (Phase 1 doesn't cover it), voiding (Phase 1 doesn't cover it either), Seat/SSR workflow depth (Phase 1 confirms syntax only), FXL/TQT/TTE/FQF (scope-dependent), D4's exact "5" enumeration (low-priority), D21 (escalated, not research-resolvable).
3. **What evidence was collected?** No new external web research this session — the evidence is the four supplied Phase 1 artifacts themselves, inspected directly and compared claim-by-claim against the existing research log and closure report.
4. **What conflicts were discovered?** None between this session and Phase 1 that survive scrutiny (§E). One conflict *resolved* by their joint agreement (FXX vs. the prior curriculum "historical correction"). One item *escalated* rather than resolved because it's implementation-impacting (D21).
5. **What must happen before the next stage?** Product-owner acknowledgment of the B5 resolution; a decision on how to handle D21 relative to the shipped engine code; the Research Log should be updated to reflect this session's resolutions (see the actual changes made, listed below) — done, not merely recommended, within this session.
6. **Are we allowed to proceed?** **Yes.** Nothing found here blocks any other pass. Several long-standing blockers (B2, most of B5) are now closed or substantially closed.

---

## K. PASS C VERDICT

## **COMPLETE_WITH_DOCUMENTED_LIMITATIONS**

The actual Phase 1 artifacts were inspected in full, and the material reconciliation surface (built from the artifacts, not merely the prompt's examples) was reconciled to a genuinely strong degree — the large majority of this session's prior open items are now resolved, substantially resolved, or convergently strengthened as genuine negative findings. It is not "COMPLETE" without qualification because three items remain bounded but explicitly non-blocking limitations: D19 and voiding are simply outside what the Phase 1 artifacts cover (Pass C cannot reconcile against material that was never in scope for Phase 1 either), and D21 requires a decision this report has no authority to make. None of the three prevents safe progression to other work.

---

## RESEARCH LOG CHANGES ACTUALLY MADE THIS SESSION

(Reported per §20 of the governing prompt — described here, applied directly to `AeroBridge_Amadeus_Gap_Analysis_Research_Log.md` in this same session, not merely proposed.)

- **D6 (FXX):** status changed from `CONFLICT_UNRESOLVED` to `RESOLVED — FXX confirmed real`, with the Phase 1 sourcing added alongside the original two sources.
- **D18 (direct-sell):** status changed from `UNKNOWN / candidate design decision` to `CONFIRMED — both display-sell and long/direct-sell are real Amadeus behavior`, per Phase 1's explicit `SS[airline][flight]...` record.
- **D21 (QE/QN/QD):** updated from "substantially clarified, two-source" to "**independently confirmed by Phase 1 — now escalated as an implementation-impacting discrepancy** requiring engineering/Decision-7 attention, not further research."
- **B2 (Split/Claim PNR):** status changed from `UNVERIFIED` to `RESOLVED — CANONICAL (Split, via Phase 1's SP record, evidence strength E5) and RESOLVED (Claim, via Phase 1's RO audit record)`.
- **B5 ("Amadeus Offers"):** annotated (not silently closed) with the Special Notice content in full, and re-labeled `SUBSTANTIALLY RESOLVED — CRYPTIC, PENDING PRODUCT-OWNER ACKNOWLEDGMENT`, explicitly distinguished from a routine resolution given its history.
- **Top status header:** updated to point to this Pass C report as the authoritative record of these changes.

---

## FINAL RESPONSE FORMAT

**Pass C:** COMPLETE_WITH_DOCUMENTED_LIMITATIONS

**What was reconciled:** the complete Reference Layer research surface (Passes A/B/D findings) against all 88 Phase 1 canonical/scoped records, 42 audit entries, and 18 out-of-scope extension records.

**What was resolved:** D6 (FXX), D18 (direct-sell), B2 (Split/Claim PNR) — fully. B5 ("Amadeus Offers") — substantially, pending acknowledgment; this is the single most significant outcome of this session.

**What remains unresolved:** D19 (post-ticketing/interface applicability — Phase 1 doesn't cover it), voiding (same), Seat/SSR workflow depth beyond base syntax, FXL/TQT/TTE/FQF (scope-dependent), D4's exact-count enumeration (low-priority).

**Critical conflicts:** none between this session and Phase 1. One prior conflict (D6) resolved by their agreement.

**Implementation-impacting issues:** D21 — `QE`/`QN`/`QD`'s real functions, now confirmed by two independent lineages, appear to differ from AeroBridge's existing engine-reference documentation. Escalated for engineering/Decision-7 review; not modified here.

**Required next stage:** product-owner acknowledgment of the B5 resolution; a decision on D21's handling; otherwise, the remaining backlog (voiding, Seat/SSR) is unaffected by this pass and remains available for future research sessions.

**Overall Reference Layer readiness:** **still NOT_READY**, stated separately and deliberately not upgraded merely because Pass C succeeded. Pass C answers a narrower question than overall readiness. What changes the overall picture: Pass C is no longer a 0%-blocked pass (a major structural improvement), and B5 — previously the project's most stubborn open escalation — is now substantially resolved. But Pass E's carrier-context work still has not run as its own pass (EG-1, the raw curriculum document itself, has still not been directly supplied to this session — only cited by Phase 1), voiding and Seat/SSR remain genuine content gaps, and D21 is a new, real, unresolved engineering-relevant question. The overall verdict from the prior Final Deliverables document is not mechanically reissued here — a proper re-issuance should follow the product-owner's response to B5 and D21, since both materially affect the honest answer.
