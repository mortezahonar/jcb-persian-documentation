# Start Here: Onboarding Guide for Joomla Component Builder
# از اینجا شروع کنید: راهنمای ورود به جوملا کامپوننت بیلدر

## What this page does
## این صفحه چه کاری انجام می‌دهد

Joomla Component Builder (JCB) packs years of community knowledge into one documentation set. This page curates the most important links and concepts so that a newcomer can move from “I have Joomla experience” to “I can ship a JCB component” without getting lost in the library. Use it together with the [Home](./index.md) index: Start Here gives you the narrative path, while Home provides a chapter-by-chapter reference.
جوملا کامپوننت بیلدر (JCB) سال‌ها دانش جامعه را در یک مجموعه مستندات جمع کرده است. این صفحه مهم‌ترین لینک‌ها و مفاهیم را گردآوری می‌کند تا یک تازه‌وارد بتواند از "تجربه جوملا دارم" به "می‌توانم یک کامپوننت JCB تحویل بدهم" برسد، بدون اینکه در کتابخانه گم شود. از آن همراه با [خانه](./index.md) استفاده کنید: **شروع از اینجا** مسیر روایی را می‌دهد، در حالی که **خانه** مرجعی فصل‌به‌فصل ارائه می‌دهد.

---

## Step 1 – Understand the landscape
## قدم ۱ – درک فضای کلی

