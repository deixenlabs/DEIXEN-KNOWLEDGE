---
name: DEIXEN Source-vs-Output Sufficiency Audit
status: HISTORICAL AUDIT RECORD (pre-Opus, 2026-09). Its readiness verdict describes that phase only; current state is in file 07. Original status — Audit pass. Four unambiguous factual recoveries were made directly in files 03 and 06 during this pass (listed below) — no redesign, no curriculum restructuring, no new decisions.
owns: Whether the current canonical set contains the strongest truthful version of DEIXEN's source knowledge, ahead of Opus review
---

> **Synchronization note — Phase 2, 2026-09-24.** Working name: **DEIXEN**
> (provisional; see `DEIXEN_Operating_Constitution.md` §1). "AeroBridge" survives
> only inside historical filenames and provenance statements. Owner: **Karim** —
> earlier project records used the name "Malik" for the same person; those
> references now read "Karim". Current project state and every decision:
> `07_DEIXEN_Canonical_Decisions_and_Current_State.md`. Amadeus facts: only
> claims marked VERIFIED under 07 Decision 12 may be taught as fact.

> **Historical record.** This audit's "READY FOR OPUS" verdict belongs to the
> ended pre-Opus phase. Its recoveries into files 03 and 06 still stand; its
> verdict and recommendations do not describe the current state.


# DEIXEN — Source-vs-Output Sufficiency Audit

The question this document answers is not "did every sentence survive" —
it's "if nobody ever opened the original OLD/NEW files again, would the
current canonical set still contain what a future implementation agent
actually needs." Sources were re-read directly for this pass, not recalled
from memory of the earlier consolidation. Four gaps found this way were
small, unambiguous, source-grounded factual restorations — not design
decisions — and were fixed directly in files 03 and 06 rather than only
listed, per this pass's own permission to make direct edits where the
correction is unambiguous. They're marked **RECOVERED THIS PASS** below
rather than left as open findings.

## Final Source-to-Output Matrix

