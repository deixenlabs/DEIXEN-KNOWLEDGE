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
| Karim | Approves every phase gate, every new file, every decision reserved to the owner | — |
| Claude (Opus), project lead | Reviews, edits, synchronizes, verifies Amadeus behavior on the web, prepares briefs for Design and Code | Treat its own work as approved; present self-review as independent review |
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
| 3. Verification & readiness | See §4 | Verified Reference; Slice Build Spec; Design Brief; environment pack | Karim approves the pack | **In progress** (3.1, 3.2, 3.4 done) |
| 4. Design | Claude Design explores directions from the Design Brief; Karim chooses; the chosen direction is refined | Approved design | Karim approves direction | Waiting |
| 5. Build | Claude Code builds the slice (evening computer sessions); verification loop from 08 §26; Karim tests it as a learner | Working slice meeting 07's Definition of Done | Karim confirms the slice works | Waiting |
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
Karim 2026-09-25. No other new file without Karim's
approval (Roadmap rule carried forward: a new file needs a real, unowned
responsibility).

## 6. Working Rules for Every Phase

- A phase is closed only when its output is checked against its purpose
  (Constitution §20) and Karim approves the gate.
- Any material change to a file triggers an impact check on every file that
  depends on it (Constitution §15; dependency lines in file 00 §A10).
- Save tokens by narrowing context — focused specs, targeted edits, only the
  files a task needs — never by skipping verification or review.
- Each phase report to Karim is short and plain: what changed, what is still
  open, and what Karim needs to decide, with a clear recommendation.

## 7. Current Phase

Phase 2 complete (uploaded 2026-09-25). Phase 3: step 3.1 done (Verified Reference, second edition 2026-09-25); step 3.2 done — Karim approved Decisions 22 and 23 (2026-09-25). Decision 24 (`SRCTCM` step) approved, and creation of the three Phase 3 files approved (2026-09-25). 3.4 Design Brief written (`DEIXEN_Design_Brief.md`). Next: 3.3 Slice Build Spec, then 3.5 environment pack, then 3.6 readiness check.
