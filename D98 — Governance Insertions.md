# DEIXEN — Decision 98 Governance Insertions

**Repository:** `deixenlabs/DEIXEN-KNOWLEDGE`  
**Source branch:** `main`  
**Source commit inspected:** `06b3bb67193d55933aaf6d82c1a541ac1ae46f70`  
**Prepared:** 2026-11-06  
**Purpose:** Synchronize the approved Home and Learning experience direction across the canonical decision ledger, decision-resolution register, the existing Learning Experience Architecture draft, and the Execution Plan status.

> **Important:** This is an insertion pack, not a replacement for any of the three source files. Do not upload this file under the canonical filenames. Apply each insertion to the current file at the precise location stated below. Re-fetch `main` before editing and preserve any newer changes.

---

## 1. `07_DEIXEN_Canonical_Decisions_and_Current_State.md`

### 1A. Add the following current-state bullet

**Location:** Under `### Product & Architecture — owned in detail by 03_DEIXEN_Canonical_Product_and_Architecture.md`, immediately after the existing `Top-Level Navigation` bullet and before `Platform Direction`.

Insert:

- Home and Learning Experience Direction — **Approved (Decision 98, 2026-11-06).** The first area is named **Home** (English) / **الرئيسية** (Arabic), replacing **Flight Deck / قمرة القيادة** as the current user-facing area name. Home provides personalized orientation around the learner's present situation and most useful next action, with concise context about the wider professional-development journey. Learning provides a discovery overview for learning paths/tracks and courses, followed by focused lessons. The five areas, Terminal centrality, Scenario Bank's case-discovery role and in-Terminal scenario execution, and Growth's evidence role remain unchanged. Detailed flows, visual compositions, and implementation remain separate work.

### 1A-2. Add a current-project-status note

**Location:** In `## Current Project Status`, insert a separate paragraph after the long paragraph beginning `**Phase:** Phase 4 (Design) closed...` and before the `Phase 4 record:` paragraph.

Insert:

**Separate product-experience task (Decision 98, 2026-11-06):** The owner approved the Home / الرئيسية area name and the high-level Home/Learning experience direction. The documentation synchronization is separate from Phase 6 curriculum expansion; it does not start Phase 6, change its scope or gates, authorize app-code changes, or claim the redesigned experiences are implemented. Detailed UX specifications and validation must precede a separately authorized implementation task.

### 1B. Add Decision 98

**Location:** Immediately after the complete `Decision 97 — Native Cumulative Ghost Mode and Isolated Independent Workflow Assessment` entry and immediately before `## Definition of Done — for the current frozen vertical slice`.

Insert:

* **Decision 98 — Home naming and the Home/Learning experience direction. Closed — Karim, 2026-11-06.**

  **(a) First area name.** The first top-level area is named **Home** in English and **الرئيسية** in Arabic. This replaces **Flight Deck / قمرة القيادة** as the current user-facing area name. The area itself remains the same first area in the existing five-area architecture; this decision does not add a sixth area. Earlier decisions, screenshots, filenames, implementation identifiers, and historical descriptions retain their original wording unless separately updated through the appropriate process.

  **(b) Home's approved responsibility.** Home is a personalized learner-orientation experience. It should begin with the learner's relevant current situation, present the most useful next action supported by the actual learner state and current learning/work sequence, briefly explain why that action is appropriate, and provide a concise view of the wider professional-development journey. The immediate need and next useful action take priority; the wider journey is context, not a competing curriculum map. Home must not duplicate the full Learning catalogue or Growth's detailed evidence review, invent progress or competence, or imply job-readiness without supporting evidence.

  **(c) Learning's approved responsibility.** Learning has two connected experiences: (1) a Learning Overview / Discovery experience through which the learner can understand and explore learning paths/tracks and courses, with navigation into modules and lessons; and (2) a focused Lesson Experience centered on one learning objective at a time. The intended experience should help the learner understand what they will learn, why it matters in professional work, how learning connects to relevant practice, and what is available versus planned. The experience-level discovery hierarchy is **learning paths / tracks → courses → modules → lessons**. This does not settle the final curriculum data model, taxonomy, naming, ordering, prerequisite relationships, or content; those remain subject to evidence-based curriculum design and their owning canonical sources. This decision does not authorize unapproved or future-plan content to appear as available. Lesson or course completion is not proof of independent competence.

  **(d) Preserved product architecture.** The five top-level areas remain Home, Learning, Terminal, Scenario Bank, and Growth. Terminal remains the operational heart. Scenario Bank remains the case-discovery/selection experience; a scenario continues to run as a mode inside Terminal under Decision 92. Growth remains responsible for evidence-led capability development. Assessment remains within the existing learning/operational journey and is not a sixth area. This decision does not change the Customer Journey, Professional/Learner Journey, or Work Task Lifecycle contracts.

  **(e) Preserved learning, operational, and evidence rules.** No Amadeus behavior or command truth is added or changed; Decision 12 and the Amadeus Verification Standard remain controlling. No curriculum content, command order, skill-state definition, prerequisite lock, assistance rule, Coach boundary, F-07 independence rule, Ghost Mode rule, assessment contract, scenario transfer scope, evidence formula, Growth status, Terminal record, event schema, or Booking Chain workflow/evidence meaning is changed by this decision. In particular, the Booking Chain / route remains the workflow representation of one specific operational task, not a complete curriculum map, competency map, or professional-journey map. Its exact visual placement on Home or Learning remains open for detailed UX design.

  **(f) Approval boundary.** This decision approves the high-level Home/Learning experience direction and the current user-facing Home name. It does not approve detailed screen layouts, visual compositions, components, navigation mechanics, responsive interactions, final curriculum taxonomy, or a specific recommendation algorithm. It does not authorize application-code changes and does not claim that the new experiences have been implemented. At the time of this decision, `deixen-app/main` still contains the earlier Flight Deck implementation and the existing single-lesson Learning experience. Detailed UX specifications and validation must precede a separately authorized implementation task.

  **(g) Documentation impact.** The approved direction is reflected in `02 — DEIXEN UX Strategy & Experience Architecture.md` and `03_DEIXEN_Canonical_Product_and_Architecture.md`. This decision and its current status are recorded here and in `13_DEIXEN_Decision_Resolution_Register.md`. The existing `DEIXEN_Learning_Experience_Architecture.md` remains a draft, not canonical; it receives a reading-rule clarification so its older Flight Deck/Learning wording cannot be mistaken for the current area responsibilities. The Learning Design Specification, curriculum content, Amadeus Verified Reference, Operating Constitution, app code, translations, styles, assets, and tests are not changed by this documentation update.

