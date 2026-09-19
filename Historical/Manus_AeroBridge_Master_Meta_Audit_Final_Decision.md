# AeroBridge — التدقيق الرئيسي النهائي المحكَّم بالأدلة

**نوع الوثيقة:** Final Actionable Product Audit + Implementation Roadmap

**المؤلف:** Manus AI

**حالة القرار:** **Preserve and Harden — حافظ على النظام الصحيح، وأصلح عيوب الثقة والاتساق والوصول بأصغر نطاق آمن.**

**تاريخ التدقيق:** 17 أغسطس 2026

**نطاق هذه الوثيقة:** تحكيم الأدلة الحالية، التدقيقات المرفقة، المصدر المنقح، الصور البصرية، وسجل التحقق الحي. هذه الوثيقة لا تمنح تفويضاً لتعديل الكود، ولا تستبدل قرار المنتج أو المحتوى حيث وُسمت المسألة `NEEDS VALIDATION`.

> **الخلاصة التنفيذية:** AeroBridge ليس منتجاً يحتاج إلى إعادة تصميم. نواته الصحيحة موجودة: هوية Flight Deck Console مميزة، تجربة Practice تتمحور حول Terminal حقيقي محلي، حلقة تعلم مترابطة، حفظ محلي فعلي للأدلة، فصل واضح بين Growth Record وProgress Tracking، واهتمام جيد بالحركة المنخفضة وببديل الجدول للبيانات. النسخة المنقحة عالجت بالفعل عيبين شديدي الخطورة كانا ظاهرين في المصدر الأقدم: إرسال الإدخال الفارغ الذي كان يتحول إلى `FQD`، ورسالة Coach الحمراء الوهمية عند أول استخدام. لذلك لا يجوز إعادة فتح هذين العيبين كأنهما ما زالا قائمين.
>
> **المشكلات المفتوحة الآن** تتركز في ثلاثة جذور: أرقام ومقاييس لا تملك provenance واضحاً، حدود Assessment وبعض الأفعال التي تؤكد نجاحاً لم يحدث، وفجوات الوصول/التفاعل في مجموعات التحكم والـ overlays. توجد كذلك فجوة نطاقية لا يجوز إغفالها: **Customer Service** موجود كمسار ومجال منتج، عبر track selector وسيناريو خدمة ومهارة De-escalation، لكنه لا يملك في الأدلة الحالية منهج مراحل مكتملاً. يجب أن يدخل هذا المسار في التحليل، لكن يجب ألا نخترع له curriculum غير مثبت؛ الحالة الصحيحة المؤقتة هي `not yet available / in preparation`.

---

## 1. القرار النهائي

القرار العام هو **MODIFY بشكل موجّه**، مع اعتماد عدد من الإصلاحات الموجودة بالفعل في النسخة المنقحة بوصفها baseline يجب الحفاظ عليه. لا يوجد دليل يبرر تغيير بنية التنقل، أو إنشاء route مستقل لـ Assessment، أو دمج Growth Record وProgress Tracking، أو إضافة backend أو engine semantics أو metrics حقيقية. هذه التغييرات ستزيد المخاطر وتخالف نية المنتج المثبتة في `ideas.md`.[1]

| مجال القرار | الحكم | السبب الأدلةي |
|---|---|---|
| الهوية البصرية | **ACCEPT / PRESERVE** | Flight Deck Console متماسك بصرياً ووظيفياً، وتؤكده نية المنتج والصور السبع. |
| Terminal وPractice | **ACCEPT / PRESERVE WITH HARDENING** | هو سطح التدريب المركزي، وله command history وFocus Mode وlocal disclosure وmode structure حقيقية. |
| حلقة التعلم | **ACCEPT / PRESERVE** | توجد handoffs فعلية عبر `setPracticeContext` وحفظ/قراءة محلية للأدلة. |
| Consumer Services / Customer Service | **ACCEPT AS SCOPE SIGNAL; MODIFY PRESENTATION** | المسار موجود في selector والسيناريو والمهارة، لكن stage map الخدمي غير مثبت؛ لا يجوز عرضه كمحتوى تقني تحت اسم Service. |
| أرقام التقدم والمقاييس | **ACCEPT PROBLEM; MODIFY SOURCE OF TRUTH** | الأرقام الثابتة لا تتطابق مع arrays أو السجلات المعروضة، وبعضها قد يكون planned content لكن لا يوجد قرار محتوى يثبته. |
| Assessment boundary | **ACCEPT PROBLEM; MODIFY DISCLOSURE** | carry-over الحالي صامت، و`No hints` لا يشتق من الحالة الحقيقية. العزل الكامل يحتاج قراراً تربوياً. |
| اللغة العربية/RTL | **DEFER / NEEDS VALIDATION** | الـ toggle صادق جزئياً الآن، لكن لا توجد ترجمة أو `dir` أو عقد RTL كامل. |
| سطح المكتب/Tablet/keyboard/screen reader | **NEEDS VALIDATION** | لا توجد أدلة تشغيلية كافية لهذه البيئات، ولا يجوز تحويل CSS inference إلى حكم runtime. |

---

## 2. corpus الأدلة وحدود الوصول

تمت قراءة ملف `AeroBridge_Master_Meta_Audit_Prompt.md` باعتباره وثيقة الحوكمة، ثم جُمّدت مواد المشروع والأرشيفات والتدقيقات المرفقة. تمت قراءة ملفات المصدر الحالية في النسخة المنقحة، و`ideas.md`، وسجل التحقق الحي، ومقارنة المصدر المنقح بالمصدر الأقدم، كما تمت مشاهدة **42 tile** مرتبة من الصور السبع الطويلة. سجل الأدلة التفصيلي محفوظ في [Evidence Dossier][2]، وملاحظات الصور في [Visual Findings][3]، وسجل الأحكام claim-by-claim في [Claim Ledger][4].

المصدر الأقوى المتاح هو النسخة المنقحة المستخرجة من `AEROBRIDGE_REVISED_FINAL (1).zip`. مسار التنفيذ المحدد في تعليمات المشروع `/home/ubuntu/aerobridge-revised/aerobridge-share-preview` لم يكن موجوداً في sandbox أثناء هذا الاستئناف؛ لذلك لم تُجرَ تعديلات عليه ولم يُدّعَ فحص build لذلك المسار بعينه. عوضاً عن ذلك، استُخدم المصدر المنقح المستخرج، مع اعتماد `Phase_3_Live_Findings.md` كسجل تحقق حي للإصلاحات التي ثبتت في preview.[5]

> **قاعدة مهمة:** غياب runtime evidence لا يعني أن السلوك مكسور، كما أن وجود CSS لا يعني أن السلوك صحيح في كل جهاز. لذلك تُصنَّف tablet، keyboard، touch، screen-reader، font reachability، وRTL الكامل بوصفها `NEEDS VALIDATION` حيث لا يوجد دليل مباشر.

### 2.1 تسلسل قوة الأدلة

