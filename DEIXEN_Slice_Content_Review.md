# DEIXEN — Slice Content: Review Copy (G2 + G3)

> **Reading copy for Karim's review — not a project file.** The source of truth is the three content files for `deixen-app/content/` (`data/slice.json`, `en/text.json`, `ar/text.json`); this page is generated from them. Author: Claude (project lead), 2026-09-25. Self-review only (07 D17). **Updated 2026-09-25 (readiness check 3.6):** Decision 27 applied; seven small fixes marked ✎ below, all awaiting Karim's approval at the Phase 3 gate.

Every Amadeus statement traces to a VERIFIED entry in `DEIXEN_Amadeus_Verified_Reference.md` (third edition). All flights, fares, names and numbers are fictional.

## 1. Task and scenario

**Book and price a one-way flight** / حجز رحلة ذهاب فقط وتسعيرها

- ✎ EN: Mr Saad Alharbi wants one seat from Riyadh (RUH) to Dubai (DXB) on {TASK_DATE}, on flight 6X 403 in class Y. Your agency's phone: 966110000000. His mobile for the airline: 966500000001. Ticketing arrangement: TKOK. He requested the booking himself. Build the booking, end the transaction, then price it.
- ✎ AR: السيد سعد الحربي يريد مقعدًا واحدًا من الرياض (RUH) إلى دبي (DXB) بتاريخ {TASK_DATE}، على الرحلة 6X 403 بالدرجة Y. هاتف وكالتك: 966110000000. جواله لإرساله لشركة الطيران: 966500000001. ترتيب إصدار التذكرة: TKOK. وهو من طلب الحجز بنفسه. أنشئ الحجز، وأنهِ المعاملة، ثم سعّره.

**Scenario: the passenger refuses to give a mobile number** / سيناريو: الراكب يرفض إعطاء رقم جواله

- EN: Mr Fahad Alqahtani wants one seat from Jeddah (JED) to Dubai (DXB) on {SCN_DATE}, on flight 6X 515 in class B. Your agency's phone: 966110000000. When you ask for his mobile number or e-mail for the airline, he says he does not want to share them. Ticketing arrangement: TKOK. He requested the booking himself. Build the booking, end the transaction, then price it.
- AR: السيد فهد القحطاني يريد مقعدًا واحدًا من جدة (JED) إلى دبي (DXB) بتاريخ {SCN_DATE}، على الرحلة 6X 515 بالدرجة B. هاتف وكالتك: 966110000000. عندما تطلب رقم جواله أو بريده الإلكتروني لإرسالهما لشركة الطيران، يقول إنه لا يريد مشاركتهما. ترتيب إصدار التذكرة: TKOK. وهو من طلب الحجز بنفسه. أنشئ الحجز، وأنهِ المعاملة، ثم سعّره.

| Step | Main task — expected entry | Scenario — expected entry |
|---|---|---|
| AN | `AN{TASK_DATE}RUHDXB` | `AN{SCN_DATE}JEDDXB` |
| SS | `SS1Y2` | `SS1B3` |
| NM | ✎ `NM1ALHARBI/SAAD MR` | `NM1ALQAHTANI/FAHAD MR` |
| AP | `AP966110000000` | `AP966110000000` |
| CTC | `SRCTCM-966500000001` (an ending such as `/US` is accepted, not checked — ✎ K7) | `SRCTCR-REFUSED` |
| TK | `TKOK` | `TKOK` |
| RF | ✎ `RFMR ALHARBI` | `RFMR ALQAHTANI` |
| ER | `ER` | `ER` |
| FXP | `FXP` | `FXP` |

Scenario contract (07): objective — Complete and price the booking while recording, correctly, that the passenger refused to share contact details with the airline. · constraints — One adult, one flight, class B on 6X 515. No mobile number or e-mail is available. Do not invent contact details and do not bypass the end-of-transaction warning. · differentiating condition — The passenger refuses to give a mobile number or e-mail. The learner must record the refusal with SRCTCR instead of transferring a mobile with SRCTCM (V-13). · load-bearing skills — CTC, ER · acceptance — Scenario completed = the full scenario path with every checklist item met; the CTC step satisfied by SRCTCR (not by bypassing the warning with a second ER). · assessment linkage — Not the formal assessment (Build Spec §9). Completing the scenario is one of the three conditions of 'Completed' (Build Spec §10, K4). · evidence linkage — Events carry context='scenario' and scenarioId='scn-refuses-mobile' (Build Spec §11). TRANSFERRED is possible only for CTC and ER (load-bearing), and only on independent full-checklist success (Build Spec §7). · state integrity — Starts a fresh practice PNR; does not change the main task, other skills' data, or any global setting.

## 2. Lessons (schema of file 03)

Common: practiceBridge = Terminal, task 'task-main', step = the lesson's skill (L10-FQD: optional step); completionRule = The learner reaches the end of the lesson body and presses the practice button. Records lesson_completed only; never skill evidence (Build Spec §3).

### L01-AN — Find flights with AN / البحث عن الرحلات بالأمر AN

Verified basis: V-01, V-02, V-03, V-14 · Example: `AN14FEBSTOFRA1700` (official (V-01)) · Prerequisite: —

**EN — Request an availability display for a date and a city pair.**

An availability display lists the flights that have at least one seat available for sale or waitlist. It covers dates up to 361 days ahead and up to 3 days back.

Flights appear in this order: non-stop flights first, then direct flights (stops, same flight number and aircraft), then connecting flights.

The entry is AN, then the date (day and three-letter month), then the origin and destination city codes written together. You may add a departure time at the end. Official example: AN14FEBSTOFRA1700.

To ask for one airline's display, put its code right after AN — official example: ANMH06NOVKULSIN.

Every flight in the display starts with a line number. Keep it in mind: the next step uses it. Each booking class appears as a letter followed by a figure; a display can show up to 26 classes.

<div dir="rtl">

**AR — طلب عرض التوافر لتاريخ ومسار (مدينتين) محددين.**

تعرض شاشة التوافر الرحلاتِ التي فيها مقعد واحد على الأقل متاح للبيع أو لقائمة الانتظار. وتغطي التواريخ حتى 361 يومًا قادمة وحتى 3 أيام ماضية.

تظهر الرحلات بهذا الترتيب: الرحلات بدون توقف أولًا، ثم الرحلات المباشرة (فيها توقف بنفس رقم الرحلة ونفس الطائرة)، ثم رحلات الربط.