---

## 2. `13_DEIXEN_Decision_Resolution_Register.md`

**Location:** In `## 3. Current Decision Register`, insert the following row immediately after the existing `Native Cumulative Ghost Mode and Isolated Independent Workflow Assessment (07 D97)` row and immediately before `## 4. What Is Not Blocking`.

Insert:

| Home naming and Home/Learning experience direction (07 D98) | CLOSED — Karim, 2026-11-06 (07 D98): Home / الرئيسية replaces Flight Deck / قمرة القيادة as the current user-facing name; Home prioritizes the learner's current need and most useful next action with concise context about the wider professional journey; Learning provides discovery for paths/tracks and courses followed by focused lessons; exact curriculum taxonomy, order, prerequisites, and detailed flows remain subject to curriculum design and validation; five areas, Terminal centrality, Scenario Bank, Growth, Booking Chain semantics, Amadeus truth, skill/evidence/assessment rules remain unchanged; app implementation is neither authorized nor claimed by D98 | Karim | Prepare and validate detailed Home/Learning UX specifications before implementation |

---

## 3. `DEIXEN_Learning_Experience_Architecture.md`

**Location:** In the `Reading rule — Phase 2 synchronization` numbered list near the top of the document, insert item 9 immediately after the existing item `8. Roles and names.` and before the `# DEIXEN — Learning Experience Architecture (DRAFT, FIRST BUILD)` heading.

Insert:

> 9. **Current Home and Learning direction (07 Decision 98, 2026-11-06).** For the current user-facing area name and the approved high-level Home/Learning responsibilities, use Decision 98 and the updated canonical product/architecture and UX documents (`03_DEIXEN_Canonical_Product_and_Architecture.md` and `02 — DEIXEN UX Strategy & Experience Architecture.md`). **Home / الرئيسية** is the current name; references to "Flight Deck" in this draft are historical labels or descriptions of the earlier implementation. Learning now has an approved direction comprising a discovery overview followed by focused lessons. This reading rule does not approve this draft as canonical, settle curriculum taxonomy or order, or alter learning mechanics, state/evidence/assessment rules, the Coach contract, Amadeus truth, or implementation requirements. Where this draft conflicts with D98 or the updated canonical sources on Home/Learning responsibilities, D98 and those updated sources control.

---

## 4. `DEIXEN_Execution_Plan.md`

The Execution Plan owns current work sequence and status. Its current status must acknowledge D98 without falsely moving the project into Phase 6 or treating documentation approval as implementation.

### 4A. Update the front-matter `status` line

**Location:** The `status:` value in the YAML-like front matter at the top of `DEIXEN_Execution_Plan.md`, which currently ends with `S2-28 / S2-74 (native cumulative Ghost Mode and isolated independent workflow assessment) closed by Decision 97, 2026-10-28`.

Append to that same `status:` value:

`; Home and Learning experience direction approved 2026-11-06 (07 Decision 98); documentation synchronization is separate from Phase 6 and does not claim app implementation`

### 4B. Add a current-phase note

**Location:** Immediately after the opening paragraph under `## 7. Current Phase` (the paragraph beginning `**The detour before Phase 6...` and ending `**...next: Karim starts Phase 6 himself.**`) and before the subsequent sentence beginning `Phase 5 closed on 2026-10-02`.

Insert:

**Separate product-experience task (07 Decision 98, 2026-11-06):** Karim approved the current Home / الرئيسية name and the high-level Home/Learning experience direction. The knowledge-document synchronization is being handled separately from Phase 6 curriculum expansion. It does not start Phase 6, change its scope or gates, authorize app-code changes, or claim the redesigned Home and Learning experiences are implemented. Detailed UX specifications and validation must precede a separately authorized implementation task. Phase 6 remains unstarted and begins when Karim starts it.

---

## 5. Consistency rules while applying these insertions

- Do not globally replace every historical occurrence of `Flight Deck` with `Home`. Historical decisions, build records, design references, and existing internal implementation names must remain historically accurate.
- Do not change the five-area architecture, create a sixth area, move assessment out of its existing journey, or move scenario execution out of Terminal.
- Do not turn the Booking Chain / route band into a curriculum or competency map.
- Do not interpret the proposed Learning discovery hierarchy as a final curriculum structure or permission to invent courses, skills, prerequisites, locks, or content.
- Do not change the Amadeus Verified Reference, command behavior, evidence/skill-state rules, or existing Learning Design mechanics under this decision.
- Do not mark the app as updated. The app's Home naming, navigation, Learning Overview, localized strings, accessibility behavior, and tests require a separate specification and implementation task.