| الرتبة | نوع الدليل | استخدامه في هذا التدقيق |
|---|---|---|
| E4 / Direct | المصدر المنقح، runtime الموثق، أو صورة محددة | يثبت العيوب الحالية أو الإصلاحات الموجودة. |
| E3 / Strongly corroborated | مصدر + صورة، أو اشتقاق مستقل عبر نوعي دليل | يستخدم لرفع الثقة دون اعتبار التكرار دليلاً مستقلاً. |
| E2 / Cross-audit analysis | اتفاق تحليلي يعتمد غالباً على نفس المصدر | يستخدم لتتبع النمط، لا لإثباته وحده. |
| NEEDS VALIDATION | لا يوجد runtime/device/product decision كافٍ | لا يُحوَّل إلى P0/P1 إلزامي قبل الاختبار أو القرار. |
| REJECTED | يناقضه المصدر الأقوى أو يتجاوز الحدود | لا يدخل خارطة التنفيذ. |

التدقيقات التاريخية ليست أصواتاً. تكرار claim في أكثر من ملف لا يحوّله إلى حقيقة، وقد ثبت ذلك في ادعاءات bottom-nav ذي الأربع أعمدة، وإخفاء session readout، وسلوك caret مع reduced motion؛ القراءة الكاملة للـ cascade والصور عكست تلك الادعاءات.[6]

---

## 3. نطاق AeroBridge الكامل والمسارات التي لا يجوز إسقاطها

AeroBridge ليس شاشة Terminal منفردة. المصدر المنقح يعرّف خمسة top-level views: `Progression`, `Practice`, `Scenarios`, `Growth Record`, و`Progress Tracking`. Assessment ليس route مستقلاً؛ هو mode داخل Practice. هذا الوضع مدعوم مباشرة بالمصدر وبنية المنتج، ولذلك لا يُنشأ له route جديد.

### 3.1 Consumer Services / Customer Service

يوجد دليل مباشر على مسار إضافي لا تمثله بعض التدقيقات بصورة كافية. في `Home.tsx` يظهر track selector بين `Technical Track` و`Customer Service`; يظهر كذلك سيناريو `SC-026 — Difficult customer at the airport` بفئة `Customer Service` ومهارات `De-escalation`, `English`, و`Recovery`; كما تظهر مهارة `DE-ESC — De-escalation` في سجل المهارات.[7]

لكن الدليل نفسه يثبت حدوداً مهمة: مصفوفة `levels` واحدة وثابتة ومحتواها تقني، ومرحلة `STAGE MAP` تُعرض بوصفها `Technical workflow milestones` حتى بعد اختيار Customer Service. إذن لدينا **مسار منتج حقيقي من حيث النية والإشارة والسيناريو**، لكن ليس لدينا ما يثبت وجود curriculum service كامل أو stage map مستقل. الحكم المحكّم هو التالي:

| سؤال النطاق | الحكم |
|---|---|
| هل Customer Service موجود في المنتج؟ | نعم، **مؤكد مباشرة**. |
| هل هو مسار مستقل مكتمل مثل Technical؟ | **NEEDS VALIDATION**؛ لا توجد مراحل خدمة كافية في المصدر. |
| هل يجوز إخفاؤه من التدقيق لأنه ظهر في سيناريو واحد فقط؟ | لا. وجوده المباشر يجعله جزءاً من scope analysis. |
| هل يجوز عرض Technical milestones تحت Service؟ | لا؛ هذا عيب محتوى/IA يجب إصلاحه. |
| ما الحالة الآمنة الآن؟ | `Customer Service curriculum is being prepared` أو `Not yet available in this preview`. |
| هل يجوز اختراع مراحل خدمة؟ | لا؛ ذلك سيخالف product boundary ويصنع product truth غير مدعوم. |

هذا المسار يجب أن يظهر في roadmap بوصفه **P1 content-integrity correction**، لا بوصفه دعوة لبناء curriculum كامل ضمن هذه الدورة.

### 3.2 ما يجب الحفاظ عليه

> **VALID EXISTING SYSTEM — PRESERVE:** هوية Flight Deck Console، لوحة الألوان البحرية مع Vector Blue والدلالات التشغيلية الأخضر/العنبر/الأحمر، monospace readouts، Terminal-first Practice، Learn/Practice/Assessment، Focus Mode، Arrow Up/Down history recall، local/illustrative disclosure، حلقة Progression → Practice → Assessment → Growth → Tracking → Scenarios → Next Action، separate Growth/Tracking، localStorage evidence pipeline، reduced-motion coverage، chart + same-data table fallback، وPractice-centered mobile rail.

الهوية ليست زينة. الـ Terminal chrome والـ monospace يضبطان توقع الدقة ويتوافقان مع تدريب command recall. كما أن فصل Growth عن Tracking ليس تكراراً عبثياً: الأول يفسّر skill-level patterns، والثاني يعرض session-level trend. دمجهما سيكون تغييراً أكبر من المشكلة التي يحاول حلها.[1]

---

## 4. ما أُغلق بالفعل وما بقي مفتوحاً

النسخة المنقحة ليست المصدر الأقدم. لذلك يجب أن تميّز خطة التنفيذ بين **closed regressions** و**live findings**.

| Finding تاريخي | حالة النسخة المنقحة | قرار التدقيق النهائي |
|---|---|---|
| blank submit → `FQD` | عولج guardياً، وثبت live أن LOG بقي 01 ولم يظهر row | **أغلق؛ حافظ واختبر regression فقط** |
| first-use Coach red error | أصبح `READY · AWAITING COMMAND` neutral، وثبت live | **أغلق؛ حافظ واختبر** |
| seeded timer 4:32 | يبدأ من 0 | **أغلق الجزء الأساسي؛ راجع provenance للمقاييس المتبقية** |
| fresh accuracy 86% | أصبحت 0 قبل submission | **أغلق الجزء الأساسي** |
| viewport `maximum-scale=1` | أُزيل | **أغلق؛ اختبر zoom** |
| fonts commented/wrong | روابط Cairo/IBM Plex Mono/Space Grotesk أصبحت فعالة في HTML | **أغلق source-level؛ runtime reachability NEEDS VALIDATION** |
| mode tabs بلا semantics | mode-tabs أصبحت `role=tablist` و`aria-selected` | **جزئي؛ Growth/track/filter/metric ما زالت مفتوحة** |
| mobile input 15px | النسخة المنقحة تحتوي 16px | **أغلق source-level؛ device validation مطلوب** |
| Assessment carry-over | ما زال قائماً | **P0 open** |
| Coach Open reference | ما زال toast-only | **P1 open** |
| static counts/provenance | ما زالت أرقام عديدة ثابتة | **P0/P1 open حسب الأثر** |
| Customer Service stage mismatch | ما زال technical map تحت Service selector | **P1 open** |

