<div dir="rtl">

<div align="center">

# 🌐 الموضوع الحادي عشر: عنوان الـ IP وتقسيم الشبكات <span dir="ltr">(IP Address and Subnetting)</span>

<a href="#part1-ip-address">🟦 الجزء الأول: عنوان الـ IP</a> &nbsp;|&nbsp; <a href="#part2-subnetting">🟩 الجزء الثاني: تقسيم الشبكات</a>

</div>

## 📑 جدول المحتويات

| # | القسم الرئيسي | المواضيع الفرعية |
|:---:|:---:|:---:|
| - | <a href="#part1-ip-address">🟦 الجزء الأول: عنوان الـ IP</a> | - |
| 1 | <a href="#ip-definition-importance">تعريف عنوان الـ IP وأهميته</a> | - |
| 2 | <a href="#ipv4-components">مكونات عنوان الـ IPv4</a> | <a href="#ipv4-components"><span dir="ltr">Bit</span></a><br><a href="#ipv4-components"><span dir="ltr">Byte</span></a><br><a href="#ipv4-components"><span dir="ltr">Octet</span></a> |
| 3 | <a href="#ipv4-vs-ipv6">نبذة: <span dir="ltr">IPv4</span> مقابل <span dir="ltr">IPv6</span> (مقارنة كاملة)</a> | - |
| 4 | <a href="#ip-layer-nature">الطبقة التي يعمل بها الـ IP وثباته</a> | - |
| 5 | <a href="#ip-vs-mac">الفرق بين الـ <span dir="ltr">IP</span> والـ <span dir="ltr">MAC Address</span></a> | <a href="#ip-vs-mac">مراجعة الـ <span dir="ltr">MAC Address</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#ip-vs-mac">جدول المقارنة الكامل</a><br>&nbsp;&nbsp;&nbsp;<a href="#ip-vs-mac">ليه محتاجين عنوانين مش واحد بس</a><br>&nbsp;&nbsp;&nbsp;<a href="#ip-vs-mac"><span dir="ltr">Flat</span> مقابل <span dir="ltr">Hierarchical</span></a> |
| 6 | <a href="#iana">منظمة <span dir="ltr">IANA</span> وسجلات الإنترنت</a> | <a href="#iana">التسلسل الهرمي للسجلات</a><br>&nbsp;&nbsp;&nbsp;<a href="#iana">سجل <span dir="ltr">WHOIS</span></a> |
| 7 | <a href="#ip-classes">فئات الـ <span dir="ltr">IP (Classes A–E)</span></a> | <a href="#ip-classes">مدى كل فئة</a><br>&nbsp;&nbsp;&nbsp;<a href="#ip-classes">الفرق بين الفئات</a><br>&nbsp;&nbsp;&nbsp;<a href="#ip-classes">ليه <span dir="ltr">D, E</span> مالهمش <span dir="ltr">Subnet Mask</span></a> |
| 8 | <a href="#network-host-id">أجزاء عنوان الـ <span dir="ltr">IP</span>: <span dir="ltr">Network ID</span> و<span dir="ltr">Host ID</span></a> | - |
| 9 | <a href="#network-host-broadcast">أنواع العناوين داخل الشبكة</a> | <a href="#network-host-broadcast"><span dir="ltr">Network Address</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#network-host-broadcast"><span dir="ltr">Host Address</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#network-host-broadcast"><span dir="ltr">Broadcast Address</span></a> |
| 10 | <a href="#ip-types">أنواع عناوين الـ IP</a> | <a href="#private-public-ip"><span dir="ltr">Private</span> و<span dir="ltr">Public</span> (+فئات الـ Public لكل Class)</a><br>&nbsp;&nbsp;&nbsp;<a href="#apipa-virtual-ip"><span dir="ltr">APIPA</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#apipa-virtual-ip"><span dir="ltr">Virtual IP</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#multicast-loopback"><span dir="ltr">Multicast</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#multicast-loopback"><span dir="ltr">Loopback</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#reserved-addresses">عناوين محجوزة أخرى</a> |
| 11 | <a href="#network-address-benefit">فائدة عنوان الشبكة في التحكم والحماية</a> | <a href="#network-address-benefit"><span dir="ltr">ACL</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#network-address-benefit">مثال الجدار الناري</a> |
| 12 | <a href="#ip-assignment-methods">طرق حصول الجهاز على عنوان <span dir="ltr">IP</span> وإعداداته</a> | <a href="#assignment-table"><span dir="ltr">DHCP / DHCPv6 / Static / APIPA / EUI-64</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#default-gateway"><span dir="ltr">Default Gateway</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#devices-with-ip">الأجهزة التي تمتلك عنوان IP</a><br>&nbsp;&nbsp;&nbsp;<a href="#ipconfig-renew">أمر <span dir="ltr">ipconfig /renew</span></a> |
| 13 | <a href="#routing">التوجيه: جدول التوجيه وأنواع المسارات</a> | <a href="#routing-table">جدول التوجيه</a><br>&nbsp;&nbsp;&nbsp;<a href="#routing-protocols">بروتوكولات التوجيه</a><br>&nbsp;&nbsp;&nbsp;<a href="#router-uses-ip">كيف يستخدم الراوتر الـ IP للتوجيه</a><br>&nbsp;&nbsp;&nbsp;<a href="#default-vs-static-route"><span dir="ltr">Default Route</span> مقابل <span dir="ltr">Static Route</span></a> |
| 14 | <a href="#ip-header">عملية التغليف وهيدر الـ IP</a> | - |
| 15 | <a href="#ip-port-relationship">العلاقة بين IP والـ <span dir="ltr">Port Number</span></a> | <a href="#ip-port-relationship">مفهوم الـ <span dir="ltr">Socket</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#ip-port-relationship"><span dir="ltr">Source</span> و<span dir="ltr">Destination Port</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#ip-port-relationship">الـ <span dir="ltr">Ephemeral Ports</span></a> |
| 16 | <a href="#nat">ترجمة عناوين الشبكة <span dir="ltr">NAT</span></a> | <a href="#nat-types">أنواعه</a><br>&nbsp;&nbsp;&nbsp;<a href="#pat-home-router">مثال: راوتر منزلي بـ <span dir="ltr">IP</span> عام واحد لأكثر من 10 أجهزة</a><br>&nbsp;&nbsp;&nbsp;<a href="#nat-table-records">سجلات <span dir="ltr">NAT (NAT Table)</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#nat-terms">مصطلحاته</a> |
| 17 | <a href="#network-monitoring">مراقبة الشبكة عبر عنوان الـ IP</a> | - |
| - | <a href="#part2-subnetting">🟩 الجزء الثاني: تقسيم الشبكات</a> | - |
| 1 | <a href="#why-subnetting">مقدمة: ليه بنقسم الشبكة؟</a> | - |
| 2 | <a href="#subnet-mask-basics"><span dir="ltr">Subnet Mask</span>: تعريفه وقواعده</a> | - |
| 3 | <a href="#anding">عملية <span dir="ltr">ANDing</span></a> | - |
| 4 | <a href="#number-systems">أنظمة العد وطرق التحويل بينها</a> | <a href="#number-systems"><span dir="ltr">Base 10 / Base 2 / Base 16</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#weights-table">جدول الأوزان (الجدول السحري)</a><br>&nbsp;&nbsp;&nbsp;<a href="#binary-decimal-conversion">تحويل ديسيمال ↔ باينري</a><br>&nbsp;&nbsp;&nbsp;<a href="#binary-range">مدى الاحتمالات في الباينري</a><br>&nbsp;&nbsp;&nbsp;<a href="#hex-binary-conversion">تحويل هيكس ↔ باينري</a><br>&nbsp;&nbsp;&nbsp;<a href="#hex-range">مدى الاحتمالات في الهيكس</a><br>&nbsp;&nbsp;&nbsp;<a href="#bit-count-rule">معرفة عدد البتات لأي رقم</a> |
| 5 | <a href="#cidr">نظام <span dir="ltr">CIDR</span> وكتابة السلاش</a> | - |
| 6 | <a href="#subnetting-laws">القوانين الأساسية للتقسيم</a> | <a href="#subnetting-laws">عدد الشبكات <span dir="ltr">2ⁿ</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#subnetting-laws">عدد الأجهزة <span dir="ltr">2ʰ − 2</span></a><br>&nbsp;&nbsp;&nbsp;<a href="#subnetting-laws">حجم القفزة <span dir="ltr">Block Size</span></a> |
| 7 | <a href="#solving-steps">خطوات حل أي مسألة <span dir="ltr">Subnetting</span></a> | - |
| 8 | <a href="#worked-examples">أمثلة محلولة خطوة بخطوة</a> | <a href="#example-easy">مثال سهل</a><br>&nbsp;&nbsp;&nbsp;<a href="#example-medium">مثال متوسط (معطى: عدد الأجهزة)</a><br>&nbsp;&nbsp;&nbsp;<a href="#example-advanced">مثال متقدم (معطى: عدد الشبكات)</a> |
| 9 | <a href="#subnet-id-boundaries">حساب <span dir="ltr">Subnet ID</span> وحدود كل شبكة فرعية</a> | - |
| 10 | <a href="#vlsm"><span dir="ltr">VLSM</span>: التقسيم متغير الطول</a> | - |
| 11 | <a href="#supernetting"><span dir="ltr">Supernetting</span></a> | - |
| 12 | <a href="#identify-class">معرفة الفئة من الـ <span dir="ltr">IP</span> والـ <span dir="ltr">Subnet Mask</span></a> | - |
| 13 | <a href="#octet-split">تقسيم أوكتت واحد بين الشبكات والأجهزة</a> | - |
| 14 | <a href="#find-network-of-host">إيجاد عنوان شبكة جهاز معين</a> | - |
| - | <a href="#review-questions">❓ أسئلة المراجعة الشاملة</a> | - |

---

<h2 dir="rtl" align="right" id="part1-ip-address">🟦 الجزء الأول: عنوان الـ IP <span dir="ltr">(IP Address)</span></h2>

<h3 dir="rtl" align="right" id="ip-definition-importance">1. تعريف عنوان الـ IP وأهميته</h3>

عنوان الـ <span dir="ltr">IP (Internet Protocol Address)</span> هو عنوان **منطقي (Logical Address)** يُستخدم لتحديد هوية أي جهاز على الشبكة، ويعمل في **طبقة الشبكة (Network Layer)** — الطبقة الثالثة من نموذج الـ <span dir="ltr">OSI</span> (راجع [الموضوع الرابع](../4-osi-model.md))، وهو ما يقابله في نموذج الـ <span dir="ltr">TCP/IP</span> طبقة الـ <span dir="ltr">Internet Layer</span> (راجع [الموضوع السابع](../7-tcp-ip-model.md)).

**أهمية عنوان الـ IP:**
- بيسمح بتوجيه البيانات <span dir="ltr">(Routing)</span> بين شبكات مختلفة، وده أهم فرق بينه وبين عنوان الـ <span dir="ltr">MAC</span> اللي شغال جوه الشبكة الواحدة بس.
- بيدي كل جهاز هوية فريدة تسمح بالتواصل معاه من أي مكان في الإنترنت أو الشبكة الداخلية.
- بيحدد انتماء الجهاز لشبكة معينة (Network) من خلال جزء الـ <span dir="ltr">Network ID</span> منه، وهو ما يُبنى عليه كل موضوع الـ <span dir="ltr">Subnetting</span> في الجزء الثاني من هذا الملف.
- بيسمح بتقسيم الشبكات الكبيرة إلى شبكات أصغر (تفصيل كامل في <a href="#why-subnetting">الجزء الثاني</a>)، وهو ما يحقق فوائد كبيرة في الإدارة والتحكم والأمان.

