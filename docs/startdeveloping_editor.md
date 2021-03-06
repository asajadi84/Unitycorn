---
id: startdeveloping_editor
title: بررسی ادیتور یونیتی
slug: /startdeveloping/editor
---

بعد از باز کردن یک پروژه در یونیتی رابط کاربری اصلی آن که ادیتور یونیتی نیز نامیده می‌شود به صورت زیر نمایش داده خواهد شد. ادیتور یونیتی از پنجره‌های مختلفی تشکیل شده است. مکان هر پنجره در چینش (layout) پیش‌فرض یونیتی به صورت فوق می‌باشد:

![image](/img/unity_editor_breakdown.png)

یونیتی چینش‌های دیگری نیز دارد. برای مشاهده و امتحان آن‌ها از منوی کشویی Layout واقع در تولبار یونیتی (که در آن نام چینش فعلی نوشته شده است؛ مثل Default در تصویر بالا) گزینه‌های مختلف را امتحان کنید.

پنجره‌های یونیتی قابلیت جابجایی و تغییر مکان به صورت دستی را نیز دارند. برای انجام این کار کافی‌است زبانه‌ی هر پنجره (که نام پنجره در آن نوشته شده است) توسط ماوس drag شود. برای بستن یک پنجره بایستی بر روی زبانه‌ی آن راست کلیک کرده و بر روی Close Tab کلیک کرد. برای فراخوانی پنجره‌هایی که در رابط کاربری قرار ندارند نیز می‌توان از منوی Window اقدام نمود. این تغییرات همراه پروژه ذخیره می‌شوند و پس از آن با باز کردن پروژه چینش مطابق تغییرات داده شده خواهد بود.

تغییرات داده شده در رابط کاربری را می‌توان تحت یک چینش جدید ذخیره کرد. برای این کار پس از انجام تغییرات موردنظر از منوی کشویی Layout گزینه‌ی Save Layout را انتخاب کنید.

در صورتی که در یکی از چینش‌های یونیتی تغییراتی ایجاد کرده و قصد بازگرداندن آن به تنظیمات اولیه را داشته باشید نیز می‌توانید از همین منو Revert Factory Setting را انتخاب کنید.

هرکدام از این پنجره‌ها وظیفه‌ی خاصی بر عهده دارند که در ادامه آن‌ها را بررسی می‌کنیم.

## پنجره‌ی Project

![image](/img/unity_editor_project_window.png)

این پنجره امکان کاوش فولدر Assets پروژه‌ی باز شده را فراهم می‌کند.

پنجره‌ی Project دو حالت یک‌ستونه و دوستونه دارد که در تصویر بالا حالت دوستونه‌ی آن نمایش داده شده است. برای تغییر حالت بر روی زبانه‌ی پنجره راست کلیک کرده و یکی از گزینه‌های One Column Layout یا Two Column Layout را انتخاب کنید.

در حالت دوستونه در ستون سمت چپ سلسله‌مراتب فایل‌ها و فولدرهای موجود در فولدر Assets پروژه و در ستون سمت راست محتوای فولدری که در ستون چپ انتخاب شده است نشان داده می‌شود. اندازه‌ی thumbnailهای این ستون را می‌توان از طریق نوار لغزنده‌ی سمت راست و پایین پنجره تغییر داد (این thumbnailها تا یک حد خاص کوچک شده و بعد از آن در هنگام رسیدن به حداقل اندازه به صورت لیست در می‌آیند).

در نوار بالایی این پنجره (نوار کنترل) با کلیک بر روی دکمه‌ی Create می‌توان اقدام به ایجاد فولدر و یا asset نمود. این منو از طریق راست کلیک بر روی فضای خالی ستون سمت راست و نگه داشتن فلش ماوس بر روی گزینه‌ی Create نیز قابل فراخوانی است. با استفاده از نوار جستجو می‌توان به جستجو در پروژه پرداخت و حتی می‌توان نتیجه‌ی جستجو را با کلیک بر روی آیکون ستاره‌ی این نوار ذخیره کرد. این ذخیره در قسمت Favorites منوی سمت چپ جای خواهد گرفت.