سجل التحقق الحي يؤكد أن TypeScript check وproduction build يمران في المرحلة السابقة، مع تحذيرات host-specific تخص analytics placeholders و`/manus-storage/...` assets.[5] هذه النتيجة لا تغلق portability أو deployment reachability؛ لكنها تثبت أن الإصلاحات المنقحة لم تكسر build في بيئة التحقق المسجلة.

---

## 5. التدقيق المحكَّم: النتائج الرئيسية

النتائج الآتية هي findings الحالية فقط. الإصلاحات المغلقة مذكورة للتتبع ولا تعاد كأعمال جديدة. كل finding يستخدم عقد المشكلة المطلوب: المشكلة، الأهمية، الدليل، وضع الدليل، الاستقلالية، المنطقة، السبب الجذري، التوصية، الأولوية، الآثار الجانبية، معيار القبول، اختبار regression، والثقة.

### F-001 — أرقام ومقاييس غير مملوكة بوضوح لمصدر بيانات

| الحقل | الحكم |
|---|---|
| **المشكلة** | النسخة المنقحة تعرض `3 / 8 stages` رغم أن مصفوفة `levels` تضم 6 عناصر، و`23 / 40 scenarios` رغم أن `scenarios` تضم 5 عناصر، و`LOG 04 / 12` مع ثلاثة event cards مرئية، إضافة إلى `128 / 210` و`6 / 9 command sets` ومقاييس أخرى لا يظهر مالك بيانات حقيقي لها. |
| **لماذا يهم** | AeroBridge يقدّم نفسه كتدريب قائم على evidence. عندما لا تتطابق headline numbers مع الصفوف أو arrays، يفقد المتدرب القدرة على التمييز بين evidence الحقيقي وpreview copy. هذا يضر الثقة والتعلم، وليس مجرد تجميلاً رقمياً. |
| **الدليل** | `levels` ستة عناصر و`scenarios` خمسة و`seedProgress` ثلاثة في المصدر المنقح؛ الأرقام الثابتة تظهر في `Progression`, `Scenarios`, `Practice`, و`Growth`. الصور 55514 و55517 و55526 و55528 تؤكد presentation الفعلية. [7] [3] |
| **Evidence Status** | **E4 / Direct** للـ mismatch؛ **NEEDS VALIDATION** لمعنى الأرقام الأكبر: هل هي planned totals أم أخطاء؟ |
| **Evidence Independence** | المصدر + صور مستقلة نسبياً؛ ليس اعتماداً على عدد التدقيقات. |
| **Affected Area** | Progression, Practice footer, Scenarios, Growth Record, labels الخاصة بالـ route/readout. |
| **Root Cause** | غياب provenance contract موحّد يميّز بين `available now`, `planned`, `illustrative`, و`local evidence`. |
| **Recommendation** | اشتق الأرقام التي تلخّص arrays أو rows مباشرة من المصدر. إذا كانت الأرقام الأكبر مقصودة للمستقبل، صغها مثل `6 available now / 8 planned` أو `3 recorded / 12 planned events`. أصلح `Exchanges & Refunds` ما لم يكن له مصدر فعلي في dataset. لا تضف عناصر وهمية لمجاراة الرقم. |
| **Priority** | **P0 — Blocking / Trust integrity** للـ derivation؛ قرار totals النهائي **DEFER**. |
| **Side Effects** | ستتغير screenshots والأرقام المعروضة؛ وهذا أثر مقصود. يجب ألا يتغير scoring أو localStorage shape. |
| **Acceptance Criteria** | كل رقم يطابق source array/rows أو يحمل qualifier واضحاً؛ لا يظهر category بلا عنصر مطابق؛ كل metric يملك provenance text قابلاً للقراءة والربط البرمجي. |
| **Regression Test** | أضف/احذف عنصراً من `levels` و`scenarios` وتحقق أن العرض يتغير تلقائياً؛ امسح السجلات وتحقق من `0 recorded`; راجع Growth/Tracking بعد assessment حقيقي. |
| **Confidence / Decision** | **Very High / ACCEPT + MODIFY**. |

### F-002 — Assessment state contract غير صريح

| الحقل | الحكم |
|---|---|
| **المشكلة** | عند الانتقال إلى Assessment، تستمر `commandHistory` و`hintCount` من Learn/Practice، بينما label يظل `No hints` ما لم تكتمل الجلسة. النتيجة أن score قد يشمل نشاطاً سابقاً دون إفصاح، والواجهة قد تقول عكس الحالة الفعلية. |
| **لماذا يهم** | هذا يمس integrity للنتيجة التعليمية المركزية. المتدرب يحتاج أن يعرف ما الذي يُقاس، وما الذي انتقل، وما إذا كانت hints أثرت في الجلسة. |
| **الدليل** | `setMode` في `Home.tsx` يغيّر mode ويصفّر `sessionComplete` فقط؛ `assessmentScore(commandHistory, hintCount)` يستخدم الحالة المشتركة؛ label Assessment في mode tabs يعتمد على `sessionComplete` لا `hintCount`.[7] |
| **Evidence Status** | **E4 / Direct**. |
| **Evidence Independence** | مصدر حالي مباشر؛ لا يحتاج consensus. |
| **Affected Area** | Practice modes، AssessmentReport، hint disclosure، scoring interpretation. |
| **Root Cause** | لا يوجد entry contract معلن بين guided practice وevaluated assessment. |
| **Recommendation** | في الإصلاح الآمن الأول، عند الدخول إلى Assessment مع history/hints سابقة اعرض إفصاحاً صريحاً مثل `N prior commands / N hints carried into this session`. اجعل label مشتقاً من `hintCount`. لا تعزل الحالة ولا تغيّر scoring formula قبل قرار تربوي يحدد هل Assessment يبدأ من صفر أم يقيس continuity. |
| **Priority** | **P0**. |
| **Side Effects** | قد يرى المتدرب disclosure إضافياً؛ لا يجب أن تتغير نتيجة score أو persistence في هذه المرحلة. |
| **Acceptance Criteria** | صفر نشاط سابق = لا disclosure و`No hints`; نشاط سابق = disclosure دقيق وlabel يطابق العدد؛ Finish Session يكتب نفس record shape. |
| **Regression Test** | Learn command → Assessment؛ Reference open قبل Assessment؛ Assessment بدون hints؛ Assessment بعد hint؛ Retry assessment؛ تحقق من Growth/Tracking record. |
| **Confidence / Decision** | **Very High / ACCEPT**؛ isolation الكامل **NEEDS VALIDATION**. |

### F-003 — أفعال عالية الثقة تؤكد نجاحاً غير موجود

