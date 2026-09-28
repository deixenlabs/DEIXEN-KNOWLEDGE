---
name: DEIXEN Amadeus Verified Reference
status: CURRENT — third edition, 2026-09-25 (Execution Plan Phase 3.1–3.2; screen layouts added for Build Spec gap G1); amended 2026-09-25 at the readiness check (3.6): U-12–U-14, handling note updated to 07 Decision 27; amended 2026-09-26 (07 Decision 49): V-14 weekday codes, V-18 segment line after end of transaction. Scope so far: the first-build slice (07 Decisions 22, 24) and its prerequisites.
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


## 2A. Verified screen layouts — first-build slice (Build Spec gap G1)

**How to read this section.** Each entry records the *layout* of an official
example screen: which fields appear, in which order, on which line. The
official screens are not copied here; they are described field by field,
and a **DEIXEN rendering** shows the same layout filled with DEIXEN's own
fictional practice data (07 D23; Build Spec §5). Search results flatten
the official screens into one line of text, so the *order* of fields and
lines is verified, but the exact number of spaces between columns is not
(see U-06). Where one field's *meaning* is not stated by any source, the
entry says so; such meanings are never taught.

### V-14 `AN` availability display — layout VERIFIED
- **Header line:** a banner between double asterisks naming the display
  (neutral display: `AMADEUS AVAILABILITY - AN`; carrier-preferred display:
  the airline's name, then `- AN`); then the destination code; the
  destination name, a dot and the country code; a number joined to a
  two-letter weekday; the date (DDMMM); a time (`0000` in both official
  examples, whose entries had no time).
- **Flight lines:** line number; airline code and flight number; the
  booking classes, each a letter followed by one figure (e.g. letter + `9`,
  letter + `0`); a slash and the origin; the destination; departure time;
  arrival time; a code group ending in the equipment code (e.g. `E0/73H`);
  total elapsed flying time (e.g. `1:15`). When a flight has more classes
  than fit, the class list continues on the next line under the first.
- Stated by the source: a display can show up to 26 classes; a flight is
  listed only if at least one class is available for sale or waitlist; a
  flight irregularity code, when present, sits after the equipment code
  and before the elapsed flying time.
- **Weekday codes (added 2026-09-26, 07 D49):** all seven two-letter codes
  appear in official example headers, each matching the calendar weekday of
  the date beside it: `MO` (02DEC 2024; 10MAR 2025), `TU` (10DEC 2024),
  `WE` (06NOV 2024; 19FEB 2025), `TH` (05DEC 2024; 13MAR 2025), `FR`
  (29NOV 2024; 14FEB 2025), `SA` (16NOV 2024), `SU` (the one official `AN`-header
  example reported in build session 2, 07 D48). An official
  flight-information display labels the same codes as its day column
  (`DY`: `SA` for 16NOV 2024 and `SU` for the arrival on the next day). So the weekday in the `AN` header
  is the weekday of the requested date, written `MO TU WE TH FR SA SU`.
  Sources (accessed 2026-09-26): Amadeus Service Hub, "How to request a
  single air display (Cryptic)" (`FR 14FEB`) —
  https://servicehub.amadeus.com/c/portal/view-solution/911144/how-to-request-a-single-air-display-cryptic- ;
  "How to request a carrier-preferred availability display (Cryptic)"
  (`WE 06NOV`) — URL below; "How to use 7-day search (Cryptic)"
  (`TH 05DEC`, `MO 02DEC`) —
  https://servicehub.amadeus.com/c/portal/view-solution/894176/how-to-use-7-day-search-cryptic- ;
  "How to display flight information (FLIFO) (Cryptic)" (`SA 16NOV`,
  `TU 10DEC`; `DY` column) —
  https://servicehub.amadeus.com/c/portal/view-solution/872846/how-to-display-flight-information-flifo-cryptic- ;
  "How to sell a flight (Cryptic)" (`WE 19FEB`, `MO 10MAR`, `TH 13MAR`) —
  V-15 URL; "How to waitlist a flight (Cryptic)" (`FR 29NOV`) —
  https://servicehub.amadeus.com/c/portal/view-solution/783251/how-to-waitlist-a-flight-cryptic-
- **Not stated by any source found (not taught):** the meaning of the
  number before the weekday in the header; the meaning of the figure after
  each class letter; the meaning of the `E0` code group. A non-official
  training deck describes the header number as days until departure and
  the class list with seat figures — one non-official source, so UNVERIFIED
  (U-09).
- DEIXEN rendering (fictional data):
  ```
  ** AMADEUS AVAILABILITY - AN ** DXB DUBAI.AE        30 SU 25OCT 0000
   1   6X 401  J9 C9 Y9 B9 M9 /RUH    DXB    0730    1030  E0/320  2:00
   2   6X 403  J4 C2 Y9 B9 M0 /RUH    DXB    1245    1545  E0/320  2:00
  ```
- Sources: Amadeus Service Hub, "How to request a carrier-preferred
  availability display (Cryptic)" (updated 2024-12-13; example display
  for `ANMH06NOVKULSIN`) —
  https://servicehub.amadeus.com/c/portal/view-solution/864341/how-to-request-a-carrier-preferred-availability-display ;
  "How to understand air availability display (AN) (Cryptic)" (print view
  dated 2025-04-29; annotated neutral display) —
  https://servicehub.amadeus.com/c/portal/view-solution/897281/how-to-understand-an-air-availability-display-an- ;
  non-official, for U-09 only: "Chapter 4 – Air Amadeus – Availability"
  (slideshare) — https://www.slideshare.net/slideshow/chapter-4-air-amadeus-availabilitypptx/260162654

