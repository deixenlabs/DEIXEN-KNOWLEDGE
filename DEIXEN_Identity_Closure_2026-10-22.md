# DEIXEN — Identity closure sheet (2026-10-22)

Status: **proposal, self-review by the project lead (07 D17).** Nothing here is recorded in 07 yet.
Karim's answers turn §3 into a new 07 decision (draft in §5). Floor: Flight Deck prototype **r5**, approved by Karim
2026-10-22 ("r5 as the minimum"), with the per-step task facts (`stepFacts`) approved the same day.

## 1. Sources read for this sheet
- 07 and 13 from GitHub `deixenlabs/DEIXEN-KNOWLEDGE`, `main` = `5abee9e` (2026-10-17). The Project's copies of 07 and
  13 stop at D76 (2026-10-04) and are **out of date**. The repository holds D77–D90.
- `design/identity/DEIXEN_Identity_Kit.md` (Kit v0.2.1, chosen in D81).
- Chat records of 2026-10-20 (raven logo, lockup A, v11) and 2026-10-21/22 (Scenario Bank v1, Flight Deck C, r3–r5).
- r5 itself (`DEIXEN_FlightDeck_proto_r5.html`), inspected for corner radii, surfaces and lighting.

## 2. Diagnosis: why the identity still feels incomplete
DEIXEN has **two visual languages**, and only one is recorded.

| | Recorded (in the app since D84/D85) | Not recorded (Karim's choices since 2026-10-17) |
|---|---|---|
| Where | The Terminal kit: K1–K10 (D81), light, no boxes, typeset name (D83) | Flight Deck v11 → r5, raven logo, Scenario Bank v1 |
| Screens without a record | "Quiet by design" (D81 (b) 1); tests F4 and F5-B failed | Route band RUH → DXB carries the screen (direction C) |
| Name in the bar | "DEIXEN" set as text, no drawn mark (D83 (c)) | Raven-in-D mark + lockup A (2026-10-20) |
| Corners | 2 px for cells and controls, square elsewhere (K10, D81 (e)) | 8–12 px (r5: nav 8, capsule 12, buttons 6–8) |
| Surfaces | No surface, frame, card fill or shadow (D83 (b)) | Full-width tonal bands (containment B) |
| Light | One wide ambient light on every screen (D83 (a)) | None in r5 |
| Accent | No brand accent; red = errors and Reset everything (K7, D77 item 2) | Ember `#E34234` proposed as an app accent (2026-10-21); logo eye only (2026-10-20) |

The incompleteness comes from these two languages, not from a missing ornament. It closes when one kit covers
both, with one rule for each row above.

## 3. Decisions for Karim (D29 item 2: reserved)
| # | Question | Recommendation |
|---|---|---|
| 1 | Logo: the raven-in-D mark, open on the left, with lockup A, replaces the typeset name of D83 (c). The 16 px favicon limit is accepted. | **Agree** |
| 2 | Ember `#E34234` lives only in the raven's eye. It is never an app accent. Errors stay `#e5675f`. | **Agree** (two near reds on one screen would blur what red means) |
| 3 | Screens without a record carry the **route band** (direction C, r5) as a kit element (proposed K11). This replaces D81 (b) 1 ("quiet by design"). Full-width tonal bands are allowed: no border, corner, shadow or card. Boxes and cards stay forbidden. Amends D83 (b). | **Agree** |
| 4 | One corner rule for the whole product: (a) the Terminal's 2 px everywhere, or (b) r5's 8–12 px everywhere. See `CORNERS_r5_vs_2px.png`. | **(a) 2 px.** It comes from the character cell (K2), so the Terminal and the Flight Deck read as one product. |
| 5 | The D83 ambient light on the Flight Deck, which r5 does not have yet. | **Test next round** (one variable, render before deciding) |

Outside the identity: **Scenario Bank v1** (the scenario runs as a mode inside the Terminal). This changes where
the scenario runs (07 D57 (e), D59 (d); Build Spec §7B item 15). It is product structure, not look. It needs its own
decision and impact check, so it is kept out of this file.

## 4. What closes the identity file
1. Karim answers §3.
2. Kit v0.3 written: Kit v0.2.1 + logo + K11 route band + the bands rule + one corner rule + r5's bar.
3. Proof on a second screen with no record (Growth), so K11 is a rule, not a one-off. Then the "cover the name"
   test in English, Arabic and at 390 px.
4. The 07 decision recorded (§5). The app change then runs as a build task, like Step 4.
Learning, Ghost Mode and the Scenario Bank are then **application** of the kit, not identity work.

## 5. Draft record (filled in after Karim's answers)
**Decision 91 — The identity completed: the logo, the route band, one corner rule. Closed — Karim, [date]** (D29 item
2). Replaces D83 (c) (typeset name → raven-in-D lockup A); replaces D81 (b) 1 (screens with no record carry the route
band, K11); amends D83 (b) (full-width tonal bands allowed; no boxes); [corner rule per answer 4]; ember only in the
logo's eye, K7 unchanged. Kit v0.3 in `design/identity/` with sha256 in `MANIFEST.md`. Not affected: product
structure, learning logic and content, engine output, D30 placement, WCAG 2.1 AA, both languages (D80).

## 6. Blocker to recording
The Project's knowledge store is over its limit (2.57 MB of 2.0 MB), so writes are refused. Its copies of 07 and 13
are also 18 days old. Either remove old exploration files from the Project, or Karim uploads the decision files to
GitHub himself, as before.
