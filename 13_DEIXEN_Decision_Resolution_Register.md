---
name: AeroBridge Decision Resolution Register
status: Decision-resolution pass only. No implementation, no curriculum redesign, no Skill Graph work performed or begun.
owns: The audited status of every known decision, as of the end of this pass
---

# AeroBridge — Decision Resolution Register

## Decision Resolution Summary

Of the items tracked across the canonical set, the large majority are now
genuinely **Closed/Approved** — product positioning, the five-area
structure, Terminal centrality, platform sequencing, and localization all
moved from open to decided across this and the two preceding turns. One
technical question (engine strategy) is settled as delegated judgment. What
remains open splits cleanly into three different kinds of "not yet," which
this register keeps separate rather than collapsing into one undifferentiated
backlog: things waiting on Malik's own forthcoming work (visual execution,
naming), things waiting on source material that may or may not still exist
(three referenced documents, the deeper curriculum rationale), and things
waiting on a domain expert who hasn't been engaged yet (all Amadeus
real-world accuracy claims). None of the three block starting the Knowledge
Recovery Pass. No item below was manufactured for completeness — every row
traces to something already identified in the canonical files or this
conversation.

## Closed Decisions Confirmed

Not reopened, not reconfirmed here beyond a pointer — restated only to
establish the baseline this register audits against:

- Product Positioning (professional aviation-ops training platform)
- Terminal Priority (the operational heart)
- Five-Area Information Architecture (Work Shift Simulator excluded pending its own review)
- Platform Direction (not PWA/backend/accounts-first; not a rejection of them either)
- Design Positioning (professional/operational register; separate from Execution)
- Responsive Density baseline (320/360/390/430 + 768/1024/1280–1440)
- Localization (Arabic + English, RTL + LTR — required, not merely inherited)
- Personal-first framing and Saudi/Gulf training context (validation strategy and current focus, not permanent commitments)
- Named historical employers/persona as useful context, not locked strategic commitment
- Vertical Slice Before Scale, and its current instance (Decision 8A: `AN → SS → FQD → FXP`, one scenario)
- Coach Core Guided Learning Layer (mandatory, five touchpoints, state-bound)
- Customer Service Curriculum Contract (separate competency, out of the initial slice)
- Evidence & Readiness Contract, Assessment State Contract, Scenario Differentiation Contract (all Closed as governing rules — see Delegated Technical Decisions for what's still unbuilt under them)
- Manus Collaboration Protocol; Cross-Review Arbitration Outcome (architecture/Terminal-centrality portion only — its visual-direction portion is superseded, not reopened, by the Design Execution decision above)

All are full canonical detail in files 03/04/06/07/08 respectively — not
restated here.

## Delegated Technical Decisions

**Engine strategy — settled.** Neither a full rewrite nor a literal port:
the engine reference becomes a framework-agnostic behavioral contract, the
new implementation is written fresh against it, and the historical
vanilla-JS engine is kept as a conformance-testing oracle. Rationale and
detail in `10_AeroBridge_New_Recommendations.md` §1. This is a decision, not
a proposal — it does not need to come back to Malik, and it does not
authorize starting to build it in this pass.

**Evidence/state schema — partially settled, remainder delegated and not
yet done.** The governing contracts (what qualifies as evidence, how
Assessment carries state, what makes a scenario distinct) are genuinely
Closed. The concrete schema those contracts imply — actual field names, what
a persisted record object looks like, exact hint-counting mechanics — has
not been designed. That design work is technical judgment within Claude's
authority once scheduled; it is independent of Knowledge Recovery and does
not block it.

**Coach layout ownership** (global persistent element vs. per-page
component) — explicitly left open in the Coach contract itself, to be
resolved as an ordinary implementation choice when build work reaches it.
Not a Malik decision; not blocking anything now.

## Remaining Malik Decisions

None currently block the next phase. Two items remain genuinely his, but
both are already correctly parked pending his own separate work rather than
needing action right now — listed for completeness, not because either
needs a response:

| Decision | Why it matters | Evidence available | Recommendation | Consequence of delaying |
|---|---|---|---|---|
| Design Execution (colors, typography, logo, identity, imagery, motion) | Determines the product's actual look, separate from the already-settled positioning | Historical dark-navy/blue tokens exist as evidence, not a default (file 04); Malik is preparing a separate design-reference note | No recommendation appropriate — explicitly Malik's to lead, with Claude Design collaborating once his note arrives | None — nothing is blocked by leaving this open; premature guessing would be the actual risk |
| Naming/branding ("AeroBridge" is a working title) | Final identity affects design execution and any external-facing material | None yet — explicitly open for future exploration | No recommendation appropriate | None — same as above |

## External / SME Validation Items

None of these can be honestly resolved by documentation, prior approval, or
implementation behavior, no matter how carefully verified. Each requires an
actual domain expert:

1. **Command-level accuracy** — whether `AN`/`SS`/`FQD`/`FXP`'s documented
   syntax and behavior genuinely match real Amadeus, not just the internal
   consistency already verified in
   `05_AeroBridge_Canonical_Amadeus_Engine_Reference.md`.
2. **Whole-workflow validity** — whether `AN → SS → FQD → FXP` as a combined
   path is a coherent, recognizable real-world reservations task, not four
   individually-valid commands strung together for engineering convenience.
   Recorded, not assumed, per the prior correction pass.
3. **Acceptability of the engine's built-in simplifications** for the
   stated job-readiness goal — one seat per PNR rather than per passenger,
   no child/infant fare types, Timatic limited to Egyptian passports, a
   two-segment ceiling. These are real, working, intentional limitations;
   whether any of them would leave a learner unprepared for a real
   interview question is a domain judgment, not something implementation
   verification can answer.
4. **By extension**, the other 33 already engine-verified commands, if and
   when they're taught as authoritative beyond the frozen slice.

None of these block entering Knowledge Recovery — recovery is about
documents, this is about real-world fact-checking. They run in parallel,
not in sequence.

## Knowledge Recovery Dependencies

Explicitly not resolved in this pass, and explicitly not to be guessed at:

- **Three referenced-but-unsupplied documents**: the actual Claude/Manus
  arbitration record, the Domain/SME validation brief with its SME-01…SME-10
  claim register, and a Scenario Bank architecture decision review cited
  from inside the repository's own code. If Malik has access to any of
  these, supplying them would materially help the Recovery Pass; if they no
  longer exist, that itself is worth confirming rather than assuming.
- **The curriculum structure question** (competency-ordered progression vs.
  the existing engine-implementation-ordered structure) — genuinely
  undecided, and deliberately not finalized here per this pass's own
  boundary. Before it can be responsibly decided, OLD's actual curriculum
  design reasoning needs full recovery: was the current lesson order a
  deliberate pedagogical choice or an artifact of build sequence? The
  answer isn't currently known either way, which is itself the reason this
  can't be resolved yet.
- **Lesson 17 ("Evaluation Means")** — an undefined gap explicitly carried
  over from earlier planning generations. Worth checking whether earlier
  OLD material ever resolved this before treating it as a fresh design
  question.
- **The 8 of 11 Advanced-course lessons currently marked future-plan** —
  what each actually requires (new engine commands vs. new content only vs.
  genuinely out of scope) has not been determined; recovery should check
  whether OLD's own planning ever specified this before it gets designed
  from scratch.

None of these block *starting* Knowledge Recovery — they are largely what
that pass exists to resolve.

## Safe-to-Defer Items

Real, known, not urgent, and correctly left alone:

- The missing NEW React implementation artifact — no such codebase has been
  supplied to any pass; its actual structure and behavior will need to be
  established from real code, not documentation, whenever implementation
  begins. Not fabricated, not guessed at here.
- `ancillary.js`'s data-initialization wiring (six coded-but-unreachable
  commands) — defer until ancillary-specific scenario content is actually
  planned.
- `cleanRunsNeeded`'s real mastery-rule definition — currently an honestly-
  labeled placeholder; needs real usage data to design against, which
  doesn't exist yet.
- The live-echo element-numbering display bug (`AP`/`TK`/`RF`) — already
  flagged in the historical record as needing its own scoped discussion,
  separate from unrelated work. That's still correct; nothing has changed.
- Work Shift Simulator's eventual scope — real, preserved, not scoped, not
  urgent.
- Updating the *original* OLD documents' own tech-debt tables to reflect the
  now-confirmed RT fix — a housekeeping nicety, not a blocker to anything.

## Final Decision Register

