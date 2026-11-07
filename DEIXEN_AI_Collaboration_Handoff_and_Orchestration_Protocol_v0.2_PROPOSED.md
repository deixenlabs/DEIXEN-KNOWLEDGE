---
name: DEIXEN AI Collaboration, Handoff & Orchestration Protocol
version: 0.2
prepared: 2026-11-07
status: PROPOSED — owner review required; not adopted or canonical
replaces_proposed: DEIXEN_AI_Collaboration_and_Handoff_Protocol_v0.1.md (proposal only; v0.1 remains preserved as history)
owns:
  - reusable task brief and context-transfer mechanics;
  - cross-tool task routing and collaboration patterns;
  - proposed local Agent Bridge operating model and adapter boundaries;
  - receiver preflight, clarification, independent-first-pass and cross-review procedure;
  - return handoff and evidence continuity;
  - zero-additional-cost integration policy and tool-availability classification.
subordinate_to:
  - DEIXEN_Operating_Constitution.md
  - 07_DEIXEN_Canonical_Decisions_and_Current_State.md
  - 08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process.md
  - DEIXEN_Execution_Plan.md
---

# DEIXEN — AI Collaboration, Handoff & Orchestration Protocol

## 1. Purpose

DEIXEN work may move between conversational assistants, research tools, design environments, coding agents, local command-line agents, and specialist reviewers. The project must benefit from their different capabilities without becoming dependent on one vendor, one model, one interface, or manual copy-and-paste as its only integration method.

This protocol defines both:

1. **Collaboration discipline:** how a task is described, scoped, transferred, clarified, reviewed, verified, and handed back.
2. **Tool-to-tool orchestration:** how an authorized agent can ask a central local bridge to start a task in another compatible AI tool, receive its result, pass that result to another specialist, and return a traceable synthesis.

The intended outcome is a coordinated working system, not merely a list of tools and their assigned roles.

The system should:

- use the strongest available tool for the relevant subtask rather than forcing one tool to do everything;
- allow tools to invoke one another through supported interfaces where technically and contractually permitted;
- preserve a common task state, source references, decisions, and permissions across tools;
- distinguish independent work, continuation, critique, and implementation;
- avoid unnecessary model calls, repeated explanations, duplicate research, and avoidable credit consumption;
- operate without new paid API keys, paid orchestration hosting, or automatic overage charges in its initial design;
- remain adaptable when products, models, plans, or access methods change.

**Core principle:** the bridge coordinates access and work; the assigned agents produce analysis or execution; DEIXEN's existing governance and the human owner retain decision authority.

## 2. Scope, ownership and authority boundaries

### 2.1 This protocol owns

- the reusable task brief and evidence packet;
- the minimum context needed by a receiving tool;
- capability-based tool discovery and routing principles;
- the proposed local Agent Bridge and its interaction contract;
- cross-tool continuation, specialist delegation, parallel exploration, independent review, cross-review, synthesis, implementation, and verification handoffs;
- receiver preflight and material clarification behavior;
- cost, privacy, and access checks before a tool is invoked;
- the receiving tool's return package and the next handoff.

### 2.2 This protocol does not own

- project, product, brand, UX, curriculum, architecture, or domain decisions;
- the permanent allocation of project roles or decision authority;
- permission to edit, commit, push, merge, publish, deploy, buy, or spend money;
- the criteria for when independent review is mandatory;
- Amadeus truth or any other specialist domain truth;
- implementation acceptance or software test standards;
- the general theory of prompt engineering beyond task definition and cross-tool transfer;
- permission to bypass an existing DEIXEN decision, source, verification gate, or owner approval.

Those matters remain controlled by their existing owners and governing sources.

### 2.3 No authority is created by the bridge

Installing, configuring, or calling the bridge does not:

- appoint a new permanent project lead;
- make every connected agent a project decision-maker;
- convert a recommendation into an approved decision;
- grant repository write, commit, push, merge, publishing, or deployment permission;
- satisfy an independent-review gate automatically;
- allow an agent to change a reserved owner decision;
- allow any agent to lower DEIXEN's Amadeus verification standard.

A task assignment is not itself authority unless the current governing documents and applicable owner authorization permit that assignment.

**Governance dependency:** current role restrictions in Decision 17, the D93 project-lead delegation, D29 reserved matters, the Operating Constitution §9, and the Execution Plan §2 must be reconciled before the bridge is used to give previously consultative-only tools active project work. This protocol must not silently override them. See the Integration & Governance Patches document.

## 3. Proposed architecture: one local bridge, multiple interchangeable agents

### 3.1 The components

The recommended architecture has five layers:

**A. Human owner and DEIXEN governance**  
The owner establishes the mission, approves reserved matters, sets scope, and grants or withholds execution permission. Canonical decisions and owning documents remain authoritative.