يُكتب الأمر هكذا: AN، ثم التاريخ (اليوم ثم الشهر بثلاثة أحرف)، ثم رمزا مدينتي المغادرة والوصول متصلين. ويمكنك إضافة وقت المغادرة في النهاية. مثال رسمي: AN14FEBSTOFRA1700.

لطلب عرض خاص بشركة طيران واحدة، ضع رمزها مباشرة بعد AN — مثال رسمي: ANMH06NOVKULSIN.

كل رحلة في الشاشة تبدأ برقم سطر. تذكّره، فالخطوة التالية تستخدمه. وتظهر كل درجة حجز حرفًا يليه رقم، ويمكن أن تعرض الشاشة حتى 26 درجة.

</div>

Ghost Mode (demo booking): `AN{DEMO_DATE}RUHJED` — each entry followed by a pause and a live `reveal`.

### L02-SS — Sell a seat with SS / بيع مقعد بالأمر SS

Verified basis: V-03, V-15 · Example: `SS1M3` (DEIXEN example built from the V-03 pattern) · Prerequisite: L01-AN

**EN — Sell seats in one booking class from the line of an availability display.**

SS reserves seats on a flight for a given class and date. When you sell from an availability display, this is called a short sell.

The short sell is written: SS, then the number of seats, then the booking class, then the line number from the display. Example built from this pattern: SS1M3 (one seat, class M, line 3).

The system answers by showing the booking as it now stands. A confirmed segment shows the status HK with the seat count, for example HK1.

In DEIXEN's tasks, the number of seats equals the number of passengers in the task.

<div dir="rtl">

**AR — بيع مقاعد في درجة حجز واحدة من سطر في شاشة التوافر.**

الأمر SS يحجز مقاعد على رحلة لدرجة وتاريخ محددين. وعندما تبيع من شاشة التوافر يُسمّى ذلك البيع المختصر (short sell).

يُكتب البيع المختصر هكذا: SS، ثم عدد المقاعد، ثم درجة الحجز، ثم رقم السطر من الشاشة. مثال مبني على هذا النمط: SS1M3 (مقعد واحد، الدرجة M، السطر 3).

يرد النظام بعرض الحجز كما أصبح. ويظهر المقطع المؤكَّد بالحالة HK مع عدد المقاعد، مثل HK1.

في مهام DEIXEN يكون عدد المقاعد مساويًا لعدد الركاب في المهمة.

</div>

Ghost Mode (demo booking): `AN{DEMO_DATE}RUHJED` → `SS1M1` — each entry followed by a pause and a live `reveal`.

### L03-NM — Add the passenger name with NM / إضافة اسم الراكب بالأمر NM

Verified basis: V-07, V-08, V-18 · Example: `NM1JONES/TOM MR` (DEIXEN example built from the V-07 pattern (official NM2JONES/TOM MR/…)) · Prerequisite: L02-SS

**EN — Enter the passenger's name with the correct count, surname, first name and title.**

The name element is written: NM, then the number of passengers, then SURNAME/FIRST NAME and the title. Example built from this pattern: NM1JONES/TOM MR.

The name is one of the five mandatory elements of a booking, known as PRINT: Phone, Received from, Itinerary, Name, Ticketing.

In a booking display, names always come first, before the flights. That is why, once you add a name, the flight you sold is shown on line 2 instead of line 1: each line number always shows the element's place in the booking as it stands now.

<div dir="rtl">

**AR — إدخال اسم الراكب بالعدد الصحيح واسم العائلة والاسم الأول واللقب.**

يُكتب عنصر الاسم هكذا: NM، ثم عدد الركاب، ثم اسم العائلة/الاسم الأول ثم اللقب. مثال مبني على هذا النمط: NM1JONES/TOM MR.

الاسم واحد من العناصر الخمسة الإلزامية في الحجز، المعروفة باسم PRINT: الهاتف (Phone)، ومَن طلب الحجز (Received from)، وخط السير (Itinerary)، والاسم (Name)، وترتيب إصدار التذكرة (Ticketing).

في عرض الحجز تأتي الأسماء دائمًا أولًا قبل الرحلات. لذلك بعد إضافة الاسم تظهر الرحلة التي بعتها في السطر 2 بدلًا من السطر 1: فرقم كل سطر يدل دائمًا على مكان العنصر في الحجز كما هو الآن.

</div>

Ghost Mode (demo booking): `AN{DEMO_DATE}RUHJED` → `SS1M1` → `NM1SALEM/OMAR MR` — each entry followed by a pause and a live `reveal`.

### L04-AP — Add a contact with AP / إضافة جهة اتصال بالأمر AP

Verified basis: V-08, V-11, V-18 · Example: `AP966120000000` (DEIXEN example (fictional number) built from V-11) · Prerequisite: L03-NM

**EN — Add the booking's contact element as free text with the phone number the task gives.**

AP adds a contact element. After AP you write the contact as free text. Example with a fictional number: AP966120000000.

The booking shows it as a separate element that starts with AP.

In this slice, the booking's phone is added with AP, using the phone number the task gives you.

<div dir="rtl">

**AR — إضافة عنصر الاتصال في الحجز كنص حر برقم الهاتف الذي تعطيه المهمة.**

الأمر AP يضيف عنصر اتصال. بعد AP تكتب بيانات الاتصال كنص حر. مثال برقم وهمي: AP966120000000.

يظهر في الحجز كعنصر مستقل يبدأ بـ AP.

في هذا الجزء من التدريب يُضاف هاتف الحجز بالأمر AP، باستخدام رقم الهاتف الذي تعطيك إياه المهمة.

</div>

Ghost Mode (demo booking): `AN{DEMO_DATE}RUHJED` → `SS1M1` → `NM1SALEM/OMAR MR` → `AP966120000000` — each entry followed by a pause and a live `reveal`.

### L05-CTC — Pass the passenger's contact to the airline: SRCTCM (and SRCTCR) / إرسال بيانات اتصال الراكب لشركة الطيران: SRCTCM (و SRCTCR)

Verified basis: V-13, V-18 · Example: `SRCTCM-966500000009` (DEIXEN example (fictional number) built from V-13) · Prerequisite: L04-AP

**EN — Transfer the passenger's mobile number to the airline with SRCTCM, or record a refusal with SRCTCR.**

Under IATA resolution 830d, agents must pass the passenger's contact details to the airline, for use during irregular operations (for example, flight disruptions).

To pass a mobile number, write SRCTCM, a dash, then the number. Example with a fictional number: SRCTCM-966500000009. The dash after SRCTCM is mandatory. ✎ Official example: SRCTCM-3054996244/US (the ending /US is outside this slice).

