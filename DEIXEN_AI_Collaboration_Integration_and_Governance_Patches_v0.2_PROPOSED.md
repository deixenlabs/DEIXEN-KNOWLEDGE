# DEIXEN — AI Collaboration & Orchestration Integration Patches v0.2

**Prepared:** 7 November 2026  
**Repository:** `deixenlabs/DEIXEN-KNOWLEDGE`  
**Branch inspected:** `main`  
**Commit inspected:** `7d5f8e0e6a0e1007dce387d783b31f6214e325c9`  
**Status:** PROPOSED — do not apply until owner review and the governance conditions in §5 are resolved.  
**Purpose:** Integrate the proposed v0.2 collaboration/orchestration protocol with the smallest necessary document changes, while preserving current authority and decision records.

> This is an integration instruction pack, not replacement copies of the long canonical files. Re-fetch `main` before applying any future patch. No GitHub write is authorized by this document.

---

## 1. Recommended document ownership

| File | Existing ownership | Recommended action | Reason |
|---|---|---|---|
| `DEIXEN_AI_Collaboration_Handoff_and_Orchestration_Protocol_v0.2_PROPOSED.md` | Proposed operational companion | Review as the dedicated owner of task packets, cross-tool routing, Bridge interface, handoffs and cost/privacy routing | The new responsibility is larger than handoff formatting alone, but remains subordinate to governance |
| `08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process.md` | AI behavior, authority, task authorization, independent review, verification, model/cost discipline | Add concise scope boundary and reference only; do not duplicate the detailed protocol | File 08 explicitly excludes detailed prompt construction and session-handoff mechanics |
| `00_DEIXEN_Knowledge_Consolidation_Plan.md` | Corpus map and dependency lines | Add the protocol as a proposed supporting reference in A6 and a dependency line in A10 after owner acceptance | It records document relationships but does not create authority |
| `DEIXEN_Operating_Constitution.md` | Highest operating method/authority/role boundaries | No immediate change. Prepare a conditional §9 amendment only after the D17/D93 and D98 issues are reconciled | Current §9 says other tools have no project role and are consultative only; a protocol cannot override this |
| `DEIXEN_Execution_Plan.md` | Current phase sequencing, gates and role allocation | No immediate change. Prepare a conditional §2 update only after the owner adopts a task-scoped delegation decision | It currently says “No other AI tool has a role” and names only existing occupants |
| `07_DEIXEN_Canonical_Decisions_and_Current_State.md` | Canonical project decisions/current state | No edit in this package | A governance decision is not created by drafting a protocol |
| `13_DEIXEN_Decision_Resolution_Register.md` | Decision/status register | No edit in this package | Record only after a numbered decision has been properly adopted |
| `DEIXEN Detour Prompt Package v1.8.MD` | Detour Charter, Prompt 0–7, HANDOFF BLOCK and Freeze Package | Leave unchanged | It already has a stronger task-specific handoff mechanism and is not a general agent orchestration protocol |
| `CLAUDE.md` | App-specific Claude Code instructions | Leave unchanged until a Claude Code adapter is installed and tested | Do not make a global protocol depend on a Claude-only file |
| `05 — UX Flows, UI Specifications & Design System — Planning.md` | Product UX/UI specification | Leave unchanged | Product-screen handoffs are not AI-tool orchestration ownership |
| `00 — DEIXEN Product Experience & Design Framework Index.md` | Product design framework index | Leave unchanged | The proposed protocol is a general operating companion, not a product-design framework document |
| `deixen-app` source code | Application implementation | No action | The bridge is a local developer tool, not a DEIXEN learner-facing feature |

---

## 2. Proposed File 08 amendments

Apply only after the owner accepts the v0.2 protocol's purpose and placement. Preserve all other content and the current YAML structure.

### 2A. Front matter — `does_not_own`

**Current item:**

```yaml
- session-handoff mechanics.
```

**Proposed replacement:**

```yaml
- detailed cross-tool task routing, Agent Bridge operation, handoff packets, and return-handoff mechanics (owned by `DEIXEN_AI_Collaboration_Handoff_and_Orchestration_Protocol_v0.2_PROPOSED.md` after adoption).
```