**B. Task coordinator**  
The coordinator interprets the task, decomposes it where useful, identifies the capability needed for each part, chooses the collaboration pattern, and evaluates the returned evidence. Under the current governance baseline, Gemini's project-lead delegation remains governed by D93. The coordinator role must not be reassigned by this protocol. If the D93-named Gemini 4 Argon route is not available under the owner's current plan, the system must not silently substitute a different model and still call it the D93 project lead. A different model may be used for a non-authoritative technical pilot or a task-specific role only where the current governance and owner authorization permit it.

**C. DEIXEN Agent Bridge — working name, not a final product name**  
A small local orchestration service on the owner's computer. It exposes a controlled MCP interface to compatible AI clients and invokes only explicitly registered local agent adapters. It stores task IDs, task packets, status, permissions, returned artifacts, and verification records locally.

The bridge is a traffic controller and evidence courier. It is not another AI model, is not the project lead, and must not make substantive DEIXEN decisions.

**D. Agent adapters**  
A separate adapter for each supported execution surface. An adapter uses the product's documented interface, such as its official CLI in headless mode. Each adapter reports its actual model/surface, authentication route, availability, limits, and errors. Unsupported or GUI-only environments are marked manual rather than simulated as automated.

**E. Local task and evidence store**  
A local folder plus a small SQLite task ledger (or an equally simple local store) records the task packet, routing, status, results, evidence references, file hashes where relevant, and return handoff. It is not a new source of project truth: canonical facts continue to live in their owning files and repositories.

### 3.2 Interaction diagram

```text
Karim / human project owner
          |
          | mission, reserved decisions, approvals
          v
Authorized task coordinator
          |
          | MCP tool call: discover / delegate / retrieve result
          v
DEIXEN Agent Bridge (local; no paid hosting)
          |
          +---- Antigravity CLI adapter (agy)
          |
          +---- Codex CLI adapter (codex exec)
          |
          +---- Claude Code adapter (claude -p; only if access is already covered)
          |
          +---- Other verified adapters added later
          |
          +---- Manual handoff packet for GUI-only tools
          |
          v
Structured results + source evidence + task log
          |
          v
Coordinator review / cross-review / synthesis
          |
          v
Owner approval where required -> next task / implementation / close
```

### 3.3 Why the bridge is the central link

Without a central bridge, every pair of tools would need a separate connection, prompt convention, file-transfer rule, and status mechanism. That creates many fragile links and makes it difficult to know which version of the task or output is current.

With the bridge, each compatible AI client connects to one DEIXEN interface. The bridge knows which adapters are installed and permitted. An agent can request a specialist task through one tool call, receive the specialist's structured response, and continue its own workflow.

The bridge must not decide which tool is best by brand reputation alone. It exposes capabilities and current availability; the coordinator chooses the appropriate route for the task.

### 3.4 Local-first deployment

The first implementation should run locally on the owner's computer:

- no cloud server;
- no hosted orchestration subscription;
- no publicly exposed MCP endpoint;
- no new external database;
- no paid API key;
- no automatic billing or purchased credits;
- no automatic GitHub writes.

Use a local MCP transport supported by the connected clients. A local `stdio` server is the simplest starting point and avoids opening a network port. If verified client compatibility later makes a shared `localhost` Streamable HTTP server materially better, it may be evaluated while remaining bound to the local machine and protected against other local processes. Do not expose the bridge to the public internet in the initial release.

A single local task store can be shared by separate local bridge processes if the clients use `stdio`; alternatively, a single local server may serve multiple verified clients. The implementation choice must be tested against the actual supported clients rather than assumed.

## 4. MCP, A2A, CLI and API — what each one does

These technologies solve different problems and must not be treated as interchangeable.

| Technology | What it does | Role in the proposed system |
|---|---|---|
| MCP (Model Context Protocol) | Standard interface through which an AI application can discover and call tools, read resources, and use prompt templates exposed by a server | The preferred common interface between compatible AI clients and the DEIXEN Bridge |
| A2A (Agent2Agent) | Open protocol for communication and task exchange between independent agent applications | A possible later layer if agents expose A2A endpoints and direct agent-to-agent discovery is genuinely needed |
| Official CLI | A vendor-supported command-line interface that can be run interactively or programmatically | The preferred way for the local bridge to start a worker agent without a separately billed API key, when the product and plan permit it |
| API | A programmatic service interface to a model or agent | Excluded from the initial zero-additional-cost baseline unless an owner-approved free tier is both suitable and safe for the data involved |

**MCP alone does not make two AI models talk to one another.** MCP gives an AI host access to tools. The DEIXEN Bridge supplies the missing orchestration logic: one of its tools can receive a delegation request, invoke a registered agent adapter, collect its result, and return that result to the caller.

**A2A is not required for the first version.** It is worth considering later if a vendor or specialist agent exposes a native A2A endpoint. Building an A2A network now would add complexity without solving a confirmed blocker that a local MCP bridge and official CLIs cannot solve.

