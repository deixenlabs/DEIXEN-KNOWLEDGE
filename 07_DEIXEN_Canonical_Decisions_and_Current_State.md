---
name: AeroBridge Canonical Decisions & Current State
owns: The single decisions ledger and current project status going forward
supersedes reading in isolation: AeroBridge_Decisions_and_Current_State.md
authority note: Where a decision below is owned in more detail elsewhere in this canonical set (product/architecture, design, engine, curriculum/Coach), this file states the decision and its status, and points there rather than duplicating — the same single-ownership discipline the original NEW document already established and this pass is preserving.
---

# AeroBridge — Canonical Decisions & Current State

## Document Authority

Priority order for resolving any disagreement: (1) explicit decisions in this
document, (2) current approved architecture
(`03_AeroBridge_Canonical_Product_and_Architecture.md`), (3) evidence-based
review outcomes, (4) new suggestions. Historical discussions, old audits, and
prior ideas are reference material — they do not automatically override an
approved decision here. **For this consolidation pass specifically, the
governing consolidation prompt sits above even this ordering** — see
`00_AeroBridge_Knowledge_Consolidation_Plan.md` and the visual-direction note
in `04_AeroBridge_Canonical_Design_System.md` for the one place this matters
in practice.

## Referenced but not supplied to this consolidation

