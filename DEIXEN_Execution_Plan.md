---
name: DEIXEN Execution Plan
status: GOVERNING — approved by Karim on 2026-09-24 (07 Decision 16); the four-step detour between Phase 5 and Phase 6 inserted by Karim on 2026-10-02 (07 Decision 68); the detour's Freeze accepted and recorded, and Prompt 7 authorized, 2026-10-03 (07 Decisions 69–70); before-Step-4 tasks 1 (F-19), 2 (F-02), 3 (F-03), 4 (F-05) and 5 (F-04 (A)(B)) landed, 2026-10-04 (07 Decisions 72–76); Karim's owner decisions and an identity exploration inserted before step 4, 2026-10-05 (07 Decisions 77–78)
owns: Work sequence, phases, gates, current phase, and role assignments
does not own: how work is performed (Operating Constitution); decisions (07); Amadeus truth (Amadeus Verified Reference)
replaces: DEIXEN_MASTER_PRE_OPUS_FOUNDATION_PREPARATION_PLAN-1.md and DEIXEN_MASTER_EXECUTION_ROADMAP.md (both historical from 2026-09-24)
---

# DEIXEN — Execution Plan

## 1. Goal

Build DEIXEN into a platform that teaches professional Amadeus — Basic and
Advanced — to a beginner, to the level the Saudi/Gulf job market expects,
with Terminal behavior that matches real Amadeus (07 Decision 18). Start with
one complete, verified vertical slice; expand only after it works for a real
learner.

## 2. Roles (07 Decision 17)

| Who | Does | Does not |
|---|---|---|
| Karim | Decides what is reserved to him (07 D29): identity, scope, name/brand/visual direction, money/legal/publishing, governance changes, and confirming the slice works as a learner | — |
| Claude (Opus), project lead | Reviews, edits, synchronizes, verifies Amadeus behavior on the web, prepares briefs for Design and Code; decides everything not reserved to Karim, records it in 07 "by delegation (D29)" and reports briefly | Decide a reserved matter; present self-review as independent review; lower the Verification Standard |
| Claude Design | Explores and executes design within the Design Brief | Decide final visual direction |
| Claude Code | Implements the approved specifications | Add scope, invent Amadeus behavior, reinterpret decisions |

No other AI tool has a role. No gate in this plan requires a separate
independent review (waived by Karim).

## 3. Phases