**Important:** Keep the existing exclusion for “prompt-construction method” unless and until the missing legacy Prompt Engineering document is recovered and its ownership is reconciled. The proposed v0.2 protocol does not claim ownership of general prompt-engineering theory. File 08 also points to that legacy reference for Work-Task Classification (§11), the detailed independence mechanism (§13.2), and the broader output contract (§22). Do not redirect those references wholesale to v0.2: v0.2 owns orchestration and handoff mechanics, not those broader disciplines. Recover the original file or review those specific references separately.

### 2B. §1 Purpose and Scope — ownership boundary

**Current bullet:**

```text
- session continuity/handoff mechanics.
```

**Proposed replacement:**

```text
- detailed cross-tool task routing, Agent Bridge operation, handoff packets, and return-handoff mechanics, which are defined in the supporting `DEIXEN_AI_Collaboration_Handoff_and_Orchestration_Protocol_v0.2_PROPOSED.md` after adoption.
```

**Insert immediately after the list, before “When this document references those domains…”**

```text
The supporting AI Collaboration, Handoff & Orchestration Protocol defines the practical task packet, capability-based routing, local Bridge interface, cross-tool delegation patterns, receiver preflight, and return handoff. It is subordinate to this document, the Operating Constitution, the canonical decision record, and the Execution Plan. It does not create standing tool roles, decision authority, approval, repository permissions, or execution authorization. File 08 remains controlling for agent behavior, task authorization, independent-review governance, conflict handling, and verification discipline.
```

### 2C. §9 Current Roles — conditional note only

Do **not** expand the current agent occupants or turn the tool inventory into permanent roles before the D17/D93 governance issue is resolved.

After a separate owner decision explicitly permits temporary specialist assignments, add a short rule under §9.4 or §9.5:

```text
Task-scoped specialist assignments may be made only where the current canonical decision record and Execution Plan permit them. A task assignment identifies the exact tool/product surface, assigned work, evidence requirements, output, scope, permissions, and approving authority. It creates no standing role and does not transfer the project lead's delegation, D29 reserved matters, owner authority, independent-review status, or domain authority. The supporting AI Collaboration, Handoff & Orchestration Protocol defines the mechanics; it does not grant the permission.
```

This insertion is **conditional**. It must not be used to bypass Decision 17's current restriction that other tools are consultative-only.

### 2D. §30 Cost / Model-Selection Governance — optional concise clarification

Consider adding one line only if the owner wants the no-new-spend constraint in File 08 itself:

```text
A local MCP bridge or open-source orchestrator does not make model inference free; use only the access routes and quotas approved for the task, and do not trigger paid API billing, purchased credits, or automatic overages without explicit owner authorization.
```

The detailed routing and cost table remains in the supporting protocol.

---

## 3. Proposed Knowledge Consolidation Plan amendments

Apply only after owner acceptance and after the protocol's filename/status are finalized.

### 3A. A6 — Supporting references

Preserve the existing A6 entries. Add a separate note immediately after the existing list:

```text
**Current AI collaboration companion (proposed):** `DEIXEN_AI_Collaboration_Handoff_and_Orchestration_Protocol_v0.2_PROPOSED.md`. It defines task-packet, cross-tool routing, local Agent Bridge, and return-handoff mechanics. It remains subordinate to the Operating Constitution, canonical decisions, File 08, and Execution Plan; it does not grant roles or execution authority.

**Legacy references unresolved:** `UNIVERSAL_AI_SESSION_HANDOFF_PROTOCOL.md` and `DEIXEN_Prompt_Engineering_and_Governance_UNIFIED_PROPOSED.md` remain listed above as supporting references. Their full contents were not located in the current `main` snapshot or the accessible Library during the 2026-11-07 review. Do not delete, promote, or replace them solely on the basis of this search; recover the originals or formally resolve their status first.
```

Do not claim these legacy references were read in full. File 08 still points to the Prompt Engineering reference for Work-Task Classification (§11), independence mechanics (§13.2), and output-contract guidance (§22). Version 0.2 does not replace those topics; do not change those cross-references to v0.2 merely to remove a broken link.

### 3B. A10 — dependency line

Insert after:

```text
- Constitution → Execution Plan → every phase.
```

Proposed line:

```text
- Constitution + 07 + File 08 + Execution Plan → `DEIXEN_AI_Collaboration_Handoff_and_Orchestration_Protocol_v0.2_PROPOSED.md` → material cross-tool task routing and handoffs; subordinate only, with no authority to alter roles, permissions, decisions, domain sources, or execution gates.
```