---

<h3 dir="rtl" align="right" id="ipv4-components">2. مكونات عنوان الـ IPv4</h3>

عنوان الـ <span dir="ltr">IPv4</span> يتكون من **32 بت (Bit)** مقسمة إلى **4 أجزاء (Octets)**، كل جزء منها 8 بت (1 بايت)، ويُكتب بصيغة عشرية (Decimal) مفصولة بنقاط.

<div align="center">
<img src="images/11-1-ipv4-address-format.webp" width="700">
<br><em>شكل عنوان الـ IPv4: 4 أوكتت × 8 بت = 32 بت</em>
</div>

**المصطلحات الأساسية:**

| المصطلح | التعريف | مثال |
|:---:|:---:|:---:|
| <span dir="ltr">Bit</span> | أصغر وحدة بيانات، وقيمتها إما <span dir="ltr">0</span> أو <span dir="ltr">1</span> | البت الأول في `11000000` هو `1` |
| <span dir="ltr">Byte</span> | مجموعة من 8 بت | `11000000` = 1 بايت |
| <span dir="ltr">Octet</span> | نفس معنى الـ <span dir="ltr">Byte</span> لكن يُستخدم تحديدًا عند الحديث عن أجزاء عنوان الـ IP | في العنوان `192.168.43.241` كل رقم (192، 168، 43، 241) يمثل أوكتت واحد = 8 بت |

> 💡 كل أوكتت قيمته العشرية تتراوح من `0` إلى `255`، لأن أقصى قيمة ممكنة لـ 8 بت هي <span dir="ltr">2⁸ − 1 = 255</span>.

---

<h3 dir="rtl" align="right" id="ipv4-vs-ipv6">3. نبذة: IPv4 مقابل IPv6</h3>

<div align="center">
<img src="images/11-10-ipv4-vs-ipv6-comparison.png" width="600">
<br><em>مقارنة سريعة: طول العنوان وعدد العناوين المتاحة في IPv4 مقابل IPv6</em>
</div>

| المقارنة | <span dir="ltr">IPv4</span> | <span dir="ltr">IPv6</span> |
|:---:|:---:|:---:|
| الطول | 32 بت | 128 بت |
| عدد العناوين المتاحة | حوالي 4.3 مليار عنوان | عدد هائل (تقريبًا غير محدود عمليًا) |
| صيغة الكتابة | عشري مفصول بنقاط (مثال: `192.168.1.1`) | هيكساديسيمال مفصول بنقطتين رأسيتين (مثال: `2001:0db8::1`) |
| عدد الأجزاء | 4 أوكتتات | 8 مجموعات (كل مجموعة 16 بت) |
| هيدر الحزمة | معقّد نسبيًا (يحتوي حقول أكثر، منها ما هو نادر الاستخدام) | مبسّط ومحسّن للأداء (حقول أقل وأسرع في المعالجة عند الراوترات) |
| الحاجة لـ <span dir="ltr">NAT</span> | ضرورية غالبًا بسبب محدودية العناوين (راجع <a href="#nat">البند 16</a>) | غير ضرورية عادة، لأن كل جهاز يمكن أن يمتلك عنوان Public فريد خاص به |
| الإعداد التلقائي | يعتمد على <span dir="ltr">DHCP</span> بشكل أساسي | يدعم إعدادًا ذاتيًا بدون DHCP عبر <span dir="ltr">SLAAC (Stateless Address Autoconfiguration)</span> بالإضافة إلى DHCPv6 |
| البث <span dir="ltr">(Broadcast)</span> | موجود (Broadcast Address) | غير موجود إطلاقًا؛ تم الاستغناء عنه بالكامل لصالح Multicast وAnycast |
| الأمان | اختياري (IPSec يُضاف كطبقة إضافية) | مدمج ومصمَّم داخل البروتوكول من الأساس (IPSec جزء أصلي منه) |
| السبب في وجوده | — | نفاد عناوين IPv4 مع توسع الإنترنت، إضافة لحل مشكلة نفاد العناوين وتحسينات أمنية وأدائية |

> 📌 باقي هذا الملف يتناول <span dir="ltr">IPv4</span> بالتفصيل لأنه الأساس المطلوب في مقرر <span dir="ltr">Network+</span>.

---

<h3 dir="rtl" align="right" id="ip-layer-nature">4. الطبقة التي يعمل بها الـ IP وثباته</h3>

- يعمل عنوان الـ <span dir="ltr">IP</span> في **طبقة الشبكة (Layer 3 – Network Layer)** من نموذج الـ <span dir="ltr">OSI</span>، وهي المسؤولة عن التوجيه <span dir="ltr">(Routing)</span> واختيار أفضل مسار للبيانات (راجع تفاصيل الطبقة في [الموضوع الرابع](../4-osi-model.md) و[الموضوع السابع](../7-tcp-ip-model.md)).
- عنوان الـ IP **قابل للتغيير**: يمكن أن يتغير حسب الشبكة التي يتصل بها الجهاز، أو حسب طريقة التوزيع (يدوي أو تلقائي عبر <span dir="ltr">DHCP</span>) — على عكس عنوان الـ <span dir="ltr">MAC</span> الثابت المحفور في كرت الشبكة.

---

<h3 dir="rtl" align="right" id="ip-vs-mac">5. الفرق بين الـ IP والـ MAC Address</h3>

قبل المقارنة، لازم نراجع تعريف عنوان الـ <span dir="ltr">MAC</span> نفسه (تم شرحه بالتفصيل في [الموضوع التاسع – Ethernet/LAN](../9-ethernet-lan.md))، ونلخص أهم عناصره هنا للمقارنة:

- **تعريفه:** عنوان **مادي (Physical Address)** محفور في كرت الشبكة <span dir="ltr">(NIC)</span> من المصنع.
- **مكوناته ونظامه:** طوله 48 بت، ويُكتب بنظام <span dir="ltr">Hexadecimal (Base 16)</span> في صورة 6 أزواج (مثال: `00:1A:2B:3C:4D:5E`).
- **تقسيماته:** أول 24 بت (3 بايت) تمثل <span dir="ltr">OUI (Organizationally Unique Identifier)</span> — معرف الشركة المصنّعة — وآخر 24 بت تمثل **معرف كرت الشبكة نفسه (NIC-specific)**، وفائدة هذا التقسيم أنه يضمن عدم تكرار نفس الـ MAC عالميًا.
- **الطبقة التي يعمل بها:** طبقة ربط البيانات <span dir="ltr">(Data Link Layer – Layer 2)</span>.
- **ثباته:** ثابت لا يتغير (إلا بتقنيات معينة مثل <span dir="ltr">MAC Spoofing</span>).
- **منظمته:** تُدار بواسطة <span dir="ltr">IEEE</span>، وهي المسؤولة عن توزيع أرقام الـ <span dir="ltr">OUI</span> على الشركات المصنّعة.

**جدول المقارنة الكامل:**

| وجه المقارنة | <span dir="ltr">IP Address</span> | <span dir="ltr">MAC Address</span> |
|:---:|:---:|:---:|
| النوع | منطقي <span dir="ltr">(Logical)</span> | مادي <span dir="ltr">(Physical)</span> |
| الطبقة | Layer 3 – Network | Layer 2 – Data Link |
| الطول | 32 بت (IPv4) | 48 بت |
| نظام الكتابة | عشري (Decimal) | هيكساديسيمال (Hex) |
| الثبات | قابل للتغيير | ثابت |
| الجهة المسؤولة | <span dir="ltr">IANA</span> | <span dir="ltr">IEEE</span> |
| نوع العنونة | هرمي <span dir="ltr">(Hierarchical)</span> | مسطح <span dir="ltr">(Flat)</span> |
| الاستخدام | التوجيه بين شبكات مختلفة | التواصل داخل نفس الشبكة المحلية |

**ليه محتاجين عنوانين مش عنوان واحد بس؟**
لأن العنوان المادي (MAC) وحده لا يكفي للتوجيه بين شبكات مختلفة حول العالم — فهو غير هرمي <span dir="ltr">(Flat)</span> ولا يحمل أي معلومة عن موقع الجهاز أو الشبكة التي ينتمي إليها. عنوان الـ IP هرمي <span dir="ltr">(Hierarchical)</span> يحمل جزءًا يدل على الشبكة وجزءًا يدل على الجهاز، وهو ما يمكّن أجهزة التوجيه <span dir="ltr">(Routers)</span> من إيصال البيانات عبر شبكات متعددة دون معرفة تفاصيل كل جهاز على حدة.

> 🔗 **خاصية الترتيب الهرمي مقابل المسطح:** عنوان الـ IP خاصية أساسية فيه أنه <span dir="ltr">Hierarchical Address</span> (به تدرج: شبكة ثم جهاز)، بينما عنوان الـ MAC هو <span dir="ltr">Flat Address</span> (لا تدرج فيه، كل عنوان مستقل تمامًا عن الآخر). هذا الفرق هو السبب الجوهري في إمكانية عمل الـ <span dir="ltr">Subnetting</span> على مستوى الـ IP فقط، وسنعتمد عليه بشكل كامل في <a href="#part2-subnetting">الجزء الثاني</a>.

---

<h3 dir="rtl" align="right" id="iana">6. منظمة IANA وسجلات الإنترنت</h3>

<span dir="ltr">IANA (Internet Assigned Numbers Authority)</span> هي **السلطة العالمية المسؤولة عن تخصيص أرقام الإنترنت**، بما في ذلك توزيعات وأقسام وفئات وأنواع عناوين الـ <span dir="ltr">IP</span>، وكذلك أرقام الـ <span dir="ltr">Ports</span> (راجع [الموضوع الخامس](../5-port-numbers.md)) والبروتوكولات.

تتفرع من IANA **خمس منظمات إقليمية (RIRs – Regional Internet Registries)** تتولى توزيع عناوين الـ IP على مستوى كل قارة/منطقة:

| المنظمة | المنطقة المسؤولة عنها |
|:---:|:---:|
| <span dir="ltr">ARIN</span> | أمريكا الشمالية |
| <span dir="ltr">RIPE NCC</span> | أوروبا والشرق الأوسط وآسيا الوسطى |
| <span dir="ltr">APNIC</span> | آسيا والمحيط الهادئ |
| <span dir="ltr">LACNIC</span> | أمريكا اللاتينية والكاريبي |
| <span dir="ltr">AFRINIC</span> | أفريقيا |

**التسلسل الهرمي لسجلات الإنترنت (Internet Registries):**
توزيع عناوين الـ IP لا يحدث دفعة واحدة من IANA مباشرة لكل مستخدم، بل عبر تسلسل هرمي من السجلات:

```
IANA (السلطة العالمية)
   ↓
RIRs الخمس (توزيع إقليمي: ARIN, RIPE NCC, APNIC, LACNIC, AFRINIC)
   ↓
ISPs / LIRs (مزودو خدمة الإنترنت والسجلات المحلية الكبرى)
   ↓
المستخدم النهائي (شركتك، منزلك)
```

**سجل الـ <span dir="ltr">WHOIS</span>:** قاعدة بيانات عامة يمكن لأي شخص الاستعلام منها لمعرفة الجهة المالكة لأي عنوان IP عام أو نطاق (Domain)، وتُدار بيانات هذا السجل بواسطة الـ RIRs كل حسب منطقته.

---