با استفاده از دو آیکون دیگر نوار بالای این پنجره می‌توان assetها را برحسب نوع و یا برچسبی که در حین توسعه به آن‌ها داده‌ایم فیلتر کرد.

در نسخه‌های جدید یونیتی (۲۰۱۸ به بالا) هنگام ایجاد یک پروژه‌ی جدید به طور پیش‌فرض در این فولدر زیرفولدری با نام Scenes و در داخل آن فایل صحنه‌ای که باز شده قرار دارد (در حالی که در نسخه‌های قدیمی فولدر Assets کاملاً خالی بود و این مراحل به صورت دستی انجام می‌شد).

:::note نکته
در صورتی که ورژن یونیتی شما به دلیل قدیمی بودن فایل و فولدر صحنه را به صورت خودکار ایجاد نکرد در پنجره‌ی Project در مسیر ریشه به صورت دستی فولدری به نام Scenes ایجاد کرده و سپس از طریق منوی File گزینه‌ی Save Scene را انتخاب و صحنه را با نام دلخواه در این فولدر ذخیره کنید.
:::

از این پنجره بیشتر برای سه کار زیر استفاده می‌شود:

۱- import کردن asset به پروژه: برای وارد کردن asset به پروژه فایل‌های مدنظر را از explorer ویندوز (یعنی یک فولدر باز یا حتی دسکتاپ) به روی ستون سمت راست این پنجره drag and drop می‌کنیم. این فرآیند در حد چند ثانیه به طول می‌انجامد. چرا که یونیتی به ازای هر فایل و فولدر asset یک فایل متا در کنار آن می‌سازد که تنظیماتشان در پروژه را در خود ذخیره می‌کند (به همین علت نباید assetها را به طور مستقیم و از طریق explorer ویندوز به فولدر Assets اضافه کنیم).

![image](/img/project_in_explorer_vs_project_window.png)

*از چپ به راست: فولدر پروژه در اکسپلورر ویندوز، فولدر Assets پروژه در اکسپلورر ویندوز و پنجره‌ی Projects*

۲- تغییر تنظیمات assetها: با کلیک کردن بر روی هر فایل در ستون سمت راست تنظیمات آن در پنجره‌ی Inspector نمایش داده می‌شود (بسته به نوع فایل تنظیمات تغییر می‌کنند) که این تنظیمات در متای فایل ذخیره می‌شوند.

۳- نسبت دادن یک asset به فیلد یک کامپوننت در درون Inspector: در این حالت asset موردنظر از ستون سمت راست پنجره‌ی Project بر روی فیلد مدنظر drag and drop می‌شود.

## نمای صحنه (Scene) و ابزارهای دگرگونی

![image](/img/unity_editor_scene_window.png)

این نما از اصلی‌ترین اجزای یونیتی است. وقتی در یک پروژه فایل صحنه‌ای را باز می‌کنیم آن صحنه در این نما نمایش داده می‌شود. امکان جابجایی، چرخش و تغییر اندازه‌ی گیم آبجکت‌ها از طریق کلیک کردن در این نما و استفاده از ابزارهای تولبار امکان‌پذیر است.

:::note نکته
این نما، نمایی که کاربر نهایی مشاهده می‌کند نیست؛ تصویری که بازیکن نهایی از صحنه می‌بیند، توسط گیم‌آبجکتی به نام Main Camera (دوربین اصلی) که به طور پیش‌فرض در هر صحنه‌ای وجود دارد از زاویه و مکانی خاص در صحنه گرفته شده و در نهایت برای کاربر رندر می‌شود. این عمل مثل فیلم‌برداری است که تماشاگر در نهایت تنها از دریچه‌ی دوربین و زاویه‌ای که توسط کارگردان مشخص شده می‌تواند به یک سکانس نگاه کند (دکوپاژ) و امکان مشاهده‌ی صحنه از زاویه‌ی دیگری را ندارد. این نما صرفاً برای چیدن صحنه توسط توسعه‌دهنده و مدیریت اجزای آن است.
:::

