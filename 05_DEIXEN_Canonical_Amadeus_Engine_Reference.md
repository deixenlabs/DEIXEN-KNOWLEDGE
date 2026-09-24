---
name: DEIXEN Canonical Amadeus Engine Reference
status: HISTORICAL IMPLEMENTATION REFERENCE (07 Decision 14, 2026-09-24) — describes the old engine, whose code is not available. Not the build baseline and not evidence of real Amadeus behavior.
owns: A record of what the old engine implemented — its command set, RBD table, error taxonomy, and known issues
supersedes reading in isolation: COMMAND_REFERENCE.md, DEVELOPMENT_RULES.md §8
source discipline: Every line below traces to either the OLD command-reference document or direct inspection of the supplied repository's code — never to general Amadeus/GDS knowledge. Where the two disagree, the code wins, per the project's own DEVELOPMENT_RULES.md §3 rule, and the disagreement is noted.
---

> **Synchronization note — Phase 2, 2026-09-24.** Working name: **DEIXEN**
> (provisional; see `DEIXEN_Operating_Constitution.md` §1). "AeroBridge" survives
> only inside historical filenames and provenance statements. Owner: **Karim** —
> earlier project records used the name "Malik" for the same person; those
> references now read "Karim". Current project state and every decision:
> `07_DEIXEN_Canonical_Decisions_and_Current_State.md`. Amadeus facts: only
> claims marked VERIFIED under 07 Decision 12 may be taught as fact.


# DEIXEN — Amadeus Engine Reference (Historical Implementation Record)

> **How to read this file (2026-09-24).** Everything below describes the
> old vanilla-JS engine as inspected during the 2026-09-03 consolidation
> pass. That code is no longer available (07 Decision 19), and the new build
> is written fresh (Decision 14). Use this file to learn what the old engine
> did and which mistakes not to repeat — never as a specification and never
> as Amadeus truth. Real Amadeus behavior is owned by
> `DEIXEN_Amadeus_Verified_Reference.md` (Decision 15, created in Execution
> Plan Phase 3) under the Verification Standard (Decision 12). The old
> engine's limitations and Known Issues below are not requirements for the
> new build.

This is the old engine's full command set (37 commands, verified at the time
directly against `parser.js`/`pnr.js`/`pricing.js`/`ancillary.js`/`queues.js`/
`seatmaps.js`/`errors.js` in the repository supplied to the 2026-09-03 pass).
It documents what that **engine could do**. The first-build slice
(`AN → SS → NM → AP → SRCTCM → TK → RF → ER → FXP`, 07 Decisions 22 and 24) is owned by
`07_DEIXEN_Canonical_Decisions_and_Current_State.md`.

**No item below is asserted from general Amadeus knowledge.** Every command's
described behavior is what the supplied code actually did. Anything beyond
this scope (new command families, real-GDS edge cases not covered here) is
out of scope for this reference and must be
VERIFIED under the Verification Standard (07 Decision 12) before being
treated as authoritative.

**Two different kinds of truth, held apart on purpose:**
- **Implementation truth** — what the previously supplied
  AeroBridge repository (now absent) demonstrably did. Every "Code-verified" tag below is this, and only this:
  confirmed by reading the actual source, nothing more.
- **Domain truth** — what real Amadeus/GDS behavior actually should be. This
  requires the Verification Standard (07 Decision 12) and
  must never be inferred from implementation truth alone, no matter how
  confidently or how often a command has been code-verified.

A "Code-verified" tag is never a claim about domain truth, and repeating it
across many rows below doesn't accumulate into one — each row is one more
confirmation of what the code does, not one step closer to confirming what
real Amadeus does.

## Structural facts (all verified against `parser.js`)

- Input is uppercased before dispatch (case-insensitive entry).
- The first 3 characters are checked against a fixed 3-letter command list
  first (`FQD, FXP, TTP, FXB, DAC, DNA, FQN, FQR`); if no match, the first 2
  characters are checked against the 2-letter list.
- Any unmatched prefix returns `UNKNOWN COMMAND` immediately.
- Maximum 2 segments per PNR (round-trip only — no multi-city, no
  connections).
- Maximum 9 passengers per PNR, adults only (no child/infant fare types).

## RBD (Booking Class) Table

`F, A, J, C, D, Y, B, M, H, K` — 10 classes, loaded from `Data/rbd.json`, with
a hardcoded fallback to this exact list if the data file doesn't resolve to
exactly 10 codes.

## Command Reference by Family