| الحقل | الحكم |
|---|---|
| **المشكلة** | `Coach → Open reference` يعرض toast يقول إن المرجع فُتح لكنه لا يستدعي `setReferenceOpen`. `Backup` في Growth يعرض نجاح إنشاء backup دون file/export/storage write قابل للتحقق. وهناك actions أخرى toast-only مثل بعض section actions وSort وFilters. |
| **لماذا يهم** | false confirmation يعلّم المتدرب أن النظام يقول “تم” حتى عندما لم يحدث شيء. الضرر أعلى في Coach لأنه يقع في مسار corrective next move، وفي Backup لأنه يوحي بسلامة evidence. |
| **الدليل** | source المنقح: Coach action في السطر 319 toast-only، Backup في Growth السطر 351 toast-only، Sort في Scenarios لا يعيد ترتيب القائمة. [7] |
| **Evidence Status** | **E4 / Direct** للـ Coach/Backup/Sort؛ visibility الفعلية للـ toast تحتاج runtime validation بسبب غياب `<Toaster/>`. |
| **Evidence Independence** | مصدر حالي مباشر؛ الصور تؤكد وجود controls لا behavior الداخلي. |
| **Affected Area** | Coach, Growth, Scenarios, shared feedback. |
| **Root Cause** | غياب interaction honesty contract: control مرئي وقابل للنقر دون state transition أو destination حقيقي. |
| **Recommendation** | اربط Coach reference بنفس mechanism الخاص بمرجع Terminal، وبنفس hint behavior؛ أعد تسمية Backup إلى `Local preview — no backup file is written` ما لم يعتمد المنتج export محلياً حقيقياً؛ اربط Sort بالحقول الموجودة؛ أزل أو وسم بقية actions كـ preview/roadmap بدلاً من toast نجاح. Mount `<Toaster/>` كإصلاح resilience منفصل قبل اعتبار toast feedback مؤكداً. |
| **Priority** | Coach وBackup **P1 قريب من P0**؛ بقية toast-only **P1/P2 حسب أثرها**. |
| **Side Effects** | قد تختفي بعض الأزرار أو تتغير copy؛ يجب عدم اختراع routes أو backend. |
| **Acceptance Criteria** | كل control إما يغيّر state أو يفتح destination أو يوضح عدم التوفر؛ Coach يفتح نفس drawer؛ Backup لا يدعي كتابة غير موجودة؛ Sort يغيّر ترتيباً مرئياً. |
| **Regression Test** | افتح Reference من Terminal ومن Coach وقارن state/hint؛ اضغط Backup وتحقق من وجود artifact إن كان export معتمداً؛ جرّب كل toast-only control وسجّل النتيجة. |
| **Confidence / Decision** | **High / ACCEPT**. |

### F-004 — Customer Service موجود في scope لكن يعرض curriculum تقنياً تحت اسم خدمة

| الحقل | الحكم |
|---|---|
| **المشكلة** | اختيار Customer Service يغيّر الوصف فقط، بينما stage map يبقى `Technical workflow milestones` ومحتوى `levels` تقنياً. في المقابل يوجد سيناريو خدمة حقيقي ومهارة De-escalation، لذلك إسقاط المسار من التدقيق سيكون omission في نطاق المنتج. |
| **لماذا يهم** | هذا يضلل المتدرب حول عمق المسار، وقد يفسر اختياره لمسار خدمة على أنه انتقل إلى curriculum مختلف بينما هو ما زال يرى Technical stages. كما أن service training ليس مجرد تسمية؛ له أهداف تعلم مختلفة مثل empathy وrecovery وEnglish. |
| **الدليل** | selector وdescription في `Progression`; `SC-026` Customer Service و`DE-ESC` في arrays؛ render milestones غير مشروط بالـ track.[7] الصور 55517 و55514 تؤكد وجود السيناريو والselector.[3] |
| **Evidence Status** | **E4 / Direct** للـ mismatch ووجود scope signal؛ **NEEDS VALIDATION** لمدى اكتمال curriculum الخدمي. |
| **Evidence Independence** | مصدر + صورة + Project Knowledge؛ لا يعتمد على التكرار. |
| **Affected Area** | Progression track selector، stage map، Scenarios، Growth skills. |
| **Root Cause** | track selector ليس له data contract يربط selected track بمصدر milestones مستقل. |
| **Recommendation** | في هذه الدورة، عندما يكون track = service، اعرض `Customer Service curriculum is being prepared` أو `Not yet available in this preview` باستخدام StateNotice، وأبقِ Technical content تحت Technical فقط. احتفظ بـ `SC-026` كسيناريو خدمة مؤكد. لا تنشئ service stages أو scoring semantics غير موجودة. |
| **Priority** | **P1 — Content/IA integrity**. |
| **Side Effects** | سيظهر empty/unavailable state بدلاً من قائمة مراحل؛ هذا أصح من عرض محتوى خاطئ. |
| **Acceptance Criteria** | اختيار Service لا يعرض أي Technical milestone؛ Technical selector لا يتغير؛ scenario `SC-026` يبقى قابلاً للاكتشاف؛ copy تشرح حدود preview. |
| **Regression Test** | toggle Technical → Service → Technical؛ تحقق من stage labels والمحتوى؛ افتح `SC-026` وتحقق من context؛ راجع عدم تغيير Technical flow. |
| **Confidence / Decision** | **High / ACCEPT + MODIFY**؛ بناء curriculum كامل **DEFER**. |

### F-005 — readiness language يتجاوز حدود local simulation

| الحقل | الحكم |
|---|---|
| **المشكلة** | `Operationally ready` يظهر كـ verdict عند score 85، و`Saudi readiness` يظهر كعنوان جانبي، مع أن `ideas.md` يعرّف المنتج كـ local mock/presentation-first ولا يوفر authority أو rubric خارجياً. |
| **لماذا يهم** | قد يفهم المتدرب أو جهة عمل أن score يثبت operational competency أو readiness رسمية. هذا يخلط illustrative output مع qualification. |
| **الدليل** | `AssessmentReport` في السطر 234، `SideNav` في 178، و`ideas.md` الذي يمنع real metrics ويشترط وضوح local/non-production.[1] [7] |
| **Evidence Status** | **E4 / Direct**. |
| **Evidence Independence** | مصدر + product intent. |
| **Affected Area** | Assessment, sidebar, Growth/Reports copy. |
| **Root Cause** | vocabulary غير محدود صراحةً بحدود local training signal. |
| **Recommendation** | استخدم `Strong local result`, `Local session signal`, `Review recommended`, أو `Continue to scenario practice`. أبقِ feedback category structure وnext-action loop. لا تستخدم Saudi readiness إلا إذا توفر قرار منتج ومقياس موثوق يثبت المقصود. |
| **Priority** | **P1**. |
| **Side Effects** | تخفيف copy قد يقلل الإحساس التسويقي بالـ readiness لكنه يزيد الصدق التعليمي. |
| **Acceptance Criteria** | لا توجد عبارة certification-grade دون تعريف authority/rubric؛ كل verdict يذكر local training scope؛ Report يبقى مفهوماً وقابلاً للتنفيذ. |
| **Regression Test** | راجع جميع strings المحتوية `ready`, `readiness`, `qualified`, `operational`; نفّذ score منخفضاً ومتوسطاً وعالياً وتحقق من copy. |
| **Confidence / Decision** | **High / ACCEPT + MODIFY**. |