| Source | Knowledge Area | Important Knowledge | Current Output Location | Status | Lost/Compressed? | Recover Before Opus? | Reason |
|---|---|---|---|---|---|---|---|
| PROJECT-20.md | Product | L1–L9 → job-title → skill-content mapping, with "guidance framework, not a certificate" caveat | `03` "Who this is actually for" | **RECOVERED THIS PASS** | Was compressed to a vague "implied job-title ladder" | Done | Concrete mechanism behind the core "job readiness" claim; a future Skill Graph pass needs this exact shape, not a vaguer restatement |
| PROJECT-20.md / PRODUCT_STRATEGY doc | Product | Named employers, high-pressure call-center framing, dual-competency principle | `03` | PRESERVED | No | — | Employers and dual-competency goal both present; call-center characterization added during this pass's recovery edit |
| SDD.md | Architecture / Evidence | Event Log's exact 4 logged fields (event type, command, result, timestamp) and the pure-engine-modules boundary | `03` Persistence Architecture | **RECOVERED THIS PASS** | Was absent entirely — only the general "Event Log" concept survived | Done | Concrete precedent for the still-pending evidence/state schema design; cheap to preserve, costly to rediscover later |
| SDD.md | Architecture | Vanilla JS / no-framework / static-hosting / pure-modules decisions | `01`, `03` (historical notes) | PRESERVED | No | — | Directly and repeatedly verified against actual code |
| AMADEUS_CURRICULUM.md | Curriculum | Ghost Mode exact JSON schema + text-only/no-audio constraint | `06` Ghost Mode | **RECOVERED THIS PASS** | Concept survived, exact schema and no-audio detail had been dropped | Done | A future implementer would otherwise re-derive field names from scratch and could easily add audio no one decided to include |
| AMADEUS_CURRICULUM.md | Curriculum | Speed Drills mechanic (sub-mode, CPM from existing Event Log timestamps, no new engine logic) | `06` Speed Drills | PRESERVED | No | — | Checked directly against source; this one held up despite being a flagged risk area |
| AMADEUS_CURRICULUM.md | Curriculum | Customer Service track's 5 specific lesson topics; lesson 5's Terminal+English hybrid nature; the Anger Meter's exact mechanic | `06` Customer Service Track | **RECOVERED THIS PASS** | Compressed to "5 lessons... Anger Meter... tied to Event Log" with no operational detail | Done | The Anger Meter and the Terminal/dialogue integration point are concrete, differentiating design features, not incidental detail |
| AMADEUS_CURRICULUM.md | Curriculum | L9/IROPS/Timatic command mapping; Saudi carrier IATA codes (SV/XY/F3); "Time-Pressure Tag" concept | `06` L9 Specialization | **RECOVERED THIS PASS** (mapping + codes); **HISTORICAL ONLY** (Time-Pressure Tag — source document never supplied, exact mechanic not responsibly reconstructable) | IATA codes and the tag concept were both absent | Codes: done. Tag: concept preserved, mechanic explicitly marked unrecoverable | Codes are trivial, free specificity. The tag mechanic can't be faithfully rebuilt without its source, but the underlying idea (time-pressure performance scenarios) is worth keeping as a direction |
| AMADEUS_CURRICULUM.md | Curriculum | Basic/Advanced applicability counts (17 Basic lessons, 2 of 11 Advanced fully usable, Future Expansion Backlog gating rule) | `06` | PRESERVED | No | — | Verified directly against source; ratios and the "never shown as available Practice content" rule both intact |
| AMADEUS_CURRICULUM.md | Curriculum | FQD/FXP historical naming corrections (not "FQ", not "FXP/FXX") | `05`, `06` | PRESERVED + REFINED | No | — | Carried forward, and this pass's earlier correction round fixed the label so it reads as implementation-consistency rather than an overclaimed domain re-verification |
| COMMAND_REFERENCE.md | Amadeus | Full 37-command set, RBD table, error taxonomy, all documented constraints | `05` | PRESERVED + REFINED | No | — | Individually verified against actual code, including one bug found already fixed and one additional affected function neither OLD document had caught |
| DEVELOPMENT_RULES.md | Engineering/QA | Known tech-debt registry (7 items), AI development/verification loop, integration testing checklist | `05`, `08` | PRESERVED + REFINED | No | — | All 7 items individually verified against code; current status corrected where the written record had gone stale |
| DESIGN_SYSTEM_UI_BLUEPRINT.md | UX/Design | "Continue where you left off" resume card (badge, ring animation, level name, "N of M" subtext, single Continue action) | `04` | PRESERVED | No | — | Checked directly; captured in full, generalized appropriately from the one worked example |
| DESIGN_SYSTEM_UI_BLUEPRINT.md | UX/Design | Real verified color tokens, typography, spacing/radius, shared shell structure | `04` | PRESERVED + REFINED | No | — | Preserved as historical evidence; also now correctly separated from the (still-open) Design Execution decision so it isn't mistaken for a locked default |
| PRODUCT_STRATEGY_UX_ARCHITECTURE-1.md | Product | UX/Product principles (Honesty before beauty, No Fabrication, Honest Scope, etc.) | `03`, `04` | PRESERVED | No | — | Present, though distributed across two files rather than listed together — see Should-Not-Recover note on this below |
| PRODUCT_STRATEGY_UX_ARCHITECTURE-1.md | Product | Retention-strategy rejection of streaks/manufactured urgency; no-invented-CPM-threshold rule | `06` (CPM rule), decisions ledger (streak non-trust-bearing) | PRESERVED | No | — | Both rules independently verified present |
| AeroBridge_Decisions_and_Current_State.md | Decisions | All 11 numbered decisions, evidence contracts, baseline-hash finding | `07` | PRESERVED + REFINED | No | — | Fully carried forward and subsequently corrected across two rounds (Positioning/Execution split, validation-status split) |
| AeroBridge_AI_Working_Rules.md | Process | Multi-agent protocol, decision-state vocabulary, Manus modes | `08` | PRESERVED | No | — | Verified present in full |
| *(cross-cutting)* | Domain | Real-world accuracy of any documented Amadeus command behavior | `05` (as code-verified only) | VERIFY / EXTERNAL VALIDATION | N/A — never available internally | External, not a recovery item | Already correctly tracked in `07` Decision 7; this audit doesn't change that status |

## ACTUAL KNOWLEDGE THAT FELL THROUGH THE CRACKS

All four items below were recovered directly during this pass (see the matrix). Listed here because the task calls for this section regardless of whether items were left open or already fixed — an empty list would misrepresent what was actually found.

| Item | Original source | Why it's valuable | Severity | Recovered before Opus? | Canonical destination |
|---|---|---|---|---|---|
| L1–L9 → job-title → skill mapping, with its "guidance framework, not a certificate" caveat | PROJECT-20.md | Concrete evidence behind the core job-readiness claim; directly needed by the future Skill Graph pass | **HIGH** | Yes | `03_DEIXEN_Canonical_Product_and_Architecture.md` |
| Event Log's 4 specific fields + pure-modules boundary | SDD.md | Free, proven starting shape for the still-pending evidence/state schema | **MEDIUM** | Yes | `03_DEIXEN_Canonical_Product_and_Architecture.md` |
| Customer Service track's 5 lesson topics, lesson 5's Terminal-hybrid nature, and the Anger Meter's exact mechanic | AMADEUS_CURRICULUM.md | Concrete, differentiating design features, not incidental color | **MEDIUM-HIGH** | Yes | `06_DEIXEN_Canonical_Curriculum_and_Coach.md` |
| Ghost Mode's exact JSON schema and text-only/no-audio constraint | AMADEUS_CURRICULUM.md | Prevents re-deriving field names from scratch and losing a specific, deliberate design constraint | **MEDIUM** | Yes | `06_DEIXEN_Canonical_Curriculum_and_Coach.md` |