| Item | Category | Status | Owner | Evidence Needed | Blocks Next Phase? | Action |
|---|---|---|---|---|---|---|
| Product Positioning | Product | CLOSED/APPROVED | Malik | None | No | Carry forward |
| Five-Area IA / Terminal Priority | Product | CLOSED/APPROVED | Malik | None | No | Carry forward |
| Platform Direction (PWA/backend sequencing) | Technical/Product | CLOSED/APPROVED | Malik | None | No | Carry forward |
| Localization (AR+EN, RTL+LTR) | Product | CLOSED/APPROVED | Malik | None | No | Carry forward; build approach is a separate technical detail |
| Design Positioning | Product | CLOSED/APPROVED | Malik | None | No | Carry forward |
| Design Execution (colors/type/logo/etc.) | Visual | OPEN — MALIK | Malik | Malik's design-reference note | No | Wait; no action in Recovery Pass |
| Naming/Branding | Product/Brand | OPEN — MALIK | Malik | Future exploration | No | Wait |
| Personal-first & Saudi/Gulf framing | Product | CLOSED/APPROVED | Malik | None | No | Carry forward |
| Engine Strategy (contract + conformance oracle) | Technical | DELEGATED TECHNICAL DECISION | Claude | None | No | Carry forward as settled |
| Evidence/State concrete schema | Technical | DELEGATED, not yet done | Claude | None (needs scheduling, not evidence) | No | Design in a dedicated pass, independent of Recovery |
| Coach layout ownership | Technical | SAFE TO DEFER | Claude/build | None | No | Resolve at build time |
| Curriculum structure (competency vs. engine order) | Learning architecture | OPEN — KNOWLEDGE RECOVERY | Claude, pending recovery | OLD curriculum design rationale | No (this is Recovery's job) | Address in Recovery Pass; do not finalize now |
| Lesson 17 "Evaluation Means" gap | Learning content | OPEN — KNOWLEDGE RECOVERY | Claude, pending recovery | Check OLD v7/v9 material | No | Check during Recovery |
| 8 future-plan Advanced lessons | Learning content | OPEN — KNOWLEDGE RECOVERY | Claude, pending recovery | OLD planning material, if any | No | Check during Recovery |
| 3 missing referenced documents | Knowledge/process | OPEN — KNOWLEDGE RECOVERY | Claude; Malik if he can locate source material | The documents themselves | No | Search for/request during Recovery |
| Command-level Amadeus accuracy (AN/SS/FQD/FXP, then the other 33) | Domain fact | OPEN — EXTERNAL VALIDATION | SME | Domain expert review | No (parallel track) | Keep SME workstream moving |
| Whole-workflow validity of the frozen slice | Domain fact | OPEN — EXTERNAL VALIDATION | SME | Domain expert review | No | Include explicitly in SME scope |
| Acceptability of engine simplifications for job-readiness | Domain judgment | OPEN — EXTERNAL VALIDATION | SME (+ Malik if a real gap surfaces) | Domain expert review | No | Include in SME brief |
| Missing NEW React codebase | Implementation artifact | SAFE TO DEFER | Whoever begins implementation | Real code, if it exists | No | Defer to implementation start |
| `ancillary.js` wiring timing | Technical | SAFE TO DEFER | Claude | None | No | Defer |
| `cleanRunsNeeded` real rule | Technical/Learning | SAFE TO DEFER | Claude | Real usage data | No | Defer |
| Live-echo numbering bug fix timing | Technical | SAFE TO DEFER | Claude | None | No | Defer, own scoped discussion later |
| Work Shift Simulator scope | Product | SAFE TO DEFER | Malik (future) | None | No | Revisit if it becomes a real candidate |
| Named personas/employers specificity | Product | SUPERSEDED (resolved this turn) | — | — | No | Stale references in file 09 §7 and file 10 §6 should be read as actioned |

## Explicit Exit Gate

All currently known decisions carry a status. No open item is being treated
as settled, and no closed item has been reopened without cause. Delegated
technical matters are separated from genuine Malik decisions, which are
currently zero in number and blocking nothing. External validation
requirements and knowledge-recovery dependencies are stated explicitly
rather than folded into either. Curriculum restructuring has not been
finalized — only classified.

**AeroBridge is READY TO ENTER KNOWLEDGE RECOVERY.**
