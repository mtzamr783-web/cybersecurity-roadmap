<div dir="rtl" align="right">

# الوحدة السادسة: How The Web Works

## 📑 فهرس الوحدة

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">#</th><th align="right" style="text-align:right">الغرفة</th><th align="right" style="text-align:right">الموضوعات بالترتيب</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="#module-intro">مقدمة الوحدة</a></td><td align="right" style="text-align:right">كيف يعمل الويب: DNS وHTTP وبنية المواقع ورحلة الطلب كاملة</td></tr>
<tr><td align="right" style="text-align:right">1</td><td dir="ltr" align="left" style="text-align:left"><a href="#room-1">DNS in Detail</a></td><td align="right" style="text-align:right"><a href="#t1-1">1.1 التعريف بالغرفة وأهدافها</a><br><a href="#t1-2">1.2 ما هو DNS ولماذا نحتاجه</a><br><a href="#t1-3">1.3 بنية اسم النطاق والتسلسل الهرمي</a><br><a href="#t1-4">1.4 نطاق المستوى الأعلى TLD</a><br><a href="#t1-5">1.5 نطاق المستوى الثاني وطول النطاق وقيود الإنشاء</a><br><a href="#t1-6">1.6 النطاق الفرعي وأمثلة لكل نوع</a><br><a href="#t1-7">1.7 أنواع سجلات DNS</a><br><a href="#t1-8">1.8 ماذا يحدث عند طلب DNS بالتفصيل</a><br><a href="#t1-9">1.9 كيف يتعامل المتصفح ونظام التشغيل مع طلب DNS</a><br><a href="#t1-10">1.10 أمن DNS: الهجمات والحماية</a><br><a href="#t1-11">1.11 الزاوية الأمنية: أدوات الاستطلاع والتحقيق في DNS</a><br><a href="#t1-12">1.12 الزاوية الأمنية: تحليل سجلات DNS واكتشاف الاتصالات الخبيثة</a><br><a href="#t1-13">1.13 أدوات استعلام DNS والتحقق منه</a><br><a href="#t1-14">1.14 جدول مرجعي: سجلات DNS والأدوات (Cheatsheet)</a><br><a href="#t1-15">1.15 سيناريو: جهاز يرسل استعلامات DNS غريبة</a><br><a href="#t1-16">1.16 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">2</td><td dir="ltr" align="left" style="text-align:left"><a href="#room-2">HTTP in Detail</a></td><td align="right" style="text-align:right"><a href="#t2-1">2.1 التعريف بالغرفة وأهدافها</a><br><a href="#t2-2">2.2 ما هو HTTP وما هو HTTPS</a><br><a href="#t2-3">2.3 إصدارات HTTP (1.1 و2 و3)</a><br><a href="#t2-4">2.4 تشريح عنوان URL</a><br><a href="#t2-5">2.5 بنية طلب HTTP</a><br><a href="#t2-6">2.6 بنية استجابة HTTP وتفكيكها سطرًا سطرًا</a><br><a href="#t2-7">2.7 رؤوس HTTP (Headers)</a><br><a href="#t2-8">2.8 طرق HTTP (Methods)</a><br><a href="#t2-9">2.9 رموز الحالة (Status Codes)</a><br><a href="#t2-10">2.10 الكوكيز (Cookies)</a><br><a href="#t2-11">2.11 الكوكيز مقابل تخزين المتصفح (Web Storage)</a><br><a href="#t2-12">2.12 الزاوية الأمنية: HTTP من منظور المهاجم والمدافع</a><br><a href="#t2-13">2.13 أدوات إرسال الطلبات وتحليل السجلات</a><br><a href="#t2-14">2.14 جدول مرجعي: HTTP والأدوات (Cheatsheet)</a><br><a href="#t2-15">2.15 سيناريو: موجة محاولات دخول على صفحة تسجيل الدخول</a><br><a href="#t2-16">2.16 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">3</td><td dir="ltr" align="left" style="text-align:left"><a href="#room-3">How Websites Work</a></td><td align="right" style="text-align:right"><a href="#t3-1">3.1 التعريف بالغرفة وأهدافها</a><br><a href="#t3-2">3.2 نموذج العميل والخادم</a><br><a href="#t3-3">3.3 Frontend و Backend</a><br><a href="#t3-4">3.4 مكونات الخلفية: الخادم وقاعدة البيانات والطبقة الوسيطة</a><br><a href="#t3-5">3.5 واجهات API وصيغة JSON</a><br><a href="#t3-6">3.6 المكونات الوسيطة: Load Balancer وCDN وWAF</a><br><a href="#t3-7">3.7 دورة حياة طلب الويب</a><br><a href="#t3-8">3.8 أين تقع الهجمات: Frontend وBackend وما بينهما</a><br><a href="#t3-9">3.9 الزاوية الأمنية: المراقبة ومنطق التطبيق</a><br><a href="#t3-10">3.10 أدوات فحص دورة حياة الطلب</a><br><a href="#t3-11">3.11 جدول مرجعي: بنية الويب والأدوات (Cheatsheet)</a><br><a href="#t3-12">3.12 سيناريو: تباطؤ الموقع وطلبات غير معتادة</a><br><a href="#t3-13">3.13 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">4</td><td dir="ltr" align="left" style="text-align:left"><a href="#room-4">Putting it all together</a></td><td align="right" style="text-align:right"><a href="#t4-1">4.1 التعريف بالغرفة وأهدافها</a><br><a href="#t4-2">4.2 رحلة تسجيل دخول كاملة من البداية إلى النهاية</a><br><a href="#t4-3">4.3 أدوات المطور وتبويب Network</a><br><a href="#t4-4">4.4 ربط DNS وعنوان IP وHTTP</a><br><a href="#t4-5">4.5 سياسة الأصل الواحد (Same-Origin Policy) وCORS</a><br><a href="#t4-6">4.6 تحليل حركة HTTP لاكتشاف الهجمات</a><br><a href="#t4-7">4.7 ربط استجابات الخادم بأخطاء التهيئة</a><br><a href="#t4-8">4.8 خريطة: من مفاهيم الوحدة إلى الهجمات المقابلة</a><br><a href="#t4-9">4.9 الزاوية الأمنية: سير عمل المحلل مع طلب مشبوه</a><br><a href="#t4-10">4.10 أدوات التتبع والفحص</a><br><a href="#t4-11">4.11 جدول مرجعي: التحليل وربط المفاهيم (Cheatsheet)</a><br><a href="#t4-12">4.12 سيناريو: رابط تصيد وربط الأدلة معًا</a><br><a href="#t4-13">4.13 كيف تتعامل مع أسئلة الغرفة بمنهجية</a></td></tr>
<tr><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right"><a href="#module-glossary">جدول المصطلحات</a></td><td align="right" style="text-align:right">أهم مصطلحات الوحدة بمعانيها وأرقام الغرف</td></tr>
</tbody>
</table>

<a id="module-intro"></a>

## 🧭 مقدمة عن الوحدة

كل ما نفعله على الإنترنت، من فتح موقع إلى تسجيل دخول إلى تنزيل ملف، يبدأ بكتابة **رابط** ثم تحدث وراءه سلسلة من الخطوات: ترجمة الاسم إلى عنوان، وبناء اتصال، وتبادل رسائل بلغة متفق عليها، ثم عرض الصفحة. وفهم هذه السلسلة هو **أساس تحليل هجمات الويب**، لأن المحلل لا يستطيع أن يعرف ما هو الشاذ قبل أن يعرف ما هو الطبيعي.

تسير الوحدة في أربع غرف:

- **DNS in Detail:** كيف تتحول أسماء النطاقات إلى عناوين IP، وأنواع السجلات، وهجمات DNS.
- **HTTP in Detail:** لغة الويب: الطلبات والاستجابات والرؤوس والطرق ورموز الحالة والكوكيز.
- **How Websites Work:** البنية الخلفية: العميل والخادم، Frontend وBackend، ودورة حياة الطلب.
- **Putting it all together:** تجميع كل ما سبق في رحلة واحدة، وأدوات المتصفح، وتحليل الحركة.

وفي كل غرفة: **زاوية أمنية** تربط الموضوع بعمل فريق الدفاع (Blue Team / SOC)، وجدول مرجعي **Cheatsheet** حيث توجد أوامر أو صياغات، وفقرة **خلاصة المحلل الأمني (SOC Takeaways)**، وفي آخر الوحدة جدول مصطلحات. وجميع الأمثلة بقيم خاصة بنا للشرح (مثل `example.com` وعناوين `192.0.2.x`)، ولا تتضمن حلولًا لأسئلة المنصة.

<br>

<a id="room-1"></a>
<table align="center" width="100%"><tr><td align="right" style="text-align:right">

### 🚪 الغرفة 1: DNS in Detail (نظام أسماء النطاقات بالتفصيل)

</td></tr></table>

<h1 dir="ltr" align="left" style="text-align:left">DNS in Detail</h1>

### <a id="t1-1"></a>1.1 التعريف بالغرفة وأهدافها

كل ما نفعله على الويب يبدأ بسؤال بسيط: **ما عنوان هذا الموقع؟** نحن نكتب أسماء سهلة التذكر مثل `example.com`، بينما تتحدث الأجهزة فيما بينها بعناوين **IP** فقط. والذي يترجم بين الاسم والعنوان هو **DNS (Domain Name System)**، أي **نظام أسماء النطاقات**، وهو أحد أهم الأنظمة وأكثرها استهدافًا في الأمن السيبراني، لأن كل اتصال تقريبًا يمر به.

ومن أهداف الغرفة أن نكون قادرين في نهايتها على:
- شرح ما هو DNS ولماذا لا يمكن للويب أن يعمل بدونه.
- قراءة اسم النطاق وتفكيكه إلى **Root** و**TLD** و**Second-Level Domain** و**Subdomain**.
- معرفة قيود طول النطاق والرموز المسموح بها عند إنشائه.
- التفريق بين سجلات **A** و**AAAA** و**CNAME** و**MX** و**TXT** وما تُستخدم له.
- تتبع ما يحدث بالتفصيل حين يطلب جهازك عنوان موقع، ودور **TTL** والتخزين المؤقت.
- فهم أخطار **DNS Spoofing** و**Cache Poisoning** ودور **DNSSEC**.
- استخدام أدوات الاستعلام والاستطلاع (`nslookup` و`dig` و`whois` و`dnsenum`) بشكل مشروع.
- ربط سجلات DNS بمراقبة الشبكة لاكتشاف الاتصالات الخبيثة مثل **DNS Tunneling** و**C2**.

<h2 dir="ltr" align="left" style="text-align:left">📌 Concepts Covered</h2>

### <a id="t1-2"></a>1.2 ما هو DNS ولماذا نحتاجه

الأجهزة على الشبكة تتعرف على بعضها بعناوين **IP** مثل `192.0.2.10` (IPv4) أو `2001:db8::10` (IPv6)، وهي أرقام يصعب على الإنسان حفظها وقد **تتغير** مع الزمن. فجاء **DNS** كـ **دليل هاتف موزّع للإنترنت**: تسأله عن اسم فيعطيك العنوان المقابل.

ولهذا النظام ثلاث فوائد رئيسية:
- **سهولة التذكر:** نتعامل بأسماء بدل الأرقام.
- **المرونة:** يمكن لصاحب الموقع تغيير عنوان الخادم دون أن يعرف المستخدمون شيئًا، لأن الاسم يبقى ثابتًا.
- **التوزيع:** لا توجد قاعدة بيانات واحدة ضخمة، بل خوادم كثيرة كل منها مسؤول عن جزء، مما يعطي سرعة وقدرة على التحمل.

ويعمل DNS غالبًا على المنفذ **53** بروتوكول **UDP** للاستعلامات الصغيرة، وبروتوكول **TCP** عند كبر الاستجابة أو في عمليات مثل نقل المنطقة (Zone Transfer). وتوجد نسخ مشفرة هي **DNS over TLS (DoT)** على المنفذ 853 و**DNS over HTTPS (DoH)** على المنفذ 443.

وتذكّر أن DNS **بروتوكول قديم صُمّم دون تشفير أو تحقق من الهوية**، وهذا سبب كثرة هجماته، وسنعود لذلك في موضوعي الأمن.

### <a id="t1-3"></a>1.3 بنية اسم النطاق والتسلسل الهرمي

الأسماء في DNS مرتبة في **شجرة**، وتُقرأ من **اليمين إلى اليسار** من الأعم إلى الأخص. وفي أعلى الشجرة يوجد **الجذر (Root)** ويُرمز له بنقطة `.` وغالبًا لا نكتبها، وتحته نطاقات المستوى الأعلى، ثم نطاقات المستوى الثاني، ثم النطاقات الفرعية.

<p align="center">
  <img src="images/dns-hierarchy.png" width="620" alt="التسلسل الهرمي للنطاقات"><br>
  <sub>شجرة DNS: الجذر في الأعلى (أحمر)، ثم نطاقات المستوى الأعلى TLD (أزرق)، ثم نطاقات المستوى الثاني (أخضر)</sub>
</p>

وبأخذ الاسم `www.example.com.` مثالًا تُقرأ أجزاؤه هكذا:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الجزء</th><th align="right" style="text-align:right">المستوى</th><th align="right" style="text-align:right">الدور</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><code>.</code> (النقطة الأخيرة)</td><td dir="ltr" align="left" style="text-align:left"><b>Root</b></td><td align="right" style="text-align:right">قمة الشجرة، تديره خوادم الجذر</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>com</code></td><td dir="ltr" align="left" style="text-align:left"><b>TLD</b></td><td align="right" style="text-align:right">نطاق المستوى الأعلى</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>example</code></td><td dir="ltr" align="left" style="text-align:left"><b>Second-Level Domain (SLD)</b></td><td align="right" style="text-align:right">الاسم الذي يسجله صاحب الموقع</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>www</code></td><td dir="ltr" align="left" style="text-align:left"><b>Subdomain</b></td><td align="right" style="text-align:right">قسم أو خدمة تحت النطاق</td></tr>
</tbody>
</table>

والاسم الكامل بكل أجزائه، وتنتهي بنقطة الجذر، يسمى **FQDN (Fully Qualified Domain Name)**. وكل جزء بين نقطتين يسمى **Label (تسمية)**.

### <a id="t1-4"></a>1.4 نطاق المستوى الأعلى TLD

**TLD (Top-Level Domain)** هو آخر جزء في الاسم، مثل `.com` و`.org` و`.eg`. والغرض منه **تصنيف النطاقات** بحسب النشاط أو البلد، وتوزيع مسؤولية الإدارة بين جهات مختلفة بدل جهة واحدة. وله نوعان رئيسيان:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">النوع</th><th align="right" style="text-align:right">المعنى</th><th align="right" style="text-align:right">أمثلة</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>gTLD</b> (Generic TLD)</td><td align="right" style="text-align:right">نطاق عام يرتبط بنوع النشاط</td><td align="right" style="text-align:right"><code>.com</code> تجاري، <code>.org</code> منظمات، <code>.net</code> شبكات، <code>.edu</code> تعليم، <code>.gov</code> حكومات، <code>.mil</code> جيش</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>ccTLD</b> (Country Code TLD)</td><td align="right" style="text-align:right">رمز من حرفين يخص دولة</td><td align="right" style="text-align:right"><code>.eg</code> مصر، <code>.uk</code> بريطانيا، <code>.ca</code> كندا، <code>.de</code> ألمانيا</td></tr>
</tbody>
</table>

وبعض النطاقات **مقيّدة** (مثل `.edu` و`.gov` و`.mil`) فلا يسجلها إلا جهات مؤهلة، بينما تفتح أخرى مثل `.com` للجميع. وأضيفت في السنوات الأخيرة مئات النطاقات الجديدة (مثل `.xyz` و`.online`)، وبعضها رخيص جدًا ولذلك يكثر استخدامه في **النطاقات الخبيثة**، وهي نقطة يراعيها المحلل عند الفرز.

### <a id="t1-5"></a>1.5 نطاق المستوى الثاني وطول النطاق وقيود الإنشاء

**Second-Level Domain (SLD)** هو الجزء الذي يسبق الـ TLD مباشرة، وهو **الاسم الذي يحجزه صاحب الموقع** من جهة تسجيل (Registrar). مثل `example` في `example.com`، أو `google` في `google.com`، أو `tryhackme` في `tryhackme.com`.

وللنطاقات **قيود** عند الإنشاء، تنطبق على كل Label:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">القاعدة</th><th align="right" style="text-align:right">التفصيل</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><b>الطول</b></td><td align="right" style="text-align:right">كل Label (الجزء بين نقطتين) بحد أقصى <b>63 حرفًا</b></td></tr>
<tr><td align="right" style="text-align:right"><b>الطول الكلي</b></td><td align="right" style="text-align:right">الاسم الكامل بحد أقصى <b>253 حرفًا</b> في صيغته النصية</td></tr>
<tr><td align="right" style="text-align:right"><b>الرموز</b></td><td align="right" style="text-align:right">حروف إنجليزية <code>a-z</code> وأرقام <code>0-9</code> وشرطة <code>-</code></td></tr>
<tr><td align="right" style="text-align:right"><b>الشرطة</b></td><td align="right" style="text-align:right">لا يبدأ الـ Label ولا ينتهي بشرطة</td></tr>
<tr><td align="right" style="text-align:right"><b>الحروف الكبيرة</b></td><td align="right" style="text-align:right">غير حساسة لحالة الأحرف: <code>Example.COM</code> يساوي <code>example.com</code></td></tr>
<tr><td align="right" style="text-align:right"><b>الأسماء غير اللاتينية</b></td><td align="right" style="text-align:right">تُحوَّل إلى صيغة <b>Punycode</b> تبدأ بـ <code>xn--</code></td></tr>
</tbody>
</table>

وتفيد هذه القواعد في **الفحص الأمني**: Label طويل جدًا أو يبدو عشوائيًا في استعلام DNS علامة مشبوهة (سنراها في DNS Tunneling)، ووجود `xn--` في الاسم قد يدل على **نطاق مموه بحروف تشبه الحروف اللاتينية** (Homograph) يُستخدم في التصيد.

### <a id="t1-6"></a>1.6 النطاق الفرعي وأمثلة لكل نوع

**Subdomain** هو جزء يضيفه صاحب النطاق **على يسار** الـ SLD دون الحاجة لتسجيل جديد، ليقسم خدماته: `mail.example.com` للبريد، و`blog.example.com` للمدونة، و`api.example.com` للواجهات البرمجية. وله نفس قيود الـ Label، ويمكن تداخل أكثر من مستوى مثل `dev.api.example.com`، بشرط ألا يتجاوز الاسم الكامل 253 حرفًا.

والجدول التالي يجمع مثالًا لكل نوع:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">النوع</th><th align="right" style="text-align:right">مثال</th><th align="right" style="text-align:right">ملاحظة</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Root</b></td><td align="right" style="text-align:right"><code>.</code></td><td align="right" style="text-align:right">غالبًا غير مكتوب</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>TLD</b> (gTLD)</td><td dir="ltr" align="left" style="text-align:left"><code>.com</code> <code>.org</code> <code>.gov</code></td><td align="right" style="text-align:right">نشاط</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>TLD</b> (ccTLD)</td><td dir="ltr" align="left" style="text-align:left"><code>.eg</code> <code>.uk</code></td><td align="right" style="text-align:right">دولة</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>SLD</b></td><td align="right" style="text-align:right"><code>example</code> في <code>example.com</code></td><td align="right" style="text-align:right">يُسجَّل لدى Registrar</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Subdomain</b></td><td align="right" style="text-align:right"><code>www</code> و<code>mail</code> و<code>api</code> في <code>www.example.com</code></td><td align="right" style="text-align:right">يضيفه المالك مجانًا</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>FQDN</b></td><td dir="ltr" align="left" style="text-align:left"><code>www.example.com.</code></td><td align="right" style="text-align:right">الاسم الكامل بالنقطة الأخيرة</td></tr>
</tbody>
</table>

وللمحلل الأمني أهمية خاصة للنطاقات الفرعية، فكثير من الهجمات تستغل **نطاقات فرعية منسية** (مثل `old-test.example.com`) أو تستعمل **اسم الشركة كنطاق فرعي** داخل نطاق خبيث (`login.example.com.attacker.net`) ليبدو الرابط مألوفًا، والعبرة دائمًا بقراءة الاسم **من اليمين**: النطاق الحقيقي هنا هو `attacker.net`.

### <a id="t1-7"></a>1.7 أنواع سجلات DNS