If the passenger refuses to share contact details, record the refusal: SRCTCR, a dash, then a short free text such as REFUSED. Official example: SRCTCR-REFUSED/P3 (the ending /P3 is outside this slice).

The AP element and this contact SSR are separate elements in the booking. If none of SRCTCM, SRCTCE (e-mail) or SRCTCR is present, ending the transaction shows a warning.

<div dir="rtl">

**AR — تحويل رقم جوال الراكب إلى شركة الطيران بالأمر SRCTCM، أو تسجيل رفضه بالأمر SRCTCR.**

بموجب قرار IATA رقم 830d يجب على الوكلاء تمرير بيانات اتصال الراكب إلى شركة الطيران، لاستخدامها عند اضطراب التشغيل (مثل تعطّل الرحلات).

لتمرير رقم الجوال اكتب SRCTCM ثم شرطة ثم الرقم. مثال برقم وهمي: SRCTCM-966500000009. الشرطة بعد SRCTCM إلزامية. ✎ مثال رسمي: SRCTCM-3054996244/US (الجزء الأخير /US خارج نطاق هذا الجزء من التدريب).

إذا رفض الراكب مشاركة بيانات الاتصال، سجّل الرفض: SRCTCR ثم شرطة ثم نص حر قصير مثل REFUSED. مثال رسمي: SRCTCR-REFUSED/P3 (الجزء الأخير /P3 خارج نطاق هذا الجزء من التدريب).

عنصر AP وعنصر SSR هذا عنصران منفصلان في الحجز. وإذا لم يوجد أيٌّ من SRCTCM أو SRCTCE (البريد الإلكتروني) أو SRCTCR، يظهر تحذير عند إنهاء المعاملة.

</div>

Ghost Mode (demo booking): `AN{DEMO_DATE}RUHJED` → `SS1M1` → `NM1SALEM/OMAR MR` → `AP966120000000` → `SRCTCM-966500000009` — each entry followed by a pause and a live `reveal`.

### L06-TK — Set the ticketing arrangement with TK / تحديد ترتيب إصدار التذكرة بالأمر TK

Verified basis: V-08, V-09, V-18 · Example: `TKOK` (official (V-09)) · Prerequisite: L05-CTC

**EN — Add the ticketing arrangement element the task asks for.**

The ticketing arrangement is the T of PRINT. Two entries: TKOK, or TKTL followed by a date for a time limit.

If the TK element is missing, ending the transaction can return the message NEED TICKETING ARRANGEMENT. Whether TK is mandatory depends on the office's settings; in DEIXEN's practice office it is mandatory.

The booking shows TKOK as TK OK followed by the date and the office.

<div dir="rtl">

**AR — إضافة عنصر ترتيب إصدار التذكرة الذي تطلبه المهمة.**

ترتيب إصدار التذكرة هو حرف T في PRINT. وله أمران: TKOK، أو TKTL متبوعًا بتاريخ لتحديد مهلة.

إذا غاب عنصر TK، قد يعيد إنهاءُ المعاملة الرسالة NEED TICKETING ARRANGEMENT. وكون TK إلزاميًا أم لا يعتمد على إعدادات المكتب؛ وفي مكتب التدريب في DEIXEN هو إلزامي.

يظهر TKOK في الحجز بالشكل TK OK متبوعًا بالتاريخ والمكتب.

</div>

Ghost Mode (demo booking): `AN{DEMO_DATE}RUHJED` → `SS1M1` → `NM1SALEM/OMAR MR` → `AP966120000000` → `SRCTCM-966500000009` → `TKOK` — each entry followed by a pause and a live `reveal`.

### L07-RF — Record who asked for the booking: RF / تسجيل مَن طلب الحجز: RF

Verified basis: V-08, V-10 · Example: `RFMR SMITH` (official (V-10)) · Prerequisite: L06-TK

**EN — Add the Received From element naming who requested the booking.**

RF records who asked for the booking. Write RF, then free text naming that person. Official example: RFMR SMITH.

A booking cannot be filed unless an RF element is present. After the transaction ends, RF no longer shows in the booking; it moves to the booking's history.

<div dir="rtl">

**AR — إضافة عنصر Received From الذي يذكر مَن طلب الحجز.**

الأمر RF يسجّل مَن طلب الحجز. اكتب RF ثم نصًا حرًا باسم ذلك الشخص. مثال رسمي: RFMR SMITH.

لا يمكن حفظ الحجز دون وجود عنصر RF. وبعد إنهاء المعاملة لا يظهر RF في الحجز، بل ينتقل إلى سجل الحجز.

</div>

Ghost Mode (demo booking): `AN{DEMO_DATE}RUHJED` → `SS1M1` → `NM1SALEM/OMAR MR` → `AP966120000000` → `SRCTCM-966500000009` → `TKOK` → `RFMR SALEM` — each entry followed by a pause and a live `reveal`.

### L08-ER — End the transaction with ER / إنهاء المعاملة بالأمر ER

Verified basis: V-08, V-09, V-10, V-13, V-18 · Example: `ER` (official (V-10)) · Prerequisite: L07-RF

**EN — End the transaction when every required element is present, and read the result.**

ER ends the transaction and redisplays the booking. (ET also ends the transaction.)

Before ER, check PRINT — Phone, Received from, Itinerary, Name, Ticketing — and the passenger contact SSR.

If TK is missing, you can get NEED TICKETING ARRANGEMENT. If no contact SSR is present, you get the warning MISSING SSR CTCM MOBILE OR SSR CTCE EMAIL OR SSR CTCR NON-CONSENT. Entering ER again bypasses that warning, but the bypass is recorded in the booking's history; in DEIXEN's tasks the contact SSR must be added instead.

When the transaction ends, the header line gets more information, including the six-character record locator used to retrieve the booking.

<div dir="rtl">

**AR — إنهاء المعاملة عندما تكتمل كل العناصر المطلوبة، وقراءة النتيجة.**

الأمر ER ينهي المعاملة ويعيد عرض الحجز. (والأمر ET أيضًا ينهي المعاملة.)

قبل ER راجع PRINT — الهاتف، ومَن طلب الحجز، وخط السير، والاسم، وترتيب إصدار التذكرة — وعنصر SSR لاتصال الراكب.

إذا غاب TK قد تظهر الرسالة NEED TICKETING ARRANGEMENT. وإذا لم يوجد عنصر SSR للاتصال يظهر التحذير MISSING SSR CTCM MOBILE OR SSR CTCE EMAIL OR SSR CTCR NON-CONSENT. إدخال ER مرة ثانية يتجاوز هذا التحذير، لكن التجاوز يُسجَّل في سجل الحجز؛ وفي مهام DEIXEN يجب إضافة عنصر الاتصال بدلًا من التجاوز.

