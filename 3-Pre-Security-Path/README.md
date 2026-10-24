<div dir="rtl" align="right">

# 🎓 مسار Pre-Security: فهرس الوحدات

## 📑 جدول المحتويات

<table dir="rtl" width="100%">
<tr><th align="center" style="text-align:center">#</th><th align="right" style="text-align:right">الوحدة</th><th align="right" style="text-align:right">نبذة</th></tr>
<tr><td align="center">—</td><td align="right"><a href="#module-intro">مقدمة الفهرس</a></td><td align="right">إيه هو الملف ده وإزاي تستخدمه</td></tr>
<tr><td align="center" style="text-align:center">1</td><td dir="ltr" align="left" style="text-align:left"><a href="#module-1">Introduction to Cyber Security</a></td><td align="right" style="text-align:right">مدخل إلى الأمن السيبراني: الأمن الهجومي والأمن الدفاعي، والوظائف المتاحة في المجال، وأول أدوات اكتشاف المحتوى.</td></tr>
<tr><td align="center" style="text-align:center">2</td><td dir="ltr" align="left" style="text-align:left"><a href="#module-2">Computer Fundamentals</a></td><td align="right" style="text-align:right">أساسيات الحاسوب: مكوناته الداخلية، وأنواع الأجهزة، ونموذج العميل والخادم، والمحاكاة الافتراضية (Virtualisation)، والحوسبة السحابية.</td></tr>
<tr><td align="center" style="text-align:center">3</td><td dir="ltr" align="left" style="text-align:left"><a href="#module-3">Operating Systems Basics</a></td><td align="right" style="text-align:right">أنظمة التشغيل: المفاهيم العامة، وأساسيات Windows، وسطر الأوامر في Linux وWindows، وتأمين نظام التشغيل.</td></tr>
<tr><td align="center" style="text-align:center">4</td><td dir="ltr" align="left" style="text-align:left"><a href="#module-4">Software Basics</a></td><td align="right" style="text-align:right">أساسيات البرمجيات: تمثيل البيانات والترميز، ومدخل إلى Python وJavaScript وقواعد البيانات وSQL.</td></tr>
<tr><td align="center" style="text-align:center">5</td><td dir="ltr" align="left" style="text-align:left"><a href="#module-5">Network Fundamentals</a></td><td align="right" style="text-align:right">أساسيات الشبكات: فهرس مرتب لمواضيع كورس Network+ الشامل، من تعريف الشبكة ونموذج OSI وTCP/IP حتى التوجيه والأمن واستكشاف الأعطال.</td></tr>
<tr><td align="center" style="text-align:center">6</td><td dir="ltr" align="left" style="text-align:left"><a href="#module-6">How The Web Works</a></td><td align="right" style="text-align:right">كيف يعمل الويب: نظام DNS، وبروتوكول HTTP، وبنية المواقع، ورحلة الطلب كاملة من المتصفح إلى الخادم.</td></tr>
<tr><td align="center" style="text-align:center">7</td><td dir="ltr" align="left" style="text-align:left"><a href="#module-7">Attacks and Defenses</a></td><td align="right" style="text-align:right">الهجوم والدفاع: ثلاثية CIA، ومفاهيم التشفير، وعقلية المهاجم ودورة الهجوم، وتحديات CTF، وأسس عمل المدافع وفريق SOC.</td></tr>
</table>

<a id="module-intro"></a>

## 🧭 مقدمة الفهرس

الملف ده هو **الفهرس الرئيسي** لمسار **Pre-Security** الموجود في فولدر [`3-Pre-Security-Path`](./)، وهدفه إنه يجمعلك جدول المحتويات بتاع كل وحدة من الوحدات السبع في مكان واحد.

### 🎯 المسار ده مقدمة للمسارات اللي بعده

المسار ده **مقدمة** للمسارات الأعمق اللي هكملها بعده في رحلتي في مجال **أمن المعلومات (Cybersecurity)**، وهدفه إنه يحط **الأساس** اللي أي حد داخل المجال لازم يكون واقف عليه قبل ما يتخصص. وبيغطي سبع وحدات:

- **مدخل للأمن السيبراني:** يعني إيه أمن هجومي وأمن دفاعي، والوظائف المتاحة في المجال.
- **أساسيات الحاسوب:** مكونات الجهاز، والـ Client/Server، والـ Virtualization والـ Cloud.
- **أنظمة التشغيل:** Windows وLinux وسطر الأوامر فيهم، وإزاي نأمّن النظام.
- **أساسيات البرمجيات:** تمثيل البيانات والترميز، ومدخل لـ Python وJavaScript وSQL.
- **أساسيات الشبكات:** الـ OSI وTCP/IP والـ IP والتوجيه والأمن، وده ملخص كورس Network+.
- **كيف يعمل الويب:** الـ DNS والـ HTTP وبنية المواقع ورحلة الطلب كاملة.
- **الهجوم والدفاع:** ثلاثية CIA والتشفير وعقلية المهاجم وأسس عمل المدافع (SOC).

### 💡 ليه الحاجات دي مهمة في أمن المعلومات؟

المحلل الأمني **مش هيقدر يحمي حاجة هو مش فاهم إزاي بتشتغل**. فمثلًا: مفيش تحليل لتنبيه شبكة من غير فهم الـ IP والـ DNS والـ Ports، ولا تحقيق في حادثة على جهاز من غير معرفة بنظام التشغيل والـ Logs وسطر الأوامر، ولا فهم لثغرة في موقع من غير معرفة بالـ HTTP وقواعد البيانات والكود. ولذلك كل وحدة هنا بتنتهي بـ **زاوية أمنية** وخلاصة للمحلل الأمني (SOC Takeaways) بتربط المعلومة بالشغل الفعلي.

### ⏱ ملحوظة عن المسار ده

المسار ده **مخدش مني وقت كبير**، لأنه في الأصل **مقدمات** بسيطة وأغلبها كنت عارفها: جزء منها درسته في **الجامعة**، وجزء في **كورس CompTIA (Network+ وغيره)**. فالغرض من توثيقه هنا هو **المراجعة وترتيب الأساس** وتوحيد المصطلحات قبل الدخول في الحاجات الأعمق. وبعد كده هندرس كل حاجة من دول **بالتفصيل الأكبر** في المسارات الجاية.

### 🧭 إزاي تستخدم الملف

تحت كل عنوان وحدة هتلاقي **الجدول الأصلي بتاعها زي ما هو موجود جوه ملفها**، وكل رابط في الجدول بيوديك **على طول للنقطة المطلوبة** جوه الملف من غير ما تفتحه وتدور فيه. والشرح في الملفات بالعربي مع المصطلحات بالإنجليزي، وفي آخر كل غرفة خلاصة عملية للمحلل الأمني (SOC Takeaways).

<br>

<a id="module-1"></a>

<table width="100%">
<tr><td align="center">

## 🛡 [الوحدة الأولى: Introduction to Cyber Security](./1-Introduction-to-Cyber-Security.md)

مدخل إلى الأمن السيبراني: الأمن الهجومي والأمن الدفاعي، والوظائف المتاحة في المجال، وأول أدوات اكتشاف المحتوى.

</td></tr>
</table>