<h3 dir="rtl" align="right" id="ip-classes">7. فئات الـ IP (Classes A–E)</h3>

عناوين الـ <span dir="ltr">IPv4</span> مقسّمة إلى 5 فئات <span dir="ltr">(Classes)</span> حسب قيمة أول أوكتت:

<div align="center">
<img src="images/11-2-classes-first-octet-range.png" width="500">
<br><em>مدى أول أوكتت لكل فئة</em>
</div>

| الفئة | مدى أول أوكتت | الاستخدام | عدد الأجهزة القصوى |
|:---:|:---:|:---:|:---:|
| <span dir="ltr">Class A</span> | 1 – 126 | مؤسسات ضخمة جدًا | 16,777,214 |
| <span dir="ltr">Class B</span> | 128 – 191 | مؤسسات متوسطة الحجم | 65,534 |
| <span dir="ltr">Class C</span> | 192 – 223 | مؤسسات صغيرة | 254 |
| <span dir="ltr">Class D</span> | 224 – 239 | البث المتعدد <span dir="ltr">(Multicast)</span> | — |
| <span dir="ltr">Class E</span> | 240 – 254 | أغراض بحثية/تجريبية <span dir="ltr">(Research)</span> | — |

> ملاحظة: النطاق `127.x.x.x` محجوز لعنوان الاسترجاع الذاتي <span dir="ltr">Loopback Address</span>، وهو غير مُتاح للاستخدام كعنوان جهاز عادي (تفصيل كامل في <a href="#ip-types">البند العاشر</a>).

**السابنت ماسك الافتراضي لكل فئة:**

<div align="center">
<img src="images/11-3-classes-default-subnet-mask.png" width="500">
<br><em>Subnet Mask الافتراضي لكل فئة</em>
</div>

| الفئة | Subnet Mask الافتراضي | صيغة CIDR |
|:---:|:---:|:---:|
| Class A | `255.0.0.0` | `/8` |
| Class B | `255.255.0.0` | `/16` |
| Class C | `255.255.255.0` | `/24` |

**كيف توزّع كل فئة الأوكتتات بين Network و Host:**

<div align="center">
<img src="images/11-6-classes-network-host-bits-diagram.png" width="600">
<br><em>توزيع الأوكتتات الأربعة بين Network و Host لكل فئة</em>
</div>

- <span dir="ltr">Class A</span>: أول أوكتت فقط ثابت للشبكة (Network)، والثلاثة الباقية للأجهزة. عدد الشبكات قليل جدًا، لكن عدد الأجهزة المتاحة في كل شبكة ضخم جدًا.
- <span dir="ltr">Class B</span>: أول أوكتتين ثابتين للشبكة، والأوكتتين الباقيين للأجهزة.
- <span dir="ltr">Class C</span>: أول ثلاثة أوكتتات ثابتة للشبكة، والأوكتت الأخير فقط للأجهزة. عدد الشبكات كبير جدًا، لكن عدد الأجهزة المتاحة في كل شبكة قليل نسبيًا (مناسبة للمنازل والشركات الصغيرة).

<div align="center">
<img src="images/11-11-class-a-network-host-breakdown.png" width="550">
<br><em>Class A بالتفصيل: مدى الأوكتت الأول (1–126)، توزيع Network/Host، وخاصية "عدد شبكات قليل، عدد أجهزة كبير"</em>
</div>

<div align="center">
<img src="images/11-12-class-b-network-host-breakdown.png" width="550">
<br><em>Class B بالتفصيل: مدى الأوكتت الأول (128–191) وتوزيع Network/Host</em>
</div>

<div align="center">
<img src="images/11-13-class-c-network-host-breakdown.png" width="550">
<br><em>Class C بالتفصيل: مدى الأوكتت الأول (192–223)، وخاصية "شبكات كثيرة بعدد أجهزة قليل" المناسبة للمنازل والشركات الصغيرة</em>
</div>

**ليه Class D و E مالهمش Subnet Mask؟**
لأنهما غير مخصصين لعناوين أجهزة عادية على الإطلاق:
- <span dir="ltr">Class D</span> مخصصة بالكامل لعناوين البث المتعدد <span dir="ltr">(Multicast)</span>، وهي تمثل مجموعة من الأجهزة وليست جهازًا واحدًا، فلا معنى لتقسيمها إلى Network/Host.
- <span dir="ltr">Class E</span> محجوزة للأغراض البحثية والتجريبية ولم تُطرح للاستخدام العام.

---

<h3 dir="rtl" align="right" id="network-host-id">8. أجزاء عنوان الـ IP: Network ID و Host ID</h3>

<div align="center">
<img src="images/11-4-network-id-host-id-table.png" width="700">
<br><em>تقسيم Network ID إلى جزء Network وجزء Host، وجدول الفئات الكامل</em>
</div>

كل عنوان <span dir="ltr">IP</span> ينقسم منطقيًا لجزئين:

| الجزء | معناه |
|:---:|:---:|
| <span dir="ltr">Network ID</span> | الجزء الثابت الذي يجب أن يكون **متطابقًا** لكل الأجهزة الموجودة على نفس الشبكة (نفس الـ Switch)، وهو يقابل البتات التي قيمتها `1` في الـ Subnet Mask |
| <span dir="ltr">Host ID</span> | الجزء **المتغير** من جهاز لآخر داخل نفس الشبكة، ويقابل البتات التي قيمتها `0` في الـ Subnet Mask |

**جدول الفئات الكامل (المدى + الصيغة + الاستخدام):**

| Class | الصيغة | الاستخدام | مدى العناوين | أقصى عدد Hosts |
|:---:|:---:|:---:|:---:|:---:|
| A | N.H.H.H | مؤسسات كبيرة قليلة العدد | `1.0.0.0 – 126.0.0.0` | 16,777,214 |
| B | N.N.H.H | مؤسسات متوسطة الحجم | `128.1.0.0 – 191.254.0.0` | 65,534 |
| C | N.N.N.H | مؤسسات صغيرة نسبيًا | `192.0.1.0 – 223.255.254.0` | 254 |

> 💡 **قاعدة الثبات حسب الفئة:** في <span dir="ltr">Class A</span> يجب أن يكون أول أوكتت ثابتًا، في <span dir="ltr">Class B</span> يجب أن يكون أول أوكتتين ثابتين، وفي <span dir="ltr">Class C</span> يجب أن تكون أول ثلاثة أوكتتات ثابتة داخل الشبكة الواحدة.

---

<h3 dir="rtl" align="right" id="network-host-broadcast">9. أنواع العناوين داخل الشبكة</h3>

| النوع | التعريف | مثال (على شبكة `192.168.1.0/24`) |
|:---:|:---:|:---:|
| <span dir="ltr">Network Address</span> | أول عنوان في نطاق الشبكة، يمثل الشبكة نفسها ولا يُخصَّص لأي جهاز | `192.168.1.0` |
| <span dir="ltr">Host Address</span> | أي عنوان بين عنوان الشبكة وعنوان البث، يُخصَّص فعليًا لجهاز | `192.168.1.1` إلى `192.168.1.254` |
| <span dir="ltr">Broadcast Address</span> | آخر عنوان في نطاق الشبكة، يُستخدم لإرسال بيانات لكل الأجهزة على الشبكة دفعة واحدة | `192.168.1.255` |

> 🔗 هذا التقسيم هو نفس السبب في معادلة عدد الأجهزة <span dir="ltr">2ʰ − 2</span> التي سنشرحها بالتفصيل في <a href="#subnetting-laws">الجزء الثاني</a>، لأن عنواني الشبكة والبث محجوزان دائمًا ولا يُحسبان ضمن الأجهزة القابلة للاستخدام.

---

<h3 dir="rtl" align="right" id="ip-types">10. أنواع عناوين الـ IP</h3>

<h4 dir="rtl" align="right" id="private-public-ip">أ. Private و Public IP</h4>

| النوع | الوصف |
|:---:|:---:|
| <span dir="ltr">Private IP</span> (خاص) | عناوين محجوزة للاستخدام داخل الشبكات المحلية فقط، غير قابلة للتوجيه على الإنترنت العام |
| <span dir="ltr">Public IP</span> (عام) | عناوين فريدة عالميًا يمكن الوصول إليها عبر الإنترنت |

**نطاقات الـ Private IP (RFC 1918)** — سبق ذكرها في [الموضوع السابع](../7-tcp-ip-model.md):

| الفئة | النطاق الخاص |
|:---:|:---:|
| Class A | `10.0.0.0 – 10.255.255.255` |
| Class B | `172.16.0.0 – 172.31.255.255` |
| Class C | `192.168.0.0 – 192.168.255.255` |

<div align="center">
<img src="images/11-14-private-ip-classes-table.png" width="600">
<br><em>جدول Private IP Address Classes: النطاق، الـ Subnet Mask الافتراضي، والاستخدام النموذجي لكل فئة</em>
</div>

**عناوين الـ Public IP حسب كل فئة:** أي عنوان داخل مدى الفئة (المذكور في <a href="#ip-classes">البند السابع</a>) ولا يقع ضمن النطاقات الخاصة أعلاه ولا ضمن النطاقات المحجوزة الأخرى (مثل APIPA أو Loopback) يُعتبر تلقائيًا **عنوان Public** قابل للتوجيه على الإنترنت:

| الفئة | مدى الفئة الكامل | الجزء الخاص (Private) منها | الباقي متاح كـ Public |
|:---:|:---:|:---:|:---:|
| Class A | `1.0.0.0 – 126.255.255.255` | `10.0.0.0 – 10.255.255.255` فقط | كل الباقي |
| Class B | `128.0.0.0 – 191.255.255.255` | `172.16.0.0 – 172.31.255.255` فقط | كل الباقي |
| Class C | `192.0.0.0 – 223.255.255.255` | `192.168.0.0 – 192.168.255.255` فقط | كل الباقي |

> 💡 يعني عمليًا: كل عنوان Public IP بترجعله شركتك أو الراوتر بتاعك من الـ ISP، هو عنوان مُنتقى من نفس فئات A/B/C العادية، لكنه خارج النطاقات الخاصة المحجوزة، وهو ما يخلّيه صالحًا للظهور والتوجيه على الإنترنت العام مباشرة.

<h4 dir="rtl" align="right" id="apipa-virtual-ip">ب. APIPA و Virtual IP</h4>

| النوع | الوصف |
|:---:|:---:|
| <span dir="ltr">APIPA</span> (تلقائي) | عنوان يُخصصه الجهاز لنفسه تلقائيًا (بمدى `169.254.0.0/16`) عند فشل الحصول على IP من DHCP |
| <span dir="ltr">Virtual IP</span> (افتراضي) | عنوان IP غير مرتبط بكرت شبكة فعلي واحد، يُستخدم غالبًا في موازنة الأحمال <span dir="ltr">(Load Balancing)</span> أو أنظمة التعافي من الكوارث لتمثيل عدة أجهزة بعنوان واحد |

<h4 dir="rtl" align="right" id="multicast-loopback">ج. Multicast و Loopback Address</h4>

| النوع | الوصف |
|:---:|:---:|
| <span dir="ltr">Multicast Address</span> (بث متعدد) | عنوان من نطاق <span dir="ltr">Class D</span> (`224.0.0.0 – 239.255.255.255`) يمثل مجموعة من الأجهزة معًا، وليس جهازًا واحدًا؛ يُستخدم لإرسال بيانات لمجموعة مشتركين محددة فقط (بدلًا من كل الشبكة كما في Broadcast) |
| <span dir="ltr">Loopback Address</span> (الاسترجاع الذاتي) | النطاق `127.0.0.0/8` (وأشهر مثال `127.0.0.1`)، يُستخدم لاختبار كرت الشبكة والبرمجيات على نفس الجهاز دون إرسال أي بيانات فعليًا على الشبكة |

