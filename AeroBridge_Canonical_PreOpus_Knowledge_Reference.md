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


# AeroBridge — Canonical Amadeus Training Knowledge Reference — Pre-Opus Final

**This is the primary controlled knowledge handoff for Claude Opus 5's final adversarial review.** It is not itself the final post-Opus canonical reference — it is what Opus reviews before that reference can exist. Everything in it is drawn from `AeroBridge_Amadeus_Gap_Analysis_Research_Log.md`, `AeroBridge_PassD_Final_Closure_Report.md`, `AeroBridge_PassC_Reconciliation_Report.md`, and `AeroBridge_Evidence_State_Confirmation_Gate_Report.md` — no new broad research was performed to build it; one narrowly targeted evidence check was performed (voiding, per §H-1) because it was named as a priority instructional-safety question this pass was explicitly asked to resolve or bound.

---

## A. SCOPE AND BOUNDARY

- **AeroBridge Amadeus scope:** professional Air Reservations & Ticketing competence, Basic + Advanced, for the Amadeus Cryptic interface specifically.
- **Cryptic-only boundary:** API, NDC/Offer & Order, and other Amadeus interfaces are never treated as Cryptic proof unless interface applicability is explicitly established for that exact claim. Several findings below are explicitly excluded or caveated on this basis (D21's domain-truth sourcing note, D19, and the voiding finding in §H-1).
- **Basic + Advanced target:** the learner-facing identity is **AeroBridge Professional Amadeus Basic + Advanced** — not a carrier-branded curriculum.
- **EgyptAir / Saudi relevance boundary:** EgyptAir material (the starting syllabus, and Phase 1's citation of "the user's own stated 25-topic list") is internal baseline/provenance evidence only, never a learner-facing identity. Saudi-market evidence (Pass F) is employability context, never technical proof. Neither may be silently promoted to Amadeus technical fact.
- **Explicit exclusions:** Hotel/Car `OFS` variants (confirmed real, out of the air-scoped Core registry); NDC/Offer & Order generally (confirmed real, distinct interface); the SEO/mirror-site contamination network (`mambu.com`, `curvyyoga.com`, `chyronhego.com`, `studyabroadfoundation.org`, and — newly confirmed this pass — `secondnaturejournal.com`), which independently fabricated at least four false command claims (`RF`="Refund", `FT`="fare details", `TKT`="check ticket status", `FX` alone="cancel"), all already directly debunked by Phase 1's own audit and now independently re-confirmed by this pass's own fresh search.

---

## B–D. BEHAVIORAL SUFFICIENCY GATE — LOAD-BEARING DOMAINS

Not a completeness check. Each domain is classified using the actual behavioral chain (concept → prerequisite → command/syntax → variants → context → state before/after → workflow position → validation → failure → recovery → curriculum scope → currentness → evidence → confidence), not merely "is a command known."

### Basic / foundational behavior

| Domain | Classification | Evidence-based reason |
|---|---|---|
| Availability (`AN`/`SN`) | **SUFFICIENT WITH EXPLICIT LIMITATION** | Code-verified in AeroBridge's own engine (implementation truth); no dedicated fresh domain-truth research was run against `AN` specifically, though nothing found anywhere contradicts it. The limitation is absence of independent domain re-confirmation, not any contrary evidence. |
| Sell / `SS` | **SUFFICIENT WITH EXPLICIT LIMITATION** | Both from-display (`SS1Y3`) and standalone long-sell forms confirmed via Phase 1 (D18, RESOLVED). Failure/recovery behavior for an invalid sell is not established — `Exact Amadeus Response = UNKNOWN` for that case. |
| PNR construction / mandatory elements | **SUFFICIENT WITH EXPLICIT LIMITATION** | `NM`/`AP`/`APE`/`APM`/`TK`/`RF` all independently confirmed (existing engine reference + Phase 1). The exact enumerated "5 mandatory elements" list (D4) is not pinned to one single source — components are solid, the precise count/list is not. |
| Optional elements (SSR/seat/FF/remarks) | **MATERIAL BLIND SPOT** | `SR CTCM`/`SR CTCE` syntax confirmed at the example level (converging sources). Prerequisites, passenger/segment association mechanics, timing within the PNR-build sequence, and persistence behavior are **not established** — this is the least-evidenced Basic-tier domain in the whole project despite being explicitly load-bearing. A learner could be shown that SSRs exist without being taught when/how they correctly attach. |
| Retrieval / PDR | **SUFFICIENT WITH EXPLICIT LIMITATION** | `RT` code-verified; "retrieve a PNR or a PDR" confirmed as one official lesson; PDR's 4-day auto-deletion rule is single-sourced (D9), not officially confirmed. |
| PNR modification / cancellation | **SUFFICIENT WITH EXPLICIT LIMITATION** | `XE` is code-verified with a fully documented scope boundary (cannot cancel SSR/mobile/email/remarks/OSI/tickets/seat). "Associate/disassociate PNR elements" is confirmed as real official curriculum content (D16) but has **no confirmed syntax** — the same underlying gap as Optional Elements above, not a second independent one. |
| PNR history | **SUFFICIENT FOR TRAINING** | `RH` confirmed via two independent lineages (this project's official source, Phase 1's separate official source), including the genuinely useful ARNK-exclusion negative-knowledge note. |
| Pricing / fare quote | **SUFFICIENT WITH EXPLICIT LIMITATION** | `FQD` code-verified. The specific PNR-condition prerequisites for a successful `FQD`/`FXP` were never directly targeted — only indirectly supported (TTC's itinerary+name precondition, the official course's Itinerary→Pricing sequence). |
| TST concepts and display | **SUFFICIENT WITH EXPLICIT LIMITATION** | A3 (official source) plus D8's precondition (single-sourced). |
| Ticketing | **SUFFICIENT FOR TRAINING** | `TTP` code-verified; the surrounding workflow (display TST → issue) confirmed via the official course sequence. |
| TTL / time-limit workflow | **SUFFICIENT FOR TRAINING** | D1 — one of the two or three best-evidenced findings in the entire project: official product confirmation, the Amadeus-specific `OPW`/`OPC` vs. non-Amadeus `ADTK` distinction independently confirmed by two airline sources. |
| Queues (`QT`/`QC`/`QS`/`QE`/`QN`/`QD`) | **QUARANTINED — see §H-2, the single most important disposition in this document** | `QT`/`QC`/`QS` are reasonably well-supported. `QE`/`QN`/`QD`'s *actual functions*, now confirmed at strong domain-truth confidence by three independent lineages (this project's two sources, Phase 1's own independent audit), **appear to diverge from AeroBridge's own existing, code-verified engine-reference documentation.** Not merely under-evidenced — the currently-documented AeroBridge behavior may itself be teaching the wrong function for three real commands. |
| Basic error interpretation and recovery | **SUFFICIENT WITH EXPLICIT LIMITATION** | The existing 34-message taxonomy (engine reference, code-verified) plus scattered exact-text findings (D1, D14, D19 — the latter interface-caveated). No systematic Basic-tier error/recovery sweep has been performed as its own exercise. |

### Advanced behavior

| Domain | Classification | Evidence-based reason |
|---|---|---|
| Non-homogeneous PNR | **SUFFICIENT FOR TRAINING** | B1, confirmed against the existing syllabus and independently corroborated; naturally bounded by AeroBridge's existing no-child/infant-fare-type limitation. |
| Split / Claim | **SUFFICIENT WITH EXPLICIT LIMITATION** | `SP` confirmed at Phase 1's highest evidence tier (E5, three convergent sources); `RO` (claim) confirmed via an official source. Existence and syntax are strong; workflow-level detail (when a split is operationally appropriate, what happens to each resulting PNR afterward) is not established. |
| Complex PNR modification | **MATERIAL BLIND SPOT** | Same underlying gap as Optional Elements/associate-disassociate above — not a second, independent blind spot. |
| Fare rules / Mini Rules | **SUFFICIENT FOR TRAINING** | B4 — official, live, current source; one of the strongest findings in the project. |
| Advanced pricing families | **SUFFICIENT WITH EXPLICIT LIMITATION** | The well-evidenced core (`FXQ`/`FXY`/`FXG`/`FXI`/`FXE`/`FXO`, all Phase-1-confirmed) is strong. `FXX` is now RESOLVED (four convergent sources). `FXL`/`TQT`/`TTE`/`FQF` remain weak, single-sourced, absent from Phase 1 entirely — **explicitly quarantined as scope-dependent candidates, not taught as confirmed.** A newly-surfaced reference this pass (`HE FXF`, from the same official ATC quick card as `FXI`) is noted as an existence lead only, not investigated further, consistent with the instruction not to expand scope merely because additional features can be found. |
| Reissue (voluntary/involuntary) | **SUFFICIENT FOR TRAINING** | `FXQ` (voluntary) and `FXI` (involuntary) both carry real, distinct, evidenced workflows (D7, D13, D20) — one of the clearest, best-differentiated domains in the whole project. Currentness caveat: sourcing spans 2013–2017; not re-verified as still current this pass. |
| Refund | **SUFFICIENT WITH EXPLICIT LIMITATION** | D12 — strong (the `TRF` family, the Category 33 guarantee rule, the voluntary/involuntary guarantee distinction). Exact failure-response text is the one named gap. |
| EMD / Ancillary | **SUFFICIENT WITH EXPLICIT LIMITATION** | D14 is one of the two findings in the whole project with confirmed exact failure text (`MISSING OR INVALID ISSUED IN CONNECTION WITH`). `FXG`'s scope was corrected from a broad EMD-pricing claim to Phase 1's more specific seat-pricing-follow-up-after-`ST` scope — the correction itself is evidence the domain is being actively verified, not merely accumulated. |
| Queues and queue-state behavior (Advanced) | **QUARANTINED** | Same disposition as the Basic-tier queue entry above — one blind spot, not two. |
| SSR / seat / association workflow | **MATERIAL BLIND SPOT** | Same underlying gap as Optional Elements above. |
| Post-ticketing behavior | **MATERIAL BLIND SPOT, lower priority** | D19's `HK`→`TK` / `VERIFY ITINERARY` finding is real but explicitly NDC/British-Airways-sourced, not Cryptic-confirmed after repeated attempts. Lower-priority because post-ticketing sits outside the currently-frozen `AN→SS→FQD→FXP` implementation slice. |
| Operational recovery (general) | **SUFFICIENT WITH EXPLICIT LIMITATION** | Real recovery evidence exists for the specific areas it was found (TTL/D1, EMD precondition/D14, refund/D12) but no systematic, domain-wide recovery-procedure sweep exists. |
| Voiding | **MATERIAL BLIND SPOT — targeted check performed this pass, still unresolved; see §H-1** | |
| Relevant carrier/market context | **SUFFICIENT WITH EXPLICIT LIMITATION** | Sufficient for its declared light-touch purpose (Pass F); not a substitute for the still-blocked Pass E. |

---

## E. CURRICULUM MAPPING

Basic/Advanced/Shared/Optional/Out-of-scope status for every domain above matches the constitution's §9A.5 taxonomy exactly as recorded in the Research Log — not restated field-by-field here to avoid duplicated authority. Net picture: the large majority of load-bearing Basic content maps cleanly; several Advanced pricing-family candidates (`FXL`/`TQT`/`TTE`/`FQF`) remain explicitly `SHARED_UNCLEAR` pending a scope decision, not a curriculum-placement failure.

## F. EVIDENCE AND PROVENANCE

Every claim in §B–D traces to a named source in the Research Log, the Pass C Reconciliation Report, or §H below — not restated per-item here. The single most consequential provenance fact in the whole project: **the SEO/mirror-site contamination network** (five confirmed domains) independently produced four fabricated command claims, all already excluded. Its recurrence in this pass's own fresh search (a sixth encounter, a fifth domain — `secondnaturejournal.com`) is itself evidence the exclusion is durable and worth keeping active for any future research.

## G. CURRENTNESS

- **CURRENT, live-source-confirmed:** D1 (TTL), D12 (Refund/`TRF`), D5 (PNR history/`RH`), D21's domain-truth sourcing (queue functions), D18 (direct-sell).
- **DATED / PLAUSIBLY APPLICABLE, not re-verified as still current:** D13 (`FXI`, 2013–2014), D20 (`FXQ`), D10 (`FXY`, 2014–2017 range — Phase 1's 2017 source is the freshest available), the ATC reissue-once-if-flown precondition (D7, 2016).
- **HISTORICAL, explicitly excluded from every conclusion above:** the 2000 and 2002-dated sources encountered early in Pass D, never promoted.
- **CURRENTNESS_UNKNOWN:** the voiding business-rule context found this pass (§H-1) — the source itself carries no clear date.

## H. UNCERTAINTY AND QUARANTINE

**This section exists so unresolved knowledge cannot silently enter authoritative learner-facing behavior. Nothing below may be taught, simulated, or engineered against without first clearing the condition stated for it.**

### H-1. Voiding — targeted check performed this pass, still a Material Blind Spot

One narrowly-targeted search was performed this pass specifically because voiding has been named, repeatedly, as the highest learner-risk gap in the project (market-confirmed as a real job duty, never Cryptic-confirmed technically). Result:

- A cross-GDS technical-integration source (structured like API/XML documentation — "TicketVoidRQ"-style naming) states Amadeus's own voiding deadline as **"until the end of the business day (23:59)"**, and that a void transaction requires the 13-digit ticket number, the PNR record locator, and the office's IATA number/pseudo-city code. **This is business-rule context, not confirmed Cryptic syntax, and is explicitly NOT promoted to `AMADEUS_CRYPTIC_FACT`** — the source's own structure indicates an API-interface origin, and per this project's own interface rule that bars promotion without explicit Cryptic applicability.
- The same search independently re-confirmed the SEO/mirror-site contamination network (§A, §F) as the source of the false "`RF`=Refund" / "`TKT`=check ticket status" / "`FT`=fare details" claims — useful confirmation, not new voiding evidence.
- **No Cryptic-specific voiding command or exact response text was found.** Per this project's own stop-condition rule, further searching this pass is not warranted — three separate sessions have now tried and failed to find official Cryptic voiding syntax.
- **Disposition: MATERIAL BLIND SPOT, quarantined from learner-facing promotion.** The business-rule context (deadline, required identifiers) may be used as background orientation only, explicitly labeled as unconfirmed-interface context, never as confirmed Cryptic command behavior.

### H-2. Queue command family (`QE`/`QN`/`QD`) — the highest-severity quarantine in this document

Three independent lineages (this project's session, Phase 1's registry, Phase 1's own prior internal audit) converge on: `QE` = place PNR on queue; `QN` = remove current item, show next; `QD` = delay/requeue current, show next. AeroBridge's own existing, code-verified engine-reference documentation describes different functions for these same three commands. **This must not be taught, simulated, or engineered against in either direction until AeroBridge's actual source code is re-inspected** — not because the domain-truth evidence is weak (it is unusually strong for this project), but because which side of the implementation-truth/domain-truth gap is actually correct in the shipped product is genuinely unknown from anything available to this review.

### H-3. Optional elements / associate-disassociate / SSR-seat association mechanics

Real, official, load-bearing curriculum content (confirmed module existence) with no confirmed command-level workflow syntax. Quarantined from any claim more specific than "these elements exist and are taught as a named topic."

### H-4. `FXL`/`TQT`/`TTE`/`FQF`

Existence candidates only, single non-official source, absent from Phase 1. Quarantined from any curriculum promotion pending a scope decision.

### H-5. Post-ticketing schedule-change behavior (D19)

NDC/airline-specific source only. Quarantined from any Cryptic-facing claim.

### H-6. B5 "Amadeus Offers"

**Not fully quarantined — substantially resolved, but its exact confidence level must travel with it wherever it's used.** Resolved to the Cryptic `OFS`/`RTOF`/`TQQ`/`OFN`/`OFV`/`OFK` family via Phase 1's own citation of the actual curriculum topic list — strong, but Phase-1-sourced rather than this project's own direct inspection of that list. Safe for continued planning use; not yet safe as an unqualified "confirmed" fact in learner-facing copy without the qualifying sentence carried alongside it.

---

## I. FINAL OPUS CHALLENGE REGISTER

The exact items Opus must adversarially attack, in priority order:

1. **Does the QE/QN/QD domain-truth-vs-implementation-truth gap (H-2) indicate AeroBridge's shipped engine has a real behavioral defect, or is the engine-reference documentation merely mis-described relative to correct code?** This cannot be resolved without code access this review does not have — Opus should determine whether this is safe to carry to engineering as-is or needs an intermediate verification step first.
2. **Is B5's resolution (H-6) strong enough to act on, given it rests on Phase 1's citation rather than this project's own inspection of the source curriculum list?**
3. **Does the Optional Elements/SSR-association blind spot (H-3) — arguably the single most under-evidenced *load-bearing* domain in the project — represent an acceptable carry-forward, or does Basic-tier curriculum work need to pause until it's resolved?**
4. **Is the FXX resolution (four convergent sources, none official-Amadeus-direct) strong enough to actually reverse the prior canonical curriculum's documented correction, or does that require a fifth, official-tier source before the documentation itself is changed?**
5. **Given the now-repeatedly-confirmed SEO/mirror-site contamination network, should this project's search methodology add an explicit source-domain denylist rather than relying on per-finding judgment each time?** — a process question, not a domain-truth one, but worth Opus's attention given how many times the same five domains have resurfaced.

---

## UNIFIED CARRY-FORWARD REGISTER

The single authoritative register. Every unresolved or bounded item in the project, in one place, with the exact fields Opus needs — no reconstruction from scattered checkpoints required.

| ID | Current status | Established | Not established | Why it matters | Learner-safety relevance | Engine/implementation relevance | Opus should challenge? | Further research prohibited/unnecessary? | Owner/action | Final disposition target |
|---|---|---|---|---|---|---|---|---|---|---|
| QUEUE-1 (D21) | Domain truth confirmed (3 lineages); implementation-truth unresolved | Real functions of `QE`/`QN`/`QD` per external evidence | Whether AeroBridge's shipped code matches its own documentation or this domain-truth evidence | Could cause a learner to be taught the wrong queue command function, or an engineer to build against the wrong spec | **HIGH** — direct behavioral teaching risk | **HIGH** — already-shipped command family | **YES — top priority** | Yes, research is complete; this needs code access, not more search | Engineering / Decision 7 | Code re-inspection, then reconcile engine reference |
| SSR-1 (Optional elements / associate-disassociate) | Existence confirmed; workflow unestablished | `SR CTCM`/`SR CTCE` syntax; module-level curriculum confirmation | Prerequisites, association mechanics, timing, persistence | Load-bearing Basic+Advanced domain with almost no behavioral depth | MEDIUM-HIGH | LOW currently (not yet built) | YES | No — a genuinely promising further-research target, unlike voiding | Future Pass D/B resumption | Dedicated research session |
| VOID-1 (A4/D3) | UNVERIFIED, one targeted check performed this pass | Business-rule context (deadline, required identifiers), interface-uncertain | Any Cryptic-specific command or exact response | Market-confirmed real job duty, never technically confirmed | **HIGH** | LOW (not built) | YES | **Yes for now** — three sessions have tried; further identical-approach search is unlikely to help per this project's own stop-condition rule | Future research with a different approach/source type, if pursued | A genuinely different research angle, or accept as a standing limitation |
| PRICE-1 (FXX, D6) | RESOLVED (4 sources) | Real, distinct command, price-without-save | Whether the prior canonical curriculum correction has been formally retracted | Directly contradicts existing project documentation | MEDIUM | LOW | YES — verify the resolution holds under adversarial scrutiny | Not further research; a documentation-retraction action | Product owner / curriculum documentation update | Formal retraction of the prior "historical correction" |
| PRICE-2 (FXL/TQT/TTE/FQF) | Existence candidates, unconfirmed | Weak single-source mentions | Official confirmation, scope | Low-moderate — not currently taught | LOW | LOW | Optional | Yes, unless a scope decision reopens it | Product owner (scope call) | Explicit include/exclude decision |
| OFFER-1 (B5) | SUBSTANTIALLY RESOLVED, pending acknowledgment | Cryptic `OFS` family real and current; Phase-1-cited curriculum-list linkage | This project's own direct inspection of the raw curriculum list | The project's longest-standing, highest-stakes escalation | MEDIUM (architecture-adjacent, not immediate teaching risk) | LOW | YES | No — acknowledgment-dependent, not research-dependent | Product owner acknowledgment; ideally, eventual direct sight of the curriculum list | Formal closure once acknowledged |
| POST-1 (D19) | UNRESOLVED, interface-caveated | NDC-sourced HK→TK/`VERIFY ITINERARY` behavior | Cryptic applicability | Real if it transfers; currently outside the frozen slice | LOW currently, rises later | LOW currently | Optional | Yes for now — outside current priority scope | Future Pass D resumption when Post-ticketing becomes material | Cryptic-specific source check |
| SCOPE-1 (25 vs. 27 topic-count) | OPEN, newly named | Both counts exist in real artifacts | Whether they describe the same document | Underlies confidence in several curriculum-scope claims including OFFER-1 | LOW-MEDIUM | NONE | Optional | No — a quick, worthwhile check whenever curriculum work resumes | Future session | Direct comparison once both lists are available |
| B3 (waitlist/passive/ghost/open/ARNK) | UNVERIFIED, convergent negative finding | Neither this project nor Phase 1 substantiated these | Any confirming source | Low — never close to promotion | LOW | NONE | No | Yes — this is now a well-established negative finding | None required | Remains a documented non-finding unless new evidence appears unprompted |
| CONTAM-1 (SEO/mirror-site network) | CONFIRMED, five domains | The network fabricates specific false command claims | Whether other, not-yet-encountered domains belong to the same network | Prevents specific known-false claims from re-entering the project | Indirect (protective) | NONE | No | N/A — this is a completed exclusion, not an open question | None required | Keep the denylist active for future research |
| ELEM-1 (D4, mandatory element count) | Components resolved; exact enumerated list open | `NM`/`AP`/`APE`/`APM`/`TK`/`RF` all independently confirmed as real elements | A single source stating the exact enumerated "5" | Low residual risk — the components a learner needs are all confirmed; only the precise summary count is unpinned | LOW | NONE | No | Yes — low priority, components already sufficient for training | None required unless convenient | Close opportunistically if a source is found; not worth a dedicated session |