<p align="center"><sub>📚 جدول محتويات الوحدة</sub></p>

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">#</th><th align="right" style="text-align:right">الغرفة</th><th align="right" style="text-align:right">الموضوعات بالترتيب</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./1-Introduction-to-Cyber-Security.md#module-intro">مقدمة الوحدة</a></td><td align="right" style="text-align:right">تعريف الأمن السيبراني، وما ستتناوله الوحدة</td></tr>
<tr><td align="right" style="text-align:right">1</td><td dir="ltr" align="left" style="text-align:left"><a href="./1-Introduction-to-Cyber-Security.md#room-1">Offensive Security Intro</a></td><td align="right" style="text-align:right"><a href="./1-Introduction-to-Cyber-Security.md#t1-1">1.1 التعريف بالأمن الهجومي وهدف الغرفة</a><br><a href="./1-Introduction-to-Cyber-Security.md#t1-2">1.2 المفاهيم الأساسية</a><br><a href="./1-Introduction-to-Cyber-Security.md#t1-3">1.3 أكواد الاستجابة (HTTP Status Codes)</a><br><a href="./1-Introduction-to-Cyber-Security.md#t1-4">1.4 دورة اكتشاف المحتوى: من القائمة إلى النتائج</a><br><a href="./1-Introduction-to-Cyber-Security.md#t1-5">1.5 تجهيز البيئة</a><br><a href="./1-Introduction-to-Cyber-Security.md#t1-6">1.6 البحث عن الصفحات المخفية بأمر dirb</a><br><a href="./1-Introduction-to-Cyber-Security.md#t1-7">1.7 قراءة مخرجات dirb</a><br><a href="./1-Introduction-to-Cyber-Security.md#t1-8">1.8 الزاوية الأمنية: كيف يبدو البحث عن الصفحات المخفية في سجلات الخادم</a><br><a href="./1-Introduction-to-Cyber-Security.md#t1-9">1.9 سيناريو: من الاستكشاف إلى اكتشاف الثغرة</a></td></tr>
<tr><td align="right" style="text-align:right">2</td><td dir="ltr" align="left" style="text-align:left"><a href="./1-Introduction-to-Cyber-Security.md#room-2">Defensive Security Intro</a></td><td align="right" style="text-align:right"><a href="./1-Introduction-to-Cyber-Security.md#t2-1">2.1 التعريف بالأمن الدفاعي وأهميته</a><br><a href="./1-Introduction-to-Cyber-Security.md#t2-2">2.2 المفاهيم الأساسية</a><br><a href="./1-Introduction-to-Cyber-Security.md#t2-3">2.3 مقارنة بين الأمن الهجومي والدفاعي</a><br><a href="./1-Introduction-to-Cyber-Security.md#t2-4">2.4 تسلسل عمل المحلل الأمني</a><br><a href="./1-Introduction-to-Cyber-Security.md#t2-5">2.5 فتح لوحة المراقبة وكشف النشاط المشبوه</a><br><a href="./1-Introduction-to-Cyber-Security.md#t2-6">2.6 تحليل الهجوم (Investigation)</a><br><a href="./1-Introduction-to-Cyber-Security.md#t2-7">2.7 الاستجابة (Response) بحظر المصدر</a><br><a href="./1-Introduction-to-Cyber-Security.md#t2-8">2.8 الزاوية الأمنية: جودة التنبيه ومخاطر الحظر</a><br><a href="./1-Introduction-to-Cyber-Security.md#t2-9">2.9 سيناريو: محلل SOC يتعامل مع حدث حقيقي</a></td></tr>
<tr><td align="right" style="text-align:right">3</td><td dir="ltr" align="left" style="text-align:left"><a href="./1-Introduction-to-Cyber-Security.md#room-3">Careers in Cyber</a></td><td align="right" style="text-align:right"><a href="./1-Introduction-to-Cyber-Security.md#t3-1">3.1 التعريف بالمجال والغرفة</a><br><a href="./1-Introduction-to-Cyber-Security.md#t3-2">3.2 المفاهيم الأساسية</a><br><a href="./1-Introduction-to-Cyber-Security.md#t3-3">3.3 أشهر الوظائف</a><br><a href="./1-Introduction-to-Cyber-Security.md#t3-4">3.4 خريطة الأدوار وكيف تتكامل</a><br><a href="./1-Introduction-to-Cyber-Security.md#t3-5">3.5 اختيار المجال</a><br><a href="./1-Introduction-to-Cyber-Security.md#t3-6">3.6 الزاوية الأمنية: الأخلاقيات والإذن ومستويات عمل المحلل</a><br><a href="./1-Introduction-to-Cyber-Security.md#t3-7">3.7 سيناريو: مؤسسة واحدة وأدوار مختلفة</a></td></tr>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./1-Introduction-to-Cyber-Security.md#module-commands">جدول الأوامر المستخدمة</a></td><td align="right" style="text-align:right">ملخص الأوامر المستخدمة في الوحدة ووظيفة كل منها</td></tr>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./1-Introduction-to-Cyber-Security.md#module-glossary">جدول المصطلحات</a></td><td align="right" style="text-align:right">أهم مصطلحات الوحدة بمعانيها وأرقام الغرف</td></tr>
</tbody>
</table>

<br>

<a id="module-2"></a>

<table width="100%">
<tr><td align="center">

## 💻 [الوحدة الثانية: Computer Fundamentals](./2-Computer-Fundamentals.md)

أساسيات الحاسوب: مكوناته الداخلية، وأنواع الأجهزة، ونموذج العميل والخادم، والمحاكاة الافتراضية (Virtualisation)، والحوسبة السحابية.

</td></tr>
</table>