### 3C. Do not place the protocol in A1

Do not promote this protocol to a governing source. Its correct proposed location is the supporting-reference area because it operationalizes existing authority rather than creating it.

---

## 4. Conditional Operating Constitution and Execution Plan amendments

These are **not ready to apply**. They depend on a separate owner decision that reconciles the current tool-role restrictions.

### 4A. Operating Constitution §9 — other tools

Current §9 states that Sonnet, ChatGPT, Manus and other tools have no project role and may provide consultative input only if Karim chooses. This is consistent with the older Decision 17 position but conflicts with the requested future of active, task-scoped tool-to-tool execution.

If the owner adopts a new decision allowing temporary specialist assignments, the proposed replacement should be narrowly framed:

```text
Other AI Tools — No standing role is created by their availability or connection to the Bridge. A tool may perform a temporary, bounded specialist assignment only when the current canonical decision record permits it and the assignment is made by the authorized project coordinator or owner within that permission. The task packet must name the exact surface, task, sources, required output, permissions, and approval boundary. Such an assignment does not grant project-lead status, decision authority, repository access beyond its task, or permission to perform external actions. Until the required owner decision is recorded, the existing consultative-only restriction remains in force.
```

Do not replace the current text until the new decision is accepted and recorded.

### 4B. Execution Plan §2 — task allocation

If and only if the new decision is adopted, update §2 to distinguish:

- **Standing project authority:** Karim and Gemini's project-lead delegation as governed by D93/D29;
- **Task-specific specialist assignments:** temporarily assigned by the authorized coordinator where the new decision permits; no permanent vendor/model role;
- **Implementation agents:** task-specific and authorized for the exact repository/path/task;
- **Manual-only surfaces:** receive prepared handoffs but are not described as automated adapters.

The tool capability inventory belongs in an operational registry or appendix, not as a permanent “one brand = one role” table.

Do not alter the phase sequence, gates, or current Phase 6 status as part of this update.

---

## 5. Required governance reconciliation before active multi-agent delegation

### 5A. D98 collision — unresolved

Two different materials currently use the label D98:

1. `D98 — Governance Insertions.md` in the accessible Library describes **Home naming and Home/Learning experience direction** as D98.
2. `DEIXEN_Dual_Tool_Design_Role_Amendment_Patches.md` in the accessible Library describes **dual-tool visual design collaboration** as D98.

The current canonical `07_DEIXEN_Canonical_Decisions_and_Current_State.md` on `main` ends at D97 (blob SHA `492f65c3c45673aa5042b564fc34d1675d8aeaf6`). The current `13_DEIXEN_Decision_Resolution_Register.md` (blob SHA `72fb591a52e1bb6d8ece713cee598f04b82284ab`) contains D93 as its latest decision row and no D98/D99 row. The Home/Learning D98 insertion pack was not found integrated into those current canonical files during this check.

**Instruction:** Do not apply `DEIXEN_Dual_Tool_Design_Role_Amendment_Patches.md` as written. Do not assign a new decision number to this orchestration protocol until the owner reconciles which D98 is intended, what was accepted, and what belongs next in the canonical sequence.

### 5B. Decision 17 and D93

- D93 transferred the project-lead role and D29 delegation from Claude to Gemini; it did not automatically abolish every restriction in D17.
- D17 says other named tools have no project role and may provide consultative input only if Karim chooses.
- File 08 §9 describes task-based roles, but its current occupant list is still based on the Execution Plan.
- Constitution §9 and Execution Plan §2 still contain restrictive wording for other tools.

A new protocol cannot silently turn consultative tools into active task executors. If the owner wants the bridge to route actual execution to specialist agents, a narrow owner decision must explicitly permit task-scoped assignments while preserving D93/D29 and reserved matters.

### 5C. Draft decision concept — no number assigned

The following is a **draft concept only**. It is not a recorded decision and must not be inserted into 07 or 13 under an invented number.