| Phase | What happens | Output | Gate | Status |
|---|---|---|---|---|
| 0. Source lock | Read the Project and repository; decide which copies count | Corpus inventory | — | **Done** 2026-09-24 |
| 1. Review (read-only) | Look for contradictions, gaps, stale statements | 16 findings (file 13 §2) | Karim reviews findings | **Done** 2026-09-24 |
| 2. Synchronization | Apply decisions 12–21; fix contradictions; migrate names; mark every file's status | Updated corpus; Corpus Map (file 00) | Karim uploads the files | **Done** 2026-09-25 |
| 3. Verification & readiness | See §4 | Verified Reference; Slice Build Spec; Design Brief; environment pack | Karim approves the pack | **Done** 2026-09-25 (07 D28) |
| 4. Design | Claude Design explores directions from the Design Brief; Karim chooses; the chosen direction is refined | Approved design | Karim approves direction | **Done** 2026-09-26 (07 D42) |
| 5. Build | Claude Code builds the slice (evening computer sessions); verification loop from 08 §26; Karim tests it as a learner | Working slice meeting 07's Definition of Done | Karim confirms the slice works | **Done** 2026-10-02 (07 D67) |
| Detour step 1. External Engine / Open-Source Investigation | Opus 5.5, in a clean session, investigates whether any open-source implementation, architectural idea, dataset, or evidence deserves to affect the engine or the way it is expanded in Phase 6; target code: tag `phase-5-final` at `3fdb342429dc99ebf8268bad0da3075eacbd40a7` in `deixen-app`; modifies nothing | Technical Recommendation — advisory, not a gate, not a formal independent review; delivered in the chat reply only, with a short "Design-facing requirements" section (a secondary lens, not a selection criterion) | none stated (advisory; binds only if Karim explicitly accepts it) | **Done** 2026-10-03 (handoff block used by Steps 2–3) |
| Detour step 2. Learning Design + Learning Experience Review | Reviews learning design and learning experience, with Karim's learner-test record (07 D67) as input; modifies nothing | Learning Decision — a recommendation within its own domain | none stated (binds only if Karim explicitly accepts it) | **Done** 2026-10-03 (handoff block used by Step 3) |
| Detour step 3. Synthesize & Freeze Decisions | Synthesizes engine, learning and product constraints; modifies nothing | Freeze Package proposal — the Freeze (locked decisions, listed open items, the procedure for changing them), the design scope, when each accepted change must land, the ledger, the requirements and candidates for step 4, the preserve list, the coverage | Karim explicitly accepts the Freeze Package; its Freeze, design scope and landing times are then recorded in 07, and step 4 starts only after that record exists | **Done** 2026-10-03 — Karim accepted the Freeze Package; recorded in 07 D69 |
| Identity exploration (before step 4; 07 D78) | Explores the whole visual identity with the Design Exploration Skill in open identity mode — dark as the primary direction, red also for errors (07 D77); the wordmark only if the question names it; product truth, engine output, learning logic and content, colour jobs, accessibility and both languages stay closed; modifies no repository and no canonical file | Candidate directions and Karim's comparison — proposals only | Karim chooses a direction (or none); his choice is recorded in 07 and restates step 4's design scope | Next |
| Detour step 4. Design Improvement Round (UX / UI / learning surfaces / Terminal experience) → Design Verification | Improves and verifies the design inside the design scope recorded in 07, in isolation and reversibly; anything outside its authority goes through the return path (one round, Karim decides) | Its verified design changes (isolated until accepted; "no material design change" is a valid result) plus the Detour Closing Report | Karim accepts the Detour Closing Report (accepts or rejects the design changes, schedules the remaining implementation tasks, starts Phase 6) | Waiting — the before-Step-4 tasks are done (07 D69 (c); D72–D76); base tagged `step4-base`; Prompt 7 done and the Skill accepted (07 D70, D78); waits for the identity exploration and Karim's recorded choice (07 D78) |
| 6. Expansion | Next lessons, Basic then Advanced — each chunk goes verify → spec → build → test | Growing curriculum | Karim, per chunk | Waiting |

Detour steps 1–4 run under the shared Detour Charter (v1.8), embedded in each step's prompt (not a file); each is started separately by Karim and stops after its own deliverable (07 D68). Between step 3 and step 4, Prompt 7 builds the DEIXEN Design Exploration Skill — an auxiliary tooling action, not a fifth step and not a gate; Karim accepts the Skill before step 4 is prepared (07 D70) — accepted 2026-10-05 (07 D78). Before step 4, an identity exploration runs with that Skill (07 D78) — not a fifth step and not a gate; step 4 is prepared after Karim records his chosen direction and step 4's restated scope.

## 4. Phase 3 in Detail

**3.1 Verify the slice's Amadeus behavior (07 Decision 12).** Start with the
slice path and everything it depends on: `AN`, `SS`, `FQD`, `FXP`, and every
prerequisite a real pricing needs (for example, whether a passenger name must
exist first). Record results in `DEIXEN_Amadeus_Verified_Reference.md`
(approved, Decision 15). Report plainly what could not be verified and why.
No weak source is used to fill a gap.

**3.2 Karim decision gate.** Two decisions, each with evidence and a clear
recommendation: (a) whether the slice path needs adjusting (Decision 20);
(b) how the Terminal handles output formats or error texts that cannot be
verified publicly (Decision 13, open item).

**3.3 Slice Build Spec.** One file that gathers, for the slice only, the
requirements now spread across 03, 04, 06, 07, the Learning Design
Specification, and the Learning Experience Architecture — plus the concrete
evidence/state design (the delegated schema, and the open Event Log
questions). Its purpose is that Claude Code reads one focused specification,
not about 10,000 lines of foundation documents. It cites its sources; it
adds no new decisions.