يحتفظ كل نطاق بملف اسمه **Zone** يحتوي **سجلات (Records)** تخبر العالم أين خدماته. وكل سجل له **نوع (Type)** و**قيمة** و**TTL**. وأهم الأنواع:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">السجل</th><th align="right" style="text-align:right">الوظيفة</th><th align="right" style="text-align:right">مثال توضيحي</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>A</b></td><td align="right" style="text-align:right">يربط الاسم بعنوان <b>IPv4</b></td><td dir="ltr" align="left" style="text-align:left"><code>example.com. 300 A 192.0.2.10</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>AAAA</b></td><td align="right" style="text-align:right">يربط الاسم بعنوان <b>IPv6</b> (يُنطق Quad-A)</td><td dir="ltr" align="left" style="text-align:left"><code>example.com. 300 AAAA 2001:db8::10</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>CNAME</b></td><td align="right" style="text-align:right"><b>اسم مستعار</b> يشير إلى اسم آخر بدل عنوان</td><td dir="ltr" align="left" style="text-align:left"><code>www.example.com. CNAME example.com.</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>MX</b></td><td align="right" style="text-align:right">يحدد <b>خوادم البريد</b> مع رقم أولوية (الأقل أولًا)</td><td dir="ltr" align="left" style="text-align:left"><code>example.com. MX 10 mail.example.com.</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>TXT</b></td><td align="right" style="text-align:right">نص حر يحمل معلومات تحقق وسياسات</td><td dir="ltr" align="left" style="text-align:left"><code>"v=spf1 include:_spf.example.com ~all"</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>NS</b></td><td align="right" style="text-align:right">يحدد <b>خوادم الأسماء</b> المسؤولة عن النطاق</td><td dir="ltr" align="left" style="text-align:left"><code>example.com. NS ns1.example.com.</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>PTR</b></td><td align="right" style="text-align:right"><b>بحث عكسي</b>: من العنوان إلى الاسم</td><td dir="ltr" align="left" style="text-align:left"><code>10.2.0.192.in-addr.arpa. PTR example.com.</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>SOA</b></td><td align="right" style="text-align:right">بيانات المنطقة: الخادم الأساسي ورقم النسخة</td><td align="right" style="text-align:right">يتحكم في نقل المنطقة</td></tr>
</tbody>
</table>

وتفصيل أهم خمسة سجلات:

- **سجل A:** أكثر السجلات استخدامًا. قد يحمل الاسم أكثر من سجل A للتوزيع بين عدة خوادم.
- **سجل AAAA:** نظير A لعناوين IPv6. ويستخدمه المتصفح مع A بحسب ما تدعمه الشبكة.
- **سجل CNAME:** يفيد حين يستضيف طرف ثالث (CDN أو منصة سحابية) خدمتك: تشير `shop.example.com` إلى اسم المنصة، فإذا غيّرت المنصة عنوانها لا تحتاج لتعديل. ولا يجوز وضعه على **الجذر** (`example.com` نفسه) مع سجلات أخرى.
- **سجل MX:** حين يرسل أحدهم بريدًا إلى `user@example.com` يبحث خادمه عن MX الخاص بـ `example.com`. وكل سجل له **Priority** والأقل رقمًا يُجرَّب أولًا، فإن تعطل انتقل الإرسال إلى التالي.
- **سجل TXT:** صار مكانًا لوسائل أمنية: **SPF** يحدد الخوادم المسموح لها بإرسال البريد باسم النطاق، و**DKIM** يضع المفتاح العام لتوقيع الرسائل، و**DMARC** يحدد سياسة التعامل مع الرسائل المزورة، كما يُستخدم لإثبات **ملكية النطاق** للمنصات (برمز تحقق).

ومن زاوية الدفاع، سجلات **SPF/DKIM/DMARC** هي خط مقاومة أول ضد **انتحال البريد (Email Spoofing)**، وغيابها يجعل التصيد باسم الشركة أسهل.

### <a id="t1-8"></a>1.8 ماذا يحدث عند طلب DNS بالتفصيل

حين تكتب `www.example.com` في المتصفح، يمر طلب الـ DNS بخطوات متسلسلة. وهنا يظهر نوعان من الخوادم يجب التفريق بينهما:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">النوع</th><th align="right" style="text-align:right">الدور</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><b>Recursive DNS Server</b> (المحلل التكراري)</td><td align="right" style="text-align:right">يستقبل سؤالك <b>ويتولى البحث نيابة عنك</b> حتى يجد الجواب، وغالبًا يقدمه <b>مزود الإنترنت (ISP)</b> أو خدمة عامة مثل <code>8.8.8.8</code> و<code>1.1.1.1</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Root DNS Server</b></td><td align="right" style="text-align:right">يعرف <b>أي خوادم تدير كل TLD</b>. وتوجد 13 مجموعة عناوين لخوادم الجذر موزعة على مئات الأجهزة حول العالم</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>TLD Server</b></td><td align="right" style="text-align:right">يعرف <b>أي خوادم تدير كل نطاق</b> تحت هذا الـ TLD (مثل خوادم <code>.com</code>)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Authoritative DNS Server</b></td><td align="right" style="text-align:right">الخادم <b>صاحب الكلمة الأخيرة</b> لنطاق معين، عنده السجلات الأصلية</td></tr>
</tbody>
</table>

<p align="center">
  <img src="images/dns-resolution-flow.png" width="520" alt="مراحل طلب DNS"><br>
  <sub>رحلة الطلب: 1 جهازك، 2 الـ Recursive، 3 الـ Root، 4 الـ Authoritative، 5 عودة الجواب إلى الجهاز</sub>
</p>

وخطوات الطلب بالتسلسل (والأرقام في الصورة تقابل الخطوات الأساسية):

1. **جهازك يسأل (الرقم 1):** يتحقق أولًا من الذاكرة المحلية (سيأتي تفصيلها)، فإن لم يجد أرسل السؤال إلى **Recursive DNS Server**.
2. **المحلل التكراري (الرقم 2):** يفحص **ذاكرته المؤقتة (Cache)**، فإن وجد الجواب بصلاحية سارية أرجعه فورًا وانتهى الأمر.
3. **الجذر (الرقم 3):** إن لم يجد، يسأل أحد خوادم الجذر، فيجيبه **بإحالة (Referral)** إلى خوادم الـ TLD المناسبة، مثل `.com`.
4. **TLD ثم الـ Authoritative (الرقم 4):** يسأل خادم الـ TLD، فيحيله إلى **الخادم المسؤول عن النطاق**، ثم يسأل ذلك الخادم فيجيب بالسجل المطلوب.
5. **عودة الجواب (الرقم 5):** يصل الجواب إلى المحلل التكراري فيخزنه، ثم يرسله إلى جهازك، ويتصل المتصفح بالعنوان.

ولاحظ أن الصورة **تبسّط** الرحلة بحذف خطوة الـ TLD، لكن في الواقع هي حلقة وصل بين الجذر والخادم المسؤول.

وفي كل مرحلة لا يُعاد البحث من البداية في الطلبات اللاحقة لأن الجواب مخزن **لمدة محددة**، وهي **TTL**.

**TTL (Time To Live)** رقم بالثواني مرفق بكل سجل، يحدد **كم تحتفظ الخوادم والأجهزة بالجواب** قبل أن تسأل من جديد. مثلًا `TTL = 300` يعني خمس دقائق. وله حسابان متعارضان:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">القيمة</th><th align="right" style="text-align:right">الميزة</th><th align="right" style="text-align:right">العيب</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right">TTL <b>كبير</b> (ساعات أو أيام)</td><td align="right" style="text-align:right">ضغط أقل على الخوادم وسرعة أعلى</td><td align="right" style="text-align:right">أي تغيير في العنوان يتأخر وصوله لأن الجميع يحتفظ بالقديم</td></tr>
<tr><td align="right" style="text-align:right">TTL <b>صغير</b> (ثوانٍ أو دقائق)</td><td align="right" style="text-align:right">التغيير ينتشر بسرعة، مناسب للتوزيع والطوارئ</td><td align="right" style="text-align:right">استعلامات أكثر</td></tr>
</tbody>
</table>

ومن زاوية الأمن: **TTL شديد القصر** على نطاق غريب قد يدل على نشاط مخادع يبدّل عناوينه باستمرار (**Fast Flux**)، وقد يستخدمه المهاجم لينقل خادم الـ C2 بسرعة.

### <a id="t1-9"></a>1.9 كيف يتعامل المتصفح ونظام التشغيل مع طلب DNS

قبل أن يصل السؤال إلى الشبكة، يمر الاسم على **طبقات من الذاكرة المحلية**، لتوفير الوقت وتقليل الاستعلامات:

1. **ذاكرة المتصفح (Browser Cache):** يحتفظ المتصفح بالأسماء التي زارها مؤخرًا.
2. **ذاكرة نظام التشغيل (OS Resolver Cache):** عميل DNS في النظام يحتفظ بنتائج الطلبات السابقة من كل البرامج.
3. **ملف الـ hosts:** ملف نصي يربط أسماء بعناوين **يدويًا** ويُقرأ **قبل** الشبكة. وهو في `C:\Windows\System32\drivers\etc\hosts` على ويندوز، و`/etc/hosts` على لينكس.
4. **المحلل التكراري المضبوط على الجهاز:** وعنوانه يأتي من إعدادات الشبكة (غالبًا من DHCP)، ويظهر في `/etc/resolv.conf` أو `ipconfig /all`.

وللتعامل معها: لو غيرت سجلًا وما زال جهازك يرى القديم، فالسبب غالبًا **TTL لم ينتهِ** أو ذاكرة محلية قديمة، ويمكن مسحها (أوامرها في قسم الأدوات).

والخطر الأمني: **ملف hosts** هدف لبرمجيات خبيثة تضيف سطرًا يوجه اسم موقع بنك أو موقع تحديثات أمنية إلى عنوان المهاجم، أو تحجب مواقع شركات الحماية بتوجيهها إلى `127.0.0.1`. ولذلك يفحصه المحلل أثناء الفحص الجنائي للجهاز.

### <a id="t1-10"></a>1.10 أمن DNS: الهجمات والحماية

بما أن DNS هو **أساس الثقة** في الاتصال (يحدد إلى أين تذهب)، فإن التلاعب به يخدع المستخدم دون أن يلحظ. وأهم الأخطار:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الهجوم</th><th align="right" style="text-align:right">الفكرة</th><th align="right" style="text-align:right">الأثر</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DNS Spoofing / Cache Poisoning</b></td><td align="right" style="text-align:right">حقن جواب <b>مزور</b> في ذاكرة المحلل التكراري (بتخمين رقم المعاملة والمنفذ) ليخزّنه ويقدمه للجميع</td><td align="right" style="text-align:right">توجيه آلاف المستخدمين إلى موقع المهاجم مع أن الاسم صحيح</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DNS Hijacking</b></td><td align="right" style="text-align:right">تغيير إعدادات DNS في الراوتر أو الجهاز، أو سرقة حساب جهة التسجيل</td><td align="right" style="text-align:right">توجيه كل الطلبات أو النطاق كاملًا</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Typosquatting / Lookalike</b></td><td align="right" style="text-align:right">تسجيل أسماء تشبه الأسماء الأصلية (<code>examp1e.com</code>)</td><td align="right" style="text-align:right">التصيد وسرقة البيانات</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Subdomain Takeover</b></td><td align="right" style="text-align:right">نطاق فرعي بـ CNAME يشير لخدمة سحابية محذوفة، فيسجلها المهاجم</td><td align="right" style="text-align:right">السيطرة على نطاق فرعي موثوق</td></tr>
<tr><td align="right" style="text-align:right"><b>Zone Transfer مفتوح</b></td><td align="right" style="text-align:right">خادم يسمح لأي أحد بتنزيل كل سجلات النطاق (<code>AXFR</code>)</td><td align="right" style="text-align:right">كشف كامل لبنية الشبكة</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DNS Amplification</b></td><td align="right" style="text-align:right">استعلام صغير بعنوان مصدر مزور يستجلب رد كبيرًا إلى الضحية</td><td align="right" style="text-align:right">هجوم <b>DDoS</b></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DNS Tunneling</b></td><td align="right" style="text-align:right">تهريب بيانات أو أوامر داخل أسماء الاستعلامات</td><td align="right" style="text-align:right">سرقة بيانات وقناة <b>C2</b></td></tr>
</tbody>
</table>

ولحماية السجلات من التزوير تُستخدم تقنية **DNSSEC (DNS Security Extensions)**. فكرتها: **توقيع رقمي** على كل مجموعة سجلات، يستطيع المحلل التكراري **التحقق منه**، فإن تلاعب أحد بالجواب ينكسر التوقيع ويُرفض. وتعتمد على:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">العنصر</th><th align="right" style="text-align:right">الدور</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DNSKEY</b></td><td align="right" style="text-align:right">المفتاح العام للنطاق</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>RRSIG</b></td><td align="right" style="text-align:right">التوقيع الرقمي على مجموعة السجلات</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DS</b></td><td align="right" style="text-align:right">بصمة مفتاح النطاق، تُخزَّن عند النطاق <b>الأب</b> لبناء <b>سلسلة ثقة (Chain of Trust)</b> تنتهي بالجذر</td></tr>
</tbody>
</table>

وحدود DNSSEC مهمة: هو يحمي **صحة وسلامة** الجواب (Authenticity & Integrity) ولا **يشفّر** الاستعلام، فمن يراقب الشبكة يرى أي نطاق طلبته. أما **DoH** و**DoT** فيشفران الاتصال بين جهازك والمحلل التكراري لحماية الخصوصية، لكنهما قد يعميان فريق الدفاع إذا لم تُراقب الجهة التي تتجه إليها الاستعلامات.

وإجراءات الحماية العملية: تفعيل **DNSSEC** على النطاقات المملوكة، وقفل النطاق عند جهة التسجيل (**Registrar Lock**) و**المصادقة الثنائية** على حساب التسجيل، وتقييد **Zone Transfer** للخوادم المصرح بها فقط، وتحديث برمجيات DNS، وحصر الاستعلامات الصادرة على **خوادم DNS المؤسسية** في الجدار الناري.

### <a id="t1-11"></a>1.11 الزاوية الأمنية: أدوات الاستطلاع والتحقيق في DNS

يبدأ المهاجم أي عملية بجمع معلومات عن الهدف، وسجلات DNS **عامة ومتاحة للجميع**، فهي أول مصدر. وعلى المحلل الأمني أن يعرف **ما يراه المهاجم** ليُغلق ما لا يجب أن يظهر، وليحقق في نطاق مشبوه. وأشهر الأدوات:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الأداة</th><th align="right" style="text-align:right">ما تفعله</th><th align="right" style="text-align:right">استخدام المحلل</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><code>nslookup</code></td><td align="right" style="text-align:right">استعلام DNS بسيط، موجودة في ويندوز ولينكس</td><td align="right" style="text-align:right">فحص سريع لسجل أو اختبار خادم محدد</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>dig</code></td><td align="right" style="text-align:right">أداة لينكس الأقوى، تعرض الاستجابة كاملة</td><td align="right" style="text-align:right">التحقيق التفصيلي، وتتبع المسار (<code>+trace</code>)، واختبار Zone Transfer</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>whois</code></td><td align="right" style="text-align:right">بيانات تسجيل النطاق: الجهة والتواريخ وخوادم الأسماء</td><td align="right" style="text-align:right"><b>عمر النطاق</b>: النطاق حديث التسجيل مؤشر مشبوه</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>dnsenum</code></td><td align="right" style="text-align:right">تعداد شامل: السجلات وخوادم الأسماء ومحاولة Zone Transfer وتخمين نطاقات فرعية</td><td align="right" style="text-align:right">معرفة ما قد يكتشفه المهاجم عن نطاقاتك</td></tr>
</tbody>
</table>

وتنبيه قانوني وأخلاقي: **لا تُجرِّب أدوات التعداد (خاصة التخمين وZone Transfer) إلا على نطاقات تملكها أو لديك تصريح مكتوب بفحصها**. أما الاستعلامات العادية عن السجلات العامة فهي مشروعة.

### <a id="t1-12"></a>1.12 الزاوية الأمنية: تحليل سجلات DNS واكتشاف الاتصالات الخبيثة

الشبكة التي لا تراقب DNS تفقد أحد أفضل مصادر الكشف، لأن **كل برنامج خبيث تقريبًا يحتاج DNS** ليجد خادمه، ولأن DNS **مسموح عادة** في الجدار الناري. ولذلك يعده فريق الـ SOC من الأولويات.

**مصادر سجلات DNS:**
- سجلات **الخادم التكراري** المؤسسي (BIND query log، Windows DNS).
- أداة **Zeek** وملف `dns.log` من مراقبة الشبكة.
- حدث **Sysmon رقم 22 (DNSEvent)** على الأجهزة، ويربط الاستعلام **بالعملية** التي أرسلته.
- سجلات الجدار الناري و**Passive DNS** لقاعدة تاريخية عن النطاقات.

**DNS Tunneling:** يستخدمه المهاجم لأن DNS يمر من معظم الحواجز. يضع البيانات المسروقة مرمّزة (غالبًا Base64 أو Hex) داخل **Label طويل** في اسم نطاق يملكه، فيصل السؤال عبر الإنترنت إلى **خادمه الـ Authoritative**، وتحمل الإجابات (غالبًا TXT) الأوامر المرسلة للبرمجية. وهكذا تتشكل قناة **C2 (Command and Control)** دون أي اتصال مباشر بالمهاجم.

<p align="center">
  <img src="images/dns-tunneling.svg" width="820" alt="آلية DNS Tunneling"><br>
  <sub>البيانات داخل اسم الاستعلام، تمر عبر المحلل التكراري المسموح به إلى خادم المهاجم، والرد يحمل الأوامر</sub>
</p>

**مؤشرات الكشف (Indicators):**

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">المؤشر</th><th align="right" style="text-align:right">لماذا هو مشبوه</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><b>Label طويل جدًا أو عشوائي</b></td><td align="right" style="text-align:right">البيانات المرمّزة تبدو كحروف عشوائية</td></tr>
<tr><td align="right" style="text-align:right"><b>عدد ضخم من النطاقات الفرعية الفريدة</b> لنطاق واحد</td><td align="right" style="text-align:right">كل استعلام يحمل قطعة بيانات مختلفة</td></tr>
<tr><td align="right" style="text-align:right"><b>نسبة عالية من استعلامات TXT أو NULL</b></td><td align="right" style="text-align:right">هي الأنسب لنقل البيانات</td></tr>
<tr><td align="right" style="text-align:right"><b>حركة منتظمة على فترات ثابتة</b> (Beaconing)</td><td align="right" style="text-align:right">برمجية تتصل بخادمها بجدول منتظم</td></tr>
<tr><td align="right" style="text-align:right"><b>ارتفاع في NXDOMAIN</b></td><td align="right" style="text-align:right">أسماء مولدة آليًا (<b>DGA</b>) لا تُسجَّل كلها</td></tr>
<tr><td align="right" style="text-align:right"><b>نطاق حديث التسجيل أو بامتداد غير معتاد</b></td><td align="right" style="text-align:right">تفحصه بـ <code>whois</code> والسمعة</td></tr>
<tr><td align="right" style="text-align:right"><b>استعلامات مباشرة لخادم DNS خارجي</b></td><td align="right" style="text-align:right">تجاوز خادم المؤسسة لتفادي المراقبة</td></tr>
</tbody>
</table>

والمنهج الصحيح: **تجميع الاستعلامات حسب النطاق الأب** وعد الفريد منها، وحساب متوسط الطول، ثم فحص الأعلى منها يدويًا. وسنرى مثالًا على ذلك في قسم الأدوات.

<h2 dir="ltr" align="left" style="text-align:left">🛠 Commands &amp; Hands-on</h2>

### <a id="t1-13"></a>1.13 أدوات استعلام DNS والتحقق منه

الأمثلة التالية بنطاق `example.com` المخصص للتوثيق، وعناوين من الفئات المحجوزة للأمثلة (`192.0.2.x` و`2001:db8::`)، وكل مخرج هنا **توضيحي** لشرح الشكل.

**1) استعلام بسيط بـ `nslookup`:**

<div dir="ltr" align="left">

```bash
nslookup example.com               # default A record
nslookup -type=MX example.com      # mail servers
nslookup -type=TXT example.com     # TXT records
nslookup example.com 8.8.8.8       # ask a specific resolver
nslookup 192.0.2.10                # reverse lookup (PTR)
```

</div>

**2) استعلام تفصيلي بـ `dig`:**

<div dir="ltr" align="left">

```bash
dig example.com                    # A record + full response
dig example.com AAAA +short        # only the value
dig MX example.com                 # mail records
dig @1.1.1.1 example.com           # use a chosen resolver
dig +trace example.com             # follow root > TLD > auth
dig -x 192.0.2.10                  # reverse lookup
dig example.com NS +short          # name servers
```

</div>

وشكل المخرج المختصر لسجل A (توضيحي):

<div dir="ltr" align="left">

```text
;; ANSWER SECTION:
example.com.   300   IN   A   192.0.2.10
;; Query time: 24 msec
;; SERVER: 192.0.2.53#53(192.0.2.53)
```

</div>

والقراءة: الاسم، ثم **TTL** (300 ثانية)، ثم الفئة `IN` (Internet)، ثم **النوع** `A`، ثم **القيمة**. ويظهر في الأسفل **الخادم الذي أجاب** وزمن الاستعلام.

**3) بيانات التسجيل بـ `whois`:**

<div dir="ltr" align="left">

```bash
whois example.com
```

