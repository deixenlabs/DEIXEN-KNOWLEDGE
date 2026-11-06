# DEIXEN — Architecture Alignment & Change Log

**Package:** Product Experience & Design Framework v0.3  
**Date:** 7 November 2026  
**Status:** Documentation update for owner review; new architecture remains a proposal.

## 1. What changed

| File | Change | Reason |
|---|---|---|
| `00 — ... Index.md` | Rebuilt the index to add the unified architecture and change log, clarify authority levels, and record Home naming. | The old index did not identify a dedicated architecture bridge or explain its non-canonical status. |
| `02 — UX Strategy & Experience Architecture.md` | Reworked the UX model around five current areas, three lifecycles, progressive Ghost, Scenario Bank → Terminal hand-off, Customer/Coach separation, assessment, and Growth. | The earlier document described the areas but not their complete connected experience. |
| `03 — Product Design Language.md` | Added guidance for showing integrated context while preserving distinct information roles. | The architecture has direct implications for visual hierarchy and information separation, not for final visual identity. |
| `04 — Brand Strategy & Visual Identity.md` | No content change. | The architecture does not decide brand positioning, logo, symbol, typography, or palette. The file is included unchanged for a coherent package. |
| `05 — UX Flows, UI Specifications & Design System — Planning.md` | Expanded specification inputs, case-to-run contract, mode policies, evidence requirements, validation cases, and traceability. | The old planning document did not explicitly cover the new cross-capability architecture. |
| `06 — Unified Experience & Runtime Architecture.md` | Updated to v0.2; identifies the bounded booking task as the first architecture-test candidate and links to the stage map. | Connects the abstract responsibility model to an actual task without turning the proposal into implementation authorization. |
| `08 — DEIXEN First Integrated Professional Task Map.md` | New stage-by-stage task map with ownership, event/evidence capture, branches, support policy, D97 assessment relationship, and acceptance criteria. | Pressure-tests whether the proposed Task Runtime and capability boundaries can support one coherent professional task. |
| Master strategic brief | Preserved the Home / الرئيسية synchronization and previous unified-architecture section; appended Part XVII summarizing the bounded new-booking task map, its limits, evidence boundary, and validation gates. | Link the task-level test to the strategic direction without converting it into a final market-priority decision or an implementation commitment. |
| `README.md` | Updated package inventory and handling instructions. | Reflects actual package contents and decision boundaries. |

## 2. Consistency decisions applied

### Five areas

The package consistently uses: **Home, Learning, Terminal, Scenario Bank, Growth**. Ghost, Coach, Customer Interaction, Task Runtime, and Assessment & Evidence are shared capabilities/modes, not new top-level areas.

### D92

Scenario Bank remains the case discovery/definition space. Scenario execution remains inside Terminal. The architecture does not create a second Terminal or change D92.

### D97

Cumulative Ghost and no state injection are preserved. Independent assessment remains isolated and must use a fresh session/run, clean operational state, a distinct unpractised task/variant, and no instructional Ghost/hints/Coach assistance during the attempt. A completed-but-nonqualifying attempt is not independent evidence.

### Operational truth and transcript

Amadeus truth remains grounded in the approved Verified Reference and operational engine. Customer facts, customer dialogue, Coach explanations, and assessment judgments remain separate. The Terminal record remains LTR/monospace and restricted to learner entries, Amadeus output, and the one permitted labelled DEIXEN training line.

### Evidence

Operational accuracy, professional judgment, communication, recovery, independence, retention/transfer, and customer experience remain distinguishable. No percentage score or numeric readiness meter is introduced.

### Product design and brand

The architecture requires visual clarity between information types but does not approve any screen composition, panel arrangement, component, token, logo, color, or typeface. The Brand Strategy file is intentionally unchanged.

## 3. Governance items not changed

- D92, D97, D98, the frozen slice boundary, Amadeus Verification Standard, and any other canonical decision were not edited by this package.
- No source-code repository or application file was changed.
- No curriculum content or command/reference behavior was changed.
- No backend, account, sync, voice, LLM, or work-shift implementation was authorized.

## 4. Open synchronization check: D98

The inspected canonical `03_DEIXEN_Canonical_Product_and_Architecture.md` states that Home / الرئيسية supersedes Flight Deck as the current user-facing name under D98. A separate `D98 — Governance Insertions.md` upload describes insertions still to be applied to the canonical decision log and resolution register. The authoritative `07` decision log and `13` register were not present in the inspected framework folder, so this package does not claim that every governance record is synchronized.

