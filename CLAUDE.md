# CLAUDE.md — DEIXEN app (first-build slice)

> Status: APPROVED by Karim 2026-09-25 (07 Decision 26). First edition
> (Execution Plan 3.5); Decision 27 applied 2026-09-25 (§3 rule 2, §8); Decisions 30, 33, 34 applied 2026-09-25 (§3 rule 2); Phase 4 gate (07 Decision 42) applied 2026-09-26 (§2, §4, §5, §8); Decision 45 (boards in `design/phase4/`) applied 2026-09-26 (§2, §4). This file is the master copy of the
> Claude Code instructions; at build start it becomes the first file of the
> code repository.

## 1. What you are building

DEIXEN trains a beginner to work in the real Amadeus reservation system
(Cryptic command line). You build **one vertical slice**, nothing more. The
full specification is:

**`../DEIXEN-KNOWLEDGE/DEIXEN_Slice_Build_Spec.md`** — read it in full at
the start of every session. It is the only build specification.

## 2. Where things live

Two repositories side by side in one parent folder:

```
<parent>/
├── DEIXEN-KNOWLEDGE/   ← project knowledge (read-only for you)
└── deixen-app/         ← the code (this repository)
```

Files you read from `DEIXEN-KNOWLEDGE/` (never copy them into this repo —
one owner per truth):

| File | Use it for |
|---|---|
| `DEIXEN_Slice_Build_Spec.md` | What to build — always |
| `DEIXEN_Amadeus_Verified_Reference.md` | Any Amadeus syntax, message, or display — the only source |
| `design/phase4/` — the approved Phase 4 boards listed in spec §2, `tokens.css`, and `MANIFEST.md` (read-only copy of the Claude Design canvas, 07 D45) | Anything visual: layout, identity, states, controls (spec §2 says which boards and how to read them) |
| `07_DEIXEN_Canonical_Decisions_and_Current_State.md` | Only when the spec cites a decision you need to read |

Do not read the Learning Design Specification or the Learning Experience
Architecture unless the spec's text is unclear; the spec already extracts
what the slice needs. If you do read them and they conflict with the spec,
stop and report (§6).

## 3. Hard rules

1. **No invented Amadeus.** Every command, format, status code, message, and
   screen comes from an entry marked VERIFIED in the Verified Reference. Your
   own knowledge of Amadeus or any other GDS is never a source. If the spec
   needs something the Reference does not have, stop and report.
2. **Three kinds of Terminal output** (spec §5): Amadeus output (verified
   only), training message (visibly marked), Coach explanation (beside, never
   instead). The Terminal holds only Amadeus output and one short labeled
   training line; feedback, hints and Coach go in the DEIXEN panel (spec §5,
   Decision 30). A wrong entry of a known command shows its feedback item's
   `terminalLine` and leaves the PNR unchanged (Decision 33); a long
   training message shows its first sentence only (Decision 34). A detail the spec lists as partly verified (spec §5, Decision
   27) is drawn in the verified pattern with the "Layout detail not fully
   verified" marker and never taught; anything with no verified pattern is a
   training message — never a guessed Amadeus look.
3. **No Amadeus content authoring.** Lessons, feedback texts, Ghost Mode
   scripts, task and scenario data come as content files written by the
   project lead and approved by Karim. You wire them in; you do not write or
   "improve" their wording.
4. **Scope is frozen** (spec §1). No extra commands, areas, features,
   backend, login, or analytics. A useful idea you notice goes in
   `docs/ISSUES.md`, not in the code.
5. **Evidence honesty.** Never show progress, a status, or success that the
   stored events do not support. Derived values (skill states, independence,
   Growth status) are computed on read, never stored.
6. **One hint counter**, incremented in one place, counting learner requests
   only. The independence flag is separate (spec §8).
7. **No false affordance.** Every visible control works or is labeled
   unavailable.
8. **Never fabricate test results.** If you could not run or observe
   something, say so.

## 4. Technical baseline

- Frontend-only static web app; state in `localStorage` under the key and
  schema in spec §11; no server calls.
- Default stack: TypeScript, React, Vite; Vitest for unit tests; Playwright
  for end-to-end and breakpoint checks. You may choose differently if you
  write the reason in `docs/DECISIONS.md` first — this is your delegated
  technical authority; it does not cover product, content, or learning
  rules.
- Arabic + English, RTL + LTR, switchable. All learner-facing strings in
  locale files; none hard-coded.
