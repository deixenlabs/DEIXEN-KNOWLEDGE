---
name: DEIXEN Slice Build Spec
status: CURRENT — APPROVED by Karim 2026-09-25 (07 Decision 26). Updated 2026-09-25: gaps G1–G3 (§5, §12); Decision 27 (K5, K6) applied to §4, §5, §12, §13; K7 (§6 row 5, §12) approved in the Phase 3 gate (07 D28). Phase 4, 2026-09-25: 07 Decisions 30, 32–34, 36 applied to §5 and §13; Decisions 37–38 to §4 and §8. Phase 4 gate, 2026-09-26: 07 Decision 42 (approved design, `tokens.css`) applied to §2; Decision 44 (`AN` header number) to §5 and §12; Decision 45 (boards exported to `design/phase4/`) to §2. Phase 5, 2026-09-26: 07 Decisions 46 (`result` on ending events) and 47 (one tab at a time) applied to §11. 2026-09-26: 07 Decision 49 applied to §6 ("not recognized" vs "not covered") and new §6A (rules for build step 2 part B). 2026-09-28: 07 Decision 50 — §6A items 8–10. 2026-09-28: 07 Decision 52 — new §7A (rules for build step 3), pointers in §8, §10, §11. 2026-09-28: 07 Decision 53 — §7A items 1 (return to practice, app I-12) and 14 (data-reset notice). 2026-09-28: 07 Decision 54 — new §7B (rules for build step 4: the current step for hints, hint levels on the screen, the entry field, parts 4A/4B, load notices), pointer in §8. 2026-09-29: 07 Decisions 55–56 — §7A item 1 (a run also starts at an accepted hint request, app I-12), items 1 and 11 and §9 (pointers to the in-app exit), §7B heading and new items 6–10 ("Booking as it stands", leaving a running assessment or scenario, storage refused, the name as a string key, behaviours over time); 07 Decision 57 — §7B items 11–15 (the Flight Deck's recommended action, the practice run when moving between screens, Learning, Ghost Mode replays, when the scenario and the assessment start). 2026-09-30: 07 Decision 58 — §7B items 16–18 (the way into Ghost Mode, Ghost typing speed, "In your task"); 07 Decision 59 — §7A item 13, §7B item 11 (d) and §10 ("the scenario completed" means completed with every checklist item met), §7B items 19–20 (the scenario and assessment rows; the assessment and scenario screens). 2026-09-30: 07 Decision 61 — new §7C (rules for build step 5, Coach: when each Coach text shows, Coach and independence, the assessment and the scenario, the bypass, the escalation count, the Growth note, the five touchpoints), pointers in §6A item 2 and §8. 2026-10-01: 07 Decision 62 — §7C item 6 (the escalation offer may follow the bypass notes in practice, app I-22). 2026-10-01: 07 Decision 63 — new §7D (rules for build steps 6 and 7: step 6 as a check with a Definition of Done trace, the end note in view, the scrolling notes block, the phone drawer, what the accessibility baseline means here, the localization and breakpoint passes, lockup B, what automated checks cannot prove), pointers in §2 and §13. 2026-10-02: 07 Decision 64 — §7B item 17 and §7D item 5 (d) corrected (`--motion-demo-hold` stays under reduced motion: a still reading pause, app I-23); §7D item 6 (English terms written in the approved Arabic content are allowed, app I-24). 2026-10-04: 07 Decision 76 (F-04 (A)(B) landed; 07 D69 F-04 amends D40) — §7 (learner-facing wording: two terms), §7B item 11 (the chain word), §7C item 8 (the chain word), §8 (the note after a valid entry that does not count as done on your own). First edition (Execution Plan 3.3); proposals K1–K4 approved (07 Decision 25). With this approval, the LDS/LXA content extracted here is binding for the slice (LDS and LXA reading rules, point 1).
owns: The single build specification Claude Code implements for the first-build slice. It gathers requirements from their owners and designs the evidence/state schema (delegated to Claude — file 13).
does not own: any decision (07); Amadeus behavior (Verified Reference); product structure (03); design (Design Brief / Phase 4). Where this file and an owner disagree, the owner wins and the conflict is reported.
---

# DEIXEN — Slice Build Spec

Reading guide for Claude Code: §1–§3 say **what** to build, §4–§6 **how the
Terminal behaves**, §7–§10 **how learning and evidence work**, §11 **data**,
§12 **what is still open**, §13 **Definition of Done**. Tags: **[D]** =
decided (source cited); **[DELEGATED]** = technical design by Claude within
its delegation; **[PROPOSED]** = needs Karim's approval (all listed in §12;
none open at present).

---

## 1. Scope

**[D] What the slice is** (07 Decisions 8A, 20, 22, 24): one real Pricing &
Ticketing task, end to end, with real content:

`AN → SS → NM → AP → SRCTCM → TK → RF → ER → FXP` — `FQD` optional.

through the full chain (03): Learning → Terminal/Practice → Scenario →
Assessment → Evidence → Growth/Readiness. Exactly **1** scenario, **1** owned
assessment record, **1** qualitative Growth/Readiness output, Coach at all
five touchpoints (07 D8A, D9).

**[D] Not in the slice** (07 D8A): full curriculum; more scenarios; Customer
Service track; Speed Drills; spaced-retrieval prompt (LDS §24); any Amadeus
behavior not VERIFIED; numeric readiness; backend, accounts, login, sync, PWA
(03 Platform Direction); new top-level areas.

**[D] Scope limits inside the slice** (07 D25, K1; D14 requires every limit
to be explicit and disclosed): one adult passenger; one flight segment; a single
applicable fare, so `FXP` never needs the `FXT` selection step (V-05). Any
entry outside these limits gets the "not covered in this slice" message
(§5).

## 2. Product frame

- **[D] Five areas, no sixth** (03): Flight Deck · Learning · Terminal/Practice
  · Scenario Bank · Growth/Readiness. Assessment is a mode inside practice.
- **[D] Areas and controls outside the slice** are shown as truthfully
  labeled unavailable — never as working (07 Definition of Done).
- **[D] Arabic + English, RTL + LTR**, switchable (07 D11). How it is built
  is an implementation choice.
- **[D] Platform:** frontend-only web app; state in `localStorage`; no
  login; a session is the browser plus its storage (03 Persistence). Stack
  choice is Claude Code's (delegated), recorded in `CLAUDE.md` (3.5).
- **[D] Visual design** is the approved Phase 4 design (07 D42): direction
  A "Margin", on the Claude Design canvas
  https://claude.ai/artifact/PaSoos61b5By1yqdmUK1JM at version
  `1790413092-0523`, and its one token file `tokens.css`.
  - **Values:** every colour, type step (both scripts), space, radius, rule,
    layout width, motion and layer comes from `tokens.css`, through its role
    tokens (sections 2–9 of the file), never a raw value — the frames follow
    the same rule. `tokens.css` is used unchanged (sha256 in 07 D42).
  - **Typefaces** (07 D42): IBM Plex Mono for the record (Terminal); Public
    Sans with IBM Plex Sans Arabic for the interface; Literata with Noto
    Naskh Arabic for DEIXEN's voice; fallbacks as in `tokens.css`. All are
    open-licence; how they are delivered is a technical choice (CLAUDE.md §4).
  - **Header wordmark: lockup B** (07 D42). Below 24 px cap height (desktop
    header 18 px, phone header 15 px) the wordmark keeps its field line and
    drops the ticks. The frames draw lockup A; B governs.
  - **Where the boards are (07 D45):** a read-only copy of every board
    below, and `tokens.css`, is in `DEIXEN-KNOWLEDGE/design/phase4/`
    (files `<name>.dc.html`), with `MANIFEST.md` giving each file's sha256.
    Read the boards there. Before relying on a board, check its sha256
    against the manifest; a mismatch or a missing board means stop and ask
    (CLAUDE.md §6). The boards expect the canvas runtime (`support.js`, not
    copied): read them as HTML markup — layout, role tokens, words, ARIA.
  - **Boards to read** (files `project/<name>.dc.html` on the canvas;
    `design/phase4/<name>.dc.html` in the repository):
    `P1-B-Identity` (wordmark, mark and icons, header lockups, the three
    voices), `P1-C-Rules` (what the identity is and must never become),
    `P1-D-Tokens` (the token file shown), `P1-E-Behaviour` (every Terminal
    state once), `P1-F-Controls` (default, hover, focus, active, disabled for
    every control), the eight states in English `P1-01` … `P1-08` at 1440 and
    390 (including `P1-04c` keyboard open and `P1-04d` DEIXEN drawer open),
    the same in Arabic `P2-AR-*`, the other widths `P2-BP-*`, the phone menu
    `P2-Menu-390-EN/AR`, and `P2-Issues` (the record of every design answer).
    Not part of the design: the session-1 boards (`A*`, `B*`, `C*`,
    `Issues`), the audit board `P1-A-Audit`, the map board `Main`.
  - **What a frame is:** one moment of one state. Behaviour comes from this
    spec (§3–§10); Terminal lines come from the engine and `slice.json`
    (the lines in frames are samples of the verified renderings); words come
    from the string files (interface words: `ui.*` keys, 07 D43). Where a
    frame and this spec disagree, this spec wins and the difference is
    reported (CLAUDE.md §6).
- **[D] Accessibility and breakpoints:** file 04 (WCAG 2.1 AA; keyboard;
  320–1440 px). Terminal workspace is never sacrificed on mobile. How the
  build proves it: §7D items 5–7 (07 D63).

## 3. Learner states and screens

**[D]** The eight states of LXA §8, with LXA §9 transitions:

| State | Must do | Produces evidence? |
|---|---|---|
| `ORIENTATION` (Flight Deck) | One recommended next action from evidence; fresh learner → first Lesson | No |
| `LEARNING` (Lesson) | Lesson content; `practiceBridge` into Terminal | Lesson completion only (never skill evidence) |
| `GHOST_MODE` | Play/pause/replay; `reveal` steps use the live simulator's output (06) | No — never above INTRODUCED |
| `TERMINAL_PRACTICE` | §4–§8 | Yes |
| `TERMINAL_ASSESSMENT` | Same Terminal; entry is announced, never silent; carry-over disclosed; hint label honest (07 Assessment contract) | The one assessment record |
| `SCENARIO_SESSION` | Terminal framed by the scenario's objective/constraints | Yes, scenario-linked |
| `GROWTH_READINESS` | One status: Completed / In Progress / Needs More Practice; honest empty state | No |
| `RESET_RECOVERY` | Confirm/cancel full reset → clean `ORIENTATION` | Clears all |

## 4. Terminal — interaction skeleton

