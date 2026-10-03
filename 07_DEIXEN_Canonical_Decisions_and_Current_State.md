---
name: DEIXEN Canonical Decisions & Current State
owns: The single decisions ledger and current project status going forward
supersedes reading in isolation: AeroBridge_Decisions_and_Current_State.md
last synchronized: 2026-09-26 (Phase 4 closed — gate approved, Decision 42; delegated Decisions 43–44; approved boards exported, Decision 45; Phase 5 started — build step 1 locked, Decisions 46–47; step 2 part A locked, Decision 48; step 2 part B prepared, Decision 49; part B checked, Decision 50; step 2 locked, Decision 51; step 3 prepared, Decision 52; step 3 locked, Decision 53; step 4 prepared, Decision 54; step 4A checked and locked, Decision 55 (2026-09-29); leaving a running assessment or scenario inside the app, Decision 56; rules for build step 4B, Decision 57 (all 2026-09-29); step 4B-1 checked, Decision 58; rules for build step 4B-2, Decision 59; step 4B-2 checked and build step 4 complete, Decision 60; rules for build step 5 (Coach), Decision 61 (all 2026-09-30); step 5 checked and locked, Decision 62; rules for build steps 6 and 7, Decision 63 (both 2026-10-01); steps 6 and 7 checked, Decision 64; step 7 merged and the build complete, Decision 65; the learner test prepared, Decision 66; Phase 5 closed by Karim after his learner test, Decision 67; the four-step detour before Phase 6, Decision 68 (all 2026-10-02); the accepted Freeze of the detour, Decision 69; Prompt 7 authorized, Decision 70; the Constitution's repository address, Decision 71 (all 2026-10-03); before-Step-4 task 1, F-19, landed, Decision 72 (2026-10-04))
authority note: Where a decision below is owned in more detail elsewhere in this canonical set (product/architecture, design, engine, curriculum/Coach), this file states the decision and its status, and points there rather than duplicating — the same single-ownership discipline the original NEW document already established and this pass is preserving.
---

> **Synchronization note — Phase 2, 2026-09-24.** Working name: **DEIXEN**
> (provisional; see `DEIXEN_Operating_Constitution.md` §1). "AeroBridge" survives
> only inside historical filenames and provenance statements. Owner: **Karim** —
> earlier project records used the name "Malik" for the same person; those
> references now read "Karim". Current project state and every decision:
> `07_DEIXEN_Canonical_Decisions_and_Current_State.md`. Amadeus facts: only
> claims marked VERIFIED under 07 Decision 12 may be taught as fact.


# DEIXEN — Canonical Decisions & Current State

## Document Authority

`DEIXEN_Operating_Constitution.md` governs how work is performed;
`DEIXEN_Execution_Plan.md` governs work sequence and phase gates. Within
project truth, the priority order for resolving any disagreement is:
(1) explicit decisions in this document, (2) current approved architecture
(`03_DEIXEN_Canonical_Product_and_Architecture.md`), (3) evidence-based
review outcomes, (4) new suggestions. For Amadeus domain truth, Decision 12
below governs. Historical discussions, old audits, and prior ideas are
reference material — they do not override an approved decision here. (The
2026-09-03 consolidation pass placed its own governing prompt above this
ordering for that pass only; that override is historical and no longer
applies.)

## Absent Artifacts (Decision 19)

Several artifacts are named in project history but are not present in the
Project or the repository — among them the former files 01, 02, 09, 10 and
11, the Claude/Manus arbitration record, the Domain/SME Validation Brief and
its SME-01…SME-10 register, the Scenario Bank architecture review, the Phase 1
command-registry JSON files, the EgyptAir curriculum document, and every
codebase (the old vanilla-JS repository and the React "Rebound Baseline").
Per Decision 19 they are recorded as **absent**; no work waits on them.
Anything this ledger once reported "from" them (for example "Phase 3 gate:
CLOSED") is historical and was never independently verified. The maintained
list lives in `00_DEIXEN_Knowledge_Consolidation_Plan.md` (Corpus Map).

## Current Project Status

**Governing plan:** `DEIXEN_Execution_Plan.md` (approved by Karim,
2026-09-24). The earlier "Pre-Opus Foundation Preparation" phase and its plan
were ended by Karim's decision on 2026-09-24 and are historical.

**Phase:** Phase 4 (Design) closed on 2026-09-26 — Karim approved the gate
(Decision 42). **Phase 5 (Build), closed 2026-10-02 (Decision 67); current: the detour before Phase 6 (Decision 68)** — build step 1 (evidence store)
locked 2026-09-26 (Decision 46); step 2 part A (engine core, `AN`, `SS`,
`NM`, `AP`) locked the same day (Decision 48); step 2 part B prepared (Decision 49: the D48 follow-ups I-4, I-5, I-6 closed, and the part B rules written into Build Spec §6A); Claude Code built part B in its third session (not merged: two layouts were missing); the project lead supplied them (Decision 50); session 3B finished, merged and tagged part B (Decision 51). Build step 3 (bridge, independence flag, skill states, Growth status, one-tab rule D47) prepared (Decision 52: Build Spec §7A), built in session 4 and locked (Decision 53, tag `step-3-bridge`, 723 tests). Build step 4 prepared (Decision 54: Build Spec §7B) and split into 4A (app shell and Terminal practice) and 4B (the other seven states). 4A built in session 5 and locked (Decision 55, tag `step-4a-terminal`, 818 unit/component and 69 browser tests); leaving a running assessment or scenario inside the app decided (Decision 56); the rules 4B would otherwise guess closed (Decision 57: Build Spec §7B items 11–15). 4B-1 (Flight Deck, Learning, Ghost Mode, Growth, Reset, Scope Disclosure) built in session 6 and checked (Decision 58: 943 unit/component and 104 browser tests; merged and tagged `step-4b1-screens` at the start of session 7); the rules for 4B-2 written (Decision 59: Build Spec §7B items 19–20, the meaning of "the scenario completed"). Session 7 merged 4B-1 (tag `step-4b1-screens`) and built 4B-2 (Decision 60: tag `step-4b2-screens`, 994 unit/component and 158 browser tests); build step 4 is complete — all eight states. The rules for build step 5 (Coach; app I-21) are closed (Decision 61: Build Spec §7C); session 8 built step 5 (Decision 62: tag `step-5-coach`, 1070 unit/component and 187 browser tests). The rules for build steps 6 and 7 are closed (Decision 63: Build Spec §7D); session 9 ran both (Decision 64: tag `step-6-check`; step 7 complete on `feature/step7-pass`, 1070 unit/component and 268 browser tests); session 9B closed app I-23 and I-24 in the app and merged step 7 (Decision 65: `main` = tag `step-7-pass` = `3fdb342`). Every build step of `CLAUDE.md` §7 is done. The learner test is prepared (Decision 66). Karim ran it and closed Phase 5 (Decision 67): the slice works end to end; what the test found about teaching a beginner goes into the four-step detour Karim inserted before Phase 6 (Decision 68; Step 1 targets tag `phase-5-final` = `3fdb342`). Detour steps 1–3 ran on 2026-10-02 and 2026-10-03; Karim accepted the Freeze Package, and its Freeze, design scope and landing times are recorded as Decision 69. The first before-Step-4 task, F-19 (reproducible test evidence), landed on 2026-10-04 (Decision 72: `main` = `c093d5e`). Next: the remaining before-Step-4 tasks of Decision 69 (c) — F-02, F-03, F-05, F-04 — each from `main` after the previous one has landed, then Prompt 7 (the Design Exploration Skill; authorized, Decision 70), then Step 4. Claude Code builds the slice from
`DEIXEN_Slice_Build_Spec.md`, `CLAUDE.md`, the content files, the approved
design and `tokens.css`. Standing delegation to Claude: Decision 29.
Phase 4 record: Claude Design proposed three directions (A "Margin",
B "Instrument", C "Airside"); Karim chose **A** (Decision 31) and fixed what
the Terminal may contain (Decision 30). A was refined against the validation
matrix of Decision 35; Part 1 and Part 2 were reviewed by the project lead
on 2026-09-25/26 (self-review, D17; answers in Decision 41); a third Claude
Design session applied the last fixes, checked by the project lead on
2026-09-26; Karim approved the gate the same day (Decision 42). Preparing
Phase 5, the interface words became string keys (Decision 43) and the `AN`
header-number gap was closed (Decision 44); the approved boards were
exported read-only into the repository so Claude Code can read them
(Decision 45).

**Phase 3 record:** Phase 2 (Foundation Synchronization) completed on
2026-09-24. Phase 3: Step 3.1 produced `DEIXEN_Amadeus_Verified_Reference.md`
(second edition 2026-09-25). Step 3.2: Karim approved the adjusted slice path
(Decision 22), the Terminal output rule (Decision 23), and the `SRCTCM`
step (Decision 24) on 2026-09-25, and approved creating the three Phase 3
files (Slice Build Spec, Design Brief, Claude Code environment pack). Step
3.4 (Design Brief) and step 3.3 (`DEIXEN_Slice_Build_Spec.md`, draft) are
written; Karim approved its four proposals (Decision 25) and then the
Build Spec and `CLAUDE.md` as a whole (Decision 26). Gaps G1–G3 closed by
Claude on 2026-09-25: screen layouts added to the Verified Reference
(third edition, V-14–V-18); slice content and the Simulator Scope
Disclosure written as the content files for `deixen-app/content/`
(awaiting Karim's review). G1 raised K5 and K6; Karim approved both (Decision 27),
and Claude applied them on 2026-09-25 (Build Spec §4/§5/§12/§13, `CLAUDE.md`
§3/§8, Decision 14's wording below, LDS/LXA reading rules, Verified
Reference §3, Design Brief, Scope Disclosure). Readiness check (3.6) run the
same day: passed, subject to Karim's approval of one new item (Build Spec
K7 — contact-SSR endings, Verified Reference U-12) and of seven small
content fixes (listed in `DEIXEN_Slice_Content_Review.md`). Karim approved
the gate the same day (Decision 28).

**Implementation state:** the first build (Decision 20), written from
scratch against approved specifications (Decision 14), is the app in
`deixen-app` on Karim's computer: every build step done, `main` = tag
`step-7-pass` (Decision 65); since 2026-10-04 `main` = `c093d5e`, which adds
F-19's test-only change and changes nothing a learner sees (Decision 72). It counts as the working slice only after
Karim's learner test (the Phase 5 gate). No implementation or design
execution is authorized by this status alone; each follows its Execution
Plan gate.

**Design:** Design Positioning closed; Design Execution closed for the
slice — the approved design of Decision 42 (direction A "Margin", refined)
and its one token file `tokens.css`; a read-only copy of the approved
boards is in the repository at `design/phase4/` (Decision 45). Identity
stays provisional (Constitution §1).

## Decisions Ledger

Decisions are grouped by owning topic. Status values: **Closed**, **Approved
Baseline Rule**, **Approved Contract**, **Approved Scope Boundary**,
**Superseded** (replaced by a later decision, kept for traceability), or
**OPEN**. Where a decision concerns a verification process, **Closed**
describes only that the *requirement* is established — never that the
verification itself has been executed; that distinction is stated wherever it
applies.

### Product & Architecture — owned in detail by `03_DEIXEN_Canonical_Product_and_Architecture.md`
- Product Positioning — **Closed.** Professional aviation operations training
  platform; not travel/LMS/content-only.
- Terminal Priority — **Closed.** The operational heart; any proposal reducing
  its role needs critical review.
- Top-Level Navigation — **Closed.** Five areas only; no sixth (including Work
  Shift Simulator) without explicit review.
- Platform Direction — **Closed — Reconfirmed with nuance.** The current
  stage is not optimized around PWA-first, offline-first, backend-first,
  accounts, sync, or commercial infrastructure — the near-term objective is a
  learning product that genuinely teaches, provable through real use, not
  infrastructure ahead of evidence it's needed. This is explicitly **not
  rejection**: backend, accounts, sync, PWA capabilities, and broader
  commercial infrastructure remain real future possibilities once the
  product proves valuable, to be introduced on evidence and sound technical
  judgment. Where preserving a clean architectural seam toward that future
  costs little now, do so — but do not architect against infrastructure that
  isn't needed yet.
- Responsive Density & Proportion — **Closed.** Validate at 320/360/390/430px
  mobile and 768/1024/1280–1440px tablet/desktop; Terminal's workspace is
  never sacrificed for density.
- Vertical Slice Before Scale — **Approved Baseline Rule.** Full rule owned by
  `03_DEIXEN_Canonical_Product_and_Architecture.md`; the current frozen
  boundary is Decision 8A below.

### Design — owned in detail by `04_DEIXEN_Canonical_Design_System.md`
- Design Positioning — **Closed.** DEIXEN reads as professional,
  operational, serious aviation-operations software — never a consumer app,
  classroom product, generic LMS, or entertainment dashboard. Not reopened by
  this consolidation; not affected by the item below.
- Design Execution — **Closed for the slice (Decision 42, 2026-09-26).**
  Karim chose direction A "Margin" (Decision 31): light-led, with tokens
  structured so a dark theme can be added later — this closes the
  light-vs-dark question. At the Phase 4 gate he approved the refined
  design, the typefaces, header lockup B and `tokens.css` as the one token
  file (Decision 42). Identity stays provisional: DEIXEN is a working name
  (Constitution §1); a dark theme is not designed. The earlier dark-navy/blue
  execution in file 04 remains historical input only.

### Amadeus — domain truth, implementation history, and the frozen slice
- **Domain truth** is owned by `DEIXEN_Amadeus_Verified_Reference.md`
  (Decision 15, created in Execution Plan Phase 3) under the Verification
  Standard (Decision 12). Third edition 2026-09-25 (amended at the
  readiness check, U-12–U-14): it verifies every
  command in the adjusted slice path (Decision 22) — `AN`, `SS`, `NM`, `AP`,
  `TK`, `RF`, `ER`, `FXP` — plus `FQD`, `FXX`, the mandatory PNR elements, and
  the IATA passenger-contact SSRs, and the screen layouts of the slice
  (V-14–V-18). Everything not listed there as VERIFIED is UNVERIFIED.
- **Implementation history:** `05_DEIXEN_Canonical_Amadeus_Engine_Reference.md`
  describes the old engine (37 commands) whose code is not available. It is a
  historical implementation reference only (Decision 14) — neither the build
  baseline nor evidence of real Amadeus behavior.
- Vertical Slice Implementation Boundary (Decision 8A) — **Closed — Frozen /
  Verification-Pending.** Path: the full core transformation chain.
  Workflow family: Pricing & Ticketing. Terminal command boundary: as
  adjusted by Decisions 22 and 24 — `AN → SS → NM → AP → SRCTCM → TK → RF → ER → FXP`, with
  `FQD` as an optional step (the original `AN → SS → FQD → FXP` is
  superseded). Scenario count: 1 behaviorally differentiated scenario.
  Evidence: 1 owned assessment record from real learner actions.
  Growth/Readiness: 1 bounded, qualitative output — no numeric Saudi Readiness
  percentage. Coach: required across all touchpoints spanning the slice.
  **Explicitly deferred from this boundary:** full curriculum authoring, full
  Scenario Bank expansion, Customer Service curriculum, any Amadeus behavior
  not VERIFIED under Decision 12, broad Saudi readiness scoring,
  backend/auth/PWA expansion, new top-level areas, scoring/persistence
  redesign, and visual-identity work beyond what the Design phase approves.
  Any change to the command set, scenario count, or evidence type needs an
  explicit decision update — including the case covered by Decision 20
  (verification shows the path lacks a required step).
- **Amadeus research backlog** (leads carried from the historical evidence
  package; each is UNVERIFIED until checked under Decision 12):
  whether `FXP` works without a passenger name (UNVERIFIED; no longer
  blocks the slice, which enters `NM` first — Decision 22); `QE`/`QN`/`QD` — research
  leads describe functions different from the old engine, so neither version
  is taught (Decision 13); SSR/seat association workflow; voiding; `FXX`
  is now VERIFIED as a real entry (Verified Reference V-06), so the older
  curriculum "correction" that excluded it was wrong; `FXL`/`TQT`/`TTE`/`FQF`; "Amadeus Offers" (`OFS` family);
  post-ticketing segment-status behavior; which entry creates the PRINT
  "Phone" element (`AP` assumed, not stated by a source — Verified
  Reference U-14; the five PRINT elements themselves are VERIFIED, V-08);
  the endings of contact SSRs (U-12); accepted name titles (U-13); the
  real Cryptic host response to each wrong entry in the slice (added
  2026-09-25 — an Amadeus Web Services list of predefined host messages
  exists, but it is an API source, so under Decision 12 it cannot verify
  Cryptic behavior, and it does not say which message follows which entry;
  a message verified later replaces the training line in the same place
  (Decisions 30, 33) with no design change).
### Curriculum & Coach — owned in detail by `06_DEIXEN_Canonical_Curriculum_and_Coach.md`
- Coach Core Guided Learning Layer (Decision 9) — **Closed — Approved.**
  Mandatory, five required touchpoints, state-bound, never static. Layout
  ownership (global element vs. per-page component) is explicitly **Open**
  for whoever implements it to resolve within that approved boundary. For
  the slice: drawn in the approved design (Decision 42); the rules for
  building it are Decision 61 (Build Spec §7C).
- Customer Service Curriculum Contract (Decision 6) — **Closed — Approved
  Scope Boundary.** Separate global competency; not part of the initial
  slice; no CS proficiency/readiness metric shown as measured evidence until
  its own contract (content model, competency structure, assessment logic,
  evidence pathway, domain-verification requirements) is defined.

### Evidence, Assessment & Scenarios

**Evidence & Readiness Contract — Closed, Approved Contract.** A
learner-facing metric may be shown as personal evidence only when its
source, ownership, calculation, scope, and qualification are explicit and
traceable. Four evidence classes: **Recorded** (direct learner action,
persisted), **Calculated** (deterministic derivation from Recorded evidence),
**Illustrative** (static/prototype, must be labeled, not proof), **Planned /
Unavailable** (must be labeled, never shown as current performance).
Growth/Tracking aggregates may only use the persisted evidence records via
the persistence architecture in
`03_DEIXEN_Canonical_Product_and_Architecture.md`. Skill values stay
illustrative until a real formula and evidence owner are approved; streaks
stay non-trust-bearing until a continuity rule is approved. Scenario
performance claims require scenario-specific evidence — labels are never
evidence. For the frozen slice specifically, Growth/Readiness may show only a
qualitative status (Completed / In Progress / Needs More Practice) — not a
number or percentage, which remains unauthorized until a formula is
separately approved.

**Assessment State Contract — Closed, Approved Contract.** Assessment is a
continuous current-session state, not a historically isolated one — entering
it doesn't silently wipe current command history or hint state, but prior
persisted records from earlier sessions are never merged into the current
score. The UI must disclose current-session carry-over whenever it's present.
The hint label must reflect the real hint count — never falsely claim "no
hints" when hints were used. A zero-history, zero-hint session needs no
carry-over disclosure, since there's nothing to disclose. This contract does
not authorize a clean-reset redesign or a scoring/schema change.

**Scenario Differentiation Contract — Closed, Approved Contract.** A scenario
counts as behaviorally distinct only if it changes at least one real
operational condition the learner must respond to, observably reflected in
evidence — a different title, category, badge, or image is not enough. Every
implemented scenario needs an owned Objective, task Constraints, explicit
Expected behavior/acceptance criteria, scenario-aware Feedback (generic
command feedback doesn't satisfy this), Assessment linkage, Evidence linkage,
and state integrity (no hidden global mutation). Operational/GDS semantics a
scenario uses remain gated until VERIFIED under Decision 12. An
unimplemented scenario may be shown as planned/unavailable — never as
completed competency. The first vertical slice needs only **one** scenario to
prove real behavioral differentiation — not a full Scenario Bank.

### Domain Verification

**Decision 7 (Domain/SME Validation Dependency) — Superseded** by Decision 12
on 2026-09-24: no SME is available, and verification now runs through
trusted, current web sources. Two parts of Decision 7 survive inside
Decision 12 unchanged in substance: (a) no aviation/GDS behavior may be
promoted from AI inference — the pipeline is Source → Review → Verified
Reference → Structured content → Implementation → QA, never AI generation →
implementation → assumed truth; and (b) verification must cover both
*command-level* correctness and *whole-workflow* validity — whether the slice
path is a coherent, recognizable real reservations task, not four commands
strung together for engineering convenience.

Code-level verification (what an implementation does) and domain
verification (what real Amadeus does) remain two different kinds of
verification; neither substitutes for the other.

### Process
- Manus Collaboration Protocol (Decision 10A) — **Superseded (historical).**
  Manus has no role in the project (Decision 17).
- Cross-Review Arbitration Outcome (Decision 10) — **Superseded
  (historical).** Its surviving content already lives in its own decisions:
  five-area architecture and Terminal centrality (Product & Architecture
  above). Its visual-direction portion was superseded earlier by the Design
  Execution decision.

### Localization — Decision 11
**Status: Closed — Approved.** DEIXEN must support Arabic + English, with
RTL + LTR. This is an explicit product decision, not merely a historical
default carried over — it is treated as approved unless Karim explicitly
reopens it. **Decided, but distinct from implementation approach:** the
earlier implementation's actual Arabic/RTL build (verified directly in the
supplied repository — see
the former file `01_AeroBridge_Repository_Reality_Report.md` §3, now absent) is preserved as useful
prior evidence that this is achievable and roughly what it looks like in
practice — it is not a template to simply be copied into whatever
implementation comes next. How localization is actually built (data-driven
strings vs. hardcoded, per-component RTL handling, which library if any) is
an ordinary technical implementation choice, not decided here.

### Decisions of 2026-09-24 (Karim)

- **Decision 12 — Amadeus Verification Standard. Closed — Approved.**
  A claim about real Amadeus (syntax, behavior, prerequisite, output, error
  text, workflow) is **VERIFIED** only when it is supported by (a) a publicly
  readable official Amadeus source, or (b) at least two independent, trusted
  sources that agree (for example airline or training-centre manuals or
  published Amadeus-based course material), none on the denylist. In both
  cases the source must concern the Amadeus Cryptic interface (API, NDC, or
  another GDS cannot verify a Cryptic claim), must not be clearly outdated
  for the claim, and the exact URL, access date, the source's own date where
  shown, and the specific statement supported are recorded in the Verified
  Reference. Everything else is **UNVERIFIED**, with the reason recorded (no
  source, single non-official source, conflicting sources, login-walled,
  wrong interface, outdated). Model memory and general GDS knowledge are never
  sources. A weak source is never used to close a gap: an honest UNVERIFIED is
  the required outcome. **Denylist** (sites shown to publish fabricated
  Amadeus commands): mambu.com, curvyyoga.com, chyronhego.com,
  studyabroadfoundation.org, secondnaturejournal.com — extended when new
  evidence of fabrication appears. The historical evidence package names its
  sources by site or description, not by URL and date, so every finding in it
  is UNVERIFIED until re-checked; its earlier statuses ("RESOLVED",
  "SUFFICIENT FOR TRAINING", …) are historical.
- **Decision 13 — Teaching boundary. Closed — Approved.** Only VERIFIED
  claims may be taught as fact or used in lessons, Coach guidance,
  assessment criteria, scenarios, or simulated Terminal behavior. UNVERIFIED
  claims stay in internal documents. If the slice needs a behavior that is
  UNVERIFIED, the gap goes to Karim before build; nothing is invented to fill
  it. The former open item (unverifiable layouts and error texts) is closed
  by Decision 23.
- **Decision 14 — Old engine is history. Closed — Approved.** File 05 is a
  historical implementation reference; its code is not available. The new
  implementation is written fresh from the Verified Reference and approved
  specifications. The former delegated "engine strategy" (keep the old engine
  as a conformance oracle) is withdrawn — the oracle does not exist and may
  itself be wrong (e.g. `QE`/`QN`/`QD`). The old engine's limitations (one
  seat per PNR, two-segment limit, adults-only fares, Egypt-only Timatic,
  non-functional `FQN`/`FQR`, unreachable ancillaries) and its Known Issues
  are not requirements; they are lessons (e.g. every element number shown is
  the element's number in the PNR as it stands at that moment, computed by
  the same function as the final display — wording of Decision 27). Any limitation in the new build
  must be an explicit, disclosed scope decision.
- **Decision 15 — Amadeus Verified Reference. Closed — Approved.**
  `DEIXEN_Amadeus_Verified_Reference.md`, created in Execution Plan Phase 3,
  is the single authority for Amadeus domain truth. Until it exists, no
  Amadeus claim is VERIFIED.
- **Decision 16 — Governance set. Closed — Approved.** Governing:
  `DEIXEN_Operating_Constitution.md`, `DEIXEN_Execution_Plan.md`, and
  `08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process.md` (now canonical).
  Supporting references (consulted, never governing):
  `DEIXEN_Prompt_Engineering_and_Governance_UNIFIED_PROPOSED.md`,
  `UNIVERSAL_AI_SESSION_HANDOFF_PROTOCOL.md`, the AI Operating Environment
  review, and the Amadeus Research Constitution. Historical: the Pre-Opus
  Foundation Preparation Plan, the Master Execution Roadmap, and the Approved
  Corpus Review & Opus Readiness Brief.
- **Decision 17 — Roles. Closed — Approved.** Karim: final authority. Claude
  (Opus) as project lead: reviewer, editor, and verifier; a separate
  independent review is waived by Karim, so self-reviews are labeled as
  self-reviews. Claude Design: design exploration and execution. Claude Code:
  implementation. Manus, ChatGPT, and Sonnet have no project role; any other
  tool may give consultative input only if Karim chooses.
- **Decision 18 — Curriculum goal. Closed — Approved.** DEIXEN teaches
  professional Amadeus — Basic and Advanced — sized to what the Saudi/Gulf job
  market requires of a beginner, with behavior matching real Amadeus
  (Decisions 12–13). The EgyptAir course structure is historical input only;
  the EgyptAir curriculum document is not required. Market requirements must
  themselves be sourced (job postings with URL and date).
- **Decision 19 — Absent artifacts. Closed — Approved.** Anything referenced
  but not present in the Project or repository is recorded as absent; no work
  waits on it.
- **Decision 20 — First build. Closed — Approved.** The first build is the
  frozen slice (Decision 8A), after Phase 3 verification. If verification
  shows the path lacks a required step, Claude presents the evidence and
  Karim decides the adjustment.
- **Decision 21 — Owner name. Closed.** The owner is Karim. Earlier records
  used the name "Malik" for the same person.

### Decisions of 2026-09-25 (Karim)

- **Decision 22 — Slice path adjusted (under Decision 20). Closed —
  Approved.** Evidence: an Amadeus PNR needs five mandatory elements (PRINT —
  Verified Reference V-08), so `AN → SS → FQD → FXP` alone is not a real job
  task. The slice command path is `AN → SS → NM → AP → TK → RF → ER → FXP`;
  `FQD` stays an optional step. Every command in the path is VERIFIED
  (V-01, V-03, V-05, V-07, V-09, V-10, V-11). Scenario count, evidence type,
  and every other part of Decision 8A are unchanged.
- **Decision 23 — Terminal output rule (closes the Decision 13 open item).
  Closed — Approved.** The Terminal reproduces the display formats shown in
  the official examples recorded in the Verified Reference. Any message or
  screen with no verified source (for example the exact text of an error for
  wrong input) is shown as a plain training message, visibly marked as such
  — never written to look like authentic Amadeus text. Verified messages
  (e.g. **NEED TICKETING ARRANGEMENT**, V-09) are reproduced as recorded.
  *Where each kind is placed is refined by Decision 30 (2026-09-25).*

- **Decision 24 — Passenger contact SSR in the slice. Closed — Approved.**
  Evidence: Verified Reference V-13 — under IATA resolution 830d, end of
  transaction shows **MISSING SSR CTCM MOBILE OR SSR CTCE EMAIL OR SSR CTCR
  NON-CONSENT** when no `SRCTCM`/`SRCTCE`/`SRCTCR` is present. `SRCTCM` is
  added after `AP`. Final slice path: `AN → SS → NM → AP → SRCTCM → TK → RF → ER → FXP`; `FQD` optional. If the learner
  reaches `ER` without it, the Terminal shows that verified warning
  (Decision 23).
- **Decision 25 — Slice Build Spec proposals. Closed — Approved.** K1: slice
  limits — one adult passenger, one segment, a single applicable fare (no
  `FXT` step); anything else gets the "not covered in this slice" message.
  K2: the one scenario — the passenger refuses to give a mobile number; the
  learner records it with `SRCTCR` (Verified Reference V-13). K3: an
  assessment or scenario attempt interrupted by closing the browser is
  recorded as abandoned (neither passed nor failed) and the learner is told
  on return. K4: the Growth/Readiness status rule in the Build Spec §10.
- **Decision 26 — Slice Build Spec and `CLAUDE.md`. Closed — Approved.**
  `DEIXEN_Slice_Build_Spec.md` is the build specification for the slice;
  `CLAUDE.md` is the Claude Code instruction file.
- **Decision 27 — Build Spec K5 and K6. Closed — Approved (2026-09-25).**
  K5: every element number shown in the Terminal is the element's number in
  the PNR as it stands at that moment, computed by the same function as the
  final display (Verified Reference V-18). This replaces the wording
  "numbers shown during entry must match the final PNR numbering" in
  Decision 14's lesson example, Build Spec §4/§13 and `CLAUDE.md` §8
  (edits applied by Claude 2026-09-25). K6: screen details that official examples
  show only partly (Verified Reference U-07, U-09, U-10, U-11) are shown
  in the verified pattern with a visible "Layout detail not fully
  verified" marker, never taught, and listed in the Scope Disclosure;
  details with no official pattern (stored `SRCTCR`, `RF` before end of
  transaction) stay plain training messages under Decision 23.
- **Decision 28 — Phase 3 gate. Closed — Approved (2026-09-25).** Karim
  approved the Phase 3 pack: `DEIXEN_Amadeus_Verified_Reference.md` (third
  edition, amended U-12–U-14), `DEIXEN_Slice_Build_Spec.md` (with Decision
  27 applied), `DEIXEN_Design_Brief.md`, `CLAUDE.md`, and the content files
  (`data/slice.json`, `en/text.json`, `ar/text.json`) including the seven
  readiness-check fixes; and K7 — contact-SSR endings (Verified Reference
  U-12) are not taught, a learner-typed ending is accepted and not checked,
  and the gap is disclosed (`disc.7`). Phase 3 is closed; Phase 4 (Design)
  begins.
- **Decision 29 — Standing delegation to the project lead. Closed —
  Approved (2026-09-25).** Karim delegates to Claude (project lead) the
  decisions he would otherwise approve on Claude's recommendation. Claude
  decides, applies, records each such decision here as "by delegation
  (D29)", and reports it to Karim briefly afterwards; Karim may reverse any
  of them. **Reserved to Karim — Claude asks first:** (1) product identity,
  scope, product boundaries, the frozen slice boundary (D8A), new areas or
  major features, and the curriculum goal (D18); (2) the working name,
  brand, visual identity and the final design direction (Phase 4 choice);
  (3) anything involving money, accounts, legal matters, publishing outside
  the project, or real learners' data; (4) changes to the governance set
  (Constitution, Execution Plan phases or roles); (5) confirming as a learner
  that the slice works (Phase 5 gate). **Never delegable, even by
  request:** lowering the Verification Standard or the teaching boundary
  (D12, D13) — an honest UNVERIFIED stays the outcome. Claude's reviews
  remain self-reviews (D17).
- **Phase 3 files — creation approved (Execution Plan §5).** Karim approved
  creating the Slice Build Spec, the Design Brief, and the Claude Code
  environment files (`CLAUDE.md` and repository scaffolding).

### Decisions of 2026-09-25 — Phase 4 (Karim, and by delegation D29)

- **Decision 30 — The Terminal shows Amadeus only. Closed — Approved
  (Karim, 2026-09-25).** Inside the Terminal appear only: Amadeus output
  (Decision 23, kind 1), with the "Layout detail not fully verified" marker
  where Decision 27 requires it; and — only where Amadeus would answer but
  no verified text exists — **one short training line**, labeled "Training
  message" (Decision 23, kind 2). Feedback texts, hints, Coach explanations
  and every other DEIXEN explanation live in a separate **DEIXEN panel**:
  beside the Terminal on desktop, on demand on mobile (LXA §18). This refines
  where Decision 23's three kinds are placed; it does not change what each
  kind may say. File 06's error-message discipline (official message shown
  verbatim, explanation alongside) is unchanged — the panel is "alongside".