## 5. Zero-additional-cost policy and verified integration options

### 5.1 Meaning of “free”

The required target is **zero additional direct spend for the initial bridge**. It does not mean unlimited AI inference or zero consumption of the usage quotas attached to an existing plan.

The bridge must use existing subscriptions or free allowances only. It must not silently switch to a paid API, purchase credits, enable overages, or create cloud infrastructure charges.

The default configuration is:

```text
NEW_PAID_API_KEYS = DISABLED
PAID_API_FALLBACK = DISABLED
PURCHASED_CREDITS = DISABLED
AUTOMATIC_OVERAGES = DISABLED
CLOUD_HOSTING = DISABLED
PUBLIC_MCP_ENDPOINT = DISABLED
GITHUB_WRITE_ACTIONS = DISABLED
```

If a task cannot run under the currently available no-additional-cost routes, the bridge must report “not available under current free/covered access” and offer a manual or later alternative. It must never quietly create a bill.

### 5.2 Tool capability and access matrix as of 7 November 2026

Availability, plan limits, model names, and vendor terms can change. The bridge must perform a current availability check at setup and before an invocation rather than permanently hardcoding today's plan table.

| Tool / surface | Verified programmatic path | No-additional-cost position | Proposed status |
|---|---|---|---|
| Google Antigravity CLI (`agy`) | Official headless CLI, JSON/stream-JSON output, session continuation, model/agent selection, MCP support, and native subagents | Individual plan is $0 and includes CLI access, but has basic weekly limits. Free model access differs from paid plans. Gemini 4 Argon requires Google AI Pro/eligible trial; it is not a baseline free model. Claude Sonnet 4.6 and Opus 4.6 are listed for the free tier at the time of this review but are scheduled for removal on 18 November 2026. | **Primary initial Google-side adapter**, with live model/plan check. Never assume Argon 4 is free. |
| OpenAI Codex CLI | Official `codex exec` non-interactive mode, JSONL output, local CLI authentication through a ChatGPT account, and MCP client configuration | Codex is included in ChatGPT Free with plan-dependent limits. Codex Cloud is not included in Free; the proposed path is the local CLI, not Cloud tasks. | **Primary initial OpenAI-side worker adapter**, subject to account allowance and local sandbox. |
| Claude Code CLI | Official `claude -p` non-interactive mode and MCP support | Claude Code access requires an active Claude Pro or Max subscription, or separately billed Console access. Claude Free alone is not a zero-cost route. | **Conditional adapter only if the owner already has an active Pro/Max subscription.** Do not use Console API billing in the initial baseline. |
| Gemini CLI | Official headless mode, JSON output, and MCP client support | Google documents free access through a Google account under Gemini Code Assist individual limits. However, Google's Gemini CLI terms explicitly prohibit third-party tools/services from directly accessing the services powering Gemini CLI through its OAuth credentials (an OpenClaw example is given). | **Do not let the Bridge spawn or wrap Gemini CLI using its Google-account OAuth.** It may be used directly by the owner as a first-party CLI, but it is not an outbound worker adapter in this design. Use the official Antigravity CLI for Google-agent orchestration instead. |
| Google AI Studio web app | Visual playground and official Gemini API/Interactions API | API free tiers exist, but Google's pricing table states that free-tier prompts/responses may be used to improve its products. API use is also distinct from operating the AI Studio web UI. | **Manual GUI handoff in the baseline.** Do not send confidential DEIXEN materials through a free API tier. A later API route requires a data/privacy and billing review. |
| Claude Design | The design environment is available as a product surface; no verified public CLI/agent endpoint for automating a Claude Design workspace was established in this review | The Claude Design workspace must not be equated with Claude Code or with access to the same model in another application. | **Manual design handoff in v1.** Bridge prepares the brief and returns collected deliverables; the user opens and runs the design environment. |
| ChatGPT conversation UI | No supported general-purpose external API to operate this specific conversation as an agent was established here | ChatGPT subscription usage is not the same thing as a public API key. | **Manual conversational handoff.** Use Codex CLI as the separate programmable OpenAI agent surface where appropriate; do not claim it is the same experience as ChatGPT web. |

### 5.3 Important free-tier privacy and terms restrictions

1. **Gemini CLI OAuth restriction:** the Bridge must not call Gemini CLI as a subprocess using the owner's Google-account OAuth credentials. Google's terms warn against third-party tools/services doing this. The first implementation should use the official Antigravity CLI for Google-side automated work.
2. **Google AI Studio free API:** the free-tier pricing information states that content may be used to improve Google's products. Do not treat “free API” as automatically suitable for private DEIXEN source files, internal strategy, or any sensitive data. Use sanitized public/non-confidential excerpts only if separately permitted; otherwise use another approved route or manual review.
3. **Claude Code:** a free Claude account does not include Claude Code. Do not create a Console API key or trigger usage-based billing merely to complete a bridge task.
4. **Antigravity model availability:** do not describe Gemini 4 Argon as free. Under the current model table, Argon requires Google AI Pro or an eligible trial. The exact free models and the temporary 4.6 model window must be checked at runtime.
5. **Codex:** use the local CLI with ChatGPT-managed authentication and the plan's own limits. Do not switch to an API key or Codex Cloud charge as an automatic fallback.

