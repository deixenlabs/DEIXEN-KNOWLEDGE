# DEIXEN — Home & Learning Documentation Update

**Prepared:** 2026-11-06  
**Knowledge repository:** `deixenlabs/DEIXEN-KNOWLEDGE`  
**Knowledge branch inspected:** `main`  
**Knowledge source commit:** `06b3bb67193d55933aaf6d82c1a541ac1ae46f70`  
**App repository inspected for implementation status only:** `deixenlabs/deixen-app`  
**App branch:** `main`  
**App source commit:** `dde546952b07b17d9bd43722e298a02a3755a706`

## What this package contains

1. **`02 — DEIXEN UX Strategy & Experience Architecture.md`** — complete replacement for the existing UX strategy document. It records the approved Home and Learning direction, the responsibilities of all five areas, the distinction between curriculum, skills, work-task workflow, and learner evidence, and the validation boundaries.
2. **`03_DEIXEN_Canonical_Product_and_Architecture.md`** — complete replacement for the canonical product and architecture document. It updates the five-area definitions, current Home naming, relationship between areas, and the task-specific meaning of the Booking Chain while retaining the other architecture sections.
3. **`D98 — Governance Insertions.md`** — exact insertion instructions and text for Decision 98 and synchronization updates in `07`, `13`, the Learning Experience Architecture draft, and the Execution Plan. This is an amendment pack, **not** a canonical repository document and must not be uploaded under one of those source filenames.

## Upload / application order

Before uploading anything, open the current GitHub `main` versions and confirm that the source files have not changed since the source commit recorded above. If any target has newer edits, reconcile them first; do not overwrite newer work with this package blindly.

1. Replace `02 — DEIXEN UX Strategy & Experience Architecture.md` with the complete file supplied here.
2. Replace `03_DEIXEN_Canonical_Product_and_Architecture.md` with the complete file supplied here.
3. Apply the two exact insertions to `07_DEIXEN_Canonical_Decisions_and_Current_State.md`: the current-state bullet under Product & Architecture, a separate current-project-status note, and the full Decision 98 after D97 and before the current-slice Definition of Done.
4. Add the D98 row to `13_DEIXEN_Decision_Resolution_Register.md`, after the D97 row and before `## 4. What Is Not Blocking`.
5. Add reading-rule item 9 to `DEIXEN_Learning_Experience_Architecture.md`, immediately after item 8 and before the document's main title.
6. Apply the two small current-status insertions to `DEIXEN_Execution_Plan.md`: append the D98 status wording to its front-matter `status:` value, and add the separate product-experience task note under `## 7. Current Phase` at the exact anchor given in the D98 insertion file.

The precise insertion wording and anchors are in `D98 — Governance Insertions.md`. Do not replace the full `07`, `13`, Learning Experience Architecture, or Execution Plan files with the insertion pack.

## What changed conceptually

- The first area is now **Home** in English and **الرئيسية** in Arabic as the current user-facing name. This does not add an area or erase the historical Flight Deck record.
- Home is a personalized orientation point: current learner situation, most useful next step, why it is recommended, and a compact view of the wider professional journey.
- Learning has two connected experiences: curriculum discovery and a focused lesson experience. The experience-level discovery hierarchy is paths/tracks → courses → modules → lessons. Final curriculum taxonomy, ordering, prerequisite relationships, and content remain subject to curriculum evidence and the owning curriculum sources.
- The five areas remain Home, Learning, Terminal, Scenario Bank, and Growth. Terminal remains the operational heart; scenario execution remains inside Terminal; Growth retains the detailed evidence role.
- The Booking Chain remains a route for one operational work task. It is not converted into a curriculum, skill, or career map.
- Learning activity completion is not evidence of independent competence or job-readiness.

## What was deliberately not changed

- No application source code, route identifiers, navigation, Arabic or English UI strings, CSS/tokens, assets, or tests were changed.
- No Amadeus truth, command behavior, Terminal record, skill model, evidence formula, assessment, Ghost Mode, Coach, F-07, Scenario Bank contract, or Growth rules were changed.
- No curriculum content, final curriculum taxonomy, order, prerequisites, or future-plan availability were decided.
- No visual identity, logo, typography, color, layout, motion, component, or detailed screen composition was approved.
- No sixth area was added; assessment remains internal to the existing journey.
- Phase 6 was not started, rescheduled, or re-scoped. The Execution Plan note makes clear that the documentation task is separate from Phase 6.

## Current application status — verified separately

At inspected `deixen-app/main` (`dde546952b07b17d9bd43722e298a02a3755a706`):

- `src/ui/Shell.tsx` still uses the internal screen/navigation identifier `flightDeck`.
- `src/ui/FlightDeck.tsx` still implements the former Flight Deck orientation screen.
- `src/ui/Learning.tsx` still opens a single focused lesson and has a lesson strip; there is no full Learning Overview / path-and-course discovery experience yet.
- `content/ar/text.json` still contains the prior Arabic user-facing strings such as `قمرة القيادة` and `العودة إلى قمرة القيادة`; `content/en/text.json` still contains `Flight Deck` and `Back to Flight Deck`.
- `src/ui/RouteBand.tsx` still derives its route from one task's route data, not from the complete curriculum.

These are observations from the current app repository, not requests to change those files in this documentation package. A separate detailed UX specification, implementation authorization, localization update, and test/verification task are required before claiming the new experience is in the app.

## Important handling notes

- Preserve historic wording in D1–D97 and old build records; do not globally rename every historic `Flight Deck` occurrence.
- Retain the current five-area architecture and existing ownership boundaries.
- Before uploading each replacement, compare against the latest GitHub version. GitHub's file update operation requires the **current blob SHA** for that file; use the SHA from the version you actually fetched, not one copied from this guide if the branch has moved.
- Upload the files in order and verify each result before moving to the next. The repository was **not modified** during this preparation; all changes here are local files for owner review and manual upload.
