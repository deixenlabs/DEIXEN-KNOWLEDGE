DEVELOPMENT_RULES.md — قواعد الجودة والتطوير
جزء من قاعدة معرفة AeroBridge — الفهرس الكامل في PROJECT.md §0.5 هذا الملف عن سياسات المشروع (اختبار، إصدارات، مراجعة). شخصية Claude وأسلوب عمله موجودة بشكل منفصل في Custom Instructions الخاصة بالـ Project — الاتنين مكملين بعض مش مكررين.
1. §1.1 — البناء والتثبيت صفحة بصفحة
أي مرحلة بتحتوي أكتر من شاشة/صفحة مستقلة، تُبنى وتُعرض كل واحدة على حدة وتتثبت بموافقة صريحة قبل الانتقال للي بعدها — بلا استثناء. المكونات المشتركة بين الشاشات (زي الهيدر والـ Bottom Nav) تُبنى وتُثبّت أولًا كوحدة مستقلة قبل أي شاشة فردية، وكل شاشة بعد كده بتستخدمها من غير إعادة بناء.
2. اختبار كل مرحلة
يجب تجربة واختبار كل مرحلة بعد الانتهاء منها مباشرة والتأكد من خلوها من الأخطاء وأن النتيجة مرضية بالكامل قبل الانتقال للمرحلة التالية.
3. الدقة المتناهية لأوامر أماديوس
يجب التحقق بنسبة 100% من صحة كل أمر أو كود أو استجابة تخص نظام أماديوس. المصدر الوحيد المقبول هو الكود الفعلي في COMMAND_REFERENCE.md — مش الذاكرة العامة عن أماديوس، ومش أي مستند تخطيط سابق (Spec) لو تعارض مع الكود الشغّال فعليًا.
4. سياسة الإصدارات (Version Control & Rollback)
البند
السياسة
نظام الإصدارات
كل مرحلة مكتملة ومُعتمدة تُصمم بوسم (Tag) في Git
فروع العمل
main للاستقرار — feature/... للتطوير
آلية التراجع
خلل جوهري ← العودة للوسم السابق المستقر فورًا
سجل التغييرات
كل تحديث يُوثق في CHANGELOG.md (ملف Git، مش جزء من قاعدة معرفة Claude)
5. سياسة المراجعة الذاتية (Self-Review Policy)
قبل تسليم أي ميزة مهمة أو تغيير بنية أو تنفيذ كود: مراجعة داخلية موجزة للتحقق من صحة العمل، اتساقه مع الملفات المرجعية، وخلوه من أي تراجع في الجودة. لا تُنشر نتائج المراجعة إلا لو طُلب صراحةً.
6. §1.4 — AI Development & Verification Loop (قاعدة رسمية تنطبق على كل كود غير تافه)
AI Development Loop — Mandatory Execution Cycle
For every non-trivial implementation task, you MUST follow a closed verification loop instead of treating code generation as the final step.
Required Loop
1. AUDIT
Inspect the relevant existing files, architecture, dependencies, and source-of-truth references before changing anything.
2. PLAN
Determine the smallest correct implementation that satisfies the requirement without duplicating existing logic or introducing unnecessary abstractions.
3. IMPLEMENT
Make the required changes only within the approved scope.
4. TEST
Run the appropriate tests against the real implementation. Prefer direct engine/Node tests before browser integration when applicable.
5. OBSERVE
Do not assume the implementation is correct because the code looks correct. Examine the actual test output and behavior.
6. DIAGNOSE
If a test fails or behavior is inconsistent, identify the actual root cause before modifying the code again.
7. CORRECT
Fix the root cause in the correct layer. Do not hide defects with workarounds in unrelated layers.
8. RE-TEST
After every substantive correction, run the relevant test again. Do not consider the task complete based on the first successful-looking implementation.
9. REGRESSION CHECK
Verify that previously working behavior affected by the change still works.
10. SELF-REVIEW
Before delivery, perform a concise internal review for:
- architectural consistency,
- source-of-truth compliance,
- realistic Amadeus behavior,
- unintended side effects,
- scope violations,
- regressions,
- fabricated or duplicated logic.
Critical Rules
- A generated code file is NOT considered successful until its behavior has been verified.
- Never treat "the code looks correct" as evidence of correctness.
- Never fabricate test results.
- Never skip testing merely because the implementation appears simple if the change affects engine behavior, architecture, or shared systems.
- Never fix a symptom in a higher layer when the actual defect belongs in the underlying engine.
- Do not expand the scope simply because a related issue was discovered. Document unrelated Tech Debt and defer it according to project rules.
- If the real implementation cannot be verified, explicitly state that verification is incomplete.
Completion Criterion
A task is complete only when:
AUDIT → PLAN → IMPLEMENT → TEST → OBSERVE → DIAGNOSE → CORRECT (if needed) → RE-TEST → REGRESSION CHECK → SELF-REVIEW
has been completed to the extent appropriate for the risk of the task.
For trivial changes, use a proportionally lighter version of the loop. For architectural, engine, integration, or high-risk changes, execute the full loop.
7. اختبارات التكامل (Integration Testing)
البند
الوصف
Event Log ↔ المحركات
كل تفاعل يُسجل وينعكس في Roadmap و Coach و Profile
بين الشاشات
التنقل يحافظ على حالة البيانات (State)
Storage
حفظ واسترجاع صحيح عبر جلسات متعددة
RTL/LTR
التبديل بين العربية والإنجليزية بدون كسر تخطيط — شامل انعكاس الهيدر
8. Tech Debt معروف (اكتُشف أثناء مراجعة الكود — قبل Phase 4)
هذه بنود عمل موثّقة، مش أخطاء عاجلة — لازم تتحل قبل ما event-bridge.js يوصّل errors.js بالكامل لـ Work Mode في Phase 4:
#
المشكلة
التفصيل
المصدر
1
Entry ميت في كتالوج الأخطاء
DUPLICATE SEGMENT EXISTS موجودة في errors.json بس مفيش أي تحقق تكرار في pnr.js يرجّعها فعليًا
COMMAND_REFERENCE.md §11
2
Entry ميت تاني
MAX 9 PASSENGERS PER SEGMENT — الرسالة الحقيقية اللي الكود بيرجعها هي MAXIMUM 9 PASSENGERS PER PNR (موجودة كـ Entry منفصل وصحيح)
نفس المصدر
3
فجوة وظيفية حقيقية (أولوية أعلى)
matchKeys بتاعة Entry ITEM NOT FOUND / NO PNR ماعندهاش RECORD LOCATOR NOT FOUND — وهي الرسالة الحقيقية اللي retrievePnr() بترجعها لما RT يفشل. النتيجة: Coach حاليًا مش هيلتقط خطأ RT الحقيقي
نفس المصدر
4
قيد تصميمي معروف
XE (حذف عنصر) بيغطي بس الركاب/الـSegments/AP/TK/RF/الفنادق/السيارات — SSR والموبايل والإيميل والملاحظات والتذاكر والمقعد مش قابلة للحذف الفردي حاليًا
COMMAND_REFERENCE.md §3
5
قيد تصميمي معروف
مقعد واحد بس لكل PNR (مش لكل راكب) — موثّق ومؤجل عمدًا في كود pnr.js نفسه
COMMAND_REFERENCE.md §6
6
بيانات غير مكتملة
FQN/FQR (قواعد التسعير) جاهزة بالكود بس غير فعّالة عمليًا — fares.json مفيهوش حقل rules لأي تعريفة لحد دلوقتي
COMMAND_REFERENCE.md §4
7
ترقيم عناصر ثابت (Hardcoded) في الصدى اللحظي
pnr.js بيرجّع رقم عنصر مكتوب حرفيًا في addContact ("2. AP..."), addTicketingArrangement ("3. TK OK"), وaddReceivedFrom ("4. RF...") — مش محسوب ديناميكيًا زي formatPnrLines() اللي بيحسب ترقيم الـPNR النهائي فعليًا وقت ER/ET. النتيجة: الصدى اللحظي وقت كتابة الأمر ممكن يعرض رقم عنصر غلط لو سبقه أكتر من راكب واحد أو أكتر من Segment، ويتناقض مع الرقم الصح في الـPNR النهائي. أثر تعليمي مباشر: المتدرب ممكن يتعلم رقم عنصر غلط ويستخدمه غلط بعدين مع XE. event-bridge.js تعمّد عدم التعويض عن ده أو إعادة تنسيقه (Pass-Through صريح، مفيهوش أي منطق تصحيح جوه الـbridge) — الإصلاح الصحيح مكانه pnr.js نفسه، مش الـbridge.
pnr.js (addContact/addTicketingArrangement/addReceivedFrom) — اكتُشفت أثناء اختبار event-bridge.js الفعلي في Node، مش من مراجعة الكود الأصلية اللي أنتجت باقي الجدول ده
قرار: البند 3 له أولوية قبل تفعيل Coach الكامل (Phase 4-5) لأنه فجوة وظيفية مش مجرد توثيق ناقص. الباقي (1، 2، 4، 5، 6) قيود موثّقة يمكن تأجيلها لمراحل توسعة لاحقة (Phase 10). البند 7 مختلف في طبيعته عن الباقي — مش جزء من Phase 10 Backlog (مش منهج مستقبلي)، لكن قرار صريح بعدم لمس pnr.js أثناء مرحلة event-bridge.js الحالية. موثّق/مؤجل بس، لسه مش متصلّح، وقرار توقيت الإصلاح يحتاج نقاش مسبق منفصل مش مربوط بجدول Phase 10.
بند مقترح: التحقق من سلامة الرفع عبر الموبايل (Mobile Upload Integrity Check)
أي ملف بيتراجع محتواه (نسخ من جهاز → لصق في GitHub، سواء عبر Upload أو Create new file) لازم يتعمله تحقق عددي، مش بصري بس:
قبل النسخ، اعرف عدد أسطر الملف الأصلي (لو الملف جاي من Claude، هطلب منك تحديد العدد وقت التسليم)
بعد اللصق في GitHub، قبل الـ Commit، دوس على أي مكان في محرر الكود واعمل Select All — GitHub بيوضح عدد الأسطر/الحروف المحددة في بعض الحالات، أو ببساطة انزل لآخر سطر واتأكد إنه فعلاً آخر سطر بالملف الأصلي (زي </html>)
لو الملف كبير (أكتر من ~300 سطر)، الأفضل معماريًا نستخدم Upload files (مش Create new file) لما يكون ممكن، لأن الرفع المباشر للملف بينسخ البايتات زي ما هي من غير المرور بمحرر لصق بيعتمد على الـ Clipboard — ده بيقلل احتمالية القطع الناتج عن حدود الـ Clipboard في بعض تطبيقات الموبايل
DEVELOPMENT_RULES.md — أي بند هنا قابل للتطبيق فورًا على أي كود جديد، بلا استثناء.
9. سياسة توفير التوكنز والتكلفة (Token & Cost Efficiency Policy)
> هدف هذا القسم: تقليل استهلاك التوكنز بلا التضحية بالدقة على المهام المعمارية/الحرجة. القاعدة العامة: **الجهد يتناسب مع المخاطرة**، مش كل مهمة محتاجة نفس العمق.
### أ. اختيار الموديل حسب نوع المهمة

