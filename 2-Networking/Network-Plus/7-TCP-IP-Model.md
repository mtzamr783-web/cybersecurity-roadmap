<div dir="rtl">

<div align="center">

# 🌐 07. نموذج <span dir="ltr">TCP/IP</span> | TCP/IP Model

</div>

---

<h2 dir="rtl" align="right">📌 الفهرس السريع</h2>

| الرقم | الموضوع |
|---|---|
| 1 | [تعريف نموذج <span dir="ltr">TCP/IP</span> وأشكال استخدامه](#1-تعريف-نموذج-tcpip-وأشكال-استخدامه) |
| 2 | [ليه لسه بندرس <span dir="ltr">OSI Model</span> والشغال فعليًا هو <span dir="ltr">TCP/IP</span>؟](#2-ليه-لسه-بندرس-osi-model-والشغال-فعليا-هو-tcpip) |
| 3 | [النسخة القديمة (4 طبقات) مقابل النسخة المحدثة (5 طبقات)](#3-النسخة-القديمة-4-طبقات-مقابل-النسخة-المحدثة-5-طبقات) |
| 4 | [المقارنة التفصيلية بين <span dir="ltr">OSI</span> و <span dir="ltr">TCP/IP</span>](#4-المقارنة-التفصيلية-بين-osi-و-tcpip) |
| 5 | [وظيفة كل طبقة في نموذج <span dir="ltr">TCP/IP</span>](#5-وظيفة-كل-طبقة-في-نموذج-tcpip) |
| 6 | [أهم البروتوكولات العاملة في كل طبقة](#6-أهم-البروتوكولات-العاملة-في-كل-طبقة) |
| 7 | [الفرق بين <span dir="ltr">TCP</span> و <span dir="ltr">UDP</span>](#7-الفرق-بين-tcp-و-udp) |
| 8 | [المسميات (<span dir="ltr">PDU</span>) وعملية <span dir="ltr">Encapsulation / Decapsulation</span>](#8-المسميات-pdu-وعملية-encapsulation--decapsulation) |
| 9 | [سبب التسمية <span dir="ltr">TCP/IP</span>](#9-سبب-التسمية-tcpip) |
| 10 | [جدول مرجعي: أشهر 20 بورت (مراجعة سريعة)](#10-جدول-مرجعي-أشهر-20-بورت-مراجعة-سريعة) |
| 11 | [كبسولة المذاكرة السريعة](#11-كبسولة-المذاكرة-السريعة) |

---

<h2 dir="rtl" align="right" id="1-تعريف-نموذج-tcpip-وأشكال-استخدامه">1️⃣ تعريف نموذج <span dir="ltr">TCP/IP</span> وأشكال استخدامه</h2>

نموذج <span dir="ltr">TCP/IP</span> (اختصار لـ <span dir="ltr">Transmission Control Protocol / Internet Protocol</span>) هو مجموعة البروتوكولات (<span dir="ltr">Protocol Suite</span>) اللي **فعليًا بتشغّل الإنترنت والشبكات في الواقع العملي**، على عكس نموذج <span dir="ltr">OSI</span> اللي هو نموذج نظري مرجعي بس.

باختصار، هو بروتوكول (أو بالأصح مجموعة بروتوكولات) مصمم بفلسفة أساسية: **نقل الداتا بنجاح تحت أي ظروف**، حتى لو كان فيه:

* ضعف أو بطء في الاتصال.
* انقطاعات متكررة في الشبكة.
* فقدان جزء من الحزم (<span dir="ltr">Packet Loss</span>) أثناء النقل.

ده رجّاع لأصل نشأته؛ لأنه اتطور أصلًا من مشروع عسكري أمريكي (<span dir="ltr">ARPANET</span>) في السبعينات، وكان لازم يضمن وصول البيانات حتى لو جزء من الشبكة اتدمر أو انقطع (زي ظروف الحرب الباردة وقتها).

<div align="center">

![نموذج TCP/IP بأربع طبقات: Application, Transport, Internet, Link](images/7-2-tcpip-model-4-layers.png)

</div>

**أشكال استخدامه** (يعني بيتمثل عمليًا في):

* كل مرة بتفتح فيها متصفح وتزور موقع، بتستخدم <span dir="ltr">TCP/IP</span> عشان توصلك الداتا.
* كل تطبيق على الموبايل بيتواصل مع سيرفر (واتساب، انستجرام، تليجرام) بيعتمد على نفس المجموعة دي من البروتوكولات.
* عنونة كل جهاز على الشبكة (<span dir="ltr">IP Addressing</span>) وتوجيه الحزم بين الشبكات (<span dir="ltr">Routing</span>) كلها جزء من نفس النموذج.
* هو النموذج اللي بتتبني عليه كل بروتوكولات الطبقات العليا زي <span dir="ltr">HTTP, FTP, DNS, SMTP</span> وغيرهم.

---

<h2 dir="rtl" align="right" id="2-ليه-لسه-بندرس-osi-model-والشغال-فعليا-هو-tcpip">2️⃣ ليه لسه بندرس <span dir="ltr">OSI Model</span> والشغال فعليًا هو <span dir="ltr">TCP/IP</span>؟</h2>

سؤال منطقي جدًا وبيتسأل كتير: طالما <span dir="ltr">TCP/IP</span> هو اللي شغال فعليًا في كل الأجهزة والشبكات حوالينا، ليه بندرس <span dir="ltr">OSI Model</span> بـ 7 طبقات من الأساس؟ الإجابة في عدة نقاط:

* **الدقة التعليمية:** نموذج <span dir="ltr">OSI</span> بيقسم العملية لـ 7 طبقات منفصلة وواضحة، وده بيسهّل شرح وفهم كل وظيفة لوحدها من غير تداخل، عكس <span dir="ltr">TCP/IP</span> اللي بيدمج عدة وظائف في طبقة واحدة.
* **اللغة المشتركة:** كل مهندسي الشبكات في العالم بيستخدموا مصطلحات <span dir="ltr">OSI</span> (زي "المشكلة في <span dir="ltr">Layer 2</span>" أو "فحص على مستوى <span dir="ltr">Layer 7</span>") كلغة موحدة لوصف أي عطل أو تحليل، حتى لو الأدوات الفعلية شغالة بمنطق <span dir="ltr">TCP/IP</span>.
* **منهجية استكشاف الأعطال (<span dir="ltr">Troubleshooting</span>):** المرور طبقة بطبقة بمنطق <span dir="ltr">OSI</span> (من <span dir="ltr">Physical</span> لحد <span dir="ltr">Application</span> أو العكس) بيدي منهج منظم لعزل أي مشكلة في الشبكة، وده أساسي في امتحان الـ <span dir="ltr">Network+</span> والعمل الميداني.
* **معيار المقارنة:** أي بروتوكول أو تقنية جديدة بتتقيّم وتتوصف بالنسبة لمكانها في طبقات <span dir="ltr">OSI</span>، حتى لو مش هتشتغل فعليًا كطبقة منفصلة.

باختصار: **<span dir="ltr">OSI</span> نموذج بنتعلم بيه إزاي نفهم ونحلل، و<span dir="ltr">TCP/IP</span> نموذج بيوصف إزاي الشبكة فعلًا بتشتغل.**

---

<h2 dir="rtl" align="right" id="3-النسخة-القديمة-4-طبقات-مقابل-النسخة-المحدثة-5-طبقات">3️⃣ النسخة القديمة (4 طبقات) مقابل النسخة المحدثة (5 طبقات)</h2>

نموذج <span dir="ltr">TCP/IP</span> نفسه اتقدم بيه أكتر من وصف عبر السنين:

<div align="center">

![مقارنة بين TCP/IP الأصلي بأربع طبقات والنسخة المحدثة بخمس طبقات](images/7-4-tcpip-original-vs-updated-5-layers.png)

</div>

* **النسخة الأصلية (<span dir="ltr">Original / Classic</span>) - 4 طبقات:** كانت بتضم <span dir="ltr">Application, Transport, Internet, Link</span>؛ وكانت طبقة الـ <span dir="ltr">Link</span> بتدمج فيها وظائف طبقتين مختلفين تمامًا (<span dir="ltr">Data Link</span> و <span dir="ltr">Physical</span>) في طبقة واحدة بس.
* **النسخة المحدثة (<span dir="ltr">Updated / Modern</span>) - 5 طبقات:** فصلت طبقة الـ <span dir="ltr">Link</span> القديمة لطبقتين منفصلتين وواضحتين: <span dir="ltr">Data Link</span> و <span dir="ltr">Physical</span>، عشان تقرب أكتر من دقة نموذج <span dir="ltr">OSI</span> وتسهّل عملية التدريس والمقارنة.

النسخة المحدثة دي هي اللي بتتدرّس غالبًا دلوقتي، وبتخلي المقارنة مع <span dir="ltr">OSI</span> أسهل بكتير؛ لأن أول 4 طبقات من <span dir="ltr">OSI</span> (من فوق) بتتقابل واحدة لواحدة مع طبقات <span dir="ltr">TCP/IP</span> الخمسة، وباقي الـ 3 طبقات العليا في <span dir="ltr">OSI</span> بتتلخص كلها في طبقة <span dir="ltr">Application</span> واحدة في <span dir="ltr">TCP/IP</span>.

---

<h2 dir="rtl" align="right" id="4-المقارنة-التفصيلية-بين-osi-و-tcpip">4️⃣ المقارنة التفصيلية بين <span dir="ltr">OSI</span> و <span dir="ltr">TCP/IP</span></h2>

أهم نقطة لازم تتثبت في دماغك: **العدد مش هو المهم، المهم هو التطابق الوظيفي.** يعني طبقة الـ <span dir="ltr">Application</span> في <span dir="ltr">TCP/IP</span> مش بس "بديلة" لطبقة <span dir="ltr">Application</span> في <span dir="ltr">OSI</span>، لكنها **بتلخّص وتدمج وظائف 3 طبقات كاملة** من الـ <span dir="ltr">OSI</span> جوّاها.

<div align="center">

![مقارنة مباشرة توضح خطأ شائع في مطابقة طبقة Application بين الموديلين](images/7-3-osi-vs-tcpip-compare-wrong-mapping.png)

</div>

**الخطأ الشائع اللي لازم تتجنبه:** كتير بيفتكروا إن طبقة الـ <span dir="ltr">Application</span> في <span dir="ltr">TCP/IP</span> بتقابل بس طبقة الـ <span dir="ltr">Application</span> في <span dir="ltr">OSI</span> وخلاص، وده غلط. الصح إنها بتقابل **3 طبقات مع بعض**: <span dir="ltr">Application + Presentation + Session</span>.

<div align="center">

![مطابقة رقمية بين طبقات OSI السبعة وطبقات TCP/IP](images/7-6-osi-tcpip-layer-mapping-numbered.png)

</div>

<div align="center">

| طبقة <span dir="ltr">OSI</span> | تقابلها في <span dir="ltr">TCP/IP</span> |
|:---:|:---:|
| <span dir="ltr">Application</span> | <span dir="ltr">Application</span> |
| <span dir="ltr">Presentation</span> | <span dir="ltr">Application</span> |
| <span dir="ltr">Session</span> | <span dir="ltr">Application</span> |
| <span dir="ltr">Transport</span> | <span dir="ltr">Transport</span> |
| <span dir="ltr">Network</span> | <span dir="ltr">Internet</span> |
| <span dir="ltr">Data Link</span> | <span dir="ltr">Data Link</span> (أو <span dir="ltr">Network Access</span> في النسخة القديمة) |
| <span dir="ltr">Physical</span> | <span dir="ltr">Physical</span> (أو <span dir="ltr">Network Access</span> في النسخة القديمة) |

</div>

<div align="center">

![ملخص بصري لتجميع الطبقات: Application+Presentation+Session تساوي Application، وNetwork تساوي Internet، وData Link+Physical تساوي Network Access](images/7-7-osi-to-tcpip-mapping-summary-box.png)

</div>

يعني ملخص التجميع كده:

* <span dir="ltr">Application + Presentation + Session</span> ➜ طبقة <span dir="ltr">Application</span> واحدة.
* <span dir="ltr">Network</span> ➜ طبقة <span dir="ltr">Internet</span>.
* <span dir="ltr">Data Link + Physical</span> ➜ طبقة <span dir="ltr">Network Access</span> (في النسخة القديمة) أو طبقتين منفصلتين بنفس الاسم في النسخة المحدثة.

---

<h2 dir="rtl" align="right" id="5-وظيفة-كل-طبقة-في-نموذج-tcpip">5️⃣ وظيفة كل طبقة في نموذج <span dir="ltr">TCP/IP</span></h2>

هنا هنشرح وظيفة كل طبقة (بالنسخة المحدثة بـ 5 طبقات) بترتيب من الأعلى للأسفل:

* **طبقة <span dir="ltr">Application</span>:** الطبقة اللي بيتفاعل معاها المستخدم مباشرة والبرامج اللي بتنتج وتستقبل البيانات (المتصفح، تطبيق الإيميل، إلخ). هي المسؤولة عن تجهيز البيانات بصيغة يفهمها البرنامج، وبتدمج جوّاها كل وظائف التنسيق (<span dir="ltr">Formatting</span>) والتشفير وإدارة الجلسات اللي كانت متقسمة في <span dir="ltr">OSI</span>.
* **طبقة <span dir="ltr">Transport</span>:** مسؤولة عن نقل البيانات بين البرنامج المصدر والبرنامج الوجهة (<span dir="ltr">Process-to-Process Communication</span>)، وبتحدد هل النقل هيكون موثوق ومضمون (<span dir="ltr">TCP</span>) ولا سريع من غير ضمانات (<span dir="ltr">UDP</span>)، وبتستخدم أرقام البورتات (<span dir="ltr">Port Numbers</span>) لتوجيه البيانات للبرنامج الصح.
* **طبقة <span dir="ltr">Internet</span>:** مسؤولة عن العنونة المنطقية (<span dir="ltr">Logical Addressing</span>) باستخدام عناوين الـ <span dir="ltr">IP</span>، وتحديد أفضل مسار (<span dir="ltr">Routing</span>) عشان توصل الحزمة من الشبكة المصدر للشبكة الوجهة، حتى لو فيه شبكات كتير بينهم.
* **طبقة <span dir="ltr">Network Access</span> (أو <span dir="ltr">Data Link + Physical</span> في النسخة المحدثة):** مسؤولة عن النقل الفعلي للبيانات كإشارات كهربائية أو ضوئية أو راديوية عبر الوسط الفيزيائي (كابل، فايبر، واي فاي)، وكمان مسؤولة عن العنونة الفيزيائية (<span dir="ltr">MAC Address</span>) والتحكم في الوصول للوسط الناقل.

---

<h2 dir="rtl" align="right" id="6-أهم-البروتوكولات-العاملة-في-كل-طبقة">6️⃣ أهم البروتوكولات العاملة في كل طبقة</h2>

* **طبقة <span dir="ltr">Application</span>:** <span dir="ltr">HTTP/HTTPS, FTP, SSH, Telnet, DNS, DHCP, SMTP, POP3, IMAP, SNMP</span>.
* **طبقة <span dir="ltr">Transport</span>:** <span dir="ltr">TCP</span> و <span dir="ltr">UDP</span> بس - دول أهم بروتوكولين في الطبقة دي.
* **طبقة <span dir="ltr">Internet</span>:** <span dir="ltr">IP (IPv4/IPv6), ICMP, ARP</span>.
* **طبقة <span dir="ltr">Network Access</span>:** <span dir="ltr">Ethernet, Wi-Fi (802.11), PPP</span>، وبروتوكولات التحكم في الوصول للوسط زي <span dir="ltr">CSMA/CD</span> و <span dir="ltr">CSMA/CA</span>.

---

<h2 dir="rtl" align="right" id="7-الفرق-بين-tcp-و-udp">7️⃣ الفرق بين <span dir="ltr">TCP</span> و <span dir="ltr">UDP</span></h2>

أهم نقطة في طبقة الـ <span dir="ltr">Transport</span>، وأكتر حاجة بتتسأل في الامتحان بشكل مباشر:

<div align="center">

| المعيار | <span dir="ltr">TCP</span> | <span dir="ltr">UDP</span> |
|:---:|:---:|:---:|
| الاسم الكامل | <span dir="ltr">Transmission Control Protocol</span> | <span dir="ltr">User Datagram Protocol</span> |
| نوع الاتصال | موجه بالاتصال (<span dir="ltr">Connection-Oriented</span>) | بلا اتصال (<span dir="ltr">Connectionless</span>) |
| الموثوقية | مضمون 100% (تأكيد استلام + إعادة إرسال) | غير مضمون، من غير تأكيد استلام |
| السرعة | أبطأ نسبيًا بسبب الفحص والتأكيد | أسرع بكتير لعدم وجود أي فحص |
| ترتيب البيانات | بيحافظ على ترتيب وصول الحزم | مفيش ترتيب مضمون للحزم |
| مرحلة الاتصال | يبدأ بمصافحة (<span dir="ltr">3-Way Handshake</span>) | بيبدأ الإرسال على طول من غير أي مصافحة |
| أفضل استخدام له | نقل ملفات، مواقع، إيميلات (دقة أهم من السرعة) | بث فيديو مباشر، مكالمات صوتية (سرعة أهم من الدقة) |

</div>

**قاعدة تفتكرها بيها بسهولة:** لو البيانات لازم توصل **كاملة وصح** حتى لو أبطأ ➜ <span dir="ltr">TCP</span>. لو البيانات لازم توصل **بسرعة** حتى لو جزء منها ضاع ➜ <span dir="ltr">UDP</span>.

---

<h2 dir="rtl" align="right" id="8-المسميات-pdu-وعملية-encapsulation--decapsulation">8️⃣ المسميات (<span dir="ltr">PDU</span>) وعملية <span dir="ltr">Encapsulation / Decapsulation</span></h2>

كل طبقة من طبقات <span dir="ltr">TCP/IP</span> بتضيف "غلاف" (<span dir="ltr">Header</span>) خاص بيها فوق البيانات القادمة من الطبقة اللي فوقها، وده اللي بيتسمى **<span dir="ltr">Protocol Data Unit (PDU)</span>** - يعني اسم البيانات بيتغير حسب الطبقة اللي هي فيها دلوقتي:

<div align="center">

| الطبقة | اسم الـ <span dir="ltr">PDU</span> |
|:---:|:---:|
| <span dir="ltr">Application</span> | <span dir="ltr">Data</span> |
| <span dir="ltr">Transport</span> | <span dir="ltr">Segment</span> (لو <span dir="ltr">TCP</span>) أو <span dir="ltr">Datagram</span> (لو <span dir="ltr">UDP</span>) |
| <span dir="ltr">Internet</span> | <span dir="ltr">Packet</span> |
| <span dir="ltr">Network Access</span> | <span dir="ltr">Frame</span> |

</div>

<div align="center">

![شرح تفصيلي لعملية Encapsulation و Decapsulation والتفاعل بين نفس الطبقة على الجهازين](images/7-5-encapsulation-decapsulation-same-layer-interaction.png)

</div>

**عملية <span dir="ltr">Encapsulation</span> (التغليف):** بتحصل عند **جهاز الإرسال**؛ البيانات بتنزل من طبقة <span dir="ltr">Application</span> للأسفل، وكل طبقة بتضيف <span dir="ltr">Header</span> خاص بيها (فيه معلومات زي رقم البورت، عنوان الـ <span dir="ltr">IP</span>، عنوان الـ <span dir="ltr">MAC</span>) لحد ما توصل لطبقة <span dir="ltr">Network Access</span> وتتحول لإشارات وتتبعت فعليًا على الوسط الناقل.

**عملية <span dir="ltr">Decapsulation</span> (فك التغليف):** بتحصل عند **جهاز الاستقبال**، وهي عكس العملية بالظبط؛ البيانات بتطلع من طبقة <span dir="ltr">Network Access</span> لفوق، وكل طبقة بتشيل الـ <span dir="ltr">Header</span> بتاعها وتقرأ المعلومة اللي محتاجاها، وتسلّم الباقي للطبقة اللي فوقها، لحد ما توصل البيانات الأصلية لطبقة الـ <span dir="ltr">Application</span> عند المستقبل.

**مفهوم <span dir="ltr">Same-Layer Interaction</span>:** المهم إنك تفهم إن كل طبقة عند جهاز الإرسال بتتواصل منطقيًا مع **نفس الطبقة بالظبط** عند جهاز الاستقبال (مثلًا طبقة <span dir="ltr">Transport</span> عند الاثنين بتتفاهم مع بعض بمنطق <span dir="ltr">Host-to-Host Communication</span>)، حتى لو فعليًا البيانات مرّت بكل الطبقات التانية وعدّت على أجهزة توجيه (<span dir="ltr">Routers</span>) في النص.

---

<h2 dir="rtl" align="right" id="9-سبب-التسمية-tcpip">9️⃣ سبب التسمية <span dir="ltr">TCP/IP</span></h2>

النموذج اتسمى بالاسم ده لأنه في الأساس مسمى على اسم **أهم وأشهر بروتوكولين** فيه، واللي بيمثلوا العمود الفقري لعملية النقل كلها:

* **<span dir="ltr">TCP (Transmission Control Protocol)</span>:** ممثل طبقة الـ <span dir="ltr">Transport</span>، ومسؤول عن ضمان وصول البيانات بشكل موثوق ومرتب.
* **<span dir="ltr">IP (Internet Protocol)</span>:** ممثل طبقة الـ <span dir="ltr">Internet</span>، ومسؤول عن العنونة والتوجيه بين الشبكات.

رغم إن النموذج فعليًا بيضم عشرات البروتوكولات التانية (زي <span dir="ltr">UDP, ICMP, ARP, DNS</span>...)، إلا إن الاسم اتثبت تاريخيًا على أشهر بروتوكولين فيه، بالظبط زي ما بيحصل مع أسماء تجارية كتير بتتسمى على أول أو أشهر منتج فيها.

---

<h2 dir="rtl" align="right" id="10-جدول-مرجعي-أشهر-20-بورت-مراجعة-سريعة">🔟 جدول مرجعي: أشهر 20 بورت (مراجعة سريعة)</h2>

جدول مرجعي سريع لأشهر البورتات اللي بتشتغل فوق طبقة الـ <span dir="ltr">Transport</span> (تفاصيلها الكاملة موجودة في ملف [5-port-number.md](5-port-number.md))، مفيد هنا كمراجعة سريعة وربط بين البروتوكول والطبقة اللي بيشتغل عليها:

<div align="center">

![جدول لأشهر 20 بورت مع البروتوكول والاستخدام](images/7-1-common-ports-table.png)

</div>

<div align="center">

| البورت | البروتوكول | الاستخدام |
|:---:|:---:|:---:|
| 20 | <span dir="ltr">TCP</span> | <span dir="ltr">FTP</span> (نقل البيانات) |
| 21 | <span dir="ltr">TCP</span> | <span dir="ltr">FTP</span> (التحكم) |
| 22 | <span dir="ltr">TCP</span> | <span dir="ltr">SSH</span> |
| 23 | <span dir="ltr">TCP</span> | <span dir="ltr">Telnet</span> |
| 53 | <span dir="ltr">UDP/TCP</span> | <span dir="ltr">DNS</span> |
| 67 | <span dir="ltr">UDP</span> | <span dir="ltr">DHCP</span> (من السيرفر للعميل) |
| 68 | <span dir="ltr">UDP</span> | <span dir="ltr">DHCP</span> (من العميل للسيرفر) |
| 69 | <span dir="ltr">UDP</span> | <span dir="ltr">TFTP</span> |
| 80 | <span dir="ltr">TCP</span> | <span dir="ltr">HTTP</span> |
| 110 | <span dir="ltr">TCP</span> | <span dir="ltr">POP3</span> |
| 123 | <span dir="ltr">UDP</span> | <span dir="ltr">NTP</span> |
| 138 / 139 | <span dir="ltr">UDP / TCP</span> | <span dir="ltr">NetBIOS</span> |
| 143 | <span dir="ltr">TCP</span> | <span dir="ltr">IMAP</span> |
| 161 | <span dir="ltr">UDP</span> | <span dir="ltr">SNMP</span> |
| 443 | <span dir="ltr">TCP</span> | <span dir="ltr">HTTPS</span> |
| 445 | <span dir="ltr">TCP</span> | <span dir="ltr">SMB</span> |
| 3389 | <span dir="ltr">TCP</span> | <span dir="ltr">RDP</span> |

</div>

---

<h2 dir="rtl" align="right" id="11-كبسولة-المذاكرة-السريعة">📝 كبسولة المذاكرة السريعة (<span dir="ltr">Cheat Sheet</span>)</h2>

<div align="center">

| النقطة | الملخص |
|:---:|:---:|
| التعريف | مجموعة بروتوكولات فعليًا بتشغّل الإنترنت، تصميمها الأساسي لضمان نقل الداتا رغم الأعطال |
| ليه بندرس <span dir="ltr">OSI</span> برضو | عشان الدقة التعليمية واللغة المشتركة ومنهجية استكشاف الأعطال |
| عدد الطبقات | 4 طبقات (النسخة القديمة) أو 5 طبقات (النسخة المحدثة اللي فصلت <span dir="ltr">Data Link</span> عن <span dir="ltr">Physical</span>) |
| المطابقة مع <span dir="ltr">OSI</span> | <span dir="ltr">Application+Presentation+Session ➜ Application</span> \| <span dir="ltr">Network ➜ Internet</span> \| <span dir="ltr">Data Link+Physical ➜ Network Access</span> |
| بروتوكولات <span dir="ltr">Transport</span> | <span dir="ltr">TCP</span> (موثوق وبطيء) و <span dir="ltr">UDP</span> (سريع وغير موثوق) |
| <span dir="ltr">PDU</span> بالترتيب | <span dir="ltr">Data ➜ Segment/Datagram ➜ Packet ➜ Frame</span> |
| <span dir="ltr">Encapsulation</span> | تغليف البيانات بإضافة <span dir="ltr">Headers</span> عند جهاز الإرسال (من فوق لتحت) |
| <span dir="ltr">Decapsulation</span> | فك التغليف عند جهاز الاستقبال (من تحت لفوق) |
| سبب التسمية | نسبة لأشهر بروتوكولين فيه: <span dir="ltr">TCP</span> و <span dir="ltr">IP</span> |

</div>

</div>