### F-006 — فجوات semantics والوصول في controls والـ landmarks

| الحقل | الحكم |
|---|---|
| **المشكلة** | mode-tabs فقط حصلت على semantics؛ Growth tabs وtrack/filter/metric controls لا تملك selection semantics مؤكدة. لا يوجد `<main>` أو skip link، وdesktop SideNav لا يحمل `aria-current`. `AnimatedBar` ليس `progressbar`. |
| **لماذا يهم** | المتدرب الذي يستخدم keyboard أو assistive technology قد لا يعرف الخيار المحدد أو الصفحة الحالية، ولا يستطيع تفسير bar progress كقيمة. هذه فجوة وصول مباشرة، لا preference بصري. |
| **الدليل** | source المنقح: mode semantics في 309، plain buttons في Growth/Scenarios/Tracking، shell في 370، AnimatedBar في 139–142؛ الصور تؤكد أن controls tab-like بصرياً.[7] |
| **Evidence Status** | **E4 / Direct** للـ markup gaps؛ actual screen-reader output **NEEDS VALIDATION**. |
| **Evidence Independence** | مصدر + visual confirmation؛ لا تعتمد على audit consensus. |
| **Affected Area** | Shared shell، Growth، Scenarios، Progression، Tracking، Practice. |
| **Root Cause** | عدم وجود shared interaction-semantics pattern يُطبّق حسب behavior. |
| **Recommendation** | استخدم `role=tablist/tab/tabpanel` للـ panel swaps، و`aria-pressed` للتبديلات/الفلاتر حيث يلزم. أضف `<main id=main-content>` وskip link وdesktop `aria-current`. أضف `role=progressbar`, `aria-valuenow/min/max` للـ AnimatedBar عندما يكون progress حقيقياً. لا تغيّر visual styling. |
| **Priority** | **P1**. |
| **Side Effects** | قد تتغير keyboard behavior إن أُدخل roving tabindex؛ يجب اختيار pattern وفق السلوك الفعلي لا الشكل. |
| **Acceptance Criteria** | selected state معلن لكل group؛ tab panels مرتبطة؛ skip link يعمل؛ current page معلن على desktop؛ progress values قابلة للقراءة. |
| **Regression Test** | keyboard-only pass؛ فحص DOM/axe؛ screenshot diff للتأكد من عدم تغير الشكل؛ اختبار Growth tabs وScenarios filters وTracking metric switcher. |
| **Confidence / Decision** | **High / ACCEPT**؛ screen-reader closure **NEEDS VALIDATION**. |

### F-007 — overlays وFocus Mode تحتاج عقد تركيز، مع عدم تغيير طبيعتها

| الحقل | الحكم |
|---|---|
| **المشكلة** | لا يوجد دليل مصدر على Escape handling أو return focus أو focus containment في Focus Mode، Reference drawer، وmobile navigation drawer. |
| **لماذا يهم** | قد ينتقل keyboard focus إلى background obscured أو يفقد المستخدم موضعه، خصوصاً في drawer وFocus Mode. |
| **الدليل** | لا توجد handlers موثقة في المصدر المنقح؛ الصور لا تكفي لإثبات keyboard behavior. [7] |
| **Evidence Status** | **E4 / Confirmed source gap**؛ نجاح الحل **NEEDS VALIDATION**. |
| **Evidence Independence** | source gap مباشر؛ لا يُثبت من تكرار التدقيقات. |
| **Affected Area** | Focus Mode، Reference drawer، mobile drawer. |
| **Root Cause** | overlays/workspace states لا تشترك في focus-management contract. |
| **Recommendation** | أضف Escape وreturn focus، واستخدم `role=dialog` و`aria-modal` فقط حيث يكون surface modal فعلاً. Focus Mode قد يكون immersive workspace لا dialog؛ لا تفرض trap غير مناسب. حافظ على `:has()` scroll-lock. |
| **Priority** | **P1**. |
| **Side Effects** | focus trap ناقص قد يكون أسوأ من غيابه؛ التنفيذ يحتاج اختباراً حقيقياً. |
| **Acceptance Criteria** | keyboard يدخل ويستخدم ويخرج من كل surface؛ Escape يعيد focus إلى trigger؛ background لا يدخل tab order عندما يكون modal. |
| **Regression Test** | keyboard-only test على desktop/mobile widths؛ screen reader smoke test؛ فتح/غلق reference من كل entry point. |
| **Confidence / Decision** | **High gap / ACCEPT WITH VALIDATION GATE**. |

### F-008 — skill trends لا تتفق مع معنى favorability

| الحقل | الحكم |
|---|---|
| **المشكلة** | Skills مرتفعة مثل AN/SS تحمل `trend: down` وتُرسم بسهم لأسفل أخضر، بينما skills الضعيفة FQD/FXP تحمل `up` وتُرسم amber؛ النص المصاحب يفسر `up` كـ Improving. |
| **لماذا يهم** | القراءة الأولى للسهم واللون تناقض النص؛ وقد يظن المتدرب أن انخفاض المهارة الجيدة أو ارتفاع المهارة الضعيفة هو نفس نوع trend. |
| **الدليل** | `skillRows`, `SkillRow`, trend class، وhover copy في المصدر المنقح.[7] |
| **Evidence Status** | **E4 / Direct**. |
| **Evidence Independence** | source مباشر؛ الصورة تؤكد وجود arrows/values. |
| **Affected Area** | Growth Record strength/attention panels، mobile detail. |
| **Root Cause** | trend field يخلط raw direction مع favorable direction. |
| **Recommendation** | عرّف contract واضحاً: إما `up/down` يعني تغيراً خاماً ويُعرض بنص محايد، أو اشتق icon/tone من favorability لكل skill. حافظ على underlying data حتى يحسم product owner semantics. |
| **Priority** | **P1**. |
| **Side Effects** | قد تتغير ألوان/اتجاهات ظاهرة؛ لا تغيّر score values. |
| **Acceptance Criteria** | arrow/color/copy متوافقة لكل row؛ skill مرتفعة لا توحي بتدهور دون text evidence. |
| **Regression Test** | matrix تغطي values 20/45/60/88/92؛ تحقق desktop/mobile selected state. |
| **Confidence / Decision** | **Medium–High / ACCEPT + MODIFY**. |

### F-009 — mobile coaching parity ناقصة

