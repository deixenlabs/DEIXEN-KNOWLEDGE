---
name: DEIXEN Slice Build Spec
status: CURRENT — APPROVED by Karim 2026-09-25 (07 Decision 26). Updated 2026-09-25: gaps G1–G3 (§5, §12); Decision 27 (K5, K6) applied to §4, §5, §12, §13; K7 (§6 row 5, §12) approved in the Phase 3 gate (07 D28). Phase 4, 2026-09-25: 07 Decisions 30, 32–34, 36 applied to §5 and §13; Decisions 37–38 to §4 and §8. Phase 4 gate, 2026-09-26: 07 Decision 42 (approved design, `tokens.css`) applied to §2; Decision 44 (`AN` header number) to §5 and §12; Decision 45 (boards exported to `design/phase4/`) to §2. Phase 5, 2026-09-26: 07 Decisions 46 (`result` on ending events) and 47 (one tab at a time) applied to §11. 2026-09-26: 07 Decision 49 applied to §6 ("not recognized" vs "not covered") and new §6A (rules for build step 2 part B). 2026-09-28: 07 Decision 50 — §6A items 8–10. 2026-09-28: 07 Decision 52 — new §7A (rules for build step 3), pointers in §8, §10, §11. 2026-09-28: 07 Decision 53 — §7A items 1 (return to practice, app I-12) and 14 (data-reset notice). 2026-09-28: 07 Decision 54 — new §7B (rules for build step 4: the current step for hints, hint levels on the screen, the entry field, parts 4A/4B, load notices), pointer in §8. 2026-09-29: 07 Decisions 55–56 — §7A item 1 (a run also starts at an accepted hint request, app I-12), items 1 and 11 and §9 (pointers to the in-app exit), §7B heading and new items 6–10 ("Booking as it stands", leaving a running assessment or scenario, storage refused, the name as a string key, behaviours over time); 07 Decision 57 — §7B items 11–15 (the Flight Deck's recommended action, the practice run when moving between screens, Learning, Ghost Mode replays, when the scenario and the assessment start). First edition (Execution Plan 3.3); proposals K1–K4 approved (07 Decision 25). With this approval, the LDS/LXA content extracted here is binding for the slice (LDS and LXA reading rules, point 1).
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
  320–1440 px). Terminal workspace is never sacrificed on mobile.

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
   `scn.fb.bypassed` (scenario) and `coach.bypassRecorded`. Any other entry
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
  §29 item 4).

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
    assessment completed with every checklist item met" and "the scenario
    completed" both mean item 11; (4) In Progress. Needs More Practice
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

## 7B. Rules for build step 4 (07 D54–D57)

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
    (d) the scenario has not been completed (§7A item 11) →
    `ui.fd.openScenario`;
    (e) otherwise → `ui.fd.openGrowth`.
    Exactly one action on the screen has the primary-button style (`P1-F`).
    In (a) and (b) it sits in the Next row as drawn; in (c)–(e) no row
    carries Next, and the action takes that place under the chain, with
    existing patterns only. The chain's status words stay as 07 D40 says.
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
- **Escalation:** after `ESCALATION_ERROR_COUNT` same-category errors on a
  skill in one session, Coach *offers* the lesson link; suppressed once the
  skill is CONSOLIDATED unless NEEDS_REINFORCEMENT is active.
- **Coach (06, LXA §11):** learner-initiated by default; bound to real
  state; present at the five touchpoints; tone describes the unmet
  condition, never blames (LDS Principle 7); presents Amadeus behavior as
  fact only if VERIFIED. Mobile: collapsed/on-demand (LXA §18). Layout
  (global vs per-page) is the builder's choice within these rules.

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
| Completed | All nine required skills DEMONSTRATED_INDEPENDENT or higher, **and** the assessment completed with every checklist item met, **and** the scenario completed |
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