- The command simulator (`src/engine/`) is pure logic: input → result. It
  never touches storage or UI. One thin bridge calls it and records the
  event (spec §11).
- Provisional numbers (`CONSOLIDATED_COUNT`, `REINFORCEMENT_FAIL_COUNT`,
  `ESCALATION_ERROR_COUNT`) live in one config file.
- Visual values come only from `src/styles/tokens.css` — the approved
  token file (07 Decision 42), used unchanged; check its sha256 against 07
  D42 when you add it. Components use its role tokens, never raw colours or
  sizes. A value the design needs that the file lacks: stop and ask (§6).
- Read the design from `../DEIXEN-KNOWLEDGE/design/phase4/` (spec §2;
  07 D45), not from the canvas. Check a board's sha256 against
  `MANIFEST.md` before relying on it. If a board you need is missing or
  fails the check, stop and ask Karim — never rebuild a screen from memory
  or from this file's description.

## 5. Repository layout

```
deixen-app/
├── CLAUDE.md
├── content/              ← approved content files (lessons, tasks,
│   ├── en/  ar/            scenario, feedback, Ghost Mode, disclosure)
│   └── data/             ← fictional flights and fares for the slice
├── src/
│   ├── engine/           ← command simulator, one module per command
│   ├── evidence/         ← event store, derivations (skills, status)
│   ├── bridge/           ← engine ↔ evidence
│   ├── ui/               ← screens for the eight states (spec §3)
│   ├── coach/
│   ├── i18n/
│   ├── styles/
│   │   └── tokens.css    ← approved token file (07 D42), unchanged
│   └── config.ts         ← provisional numbers
├── tests/
│   ├── engine/           ← every checklist item, valid and invalid
│   ├── evidence/         ← independence, skill states, status rule
│   └── e2e/              ← full path, scenario, assessment, breakpoints
└── docs/
    ├── DECISIONS.md      ← your technical choices, with reasons
    └── ISSUES.md         ← anything out of scope or unresolved
```

## 6. When to stop and ask

Stop, write the question in `docs/ISSUES.md`, and tell Karim in plain
language when:

- the spec and a source file disagree;
- the spec needs Amadeus behavior the Verified Reference lacks;
- a rule would force a weaker learning or evidence behavior to make the code
  easier;
- a task would change scope, meaning, or a decision.

Do not choose an answer silently.

## 7. How to work (file 08 §26)

For every non-trivial change: **audit → plan → implement → test → observe →
diagnose → correct → re-test → regression check → self-review.** Build in
this order, testing and locking each before the next:

1. Evidence store and schema (spec §11) with tests.
2. Engine: one command at a time along the path, each with checklist tests.
3. Bridge, independence flag, skill states, Growth status — with tests.
4. Terminal screen (spec §4–§5), then the other seven states.
5. Coach at the five touchpoints.
6. Scenario and assessment.
7. Localization pass, accessibility pass, breakpoints.

Git: `main` stays working; work on `feature/...` branches; tag each locked
step.

## 8. Verification checklist (run before reporting any step done)

- [ ] Unit tests pass for everything touched; new behavior has new tests.
- [ ] Each command: every checklist item tested for pass and fail.
- [ ] Every Amadeus string in the UI traced to a Verified Reference entry
      (grep for strings; list any without a source).
- [ ] Training messages are visibly different from Amadeus output.
- [ ] Every element number shown is the element's number in the PNR at that
      moment, produced by the one numbering function the final display uses
      (spec §4); tests cover `SS` 1 → 2 after `NM` and `SSR CTCM` 4 → 5
      after `TK`.
- [ ] Every partly verified detail in spec §5 shows the marker.
- [ ] Hint-adjacent and corrective-feedback-adjacent successes are not
      counted as independent.
- [ ] Events persist across reload; schema mismatch triggers reset; reset
      clears everything.
- [ ] No cross-session merging in assessment; carry-over disclosed.
- [ ] Arabic/RTL and English/LTR both render; layout mirrors correctly.
- [ ] Breakpoints 320 / 360 / 390 / 430 / 768 / 1024 / 1280–1440 px.
- [ ] Keyboard-only use works, including the Terminal input.
- [ ] No raw colour or size outside `tokens.css`; screens match the
      approved boards (spec §2); header wordmark is lockup B.
- [ ] Spec §13 Definition of Done items affected by the step still hold.

Report to Karim in short, plain language: what was built, what was tested
and observed, what is still open.