Three artifacts are leaned on by name in the source material but were not
part of this pass's evidence: `AeroBridge_Pre_Phase3_Arbitration_and_Scope.md`
(the actual Claude/Manus arbitration record — the documents below only
summarize its conclusions), `AeroBridge_Domain_SME_Validation_Brief.md` plus
its SME-01…SME-10 claim register (governs Decision 7 below), and
`AeroBridge_Scenario_Bank_Architecture_Decision_Review.md` (referenced from
inside the repository's own code comments). Any claim below that depends on
one of these — most notably "Phase 3 gate: CLOSED" — should be read as
**reported, not independently re-verified**, per the original document's own
explicit caution about exactly this.

## Current Project Status

**Phase:** Prototype Entry / Visual Direction Stabilization. Read "Visual
Direction Stabilization" as referring specifically to Design *Execution*
(colors, typography, identity, imagery) — that's the part this correction
pass keeps genuinely open ahead of the next design phase. It does not refer
to Design *Positioning* (professional/operational/serious), which is closed
and unaffected. See `04_AeroBridge_Canonical_Design_System.md`.

**Current objective:** execute the approved bounded prototype scope on the
current implementation target, using approved product/UX behavior as the
behavioral baseline.

**Implementation target:** a "Rebound Baseline — Replacement Controlled
State" — source-tree SHA-256 `5ac24787…95aa`, archive SHA-256
`7ca3beb8…3635d`, 85 files, React + TypeScript + pnpm. **This consolidation
pass was not given that codebase** — the repository actually supplied
(`aerobridge-main.zip`, hash `73f1ca01…9950`) is a different, 37-file, plain
HTML/CSS/vanilla-JS project that matches the product's earlier architecture
instead. Full evidence in
`01_AeroBridge_Repository_Reality_Report.md` §1. Treat this as an open
logistics gap, not a contradiction to resolve — see
`09_AeroBridge_Decisions_Requiring_Malik_Approval.md`.

**Review state:** an independent Claude review and an independent
Manus implementation-aware review were both completed, followed by a
cross-review arbitration. That arbitration concluded the five-area
architecture, Terminal centrality, and overall visual/interaction identity
should be preserved rather than reopened, and that bounded prototype
implementation is authorized within a frozen vertical slice while full-scale
work and all domain-sensitive aviation/GDS claims remain gated. This pass
reports that conclusion; it could not independently re-verify it, since the
arbitration record itself wasn't supplied (see above).

## Decisions Ledger

Decisions are grouped by owning topic. Status values: **Closed**, **Approved
Baseline Rule**, **Approved Contract**, **Approved Scope Boundary**, or
**OPEN**. Two refinements to these, applied consistently below rather than
introducing new status categories: a **Closed** decision that specifically
deserves your conscious reconfirmation (rather than silent inheritance)
carries an explicit **"(Reconfirmation Requested)"** tag right after the
status word, with the reason and pointer to
`09_AeroBridge_Decisions_Requiring_Malik_Approval.md` alongside it — so that
is visible from this file alone, not only by cross-referencing file 09
separately. And where a decision concerns a validation process rather than a
product/design fact, **Closed** describes only that the *requirement* is
established (scope, ownership, and process agreed) — it never means the
*validation itself* has been executed or passed; that distinction is stated
explicitly wherever it applies.

### Product & Architecture — owned in detail by `03_AeroBridge_Canonical_Product_and_Architecture.md`
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
  `03_AeroBridge_Canonical_Product_and_Architecture.md`; the current frozen
  boundary is Decision 8A below.

### Design — owned in detail by `04_AeroBridge_Canonical_Design_System.md`
- Design Positioning — **Closed.** AeroBridge reads as professional,
  operational, serious aviation-operations software — never a consumer app,
  classroom product, generic LMS, or entertainment dashboard. Not reopened by
  this consolidation; not affected by the item below.
- Design Execution — **OPEN.** Exact colors/tokens, typography, logo/wordmark,
  visual identity, composition, imagery, effects, and overall visual
  expression are genuinely unsettled, pending the next dedicated design
  phase. The earlier dark-navy/blue execution is preserved as historical
  evidence and design input only — neither approved nor rejected by this
  status.

### Amadeus Engine — owned in detail by `05_AeroBridge_Canonical_Amadeus_Engine_Reference.md`
- The 37-command engine is code-verified and current — see
  `05_AeroBridge_Canonical_Amadeus_Engine_Reference.md` for exactly what
  "code-verified" does and doesn't establish.
- Vertical Slice Implementation Boundary (Decision 8A) — **Closed — Frozen /
  Domain-Validation-Pending.** Path: the full core transformation chain.
  Workflow family: Pricing & Ticketing. Terminal command boundary: `AN → SS →
  FQD → FXP` only. Scenario count: 1 behaviorally differentiated scenario.
  Evidence: 1 owned assessment record from real learner actions.
  Growth/Readiness: 1 bounded, qualitative output — no numeric Saudi Readiness
  percentage. Coach: required across all touchpoints spanning the slice.
  **Explicitly deferred from this boundary:** full curriculum authoring, full
  Scenario Bank expansion, Customer Service curriculum, new GDS/aviation
  semantics, broad Saudi readiness scoring, backend/auth/PWA expansion, new
  top-level areas, scoring/persistence redesign, or a full visual rebrand
  that discards the approved identity. Any change to the command set,
  scenario count, or evidence type needs an explicit decision update.

### Curriculum & Coach — owned in detail by `06_AeroBridge_Canonical_Curriculum_and_Coach.md`
- Coach Core Guided Learning Layer (Decision 9) — **Closed — Approved.**
  Mandatory, five required touchpoints, state-bound, never static. Layout
  ownership (global element vs. per-page component) is explicitly **Open**
  for whoever implements it to resolve within that approved boundary.
- Customer Service Curriculum Contract (Decision 6) — **Closed — Approved
  Scope Boundary.** Separate global competency; not part of the initial
  slice; no CS proficiency/readiness metric shown as measured evidence until
  its own contract (content model, competency structure, assessment logic,
  evidence pathway, domain/SME requirements) is defined.

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
`03_AeroBridge_Canonical_Product_and_Architecture.md`. Skill values stay
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
scenario uses remain validation-gated until domain/SME review. An
unimplemented scenario may be shown as planned/unavailable — never as
completed competency. The first vertical slice needs only **one** scenario to
prove real behavioral differentiation — not a full Scenario Bank.

### Domain / SME Validation

**Domain/SME Validation Dependency (Decision 7).** Two statuses that must not
be collapsed into one: the **validation requirement is Closed** — formally
assigned for the frozen slice, covering the current command model
(`AN`/`SS`/`FQD`/`FXP`) and the one selected scenario's operational
semantics, governed by the two not-supplied artifacts named above. The
**validation execution is still Pending** — the actual SME sign-off has not
happened, and nothing in either consolidation pass can substitute for it. No
authoritative aviation/GDS behavior may be promoted from AI inference; the
required pipeline is Source → Review → Approval → Structured content →
Implementation → QA, never AI generation → implementation → assumed truth.

**Scope note added by this correction pass — not a change to Decision 8A:**
validation must explicitly cover two distinct questions, not just one.
*Command-level/domain semantics* — is each command's syntax and individual
behavior correct for real Amadeus. *Whole-workflow/task validity* — does the
combined frozen path (`AN → SS → FQD → FXP`) represent a coherent,
recognizable real-world reservations task appropriate for the training
context, not merely four individually-valid commands strung together for
engineering convenience. This pass does not assume an answer to the second
question — it's recorded here as something the validation process must
confirm, not something already known.

Expanded command families beyond the frozen slice — including, by extension,
the other 33 commands already engine-verified in
`05_AeroBridge_Canonical_Amadeus_Engine_Reference.md` — need this same
domain/SME validation before being presented as authoritative training
behavior, even though that engine reference already carries a separate,
real, code-level verification. **These are two different kinds of
verification** (code-correctness vs. real-world domain accuracy) and neither
substitutes for the other.

### Process
- Manus Collaboration Protocol (Decision 10A) — **Closed, Approved Operating
  Rule.** Full detail in
  `08_AeroBridge_Canonical_AI_Working_Rules_and_Dev_Process.md`.
- Cross-Review Arbitration Outcome (Decision 10) — **Closed, Approved
  Outcome, with one scope correction.** The arbitration concluded the
  five-area architecture, Terminal centrality, *and* overall visual
  direction should all be preserved rather than reopened. The
  architecture/Terminal-centrality part of that conclusion stands and is not
  reopened by anything in this correction pass. The visual-direction part is
  superseded — not because the arbitration was flawed, but because a later,
  more specific instruction explicitly reopens Design Execution (see the
  Design section above and `04_AeroBridge_Canonical_Design_System.md`).

### Localization — Decision 11
**Status: Closed — Approved.** AeroBridge must support Arabic + English, with
RTL + LTR. This is an explicit product decision, not merely a historical
default carried over — it is treated as approved unless Malik explicitly
reopens it. **Decided, but distinct from implementation approach:** the
earlier implementation's actual Arabic/RTL build (verified directly in the
supplied repository — see
`01_AeroBridge_Repository_Reality_Report.md` §3) is preserved as useful
prior evidence that this is achievable and roughly what it looks like in
practice — it is not a template to simply be copied into whatever
implementation comes next. How localization is actually built (data-driven
strings vs. hardcoded, per-component RTL handling, which library if any) is
an ordinary technical implementation choice, not decided here.