دکمه‌های نوار بالایی این نما بیشتر برای بازی‌های سه‌بعدی کاربرد دارند. تغییر تنظیمات این نوار در خروجی نهایی تاثیر ندارد و صرفا ابزارهایی برای راحتی بیشتر مراحل توسعه هستند. در صورتی که دکمه‌ی ۲D فعال باشد (که در پروژه‌های دوبعدی به صورت پیش‌فرض فعال است) صحنه از زاویه‌ای نشان داده می‌شود که اسپرایت‌ها تخت به نظر برسند. این بدین معناست که حتی در پروژه‌های دوبعدی یونیتی هم صحنه در اصل سه‌بعدی است؛ اما زاویه‌ی تصویربرداری Main Camera به صورتی است که عمود بر صفحات تخت اسپرایت بوده و دکوپاژ به صورت دوبعدی برای کاربر نهایی به نظر برسد.

در نمای سه‌بعدی Scene Gizmo در سمت راست و بالای نما نشان داده می‌شود که زاویه‌ی دید فعلی توسعه‌دهنده از صحنه را تغییر می‌دهد (مجدداً تاکید می‌کنیم این ارتباطی با خروجی نهایی بازی ندارد). با کلیک روی هر محور زاویه‌ی دید توسعه‌دهنده بر روی همان محور عمود می‌شود. بدیهی است که دوربین بازی بر محور Z عمود است که باعث شده تا توهم نداشتن عمق القا شود.

### ابزارهای دگرگونی (Transform Tools)

از دیگر ابزارهای مدیریت صحنه می‌توان ابزارهای دگرگونی (Transform Tools) تولبار یونیتی را نام برد. در هر زمان تنها یکی از این ابزارها می‌تواند فعال باشد.

![image](/img/unity_editor_transform_tools.png)

ابزارهای دگرگونی دو دسته هستند. دسته‌ی اول ابزارهای ناوبری (navigation) در صحنه شامل ابزار تغییر مکان (Hand)، تغییر زاویه (Orbit) و تغییر میدان دید (Zoom) نمای صحنه. توسعه‌دهنده با drag کردن کلیدهای ماوس در نمای صحنه می‌تواند از این ابزارها به صورت زیر استفاده کند:

![image](/img/unity_editor_transform_tools_via_mouse.png)

یک راه دیگر برای گشت و گذار در نمای صحنه (در حالت سه‌بعدی) نگه داشتن کلیک راست و استفاده از کلیدهای WASD کیبورد (مشابه بازی‌های FPS) است.

ابزارهای دسته‌ی دوم برای تغییر مشخصات گیم آبجکت‌ها هستند که برای استفاده از آن‌ها باید ابتدا گیم آبجکت را با کلیک کردن روی آن در نمای صحنه (یا اسم آن در پنجره‌ی Hierarchy) انتخاب کرد. این ابزارها عبارتند از:

![image](/img/unity_editor_transform_tools_via_keyboard.png)

* ابزار Move: برای جابجا کردن گیم آبجکت استفاده می‌شود. پس از انتخاب این ابزار پیکان‌هایی در راستای محورهای مختصات بر روی گیم آبجکت ظاهر می‌شوند که به drag کردن آن‌ها می‌توان گیم آبجکت را در راستای مربوطه حرکت داد.

* ابزار Rotate: برای چرخاندن گیم آبجکت استفاده می‌شود.

* ابزار Scale: برای تغییر اندازه‌ی گیم آبجکت استفاده می‌شود.

* ابزار RectTransform: از سه ابزار قبلی بیشتر برای گیم آبجکت‌های سه‌بعدی استفاده می‌شود. برای گیم آبجکت‌های دوبعدی از ابزار RectTransform استفاده شده که در اطراف گیم آبجکت چهار گیره ایجاد کرده که امکان تغییر اندازه از طریق آن‌ها وجود داشته و با drag خود گیم آبجکت هم می‌توان به جابجایی آن پرداخت.

