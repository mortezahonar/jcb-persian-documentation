# Joomla Component Builder - Beginner-Friendly Guide
# جوملا کامپوننت بیلدر - راهنمای ساده و روان

This guide provides a practical, beginner-friendly overview of how to use **Joomla Component Builder (JCB)** based on the *Introduction to Joomla Component Builder* tutorial.
این راهنما مروری ساده، روان و عملی از نحوه استفاده از **جوملا کامپوننت بیلدر (JCB)** بر اساس آموزش *مقدمه‌ای بر جوملا کامپوننت بیلدر* ارائه می‌دهد.
It explains the essential workflow, tools, and best practices - with accurate, up-to-date details reflecting the latest JCB UI and behavior.
گردش کار ضروری، ابزارها و بهترین روش‌ها را توضیح می‌دهد - با جزئیات دقیق و به‌روز که منعکس‌کننده آخرین رابط کاربری و رفتار JCB است.

---

## 1) Prerequisites & Mindset
## ۱) پیش‌نیازها و ذهنیت

[00:00:18](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h00m18s)

JCB is designed for developers familiar with **PHP** and the **Joomla MVC framework**.
JCB برای توسعه‌دهندگانی طراحی شده است که با **PHP** و **چارچوب MVC جوملا** آشنا هستند.

* **PHP knowledge:** The builder automates large parts of code generation but expects that you can understand and edit PHP.
* **آشنایی با PHP:** بیلدر بخش بزرگی از تولید کد را خودکار می‌کند اما انتظار دارد بتوانید PHP را درک و ویرایش کنید.
* **Learning Joomla's API:** Explore Joomla's core structure (models, views, controllers) to understand how JCB-generated components fit in. Open the Joomla `/components` directory, browse its folders, and inspect how core components are structured.
* **یادگیری API جوملا:** ساختار هسته جوملا (مدل‌ها، ویوها، کنترلرها) را بررسی کنید تا بفهمید کامپوننت‌های تولیدشده با JCB چگونه در آن جای می‌گیرند. پوشه `/components` جوملا را باز کنید، پوشه‌های آن را مرور کنید و ببینید کامپوننت‌های هسته چگونه ساختاردهی شده‌اند.
* **Using an IDE (e.g., NetBeans):** You can jump to function definitions (like `getLayout`) to trace how Joomla handles rendering.
* **استفاده از IDE (مثلاً NetBeans):** می‌توانید به تعریف توابع (مانند `getLayout`) بروید تا ببینید جوملا رندرینگ را چگونه مدیریت می‌کند.

*Tip:* If you're new to PHP or Joomla MVC, consider online developer courses before diving deeper.
*نکته:* اگر هنوز با PHP یا MVC جوملا آشنا نیستید، پیش از ورود عمیق‌تر، دوره‌های آنلاین توسعه‌دهندگی را در نظر بگیرید.

---

## 2) Local Development Environment
## ۲) محیط توسعه محلی

[00:04:17](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h04m17s)

You should **build and test components offline** on a local sandbox environment.
باید کامپوننت‌ها را **به‌صورت آفلاین** در یک محیط آزمایشی محلی **ساخته و تست کنید**.

### Recommended Setup
### راه‌اندازی پیشنهادی

* **Operating System:** Ubuntu or another Linux distribution.
* **سیستم‌عامل:** اوبونتو یا یکی دیگر از توزیع‌های لینوکس.
* **Stack:** PHP, MySQL/MariaDB, and Joomla installed locally.
* **پشته نرم‌افزاری:** PHP، MySQL/MariaDB و جوملا که به‌صورت محلی نصب شده‌اند.
* **Debug Tools:** Add tools like Xdebug to inspect and debug your code efficiently.
* **ابزارهای اشکال‌زدایی:** ابزارهایی مانند Xdebug را اضافه کنید تا کد خود را به‌صورت کارآمد بررسی و اشکال‌زدایی کنید.

Developing locally lets you work offline, debug easily, and avoid server-related issues.
توسعه محلی به شما امکان می‌دهد آفلاین کار کنید، به‌راحتی اشکال‌زدایی کنید و از مشکلات مرتبط با سرور دور بمانید.

*Resource Suggestion:* The course *"Up and Running with Linux for PHP Developers with Jon Peck"* (Lynda.com) is a great starting point for setting up your environment.
*پیشنهاد منبع:* دوره *"Up and Running with Linux for PHP Developers with Jon Peck"* (Lynda.com) نقطه شروع خوبی برای راه‌اندازی محیط شماست.

---

## 3) Security and Offline Preference
## ۳) امنیت و ترجیح کار آفلاین