### 5.4 What “zero cost” can and cannot guarantee

The software layer can be free: MCP is an open protocol, the bridge can be a small local open-source program, SQLite is local, and the CLI software can be installed without paying for a bridge service. But the model calls still consume the quota of the plan or free allowance being used. Free quotas may be reduced, exhausted, changed, or unavailable at a given time.

The system can guarantee that it does not intentionally create additional API or hosting charges. It cannot guarantee unlimited inference or that a provider will keep a particular free model available.

## 6. Capability-based agent registry and routing

### 6.1 Do not hardcode permanent vendor roles

The registry is an inventory of available execution routes, not a permanent role chart. The same model or application may perform different work depending on the task, enabled tools, account plan, and permissions. A model name alone does not establish role, authority, or capability.

Each registered agent route should declare:

- product and exact surface (for example, Antigravity CLI rather than simply “Gemini”);
- model/version currently available, if exposed;
- authentication type (included plan, local account session, API key, or manual GUI);
- available capabilities (web research, code reading, code writing, test execution, design exploration, image generation, document editing, structured output, long-context review, local files, MCP, etc.);
- known constraints and unsupported operations;
- plan/quota status when the product exposes it;
- permitted working directories and file classes;
- default execution mode (read-only, review-only, proposal, or separately authorized write);
- current status: AVAILABLE / LIMITED / AUTH REQUIRED / PAID ONLY / MANUAL ONLY / DISABLED.

### 6.2 Routing rules

The coordinator selects an agent based on:

1. the subtask's actual capability requirements;
2. source access and quality requirements;
3. ability to return verifiable, structured evidence;
4. current no-additional-cost access;
5. context-transfer and privacy restrictions;
6. the task's authorization and risk level.

Do not run every available agent on every task. A second agent is justified when it contributes a distinct capability, a useful independent view, or meaningful risk reduction. Agreement between multiple AI agents is not proof by itself.

### 6.3 Agent identity must be explicit

Every result must identify the actual tool, product surface, model/version when available, access route, and whether the result came from a native agent session, a CLI subprocess, an MCP tool, or a manual GUI handoff.

Do not label a Codex CLI run as a ChatGPT web conversation, a Claude model selected inside Antigravity as Claude Design, or an Antigravity-hosted Gemini model as the standalone Gemini CLI.

## 7. Collaboration patterns: select the right workflow

The sender/coordinator must choose one of these patterns before delegating. They are not interchangeable.

### 7.1 Direct execution

One assigned tool completes a bounded task. Use when the task is self-contained and one tool has the necessary capabilities. No second agent is required merely for appearance.

### 7.2 Continuation delegation

A receiving agent continues unfinished work. Transfer the current state, prior decisions, reasons, evidence, open items, and exact remaining task. The receiver may challenge an item when new evidence or a contradiction justifies it, but must not silently rewrite history.

### 7.3 Specialist delegation

The coordinator breaks a material task into bounded subtasks and sends each to the agent with the relevant capability. Examples: source research, repository inspection, test execution, design exploration, document consistency review, or structured data analysis. Each specialist returns evidence and a clear boundary around what it did not verify.

### 7.4 Parallel independent first pass

Use when genuinely independent perspectives are valuable. Send the same essential sources, context, constraints, and neutral criteria to each agent. Do not reveal another agent's findings or preferred conclusion before the first pass is complete.

This is especially useful for creative exploration, major product strategy, architecture alternatives, and high-risk audits.

### 7.5 Cross-review

Only after independent first passes exist may one agent review the other's output. The review must target evidence, acceptance criteria, omissions, and practical consequences—not author identity or style preference.

If the reviewer has already seen the prior analysis, label the review as exposed rather than cleanly independent. File 08 §13 remains controlling for any formal independent-review gate.

### 7.6 Synthesis

The coordinator compares each claim against the source evidence and acceptance criteria. It preserves disagreement, uncertainty, and unresolved questions. It does not average the agents' answers or let the majority vote become truth.

### 7.7 Implementation and verification

An implementation agent receives only an approved specification, exact repository and branch, base commit, file scope, permissions, and test requirements. A separate verification assignment may be made when allowed and useful. The bridge must not merge, push, publish, or change canonical decisions by default.

### 7.8 Manual GUI handoff

When an environment has no verified machine interface, the bridge creates a ready-to-send brief, packages required inputs, states the exact expected return, and records the returned result when the owner brings it back. It must not claim automated execution.

## 8. The Bridge's MCP contract