**3.4 Design Brief.** One file for Claude Design: what is Frozen (product
structure, Terminal centrality, contracts, accessibility, breakpoints,
Arabic/English RTL/LTR), what is Directional, and what is Open (colors, type,
identity, light vs. dark).

**3.5 Execution environment pack.** Before any design or code session:
the Claude Code instruction file (`CLAUDE.md`), repository layout, test and
verification checklist, and any Claude skills worth creating — each justified
by a concrete need, not added for completeness. Designed so every session
starts with the minimum context it needs.

**3.6 Readiness check** (Constitution §19): authority clear, files consistent,
every Amadeus behavior in the slice VERIFIED or explicitly handled per 3.2.

## 5. New Files

Approved: `DEIXEN_Amadeus_Verified_Reference.md` (Decision 15); the Slice
Build Spec, the Design Brief (`DEIXEN_Design_Brief.md`), and the Claude Code
environment files (`CLAUDE.md` and repository scaffolding) — approved by
Karim 2026-09-25; `tokens.css`, the one token file in the code repository —
approved by Karim 2026-09-26 (07 D42); `design/phase4/` in this
repository — a read-only copy of the approved boards, `tokens.css` and a
sha256 manifest — approved by Karim 2026-09-26 (07 D45); `DEIXEN_Detour_Prompt_Package_v1.8.md` in this
repository — approved by Karim 2026-10-02 as a review and transport
artifact with no authority: 07 Decision 68 governs, and the package is the
working copy of the detour's prompts. No other new file without Karim's
approval (Roadmap rule carried forward: a new file needs a real, unowned
responsibility).

## 6. Working Rules for Every Phase

- A phase is closed only when its output is checked against its purpose
  (Constitution §20) and the gate is approved — by Karim when the gate
  contains a matter reserved to him (07 D29: e.g. the design direction, the
  learner test of Phase 5), otherwise by Claude under D29 with a short report.
- Any material change to a file triggers an impact check on every file that
  depends on it (Constitution §15; dependency lines in file 00 §A10).
- Save tokens by narrowing context — focused specs, targeted edits, only the
  files a task needs — never by skipping verification or review.
- Each phase report to Karim is short and plain: what changed, what is still
  open, and what Karim needs to decide, with a clear recommendation.

## 7. Current Phase