</div>

وأهم الحقول للمحلل: **Creation Date** (تاريخ الإنشاء)، و**Registrar**، و**Name Server**، و**Updated Date**. وكثير من النطاقات تُخفي بيانات المالك (Privacy) فالتركيز على **التواريخ** وخوادم الأسماء.

**4) التعداد بـ `dnsenum` (على نطاق مصرح لك به فقط):**

<div dir="ltr" align="left">

```bash
dnsenum example.com                       # basic enumeration
dnsenum --enum example.com                # shortcut options
dnsenum -f subdomains.txt example.com     # brute force from list
dnsenum --dnsserver 192.0.2.53 example.com
```

</div>

وتُظهر الأداة خوادم الأسماء وسجلات A وMX، وتحاول **Zone Transfer** على كل خادم، وتخمن نطاقات فرعية من قائمة كلمات. وهذه النتائج هي **ما يراه المهاجم** عن مؤسستك.

**5) الذاكرة المحلية وملف hosts:**

<div dir="ltr" align="left">

```text
:: Windows (cmd as administrator)
ipconfig /displaydns          show the local DNS cache
ipconfig /flushdns            clear the local DNS cache
type C:\Windows\System32\drivers\etc\hosts

:: Linux
resolvectl query example.com  query via systemd-resolved
resolvectl flush-caches       clear the cache
cat /etc/resolv.conf          which resolver is configured
cat /etc/hosts
```

</div>

**6) تحليل سجل DNS لاكتشاف أنماط مشبوهة:**

لنفترض ملف استعلامات بسيط بصيغة `الوقت  العميل  الاسم  النوع`:

<div dir="ltr" align="left">

```text
10:01:02 10.0.0.15 www.example.com A
10:01:07 10.0.0.15 mail.example.com A
10:02:11 10.0.0.23 dGhpcy1pcy1zZWNyZXQ1.c2.badsite.test TXT
10:02:16 10.0.0.23 aGVsbG8tdGhlcmUtZnJpZW5k.c2.badsite.test TXT
10:02:21 10.0.0.23 cGF5bG9hZC1jaHVuay0wMDM.c2.badsite.test TXT
```

</div>

وبهذه الأوامر نجمع عدد الاستعلامات الفريدة لكل نطاق أب (آخر مقطعين) ونحسب طول الاسم:

<div dir="ltr" align="left">

```bash
# count queries per parent domain (last two labels)
awk '{n=split($3,a,"."); print a[n-1]"."a[n]}' dns.log \
  | sort | uniq -c | sort -rn

# show the longest query names
awk '{print length($3), $2, $3}' dns.log | sort -rn | head

# only TXT queries per client
awk '$4=="TXT"{print $2}' dns.log | sort | uniq -c | sort -rn
```

</div>

والنتيجة المتوقعة في هذا المثال: النطاق `badsite.test` يظهر بعدد كبير من الاستعلامات **TXT** القادمة من جهاز واحد (`10.0.0.23`) بأسماء طويلة عشوائية، وهي **أنموذج DNS Tunneling** يستحق التحقيق.

### <a id="t1-14"></a>1.14 جدول مرجعي: سجلات DNS والأدوات (Cheatsheet)

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الأمر أو السجل</th><th align="right" style="text-align:right">الاستخدام</th><th align="right" style="text-align:right">مثال عملي</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><code>nslookup &lt;name&gt;</code></td><td align="right" style="text-align:right">استعلام سريع عن سجل A</td><td dir="ltr" align="left" style="text-align:left"><code>nslookup example.com</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>nslookup -type=MX &lt;name&gt;</code></td><td align="right" style="text-align:right">معرفة خوادم البريد</td><td dir="ltr" align="left" style="text-align:left"><code>nslookup -type=MX example.com</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>nslookup &lt;name&gt; &lt;server&gt;</code></td><td align="right" style="text-align:right">اختبار خادم محدد</td><td dir="ltr" align="left" style="text-align:left"><code>nslookup example.com 8.8.8.8</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>dig &lt;name&gt; &lt;type&gt;</code></td><td align="right" style="text-align:right">استجابة تفصيلية</td><td dir="ltr" align="left" style="text-align:left"><code>dig example.com AAAA</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>dig +short</code></td><td align="right" style="text-align:right">القيمة فقط</td><td dir="ltr" align="left" style="text-align:left"><code>dig example.com +short</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>dig @&lt;server&gt;</code></td><td align="right" style="text-align:right">سؤال خادم محدد</td><td dir="ltr" align="left" style="text-align:left"><code>dig @1.1.1.1 example.com</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>dig +trace</code></td><td align="right" style="text-align:right">تتبع الرحلة من الجذر</td><td dir="ltr" align="left" style="text-align:left"><code>dig +trace example.com</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>dig -x &lt;ip&gt;</code></td><td align="right" style="text-align:right">بحث عكسي PTR</td><td dir="ltr" align="left" style="text-align:left"><code>dig -x 192.0.2.10</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>whois &lt;domain&gt;</code></td><td align="right" style="text-align:right">بيانات التسجيل والتواريخ</td><td dir="ltr" align="left" style="text-align:left"><code>whois example.com</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>dnsenum &lt;domain&gt;</code></td><td align="right" style="text-align:right">تعداد سجلات ونطاقات فرعية</td><td dir="ltr" align="left" style="text-align:left"><code>dnsenum example.com</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>ipconfig /displaydns</code></td><td align="right" style="text-align:right">عرض ذاكرة DNS (ويندوز)</td><td dir="ltr" align="left" style="text-align:left"><code>ipconfig /displaydns</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>ipconfig /flushdns</code></td><td align="right" style="text-align:right">مسح الذاكرة المحلية</td><td dir="ltr" align="left" style="text-align:left"><code>ipconfig /flushdns</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>resolvectl flush-caches</code></td><td align="right" style="text-align:right">مسح الذاكرة (لينكس)</td><td dir="ltr" align="left" style="text-align:left"><code>resolvectl flush-caches</code></td></tr>
<tr><td align="right" style="text-align:right">سجل A / AAAA</td><td align="right" style="text-align:right">عنوان IPv4 / IPv6</td><td dir="ltr" align="left" style="text-align:left"><code>192.0.2.10</code> / <code>2001:db8::10</code></td></tr>
<tr><td align="right" style="text-align:right">سجل CNAME</td><td align="right" style="text-align:right">اسم مستعار</td><td dir="ltr" align="left" style="text-align:left"><code>www → example.com</code></td></tr>
<tr><td align="right" style="text-align:right">سجل MX</td><td align="right" style="text-align:right">خادم البريد وأولويته</td><td dir="ltr" align="left" style="text-align:left"><code>10 mail.example.com</code></td></tr>
<tr><td align="right" style="text-align:right">سجل TXT</td><td align="right" style="text-align:right">SPF وDKIM وإثبات الملكية</td><td dir="ltr" align="left" style="text-align:left"><code>v=spf1 ... ~all</code></td></tr>
<tr><td align="right" style="text-align:right">سجل NS</td><td align="right" style="text-align:right">خوادم الأسماء</td><td dir="ltr" align="left" style="text-align:left"><code>ns1.example.com</code></td></tr>
<tr><td align="right" style="text-align:right">سجل PTR</td><td align="right" style="text-align:right">من العنوان إلى الاسم</td><td dir="ltr" align="left" style="text-align:left"><code>10.2.0.192.in-addr.arpa</code></td></tr>
</tbody>
</table>

<h2 dir="ltr" align="left" style="text-align:left">🖼 Practical Scenarios</h2>

### <a id="t1-15"></a>1.15 سيناريو: جهاز يرسل استعلامات DNS غريبة

ينبه نظام المراقبة على جهاز داخلي (`10.0.0.23`) أرسل خلال ساعة **آلاف** الاستعلامات إلى نطاق واحد غير معروف. خطوات المحلل:

1. **تجميع الاستعلامات** حسب النطاق الأب: يظهر نطاق واحد بعدد فريد ضخم من النطاقات الفرعية، وأسماؤها طويلة وعشوائية، ونوعها **TXT**.
2. **فحص النطاق:** `whois` يبين أنه سُجّل منذ **أيام قليلة**، وخوادم الأسماء تابعة لجهة غير معروفة، و`dig` يظهر **TTL** قصيرًا جدًا.
3. **ربط الاستعلامات بالعملية:** من سجلات **Sysmon (حدث 22)** على الجهاز نعرف أي برنامج أرسلها، فنجد عملية غير مألوفة تعمل من مجلد مؤقت.
4. **التقييم:** نمط الطول والتواتر المنتظم وTXT يطابق **DNS Tunneling** كقناة C2 أو تهريب بيانات.
5. **الاحتواء:** عزل الجهاز عن الشبكة، وحجب النطاق على خادم DNS المؤسسي والجدار الناري، ومنع الاستعلامات الصادرة المباشرة عن خادم DNS المؤسسي.
6. **التوسع:** البحث عن أجهزة أخرى استعلمت عن **نفس النطاق**، وتحديد **حجم البيانات** التي قد تكون خرجت، والتوثيق.

والدرس: **DNS مصدر كشف قوي** لأن البرمجية الخبيثة لا تستطيع الاتصال بخادمها دون أن تسأل عنه.

### <a id="t1-16"></a>1.16 كيف تتعامل مع أسئلة الغرفة بمنهجية

تتضمن غرفة المنصة أسئلة تطبيقية على سجلات DNS وقيم TTL وخوادم DNS. ولا تُذكر هنا حلول، بل **طريقة العمل**:

1. **حدد نوع المطلوب أولًا:** هل السؤال عن نوع سجل، أم عن مدة صلاحية، أم عن جهة معينة؟
2. **اربط نوع المعلومة بنوع السجل:** عنوان IPv4 يوحي بسجل A، وعنوان IPv6 بـ AAAA، واسم مستعار بـ CNAME، وبريد بـ MX، ونص تحقق بـ TXT.
3. **اقرأ المخرج بدقة:** في ناتج `nslookup` و`dig` ابحث عن العمود المطلوب (النوع أو القيمة أو TTL) ولا تعتمد على التخمين.
4. **ميّز بين الخوادم:** الخادم الذي **يبحث نيابةً عنك** (Recursive) غير الخادم **صاحب السجل الأصلي** (Authoritative).
5. **جرّب بنفسك:** `nslookup` و`dig` في أي بيئة مسموح بها لترى الصورة الحقيقية.

<h2 dir="ltr" align="left" style="text-align:left">📝 Practical Takeaways</h2>

- **DNS** يحول الأسماء إلى عناوين IP، ويعمل على المنفذ **53** (UDP وTCP)، وقد صُمم دون تشفير أو تحقق من الهوية.
- الاسم يُقرأ من **اليمين**: Root ثم **TLD** ثم **SLD** ثم **Subdomain**. وLabel بحد أقصى 63 حرفًا، والاسم الكامل بحد أقصى 253.
- **gTLD** لنوع النشاط و**ccTLD** للدول.
- السجلات: **A** (IPv4)، **AAAA** (IPv6)، **CNAME** (اسم مستعار)، **MX** (بريد وأولويته)، **TXT** (نص: SPF/DKIM/DMARC/تحقق)، **NS** (خوادم الأسماء)، **PTR** (عكسي).
- الرحلة: ذاكرة محلية ثم **Recursive** ثم **Root** ثم **TLD** ثم **Authoritative**، وتُخزَّن النتيجة بحسب **TTL**.
- **DNSSEC** يضمن صحة الجواب ولا يشفره، و**DoH/DoT** يشفران الاتصال بالمحلل التكراري.
- أدوات الاستطلاع: `nslookup` و`dig` و`whois` و`dnsenum`، ولا تُستعمل للتعداد إلا بتصريح.

## 🛡 خلاصة المحلل الأمني (SOC Takeaways)

- **DNS قناة مراقبة ثمينة:** كل برمجية خبيثة تحتاج الاستعلام عن خادمها، وغالبًا لا يحجبه الجدار الناري.
- **مؤشرات DNS Tunneling:** Label طويل عشوائي، عدد ضخم من النطاقات الفرعية الفريدة لنطاق واحد، كثرة TXT، حركة منتظمة (Beaconing)، وارتفاع NXDOMAIN (DGA).
- **افحص عمر النطاق** بـ `whois`، فالنطاقات حديثة التسجيل بامتدادات رخيصة من أكثر مصادر الخطر.
- اربط استعلام DNS **بالعملية والجهاز** (Sysmon 22، وZeek `dns.log`) لتعرف المصدر الفعلي.
- اقرأ الروابط **من اليمين**: `login.example.com.attacker.net` نطاقه الحقيقي `attacker.net`.
- افحص **ملف hosts** وإعدادات DNS في الراوتر عند الاشتباه في التوجيه.
- فعّل **DNSSEC** وقفل النطاق وقيّد Zone Transfer، وضيّق الاستعلامات الصادرة على خوادم DNS المؤسسية.

<br>

<a id="room-2"></a>
<table align="center" width="100%"><tr><td align="right" style="text-align:right">

### 🚪 الغرفة 2: HTTP in Detail (بروتوكول HTTP بالتفصيل)

</td></tr></table>

<h1 dir="ltr" align="left" style="text-align:left">HTTP in Detail</h1>

### <a id="t2-1"></a>2.1 التعريف بالغرفة وأهدافها

بعد أن عرف المتصفح عنوان الخادم عبر DNS، يأتي السؤال التالي: **بأي لغة يتخاطب مع الخادم؟** هذه اللغة هي **HTTP (HyperText Transfer Protocol)**. وكل صفحة وصورة وتسجيل دخول ونموذج تملؤه تمر عبره، ولذلك فهو المكان الأول الذي ينظر فيه المحلل الأمني حين يفحص هجومًا على تطبيق ويب.

ومن أهداف الغرفة أن نكون قادرين في نهايتها على:
- شرح ما هو **HTTP** وما الفرق بينه وبين **HTTPS**، وتعرّف إصداراته (1.1 و2 و3).
- تفكيك عنوان **URL** إلى أجزائه (Scheme وHost وPort وPath وQuery وFragment).
- قراءة **طلب HTTP** و**استجابته** سطرًا سطرًا.
- فهم أهم **الرؤوس (Headers)** في الطلب والاستجابة.
- التفريق بين **الطرق (Methods)** مثل GET وPOST وPUT وDELETE.
- قراءة **رموز الحالة (Status Codes)** وتصنيفاتها.
- فهم **الكوكيز (Cookies)** وكيف يتذكرك الموقع، والفرق بينها وبين تخزين المتصفح (Web Storage).
- إرسال الطلبات بأداة `curl` وتحليل سجلات خادم الويب.

<h2 dir="ltr" align="left" style="text-align:left">📌 Concepts Covered</h2>

### <a id="t2-2"></a>2.2 ما هو HTTP وما هو HTTPS

**HTTP** هو البروتوكول الذي يستخدمه **العميل (Client)**، أي المتصفح أو أي أداة، لطلب الموارد من **خادم الويب (Web Server)**. ويعمل بنموذج بسيط: **طلب (Request) ثم استجابة (Response)**. العميل يبدأ دائمًا، والخادم يرد.

وله خاصيتان مهمتان:
- **Stateless (بلا ذاكرة):** كل طلب مستقل، ولا يتذكر الخادم من أنت بين طلب وآخر. ولهذا اخترعت **الكوكيز** لاحقًا.
- **نص مقروء (Plain Text):** رسائله نصوص يمكن لأي أحد على الطريق قراءتها وتعديلها إذا لم تكن مشفرة.

والفرق بين النسختين:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">وجه المقارنة</th><th align="right" style="text-align:right">HTTP</th><th align="right" style="text-align:right">HTTPS</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><b>المعنى</b></td><td dir="ltr" align="left" style="text-align:left">HyperText Transfer Protocol</td><td dir="ltr" align="left" style="text-align:left">HTTP <b>Secure</b></td></tr>
<tr><td align="right" style="text-align:right"><b>المنفذ الافتراضي</b></td><td align="right" style="text-align:right"><code>80</code></td><td align="right" style="text-align:right"><code>443</code></td></tr>
<tr><td align="right" style="text-align:right"><b>التشفير</b></td><td align="right" style="text-align:right">لا يوجد</td><td align="right" style="text-align:right">مشفر بـ <b>TLS</b></td></tr>
<tr><td align="right" style="text-align:right"><b>الشهادة</b></td><td align="right" style="text-align:right">لا تحتاج</td><td align="right" style="text-align:right">تحتاج <b>شهادة رقمية</b> من جهة موثوقة</td></tr>
<tr><td align="right" style="text-align:right"><b>قراءة البيانات في الطريق</b></td><td align="right" style="text-align:right">ممكنة (كلمات المرور تظهر نصًا)</td><td align="right" style="text-align:right">غير ممكنة</td></tr>
<tr><td align="right" style="text-align:right"><b>كشف التلاعب</b></td><td align="right" style="text-align:right">لا</td><td align="right" style="text-align:right">نعم (سلامة البيانات)</td></tr>
<tr><td align="right" style="text-align:right"><b>التحقق من هوية الخادم</b></td><td align="right" style="text-align:right">لا</td><td align="right" style="text-align:right">نعم عبر الشهادة</td></tr>
</tbody>
</table>

و**HTTPS ليس بروتوكولًا جديدًا**، بل هو HTTP نفسه داخل نفق مشفر. ولاحظ أن القفل الأخضر في المتصفح **يعني أن الاتصال مشفر فقط، ولا يعني أن الموقع آمن أو غير خبيث**، فمواقع التصيد كثيرًا ما تستخدم HTTPS أيضًا.

### <a id="t2-3"></a>2.3 إصدارات HTTP (1.1 و2 و3)

لم يبقَ HTTP على حاله منذ ظهوره، وتغيرت طريقة **نقل** الرسائل مع بقاء **معناها** كما هو: نفس الطرق (GET وPOST...) ونفس رموز الحالة ونفس الرؤوس. أهم الإصدارات:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الإصدار</th><th align="right" style="text-align:right">الصيغة</th><th align="right" style="text-align:right">أبرز ما يميزه</th><th align="right" style="text-align:right">النقل</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>HTTP/1.0</b></td><td align="right" style="text-align:right">نصي</td><td align="right" style="text-align:right">اتصال جديد لكل طلب (بطيء)</td><td dir="ltr" align="left" style="text-align:left">TCP</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>HTTP/1.1</b></td><td align="right" style="text-align:right"><b>نصي مقروء</b></td><td align="right" style="text-align:right">اتصال دائم (Keep-Alive)، ورأس <b>Host</b> لدعم استضافة مواقع متعددة، وما زال واسع الاستخدام</td><td dir="ltr" align="left" style="text-align:left">TCP</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>HTTP/2</b></td><td align="right" style="text-align:right"><b>ثنائي (Binary)</b></td><td align="right" style="text-align:right"><b>Multiplexing</b>: عدة طلبات متزامنة على اتصال واحد، وضغط للرؤوس (HPACK)</td><td align="right" style="text-align:right">TCP + TLS (عمليًا في المتصفحات)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>HTTP/3</b></td><td align="right" style="text-align:right">ثنائي</td><td align="right" style="text-align:right">يعمل فوق <b>QUIC</b> بدل TCP، ويدمج TLS 1.3، ويقلل التأخير عند ضياع الحزم</td><td align="right" style="text-align:right"><b>UDP</b> (المنفذ 443)</td></tr>
</tbody>
</table>

والنقاط المهمة للمحلل الأمني:
- ما نكتبه في هذه الغرفة من أسطر نصية (`GET / HTTP/1.1`) هو **شكل 1.1**. أما في HTTP/2 وHTTP/3 فالرسائل **ثنائية**، فلا تُقرأ بالعين في التقاط الشبكة وتحتاج أدوات تفكها (مثل Wireshark أو أدوات المتصفح).
- **المفاهيم لا تتغير:** الطريقة والمسار والرؤوس ورمز الحالة موجودة في كل الإصدارات، ولذلك تبقى هذه الغرفة صالحة.
- في سجلات الخادم قد ترى `HTTP/2.0` أو `HTTP/1.1` في سطر الطلب، وهذا يخبرك أي إصدار استخدمه العميل. والأدوات الآلية الضعيفة غالبًا تستخدم **1.0 أو 1.1**، فاختلاف الإصدار قد يكون مؤشرًا إضافيًا.
- HTTP/3 يعمل على **UDP/443**، فمن يراقب **TCP/443 فقط** قد تفوته حركة مرور الويب المشفرة بـ QUIC.

### <a id="t2-4"></a>2.4 تشريح عنوان URL

**URL (Uniform Resource Locator)** هو العنوان الكامل الذي يخبر المتصفح **أين** المورد و**كيف** يصل إليه. وله أجزاء كل منها له وظيفة:

<p align="center">
  <img src="images/url-anatomy.png" width="700" alt="تشريح عنوان URL"><br>
  <sub>أجزاء الرابط: Scheme وUser وHost وPort وPath وQuery String وFragment</sub>