<h4 dir="rtl" align="right" id="reserved-addresses">د. عناوين محجوزة أخرى</h4>

| العنوان | الاستخدام |
|:---:|:---:|
| `0.0.0.0` | يمثل "أي عنوان غير معروف/غير محدد بعد"، يُستخدم أحيانًا كعنوان مصدر مؤقت قبل حصول الجهاز على IP فعلي |
| `255.255.255.255` | عنوان البث المحدود <span dir="ltr">(Limited Broadcast)</span>، يرسل لكل الأجهزة على الشبكة المحلية بغض النظر عن عنوان الشبكة |

---

<h3 dir="rtl" align="right" id="network-address-benefit">11. فائدة عنوان الشبكة في التحكم والحماية</h3>

من أهم فوائد عنوان الشبكة أنه يسمح بتطبيق قواعد التحكم <span dir="ltr">(Access Control List – ACL)</span> على **شبكة كاملة بعنوان واحد**، بدلًا من التعامل مع كل جهاز على حدة. الـ <span dir="ltr">ACL</span> هي قائمة قواعد تُطبَّق عادةً على الراوتر أو الجدار الناري <span dir="ltr">(Firewall)</span> لتحديد أي حركة بيانات مسموح بها وأيها ممنوعة.

**مثال تطبيقي:** لو عايزين نمنع شبكة فيها 200 جهاز من الوصول إلى الإنترنت، فبدلًا من إضافة 200 قاعدة منفصلة (عنوان كل جهاز على حدة) داخل سيرفر الجدار الناري، يكفي كتابة **قاعدة واحدة تستهدف عنوان الشبكة نفسه** (مثال: `192.168.10.0/24`)، وتُطبَّق تلقائيًا على كل الأجهزة المنتمية لهذه الشبكة.

هذا المبدأ نفسه هو أساس فائدة تقسيم مجال البث <span dir="ltr">(Broadcast Domain)</span> عن طريق الـ Subnetting: فكل ما كانت الشبكة أصغر (بعد التقسيم)، كل ما كان التحكم فيها والتعامل معها إداريًا وأمنيًا أسهل وأدق، وقلّ الازدحام الناتج عن رسائل البث (تفصيل كامل في <a href="#why-subnetting">بداية الجزء الثاني</a>).

---

<h3 dir="rtl" align="right" id="ip-assignment-methods">12. طرق حصول الجهاز على عنوان IP وإعداداته</h3>

<h4 dir="rtl" align="right" id="assignment-table">أ. طرق التوزيع</h4>

| الطريقة | الوصف |
|:---:|:---:|
| <span dir="ltr">DHCP</span> | توزيع تلقائي لعنوان IPv4 من سيرفر مخصص (راجع تفاصيل عملية <span dir="ltr">DORA</span> في [الموضوع العاشر](../10-network-devices.md)) |
| <span dir="ltr">DHCPv6</span> | نفس فكرة DHCP لكن لتوزيع عناوين IPv6 |
| <span dir="ltr">Static</span> | تعيين العنوان يدويًا من قِبل المسؤول عن الشبكة، ويظل ثابتًا حتى يُغيَّر يدويًا |
| <span dir="ltr">APIPA</span> | تعيين ذاتي تلقائي (`169.254.x.x`) عند فشل الجهاز في الوصول لسيرفر DHCP |
| <span dir="ltr">EUI-64</span> | آلية تلقائية (تُستخدم غالبًا مع IPv6) يُشتق فيها الجزء الخاص بالجهاز من عنوان الـ IP مباشرة من عنوان الـ MAC الخاص به |

<h4 dir="rtl" align="right" id="default-gateway">ب. Default Gateway</h4>

<span dir="ltr">Default Gateway</span> هو عنوان الـ <span dir="ltr">IP</span> الخاص بالراوتر (أو أي جهاز توجيه) الذي يستخدمه الجهاز للخروج من شبكته المحلية إلى أي شبكة أخرى (بما في ذلك الإنترنت). أي بيانات وجهتها خارج نطاق الشبكة المحلية للجهاز تُرسَل أولًا إلى الـ Default Gateway ليتولى هو توجيهها.

بالإضافة لعنوان الـ IP نفسه، يحتاج الجهاز عادة **إعدادات مصاحبة** حتى يقدر يتواصل بشكل كامل، أهمها: الـ <span dir="ltr">Subnet Mask</span>، والـ <span dir="ltr">Default Gateway</span>، وخادم الـ <span dir="ltr">DNS</span> (راجع تفاصيل الـ DNS في [الموضوع العاشر](../10-network-devices.md)) — وكلها تُوزَّع تلقائيًا مع الـ IP عند استخدام DHCP.

<h4 dir="rtl" align="right" id="devices-with-ip">ج. الأجهزة التي تمتلك عنوان IP</h4>

أي جهاز يحتاج التواصل عبر الشبكة يحتاج عنوان IP، وهذا يشمل: أجهزة الكمبيوتر والهواتف، الطابعات الشبكية، الراوترات والسويتشات القابلة للإدارة <span dir="ltr">(Managed Switches)</span>، الكاميرات الأمنية، وأجهزة إنترنت الأشياء <span dir="ltr">(IoT)</span> بشكل عام — أي جهاز "ذكي" متصل بالشبكة يحتاج عنوانًا فريدًا للتواصل.

<h4 dir="rtl" align="right" id="ipconfig-renew">د. أمر ipconfig /renew</h4>

أمر يُستخدم في أنظمة <span dir="ltr">Windows</span> لإجبار الجهاز على تجديد طلب الحصول على عنوان IP جديد من سيرفر الـ <span dir="ltr">DHCP</span>، ويُستخدم غالبًا عند حدوث مشاكل في الاتصال أو عند الحاجة لتحديث إعدادات الشبكة يدويًا دون إعادة تشغيل الجهاز.

---

<h3 dir="rtl" align="right" id="routing">13. التوجيه: جدول التوجيه وأنواع المسارات</h3>

<h4 dir="rtl" align="right" id="routing-table">أ. جدول التوجيه</h4>

**جدول التوجيه <span dir="ltr">(Routing Table)</span>** هو جدول موجود داخل كل راوتر، يحتوي على المعلومات التي يحتاجها لتحديد أفضل مسار لإرسال البيانات، وأهم محتوياته:
- عنوان الشبكة الوجهة <span dir="ltr">(Destination Network)</span>
- الـ Subnet Mask الخاص بها
- عنوان القفزة التالية <span dir="ltr">(Next Hop)</span>
- واجهة الخروج <span dir="ltr">(Exit Interface)</span>

<h4 dir="rtl" align="right" id="routing-protocols">ب. بروتوكولات التوجيه</h4>

**بروتوكولات التوجيه <span dir="ltr">(Routing Protocols)</span>** هي البروتوكولات التي تستخدمها الراوترات لتبادل معلومات المسارات بينها بشكل تلقائي وبناء جداول التوجيه (مثل <span dir="ltr">RIP, OSPF, EIGRP, BGP</span>) — سيتم التوسع فيها بالتفصيل عند دراسة موضوع التوجيه المتقدم لاحقًا في المسار.

<h4 dir="rtl" align="right" id="router-uses-ip">ج. كيف يستخدم الراوتر الـ IP للتوجيه</h4>

عندما تصل حزمة بيانات إلى الراوتر، يقارن الراوتر عنوان الشبكة الوجهة (المُستخرَج من عنوان الـ IP الوجهة عبر عملية <span dir="ltr">ANDing</span> — انظر <a href="#anding">البند الثالث من الجزء الثاني</a>) بالمسارات المخزّنة في جدول التوجيه الخاص به، ويختار أفضل مسار مطابق (عادة الأكثر تحديدًا)، ثم يعيد توجيه الحزمة عبر واجهة الخروج المناسبة نحو القفزة التالية، وتتكرر هذه العملية عند كل راوتر في الطريق حتى تصل الحزمة لوجهتها النهائية.

<h4 dir="rtl" align="right" id="default-vs-static-route">د. Default Route مقابل Static Route</h4>

| النوع | التعريف | متى يُستخدم |
|:---:|:---:|:---:|
| <span dir="ltr">Static Route</span> | مسار مُحدَّد يدويًا من قِبل المسؤول لشبكة وجهة **معينة** بالتحديد | عند الحاجة للتحكم الدقيق في مسار شبكة أو شبكات معينة بعينها |
| <span dir="ltr">Default Route</span> | مسار "افتراضي" يُستخدم كحل احتياطي شامل لأي وجهة **غير موجودة** في جدول التوجيه، ويُكتب عادة بصيغة `0.0.0.0/0` | عند الحاجة لتوجيه أي بيانات لا تطابق أي مسار محدد آخر (غالبًا للخروج إلى الإنترنت) |

**الفرق الجوهري:** الـ Static Route محدد ودقيق لشبكة بعينها، بينما الـ Default Route عام وشامل ويُستخدم كملاذ أخير عندما لا يجد الراوتر أي مسار أكثر تحديدًا يطابق وجهة الحزمة.

---

<h3 dir="rtl" align="right" id="ip-header">14. عملية التغليف وهيدر الـ IP</h3>

عند إرسال البيانات، يقوم الجهاز بعملية **التغليف <span dir="ltr">(Encapsulation)</span>** التي شُرحت بالتفصيل في [الموضوع الرابع](../4-osi-model.md) و[الموضوع السابع](../7-tcp-ip-model.md)، حيث تُضاف عند طبقة الشبكة معلومات **هيدر الـ IP <span dir="ltr">(IP Header)</span>** والتي تحتوي على أهم الحقول التالية:

| الحقل | الوظيفة |
|:---:|:---:|
| <span dir="ltr">Source IP</span> | عنوان الجهاز المُرسِل |
| <span dir="ltr">Destination IP</span> | عنوان الجهاز المستقبِل |
| <span dir="ltr">TTL (Time to Live)</span> | يحدد أقصى عدد قفزات <span dir="ltr">(Hops)</span> يمكن أن تمر بها الحزمة قبل إسقاطها، لمنع دورانها إلى الأبد |
| <span dir="ltr">Protocol</span> | يوضح البروتوكول المستخدم في الطبقة الأعلى (مثل TCP أو UDP، راجع [الموضوع السابع](../7-tcp-ip-model.md)) |

---

<h3 dir="rtl" align="right" id="ip-port-relationship">15. العلاقة بين IP والـ Port Number</h3>

عنوان الـ <span dir="ltr">IP</span> وحده **يحدد الجهاز** فقط، لكنه لا يحدد **أي برنامج أو خدمة** داخل هذا الجهاز يجب أن يستقبل البيانات. هنا يأتي دور رقم الـ <span dir="ltr">Port</span> (تم شرحه بالتفصيل الكامل في [الموضوع الخامس](../5-port-numbers.md)):

| العنصر | الطبقة | الوظيفة |
|:---:|:---:|:---:|
| <span dir="ltr">IP Address</span> | Layer 3 – Network | يحدد **الجهاز** (مين المُرسِل ومين المستقبِل) |
| <span dir="ltr">Port Number</span> | Layer 4 – Transport | يحدد **الخدمة/البرنامج** المطلوب داخل هذا الجهاز (مثل متصفح، بريد إلكتروني، لعبة أونلاين...) |

