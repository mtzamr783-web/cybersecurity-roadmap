<div dir="rtl">

# الموضوع الثالث والعشرون (الأخير): إدارة ومراقبة وتحسين أداء الشبكة (Management, Monitoring, and Optimization)

## جدول المحتويات

| # | القسم الرئيسي | المواضيع الفرعية |
|:---:|:---:|:---:|
| 1 | [مقدمة والتعريف بالموضوع](#introduction) | [المسؤول عن المراقبة](#who-monitors)<br>[ماذا يتم من خلال المراقبة](#what-monitoring-does)<br>[تحديد الأداء عبر المراقبة](#determining-performance) |
| 2 | [بروتوكول SNMP](#snmp) | [التعريف والأهمية](#snmp-definition)<br>[الوظائف](#snmp-functions)<br>[المكونات](#snmp-components)<br>[الإصدارات](#snmp-versions)<br>[الأوامر والمنافذ](#snmp-commands) |
| 3 | [بروتوكول Syslog](#syslog) | [التعريف وآلية العمل](#syslog-definition)<br>[سيرفر Syslog ومكوناته](#syslog-server)<br>[مستويات الرسائل](#syslog-levels)<br>[تحديد مستوى الاستقبال](#syslog-level-selection) |
| 4 | [بروتوكول NetFlow](#netflow) | [التعريف وآلية العمل](#netflow-definition)<br>[المكونات وطريقة العمل](#netflow-mechanism)<br>[الاعتمادية في التحليل](#netflow-dependency)<br>[سيرفر NetFlow](#netflow-server)<br>[الإصدارات](#netflow-versions)<br>[مفهوم Flow](#netflow-flow) |
| 5 | [برنامج Wireshark](#wireshark) | [التعريف](#wireshark-definition)<br>[آلية العمل والوظيفة](#wireshark-mechanism)<br>[المكونات](#wireshark-components) |
| 6 | [برنامج NMAP](#nmap-tool) | - |
| 7 | [نظام كشف التسلل IDS](#ids-topic23) | - |
| 8 | [نظام كشف ومنع التسلل IPS](#ips-topic23) | - |
| 9 | [توثيق الشبكة (Network Documentation)](#network-documentation) | [المخططات وأنواعها](#diagrams)<br>[إدارة الأصول](#asset-management)<br>[توثيق المورّدين](#vendor-documentation)<br>[خطوط الأساس](#baselines-topic23) |
| 10 | [جودة الخدمة (QoS)](#qos) | - |
| 11 | [أنواع QoS](#qos-types) | - |
| 12 | [حل مشكلة الازدحام بواسطة QoS](#qos-congestion-solution) | - |
| 13 | [أنواع التأخير في الشبكة](#delay-types) | [Processing Delay](#processing-delay)<br>[Queuing Delay](#queuing-delay)<br>[Serialization Delay](#serialization-delay)<br>[Propagation Delay](#propagation-delay) |
| 14 | [أضرار الازدحام في الشبكة](#congestion-damages) | [Lack of Bandwidth](#lack-bandwidth)<br>[Packet Loss](#packet-loss)<br>[Delay](#delay-damage)<br>[Jitter](#jitter-damage) |
| 15 | [التصنيف والتعليم (Classification and Marking)](#classification-marking) | - |
| 16 | [صفوف البيانات (Queues) وأنواعها](#queues) | - |
| 17 | [نظام CoS](#cos) | - |
| 18 | [درجات البيانات في QoS (DSCP)](#dscp) | - |
| 19 | [توزيع الحمل (Load Balancing / NLB / Cluster)](#load-balancing) | - |
| 20 | [السياسات والإجراءات واللوائح](#policies-procedures) | [السياسات](#policies-list)<br>[الإجراءات](#procedures-list)<br>[المستندات القياسية](#business-documents)<br>[اللوائح التنظيمية](#regulations) |
| 21 | [إجراءات السلامة](#safety-practices) | [السلامة الكهربائية](#electrical-safety)<br>[سلامة التركيب](#installation-safety)<br>[إجراءات الطوارئ](#emergency-procedures)<br>[HVAC](#hvac) |
| 22 | [تجزئة الشبكة](#network-segmentation) | [Medianets](#medianets)<br>[VTC](#vtc)<br>[الأنظمة القديمة](#legacy-systems)<br>[فصل الشبكات الخاصة/العامة](#public-private-separation)<br>[Honeypot/Honeynet](#honeypot-topic23)<br>[بيئة الاختبار](#testing-lab)<br>[الامتثال](#compliance) |
| 23 | [إضافات تحسين الأداء](#optimization-additions) | [الاتصالات الموحدة](#unified-communications)<br>[Traffic Shaping](#traffic-shaping)<br>[محركات التخزين المؤقت](#caching-engines)<br>[High Availability](#ha-topic23)<br>[Fault Tolerance](#ft-topic23)<br>[النسخ الاحتياطي](#backups-topic23)<br>[CARP](#carp) |
| 24 | [الشبكات الافتراضية (Virtual Networking)](#virtual-networking) | [Hypervisor](#hypervisor)<br>[vSwitch](#vswitch)<br>[vNIC](#vnic)<br>[vRouter](#vrouter)<br>[vFirewall](#vfirewall)<br>[SDN](#sdn)<br>[Jumbo Frame](#jumbo-frame) |
| 25 | [شبكات التخزين](#storage-networks) | [SAN](#san)<br>[NAS](#nas)<br>[iSCSI](#iscsi)<br>[Fibre Channel / FCoE](#fibre-channel)<br>[InfiniBand](#infiniband) |
| 26 | [الحوسبة السحابية](#cloud-computing) | [نماذج الخدمة](#cloud-service-models)<br>[نماذج النشر](#cloud-deployment-models)<br>[طرق الاتصال](#cloud-connectivity)<br>[الاعتبارات الأمنية](#cloud-security)<br>[العلاقة بين المحلي والسحابي](#cloud-vs-local) |
| 27 | [تركيب المعدات وموقعها](#equipment-location) | [MDF/IDF](#mdf-idf)<br>[إدارة الكابلات](#cable-management)<br>[إدارة الطاقة](#power-management-topic23)<br>[وضع الأجهزة](#device-placement)<br>[التسميات](#labeling)<br>[مراقبة وأمان الـ Rack](#rack-monitoring-security) |
| 28 | [إدارة التغيير (Change Management)](#change-management) | - |
| 29 | [جدول المراجعة السريع](#cheat-sheet-23) | - |

---

<h2 dir="rtl" align="right" id="introduction">1. مقدمة والتعريف بالموضوع</h2>

<p dir="rtl" align="right">
ده آخر موضوع في السلسلة كاملة، وهو عملياً موضوع "ختامي" بيجمع خيوط كتير من كل المواضيع اللي فاتت. لو بنيت شبكة صح (المواضيع من 1 لـ 20)، وعرفت تأمّنها (18، 19)، وتشخّص مشاكلها (21، 22) — السؤال الأخير هو: <strong>إزاي تدير الشبكة دي بشكل احترافي ومستمر، وتراقب أداءها، وتحسّنه باستمرار؟</strong> ده بالظبط اللي الموضوع ده بيجاوب عليه.
</p>

<h3 dir="rtl" align="right" id="who-monitors">1.1 من المسؤول عن مراقبة الشبكة؟</h3>

<p dir="rtl" align="right">
المسؤولية دي مش شخص واحد بالضرورة — بتتوزع حسب حجم المؤسسة: في الشركات الصغيرة، غالباً مهندس الشبكات نفسه أو مسؤول تقنية المعلومات (IT Admin) بيتولى المراقبة بجانب مهامه التانية. في المؤسسات الكبيرة، بيكون فيه فريق متخصص بالكامل (Network Operations Center - NOC) شغله الوحيد مراقبة الشبكة على مدار الساعة، وأحياناً بيتكامل مع فريق الأمن (SOC - Security Operations Center) لو المراقبة ليها بعد أمني.
</p>

<h3 dir="rtl" align="right" id="what-monitoring-does">1.2 ما الذي يتم من خلال مراقبة الشبكة؟</h3>

<p dir="rtl" align="right">
مراقبة الشبكة مش مجرد "مشاهدة" — هي عملية جمع مستمر للبيانات عن حالة كل مكونات الشبكة (أجهزة، روابط، خدمات)، وتحليلها، واكتشاف أي شذوذ أو تدهور في الأداء <strong>قبل ما يتحول لمشكلة حقيقية تأثر على المستخدمين</strong>. ده بيشمل تتبع استخدام النطاق الترددي، حالة الأجهزة (شغالة/معطّلة)، معدلات الأخطاء، وسجلات الأحداث (Logs) من كل الأجهزة.
</p>

<h3 dir="rtl" align="right" id="determining-performance">1.3 تحديد أداء الشبكة من خلال المراقبة</h3>

<p dir="rtl" align="right">
أداء الشبكة بيتحدد بمقارنة الحالة الحالية بخط الأساس (Baseline — تذكير سريع من المواضيع السابقة، وموضّح بالتفصيل في القسم 9.4) — القياس المرجعي للأداء الطبيعي. من غير مراقبة مستمرة، مفيش طريقة موضوعية تعرف بيها هل الشبكة "بطيئة دلوقتي" فعلاً أو ده أداءها الطبيعي. الأدوات الأساسية اللي بتوفر البيانات دي هي البروتوكولات الموضّحة في الأقسام الجاية (SNMP, Syslog, NetFlow) بالإضافة لأدوات التحليل المباشر (Wireshark, NMAP) وأنظمة الحماية (IDS/IPS).
</p>

---

<h2 dir="rtl" align="right" id="snmp">2. بروتوكول SNMP (Simple Network Management Protocol)</h2>

<h3 dir="rtl" align="right" id="snmp-definition">2.1 التعريف بالبروتوكول وأهميته وكيف يعمل</h3>

<p dir="rtl" align="right">
SNMP هو البروتوكول القياسي لإدارة ومراقبة أجهزة الشبكة عن بعد (راوترات، سويتشات، سيرفرات، طابعات — أي جهاز "متوافق مع SNMP"). أهميته إنه بيوفر <strong>طريقة موحّدة</strong> لجمع معلومات عن حالة مئات أو آلاف الأجهزة من نقطة مركزية واحدة، بدل ما تدخل على كل جهاز بمفرده.
</p>

<p dir="rtl" align="right">
<strong>آلية العمل:</strong> محطة إدارة مركزية (Management Station / NMS - Network Management System) بتقوم بعملية <strong>استقصاء (Polling)</strong> للأجهزة على فترات زمنية ثابتة أو عشوائية، بتطلب منها تكشف عن معلومات معينة. البروتوكول بيستخدم UDP لنقل الرسائل (Datagrams) بين محطة الإدارة والـ Agent الشغال على كل جهاز مُدار.
</p>

<h3 dir="rtl" align="right" id="snmp-functions">2.2 وظائف البروتوكول</h3>

<ul dir="rtl">
<li><strong>جمع المعلومات:</strong> الحصول على حالة الجهاز الحالية (استخدام المعالج، الذاكرة، حالة الواجهات).</li>
<li><strong>تعديل الإعدادات عن بعد:</strong> إرسال أوامر لتغيير إعداد معين على الجهاز مباشرة.</li>
<li><strong>التنبيه الفوري (Trapping):</strong> إعلام محطة الإدارة فوراً بحدث مهم من غير ما تستني دورة الاستقصاء التالية.</li>
</ul>

<h3 dir="rtl" align="right" id="snmp-components">2.3 مكونات بروتوكول SNMP</h3>

<ul dir="rtl">
<li><strong>Manager (محطة الإدارة / NMS):</strong> النظام المركزي اللي بيجمع ويحلل البيانات من كل الأجهزة.</li>
<li><strong>Agent (الوكيل):</strong> برنامج صغير شغال على كل جهاز مُدار، مسؤول عن جمع بيانات الجهاز محلياً والرد على استفسارات الـ Manager.</li>
<li><strong>MIB (Management Information Base):</strong> قاعدة بيانات هرمية بتحدد كل قطعة معلومة يقدر الـ Agent يبلّغ عنها (زي رقم تعريفي لكل متغير — Object Identifier / OID).</li>
</ul>

<h3 dir="rtl" align="right" id="snmp-versions">2.4 إصدارات بروتوكول SNMP</h3>

<table>
<tr><th align="center">الإصدار</th><th align="center">أهم خصائصه</th></tr>
<tr><td align="center"><strong>SNMPv1</strong></td><td align="center">الإصدار الأصلي — مصادقة ضعيفة جداً عبر "Community String" (زي كلمة مرور نص واضح غير مشفّر)</td></tr>
<tr><td align="center"><strong>SNMPv2 (SNMPv2c)</strong></td><td align="center">تحسينات في الأداء ونقل حجم بيانات أكبر، لكن لسه بيستخدم Community String غير مشفّر لنفس مشكلة v1 الأمنية</td></tr>
<tr><td align="center"><strong>SNMPv3</strong></td><td align="center">الإصدار الآمن — بيضيف <strong>مصادقة حقيقية وتشفير كامل</strong> للرسائل، وهو الموصى به حصرياً في البيئات الحديثة</td></tr>
</table>

<h3 dir="rtl" align="right" id="snmp-commands">2.5 أوامر بروتوكول SNMP والمنافذ</h3>

<table>
<tr><th align="center">الأمر</th><th align="center">الوظيفة</th><th align="center">المنفذ (Port)</th></tr>
<tr><td align="center"><code>GetRequest</code></td><td align="center">طلب من الـ Manager للـ Agent للحصول على قيمة معينة (بيانات عن حالة الجهاز)</td><td align="center">UDP 161</td></tr>
<tr><td align="center"><code>SetRequest</code></td><td align="center">طلب من الـ Manager لتعديل إعداد معين على الجهاز</td><td align="center">UDP 161</td></tr>
<tr><td align="center"><code>GetResponse</code></td><td align="center">رد الـ Agent على طلب GetRequest بالقيمة المطلوبة</td><td align="center">UDP 161</td></tr>
<tr><td align="center"><code>Trap</code></td><td align="center">تنبيه غير مطلوب (Unsolicited) بيرسله الـ Agent تلقائياً لحدث مهم محدد مسبقاً من الإدارة</td><td align="center">UDP 162</td></tr>
</table>

---

<h2 dir="rtl" align="right" id="syslog">3. بروتوكول Syslog</h2>

<h3 dir="rtl" align="right" id="syslog-definition">3.1 ما هو وكيف يعمل</h3>

<p dir="rtl" align="right">
Syslog هو بروتوكول ومعيار قياسي لإرسال وتجميع <strong>رسائل السجلات (Log Messages)</strong> من أجهزة الشبكة والسيرفرات المختلفة إلى مكان مركزي واحد. بدل ما تدخل على كل جهاز بمفرده تقرا سجلاته، كل الأجهزة بترسل رسائلها لسيرفر Syslog مركزي، وده بيسهّل جداً عملية المراجعة والتدقيق (Auditing) والربط بين أحداث حصلت في أجهزة مختلفة في نفس الوقت.
</p>

<h3 dir="rtl" align="right" id="syslog-server">3.2 سيرفر Syslog ومكوناته</h3>

<p dir="rtl" align="right">
سيرفر Syslog هو النقطة المركزية اللي بتستقبل وتخزّن وتصنّف كل الرسائل الواردة من الأجهزة المختلفة. بيتكوّن نظام Syslog من:
</p>

<ul dir="rtl">
<li><strong>المُرسِل (Originator):</strong> الجهاز اللي بيولّد الرسالة (راوتر، سويتش، سيرفر، فايروول).</li>
<li><strong>المُوجِّه/المُرحِّل (Relay):</strong> جهاز وسيط اختياري بيمرر الرسائل من عدة مصادر للسيرفر المركزي.</li>
<li><strong>المُجمِّع (Collector / Syslog Server):</strong> السيرفر النهائي اللي بيستقبل ويخزّن كل الرسائل لتحليلها لاحقاً.</li>
</ul>

<p dir="rtl" align="right">
كل رسالة Syslog بتتصنّف بناءً على مكوّنين أساسيين: <strong>Facility</strong> (المصدر أو نوع العملية اللي ولّدت الرسالة — زي kernel, mail, auth) و <strong>Severity</strong> (مستوى الخطورة، موضّح بالتفصيل تحت).
</p>

<h3 dir="rtl" align="right" id="syslog-levels">3.3 مستويات Syslog (أنواع الرسائل)</h3>

<p dir="rtl" align="right">
كل رسالة Syslog ليها مستوى خطورة (Severity Level) من 0 لـ 7 — كل ما الرقم أقل، كل ما الخطورة أعلى:
</p>

<table>
<tr><th align="center">الرقم</th><th align="center">الاسم</th><th align="center">الوصف</th></tr>
<tr><td align="center">0</td><td align="center">Emergency</td><td align="center">النظام غير قابل للاستخدام تماماً — أعلى درجة خطورة</td></tr>
<tr><td align="center">1</td><td align="center">Alert</td><td align="center">يجب اتخاذ إجراء فوري</td></tr>
<tr><td align="center">2</td><td align="center">Critical</td><td align="center">حالة حرجة</td></tr>
<tr><td align="center">3</td><td align="center">Error</td><td align="center">حالة خطأ فعلية</td></tr>
<tr><td align="center">4</td><td align="center">Warning</td><td align="center">تحذير من حالة محتملة الخطورة</td></tr>
<tr><td align="center">5</td><td align="center">Notice</td><td align="center">حدث طبيعي لكنه مهم بما يكفي للتسجيل</td></tr>
<tr><td align="center">6</td><td align="center">Informational</td><td align="center">رسائل معلوماتية عادية</td></tr>
<tr><td align="center">7</td><td align="center">Debug</td><td align="center">أدق التفاصيل، تُستخدم غالباً لتشخيص برمجي — أقل درجة خطورة</td></tr>
</table>

<h3 dir="rtl" align="right" id="syslog-level-selection">3.4 تحديد مستوى رسائل Syslog المطلوب استلامه</h3>

<p dir="rtl" align="right">
عند إعداد Syslog على جهاز، بتحدد <strong>الحد الأدنى</strong> لمستوى الخطورة اللي عايز تستقبله — ولازم تفهم إن اختيار مستوى معين بيعني استلام <strong>كل الرسائل من المستوى ده وأعلى منه خطورة</strong> (يعني أرقام أقل أو مساوية). مثلاً لو حددت "Warning" (مستوى 4)، هتستقبل كل رسائل Warning وError وCritical وAlert وEmergency، لكن مش هتستقبل Notice أو Informational أو Debug. الاختيار الصح بيوازن بين تفويت معلومة مهمة (لو المستوى عالي جداً) وإغراق السيرفر برسائل زيادة عن اللزوم (لو المستوى منخفض جداً زي Debug في بيئة إنتاج).
</p>

---

<h2 dir="rtl" align="right" id="netflow">4. بروتوكول NetFlow</h2>

<h3 dir="rtl" align="right" id="netflow-definition">4.1 ما هو وكيف يعمل</h3>

<p dir="rtl" align="right">
NetFlow هو بروتوكول (طوّرته شركة سيسكو في الأصل، وبقى معيار صناعي بمعادلات مشابهة من شركات تانية زي sFlow وJFlow) مخصص لجمع وتحليل <strong>إحصائيات حركة البيانات (Traffic Statistics)</strong> المارة عبر جهاز شبكة (غالباً راوتر أو سويتش من المستوى الثالث). على عكس Syslog (اللي بيسجّل أحداث) أو SNMP (اللي بيجمع حالة الجهاز)، NetFlow متخصص تحديداً في الإجابة على سؤال: <strong>"مين بيتواصل مع مين، وبإيه بروتوكول، وبكام؟"</strong>
</p>

<h3 dir="rtl" align="right" id="netflow-mechanism">4.2 المكونات وطريقة العمل</h3>

<p dir="rtl" align="right">
بيتكوّن نظام NetFlow من ثلاثة عناصر أساسية:
</p>

<ul dir="rtl">
<li><strong>Exporter (المُصدِّر):</strong> جهاز الشبكة نفسه (الراوتر/السويتش) اللي بيراقب الحركة المارة عبره ويولّد سجلات الـ Flow.</li>
<li><strong>Collector (المُجمِّع):</strong> سيرفر بيستقبل ويخزّن سجلات الـ Flow المُرسَلة من كل أجهزة الـ Exporter في الشبكة.</li>
<li><strong>Analyzer (المُحلِّل):</strong> أداة أو برنامج بيحلل البيانات المُجمَّعة ويطلع تقارير وإحصائيات مفهومة للإداري (استخدام النطاق الترددي حسب التطبيق، أكتر المستخدمين استهلاكاً، إلخ).</li>
</ul>

<h3 dir="rtl" align="right" id="netflow-dependency">4.3 على ماذا يعتمد في تحليل حركة البيانات</h3>

<p dir="rtl" align="right">
NetFlow بيعتمد في التصنيف على مجموعة خصائص بتُعرف بـ <strong>"المفتاح ذو السبع عناصر" (7-Tuple)</strong> — عنوان IP المصدر، عنوان IP الوجهة، منفذ المصدر، منفذ الوجهة، نوع البروتوكول (TCP/UDP)، نوع الخدمة (ToS)، وواجهة الإدخال. أي حزم بتشترك في نفس القيم السبعة دي بتُعتبر جزء من نفس الـ Flow الواحد.
</p>

<h3 dir="rtl" align="right" id="netflow-server">4.4 سيرفر NetFlow</h3>

<p dir="rtl" align="right">
سيرفر NetFlow (الـ Collector) هو نظام مركزي بيستقبل سجلات الـ Flow من كل أجهزة الشبكة، وبيخزّنها لفترة معينة عشان تتحلل لاحقاً — سواء لتحليل الأداء، أو التخطيط للسعة المستقبلية (Capacity Planning)، أو حتى التحقيقات الأمنية بعد وقوع حادثة (Forensics).
</p>

<h3 dir="rtl" align="right" id="netflow-versions">4.5 إصدارات بروتوكول NetFlow</h3>

<p dir="rtl" align="right">
الإصدارات الأشهر هي <strong>NetFlow v5</strong> (الأكثر انتشاراً تاريخياً، لكنه محدود لدعم IPv4 بس) و <strong>NetFlow v9</strong> (مرن أكتر، بيدعم IPv6 والقوالب القابلة للتخصيص Templates). وفيه معيار صناعي مفتوح مبني على NetFlow v9 اسمه <strong>IPFIX (IP Flow Information Export)</strong> بقى معتمد رسمياً من IETF.
</p>

<h3 dir="rtl" align="right" id="netflow-flow">4.6 مفهوم الـ Flow</h3>

<p dir="rtl" align="right">
الـ <strong>Flow</strong> هو تسلسل من الحزم بتشترك في نفس القيم السبعة الموضّحة فوق (نفس عنواني المصدر والوجهة، نفس المنافذ، نفس البروتوكول...) وبتُعتبر جزء من نفس "محادثة" واحدة منطقياً — زي كل الحزم المكوّنة لجلسة تصفّح واحدة لموقع معين. بدل ما NetFlow يسجّل كل حزمة بمفردها (وده هيكون ضخم جداً)، بيلخّص كل الـ Flow في سجل واحد (كام بايت اتبعتوا، كام حزمة، من إمتى لإمتى)، وده بيخلي التحليل عملي وفعّال حتى على شبكات ضخمة جداً.
</p>

---

<h2 dir="rtl" align="right" id="wireshark">5. برنامج وبروتوكول Wireshark</h2>

<h3 dir="rtl" align="right" id="wireshark-definition">5.1 التعريف</h3>

<p dir="rtl" align="right">
Wireshark هو أشهر برنامج مجاني ومفتوح المصدر لالتقاط وتحليل حزم البيانات (Packet Analyzer / Protocol Analyzer) بواجهة رسومية — النسخة الرسومية المكافئة لأداة <code>tcpdump</code> السطرية (الموضّحة بالتفصيل في الموضوع 20).
</p>

<h3 dir="rtl" align="right" id="wireshark-mechanism">5.2 آلية العمل والوظيفة</h3>

<p dir="rtl" align="right">
البرنامج بيشغّل كارت الشبكة في وضع <strong>Promiscuous Mode</strong> (بيلتقط كل الحزم المارة على الوسط الناقل، مش بس اللي موجّهة له تحديداً)، وبيعرضها في الوقت الفعلي مع تحليل تلقائي لكل طبقة من طبقات البروتوكول (من Ethernet Frame وصولاً لبيانات التطبيق نفسه). بيدّي شفافية كاملة لمحتوى الحركة، وده اللي بيخليه أداة أساسية جداً في التشخيص العميق والتحليل الأمني — وأداة اختراق قوية في نفس الوقت لو استُخدم على شبكة غير مشفّرة (Packet Sniffing، الموضّح في الموضوع 18).
</p>

<h3 dir="rtl" align="right" id="wireshark-components">5.3 المكونات</h3>

<ul dir="rtl">
<li><strong>Capture Filters (فلاتر الالتقاط):</strong> بتحدد مسبقاً أي حركة بس تتلقط (زي التقاط حركة جهاز معين بس)، وده بيقلل حجم البيانات الملتقطة من الأساس.</li>
<li><strong>Display Filters (فلاتر العرض):</strong> بتفلتر الحزم اللي اتلقطت بالفعل عشان تعرض بس اللي محتاجه (زي <code>http</code> أو <code>ip.addr == 192.168.1.1</code>).</li>
<li><strong>Packet List / Packet Details / Packet Bytes:</strong> ثلاث أجزاء أساسية في الواجهة — قائمة الحزم، تفاصيل الحزمة المختارة طبقة بطبقة، والبيانات الخام بالـ Hex.</li>
</ul>

---

<h2 dir="rtl" align="right" id="nmap-tool">6. برنامج NMAP</h2>

<p dir="rtl" align="right">
تذكير سريع (اتشرح بالتفصيل الكامل في الموضوع 21) — <code>nmap</code> (Network Mapper) هو الأداة المرجعية القياسية لفحص المنافذ (Port Scanning) واكتشاف الخدمات الشغالة على الأجهزة، وبتُستخدم في سياق الموضوع ده كأداة مراقبة استباقية: مراجعة دورية لأي منافذ مفتوحة بدون داعٍ على الشبكة، كجزء من عمليات الفحص الدوري (Scanning) الموضّحة في المواضيع السابقة.
</p>

---

<h2 dir="rtl" align="right" id="ids-topic23">7. نظام كشف التسلل (IDS)</h2>

<p dir="rtl" align="right">
تذكير سريع (اتشرح بالتفصيل في الموضوعين 18 و19) — نظام مراقبة سلبي (Passive) بيكتشف الأنشطة المشبوهة عبر مقارنة الحركة بتوقيعات هجمات معروفة أو سلوك غير طبيعي، ويصدر تنبيه (Alert) فقط دون تدخل مباشر. في سياق المراقبة المستمرة، الـ IDS بيُعتبر مصدر بيانات إضافي مهم بيتكامل مع سيرفرات Syslog وSNMP لإعطاء صورة أمنية شاملة عن حالة الشبكة.
</p>

---

<h2 dir="rtl" align="right" id="ips-topic23">8. نظام كشف ومنع التسلل (IPS)</h2>

<p dir="rtl" align="right">
تذكير سريع (اتشرح بالتفصيل في الموضوعين 18 و19) — نفس آلية كشف الـ IDS، لكن بيعمل بشكل نشط (Active/In-line) ضمن مسار حركة البيانات مباشرة، وبمجرد اكتشاف تهديد بيقدر يمنعه فوراً بدون انتظار تدخل بشري.
</p>

---

<h2 dir="rtl" align="right" id="network-documentation">9. توثيق الشبكة (Network Documentation)</h2>

<p dir="rtl" align="right">
التوثيق الجيد هو "مفاتيح المملكة" لأي شبكة — من غيره، أي عملية تشخيص أو توسعة مستقبلية بتاخد وقت أطول بكثير وبتعتمد على حفظ الشخص القائم بالصيانة لتفاصيل الشبكة من دماغه بس. أفضل ممارسة: الاحتفاظ بالتوثيق في <strong>ثلاث نسخ</strong> — نسخة إلكترونية سهلة التعديل، نسخة ورقية في مكان يسهل الوصول له، ونسخة على قرص خارجي (ويُفضّل خارج الموقع نفسه) كحماية إضافية لو حصل كارثة فيزيائية.
</p>

<h3 dir="rtl" align="right" id="diagrams">9.1 المخططات وأنواعها (Schematics and Diagrams)</h3>

<ul dir="rtl">
<li><strong>Wiring Diagrams/Schematics (مخططات التوصيلات):</strong> توضّح مسار كل كابل فيزيائياً — من أي منفذ لأي منفذ، عبر أي مسار في المبنى.</li>
<li><strong>Physical Network Diagrams (المخططات الفيزيائية):</strong> بتوضح الموقع الفعلي للأجهزة في العالم الحقيقي — في أي غرفة، أي طابق، أي رف.</li>
<li><strong>Logical Network Diagrams (المخططات المنطقية):</strong> بتوضح إزاي البيانات بتتحرك منطقياً بين الأجهزة (عناوين IP، VLANs، مسارات التوجيه)، بغض النظر عن الموقع الفيزيائي الفعلي.</li>
</ul>

<h3 dir="rtl" align="right" id="asset-management">9.2 إدارة الأصول (Asset Management)</h3>

<p dir="rtl" align="right">
سجل شامل بكل الأجهزة والمعدات المملوكة للمؤسسة — الموديل، الرقم التسلسلي، تاريخ الشراء، حالة الضمان، والموقع الحالي. مهم جداً لتخطيط دورة حياة الأجهزة (راجع System Life Cycle في الموضوع 19) ولأغراض الجرد والتأمين.
</p>

<h3 dir="rtl" align="right" id="vendor-documentation">9.3 توثيق المورّدين (Vendor Documentation)</h3>

<p dir="rtl" align="right">
الاحتفاظ بكل الأدلة والوثائق الرسمية اللي بتوفرها الشركة المصنّعة لكل جهاز — مواصفات فنية، أدلة الإعداد، ومعلومات الدعم الفني والضمان.
</p>

<h3 dir="rtl" align="right" id="baselines-topic23">9.4 خطوط الأساس (Baselines)</h3>

<p dir="rtl" align="right">
تذكير سريع (اتشرحت بالتفصيل في المواضيع 18 و19 و22) — القياس المرجعي للأداء الطبيعي للشبكة، وهو الأساس اللي بيبنى عليه أي تحليل مراقبة لاحق في القسم الأول من الموضوع ده.
</p>

---

<h2 dir="rtl" align="right" id="qos">10. جودة الخدمة (QoS – Quality of Service)</h2>

<p dir="rtl" align="right">
QoS هي مجموعة تقنيات بتتحكم في <strong>كيفية توزيع موارد الشبكة المحدودة</strong> عشان تضمن مستوى أداء معين لأنواع معينة من الحركة، بدل ما تعامل كل حركة البيانات بنفس الأولوية. الفكرة الأساسية: تعطي أولوية أعلى لأنواع حركة حساسة للوقت (زي مكالمات VoIP والفيديو المباشر) على حساب حركة أقل حساسية (زي تنزيل ملف كبير في الخلفية)، عشان لو حصل ازدحام، الحركة الحساسة تفضل سليمة والحركة الأقل أهمية هي اللي تتأثر.
</p>

---

<h2 dir="rtl" align="right" id="qos-types">11. أنواع QoS</h2>

<p dir="rtl" align="right">
QoS بتتحقق عملياً عبر آليتين أساسيتين مكمّلتين لبعض:
</p>

<ul dir="rtl">
<li><strong>Integrated Services (IntServ):</strong> نموذج بيحجز موارد معينة (Bandwidth) لتدفق بيانات محدد مسبقاً من البداية للنهاية عبر الشبكة كلها (End-to-End)، باستخدام بروتوكول زي RSVP (Resource Reservation Protocol). دقيق جداً لكنه معقّد وصعب التوسع على شبكات كبيرة.</li>
<li><strong>Differentiated Services (DiffServ):</strong> النموذج الأكثر شيوعاً في الشبكات الحديثة — بدل حجز موارد لكل تدفق بيانات على حدة، الحركة بتُصنَّف لفئات (Classes) عريضة، وكل فئة بتاخد معاملة معينة عند كل جهاز على المسار بناءً على علامة (Marking) موجودة في رأس الحزمة نفسها (موضّحة بالتفصيل في قسم DSCP، القسم 18). أبسط وأكثر قابلية للتوسع.</li>
</ul>

---

<h2 dir="rtl" align="right" id="qos-congestion-solution">12. حل مشكلة الازدحام في الشبكة بواسطة QoS</h2>

<p dir="rtl" align="right">
لو الشبكة عندها نطاق ترددي زيادة عن الحاجة، مفيش داعي أصلاً لـ QoS — كل الحركة هتعدي بسلاسة. المشكلة بتظهر تحديداً وقت <strong>الازدحام (Congestion)</strong>، لما حجم الحركة المطلوب أكبر من السعة المتاحة على رابط معين. QoS بتحل المشكلة دي مش بزيادة النطاق الترددي الفعلي، لكن بإدارة أذكى للأولويات: الحركة المهمة (زي الصوت) بتتعامل معاها الأجهزة أولاً وبأقل تأخير ممكن، بينما الحركة الأقل أهمية (زي تحديثات الخلفية) بتنتظر دورها أو تتأخر شوية من غير ما يلاحظ المستخدم فرق حقيقي.
</p>

---

<h2 dir="rtl" align="right" id="delay-types">13. أنواع التأخير في الشبكة (Types of Network Delay)</h2>

<p dir="rtl" align="right">
زمن الاستجابة الكلي (End-to-End Delay) اللي بتحسه أي تطبيق فعلياً هو مجموع أربع أنواع تأخير مختلفة بتحصل في كل قفزة على مسار الحزمة:
</p>

<h3 dir="rtl" align="right" id="processing-delay">13.1 وقت المعالجة (Processing Delay)</h3>
<p dir="rtl" align="right">
الوقت اللي بياخده الجهاز (راوتر أو سويتش) عشان يفحص رأس الحزمة الواردة ويقرر إيه المفروض يعمله بيها (يوجّهها لفين، يطبّق عليها أي قاعدة أمنية أو QoS). كل ما زادت القواعد والفحوصات المُعدّة على الجهاز (زي ACLs معقدة)، كل ما زاد وقت المعالجة.
</p>

<h3 dir="rtl" align="right" id="queuing-delay">13.2 وقت الانتظار في الطابور (Queuing Delay)</h3>
<p dir="rtl" align="right">
الوقت اللي الحزمة بتقضيه منتظرة في طابور الانتظار (Queue) بتاع الجهاز، قبل ما يجيلها دورها للمعالجة أو الإرسال. ده التأخير اللي بيتأثر بشكل مباشر جداً بمدى الازدحام على الجهاز، وهو تحديداً النوع اللي آليات صفوف البيانات (Queues، الموضّحة في القسم 16) بتحاول تديره بذكاء.
</p>

<h3 dir="rtl" align="right" id="serialization-delay">13.3 وقت التسلسل (Serialization Delay)</h3>
<p dir="rtl" align="right">
الوقت اللي بياخده الجهاز عشان "يحوّل" الحزمة من بيانات في الذاكرة لإشارة كهربائية أو ضوئية فعلية بترسل عبر الوسيط، بت بت بشكل متسلسل. بيعتمد بشكل مباشر على حجم الحزمة وسرعة الرابط — رابط أبطأ (زي خط WAN قديم) بياخد وقت تسلسل أطول بكثير من رابط Ethernet سريع.
</p>

<h3 dir="rtl" align="right" id="propagation-delay">13.4 وقت الانتشار (Propagation Delay)</h3>
<p dir="rtl" align="right">
الوقت اللي الإشارة نفسها بتاخده عشان "تسافر" فيزيائياً عبر الوسيط الناقل من نقطة لنقطة — بيعتمد بشكل مباشر على <strong>المسافة الفيزيائية</strong> وسرعة انتقال الإشارة في الوسيط المستخدم. ده اللي بيفسّر الـ Latency العالي جداً في اتصالات الأقمار الصناعية (الموضّحة في الموضوع 20) — المسافة الهائلة للقمر الصناعي بتعني وقت انتشار طويل جداً، بغض النظر عن سرعة أي جهاز على المسار.
</p>

---

<h2 dir="rtl" align="right" id="congestion-damages">14. الأضرار الناتجة عن الازدحام داخل الشبكة</h2>

<h3 dir="rtl" align="right" id="lack-bandwidth">14.1 نقص النطاق الترددي (Lack of Bandwidth)</h3>
<p dir="rtl" align="right">
لما الطلب على السعة يتجاوز السعة الفعلية المتاحة على رابط معين باستمرار، النتيجة تدهور عام في الأداء لكل المستخدمين المشتركين في نفس الرابط — الحل الجذري طويل المدى هو ترقية السعة نفسها، وQoS هنا بس بتدير الأولويات مؤقتاً لحد ما الترقية تحصل.
</p>

<h3 dir="rtl" align="right" id="packet-loss">14.2 فقدان الحزم (Packet Loss)</h3>
<p dir="rtl" align="right">
لما طابور الانتظار (Queue) في جهاز معين يمتلئ بالكامل بسبب الازدحام، أي حزمة جديدة وصلت بعد كده بتتسقط تلقائياً (Tail Drop) لأنه مفيش مكان ليها. النتيجة: إعادة إرسال متكررة (بتزود الحمل أكتر) وتدهور ملحوظ في جودة التطبيقات الحساسة.
</p>

<h3 dir="rtl" align="right" id="delay-damage">14.3 التأخير (Delay)</h3>
<p dir="rtl" align="right">
مجموع أنواع التأخير الأربعة الموضّحة في القسم 13 مجتمعة — كل ما زاد الازدحام، زاد بشكل خاص وقت الانتظار في الطابور (Queuing Delay)، وده بيزود زمن الاستجابة الكلي بشكل واضح للمستخدم.
</p>

<h3 dir="rtl" align="right" id="jitter-damage">14.4 التذبذب (Jitter)</h3>
<p dir="rtl" align="right">
عدم انتظام زمن وصول الحزم المتتالية بعضها عن بعض بسبب التفاوت في مستوى الازدحام لحظة بلحظة — حزمة بتوصل بسرعة والتانية بعدها بتتأخر بسبب طابور انتظار امتلأ فجأة. مضر بشكل خاص جداً لتطبيقات الوقت الحقيقي زي VoIP والفيديو المباشر، حتى لو مفيش فقدان حزم خالص.
</p>

---

<h2 dir="rtl" align="right" id="classification-marking">15. التصنيف والتعليم (Classification and Marking)</h2>

<p dir="rtl" align="right">
قبل ما أي جهاز يقدر يعامل أنواع حركة مختلفة بأولويات مختلفة، لازم أولاً <strong>يميّز</strong> بينها. العملية دي بتتم على خطوتين:
</p>

<ul dir="rtl">
<li><strong>Classification (التصنيف):</strong> فحص الحزمة وتحديد أي "فئة" (Class) هي تنتمي ليها — بناءً على البروتوكول، المنفذ، عنوان المصدر أو الوجهة، أو حتى فحص أعمق لمحتوى الحزمة نفسها (Deep Packet Inspection).</li>
<li><strong>Marking (التعليم):</strong> بعد ما تحدد الفئة، الجهاز بيحط "علامة" في رأس الحزمة (زي قيمة DSCP في رأس IP، أو قيمة CoS في رأس Ethernet) عشان أي جهاز تاني على المسار يقدر يتعرف على الفئة دي فوراً من غير ما يحتاج يعيد عملية التصنيف الكاملة من الصفر في كل قفزة — ده بيوفر أداء كبير جداً.</li>
</ul>

<p dir="rtl" align="right">
أفضل ممارسة: التصنيف والتعليم بيتم <strong>أقرب ما يمكن لمصدر الحركة</strong> (عند حافة الشبكة)، وباقي الأجهزة على المسار بتعتمد على العلامة الموجودة أصلاً بدل ما تعيد الفحص من جديد.
</p>

---

<h2 dir="rtl" align="right" id="queues">16. صفوف البيانات (Queues) وأنواعها</h2>

<p dir="rtl" align="right">
بعد ما الحزمة اتصنّفت وعُلِّمت، الجهاز بيحتاج آلية لتحديد <strong>ترتيب إرسالها</strong> من بين كل الحزم المنتظرة. من أشهر آليات الطوابير:
</p>

<ul dir="rtl">
<li><strong>FIFO (First In, First Out):</strong> أبسط آلية — أول حزمة توصل هي أول حزمة تتبعت، من غير أي اعتبار للأولوية. مناسبة بس لو مفيش ازدحام حقيقي أو تفاوت في أهمية الحركة.</li>
<li><strong>Priority Queuing (PQ):</strong> عدة طوابير بأولويات مختلفة تماماً — الطابور الأعلى أولوية بيتفرّغ بالكامل الأول قبل ما أي حزمة من طابور أقل أولوية تتبعت. خطر: لو الطابور عالي الأولوية مزدحم باستمرار، الطوابير الأقل ممكن "تتجوّع" (Starvation) تماماً.</li>
<li><strong>Weighted Fair Queuing (WFQ):</strong> بتوزّع النطاق الترددي المتاح بين كل الطوابير بشكل عادل نسبياً حسب "وزن" كل فئة، بحيث حتى الفئات الأقل أولوية بتاخد نصيبها ولو أقل، من غير ما تتجوّع تماماً.</li>
<li><strong>Class-Based Queuing (CBQ):</strong> بتخصص عرض نطاق ترددي مضمون لكل فئة (Class) بناءً على التصنيف اللي تم في القسم السابق، مع إمكانية استعارة سعة إضافية من فئات تانية مش مستخدمة لسعتها كاملة وقتياً.</li>
</ul>

---

<h2 dir="rtl" align="right" id="cos">17. نظام CoS (Class of Service)</h2>

<p dir="rtl" align="right">
CoS هي آلية تصنيف وتعليم (زي DSCP، لكن على مستوى مختلف) بتشتغل على <strong>طبقة الوصلة (Layer 2 – Ethernet)</strong> بدل طبقة الشبكة. بتستخدم حقل بحجم 3 بت اسمه <strong>PCP (Priority Code Point)</strong> موجود جوه رأس إطار Ethernet المُوسوم بـ VLAN (حسب معيار IEEE 802.1Q)، ومُعرَّفة رسمياً في معيار <strong>IEEE 802.1p</strong>.
</p>

<p dir="rtl" align="right">
<strong>الفرق الجوهري عن DSCP:</strong> CoS بتشتغل بس داخل الشبكة المحلية (LAN) على مستوى الإطار (Frame)، ومش بتنتقل عبر أجهزة التوجيه (Routers) اللي بتشتغل على مستوى الحزمة (Packet) — لأن رأس Ethernet بيتشال ويتبنى من جديد في كل قفزة راوتر. لو عايز تحافظ على الأولوية عبر شبكات متعددة ومتصلة براوترات، DSCP هي الآلية المناسبة، أما CoS فهي الأنسب داخل نطاق شبكة محلية واحدة (LAN Segment).
</p>

---

<h2 dir="rtl" align="right" id="dscp">18. درجات البيانات في جودة الخدمة (DSCP Levels / CoS Levels)</h2>

<p dir="rtl" align="right">
معيار <strong>DSCP (Differentiated Services Code Point)</strong> — أو DiffServ — بيستخدم حقل بحجم 6 بت جوه حقل الـ 8 بت (DS Field) في رأس حزمة IP للتصنيف، وده نظرياً بيسمح بـ 64 فئة حركة مختلفة، لكن عملياً معظم الشبكات بتستخدم أربع تصنيفات أساسية:
</p>

<ul dir="rtl">
<li><strong>Default:</strong> حركة "أفضل جهد ممكن" (Best-Effort) بدون أي أولوية خاصة — التصنيف الافتراضي لمعظم الحركة العادية.</li>
<li><strong>Expedited Forwarding (EF):</strong> مخصصة للحركة الأكثر حساسية للتأخير والفقدان (زي VoIP) — أعلى أولوية.</li>
<li><strong>Assured Forwarding (AF):</strong> بتضمن مستوى معين من التسليم تحت شروط محددة مسبقاً — مناسبة لتطبيقات مهمة لكن أقل حساسية من الصوت المباشر.</li>
<li><strong>Class Selector (CS):</strong> بتحافظ على التوافق العكسي مع حقل IP Precedence القديم (اللي كان جزء من حقل Type of Service - TOS الأصلي).</li>
</ul>

<p dir="rtl" align="right">
وعلى مستوى CoS (Layer 2)، معيار IEEE 802.1p بيحدد <strong>ثماني مستويات</strong> (0 لـ 7) عبر حقل PCP الموضّح في القسم السابق:
</p>

<table>
<tr><th align="center">المستوى</th><th align="center">الوصف</th></tr>
<tr><td align="center">0</td><td align="center">Best Effort (أفضل جهد ممكن)</td></tr>
<tr><td align="center">1</td><td align="center">Background (حركة خلفية)</td></tr>
<tr><td align="center">2</td><td align="center">Standard (احتياطي)</td></tr>
<tr><td align="center">3</td><td align="center">Excellent Load (تطبيقات أعمال حرجة)</td></tr>
<tr><td align="center">4</td><td align="center">Controlled Load (بث وسائط مستمر - Streaming)</td></tr>
<tr><td align="center">5</td><td align="center">Voice and Video (صوت وفيديو تفاعلي، أقل من 100ms تأخير وتذبذب)</td></tr>
<tr><td align="center">6</td><td align="center">Layer 3 Network Control (أقل من 10ms تأخير وتذبذب)</td></tr>
<tr><td align="center">7</td><td align="center">Layer 2 Network Control (أقل تأخير وتذبذب على الإطلاق)</td></tr>
</table>

<p dir="rtl" align="right">
مستويات QoS غالباً بتُحدَّد لكل مكالمة أو جلسة، أو مسبقاً عبر اتفاقية مستوى خدمة (SLA — راجع الموضوع 19).
</p>

---

<h2 dir="rtl" align="right" id="load-balancing">19. عملية توزيع الحمل (Load Balancing / NLB / Cluster)</h2>

<p dir="rtl" align="right">
توزيع الحمل هو توزيع الطلبات الواردة على أكتر من مورد (سيرفر، رابط، مسار) عوضاً عن الاعتماد على مورد واحد بس، وده بيحقق هدفين مهمين في نفس الوقت: <strong>تحسين الأداء</strong> (كل الموارد شغالة معاً بدل واحد بس) و <strong>التكرارية/التوافرية العالية</strong> (لو مورد واحد فشل، الباقي يكمّل الشغل).
</p>

<h3 dir="rtl" align="right" id="nlb-cluster-types">19.1 أنواع NLB و Cluster</h3>

<ul dir="rtl">
<li><strong>NLB (Network Load Balancing):</strong> توزيع طلبات الشبكة (غالباً على مستوى تطبيق ويب أو خدمة) على عدة سيرفرات متطابقة تبدو للمستخدم النهائي وكأنها خدمة واحدة، عبر جهاز أو برنامج موزّع أحمال (Load Balancer) يقف أمام السيرفرات دي.</li>
<li><strong>Cluster (العنقود):</strong> مجموعة سيرفرات مرتبطة ببعض بتشتغل معاً كوحدة واحدة منطقياً — بتشارك نفس المهمة وبتعرف حالة بعضها البعض، بحيث لو سيرفر واحد فشل، سيرفر تاني في العنقود يقدر ياخد مكانه فوراً (Failover) من غير انقطاع ملحوظ للخدمة.</li>
</ul>

<h3 dir="rtl" align="right" id="load-balancing-levels">19.2 توزيع الحمل على مستوى المسارات والسيرفرات والراوترات</h3>

<ul dir="rtl">
<li><strong>على مستوى السيرفرات:</strong> الشكل الأشيع — عدة سيرفرات ويب أو تطبيقات متطابقة، وموزّع الأحمال بيقرر يوجّه كل طلب جديد لأي سيرفر بناءً على خوارزمية معينة (Round Robin، أقل عدد اتصالات نشطة، أو حسب حمل المعالج الفعلي).</li>
<li><strong>على مستوى المسارات (الروابط):</strong> توزيع حركة البيانات على أكتر من رابط اتصال متاح بين نفس النقطتين بدل الاعتماد على رابط واحد بس (زي مفهوم Redundant Circuits الموضّح في الموضوع 20) — بيزود عرض النطاق الترددي الكلي المتاح وبيوفر تكرارية لو رابط واحد فشل.</li>
<li><strong>على مستوى الراوترات:</strong> بروتوكولات زي <strong>HSRP</strong> (Hot Standby Router Protocol) أو <strong>VRRP</strong> (Virtual Router Redundancy Protocol) بتسمح لأكتر من راوتر فيزيائي يشتركوا في تمثيل "بوابة افتراضية واحدة" (Virtual IP) للأجهزة في الشبكة المحلية — لو الراوتر النشط فشل، راوتر احتياطي ياخد مكانه فوراً وبشكل شفاف تماماً من منظور الأجهزة المتصلة، من غير ما تحتاج تغيّر إعداد البوابة عندها خالص.</li>
</ul>

---

<h2 dir="rtl" align="right" id="policies-procedures">20. السياسات والإجراءات واللوائح</h2>

<p dir="rtl" align="right">
إدارة الشبكة مش بس تقنية — جزء كبير منها إداري وقانوني. القسم ده بيغطي الإطار المؤسسي اللي بيحكم كل قرار تقني.
</p>

<h3 dir="rtl" align="right" id="policies-list">20.1 السياسات (Policies)</h3>

<ul dir="rtl">
<li><strong>Privileged User Agreement (اتفاقية المستخدم المتميز):</strong> وثيقة رسمية بيوقّعها أي موظف عنده صلاحيات إدارية عالية (زي مدير نظام أو شبكة)، بتوضح مسؤولياته الإضافية والقيود المفروضة على استخدام صلاحياته دي.</li>
<li><strong>Password Policy (سياسة كلمات المرور):</strong> القواعد الرسمية لتعقيد وطول ودورية تغيير كلمات المرور — راجع مبادئها في الموضوع 18.</li>
<li><strong>On-boarding/Off-boarding Procedures (إجراءات التعيين وإنهاء الخدمة):</strong> خطوات موحّدة لإنشاء (أو حذف فوري) حسابات وصلاحيات الموظف عند التحاقه بالعمل أو تركه — التأخير في إجراءات Off-boarding من أشهر الثغرات الأمنية الحقيقية في المؤسسات.</li>
<li><strong>Licensing Restrictions / International Export Controls:</strong> تذكير سريع (اتشرحوا بالتفصيل في الموضوع 18).</li>
<li><strong>Data Loss Prevention – DLP (منع فقدان البيانات):</strong> سياسات وأدوات تقنية بتمنع تسريب البيانات الحساسة خارج المؤسسة (عبر البريد، أجهزة USB، أو رفعها لخدمات سحابية غير مصرح بها).</li>
<li><strong>Remote Access Policies (سياسات الوصول عن بعد):</strong> القواعد الحاكمة لاتصال الموظفين بشبكة المؤسسة من خارجها (عبر VPN غالباً)، وبتحدد مين مسموح له، وبأي أجهزة، وتحت أي شروط أمنية.</li>
<li><strong>Incident Response Policies:</strong> تذكير سريع (اتشرحت بالتفصيل في الموضوع 18).</li>
<li><strong>BYOD (Bring Your Own Device):</strong> سياسة تحدد شروط استخدام الموظفين لأجهزتهم الشخصية (موبايل، لابتوب) للوصول لموارد الشركة، وبتوازن بين مرونة الموظف ومخاطر أمنية إضافية (جهاز غير مُدار بالكامل من الشركة).</li>
<li><strong>AUP (Acceptable Use Policy – سياسة الاستخدام المقبول):</strong> توضح بالتفصيل الاستخدامات المسموحة والممنوعة لموارد الشبكة والإنترنت التابعة للمؤسسة.</li>
<li><strong>NDA (Non-Disclosure Agreement – اتفاقية عدم الإفصاح):</strong> عقد قانوني بيلزم الموظف أو المتعاقد بعدم الإفصاح عن معلومات سرية خاصة بالمؤسسة، حتى بعد انتهاء علاقته بيها.</li>
<li><strong>System Life Cycle:</strong> تذكير سريع (اتشرح بالتفصيل في الموضوع 18)، شاملاً Asset Disposal (التخلص السليم من الأصول).</li>
</ul>

<h3 dir="rtl" align="right" id="procedures-list">20.2 الإجراءات (Procedures)</h3>

<p dir="rtl" align="right">
الإجراءات هي "التطبيق العملي" للسياسات — خطوات محددة ومفصّلة خطوة بخطوة لتنفيذ سياسة معينة عملياً (زي الخطوات الفنية بالتفصيل لإنشاء حساب مستخدم جديد ضمن سياسة On-boarding). الفرق الجوهري: السياسة بتقول "إيه المطلوب"، والإجراء بيقول "إزاي بالضبط يتم تنفيذه".
</p>

<h3 dir="rtl" align="right" id="business-documents">20.3 المستندات القياسية للأعمال (Standard Business Documents)</h3>

<ul dir="rtl">
<li><strong>SLA (Service Level Agreement):</strong> تذكير سريع (اتشرح في الموضوع 19) — التزام رسمي بمستوى خدمة محدد بالأرقام.</li>
<li><strong>MOU (Memorandum of Understanding):</strong> مذكرة تفاهم غير ملزمة قانونياً بشكل كامل، بتوثق اتفاق عام بين طرفين على التعاون في مجال معين.</li>
<li><strong>MSA (Master Service Agreement):</strong> عقد إطاري شامل بيحدد الشروط العامة اللي هتحكم كل التعاملات المستقبلية بين طرفين، بحيث مفيش داعي يتفاوضوا من الصفر في كل مرة.</li>
</ul>

<h3 dir="rtl" align="right" id="regulations">20.4 اللوائح التنظيمية (Regulations)</h3>

<p dir="rtl" align="right">
معايير قانونية أو صناعية إلزامية بتفرضها جهات خارجية (حكومية أو صناعية) على المؤسسة، وعدم الالتزام بيها بيعرّض المؤسسة لعقوبات قانونية أو مالية — زي معايير حماية بيانات معينة حسب طبيعة الصناعة (المالية، الصحية، إلخ) أو حسب الدولة اللي بتعمل فيها المؤسسة.
</p>

---

<h2 dir="rtl" align="right" id="safety-practices">21. إجراءات السلامة (Safety Practices)</h2>

<h3 dir="rtl" align="right" id="electrical-safety">21.1 السلامة الكهربائية (Electrical Safety)</h3>
<p dir="rtl" align="right">
إجراءات لحماية الأفراد من مخاطر الصعق الكهربائي عند التعامل مع معدات الشبكة، والحماية من الحرائق الناتجة عن مشاكل كهربائية — زي استخدام مقابس مؤرَّضة (Grounded) بشكل صحيح، وعدم تحميل دوائر كهربائية زيادة عن طاقتها.
</p>

<h3 dir="rtl" align="right" id="installation-safety">21.2 سلامة التركيب (Installation Safety)</h3>
<p dir="rtl" align="right">
ممارسات آمنة أثناء تركيب المعدات والكابلات نفسها — زي تجنّب مد كابلات عبر أرضية مفتوحة (خطر تعثّر وتلف الكابل، زي ما اتشرح في الموضوع 22)، والالتزام بأقصى نصف قطر انحناء (Bend Radius) مسموح لكابلات الألياف الضوئية.
</p>

<h3 dir="rtl" align="right" id="emergency-procedures">21.3 إجراءات الطوارئ (Emergency Procedures)</h3>
<p dir="rtl" align="right">
خطط واضحة وموثّقة للتصرف في حالات الطوارئ (حريق، زلزال، انقطاع كهرباء طويل) — تشمل مسارات إخلاء واضحة، ومواقع أزرار قطع الطاقة الفورية (EPO – Emergency Power Off) في غرف السيرفرات.
</p>

<h3 dir="rtl" align="right" id="hvac">21.4 التحكم بالحرارة والتهوية (HVAC)</h3>
<p dir="rtl" align="right">
أنظمة التكييف والتهوية (Heating, Ventilation, and Air Conditioning) ضرورية جداً لغرف السيرفرات — المعدات بتولّد حرارة كبيرة، والحرارة الزايدة أو الرطوبة غير المضبوطة بتقلل عمر المعدات وبتزود احتمالية الأعطال بشكل كبير (راجع الظروف الفيزيائية في الموضوع 22).
</p>

---

<h2 dir="rtl" align="right" id="network-segmentation">22. تجزئة الشبكة (Network Segmentation)</h2>

<h3 dir="rtl" align="right" id="medianets">22.1 Medianets</h3>
<p dir="rtl" align="right">
شبكات مُصمَّمة ومُهيَّأة خصيصاً لنقل وسائط الاتصال الحساسة (صوت وفيديو) بأفضل جودة ممكنة، غالباً بتطبيق QoS بشكل مكثّف ومخصص لهذا النوع من الحركة تحديداً.
</p>

<h3 dir="rtl" align="right" id="vtc">22.2 مؤتمرات الفيديو (VTC – Video Teleconferencing)</h3>
<p dir="rtl" align="right">
أنظمة الاتصال المرئي بين مواقع متعددة — بتحتاج عرض نطاق ترددي عالي وثابت وحساسية شديدة لكل من الـ Latency والـ Jitter (الموضّحين في القسم 13/14)، وده بيخليها من أكبر المستفيدين من تطبيق QoS بشكل صحيح.
</p>

<h3 dir="rtl" align="right" id="legacy-systems">22.3 الأنظمة القديمة (Legacy Systems)</h3>
<p dir="rtl" align="right">
أجهزة أو أنظمة قديمة لسه شغالة في الشبكة لكنها مش بتدعم معايير أو بروتوكولات حديثة (زي أجهزة مش بتدعم تشفير حديث). أفضل ممارسة أمنية: عزل الأنظمة دي في شبكة فرعية منفصلة (VLAN مخصص) عشان تقلل خطرها على باقي الشبكة الحديثة.
</p>

<h3 dir="rtl" align="right" id="public-private-separation">22.4 فصل الشبكات الخاصة عن العامة</h3>
<p dir="rtl" align="right">
مبدأ أساسي في تصميم الشبكة — فصل الشبكة الداخلية الخاصة (اللي فيها بيانات وأنظمة حساسة) تماماً عن أي شبكة عامة أو متاحة للزوار (Guest Wi-Fi مثلاً)، بحيث اختراق واحدة ميديش وصول مباشر للتانية. نفس المبدأ اللي عليه مبنية فكرة الـ DMZ (الموضّحة بالتفصيل في الموضوع 19).
</p>

<h3 dir="rtl" align="right" id="honeypot-topic23">22.5 Honeypot / Honeynet</h3>
<p dir="rtl" align="right">
تذكير سريع (اتشرحت بالتفصيل الكامل في الموضوع 19، شاملة Hardware مقابل Software Honeypot وDecoys وDNS Sinkholes) — أنظمة وهمية مصممة لجذب المهاجمين ودراسة أساليبهم بمعزل عن الأصول الحقيقية.
</p>

<h3 dir="rtl" align="right" id="testing-lab">22.6 بيئة الاختبار (Testing Lab)</h3>
<p dir="rtl" align="right">
شبكة فرعية معزولة تماماً عن بيئة الإنتاج (Production)، مخصصة لتجربة تحديثات أو إعدادات جديدة قبل تطبيقها فعلياً على الشبكة الحقيقية — بتقلل جذرياً من مخاطر إن تغيير جديد يسبب مشكلة غير متوقعة في بيئة العمل الفعلية.
</p>

<h3 dir="rtl" align="right" id="compliance">22.7 الامتثال (Compliance)</h3>
<p dir="rtl" align="right">
التأكد من إن تصميم وتجزئة الشبكة متوافقين مع اللوائح التنظيمية المطلوبة (الموضّحة في القسم 20.4) — أحياناً التجزئة نفسها بتكون شرط إلزامي قانوني (زي عزل بيانات مالية حساسة في شبكة فرعية منفصلة تماماً).
</p>

---

<h2 dir="rtl" align="right" id="optimization-additions">23. إضافات تحسين الأداء</h2>

<h3 dir="rtl" align="right" id="unified-communications">23.1 الاتصالات الموحدة (Unified Communications – UC)</h3>
<p dir="rtl" align="right">
دمج خدمات الاتصال الفوري (زي الرسائل الفورية) مع خدمات غير فورية (زي البريد الصوتي والفاكس) في منظومة واحدة متكاملة، بحيث الشخص يقدر يستقبل نفس الرسالة عبر وسيط مختلف عن اللي أُرسلت بيه. بتتكوّن من: <strong>UC Servers</strong> (قلب النظام، بيدير التحكم بالمكالمات)، <strong>UC Devices</strong> (نقاط النهاية زي الكمبيوترات والهواتف الذكية)، و <strong>UC Gateways</strong> (بتربط الشبكة القائمة على IP بشبكة الهاتف التقليدية PSTN).
</p>

<h3 dir="rtl" align="right" id="traffic-shaping">23.2 تشكيل الحركة (Traffic Shaping)</h3>
<p dir="rtl" align="right">
تقنية تحسين أخرى — بتأخّر عمداً حزم معينة (بتخزينها مؤقتاً في طابور FIFO) بتستوفي شروط معينة، عشان تضمن عرض نطاق ترددي كافٍ لحركة تانية أهم. بتستخدم مبدأ "عقد حركة" (Traffic Contract) بيحدد أي حزم مسموح لها تعدي ومتى — بتُطبَّق غالباً عند حافة الشبكة للتحكم في الحركة الداخلة.
</p>

<h3 dir="rtl" align="right" id="caching-engines">23.3 محركات التخزين المؤقت (Caching Engines)</h3>
<p dir="rtl" align="right">
أجهزة أو برامج بتحتفظ بنسخة محلية من محتوى كثير الطلب (صفحات ويب، ملفات) قريبة من المستخدمين، بدل ما كل طلب يروح لمصدره الأصلي البعيد في كل مرة — بيقلل استهلاك النطاق الترددي بشكل كبير للمحتوى المتكرر، وبيسرّع زمن الاستجابة للمستخدم.
</p>

<h3 dir="rtl" align="right" id="ha-topic23">23.4 التوافرية العالية (High Availability)</h3>
<p dir="rtl" align="right">
تذكير سريع — تصميم بيضمن استمرار الخدمة شغالة بأقل قدر ممكن من التوقف، غالباً بالجمع بين التكرارية (Redundancy) والتبديل التلقائي عند العطل (Failover)، ومرتبطة مباشرة بمفاهيم Load Balancing وClustering الموضّحة في القسم 19.
</p>

<h3 dir="rtl" align="right" id="ft-topic23">23.5 تحمّل الأعطال (Fault Tolerance)</h3>
<p dir="rtl" align="right">
تذكير سريع (اتشرح كمفهوم في المواضيع السابقة) — قدرة النظام على الاستمرار في العمل حتى لو فشل أحد مكوناته، عادةً عبر مكونات احتياطية (زي NIC Teaming الموضّح في الموضوع 22، أو Dual Power Supplies الموضّحة في الموضوع 19).
</p>

<h3 dir="rtl" align="right" id="backups-topic23">23.6 النسخ الاحتياطي (Archives/Backups)</h3>
<p dir="rtl" align="right">
تذكير سريع (اتشرحت أنواعه الثلاثة بالتفصيل الكامل في الموضوع 19: Full, Differential, Incremental).
</p>

<h3 dir="rtl" align="right" id="carp">23.7 بروتوكول CARP (Common Address Redundancy Protocol)</h3>
<p dir="rtl" align="right">
بروتوكول مفتوح المصدر (بديل غير مسجّل ملكية لبروتوكولات زي HSRP وVRRP الموضّحة في القسم 19.2) بيسمح لمجموعة من الأجهزة (غالباً فايروولات أو راوترات) تشترك في عنوان IP واحد (Virtual IP)، بحيث لو الجهاز النشط فشل، جهاز تاني في المجموعة ياخد مكانه فوراً بشكل شفاف تماماً.
</p>

---

<h2 dir="rtl" align="right" id="virtual-networking">24. الشبكات الافتراضية (Virtual Networking)</h2>

<p dir="rtl" align="right">
فكرة الافتراضية بسيطة: بدل تخصيص جهاز فيزيائي منفصل لكل سيرفر، بتشغّل عدة نسخ من نظام التشغيل، كل واحدة في "بيئة افتراضية" مستقلة، على نفس القطعة الفيزيائية الواحدة — ده بيوفر في الطاقة، وبيعظّم استغلال موارد المعالج والذاكرة.
</p>

<h3 dir="rtl" align="right" id="hypervisor">24.1 الـ Hypervisor</h3>
<p dir="rtl" align="right">
البرنامج المسؤول عن إدارة توزيع موارد الجهاز الفيزيائي (Host) على كل الأجهزة الافتراضية (VMs) الشغالة فوقه. نوعان أساسيان:
</p>
<ul dir="rtl">
<li><strong>Type I (Native / Bare Metal):</strong> بيشتغل مباشرة فوق هاردوير الجهاز المضيف بدون نظام تشغيل وسيط — أمثلة: VMware vSphere و Microsoft Hyper-V. أداء أعلى، وشائع في بيئات السيرفرات والإنتاج.</li>
<li><strong>Type II (Hosted):</strong> بيشتغل فوق نظام تشغيل عادي موجود بالفعل على الجهاز — أمثلة: VMware Workstation و VirtualBox. أسهل في الإعداد، وشائع للاستخدام الشخصي والتجريبي.</li>
</ul>

<h3 dir="rtl" align="right" id="vswitch">24.2 السويتش الافتراضي (vSwitch)</h3>
<p dir="rtl" align="right">
نسخة برمجية من سويتش الطبقة الثانية، بتقدر تنشئ VLANs وتوصّل السيرفرات الافتراضية ببعضها، وكل ده داخل نفس الجهاز الفيزيائي الواحد. الـ <strong>Distributed Virtual Switch</strong> نوع متقدم منه بيمتد عبر عدة أجهزة Hosts فيزيائية مختلفة، وبيربط الأجهزة الافتراضية اللي في نفس العنقود (Cluster) حتى لو موزّعة على أجهزة مختلفة.
</p>

<h3 dir="rtl" align="right" id="vnic">24.3 كارت الشبكة الافتراضي (vNIC)</h3>
<p dir="rtl" align="right">
كل جهاز افتراضي (VM) عنده كارت شبكة افتراضي خاص بيه (vNIC) بيتصل بالسويتش الافتراضي، واللي بدوره بيتصل بكارت الشبكة الفيزيائي الحقيقي (NIC) على الجهاز المضيف. نقطة مهمة للامتحان: كارت الشبكة الفيزيائي الواحد بيقدر ينقل حركة بعناوين MAC افتراضية متعددة مختلفة في نفس الوقت، واحد لكل VM.
</p>

<h3 dir="rtl" align="right" id="vrouter">24.4 الراوتر الافتراضي (vRouter)</h3>
<p dir="rtl" align="right">
برمجية بتنفّذ وظيفة التوجيه بشكل مستقل — كل راوتر افتراضي عنده جدول توجيه خاص بيه منفصل عن باقي الراوترات الافتراضية التانية على نفس الجهاز المضيف.
</p>

<h3 dir="rtl" align="right" id="vfirewall">24.5 الجدار الناري الافتراضي (vFirewall)</h3>
<p dir="rtl" align="right">
نفس فكرة الجدار الناري الفيزيائي، لكن كبرنامج بالكامل — بيُستخدم للتحكم في الحركة بين الشبكات الفرعية الافتراضية اللي أنشأها الـ vRouter.
</p>

<h3 dir="rtl" align="right" id="sdn">24.6 الشبكات مُعرَّفة البرمجيات (SDN – Software-Defined Networking)</h3>
<p dir="rtl" align="right">
منهج حديث بيفصل بين <strong>طبقة التحكم (Control Plane)</strong> — اللي بتقرر إزاي تتوجه الحركة — و <strong>طبقة نقل البيانات الفعلي (Data Plane)</strong> على الأجهزة نفسها، وبيخلي التحكم في الشبكة كله <strong>قابل للبرمجة مركزياً</strong> بدل ما يكون موزّع على كل جهاز بمفرده. نفس الفلسفة اللي بُنيت عليها معمارية SD-WAN الموضّحة بالتفصيل في الموضوع 20 (Control Plane مقابل Data Plane)، لكن هنا مطبّقة على مستوى الشبكة الداخلية (LAN/Data Center) بدل الـ WAN.
</p>

<h3 dir="rtl" align="right" id="jumbo-frame">24.7 الإطارات العملاقة (Jumbo Frame)</h3>
<p dir="rtl" align="right">
إطارات Ethernet بحمولة بيانات أكبر من الحد الافتراضي (1500 بايت) — ممكن توصل لأكتر من 9000 بايت. استخدامها بيقلل الحمل الإضافي (Overhead) ودورات معالجة المعالج المطلوبة لكل نفس الكمية من البيانات، لأن عدد الإطارات المطلوبة يقل بشكل كبير. مفيدة جداً في الشبكات عالية السرعة، وخصوصاً في بيئات شبكات التخزين (SAN، الموضّحة في القسم التالي) حيث بتتحسّن الأداء بشكل ملحوظ.
</p>

---

<h2 dir="rtl" align="right" id="storage-networks">25. شبكات التخزين (Storage Networks)</h2>

<h3 dir="rtl" align="right" id="san">25.1 شبكة منطقة التخزين (SAN – Storage Area Network)</h3>
<p dir="rtl" align="right">
شبكة عالية السعة مخصصة بالكامل لتوصيل أجهزة تخزين البيانات، ومنفصلة فيزيائياً عن شبكة LAN العادية، عبر سويتش متخصص في التخزين. الفكرة: عزل حركة التخزين الثقيلة عن حركة المستخدمين العادية، لضمان أداء عالٍ ومستقر لكليهما.
</p>

<h3 dir="rtl" align="right" id="nas">25.2 التخزين المتصل بالشبكة (NAS – Network-Attached Storage)</h3>
<p dir="rtl" align="right">
بديل أبسط للـ SAN — بيوفر نفس الوظيفة (تخزين مركزي مشترك) لكن أي جهاز متصل بشبكة LAN العادية يقدر يوصله ويشارك ملفات معاه مباشرة، باستخدام بروتوكولات مألوفة زي NFS وCIFS وHTTP، بدون الحاجة لبنية تحتية متخصصة منفصلة زي الـ SAN.
</p>

<table>
<tr><th align="center">المقارنة</th><th align="center">SAN</th><th align="center">NAS</th></tr>
<tr><td align="center">مستوى الوصول</td><td align="center">مستوى الكتلة (Block-Level) عبر بروتوكول Fibre Channel متخصص</td><td align="center">مستوى الملف (File-Level) عبر بروتوكولات شبكة عادية (NFS/CIFS)</td></tr>
<tr><td align="center">البنية التحتية</td><td align="center">شبكة منفصلة تماماً عن LAN</td><td align="center">تستخدم نفس شبكة LAN الموجودة</td></tr>
<tr><td align="center">التعقيد والتكلفة</td><td align="center">أعلى تعقيداً وتكلفة</td><td align="center">أبسط وأرخص في الإعداد</td></tr>
<tr><td align="center">الأداء المتخصص</td><td align="center">أعلى أداءً للأحمال الثقيلة جداً</td><td align="center">كافٍ لمعظم احتياجات مشاركة الملفات العادية</td></tr>
</table>

<h3 dir="rtl" align="right" id="iscsi">25.3 بروتوكول iSCSI</h3>
<p dir="rtl" align="right">
معيار بيسمح بتغليف أوامر SCSI (البروتوكول التقليدي للتخزين) داخل حزم IP عادية — وده بيسمح باستخدام نفس شبكة IP العادية لنقل حركة التخزين بدل الحاجة لبنية تحتية منفصلة تماماً زي الـ Fibre Channel. حل اقتصادي شائع جداً للحصول على مميزات SAN من غير تكلفة البنية التحتية المتخصصة الكاملة.
</p>

<h3 dir="rtl" align="right" id="fibre-channel">25.4 Fibre Channel و FCoE</h3>
<ul dir="rtl">
<li><strong>Fibre Channel (FC):</strong> تقنية شبكية عالية السرعة (بسرعات شائعة 2، 4، 8، 16 جيجابت في الثانية) مخصصة أساساً لتوصيل أجهزة تخزين البيانات، وبتشتغل عبر شبكة ضوئية منفصلة تماماً وغير متوافقة مع شبكة IP العادية.</li>
<li><strong>FCoE (Fibre Channel over Ethernet):</strong> بتغلّف حركة Fibre Channel داخل إطارات Ethernet عادية (بنفس فكرة iSCSI تقريباً، لكن مش بتستخدم IP خالص) — بتسمح بمرور حركة التخزين المتخصصة دي عبر شبكة Ethernet موجودة بالفعل.</li>
</ul>

<h3 dir="rtl" align="right" id="infiniband">25.5 معيار InfiniBand</h3>
<p dir="rtl" align="right">
معيار اتصال بأداء عالي جداً وزمن استجابة منخفض جداً، بيُستخدم كوصلة مباشرة أو مُبدَّلة (Switched) بين السيرفرات وأنظمة التخزين، أو بين أنظمة التخزين مع بعضها. بيستخدم معمارية "نسيج تبديل" (Switched Fabric)، ومحولاته بتقدر تتبادل معلومات عن جودة الخدمة (QoS) بينها مباشرة.
</p>

---

<h2 dir="rtl" align="right" id="cloud-computing">26. الحوسبة السحابية (Cloud Concepts)</h2>

<p dir="rtl" align="right">
التخزين السحابي بيضع البيانات على سيرفر مركزي، لكن على عكس مركز البيانات الداخلي التقليدي، البيانات دي متاح الوصول ليها من أي مكان وغالباً من أنواع أجهزة مختلفة جداً. الحلول السحابية عادةً بتوفر تحمّل أعطال وتخصيص موارد حوسبة ديناميكي (معالج، ذاكرة، شبكة) حسب الحاجة الفعلية.
</p>

<h3 dir="rtl" align="right" id="cloud-service-models">26.1 نماذج الخدمة السحابية (Service Models)</h3>

<table>
<tr><th align="center">النموذج</th><th align="center">ماذا يوفّر المزوّد</th><th align="center">ماذا تدير المؤسسة بنفسها</th></tr>
<tr><td align="center"><strong>IaaS (Infrastructure as a Service)</strong></td><td align="center">البنية التحتية أو مركز البيانات (الهاردوير فقط)</td><td align="center">أنظمة التشغيل والتطبيقات بالكامل</td></tr>
<tr><td align="center"><strong>PaaS (Platform as a Service)</strong></td><td align="center">البنية التحتية + نظام التشغيل والمنصة البرمجية</td><td align="center">التطبيقات نفسها بس</td></tr>
<tr><td align="center"><strong>SaaS (Software as a Service)</strong></td><td align="center">كل شيء — البنية التحتية، النظام، التطبيق كامل جاهز للاستخدام</td><td align="center">لا شيء تقريباً، فقط الاستخدام</td></tr>
</table>

<h3 dir="rtl" align="right" id="cloud-deployment-models">26.2 نماذج النشر السحابي (Deployment Models)</h3>

<ul dir="rtl">
<li><strong>Private Cloud (سحابة خاصة):</strong> مملوكة ومُدارة من مؤسسة واحدة لاستخدامها الحصري بس.</li>
<li><strong>Public Cloud (سحابة عامة):</strong> بتوفرها جهة خارجية (طرف ثالث) — بتنقل التفاصيل التقنية للمزوّد لكن بتتنازل عن جزء من التحكم، وممكن تفتح ثغرات أمنية إضافية.</li>
<li><strong>Hybrid Cloud (سحابة هجينة):</strong> مزيج بين الخاصة والعامة — مثلاً تستخدم بنية المزوّد التحتية لكن تدير بياناتك بنفسك.</li>
<li><strong>Community Cloud (سحابة مجتمعية):</strong> مملوكة ومُدارة من مجموعة مؤسسات بتشترك في هدف مشترك واحد.</li>
</ul>

<h3 dir="rtl" align="right" id="cloud-connectivity">26.3 طرق الاتصال بالسحابة (Connectivity Methods)</h3>

<ul dir="rtl">
<li><strong>VPN:</strong> الطريقة الأكثر مباشرة — زي خدمة Amazon VPC اللي بتنشئ اتصال VPN كامل بين شبكة المؤسسة بأكملها والسحابة.</li>
<li><strong>Remote Desktop (RDP):</strong> اتصال مباشر بسيرفر معين بدل الشبكة كاملة — RDP لسيرفرات Windows، وSSH (الموضّح في الموضوع 21) لسيرفرات Linux.</li>
<li><strong>FTP:</strong> مناسب لعمليات نقل البيانات بالجملة (Bulk Downloads).</li>
<li><strong>VMware Remote Console:</strong> بيسمح بتوصيل قرص DVD محلي افتراضياً للسيرفر السحابي، مفيد لرفع ملفات تثبيت أو صور ISO.</li>
</ul>

<h3 dir="rtl" align="right" id="cloud-security">26.4 الاعتبارات الأمنية للحوسبة السحابية</h3>

<ul dir="rtl">
<li>السحابة معرّضة لنفس أنواع الهجمات اللي بتتعرضلها البيئات المحلية بالضبط (زي هجمات التصيّد اللي بتستهدف موظفي المزوّد نفسه).</li>
<li>كتير من العملاء بيفشلوا يتأكدوا إن المزوّد فعلاً بيحمي بياناتهم بنفس الجدية في البيئات متعددة المستأجرين (Multi-tenant).</li>
<li>مفيش معيار عالمي موحّد بيحكم خصوصية البيانات عند كل مزودي الخدمة.</li>
<li>أمان البيانات بيختلف بشكل كبير حسب الدولة، والعميل غالباً مش عارف بياناته فعلياً فين جغرافياً في أي لحظة.</li>
</ul>

<h3 dir="rtl" align="right" id="cloud-vs-local">26.5 العلاقة بين الموارد المحلية والسحابية</h3>

<table>
<tr><th align="center">وجه المقارنة</th><th align="center">البيئة المحلية (Local)</th><th align="center">البيئة السحابية (Cloud)</th></tr>
<tr><td align="center">الاستثمار الأولي في البنية التحتية</td><td align="center">مرتفع (معدات + فريق إدارة)</td><td align="center">منخفض جداً</td></tr>
<tr><td align="center">قابلية التوسع</td><td align="center">تحتاج استثمار إضافي في كل مرة</td><td align="center">فورية وسريعة جداً</td></tr>
<tr><td align="center">نموذج التكلفة</td><td align="center">نفقات رأسمالية (CapEx)</td><td align="center">اشتراكات شهرية دورية (OpEx)</td></tr>
<tr><td align="center">مستوى التحكم</td><td align="center">تحكم كامل للمؤسسة</td><td align="center">تحكم جزئي، بعضه بيد المزوّد</td></tr>
<tr><td align="center">معرفة موقع البيانات</td><td align="center">معروف ومؤكد دائماً</td><td align="center">قد يتغيّر ومش دائماً واضح</td></tr>
</table>

---

<h2 dir="rtl" align="right" id="equipment-location">27. تركيب المعدات وموقعها</h2>

<h3 dir="rtl" align="right" id="mdf-idf">27.1 غرفة التوزيع الرئيسية والفرعية (MDF / IDF)</h3>
<ul dir="rtl">
<li><strong>MDF (Main Distribution Frame):</strong> النقطة المركزية اللي فيها كل خطوط الاتصال الخارجية والداخلية بتتجمع — غالباً غرفة السيرفرات الرئيسية.</li>
<li><strong>IDF (Intermediate Distribution Frame):</strong> نقاط توزيع فرعية (غالباً غرفة أو خزانة على كل طابور أو منطقة) بتتصل بالـ MDF وبتوزّع الاتصال للمستخدمين النهائيين في منطقتها.</li>
</ul>

<h3 dir="rtl" align="right" id="cable-management">27.2 إدارة الكابلات (Cable Management)</h3>
<p dir="rtl" align="right">
تنظيم فيزيائي منهجي للكابلات (حاملات كابلات، ترقيم، تجميع منظّم) — بيسهّل التتبع والتشخيص المستقبلي بشكل كبير جداً، ويقلل مخاطر التلف الفيزيائي والتشابك.
</p>

<h3 dir="rtl" align="right" id="power-management-topic23">27.3 إدارة الطاقة (Power Management)</h3>
<p dir="rtl" align="right">
تذكير سريع (اتشرحت بالتفصيل في الموضوع 19: UPS، المولدات، مصادر الطاقة المزدوجة) — التخطيط السليم لتوزيع الطاقة على كل معدات الـ Rack بأمان وبدون تحميل زيادة.
</p>

<h3 dir="rtl" align="right" id="device-placement">27.4 وضع الأجهزة (Device Placement)</h3>
<p dir="rtl" align="right">
مبدأ عملي مهم: الأجهزة المتاحة للإنترنت (زي سيرفر الويب العام) لازم توضع في الـ DMZ، بينما الأجهزة الداخلية الحساسة (زي سيرفر ملفات داخلي) توضع داخل الشبكة الداخلية المحمية. الجدار الناري نفسه غالباً بيوضع مباشرة بعد الراوتر الحدودي (Border Router) القادم من الإنترنت.
</p>

<h3 dir="rtl" align="right" id="labeling">27.5 التسميات (Labeling)</h3>
<p dir="rtl" align="right">
تسمية واضحة ومتسقة لكل كابل، منفذ، وجهاز — تبدو تفصيلة بسيطة، لكنها بتوفر وقت هائل في أي عملية تشخيص أو صيانة مستقبلية، خصوصاً لو الشخص اللي بيصلّح المشكلة مش هو اللي ركّب الشبكة أصلاً.
</p>

<h3 dir="rtl" align="right" id="rack-monitoring-security">27.6 مراقبة وأمان الـ Rack</h3>
<p dir="rtl" align="right">
مراقبة الظروف الفيزيائية للـ Rack (الحرارة، الرطوبة) بشكل مستمر، مع تأمين فيزيائي للـ Rack نفسه (أقفال، تحكم بالوصول) لمنع أي وصول فيزيائي غير مصرح به للمعدات الحساسة.
</p>

---

<h2 dir="rtl" align="right" id="change-management">28. إدارة التغيير (Change Management Procedures)</h2>

<p dir="rtl" align="right">
عملية إدارة التغيير هي إطار عمل رسمي بيضمن إن أي تعديل على الشبكة (حتى لو بسيط) بيتم بطريقة منظّمة ومدروسة، بدل ما يحصل بشكل عشوائي وممكن يسبب أعطال غير متوقعة.
</p>

<ul dir="rtl">
<li><strong>Change Request (طلب التغيير):</strong> الخطوة الأولى — توثيق رسمي لأي تغيير مقترح قبل تنفيذه، بيوضح إيه المطلوب بالظبط وليه.</li>
<li><strong>Configuration Procedures (إجراءات التنفيذ):</strong> الخطوات الفنية التفصيلية اللازمة لتطبيق التغيير عملياً.</li>
<li><strong>Rollback Process (عملية التراجع):</strong> تذكير سريع (اتشرحت بالتفصيل في الموضوع 18 ضمن Patch Management) — خطة جاهزة للتراجع الفوري عن التغيير لو سبب مشكلة غير متوقعة.</li>
<li><strong>Potential Impact (التأثير المحتمل):</strong> تقييم مسبق لأي تأثير جانبي ممكن يحصل نتيجة التغيير، على أنظمة أو مستخدمين تانيين غير المستهدَفين مباشرة.</li>
<li><strong>Notification (الإخطار):</strong> إبلاغ كل الأطراف المتأثرة (فريق تقني، مستخدمين) بالتغيير القادم مسبقاً.</li>
<li><strong>Approval Process (عملية الموافقة):</strong> مراجعة واعتماد رسمي للتغيير من جهة مسؤولة (لجنة تغيير - CAB مثلاً) قبل التنفيذ، خصوصاً للتغييرات عالية المخاطر.</li>
<li><strong>Authorized Downtime (فترة التوقف المصرَّح بها):</strong> نافذة زمنية محددة ومتفق عليها مسبقاً يُسمح خلالها بتوقف الخدمة لتنفيذ التغيير، غالباً في أوقات قليلة الاستخدام.</li>
<li><strong>Notification of Change (الإخطار بإتمام التغيير):</strong> إبلاغ كل الأطراف بعد اكتمال التغيير فعلياً ونجاحه.</li>
<li><strong>Documentation (التوثيق):</strong> تسجيل التغيير بالكامل في السجلات الرسمية بعد التنفيذ، ليكون جزء من التاريخ الموثّق للشبكة (راجع القسم 9).</li>
</ul>

---

<h2 dir="rtl" align="right" id="cheat-sheet-23">29. جدول المراجعة السريع (Cheat Sheet)</h2>

| المفهوم / البروتوكول | الفئة | الفكرة الأساسية |
|:---:|:---:|:---:|
| SNMP | بروتوكول إدارة | استقصاء دوري لحالة الأجهزة عبر UDP 161/162 |
| SNMPv3 | بروتوكول إدارة | الإصدار الآمن الوحيد بمصادقة وتشفير حقيقيين |
| MIB / OID | SNMP | قاعدة بيانات هرمية لكل متغير يمكن الاستعلام عنه |
| Syslog | بروتوكول تسجيل | تجميع مركزي لسجلات الأحداث من كل الأجهزة |
| Syslog Severity 0-7 | Syslog | 0=Emergency (الأخطر) حتى 7=Debug (الأقل خطورة) |
| NetFlow | بروتوكول تحليل حركة | إحصائيات "مين بيتكلم مع مين" عبر Flows |
| 7-Tuple | NetFlow | المفاتيح السبعة التي تحدد الـ Flow الواحد |
| Wireshark | أداة تحليل حزم | التقاط وتحليل رسومي كامل لمحتوى الحزم |
| QoS | تحسين أداء | أولوية مختلفة لأنواع حركة مختلفة |
| IntServ / DiffServ | أنواع QoS | حجز موارد End-to-End مقابل تصنيف بعلامات |
| Processing/Queuing/Serialization/Propagation Delay | أنواع التأخير | معالجة / انتظار / تحويل لإشارة / انتقال فيزيائي |
| DSCP | تصنيف Layer 3 | 6 بت في رأس IP: Default, EF, AF, CS |
| CoS / PCP | تصنيف Layer 2 | 3 بت في إطار 802.1Q، 8 مستويات (802.1p) |
| FIFO / PQ / WFQ / CBQ | صفوف البيانات | آليات مختلفة لترتيب إرسال الحزم المنتظرة |
| HSRP / VRRP / CARP | تكرارية راوتر | بروتوكولات Virtual IP للتبديل التلقائي بين راوترات |
| NLB / Cluster | توزيع حمل | توزيع طلبات على سيرفرات متعددة تعمل كوحدة واحدة |
| DLP | سياسة | منع تسريب البيانات الحساسة خارج المؤسسة |
| BYOD / AUP / NDA | سياسات | الأجهزة الشخصية / الاستخدام المقبول / عدم الإفصاح |
| SLA / MOU / MSA | مستندات أعمال | اتفاقية خدمة / تفاهم / عقد إطاري شامل |
| Honeypot/Honeynet | تجزئة أمنية | تذكير من الموضوع 19 |
| Type I / Type II Hypervisor | افتراضية | Bare Metal مباشر مقابل فوق نظام تشغيل مضيف |
| vSwitch / vNIC / vRouter / vFirewall | مكونات افتراضية | نسخ برمجية من أجهزة الشبكة الفيزيائية |
| SDN | شبكات معرّفة برمجياً | فصل Control Plane عن Data Plane مركزياً |
| Jumbo Frame | أداء | إطار Ethernet بحمولة أكبر من 1500 بايت |
| SAN | تخزين | شبكة تخزين منفصلة عالية السعة (Block-Level) |
| NAS | تخزين | تخزين مشترك عبر LAN العادية (File-Level) |
| iSCSI | تخزين | تغليف أوامر SCSI داخل حزم IP |
| Fibre Channel / FCoE | تخزين | شبكة ضوئية متخصصة / تغليفها داخل Ethernet |
| InfiniBand | تخزين | اتصال فائق السرعة ومنخفض التأخير |
| IaaS / PaaS / SaaS | نماذج سحابية | هاردوير فقط / + منصة / + تطبيق كامل |
| Private/Public/Hybrid/Community Cloud | نشر سحابي | درجات مختلفة من الملكية والإدارة المشتركة |
| MDF / IDF | تركيب معدات | نقطة توزيع رئيسية / فرعية |
| Change Request / Rollback / CAB Approval | إدارة التغيير | عملية رسمية منظّمة لأي تعديل على الشبكة |

</div>