### Availability
| Command | Behavior | Status |
|---|---|---|
| `AN` | `AN` + 2-digit day + 3-letter month + origin + destination, e.g. `AN15JULCAIDXB`. Validates day range, airport existence (per side), origin≠destination, and flight existence; stores the result for later `SS` reference. | **Code-verified** |
| `SN` | Schedule display. Cannot seed a subsequent `SS` the way `AN` can. | **Code-verified** |

### PNR Core (name, contact, ticketing, sell)
| Command | Behavior | Status |
|---|---|---|
| `SS` | Sell from a displayed availability line, or direct sell. | **Code-verified** |
| `NM` | Add a passenger name (`NM1…` repeated per passenger — no `NM2`/`NM3` multi-name-in-one-line syntax). Two distinct real messages depending on state: `MAXIMUM 9 PASSENGERS PER PNR` before a segment sets an expected count, or `ALL PASSENGERS ALREADY NAMED` once that expected count is reached — a distinction not previously written down anywhere in the source documents, recovered here from the code directly. | **Code-verified; refined beyond prior documentation** |
| `AP` | Add phone contact. **Live per-command echo hardcodes the element number as `"2."` regardless of actual position** — see Known Issues below. | **Code-verified, with a known display bug** |
| `APM` / `APE` | Mobile / email contact. Echo carries no element number at all (not affected by the numbering bug, but also never numbered). | **Code-verified** |
| `TK` (`TKOK` / `TKTL`+date) | Ticketing arrangement. **Live echo hardcodes `"3."`** for both the immediate-OK and the time-limit variant. | **Code-verified, with a known display bug (affects both variants)** |
| `RF` | Received-from. **Live echo hardcodes `"4."`.** | **Code-verified, with a known display bug** |

### End / Retrieve / Manage
| Command | Behavior | Status |
|---|---|---|
| `ER` / `ET` | End-and-retrieve / end-transact. Require: ≥1 segment, named-passenger count equal to sold-seat count, and `AP`/`TK`/`RF` all present. Compute element numbering **correctly and dynamically** via `formatPnrLines()` for the final PNR display — this is the numbering the live per-command echoes above should match but currently don't. | **Code-verified** |
| `RT` | Retrieve a stored PNR by record locator. Returns `RECORD LOCATOR NOT FOUND` on failure. | **Code-verified — see Known Issues for its history** |
| `IG` | Ignore (discard current PNR without saving). | **Code-verified** |
| `XE` | Cancel an element by line number. Covers passengers, segments, `AP`, `TK`, `RF`, hotel segments, and car segments only — **cannot** individually cancel SSR, mobile, email, remarks, OSI, tickets, or seat assignment. | **Code-verified, documented design constraint** |
| `RM` / `OS` | Remarks / other-service (no fare effect). | **Code-verified** |

### Pricing & Ticketing
| Command | Behavior | Status |
|---|---|---|
| `FQD` | Fare quote display. | **Code-verified** |
| `FXP` / `FXB` | Fare pricing implemented by the supplied engine. The engine recognizes `FXP`/`FXB` and has no `FXX` handler. **`FXX` is a real Amadeus entry (VERIFIED — `DEIXEN_Amadeus_Verified_Reference.md` V-06). The absence of an `FXX` handler here is an implementation-scope fact only.** | **Code-verified** |
| `FQN` / `FQR` | Fare rules — identical handler for both. **Coded but non-functional**: `Data/fares.json` has zero fare entries with a `rules` field, confirmed by direct inspection. | **Coded, not yet functional — confirmed still true** |
| `TTP` | Ticketing. Blocked if ticketing arrangement is still `TL` (time-limited, not `OK`). | **Code-verified** |

### Ancillary Services
| Command | Behavior | Status |
|---|---|---|
| `HA` / `HS` | Hotel availability / sell. | **Coded and correct in isolation, but see Known Issues — not currently reachable with real data in the supplied build** |
| `CA` / `CS` | Car availability / sell (not `VC`). | **Same caveat as HA/HS** |
| `SR` | Special service request — 8 SSR codes only. | **Same caveat as HA/HS** |
| `TI` | Timatic. Simplified, Egypt-passport-only. | **Same caveat as HA/HS** |

### Seating
| Command | Behavior | Status |
|---|---|---|
| `SM` | Seat map display. | **Code-verified and reachable** |
| `ST` | Select seat. **One seat total per PNR, not per passenger** — an explicitly documented, intentionally deferred design constraint in the code itself, with a specific future target ("Phase 14") named in a code comment. | **Code-verified, documented design constraint** |

### Decode
| Command | Behavior | Status |
|---|---|---|
| `DAC` / `DNA` | Airline/airport code decode. | **Code-verified** |

