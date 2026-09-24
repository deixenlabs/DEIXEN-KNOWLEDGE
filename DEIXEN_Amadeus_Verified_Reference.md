---
name: DEIXEN Amadeus Verified Reference
status: CURRENT — second edition, 2026-09-25 (Execution Plan Phase 3.1–3.2). Scope so far: the first-build slice (07 Decisions 22, 24) and its prerequisites.
owns: The single authority for real Amadeus behavior (07 Decision 15). Only entries marked VERIFIED here may be taught or simulated (07 Decision 13).
does not own: product, curriculum, or learning decisions; what any DEIXEN code does (implementation truth)
---

# DEIXEN — Amadeus Verified Reference

## 1. How to read this file

- **VERIFIED** — meets the Verification Standard (07 Decision 12): a publicly
  readable official Amadeus source, or two independent trusted sources that
  agree; Cryptic interface; URL and access date recorded.
- **UNVERIFIED** — anything else, with the reason. Never taught as fact.
- **Evidence method (honest limit).** The main official source is Amadeus
  Service Hub (`servicehub.amadeus.com`), which Amadeus publishes openly. Its
  pages block automated full-page reading, so each entry below rests on the
  text the page itself exposes in search results. An entry is VERIFIED only
  when that exposed text states the claim directly — never by inference.
- All sources accessed **2026-09-25**. A source's own date is given where the
  source shows one.
- Scope: syntax and behavior described here are as the sources describe
  them. Office-profile settings, airline policies, and markets can change
  behavior; where a source says so, the entry says so.

## 2. Verified entries — first-build slice

### V-01 `AN` — Availability display — VERIFIED
- An availability display lists flights with at least one seat available for
  sale or waitlist; a schedule display lists all scheduled flights, including
  full or cancelled ones.
- Both displays cover up to 361 days ahead and 3 days back.
- Order: non-stop, then direct (stops, same flight number and aircraft), then
  connecting flights.
- Entry pattern shown by the source: transaction code, date, city pair,
  optional time — e.g. `AN14FEBSTOFRA1700`.
- Source: Amadeus Service Hub, "How to request a single air display (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/911144/how-to-request-a-single-air-display-cryptic-

### V-02 `AN` with airline code — VERIFIED
- A carrier-preferred display is requested by putting the airline code after
  the availability code — e.g. `ANMH06NOVKULSIN`.
- Source: Amadeus Service Hub, "How to request a carrier-preferred availability display (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/864341/how-to-request-a-carrier-preferred-availability-display

### V-03 `SS` — Segment sell — VERIFIED
- `SS` reserves seats on flights for a given class and date.
- Two forms: **short sell** from an availability or schedule display, and
  **long sell** when all flight details are known, without displaying
  availability first.
- Short-sell composition: `SS` + number of passengers + booking class + line
  number (source also notes `SG`/`PG` additions for groups).
- A confirmed sold segment appears in the PNR with status `HK` and a seat
  count (e.g. `HK1`), as the official PNR examples show.
- Sources: Amadeus Service Hub, "How to sell a flight (Cryptic)" (page dated
  2024-12-19) — https://servicehub.amadeus.com/c/portal/view-solution/784197/how-to-sell-a-flight-cryptic- ;
  "How to create a group PNR (Cryptic)" — https://servicehub.amadeus.com/c/portal/view-solution/842651/how-to-create-a-group-pnr-cryptic-

### V-04 `FQD` — Fare display — VERIFIED
- Basic entry: `FQD` + city pair (e.g. `FQDAMSNYC`). Options are added,
  each separated by a slash (e.g. `/A` airline, `/D` date, `/R,UP`).
- `+` and `@` indicators in the display mean: use `FQN` to see the fare
  rules. `FQN` + line number shows the fare notes for that line.
- Sources: Amadeus Service Hub — "How to request a Fare Display (FQD) with options (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/716365606/how-to-request-a-fare-display-fqd-with-options-cryptic- ;
  "How to interpret Fare Display (FQD) symbols (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/832707/how-to-interpret-fare-display-fqd-symbols-cryptic- ;
  "How to find fare rules after the PNR is priced and ticketed (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/3889546/how-to-find-fare-rules-after-the-pnr-is-priced-and-ticketed-cryptic-

### V-05 `FXP` — Itinerary pricing, stored — VERIFIED
- `FXP` prices a PNR keeping the booked classes and creates a TST (stored
  pricing record).
- When several fares apply, the system lists them; the agent selects one
  with `FXT` + fare number.
- Sources: Amadeus Service Hub, "How to price a PNR and keep the booked classes (Cryptic)" (2024-09-10) —
  https://servicehub.amadeus.com/c/portal/view-solution/965173/how-to-price-a-pnr-and-keep-the-booked-classes-cryptic- ;
  THAI-AMADEUS Southeast Asia training department, Amadeus fares quick card —
  https://www.thaiamadeus.com/THILA/file/QuickCardFare2016.pdf

