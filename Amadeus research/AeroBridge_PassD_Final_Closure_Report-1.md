# AeroBridge — Pass D Final Closure Report

Amadeus Reference Layer — Workflow / State / Error / Recovery Gap Analysis

This report reconstructs the full Pass D history (four sessions, logged in `AeroBridge_Amadeus_Gap_Analysis_Research_Log.md`), applies the materiality gate to every remaining open item rather than researching everything further, performs one targeted piece of closure-specific research (the D21 queue-command conflict, explicitly called out as warranting continued attention), and issues a verdict. Per the governing instruction, this is not a request to eliminate every open question — it is a request for the strongest closure the evidence actually supports.

---

## A. FINAL VERDICT

## **CLOSED WITH BOUNDED CARRY-FORWARD**

Pass D's material objective — identify workflow/state/error/recovery gaps, verify what can be verified, explicitly bound what cannot, surface genuine conflicts, and determine whether the project may safely proceed — has been achieved. This is not a forced closure: reasoning for it is given in full below, including an explicit account of why the domains that remain PARTIALLY_COVERED do not block safe progression, and one substantial escalation (the queue-command family discrepancy) that is preserved, not resolved.

**The reasoning turns on one distinction that this closure pass is making explicit for the first time: materiality relative to the currently frozen implementation slice versus materiality relative to the full eventual Basic + Advanced curriculum.** The product-governance corpus's Decision 8A freezes the current buildable scope to four commands — `AN → SS → FQD → FXP`. Of Pass D's seven priority domains, only **Availability→Sell** (covers AN/SS) and **Pricing** (covers FQD/FXP) are material to that frozen scope. Both have real, evidence-backed findings with clearly bounded open questions. The other five domains — Post-ticketing, Refund, EMD/Ancillary, Queue, Seat/SSR — are all outside the frozen slice; they matter to the *eventual* full curriculum (all are named in the original starting syllabus) but do not gate whether the currently-authorized implementation work can proceed, and Decision 8A itself already defers "full-scale curriculum authoring across all command families" from the current boundary. This report applies both lenses explicitly rather than silently picking one — see Section C and D.

---

## B. PASS D MATERIAL FINDINGS

