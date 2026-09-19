# AeroBridge — Master Meta-Audit & Independent Decision Engine

**Role:** Independent fourth-pass adjudication of Audit A (ChatGPT Master Synthesis), Audit B (Manus Master Synthesis), and Audit C (Stage 4 Master Consensus), cross-checked against the current Project Knowledge (Phase 1–3 notes, the Claude AeroBridge Knowledge Pack, the Arabic audit-plan governance doc), all seven supplied screenshots, and the AeroBridge Master Project Instructions.
**Method:** Evidence arbitration, not majority vote. Repetition across audits is treated as a corroboration signal only, never as proof.
**Status:** Preserve and Refine — confirmed independently, with one material correction to how "fixed" should be read right now (§7, §10).

---

## 1. Executive Verdict

**AeroBridge should be preserved and refined. All three candidate audits reach this same direction independently, and direct source inspection in this pass confirms it is earned, not aspirational** — a real Flight Deck Console identity, a genuine Terminal workstation with working command history and Focus Mode, and a five-screen loop wired through real state and real `localStorage` persistence, not implied by navigation alone.

Two things this pass adds that none of the three candidate audits could see:

1. **The corpus itself has drifted.** The project's own Phase 2/3 process notes and the "Claude AeroBridge Knowledge Pack" — the artifact presented as *current* source for this review — disagree with each other on whether the two headline P0 defects every audit independently found (empty-input fabricating a command; a fabricated red error on first use) are actually fixed. Direct line-level evidence shows at least three specific fixes genuinely landed in *some* build (Coach neutral-state, the language-toggle honesty fix, and partial tab-ARIA semantics), yet the Knowledge Pack's own bundled full source still contains the pre-fix code for all of them, verbatim. This is addressed in full in §7 and §10 and is now the single highest-priority item in this report, ahead of every UI fix below it, because no other finding can be trusted as "still open" or "already closed" until it is resolved.
2. **A second competency domain — Customer Service / soft-skills — already exists inside the product's data model (a skill row, a scenario category, a track selector) but has no real content, no practice mechanism, and no assessment engine of its own.** All three audits correctly flag the track-selector as a *labeling honesty bug* (Technical content shown under a Service label). None of the three step back and ask the strategic question this pass asks in §9 and §11: is AeroBridge a single-domain GDS-command trainer with a Customer Service *label* attached, or does it intend to become a genuine dual-competency (technical + service) readiness product? The Growth Record's own skill model has already answered "dual" at the data layer (`DE-ESC` sits alongside `AN`/`SS`/`FQD`/`FXP` as an equally-weighted skill), while the content layer has not caught up. This is a product-architecture decision hiding inside what looked like a UI bug.

Everything else in this report — the accessibility pass, the mobile hardening, the provenance sweep, the false-affordance cleanup — is convergently confirmed by all three audits and by this pass's own direct source reading, and can proceed on the timeline in §29–§31. None of it requires touching the command engine, the scoring formula, or the route structure.

---

## 2. Context-Reconstruction Summary

Before forming any judgment, this pass retrieved and read in full:

- **The Master Project Instructions** governing this project (preservation boundaries, evidence hierarchy, the Claude/Manus role split, the priority model, the AI self-review loop).
- **`AeroBridge_Master_Meta_Audit_Prompt.md`** (1,229 lines) — the operative instruction set for this specific deliverable, read in full before any analysis began.
- **All three candidate audits in full:** `CHATGPT_AEROBRIDGE_MASTER_SYNTHESIS_AUDIT.md` (1,263 lines), `MANUS_AEROBRIDGE_MASTER_SYNTHESIS_AUDIT.md` (313 lines), `AEROBRIDGE_STAGE4_MASTER_CONSENSUS_AUDIT.md` (1,126 lines) — every decision table, preservation section, rejection list, and open-question list in each.
- **Current Project Knowledge:** `AeroBridge_Phase_1_Scope_Notes.md`, `PHASE_2_SOURCE_MAPPING.md`, `Phase_3_Live_Findings.md`, `Claude_AeroBridge_Knowledge_Pack.md` (the full current `Home.tsx`, `index.css`, `index.html`, and every supporting component), and the Arabic-language audit-governance plan.
- **All seven supplied screenshots**, inspected directly rather than inferred from filenames — these are the same seven images (`55514`–`55528.jpg`) already used as evidence by all three candidate audits, not new material, and every one is a mobile capture (~360–430px). **No desktop or tablet screenshot exists anywhere in this project's evidence history**, a gap this pass treats as material (§10, §17).
- **Direct source verification**, via targeted search of the bundled current source, of roughly twenty specific claims made across the three audits — not to re-litigate settled findings, but to determine which are still open, which are already fixed, and where the two disagree (§7).

This sequence — Project Knowledge and visual evidence before verdicts — follows the meta-audit prompt's non-negotiable protocol. The single most consequential thing it surfaced was not in any of the three audits: an unresolved conflict inside the Project Knowledge itself about the current state of the two most-cited defects.

---

## 3. Reconstructed AeroBridge Model

**What AeroBridge is, independent of any audit's framing:** a self-contained, client-side training simulator for airline-reservation agent workflows, styled as an operational "Flight Deck Console." A learner practices a small, realistic-looking command vocabulary (`AN`, `SS`, `FQD`, `FXP`) modeled on Amadeus-style GDS syntax, inside a literal terminal UI, and receives a locally-computed accuracy/sequencing/hint score with no live carrier system behind it — a fact the product discloses explicitly and consistently ("LOCAL TRAINING SIMULATION," "ILLUSTRATIVE · VERIFY WITH YOUR COURSE MATERIAL").

**Who it is for:** an entry-to-intermediate learner preparing for a reservations/ticketing agent role, with an explicit Saudi-market lean (a "Saudi readiness" metric, an Arabic-toggle affordance, a persona name — Karim Ahmed — consistent with the region). The vocabulary taught is basic (one workflow, four commands), which is consistent with an early-stage or foundational learner, not an advanced-certification tool.

**What problem it solves:** the gap between not knowing GDS command syntax/sequence and being able to execute one real booking-to-ticketing workflow under evaluation, with a persisted record a learner (or instructor) can point to as evidence of practice.

**Core loop, confirmed by direct source (`setPracticeContext` call sites, `localStorage` read/write across three screens):**

> Progression (orientation) → Practice (Terminal: Learn → Practice → Assessment) → assessment record persisted → Growth Record (skill-level interpretation) → Progress Tracking (session-level trend) → Scenarios (contextual application) → back into Practice with carried context.

This is a real, working spine, not five pages linked by a nav bar — the strongest and most consistent finding across all three candidate audits, and independently confirmed here.

**The one place this model is asymmetric, which none of the three audits treat as a modeling question:** the loop above is mature for exactly one domain (Technical/GDS, and within that, only one of six planned stages — "Pricing & Ticketing" — actually has a working Terminal workflow behind it; the rest are locked or pre-labeled "mastered" with no assessment record backing that status — see §10). A second domain, Customer Service, is present as a navigational *choice* (the Progression track selector), a *scoring dimension* (the `DE-ESC` skill row), and a *scenario flavor* (one scenario of five), but has no Terminal equivalent, no command vocabulary, and no assessment engine. The product's real, current shape is: **one working technical-training loop, plus scaffolding for a second competency the content layer has not built.** Any "what is AeroBridge" answer that omits this asymmetry is describing the intended product, not the actual one.

**What "success" means here, more precisely than "the trainee feels good":** the trainee can reliably reproduce the correct AN→SS→FQD→FXP sequence with few hints, evidenced by a saved record that does not silently include unscored practice activity. For the *product*, success means every visible number, status, and confirmation is true of something that actually happened — this is the product's own explicit design contract (§C.5 in Audits A/B/C; independently confirmed in `index.css`/`Home.tsx`), and it is the standard this report holds every other finding against.

---

## 4. Evidence Hierarchy

This pass applies the hierarchy below, consistent with both the Master Project Instructions and the meta-audit prompt, and resolves one non-obvious tension inside it explicitly:

| Rank | Source | Notes |
|---|---|---|
| 1 | Direct current source / literal code, read in this pass | Highest weight — but see the caveat below: two *different* "current source" artifacts exist in this project and disagree (§7). |
| 2 | Explicit product intent (`ideas.md`, Phase notes, Master Project Instructions) | Governs scope/preservation boundaries. |
| 3 | Direct visual evidence (the seven screenshots) | Confirms what actually paints; silent on anything not captured (desktop/tablet — never captured). |
| 4 | Independently re-derived analysis (recomputed contrast math, traced CSS cascades) | Present in Audit C at high quality; used here as corroboration, not as a substitute for #1–3. |
| 5 | Cross-audit agreement | Corroboration signal only. All three audits demonstrate, in their own text, cases where repeated claims across the corpus were *wrong* once the full cascade was traced (the "4-column nav" and "hidden mobile readout" claims — §7). Repetition is explicitly not elevated to fact anywhere in this report. |
| 6 | Narrative self-report of what was implemented/validated (implementation reports, "PASS" checklists, described-but-not-reproducible browser walkthroughs) | Treated as a claim to be checked against #1–3, not as evidence in itself — this is the exact class of evidence that turned out to be the least reliable in this pass (§7). |

**The caveat that matters most:** rank 1 is not a single artifact. `Claude_AeroBridge_Knowledge_Pack.md` presents itself as "current prototype source." `PHASE_2_SOURCE_MAPPING.md` presents itself as literal file:line extracts from the current source. Where these two disagree, this report treats neither as automatically authoritative — it names the conflict and downgrades confidence accordingly (§7), exactly as Rule 27/29 of the meta-audit prompt requires, rather than silently picking whichever is more convenient.

---

## 5. Audit-by-Audit Claim Arbitration

The three candidate audits converge far more than they diverge. Rather than re-litigate every row of three ~4-column decision matrices, this section arbitrates by *finding cluster* — every cluster below was independently checked against the current source in this pass, not accepted on citation count.

| Cluster | Audit A (ChatGPT) | Audit B (Manus) | Audit C (Stage 4) | This pass's arbitration |
|---|---|---|---|---|
| Empty/whitespace submit fabricates a command | AB-F01, MUST FIX, E4 | AB-01, MUST FIX, E4 | MC-001, MUST FIX, E4 | **ACCEPT the defect as real in the Knowledge Pack's bundled source; STATUS AMBIGUOUS in the live/authoritative build** — see §7. Fix scope and acceptance criteria all three propose are correct regardless of current status; treat as MUST FIX + MUST RE-VERIFY. |
| Fabricated first-use Coach error | AB-F02 | AB-02 | MC-002 | **ACCEPT as historically real** (confirmed against the actual rendered screenshot, not just source — the Coach panel's `FORMAT ERROR · CHECK ENTRY` text is visible in Image 5/7 of the shared corpus). **A fix exists in the traced source** (`PHASE_2_SOURCE_MAPPING.md`, line-level) and is plausible but has no photographic confirmation anywhere in this project. Re-verify before closing. |
| Headline counts don't reconcile (3/8, 23/40, LOG 04/12) | AB-F03 | AB-02(part)/N.2 | MC-003 | **ACCEPT, confirmed independently** against the live array lengths in the Knowledge Pack source. Extends further than any of the three state explicitly — see §10 (Level 01's "Evidence verified across recent sessions" claim with zero backing record). |
| Assessment mode-switch state bleed / static hint label | AB-F05 | (folded into AB-01 area) | MC-004 | **ACCEPT, confirmed still present in *every* source snapshot available to this pass**, including the one showing other fixes already applied. This is the one item in the whole corpus with the least ambiguity about being currently, actually broken. |
| Toast-only false affordances (Backup, "Open reference," etc.) | AB-F04 | (folds into AB-04 area) | MC-006 | **ACCEPT**, and elevate: Audit C's independent finding that no `<Toaster/>` is mounted anywhere (MC-028) means some of these controls may produce *no visible feedback at all*, which is worse than a false-success toast. Confirmed independently in this pass (`App.tsx` renders only `<Home/>`; no `<Toaster/>`, no router, no error boundary anywhere in the render tree). |
| Fonts never provisioned | AB-F08 | (implicit in provenance discussion) | MC-007 | **ACCEPT, confirmed directly** — the font `<link>` block in `index.html` sits inside a comment explicitly marked for deletion and even references the wrong family (`Inter`) if uncommented. No contradicting "fixed" evidence exists anywhere in the corpus for this one. |
| Viewport zoom disabled | AB-F09 | (implicit) | MC-008 | **ACCEPT, confirmed directly**, `maximum-scale=1` is still present. No contradicting evidence anywhere. |
| EN/AR toggle claims a switch that doesn't happen | AB-F12 | (implicit) | MC-009 | **ACCEPT as historically real; a fix exists in the traced source** (`PHASE_2_SOURCE_MAPPING.md` shows the exact honest relabel already written) but, like the Coach fix, is absent from the Knowledge Pack's bundled copy. Re-verify before closing. |
| Contrast failures (primary button, faint text) | AB-F07 | (implicit) | MC-012, independently recomputed | **ACCEPT** — Audit C's independent WCAG math is the strongest evidence in the corpus for any single finding; not disputed by A or B. |
| Missing tab/toggle/progress semantics | AB-F10 | (implicit) | MC-013–016 | **ACCEPT** — and partially already actioned: the traced source shows `role="tablist"`/`role="tab"`/`aria-selected` added to the Practice mode-tabs specifically, while the Knowledge Pack's bundled copy still lacks it. The other four tab-like groups (`growth-tabs`, `track-tabs`, `filter-tabs`, `metric-switcher`) show no evidence of the same fix anywhere — treat as still fully open. |
| Mobile input 15px override | AB-F06 | AB-11(ish) | MC-011 | **ACCEPT, confirmed still active by full cascade trace.** Two `.page-practice .terminal-input input` rules exist at equal specificity: a global one setting `16px`, and a second one inside `@media (max-width: 739px)` appearing *later* in the file, setting `15px`. Equal specificity plus later source order plus a satisfied media condition means the `15px` rule wins at every width represented in this project's screenshots. (An earlier pass of this report misread this as resolved by stopping at the first `.page-practice` override found, without checking for a second, later one — corrected here after re-tracing the full cascade, the same discipline §7.1 credits Audit C for and this report should be held to as well.) |
| Customer Service track shows Technical content under a Service label | AB-F14 / P1-8 | MD-10 | MC-021 | **ACCEPT the immediate UI fix; ELEVATE the underlying question** — see §9, §10, §11. All three treat this as a labeling bug alone; this pass treats it as a labeling bug *and* an unresolved architecture decision. |
| Preserve identity / Terminal-first / five-screen loop / reject redesign, autocomplete, gamification, MapView activation, Assessment-as-route, Growth/Tracking merge | All three, unanimous | All three, unanimous | All three, unanimous | **ACCEPT unanimously** — see §6. Independently re-confirmed against source in this pass; no contradicting evidence found anywhere. |

Where this table says "confirmed still present" or "confirmed already fixed" without qualification, that determination was made by direct grep/read against `Claude_AeroBridge_Knowledge_Pack.md` and `PHASE_2_SOURCE_MAPPING.md` in this pass, not inherited from any of the three audits.

---

## 6. Major Agreements

All three audits — and this pass, independently — agree on the following without material qualification. These are the strongest-evidenced conclusions in the entire corpus and should not be reopened absent genuinely new evidence:

- **Preserve** the Flight Deck Console visual identity (deep navy, Vector Blue, green/amber/red operational semantics, monospace command/readout typography) in its entirety.
- **Preserve** the Terminal as the dominant, full-width work surface and the architectural center of the product.
- **Preserve** Learn/Practice/Assessment as modes inside the Terminal, not as separate routes.
- **Preserve** the five-screen loop and its real, source-confirmed cross-screen context handoffs (`setPracticeContext`).
- **Preserve** Growth Record and Progress Tracking as two distinct destinations (different evidence grain: skill-level interpretation vs. session-level trend).
- **Preserve** the chart-plus-accessible-table pattern on Progress Tracking without a charting-library migration.
- **Preserve** the `prefers-reduced-motion` implementation, confirmed more thorough than a first read suggests (a global catch-all plus component-scoped refinements, explicitly covering the terminal caret).
- **Preserve** the existing "LOCAL TRAINING SIMULATION / ILLUSTRATIVE" disclosure pattern — the correct fix for undisclosed numbers elsewhere is to extend this exact pattern, not invent a new one.
- **Reject** redesign or architecture reset of any kind.
- **Reject** command autocomplete and any change to command matching or the scoring formula for presentation reasons.
- **Reject** activating the unused `MapView`/`Map.tsx` component on the strength of a "View map" label alone.
- **Reject** gamification expansion (badges, leaderboards, confetti) as a *future addition* — see §10 for why this rejection is now in tension with what already ships.
- **Reject** a default mobile Coach FAB/bottom-sheet pattern absent device evidence that the current in-flow placement actually fails.
- **The empty-command and first-use-Coach defects are the two most urgent findings in the entire corpus, treated as the top priority by all three audits independently** — which is exactly why the ambiguity about their current status (§7) matters more than any other single finding in this report.

