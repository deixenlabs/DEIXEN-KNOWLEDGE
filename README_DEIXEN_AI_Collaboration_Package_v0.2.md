# DEIXEN — AI Collaboration, Handoff & Orchestration Package v0.2

**Prepared:** 7 November 2026  
**Knowledge repository snapshot inspected:** `deixenlabs/DEIXEN-KNOWLEDGE` / `main` / `7d5f8e0e6a0e1007dce387d783b31f6214e325c9`  
**Package status:** Proposed for owner review. Not canonical. No GitHub changes were made.

## Why v0.2 exists

The earlier v0.1 document described task briefs, evidence transfer, clarification, independent review, parallel exploration, and return handoffs. That is useful, but it did not define the central mechanism needed for the owner's updated goal: agents should be able to call other compatible agents, use their specialist capabilities, receive their results, and continue the workflow through a controlled shared bridge.

Version 0.2 adds a local-first orchestration architecture and an explicit zero-additional-cost policy. It distinguishes the MCP protocol from the routing software that must sit behind it, and separates automated CLI routes from manual-only GUI surfaces.

## Package contents

1. **`DEIXEN_AI_Collaboration_Handoff_and_Orchestration_Protocol_v0.2_PROPOSED.md`**  
   The complete proposed operating protocol. It defines the local Bridge architecture, MCP/A2A/CLI/API distinctions, free-first integration matrix, capability-based routing, delegation patterns, task packets, security and permissions, evidence returns, Detour compatibility, implementation stages, and acceptance criteria.

2. **`DEIXEN_AI_Collaboration_Integration_and_Governance_Patches_v0.2_PROPOSED.md`**  
   Targeted proposed edits and governance dependencies. It identifies what should change in File 08 and the Corpus Map, what must remain untouched for now, and the decision issue that must be resolved before previously consultative-only tools can become active task executors.

## Current repository state verified

The current `main` snapshot remains at commit `7d5f8e0e6a0e1007dce387d783b31f6214e325c9`. The following current files were read from GitHub:

| File | Current blob SHA | Review relevance |
|---|---|---|
| `08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process.md` | `f0174492cacff24e58ec6e8f1c30ad22f021f410` | Owns agent behaviour, authority, task authorization, independent review, verification and model/cost governance; excludes detailed prompt-construction and session-handoff mechanics |
| `DEIXEN_Operating_Constitution.md` | `e5cff2744ea3f26b629992995299cac26e001f57` | §9 still contains older restrictions on other AI tools |
| `DEIXEN_Execution_Plan.md` | `44098d1957f3bbbe3f58b8e9f379b1314ab9097e` | §2 still lists only the existing project lead/design/code occupants and says no other AI tool has a role |
| `00_DEIXEN_Knowledge_Consolidation_Plan.md` | `9f3b17396ac480dca06acc310aea1bf9f75a5ec2` | A6 lists two older supporting references; A10 records current corpus dependencies |
| `07_DEIXEN_Canonical_Decisions_and_Current_State.md` | `492f65c3c45673aa5042b564fc34d1675d8aeaf6` | The current canonical decision record ends at D97 |
| `13_DEIXEN_Decision_Resolution_Register.md` | `72fb591a52e1bb6d8ece713cee598f04b82284ab` | No D98/D99 entry is present in the current register; D93 is the latest relevant role row |
| `DEIXEN Detour Prompt Package v1.8.MD` | `3fd86699f58bb44a44a4eb3e578b006471194b84` | Read specifically for its Charter, self-contained HANDOFF BLOCK, input preservation and Freeze Package pattern |

The private `deixen-app` repository was not fully audited in this task. Its `CLAUDE.md` was read, but no app implementation work was needed for this documentation/architecture proposal.

## Important findings

### 1. The Detour already contains a strong handoff precedent

The v1.8 Detour package states that step results move forward as HANDOFF BLOCKS, with the block as the only part pasted forward. It requires the block to be self-contained and to include claims, evidence pointers, reasoning, exact input disposition (used/rejected/passed on unchanged), preserved material, open items, coverage, and next-step requirements. Its Freeze Package is a richer handoff containing everything the following step needs. v0.2 preserves this rather than replacing it.

### 2. MCP is the connector, not the whole orchestrator

MCP gives an AI application a standard way to discover and call tools. The proposed DEIXEN Bridge is the software that implements routing: it receives a delegation request, starts a permitted local CLI agent, tracks the task, and returns the result. A2A is an optional later path for remote agents that expose native A2A endpoints; it is not required for the first local prototype.

### 3. A free integration route is plausible, with limits

The strongest initial candidates are Antigravity CLI and Codex CLI, both of which have supported non-interactive execution paths. Codex is included with ChatGPT Free subject to usage limits. Antigravity Individual is free but has weekly limits and plan-dependent model access. Gemini 4 Argon requires Google AI Pro or an eligible trial, so it must not be described as a free baseline. If Argon is not available, the system must not silently swap in another model and still call it the D93 project lead; a different model may be used for a non-authoritative technical pilot or only under a separately permitted task-specific assignment. Claude Code requires Pro/Max or separately billed Console access. Google's Gemini CLI terms restrict third-party software from directly accessing the services powering Gemini CLI through its Google-account OAuth; v0.2 excludes that route. The Google AI Studio free API tier also carries a data-use caveat, so it is not treated as a safe route for confidential DEIXEN content.

“Free” in this package means no new API key billing, paid hosting, purchased credits or automatic overages. It does not mean unlimited model usage.

### 4. Governance currently blocks unrestricted active use of all tools

The current Constitution §9 and Execution Plan §2 still describe other AI tools as having no project role or consultative-only status. D17 and D93 must be read together; D93 did not silently remove every restriction in D17. A task-scoped multi-agent bridge cannot create permission by itself. The integration patches therefore contain a draft owner-decision concept but intentionally do not assign a number or edit the canonical decision records.

### 5. D98 remains unresolved in the current repository snapshot

The accessible Library contains two different D98-labelled documents:

- `D98 — Governance Insertions.md`: Home and Learning experience direction.
- `DEIXEN_Dual_Tool_Design_Role_Amendment_Patches.md`: dual-tool visual design collaboration.

The current canonical 07 and 13 on `main` do not contain D98 or D99. Do not apply the dual-tool patch as written, do not create a guessed D99, and do not rely on either proposal as a canonical decision until the owner resolves the sequence and synchronization.

## What this package does not claim

- It does not implement a DEIXEN Bridge.
- It does not prove the owner's local CLI installations, login state, model quotas, or MCP configuration.
- It does not prove that Claude Design or Google AI Studio GUI sessions can be launched programmatically.
- It does not create project roles or authorize previously consultative-only tools to execute project work.
- It does not authorize code, canonical document, or GitHub changes.
- It does not authorize API spend, purchased credits, or hosted services.

## Recommended next step

Resolve the D98 and D17/D93 governance boundary first. Then, if the owner adopts the v0.2 operating model, run a read-only local pilot connecting Antigravity CLI to Codex CLI through a minimal MCP Bridge, with no paid API key, no cloud hosting, no repository write, and a verifiable task log.