</p>

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الجزء</th><th align="right" style="text-align:right">الوظيفة</th><th align="right" style="text-align:right">مثال</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Scheme</b></td><td align="right" style="text-align:right">البروتوكول المستخدم للوصول</td><td align="right" style="text-align:right"><code>http</code> و<code>https</code> و<code>ftp</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>User</b></td><td align="right" style="text-align:right">بيانات دخول مدمجة في الرابط (نادرة وخطرة)</td><td dir="ltr" align="left" style="text-align:left"><code>user:pass@</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Host</b></td><td align="right" style="text-align:right">اسم النطاق أو عنوان IP للخادم</td><td dir="ltr" align="left" style="text-align:left"><code>shop.example.com</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Port</b></td><td align="right" style="text-align:right">المنفذ، ويُحذف إن كان الافتراضي</td><td align="right" style="text-align:right"><code>:8080</code> (من 1 إلى 65535)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Path</b></td><td align="right" style="text-align:right">اسم الملف أو المسار على الخادم</td><td dir="ltr" align="left" style="text-align:left"><code>/products/list</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Query String</b></td><td align="right" style="text-align:right">معلومات إضافية تبدأ بـ <code>?</code> وتُفصل بـ <code>&amp;</code></td><td dir="ltr" align="left" style="text-align:left"><code>?id=5&amp;sort=asc</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Fragment</b></td><td align="right" style="text-align:right">موضع داخل الصفحة، يبقى عند المتصفح ولا يُرسل للخادم</td><td dir="ltr" align="left" style="text-align:left"><code>#reviews</code></td></tr>
</tbody>
</table>

مثال كامل بقيمنا الخاصة:

<div dir="ltr" align="left">

```text
https://admin:secret@shop.example.com:8443/items/view?id=7&lang=ar#price
<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right"></th><th align="right" style="text-align:right"></th><th align="right" style="text-align:right"></th><th align="right" style="text-align:right"></th><th align="right" style="text-align:right"></th><th align="right" style="text-align:right"></th></tr></thead>
<tbody>
</tbody>
</table>
Scheme  User         Host              Port Path       Query       Fragment
```

</div>

ملاحظات مهمة:
- الـ **Fragment** لا يصل إلى الخادم أبدًا، فلن تراه في سجلات الخادم.
- الرموز الخاصة تُشفَّر بنمط **URL Encoding** (مثل المسافة `%20` وعلامة `/` تكون `%2F`)، ويستخدمها المهاجمون لإخفاء الحمولات.
- وجود **User** في الرابط (`user:pass@host`) أسلوب قديم، ويُستخدم اليوم **للخداع**: الرابط `https://bank.com@evil.net` يبدو أنه البنك لكن **المضيف الحقيقي هو `evil.net`**.

### <a id="t2-5"></a>2.5 بنية طلب HTTP

الطلب رسالة نصية من ثلاثة أجزاء:

1. **سطر الطلب (Request Line):** الطريقة، ثم المسار، ثم إصدار البروتوكول.
2. **الرؤوس (Headers):** أسطر `الاسم: القيمة` تصف الطلب.
3. **الجسم (Body):** اختياري، يحمل البيانات المرسلة (في POST مثلًا).

<div dir="ltr" align="left">

```http
GET /items/view?id=7 HTTP/1.1
Host: shop.example.com
User-Agent: Mozilla/5.0 (X11; Linux x86_64) Firefox/120.0
Accept: text/html
Accept-Encoding: gzip
Referer: https://shop.example.com/items
Cookie: session=abc123

```

</div>

وهذا الطلب ينتهي **بسطر فارغ** يعلن للخادم نهاية الرؤوس. والرأس **Host** هو الوحيد الإلزامي تقريبًا في HTTP/1.1، لأن الخادم الواحد قد يستضيف مواقع كثيرة ويحتاج أن يعرف أيها تريد.

### <a id="t2-6"></a>2.6 بنية استجابة HTTP وتفكيكها سطرًا سطرًا

الاستجابة أيضًا من ثلاثة أجزاء: **سطر الحالة (Status Line)**، ثم **رؤوس الاستجابة**، ثم **الجسم (Body)** وهو المحتوى المطلوب.

الرسم التالي يجمع **الطلب والاستجابة** جنبًا إلى جنب، لترى أن لهما نفس الشكل: سطر البداية ثم الرؤوس ثم سطر فارغ ثم الجسم.

<p align="center">
  <img src="images/http-anatomy.svg" width="820" alt="تشريح طلب واستجابة HTTP"><br>
  <sub>الطلب والاستجابة مع تسمية كل سطر ووظيفته</sub>
</p>

<div dir="ltr" align="left">

```http
HTTP/1.1 200 OK
Server: nginx/1.25.0
Date: Mon, 12 Oct 2026 10:15:00 GMT
Content-Type: text/html; charset=UTF-8
Content-Length: 1256

<!DOCTYPE html>
<html> ... </html>
```

</div>

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">السطر</th><th align="right" style="text-align:right">الاسم</th><th align="right" style="text-align:right">ماذا يعني</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right">1</td><td dir="ltr" align="left" style="text-align:left"><b>Status Line</b></td><td align="right" style="text-align:right">إصدار البروتوكول ثم <b>رمز الحالة</b> وعبارته (<code>200 OK</code> نجاح)</td></tr>
<tr><td align="right" style="text-align:right">2</td><td dir="ltr" align="left" style="text-align:left"><b>Server</b></td><td align="right" style="text-align:right">برنامج الخادم وإصداره (<code>nginx/1.25.0</code>)</td></tr>
<tr><td align="right" style="text-align:right">3</td><td dir="ltr" align="left" style="text-align:left"><b>Date</b></td><td align="right" style="text-align:right">تاريخ ووقت ومنطقة الخادم الزمنية</td></tr>
<tr><td align="right" style="text-align:right">4</td><td dir="ltr" align="left" style="text-align:left"><b>Content-Type</b></td><td align="right" style="text-align:right">نوع المحتوى: HTML أو صورة أو PDF أو JSON...</td></tr>
<tr><td align="right" style="text-align:right">5</td><td dir="ltr" align="left" style="text-align:left"><b>Content-Length</b></td><td align="right" style="text-align:right">حجم الجسم بالبايت، للتأكد من وصوله كاملًا</td></tr>
<tr><td align="right" style="text-align:right">6</td><td align="right" style="text-align:right"><b>سطر فارغ</b></td><td align="right" style="text-align:right">يفصل الرؤوس عن الجسم</td></tr>
<tr><td align="right" style="text-align:right">7 وما بعده</td><td dir="ltr" align="left" style="text-align:left"><b>Body</b></td><td align="right" style="text-align:right">البيانات الفعلية، مثل كود الصفحة</td></tr>
</tbody>
</table>

وللمحلل الأمني ملاحظة: رأس **Server** يكشف **اسم الخادم وإصداره**، وهذا يفيد المهاجم في البحث عن ثغرات هذا الإصدار، ولذلك يُنصح بإخفائه أو تقليله.

### <a id="t2-7"></a>2.7 رؤوس HTTP (Headers)

**الرؤوس** بيانات إضافية تصاحب الطلب أو الاستجابة. قد لا تكون إلزامية لإنشاء طلب، لكنها ضرورية لعمل المواقع بشكل صحيح.

**رؤوس الطلب الشائعة (من العميل إلى الخادم):**

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الرأس</th><th align="right" style="text-align:right">وظيفته</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Host</b></td><td align="right" style="text-align:right">اسم الموقع المطلوب (مهم عند استضافة مواقع كثيرة على خادم واحد)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>User-Agent</b></td><td align="right" style="text-align:right">نوع المتصفح أو الأداة وإصدارها، ليجهّز الخادم محتوى مناسبًا</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Referer</b></td><td align="right" style="text-align:right">الصفحة التي جئت منها إلى هذا الرابط (والاسم مكتوب هكذا بخطأ إملائي تاريخي)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Accept-Encoding</b></td><td align="right" style="text-align:right">أنواع الضغط التي يدعمها المتصفح (<code>gzip</code> وغيره)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Content-Length</b></td><td align="right" style="text-align:right">حجم البيانات المرسلة، كما في نماذج POST</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Content-Type</b></td><td align="right" style="text-align:right">نوع البيانات المرسلة في الجسم</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Cookie</b></td><td align="right" style="text-align:right">الكوكيز المخزنة التي يرسلها المتصفح ليتعرف الخادم عليك</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Authorization</b></td><td align="right" style="text-align:right">بيانات المصادقة (مثل Bearer Token)</td></tr>
</tbody>
</table>

**رؤوس الاستجابة الشائعة (من الخادم إلى العميل):**

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الرأس</th><th align="right" style="text-align:right">وظيفته</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Set-Cookie</b></td><td align="right" style="text-align:right">يأمر المتصفح بتخزين كوكي ويرسله لاحقًا مع كل طلب</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Cache-Control</b></td><td align="right" style="text-align:right">كم يخزن المتصفح الاستجابة قبل طلبها مجددًا</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Content-Type</b></td><td align="right" style="text-align:right">نوع البيانات (HTML وCSS وJS وصور وPDF) ليعالجها المتصفح بالشكل الصحيح</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Content-Encoding</b></td><td align="right" style="text-align:right">طريقة الضغط المستخدمة لتقليل الحجم</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Server</b></td><td align="right" style="text-align:right">برنامج الخادم وإصداره</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Location</b></td><td align="right" style="text-align:right">عنوان التحويل عند رموز 3xx</td></tr>
</tbody>
</table>

### <a id="t2-8"></a>2.8 طرق HTTP (Methods)

**الطريقة (Method)** تخبر الخادم **ماذا تريد أن تفعل بالمورد**.

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الطريقة</th><th align="right" style="text-align:right">الغرض</th><th align="right" style="text-align:right">أين تظهر البيانات</th><th align="right" style="text-align:right">مثال</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>GET</b></td><td align="right" style="text-align:right"><b>جلب</b> مورد</td><td align="right" style="text-align:right">في الرابط (Query String)</td><td align="right" style="text-align:right">فتح صفحة، <code>GET /items?id=7</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>POST</b></td><td align="right" style="text-align:right"><b>إرسال</b> بيانات لإنشاء شيء أو معالجته</td><td align="right" style="text-align:right">في <b>الجسم (Body)</b></td><td align="right" style="text-align:right">تسجيل الدخول، تعبئة نموذج</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>PUT</b></td><td align="right" style="text-align:right"><b>استبدال أو تحديث</b> مورد موجود</td><td align="right" style="text-align:right">في الجسم</td><td align="right" style="text-align:right">تعديل بيانات حساب</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DELETE</b></td><td align="right" style="text-align:right"><b>حذف</b> مورد</td><td align="right" style="text-align:right">غالبًا في المسار</td><td dir="ltr" align="left" style="text-align:left"><code>DELETE /items/7</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>PATCH</b></td><td align="right" style="text-align:right">تعديل <b>جزء</b> من المورد</td><td align="right" style="text-align:right">في الجسم</td><td align="right" style="text-align:right">تغيير حقل واحد</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>HEAD</b></td><td align="right" style="text-align:right">مثل GET لكن <b>الرؤوس فقط</b> بلا جسم</td><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right">فحص وجود مورد وحجمه</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>OPTIONS</b></td><td align="right" style="text-align:right">سؤال الخادم عن <b>الطرق المسموحة</b></td><td align="right" style="text-align:right">—</td><td align="right" style="text-align:right">فحص CORS</td></tr>
</tbody>
</table>

أمثلة على الشكل:

<div dir="ltr" align="left">

```http
POST /login HTTP/1.1
Host: shop.example.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 29

username=ali&password=Pass123
```

</div>

وهنا نقطة مهمة: **لا ترسل بيانات حساسة بـ GET**، لأن الرابط يُخزَّن في سجل المتصفح وسجلات الخادم والوسطاء. أما POST فيضعها في الجسم، لكنه **لا يشفرها** بنفسه، فالتشفير يأتي من HTTPS.

### <a id="t2-9"></a>2.9 رموز الحالة (Status Codes)

رمز الحالة رقم من **ثلاث خانات** يخبرك **ماذا حدث للطلب**. وتصنف بحسب الرقم الأول:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الفئة</th><th align="right" style="text-align:right">المعنى</th><th align="right" style="text-align:right">أمثلة</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>1xx</b></td><td align="right" style="text-align:right"><b>معلومات (Informational)</b>: الطلب استُلم وتتم المعالجة</td><td dir="ltr" align="left" style="text-align:left"><code>100 Continue</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>2xx</b></td><td align="right" style="text-align:right"><b>نجاح (Success)</b></td><td align="right" style="text-align:right"><code>200 OK</code>، <code>201 Created</code>، <code>204 No Content</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>3xx</b></td><td align="right" style="text-align:right"><b>إعادة توجيه (Redirection)</b></td><td align="right" style="text-align:right"><code>301 Moved Permanently</code>، <code>302 Found</code>، <code>304 Not Modified</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>4xx</b></td><td align="right" style="text-align:right"><b>خطأ من العميل (Client Error)</b></td><td align="right" style="text-align:right"><code>400</code>، <code>401</code>، <code>403</code>، <code>404</code>، <code>405</code>، <code>429</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>5xx</b></td><td align="right" style="text-align:right"><b>خطأ من الخادم (Server Error)</b></td><td align="right" style="text-align:right"><code>500</code>، <code>502</code>، <code>503</code>، <code>504</code></td></tr>
</tbody>
</table>

الرموز الأكثر شيوعًا:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الرمز</th><th align="right" style="text-align:right">الاسم</th><th align="right" style="text-align:right">المعنى العملي</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><b>200</b></td><td dir="ltr" align="left" style="text-align:left">OK</td><td align="right" style="text-align:right">نجح الطلب</td></tr>
<tr><td align="right" style="text-align:right"><b>201</b></td><td dir="ltr" align="left" style="text-align:left">Created</td><td align="right" style="text-align:right">أُنشئ مورد جديد (بعد POST مثلًا)</td></tr>
<tr><td align="right" style="text-align:right"><b>301</b></td><td dir="ltr" align="left" style="text-align:left">Moved Permanently</td><td align="right" style="text-align:right">انتقل المورد نهائيًا إلى رابط جديد</td></tr>
<tr><td align="right" style="text-align:right"><b>302</b></td><td dir="ltr" align="left" style="text-align:left">Found</td><td align="right" style="text-align:right">تحويل مؤقت</td></tr>
<tr><td align="right" style="text-align:right"><b>400</b></td><td dir="ltr" align="left" style="text-align:left">Bad Request</td><td align="right" style="text-align:right">الطلب مشوه أو غير مفهوم</td></tr>
<tr><td align="right" style="text-align:right"><b>401</b></td><td dir="ltr" align="left" style="text-align:left">Unauthorized</td><td align="right" style="text-align:right"><b>لم تسجل دخولك</b> أو بيانات الدخول خاطئة</td></tr>
<tr><td align="right" style="text-align:right"><b>403</b></td><td dir="ltr" align="left" style="text-align:left">Forbidden</td><td align="right" style="text-align:right"><b>مسجل لكن ليست لديك صلاحية</b></td></tr>
<tr><td align="right" style="text-align:right"><b>404</b></td><td dir="ltr" align="left" style="text-align:left">Not Found</td><td align="right" style="text-align:right">المورد غير موجود</td></tr>
<tr><td align="right" style="text-align:right"><b>405</b></td><td dir="ltr" align="left" style="text-align:left">Method Not Allowed</td><td align="right" style="text-align:right">الطريقة غير مسموحة لهذا المسار</td></tr>
<tr><td align="right" style="text-align:right"><b>429</b></td><td dir="ltr" align="left" style="text-align:left">Too Many Requests</td><td align="right" style="text-align:right">تجاوزت حد الطلبات (Rate Limit)</td></tr>
<tr><td align="right" style="text-align:right"><b>500</b></td><td dir="ltr" align="left" style="text-align:left">Internal Server Error</td><td align="right" style="text-align:right">عطل داخلي في الخادم</td></tr>
<tr><td align="right" style="text-align:right"><b>502</b></td><td dir="ltr" align="left" style="text-align:left">Bad Gateway</td><td align="right" style="text-align:right">خادم وسيط تلقى رد سيئًا من خادم خلفي</td></tr>
<tr><td align="right" style="text-align:right"><b>503</b></td><td dir="ltr" align="left" style="text-align:left">Service Unavailable</td><td align="right" style="text-align:right">الخدمة غير متاحة أو مثقلة</td></tr>
</tbody>
</table>

والفرق بين **401** و**403** يلتبس على الكثيرين: 401 تعني **"من أنت؟"** و403 تعني **"أعرفك لكن لا يحق لك"**.

### <a id="t2-10"></a>2.10 الكوكيز (Cookies)

بما أن HTTP لا يتذكر شيئًا، فكيف يعرف الموقع أنك سجلت دخولك قبل ثانية؟ بالـ **Cookie**: قطعة بيانات صغيرة **يعطيها الخادم للمتصفح**، فيعيدها المتصفح **مع كل طلب لاحق**.

<p align="center">
  <img src="images/http-cookies-flow.png" width="760" alt="رحلة الكوكي"><br>
  <sub>الخادم يرسل Set-Cookie بعد تسجيل الدخول، والمتصفح يعيد Cookie مع كل طلب لاحق</sub>
</p>

وخطواتها:
1. تسجل دخولك، فيتحقق الخادم من بياناتك.
2. يرد الخادم برأس `Set-Cookie: session=abc123` يحمل **معرّف الجلسة (Session ID)**.
3. يخزنه المتصفح، ويرسله في كل طلب لاحق برأس `Cookie: session=abc123`.
4. الخادم يبحث عن المعرّف فيعرف أنك أنت.

ومن استخدامات الكوكيز: **الجلسات** (البقاء مسجلًا)، و**التفضيلات** (اللغة والمظهر)، و**السلة** في المتاجر، و**التتبع** الإعلاني.

وتحمل الكوكي **سمات (Attributes)** تحميها:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">السمة</th><th align="right" style="text-align:right">الوظيفة</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Secure</b></td><td align="right" style="text-align:right">تُرسل عبر HTTPS فقط</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>HttpOnly</b></td><td align="right" style="text-align:right">لا يمكن قراءتها بـ JavaScript، فتحمي من سرقتها بـ XSS</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>SameSite</b></td><td align="right" style="text-align:right">تقيد إرسالها مع الطلبات من مواقع أخرى (<code>Strict</code> أو <code>Lax</code> أو <code>None</code>) وتحمي من CSRF</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Expires / Max-Age</b></td><td align="right" style="text-align:right">مدة الصلاحية</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Domain / Path</b></td><td align="right" style="text-align:right">النطاق والمسار الذي تُرسل إليه</td></tr>
</tbody>
</table>

مثال:

<div dir="ltr" align="left">

```http
Set-Cookie: session=abc123; Secure; HttpOnly;
            SameSite=Lax; Max-Age=3600; Path=/
```

</div>

وكوكي الجلسة **تعادل كلمة المرور** مدة صلاحيتها: من سرقها دخل حسابك دون كلمة المرور، وهذا هجوم **Session Hijacking**.

### <a id="t2-11"></a>2.11 الكوكيز مقابل تخزين المتصفح (Web Storage)

للمتصفح مكان آخر لحفظ البيانات غير الكوكيز، هو **Web Storage**، وله نوعان:
- **localStorage:** يبقى حتى يُمسح يدويًا، ويشترك فيه كل تبويبات الموقع.
- **sessionStorage:** يزول عند إغلاق التبويب.

والفرق الجوهري أن الكوكيز **يرسلها المتصفح تلقائيًا** مع كل طلب إلى الخادم، بينما Web Storage **يبقى في المتصفح** ولا يُرسل إلا إذا كتب كود JavaScript ذلك.

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">وجه المقارنة</th><th align="right" style="text-align:right"><b>Cookie</b></th><th align="right" style="text-align:right"><b>localStorage</b></th><th align="right" style="text-align:right"><b>sessionStorage</b></th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><b>تُرسل للخادم تلقائيًا</b></td><td align="right" style="text-align:right">نعم، مع كل طلب</td><td align="right" style="text-align:right">لا</td><td align="right" style="text-align:right">لا</td></tr>
<tr><td align="right" style="text-align:right"><b>الحجم التقريبي</b></td><td align="right" style="text-align:right">نحو 4 كيلوبايت</td><td align="right" style="text-align:right">نحو 5 ميجابايت</td><td align="right" style="text-align:right">نحو 5 ميجابايت</td></tr>
<tr><td align="right" style="text-align:right"><b>المدة</b></td><td align="right" style="text-align:right">بحسب <code>Expires</code> أو <code>Max-Age</code></td><td align="right" style="text-align:right">حتى تُمسح</td><td align="right" style="text-align:right">حتى يُغلق التبويب</td></tr>
<tr><td align="right" style="text-align:right"><b>يمكن حمايتها من JavaScript</b></td><td align="right" style="text-align:right"><b>نعم</b> بسمة <code>HttpOnly</code></td><td align="right" style="text-align:right"><b>لا</b>، أي سكربت في الصفحة يقرؤها</td><td align="right" style="text-align:right"><b>لا</b></td></tr>
<tr><td align="right" style="text-align:right"><b>من يكتبها</b></td><td align="right" style="text-align:right">الخادم أو JavaScript</td><td align="right" style="text-align:right">JavaScript فقط</td><td align="right" style="text-align:right">JavaScript فقط</td></tr>
</tbody>
</table>

