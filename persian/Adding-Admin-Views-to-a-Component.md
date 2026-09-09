# **Adding Admin Views to a Component**
# **افزودن ویوهای ادمین به یک کامپوننت**

*(Based on the Joomla Component Builder Tutorial Video)*
*(بر اساس ویدیوی آموزش جوملا کامپوننت بیلدر)*
[Watch Video](https://www.youtube.com/watch?v=39vY66X7GGU&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h00m00s)
[تماشای ویدیو](https://www.youtube.com/watch?v=39vY66X7GGU&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h00m00s)

---

## **Overview**
## **مرور**

In this tutorial, we'll explore how to **add admin views** to a component using **Joomla Component Builder (JCB)**.
در این آموزش بررسی می‌کنیم که چگونه با استفاده از **جوملا کامپوننت بیلدر (JCB)**، **ویوهای ادمین** را به یک کامپوننت **اضافه** کنیم.
You'll learn how to connect your created admin views to your component, configure visibility settings, enable key Joomla features like **Auto Check-In**, **Version History**, **Import/Export**, and **Front-End Editing**, and understand how these affect your workflow and generated component.
یاد می‌گیرید چگونه ویوهای ادمین ساخته‌شده را به کامپوننت خود متصل کنید، تنظیمات نمایش را پیکربندی کنید، قابلیت‌های کلیدی جوملا مانند **چک‌این خودکار**، **تاریخچه نسخه‌ها**، **واردات/صادرات** و **ویرایش فرانت‌اند** را فعال کنید و بدانید این‌ها چگونه بر گردش کار و کامپوننت تولیدشده شما اثر می‌گذارند.

> 🔎 **New to Admin Views?** Start with the [JCB Admin Views feature overview](./Features/JCB-Admin-Views.md) to understand the
> 🔎 **تازه‌کار با ویوهای ادمین؟** برای درک مفاهیم قبل از اعمال آن‌ها در یک کامپوننت، با [مرور قابلیت ویوهای ادمین JCB](./Features/JCB-Admin-Views.md) شروع کنید
> concepts before applying them inside a component.
> تا مفاهیم را قبل از اعمال آن‌ها در یک کامپوننت درک کنید.

Admin Views are the mandatory, schema-defining layer for every JCB-built component. Each one is bound to a database table and automatically supplies the generated models, controllers, list/edit layouts, and permission handling that power Joomla's MVC stack. Because of this, a component cannot compile without at least one Admin View, and any additional component behaviour should always build on top of these generated CRUD foundations.
ویوهای ادمین لایهٔ الزامی و تعیین‌کنندهٔ اسکیما برای هر کامپوننت ساخته‌شده با JCB هستند. هر یک به یک جدول دیتابیس متصل است و به‌صورت خودکار مدل‌ها، کنترلرها، لایه‌های لیست/ویرایش و مدیریت دسترسی‌های تولیدشده را فراهم می‌کند که پشته MVC جوملا را تغذیه می‌کنند. به همین دلیل، یک کامپوننت بدون حداقل یک ویوی ادمین نمی‌تواند کامپایل شود و هر رفتار اضافی کامپوننت باید همیشه بر پایه این پی‌های CRUD تولیدشده ساخته شود.

This section assumes that you have already:
این بخش فرض می‌کند که شما قبلاً:

* Installed Joomla Component Builder.
* جوملا کامپوننت بیلدر را نصب کرده‌اید.
* Created one or more **Admin Views** with fields (see the previous tutorials on Field Types and Admin Views).
* یک یا چند **ویوی ادمین** همراه با فیلد ایجاد کرده‌اید (به آموزش‌های قبلی درباره انواع فیلد و ویوهای ادمین مراجعه کنید).

> **Need to update a shared Admin View?** Inside JCB select the view, click **Reset** to pull the latest version from this repository, or point your instance to a fork if you maintain a customised baseline. This keeps collaborative projects aligned while still allowing overrides per project.
> **نیاز به به‌روزرسانی یک ویوی ادمین مشترک دارید؟** در JCB ویو را انتخاب کنید و روی **بازنشانی** کلیک کنید تا آخرین نسخه از این مخزن دریافت شود، یا اگر یک نسخه پایه سفارشی‌شده نگهداری می‌کنید، نمونه خود را به یک فورک هدایت کنید. این کار پروژه‌های مشارکتی را هماهنگ نگه می‌دارد و همچنان امکان override کردن را در هر پروژه فراهم می‌کند.

---

## **1. Connecting Admin Views to a Component**
## **۱. اتصال ویوهای ادمین به یک کامپوننت**

[00:00:28](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h00m28s)

1. In JCB, open your **Component** (for example, *Sermon Distributor*).
۱. در JCB، **کامپوننت** خود را باز کنید (برای مثال، *Sermon Distributor*).
2. Navigate to **Settings → Admin Views**.
۲. به **Settings → Admin Views** بروید.
   This is where you link your existing admin views to the component.
   اینجا جایی است که ویوهای ادمین موجود خود را به کامپوننت متصل می‌کنید.
3. Click the **Add** button, then select an **Admin View** from the dropdown.
۳. روی دکمه **Add** کلیک کنید، سپس یک **ویوی ادمین** را از منوی کشویی انتخاب کنید.
4. Repeat this process for each view you wish to attach.
۴. این فرآیند را برای هر ویویی که می‌خواهید متصل کنید تکرار کنید.

**Tip:**
**نکته:**
If you have many admin views, type the view's name in the search bar to locate it quickly.
اگر ویوهای ادمین زیادی دارید، نام ویو را در نوار جستجو تایپ کنید تا سریع آن را پیدا کنید.

---

## **2. Adding View Icons**
## **۲. افزودن آیکون‌های ویو**

[00:01:39](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h01m39s)

When you assign an admin view, you can set an **icon** to represent it in the backend interface.
وقتی یک ویوی ادمین را اختصاص می‌دهید، می‌توانید یک **آیکون** تنظیم کنید تا آن را در رابط بک‌اند نمایش دهد.

* JCB uses **Joomla Standard Icomoon Fonts** for these icons.
* JCB از **فونت‌های استاندارد Icomoon جوملا** برای این آیکون‌ها استفاده می‌کند.
* When selecting an icon, you'll see a preview immediately.
* هنگام انتخاب آیکون، بلافاصله یک پیش‌نمایش می‌بینید.
* The icon you choose appears in the Joomla Administrator's component sidebar and dashboard.
* آیکونی که انتخاب می‌کنید در سایدبار کامپوننت و داشبورد مدیر جوملا ظاهر می‌شود.

**Tip:**
**نکته:**
Choose icons that visually match your view's purpose (e.g., a document icon for "Articles," a user icon for "Authors").
آیکون‌هایی انتخاب کنید که از نظر بصری با هدف ویو شما هماهنگ باشند (مثلاً آیکون سند برای "مقالات"، آیکون کاربر برای "نویسندگان").

---

## **3. Admin Menu Visibility**
## **۳. قابلیت نمایش منوی ادمین**

[00:02:29](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h02m29s)

JCB gives you switches to control how each view appears in your component's admin menu.
JCB سوئیچ‌هایی در اختیار شما قرار می‌دهد تا کنترل کنید هر ویو چگونه در منوی ادمین کامپوننت شما ظاهر شود.

* **Admin Menu:**
* **منوی ادمین:**
  Enable this if you want the view to appear in the Joomla sidebar (under your component's menu).
  اگر می‌خواهید ویو در سایدبار جوملا (زیر منوی کامپوننت شما) ظاهر شود، این را فعال کنید.

---

## **4. Dashboard Item Visibility**
## **۴. قابلیت نمایش آیتم داشبورد**

[00:03:04](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h03m04s)

* **Dashboard (List of Records):**
* **داشبورد (لیست رکوردها):**
  Adds a shortcut icon to the main dashboard for viewing records.
  یک آیکون میانبر به داشبورد اصلی برای مشاهده رکوردها اضافه می‌کند.
* **Dashboard (Add Record):**
* **داشبورد (افزودن رکورد):**
  Adds a button that allows quick creation of new records directly from the component dashboard.
  دکمه‌ای اضافه می‌کند که امکان ایجاد سریع رکوردهای جدید را مستقیماً از داشبورد کامپوننت فراهم می‌کند.

If you prefer not to show "Add Record" on the dashboard, set it to **No**.
اگر ترجیح می‌دهید "افزودن رکورد" در داشبورد نمایش داده نشود، آن را روی **خیر** تنظیم کنید.

---

## **5. Submenu Inclusion**
## **۵. گنجاندن در زیرمنو**

[00:03:41](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h03m41s)

You can include or exclude a view from the **submenu** (the collapsible navigation area inside each admin view).
می‌توانید یک ویو را در **زیرمنو** (ناحیه ناوبری جمع‌شونده داخل هر ویوی ادمین) قرار دهید یا از آن خارج کنید.

* Enable this if the view should be accessible as a submenu option.
* اگر ویو باید به‌عنوان یک گزینه زیرمنو در دسترس باشد، این را فعال کنید.

---

## **6. Auto Check-In Feature**
## **۶. قابلیت چک‌این خودکار**

[00:03:57](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h03m57s)

This feature automatically checks in items that have been checked out for longer than a defined period.
این قابلیت به‌صورت خودکار آیتم‌هایی را که بیشتر از یک بازه مشخص چک‌اوت شده‌اند، چک‌این می‌کند.

* Enable **Auto Check-In** in your admin view settings.
* **چک‌این خودکار** را در تنظیمات ویوی ادمین خود فعال کنید.
* Configure the timeout duration in your component's **Global Settings** under "Auto Check-In Period."
* مدت زمان تایم‌اوت را در **تنظیمات سراسری** کامپوننت خود، در بخش "دوره چک‌این خودکار" پیکربندی کنید.

**Example:**
**مثال:**
If a user forgets to close an item, JCB's auto-check-in feature will automatically release the lock after a set time.
اگر کاربر فراموش کند آیتمی را ببندد، قابلیت چک‌این خودکار JCB پس از یک زمان مشخص، قفل را به‌صورت خودکار آزاد می‌کند.

---

## **7. Enable Version History**
## **۷. فعال‌سازی تاریخچه نسخه‌ها**

[00:05:06](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h05m06s)

The **History Component** integration allows Joomla to track every change made to records in your component.
یکپارچه‌سازی **کامپوننت تاریخچه** به جوملا امکان می‌دهد هر تغییری را که روی رکوردهای کامپوننت شما اعمال می‌شود، پیگیری کند.

**Steps to Use Version History:**
**مراحل استفاده از تاریخچه نسخه‌ها:**

1. Enable **Keep History** in the Admin View.
۱. **Keep History** را در ویوی ادمین فعال کنید.
2. Edit an item (e.g., "Preacher → A Capella Music").
۲. یک آیتم را ویرایش کنید (مثلاً "Preacher → A Capella Music").
3. Click **Versions** at the top toolbar.
۳. روی **Versions** در نوار ابزار بالا کلیک کنید.
4. You can:
۴. شما می‌توانید:

   * View all previous saved versions.
   * همه نسخه‌های ذخیره‌شده قبلی را مشاهده کنید.
   * Restore a prior version if needed.
   * در صورت نیاز، یک نسخه قبلی را بازیابی کنید.

**Tip:**
**نکته:**
You can also define how many historical versions Joomla keeps for each item.
همچنین می‌توانید تعیین کنید جوملا برای هر آیتم چند نسخه تاریخی نگه دارد.

---

## **8. Add Metadata Support**
## **۸. افزودن پشتیبانی متادیتا**

[00:14:23](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h14m23s)

If your view's data will appear on the front end, enable **Metadata** support.
اگر داده‌های ویو شما در فرانت‌اند نمایش داده می‌شوند، پشتیبانی **متادیتا** را فعال کنید.

* Metadata adds SEO-related data (title, description, keywords) to your pages.
* متادیتا داده‌های مرتبط با SEO (عنوان، توضیحات، کلمات کلیدی) را به صفحات شما اضافه می‌کند.
* While less crucial for search engines today, it still improves content organization and social sharing previews.
* اگرچه امروزه برای موتورهای جستجو کمتر حیاتی است، همچنان سازمان‌دهی محتوا و پیش‌نمایش‌های اشتراک‌گذاری اجتماعی را بهبود می‌بخشد.

Enable metadata for content views that represent unique or indexable front-end pages.
برای ویوهای محتوایی که نمایانگر صفحات فرانت‌اند یکتا یا قابل ایندکس‌شدن هستند، متادیتا را فعال کنید.

---

## **9. Enable Access Control**
## **۹. فعال‌سازی کنترل دسترسی**

[00:15:37](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h15m37s)

The **Access Switch** enables Joomla's standard access-level dropdown (e.g., *Public*, *Registered*, *Special*).
**سوئیچ دسترسی**، منوی کشویی استاندارد سطح دسترسی جوملا را فعال می‌کند (مثلاً *عمومی*، *ثبت‌نام‌شده*، *ویژه*).

This helps restrict content visibility based on user roles or groups.
این کار به محدود کردن قابلیت نمایش محتوا بر اساس نقش‌ها یا گروه‌های کاربری کمک می‌کند.

* Enable **Access** in your Admin View if you want per-item access control.
* اگر کنترل دسترسی برای هر آیتم می‌خواهید، **Access** را در ویوی ادمین خود فعال کنید.
* Often combined with **permissions**, though typically not both at once.
* معمولاً با **دسترسی‌ها** ترکیب می‌شود، هرچند به‌طور معمول هر دو همزمان استفاده نمی‌شوند.

---

## **10. Import/Export Data**
## **۱۰. واردات/صادرات داده**

[00:16:38](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h16m38s)

JCB can automatically add **Import/Export** functionality to each admin view.
JCB می‌تواند به‌صورت خودکار قابلیت **واردات/صادرات** را به هر ویوی ادمین اضافه کند.

* Toggle **Export/Import Data** to "Yes" to enable it.
* **Export/Import Data** را روی "بله" قرار دهید تا فعال شود.
* After compilation, each admin list view will have:
* پس از کامپایل، هر ویوی لیست ادمین این موارد را خواهد داشت:

  * An **Export** button (download CSV data).
  * یک دکمه **Export** (دانلود داده CSV).
  * An **Import** button (upload and map CSV data to database fields).
  * یک دکمه **Import** (بارگذاری و نگاشت داده CSV به فیلدهای دیتابیس).

**Note:**
**یادداشت:**
Encrypted fields require care - imported data won't automatically re-encrypt unless handled manually.
فیلدهای رمزنگاری‌شده نیاز به دقت دارند - داده‌های واردشده به‌صورت خودکار رمزنگاری مجدد نمی‌شوند مگر اینکه به‌صورت دستی مدیریت شوند.

---

## **11. Edit/Create Site Views**
## **۱۱. ویرایش/ایجاد ویوهای سایت**

[00:18:20](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h18m20s)

This is one of JCB's most powerful features.
این یکی از قدرتمندترین قابلیت‌های JCB است.
When enabled, it allows **front-end editing** of your admin data.
وقتی فعال شود، **ویرایش فرانت‌اند** داده‌های ادمین شما را امکان‌پذیر می‌کند.

### **How It Works**
### **نحوه کار**

1. Enable the switch **Edit Create Site View** in your admin view settings.
۱. سوئیچ **Edit Create Site View** را در تنظیمات ویوی ادمین خود فعال کنید.
2. Upon compiling:
۲. پس از کامپایل:

   * JCB generates a **site view** version of your admin form.
   * JCB یک نسخه **ویوی سایت** از فرم ادمین شما تولید می‌کند.
   * This includes all fields, validation, and permission checks.
   * این شامل همه فیلدها، اعتبارسنجی و بررسی‌های دسترسی است.
3. You can then add menu links or modules to expose the front-end editing interface.
۳. سپس می‌توانید لینک‌های منو یا ماژول‌ها را اضافه کنید تا رابط ویرایش فرانت‌اند نمایان شود.

**Example:**
**مثال:**
A "Company" admin view, when enabled, generates a front-end page where logged-in users can:
یک ویوی ادمین "Company" وقتی فعال می‌شود، صفحه‌ای فرانت‌اند تولید می‌کند که کاربران واردشده می‌توانند:

* Edit company data.
* داده‌های شرکت را ویرایش کنند.
* Add new records (if permitted).
* رکوردهای جدید اضافه کنند (در صورت مجاز بودن).

Permissions are enforced automatically - if a user lacks permission to edit certain fields, those will not appear in their form.
دسترسی‌ها به‌صورت خودکار اعمال می‌شوند - اگر کاربری مجوز ویرایش برخی فیلدها را نداشته باشد، آن فیلدها در فرم او ظاهر نمی‌شوند.

**Important:**
**مهم:**
JCB generates the front-end code but doesn't automatically create menu links.
JCB کد فرانت‌اند را تولید می‌کند اما به‌صورت خودکار لینک‌های منو ایجاد نمی‌کند.
You must manually link these site views via Joomla menu items or custom templates.
شما باید این ویوهای سایت را به‌صورت دستی از طریق آیتم‌های منوی جوملا یا قالب‌های سفارشی متصل کنید.

---

## **12. Ordering and Display**
## **۱۲. ترتیب‌دهی و نمایش**

[00:24:48](https://www.youtube.com/watch?v=39vY66X7GGU&t=00h24m48s)

The **Order** column in the Admin View Settings determines:
ستون **Order** در تنظیمات ویوی ادمین تعیین می‌کند:

* The order in which views appear in the admin sidebar.
* ترتیبی که ویوها در سایدبار ادمین ظاهر می‌شوند.
* The order of submenu items and icons.
* ترتیب آیتم‌های زیرمنو و آیکون‌ها.

Adjust these numbers to organize your admin panel logically (for example, list views before edit views).
این اعداد را تنظیم کنید تا پنل ادمین خود را به‌صورت منطقی سازمان‌دهی کنید (مثلاً ویوهای لیست قبل از ویوهای ویرایش).

---

## **Conclusion**
## **نتیجه‌گیری**

Adding and configuring admin views is a critical part of JCB's workflow.
افزودن و پیکربندی ویوهای ادمین بخش حیاتی گردش کار JCB است.
Through these settings, you can define how each view behaves in the backend and, optionally, how it integrates with your site's front end.
از طریق این تنظیمات، می‌توانید تعیین کنید هر ویو در بک‌اند چگونه رفتار کند و در صورت تمایل، چگونه با فرانت‌اند سایت شما یکپارچه شود.

By following these steps, you'll ensure your component:
با دنبال کردن این مراحل، مطمئن می‌شوید کامپوننت شما:

* Is user-friendly for administrators.
* برای مدیران کاربرپسند است.
* Supports Joomla-native features like auto check-in and version history.
* از قابلیت‌های بومی جوملا مانند چک‌این خودکار و تاریخچه نسخه‌ها پشتیبانی می‌کند.
* Provides flexible access and import/export capabilities.
* قابلیت‌های دسترسی و واردات/صادرات منعطف فراهم می‌کند.
* Can extend seamlessly to the front-end for site-level editing.
* می‌تواند به‌صورت یکپارچه به فرانت‌اند برای ویرایش در سطح سایت گسترش یابد.

---