**[D] File 03 Terminal Behavioral Skeleton**, per exchange: Awaiting input →
Command submitted → Valid **or** Invalid/out-of-boundary → Hint requested →
Completion detected → Reset/retry.

- **[D] Binding rule (03):** empty or unrecognized input is never silently
  turned into a different valid command.
- **[D]** "Not recognized" and "not covered in this slice" are different
  messages (03).
- **[D] Element numbering (07 D27, K5; replaces the D14 wording):** every
  element number shown in the Terminal is the element's number in the PNR
  *as it stands at that moment*, computed by **one** function that the final
  PNR display also uses (Verified Reference V-18). Order: names, then air
  segments, then contact (`AP`), then `TK`, then SSR and other elements —
  `TK` is displayed before an SSR entered earlier. So numbers change as the
  PNR grows, exactly as in the official examples: the segment sold by `SS`
  is element 1 until `NM` adds a name, then 2; after `TKOK`, an `SSR CTCM`
  entered before it moves from 4 to 5. No screen may show a number that
  function did not produce (the old Known Issue #7 lesson, 07 D14).
- **[D] Hint counter (03):** one counter, incremented in exactly one place,
  counting learner-requested hints only (LDS §15).
- **[D] Reset task (07 D37):** the one Reset/retry learner control (03), in
  `TERMINAL_PRACTICE` only: starts the practice booking again from empty;
  events already recorded stay. No separate retry control. Not offered in
  assessment or scenario. Full reset = `RESET_RECOVERY` (§3).

## 5. Terminal — output rules

**[D] 07 Decision 23 + 06 error-message discipline.** Every output line is
one of three kinds, each visibly distinct:

1. **Amadeus output** — only formats taken from official examples recorded
   in the Verified Reference. Verified messages are reproduced exactly:
   `NEED TICKETING ARRANGEMENT` (V-09);
   `MISSING SSR CTCM MOBILE OR SSR CTCE EMAIL OR SSR CTCR NON-CONSENT` (V-13).
2. **Training message** — for anything with no verified source (e.g. the
   response to a malformed entry). Visibly marked as a training message;
   never styled or worded to pass as real Amadeus text.
3. **Coach explanation** — plain language beside the output; never replaces
   a real Amadeus message.

**[D] Placement (07 Decision 30).** The Terminal contains only kind 1
(with the marker below where it applies) and, where Amadeus would answer but
no verified text exists, **one short training line** labeled with
`ui.trainingLabel`. Kind 3, every feedback text (§8), every hint, and every
other DEIXEN explanation appear in the **DEIXEN panel** — beside the
Terminal on desktop, on demand on mobile (LXA §18).

**[D] Wrong entry of a known command (07 Decision 33).** An entry of a §6
command that fails its checklist leaves the practice PNR unchanged (a DEIXEN
rule — the slice has no `XE`). The Terminal shows the training line named in
`slice.json` `feedback[].terminalLine`: `tm.notAccepted` when the entry does
not follow the verified pattern or points to something that does not exist
(format, date range, no display, missing line); `tm.notForTask` when the
entry is well formed but its data is not the task's. A more specific message
wins where its condition holds: verified messages and `tm.rfMissing` /
`tm.otherMissing` for `ER` (§6 row 8), `tm.noPracticeData`,
`tm.classNotOffered`, `tm.secondName`, `tm.fxpBeforeName`. The feedback text
itself goes to the panel. An unknown command stays `tm.notRecognized`; an
entry outside the slice stays `tm.notCovered` (03).

**[D] Long training messages (07 Decision 34).** A training message with
more than one sentence shows its first sentence in the Terminal, labeled;
the rest of the same string appears in the panel. Split the authored text
at the end of its first sentence *before* filling tokens (`{RF_TEXT}`,
`{CTCR_TEXT}`), so learner-typed text can never move the split. Never
rewrite or shorten a string.

**[D] Script and direction (07 Decision 32).** Terminal entries and Amadeus
output are Latin, monospace, left-to-right in both languages. Chrome, panel
and training lines follow the interface language (Arabic: right-to-left).

**[D] Phone Terminal (07 Decision 36).** Terminal columns never wrap; the
Terminal sheet pans sideways, by touch and by keyboard.

**Screen layouts (G1 — closed 2026-09-25):** build the `AN` display, the
`SS` sell response, the `FQD` display, the `FXP` response and every PNR
redisplay from Verified Reference §2A (V-14–V-18): field order, line
order, header and element order as recorded there; fictional values from
`content/data/slice.json`. Column spacing is not verified (U-06): align
columns in a fixed-width font. No screen remains `UNVERIFIED-LAYOUT`.

**[D] Partly verified details (07 D27, K6).** Details that official
examples show only in part are drawn in the verified pattern with a visible
marker (`ui.unverifiedMarker`: "Layout detail not fully verified"), never
taught, and listed in the Scope Disclosure (`disc.6`, `disc.7`). The marker
is a fourth visual element beside the three kinds of output: it labels a
display, it is not a message. Details with no official pattern at all stay
plain training messages (07 D23).

| Detail | Reference | How the Terminal shows it |
|---|---|---|
| `AN` header number before the weekday; figure after each class letter; the `E0` code group | U-09 | V-14 pattern with the values in `slice.json` — the header number is the fixed `displays.AN.headerNumber` (`30`) in every `AN` display, never computed from the date (07 D44); one marker on the display; meanings never taught |
| `AN` header time when the entry includes a time | U-10 | The time the learner entered, in the V-14 time field, with the marker. Entry without a time → `0000`, as in both official examples (no marker needed) |
| Stored `SSR CTCM` line with the airline code filled in | U-07 (first part) | V-18 pattern `SSR CTCM` + airline + `HK1` + number, with the marker |
| PNR redisplay after `AP`, `SRCTCM`/`SRCTCR`, `TK`, `RF` | U-11 | V-18 redisplay under the `RP/` header, with the marker |
| Stored `SRCTCR` line | U-07 (second part) | No official pattern → training message `tm.ctcrLine` in place of the line. SSRs come after `TK` (V-18) and nothing follows them in the slice, so this changes no other element's number |
| `RF` before end of transaction | U-08 | No official pattern → training message `tm.rfLine`; RF gets no line number |

**Content (G2, G3):** all lesson, Ghost Mode, task, scenario, feedback,
hint, training-message, Coach, contract-text and Scope Disclosure wording
lives in `deixen-app/content/` (`data/slice.json`, `en/text.json`,
`ar/text.json`) — wire it in, never rewrite it (CLAUDE.md §3.3). Commands
inside Arabic text are Latin strings: render them left-to-right.

**Simulated data** (flights, fares, record locators) is fictional practice
data, kept in content files, never presented as real schedules or fares.

## 6. Command behavior (VERIFIED only)

Each row: what the entry is, its checklist (§8), and what the simulator does.
Only VERIFIED content from `DEIXEN_Amadeus_Verified_Reference.md`.

| # | Command | Verified basis | Correctness checklist (all items must pass) | Simulator behavior |
|---|---|---|---|---|
| 1 | `AN` | V-01, V-02, V-14 | (a) `AN` + date (DDMMM) + city pair, optional time — pattern `AN14FEBSTOFRA1700`; airline code optional after `AN` (`ANMH06NOVKULSIN`); (b) date within 361 days ahead / 3 days back; (c) city pair and date match the task | Shows availability for the task's route: flights with ≥1 seat; order non-stop → direct → connecting |
| 2 | `SS` (short sell) | V-03, V-15 | (a) `SS` + seats + class + line number; (b) line number exists in the last availability display; (c) seats = task passengers; (d) class matches the task | Adds segment with status `HK` + count (e.g. `HK1`) |
| 3 | `NM` | V-07 | (a) `NM` + count + `SURNAME/FIRST TITLE`; (b) count = passengers; (c) name matches the task | Adds name element |
| 4 | `AP` | V-11 | (a) `AP` + free-text contact; (b) contains the task's phone | Adds `AP` element as free text |
| 5 | Passenger contact SSR: `SRCTCM` (main task) / `SRCTCR` (scenario) | V-13; U-12 | Main task: (a) `SRCTCM-` + number (dash mandatory); (b) number = the passenger's mobile from the task. An ending after the number that starts with `/` (official example `SRCTCM-3054996244/US`) is accepted and not checked. Scenario: (a) `SRCTCR-` + free text (source example `SRCTCR-REFUSED/P3`; passenger association not taught as a rule). **[D] (07 D28, K7)** the endings are not taught (U-12) | Adds the SSR CTC element |
| 6 | `TK` | V-09 | (a) `TKOK`, or `TKTL` + date — whichever the task asks | Adds TK element |
| 7 | `RF` | V-10 | (a) `RF` + free text naming who requested the booking | Adds RF (shown until end of transaction, then moves to history) |
| 8 | `ER` | V-08, V-09, V-10, V-13 | (a) entered when name, itinerary, contact, TK, RF and a passenger-contact SSR are all present | Ends transaction and redisplays the PNR with a record locator. Missing TK → `NEED TICKETING ARRANGEMENT`; missing CTC SSR → the V-13 warning (a second `ER` bypasses it, per V-13); missing RF → PNR not filed (V-10; message text unverified → training message); other missing elements → training message `tm.otherMissing`, worded as DEIXEN's task rule (that `AP` is the PRINT Phone element is not stated by a source — U-14) |
| 9 | `FXP` | V-05, V-17 | (a) `FXP` entered on a PNR that has name and segment (the path guarantees this — U-01 is not exercised) | Prices with booked class; creates a TST |
| opt | `FQD` | V-04, V-16 | (a) `FQD` + city pair; options after `/` | Fare display for the task route |

- **[DELEGATED] Simulated office profile:** TK is mandatory (V-09 says this
  is an office-profile setting). Disclosed in the Simulator Scope Disclosure.
- **[D] Nothing else** is simulated as Amadeus behavior. **(07 D49,
  answering app issue I-6)** An entry whose code the Verified Reference
  names but the slice does not simulate (e.g. `FXX`, `FQN`, `ET`, `SRCTCE`)
  → `tm.notCovered`; any other entry → `tm.notRecognized` (03: two
  different messages). `FXP` after `ER`: the slice ends at the `FXP`
  display (Verified Reference U-05).
- **[D] Error categories** for Coach and evidence use the internal
  8-category taxonomy (LDS §14): FORMAT, DATA_REFERENCE, AVAILABILITY,
  GENERAL, SEQUENCE, MANDATORY_MISSING, DUPLICATE_CONFLICT, LOGICAL. These are
  DEIXEN's own labels, never shown as Amadeus text.

## 6A. Rules for build step 2 part B (07 D49)

**[D] by delegation (07 D29)** — gaps found while preparing build step 2
part B, closed so the build does not have to guess. None of them claims
Amadeus behavior beyond the Verified Reference.

1. **`ER` with more than one thing missing.** Row 8 names one response per
   missing item. When exactly one of these is missing — `TK`; the
   passenger-contact SSR; `RF`; or any of name / itinerary / `AP` — the
   Terminal shows that item's response (`NEED TICKETING ARRANGEMENT`; the
   V-13 warning; `tm.rfMissing`; `tm.otherMissing`). When more than one of
   these four is missing, it shows `tm.otherMissing`: which message real
   Amadeus shows first is not verified, so DEIXEN does not pick one. The
   panel shows `er.fb.missing`; Partial Reveal lists every missing item
   (`er.partial.*`). The PNR is not filed.