| الحقل | الحكم |
|---|---|
| **المشكلة** | `skill-hover-preview` مفيد على desktop عبر hover/focus، لكنه يختفي عند ≤739px ولا يوجد touch-equivalent ظاهر. |
| **لماذا يهم** | mobile ليس نسخة ثانوية؛ وهو device class الظاهر في الأدلة. اختفاء تفسير skill يحرم المتدرب من “why/what next” في اللحظة التي يحتاج فيها coaching. |
| **الدليل** | CSS/source وscreenshots Growth mobile؛ لا يوجد selected detail path مثبت للـ preview نفسه.[7] [3] |
| **Evidence Status** | **E4 / Direct** لغياب العرض؛ فعالية الحل **NEEDS VALIDATION**. |
| **Evidence Independence** | source + visual evidence. |
| **Affected Area** | Growth skill rows mobile. |
| **Root Cause** | الاعتماد على hover semantics في سطح لمس. |
| **Recommendation** | حوّل skill row إلى selected/tap state يعرض نفس content، مع الحفاظ على desktop hover/focus. اربط selected state بـ `aria-expanded` أو `aria-describedby` بحسب markup. |
| **Priority** | **P1**. |
| **Side Effects** | زيادة ارتفاع Growth على الهاتف؛ يجب الحفاظ على readable density. |
| **Acceptance Criteria** | tap واحد يكشف latest signal وcoach next؛ tap ثانٍ يغلق أو ينتقل بوضوح؛ لا يحتاج hover. |
| **Regression Test** | touch emulation <740px؛ keyboard focus ≥740px؛ لا يتغير desktop screenshot. |
| **Confidence / Decision** | **High / ACCEPT**. |

### F-010 — Mobile Terminal يستخدم مساحة ميتة ثابتة

| الحقل | الحكم |
|---|---|
| **المشكلة** | `.terminal-gap { height: 130px; }` ثابتة، وتظهر كفراغ كبير خصوصاً في الجلسة الفارغة. |
| **لماذا يهم** | يقلل مساحة response/input في سطح التدريب الأساسي، وقد يزيد scroll/keyboard pressure. |
| **الدليل** | CSS المصدر المنقح وPractice screenshots، مع وجود `terminal-active-line` في flex structure.[7] [3] |
| **Evidence Status** | **E4 / Direct** للمساحة؛ keyboard impact **NEEDS VALIDATION**. |
| **Evidence Independence** | source + visual. |
| **Affected Area** | Practice mobile Terminal. |
| **Root Cause** | spacer ثابت يحاول حل anchoring بدلاً من الاعتماد على flex/active-line layout. |
| **Recommendation** | قلّل أو أزل spacer، واترك bottom anchoring للمسار الموجود؛ لا تغيّر sticky input أو safe-area. |
| **Priority** | **P1**. |
| **Side Effects** | قد يتغير vertical rhythm وموضع active line؛ يلزم screenshot comparison. |
| **Acceptance Criteria** | لا فراغ مهيمن في 0-history؛ latest response/input مرئيان؛ 1 و10+ entries لا تنهاران. |
| **Regression Test** | 320/360/390/430px، 0/1/10+ history، normal/focus mode، keyboard device test. |
| **Confidence / Decision** | **High / ACCEPT**، keyboard closure **NEEDS VALIDATION**. |

### F-011 — Navigation semantics والـ breadcrumb numbering

| الحقل | الحكم |
|---|---|
| **المشكلة** | Bottom rail يرتب العناصر بصرياً `Route / Apply / Train / Evidence / Trend` ليضع Train في المركز، بينما breadcrumb numbers تظل canonical order؛ لذلك قد يظهر Scenarios كـ `03` في الموضع الثاني وPractice كـ `02` في الموضع الثالث. |
| **لماذا يهم** | يخلق تضارباً في wayfinding، لكنه لا يثبت أن five-item nav نفسها خاطئة. |
| **الدليل** | `orderedItems` في BottomNav والمحتوى route labels في المصدر، والصور تؤكد الخمسة icons وترتيبها.[7] [3] |
| **Evidence Status** | **E4 / Direct**. |
| **Evidence Independence** | source + screenshot. |
| **Affected Area** | BottomNav، page eyebrows، Progression/Practice/Scenarios/Growth/Tracking. |
| **Root Cause** | رقم route مشتق من canonical nav array لا من display order أو purpose واضح. |
| **Recommendation** | إمّا اشتق الرقم من display order في mobile فقط، أو احذف numeric breadcrumb واحتفظ بالوصف. لا تزيل Train-centering. |
| **Priority** | **P1**. |
| **Side Effects** | تغير copy في eyebrows فقط؛ desktop canonical numbering قد يبقى كما هو. |
| **Acceptance Criteria** | لا يرى mobile user رقماً يناقض موضع tap؛ desktop يبقى مقروءاً. |
| **Regression Test** | انقر الخمسة بالترتيب mobile وراجع eyebrow؛ side-nav desktop remains stable. |
| **Confidence / Decision** | **High / ACCEPT + MODIFY**. |

### F-012 — Resilience وtoast rendering غير مثبتين

| الحقل | الحكم |
|---|---|
| **المشكلة** | `App.tsx` يعرض `Home` فقط؛ لا يوجد mounted ErrorBoundary أو Toaster. مكونات ErrorBoundary/NotFound موجودة لكن غير موصولة، ووجود 19 toast call لا يثبت أنها تظهر للمستخدم. |
| **لماذا يهم** | runtime error قد يظهر blank page، وtoast-only actions قد تكون أسوأ من مجرد false confirmation إذا لم يكن لها rendering surface. |
| **الدليل** | App source المنقح ووجود المكونات غير mounted؛ Phase 3 يسجل build warnings لا compile failures.[7] [5] |
| **Evidence Status** | **E4 / Direct** لغياب mount؛ visible toast behavior **NEEDS VALIDATION**. |
| **Evidence Independence** | source مباشر. |
| **Affected Area** | app shell، all toast feedback، fallback surfaces. |
| **Root Cause** | app root minimal دون resilience/feedback mounting contract. |
| **Recommendation** | mount styled ErrorBoundary حول Home، دون router expansion؛ mount Toaster؛ اخفِ raw stack trace؛ restyle/retire NotFound قبل أن يصبح reachable. |
| **Priority** | **P1**. |
| **Side Effects** | قد يظهر toast في موضع جديد ويؤثر على screenshots؛ يجب تثبيت style identity. |
| **Acceptance Criteria** | forced error يعرض fallback Flight Deck؛ toast visible عند trigger؛ لا raw stack trace؛ build يبقى ناجحاً. |
| **Regression Test** | force render error؛ trigger all toast families؛ refresh/reload؛ اختبار keyboard fallback. |
| **Confidence / Decision** | **High gap / ACCEPT**، runtime consequence validation required. |

---

## 6. قرارات الرفض والتأجيل

### 6.1 مرفوض