### V-06 `FXX` — Itinerary pricing, not stored — VERIFIED
- `FXX` prices an itinerary without storing the result; `FXP` stores it in a
  TST. Service Hub names `FXX` and `FXP` together as itinerary pricing
  entries.
- This settles the old question (07 research backlog): `FXX` is a real
  Amadeus entry. The historical curriculum "correction" that excluded it was
  wrong.
- Sources: THAI-AMADEUS quick card (above); Amadeus Service Hub, "How to price a PNR for a specific passenger type (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/904438/how-to-price-a-pnr-for-a-specific-passenger-type-cryptic-

### V-07 `NM` — Passenger name — VERIFIED
- Name entry: `NM` + number + SURNAME/FIRST NAME TITLE (examples in the
  source: `NM1SIMPSON/MAGGIE(CHD/02JAN24)`, `NM2JONES/TOM MR/CANDY(CHD/05APR24)`).
- `CHD` for children aged 2–11, `INF` for infants up to 2; entering `CHD`
  generates an SSR telling the airline the passenger is a child.
- Sources: Amadeus Service Hub, "How to enter a name for a child or an infant (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/913799/how-to-enter-a-name-for-a-child-or-an-infant-cryptic- ;
  "How to create a name element with a passenger ID (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/812726/how-to-create-a-name-element-with-a-passenger-id

### V-08 Mandatory PNR elements — VERIFIED
- An Amadeus PNR is created with five basic mandatory elements, known as
  **PRINT**: Phone, Received from, Itinerary, Name, Ticketing.
- Source: Amadeus, "Amadeus Reservation Guidelines" (PDF hosted on Service Hub) —
  https://servicehub.amadeus.com/documents/20195/0/Amadeus+Reservation+Guidelines.pdf/069d4540-b9e6-f0b2-c701-f249b1fedd58?t=1583981454917

### V-09 `TK` — Ticketing arrangement — VERIFIED
- Entries: `TKOK`, or `TKTL` + date for a time limit.
- If the TK element is missing, ending the transaction (`ET`, `ER`, `ERK`)
  or issuing a ticket (`TTP`) can return **NEED TICKETING ARRANGEMENT**.
  Whether TK is mandatory depends on an office-profile setting; when it is
  optional, the system adds it automatically at end of transaction.
- Source: Amadeus Service Hub, "Error message: NEED TICKETING ARRANGEMENT" (2022-10-27) —
  https://servicehub.amadeus.com/c/portal/view-solution/966118/error-message-need-ticketing-arrangement

### V-10 `RF` and `ET`/`ER` — Received from, end of transaction — VERIFIED
- A PNR is completed with a Received From (`RF`) element and an end-of-
  transaction entry (`ET`; `ER` ends and redisplays).
- After end of transaction the RF field no longer shows in the PNR; it moves
  to the PNR history. In the Amadeus Training Environment the `--- RLR ---`
  tag does not appear.
- A PNR cannot be filed unless an RF element is present. Entry: `RF` +
  free text naming who requested the booking — official examples `RFMR SMITH`,
  `RFMR PAX`.
- Sources: Amadeus Service Hub, "How to add a Received From (RF) element (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/3999971/how-to-add-a-received-from-rf-element-cryptic- ;
  "How to split a PNR (Cryptic)" — https://servicehub.amadeus.com/c/portal/view-solution/920239/how-to-split-a-pnr-cryptic- ;
  "How to split a group PNR (Cryptic)" (2025-01-15, print view of solution 803842);
  "How to end the transaction in a PNR with ET or ER" —
  https://servicehub.amadeus.com/c/portal/view-solution/942980/how-to-end-the-transaction-in-a-pnr-with-et-or-er ;
  "How to create a group PNR (Cryptic)" (above)

### V-11 Contact element `AP` — VERIFIED (upgraded 2026-09-25)
- Entry: `AP` followed by the contact as free text. Official PNR displays
  show the resulting element as free text, e.g. `AP DREAM TRAVEL`,
  `AP A SMART TRAVEL +4655778899`, `APA +4688774455 SMART TRAVEL`.
- Typed variants shown by sources: `APM` mobile (displays e.g.
  `APM +447894562`), `APE` e-mail (displays e.g. `APE COLIN.ARCHER@EMAIL.COM`).
  Entry examples: `APBKK-02-2079000-B` (THAI-AMADEUS quick card);
  `APM-61 2 98766111/P2`, `APE-JCOLLINS@EMAIL.COM/P2` (Amadeus
  "Reservations Essentials: Common entries reference guide").