2. **The V-13 bypass.** After the V-13 warning, if the very next entry is
   `ER` and nothing else is missing, the PNR is filed without a contact
   SSR, and the bypass is recorded: checklist item (a) of `ER` fails; the
   panel shows `er.fb.bypassed` (practice, assessment) or
   `scn.fb.bypassed` (scenario) and `coach.bypassRecorded` (§7C item 6).
   Any other entry
   in between (valid or not) cancels the pending bypass; the next `ER`
   shows the warning again. (V-13 says only that entering `ER` again
   bypasses it; the "very next entry" window is a DEIXEN rule.)
3. **The filed PNR (successful `ER`).** V-18: header `RP/` + office ID +
   `/` + office ID, agent sign (`slice.json` `office.agentSign`), date and
   time (Z), record locator; then name, segment (the V-18 segment line
   after end of transaction, ending `*1A/E*`), `AP`, `TK OK` + date + `/`
   + office ID (the date, as in the official examples, is the PNR's
   creation date), then the contact SSR.
   `RF` is not shown (V-10). No tag line above the header (`disc.6`). The
   record locator (six characters A–Z/0–9), the date and the time are
   inputs to the engine, which stays pure (no clock, no randomness).
4. **The stored contact SSR.** `SSR CTCM` line: the V-18 pattern — `SSR
   CTCM`, `6X`, `HK1`, the number, then the learner's ending exactly as
   typed if there was one (the official line shows an ending after the
   number) — with the marker (U-07). Stored `SRCTCR`: `tm.ctcrLine` in
   place of the line, carrying no element number (it is a training message,
   not an Amadeus line); nothing follows it, so no number changes.
5. **`SRCTCR` in the main task** (well formed, but the passenger gave a
   mobile): `tm.notForTask`, panel `ctc.fb.refusalNotTask`, PNR unchanged.
   (`SRCTCM` in the scenario already has `scn.fb.ctcmInvented`.)
6. **`FXP` and completion.** Row 9's checklist holds before or after `ER`
   (a PNR with a name and a segment). The task is **complete** when `FXP`
   is accepted after the PNR has been filed by `ER` — also after a bypass
   filing, which is already recorded as not correct. `FXP` before `ER`
   prices and counts for the `FXP` skill, but does not complete the task.
7. **After completion** every further entry gets `tm.sliceEnd` and changes
   nothing (U-05). In practice the learner starts again with Reset task.
8. **(07 D50) Layouts for the filed header and `FQD`.** Build them from the
   DEIXEN renderings in Verified Reference V-18 (header after end of
   transaction: day without a leading zero, `HHMM` + `Z`) and V-16 (`FQD`,
   with what is left out and disclosed in `disc.6`).
9. **(07 D50) After filing** (Karim, build session 3, app issue I-11): an
   entry that would change the filed booking — `AP`, a contact SSR, `TK`,
   `RF`, `ER` — gets `tm.notCovered` and changes nothing (the slice does not
   simulate changing a filed booking). `FXP` still prices.
10. **(07 D50) Repeated elements before filing.** A second `AP` or a second
    contact SSR adds another element (official PNRs show several `AP…` and
    `SSR` elements). A second `TK` or a second `RF` gets `tm.notCovered` and
    changes nothing: no official example shows two, and what Amadeus does
    with a second one is not verified.

## 7. Skill model

**[D on approval — LDS §7, §10, §23]**

- One skill per path command (`FQD` optional skill, not required for
  Completed).
- States: `NOT_STARTED` → `INTRODUCED` (lesson engaged) →
  `DEMONSTRATED_INDEPENDENT` (≥1 independent full-checklist success) →
  `CONSOLIDATED` (≥2 qualifying independent successes, drill or scenario) →
  `TRANSFERRED` (independent full-checklist success inside the scenario,
  where the skill was necessary to the scenario's differentiating
  condition). Modifier: `NEEDS_REINFORCEMENT` (fresh error after
  CONSOLIDATED/TRANSFERRED; cleared by one correct full-checklist attempt).
- Demotion: TRANSFERRED → CONSOLIDATED, CONSOLIDATED → DEMONSTRATED_INDEPENDENT,
  after 2 consecutive failed reinforcement attempts.
- A single failure never removes a state. Ghost Mode never raises a skill
  above INTRODUCED.
- **Tiers (LDS §8):** Tier 2 for `AN`, `SS`, `NM`, `AP`, `SRCTCM`, `TK`,
  `RF`, `FXP`, `FQD`. **Tier 3 for `ER`** — several verified preconditions
  (§6 row 8). Tier 3 requires Error-Recovery Practice before CONSOLIDATED:
  the learner meets at least one verified failure (recommended:
  `NEED TICKETING ARRANGEMENT`) and recovers.
- **Chain practice (LDS §29 item 5):** after all nine required skills reach
  DEMONSTRATED_INDEPENDENT, the learner completes the full path once,
  unaided; a self-corrected error does not void it.
- **Learner-facing wording:** "correct in DEIXEN", never "mastered" (LDS §10,
  §29 item 4). **[D] (07 D69 F-04 (A); 07 D76)** Two terms, one meaning
  each: "Correct in DEIXEN" (`ui.correctInDeixen`, green) = this entry met
  the checklist — the panel head of a valid entry; "Done on your own"
  (`ui.doneOnYourOwn`, interface text, never green) = the step's skill is
  DEMONSTRATED_INDEPENDENT or higher — the chain rows on the Flight Deck and
  Growth. `disc.9` defines both. Neither is "mastered".

**PROVISIONAL numbers** (LDS §36) — keep in one config file, easy to change:
`CONSOLIDATED_COUNT = 2`, `REINFORCEMENT_FAIL_COUNT = 2`,
`ESCALATION_ERROR_COUNT = 3`.

## 7A. Rules for build step 3 (07 D52)

**[D] by delegation (07 D29)** — gaps found while preparing build step 3
(bridge, independence flag, skill states, Growth status), closed so the
build does not have to guess. They make §7–§11 exact; none adds an event
field or event type (§11), and none claims Amadeus behavior.

1. **Run.** A run is the Terminal work on one booking. It starts with the
   first entry — or the first accepted hint request (§7A item 10), if that
   comes first — after the app loads or after Reset task, or when an
   assessment or the scenario starts; it ends at Reset task, when another
   run starts, or when the page unloads. (A hint is recorded on a step
   attempt, item 2, and a step attempt needs a run: Karim, build session 4,
   app I-12, second half; 07 D55.) After an assessment or the scenario has
   ended, the learner can return to practice, which starts a new practice
   run on an empty booking (Karim, build session 4, app I-12; 07 D53).
   Leaving one while it runs: §7B item 7 (07 D56). Task completion (§6A item 6) does not end the
   run (later entries get `tm.sliceEnd`). The booking is not stored (§11
   stores events only), so after a reload the practice booking starts
   empty.
2. **Step attempt — the meaning of `attemptId`.** `attemptId` names one
   step attempt: the events of one skill in one run, from the first event
   on that skill until an entry of that skill is `valid` or the run ends.
   The next event on that skill opens a new step attempt.
   `command_submitted`, `hint_requested` and `feedback_shown` carry the
   `attemptId` of their skill's open step attempt. So a hint shown for a
   step counts against every later entry on that step while it stays
   visible (07 D38), until the step is passed or the run ends.
3. **`result` of `command_submitted`**, taken from the engine's result:
   `valid` — every checklist item passed; `invalid` — a slice command with
   at least one failed checklist item (this includes every refused `ER`
   and the V-13 bypass filing, §6A item 2); `out_of_scope` — the engine
   returns no checklist (`tm.notRecognized`, `tm.notCovered`,
   `tm.sliceEnd`). `skillId` is the command's skill (`SRCTCM`/`SRCTCR` →
   `CTC`), empty for `tm.notRecognized`. `errorCategory` is the category of
   the feedback item the engine returns. Only `invalid` entries are errors.
4. **`feedback_shown`.** One event for each feedback item the engine
   returns for an entry (the panel text, §5), carrying that item's own
   `skillId` and `kind` from `slice.json` — not the skill of the command
   typed. Example: in the scenario, the V-13 warning after `ER` returns
   `scn.fb.warningShown` (skill `CTC`, corrective). In `slice.json`
   feedback items, `context` `practice` means the main task, in practice
   and in the assessment (§6A item 2). Hints are recorded only as
   `hint_requested`, never also as `feedback_shown`. Coach explanations
   (`coach.*`) are not events.
5. **`ghost_played`.** Recorded when a Ghost Mode script starts, with the
   lesson's `skillId`. A script reveals every skill that has an entry in it
   (`slice.json` `ghostScripts`; e.g. `L05-CTC` reveals `AN`, `SS`, `NM`,
   `AP` and `CTC`). Ghost Mode is not evidence (§3) and never raises a
   skill above `INTRODUCED`. `lesson_completed` likewise carries its
   lesson's `skillId`.
6. **Independence flag (§8)** of a `command_submitted` on skill X — true
   only if all three hold: (a) no `hint_requested` carries its
   `attemptId`; (b) no `ghost_played` that reveals X lies between the
   previous `command_submitted` on X in the same session (or the session
   start) and this entry; (c) no `feedback_shown` on X with `kind`
   `corrective` lies in that same window. So (b) and (c) touch only the
   first entry on X after them — "immediately preceded" in §8. The hint
   counter is never read.
7. **Qualifying success** (for `CONSOLIDATED` and `TRANSFERRED`): a
   `valid`, independent entry in `practice` or `assessment`, or in
   `scenario` for a load-bearing skill only (`CTC`, `ER` — `slice.json`
   `scenario.loadBearingSkills`; LDS §7 Fix 4).
