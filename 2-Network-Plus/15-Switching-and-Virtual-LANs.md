<div dir="rtl">

# 1️⃣5️⃣ Switching and Virtual LANs

<p dir="rtl" align="right">
الموضوع ده من أهم مواضيع الـ Network+، لأنه بيشرح إزاي جهاز الـ <strong>Switch</strong> بيشتغل جوه بجوه (Layer 2 Operations)، وإزاي بيمنع مشكلة دوران البيانات (Loops) عن طريق بروتوكول الـ <strong>STP</strong>، وإزاي بنقسم الشبكة الواحدة منطقيًا لعدة شبكات باستخدام الـ <strong>VLANs</strong>. الملف مرتب من الأبسط للأعمق: هنبدأ بمشكلة الـ Hub، بعدين أساسيات السويتش، بعدين آلية عمله الداخلية، بعدين مشكلة الدوران وحلها، بعدين تجميع الوصلات، بعدين تقسيم الشبكة لـ VLANs ونقلها عبر الترانك، وأخيرًا تصميم الشبكات الكبيرة والأمان والمراقبة. الموضوع مرتبط جدًا بملف <a href="09-Ethernet-LAN.md">Topic 9 - Ethernet/LAN</a> وملف <a href="10-Networking-Devices.md">Topic 10 - Networking Devices</a>، فلو حابب تراجع أساسيات الإيثرنت والسويتش قبل ما تكمل، ده هيساعدك.
</p>

---

## 📑 جدول المحتويات (Table of Contents)

