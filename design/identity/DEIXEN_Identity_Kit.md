<!--
  DEIXEN Identity Kit — AS CHOSEN by Karim, 2026-10-13 (07 Decision 81).
  Read-only copy for Claude Code. The text below is Kit v0.2.1 (2026-10-13) unchanged, as Karim chose it.
  Its "Status: EXPLORATION" and "nothing is recorded" lines describe the draft before the choice; the record is
  07 D80–D81. How the kit is used in Step 4, and which of its §3 gaps stay open: 07 D81 (e)–(f).
  Part 2 (handoff 2026-10-13 (k)) changed nothing in the kit: hypotheses B and C were not adopted; K3 stays square
  and flat; G6 (motion) stays a named gap.
  Reference renders in this folder: DEIXEN_Terminal_States_2026-10-12_r1.html (Terminal S1–S7) and
  DEIXEN_FlightDeck_Growth_Step4P1_2026-10-13.html (Flight Deck and Growth, B1–B3 and X1–X4).
-->

# DEIXEN — Kit v0.2.1 (desktop), draft 2026-10-13

Status: EXPLORATION (07 D78/D79), open identity mode. **v0.2.1 draft (Step 4 Part 1, 2026-10-13):** header corrected
(Karim's item 5), §3 G3/G5 updated after Karim's decisions of 2026-10-13, G5b and G6 named. Proposal text only; every
v0.2.1 change is marked *(v0.2.1)*. Nothing else in §1 changed.
Earlier status: Updated after step 1 (P6): K3 extended, K4 refused rail, K10
added. **v0.1, after step 2 (states sheet):** K1 note head, K3 refused newest, K4 booking close, K5 grey continuation,
K7 no tick, K9 accepted line, K10 brief control and shown levels; §2 and §4 item 1 updated. Every v0.1 change is marked *(v0.1)*.
**v0.2, after step 3 (generation test: Flight Deck, Growth):** K1 one title per screen and a note with no entry; K3 the
light on the chain's current step and on the current status; K4/K5/K6 the booking chain; K8 screens with no Terminal;
K10 the one filled control; §2 and §3 updated (gaps G3–G5 open, for Karim). Every v0.2 change is marked *(v0.2)*.
*(v0.2.1)* v0.2 lines are of four kinds (a)–(d) as in handoff (i) §4; lines marked (d) are open design decisions, not derived extensions. Step 0 of the Identity Finish Plan (approved by Karim
2026-10-12 20:16). A proposal: nothing here is recorded in 07 until plan §5. Source of every element:
`DEIXEN_Terminal_P5.2_2026-10-12.html` (handoffs (b), (c), (d)), written down — not redesigned. Values are the
P5.2 values (proposals under the approved role-token names, 07 D78). Desktop only.

**How to use it.** A screen is DEIXEN when every visible part is built from these elements and their rules, and
nothing on it does a job that a kit element already does in another way. An element used outside its "Used for"
is a fault, even if it looks good. Where the kit has no element for a job, the gap is named (§3), not filled
by taste.

## 1. The elements

### K1 — Two voices
- **Meaning:** who is speaking. Amadeus (and the learner's entries to it) speaks in **JetBrains Mono**,
  unlabelled; DEIXEN speaks in **Inter** (English) / **Noto Sans Arabic** (Arabic).
- **Used for (mono):** record lines, entries, the entry line, Amadeus codes inside DEIXEN text (`RUH`, `6X 403`,
  `TKOK`), quotes of entries in the feedback, and the record's own grid (exchange numbers `01…`, the prompt `>`).
- **Used for (sans):** every word DEIXEN writes — labels, task, feedback, controls, counts.
- **Rules:** Amadeus output is never outshone: no DEIXEN element is brighter or larger than the newest record
  line except the task title. Record lines keep `white-space: pre`, left-to-right, never wrapped (D69 (b) limit 1).
- **Note head** *(v0.1)*: every DEIXEN note starts with its label and the echo of its entry in mono ("Feedback  ER",
  "Coach  ER"); the verdict or text follows.
- **One title per screen** *(v0.2)*: at the task title's size (20px): the task on the Terminal and the Flight Deck;
  the status word on Growth. Every other DEIXEN line is smaller.
- **A note with no entry** *(v0.2)*: a note that belongs to no entry (Growth's Coach note) starts with its label only.
- **Forbidden:** mono for DEIXEN's own words or numbers (a count of hints is DEIXEN's, not Amadeus's); a label
  on Amadeus output ("Amadeus says…"); sans inside a record line.

### K2 — The cell (one family, from the entry line's block cursor)
- **Meaning:** one character position in the Terminal. The cell always points at an exact place.
- **Members:**
  | Member | Look (P5.2) | Means |
  |---|---|---|
  | Cursor | frosted white block, 8×16 | your next character goes here |
  | Refused cell | red block 12×18, radius 2, mono "?" in `--on-danger`, in the record's gutter | this entry was not accepted |
  | Wrong-character cell | 1ch × 17px, 1.5px red outline, light red fill; empty where a missing "/" belongs | this position is wrong |
  | Fix cell | 1ch × 17px, 1px neutral grey outline, around the corrected character | this position is the change |
- **Used for:** the entry line, the record's gutter, quotes of entries in the feedback. Nowhere else.
- **Rules:** a cell is the size of a character (or of the gutter slot); its corner is 2px. The "?" is the
  refused-entry mark approved by Karim (2026-10-12) — never an icon, never a disc.
- **Forbidden:** cells as bullets, badges, status pills, avatars, nav markers or decoration; a red cell without
  the text that says what was refused (never by colour alone, D77 item 2).

### K3 — The light
- **Meaning:** where the learner is now. The newest exchange sits on a slightly brighter band
  (`--surface-current` #181818 on #0c0c0c) and its rail is lit (#fafafa). In the booking, the newest element's
  text is lit.
- **Used for:** one "now" per region: the newest exchange (record), the newest booking element (panel), the
  current area in the navigation (band the full height of the top bar, text lit; added in step 1, G2).
  *(v0.2)* The current step of the booking chain on the Flight Deck ("Next"): band, rule segment lit (keeping its
  pattern, as the refused exchange keeps its dotted rail), text lit; when no step is next (Build Spec §7B item 11
  (c)–(e)), the row of the recommended action (the assessment or the scenario row). The current status in Growth's
  "The three statuses" (board P1-07a marks it `aria-current`). Growth's chain has no "now" (07 D41 (g)).
- **Rules:** older lines are **never dimmed** — the light adds, it never takes away. Square edges (the band is
  not a card). *(v0.1)* A refused newest exchange is lit like any other (its rail stays dotted). A region may have
  no "now": an empty record (S1), a filed booking where nothing changed (S6).
- **Forbidden:** the light as hover, selection or emphasis for importance; two lit items in one region; dimming
  history to make the light work.

### K4 — The rail and the numbered exchange
- **Meaning:** an exchange is one entry and the system's answer to it, joined. Each exchange carries its own rail
  (1px line from under the entry down the answer, turning right at the end, radius 4). Exchanges are numbered
  `01`, `02`… in the number column; the entry line shows the **next** number.
- **Grid:** number column 40px · gutter 20px (the refused cell sits here) · text with 16px inset. The entry
  line uses the same grid; labels that sit on the Terminal ("Amadeus entry", the mode) start on the text column,
  in both languages (the Terminal stays left-to-right, K8).
- **Refused exchange:** its rail is dotted and does not turn — the entry did not enter the record.
- **The booking closes** *(v0.1)*: when the booking is filed (valid `ER`), "Booking as it stands" loses its dashed
  open end and its rule turns at the end, the rail's own turn (16px, radius 4): settled. An empty booking is its
  label and the dashed open end only (S1, S7). *Weak in render: the turn is small; judged in step 4.*
- **The record scrolls** *(v0.1, builder's behaviour, Build Spec §7B item 10)*: the newest exchange stays in view;
  earlier ones leave at the top edge, never with a refused cell cut in half. The exchange numbers say what is above.
- **Forbidden:** numbers on anything that is not an exchange (areas, hints, steps); rails as decoration.
  *(v0.2)* So the booking chain carries no 01–10 (board P1-01 numbered its rows).

### K5 — Lines join things that belong together
- **Meaning:** a line is a relation, never a divider for its own sake. Three kinds exist:
  the rail (entry → answer, K4); the **red tie** (one continuous red line from a refused exchange to its
  feedback, ending in a 3.5px red dot at the panel edge, then a dotted grey continuation to "Correct in
  DEIXEN"); the **booking line** (the elements of one booking, on one vertical rule).
  *(v0.2)* The **booking chain** (Flight Deck, Growth) is a booking line for the path: the nine required steps on one
  rule, solid where the step is done on your own, dashed where it is not (K6); the rule turns at its end only when all
  nine are done (as the booking closes, K4). `FQD` (optional, not required for Completed) sits under it, off the rule;
  the assessment and scenario rows sit under that, off the rule (not members of the sequence).
- **Rules:** solid = settled; dashed = not settled (K6); red = the relation of a refused entry. *(v0.1)* Where the
  refused entry has a Coach note, the tie's vertical continues **solid grey** along it (same entry, explanation);
  dotted grey stays for the way to another entry's note ("Correct in DEIXEN" of the fix).
- **Forbidden:** red lines for anything but a refused/error relation; lines that join nothing.

### K6 — Dashed = not settled
- **Meaning:** this is still open. Used for: the open end of "Booking as it stands" (the rule continues dashed,
  no floor, no "+", no words); the rule under a partly verified display, with the note under it (F-03: the note
  belongs to the display, never to the entry). *(v0.2)* A step of the booking chain not yet done on your own.
- **Forbidden:** dashed as a style for borders, placeholders or empty states that are settled.

### K7 — Colour jobs (dark ground)
| Colour | Job (one each, D77 item 2 for red) | Never |
|---|---|---|
| Near-black ground #0c0c0c, greys | the record and the interface's words | — |
| Frosted white #f2f2f2 (fill/outline) | interaction only (controls, the cursor) | as text emphasis or decoration |
| Red #e5675f | refused entries, wrong entries, errors; the irreversible action (Reset everything) | alone: always with text and structure |
| Green #66c28f | "Correct in DEIXEN" and nothing else — its words only, no tick icon *(v0.1)* | for "Completed" (07 D76 / app I-27) or any success |
- No brand accent colour (no blue, pink, magenta: Karim 2026-10-07/08). No coloured strips on cards.

### K10 — Controls (added in step 1 from the cell, G1)
- **Shape:** corner 2px (the cell's corner); 1px frosted-white outline at 40% (3.5:1 on the ground, WCAG 1.4.11);
  frosted-white text. **Send** is the one filled control (it is the action that makes the next exchange).
  Disabled: grey outline #2a2a2a, grey text. No pills, no icons, no keycaps ("Enter" is a word in DEIXEN's voice).
- **The one filled control** *(v0.2)*: the screen's one forward action — Send on the Terminal; the recommended action
  on the Flight Deck (07 D57, Build Spec §7B item 11: exactly one primary-style action), in its row; "Start lesson 1"
  on an empty Growth (board P1-07b).
- **Place:** a control sits next to what it acts on — Reset task and Start assessment at the record's head, on
  the Terminal column's right edge; Send at the end of the entry line; hint levels in the panel.
- **Hint levels:** shown in their order (Nudge → Partial Reveal, only at `ER` → Full Reveal) and joined by a short
  line (K5: one sequence, one counter); the count after them in DEIXEN's voice.
- **Brief control** *(v0.1)*: Hide brief / Show brief is a control (22px high), on the Task label row at its end.
  The brief folds when the notes grow (S5–S7; P1-05 draws it folded at the assessment start).
- **Shown hint levels** *(v0.1)*: a shown level is no longer a control — its word stays in the ladder, no box; its
  text sits above the ladder, level by level, on one rule (one sequence, K5). The block grows upward, so the ladder
  keeps its place. The count moved to the Hints title row (three levels and the count do not fit one 420px row).
- **Forbidden:** pills, rounded 6–10px corners, icons, controls in any colour but frosted white (red only for
  Reset everything).

### K8 — Composition (Option C)
- Terminal left, DEIXEN panel right (Task → Booking as it stands → Feedback), the same in English and Arabic.
  The Terminal column starts with its head row (mode, Reset task, Start assessment); the panel starts on the same
  row with "Task" (step 1).
  Arabic text inside each part is right-to-left and starts at the part's right edge; the Terminal, the record and
  the entry line stay left-to-right.
- Stage: 1200×720, scaled whole to the window (1440 = ×1.2; 1280 = ×1.067).
- *(v0.2)* **Screens with no Terminal** (Flight Deck, Growth) keep the two parts: the path on the left, where the
  record sits (the chain, its rows, the recommended action), DEIXEN's reading in the panel on the right (status,
  notes, what else exists); both start on the same head row. Option C: the parts keep their places in Arabic; inside
  the left part DEIXEN's text runs right-to-left from the part's right edge (the chain's rule moves to that edge);
  codes stay left-to-right. No divider between the parts (K5).

### K9 — The verified Amadeus response in the training line's place
- A verified Amadeus message (`INVALID FORMAT/NOT ENTERED/`) takes the training line's place under a refused
  entry, in the Amadeus voice, with no DEIXEN label (07 D23, D30, D33). The one labelled DEIXEN training line is
  used only where no verified response exists.
- *(v0.1)* **Accepted training line** (e.g. `tm.rfLine`, first sentence, D34): label `ui.trainingLabel` in DEIXEN grey
  (not red), text in sans, solid rail. In "Booking as it stands" the same first sentence with its label and **no
  number** (Build Spec §7B item 6).

## 2. Every element still generic (P5.2) — by region
| Region | Generic element (P5.2) | Why generic | Step |
|---|---|---|---|
| Top bar | centred nav with 2px underline on the active area | the default tab indicator of every web app; carries no kit meaning | 1 — closed in P6 (K3) |
| Top bar | language switch with a dropdown chevron | a menu sign on a two-way switch: a false hint of a menu | 1 — closed in P6 |
| Toolbar | "Terminal · Practice" breadcrumb | repeats the nav; a dot-separated breadcrumb is a default | 1 — closed in P6 (record head) |
| Toolbar | two outline buttons, radius 6, far right above the panel | default secondary buttons, placed away from what they act on (the record) | 1 — closed in P6 (K10) |
| Entry bar | full-width rule above the bottom area | a divider that joins nothing (K5 forbids) | 1 — closed in P6 |
| Entry bar | `Enter` in a keycap box | the default keyboard-hint chip; mono for a non-Amadeus word (K1) | 1 — closed in P6 |
| Entry bar | white Send pill, radius 6 | default primary button shape | 1 — closed in P6 (K10) |
| Entry bar | the next exchange (05) has no rail | tried in P6 round 1 (dashed open rail); dropped: it clashed with the refused exchange's dotted rail. The next number, prompt and cursor carry it | 1 — not a gap |
| Hints | outline pill buttons, lightbulb icon on Nudge only | default icon button; the one icon in the screen | 1 — closed in P6 (K10) |
| Hints | hint count `0` in bold mono | DEIXEN's count in the Amadeus voice (K1) | 1 — closed in P6 |
| Hints | levels shown as unrelated buttons | the ladder's order (Nudge → Partial Reveal → Full Reveal, one counter, Build Spec §8) is not shown | 1 — closed in P6 (K10, weak: the joining line is small) |
| Panel | "Hide brief" underlined grey link | a control not in the interaction colour (K7) | 2 — closed (K10 brief control) |
| Panel | ✓ icon before "Correct in DEIXEN" | a generic tick icon (the only pictogram left) | 2 — closed (K7: words only) |
| Panel | "Task" label + 20px title + body text | plain article typography; carries no kit element | 2 — judged: stays. The title is K1's one allowed exception; the brief is learning content. Step 4 critic may reopen |
| States | Coach note, Full Reveal text, assessment mode, empty record, filed booking | not yet drawn with the kit | 2 — drawn (states sheet S1–S7) |
| States | assessment mode is told only by the mode word, the missing controls and the announcement | quiet; no kit element marks a run boundary in the record | open — named in handoff (f) §4, not filled |
| Flight Deck, Growth *(v0.2)* | built from the kit (step 3) | identity rests on the chain's line, the light and the one filled control; quieter than the Terminal | 3 — self-review in handoff (h) §2; step 4 critic |

## 3. Gaps (the kit had no element)
*(v0.2.1)* **After Karim's decisions of 2026-10-13** (Step 4 prompt, items 2–4; render-only until plan §5):
- **G3 — App shell: decided by Karim.** The shell is the Terminal's, copied onto Flight Deck and Growth; the Terminal
  does not change: 64px bar, 1px rule under it (#242424), nav centred on the stage (27px between items; the current
  area in the light, 16px each side), 32px page margins, 48px column gap, the Terminal's language control (current
  language first in its colour, a 1×14px divider, the other language in grey). Applied render-only in Step 4 Part 1
  (B1). At Step 4 three layout values in `tokens.css` change under the same role names: `--layout-header` 56→64px,
  `--layout-page-margin` 40→32px, `--layout-column-gap` 40→48px (lines 190/191/194; approved in D42 for the light
  "Margin" design; D78 reopens layout). **Logged as open, not forced:** whether the rule under the bar is a "line that
  joins nothing" (K5); the divider in the language control (K5) and the current label's brightness (K3); the Arabic
  label order (current first, so it swaps). The centred nav departs from the approved boards (nav after the
  wordmark); it stays centred when the wordmark returns while the wordmark is under about 300 stage px.
- **Nav text (handoff (i) row 8): render-only, not standardized.** 14px / 400; idle `--text-meta` (#9c9c9c); current
  `--text-record-cur` (#fafafa) on `--surface-current` (#181818); Arabic in Noto Sans Arabic at the same 14px (the
  step-3 screens used `--fs-ui` 15px / 500 in Arabic). Not reconciled with `tokens.css` (`--weight-medium` 500 "nav").
- **G5 — withdrawn** (handoff (i) §3): every lit band renders #181818.
- **G5b — one token layer: decided by Karim.** All three screens use the Terminal's rendered `.v-strong` values
  (states sheet r1, lines 104–117): `--text-record` #e4e4e4, `--text-record-cur` (lit) #fafafa, `--text-secondary`
  #c4c4c4, `--text-meta` / `--text-deixen` (labels) #9c9c9c, `--fs-prose` 14.5px (Latin). Per role, the step-3
  screens had: labels, prose and lit text **dimmer**; idle nav **slightly brighter** (#a3a3a3 vs #9c9c9c).
- **G4 — type values: still open.** Label 12.5px/500 vs 12px/400; title weight 500 (−0.2px) vs 600; control text
  13px/400 vs 14px/500 (15px in Arabic); Growth's status title 20px vs approved 28px (`--type-title-2`).
- **G6 — motion** (named for Part 2, Hypothesis B): the kit has no motion rule. Precedent: `tokens.css` §8 "Motion:
  explains a change, never decorates" (`--motion-reveal` 200ms, `--motion-mark` 420ms, one easing, all 0 under
  reduced motion).

*(v0.2)* Open after step 3 — named, not filled (they change the Terminal too, so Karim decides). *(v0.2.1: superseded
by the block above for G3, G5; kept as history.)*
- **G3 — App shell.** The kit has no top bar (height, nav place, wordmark place, rule under it, language switch) and
  no stage margins or column gap. Step 3 used the approved role tokens (56px bar, 40px margins, 40px gap, nav after
  the wordmark) and one control naming the other language; the Terminal (states sheet) has a 64px bar with a rule
  under it, centred nav, "English | العربية" with a divider and the current language brighter, 32px margins, 48px gap.
  Two Terminal parts conflict with the kit's own words: the rule under the bar (K5) and the switch's divider and
  brightness for the selected language (K5, K3). Recommendation (handoff (h) §5): K11 = the Terminal's geometry
  without those two parts.
- **G4 — Type values.** Sizes and weights of labels, titles, prose and control text are not written (step 3 used
  approved role tokens; the Terminal uses label 12.5px/500, title weight 500, control text 13px).
- **G5 — One value differs.** K3 says `--surface-current` #181818; the states sheet uses #161616.

Closed in step 1:
- **Controls.** The kit says what colour a control is (K7) but not its shape. Step 1 closes this from the cell:
  corner 2px (the cell's corner), no pills, no icons (G1).
- **"Where you are" outside the record.** The current area in the navigation needs a "now" mark; K3 (the light)
  is the kit's "now". Step 1 tests extending K3 to the navigation (one lit item per region) (G2).

## 4. Record-ready texts (for plan §5; nothing is recorded until Karim chooses)
1. **Decision 80 — Option C** (amends 07 D77 item 7's reading for layout): one composition in both languages —
   Terminal left, DEIXEN panel right, the same header order and control places; Arabic text inside each part is
   set right-to-left and starts at the part's right edge; the Terminal, the record and the entry line stay
   left-to-right. *Reconciled with handoff (c) §2 (v0.1): the record text there is the one to use; it also amends
   D11's layout reading and changes the `CLAUDE.md` checklist line "layout mirrors correctly" to "Arabic text inside
   each part is RTL and right-aligned; the composition is the same in both languages".*
2. **The refused-entry mark:** the refused cell (K2): the Terminal's own character cell in red, 12×18, radius 2,
   holding a mono "?"; approved by Karim 2026-10-12 over ✕. Amend the refused-state mark in the Build Spec /
   design notes when the identity is recorded (07 D78).
3. **`ui.unverifiedMarker`** — new wording, approved by Karim 2026-10-12 (plan §5), to `text.json` / `text-1.json`
   through 07 D77 item 6 (both copies identical, F-21):
   - EN: "Official Amadeus pattern; small details may differ in the real system, so don’t memorise them."
   - AR: «النمط الرسمي في Amadeus، لكن تفاصيله الصغيرة قد تختلف في النظام الحقيقي، فلا تحفظها.»
   - Shape: the dashed rule the width of the display, the note under it (K6). Names no detail (details stay in
     `disc.6`).
4. **`INVALID FORMAT/NOT ENTERED/`** as a V-entry in the Verified Reference (source as rendered in P5.2:
   Amadeus Service Hub 839546, updated 02/10/2025 — the message after an incorrect `NM` format) and its
   `slice.json` mapping: as written in handoff (c) §3.