### Queue Management
| Command | Behavior | Status |
|---|---|---|
| `QT` / `QC` / `QS` | Queue table / count / start browsing a queue. | **Code-verified and reachable** |
| `QN` / `QI` | Next / ignore within an active queue-browse session. **Inside the main command parser, these always return `NOT IN QUEUE MODE` regardless of context** — the real logic lives in a separate queue-mode handler, reached only when a queue browse is actually active, checked *before* the main parser runs. This routing was specifically identified as necessary and has been correctly built. | **Code-verified — routing confirmed correctly implemented** |
| `QE` / `QD` | Exit queue mode / delete PNR from queue. | **Code-verified** |

**Queue quarantine:** research leads in the historical evidence package describe different functions for `QE`/`QN`/`QD` than this table. Neither version may be taught or simulated (07 Decision 13) until one is VERIFIED under Decision 12.

## Error Taxonomy

8 categories: `FORMAT`, `DATA_REFERENCE`, `SEQUENCE`, `MANDATORY_MISSING`,
`DUPLICATE_CONFLICT`, `AVAILABILITY`, `LOGICAL`, `GENERAL` — 34 catalogued
messages in `Data/errors.json`, each with an Arabic cause/correction pair for
Coach use.

**Governing rule for any Coach or UI surface touching these messages:** the
official error message is shown verbatim, always; a plain-language
explanation goes alongside it, never in place of it. Substituting a "nicer"
message breaks the realism the whole training environment depends on.

## Known Issues — status at the 2026-09-03 inspection (old engine only; lessons for the new build, not requirements — 07 Decision 14)

| # | Issue | Current status |
|---|---|---|
| 1 | `DUPLICATE SEGMENT EXISTS` exists in the error catalog but no code path ever produces it | **Still a dead entry** — confirmed by direct search; no duplicate-segment check exists anywhere in `pnr.js`. Low priority, safe to defer. |
| 2 | `MAX 9 PASSENGERS PER SEGMENT` exists in the catalog but the real message the code returns is `MAXIMUM 9 PASSENGERS PER PNR` | **Still a dead entry** — confirmed; the real message is correct and in active use. Low priority. |
| 3 | The `matchKeys` for `ITEM NOT FOUND / NO PNR` were missing `RECORD LOCATOR NOT FOUND` — the actual string `RT` returns on failure — so the Coach could not recognize a real failed retrieval | **FIXED.** Direct inspection of `Data/errors.json` shows `matchKeys` now includes both strings. This was previously the single highest-priority item in the whole registry (it gated full Coach activation). It no longer blocks anything. **The written documentation predating this reference had not caught up to this fix — this file is the correction.** |
| 4 | `XE` cannot individually cancel SSR/mobile/email/remarks/OSI/tickets/seat | **Still true, documented design constraint**, not a bug — a deliberate current limitation. |
| 5 | One seat per PNR, not per passenger | **Still true, documented design constraint**, with a specific named future target (internal "Phase 14") for the fix. |
| 6 | `FQN`/`FQR` non-functional pending `fares.json` `rules` data | **Still true, confirmed by direct inspection** — zero `rules` fields exist in the fare data. |
| 7 | `pnr.js` hardcodes live-echo element numbers for `AP` (`"2."`), `TK`/`TKTL` (`"3."`), and `RF` (`"4."`) instead of computing them dynamically the way the final-PNR formatter does — so the number shown while typing can be wrong once more than one passenger or segment precedes it, risking a learner memorizing the wrong number to use later with `XE` | **Still true, confirmed by direct inspection.** Also confirmed to affect the ticketing-time-limit variant (`addTicketingTimeLimit`) in addition to the two functions previously named — a fourth affected function this reference adds. Deliberately not patched in the integration layer (explicit pass-through by design); the real fix belongs in the PNR module itself and needs its own scoped discussion before being touched. |
| 8 *(new, found this pass — not in any prior document)* | `ancillary.js` (`HA`/`HS`/`CA`/`CS`/`SR`/`TI`) is fully coded and wired into the command dispatcher, but its data-initialization function is deliberately never called anywhere in the integration layer | **Confirmed by direct inspection of the integration code's own comments.** These six commands are not currently reachable with real data in the supplied build, despite being documented and code-complete. No scenario currently exercises them, which is why this was left unwired rather than an oversight — but it means this command family should not be assumed live without re-checking. |

## What this reference deliberately does not do

It does not claim that anything above is real-world-accurate Amadeus
behavior. Real Amadeus behavior is decided only under the Verification
Standard (07 Decision 12) and recorded in the Verified Reference. What this
file records is what the old engine's code did at the time it was inspected
(2026-09-03) — nothing more.