**الـ Socket:** الدمج بين عنوان الـ IP ورقم الـ Port معًا (مثال: `192.168.1.10:443`) يُكوّن ما يُسمى <span dir="ltr">Socket</span>، وهو ما يحدد بدقة متناهية **جهازًا بعينه + خدمة بعينها عليه** — وهو نفس مفهوم الـ <span dir="ltr">Socket Pair / 4-Tuple</span> الذي شُرح بالتفصيل في [الموضوع الخامس](../5-port-numbers.md).

**ما الذي "يُضاف" لعنوان الـ IP علشان الجهاز يقدر يطلع على الإنترنت؟**
عند إرسال أي طلب (مثل فتح موقع على المتصفح)، الجهاز لا يرسل عنوان الـ IP بمفرده، بل يرفقه بالمعلومات التالية:

1. **Destination Port:** رقم Port ثابت ومعروف للخدمة المطلوبة على السيرفر البعيد (مثال: `443` لـ HTTPS، `80` لـ HTTP).
2. **Source Port:** رقم Port **عشوائي** يختاره الجهاز المُرسِل لنفسه من نطاق الـ <span dir="ltr">Ephemeral Ports</span> (منافذ مؤقتة، عادة من `49152` إلى `65535`) — وهذا الرقم هو ما يسمح للجهاز بالتفريق بين عدة اتصالات مفتوحة في نفس الوقت (مثال: فتح أكتر من تبويب في المتصفح على نفس الموقع، كل تبويب له Source Port مختلف).

> 🔗 مفهوم الـ Ephemeral Ports واختياره العشوائي تم شرحه بالتفصيل في [الموضوع السادس – OSI Practical Lab](../6-osi-practical-lab.md).

---

<h3 dir="rtl" align="right" id="nat">16. ترجمة عناوين الشبكة NAT</h3>

<span dir="ltr">NAT (Network Address Translation)</span> هي تقنية تُستخدم لترجمة عناوين الـ <span dir="ltr">IP</span> الخاصة <span dir="ltr">(Private)</span> غير القابلة للتوجيه على الإنترنت إلى عنوان IP عام <span dir="ltr">(Public)</span> واحد أو أكثر، والعكس.

**فوائد ووظيفة NAT:**
- تسمح لعدة أجهزة داخل شبكة محلية بمشاركة عنوان IP عام واحد للوصول إلى الإنترنت، مما يقلل الحاجة لعناوين عامة كثيرة (يعالج جزئيًا مشكلة نفاد عناوين IPv4).
- تضيف طبقة أمان إضافية، لأن الأجهزة الداخلية غير مرئية مباشرة من الإنترنت الخارجي.

<h4 dir="rtl" align="right" id="nat-types">أ. أنواع NAT</h4>

| النوع | الوصف |
|:---:|:---:|
| <span dir="ltr">Static NAT</span> | ترجمة ثابتة عنوان خاص واحد ↔ عنوان عام واحد بشكل دائم |
| <span dir="ltr">Dynamic NAT</span> | ترجمة من مجموعة عناوين خاصة إلى مجموعة عناوين عامة، بشكل تلقائي غير ثابت |
| <span dir="ltr">PAT (Port Address Translation)</span> | يُعرف أيضًا بـ <span dir="ltr">NAT Overload</span>، يسمح لعدة أجهزة بمشاركة عنوان IP عام واحد عن طريق التفريق بينهم بأرقام Ports مختلفة |

<h4 dir="rtl" align="right" id="pat-home-router">ب. مثال تطبيقي: إزاي راوتر منزلي بـ IP عام واحد يخدم أكثر من 10 أجهزة</h4>

هذا هو التطبيق العملي الأشهر لـ <span dir="ltr">PAT</span>، ويعتمد بالكامل على <a href="#ip-port-relationship">العلاقة بين IP والـ Port</a> المشروحة أعلاه:

الراوتر المنزلي عادة عنده **عنوان Public IP واحد فقط** من مزود الخدمة <span dir="ltr">(ISP)</span>، بينما كل جهاز داخل المنزل (موبايل، لابتوب، سمارت تي في...) له **عنوان Private IP مختلف**. عند خروج أي جهاز للإنترنت:

1. الجهاز يرسل طلبه بعنوانه الخاص (Private IP) + Source Port عشوائي اختاره هو لنفسه.
2. الراوتر يستقبل الطلب، ويستبدل عنوان الـ IP الخاص بعنوانه العام (Public IP) الوحيد، **لكنه يغيّر رقم الـ Source Port لرقم عشوائي جديد فريد** لا يتعارض مع أي جهاز آخر متصل في نفس اللحظة.
3. الراوتر يسجّل هذه العملية في **جدول ترجمة (NAT Table)** داخلي يربط بين: (Private IP + Port الأصلي للجهاز) ⬌ (Public IP + Port الجديد المُخصَّص).
4. لما يرجع الرد من الإنترنت لنفس الـ Port الجديد، الراوتر يرجع لجدول الترجمة، يعرف بالظبط الرد ده خاص بأنهي جهاز داخلي، ويوجهه له.

**مثال مبسط:**

| الجهاز | Private IP | Source Port الأصلي | بعد الترجمة (Public IP:Port) |
|:---:|:---:|:---:|:---:|
| موبايل 1 | `192.168.1.10` | `51000` | `41.32.10.5:61001` |
| لابتوب | `192.168.1.11` | `51000` | `41.32.10.5:61002` |
| سمارت تي في | `192.168.1.12` | `52310` | `41.32.10.5:61003` |

لاحظ أن الـ Public IP **واحد ثابت** لكل الأجهزة (`41.32.10.5`)، لكن رقم الـ Port المُترجَم مختلف لكل اتصال — وهذا بالضبط ما يسمح بتمييز آلاف الاتصالات المتزامنة عبر عنوان Public واحد فقط، لأن نطاق أرقام الـ Port يصل لـ 65,535 رقم مختلف لكل عنوان IP.

<h4 dir="rtl" align="right" id="nat-table-records">ج. سجلات NAT (NAT Table / NAT Records)</h4>

**جدول ترجمة الـ NAT <span dir="ltr">(NAT Table)</span>** هو السجل الفعلي الذي يحتفظ به الراوتر (أو جدار الحماية) لكل عملية ترجمة تحدث، وهو ما يجعل عملية الـ <a href="#pat-home-router">PAT</a> ممكنة أصلًا. كل سطر (سجل/Record) في هذا الجدول يحتوي عادةً على الحقول التالية:

| الحقل | الوظيفة |
|:---:|:---:|
| <span dir="ltr">Private IP : Private Port</span> | عنوان ومنفذ الجهاز الداخلي الأصليين قبل الترجمة |
| <span dir="ltr">Public IP : Public Port</span> | عنوان ومنفذ الراوتر العام بعد الترجمة (المُستخدَم فعليًا على الإنترنت) |
| <span dir="ltr">Destination IP : Destination Port</span> | عنوان ومنفذ السيرفر البعيد الذي يتواصل معه الجهاز |
| <span dir="ltr">Protocol</span> | نوع البروتوكول المستخدم (<span dir="ltr">TCP</span> أو <span dir="ltr">UDP</span>، راجع <a href="#ip-port-relationship">البند 15</a>) |
| <span dir="ltr">Timeout / Idle Time</span> | المدة الزمنية التي يظل بها السجل نشطًا؛ لو لم يُستخدم الاتصال لفترة معينة، يُحذف السجل تلقائيًا لتحرير رقم الـ Port لاستخدامه من جديد |

**لماذا هذا السجل مهم؟** بدون هذا الجدول، لن يعرف الراوتر إلى أي جهاز داخلي يوجّه أي رد قادم من الإنترنت — فهو "الذاكرة" التي تربط كل طلب صادر بردّه الوارد، ولهذا السبب أجهزة NAT تُعتبر عمومًا **Stateful** (تحتفظ بحالة كل اتصال)، على عكس التوجيه العادي الذي لا يحتاج تذكّر أي شيء عن الحزم السابقة.

<h4 dir="rtl" align="right" id="nat-terms">د. مصطلحات NAT</h4>

| المصطلح | المعنى |
|:---:|:---:|
| <span dir="ltr">Inside Local</span> | العنوان الخاص للجهاز الداخلي كما يُرى من داخل الشبكة المحلية |
| <span dir="ltr">Inside Global</span> | العنوان العام الذي يُترجَم إليه الجهاز الداخلي عند خروجه للإنترنت |
| <span dir="ltr">Outside Local</span> | كيف يُرى الجهاز الخارجي (على الإنترنت) من داخل الشبكة المحلية |
| <span dir="ltr">Outside Global</span> | العنوان العام الحقيقي للجهاز الخارجي كما هو على الإنترنت |
| <span dir="ltr">Global Address</span> | أي عنوان يُستخدم على الإنترنت العام |
| <span dir="ltr">Local Address</span> | أي عنوان يُستخدم داخل الشبكة المحلية الخاصة |

---

<h3 dir="rtl" align="right" id="network-monitoring">17. مراقبة الشبكة عبر عنوان الـ IP</h3>

توجد برامج وبروتوكولات مخصصة لمراقبة حالة الأجهزة على الشبكة اعتمادًا على عنوان الـ <span dir="ltr">IP</span> الخاص بكل منها، أبرزها بروتوكول <span dir="ltr">SNMP (Simple Network Management Protocol)</span>، الذي يسمح لأدوات المراقبة بجمع معلومات عن أداء وحالة الأجهزة (مثل الراوترات والسويتشات والسيرفرات) عن بُعد، والتنبيه عند حدوث أعطال أو تجاوز حدود معينة في الاستخدام.

---
---

<h2 dir="rtl" align="right" id="part2-subnetting">🟩 الجزء الثاني: تقسيم الشبكات <span dir="ltr">(IP Subnetting)</span></h2>

> ⚠️ هذا الجزء هو **الأهم** في هذا الملف. كل خطوة هنا محلولة بالتفصيل مع أمثلة عملية، لأن فهم الـ Subnetting يعتمد بشكل كامل على التمرّن على الأرقام وليس الحفظ.

<h3 dir="rtl" align="right" id="why-subnetting">1. مقدمة: ليه بنقسم الشبكة؟</h3>

تخيل شبكة واحدة كبيرة <span dir="ltr">(Single Flat Network)</span> تضم كل أجهزة شركة كاملة بدون أي تقسيم. هذا التصميم يسبب مشاكل جوهرية:

- **مجال بث واحد ضخم <span dir="ltr">(Broadcast Domain)</span>:** أي رسالة بث <span dir="ltr">(Broadcast)</span> يرسلها أي جهاز تصل لكل الأجهزة الأخرى، مما يزيد الازدحام على الشبكة ويهدر عرض النطاق الترددي بلا داعٍ.
- **صعوبة الإدارة والتحكم:** لا يمكن فصل أقسام الشركة (مثل قسم المحاسبة عن قسم تقنية المعلومات) منطقيًا أو تطبيق سياسات أمان مختلفة لكل قسم (راجع فائدة عنوان الشبكة في التحكم، <a href="#network-address-benefit">البند 11 من الجزء الأول</a>).
- **هدر في عناوين الـ IP:** بدون تقسيم، أي شبكة صغيرة تحتاج فقط لعدد قليل من الأجهزة تضطر لاستخدام نطاق IP كامل مُصمَّم لآلاف الأجهزة.