| Issue | Claim | Evidence Status | Materiality | Final Disposition | Blocking? |
|---|---|---|---|---|---|
| D1 | TTL/auto-cancellation; Amadeus-specific OPW/OPC vs. non-Amadeus ADTK | PARTIALLY_VERIFIED, CURRENT | Material to Pricing/Ticketing generally | Carry forward as a genuine curriculum-content finding | NO |
| D4 | Cryptic mandatory-element count (5 named, 3 different sources cite "5"; not enumerated) | UNVERIFIED (exact list) | Material to PNR construction (in frozen-slice-adjacent territory, since PNR completion underlies SS/FQD) | Cryptic exact count = UNKNOWN; carry forward | NO |
| D6 | FXX — real distinct command vs. prior project "historical correction" | CONFLICT_UNRESOLVED | Material to the broader FX-family, NOT to the frozen slice's `FXP`/`FXB` specifically (those remain independently confirmed) | Preserve conflict; escalate to Phase 1 reconciliation | NO |
| D18 | `SS` sell-from-display-line mechanism confirmed; "direct sell" (AeroBridge's own implemented mode) not confirmed in real Amadeus by any source found | PARTIALLY_VERIFIED (line-sell); UNESTABLISHED (direct-sell) | **Material to the frozen slice directly — `SS` is one of the four frozen commands** | See Section C — this is the one frozen-slice-relevant open question | NO, but flagged for design-decision review |
| D19 | HK→TK segment-status shift, `VERIFY ITINERARY` error | PARTIALLY_VERIFIED, NDC/airline-specific source only | Material to future Post-ticketing content, NOT frozen-slice-material (post-ticketing is outside `AN/SS/FQD/FXP`) | Carry forward, explicitly NDC-sourced, not Cryptic-confirmed | NO |
| D21 | Queue command family (`QE`/`QN`/`QD`/`QI`) — divergence between AeroBridge's own documented implementation and real Amadeus | **Substantially clarified this session — see below** | Material to the *engine reference's* accuracy (already-implemented AeroBridge behavior), NOT frozen-slice-material (queue commands are outside `AN/SS/FQD/FXP`) | **Escalate to engine-reference/Phase 1 reconciliation explicitly** | NO for Pass D/frozen slice; YES for whoever next touches the queue engine code or the Phase 1 registry |
| B2/B3 | Split/Claim PNR; Waitlist/Passive/Ghost/Open/ARNK segments | UNVERIFIED/NEEDS_EXTERNAL_CONFIRMATION | Advanced-tier, not frozen-slice-material | Carry forward unchanged | NO |
| B5 | "Amadeus Offers" | CONFLICT_UNRESOLVED, ESCALATED | Already on its own escalation track (EG-1-dependent) | Unchanged — held exactly as instructed | NO (already correctly non-blocking, per standing instruction) |

### D21 — resolved from "possible conflict" to "substantially clarified, multi-command divergence" (this session's one piece of targeted research)

Two new, better-authority sources were found:

1. **An official amadeus.com blog post (`amadeus.com/de/blog`, "How to display and process queues")** describing the real workflow: `QT` (display active queues) → `QS[queue]C[category]` (start processing) → then either `QD` (**redisplay: requeue current, show next**), `QN` (**remove current from queue, show next**), or `QI` (**ignore changes and leave the queue**).
2. **A Travelport-hosted cross-GDS format-comparison table**, whose Amadeus-specific column independently states: "Place PNR on queue" = `QE[number]`, and "Queue remove" = `QN`.

**Comparing this to AeroBridge's own already-code-verified engine reference** (`QT`/`QC`/`QS` — queue table/count/start browsing; `QN`/`QI` — next/ignore within active browse; `QE`/`QD` — exit queue mode/delete PNR from queue): the *existence* of `QT`/`QS`/`QN`/`QI`/`QE`/`QD` as a command family is consistent across both, but **the specific function assigned to `QN`, `QD`, and especially `QE` appears to differ** — the new sources describe `QE` as *placing* a PNR onto a queue (an entry action) and `QN` as *removing* the current PNR from the queue being browsed, where AeroBridge's documentation describes `QE` as *exiting* browse mode and `QN` as *advancing* to the next item.

**This is not resolved here.** Per the governing instruction, a finding that could bear on already-implemented AeroBridge command semantics is escalated, not silently corrected. It is also not treated as proof that AeroBridge's engine is "wrong" — the existing engine reference was verified against AeroBridge's *own supplied code*, which is a legitimate, different kind of truth (implementation truth) from what these two new sources describe (real-Amadeus domain truth); the two were never claimed to be identical, and Decision 7's domain/SME validation dependency exists precisely to check implementation truth against domain truth before anything is taught as authoritative. **This finding is exactly what that dependency should examine for the queue command family specifically.**

---

## C. VERIFIED / SUFFICIENTLY SUPPORTED RESULTS

**Amadeus fact, frozen-slice-relevant:**
- `SS` sells from a numbered line of a prior display (`SS1Y3` pattern) — PARTIALLY_VERIFIED, moderate-authority source.
- `FXP`/`FXB` pricing commands remain independently confirmed (unaffected by the D6/FXX conflict, which concerns a different, additional command).
- The `TRF`/`FXQ`/`FXI` reissue/refund family, Category 31/33 guarantee split — SUFFICIENTLY_COVERED, official sources.
- EMD-S/EMD-A distinction and the `MISSING OR INVALID ISSUED IN CONNECTION WITH` precondition — SUFFICIENTLY_COVERED.

**Amadeus Cryptic fact, contextual limitation attached:**
- PNR mandatory elements (Name/AP/TK/RF pattern, "5" cited but not enumerated) — real, but incomplete.
- Official "Reservations in Amadeus" course sequence (Availability → PNR → Itinerary/Invoice → Pricing → Ticketing → Queues) — real, module-level, not command-level.

**Currentness limitation, explicitly flagged, not blended in as current:**
- D13 (`FXI`), D1's GTL/ATL presentation — 2013–2014-sourced; several sources touched this session (the 2000 and 2002-dated Scribd documents) were used only for very stable foundational syntax and explicitly excluded from any claim needing recent confirmation.

**AeroBridge design decision, newly and explicitly separated out (not previously stated this precisely):**
- **AeroBridge's "direct sell" support for `SS`** should be treated as `AEROBRIDGE_DESIGN_DECISION` pending confirmation, not asserted as `AMADEUS_FACT` — no source found across four sessions confirms a freestanding direct-sell mode in real Amadeus; every real usage example found sells from a displayed line. This does not mean AeroBridge is wrong to support it (simulators reasonably make interaction-convenience choices), but it should not be represented to a learner as confirmed real-Amadeus behavior without further evidence.

---

## D. REMAINING UNKNOWN / CONFLICTED

| Question | Evidence available | Why unresolved | Epistemic status | Blocking? | Required future evidence/decision | Owning phase |
|---|---|---|---|---|---|---|
| Does real Amadeus support `SS` without a prior availability display? | Consistent "sell from line" examples only; no direct-sell example found | No source directly addresses the negative case | UNKNOWN | NO for Pass D closure; relevant to Terminal fidelity | A direct Amadeus technical source addressing standalone sell syntax | Future Pass D resumption, or design review of the existing "direct sell" feature |
| Exact failure text for an invalid `SS` line reference | None | Not found in any source this project has used | UNKNOWN (`Exact Amadeus Response = UNKNOWN`) | NO | A source showing the actual rejection | Future Pass D resumption |
| Does the `VERIFY ITINERARY` / HK→TK finding (D19) apply to Cryptic? | NDC/BA-specific release notes only | Wrong interface confirmed by source itself | UNKNOWN for Cryptic; PARTIALLY_VERIFIED for NDC | NO (post-ticketing is outside the frozen slice) | A Cryptic-specific source | Future Pass D resumption, when Post-ticketing becomes material |
| Real function of `QE`/`QN`/`QD` in Cryptic | Two new sources (official blog + cross-GDS table), converging with each other, diverging from AeroBridge's own documentation | Implementation truth vs. domain truth not yet reconciled | PARTIALLY_VERIFIED (domain) / CONFLICTING with implementation truth | NO for Pass D/frozen slice; **YES for the queue command family's eventual accuracy** | Domain/SME validation (Decision 7) specifically for the queue family; Phase 1 artifacts, once supplied | Engine reference maintenance / Phase 1 reconciliation (Pass C) |
| FXX identity (D6) | Two non-official but mutually consistent sources vs. prior project documentation | Neither side officially sourced | CONFLICT_UNRESOLVED | NO (not frozen-slice-material) | An official Amadeus source, either direction | Phase 1 reconciliation (Pass C) |
| B2/B3 command identities | Single-to-two non-official sources | Not independently corroborated by an official source | UNVERIFIED/NEEDS_EXTERNAL_CONFIRMATION | NO | A second, ideally official, source | Future Pass B resumption |
| B5 "Amadeus Offers" | Strong general-industry evidence (NDC), zero EgyptAir-curriculum-specific evidence | EG-1 not supplied | CONFLICT_UNRESOLVED, ESCALATED | NO (already on its own track) | EG-1 (actual EgyptAir curriculum document) | Held, per standing instruction |
| Seat/SSR workflow detail (Domain 7) | Module-level confirmation only (A1, D16); no command-level workflow research performed | Never directly targeted across four sessions | Largely UNRESEARCHED | NO (outside frozen slice) | Dedicated research if/when Domain 7 becomes material | Future Pass D resumption or Pass B/E expansion |

---

## E. NEGATIVE FINDINGS

- **ADTK is actively disconfirmed as an Amadeus element** — two independent sources (an airline trade notice, an airline FAQ) state it is the *non*-Amadeus GDS format. This is a positive exclusion, not merely an absence of evidence, and should be treated with corresponding confidence (do not teach ADTK as Amadeus under any framing).
- **Ghost/passive segment codes (GK/GL/GN/PK) — investigated across three sessions, never reached even a second independent source.** Explicitly historical-only-attempt, not evidence of nonexistence.
- **Direct-sell mode for `SS` — investigated across four sessions specifically, never found supporting evidence.** Not proof it doesn't exist in real Amadeus; proof that this project's available research tools did not surface it. Treated as a negative finding, not a disproof.
- **XI/XD as `XE` siblings — single, weak, SDK-inferred source only, not pursued further.** Correctly deprioritized per the materiality gate (AeroBridge's own `XE` behavior is already code-verified and unaffected).
- **NDC/API evidence was repeatedly found adjacent to genuine Cryptic questions this pass (D19, and the GitHub SDK material from earlier sessions) and was consistently excluded from Cryptic conclusions rather than blended in.** This is itself worth recording as evidence the discipline is holding across an extended, multi-session research effort, not just a first-session intention.

---

## F. CONFLICTS AND ESCALATIONS

**1. D6 — FXX.** Conflicting claims: (a) AeroBridge's canonical curriculum documentation states a "historical correction" that pricing commands are `FXP`/`FXB`, not "FXX"; (b) two non-official, mutually-consistent sources this session describe `FXX` as a real, distinct, currently-taught command (price without saving vs. `FXP`'s price-and-save). Source identity: neither side is officially Amadeus-sourced. Context may explain the difference (possible historical deprecation either direction) but cannot be determined from available evidence. **Not resolved. Escalation required: Phase 1 reconciliation (Pass C), or a direct official-source check, before any FX-family curriculum content beyond `FXP`/`FXB` is authored.**

**2. D21 — Queue command family.** Conflicting claims: AeroBridge's own code-verified engine reference vs. two new, mutually-reinforcing sources (official Amadeus blog + independent cross-GDS comparison table) on the specific functions of `QE`, `QN`, and `QD`. Source identity: AeroBridge's side is implementation truth (verified against actual supplied code); the new sources are domain truth (what real Amadeus does). These are explicitly different kinds of truth per this project's own framework, and a difference between them is not automatically an error on either side — it is exactly the situation Decision 7's domain/SME validation dependency exists to examine. **Not resolved. Escalation required: this specific command family should be an explicit, named item in whatever Domain/SME validation work eventually executes, and should be flagged before the queue commands are taught as authoritative beyond AeroBridge's own simulator context.**

**3. B5 — "Amadeus Offers."** Unchanged from prior sessions. Held per explicit standing instruction. Not re-litigated here.

No other material conflicts were found or reopened this session.

---

## G. RESEARCH LOG CHANGES

The following changes were actually made to `AeroBridge_Amadeus_Gap_Analysis_Research_Log.md` (not merely recommended — see the diff reflected in the delivered file):

- **D21 updated in place**: status upgraded from "single-source, unconfirmed conflict candidate" to "two-source, mutually-reinforcing domain-truth evidence, in explicit tension with AeroBridge's own implementation truth" — with both new sources cited and the implementation-truth-vs-domain-truth framing added.
- **Top status header updated** to reflect this closure report's existence and verdict, and to point to this document as the authoritative closure record rather than duplicating the full reasoning inline in the log.
- **No findings were downgraded.** No prior finding was deleted. This closure pass added interpretive framing (the frozen-slice materiality lens) and one substantially strengthened finding (D21); it did not overturn anything previously recorded.

---

## H. DOWNSTREAM IMPACT

- **Pass C (Coverage Comparison):** gains two new, specific, named reconciliation items (D6, D21) beyond what was already queued (D5, D7, D12–D20). D21 specifically should be treated as higher-priority within Pass C than a generic candidate, given it touches already-implemented engine behavior.
- **Pass E (Airline/EgyptAir Layer):** unaffected by this closure; remains blocked on EG-1 exactly as before.
- **Pass F (Saudi Market):** unaffected.
- **Pass G (Currentness/Legacy Sweep):** inherits an explicit list of dated sources (2000, 2002, 2013–2014) that were used cautiously this session and should be the first candidates when Pass G actually runs.
- **Pass H (Adversarial Completeness Review):** D18's "direct sell" finding and D21's queue-family finding are themselves examples of adversarial findings already surfaced organically during Pass D — Pass H's job is not starting from zero.
- **Knowledge Architecture / future engineering:** **not executed, not begun, and this report does not authorize beginning them.** The one item worth flagging for whoever eventually does touch engine code: D21 means the queue command family should not be assumed correct-as-documented without the Decision 7 validation step, specifically for `QE`/`QN`/`QD`.

---

## I. PROGRESSION DECISION

**ARE WE ALLOWED TO PROCEED? YES, WITH BOUNDED CARRY-FORWARD.**

The frozen implementation slice's two directly-material domains (Availability→Sell, Pricing) have real, if imperfect, evidentiary support, with the one meaningful open question (direct-sell mode) explicitly named and correctly classified as a design-decision question rather than a blocking technical unknown. The five domains outside the frozen slice remain genuinely open at varying depths, but none of them gates anything currently authorized to proceed — they are exactly the kind of explicitly-bounded, non-blocking carry-forward this closure standard is built to accommodate. The one substantial new finding this session (D21) is a real escalation, correctly preserved rather than resolved, and does not block Pass D's own closure because it concerns already-implemented engine behavior outside the frozen slice, not new research this pass needs to complete. B5, EG-1, and EG-2 remain exactly as they were — this closure changes nothing about their status.

---

## REQUIRED SIX-QUESTION CHECKPOINT

1. **What did we finish?** A full reconstruction and materiality-gated review of four Pass D sessions; one targeted piece of new research (D21) that substantially clarified what had been the single most concrete open conflict; an explicit frozen-slice-vs-full-curriculum materiality framework applied for the first time.
2. **What remains unresolved?** D4 (exact count), D6 (FXX), D18 (direct-sell), D19 (interface applicability), D21 (queue semantics, now better-evidenced but still not confirmed against AeroBridge's implementation), B2, B3, B5, EG-1, EG-2 — all named, all bounded, none blocking per the reasoning above.
3. **What evidence was collected?** One official Amadeus blog post (queue workflow) and one independent cross-GDS comparison table (Travelport-hosted, Amadeus column), both converging on a queue-command function set that diverges from AeroBridge's own documentation — see Section B/F for full detail.
4. **What conflicts were discovered?** D21 substantially strengthened from a single-source candidate to a two-source, mutually-reinforcing domain-truth finding, explicitly framed as implementation-truth-vs-domain-truth rather than a simple error. No other new conflicts.
5. **What must happen before the next stage?** Nothing blocks continuing to other passes or to drafting the five required deliverables with explicit limitations noted. D21 and D6 should be prioritized within Pass C once the Phase 1 artifacts are supplied.
6. **Are we allowed to proceed?** **YES, WITH BOUNDED CARRY-FORWARD** — see Section I.
