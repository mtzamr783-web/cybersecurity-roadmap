<div dir="rtl">

# الموضوع الحادي والعشرون: أدوات سطر الأوامر (Command-Line Tools)

## جدول المحتويات

| # | القسم الرئيسي | المواضيع الفرعية |
|:---:|:---:|:---:|
| 1 | [مقدمة عن الموضوع](#introduction) | - |
| 2 | [التعريف بالموضوع وأهميته وفوائده](#definition-importance) | - |
| 3 | [أداة التعقب Traceroute / tracert](#traceroute) | - |
| 4 | [أداة ipconfig](#ipconfig) | [الاستخدام الأساسي](#ipconfig-basic)<br>[ipconfig /all](#ipconfig-all)<br>[ipconfig /release](#ipconfig-release)<br>[ipconfig /renew](#ipconfig-renew)<br>[المعادل في Linux: أمر ip](#ip-command) |
| 5 | [أداة Ping](#ping) | [رسائل وأخطاء Ping](#ping-messages)<br>[خيارات التحكم في الباكيت](#ping-options) |
| 6 | [أداة PathPing](#pathping) | [المعادل في Linux/Unix](#pathping-linux-equivalent) |
| 7 | [أداة قياس عرض النطاق iperf](#iperf) | - |
| 8 | [أداة فحص المنافذ nmap](#nmap) | - |
| 9 | [أوامر بروتوكول ARP](#arp-commands) | [arp -a](#arp-a)<br>[arp -s](#arp-s)<br>[arp -d](#arp-d) |
| 10 | [تشخيص DNS: nslookup و dig](#dns-diagnostics) | [nslookup](#nslookup)<br>[dig](#dig) |
| 11 | [أمر hostname](#hostname) | - |
| 12 | [أمر route](#route-print) | [route print](#route-print-sub)<br>[route add/change/delete](#route-modify) |
| 13 | [أمر nbtstat](#nbtstat) | - |
| 14 | [أمر netstat](#netstat) | [-r](#netstat-r)<br>[-o](#netstat-o)<br>[-a](#netstat-a)<br>[-b](#netstat-b)<br>[-n](#netstat-n) |
| 15 | [أداة التقاط الحزم tcpdump](#tcpdump) | - |
| 16 | [أوامر Telnet](#telnet) | - |
| 17 | [أمر SSH](#ssh) | - |
| 18 | [أوامر FTP](#ftp) | - |
| 19 | [أوامر تشخيص على أجهزة سيسكو](#cisco-show-commands) | [show interface](#show-interface)<br>[show running-config](#show-config)<br>[show ip route](#show-route) |
| 20 | [جدول المراجعة السريع](#cheat-sheet-21) | - |

---

<h2 dir="rtl" align="right" id="introduction">1. مقدمة عن الموضوع</h2>

<p dir="rtl" align="right">
كل المواضيع اللي درستها لحد دلوقتي (الشبكات، البروتوكولات، الأمان، الـ WAN...) كانت بتشرح <strong>إزاي الشبكة المفروض تشتغل نظرياً</strong>. الموضوع ده مختلف تماماً — هو الجسر بين النظرية والتطبيق العملي الفعلي. مهما كانت معرفتك النظرية قوية، في لحظة معينة هتقف قدام شبكة حقيقية فيها مشكلة (جهاز مش بيوصل للإنترنت، سيرفر مش عايز يرد، اتصال بطيء بشكل غريب) ومحتاج تشخّص المشكلة دي <strong>بنفسك ومن سطر الأوامر مباشرة</strong> — من غير واجهات رسومية مساعدة.
</p>

<p dir="rtl" align="right">
الأدوات دي أحياناً بتُسمى "أدوات اكتشاف الأخطاء وتصحيحها" (Troubleshooting Tools) وأحياناً "أدوات سطر الأوامر" (Command-Line Tools) — الاسمين بيقصدوا نفس المجموعة بالظبط، لأن كل أدوات تشخيص الشبكة العملية دي بتتنفذ من الـ Command Prompt أو الـ Terminal.
</p>

---

<h2 dir="rtl" align="right" id="definition-importance">2. التعريف بالموضوع وأهميته وفوائده ولماذا نحتاجه</h2>

<p dir="rtl" align="right">
أدوات سطر الأوامر هي مجموعة برامج مدمجة أصلاً في نظام التشغيل (Windows, Linux, macOS) بتسمح لك تتفاعل مباشرة مع طبقات نموذج <strong>TCP/IP</strong> — تفحص الإعدادات، تختبر الاتصال، تتابع مسار البيانات، وتحلل أي مشكلة ممكن تكون حاصلة في أي طبقة من الطبقات.
</p>

<p dir="rtl" align="right">
<strong>ليه نحتاجها بالتحديد؟</strong>
</p>

<ul dir="rtl">
<li><strong>السرعة:</strong> غالباً أسرع بكثير من فتح واجهات رسومية متعددة عشان توصل لنفس المعلومة.</li>
<li><strong>التوفر في كل مكان:</strong> موجودة بشكل افتراضي في كل نظام تشغيل تقريباً، من غير الحاجة لتثبيت أي برنامج إضافي.</li>
<li><strong>التحكم الدقيق:</strong> بتوفر خيارات وباراميترات تفصيلية (Switches/Flags) بتسمح لك تتحكم بدقة في طريقة عمل الأداة نفسها.</li>
<li><strong>أساس أي عملية تشخيص شبكة حقيقية:</strong> أي مهندس شبكات أو محلل أمني، أول ما بيواجه مشكلة، بيرجع لنفس الأدوات دي كخط دفاع أول قبل أي حاجة تانية.</li>
<li><strong>فهم أعمق للبروتوكولات:</strong> استخدام الأدوات دي عملياً بيرسّخ فهمك النظري لطبقات TCP/IP وبروتوكولاتها (IP, ICMP, ARP, DNS...) لأنك بتشوف نتائجها بعينك مباشرة.</li>
</ul>

---

<h2 dir="rtl" align="right" id="traceroute">3. أداة التعقب (Traceroute / tracert)</h2>

<p dir="rtl" align="right">
أداة Traceroute (وبتُكتب <code>tracert</code> في Windows، و<code>traceroute</code> في Linux/macOS) بتوضح <strong>المسار الكامل خطوة بخطوة (Hop by Hop)</strong> اللي الحزمة بتاخده من جهازك وصولاً للوجهة النهائية، وبتقيس زمن الاستجابة (Latency) عند كل قفزة (Hop) على الطريق.
</p>

<h3 dir="rtl" align="right" id="traceroute-mechanism">3.1 آلية العمل</h3>

<p dir="rtl" align="right">
الأداة بتستغل حقل <strong>TTL (Time to Live)</strong> في رأس حزمة IP بطريقة ذكية جداً: بتبعت أول حزمة بقيمة TTL=1. أول راوتر يستقبلها بيقلل الـ TTL لصفر، وبيضطر يرفضها ويرد برسالة خطأ ICMP "Time Exceeded" — وده بيكشف عنوان أول راوتر في المسار. بعد كده بتبعت حزمة تانية بـ TTL=2، فتعدي أول راوتر وتوصل للراوتر الثاني، اللي هو كمان هيرفضها ويرد بنفس رسالة الخطأ — وده بيكشف عنوان الراوتر الثاني. العملية دي بتتكرر (TTL=3, 4, 5...) لحد ما الحزمة توصل فعلياً للوجهة النهائية وترد برد عادي، وبكده الأداة تكون رسمت المسار بالكامل راوتر بعد راوتر.
</p>

<div align="center"><pre><code>C:\&gt; tracert google.com

Tracing route to google.com [142.250.190.14]
over a maximum of 30 hops:

  1    1 ms    1 ms    1 ms  192.168.1.1
  2   12 ms   11 ms   10 ms  10.10.0.1
  3   15 ms   14 ms   13 ms  41.33.1.254
  4   35 ms   33 ms   34 ms  142.250.190.14

Trace complete.</code></pre></div>

<h3 dir="rtl" align="right" id="traceroute-uses">3.2 الاستخدامات العملية</h3>

<ul dir="rtl">
<li><strong>تحديد مكان المشكلة بالظبط:</strong> لو الاتصال بطيء أو منقطع، Traceroute بيوريك بالضبط عند أي قفزة (Hop) بدأت المشكلة تظهر — هل المشكلة عندك، عند مزود الخدمة (ISP)، أو في مكان بعيد تماماً عن نطاق تحكمك.</li>
<li><strong>فحص مسار حركة البيانات:</strong> مفيد لفهم إزاي البيانات بتتحرك فعلياً عبر الإنترنت أو الشبكة الداخلية، ولو المسار غير منطقي أو طويل بشكل غير متوقع.</li>
</ul>

---

<h2 dir="rtl" align="right" id="ipconfig">4. أداة ipconfig</h2>

<h3 dir="rtl" align="right" id="ipconfig-basic">4.1 الاستخدام الأساسي: إظهار إعدادات العنوان المنطقي</h3>

<p dir="rtl" align="right">
أمر <code>ipconfig</code> بيعرض إعدادات العنوان المنطقي (Logical Address) الأساسية لكل بطاقة شبكة (Network Adapter) متصلة بالجهاز — يعني عنوان IP، قناع الشبكة الفرعية (Subnet Mask)، والبوابة الافتراضية (Default Gateway) — من غير أي تفاصيل زيادة.
</p>

<div align="center"><pre><code>C:\&gt; ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:
   Connection-specific DNS Suffix  . :
   IPv4 Address. . . . . . . . . . . : 192.168.1.25
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . : 192.168.1.1</code></pre></div>

<p dir="rtl" align="right">
<strong>أهميته:</strong> أول أمر بتنفذه غالباً في أي عملية تشخيص شبكة — لو الجهاز أصلاً مالوش عنوان IP سليم أو البوابة الافتراضية غلط، مفيش فايدة تفحص أي حاجة تانية قبل ما تصحّح ده الأول.
</p>

<h3 dir="rtl" align="right" id="ipconfig-all">4.2 أمر ipconfig /all</h3>

<p dir="rtl" align="right">
نسخة موسّعة وتفصيلية جداً من الأمر الأساسي — بتعرض <strong>كل</strong> المعلومات المتعلقة بإعدادات الشبكة، مش بس الأساسيات. من أهم المعلومات الإضافية اللي بتظهر:
</p>

<ul dir="rtl">
<li>عنوان MAC الفعلي (Physical Address) لكل بطاقة شبكة.</li>
<li>عناوين سيرفرات DNS المُعدّة على الجهاز.</li>
<li>حالة تفعيل DHCP (مفعّل أو لا) وعنوان سيرفر DHCP اللي وزّع العنوان.</li>
<li>تاريخ ووقت استلام عقد الإيجار (Lease Obtained) وتاريخ انتهائه (Lease Expires) في حالة إن العنوان جاي من DHCP.</li>
<li>Host Name الخاص بالجهاز ووصف بطاقة الشبكة بالكامل.</li>
</ul>

<div align="center"><pre><code>C:\&gt; ipconfig /all

Ethernet adapter Ethernet:
   Description . . . . . . . . . . . : Realtek PCIe GbE Family Controller
   Physical Address. . . . . . . . . : 00-1A-2B-3C-4D-5E
   DHCP Enabled. . . . . . . . . . . : Yes
   IPv4 Address. . . . . . . . . . . : 192.168.1.25
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Lease Obtained. . . . . . . . . . : Monday, September 15, 2026 9:00:00 AM
   Lease Expires . . . . . . . . . . : Tuesday, September 16, 2026 9:00:00 AM
   Default Gateway . . . . . . . . . : 192.168.1.1
   DHCP Server . . . . . . . . . . . : 192.168.1.1
   DNS Servers . . . . . . . . . . . : 8.8.8.8
                                       8.8.4.4</code></pre></div>

<h3 dir="rtl" align="right" id="ipconfig-release">4.3 أمر ipconfig /release</h3>

<p dir="rtl" align="right">
بيتخلّى الجهاز عن عنوان الـ IP الحالي اللي أخده من سيرفر DHCP — يعني بيبلّغ سيرفر الـ DHCP رسمياً إن العنوان ده مش محتاجه دلوقتي، وسيرفر الـ DHCP بيحرر (Release) العنوان ده ليكون متاح لأجهزة تانية. بعد تنفيذ الأمر ده، الجهاز عملياً بيفضل <strong>من غير عنوان IP خالص</strong> لحد ما تطلب عنوان جديد (عن طريق <code>/renew</code> أو إعادة تشغيل الجهاز).
</p>

<div align="center"><pre><code>C:\&gt; ipconfig /release

Ethernet adapter Ethernet:
   Connection-specific DNS Suffix  . :
   
   IPv4 Address. . . . . . . . . . . : 0.0.0.0</code></pre></div>

<h3 dir="rtl" align="right" id="ipconfig-renew">4.4 أمر ipconfig /renew</h3>

<p dir="rtl" align="right">
بيطلب من الجهاز إنه يتواصل مع سيرفر DHCP من جديد ويطلب عنوان IP جديد (أو تجديد العنوان القديم لو لسه متاح). غالباً بيُستخدم مباشرة بعد <code>/release</code> عشان تجبر الجهاز ياخد عنوان جديد تماماً من الصفر — تقنية تشخيص كلاسيكية جداً لحل مشاكل زي: عنوان IP متضارب مع جهاز تاني، أو إعدادات شبكة قديمة عالقة، أو مشكلة في التواصل مع سيرفر DHCP.
</p>

<div align="center"><pre><code>C:\&gt; ipconfig /renew

Ethernet adapter Ethernet:
   Connection-specific DNS Suffix  . :
   IPv4 Address. . . . . . . . . . . : 192.168.1.30
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . : 192.168.1.1</code></pre></div>

<p dir="rtl" align="right">
<strong>ملاحظة مهمة:</strong> عادةً بيُستخدم الاتنين معاً بالترتيب: <code>ipconfig /release</code> ثم <code>ipconfig /renew</code> — دورة كاملة (Release ثم Renew) بتضمن إن الجهاز اخد عنوان نضيف تماماً من سيرفر DHCP، بدل ما يعتمد على أي معلومة قديمة مخزّنة محلياً.
</p>

<h3 dir="rtl" align="right" id="ip-command">4.5 المعادل في Linux: أمر ip</h3>

<p dir="rtl" align="right">
في توزيعات Linux الحديثة، أمر <code>ip</code> بقى البديل الرسمي والموصى به بدلاً من الأوامر القديمة <code>ifconfig</code> و <code>route</code> (اللي بقيا معتبرين Deprecated في كتير من التوزيعات الحديثة). الأمر ده بيغطي وظائف ipconfig كامل وjmore، وبيتفرّع لعدة أوامر فرعية حسب المطلوب:
</p>

<table>
<tr><th align="center">الأمر</th><th align="center">الوظيفة</th></tr>
<tr><td align="center"><code>ip addr</code> (أو <code>ip a</code>)</td><td align="center">عرض عناوين IP لكل واجهة شبكة — معادل <code>ipconfig</code> الأساسي</td></tr>
<tr><td align="center"><code>ip route</code></td><td align="center">عرض جدول التوجيه المحلي — معادل <code>route print</code> (الموضّح في القسم 11)</td></tr>
<tr><td align="center"><code>ip link</code></td><td align="center">عرض حالة واجهات الشبكة نفسها (Up/Down) وعنوان MAC لكل واحدة</td></tr>
</table>

<div align="center"><pre><code>user@linux:~$ ip addr

2: eth0: &lt;BROADCAST,MULTICAST,UP,LOWER_UP&gt;
    inet 192.168.1.25/24 brd 192.168.1.255 scope global eth0
    link/ether 00:1a:2b:3c:4d:5e brd ff:ff:ff:ff:ff:ff</code></pre></div>

---

<h2 dir="rtl" align="right" id="ping">5. أداة Ping</h2>

<p dir="rtl" align="right">
Ping هي أشهر وأبسط أداة لفحص الاتصال بين جهازين — بتبعت حزم <strong>ICMP Echo Request</strong> للجهاز الهدف، ولو الجهاز شغال وقادر يرد، بيرجّع حزم <strong>ICMP Echo Reply</strong>. الاسم نفسه ("Ping") مستوحى من صوت السونار في الغواصات — بتبعت نبضة وتستنى الصدى يرجع.
</p>

<div align="center"><pre><code>C:\&gt; ping 8.8.8.8

Pinging 8.8.8.8 with 32 bytes of data:
Reply from 8.8.8.8: bytes=32 time=14ms TTL=118
Reply from 8.8.8.8: bytes=32 time=13ms TTL=118
Reply from 8.8.8.8: bytes=32 time=15ms TTL=118
Reply from 8.8.8.8: bytes=32 time=14ms TTL=118

Ping statistics for 8.8.8.8:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 13ms, Maximum = 15ms, Average = 14ms</code></pre></div>

<h3 dir="rtl" align="right" id="ping-messages">5.1 رسائل وأخطاء Ping الشائعة</h3>

<table>
<tr><th align="center">الرسالة</th><th align="center">المعنى</th></tr>
<tr><td align="center"><strong>Reply from X: bytes=... time=... TTL=...</strong></td><td align="center">نجاح — الجهاز الهدف رد فعلاً، ومعاها زمن الاستجابة (Round Trip Time) وقيمة TTL المتبقية</td></tr>
<tr><td align="center"><strong>Request Timed Out</strong></td><td align="center">الطلب اتبعت لكن مفيش رد وصل خلال المهلة المحددة — غالباً الجهاز الهدف مش موجود، أو فيه جدار ناري بيمنع ICMP، أو مشكلة في المسار</td></tr>
<tr><td align="center"><strong>Destination Host Unreachable</strong></td><td align="center">الراوتر المحلي أو جهاز على المسار أعلن إنه مش عارف يوصل للهدف أصلاً — غالباً مشكلة في التوجيه (Routing) قبل ما الطلب يوصل بعيد</td></tr>
<tr><td align="center"><strong>Unknown Host</strong></td><td align="center">فشل في تحليل اسم النطاق (Domain Name) لعنوان IP — يعني في الأغلب مشكلة في DNS نفسه، مش في الاتصال بالهدف</td></tr>
<tr><td align="center"><strong>TTL Expired in Transit</strong></td><td align="center">الحزمة دارت في حلقة (Loop) أو المسار طويل جداً وخلصت الـ TTL بتاعتها قبل ما توصل للهدف</td></tr>
</table>

<h3 dir="rtl" align="right" id="ping-options">5.2 خيارات التحكم في الباكيت مع Ping</h3>

<table>
<tr><th align="center">الخيار</th><th align="center">الوظيفة</th></tr>
<tr><td align="center"><code>-t</code></td><td align="center">استمرار إرسال طلبات Ping بلا توقف حتى يتم إيقافها يدوياً (Ctrl+C) — مفيد لمراقبة استقرار اتصال معين لفترة طويلة</td></tr>
<tr><td align="center"><code>-n [عدد]</code></td><td align="center">تحديد عدد مرات إرسال الطلب (الافتراضي في Windows هو 4 مرات فقط)</td></tr>
<tr><td align="center"><code>-l [حجم]</code></td><td align="center">تحديد حجم البيانات (Payload) بالبايت في كل حزمة — مفيد لاختبار كيف تتصرف الشبكة مع حزم أكبر من العادي</td></tr>
<tr><td align="center"><code>-f</code></td><td align="center">إرسال الحزمة بعلامة "Don't Fragment" مفعّلة، لمنع تجزيء الحزمة أثناء الطريق — مفيد لاختبار أكبر حجم حزمة (MTU) يقدر المسار يستوعبه من غير تجزيء</td></tr>
<tr><td align="center"><code>-i [TTL]</code></td><td align="center">تحديد قيمة TTL يدوياً بدلاً من القيمة الافتراضية</td></tr>
<tr><td align="center"><code>-a</code></td><td align="center">تحليل عنوان IP الهدف عكسياً لمعرفة اسم المضيف (Hostname) المرتبط به</td></tr>
<tr><td align="center"><code>-4</code> / <code>-6</code></td><td align="center">إجبار الأمر على استخدام IPv4 أو IPv6 صراحةً بدلاً من الاختيار التلقائي</td></tr>
</table>

---

<h2 dir="rtl" align="right" id="pathping">6. أداة PathPing (التعقب وكشف الأخطاء معاً)</h2>

<p dir="rtl" align="right">
PathPing هي أداة هجينة بتجمع بين فكرة <strong>Traceroute</strong> (رسم المسار الكامل خطوة بخطوة) وفكرة <strong>Ping</strong> (قياس الأداء وفقدان الحزم) في أداة واحدة، وبتوفرها Microsoft فقط في Windows. الأداة بترسل عدد كبير من طلبات Ping لكل قفزة (Hop) على المسار على مدار فترة زمنية (100 طلب لكل Hop بشكل افتراضي)، وبكده بتقدر تحسب <strong>نسبة فقدان الحزم (Packet Loss %) عند كل قفزة على حدة</strong> — مش بس زمن الاستجابة زي Traceroute العادي.
</p>

<div align="center"><pre><code>C:\&gt; pathping google.com

Tracing route to google.com over a maximum of 30 hops:
  0  MyPC [192.168.1.25]
  1  192.168.1.1
  2  10.10.0.1
  3  142.250.190.14

Computing statistics for 100 seconds...
            Source to Here   This Node/Link
Hop  RTT    Lost/Sent = Pct  Lost/Sent = Pct  Address
  0                                           MyPC [192.168.1.25]
                                0/ 100 =  0%   |
  1    1ms     0/ 100 =  0%    0/ 100 =  0%   192.168.1.1
                                2/ 100 =  2%   |
  2   12ms     2/ 100 =  2%    2/ 100 =  2%   10.10.0.1
                                0/ 100 =  0%   |
  3   35ms     2/ 100 =  2%    0/ 100 =  0%   142.250.190.14</code></pre></div>

<p dir="rtl" align="right">
<strong>الفايدة الأساسية:</strong> Traceroute العادي بيوريك المسار وزمن الاستجابة بس، لكن PathPing بيوريك بالتحديد <strong>أي قفزة (Hop) هي اللي بتسبب فقدان الحزم أو التأخير الحقيقي</strong> — وده بيساعدك تفرّق بين مشكلة في راوتر معين على المسار، ومشكلة في الوجهة النهائية نفسها.
</p>

<h3 dir="rtl" align="right" id="pathping-linux-equivalent">6.1 المعادل في Linux/Unix</h3>

<p dir="rtl" align="right">
أداة PathPing حصرية على Windows، لكن نفس الفكرة (دمج Traceroute مع إحصائيات فقدان الحزم) متوفرة في Linux/Unix عن طريق أداة <code>mtr</code> (My Traceroute) — بتوفر نفس المعلومات (المسار + نسبة الفقد + زمن الاستجابة لكل قفزة) لكن بواجهة تفاعلية بتتحدث لحظياً أثناء التشغيل، بدل ما تستني فترة زمنية محددة زي PathPing.
</p>

---

<h2 dir="rtl" align="right" id="iperf">7. أداة قياس عرض النطاق الترددي (iperf)</h2>

<p dir="rtl" align="right">
كل الأدوات اللي اتشرحت لحد دلوقتي بتجاوب على سؤال "هل فيه اتصال؟" أو "فين المشكلة؟"، لكن <code>iperf</code> (واصدارها الأحدث <code>iperf3</code>) بتجاوب على سؤال مختلف تماماً: <strong>"إيه السرعة الفعلية الحقيقية بين نقطتين؟"</strong> — وهي الأداة العملية المرجعية لقياس مفاهيم <strong>Bandwidth مقابل Throughput</strong> اللي اتشرحت نظرياً في الموضوع 20 (قسم مقاييس الأداء).
</p>

<p dir="rtl" align="right">
<strong>آلية العمل:</strong> الأداة بتحتاج جهازين — واحد بيشتغل بدور <strong>Server</strong> (مستقبِل، في وضع انتظار)، والتاني بدور <strong>Client</strong> (بيبدأ الاختبار الفعلي ويبعت بيانات تجريبية للسيرفر لفترة زمنية معينة). بعد انتهاء الاختبار، الأداة بتحسب وتعرض السرعة الفعلية المُحققة (Throughput) بين الجهازين.
</p>

<div align="center"><pre><code>REM على الجهاز الأول (Server):
$ iperf3 -s

Server listening on 5201

REM على الجهاز الثاني (Client):
$ iperf3 -c 192.168.1.25

Connecting to host 192.168.1.25, port 5201
[ ID] Interval           Transfer     Bitrate
[  5]   0.00-10.00  sec   1.10 GBytes   943 Mbits/sec</code></pre></div>

<p dir="rtl" align="right">
<strong>الاستخدام العملي:</strong> مفيد جداً لتحديد هل مشكلة "الاتصال البطيء" اللي بيشتكي منها المستخدم فعلاً مشكلة حقيقية في السرعة (يعني Throughput منخفض فعلاً عن المتوقع)، أو إن السرعة الفعلية سليمة والمشكلة في مكان تاني (تطبيق معين، DNS، إلخ) — بدل ما تعتمد على "شكل" الاتصال بس من أدوات زي Ping اللي بتقيس زمن الاستجابة (Latency) مش السرعة الفعلية (Throughput).
</p>

---

<h2 dir="rtl" align="right" id="nmap">8. أداة فحص المنافذ (nmap)</h2>

<p dir="rtl" align="right">
<code>nmap</code> (Network Mapper) هي الأداة المرجعية القياسية لتنفيذ <strong>Port Scanning</strong> (الموضّح كمفهوم نظري في الموضوع 18) عملياً من سطر الأوامر — بتفحص جهاز أو نطاق كامل من عناوين IP وترجّع لك حالة كل منفذ (Open/Closed/Filtered) والخدمة الشغالة عليه، وأحياناً حتى نوع نظام التشغيل نفسه.
</p>

<div align="center"><pre><code>$ nmap 192.168.1.10

Starting Nmap
Nmap scan report for 192.168.1.10
Host is up (0.0012s latency).

PORT     STATE    SERVICE
22/tcp   open     ssh
80/tcp   open     http
443/tcp  open     https
3389/tcp closed   ms-wbt-server</code></pre></div>

<p dir="rtl" align="right">
<strong>أهم أنماط الفحص الشائعة:</strong>
</p>

<table>
<tr><th align="center">الخيار</th><th align="center">الوظيفة</th></tr>
<tr><td align="center"><code>-sS</code></td><td align="center">فحص SYN (Half-Open/Stealth Scan) — أشهر وأسرع نمط فحص، بدون إكمال الـ Handshake بالكامل</td></tr>
<tr><td align="center"><code>-sT</code></td><td align="center">فحص TCP Connect (Full Open Scan) — يكمّل الـ Three-Way Handshake بالكامل مع كل منفذ</td></tr>
<tr><td align="center"><code>-sV</code></td><td align="center">اكتشاف إصدار الخدمة الشغالة على كل منفذ مفتوح، مش بس رقم المنفذ</td></tr>
<tr><td align="center"><code>-O</code></td><td align="center">محاولة تحديد نظام التشغيل بتاع الجهاز الهدف (OS Fingerprinting)</td></tr>
<tr><td align="center"><code>-p [نطاق]</code></td><td align="center">تحديد منفذ أو نطاق منافذ معين للفحص، بدل الفحص الافتراضي الشامل</td></tr>
</table>

<p dir="rtl" align="right">
<strong>الاستخدام المزدوج:</strong> nmap أداة محايدة تماماً — ممكن تُستخدم من فريق الأمن (Blue Team) لمراجعة أي منافذ مفتوحة على شبكته من غير داعٍ (تقليل سطح الهجوم — راجع الموضوع 18)، وممكن تُستخدم من مهاجم (Red Team/Black Hat) في مرحلة Reconnaissance بالظبط زي ما اتشرح في الموضوع 18، وده اللي بيخليها من أهم الأدوات المزدوجة الاستخدام في عالم الشبكات والأمن.
</p>

---

<h2 dir="rtl" align="right" id="arp-commands">9. الأوامر والأدوات الخاصة ببروتوكول ARP</h2>

<p dir="rtl" align="right">
بروتوكول ARP (Address Resolution Protocol) مسؤول عن ربط عنوان IP بعنوان MAC داخل الشبكة المحلية — وأمر <code>arp</code> بيسمحلك تتفاعل مباشرة مع <strong>جدول ARP المحلي (ARP Cache/Table)</strong> المخزّن على جهازك، اللي فيه كل الربط بين عناوين IP وMAC للأجهزة اللي جهازك تواصل معاها مؤخراً في الشبكة المحلية.
</p>

<h3 dir="rtl" align="right" id="arp-a">9.1 أمر arp -a</h3>

<p dir="rtl" align="right">
بيعرض <strong>محتوى جدول ARP الحالي بالكامل</strong> — كل عناوين IP المعروفة محلياً مربوطة بعناوين MAC المقابلة لها، ونوع الإدخال (Dynamic لو اكتشفه الجهاز تلقائياً، أو Static لو تم إدخاله يدوياً).
</p>

<div align="center"><pre><code>C:\&gt; arp -a

Interface: 192.168.1.25 --- 0x5
  Internet Address      Physical Address      Type
  192.168.1.1            00-11-22-33-44-55     dynamic
  192.168.1.10           aa-bb-cc-dd-ee-ff     dynamic</code></pre></div>

<p dir="rtl" align="right">
<strong>الاستخدام التشخيصي:</strong> مفيد جداً لاكتشاف حالات تزوير ARP (ARP Spoofing — الموضّح بالتفصيل في الموضوع 18) — لو لاحظت إن عنوان MAC لجهاز معروف (زي البوابة الافتراضية) اتغيّر بشكل غير متوقع في الجدول، ده علامة تحذيرية قوية على هجوم محتمل.
</p>

<h3 dir="rtl" align="right" id="arp-s">9.2 أمر arp -s</h3>

<p dir="rtl" align="right">
بيسمحلك تضيف إدخال <strong>ثابت (Static)</strong> يدوياً لجدول ARP، بربط عنوان IP معين بعنوان MAC معين بشكل دائم (مش هيتحذف تلقائياً زي الإدخالات الديناميكية العادية). ده بيستخدم أحياناً كطبقة حماية إضافية ضد ARP Spoofing لأجهزة حرجة جداً (زي البوابة الافتراضية) — بربط عنوانها بعنوان MAC ثابت يدوياً، بحيث أي محاولة تزوير بعنوان MAC مختلف تُرفض تلقائياً.
</p>

<div align="center"><pre><code>C:\&gt; arp -s 192.168.1.1 00-11-22-33-44-55</code></pre></div>

<h3 dir="rtl" align="right" id="arp-d">9.3 أمر arp -d</h3>

<p dir="rtl" align="right">
بيمسح إدخال معين (أو الجدول بالكامل لو استُخدم بدون تحديد عنوان) من جدول ARP. مفيد جداً في التشخيص لو الجدول فيه معلومة قديمة أو خاطئة (زي عنوان MAC قديم لجهاز تم تغييره) وعايز تجبر الجهاز يعمل استعلام ARP جديد من الصفر.
</p>

<div align="center"><pre><code>C:\&gt; arp -d 192.168.1.10

REM لمسح الجدول بالكامل:
C:\&gt; arp -d *</code></pre></div>

---

<h2 dir="rtl" align="right" id="dns-diagnostics">10. تشخيص DNS: nslookup و dig</h2>

<h3 dir="rtl" align="right" id="nslookup">10.1 أمر nslookup</h3>

<p dir="rtl" align="right">
<code>nslookup</code> (Name Server Lookup) هي أداة أساسية لتشخيص مشاكل <strong>DNS</strong> — بتسمحلك تستفسر مباشرة عن سجلات DNS لاسم نطاق معين (بتحوّله لعنوان IP)، أو العكس (تحويل عنوان IP لاسم نطاق - Reverse Lookup)، وبتقدر كمان تحدد أي سيرفر DNS معين تستفسر منه بدل الاعتماد على السيرفر الافتراضي المُعد على جهازك. متوفرة في Windows وLinux معاً.
</p>

<div align="center"><pre><code>C:\&gt; nslookup google.com

Server:  UnKnown
Address:  192.168.1.1

Non-authoritative answer:
Name:    google.com
Addresses:  142.250.190.14</code></pre></div>

<p dir="rtl" align="right">
<strong>الاستخدام التشخيصي:</strong> لو موقع معين مش بيفتح، nslookup بيساعدك تحدد فوراً هل المشكلة في <strong>تحليل الاسم (DNS Resolution)</strong> نفسه (يعني اسم النطاق مش بيتحول لعنوان IP أصلاً) أو إن المشكلة في مكان تاني بعد ما الاسم اتحل بنجاح (يعني عندك عنوان IP صحيح لكن مفيش استجابة منه).
</p>

<h3 dir="rtl" align="right" id="dig">10.2 أمر dig</h3>

<p dir="rtl" align="right">
<code>dig</code> (Domain Information Groper) هو الأداة المكافئة لـ nslookup لكنها الأشهر والمفضّلة في بيئات Linux/Unix — وبتوفر تفاصيل أعمق وأدق بكتير عن استعلامات DNS في مخرج واحد شامل: نوع السجل بالتحديد (A, MX, NS, TXT...)، مدة الصلاحية (TTL) الخاصة بالسجل نفسه، وحالة الاستعلام (Status) بشكل واضح.
</p>

<div align="center"><pre><code>$ dig google.com

;; QUESTION SECTION:
;google.com.                     IN      A

;; ANSWER SECTION:
google.com.               259    IN      A       142.250.190.14

;; Query time: 14 msec
;; SERVER: 192.168.1.1#53(192.168.1.1)
;; WHEN: Tue Sep 15 10:00:00 2026</code></pre></div>

<p dir="rtl" align="right">
<strong>الفرق العملي عن nslookup:</strong> dig بيدّي معلومة أشمل وأدق في استعلام واحد (زي وقت الاستعلام الفعلي بالمللي ثانية، وTTL السجل نفسه)، وبيقدر تحدد بيه نوع السجل المطلوب بسهولة أكبر (مثلاً <code>dig google.com MX</code> لسجلات البريد بس)، وده اللي خلاه الأداة المفضّلة لمحترفي الشبكات في بيئات Linux، حتى لو nslookup لسه متاح ومستخدم برضو.
</p>

---

<h2 dir="rtl" align="right" id="hostname">11. أمر hostname</h2>

<p dir="rtl" align="right">
أبسط أمر في الموضوع كله — بيطبع <strong>اسم الجهاز (Host Name)</strong> بتاع الكمبيوتر الحالي بس، من غير أي معلومات إضافية. بسيط جداً لكنه مفيد سريعاً في السكربتات (Scripts) أو لما تحتاج تتأكد بسرعة من اسم الجهاز اللي شغال عليه دلوقتي، خصوصاً لو بتشتغل عن بعد على أكتر من جهاز في نفس الوقت.
</p>

<div align="center"><pre><code>C:\&gt; hostname

DESKTOP-MOTAZ01</code></pre></div>

---

<h2 dir="rtl" align="right" id="route-print">12. أمر route</h2>

<h3 dir="rtl" align="right" id="route-print-sub">12.1 عرض جدول التوجيه: route print</h3>

<p dir="rtl" align="right">
بيعرض <strong>جدول التوجيه المحلي (Routing Table)</strong> بتاع جهازك — يعني إزاي الجهاز نفسه (مش الراوتر) بيقرر يوجّه حركة البيانات لأي وجهة، وبأي بوابة، وعن طريق أي واجهة شبكة (Interface).
</p>

<div align="center"><pre><code>C:\&gt; route print

===========================================================================
Interface List
 12...00 1a 2b 3c 4d 5e ......Realtek PCIe GbE Family Controller
===========================================================================
IPv4 Route Table
===========================================================================
Active Routes:
Network Destination        Netmask          Gateway       Interface  Metric
          0.0.0.0          0.0.0.0       192.168.1.1    192.168.1.25     25
        192.168.1.0    255.255.255.0         On-link    192.168.1.25    281
===========================================================================</code></pre></div>

<p dir="rtl" align="right">
<strong>أهم عمود:</strong> السطر اللي فيه Network Destination = <code>0.0.0.0</code> هو <strong>المسار الافتراضي (Default Route)</strong> — أي وجهة الجهاز ملوش مسار محدد ليها في الجدول، بتُوجَّه تلقائياً للبوابة المذكورة في هذا السطر (غالباً البوابة الافتراضية للشبكة).
</p>

<p dir="rtl" align="right">
<strong>الاستخدام التشخيصي:</strong> مفيد جداً لو الجهاز عنده أكتر من واجهة شبكة (زي Wi-Fi وEthernet في نفس الوقت، أو اتصال VPN شغال) وحاصل تعارض أو غموض في إزاي البيانات المفروض تتوجّه — جدول التوجيه بيوضح الأولويات (Metric) بين المسارات المختلفة المتاحة.
</p>

<h3 dir="rtl" align="right" id="route-modify">12.2 تعديل جدول التوجيه: route add / change / delete</h3>

<p dir="rtl" align="right">
أمر <code>route</code> مش بس بيعرض الجدول — بيقدر كمان <strong>يعدّل عليه مباشرة</strong> ويضيف مسارات ثابتة (Static Routes) يدوياً على مستوى الجهاز نفسه، وده مفيد جداً في حالات خاصة زي جهاز عنده أكتر من واجهة شبكة ومحتاج يوجّه نوع معين من الحركة عبر مسار مختلف عن المسار الافتراضي:
</p>

<table>
<tr><th align="center">الأمر</th><th align="center">الوظيفة</th></tr>
<tr><td align="center"><code>route add [شبكة] mask [قناع] [بوابة]</code></td><td align="center">إضافة مسار ثابت جديد يوجّه حركة شبكة معينة عبر بوابة محددة</td></tr>
<tr><td align="center"><code>route change [شبكة] mask [قناع] [بوابة جديدة]</code></td><td align="center">تعديل بوابة مسار موجود فعلاً بدون حذفه وإعادة إضافته من الصفر</td></tr>
<tr><td align="center"><code>route delete [شبكة]</code></td><td align="center">حذف مسار ثابت موجود بالكامل من الجدول</td></tr>
</table>

<div align="center"><pre><code>C:\&gt; route add 10.0.0.0 mask 255.0.0.0 192.168.1.254

C:\&gt; route delete 10.0.0.0</code></pre></div>

<p dir="rtl" align="right">
<strong>ملاحظة مهمة:</strong> المسارات المُضافة بالأمر ده بشكل افتراضي بتكون <strong>مؤقتة</strong> وبتُمسح تلقائياً بعد إعادة تشغيل الجهاز، إلا لو استخدمت خيار <code>-p</code> (Persistent) عشان تضمن إن المسار يفضل محفوظ حتى بعد إعادة التشغيل.
</p>

---

<h2 dir="rtl" align="right" id="nbtstat">13. أمر nbtstat</h2>

<p dir="rtl" align="right">
<code>nbtstat</code> (NetBIOS over TCP/IP Statistics) أداة متخصصة في تشخيص مشاكل بروتوكول <strong>NetBIOS</strong> — بروتوكول قديم بيُستخدم في شبكات Windows لتحليل أسماء الأجهزة (NetBIOS Names) وربطها بعناوين IP، بشكل مشابه لفكرة DNS لكن على مستوى الشبكة المحلية فقط وبطريقة أقدم بكتير.
</p>

<div align="center"><pre><code>C:\&gt; nbtstat -n

Local Area Connection:
Node IpAddress: [192.168.1.25] Scope Id: []

       NetBIOS Local Name Table

       Name               Type         Status
    ---------------------------------------------
    DESKTOP-MOTAZ01 &lt;00&gt;  UNIQUE      Registered
    WORKGROUP       &lt;00&gt;  GROUP       Registered</code></pre></div>

<p dir="rtl" align="right">
<strong>الاستخدام حالياً:</strong> بروتوكول NetBIOS بقى قليل الاستخدام جداً في الشبكات الحديثة (اللي بتعتمد على DNS بالكامل)، لكن لسه موجود في بيئات Windows القديمة أو شبكات المكاتب الصغيرة (Workgroups)، فيفيد لتشخيص مشاكل مشاركة الملفات والطابعات في البيئات دي.
</p>

---

<h2 dir="rtl" align="right" id="netstat">14. أمر netstat</h2>

<p dir="rtl" align="right">
<code>netstat</code> (Network Statistics) من أقوى وأشمل أدوات التشخيص — بيعرض <strong>كل الاتصالات الشبكية النشطة</strong> على الجهاز حالياً، وإحصائيات شاملة عن البروتوكولات، ومعلومات تفصيلية جداً حسب الخيار (Switch) المستخدم:
</p>

<table>
<tr><th align="center">الخيار</th><th align="center">الوظيفة</th></tr>
<tr><td align="center" id="netstat-r"><code>-r</code></td><td align="center">عرض جدول التوجيه (Routing Table) — نفس المعلومة اللي بيعرضها <code>route print</code> بالظبط، لكن من خلال netstat.</td></tr>
<tr><td align="center" id="netstat-o"><code>-o</code></td><td align="center">عرض رقم العملية (PID – Process ID) المسؤولة عن كل اتصال — مفيد جداً لمعرفة أي برنامج بالتحديد بيفتح اتصال معين (خصوصاً مفيد لتحديد برنامج خبيث بيتواصل مع جهة خارجية بدون علمك).</td></tr>
<tr><td align="center" id="netstat-a"><code>-a</code></td><td align="center">عرض كل الاتصالات النشطة وكل المنافذ (Ports) في وضع الاستماع (Listening) على الجهاز، سواء TCP أو UDP.</td></tr>
<tr><td align="center" id="netstat-b"><code>-b</code></td><td align="center">عرض اسم البرنامج التنفيذي (.exe) نفسه المسؤول عن كل اتصال، مش بس رقم الـ PID — بيدّي معلومة أوضح ومباشرة أكتر من <code>-o</code>.</td></tr>
<tr><td align="center" id="netstat-n"><code>-n</code></td><td align="center">عرض العناوين وأرقام المنافذ بصيغتها الرقمية مباشرة (Numerical)، من غير محاولة تحليلها لأسماء (Hostnames) — بيخلي تنفيذ الأمر أسرع بكتير لأنه مش بيعمل استعلامات DNS إضافية.</td></tr>
</table>

<div align="center"><pre><code>C:\&gt; netstat -ano

  Proto  Local Address          Foreign Address        State           PID
  TCP    192.168.1.25:52344     142.250.190.14:443     ESTABLISHED     4521
  TCP    0.0.0.0:135            0.0.0.0:0              LISTENING       912
  UDP    192.168.1.25:5353      *:*                                    3020</code></pre></div>

<p dir="rtl" align="right">
<strong>الاستخدام التشخيصي والأمني:</strong> من أهم أدوات الفحص الأمني الأولي على أي جهاز — بتقدر تكتشف بيها اتصالات غريبة أو غير متوقعة لعناوين IP خارجية غير معروفة، وبربطها بـ <code>-o</code> أو <code>-b</code> تقدر تحدد فوراً أي برنامج بالتحديد هو المسؤول عن الاتصال ده، وده بيساعد جداً في اكتشاف برمجيات خبيثة زي الـ Backdoor أو الـ Trojan (الموضّحين في الموضوع 18) بتحاول تتواصل مع سيرفر تحكم خارجي.
</p>

---

<h2 dir="rtl" align="right" id="tcpdump">15. أداة التقاط الحزم (tcpdump)</h2>

<p dir="rtl" align="right">
<code>tcpdump</code> هي أداة التقاط حزم (Packet Capture) من سطر الأوامر في Linux/Unix — ببساطة، هي <strong>النسخة النصية من Wireshark</strong> (اللي هو البرنامج الرسومي الأشهر لالتقاط وتحليل حزم البيانات المارة عبر الشبكة — راجع مفهوم Packet Sniffing في الموضوع 18). بتلتقط الحزم المارة على واجهة شبكة معينة لحظياً وبتعرض تفاصيلها في الترمينال مباشرة.
</p>

<div align="center"><pre><code>$ sudo tcpdump -i eth0

12:00:01.123456 IP 192.168.1.25.52344 &gt; 142.250.190.14.443: Flags [S], seq 123456789
12:00:01.135678 IP 142.250.190.14.443 &gt; 192.168.1.25.52344: Flags [S.], seq 987654321
12:00:01.135900 IP 192.168.1.25.52344 &gt; 142.250.190.14.443: Flags [.], ack 987654322</code></pre></div>

<p dir="rtl" align="right">
<strong>أهم الخيارات الشائعة:</strong>
</p>

<table>
<tr><th align="center">الخيار</th><th align="center">الوظيفة</th></tr>
<tr><td align="center"><code>-i [واجهة]</code></td><td align="center">تحديد واجهة الشبكة المطلوب الالتقاط منها (زي eth0)</td></tr>
<tr><td align="center"><code>-w [ملف]</code></td><td align="center">حفظ الحزم الملتقطة في ملف (بصيغة .pcap) لتحليلها لاحقاً، حتى في Wireshark نفسه</td></tr>
<tr><td align="center"><code>host [عنوان]</code></td><td align="center">فلترة الالتقاط ليشمل حركة جهاز معين بس، بدل كل الحركة المارة على الواجهة</td></tr>
<tr><td align="center"><code>port [رقم]</code></td><td align="center">فلترة الالتقاط ليشمل منفذ معين بس (زي <code>port 80</code> لحركة HTTP بس)</td></tr>
</table>

<p dir="rtl" align="right">
<strong>الأهمية:</strong> بعكس netstat اللي بيوريك <strong>هل</strong> فيه اتصال وإيه حالته، tcpdump بيوريك <strong>محتوى الحزم نفسها</strong> وهي عابرة فعلياً عبر الشبكة — أداة أساسية جداً في التحليل الأمني العميق واكتشاف الأنشطة المشبوهة على مستوى البروتوكول مباشرة.
</p>

---

<h2 dir="rtl" align="right" id="telnet">16. أوامر Telnet</h2>

<p dir="rtl" align="right">
Telnet هو بروتوكول وأداة قديمة جداً بتسمحلك تفتح جلسة اتصال نصية (Text-based Session) عن بعد مع جهاز أو خدمة تانية عبر الشبكة، وبتشتغل غالباً على منفذ 23 بشكل افتراضي.
</p>

<div align="center"><pre><code>C:\&gt; telnet 192.168.1.10 23</code></pre></div>

<p dir="rtl" align="right">
<strong>الاستخدام كأداة تشخيص (مش كأداة إدارة عن بعد):</strong> رغم إن Telnet بقى غير آمن تماماً كأداة إدارة عن بعد (لأنه بينقل كل البيانات بما فيها كلمات المرور <strong>كنص واضح غير مشفّر</strong> — نفس فكرة PAP الموضّحة في الموضوع 20)، لسه بيُستخدم بشكل شائع جداً في التشخيص كأداة <strong>لفحص هل منفذ معين مفتوح وبيرد فعلاً</strong> على جهاز أو سيرفر بعيد. لو الأمر قدر يفتح الاتصال، ده معناه المنفذ مفتوح والخدمة شغالة ورادة؛ لو فشل الاتصال، فده يدل على إن المنفذ مقفول، أو الخدمة متوقفة، أو فيه جدار ناري بيمنع الوصول.
</p>

---

<h2 dir="rtl" align="right" id="ssh">17. أمر SSH</h2>

<p dir="rtl" align="right">
<strong>SSH (Secure Shell)</strong> هو البديل الآمن الحديث لـ Telnet بالكامل — بيوفر نفس فكرة فتح جلسة تحكم عن بعد (Remote Shell)، لكن مع <strong>تشفير كامل</strong> لكل حركة البيانات المتبادلة بما فيها بيانات الدخول، وده بيمنع أي هجوم Packet Sniffing من كشف كلمة المرور أو محتوى الجلسة زي ما بيحصل مع Telnet.
</p>

<div align="center"><pre><code>$ ssh motaz@192.168.1.10

motaz@192.168.1.10's password: ********
Welcome to Ubuntu 24.04 LTS
motaz@server:~$ </code></pre></div>

<p dir="rtl" align="right">
<strong>ليه SSH بقى المعيار القياسي حالياً:</strong> بيشتغل افتراضياً على <strong>Port 22</strong>، وبيدعم كمان طرق مصادقة أقوى من كلمة المرور العادية زي <strong>المصادقة بالمفاتيح (Key-based Authentication)</strong> — زوج من المفاتيح (عام وخاص) بيسمح بتسجيل دخول آمن جداً من غير الحاجة لكتابة كلمة مرور خالص، وبيمنع تماماً هجمات Brute Force على كلمة المرور (الموضّحة في الموضوع 18). أي مؤسسة أو مهندس شبكات حالياً بيعتمد على SSH بشكل كامل بديلاً عن Telnet لأي إدارة فعلية عن بعد لأجهزة الشبكة والسيرفرات.
</p>

---

<h2 dir="rtl" align="right" id="ftp">18. أوامر FTP</h2>

<p dir="rtl" align="right">
FTP (File Transfer Protocol) بروتوكول وأداة سطر أوامر مخصصة لنقل الملفات بين جهازك وسيرفر بعيد. بيشتغل على منفذين أساسيين: <strong>Port 21</strong> للتحكم (Control — إرسال الأوامر نفسها) و <strong>Port 20</strong> لنقل البيانات الفعلية (Data).
</p>

<div align="center"><pre><code>C:\&gt; ftp ftp.example.com

Connected to ftp.example.com.
User (ftp.example.com:(none)): motaz
Password: ********
230 Login successful.
ftp&gt; </code></pre></div>

<p dir="rtl" align="right">
<strong>أهم الأوامر الفرعية داخل جلسة FTP:</strong>
</p>

<table>
<tr><th align="center">الأمر</th><th align="center">الوظيفة</th></tr>
<tr><td align="center"><code>open</code></td><td align="center">فتح اتصال بسيرفر FTP محدد</td></tr>
<tr><td align="center"><code>ls</code> / <code>dir</code></td><td align="center">عرض قائمة الملفات والمجلدات في الموقع الحالي على السيرفر البعيد</td></tr>
<tr><td align="center"><code>get [ملف]</code></td><td align="center">تنزيل ملف واحد من السيرفر البعيد للجهاز المحلي</td></tr>
<tr><td align="center"><code>put [ملف]</code></td><td align="center">رفع ملف واحد من الجهاز المحلي للسيرفر البعيد</td></tr>
<tr><td align="center"><code>mget</code> / <code>mput</code></td><td align="center">تنزيل/رفع عدة ملفات دفعة واحدة</td></tr>
<tr><td align="center"><code>close</code></td><td align="center">إغلاق الاتصال الحالي بالسيرفر مع بقاء برنامج FTP نفسه شغال</td></tr>
<tr><td align="center"><code>bye</code> / <code>quit</code></td><td align="center">إغلاق الاتصال والخروج من برنامج FTP بالكامل</td></tr>
</table>

<p dir="rtl" align="right">
<strong>ملاحظة أمنية مهمة:</strong> بروتوكول FTP التقليدي بينقل بيانات الدخول (اسم المستخدم وكلمة المرور) والملفات نفسها <strong>بدون أي تشفير</strong> — يعني معرّض بالكامل لهجوم Packet Sniffing (الموضّح في الموضوع 18). البدائل الآمنة الحديثة هي <strong>SFTP</strong> (SSH File Transfer Protocol، بيشتغل فوق SSH المشفّر الموضّح في القسم 16) أو <strong>FTPS</strong> (FTP over SSL/TLS).
</p>

---

<h2 dir="rtl" align="right" id="cisco-show-commands">19. أوامر تشخيص على أجهزة سيسكو (show commands)</h2>

<p dir="rtl" align="right">
كل الأدوات اللي اتشرحت لحد دلوقتي بتتنفذ من <strong>جهاز المستخدم النهائي</strong> (كمبيوتر أو سيرفر) للتشخيص من زاويته. لكن أحياناً المشكلة لازم تتشخّص من <strong>داخل جهاز الشبكة نفسه</strong> (راوتر أو سويتش سيسكو)، وده بيتم عن طريق أوامر <code>show</code> المتخصصة اللي بتشتغل من داخل واجهة سطر أوامر سيسكو (Cisco IOS CLI) بعد تسجيل الدخول للجهاز (غالباً عبر SSH — راجع القسم 16، أو Console Cable مباشرة).
</p>

<h3 dir="rtl" align="right" id="show-interface">19.1 أمر show interface</h3>

<p dir="rtl" align="right">
بيعرض حالة كل واجهة (Interface) على الراوتر أو السويتش بالتفصيل — هل الواجهة شغالة (Up/Up) أو متعطّلة، سرعة ونمط الاتصال (Speed/Duplex)، وإحصائيات حركة مرور مهمة زي عدد الحزم المُرسلة والمستقبلة وعدد الأخطاء (Errors) والتصادمات (Collisions) اللي حصلت على الواجهة دي.
</p>

<div align="center"><pre><code>Router# show interface GigabitEthernet0/1

GigabitEthernet0/1 is up, line protocol is up
  Hardware is GigabitEthernet, address is 001a.2b3c.4d5e
  Full-duplex, 1000Mb/s
  5 minute input rate 1200 bits/sec
  0 input errors, 0 CRC, 0 frame, 0 overrun</code></pre></div>

<h3 dir="rtl" align="right" id="show-config">19.2 أمر show running-config</h3>

<p dir="rtl" align="right">
بيعرض <strong>الإعدادات الفعلية الشغالة حالياً</strong> على الجهاز (Running Configuration) — كل القواعد والإعدادات اللي مُطبَّقة عليه دلوقتي، من عناوين الواجهات لحد قواعد ACL وبروتوكولات التوجيه المُفعّلة. مهم جداً التنويه إن الإعدادات دي مخزّنة في الذاكرة العشوائية (RAM) بس، وممكن تتفقد لو الجهاز أُعيد تشغيله من غير حفظها في ملف الإعدادات الدائم (Startup Configuration).
</p>

<h3 dir="rtl" align="right" id="show-route">19.3 أمر show ip route</h3>

<p dir="rtl" align="right">
بيعرض <strong>جدول التوجيه (Routing Table)</strong> الخاص بالراوتر نفسه — نفس فكرة <code>route print</code> (القسم 11) بالظبط، لكن من منظور جهاز الشبكة (الراوتر) نفسه، مش من منظور جهاز المستخدم النهائي. بيوضح كل المسارات المعروفة للراوتر (سواء متعلمة تلقائياً عبر بروتوكولات توجيه ديناميكية أو مُعدّة يدوياً كمسارات ثابتة - Static Routes) والواجهة المستخدمة للوصول لكل مسار.
</p>

<div align="center"><pre><code>Router# show ip route

Gateway of last resort is 41.33.1.1 to network 0.0.0.0

C    192.168.1.0/24 is directly connected, GigabitEthernet0/1
S*   0.0.0.0/0 [1/0] via 41.33.1.1</code></pre></div>

<p dir="rtl" align="right">
<strong>أهمية أوامر show بشكل عام:</strong> بينما أدوات الأقسام السابقة بتشخّص المشكلة من زاوية "هل جهازي عنده مشكلة في الوصول للشبكة؟"، أوامر show بتشخّص المشكلة من زاوية معاكسة تماماً: "هل جهاز الشبكة نفسه (الراوتر/السويتش) معدّى صح ومفيهوش مشكلة من الأساس؟" — وده بيكمّل الصورة الكاملة لعملية التشخيص من الطرفين.
</p>

---

<h2 dir="rtl" align="right" id="cheat-sheet-21">20. جدول المراجعة السريع (Cheat Sheet)</h2>

| الأداة / الأمر | الفئة | الوظيفة الأساسية |
|:---:|:---:|:---:|
| tracert / traceroute | تشخيص مسار | رسم مسار الحزمة كامل خطوة بخطوة عبر استغلال TTL |
| ipconfig | إعدادات شبكة | عرض IP/Subnet Mask/Gateway الأساسيين |
| ipconfig /all | إعدادات شبكة | عرض كل التفاصيل: MAC, DNS, DHCP, Lease |
| ipconfig /release | إعدادات شبكة | تحرير عنوان IP الحالي من DHCP |
| ipconfig /renew | إعدادات شبكة | طلب عنوان IP جديد من DHCP |
| ip addr / ip route / ip link | إعدادات شبكة (Linux) | المعادل الحديث لـ ifconfig وroute في Linux |
| ping | فحص اتصال | إرسال ICMP Echo Request وقياس الاستجابة |
| ping -t / -n / -l / -f | فحص اتصال | تحكم في التكرار، العدد، الحجم، ومنع التجزيء |
| PathPing | تشخيص مسار + أداء | Traceroute + إحصائيات فقدان الحزم لكل Hop (Windows فقط) |
| mtr | تشخيص مسار + أداء | معادل PathPing في Linux/Unix، تفاعلي لحظي |
| iperf / iperf3 | قياس أداء | قياس Throughput الفعلي بين جهازين (Client/Server) |
| nmap | فحص منافذ | Port Scanning فعلي: حالة المنافذ، الخدمات، ونظام التشغيل |
| arp -a | جدول ARP | عرض جدول ARP بالكامل |
| arp -s | جدول ARP | إضافة إدخال IP↔MAC ثابت يدوياً |
| arp -d | جدول ARP | حذف إدخال أو الجدول بالكامل |
| nslookup | تشخيص DNS | استعلام DNS مباشر (اسم↔IP)، متوفر في Windows/Linux |
| dig | تشخيص DNS (Linux) | استعلام DNS أعمق وأدق، مفضّل في بيئات Linux |
| hostname | معلومة أساسية | طباعة اسم الجهاز الحالي |
| route print | جدول توجيه | عرض جدول التوجيه المحلي للجهاز |
| route add / change / delete | جدول توجيه | إضافة/تعديل/حذف مسار ثابت يدوياً |
| nbtstat | NetBIOS | تشخيص أسماء وإحصائيات NetBIOS |
| netstat -r | اتصالات نشطة | عرض جدول التوجيه (مثل route print) |
| netstat -o | اتصالات نشطة | إظهار PID المسؤول عن كل اتصال |
| netstat -a | اتصالات نشطة | كل الاتصالات والمنافذ في وضع الاستماع |
| netstat -b | اتصالات نشطة | إظهار اسم البرنامج التنفيذي المسؤول عن الاتصال |
| netstat -n | اتصالات نشطة | عرض سريع بصيغة رقمية بدون تحليل أسماء |
| tcpdump | التقاط حزم (Linux) | النسخة النصية من Wireshark، تحليل الحزم لحظياً |
| telnet | فحص منفذ / إدارة قديمة | فتح جلسة نصية أو فحص هل منفذ معين مفتوح ورادّ (غير مشفّر) |
| ssh | إدارة عن بعد آمنة | بديل Telnet المشفّر بالكامل، Port 22 |
| ftp | نقل ملفات | رفع وتنزيل الملفات عبر Port 21 (تحكم) و20 (بيانات) |
| show interface | تشخيص سيسكو | حالة الواجهة، السرعة، الأخطاء والتصادمات |
| show running-config | تشخيص سيسكو | الإعدادات الفعلية الشغالة حالياً على الجهاز |
| show ip route | تشخيص سيسكو | جدول التوجيه من منظور الراوتر نفسه |

</div>