---

## 7. Major Contradictions

### 7.1 Contradictions *inside* the three-audit corpus (already resolved by cascade tracing)

Audit C traces three claims that were repeated across multiple upstream Stage 3 audits and shown to be **wrong once the full CSS cascade was read rather than the first matching rule found**: the bottom navigation rendering as 4 columns instead of 5, the mobile session readout being "simply hidden," and the terminal caret "ignoring" reduced motion. This pass independently re-checked all three against the current CSS and confirms Audit C's rejection in every case — the earlier rules exist in the file, but later, more specific rules (one of them `!important`) override them, and the reduced-motion block uses a universal `*` selector that covers the caret without naming it. **This is the clearest demonstration in the whole project of why cross-audit repetition is not evidence** — several independently-run audits cited the identical line number and reached the identical wrong conclusion, because none of them read past the first matching rule.

### 7.2 A contradiction none of the three audits could see: the Project Knowledge disagrees with itself about whether the top P0 fixes landed

This is the most consequential finding in this report and is new to this pass.

**The claim, made in three separate places in Project Knowledge:**
- `AEROBRIDGE_IMPLEMENTATION_REPORT.md` (embedded in the Knowledge Pack) states plainly that empty/whitespace submission is now a genuine no-op with an inline `Enter a command before executing.` message, and that the first-use Coach state is now neutral, showing `READY · AWAITING COMMAND`.
- `DETERMINISTIC_VALIDATION.md` lists both as `PASS` in a 15/15 checklist.
- `Phase_3_Live_Findings.md` separately describes a live-browser walkthrough confirming the same two behaviors, plus a valid-command regression check.

**What direct source inspection in this pass actually finds**, reading the full `Home.tsx` bundled in the same Knowledge Pack that contains the three claims above:

- `submitCommand` still begins with `const nextCommand = command.trim().toUpperCase() || "FQD";`, with no guard, no early return, and no conditional rendering of any inline validation message before this line executes. A blank submission still computes to `"FQD"`, still runs through the full command-evaluation logic, and still appends to `commandHistory`.
- The Coach panel's fallback still reads `latestEntry?.response ?? "FORMAT ERROR · CHECK ENTRY"` with the accompanying hardcoded body text "The availability entry needs the airline prefix before the flight number." — and the base `.coach-block code` CSS rule colors this red by default. **This exact state is also visible directly in one of the seven supplied screenshots** (the Practice screen at 1:25/77% battery shows the fabricated red error text pixel-for-pixel), which is the same screenshot set all three candidate audits already had.

**A second, independently-traced source artifact partially corroborates the "fixed" claim.** `PHASE_2_SOURCE_MAPPING.md`, which presents itself as literal `file:line` extracts from the current source, shows a *different*, already-fixed version of the Coach fallback (`"coach-code--neutral"` styling, `"READY · AWAITING COMMAND"` text, `"Submit a command when you are ready. No evidence is recorded until you act."` body) — matching the Implementation Report's claim exactly. The same file also shows a fixed, honest version of the EN/AR language toggle (relabeled `aria-label`, an honest "roadmap only" toast in place of the false "Interface language set to…" message) and shows `role="tablist"`/`role="tab"`/`aria-selected` added to the Practice mode-tabs — none of which appear in the Knowledge Pack's bundled full source.

**What this pass does *not* find anywhere in the corpus:** a literal source-line excerpt confirming the empty-submit *guard clause* specifically exists. Every piece of evidence for that one specific fix is narrative (the Implementation Report's prose, the validation checklist's PASS row, the live-findings description) rather than a traced code citation like the Coach and language-toggle fixes have.

**Resolution applied in this report, per the evidence hierarchy in §4:**

| Item | Verdict | Confidence | Basis |
|---|---|---|---|
| Coach first-use fallback | **Likely genuinely fixed in the authoritative build; the Knowledge Pack's bundled copy is a stale pre-fix snapshot** | Medium-High | Direct traced-source citation (`PHASE_2_SOURCE_MAPPING.md`) + narrative corroboration (Phase 3). No photographic confirmation of the *fixed* state exists anywhere, only of the buggy state. |
| EN/AR toggle honesty | **Likely genuinely fixed; same staleness explanation** | Medium-High | Same pattern — direct traced-source citation exists. |
| Mode-tab ARIA semantics (Practice only) | **Likely genuinely fixed for this one control group; the other four tab-like groups show no such evidence** | Medium | Direct traced-source citation for this one instance only. |
| Empty-submit guard | **UNRESOLVED — do not assume either way** | Low | Only narrative evidence for the fix; the one full source copy available shows the pre-fix code with no ambiguity. This is the single most-cited P0 defect in the entire three-audit corpus; it must be re-verified directly against the live build before it is treated as closed *or* reopened. |
| Assessment "No hints" static label (MC-004) | **Confirmed still broken, in every source snapshot available, including the ones that show other fixes applied** | High | This is the one item where the "fixed" and "unfixed" source artifacts agree with each other — both still show `{sessionComplete ? "Report ready" : "No hints"}`, unconnected to real `hintCount`. |

**Why this belongs above every other finding in this report:** none of the three candidate audits could have caught this, because all three were built from an earlier evidence package (the five Stage-3 audits plus the same seven screenshots) that predates the Phase 1–3 process notes and the Knowledge Pack entirely. It is not a criticism of any of the three audits. It is a corpus-integrity failure of exactly the kind the project's own Arabic-language governance plan warns about (§3, "Corpus Integrity Check" — *"if a file is incomplete, duplicated, or unreadable, stop analysis and fix the corpus first"*) and the kind the Master Project Instructions' §8 (AI Loop / Process Records) warns about directly: *"do not represent manual validation as an external model verdict... a missing model result must remain a missing model result."* A "PASS" in a checklist is not evidence once a contradicting source artifact exists in the same package — and here, one does.

---

## 8. Rejected Recommendations

Consolidated across all three audits' explicit rejection lists (RJ-01 through RJ-20 in Audit A, RJ-01 through RJ-09 in Audit B, the equivalent list in Audit C), with unanimous agreement in every case checked. This pass adds no new rejections beyond what is implied by §10's honesty principle (the streak/readiness widgets are not "rejected" — they already exist and must be resolved, not merely kept off a future roadmap).

| Rejected | Why | Would only be revisited if |
|---|---|---|
| Redesign / re-theme into generic SaaS or LMS styling | Destroys the product's strongest differentiated asset; contradicts explicit reference-preservation intent | Never, absent a full product-direction change |
| Assessment as a separate top-level route | Fragments Terminal continuity (history, hints, Focus Mode) across a navigation boundary for no evidenced benefit; the actual Assessment problem (MC-004) is a state-isolation bug a new route would not even fix | Never on current evidence |
| Merging Growth Record and Progress Tracking | They read different evidence grains (skill-level vs. session-level); product intent names them as distinct loop stages | Only if future task research shows trainees cannot locate evidence under the current split |
| Command autocomplete | Conflicts with recall-based training pedagogy | Only with an explicit pedagogical-model change |
| Engine Pause/Resume or other invented processing/interrupted states | The command evaluator is synchronous; there is nothing to pause. Inventing UI for a state with no real trigger is the exact defect this whole report exists to correct, applied to itself | Only if a real async engine is built |
| Gamification **expansion** (new badges, leaderboards, confetti) | Contradicts the product's professional-console positioning; unsupported by any learning-outcome evidence | Not applicable — see §10 for what already exists and must be resolved instead |
| Activating `MapView`/`Map.tsx` | An unused, unimported component and a "View map" label are evidence of prior scaffolding, not of product need | Only if a curriculum owner defines a map-dependent task |
| Chart-library migration (e.g., to Recharts) | The existing chart-plus-table pattern already meets the accessibility need it would solve | Only if a genuinely new interaction requirement emerges |
| A global persistent "Next Action" widget | Existing contextual CTAs already perform this job; a global widget risks dashboardization | Only if task research proves the current contextual pattern fails |
| A default mobile Coach FAB/bottom-sheet | No evidence the current in-flow, subordinate placement is missed or obstructive | Only after native-keyboard device testing shows a real problem |
| Expanding Customer Service curriculum inside this hardening revision | Curriculum authority/content ownership is outside this audit's scope | Only once a content owner commits real Service curriculum (§9, §11) |
| Treating the 4-column nav / hidden readout / caret-ignores-motion claims as current defects | Refuted by full-cascade tracing, independently reproduced in this pass | Never — these are resolved, not deferred |