ومن هنا قاعدة أمنية مهمة: **تخزين رمز الجلسة أو التوكن في localStorage أخطر** من تخزينه في كوكي `HttpOnly`، لأن أي ثغرة **XSS** تسمح للمهاجم بقراءته وسرقته مباشرة. وفي المقابل الكوكي ترسل تلقائيًا فتحتاج حماية من **CSRF** بسمة `SameSite`. ولا تحفظ في أي منهما كلمات المرور أو بيانات حساسة بلا حاجة.

والتنبيه: `HttpOnly` يمنع **القراءة** فقط، لكنه لا يمنع سكربت خبيثًا من **إرسال طلبات** باسم المستخدم من داخل صفحته.

### <a id="t2-12"></a>2.12 الزاوية الأمنية: HTTP من منظور المهاجم والمدافع

كل ما سبق من تفاصيل هو **سطح الهجوم** لتطبيقات الويب:

1. **التلاعب بالمعاملات (Parameter Tampering):** تغيير `?id=7` إلى `?id=8` لقراءة بيانات غيرك، وهي ثغرة **IDOR** (Insecure Direct Object Reference). الخادم السليم يتحقق أن المستخدم **يملك** المورد.
2. **التلاعب بالطريقة (Method Tampering):** تجربة `PUT` أو `DELETE` على مسار مصمم لـ GET، فإذا لم يقيّدها الخادم حدث تعديل أو حذف غير مصرح.
3. **سرقة الجلسة:** كوكي بلا `HttpOnly` و`Secure` قابلة للسرقة بـ XSS أو بالتنصت على HTTP.
4. **كشف المعلومات:** رأس `Server` ورسائل الخطأ المفصلة تعطي المهاجم معلومات.
5. **التخزين الخاطئ للجلسة:** وضع التوكن في `localStorage` يجعل سرقته بـ XSS أسهل (انظر الموضوع السابق).
6. **أدوات الاعتراض:** أدوات مثل **Burp Suite** و**OWASP ZAP** تقف بين المتصفح والخادم وتتيح تعديل أي طلب قبل إرساله، وهذا ما يفعله المهاجم، وما يستخدمه المدافع لاختبار تطبيقه.

وأنماط **رموز الحالة** في السجلات تحكي القصة:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">النمط في السجل</th><th align="right" style="text-align:right">التفسير المحتمل</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right">موجة من <b>401</b> على <code>/login</code> من عنوان واحد</td><td align="right" style="text-align:right">هجوم تخمين كلمات مرور (Brute Force)</td></tr>
<tr><td align="right" style="text-align:right">كثرة <b>404</b> من عنوان واحد على مسارات متنوعة</td><td align="right" style="text-align:right"><b>مسح</b> للمجلدات والملفات (Directory Scanning)</td></tr>
<tr><td align="right" style="text-align:right"><b>403</b> متكررة على مسارات الإدارة</td><td align="right" style="text-align:right">محاولات وصول غير مصرح</td></tr>
<tr><td align="right" style="text-align:right"><b>500</b> بعد إدخال رموز مثل <code>'</code> أو <code>&lt;</code></td><td align="right" style="text-align:right">مؤشر على <b>حقن</b> (Injection) ناجح جزئيًا</td></tr>
<tr><td align="right" style="text-align:right"><b>200</b> على <code>/admin</code> من عنوان خارجي</td><td align="right" style="text-align:right">قد يكون اختراقًا فعليًا، يحتاج فحصًا فوريًا</td></tr>
<tr><td align="right" style="text-align:right">قفزة في <b>429</b> و<b>503</b></td><td align="right" style="text-align:right">هجوم حجب خدمة (DoS) أو أتمتة</td></tr>
</tbody>
</table>

<h2 dir="ltr" align="left" style="text-align:left">🛠 Commands &amp; Hands-on</h2>

### <a id="t2-13"></a>2.13 أدوات إرسال الطلبات وتحليل السجلات

**1) الأداة `curl`:** عميل HTTP من سطر الأوامر، ممتاز لرؤية ما يجري فعلًا بلا متصفح.

<div dir="ltr" align="left">

```bash
curl http://example.com               # simple GET, body only
curl -I http://example.com            # HEAD: headers only
curl -v http://example.com            # verbose: request + response
curl -i http://example.com            # response with headers
curl -L http://example.com            # follow redirects
curl -I --http1.1 https://example.com # force HTTP/1.1
curl -I --http2 https://example.com   # try HTTP/2
curl -A "MyAgent/1.0" http://example.com   # custom User-Agent
curl -H "Accept: application/json" http://example.com
curl -o page.html http://example.com  # save body to a file
```

</div>

**2) طرق مختلفة وإرسال البيانات:**

<div dir="ltr" align="left">

```bash
# POST with form data
curl -X POST -d "username=ali&password=Pass123" \
     http://example.com/login

# POST with JSON
curl -X POST -H "Content-Type: application/json" \
     -d '{"name":"ali"}' http://example.com/api/users

# PUT and DELETE
curl -X PUT    -d "name=new" http://example.com/api/users/7
curl -X DELETE http://example.com/api/users/7

# Ask which methods are allowed
curl -X OPTIONS -i http://example.com/api/users
```

</div>

**3) الكوكيز مع `curl`:**

<div dir="ltr" align="left">

```bash
curl -c jar.txt http://example.com/login   # save cookies
curl -b jar.txt http://example.com/profile # send saved cookies
curl -b "session=abc123" http://example.com/profile
```

</div>

**4) قراءة الاستجابة فقط للرمز:**

<div dir="ltr" align="left">

```bash
curl -s -o /dev/null -w "%{http_code}\n" http://example.com
curl -s -o /dev/null -w "%{http_code} %{redirect_url}\n" \
     http://example.com/old
```

</div>

**5) تحليل سجل الوصول (Access Log):** خوادم مثل Apache وNginx تسجل كل طلب سطرًا واحدًا. وهذا الشكل الشائع (قيمنا للتوضيح):

<div dir="ltr" align="left">

```text
203.0.113.7 - - [12/Oct/2026:10:15:01 +0000] "POST /login
HTTP/1.1" 401 512 "-" "python-requests/2.31"
```

</div>

وحقوله: **عنوان العميل**، ثم الوقت، ثم **سطر الطلب** (الطريقة والمسار والإصدار)، ثم **رمز الحالة**، ثم الحجم، ثم **Referer**، ثم **User-Agent**. وبأدوات الشل نستخرج الأنماط:

<div dir="ltr" align="left">

```bash
# top client IPs
awk '{print $1}' access.log | sort | uniq -c | sort -rn | head

# count of each status code
awk '{print $9}' access.log | sort | uniq -c | sort -rn

# IPs that got many 401 (brute force)
awk '$9==401 {print $1}' access.log | sort | uniq -c \
  | sort -rn | head

# IPs scanning for missing files (404)
awk '$9==404 {print $1}' access.log | sort | uniq -c \
  | sort -rn | head

# non-browser user agents
grep -i -E "curl|python|sqlmap|nikto" access.log
```

</div>

### <a id="t2-14"></a>2.14 جدول مرجعي: HTTP والأدوات (Cheatsheet)

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">العنصر</th><th align="right" style="text-align:right">المعنى</th><th align="right" style="text-align:right">مثال</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl -I</code></td><td align="right" style="text-align:right">الرؤوس فقط (HEAD)</td><td dir="ltr" align="left" style="text-align:left"><code>curl -I http://example.com</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl -v</code></td><td align="right" style="text-align:right">عرض الطلب والاستجابة</td><td dir="ltr" align="left" style="text-align:left"><code>curl -v http://example.com</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl -L</code></td><td align="right" style="text-align:right">اتباع التحويلات</td><td dir="ltr" align="left" style="text-align:left"><code>curl -L http://example.com</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl --http1.1</code> / <code>--http2</code></td><td align="right" style="text-align:right">فرض إصدار HTTP</td><td dir="ltr" align="left" style="text-align:left"><code>curl -I --http2 &lt;url&gt;</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl -X &lt;M&gt;</code></td><td align="right" style="text-align:right">تحديد الطريقة</td><td dir="ltr" align="left" style="text-align:left"><code>curl -X DELETE &lt;url&gt;</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl -d</code></td><td align="right" style="text-align:right">إرسال بيانات في الجسم</td><td dir="ltr" align="left" style="text-align:left"><code>curl -d "a=1&amp;b=2" &lt;url&gt;</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl -H</code></td><td align="right" style="text-align:right">إضافة رأس</td><td dir="ltr" align="left" style="text-align:left"><code>curl -H "Accept: text/html" &lt;url&gt;</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl -A</code></td><td align="right" style="text-align:right">تغيير User-Agent</td><td dir="ltr" align="left" style="text-align:left"><code>curl -A "Agent/1.0" &lt;url&gt;</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl -b / -c</code></td><td align="right" style="text-align:right">إرسال / حفظ الكوكيز</td><td dir="ltr" align="left" style="text-align:left"><code>curl -b "s=1" &lt;url&gt;</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl -w</code></td><td align="right" style="text-align:right">طباعة قيم مثل رمز الحالة</td><td dir="ltr" align="left" style="text-align:left"><code>curl -w "%{http_code}" &lt;url&gt;</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">GET / POST</td><td align="right" style="text-align:right">جلب / إرسال</td><td align="right" style="text-align:right">البيانات في الرابط / في الجسم</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">PUT / PATCH</td><td align="right" style="text-align:right">استبدال / تعديل جزئي</td><td dir="ltr" align="left" style="text-align:left"><code>PUT /users/7</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">DELETE</td><td align="right" style="text-align:right">حذف</td><td dir="ltr" align="left" style="text-align:left"><code>DELETE /users/7</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">2xx / 3xx</td><td align="right" style="text-align:right">نجاح / تحويل</td><td align="right" style="text-align:right"><code>200</code> و<code>301</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">4xx / 5xx</td><td align="right" style="text-align:right">خطأ عميل / خطأ خادم</td><td align="right" style="text-align:right"><code>404</code> و<code>500</code></td></tr>
<tr><td align="right" style="text-align:right">401 / 403</td><td align="right" style="text-align:right">غير مسجل / غير مصرح</td><td align="right" style="text-align:right">من أنت؟ / لا يحق لك</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>Set-Cookie</code> / <code>Cookie</code></td><td align="right" style="text-align:right">الخادم يعطي / المتصفح يعيد</td><td dir="ltr" align="left" style="text-align:left"><code>session=abc123</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>HttpOnly</code> / <code>Secure</code></td><td align="right" style="text-align:right">منع JS / HTTPS فقط</td><td align="right" style="text-align:right">سمات الكوكي</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>localStorage</code></td><td align="right" style="text-align:right">تخزين بالمتصفح لا يُرسل تلقائيًا</td><td align="right" style="text-align:right">قابل للقراءة بـ XSS</td></tr>
</tbody>
</table>

<h2 dir="ltr" align="left" style="text-align:left">🖼 Practical Scenarios</h2>

### <a id="t2-15"></a>2.15 سيناريو: موجة محاولات دخول على صفحة تسجيل الدخول

يرسل نظام المراقبة تنبيهًا بارتفاع في أخطاء 401. خطوات المحلل:

1. **استخراج الأعلى تكرارًا:** من سجل الوصول يظهر عنوان واحد (`203.0.113.7`) أرسل مئات الطلبات `POST /login` خلال دقائق، وأغلبها `401`.
2. **فحص User-Agent:** القيمة `python-requests/2.31`، أي **سكربت** وليس متصفحًا.
3. **البحث عن نجاح:** نبحث عن `200` أو `302` من نفس العنوان بعد سلسلة الفشل، فنجد طلبًا واحدًا بنجاح ثم دخولًا إلى `/account`. أي أن **التخمين نجح**.
4. **تحديد الأثر:** ما الحساب؟ وماذا فعل بعد الدخول؟ هل وصل إلى بيانات أخرى؟
5. **الاحتواء:** حجب العنوان، وإنهاء جلسة الحساب، وإعادة تعيين كلمة المرور، وتفعيل **المصادقة متعددة العوامل (MFA)**.
6. **التحسين:** تفعيل **Rate Limiting** وقفل الحساب مؤقتًا وتنبيهات على أنماط 401.

### <a id="t2-16"></a>2.16 كيف تتعامل مع أسئلة الغرفة بمنهجية

تتضمن الغرفة أسئلة تطبيقية تتعامل فيها مع خادم تجريبي بطرق GET وPOST وPUT وDELETE وتنظر في رموز الحالة. ولا تُذكر هنا إجابات، بل **أسلوب العمل**:

1. **اقرأ المطلوب بدقة:** هل المطلوب طريقة؟ أم رمز حالة؟ أم رأسًا؟
2. **اربط الطريقة بغرضها:** جلب = GET، إرسال بيانات = POST، تحديث = PUT، حذف = DELETE.
3. **انظر في الاستجابة كاملة:** رمز الحالة ثم الرؤوس ثم الجسم، فالجواب غالبًا في أحدها.
4. **استعمل أدوات المتصفح:** تبويب **Network** في أدوات المطور يريك كل طلب واستجابته.
5. **جرّب بنفسك** بـ `curl -v` لتفهم ما يحدث فعلًا.

<h2 dir="ltr" align="left" style="text-align:left">📝 Practical Takeaways</h2>

- **HTTP** بروتوكول طلب واستجابة، **Stateless** ونصي، على المنفذ **80**، و**HTTPS** يضيف تشفير **TLS** على المنفذ **443**.
- **URL**: Scheme وUser وHost وPort وPath وQuery وFragment، والـ Fragment لا يصل للخادم.
- **الطلب**: سطر الطلب ثم الرؤوس ثم سطر فارغ ثم الجسم. **الاستجابة**: سطر الحالة ثم الرؤوس ثم سطر فارغ ثم الجسم.
- **الطرق**: GET جلب، POST إرسال، PUT تحديث، DELETE حذف.
- **الرموز**: 1xx معلومات، 2xx نجاح، 3xx تحويل، 4xx خطأ عميل، 5xx خطأ خادم.
- **401** = من أنت؟ و**403** = لا يحق لك.
- **HTTP/1.1** نصي، و**HTTP/2** و**HTTP/3** ثنائيان (HTTP/3 على UDP/443 عبر QUIC)، والمعنى واحد.
- **الكوكيز** تحل مشكلة غياب الذاكرة، وتُحمى بـ `Secure` و`HttpOnly` و`SameSite`.
- `curl -v` أفضل صديق لفهم HTTP.

## 🛡 خلاصة المحلل الأمني (SOC Takeaways)

- **سجلات الوصول** هي المصدر الأول لاكتشاف هجمات الويب: اقرأ العنوان والطريقة والمسار والرمز و User-Agent.
- **أنماط الرموز:** 401 كثيرة = Brute Force، 404 كثيرة = مسح، 500 بعد رموز غريبة = حقن محتمل.
- **User-Agent غير بشري** (`curl` أو `python-requests` أو `sqlmap` أو `nikto`) يستحق الفحص، مع التذكر أنه **قابل للتزوير**.
- **IDOR:** راقب تسلسل قيم `id` المتتالية من حساب واحد.
- **الجلسات:** اربط الكوكي بعنوان IP وUser-Agent، وانتبه لتغيرهما المفاجئ.
- **HTTP/2 وHTTP/3 ثنائيان:** لا تعتمد على قراءة النص الخام، واستعمل أدوات تفكهما، وراقب **UDP/443** إلى جانب TCP/443.
- **لا تخزن التوكنات في localStorage** إن أمكن، فالكوكي `HttpOnly` أحمى من XSS.
- **HTTPS** يحمي الطريق ولا يضمن أن الموقع نفسه سليم.
- أخفِ إصدار الخادم، وقيد الطرق غير اللازمة، وفعّل `Secure` و`HttpOnly` و`SameSite`.

<br>

<a id="room-3"></a>
<table align="center" width="100%"><tr><td align="right" style="text-align:right">

### 🚪 الغرفة 3: How Websites Work (كيف تعمل المواقع)

</td></tr></table>

<h1 dir="ltr" align="left" style="text-align:left">How Websites Work</h1>

### <a id="t3-1"></a>3.1 التعريف بالغرفة وأهدافها

عرفنا في الغرفتين السابقتين **عنوان** الموقع (DNS) و**لغة** التخاطب معه (HTTP). تجيب هذه الغرفة عن سؤال أوسع: **ما الذي يقف خلف الصفحة؟** أي المكونات التي تتعاون لتقديم تطبيق ويب للمستخدم، والمراحل التي يمر بها الطلب منذ كتابة الرابط حتى ظهور الصفحة.

ومن أهداف الغرفة أن نكون قادرين في نهايتها على:
- شرح نموذج **العميل والخادم (Client-Server)**.
- التفريق بين **Frontend** و**Backend** ولغات كل منهما.
- معرفة دور **خادم الويب** و**قاعدة البيانات** و**الطبقة الوسيطة**، وفهم **واجهات API** وصيغة **JSON**.
- تعرّف المكونات الشائعة بين المستخدم والخادم: **Load Balancer** و**CDN** و**WAF**.
- تتبع **دورة حياة الطلب** خطوة بخطوة: DNS ثم TCP ثم TLS ثم HTTP.
- فهم أين يراقب المدافع وأين يهاجم المهاجم.

<h2 dir="ltr" align="left" style="text-align:left">📌 Concepts Covered</h2>

### <a id="t3-2"></a>3.2 نموذج العميل والخادم

الويب كله مبني على علاقة بسيطة:
- **العميل (Client):** المتصفح أو أي أداة تبدأ الطلب وتعرض النتيجة.
- **الخادم (Server):** برنامج على جهاز آخر ينتظر الطلبات ويعالجها ويرد.

وتتم المحادثة بينهما بـ **HTTP**. والعميل **يبدأ دائمًا**، والخادم **لا يرسل شيئًا من تلقاء نفسه** إلا ردًا على طلب.

وبين الاثنين تقع في الواقع طبقات متعددة، وهذا رسم تقريبي لأشهرها:

<p align="center">
  <img src="images/web-architecture.svg" width="820" alt="بنية تطبيق الويب"><br>
  <sub>العميل ثم الطبقات الوسيطة (CDN وWAF وLoad Balancer) ثم خادم الويب ثم التطبيق ثم قاعدة البيانات</sub>
</p>

### <a id="t3-3"></a>3.3 Frontend و Backend

يُقسم عمل الموقع إلى جانبين:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">وجه المقارنة</th><th align="right" style="text-align:right"><b>Frontend</b> (جانب العميل)</th><th align="right" style="text-align:right"><b>Backend</b> (جانب الخادم)</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><b>أين يعمل</b></td><td align="right" style="text-align:right">داخل <b>المتصفح</b></td><td align="right" style="text-align:right">على <b>الخادم</b></td></tr>
<tr><td align="right" style="text-align:right"><b>الوظيفة</b></td><td align="right" style="text-align:right">عرض الواجهة والتفاعل مع المستخدم</td><td align="right" style="text-align:right">معالجة الطلبات والتحقق والتخزين</td></tr>
<tr><td align="right" style="text-align:right"><b>اللغات</b></td><td align="right" style="text-align:right"><b>HTML</b> و<b>CSS</b> و<b>JavaScript</b></td><td align="right" style="text-align:right"><b>PHP</b> و<b>Python</b> و<b>Node.js</b> و<b>Ruby</b> و<b>Java</b></td></tr>
<tr><td align="right" style="text-align:right"><b>من يراه</b></td><td align="right" style="text-align:right">المستخدم (والمهاجم) يرى كل الكود</td><td align="right" style="text-align:right">المستخدم <b>لا</b> يرى الكود</td></tr>
<tr><td align="right" style="text-align:right"><b>هل يُوثق به</b></td><td align="right" style="text-align:right"><b>لا</b>، لأن المستخدم يقدر يعدله</td><td align="right" style="text-align:right">نعم، هو مكان القرار النهائي</td></tr>
</tbody>
</table>

وأدوار لغات الواجهة الثلاث:
- **HTML:** **هيكل** الصفحة (عناوين، نصوص، نماذج).
- **CSS:** **تنسيق** الشكل (ألوان، خطوط، تخطيط).
- **JavaScript:** **التفاعل** (استجابة للنقر، تحديث دون إعادة تحميل).

والقاعدة الأمنية الذهبية: **لا تثق بأي شيء يأتي من العميل.** فكل تحقق يجري في الـ Frontend فقط يمكن تجاوزه بتعديل الطلب، ولذلك يجب إعادة التحقق في الـ Backend.

### <a id="t3-4"></a>3.4 مكونات الخلفية: الخادم وقاعدة البيانات والطبقة الوسيطة