| # | القسم الرئيسي | المواضيع الفرعية |
|:---:|:---:|:---:|
| 1 | [المقدمة: من الـ Hub إلى الـ Switch](#intro) | [مشاكل جهاز الـ Hub](#hub-limitations)<br>[الحاجة لجهاز الـ Switch](#need-for-switch) |
| 2 | [أساسيات جهاز الـ Switch](#switch-basics) | [تعريف السويتش وطبقة عمله](#switch-definition)<br>[وظائف ومهام السويتش](#switch-functions)<br>[مجال التصادم والـ Full-Duplex](#switch-collision-domain)<br>[سرعة السويتش وقدرته على النقل](#switch-speed)<br>[أنظمة تشغيل السويتشات](#switch-os)<br>[إدارة السويتش وأنواعه الإدارية](#switch-management) |
| 3 | [كيف يقوم السويتش بتمرير البيانات](#layer2-functions) | [عملية تعلم العناوين](#address-learning)<br>[جدول العناوين الفيزيائية](#mac-address-table)<br>[قرارات التصفية والإرسال](#forward-filter)<br>[عملية الإغراق](#flooding)<br>[تحديث الجدول](#table-aging)<br>[طرق التحويل الداخلي للفريمات](#switching-methods) |
| 4 | [عملية منع دوران البيانات](#loop-prevention) | [أسباب حدوث الدوران](#why-loops-happen)<br>[مشاكل الدوران](#loop-problems) |
| 5 | [بروتوكول الـ STP](#stp) | [تعريف البروتوكول ووظيفته](#stp-definition)<br>[رسائل الـ BPDU](#bpdu)<br>[قيمة الأولوية](#bridge-priority)<br>[انتخاب الـ Root Bridge](#root-bridge-election)<br>[تكلفة المسار](#path-cost)<br>[أدوار المنافذ](#port-roles)<br>&nbsp;&nbsp;&nbsp;[Root Port](#root-port)<br>&nbsp;&nbsp;&nbsp;[Designated Port](#designated-port)<br>&nbsp;&nbsp;&nbsp;[Blocked Port](#blocked-port)<br>[حالات منافذ STP](#port-states)<br>[عملية الاستقرار Convergence](#stp-convergence)<br>[تقنيات حماية إضافية للـ STP](#stp-protections) |
| 6 | [تجميع الوصلات EtherChannel](#etherchannel) | [تعريفه وفائدته](#etherchannel-definition)<br>[بروتوكولات التفاوض](#etherchannel-protocols) |
| 7 | [الشبكات المحلية الافتراضية VLANs](#vlan) | [تعريف الـ VLAN وأهميته](#vlan-definition)<br>[مميزات وفوائد الـ VLAN](#vlan-benefits)<br>[علاقة الراوتر بالـ VLAN](#vlan-router-relation)<br>[أنواع الـ VLAN](#vlan-types)<br>[طرق تخصيص المنافذ](#vlan-port-assignment)<br>[الـ VMPS](#vmps)<br>[تسمية الـ VLANs](#vlan-naming)<br>[أنواع منافذ الـ VLAN](#vlan-port-types)<br>[الـ VLAN ID](#vlan-id) |
| 8 | [الترانك Trunking](#trunking) | [تعريف الترانك ووظيفته](#trunking-definition)<br>[بروتوكول ISL](#isl)<br>[بروتوكول 802.1Q](#dot1q)<br>[بروتوكول DTP](#dtp)<br>[بروتوكول VTP](#vtp) |
| 9 | [تصميم الشبكة الهرمي وأنواع السويتش](#switch-hierarchy) | [Access Switch](#access-switch)<br>[Distribution Switch](#distribution-switch)<br>[Core Switch](#core-switch) |
| 10 | [أمان منافذ السويتش](#port-security) | [هجمات شائعة تستهدف السويتش](#switching-attacks)<br>[ربط أكثر من جهاز بمنفذ واحد](#multiple-devices-port)<br>[حماية 802.1X و NAC](#dot1x-nac)<br>[إعدادات Port Violation](#port-violation)<br>[طرق ربط المنافذ بالعناوين](#port-mac-binding) |
| 11 | [تقنية الـ PoE](#poe) | [تعريف PoE وعلاقته بالإيثرنت](#poe-definition)<br>[معايير وطرق تشغيل PoE](#poe-standards) |
| 12 | [منفذ تحليل البيانات](#span-rspan) | [SPAN](#span)<br>[RSPAN](#rspan) |

---

<h2 dir="rtl" align="right" id="intro">1️⃣ المقدمة: من الـ Hub إلى الـ Switch</h2>

<h3 dir="rtl" align="right" id="hub-limitations">🔹 مشاكل جهاز الـ Hub</h3>

<p dir="rtl" align="right">
قبل ما نتكلم عن السويتش، لازم نفهم ليه احتجنا له من الأساس. جهاز الـ <strong>Hub</strong> هو جهاز يعمل على <strong>Layer 1 (Physical Layer)</strong> من نموذج الـ OSI، ووظيفته الوحيدة إنه يستقبل الإشارة الكهربائية (Signal) من أي منفذ ويعيد إرسالها (Repeat) لكل باقي المنافذ التانية من غير أي ذكاء أو فهم للبيانات اللي بتمر بيه. الـ Hub معزول تمامًا عن مفهوم العناوين (لا يعرف MAC ولا IP)، وكل اللي بيعمله هو تكبير الإشارة وبثها للجميع.
</p>

<p dir="rtl" align="right">
المشاكل الأساسية اللي كانت موجودة في جهاز الـ Hub:
</p>

<ul dir="rtl">
<li><strong>مجال تصادم واحد (Single Collision Domain):</strong> كل الأجهزة المتصلة بالـ Hub بتشارك نفس مجال التصادم، يعني لو جهازين بعتوا بيانات في نفس اللحظة يحصل تصادم (Collision) والبيانات بتتلف ولازم تتبعت تاني.</li>
<li><strong>البث للجميع (Flooding للجميع دايمًا):</strong> أي بيانات بتوصل للـ Hub بتتبعت لكل المنافذ عدا المنفذ المرسل، حتى لو الرسالة كانت خاصة بجهاز واحد بس، وده بيهدر الـ Bandwidth بشكل كبير.</li>
<li><strong>ضعف الأمان:</strong> بما إن كل جهاز بياخد نسخة من كل البيانات المارة، أي جهاز على الشبكة يقدر يشوف بيانات باقي الأجهزة (Sniffing سهل جدًا).</li>
<li><strong>عدم دعم الـ Full-Duplex الحقيقي:</strong> بسبب مجال التصادم المشترك، الأجهزة المتصلة بالـ Hub غالبًا بتشتغل على Half-Duplex بس.</li>
<li><strong>العدد الأقصى للأجهزة:</strong> الـ Hub بيقلل من كفاءة الشبكة كل ما زاد عدد الأجهزة المتصلة بيه، لأن احتمالية التصادم بتزيد كل ما زاد عدد الأجهزة المشتركة في نفس مجال التصادم، وده بيخلي أداء الشبكة يقل بشكل ملحوظ مع زيادة عدد المستخدمين.</li>
</ul>

<h3 dir="rtl" align="right" id="need-for-switch">🔹 الحاجة لجهاز الـ Switch</h3>

<p dir="rtl" align="right">
بسبب كل المشاكل دي، احتجنا لجهاز أذكى يقدر يفهم العناوين الفيزيائية (MAC Addresses) ويوجه البيانات للجهاز المقصود بس، بدل ما يبثها للجميع. هنا ظهر جهاز الـ <strong>Switch</strong> اللي بيعمل على <strong>Layer 2 (Data Link Layer)</strong>، وبيحل معظم مشاكل الـ Hub عن طريق إنه بيخلق مجال تصادم منفصل لكل منفذ (Micro-segmentation)، وبيتعلم عناوين الأجهزة المتصلة بيه، وبيبعت البيانات للمنفذ الصح بس مش لكل المنافذ.
</p>

---

<h2 dir="rtl" align="right" id="switch-basics">2️⃣ أساسيات جهاز الـ Switch</h2>

<h3 dir="rtl" align="right" id="switch-definition">🔹 تعريف السويتش وطبقة عمله</h3>

<p dir="rtl" align="right">
جهاز الـ <strong>Switch</strong> هو جهاز شبكات ذكي بيربط عدة أجهزة مع بعض في نفس الشبكة المحلية (LAN)، وبيشتغل بشكل أساسي على <strong>Layer 2 - Data Link Layer</strong> من نموذج الـ OSI (راجع <a href="04-OSI-Model.md">Topic 4 - OSI Model</a>). الفكرة الأساسية إن السويتش بيتعلم عناوين الـ MAC الخاصة بالأجهزة المتصلة بيه عن طريق فحص الفريمات (Frames) اللي بتمر بيه، وبيبني جدول داخلي بيربط كل عنوان MAC بالمنفذ (Port) اللي الجهاز ده متصل بيه. لما توصله بيانات لعنوان معين، بيبحث في الجدول ده ويبعت البيانات للمنفذ الصح بس، وده اللي بيديله كفاءة أعلى بكتير من الـ Hub.
</p>

<p dir="rtl" align="right">
السويتش التقليدي (Layer 2 Switch) بيتعامل مع البيانات على مستوى الـ <strong>Frames</strong> والعناوين الفيزيائية (MAC Addresses) بس، من غير ما يفهم عناوين الـ IP. لكن الجملة الشهيرة اللي بتتقال في الكورسات هي إن "السويتش هو جهاز Layer 2، لكن السويتشات الحديثة بقت Layer 3 Switches" - يعني فيه سويتشات متقدمة بقت قادرة تعمل Routing بين الشبكات الفرعية المختلفة (زي الراوتر بالظبط)، وده هيتفصل أكتر في قسم <a href="#switch-hierarchy">تصميم الشبكة الهرمي</a> لاحقًا في الملف ده، وراجع كمان <a href="12-Introduction-to-IP-Routing.md">Topic 12</a> و<a href="13-Routing-Protocols.md">Topic 13</a>.
</p>

<h3 dir="rtl" align="right" id="switch-functions">🔹 وظائف ومهام السويتش</h3>

<ul dir="rtl">
<li><strong>Address Learning:</strong> تعلم عناوين الـ MAC للأجهزة المتصلة وربطها بالمنافذ.</li>
<li><strong>Forwarding/Filtering:</strong> اتخاذ قرار إرسال البيانات للمنفذ الصحيح أو تجاهلها.</li>
<li><strong>Loop Avoidance:</strong> منع دوران البيانات في الشبكة عن طريق بروتوكول STP.</li>
<li><strong>Micro-segmentation:</strong> عزل كل منفذ في مجال تصادم منفصل (Collision Domain).</li>
<li>دعم تقنيات إضافية زي الـ VLANs، الـ Trunking، الـ Port Security، والـ PoE في بعض الأجهزة.</li>
</ul>

<p dir="rtl" align="right">
الوظائف دي هتتشرح كل واحدة فيها بالتفصيل في الأقسام الجاية، وده الترتيب اللي هنمشي بيه: الأول هنفهم خصائص السويتش الأساسية (السرعة، مجال التصادم، الإدارة)، بعدين هنغوص في التفاصيل الداخلية لكل وظيفة.
</p>

<h3 dir="rtl" align="right" id="switch-collision-domain">🔹 مجال التصادم والـ Full-Duplex</h3>

<p dir="rtl" align="right">
كل منفذ (Port) في جهاز السويتش بيمثل مجال تصادم منفصل (Separate Collision Domain) عن باقي المنافذ. ده معناه إن جهازين متصلين بمنفذين مختلفين في نفس السويتش مش هيحصل بينهم تصادم أبدًا، وده بيسمح للسويتش بدعم الـ <strong>Full-Duplex</strong> الحقيقي، يعني الإرسال والاستقبال في نفس الوقت من غير أي تصادم. أما مجال البث (Broadcast Domain) فبيفضل واحد لكل السويتش (إلا لو عملنا VLANs، هيتشرح لاحقًا في القسم رقم 7).
</p>

<h3 dir="rtl" align="right" id="switch-speed">🔹 سرعة السويتش وقدرته على النقل</h3>

<p dir="rtl" align="right">
سرعة السويتش بتعتمد على سرعة كل منفذ فيه (10/100/1000 Mbps أو حتى 10/40/100 Gbps في السويتشات الحديثة)، وكل منفذ ممكن يشتغل بسرعة مختلفة عن التاني حسب الجهاز المتصل بيه (راجع مفهوم Auto-negotiation في <a href="09-Ethernet-LAN.md">Topic 9</a>). السويتشات الحديثة بتدعم كمان مفهوم الـ <strong>Switching Fabric (Backplane)</strong> اللي بيحدد أقصى سرعة إجمالية يقدر السويتش يتعامل معاها في نفس الوقت على كل منافذه مجتمعة، فسويتش عنده 24 منفذ بسرعة 1 Gbps مش بالضرورة يقدر يشغل كل المنافذ دي بأقصى سرعة في نفس اللحظة لو الـ Backplane بتاعه أصغر من مجموع سرعات المنافذ.
</p>

<h3 dir="rtl" align="right" id="switch-os">🔹 أنظمة تشغيل السويتشات</h3>

<p dir="rtl" align="right">
السويتشات (خصوصًا الاحترافية زي أجهزة Cisco) بتشتغل بأنظمة تشغيل خاصة بيها بتتحكم في كل إعداداتها، أشهرها نظام <strong>Cisco IOS (Internetwork Operating System)</strong>. الفرق بين الأنظمة المختلفة بيكون غالبًا في:
</p>

<ul dir="rtl">
<li><strong>مستوى الدعم للميزات المتقدمة:</strong> بعض الأنظمة بتدعم VLANs وTrunking وQoS متقدم، وبعضها بيكون أبسط (سويتشات Unmanaged).</li>
<li><strong>طريقة الإدارة:</strong> بعض الأنظمة بتدعم واجهة سطر أوامر (CLI) كاملة، وبعضها بس واجهة ويب بسيطة.</li>
<li><strong>القابلية للبرمجة (Programmability):</strong> السويتشات الحديثة جدًا بتدعم APIs وأتمتة عبر أدوات زي Ansible أو Python.</li>
</ul>

<h3 dir="rtl" align="right" id="switch-management">🔹 إدارة السويتش وأنواعه الإدارية</h3>

<p dir="rtl" align="right">
حسب مستوى الإدارة، السويتشات بتتقسم لثلاث فئات رئيسية:
</p>

<ul dir="rtl">
<li><strong>Unmanaged Switch:</strong> سويتش بسيط بدون أي إعدادات، شغال بمجرد التوصيل (Plug and Play)، غالبًا بيستخدم في الشبكات المنزلية الصغيرة.</li>
<li><strong>Managed Switch:</strong> بيدعم إعدادات متقدمة زي الـ VLANs، الـ Port Security، الـ STP tuning، وممكن يتم الوصول له عن طريق CLI أو واجهة ويب أو SNMP.</li>
<li><strong>Smart/Web-managed Switch:</strong> حل وسط بين الاتنين، بيدعم بعض الإعدادات الأساسية من خلال واجهة ويب بسيطة من غير تعقيد الـ CLI الكامل.</li>
</ul>

<p dir="rtl" align="right">
من أهم الإعدادات اللي ممكن نتحكم فيها في السويتش المُدار (Managed): تفعيل/تعطيل المنافذ، ضبط الـ VLANs، ضبط الـ Trunking، تفعيل الـ Port Security، ضبط الـ Spanning Tree، وضبط الـ SNMP للمراقبة عن بعد. الأقسام الجاية هتشرح كل واحدة من الإعدادات دي بالتفصيل، بدايةً من الآلية الداخلية اللي بيشتغل بيها السويتش قبل حتى ما نتكلم عن إعداده.
</p>

---

<h2 dir="rtl" align="right" id="layer2-functions">3️⃣ كيف يقوم السويتش بتمرير البيانات (Layer 2 Forwarding)</h2>

<h3 dir="rtl" align="right" id="address-learning">🔹 عملية تعلم العناوين (Address Learning)</h3>

<p dir="rtl" align="right">
لما فريم (Frame) يوصل لأي منفذ في السويتش، السويتش بيفحص عنوان الـ MAC الخاص بالمرسل (Source MAC Address) الموجود في هيدر الفريم، وبيسجله في جدول العناوين الفيزيائية (MAC Address Table) مع رقم المنفذ اللي وصل منه الفريم ده. بالطريقة دي، السويتش بيتعلم مين متصل بأي منفذ بشكل تلقائي وديناميكي (Dynamic Learning) من غير أي إعداد يدوي، وده اللي بيميزه عن الـ Hub اللي معندوش أي فكرة عن العناوين خالص.
</p>

<h3 dir="rtl" align="right" id="mac-address-table">🔹 جدول العناوين الفيزيائية (MAC Address Table)</h3>

<p dir="rtl" align="right">
جدول العناوين الفيزيائية (وبيتسمى كمان <strong>CAM Table - Content Addressable Memory</strong>) هو الجدول الداخلي اللي بيحتفظ فيه السويتش بربط كل عنوان MAC بالمنفذ اللي اتعلم منه. الجدول ده بيتكون من عمودين أساسيين: عنوان الـ MAC، ورقم المنفذ (Port Number)، وممكن يضاف عمود ثالث للـ VLAN ID لو الشبكة فيها أكتر من VLAN.
</p>

<p dir="rtl" align="right">
كل ما زاد عدد الأجهزة المتصلة بالشبكة، كل ما زاد حجم الجدول ده، وحجم الجدول محدود بمساحة الذاكرة المخصصة له في السويتش، فلو الجدول امتلأ بالكامل، السويتش ممكن يضطر يعامل الفريمات الجديدة كإغراق (Flooding) بدل التحويل المباشر لحد ما تتوفر مساحة. (ملحوظة: امتلاء الجدول ده ممكن يحصل عمدًا كهجوم، هنشرحه في قسم <a href="#switching-attacks">هجمات السويتش</a> لاحقًا).
</p>

<h3 dir="rtl" align="right" id="forward-filter">🔹 قرارات التصفية والإرسال (Forward/Filter Decisions)</h3>

<p dir="rtl" align="right">
لما السويتش يستقبل فريم، بيبص على عنوان الـ MAC الخاص بالمُستقبِل (Destination MAC Address) ويقارنه بجدول العناوين:
</p>

<ul dir="rtl">
<li>لو العنوان موجود في الجدول ومرتبط بمنفذ معين → السويتش بيبعت الفريم للمنفذ ده بس (Forwarding).</li>
<li>لو العنوان بتاع نفس المنفذ اللي جه منه الفريم → السويتش بيتجاهل الفريم تمامًا لأن الجهازين على نفس السيجمنت أصلاً (Filtering).</li>
<li>لو العنوان مش موجود في الجدول خالص → السويتش بيلجأ لعملية الإغراق (Flooding)، هنشرحها في الفقرة الجاية.</li>
</ul>

<h3 dir="rtl" align="right" id="flooding">🔹 عملية الإغراق (Flooding)</h3>

<p dir="rtl" align="right">
لو عنوان الـ MAC الخاص بالمُستقبِل مش موجود في جدول العناوين (يعني السويتش لسه ما اتعلموش)، السويتش بيضطر يبعت نسخة من الفريم لكل المنافذ عدا المنفذ اللي جه منه الفريم الأصلي، تمامًا زي ما كان بيعمل الـ Hub، وده بيتسمى <strong>Flooding</strong> أو <strong>Unknown Unicast Flooding</strong>. الهدف من ده إن الجهاز المقصود، لو كان فعلاً متصل بالشبكة، هيرد على الفريم، وعند الرد ده السويتش هيتعلم عنوانه ويسجله في الجدول، وبعدها أي اتصال جاي هيتبعت مباشرة للمنفذ الصح من غير إغراق.
</p>

<p dir="rtl" align="right">
نفس الأمر بيحصل مع رسائل الـ <strong>Broadcast</strong> (زي رسائل الـ ARP Requests) اللي دايمًا بتتبعت لكل المنافذ بطبيعتها، بغض النظر عن وجود العنوان في الجدول أو لأ.
</p>

<h3 dir="rtl" align="right" id="table-aging">🔹 تحديث الجدول (Aging)</h3>

<p dir="rtl" align="right">
جدول العناوين مش ثابت للأبد، كل مدخل (Entry) فيه ليه وقت صلاحية (Aging Time)، وغالبًا بيكون افتراضيًا حوالي <strong>300 ثانية (5 دقائق)</strong>. لو عنوان معين ما ظهرش في أي فريم جديد خلال المدة دي، السويتش بيمسحه من الجدول تلقائيًا عشان يوفر مساحة للأجهزة النشطة، ولو الجهاز ده بعت أي فريم تاني بعد كده، السويتش هيعيد تعلم عنوانه من الأول.
</p>

<h3 dir="rtl" align="right" id="switching-methods">🔹 طرق التحويل الداخلي للفريمات (Switching Methods)</h3>

<p dir="rtl" align="right">
بعد ما فهمنا إزاي السويتش بيتخذ قرار الإرسال، السؤال التاني: هل السويتش بيستنى يستقبل الفريم كامل الأول قبل ما يبدأ يبعته؟ ولا بيبدأ الإرسال فورًا؟ الإجابة بتختلف حسب طريقة التحويل (Switching Method) المستخدمة، وفيه ثلاث طرق رئيسية:
</p>

<ul dir="rtl">
<li><strong>Store-and-Forward:</strong> السويتش بيستقبل الفريم بالكامل الأول، بيتأكد من سلامته عن طريق فحص الـ FCS (Frame Check Sequence)، ولو الفريم سليم بيبعته للمنفذ الصح؛ لو فيه خطأ بيرفضه تمامًا. الطريقة دي الأكتر أمانًا ودقة لكنها الأبطأ نسبيًا لأنها بتستنى وصول الفريم كامل الأول.</li>
<li><strong>Cut-Through:</strong> السويتش بيبدأ إرسال الفريم بمجرد ما يقرأ عنوان الـ MAC الخاص بالمُستقبِل بس (أول جزء من الفريم)، من غير ما يستنى وصوله كامل ومن غير ما يفحص الأخطاء. الطريقة دي أسرع بكتير لكن ممكن تمرر فريمات فيها أخطاء أو تصادمات لأنها معندهاش فحص للـ FCS.</li>
<li><strong>Fragment-Free:</strong> حل وسط بين الطريقتين، السويتش بيستنى وصول أول 64 بايت بس من الفريم (وهو أقل حجم ممكن يحصل فيه تصادم حسب معايير الإيثرنت) قبل ما يبدأ الإرسال، وده بيقلل من تمرير الفريمات التالفة بسبب التصادم من غير ما يضحي بالسرعة زي الـ Store-and-Forward بالكامل.</li>
</ul>

<p dir="rtl" align="right">
اختيار الطريقة المناسبة بيعتمد على التوازن المطلوب بين السرعة والدقة، والسويتشات الحديثة غالبًا بتستخدم Store-and-Forward كإعداد افتراضي لأن قوة المعالجة بقت كافية إنها متأثرش على السرعة بشكل ملحوظ.
</p>

---

<h2 dir="rtl" align="right" id="loop-prevention">4️⃣ عملية منع دوران البيانات (Loop Prevention)</h2>

<h3 dir="rtl" align="right" id="why-loops-happen">🔹 أسباب حدوث دوران البيانات</h3>

<p dir="rtl" align="right">
دوران البيانات (Switching Loop) بيحصل لما يكون فيه أكتر من مسار فيزيائي واحد بين نفس السويتشين أو أكتر (Redundant Links)، وده غالبًا بيتعمل عن قصد عشان توفير مسار احتياطي (Redundancy) في حالة سقوط أي وصلة. المشكلة إن السويتشات بطبيعتها بتعمل Flooding لأي فريم Broadcast أو فريم مجهول العنوان (زي ما شرحنا في القسم اللي فات)، فلو فيه مسار دائري بين السويتشات، الفريم ده هيدور في حلقة مفرغة من غير ما يوصل لنهاية أبدًا.
</p>

<h3 dir="rtl" align="right" id="loop-problems">🔹 مشاكل الدوران</h3>

<ul dir="rtl">
<li><strong>Broadcast Storm:</strong> الفريمات بتتضاعف وتدور في حلقات لا نهائية وبتستهلك كل الـ Bandwidth المتاح لحد ما الشبكة بالكامل توقف عن العمل.</li>
<li><strong>عدم استقرار جدول العناوين (MAC Table Instability):</strong> السويتش بيشوف نفس عنوان الـ MAC بييجي من أكتر من منفذ في نفس الوقت (لأن الفريم بيدور)، فبيفضل يحدث الجدول باستمرار بشكل خاطئ.</li>
<li><strong>استقبال نسخ متعددة من نفس الفريم (Duplicate Frame Delivery):</strong> الجهاز المستقبِل ممكن يستلم أكتر من نسخة من نفس الفريم، وده بيسبب مشاكل في التطبيقات اللي بتتأثر بتكرار البيانات.</li>
</ul>

<p dir="rtl" align="right">
عشان نستفيد من فوائد الـ Redundant Links (توفير مسار احتياطي) من غير ما نقع في مشاكل الدوران دي، ظهر بروتوكول <strong>Spanning Tree Protocol (STP)</strong>.
</p>

---

<h2 dir="rtl" align="right" id="stp">5️⃣ بروتوكول الـ STP (Spanning Tree Protocol)</h2>

<h3 dir="rtl" align="right" id="stp-definition">🔹 تعريف البروتوكول ووظيفته</h3>

<p dir="rtl" align="right">
بروتوكول <strong>STP (IEEE 802.1D)</strong> هو بروتوكول بيشتغل على مستوى الـ Layer 2، ووظيفته الأساسية إنه يمنع حدوث دوران البيانات (Loops) في الشبكات اللي فيها مسارات احتياطية متعددة بين السويتشات، من غير ما يفقدنا ميزة التوفر الاحتياطي (Redundancy). الفكرة الأساسية إن STP بيبني "شجرة منطقية" (Logical Tree) من السويتشات، وبيحدد مسار واحد نشط فقط بين أي سويتشين، وأي مسار زيادة بيتم إغلاقه منطقيًا (Blocking) لحد ما يحتاجه في حالة سقوط المسار النشط.
</p>

<h3 dir="rtl" align="right" id="bpdu">🔹 رسائل الـ BPDU (Bridge Protocol Data Units)</h3>

<p dir="rtl" align="right">
عشان السويتشات تقدر تتفق فيما بينها على شكل الشجرة المنطقية، بتتبادل رسائل خاصة اسمها <strong>BPDU</strong> بشكل دوري (كل ثانيتين افتراضيًا). رسائل الـ BPDU بتحمل معلومات مهمة زي:
</p>

<ul dir="rtl">
<li>قيمة أولوية السويتش المرسل (Bridge Priority) وعنوان الـ MAC بتاعه، عشان تحديد هوية السويتش (Bridge ID).</li>
<li>معلومات عن السويتش اللي يعتقد إنه الـ Root Bridge حاليًا.</li>
<li>تكلفة المسار (Path Cost) من السويتش المرسل لحد الـ Root Bridge.</li>
<li>رقم المنفذ اللي اتبعتت منه الرسالة (Port ID).</li>
</ul>

<p dir="rtl" align="right">
باستخدام المعلومات دي، كل السويتشات بتقدر توصل لاتفاق جماعي على شكل الشبكة، وتحدد مين هو السويتش الرئيسي، ومين هي المنافذ اللي هتشتغل ومين اللي هتتقفل.
</p>

<h3 dir="rtl" align="right" id="bridge-priority">🔹 قيمة الأولوية (Bridge Priority)</h3>

<p dir="rtl" align="right">
كل سويتش ليه قيمة أولوية (Bridge Priority) بتتراوح من 0 إلى 65535، والقيمة الافتراضية غالبًا بتكون <strong>32768</strong>. القيمة دي بتتجمع مع عنوان الـ MAC الخاص بالسويتش عشان تكون ما يُسمى بـ <strong>Bridge ID</strong>. القيمة دي هي الأساس اللي بيتم على أساسه اختيار الـ Root Bridge: كل ما كانت قيمة الأولوية أقل، كل ما كانت أفضلية السويتش في الفوز بمنصب الـ Root Bridge أعلى.
</p>

<h3 dir="rtl" align="right" id="root-bridge-election">🔹 انتخاب السويتش الرئيسي (Root Bridge Election)</h3>

<p dir="rtl" align="right">
عملية اختيار الـ <strong>Root Bridge</strong> بتتم بمقارنة قيم الـ Bridge ID بين كل السويتشات المشاركة في الشبكة:
</p>

<ol dir="rtl">
<li>أول معيار للمقارنة هو قيمة <strong>Bridge Priority</strong>: السويتش صاحب أقل قيمة أولوية بيفوز.</li>
<li>لو فيه تعادل في قيمة الأولوية بين اتنين سويتش أو أكتر، المقارنة بتتحول لعنوان الـ <strong>MAC Address</strong>: السويتش صاحب أصغر عنوان MAC (رقميًا) بيفوز.</li>
</ol>

<p dir="rtl" align="right">
السويتش اللي بيفوز بيبقى هو الـ <strong>Root Bridge</strong> لكل الشبكة، وكل باقي السويتشات (وبتتسمى <strong>Non-Root Bridges</strong>) بتحسب مسافتها منه عشان تبني الشجرة المنطقية.
</p>

<h3 dir="rtl" align="right" id="path-cost">🔹 تكلفة المسار (Path Cost)</h3>

<p dir="rtl" align="right">
تكلفة المسار (Path Cost) هي قيمة بتحدد "بعد" السويتش عن الـ Root Bridge، وبتُحسب بناءً على سرعة الوصلة (Link Speed)؛ كل ما كانت سرعة الوصلة أعلى، كل ما كانت تكلفتها أقل (لأن الوصلة السريعة "أرخص" من ناحية زمن الوصول). القيم القياسية للتكلفة حسب سرعة الوصلة تقريبًا:
</p>

<table align="center">
<tr><th>سرعة الوصلة</th><th>تكلفة المسار (Cost)</th></tr>
<tr><td>10 Mbps</td><td>100</td></tr>
<tr><td>100 Mbps</td><td>19</td></tr>
<tr><td>1 Gbps</td><td>4</td></tr>
<tr><td>10 Gbps</td><td>2</td></tr>
</table>

<p dir="rtl" align="right">
لو المسار من سويتش معين للـ Root Bridge بيمر بأكتر من وصلة (عبر سويتشات وسيطة)، تكلفة المسار الكلية بتكون مجموع تكلفة كل الوصلات دي (Cumulative Path Cost). السويتش بيختار المسار الأقل تكلفة من بين كل المسارات المتاحة له للوصول للـ Root Bridge.
</p>

<h3 dir="rtl" align="right" id="port-roles">🔹 أدوار المنافذ (Port Roles)</h3>

<p dir="rtl" align="right">
بعد ما يتحدد الـ Root Bridge وتُحسب تكلفة المسارات، كل منفذ في الشبكة بياخد دور معين حسب مكانه:
</p>

<h4 dir="rtl" align="right" id="root-port">▪️ Root Port (RP)</h4>

<p dir="rtl" align="right">
هو المنفذ الوحيد في كل سويتش (غير الـ Root Bridge نفسه) اللي بيوفر أقل تكلفة مسار (Lowest Path Cost) للوصول للـ Root Bridge. كل سويتش (Non-Root) ليه Root Port واحد بس، وده بيفضل دايمًا في وضع الإرسال (Forwarding).
</p>

<p dir="rtl" align="right">
<strong>مثال:</strong> لو عندنا سويتشين (A و B) متصلين مباشرة بـ Root Bridge بوصلتين مختلفتين، السويتش اللي وصلته له تكلفة أقل (يعني سرعتها أعلى) هيكون منفذه هو الـ Root Port. لو عندنا ثلاث سويتشات متسلسلة (Root ← B ← C)، السويتش C هياخد الـ Root Port بتاعه على المنفذ المتصل بـ B مباشرة، وتكلفة المسار بتتجمع من C لـ B لـ Root. ولو عندنا أربع سويتشات في حلقة (Ring)، كل سويتش هيحسب أقصر مسار ليه للـ Root سواء من الاتجاه اليمين أو الشمال، ويختار الأقل تكلفة.
</p>

<h4 dir="rtl" align="right" id="designated-port">▪️ Designated Port (DP)</h4>

<p dir="rtl" align="right">
على كل سيجمنت (Segment) بين سويتشين، لازم يكون فيه منفذ واحد بس مسؤول عن تمرير البيانات، وده بيتسمى <strong>Designated Port</strong>. الاختيار بيتم بمقارنة تكلفة المسار للـ Root Bridge من كل سويتش على السيجمنت، والسويتش صاحب أقل تكلفة بيفوز بمنصب الـ Designated Port على السيجمنت ده. الـ Root Bridge نفسه، كل منافذه بتكون Designated Ports تلقائيًا (لأن تكلفته للوصول لنفسه = صفر).
</p>

<h4 dir="rtl" align="right" id="blocked-port">▪️ Blocked / Non-Designated Port (BP)</h4>

<p dir="rtl" align="right">
أي منفذ مش Root Port ومش Designated Port بيتحول لحالة <strong>Blocking</strong>، يعني بيوقف استقبال وإرسال البيانات العادية (بيفضل بس يستقبل رسائل BPDU عشان يعرف لو حصل تغيير في الشبكة). ده هو المسار الاحتياطي اللي بيمنع الدوران، وهيتفعل تلقائيًا لو المسار النشط سقط.
</p>

<h3 dir="rtl" align="right" id="port-states">🔹 حالات منافذ STP (Port States)</h3>

<p dir="rtl" align="right">
منفذ السويتش بيمر بعدة حالات قبل ما يوصل لحالة الإرسال الكامل، والجدول ده بيلخص كل حالة والمدة التقريبية بتاعتها:
</p>

<table align="center">
<tr><th>الحالة</th><th>الوصف</th><th>المدة التقريبية</th></tr>
<tr><td><strong>Blocking</strong></td><td>المنفذ مقفول، بيستقبل BPDUs بس، ولا يرسل أو يستقبل بيانات</td><td>20 ثانية (Max Age)</td></tr>
<tr><td><strong>Listening</strong></td><td>المنفذ بدأ يشارك في حساب الشجرة المنطقية، لسه مبيمررش بيانات</td><td>15 ثانية (Forward Delay)</td></tr>
<tr><td><strong>Learning</strong></td><td>المنفذ بدأ يبني جدول عناوين الـ MAC، لسه مبيمررش بيانات المستخدمين</td><td>15 ثانية (Forward Delay)</td></tr>
<tr><td><strong>Forwarding</strong></td><td>المنفذ بيشتغل بشكل طبيعي، بيرسل ويستقبل البيانات</td><td>مستمر لحد أي تغيير</td></tr>
<tr><td><strong>Disabled</strong></td><td>المنفذ متوقف بالكامل يدويًا أو بسبب عطل</td><td>لحد ما يتفعل يدويًا</td></tr>
</table>

<p dir="rtl" align="right">
عملية انتقال المنفذ من حالة Blocking لحد حالة Forwarding مش بتحصل فجأة، لازم يمر بمراحل Listening ثم Learning أولاً، والهدف من ده إنه يتأكد إن الشجرة المنطقية استقرت تمامًا قبل ما يبدأ يمرر بيانات المستخدمين الحقيقية، عشان يتجنب حدوث Loops مؤقتة أثناء فترة إعادة الحساب.
</p>

<h3 dir="rtl" align="right" id="stp-convergence">🔹 عملية الاستقرار (STP Convergence)</h3>

<p dir="rtl" align="right">
<strong>STP Convergence</strong> هي العملية اللي بتاخدها كل سويتشات الشبكة عشان توصل لاتفاق جماعي كامل على شكل الشجرة المنطقية: مين الـ Root Bridge، ومين الـ Root Ports، ومين الـ Designated Ports، ومين المنافذ المقفولة. الوقت التقليدي اللي بروتوكول STP الأصلي (802.1D) بياخده عشان الشبكة تستقر بالكامل ممكن يوصل لحوالي <strong>30-50 ثانية</strong> (بسبب مراحل Blocking و Listening و Learning اللي فاتت).
</p>

<p dir="rtl" align="right">
العوامل اللي ممكن تلغي عملية الاستقرار وتخلي الشبكة تعيد حساب الشجرة من جديد:
</p>

<ul dir="rtl">
<li>إضافة أو إزالة سويتش جديد للشبكة.</li>
<li>سقوط أو استعادة أي وصلة بين السويتشات (Link Down/Up).</li>
<li>تغيير في قيمة الأولوية (Priority) لأي سويتش يدويًا.</li>
<li>تغيير في تكلفة المسار (Path Cost) نتيجة تغيير سرعة وصلة معينة.</li>
</ul>

<p dir="rtl" align="right">
بسبب بطء بروتوكول STP الأصلي، ظهرت نسخ محسّنة زي <strong>RSTP (Rapid Spanning Tree Protocol - IEEE 802.1w)</strong> اللي بتقلل وقت الاستقرار لثواني معدودة بدل عشرات الثواني، و<strong>MSTP (Multiple Spanning Tree Protocol)</strong> اللي بيسمح بتشغيل أكتر من شجرة منطقية مستقلة لكل مجموعة VLANs.
</p>

<h3 dir="rtl" align="right" id="stp-protections">🔹 تقنيات حماية إضافية للـ STP</h3>

<p dir="rtl" align="right">
بالإضافة للعمل الأساسي لبروتوكول STP، فيه مجموعة من الميزات الإضافية اللي بتحسن أداءه وتحميه من مشاكل الإعداد الخاطئ:
</p>

<ul dir="rtl">
<li><strong>PortFast:</strong> بتُستخدم على منافذ الـ Access اللي متصلة بأجهزة نهائية (كمبيوتر مثلاً) بس، مش بسويتشات تانية. بتخلي المنفذ يقفز فورًا لحالة Forwarding من غير ما يمر بمراحل Listening وLearning البطيئة، لأن مفيش احتمال حدوث Loop من جهاز نهائي واحد.</li>
<li><strong>BPDU Guard:</strong> بتتفعل غالبًا مع PortFast، ووظيفتها إنها تقفل المنفذ تلقائيًا (Err-Disabled) لو استقبل رسالة BPDU بشكل غير متوقع، لأن ده معناه إن حد وصل سويتش أو جهاز مش مصرح بيه على منفذ كان المفروض يكون لجهاز نهائي بس.</li>
<li><strong>Root Guard:</strong> بتمنع أي منفذ معين من أنه يقبل يبقى Root Port، يعني بتمنع سويتش خارجي (زي سويتش موصل غلط أو بقصد سيء) من أنه يفوز بمنصب الـ Root Bridge على حساب السويتش الأساسي المعتمد في التصميم.</li>
<li><strong>Loop Guard:</strong> بتحمي من حدوث Loop في حالة إن منفذ كان في وضع Blocking توقف عن استقبال رسائل BPDU بشكل غير طبيعي (مش بسبب سقوط الوصلة فعليًا)، فبدل ما يتحول تلقائيًا لـ Forwarding بالخطأ، الميزة دي بتخليه يفضل في وضع Blocking للأمان.</li>
</ul>

---

<h2 dir="rtl" align="right" id="etherchannel">6️⃣ تجميع الوصلات (EtherChannel / Link Aggregation)</h2>

<h3 dir="rtl" align="right" id="etherchannel-definition">🔹 تعريفه وفائدته</h3>

<p dir="rtl" align="right">
لاحظنا في قسم STP إن أي وصلة احتياطية زيادة بين سويتشين بتتقفل (Blocking) عشان تمنع حدوث Loop، وده معناه إن الـ Bandwidth الإضافي بتاع الوصلة دي بيروح هدر طول ما مفيش عطل. تقنية <strong>EtherChannel</strong> (أو بمصطلحها العام <strong>Link Aggregation</strong>) بتحل المشكلة دي بطريقة مختلفة: بدل ما نخلي STP يقفل الوصلات الزيادة، بندمج عدة وصلات فيزيائية (Physical Links) بين نفس السويتشين في وصلة منطقية واحدة (Logical Link)، وبالنسبالة لبروتوكول STP الوصلة المجمعة دي بتظهر كوصلة واحدة بس، فمفيش داعي يقفل حاجة.
</p>

<p dir="rtl" align="right">
الفوائد الأساسية لتقنية EtherChannel:
</p>

<ul dir="rtl">
<li><strong>زيادة الـ Bandwidth الكلي:</strong> جمع سرعات كل الوصلات المشتركة في القناة (مثلاً 4 وصلات بسرعة 1 Gbps هتدي سرعة إجمالية تقارب 4 Gbps).</li>
<li><strong>توفر عالي (High Availability):</strong> لو وصلة واحدة من ضمن القناة سقطت، الترافيك بيتوزع تلقائيًا على باقي الوصلات من غير أي انقطاع أو إعادة حساب لشجرة الـ STP.</li>
<li><strong>الاستفادة الكاملة من كل الوصلات الفيزيائية</strong> بدل ما STP يقفل بعضها.</li>
</ul>

<h3 dir="rtl" align="right" id="etherchannel-protocols">🔹 بروتوكولات التفاوض</h3>

<p dir="rtl" align="right">
عشان السويتشين يتفقوا على تجميع الوصلات صح، بيستخدموا بروتوكول تفاوض (Negotiation Protocol)، وأشهرهم:
</p>

<ul dir="rtl">
<li><strong>LACP (Link Aggregation Control Protocol - IEEE 802.3ad):</strong> بروتوكول معياري مفتوح ومدعوم من كل الشركات المصنعة تقريبًا.</li>
<li><strong>PAgP (Port Aggregation Protocol):</strong> بروتوكول خاص بشركة Cisco (Proprietary) بيعمل نفس الوظيفة.</li>
</ul>

<p dir="rtl" align="right">
الوصلات المجمعة في نفس القناة لازم تكون متطابقة في الإعدادات (نفس السرعة، نفس وضع الـ Duplex، ونفس إعدادات الـ VLAN/Trunking) عشان عملية التجميع تنجح بشكل صحيح.
</p>

---

<h2 dir="rtl" align="right" id="vlan">7️⃣ الشبكات المحلية الافتراضية (VLANs)</h2>

<h3 dir="rtl" align="right" id="vlan-definition">🔹 تعريف الـ VLAN وأهميته</h3>

<p dir="rtl" align="right">
الشبكة المحلية (LAN) في وضعها الطبيعي، كل الأجهزة المتصلة بنفس السويتش (أو مجموعة سويتشات متصلة ببعض) بتشارك نفس مجال البث الواحد (Broadcast Domain)، يعني أي رسالة Broadcast بتوصل لكل الأجهزة. الشبكة المحلية الافتراضية (<strong>VLAN - Virtual LAN</strong>) هي تقنية بتسمح لنا نقسم شبكة فيزيائية واحدة (سويتش واحد أو مجموعة سويتشات) لعدة شبكات منطقية منفصلة، وكل شبكة منطقية (VLAN) بيكون ليها مجال بث خاص بيها، بمعنى إن الأجهزة في VLAN معين مش هتستقبل رسائل Broadcast من أجهزة في VLAN تاني، رغم إنهم فيزيائيًا ممكن يكونوا متصلين بنفس جهاز السويتش.
</p>

<h3 dir="rtl" align="right" id="vlan-benefits">🔹 مميزات وفوائد الـ VLAN</h3>

<ul dir="rtl">
<li><strong>الأمان (Security):</strong> عزل الأقسام الحساسة (زي قسم المحاسبة أو الإدارة) عن باقي أقسام الشبكة منطقيًا، حتى لو كانوا على نفس السويتش الفيزيائي.</li>
<li><strong>تقليل حجم مجال البث (Broadcast Domain Reduction):</strong> تقسيم شبكة كبيرة لعدة VLANs بيقلل من كمية الـ Broadcast Traffic في كل شبكة فرعية، وده بيحسن الأداء.</li>
<li><strong>المرونة في التنظيم (Flexibility):</strong> ممكن نجمع أجهزة موجودة فيزيائيًا في أماكن مختلفة (طوابق مختلفة مثلاً) في نفس الـ VLAN المنطقي، بدل ما التنظيم يكون مربوط بالموقع الفيزيائي بس.</li>
<li><strong>سهولة الإدارة (Manageability):</strong> تطبيق سياسات مختلفة (QoS، ACLs) على كل قسم من أقسام الشركة بشكل منفصل وواضح.</li>
<li><strong>توفير التكلفة:</strong> بدل ما نشتري سويتش فيزيائي منفصل لكل قسم، بنستخدم سويتش واحد ونقسمه منطقيًا لعدة VLANs.</li>
</ul>

<h3 dir="rtl" align="right" id="vlan-router-relation">🔹 علاقة الراوتر بالـ VLAN (Router-on-a-Stick)</h3>

<p dir="rtl" align="right">
بما إن كل VLAN بيمثل شبكة منطقية منفصلة (Broadcast Domain منفصل)، فالأجهزة اللي في VLANs مختلفة معندهاش طريقة تتواصل مع بعضها مباشرة على مستوى Layer 2، ولازم يتدخل جهاز Layer 3 (راوتر أو Layer 3 Switch) عشان يعمل توجيه (Routing) بين الشبكات الفرعية دي. الحل الكلاسيكي المشهور بيتسمى <strong>Router-on-a-Stick</strong>: بدل ما نوصل الراوتر بكل VLAN عن طريق منفذ فيزيائي منفصل (وده مكلف ومحدود بعدد منافذ الراوتر)، بنوصل الراوتر بالسويتش عن طريق <strong>منفذ واحد بس</strong> يشتغل كـ Trunk Port (هيتشرح في القسم الجاي)، وبنقسم المنفذ ده منطقيًا لعدة Sub-interfaces، كل Sub-interface بيمثل بوابة (Gateway) لواحد من الـ VLANs. بالطريقة دي، ممكن راوتر بمنفذ فيزيائي واحد يوجّه البيانات بين خمس أو أكتر من VLANs مختلفة في نفس الوقت.
</p>

<h3 dir="rtl" align="right" id="vlan-types">🔹 أنواع الـ VLAN</h3>

<ul dir="rtl">
<li><strong>Default VLAN:</strong> الـ VLAN الافتراضي اللي كل منافذ السويتش بتكون عليه من المصنع (غالبًا VLAN 1)، ومش مفضل نستخدمه لنقل بيانات المستخدمين لأسباب أمنية.</li>
<li><strong>Data VLAN:</strong> الـ VLAN المخصص لنقل بيانات المستخدمين العادية (Traffic).</li>
<li><strong>Voice VLAN:</strong> VLAN مخصص لأجهزة الاتصال الصوتي عبر الشبكة (VoIP Phones)، وبيتم فصله عن بيانات المستخدمين العادية عشان يضمن جودة صوت أعلى (QoS).</li>
<li><strong>Management VLAN:</strong> VLAN مخصص لإدارة أجهزة الشبكة نفسها (الوصول لواجهة إدارة السويتش)، ومفضل يتفصل عن باقي الـ VLANs لأسباب أمنية.</li>
<li><strong>Native VLAN:</strong> الـ VLAN اللي بيتم نقل بياناته على وصلة الـ Trunk من غير وضع علامة (Tag) عليه، هنشرحه بالتفصيل في قسم الترانك.</li>
</ul>

<h3 dir="rtl" align="right" id="vlan-port-assignment">🔹 طرق تخصيص منافذ السويتش للـ VLAN</h3>

<p dir="rtl" align="right">
السؤال المهم هنا: السويتش إزاي بيعرف إن المنافذ من 1 لـ 5 مثلاً تابعة لـ VLAN رقم 1، والمنافذ من 6 لـ 11 تابعة لـ VLAN رقم 2، رغم إن كل منفذ منفصل فيزيائيًا عن التاني؟ الإجابة إن السويتش بيحتفظ بجدول داخلي (Configuration Table) بيربط كل رقم منفذ برقم VLAN معين، وده بيتحدد بواحدة من طريقتين:
</p>

<ul dir="rtl">
<li><strong>Static VLAN Assignment (Port-based):</strong> الطريقة الأكتر شيوعًا، فيها المسؤول عن الشبكة بيحدد يدويًا إن المنفذ رقم كذا تابع لـ VLAN رقم كذا، والإعداد ده بيتخزن في ذاكرة السويتش ومش بيتغير إلا لو المسؤول غيّره يدويًا.</li>
<li><strong>Dynamic VLAN Assignment:</strong> الطريقة دي بتحدد الـ VLAN تلقائيًا حسب هوية الجهاز المتصل (زي عنوان الـ MAC بتاعه)، مش حسب رقم المنفذ نفسه، وده بيتم عن طريق خادم مركزي زي الـ VMPS.</li>
</ul>

<h3 dir="rtl" align="right" id="vmps">🔹 الـ VMPS (VLAN Membership Policy Server)</h3>

<p dir="rtl" align="right">
الـ <strong>VMPS</strong> هو خادم مركزي (أو خاصية مدمجة في بعض السويتشات) بيحتفظ بقاعدة بيانات بتربط كل عنوان MAC بـ VLAN معين. لما جهاز جديد يتصل بأي منفذ في السويتش، السويتش بيسأل الـ VMPS "الجهاز صاحب العنوان ده تابع لأنهي VLAN؟"، والـ VMPS بيرد بالإجابة، والسويتش بيخصص المنفذ للـ VLAN ده تلقائيًا. الفايدة الأساسية من الطريقة دي إن الجهاز يقدر يتنقل من منفذ لمنفذ (أو حتى من سويتش لسويتش) ويفضل في نفس الـ VLAN بتاعه تلقائيًا من غير أي إعداد يدوي إضافي، وده مفيد جدًا في البيئات اللي فيها أجهزة متحركة كتير.
</p>

<h3 dir="rtl" align="right" id="vlan-naming">🔹 تسمية الـ VLANs</h3>

<p dir="rtl" align="right">
بالإضافة لرقم الـ VLAN (VLAN ID)، بيتم إعطاء كل VLAN اسمًا وصفيًا (VLAN Name) عشان يسهل على المسؤول فهم الغرض منه بسرعة من غير ما يحتاج يتذكر الأرقام. الأسماء دي غالبًا بترمز لدور الـ VLAN أو القسم اللي بيخدمه، زي مثلاً: <strong>Sales_VLAN</strong>، <strong>HR_VLAN</strong>، <strong>Voice_VLAN</strong>، <strong>Management_VLAN</strong>، <strong>Guest_VLAN</strong>. التسمية الواضحة دي بتساعد كتير في تسهيل عمليات الصيانة واستكشاف الأخطاء (Troubleshooting) في الشبكات الكبيرة اللي فيها عدد كبير من الـ VLANs.
</p>

<h3 dir="rtl" align="right" id="vlan-port-types">🔹 أنواع منافذ الـ VLAN</h3>

<ul dir="rtl">
<li><strong>Access Port:</strong> منفذ مخصص لـ VLAN واحد بس، وبيستخدم للاتصال بالأجهزة النهائية (كمبيوتر، طابعة...إلخ). الجهاز المتصل بالمنفذ ده مش بيعرف أصلاً إن فيه حاجة اسمها VLAN، لأن الفريمات اللي بتوصله بتكون من غير أي علامة (Untagged).</li>
<li><strong>Trunk Port:</strong> منفذ بيقدر ينقل بيانات أكتر من VLAN في نفس الوقت عبر نفس الوصلة الفيزيائية، وبيستخدم للربط بين السويتشات مع بعض، أو بين السويتش والراوتر (في حالة Router-on-a-Stick). هيتشرح بالتفصيل في القسم الجاي (Trunking).</li>
</ul>

<h3 dir="rtl" align="right" id="vlan-id">🔹 الـ VLAN ID</h3>

<p dir="rtl" align="right">
كل VLAN بيتحدد برقم تعريفي فريد (VLAN ID) بيتراوح من <strong>1 إلى 4094</strong> حسب المعيار (802.1Q). بعض الأرقام محجوزة لأغراض خاصة (زي VLAN 1 اللي بيكون الـ Default VLAN، والمدى من 1002-1005 المحجوز تاريخيًا في أجهزة Cisco لبروتوكولات قديمة). الرقم ده هو اللي بيتم وضعه كعلامة (Tag) على الفريم عند مروره على وصلة الـ Trunk، عشان السويتش المستقبِل يعرف الفريم ده تابع لأنهي VLAN.
</p>

---

<h2 dir="rtl" align="right" id="trunking">8️⃣ الترانك (Trunking)</h2>

<h3 dir="rtl" align="right" id="trunking-definition">🔹 تعريف الترانك ووظيفته</h3>

<p dir="rtl" align="right">
<strong>Trunking</strong> هو التقنية اللي بتسمح لوصلة فيزيائية واحدة (Trunk Link) بنقل بيانات أكتر من VLAN في نفس الوقت. من غير الترانك، كنا هنحتاج وصلة فيزيائية منفصلة لكل VLAN بين السويتشات، وده مكلف وغير عملي خالص في الشبكات الكبيرة. الترانك بيحل المشكلة دي عن طريق إضافة علامة (Tag) لكل فريم بتوضح هو تابع لأنهي VLAN، وبكده السويتش المستقبِل يعرف يوجه الفريم للـ VLAN الصحيح رغم إن كل الفريمات جت على نفس الوصلة الفيزيائية.
</p>

<p dir="rtl" align="right">
فيه بروتوكولين رئيسيين بيقوموا بعملية الترانك ووضع العلامات دي:
</p>

<h3 dir="rtl" align="right" id="isl">🔹 بروتوكول ISL (Inter-Switch Link)</h3>

<p dir="rtl" align="right">
بروتوكول <strong>ISL</strong> هو بروتوكول قديم خاص بشركة Cisco (Proprietary)، وطريقة عمله إنه بيقوم بتغليف الفريم بالكامل (Encapsulation) داخل هيدر خاص جديد بيحتوي على رقم الـ VLAN بتاعه، يعني بيضيف هيدر كامل حوالين الفريم الأصلي مش مجرد حقل بسيط جواه.
</p>

<p dir="rtl" align="right">
عيوب بروتوكول ISL:
</p>

<ul dir="rtl">
<li>بروتوكول خاص بشركة Cisco بس (Proprietary)، يعني مش هيشتغل لو كان فيه سويتشات من شركات مختلفة في نفس الشبكة.</li>
<li>بيزود حجم الفريم بشكل أكبر بسبب الهيدر الإضافي الكامل اللي بيتضاف، وده بيستهلك Bandwidth أكتر.</li>
<li>بروتوكول قديم ومهجور تقريبًا لصالح المعيار المفتوح 802.1Q.</li>
</ul>

<h3 dir="rtl" align="right" id="dot1q">🔹 بروتوكول 802.1Q</h3>

<p dir="rtl" align="right">
بروتوكول <strong>802.1Q</strong> هو معيار مفتوح (Open Standard) من IEEE، وطريقة عمله مختلفة عن الـ ISL: بدل ما يغلف الفريم بالكامل بهيدر جديد، بيضيف حقل صغير بس (4 بايت) جوه هيدر الإيثرنت الأصلي نفسه، بيتسمى <strong>Tag</strong>، وبيحمل رقم الـ VLAN ID الخاص بالفريم. الطريقة دي أخف بكتير من ناحية الحجم المُضاف، وبما إنه معيار مفتوح، بيشتغل مع أجهزة أي شركة مصنعة، وده اللي خلاه المعيار السائد حاليًا في كل الشبكات الحديثة تقريبًا.
</p>

<p dir="rtl" align="right">
مميزات بروتوكول 802.1Q:
</p>

<ul dir="rtl">
<li>معيار مفتوح ومدعوم من كل الشركات المصنعة تقريبًا (Cisco, Juniper, HP...إلخ).</li>
<li>حجم إضافي أقل بكتير مقارنة بـ ISL (4 بايت بس بدل هيدر كامل).</li>
<li>بيدعم مفهوم الـ <strong>Native VLAN</strong>: وهو VLAN معين بيتفق عليه طرفي وصلة الترانك، وبياخد معاملة خاصة إنه بيتبعت من غير علامة (Untagged) على الوصلة، وأي فريم بييجي من غير علامة على الترانك بيُفترض تلقائيًا إنه تابع للـ Native VLAN.</li>
</ul>

<h3 dir="rtl" align="right" id="dtp">🔹 بروتوكول DTP (Dynamic Trunking Protocol)</h3>

<p dir="rtl" align="right">
<strong>DTP</strong> هو بروتوكول خاص بشركة Cisco بيسمح لمنفذين متصلين ببعض في سويتشين مختلفين إنهم يتفاوضوا تلقائيًا على تحويل الوصلة بينهم من Access Port لـ Trunk Port من غير تدخل يدوي، بمجرد ما الطرفين يتفقوا إن كل واحد فيهم قادر يشتغل Trunk. الميزة دي مريحة لكنها بتُعتبر ثغرة أمنية لو اتسابت شغالة على منافذ Access العادية، لأن أي جهاز غريب متصل ممكن يحاول يتفاوض على ترقية المنفذ لـ Trunk ويوصل لبيانات كل الـ VLANs (هنشرح الهجوم ده بالتفصيل في قسم <a href="#switching-attacks">هجمات السويتش</a>)، فالممارسة الأمنية السليمة إنك تعطل DTP يدويًا وتحدد نوع المنفذ (Access أو Trunk) بشكل صريح.
</p>

<h3 dir="rtl" align="right" id="vtp">🔹 بروتوكول VTP (VLAN Trunking Protocol)</h3>

<p dir="rtl" align="right">
<strong>VTP</strong> هو بروتوكول خاص بشركة Cisco تاني، لكن وظيفته مختلفة تمامًا عن DTP: بدل ما تدخل وتنشئ نفس الـ VLANs يدويًا على كل سويتش في الشبكة واحد واحد، الـ VTP بيسمح بتوزيع معلومات إنشاء وتعديل وحذف الـ VLANs تلقائيًا من سويتش رئيسي (VTP Server) لباقي السويتشات (VTP Clients) المتصلة على وصلات الترانك، وده بيوفر وقت ومجهود كبير في الشبكات الكبيرة اللي فيها عدد كبير من السويتشات. لازم كل السويتشات المشتركة تكون في نفس الـ VTP Domain عشان تتزامن مع بعضها.
</p>

---

<h2 dir="rtl" align="right" id="switch-hierarchy">9️⃣ تصميم الشبكة الهرمي وأنواع السويتش (Hierarchical Network Design)</h2>

<p dir="rtl" align="right">
دلوقتي وبعد ما فهمنا آلية عمل السويتش والـ VLANs والترانك، نقدر نفهم إزاي الشبكات الكبيرة بتنظم عدد كبير من السويتشات مع بعض. في تصميم الشبكات الكبيرة، بيتم تقسيم السويتشات حسب دورها في الشبكة لثلاث طبقات أساسية:
</p>

<h3 dir="rtl" align="right" id="access-switch">🔹 Access Switch</h3>

<p dir="rtl" align="right">
ده السويتش اللي بيتصل بيه المستخدم النهائي مباشرة (الأجهزة، الطابعات، الهواتف الشبكية...إلخ). بيكون أقرب طبقة للمستخدم، ومسؤول عن توفير الاتصال الفعلي للأجهزة، وغالبًا فيه بيتم تفعيل ميزات زي الـ <strong>Port Security</strong> وتخصيص الـ <strong>VLAN</strong> المناسب لكل منفذ (Access Ports).
</p>

<h3 dir="rtl" align="right" id="distribution-switch">🔹 Distribution Switch</h3>

<p dir="rtl" align="right">
طبقة وسيطة بتجمع بين عدة Access Switches عن طريق وصلات <strong>Trunk</strong>، ومسؤولة عن تطبيق السياسات (Policies) زي الـ <strong>Routing بين الـ VLANs (Inter-VLAN Routing)</strong> اللي شرحناه في قسم Router-on-a-Stick، والـ Access Control Lists (ACLs)، والـ QoS. ده معناها إن الـ Distribution Switch غالبًا بيكون سويتش من نوع Layer 3.
</p>

<h3 dir="rtl" align="right" id="core-switch">🔹 Core Switch</h3>

<p dir="rtl" align="right">
أعلى طبقة في الهيكل الهرمي، ودوره الأساسي هو النقل السريع للبيانات (High-Speed Backbone) بين طبقات الـ Distribution المختلفة. الـ Core Switch مصمم عشان يكون سريع جدًا في التحويل (Switching) وموثوق (High Availability)، وعادة مش بيتعامل مع سياسات معقدة عشان يفضل أسرع ما يمكن. الوصلات بين طبقة الـ Core وطبقة الـ Distribution غالبًا بتستخدم <strong>EtherChannel</strong> عشان توفر أعلى Bandwidth ممكن مع الحفاظ على التوفر العالي.
</p>

<p dir="rtl" align="right">
العناوين اللي بيستخدمها كل مستوى بتختلف حسب دوره: الـ Access بيتعامل غالبًا بعناوين MAC (Layer 2)، بينما الـ Distribution والـ Core بيتعاملوا كمان بعناوين IP (Layer 3) خصوصًا لو بيعملوا Routing بين الشبكات الفرعية.
</p>

---

<h2 dir="rtl" align="right" id="port-security">🔟 أمان منافذ السويتش (Port Security)</h2>

<h3 dir="rtl" align="right" id="switching-attacks">🔹 هجمات شائعة تستهدف السويتش</h3>

<p dir="rtl" align="right">
قبل ما نتكلم عن طرق الحماية، مهم نفهم إيه اللي إحنا بنحمي السويتش منه؛ فيه نوعين رئيسيين من الهجمات اللي بتستهدف طبقة الـ Layer 2:
</p>

<ul dir="rtl">
<li><strong>MAC Flooding / CAM Table Overflow Attack:</strong> المهاجم بيبعت عدد ضخم جدًا من الفريمات بعناوين MAC مصطنعة وعشوائية بشكل متكرر، بهدف إغراق جدول العناوين الفيزيائية (CAM Table) اللي شرحناه في القسم رقم 3 لحد ما يمتلئ بالكامل. لما الجدول يمتلئ، السويتش بيفقد قدرته على التمييز بين الأجهزة، وبيضطر يتصرف زي الـ Hub تمامًا (يعمل Flooding لكل البيانات على كل المنافذ)، وده بيسمح للمهاجم بالتنصت (Sniffing) على بيانات باقي الأجهزة على نفس السويتش.</li>
<li><strong>VLAN Hopping:</strong> هجوم بيهدف لتخطي عزل الـ VLANs والوصول لبيانات VLAN تاني المفروض المهاجم معندوش صلاحية يوصله. بيتم بطريقتين أساسيتين: الأولى <strong>Switch Spoofing</strong> وفيها المهاجم بيخلي جهازه يتظاهر إنه سويتش عن طريق استغلال بروتوكول الـ DTP عشان يقنع السويتش الحقيقي يحول المنفذ لـ Trunk Port، وبكده يوصل لكل الـ VLANs المارة على الترانك. والتانية <strong>Double Tagging</strong> وفيها المهاجم بيبعت فريم بعلامتين (Tags) فوق بعض؛ السويتش الأول بيشيل العلامة الخارجية بس ويمرر الفريم بالعلامة التانية اللي هي فعليًا بتاعة VLAN تاني غير المصرح بيه للمهاجم.</li>
</ul>

<p dir="rtl" align="right">
الحماية من الهجومين دول بتعتمد أساسًا على تفعيل <strong>Port Security</strong> (للحماية من MAC Flooding)، وتعطيل الـ DTP يدويًا وتحديد نوع كل منفذ بشكل صريح (للحماية من VLAN Hopping)، وهو بالظبط اللي هنشرحه في باقي القسم ده.
</p>

<h3 dir="rtl" align="right" id="multiple-devices-port">🔹 ربط أكثر من جهاز بمنفذ واحد</h3>

<p dir="rtl" align="right">
منفذ السويتش الواحد ممكن يخدم أكتر من جهاز في نفس الوقت لو كان متصل بيه جهاز وسيط زي <strong>Hub</strong> قديم، أو <strong>Access Point لاسلكي</strong>، أو <strong>هاتف VoIP</strong> بيه منفذ تمرير إضافي (Pass-through Port) للكمبيوتر. في الحالات دي، السويتش بيتعامل مع كل عنوان MAC مستقل زي أي جهاز عادي على نفس المنفذ، ولازم الأمان يتظبط بحذر عشان ميحصلش استغلال للأمر ده.
</p>

<h3 dir="rtl" align="right" id="dot1x-nac">🔹 حماية 802.1X و NAC</h3>

<p dir="rtl" align="right">
<strong>802.1X</strong> هو بروتوكول مصادقة (Authentication) على مستوى المنفذ، بيمنع أي جهاز من الوصول الكامل للشبكة إلا بعد ما يثبت هويته (عن طريق اسم مستخدم وكلمة سر، أو شهادة رقمية Certificate) لخادم مصادقة مركزي (زي RADIUS Server). لحد ما الجهاز يتم التحقق منه، المنفذ بيفضل مقفول أو بيسمح بمرور بيانات المصادقة بس.
</p>

<p dir="rtl" align="right">
<strong>NAC (Network Access Control)</strong> هو مفهوم أشمل من 802.1X، بيضيف طبقات فحص إضافية قبل السماح للجهاز بالدخول للشبكة، زي التأكد إن الجهاز عليه آخر تحديثات الحماية، وبرنامج مكافحة الفيروسات شغال ومحدث، وإنه ملتزم بسياسات الشركة الأمنية، قبل ما يتم قبوله على الشبكة أو توجيهه لشبكة معزولة (Quarantine VLAN) لحد ما يستوفي الشروط.
</p>

<h3 dir="rtl" align="right" id="port-violation">🔹 إعدادات Port Violation</h3>

<p dir="rtl" align="right">
عند تفعيل خاصية <strong>Port Security</strong> على منفذ معين، بيتم تحديد أقصى عدد من عناوين الـ MAC المسموح بيها على المنفذ (وده بالمناسبة هو الدفاع الأساسي ضد هجوم الـ MAC Flooding اللي شرحناه فوق، لأنه بيمنع المهاجم من إغراق الجدول من الأساس)، ولو حصل تجاوز للعدد ده (يعني جهاز غير مصرح بيه حاول يتصل)، السويتش بياخد أحد ثلاث إجراءات حسب الإعداد المُحدد:
</p>

<ul dir="rtl">
<li><strong>Protect:</strong> يتجاهل الفريمات القادمة من العناوين غير المصرح بيها فقط، من غير أي تسجيل أو إشعار.</li>
<li><strong>Restrict:</strong> نفس تصرف Protect، لكن بيسجل الحدث (Log) ويبعت إشعار (SNMP Trap) للمسؤول.</li>
<li><strong>Shutdown:</strong> يقفل المنفذ بالكامل تلقائيًا (Err-Disabled State) عند حدوث المخالفة، ولازم تدخل يدوي من المسؤول عشان يعيد تفعيل المنفذ من جديد. ده الوضع الافتراضي وأكتر إجراء متشدد.</li>
</ul>

<h3 dir="rtl" align="right" id="port-mac-binding">🔹 طرق ربط المنافذ بالعناوين</h3>

<ul dir="rtl">
<li><strong>Static Secure MAC Addresses:</strong> المسؤول بيدخل عناوين الـ MAC المسموح بيها يدويًا لكل منفذ.</li>
<li><strong>Dynamic Secure MAC Addresses:</strong> السويتش بيتعلم أول عنوان (أو عدد معين من العناوين) يتصل بالمنفذ تلقائيًا، لكن الإعداد ده بيتمسح لو السويتش اتعاد تشغيله (Reboot).</li>
<li><strong>Sticky Secure MAC Addresses:</strong> حل وسط، السويتش بيتعلم العناوين تلقائيًا زي الـ Dynamic، لكن بيحفظها في ملف الإعدادات بشكل دائم (Running/Startup Config)، فمتفضلش لو حصل إعادة تشغيل.</li>
</ul>

---

<h2 dir="rtl" align="right" id="poe">1️⃣1️⃣ تقنية الـ PoE (Power over Ethernet)</h2>

<h3 dir="rtl" align="right" id="poe-definition">🔹 تعريف PoE وعلاقته بالإيثرنت</h3>

<p dir="rtl" align="right">
تقنية <strong>PoE (Power over Ethernet)</strong> بتسمح بنقل الطاقة الكهربائية جنبًا إلى جنب مع بيانات الشبكة عبر نفس كابل الإيثرنت (Cat5e/Cat6)، وده بيلغي الحاجة لتوصيل مصدر طاقة منفصل لكل جهاز. الفايدة الأساسية إنها بتسهل تركيب أجهزة زي كاميرات المراقبة (IP Cameras)، هواتف VoIP، ونقاط الوصول اللاسلكي (Wireless Access Points) في أماكن صعب توصيل كهرباء عادية ليها.
</p>

<h3 dir="rtl" align="right" id="poe-standards">🔹 معايير وطرق تشغيل PoE</h3>

<p dir="rtl" align="right">
فيه أكتر من معيار لتقنية الـ PoE، بيختلفوا في كمية الطاقة اللي بيقدروا يوفروها للجهاز المتصل:
</p>

<table align="center">
<tr><th>المعيار</th><th>الاسم</th><th>أقصى طاقة</th></tr>
<tr><td>802.3af</td><td>PoE</td><td>~15.4 واط</td></tr>
<tr><td>802.3at</td><td>PoE+</td><td>~30 واط</td></tr>
<tr><td>802.3bt</td><td>PoE++ / 4PPoE</td><td>~60-100 واط</td></tr>
</table>

<p dir="rtl" align="right">
عملية توفير الطاقة بتتم بطريقتين رئيسيتين: <strong>Endspan</strong> وفيها السويتش نفسه بيكون فيه دعم مدمج لتوفير الطاقة (PoE Switch)، أو <strong>Midspan</strong> وفيها بيتم استخدام جهاز وسيط (PoE Injector) بين السويتش العادي (اللي مبيدعمش PoE) والجهاز النهائي، عشان يضيف الطاقة على الكابل قبل ما يوصل للجهاز.
</p>

---

<h2 dir="rtl" align="right" id="span-rspan">1️⃣2️⃣ منفذ تحليل البيانات (SPAN / RSPAN)</h2>

<h3 dir="rtl" align="right" id="span">🔹 SPAN (Switched Port Analyzer)</h3>

<p dir="rtl" align="right">
منفذ الـ <strong>SPAN</strong> (وبيتسمى كمان Port Mirroring) هو خاصية بتسمح للمسؤول بعمل نسخة من البيانات المارة على منفذ أو مجموعة منافذ معينة (أو حتى VLAN كامل) وإرسالها لمنفذ آخر مخصص لأغراض المراقبة والتحليل. الفايدة الأساسية إن المسؤول يقدر يوصل جهاز تحليل بروتوكولات (Protocol Analyzer زي Wireshark) على منفذ الـ SPAN ده، ويشوف كل البيانات المارة على المنفذ الأصلي من غير ما يتدخل مباشرة في مسار البيانات الحقيقي أو يأثر على أداء الشبكة.
</p>

<h3 dir="rtl" align="right" id="rspan">🔹 RSPAN (Remote SPAN)</h3>

<p dir="rtl" align="right">
<strong>RSPAN</strong> هو امتداد لخاصية الـ SPAN، بيسمح بنسخ البيانات من منفذ على سويتش معين وإرسالها لمنفذ مراقبة على سويتش <strong>مختلف تمامًا</strong> في مكان تاني من الشبكة، عن طريق تخصيص VLAN خاص بنقل بيانات المراقبة دي عبر الشبكة كلها (RSPAN VLAN). الفايدة الأساسية إنك مش مضطر يكون جهاز المراقبة قريب فيزيائيًا من السويتش اللي عايز تراقبه، ده مفيد جدًا في الشبكات الكبيرة الموزعة على أكتر من مبنى أو طابق.
</p>

</div>