| القرار المرفوض | سبب الرفض |
|---|---|
| إعادة تصميم كاملة أو تحويل المنتج إلى dashboard عام | يخالف `reference-preservation project` ويزيد blast radius. |
| إنشاء Assessment route مستقلاً | Assessment mode داخل Terminal ومتصّل بهوياً وتدريبياً. |
| دمج Growth Record وProgress Tracking | يخفي فرق evidence grain بين skill interpretation وsession trend. |
| تغيير command matching أو scoring formula | لا دليل أن engine هو سبب مشكلات العرض؛ الحدود تمنع اختراع semantics. |
| إضافة autocomplete أو commands جديدة | توسع engine ويفسد recall-based training. |
| تفعيل `Map.tsx` لأن `View map` موجود | dead component ليس requirement؛ activation speculative. |
| تحويل Coach إلى FAB/bottom-sheet الآن | Coach بالفعل in-flow وتابع للTerminal؛ لا device evidence على فشل placement. |
| إضافة processing/interrupted states | submission synchronous ولا يوجد trigger حقيقي. |
| ترحيل chart إلى library | chart + table fallback حالي ومربوط بنفس data، وهو strength يجب الحفاظ عليه. |
| partial RTL | سيكون سلوكاً مضللاً؛ يلزم قرار scope وtranslation وdir/lang واختبار bidi كامل. |
| اعتماد consensus كدليل | يخالف hierarchy والاستقلالية؛ استخدم المصدر والruntime أولاً. |

### 6.2 مؤجل أو مشروط بالتحقق

| المسألة | الحالة المطلوبة قبل القرار |
|---|---|
| totals 8/40/12/210 | قرار content owner يحدد planned totals أو available totals. |
| Customer Service curriculum الكامل | curriculum source أو product brief يحدد المراحل والقياس. |
| Assessment isolation الكامل | قرار learning design يحدد continuous session أم clean evaluation. |
| Tablet 740–1099 | render walkthrough عند 768/834/1024. |
| Desktop 1100+ | screenshots عند 1280/1440، مع check للـ Terminal/Coach split. |
| Native keyboard | iOS Safari وAndroid Chrome عند 320/360/390/430. |
| Screen reader | NVDA/VoiceOver/TalkBack بعد semantics implementation. |
| Touch targets | physical/emulated touch walkthrough؛ لا يكفي CSS number. |
| Font loading | computed family وnetwork/reachable asset في deployment environment. |
| Hamburger duplication | فحص drawer contents قبل أي إزالة أو دمج. |
| Toast rendering | browser trigger بعد mount أو تحقق مباشر من hosting. |

---

## 7. خارطة التنفيذ الآمنة

الخارطة ليست ملخصاً أعمى لكل توصية تاريخية. هي ترتيب dependency-aware، وتحدد ما يتغير وما يبقى untouched.

### P0 — Trust and assessment integrity

| الترتيب | التغيير | المكونات | ما يبقى دون لمس | معيار الخروج |
|---|---|---|---|---|
| P0.1 | اشتق/وسم كل counts والـ provenance | Progression, Practice, Scenarios, Growth | scoring, persistence, arrays as sample data | لا mismatch صامت؛ planned/local واضح. |
| P0.2 | أصلح Assessment entry disclosure وhint label | Practice mode tabs/AssessmentReport | scoring formula، localStorage shape، mode architecture | carry-over معلن؛ label يطابق count. |
| P0.3 | أغلق Customer Service misleading stage map | Progression track selector/stage map | Technical content وSC-026 | Service لا يعرض Technical milestones؛ unavailable state واضح. |
| P0.4 | أزل readiness/certification implication | AssessmentReport, SideNav, Growth copy | debrief structure وnext-action loop | كل verdict local/scope-limited. |

### P1 — Functional honesty, accessibility, and mobile comfort

| الترتيب | التغيير | المكونات | الاعتماد | ما يبقى دون لمس |
|---|---|---|---|---|
| P1.1 | Coach reference الحقيقي وBackup honesty وSort/filter actions | Coach, Growth, Scenarios, Section actions | Toaster decision لكل feedback | لا backend ولا new route. |
| P1.2 | Shared semantics وlandmarks | shell, tabs, filters, metric switcher, AnimatedBar | لا dependencies خارج React/DOM | visual styling وchart/table. |
| P1.3 | Focus/Escape/return focus | Focus Mode, Reference, mobile drawer | keyboard design validation | `:has()` scroll-lock وplacement. |
| P1.4 | trend favorability وmobile skill coaching | Growth SkillRow/CSS | skill semantics decision | values وdesktop hover. |
| P1.5 | تقليل terminal-gap | Practice CSS | device keyboard test | sticky input/safe-area/history. |
| P1.6 | mount Toaster وstyled ErrorBoundary | App.tsx, fallback components | forced-error test | main route architecture. |
| P1.7 | breadcrumb numbering | BottomNav/page eyebrows | visual walkthrough | Train-centering والخمسة عناصر. |

### P2 — Hygiene and polish

| الترتيب | التغيير | القرار |
|---|---|---|
| P2.1 | token consolidation | بعد visual snapshot؛ لا تغير values. |
| P2.2 | إزالة duplicate per-command toasts | بعد التأكد أن Terminal history كافية. |
| P2.3 | touch target tuning | بعد touch validation، مع الحفاظ على density. |
| P2.4 | remove/wire unreachable `hint-dependency` | قرار taxonomy. |
| P2.5 | document/bundle hosted assets and analytics | handoff portability فقط. |
| P2.6 | simplify KPI ornaments | إذا أثبت comprehension test وجود noise. |
| P2.7 | توثيق Map residue | لا activation. |

### ما يبقى untouched صراحةً

لا تغيّر `assessmentScore`, command matching، `localStorage` record shape، context handoffs، route model، Practice/Assessment mode model، `setPracticeContext`، chart/table fallback، reduced-motion block، sticky input، safe-area behavior، Arrow Up/Down recall، أو الهوية البصرية العامة. أي patch يمس هذه المناطق يجب أن يفتح change request جديداً مع evidence مختلف.

---

## 8. مصفوفة state وlearning contract

| الحالة | العقد الصحيح | الأثر على evidence | الحكم الحالي |
|---|---|---|---|
| First use | `READY · AWAITING COMMAND` neutral | لا evidence | **مغلق بعد الإصلاح؛ preserve** |
| Empty input | inline validation، لا history ولا score ولا toast نجاح | لا أثر | **مغلق بعد الإصلاح؛ preserve** |
| Ready | session ready مع history ممكنة | لا أثر جديد | **صحيح** |
| Success | response حقيقي داخل local simulation | يدخل history وقد يؤثر في Assessment | **صحيح بعد guard** |
| Syntax/sequence/decision error | error response وCoach corrective move | يسجل failure محلياً | **صحيح** |
| Assessment active | hints suppressed، entry contract واضح | scoring حسب العقد المعلن | **جزئي؛ F-002** |
| Assessment complete | real computed record إلى localStorage | Growth/Tracking reflect | **صحيح؛ لا تغيّر pipeline** |
| No evidence | StateNotice + CTA إلى practice | لا metric شخصي | **صحيح** |
| Illustrative/sample | provenance واضح، لا يتنكر كـ learner evidence | لا يدخل score بصمت | **جزئي؛ F-001/F-005** |
| Customer Service unavailable | لا Technical content تحت Service | لا evidence | **مطلوب؛ F-004** |
| Processing/interrupted | لا تعرضه دون trigger async حقيقي | لا أثر | **غير موجود؛ لا تخترعه** |