**Required check before repository synchronization:** inspect the authoritative current versions of `07` and `13`; confirm that D98 is recorded in both; then synchronize any remaining companion references through the project's normal process. Do not infer completion from this package alone.

## 5. Current implementation caveat

The architecture document includes a dated summary of the latest read-only app inspection available in the conversation. It is a snapshot, not a fresh repository inspection performed during this documentation update. Re-fetch the current `main` state and re-verify implementation before preparing tickets or implementation instructions.

## 6. What this update establishes

The new-booking task in `08` is a bounded architecture-test candidate: one adult traveller, one passenger, one segment, one fare context within the verified scope, and an itinerary already selected and confirmed by the customer. This avoids assuming that live availability search, fare comparison, ticketing, or payment are already verified. The choice is not a final market-priority decision; practitioner and job-task research must confirm its representativeness.

The map details each phase, the customer information, learner action, Scenario Bank, Terminal, Coach, Task Runtime, and evidence responsibilities. It also tests clarification loops, customer changes, engine rejection, system-accepted/task-wrong outcomes, unsupported scope, interruption, recovery, and independent-assessment isolation.

## 7. Recommended next step

Create and validate the Case Package Definition for this bounded task: synthetic customer facts, disclosure rules, selected-itinerary provenance, verified operational scope, allowed branches, task criteria, support policy, and evidence events. Do not write detailed screen specifications or code tickets until the case and its criteria pass reference and practitioner review.

## 8. v0.3 — Case Package Definition and reference/practitioner gates

| File | Change | Why |
|---|---|---|
| `00 — ... Index.md` | Added CP-001 and practitioner-review deliverables; clarified current release gates. | The architecture now has a concrete, inspectable case candidate. |
| `02 — UX Strategy & Experience Architecture.md` | Added CP-001 experience implications and the need to keep dialogue, task context, Terminal, and Coach distinct. | The case tests information disclosure and channel separation. |
| `05 — UX Flows, UI Specifications & Design System — Planning.md` | Added Case Package, Verified Reference, practitioner, and RF task-validation gates before detailed specs. | Avoid specifying unverified operational content or unvalidated professional flow. |
| `06 — Unified Experience & Runtime Architecture.md` | Added CP-001 stress-test results, current RF acceptance gap, U-12/U-14 gates, and required runtime-state separation. | The current implementation reveals a semantic validation need beyond command validity. |
| `08 — First Integrated Professional Task Map.md` | Added the provisional mobile disclosure choice and the RF semantic-mismatch finding. | The abstract task map is now tied to a named case and observed engine behavior. |
| `09 — Case Package Definition — New Reservation.md` | New complete CP-001 case package, reference matrix, staged responsibility map, branch catalogue, criteria, and explicit verdict. | Detailed architecture stress test. |
| `10 — Practitioner Review Brief & Response Form.md` | New ready-to-send review request and response form. | Professional-practice validation remains external and pending. |
| Master strategic brief | Added Part XVIII connecting CP-001 to strategic direction and documenting verification/practitioner limits. | Preserve strategic continuity without converting the candidate into a canonical decision. |
| `README.md` | Updated package inventory and current limits. | Accurate hand-off. |
| `03` and `04` | No content changes. | The case does not determine design language or visual identity. |

### Findings and required modifications

1. The live Verified Reference fetched from Knowledge `main` is third edition, V-01–V-18, through 2026-10-15. A working spec that mentions a future fourth edition is not a replacement for the live reference.
2. U-12 blocks release of the case's current bare-number passenger CTCM entry as verified operational content.
3. U-14 blocks teaching a universal equivalence between PRINT “Phone” and AP.
4. The current `rf.ts` accepts any non-empty RF text without checking the requester; the current `fxp.ts` completion flag follows filed state plus accepted FXP. Runtime/Assessment must independently validate semantic task correctness.
5. No external practitioner review has been performed; the brief is prepared, not sent/endorsed.

## 9. What has not changed

- D92, D97, D98, the five product areas, and the frozen first-slice boundary are not amended.
- No canonical decisions or resolution registers were edited.
- No Amadeus Verified Reference entry was added or promoted.
- No app code, content JSON, or test suite was changed.
- No screen design, design token, brand identity, or visual decision was approved.
- No ticketing/payment/refund/changes workflow was added.

## 10. Current package verdict

**تنجح مع تعديل** — the conceptual responsibility model survives CP-001, but content release is on hold pending U-12/U-14 and practitioner review, and the runtime design must add explicit task-level semantic validation and separate operational completion from task acceptance/evidence qualification.