<p align="center"><sub>📚 جدول محتويات الوحدة</sub></p>

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">#</th><th align="right" style="text-align:right">الغرفة</th><th align="right" style="text-align:right">الموضوعات بالترتيب</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./2-Computer-Fundamentals.md#module-intro">مقدمة الوحدة</a></td><td align="right" style="text-align:right">تعريف الحوسبة وما ستتناوله الوحدة</td></tr>
<tr><td align="right" style="text-align:right">1</td><td dir="ltr" align="left" style="text-align:left"><a href="./2-Computer-Fundamentals.md#room-1">Inside a Computer System</a></td><td align="right" style="text-align:right"><a href="./2-Computer-Fundamentals.md#t1-1">1.1 التعريف بالغرفة وأهميتها</a><br><a href="./2-Computer-Fundamentals.md#t1-2">1.2 ما هو الكمبيوتر وكيف تترابط مكوناته</a><br><a href="./2-Computer-Fundamentals.md#t1-3">1.3 المكونات الأساسية في نظرة واحدة</a><br><a href="./2-Computer-Fundamentals.md#t1-4">1.4 اللوحة الأم (Motherboard)</a><br><a href="./2-Computer-Fundamentals.md#t1-5">1.5 المعالج (CPU)</a><br><a href="./2-Computer-Fundamentals.md#t1-6">1.6 الذاكرة العشوائية (RAM)</a><br><a href="./2-Computer-Fundamentals.md#t1-7">1.7 وحدات التخزين (HDD و SSD)</a><br><a href="./2-Computer-Fundamentals.md#t1-8">1.8 كرت الشاشة (GPU) ومزود الطاقة (PSU)</a><br><a href="./2-Computer-Fundamentals.md#t1-9">1.9 كرت الشبكة (NIC)</a><br><a href="./2-Computer-Fundamentals.md#t1-10">1.10 الأجهزة الطرفية (Peripherals)</a><br><a href="./2-Computer-Fundamentals.md#t1-11">1.11 الزاوية الأمنية: أمن مكونات الجهاز</a><br><a href="./2-Computer-Fundamentals.md#t1-12">1.12 تدريب: تركيب القطع على اللوحة الأم</a><br><a href="./2-Computer-Fundamentals.md#t1-13">1.13 ماذا يحدث عند الضغط على زر الباور؟</a><br><a href="./2-Computer-Fundamentals.md#t1-14">1.14 تدريب: تتبّع عملية الإقلاع</a><br><a href="./2-Computer-Fundamentals.md#t1-15">1.15 سيناريو: رحلة معلومة داخل الجهاز</a></td></tr>
<tr><td align="right" style="text-align:right">2</td><td dir="ltr" align="left" style="text-align:left"><a href="./2-Computer-Fundamentals.md#room-2">Computer Types</a></td><td align="right" style="text-align:right"><a href="./2-Computer-Fundamentals.md#t2-1">2.1 التعريف بالغرفة وأهميتها</a><br><a href="./2-Computer-Fundamentals.md#t2-2">2.2 معايير التصنيف</a><br><a href="./2-Computer-Fundamentals.md#t2-3">2.3 أنواع الأجهزة الرئيسية (Types of Computers)</a><br><a href="./2-Computer-Fundamentals.md#t2-4">2.4 الأجهزة المدمجة والمحمولة (Embedded & Mobile Devices)</a><br><a href="./2-Computer-Fundamentals.md#t2-5">2.5 المقارنة بين الأنواع</a><br><a href="./2-Computer-Fundamentals.md#t2-6">2.6 الزاوية الأمنية: لكل نوع جهاز تهديداته</a><br><a href="./2-Computer-Fundamentals.md#t2-7">2.7 سيناريو: أجهزة مؤسسة واحدة</a></td></tr>
<tr><td align="right" style="text-align:right">3</td><td dir="ltr" align="left" style="text-align:left"><a href="./2-Computer-Fundamentals.md#room-3">Client-Server Basics</a></td><td align="right" style="text-align:right"><a href="./2-Computer-Fundamentals.md#t3-1">3.1 التعريف بالغرفة وأهميتها</a><br><a href="./2-Computer-Fundamentals.md#t3-2">3.2 العميل والخادم</a><br><a href="./2-Computer-Fundamentals.md#t3-3">3.3 أنواع الخوادم</a><br><a href="./2-Computer-Fundamentals.md#t3-4">3.4 دورة الطلب والاستجابة</a><br><a href="./2-Computer-Fundamentals.md#t3-5">3.5 الزاوية الأمنية: أين يُهاجَم نموذج العميل والخادم؟</a><br><a href="./2-Computer-Fundamentals.md#t3-6">3.6 سيناريو: زيارة موقع بنك</a></td></tr>
<tr><td align="right" style="text-align:right">4</td><td dir="ltr" align="left" style="text-align:left"><a href="./2-Computer-Fundamentals.md#room-4">Virtualisation Basics</a></td><td align="right" style="text-align:right"><a href="./2-Computer-Fundamentals.md#t4-1">4.1 التعريف بالغرفة وأهميتها</a><br><a href="./2-Computer-Fundamentals.md#t4-2">4.2 المفاهيم الأساسية</a><br><a href="./2-Computer-Fundamentals.md#t4-3">4.3 أنواع الـ Hypervisor</a><br><a href="./2-Computer-Fundamentals.md#t4-4">4.4 مكونات الآلة الافتراضية (Virtual Machine)</a><br><a href="./2-Computer-Fundamentals.md#t4-5">4.5 الفوائد والاستخدامات في الأمن السيبراني</a><br><a href="./2-Computer-Fundamentals.md#t4-6">4.6 الجهاز الافتراضي مقابل الحاوية</a><br><a href="./2-Computer-Fundamentals.md#t4-7">4.7 الزاوية الأمنية: الافتراضية سلاح ذو حدين</a><br><a href="./2-Computer-Fundamentals.md#t4-8">4.8 سيناريو: مختبر أمني آمن</a></td></tr>
<tr><td align="right" style="text-align:right">5</td><td dir="ltr" align="left" style="text-align:left"><a href="./2-Computer-Fundamentals.md#room-5">Cloud Computing Fundamentals</a></td><td align="right" style="text-align:right"><a href="./2-Computer-Fundamentals.md#t5-1">5.1 التعريف بالغرفة وأهميتها</a><br><a href="./2-Computer-Fundamentals.md#t5-2">5.2 خصائص الحوسبة السحابية</a><br><a href="./2-Computer-Fundamentals.md#t5-3">5.3 نماذج الخدمة</a><br><a href="./2-Computer-Fundamentals.md#t5-4">5.4 نماذج النشر</a><br><a href="./2-Computer-Fundamentals.md#t5-5">5.5 مسؤولية الأمن المشتركة (Shared Responsibility)</a><br><a href="./2-Computer-Fundamentals.md#t5-6">5.6 الزاوية الأمنية: أين تقع الأخطاء في السحابة؟</a><br><a href="./2-Computer-Fundamentals.md#t5-7">5.7 سيناريو: نقل موقع شركة إلى السحابة</a></td></tr>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./2-Computer-Fundamentals.md#module-glossary">جدول المصطلحات</a></td><td align="right" style="text-align:right">أهم مصطلحات الوحدة بمعانيها وأرقام الغرف</td></tr>
</tbody>
</table>

<br>

<a id="module-3"></a>

<table width="100%">
<tr><td align="center">

## 🖥 [الوحدة الثالثة: Operating Systems Basics](./3-Operating-Systems-Basics.md)

أنظمة التشغيل: المفاهيم العامة، وأساسيات Windows، وسطر الأوامر في Linux وWindows، وتأمين نظام التشغيل.

</td></tr>
</table>