* ابزار Transform: این ابزار به تازگی اضافه شده و ترکیبی از سه ابزار Move و Rotate و Scale است.

تغییرات لازم به ندرت از طریق این ابزارها بر روی گیم آبجکت اعمال می‌شود و اکثر توسعه‌دهندگان مقادیر مدنظر را از طریق کامپوننت Transform گیم آبجکت (در پنجره‌ی Inspector) تغییر می‌دهند.

:::note نکته
در تولبار یونیتی دو دکمه‌ی به هم چسبیده وجود دارد که بر موقعیت‌یابی ابزارهای فوق تاثیر می‌گذارند:
:::

![image](/img/handle_position_buttons.png)

هر دکمه دو حالت دارد که با کلیک بر روی آن به حالت دیگر سوییچ می‌شود.

دکمه‌ی سمت راست Local/Global بوده که تعیین می‌کند هنگام انتخاب یک ابزار، محورهای مختصات بر روی گیم آبجکت منطبق باشد (Local) یا جهان بازی (Global)؛ به این معنی که در حالت Global محورهای مختصاتی که گیم آبجکت در راستای آن‌ها عملی را انجام می‌دهد همان محورهای مختصات جهان هستند در حالی که در حالت Local محورها بر گیم آبجکت منطبق بوده و برای مثال با چرخش ۹۰ درجه‌ی گیم آبجکت محور x عمودی و محور y افقی شده و اعمالی مثل حرکت در راستای محورهای جابجا شده انجام خواهد شد.

دکمه‌ی سمت راست نیز Pivot/Center بوده که تعیین می‌کند که ابزار در نقطه‌ی ثقل گیم آبجکت قرار بگیرد (Pivot) و یا در مرکز آن (Center).

کلید میانبر این دو دکمه در کیبورد X و Z است.

### سایر دکمه‌های نوار کنترل نمای صحنه

* دکمه‌ی دارای آیکون خورشید در نوار بالای نمای صحنه گیم آبجکت‌های نور را فعال/غیرفعال می‌کند. گیم آبجکت‌های نوردهی در اکثر اوقات تنها در بازی‌های سه‌بعدی استفاده می‌شوند (مگر در بازی‌های دوبعدی با گرافیک خیلی پیشرفته)؛ چرا که در بازی‌های دوبعدی اغلب از اسپرایت‌های png استفاده می‌شود که به نور حساس نیستند (نور بر روشنایی آن‌ها تاثیری ندارد).

* دکمه‌ی دارای آیکون بلندگو صدای صحنه را فعال/غیرفعال می‌کند.

* دکمه‌ی دارای آیکون تصویر وظیفه‌ی فعال/غیرفعال کردن افکت‌های صحنه را برعهده دارد. با کلیک بر روی آن تمام افکت‌ها فعال/غیرفعال شده و یا می‌توان با کلیک بر روی مثلت کوچک کنارش انواع افکت‌ها را به تفکیک فعال/غیرفعال نمود.

* دکمه‌ی Gizmos وظیفه‌ی فعال/غیرفعال کردن Gizmoها را بر عهده دارد. Gizmo به خطوط و اشکال راهنما گفته می‌شود که تنها برای توسعه‌دهنده قابل مشاهده هستند.

## نمای بازی (Game)

![image](/img/unity_editor_game_window.png)

این نمایی است که بازیکن از صحنه خواهد داشت و توسط Main Camera (یا دوربین دیگری) رندر شده است. با استفاده از منوی Display نوار کنترل می‌توان خروجی رندر شده از سایر دوربین‌ها (در صورت وجود) را مشاهده کرد. در پروژه‌های دوبعدی یک صحنه‌ی خالی در پنجره‌ی Game به صورت صفحه‌ای آبی رنگ است؛ اما در پروژه‌های سه‌بعدی آسمان و افق دیده می‌شود که به دلیل وجود اسکای باکس (جعبه‌ی آسمان) پیش‌فرض یونیتی می‌باشد.