- **Decision 31 — Visual direction A "Margin". Closed — Approved (Karim,
  2026-09-25).** Of the three directions Claude Design proposed (A "Margin":
  light, two inks, DEIXEN in the margin; B "Instrument": dark cockpit;
  C "Airside": light room, black screen, yellow — artifact
  https://claude.ai/artifact/PaSoos61b5By1yqdmUK1JM), Karim chose **A**,
  judging B and C closer to an AI-generated look, and asked for A to be
  refined to remove every AI trace. The project lead had recommended C; the
  choice is Karim's (D29 reserved item 2). This closes the Design Brief's
  reserved "visual direction" item and the light-vs-dark item:
  **light-led, with tokens structured so a dark theme can be added later**.
  Identity remains provisional (the name is not final — Constitution §1).
  Refined values are approved at the Phase 4 gate.
- **Decision 32 — Script and direction inside the Terminal. Closed — by
  delegation (D29), 2026-09-25.** Terminal entries and Amadeus output are
  Latin, monospace and left-to-right in both interface languages. The
  interface chrome, the DEIXEN panel and the training line follow the
  interface language (Arabic → right-to-left; commands inside Arabic text
  stay Latin and left-to-right, Build Spec §5). Closes the Design Brief §4
  open question.
- **Decision 33 — Training lines for a wrong entry of a known command.
  Closed — by delegation (D29), 2026-09-25.** When an entry of a slice
  command fails its checklist (Build Spec §6) and no verified message or more
  specific training message applies, the Terminal shows one training line:
  (a) **`tm.notAccepted`** — EN "Entry not accepted." / AR «الإدخال غير
  مقبول.» — when the entry does not follow the verified pattern or refers to
  something that does not exist (format, date range, missing display or
  line); (b) **`tm.notForTask`** — EN "Entry not used: it does not match the
  task." / AR «لم يُستخدم الإدخال: لا يطابق المهمة.» — when the entry is well
  formed but its data is not the task's (wrong name, phone, seats, class,
  route, date, `TK` variant). (b) was added while checking where (a) is used:
  for a well-formed entry, "not accepted" would suggest that Amadeus rejects
  it, which is not verified (Decision 13). In both cases the practice PNR is
  **left unchanged** — a DEIXEN rule (the slice has no `XE` to remove a wrong
  element), not an Amadeus claim. The specific feedback text appears in the
  DEIXEN panel. The mapping of every feedback item to its Terminal line is in
  `slice.json` (`feedback[].terminalLine`); Build Spec §5 states the rule.
- **Decision 34 — Long training messages. Closed — by delegation (D29),
  2026-09-25.** When a training message has more than one sentence, the
  Terminal shows its first sentence, labeled; the rest of the same string
  appears in the DEIXEN panel. The split is made on the authored text before
  tokens such as `{RF_TEXT}` are filled. No text is rewritten.
- **Decision 35 — Phase 4 validation matrix. Closed — by delegation (D29),
  2026-09-25.** The refinement of direction A is checked on: the eight
  learner states at 1440 and 390 px, in English and Arabic; Flight Deck and
  Terminal practice at 320 / 360 / 430 / 768 / 1024 / 1280 px in English,
  and in Arabic at 320 and 1024 px. This narrows the Design Brief §8 item 2
  deliverable for the design phase only. It does **not** narrow the build:
  the Definition of Done below still requires every state to pass at every
  breakpoint of file 04, in both languages.
