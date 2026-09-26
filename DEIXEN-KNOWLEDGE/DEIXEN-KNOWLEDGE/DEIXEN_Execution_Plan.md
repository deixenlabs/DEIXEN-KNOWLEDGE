---
name: DEIXEN Execution Plan
status: GOVERNING — approved by Karim on 2026-09-24 (07 Decision 16)
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
| 5. Build | Claude Code builds the slice (evening computer sessions); verification loop from 08 §26; Karim tests it as a learner | Working slice meeting 07's Definition of Done | Karim confirms the slice works | **Next** |
| 6. Expansion | Next lessons, Basic then Advanced — each chunk goes verify → spec → build → test | Growing curriculum | Karim, per chunk | Waiting |

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
sha256 manifest — approved by Karim 2026-09-26 (07 D45). No other new file without Karim's
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

**Phase 5 — Build (next, from 2026-09-26).** Phase 4 closed: Karim approved
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
next, step 2 part B (`SRCTCM`/`SRCTCR`, `TK`, `RF`, `ER`, `FXP`, `FQD`).

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
