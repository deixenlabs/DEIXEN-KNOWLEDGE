# DEIXEN — Dual-Tool Visual Design Collaboration
## Repository Amendment Pack

**Prepared from:** `deixenlabs/DEIXEN-KNOWLEDGE`  
**Source branch:** `main`  
**Source commit inspected:** `1f4d43c95bdcc3c0144a61e5e65349f6ac9caf3f`  
**Prepared:** 2026-11-06  
**Purpose:** Apply the dual-tool visual design arrangement consistently without rewriting historical decision records or changing completed phases.

This pack contains targeted amendment text for three larger governance files. It is not a replacement for those full files. Apply the exact changes to the current `main` versions only after reviewing the proposed content.

---

# 1. DEIXEN_Operating_Constitution.md

## 1.1 Add this row to the Amendment Record

Add after the 2026-10-25 §9 entry:

| 2026-11-06 | §9 | Added the owner-directed dual-tool visual design arrangement: Google AI Studio (Gemini/Argon 4) and Claude Design (Opus 5.5) both participate in independent visual exploration; Claude Code remains the primary implementation agent; Antigravity is a complementary development environment. No change to D93 project-lead delegation or owner authority. | Karim (07 Decision 98) |

## 1.2 Replace the entire existing §9 with the following

## 9. CURRENT MODEL AND TOOL ROLES

Roles attach to tasks and explicitly delegated responsibilities, not permanently to model names. The model/version pairings below describe the current working setup as of 2026-11-06; they may change as capabilities and project needs evolve.

### Karim — Project Owner

Karim retains final human authority over the matters reserved to him in §8 and the current Decision Register. In particular, AI tools may explore and recommend visual directions, but cannot approve the final brand identity or material visual direction.

### Gemini — Project Lead (07 Decision 93)

Gemini 4 Argon remains the designated primary project lead under Decision 93. Its project-lead responsibilities and the limits of its delegation remain governed by D93 and D29.

Using Gemini/Argon 4 through Google AI Studio for visual exploration is a task-specific design use. It does not create a second project-lead delegation, change D93, or grant additional decision authority.

Project-lead reviews remain self-reviews unless a genuinely separate reviewer performs them. They must never be presented as independent reviews.

### Google AI Studio — Visual Design Exploration

The current working model pairing is Gemini / Argon 4.

Google AI Studio may actively explore, generate, prototype, and iterate on brand identity and product visual-design directions within the brief and permissions of the assigned task.

It is a full creative exploration environment alongside Claude Design, not merely a source of occasional comments. Its outputs remain proposals and do not carry approval or canonical authority.

### Claude Design — Visual Design Exploration

The current working model pairing is Claude Opus 5.5.

Claude Design may independently explore, generate, prototype, critique, and refine brand identity and product visual-design directions within the assigned brief.

It shares the visual exploration responsibility with Google AI Studio. It is not the exclusive design tool, and its output is not presumed superior or final.

### Dual-tool collaboration rule

For relevant design tasks, both environments should receive the same essential strategic context, requirements, constraints, and evaluation criteria. They should first produce independent explorations before seeing or adapting to each other's concepts.

After the independent first pass, cross-critique and iterative synthesis may be used to improve the work. Preserve distinct alternatives where useful; do not mechanically average outputs or force premature convergence.

The purpose is to benefit from complementary capabilities and reduce dependence on a single model—not to create competition for its own sake.

The owner retains final design authority. Tool participation does not authorize repository changes or production implementation.

### Claude Code — Software Implementation

Claude Code remains the primary implementation agent for approved software changes within the authorized scope.

It implements approved specifications and must surface missing requirements, contradictions, or material deviations rather than silently changing product intent.

### Antigravity — Complementary Development Environment

Antigravity is a complementary development environment in the owner's workflow. Its exact role—such as inspection, execution, experimentation, or validation—must be stated in the relevant task assignment.

It does not automatically receive project-lead authority, final design authority, or permission to modify repositories beyond the task's authorization.

### Other AI tools

Other tools may be used when the owner or task brief authorizes them. Their capabilities do not create authority. They remain subject to the same source, evidence, permission, and verification requirements.

---

# 2. DEIXEN_Execution_Plan.md

## Replace the entire existing §2 with the following

## 2. Roles and Current Tool Allocation

The project roles below are task-based. Tool/model names describe the current working setup, not permanent dependencies. Decision 93 continues to govern the project-lead delegation; Decision 98 governs the dual-tool visual design arrangement.

| Who / Environment | Does | Does not |
|---|---|---|
| Karim | Retains final authority over identity, scope, name/brand/visual direction, governance, and other matters reserved by D29 and the current Decision Register | Delegate a reserved decision merely by requesting exploration or a recommendation |
| Gemini — Project Lead (D93) | Leads project review, knowledge work, synchronization, Amadeus verification under D12, and execution preparation within D29 | Override reserved owner decisions, lower verification standards, or present self-review as independent |
| Google AI Studio — Gemini/Argon 4 | Independently explores, prototypes, and iterates brand and product visual directions under D98 and the applicable design brief | Claim exclusive design authority, approve the final direction, or modify production code without separate authorization |
| Claude Design — Opus 5.5 | Independently explores, prototypes, critiques, and iterates brand and product visual directions alongside Google AI Studio under D98 | Claim exclusive design authority, approve the final direction, or assume its output is preferred |
| Claude Code | Implements approved software specifications within the authorized task scope | Add scope, invent Amadeus behavior, or silently reinterpret decisions |
| Antigravity | Serves as a complementary development environment; its exact task role is stated in each assignment | Automatically assume project-lead authority or unrestricted write permission |
| Other tools | May provide task-authorized specialist or consultative assistance | Acquire authority through capability, confidence, or model reputation |