<p align="center"><sub>📚 جدول محتويات الوحدة</sub></p>

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">#</th><th align="right" style="text-align:right">الغرفة</th><th align="right" style="text-align:right">الموضوعات بالترتيب</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./3-Operating-Systems-Basics.md#module-intro">مقدمة الوحدة</a></td><td align="right" style="text-align:right">تعريف نظام التشغيل ولماذا تُعد الوحدة محورية للمحلل الأمني</td></tr>
<tr><td align="right" style="text-align:right">1</td><td dir="ltr" align="left" style="text-align:left"><a href="./3-Operating-Systems-Basics.md#room-1">Operating Systems Introduction</a></td><td align="right" style="text-align:right"><a href="./3-Operating-Systems-Basics.md#t1-1">1.1 التعريف بالغرفة وهدفها</a><br><a href="./3-Operating-Systems-Basics.md#t1-2">1.2 ما هو نظام التشغيل وأين يقع</a><br><a href="./3-Operating-Systems-Basics.md#t1-3">1.3 واجبات نظام التشغيل</a><br><a href="./3-Operating-Systems-Basics.md#t1-4">1.4 أنواع أنظمة التشغيل واستخداماتها</a><br><a href="./3-Operating-Systems-Basics.md#t1-5">1.5 عائلات أنظمة التشغيل الرئيسية</a><br><a href="./3-Operating-Systems-Basics.md#t1-6">1.6 لماذا توجد أنظمة تشغيل كثيرة</a><br><a href="./3-Operating-Systems-Basics.md#t1-7">1.7 أدوات نظام التشغيل</a><br><a href="./3-Operating-Systems-Basics.md#t1-8">1.8 كيف نتفاعل مع نظام التشغيل: GUI و CLI</a><br><a href="./3-Operating-Systems-Basics.md#t1-9">1.9 النواة ومساحتا النواة والمستخدم</a><br><a href="./3-Operating-Systems-Basics.md#t1-10">1.10 مكالمات النظام (System Calls)</a><br><a href="./3-Operating-Systems-Basics.md#t1-11">1.11 أمن نظام التشغيل</a><br><a href="./3-Operating-Systems-Basics.md#t1-12">1.12 سيناريو: ماذا يحدث عند فتح ملف مستند</a></td></tr>
<tr><td align="right" style="text-align:right">2</td><td dir="ltr" align="left" style="text-align:left"><a href="./3-Operating-Systems-Basics.md#room-2">Windows Basics</a></td><td align="right" style="text-align:right"><a href="./3-Operating-Systems-Basics.md#t2-1">2.1 التعريف بالغرفة وأهدافها</a><br><a href="./3-Operating-Systems-Basics.md#t2-2">2.2 نبذة تاريخية عن ويندوز</a><br><a href="./3-Operating-Systems-Basics.md#t2-3">2.3 تسجيل الدخول والمصادقة</a><br><a href="./3-Operating-Systems-Basics.md#t2-4">2.4 أنواع الحسابات في ويندوز</a><br><a href="./3-Operating-Systems-Basics.md#t2-5">2.5 سطح المكتب وشريط المهام وقائمة ابدأ</a><br><a href="./3-Operating-Systems-Basics.md#t2-6">2.6 الأدوات والتطبيقات المدمجة</a><br><a href="./3-Operating-Systems-Basics.md#t2-7">2.7 معلومات النظام وصفحة حول الكمبيوتر</a><br><a href="./3-Operating-Systems-Basics.md#t2-8">2.8 استكشاف الملفات وإدارتها</a><br><a href="./3-Operating-Systems-Basics.md#t2-9">2.9 الإعدادات ولوحة التحكم</a><br><a href="./3-Operating-Systems-Basics.md#t2-10">2.10 تحديث ويندوز وإدارة التطبيقات</a><br><a href="./3-Operating-Systems-Basics.md#t2-11">2.11 مدير المهام (Task Manager)</a><br><a href="./3-Operating-Systems-Basics.md#t2-12">2.12 أمان ويندوز (Windows Security)</a><br><a href="./3-Operating-Systems-Basics.md#t2-13">2.13 الزاوية الأمنية: ما الذي يهم المحلل في ويندوز</a><br><a href="./3-Operating-Systems-Basics.md#t2-14">2.14 التطبيق العملي: يوم موظف جديد</a><br><a href="./3-Operating-Systems-Basics.md#t2-15">2.15 سيناريو: فحص محطة عمل مشبوهة</a></td></tr>
<tr><td align="right" style="text-align:right">3</td><td dir="ltr" align="left" style="text-align:left"><a href="./3-Operating-Systems-Basics.md#room-3">Linux CLI Basics</a></td><td align="right" style="text-align:right"><a href="./3-Operating-Systems-Basics.md#t3-1">3.1 التعريف بالغرفة وأهميتها</a><br><a href="./3-Operating-Systems-Basics.md#t3-2">3.2 الـ Shell والـ Terminal والـ CLI</a><br><a href="./3-Operating-Systems-Basics.md#t3-3">3.3 هيكل نظام الملفات</a><br><a href="./3-Operating-Systems-Basics.md#t3-4">3.4 الأذونات (Permissions)</a><br><a href="./3-Operating-Systems-Basics.md#t3-5">3.5 التنقل: pwd و cd و ls</a><br><a href="./3-Operating-Systems-Basics.md#t3-6">3.6 قراءة الملفات: cat و less و head و tail</a><br><a href="./3-Operating-Systems-Basics.md#t3-7">3.7 إنشاء وإدارة الملفات والمجلدات: mkdir و touch و cp و mv و rm</a><br><a href="./3-Operating-Systems-Basics.md#t3-8">3.8 تغيير الأذونات والمالك: chmod و chown</a><br><a href="./3-Operating-Systems-Basics.md#t3-9">3.9 الصلاحيات العالية: sudo</a><br><a href="./3-Operating-Systems-Basics.md#t3-10">3.10 البحث: find و grep</a><br><a href="./3-Operating-Systems-Basics.md#t3-11">3.11 إدارة العمليات: ps و top و kill</a><br><a href="./3-Operating-Systems-Basics.md#t3-12">3.12 استكشاف الشبكة: ip و ifconfig و netstat</a><br><a href="./3-Operating-Systems-Basics.md#t3-13">3.13 الزاوية الأمنية: لينكس في عين المحلل</a><br><a href="./3-Operating-Systems-Basics.md#t3-14">3.14 سيناريو: خادم لينكس يتعرض لتخمين كلمات المرور</a></td></tr>
<tr><td align="right" style="text-align:right">4</td><td dir="ltr" align="left" style="text-align:left"><a href="./3-Operating-Systems-Basics.md#room-4">Windows CLI Basics</a></td><td align="right" style="text-align:right"><a href="./3-Operating-Systems-Basics.md#t4-1">4.1 التعريف بالغرفة وأهميتها</a><br><a href="./3-Operating-Systems-Basics.md#t4-2">4.2 الفرق بين CMD و PowerShell</a><br><a href="./3-Operating-Systems-Basics.md#t4-3">4.3 أوامر CMD: التنقل واستكشاف الملفات</a><br><a href="./3-Operating-Systems-Basics.md#t4-4">4.4 أوامر CMD: إدارة الملفات والمجلدات</a><br><a href="./3-Operating-Systems-Basics.md#t4-5">4.5 أوامر CMD: الشبكة</a><br><a href="./3-Operating-Systems-Basics.md#t4-6">4.6 أوامر CMD: الحسابات والمجموعات والمشاركات</a><br><a href="./3-Operating-Systems-Basics.md#t4-7">4.7 PowerShell: الأساسيات والعمليات والخدمات</a><br><a href="./3-Operating-Systems-Basics.md#t4-8">4.8 PowerShell: البحث عن الملفات والنصوص</a><br><a href="./3-Operating-Systems-Basics.md#t4-9">4.9 PowerShell: سجلات الأحداث</a><br><a href="./3-Operating-Systems-Basics.md#t4-10">4.10 أهم أرقام الأحداث (Event IDs) في ويندوز</a><br><a href="./3-Operating-Systems-Basics.md#t4-11">4.11 الزاوية الأمنية: كشف النشاط المشبوه بأوامر ويندوز</a><br><a href="./3-Operating-Systems-Basics.md#t4-12">4.12 سيناريو: حساب جديد وتخمين سابق</a></td></tr>
<tr><td align="right" style="text-align:right">5</td><td dir="ltr" align="left" style="text-align:left"><a href="./3-Operating-Systems-Basics.md#room-5">Operating System Security</a></td><td align="right" style="text-align:right"><a href="./3-Operating-Systems-Basics.md#t5-1">5.1 التعريف بالغرفة وأهميتها</a><br><a href="./3-Operating-Systems-Basics.md#t5-2">5.2 تقليل سطح الهجوم</a><br><a href="./3-Operating-Systems-Basics.md#t5-3">5.3 المبادئ الأساسية</a><br><a href="./3-Operating-Systems-Basics.md#t5-4">5.4 تعطيل الخدمات والبروتوكولات غير الضرورية</a><br><a href="./3-Operating-Systems-Basics.md#t5-5">5.5 إدارة المصادقة (Authentication)</a><br><a href="./3-Operating-Systems-Basics.md#t5-6">5.6 إدارة الصلاحيات والوصول (Access Control و RBAC)</a><br><a href="./3-Operating-Systems-Basics.md#t5-7">5.7 إدارة التحديثات والترقيعات (Patch Management)</a><br><a href="./3-Operating-Systems-Basics.md#t5-8">5.8 جدار الحماية المحلي (Host-Based Firewall)</a><br><a href="./3-Operating-Systems-Basics.md#t5-9">5.9 حماية النقاط النهائية (Endpoint Protection)</a><br><a href="./3-Operating-Systems-Basics.md#t5-10">5.10 التسجيل والتدقيق (Logging و Auditing)</a><br><a href="./3-Operating-Systems-Basics.md#t5-11">5.11 تشفير القرص (Full Disk Encryption)</a><br><a href="./3-Operating-Systems-Basics.md#t5-12">5.12 قائمة تحصين مختصرة</a><br><a href="./3-Operating-Systems-Basics.md#t5-13">5.13 الزاوية الأمنية: كيف نتحقق أن النظام مُحصَّن</a><br><a href="./3-Operating-Systems-Basics.md#t5-14">5.14 سيناريو: تحصين خادم قبل نشره</a></td></tr>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./3-Operating-Systems-Basics.md#module-cheatsheet">جدول الأوامر (Cheatsheet)</a></td><td align="right" style="text-align:right">ملخص أوامر لينكس وويندوز: الأمر واستخدامه ومثال عملي</td></tr>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./3-Operating-Systems-Basics.md#module-glossary">جدول المصطلحات</a></td><td align="right" style="text-align:right">أهم مصطلحات الوحدة بمعانيها وأرقام الغرف</td></tr>
</tbody>
</table>

<br>

<a id="module-4"></a>

<table width="100%">
<tr><td align="center">

## 🧩 [الوحدة الرابعة: Software Basics](./4-Software-Basics.md)

أساسيات البرمجيات: تمثيل البيانات والترميز، ومدخل إلى Python وJavaScript وقواعد البيانات وSQL.

</td></tr>
</table>