**الحل هو التقسيم <span dir="ltr">(Subnetting)</span>:** تقسيم شبكة واحدة كبيرة إلى عدة شبكات فرعية أصغر <span dir="ltr">(Subnets)</span>، كل واحدة منها لها مجال بث خاص بها وحدود منفصلة، وهذا ممكن تحديدًا بفضل الطبيعة الهرمية <span dir="ltr">(Hierarchical)</span> لعنوان الـ IP التي ذكرناها في <a href="#ip-vs-mac">البند الخامس من الجزء الأول</a>.

<div align="center">
<img src="images/11-7-network-subnet-division-diagram.png" width="450">
<br><em>تقسيم شبكة واحدة إلى عدة Subnets أصغر</em>
</div>

---

<h3 dir="rtl" align="right" id="subnet-mask-basics">2. Subnet Mask: تعريفه وقواعده</h3>

**Subnet Mask** هو رقم مكوّن من 32 بت (بنفس صيغة عنوان الـ IP)، وظيفته الوحيدة هي **تحديد أي جزء من عنوان الـ IP يمثل الشبكة <span dir="ltr">(Network)</span> وأي جزء يمثل الجهاز <span dir="ltr">(Host)</span>**.

**قاعدة كتابته (لا يجوز خلطها):**
> يجب أن يكون Subnet Mask عبارة عن **سلسلة متصلة من الواحدات (1) تليها مباشرة سلسلة متصلة من الأصفار (0)**، ولا يجوز أبدًا أن يتخلل الأصفارَ رقمُ واحد، أو العكس.

- البتات التي قيمتها `1` ⬅ خاصة بـ **الشبكة (Network)**.
- البتات التي قيمتها `0` ⬅ خاصة بـ **الأجهزة (Host)**.

**طرق كتابة الـ Subnet Mask:**
1. **الصيغة العشرية الكاملة:** مثل `255.255.255.0`.
2. **صيغة CIDR (السلاش):** مثل `/24` — وسيتم شرحها بالتفصيل في <a href="#cidr">البند التالي</a>.

**فائدة الـ Subnet Mask ولماذا يحتاجه الجهاز:** بدونه، لا يستطيع أي جهاز أو راوتر تحديد هل عنوان IP معين يقع داخل نفس شبكته المحلية أم في شبكة أخرى بعيدة تحتاج توجيه عبر الـ <span dir="ltr">Default Gateway</span> (راجع <a href="#ip-assignment-methods">البند 12 من الجزء الأول</a>).

---

<h3 dir="rtl" align="right" id="anding">3. عملية ANDing</h3>

عملية <span dir="ltr">ANDing</span> هي العملية المنطقية التي يستخدمها الجهاز فعليًا لمعرفة **عنوان الشبكة** الخاص به، وذلك بتطبيق عملية <span dir="ltr">AND</span> المنطقية (بت مقابل بت) بين عنوان الـ IP والـ Subnet Mask الخاص به:

| قاعدة AND | الناتج |
|:---:|:---:|
| 1 AND 1 | 1 |
| 1 AND 0 | 0 |
| 0 AND 1 | 0 |
| 0 AND 0 | 0 |

**مثال:**
```
IP:          11000000.10101000.00000001.00000101   (192.168.1.5)
Subnet Mask: 11111111.11111111.11111111.00000000   (255.255.255.0)
------------------------------------------------  AND
Network ID:  11000000.10101000.00000001.00000000   (192.168.1.0)
```
الناتج هو عنوان الشبكة `192.168.1.0`، وهو ما يستخدمه الراوتر لمعرفة هل الوجهة داخل نفس الشبكة المحلية أم تحتاج توجيه خارجي (راجع <a href="#router-uses-ip">كيف يستخدم الراوتر الـ IP للتوجيه</a>).

---

<h3 dir="rtl" align="right" id="number-systems">4. أنظمة العد وطرق التحويل بينها</h3>

فهم الـ Subnetting يعتمد بشكل كامل على القدرة على التحويل بسهولة بين ثلاثة أنظمة عد:

| النظام | الاسم | القاعدة |
|:---:|:---:|:---:|
| <span dir="ltr">Base 10</span> | العشري (Decimal) | الأرقام من 0 إلى 9 |
| <span dir="ltr">Base 2</span> | الثنائي (Binary) | كل رقم له احتمالان فقط: 0 أو 1 |
| <span dir="ltr">Base 16</span> | الهيكساديسيمال (Hexadecimal) | الأرقام من 0-9 ثم الحروف A-F (تُستخدم أساسًا في كتابة عناوين MAC) |

<h4 dir="rtl" align="right" id="weights-table">أ. جدول الأوزان (الجدول السحري)</h4>

الأداة الأهم على الإطلاق في كل عمليات التحويل والتقسيم هي **جدول الأوزان**، وهو ببساطة قيم القوى المتتالية للرقم 2:

<div align="center">
<img src="images/11-8-powers-of-two-table.png" width="450">
<br><em>جدول قوى الرقم 2 (Powers of Two)</em>
</div>

**جدول الأوزان الخاص بالأوكتت الواحد (8 بت) — وهو ما يُستخدم عمليًا في كل مسائل الـ Subnetting:**

| الوزن | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| مكافئ | 2⁷ | 2⁶ | 2⁵ | 2⁴ | 2³ | 2² | 2¹ | 2⁰ |

<h4 dir="rtl" align="right" id="binary-decimal-conversion">ب. التحويل بين الباينري والديسيمال</h4>

**من الباينري إلى الديسيمال:** نضع تحت كل بت قيمته من جدول الأوزان، ثم نجمع فقط الأوزان المقابلة للبتات التي قيمتها `1`.

**مثال:** حوّل `11000000` إلى ديسيمال:

| 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |

الناتج = `128 + 64 = 192` ✅

**من الديسيمال إلى الباينري:** نبدأ من أكبر وزن في الجدول، ونسأل: هل هذا الوزن **أصغر من أو يساوي** الرقم المطلوب تحويله؟
- لو **نعم** ⬅ نضع `1` تحت هذا الوزن، ونطرحه من الرقم، ونكمل بالباقي على باقي الأوزان.
- لو **لا** ⬅ نضع `0` تحت هذا الوزن، ونكمل بنفس الرقم على الوزن الأصغر التالي.

**مثال:** حوّل `172` إلى باينري:

| الوزن | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| هل الوزن ≤ الباقي؟ | 128≤172 ✅ | 44<64 ❌ | 44≥32 ✅ | 12<16 ❌ | 12≥8 ✅ | 4≥4 ✅ | 0<2 ❌ | 0<1 ❌ |
| البت | 1 | 0 | 1 | 0 | 1 | 1 | 0 | 0 |
| الباقي بعد الطرح | 172-128=44 | 44 | 44-32=12 | 12 | 12-8=4 | 4-4=0 | 0 | 0 |

الناتج: `172 = 10101100` ✅

<h4 dir="rtl" align="right" id="binary-range">ج. طريقة التعبير عن مدى الاحتمالات في النظام الثنائي</h4>

كل بت إضافي يُضاعف عدد الاحتمالات الممكنة (لأن كل بت له احتمالان: 0 أو 1). القاعدة العامة: **عدد الاحتمالات = 2 (عدد البتات)**:

| عدد البتات | عدد الاحتمالات | المدى (من - إلى) |
|:---:|:---:|:---:|
| 1 بت | 2¹ = 2 | `0` إلى `1` |
| 2 بت | 2² = 4 | `00` إلى `11` |
| 4 بت | 2⁴ = 16 | `0000` إلى `1111` |
| 8 بت (أوكتت كامل) | 2⁸ = 256 | `00000000` إلى `11111111` (أي من 0 إلى 255 بالديسيمال) |

> 💡 هذا بالضبط سبب أن قيمة أي أوكتت في عنوان IP تتراوح من `0` إلى `255`: لأن الأوكتت 8 بت، وأقصى قيمة ممكنة هي `2⁸ − 1 = 255`.

<h4 dir="rtl" align="right" id="hex-binary-conversion">د. التحويل بين الهيكساديسيمال والباينري</h4>

كل خانة هيكساديسيمال واحدة (0-9, A-F) تقابل بالضبط **4 بتات باينري**:

| Hex | Binary | Hex | Binary |
|:---:|:---:|:---:|:---:|
| 0 | 0000 | 8 | 1000 |
| 1 | 0001 | 9 | 1001 |
| 2 | 0010 | A | 1010 |
| 3 | 0011 | B | 1011 |
| 4 | 0100 | C | 1100 |
| 5 | 0101 | D | 1101 |
| 6 | 0110 | E | 1110 |
| 7 | 0111 | F | 1111 |

**طريقة التحويل من Hex إلى Binary:** نستبدل كل خانة هيكس بمقابلها من 4 بتات مباشرة من الجدول، ونلصقهم مع بعض.
**طريقة التحويل من Binary إلى Hex:** نقسّم البتات إلى مجموعات كل مجموعة 4 بتات (من اليمين لليسار)، ونحول كل مجموعة لخانة هيكس من الجدول.

**مثال تطبيقي — تحويل عنوان MAC إلى باينري:**
عنوان MAC مثل `3C:5A` يتحول كالتالي:
```
3    C    5    A
0011 1100 0101 1010
```
الناتج الباينري الكامل: `00111100 01011010`

> 🔗 هذا التمرين يربط مباشرة بما تم شرحه عن نظام كتابة عنوان MAC بالهيكساديسيمال في <a href="#ip-vs-mac">البند الخامس من الجزء الأول</a> وفي [الموضوع التاسع](../9-ethernet-lan.md).

<h4 dir="rtl" align="right" id="hex-range">هـ. طريقة التعبير عن مدى الاحتمالات في نظام الهيكساديسيمال</h4>

بنفس منطق النظام الثنائي، لكن كل خانة هيكس واحدة لها **16 احتمالًا** (من 0 إلى F)، لأنها تمثل 4 بتات (2⁴ = 16):

| عدد الخانات | عدد الاحتمالات | المدى |
|:---:|:---:|:---:|
| خانة واحدة | 16 | `0` إلى `F` |
| خانتان | 256 | `00` إلى `FF` |
| 6 خانات (عنوان MAC كامل) | 2⁴⁸ (عدد ضخم) | `00:00:00:00:00:00` إلى `FF:FF:FF:FF:FF:FF` |

<h4 dir="rtl" align="right" id="bit-count-rule">و. معرفة "الرقم ده كام بت؟"</h4>

قبل التحويل، أحيانًا محتاج تعرف بسرعة عدد البتات اللازمة لتمثيل رقم معين. القانون: **أوجد أكبر وزن في جدول الأوزان يكون أصغر من (أو يساوي) الرقم المطلوب**، وترتيب هذا الوزن في الجدول يحدد لك عدد البتات المطلوبة (لأن كل الأوزان الأصغر منه يجب تضمينها كاحتمالات).

**مثال:** الرقم `100` — أكبر وزن أصغر منه أو يساويه هو `64` (وهو 2⁶)، إذن الرقم يحتاج 7 بتات كحد أقصى ليُكتب بالكامل (من 2⁶ إلى 2⁰).

---

<h3 dir="rtl" align="right" id="cidr">5. نظام CIDR وكتابة السلاش</h3>

<span dir="ltr">CIDR (Classless Inter-Domain Routing)</span> هي طريقة مختصرة لكتابة الـ Subnet Mask، بحيث بدلًا من كتابة الأربع أوكتتات كاملة، نكتب فقط **عدد البتات التي قيمتها 1** بعد علامة السلاش `/`.