عند إنهاء المعاملة يُضاف إلى سطر العنوان مزيد من المعلومات، منها رمز الحجز المكوّن من ستة أحرف الذي يُستخدم لاسترجاع الحجز.

</div>

Ghost Mode (demo booking): `AN{DEMO_DATE}RUHJED` → `SS1M1` → `NM1SALEM/OMAR MR` → `AP966120000000` → `SRCTCM-966500000009` → `RFMR SALEM` → `ER` → `TKOK` → `ER` — each entry followed by a pause and a live `reveal`.

### L09-FXP — Price the booking with FXP / تسعير الحجز بالأمر FXP

Verified basis: V-05, V-06, V-17 · Example: `FXP` (official (V-05)) · Prerequisite: L08-ER

**EN — Price the booking in its booked class and store the result.**

FXP prices the booking keeping the booked classes, and stores the result in a TST (a stored pricing record). FXX prices without storing anything.

When several fares apply, the system lists them and the agent chooses one with FXT and the fare number. In this slice only one fare applies, so you will not need FXT.

The pricing display starts with the passenger, then a table of the flights with the booking class and the fare basis, then the fare and tax lines.

<div dir="rtl">

**AR — تسعير الحجز بدرجته المحجوزة وحفظ النتيجة.**

الأمر FXP يسعّر الحجز مع الإبقاء على درجات الحجز كما هي، ويحفظ النتيجة في TST (سجل تسعير محفوظ). أما FXX فيسعّر دون حفظ أي شيء.

عندما تنطبق عدة أسعار يعرضها النظام في قائمة، ويختار الوكيل واحدًا بالأمر FXT ورقم السعر. في هذا الجزء من التدريب ينطبق سعر واحد فقط، فلن تحتاج FXT.

تبدأ شاشة التسعير بالراكب، ثم جدول الرحلات مع درجة الحجز وأساس السعر (fare basis)، ثم أسطر السعر والضرائب.

</div>

Ghost Mode (demo booking): `AN{DEMO_DATE}RUHJED` → `SS1M1` → `NM1SALEM/OMAR MR` → `AP966120000000` → `SRCTCM-966500000009` → `TKOK` → `RFMR SALEM` → `ER` → `FXP` — each entry followed by a pause and a live `reveal`.

### L10-FQD — Optional: look at fares with FQD / اختياري: عرض الأسعار بالأمر FQD (optional)

Verified basis: V-04, V-16 · Example: `FQDAMSNYC` (official (V-04)) · Prerequisite: L01-AN

**EN — Display the fares for a city pair.**

FQD displays fares for a city pair: FQD followed by the city pair. Official example: FQDAMSNYC. Options come after the city pair, each after a slash.

A + or @ next to a fare means the fare rules can be read with FQN and the line number. FQN is outside this slice.

This step is optional; it is not needed to complete the slice.

<div dir="rtl">

**AR — عرض الأسعار لمسار بين مدينتين.**

الأمر FQD يعرض الأسعار لمسار: FQD متبوعًا برمزي المدينتين. مثال رسمي: FQDAMSNYC. وتأتي الخيارات بعد رمزي المدينتين، كل خيار بعد شرطة مائلة.

علامة + أو @ بجانب السعر تعني أنه يمكن قراءة شروط السعر بالأمر FQN ورقم السطر. والأمر FQN خارج نطاق هذا الجزء.

هذه الخطوة اختيارية وليست مطلوبة لإكمال هذا الجزء من التدريب.

</div>

Ghost Mode (demo booking): `FQDRUHJED` — each entry followed by a pause and a live `reveal`.

Note on the ER Ghost script: The ER script deliberately omits TK first, so the demo shows the verified NEED TICKETING ARRANGEMENT message and the recovery (Error-Recovery Practice model, Build Spec §7).

## 3. Feedback and hints (Build Spec §8 test applied)

