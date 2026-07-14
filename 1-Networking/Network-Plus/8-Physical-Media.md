<div align="center">

# <span dir="ltr">Physical Media</span> - الربط الفيزيائي

</div>

<div dir="rtl">

| القسم الرئيسي | المواضيع الفرعية |
| :--- | :--- |
| **[مقدمة](#intro)** | - |
| **[أولاً: الكابلات المحورية](#coaxial)** | • [تعريف الكابل المحوري](#coaxial-def)<br>• [مكونات الكابل المحوري](#coaxial-components)<br>• [الأنواع الرئيسية: Thick و Thin](#coaxial-types)<br>• [معايير RG للكابلات المحورية](#coaxial-rg)<br>• [موصلات الكابل المحوري](#coaxial-connectors) |
| **[ثانياً: الكابلات المجدولة](#twisted-pair)** | • [تعريف الكابل المجدول](#twisted-pair-def)<br>• [مكانة الكابل المجدول في الشبكات](#twisted-pair-status)<br>• [مكونات الكابل المجدول](#twisted-pair-components)<br>• [ترتيب الألوان (T568A / T568B)](#color-order)<br>• [أنماط توصيل الكابل: Straight / Crossover / Rollover](#cable-patterns)<br>• [أنواع الكابل المجدول من ناحية التغليف: UTP و STP](#utp-stp)<br>• [أطراف رؤوس الكابل المجدول](#twisted-pair-connectors)<br>• [فئات الكابلات المجدولة (Cat)](#cable-categories) |
| **[ثالثاً: كابلات الألياف الضوئية](#fiber)** | • [تعريف كابل الألياف الضوئية واستخداماته](#fiber-def)<br>• [مكونات كابل الألياف الضوئية](#fiber-components)<br>• [أقسام تصنيع الألياف الضوئية: Single-mode و Multi-mode](#fiber-modes)<br>• [أطراف رؤوس كابلات الألياف الضوئية](#fiber-connectors)<br>• [منافذ الكابلات الضوئية](#fiber-ports)<br>• [مميزات وعيوب الألياف الضوئية](#fiber-pros-cons) |
| **[رابعاً: الكابلات المتسلسلة ومنافذها](#serial)** | • [تعريف الكابل المتسلسل واستخدامه](#serial-def)<br>• [الـ DTE والـ DCE](#dte-dce)<br>• [طريقة التوصيل بالأجهزة](#serial-connection) |
| **[خامساً: لوحة تجميع الكابلات](#patch-panel)** | • [تعريفها وأنواعها](#patch-panel-types) |
| **[سادساً: خصائص كابلات الشبكة](#cable-properties)** | • [سرعة النقل والمسافة](#speed-distance)<br>• [اتجاه الإرسال: Simplex / Half Duplex / Full Duplex](#duplex-modes) |
| **[ملخص شامل للمقارنة بين كل الكابلات](#summary-table)** | - |

<h2 id="intro" dir="rtl" align="right">مقدمة</h2>

الموضوع ده بيتكلم عن الطبقة الفيزيائية <span dir="ltr">(Physical Layer)</span> في نموذج <span dir="ltr">OSI</span>، وتحديدًا وسائط النقل <span dir="ltr">(Physical Media)</span> اللي بتوصل الأجهزة ببعضها في الشبكة. الوسائط دي بتتقسم بشكل أساسي لـ 3 أنواع رئيسية من الكابلات، بالإضافة لكابلات التوصيل الإداري والتحكم:

1. الكابلات المحورية <span dir="ltr">Coaxial Cable</span>
2. الكابلات المجدولة <span dir="ltr">Twisted Pair</span>
3. كابلات الألياف الضوئية <span dir="ltr">Fiber Optic</span>
4. الكابلات المتسلسلة <span dir="ltr">Serial Cables</span> (للتحكم والإدارة)

فهم الفرق بين كل نوع، ومميزاته وعيوبه، ومتى بيتستخدم، هو أساس أي حد بيدخل مجال الشبكات أو الأمن السيبراني، لأن أي هجوم فيزيائي على الشبكة (زي الـ <span dir="ltr">Wiretapping</span> أو التنصت على الكابل) بيعتمد على فهمك لطبيعة الوسيط نفسه.

<div align="center">
<img src="images/8-1-intro-physical-media.png" width="600">
<br>
<em>الأنواع الثلاثة الأساسية لوسائط الربط الفيزيائي</em>
</div>

---

<h2 id="coaxial" dir="rtl" align="right">أولاً: الكابلات المحورية <span dir="ltr">Coaxial Cable</span></h2>

<h3 id="coaxial-def" dir="rtl" align="right">تعريف الكابل المحوري</h3>

الكابل المحوري هو كابل نحاسي قديم نسبيًا كان بيُستخدم كوسيط أساسي لنقل البيانات في الشبكات القديمة، وحاليًا بقى استخدامه الأساسي في نقل إشارات التلفزيون <span dir="ltr">(Cable TV)</span> والإنترنت من مزودي الخدمة <span dir="ltr">(ISP)</span> عن طريق تقنية <span dir="ltr">DOCSIS</span>، وكمان في أنظمة المراقبة <span dir="ltr">(CCTV)</span> القديمة.

سُمي "محوري" لأنه بيتكون من موصل مركزي واحد <span dir="ltr">(core)</span> محاط بطبقات تانية تلف حوله في نفس المحور <span dir="ltr">(axis)</span>.

<div align="center">
<img src="images/8-2-coaxial-cable-intro.png" width="550">
<br>
<em>الكابل المحوري ومكوناته الأساسية</em>
</div>

<h3 id="coaxial-components" dir="rtl" align="right">مكونات الكابل المحوري</h3>

الكابل المحوري بيتكون من 4 طبقات أساسية من الداخل للخارج:

| الطبقة | الاسم بالإنجليزي | الوظيفة |
|:---:|:---:|:---:|
| اللب المركزي | <span dir="ltr">Core / Conductor</span> | سلك نحاسي مصمت أو مجدول، هو المسؤول عن نقل الإشارة الكهربائية فعليًا |
| العازل | <span dir="ltr">Dielectric Insulator</span> | طبقة بلاستيكية بتعزل الـ Core عن الحماية المعدنية وتمنع التماس |
| الحماية المعدنية | <span dir="ltr">Metallic Shield / Braiding</span> | شبكة معدنية مجدولة أو ورقة ألومنيوم بتحمي الإشارة من التداخل الكهرومغناطيسي <span dir="ltr">(EMI)</span> |
| الغلاف الخارجي | <span dir="ltr">Outer Jacket</span> | طبقة بلاستيكية خارجية بتحمي الكابل من العوامل الخارجية (رطوبة، احتكاك) |

<div align="center">
<img src="images/8-2b-coaxial-cable-cutaway.svg" width="450">
<br>
<em>مقطع عرضي يوضح طبقات الكابل المحوري</em>
</div>

💡 **ملاحظة أمنية**: طبقة الـ <span dir="ltr">Shield</span> مش بس بتمنع التداخل، لكن كمان بتقلل من إمكانية تسريب الإشارة للخارج (اللي ممكن يُستغل في هجمات التنصت الفيزيائي)، وده سبب من أسباب تفضيل الكابل المحوري على الكابل المجدول العادي في بيئات معينة قديمًا.

<h3 id="coaxial-types" dir="rtl" align="right">الأنواع الرئيسية: <span dir="ltr">Thick</span> و <span dir="ltr">Thin</span></h3>

**أ- <span dir="ltr">Thick Coaxial (10Base5)</span>**
- كابل سميك وصلب (قطره حوالي 10 مم)، صعب التمديد والانحناء.
- بيدعم مسافات أطول تصل لحوالي 500 متر بدون تكرار للإشارة.
- كان بيُستخدم كـ "العمود الفقري" <span dir="ltr">(Backbone)</span> في الشبكات الكبيرة، وبيتم توصيل الأجهزة بيه عن طريق وحدة تسمى <span dir="ltr">Vampire Tap</span> أو <span dir="ltr">Transceiver</span>.
- معروف كمان باسم <span dir="ltr">"Frozen Yellow Garden Hose"</span> بسبب لونه الأصفر وصلابته.

**ب- <span dir="ltr">Thin Coaxial (10Base2)</span>**
- كابل أرفع وأسهل في التمديد، أرخص من النوع السميك.
- المسافة القصوى أقل، حوالي 185 متر لكل قطعة.
- بيتم توصيله مباشرة بكارت الشبكة عن طريق موصل <span dir="ltr">BNC</span> على شكل حرف <span dir="ltr">T</span>، وبيحتاج مقاومة ختامية <span dir="ltr">(Terminator)</span> في نهاية كل طرف من الشبكة عشان يمنع ارتداد الإشارة.
- كان بيُستخدم في شبكات <span dir="ltr">Bus Topology</span> الصغيرة.

 فيه كمان تصنيف تاني للكابل المحوري حسب مكان التركيب: <span dir="ltr">Plenum</span> (غلافه مقاوم للحريق ومسموح تمديده في فتحات التكييف بالأسقف) و <span dir="ltr">Non-Plenum</span> (غلاف عادي PVC، أرخص لكن ممنوع استخدامه في أماكن التهوية لأنه بيطلق غازات سامة عند الاحتراق).

<h3 id="coaxial-rg" dir="rtl" align="right">معايير <span dir="ltr">RG</span> للكابلات المحورية</h3>

<span dir="ltr">RG</span> اختصار لـ <span dir="ltr">Radio Guide</span>، وهي معايير بتحدد سُمك ومواصفات الكابل المحوري ومقاومته الكهربائية <span dir="ltr">(Impedance)</span>. أشهر الأنواع:

| المعيار | الاسم الشائع | المقاومة | الاستخدام |
|:---:|:---:|:---:|:---:|
| <span dir="ltr">RG-6</span> | - | 75 أوم | كابلات التلفزيون والإنترنت من مزودي الخدمة، مسافات أطول من RG-59 |
| <span dir="ltr">RG-59</span> | - | 75 أوم | كابلات <span dir="ltr">CCTV</span> ونقل الفيديو التناظري لمسافات قصيرة |
| <span dir="ltr">RG-58 A/U</span> | <span dir="ltr">Thinnet</span> | 50 أوم | شبكات <span dir="ltr">10Base2</span> |
| <span dir="ltr">RG-8</span> | <span dir="ltr">Thicknet</span> | 50 أوم | شبكات <span dir="ltr">10Base5</span> |
| <span dir="ltr">RG-62</span> | - | 93 أوم | شبكات <span dir="ltr">ARCnet</span> (قديمة جدًا) |

 الفرق الأساسي بين معايير الـ 50 أوم ومعايير الـ 75 أوم إن الأولى صُممت أصلًا لنقل بيانات الشبكات (إشارة رقمية)، والتانية صُممت لنقل إشارات الفيديو والتلفزيون (إشارة تناظرية عالية التردد).

<div align="center">
<img src="images/8-3-coaxial-rg-standards-table.png" width="600">
<br>
<em>جدول معايير RG واستخداماتها</em>
</div>

<div align="center">
<img src="images/8-4-coaxial-rg-cable-types.png" width="500">
<br>
<em>مقارنة فيزيائية بين RG-58 و RG-8X و RG-8U</em>
</div>

<h3 id="coaxial-connectors" dir="rtl" align="right">موصلات الكابل المحوري</h3>

- **<span dir="ltr">BNC (Bayonet Neill-Concelman)</span>**: موصل بيتقفل بحركة لف وقفل سريع (ربع لفة)، بيُستخدم مع الكابل الرفيع <span dir="ltr">(Thin Coax)</span> وفي أجهزة القياس والـ <span dir="ltr">CCTV</span> القديمة.
- **<span dir="ltr">F-Connector</span>**: موصل بيتلف زي البرغي، وهو الأشهر حاليًا لأنه بيُستخدم في كابلات الـ <span dir="ltr">RG-6</span> لتوصيل التلفزيون والراوتر بخدمة الإنترنت الكابلي.
- **<span dir="ltr">N-Connector</span>**: موصل أكبر حجمًا وأقوى، بيُستخدم في التطبيقات الصناعية وأنظمة الاتصالات اللاسلكية عالية القدرة.
- **<span dir="ltr">Terminator</span>**: مش موصل توصيل فعلي، لكنه مقاومة بتتركب في آخر الكابل في شبكات الـ <span dir="ltr">Bus Topology</span> عشان تمتص الإشارة وتمنع ارتدادها.

---

<h2 id="twisted-pair" dir="rtl" align="right">ثانياً: الكابلات المجدولة <span dir="ltr">Twisted Pair</span></h2>

<h3 id="twisted-pair-def" dir="rtl" align="right">تعريف الكابل المجدول</h3>

الكابل المجدول هو نوع من كابلات النحاس بيتكون من أزواج من الأسلاك ملفوفة حوالين بعضها (كل زوج بيتلف حوالين نفسه بعدد لفات مختلف عن باقي الأزواج). فكرة اللف دي مش شكلية، لكنها بتقلل من التداخل الكهرومغناطيسي بين الأزواج نفسها <span dir="ltr">(Crosstalk)</span> ومن التداخل الخارجي <span dir="ltr">(EMI)</span>.

<div align="center">
<img src="images/8-5-utp-cable-definition.png" width="500">
<br>
<em>الكابل المجدول غير المحمي UTP</em>
</div>

<h3 id="twisted-pair-status" dir="rtl" align="right">مكانة الكابل المجدول في عالم الشبكات</h3>

الكابل المجدول هو **الوسيط الأكثر انتشارًا** في شبكات الـ <span dir="ltr">LAN</span> حاليًا، بسبب سهولة تركيبه، رخص تكلفته مقارنة بالألياف الضوئية، وكفايته لمعظم استخدامات الشبكات المحلية. بيُستخدم في توصيل الأجهزة بالـ <span dir="ltr">Switch</span>، وفي البنية التحتية لمعظم المكاتب والمنازل.

<h3 id="twisted-pair-components" dir="rtl" align="right">مكونات الكابل المجدول</h3>

- **الأسلاك النحاسية**: 8 أسلاك مقسمة لـ 4 أزواج <span dir="ltr">(pairs)</span>، كل زوج ملفوف حوالين بعضه.
- **العزل الفردي**: كل سلك مغطى بطبقة عزل ملونة تميزه.
- **طبقة الحماية (اختيارية)**: موجودة بس في النوع المحمي <span dir="ltr">STP</span>.
- **الغلاف الخارجي**: بيحمي كل الأزواج الأربعة سوا.

<div align="center">
<img src="images/8-6-utp-cable-pairs-photo.png" width="450">
<br>
<em>الأزواج الأربعة داخل الكابل المجدول وألوانها (أخضر / أزرق / برتقالي / بني)</em>
</div>

<h3 id="color-order" dir="rtl" align="right">ترتيب الألوان <span dir="ltr">(T568A / T568B)</span></h3>

فيه معياريين عالميين لترتيب ألوان الأسلاك الثمانية جوه موصل الـ <span dir="ltr">RJ-45</span>، وهما <span dir="ltr">T568A</span> و <span dir="ltr">T568B</span>. الاختلاف بينهم بس في مكان زوجي الألوان الأخضر والبرتقالي، وباقي الترتيب زي بعضه.

**ترتيب <span dir="ltr">T568A</span>** (من الطرف 1 للطرف 8):
أبيض/أخضر، أخضر، أبيض/برتقالي، أزرق، أبيض/أزرق، برتقالي، أبيض/بني، بني

**ترتيب <span dir="ltr">T568B</span>** (من الطرف 1 للطرف 8):
أبيض/برتقالي، برتقالي، أبيض/أخضر، أزرق، أبيض/أزرق، أخضر، أبيض/بني، بني

<span dir="ltr">T568B</span> هو المعيار الأكثر استخدامًا في الشركات والشبكات التجارية حاليًا، رغم إن الاتنين بيشتغلوا بنفس الكفاءة الكهربائية طالما اتطبقوا بشكل متسق على طرفي الكابل.

<div align="center">
<img src="images/8-7-t568a-t568b-wiring.png" width="500">
<br>
<em>ترتيب الأسلاك الكامل في معياري T568A و T568B</em>
</div>

<h3 id="cable-patterns" dir="rtl" align="right">أنماط توصيل الكابل: <span dir="ltr">Straight-Through / Crossover / Rollover</span></h3>

بناءً على ترتيب الألوان في طرفي الكابل، بيتحدد نوع الكابل ووظيفته:

**أ- <span dir="ltr">Straight-Through Cable</span>**
- نفس ترتيب الألوان في الطرفين (مثلاً <span dir="ltr">T568B</span> في الطرفين).
- بيُستخدم لتوصيل أجهزة من **نوع مختلف** فيما بينها: <span dir="ltr">PC ↔ Switch</span>، أو <span dir="ltr">Switch ↔ Router</span>.
- هو الأكثر شيوعًا في الاستخدام اليومي.

<div align="center">
<img src="images/8-8-straight-through-wiring.png" width="550">
<br>
<em>ترتيب الأسلاك في كابل Straight-Through</em>
</div>

**ب- <span dir="ltr">Crossover Cable</span>**
- ترتيب مختلف بين الطرفين: طرف <span dir="ltr">T568A</span> والطرف التاني <span dir="ltr">T568B</span>.
- بيُستخدم لتوصيل أجهزة من **نفس النوع** فيما بينها: <span dir="ltr">PC ↔ PC</span>، أو <span dir="ltr">Switch ↔ Switch</span>، أو <span dir="ltr">Router ↔ Router</span>.
- الفكرة إنه بيقلب أسلاك الإرسال <span dir="ltr">(Tx)</span> مع أسلاك الاستقبال <span dir="ltr">(Rx)</span> عشان الجهازين يقدروا يبعتوا ويستقبلوا صح بدون تعارض.
- **ملاحظة**: أغلب الأجهزة الحديثة فيها خاصية <span dir="ltr">Auto-MDIX</span> اللي بتخلي الجهاز يكتشف نوع التوصيل تلقائيًا، فبقى ممكن تستخدم Straight-Through حتى بين أجهزة من نفس النوع.

<div align="center">
<img src="images/8-10-crossover-wiring.png" width="550">
<br>
<em>ترتيب الأسلاك في كابل Crossover</em>
</div>

**جـ- <span dir="ltr">Rollover Cable</span>**
- ترتيب الألوان في الطرف التاني هو **معكوس تمامًا** لترتيب الطرف الأول (لو الطرف الأول 1-2-3-4-5-6-7-8، الطرف التاني بيبقى 8-7-6-5-4-3-2-1).
- مش بيُستخدم لنقل بيانات الشبكة العادية، لكنه بيُستخدم لأغراض **الإدارة والتحكم** <span dir="ltr">(Console/Management)</span>، بالتحديد لتوصيل جهاز الكمبيوتر بمنفذ الـ <span dir="ltr">Console</span> في الراوتر أو السويتش عن طريق موصل <span dir="ltr">RJ-45 to DB-9</span> أو <span dir="ltr">USB</span>.
- معروف كمان باسم <span dir="ltr">Cisco Console Cable</span>.

<div align="center">
<img src="images/8-9-rollover-wiring.png" width="550">
<br>
<em>ترتيب الأسلاك في كابل Rollover</em>
</div>

جدول مقارنة سريع:

| النوع | ترتيب الطرفين | الاستخدام | يوصل بين |
|:---:|:---:|:---:|:---:|
| <span dir="ltr">Straight-Through</span> | نفس المعيار في الطرفين | نقل بيانات بين أجهزة مختلفة | <span dir="ltr">PC ↔ Switch</span>، <span dir="ltr">Switch ↔ Router</span> |
| <span dir="ltr">Crossover</span> | معيار مختلف بين الطرفين (A و B) | نقل بيانات بين أجهزة متشابهة | <span dir="ltr">PC ↔ PC</span>، <span dir="ltr">Switch ↔ Switch</span> |
| <span dir="ltr">Rollover</span> | ترتيب معكوس بالكامل | إدارة وتحكم <span dir="ltr">(Console)</span> | <span dir="ltr">PC ↔ Router/Switch Console Port</span> |

<h3 id="utp-stp" dir="rtl" align="right">أنواع الكابل المجدول من ناحية التغليف</h3>

**1- <span dir="ltr">UTP (Unshielded Twisted Pair)</span>**
- الأزواج غير محمية بأي طبقة معدنية إضافية، غلافه الخارجي بلاستيكي بس.
- أرخص وأسهل في التركيب والمرونة.
- الأكثر شيوعًا في الشبكات المحلية والمكاتب والمنازل.
- أكثر عرضة للتداخل الكهرومغناطيسي <span dir="ltr">(EMI)</span> في البيئات الصناعية القريبة من مصادر كهرباء قوية.

**2- <span dir="ltr">STP (Shielded Twisted Pair)</span>** وأنواعها الفرعية:
- **<span dir="ltr">FTP (Foiled Twisted Pair)</span>**: طبقة ورق ألومنيوم واحدة بتغلف كل الأزواج مع بعض.
- **<span dir="ltr">STP</span>**: كل زوج بيتغلف بطبقة حماية على حدة، حماية أقوى من FTP.
- **<span dir="ltr">S-FTP / SSTP (Screened Shielded Twisted Pair)</span>**: بتجمع بين حماية كل زوج على حدة + طبقة حماية عامة تانية للكابل كله، أعلى مستوى حماية.

- بيُستخدم في البيئات اللي فيها تداخل كهرومغناطيسي عالي، زي المصانع وجانب المعدات الكهربائية الثقيلة.
- بيحتاج توصيل أرضي <span dir="ltr">(Grounding)</span> صحيح عشان يبقى فعّال، وإلا ممكن يبقى مصدر تشويش بدل ما يمنعه.

<div align="center">
<img src="images/8-12-shielded-twisted-pair-types.png" width="600">
<br>
<em>أنواع الكابل المجدول المحمي: FTP / STP / S-FTP / SSTP</em>
</div>

<div align="center">
<img src="images/8-11-utp-ftp-stp-sftp-types.png" width="450">
<br>
<em>مقارنة بصرية بين UTP و FTP و STP و S-FTP</em>
</div>

| المقارنة | <span dir="ltr">UTP</span> | <span dir="ltr">STP</span> |
|:---:|:---:|:---:|
| التكلفة | أقل | أعلى |
| المرونة | أعلى | أقل |
| الحماية من التداخل | أقل | أعلى |
| سهولة التركيب | أسهل | أصعب (يحتاج تأريض) |
| الاستخدام الشائع | مكاتب، منازل، شبكات LAN عادية | بيئات صناعية، مناطق تداخل كهرومغناطيسي عالي |

<h3 id="twisted-pair-connectors" dir="rtl" align="right">أطراف رؤوس الكابل المجدول</h3>

- **<span dir="ltr">RJ-45</span>**: الموصل الأشهر لكابلات الشبكة (8 أسنان)، بيُستخدم في كل تطبيقات الإيثرنت الحديثة.
- **<span dir="ltr">RJ-11</span>**: أصغر حجمًا (4 أو 6 أسنان)، بيُستخدم في خطوط الهاتف الأرضي والفاكس، وأحيانًا في مودمات الـ ADSL.

<div align="center">
<img src="images/8-13-rj45-pinout.png" width="450">
<br>
<em>ترقيم أسنان موصل RJ-45 من 1 إلى 8 حسب المعيارين</em>
</div>

<h3 id="cable-categories" dir="rtl" align="right">فئات الكابلات المجدولة <span dir="ltr">(Cat)</span></h3>

| الفئة | أقصى سرعة | أقصى تردد | ملاحظات |
|:---:|:---:|:---:|:---:|
| <span dir="ltr">Cat 3</span> | 10 <span dir="ltr">Mbps</span> | 16 <span dir="ltr">MHz</span> | قديم جدًا، كان بيُستخدم في الهاتف والشبكات القديمة |
| <span dir="ltr">Cat 5</span> | 100 <span dir="ltr">Mbps</span> | 100 <span dir="ltr">MHz</span> | قديم، حل محله Cat 5e |
| <span dir="ltr">Cat 5e</span> | 1 <span dir="ltr">Gbps</span> | 100 <span dir="ltr">MHz</span> | الأكثر شيوعًا في المنازل والمكاتب الصغيرة (e = enhanced) |
| <span dir="ltr">Cat 6</span> | 1 <span dir="ltr">Gbps</span> (10 <span dir="ltr">Gbps</span> لمسافة قصيرة تصل لـ 55 م) | 250 <span dir="ltr">MHz</span> | فيه فاصل بلاستيكي داخلي <span dir="ltr">(spline)</span> لتقليل الـ Crosstalk |
| <span dir="ltr">Cat 6a</span> | 10 <span dir="ltr">Gbps</span> لمسافة 100 م كاملة | 500 <span dir="ltr">MHz</span> | مواصفات أقوى ضد التداخل، أسلاك أسمك |
| <span dir="ltr">Cat 7</span> | 10 <span dir="ltr">Gbps</span> فأكثر | 600 <span dir="ltr">MHz</span> | كل زوج محمي على حدة (STP)، يحتاج موصل خاص GG45 |
| <span dir="ltr">Cat 8</span> | 25-40 <span dir="ltr">Gbps</span> | 2000 <span dir="ltr">MHz</span> | لمسافات قصيرة جدًا (30 م)، بيُستخدم في مراكز البيانات |

**حد المسافة العام** لكابلات النحاس المجدولة هو **100 متر** كأقصى مسافة قبل ما الإشارة تضعف بشكل مؤثر <span dir="ltr">(Attenuation)</span>، وده بينطبق على معظم فئات الـ Cat بغض النظر عن السرعة.

<div align="center">
<img src="images/8-14-cable-categories-chart.png" width="600">
<br>
<em>مخطط سرعات وترددات فئات Cat المختلفة</em>
</div>

<div align="center">
<img src="images/8-15-cable-categories-table-ar.png" width="600">
<br>
<em>جدول استخدامات كل فئة Cat</em>
</div>

<div align="center">
<img src="images/8-16-cable-categories-photos.png" width="600">
<br>
<em>مقارنة فيزيائية بين فئات UTP/SFTP المختلفة</em>
</div>

---

<h2 id="fiber" dir="rtl" align="right">ثالثاً: كابلات الألياف الضوئية <span dir="ltr">Fiber Optic Cables</span></h2>

<h3 id="fiber-def" dir="rtl" align="right">تعريف كابل الألياف الضوئية واستخداماته</h3>

كابل الألياف الضوئية بينقل البيانات في صورة **نبضات ضوئية** بدل الإشارات الكهربائية، عن طريق ألياف زجاجية أو بلاستيكية رفيعة جدًا. بيُستخدم أساسًا في:
- الربط بين المدن والدول <span dir="ltr">(Backbone Networks)</span> وخطوط الإنترنت البحرية.
- الربط بين مراكز البيانات <span dir="ltr">(Data Centers)</span>.
- شبكات الـ <span dir="ltr">FTTH (Fiber To The Home)</span> لتوفير إنترنت فائق السرعة للمنازل.
- أي بيئة محتاجة سرعة عالية جدًا أو مسافات طويلة أو حماية قصوى من التنصت.

<div align="center">
<img src="images/8-17-fiber-optic-intro.png" width="550">
<br>
<em>كابل الألياف الضوئية - نقل بيانات عالي السرعة</em>
</div>

<h3 id="fiber-components" dir="rtl" align="right">مكونات كابل الألياف الضوئية</h3>

| المكوّن | الوظيفة |
|:---:|:---:|
| <span dir="ltr">Glass Core</span> | اللب الزجاجي الرفيع اللي بينقل الضوء فعليًا |
| <span dir="ltr">Cladding</span> | طبقة زجاجية حوالين الـ Core بمعامل انكسار مختلف، بتخلي الضوء ينعكس جوه الـ Core بدل ما يتسرب (مبدأ الانعكاس الكلي الداخلي) |
| <span dir="ltr">Coating / Buffer</span> | طبقة بلاستيكية بتحمي الألياف من الرطوبة والكسر |
| <span dir="ltr">Strength Member</span> | ألياف تقوية (زي الكيفلار أو أسلاك الصلب) بتحمي الكابل من الشد الميكانيكي |
| <span dir="ltr">Outer Jacket</span> | الغلاف الخارجي الواقي |

<div align="center">
<img src="images/8-18-fiber-optic-structure-basic.png" width="500">
<br>
<em>مكونات كابل الألياف الضوئية الأساسية: Core / Cladding / Coating / Strength Member / Outer Jacket</em>
</div>

الكابلات المستخدمة في المسافات الطويلة جدًا (زي الكابلات البحرية) بتضيف طبقات حماية إضافية زي أسلاك الصلب المجلفن <span dir="ltr">(Galvanized Armor Wires)</span> وحاجز مائي <span dir="ltr">(Water Barrier)</span> وأنبوب نحاسي لحماية الألياف من الضغط والرطوبة تحت الأرض أو تحت البحر:

<div align="center">
<img src="images/8-19-fiber-optic-structure-armored.png" width="550">
<br>
<em>مكونات كابل الألياف الضوئية المدرّع للمسافات الطويلة</em>
</div>

<div align="center">
<img src="images/8-20-fiber-optic-cutaway-colorful.png" width="450">
<br>
<em>مقطع عرضي يوضح حزمة الألياف الزجاجية داخل الكابل</em>
</div>

<h3 id="fiber-modes" dir="rtl" align="right">أقسام تصنيع الألياف الضوئية</h3>

**أ- <span dir="ltr">Single-Mode Fiber (SMF)</span>**
- قطر الـ Core صغير جدًا (حوالي 9 ميكرون)، بيسمح لشعاع ضوء واحد بس يمر (بمسار واحد مستقيم تقريبًا).
- بيستخدم مصدر ضوء ليزر <span dir="ltr">(Laser)</span>.
- بيدعم مسافات طويلة جدًا (تصل لعشرات ومئات الكيلومترات) بأقل فقدان للإشارة.
- أغلى في التكلفة، وبيُستخدم في الربط بين المدن ومراكز البيانات البعيدة.
- الغلاف عادة أصفر اللون كعلامة تمييز عالمية.

**ب- <span dir="ltr">Multi-Mode Fiber (MMF)</span>**
- قطر الـ Core أكبر (50 أو 62.5 ميكرون)، بيسمح بمرور أكتر من شعاع ضوء في مسارات متعددة <span dir="ltr">(modes)</span> في نفس الوقت.
- بيستخدم مصدر ضوء LED أو ليزر رخيص <span dir="ltr">(VCSEL)</span>.
- مسافته أقصر (عادة حتى 550 متر أو أقل حسب الفئة)، بسبب ظاهرة تشتت الإشارة <span dir="ltr">(Modal Dispersion)</span> بسبب تعدد المسارات.
- أرخص من الـ Single-Mode، وبيُستخدم داخل المباني ومراكز البيانات القريبة.
- الغلاف عادة برتقالي أو أكوا <span dir="ltr">(aqua)</span> حسب الفئة.

| المقارنة | <span dir="ltr">Single-Mode</span> | <span dir="ltr">Multi-Mode</span> |
|:---:|:---:|:---:|
| قطر الـ Core | صغير (~9 μm) | أكبر (50/62.5 μm) |
| مصدر الضوء | ليزر | LED / VCSEL |
| المسافة | طويلة جدًا (كيلومترات) | قصيرة (أمتار لمئات الأمتار) |
| التكلفة | أعلى | أقل |
| لون الغلاف الشائع | أصفر | برتقالي / أكوا |

<div align="center">
<img src="images/8-21-fiber-single-multi-mode.png" width="550">
<br>
<em>الفرق بين مسار الضوء في Single-Mode و Multi-Mode</em>
</div>

<h3 id="fiber-connectors" dir="rtl" align="right">أطراف رؤوس كابلات الألياف الضوئية</h3>

- **<span dir="ltr">SC (Subscriber Connector)</span>**: موصل مربع الشكل، بيتركب بدفعة بسيطة (Push-Pull)، من أكتر الأنواع شيوعًا.
- **<span dir="ltr">LC (Lucent Connector)</span>**: موصل أصغر حجمًا من الـ SC، بيُستخدم كتير في المعدات الحديثة عالية الكثافة (زي الـ SFP modules).
- **<span dir="ltr">ST (Straight Tip)</span>**: موصل دائري بيتقفل بلفة ربع دورة زي الـ BNC، أقدم نوع وبيُستخدم أقل حاليًا.
- **<span dir="ltr">MTRJ (Mechanical Transfer Registered Jack)</span>**: بيجمع زوج من الألياف (إرسال واستقبال) في موصل واحد صغير.

<h3 id="fiber-ports" dir="rtl" align="right">منافذ الكابلات الضوئية</h3>

المنافذ اللي بتستقبل كابلات الألياف الضوئية في المعدات الشبكية غالبًا مش منفذ ثابت زي RJ-45، لكنها بتعتمد على وحدة تحويل <span dir="ltr">(Transceiver Module)</span> بتترّكب في السويتش أو الراوتر، زي:
- **<span dir="ltr">SFP (Small Form-factor Pluggable)</span>**: وحدة صغيرة قابلة للفك والتركيب، بتدعم سرعات تصل لـ 1 <span dir="ltr">Gbps</span>.
- **<span dir="ltr">SFP+</span>**: نسخة محسّنة بتدعم سرعات تصل لـ 10 <span dir="ltr">Gbps</span>.
- **<span dir="ltr">QSFP</span>**: بيدعم سرعات أعلى (40 <span dir="ltr">Gbps</span> فأكثر)، بيُستخدم في مراكز البيانات الكبيرة.

<h3 id="fiber-pros-cons" dir="rtl" align="right">مميزات وعيوب استخدام كابلات الألياف الضوئية</h3>

**المميزات:**
- سرعات نقل عالية جدًا ومسافات طويلة بدون تكرار للإشارة.
- مناعة كاملة تقريبًا ضد التداخل الكهرومغناطيسي <span dir="ltr">(EMI)</span> لأنها مش بتنقل كهرباء أصلًا.
- أصعب بكتير في التنصت عليها مقارنة بالكابل النحاسي، لأن أي محاولة قطع أو "تنصت فيزيائي" بتسبب انقطاع ملحوظ في الإشارة يقدر يكتشفه الفني بسهولة.
- أخف وزنًا وأرفع حجمًا من الكابل النحاسي المكافئ لها في السعة.

**العيوب:**
- التكلفة أعلى بكتير (سواء الكابل نفسه أو المعدات المصاحبة له زي الـ Transceivers).
- التركيب والصيانة بتحتاج مهارة وأدوات متخصصة (زي أجهزة الـ Fusion Splicing).
- هشة نسبيًا وسهلة الكسر لو انثنت بزاوية حادة جدًا.
- صعوبة إصلاحها ميدانيًا مقارنة بكابل النحاس.

---

<h2 id="serial" dir="rtl" align="right">رابعاً: الكابلات المتسلسلة ومنافذها <span dir="ltr">Serial Cables and Interfaces</span></h2>

<h3 id="serial-def" dir="rtl" align="right">تعريفها</h3>

الكابل المتسلسل هو نوع من الكابلات بينقل البيانات بت بعد بت في تتابع واحد على نفس السلك <span dir="ltr">(bit by bit, sequentially)</span>، على عكس الكابلات المتوازية اللي كانت بتنقل عدة بتات في نفس الوقت على أسلاك منفصلة.

<div align="center">
<img src="images/8-22-serial-cables-interfaces.png" width="600">
<br>
<em>الكابلات المتسلسلة ومنافذها</em>
</div>

**استخدامها في عالم الشبكات:**
- الاتصال بأجهزة الراوتر القديمة عبر واجهات <span dir="ltr">WAN</span> (زي خطوط <span dir="ltr">T1</span> أو <span dir="ltr">Frame Relay</span>).
- بروتوكولات زي <span dir="ltr">HDLC</span> و <span dir="ltr">PPP</span> بتشتغل على الواجهات المتسلسلة دي.
- الاتصال بمنفذ الـ <span dir="ltr">Console</span> في الأجهزة الشبكية للإدارة الأولية (باستخدام كابل <span dir="ltr">Rollover</span> ومحول <span dir="ltr">RJ-45 to DB-9</span>).

<h3 id="serial-connection" dir="rtl" align="right">كيفية التوصيل بينها وبين الأجهزة</h3>

بيتم التوصيل عادة عن طريق موصلات <span dir="ltr">DB-9</span> أو <span dir="ltr">DB-25</span>، وحاليًا بتُستبدل غالبًا بمحولات <span dir="ltr">USB to Serial</span> لأن أغلب أجهزة الكمبيوتر الحديثة معندهاش منفذ متسلسل تقليدي.

<h3 id="dte-dce" dir="rtl" align="right">الـ <span dir="ltr">DTE</span> والـ <span dir="ltr">DCE</span></h3>

- **<span dir="ltr">DTE (Data Terminal Equipment)</span>**: هو الجهاز اللي "بيولّد" أو "بيستقبل" البيانات النهائية، زي الراوتر أو الكمبيوتر.
- **<span dir="ltr">DCE (Data Circuit-terminating Equipment)</span>**: هو الجهاز المسؤول عن **توفير التوقيت (Clocking)** وتحويل الإشارة عشان تتنقل على خط الاتصال، زي المودم أو وحدة الـ <span dir="ltr">CSU/DSU</span>.

 في الاتصال المتسلسل، جهاز الـ DCE هو المسؤول عن ضبط سرعة الساعة <span dir="ltr">(Clock Rate)</span> اللي هيتزامن بيها نقل البيانات، والـ DTE بيعتمد على التوقيت ده. في المعامل والمحاكاة (زي Packet Tracer)، بتحدد سرعة الـ Clock Rate يدويًا على الطرف اللي معاه كابل الـ DCE.

---

<h2 id="patch-panel" dir="rtl" align="right">خامساً: لوحة تجميع وتنظيم الكابلات <span dir="ltr">Patch Panel</span></h2>

<h3 id="patch-panel-types" dir="rtl" align="right">تعريفها وأنواعها</h3>

الـ <span dir="ltr">Patch Panel</span> هي لوحة معدنية بيها عدد كبير من منافذ الـ <span dir="ltr">RJ-45</span> (أو الألياف الضوئية)، بتُستخدم كنقطة وسيطة بين كابلات الشبكة الممتدة داخل الحوائط (من نقاط الشبكة في المكاتب) وبين جهاز الـ <span dir="ltr">Switch</span>. الهدف منها تنظيم الكابلات وتسهيل الصيانة، لأنك بدل ما تلمس الأسلاك جوه الحائط تقدر تغيّر التوصيل من على اللوحة نفسها بكابل قصير <span dir="ltr">(Patch Cable)</span>.

أنواعها الرئيسية:
- **<span dir="ltr">Copper Patch Panel</span>**: مخصصة لكابلات النحاس المجدولة (RJ-45)، وبتُستخدم في معظم الشبكات المكتبية العادية.
- **<span dir="ltr">Fiber Patch Panel</span>**: مخصصة لكابلات الألياف الضوئية، وفيها غالبًا مساحة إضافية لحفظ الطول الزائد من الكابل الضوئي بدون ما ينثني بزاوية حادة.
- **<span dir="ltr">Modular Patch Panel</span>**: بتسمح بتغيير أو إضافة منافذ فردية <span dir="ltr">(Keystone Jacks)</span> بدل ما تكون اللوحة كلها ثابتة.

**الفايدة الأمنية**: تنظيم الـ Patch Panel وتوثيق كل منفذ بيسهّل جدًا اكتشاف أي جهاز غريب اتوصل بالشبكة فيزيائيًا، وهو جزء من ممارسات الأمان الفيزيائي <span dir="ltr">(Physical Security)</span> في أي بنية تحتية.

---

<h2 id="cable-properties" dir="rtl" align="right">سادساً: خصائص كابلات الشبكة</h2>

<h3 id="speed-distance" dir="rtl" align="right">سرعة النقل والمسافة</h3>

كل نوع كابل بيتحدد بمواصفتين أساسيتين بيتنافسوا مع بعض غالبًا: **السرعة القصوى** اللي يقدر ينقلها، و**أقصى مسافة** يقدر يوصلها بدون ما الإشارة تضعف بشكل مؤثر <span dir="ltr">(Attenuation)</span>. القاعدة العامة إن زيادة السرعة أو المسافة بتحتاج جودة تصنيع أعلى (فئة أعلى في النحاس، أو تحول للألياف الضوئية).

| نوع الكابل | أقصى سرعة تقريبية | أقصى مسافة (بدون Repeater) |
|:---:|:---:|:---:|
| <span dir="ltr">Coaxial (Thin)</span> | 10 <span dir="ltr">Mbps</span> | 185 م |
| <span dir="ltr">Coaxial (Thick)</span> | 10 <span dir="ltr">Mbps</span> | 500 م |
| <span dir="ltr">UTP Cat 5e/6</span> | 1-10 <span dir="ltr">Gbps</span> | 100 م |
| <span dir="ltr">Multi-Mode Fiber</span> | 10+ <span dir="ltr">Gbps</span> | حتى 550 م |
| <span dir="ltr">Single-Mode Fiber</span> | 100+ <span dir="ltr">Gbps</span> | عشرات الكيلومترات |

<h3 id="duplex-modes" dir="rtl" align="right">اتجاه الإرسال بين الأجهزة</h3>

بيوصف اتجاه تدفق البيانات على وسيط النقل، وله 3 أنماط:

**أ- <span dir="ltr">Simplex Mode</span>**
- الإرسال في اتجاه واحد بس، جهاز بيبعت والتاني بيستقبل فقط، من غير رجوع.
- مثال: أجهزة الراديو التقليدية، لوحات العرض <span dir="ltr">(Display Boards)</span>.

<div align="center">
<img src="images/8-23-simplex-mode.png" width="500">
<br>
<em>نمط Simplex - اتجاه واحد فقط</em>
</div>

**ب- <span dir="ltr">Half Duplex Mode</span>**
- الإرسال في الاتجاهين، لكن مش في نفس الوقت — أي وقت بيبعت الجهاز مش بيقدر يستقبل، والعكس.
- مثال: أجهزة اللاسلكي <span dir="ltr">(Walkie-Talkie)</span>، والشبكات القديمة اللي كانت بتشتغل على <span dir="ltr">Hub</span> (لأن الـ Hub بيبعت لكل الأجهزة مرة واحدة فبيحصل تصادم لو بعتوا في نفس الوقت - <span dir="ltr">Collision</span>).

<div align="center">
<img src="images/8-24-half-duplex-mode.png" width="500">
<br>
<em>نمط Half Duplex - اتجاهين بالتناوب</em>
</div>

**جـ- <span dir="ltr">Full Duplex Mode</span>**
- الإرسال والاستقبال في نفس الوقت في الاتجاهين، من غير ما يأثروا على بعض.
- مثال: المكالمات الهاتفية العادية، وشبكات الإيثرنت الحديثة اللي بتشتغل على <span dir="ltr">Switch</span> (لأن الـ Switch بيوفر مسار مخصص لكل جهاز فمفيش تصادم).

<div align="center">
<img src="images/8-25-full-duplex-mode.png" width="500">
<br>
<em>نمط Full Duplex - اتجاهين في نفس الوقت</em>
</div>

<div align="center">
<img src="images/8-26-transmission-modes-summary.png" width="600">
<br>
<em>ملخص شامل لأنماط الإرسال الثلاثة</em>
</div>

| النمط | الاتجاه | التزامن | مثال |
|:---:|:---:|:---:|:---:|
| <span dir="ltr">Simplex</span> | اتجاه واحد فقط | - | راديو، بث تلفزيوني |
| <span dir="ltr">Half Duplex</span> | اتجاهين، بالتناوب | لا يوجد | Walkie-Talkie، شبكة على Hub |
| <span dir="ltr">Full Duplex</span> | اتجاهين، في نفس الوقت | يوجد | مكالمة هاتفية، شبكة على Switch |

---

<h2 id="summary-table" dir="rtl" align="right">ملخص شامل للمقارنة بين كل الكابلات</h2>

<div align="center">
<img src="images/8-27-cable-types-summary-ar.png" width="650">
<br>
<em>ملخص أنواع الكابلات والموصلات في الشبكات</em>
</div>

<div align="center">
<img src="images/8-28-network-cables-types-infographic.png" width="650">
<br>
<em>مقارنة شاملة بين Coaxial و Fiber Optic و STP و UTP</em>
</div>

| الخاصية | <span dir="ltr">Coaxial</span> | <span dir="ltr">Twisted Pair (UTP/STP)</span> | <span dir="ltr">Fiber Optic</span> |
|:---:|:---:|:---:|:---:|
| نوع الإشارة | كهربائية | كهربائية | ضوئية |
| السرعة | منخفضة (~10 Mbps) | متوسطة إلى عالية (حتى 40 Gbps) | عالية جدًا (100+ Gbps) |
| المسافة القصوى | 185-500 م | 100 م | كيلومترات (Single-Mode) |
| المقاومة للتداخل الكهرومغناطيسي | متوسطة | منخفضة (UTP) / متوسطة (STP) | مناعة كاملة |
| التكلفة | متوسطة | منخفضة | مرتفعة |
| سهولة التركيب | متوسطة | سهلة جدًا | صعبة (تحتاج تخصص) |
| الاستخدام الحالي الشائع | إنترنت كابلي، CCTV قديم | شبكات LAN المكتبية والمنزلية | Backbone، مراكز بيانات، FTTH |
| مقاومة التنصت الفيزيائي | منخفضة | منخفضة | عالية جدًا |

**نقاط مهمة للمراجعة السريعة:**

- <span dir="ltr">Coaxial</span> = موصل مركزي واحد، RG-6/RG-59 للتلفزيون والإنترنت الكابلي.
- <span dir="ltr">Twisted Pair</span> = 4 أزواج، T568A/T568B، حد أقصى 100 متر لكل الفئات.
- <span dir="ltr">Straight-Through</span> لأجهزة مختلفة، <span dir="ltr">Crossover</span> لأجهزة متشابهة، <span dir="ltr">Rollover</span> للإدارة.
- <span dir="ltr">Single-Mode</span> = مسافات طويلة وليزر، <span dir="ltr">Multi-Mode</span> = مسافات قصيرة و LED.
- <span dir="ltr">DTE</span> بيستقبل/يولّد البيانات، <span dir="ltr">DCE</span> بيوفر التوقيت (Clocking).
- <span dir="ltr">Full Duplex</span> = إرسال واستقبال في نفس الوقت (Switch)، <span dir="ltr">Half Duplex</span> = بالتناوب (Hub).

</div>