Two smaller items were recovered alongside the above at essentially zero
cost (Saudi carrier IATA codes; the call-center characterization of the
target work environment) — **LOW** severity, folded into the same edits
rather than tracked as separate rows.

One item could not be responsibly recovered: the "Time-Pressure Tag"
mechanic referenced in AMADEUS_CURRICULUM.md traces to a design document
(`UI_GUIDELINES.md §8`) that was never supplied to any consolidation pass.
The underlying idea is preserved as a curriculum direction in `06`; the
exact mechanic is marked **HISTORICAL ONLY / possibly no longer current**
rather than guessed at.

## What Should NOT Be Recovered

- **The full text of `UI_GUIDELINES.md` and `DESIGN_SYSTEM.md` (the original
  v9-era design documents).** OLD's own later strategy document
  (`PRODUCT_STRATEGY_UX_ARCHITECTURE-1.md`) explicitly archived these
  itself, before this consolidation ever began — their design conclusions
  were superseded by `DESIGN_SYSTEM_UI_BLUEPRINT.md`'s real, built, verified
  tokens. Recovering their specific visual specs now would reintroduce a
  direction OLD's own process had already moved past, and would muddy the
  now-correctly-separated Design Positioning/Execution split. Where a
  concept from them still had live value (the Time-Pressure Tag idea), it's
  preserved above; the rest is intentionally superseded.
- **PROJECT.md's original v9 phase list and 7-screen structure.** Superseded
  by the current five-area IA, itself a closed decision. Keeping the old
  phase numbering around invites confusion with the current Vertical Slice
  boundary, which uses different sequencing entirely.
- **The specific "screen 3" / fixed-screen-number references** in
  AMADEUS_CURRICULUM.md (e.g., Speed Drills living "on screen 3"). The
  underlying placement (within Practice) is preserved; the numbering
  scheme itself belongs to an IA that no longer applies.
- **Detailed re-litigation of the RT-retrieval bug's original "still open"
  framing.** Already correctly handled: the current engine reference
  reports it as fixed, verified directly against code, with the historical
  framing noted as stale documentation rather than restored as current
  status.
- **The historical PWA-first mandate as a re-adopted requirement.** Already
  correctly treated as intentionally superseded, with Karim's explicit
  reconfirmation on record. Re-surfacing it as live scope would casually
  reopen a closed decision without new evidence.

## Readiness Verdict

**READY FOR OPUS WITH NON-BLOCKING RECOVERY NOTES.**

Not a clean "no gaps found" verdict — four genuine, material gaps were
found, and the standard set for this audit explicitly forbids calling
something ready just because an omission is technically non-blocking. What
justifies this verdict instead is that all four gaps were the kind
explicitly permitted to be fixed directly within this same pass (unambiguous
factual restorations, not decisions), and they were fixed, not merely
noted. What remains — the Time-Pressure Tag's exact mechanic, and the
ordinary SME/domain validation dependency already tracked elsewhere — are
genuinely HISTORICAL ONLY or EXTERNAL VALIDATION items respectively, neither
of which this audit (or Opus) can resolve by more document work.

## Final Recommendation

**SHOULD WE MOVE TO OPUS NOW? YES.**

**Why:** the material knowledge gaps this pass specifically went looking for
— the ones flagged as likely risk areas — were real, were found by direct
source comparison rather than assumption, and were corrected in place. The
canonical set now contains the L1–L9 job mapping, the Event Log's concrete
shape, the Customer Service track's actual content, and Ghost Mode's actual
schema — none of which existed in the output set an hour ago.

**Blocking issues:** none.

**Non-blocking issues:** the Time-Pressure Tag mechanic remains unrecovered
because its source document doesn't exist in this workspace — flagged
honestly rather than invented.

**Recovery required before Opus:** none remaining — the four material items
found were recovered as part of this same pass.

**Knowledge that should stay historical/deferred:** `UI_GUIDELINES.md`/
`DESIGN_SYSTEM.md`'s specific visual specs, PROJECT.md's original phase
list, and old fixed-screen-number references — all listed above with
reasoning, not just asserted.

**Remaining external validation:** unchanged from the existing Decision
Resolution Register — command-level Amadeus accuracy, whole-workflow
validity of the frozen slice, and the acceptability of the engine's built-in
simplifications all still require an actual domain expert. No amount of
further document work substitutes for that, and this audit does not
pretend otherwise.

## Final Line

**READY FOR OPUS WITH NON-BLOCKING RECOVERY NOTES.**
