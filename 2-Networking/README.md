<div dir="rtl">

# 📚 فهرس مواضيع كورس Network+ الشامل

الملف ده هو **الفهرس الرئيسي** لكل مواضيع مادة الـ **CompTIA Network+** الموجودة في فولدر [`Network-Plus`](./Network-Plus/)، وهدفه إنه يجمعلك جدول المحتويات (TOC) بتاع كل موضوع من المواضيع الـ 10 في مكان واحد.

تحت كل عنوان موضوع هتلاقي **الجدول الأصلي بتاعه بالظبط** زي ما هو موجود جوه ملفه، وكل رابط في الجدول بيوديك **على طول للنقطة المطلوبة** جوه الملف من غير ما تفتحه وتدور فيه يدويًا.

---

## 🗂️ الفهرس السريع لكل المواضيع

| # | الموضوع | نبذة عن المحتوى |
|:---:|:---:|:---:|
| 1 | [مقدمة في الشبكات](./Network-Plus/01-Intro-To-Network.md) | تعريف الشبكة، أهدافها ومميزاتها، عناصرها المكوّنة، أنواعها المختلفة، والطوبولوجيا الفيزيائية والمنطقية |
| 2 | [مصطلحات الشبكات الأساسية](./Network-Plus/02-Networking-Terminology.md) | 44 مصطلح شبكات أساسي (Network، Subnet، DHCP، DNS، Firewall...إلخ) مقسّمين حسب التصنيف: بنية وربط، أجهزة، عنونة وبروتوكولات، أمان، وشبكات لاسلكية |
| 3 | [عملي: شبكات الأجهزة الافتراضية](./Network-Plus/03-Lab-VM-Networking.md) | لاب عملي لإنشاء وتوصيل جهازين افتراضيين، تغيير الـ IP يدويًا، وأجزاءه، واختبار الاتصال بأمر Ping |
| 4 | [نموذج الـ OSI Model بالتفصيل](./Network-Plus/04-OSI-Model.md) | خصائص النموذج، شرح كل طبقة من الطبقات السبعة بالتفصيل، الأجهزة المرتبطة بكل طبقة، ومقارنته بنموذج TCP/IP |
| 5 | [أرقام المنافذ والبروتوكولات](./Network-Plus/05-Port-Number.md) | علاقة Port Number بنموذج OSI، نطاق الأرقام وفئاتها الثلاثة، علاقتها بالـ IP (مفهوم Socket) والـ DNS، أداة netstat، أشهر البورتات، والجانب الأمني وطرق الاختراق |
| 6 | [عملي: محاكاة نموذج OSI](./Network-Plus/06-Lab-OSI-Model.md) | لاب عملي شامل: تركيب Web Server عبر IIS، تتبع الاتصالات بـ netstat، الـ 3-Way Handshake، تركيبة الـ MAC Address، بروتوكول ARP، وARP Spoofing |
| 7 | [نموذج TCP/IP ومقارنته بالـ OSI](./Network-Plus/07-TCP-IP-Model.md) | طبقات TCP/IP (القديمة والمحدثة)، مقارنته التفصيلية بـ OSI، البروتوكولات في كل طبقة، الفرق بين TCP وUDP، وعملية الـ Encapsulation/Decapsulation |
| 8 | [الأوساط الفيزيائية وكابلات التوصيل](./Network-Plus/08-Physical-Media.md) | الكابلات المحورية والمجدولة والضوئية والمتسلسلة، لوحة تجميع الكابلات، معايير التسمية والأسلاك المهيكلة (TIA/EIA-568)، وخصائص كابلات الشبكة |
| 9 | [تقنيات الإيثرنت والشبكات المحلية](./Network-Plus/09-Ethernet-LAN.md) | تقنيات Token Ring وARC-Net وEthernet، التحكم في الوصول للوسيط (Collision/Broadcast Domain)، عنونة MAC، صيغة الإطار، وعلاقة الإيثرنت بنموذج OSI |
| 10 | [أجهزة الشبكات](./Network-Plus/10-Networking-Devices.md) | مهايئات الشبكة (NIC، Modem، Transceiver)، الأجهزة الأساسية (Hub/Bridge/Switch/WAP)، أجهزة الربط بين الشبكات (Router/Firewall)، أجهزة إضافية متخصصة، وخدمتا DNS وDHCP |

---

## 1) 📘 [الموضوع الأول: مقدمة في الشبكات](./Network-Plus/01-Intro-To-Network.md)

