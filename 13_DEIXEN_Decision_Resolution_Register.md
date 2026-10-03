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

Update 2026-09-28 (Phase 5, build step 2 locked; step 3 prepared): step 2
locked (07 D50–D51, tag `step-2b-engine`). Preparing step 3, the gaps in
Build Spec §7–§11 were closed in a new §7A (07 D52); two strings
(`ui.oneTab.*`) and one feedback item (`reveal.ER.ready`) added. The GitHub
main folder, read 2026-09-28, holds the current files: the layout row is
closed. Same day: step 3 built and locked (07 D53, tag `step-3-bridge`, 723
tests); `ui.dataReset` added; return to practice after a finished
assessment or scenario (Karim, app I-12).

Update 2026-09-28 (step 4 prepared): the "current step" for hints defined,
with the hint-level display, the entry-field case rule, the 4A/4B split and
the load notices — Build Spec §7B (07 D54). The in-app exit from a running
assessment or scenario now has to be decided before 4B.

Update 2026-09-29 (step 4A locked): session 5 built 4A — tag
`step-4a-terminal`, 818 unit/component and 69 browser tests (07 D55).
App I-12 (second half: a run starts at an accepted hint request), I-13
(storage refused), I-14 (the name as one key) and I-15 ("Booking as it
stands") closed; the over-time behaviours (app T7) accepted with two
guards. Leaving a running assessment or scenario inside the app decided:
after a confirmation, it is recorded as abandoned (07 D56). 7 strings
added (216 keys in each string file). The places 4B would guess closed in Build Spec §7B items 11–15 (07 D57). Next: 4B in two sessions.

Update 2026-09-30 (step 4B-1 checked): session 6 built the Flight Deck,
Learning, Ghost Mode, Growth, Reset and the Scope Disclosure page on
`feature/screens-4b1` (reported: 943 unit/component and 104 browser
tests). Checked against the repository itself, read-only (07 D58): the
code and the named tests match the rules; the Amadeus-string trace gap of
D55 is closed; two tests are missing (a stored `SRCTCR` in "Booking as it
stands"; Ghost Mode in the "no false affordance" test) and the planted
faults are not recorded. App I-16 to I-20 answered (Build Spec §7B items
16–18). Merge and tag `step-4b1-screens` at the start of session 7, after
the two tests are added.

Update 2026-09-30 (build step 4 complete): session 7 closed the 4B-1
gaps, merged it (tag `step-4b1-screens`), built 4B-2 — the assessment and
scenario screens and the leave question — and merged it (tag
`step-4b2-screens`; reported 994 unit/component and 158 browser tests).
Checked against the repository, read-only (07 D60). D58's "no `SRCTCR`
test" finding was wrong at the bridge level and is corrected in D60. Next:
the rules for build step 5 (Coach; app I-21). Rules for 4B-2 written
(07 D59, Build Spec §7B items 19–20): "the scenario completed" means
completed with every checklist item met (as `slice.json`
`scenario.acceptance` says); the scenario and assessment rows follow the
same test; the end of an assessment shows `ui.assessment.result` or the
new `ui.assessment.resultUnmet` (217 keys in each string file).

Update 2026-09-30 (rules for build step 5 closed): 07 D61, Build Spec
§7C. Every Coach text in the slice is diagnostic, so Coach texts stay
out of the event record and independence is unchanged; Coach speaks in
the assessment and the scenario as in practice (file 06 requires both
touchpoints), without the escalation offer; the bypass keeps its
feedback note and `coach.bypassRecorded`; Coach never opens the phone
drawer by itself; the escalation count is per session, per skill and
category, across contexts; a new Coach note on Growth says why the status
is Needs More Practice; the five touchpoints are mapped to screens.
Strings: `coach.escalate` reworded count-neutral; `ui.coach.openLesson`,
`coach.growth.reinforce`, `coach.growth.assessmentUnmet` added (220 keys
in each string file). Next: session 8 (build step 5).

Update 2026-10-01 (build step 5 complete): session 8 built Coach (tag
`step-5-coach`; reported 1070 unit/component and 187 browser tests) and
answered I-21. Checked against the repository, read-only (07 D62): the
code follows Build Spec §7C; 22 planted faults recorded as planted. App
I-22 (the escalation offer at a bypass) kept as the spec says and written
into §7C item 6. Next: build steps 6 and 7, then Karim's learner test.

Update 2026-10-01 (rules for build steps 6 and 7 closed): 07 D63, Build
Spec §7D. Step 6 is a check proved as a Definition of Done trace; step 7
is the pass, with what "the accessibility baseline passes" means written
out (WCAG check at all eight widths, keyboard, touch targets, reduced
motion, text spacing, in-between widths, non-text contrast, names). Gaps
found in the repository closed as rules: the scrolling notes block gets a
role and name; the phone drawer opens on the newest notes; the end note
stays in view; lockup B gets a test. No string, token or event added.
Next: session 9 (steps 6 and 7), then Karim's learner test.

Update 2026-10-02 (build steps 6 and 7 checked): 07 D64. Session 9 ran
step 6 (tag `step-6-check`: the Definition of Done trace, every §13 line
proved except the learner's own run) and step 7 on `feature/step7-pass`
(nine defects fixed, 15 planted faults caught, 268 browser tests). App
I-23 answered: `tokens.css` kept; the spec's "both 0" corrected (the hold
is a still reading pause). App I-24 answered: English terms written in the
approved Arabic content are allowed. Next: session 9B merges and tags
`step-7-pass`; then Karim's learner test.

Update 2026-10-02 (build complete; learner test prepared): 07 D65 —
session 9B checked against the repository: one commit (`a697bce`: the
reduced-motion test renamed, checks unchanged; I-23 and I-24 marked
closed), merged into `main` (`3fdb342`), tag `step-7-pass`; `src/`,
`content/` and `tokens.css` untouched. Every build step is done. 07 D66 —
Karim's learner test prepared: a guide in Egyptian Arabic with a report
form (a Claude doc), 14 steps in two sittings, every watch point folded
in, and what it cannot cover stated. Next: Karim runs the test; his
verdict is the Phase 5 gate.

Update 2026-10-02 (Phase 5 closed): 07 D67 — Karim ran the learner test
and closed Phase 5: the slice works end to end; his findings (lessons
assume prior knowledge, Ghost Mode screens unexplained, the practice
booking reported lost, training lines that look alike whether right or
wrong) go into the detour he plans before Phase 6, as input to its
learning review. Before the snapshot tag, a read-only check of the
practice-run finding (detour package v1.8, Prompt 0).

Update 2026-10-02 (Phase 5 snapshot fixed; the detour decided): results,
not new decisions. **Prompt 0** (the practice-run check of the
learner-test finding, 07 D67): classification (b). No path loses the
booking where the Build Spec (§7A item 1, §7B item 12) says the run
continues. But in six paths a practice button correctly starts a new,
empty booking without saying so on screen; the three most likely to match
Karim's report are reached when the app itself (Flight Deck, Learning
area, escalation offer) sends the learner back to a lesson whose step is
already done in this run. Carried into Step 2 as learner-test input, not
fixed now. **Phase 5 snapshot fixed:** annotated tag `phase-5-final` at
`3fdb342429dc99ebf8268bad0da3075eacbd40a7` (local only, no remote), after
typecheck, 1070/1070 unit tests, build and 268/268 browser tests passed.
Observation for Step 1, not a decision: running the browser tests
rewrites 209 tracked files in `docs/a11y` and `docs/screens` (the random
booking reference); they were restored before tagging. 07 D68 — Karim
inserted the four-step detour between Phase 5 and Phase 6 (Execution Plan
§3, §5, §7 updated; 00 updated). Next: Step 1.

Update 2026-10-03 (detour steps 1–3; the Freeze accepted): Steps 1 and 2
ran and Karim accepted their handoff blocks; Step 3 proposed the Freeze
Package; the project lead reviewed it (self-review, D17); Karim accepted
it with his changes. 07 D69 records the Freeze (F-01–F-21, 13 open items,
how a frozen decision is changed), step 4's design scope and the landing
times, verbatim; a separate check confirmed the record matches the
accepted text. 07 D70 authorizes Prompt 7 (the Design Exploration Skill,
auxiliary tooling, not a step). 07 D71: Karim decides the Constitution's
repository address. Sync incident the same day: at 14:25 an upload
replaced 07 and 13 with copies of 2026-10-02 (old copies loose in
`C:\Users\DELL\Downloads\`); restored from GitHub history and re-uploaded
at 15:27; uploads now come only from the knowledge folder, and Karim
deleted the loose copies. Next: the before-Step-4 tasks (07 D69 (c)),
then Prompt 7, then step 4.

Update 2026-10-04 (before-Step-4 task 1, F-19, landed): 07 D72 — checked
against the repository, read-only. `main` = `c093d5e` (merge of
`feature/f19-reproducible-tests`; not tagged). The tests now use a fixed
locator source through the bridge's existing random dependency and a fixed
time zone; screenshots are taken with the pointer on nothing interactive
and transitions finished, and are rewritten only beyond a measured
tolerance (app I-25: the largest "noise" was the foot buttons' hover fade).
Three planted changes were each caught. Only test code and evidence files
changed; the built app is unchanged. Next: before-Step-4 task 2, F-02.

Update 2026-10-04 (before-Step-4 task 2, F-02, landed): 07 D73 — checked
against the repository, read-only. `main` = `b5c66e5` (merge of
`feature/f02-training-roles`; not tagged). The bridge now gives every
training line — in the Terminal and in "Booking as it stands" — a role
(refused / accepted / outside), from the entry's recorded result computed in
one place; a line standing for a stored element (`tm.rfLine`, `tm.ctcrLine`)
takes the role of the entry that created the element. Only `src/bridge/`, one
new test file and the app's docs changed; nothing a learner sees changed.
Five planted faults caught. Next: before-Step-4 task 3, F-03.

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
| Repository layout on GitHub (read 2026-09-26): current files are nested two folders deep; the main folder has older copies; Build Spec D46–D47 missing | CLOSED 2026-09-28 — main folder read again: current files (07 with D51, Build Spec §6A items 8–10, content files) (07 D52) | Karim uploads | Keep uploading each update to the main folder |
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
| Exact wording of app `docs/ISSUES.md` I-4…I-7 and `docs/DECISIONS.md` T3 into 07 | CLOSED — received in the session-3 report; matches D48/D49 in substance (07 D50) | — | — |
| Build step 2 part B (sessions 3, 3B) | CLOSED — merged, tag `step-2b-engine`, 600 tests (07 D51) | — | Build step 3 |
| Two local copies of `DEIXEN-KNOWLEDGE` on Karim's computer (`Documents\DEIXEN\…` used by Claude Code; `Downloads\Documents\…` git copy) | CLOSED 2026-10-03 — the knowledge folder is `Downloads\Documents\DEIXEN\DEIXEN-KNOWLEDGE` (07 D58); detour Step 3 found the older duplicate folders gone (Freeze Package S3-03 (c)) | Karim | Uploads only from that folder |
| App I-8 header after end of transaction; I-9 `FQD` layout | CLOSED — DEIXEN renderings in Verified Reference V-18, V-16; `disc.6` (07 D50) | Claude (D29) | Build in the finish session |
| App I-10 `TK OK` date `DDMMM`; I-11 changes after filing not covered | CLOSED — Karim in session 3 (07 D50; Build Spec §6A item 9) | Karim | — |
| Gaps for build step 3 (run and step-attempt boundaries; `result` mapping; which skill a feedback event belongs to; Ghost reveals; "immediately preceded"; skill-state pass and demotion; Error-Recovery Practice on `ER`; which hint levels apply; `reveal.ER` when nothing is missing; `{MISSING_LIST}` undefined; assessment/scenario completion; Growth order; `ui.growth.empty` vs the rule; engine inputs) | CLOSED — Build Spec §7A; `reveal.ER.ready`, `ui.oneTab.*`, token rule, `ui.growth.empty` (07 D52) | Claude (D29) | Claude Code session 4 |
| Build step 3 (session 4) | CLOSED — merged, tag `step-3-bridge`, 723 tests (07 D53) | — | Build step 4 |
| Return to practice after a finished assessment or scenario (app I-12) | CLOSED — Karim in session 4; Build Spec §7A item 1 (07 D53). Verbatim wording received in the session-5 report: its second half (a practice run starts at an accepted hint request) was missing from §7A item 1 — added (07 D55) | Karim | Build 4B-1 wires `startPractice()` |
| Notice when an unreadable or other-version record is reset (Build Spec §11) had no wording | CLOSED — `ui.dataReset` EN/AR (07 D53) | Claude (D29) | Screen shows it once (step 4) |
| Which skill is "the current step" for hints | CLOSED — Build Spec §7B item 1 (07 D54); the handoff's path-order starting point rejected (it conflicts with `P1-04b` / `er.partial.*`) | Claude (D29) | Claude Code session 5 (4A) |
| Gaps for build step 4 (hint levels on the screen; entry-field case; controls to states not yet built; where the load notices appear) | CLOSED — Build Spec §7B items 2–5 (07 D54) | Claude (D29) | Claude Code session 5 (4A) |
| Build step 4, part 4A (app shell, load notices, Terminal practice) | CLOSED — merged, tag `step-4a-terminal`, 818 unit/component + 69 browser tests (07 D55) | — | Build step 4B |
| App T7 — behaviours over time no frame shows (where a new entry lands, brief folding, which notes stay, scroll position) | CLOSED — accepted with two guards, Build Spec §7B item 10 (07 D55) | Claude (D29) | — |
| Browser refuses storage: empty page, no approved notice (app I-13) | CLOSED — `ui.noStorage.*` EN/AR, Build Spec §7B item 8 (07 D55) | Claude (D29) | Build 4B-1 |
| "DEIXEN" as a word in three places (app I-14) | CLOSED — `ui.brand.name`, Build Spec §7B item 9 (07 D55) | Claude (D29) | Build 4B-1 |
| How `TK`, the contact SSR and `RF` read in "Booking as it stands" (app I-15) | CLOSED — Build Spec §7B item 6 (07 D55): verified forms only; `SSR CTCM` stops before the U-07 field; `SRCTCR` and pre-filing `RF` unnumbered, as their training line | Claude (D29) | Build 4B-1 |
| `CLAUDE.md` §8 Amadeus-string trace not reported for the 4A screens | CLOSED — re-run in session 6: the screens write no Amadeus text; every booking-panel form traces to V-07, V-11 or V-18 (07 D58) | Claude Code | — |
| Older `DEIXEN-KNOWLEDGE\DEIXEN-KNOWLEDGE\` sub-folder inside the main folder on Karim's computer (seen in session 5, not used) | CLOSED 2026-10-03 — gone (detour Step 3, Freeze Package S3-03 (c)) | Karim | — |
| Gaps for build step 4B (the Flight Deck's recommended action; the practice run between screens; lesson locking and the Learning link; Ghost replays; when the scenario and the assessment start) | CLOSED — Build Spec §7B items 11–15 (07 D57) | Claude (D29) | Sessions 4B-1, 4B-2 |
| Build step 4, part 4B-1 (Flight Deck, Learning, Ghost Mode, Growth, Reset, Scope Disclosure) | CLOSED — merged, tag `step-4b1-screens`, 944 unit/component + 104 browser tests (07 D58, D60) | — | — |
| 4B-1 gaps found in the repository: the panel side of a stored `SRCTCR` in "Booking as it stands" (the bridge side was already tested — D58 was wrong there); Ghost Mode in the "no false affordance" test; the 17 planted faults not recorded | CLOSED — tests added, faults recorded in app T8 (07 D60) | — | — |
| App I-16 ("In your task"), I-17 (no way into Ghost Mode drawn), I-18 (Ghost typing speed vs `tokens.css`), I-20 (empty Flight Deck status) | CLOSED — Build Spec §7B items 16–18; I-20 accepted (07 D58) | Claude (D29) | — |
| Where the knowledge folder is on Karim's computer | CLOSED — read from the device: `C:\Users\DELL\Downloads\Documents\DEIXEN\DEIXEN-KNOWLEDGE`, beside `deixen-app` (07 D58); earlier handoffs wrote it as `Documents\DEIXEN\DEIXEN-KNOWLEDGE` | — | Uploads go there |
| App I-19 (Ghost Mode: Pause and Replay, no "Play" word) | CLOSED — accepted as `P1-03` draws it (07 D58) | Claude (D29) | — |
| Ghost setup typing may feel slow at 70 ms per key | NOTED — learner-test watch point; a second token would be Karim's (07 D58) | Karim | Re-test (07 D69, F-11) — the Phase 5 learner test is done (07 D67) |
| "The scenario completed" read two ways (ended `completed` vs every checklist item met) | CLOSED — every checklist item met, as `slice.json` `scenario.acceptance` says; rows follow the same test (07 D59; Build Spec §7A item 13, §7B items 11 (d), 19, §10) | Claude (D29); Karim may reverse | 4B-1 aligned before merge |
| Where the assessment result shows; what shows when an assessment ends without every item met | CLOSED — `ui.assessment.result` / new `ui.assessment.resultUnmet`, in the DEIXEN panel (07 D59; Build Spec §7B item 20) | Claude (D29) | Session 7 |
| Build step 4, part 4B-2 (assessment and scenario screens, the leave question) | CLOSED — merged, tag `step-4b2-screens`, 994 unit/component + 158 browser tests (07 D60); build step 4 complete | — | Build step 5 |
| Rules for build step 5 (app I-21): Coach in the assessment ("on your own"); `coach.bypassRecorded` beside `ui.assessment.resultUnmet`; Coach never opening the phone drawer by itself | CLOSED — Build Spec §7C items 4–6 (07 D61); none changes what the assessment or the evidence means | Claude (D29); Karim may reverse | Session 8 |
| `session-export-1790735258194.zip` left in Karim's Downloads by session 7 (it read session 6's transcript to rebuild the fault list) | CLOSED 2026-10-03 — deleted by Karim (handoff housekeeping) | Karim | — |
| Third copy of the knowledge folder at `Documents\DEIXEN-KNOWLEDGE` (Windows line endings; fails the manifest check; seen in session 6, not used) | CLOSED 2026-10-03 — deleted by Karim (handoff housekeeping) | Karim | — |
| Escalation offer needs a per-session count of same-category errors | CLOSED — Build Spec §7C item 7 (07 D61): invalid entries, same skill and category, one app load, all contexts; offered in practice only; new link `ui.coach.openLesson` | Claude (D29) | Session 8 |
| Leaving a running assessment or scenario inside the app (K3 covers only closing the browser) | CLOSED — after a confirmation (`ui.leave.*`), leaving records it as abandoned; navigation stays enabled (07 D56; Build Spec §7B item 7) | Claude (D29); Karim may reverse | Build 4B-2 |
| Whether a Coach explanation beside a verified message (e.g. `coach.needTk`) counts as corrective feedback for independence | CLOSED — no: all six `coach.*` texts are diagnostic under the §8 test; Coach texts stay out of the event record; later corrective content must be a feedback item (07 D61; Build Spec §7C item 3) | Claude (D29) | — |
| `AN` checklist (b) rarely fails (app I-7) | NOTED — learning-evidence observation (07 D48) | — | Revisit at curriculum expansion |
| Growth could show Needs More Practice beside chain rows that all read "Correct in DEIXEN" (a skill with `NEEDS_REINFORCEMENT` keeps its state) | CLOSED — a Coach note on Growth says why (`coach.growth.*`; Build Spec §7C item 8; 07 D61) | Claude (D29); Karim may change the words | Session 8 |
| Learning touchpoint has no Coach note on the lesson page (no approved Coach text for it; served by the recommended lesson, the lesson, its next steps and the escalation offer — Build Spec §7C item 9) | NOTED — learner-test watch point (07 D61) | Karim | Re-test (07 D69, F-11) — the Phase 5 learner test is done (07 D67) |
| Build step 5 (Coach: explanations beside verified output, the escalation offer, the Growth note) | CLOSED — merged, tag `step-5-coach`, 1070 unit/component + 187 browser tests (07 D62) | — | Build steps 6–7 |
| The escalation offer at a bypass filing (app I-22) | CLOSED — kept as built per §7C item 7; written into §7C item 6 (07 D62) | Claude (D29); Karim may reverse | — |
| A learner returning to practice after an assessment can meet the offer at once with a high count (assessment errors count, §7C item 7) | NOTED — learner-test watch point (07 D62) | Karim | Re-test (07 D69, F-11) — the Phase 5 learner test is done (07 D67) |
| Scrolling notes block (1024–1440): keyboard and screen-reader behaviour; the offer below the fold in the 320 px phone drawer | CLOSED as rules — Build Spec §7D items 3–4 (07 D63): a named region while it scrolls; the drawer opens on the newest notes | Claude (D29) | Session 9 builds and tests it |
| Build steps 6 and 7 (session 9) | CLOSED — step 6 tag `step-6-check`; step 7 complete on its branch, merged and tagged `step-7-pass` in session 9B (07 D64) | — | Karim's learner test |
| Session 9B: merge and tag build step 7 | CLOSED — `main` = tag `step-7-pass` = `3fdb342`; only the test name, a comment, a message and the app docs changed; every build step done (07 D65) | — | — |
| 9B's own final runs (1070 / 268, slow test 2.1 s) are in its report, not in T12 (T12 keeps session 9's runs) | NOTED — not blocking: 9B changed no code or check (07 D65) | Claude Code | Next session records its runs in T12 |
| Karim's learner test — the Phase 5 gate (07 D29 item 5) | CLOSED — Phase 5 closed by Karim (07 D67); findings carried into the detour | Karim | — |
| Learner-test findings: lessons and Ghost Mode too hard for a beginner; training lines look alike right or wrong (`RF`) | CARRIED — every note became a Step 2 row and was placed by Step 3; answered in the Freeze (07 D69: F-02 training-line roles, F-03 marker, F-05 continuity, F-08 lessons and orientation, F-09 field annotations); results with no reason recorded stay open to the re-test (S2-17–S2-20, F-11) | Karim | Landing times in 07 D69 (c) |
| Practice booking reported lost while moving between commands (exact steps unknown) | CLOSED — Prompt 0, 2026-10-02: classification (b). No path loses the booking where the Build Spec (§7A item 1, §7B item 12) says the run continues; in six paths a practice button correctly starts a new, empty booking without saying so on screen — the three most likely to match Karim's report are reached when the app itself (Flight Deck, Learning area, escalation offer) sends the learner back to a lesson whose step is already done in this run. Not fixed now (07 D67) | — | Carried into detour Step 2 as learner-test input |
| Detour between Phase 5 and Phase 6 (07 D68) | CLOSED — Karim, 2026-10-02; Execution Plan §3, §5, §7 and 00 updated. Steps 1–3 done 2026-10-03 | Karim | Before-Step-4 tasks, Prompt 7, then step 4 |
| Phase 5 snapshot | DONE 2026-10-02 — annotated tag `phase-5-final` at `3fdb342429dc99ebf8268bad0da3075eacbd40a7` (local only, no remote), after typecheck, 1070/1070 unit tests, build and 268/268 browser tests passed | — | Step 1's target code (07 D68) |
| Running the browser tests rewrites 209 tracked files in `deixen-app` `docs/a11y` and `docs/screens` (the random booking reference); restored before tagging | CLOSED 2026-10-04 — F-19 landed: merged into `main` = `c093d5edd9b87b4ac232638b0e0c9b3ecb764abb` (not tagged); the first run had rewritten 205 files, not 209; a fixed locator source and time zone, screenshots taken at rest and written only beyond a measured tolerance; app I-25 closed; repeated runs leave `docs/screens` and `docs/a11y` untouched (07 D72) | Claude (D29) | — |
| Before-Step-4 task 2: F-02, a role for every training line (07 D69 (c) item 1) | CLOSED 2026-10-04 — F-02 landed: merged into `main` = `b5c66e527b159ae60b4539cf384293215cec9094` (not tagged); role from the recorded result, never from the key; stored-element lines take their creator's role; 1146 unit/component, 271 browser (07 D73) | Claude (D29) | Step 4 presents the roles (07 D69 (b)) |
| Step 4 executor role: Plan §2 says Claude Code implements approved specifications; for Step 4, the Freeze recorded in 07 is the approved specification | CLOSED — Karim, 2026-10-03: step 4 runs in Claude Code, Opus 5.5, Max effort, on a separate branch in `deixen-app` (07 D69, open item S3-06); no role change | Karim | — |
| Prompt 7 (Design Exploration Skill build) has no recorded authorization | CLOSED — authorized by Karim, 2026-10-03 (07 D70) | Karim | Runs after the before-Step-4 tasks |
| Package v1.8 §14 items 8–10: `tokens.css` and the content files in Step 4's scope; the untested parts of the learner test; the package review was not run in a fresh session | CLOSED 2026-10-03 — item 8 settled by the Freeze (07 D69: `tokens.css` not edited by step 4; content changes kept identical in both copies, F-21); item 9 carried into the re-test (F-11); item 10 history (Karim accepted the review result and proceeded) | Karim | — |
| The detour's Freeze Package (step 3) | CLOSED — accepted by Karim 2026-10-03 with his changes; the Freeze, design scope and landing times recorded verbatim (07 D69); the record checked against the accepted text (match) | Karim | Before-Step-4 tasks (07 D69 (c)) |
| Freeze open items (07 D69): S1-37 storage reset (closed — keep the wipe, F-15 b); S2-03 Flight Deck notes (closed — none); S3-06 who runs step 4 (closed, row above); S2-13 red for wrong entries (decided for now: `tokens.css` unchanged; open again after the re-test); S2-17–S2-20 results with no reason recorded (open — re-test); S2-24 reversing D33 (open — Karim, once a verified undo exists); S2-28/S2-74 Ghost scripts (open — Karim, before the first Phase 6 Ghost script); S3-03 master `CLAUDE.md` = app copy (closed 2026-10-03 — done, row below); S3-08 presentation of later learning changes (open — re-test) | As listed; 07 D69 is the record | Karim | Each as listed |
| Master `CLAUDE.md` in `DEIXEN-KNOWLEDGE` differs from the `deixen-app` copy in the §4 design-path line (S3-03) | CLOSED 2026-10-03 — decided by Karim (07 D69); done: Karim copied the app's `CLAUDE.md` over the master and uploaded it; GitHub main (commit 381998c) changes only that line, which now reads `../DEIXEN-KNOWLEDGE/design/phase4/` | Karim | — |
| Learner re-test (07 D69, F-11) | OPEN — after step 4 or at the start of Phase 6, Karim's choice; not a gate | Karim | Karim chooses the point and the learner |
| Constitution §5 repository address (`deixenlabs/DEIXEN-KNOWLEDGE`) | CLOSED — decided by Karim 2026-10-03 (07 D71); Amendment Record updated | Karim | — |
| The copy of the Constitution in the claude.ai Project's instructions still shows the old §5 address | OPEN — not blocking: the repository file counts (Constitution §5 item 4) | Karim | Karim edits the Project instructions |
| Sync incident 2026-10-03: an upload at 14:25 replaced 07 and 13 with copies of 2026-10-02 | CLOSED — restored from GitHub history and re-uploaded at 15:27; cause (old copies loose in `Downloads\`) removed by Karim | Karim | Upload only from the knowledge folder |
| Claude cannot push to `deixenlabs/DEIXEN-KNOWLEDGE` (no GitHub App installation) | NOTED — not blocking; Karim uploads every change | Karim | Optional: install the Claude GitHub App |
| Reduced motion keeps Ghost Mode's 1.2 s hold between displays (app I-23) | CLOSED — `tokens.css` unchanged; Build Spec §7B item 17 and §7D item 5 (d) corrected (07 D64) | Claude (D29); a change to `tokens.css` would be Karim's | — |
| English terms inside the approved Arabic content (app I-24) | CLOSED — allowed; Build Spec §7D item 6 (07 D64) | Claude (D29); Karim may change the content | Stays until the Arabic check of the re-test (07 D69, F-10, F-11) |
| Learner-test watch points from step 7: the scenario's folded title wrapping to four lines at 1024; taller lesson links on phones; the drawer opening at the newest note; notes added inside an open phone drawer not announced to a screen reader | NOTED (07 D64) | Karim | Re-test (07 D69, F-11) — the Phase 5 learner test is done (07 D67) |
| The unit suite's per-test time limit raised to 30 s (machine load) | NOTED — accepted; a real hang shows later (07 D64) | Claude Code | Watch for slow tests |
| Rules for build steps 6 and 7 (what the check proves; what "the accessibility baseline passes" means; localization and breakpoint passes; lockup B test; the end note in view) | CLOSED — Build Spec §7D (07 D63) | Claude (D29); Karim may reverse | Session 9 |
| Screen-reader use of the slice (how it is spoken; meaningful reading order) | OPEN — not provable by automated checks; accessibility trees saved for reading (07 D63; Build Spec §7D item 10) | Karim | Disclose; revisit before real learners other than Karim |
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

Absent artifacts (D19), the EgyptAir curriculum (D18), Design Execution (closed for the slice, 07 D42), and the Advanced backlog do not block the detour or Phase 6. (Before 2026-10-03 this line read "do not block Phase 5".)