---

## 9. Unresolved Questions

Every product-owner decision below is genuinely unresolved by any evidence in this project — not because no one looked, but because the answer depends on information (curriculum plans, hosting/deployment intent, definitions of "readiness") that does not exist in any supplied artifact. This pass does not force an answer to any of them; it states what depends on each.

| ID | Question | What depends on it | New in this pass? |
|---|---|---|---|
| Q1 | **Which build is actually live right now** — does the deployed preview behave like the Knowledge Pack's bundled source, or like the fixes traced in Phase 2/3? | Whether roughly six items (§7) are still open work or already-closed items needing only a regression test | **Yes — new** |
| Q2 | Is Customer Service intended to become a real, equally-built second competency track, or is it intentionally a minor scenario flavor that should be de-scoped from the track selector entirely? | Whether MC-021's honest-empty-state is the *whole* fix, or an interim step before a real curriculum build; whether `DE-ESC` belongs in the core skill model at all | **Reframed — the labeling question is old, the architecture question is new (§10, §11)** |
| Q3 | Are `8` stages / `40` scenarios / `12` log entries / `210` commands genuine planned future totals, or should displayed totals simply match the `6`/`5`/`3` actually built? | Whether the count-reconciliation fix (§5) is a pure derivation correction or should retain a larger number with an explicit "N available now / M planned" qualifier | Carried from all three audits |
| Q4 | Should "Backup" become a real local export (e.g., a JSON download of the `localStorage` record), or be permanently relabeled as unavailable? | The cost and shape of one specific false-affordance fix | Carried from Audit C |
| Q5 | Is Arabic/RTL in near-term release scope, or does the product remain EN-only for the foreseeable future? | Whether the interim toggle-honesty fix is the whole fix or a placeholder before a real i18n program | Carried from all three audits |
| Q6 | Should Learn/Practice/Assessment modes fully isolate history and hints on switch, or remain continuous with honest disclosure of carried-over activity? | The permanent design of MC-004's fix, beyond the interim disclosure | Carried from all three audits |
| Q7 | What does "Saudi readiness" actually measure, and does the same question apply to the sidebar "streak" widget's "10-day target"? | Whether either can remain in any form, or must be removed pending a real definition | **Extended in this pass to include the streak widget — see §10** |
| Q8 | Is `Map.tsx` a planned future feature or pure dead code to be removed? | MC-029's disposition | Carried from Audit C |
| Q9 | Does the real-world Amadeus/GDS command `FXP` actually correspond to what this product's `FXP` teaches (a first-time itinerary price quote), or does it more properly correspond to fare-exchange/reissue pricing in real GDS usage — and if so, is the current mapping an intentional simplification or an unreviewed accuracy gap? | Domain-realism risk (§14) — this is a training product; a wrong command-to-meaning mapping teaches an incorrect procedural habit, which is the single worst failure mode available to this kind of product | **New in this pass — flagged, not asserted (this pass's own domain knowledge of the exact real-world FXP usage is not fully certain and should not be treated as settled without a GDS subject-matter reviewer)** |

---

## 10. New Blind Spots All Three Audits Missed

Each item below was checked directly against the current source in this pass. None is a restatement of an existing audit finding — each is either evidence none of the three had access to, or a question none of the three asked of evidence they did have.

### 10.1 The corpus-integrity gap (§7.2)

Already covered in full above; listed here because it is, by a wide margin, the most consequential new finding in this report. **Severity: Critical. Blocks: nothing in the P0 UI work itself, but blocks treating any "already fixed" claim in this project as settled until Q1 is answered.**

### 10.2 Customer Service is an architecture question wearing a bug's clothes

All three audits (MC-021, AB-F14/P1-8, MD-10) correctly identify that selecting the "Customer Service" track shows Technical-track content under a Service label, and correctly classify the interim fix as an honest empty state. What none of them examine is *why* the product already behaves as if a second competency domain is real, in three separate places that were each built independently:

- The Progression screen's track selector (`"technical" | "service"`) — a navigational choice.
- The Scenarios list's `category` field, where one of five seeded scenarios ("Difficult customer at the airport," `SC-026`) is explicitly `"Customer Service"`, tagged with `De-escalation`, `English`, `Recovery` — a content classification.
- The Growth Record's `skillRows` array, where `DE-ESC` (`De-escalation`) is scored, trended, and displayed with exactly the same visual weight as `AN`/`SS`/`FQD`/`FXP`, and currently sits inside the "Needs attention" panel alongside two Technical-track skills — an **evaluation** claim.

That third one is the important one. A skill row in Growth Record is not cosmetic — it is the product asserting, to the learner, that de-escalation competency is being measured and tracked exactly as rigorously as command accuracy. But there is no Terminal-equivalent practice surface, no command vocabulary, and no assessment engine anywhere in the source that could actually produce a real `DE-ESC` score. **The competency model has already committed, at the data layer, to AeroBridge being a two-domain (technical + service) readiness product. The content and simulation layers have not.** This is a materially different problem from "the track toggle needs an honest empty state" — it is a question of whether the product's own evaluation surface is currently making an assessment claim it cannot back up, which is precisely the trust-integrity category every MUST FIX item in this corpus already belongs to, just not yet named for this specific instance.

**Recommendation:** treat this as a §24/§27 decision, not a §5 bug fix. Either (a) commit to building a real Customer Service practice+assessment mechanism eventually and, in the interim, remove `DE-ESC` from the scored skill model (or clearly separate it as "not yet assessed") so the Growth Record does not claim a measurement it cannot produce, or (b) formally scope Customer Service down to a scenario-flavor label only and remove the track selector and the `DE-ESC` skill row entirely. Both are legitimate answers; leaving the current partial state unresolved is not.

### 10.3 A desktop-only, un-screenshotted region of the product contains exactly the pattern every audit rejects for the future — because it already ships

Every one of the seven supplied screenshots is a mobile capture. The desktop-only side navigation (`.side-nav`, gated behind `@media (min-width: 1100px)`) has therefore never been visually inspected by any of the three candidate audits, or by the person assembling the evidence packages that fed them. Reading the source directly, that side navigation contains two widgets with no equivalent anywhere in the mobile experience:

- `"Saudi readiness" — Evidence path · 24%` — a hardcoded literal, not computed from any array, record, or session state anywhere in the source.
- `"Current streak: 7 days"`, a filled progress track at a hardcoded 70%, captioned `"7 of 10-day target."` — also a hardcoded literal with no backing computation.

All three audits' explicit rejection lists include, near-verbatim across all three: *reject adding gamification — badges, streaks, leaderboards, confetti — because it contradicts the professional console identity and is unsupported by evidence.* That rejection is correct. **It is also already moot for the streak counter specifically, because a fabricated streak-with-a-target-and-a-progress-bar is not a proposal on a roadmap — it is live in the current source, sitting directly beside an equally unexplained "readiness" percentage, in the one region of the UI that has never been in front of an evidence-gathering screenshot.** This was not a synthesis failure by any of the three audits — it was a genuine coverage gap in the underlying evidence package they were given, and it is worth naming explicitly, because it means the mobile-only screenshot set has a structural blind spot: anything desktop-exclusive has effectively never been reviewed by this entire audit lineage, not just this one widget.

**Recommendation:** fold both widgets into the same provenance/honesty sweep as MC-003/MC-005 (§5, §24) — either derive real values from actual session/assessment history, or remove them, or label them explicitly as illustrative. Do not treat the streak counter as a smaller problem than the headline `3/8` count merely because it was never photographed; the underlying defect (a fabricated number presented with full evidentiary authority) is identical.

### 10.4 The honesty pattern extends one level further than any audit's table currently states

MC-003/AB-F03 correctly catch the `3/8` stage count against the six-item `levels` array. What none of the three audits' tables name specifically: **Level 01 ("Sign-in & Encode / Decode") is hardcoded `state: "mastered", progress: 100`, and clicking its expanded state renders the copy "Evidence verified across recent sessions" — while zero records anywhere in `seedProgress` correspond to that stage.** (Level 02, "Availability & Sell," at least has a matching seed record — `EV-038`, 84%, passed — so it is not part of this finding.) This is the same class of defect as the headline counts, one layer deeper: a specific, first-person evidentiary claim ("verified") attached to a stage with no evidence behind it at all. It should be corrected in the same pass as MC-003, using the same derivation-or-honest-label principle, not treated as a separate initiative.