| المحتويات |
|---:|
| [1. يعني إيه شبكة أصلاً؟ (What is a Network?)](./Network-Plus/01-Intro-To-Network.md#sec-1) |
| [2. أهداف الشبكات (Goals of Networking)](./Network-Plus/01-Intro-To-Network.md#sec-2) |
| [3. مزايا وجود الشبكات (Advantages of Networks)](./Network-Plus/01-Intro-To-Network.md#sec-3) |
| [4. العناصر المكونة للشبكة (Network Components)](./Network-Plus/01-Intro-To-Network.md#sec-4) |
| [5. أنواع الشبكات (Types of Networks)](./Network-Plus/01-Intro-To-Network.md#sec-5) |
| [6. Network Topology (الطوبولوجيا الفيزيائية والمنطقية)](./Network-Plus/01-Intro-To-Network.md#sec-6) |

---

## 2) 📘 [الموضوع الثاني: مصطلحات الشبكات الأساسية](./Network-Plus/02-Networking-Terminology.md)

| الرقم | المصطلح التقني (English) | المفهوم باللغة العربية | التصنيف الأساسي |
| :---: | :--- | :--- | :--- |
| 1 | [Network](./Network-Plus/02-Networking-Terminology.md#1-network-الشبكة) | الشبكة | المفاهيم البنيوية والربط |
| 2 | [Subnet](./Network-Plus/02-Networking-Terminology.md#2-subnet-الشبكة-الفرعية) | الشبكة الفرعية | المفاهيم البنيوية والربط |
| 3 | [Internetwork](./Network-Plus/02-Networking-Terminology.md#3-internetwork-تشبيك-الشبكات-المتعددة) | تشبيك الشبكات المتعددة | المفاهيم البنيوية والربط |
| 4 | [Intranet](./Network-Plus/02-Networking-Terminology.md#4-intranet-الشبكة-الداخلية-المغلقة) | الشبكة الداخلية المغلقة | المفاهيم البنيوية والربط |
| 5 | [Extranet](./Network-Plus/02-Networking-Terminology.md#5-extranet-الشبكة-الخارجية-الممتدة) | الشبكة الخارجية الممتدة | المفاهيم البنيوية والربط |
| 6 | [Internet](./Network-Plus/02-Networking-Terminology.md#6-internet-شبكة-الإنترنت-العالمية) | شبكة الإنترنت العالمية | المفاهيم البنيوية والربط |
| 7 | [ISP (Internet Service Provider)](./Network-Plus/02-Networking-Terminology.md#7-isp-internet-service-provider---مزود-خدمة-الإنترنت) | مزود خدمة الإنترنت | المفاهيم البنيوية والربط |
| 8 | [DMZ (Demilitarized Zone)](./Network-Plus/02-Networking-Terminology.md#8-dmz-demilitarized-zone---المنطقة-منزوعة-السلاح-الأمنية) | المنطقة منزوعة السلاح الأمنية | البنية والأمن |
| 9 | [Workstation](./Network-Plus/02-Networking-Terminology.md#9-workstation-محطة-العمل-المتطورة) | محطة العمل المتطورة | أجهزة وعناصر الشبكة |
| 10 | [Client](./Network-Plus/02-Networking-Terminology.md#10-client-العميل-المستهلك-للخدمة) | العميل المستهلك للخدمة | أجهزة وعناصر الشبكة |
| 11 | [Server](./Network-Plus/02-Networking-Terminology.md#11-server-الخادم--السيرفر-المركزي) | الخادم / السيرفر المركزي | أجهزة وعناصر الشبكة |
| 12 | [Host](./Network-Plus/02-Networking-Terminology.md#12-host-المضيف-الشبكي) | المضيف الشبكي | أجهزة وعناصر الشبكة |
| 13 | [NIC (Network Interface Card)](./Network-Plus/02-Networking-Terminology.md#13-nic-network-interface-card---بطاقة-واجهة-الشبكة) | بطاقة واجهة الشبكة | أجهزة وعناصر الشبكة |
| 14 | [Hub](./Network-Plus/02-Networking-Terminology.md#14-hub-الموزع-التقليدي) | الموزع التقليدي (الغبى) | أجهزة وعناصر الشبكة |
| 15 | [Switch](./Network-Plus/02-Networking-Terminology.md#15-switch-المبدل-الذكي) | المبدل الذكي (السويتش) | أجهزة وعناصر الشبكة |
| 16 | [Router](./Network-Plus/02-Networking-Terminology.md#16-router-الموجه-الشبكي) | الموجه الشبكي (الراوتر) | أجهزة وعناصر الشبكة |
| 17 | [Access Point (AP)](./Network-Plus/02-Networking-Terminology.md#17-access-point-ap---نقطة-الوصول-اللاسلكية) | نقطة الوصول اللاسلكية | أجهزة وعناصر الشبكة |
| 18 | [VLAN (Virtual LAN)](./Network-Plus/02-Networking-Terminology.md#18-vlan-virtual-local-area-network---الشبكة-المحلية-الافتراضية) | الشبكة المحلية الافتراضية | أجهزة وعناصر الشبكة |
| 19 | [MAC Address](./Network-Plus/02-Networking-Terminology.md#19-mac-address-media-access-control---العنوان-الفيزيائي-المادي) | العنوان الفيزيائي والمادي | العنونة والبروتوكولات |
| 20 | [IP Address](./Network-Plus/02-Networking-Terminology.md#20-ip-address-internet-protocol-address---العنوان-المنطقي-الرقمي) | العنوان المنطقي الرقمي | العنونة والبروتوكولات |
| 21 | [Subnet Mask](./Network-Plus/02-Networking-Terminology.md#21-subnet-mask-قناع-الشبكة-الفرعية) | قناع الشبكة الفرعية | العنونة والبروتوكولات |
| 22 | [Host Address](./Network-Plus/02-Networking-Terminology.md#22-host-address-عنوان-المضيف-الخاص) | عنوان المضيف الخاص | العنونة والبروتوكولات |
| 23 | [Port & Port Number](./Network-Plus/02-Networking-Terminology.md#23-port--port-number-المنفذ-والرقم-البرمجي-للمنافذ) | المنفذ والرقم البرمجي | العنونة والبروتوكولات |
| 24 | [DHCP](./Network-Plus/02-Networking-Terminology.md#24-dhcp-dynamic-host-configuration-protocol) | بروتوكول التعيين الديناميكي | العنونة والبروتوكولات |
| 25 | [DNS](./Network-Plus/02-Networking-Terminology.md#25-dns-domain-name-system) | نظام أسماء النطاقات دليلي | العنونة والبروتوكولات |
| 26 | [NAT (Network Address Translation)](./Network-Plus/02-Networking-Terminology.md#26-nat-network-address-translation---ترجمة-وتحويل-العناوين) | ترجمة وتحويل العناوين | العنونة والبروتوكولات |
| 27 | [TCP (Transmission Control Protocol)](./Network-Plus/02-Networking-Terminology.md#27-tcp-transmission-control-protocol---بروتوكول-التحكم-في-النقل) | بروتوكول التحكم في النقل | العنونة والبروتوكولات |
| 28 | [UDP (User Datagram Protocol)](./Network-Plus/02-Networking-Terminology.md#28-udp-user-datagram-protocol---بروتوكول-حزم-بيانات-المستخدم) | بروتوكول حزم بيانات المستخدم | العنونة والبروتوكولات |
| 29 | [Firewall](./Network-Plus/02-Networking-Terminology.md#29-firewall-جدار-الحماية-الأمني-الشامل) | جدار الحماية الأمني | الأمن والشبكات الافتراضية |
| 30 | [VPN (Virtual Private Network)](./Network-Plus/02-Networking-Terminology.md#30-vpn-virtual-private-network---الشبكة-الافتراضية-الخاصة) | الشبكة الافتراضية الخاصة | الأمن والشبكات الافتراضية |
| 31 | [Wireless Networks (Wi-Fi)](./Network-Plus/02-Networking-Terminology.md#31-wireless-networks-الاتصالات-والشبكات-اللاسلكية) | الاتصالات والشبكات اللاسلكية | الأنماط والترددات اللاسلكية |
| 32 | [2.4 GHz vs 5 GHz Frequencies](./Network-Plus/02-Networking-Terminology.md#32-مقارنة-تفصيلية-عميقة-بين-الترددات-اللاسلكية-24-ghz-vs-5-ghz) | مقارنة الترددات اللاسلكية | الأنماط والترددات اللاسلكية |
| 33 | [Transmission Modes](./Network-Plus/02-Networking-Terminology.md#33-transmission-modes-أنماط-تدفق-وقنوات-النقل) | أنماط تدفق وقنوات النقل | طرق وبث البيانات |
| 34 | [Data Casting (Data Delivery)](./Network-Plus/02-Networking-Terminology.md#34-data-casting-modes-طرق-توجيه-وبث-البيانات-وإرسالها) | طرق توجيه وبث البيانات | طرق وبث البيانات |
| 35 | [Framing](./Network-Plus/02-Networking-Terminology.md#35-framing-تأطير-وتغليف-البيانات-في-الطبقة-الثانية) | تأطير وتغليف البيانات | طرق وبث البيانات |
| 36 | [Error Detection & Correction](./Network-Plus/02-Networking-Terminology.md#36-error-detection--correction-كشف-الأخطاء-وتصحيحها) | كشف الأخطاء وتصحيحها | طرق وبث البيانات |
| 37 | [Default Gateway](./Network-Plus/02-Networking-Terminology.md#37-default-gateway-البوابة-الافتراضية) | البوابة الافتراضية | العنونة والبروتوكولات |
| 38 | [Loopback Address](./Network-Plus/02-Networking-Terminology.md#38-loopback-address-عنوان-الاستدعاء-الذاتي) | عنوان الاستدعاء الذاتي | العنونة والبروتوكولات |
| 39 | [APIPA](./Network-Plus/02-Networking-Terminology.md#39-apipa-automatic-private-ip-addressing) | العنونة الذاتية التلقائية | العنونة والبروتوكولات |
| 40 | [CIDR Notation](./Network-Plus/02-Networking-Terminology.md#40-cidr-notation-صيغة-كتابة-الشبكة-المختصرة) | صيغة كتابة الشبكة المختصرة | العنونة والبروتوكولات |
| 41 | [Private IP Ranges](./Network-Plus/02-Networking-Terminology.md#41-private-ip-ranges-نطاقات-العناوين-الخاصة) | نطاقات العناوين الخاصة الكاملة | العنونة والبروتوكولات |
| 42 | [IPv6](./Network-Plus/02-Networking-Terminology.md#42-ipv6-الجيل-السادس-من-بروتوكول-الإنترنت) | الجيل السادس من عناوين الإنترنت | العنونة والبروتوكولات |
| 43 | [MTU](./Network-Plus/02-Networking-Terminology.md#43-mtu-maximum-transmission-unit) | أقصى حجم لوحدة النقل | طرق وبث البيانات |
| 44 | [Bandwidth, Throughput, Latency & Jitter](./Network-Plus/02-Networking-Terminology.md#44-bandwidth-throughput-latency--jitter-مقاييس-أداء-الشبكة) | مقاييس أداء الشبكة | طرق وبث البيانات |

---

## 3) 📘 [الموضوع الثالث: عملي - شبكات الأجهزة الافتراضية](./Network-Plus/03-Lab-VM-Networking.md)

| المحتويات |
|---:|
| [1️⃣ تحميل برنامج المحاكاة (VMware)](./Network-Plus/03-Lab-VM-Networking.md#download-vmware) |
| [2️⃣ إنشاء Virtual Machine — الفرق بين Typical و Custom](./Network-Plus/03-Lab-VM-Networking.md#typical-vs-custom) |
| [3️⃣ إنشاء 2 Virtual Machines](./Network-Plus/03-Lab-VM-Networking.md#create-two-vms) |
| [4️⃣ توصيل الجهازين ببعض (Physical Connection via Virtual Switch)](./Network-Plus/03-Lab-VM-Networking.md#connect-vms-vswitch) |
| [5️⃣ تغيير الـ IP Address يدويًا](./Network-Plus/03-Lab-VM-Networking.md#change-ip-manually) |
| [6️⃣ أجزاء الـ IP Address](./Network-Plus/03-Lab-VM-Networking.md#ip-address-parts) |
| [7️⃣ إيقاف الـ Firewall (جدار الحماية)](./Network-Plus/03-Lab-VM-Networking.md#disable-firewall) |
| [8️⃣ اختبار التوصيل بأمر Ping](./Network-Plus/03-Lab-VM-Networking.md#test-ping) |
| [9️⃣ أوامر تشخيص إضافية مفيدة (Diagnostic Commands)](./Network-Plus/03-Lab-VM-Networking.md#diagnostic-commands) |
| [📝 ملخص اللاب](./Network-Plus/03-Lab-VM-Networking.md#lab-summary) |

---

## 4) 📘 [الموضوع الرابع: نموذج الـ OSI Model بالتفصيل](./Network-Plus/04-OSI-Model.md)

| المحتويات |
|---|
| [مقدمة عن الموضوع](./Network-Plus/04-OSI-Model.md#مقدمة-عن-الموضوع) |
| [خصائص وسمات الـ OSI Model](./Network-Plus/04-OSI-Model.md#خصائص-وسمات-الـ-osi-model) |
| [الطبقات السبعة بالترتيب](./Network-Plus/04-OSI-Model.md#الطبقات-السبعة-بالترتيب) |
| [1) طبقة الـ Application Layer](./Network-Plus/04-OSI-Model.md#1-طبقة-الـ-application-layer-الطبقة-السابعة) |
| [2) طبقة الـ Presentation Layer](./Network-Plus/04-OSI-Model.md#2-طبقة-الـ-presentation-layer-الطبقة-السادسة) |
| [3) طبقة الـ Session Layer](./Network-Plus/04-OSI-Model.md#3-طبقة-الـ-session-layer-الطبقة-الخامسة) |
| [4) طبقة الـ Transport Layer](./Network-Plus/04-OSI-Model.md#4-طبقة-الـ-transport-layer-الطبقة-الرابعة) |
| [5) طبقة الـ Network Layer](./Network-Plus/04-OSI-Model.md#5-طبقة-الـ-network-layer-الطبقة-الثالثة) |
| [6) طبقة الـ Data Link Layer](./Network-Plus/04-OSI-Model.md#6-طبقة-الـ-data-link-layer-الطبقة-الثانية) |
| [7) طبقة الـ Physical Layer](./Network-Plus/04-OSI-Model.md#7-طبقة-الـ-physical-layer-الطبقة-الأولى) |
| [جدول ملخص لكل الطبقات السبعة](./Network-Plus/04-OSI-Model.md#جدول-ملخص-لكل-الطبقات-السبعة-للمراجعة-السريعة) |
| [الأجهزة اللي بتشتغل في كل طبقة](./Network-Plus/04-OSI-Model.md#الأجهزة-اللي-بتشتغل-في-كل-طبقة) |
| [مقارنة سريعة: OSI مقابل TCP/IP](./Network-Plus/04-OSI-Model.md#مقارنة-سريعة-osi-مقابل-tcpip) |
| [طريقة حفظ ترتيب الطبقات (Mnemonic)](./Network-Plus/04-OSI-Model.md#طريقة-حفظ-ترتيب-الطبقات-mnemonic) |
| [خلاصة سريعة](./Network-Plus/04-OSI-Model.md#خلاصة-سريعة) |

---

## 5) 📘 [الموضوع الخامس: أرقام المنافذ والبروتوكولات](./Network-Plus/05-Port-Number.md)

| # | القسم الرئيسي | المواضيع الفرعية |
|:---:|:---:|:---:|
| 1 | [مقدمة عن الموضوع](./Network-Plus/05-Port-Number.md#intro) | [مكان الـ Port Number في نموذج OSI مقارنةً بالطبقات التانية](./Network-Plus/05-Port-Number.md#port-osi-relation) |
| 2 | [نطاق أرقام البورت (Port Number Range)](./Network-Plus/05-Port-Number.md#port-range) | [ليه النطاق بالظبط كده؟](./Network-Plus/05-Port-Number.md#port-range-reason)<br>[مين اللي بيحدد ويوزع الأرقام دي؟ (IANA)](./Network-Plus/05-Port-Number.md#port-range-iana) |
| 3 | [تقسيمات (فئات) أرقام البورت الثلاثة](./Network-Plus/05-Port-Number.md#port-categories) | [System Ports (Well-Known Ports)](./Network-Plus/05-Port-Number.md#system-ports)<br>[User Ports (Registered Ports)](./Network-Plus/05-Port-Number.md#user-ports)<br>[Dynamic/Private Ports (Ephemeral Ports)](./Network-Plus/05-Port-Number.md#dynamic-ports) |
| 4 | [العلاقة بين Port Number و IP Address](./Network-Plus/05-Port-Number.md#ip-port-relation) | [مفهوم الـ Socket](./Network-Plus/05-Port-Number.md#socket-concept) |
| 5 | [العلاقة بين Port Number و DNS](./Network-Plus/05-Port-Number.md#dns-port-relation) | - |
| 6 | [أداة netstat](./Network-Plus/05-Port-Number.md#netstat-tool) | [طريقة الاستخدام](./Network-Plus/05-Port-Number.md#netstat-usage)<br>[مثال عملي شامل](./Network-Plus/05-Port-Number.md#netstat-example) |
| 7 | [جدول أشهر 20 بورت (Common Ports)](./Network-Plus/05-Port-Number.md#common-ports) | [بورتات إضافية مهمة (مكملة للجدول السابق)](./Network-Plus/05-Port-Number.md#additional-ports) |
| 8 | [العلاقة بين نوع البروتوكول (TCP/UDP) واختيار البورت](./Network-Plus/05-Port-Number.md#protocol-port-relation) | - |
| 9 | [دور Port Number في عملية الـ Multiplexing / Demultiplexing](./Network-Plus/05-Port-Number.md#multiplexing-demultiplexing) | [Multiplexing (وقت الإرسال)](./Network-Plus/05-Port-Number.md#multiplexing-send)<br>[Demultiplexing (وقت الاستقبال)](./Network-Plus/05-Port-Number.md#demultiplexing-receive)<br>[إزاي السيرفر مش بيتلخبط بين أكتر من كلاينت على نفس البورت؟](./Network-Plus/05-Port-Number.md#connection-identification) |
| 10 | [الجانب الأمني (Security) المرتبط بأرقام البورت](./Network-Plus/05-Port-Number.md#port-security) | [Port Scanning (فحص المنافذ)](./Network-Plus/05-Port-Number.md#port-scanning)<br>[حالات البورت (Port States)](./Network-Plus/05-Port-Number.md#port-states)<br>[Firewall Rules (قواعد جدار الحماية)](./Network-Plus/05-Port-Number.md#firewall-rules)<br>[بورتات مرتبطة بمخاطر أمنية معروفة](./Network-Plus/05-Port-Number.md#risky-ports)<br>[Port Forwarding (إعادة توجيه المنافذ)](./Network-Plus/05-Port-Number.md#port-forwarding) |
| 11 | [إزاي بيحصل الاختراق من خلال أرقام البورت؟ (نظرة عامة)](./Network-Plus/05-Port-Number.md#hacking-overview) | [اكتشاف البورتات المفتوحة (Discovery)](./Network-Plus/05-Port-Number.md#discovery-phase)<br>[تحديد نوع وإصدار الخدمة (Fingerprinting)](./Network-Plus/05-Port-Number.md#fingerprinting-phase)<br>[البحث عن ثغرات معروفة ومحاولة الاستغلال (Exploitation Attempt)](./Network-Plus/05-Port-Number.md#exploitation-phase) |
| 12 | [خلاصة سريعة](./Network-Plus/05-Port-Number.md#summary) | - |

---

## 6) 📘 [الموضوع السادس: عملي - محاكاة نموذج OSI](./Network-Plus/06-Lab-OSI-Model.md)

| # | الموضوع |
|---|---------|
| 1 | [فكرة اللاب والهدف منه](./Network-Plus/06-Lab-OSI-Model.md#section-1) |
| 2 | [تجهيز البيئة الافتراضية](./Network-Plus/06-Lab-OSI-Model.md#section-2) |
| 3 | [تركيب وتفعيل خدمة الـ Web Server (IIS)](./Network-Plus/06-Lab-OSI-Model.md#section-3) |
| 4 | [إنشاء الـ Website من خلال IIS Manager](./Network-Plus/06-Lab-OSI-Model.md#section-4) |
| 5 | [تفعيل الصفحة الرئيسية (Default Document)](./Network-Plus/06-Lab-OSI-Model.md#section-5) |
| 6 | [اختبار الاتصال من جهاز الـ Client](./Network-Plus/06-Lab-OSI-Model.md#section-6) |
| 7 | [تتبع الاتصالات باستخدام أمر netstat -n](./Network-Plus/06-Lab-OSI-Model.md#section-7) |
| 8 | [أعمق في الـ TCP: الـ 3-Way Handshake](./Network-Plus/06-Lab-OSI-Model.md#section-8) |
| 9 | [أعمق في البورتات: الـ Ephemeral Ports](./Network-Plus/06-Lab-OSI-Model.md#section-9) |
| 10 | [تركيبة الـ MAC Address](./Network-Plus/06-Lab-OSI-Model.md#section-10) |
| 11 | [طرق معرفة الـ MAC Address](./Network-Plus/06-Lab-OSI-Model.md#section-11) |
| 12 | [الـ ARP بالتفصيل الكامل](./Network-Plus/06-Lab-OSI-Model.md#section-12) |
| 13 | [مشكلة عملية: تغيير كارت الشبكة وتأثيره على الـ ARP Cache](./Network-Plus/06-Lab-OSI-Model.md#section-13) |
| 14 | [أوامر ARP: ملخص شامل](./Network-Plus/06-Lab-OSI-Model.md#section-14) |
| 15 | [الجانب الأمني: ARP Spoofing / ARP Poisoning](./Network-Plus/06-Lab-OSI-Model.md#section-15) |
| 16 | [ربط التجربة كلها بطبقات الـ OSI Model](./Network-Plus/06-Lab-OSI-Model.md#section-16) |
| 17 | [جدول تلخيصي شامل للمراجعة](./Network-Plus/06-Lab-OSI-Model.md#section-17) |

---

## 7) 📘 [الموضوع السابع: نموذج الـ TCP/IP ومقارنته بالـ OSI](./Network-Plus/07-TCP-IP-Model.md)

| الرقم | الموضوع |
|---|---|
| 1 | [تعريف نموذج <span dir="ltr">TCP/IP</span> وأشكال استخدامه](./Network-Plus/07-TCP-IP-Model.md#1-تعريف-نموذج-tcpip-وأشكال-استخدامه) |
| 2 | [ليه لسه بندرس <span dir="ltr">OSI Model</span> والشغال فعليًا هو <span dir="ltr">TCP/IP</span>؟](./Network-Plus/07-TCP-IP-Model.md#2-ليه-لسه-بندرس-osi-model-والشغال-فعليا-هو-tcpip) |
| 3 | [النسخة القديمة (4 طبقات) مقابل النسخة المحدثة (5 طبقات)](./Network-Plus/07-TCP-IP-Model.md#3-النسخة-القديمة-4-طبقات-مقابل-النسخة-المحدثة-5-طبقات) |
| 4 | [المقارنة التفصيلية بين <span dir="ltr">OSI</span> و <span dir="ltr">TCP/IP</span>](./Network-Plus/07-TCP-IP-Model.md#4-المقارنة-التفصيلية-بين-osi-و-tcpip) |
| 5 | [وظيفة كل طبقة في نموذج <span dir="ltr">TCP/IP</span>](./Network-Plus/07-TCP-IP-Model.md#5-وظيفة-كل-طبقة-في-نموذج-tcpip) |
| 6 | [أهم البروتوكولات العاملة في كل طبقة](./Network-Plus/07-TCP-IP-Model.md#6-أهم-البروتوكولات-العاملة-في-كل-طبقة) |
| 7 | [الفرق بين <span dir="ltr">TCP</span> و <span dir="ltr">UDP</span>](./Network-Plus/07-TCP-IP-Model.md#7-الفرق-بين-tcp-و-udp) |
| 8 | [المسميات (<span dir="ltr">PDU</span>) وعملية <span dir="ltr">Encapsulation / Decapsulation</span>](./Network-Plus/07-TCP-IP-Model.md#8-المسميات-pdu-وعملية-encapsulation--decapsulation) |
| 9 | [سبب التسمية <span dir="ltr">TCP/IP</span>](./Network-Plus/07-TCP-IP-Model.md#9-سبب-التسمية-tcpip) |
| 10 | [جدول مرجعي: أشهر 20 بورت (مراجعة سريعة)](./Network-Plus/07-TCP-IP-Model.md#10-جدول-مرجعي-أشهر-20-بورت-مراجعة-سريعة) |
| 11 | [كبسولة المذاكرة السريعة](./Network-Plus/07-TCP-IP-Model.md#11-كبسولة-المذاكرة-السريعة) |

---

## 8) 📘 [الموضوع الثامن: الأوساط الفيزيائية وكابلات التوصيل](./Network-Plus/08-Physical-Media.md)

| القسم الرئيسي | المواضيع الفرعية |
| :--- | :--- |
| **[مقدمة](./Network-Plus/08-Physical-Media.md#intro)** | - |
| **[أولاً: الكابلات المحورية](./Network-Plus/08-Physical-Media.md#coaxial)** | • [تعريف الكابل المحوري](./Network-Plus/08-Physical-Media.md#coaxial-def)<br>• [مكونات الكابل المحوري](./Network-Plus/08-Physical-Media.md#coaxial-components)<br>• [الأنواع الرئيسية: Thick و Thin](./Network-Plus/08-Physical-Media.md#coaxial-types)<br>• [معايير RG للكابلات المحورية](./Network-Plus/08-Physical-Media.md#coaxial-rg)<br>• [موصلات الكابل المحوري](./Network-Plus/08-Physical-Media.md#coaxial-connectors) |
| **[ثانياً: الكابلات المجدولة](./Network-Plus/08-Physical-Media.md#twisted-pair)** | • [تعريف الكابل المجدول](./Network-Plus/08-Physical-Media.md#twisted-pair-def)<br>• [مكانة الكابل المجدول في الشبكات](./Network-Plus/08-Physical-Media.md#twisted-pair-status)<br>• [مكونات الكابل المجدول](./Network-Plus/08-Physical-Media.md#twisted-pair-components)<br>• [ترتيب الألوان (T568A / T568B)](./Network-Plus/08-Physical-Media.md#color-order)<br>• [أنماط توصيل الكابل: Straight / Crossover / Rollover](./Network-Plus/08-Physical-Media.md#cable-patterns)<br>• [أنواع الكابل المجدول من ناحية التغليف: UTP و STP](./Network-Plus/08-Physical-Media.md#utp-stp)<br>• [أطراف رؤوس الكابل المجدول](./Network-Plus/08-Physical-Media.md#twisted-pair-connectors)<br>• [فئات الكابلات المجدولة (Cat)](./Network-Plus/08-Physical-Media.md#cable-categories)<br>• [التغذية الكهربائية عبر الكابل PoE](./Network-Plus/08-Physical-Media.md#poe) |
| **[ثالثاً: كابلات الألياف الضوئية](./Network-Plus/08-Physical-Media.md#fiber)** | • [تعريف كابل الألياف الضوئية واستخداماته](./Network-Plus/08-Physical-Media.md#fiber-def)<br>• [مكونات كابل الألياف الضوئية](./Network-Plus/08-Physical-Media.md#fiber-components)<br>• [أقسام تصنيع الألياف الضوئية: Single-mode و Multi-mode](./Network-Plus/08-Physical-Media.md#fiber-modes)<br>• [أطوال الموجة الضوئية المستخدمة](./Network-Plus/08-Physical-Media.md#fiber-wavelengths)<br>• [أطراف رؤوس كابلات الألياف الضوئية](./Network-Plus/08-Physical-Media.md#fiber-connectors)<br>• [منافذ الكابلات الضوئية](./Network-Plus/08-Physical-Media.md#fiber-ports)<br>• [تقنيات WDM / CWDM / DWDM](./Network-Plus/08-Physical-Media.md#fiber-wdm)<br>• [مميزات وعيوب الألياف الضوئية](./Network-Plus/08-Physical-Media.md#fiber-pros-cons) |
| **[رابعاً: الكابلات المتسلسلة ومنافذها](./Network-Plus/08-Physical-Media.md#serial)** | • [تعريف الكابل المتسلسل واستخدامه](./Network-Plus/08-Physical-Media.md#serial-def)<br>• [الـ DTE والـ DCE](./Network-Plus/08-Physical-Media.md#dte-dce)<br>• [طريقة التوصيل بالأجهزة](./Network-Plus/08-Physical-Media.md#serial-connection) |
| **[خامساً: لوحة تجميع الكابلات](./Network-Plus/08-Physical-Media.md#patch-panel)** | • [تعريفها وأنواعها](./Network-Plus/08-Physical-Media.md#patch-panel-types) |
| **[سادساً: معايير تسمية الإيثرنت](./Network-Plus/08-Physical-Media.md#ethernet-naming)** | - |
| **[سابعاً: معيار الأسلاك المهيكلة TIA/EIA-568](./Network-Plus/08-Physical-Media.md#structured-cabling)** | - |
| **[ثامناً: خصائص كابلات الشبكة](./Network-Plus/08-Physical-Media.md#cable-properties)** | • [سرعة النقل والمسافة](./Network-Plus/08-Physical-Media.md#speed-distance)<br>• [مشاكل الكابلات الشائعة](./Network-Plus/08-Physical-Media.md#cable-problems)<br>• [اتجاه الإرسال: Simplex / Half Duplex / Full Duplex](./Network-Plus/08-Physical-Media.md#duplex-modes) |
| **[ملخص شامل للمقارنة بين كل الكابلات](./Network-Plus/08-Physical-Media.md#summary-table)** | - |

---

## 9) 📘 [الموضوع التاسع: تقنيات الإيثرنت والشبكات المحلية](./Network-Plus/09-Ethernet-LAN.md)

| # | القسم الرئيسي | المواضيع الفرعية |
|:---:|:---:|:---:|
| 1 | [مقدمة عن الموضوع](./Network-Plus/09-Ethernet-LAN.md#intro) | - |
| 2 | [التقنيات الثلاث المستخدمة في الشبكات المحلية](./Network-Plus/09-Ethernet-LAN.md#lan-technologies) | - |
| 3 | [أولاً: تقنية Token Ring](./Network-Plus/09-Ethernet-LAN.md#token-ring) | [جهاز الـ MAU: الاستخدام وطريقة العمل](./Network-Plus/09-Ethernet-LAN.md#token-ring-mau) |
| 4 | [خاصية Token Passing و Ring Topology](./Network-Plus/09-Ethernet-LAN.md#token-passing) | - |
| 5 | [ثانياً: تقنية ARC-Net](./Network-Plus/09-Ethernet-LAN.md#arcnet) | - |
| 6 | [ثالثاً: تقنية Ethernet](./Network-Plus/09-Ethernet-LAN.md#ethernet) | [المعايير، نظام التسمية، والسرعات](./Network-Plus/09-Ethernet-LAN.md#ethernet-standards-speeds)<br>&nbsp;&nbsp;&nbsp;[معايير IEEE 802.3 وتطورها التاريخي](./Network-Plus/09-Ethernet-LAN.md#ethernet-standards-history)<br>&nbsp;&nbsp;&nbsp;[نظام تسمية معايير الإيثرنت](./Network-Plus/09-Ethernet-LAN.md#ethernet-naming-convention)<br>&nbsp;&nbsp;&nbsp;[تطور سرعات الإيثرنت عبر الزمن](./Network-Plus/09-Ethernet-LAN.md#ethernet-speed-evolution)<br>[التحكم في الوصول للوسيط: مجالات التصادم والبث ووضعا الإرسال](./Network-Plus/09-Ethernet-LAN.md#ethernet-media-access)<br>&nbsp;&nbsp;&nbsp;[مجالا التصادم والبث](./Network-Plus/09-Ethernet-LAN.md#ethernet-collision-broadcast-domains)<br>&nbsp;&nbsp;&nbsp;[وضعا الإرسال وآلية CSMA/CD](./Network-Plus/09-Ethernet-LAN.md#ethernet-duplex-csmacd)<br>[الطوبولوجيا ومهام الإيثرنت الأساسية](./Network-Plus/09-Ethernet-LAN.md#ethernet-topology-tasks)<br>[عنوان الإيثرنت (MAC Address)](./Network-Plus/09-Ethernet-LAN.md#ethernet-mac-address)<br>[صيغة إطار الإيثرنت (Ethernet Frame Format)](./Network-Plus/09-Ethernet-LAN.md#ethernet-frame-format)<br>[تقنيات وبروتوكولات مكمّلة للإيثرنت](./Network-Plus/09-Ethernet-LAN.md#ethernet-related-protocols)<br>&nbsp;&nbsp;&nbsp;[تجميع الروابط (Channel Bonding)](./Network-Plus/09-Ethernet-LAN.md#ethernet-channel-bonding)<br>&nbsp;&nbsp;&nbsp;[بروتوكول ARP](./Network-Plus/09-Ethernet-LAN.md#ethernet-arp)<br>&nbsp;&nbsp;&nbsp;[تقنية PoE](./Network-Plus/09-Ethernet-LAN.md#ethernet-poe)<br>[علاقة الإيثرنت بنموذج OSI والفروق المفاهيمية المهمة](./Network-Plus/09-Ethernet-LAN.md#ethernet-osi-concepts) |
| 7 | [مقارنة سريعة بين التقنيات الثلاث](./Network-Plus/09-Ethernet-LAN.md#lan-tech-comparison) | - |
| 8 | [جدول ملخص شامل للمراجعة السريعة](./Network-Plus/09-Ethernet-LAN.md#summary-table) | - |

---

## 10) 📘 [الموضوع العاشر: أجهزة الشبكات](./Network-Plus/10-Networking-Devices.md)

| # | القسم الرئيسي | المواضيع الفرعية |
|:---:|:---:|:---:|
| 1 | [مقدمة عن الموضوع](./Network-Plus/10-Networking-Devices.md#intro) | - |
| 2 | [أولاً: مهايئات الشبكة (Network Adapters)](./Network-Plus/10-Networking-Devices.md#adapters) | [كرت الشبكة (NIC)](./Network-Plus/10-Networking-Devices.md#nic)<br>[المودم (Modem) وتقنية ADSL](./Network-Plus/10-Networking-Devices.md#modem-adsl)<br>&nbsp;&nbsp;&nbsp;[تقنية ADSL](./Network-Plus/10-Networking-Devices.md#adsl-technology)<br>[مجمّع خطوط المشتركين الرقمية (DSLAM)](./Network-Plus/10-Networking-Devices.md#dslam)<br>[الـ Transceiver: الأشكال والأنواع (SFP و XFP)](./Network-Plus/10-Networking-Devices.md#transceiver)<br>[محول الوسائط (Media Converter)](./Network-Plus/10-Networking-Devices.md#media-converter)<br>[الموصلات ومقاومات الإنهاء (Connectors و Terminators)](./Network-Plus/10-Networking-Devices.md#connectors-terminators) |
| 3 | [ثانياً: أجهزة الشبكة الأساسية (Network Devices)](./Network-Plus/10-Networking-Devices.md#network-devices) | [Hub](./Network-Plus/10-Networking-Devices.md#hub)<br>[Bridge](./Network-Plus/10-Networking-Devices.md#bridge)<br>[Switch](./Network-Plus/10-Networking-Devices.md#switch)<br>&nbsp;&nbsp;&nbsp;[طرق التحويل الداخلية (Switching Modes)](./Network-Plus/10-Networking-Devices.md#switch-modes)<br>[نقطة الوصول اللاسلكية (WAP) وطرق التنافس (Contention Methods)](./Network-Plus/10-Networking-Devices.md#wap-contention)<br>&nbsp;&nbsp;&nbsp;[طرق التنافس على الوسيط](./Network-Plus/10-Networking-Devices.md#wap-contention-methods) |
| 4 | [ثالثاً: أجهزة الربط بين الشبكات (Internetwork Devices)](./Network-Plus/10-Networking-Devices.md#internetwork-devices) | [الراوتر (Router)](./Network-Plus/10-Networking-Devices.md#router)<br>&nbsp;&nbsp;&nbsp;[عملية الـ Forwarding بالتفصيل](./Network-Plus/10-Networking-Devices.md#router-forwarding-process)<br>[جدار الحماية (Firewall)](./Network-Plus/10-Networking-Devices.md#firewall)<br>[السويتش متعدد الطبقات (Multilayer Switch)](./Network-Plus/10-Networking-Devices.md#multilayer-switch) |
| 5 | [رابعاً: أجهزة وخدمات إضافية في الشبكة](./Network-Plus/10-Networking-Devices.md#other-devices) | [Repeater](./Network-Plus/10-Networking-Devices.md#repeater)<br>[IDS و IPS](./Network-Plus/10-Networking-Devices.md#ids-ips)<br>[CSU/DSU](./Network-Plus/10-Networking-Devices.md#csu-dsu)<br>[السيرفر (Server)](./Network-Plus/10-Networking-Devices.md#server)<br>[موسّع المدى اللاسلكي (Wireless Range Extender)](./Network-Plus/10-Networking-Devices.md#range-extender)<br>[موزّع الأحمال (Load Balancer)](./Network-Plus/10-Networking-Devices.md#load-balancer)<br>[مُركّز الـ VPN (VPN Concentrator)](./Network-Plus/10-Networking-Devices.md#vpn-concentrator)<br>[فلتر المحتوى ومُشكّل الحزم (Content Filter و Packet Shaper)](./Network-Plus/10-Networking-Devices.md#content-filter-shaper)<br>[أجهزة الـ VoIP: Endpoint، PBX، وGateway](./Network-Plus/10-Networking-Devices.md#voip-devices)<br>[السيرفر الوسيط (Proxy Server)](./Network-Plus/10-Networking-Devices.md#proxy-server) |
| 6 | [خامساً: خدمتا DNS و DHCP](./Network-Plus/10-Networking-Devices.md#dns-dhcp) | [خدمة DNS](./Network-Plus/10-Networking-Devices.md#dns)<br>&nbsp;&nbsp;&nbsp;[أنواع سجلات الـ DNS](./Network-Plus/10-Networking-Devices.md#dns-records)<br>&nbsp;&nbsp;&nbsp;[الداخلي مقابل الخارجي](./Network-Plus/10-Networking-Devices.md#dns-internal-external)<br>&nbsp;&nbsp;&nbsp;[الاستضافة عند طرف ثالث](./Network-Plus/10-Networking-Devices.md#dns-third-party)<br>&nbsp;&nbsp;&nbsp;[التسلسل الهرمي](./Network-Plus/10-Networking-Devices.md#dns-hierarchy)<br>&nbsp;&nbsp;&nbsp;[منطقة التوجيه مقابل العكس](./Network-Plus/10-Networking-Devices.md#dns-zones)<br>[خدمة DHCP وعملية DORA](./Network-Plus/10-Networking-Devices.md#dhcp)<br>&nbsp;&nbsp;&nbsp;[عملية DORA بالتفصيل](./Network-Plus/10-Networking-Devices.md#dhcp-dora)<br>&nbsp;&nbsp;&nbsp;[إعدادات إدارة الـ DHCP](./Network-Plus/10-Networking-Devices.md#dhcp-management) |
| 7 | [مقارنة شاملة بين كل الأجهزة](./Network-Plus/10-Networking-Devices.md#devices-comparison) | - |
| 8 | [البروتوكولات المستخدمة في كل جهاز](./Network-Plus/10-Networking-Devices.md#devices-protocols) | - |
| 9 | [جدول ملخص شامل للمراجعة السريعة](./Network-Plus/10-Networking-Devices.md#summary-table) | - |

---

</div>
