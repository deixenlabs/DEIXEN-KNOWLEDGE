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

Update 2026-09-25 (Phase 4, steps 1–4): Claude Design proposed three
directions; Karim chose A "Margin" (07 D31) and ruled that the Terminal
shows Amadeus only (07 D30). Five delegated decisions recorded (07 D32–D36).
Impact check done: Build Spec §5/§13, Design Brief §4/§6/§8, `CLAUDE.md` §3,
file 04, `slice.json`, both string files, the content reading copy,
Execution Plan §3/§7, file 00. Refinement of A under way; three items stay
open (below).

Update 2026-09-26 (Phase 4, steps 5–6): Part 1 and Part 2 of the refinement
reviewed (self-review, 07 D17). Every Terminal line in every frame matches the
Verified Reference renderings; Part 1 fixes applied. Answers recorded as 07
D41. What remains: a short fix pass in a new Claude Design session, then the
Phase 4 gate (Karim).

Update 2026-09-26 (Phase 4 gate): the session-3 fixes checked (self-review,
07 D17) — all six applied, every Amadeus display line still matches the
Verified Reference renderings, `tokens.css` unchanged. **Karim approved the gate
(07 D42): refined direction A, typefaces, header lockup B, `tokens.css`.
Phase 4 is closed; Phase 5 (Build) is next.** Preparing Phase 5 (by
delegation): interface words added as `ui.*` keys (07 D43); the `AN` header
number gap closed (07 D44); Build Spec §2 and `CLAUDE.md` now point to the
approved design. One question for Karim (below): how Claude Code will read
the approved boards.

Update 2026-09-26 (Phase 5 preparation): repository checked against the
Project (Constitution §5) — the 12 files of the Phase 4 gate are the current
versions (Execution Plan identical line for line; the other 11 carry every
Phase 4 gate change; both string files have the same 204 keys, and every key
`slice.json` lists exists). Karim approved exporting the approved boards
into the repository (07 D45): the open question below is closed. The
repository check also found that the Corpus Map (file 00 A8/A9) was wrong
about some historical files; corrected in file 00 (row below).

