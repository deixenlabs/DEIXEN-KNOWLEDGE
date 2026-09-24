---
name: DEIXEN Decision Resolution Register
status: CURRENT — rewritten 2026-09-24 (Execution Plan Phase 2). Replaces the 2026-09 version whose verdict was "READY TO ENTER KNOWLEDGE RECOVERY"; that version remains in repository history.
owns: The audited status of every known decision and open item, and the disposition of the Phase 1 review findings
does not own: the decisions themselves (file 07 states them); Amadeus domain truth (DEIXEN_Amadeus_Verified_Reference.md, Phase 3)
---

> **Synchronization note — Phase 2, 2026-09-24.** Working name: **DEIXEN**
> (provisional). Owner: **Karim** — earlier records used the name "Malik" for
> the same person. Decisions are stated in
> `07_DEIXEN_Canonical_Decisions_and_Current_State.md`; this file tracks their
> status and the open items around them.

# DEIXEN — Decision Resolution Register

## 1. Summary

On 2026-09-24 Karim replaced the Pre-Opus preparation phase with
`DEIXEN_Execution_Plan.md`, assigned Claude (Opus) as project lead (reviewer,
editor, verifier), removed the SME dependency in favor of a web Verification
Standard, and confirmed that files absent from the Project and repository are
simply absent. Phase 1 (read-only review) produced 16 findings; all are
dispositioned below. The former "Knowledge Recovery" phase no longer exists —
its items are reassigned to Phase 3 (verification and readiness) or to later
curriculum authoring.

What still stands between the project and its first build is concentrated in
one place: the slice's Amadeus behavior. The first edition of the Verified
Reference (2026-09-25) covers it except the items listed there as UNVERIFIED.

## 2. Phase 1 Findings — Disposition

Review type: self-review by the project lead (Decision 17 — independent
review waived by Karim).

| # | Finding | Disposition | Where |
|---|---|---|---|
| F1 | No traceable sources for Amadeus claims. (Correction after Karim added six evidence files on 2026-09-24: sources are named by site or description, but no file gives a URL and access date.) | All Amadeus claims UNVERIFIED until re-checked | 07 D12; Phase 3 |
| F2 | The slice path `AN → SS → FQD → FXP` has no passenger-name step; pricing prerequisites were never confirmed | Phase 3 priority; slice change only by Karim decision | 07 D8A, D20 |
| F3 | SME Decision 7 impossible — no SME | Superseded by Decision 12 | 07 |
| F4 | Old engine code unavailable; "conformance oracle" strategy unexecutable and possibly wrong (`QE`/`QN`/`QD`) | Withdrawn; 05 historical | 07 D14; 05 |
| F5 | Old engine limitations conflict with "behavior matching real Amadeus" | Not requirements; lessons only | 07 D14 |
| F6 | Contradictory project-state statements across 00/07/13/14/evidence files/LXA | One current status in 07; others marked historical | 07, 00, 14, banners |
| F7 | Old owner name (~60 places) and old product name in current content | Migrated; history preserved in filenames | all current files |
| F8 | Constitution §9 roles and the absent execution plan | §9 amended; Execution Plan written | Constitution, Plan |
| F9 | Manus contradiction (07/13 vs 08) | Manus historical, no role | 07 D10A, D17; 08 |
| F10 | Curriculum anchored on EgyptAir; market-evidence sources missing | Goal redefined; market requirements must be sourced | 07 D18; 06 |
| F11 | LDS/LXA unaware of the Amadeus evidence and new decisions; very large | Reading-rule note added to both; slice-only extraction in Phase 3 | LDS, LXA, Plan |
| F12 | 8A deferred "a rebrand that discards the approved identity" though no identity is approved | Wording corrected | 07 D8A |
| F13 | Referenced files missing | Recorded absent | 07 D19; 00 |
| F14 | Operational documents heavy and built on retired phases | Demoted to supporting | 07 D16; banners |
| F15 | Voiding and SSR/seat — market-required, unverified | Advanced-track backlog; Decision 12 applies | 07 research backlog |
| F16 | Skill state "VERIFIED" collides with the new source label "VERIFIED" | Skill state renamed **CONSOLIDATED** | LDS, LXA |

