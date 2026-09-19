# AMADEUS_CURRICULUM.md — المنهج التعليمي الشامل

> جزء من قاعدة معرفة AeroBridge — الفهرس الكامل في `PROJECT.md §0.5`
> **كل درس هنا اتراجع فرديًا مقابل `COMMAND_REFERENCE.md`** قبل ما يتصنّف "قابل للتطبيق" أو "خطة مستقبلية" — تطبيقًا لمبدأ Honest Scope في `PROJECT.md §3`.

تم اعتماد منهج دورات **مصر للطيران (EgyptAir Training Center)**، بالإضافة لمسار متكامل لمهارات خدمة العملاء.

---

## المسار الأول: Amadeus Technical Training

### أ. الدورة الأساسية — Basic Amadeus Course (قابلة للتطبيق بالكامل تقريبًا)

| # | الدرس | الأمر المستخدم | الحالة |
|:---:|:---|:---|:---:|
| 1 | Information about Amadeus System | — (نظري) | ✅ |
| 2 | Booking Class | بيانات RBD | ✅ |
| 3 | Class of Transportation | — (نظري) | ✅ |
| 4 | Amadeus Availability | `AN` | ✅ |
| 5 | Create a Basic PNR | `NM`, `SS`, `AP`, `TK`, `RF`, `ER` | ✅ |
| 6 | AIS (Amadeus Information System) | — (نظري) | ✅ |
| 7 | Flight Booked Outside Amadeus Egypt | — (نظري) | ✅ |
| 8 | Amadeus Fare Quote Display | `FQD` **(تصحيح: مش "FQ")** | ✅ |
| 9 | Informative Pricing (One-Way) | `FQD` | ✅ |
| 10 | Informative Pricing (Round-Trip) | `FQD` مرتين (ذهاب ثم عودة — مفيش أمر واحد للرحلتين معًا) | ✅ (بملاحظة) |
| 11 | Discounts | — | ➡️ خطة مستقبلية |
| 12 | Multiply Fare | — | ➡️ خطة مستقبلية |
| 13 | Itinerary Pricing | `FXP` / `FXB` **(تصحيح: مش "FXP/FXX")** | ✅ |
| 14 | Sending Messages | — | ➡️ خطة مستقبلية |
| 15 | PNR Processing | `ER`, `ET`, `RT`, `IG`, `XE` | ✅ |
| 16 | Amadeus Exchange (Reissue) Steps | — | ➡️ خطة مستقبلية |
| 17 | Evaluation Means | *[يحتاج تحديد أداة تقييم مناسبة — فجوة قديمة من v7]* | ⚠️ ناقص التعريف |

### ب. الدورة المتقدمة — Advanced Amadeus Course

**الفئة المستهدفة:** موظفو المبيعات والحجز. **المتطلبات:** إتمام الأساسية.

| # | الدرس | الحالة | ملاحظة |
|:---:|:---|:---:|:---|
| 1 | Air Advanced Functions | ➡️ خطة مستقبلية | غير معرّف بدقة كفاية للتطبيق |
| 2 | Non-Homogenous PNR | ✅ **جزئيًا** | مجموعات بالغين (لحد 9 عبر `NM1` متكرر) شغالة فعلاً. مسافرين مختلطين (أطفال/رضع CHD/INF) ➡️ خطة مستقبلية |
| 3 | Amadeus Offers | ➡️ خطة مستقبلية | — |
| 4 | Revalidation | ➡️ خطة مستقبلية | — |
| 5 | Manual Reissue | ➡️ خطة مستقبلية | — |
| 6 | Amadeus Ticket Changer (ATC) | ➡️ خطة مستقبلية | — |
| 7 | Issuing EMDs | ➡️ خطة مستقبلية | — |
| 8 | Book & Price Ancillary Services | ✅ **قابل للتطبيق كاملًا** | `HA`, `HS`, `CA`, `CS`, `SR` كلهم شغالين |
| 9 | Display & Print Sales Report (TJ) | ➡️ خطة مستقبلية | — |
| 10 | Refund | ➡️ خطة مستقبلية | — |
| 11 | ATC Refund | ➡️ خطة مستقبلية | — |

**خلاصة:** 2 من 11 درس قابلين للتطبيق كاملًا الآن، 1 جزئيًا، الباقي (8) خطة مستقبلية بالكامل.

---

## المسار الثاني: Airline Customer Service & Communication Mastery

مستقل عن حالة تنفيذ المحرك — محتوى حواري/سيناريوهات، مش أوامر Amadeus:

| # | الدرس | الوصف |
|:---:|:---|:---|
| 1 | Passenger Profiling & Types | VIP, Angry Passengers, First-Time Flyers, Corporate Clients, Families |
| 2 | Professional English Scripts | جمل جاهزة لكل موقف (تأخير، تغيير موعد، زيادة أمتعة، غرامات) |
| 3 | De-escalation & Conflict Resolution | تهدئة العميل الغاضب |
| 4 | Cross-selling & Upselling | عرض Ancillaries وترقية الدرجات باحترافية |
| 5 | Scenario-Based Simulations | أمر Terminal فعلي (من الأوامر ✅ القابلة للتطبيق بس) + رد إنجليزي مناسب معًا |

**آلية Anger Meter — [جديد v9، تحسين لبند 5]:** كل سيناريو حواري بيربط اختيارات الرد بمؤشر مرئي (هادئ ↔ غاضب) بيتحرك حسب جودة الاختيار — تعزيز مباشر لدرس De-escalation (بند 3)، ومسجّل كـ Event في Event Log.

---

## L9 — Timatic, IROPS & Saudi Market Specialization (تفصيل)

**نقطة مهمة:** الوحدة دي **مش محتاجة أي أمر جديد في المحرك** — بتُبنى بالكامل من أوامر ✅ موجودة فعلاً:

| السيناريو | الأوامر المستخدمة |
|:---|:---|
| إلغاء/تأخير رحلة وإعادة حجز (IROPS) | `RT` (استرجاع) → `XE` (إلغاء السطر القديم) → `SS`/`AN` (بيع رحلة بديلة) → `ER` (إغلاق) |
| Timatic لراكب | `TI` (⚠️ حاليًا Egypt-only، راجع `COMMAND_REFERENCE.md §5`) |
| حجوزات مجموعات/عمرة | `NM1` متكرر لحد 9 بالغين (نفس آلية Non-Homogenous PNR الجزئية أعلاه) |

**محتوى معلوماتي مصاحب (بدون أوامر):** خصوصيات تشغيلية لشركات الطيران السعودية — Saudia (`SV`), flynas (`XY`), flyadeal (`F3`) — وسيناريوهات قياس الأداء تحت ضغط وقت (مرتبطة بـ Time-Pressure Tag في `UI_GUIDELINES.md §8`).

---

## تنسيق تأليف Ghost Mode (Content Authoring Format) — [جديد v9]

كل درس Ghost Mode (`UI_GUIDELINES.md §4`) بيتخزن كـ JSON بالشكل ده:

```json
{
  "lessonId": "L2-availability-an",
  "steps": [
    { "type": "type", "text": "AN15JULCAIDXB", "charDelayMs": 60 },
    { "type": "pause", "durationMs": 400 },
    { "type": "reveal", "source": "COMMAND_REFERENCE.md#AN" }
  ]
}
```

- `type` بيتكتب حرف حرف بتأخير `charDelayMs` — نصي بالكامل، بدون صوت
- `reveal` بيسحب الرد الفعلي من نفس منطق المحرك (مش رد مكتوب يدويًا منفصل) عشان يفضل متطابق مع `COMMAND_REFERENCE.md` تلقائيًا

---

## Speed Drills (تعريف) — [جديد v9]

وضع تدريب فرعي جوه تاب **Practice** بالشاشة 3: تكرار نفس الأمر (من الأوامر ✅ فقط) عدة مرات بمؤقت، وحساب سرعة الكتابة (Characters Per Minute) من طوابع Event Log الموجودة أصلاً — **مفيش منطق محرك جديد مطلوب**، بس عرض/تجميع بيانات في `performance.js`.

---

## خطة التوسع المستقبلية (Future Expansion Backlog)

> **نظري بالكامل — لا يوجد تطبيق عملي في المحاكي حاليًا.** يُفعَّل فقط بعد توسعة حقيقية في محرك الكود (`Phase 10` في `PROJECT.md §4`). لا يُعرض للمتدرب كمحتوى "Practice" قابل للتنفيذ.

| الدرس | من أي مسار |
|:---|:---|
| Discounts | أساسية #11 |
| Multiply Fare | أساسية #12 |
| Sending Messages | أساسية #14 |
| Amadeus Exchange (Reissue) Steps | أساسية #16 |
| Air Advanced Functions | متقدمة #1 |
| Non-Homogenous PNR (مسافرين مختلطين CHD/INF) | متقدمة #2 (جزء) |
| Amadeus Offers | متقدمة #3 |
| Revalidation | متقدمة #4 |
| Manual Reissue | متقدمة #5 |
| Amadeus Ticket Changer (ATC) | متقدمة #6 |
| Issuing EMDs | متقدمة #7 |
| Display & Print Sales Report (TJ) | متقدمة #9 |
| Refund | متقدمة #10 |
| ATC Refund | متقدمة #11 |

---

> *AMADEUS_CURRICULUM.md — أي درس هنا مصنّف "✅" يقدر يتحول لمحتوى Lesson فعلي في UI_GUIDELINES.md §4 من غير أي انتظار. أي درس "➡️" يستنى Phase 10.*