Update 2026-09-26 (Phase 5, build steps 1–2A): steps 1 and 2 part A locked
(07 D46, D48); one tab at a time (07 D47). Preparing step 2 part B (07 D49):
the weekday codes of the `AN` header are VERIFIED (V-14); `6X` has the
invented name `PRACTICE AIRLINE`; `disc.2` matches the "not recognized" /
"not covered" rule; the part B gaps are closed in Build Spec §6A. The
repository `DEIXEN-KNOWLEDGE` on GitHub was read the same day: its main
folder holds pre-Phase-5 copies, and the newest copies of 07, 13 and the
Execution Plan sit two folders deep (`DEIXEN-KNOWLEDGE/DEIXEN-KNOWLEDGE/`);
the Build Spec with D46–D47 is not on GitHub at all. Karim is asked to put
the current files in the main folder (row below).

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
| Design Execution (colors, type, logo, identity) | CLOSED for the slice — approved design, typefaces, lockup B, `tokens.css` (07 D42, 2026-09-26); identity provisional | Karim | Carry into Phase 5 (Build Spec §2) |
| Working name DEIXEN | PROVISIONAL | Karim | Reopen only on evidence (Constitution §1) |
| Personal-first & Saudi/Gulf framing | CLOSED | Karim | Carry forward |
| Vertical Slice rule; slice boundary (D8A) | CLOSED — path adjusted by D22; all path commands VERIFIED | Karim | Slice Build Spec (3.3) |
| Slice path adjustment (D22) | CLOSED — Approved 2026-09-25 | Karim | — |
| `SRCTCM` step in the slice (D24) | CLOSED — Approved 2026-09-25 | Karim | — |
| Design Brief (Execution Plan 3.4) | CLOSED — Approved 2026-09-25 (07 D28) | — | Input to Phase 4 |
| Slice Build Spec (3.3) | CLOSED — Approved 2026-09-25 (D26) | Karim | — |
| Build Spec K1–K4 (D25) | CLOSED — Approved 2026-09-25 | Karim | — |
| `CLAUDE.md` (3.5) | CLOSED — Approved 2026-09-25 (D26) | Karim | — |
| Build Spec G1 (example screens) | DONE 2026-09-25 — Verified Reference V-14–V-18; residual details U-06–U-11 | Claude | K6 |
| Build Spec G2–G3 (slice content; Scope Disclosure) | CLOSED — Approved 2026-09-25 with the 7 readiness-check fixes (07 D28) | — | — |
| Build Spec K5 — element numbering (V-18 live renumbering vs. literal Build Spec §4 / D14 wording) | CLOSED — Approved 2026-09-25 (07 D27); APPLIED 2026-09-25 (Build Spec §4/§13, `CLAUDE.md` §8, 07 D14, LDS/LXA reading rules) | Claude | — |
| Build Spec K6 — screen details only partly shown in official examples (U-07–U-11) | CLOSED — Approved 2026-09-25 (07 D27); APPLIED 2026-09-25 (Build Spec §5/§12/§13, `CLAUDE.md` §3/§8, Design Brief §4, `disc.6`, Verified Reference §3) | Claude | — |
| Build Spec K7 — contact-SSR endings (Verified Reference U-12), found at the readiness check | CLOSED — Approved 2026-09-25 (07 D28) | — | Research the endings before the Basic track expands |
| Name titles other than `MR` (U-13) | UNVERIFIED — slice main passenger is `MR` (07 D28) | Claude | Research with the Basic track |
| `AP` as the PRINT 'Phone' element | UNVERIFIED (Verified Reference U-14); lessons avoid claiming it; `tm.otherMissing` reworded as a DEIXEN task rule | Claude | Verify when the next Reference edition is made; not blocking |
| Readiness check (3.6) | PASSED 2026-09-25 (self-review, 07 D17); K7 and the 7 content fixes approved (07 D28) | — | — |
| Phase 3 gate (Execution Plan §3) | CLOSED — Approved 2026-09-25 (07 D28) | Karim | — |
| Standing delegation to the project lead (07 D29) | CLOSED — Approved 2026-09-25; reserved list in 07 D29 | Karim | Claude records delegated decisions in 07 as "by delegation (D29)" |
| Phase 4 — Design direction | CLOSED — A "Margin" chosen 2026-09-25 (07 D31); B and C not taken | Karim | Refinement (Plan §7 step 5) |
| Terminal shows Amadeus only; feedback/hints/Coach in a DEIXEN panel (07 D30) | CLOSED — Approved 2026-09-25 | Karim | Applied: Build Spec §5/§13, Brief §4, `CLAUDE.md` §3 |
| Terminal script/direction (D32); wrong-entry training lines `tm.notAccepted` / `tm.notForTask`, PNR unchanged (D33); long training messages (D34); Phase 4 validation matrix (D35); phone Terminal pans, no wrap (D36) | CLOSED — by delegation (D29), 2026-09-25 | Claude | Karim may reverse any. `tm.notForTask` was added during the impact check (see 07 D33) |
| Arabic chrome drafts from Claude Design (area names, hint levels, controls, other chrome — list on the canvas board P2-Issues) | DONE 2026-09-26 — 71 `ui.*` keys in both string files, listed in `slice.json` (07 D43; D41 fixes included; one AR wording made count-neutral) | Claude; Karim may change any word | — |
| Phase 4 gate items reserved to Karim (07 D29 item 2) | CLOSED — Approved 2026-09-26 (07 D42): refined direction A; the five typefaces; lockup B; `tokens.css` in the code repository | Karim | — |
| Karim checks the canvas with real fonts (line breaks in both scripts) | CLOSED with the gate — Karim was asked to look before approving; no separate report | — | The build checks line breaks at every breakpoint in both languages (Definition of Done) |
| Retry / Reset scope in the Terminal | CLOSED — by delegation 2026-09-25 (07 D37): one "Reset task" in practice only; no "Retry step"; full reset in Growth | Claude | Done — `ui.term.resetTask`, `ui.reset.everything` (07 D43) |
| Hint order | CLOSED — by delegation 2026-09-25 (07 D38): in order; inapplicable levels not shown | Claude | — |
| `ui.assessment.carryover` read "1 hints" (Claude Design Part 1, issue 01) | CLOSED — reworded count-neutral (07 D39) | Claude | — |
| Chain status words ("Practised" in the Part 1 design) | CLOSED — "Correct in DEIXEN" / dash / Next / Optional (07 D40) | Claude | — |
| `AN` header number before the weekday: Build Spec §5 says "values in `slice.json`", but `slice.json` held no such value (found in the Part 1 review) | CLOSED 2026-09-26 (07 D44) — fixed value `30` in every `AN` display, never computed from the date; marker; not taught | Claude | — |
| How Claude Code reads the approved boards: they live on the Claude Design canvas, a claude.ai page behind sign-in that a Claude Code session on Karim's computer cannot open | CLOSED — Approved 2026-09-26 (07 D45): 68 boards + `tokens.css` copied unchanged into `design/phase4/` with a sha256 manifest; Build Spec §2, `CLAUDE.md` §2/§4, 00, Execution Plan §5 updated | Karim | Karim uploads the folder; Claude Code checks the manifest before reading |
| Corpus Map vs repository (found 2026-09-26): 00 A9 listed as absent some files that are in the repository's `Historical/` folders (`PROJECT-20.md`, `SDD.md`, `AMADEUS_CURRICULUM.md`, `COMMAND_REFERENCE.md`, `DESIGN_SYSTEM_UI_BLUEPRINT.md`, `DEVELOPMENT_RULES.md`, `PRODUCT_STRATEGY_UX_ARCHITECTURE-1.md`, the Approved Corpus Review & Opus Readiness Brief, and others); 00 A8 said two historical plans are in the repository, which they are not | CORRECTED in 00 (by delegation, D29) | Claude | Historical only — no current file depends on them (07 D16, D19); not blocking. The repository has two folders, `Historical` and `Historical ` (trailing space) — Karim may merge them when convenient |
| Real Cryptic host response to each wrong entry in the slice | OPEN — research backlog (07) | Claude | Needs official Cryptic sources (D12); an API host-message list cannot verify it. A verified message replaces the training line in place |
| Repository `DEIXEN-KNOWLEDGE` out of date (main folder, read 2026-09-25, does not show the Execution Plan, Constitution, Verified Reference, Build Spec, Design Brief, `CLAUDE.md`; still has 08 under its old name) | CLOSED 2026-09-25 — Karim reports the files are updated in both places | — | Keep both in step after each change |
| Repository layout on GitHub (read 2026-09-26): current files are nested two folders deep; the main folder has older copies; Build Spec D46–D47 missing | OPEN — sync problem (Constitution §5.4, §18) | Karim uploads | Put the current files in the main folder; Claude Code reads the local copy, so Karim's local `DEIXEN-KNOWLEDGE` must hold the current files before session 3 |
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
| Evidence/State concrete schema | DONE (delegated) — Slice Build Spec §11; answers the Event Log granularity and chain-continuity questions by design. Built and locked as build step 1 (07 D46); `result` on ending events clarified; one tab at a time (07 D47) | Claude | — |
| Two browser tabs at once (Claude Code `ISSUES.md` I-2, 2026-09-26) | CLOSED — 07 D47 (one tab records; the other shows a notice) | Claude (D29) | Implemented at build step 3 |
| File 03 said Calculated evidence is persisted (Claude Code `ISSUES.md` I-3) | CORRECTED in 03 (07 D46) | Claude (D29) | — |
| `AN6X…` header needs a fictional airline name (app `ISSUES.md` I-4) | CLOSED — `airlineName` `PRACTICE AIRLINE` in `slice.json` (07 D49) | Claude (D29); Karim may change the name | Claude Code wires it in (session 3) |
| `AN` weekday codes other than `SU` (app I-5) | VERIFIED — all seven codes in official `AN` headers (Verified Reference V-14, amended 2026-09-26; 07 D49) | — | — |
| `disc.2` wording vs "not recognized" rule (app I-6) | CLOSED — `disc.2` EN/AR and Build Spec §6 reworded (07 D49) | Claude (D29) | — |
| Gaps for build step 2 part B (multiple missing items at `ER`; bypass window; filed-PNR layout; stored `SSR CTCM` ending; `SRCTCR` in the main task; `FXP` before `ER`; entries after completion) | CLOSED — Build Spec §6A (07 D49); V-18 segment line after end of transaction recorded | Claude (D29) | Claude Code session 3 |
| Exact wording of app `docs/ISSUES.md` I-4…I-7 and `docs/DECISIONS.md` T3 into 07 | OPEN — requested in the session-3 prompt | Claude | After session 3 |
| `AN` checklist (b) rarely fails (app I-7) | NOTED — learning-evidence observation (07 D48) | — | Revisit at curriculum expansion |
| Coach layout (global vs per-page) | DRAWN in the approved design (07 D42): DEIXEN's margin on desktop, the DEIXEN drawer on phones, only when a coach string applies; code structure DELEGATED | Claude Code | At build |
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

Absent artifacts (D19), the EgyptAir curriculum (D18), Design Execution (closed for the slice, 07 D42), and the Advanced backlog do not block Phase 5.