> **Working title:** Task-Scoped Multi-Tool Collaboration and Local Agent Bridge.
>
> The owner authorizes a controlled, local-first mechanism through which the existing authorized project coordinator may assign temporary specialist tasks to compatible AI tools/surfaces. Each assignment must define mission, role, sources, deliverables, acceptance criteria, permission level, data classification, cost ceiling, and return evidence. The mechanism creates no standing role for any tool, does not transfer D93 project-lead authority, does not expand D29 delegation or reduce owner-reserved decisions, does not waive independent-review rules, and does not override Amadeus verification. The initial deployment uses local MCP and officially supported CLI access under existing/free plan quotas, with no paid API, paid hosting, automatic overages, or GitHub write access. Any change to these cost/privacy constraints requires separate owner approval. Until the decision is recorded, existing tool-role restrictions remain in force.

The final decision text and number must be determined only after D98 is reconciled and the owner explicitly accepts the scope.

---

## 6. Files deliberately left unchanged

- `07_DEIXEN_Canonical_Decisions_and_Current_State.md` — no new or renumbered decision is created here.
- `13_DEIXEN_Decision_Resolution_Register.md` — no decision row is inserted before owner approval.
- `DEIXEN_Operating_Constitution.md` — no role/authority amendment is applied before the governance prerequisite.
- `DEIXEN_Execution_Plan.md` — no current role chart or phase table is silently changed.
- `CLAUDE.md` — no app-side instruction/configuration change is authorized until an adapter is tested.
- `DEIXEN Detour Prompt Package v1.8.MD` — its specialized handoff mechanism remains unchanged.
- `05 — UX Flows, UI Specifications & Design System — Planning.md` — no general AI collaboration material is inserted there.
- `00 — DEIXEN Product Experience & Design Framework Index.md` — no change; the protocol is not within that index's product-design ownership.
- `deixen-app` — no source, content, configuration, or test change is authorized.

---

## 7. Verified / proposed / unresolved status

### Verified in the reviewed sources

- File 08 explicitly excludes detailed prompt-construction and session-handoff mechanics from its scope, while retaining agent behavior, authority, task authorization, independent review, verification, and cost governance.
- The current Constitution §9 and Execution Plan §2 still contain older role restrictions for other tools.
- D93 assigns the project-lead role to Gemini (Gemini 4 Argon as the named pairing) and preserves D29/D12/D13 boundaries.
- The Detour v1.8 package has a strong self-contained HANDOFF BLOCK and Freeze Package pattern; it is a specialized workflow, not a general cross-tool bridge.
- Current 07 ends at D97; the current 13 register does not contain the D98 Home/Learning entry or the D98 dual-design proposal.
- The v0.1 handoff protocol is a proposed Library artifact and not canonical.

### Proposed

- Adopt the v0.2 protocol as the detailed companion to File 08.
- Build a local Agent Bridge that exposes narrow MCP tools and invokes supported official CLI adapters.
- Use Antigravity CLI and Codex CLI as the first technical pilot routes, subject to live installation/access checks.
- Keep GUI-only tools manual in the first version.

### Unresolved

- Recovery/status of `UNIVERSAL_AI_SESSION_HANDOFF_PROTOCOL.md` and `DEIXEN_Prompt_Engineering_and_Governance_UNIFIED_PROPOSED.md`.
- D98 identity and synchronization.
- Whether Decision 17 is to be narrowly amended to permit temporary specialist execution by previously consultative-only tools.
- Which CLI tools are installed and authenticated on the owner's current machine and the exact free/covered plan access available at implementation time.
- Whether the owner has an active Claude Pro/Max plan; no assumption is made.
- Actual Bridge prototype, security test, quota check, Windows integration, and end-to-end invocation test; none has been implemented here.

---

## 8. Application sequence after owner approval

1. Resolve D98 and the current D17/D93 role boundary.
2. Decide whether to adopt the v0.2 protocol and the narrow task-scoped delegation concept.
3. If required, record the new owner decision in the correct sequence in 07 and 13.
4. Apply the minimal File 08 cross-reference/scope edits.
5. Apply the Constitution §9 and Execution Plan §2 changes only to the extent required by the adopted decision.
6. Add the supporting-reference and dependency lines to 00.
7. Re-fetch all target files from current `main`, apply exact edits, and verify diffs before the owner uploads them.
8. Keep the proposed protocol labelled `PROPOSED` until formal adoption has been completed.
9. Start with the local read-only Antigravity-to-Codex pilot. Do not connect Claude Code or GUI-only tools until their exact access route is verified.

No GitHub changes, commits, branches, or pull requests were made by this package.