The initial Bridge should expose a small number of narrow tools. Tool names below are a proposed interface, not implemented functionality.

| Proposed MCP tool | Purpose | Safety rule |
|---|---|---|
| `list_available_agents` | Return the current registry: routes, capabilities, status, limits, and manual-only options | Must not infer or invent availability; probe the installed CLI and report unknown states |
| `prepare_task_packet` | Create a complete, self-contained task packet and a local task ID | Does not grant authority or start execution |
| `delegate_agent_task` | Start one registered agent adapter with a bounded task packet | Must validate allowed agent, task type, permissions, directory, cost policy, and concurrency before starting |
| `get_agent_task_status` | Return queued/running/completed/failed/blocked state and progress metadata | No claim of completion until the worker process returns success and output is checked |
| `get_agent_task_result` | Retrieve the worker's structured return package and artifact references | Must preserve source references and distinguish result from approval |
| `prepare_manual_handoff` | Create a ready-to-send brief for GUI-only tools such as Claude Design or Google AI Studio | Clearly labels it MANUAL; does not pretend to start the GUI session |
| `record_owner_approval` | Record an explicit owner approval supplied through an authorized UI action or confirmed human input | Must not infer approval from silence, a model response, or a file upload |

The bridge must not expose an unrestricted `run_any_shell_command`, arbitrary filesystem access, or unrestricted Git write capability to remote or model-controlled calls.

### 8.1 Minimum task record

Each task receives a unique local ID and records:

- task ID, date/time, sender and receiving tool/surface;
- parent task ID if this is a delegated subtask;
- mission, work type, execution authorization, and expected output;
- exact agent route, model/version and access route;
- source files/URLs/commits and their evidence classification;
- allowed and prohibited actions;
- permitted path list and read/write mode;
- cost policy and whether an additional owner approval is required;
- task status, worker output, logs, usage metadata when available;
- artifacts created and hashes when appropriate;
- unresolved questions and return handoff.

### 8.2 Prevent loops and runaway delegation

The initial bridge should enforce:

- delegation depth limited to one worker level by default;
- no automatic recursive delegation by a worker unless specifically enabled for that task;
- a bounded number of parallel workers set in configuration;
- a bounded retry count;
- a task timeout and cancellation route;
- no duplicate invocation after a successful result unless a new reason is recorded;
- no repeated cross-review loop without a material finding;
- an explicit stop when a provider quota is exhausted or a paid route is the only remaining option.

The point is to use the tools more intelligently, not to multiply model calls.

## 9. Task brief and handoff packet

The brief should be proportionate to risk. Do not make a large form for every small task. The bridge can assemble the packet from project sources and the coordinator's task request.

### 9.1 Required core for material work

1. **Mission and reason** — what must be achieved and why it matters.
2. **Task type** — research, review, audit, design exploration, implementation, testing, verification, synthesis, or continuation.
3. **Recipient and exact surface** — the tool, product, and interface that will actually perform the task.
4. **Current state** — completed work, actual status, what remains, and what is not known.
5. **Sources and evidence** — precise files, sections, URLs, versions, commit SHAs, screenshots, tests, and data; distinguish VERIFIED, OWNER-REPORTED, PRIOR-AGENT CLAIM, HYPOTHESIS, and UNKNOWN.
6. **Decisions and constraints** — relevant canonical decisions, status, reason for important boundaries, and rejected or open alternatives when material.
7. **Expected deliverables and acceptance criteria** — observable result and required format; do not prescribe the review verdict.
8. **Role, authority and permissions** — what this agent is assigned to do, read/write limits, external actions, and who approves.
9. **Clarifications and assumptions** — ask only questions that materially change scope, safety, correctness, authority, or acceptance.
10. **Verification and return handoff** — evidence to provide, what must be checked, and what the next participant needs.

### 9.2 Useful technical state for code work

Where relevant include:

- repository and exact path;
- branch and base commit SHA;
- actual clean/dirty state;
- changed files and commit status;
- build/test baseline and exact commands;
- environment and access assumptions;
- permitted operations, especially local writes, commits, pushes, merges, and publishing;
- any workspace isolation or worktree requirement.

The receiving agent must inspect its own workspace. It must not assume that another tool's local files, credentials, browser session, conversation memory, or uncommitted changes are shared.

### 9.3 Evidence and source preservation

Do not send a prior agent's conclusion without the sources needed to test it. Prefer precise references to authoritative files over copying entire repositories. Copy the relevant evidence passages or files when the recipient cannot access the source directly. Never copy passwords, API keys, session tokens, personal secrets, or `.env` files.

For Amadeus, the current Verified Reference and verification rules remain controlling. An agent's model memory or simulator output cannot upgrade an unverified claim.

## 10. Receiver preflight and clarification

Before material work begins, the receiving agent must:

