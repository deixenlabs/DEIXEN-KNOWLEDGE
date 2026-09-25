---
name: DEIXEN Knowledge Consolidation Plan & Corpus Map
status: CURRENT (Part A, 2026-09-24) + HISTORICAL (Part B, the 2026-09-03 consolidation pass)
owns: The Corpus Map — every project file's role, authority, and dependencies; the list of absent artifacts; consolidation methodology (per Operating Constitution §3)
---

# DEIXEN — Knowledge Consolidation Plan & Corpus Map

> **Synchronization note — Phase 2, 2026-09-24.** Working name: **DEIXEN**
> (provisional; see `DEIXEN_Operating_Constitution.md` §1). "AeroBridge" survives
> only inside historical filenames and provenance statements. Owner: **Karim** —
> earlier project records used the name "Malik" for the same person; those
> references now read "Karim". Current project state and every decision:
> `07_DEIXEN_Canonical_Decisions_and_Current_State.md`. Amadeus facts: only
> claims marked VERIFIED under 07 Decision 12 may be taught as fact.

# Part A — Corpus Map (current as of 2026-09-24)

This map says what each file is for and how much authority it carries. When
two files disagree, the one with higher authority wins (07 "Document
Authority"); a file's category here is not changed by its filename, its
length, or the word "Canonical" in its title.

## A1. Governing — how work is done and in what order

| File | Role | Status |
|---|---|---|
| `DEIXEN_Operating_Constitution.md` | Working method, authority, evidence discipline, roles | Approved by Karim; §9 and a §8 clarification amended 2026-09-24 |
| `DEIXEN_Execution_Plan.md` | Phases, gates, current phase | Approved by Karim, 2026-09-24 |
| `08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process.md` | AI working rules, verification loop, dev process | Canonical (07 D16); renamed from `…_UNIFIED_PROPOSED.md` |

## A2. Canonical project truth

| File | Owns | Depends on |
|---|---|---|
| `07_DEIXEN_Canonical_Decisions_and_Current_State.md` | Every decision; current state; Verification Standard (D12) | Constitution, Plan |
| `13_DEIXEN_Decision_Resolution_Register.md` | Status of every decision/open item; Phase 1 findings | 07 |
| `03_DEIXEN_Canonical_Product_and_Architecture.md` | Product identity, 5 areas, platform, persistence, vertical-slice rule | 07 |
| `04_DEIXEN_Canonical_Design_System.md` | Design principles, accessibility, anti-patterns; Design Execution open | 03, 07 |
| `06_DEIXEN_Canonical_Curriculum_and_Coach.md` | Curriculum goal and historical baseline; Coach contract; Ghost Mode; Speed Drills | 07 (D12, D13, D18), Verified Reference |

## A3. Amadeus domain truth, and planned files

| File | Owns / will own | Status |
|---|---|---|
| `DEIXEN_Amadeus_Verified_Reference.md` | The only authority for real Amadeus behavior (07 D15) | Current — third edition 2026-09-25 (screen layouts V-14–V-18), amended at the readiness check (U-12–U-14); approved in the Phase 3 gate (07 D28) |
| `DEIXEN_Slice_Build_Spec.md` | The build specification for the first-build slice; the evidence/state schema | Approved 2026-09-25 (07 D25, D26); G1–G3 closed; D27 (K5–K6) applied; K7 approved (07 D28) |
| `deixen-app/content/` — `data/slice.json`, `en/text.json`, `ar/text.json` | All slice wording and fictional data: lessons, Ghost Mode scripts, task, scenario, feedback/hints, training messages, Coach explanations, contract texts, Scope Disclosure (Build Spec G2–G3) | Approved 2026-09-25 with the readiness-check fixes (07 D28). Reading copy: `DEIXEN_Slice_Content_Review.md` (not a project file). Lives in the code repository's approved `content/` folder (CLAUDE.md §5), not in this repository; depends on the Verified Reference and the Build Spec |
| `DEIXEN_Design_Brief.md` | What Claude Design receives for Phase 4 | Approved 2026-09-25 (07 D28) — input to Phase 4 |
| `CLAUDE.md` | Claude Code instructions, repository layout, verification checklist (Execution Plan 3.5) | Approved 2026-09-25 (07 D26), D27 applied — master copy; moves into the code repository `deixen-app` at build start |

## A4. Draft authority — learning foundation

| File | Owns | Status |
|---|---|---|
| `DEIXEN_Learning_Design_Specification.md` | How DEIXEN teaches: skill states, assistance, feedback, assessment, evidence | Draft; reading rule added 2026-09-24; binding for the slice only through the Phase 3 Slice Build Spec |
| `DEIXEN_Learning_Experience_Architecture.md` | How the learning system becomes the learner's experience | Same as above |

## A5. Historical implementation record

| File | What it is |
|---|---|
| `05_DEIXEN_Canonical_Amadeus_Engine_Reference.md` | What the old (unavailable) engine did. Not a spec, not Amadeus truth (07 D14) |

## A6. Supporting references — consulted, never governing (07 D16)

`DEIXEN_Prompt_Engineering_and_Governance_UNIFIED_PROPOSED.md`,
`UNIVERSAL_AI_SESSION_HANDOFF_PROTOCOL.md`,
`DEIXEN_AI_Operating_Environment___Final_Extension_Ecosystem___Acceptance_Review.md`,
and `AeroBridge_Amadeus_Master_Knowledge_Constitution_and_Research_Prompt-3__1_.md`
(research methodology; Decision 12 overrides it where they differ).

## A7. Historical Amadeus evidence — research leads, all UNVERIFIED (07 D12)

| File | Note |
|---|---|
| `AeroBridge_Amadeus_Gap_Analysis_Research_Log-2__1_.md` | The findings log (A1–A4, B1–B5, D1–D21); names sources by site, no URLs/dates |
| `AeroBridge_PassC_Reconciliation_Report-1__1_.md` | Reconciliation against Phase 1 registry files that are now absent |
| `AeroBridge_PassD_Final_Closure_Report-1__1_.md` | Workflow/state/error/recovery closure |
| `AeroBridge_Evidence_State_Confirmation_Gate_Report__1_.md` | Pre-Opus gate report |
| `AeroBridge_Amadeus_Reference_Layer_Final_Deliverables-2.md` | Gap analysis, backlog, acceptance criteria (latest version) |
| `AeroBridge_Amadeus_Reference_Layer_Final_Deliverables-1__1_.md` | **Superseded** — earlier version of the file above |
| `AeroBridge_Canonical_PreOpus_Knowledge_Reference.md` | Carry-forward register; "Canonical" in its title is historical |

## A8. Historical audits and plans

| File | Note |
|---|---|
| Part B of this file | The 2026-09-03 consolidation record |
| `14_DEIXEN_Source_vs_Output_Sufficiency_Audit.md` | Pre-Opus audit; its verdict is historical |
| `DEIXEN_MASTER_PRE_OPUS_FOUNDATION_PREPARATION_PLAN-1.md` (repository) | Ended by Karim, 2026-09-24 |
| `DEIXEN_MASTER_EXECUTION_ROADMAP.md` (repository) | Replaced by the Execution Plan |

## A9. Absent artifacts (07 Decision 19 — no work waits on them)

Former files `01_…Repository_Reality_Report`, `02_…Source_Reconciliation_Report`,
`09_…Decisions_Requiring_Approval`, `10_…New_Recommendations`,
`11_…Consistency_Audit_and_Readiness_Review`; the Approved Corpus Review &
Opus Readiness Brief; the Claude/Manus arbitration record; the Domain/SME
Validation Brief and SME-01…SME-10 register; the Scenario Bank architecture
review; the Learning Design adversarial review; the Phase 1 registry files
(`aerobridge-final-canonical-registry.json`, `aerobridge-command-audit.json`,
`aerobridge-out-of-scope-modules.json`, `aerobridge-final-registry-lock-report.md`);
the EgyptAir curriculum document; the OLD-generation source documents
(`PROJECT-20.md`, `SDD.md`, `AMADEUS_CURRICULUM.md`, `COMMAND_REFERENCE.md`,
and others named in Part B); and every codebase (the vanilla-JS
`aerobridge-main.zip` and the React "Rebound Baseline").

## A10. Main dependency lines

- Constitution → Execution Plan → every phase.
- 07 (decisions) → 03, 04, 06, 13, LDS, LXA.
- Verified Reference (Phase 3) → 06 lessons, Coach, Terminal behavior, scenarios, assessment criteria; → `deixen-app/content/` (a change to any V- or U- entry re-checks the content files).
- 07, 03, 04, 06, LDS, LXA, Verified Reference → Slice Build Spec → Claude Code; 03, 04, 07, LXA → Design Brief → Claude Design. A change upstream re-checks these two files.
- LDS → LXA (LXA translates LDS; it never redefines it).
- A change to any upstream file triggers an impact check on everything below it (Constitution §15).
- 07 D27 (element numbering; partly verified details) → Build Spec §4/§5/§13, `CLAUDE.md` §3/§8, LDS/LXA reading rules, Design Brief §4, Scope Disclosure — impact check done 2026-09-25.

**Repository note (2026-09-25).** Karim reports that the Project and the
repository now hold the same current files. In the Project, `text.json` is
`en/text.json` and `text-1.json` is `ar/text.json`; `text_PATCH.json` is
obsolete (merged 2026-09-25).

---


# Part B — Historical record: the 2026-09-03 knowledge-consolidation pass

### 0. What this pass actually did

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

### 1. Full Source Inventory

| # | File | Generation | Size | Language | Role |
|---|---|---|---|---|---|
| 1 | `AeroBridge_Master_Knowledge_Consolidation_Prompt.md` | Governing instruction | 1,647 lines | EN | The task specification for this entire pass. Not a knowledge source itself. |
| 2 | `PROJECT-20.md` | OLD (v9, earliest of the two OLD strata) | 128 lines | AR | Master index/roadmap for the OLD generation. Near word-for-word identical to the repository's own internal `Project.md`. |
| 3 | `SDD.md` | OLD (v9 stratum) | 89 lines | AR | System Design Document — tech stack, architecture, data contracts, Event Log design. |
| 4 | `AMADEUS_CURRICULUM.md` | OLD (v9 stratum) | 135 lines | AR | Full training curriculum (Basic/Advanced/Customer Service tracks), Ghost Mode & Speed Drills specs. |
| 5 | `COMMAND_REFERENCE.md` | OLD (v9 stratum, later code-audited) | 211 lines | AR | Code-derived Amadeus command reference. Governing prompt flagged this IMPORTANT. |
| 6 | `PRODUCT_STRATEGY_UX_ARCHITECTURE-1.md` | OLD (later stratum — explicitly archives the v9 UI/DESIGN docs) | 327 lines | AR | Product/UX strategy: personas, domains, principles, retention/metrics philosophy. |
| 7 | `DESIGN_SYSTEM_UI_BLUEPRINT.md` | OLD (Phase 2, successor to #6) | 128 lines | AR | Real visual tokens and screen blueprints, with documented historical Karim approval. |
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

### 2. The single most important finding of this pass

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

### 3. Workflow phases and their status

| Phase | Status | Where the output lives |
|---|---|---|
| 1. Discover (read everything once, no conclusions) | Complete | This document, §1 |
| 2. Inventory (catalog every file's real scope) | Complete | This document, §1 |
| 3. Map (topic → source-file ownership, old and new) | Complete | `02_AeroBridge_Source_Reconciliation_Report.md` |
| 4. Extract (pull every fact, tagged by source) | Complete | Distributed across the canonical files (03–08) |
| 5. Reconcile (classify: superseded/recovered/conflict/open/etc.) | Complete | `02_AeroBridge_Source_Reconciliation_Report.md` |
| 6. Verify (repository + code-level checking) | Complete | `01_AeroBridge_Repository_Reality_Report.md` |
| 7. Decide / flag for Karim | Complete | `09_AeroBridge_Decisions_Requiring_Malik_Approval.md` |
| 8. Consolidate (final canonical files) | Complete | `03`–`08` (see §4 below) |
| 9. Pre-implementation readiness review | Complete | `11_AeroBridge_Consistency_Audit_and_Readiness_Review.md` |
| 10. Cross-audit | Complete | `11_AeroBridge_Consistency_Audit_and_Readiness_Review.md` |
| 11. Finalize | This document | — |

### 4. Final file map (single owner per concept, per the governing prompt's own rule)

| File | Owns |
|---|---|
| `01_AeroBridge_Repository_Reality_Report.md` | What the supplied code actually does, verified line-by-line where it mattered. Hash mismatch, architecture, per-command verification, tech-debt current status. |
| `02_AeroBridge_Source_Reconciliation_Report.md` | The OLD-vs-NEW comparison itself: topic by topic, what each generation said, and the classification. |
| `03_DEIXEN_Canonical_Product_and_Architecture.md` | Product identity, vision, personas, the 5-area IA, platform direction, navigation. |
| `04_DEIXEN_Canonical_Design_System.md` | Visual/UX principles (Design Positioning closed, Design Execution open), historical tokens, accessibility baseline, anti-patterns. |
| `05_DEIXEN_Canonical_Amadeus_Engine_Reference.md` | The full command set, RBD table, error taxonomy, and current-implementation status per command. |
| `06_DEIXEN_Canonical_Curriculum_and_Coach.md` | Lesson structure, both tracks, Ghost Mode, Speed Drills, and the Coach behavioral contract. |
| `07_DEIXEN_Canonical_Decisions_and_Current_State.md` | The single decisions log going forward — supersedes reading the original NEW `Decisions_and_Current_State.md` in isolation. |
| `08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process.md` | How any AI (or Karim) should work on this project — multi-agent protocol plus the still-valid OLD process/testing/cost rules. |
| `09_AeroBridge_Decisions_Requiring_Malik_Approval.md` | Everything that is a judgment call, not a fact — waits on Karim. |
| `10_AeroBridge_New_Recommendations.md` | This pass's own suggestions, explicitly labeled as suggestions. |
| `11_AeroBridge_Consistency_Audit_and_Readiness_Review.md` | Final self-check against the governing prompt's own completion criteria. |

### 5. Legend used throughout the sibling reports

- **RECOVERED** — real OLD content that NEW does not contain and does not contradict; carried forward.
- **SUPERSEDED** — NEW consciously and explicitly replaces an OLD position (stated as a decision, not a silent drop).
- **CONFLICT** — OLD and NEW state genuinely incompatible things and neither has formally superseded the other.
- **OPEN** — neither generation has decided; flagged for Karim.
- **VERIFIED (code)** — checked directly against the supplied repository's source. This establishes implementation truth only — what the code does — never real-world Amadeus/GDS accuracy, which is a separate, still-pending domain/SME validation question regardless of how many times something has been code-verified.
- **VERIFIED (doc-only)** — internally consistent across documents but the repository doesn't cover it. Most notably: the React/TypeScript "Rebound Baseline" NEW's own documents describe. No such codebase was ever supplied to any pass of this work. Treat every detail about it (file count, hash, `pnpm` results, internal structure) as a claim those documents make, not as something this consolidation inspected — and do not let a future pass drift into writing about it as if it had been.
- **UNVERIFIABLE** — depends on one of the missing referenced artifacts (§1 above).
- **Design Positioning vs. Design Execution** — a distinction introduced during the post-consolidation correction pass (see `04_DEIXEN_Canonical_Design_System.md`): Positioning (professional/operational register) is closed and was never actually reopened; Execution (exact colors, type, identity) is the part genuinely open for the next design phase. Treat any older phrase like "visual direction: open" as referring to Execution only.

### 6. What remains genuinely open after this pass

Arabic/RTL and the PWA-sequencing question were resolved by Karim directly
after this pass and are no longer open — see
`07_DEIXEN_Canonical_Decisions_and_Current_State.md` Decisions 11 and
Platform Direction. What genuinely remains open, each detailed in
`09_AeroBridge_Decisions_Requiring_Malik_Approval.md`: the missing
NEW-baseline codebase (no React implementation has ever been supplied to
inspect — see the VERIFIED (doc-only) note above), the three missing
referenced artifacts, and several smaller items surfaced during repository
verification (the `ancillary.js` wiring gap, the `cleanRunsNeeded`
placeholder status, the live-echo numbering bug's fix timing). The
engine-strategy question (rebuild clean, reuse selectively, or hybrid) is
technical judgment delegated to Claude rather than a Karim-approval item —
see the recommendation in `10_AeroBridge_New_Recommendations.md`.