### 10.5 If the Toaster genuinely isn't mounted, roughly a dozen "SHOULD FIX" triage decisions in this corpus need re-scoping, not just relabeling

Audit C's MC-028 (confirmed independently in this pass: `App.tsx` renders only `<Home/>`, with no `<Router>`, `<ErrorBoundary>`, or `<Toaster/>` anywhere in the tree) is the correct catch, but its consequence is under-weighted even in Audit C's own tiering. If no `<Toaster/>` is mounted, then every one of the ~19 `toast.*()` calls across the twelve-plus controls flagged in MC-006/AB-F04 may render **nothing visible at all** on click, not a misleading-but-visible success message. That is a worse failure mode than the one every existing MUST FIX/SHOULD FIX classification assumes (a toast that lies vs. a control that appears to do literally nothing). This does not change *what* needs fixing, but it changes the order: mounting a real `<Toaster/>` (§24, M7) must happen **before**, not alongside, the false-affordance triage in MC-006 — otherwise that triage is being performed against an unknown actual behavior.

### 10.6 Domain-terminology accuracy is almost entirely unexamined by all three audits

Across roughly 3,700 lines of combined audit text, virtually none of it evaluates whether `AN`/`SS`/`FQD`/`FXP` map correctly onto real Amadeus/GDS command semantics — the audits are near-exclusively UI/UX/accessibility focused. `AN` (Availability) and `SS` (Sell Segment) are standard, uncontroversial GDS shorthand. `FQD` (Fare Quote Display) is also standard. `FXP`, as used in this product, is presented as a general first-time price-quote command — but in real-world Amadeus usage, `FXP`-family entries more typically apply to fare **exchange/reissue** pricing rather than an initial itinerary quote. **This pass is not certain enough of the precise real-world scope of `FXP` to assert it as a confirmed error**, and states that uncertainty explicitly rather than manufacturing false confidence — but flags it because this is a training product whose entire value proposition is that its command vocabulary is trustworthy, and a wrong command-to-meaning mapping is the domain-specific equivalent of everything else in this report: a false claim of correctness. **Recommendation:** a one-time GDS subject-matter review of the four-command vocabulary, cheap relative to its risk, before any additional curriculum content is authored on top of it (§14, §25).

---

## 11. Product Strategy Verdict

**The smallest product that delivers AeroBridge's core transformation without destroying its identity is what already exists today, with the trust layer repaired:** one real, working Technical-track workflow (Pricing & Ticketing) taught through a credible terminal, evaluated honestly, and reflected in two distinct evidence surfaces. Everything else currently visible — the other five Technical stages, the Customer Service track, the larger scenario library — is either locked, seeded, or a scaffold. That is not a criticism; a single, honestly-evaluated workflow that a learner can trust is a stronger MVP than five superficially-present but hollow ones.

**The one live strategic fork is Customer Service (§10.2).** This is not a UX question — it is a positioning question: does AeroBridge differentiate as a *technical* GDS-command trainer, or as a *readiness* trainer spanning technical and interpersonal service skills? The product's own persistence layer has quietly already voted for the second answer (the `DE-ESC` skill row) without the content layer, the practice mechanism, or a product decision backing it up. This should be resolved explicitly and soon — not because the current state is broken in a way that blocks release, but because every week it stays unresolved is a week the Growth Record keeps making an evaluation claim (`DE-ESC` scoring) the product cannot actually support.

**Unnecessary capability, confirmed absent and correctly absent:** no backend, no accounts, no live carrier integration, no PWA layer (§17), no gamification beyond the two hardcoded widgets flagged in §10.3, which should be resolved rather than expanded. The product is correctly scoped as a client-side, local-evidence prototype, and every audit's rejection list (§8) protects that scoping correctly.

## 12. User / Persona Verdict

The evidenced persona is a single, entry-to-intermediate learner preparing for a reservations/ticketing role, with an explicit Saudi-market lean (the "Saudi readiness" widget, the Arabic-toggle affordance, the `lang="en"` document that never actually changes even when the toggle is used, the persona name). Nothing in the source or content evidences a distinct advanced or job-seeking-specific persona track today — the vocabulary is uniformly basic (one four-command workflow), so **the product should not be evaluated as if it already serves both a beginner and an advanced audience; it currently serves one, and building for an "advanced" persona ahead of finishing the beginner path (which itself has five of six stages unbuilt) would be premature.**

For this persona, the trust-integrity fixes in §5/§24 matter more than any visual change: a learner deciding whether to trust a training tool with their actual job preparation is more sensitive to a fabricated error message or an unearned "ready" claim than to spacing or contrast — though the contrast fixes are real accessibility requirements independent of that argument and should proceed regardless.

## 13. Learning-System Verdict

**What a learner should reliably be able to do after using AeroBridge, based only on what is actually built:** correctly recall and sequence a four-command Amadeus-style pricing-and-ticketing workflow (`AN → SS → FQD → FXP`) under evaluation, with an accurate account of their own accuracy, sequencing, and hint reliance. That is a real, narrow, achievable competency claim — and it is the *only* one the current build supports; claims broader than this (general "reservations agent readiness," "Saudi readiness") are not yet backed by content.

**Genuine strengths, independently confirmed:** the rejection of autocomplete correctly protects recall-based practice; the Learn → Practice → Assessment structure is a real, escalating-stakes pedagogical sequence, not three re-skins of the same screen; the Coach's per-response guidance is genuinely tied to the specific error kind (`syntax`/`sequence`/`decision`), not generic.

**Genuine weaknesses beyond what any audit tables as a discrete item:** the Assessment mode-switch state bleed (MC-004) does not just create a UI-honesty problem — it threatens the *validity* of the one score this product exists to produce, since Learn/Practice activity (including hint usage) can silently count toward an Assessment result while the UI claims "No hints." A training product's single most important promise is that its evaluation means what it says; this bug sits directly on that promise. Fix it before any content expansion, not after — expanding curriculum on top of an assessment engine with an unresolved isolation question compounds the risk rather than working around it.

**Transfer to real work:** reasonable to claim for the one built workflow; entirely unevidenced for anything else, including Customer Service (§10.2).

## 14. Aviation / Domain Verdict

`AN` (Availability) and `SS` (Sell Segment) match standard GDS shorthand and are not in question. `FQD` (Fare Quote Display) likewise. **`FXP`, as currently taught (a general first-time price-quote step), is the one command in the vocabulary this pass cannot confirm is domain-accurate** — real-world Amadeus usage of `FXP`-family entries more typically applies to fare exchange/reissue pricing rather than an initial quote (§10.6, Q9). This is stated as a flag requiring a subject-matter reviewer, not as a confirmed defect — inventing domain certainty here would violate the same evidence discipline this report holds every other claim to.

**Known domain simplification, correctly disclosed:** a single always-available flight/fare set with no live-inventory variability. This is an acceptable, clearly-labeled abstraction ("LOCAL TRAINING SIMULATION") appropriate for a foundational learner and should not be built out into fake variability merely for realism's sake.

**One inconsistency worth an explicit decision rather than silent tolerance:** command-sequence order is enforced in Assessment mode but not in Learn or Practice. This is defensible as a deliberate instructional-design choice (free exploration while learning, strict evaluation only when it counts) — but nothing in the product states this is deliberate, so it currently reads as inconsistent rather than intentional. Make the choice explicit in Coach/Reference copy once decided (Q6-adjacent).

## 15. Simulation / Practice Verdict

**What must be realistic:** the command syntax and the sequential dependency logic between the four commands — both are already correctly modeled. **What can be abstracted:** network latency and processing delay — correctly abstracted today (the response is synchronous), and MC-032 correctly recommends against adding a fake delay purely for realism. **What must never be falsely represented:** evaluation state. This is exactly where the two P0 defects at the center of this entire report live (a fabricated command event, a fabricated error), which is why they outrank every cosmetic finding in this corpus, not merely because three audits happened to notice them first.

## 16. UX Verdict

Cognitive load is appropriately scoped for the taught vocabulary (four commands, one workflow). Navigation is coherent and the five-item structure is correctly defended by all three audits against the stale "4-column" claim (§7.1). Audit C's canonical state matrix (its §I.3) is the strongest single UX artifact in the corpus — it correctly separates *states with a real trigger* from *states that would have to be invented* (processing, interrupted), and should be adopted as-is as the shared state contract for implementation, rather than re-derived. This report's only addition to it is the disposition already captured in §5/§7 for the first-use and empty-input rows specifically.