[00:07:51](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h07m51s)

Although JCB can run on a live server, it's best used **offline**.
اگرچه JCB می‌تواند روی سرور زنده اجرا شود، بهترین حالت استفاده از آن **آفلاین** است.

When compiling, JCB places your build temporarily in the Joomla `/tmp` directory.
هنگام کامپایل، JCB خروجی شما را به‌صورت موقت در پوشه `/tmp` جوملا قرار می‌دهد.
If hosted online, this could expose your compiled packages publicly.
اگر سایت روی هاست آنلاین باشد، این کار می‌تواند پکیج‌های کامپایل‌شده شما را به‌صورت عمومی در معرض دید قرار دهد.

To stay safe:
برای ایمن ماندن:

* Always develop locally when possible.
* تا حد امکان همیشه به‌صورت محلی توسعه دهید.
* If you must work online, delete temporary builds immediately after compiling.
* اگر مجبورید آنلاین کار کنید، بلافاصله پس از کامپایل، خروجی‌های موقت را حذف کنید.
* Limit server permissions to protect sensitive directories.
* برای محافظت از پوشه‌های حساس، دسترسی‌های سرور را محدود کنید.

---

## 4) Understanding the Purpose of JCB
## ۴) درک هدف JCB

[00:03:55](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h03m55s)

The **Joomla Component Builder** was created to **accelerate development** by automating repetitive code generation for Joomla components.
**جوملا کامپوننت بیلدر** برای **تسریع توسعه** با خودکارسازی تولید کدهای تکراری کامپوننت‌های جوملا ساخته شده است.

It:
این ابزار:

* Follows **Joomla conventions** closely.
* از **قراردادهای جوملا** پیروی نزدیکی می‌کند.
* Lets you **customize generated code** freely.
* به شما امکان می‌دهد **کد تولیدشده** را آزادانه **شخصی‌سازی** کنید.
* Supports **complex admin and site interfaces** using standard MVC structure.
* با استفاده از ساختار MVC استاندارد، از **رابط‌های پیچیده ادمین و سایت** پشتیبانی می‌کند.

You're encouraged to suggest improvements or share better implementation methods with the developer community.
شما تشویق می‌شوید بهبودهایی پیشنهاد دهید یا روش‌های پیاده‌سازی بهتری را با جامعه توسعه‌دهندگان به اشتراک بگذارید.

---

## 5) Creating Your First Component
## ۵) ساخت نخستین کامپوننت

[00:05:43](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h05m43s)

Once JCB is installed in your local Joomla site:
پس از نصب JCB در سایت جوملا محلی شما:

1. Go to **Components → Component Builder → Components → New**.
۱. به **Components → Component Builder → Components → New** بروید.
2. Enter:
۲. وارد کنید:

   * **Name:** The readable name of your component.
   * **Name:** نام خوانا و قابل‌فهم کامپوننت شما.
   * **Option:** Usually formatted as `com_example`.
   * **Option:** معمولاً به‌صورت `com_example` قالب‌بندی می‌شود.
   * **Description:** Short overview of purpose.
   * **Description:** مرور کوتاهی از هدف.
   * **Version:** Your current version number.
   * **Version:** شماره نسخه فعلی شما.
3. Save the new component.
۳. کامپوننت جدید را ذخیره کنید.

You now have the foundation for your custom extension.
اکنون پایه و اساس افزونه سفارشی خود را دارید.

> 📘 Want a refresher on what the component controls? Review [Joomla Components in JCB](./Joomla-Components.md) to see how views, helpers, assets, and packaging metadata all converge inside this single definition.
> 📘 می‌خواهید مرور تازه‌ای بر آنچه کامپوننت کنترل می‌کند داشته باشید؟ [کامپوننت‌های جوملا در JCB](./Joomla-Components.md) را مرور کنید تا ببینید ویوها، هلپرها، دارایی‌ها و متادیتای پکیجینگ چگونه همه در همین تعریف واحد جمع می‌شوند.

---

## 6) Adding Admin Views and Fields
## ۶) افزودن ویوهای ادمین و فیلدها

[00:06:07](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h06m07s)

Admin views define the **backend structure** and determine how data is managed.
ویوهای ادمین **ساختار بک‌اند** را تعریف می‌کنند و تعیین می‌کنند داده‌ها چگونه مدیریت شوند.

### Steps to Add an Admin View:
### مراحل افزودن یک ویوی ادمین:

1. Navigate to **Admin Views → New**.
۱. به **Admin Views → New** بروید.
2. Choose between:
۲. بین این‌ها انتخاب کنید:

   * **Item View** (single record)
   * **ویوی آیتم** (تک‌رکورد)
   * **List View** (multiple records)
   * **ویوی لیست** (چند رکورد)
3. Link the view to a **database table** (JCB auto-generates this table).
۳. ویو را به یک **جدول دیتابیس** متصل کنید (JCB این جدول را به‌صورت خودکار تولید می‌کند).
4. Configure ACL (permissions), toolbar options, and category/tag support.
۴. ACL (دسترسی‌ها)، گزینه‌های نوار ابزار و پشتیبانی دسته‌بندی/برچسب را پیکربندی کنید.

### Adding Fields:
### افزودن فیلدها:

* Go to **Fields → New**.
* به **Fields → New** بروید.
* Define field type (text, list, media, repeatable, etc.).
* نوع فیلد را تعریف کنید (متن، لیست، رسانه، تکرارشونده و غیره).
* Assign the field to the correct admin view.
* فیلد را به ویوی ادمین درست اختصاص دهید.
* Configure validation rules, default values, and filters.
* قواعد اعتبارسنجی، مقادیر پیش‌فرض و فیلترها را پیکربندی کنید.

Fields can be reused across views, plugins, and modules.
فیلدها را می‌توان در ویوها، پلاگین‌ها و ماژول‌های مختلف دوباره استفاده کرد.

---

## 7) Building Frontend (Site) Views
## ۷) ساخت ویوهای فرانت‌اند (سایت)

[00:07:24](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h07m24s)

Frontend or "site" views define what visitors see on your website.
ویوهای فرانت‌اند یا "سایت" تعریف می‌کنند که بازدیدکنندگان در وب‌سایت شما چه می‌بینند.

### Steps:
### مراحل:

1. Go to **Site Views → New**.
۱. به **Site Views → New** بروید.
2. Choose between **List** or **Item** view types.
۲. بین نوع ویوهای **لیست** یا **آیتم** انتخاب کنید.
3. Connect the site view to its corresponding table or Dynamic GET.
۳. ویوی سایت را به جدول متناظر یا Dynamic Get آن متصل کنید.
4. Define templates and layouts to control how data is displayed.
۴. قالب‌ها و لایه‌ها را برای کنترل نحوه نمایش داده‌ها تعریف کنید.

Templates allow page-level customization, while layouts define smaller view sections.
قالب‌ها شخصی‌سازی در سطح صفحه را امکان‌پذیر می‌کنند، در حالی که لایه‌ها بخش‌های کوچک‌تری از ویو را تعریف می‌کنند.

---

## 8) Using Dynamic GETs
## ۸) استفاده از Dynamic Get‌ها

[00:08:14](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h08m14s)

**Dynamic GETs** are JCB's **visual query builder**, letting you create advanced database queries without manual SQL.
**Dynamic Get‌ها** **کوئری‌ساز بصری** JCB هستند که به شما امکان می‌دهند بدون SQL دستی، کوئری‌های پیشرفته دیتابیس بسازید.

Use a Dynamic GET when:
وقتی از یک Dynamic Get استفاده کنید که:

* You need to fetch data from multiple tables.
* نیاز دارید داده‌ها را از چند جدول دریافت کنید.
* You want to apply filters, joins, or ordering visually.
* می‌خواهید فیلترها، جوین‌ها یا ترتیب‌دهی را به‌صورت بصری اعمال کنید.

### To Create a Dynamic GET:
### برای ایجاد یک Dynamic Get:

1. Go to **Dynamic GETs → New**.
۱. به **Dynamic GETs → New** بروید.
2. Select a **base table**.
۲. یک **جدول پایه** انتخاب کنید.
3. Add **joins**, **fields**, and **filters**.
۳. **جوین‌ها**، **فیلدها** و **فیلترها** را اضافه کنید.
4. Save it and link it to a **Site View** or **Admin Report View**.
۴. آن را ذخیره کنید و به یک **ویوی سایت** یا **ویوی گزارش ادمین** متصل کنید.

This feature keeps your logic organized and reusable across multiple layouts.
این قابلیت منطق شما را سازمان‌یافته و در چند لایه قابل‌استفاده مجدد نگه می‌دارد.

---

## 9) Compiling and Installing the Component
## ۹) کامپایل و نصب کامپوننت

[00:08:51](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h08m51s)

After defining views, fields, and templates, it's time to build your installable component.
پس از تعریف ویوها، فیلدها و قالب‌ها، وقت آن است که کامپوننت قابل‌نصب خود را بسازید.

### Compile Steps:
### مراحل کامپایل:

1. From the **Component list**, click **Compile**.
۱. از **لیست کامپوننت‌ها**، روی **Compile** کلیک کنید.
2. Choose:
۲. انتخاب کنید:

   * **Test Mode (Dry Run):** Generate code without installation.
   * **حالت تست (Dry Run):** تولید کد بدون نصب.
   * **Normal Build:** Create an installable ZIP file.
   * **بیلد معمولی:** ایجاد یک فایل ZIP قابل‌نصب.
3. After successful build:
۳. پس از ساخت موفق:

   * You can **install directly** from JCB's compiler view, or
   * می‌توانید **مستقیماً** از ویوی کامپایلر JCB **نصب** کنید، یا
   * Upload the ZIP via Joomla's **Extensions → Install**.
   * فایل ZIP را از طریق **Extensions → Install** جوملا بارگذاری کنید.

Verify that:
بررسی کنید که:

* Backend views load correctly under **Components → Your Component**.
* ویوهای بک‌اند زیر **Components → Your Component** به درستی بارگذاری شوند.
* Site menu items link to frontend views as expected.
* آیتم‌های منوی سایت همان‌طور که انتظار می‌رود به ویوهای فرانت‌اند لینک شوند.

---

## 10) Contributing and Feature Requests
## ۱۰) مشارکت و درخواست‌های قابلیت

[00:09:50](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h09m50s)

The developer encourages collaboration to ensure JCB's ongoing improvement.
توسعه‌دهنده همکاری را تشویق می‌کند تا بهبود مستمر JCB تضمین شود.

If you encounter issues or have feature suggestions:
اگر با مشکلی مواجه شدید یا پیشنهاد قابلیتی دارید:

* Report them publicly on GitHub under the **Issues** section.
* آن‌ها را به‌صورت عمومی در گیت‌هاب، زیر بخش **Issues** گزارش دهید.
* Start new **feature requests** there.
* **درخواست‌های قابلیت** جدید را آنجا آغاز کنید.
* For sponsored development or priority requests, you can reach out directly to the maintainer.
* برای توسعه با حمایت مالی یا درخواست‌های اولویت‌دار، می‌توانید مستقیماً با نگه‌دارنده تماس بگیرید.

Engaging publicly ensures that discussions and resolutions benefit everyone.
مشارکت عمومی تضمین می‌کند که بحث‌ها و راه‌حل‌ها به نفع همه باشد.

---

## 11) Supporting the Project
## ۱۱) حمایت از پروژه

[00:08:51](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h08m51s)

Since JCB is free, users are asked **not to distribute the training videos** without permission.
از آنجا که JCB رایگان است، از کاربران خواسته می‌شود **ویدیوهای آموزشی را** بدون اجازه **توزیع نکنند**.
If you find value in the tool and it saves you time, consider contributing financially to help fund continued development.
اگر این ابزار برای شما ارزشمند است و وقت شما را صرفه‌جویی می‌کند، مشارکت مالی را برای تأمین بودجه توسعه مستمر در نظر بگیرید.

Your support helps sustain improvements for the whole Joomla developer community.
حمایت شما به پایداری بهبودها برای کل جامعه توسعه‌دهندگان جوملا کمک می‌کند.

---

## 12) Summary - Complete Workflow
## ۱۲) خلاصه - گردش کار کامل

[00:11:09](https://www.youtube.com/watch?v=9evJkBTnKxE&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h11m09s)

1. **Set up** a local Joomla environment.
۱. یک محیط جوملا محلی **راه‌اندازی** کنید.
2. **Install** Joomla Component Builder.
۲. جوملا کامپوننت بیلدر را **نصب** کنید.
3. **Create** your component (base configuration).
۳. کامپوننت خود را **ایجاد** کنید (پیکربندی پایه).
4. **Add** Admin Views and Fields.
۴. ویوهای ادمین و فیلدها را **اضافه** کنید.
5. **Build** Site Views and Templates.
۵. ویوهای سایت و قالب‌ها را **بسازید**.
6. **Use Dynamic GETs** for complex queries.
۶. برای کوئری‌های پیچیده از **Dynamic Get‌ها** استفاده کنید.
7. **Compile and Test** using Dry Run mode.
۷. با استفاده از حالت Dry Run **کامپایل و تست** کنید.
8. **Install** and verify functionality.
۸. **نصب** کنید و عملکرد را بررسی کنید.
9. **Refine and iterate** until stable.
۹. تا رسیدن به پایداری، **بهبود و تکرار** کنید.
10. **Contribute** to the JCB community.
۱۰. در جامعه JCB **مشارکت** کنید.

---