8. **Skill states**, computed on read by one pass over the skill's events
   in stored order (append-only, one recording tab, 07 D47), with the
   provisional numbers from the config file:
   - `INTRODUCED`: a `lesson_completed` or a `ghost_played` that reveals
     the skill. A skill may reach a higher state without it; the state
     shown is the highest reached.
   - `DEMONSTRATED_INDEPENDENT`: one `valid`, independent entry, in any
     context. Once reached it is kept — demotion stops here.
   - `CONSOLIDATED`: the qualifying successes counted since the last
     demotion to `DEMONSTRATED_INDEPENDENT` reach `CONSOLIDATED_COUNT`; for
     `ER`, Error-Recovery Practice (item 9) must also be on record.
   - `TRANSFERRED`: `CONSOLIDATED`, and at least one qualifying success
     since the last demotion from `TRANSFERRED` was in `scenario`. (A
     transferred skill therefore always meets the CONSOLIDATED count, so
     demotion to CONSOLIDATED keeps its meaning — LDS §7 Fix 3–4.)
   - `NEEDS_REINFORCEMENT`: set by an `invalid` entry on a skill at
     `CONSOLIDATED` or `TRANSFERRED` (any context) when it is not already
     active; cleared by the next `valid` entry on that skill (§7: "one
     correct full-checklist attempt" — independence is not required to
     clear it). While it is active, every `invalid` entry on the skill is
     a failed reinforcement attempt; `REINFORCEMENT_FAIL_COUNT` consecutive
     ones demote the skill one level and restart that count:
     `TRANSFERRED` → `CONSOLIDATED` (the scenario evidence must be earned
     again; the modifier stays active), `CONSOLIDATED` →
     `DEMONSTRATED_INDEPENDENT` (the qualifying count restarts at 0; the
     modifier ends).
9. **Error-Recovery Practice on `ER`** (§7, Tier 3): a step attempt on `ER`
   that holds at least one `invalid` `ER` entry with `errorCategory`
   `MANDATORY_MISSING` and ends with a `valid` `ER`. Every refusal at `ER`
   in the slice comes from a missing element that the Verified Reference
   makes mandatory (V-08, V-09, V-10, V-13), so each one counts as meeting
   a verified failure. Any context; the recovering `ER` need not be
   independent; a bypass filing is not a recovery. The scenario path
   "warning, then `SRCTCR`, then `ER`" is one (`slice.json`
   `scenario.expectedBehavior`).
10. **Which hint levels apply** (§8, 07 D38), for the current step:
    *Nudge* applies once the step attempt holds an `invalid` entry, and
    shows `nudge.` + the `errorCategory` of its last `invalid` entry.
    *Partial Reveal* applies only to `ER`, once the step attempt holds a
    refused `ER`; it lists `er.partial.*` for every element missing now.
    *Full Reveal* always applies: `reveal.<SKILL>`; for `CTC` in the
    scenario `scn.reveal.ctc`; for `ER`, `reveal.ER` when an element is
    missing, `reveal.ER.ready` when none is. Levels are given in order
    among those that apply; the bridge refuses a level that does not apply
    and a request that skips one that does. Each accepted request records
    one `hint_requested` — the only place the hint counter grows (§4).
    `ui.hintLabel` shows the number of `hint_requested` events in the
    current session.
11. **Assessment and scenario runs.** Starting one records
    `assessment_started` or `scenario_started` (with `scenarioId`
    `scn-refuses-mobile`) and starts a new run on an empty booking with
    that task's data (`tasks.main` for the assessment, `tasks.scenario` for
    the scenario) and a new `chainId`. Task completion (§6A item 6) records
    `assessment_ended` / `scenario_ended` with `result` `completed`. A run
    **completed with every checklist item met** holds a `valid` `ER`
    followed by a `valid` `FXP` (a failed entry leaves the booking
    unchanged, so a booking filed by a valid `ER` means every earlier step
    was met; a bypass filing is not a valid `ER`). Carry-over
    (`ui.assessment.carryover`): `{N}` = `command_submitted` events and
    `{H}` = `hint_requested` events in the current session before
    `assessment_started`, shown only when either is above 0. No event from
    another session enters an assessment result. Leaving a running
    assessment or scenario inside the app (without closing the browser) is
    §7B item 7 (07 D56): after a confirmation it records
    `assessment_ended` / `scenario_ended` with `result` `abandoned`.
12. **Chain practice** (§7). A practice run gets a `chainId` when it starts
    if all nine required skills are `DEMONSTRATED_INDEPENDENT` or higher at
    that moment. A chain run is **completed unaided** when it holds a
    `valid` `ER` followed by a `valid` `FXP`, and from its first event to
    that `FXP` the session holds no `hint_requested`, no corrective
    `feedback_shown` and no `ghost_played`. `invalid` entries do not void
    it (self-corrected errors, LDS §11). One query lists chain runs with
    this result (§13 "queryable through `chainId`").
13. **Growth / Readiness order** (§10). Checked in this order; the first
    that holds is shown: (1) the empty state — no event other than
    `ghost_played` (Ghost Mode is not evidence, §3); (2) Needs More
    Practice — a skill has `NEEDS_REINFORCEMENT` active, or the last
    assessment that ended `completed` was not completed with every
    checklist item met (abandoned attempts are neither passed nor failed,
    K3, and are skipped); (3) Completed — the §10 conditions, where "the
    assessment completed with every checklist item met" and "the scenario completed" both mean a run
    completed with every checklist item met (item 11; for the scenario,
    `slice.json` `scenario.acceptance`; 07 D59); (4) In Progress. Needs More Practice
    comes before Completed: a current weakness is shown, not hidden.
    `ui.growth.empty` is worded to match (1). "Reset everything" is offered
    whenever the status is not the empty state (07 D41 i).
14. **Interrupted attempts** (§9, K3). The check built in step 1 runs once
    per load, in the recording tab only (07 D47). The bridge reports the
    attempts it marked abandoned during this load, so the screen can show
    `ui.abandoned` once (`{WHAT}` = `ui.what.assessment` or
    `ui.what.scenario`). When the load found an unreadable or other-version
    record and reset it (§11), the bridge reports that too, and the screen
    shows `ui.dataReset` once (07 D53).
15. **One tab at a time** (§11, 07 D47). In a second tab the bridge opens
    the store in a non-recording mode: it writes nothing, runs no
    interrupted-attempt check, and the screen shows only `ui.oneTab.title`
    and `ui.oneTab.body`. After the other tab closes, a reload makes this
    tab the recording tab. How the second tab is detected is Claude Code's
    choice.
16. **Engine inputs** (§6A item 3). The bridge gives the engine: the
    learner's local calendar date (for `{TASK_DATE}`, `{SCN_DATE}`,
    `{DEMO_DATE}` and the `AN` date window, V-01); the current UTC date and
    time (the filed header, `Z`); and, for each `ER`, a fresh record
    locator — six characters A–Z/0–9 from a random source. None of them is
    stored.

## 7B. Rules for build step 4 (07 D54–D59)

**[D] by delegation (07 D29)** — closed while preparing build step 4
(screens), so the build does not have to guess. None adds an event field or
event type (§11), and none claims Amadeus behavior.

1. **The current step** — the skill whose hint levels the DEIXEN panel
   offers (§7A item 10; 07 D38). One function computes it from the current
   run; the screen asks it and never works it out itself. Checked in this
   order; the first that holds decides:
   (a) the task is complete (§6A item 6) → **no current step**: no hint
   level applies and no level is shown; `ui.hintLabel` stays;
   (b) the booking has been filed — by a `valid` `ER` or by a bypass filing
   (§6A item 2) → **`FXP`**: nothing else can change a filed booking (§6A
   item 9);
   (c) the Terminal was opened from a lesson's practice button or from
   Ghost Mode's `ui.ghost.practise`, and no `valid` or `invalid` entry has
   been made since → **that lesson's skill** (`slice.json`
   `lessonCommon.practiceBridge`: "step = the lesson's skill"; `L10-FQD`:
   `FQD`);
   (d) the run's last entry whose `result` is `valid` or `invalid` was
   `invalid`, on skill X → **X**. So after a refused `ER` the current step
   is `ER` even while `TK` is missing — where the approved design offers
   Partial Reveal (`P1-04b`; `P1-E` "Hint shown") and what `reveal.ER`
   ("… Missing now: {MISSING_LIST}") and `er.partial.*` are written for;
   (e) otherwise → **the first skill in path order** `AN`, `SS`, `NM`,
   `AP`, `CTC`, `TK`, `RF`, `ER` with no `valid` entry in the run (before
   filing this always finds one, since a `valid` `ER` files the booking).
   `out_of_scope` entries (§7A item 3) never move the current step. `FQD`
   is the current step only through (c) or (d): it is optional (§7). An
   accepted hint request is recorded on the current step's open step
   attempt (§7A item 2), so this rule also decides which later entry the
   hint counts against.
   *Why not path order alone:* after a refused `ER` with `TK` missing it
   would name `TK`, so Partial Reveal (`ER` only) could never be offered
   where the design and `er.partial.*` need it; and a learner who has just
   typed a wrong `TK` would get hints for a different step.