1. Restate its understanding of the mission, task type, scope, expected deliverables, and permissions.
2. Identify conflicts between the task packet, the current source files, decisions, and the actual environment.
3. Separate facts it has verified from facts it has only been told.
4. Identify missing information that could materially change the result, safety, authority, or acceptance.
5. Ask only the questions needed to resolve those material gaps.

There is no minimum number of questions. If the task is clear, proceed. If an ambiguity is non-blocking, state the assumption and its effect. If a missing answer changes scope, authority, source correctness, or acceptance, stop at that boundary and ask before the affected action.

Do not repeat a question already answered in the task packet or current governing source. Do not ask for approval where valid approval already exists; do not infer approval where it does not.

## 11. Anti-bias and independent review

The receiver evaluates the actual artifact and evidence, not its presumed author.

- Do not assume a result is good because it came from the project lead or a preferred tool.
- Do not assume a result is defective because it came from a different model or uses a different implementation style.
- Inspect the original artifact and source material when the claim depends on them.
- A previous summary is a navigation aid, not a substitute for the current source.
- For an independent first pass, do not expose the previous agent's recommendation, preferred verdict, or persuasive framing unless required by the task.
- If prior findings were visible, disclose that exposure.
- A separate vendor/model brand does not automatically make a review independent.
- Formal independent-review requirements and limits remain controlled by File 08 §13.

## 12. Permissions, security and cost controls

### 12.1 Default permission levels

- **READ_ONLY:** inspect, research, and report; no file changes.
- **REVIEW_ONLY:** critique or verify; no file changes.
- **PROPOSAL_ONLY:** draft replacement text or patch suggestions, but do not apply them to canonical files.
- **WORKSPACE_WRITE:** edit only a named local workspace or isolated worktree; no commit/push/merge unless separately authorized.
- **EXTERNAL_ACTION:** publish, send, spend, deploy, or contact an outside party; always requires separate explicit owner authorization.

A task may not silently escalate from one level to another.

### 12.2 Repository protections

For the initial bridge:

- GitHub writes, pushes, merges, releases, and PR creation are disabled;
- canonical repositories are read-only by default;
- implementation tasks use a separate local worktree or isolated copy;
- simultaneous workers must not write to the same files;
- the bridge checks path allowlists before reading or writing;
- all modifications are reported as diffs and remain unaccepted until the authorized review/approval process;
- secrets, credentials, `.env` files, and private authentication material are never passed to model prompts.

### 12.3 Data classification

Before routing material to an external service, label it:

- **PUBLIC:** safe to send through a public tool;
- **INTERNAL:** ordinary project information, subject to the provider/account terms approved by the owner;
- **CONFIDENTIAL:** private product strategy, private code, commercial information, or sensitive learner information; only send through an explicitly approved route with appropriate data handling;
- **SECRET / CREDENTIAL:** passwords, tokens, API keys, private keys, or equivalent; never send to any model or handoff packet.

If the privacy terms of a free route do not fit the data classification, do not use that route just because it is free.

### 12.4 Cost checks

Before every invocation, the bridge checks that the route is included in the owner's permitted no-additional-cost configuration. If the only available route is paid, exhausted, or uncertain, it stops and reports the condition. No fallback to API billing, paid credits, or a paid plan is allowed by default.

## 13. Return handoff: what every agent must give back

The receiving tool returns a structured result useful to the next participant without reconstructing the conversation:

1. **Outcome:** COMPLETED / PARTIALLY COMPLETED / BLOCKED / FAILED / NOT STARTED.
2. **Understanding:** the mission and scope it actually worked against.
3. **What was done:** concrete analysis, edits, research, designs, or tests.
4. **What was not done:** unverified claims, skipped checks, unresolved questions, and prohibited actions not taken.
5. **Evidence:** source references, exact file paths/sections, test results, screenshots, logs, commit/branch identifiers, and usage metadata when available.
6. **Artifacts:** exact path, version, file hash where practical, and whether the artifact is a proposal or an applied change.
7. **Risks and deviations:** contradictions, assumptions, limitations, and scope changes.
8. **Next action:** the specific next task, the appropriate recipient, and required input.
9. **Updated handoff packet:** when work will continue in another tool, a self-contained packet for that tool.

Never report “done,” “verified,” “merged,” “uploaded,” “approved,” or “independent” unless that state has supporting evidence. Completion of an agent task is not project acceptance.

## 14. Compatibility with the existing Detour handoff method

`DEIXEN Detour Prompt Package v1.8.MD` already contains a mature task-specific handoff mechanism and must not be rewritten or replaced by this general protocol.

Its established strengths should be reused:

- each step is started separately and stops after its own deliverable;
- the result moves forward through a HANDOFF BLOCK;
- the HANDOFF BLOCK is self-contained and includes the evidence pointers and reasoning required by the next step, rather than saying “see the report above”;
- inputs are explicitly used, rejected with a reason, or passed on unchanged; nothing is silently dropped;
- open items, coverage, preserved material, and next-step requirements are carried forward;
- the Freeze Package is a richer handoff that contains the accepted Freeze plus all details required by the next step;
- the canonical 07 remains the decision source, while the Freeze Package is the operational working copy of the accepted material.