## Definition of Done — for the current frozen vertical slice

All of the following must hold before the slice counts as done: implementation
verified against the actual current baseline (not a stale hash); a learner
can complete the one real Pricing & Ticketing path end to end with real
content; Terminal supports `AN → SS → FQD → FXP` with working valid/invalid
handling, hints, and completion detection; the one scenario is behaviorally
distinct per its contract; Assessment behaves per its contract (accurate hint
labeling, correct carry-over disclosure, no cross-session score merging);
evidence persists and traces correctly; Growth/Readiness shows only the one
bounded qualitative output; Coach behaves correctly at all five required
touchpoints; no false affordance remains anywhere in the slice — every
visible control either works or is truthfully labeled planned/unavailable;
responsive validation passes at all named breakpoints; the accessibility
baseline is met; a reset mechanism produces a clean state on demand; and
domain-sensitive claims actually used within the slice are SME-validated, not
merely implemented. Explicitly **not** required for this Done: full
curriculum authoring, full Scenario Bank, Customer Service implementation,
backend/auth, PWA-first behavior, or any Saudi Readiness scoring formula.

## Restricted Areas (no change without explicit review)

**Product core:** don't turn AeroBridge content-first, don't reduce Terminal
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

Every decision should support: AeroBridge helps users become operationally
ready for real airline reservation and ticketing work through realistic
practice and measurable capability — pursuing genuine job readiness,
including the Saudi-market outcome, without ever overstating what the
evidence can prove.