**The detour before Phase 6 — under way (07 Decision 68).** Phase 5 closed
on 2026-10-02: Karim ran his learner test and closed the gate (07 D67); his
findings go into the detour as input to Step 2. The Phase 5 snapshot is
the annotated tag `phase-5-final` at `3fdb342` in `deixen-app` (local; 13).
Four steps (§3), each started separately by Karim. Steps 1–3 are done
(2026-10-02/03); Karim accepted the Freeze Package, recorded as 07 D69 —
the Freeze, step 4's design scope and when each accepted change lands.
The before-Step-4 tasks of 07 D69 (c) are all done, each a Claude Code task
started by Karim, the first from `phase-5-final` and each later one from
`main` after the previous had landed: F-19 (07 D72), F-02 (07 D73), F-03
(07 D74), F-05 (07 D75), and F-04 (A)(B) done 2026-10-04, 07 D76, `main` =
`8f9c355`; F-20 done by Karim. Karim tagged the base `step4-base` (2026-10-05); Prompt 7 built the Design Exploration Skill and Karim accepted it (07 D70, D78). On 2026-10-05 Karim recorded seven owner decisions (07 D77; among them: the primary visual direction is dark, and red also marks errors) and chose to explore the identity before step 4 (07 D78). Next, in order: the identity exploration (a fresh session, Opus 5.5, Max, with the Skill v1.1 — Claude Code on Karim's computer, outside both repositories); Karim chooses a direction and it is recorded in 07 with step 4's restated scope; then step 4 is prepared and run (Claude
Code, Opus 5.5, Max, on a separate branch — 07 D69, S3-06). The learner
re-test runs after step 4 or at the start of Phase 6, as Karim chooses; it
is not a gate (07 D69, F-11). Phase 6 starts after Karim accepts the
Detour Closing Report.

**Phase 5 — Build (2026-09-26 to 2026-10-02; closed, 07 D67).** Phase 4 closed: Karim approved
the gate (07 Decision 42) — the refined direction A "Margin", the
typefaces, header lockup B, and `tokens.css`. Standing delegation: 07
Decision 29.

Ready for the first Claude Code session: `DEIXEN_Slice_Build_Spec.md`
(§2 now names the approved design and the boards to read), `CLAUDE.md`, the
content files (interface words added as `ui.*` keys, 07 D43; `AN` header
number rule, 07 D44), `tokens.css`, the approved boards in `design/phase4/`
(07 D45), and the Verified Reference. Phase 5 runs
as its row in §3 says: Claude Code builds in evening computer sessions,
following `CLAUDE.md` §7 (build order) and 08 §26 (verification loop);
Claude (project lead) prepares each session and checks its result; the
gate is Karim's own test as a learner (07 D29 item 5).

Build progress: step 1 (evidence store) locked 2026-09-26 (07 D46); step 2
part A (engine core, `AN`, `SS`, `NM`, `AP`) locked 2026-09-26 (07 D48);
next, step 2 part B (`SRCTCM`/`SRCTCR`, `TK`, `RF`, `ER`, `FXP`, `FQD`),
prepared 2026-09-26 (07 D49; Build Spec §6A); step 2 locked 2026-09-28 (07 D50–D51, tag `step-2b-engine`); step 3 (bridge) prepared 2026-09-28 (07 D52; Build Spec §7A) and locked the same day (07 D53, tag `step-3-bridge`); step 4 prepared 2026-09-28 (07 D54; Build Spec §7B) and split into 4A (app shell and Terminal practice) and 4B (the other seven states); step 4A built in session 5 and locked 2026-09-29 (07 D55, tag `step-4a-terminal`); leaving a running assessment or scenario inside the app decided (07 D56); the rules for 4B written (07 D57; Build Spec §7B items 11–15); step 4B-1 (Flight Deck, Learning, Ghost Mode, Growth, Reset, Scope Disclosure) built in session 6 and checked 2026-09-30 (07 D58; merged and tagged `step-4b1-screens` at the start of session 7); the rules for 4B-2 written (07 D59; Build Spec §7B items 19–20); session 7 merged 4B-1 (tag `step-4b1-screens`) and built 4B-2 (07 D60, tag `step-4b2-screens`) — build step 4 complete; the rules for build step 5 (Coach) written 2026-09-30 (07 D61; Build Spec §7C); session 8 built step 5, checked and locked 2026-10-01 (07 D62, tag `step-5-coach`); the rules for build steps 6 and 7 written 2026-10-01 (07 D63; Build Spec §7D); session 9 ran both, checked 2026-10-02 (07 D64; tag `step-6-check`; step 7 merged and tagged `step-7-pass` in session 9B) — every build step done; then Karim's learner test (the Phase 5 gate), run on 2026-10-02, and Phase 5 closed (07 D67).

Phase 4 record (2026-09-25/26): steps 1–4 — three directions, Karim chose
A (07 D31) and ruled that the Terminal shows Amadeus only (07 D30);
delegated rules D32–D36. Step 5 — refinement of A (Part 1: AI-look audit,
identity, one `tokens.css`, eight states EN; Part 2: Arabic, all
breakpoints, phone menu; session 3: last fixes). Step 6 — Claude's check
(self-review): passes the Brief and Build Spec (07 D41; session 3 checked
2026-09-26). Step 7 — gate approved (07 D42).

History: Phase 2 complete 2026-09-25. Phase 3: 3.1 Verified Reference
(editions 1–3); 3.2 Decisions 22–24; 3.3 Build Spec (D25, D26); 3.4 Design
Brief; 3.5 `CLAUDE.md` (code in `deixen-app` beside `DEIXEN-KNOWLEDGE`);
G1–G3; Decision 27 applied; 3.6 passed; gate approved (D28), all 2026-09-25.