| ID | Kind | EN | AR |
|---|---|---|---|
| `an.fb.format` | diagnostic · FORMAT · AN/a · all | This entry doesn't follow the availability pattern. Compare its parts, in order, with the pattern in the lesson. | <span dir="rtl">هذا الإدخال لا يتبع نمط عرض التوافر. قارن أجزاءه، بالترتيب، مع النمط في الدرس.</span> |
| `an.fb.dateRange` | diagnostic · DATA_REFERENCE · AN/b · all | The date is outside the period an availability display covers. | <span dir="rtl">التاريخ خارج الفترة التي يغطيها عرض التوافر.</span> |
| `an.fb.taskMismatch` | diagnostic · LOGICAL · AN/c · all | The entry is valid, but the date or the city pair is not the one in the task. | <span dir="rtl">الإدخال صحيح، لكن التاريخ أو المسار ليس هو المطلوب في المهمة.</span> |
| `ss.fb.noDisplay` | diagnostic · SEQUENCE · SS/b · all | There is no availability display to sell from yet. | <span dir="rtl">لا توجد شاشة توافر للبيع منها بعد.</span> |
| `ss.fb.format` | diagnostic · FORMAT · SS/a · all | This entry doesn't follow the short-sell pattern. Check each part and its order. | <span dir="rtl">هذا الإدخال لا يتبع نمط البيع المختصر. راجع كل جزء وترتيبه.</span> |
| `ss.fb.lineMissing` | diagnostic · DATA_REFERENCE · SS/b · all | The line number in your entry isn't in the last availability display. | <span dir="rtl">رقم السطر في إدخالك غير موجود في آخر شاشة توافر.</span> |
| `ss.fb.seats` | diagnostic · LOGICAL · SS/c · all | The number of seats doesn't match the number of passengers in the task. | <span dir="rtl">عدد المقاعد لا يساوي عدد الركاب في المهمة.</span> |
| `ss.fb.class` | diagnostic · LOGICAL · SS/d · all | The class in your entry isn't the class the task asks for — or the line isn't the task's flight. | <span dir="rtl">الدرجة في إدخالك ليست الدرجة المطلوبة في المهمة — أو السطر ليس رحلة المهمة.</span> |
| `nm.fb.format` | diagnostic · FORMAT · NM/a · all | This name entry doesn't follow the name pattern. Check the separator between surname and first name, and the title. | <span dir="rtl">إدخال الاسم لا يتبع نمط الاسم. راجع الفاصل بين اسم العائلة والاسم الأول، وراجع اللقب.</span> |
| `nm.fb.count` | diagnostic · LOGICAL · NM/b · all | The passenger count in the name entry doesn't match the task. | <span dir="rtl">عدد الركاب في إدخال الاسم لا يطابق المهمة.</span> |
| `nm.fb.name` | diagnostic · DATA_REFERENCE · NM/c · all | The name doesn't match the passenger in the task. Check the spelling. | <span dir="rtl">الاسم لا يطابق الراكب في المهمة. راجع التهجئة.</span> |
| `ap.fb.format` | diagnostic · FORMAT · AP/a · all | The contact element has no text after AP. | <span dir="rtl">عنصر الاتصال لا يحتوي نصًا بعد AP.</span> |
| `ap.fb.phone` | diagnostic · DATA_REFERENCE · AP/b · all | The contact element doesn't contain the phone number the task gives. | <span dir="rtl">عنصر الاتصال لا يحتوي رقم الهاتف الذي تعطيه المهمة.</span> |
| `ctc.fb.format` | diagnostic · FORMAT · CTC/a · all | ✎ This contact SSR doesn't follow the pattern. Compare it, part by part, with the pattern in the lesson. | <span dir="rtl">عنصر SSR للاتصال لا يتبع النمط. قارنه، جزءًا جزءًا، مع النمط في الدرس.</span> |
| `ctc.fb.number` | diagnostic · DATA_REFERENCE · CTC/b · practice | The number in the contact SSR isn't the passenger's mobile from the task. | <span dir="rtl">الرقم في عنصر SSR للاتصال ليس جوال الراكب المذكور في المهمة.</span> |
| `scn.fb.ctcmInvented` | diagnostic · LOGICAL · CTC/a · scenario | This passenger did not give a mobile number. A contact SSR with a number would not match what the passenger told you. | <span dir="rtl">هذا الراكب لم يعطِ رقم جوال. عنصر اتصال فيه رقم لن يطابق ما قاله لك الراكب.</span> |
| `scn.fb.warningShown` | ✎ corrective · MANDATORY_MISSING · CTC/a · scenario | The warning lists three ways to satisfy it. Which one matches this passenger's answer? | <span dir="rtl">التحذير يذكر ثلاث طرق لاستيفائه. أيّها يطابق إجابة هذا الراكب؟</span> |
| `scn.fb.bypassed` | diagnostic · MANDATORY_MISSING · ER/a · scenario | The booking was filed without recording the passenger's refusal. The bypass is recorded in the booking's history, and this step does not count as correct. | <span dir="rtl">حُفظ الحجز دون تسجيل رفض الراكب. التجاوز مسجَّل في سجل الحجز، ولا تُحتسب هذه الخطوة صحيحة.</span> |
| `tk.fb.format` | diagnostic · FORMAT · TK/a · all | This isn't one of the two ticketing arrangement entries. | <span dir="rtl">هذا ليس أحد أمرَي ترتيب إصدار التذكرة.</span> |
| `tk.fb.variant` | diagnostic · LOGICAL · TK/a · all | The ticketing arrangement is valid, but it isn't the one the task asks for. | <span dir="rtl">ترتيب إصدار التذكرة صحيح، لكنه ليس المطلوب في المهمة.</span> |
| `rf.fb.format` | diagnostic · FORMAT · RF/a · all | RF needs free text naming who requested the booking. | <span dir="rtl">الأمر RF يحتاج نصًا حرًا يذكر مَن طلب الحجز.</span> |
| `er.fb.missing` | diagnostic · MANDATORY_MISSING · ER/a · all | The booking isn't complete yet: at least one required element is missing. | <span dir="rtl">الحجز لم يكتمل بعد: عنصر مطلوب واحد على الأقل ناقص.</span> |
| `er.fb.bypassed` | diagnostic · MANDATORY_MISSING · ER/a · practice | The booking was filed without a passenger contact SSR. The bypass is recorded in the booking's history, and this step does not count as correct. | <span dir="rtl">حُفظ الحجز دون عنصر SSR لاتصال الراكب. التجاوز مسجَّل في سجل الحجز، ولا تُحتسب هذه الخطوة صحيحة.</span> |
| `fxp.fb.format` | diagnostic · FORMAT · FXP/a · all | This isn't the pricing entry used in this step. | <span dir="rtl">هذا ليس أمر التسعير المستخدم في هذه الخطوة.</span> |
| `fxp.fb.noPnr` | diagnostic · SEQUENCE · FXP/a · all | There is no complete booking to price yet. | <span dir="rtl">لا يوجد حجز مكتمل لتسعيره بعد.</span> |
| `fqd.fb.format` | diagnostic · FORMAT · FQD/a · all | This entry doesn't follow the fare display pattern. | <span dir="rtl">هذا الإدخال لا يتبع نمط عرض الأسعار.</span> |
| `fqd.fb.route` | diagnostic · LOGICAL · FQD/a · all | The city pair isn't the task's route. | <span dir="rtl">المسار ليس مسار المهمة.</span> |
| `er.partial.name` | diagnostic · MANDATORY_MISSING · ER/a · all | Missing: the passenger name. | <span dir="rtl">الناقص: اسم الراكب.</span> |
| `er.partial.itinerary` | diagnostic · MANDATORY_MISSING · ER/a · all | Missing: the flight segment. | <span dir="rtl">الناقص: مقطع الرحلة.</span> |
| `er.partial.phone` | diagnostic · MANDATORY_MISSING · ER/a · all | Missing: the contact (phone) element. | <span dir="rtl">الناقص: عنصر الاتصال (الهاتف).</span> |
| `er.partial.ticketing` | diagnostic · MANDATORY_MISSING · ER/a · all | Missing: the ticketing arrangement. | <span dir="rtl">الناقص: ترتيب إصدار التذكرة.</span> |
| `er.partial.received` | diagnostic · MANDATORY_MISSING · ER/a · all | Missing: the Received From element. | <span dir="rtl">الناقص: عنصر Received From.</span> |
| `er.partial.contactSsr` | diagnostic · MANDATORY_MISSING · ER/a · all | Missing: the passenger contact SSR for the airline. | <span dir="rtl">الناقص: عنصر SSR لاتصال الراكب لشركة الطيران.</span> |
| `reveal.AN` | corrective · — · AN/* · all | Type {EXPECTED_ENTRY} — AN, the date, then the two city codes. | <span dir="rtl">اكتب {EXPECTED_ENTRY} — الأمر AN، ثم التاريخ، ثم رمزا المدينتين.</span> |
| `reveal.SS` | corrective · — · SS/* · all | Type {EXPECTED_ENTRY} — seats, class, then the line number of the task's flight. | <span dir="rtl">اكتب {EXPECTED_ENTRY} — عدد المقاعد، ثم الدرجة، ثم رقم سطر رحلة المهمة.</span> |
| `reveal.NM` | corrective · — · NM/* · all | Type {EXPECTED_ENTRY} | <span dir="rtl">اكتب {EXPECTED_ENTRY}</span> |
| `reveal.AP` | corrective · — · AP/* · all | Type {EXPECTED_ENTRY} | <span dir="rtl">اكتب {EXPECTED_ENTRY}</span> |
| `reveal.CTC` | corrective · — · CTC/* · practice | Type {EXPECTED_ENTRY} — the dash after SRCTCM is mandatory. | <span dir="rtl">اكتب {EXPECTED_ENTRY} — الشرطة بعد SRCTCM إلزامية.</span> |
| `scn.reveal.ctc` | corrective · — · CTC/* · scenario | Record the refusal: type {EXPECTED_ENTRY} | <span dir="rtl">سجّل الرفض: اكتب {EXPECTED_ENTRY}</span> |
| `reveal.TK` | corrective · — · TK/* · all | Type {EXPECTED_ENTRY} | <span dir="rtl">اكتب {EXPECTED_ENTRY}</span> |
| `reveal.RF` | corrective · — · RF/* · all | Type {EXPECTED_ENTRY} | <span dir="rtl">اكتب {EXPECTED_ENTRY}</span> |
| `reveal.ER` | corrective · — · ER/* · all | Add the missing element first, then type ER. Missing now: {MISSING_LIST} | <span dir="rtl">أضف العنصر الناقص أولًا، ثم اكتب ER. الناقص الآن: {MISSING_LIST}</span> |
| `reveal.FXP` | corrective · — · FXP/* · all | Type {EXPECTED_ENTRY} | <span dir="rtl">اكتب {EXPECTED_ENTRY}</span> |
| `reveal.FQD` | corrective · — · FQD/* · all | Type {EXPECTED_ENTRY} | <span dir="rtl">اكتب {EXPECTED_ENTRY}</span> |

## 4. Nudges (diagnostic — error category only)

| ID | Kind | EN | AR |
|---|---|---|---|
| `nudge.FORMAT` | diagnostic | Look at the shape of your entry: a part is missing, extra, or out of order. | <span dir="rtl">انظر إلى شكل إدخالك: هناك جزء ناقص أو زائد أو في غير ترتيبه.</span> |
| `nudge.DATA_REFERENCE` | diagnostic | The entry's shape is fine; one value in it doesn't match what it refers to. | <span dir="rtl">شكل الإدخال سليم؛ لكن قيمة فيه لا تطابق ما تشير إليه.</span> |
| `nudge.AVAILABILITY` | diagnostic | What you asked for isn't available in the display. | <span dir="rtl">ما طلبته غير متاح في الشاشة.</span> |
| `nudge.GENERAL` | diagnostic | Something in this entry isn't accepted. Re-read the task step. | <span dir="rtl">شيء في هذا الإدخال غير مقبول. أعد قراءة خطوة المهمة.</span> |
| `nudge.SEQUENCE` | diagnostic | This entry needs something that has to come before it. | <span dir="rtl">هذا الإدخال يحتاج شيئًا يجب أن يأتي قبله.</span> |
| `nudge.MANDATORY_MISSING` | diagnostic | A required element of the booking is still missing. | <span dir="rtl">لا يزال عنصر مطلوب في الحجز ناقصًا.</span> |
| `nudge.DUPLICATE_CONFLICT` | diagnostic | This conflicts with something already in the booking. | <span dir="rtl">هذا يتعارض مع شيء موجود في الحجز.</span> |
| `nudge.LOGICAL` | diagnostic | The entry is valid, but it doesn't match the task. | <span dir="rtl">الإدخال صحيح، لكنه لا يطابق المهمة.</span> |

## 5. Training messages (DEIXEN's words — always labeled)

| ID | Kind | EN | AR |
|---|---|---|---|
| `tm.notRecognized` |  | Entry not recognized. | <span dir="rtl">الإدخال غير معروف.</span> |
| `tm.notCovered` |  | This entry is not covered in this slice of DEIXEN. It may be a real Amadeus entry; DEIXEN does not simulate it yet. | <span dir="rtl">هذا الإدخال غير مشمول في هذا الجزء من DEIXEN. قد يكون أمرًا حقيقيًا في Amadeus، لكن DEIXEN لا يحاكيه بعد.</span> |
| `tm.noPracticeData` |  | DEIXEN has practice flights only for the task's route in this slice. | <span dir="rtl">في هذا الجزء لا توجد رحلات تدريب إلا لمسار المهمة.</span> |
| `tm.classNotOffered` |  | In this practice display that class shows 0. The real Amadeus response to selling such a class is not verified, so DEIXEN does not simulate it. | <span dir="rtl">في شاشة التدريب هذه تظهر تلك الدرجة بالرقم 0. رد Amadeus الحقيقي على بيع درجة كهذه غير موثَّق، لذلك لا يحاكيه DEIXEN.</span> |
| `tm.fxpBeforeName` |  | In this slice, pricing is practiced on a booking that already has a name and a flight. | <span dir="rtl">في هذا الجزء يُتدرَّب على التسعير لحجز فيه اسم ورحلة بالفعل.</span> |
| `tm.rfMissing` |  | The booking was not filed: the Received From element is missing. (The exact Amadeus wording of this message is not verified.) | <span dir="rtl">لم يُحفظ الحجز: عنصر Received From ناقص. (الصياغة الدقيقة لهذه الرسالة في Amadeus غير موثَّقة.)</span> |
| `tm.otherMissing` |  | ✎ DEIXEN did not file the booking: an element this task requires is missing. (How Amadeus responds here is not verified.) | <span dir="rtl">لم يحفظ DEIXEN الحجز: عنصر تتطلبه هذه المهمة ناقص. (رد Amadeus في هذه الحالة غير موثَّق.)</span> |
| `tm.secondName` |  | This slice practices one adult passenger only. | <span dir="rtl">هذا الجزء يتدرب على راكب بالغ واحد فقط.</span> |
| `tm.rfLine` |  | Received From recorded: {RF_TEXT}. (How Amadeus displays RF before the end of the transaction is not verified.) | <span dir="rtl">سُجّل Received From: {RF_TEXT}. (طريقة عرض Amadeus لعنصر RF قبل إنهاء المعاملة غير موثَّقة.)</span> |
| `tm.ctcrLine` |  | Contact refusal recorded (SRCTCR): {CTCR_TEXT}. (How Amadeus displays it is not verified.) | <span dir="rtl">سُجّل رفض الاتصال (SRCTCR): {CTCR_TEXT}. (طريقة عرض Amadeus له غير موثَّقة.)</span> |
| `tm.sliceEnd` |  | The slice ends at the pricing display. What happens to the stored pricing record afterwards is not simulated. | <span dir="rtl">ينتهي هذا الجزء عند شاشة التسعير. لا يحاكي ما يحدث لسجل التسعير المحفوظ بعد ذلك.</span> |

## 6. Coach explanations (beside real Amadeus output)

| ID | Kind | EN | AR |
|---|---|---|---|
| `coach.needTk` |  | This is a real Amadeus message. It means a required element is missing: the ticketing arrangement. | <span dir="rtl">هذه رسالة حقيقية من Amadeus. معناها أن عنصرًا مطلوبًا ناقص: ترتيب إصدار التذكرة.</span> |
| `coach.missingCtc` |  | This is a real Amadeus warning. The booking has no contact SSR for the airline: a mobile number, an e-mail, or a recorded refusal. | <span dir="rtl">هذا تحذير حقيقي من Amadeus. الحجز لا يحتوي عنصر SSR للاتصال لشركة الطيران: رقم جوال، أو بريد إلكتروني، أو رفض مسجَّل.</span> |
| `coach.bypassRecorded` |  | Entering ER again bypasses the warning, and the bypass is recorded in the booking's history. | <span dir="rtl">إدخال ER مرة ثانية يتجاوز التحذير، ويُسجَّل التجاوز في سجل الحجز.</span> |
| `coach.erDone` |  | The transaction is ended. The last part of the header line is the record locator. | <span dir="rtl">انتهت المعاملة. الجزء الأخير من سطر العنوان هو رمز الحجز.</span> |
| `coach.fxpDone` |  | The booking is priced and the result is stored as a TST. | <span dir="rtl">تم تسعير الحجز وحُفظت النتيجة في TST.</span> |
| `coach.escalate` |  | This kind of error has come up {N} times on this step. Do you want to open the lesson again? | <span dir="rtl">تكرر هذا النوع من الأخطاء {N} مرات في هذه الخطوة. هل تريد فتح الدرس مرة أخرى؟</span> |

## 7. Contract texts (assessment, growth, reset)

| ID | Kind | EN | AR |
|---|---|---|---|
| `ui.trainingLabel` |  | Training message | <span dir="rtl">رسالة تدريبية</span> |
| `ui.unverifiedMarker` |  | Layout detail not fully verified | <span dir="rtl">تفصيل في الشكل غير موثَّق بالكامل</span> |
| `ui.correctInDeixen` |  | Correct in DEIXEN | <span dir="rtl">صحيح في DEIXEN</span> |
| `ui.hintLabel` |  | Hints used in this session: {N} | <span dir="rtl">التلميحات المستخدمة في هذه الجلسة: {N}</span> |
| `ui.assessment.intro` |  | You are starting the assessment: the full booking and pricing path, on your own. Entries and hints from this session stay visible and are counted; earlier sessions are not included. | <span dir="rtl">أنت تبدأ التقييم: مسار الحجز والتسعير كاملًا، بمفردك. تبقى إدخالات وتلميحات هذه الجلسة ظاهرة وتُحتسب؛ ولا تُضم الجلسات السابقة.</span> |
| `ui.assessment.carryover` |  | Before the assessment started, this session already had {N} entries and {H} hints. They stay visible and are included in this result. | <span dir="rtl">قبل بدء التقييم كان في هذه الجلسة {N} إدخالات و{H} تلميحات. تبقى ظاهرة وهي محسوبة ضمن هذه النتيجة.</span> |
| `ui.assessment.result` |  | The full path works end to end for you on this occasion. This is not a general competence rating. | <span dir="rtl">المسار الكامل يعمل معك من البداية للنهاية في هذه المرة. هذا ليس تقييمًا عامًا للكفاءة.</span> |
| `ui.abandoned` |  | Your last {WHAT} was interrupted when the browser closed. It is recorded as abandoned — neither passed nor failed. | <span dir="rtl">انقطع آخر {WHAT} عند إغلاق المتصفح. سُجّل كـ«متروك» — لا ناجح ولا راسب.</span> |
| `ui.growth.completed` |  | Completed | <span dir="rtl">مكتمل</span> |
| `ui.growth.inProgress` |  | In progress | <span dir="rtl">قيد التقدم</span> |
| `ui.growth.needsPractice` |  | Needs more practice | <span dir="rtl">يحتاج مزيدًا من التدريب</span> |
| `ui.growth.empty` |  | No practice recorded yet. Your status appears after your first practice entries. | <span dir="rtl">لا يوجد تدريب مسجَّل بعد. ستظهر حالتك بعد أول إدخالات تدريب.</span> |
| `ui.growth.basis` |  | This status comes only from your recorded practice in DEIXEN. It is not a job-readiness score. | <span dir="rtl">هذه الحالة مبنية فقط على تدريبك المسجَّل في DEIXEN. وليست درجة جاهزية للعمل.</span> |
| `ui.reset.confirm` |  | Reset everything? All your recorded practice in this browser will be deleted. This cannot be undone. | <span dir="rtl">إعادة ضبط كل شيء؟ سيُحذف كل تدريبك المسجَّل في هذا المتصفح. لا يمكن التراجع عن ذلك.</span> |
| `ui.what.assessment` |  | assessment | <span dir="rtl">تقييم</span> |
| `ui.what.scenario` |  | scenario | <span dir="rtl">سيناريو</span> |

## 8. Simulator Scope Disclosure (G3)

- **EN:** What this simulator does and does not do
- <span dir="rtl">**AR:** ما الذي يفعله هذا المحاكي وما لا يفعله</span>
- ✎ **EN:** DEIXEN is a practice simulator, not Amadeus. All flights, seats, fares, taxes, names, phone numbers, office codes and record locators are invented for practice. The airline code 6X is used only as a practice code; no real schedule or fare is shown.
- ✎ <span dir="rtl">**AR:** DEIXEN محاكي للتدريب، وليس Amadeus. كل الرحلات والمقاعد والأسعار والضرائب والأسماء وأرقام الهواتف ورموز المكاتب ورموز الحجز مختلَقة للتدريب. ويُستخدم رمز الطيران 6X رمزًا للتدريب فقط؛ ولا يُعرض أي جدول أو سعر حقيقي.</span>
- **EN:** Only these entries are simulated: AN, SS, NM, AP, SRCTCM, SRCTCR, TK, RF, ER, FXP, and FQD (optional). Any other entry gets the message 'not covered in this slice' — a DEIXEN limit, not an Amadeus one.
- <span dir="rtl">**AR:** الأوامر المُحاكاة فقط هي: AN و SS و NM و AP و SRCTCM و SRCTCR و TK و RF و ER و FXP و FQD (اختياري). أي إدخال آخر تظهر له رسالة «غير مشمول في هذا الجزء» — وهذا حد في DEIXEN، لا في Amadeus.</span>
- **EN:** This slice practices one adult passenger, one flight, and one applicable fare. Real Amadeus also handles children and infants, several passengers and flights, groups, and fare lists where you choose a fare with FXT.
- <span dir="rtl">**AR:** هذا الجزء يتدرب على راكب بالغ واحد، ورحلة واحدة، وسعر واحد منطبق. أما Amadeus الحقيقي فيتعامل أيضًا مع الأطفال والرضّع، وعدة ركاب ورحلات، والمجموعات، وقوائم الأسعار التي تختار منها بالأمر FXT.</span>
- **EN:** DEIXEN's practice office requires a ticketing arrangement (TK) before the transaction can end. In real Amadeus this depends on the office's settings.
- <span dir="rtl">**AR:** مكتب التدريب في DEIXEN يشترط وجود ترتيب إصدار التذكرة (TK) قبل إنهاء المعاملة. وفي Amadeus الحقيقي يعتمد ذلك على إعدادات المكتب.</span>
- **EN:** Lines marked 'Training message' are DEIXEN's own words. The real Amadeus wording of many error messages is not publicly documented, so DEIXEN does not imitate it.
- <span dir="rtl">**AR:** الأسطر المعلَّمة بـ«رسالة تدريبية» هي كلمات DEIXEN نفسه. فالصياغة الحقيقية لكثير من رسائل الخطأ في Amadeus غير منشورة، لذلك لا يقلدها DEIXEN.</span>
- ✎ **EN:** Screens follow the layout of official Amadeus examples. Column spacing may differ. Some details appear in official examples only in part: the codes in the availability display (the number before the weekday, the figure after each class letter, the E0 code), the header time when you enter a time, the airline code in a stored mobile-contact line, and the booking display after AP, SRCTCM, SRCTCR, TK and RF entries. DEIXEN marks these 'Layout detail not fully verified' and does not teach them. Where no official example exists at all (a stored SRCTCR line; RF before the transaction ends), DEIXEN shows a training message instead. DEIXEN does not show the RLR tag or airline messages under a sold flight.
- ✎ <span dir="rtl">**AR:** تتبع الشاشات شكل أمثلة Amadeus الرسمية. قد تختلف المسافات بين الأعمدة. بعض التفاصيل لا تظهر في الأمثلة الرسمية إلا جزئيًا: رموز شاشة التوافر (الرقم قبل اليوم في سطر العنوان، والرقم بعد كل حرف درجة، والرمز E0)، ووقت سطر العنوان عندما تُدخل وقتًا، ورمز شركة الطيران في سطر جوال الراكب المحفوظ، وعرض الحجز بعد الأوامر AP و SRCTCM و SRCTCR و TK و RF. يعلّم DEIXEN هذه التفاصيل بعبارة «تفصيل في الشكل غير موثَّق بالكامل» ولا يشرحها. وحيث لا يوجد مثال رسمي أصلًا (سطر SRCTCR المحفوظ، وعنصر RF قبل إنهاء المعاملة) يعرض DEIXEN رسالة تدريبية بدلًا منه. ولا يعرض DEIXEN علامة RLR ولا رسائل شركة الطيران تحت الرحلة المبيعة.</span>
- ✎ **EN:** Practice flights exist only for the task routes. The meaning of some codes on the screens (for example the figures after class letters) is not taught, because DEIXEN could not verify it from official sources. Official examples of SRCTCM and SRCTCR end with an extra part (for example /US or /P3); what that part must contain is not covered in this slice, and DEIXEN accepts the entry with or without it.
- ✎ <span dir="rtl">**AR:** رحلات التدريب موجودة فقط لمسارات المهام. ولا يُشرح معنى بعض الرموز على الشاشات (مثل الأرقام بعد أحرف الدرجات) لأن DEIXEN لم يستطع توثيقها من مصادر رسمية. وتنتهي أمثلة SRCTCM و SRCTCR الرسمية بجزء إضافي (مثل /US أو /P3)؛ وما يجب أن يحتويه هذا الجزء غير مشمول في هذا الجزء من التدريب، ويقبل DEIXEN الإدخال به أو بدونه.</span>
- **EN:** The slice ends at the pricing display. It does not simulate what happens to the stored pricing record afterwards, or ticket issuance.
- <span dir="rtl">**AR:** ينتهي هذا الجزء عند شاشة التسعير. لا يحاكي ما يحدث لسجل التسعير المحفوظ بعد ذلك، ولا إصدار التذكرة.</span>
- **EN:** 'Correct in DEIXEN' means your entry met this simulator's checklist. It is not a certificate of workplace readiness.
- <span dir="rtl">**AR:** «صحيح في DEIXEN» تعني أن إدخالك استوفى قائمة التحقق في هذا المحاكي. وليست شهادة جاهزية للعمل.</span>

## 9. Borderline items flagged by the self-review

- ✎ `scn.fb.warningShown` — re-tagged **corrective** at the readiness check (2026-09-25): together with the real warning, which names the three options, it leaves only one answer, so a success right after it should not count as independent. This protects the meaning of TRANSFERRED on the scenario's load-bearing CTC skill.
- ✎ `ctc.fb.format` — reworded: "one required character is missing" pointed straight at the dash. Now diagnostic without narrowing.
- ✎ Scenario expected behaviour — "without triggering or bypassing the warning" became "without bypassing": meeting the real warning and then adding SRCTCR is a correct recovery (the constraint and acceptance text already said this).
- `er.partial.*` — tagged diagnostic as the Build Spec §8 defines Partial Reveal; they name the missing element, not the entry.
- `ss.fb.class` — names the checklist item, not the value. Diagnostic.
- Error-category assignment per feedback item is the author's judgment (file 05 lists the 8 categories without definitions).