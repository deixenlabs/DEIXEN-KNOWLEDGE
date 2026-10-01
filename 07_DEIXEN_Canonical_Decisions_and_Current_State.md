---
name: DEIXEN Canonical Decisions & Current State
owns: The single decisions ledger and current project status going forward
supersedes reading in isolation: AeroBridge_Decisions_and_Current_State.md
last synchronized: 2026-09-26 (Phase 4 closed — gate approved, Decision 42; delegated Decisions 43–44; approved boards exported, Decision 45; Phase 5 started — build step 1 locked, Decisions 46–47; step 2 part A locked, Decision 48; step 2 part B prepared, Decision 49; part B checked, Decision 50; step 2 locked, Decision 51; step 3 prepared, Decision 52; step 3 locked, Decision 53; step 4 prepared, Decision 54; step 4A checked and locked, Decision 55 (2026-09-29); leaving a running assessment or scenario inside the app, Decision 56; rules for build step 4B, Decision 57 (all 2026-09-29); step 4B-1 checked, Decision 58; rules for build step 4B-2, Decision 59; step 4B-2 checked and build step 4 complete, Decision 60; rules for build step 5 (Coach), Decision 61 (all 2026-09-30); step 5 checked and locked, Decision 62; rules for build steps 6 and 7, Decision 63 (both 2026-10-01))
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
(Decision 42). **Current: Phase 5 (Build)** — build step 1 (evidence store)
locked 2026-09-26 (Decision 46); step 2 part A (engine core, `AN`, `SS`,
`NM`, `AP`) locked the same day (Decision 48); step 2 part B prepared (Decision 49: the D48 follow-ups I-4, I-5, I-6 closed, and the part B rules written into Build Spec §6A); Claude Code built part B in its third session (not merged: two layouts were missing); the project lead supplied them (Decision 50); session 3B finished, merged and tagged part B (Decision 51). Build step 3 (bridge, independence flag, skill states, Growth status, one-tab rule D47) prepared (Decision 52: Build Spec §7A), built in session 4 and locked (Decision 53, tag `step-3-bridge`, 723 tests). Build step 4 prepared (Decision 54: Build Spec §7B) and split into 4A (app shell and Terminal practice) and 4B (the other seven states). 4A built in session 5 and locked (Decision 55, tag `step-4a-terminal`, 818 unit/component and 69 browser tests); leaving a running assessment or scenario inside the app decided (Decision 56); the rules 4B would otherwise guess closed (Decision 57: Build Spec §7B items 11–15). 4B-1 (Flight Deck, Learning, Ghost Mode, Growth, Reset, Scope Disclosure) built in session 6 and checked (Decision 58: 943 unit/component and 104 browser tests; merged and tagged `step-4b1-screens` at the start of session 7); the rules for 4B-2 written (Decision 59: Build Spec §7B items 19–20, the meaning of "the scenario completed"). Session 7 merged 4B-1 (tag `step-4b1-screens`) and built 4B-2 (Decision 60: tag `step-4b2-screens`, 994 unit/component and 158 browser tests); build step 4 is complete — all eight states. The rules for build step 5 (Coach; app I-21) are closed (Decision 61: Build Spec §7C); session 8 built step 5 (Decision 62: tag `step-5-coach`, 1070 unit/component and 187 browser tests). The rules for build steps 6 and 7 are closed (Decision 63: Build Spec §7D). Next: session 9 — build step 6 (check the scenario and the assessment with Coach in place) and step 7 (localization, accessibility and breakpoint pass), then Karim's learner test. Claude Code builds the slice from
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

**Implementation state:** no codebase exists in the project's hands. The first
build (Decision 20) will be written from scratch against approved
specifications (Decision 14). No implementation or design execution is
authorized by this status alone; each follows its Execution Plan gate.

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