- **خادم الويب (Web Server):** برنامج مثل **Apache** و**Nginx** و**IIS**، يستقبل الطلب ويقدم الملفات الثابتة (HTML وصور) أو يمرر الطلب إلى التطبيق.
- **الطبقة الوسيطة / التطبيق (Middleware / Application Layer):** الكود الذي يحمل **منطق التطبيق** (Application Logic)، مثل التحقق من كلمة المرور وحساب سلة المشتريات.
- **قاعدة البيانات (Database):** تخزن البيانات الدائمة (المستخدمون والمنتجات والطلبات)، مثل **MySQL** و**PostgreSQL** و**MongoDB**.

وكيف يتعاونون: يصل طلب `GET /items?id=7` إلى خادم الويب، فيمرره إلى التطبيق، فيسأل التطبيق قاعدة البيانات عن المنتج 7، ثم يبني صفحة HTML بالنتيجة، ويعيدها عبر الخادم إلى المتصفح.

### <a id="t3-5"></a>3.5 واجهات API وصيغة JSON

كثير من المواقع الحديثة لا تعيد صفحة HTML كاملة في كل مرة. الصفحة تُحمَّل مرة، ثم يرسل كود **JavaScript** طلبات في الخلفية إلى **API** ويحدّث جزءًا من الشاشة. و**API (Application Programming Interface)** هي **واجهة برمجية** يتعامل معها البرنامج، لا الإنسان، وتستقبل طلبات HTTP وترد ببيانات.

والنمط الأشهر لبنائها هو **REST**: كل شيء **مورد (Resource)** له مسار، والطريقة تحدد الفعل:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الطلب</th><th align="right" style="text-align:right">المعنى</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><code>GET /api/users/7</code></td><td align="right" style="text-align:right">اجلب المستخدم 7</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>POST /api/users</code></td><td align="right" style="text-align:right">أنشئ مستخدمًا جديدًا</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>PUT /api/users/7</code></td><td align="right" style="text-align:right">حدّث المستخدم 7</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>DELETE /api/users/7</code></td><td align="right" style="text-align:right">احذف المستخدم 7</td></tr>
</tbody>
</table>

وتتبادل هذه الواجهات البيانات غالبًا بصيغة **JSON (JavaScript Object Notation)**، وهي نص منظم من أزواج `مفتاح: قيمة`:

<div dir="ltr" align="left">

```json
{
  "id": 7,
  "name": "ali",
  "roles": ["user"],
  "active": true
}
```

</div>

ويحمل الطلب والرد الرأس `Content-Type: application/json` ليعرف الطرف الآخر كيف يقرأ الجسم. وتُرسل الهوية عادة برأس **Authorization** (مثل `Bearer <token>`) أو بكوكي الجلسة.

ولماذا يهم المحلل؟
- ترى في **تبويب Network** طلبات من نوع **XHR/Fetch** إلى مسارات `/api/...` وليس فقط صفحات.
- الـ **API** سطح هجوم مستقل: مساراتها كثيرة وبعضها **منسي أو غير موثق**، ولا يمر دائمًا على نفس حماية الصفحات.
- من أشهر مشكلاتها **IDOR** في المسارات (`/api/users/7` ثم `8`)، و**كشف بيانات زائدة** (ترد بحقول أكثر مما تعرضه الواجهة)، وضعف التحقق من الصلاحيات.
- **جسم** طلب الـ API (JSON) لا يظهر في سجل الوصول المعتاد، فهو يريك المسار والطريقة والرمز فقط، أما الجسم فيظهر في سجلات التطبيق أو الـ WAF.

### <a id="t3-6"></a>3.6 المكونات الوسيطة: Load Balancer وCDN وWAF

في المواقع الكبيرة تقف مكونات بين المستخدم والخادم:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">المكون</th><th align="right" style="text-align:right">وظيفته</th><th align="right" style="text-align:right">لماذا يهم المحلل</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Load Balancer</b></td><td align="right" style="text-align:right">يوزع الطلبات على عدة خوادم لتحمل الحمل</td><td align="right" style="text-align:right">عنوان المصدر في سجلات الخادم قد يكون عنوان <b>الموزع</b> لا العميل</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>CDN</b></td><td align="right" style="text-align:right">شبكة نسخ تخزن المحتوى قرب المستخدم وتسرّع التحميل</td><td align="right" style="text-align:right">يخفي عنوان الخادم الحقيقي</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>WAF (Web Application Firewall)</b></td><td align="right" style="text-align:right">جدار ناري <b>للتطبيقات</b> يفلتر طلبات HTTP الخبيثة</td><td align="right" style="text-align:right">مصدر تنبيهات مهم، ويمكن أن يخطئ</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Reverse Proxy</b></td><td align="right" style="text-align:right">يستقبل الطلبات نيابة عن الخادم ويمررها</td><td align="right" style="text-align:right">ينقل العنوان الحقيقي في رأس <code>X-Forwarded-For</code></td></tr>
</tbody>
</table>

ملاحظة مهمة للمحلل: حين ترى في السجلات عنوانًا واحدًا لكل الزوار، فغالبًا هو **الموزع أو الوكيل**، والعنوان الحقيقي في رأس **X-Forwarded-For**، وهو **قابل للتزوير** من العميل فلا يُوثق به إلا إذا أضافته جهة موثوقة.

### <a id="t3-7"></a>3.7 دورة حياة طلب الويب

حين تكتب `https://shop.example.com/items` وتضغط Enter تمر الرحلة بهذه المراحل:

<p align="center">
  <img src="images/web-request-lifecycle.svg" width="820" alt="دورة حياة طلب الويب"><br>
  <sub>الخطوات: DNS ثم TCP ثم TLS ثم HTTP ثم عرض الصفحة</sub>
</p>

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الخطوة</th><th align="right" style="text-align:right">ماذا يحدث</th><th align="right" style="text-align:right">البروتوكول</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>1. DNS Resolution</b></td><td align="right" style="text-align:right">ترجمة اسم النطاق إلى عنوان IP</td><td align="right" style="text-align:right">DNS (منفذ 53)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>2. TCP Handshake</b></td><td align="right" style="text-align:right">بناء اتصال موثوق: <code>SYN</code> ثم <code>SYN-ACK</code> ثم <code>ACK</code></td><td dir="ltr" align="left" style="text-align:left">TCP</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>3. TLS Handshake</b></td><td align="right" style="text-align:right">الاتفاق على التشفير وتبادل الشهادات والمفاتيح (<b>HTTPS فقط</b>)</td><td dir="ltr" align="left" style="text-align:left">TLS</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>4. HTTP Request</b></td><td align="right" style="text-align:right">المتصفح يرسل الطلب</td><td dir="ltr" align="left" style="text-align:left">HTTP</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>5. HTTP Response</b></td><td align="right" style="text-align:right">الخادم يرد بالـ HTML</td><td dir="ltr" align="left" style="text-align:left">HTTP</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>6. Rendering</b></td><td align="right" style="text-align:right">يبني المتصفح الصفحة، ويطلب بقية الأصول (CSS وJS وصور) بطلبات إضافية</td><td dir="ltr" align="left" style="text-align:left">HTTP</td></tr>
</tbody>
</table>

ولاحظ أن **الخطوة 3 تُتخطى مع HTTP العادي**، وأن صفحة واحدة تتطلب غالبًا **عشرات الطلبات** لجلب كل أصولها.

وفي **HTTP/3** يحل **QUIC** (فوق UDP) محل الخطوتين 2 و3 معًا، فيُبنى الاتصال والتشفير في خطوة واحدة تقريبًا، لكن الفكرة العامة للرحلة تبقى كما هي.

وتتأخر الصفحة عادة بسبب أحد هذه الأجزاء، ولذلك يقيس المهندس زمن كل مرحلة على حدة (انظر الأوامر).

### <a id="t3-8"></a>3.8 أين تقع الهجمات: Frontend وBackend وما بينهما

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الجانب</th><th align="right" style="text-align:right">أمثلة هجمات</th><th align="right" style="text-align:right">الحماية</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Frontend</b></td><td align="right" style="text-align:right">XSS، عبث بالحقول المخفية، كشف أسرار في JavaScript</td><td align="right" style="text-align:right">ترميز المخرجات (Output Encoding)، عدم وضع أسرار في الواجهة</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Backend</b></td><td align="right" style="text-align:right">SQL Injection، Command Injection، كسر المصادقة</td><td align="right" style="text-align:right">استعلامات معلمة (Parameterized Queries)، التحقق من المدخلات</td></tr>
<tr><td align="right" style="text-align:right"><b>الطبقات الوسيطة</b></td><td align="right" style="text-align:right">تجاوز WAF، تزوير <code>X-Forwarded-For</code></td><td align="right" style="text-align:right">عدم الاعتماد على رؤوس قابلة للتزوير</td></tr>
<tr><td align="right" style="text-align:right"><b>قاعدة البيانات</b></td><td align="right" style="text-align:right">وصول مباشر وكلمات مرور ضعيفة</td><td align="right" style="text-align:right">عزلها وصلاحيات الحد الأدنى</td></tr>
</tbody>
</table>

### <a id="t3-9"></a>3.9 الزاوية الأمنية: المراقبة ومنطق التطبيق

من منظور **SOC** و**Blue Team**:

1. **مراقبة المنافذ 80 و443:** هي بوابة الدخول الأساسية، وأي خدمة ويب على منفذ آخر غير معلوم (مثل 8080 أو 8000) يجب أن تُعرف وتُوثق، فالخدمات المنسية هدف مفضل.
2. **الطلبات الشاذة:** طلبات بأحجام ضخمة، أو طرق غير معتادة، أو مسارات لا يعرفها التطبيق، أو أنماط متكررة بسرعة.
3. **ثغرات منطق التطبيق (Application Logic Flaws):** هي أخطاء في **تصميم** التطبيق لا في برنامج الخادم، ولا يكتشفها الجدار الناري أو WAF دائمًا. مثال: تجاوز خطوة الدفع بالانتقال مباشرة إلى رابط التأكيد، أو تغيير السعر في الحقل المخفي. ويلزم لاكتشافها **فهم ما هو الطبيعي** للتطبيق.
4. **هجمات تستهدف التطبيق (Web Application Attacks):** مثل SQL Injection وXSS وPath Traversal، وتظهر آثارها في **الرابط والجسم والرؤوس**.
5. **الجانب الخلفي:** قاعدة البيانات يجب ألا تكون مكشوفة للإنترنت، بل تُكلَّم من التطبيق فقط.

<h2 dir="ltr" align="left" style="text-align:left">🛠 Commands &amp; Hands-on</h2>

### <a id="t3-10"></a>3.10 أدوات فحص دورة حياة الطلب

**1) قياس زمن كل مرحلة بـ `curl -w`:**

<div dir="ltr" align="left">

```bash
curl -s -o /dev/null https://example.com -w "\
dns:     %{time_namelookup}\n\
connect: %{time_connect}\n\
tls:     %{time_appconnect}\n\
first:   %{time_starttransfer}\n\
total:   %{time_total}\n"
```

</div>

وتمثل هذه القيم **تراكميًا** المراحل: DNS ثم اتصال TCP ثم TLS ثم أول بايت من الاستجابة ثم الإجمالي. وشكل ناتج توضيحي:

<div dir="ltr" align="left">

```text
dns:     0.012
connect: 0.045
tls:     0.110
first:   0.185
total:   0.190
```

</div>

**2) رؤية التفاصيل بـ `curl -v`:**

<div dir="ltr" align="left">

```bash
curl -v https://example.com 2>&1 | head -30
```

</div>

وسترى مراحل: التعرف على العنوان، ثم `Connected`، ثم TLS handshake وتفاصيل الشهادة، ثم الطلب والاستجابة.

**3) فحص التشفير والشهادة بـ `openssl`:**

<div dir="ltr" align="left">

```bash
openssl s_client -connect example.com:443 \
        -servername example.com </dev/null
```

</div>

وأهم ما نقرؤه: **الشهادة** (من أصدرها ومتى تنتهي)، و**إصدار TLS** و**الشفرة (Cipher)** المستخدمة. ولعرض الشهادة فقط:

<div dir="ltr" align="left">

```bash
openssl s_client -connect example.com:443 \
        -servername example.com </dev/null 2>/dev/null \
  | openssl x509 -noout -subject -issuer -dates
```

</div>

**4) فحص أن الخدمة تستمع:**

<div dir="ltr" align="left">

```bash
ss -tlnp | grep -E ':(80|443)\b'   # listening web ports
curl -sI http://localhost          # headers from local server

# call an API and pretty-print the JSON
curl -s -H "Accept: application/json" \
     http://example.com/api/users/7 | python3 -m json.tool
```

</div>

### <a id="t3-11"></a>3.11 جدول مرجعي: بنية الويب والأدوات (Cheatsheet)

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">العنصر</th><th align="right" style="text-align:right">المعنى</th><th align="right" style="text-align:right">مثال</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left">Client</td><td align="right" style="text-align:right">يبدأ الطلب</td><td align="right" style="text-align:right">متصفح، <code>curl</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">Web Server</td><td align="right" style="text-align:right">يستقبل ويقدم الملفات</td><td align="right" style="text-align:right">Apache، Nginx، IIS</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">Application</td><td align="right" style="text-align:right">منطق التطبيق</td><td align="right" style="text-align:right">PHP، Python، Node.js</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">Database</td><td align="right" style="text-align:right">البيانات الدائمة</td><td align="right" style="text-align:right">MySQL، PostgreSQL</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">Load Balancer</td><td align="right" style="text-align:right">توزيع الحمل</td><td align="right" style="text-align:right">نقطة دخول واحدة لعدة خوادم</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">CDN</td><td align="right" style="text-align:right">نسخ قريبة من المستخدم</td><td align="right" style="text-align:right">تسريع المحتوى الثابت</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">WAF</td><td align="right" style="text-align:right">جدار ناري للتطبيقات</td><td align="right" style="text-align:right">يحجب حمولات مشبوهة</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>X-Forwarded-For</code></td><td align="right" style="text-align:right">عنوان العميل خلف وكيل</td><td align="right" style="text-align:right">قابل للتزوير</td></tr>
<tr><td align="right" style="text-align:right">DNS ثم TCP ثم TLS ثم HTTP</td><td align="right" style="text-align:right">ترتيب مراحل الطلب</td><td align="right" style="text-align:right">الخطوة 3 لـ HTTPS فقط</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl -w</code></td><td align="right" style="text-align:right">قياس زمن المراحل</td><td dir="ltr" align="left" style="text-align:left"><code>%{time_namelookup}</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>openssl s_client</code></td><td align="right" style="text-align:right">فحص TLS والشهادة</td><td dir="ltr" align="left" style="text-align:left"><code>-connect host:443</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>ss -tlnp</code></td><td align="right" style="text-align:right">المنافذ المستمعة</td><td align="right" style="text-align:right">فحص 80 و443</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">API / REST</td><td align="right" style="text-align:right">واجهة برمجية، مورد لكل مسار</td><td dir="ltr" align="left" style="text-align:left"><code>GET /api/users/7</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">JSON</td><td align="right" style="text-align:right">صيغة تبادل بيانات</td><td dir="ltr" align="left" style="text-align:left"><code>{"id": 7}</code> + <code>Content-Type: application/json</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>python3 -m json.tool</code></td><td align="right" style="text-align:right">تنسيق JSON للقراءة</td><td dir="ltr" align="left" style="text-align:left"><code>curl -s &lt;url&gt; | python3 -m json.tool</code></td></tr>
</tbody>
</table>

<h2 dir="ltr" align="left" style="text-align:left">🖼 Practical Scenarios</h2>

### <a id="t3-12"></a>3.12 سيناريو: تباطؤ الموقع وطلبات غير معتادة

يشتكي المستخدمون من بطء موقع الشركة، وتصل تنبيهات عن زيادة الطلبات. خطوات المحلل:

1. **تحديد المرحلة البطيئة:** `curl -w` يظهر أن **DNS** و**TLS** سريعان، لكن **أول بايت** يتأخر كثيرًا، فالمشكلة في **الخادم أو التطبيق** لا في الشبكة.
2. **فحص السجلات:** عدد الطلبات إلى `/search` ارتفع آلاف المرات من عدد قليل من العناوين.
3. **تحليل الشكل:** الطلبات متتابعة بنمط آلي، وتحتوي معاملات طويلة غريبة، وتتسبب في ردود **500** من حين لآخر.
4. **التقدير:** إما **DoS على طبقة التطبيق** أو **محاولات حقن** عبر معامل البحث.
5. **الاحتواء:** تحديد معدل الطلبات (Rate Limit) وحجب العناوين على الـ WAF.
6. **المتابعة:** مراجعة سجلات قاعدة البيانات هل وصل الحقن إليها، وتصحيح الكود.

### <a id="t3-13"></a>3.13 كيف تتعامل مع أسئلة الغرفة بمنهجية

أسئلة هذه الغرفة نظرية في الغالب عن مكونات الويب ومراحل الطلب. ولا تُذكر هنا إجابات، بل **طريقة التفكير**:

1. **حدد الجانب:** هل السؤال عن شيء يعمل في **المتصفح** أم على **الخادم**؟
2. **تتبع رحلة الطلب بالترتيب:** DNS ثم TCP ثم TLS ثم HTTP، وحدد أين يقع السؤال منها.
3. **اربط اللغة بدورها:** هيكل (HTML)، تنسيق (CSS)، تفاعل (JavaScript)، معالجة (Backend).
4. **اقرأ الصياغة جيدًا:** كثيرًا ما تختلف إجابتان في كلمة واحدة مثل "يبدأ" و"يرد".

<h2 dir="ltr" align="left" style="text-align:left">📝 Practical Takeaways</h2>

- الويب **عميل وخادم**: العميل يطلب والخادم يرد.
- **Frontend** (HTML وCSS وJavaScript) يعمل في المتصفح ولا يُوثق به، و**Backend** (PHP وPython وNode.js وRuby) يعمل على الخادم وهو مكان القرار.
- **خادم الويب** يستقبل، و**التطبيق** يعالج، و**قاعدة البيانات** تخزن.
- بين المستخدم والخادم قد يوجد **Load Balancer** و**CDN** و**WAF** و**Reverse Proxy**.
- مراحل الطلب: **DNS ثم TCP ثم TLS ثم HTTP ثم العرض**، والـ TLS لـ HTTPS فقط.
- **API** واجهة برمجية، وغالبًا **REST** بصيغة **JSON**، وهي سطح هجوم مستقل.
- المنفذان **80** و**443** هما بوابة الويب.

## 🛡 خلاصة المحلل الأمني (SOC Takeaways)

- **راقب 80 و443** وكل منفذ ويب آخر، ووثّق الخدمات المنسية.
- **حدد المرحلة البطيئة** (DNS أم TLS أم التطبيق) قبل أن تحكم أن هناك هجومًا.
- **لا تثق في `X-Forwarded-For`** إلا من وكيل موثوق، وتذكر أن عنوان الموزع قد يظهر مكان العميل.
- **ثغرات المنطق** تحتاج فهم الطبيعي من التطبيق، ولا تلتقطها التواقيع دائمًا.
- **تحقق من الشهادات:** تاريخ الانتهاء وجهة الإصدار، فالشهادة المنتهية أو الغريبة مؤشر.
- **قاعدة البيانات** لا يجب أن تكون مكشوفة للإنترنت.
- **جرد مسارات الـ API** وراقبها كما تراقب الصفحات، وانتبه لتسلسل المعرفات (IDOR).
- كل تحقق في الـ Frontend فقط **يُعاد في الـ Backend**.

<br>

<a id="room-4"></a>
<table align="center" width="100%"><tr><td align="right" style="text-align:right">

### 🚪 الغرفة 4: Putting it all together (تجميع كل شيء معًا)

</td></tr></table>

<h1 dir="ltr" align="left" style="text-align:left">Putting it all together</h1>

### <a id="t4-1"></a>4.1 التعريف بالغرفة وأهدافها

هذه الغرفة **تطبيق تجميعي** لكل ما سبق في الوحدة: **URL** و**DNS** و**HTTP** و**الرؤوس** و**دورة حياة الطلب**. بدل أن ننظر لكل قطعة منفردة نتتبع **رحلة واحدة كاملة**، ثم نتعلم كيف نراقبها في المتصفح، وكيف يستخدم المحلل ما تراه في حركة HTTP لاكتشاف الهجمات.

ومن أهداف الغرفة أن نكون قادرين في نهايتها على:
- تتبع رحلة **تسجيل دخول** كاملة من كتابة الرابط حتى ظهور الصفحة.
- استخدام **Developer Tools** وتبويب **Network** لمراقبة الطلبات.
- ربط **DNS** و**عنوان IP** و**HTTP** معًا.
- فهم **Origin** و**Same-Origin Policy** و**CORS**.
- اكتشاف الهجمات من **متغيرات الاستعلام** و**User-Agent** والرؤوس.
- ربط استجابات الخادم **بأخطاء التهيئة** والثغرات المحتملة.

<h2 dir="ltr" align="left" style="text-align:left">📌 Concepts Covered</h2>