| صيغة CIDR | Subnet Mask المكافئ | عدد بتات الشبكة |
|:---:|:---:|:---:|
| `/8` | `255.0.0.0` | 8 |
| `/16` | `255.255.0.0` | 16 |
| `/18` | `255.255.192.0` | 18 |
| `/20` | `255.255.240.0` | 20 |
| `/21` | `255.255.248.0` | 21 |
| `/24` | `255.255.255.0` | 24 |
| `/27` | `255.255.255.224` | 27 |

**معنى `/24` عمليًا:** أول 24 بت من العنوان (أول 3 أوكتتات) ثابتة وتمثل الشبكة، والـ 8 بت المتبقية (الأوكتت الأخير) للأجهزة.

> 💡 نظام CIDR سُمّي "Classless" لأنه حرّر التقسيم من قيود الفئات التقليدية الثابتة (A, B, C)، وسمح بتقسيم أي شبكة بأي عدد بتات نحتاجه فعليًا، بدل الالتزام بحدود الفئة الافتراضية فقط — وهذا هو أساس كل عملية الـ Subnetting نفسها.

---

<h3 dir="rtl" align="right" id="subnetting-laws">6. القوانين الأساسية للتقسيم</h3>

<div align="center">
<img src="images/11-5-hosts-formula-why-minus-2.png" width="600">
<br><em>سبب طرح 2 من معادلة عدد الأجهزة</em>
</div>

**القانون الأول: عدد الشبكات الفرعية**
$$\text{عدد الشبكات} = 2^n$$
حيث **n** = عدد البتات التي تم استلافها من جزء الأجهزة وتحويلها لجزء الشبكة (أي عدد الواحدات الإضافية في الـ Subnet Mask بعد المدى الافتراضي للفئة).

**القانون الثاني: عدد الأجهزة المتاحة في كل شبكة فرعية**
$$\text{عدد الأجهزة} = 2^h - 2$$
حيث **h** = عدد البتات المتبقية لجزء الأجهزة (أي عدد الأصفار في الـ Subnet Mask).

**ليه بنطرح 2؟**
لأن أي شبكة عليها دائمًا عنوانان محجوزان لا يُخصَّصان لأي جهاز فعلي:
- **الأول:** عنوان الشبكة نفسه <span dir="ltr">(Network ID)</span> — لا يُوزَّع لأي جهاز، هو ممثل الشبكة فقط.
- **الأخير:** عنوان البث <span dir="ltr">(Broadcast Address)</span> — مخصص لإرسال بيانات لكل أجهزة الشبكة دفعة واحدة، وليس لجهاز بعينه.

**القانون الثالث: حجم القفزة (Block Size)**
حجم القفزة هو الفرق بين بداية كل شبكة فرعية والتالية لها، ويُحسب كالتالي:
$$\text{Block Size} = 256 - \text{قيمة الأوكتت المتغير في الـ Subnet Mask}$$

**مثال:** لو الـ Subnet Mask هو `255.255.255.224`، فالأوكتت المتغير قيمته `224`، وحجم القفزة = `256 - 224 = 32`. يعني كل شبكة فرعية تبدأ بعد 32 عنوانًا من التي قبلها (0, 32, 64, 96, ...).

**جدول تلخيصي شامل** يجمع الفئة، مداها، الـ Subnet Mask الافتراضي، عدد الشبكات، وعدد الأجهزة داخل كل شبكة معًا في مكان واحد:

<div align="center">
<img src="images/11-9-subnetting-summary-table.png" width="700">
<br><em>جدول تلخيصي: الفئة، البداية والنهاية، Subnet Mask، عدد الشبكات، وعدد الأجهزة في كل شبكة</em>
</div>

---

<h3 dir="rtl" align="right" id="solving-steps">7. خطوات حل أي مسألة Subnetting</h3>

بغض النظر عن نوع المعطى (سواء عدد الأجهزة المطلوب، أو عدد الشبكات المطلوب)، الخطوات ثابتة دائمًا:

1. حدد الـ Subnet Mask الأصلي (الافتراضي للفئة أو المُعطى في السؤال) وحوّله إلى باينري.
2. حدد المطلوب (عدد الأجهزة أم عدد الشبكات؟) وطبّق القانون المناسب (`2ⁿ` أو `2ʰ − 2`) لإيجاد عدد البتات اللازم استلافها.
3. عدّل الـ Subnet Mask بتحويل العدد اللازم من الأصفار (من جهة اليسار) إلى واحدات.
4. حوّل الـ Subnet Mask الجديد من باينري إلى ديسيمال باستخدام جدول الأوزان.
5. احسب حجم القفزة (Block Size)، واستخرج منه عناوين كل الشبكات الفرعية (Subnet IDs) وحدودها.

---

<h3 dir="rtl" align="right" id="worked-examples">8. أمثلة محلولة خطوة بخطوة</h3>

<h4 dir="rtl" align="right" id="example-easy">🟢 مثال 1 (سهل) — تحديد بيانات شبكة CIDR بسيطة</h4>

**السؤال:** عندنا شبكة `192.168.5.0/26`. المطلوب: عدد بتات الشبكة، عدد بتات الأجهزة، عدد الأجهزة المتاحة، وحجم القفزة.

**الحل:**
- `/26` يعني 26 بت للشبكة، وبما أن العنوان بالكامل 32 بت، إذن بتات الأجهزة = `32 - 26 = 6` بت.
- عدد الأجهزة = `2⁶ - 2 = 64 - 2 = 62` جهاز.
- الـ Subnet Mask بالباينري: `11111111.11111111.11111111.11000000` ⬅ بالديسيمال: `255.255.255.192`.
- حجم القفزة = `256 - 192 = 64`.
- الشبكات الفرعية تبدأ من: `192.168.5.0`, `192.168.5.64`, `192.168.5.128`, `192.168.5.192` ...

<h4 dir="rtl" align="right" id="example-medium">🟡 مثال 2 (متوسط) — معطى: عدد الأجهزة المطلوب</h4>

**السؤال:** عندنا `IP: 198.61.20.0/24`، والمطلوب تقسيم الشبكة بحيث يكون في كل شبكة فرعية **30 جهاز**.

**الحل خطوة بخطوة:**

**الخطوة 1:** الـ Subnet Mask الأصلي `/24`:
```
11111111.11111111.11111111.00000000
```
الأوكتت الأخير بالكامل (8 بت) متاح حاليًا للأجهزة.

**الخطوة 2:** تطبيق قانون `2ʰ = ؟` لمعرفة عدد بتات الأجهزة اللازمة لتغطية 30 جهاز:
$$2^5 = 32$$
بما أن أول وآخر عنوان لا يُحسبان، فـ `32 - 2 = 30` جهاز ✅ (بالضبط العدد المطلوب).

**الخطوة 3:** بما أن 5 بت هتفضل للأجهزة، الباقي من الـ 8 بت الأصلية (وهو `8 - 5 = 3` بت) هيتحول للشبكات:
```
11111111.11111111.11111111.11100000
```

**الخطوة 4:** تحويل الـ Subnet Mask الجديد من باينري لديسيمال باستخدام جدول الأوزان — الأوكتت الأخير `11100000` = `128+64+32 = 224`:
$$\text{Subnet Mask} = 255.255.255.224 \;(/27)$$

**الخطوة 5:** حساب عدد الشبكات الناتجة من الـ 3 بت المستلفة:
$$2^3 = 8 \text{ شبكات}$$

**ملخص الحل:** حصلنا على **8 شبكات فرعية**، كل شبكة فيها **30 جهاز قابل للاستخدام** (من إجمالي 32 عنوان)، وحجم القفزة = `256 - 224 = 32`.

<h4 dir="rtl" align="right" id="example-advanced">🔴 مثال 3 (متقدم) — معطى: عدد الشبكات المطلوب</h4>

**السؤال:** عندنا `IP: 172.24.0.0/16` (من كلاس B)، والمطلوب تقسيمها إلى **32 شبكة فرعية**، مع حساب عدد الأجهزة في كل شبكة وتحديد الـ Subnet ID لكل شبكة.

**الحل خطوة بخطوة:**

**الخطوة 1:** الـ Subnet Mask الأصلي لـ `/16`: `255.255.0.0` ⬅ بالباينري:
```
11111111.11111111.00000000.00000000
```

**الخطوة 2:** تطبيق قانون `2ⁿ = ؟` لمعرفة عدد بتات الشبكات اللازمة لتغطية 32 شبكة:
$$2^5 = 32 \text{ شبكة}$$
إذن نحتاج استلاف 5 بت من جزء الأجهزة وتحويلها لجزء الشبكة.

**الخطوة 3:** تعديل الـ Subnet Mask بإضافة 5 بت من أول الأوكتت الثالث:
```
11111111.11111111.11111000.00000000
```

**الخطوة 4:** حساب عدد بتات الأجهزة المتبقية: كان أصل الأجهزة 16 بت (الأوكتتين الأخيرين في /16)، استلفنا منها 5 بت، فتبقى `16 - 5 = 11` بت للأجهزة:
$$2^{11} - 2 = 2048 - 2 = 2046 \text{ جهاز في كل شبكة فرعية}$$

**الخطوة 5:** تحويل الـ Subnet Mask الجديد لديسيمال — الأوكتت الثالث `11111000` = `128+64+32+16+8 = 248`:
$$\text{Subnet Mask} = 255.255.248.0 \;(/21)$$

**الخطوة 6:** حساب حجم القفزة في الأوكتت الثالث: `256 - 248 = 8`. إذن الشبكات الفرعية (Subnet IDs) تبدأ من:
`172.24.0.0` , `172.24.8.0` , `172.24.16.0` , `172.24.24.0` ... وهكذا بفارق 8 في الأوكتت الثالث، حتى نصل لـ 32 شبكة.

**ملخص الحل:** حصلنا على **32 شبكة فرعية**، كل شبكة فيها **2046 جهاز قابل للاستخدام**.

> 🔑 **استنتاج مهم من مقارنة المثالين 2 و3:**
> - في **المثال 2** كان المعطى هو عدد الأجهزة، فطبّقنا `2ʰ` وجعلنا الأس (h) يمثل **بتات الأجهزة (الأصفار)**، والباقي تلقائيًا يكون للشبكات.
> - في **المثال 3** كان المعطى هو عدد الشبكات، فطبّقنا `2ⁿ` وجعلنا الأس (n) يمثل **بتات الشبكات (الواحدات)**، والباقي تلقائيًا يكون للأجهزة.
> **القاعدة الذهبية:** حدّد أولًا هل المُعطى في السؤال عدد أجهزة أم عدد شبكات، لأن هذا يحدد أي طرف من المعادلة تبدأ منه.

---

<h3 dir="rtl" align="right" id="subnet-id-boundaries">9. حساب Subnet ID وحدود كل شبكة فرعية</h3>

بعد تحديد حجم القفزة <span dir="ltr">(Block Size)</span>، يمكن استخراج **كل** الشبكات الفرعية وحدودها بسهولة عن طريق ضرب مضاعفات حجم القفزة.

**مثال:** بالاستمرار على مثال `198.61.20.0/27` (حجم القفزة = 32):

| # | Subnet ID (Network) | أول Host | آخر Host | Broadcast |
|:---:|:---:|:---:|:---:|:---:|
| 1 | `198.61.20.0` | `198.61.20.1` | `198.61.20.30` | `198.61.20.31` |
| 2 | `198.61.20.32` | `198.61.20.33` | `198.61.20.62` | `198.61.20.63` |
| 3 | `198.61.20.64` | `198.61.20.65` | `198.61.20.94` | `198.61.20.95` |
| ... | ... | ... | ... | ... |
| 8 | `198.61.20.224` | `198.61.20.225` | `198.61.20.254` | `198.61.20.255` |

