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

Update 2026-09-25 (Phase 3.2): Karim approved the adjusted slice path
(07 Decision 22), the Terminal output rule (07 Decision 23), and the
`SRCTCM` step (07 Decision 24). Every command in the slice path is VERIFIED
(Verified Reference, second edition). Design Brief written (3.4). What
remains before the first build: Slice Build Spec (3.3), environment pack
(3.5), readiness check (3.6).

Update 2026-09-25 (Phase 3.6): 3.3 and 3.5 done (D25, D26); gaps G1–G3
closed; K5–K6 approved (D27) and applied. Readiness check run: passed,
subject to Karim's approval at the Phase 3 gate of K7 (contact-SSR
endings) and seven small content fixes. The repository `DEIXEN-KNOWLEDGE`
appears to be behind the Project (its main folder, read 2026-09-25, does not show the Phase 2–3 files); it must be brought up
to date before Phase 5, because `CLAUDE.md` makes Claude Code read from it.

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
| Vertical Slice rule; slice boundary (D8A) | CLOSED — path adjusted by D22; all path commands VERIFIED | Karim | Slice Build Spec (3.3) |
| Slice path adjustment (D22) | CLOSED — Approved 2026-09-25 | Karim | — |
| `SRCTCM` step in the slice (D24) | CLOSED — Approved 2026-09-25 | Karim | — |
| Design Brief (Execution Plan 3.4) | DONE — synchronized with D27 2026-09-25; awaiting Karim at the Phase 3 gate | Karim | Approve at the gate |
| Slice Build Spec (3.3) | CLOSED — Approved 2026-09-25 (D26) | Karim | — |
| Build Spec K1–K4 (D25) | CLOSED — Approved 2026-09-25 | Karim | — |
| `CLAUDE.md` (3.5) | CLOSED — Approved 2026-09-25 (D26) | Karim | — |
| Build Spec G1 (example screens) | DONE 2026-09-25 — Verified Reference V-14–V-18; residual details U-06–U-11 | Claude | K6 |
| Build Spec G2–G3 (slice content; Scope Disclosure) | DONE 2026-09-25 — `deixen-app/content/` (3 files); readiness-check fixes applied (7 items, ✎ in the review copy) | Karim | Approve at the Phase 3 gate |
| Build Spec K5 — element numbering (V-18 live renumbering vs. literal Build Spec §4 / D14 wording) | CLOSED — Approved 2026-09-25 (07 D27); APPLIED 2026-09-25 (Build Spec §4/§13, `CLAUDE.md` §8, 07 D14, LDS/LXA reading rules) | Claude | — |
| Build Spec K6 — screen details only partly shown in official examples (U-07–U-11) | CLOSED — Approved 2026-09-25 (07 D27); APPLIED 2026-09-25 (Build Spec §5/§12/§13, `CLAUDE.md` §3/§8, Design Brief §4, `disc.6`, Verified Reference §3) | Claude | — |
| Build Spec K7 — contact-SSR endings (Verified Reference U-12), found at the readiness check | OPEN — proposal in Build Spec §12; applied provisionally in the content | Karim | Decide at the Phase 3 gate |
| Name titles other than `MR` (U-13) | UNVERIFIED — slice main passenger changed to `MR` (content fix, awaiting gate) | Claude | Research with the Basic track |
| `AP` as the PRINT 'Phone' element | UNVERIFIED (Verified Reference U-14); lessons avoid claiming it; `tm.otherMissing` reworded as a DEIXEN task rule | Claude | Verify when the next Reference edition is made; not blocking |
| Readiness check (3.6) | RUN 2026-09-25 — PASSED subject to Karim's approval of K7 and the 7 content fixes (self-review, 07 D17) | Karim | Phase 3 gate |
| Phase 3 gate (Execution Plan §3) | PREPARED 2026-09-25 — awaiting Karim | Karim | Approve the pack → Phase 4 |
| Repository `DEIXEN-KNOWLEDGE` out of date (main folder, read 2026-09-25, does not show the Execution Plan, Constitution, Verified Reference, Build Spec, Design Brief, `CLAUDE.md`; still has 08 under its old name) | OPEN — found 2026-09-25 | Karim | Upload the current Project files before Phase 5 |
| Coach contract (D9); CS contract (D6) | CLOSED | Karim | Carry forward |
| Evidence, Assessment, Scenario contracts | CLOSED (unbuilt) | Karim | Slice Build Spec, Phase 3 |
| Domain/SME validation (D7) | SUPERSEDED by D12 | — | — |
| Manus protocol (D10A); arbitration outcome (D10) | SUPERSEDED (historical) | — | — |
| Verification Standard (D12); Teaching boundary (D13) | CLOSED | Karim | Apply in Phase 3 |
| Terminal display formats / error texts that cannot be verified | CLOSED by D23 (official example formats; unsourced messages shown as labeled training messages) | Karim | Apply in 3.3 |
| Old engine as history; fresh build (D14) | CLOSED | Karim | — |
| Amadeus Verified Reference (D15) | CLOSED — third edition 2026-09-25, amended at the readiness check (U-12–U-14) | Claude | Extend as scope grows |
| Governance set (D16); Roles (D17) | CLOSED | Karim | — |
| Curriculum goal (D18) | CLOSED | Karim | Market evidence sourced during curriculum work |
| Absent artifacts (D19); First build (D20); Owner name (D21) | CLOSED | Karim | — |
| Engine strategy "conformance oracle" (former delegated decision) | WITHDRAWN | — | Replaced by D14 |
| Evidence/State concrete schema | DONE (delegated) — Slice Build Spec §11; answers the Event Log granularity and chain-continuity questions by design | Claude | — |
| Coach layout (global vs per-page) | DELEGATED | Claude Design / Code | Resolve at build |
| Curriculum order (competency vs command order); Lesson 17; 8 Advanced lessons | OPEN | Claude, then Karim | Curriculum authoring after the slice (D18) |
| Pricing prerequisites of the slice (name before `FXP`?) | UNVERIFIED (U-01) — no longer blocking: D22 puts `NM` before `FXP` | — | — |
| Old path `AN → SS → FQD → FXP` still written in LDS (§ tiers, ~l.604, ~l.715), LXA (~l.153), 05 | Superseded by D22; LDS/LXA reading rules point to 07; 05 updated | Claude | Slice Build Spec uses the D22 path |
| `QE`/`QN`/`QD` real functions | OPEN — not taught | Claude | Verification when queues enter scope |
| `FXX` real entry | VERIFIED (V-06) | — | — |
| SSR/seat association; voiding; `FXL`/`TQT`/`TTE`/`FQF`; Offers (`OFS`); post-ticketing status; contact-SSR endings (U-12); name titles (U-13); `AP` as PRINT Phone (U-14) | OPEN — backlog (the five PRINT elements themselves are VERIFIED, V-08) | Claude | Verification when each enters scope |
| Work Shift Simulator scope | DEFERRED | Karim | Revisit only if it becomes a real candidate |
| `cleanRunsNeeded` (old placeholder) | HISTORICAL | — | Mastery rules come from LDS, not old code |
| `ancillary.js` wiring; live-echo numbering bug (#7) | HISTORICAL (old engine) | — | Lessons only (D14) |

## 4. What Is Not Blocking

Absent artifacts (D19), the EgyptAir curriculum (D18), Design Execution (its
own phase), and the Advanced backlog do not block Phase 3.