### V-15 `SS` sell response — layout VERIFIED
- The response to a sell entry is the booking as it now stands, under a
  header line `RP/` + office ID + `/` (a new PNR's header: "RP followed by
  your Office ID" — V-18 source).
- **Segment line while the PNR is being built:** segment number; airline;
  flight number; booking class; date (DDMMM); one digit for the day of the
  week (Service Hub's ghost-segment page calls this field the day of the
  week; in the official retrieve-PNR example, 05JAN and 07JAN 2025 — a
  Sunday and a Tuesday — show `7` and `2`, i.e. Monday = 1 … Sunday = 7); city pair written together (e.g. `LHRFCO`); status and seat count
  (`HK1`); an optional terminal; departure time; arrival time; equipment;
  further one-letter codes (meanings not stated — not taught).
- Airline text may follow directly below the segment (official example:
  a pointer to `RTSVC`); the source says this text appears only when the
  seat is booked, not on a retrieved PNR, and its content varies by
  airline. DEIXEN shows no airline text.
- In the official example the PNR has no name yet and the segment is
  element **1** (see V-18 on numbering).
- DEIXEN rendering (fictional data):
  ```
  RP/XXXXXXXXX/
    1  6X 403 Y 25OCT 7 RUHDXB HK1       1245 1545  320 E 0
  ```
- Sources: Amadeus Service Hub, "How to sell a flight (Cryptic)"
  (2024-12-19) — https://servicehub.amadeus.com/c/portal/view-solution/784197/how-to-sell-a-flight-cryptic- ;
  "How to enter a ghost segment (Cryptic)" (day-of-week field) —
  https://live-travel.community.amadeus.com/c/portal/view-solution/893186/how-to-enter-a-ghost-segment-cryptic-

### V-16 `FQD` fare display — layout VERIFIED
- **Header lines:** the entry echoed; notice lines (e.g. that more fares
  are available in other currencies; that surcharges may apply — check the
  rule); a rate-of-exchange line (`ROE` …); a line joining date, city pair,
  a global indicator and mileage figures (`TPM`/`MPM`).
- **Column header:** `LN FARE BASIS OW <currency> RT …` followed by
  penalty, dates/days, advance purchase, minimum and maximum stay columns,
  then airline and fare-type columns.
- **Fare lines:** two-digit line number; `+` or `@` where applicable (V-04:
  use `FQN` for the rules); fare basis; the fare in the one-way or
  round-trip column; the remaining columns; closing with a page counter
  (`> PAGE 1/12`).
- DEIXEN renders only this layout; the meaning of the penalty, date,
  stay and fare-type columns is not taught (not needed for the slice).
- Sources: Amadeus Service Hub, "How to interpret Fare Display (FQD)
  symbols (Cryptic)" (listed as updated 2026-06-23) —
  https://servicehub.amadeus.com/c/portal/view-solution/832707/how-to-interpret-fare-display-fqd-symbols-cryptic- ;
  "How to request a Fare Display (FQD) for a past date ticket (Cryptic)"
  (single-airline example) —
  https://servicehub.amadeus.com/c/portal/view-solution/824651/how-to-request-a-fare-display-fqd-for-a-past-date-ticket-cryptic-

### V-17 `FXP` pricing response (single applicable fare) — layout VERIFIED
- Line order: the entry echoed; passenger number and name (`01` +
  SURNAME/FIRST, with or without title); `LAST TKT DTE` + date (one source
  adds `- DATE OF ORIGIN`); a dashed rule; the column header
  `AL FLGT BK T DATE TIME FARE BASIS NVB NVA BG`; the origin city on its
  own line; one line per segment (destination, airline, flight, booking
  class, a second class column, date, time, fare basis, validity dates,
  baggage); the fare line (currency and amount, then the fare calculation
  ending `END ROE…`); tax lines (currency, amount, tax code); the grand
  total; message lines (e.g. ticket stock or validating-carrier notices).
- Plain `FXP` shows this layout (THAI-AMADEUS card); official Service Hub
  pages show the same layout for `FXP/R,UP`, `FXP/FF-…`, `FXB` and `FXT`.
  When several fares apply, a numbered fare list appears instead (V-05) —
  not reached in the slice (Decision 25, K1).
- Not taught: the meaning of `NVB`, `NVA`, `BG`, the fare calculation
  line, or the tax codes.
- DEIXEN rendering (fictional data):
  ```
  FXP
  01 ALHARBI/SAAD MR
  LAST TKT DTE 25OCT26 - DATE OF ORIGIN
  ------------------------------------------------------------
       AL FLGT  BK T DATE  TIME  FARE BASIS      NVB  NVA   BG
   RUH
   DXB 6X   403 Y  Y 25OCT 1245  Y1OW                      1P
  SAR   900.00      25OCT26RUH 6X DXB240.00NUC240.00END ROE3.750000
  SAR   150.00-YR
  SAR  1050.00
  ```
- Sources: Amadeus Service Hub, "How to price a PNR and keep the booked
  classes (Cryptic)" (2024-09-10) —
  https://servicehub.amadeus.com/c/portal/view-solution/965173/how-to-price-a-pnr-and-keep-the-booked-classes-cryptic- ;
  THAI-AMADEUS fares quick card (plain `FXP` example) —
  https://www.thaiamadeus.com/THILA/file/QuickCardFare2016.pdf ;
  "How to price a PNR with Fare Family option (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/879731/how-to-price-a-pnr-with-fare-family-option-cryptic-

### V-18 PNR display — header, element order, numbering — VERIFIED
- **Header:** generated after the first entry of a new PNR as `RP/` +
  office ID; when the transaction is ended and the PNR redisplayed, more
  information is added to the header line — in the official examples:
  office IDs, agent sign/duty code, date/time (Z), and a six-character
  record locator. Tags such as `RLR` or `TST` may appear above the header
  (V-10: `RLR` does not appear in the Amadeus Training Environment). The
  official examples mask office IDs as `XXXXXXXXX`; DEIXEN does the same.
- **Element order** in every official display found: names (`1.SURNAME/
  FIRST TITLE`), then air segments, then contact (`AP…`), then `TK`, then
  SSR and other elements.
- **Numbering:** every displayed element carries its number in the PNR
  *as it stands*: in the sell response (V-15) the segment is element 1
  because no name exists yet; in every PNR that has a name, the name is 1
  and the first segment is 2. The same holds for `TK` and SSR elements:
  `TK` is always displayed before SSRs, whatever order they were entered in.
- **Displayed forms:** a stored ticketing arrangement shows as
  `TK OK` + date + `/` + office (in the official examples the date equals
  the PNR's creation date); a stored mobile contact SSR shows as
  `SSR CTCM` + airline + `HK1` + number; after end of transaction, segment
  lines end with `*1A/E*`.
- **Segment line after end of transaction (added 2026-09-26, 07 D49):** in
  every official redisplay after end of transaction found, the segment line
  is: element number; airline and flight number; booking class; date; the
  one-digit day of the week; city pair; status and seat count; an optional
  terminal; departure time; arrival time; `*1A/E*`. The equipment and the
  one-letter codes of the sell response (V-15) are not shown. Examples:
  `2 KL1196 T 05JAN 7 OSLAMS HK1 0630 0830 *1A/E*`;
  `2 SQ 351 Z 04MAY 7 CPHSIN HK1 3 1155 0625+1 *1A/E*`. Sources (accessed
  2026-09-26): "How to retrieve/display a PNR (Cryptic)" (URL below);
  "How to copy a PNR (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/917534/copy-a-displayed-pnr-with-a-link-to-the-original-booking ;
  "How to add Special Service Requests (SSRs) to a PNR (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/968144/how-to-add-ssr-elements-to-a-pnr-cryptic-
  DEIXEN rendering (fictional data):
  ```
    2  6X 403 Y 25OCT 7 RUHDXB HK1  1245 1545  *1A/E*
  ```
- The response to an individual name entry is the PNR redisplayed under
  the `RP/` header (official group-name example). Official redisplay
  examples were found for `SS` and `NM`; none was found for `AP`,
  `SRCTCM`/`SRCTCR`, `TK`, or `RF` entries (U-11).
- Sources: Amadeus Service Hub, "How to interpret a PNR header line
  (Cryptic)" — https://servicehub.amadeus.com/c/portal/view-solution/3868887/how-to-interpret-a-pnr-header-line-cryptic- ;
  "How to retrieve/display a PNR (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/453392470/how-to-retrieve/display-a-pnr-cryptic- ;
  "How to display Minimum Connecting Time (MCT) from a PNR (Cryptic)" —
  https://servicehub.amadeus.com/c/portal/view-solution/769622/how-to-display-minimum-connecting-time-mct-from-a-pnr-cryptic- ;
  "How to add a form of identification (FOID) to a PNR (Cryptic)"
  (`SSR CTCM` display) —
  https://servicehub.amadeus.com/c/portal/view-solution/890757/how-to-add-a-form-of-identification-foid-to-a-pnr-cryptic- ;
  "How to create a group name (Cryptic)" (redisplay after a name entry) —
  https://servicehub.amadeus.com/c/portal/view-solution/933799/how-to-create-a-group-name-cryptic- ;
  "How to sell a flight (Cryptic)" (V-15).

## 3. Unverified — slice-relevant

| # | Claim | Reason |
|---|---|---|
| U-01 | `FXP` requires passenger names in the PNR | No source states it. **No longer blocks the slice:** the approved path (07 Decisions 22, 24) enters `NM` before `FXP`, so the slice never tests this case |
| U-02 | Exact error texts for wrong `AN`, `SS`, `NM`, `AP`, `FXP` input | Not found in exposed official text. Handled by 07 Decision 23 (clearly labeled training messages) |
| U-03 | ~~`AP` phone entry syntax~~ | Closed — now VERIFIED (V-11) |
| U-04 | Full screen layouts beyond what official examples show | Layouts now recorded for `AN`, `SS`, `FQD`, `FXP` and the PNR (V-14–V-18). Anything outside them is handled by 07 Decision 23 |
| U-05 | Whether a TST created by `FXP` after `ER` needs a further `ER`/`ET` to be kept in the PNR | Not found. The slice ends at a completed `FXP` display, so it does not simulate what happens to the TST afterwards |
| U-06 | Exact column spacing of every screen | Search results flatten the official screens; field order is verified (V-14–V-18), spacing is not. DEIXEN aligns columns in a fixed-width font — a presentation choice, disclosed |
| U-07 | How a contact SSR entered without an airline code is displayed (whether the airline code is filled in); any official display of a stored `SSR CTCR` | Only a display of `SSR CTCM` with an airline code was found (V-18); no Amadeus `CTCR` display found (airline pages show other GDSs only) |
| U-08 | How the `RF` element looks in the PNR before end of transaction | No official display found (V-10 only says it disappears after end of transaction) |
| U-09 | Meaning of the header number before the weekday, of the figure after each class letter, and of `E0` in `AN` | One non-official source only (V-14) |
| U-10 | The `AN` header time when the entry includes a departure time | Both official examples had no time and show `0000` |
| U-11 | That `AP`, `SRCTCM`/`SRCTCR`, `TK` and `RF` entries are answered with a PNR redisplay | Official redisplay examples exist for `SS` and `NM` only (V-15, V-18) |
| U-12 | What must follow the number or text in a contact SSR: whether an ending is required, and what it contains | Conflicting / non-official sources. Every official example has an ending: `SRCTCM-3054996244/US`, `SRCTCMAFHK1-0034563214/P1`, `SRCTCR-REFUSED/P3`, `SRCTCRSNHK1-REFUSED/P4` (Service Hub page of V-13). Two re-hosted training references describe the ending as a slash and the country of the phone number (`SRCTCM-4164915050/CA`; `SRCTCM-9837486432/XX`) — provenance not established. An airline notice gives the bare format `SRCTCM-Phone number`. Sources: https://www.scribd.com/document/873058229/Amadeus-Quick-Reference-PNR-Formats-Part-Two ; https://www.scribd.com/document/791436192/Amadeus-Quick-Reference ; Turkish Airlines notice, https://airc.ir/Circular/2020/TK/Passenger-Information.pdf (all accessed 2026-09-25). Handled by Build Spec §12 K7 |
| U-13 | Which name titles are accepted besides `MR` (e.g. `MS`, `MRS`) | Official examples found show `MR` or no title (V-07, V-10, V-18); one non-official source lists `MR`/`MS` only. The slice uses `MR` |
| U-14 | That the PRINT "Phone" element (V-08) is the `AP` element | No source states it directly. An official course outline lists "How to add the AP, RF and TK elements" under PNR mandatory elements (https://www.learn.amadeus.com/OnlineCourse-1513851695-module-24.en.htm) — suggestive, not a statement. The slice requires `AP` as a DEIXEN task rule; its message does not claim Amadeus behavior |

Handling of U-06–U-11 in the slice: 07 Decision 27 (K6) — partly shown
details (U-07 first part, U-09, U-10, U-11) are drawn in the verified
pattern with a "Layout detail not fully verified" marker, never taught, and
disclosed; details with no official pattern (U-07 second part, U-08) are
training messages under 07 Decision 23. Details: Build Spec §5. U-12–U-14:
Build Spec §6 and §12.

## 4. Research backlog — outside the slice (not yet researched under D12)

`QE`/`QN`/`QD` queues; SSR/seat association; voiding; `FXL`/`TQT`/`TTE`/`FQF`
details; Amadeus Offers (`OFS`); post-ticketing segment status. Each stays
UNVERIFIED until researched.

## 5. Change log

| Date | Change |
|---|---|
| 2026-09-25 | First edition: V-01 to V-12, U-01 to U-04 |
| 2026-09-25 | Second edition: V-11 upgraded to VERIFIED; V-10 adds RF entry syntax; new V-13 (IATA contact SSRs); U-01 no longer blocking; U-03 closed; new U-05 |
| 2026-09-25 | Third edition (Build Spec G1): new §2A with screen layouts V-14 (`AN`), V-15 (`SS`), V-16 (`FQD`), V-17 (`FXP`), V-18 (PNR header, order, numbering); U-04 narrowed; new U-06–U-11 |
| 2026-09-25 | Amendment (readiness check 3.6): new U-12 (contact-SSR endings), U-13 (name titles), U-14 (`AP` as PRINT Phone); §3 handling note now cites 07 Decision 27; V-17 rendering uses the task passenger `ALHARBI/SAAD MR` (fictional data only). No V- entry changed |
| 2026-09-26 | Amendment (07 Decision 49): V-14 — the seven weekday codes of the `AN` header verified from official examples (Karim's in-session answer to app issue I-5 confirmed); V-18 — segment line after end of transaction recorded. U-09 unchanged (the header number's meaning stays unverified) |