هذا العقد يربط learning quality بصدق الحالة: لا يكفي أن تبدو الشاشة صحيحة؛ يجب أن يعرف المتدرب ماذا حدث، وما الذي قيس، وما الذي لم يُقَس.

---

## 9. بوابة التحقق النهائية

قبل إعلان أي P0/P1 مغلق، يجب تنفيذ الاختبارات التالية. هذه ليست اقتراحات تجميلية؛ هي شروط إغلاق.

| طبقة التحقق | المسار |
|---|---|
| Build | TypeScript check وproduction build بعد كل مجموعة patches؛ لا تعتبر host warnings compile failure، لكن وثّقها. |
| Core practice | fresh load، empty/whitespace submit، AN → SS → FQD → FXP، invalid command، Arrow Up/Down، Reference من الطرفين، Focus Mode، Assessment finish/retry. |
| Evidence integrity | راجع arrays/rows والـ headline numbers، امسح localStorage، أنشئ record جديداً، ثم تحقق من Growth وTracking. |
| Scope | Technical → Customer Service → Technical؛ لا Technical milestones تحت Service؛ افتح SC-026 وتحقق من context. |
| Accessibility | keyboard-only، skip link، current page، tabs/toggles، progressbar، focus return/Escape، ثم NVDA/VoiceOver/TalkBack. |
| Responsive | 320/360/390/430/739/768/834/1024/1280/1440؛ لا horizontal overflow، لا clipped Execute، ولا overlay collision. |
| Native keyboard | iOS Safari وAndroid Chrome؛ history visible أو page scrolls correctly؛ input/Execute reachable. |
| Visual regression | compare Flight Deck identity، Terminal dominance، five-item rail، Growth/Tracking separation، chart/table، reduced-motion. |
| Deployment | computed font families، fonts/assets reachable، analytics warning documented، no raw stack trace، toast visibly rendered. |

### Stop condition

تتوقف دورة التدقيق العامة بعد تحقق P0/P1 وقبول حدود `NEEDS VALIDATION`. لا يُفتح تدقيق جديد إلا إذا ظهر دليل جديد يغيّر قرار P0، أو تغير scope المنتج، أو فشل implementation يكشف أن قراراً سابقاً غير صحيح، أو بقي contradiction لا يحسمه المصدر الحالي.

---

## 10. حلقة المراجعة الذاتية الداخلية

تمت مراجعة هذا التقرير داخلياً عبر المرور على متطلبات التغطية: UX، التعلم، motivation، feedback، progress، Terminal، fullscreen، mobile، typography، visual identity، accessibility، responsive، functional connectivity، وregression risk. ثم اختُبرت الاستنتاجات ضد احتمال أن تكون مجرد تفضيلات بصرية أو تكرار تاريخي؛ لذلك أُغلقت findings التي عالجتها النسخة المنقحة، ووسمت runtime gaps بـ `NEEDS VALIDATION`، وأُبقي Customer Service ضمن النطاق بعد التحقق من المصدر المباشر.

في جولة contradiction hunt، ظهر أن أقوى التعارضات لا تتعلق بجودة الهوية، بل بالفرق بين clean archive والنسخة المنقحة. لذلك لم تُنقل نتائج fonts/zoom/blank-submit/Coach-first-use كما هي من التاريخ، بل صُنّفت closed أو runtime validation. وفي جولة learning-product challenge، تبين أن الإصلاحات ذات القيمة الأعلى ليست حذف زخارف أو إعادة توزيع cards، بل جعل evidence provenance وAssessment boundary وnext action صادقة وقابلة للفهم. وفي جولة minimality، كان أصغر حل Customer Service هو unavailable state، وأصغر حل Assessment هو disclosure، وأصغر حل الأرقام هو derivation/qualifier، لا بناء أنظمة جديدة.

أما الجولة الأخيرة فاختبرت الفرضية الأقوى: هل يحتاج المنتج إلى redesign؟ الدليل لا يثبت ذلك. بالعكس، إعادة البناء قد تكسر context handoffs وlocal persistence وTerminal learning loop، في حين أن العيوب المفتوحة يمكن إصلاحها في markup/state/copy/CSS محدود. لذلك بقي الحكم النهائي **Preserve and Harden**.

---

## 11. الحكم النهائي القابل للتنفيذ

> **AeroBridge صالح ليكون أساساً لمنتج تدريب متماسك، لكنه ليس جاهزاً بعد بوصفه مرجعاً موثوقاً للإصدار التالي ما لم تُغلق F-001 وF-002، ويُصحّح عرض Customer Service، وتُزال لغة readiness غير المدعومة، وتُنفّذ إصلاحات الوصول والتفاعل ذات الأثر العالي.**

النتيجة ليست “غيّر كل شيء”، وليست “كل ما سبق في التدقيقات صحيح”. النتيجة الأدق هي: **حافظ على النظام الموجود والصحيح، ثبّت الإصلاحات المنقحة، أصلح ما بقي من trust/accessibility/scope بأقل blast radius، وامتنع عن اختراع curriculum أو metrics أو engine semantics لا يثبتها المصدر.**

---

## المراجع

[1]: file:///home/ubuntu/projects/aerobridge-ded2c12d/work/meta_audit/revised_final/aerobridge-share-preview/ideas.md "AeroBridge ideas.md — design ground truth and product boundary"

[2]: file:///home/ubuntu/projects/aerobridge-ded2c12d/work/meta_audit/evidence_dossier.md "AeroBridge Evidence Dossier"

[3]: file:///home/ubuntu/projects/aerobridge-ded2c12d/work/meta_audit/visual_findings.md "AeroBridge verified visual findings from 42 screenshot tiles"

[4]: file:///home/ubuntu/projects/aerobridge-ded2c12d/work/meta_audit/claim_ledger.md "AeroBridge claim-by-claim adjudication ledger"

[5]: file:///home/ubuntu/projects/aerobridge-ded2c12d/Phase_3_Live_Findings.md "AeroBridge Phase 3 Live Findings"

[6]: file:///home/ubuntu/upload/AEROBRIDGE_STAGE4_MASTER_CONSENSUS_AUDIT.md "AeroBridge Stage 4 Master Consensus Audit — historical analytical material"

[7]: file:///home/ubuntu/projects/aerobridge-ded2c12d/work/meta_audit/revised_final/aerobridge-share-preview/client/src/pages/Home.tsx "AeroBridge revised Home.tsx — current implementation source"

[8]: file:///home/ubuntu/projects/aerobridge-ded2c12d/work/meta_audit/revised_final/aerobridge-share-preview/client/index.html "AeroBridge revised index.html — current document shell"

[9]: file:///home/ubuntu/projects/aerobridge-ded2c12d/PHASE_2_SOURCE_MAPPING.md "AeroBridge Phase 2 source mapping and product-surface inventory"