- **Decision 36 — Terminal on a phone. Closed — by delegation (D29),
  2026-09-25.** Terminal columns never wrap; the Terminal sheet pans
  sideways (direction A's approach), so Amadeus layouts keep their verified
  line structure. The pan must work by touch and by keyboard (file 04
  keyboard rule); WCAG 2.1 reflow allows two-dimensional content such as
  this to scroll.
- **Decision 37 — Retry and reset in the Terminal. Closed — by delegation
  (D29), 2026-09-25.** File 03's "Reset / retry" learner action is one
  control, **Reset task**, in Terminal practice only: it starts the practice
  booking again from empty; recorded evidence is kept. There is no separate
  "Retry step" control — after every response the entry line is already
  awaiting the retry, so a second control would do nothing new (no false
  affordance, 07 Definition of Done). Reset task is not offered in the
  assessment or the scenario, whose attempt rules (Decision 25, K3) do not
  cover a restart. The full reset (`ui.reset.confirm`) stays the
  `RESET_RECOVERY` state, reached from Growth. Basis: 03 Behavioral
  Skeleton; Build Spec §3; Design Brief §3.
- **Decision 38 — Hint order. Closed — by delegation (D29), 2026-09-25.**
  Hint levels are offered in order for the current step: Nudge first; for
  `ER` (Tier 3) Partial Reveal next; Full Reveal last. A level already shown
  stays visible; a level that does not apply to the step (Partial Reveal
  outside `ER`) is not shown. Every request still increments the one
  counter. Basis: LDS §15 (graduated assistance), Build Spec §8.
- **Decision 39 — Count-neutral carry-over text. Closed — by delegation
  (D29), 2026-09-25.** `ui.assessment.carryover` read "1 hints" when a count
  was 1 (same problem in Arabic). Reworded without count-noun agreement:
  EN "… this session already had — entries: {N}, hints: {H}. …"; AR «…
  عدد الإدخالات: {N}، عدد التلميحات: {H}. …». Meaning unchanged.
- **Decision 40 — Status words on the chain (Flight Deck, Growth). Closed —
  by delegation (D29), 2026-09-25.** Each chain step shows the approved
  "Correct in DEIXEN" (`ui.correctInDeixen`) once its skill is
  DEMONSTRATED_INDEPENDENT or higher (Build Spec §7), otherwise a dash; the
  recommended step is marked "Next"; `FQD` is "Optional". The scenario and
  assessment rows show "Completed" or a dash. The design's word
  "Practised" is not used: the skill model does not define it, and it could
  read as competence after any attempt (07 Evidence contract).

### Decisions of 2026-09-26 — Phase 4 (by delegation D29)

- **Decision 41 — Answers to the Part 2 design review. Closed — by
  delegation (D29), 2026-09-26.** Review of the refinement of direction A
  (self-review, D17; every Terminal line in every frame compared with the
  Verified Reference renderings and the demo lines built from V-14/V-15/V-18:
  no mismatch; no demonstration frame holds the task's answer). Design
  answers: (a) Arabic notes sit on a grid of record lines that grows; leaders
  in RTL as drawn; the whole entry line stays left-to-right; the Arabic
  training strip is anchored at column 0 with its words right-to-left inside
  it (consistent with D32). (b) Phones: the "Layout detail not fully
  verified" bracket stays in the gutter, always in view; its words stand
  beside the display (reached by panning) **and** are repeated in the DEIXEN
  drawer; the bracket carries the words as its accessible name — so the
  marker stays visible on phones (D27). (c) 768 uses the phone header with
  Menu; the Terminal runs full width; DEIXEN's margin docks under it.
  (d) Phones: the language switch lives in the menu sheet. (e) Completion:
  the learner's `FXP` entry line, then the V-17 display exactly as recorded,
  including its own first line `FXP` — nothing merged or dropped (D23).
  (f) Phones: Reset task and Start assessment at the foot of the DEIXEN
  drawer, in practice only (D37). (g) "Next" appears on the Flight Deck
  only; Growth lists evidence. (h) No display-size type on learner screens.
  (i) Growth with no recorded practice does not show "Reset everything"
  (nothing to reset — no false affordance). Wording fixes for chrome drafts:
  "Booking now" → EN "Booking as it stands" / AR «الحجز كما هو الآن» (the
  old words read as a call to book); AR for "Reset task" → «ابدأ المهمة من
  جديد». Chrome words become string keys at the Phase 4 gate.

### Decisions of 2026-09-26 — Phase 4 gate and Phase 5 preparation (Karim, and by delegation D29)

- **Decision 42 — Phase 4 gate. Closed — Approved (Karim, 2026-09-26).**
  Karim approved the four gate items (D29 reserved item 2; Execution Plan
  §5): (a) **the refined direction A "Margin"** — the Claude Design canvas
  https://claude.ai/artifact/PaSoos61b5By1yqdmUK1JM at version
  `1790413092-0523`: identity, rules, tokens, behaviour and controls boards
  (`P1-B` to `P1-F`), the eight states in English (`P1-01` to `P1-08`) and
  Arabic (`P2-AR-*`), the other widths (`P2-BP-*`), the phone menu
  (`P2-Menu-*`) and the final issues board (`P2-Issues`). The session-1
  boards (directions A, B, C), the audit board and the map board are
  history, not part of the approved design. (b) **Typefaces:** IBM Plex Mono
  for the record (Terminal); Public Sans with IBM Plex Sans Arabic for the
  interface; Literata with Noto Naskh Arabic for DEIXEN's voice — all free,
  open licences. (c) **Header lockup B:** below 24 px cap height (the 18 px
  desktop header, the 15 px phone header) the wordmark keeps its field line
  and drops the ticks; from 24 px up A and B are the same drawing. The
  frames draw A; B governs the build. (d) **`tokens.css`** — the canvas file
  `project/tokens.css` (sha256
  `fd09cb17c72ce208eb10baef724111b9db76fb279871bb8a6748bd641645f80e`),
  unchanged — becomes the one token file in the code repository (new file
  approved, Execution Plan §5). Basis: the project lead's check of the
  session-3 result (self-review, D17): the six fixes of Decision 41 applied;
  every Amadeus display line in every frame matches the Verified Reference
  renderings (V-14, V-15, V-17, with V-18 numbering) and the demonstration
  lines keep the verified columns and correct weekdays; `tokens.css` unchanged since Part 2. Karim was
  asked to check line breaks in both scripts with the real fonts before
  approving; the build still checks every breakpoint in both languages
  (Definition of Done). Design Execution is closed for the slice; the name
  and identity stay provisional (Constitution §1). Phase 4 is closed;
  Phase 5 (Build) is next.
- **Decision 43 — Interface words become string keys. Closed — by
  delegation (D29), 2026-09-26.** The 71 interface words of the approved
  design (both lists on `P2-Issues`, with the Decision 41 fixes) are added
  as `ui.*` keys to `en/text.json` and `ar/text.json` and listed in
  `slice.json` `ui` (with `ui.what.*`, which were in the string files but
  missing from that list). Words that carry a value are written once with a
  token: "Start lesson {N}", "Practise {CMD} in the Terminal",
  "Watch {COMMANDS}", "Entry {N} of {T}" (tokens defined in `slice.json`
  `rules`). One Arabic wording change: "Watch {COMMANDS}" is «شاهد:
  {COMMANDS}», not «شاهد الأوامر …», because the plural «الأوامر» is wrong
  for a script with one command (L01, L10) — count-neutral, as in Decision
  39. Language names (`ui.lang.en`, `ui.lang.ar`) are the same in both files.
  Karim may change any word.
- **Decision 44 — `AN` header number. Closed — by delegation (D29),
  2026-09-26.** Build Spec §5 said the number before the weekday in the `AN`
  header takes its value from `slice.json`, which held none (found in the
  Part 1 review). Rule: every `AN` display in the slice — main task,
  scenario, Ghost Mode demo — shows the fixed value **30** (the value of the
  V-14 DEIXEN rendering and the approved design), whatever the date or
  route (`slice.json` `displays.AN.headerNumber`). It is not computed from
  the date: that would simulate the one non-official reading ("days until
  departure", Verified Reference U-09), which Decision 13 forbids. The
  display carries the "Layout detail not fully verified" marker; the number
  is never taught; `disc.6` already lists it.
- **Decision 45 — Approved boards exported into the repository. Closed —
  Approved (Karim, 2026-09-26).** A Claude Code session on Karim's computer
  cannot open the Claude Design canvas (a claude.ai page behind sign-in).
  So the approved design is copied, read-only, into
  `DEIXEN-KNOWLEDGE/design/phase4/`: the 68 boards listed in Build Spec §2
  and `tokens.css`, taken unchanged from canvas version `1790413092-0523`
  (`tokens.css` sha256 as in D42), with `MANIFEST.md` giving each file's
  sha256 (and the same list as `MANIFEST.sha256`, for `sha256sum -c`). The canvas stays the approved original and the folder is its copy:
  a file whose sha256 differs from the manifest is not the approved design.
  The boards expect the canvas runtime (`support.js`), which is not copied;
  Claude Code reads them as HTML markup — layout, role tokens, words, ARIA
  roles. Words still come from the string files and behaviour from the Build
  Spec (Build Spec §2, "What a frame is"). New files approved (Execution
  Plan §5). Closes the file 13 open item "how Claude Code reads the approved
  boards"; `CLAUDE.md` §4's "stop and ask" now applies when a board it needs
  is missing from the folder or fails its manifest check.

### Decisions of 2026-09-26 — Phase 5, build step 1 (by delegation D29)

- **Decision 46 — Build step 1 (evidence store) checked and locked. Closed
  — by delegation (D29), 2026-09-26.** Claude Code's first session built
  only `CLAUDE.md` §7 step 1: the store in `deixen-app/src/evidence/` under
  the one key `deixen.state` = `{ schemaVersion: 1, events }`, with only the
  Build Spec §11 fields and event types (any other field refused on save
  and on load), millisecond timestamps, `seq` per session, one `sessionId`
  per app load, full reset on a version mismatch or unreadable data, a
  confirmed reset that clears storage and records nothing, and the
  interrupted-attempt rule (§9, K3). Reported: 96 tests passed, 0 failed;
  typecheck and build pass; 8 deliberately planted faults each caught, then
  removed; merged to `main`, tag `step-1-evidence-store`. The project lead
  checked the report against Build Spec §11 and `CLAUDE.md` §8
  (self-review, D17: the report was read, the code was not). One
  clarification, confirmed by Karim during the session and now written into
  Build Spec §11: on `assessment_ended` and `scenario_ended`, `result` holds
  `completed` or `abandoned` (no new field). One wording fix: file 03
  "Persistence Architecture" said Recorded **and Calculated** evidence is
  persisted; corrected to match §11 (only Recorded events are stored;
  Calculated values are derived on read) — raised by Claude Code as
  `ISSUES.md` I-3. Open for the next session: Claude Code reported 70 files
  passing the design manifest check; the manifest lists 69 (68 boards and
  `tokens.css`) — a count to confirm, not a failed check.
- **Decision 47 — DEIXEN runs in one browser tab at a time. Closed — by
  delegation (D29), 2026-09-26.** Raised by Claude Code (`ISSUES.md` I-2):
  with two tabs open, one tab's save can overwrite the other's events, and
  a second tab opened during a running assessment would wrongly record it
  as abandoned. Rule: the first open tab keeps the record. A tab that
  opens while another DEIXEN tab is open records nothing, runs no
  interrupted-attempt check, and shows only a notice (`ui.oneTab.title`,
  `ui.oneTab.body`) asking the learner to use one tab; when the other tab
  is closed, reloading makes this tab the one that records. Wording,
  added to the string files at build step 3:
  EN — "DEIXEN is already open in another tab" / "To keep your record
  accurate, DEIXEN works in one tab at a time. Close this tab and continue
  in the other one, or close the other one and reload this page." AR —
  «DEIXEN مفتوح بالفعل في علامة تبويب أخرى» / «للحفاظ على دقة سجلك، يعمل
  DEIXEN في علامة تبويب واحدة فقط. أغلق هذه العلامة وتابع في الأخرى، أو
  أغلق الأخرى ثم أعِد تحميل هذه الصفحة.» The notice uses the approved
  design's existing tokens and patterns; it adds no control that does not
  work. How the second tab is detected is Claude Code's technical choice
  (`docs/DECISIONS.md`). Why not "accept and disclose": a record that can
  silently lose events breaks the evidence contract (Build Spec §11,
  `CLAUDE.md` §3 rule 5). Implemented at build step 3 (bridge). Karim may
  change the wording.

- **Decision 48 — Build step 2 part A (engine core, `AN`, `SS`, `NM`,
  `AP`) checked and locked, with open follow-ups. Closed — by delegation
  (D29), 2026-09-26.** Claude Code's second session built the pure engine
  (no clock, storage, randomness, UI or content wording), the one numbering
  function for every element kind (tests: `SS` 1 → 2 after `NM`,
  `SSR CTCM` 4 → 5 after `TK`), and the four commands. Reported: 263 tests
  passed, 0 failed (96 from step 1, 167 new); every checklist item tested
  passing and failing; every Amadeus line traced to its V-number (test and
  `docs/DECISIONS.md` T3); 15 planted faults each caught; merged to `main`,
  tag `step-2a-engine`. The design manifest has 69 lines, all OK — the
  earlier "70" was a miscount (closes the D46 follow-up). The project lead
  checked the report (self-review, D17: report read, code not read).
  **Correction:** the session brief said an `AN` entry without a time
  needs no marker; Build Spec §5 puts the marker on every `AN` display
  (U-09), and Claude Code rightly followed the spec — the brief was wrong.
  **Answered by Karim inside the session** (recorded in the app's
  `docs/ISSUES.md`; exact wording to be copied here when available):
  I-5 — the two-letter weekday in the `AN` header uses `MO`…`SU`; only
  `SU` appears in an official example, so the other six codes are shown
  only inside the already-marked `AN` display and never taught —
  **follow-up:** verify them (Decision 12) or add them to the unverified
  list (Verified Reference U-09 row) and to `disc.6`; I-6 — "not
  recognized" vs "not covered": an entry whose code is named in the
  Verified Reference but not simulated gets `tm.notCovered`, anything else
  `tm.notRecognized` — **follow-up:** `disc.2` says "any other entry" gets
  "not covered"; align its wording; case — the Terminal field shows typing
  in uppercase (step 4); the engine never rewrites an entry. **Open:**
  I-4 — a carrier-preferred `AN6X…` display needs the airline's name in
  its header (V-14); `slice.json` has the code `6X` but no fictional name,
  so that one case stops with "not built" until a clearly fictional name
  is added. **Noted, not blocking:** I-7 — `AN` dates have no year and the
  V-01 window spans 365 days, so checklist item (b) almost never fails
  (only `29FEB` and one edge date); it yields little practice evidence —
  revisit when the curriculum expands. Step 3 must open the store in a
  non-recording mode for a second tab (D47) and handle Part B commands and
  the `6X` case, which currently stop with "not built".

### Decisions of 2026-09-26 — Phase 5, preparing build step 2 part B (by delegation D29)

- **Decision 49 — D48 follow-ups closed; rules for build step 2 part B.
  Closed — by delegation (D29), 2026-09-26.** Self-review (D17).
  (a) **I-5, weekday codes — VERIFIED.** All seven codes `MO TU WE TH FR
  SA SU` appear in official Service Hub `AN` headers, each matching the
  calendar weekday of its date; an official flight-information display
  labels them as its day column. Recorded in Verified Reference V-14
  (amendment 2026-09-26). Karim's in-session answer stands; the weekday
  is the weekday of the requested date. No change to `disc.6`, which does
  not list the weekday. U-09 is unchanged: the header number's meaning
  stays unverified and D44 stands.
  (b) **I-4, the airline name for `6X`.** `slice.json` `airlineName` =
  **`PRACTICE AIRLINE`** — clearly invented, not a real airline — shown in
  the banner of a carrier-preferred `AN6X…` display (V-14:
  `** PRACTICE AIRLINE - AN **`). Amadeus itself uses `6X` as an example
  airline code on Service Hub. Karim may change the name.
  (c) **I-6, "not recognized" vs "not covered".** Rule (Karim, in
  session 2): an entry whose code the Verified Reference names but the
  slice does not simulate → `tm.notCovered`; anything else →
  `tm.notRecognized`. Build Spec §6 (the "Nothing else" line) and `disc.2`
  (EN + AR) reworded to match; `disc.2` now also says that "not
  recognized" does not mean Amadeus would reject the entry.
  (d) **Rules for build step 2 part B** (Build Spec §6A), found while
  preparing the session: `ER` with more than one missing item shows
  `tm.otherMissing` (which message Amadeus shows first is not verified);
  the V-13 bypass needs `ER` as the very next entry after the warning (a
  DEIXEN rule); the filed PNR's layout (V-18, including the segment line
  after end of transaction — newly recorded in V-18 from three official
  examples); the stored `SSR CTCM` line keeps the learner's ending as typed,
  with the marker; `tm.ctcrLine` carries no element number; `SRCTCR` in the
  main task → `tm.notForTask` with a new feedback item
  `ctc.fb.refusalNotTask` (EN/AR added; 45 feedback items, 33 diagnostic,
  12 corrective); `FXP` before `ER` prices but does not complete the task;
  after completion every entry gets `tm.sliceEnd`. `disc.6` (EN + AR) now
  says DEIXEN shows no tag lines above the header (such as RLR or TST),
  not only no RLR.
  Files changed: Verified Reference (V-14, V-18, change log), Build Spec
  (status, §6, §6A), `slice.json`, `en/text.json`, `ar/text.json`, 13,
  Execution Plan §7. Still open from D48: copy the exact wording of the app's
  `docs/ISSUES.md` (I-4…I-7) and `docs/DECISIONS.md` T3 into this file when
  Claude Code pastes them (asked for in the session-3 prompt). I-7 stays
  noted only.

### Decisions of 2026-09-28 — Phase 5, build step 2 part B (Karim in session, and by delegation D29)

- **Decision 50 — Build step 2 part B checked; its open items closed.
  Closed — by delegation (D29), 2026-09-28**, except where marked Karim.
  Claude Code's third session built `CTC`, `TK`, `RF`, `ER`, `FXP` and the
  `AN6X` banner on branch `feature/engine-b`, not merged. Reported: 552
  tests passed, 0 failed (289 new); every checklist item tested passing and
  failing; the trace test covers every new Amadeus line; 18 planted faults,
  all caught; the knowledge files and the content copy checked current; the
  design manifest 69/69. The project lead checked the report against Build
  Spec §6, §6A and `CLAUDE.md` §8 (self-review, D17: report read, code not
  read). The verbatim app `ISSUES.md` I-4…I-7 and `DECISIONS.md` T3 are
  now in the project lead's hands (D48 follow-up closed); they match D48
  and D49 in substance.
  (a) **I-8 — header after end of transaction** (blocked the merge):
  Verified Reference V-18 now carries a DEIXEN rendering from three
  official examples — the day has no leading zero (`1NOV24`), then `/`,
  `HHMM`, `Z`.
  (b) **I-9 — `FQD` layout:** V-16 now carries a DEIXEN rendering. Nothing
  is invented: the notice lines, the global indicator and mileage part of
  the date line, and the `+`/`@` sign are left out, and `disc.6` (EN + AR)
  says so; the other columns show `-`, the airline column `6X`.
  `slice.json` `fqd.note` updated.
  (c) **I-10 — `TK OK` date as `DDMMM` — Karim, in session.** Matches the
  official `TK OK01NOV` (V-18).
  (d) **I-11 — changes after filing are not covered — Karim, in session.**
  Written into Build Spec §6A item 9.
  (e) **Repeated elements** (reported rule: every repeat adds an element).
  Kept for `AP` and the contact SSR (official PNRs show several). Changed
  for `TK` and `RF`: a second one gets `tm.notCovered` and changes nothing
  — no source shows two, and inventing a display for it would teach
  something unverified (D13). Build Spec §6A item 10.
  (f) Noted: in the scenario, the V-13 warning also shows
  `scn.fb.warningShown` in the panel — as `slice.json` intends.
  Files changed: Verified Reference (V-16, V-18), Build Spec (§6A items
  8–10), `slice.json`, both string files (`disc.6`), 13. Next: a short
  Claude Code session builds (a), (b), (e), merges and tags
  `step-2b-engine`; then build step 3.

- **Decision 51 — Build step 2 (engine) complete and locked. Closed — by
  delegation (D29), 2026-09-28.** Session 3B built the filed header (V-18
  rendering), `FQD` (V-16 rendering) and the repeat rule of Build Spec §6A
  item 10; merged to `main`, tag `step-2b-engine`. Reported: 600 tests
  passed, 0 failed; typecheck and build pass; `tokens.css` unchanged;
  manifest 69/69; content copy byte-identical to the knowledge copies; 13
  planted faults, all caught; app I-8…I-11 closed (`docs/DECISIONS.md` T5).
  Self-review (D17: report read, code not read). Two points accepted:
  (a) Claude Code followed the spec over the brief — `FQD` for a route with
  no practice fares gets the more specific `tm.noPracticeData` (spec §5); a
  practice route that is not the task's gets `tm.notForTask`. The brief was
  incomplete, not the spec. (b) `FQD` with options after `/` →
  `tm.notCovered` (V-16 records no display for options; `disc.2` already
  covers entries the slice does not simulate); `FQD` + city pair + a bare
  `/` → `fqd.fb.format`. Noted: `SS` keeps an engine stop for flights that
  arrive the next day (no verified layout); no practice flight does, so it is
  never reached. Sync note: Karim's computer holds a second, git copy of the
  knowledge files (`Downloads\Documents\DEIXEN-KNOWLEDGE`) that differs from
  the one Claude Code reads (`Documents\DEIXEN\DEIXEN-KNOWLEDGE`); only the
  latter is used. Next: build step 3.

### Decisions of 2026-09-28 — Phase 5, preparing build step 3 (by delegation D29)

- **Decision 52 — Rules for build step 3; one-tab and hint strings added.
  Closed — by delegation (D29), 2026-09-28.** Self-review (D17). While
  preparing build step 3 (bridge, independence flag, skill states, Growth
  status) the project lead found places where Build Spec §7–§11 would make
  the build guess. They are closed in a new Build Spec **§7A** (16 items);
  no event field or event type is added (§11) and nothing about Amadeus is
  claimed. The main points: (a) a **run** is the Terminal work on one
  booking; the booking is not stored, so a reload starts the practice
  booking empty. (b) **`attemptId` = one step attempt** — the events of one
  skill in one run until an entry of that skill is valid; so a hint that
  stays visible (D38) counts against every later entry on that step.
  (c) `result`: `valid` = every checklist item passed; `invalid` = a slice
  command with a failed item (every refused `ER` and the V-13 bypass);
  `out_of_scope` = no checklist (`tm.notRecognized`, `tm.notCovered`,
  `tm.sliceEnd`). (d) `feedback_shown` carries the feedback item's own skill
  and kind — so the scenario's `scn.fb.warningShown` (skill `CTC`,
  corrective) makes the next `CTC` entry non-independent. (e) A Ghost Mode
  script reveals every skill that has an entry in it. (f) Corrective
  feedback and a Ghost reveal affect only the first entry on that skill
  after them ("immediately preceded", §8); without this, one corrective
  text would block independence for the rest of the session. (g) Skill
  states come from one pass over the events; `TRANSFERRED` also needs the
  `CONSOLIDATED` count (so demotion to `CONSOLIDATED` keeps its meaning,
  LDS §7 Fix 3–4); scenario successes count toward either state only for
  the load-bearing skills (`CTC`, `ER`); `NEEDS_REINFORCEMENT` is cleared by
  one valid entry, as §7 says. (h) **Error-Recovery Practice on `ER`** = a
  refused `ER` (`MANDATORY_MISSING` — every such refusal comes from an
  element the Verified Reference makes mandatory) followed by a valid `ER`
  in the same step attempt; a bypass is not a recovery. (i) **Hint
  levels:** Nudge applies once the step has a wrong entry (it names that
  entry's error category); Partial Reveal only for `ER` after a refused
  `ER`; Full Reveal always. Found while checking this: `reveal.ER` reads
  "Add the missing element first … Missing now: {MISSING_LIST}", which is
  wrong when nothing is missing — new feedback item **`reveal.ER.ready`**
  (EN "Type {EXPECTED_ENTRY}" / AR «اكتب {EXPECTED_ENTRY}», corrective; now
  46 feedback items, 33 diagnostic, 13 corrective); and the token
  `{MISSING_LIST}` had no definition — now the command codes of the
  missing elements in path order (`slice.json` `rules`, with `{RF_TEXT}`,
  `{CTCR_TEXT}`, `{WHAT}`, `{H}`). (j) An assessment or scenario is
  **completed with every checklist item met** when its run holds a valid
  `ER` followed by a valid `FXP`. (k) **Growth order:** empty state, then
  Needs More Practice, then Completed, then In Progress — a current
  weakness is shown rather than hidden; the last assessment that ended
  `completed` decides the assessment part (abandoned ones are skipped, K3).
  Ghost Mode alone leaves the empty state (it is not evidence, §3);
  `ui.growth.empty` reworded to match: EN "Nothing recorded yet. Your
  status appears after you finish a lesson or make your first practice
  entry." / AR «لا يوجد شيء مسجَّل بعد. ستظهر حالتك بعد أن تُنهي درسًا أو
  تكتب أول إدخال تدريب.» (l) The one-tab strings of Decision 47 added as
  `ui.oneTab.title` and `ui.oneTab.body` (both string files; listed in
  `slice.json` `ui`; now 208 keys in each file). (m) Engine inputs: local
  calendar date (task dates, `AN` window), UTC date and time (filed
  header), a fresh random record locator for each `ER`; none stored.
  **Left open, on purpose:** leaving a running assessment or scenario
  inside the app without closing the browser (K3 covers only closing) —
  decided before build step 6; whether a Coach explanation shown beside a
  verified message (e.g. `coach.needTk`) counts as corrective feedback —
  decided before build step 5 (Coach). Files changed: Build Spec (status,
  §7A, pointers in §8, §10, §11), `slice.json`, `en/text.json`,
  `ar/text.json`, 13, Execution Plan §7. Karim may reverse any of these.
  Also checked 2026-09-28: the GitHub repository's main folder now holds
  the current files (07 with D51, Build Spec with §6A items 8–10, the
  content files with 205 keys each) — the layout problem recorded in 13 is
  closed.

- **Decision 53 — Build step 3 (bridge and evidence rules) checked and
  locked. Closed — by delegation (D29), 2026-09-28**, except where marked
  Karim. Claude Code's fourth session built Build Spec §7A on branch
  `feature/bridge`, merged to `main`, tag `step-3-bridge`. Reported: 723
  tests passed, 0 failed (123 new); typecheck and build pass; knowledge
  markers and the content copy checked (208 keys each, byte-identical);
  manifest 69/69; `tokens.css` unchanged; 20 planted faults, all caught; the
  engine-result → event table is in the app's `docs/DECISIONS.md` T6. The
  project lead checked the report against Build Spec §7A, §13 and
  `CLAUDE.md` §8 (self-review, D17: report read, code not read). Accepted:
  (a) an unrecognized entry has no skill, so it carries no `attemptId`
  (the step-1 store had required one; no field added) — matches §7A items
  2–3. (b) One engine change: after task completion the engine reports
  which command was typed, so the `out_of_scope` event carries its skill
  (§7A item 3). (c) Demotion: the error that sets `NEEDS_REINFORCEMENT` is
  not a failed reinforcement attempt; only errors while it is active count
  — this is §7A item 8 as written; the session brief's test line ("two
  failures → TRANSFERRED → CONSOLIDATED") was loose. The spec was right,
  the brief was not (same lesson as sessions 2, 3, 3B). (d) One-tab
  detection uses a browser lock that only one tab can hold and that the
  browser releases when the tab closes; a browser without that feature
  would record in every tab — accepted, as all current major browsers have
  it (Claude Code's statement, not checked by the project lead); revisit if
  an older browser has to be supported. **Karim, in session (app I-12):**
  after an assessment or the scenario has ended, the learner can return to
  practice; this starts a new practice run — written into Build Spec §7A
  item 1 (the exact wording of app I-12 to be confirmed in the next
  session's checks). **By delegation:** Claude Code noted there was no
  approved wording for telling the learner that an unreadable or
  other-version record was reset (Build Spec §11) — a silent loss of the
  record would break the evidence contract's honesty, so a notice is
  added: `ui.dataReset` — EN "Your saved practice record could not be
  read, so DEIXEN started a new, empty record in this browser." / AR
  «تعذّرت قراءة سجل تدريبك المحفوظ، لذلك بدأ DEIXEN سجلًا جديدًا فارغًا في
  هذا المتصفح.» (both string files, 209 keys each; listed in `slice.json`;
  Build Spec §7A item 14). **Noted for build step 4:** which skill is "the
  current step" for hints (the screen gives it to the bridge) must be
  defined before the step-4 session; the D34 two-sentence split is a
  screen helper. **Noted for build step 5:** the escalation offer needs a
  per-session count of same-category errors (not built). Still open from
  D52: leaving a running assessment or scenario (before step 6); Coach
  explanations and independence (before step 5). Files changed: Build Spec
  (status, §7A items 1 and 14), `slice.json`, both string files, 13,
  Execution Plan §7. Next: build step 4 (Terminal screen, then the other
  seven states).

### Decisions of 2026-09-28 — Phase 5, preparing build step 4 (by delegation D29)

- **Decision 54 — Rules for build step 4; the "current step" for hints.
  Closed — by delegation (D29), 2026-09-28.** Self-review (D17). While
  preparing build step 4 (screens) the project lead closed the item left
  open by D53 and the places where the screens would otherwise guess; they
  are in a new Build Spec **§7B** (5 items). No event field, event type or
  string is added, and nothing about Amadeus is claimed. (a) **The current
  step** (the skill whose hint levels the panel offers; an accepted hint is
  recorded on that step's open step attempt, §7A item 2) — the first that
  holds: task complete → none; booking filed (valid `ER` or bypass) →
  `FXP`; Terminal just opened from a lesson or Ghost Mode's
  `ui.ghost.practise` with no scored entry since → the lesson's skill
  (`slice.json` `lessonCommon.practiceBridge`); the run's last `valid` or
  `invalid` entry was `invalid` on skill X → X; otherwise the first of `AN`,
  `SS`, `NM`, `AP`, `CTC`, `TK`, `RF`, `ER` with no valid entry in the run.
  `out_of_scope` entries never move it; `FQD` only through a lesson or its
  own wrong entry. The starting point written in the previous handoff
  ("the first required step in path order without a valid entry") was
  checked against the approved design and rejected: after a refused `ER`
  with `TK` missing it names `TK`, so Partial Reveal — `ER` only, §7A item
  10 — could never be offered where `P1-04b` and `P1-E` draw it and where
  `reveal.ER` / `er.partial.*` are meant to be used; and a learner who had
  just typed a wrong `TK` would get hints for another step. (b) **Hint
  levels on the screen:** Partial Reveal is drawn only when the current
  step is `ER` (D38); each level is shown / available / not available, as
  the bridge says; a shown level's text is kept in screen memory for its
  step attempt (not an event). Where a frame's enabled levels differ (the
  `P1-04a` moment was drawn before §7A item 10; `P1-05` lacks Partial
  Reveal after a refused `ER`), the spec wins (Build Spec §2). (c) **Entry
  field:** Karim's answer in session 2 ("the field shows typing in
  uppercase; the engine never rewrites an entry", D48) is built as
  capitals in the field's own value while typing, so what is shown is what
  is sent and stored — never a lowercase entry displayed as capitals.
  (d) **Two parts:** 4A — app shell, load notices, `TERMINAL_PRACTICE` with
  the DEIXEN panel, all breakpoints, both languages; 4B — the other seven
  states. Until 4B, controls leading to states not yet built are drawn
  disabled and listed; "no false affordance" is checked at 4B. Coach texts
  come at step 5. (e) **Load notices** (no board draws them): the second
  tab shows only `ui.oneTab.*`; `ui.abandoned` and `ui.dataReset` once per
  load on the first screen, DEIXEN voice, existing tokens only, never over
  the entry line. **Moved:** leaving a running assessment or scenario
  inside the app is now decided **before 4B** (not step 6), because 4B
  draws the assessment and scenario screens with the navigation in their
  header. Still open: Coach explanations and independence, and the
  per-session same-category error count (both before step 5). Files
  changed: Build Spec (status, §7B, pointer in §8), 13, Execution Plan §7;
  content files unchanged (209 keys each). Karim may reverse any of these.

### Decisions of 2026-09-29 — Phase 5, build step 4A checked (Karim in session, and by delegation D29)

- **Decision 55 — Build step 4A (app shell, load notices, Terminal
  practice) checked and locked; app I-12 to I-15 closed. Closed — by
  delegation (D29), 2026-09-29**, except where marked Karim. Claude Code's
  fifth session built Build Spec §7B items 1–5, merged to `main`, tag
  `step-4a-terminal`. Reported: 818 unit/component tests (94 new) and 69
  browser tests passed, 0 failed; typecheck and build pass; knowledge
  markers present; manifest 69/69; `tokens.css` sha256 as approved; the
  three content files byte-identical (209 keys each); automatic checks for
  WCAG 2.1 AA in both languages at four widths, keyboard-only use, no raw
  design value, no word outside the string files, screens using only the
  bridge; 18 planted faults, all caught; two real bugs found by the tests
  and fixed (the `/` and `-` keys unreachable by keyboard on phones; a tap
  on DEIXEN missed with the phone keyboard open); 38 screenshots (8 widths
  × 2 languages × 2 moments, plus keyboard, drawer, menu) compared with the
  boards by eye. The project lead checked the report against Build Spec
  §7B, §13 and `CLAUDE.md` §8 (self-review, D17: report read, code and
  screenshots not read). Accepted: (a) the four differences from the boards
  (`P1-04a` Nudge disabled; `P1-05` Partial Reveal drawn at `ER`; area
  links disabled until 4B; the feedback text where `P1-04b` / `P1-E` draw
  Coach notes) — each is what §7B items 2 and 4 say. (b) The engine
  addition: each line of a booking display carries its element number from
  the one numbering function, so the screen never reads a number off the
  Amadeus text (§4); no behaviour changed. (c) The case rule, app
  `docs/DECISIONS.md` T3 verbatim: "The engine reads entries exactly as
  given (uppercase). The Terminal field (step 4) shows letters in uppercase
  as they are typed (Karim, session 2), so the learner sees what is
  submitted; the engine never silently rewrites an entry. Leading and
  trailing spaces are trimmed." — the engine ignores outer spaces when it
  reads; the field removes nothing and `command` is stored as typed;
  matches §7B item 3. (d) The four behaviours over time that no single
  frame shows (app `docs/DECISIONS.md` T7) — accepted as the builder's
  choices where a frame shows one moment (§2), with two guards now written
  as Build Spec §7B item 10: the app never scrolls the entry line or the
  first line of the newest response out of view, and feedback notes follow
  the rule reported (the newest entry's notes plus those of the wrong
  entries just before it on the same step). (e) Noted: the session started
  from 724 tests where D53 recorded 723 (the content-only commit `3a47361`
  came between) — a count to confirm, not a failure. **Gap in the report:**
  `CLAUDE.md` §8 asks that every Amadeus string in the UI be traced to a
  Verified Reference entry; the report does not say this was re-run for
  the screens — the 4B-1 session re-runs it and reports it.
  **Karim, in session 4 (app I-12), verbatim:** "keep both —
  startPractice() after a finished attempt, and a practice run starting at
  an accepted hint request. To be written into Build Spec §7A item 1; step 4
  wires startPractice() to the screen that leads back to practice." D53
  wrote only the first half. The second half is now in §7A item 1: an
  accepted hint request made before any entry starts the run (a hint is
  recorded on a step attempt, §7A item 2, and a step attempt needs a run).
  **By delegation:** (f) **I-13 — browser storage refused** (the app showed
  an empty page). The app cannot keep the record, so it does not pretend
  to: like the second-tab notice, it shows only a notice and records
  nothing — `ui.noStorage.title` EN "DEIXEN cannot save your practice in
  this browser" / AR «لا يستطيع DEIXEN حفظ تدريبك في هذا المتصفح»;
  `ui.noStorage.body` EN "This browser is not letting DEIXEN store data,
  so no practice can be recorded. Allow this site to store data in your
  browser's settings, then reload this page." / AR «هذا المتصفح لا يسمح
  لـ DEIXEN بتخزين البيانات، لذلك لا يمكن تسجيل أي تدريب. اسمح لهذا
  الموقع بتخزين البيانات من إعدادات المتصفح، ثم أعِد تحميل الصفحة.» If a
  save fails later in a load, the same notice replaces the screen: nothing
  is ever shown as recorded that was not written (Restricted Areas,
  "never show success when nothing happened"). Build Spec §7B item 8.
  (g) **I-14 — the name as a word.** One key, `ui.brand.name` = "DEIXEN"
  (same in both files), for every place the name stands alone as a word
  and for the wordmark's accessible name; strings that contain the name
  inside a sentence keep it there; the drawn wordmark is a drawing, not
  text. Reason: the name is provisional (Constitution §1), so it should
  live in one place. Build Spec §7B item 9. (h) **I-15 — how elements read
  in "Booking as it stands"** (the panel list; the boards draw only the
  name and the segment). Rule: the panel lists the elements the Terminal
  would display at that moment, in the same order, with the number from
  the one numbering function (§4), and never a second form of an element:
  name → the name as displayed (`ALHARBI/SAAD MR`); segment → airline and
  flight number (`6X 403`, as drawn); `AP` → the element text as displayed
  (`AP 966110000000`); `TK` → the verified form `TK OK` + date + `/` +
  office (V-18); stored `SSR CTCM` → `SSR CTCM` only — the next field, the
  airline code, is the partly verified detail U-07, so the panel stops
  before it and needs no marker. Elements the Terminal shows as a training
  message (stored `SRCTCR`, U-07; `RF` before end of transaction, U-08)
  appear **without a number**, as the first sentence of that training
  message (the same text the Terminal shows, D34), labeled
  `ui.trainingLabel`; they may carry `ui.pnr.new`, never `ui.pnr.was`.
  After filing, `RF` is no longer listed (V-10). Nothing about Amadeus is
  claimed. Build Spec §7B item 6. Sync note: Claude Code saw an older
  `DEIXEN-KNOWLEDGE\DEIXEN-KNOWLEDGE\` sub-folder inside the main folder on
  Karim's computer and did not use it; Karim is asked to delete it. New
  strings (with D56): 7 keys in both string files, listed in `slice.json`
  `ui` — 216 keys in each file. Files changed: Build Spec (status, §7A
  items 1 and 11, §7B heading and items 6–10, §9), `slice.json`, both
  string files, 13, Execution Plan §7. Karim may reverse any of these.

- **Decision 56 — Leaving a running assessment or scenario inside the app.
  Closed — by delegation (D29), 2026-09-29.** Self-review (D17). Open since
  D52, moved before 4B by D54. K3 covers only closing the browser. Three
  options were weighed: (a) leaving ends the attempt as abandoned;
  (b) the attempt stays running and the learner can come back in the same
  load; (c) navigation disabled while it runs. (c) is rejected: the
  approved controls board says area links are "never disabled"
  (`P1-F-Controls`), and the assessment and scenario boards draw the
  navigation live (`P1-05`, `P1-06`); it would also leave no way out of a
  stuck attempt except closing the browser. (b) is rejected: the
  assessment is announced as "on your own" (`ui.assessment.intro`) and its
  result says the path works "on this occasion"; a learner could open a
  lesson or Ghost Mode mid-attempt and return, and "completed with every
  checklist item met" (§7A item 11) would not show it — this would change
  what the assessment means, which delegation may not do (Constitution §8).
  **Rule — (a), with a confirmation:** every way the app itself offers to
  leave a running assessment or scenario (an area link, the wordmark, the
  phone menu's Scope Disclosure link, and the browser's Back button if the
  app keeps browser history) first asks: `ui.leave.assessment` EN "If you
  leave now, this assessment ends and is recorded as abandoned — neither
  passed nor failed." / AR «إذا غادرت الآن، ينتهي هذا التقييم ويُسجَّل
  كـ«متروك» — لا ناجح ولا راسب.»; `ui.leave.scenario` EN "If you leave now,
  this scenario ends and is recorded as abandoned — neither passed nor
  failed." / AR «إذا غادرت الآن، ينتهي هذا السيناريو ويُسجَّل كـ«متروك» — لا
  ناجح ولا راسب.»; buttons `ui.leave.stay` EN "Stay" / AR «البقاء» (focus
  starts here) and `ui.leave.confirm` EN "Leave" / AR «مغادرة». Leave
  records `assessment_ended` / `scenario_ended` with `result` `abandoned`
  (existing event, no new field), ends the run, then goes where the
  learner chose; Stay changes nothing. Not leaving: switching language,
  opening or closing the phone menu, the DEIXEN drawer or the brief, the
  link to the area the learner is already in. After task completion the
  attempt has ended and nothing is asked. Abandoned attempts are neither
  passed nor failed and are skipped by Growth (§7A item 13), as with K3.
  Layout: the reset confirmation's pattern (`P1-08`) with existing tokens
  and control styles; the reset-action style stays reserved for Reset
  everything (`P1-F`). Build Spec §7B item 7, pointers in §7A items 1 and
  11 and §9. What a learner experiences: they can always leave, they are
  told first what leaving costs, and they can stay. Karim may reverse it.

- **Decision 57 — Rules for build step 4B. Closed — by delegation (D29),
  2026-09-29.** Self-review (D17). While preparing 4B the project lead
  found five places where the screens would have to guess; they are closed
  in Build Spec §7B items 11–15. No event field, event type or string is
  added, and nothing about Amadeus is claimed. (a) **The Flight Deck's one
  recommended action** (Build Spec §3 said only "from evidence; fresh
  learner → first Lesson"), computed at display time, first that holds:
  a required skill with `NEEDS_REINFORCEMENT` active → re-practise it
  (`ui.lesson.practise`, into the Terminal from its lesson); the first
  required skill in path order below `DEMONSTRATED_INDEPENDENT` → its
  lesson (`ui.lesson.start`); the assessment not yet completed with every
  checklist item met → Start assessment; the scenario not yet completed →
  Open scenario; otherwise Open Growth. Basis: LDS §23 (Advance, Reassess),
  §3, 07 D40 and the approved `P1-01` ("Next" on lesson 4 after `AN`,
  `SS`, `NM`). A current weakness comes first, as in Growth (§7A item 13).
  (b) **The practice run when the learner moves around:** it lives for the
  load (§7A item 1) — leaving the Terminal and coming back shows the same
  run. A lesson's or Ghost Mode's practice button starts a new practice run
  (`startPractice()`, app I-12) when the run's task is complete or the
  lesson's skill already has a `valid` entry in it — otherwise every entry
  would get `tm.sliceEnd` or repeat a step already done — and otherwise
  continues it; either way §7B item 1 (c) applies. (c) **Learning:** no
  lesson is locked (LDS §23 "Revisit"; the ten lessons are links in
  `P1-02`); the Learning area opens the recommended lesson, else lesson 1.
  (d) **Ghost Mode:** each start, including each Replay, records one
  `ghost_played` (a replay is a new start, §7A item 5); Pause records
  nothing. (e) **When the scenario and the assessment start.** The
  approved `P1-06` marks the Scenario Bank as the current area and shows
  the scenario screen before any entry, so opening it must not start
  anything: `scenario_started` is recorded at the learner's first entry or
  first accepted hint there (the same trigger as a practice run, §7A item
  1); until then nothing is recorded and leaving asks nothing (D56 applies
  only to a running one). The assessment starts when Start assessment is
  pressed, and the announcement shows then (07 Assessment contract). After
  either has ended, a new attempt can start the same way. Also: 4B-1 now
  includes the Scope Disclosure page, because the Flight Deck links to it
  (`P1-01`). Files changed: Build Spec (status, §7B items 11–15), 13,
  Execution Plan §7. Karim may reverse any of these.

### Decisions of 2026-09-30 — Phase 5, build step 4B-1 checked (by delegation D29)

- **Decision 58 — Build step 4B-1 (Flight Deck, Learning, Ghost Mode,
  Growth, Reset, Scope Disclosure) checked against the repository; app
  I-16 to I-20 answered; merge and tag at the start of session 7. Closed
  — by delegation (D29), 2026-09-30.** Self-review (D17), but not from the
  report alone: Karim connected `deixen-app` to the project chat, and the
  project lead read the repository **read-only** (nothing changed) — git
  history, `docs/ISSUES.md`, `docs/DECISIONS.md`, the test files and the
  code that decides the Flight Deck, Growth and the rows. Tests were not
  run by the project lead. Knowledge sync checked first: the GitHub main
  folder holds the files of 2026-09-29 (all five session-6 markers; 216
  keys in each string file). **Verified from the repository:** the app is
  in `C:\Users\DELL\Downloads\Documents\DEIXEN\deixen-app`, beside
  `DEIXEN-KNOWLEDGE` (so the "main folder" of earlier handoffs is
  `…\Downloads\Documents\DEIXEN\DEIXEN-KNOWLEDGE`); tag
  `step-4a-terminal` = `71427c5`; the content commit `58475d1` ("content:
  7 ui keys (07 D55–D56)") alone on `main`; `feature/screens-4b1` = one
  build commit `19fe327` and the docs commit `bb8b902`; not merged, not
  tagged; the three content copies byte-identical with the GitHub files;
  `tokens.css` sha256 as approved (D42); 112 screenshots in
  `docs/screens/4b1/` (7 screens × 8 widths × 2 languages — two viewed,
  `flight-deck-1440-en` matches `P1-01`). The code: the Flight Deck
  action is one pure function (`src/evidence/recommend.ts`) in the order
  of §7B item 11, with `FQD` excluded; Growth (`growth.ts`) follows §7A
  item 13; "the scenario completed" and the rows already mean completed
  with every checklist item met (`runs.ts` `scenarioCompletedMet`,
  `lastCompletedAssessmentMet`) — what D59 (a)–(b) now writes into the
  spec; the lesson strip, the practice buttons, Ghost Mode (one
  `ghost_played` per start and per Replay, reveals from the live engine),
  the storage guard and the booking-panel forms as §7B items 6, 8, 12–14
  say. Named tests exist for: every Flight Deck branch (hand-built events
  and on screen); the practice run between screens (the four cases of the
  session-6 prompt); Ghost Mode (per-start events, the next `CTC` not
  independent and the one after independent, the practice booking
  untouched, demo lines from the engine); Growth's outcomes in order,
  Ghost-only → empty, Reset confirm and Cancel; `lesson_completed` never
  skill evidence; storage refused on read, on write and later in a load;
  `RF` before and after filing; the notes rule; the Amadeus-string trace
  over the screens (`tests/ui/trace.test.ts`: the screens write no
  Amadeus text; each booking-panel form traced to V-07, V-11 or V-18 —
  the D55 gap is closed); the name key; the two scroll guards at five
  widths; the 8 widths × 2 languages for the new states; axe WCAG 2.1 AA
  on every new state in both languages at 1440, 1024, 768 and 390; a
  keyboard-only walk through all six; "no false affordance" (only the
  three controls of §7B item 4 disabled). `docs/DECISIONS.md` T7 now
  carries the notes-rule correction (the app had followed its own looser
  T7 wording; D55 (d) had recorded the rule as reported) and T8 quotes
  §7B item 11. **Only asserted by the report:** the test totals (943
  unit/component, 104 browser; the arithmetic 818 + 125 and 69 + 35 is
  right) and the final gate results (typecheck, build, manifest 69/69);
  the 17 planted faults — the repository holds no record of them, so
  which faults were planted cannot be checked. **Found missing:** no test
  shows a stored `SRCTCR` in "Booking as it stands" (the session-6 prompt
  asked for it; it shares its code with the tested `RF` row, but is not
  exercised); the "no false affordance" test does not visit Ghost Mode.
  Both are added in session 7 before the merge. **Also found:** the app
  keeps no browser history (T8), so the Back-button clause of D56 does not
  arise; screens change inside the app. **Open items, answered by
  delegation:** (a) **I-17 — no board draws a way into Ghost Mode**
  (`P1-03` draws Ghost Mode inside Learning; `P1-02` has no control for
  it; LXA §8.3 makes it learner-initiated from Learning). A gap, not a
  disagreement, so not a stop. Accepted as built: a link in the lesson's
  action row, between the practice button and Back to Flight Deck,
  worded `ui.ghost.title` ("Watch …" with the script's commands), in the
  existing link style. Build Spec §7B item 16. (b) **I-18 — Ghost typing
  speed.** `slice.json`'s note said setup entries at 15 ms per character
  and the lesson's own at 60; the approved `tokens.css` (D42), "the single
  source of every … motion … value", has `--motion-demo-key` (70 ms) and
  `--motion-demo-hold` (1200 ms), both 0 under reduced motion. The
  approved design is later than the note and owns motion (`CLAUDE.md`
  §4), so the tokens govern; the note is corrected to point to them; no
  token is added (a new token changes the approved design, which is
  Karim's). The longest script (`L09-FXP`) takes about 18 seconds.
  Learner-test watch point. Build Spec §7B item 17. (c) **I-16 — "In
  your task".** No per-lesson fact exists in the content, and for some
  lessons no sentence of the brief fits (`RF`); choosing one would be
  writing content (`CLAUDE.md` §3 rule 3). Accepted as built: the whole
  `task.brief`, words unchanged. Build Spec §7B item 18. (d) **I-19 —
  Ghost Mode has Pause and Replay but no "Play" word.** Accepted as
  built, as `P1-03` draws it: the script starts when the learner opens
  Ghost Mode, Pause is a toggle (`aria-pressed`) that resumes when
  pressed again, Replay starts again (one more `ghost_played`); no string
  added. (e) **I-20 — the Flight Deck on an empty record** shows
  Growth's empty state (`ui.growth.empty`, no basis sentence, Open
  Growth), as `P1-07b` draws it. Accepted. Also accepted: the lesson
  strip's items are links (§7B item 13); the Growth empty text is the
  approved string, not the board's older draft (D43); the Scope
  Disclosure page in the lesson's reading pattern with no current area
  (no board draws it). **Merge:** 4B-1 is accepted. Session 7 first adds
  the two missing tests and records the planted-fault list it can
  reconstruct, then merges `feature/screens-4b1` into `main` and tags
  `step-4b1-screens`. Files changed: Build Spec (status, §7B items
  16–18), `slice.json` (the `ghostScripts` note), 13, Execution Plan §7.
  Karim may reverse any of these.

- **Decision 59 — Rules for build step 4B-2 (assessment and scenario
  screens). Closed — by delegation (D29), 2026-09-30.** Self-review
  (D17). Preparing session 7, the project lead found three places the
  screens would guess, and one reading the spec left open. (a) **What "the scenario completed" means.** Build
  Spec §10 (K4) says Completed needs "the scenario completed"; §7A item
  13 and §7B item 11 (d) point to §7A item 11, which defines both "ended
  `completed`" (any task completion, including a bypass filing) and
  "completed with every checklist item met". The approved content file
  settles it: `slice.json` `scenario.acceptance` (approved by Karim, D28)
  says "Scenario completed = the full scenario path with every checklist
  item met; the CTC step satisfied by SRCTCR (not by bypassing the
  warning with a second ER)". So, everywhere a rule asks whether the
  scenario is completed — Growth's Completed status, the Flight Deck
  action (d), the scenario row — it means a scenario run **completed
  with every checklist item met** (§7A item 11). A scenario that ended
  with a bypass filing is recorded as `completed` (the event does not
  change) but does not count as the scenario completed. This follows
  approved content and the scenario's own constraint ("do not bypass the
  end-of-transaction warning"); it does not lower any standard. The 4B-1 code already reads it this
  way (D58). (b)
  **The scenario and assessment rows** on the Flight Deck and in Growth
  (D40 said "Completed" or a dash) show `ui.growth.completed` only when
  there is a run of that kind completed with every checklist item met;
  otherwise a dash. Reason: a row reading "Completed" beside an
  assessment that Growth counts as Needs More Practice would show a
  success the evidence does not support (`CLAUDE.md` §3 rule 5). (c)
  **The end of an assessment.** Nothing said where `ui.assessment.result`
  goes, or what shows when an assessment ends `completed` without every
  checklist item met (only a bypass filing can do that). Rule: at task
  completion in `TERMINAL_ASSESSMENT` the DEIXEN panel shows one note,
  once — `ui.assessment.result` if the run is completed with every
  checklist item met, otherwise the new `ui.assessment.resultUnmet` EN
  "The assessment has ended. Not every step counted as correct, so this
  result does not show the full path working. You can start a new
  assessment when you are ready." / AR «انتهى التقييم. لم تُحتسب كل
  الخطوات صحيحة، لذلك لا تُظهر هذه النتيجة أن المسار الكامل يعمل. يمكنك
  بدء تقييم جديد عندما تكون مستعدًا.» Never in the Terminal (D30). On
  phones the DEIXEN drawer opens itself for it, as for the announcement
  (`P1-05`), and closes with `ui.assessment.continue`. The note is not
  an event. Without (c) a learner who bypassed the warning would see the
  pricing display and no word that the attempt did not count. (d)
  **Leaving and areas.** The approved boards mark the current area:
  `TERMINAL_ASSESSMENT` is in the Terminal area (`P1-05`),
  `SCENARIO_SESSION` in the Scenario Bank (`P1-06`). So during a running
  assessment the Terminal link, and during a running scenario the
  Scenario Bank link, are "the link to the area the learner is already
  in" (§7B item 7): not leaving, nothing asked, nothing changes. Every
  other area link, the wordmark, the phone menu's Scope Disclosure link,
  ask first (D56); the app keeps no browser history (app T8), so
  the Back-button clause does not arise unless history is added. A lesson's or Ghost Mode's practice button can be pressed only
  on a screen reached by leaving, which has already ended the attempt;
  the bridge's refusal of those buttons while an attempt runs stays as a
  guard, and a test shows no such button can be on screen while an
  attempt runs. (e) **What the two screens hold** (from the approved
  boards, `P1-05` and `P1-06`, and §7B items 2, 15; D37): the same
  Terminal and DEIXEN panel as practice; the hint label and the hint
  levels (Partial Reveal only at `ER`); no Reset task and no Start
  assessment. Files changed: Build Spec (status, §7A item 13, §7B items
  11 (d) and 19–20, §10), `slice.json` (`ui` list, status), both string
  files (217 keys each), 13, Execution Plan §7. Karim may reverse any of
  these.

### Decisions of 2026-09-30 — Phase 5, build step 4B-2 checked and step 4 closed (by delegation D29)

- **Decision 60 — Build step 4B-2 (assessment and scenario screens, the
  leave question) checked against the repository and locked; 4B-1 merged;
  build step 4 (screens) complete. Closed — by delegation (D29),
  2026-09-30.** Self-review (D17), read-only from the repository as in D58
  (git history, `docs/DECISIONS.md` T8–T9, `docs/ISSUES.md`, the new test
  files); tests not run by the project lead. **Verified:** `main` =
  `8c7551f` = tag `step-4b2-screens` (merge of `feature/screens-4b2`:
  `fceb065` build, `dec5fb0` finish); tag `step-4b1-screens` = `4d544c4`
  (merge of 4B-1 with the close commit `d467f3a`); the content commit
  `ac787c0` ("content: ui.assessment.resultUnmet, Ghost note (07
  D58–D59)") alone on `main`; the three content copies byte-identical with
  the files of 2026-09-30 (217 keys; the content test now pins 217);
  `tokens.css` sha256 as approved. T9 records the bridge changes
  (`openScenario()` records nothing until the first entry or accepted
  hint; `attempt()`; `leaveAttempt()`; the refusals kept as a guard), the
  screens, the board differences, the "no false affordance" table for
  every screen and the 21 planted faults of 4B-2 with the test that caught
  each (all 15 the prompt named among them). A browser test exercises the
  four Definition of Done items on the built app: one hint-adjacent and
  one corrective-feedback-adjacent success excluded from independence
  (`scn.fb.warningShown` before `SRCTCR`), Error-Recovery Practice on `ER`
  on record, `TRANSFERRED` only for `CTC` and `ER` from independent
  scenario success (`AN` stays `CONSOLIDATED`), chain runs read through
  `chainId`. A browser test shows no history entry and no URL change: the
  app keeps no browser history, so D56's Back-button clause does not
  arise. T8 now lists session 6's 17 planted faults (the 13 the
  session-6 prompt named are among them; its "18th" was a real phone bug
  found by a test, not a planted fault). I-21 is recorded for step 5.
  **Only asserted:** the test totals — 944 unit/component and 104 browser
  at `step-4b1-screens`; 994 and 158 now (50 and 54 added, 0 failed) — and
  the typecheck, build and manifest results. **Correction to D58:** D58
  said no test showed a stored `SRCTCR` in "Booking as it stands". That
  was wrong: `tests/bridge/currentStep.test.ts` already had one at the
  bridge level (the row is `tm.ctcrLine`, no number, `new` then never
  `was`). The project lead's read searched only the test files it had
  copied, not the whole test tree. Session 7 added the panel-side test,
  which was the part really missing. Lesson: before saying a test is
  missing, search every test file. **Accepted:** (a) the board
  differences — `P1-05`, `P1-06` and their Arabic boards draw Nudge
  enabled before any wrong entry; built per §7B item 2, as for `P1-04a`
  (D55 a); the leave question uses `P1-08`'s layout without its danger
  rule and button (§7B item 7); the boundary line starts at the record
  column, not in the gutter (a drawing detail). (b) The assessment shows
  every answered entry of the load above its boundary, including entries
  made before a Reset task, so `ui.assessment.carryover`'s "They stay
  visible" is true of every entry `{N}` counts; a full reset empties it.
  (c) On a short phone the scenario's brief, objective and constraints
  give way and scroll before the Terminal does (spec §2: the Terminal
  workspace is never sacrificed) — found as a real bug at 320 × 568 and
  fixed; the phone key row left after the end note, fixed. (d) The phone
  assessment drawer keeps both Close and Continue (as `P1-05-390` draws);
  the 768 scenario starts with the brief folded. **Noted:** to rebuild
  session 6's fault list, Claude Code used the desktop app's session
  export, which left `session-export-1790735258194.zip` in Karim's
  Downloads folder; Karim may delete it. From now on each session
  records its planted faults in `docs/DECISIONS.md` as it goes. A
  knowledge marker with bold marks in it is hard to search; markers will
  be plain phrases. **State:** build step 4 is complete — all eight
  states of Build Spec §3 are built, wired and tested in both languages at
  every width. Definition of Done items still open: Coach at the five
  touchpoints (build step 5); the localization, accessibility and
  breakpoint pass (step 7); a learner completing the full path with real
  content (Karim's learner test, the Phase 5 gate). Build step 6
  (scenario and assessment) is built in 4B-2; what remains of it is
  checked with Coach in place. **Next:** the rules for build step 5 must
  be closed before its session: whether Coach speaks in the assessment
  ("on your own"); whether a Coach explanation beside a message counts as
  corrective feedback for independence (open since D52); where
  `coach.bypassRecorded` stands beside `ui.assessment.resultUnmet`; that
  Coach never opens the phone drawer by itself; the per-session
  same-category error count for the escalation offer (open since D53) —
  app I-21. Some of these touch what the assessment and the evidence
  mean, so each is checked against Constitution §8 before it is decided
  by delegation. Files changed: 13, Execution Plan §7.

### Decisions of 2026-09-30 — Phase 5, preparing build step 5 (by delegation D29)

- **Decision 61 — Rules for build step 5 (Coach); app I-21 closed.
  Closed — by delegation (D29), 2026-09-30.** Self-review (D17), with a
  read-only read of the app (`docs/ISSUES.md` I-21, `src/config.ts`, the
  panel and drawer code) and of the boards `P1-04b`, `P1-E`, `P1-07a`,
  `P2-Issues`. Knowledge sync checked first: the GitHub main folder holds
  the D60 files (07 "Decision 60", 13 "build step 4 complete", the
  Execution Plan "07 D60", 217 keys in each string file). The rules are in
  a new Build Spec **§7C** (10 items). No event field or event type is
  added; nothing about Amadeus is claimed beyond the Verified Reference.
  Each point was checked against Constitution §8 (what the assessment and
  the evidence mean): none changes how the assessment result, the hint
  label, independence or any skill state is computed.
  (a) **Coach explanations and independence** (open since D52). The Build
  Spec §8 test was applied to each of the six `coach.*` texts: none lets
  the learner type the correct entry without further trial. `coach.needTk`
  and `coach.missingCtc` name the missing element and restate what the
  verified message shows (V-09, V-13), at the level of the diagnostic
  `er.partial.*`; `coach.missingCtc` does not say which of the three forms
  fits the passenger — that is what made `scn.fb.warningShown` corrective
  at the readiness check, and it is shown at the same moment in the
  scenario and recorded as usual. The other four explain an output that
  has already happened or offer the lesson. So all are **diagnostic**:
  Build Spec §7A item 4 ("Coach explanations are not events") stands, and
  no recording mechanism is needed. Guard for later content: a Coach text
  that would pass the corrective test must be authored as a feedback item
  with `kind` `corrective`, never as a `coach.*` string (LDS §13: corrective
  content from any channel excludes the next success). §7C item 3.
  (b) **Coach in the assessment** (app I-21 item 1). File 06 names the
  Assessment as one of the five required touchpoints (Karim's Decision 9),
  so a silent Coach there would drop a required touchpoint; the option is
  not open to delegation either way. The explanations show as in practice:
  they are diagnostic, like the feedback texts already shown there, and
  "on your own" (`ui.assessment.intro`) already says in the same sentence
  that hints stay available and are counted. The escalation offer is not
  shown while an assessment or the scenario runs, because its lesson link
  would leave the attempt (D56); errors made there still count toward it.
  §7C items 5, 7.
  (c) **The bypass** (app I-21 item 2). Kept as Build Spec §6A item 2
  says: the feedback note (the judgment: the step does not count), then
  `coach.bypassRecorded` (the explanation: what a second `ER` does, V-13);
  one repeated clause accepted. `ui.assessment.resultUnmet` belongs to the
  completing `FXP` entry, a different step, so under §7B item 10 it never
  stands beside the bypass notes. §7C item 6.
  (d) **Placement** (app I-21 item 3). Coach texts are shown with the
  output they explain, in the entry's notes after its feedback note, under
  `ui.panel.coach` — as file 06 ("alongside"), the approved `P1-04b` and
  `P1-E`, and `P2-Issues` answer 07 ("Coach appears only with a coach
  string") have it; §8's "learner-initiated by default" governs help
  beyond that (hints; the escalation offer is the one unrequested help).
  They follow the notes rule of §7B item 10. On phones Coach never opens
  the drawer by itself: the drawer's existing "new" mark on the DEIXEN
  button signals it; the drawer opens by itself only for the assessment
  announcement and the end note, as now. §7C item 4.
  (e) **The escalation offer** (open since D53). Count = `invalid`
  `command_submitted` events with the same `skillId` and `errorCategory`
  in the current session (one app load), in any context; `out_of_scope`
  never counts; computed, never stored. Shown in Terminal practice only,
  with the entry that brings the count to `ESCALATION_ERROR_COUNT` (3,
  provisional, `src/config.ts`) and with every later such entry; suppressed
  when the skill, just before the entry, is `CONSOLIDATED` or
  `TRANSFERRED` without `NEEDS_REINFORCEMENT` active (Build Spec §8; LDS
  §15) — read before, because that error itself sets the modifier, so a
  state read after it would never suppress. It holds
  `coach.escalate` and a link to the skill's lesson, new
  `ui.coach.openLesson` — EN "Open lesson {N}" / AR «افتح الدرس {N}»;
  opening it records nothing and keeps the practice run. `coach.escalate`
  reworded without count-noun agreement, as in D39, because `{N}` can now
  pass ten and «{N} مرات» is wrong from eleven: EN "Errors of this kind on
  this step in this session: {N}. Do you want to open the lesson again?" /
  AR «عدد الأخطاء من هذا النوع في هذه الخطوة خلال هذه الجلسة: {N}. هل تريد
  فتح الدرس مرة أخرى؟» — meaning unchanged. §7C item 7.
  (f) **The five touchpoints**, each mapped to a screen and a moment
  (§7C item 9). Found while mapping them: on Growth, Needs More Practice
  caused by `NEEDS_REINFORCEMENT` could stand beside chain rows that all
  read "Correct in DEIXEN" (D40: the row follows the skill's state, which
  the modifier does not lower), so nothing said why — against file 06's
  Growth touchpoint ("explain meaningful outcomes and connect them to
  evidence"). Rule: when Growth shows Needs More Practice, a Coach note
  under the status says why, one sentence per reason that holds —
  `coach.growth.reinforce` EN "Needs practice again: {COMMANDS}. A new
  error came after earlier correct entries." / AR «يحتاج إلى تدريب من
  جديد: {COMMANDS}. ظهر خطأ جديد بعد إدخالات صحيحة سابقة.» and
  `coach.growth.assessmentUnmet` EN "The last assessment did not count
  every step as correct. A new assessment can show the full path working."
  / AR «آخر تقييم لم تُحتسب فيه كل الخطوات صحيحة. يمكن لتقييم جديد أن
  يُظهر المسار الكامل يعمل.» Existing patterns and tokens, no control, not
  an event. §7C item 8. **Stated openly:** the Learning touchpoint has no
  Coach note on the lesson page, because no approved Coach text is written
  for it; it is served by the recommended lesson, the lesson's explanation,
  "In your task", its next steps, and the escalation offer that leads back
  to the lesson. Learner-test watch point.
  Files changed: Build Spec (status, new §7C, pointers in §6A item 2 and
  §8), `slice.json` (`coachExplanations`, `ui`, `rules`, `status`), both
  string files (220 keys each), 13, Execution Plan §7. Karim may reverse
  any of these, and may change any word.

### Decisions of 2026-10-01 — Phase 5, build step 5 checked (by delegation D29)

- **Decision 62 — Build step 5 (Coach) checked against the repository and
  locked; app I-22 answered. Closed — by delegation (D29), 2026-10-01.**
  Self-review (D17), read-only from the repository as in D58 and D60 (git
  refs and history, `docs/ISSUES.md` I-21 and I-22, `docs/DECISIONS.md`
  T10, `src/evidence/coach.ts`, `src/bridge/coach.ts`,
  `src/evidence/growth.ts`, the whole test tree listed); tests not run by
  the project lead. Knowledge sync checked first: the GitHub main folder
  holds the D61 files, byte-identical with the project copies.
  **Verified:** `main` = tag `step-5-coach` = `37c204e` (merge of
  `feature/coach`: `46e1659`); the content commit `0f5bb0b` ("content:
  Coach strings (07 D61)") alone on `main` before the branch; the three
  content copies byte-identical with the D61 files (220 keys; the content
  test now pins 220); `tokens.css` sha256 as approved (D42); new test files
  `tests/bridge/coach.test.ts`, `tests/bridge/coachConfig.test.ts`,
  `tests/evidence/coach.test.ts`, `tests/ui/coach.test.tsx`,
  `tests/e2e/coach.spec.ts`. The code follows Build Spec §7C as written:
  the explanation is chosen from the engine's result (the verified source
  of the display, the filed state), never from Terminal text — exactly
  the five cases of §7C item 2, nothing for `tm.rfMissing` /
  `tm.otherMissing`; the escalation count reads only `invalid`
  `command_submitted` events with the same skill and category in the
  entry's session, any context; the offer only with a practice entry;
  suppression read from the skill states **before** the entry; the number
  only from `src/config.ts` (a test edits the config to 5 and sees the
  offer move); Growth's reasons come from the same two values that decide
  Needs More Practice, in path order with `FQD` last. T10 records the
  table of explanations with their V-numbers, the board differences, the
  five touchpoints walked in both languages, and the 22 planted faults
  with the test that caught each — **recorded as they were planted**, as
  asked. One fault (C18, the link's lesson number taken from the error
  count) was not caught at first, because the tests reached the offer only
  on lesson 3 at count 3; a test was added and the fault, planted again,
  was caught. **Only asserted:** the totals — 1070 unit/component and 187
  browser (994 + 76 and 158 + 29; the arithmetic is right), 0 failed — and
  the typecheck, build and manifest results; the 48 screenshots in
  `docs/screens/5/` were not viewed by the project lead. **Accepted:**
  (a) the board differences: `P1-04b` / `P2-AR-04b` draw only the Coach
  note after the refused `ER`; the build shows the feedback note, then
  Coach; `P1-E` "Completion" keeps the "Correct in DEIXEN" head before
  Coach — both what §7C item 4 says ("after its feedback note"). (b) The
  desktop margin's notes scroll and bring the newest into view, because at
  1024 and 1280 three refused `ER` with Coach and the offer ran over the
  hint buttons (found in the screenshots, fixed, tested); while it scrolls
  the notes block is a keyboard stop. (c) At the end of an assessment on a
  phone: the end note, then the completing entry's notes with
  `coach.fxpDone`, then the marker's words. (d) One older component test
  ("a bypass filing → …", a whole path plus Growth) given a 30-second
  budget because it ran past the 5-second default under load, before any
  change too; no assertion changed. **App I-22 — the escalation offer at a
  bypass:** built per §7C item 7 (a bypass is an `invalid` `ER` entry, so
  in practice it counts and can carry the offer); the session-8 brief's
  "only these two" was looser than the spec — the spec was right, as in
  sessions 2, 3, 3B and 4. Kept: after repeated failures to file the
  booking correctly, the offer to reopen the `ER` lesson is the help the
  escalation exists for (LDS §14: deeper-touch categories such as
  `MANDATORY_MISSING` escalate sooner). Written into Build Spec §7C item 6.
  **Noted for the learner test:** because assessment and scenario errors
  count toward the offer (§7C item 7), a learner returning to practice
  after a difficult assessment can see the offer at once with a high count
  (11 in the session's Arabic walk) — as designed; watch whether it reads
  well. **For build step 7 (the pass):** keyboard and screen-reader
  behaviour of the scrolling notes block at 1024–1440; in the phone drawer
  at 320 px the offer sits below the fold. **State:** build step 5 is
  complete. Definition of Done "Coach behaves correctly at all five
  touchpoints" is built and tested; Learning has no Coach note on the
  lesson page (D61 (f), watch point). Next: build step 6 (check the
  scenario and the assessment with Coach in place) and step 7 (the
  localization, accessibility and breakpoint pass), then Karim's learner
  test (the Phase 5 gate). Files changed: Build Spec (status, §7C item 6),
  13, Execution Plan §7. Karim may reverse any of these.

### Decisions of 2026-10-01 — Phase 5, preparing build steps 6 and 7 (by delegation D29)

- **Decision 63 — Rules for build steps 6 and 7 (the check and the pass).
  Closed — by delegation (D29), 2026-10-01.** Self-review (D17), with a
  read-only read of the app (`docs/DECISIONS.md` T9–T10, `docs/ISSUES.md`,
  the whole test tree listed, the accessibility and breakpoint browser
  tests, the panel and wordmark code). Knowledge sync checked first: the
  GitHub main folder holds the D62 files (07 "Decision 62", 13 "build step
  5 complete", the Execution Plan "07 D62", the Build Spec "app I-22").
  The rules are in a new Build Spec **§7D** (10 items). No event field,
  event type, string or token is added; nothing about Amadeus is claimed;
  each point was checked against Constitution §8 and none changes what the
  assessment, a scenario run or the evidence means — the two steps add
  checks and fixes, not behaviour. **Found in the repository** (what the
  existing tests do not yet prove): the automated WCAG check runs at four
  widths (1440, 1024, 768, 390), not all eight; no test checks touch-target
  size (file 04: ≥44 px primary, ≥24 px dense); reduced motion is tested
  only in Ghost Mode; no test checks the header wordmark is lockup B; the
  scrolling notes block made a keyboard stop in step 5 has no role or name
  (a focusable box a screen reader cannot describe); the phone drawer opens
  where it was left, so at 320 px the escalation offer can sit out of view;
  on desktop and 768 the end-of-assessment note comes after the completing
  entry's notes, so with the scrolling block it must be kept in view; and
  nothing checks the widths between the eight (browser zoom lands there:
  1280 at 200 % is 640). **Rules:** (a) build step 6 is a check, proved as
  a Definition of Done trace — every §13 line, its tests by name, and what
  was seen in the built app (§7D item 1); (b) the end note in view and
  announced at every width; the order built is kept (§7D item 2); (c) the
  scrolling notes block, while a keyboard stop, is a region named by the
  newest entry's visible head, with the same focus, keys and announcements
  as the rest (§7D item 3); (d) the phone drawer opens scrolled to the
  newest entry's notes; Coach still never opens it (§7D item 4); (e) what
  "the accessibility baseline passes" means for this build — eight checks,
  every state, both languages (§7D item 5); (f) the localization pass,
  including digits written as the approved Arabic boards write them (§7D
  item 6); (g) the breakpoint pass, every state × eight widths × two
  languages (§7D item 7); (h) lockup B tested; the trace re-run (§7D items
  8–9). **Stated openly (§7D item 10):** automated checks cannot prove how
  a screen reader speaks the app, whether the reading order is meaningful,
  whether the Arabic reads naturally, touch on a real phone, or the fonts on
  the learner's own computer. The pass saves the accessibility tree of each
  state so the project lead can read the order; Karim's learner test
  covers what a sighted learner meets; screen-reader use stays open and
  disclosed. **Session 9** runs both steps: part 1 (step 6, tag
  `step-6-check`), then part 2 (step 7, tag `step-7-pass`); if the session
  runs long after part 1 is tagged, part 2 continues in a new session with
  the same prompt. Files changed: Build Spec (status, new §7D, pointers in
  §2 and §13), 13, Execution Plan §7; content files unchanged (220 keys
  each). Karim may reverse any of these.

### Decisions of 2026-10-02 — Phase 5, build steps 6 and 7 checked (by delegation D29)

- **Decision 64 — Build steps 6 and 7 checked against the repository;
  app I-23 and I-24 answered. Closed — by delegation (D29), 2026-10-02.**
  Self-review (D17), read-only from the repository as in D58–D62 (git refs
  and history, `docs/DECISIONS.md` T11–T12, `docs/ISSUES.md` I-23 and I-24,
  the whole test tree listed, `vite.config.ts`, `src/styles/tokens.css`);
  tests not run by the project lead. **Sync:** the GitHub main folder did
  not yet hold the D63 files on 2026-10-02 (07 has no "Decision 63"); the
  copies on Karim's computer did, and session 9 read those. **Verified:**
  `main` = tag `step-6-check` = `f037880` (merge of `feature/step6-check`:
  `4ac85ae` I-22 closed, then four commits of step 6); `feature/step7-pass`
  = `2d13c8c`, ten commits after `step-6-check`, not merged, not tagged —
  as reported, because I-23 was a stop; `tokens.css` sha256 as approved
  (D42); new test files `e2e/step6.spec.ts`, `e2e/step7-notes.spec.ts`,
  `e2e/pass7.spec.ts`, `e2e/pass7-more.spec.ts`, `e2e/l10n7.spec.ts` and the
  shared walk `e2e/states.ts` (20 states and overlays). T11 holds the walk
  of the assessment and the scenario with Coach in place, the Definition of
  Done trace — every §13 line with its tests by name and what was seen —
  and the 13 planted faults of step 6, written as planted (one, S7, could
  not show at 1024 and was replaced by S7b, which was caught; S9 and S10
  use two different numbers, as asked after C18). T12 holds the 15 planted
  faults of step 7 (all caught), nine defects found and fixed with the test
  for each, the accessibility baseline item by item (axe at all eight widths
  with every overlay; keyboard; focus contrast; touch targets with the
  dense controls named — Reset task, Start assessment, the phone training
  strip; reduced motion; text spacing; 480 / 640 / 900; names and roles),
  the localization pass (digits: every approved Arabic board writes 0–9,
  and the app does too), the breakpoint pass (298 screenshots, which ones
  were looked at by eye and which were not), lockup B, the trace re-run
  (no Amadeus string without a source), 74 accessibility trees, what no
  automated check proved, and `CLAUDE.md` §8 line by line. **Only
  asserted:** the totals — 1070 unit/component throughout; browser 187 →
  204 after step 6 → 268 after step 7 (17 + 64; the arithmetic is right),
  two final runs in a row, 0 failed — and the typecheck, build and manifest
  results; the screenshots were not viewed by the project lead.
  **Accepted:** (a) the board differences of T12 — taller lesson links and
  Show brief buttons (file 04 touch targets), titles that wrap instead of
  ending in "…" (at 1024 the scenario's folded title can take four lines),
  two record lines kept above the open phone drawer (as `P1-05-390` draws),
  the Arabic lesson strip at the right edge (as `P2-AR-02` draws). (b) The
  unit suite's per-test time limit raised to 30 s (machine load; no
  assertion depends on it; 07 D62 had given one test the same) — a real
  hang now takes longer to show; failures that did not repeat when a fault
  was planted again were not counted, and T12 says so. **App I-23 — reduced
  motion and `--motion-demo-hold`.** The approved `tokens.css` sets four
  motion tokens to 0 under reduced motion but keeps the 1200 ms hold
  between Ghost Mode displays. D58 and Build Spec §7B item 17 said "both 0",
  and §7D item 5 (d) said "every motion token": the project lead's error,
  not the token file's. Decided: **keep the token file unchanged**; the
  spec is corrected. Reasons: nothing moves during the hold — it is a
  still pause for reading, which reduced motion does not ask to remove;
  with the typing already 0, a 0 hold would run a whole Ghost Mode script
  in one instant, so the learner would see only its last display; and
  changing `tokens.css` would change the approved design, which is Karim's
  (D29 item 2). **App I-24 — English words in the approved Arabic
  content** (`L02-SS.body` «البيع المختصر (short sell)»; the PRINT element
  names in `L03-NM.body`; "Received From" in `L07-RF.objective`,
  `er.partial.received`, `tm.rfMissing`, `tm.rfLine`; "fare basis" in
  `L09-FXP.body`; "Enter" in `ui.term.enterHint`). They are deliberate:
  the content Karim approved (D28) writes them as the terms and key names
  the learner meets in the real work. §7D item 6's list was incomplete;
  it now allows the English terms the approved Arabic content itself
  writes. The test already allows exactly the Latin words of the Arabic
  string file, so a new English word anywhere else still fails it. Learner-
  test watch point: whether they help. **Noted for the learner test:** the
  scenario's folded title at 1024; the taller lesson links on phones; the
  drawer opening at the newest note; on phones, notes added while the
  drawer is open are not announced to a screen reader (built as step 5
  left it). **State:** build step 6 is complete (tag `step-6-check`); build
  step 7 is complete on its branch; a short session 9B records the two
  answers, runs the suite, merges and tags `step-7-pass`. Every build step
  of `CLAUDE.md` §7 is then done. Definition of Done: every line is proved
  by tests and the walk except the first — a learner completing the path
  — which is Karim's learner test (D29 item 5); screen-reader use stays an
  open, disclosed item (D63). Files changed: Build Spec (status, §7B item
  17, §7D items 5 (d) and 6), 13, Execution Plan §7. Karim may reverse any
  of these.

### Decisions of 2026-10-02 — Phase 5, build complete; the learner test prepared (by delegation D29)

- **Decision 65 — Session 9B checked against the repository; build step 7
  merged; every build step done. Closed — by delegation (D29),
  2026-10-02.** Self-review (D17), read-only from the repository as in
  D58–D64 (git refs, `.git/logs/HEAD`, the commit and tree objects of the
  new commits, `docs/ISSUES.md`, `docs/DECISIONS.md` T12, the test tree
  listed, `tokens.css`, the content files); tests not run by the project
  lead. **Sync:** the GitHub main folder holds the D64 files (07 "Decision
  64"; the Build Spec "a still pause for reading each"; 13 "build steps 6
  and 7 checked"; the Execution Plan "07 D64"). **Verified:** session 9B
  made one commit on `feature/step7-pass`, `a697bce` (parent `2d13c8c`),
  then merged it into `main` with `3fdb342` (parents `f037880` =
  `step-6-check` and `a697bce`); tag `step-7-pass` = `3fdb342` = `main`;
  the merge's tree is the branch head's tree, so nothing changed in the
  merge. Between `2d13c8c` and `a697bce` only three files changed —
  `tests/e2e/pass7-more.spec.ts`, `docs/DECISIONS.md`, `docs/ISSUES.md`;
  `src/`, `content/` and `tokens.css` are untouched. The test file diff,
  read line by line: the reduced-motion test's name now says what §7D
  item 5 (d) says, and one comment and one failure message point to D64;
  the checks themselves are unchanged (the hold is still pinned at
  1200 ms, so a change to the token file is seen). `docs/ISSUES.md` marks
  I-23 and I-24 CLOSED by 07 D64, in the words of D64; T12 records both
  as closed and its `CLAUDE.md` §8 table reads ✔ on every line, leaving
  only "What no automated check proved". `tokens.css` is byte-identical
  with `design/phase4/tokens.css` (sha256 as D42); the three content files
  are byte-identical with the knowledge files, 220 keys in each string
  file. **Only asserted:** 9B's own final runs — 1070 / 1070
  unit/component and 268 / 268 browser, the slow test 2.1 s, typecheck
  and build passing, the 69 design files OK. T12's "Final runs" still
  records session 9's runs on `2d13c8c` (the slow test 2332 ms and
  2327 ms); 9B's runs are in its report only. Not blocking: the 9B change
  touched no code and no check. **Still open, as before:** app I-7 (`AN`
  checklist (b) rarely fails; curriculum expansion); screen-reader use
  (D63). **State:** every build step of `CLAUDE.md` §7 is done and merged.
  Definition of Done: every line is proved by tests and the walk except
  the first — a learner completing the full path — which is Karim's
  learner test (D29 item 5, Decision 66). Files changed: 13, Execution
  Plan §7.

- **Decision 66 — Karim's learner test (the Phase 5 gate) prepared.
  Closed — by delegation (D29), 2026-10-02**; the test itself and its
  verdict are Karim's (D29 item 5). The guide is a Claude doc written for
  Karim in Egyptian Arabic, "اختبار كريم كمتعلّم — DEIXEN"
  (https://claude.ai/code/artifact/1da6aae6-6619-41f0-b877-8243a623fe0f),
  with a report form inside it: a result per step (worked / confused /
  looked wrong / slow / not tried), notes, and the verdict (works — close
  Phase 5; works after the listed fixes; does not work). It teaches no
  Amadeus: the lessons in the app do. **How the app is opened:** a Claude
  Code session on `deixen-app` (Sonnet, Low effort) runs `npm run build`
  and `npm run preview -- --port 4173` and changes no file; Karim uses
  Chrome at `http://localhost:4173`, one tab, the same address every time
  (the record lives in that browser for that address). A built copy cannot
  be opened by double-click (the build loads its files from the site
  root). **Start:** an empty record — Growth, Reset everything (Cancel
  first, then confirm), or the empty state if nothing is recorded. **Order
  (14 steps, two sittings):** English — Flight Deck empty; lesson 1; Ghost
  Mode (and the longest script, `L09`); the full path with the lessons and
  hints; mistakes on purpose (an entry that is not a command; a broken
  entry; the same mistake three times → the escalation offer and its
  lesson link; Reset task); the full path alone, with `TK` left out once
  so `ER` is refused and then recovered (Error-Recovery Practice); the
  assessment; the scenario; Growth; a hard assessment (the same `AN`
  mistake four times) and then practice, to see the offer at once with a
  high count and the Growth Coach note. Then Arabic (lessons 2, 3, 7, 9
  for the English terms), widths in Chrome's device mode (1024 for the
  scenario title; 390 and 320 for the menu, the lesson links, the drawer
  and an assessment), and optional: reduced motion, a real phone on the
  home network (`--host`), a second tab, closing the browser in a running
  assessment. **Watch points folded in:** Ghost setup typing speed and "In
  your task" length (D58); no Coach note on the lesson page (D61); the
  escalation offer at once with a high count after a hard assessment
  (D62); the scenario's folded title at 1024, the taller lesson links on
  phones, the drawer opening at the newest note (D64); whether the English
  terms in the Arabic lessons help (I-24); the Ghost Mode hold under
  reduced motion, only if Karim uses it (I-23). Each Definition of Done
  line a sighted learner meets has a step. **What the test cannot cover,
  stated in the guide:** screen-reader use (open, D63; on phones, notes
  added while the drawer is open are not announced, D64); learners other
  than Karim (real learners' data is reserved to him, D29 item 3);
  browsers other than Chrome; whether the Amadeus content is right (the
  Verified Reference owns that; Karim notes anything that looks odd); touch
  on a real phone unless he does the optional step. **After the test:**
  Karim's verdict is recorded as his gate decision; each problem he finds
  becomes a fix through the usual prompt → report → check loop, then he
  re-tests only that part; a fix that changes the design, `tokens.css` or
  approved content is asked of him first (D29 item 2). Files changed: 13,
  Execution Plan §7. Karim may change any part of the plan.

### Decisions of 2026-10-02 — Phase 5 gate (Karim)

- **Decision 67 — Phase 5 closed after Karim's learner test. Closed —
  Karim, 2026-10-02** (D29 item 5). Karim ran the learner test of D66 on
  the build of D65 (`main` = `step-7-pass` = `3fdb342`) and recorded his
  results in the test document
  (https://claude.ai/code/artifact/1da6aae6-6619-41f0-b877-8243a623fe0f).
  **Verdict in the document:** "works, but what I wrote must be fixed
  first". **Decision in the project chat the same day:** close Phase 5
  now; the findings are not fixed inside Phase 5 but carried into the
  detour Karim plans before Phase 6 (its own governance decision, to be
  recorded separately), as input to its learning review (Step 2). One
  condition before the snapshot tag: the practice-run finding (below) is
  checked first, because a defect there would be frozen into the snapshot
  (detour package v1.8, Prompt 0). **What the test showed** (Karim's
  words, condensed): (1) Flight Deck — fine; his design notes are kept for
  later. (2) Lessons — written for someone who already understands; the
  terms are strange to a beginner; "the explanation itself needs an
  explanation". (3) Ghost Mode — clearly a demonstration, but the screen
  needs each part explained (where the time is, the cities, the airport);
  the text is too much and hard for a beginner; the `AN` explanation
  disappears as the commands grow. (4) Practice — after entering one
  command after another without going back to the Flight Deck, the
  booking started again from empty and the work was lost (reported; the
  exact steps are not known); training lines should look different when
  something is wrong and when it is right: a correct `RF` entry looked
  wrong to him because its training line looks like the error lines, and
  any entry answered by a training line confused him. **Per step:** works
  — opening and empty record, Flight Deck, deliberate mistakes; needs an
  explanation of the explanation — lesson 1; needs its parts explained —
  Ghost Mode; confused — first full path, assessment ("I don't
  understand anything"), scenario, Growth, Arabic; slow — the full path
  alone; not tried — the hard assessment, widths and phone, reduced
  motion, the optional checks. **What this closes and what it does not:**
  the Definition of Done line "a learner completes the full path end to
  end with real content" is met (Karim completed the path, the assessment
  and the scenario); the test also shows that the slice does not yet teach
  a true beginner well — that is a learning-quality finding, carried
  forward, not hidden. Not covered by the test: the steps not tried
  (above), screen-reader use (D63), learners other than Karim. Lessons or
  explanations that would teach new Amadeus facts still need the Verified
  Reference first (D12, D13). Files changed: 13. The Execution Plan's
  Phase 5 row is set to Done by the detour's own plan update (package
  Prompt 3), so the closure and the detour land in the plan together.

### Decisions of 2026-10-02 — The detour before Phase 6 (Karim)

- **Decision 68 — A four-step detour between Phase 5 and Phase 6. Closed
  — Karim, 2026-10-02** (D29 item 4: it changes the work sequence of the
  Execution Plan). This is the detour D67 names. After Phase 5 is closed
  (D67) and before Phase 6 (Expansion) starts, a deliberate four-step
  detour is inserted into `DEIXEN_Execution_Plan.md`. It is intentional,
  approved by Karim, short, and exists so that Phase 6 starts on
  better-informed ground. **The steps:** (1) External Engine / Open-Source
  Investigation → Technical Recommendation; (2) Learning Design + Learning
  Experience Review → Learning Decision; (3) Synthesize & Freeze Decisions
  (Engine + Learning + Product constraints); (4) Design Improvement Round
  (UX / UI / learning surfaces / Terminal experience) → Design
  Verification. Then Phase 6 (Expansion). **How the steps run:** each step
  is started separately by Karim and stops after its own deliverable. A
  step may state requirements it needs from other steps and surface
  labeled, non-binding candidates for them, but it never recommends,
  decides, or plans the execution of another step's outcome. The four
  steps run under a shared Detour Charter (v1.8), embedded as a block at
  the top of each step's prompt; it is not a repository file.
  **Authority:** steps 1 and 2 recommend within their own domain; step 3
  proposes the Freeze Package; step 4 improves and verifies the design
  inside the scope below. Nothing produced by a step binds until Karim
  explicitly accepts it. Steps 1, 2 and 3 modify nothing (no code,
  documents or decisions). **The Freeze Package** is step 3's handoff. It
  carries the Freeze (locked decisions + explicitly listed open items +
  the procedure for changing them) and everything step 4 and the closing
  report need from steps 1–3: the design scope (stated in full: the
  definition, the four limits, the exclusions and any file it names), when
  each accepted change must land (before step 4 / before Phase 6 / with
  Phase 6 / deferred), the consolidated ledger, the requirements and
  candidates step 4 must evaluate, the preserve list, and the cumulative
  coverage. Items are tracked as ledger rows with one ID each (`S1-01`,
  `S2-01`, `S3-01`, …), never renumbered by a later step; locked decisions
  are identified `F-01`, `F-02`, … and each cites the ledger row IDs it
  came from. The accepted Freeze Package is the only input step 4 takes
  from the earlier steps, and it binds step 4 and Phase 6. Its Freeze,
  design scope and landing times are then recorded here as a decision by
  Karim, and step 4 is prepared and run only after that record exists; the
  package is the working copy and 07 is the canonical copy of those parts.
  **Step 4** — only after the Freeze Package is accepted and recorded — may
  implement design changes inside the design scope defined by that
  package. Design scope = how existing engine and learning outputs are
  presented: layout, hierarchy, typography, color and semantic-state
  rendering (styling only), interaction patterns, Terminal presentation
  (styling and container only), and interface copy = text of the interface
  itself (navigation, controls, headings, empty and system states) that
  neither teaches nor carries Amadeus behavior. Limits that always apply:
  (1) engine output is rendered exactly as received: no reflow, trimming,
  re-alignment, truncation or rewording; (2) what the engine receives, and
  what counts as an attempt, hint, reveal or mastery, is unchanged; (3)
  when, whether and how much learning support appears (hints, Coach, Ghost
  Mode, Speed Drills, Scenarios, Assessment) is learning logic, not
  interaction design; (4) any text that teaches, instructs, hints,
  explains, assesses or gives feedback is learning content, not interface
  copy; if unsure, it is learning content. Excluded: engine behavior,
  learning logic and content, the wording of verified Amadeus output and
  training messages (how they are styled is semantic-state rendering,
  inside the scope), frozen files, governing documents and decisions. Step
  4 may create a new file only if the recorded design scope explicitly
  names that file; otherwise it edits existing files only. Step 4 works in
  isolation and reversibly (for example a separate branch), then verifies
  the resulting state; "no material design change" is a valid result. Its
  changes are proposals in code form and join the project only when Karim
  accepts the Detour Closing Report. Anything outside its authority goes
  through the return path. All other accepted changes (engine, learning,
  documents) are implemented as separate tasks started by Karim through
  the project's normal pipeline, on the schedule the Freeze sets. **Return
  path:** after the Freeze, if step 4 needs something outside its
  authority or something the Freeze lacks, it writes a change request,
  marks the affected item blocked, does not fake or work around it, and
  continues only with items that do not depend on it (or stops if none can
  continue). Karim decides. One round, affected item only. **The Detour
  Closing Report:** step 4 ends the whole detour with a report built from
  the Freeze Package and step 4's own results — a readiness statement for
  Phase 6, the frozen decisions, the design changes made and verified, the
  other accepted changes (grouped by when they must land) and what was
  deliberately preserved, and a coverage ledger (what was examined, what
  came out, what was deliberately left out and why). It is traceable from
  evidence to decision to change to verification. Karim reviews it,
  accepts or rejects the design changes, schedules the remaining
  implementation tasks, and starts Phase 6 himself. **Step 1** is an
  independent investigation run by Opus 5.5 in a clean session. It asks
  whether any open-source implementation, architectural idea, dataset, or
  evidence deserves to affect the engine or the way it is expanded in
  Phase 6. It also includes a short "Design-facing requirements" section
  describing what the engine, progress system, and messaging layer would
  need to expose so that a later UI can present learner feedback honestly;
  that section is a secondary lens only and is not a selection criterion.
  Target code: tag `phase-5-final` at commit
  `3fdb342429dc99ebf8268bad0da3075eacbd40a7` in the `deixen-app` repo. Its
  output is delivered in the chat reply only, with no new files and no
  modification to any repo or document. Its result is an advisory
  recommendation, not a gate, and is not treated as a formal independent
  review (D17). Any Amadeus behavior that surfaces from step 1 does not
  enter `DEIXEN_Amadeus_Verified_Reference.md`; it goes through the verify
  → spec → build → test path (D12, D13). The decision to adopt any
  external code is reserved to Karim (money/legal, D29 item 3). Files
  changed: 07. To follow (package Prompt 3): Execution Plan §3 (Phase 5
  Done, the four detour rows), §7 and its metadata; 13; file 00 §A10.

### Decisions of 2026-10-03 — The accepted Freeze of the detour (Karim)

- **Decision 69 — The accepted Freeze, design scope and landing times of
  the detour. Closed — Karim, 2026-10-03** (governance, reserved under D29;
  each F-item's Authority line names any other reserved matter). Karim
  reviewed the Freeze Package produced by detour step 3 (Decision 68) and
  explicitly accepted it on 2026-10-03; his changes of that day are
  included in the text below. As Decision 68 requires, this records the
  part of the package that belongs here, verbatim: the Freeze (locked
  decisions `F-01` to `F-21`, the explicitly listed open items, and how a
  frozen decision is changed), the design scope for step 4, and when each
  accepted change must land. The package is the working copy and this
  record is the canonical copy of those parts (Decision 68). The rest of
  the package — the consolidated ledger, coverage, requirements and
  candidates, preserve list — is not recorded here; the ledger row IDs
  (`S1-`, `S2-`, `S3-`) cited below live in the package. Where an F-item
  amends an earlier decision, its own Authority line says so (F-04: the
  chain word of D40; F-05: D57 (b); F-06: the carry-over wording of D39
  and D59 (c)); those decisions are otherwise unchanged. Changes to
  approved content (D28) and to other documents (03, 06, the Build Spec,
  the LDS) are named in each F-item's own lines, not listed here. Step 4 is
  prepared and run only after this record exists. Files changed: 07. The
  record follows, verbatim.

#### FREEZE RECORD — accepted by Karim, 2026-10-03

##### (a) The Freeze

**F-01 — What stays as it is.**

Decision: Keep through Step 4 and Phase 6:
- the pure engine (date, locator and filing time are inputs) (S1-01)
- the source on every output block, with the trace test (S1-02)
- one numbering function for every number shown (S1-03)
- line-for-line and pass/fail checklist tests as every command's template (S1-04)
- append-only events with skill states, independence and Growth derived on read (S1-05, S2-56)
- unbuilt cases stop; "not recognized" and "not covered" stay apart (S1-06)
- the Flight Deck's one action, honest empty state and planned labels (S2-50, S2-02)
- lessons tracing every Amadeus statement to a VERIFIED entry (S2-51)
- Ghost Mode on a separate demo booking: live-engine reveals, never above INTRODUCED, labelled, L08's verified refusal and recovery (S2-52, S2-08)
- the Terminal showing only Amadeus output plus one labelled training line, with DEIXEN's words in the panel (S2-53)
- blame-free feedback, one hint counter, three ordered help levels, the honest session label (S2-54)
- the escalation trigger (S2-55)
- the assessment contract as built (S2-57)
- the scenario (S2-58)

Sources: S1-01–S1-06, S2-02, S2-08, S2-50–S2-58.
What changes: nothing. Every later F-item keeps these.
Landing: none — keep as is; binding from acceptance.
Kind: none.
Authority: confirms 07 D23, D27, D30, D33, D37, D38, D47, D52, D56, D60 and the Assessment and Scenario contracts. No reserved matter. No change to approved content or design.
Reopen if: the re-test (F-11) or a verified behaviour shows one of these harms learning or blocks Phase 6.

**F-02 — Training lines: three roles, taken from the entry's result.**

Decision: Each training line — in the Terminal, and as a row in "Booking as it stands" — has one role, taken from the result of the entry whose response contains it, except a line that stands for a stored element (below):
- (i) Refused — not used; booking unchanged; result invalid. Keys: tm.notAccepted, tm.notForTask, tm.classNotOffered, tm.fxpBeforeName, tm.rfMissing, tm.otherMissing, and tm.noPracticeData when a checklist item failed.
- (ii) Accepted — the entry met the checklist, and DEIXEN shows its own line instead of an Amadeus display, because that layout is unverified or there is no practice data; result valid. Keys: tm.rfLine and tm.ctcrLine (including where they recur in later redisplays), and tm.noPracticeData after a valid AN for an airline without practice data.
- (iii) Outside what DEIXEN simulates — not an error; booking unchanged; result out_of_scope. Keys: tm.notRecognized, tm.notCovered, tm.sliceEnd, tm.secondName.

A training line that stands for a stored element (tm.rfLine, tm.ctcrLine, and any later key of this kind) takes the role of the entry that created the element, not of the entry whose redisplay contains it; the same holds for its row in "Booking as it stands".

The bridge exposes each training block's role. It derives the role in one place from the entry's result, additively and outside src/engine/. A test covers every key against every result it can appear with. Every key Phase 6 adds falls under the same rule and test.

These stay: the label "Training message" (D30), D33, D34, and every message's wording. In Step 4, the three roles must be told apart without colour alone, and a training line must never look like Amadeus text. Red stays reserved unless Karim changes tokens.css (S2-13). No role names are added. If Step 4 needs words, they are learning content and come through the content pipeline via the return path.

Sources: S2-14, S2-15, S2-40, S2-62, S3-01. Cites S1-27, S2-13, S2-71, S2-72, S2-77.
Learner benefit:
- Moment: every training line, above all RF and SRCTCR (main task and scenario), and every refusal.
- Change: the learner can tell an accepted line from a refused line from an outside-the-simulation line.
- How we'd know: in the re-test, RF and SRCTCR are read as accepted.
- Cost: one bridge field and its test, plus Step 4 design.

Landing: the exposure before Step 4; the presentation in Step 4.
Kind: engine (bridge) and design.
Authority: no reserved matter. No 07 change. No content change.
Reopen if: the re-test shows accepted lines still read as errors (then role names go through the content pipeline), or a new key fits no role.

**F-03 — The partly verified marker reads as a statement about the display.**

Decision:
- The marker stays where D27 and Build Spec §5 put it, and its details are never taught.
- The bridge exposes each Amadeus block's V-entry and its U-reasons, additively and outside src/engine/ (S1-26).
- Step 4 shows the marker as belonging to the display's layout — never to the entry or to a training line — and may link it to disc.6.
- A one-time explanation at the marker's first appearance (S2-78) is learning content. It names only a detail disc.6 already lists, never that detail's meaning, and it is written with F-09's annotations (one owner).

Sources: S2-45, S2-78. Cites S1-26, S2-71(f).
Learner benefit:
- Moment: the first AN display and the redisplays after AP, the contact SSR, TK and RF.
- Change: the learner no longer reads "not fully verified" as a verdict on their own entry.
- How we'd know: a re-test question.
- Cost: small.

Landing: the exposure before Step 4; the presentation in Step 4; the explanation before Phase 6.
Kind: engine (bridge), design, and learning content.
Authority: no reserved matter. No 07 change. The new explanation's wording is Karim's to approve (D28).
Reopen if: the re-test shows the marker is still read as being about the entry.

**F-04 — One term per meaning; reasons the learner can read.**

Decision:
- (A) Two terms, one meaning each. T1 means "this entry met DEIXEN's checklist": the panel, any valid entry. T2 means "this step counts as done on your own": the chain rows on the Flight Deck and Growth, at DEMONSTRATED_INDEPENDENT or higher. "Correct in DEIXEN" stays on exactly one of them; the other gets a new term, and disc.9 defines both.
  Karim's choice (2026-10-03): "Correct in DEIXEN" stays for T1 — the panel, as disc.9 already defines it; the panel label is unchanged. T2 gets a new term that says "on your own", written through the content pipeline in both copies (F-21). This amends D40's chain word.
  No token's job in tokens.css changes: green stays with "Correct in DEIXEN" (T1), so the T2 term is not green unless Karim later changes tokens.css.
- (B) Say why an entry doesn't count. When a valid entry will not count as done on your own, the panel says so after that entry and names the reason: a hint on this step, a demonstration of this command just before, or corrective feedback just before. The wording treats asking for help as normal practice, and never says how to make an entry count. Nothing is said before an entry.
- (C) Explain dashes and statuses. The Flight Deck and Growth say why a step shows a dash (no correct entry yet, or correct entries but none on your own). Growth explains "In progress" with one sentence per Completed condition still unmet, computed from the same values as the status. The three statuses get learner-facing definitions.

No evidence rule changes, and no new event or stored value is added.

Sources: S2-29, S2-30, S2-41, S2-63, S2-66, S2-81. Cites S1-30, S1-31, S2-19, S2-71(c), S2-72.
Changes:
- an evidence/bridge query: per entry, whether it counts as independent and why not
- a per-skill dash reason
- content in English and Arabic: the terms, the reasons, the dash and In-progress sentences, the status definitions, and disc.9

Learner benefit:
- Moment: after each valid entry, on the Flight Deck after a guided pass, and on Growth.
- Change: the learner knows whether a step counts, why not, and what is missing.
- How we'd know: in the re-test, the learner explains a dash and "In progress".
- Cost: two additive queries, short strings in two languages, and Karim's approval.

Landing: (A) and (B) — the T2 term, the reason sentences and the per-entry query — before Step 4. (C) before Phase 6.
Kind: engine (evidence/bridge), learning content, and design.
Authority: the term choice is Karim's, made 2026-10-03. It changes approved content: the D40 chain word, and disc.9 gains the T2 definition (D28).
Reopen if: learners avoid hints to keep credit (S2-81), or T2 is misread.

**F-05 — Practice-run continuity: no silent new booking; a returning learner is told.**

Decision: The run rules stay as they are: Build Spec §7A item 1 and §7B item 12, and the booking is not stored. What changes is what the learner is told:
- When a lesson's or Ghost Mode's practice button would start a new run while the current practice booking holds entries and its task is not complete, the app asks first, in the D56 pattern (stay, which changes nothing, or start new).
- When a new booking starts and nothing is lost — the task was complete, or the learner is returning after an assessment or the scenario — the learner is told once.
- On the first screen of a load, when the previous session recorded practice entries, the learner is told once that a practice booking is not kept between visits and that the record is. This is derived from stored events; no new storage.

These stay: the Flight Deck recommendation (D57 a), the Learning link (§7B item 13), and the escalation link to the skill's lesson (§7C item 7). The escalation link keeps its lesson target; a per-category target stays deferred (06). The booking stays unstored across reloads (F-15 b, c).

Sources: S1-15, S2-12, S2-21, S2-33, S2-36, S2-42, S2-61, S2-68. Cites S2-71(d), S2-77.
Changes:
- two bridge facts: "would this button discard a booking with entries?" and "did the previous session record practice entries?"
- system-state copy, as new ui.* keys written by Step 4
- Step 4's presentation

Learner benefit:
- Moment: moving from the Flight Deck, a lesson, Ghost Mode or the escalation link into the Terminal mid-path; returning after a break.
- Change: no work is lost unless the learner chooses it.
- How we'd know: the re-test reports no unexplained resets.
- Cost: two facts, one question, two notices.

Landing: the facts before Step 4; the presentation and copy in Step 4.
Kind: engine (bridge) and design.
Authority: adds a confirmation to the behaviour of D57(b) without changing when a run starts — Karim's, by accepting this Freeze. No other reserved matter.
Reopen if: the re-test still shows unexplained loss, or the question proves intrusive (then announce only).

**F-06 — Assessment: meaning kept as built, made legible.**

Decision: Keep what "completed with every checklist item met" means: a valid ER then a valid FXP, among the attempt's own events. The result means "works on this occasion" — not general competence, and not "done without help". Full Reveal is not excluded from "met": that would change what the assessment means (Constitution §8). Make it legible:
- (a) The end note states the hints used inside the attempt (already computed; exposed by the bridge).
- (b) The announcement says plainly what is assessed and how the result is decided, and does not imply "without help" while help stays available and counted.
- (c) The carry-over text says only what is true: earlier entries and hints in this session stay visible and are counted in the session hint label, and the result comes only from the assessment's own entries.
- (d) The end note is announced once, then stays findable on the assessment screen until the learner leaves. This refines §7B item 20 and D59(c).

Sources: S2-16, S2-37, S2-38, S2-65. Cites S2-57, S2-71(g).
Learner benefit:
- Moment: the start and the end of the assessment.
- Change: the learner knows what is checked and what the result means.
- How we'd know: in the re-test, the learner restates the result correctly.
- Cost: content in two languages, one bridge field, and the presentation of (d).

Landing: (d) in Step 4; (a)–(c) before Phase 6.
Kind: learning content, engine (bridge), and design.
Authority:
- Changes approved content: ui.assessment.intro, carryover (D39's wording) and result (D28).
- (d) refines D59(c) — Karim, by accepting this Freeze.
- The assessment's meaning does not change.

Reopen if: Karim rules that the assessment must show independence. That would be an owner decision changing what the assessment means.

**F-07 — Independence rules kept.**

Decision: Build Spec §7A item 6 and §8 stay unchanged:
- Any hint level on the step attempt — Nudge and Partial Reveal included — removes independence.
- A Ghost script reveals every skill whose entry it types on screen (D52 e). The alternative "reveal only the lesson's own skill" is rejected: it would credit an entry made right after watching it typed. Non-cumulative scripts stay open (S2-28, S2-74).
- A demonstration or corrective feedback affects only the next entry on that skill (D52 f). S2-32's consequence is accepted as a small risk, and F-04's wording must not reveal it.
- The lenient LDS passages (§8 line 638, §12 lines 775–777, §15 lines 914–922) get a note that Build Spec §8 governs.

Sources: S2-31, S2-32, S2-64. Cites S2-28, S2-56, S2-74, S2-81.
Landing: keep from acceptance; the LDS note before Phase 6.
Kind: documents.
Authority: confirms D52(e)(f) and the approved Build Spec. The LDS is draft authority.
Reopen if: learners who used a Nudge later fail without help, or learners exploit S2-32.

**F-08 — Starting point, orientation, lesson standard (owner decision).**

Decision:
- Owner decision: lessons assume a true beginner with no reservations, GDS or Amadeus knowledge. This replaces 03's "from theoretical knowledge"; D18 itself is unchanged.
- An orientation comes before the first command: what Amadeus is, what a booking (PNR) is, what an agent does, and why these nine steps. It sits at the start of lesson 1 (Karim, 2026-10-03); there is no separate unit, so 03's Lesson schema, which requires a practiceBridge, is unchanged.
- A lesson standard, owned by 06 and applied in the Build Spec and in every Phase 6 lesson:
  - the task's core first
  - every term defined in plain words at first use
  - the step's display shown and read, using V-14–V-18 field identities only
  - one line on why the step exists
  - facts the step doesn't need moved out of the core
  - nothing partly verified taught
- The ten lessons are rewritten in English and Arabic through Karim's pipeline.
- Terms the Verified Reference lacks — class-letter meaning, segment, waitlist, city vs airport codes, the expansion of "PNR" — go verify → spec → build → test first, or stay untaught.
- A glossary is deferred until after the re-test.

Sources: S2-04, S2-05, S2-06, S2-07, S2-25, S2-26, S2-59, S2-75. Cites S2-01, S2-51, S2-80, S2-83.
Learner benefit:
- Moment: before and during each lesson.
- Change: a beginner can follow without outside help.
- How we'd know: in the re-test, the learner explains the step before practising.
- Cost: a two-language rewrite and approval.

Landing: before Phase 6.
Kind: documents (03, 06, Build Spec), learning content, and verification.
Authority: reserved to Karim (D29 item 1). Changes 03 and approved content (D28).
Reopen if: the re-test shows the lessons are still not followed.

**F-09 — Reading the screen: field annotations (owner decision).**

Decision: Adopt LXA §22, which Build Spec §12 deferred "until real learner testing".
- Field annotations name the parts of each verified display — AN (V-14), sell response (V-15), FQD (V-16), pricing (V-17), PNR (V-18):
  - only from the field identities those entries record
  - never a U-item (the AN header number, class figures, E0, NVB/NVA/BG, the fare calculation and tax codes, the FQD penalty, date, stay and fare-type columns)
  - never the task's own line or value
  - "airport" only if verified; otherwise origin and destination
- In Ghost Mode, through an annotation step added to 06's schema (type / pause / reveal / annotate), with text written for the demonstration.
- In practice, on request, beside the learner's own displays. Diagnostic only: not events, no effect on independence.
- One owner for first-display explanations: these annotations, not Coach. The Learning touchpoint stays as D61 serves it, and is revisited after the re-test.
- Shown with the existing margin-note and leader pattern (S3-04).

Sources: S2-09, S2-10, S2-27, S2-35, S2-60, S2-67. Cites S2-11, S2-73, S2-78, S2-80, S3-04, S3-08.
Learner benefit:
- Moment: Ghost Mode and the first AN display.
- Change: the learner can name the departure time, origin, destination, flight and line-number columns.
- How we'd know: the re-test.
- Cost: the schema change, content, and a V-check. No engine change.

Landing: before Phase 6.
Kind: documents (06, Build Spec), learning content, build (bridge/UI), and verification.
Authority: reserved to Karim (D29 item 1; this is a feature the Build Spec placed outside D8A). Changes 06 and approved content.
Reopen if: annotations go unused or confuse.

**F-10 — Arabic.**

Decision:
- disc.6 in Arabic is corrected so it says DEIXEN marks these details and does not teach them («يعلّم» currently reads as the opposite).
- Before Phase 6 writes Arabic content, the re-test includes an Arabic check (lessons 2, 3, 7, 9, the Terminal, Growth), with reasons recorded. D64 (I-24) stays until then.
- Remembering the interface language across loads is deferred (it is a storage rule, §11).

Sources: S2-44, S2-69. Cites S2-20.
Landing: (1) before Phase 6; (2) within F-11; (3) deferred.
Kind: learning content.
Authority: an approved content change (D28).
Reopen if: the Arabic check finds a new cause.

**F-11 — Learner re-test, after Step 4 or at the start of Phase 6.**

Decision: The learner re-test runs after Step 4 or at the start of Phase 6 expansion, whichever Karim judges the better point to test the system as an expanding product. No second learner test runs now or before Step 4, and the re-test is not a condition for starting Phase 6. It covers:
- lesson 1 → Ghost Mode → first path → assessment → scenario → Growth
- the steps not tried in Phase 5 (the hard assessment, phone and tablet widths, reduced motion, the optional checks)
- the F-10 Arabic check
- a reason recorded for every result other than "worked"

Karim chooses the point and the learner (D29 items 3 and 5); 03 names Karim and his brother as the first validation users. A learner other than the owner is preferred. The result closes or reopens S2-17–S2-20 and tests those of F-02–F-10 that have landed by then. No new Execution Plan gate is added.

Sources: S2-01, S2-70, S2-79, S2-82. Cites S2-17–S2-20.
Landing: after Step 4 or at the start of Phase 6 — Karim's choice.
Kind: a learner test (Karim) and its preparation.
Authority: Karim's (D29 items 3 and 5).
Reopen if: not applicable — this is the check itself.

**F-12 — Off-task entries and the handler template.**

Decision:
- D33 stays.
- Before the first new command handler is written, the template separates simulating verified behaviour from judging the entry against the task. Refusing off-task entries then becomes one policy applied in one place.
- Each precondition rule carries its V-entry or training key; the builder chooses how.
- Condition: if Karim later lets a command apply a well-formed off-task entry — only once a verified way to undo exists (S2-24) — the assessment and scenario move to end-state objectives at the same time (S1-36).

Sources: S1-07, S1-20, S1-21, S1-34, S1-36, S2-23. Cites S2-24.
Learner benefit: none visible now; the behaviour is unchanged.
Landing: with Phase 6 — the first engine task.
Kind: engine.
Authority: none. D33 is unchanged.
Reopen if: XE, RT and IG stay out of Phase 6 for a long time.

**F-13 — Transaction model; no inventory yet.**

Decision:
- Before the first chunk that retrieves, changes or ends a filed booking (RT, IG/IR, XE after filing, ET, history displays), the engine keeps the working booking apart from the recorded one.
- Whether recorded versions are kept, and what each entry does, come only from verified behaviour.
- Conflict detection is not adopted: one recording tab (D47) and one learner.
- Inventory is not modelled until a chunk needs VERIFIED seat-dependent behaviour.
- Build Spec §6A item 9 stays for the slice.

Sources: S1-08, S1-09, S1-35. Cites S1-21.
Landing: with Phase 6, before that chunk.
Kind: engine, plus verification.
Authority: none.
Reopen if: a verified behaviour can't be expressed with the working/recorded split.

**F-14 — Command recognition.**

Decision:
- (a) Entries beginning APM or APE get tm.notCovered, as Build Spec §6 and D49(c) already require. Today they are shown in a form no source shows. Tests are added.
- (b) Before the first new command code, recognition moves to one registry: each code with its status, V-entry, handler and ordered pattern. A collision test and an existence test for every cited V-entry are added. Source links live in tested data, not comments; the stale dates.ts comment is fixed there. The idea comes from GDS-Trainer (MIT); no code is copied.

Sources: S1-10, S1-11, S1-12, S1-22, S1-33.
Learner benefit: (a) removes an invented display.
Landing: (a) before Phase 6; (b) with Phase 6.
Kind: engine.
Authority: (a) applies D49(c); no change.
Reopen if: an APM display becomes verified, or Phase 6 adds only a few codes.

**F-15 — Evidence schema and storage.**

Decision:
- (a) Phase 6 schema changes are additive only — older stored data still validates — under schemaVersion 1.
- (b) Decided by Karim, 2026-10-03 (S1-37): keep the reset. When the stored format changes, the old record is wiped, not migrated (03 Persistence unchanged). Reopened only if a learner would lose meaningful progress (03's own trigger).
- (c) The booking stays unstored, and the returning learner is told (F-05).
- (d) Before the chunk that adds Speed Drills, or any chunk that multiplies events: measure event size against the storage limit, and tell a full store apart from refused storage, with its own approved notice (S1-32).

Sources: S1-13, S1-14, S1-23. Cites S1-15, S1-32, S1-37, S2-61.
Landing: (a), (b) and (c) from acceptance; (d) with Phase 6.
Kind: engine (evidence) and content (the notice).
Authority: (b) is Karim's decision (03; D8A "persistence redesign"; D29 item 3).
Reopen if: the measured size stays far below the limit, or a learner loses meaningful progress.

**F-16 — Varied task instances.**

Decision: From Phase 6 on, each chunk carries at least CONSOLIDATED_COUNT (2, provisional) fictional task instances of the same verified pattern, and practice repetition draws on different instances. Which instance the assessment uses is Karim's, per chunk. The slice keeps its one task until the first chunk.

Sources: S2-39, S2-48, S2-76.
Landing: with Phase 6, in the first chunk.
Kind: engine (bridge) and content.
Authority: the assessment-instance rule is Karim's (Constitution §8).
Reopen if: never measurable otherwise — Karim's judgment.

**F-17 — Before Speed Drills and new scenarios.**

Decision:
- Speed Drills keep 06 and LDS §17's rules: no invented threshold, wrong reps excluded and their rate shown, never feeding Growth, gated at CONSOLIDATED.
- Before their chunk, decide: the drill context (an additive value), how each rep gets a fresh booking state, the timing unit (changing 06's characters-per-minute measure is Karim's), and a keystroke-safe entry field (S2-22).
- Before a second scenario: scenarios become a list. Which scenarios Completed requires is Karim's (it changes K4, §10).

Sources: S2-22, S2-46, S2-47.
Landing: with Phase 6, before those chunks.
Kind: engine (evidence), UI, and documents.
Authority: a 06 change or a K4 change is Karim's.
Reopen if: Speed Drills are dropped from Phase 6.

**F-18 — Teaching boundary and external leads.**

Decision:
- Every Amadeus statement any F-item needs comes only from VERIFIED entries. Anything missing goes verify → spec → build → test (D12, D13).
- Step 1's leads — Service Hub error-message pages (S1-17) and practitioner or fixture leads (S1-18) — enter only that way, with their chunk. A verified message replaces the training line in place.
- No external simulator, code or data is adopted (S1-19).
- Adopting or licensing external code or data, real code lists included, is Karim's (D68; D29 item 3).

Sources: S1-17, S1-18, S1-19, S1-25, S2-80. Cites S1-39.
Landing: a standing rule; the leads with their chunks.
Authority: restates D12, D13 (never delegable) and D68.
Reopen if: never lowered.

**F-19 — Reproducible test evidence.**

Decision:
- Tracked docs/screens/ and docs/a11y/ change only when what they show changes.
- Tests pass a fixed locator source through the bridge's existing random dependency; locators stay six A–Z/0–9 characters, and the app keeps a fresh random locator per ER (§7A item 16).
- Tests run with a fixed time zone.
- The first run after the change confirms that the 209 files are no longer rewritten.

Sources: S1-16, S1-24, S1-38, S3-07.
Landing: before Step 4, so that Step 4's scope audit isn't buried in rewritten files.
Kind: engine (bridge test seam, e2e helpers, playwright.config.ts).
Authority: none.
Reopen if: the files prove already stable.

**F-20 — Session instructions before Step 4.**

Decision: Before Step 4, Karim removes or replaces the older CLAUDE.md in C:\Users\DELL\Downloads\ (pre-D45). Every Claude Code session under that folder loads it, and it contradicts the design/phase4/ rule.
Status: done by Karim, 2026-10-03 — the older CLAUDE.md, 07 and 13 copies in C:\Users\DELL\Downloads\ were deleted.

Sources: S3-02. Cites S3-03.
Landing: before Step 4.
Kind: housekeeping (Karim).
Authority: Karim's files.

**F-21 — Approved content: both copies, one approval.**

Decision:
- Any change to the three content files (D28) leaves the app copy and the knowledge copy byte-identical when it joins the project.
- DEIXEN-KNOWLEDGE is not under version control. So a change made on an isolated branch is made in the app copy only, and listed key by key — verbatim, in both languages, with the three files' sha256. Karim's acceptance task then copies it into the knowledge folder.
- Learning content changes only through Karim's content pipeline.

Sources: S2-83, S3-05.
Landing: standing.
Authority: restates D28; settles package v1.8 §14 item 8 (the two copies are identical when the change joins the project).

**Open items** (13, by ID; status as of 2026-10-03):
- S1-37 — migrate or wipe the stored record when its format changes. Closed by Karim, 2026-10-03: keep the reset (wipe), F-15(b); reopened only if a learner would lose meaningful progress.
- S2-03 — Karim's Flight Deck design notes. Closed by Karim, 2026-10-03: there are no notes before Step 4; Step 4 uses only what is recorded.
- S2-13 — red for wrong entries, while tokens.css reserves red for Reset everything and colour alone fails WCAG 1.4.1. Decided for now by Karim, 2026-10-03: tokens.css is not changed; the roles are told apart by shape and label (F-02). Open again after the re-test (F-11).
- S2-17, S2-18, S2-19, S2-20 — learner-test results with no reason recorded: the full path alone "slow"; the scenario, Growth and Arabic "confused". Open — they resolve at the re-test (F-11), after Step 4 or at the start of Phase 6.
- S2-24 — reverse D33 (apply a well-formed off-task entry and teach recovery) once a verified undo exists. Open — Karim; it opens when an undo (for example XE) is VERIFIED and Karim wants recovery practice (F-12).
- S2-28, S2-74 — cumulative or non-cumulative Ghost Mode scripts. Open — Karim decides before the first Phase 6 Ghost script; if the re-test (F-11) has not run by then, it is decided without re-test evidence.
- S3-03 — the master DEIXEN-KNOWLEDGE/CLAUDE.md differs from the app copy in the §4 design-path line; the app path is the one that resolves. Decided by Karim, 2026-10-03: the master copy is made identical to the app copy. Closes when that is done.
- S3-06 — who runs Step 4. Closed by Karim, 2026-10-03: Step 4 runs in Claude Code, Opus 5.5, Max effort, on a separate branch in deixen-app.
- S3-08 — because of this Freeze's timing, lessons, the orientation, annotations, and the assessment and Growth wording land after Step 4, so their presentation is built by later tasks with existing patterns, not by the design round. Open — checked by the re-test (F-11).

**How a frozen decision is changed**

- Who: only Karim changes an F-item, the design scope, a landing time, or an open item's status. D29 delegation does not reach them. Details an F-item expressly leaves to a later spec, a chunk or the builder are not frozen; they follow the normal pipeline.
- On what evidence: new evidence that materially contradicts the item (Constitution §11). That means the F-item's own reopen evidence, a verified Amadeus fact, the re-test, or a Step 4 change request that passes the gap test. D12 and D13 are never lowered.
- Through which record: a new 07 decision by Karim naming the F-ID changed, the evidence, the new text and what it supersedes, followed by the Constitution §15 impact check. The recorded Freeze is not edited in place.
- During Step 4: the return path — a change request, the affected item blocked, one round, Karim decides. A Freeze change is recorded before Step 4 continues on that item.
- Open items close only by Karim's decision, or by the evidence they name, recorded in 07.

##### (b) Design scope for Step 4

Definition (charter, verbatim): Design scope = how existing engine and learning outputs are presented: layout, hierarchy, typography, color and semantic-state rendering (styling only), interaction patterns, Terminal presentation (styling and container only), and interface copy = text of the interface itself (navigation, controls, headings, empty and system states) that neither teaches nor carries Amadeus behavior.

Limits that always apply:
- (1) engine output is rendered exactly as received: no reflow, trimming, re-alignment, truncation or rewording;
- (2) what the engine receives, and what counts as an attempt, hint, reveal or mastery, is unchanged;
- (3) when, whether and how much learning support appears (hints, Coach, Ghost Mode, Speed Drills, Scenarios, Assessment) is learning logic, not interaction design;
- (4) any text that teaches, instructs, hints, explains, assesses or gives feedback is learning content, not interface copy; if unsure, it is learning content.

Excluded: engine behavior, learning logic and content, the wording of verified Amadeus output and training messages (how they are styled is semantic-state rendering, inside the scope), frozen files, governing documents and decisions.

Step 4 may create a new file only if the recorded design scope explicitly names that file; otherwise it edits existing files only. Only an explicit owner decision can widen this scope.

Narrowed by this Freeze:

Design files
- src/styles/tokens.css is not edited. It is the approved design (D42; D29 item 2; CLAUDE.md §4).
- Role tokens are used only for the jobs their comments state. Green means "Correct in DEIXEN"; red means the one irreversible action, Reset everything (S3-10).
- Any other need goes to Karim as a change request.
- Boards and typefaces stay as approved. The design/phase4/ boards, the canvas, the typefaces and lockup B are not edited. Step 4 lists each board difference it creates, with the F-ID or row it serves.

Source paths (deixen-app)
- May edit: src/ui/** only.
- src/ui/terminalModel.ts and other src/ui files only map bridge outputs to presentation. They compute no result, role, independence, skill state or evidence.
- Must not edit: src/App.tsx, src/main.tsx, src/engine/**, src/evidence/**, src/bridge/**, src/config.ts, src/i18n/**, src/styles/**, index.html, package.json / package-lock.json (no new dependency), vite.config.ts, playwright.config.ts, tsconfig.json, CLAUDE.md, .claude/**, .gitignore, docs/licenses/**.

String files — app copies only
- Files: content/en/text.json and content/ar/text.json, English and Arabic changed together.
- Existing keys whose wording may change (37): ui.nav.areas, ui.nav.homeLink, ui.nav.language, ui.nav.menu, ui.nav.close, ui.chain.label, ui.task, ui.status, ui.objective, ui.lesson.back, ui.lesson.inYourTask, ui.fd.openGrowth, ui.fd.openScenario, ui.ghost.pause, ui.ghost.replay, ui.ghost.practise, ui.term.history, ui.term.entryLabel, ui.term.send, ui.term.enterHint, ui.term.sending, ui.term.startAssessment, ui.keys.label, ui.keys.type, ui.brief.show, ui.brief.hide, ui.brief.pinned, ui.brief.unpin, ui.brief.constraints, ui.hints.title, ui.hints.levels, ui.assessment.continue, ui.growth.recorded, ui.growth.recordedHere, ui.growth.statuses, ui.growth.assessmentRow, ui.reset.cancel.
- New ui.* keys may be added only for F-05's system states, and for headings or control labels Step 4's layout needs. Each is registered in content/data/slice.json ui — the only change allowed in slice.json. None may teach, instruct, hint, explain, assess, give feedback, or carry Amadeus behaviour.
- Every other key is excluded (62 interface keys): ui.trainingLabel, ui.unverifiedMarker, ui.correctInDeixen, ui.hintLabel, ui.assessment.intro, ui.assessment.carryover, ui.assessment.result, ui.assessment.resultUnmet, ui.assessment.starts, ui.abandoned, ui.what.assessment, ui.what.scenario, ui.growth.completed, ui.growth.inProgress, ui.growth.needsPractice, ui.growth.empty, ui.growth.basis, ui.reset.confirm, ui.reset.everything, ui.oneTab.title, ui.oneTab.body, ui.dataReset, ui.noStorage.title, ui.noStorage.body, ui.leave.assessment, ui.leave.scenario, ui.leave.stay, ui.leave.confirm, ui.coach.openLesson, ui.lesson.start, ui.lesson.practise, ui.ghost.title, ui.ghost.progress, ui.pnr.asItStands, ui.term.resetTask, ui.chain.next, ui.chain.optional, ui.planned, ui.ghost.demoBooking, ui.ghost.watching, ui.ghost.explain, ui.mode.practice, ui.mode.demonstration, ui.mode.assessment, ui.mode.scenario, ui.panel.feedback, ui.panel.coach, ui.hints.nudge, ui.hints.partial, ui.hints.full, ui.pnr.new, ui.pnr.was, ui.area.flightDeck, ui.area.learning, ui.area.terminal, ui.area.scenarioBank, ui.area.growth, ui.brand.name, ui.lang.en, ui.lang.ar, ui.fd.moreScenarios, ui.fd.csTrack.
- Also excluded: every non-ui key — lessons, task, scn.*, feedback, reveal.*, nudge.*, tm.*, coach.*, disc.*.
- Knowledge copies are not edited by Step 4 (F-21).

Tests and evidence files
- Tests Step 4 may edit: existing files in tests/ui/ and tests/e2e/, and the key-count pin in tests/content/content.test.ts.
- New test files: only tests/ui/step4.test.tsx and tests/e2e/step4.spec.ts.
- Tests Step 4 must not edit: tests/engine/, tests/evidence/, tests/bridge/, tests/i18n/.
- Evidence files: the verification loop may rewrite existing files in docs/screens/ and docs/a11y/. Any new evidence file goes only inside docs/screens/step4/ or docs/a11y/step4/.
- Step 4 may edit docs/DECISIONS.md and docs/ISSUES.md.
- Any other new file → change request.

Placement and isolation
- D30 placement: nothing but Amadeus output and the training line goes among the Terminal's record lines. Notices and system states go in the sheet head or the panel.
- Isolation: a feature branch in deixen-app, from the base snapshot below. Step 4 merges nothing into main and does not modify DEIXEN-KNOWLEDGE.

##### (c) Landing times

**Before Step 4.** These run as Karim-started tasks, after Prompt 6 records the Freeze; Prompt 7 then runs after them. Step 4 depends on all six:
1. F-02 — role per training block (bridge).
2. F-03 — V-entry and U-reasons per Amadeus block (bridge).
3. F-04 (A) and (B) — the T2 term and the reason sentences (content pipeline, both copies), and the per-entry independence-and-reason query.
4. F-05 — the two bridge facts.
5. F-19 — reproducible tests.
6. F-20 — the stray CLAUDE.md removed or replaced (done by Karim, 2026-10-03).

Base-snapshot rule. The first before-Step-4 task starts from phase-5-final; each later one starts from main after the previous one has landed. Step 4 branches from the main commit where items 1–5 have landed and been checked and item 6 is done (F-20 is outside the repository). Karim tags it (he names it when he creates it), and the Step 4 prompt carries the tag and its full SHA. Step 4 checks that HEAD equals that SHA and that the tree is clean, else it stops. If Karim accepts no before-Step-4 change, the base is phase-5-final = 3fdb342429dc99ebf8268bad0da3075eacbd40a7.

If a dependency has not landed:
- F-19 or F-20 missing → Step 4 does not start (its precondition).
- Items 1–4 missing → the dependent Step 4 item is blocked through the return path (change request, one round, Karim decides), never faked:
  - item 1 → the F-02 presentation
  - item 2 → the F-03 presentation
  - item 3 → S2-71(c), attempt vs progress
  - item 4 → the F-05 question and notices
- Step 4 continues with the items that don't depend on it.

**Before Phase 6.**
- F-14(a)
- F-03 explanation
- F-04(C)
- F-06(a)–(c)
- F-07 LDS note
- F-08, F-09, F-10(1)
- Owner decision due: S2-28/S2-74, before the first Phase 6 Ghost script.

**After Step 4 or at the start of Phase 6 — Karim's choice.**
- F-11, the learner re-test, with F-10(2), the Arabic check.

**With Phase 6.**
- F-12, the first engine task
- F-14(b), before the first new code
- F-13, before the first filed-booking chunk
- F-15(d), before an event-multiplying chunk
- F-16, the first chunk
- F-17, before its chunks
- F-18 leads, with their chunks

**Deferred.**
- inventory (S1-09)
- real code lists (S1-39)
- a middle help level (S2-34)
- retention and the Customer Service track (S2-43, S2-49)
- a glossary (part of S2-75)
- changing the demo window (S2-32)
- remembering the interface language (F-10(3))
- the escalation offer's per-category matrix (06)

**Standing from acceptance:** F-01, F-07, F-15(a)–(c), F-18, F-21.

### Decisions of 2026-10-03 — Prompt 7 and the Constitution's repository address (Karim)

- **Decision 70 — Prompt 7 (the DEIXEN Design Exploration Skill) is
  authorized. Closed — Karim, 2026-10-03** (D29 item 4: it adds an action
  to the detour's sequence). Karim authorizes Prompt 7 of the detour
  package (`DEIXEN_Detour_Prompt_Package_v1.8.md` §11), as that package
  defines it. It is an auxiliary tooling-preparation action: **not** a
  fifth detour step, not a governance stage, and not a source of
  authority. **When:** after the before-Step-4 tasks of Decision 69 (c)
  have landed, and before the session that prepares the Step 4 prompt;
  Karim reviews the Skill and accepts or rejects it as a usable tool
  before Step 4 is prepared. **How:** a fresh Opus 5.5 session, Max
  effort, with the current 07 (including Decision 69), the Execution Plan,
  the DEIXEN product and design sources, and web access. **What it may
  change:** only the Skill's own files, in an isolated skill workspace,
  outside `deixen-app` and `DEIXEN-KNOWLEDGE`; if installing it would
  change a DEIXEN repository or a canonical document, it stops and
  returns install-ready files instead. **What it may not do:** apply the
  Skill to DEIXEN, choose or propose a DEIXEN visual direction, change the
  Freeze, the design scope or any decision (Decision 69), or widen Step
  4's scope. Anything the Skill later surfaces outside the recorded scope
  is non-binding and goes through the return path (Decision 68). Step 4
  may use the accepted Skill as an optional tool only. Closes the 13 row
  "Prompt 7 … has no recorded authorization". Files changed: 07, 13,
  Execution Plan §3/§7, 00.
- **Decision 71 — The Constitution's repository address. Closed — Karim,
  2026-10-03** (D29 item 4: a change to the governance set). Operating
  Constitution §5 names the project repository as
  `https://github.com/deixenlabs/DEIXEN-KNOWLEDGE` — the repository the
  Project syncs from. The file has carried this address since 2026-09-25,
  recorded then as a factual correction with Karim informed; Karim now
  decides it as his own governance change, and the Amendment Record's
  authority for that row now cites this decision. The copy of the
  Constitution pasted into the claude.ai Project's instructions still
  shows the old address (`malikmalik168200-design/DEIXEN-KNOWLEDGE`);
  Karim updates that copy (only he can edit the Project's instructions).
  Until he does, the file in the repository is the version that counts
  (Constitution §5 item 4). Files changed: 07, the Constitution
  (Amendment Record), 13, 00.

### Decisions of 2026-10-04 — Before-Step-4 task 1, F-19 (by delegation D29)

- **Decision 72 — F-19 (reproducible test evidence) landed; checked
  against the repository. Closed — by delegation (D29), 2026-10-04.**
  Before-Step-4 task 1 of Decision 69 (c). F-19's Authority line is
  "none", so its technical choices were the project lead's and Claude
  Code's. Self-review (D17), read-only from the repository as in D58–D65
  (git refs and `.git/logs/HEAD`; `tests/e2e/helpers.ts`, `shots.ts`,
  `shotCompare.ts`; `tests/shots/shotCompare.test.ts`; `playwright.config.ts`;
  `vite.config.ts`; `src/bridge/browser.ts`; the app's `docs/DECISIONS.md`
  T13 with its parts "F-19b" and "F-19c"; `docs/ISSUES.md` I-25; the stylesheets'
  `:hover` and transition rules; `tokens.css`); tests not run by the
  project lead. It ran as three Claude Code sessions (prompts
  `DEIXEN_Pre4_Task1_F19_PROMPT.md`, `…Task1b_F19b…`, `…Task1c_F19c…`);
  the first two stopped where their own rules said to stop, and did not
  merge. **Verified:** `main` = `c093d5edd9b87b4ac232638b0e0c9b3ecb764abb`,
  a merge (no fast-forward) of `feature/f19-reproducible-tests` (head
  `d6fdafb`) into `phase-5-final` = `3fdb342`; not tagged; the branch
  holds ten commits (`2413750` the seam and the zone, `f0d58c5` the
  evidence refresh, `28af857` and `e052c91` T13 and I-25, `4d7c0bc` F-19b
  stopped, `16e770d` pointer at rest, `3b3a5af` screenshots at rest,
  `975eb04` and `d560295` the final rule and T13, `d6fdafb` I-25 closed);
  `tokens.css` sha256 as approved (D42); by file dates, the only file in
  `src/` written since `phase-5-final` besides `bridge/browser.ts` is
  `src/ui/screens.css`, touched by a planted change and byte-identical with
  the copy read before that session (`content/en/text.json`, touched by
  the other planted change, was not compared byte for byte; Claude Code's
  `git diff` check covers it). **What F-19 now is:** (a) **the locator:** the browser tests set
  a test-only property, `window.__DEIXEN_TEST_RANDOM_INT__`, before the
  page loads (`page.addInitScript`); `src/bridge/browser.ts` passes it to
  the bridge as `randomInt` only when it is present, otherwise the
  `crypto` default — a fresh random locator per `ER` for a learner (Build
  Spec §7A item 16); the tested build is the shipped build; nothing in
  `src/engine/` changed. (b) **The time zone:** `Asia/Riyadh` for the
  browser and for Node in both test runners, with a guard test in each.
  (c) **Screenshots** are saved through one helper: the pointer is first
  moved to a point over nothing interactive, and the helper fails the test
  if any link, button, field or element with a `:hover` rule (read from
  the two stylesheets) is under it; the picture is taken with transitions
  finished; it is written only when it is new, its size differs, or more
  than 64 pixels differ by more than 8 levels on a colour channel, or any
  pixel by more than 32 — otherwise the committed file is left alone. The
  accessibility trees keep exact comparison. PNG reading uses `pngjs`
  7.0.0 (MIT), an exact-version development dependency; the built app is
  byte-identical (33 files). **Found on the way:** the first run rewrote
  **205** tracked files (201 screenshots, 4 trees), not the 209 that 13
  recorded; the 4 trees differed only in the locator; many committed
  screenshots were older than the app (for example 4B-1 pictures still
  drawing Scenario Bank as planned) and were refreshed. With the locator
  and zone fixed, 36 screenshots still changed between identical runs
  (app I-25). The project lead chose, by delegation, option (a): write a
  screenshot only beyond a small tolerance. Measuring it showed that the
  largest kind was not rendering noise: the full-width phone foot buttons
  fade over 120 ms on hover (`--motion-state`), the pointer stays where
  the test last clicked, and each run caught the fade at another point —
  up to 28 levels over up to 19 628 pixels, a real colour difference no
  tolerance could ignore while still catching a 16-level change. So the
  pictures are now taken at rest (the boards draw every control at rest)
  with transitions finished; one deliberate refresh rewrote 195
  screenshots — hover underlines and button colours back to rest, and 11
  with faint noise only; no accessibility tree changed. After it, the
  measured noise is at most 14 levels over 51 pixels (one pixel above 8)
  and 2 levels over 8 pixels; the rule's numbers are set with stated
  margins (app T13 "F-19c"). **Planted and reverted:** a word changed in
  one English string (same length), the reset button's red 16 levels
  brighter, one list moved 1 px — each rewrote exactly the screenshots that
  show it (16, 32, 32) and no other. **Only asserted:** the totals —
  1086 unit/component (1075 after task 1; 12 comparison tests added in
  task 1b, 11 after task 1c) and 271 browser (268 + 3), 0 failed;
  typecheck and build; the measurements; `git status --porcelain
  docs/screens docs/a11y` empty after the first normal run and two
  confirming runs, the second with the shell on New York time; the refresh
  groups and the planted results; the screenshots were not viewed by the
  project lead. **Correction:** the task-1c prompt expected only
  `src/bridge/browser.ts` to differ from `phase-5-final` among `src`,
  `content` and the two configuration files; the two configuration files
  also differ, because they hold F-19's time zone from task 1 — the
  prompt's error, not a deviation. **Closed:** app I-25; 13's row on the
  209 rewritten files; F-19's last line is met (the files are no longer
  rewritten). **Still open:** app I-7, as before. **For Step 4:** its
  verification loop may rewrite existing evidence files (Decision 69 (b));
  with F-19 those rewrites now mean that what a picture shows changed. A
  new hover style is picked up by the check without a test change.
  **Next:** before-Step-4 task 2, F-02, from `main` = `c093d5e`. Files
  changed: 07, 13, Execution Plan §7.

## Definition of Done — for the current frozen vertical slice

All of the following must hold before the slice counts as done: implementation
verified against the new codebase actually built for it; a learner can
complete the one real Pricing & Ticketing path end to end with real content;
Terminal supports the approved slice commands with working valid/invalid
handling, hints, and completion detection; the one scenario is behaviorally
distinct per its contract; Assessment behaves per its contract (accurate hint
labeling, correct carry-over disclosure, no cross-session score merging);
evidence persists and traces correctly; Growth/Readiness shows only the one
bounded qualitative output; Coach behaves correctly at all five required
touchpoints; no false affordance remains anywhere in the slice — every
visible control either works or is truthfully labeled planned/unavailable;
responsive validation passes at all named breakpoints; the accessibility
baseline is met; Arabic + English with RTL + LTR work (Decision 11); a reset
mechanism produces a clean state on demand; and every Amadeus behavior the
slice teaches or simulates is VERIFIED under Decision 12. Explicitly **not**
required for this Done: full curriculum authoring, full Scenario Bank,
Customer Service implementation, backend/auth, PWA-first behavior, or any
Saudi Readiness scoring formula.

## Restricted Areas (no change without explicit review)

**Product core:** don't turn DEIXEN content-first, don't reduce Terminal
importance, don't add sections without justification, don't replace
evidence-based readiness with decorative metrics. **Architecture:** don't
casually replace the five-area structure, don't add features because
they're common elsewhere, don't introduce new top-level areas without
review. **Design:** don't drift toward the anti-pattern list without
review, don't prioritize trends over realism, don't go sterile purely to
seem serious. **Coach:** never decorative, never Terminal-only, never
disconnected from real learner state, never presenting unsupported domain
guidance as authoritative. **Evidence & state:** never present illustrative
data as real evidence, never show success when nothing happened, never claim
readiness without a defensible evidence owner.

## Current North Star

Every decision should support: DEIXEN helps users become operationally
ready for real airline reservation and ticketing work through realistic
practice and measurable capability — pursuing genuine job readiness,
including the Saudi-market outcome, without ever overstating what the
evidence can prove.