<p align="center"><sub>📚 جدول محتويات الوحدة</sub></p>

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">#</th><th align="right" style="text-align:right">الغرفة</th><th align="right" style="text-align:right">الموضوعات بالترتيب</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./4-Software-Basics.md#module-intro">مقدمة الوحدة</a></td><td align="right" style="text-align:right">تعريف البرمجيات وكيف تُبنى على الأرقام والنصوص والبيانات</td></tr>
<tr><td align="right" style="text-align:right">1</td><td dir="ltr" align="left" style="text-align:left"><a href="./4-Software-Basics.md#room-1">Data Representation</a></td><td align="right" style="text-align:right"><a href="./4-Software-Basics.md#t1-1">1.1 التعريف بالغرفة وأهدافها</a><br><a href="./4-Software-Basics.md#t1-2">1.2 لماذا يعتمد الحاسوب على النظام الثنائي</a><br><a href="./4-Software-Basics.md#t1-3">1.3 البت والبايت ووحدات التخزين</a><br><a href="./4-Software-Basics.md#t1-4">1.4 الأنظمة العددية الأربعة</a><br><a href="./4-Software-Basics.md#t1-5">1.5 النظام السداسي عشري بالتفصيل</a><br><a href="./4-Software-Basics.md#t1-6">1.6 النظام الثماني Octal</a><br><a href="./4-Software-Basics.md#t1-7">1.7 التحويل بين الأنظمة العددية</a><br><a href="./4-Software-Basics.md#t1-8">1.8 تمثيل الألوان بالأرقام</a><br><a href="./4-Software-Basics.md#t1-9">1.9 تخزين القيم الرقمية في ذاكرة الكمبيوتر</a><br><a href="./4-Software-Basics.md#t1-10">1.10 الزاوية الأمنية: الأرقام والأنظمة في التحقيق</a><br><a href="./4-Software-Basics.md#t1-11">1.11 أدوات التحويل وقراءة البيانات الخام</a><br><a href="./4-Software-Basics.md#t1-12">1.12 جدول مرجعي: التحويلات والأوامر (Cheatsheet)</a><br><a href="./4-Software-Basics.md#t1-13">1.13 سيناريو: مرفق مشبوه بامتداد مزيف</a></td></tr>
<tr><td align="right" style="text-align:right">2</td><td dir="ltr" align="left" style="text-align:left"><a href="./4-Software-Basics.md#room-2">Data Encoding</a></td><td align="right" style="text-align:right"><a href="./4-Software-Basics.md#t2-1">2.1 التعريف بالغرفة وربطها بالغرفة السابقة</a><br><a href="./4-Software-Basics.md#t2-2">2.2 فكرة الترميز Encoding</a><br><a href="./4-Software-Basics.md#t2-3">2.3 ترميز ASCII</a><br><a href="./4-Software-Basics.md#t2-4">2.4 كيف نحفظ ونعرض النص</a><br><a href="./4-Software-Basics.md#t2-5">2.5 Extended ASCII وسلسلة ISO-8859</a><br><a href="./4-Software-Basics.md#t2-6">2.6 معيار Unicode ونقاط الترميز Code Points</a><br><a href="./4-Software-Basics.md#t2-7">2.7 صيغ UTF-8 و UTF-16 و UTF-32</a><br><a href="./4-Software-Basics.md#t2-8">2.8 ترميزات أخرى يراها المحلل في عمله</a><br><a href="./4-Software-Basics.md#t2-9">2.9 الزاوية الأمنية: الترميز في التحقيق والهجمات</a><br><a href="./4-Software-Basics.md#t2-10">2.10 أدوات الترميز وفكه</a><br><a href="./4-Software-Basics.md#t2-11">2.11 جدول مرجعي: الترميز والأوامر (Cheatsheet)</a><br><a href="./4-Software-Basics.md#t2-12">2.12 سيناريو: قيمة مرمّزة في طلب ويب مشبوه</a></td></tr>
<tr><td align="right" style="text-align:right">3</td><td dir="ltr" align="left" style="text-align:left"><a href="./4-Software-Basics.md#room-3">Python Simple Demo</a></td><td align="right" style="text-align:right"><a href="./4-Software-Basics.md#t3-1">3.1 التعريف بالغرفة ولغة Python</a><br><a href="./4-Software-Basics.md#t3-2">3.2 تشغيل بايثون وبنية الجملة Syntax</a><br><a href="./4-Software-Basics.md#t3-3">3.3 المتغيرات Variables</a><br><a href="./4-Software-Basics.md#t3-4">3.4 أنواع البيانات الأساسية</a><br><a href="./4-Software-Basics.md#t3-5">3.5 العمليات الحسابية والمقارنة والمنطقية</a><br><a href="./4-Software-Basics.md#t3-6">3.6 الجمل الشرطية Conditional Statements</a><br><a href="./4-Software-Basics.md#t3-7">3.7 القوائم والقواميس Lists and Dictionaries</a><br><a href="./4-Software-Basics.md#t3-8">3.8 الحلقات التكرارية Loops</a><br><a href="./4-Software-Basics.md#t3-9">3.9 الدوال Functions</a><br><a href="./4-Software-Basics.md#t3-10">3.10 المكتبات والملفات</a><br><a href="./4-Software-Basics.md#t3-11">3.11 الزاوية الأمنية: بايثون في عمل المحلل</a><br><a href="./4-Software-Basics.md#t3-12">3.12 أوامر تشغيل بايثون وأداة تحليل عملية</a><br><a href="./4-Software-Basics.md#t3-13">3.13 جدول مرجعي: أساسيات بايثون (Cheatsheet)</a><br><a href="./4-Software-Basics.md#t3-14">3.14 سيناريو: كشف تخمين كلمات المرور بسكربت وقراءة سكربت غريب</a></td></tr>
<tr><td align="right" style="text-align:right">4</td><td dir="ltr" align="left" style="text-align:left"><a href="./4-Software-Basics.md#room-4">JavaScript Simple Demo</a></td><td align="right" style="text-align:right"><a href="./4-Software-Basics.md#t4-1">4.1 التعريف بالغرفة ولغة JavaScript</a><br><a href="./4-Software-Basics.md#t4-2">4.2 أين تعمل JavaScript وكيف ندرجها في الصفحة</a><br><a href="./4-Software-Basics.md#t4-3">4.3 البيئة والطباعة console.log</a><br><a href="./4-Software-Basics.md#t4-4">4.4 المتغيرات: let و const و var</a><br><a href="./4-Software-Basics.md#t4-5">4.5 أنواع البيانات</a><br><a href="./4-Software-Basics.md#t4-6">4.6 الجمل الشرطية والحلقات</a><br><a href="./4-Software-Basics.md#t4-7">4.7 الدوال Functions</a><br><a href="./4-Software-Basics.md#t4-8">4.8 التفاعل مع عناصر الصفحة DOM</a><br><a href="./4-Software-Basics.md#t4-9">4.9 الأحداث Events</a><br><a href="./4-Software-Basics.md#t4-10">4.10 الزاوية الأمنية: XSS والمتصفح خط الدفاع الأول</a><br><a href="./4-Software-Basics.md#t4-11">4.11 قراءة جافا سكربت مشبوه</a><br><a href="./4-Software-Basics.md#t4-12">4.12 أدوات المطور وتجربة الكود</a><br><a href="./4-Software-Basics.md#t4-13">4.13 جدول مرجعي: أساسيات جافا سكربت (Cheatsheet)</a><br><a href="./4-Software-Basics.md#t4-14">4.14 سيناريو: الاشتباه بمحاولة XSS في سجلات تطبيق ويب</a></td></tr>
<tr><td align="right" style="text-align:right">5</td><td dir="ltr" align="left" style="text-align:left"><a href="./4-Software-Basics.md#room-5">Database SQL Basics</a></td><td align="right" style="text-align:right"><a href="./4-Software-Basics.md#t5-1">5.1 التعريف بالغرفة وقواعد البيانات</a><br><a href="./4-Software-Basics.md#t5-2">5.2 قاعدة البيانات ونظام إدارتها DBMS</a><br><a href="./4-Software-Basics.md#t5-3">5.3 هيكل الجداول: الجداول والصفوف والأعمدة</a><br><a href="./4-Software-Basics.md#t5-4">5.4 لغة الاستعلام الهيكلية SQL وفئات أوامرها</a><br><a href="./4-Software-Basics.md#t5-5">5.5 الاستعلام الأساسي SELECT و FROM</a><br><a href="./4-Software-Basics.md#t5-6">5.6 تصفية البيانات WHERE</a><br><a href="./4-Software-Basics.md#t5-7">5.7 الفرز وتحديد النطاق ORDER BY و LIMIT</a><br><a href="./4-Software-Basics.md#t5-8">5.8 إدارة وتعديل البيانات INSERT و UPDATE و DELETE</a><br><a href="./4-Software-Basics.md#t5-9">5.9 التجميع GROUP BY و HAVING</a><br><a href="./4-Software-Basics.md#t5-10">5.10 ربط الجداول SQL Joins</a><br><a href="./4-Software-Basics.md#t5-11">5.11 الزاوية الأمنية: SQL Injection</a><br><a href="./4-Software-Basics.md#t5-12">5.12 تجربة SQL عمليًا</a><br><a href="./4-Software-Basics.md#t5-13">5.13 جدول مرجعي: أوامر SQL (Cheatsheet)</a><br><a href="./4-Software-Basics.md#t5-14">5.14 سيناريو: تحقيق في دخول مشبوه وفي طلب يشبه SQL Injection</a></td></tr>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./4-Software-Basics.md#module-glossary">جدول المصطلحات</a></td><td align="right" style="text-align:right">أهم مصطلحات الوحدة بمعانيها وأرقام الغرف</td></tr>
</tbody>
</table>