This generic protocol adds cross-tool routing and a reusable bridge. It does not weaken or duplicate a stricter approved workflow. When a specialized workflow defines a stronger handoff contract, preserve that contract and add only missing technical routing or tool-identity information.

## 15. Relationship to existing DEIXEN documents

| Document | Existing ownership | Relationship to this protocol |
|---|---|---|
| `DEIXEN_Operating_Constitution.md` | Operating method, authority hierarchy, source/evidence handling, change management, roles | Higher authority. Any active specialist-agent assignment must be permitted by the current governance decision; this protocol cannot grant it |
| `07_DEIXEN_Canonical_Decisions_and_Current_State.md` | Canonical decisions and current state | Remains the source of project decisions; task packets may not amend it |
| `13_DEIXEN_Decision_Resolution_Register.md` | Decision status and resolution record | Records any formally adopted governance change through the proper process |
| `DEIXEN_Execution_Plan.md` | Phases, sequencing, gates, and current roles | Continues to control current project work and role allocation |
| `08_DEIXEN_Canonical_AI_Working_Rules_and_Dev_Process.md` | AI behavior, task authorization, reviewer rules, authority, verification and cost/model discipline | Governing AI rules; this protocol supplies the detailed operational routing, bridge, and transfer method beneath it |
| `00_DEIXEN_Knowledge_Consolidation_Plan.md` | Corpus map and dependency lines | Should record this proposed supporting document only after owner acceptance |
| `CLAUDE.md` | App-specific Claude Code instructions | Remains specific to Claude Code; add a short bridge connection note only if the adapter is actually configured and separately approved |
| `DEIXEN Detour Prompt Package v1.8.MD` | The Detour Charter, Prompt 0–7 and accepted HANDOFF BLOCK / Freeze Package method | Specialized workflow remains intact; this protocol supplements but does not replace it |
| `DEIXEN_Amadeus_Verified_Reference.md` | Verified Amadeus domain truth | Remains controlling; no handoff, bridge, or model output can upgrade an unverified claim |
| `05 — UX Flows, UI Specifications & Design System — Planning.md` | Product UX and UI specifications | Not the owner of general AI-agent collaboration or orchestration |

The old supporting references `UNIVERSAL_AI_SESSION_HANDOFF_PROTOCOL.md` and `DEIXEN_Prompt_Engineering_and_Governance_UNIFIED_PROPOSED.md` remain unresolved: they are named in the current corpus map and referenced by File 08, but their full contents were not located in the accessible Library or current main snapshot during this review. Do not assume they are obsolete or duplicate until their originals are recovered or their absence is formally resolved.

## 16. Adoption and staged implementation

This version remains a proposal. Uploading it, linking to it, or adding it to an AI prompt does not make it canonical or create authority.

### Stage 0 — Governance reconciliation

Before allowing external tools to act as project workers:

1. Resolve the D98 identity conflict described in the Integration & Governance Patches document.
2. Review Decision 17's consultative-only restriction alongside D93, D29, Constitution §9, File 08 §9, and Execution Plan §2.
3. If desired, adopt a narrowly scoped owner decision allowing authorized, temporary specialist assignments through the bridge while preserving the project lead, owner authority, D29 reserved list, Amadeus verification rules, and independent-review controls.
4. Record the decision in the correct sequential position only after the current decision record is reconciled. Do not invent a number.

### Stage 1 — Read-only technical pilot

- verify the owner's local installations and authenticated routes;
- verify `agy` and `codex exec` versions, current available models, account limits, and MCP support;
- confirm whether the D93-named Gemini 4 Argon route is actually available; if not, keep the pilot strictly technical/non-authoritative unless a separate owner decision permits a different coordinator;
- create a minimal local Bridge prototype with `list_available_agents`, `prepare_task_packet`, `delegate_agent_task`, `get_agent_task_status`, and `get_agent_task_result`;
- run Antigravity-to-Codex read-only delegation on a non-sensitive sample task;
- confirm no API key, paid endpoint, cloud deployment, GitHub write, or overage is used;
- verify structured result, provenance, task log, cancellation, and error handling.

### Stage 2 — Controlled specialist workflows

After the read-only pilot and required governance approval, test:

- one specialist task delegated by the authorized coordinator, without silently substituting the D93 project-lead model;
- one independent parallel first pass;
- one cross-review after first-pass completion;
- one synthesis with source/evidence comparison;
- a manual-only handoff to Claude Design or Google AI Studio.

### Stage 3 — Limited write workflow

Only after Stage 1 and 2 are accepted: enable local workspace writes in an isolated worktree for a narrowly named task. Keep commits, pushes, merges, publishing, deployment, and canonical decision edits disabled unless separately authorized.