Two further inconsistencies found while editing: file 04 still called
localization OPEN although Decision 11 closed it (fixed in 04); file 04
presented a navy/blue color language as "durable" although colors are open
(relabeled as historical input in 04).

## 3. Current Decision Register

| Item | Status | Owner | Next action |
|---|---|---|---|
| Product Positioning; Five-Area IA; Terminal Priority | CLOSED | Karim | Carry forward |
| Platform Direction (not PWA/backend-first; not a rejection) | CLOSED | Karim | Carry forward |
| Localization — Arabic + English, RTL + LTR (D11) | CLOSED | Karim | Build approach decided in Phase 3/5 |
| Design Positioning | CLOSED | Karim | Carry forward |
| Design Execution (colors, type, logo, identity) | OPEN | Karim, with Claude Design | Execution Plan Phase 4 |
| Working name DEIXEN | PROVISIONAL | Karim | Reopen only on evidence (Constitution §1) |
| Personal-first & Saudi/Gulf framing | CLOSED | Karim | Carry forward |
| Vertical Slice rule; slice boundary (D8A) | CLOSED — Verification-Pending | Karim | Phase 3 verification; D20 |
| Coach contract (D9); CS contract (D6) | CLOSED | Karim | Carry forward |
| Evidence, Assessment, Scenario contracts | CLOSED (unbuilt) | Karim | Slice Build Spec, Phase 3 |
| Domain/SME validation (D7) | SUPERSEDED by D12 | — | — |
| Manus protocol (D10A); arbitration outcome (D10) | SUPERSEDED (historical) | — | — |
| Verification Standard (D12); Teaching boundary (D13) | CLOSED | Karim | Apply in Phase 3 |
| Terminal display formats / error texts that cannot be verified | OPEN | Karim | Decide in Phase 3 with evidence |
| Old engine as history; fresh build (D14) | CLOSED | Karim | — |
| Amadeus Verified Reference (D15) | CLOSED — first edition 2026-09-25 (slice scope) | Claude | Extend as scope grows |
| Governance set (D16); Roles (D17) | CLOSED | Karim | — |
| Curriculum goal (D18) | CLOSED | Karim | Market evidence sourced during curriculum work |
| Absent artifacts (D19); First build (D20); Owner name (D21) | CLOSED | Karim | — |
| Engine strategy "conformance oracle" (former delegated decision) | WITHDRAWN | — | Replaced by D14 |
| Evidence/State concrete schema | DELEGATED — not done | Claude | Slice Build Spec, Phase 3 |
| Coach layout (global vs per-page) | DELEGATED | Claude Design / Code | Resolve at build |
| Curriculum order (competency vs command order); Lesson 17; 8 Advanced lessons | OPEN | Claude, then Karim | Curriculum authoring after the slice (D18) |
| Pricing prerequisites of the slice (name before `FXP`?) | OPEN — UNVERIFIED after search (Verified Reference U-01); mandatory PNR elements VERIFIED (V-08) | Karim | Decide slice path (D20), Phase 3.2 |
| `QE`/`QN`/`QD` real functions | OPEN — not taught | Claude | Verification when queues enter scope |
| `FXX` real entry | VERIFIED (V-06) | — | — |
| SSR/seat association; voiding; `FXL`/`TQT`/`TTE`/`FQF`; Offers (`OFS`); post-ticketing status; mandatory-element list | OPEN — backlog | Claude | Verification when each enters scope |
| Work Shift Simulator scope | DEFERRED | Karim | Revisit only if it becomes a real candidate |
| `cleanRunsNeeded` (old placeholder) | HISTORICAL | — | Mastery rules come from LDS, not old code |
| `ancillary.js` wiring; live-echo numbering bug (#7) | HISTORICAL (old engine) | — | Lessons only (D14) |

## 4. What Is Not Blocking

Absent artifacts (D19), the EgyptAir curriculum (D18), Design Execution (its
own phase), and the Advanced backlog do not block Phase 3.