**Fullscreen (Focus Mode), checked directly against source:** genuinely meets the "dominant experience" bar — `task-strip`, `mode-tabs`, and the entire Coach panel are hidden (`display: none`) rather than merely shrunk, the terminal panel expands to fill the viewport height, and the exit control remains reachable throughout. This is real, working immersion, not a cosmetic enlargement, and needs no P0/P1 attention beyond whatever the shared accessibility pass in §30 already covers for its exit control.

**Typography, beyond the font-loading and contrast findings already in §5/§24:** hierarchy and line-height choices in the source are deliberate and legible (a distinct monospace channel for terminal/command content, a display face for headings, generous line-height in the terminal body) — the open items are entirely the ones already tracked elsewhere in this report (unprovisioned fonts, contrast, the mobile input floor), not a separate hierarchy problem.

## 17. Mobile / PWA Verdict

**Mobile is unambiguously the primary, evidenced device class** — one hundred percent of the seven screenshots across the entire audit lineage are mobile captures, and the source shows deliberate mobile engineering (sticky safe-area input handling, a 16px-floor intent, breakpoint-specific density rules). This matches the Master Project Instructions' explicit mandate that mobile be first-class, not a shrunken desktop layout, and the evidence supports treating it that way.

**PWA capability is confirmed entirely absent** — no `manifest.json`, no service-worker registration, no install-prompt handling anywhere in the source. This is correct for the current stage: the project's own governing plan explicitly states PWA should remain gated behind demonstrated need rather than built preemptively, and nothing in the current evidence demonstrates that need yet. **Do not build PWA capability in this pass.** The one thing worth confirming (not fixing) is that current architectural choices are not *accidentally* closing the door on it later — nothing found in this review suggests they are; the state model is already React-state-plus-`localStorage`, which is compatible with an eventual service-worker/caching layer without rearchitecting.

## 18. Technical / Architecture Verdict

Everything user-facing is client-side: React state plus `localStorage`, no live backend logic observed anywhere in the evidence. A `server/index.ts` file is referenced in the build script but its contents are not included in any evidence available to this pass — **this pass explicitly does not know what it does, and does not assume it is more than a static-asset server for the hosting environment,** consistent with the product's own "local/illustrative" framing and the Master Project Instructions' explicit prohibition on inventing backend capability. If this needs to be resolved with certainty, it requires a direct read of that file, not an inference from this evidence.

Decisions that should be made *before* any further UI implementation beyond the P0/P1 scope in §24: whether Customer Service becomes real (architectural implications for the content/assessment layers, §19); whether `Map.tsx` is retained on a roadmap or removed (low cost either way, but it should be a decision, not indefinite limbo). Nothing found in this pass requires new backend, new persistence architecture, or new routing to complete the P0/P1 scope.

## 19. Content / Knowledge Architecture Verdict

All current content — stage definitions, scenario objects, skill rows, seed assessment records — lives as hardcoded TypeScript literals directly inside `Home.tsx`. This is a reasonable, low-overhead choice at the current content scale (six stage entries, five scenarios, five skill rows) and should not be re-architected purely for elegance (Master Project Instructions §20: "never create abstractions solely because they are elegant"). **It stops being reasonable the moment either Customer Service content or additional Technical stages actually get built** — hardcoded literals inside a page component do not scale past the current content volume without becoming an editing hazard. Recommendation: if and when Q2 (§9) resolves toward building real Customer Service content, extract stage/scenario/skill definitions into structured data (even a plain typed JSON/TS module separate from the component) *before* authoring that content, not after. Do not do this extraction now, for content that does not yet exist — that would be exactly the kind of premature abstraction the same governing principle warns against.

## 20. Assessment / Competency Verdict

The scoring formula (`accuracy × 0.5 + sequencing × 0.35 + hint-score × 0.15`) is deterministic, transparent in its own debrief screen, and not in question by any of the three audits or this pass — **do not change it to solve a presentation problem**, per unanimous agreement. The real competency-model gaps are the ones already covered: the mode-isolation ambiguity threatening score validity (§13), the static hint-count label (confirmed broken, §5/§7), and `DE-ESC`'s presence in the skill model without a supporting assessment mechanism (§10.2). All three should be resolved as part of the same P0/P1 pass, not treated as a separate initiative — they are one coherent "does the score mean what it says" problem, not three unrelated bugs.

## 21. Analytics / Telemetry Verdict

No real event analytics currently exist beyond an Umami script whose reachability outside the current hosting preview is unconfirmed (MC-031, independently corroborated — no evidence in this pass contradicts it). **If instrumentation is added later, the minimum high-value set is:** completion funnel by mode (Learn/Practice/Assessment), hint-open frequency by workflow step, and repeated-error command/step pairs — all directly tied to the actual learning loop. **Avoid vanity metrics** — the existing "Saudi readiness" and "streak" widgets (§10.3) are the cautionary example already living in the product: numbers that look like telemetry but are not connected to anything real. Any future instrumentation should be held to the same derive-or-label standard as every other number in this report.

## 22. Security / Trust / Accessibility / Internationalization Verdict