### <a id="t4-2"></a>4.2 رحلة تسجيل دخول كاملة من البداية إلى النهاية

لنتتبع مستخدمًا يفتح `https://shop.example.com/login` ويدخل بياناته:

وفي الرسم التالي كل **سهم** خطوة في الرحلة (12 سهمًا، لأن الجلب الأول لصفحة النموذج ورد الخادم ظاهران فيه).

<p align="center">
  <img src="images/end-to-end-login.svg" width="820" alt="رحلة تسجيل الدخول"><br>
  <sub>من كتابة الرابط إلى DNS ثم الاتصال ثم POST ثم الكوكي ثم الصفحة</sub>
</p>

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الخطوة</th><th align="right" style="text-align:right">ماذا يحدث</th><th align="right" style="text-align:right">المفهوم</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><b>1. كتابة الرابط</b></td><td align="right" style="text-align:right">المتصفح يفكك: Scheme=<code>https</code>، Host=<code>shop.example.com</code>، Path=<code>/login</code></td><td dir="ltr" align="left" style="text-align:left"><b>URL</b></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>2. DNS</b></td><td align="right" style="text-align:right">يسأل عن <code>shop.example.com</code> فيأتيه <code>192.0.2.10</code></td><td align="right" style="text-align:right"><b>DNS</b> (المنفذ 53)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>3. TCP</b></td><td align="right" style="text-align:right">اتصال بالعنوان على المنفذ 443</td><td dir="ltr" align="left" style="text-align:left"><b>TCP Handshake</b></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>4. TLS</b></td><td align="right" style="text-align:right">شهادة ومفاتيح لتشفير الاتصال</td><td dir="ltr" align="left" style="text-align:left"><b>TLS</b></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>5. GET /login</b></td><td align="right" style="text-align:right">المتصفح يجلب صفحة النموذج</td><td dir="ltr" align="left" style="text-align:left"><b>HTTP GET</b></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>6. POST /login</b></td><td align="right" style="text-align:right">عند الضغط على زر الدخول تُرسل البيانات في <b>الجسم</b></td><td dir="ltr" align="left" style="text-align:left"><b>HTTP POST</b> + <code>Content-Type</code></td></tr>
<tr><td align="right" style="text-align:right"><b>7. التحقق</b></td><td align="right" style="text-align:right">الخادم يفحص البيانات في قاعدة البيانات</td><td dir="ltr" align="left" style="text-align:left"><b>Backend</b></td></tr>
<tr><td align="right" style="text-align:right"><b>8. الرد</b></td><td align="right" style="text-align:right"><code>302</code> تحويل إلى <code>/account</code> مع <code>Set-Cookie</code></td><td dir="ltr" align="left" style="text-align:left"><b>Status Code</b> + <b>Cookie</b></td></tr>
<tr><td align="right" style="text-align:right"><b>9. الطلب التالي</b></td><td align="right" style="text-align:right">المتصفح يطلب <code>/account</code> مع <code>Cookie</code></td><td dir="ltr" align="left" style="text-align:left"><b>Session</b></td></tr>
</tbody>
</table>

وطلب الدخول بشكله:

<div dir="ltr" align="left">

```http
POST /login HTTP/1.1
Host: shop.example.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 29
Cookie: lang=ar

username=ali&password=Pass123
```

</div>

والرد الناجح:

<div dir="ltr" align="left">

```http
HTTP/1.1 302 Found
Location: /account
Set-Cookie: session=abc123; Secure; HttpOnly
Content-Length: 0
```

</div>

والخلاصة: **كل مفهوم في الوحدة له مكان في هذه الرحلة**، وإذا فسد جزء فسدت الرحلة: DNS معطوب = لا عنوان، TLS معطوب = لا اتصال آمن، رد 401 = بيانات خاطئة، وغياب الكوكي = لا جلسة.

### <a id="t4-3"></a>4.3 أدوات المطور وتبويب Network

كل متصفح حديث فيه **أدوات المطور (Developer Tools)** وتفتح بالمفتاح `F12`. وأهم تبويب للمحلل هو **Network**، وفيه قائمة بكل طلب أرسلته الصفحة.

**الأعمدة الأساسية:**

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">العمود</th><th align="right" style="text-align:right">ماذا يريك</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Name</b></td><td align="right" style="text-align:right">المورد المطلوب</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Status</b></td><td align="right" style="text-align:right">رمز الحالة (200 و404 و302...)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Method</b></td><td align="right" style="text-align:right">الطريقة (GET وPOST...)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Type</b></td><td align="right" style="text-align:right">نوع المحتوى (document وscript وimage...)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Size</b></td><td align="right" style="text-align:right">حجم الاستجابة</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Time / Waterfall</b></td><td align="right" style="text-align:right">زمن كل طلب ومراحله، والرسم الشلالي يبين التسلسل والتأخر</td></tr>
</tbody>
</table>

**عند النقر على أي طلب** تظهر تبويبات:
- **Headers:** رؤوس الطلب والاستجابة ورمز الحالة وعنوان الطلب.
- **Payload:** البيانات المرسلة في الجسم أو الاستعلام.
- **Response / Preview:** ما رد به الخادم.
- **Cookies:** الكوكيز المرسلة والمستقبلة.
- **Timing:** تفصيل الزمن (DNS وConnect وSSL وانتظار الخادم).

وخيارات مفيدة:
- **Filter:** تصفية حسب النوع (XHR وJS وImg) أو بحث نصي.
- **Preserve log:** يحتفظ بالسجل رغم التنقل بين الصفحات، لازم عند تتبع تسجيل دخول وتحويلات.
- **Copy as cURL:** نسخ الطلب كأمر `curl` لإعادة تنفيذه وتجربته خارج المتصفح.
- **Disable cache:** لرؤية الطلبات بدون تخزين مؤقت.

### <a id="t4-4"></a>4.4 ربط DNS وعنوان IP وHTTP

حين تجمع القطع تفهم لماذا يُطلب منك دائمًا الربط بينها:

- **DNS** يعطي **عنوان IP**، فيصبح الاتصال ممكنًا.
- **عنوان IP + المنفذ** يحددان **أي خادم وأي خدمة** (80 أو 443).
- **رأس Host** في HTTP يحدد **أي موقع** على هذا الخادم، لأن عنوانًا واحدًا قد يستضيف مواقع كثيرة.
- **الطريقة والمسار** يحددان **ماذا نفعل بأي مورد**.

وعمليًا هذا يعني أن الطلب نفسه يمكن اختباره بطرق مختلفة، ومثال يوضح الفرق بين **الاسم** و**العنوان**:

<div dir="ltr" align="left">

```bash
# normal: resolve name, then request
curl http://shop.example.com/

# skip DNS: connect to a chosen IP but keep Host header
curl --resolve shop.example.com:80:192.0.2.10 \
     http://shop.example.com/

# talk to the IP and set Host manually
curl -H "Host: shop.example.com" http://192.0.2.10/
```

</div>

وأهمية هذا للمحلل: **طلب بعنوان IP مباشر بدل اسم** (رأس Host فارغ أو عنوان) يستحق الانتباه، لأنه نمط الماسحات الآلية التي لا تعرف أسماء النطاقات.

### <a id="t4-5"></a>4.5 سياسة الأصل الواحد (Same-Origin Policy) وCORS

**الأصل (Origin)** هو ثلاثية: **Scheme + Host + Port** من الرابط. وكل صفحة تعمل في متصفحك لها أصل، والمتصفح يطبق قاعدة تسمى **Same-Origin Policy (SOP)**: **سكربت من أصل معين لا يستطيع قراءة ردود أصل آخر.**

ولماذا؟ لأنك قد تفتح موقعًا خبيثًا وفي تبويب آخر بنكك مسجَّل الدخول. ولولا SOP لقرأ سكربت الموقع الخبيث صفحات بنكك **بكوكيزك**. وتوضح هذه الأمثلة مقارنةً بالأصل `https://shop.example.com`:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الرابط</th><th align="right" style="text-align:right">نفس الأصل؟</th><th align="right" style="text-align:right">السبب</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><code>https://shop.example.com/cart</code></td><td align="right" style="text-align:right">نعم</td><td align="right" style="text-align:right">نفس الثلاثية، المسار لا يهم</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>http://shop.example.com</code></td><td align="right" style="text-align:right"><b>لا</b></td><td align="right" style="text-align:right">Scheme مختلف</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>https://api.shop.example.com</code></td><td align="right" style="text-align:right"><b>لا</b></td><td align="right" style="text-align:right">Host مختلف</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>https://shop.example.com:8443</code></td><td align="right" style="text-align:right"><b>لا</b></td><td align="right" style="text-align:right">Port مختلف</td></tr>
</tbody>
</table>

وأحيانًا يحتاج موقع شرعي أن يقرأ من أصل آخر (واجهة `app.example.com` تستدعي `api.example.com`). فجاء **CORS (Cross-Origin Resource Sharing)**: **الخادم يسمح** صراحةً لأصل معين عبر رؤوس الاستجابة:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الرأس</th><th align="right" style="text-align:right">وظيفته</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Access-Control-Allow-Origin</b></td><td align="right" style="text-align:right">الأصل المسموح له بقراءة الرد</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Access-Control-Allow-Methods</b></td><td align="right" style="text-align:right">الطرق المسموحة</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Access-Control-Allow-Headers</b></td><td align="right" style="text-align:right">الرؤوس المسموحة</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Access-Control-Allow-Credentials</b></td><td align="right" style="text-align:right">هل يُسمح بإرسال الكوكيز مع الطلب</td></tr>
</tbody>
</table>

وقبل الطلبات "الحساسة" (مثل PUT أو DELETE أو رؤوس مخصصة) يرسل المتصفح طلبًا استكشافيًا بطريقة **OPTIONS** يسمى **Preflight** ليسأل الخادم: هل تسمح؟ فإن لم يأذن لم يرسل الطلب الحقيقي.

ثلاث نقاط تُسأل كثيرًا وتُفهم خطأ:
- **SOP تحمي القراءة، لا الإرسال:** الطلب قد يصل للخادم فعلًا، لكن السكربت المهاجم لا يقرأ الرد. ولذلك توجد هجمات **CSRF** وتُواجه بسمة `SameSite` ورموز CSRF.
- **CORS ليس جدارًا ناريًا:** يقيّد **المتصفحات** فقط، ولا يمنع `curl` أو أي أداة.
- **الأخطاء الخطرة في إعداده:** `Access-Control-Allow-Origin: *` على بيانات حساسة، أو **عكس قيمة Origin** القادمة من الطلب مع `Allow-Credentials: true`، فيصير أي موقع خبيث قادرًا على قراءة بيانات المستخدم.

### <a id="t4-6"></a>4.6 تحليل حركة HTTP لاكتشاف الهجمات

يستطيع المحلل اكتشاف الهجمات من **عناصر الطلب الظاهرة** في السجلات:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">العنصر</th><th align="right" style="text-align:right">ماذا نبحث عنه</th><th align="right" style="text-align:right">مؤشر محتمل</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Query String</b></td><td align="right" style="text-align:right">رموز غريبة وتعبيرات برمجية</td><td align="right" style="text-align:right"><code>' OR 1=1</code> حقن SQL، <code>&lt;script&gt;</code> هجوم XSS، <code>../</code> اجتياز مسارات</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Path</b></td><td align="right" style="text-align:right">مسارات حساسة</td><td align="right" style="text-align:right"><code>/admin</code> و<code>/.env</code> و<code>/wp-login.php</code> و<code>/phpmyadmin</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Method</b></td><td align="right" style="text-align:right">طرق غير متوقعة</td><td align="right" style="text-align:right"><code>PUT</code> أو <code>DELETE</code> أو <code>TRACE</code> على موقع عادي</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>User-Agent</b></td><td align="right" style="text-align:right">أدوات آلية أو قيمة فارغة</td><td align="right" style="text-align:right"><code>sqlmap</code> و<code>nikto</code> و<code>curl</code> و<code>python-requests</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Referer</b></td><td align="right" style="text-align:right">مصدر مشبوه أو غير متسق</td><td align="right" style="text-align:right">رابط خارجي غريب، أو فارغ في طلبات تُفترض أنها داخلية</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Status</b></td><td align="right" style="text-align:right">نمط الرموز</td><td align="right" style="text-align:right">سيل 404 (مسح) أو 401 (تخمين) أو 500 (حقن)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Size</b></td><td align="right" style="text-align:right">حجم غير معتاد</td><td align="right" style="text-align:right">استجابة ضخمة قد تعني <b>تسريب بيانات</b></td></tr>
<tr><td align="right" style="text-align:right"><b>التوقيت</b></td><td align="right" style="text-align:right">انتظام عالٍ جدًا</td><td align="right" style="text-align:right">طلبات كل ثانية بالضبط، أي أتمتة</td></tr>
</tbody>
</table>

**أمثلة على أنماط في سطر الطلب (توضيحية، مرمّزة بالرموز كما تظهر في السجل):**

<div dir="ltr" align="left">

```text
GET /items?id=7%27%20OR%201%3D1-- HTTP/1.1
GET /download?file=..%2F..%2Fetc%2Fpasswd HTTP/1.1
GET /search?q=%3Cscript%3Ealert(1)%3C%2Fscript%3E HTTP/1.1
```

</div>

وتذكر أن هذه الأنماط تظهر **مرمّزة بـ URL Encoding** فلا بد من **فك الترميز** عند البحث عنها. ومن الأخطاء الشائعة الاعتماد على نص واحد في البحث، بينما يستعمل المهاجم ترميزات متعددة ليتهرب.

وبإمكانك إجراء فحص أولي بـ `grep`:

<div dir="ltr" align="left">

```bash
# SQL injection hints (encoded and plain)
grep -i -E "%27|union|select|or%201" access.log

# path traversal hints
grep -E "\.\./|%2e%2e|%2f\.\." access.log

# XSS hints
grep -i -E "<script|%3cscript" access.log
```

</div>

وهذه البحوث **تُنتج إنذارات كاذبة**، لذلك تُستخدم كنقطة بداية ثم يُتحقق من الاستجابة: رمز `200` بحجم مختلف عن المعتاد يستدعي فحصًا أعمق من `404`.

### <a id="t4-7"></a>4.7 ربط استجابات الخادم بأخطاء التهيئة

ليس كل ما يكشفه الخادم هجومًا، فكثير منه **أخطاء تهيئة (Misconfiguration)** تفتح الباب للمهاجم. وتظهر في الاستجابات:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">ما تراه في الاستجابة</th><th align="right" style="text-align:right">المشكلة</th><th align="right" style="text-align:right">الإصلاح</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><code>Server: Apache/2.4.49</code> أو <code>X-Powered-By: PHP/5.6</code></td><td align="right" style="text-align:right"><b>كشف الإصدار</b> يسهل استهداف ثغرات معروفة</td><td align="right" style="text-align:right">إخفاء أو تقليل الرؤوس وتحديث البرنامج</td></tr>
<tr><td align="right" style="text-align:right">رسالة خطأ فيها مسار ملف أو استعلام SQL</td><td align="right" style="text-align:right"><b>Verbose Errors</b> تكشف البنية الداخلية</td><td align="right" style="text-align:right">صفحات خطأ عامة وتسجيل التفاصيل داخليًا</td></tr>
<tr><td align="right" style="text-align:right">صفحة تعرض <b>قائمة ملفات</b> المجلد</td><td align="right" style="text-align:right"><b>Directory Listing</b> مفعل</td><td align="right" style="text-align:right">تعطيله</td></tr>
<tr><td align="right" style="text-align:right"><code>Set-Cookie</code> بدون <code>Secure</code> أو <code>HttpOnly</code></td><td align="right" style="text-align:right">كوكي الجلسة ضعيفة الحماية</td><td align="right" style="text-align:right">إضافة السمات</td></tr>
<tr><td align="right" style="text-align:right">غياب رؤوس الأمان</td><td align="right" style="text-align:right">تطبيق عرضة للنقر الخادع وXSS</td><td align="right" style="text-align:right">إضافة الرؤوس أدناه</td></tr>
<tr><td align="right" style="text-align:right"><code>Access-Control-Allow-Origin: *</code> على بيانات حساسة</td><td align="right" style="text-align:right"><b>CORS</b> واسع جدًا</td><td align="right" style="text-align:right">تقييده بمواقع محددة</td></tr>
<tr><td align="right" style="text-align:right">الموقع يعمل على HTTP بلا تحويل</td><td align="right" style="text-align:right">بيانات تمر نصًا</td><td align="right" style="text-align:right">تحويل كامل إلى HTTPS و<code>HSTS</code></td></tr>
<tr><td align="right" style="text-align:right"><code>/.git</code> أو <code>/backup.zip</code> متاحة</td><td align="right" style="text-align:right"><b>ملفات حساسة</b> مكشوفة</td><td align="right" style="text-align:right">حجبها وإزالتها</td></tr>
</tbody>
</table>

وأهم **رؤوس الأمان (Security Headers)** التي يجب أن يحملها الرد:

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">الرأس</th><th align="right" style="text-align:right">وظيفته</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Strict-Transport-Security</b> (HSTS)</td><td align="right" style="text-align:right">يلزم المتصفح بـ HTTPS دائمًا</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Content-Security-Policy</b> (CSP)</td><td align="right" style="text-align:right">يحدد مصادر السكربتات المسموحة، ويخفف XSS</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>X-Frame-Options</b></td><td align="right" style="text-align:right">يمنع تضمين الصفحة في إطار (النقر الخادع)</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>X-Content-Type-Options: nosniff</b></td><td align="right" style="text-align:right">يمنع المتصفح من تخمين نوع المحتوى</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Referrer-Policy</b></td><td align="right" style="text-align:right">يتحكم فيما يُرسل في رأس Referer</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Permissions-Policy</b></td><td align="right" style="text-align:right">يقيد ميزات المتصفح (الكاميرا وغيرها)</td></tr>
</tbody>
</table>

### <a id="t4-8"></a>4.8 خريطة: من مفاهيم الوحدة إلى الهجمات المقابلة

بعد أن عرفنا القطع كلها، هذا الجدول يربط **كل مفهوم** بأشهر الهجمات التي تستهدفه. والتفاصيل الكاملة لكل هجوم في الوحدة التالية.

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">المفهوم</th><th align="right" style="text-align:right">الهجوم المرتبط</th><th align="right" style="text-align:right">أين يظهر الأثر</th><th align="right" style="text-align:right">أهم حماية</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><b>DNS</b> (سجلات وذاكرة)</td><td dir="ltr" align="left" style="text-align:left">DNS Spoofing / Hijacking / Tunneling</td><td align="right" style="text-align:right">استعلامات شاذة وعناوين غير متوقعة</td><td align="right" style="text-align:right">DNSSEC، مراقبة DNS، قفل النطاق</td></tr>
<tr><td align="right" style="text-align:right"><b>النطاقات الفرعية</b></td><td align="right" style="text-align:right">Subdomain Takeover، تصيد بنطاق مشابه</td><td align="right" style="text-align:right">سجلات CNAME يتيمة</td><td align="right" style="text-align:right">جرد النطاقات الفرعية</td></tr>
<tr><td align="right" style="text-align:right"><b>HTTP بلا تشفير</b></td><td align="right" style="text-align:right">التنصت وسرقة البيانات (MITM)</td><td align="right" style="text-align:right">بيانات نصية على الشبكة</td><td dir="ltr" align="left" style="text-align:left">HTTPS + HSTS</td></tr>
<tr><td align="right" style="text-align:right"><b>Query String والمعاملات</b></td><td align="right" style="text-align:right">SQL Injection، XSS، Path Traversal</td><td align="right" style="text-align:right">رموز غريبة في الرابط والجسم</td><td align="right" style="text-align:right">التحقق من المدخلات، استعلامات معلمة</td></tr>
<tr><td align="right" style="text-align:right"><b>معرفات في الرابط أو الـ API</b></td><td dir="ltr" align="left" style="text-align:left">IDOR</td><td align="right" style="text-align:right">تسلسل <code>id=7,8,9</code> من حساب واحد</td><td align="right" style="text-align:right">التحقق من ملكية المورد</td></tr>
<tr><td align="right" style="text-align:right"><b>الطرق (Methods)</b></td><td dir="ltr" align="left" style="text-align:left">Method Tampering</td><td align="right" style="text-align:right">PUT/DELETE/TRACE غير متوقعة</td><td align="right" style="text-align:right">تقييد الطرق</td></tr>
<tr><td align="right" style="text-align:right"><b>الكوكيز والجلسات</b></td><td align="right" style="text-align:right">Session Hijacking، CSRF</td><td align="right" style="text-align:right">تغير IP أو User-Agent للجلسة نفسها</td><td align="right" style="text-align:right"><code>Secure</code> و<code>HttpOnly</code> و<code>SameSite</code></td></tr>
<tr><td align="right" style="text-align:right"><b>صفحة تسجيل الدخول</b></td><td align="right" style="text-align:right">Brute Force، Credential Stuffing</td><td align="right" style="text-align:right">سيل 401 على <code>/login</code></td><td align="right" style="text-align:right">MFA، Rate Limiting، قفل الحساب</td></tr>
<tr><td align="right" style="text-align:right"><b>ثقة الواجهة (Frontend)</b></td><td align="right" style="text-align:right">Parameter Tampering، تجاوز التحقق</td><td align="right" style="text-align:right">قيم أسعار أو صلاحيات معدلة</td><td align="right" style="text-align:right">إعادة التحقق في Backend</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>CORS</b></td><td align="right" style="text-align:right">قراءة بيانات من أصل خبيث</td><td align="right" style="text-align:right">رأس Allow-Origin واسع</td><td align="right" style="text-align:right">قائمة أصول محددة</td></tr>
<tr><td align="right" style="text-align:right"><b>المنفذان 80/443 والطلبات</b></td><td align="right" style="text-align:right">مسح (Scanning)، DoS على التطبيق</td><td align="right" style="text-align:right">سيل 404 أو 429 أو 503</td><td align="right" style="text-align:right">WAF، Rate Limiting</td></tr>
<tr><td align="right" style="text-align:right"><b>رؤوس الاستجابة</b></td><td align="right" style="text-align:right">كشف الإصدارات، Clickjacking</td><td align="right" style="text-align:right"><code>Server</code> وغياب رؤوس الأمان</td><td align="right" style="text-align:right">إخفاء الرؤوس وإضافة Security Headers</td></tr>
</tbody>
</table>

