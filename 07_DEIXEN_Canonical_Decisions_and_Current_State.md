---
name: DEIXEN Canonical Decisions & Current State
owns: The single decisions ledger and current project status going forward
supersedes reading in isolation: AeroBridge_Decisions_and_Current_State.md
last synchronized: 2026-09-25 (Execution Plan Phase 3.2)
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

**Phase:** Phase 2 (Foundation Synchronization) completed on 2026-09-24.
**Now:** Phase 3. Step 3.1 produced `DEIXEN_Amadeus_Verified_Reference.md`
(second edition 2026-09-25). Step 3.2: Karim approved the adjusted slice path
(Decision 22), the Terminal output rule (Decision 23), and the `SRCTCM`
step (Decision 24) on 2026-09-25, and approved creating the three Phase 3
files (Slice Build Spec, Design Brief, Claude Code environment pack). Step
3.4 (Design Brief) and step 3.3 (`DEIXEN_Slice_Build_Spec.md`, draft) are
written; Karim approved its four proposals (Decision 25) and then the
Build Spec and `CLAUDE.md` as a whole (Decision 26). Next: Claude closes
the Build Spec gaps G1–G3 (example screens, slice content, scope
disclosure), then the readiness check (3.6).

**Implementation state:** no codebase exists in the project's hands. The first
build (Decision 20) will be written from scratch against approved
specifications (Decision 14). No implementation or design execution is
authorized by this status alone; each follows its Execution Plan gate.

**Design:** Design Positioning closed; Design Execution open (Design phase =
Execution Plan Phase 4).

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
- Design Execution — **OPEN.** Exact colors/tokens, typography, logo/wordmark,
  visual identity, composition, imagery, effects, and overall visual
  expression are genuinely unsettled, pending the next dedicated design
  phase. The earlier dark-navy/blue execution and the color language written
  around it in file 04 are historical design input only — neither approved
  nor rejected. Light vs. dark direction is open.

### Amadeus — domain truth, implementation history, and the frozen slice
- **Domain truth** is owned by `DEIXEN_Amadeus_Verified_Reference.md`
  (Decision 15, created in Execution Plan Phase 3) under the Verification
  Standard (Decision 12). Second edition 2026-09-25: it verifies every
  command in the adjusted slice path (Decision 22) — `AN`, `SS`, `NM`, `AP`,
  `TK`, `RF`, `ER`, `FXP` — plus `FQD`, `FXX`, the mandatory PNR elements, and
  the IATA passenger-contact SSRs. Everything not listed there as VERIFIED is
  UNVERIFIED.
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
  post-ticketing segment-status behavior; the exact mandatory-element list.
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
  are not requirements; they are lessons (e.g. element numbers shown during
  entry must match the final PNR numbering). Any limitation in the new build
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
- **Phase 3 files — creation approved (Execution Plan §5).** Karim approved
  creating the Slice Build Spec, the Design Brief, and the Claude Code
  environment files (`CLAUDE.md` and repository scaffolding).

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