<br>

<a id="module-5"></a>

<table width="100%">
<tr><td align="center">

## 🌐 [الوحدة الخامسة: Network Fundamentals](./5-Network-Fundamentals.md)

أساسيات الشبكات: فهرس مرتب لمواضيع كورس Network+ الشامل، من تعريف الشبكة ونموذج OSI وTCP/IP حتى التوجيه والأمن واستكشاف الأعطال.

</td></tr>
</table>

<p align="center"><sub>📚 جدول محتويات الوحدة</sub></p>

<table dir="rtl" width="100%">
<tr><th align="right" style="text-align:right">المحتويات</th></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#module-intro">مقدمة الوحدة</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-0">0. الدرس التمهيدي: ملخص أساسيات الشبكات</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-1">1. مقدمة في الشبكات</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-2">2. مصطلحات الشبكات الأساسية</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-3">3. عملي: شبكات الأجهزة الافتراضية</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-4">4. نموذج الـ OSI Model بالتفصيل</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-5">5. أرقام المنافذ والبروتوكولات</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-6">6. عملي: محاكاة نموذج OSI</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-7">7. نموذج TCP/IP ومقارنته بالـ OSI</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-8">8. الأوساط الفيزيائية وكابلات التوصيل</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-9">9. تقنيات الإيثرنت والشبكات المحلية</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-10">10. أجهزة الشبكات</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-11">11. عنوان الـ IP وتقسيم الشبكات</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-12">12. مقدمة في التوجيه</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-13">13. بروتوكولات التوجيه</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-14">14. بروتوكول الإصدار السادس (IPv6)</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-15">15. التحويل والشبكات المحلية الافتراضية</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-16">16. الشبكات اللاسلكية</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-17">17. المصادقة والتحكم بالوصول</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-18">18. تهديدات الشبكة والتخفيف منها</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-19">19. الأمن المادي والمخاطر</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-20">20. الشبكات الواسعة (WAN)</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-21">21. أدوات سطر الأوامر</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-22">22. استكشاف أعطال الشبكة وإصلاحها</a></td></tr>
<tr><td align="right" style="text-align:right"><a href="./5-Network-Fundamentals.md#topic-23">23. إدارة ومراقبة وتحسين أداء الشبكة</a></td></tr>
</table>

<br>

<a id="module-6"></a>

<table width="100%">
<tr><td align="center">

## 🕸 [الوحدة السادسة: How The Web Works](./6-How-The-Web-Works.md)

كيف يعمل الويب: نظام DNS، وبروتوكول HTTP، وبنية المواقع، ورحلة الطلب كاملة من المتصفح إلى الخادم.

</td></tr>
</table>

<p align="center"><sub>📚 جدول محتويات الوحدة</sub></p>

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">#</th><th align="right" style="text-align:right">الغرفة</th><th align="right" style="text-align:right">الموضوعات بالترتيب</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./6-How-The-Web-Works.md#module-intro">مقدمة الوحدة</a></td><td align="right" style="text-align:right">كيف يعمل الويب: DNS وHTTP وبنية المواقع ورحلة الطلب كاملة</td></tr>
<tr><td align="right" style="text-align:right">1</td><td dir="ltr" align="left" style="text-align:left"><a href="./6-How-The-Web-Works.md#room-1">DNS in Detail</a></td><td align="right" style="text-align:right"><a href="./6-How-The-Web-Works.md#t1-1">1.1 التعريف بالغرفة وأهدافها</a><br><a href="./6-How-The-Web-Works.md#t1-2">1.2 ما هو DNS ولماذا نحتاجه</a><br><a href="./6-How-The-Web-Works.md#t1-3">1.3 بنية اسم النطاق والتسلسل الهرمي</a><br><a href="./6-How-The-Web-Works.md#t1-4">1.4 نطاق المستوى الأعلى TLD</a><br><a href="./6-How-The-Web-Works.md#t1-5">1.5 نطاق المستوى الثاني وطول النطاق وقيود الإنشاء</a><br><a href="./6-How-The-Web-Works.md#t1-6">1.6 النطاق الفرعي وأمثلة لكل نوع</a><br><a href="./6-How-The-Web-Works.md#t1-7">1.7 أنواع سجلات DNS</a><br><a href="./6-How-The-Web-Works.md#t1-8">1.8 ماذا يحدث عند طلب DNS بالتفصيل</a><br><a href="./6-How-The-Web-Works.md#t1-9">1.9 كيف يتعامل المتصفح ونظام التشغيل مع طلب DNS</a><br><a href="./6-How-The-Web-Works.md#t1-10">1.10 أمن DNS: الهجمات والحماية</a><br><a href="./6-How-The-Web-Works.md#t1-11">1.11 الزاوية الأمنية: أدوات الاستطلاع والتحقيق في DNS</a><br><a href="./6-How-The-Web-Works.md#t1-12">1.12 الزاوية الأمنية: تحليل سجلات DNS واكتشاف الاتصالات الخبيثة</a><br><a href="./6-How-The-Web-Works.md#t1-13">1.13 أدوات استعلام DNS والتحقق منه</a><br><a href="./6-How-The-Web-Works.md#t1-14">1.14 جدول مرجعي: سجلات DNS والأدوات (Cheatsheet)</a><br><a href="./6-How-The-Web-Works.md#t1-15">1.15 سيناريو: جهاز يرسل استعلامات DNS غريبة</a><br><a href="./6-How-The-Web-Works.md#t1-16">1.16 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">2</td><td dir="ltr" align="left" style="text-align:left"><a href="./6-How-The-Web-Works.md#room-2">HTTP in Detail</a></td><td align="right" style="text-align:right"><a href="./6-How-The-Web-Works.md#t2-1">2.1 التعريف بالغرفة وأهدافها</a><br><a href="./6-How-The-Web-Works.md#t2-2">2.2 ما هو HTTP وما هو HTTPS</a><br><a href="./6-How-The-Web-Works.md#t2-3">2.3 إصدارات HTTP (1.1 و2 و3)</a><br><a href="./6-How-The-Web-Works.md#t2-4">2.4 تشريح عنوان URL</a><br><a href="./6-How-The-Web-Works.md#t2-5">2.5 بنية طلب HTTP</a><br><a href="./6-How-The-Web-Works.md#t2-6">2.6 بنية استجابة HTTP وتفكيكها سطرًا سطرًا</a><br><a href="./6-How-The-Web-Works.md#t2-7">2.7 رؤوس HTTP (Headers)</a><br><a href="./6-How-The-Web-Works.md#t2-8">2.8 طرق HTTP (Methods)</a><br><a href="./6-How-The-Web-Works.md#t2-9">2.9 رموز الحالة (Status Codes)</a><br><a href="./6-How-The-Web-Works.md#t2-10">2.10 الكوكيز (Cookies)</a><br><a href="./6-How-The-Web-Works.md#t2-11">2.11 الكوكيز مقابل تخزين المتصفح (Web Storage)</a><br><a href="./6-How-The-Web-Works.md#t2-12">2.12 الزاوية الأمنية: HTTP من منظور المهاجم والمدافع</a><br><a href="./6-How-The-Web-Works.md#t2-13">2.13 أدوات إرسال الطلبات وتحليل السجلات</a><br><a href="./6-How-The-Web-Works.md#t2-14">2.14 جدول مرجعي: HTTP والأدوات (Cheatsheet)</a><br><a href="./6-How-The-Web-Works.md#t2-15">2.15 سيناريو: موجة محاولات دخول على صفحة تسجيل الدخول</a><br><a href="./6-How-The-Web-Works.md#t2-16">2.16 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">3</td><td dir="ltr" align="left" style="text-align:left"><a href="./6-How-The-Web-Works.md#room-3">How Websites Work</a></td><td align="right" style="text-align:right"><a href="./6-How-The-Web-Works.md#t3-1">3.1 التعريف بالغرفة وأهدافها</a><br><a href="./6-How-The-Web-Works.md#t3-2">3.2 نموذج العميل والخادم</a><br><a href="./6-How-The-Web-Works.md#t3-3">3.3 Frontend و Backend</a><br><a href="./6-How-The-Web-Works.md#t3-4">3.4 مكونات الخلفية: الخادم وقاعدة البيانات والطبقة الوسيطة</a><br><a href="./6-How-The-Web-Works.md#t3-5">3.5 واجهات API وصيغة JSON</a><br><a href="./6-How-The-Web-Works.md#t3-6">3.6 المكونات الوسيطة: Load Balancer وCDN وWAF</a><br><a href="./6-How-The-Web-Works.md#t3-7">3.7 دورة حياة طلب الويب</a><br><a href="./6-How-The-Web-Works.md#t3-8">3.8 أين تقع الهجمات: Frontend وBackend وما بينهما</a><br><a href="./6-How-The-Web-Works.md#t3-9">3.9 الزاوية الأمنية: المراقبة ومنطق التطبيق</a><br><a href="./6-How-The-Web-Works.md#t3-10">3.10 أدوات فحص دورة حياة الطلب</a><br><a href="./6-How-The-Web-Works.md#t3-11">3.11 جدول مرجعي: بنية الويب والأدوات (Cheatsheet)</a><br><a href="./6-How-The-Web-Works.md#t3-12">3.12 سيناريو: تباطؤ الموقع وطلبات غير معتادة</a><br><a href="./6-How-The-Web-Works.md#t3-13">3.13 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">4</td><td dir="ltr" align="left" style="text-align:left"><a href="./6-How-The-Web-Works.md#room-4">Putting it all together</a></td><td align="right" style="text-align:right"><a href="./6-How-The-Web-Works.md#t4-1">4.1 التعريف بالغرفة وأهدافها</a><br><a href="./6-How-The-Web-Works.md#t4-2">4.2 رحلة تسجيل دخول كاملة من البداية إلى النهاية</a><br><a href="./6-How-The-Web-Works.md#t4-3">4.3 أدوات المطور وتبويب Network</a><br><a href="./6-How-The-Web-Works.md#t4-4">4.4 ربط DNS وعنوان IP وHTTP</a><br><a href="./6-How-The-Web-Works.md#t4-5">4.5 سياسة الأصل الواحد (Same-Origin Policy) وCORS</a><br><a href="./6-How-The-Web-Works.md#t4-6">4.6 تحليل حركة HTTP لاكتشاف الهجمات</a><br><a href="./6-How-The-Web-Works.md#t4-7">4.7 ربط استجابات الخادم بأخطاء التهيئة</a><br><a href="./6-How-The-Web-Works.md#t4-8">4.8 خريطة: من مفاهيم الوحدة إلى الهجمات المقابلة</a><br><a href="./6-How-The-Web-Works.md#t4-9">4.9 الزاوية الأمنية: سير عمل المحلل مع طلب مشبوه</a><br><a href="./6-How-The-Web-Works.md#t4-10">4.10 أدوات التتبع والفحص</a><br><a href="./6-How-The-Web-Works.md#t4-11">4.11 جدول مرجعي: التحليل وربط المفاهيم (Cheatsheet)</a><br><a href="./6-How-The-Web-Works.md#t4-12">4.12 سيناريو: رابط تصيد وربط الأدلة معًا</a><br><a href="./6-How-The-Web-Works.md#t4-13">4.13 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./6-How-The-Web-Works.md#module-glossary">جدول المصطلحات</a></td><td align="right" style="text-align:right">أهم مصطلحات الوحدة بمعانيها وأرقام الغرف</td></tr>
</tbody>
</table>