### <a id="t4-9"></a>4.9 الزاوية الأمنية: سير عمل المحلل مع طلب مشبوه

حين يصلك طلب أو تنبيه عن نشاط ويب، فهذا الترتيب العملي:

1. **من؟** عنوان المصدر (وانتبه للوكيل وX-Forwarded-For) وUser-Agent.
2. **ماذا؟** الطريقة والمسار والمعاملات، وفك الترميز.
3. **أين؟** هل المورد حساس؟ وهل هو موجود أصلًا؟
4. **نتيجة؟** رمز الحالة وحجم الرد، هل نجح المهاجم؟
5. **قبل وبعد:** ماذا فعل هذا العنوان قبل الطلب وبعده؟
6. **اتساع الأثر:** هل حضر أي عنوان آخر بنفس الأسلوب؟
7. **الاحتواء والتحسين:** حجب، وتصحيح التهيئة أو الكود، وقاعدة كشف جديدة.

<h2 dir="ltr" align="left" style="text-align:left">🛠 Commands &amp; Hands-on</h2>

### <a id="t4-10"></a>4.10 أدوات التتبع والفحص

**1) إعادة تنفيذ طلب نسخته من المتصفح:** بعد **Copy as cURL** يمكن تنفيذه وتعديله:

<div dir="ltr" align="left">

```bash
curl 'https://shop.example.com/account' \
  -H 'Cookie: session=abc123' \
  -H 'User-Agent: Mozilla/5.0' \
  -i
```

</div>

**2) فحص رؤوس الأمان في موقع:**

<div dir="ltr" align="left">

```bash
curl -sI https://example.com | grep -i -E \
 "strict-transport|content-security|x-frame|x-content|referrer"
```

</div>

وغياب الرؤوس من الناتج يعني أنها **غير مفعلة**.

**3) كشف معلومات الخادم:**

<div dir="ltr" align="left">

```bash
curl -sI https://example.com | grep -i -E "^(server|x-powered-by)"
```

</div>

**4) متابعة سلسلة التحويلات:**

<div dir="ltr" align="left">

```bash
curl -sIL http://example.com | grep -i -E "^(HTTP|location)"
```

</div>

**5) اختبار سياسة CORS بطلب Preflight (على خادم تملكه):**

<div dir="ltr" align="left">

```bash
curl -i -X OPTIONS https://api.example.com/data \
  -H "Origin: https://other.example" \
  -H "Access-Control-Request-Method: GET"
```

</div>

وانظر في الرد إلى `Access-Control-Allow-Origin`: هل يعكس الأصل القادم؟ وهل يسمح بالكوكيز؟

**6) فك ترميز الرابط لقراءة الحمولة:**

<div dir="ltr" align="left">

```bash
python3 -c "import urllib.parse as u; \
print(u.unquote('id=7%27%20OR%201%3D1--'))"
```

</div>

والناتج `id=7' OR 1=1--`، وهو نمط حقن SQL يتضح بعد فك الترميز.

**7) فحص السجلات الجاهزة:**

<div dir="ltr" align="left">

```bash
# requests per IP per status
awk '{print $1, $9}' access.log | sort | uniq -c \
  | sort -rn | head

# most requested paths
awk '{print $7}' access.log | sort | uniq -c \
  | sort -rn | head

# large responses (possible data leak)
awk '$10 > 1000000 {print $1, $7, $10}' access.log
```

</div>

### <a id="t4-11"></a>4.11 جدول مرجعي: التحليل وربط المفاهيم (Cheatsheet)

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">العنصر</th><th align="right" style="text-align:right">المعنى</th><th align="right" style="text-align:right">مثال</th></tr></thead>
<tbody>
<tr><td align="right" style="text-align:right"><code>F12</code> ثم Network</td><td align="right" style="text-align:right">مراقبة الطلبات في المتصفح</td><td align="right" style="text-align:right">تبويبات Headers وPayload وTiming</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">Preserve log</td><td align="right" style="text-align:right">الاحتفاظ بالسجل عبر التنقل</td><td align="right" style="text-align:right">مهم لتتبع تسجيل الدخول</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">Copy as cURL</td><td align="right" style="text-align:right">نسخ الطلب كأمر</td><td align="right" style="text-align:right">إعادة تنفيذ خارج المتصفح</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl --resolve</code></td><td align="right" style="text-align:right">فرض عنوان IP لاسم</td><td align="right" style="text-align:right">اختبار خادم محدد</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>curl -H "Host: …"</code></td><td align="right" style="text-align:right">تحديد الموقع يدويًا</td><td align="right" style="text-align:right">اختبار استضافة مشتركة</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">URL Decoding</td><td align="right" style="text-align:right">فك <code>%27</code> إلى <code>'</code></td><td align="right" style="text-align:right">قراءة الحمولات المخفية</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">Origin</td><td dir="ltr" align="left" style="text-align:left">Scheme + Host + Port</td><td dir="ltr" align="left" style="text-align:left"><code>https://shop.example.com</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>Access-Control-Allow-Origin</code></td><td align="right" style="text-align:right">من يقرأ الرد من أصل آخر</td><td align="right" style="text-align:right"><code>*</code> أو أصل محدد</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">Preflight</td><td align="right" style="text-align:right">طلب OPTIONS قبل الطلب الحساس</td><td dir="ltr" align="left" style="text-align:left"><code>curl -X OPTIONS -H "Origin: …"</code></td></tr>
<tr><td align="right" style="text-align:right">Query مشبوه</td><td align="right" style="text-align:right"><code>'</code> و<code>&lt;script&gt;</code> و<code>../</code></td><td align="right" style="text-align:right">SQLi وXSS وTraversal</td></tr>
<tr><td align="right" style="text-align:right">404 كثيرة</td><td align="right" style="text-align:right">مسح مجلدات</td><td align="right" style="text-align:right">عنوان واحد ومسارات كثيرة</td></tr>
<tr><td align="right" style="text-align:right">401 كثيرة</td><td align="right" style="text-align:right">تخمين كلمات مرور</td><td align="right" style="text-align:right"><code>POST /login</code> متكرر</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">HSTS</td><td align="right" style="text-align:right">إجبار HTTPS</td><td dir="ltr" align="left" style="text-align:left"><code>Strict-Transport-Security</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left">CSP</td><td align="right" style="text-align:right">تقييد السكربتات</td><td dir="ltr" align="left" style="text-align:left"><code>Content-Security-Policy</code></td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><code>Server</code> / <code>X-Powered-By</code></td><td align="right" style="text-align:right">كشف التقنية والإصدار</td><td align="right" style="text-align:right">يُخفى أو يُقلل</td></tr>
</tbody>
</table>

<h2 dir="ltr" align="left" style="text-align:left">🖼 Practical Scenarios</h2>

### <a id="t4-12"></a>4.12 سيناريو: رابط تصيد وربط الأدلة معًا

يبلغك موظف عن رسالة بريد تحثه على "تحديث كلمة المرور" ويقول إنه ضغط الرابط. الرابط (مُعطَّل للتحليل، بقيمنا):

<div dir="ltr" align="left">

```text
hxxps://secure-login.example-bank.attacker.net/verify?id=4821
```

</div>

خطوات المحلل، وهي تجمع ما تعلمناه في الوحدة:

1. **قراءة الرابط من اليمين (DNS):** النطاق الحقيقي هو `attacker.net`، أما `example-bank` و`secure-login` فنطاقات فرعية للخداع.
2. **فحص النطاق:** `whois` يبين أنه سُجل **قبل أيام**، و`dig` يعطي عنوان IP لاستضافة مجهولة.
3. **فحص الخادم بأمان:** `curl -sIL` (من بيئة معزولة) يبين سلسلة تحويلات إلى صفحة تقلد صفحة الدخول، ورؤوس بلا أمان.
4. **البحث في السجلات:** في سجل الوكيل والـ DNS نبحث عن **كل الأجهزة** التي استعلمت عن `secure-login.example-bank.attacker.net` أو اتصلت بعنوانه.
5. **تحديد الأثر:** الموظف طلب الصفحة، وهل أرسل `POST` إليها؟ إن وُجد فقد **أُرسلت بيانات اعتماده**.
6. **الاحتواء:** حجب النطاق والعنوان، وإعادة تعيين كلمة مرور الموظف وإنهاء جلساته، وتفعيل MFA، وحذف الرسالة من بقية الصناديق.
7. **التوثيق والتحسين:** إضافة مؤشرات الاختراق (IoC) لأدوات المراقبة، وتوعية الموظفين.

### <a id="t4-13"></a>4.13 كيف تتعامل مع أسئلة الغرفة بمنهجية

تدور أسئلة الغرفة حول تتبع المفاهيم عمليًا. ولا تُذكر هنا إجابات، بل **أسلوب العمل**:

1. **ارسم الرحلة:** من الرابط إلى DNS إلى الاتصال إلى HTTP، ثم حدد أين يقع السؤال.
2. **استعمل أدوات المتصفح** لترى الرؤوس ورموز الحالة بنفسك.
3. **فرّق بين القطع:** ما شأن DNS؟ وما شأن HTTP؟ وما شأن الرؤوس؟
4. **ارجع إلى الغرف السابقة** لتراجع تعريفًا لا تذكره.

<h2 dir="ltr" align="left" style="text-align:left">📝 Practical Takeaways</h2>

- رحلة تسجيل الدخول تجمع كل الوحدة: **URL ثم DNS ثم TCP ثم TLS ثم GET ثم POST ثم Set-Cookie ثم Cookie**.
- **Developer Tools (F12)** وتبويب **Network** يريك الطلبات والرؤوس والرموز والتوقيت، ويمكن **نسخ الطلب كـ cURL**.
- **DNS** يعطي العنوان، و**المنفذ** يحدد الخدمة، و**Host** يحدد الموقع، و**الطريقة والمسار** يحددان الفعل.
- الهجمات تظهر في **Query** و**Path** و**User-Agent** و**الرموز** و**الأحجام** و**التوقيت**.
- كثير من الثغرات **أخطاء تهيئة** تُرى في رؤوس الاستجابة والأخطاء المفصلة وغياب رؤوس الأمان.
- **فك الترميز** ضروري قبل تحليل الحمولات.
- **SOP** تمنع قراءة ردود أصل آخر، و**CORS** استثناء يمنحه الخادم، وسوء إعداده (`*` أو عكس Origin مع الكوكيز) ثغرة.
- كل مفهوم في الوحدة له **هجوم مقابل** (جدول الخريطة)، وستجده مفصلًا في الوحدة 7.

## 🛡 خلاصة المحلل الأمني (SOC Takeaways)

- **اتبع الرحلة كاملة** عند التحقيق: DNS وشبكة وويب، فلا تنظر لقطعة واحدة.
- **افحص سطر الطلب والرمز والحجم معًا**، فالطلب المشبوه بـ 404 غير الطلب نفسه بـ 200 كبير.
- **فك ترميز الرابط** (URL Decode) قبل أن تحكم.
- **اقرأ الروابط من اليمين** لتجد النطاق الحقيقي.
- **اربط الأجهزة المتأثرة** عبر DNS ووكيل الويب بمجرد اكتشاف مؤشر.
- **تحقق من رؤوس الأمان** وإصدارات الخوادم ضمن التقييم الدوري.
- **راجع رؤوس CORS** في الاستجابات: `Allow-Origin` واسع مع `Allow-Credentials` علامة خطر.
- **دوّن مؤشرات الاختراق (IoC)** وحدّث قواعد الكشف بعد كل حادثة.

<a id="module-glossary"></a>

## 📖 جدول المصطلحات

<table dir="rtl" width="100%">
<thead><tr><th align="right" style="text-align:right">المصطلح</th><th align="right" style="text-align:right">المعنى</th><th align="right" style="text-align:right">الغرفة</th></tr></thead>
<tbody>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DNS</b></td><td align="right" style="text-align:right">نظام يترجم أسماء النطاقات إلى عناوين IP</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Root / TLD / SLD</b></td><td align="right" style="text-align:right">الجذر، نطاق المستوى الأعلى، نطاق المستوى الثاني</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>FQDN</b></td><td align="right" style="text-align:right">الاسم الكامل المؤهل بكل أجزائه</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Subdomain</b></td><td align="right" style="text-align:right">نطاق فرعي تحت نطاق رئيسي</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>gTLD / ccTLD</b></td><td align="right" style="text-align:right">نطاق عام / نطاق خاص بدولة</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>A / AAAA</b></td><td align="right" style="text-align:right">سجل عنوان IPv4 / IPv6</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>CNAME</b></td><td align="right" style="text-align:right">سجل اسم مستعار</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>MX</b></td><td align="right" style="text-align:right">سجل خادم البريد</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>TXT</b></td><td align="right" style="text-align:right">سجل نصي (SPF وDKIM وتحقق)</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>NS</b></td><td align="right" style="text-align:right">سجل خوادم الأسماء</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>PTR</b></td><td align="right" style="text-align:right">سجل البحث العكسي</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>TTL</b></td><td align="right" style="text-align:right">مدة بقاء السجل في الذاكرة المؤقتة</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Recursive / Authoritative</b></td><td align="right" style="text-align:right">خادم يبحث نيابة عنك / خادم يملك السجل الأصلي</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DNSSEC</b></td><td align="right" style="text-align:right">توقيع رقمي لسجلات DNS يضمن صحتها</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DoH / DoT</b></td><td align="right" style="text-align:right">DNS مشفر عبر HTTPS / TLS</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DNS Spoofing / Cache Poisoning</b></td><td align="right" style="text-align:right">حقن إجابات مزورة في DNS</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>DNS Tunneling</b></td><td align="right" style="text-align:right">تهريب بيانات أو أوامر داخل استعلامات DNS</td><td align="right" style="text-align:right">1</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>URL</b></td><td align="right" style="text-align:right">العنوان الكامل للمورد</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Scheme / Host / Port / Path</b></td><td align="right" style="text-align:right">البروتوكول / الخادم / المنفذ / المسار</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Query String / Fragment</b></td><td align="right" style="text-align:right">معاملات الرابط بعد <code>?</code> / موضع داخل الصفحة بعد <code>#</code></td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>URL Encoding</b></td><td align="right" style="text-align:right">ترميز الرموز الخاصة مثل <code>%20</code></td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>HTTP / HTTPS</b></td><td align="right" style="text-align:right">بروتوكول الويب / نسخته المشفرة بـ TLS</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>HTTP/1.1 / HTTP/2 / HTTP/3</b></td><td align="right" style="text-align:right">إصدارات HTTP: نصي / ثنائي متعدد الطلبات / فوق QUIC</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>QUIC</b></td><td align="right" style="text-align:right">بروتوكول نقل فوق UDP يدمج التشفير، تعتمده HTTP/3</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Stateless</b></td><td align="right" style="text-align:right">لا يتذكر الخادم الطلبات السابقة</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Request / Response</b></td><td align="right" style="text-align:right">الطلب / الاستجابة</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Header</b></td><td align="right" style="text-align:right">بيانات وصفية تصاحب الطلب أو الرد</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Method</b></td><td align="right" style="text-align:right">الفعل المطلوب: GET وPOST وPUT وDELETE</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Status Code</b></td><td align="right" style="text-align:right">رقم يبين نتيجة الطلب (2xx وغيرها)</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Cookie</b></td><td align="right" style="text-align:right">بيانات يخزنها المتصفح ويعيدها للخادم</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Web Storage</b></td><td align="right" style="text-align:right">تخزين المتصفح: localStorage وsessionStorage، لا يُرسل تلقائيًا</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Session</b></td><td align="right" style="text-align:right">حالة المستخدم المسجل، يحددها معرّف الجلسة</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>HttpOnly / Secure / SameSite</b></td><td align="right" style="text-align:right">سمات تحمي الكوكي</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>IDOR</b></td><td align="right" style="text-align:right">الوصول لمورد غيرك بتغيير معرّفه</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>XSS</b></td><td align="right" style="text-align:right">حقن سكربت في صفحة يعمل في متصفح الضحية</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>CSRF</b></td><td align="right" style="text-align:right">إجبار متصفح المستخدم على إرسال طلب باسمه دون علمه</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Access Log</b></td><td align="right" style="text-align:right">سجل الخادم لكل طلب وصله</td><td align="right" style="text-align:right">2</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Client / Server</b></td><td align="right" style="text-align:right">من يطلب / من يرد</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Frontend / Backend</b></td><td align="right" style="text-align:right">جانب المتصفح / جانب الخادم</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>HTML / CSS / JavaScript</b></td><td align="right" style="text-align:right">هيكل / تنسيق / تفاعل</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Web Server</b></td><td align="right" style="text-align:right">برنامج يستقبل الطلبات (Apache وNginx)</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Middleware / Application Logic</b></td><td align="right" style="text-align:right">طبقة التطبيق ومنطقه</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Database</b></td><td align="right" style="text-align:right">مخزن البيانات الدائم</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>API / REST</b></td><td align="right" style="text-align:right">واجهة برمجية تستقبل طلبات HTTP، ونمط REST يجعل لكل مورد مسارًا</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>JSON</b></td><td align="right" style="text-align:right">صيغة نصية لتبادل البيانات بأزواج مفتاح وقيمة</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Load Balancer</b></td><td align="right" style="text-align:right">موزع الطلبات على عدة خوادم</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>CDN</b></td><td align="right" style="text-align:right">شبكة نسخ قريبة من المستخدم</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>WAF</b></td><td align="right" style="text-align:right">جدار ناري لتطبيقات الويب</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Reverse Proxy</b></td><td align="right" style="text-align:right">وسيط يستقبل الطلبات نيابة عن الخادم</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>X-Forwarded-For</b></td><td align="right" style="text-align:right">رأس يحمل عنوان العميل خلف وكيل</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>TCP Handshake</b></td><td align="right" style="text-align:right">SYN وSYN-ACK وACK لبناء الاتصال</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>TLS Handshake</b></td><td align="right" style="text-align:right">الاتفاق على التشفير وتبادل الشهادات</td><td align="right" style="text-align:right">3</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Developer Tools</b></td><td align="right" style="text-align:right">أدوات المتصفح لفحص الطلبات (F12)</td><td align="right" style="text-align:right">4</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Waterfall</b></td><td align="right" style="text-align:right">رسم زمني لتسلسل الطلبات</td><td align="right" style="text-align:right">4</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Origin</b></td><td align="right" style="text-align:right">الثلاثية Scheme + Host + Port</td><td align="right" style="text-align:right">4</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>SOP</b></td><td align="right" style="text-align:right">Same-Origin Policy: منع قراءة ردود أصل آخر</td><td align="right" style="text-align:right">4</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>CORS</b></td><td align="right" style="text-align:right">آلية يسمح بها الخادم لأصل آخر بقراءة الرد</td><td align="right" style="text-align:right">4</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Preflight</b></td><td align="right" style="text-align:right">طلب OPTIONS استكشافي قبل الطلب الحساس</td><td align="right" style="text-align:right">4</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Copy as cURL</b></td><td align="right" style="text-align:right">نسخ طلب المتصفح كأمر curl</td><td align="right" style="text-align:right">4</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Misconfiguration</b></td><td align="right" style="text-align:right">خطأ في إعداد النظام يفتح ثغرة</td><td align="right" style="text-align:right">4</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>Security Headers</b></td><td align="right" style="text-align:right">رؤوس مثل HSTS وCSP تحمي المتصفح</td><td align="right" style="text-align:right">4</td></tr>
<tr><td dir="ltr" align="left" style="text-align:left"><b>IoC</b></td><td align="right" style="text-align:right">مؤشر اختراق يستخدم للكشف</td><td align="right" style="text-align:right">4</td></tr>
</tbody>
</table>

</div>