No authentication, no backend, and no real personal data beyond a hardcoded display name — the security surface is minimal and appropriately so for a client-only prototype; nothing in this pass identifies a new security risk beyond what §18 already covers. **Accessibility** is the area with the most concrete, already well-evidenced work (Audit C's MC-013 through MC-019 cluster, independently confirmed present as gaps in this pass): missing tab/toggle/progress semantics across five control groups, no landmark/skip-link, no confirmed overlay focus-trap. All are additive fixes that do not touch visual identity, and this report endorses Audit C's specifications for them without modification. **Internationalization** is confirmed non-functional beyond a label toggle: the `<html lang="en">` attribute never changes even when the toggle is used, `--font-ar` is defined but never applied, and no translation lookup exists anywhere. The unanimous "interim honesty fix now, full RTL only with an explicit scope decision" position from all three audits is correct and this pass adds no new consideration beyond §7's note that the interim fix appears to already exist in one traced source artifact and should be re-verified, not re-built from scratch.

## 23. Business / Career / Job-Readiness Verdict

Three distinct kinds of value are currently conflated in the product's own language and should be kept separate going forward: **learning value** (real, for the one built workflow — a learner genuinely practices something), **credential value** (currently near-zero — no rubric, no external authority, no validation body stands behind any score), and **employability value** (currently unsupported — an employer has no way to interpret "Operationally ready" or "Saudi readiness 24%" as meaning anything specific). None of the three audits frame it this way, but all three arrive at the same practical conclusion via MC-010/AB-F13/MD-14: readiness and certification-adjacent language must be scoped to what a local heuristic can actually support. This pass's addition is the framing itself — keep these three value types explicitly distinct in any future copy or marketing decision, because collapsing them is exactly the kind of overclaim this entire report exists to prevent.

---

## 24. Scope Decision: MUST / SHOULD / COULD / DEFER / REJECT

### MUST (P0 — blocks a "trustworthy" verdict; none touch the command engine, scoring formula, or route structure)

| ID | Change | Source |
|---|---|---|
| M0 | **Reconcile the corpus.** Re-verify the empty-submit guard, Coach neutral-state, EN/AR toggle honesty, and mode-tab ARIA semantics directly against the live/authoritative build before treating any of them as closed or open. Update whichever artifact (Knowledge Pack vs. Phase 2/3 notes) is stale. | New (§7) |
| M1 | Guard blank/whitespace command submission as a true no-op | All three audits |
| M2 | Neutral first-use Coach state; error styling only after a real failed command | All three audits |
| M3 | Reconcile every headline count (`3/8`, `23/40`, `LOG 04/12`, `128/210`) with real data, or explicitly label illustrative/future — **including Level 01's unbacked "Evidence verified across recent sessions" claim** | All three audits + extended (§10.4) |
| M4 | Fix Assessment mode-switch state bleed; make the "No hints" label derive from real `hintCount` — confirmed still broken in every source snapshot available | All three audits |
| M5 | Neutralize fresh-session seeded metrics (86% accuracy, 4:32 timer, 68% task progress) shown before any command | Audit C |
| M6 | False-affordance sweep on every toast-only control, Coach's "Open reference" and "Backup" first | All three audits |
| M7 | Mount a real `<Toaster/>` and a styled `ErrorBoundary` — sequence **before** M6's final triage, since M6 cannot be scoped accurately until toast rendering is confirmed | Audit C, sequencing new to this pass (§10.5) |
| M8 | Provision the three declared fonts or re-token to the actually-shipped stack | All three audits |
| M9 | Remove `maximum-scale=1` | All three audits |
| M10 | Stop the AR toggle claiming a completed switch (interim relabel/disable) | All three audits |
| M11 | Resolve the "Saudi readiness" and sidebar "streak" widgets — derive, remove, or explicitly label illustrative | Audits (readiness) + new (streak widget, §10.3) |
| M12 | Fix primary-button and `--text-faint` contrast to ≥4.5:1 | Audit C, independently recomputed |
| M13 | Remove the mobile-scoped `15px` override on `.page-practice .terminal-input input` — confirmed still active by full cascade trace, not resolved by the later token layer | All three audits, re-confirmed by full cascade trace (§5) |
| M14 | **Decide** whether Customer Service becomes a real second competency track; ship the honest interim empty state either way; if "not now," remove `DE-ESC` from the scored skill model or clearly mark it unassessed | All three audits (empty state) + new decision framing (§10.2, §11) |

### SHOULD (P1 — real, additive, none blocking)

Systemic tab/toggle/progress/landmark/focus-trap semantics pass across all five control groups (only one — Practice's mode-tabs — shows any evidence of already being partially fixed); skill-trend icon/color favorability correction; mobile skill-hover-preview parity below 740px; `--ab-*` token-layer consolidation; Scenarios' Filters/Sort fix; mobile nav breadcrumb/tap-order reconciliation; Terminal fixed-gap reduction; a GDS subject-matter review of the four-command vocabulary, `FXP` specifically (§10.6, §14) — cheap, parallelizable, should complete before new curriculum content is authored on top of the current vocabulary; the full native-keyboard/tablet/desktop/screen-reader validation matrix, since zero non-mobile evidence exists anywhere in this project's history.

### COULD (P2 — team discretion, none block this revision)

Per-command toast reduction in favor of Terminal-history-owned feedback; touch-target sizing toward 44×44 where layout allows; remove or wire the unreachable "hint-dependency" taxonomy entry; document `Map.tsx` as intentionally out of loop; document hosted-asset and analytics host-coupling for handoff; optional cosmetic processing-delay for realism; simplify decorative Progress Tracking KPI ornamentation.

### DEFER (real questions, not yet answerable from evidence — see §9)

Full Arabic/RTL build; whether `8`/`40`/`12`/`210` become real future totals vs. corrected-to-match-content; whether Backup becomes a real local export; whether `Map.tsx` is finished or removed; **the actual content build for Customer Service** (the decision in M14 is P0; the curriculum itself is not); tablet/desktop-specific layout decisions pending the validation matrix; a mobile Coach FAB/drawer pattern, pending real device evidence the current placement fails.

### REJECT

Redesign/re-theme; Growth/Tracking merge; Assessment as a separate route; command autocomplete or scoring-formula changes for presentation reasons; speculative `MapView` activation; **gamification expansion** (new badges/leaderboards/confetti) — while simultaneously requiring M11 to resolve what already exists, since "reject adding more" and "leave the fabricated streak counter alone" are not the same position; chart-library migration without a new requirement; a global persistent "Next Action" widget; treating the 4-column-nav/hidden-readout/caret-reduced-motion claims as current defects (refuted by cascade tracing, §7.1); expanding Customer Service curriculum inside this hardening pass specifically (the decision is P0; the content is not, per M14).

---

## 25. Dependency Graph

- **M0 (corpus reconciliation) gates accurate scoping of M1, M2, and M10** — nothing else in the P0 tier depends on it, but the *reported status* of these three is unreliable until it runs. M13 does not depend on M0: full cascade tracing in this pass already confirms it independently of which build is authoritative (§5), so it can proceed immediately alongside the unambiguous items below.
- **M7 (mount Toaster) must precede the final triage inside M6** — you cannot correctly classify "does this control lie about success" until you know whether its confirmation is even visible.
- **M8 (fonts) should sequence early within P0**, since font provisioning changes rendered text metrics and can shift wrapping, contrast measurement context, and touch-target boundaries — re-measure M12's contrast and any P1 touch-target work *after* M8, not before.
- **M14's decision half (P0) must precede any Customer Service content work (DEFER)** — the decision is cheap and fast; committing curriculum effort before it exists is the risk this graph exists to prevent. The interim honest-empty-state UI fix inside M14 has no dependency and can ship immediately regardless of when the decision lands.
- **The SHOULD-tier tab/toggle/ARIA pass should be built once as a shared pattern and applied to all five groups together**, not as five independent one-off fixes — Practice's mode-tabs already show a partial version of this pattern in the traced source (§7), so that one instance should inform the shared pattern rather than being redone from scratch.
- **The domain-terminology review (SHOULD) is independent of everything else and should run in parallel** — but should complete before any new curriculum content (Customer Service or additional Technical stages) is authored, so new content does not inherit a possibly-incorrect vocabulary baseline.
- **The full validation matrix (native keyboard, tablet, desktop, screen reader) can run in parallel with P0/P1 implementation**, but gates any "production reference" label — no item in P0/P1 depends on it to proceed.

---

## 26. Risk Register

| ID | Risk | Probability | Impact | Mitigation |
|---|---|---|---|---|
| R1 | Corpus/process drift recurs — a future fix gets bundled into a "current source" artifact that is itself stale, and the cycle repeats | Medium | High — erodes trust in the entire audit pipeline, not just one screen | Single reconciled source of truth per revision; re-verify PASS claims against the live build, not against a bundled snapshot, before closing any item (M0 as a standing practice, not a one-time task) |
| R2 | `FXP`'s real-world domain mapping is actually wrong, and learners internalize an incorrect procedural habit | Low–Medium (uncertain) | High — this is a training product; a wrong command-to-meaning mapping is its worst possible failure mode | GDS subject-matter review before further curriculum investment (§14, §25) |
| R3 | Customer Service remains permanently thin/decorative while the product's own positioning (Saudi readiness, employability framing) implies it matters | Medium | Medium-High | Force the M14 decision now rather than letting default inertia answer it |
| R4 | If the Toaster genuinely is unmounted, several "SHOULD FIX"-tier controls are silently producing zero visible feedback, a worse defect than currently classified | Medium (confirmed absent mount point; unconfirmed actual runtime consequence) | High for the affected controls specifically | M7 before M6's final triage (§10.5, §25) |
| R5 | An entire device class (desktop/tablet) has never been visually validated by any audit in this project's history, and the two fabricated sidebar widgets (§10.3) show that "never screenshotted" already hid a real defect once | Confirmed present | High | Full validation matrix (§24 SHOULD); explicitly do not assume desktop parity from mobile evidence anywhere else in the product either |
| R6 | Readiness/certification-adjacent language is relied upon by a real learner or employer as more authoritative than a local heuristic | Medium | High — career-consequence stakes | M11 + an explicit non-certification disclaimer alongside any readiness-style metric |
| R7 | Historical assessment records already in `seedProgress`/`localStorage` may already reflect the M4 state-bleed bug, meaning some of the evidence Growth/Tracking currently present may itself be tainted | Medium | Medium — affects trust in data already being shown as evidence, not just future data | Fix M4 first; consider whether existing records need a "may predate this fix" disclosure rather than being presented with the same confidence as future ones |

---

## 27. Decision Register

Consolidated from §9, with this pass's added items marked. Each entry states a recommendation *for whom to decide and by when*, not a unilateral answer this report is not positioned to give.

| ID | Decision needed | Recommended interim position | Owner |
|---|---|---|---|
| Q1 | Which build is currently live/authoritative | Re-verify directly (M0) before closing any of the six affected items | Engineering/QA |
| Q2 | Customer Service: real second track or scenario-flavor label only | Decide now (M14); do not leave `DE-ESC` scored without one | Product |
| Q3 | Are `8`/`40`/`12`/`210` real future totals | Correct displayed totals to match built content now (M3); revisit only if a real content plan sets larger targets | Product/Content |
| Q4 | Backup: real export or permanent relabel | Relabel now (cheap, immediate); real export only if requested | Product |
| Q5 | Arabic/RTL: near-term scope or not | Interim honesty fix stands (M10); full RTL only with a dedicated scope/content decision | Product |
| Q6 | Assessment isolation: reset on mode switch, or continuous with disclosure | Interim disclosure fix is safe either way (M4); permanent policy needs an owner | Product/Learning design |
| Q7 | What does "Saudi readiness" (and the streak target) actually measure | Remove or derive (M11) if no real definition exists within this cycle | Product/Content |
| Q8 | `Map.tsx`: future feature or dead code | Document as out-of-loop now; decide at next roadmap review | Product |
| Q9 | `FXP` real-world domain accuracy | Commission the review (§14); do not build further curriculum on the current vocabulary until answered | Content/SME |

---

## 28. Target Product Architecture

A conceptual layering of what AeroBridge actually is today, so future work targets the right layer instead of over- or under-building:

| Layer | Current state | Verdict |
|---|---|---|
| Experience / UX | Flight Deck Console identity, Terminal-first, five-screen loop | Sound, load-bearing, preserve in full |
| Content / curriculum | Hardcoded literals in `Home.tsx`; one real Technical workflow built, five stages locked/seeded, Customer Service a label with no content | Correctly scoped for current volume; will not scale past it without extraction (§19) — do not extract prematurely |
| Domain / competency model | Two implicit domains (Technical, Customer Service) asserted unequally — one fully built, one only data-modeled | The one genuine architecture-level open question in the product (§10.2, §11) |
| Simulation / practice engine | A deterministic, synchronous lookup over four command prefixes; not a real GDS simulator and does not claim to be | Correctly scoped and disclosed; do not add fake asynchronicity (§8, §15) |
| Assessment / scoring | A transparent weighted formula over a shared, imperfectly-isolated command history | Formula itself sound; isolation and label-accuracy are the real gaps (§13, §20) |
| Data / persistence | `localStorage` only, 8-record cap, no accounts, no sync | Appropriate for current scope; no evidence any larger persistence layer is needed yet |
| Infrastructure | Client-only React app; a `server/index.ts` of unknown scope referenced in the build; no PWA layer | Unknown component (`server/index.ts`) should be read directly if certainty is required; nothing here blocks P0/P1 |

---

## 29. P0 Foundation Plan

**Phase 0 — Freeze the contract.** Record the current AN→SS→FQD→FXP baseline responses, the current scoring output for a fixed input sequence, and the current `localStorage` schema before touching anything, exactly as all three audits specify — this is the comparison point every later regression check depends on.

**Phase 1 — Corpus reconciliation (M0).** Re-verify M1/M2/M10 directly against the live/authoritative build. Update whichever artifact is stale. This phase gates accurate status reporting for those three — it does not gate implementation of the items that are unambiguously still open (M3, M4, M5, M6, M7, M8, M9, M11, M12, M13, M14), which can proceed in parallel.

**Phase 2 — Trust and evidence integrity (M1–M14, order-independent except where §25 specifies sequencing).** Implement in any order except: M8 (fonts) before final M12 (contrast) measurement; M7 (Toaster) before M6's final control-by-control triage; M14's decision before any Customer Service content work begins.

**Acceptance for the P0 tier as a whole:** every number, status message, confirmation toast, and evaluation label on the Practice, Progression, Scenarios, and Growth screens is either true of real state or explicitly labeled illustrative — with zero exceptions, verified against the actually-deployed build, not against either bundled source snapshot alone.

## 30. P1 Core Product Plan

Build the shared tab/toggle/progressbar/landmark/focus-trap accessibility pattern once, apply it to all five groups (mode-tabs, growth-tabs, track-tabs, filter-tabs, metric-switcher), informed by the one group that already shows a partial fix in the traced source. Fix skill-trend icon/color semantics. Bring skill-hover-preview content to mobile via tap/selected-state. Consolidate the `--ab-*` token layer into the canonical set. Fix Scenarios' Filters/Sort. Reconcile mobile-nav breadcrumb numbering against actual tap order. Reduce the fixed Terminal gap. Commission the GDS domain-terminology review. Run the full native-keyboard/tablet/desktop/screen-reader validation matrix.

**Acceptance for the P1 tier:** every visually tab-like control group exposes correct ARIA selection semantics and is independently keyboard-operable; contrast, zoom, and font-size fixes are confirmed with real device/browser evidence, not source inspection alone; at least one desktop and one tablet screenshot exists in this project's evidence history for the first time.

## 31. P2 Expansion Plan

Team discretion, none blocking: toast-reduction in favor of Terminal-history-owned feedback, touch-target sizing, taxonomy cleanup, `Map.tsx`/asset/analytics documentation for handoff, optional realism polish, decorative KPI simplification. Any Customer Service curriculum build (post-M14 decision) belongs here or in a dedicated content initiative, not inside this hardening revision.

---

## 32. Quality Gate

| Condition | Status |
|---|---|
| Corpus integrity | **FAILED as of this pass** — Knowledge Pack and Phase 2/3 notes disagree on multiple confirmed fixes (§7). M0 must run before this gate can pass. |
| Evidence traceability for every MUST/SHOULD item | Passed — every item in §24 cites its source cluster and evidence class |
| Conflict coverage | Passed — every material conflict found (§7.1, §7.2) was traced to a decision, not left ambiguous by default |
| Scope control | Passed — no MUST/SHOULD item expands the product beyond the current architecture; the one architecture-level question (Customer Service) is explicitly routed to a decision, not silently implemented |
| Priority discipline | Passed — P0 is limited to trust/evidence-integrity and confirmed-broken items; cosmetic/preference items are P2 |
| Responsive coverage | **Partially failed** — mobile is thoroughly evidenced; desktop and tablet have zero screenshots anywhere in this project's history (§10.3, §17) |
| Accessibility coverage | Passed at the specification level (Audit C's semantics, focus, contrast work is complete and endorsed); **not yet passed at the runtime level** — no screen-reader session exists anywhere in the evidence |
| No invented engine truth | Passed — this report adds no processing/interrupted states beyond what Audit C's state matrix already correctly scopes to real triggers |
| No prototype work performed ahead of authorization | Passed — this document is analysis and decision only; no code was modified |

**Net result: this Quality Gate does not fully pass yet.** The blocking item is M0 (corpus reconciliation), not any UI finding — implementation of the unambiguous P0 items (M3–M9, M11, M12, M14) may proceed in parallel with M0, but the gate as a whole should not be declared closed until M0's re-verification is complete and the responsive/accessibility runtime gaps have at least a scheduled validation pass.

---

## 33. Evidence Gaps

No desktop or tablet screenshot exists anywhere in this project's evidence history (three candidate audits plus this pass, seven shared screenshots, all mobile). No native on-screen-keyboard test exists at any width. No screen-reader session (NVDA/VoiceOver/TalkBack) exists. No confirmation exists of what `server/index.ts` actually does. No confirmation exists of whether the `/manus-storage/...` hosted assets and the Umami analytics script resolve outside the current preview host. No GDS subject-matter confirmation exists for the `FXP` command mapping. No direct evidence exists confirming or denying whether the empty-submit guard (M1) is present in the currently-live build specifically, as distinct from the two bundled source snapshots that disagree with each other. None of these gaps block the P0 tier in §29, all of which rest on source or independently-derived evidence; they gate exactly the items marked NEEDS VALIDATION throughout this report.

---

## 34. Stop-Auditing Condition

General audit collection on AeroBridge should stop once: (a) M0 through M14 are implemented and re-verified against the live build, (b) the P1 accessibility/interaction pass is complete, and (c) the validation matrix (native keyboard, tablet, desktop, screen reader) has run at least once against the reconciled build. A new review cycle should open only if: new evidence overturns a P0 decision in this report; product scope materially changes (most likely trigger: Customer Service becomes a funded real track per M14); implementation reveals a specific decision in this report was wrong; or a new contradiction appears that cannot be settled with currently available evidence. Do not open a new full audit cycle merely because another model or another pass might phrase an already-settled finding differently — that is the exact failure mode §7.1 already demonstrates the cost of.

---

## 35. Final Executive Decision

**Preserve and refine — confirmed, unanimously, by all three prior audits and independently by this pass.** The Flight Deck Console identity, the Terminal-first architecture, and the five-screen loop are genuine, working, well-built product assets, and nothing in this review disturbs that conclusion.

What this pass changes is not the direction — it is the confidence with which "already fixed" can be asserted, and the number of things being treated as pure UI bugs that are actually one layer deeper. **Before any of the P0 UI items below are marked complete, reconcile which build is actually live (M0)** — this project's own Project Knowledge currently disagrees with itself about whether its two most-cited defects are fixed, and no other verdict in this report can be fully trusted as closed until that is resolved. **Before any Customer Service content is built, decide what Customer Service is (M14)** — the product's own competency model has already made an implicit commitment its content layer has not honored, and that gap should be closed by a decision, not by drift. **Before any new curriculum content is authored, verify the command vocabulary against real GDS domain usage (§14, §10.6)** — the one domain-realism question this pass could not fully resolve on its own.

With those three items handled first, the remainder of this report's P0/P1 scope is exactly what all three candidate audits already converged on: a disciplined trust-and-accessibility hardening pass, not a revision or a redesign, that makes the existing product tell the truth about what happened, what is measured, what is illustrative, and what the trainee should do next.