### Visual design collaboration

For future authorized brand identity and product visual-design tasks, Google AI Studio (Gemini/Argon 4) and Claude Design (Opus 5.5) are complementary exploration environments.

They receive the same essential brief and evaluation criteria but make independent first-pass explorations before cross-review. Their work may then be compared, challenged, and iteratively improved. Karim retains final approval.

The detailed collaboration and handoff workflow is defined in `05 — UX Flows, UI Specifications & Design System — Planning.md`.

### Historical phase records

The completed Phase 4, identity exploration, and refinement entries in §3 record the roles and decisions used at that historical time. They must remain intact as history. Their previous Claude Design-only assignment does not override Decision 98 for future design work.

This role allocation does not create a new phase, change the current phase, reopen a completed gate by itself, or approve any visual direction. The current Execution Plan and Decision Register continue to govern sequencing and decision status.

---

# 3. 07_DEIXEN_Canonical_Decisions_and_Current_State.md

Append the following new decision immediately after Decision 97. Do not rewrite or delete Decisions 17, 91, or 93; preserve them as historical decisions and let this new decision supersede only the specific role assignment described below.

* **Decision 98 — Dual-Tool Visual Design Collaboration. Closed — Karim, 2026-11-06.**

  **(a) Two active design environments.** For future authorized brand identity and product visual-design work, both Google AI Studio using Gemini/Argon 4 and Claude Design using Claude Opus 5.5 may actively explore, prototype, critique, and iterate design directions. Neither is the exclusive design tool or the presumed winner.

  **(b) Independent first pass.** Both environments receive the same essential strategic context, design brief, relevant source material, constraints, and evaluation criteria. Each produces an independent first exploration before seeing or adapting to the other's concepts.

  **(c) Cross-review and synthesis.** After independent proposals exist, the environments may critique one another's work and develop improved alternatives. Preserve distinct directions where useful. Combine complementary strengths only when the result becomes more coherent and effective; do not mechanically average concepts or force premature convergence.

  **(d) Owner authority.** All AI-generated designs remain proposals. Karim retains final authority over brand identity and material visual direction. This decision does not approve a logo, palette, typography, screen composition, or any other design output.

  **(e) Implementation boundary.** Claude Code remains the primary implementation agent for approved software changes. Antigravity remains a complementary development environment in Karim's workflow, with its exact role defined per task. This decision does not authorize repository or production-code changes.

  **(f) Existing role decisions.** Decision 93's Gemini project-lead delegation and Decision 29's boundaries remain unchanged. This decision supersedes Decision 17 only to the extent that D17 assigned exclusive design exploration/execution to Claude Design and excluded other tools from an active design role. Historical phase records remain unchanged.

  **(g) Scope and status.** This decision establishes a collaboration method and tool allocation only. It does not alter product architecture, learning logic, Amadeus truth, accessibility requirements, or the status of any particular visual identity decision. Current visual decision status must be read from the latest owner-approved record.

---

# 4. 13_DEIXEN_Decision_Resolution_Register.md

Insert this row in the main decision/status table, immediately after the D97 row and before the next section heading:

| Dual-tool visual design collaboration (07 D98) | CLOSED — Karim, 2026-11-06 (07 D98): Google AI Studio (Gemini/Argon 4) and Claude Design (Opus 5.5) both participate in independent brand and product visual exploration; shared brief, independent first pass, then cross-review and iterative synthesis; Karim retains final design authority; Claude Code remains primary implementation agent; Antigravity is the complementary development environment | Karim | Apply to future authorized design tasks; detailed workflow in 05 |

---

# 5. Upload and synchronization order

1. Review and apply the proposed D98 entry to `07` first, because it records the owner-approved role change and narrowly supersedes the old D17 tool exclusivity.
2. Update the row in `13`.
3. Replace §9 in `DEIXEN_Operating_Constitution.md` and §2 in `DEIXEN_Execution_Plan.md`.
4. Upload the three updated design-framework documents in this package:
   - `00 — DEIXEN Product Experience & Design Framework Index.md`
   - `04 — DEIXEN Brand Strategy & Visual Identity.md`
   - `05 — UX Flows, UI Specifications & Design System — Planning.md`
5. Check the repository for consistency after upload. Do not change the historical Phase 4 records or unrelated design, learning, architecture, or Amadeus files as part of this update.

## Files deliberately not changed

- `02 — DEIXEN UX Strategy & Experience Architecture.md`: it owns learner flows and experience behavior, not AI tool assignments.
- `03 — DEIXEN Product Design Language.md`: it owns visual/interaction principles; the multi-tool workflow is documented in 05 to avoid mixing process roles into the design-language rules.
- The master strategic product direction: its integrated UX/UI/brand philosophy is already current and tool-neutral.
- The app repository: no design or code implementation is authorized by this documentation update.
