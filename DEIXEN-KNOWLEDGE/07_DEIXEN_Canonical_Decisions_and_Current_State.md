---
name: DEIXEN Canonical Decisions & Current State
owns: The single decisions ledger and current project status going forward
supersedes reading in isolation: AeroBridge_Decisions_and_Current_State.md
last synchronized: 2026-09-26 (Phase 4 closed — gate approved, Decision 42; delegated Decisions 43–44; approved boards exported, Decision 45; Phase 5 started — build step 1 locked, Decisions 46–47; step 2 part A locked, Decision 48; step 2 part B prepared, Decision 49)
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
`NM`, `AP`) locked the same day (Decision 48); step 2 part B prepared (Decision 49: the D48 follow-ups I-4, I-5, I-6 closed, and the part B rules written into Build Spec §6A); next, Claude Code builds step 2 part B. Claude Code builds the slice from
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
  for whoever implements it to resolve within that approved boundary.
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