| نوع المهمة | الموديل المقترح | السبب |
| :--- | :--- | :--- |
| سؤال سريع، توضيح، شرح مفهوم، مراجعة نص قصير | **Haiku** (الأسرع والأرخص) | لا يحتاج تفكير معمق أو سياق كبير |
| كتابة/تعديل كود على نطاق شاشة واحدة، مهام محددة بوضوح | **Sonnet** (افتراضي المشروع) | التوازن الأنسب لمعظم شغل AeroBridge |
| قرار معماري كبير (زي دمج event-bridge.js، إعادة هيكلة عبر عدة ملفات، تشخيص باج غامض عبر المشروع كله) | **Sonnet مع تفكير ممتد (Extended Thinking) مفعّل** | يحتاج تحليل متعدد الخطوات قبل الكتابة |
| مهمة حرجة جدًا (نادرة) — قرار يصعب التراجع عنه | **Opus لو متاح** | فقط لو Sonnet فشل فعليًا في مهمة معقدة بعد محاولة واضحة |

**قاعدة عملية:** اختَر مستوى الـmodel/reasoning وفقًا لمخاطر المهمة. استخدم Sonnet العادي للمهام الروتينية، وفعّل Extended Thinking للمهام المعمارية أو عالية المخاطر، واستخدم Opus عند الحاجة لمهمة حرجة جدًا أو عندما يثبت أن مستوى أقل غير كافٍ.
### ب. متى تبدأ شات جديد (الأهم لتوفير التوكنز)
- **كل شاشة/ميزة جديدة = شات جديد.** لا تكمل في نفس الشات الطويل — كل رسالة في محادثة طويلة بتعيد معالجة كل السياق اللي قبلها.
- **مؤشر إنه وقت شات جديد:** لما تحس إن المحادثة بقت "بطيئة" أو الردود بقت أطول من اللازم، أو عدد الرسائل عدّى ~15-20 رسالة على نفس المهمة.
- **دايمًا ابدأ الشات الجديد ببرومبت مجمّع** (زي اللي بنعمله لـ event-bridge.js) بدل ما تدّي التفاصيل قطعة قطعة عبر رسائل متعددة.
### ج. قواعد كتابة الكود الموفّرة
1. **تعديل مستهدف (`str_replace`) لا إعادة كتابة كاملة** — لو التعديل المطلوب أقل من 30% من الملف، لازم يكون تعديل جزئي مش إعادة إنشاء الملف بالكامل.
2. **لا تطلب مراجعة "المشروع كله" إلا لو المشكلة فعلاً عابرة للملفات.** لو المشكلة في شاشة واحدة بس، حدد ده صراحة في الطلب ("راجع practice.html بس، مش المشروع كله").
3. **ارفع الملفات المطلوبة فقط لكل مهمة**، مش كل ملفات المشروع كل مرة. لو المهمة عن الـTerminal، ملفات الـTerminal + المحرك بس، مش كل الشاشات.
### د. قواعد الاختبار الموفّرة
1. **اختبار Playwright الكامل (screenshots + تفاعل حقيقي) للتغييرات الحرجة/المعمارية بس** (زي event-bridge.js، دمج نظام مشترك). للتعديلات الصغيرة (تغيير نص، لون واحد، حجم عنصر) يكفي مراجعة كود + وصف التغيير، من غير تشغيل متصفح كامل.
2. **لا تكرر اختبار حاجة اتأكدت شغالة قبل كده** إلا لو التعديل الجديد بيلمسها فعليًا.
### هـ. قواعد التواصل الموفّرة
1. **اجمع أسئلتك في رسالة واحدة** بدل ما تسأل سؤال، تستنى رد، تسأل التاني.
2. **لو عندك سكرين شوت للمشكلة، ابعته من أول رسالة** بدل ما توصفها نصيًا وبعدين تبعت الصورة لاحقًا.
3. **قول صراحة لو عايز رد مختصر** ("جاوبني في سطرين بس") لما تكون عارف الإجابة المتوقعة وعايز تأكيد بس.
### و. تحذير عام
الالتزام بالقواعد دي **لا يبرر التسرّع في مهام معمارية حرجة** (زي ربط المحرك الحقيقي، أو أي حاجة موثّقة كـ"ثابتة" في `SDD.md`). التوفير يكون في الأسلوب والتنظيم، مش في تقليل الدقة على القرارات المهمة.