- For the slice, the verified minimum is `AP` + free-text phone. Sub-formats
  (city prefix, `-B`/`-A` type suffix, `/P` passenger association) are shown
  only as examples; they are not taught as rules.
- Evidence note: the official "Reservations Essentials" page is on Service
  Hub (solution 1029500472) but its entry table is readable only through a
  re-hosted copy (studylib.net, dated 2025-08-14). That copy is treated as
  one source; the THAI-AMADEUS card is the second, independent one; the
  official PNR displays confirm the stored form.
- Sources: THAI-AMADEUS, "SG quick card" —
  https://www.thaiamadeus.com/THILA/file/trn/SG%20-%20QUICK%20CARD_EN_V2.pdf ;
  Amadeus Service Hub, "Reservations Essentials: Common entries reference guide" —
  https://servicehub.amadeus.com/c/portal/view-solution/1029500472/reservations-essentials-common-entries-reference-guide
  (content read via https://studylib.net/doc/27673987/reservations-essentials--common-entries-reference-guide--...);
  official PNR displays: "How to split a PNR", "How to split a group PNR",
  "How to create a group PNR", "How to retrieve a PNR (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/453392470/how-to-retrieve-a-pnr-cryptic-

### V-12 Changing a priced PNR — VERIFIED (beyond the slice)
- Changing a name or itinerary after a TST exists flags the TST; ticketing
  then returns **ITINERARY/NAME CHANGE-VERIFY TST** until the TST is deleted
  (`TTE`) and the PNR repriced (`FXP`/`FXB`), or the flag is removed.
- Source: Amadeus Service Hub, "Error message: ITINERARY/NAME CHANGE-VERIFY TST" —
  https://servicehub.amadeus.com/c/portal/view-solution/950584/error-message-itinerary/name-change-verify-tst

### V-13 IATA passenger contact SSRs (`SRCTCM`/`SRCTCE`/`SRCTCR`) — VERIFIED
- Under IATA resolution 830d, agents must pass passenger contact details to
  the airline for irregular operations.
- Entries (source examples): mobile `SRCTCM-3054996244/US`; e-mail
  `SRCTCE-…` (some characters must be replaced, e.g. `@` → `//`);
  refusal `SRCTCR-REFUSED/P3`. The dash after `SRCTCM` is mandatory.
- If none of the three is present, end of transaction displays the warning
  **MISSING SSR CTCM MOBILE OR SSR CTCE EMAIL OR SSR CTCR NON-CONSENT**.
  Entering `ER`/`ET` again bypasses it, and the bypass is recorded in PNR
  history.
- `SRCTCM` is the entry the source gives for transferring the passenger's
  mobile to the airline. Official PNR displays show `AP…` and `SSR CTC…` as
  separate elements; entering `AP` does not satisfy this warning according to
  anything found (no source says it does).
- Source: Amadeus Service Hub, "How to add an email (SRCTCE) or mobile phone number (SRCTCM) in a PNR (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/3929673/how-to-add-an-email-srctce-or-mobile-phone-number-srctcm-in-a-pnr-cryptic-

## 3. Unverified — slice-relevant

| # | Claim | Reason |
|---|---|---|
| U-01 | `FXP` requires passenger names in the PNR | No source states it. **No longer blocks the slice:** the approved path (07 Decisions 22, 24) enters `NM` before `FXP`, so the slice never tests this case |
| U-02 | Exact error texts for wrong `AN`, `SS`, `NM`, `AP`, `FXP` input | Not found in exposed official text. Handled by 07 Decision 23 (clearly labeled training messages) |
| U-03 | ~~`AP` phone entry syntax~~ | Closed — now VERIFIED (V-11) |
| U-04 | Full screen layouts beyond what official examples show | Official pages show real example screens for `AN`, `FQD`, `FXP` and PNR displays; anything outside them is handled by 07 Decision 23 |
| U-05 | Whether a TST created by `FXP` after `ER` needs a further `ER`/`ET` to be kept in the PNR | Not found. The slice ends at a completed `FXP` display, so it does not simulate what happens to the TST afterwards |

## 4. Research backlog — outside the slice (not yet researched under D12)

`QE`/`QN`/`QD` queues; SSR/seat association; voiding; `FXL`/`TQT`/`TTE`/`FQF`
details; Amadeus Offers (`OFS`); post-ticketing segment status. Each stays
UNVERIFIED until researched.

## 5. Change log

| Date | Change |
|---|---|
| 2026-09-25 | First edition: V-01 to V-12, U-01 to U-04 |
| 2026-09-25 | Second edition: V-11 upgraded to VERIFIED; V-10 adds RF entry syntax; new V-13 (IATA contact SSRs); U-01 no longer blocking; U-03 closed; new U-05 |