:::note نکته
در نمای Scene با کلیک روی هر دوربین در پنجره‌ی Hierarchy نمایی از دکوپاژ رندر شده توسط آن دوربین در گوشه‌ی پایین و سمت راست نمای Scene نمایش داده می‌شود که می‌تواند نیاز به مراجعه پنجره‌ی Game را برای مواقعی که به مشاهده‌ی دقیق احتیاج ندارد رفع کند.
:::

بعد از اجرا کردن بازی در ادیتور (که درباره‌ی آن توضیح خواهیم داد) در این پنجره است که می‌توان بازی را مشاهده و امتحان کرد و با آن تعامل داشت. در این پنجره امکان ویرایش یا تغییر هیچ‌چیز وجود ندارد و صرفاً نمایی از آن‌چه که بازی پس از خروجی گرفته شدن، در سیستم بازیکن به نظر خواهد رسید می‌باشد. البته ماجرا به این سادگی نیست و بسته به رزولوشن صفحه‌نمایش کاربر هر بازیکن ممکن است تجربه‌ی متفاوتی از تصویری که دریافت می‌کند داشته باشد. با استفاده از منوی Aspect نوار کنترل این پنجره (که در حالت پیش‌فرض بر روی گزینه‌ی Free Aspect قرار دارد) می‌توان خروجی بازی را در رزولوشن‌ها و نسبت‌های تصویر مختلف مشاهده کرد. گزینه‌های این منو مشخصات اکثر دیوایس‌های پراستفاده را در خود دارد؛ اما امکان افزودن مشخصات دلخواه نیز وجود دارد. گزینه‌ی Free Aspect نمایانگر رزولوشن یا نسبت تصویر خاصی نیست و هنگام فعال بودن آن، با تغییر اندازه‌ی پنجره‌ی Game تصویر مجدداً متناسب با ابعاد جدید رندر می‌شود.

### سایر دکمه‌های نوار کنترل نمای بازی

* فعال بودن دکمه‌ی Maximize On Play نوار کنترل باعث می‌شود تا هنگام اجرای بازی این پنجره به صورت تمام‌صفحه درآمده تا امکان بررسی دقیق‌تر بازی وجود داشته باشد. این عمل ممکن است آزاردهنده باشد؛ به همین دلیل اکثر توسعه‌دهندگان از دو مانیتور به صورت همزمان استفاده می‌کنند و پنجره‌ی Game را به مانیتور دوم انتقال می‌دهند.

* دکمه‌ی Mute Audio صدای بازی را در حالت پخش فعال/غیرفعال می‌کند.

* دکمه‌ی Stats پنجره‌ای تحت عنوان Rendering Statistics را در گوشه‌ی پنجره‌ی Game نمایان می‌کند که اطلاعاتی از قبیل فریم‌ریت، رزولوشن، تعداد درخواست‌ها به CPU و… را نشان می‌دهد. از این اطلاعات برای بررسی بهینه بودن بازی استفاده می‌شود.

* دکمه‌ی Gizmos وظیفه‌ی فعال/غیرفعال کردن Gizmoها را بر عهده دارد.

:::note نکته
استفاده از دو صفحه‌نمایش به صورت همزمان در میان توسعه‌دهندگان امری معمول بوده و سرعت عمل توسعه را بسیار بالا می‌برد. اصولاً توسعه‌دهندگان حرفه‌ای در صفحه‌نمایش اصلی اقدام به طراحی و کدنویسی کرده و نتیجه را در صفحه‌ی دوم بررسی می‌کنند. البته هنگام شروع بازی‌سازی و طی روند آموزش نیازی به صرف چنین هزینه‌هایی نیست.
:::

## پنجره‌ی Hierarchy

![image](/img/unity_editor_hierarchy_window.png)

این پنجره (که “هایه-رار-کی” تلفظ می‌شود و به معنی سلسله مراتب است) شامل لیستی می‌باشد که تمام گیم آبجکت‌های موجود در صحنه را در خود جای داده است. با کلیک روی هر گزینه، گیم آبجکت به حالت انتخاب درآمده و مشخصات آن (کامپوننت‌ها) در پنجره‌ی Inspector نمایش داده می‌شود. با دوبار کلیک گیم آبجکت در مرکز نمای صحنه قرار می‌گیرد.