**قاعدة استخراج الجدول:**
- الـ Subnet ID التالي = الـ Subnet ID الحالي + حجم القفزة.
- أول Host = Subnet ID + 1.
- الـ Broadcast = الـ Subnet ID التالي − 1 (أو: Subnet ID الحالي + حجم القفزة − 1).
- آخر Host = الـ Broadcast − 1.

---

<h3 dir="rtl" align="right" id="vlsm">10. VLSM: التقسيم متغير الطول</h3>

<span dir="ltr">VLSM (Variable Length Subnet Masking)</span> هي طريقة تقسيم متقدمة، والفرق الجوهري بينها وبين الـ Subnetting العادي:

| Subnetting العادي | VLSM |
|:---:|:---:|
| كل الشبكات الفرعية الناتجة **بنفس الحجم بالضبط** (نفس الـ Subnet Mask) | كل شبكة فرعية يمكن أن يكون لها **Subnet Mask مختلف**، بحسب احتياجها الفعلي من الأجهزة |
| قد يسبب هدرًا كبيرًا في العناوين لو احتياجات الأقسام مختلفة | يستغل عناوين الـ IP بكفاءة أكبر، ويقلل الهدر |

**مثال تطبيقي:** قسّم شبكة من كلاس B (`172.20.0.0/16`) إلى 4 أقسام بأعداد أجهزة مختلفة:

| القسم | الأجهزة المطلوبة | Subnet Mask المناسب | الشبكة الفرعية |
|:---:|:---:|:---:|:---:|
| القسم الأول | 500 جهاز | `/23` (2⁹−2 = 510) | `172.20.0.0/23` |
| القسم الثاني | 200 جهاز | `/24` (2⁸−2 = 254) | `172.20.2.0/24` |
| القسم الثالث | 50 جهاز | `/26` (2⁶−2 = 62) | `172.20.3.0/26` |
| القسم الرابع | 10 أجهزة | `/28` (2⁴−2 = 14) | `172.20.3.64/28` |

لاحظ أن كل قسم أخذ Subnet Mask مختلف تمامًا يناسب احتياجه الفعلي بالضبط، وهذا هو جوهر مرونة الـ VLSM مقارنة بالتقسيم المتساوي.

---

<h3 dir="rtl" align="right" id="supernetting">11. Supernetting</h3>

<span dir="ltr">Supernetting</span> هي العملية **العكسية** للـ Subnetting: بدلًا من تقسيم شبكة كبيرة إلى شبكات أصغر، يتم **دمج عدة شبكات صغيرة متجاورة** في شبكة واحدة أكبر، عن طريق تقليل عدد بتات الشبكة (نقل بتات من الشبكة إلى الأجهزة).

**مثال:** دمج الشبكتين `192.168.0.0/24` و`192.168.1.0/24` في شبكة واحدة `192.168.0.0/23`.

**كيف تعمل:** يتم اختصار عدد بتات الشبكة المشتركة بين النطاقات المتجاورة، بحيث يمثل عنوان واحد بـ Subnet Mask أوسع كل النطاقات المدموجة.

**عيوبها:**
- تتطلب أن تكون الشبكات المُدمجة **متجاورة رقميًا ومتوافقة حسابيًا** (على حدود صحيحة من مضاعفات القوى)، وإلا لا يمكن دمجها بشكل صحيح.
- تُستخدم أساسًا لتلخيص جداول التوجيه <span dir="ltr">(Route Summarization)</span> وتقليل حجمها، وليست شائعة الاستخدام داخل الشبكات المحلية الصغيرة.

---

<h3 dir="rtl" align="right" id="identify-class">12. معرفة الفئة من الـ IP والـ Subnet Mask</h3>

**مين اللي بيحدد للجهاز إن الـ Subnet Mask ده من كلاس معين؟**
الجهاز نفسه لا "يقرر" الفئة — بل يحدد الفئة تلقائيًا بالنظر إلى **قيمة أول أوكتت من عنوان الـ IP** ومطابقتها بجدول الفئات القياسي (المذكور في <a href="#ip-classes">البند السابع من الجزء الأول</a>). فمثلًا أي IP يبدأ بقيمة بين 192 و223 في الأوكتت الأول، يتعرف عليه الجهاز تلقائيًا كـ Class C ويطبّق عليه الـ Subnet Mask الافتراضي `255.255.255.0` ما لم يُخبَر بغير ذلك صراحة (عبر CIDR مخصص).

**المقارنة بين IP والـ Subnet Mask لتحديد الفئة:**
1. حدد أول أوكتت من عنوان الـ IP.
2. طابقه مع مدى الفئات (Class A: 1-126، B: 128-191، C: 192-223).
3. قارن الـ Subnet Mask المُعطى بالـ Subnet Mask الافتراضي للفئة؛ لو تطابقا فالشبكة **بحجمها الافتراضي (Classful)**، ولو كان الـ Subnet Mask "أطول" من الافتراضي (بتات واحدات إضافية)، فهذا يعني أن الشبكة **مُقسَّمة (Classless / Subnetted)**.

---

<h3 dir="rtl" align="right" id="octet-split">13. تقسيم أوكتت واحد بين الشبكات والأجهزة</h3>

من المهم إدراك أن التقسيم لا يحدث دائمًا على حدود أوكتت كاملة — يمكن لأوكتت واحد أن يُقسَّم **جزئيًا** بين الشبكة والأجهزة في نفس الوقت، وهذا بالضبط ما حدث في <a href="#worked-examples">مثال 2 و3</a> أعلاه، حيث تم استلاف عدد بتات (3 أو 5) من داخل أوكتت واحد فقط دون أخذ الأوكتت بالكامل.

**مثال توضيحي إضافي:** لو عندنا `/20` على شبكة كلاس B (`172.16.0.0`):
```
Subnet Mask: 11111111.11111111.11110000.00000000
             = 255.255.240.0
```
هنا الأوكتت الثالث (`11110000`) مقسوم فعليًا لنصفين: أول 4 بت منه (`1111`) خاصة بالشبكة، وآخر 4 بت (`0000`) خاصة بالأجهزة — وهذا مثال مباشر على تقسيم أوكتت واحد بين الاثنين معًا.

---

<h3 dir="rtl" align="right" id="find-network-of-host">14. إيجاد عنوان شبكة جهاز معين</h3>

لمعرفة عنوان الشبكة <span dir="ltr">(Network ID)</span> التي ينتمي إليها أي جهاز، بمعرفة عنوان الـ IP والـ Subnet Mask الخاصين به:

1. حوّل عنوان الـ IP والـ Subnet Mask إلى باينري.
2. طبّق عملية <span dir="ltr">ANDing</span> (المشروحة في <a href="#anding">البند الثالث</a>) بين الاثنين، بت بت.
3. الناتج هو عنوان الشبكة (Network ID) الذي ينتمي إليه هذا الجهاز.

**مثال سريع:** جهاز عنوانه `10.20.35.60` بـ Subnet Mask `255.255.255.0` ⬅ عنوان شبكته هو `10.20.35.0` (لأن الأوكتت الأخير بالكامل خاص بالأجهزة، فيُصفَّر تلقائيًا عند تطبيق AND).

---
---

<h2 dir="rtl" align="right" id="review-questions">❓ أسئلة المراجعة الشاملة</h2>

**1) ما الفرق الجوهري بين عنوان الـ IP وعنوان الـ MAC من حيث نوع العنونة (Flat أم Hierarchical)؟**
> عنوان الـ MAC هو <span dir="ltr">Flat Address</span> (لا يحمل أي تدرج أو معنى هرمي)، بينما عنوان الـ IP هو <span dir="ltr">Hierarchical Address</span> يحمل جزءًا للشبكة وجزءًا للجهاز، وهذا التدرج هو ما يجعل التوجيه بين الشبكات ممكنًا، وهو أيضًا أساس إمكانية تطبيق الـ Subnetting عليه.

**2) لماذا نطرح 2 من معادلة عدد الأجهزة `2ʰ`؟**
> لأن أول عنوان في أي شبكة محجوز دائمًا لعنوان الشبكة نفسه (Network ID)، وآخر عنوان محجوز دائمًا لعنوان البث (Broadcast Address)، وكلاهما لا يُخصَّص لأي جهاز فعلي.

**3) عندك شبكة `/28`، كام عدد الأجهزة المتاحة فيها؟**
> بتات الأجهزة = `32 - 28 = 4` بت ⬅ `2⁴ - 2 = 16 - 2 = 14` جهاز.

**4) ما الفرق بين Subnetting العادي و VLSM؟**
> الـ Subnetting العادي ينتج شبكات فرعية متساوية الحجم تمامًا، بينما الـ VLSM يسمح بأحجام مختلفة لكل شبكة فرعية حسب احتياجها الفعلي، مما يقلل هدر العناوين.

**5) ما هو حجم القفزة (Block Size) لشبكة بـ Subnet Mask يساوي `255.255.255.240`؟**
> `256 - 240 = 16`، فكل شبكة فرعية تبدأ بفارق 16 عن التي قبلها.

**6) لماذا لا يمتلك Class D و Class E عنوان Subnet Mask؟**
> لأنهما غير مخصصين لعناوين أجهزة عادية على الإطلاق: D للبث المتعدد (Multicast) و E للأغراض البحثية، فلا معنى لتقسيمهما إلى Network/Host.

**7) ما وظيفة عملية الـ ANDing عمليًا؟**
> تُستخدم لمعرفة عنوان الشبكة (Network ID) الذي ينتمي إليه أي جهاز، بتطبيق عملية AND المنطقية بين عنوان الـ IP والـ Subnet Mask الخاصين به بت بت.

**8) عندك متطلب 500 جهاز في شبكة واحدة، ما هو أقرب صيغة CIDR تفي بهذا الاحتياج؟**
> نحتاج `2ʰ - 2 ≥ 500` ⬅ `2⁹ - 2 = 510` تفي بالغرض (أصغر منها `2⁸-2=254` غير كافية) ⬅ بتات الأجهزة = 9 ⬅ CIDR = `/23` (لأن `32 - 9 = 23`).

**9) ما الفرق بين Supernetting و Subnetting؟**
> الـ Subnetting يقسّم شبكة كبيرة إلى شبكات أصغر (زيادة بتات الشبكة)، بينما الـ Supernetting يدمج عدة شبكات صغيرة متجاورة في شبكة واحدة أكبر (تقليل بتات الشبكة).

**10) كيف تعرف عنوان البث (Broadcast Address) لأي شبكة فرعية بسرعة؟**
> هو آخر عنوان قبل بداية الشبكة الفرعية التالية مباشرة، ويُحسب بجمع حجم القفزة (Block Size) على عنوان الشبكة الحالي، ثم طرح 1 من الناتج.

**11) ما الفرق بين Default Route و Static Route؟**
> الـ Static Route مسار محدد يدويًا لشبكة وجهة معينة بعينها، بينما الـ Default Route مسار عام شامل (`0.0.0.0/0`) يُستخدم كحل احتياطي لأي وجهة لا تطابق مسارًا آخر في جدول التوجيه.

**12) ما الفرق بين Multicast Address و Broadcast Address؟**
> الـ Broadcast يرسل البيانات لكل الأجهزة على الشبكة بلا استثناء، بينما الـ Multicast يرسل فقط لمجموعة محددة من الأجهزة المشتركة في هذا البث (من نطاق Class D)، دون إزعاج باقي أجهزة الشبكة.

</div>
