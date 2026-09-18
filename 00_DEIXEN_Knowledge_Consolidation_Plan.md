---
name: AeroBridge Knowledge Consolidation Plan
status: Phases 1–8 complete (this pass) — see §6 for what remains open
owner: This document and its sibling reports below
---

# AeroBridge — Knowledge Consolidation Plan (Living Document)

## 0. What this pass actually did

Per the governing `AeroBridge_Master_Knowledge_Consolidation_Prompt.md`, this
pass DISCOVERED, INVENTORIED, MAPPED, EXTRACTED, RECONCILED, VERIFIED, and
CONSOLIDATED all 12 supplied knowledge files plus the supplied repository
archive. Every factual claim in the sibling reports was checked against either
(a) the literal text of a source document, or (b) the literal content of the
repository (code read directly, hashes computed directly, JSON inspected
directly) — not against memory, assumption, or general Amadeus/GDS knowledge.
Where something could not be verified this way, it is labeled accordingly
rather than presented as fact. See `11_AeroBridge_Consistency_Audit_and_Readiness_Review.md`
for the explicit verification checklist this pass satisfied.

## 1. Full Source Inventory

| # | File | Generation | Size | Language | Role |
|---|---|---|---|---|---|
| 1 | `AeroBridge_Master_Knowledge_Consolidation_Prompt.md` | Governing instruction | 1,647 lines | EN | The task specification for this entire pass. Not a knowledge source itself. |
| 2 | `PROJECT-20.md` | OLD (v9, earliest of the two OLD strata) | 128 lines | AR | Master index/roadmap for the OLD generation. Near word-for-word identical to the repository's own internal `Project.md`. |
| 3 | `SDD.md` | OLD (v9 stratum) | 89 lines | AR | System Design Document — tech stack, architecture, data contracts, Event Log design. |
| 4 | `AMADEUS_CURRICULUM.md` | OLD (v9 stratum) | 135 lines | AR | Full training curriculum (Basic/Advanced/Customer Service tracks), Ghost Mode & Speed Drills specs. |
| 5 | `COMMAND_REFERENCE.md` | OLD (v9 stratum, later code-audited) | 211 lines | AR | Code-derived Amadeus command reference. Governing prompt flagged this IMPORTANT. |
| 6 | `PRODUCT_STRATEGY_UX_ARCHITECTURE-1.md` | OLD (later stratum — explicitly archives the v9 UI/DESIGN docs) | 327 lines | AR | Product/UX strategy: personas, domains, principles, retention/metrics philosophy. |
| 7 | `DESIGN_SYSTEM_UI_BLUEPRINT.md` | OLD (Phase 2, successor to #6) | 128 lines | AR | Real visual tokens and screen blueprints, with documented historical Malik approval. |
| 8 | `DEVELOPMENT_RULES.md` | OLD (spans both strata) | 145 lines | AR/EN mixed | Process rules, AI dev loop, known tech-debt registry, cost-efficiency policy. |
| 9 | `AeroBridge_Master_Context.md` | NEW | 310 lines | EN | Product identity, vision, philosophy, 5-area IA, design direction. |
| 10 | `AeroBridge_Product_Architecture_and_Rules.md` | NEW | 364 lines | EN | IA detail, Terminal state skeleton, persistence architecture, vertical-slice rule. |
| 11 | `AeroBridge_Design_System_and_UX_Principles.md` | NEW | 409 lines | EN | Abstract design principles, accessibility baseline, anti-pattern list, arbitration outcome. |
| 12 | `AeroBridge_Decisions_and_Current_State.md` | NEW | 479 lines | EN | The control document — closed/open decisions, baseline hash, evidence contracts. |
| 13 | `AeroBridge_AI_Working_Rules.md` | NEW | 84 lines | EN | Multi-agent operating protocol. |
| 14 | `aerobridge-main.zip` | **Neither OLD nor NEW's own claimed current baseline — see §2** | 37 files | Code + AR/EN UI strings | The only implementation artifact supplied. |

**Two OLD-generation strata, not one.** `PROJECT-20.md`/`SDD.md`/`AMADEUS_CURRICULUM.md`/`COMMAND_REFERENCE.md` form an earlier "v9" checkpoint that itself named `DESIGN_SYSTEM.md` and `UI_GUIDELINES.md` as current. `PRODUCT_STRATEGY_UX_ARCHITECTURE-1.md` explicitly archives those two and the v9 phase plan, while re-affirming the tech stack, the engine, and the curriculum as non-negotiable reality. `DESIGN_SYSTEM_UI_BLUEPRINT.md` is that document's own named "Phase 2" successor. Treat these four+two as one continuous OLD lineage, not a flat pile.

**Artifacts referenced but NOT supplied to this pass** (their absence is load-bearing — see `01_AeroBridge_Repository_Reality_Report.md` §5 and `09_AeroBridge_Decisions_Requiring_Malik_Approval.md`):
- `AeroBridge_Pre_Phase3_Arbitration_and_Scope.md` (the historical pre-Phase 3 arbitration record; the 5 NEW docs only summarize its conclusions)
- `AeroBridge_Domain_SME_Validation_Brief.md` + the SME-01…SME-10 claim register
- `AeroBridge_Scenario_Bank_Architecture_Decision_Review.md` (referenced from inside the repo's own `event-bridge.js` code comments, §8A/§9)
- The actual NEW-generation React/TypeScript "Rebound Baseline" codebase itself (hash `5ac24787…`/`7ca3beb8…`) — what was supplied instead is a different, older, Vanilla-JS codebase (see next section)

## 2. The single most important finding of this pass

`AeroBridge_Decisions_and_Current_State.md` states, with an exact SHA-256, that
the current authoritative implementation is a React + TypeScript + pnpm
project (`client/src/pages/Home.tsx`, `client/src/index.css`, 85 files).
**Directly computing the SHA-256 of the supplied `aerobridge-main.zip`
(`73f1ca01…9950`) shows it matches neither that hash nor the earlier
"unavailable" one, and the archive contains 37 files of plain HTML/CSS/vanilla
JavaScript — no React, no TypeScript, no `package.json` anywhere.** Full
evidence and consequences are in `01_AeroBridge_Repository_Reality_Report.md`
§1. Every other file in this consolidation should be read with that fact in
mind: wherever a document below draws on "the repository," it is drawing on
this Vanilla-JS artifact, not on NEW's own current baseline, because the
latter was never provided.

## 3. Workflow phases and their status

| Phase | Status | Where the output lives |
|---|---|---|
| 1. Discover (read everything once, no conclusions) | Complete | This document, §1 |
| 2. Inventory (catalog every file's real scope) | Complete | This document, §1 |
| 3. Map (topic → source-file ownership, old and new) | Complete | `02_AeroBridge_Source_Reconciliation_Report.md` |
| 4. Extract (pull every fact, tagged by source) | Complete | Distributed across the canonical files (03–08) |
| 5. Reconcile (classify: superseded/recovered/conflict/open/etc.) | Complete | `02_AeroBridge_Source_Reconciliation_Report.md` |
| 6. Verify (repository + code-level checking) | Complete | `01_AeroBridge_Repository_Reality_Report.md` |
| 7. Decide / flag for Malik | Complete | `09_AeroBridge_Decisions_Requiring_Malik_Approval.md` |
| 8. Consolidate (final canonical files) | Complete | `03`–`08` (see §4 below) |
| 9. Pre-implementation readiness review | Complete | `11_AeroBridge_Consistency_Audit_and_Readiness_Review.md` |
| 10. Cross-audit | Complete | `11_AeroBridge_Consistency_Audit_and_Readiness_Review.md` |
| 11. Finalize | This document | — |

## 4. Final file map (single owner per concept, per the governing prompt's own rule)

| File | Owns |
|---|---|
| `01_AeroBridge_Repository_Reality_Report.md` | What the supplied code actually does, verified line-by-line where it mattered. Hash mismatch, architecture, per-command verification, tech-debt current status. |
| `02_AeroBridge_Source_Reconciliation_Report.md` | The OLD-vs-NEW comparison itself: topic by topic, what each generation said, and the classification. |
| `03_AeroBridge_Canonical_Product_and_Architecture.md` | Product identity, vision, personas, the 5-area IA, platform direction, navigation. |
| `04_AeroBridge_Canonical_Design_System.md` | Visual/UX principles (Design Positioning closed, Design Execution open), historical tokens, accessibility baseline, anti-patterns. |
| `05_AeroBridge_Canonical_Amadeus_Engine_Reference.md` | The full command set, RBD table, error taxonomy, and current-implementation status per command. |
| `06_AeroBridge_Canonical_Curriculum_and_Coach.md` | Lesson structure, both tracks, Ghost Mode, Speed Drills, and the Coach behavioral contract. |
| `07_AeroBridge_Canonical_Decisions_and_Current_State.md` | The single decisions log going forward — supersedes reading the original NEW `Decisions_and_Current_State.md` in isolation. |
| `08_AeroBridge_Canonical_AI_Working_Rules_and_Dev_Process.md` | How any AI (or Malik) should work on this project — multi-agent protocol plus the still-valid OLD process/testing/cost rules. |
| `09_AeroBridge_Decisions_Requiring_Malik_Approval.md` | Everything that is a judgment call, not a fact — waits on Malik. |
| `10_AeroBridge_New_Recommendations.md` | This pass's own suggestions, explicitly labeled as suggestions. |
| `11_AeroBridge_Consistency_Audit_and_Readiness_Review.md` | Final self-check against the governing prompt's own completion criteria. |

## 5. Legend used throughout the sibling reports

- **RECOVERED** — real OLD content that NEW does not contain and does not contradict; carried forward.
- **SUPERSEDED** — NEW consciously and explicitly replaces an OLD position (stated as a decision, not a silent drop).
- **CONFLICT** — OLD and NEW state genuinely incompatible things and neither has formally superseded the other.
- **OPEN** — neither generation has decided; flagged for Malik.
- **VERIFIED (code)** — checked directly against the supplied repository's source. This establishes implementation truth only — what the code does — never real-world Amadeus/GDS accuracy, which is a separate, still-pending domain/SME validation question regardless of how many times something has been code-verified.
- **VERIFIED (doc-only)** — internally consistent across documents but the repository doesn't cover it. Most notably: the React/TypeScript "Rebound Baseline" NEW's own documents describe. No such codebase was ever supplied to any pass of this work. Treat every detail about it (file count, hash, `pnpm` results, internal structure) as a claim those documents make, not as something this consolidation inspected — and do not let a future pass drift into writing about it as if it had been.
- **UNVERIFIABLE** — depends on one of the missing referenced artifacts (§1 above).
- **Design Positioning vs. Design Execution** — a distinction introduced during the post-consolidation correction pass (see `04_AeroBridge_Canonical_Design_System.md`): Positioning (professional/operational register) is closed and was never actually reopened; Execution (exact colors, type, identity) is the part genuinely open for the next design phase. Treat any older phrase like "visual direction: open" as referring to Execution only.

## 6. What remains genuinely open after this pass

Arabic/RTL and the PWA-sequencing question were resolved by Malik directly
after this pass and are no longer open — see
`07_AeroBridge_Canonical_Decisions_and_Current_State.md` Decisions 11 and
Platform Direction. What genuinely remains open, each detailed in
`09_AeroBridge_Decisions_Requiring_Malik_Approval.md`: the missing
NEW-baseline codebase (no React implementation has ever been supplied to
inspect — see the VERIFIED (doc-only) note above), the three missing
referenced artifacts, and several smaller items surfaced during repository
verification (the `ancillary.js` wiring gap, the `cleanRunsNeeded`
placeholder status, the live-echo numbering bug's fix timing). The
engine-strategy question (rebuild clean, reuse selectively, or hybrid) is
technical judgment delegated to Claude rather than a Malik-approval item —
see the recommendation in `10_AeroBridge_New_Recommendations.md`.