1. **See the big picture of a component** so you understand what JCB ultimately packages. [Joomla Components in JCB](./Joomla-Components.md) explains how every view, helper, script, and configuration ends up inside the compiled extension.
۱. **تصویر بزرگ یک کامپوننت را ببینید** تا بفهمید JCB در نهایت چه چیزی را بسته‌بندی می‌کند. [کامپوننت‌های جوملا در JCB](./Joomla-Components.md) توضیح می‌دهد که چگونه هر ویو، هلپر، اسکریپت و پیکربندی در نهایت درون افزونه کامپایل‌شده قرار می‌گیرد.
2. **Review Joomla's MVC structure** to see how administrator and site applications mirror each other, how controllers, models, and views are named, and how packages are assembled. [Component Structure and MVC Implementation](./Component-Structure-and-MVC-Implementation.md) bridges the gap between Joomla theory and JCB's automation.
۲. **ساختار MVC جوملا را مرور کنید** تا ببینید اپلیکیشن‌های ادمین و سایت چگونه یکدیگر را آینه می‌کنند، کنترلرها، مدل‌ها و ویوها چگونه نام‌گذاری می‌شوند و پکیج‌ها چگونه مونتاژ می‌شوند. [ساختار کامپوننت و پیاده‌سازی MVC](./Component-Structure-and-MVC-Implementation.md) فاصله بین تئوری جوملا و خودکارسازی JCB را پر می‌کند.
3. **Clarify the JCB workflow mindset**—what the tool automates, what remains in your control, and how Dynamic Gets act as graphically designed database queries that feed your views. [Joomla Component Builder – Beginner-Friendly Guide](./Intro-to-JCB.md) summarises prerequisites, environment expectations, and the overall build loop, while the updated [Dynamic Get overview](./dynamicGet.md#overview) explains how the visual query builder maps to generated models.
۳. **ذهنیت گردش کار JCB را روشن کنید** — ابزار چه چیزی را خودکار می‌کند، چه چیزی در کنترل شما می‌ماند، و Dynamic Get‌ها چگونه به‌عنوان کوئری‌های دیتابیس گرافیکی عمل می‌کنند که ویوهای شما را تغذیه می‌کنند. [جوملا کامپوننت بیلدر – راهنمای ساده و روان](./Intro-to-JCB.md) پیش‌نیازها، انتظارات محیطی و چرخه کلی ساخت را خلاصه می‌کند، در حالی که [مرور Dynamic Get](./dynamicGet.md#overview) به‌روزشده توضیح می‌دهد کوئری‌ساز بصری چگونه به مدل‌های تولیدشده نگاشت می‌شود.
4. **Map the database-to-interface relationship** so you know how admin views, site views, and fields combine to deliver data to users. Start with the new [JCB Fields primer](./JCB-Fields.md) to see how a single field definition controls storage, rendering, validation, and sharing. Then use [General Planning](./General-Planning.md) and [Field Types](./Field-Types.md) to plan entities, choose field types, and prepare for compilation, while the refreshed [Adding Site Views](./Adding-Site-Views-to-a-Component.md) guide explains how Dynamic Gets, templates, layouts, reusable code blocks, and libraries assemble the public experience.
۴. **رابطه دیتابیس-واسط را مپ کنید** تا بدانید ویوهای ادمین، ویوهای سایت و فیلدها چگونه با هم ترکیب می‌شوند و داده‌ها را به کاربران می‌رسانند. با [آشنایی با فیلدهای JCB](./JCB-Fields.md) شروع کنید تا ببینید یک تعریف فیلد چگونه ذخیره‌سازی، رندر، اعتبارسنجی و اشتراک‌گذاری را کنترل می‌کند. سپس از [طرح‌ریزی عمومی](./General-Planning.md) و [انواع فیلد](./Field-Types.md) برای برنامه‌ریزی موجودیت‌ها، انتخاب انواع فیلد و آماده‌سازی برای کامپایل استفاده کنید، در حالی که راهنمای به‌روزشده [افزودن ویوهای سایت](./Adding-Site-Views-to-a-Component.md) توضیح می‌دهد Dynamic Get‌ها، قالب‌ها، لایه‌ها، بلوک‌های کد قابل‌استفاده مجدد و کتابخانه‌ها چگونه تجربه عمومی را می‌سازند.

> 🧭 **Outcome:** you should be able to describe the main Joomla directories, explain how JCB mirrors them, and articulate the planning steps before touching the builder interface.
> 🧭 **نتیجه:** باید بتوانید پوشه‌های اصلی جوملا را توصیف کنید، توضیح دهید JCB چگونه آن‌ها را آینه می‌کند، و مراحل برنامه‌ریزی را پیش از دست زدن به رابط بیلدر بیان کنید.

---

## Step 2 – Prepare your toolchain
## قدم ۲ – آماده‌سازی ابزارهای خود

1. **Set up a local Joomla environment** using the OctoJoom toolchain, which provisions Joomla's official Docker containers and Traefik for you. Follow [Setup Local Development Environment with OctoJoom](./Setup-Local-Development-Environment-with-OctoJoom.md) for a guided walkthrough, or replicate the same containerised requirements manually.
۱. **یک محیط جوملا محلی راه‌اندازی کنید** با استفاده از مجموعه ابزار OctoJoom، که کانتینرهای رسمی Docker جوملا و Traefik را برای شما فراهم می‌کند. برای راهنمای گام‌به‌گام، [راه‌اندازی محیط توسعه محلی با OctoJoom](./Setup-Local-Development-Environment-with-OctoJoom.md) را دنبال کنید یا همان نیازمندی‌های کانتینری را به‌صورت دستی بازسازی کنید.
2. **Install Joomla Component Builder** using the [Installation walkthrough](./Installation-of-JCB.md) (single public package, compiler usage, clearing temporary files).
۲. **جوملا کامپوننت بیلدر را نصب کنید** با استفاده از [راهنمای نصب](./Installation-of-JCB.md) (پکیج عمومی واحد، نحوه استفاده از کامپایلر، پاک‌سازی فایل‌های موقت).
3. **Verify PHP and server requirements** so compilation succeeds. The [PHP Settings reference](./PHP-Settings.md) lists recommended configuration values and troubleshooting tips.  
۳. **نیازمندی‌های PHP و سرور را بررسی کنید** تا کامپایل موفق باشد. [مرجع تنظیمات PHP](./PHP-Settings.md) مقادیر پیکربندی پیشنهادی و نکات عیب‌یابی را فهرست می‌کند.  
4. **Import demo data (optional)** to explore working examples. The [Using the JCB Demo Component](./Using-the-JCB-Demo-Component-While-Building-Your-Local-Development-System.md) guide explains how to load and inspect it.
۴. **داده‌های نمایشی را وارد کنید (اختیاری)** تا مثال‌های عملی را کاوش کنید. راهنمای [استفاده از کامپوننت نمایشی JCB](./Using-the-JCB-Demo-Component-While-Building-Your-Local-Development-System.md) توضیح می‌دهد چگونه آن را بارگذاری و بررسی کنید.

> 🧭 **Outcome:** you have a working Joomla site with JCB installed, demo data available, and confidence that server settings will not block builds.
> 🧭 **نتیجه:** یک سایت جوملا کارآمد با JCB نصب‌شده، داده‌های نمایشی موجود و اطمینان از اینکه تنظیمات سرور ساخت‌ها را مسدود نمی‌کند، دارید.

---

## Step 3 – Build your first component
## قدم ۳ – ساخت نخستین کامپوننت

1. **Start with a guided example:** follow [Hello World with Joomla Component Builder](./Hello-World-with-Joomla-Component-Builder.md) to create a simple component from scratch, including admin and site views, menu links, and permissions.  
۱. **با یک مثال راهنما شروع کنید:** [هلو ورلد با جوملا کامپوننت بیلدر](./Hello-World-with-Joomla-Component-Builder.md) را دنبال کنید تا یک کامپوننت ساده از صفر بسازید، شامل ویوهای ادمین و سایت، لینک‌های منو و دسترسی‌ها.  
2. **Reinforce the foundations** by revisiting [Basic Fields](./Basic-Fields.md), [Admin Views](./Admin-Views.md), and the [JCB Admin Views feature deep dive](./Features/JCB-Admin-Views.md) to understand how fields populate lists and forms while the builder automates the surrounding MVC code.
۲. **پایه‌ها را تقویت کنید** با مرور [فیلدهای پایه](./Basic-Fields.md)، [ویوهای ادمین](./Admin-Views.md) و [بررسی عمیق قابلیت ویوهای ادمین JCB](./Features/JCB-Admin-Views.md) تا بفهمید فیلدها چگونه لیست‌ها و فرم‌ها را پر می‌کنند در حالی که بیلدر کد MVC اطراف را خودکار می‌کند.
3. **Practice compilation and installation** by iterating through small changes, recompiling, and reinstalling within Joomla using the instructions in the Hello World tutorial and [Field Types](./Field-Types.md#5-compiling-and-installing-your-component).  
۳. **کامپایل و نصب را تمرین کنید** با تکرار تغییرات کوچک، کامپایل مجدد و نصب دوباره در جوملا با استفاده از دستورالعمل‌های آموزش هلو ورلد و [انواع فیلد](./Field-Types.md#5-compiling-and-installing-your-component).  
4. **Document your learning**—update component notes, track field names, and keep a changelog. This habit will ease later export/import or collaboration tasks.
۴. **یادگیری خود را مستند کنید** — یادداشت‌های کامپوننت را به‌روز کنید، نام فیلدها را پیگیری کنید و یک تغییر لاگ نگه دارید. این عادت کارهای بعدی واردات/صادرات یا همکاری را آسان‌تر می‌کند.

> 🧭 **Outcome:** you can create a functioning component, compile it, install it, and recognise how admin data flows to the site frontend.
> 🧭 **نتیجه:** می‌توانید یک کامپوننت کارآمد بسازید، آن را کامپایل و نصب کنید و تشخیص دهید داده‌های ادمین چگونه به فرانت‌اند سایت جریان می‌یابند.

---

## Step 4 – Explore core building blocks
## قدم ۴ – کاوش بلوک‌های سازنده اصلی

| Concept | Why it matters | Key resources |
| مفهوم | چرا اهمیت دارد | منابع کلیدی |
| --- | --- | --- |
| **Planning views and fields** | Translating requirements into database tables, relationships, and permissions. | [General Planning](./General-Planning.md), [JCB Admin Views feature guide](./Features/JCB-Admin-Views.md), [Adding Admin Views](./Adding-Admin-Views-to-a-Component.md), [Adding Site Views](./Adding-Site-Views-to-a-Component.md) |
| **برنامه‌ریزی ویوها و فیلدها** | تبدیل نیازمندی‌ها به جدول‌های دیتابیس، روابط و دسترسی‌ها. | [طرح‌ریزی عمومی](./General-Planning.md), [راهنمای قابلیت ویوهای ادمین JCB](./Features/JCB-Admin-Views.md), [افزودن ویوهای ادمین](./Adding-Admin-Views-to-a-Component.md), [افزودن ویوهای سایت](./Adding-Site-Views-to-a-Component.md) |
| **Site View composition & reuse** | Design public layouts by pairing a main Dynamic Get with templates, layouts, custom code placeholders, and optional JS/CSS libraries, then manage updates through resets or forks. | [Adding Site Views](./Adding-Site-Views-to-a-Component.md), [Adding Templates & Layouts](./Adding-Templates-and-Layouts-to-a-Site-View.md), [JCB Layouts](./JCB-Layouts.md), [dynamicGet](./dynamicGet.md) |
| **ترکیب و استفاده مجدد ویوی سایت** | طراحی لایه‌های عمومی با ترکیب یک Dynamic Get اصلی با قالب‌ها، لایه‌ها، پلیسهولدرهای کد سفارشی و کتابخانه‌های اختیاری JS/CSS؛ سپس مدیریت به‌روزرسانی‌ها از طریق بازنشانی یا فورک. | [افزودن ویوهای سایت](./Adding-Site-Views-to-a-Component.md), [افزودن قالب‌ها و لایه‌ها](./Adding-Templates-and-Layouts-to-a-Site-View.md), [لایه‌های JCB](./JCB-Layouts.md), [dynamicGet](./dynamicGet.md) |
| **Field types and validation** | Selecting the right inputs and enforcing correct data. | [JCB Fields](./JCB-Fields.md), [Field Types](./Field-Types.md), [Advanced Fields](./Advanced-Fields.md), [Adding Rule Validation](./Adding-your-own-rule-validation-to-a-field-in-JCB.md), [Easy Validation Rules](./Easy-Validation-Rules-for-Fields-in-JCB.md) |
| **انواع فیلد و اعتبارسنجی** | انتخاب ورودی‌های درست و اعمال داده صحیح. | [فیلدهای JCB](./JCB-Fields.md), [انواع فیلد](./Field-Types.md), [فیلدهای پیشرفته](./Advanced-Fields.md), [افزودن اعتبارسنجی قاعده](./Adding-your-own-rule-validation-to-a-field-in-JCB.md), [قواعد آسان اعتبارسنجی](./Easy-Validation-Rules-for-Fields-in-JCB.md) |
| **Dynamic data retrieval** | Combining records across tables without manual SQL. | [dynamicGet](./dynamicGet.md), [Add dynamicGet to a Site View](./Adding-dynamicGet-to-a-Site-View.md), [Automatic Custom Code Import](./Automatic-import-of-custom-code-during-compilation-in-JCB.md) |
| **دریافت پویای داده** | ترکیب رکوردها در بین جدول‌ها بدون SQL دستی. | [dynamicGet](./dynamicGet.md), [افزودن dynamicGet به یک ویوی سایت](./Adding-dynamicGet-to-a-Site-View.md), [واردات خودکار کد سفارشی](./Automatic-import-of-custom-code-during-compilation-in-JCB.md) |
| **Modules and placements** | Ship reusable widgets that surface component data in Joomla module positions and keep them synced via Reset/Fork workflows. | [JCB Joomla Modules](./Joomla-Modules.md) |
| **ماژول‌ها و جایگاه‌ها** | ویجت‌های قابل‌استفاده مجددی ارائه دهید که داده‌های کامپوننت را در جایگاه‌های ماژول جوملا نمایش می‌دهند و آن‌ها را از طریق گردش کارهای بازنشانی/فورک هم‌گام نگه می‌دارند. | [ماژول‌های جوملا JCB](./Joomla-Modules.md) |
| **Templates and layouts** | Wrap site/admin views with modular structures, nest layouts, and sync reusable markup from shared repositories. | [Templates & Layouts](./Adding-Templates-and-Layouts-to-a-Site-View.md), [Template Setup](./Template-Setup.md), [Layout Setup](./Layout-Setup.md) |
| **قالب‌ها و لایه‌ها** | ویوهای سایت/ادمین را با ساختارهای مدولار بپوشانید، لایه‌ها را تودرتو کنید و مارک‌آپ قابل‌استفاده مجدد را از مخازن مشترک هم‌گام کنید. | [قالب‌ها و لایه‌ها](./Adding-Templates-and-Layouts-to-a-Site-View.md), [راه‌اندازی قالب](./Template-Setup.md), [راه‌اندازی لایه](./Layout-Setup.md) |
| **Custom code and helpers** | Extending generated components safely with argument-aware snippets and hash automation. | [JCB Custom Codes Overview](./JCB-Custom-Codes.md), [Manual Custom Code Implementation](./JCB-manual-custom-code-implementation.md), [Helper Structures](./Adding-Helper-Structures-to-any-JCB-component.md), [Additional Helper Methods](./How-to-Add-More-Helper-Methods-to-Your-Components-Helper-Class.md) |
| **کد سفارشی و هلپرها** | گسترش امن کامپوننت‌های تولیدشده با قطعه‌کدهای آگاه از آرگومان و خودکارسازی هش. | [مرور کدهای سفارشی JCB](./JCB-Custom-Codes.md), [پیاده‌سازی دستی کد سفارشی](./JCB-manual-custom-code-implementation.md), [ساختارهای هلپر](./Adding-Helper-Structures-to-any-JCB-component.md), [متدهای هلپر اضافی](./How-to-Add-More-Helper-Methods-to-Your-Components-Helper-Class.md) |

> 💡 **Dynamic Gets refresher:** treat every main get as the canonical description of how a view sources its data. The visual builder lets you align joins, filters, ordering, and grouping without writing SQL, and the generated model code keeps those rules version-controlled alongside your templates.
> 💡 **مرور Dynamic Get‌ها:** هر Get اصلی را به‌عنوان توصیف معیار از نحوه دریافت داده‌ها توسط یک ویو در نظر بگیرید. کوئری‌ساز بصری به شما امکان می‌دهد جوین‌ها، فیلترها، ترتیب‌دهی و گروه‌بندی را بدون نوشتن SQL هماهنگ کنید، و کد مدل تولیدشده آن قواعد را نسخه‌کنترل‌شده در کنار قالب‌های شما نگه می‌دارد.

> 🧭 **Outcome:** you know where to deepen knowledge on each pillar as soon as your project requires it.
> 🧭 **نتیجه:** می‌دانید به محض اینکه پروژه‌تان لازم داشت، دانش خود را درباره هر رکن در کجا عمیق کنید.

---

## Step 5 – Choose your learning pathway
## قدم ۵ – مسیر یادگیری خود را انتخاب کنید

### 1. Project planning & collaboration
### ۱. برنامه‌ریزی پروژه و همکاری
- [Component Settings Deep Dive](./Component-Settings.md)
- [بررسی عمیق تنظیمات کامپوننت](./Component-Settings.md)
- [Component Settings](./Component-Settings-Overview.md)
- [تنظیمات کامپوننت](./Component-Settings-Overview.md)
- [Collaborative Workflow](./Proposed-Collaborative-Workflow-in-JCB.md)
- [گردش کار مشارکتی](./Proposed-Collaborative-Workflow-in-JCB.md)
- [Export/Import Fully Mapped Components](./Export-Import-of-fully-mapped-components.md)
- [صادرات/واردات کامپوننت‌های کاملاً مپ‌شده](./Export-Import-of-fully-mapped-components.md)
- [Automated Backup System](./Automated-backup-system-in-JCB.md)
- [سیستم پشتیبان‌گیری خودکار](./Automated-backup-system-in-JCB.md)

### 2. Data management & automation
### ۲. مدیریت داده و خودکارسازی
- [Tweaking MySQL Demo Data](./Tweaking-MySQL-Demo-Data.md)
- [تنظیم داده‌های نمایشی MySQL](./Tweaking-MySQL-Demo-Data.md)
- [Auto-create SQL Updates](./Auto-create-SQL-updates-for-Componets-in-JCB.md)
- [ایجاد خودکار به‌روزرسانی‌های SQL](./Auto-create-SQL-updates-for-Componets-in-JCB.md)
- [Automated Database Updates](./Automated-database-updates-in-Joomla-during-development-of-a-component.md)
- [به‌روزرسانی خودکار دیتابیس](./Automated-database-updates-in-Joomla-during-development-of-a-component.md)
- [JCB Custom Codes Overview](./JCB-Custom-Codes.md)
- [مرور کدهای سفارشی JCB](./JCB-Custom-Codes.md)
- [Reuse Custom Code](./Reuse-Custom-Code.md)
- [استفاده مجدد از کد سفارشی](./Reuse-Custom-Code.md)

### 3. User experience & site delivery
### ۳. تجربه کاربر و ارائه سایت
Combine layouts, Dynamic Gets, optional JavaScript/CSS libraries, and reusable custom code placeholders to craft polished administrator and frontend experiences that mirror your data model. Reset or fork Site Views when you need to sync with shared repositories or maintain long-term customisations.
لایه‌ها، Dynamic Get‌ها، کتابخانه‌های اختیاری JavaScript/CSS و پلیسهولدرهای کد سفارشی قابل‌استفاده مجدد را ترکیب کنید تا تجربه‌های جلا یافته ادمین و فرانت‌اند بسازید که مدل داده شما را آینه می‌کنند. وقتی نیاز به هم‌گام‌سازی با مخازن مشترک یا حفظ سفارشی‌سازی‌های بلندمدت دارید، ویوهای سایت را بازنشانی یا فورک کنید.
- [Custom Admin Views](./Custom-Admin-Views.md)
- [ویوهای ادمین سفارشی](./Custom-Admin-Views.md)
- [Setup Site Edit View](./Setup-Site-Edit-View-in-JCB.md)
- [راه‌اندازی ویوی ویرایش سایت](./Setup-Site-Edit-View-in-JCB.md)
- [Quick Hello World (accelerated build)](./The-Quick-Hello-Word-with-JCB.md)
- [هلو ورلد سریع (بیلد سریع)](./The-Quick-Hello-Word-with-JCB.md)
- [Custom Dashboard Option](./The-custom-dashboard-option-in-JCB.md)
- [گزینه داشبورد سفارشی](./The-custom-dashboard-option-in-JCB.md)

### 4. Extensibility & ecosystem
### ۴. قابلیت توسعه و اکوسیستم
- [Community Snippets Overview](./General-overview-of-how-community-snippets-work.md)
- [مرور قطعه‌کدهای جامعه](./General-overview-of-how-community-snippets-work.md)
- [Power-Based Class Overriding & Source Injection](./Power-Based-Class-Overriding-and-Source-Injection.md)
- [بازنویسی کلاس مبتنی بر قدرت و تزریق منبع](./Power-Based-Class-Overriding-and-Source-Injection.md)
- [Forking JCB Snippets](./Tutorial-on-forking-JCB-snippets-so-you-can-share-your-snippets-with-the-rest-of-the-Community.md)
- [فورک کردن قطعه‌کدهای JCB](./Tutorial-on-forking-JCB-snippets-so-you-can-share-your-snippets-with-the-rest-of-the-Community.md)
- [Making a Snippet Pull Request](./Tutorial-on-making-a-pull-request-at-Joomla-Component-Builder-Snippets.md)
- [ساخت Pull Request برای قطعه‌کد](./Tutorial-on-making-a-pull-request-at-Joomla-Component-Builder-Snippets.md)
- [JCB Packaging Engine](./JCB-Packaging-Engine.md)
- [موتور پکیجینگ JCB](./JCB-Packaging-Engine.md)
- [Publish Your JCB Packages](./Add-your-own-JCB-packages-to-the-JCB-Communty-Directory.md)
- [انتشار پکیج‌های JCB شما](./Add-your-own-JCB-packages-to-the-JCB-Communty-Directory.md)
- [CLI Command Suite](./CLI-Command-Suite.md)
- [مجموعه دستورات CLI](./CLI-Command-Suite.md)

> 🧭 **Outcome:** pick the pathway that matches your immediate project stage and follow the linked tutorials in sequence.
> 🧭 **نتیجه:** مسیری را انتخاب کنید که با مرحله فعلی پروژه شما سازگار است و آموزش‌های مرتبط را به ترتیب دنبال کنید.

---

## Step 6 – Maintain and scale your builds
## قدم ۶ – نگهداری و مقیاس‌پذیری ساخت‌های خود

1. **Global configuration management:** master component-level settings via [Global Settings](./Global-Settings-of-Component-Builder.md) and learn how menu parameters interact in [Manage Component Config Options](./Manage-a-Components-Global-Config-Option-Field-in-Relation-With-Menu-Params.md).  
۱. **مدیریت پیکربندی سراسری:** تنظیمات سطح کامپوننت را از طریق [تنظیمات سراسری](./Global-Settings-of-Component-Builder.md) مسلط شوید و یاد بگیرید پارامترهای منو چگونه در [مدیریت گزینه‌های پیکربندی کامپوننت](./Manage-a-Components-Global-Config-Option-Field-in-Relation-With-Menu-Params.md) تعامل می‌کنند.  
2. **Deploy upgrades confidently:** study [Auto-create SQL updates](./Auto-create-SQL-updates-for-Componets-in-JCB.md) alongside [License Template Changes](./How-to-change-the-License-Template-in-JCB.md) to automate schema migrations and package metadata.  
۲. **ارتقاءها را با اطمینان استقرار دهید:** [ایجاد خودکار به‌روزرسانی‌های SQL](./Auto-create-SQL-updates-for-Componets-in-JCB.md) را همراه با [تغییرات قالب مجوز](./How-to-change-the-License-Template-in-JCB.md) مطالعه کنید تا مهاجرت‌های اسکیما و متادیتای پکیج را خودکار کنید.  
3. **Handle translations and localisation:** combine [Easy Translation via Excel](./Easy-Translation-via-excel.md) with [Translation Manager](./Translation-Mananger-in-JCB-explained.md) to streamline multilingual work.  
۳. **ترجمه‌ها و بومی‌سازی را مدیریت کنید:** [ترجمه آسان با اکسل](./Easy-Translation-via-excel.md) را با [مدیر ترجمه](./Translation-Mananger-in-JCB-explained.md) ترکیب کنید تا کار چندزبانه روان شود.  
4. **Monitor performance and stability:** leverage [Automated Backup System](./Automated-backup-system-in-JCB.md) and [Dynamic File Inclusion Concept](./Dynamic-File-and-Folder-Inclusion-concept.md) to keep generated code maintainable.
۴. **عملکرد و پایداری را پایش کنید:** از [سیستم پشتیبان‌گیری خودکار](./Automated-backup-system-in-JCB.md) و [مفهوم گنجاندن پویای فایل](./Dynamic-File-and-Folder-Inclusion-concept.md) بهره ببرید تا کد تولیدشده قابل‌نگهداری بماند.

> 🧭 **Outcome:** you have a checklist for long-term maintenance tasks that go beyond the first release.
> 🧭 **نتیجه:** یک چک‌لیست برای کارهای نگهداری بلندمدت دارید که فراتر از نخستین انتشار است.

---

## How to navigate the documentation efficiently
## چگونه به‌صورت کارآمد در مستندات حرکت کنید

- **Use Start Here + Home together:** Start Here points you to the right topic; Home lists every chapter with timeline references for quick scanning.
- **شروع از اینجا** و **خانه** را با هم استفاده کنید: **شروع از اینجا** شما را به موضوع درست هدایت می‌کند؛ **خانه** هر فصل را با ارجاع‌های زمانی برای مرور سریع فهرست می‌کند.
- **Understand how the documentation is produced:** [Developing with Joomla Component Builder](./Developing-with-Joomla-Component-Builder.md) outlines the transcription project and gives tips for studying alongside the videos.
- **بفهمید مستندات چگونه تولید می‌شوند:** [توسعه با جوملا کامپوننت بیلدر](./Developing-with-Joomla-Component-Builder.md) پروژه رونویسی را تشریح می‌کند و نکاتی برای مطالعه همراه با ویدیوها می‌دهد.
- **Search within the repository:** use your editor's search or command-line tools (`rg "keyword" english/`) to find specific features, field names, or helper references across the Markdown files.  
- **درون مخزن جستجو کنید:** از جستجوی ویرایشگر یا ابزارهای خط فرمان (`rg "keyword" english/`) استفاده کنید تا قابلیت‌ها، نام فیلدها یا ارجاع‌های هلپر خاص را در بین فایل‌های مارک‌داون پیدا کنید.  
- **Leverage the sidebar:** [`_Sidebar.md`](./_Sidebar.md) mirrors the Home index and can be pinned in GitHub or wiki views for persistent navigation. Use the new **Features** section there to jump straight into deep dives like [JCB Admin Views](./Features/JCB-Admin-Views.md).
- **از سایدبار بهره ببرید:** [`_Sidebar.md`](./_Sidebar.md) نمایه خانه را آینه می‌کند و می‌تواند در نمای گیت‌هاب یا ویکی برای ناوبری پایدار سنجاق شود. از بخش **Features** جدید آنجا برای رفتن مستقیم به بررسی‌های عمیق مانند [ویوهای ادمین JCB](./Features/JCB-Admin-Views.md) استفاده کنید.
- **Bookmark the feature hub:** The [Features index](./Features/README.md) lists every flagship capability with links to detailed walkthroughs so you can brief teammates quickly.
- **مرکز قابلیت‌ها را نشانه کنید:** [نمایه قابلیت‌ها](./Features/README.md) هر قابلیت شاخص را با لینک به راهنماهای گام‌به‌گام فهرست می‌کند تا بتوانید سریع هم‌تیمی‌ها را راه بیندازید.
- **Track revision status:** chapter titles include progress notes while the editing project is underway. Prioritise fully edited lessons like [Field Types](./Field-Types.md) when you need polished guidance.  
- **وضعیت بازبینی را پیگیری کنید:** عنوان فصل‌ها در حالی که پروژه ویرایش در جریان است، یادداشت‌های پیشرفت را شامل می‌شوند. وقتی به راهنمایی پرداخت‌شده نیاز دارید، درس‌های کاملاً ویرایش‌شده مانند [انواع فیلد](./Field-Types.md) را در اولویت قرار دهید.  
- **Keep personal notes:** maintain a `docs/notes.md` or issue tracker in your project repo to record how you applied tutorials—this shortens the feedback loop when troubleshooting.
- **یادداشت‌های شخصی نگه دارید:** یک `docs/notes.md` یا ردیاب issue در مخزن پروژه خود نگه دارید تا ثبت کنید آموزش‌ها را چگونه اعمال کرده‌اید — این کار هنگام عیب‌یابی چرخه بازخورد را کوتاه می‌کند.

---

## Where to get help and stay updated
## از کجا کمک بگیرید و به‌روز بمانید

- **Community discussions:** join ongoing conversations and ask questions in the [JCB Discussions board](https://github.com/orgs/joomengine/discussions).
- **بحث‌های جامعه:** به گفتگوهای جاری بپیوندید و در [تابلوی بحث JCB](https://github.com/orgs/joomengine/discussions) سؤال بپرسید.
- **Video playlist:** follow the full [YouTube tutorial playlist](https://www.youtube.com/playlist?list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE) alongside the written chapters.  
- **لیست پخش ویدیویی:** [لیست پخش آموزش YouTube](https://www.youtube.com/playlist?list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE) کامل را همراه با فصل‌های نوشته‌شده دنبال کنید.  
- **Beta testing updates:** keep an eye on [Beta Testing](./Beta-Testing.md) for release notes and calls for testers.  
- **به‌روزرسانی‌های تست بتا:** [تست بتا](./Beta-Testing.md) را برای یادداشت‌های انتشار و فراخوانی تست‌کننده‌ها زیر نظر داشته باشید.  
- **Contribute back:** when you craft helpers, layouts, or snippets, consider sharing them via the snippets workflow or package directory linked above.
- **به جامعه بازگردانید:** وقتی هلپر، لایه یا قطعه‌کد می‌سازید، اشتراک‌گذاری آن‌ها را از طریق گردش کار قطعه‌کدها یا پوشه پکیج ذکرشده در بالا در نظر بگیرید.

> 🧭 **Outcome:** you know where to ask questions, watch demonstrations, and contribute improvements as you grow into the platform.
> 🧭 **نتیجه:** می‌دانید کجا سؤال بپرسید، نمایش‌ها را تماشا کنید و با رشد شما در پلتفرم، بهبودهایی مشارکت کنید.

---

## Ready for your next step?
## آماده قدم بعدی خود هستید؟

Revisit this page whenever you need to re-orient yourself or onboard a teammate. Start from Step 1 if you need a refresher on architecture, jump to Step 4 to drill into a feature, or head straight to Step 6 when preparing a release. Happy building!
هر زمان که نیاز به جهت‌یابی دوباره خود یا آشناسازی یک هم‌تیمی داشتید، به این صفحه بازگردید. اگر به مروری بر معماری نیاز دارید از قدم ۱ شروع کنید، برای ورود عمیق به یک قابلیت به قدم ۴ بروید، یا هنگام آماده‌سازی انتشار مستقیم به قدم ۶ بروید. ساخت مبارک!