### Stage 4 — Expand selectively

Add more adapters only when they offer a verified, materially useful capability under the no-additional-cost and data-handling rules. Consider A2A only when an agent needs native remote agent-to-agent interoperability that the local Bridge cannot provide cleanly.

## 17. Acceptance criteria for the first bridge prototype

The first prototype is acceptable only when all applicable checks pass:

1. It runs locally and requires no paid cloud hosting.
2. It exposes a documented MCP interface to each client that is actually tested.
3. An authorized coordinator can call the Bridge to start a separate supported CLI agent task.
4. The Bridge returns a stable task ID and status, and the coordinator can retrieve the exact result.
5. The returned result identifies the actual tool/surface/model/access route and does not mislabel one product as another.
6. Task packets include mission, source/evidence, expected output, acceptance criteria, permissions, and return requirements.
7. Read-only is the default; writes require per-task authorization and an isolated workspace.
8. No GitHub write, push, merge, publish, deploy, or external action is enabled by default.
9. The Bridge cannot silently switch to a paid API, purchased credits, or automatic overage.
10. Gemini CLI OAuth is not invoked by third-party orchestration code.
11. Sensitive data is not sent through a free-tier route whose terms are unsuitable for that data.
12. Manual-only tools are accurately reported as manual; the Bridge does not simulate having invoked them.
13. Parallel first-pass, cross-review, and synthesis are kept distinct in the task log.
14. Failed, blocked, incomplete, and cancelled tasks are reported honestly.
15. At least one end-to-end test shows an agent calling the Bridge, the Bridge invoking another permitted agent, and the result being returned to the initiating agent.

## 18. Operating principle

**Use the best available capability, not the most familiar brand. Connect the tools through one controlled bridge, not through an uncontrolled web of direct permissions. Transfer evidence, not bias. Transfer the task, not authority. Keep cost and data handling visible.**

A successful orchestration cycle is one in which the right agent completes the right bounded task, another agent can verify its claims where needed, the coordinator preserves disagreement and source evidence, and the owner retains every decision reserved to them.

## 19. Official technical references checked for this proposal

The following are current official or project-standard references checked on 7 November 2026. Recheck availability and terms before implementation because these may change.

### Antigravity

- Antigravity CLI headless mode, machine-readable output, session continuation and model selection: https://antigravity.google/docs/cli/headless/
- Antigravity CLI MCP support: https://antigravity.google/docs/mcp
- Antigravity CLI subagents: https://antigravity.google/docs/subagents?tab=cli
- Antigravity plans and baseline quota: https://www.antigravity.google/docs/plans
- Antigravity model availability by plan: https://antigravity.google/docs/models/
- Antigravity pricing: https://antigravity.google/pricing

### OpenAI Codex

- Codex CLI `codex exec` non-interactive mode: https://learn.chatgpt.com/docs/non-interactive-mode
- Codex CLI reference: https://learn.chatgpt.com/docs/cli/reference
- Codex included with ChatGPT plans, including Free, and usage limits: https://help.openai.com/en/articles/11369540-using-codex-with-your-chatgpt-plan
- OpenAI developer MCP documentation and Codex client setup: https://developers.openai.com/learn/docs-mcp

### Anthropic

- Claude Code CLI reference (`claude -p`): https://docs.anthropic.com/en/docs/claude-code/cli-usage
- Claude Code setup and supported authentication routes: https://docs.anthropic.com/en/docs/claude-code/getting-started
- Claude Code access through Pro/Max: https://support.anthropic.com/en/articles/11145838-using-claude-code-with-your-max-plan

### Gemini and Google AI Studio

- Gemini CLI MCP server configuration: https://github.com/google-gemini/gemini-cli/blob/main/docs/tools/mcp-server.md
- Gemini CLI terms and privacy notice, including the restriction on third-party services using Gemini CLI OAuth: https://github.com/google-gemini/gemini-cli/blob/main/docs/resources/tos-privacy.md
- Gemini CLI quota and pricing: https://google-gemini.github.io/gemini-cli/docs/quota-and-pricing.html
- Google AI Studio Interactions API: https://aistudio.google.com/docs/get-started
- Gemini API pricing and free-tier data-use disclosure: https://ai.google.dev/gemini-api/docs/pricing.md

### Open protocols

- MCP architecture overview: https://modelcontextprotocol.io/docs/learn/architecture
- MCP architecture specification: https://github.com/modelcontextprotocol/modelcontextprotocol/blob/main/docs/specification/2026-07-28/architecture/index.mdx
- A2A Protocol v1.0 overview/specification: https://a2a-protocol.org/v1.0.0/

---

**Status reminder:** This document is a proposal for owner review. It does not authorize or claim a local Bridge implementation, a new project role, a change to D17/D93/D29, any API expenditure, or any repository action.