2. **Hint levels on the screen.** For the current step the panel shows
   Nudge, Partial Reveal — only when the current step is `ER`; outside `ER`
   it is not shown at all (07 D38) — and Full Reveal. Each shown level is
   in one of three states, taken from the bridge: **shown** (requested in
   the current step's open step attempt: pressed, its text stays visible,
   07 D38); **available** (the next level, in order, that applies and has
   not been shown, §7A item 10: enabled); **not available** (every other:
   disabled, the `P1-F-Controls` disabled style). So a step with no wrong
   entry yet shows Nudge disabled and Full Reveal available. The text of a
   shown level is kept by the screen, in memory, for that step attempt — it
   is not an event (§7A item 4) — so it comes back when the learner returns
   to that step while its attempt is open, and goes when the attempt
   closes. Each approved frame shows one moment: where a frame's enabled
   and disabled levels differ from this rule (`P1-04a` shows Nudge enabled
   just after a valid `NM` — drawn before §7A item 10; `P1-05` shows no
   Partial Reveal after a refused `ER`), this rule wins (§2 "What a frame
   is").
3. **The entry field** (07 D48, Karim in build session 2: the field shows
   typing in uppercase; the engine never rewrites an entry). Letters are
   turned into capitals **as they are typed**, in the field's own value, so
   what the learner sees is exactly what is sent to the engine and stored
   as `command` — never a lowercase entry shown as capitals. Nothing else
   is changed (no spaces removed or added).
4. **Build step 4 is built in two parts.** **4A:** the app shell (header
   with lockup B, the five-area navigation, the phone header and menu
   sheet, the language switch; English/LTR and Arabic/RTL), the load
   notices (`ui.oneTab.*`, `ui.abandoned`, `ui.dataReset`, §7A items
   14–15), and the `TERMINAL_PRACTICE` screen with the DEIXEN panel, wired
   to the bridge, at every breakpoint in both languages. **4B:** the other
   seven states (§3). Until 4B, a control that leads to a state not yet
   built (the other areas in the navigation, Start assessment) is drawn as
   in the boards but disabled, and the report lists each one; "no false
   affordance" (§13) is checked when 4B is done. Coach texts (`coach.*`)
   come at build step 5 (Coach): in 4A the panel shows no Coach block.
5. **Where the load notices appear** (no board draws them; 07 D47 says to
   use the design's existing tokens and patterns). A second tab shows only
   `ui.oneTab.title` and `ui.oneTab.body` (§7A item 15). `ui.abandoned` and
   `ui.dataReset` are shown once per load, on the first screen shown, in
   the DEIXEN voice, with existing role tokens and patterns only, never
   covering the Terminal entry line. No control is required; any control
   added must work.
6. **"Booking as it stands" in the DEIXEN panel** (07 D55, app I-15; the
   boards draw only the name and the segment). The list holds the elements
   the Terminal would display at that moment, in the same order, each with
   its number from the one numbering function (§4) and `ui.pnr.new` /
   `ui.pnr.was` as it changes. It never shows a second form of an element:
   - name → the name as displayed (`ALHARBI/SAAD MR`); segment → airline
     and flight number (`6X 403`), as drawn in `P1-04a` and `P1-E`;
   - `AP` → the element text as displayed (`AP 966110000000`);
   - `TK` → the verified form `TK OK` + date + `/` + office (V-18);
   - stored `SSR CTCM` → `SSR CTCM` only: the next field, the airline code,
     is the partly verified detail U-07, so the panel stops before it and
     carries no marker;
   - stored `SRCTCR` (U-07) and `RF` before end of transaction (U-08), which
     the Terminal shows as training messages → **no number**; the first
     sentence of that training message (the same text the Terminal shows,
     §5 D34 split), labeled `ui.trainingLabel`; `ui.pnr.new` may apply,
     `ui.pnr.was` never;
   - after filing, `RF` is not listed (V-10), as in the filed display.
7. **Leaving a running assessment or scenario inside the app** (07 D56).
   Every way the app itself offers to leave the running screen — an area
   link, the wordmark, the phone menu's Scope Disclosure link, and the
   browser's Back button if the app keeps browser history — first shows a
   confirmation: `ui.leave.assessment` or `ui.leave.scenario`, with
   `ui.leave.stay` (focus starts here) and `ui.leave.confirm`. Leave
   records `assessment_ended` / `scenario_ended` with `result` `abandoned`
   (no new field), ends the run, then goes where the learner chose; Stay
   changes nothing. Not leaving: the language switch; opening or closing
   the phone menu, the DEIXEN drawer or the brief; the link to the area the
   learner is already in. After task completion the attempt has ended
   (§7A item 11) and nothing is asked. Layout: the reset confirmation's
   pattern (`P1-08`) with existing tokens and control styles; the
   reset-action style stays reserved for Reset everything (`P1-F`). Area
   links stay enabled (`P1-F`: "never disabled").
8. **Storage refused** (07 D55, app I-13). When the browser does not let
   the app read or write `localStorage`, the screen shows only
   `ui.noStorage.title` and `ui.noStorage.body`, like the second-tab
   notice (§7A item 15), and nothing is recorded. If a save fails later in
   the load, the same notice replaces the screen: nothing is ever shown as
   recorded that was not written.
9. **The name as a word** (07 D55, app I-14). Every place the name DEIXEN
   stands alone as a word, and the wordmark's accessible name, use
   `ui.brand.name`. Strings that contain the name inside a sentence keep
   it there. The drawn wordmark (lockup B) is a drawing, not text. The name
   is provisional (Constitution §1), so it lives in one place.
10. **Behaviours over time** that no single frame shows (07 D55; app
    `docs/DECISIONS.md` T7) — where a new entry lands, when the brief
    folds, which notes stay in the panel, the scroll position — are the
    builder's choices (§2 "What a frame is"), with two guards: the app
    never scrolls the entry line, or the first line of the newest response,
    out of view; and the panel keeps the newest entry's feedback notes plus
    those of the wrong entries just before it on the same step. A shown
    hint level follows item 2.
11. **The Flight Deck's one recommended action** (07 D57; §3; LDS §23;
    07 D40; `P1-01`). Computed from the evidence when the Flight Deck is
    shown, never stored (§10). The first that holds decides; the nine
    required skills are `AN`, `SS`, `NM`, `AP`, `CTC`, `TK`, `RF`, `ER`,
    `FXP` in that order (`FQD` is never recommended):
    (a) a required skill has `NEEDS_REINFORCEMENT` active → the first such
    skill: its chain row carries `ui.chain.next`, and the action is
    `ui.lesson.practise` (`{CMD}` = the command shown in that row), which
    opens the Terminal from that skill's lesson (item 12; item 1 (c));
    (b) a required skill is below `DEMONSTRATED_INDEPENDENT` → the first
    such skill: its row carries `ui.chain.next`, the action is
    `ui.lesson.start` (`{N}` = its lesson number), which opens that lesson
    (a fresh learner gets lesson 1, §3);
    (c) the last assessment that ended `completed` was not completed with
    every checklist item met, or none has → `ui.term.startAssessment`
    (item 15);
    (d) no scenario run has been completed with every checklist item met
    (§7A item 11; 07 D59) →
    `ui.fd.openScenario`;
    (e) otherwise → `ui.fd.openGrowth`.
    Exactly one action on the screen has the primary-button style (`P1-F`).
    In (a) and (b) it sits in the Next row as drawn; in (c)–(e) no row
    carries Next, and the action takes that place under the chain, with
    existing patterns only. The chain's status words stay as 07 D40 says, except that the word for a step at DEMONSTRATED_INDEPENDENT or higher is `ui.doneOnYourOwn` "Done on your own", in interface text, not green (07 D69 F-04 (A), which amends D40; 07 D76) (the scenario and assessment rows: item 19).
12. **The practice run when the learner moves between screens** (07 D57;
    §7A item 1). A practice run lives for the load: leaving the Terminal
    and coming back in the same load shows the same run, booking, record
    and panel (hint texts: item 2). A lesson's practice button
    (`ui.lesson.practise`) or Ghost Mode's `ui.ghost.practise` opens the
    Terminal with item 1 (c) set, and first starts a **new** practice run
    on an empty booking (`startPractice()`, app I-12) when the current
    run's task is complete (§6A item 6) or the lesson's skill already has a
    `valid` entry in the current run; otherwise it continues the current
    run. After an assessment or the scenario has ended, the Terminal area
    link and these buttons lead back to practice through `startPractice()`
    (§7A item 1).
13. **Learning** (07 D57; LDS §23 "Revisit"). No lesson is locked:
    `prerequisiteLessonIds` gives the order, not a lock; all ten lessons
    are reachable from the lesson strip (`P1-02`). The Learning area opens
    the lesson item 11 recommends in (a) or (b), otherwise lesson 1.
    `lesson_completed` follows `slice.json` `lessonCommon.completionRule`.
14. **Ghost Mode** (07 D57; §7A item 5). Each start of a script, including
    each Replay, records one `ghost_played`; Pause and resume record
    nothing. Scripts run on the demo booking in their own sandbox and never
    touch the practice run.
15. **When the scenario and the assessment start** (07 D57). The Scenario
    Bank area opens the scenario screen (`P1-06`: Scenario Bank is the
    current area) not yet started: brief, objective, constraints, an empty
    Terminal. `scenario_started` (§7A item 11) is recorded at the learner's
    first entry or first accepted hint on that screen, which then belong to
    the scenario run; until then nothing is recorded, and leaving asks
    nothing (item 7 applies only to a running scenario). The assessment
    starts when `ui.term.startAssessment` is pressed: `assessment_started`
    is recorded and the announcement shows (`ui.assessment.starts`,
    `ui.assessment.intro`, `ui.assessment.carryover` when it applies; on
    phones closed with `ui.assessment.continue`, `P1-05`). After either has
    ended, returning to the Scenario Bank shows a new, not-yet-started
    scenario screen, and Start assessment starts a new assessment.
16. **The way into Ghost Mode** (07 D58, app I-17; no board draws one).
    Each lesson page carries a link to that lesson's Ghost Mode script,
    worded `ui.ghost.title` with the script's commands, in the existing
    link pattern. No new words or patterns.
17. **Ghost typing speed** (07 D58, app I-18). Every keystroke of a script
    takes `--motion-demo-key` and each display is held for
    `--motion-demo-hold` (`tokens.css`, 07 D42). Under reduced motion
    `--motion-demo-key` is 0, so each entry appears whole at once, and
    `--motion-demo-hold` stays: it is a still pause for reading each
    display, not motion (07 D64, app I-23; corrects the earlier "both 0",
    which `tokens.css` never said). The `charDelayMs` / `durationMs` fields of the file 06 schema,
    and the speeds once written in the `slice.json` note, are not used in
    this slice.
18. **"In your task" on a lesson** (07 D58, app I-16). Shows the whole
    `task.brief`, words unchanged; the board's one-fact line is one moment
    of it. A per-lesson fact would need new content keys.
19. **The scenario and assessment rows** on the Flight Deck and in Growth
    (07 D59; refines 07 D40). Each shows `ui.growth.completed` only when a
    run of that kind has been completed with every checklist item met
    (§7A item 11); otherwise a dash. A run that ended `completed` with a
    bypass filing stays recorded as `completed` and is not shown as
    Completed.
20. **The assessment and scenario screens** (07 D59; `P1-05`, `P1-06`).
    - Both hold the same Terminal and DEIXEN panel as practice, with the
      hint label and the hint levels (item 2); neither has Reset task
      (07 D37) or Start assessment.
    - **Areas.** `TERMINAL_ASSESSMENT` is in the Terminal area (`P1-05`);
      `SCENARIO_SESSION` is in the Scenario Bank (`P1-06`). While one is
      running, the link to its own area is "the area the learner is
      already in" (item 7): nothing is asked and nothing changes.
    - **The end of an assessment.** At task completion the DEIXEN panel
      shows one note, once: `ui.assessment.result` when the run is
      completed with every checklist item met, otherwise
      `ui.assessment.resultUnmet`. Never in the Terminal (07 D30). On
      phones the DEIXEN drawer opens itself for it, as for the
      announcement, and closes with `ui.assessment.continue`. The note is
      not an event.
    - **Practice buttons** can be pressed only on a screen reached by
      leaving (item 7), so the attempt has already ended; the bridge's
      refusal of them while an attempt runs stays as a guard.

## 7C. Rules for build step 5 — Coach (07 D61)

**[D] by delegation (07 D29)** — closed while preparing build step 5
(Coach; app I-21), so the build does not have to guess. No event field or
event type is added (§11); Coach texts are not events (§7A item 4); nothing
about Amadeus is claimed beyond the Verified Reference. What stays as it
is: feedback texts, hints and "Booking as it stands" keep their own labels
and rules (§5, §7B items 2, 6, 10); Coach adds to them, it replaces none.

1. **What Coach is in the slice.** Three things, all bound to the learner's
   recorded state (06 "state binding"), all in the DEIXEN panel or on the
   Growth screen, never in the Terminal (07 D30):
   (a) **explanations beside Amadeus output** — the plain-language
   explanation file 06 places "alongside" a verified message (§5 kind 3):
   `coach.needTk`, `coach.missingCtc`, `coach.bypassRecorded`,
   `coach.erDone`, `coach.fxpDone`;
   (b) **the escalation offer** — `coach.escalate` with the link
   `ui.coach.openLesson` (item 7);
   (c) **the Growth note** — `coach.growth.reinforce`,
   `coach.growth.assessmentUnmet` (item 8).
   Every Coach text sits under the label `ui.panel.coach`.
2. **When each explanation shows** — with the entry that produced the
   output, in every mode (practice, assessment, scenario):

   | Engine result for the entry | Coach text |
   |---|---|
   | `ER` refused, the Terminal shows `NEED TICKETING ARRANGEMENT` (V-09) | `coach.needTk` |
   | `ER` refused, the Terminal shows the V-13 warning | `coach.missingCtc` |
   | `ER` files the booking through the V-13 bypass (§6A item 2) | `coach.bypassRecorded` |
   | `ER` valid: the booking is filed and redisplayed with its record locator (V-18) | `coach.erDone` |
   | `FXP` valid: the pricing display (V-05, V-17), before or after `ER` | `coach.fxpDone` |

   No other entry has a Coach explanation. `ER` refused for any other
   reason (`tm.rfMissing`, `tm.otherMissing`) has none: those are training
   messages, not verified output. Each text is VERIFIED: V-09, V-13, V-13,
   V-18, V-05.
3. **Coach and independence** (open since 07 D52). The §8 test was applied
   to every Coach text: none of them, with the checklist item, lets the
   learner type the correct entry without further trial. `coach.needTk`
   and `coach.missingCtc` name the missing element and restate what the
   verified message itself shows, like the diagnostic `er.partial.*`; they
   do not name the entry, and `coach.missingCtc` does not say which of the
   three forms fits the passenger (that is what makes the scenario's
   `scn.fb.warningShown` corrective — it is shown at the same moment and
   recorded as usual). `coach.bypassRecorded`, `coach.erDone` and
   `coach.fxpDone` explain an output that has already happened and say
   nothing about what to type next (after the first two, no entry on `ER`
   can change the filed booking, §6A item 9).
   `coach.escalate` and the Growth note say nothing about the entry. So
   every Coach text is **diagnostic**: it does not affect independence, and
   §7A item 4 holds unchanged ("Coach explanations are not events"). **Rule
   for later content:** a Coach text that would pass the corrective test
   must be authored as a feedback item with `kind` `corrective` (recorded
   as `feedback_shown`), never as a `coach.*` string (LDS §13: corrective
   content from any channel excludes the next success).
4. **Where it shows.**
   - Desktop and 768: in the DEIXEN panel, in the entry's notes, after its
     feedback note (if any): the label `ui.panel.coach`, the entry echo,
     the text — as `P1-04b` and `P1-E` draw it. Existing tokens and
     patterns only.
   - Phones: in the DEIXEN drawer, in the same place. **Coach never opens
     the drawer by itself.** The drawer's existing "new" mark on the
     DEIXEN button (`ui.pnr.new`) tells the learner a note is waiting. The
     drawer opens by itself only for the two moments that already do: the
     assessment announcement and the end-of-assessment note (§7B items 15,
     20). When the end note opens it, the end note comes first, then the
     completing entry's notes (including `coach.fxpDone`).
   - A Coach text belongs to its entry and follows the notes rule of §7B
     item 10: it stays while that entry's notes stay, and goes with them.
   - Shown with the output, not on request. File 06 places the explanation
     alongside the verified message, and the approved design draws it so
     (`P1-04b`, `P1-E`; `P2-Issues` answer 07: Coach appears only with a
     coach string). §8's "learner-initiated by default" governs help beyond
     that: hints stay learner-requested, and the escalation offer is the
     one help that comes without a request.
5. **In the assessment and the scenario** (app I-21 item 1). The
   explanations of item 2 show exactly as in practice. File 06 names the
   Assessment and the Scenario as Coach touchpoints; each explanation is
   diagnostic (item 3) and says what the real message means, as the
   diagnostic feedback texts already shown there do. The announcement's
   "on your own" (`ui.assessment.intro`) does not mean without help: the
   same text says hints stay available and are counted (07 Assessment
   contract; `P2-Issues` answer 06). Nothing in this item changes how the
   assessment result, the hint label, independence or the evidence are
   computed. **Not shown while an assessment or the scenario runs:** the
   escalation offer (item 7) — its link would leave the attempt (§7B item
   7); errors made there still count toward it (item 7).
6. **The bypass** (app I-21 item 2). At a bypass filing the entry's notes
   hold its feedback note (`er.fb.bypassed` in practice and the
   assessment, `scn.fb.bypassed` in the scenario — the judgment: the step
   does not count) and then `coach.bypassRecorded` (the explanation: what
   the second `ER` did in Amadeus, V-13), as §6A item 2 says. The one
   repeated clause is accepted: the two notes have different jobs. In the
   assessment, `ui.assessment.resultUnmet` belongs to the completing `FXP`
   entry, a different entry on a different step, so by §7B item 10 it
   never stands beside the bypass notes. In practice, a bypass is an
   `invalid` `ER` entry like any other, so once its count has reached
   `ESCALATION_ERROR_COUNT` the escalation offer (item 7) follows the two
   bypass notes, under the same Coach head (07 D62, app I-22).
7. **The escalation offer** (§8; LDS §13, §15; open since 07 D53).
   - **The count:** `command_submitted` events with `result` `invalid`,
     the same `skillId` and the same `errorCategory`, in the current
     session (`sessionId`, one app load), in any context — practice,
     assessment and scenario errors all count. `out_of_scope` entries are
     not errors (§7A item 3) and never count. Computed from the events when
     needed, never stored (§11).
   - **When it shows:** with an `invalid` entry in `TERMINAL_PRACTICE`
     whose (skill, category) count, this entry included, has reached
     `ESCALATION_ERROR_COUNT` (config file, provisional), and with every
     later `invalid` entry of the same skill and category in the session.
     `{N}` = that count.
   - **Suppressed** when the skill's state just **before** this entry is
     `CONSOLIDATED` or `TRANSFERRED` and `NEEDS_REINFORCEMENT` is not active
     (§8; LDS §15). Read before the entry, because an error on such a skill
     itself sets `NEEDS_REINFORCEMENT` (§7A item 8), so a state read after
     it would never suppress. From the next `invalid` entry on, the modifier
     is active and the offer can show. Never shown while an assessment or
     the scenario runs (item 5).
   - **What it holds:** `coach.escalate`, then the link
     `ui.coach.openLesson` (`{N}` = the lesson number of that skill,
     `L01`…`L10`), in the existing link pattern. It opens that lesson; the
     practice run continues (§7B item 12). There is no "No" control:
     declining is simply typing on. Opening the lesson records nothing
     (`lesson_completed` follows its own rule, `slice.json`
     `lessonCommon.completionRule`).
8. **The Growth note** (06: Growth "explain meaningful outcomes and connect
   them to evidence"). Found while preparing step 5: when the status is
   Needs More Practice because a skill has `NEEDS_REINFORCEMENT` active,
   every chain row can still read "Done on your own" (07 D40, D76: the row
   follows the skill's state, which the modifier does not lower), so
   nothing on Growth said why. Rule: when Growth shows Needs More Practice
   (§7A item 13 (2)), a Coach note under the status and `ui.growth.basis`
   says why, one sentence for each reason that holds, in this order:
   `coach.growth.reinforce` (`{COMMANDS}` = the commands of the skills
   with `NEEDS_REINFORCEMENT` active — each as its chain row shows it, as
   in §7B item 11 (a) — in path order, `FQD` last, joined as in
   `slice.json` `rules`); `coach.growth.assessmentUnmet` (the last
   assessment that ended `completed` was not completed with every
   checklist item met). Label `ui.panel.coach`, DEIXEN's voice, existing
   patterns and tokens, no control (the Flight Deck carries the next
   action, §7B item 11). Not shown for the other statuses. Computed at
   display time; not an event.
9. **The five touchpoints** (06; 07 D9) — where each one is in the slice:

   | Touchpoint | Screen and moment | What serves it |
   |---|---|---|
   | Learning | `LEARNING`: when a lesson is opened | The Learning area opens the recommended lesson (§7B item 13); the lesson's explanation and "In your task" (§7B item 18); its practice button and Ghost Mode link as next steps; and the escalation offer, which brings a learner back to the lesson of the step they are struggling with (item 7). No Coach note on the lesson page itself: no approved Coach text is written for it |
   | Terminal / Practice | `TERMINAL_PRACTICE`: with each entry | Item 2 explanations; item 7 offer; with the feedback texts and hints (§5, §7B item 2) |
   | Scenario | `SCENARIO_SESSION`: with each entry | Item 2 explanations (the V-13 warning with `scn.fb.warningShown`; the bypass with `scn.fb.bypassed`); no escalation offer (item 5) |
   | Assessment | `TERMINAL_ASSESSMENT`: with each entry, and at its end | Item 2 explanations; the announcement and the end note stay as §7B items 15 and 20 say; hints counted and labelled honestly; no escalation offer (item 5) |
   | Growth / Readiness | `GROWTH_READINESS`: when shown | The status and `ui.growth.basis`; the chain rows; the item 8 note when the status is Needs More Practice |

10. **Strings** (07 D61): new `ui.coach.openLesson`,
    `coach.growth.reinforce`, `coach.growth.assessmentUnmet`;
    `coach.escalate` reworded without count-noun agreement (as 07 D39),
    because `{N}` can now pass ten, where the Arabic «{N} مرات» is wrong;
    meaning unchanged. 220 keys in each string file (226 since 07 D76).

## 7D. Rules for build steps 6 and 7 — the check and the pass (07 D63)

**[D] by delegation (07 D29)** — closed while preparing build steps 6
(scenario and assessment, checked with Coach in place) and 7 (localization,
accessibility and breakpoint pass), so neither has to guess. No event field,
event type, string or token is added; nothing about Amadeus is claimed; no
rule changes what the assessment, a scenario run or any evidence means
(Constitution §8). Both steps add **checks and fixes**, not behaviour: a
defect found is fixed with a test that would have caught it; a fix that
would need a new string, token, event field or a changed rule is a stop
(`CLAUDE.md` §6).

1. **Build step 6 is a check, not new work.** The assessment and the
   scenario were built in 4B-2 (07 D60) and Coach in step 5 (07 D62). Step 6
   walks both end to end with Coach in place and proves each §13 line that
   concerns them on the built app: the announced entry and carry-over; the
   honest hint label; no cross-session merging; the end note (`result` /
   `resultUnmet`); the scenario's differentiating condition and
   scenario-aware feedback; `TRANSFERRED` only for `CTC` and `ER`, from
   independent scenario successes; one hint-adjacent and one
   corrective-feedback-adjacent success excluded from independence; one
   Error-Recovery Practice on `ER`; chain runs read through `chainId`; and
   that Coach changed none of these (same events, same results). The result
   is a **Definition of Done trace**: every §13 line, the tests that prove
   it (by file and name), and what was seen in the built app.
2. **The end of an assessment in view.** At every width, when an assessment
   ends, its end note (§7B item 20) is in view without the learner
   scrolling, and it is announced (`role="status"`). Phones: as built — the
   drawer opens itself, the end note first (§7C item 4). 768 and desktop:
   the end note may stay after the completing entry's notes (the order
   built), but the newest-into-view rule of the scrolling notes (07 D62 (b))
   includes it.
3. **The scrolling notes block (1024–1440; 07 D62).** While it scrolls and
   is a keyboard stop, it is a named region: `role="region"`, named by the
   visible head of the newest entry's notes (`aria-labelledby`; for example
   "Feedback ER" or "Coach ER") — existing words only. It shows the same
   visible focus as every other stop; arrow keys and Page Up/Down scroll
   it; Tab reaches the link inside it (the escalation offer); it is not a
   stop when it does not scroll. New notes are announced once: the polite
   live region keeps earlier notes' elements in place when a new entry
   arrives, so a screen reader is told only what was added.
4. **The phone drawer (07 D62: the offer below the fold at 320 px).** Coach
   still never opens the drawer (§7C item 4). When the learner opens it,
   the drawer starts scrolled so the head of the newest entry's notes is at
   its top (all of them when they fit), so the escalation offer is either in
   view or directly below, reached by scrolling and by Tab inside the drawer.
   Nothing in the drawer changes order (§7C item 4 still decides the end of
   an assessment).
5. **What "the accessibility baseline passes" means here** (file 04; WCAG
   2.1 AA). All of these, on every state of §3, in both languages:
   (a) the automated WCAG 2.0/2.1 A and AA check, at all eight widths, with
   every overlay open once (phone menu, DEIXEN drawer, leave question,
   reset confirmation, load notices, the second-tab and storage notices);
   (b) keyboard only: every control reached and used; a visible focus on
   each; no trap except the modal question, where Tab stays inside and
   Escape is Stay; focus order follows the visual reading order;
   (c) touch targets at phone widths and 768: every control at least
   `--layout-target` high and wide, except the dense secondary controls,
   which are at least `--layout-target-dense` (listed by name in the app's
   `docs/DECISIONS.md`); links inside running text are exempt and named;
   (d) reduced motion: under `prefers-reduced-motion: reduce` every motion
   token that drives an animation or a transition resolves to 0 and nothing
   animates (the proof mark, the drawer, Ghost Mode's typing);
   `--motion-demo-hold`, the still pause between Ghost Mode displays, stays
   as `tokens.css` sets it (07 D64, app I-23);
   (e) text spacing (WCAG 1.4.12): with line height 1.5, paragraph spacing
   2 × size, letter spacing 0.12 em and word spacing 0.16 em applied, no
   text is cut off and no control is covered, at 1440 and 390 — Terminal
   lines still never wrap (07 D36) and may pan, but nothing is lost;
   (f) zoom and reflow (WCAG 1.4.4, 1.4.10): the widths between the eight —
   480, 640 and 900 — also show no page-level horizontal scroll and keep
   the entry line in view (1280 at 200 % is 640; 1280 at 400 % is 320);
   (g) non-text contrast: the focus indicators and the marker bracket at
   least 3:1 against what is beside them, computed from the rendered
   colours;
   (h) names and roles: every control's accessible name comes from the
   string files; the language switch keeps its radio roles.
6. **The localization pass.** On every state, both languages: no missing
   key; no English word on an Arabic screen except the allowed ones —
   commands and codes, Amadeus output, `ui.brand.name`, "Amadeus" inside a
   string, the language name `ui.lang.en`, and the English terms the
   approved Arabic content itself writes (glosses such as «البيع المختصر
   (short sell)», the PRINT element names, "Received From", "fare basis",
   and key names such as "Enter" — 07 D64, app I-24); interface right-to-left,
   Terminal and commands left-to-right (07 D32); arrows and other
   directional signs mirror, non-directional ones do not; digits written as
   the approved Arabic boards write them, the same way everywhere (if the
   boards themselves disagree, stop and ask); no clipped or broken word with
   the real fonts at any width (screenshot review).
7. **The breakpoint pass.** Every state × 320 / 360 / 390 / 430 / 768 /
   1024 / 1280 / 1440 × both languages, at the boards' heights (and 320 ×
   568): no page-level horizontal scroll; the entry line in view; the
   Terminal workspace never given up (spec §2); screenshots kept and
   compared by eye with the board for that state and width where one exists.
8. **Identity and values.** A test shows the header wordmark is lockup B at
   every width (the field line, no ticks; size from the `--wordmark-cap*`
   tokens; name `ui.brand.name`); the no-raw-value and string-file tests
   run again over all of `src/ui/`.
9. **The Amadeus-string trace** (`CLAUDE.md` §8) runs again over the engine,
   the screens and the Coach texts, and its result is reported.
10. **What automated checks cannot prove** is written down, not implied.
    The pass saves the accessibility tree of each state in both languages
    (text files in `docs/a11y/`) so the reading order can be read without a
    screen reader. Still not proven by any test: how a screen reader
    actually speaks the app; whether reading order is meaningful beyond the
    tree; whether the Arabic reads naturally; touch on a real phone; the
    fonts on the learner's own computer. Karim's learner test covers what a
    sighted learner meets (07 D29 item 5); screen-reader use stays an open,
    disclosed item.

## 8. Independence, hints and feedback

**[D on approval — LDS §7 Fix 2, §13, §15; LXA §11]**

- **Hint levels, one counter:** Nudge (error category only; diagnostic) →
  Partial Reveal (which checklist item is unmet, Tier 3 only; diagnostic) →
  Full Reveal (the fix; corrective). Each is learner-requested and
  increments the one counter. **[D] (07 D38)** Offered in this order for
  the current step (§7B item 1); a shown level stays visible; Partial Reveal is not shown
  outside `ER`.
- **Every feedback text is authored as `diagnostic` or `corrective`.** Test:
  if the text plus the checklist item lets the learner type the correct
  command without further trial, it is corrective.
- **Independence flag** (Calculated, per attempt; exact rule §7A item 6) is true only if: no hint
  was used on this attempt; no same-command Ghost Mode reveal immediately
  preceded it; and the immediately preceding feedback on this skill was not
  corrective. It is **not** the hint counter and never changes it.
- **[D] Saying why a valid entry does not count (07 D69 F-04 (B); 07
  D76).** The flag and its reasons come from one function (§7A item 6:
  `hint`, `demonstration`, `correctiveFeedback`, in that order); the bridge
  gives them with each learner entry (`ownWork`: for a `valid` entry
  `{ counts, reasons }`, otherwise none). After a `valid` entry that does not
  count, the panel shows one note under that entry's "Correct in DEIXEN"
  head: `ind.notCounted`, one sentence per reason (`ind.hint`, `ind.demo`,
  `ind.feedback`), then `ind.normal` (`slice.json` `independenceNotes`). It
  is part of that entry's notes (§7B item 10), never in the Terminal, never
  recorded, and never opens the phone drawer. Nothing is said before an
  entry, and nothing says how to make an entry count (07 D69 F-07).
- **Escalation:** after `ESCALATION_ERROR_COUNT` same-category errors on a
  skill in one session, Coach *offers* the lesson link; suppressed once the
  skill is CONSOLIDATED unless NEEDS_REINFORCEMENT is active. Exact rule: §7C
  item 7 (07 D61).
- **Coach (06, LXA §11):** learner-initiated by default; bound to real
  state; present at the five touchpoints; tone describes the unmet
  condition, never blames (LDS Principle 7); presents Amadeus behavior as
  fact only if VERIFIED. Mobile: collapsed/on-demand (LXA §18). Layout
  (global vs per-page) is the builder's choice within these rules.
  **[D] (07 D61)** Exact rules: §7C — explanations beside verified output
  are shown with it (06 "alongside"; §7C item 4); every Coach text in the
  slice is diagnostic and not an event (§7C item 3); on phones Coach never
  opens the drawer by itself.

## 9. Scenario and assessment

**[D] Scenario contract (07):** one scenario that changes at least one real
operational condition, observable in evidence; with Objective, Constraints,
Expected behavior, scenario-aware Feedback, Assessment linkage, Evidence
linkage, and no hidden global state change. Only VERIFIED behavior.

**[D] The scenario (07 D25, K2).** "The passenger refuses to share
a mobile number." Differentiating condition: the learner must record the
refusal with `SRCTCR` (V-13: `SRCTCR-REFUSED/P3`) instead of `SRCTCM`.
Load-bearing skills: passenger contact SSR (row 5), `ER`. Why this one: it is
verified end to end, it changes what the learner types, and a professional
agent meets it in real work (IATA 830d). Alternative: a customer who wants a
specific airline (carrier-preferred `AN`, V-02).

**[D] Assessment (07 Assessment contract; LDS §20):** one formal assessment
= the full path in `TERMINAL_ASSESSMENT`. Entry announced; no history/hint
wipe on entry; no merging with earlier sessions; carry-over disclosed when
present; hint label shows the real count. Reported only as "the pipeline
works end to end for this learner on this occasion" — never a general
competence claim.

**[D] Interrupted assessment or scenario (07 D25, K3).** If the
browser closes mid-attempt, the attempt is recorded as abandoned (not
passed, not failed) and the learner is told so on return. Resolves LXA
open items 1–2. Leaving one inside the app: §7B item 7 (07 D56) — the
learner is told first and may stay; leaving records it as abandoned.

## 10. Growth / Readiness

**[D]** One qualitative status (order of the rules: §7A item 13), computed from evidence at display time,
never stored as a separate number (LDS §29 item 3; 07 Evidence contract).

**[D] Status rule (07 D25, K4):**

| Status | Rule |
|---|---|
| Completed | All nine required skills DEMONSTRATED_INDEPENDENT or higher, **and** the assessment completed with every checklist item met, **and** the scenario completed with every checklist item met (§7A item 11; 07 D59) |
| Needs More Practice | Any skill has NEEDS_REINFORCEMENT active, **or** the last assessment attempt ended with unmet checklist items |
| In Progress | Any other state with at least one Recorded event |
| (empty state) | No evidence yet — shown honestly, no placeholder score |

## 11. Evidence and state schema

**[DELEGATED — file 13 "Evidence/State concrete schema"]** Starts from the
historical four-field Event Log (type, command, result, timestamp — 03) and
adds only what a named requirement needs. This build is new (07 D14), so the
open Event Log questions (LDS §21, §36; LXA §17) are answered by design, not
by inspection.

**Storage:** one `localStorage` key `deixen.state`:
`{ schemaVersion: 1, events: Event[] }`. Only Recorded events are stored;
everything Calculated (skill states, independence, status) is derived when
read (03; LDS §29 item 3). Version mismatch or unreadable data → full reset
(03).

**Event fields:**

| Field | Why it is needed |
|---|---|
| `id` | Unique reference |
| `type` | Historical field (03) — see event types below |
| `command` | Historical field — the literal learner entry |
| `result` | Historical field — `valid` / `invalid` / `out_of_scope`; on `assessment_ended` and `scenario_ended`: `completed` / `abandoned` (07 D46) |
| `timestamp` | Historical field — ISO 8601 **with milliseconds**; with `seq` answers the granularity question (LDS §21) |
| `seq` | Strict order within a session, so "immediately preceding" is exact even if two events share a timestamp |
| `sessionId` | Assessment contract (no cross-session merging); session = one app load until unload **[DELEGATED; resolves LXA open item 3]** |
| `attemptId` | Groups hint/feedback events with the attempt they belong to — needed for the independence flag. One step attempt (§7A item 2) |
| `skillId` | Which skill the attempt belongs to |
| `context` | `practice` / `assessment` / `scenario` — assessment and transfer rules |
| `chainId` | Set during chain practice, assessment and scenario runs; answers chain-continuity (LDS §29 item 5; LXA open item 5) |
| `errorCategory` | One of the 8 categories, when invalid |
| `checklist` | Map of checklist item → pass/fail (LDS §6) |
| `hintLevel` | On `hint_requested`: `nudge` / `partial` / `full` |
| `feedbackKind` | On `feedback_shown`: `diagnostic` / `corrective` |
| `scenarioId` | On scenario events |

**Event types:** `lesson_completed`, `ghost_played`, `command_submitted`,
`hint_requested`, `feedback_shown`, `assessment_started`,
`assessment_ended` (completed/abandoned), `scenario_started`,
`scenario_ended` (completed/abandoned). A confirmed reset clears storage
entirely and records nothing (LXA §8.8).

**One tab at a time (07 D47):** the first open DEIXEN tab keeps the
record. A tab opened while another is open records nothing, runs no
interrupted-attempt check, and shows only the `ui.oneTab.*` notice; after
the other tab closes, a reload makes it the recording tab.

**Engine boundary (03 historical precedent):** the command simulator is pure
logic with no knowledge of storage; one thin bridge calls it and writes the
event.

## 12. Open items before and during the build

**Karim decisions — all four approved 2026-09-25 (07 Decision 25); their tags above now read [D]:**

| # | Item | Claude's recommendation |
|---|---|---|
| K1 | Slice limits: 1 adult, 1 segment, single fare | Agree |
| K2 | The scenario: passenger refuses mobile → `SRCTCR` | Agree |
| K3 | Interrupted assessment/scenario → recorded as abandoned | Agree |
| K4 | Growth status rule (§10) | Agree |

**Gaps Claude closes before the build (Readiness check 3.6) — all three closed 2026-09-25, content approved 2026-09-25 (07 D28):**

| # | Gap | Result |
|---|---|---|
| G1 | Example screens for `AN`, `SS` response, `FQD`, `FXP` response | **Closed.** Layouts recorded as V-14–V-18 (plus the PNR header, element order and numbering). Residual unverified details U-06–U-11 → K6. Conflict with §4 numbering → K5 |
| G2 | Slice content | **Done — approved (07 D28)** with the readiness-check fixes. `deixen-app/content/` (3 files; reading copy `DEIXEN_Slice_Content_Review.md`): 10 lessons EN+AR, 10 Ghost scripts on a separate demo booking, main task + scenario data, 44 feedback texts (32 diagnostic, 12 corrective — `scn.fb.warningShown` re-tagged at the readiness check), 8 nudges, training messages, Coach explanations, contract texts |
| G3 | Simulator Scope Disclosure | **Done — approved (07 D28).** 9 items EN+AR (`disc.*`); `disc.6`/`disc.7` updated for Decision 27 and K7 |

**Karim decisions raised by G1 — both approved 2026-09-25 (07 Decision 27), applied in §4, §5 and §13:**

| # | Item | Claude's recommendation |
|---|---|---|
| K5 | Element numbering: replace "number shown during entry = number in the final PNR" (§4) with "every number shown = the element's number in the PNR as it stands at that moment, computed by the same function as the final display" — what official examples show (V-18) and what the old Known Issue #7 lesson actually asked for (LDS §14). Alternative: keep the literal rule by changing the approved path order (`NM` before `SS`, `TK` before `SRCTCM`) — reopens D22/D24 | Agree with the replacement |
| K6 | Screen details official examples show only partly (U-07, U-09, U-10, U-11: airline code in the stored `SSR CTCM` line; the `AN` header number; the `AN` header time when a time is entered; redisplay after `AP`/`SRCTCM`/`TK`/`RF`): show the verified pattern with a small "Layout detail not fully verified" marker, never teach the detail, list it in the Disclosure. Details with no official pattern at all (stored `SRCTCR`, `RF` before end of transaction — U-07, U-08) stay plain training messages under D23. Alternative: D23 strictly — every such line becomes a training message | Agree with the marker approach |

**Raised by the readiness check (3.6), 2026-09-25 — approved 2026-09-25 (07 Decision 28):**

| # | Item | Claude's recommendation |
|---|---|---|
| K7 | Contact-SSR endings (Verified Reference U-12). Every official example ends with something after the number or text (`SRCTCM-3054996244/US`, `SRCTCMAFHK1-0034563214/P1`, `SRCTCR-REFUSED/P3`); two training references describe `/US` as the phone's country, while an airline notice gives the bare format `SRCTCM-Phone number`. Proposal: keep the approved entries (`SRCTCM-` + number; `SRCTCR-` + free text); the lesson shows the official example with its ending and says the ending is outside the slice; an ending typed by the learner is accepted and not checked; listed in the Disclosure (`disc.7`). Alternative: require an ending — this would teach a rule not yet VERIFIED (07 D13) | Agree with the proposal; research the endings before the Basic track expands |

**Closed at the Phase 4 gate, 2026-09-26:** the `AN` header number before
the weekday had no value in `slice.json` although §5 pointed there — closed
by 07 Decision 44 (fixed value `30`, never computed, never taught). The
visual design is approved (07 D42; §2).

**Deferred — not in this slice:** Terminal Screen Literacy candidate (LXA
§22, new candidate) — outside the frozen boundary (07 D8A); revisit after
real learner testing. Speed Drills, spaced retrieval, Customer Service
track, `XE`/Known Issue #7 mitigation (no `XE` in the slice).

## 13. Definition of Done

**[D] 07 Definition of Done**, plus **[D on approval] LDS §32**:

(How build steps 6 and 7 prove each line: §7D, 07 D63.)

- [ ] A learner completes the full path end to end with real content.
- [ ] Every command in §6 works with valid and invalid handling, hints, and
      completion detection; nothing outside §6 is simulated.
- [ ] Every output line is one of the three kinds in §5, visibly distinct;
      no invented Amadeus text anywhere. The Terminal holds only Amadeus
      output and labeled training lines; feedback, hints and Coach are in the
      DEIXEN panel (07 D30); wrong entries show the `terminalLine` of their
      feedback item and leave the PNR unchanged (07 D33).
- [ ] Every element number shown equals the element's number in the PNR at
      that moment, from the one numbering function the final display uses
      (§4; e.g. `SS` segment 1 → 2 after `NM`; `SSR CTCM` 4 → 5 after `TK`).
- [ ] Every partly verified detail in §5 carries the marker; nothing marked
      is taught; every item is in the Scope Disclosure.
- [ ] The scenario is behaviorally distinct per the contract and produces
      TRANSFERRED only for load-bearing, independent skills.
- [ ] Assessment follows its contract: announced entry, honest hint label,
      carry-over disclosure, no cross-session merging.
- [ ] Observed and correctly handled: one hint-adjacent success, one
      corrective-feedback-adjacent success (both excluded from independence),
      one Error-Recovery Practice instance on `ER`.
- [ ] Chain practice evidence is queryable through `chainId`.
- [ ] Evidence persists and traces; Growth shows only the §10 status.
- [ ] Coach behaves correctly at all five touchpoints.
- [ ] No false affordance anywhere.
- [ ] Arabic + English, RTL + LTR.
- [ ] Accessibility baseline and all breakpoints in file 04 pass.
- [ ] Reset produces a clean state; schema mismatch triggers reset.

## 14. Sources

07 (D8A, D9, D11, D12–D14, D20, D22–D27; Evidence, Assessment, Scenario
contracts; Definition of Done) · 03 (IA, Terminal skeleton, schemas,
persistence) · 04 (accessibility, breakpoints) · 06 (Coach contract, error
discipline, Ghost Mode schema) · LDS §5–§8, §10, §13–§16, §18, §20–§23,
§29, §32, §36 · LXA §8, §9, §11, §12, §17, §18, §22 ·
`DEIXEN_Amadeus_Verified_Reference.md` V-01–V-18, U-01–U-14 · `deixen-app/content/` ·
`DEIXEN_Design_Brief.md`.