:::note نکته
در نسخه‌های جدید یونیتی در پنجره‌ی Hierarchy علاوه بر گیم آبجکت‌ها، نام صحنه نیز در بالای لیست گیم آبجکت‌ها نمایش داده می‌شود. به این جهت که در نسخه‌های جدید یونیتی می‌توان گیم آبجکت‌های چند صحنه را به طور همزمان مدیریت کرد. برای اطلاعات بیشتر به مقاله‌ی Multi-Scene editing داکیومنتیشن یونیتی مراجعه کنید.
:::

برای ساخت گیم آبجکت جدید از منوی Create نوار کنترل این پنجره استفاده می‌شود. در بیشتر اوقات در روند توسعه گیم آبجکتی خالی ساخته شده و با افزودن کامپوننت‌ها به آن هویت و هدف مشخصی داده می‌شود.

گیم آبجکت‌ها این قابلیت را دارند که زیرمجموعه‌ی گیم آبجکت دیگری شوند (که در طراحی بازی بسیار کاربردی است). برای این کار گیم آبجکت فرزند را در این لیست بر روی گیم آبجکت والد موردنظر drag می‌کنیم.

## پنجره‌ی Inspector

![image](/img/unity_editor_inspector_window.png)

از این پنجره اغلب برای تغییر تنظیمات اجزای بازی (فارغ از پنجره‌ای که در آن قرار دارند) استفاده می‌شود. این پنجره متناسب با نوع جزء انتخاب شده (asset یا گیم آبجکت) تغییر می‌کند. حالت‌های مختلف را با هم بررسی می‌کنیم:

* هنگام انتخاب یک گیم آبجکت (با کلیک بر روی آن در نمای صحنه و یا نام آن از پنجره‌ی Hierarchy) کامپوننت‌های گیم آبجکت انتخاب شده در این پنجره نمایش داده خواهد شد.

* هنگام انتخاب یک asset (با کلیک بر روی آن در پنجره‌ی Project) تنظیمات آن (که بسته به فرمت فایل تغییر می‌کند) در این پنجره مشاهده خواهد شد. این تنظیمات در فایل متای asset موردنظر ذخیره می‌شوند.

* همچنین هنگام ورود به هر یک از تنظیمات پروژه (ورودی‌ها، برچسب‌ها و لایه‌ها، زمان، فیزیک و…) از طریق منوی Edit و زیرمنوی Project Settings، فیلدهای تنظیمات در این پنجره قرار می‌گیرند.

## تولبار یونیتی

![image](/img/unity_editor_toolbar.png)

تولبار یونیتی شامل بخش‌های مختلفی است که از چپ به راست عبارتند از:

* ابزارهای دگرگونی
* سوییچ‌های Local/Global و Pivot/Center
* دکمه‌های کنترل پخش که برای اجرای بازی در پنجره‌ی Game استفاده می‌شوند.

![image](/img/unity_editor_play_buttons.png)

* دکمه‌ی کلاود برای باز کردن پنجره‌ی Unity Services (که احتمالاً در ایران کاربرد ندارد)
* منوی آبشاری Account که برای دسترسی به اکانت یونیتی وارد شده در برنامه استفاده می‌شود.
* منوی آبشاری Layers که برای نمایش/پنهان کردن و مدیریت لایه‌های بازی استفاده می‌شود. این منو شباهت زیادی به پنل Layers فتوشاپ دارد.
* منوی آبشاری Layout که برای تغییر و مدیریت چینش ادیتور استفاده می‌شود.

## سایر پنجره‌های ادیتور یونیتی

به جز پنجره‌هایی که بررسی کردیم، پنجره‌های دیگری نیز در ادیتور وجود دارد که برای دیباگ و مدیریت خطا، انیمیشن‌سازی، بهینه‌سازی بازی و… استفاده می‌شوند. به دلیل تخصصی بودن این پنجره‌ها، بررسی آن‌ها در قسمت‌های مربوط به خودشان انجام خواهد شد.