<br>

<a id="module-7"></a>

<table width="100%">
<tr><td align="center">

## ⚔ [الوحدة السابعة: Attacks and Defenses](./7-Attacks-and-Defenses.md)

الهجوم والدفاع: ثلاثية CIA، ومفاهيم التشفير، وعقلية المهاجم ودورة الهجوم، وتحديات CTF، وأسس عمل المدافع وفريق SOC.

</td></tr>
</table>

<p align="center"><sub>📚 جدول محتويات الوحدة</sub></p>

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">#</th><th align="right" style="text-align:right">الغرفة</th><th align="right" style="text-align:right">الموضوعات بالترتيب</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./7-Attacks-and-Defenses.md#module-intro">مقدمة الوحدة</a></td><td align="right" style="text-align:right">ثلاثية CIA والتشفير وعقلية المهاجم وعقلية المدافع وتحديات CTF</td></tr>
<tr><td align="right" style="text-align:right">1</td><td dir="ltr" align="left" style="text-align:left"><a href="./7-Attacks-and-Defenses.md#room-1">The CIA Triad</a></td><td align="right" style="text-align:right"><a href="./7-Attacks-and-Defenses.md#t1-1">1.1 التعريف بالغرفة وأهدافها</a><br><a href="./7-Attacks-and-Defenses.md#t1-2">1.2 لماذا نحتاج إطارًا للأمن؟</a><br><a href="./7-Attacks-and-Defenses.md#t1-3">1.3 الأصول والتهديدات والثغرات والمخاطر</a><br><a href="./7-Attacks-and-Defenses.md#t1-4">1.4 ثلاثية CIA نظرة عامة</a><br><a href="./7-Attacks-and-Defenses.md#t1-5">1.5 السرية (Confidentiality)</a><br><a href="./7-Attacks-and-Defenses.md#t1-6">1.6 السلامة / النزاهة (Integrity)</a><br><a href="./7-Attacks-and-Defenses.md#t1-7">1.7 التوافر / الإتاحة (Availability)</a><br><a href="./7-Attacks-and-Defenses.md#t1-8">1.8 كيف تُنتهك الركائز الثلاث</a><br><a href="./7-Attacks-and-Defenses.md#t1-9">1.9 العلاقة بين الركائز والموازنة بينها</a><br><a href="./7-Attacks-and-Defenses.md#t1-10">1.10 ما بعد الثلاثية: مفاهيم مكملة</a><br><a href="./7-Attacks-and-Defenses.md#t1-11">1.11 عقلية الأمن السيبراني (Security Mindset)</a><br><a href="./7-Attacks-and-Defenses.md#t1-12">1.12 الزاوية الأمنية: تقييم أثر الحادث بالثلاثية</a><br><a href="./7-Attacks-and-Defenses.md#t1-13">1.13 أدوات بسيطة لتطبيق الثلاثية عمليًا</a><br><a href="./7-Attacks-and-Defenses.md#t1-14">1.14 جدول مرجعي: ثلاثية CIA (Cheatsheet)</a><br><a href="./7-Attacks-and-Defenses.md#t1-15">1.15 سيناريو: تقييم حادث فدية بالثلاثية</a><br><a href="./7-Attacks-and-Defenses.md#t1-16">1.16 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">2</td><td dir="ltr" align="left" style="text-align:left"><a href="./7-Attacks-and-Defenses.md#room-2">Cryptography Concepts</a></td><td align="right" style="text-align:right"><a href="./7-Attacks-and-Defenses.md#t2-1">2.1 التعريف بالغرفة وأهدافها</a><br><a href="./7-Attacks-and-Defenses.md#t2-2">2.2 لماذا نحتاج التشفير؟</a><br><a href="./7-Attacks-and-Defenses.md#t2-3">2.3 حالات البيانات الثلاث (Data States)</a><br><a href="./7-Attacks-and-Defenses.md#t2-4">2.4 المصطلحات الأساسية في التشفير</a><br><a href="./7-Attacks-and-Defenses.md#t2-5">2.5 عملية التشفير وفك التشفير</a><br><a href="./7-Attacks-and-Defenses.md#t2-6">2.6 مثال تعليمي: شفرة قيصر (Caesar Cipher)</a><br><a href="./7-Attacks-and-Defenses.md#t2-7">2.7 التشفير المتماثل (Symmetric Encryption)</a><br><a href="./7-Attacks-and-Defenses.md#t2-8">2.8 التشفير غير المتماثل (Asymmetric Encryption)</a><br><a href="./7-Attacks-and-Defenses.md#t2-9">2.9 المقارنة والنهج الهجين (Hybrid Approach)</a><br><a href="./7-Attacks-and-Defenses.md#t2-10">2.10 دوال التجزئة (Hashing)</a><br><a href="./7-Attacks-and-Defenses.md#t2-11">2.11 التوقيع الرقمي (Digital Signature)</a><br><a href="./7-Attacks-and-Defenses.md#t2-12">2.12 الشهادات الرقمية و HTTPS</a><br><a href="./7-Attacks-and-Defenses.md#t2-13">2.13 HTTPS: النهج الهجين في العمل</a><br><a href="./7-Attacks-and-Defenses.md#t2-14">2.14 تقادم الخوارزميات وأنواع الهجمات على التشفير</a><br><a href="./7-Attacks-and-Defenses.md#t2-15">2.15 الزاوية الأمنية: التشفير في عمل المدافع</a><br><a href="./7-Attacks-and-Defenses.md#t2-16">2.16 تجربة التشفير بأوامر سطر الأوامر</a><br><a href="./7-Attacks-and-Defenses.md#t2-17">2.17 جدول مرجعي: التشفير والأدوات (Cheatsheet)</a><br><a href="./7-Attacks-and-Defenses.md#t2-18">2.18 سيناريو: شهادة مشبوهة على صفحة تسجيل دخول</a><br><a href="./7-Attacks-and-Defenses.md#t2-19">2.19 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">3</td><td dir="ltr" align="left" style="text-align:left"><a href="./7-Attacks-and-Defenses.md#room-3">Become a Hacker</a></td><td align="right" style="text-align:right"><a href="./7-Attacks-and-Defenses.md#t3-1">3.1 التعريف بالغرفة وأهدافها</a><br><a href="./7-Attacks-and-Defenses.md#t3-2">3.2 فلسفة الهجوم: لماذا يفكر المدافع كمهاجم؟</a><br><a href="./7-Attacks-and-Defenses.md#t3-3">3.3 أنواع المهاجمين والهاكرز</a><br><a href="./7-Attacks-and-Defenses.md#t3-4">3.4 الهاكر الأخلاقي والحدود القانونية</a><br><a href="./7-Attacks-and-Defenses.md#t3-5">3.5 دورة حياة الهجوم</a><br><a href="./7-Attacks-and-Defenses.md#t3-6">3.6 تفصيل المراحل: الاستطلاع والفحص</a><br><a href="./7-Attacks-and-Defenses.md#t3-7">3.7 تفصيل المراحل: الاستغلال والحصول على الوصول</a><br><a href="./7-Attacks-and-Defenses.md#t3-8">3.8 الهندسة الاجتماعية (Social Engineering)</a><br><a href="./7-Attacks-and-Defenses.md#t3-9">3.9 تفصيل المراحل: الإبقاء على الوصول ومحو الآثار</a><br><a href="./7-Attacks-and-Defenses.md#t3-10">3.10 منهجية اختبار الاختراق (Penetration Testing)</a><br><a href="./7-Attacks-and-Defenses.md#t3-11">3.11 أطر العمل: Cyber Kill Chain و MITRE ATT&CK</a><br><a href="./7-Attacks-and-Defenses.md#t3-12">3.12 الزاوية الأمنية: كيف يكتشف المدافع كل مرحلة؟</a><br><a href="./7-Attacks-and-Defenses.md#t3-13">3.13 أدوات الكشف الدفاعي لمراحل الهجوم</a><br><a href="./7-Attacks-and-Defenses.md#t3-14">3.14 جدول مرجعي: مراحل الهجوم والكشف (Cheatsheet)</a><br><a href="./7-Attacks-and-Defenses.md#t3-15">3.15 سيناريو: سلسلة تنبيهات تحكي قصة اختراق</a><br><a href="./7-Attacks-and-Defenses.md#t3-16">3.16 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">4</td><td dir="ltr" align="left" style="text-align:left"><a href="./7-Attacks-and-Defenses.md#room-4">Mystery Chest</a></td><td align="right" style="text-align:right"><a href="./7-Attacks-and-Defenses.md#t4-1">4.1 التعريف بالغرفة وأهدافها</a><br><a href="./7-Attacks-and-Defenses.md#t4-2">4.2 ما هو الـ CTF ولماذا يهم؟</a><br><a href="./7-Attacks-and-Defenses.md#t4-3">4.3 فئات تحديات الـ CTF</a><br><a href="./7-Attacks-and-Defenses.md#t4-4">4.4 منهجية حل التحديات</a><br><a href="./7-Attacks-and-Defenses.md#t4-5">4.5 التعرف على الترميزات والتشفيرات الشائعة</a><br><a href="./7-Attacks-and-Defenses.md#t4-6">4.6 أدوات الحل الأساسية</a><br><a href="./7-Attacks-and-Defenses.md#t4-7">4.7 مثال تطبيقي كامل: فك طبقتين</a><br><a href="./7-Attacks-and-Defenses.md#t4-8">4.8 الزاوية الأمنية: من الـ CTF إلى عمل المحلل</a><br><a href="./7-Attacks-and-Defenses.md#t4-9">4.9 أدوات فك الترميز في سطر الأوامر</a><br><a href="./7-Attacks-and-Defenses.md#t4-10">4.10 جدول مرجعي: تحديات التشفير والترميز (Cheatsheet)</a><br><a href="./7-Attacks-and-Defenses.md#t4-11">4.11 سيناريو: أمر PowerShell مرمّز في تنبيه EDR</a><br><a href="./7-Attacks-and-Defenses.md#t4-12">4.12 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">5</td><td dir="ltr" align="left" style="text-align:left"><a href="./7-Attacks-and-Defenses.md#room-5">Become a Defender</a></td><td align="right" style="text-align:right"><a href="./7-Attacks-and-Defenses.md#t5-1">5.1 التعريف بالغرفة وأهدافها</a><br><a href="./7-Attacks-and-Defenses.md#t5-2">5.2 عقلية الدفاع وفريق Blue Team</a><br><a href="./7-Attacks-and-Defenses.md#t5-3">5.3 الدفاع العميق (Defense in Depth)</a><br><a href="./7-Attacks-and-Defenses.md#t5-4">5.4 طبقات الدفاع بالتفصيل</a><br><a href="./7-Attacks-and-Defenses.md#t5-5">5.5 أنواع الضوابط الأمنية</a><br><a href="./7-Attacks-and-Defenses.md#t5-6">5.6 ربط الضوابط بثلاثية CIA</a><br><a href="./7-Attacks-and-Defenses.md#t5-7">5.7 تقليل سطح الهجوم والتقوية (Hardening)</a><br><a href="./7-Attacks-and-Defenses.md#t5-8">5.8 فريق SOC وأدواته</a><br><a href="./7-Attacks-and-Defenses.md#t5-9">5.9 فرز التنبيهات (Alert Triage)</a><br><a href="./7-Attacks-and-Defenses.md#t5-10">5.10 الاستجابة للحوادث (Incident Response)</a><br><a href="./7-Attacks-and-Defenses.md#t5-11">5.11 الزاوية الأمنية: بناء قاعدة كشف وقياس الأداء</a><br><a href="./7-Attacks-and-Defenses.md#t5-12">5.12 أدوات المراقبة والاستجابة الأساسية</a><br><a href="./7-Attacks-and-Defenses.md#t5-13">5.13 جدول مرجعي: الدفاع والاستجابة (Cheatsheet)</a><br><a href="./7-Attacks-and-Defenses.md#t5-14">5.14 سيناريو: فرز تنبيه واستجابة كاملة</a><br><a href="./7-Attacks-and-Defenses.md#t5-15">5.15 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="./7-Attacks-and-Defenses.md#module-glossary">جدول المصطلحات</a></td><td align="right" style="text-align:right">أهم مصطلحات الوحدة بمعانيها وأرقام الغرف</td></tr>
</tbody>
</table>

</div>