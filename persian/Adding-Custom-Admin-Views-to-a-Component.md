# **Adding Custom Admin Views to a Component**
# **افزودن ویوهای مدیریتی سفارشی به یک کامپوننت**

---

## **Overview**
## **مرور کلی**

In Joomla Component Builder (JCB), *Custom Admin Views* allow developers to create dynamic and flexible administrative views inside their components. These views enhance the backend interface by providing additional dashboard sections, menu links, and functionality such as custom buttons and result displays.
در جوملا کامپوننت بیلدر (JCB)، *ویوهای مدیریتی سفارشی* به توسعه‌دهندگان اجازه می‌دهند ویوهای مدیریتی پویا و انعطاف‌پذیری درون کامپوننت‌های خود ایجاد کنند. این ویوها رابط بک‌اند را با فراهم‌کردن بخش‌های داشبورد اضافی، لینک‌های منو و قابلیت‌هایی مانند دکمه‌های سفارشی و نمایش نتایج ارتقا می‌دهند.

Think of them as the admin-side counterpart to Site Views: you use the same building blocks—**Layouts**, **Templates**, **Dynamic Gets**, **Custom Code blocks**, and optional **JavaScript/CSS libraries**—but you aim the output at administrators instead of public visitors. This lets you prototype dashboards, data utilities, or one-off workflow helpers without abandoning the JCB compile cycle.
آن‌ها را به‌عنوان همتای سمت ادمین ویوهای سایت در نظر بگیرید: از همان بلوک‌های سازنده استفاده می‌کنید — **لایه‌ها (Layout)**، **قالب‌ها**، **Dynamic Getها**، **بلوک‌های کد سفارشی (Custom Code)** و **کتابخانه‌های اختیاری جاوااسکریپت/سی‌اس‌اس** — اما خروجی را به‌جای بازدیدکنندگان عمومی، برای مدیران هدف می‌گیرید. این به شما امکان می‌دهد داشبوردها، ابزارهای داده‌ای یا کمک‌کارهای گردش کار یک‌بارمصرف را بدون رهاکردن چرخه کامپایل JCB نمونه‌سازی کنید.

In this example, we'll use the **Cost-Benefit Projection** component to demonstrate how to add and configure *Custom Admin Views* in JCB.
در این مثال، از کامپوننت **پیش‌بینی هزینه-فایده (Cost-Benefit Projection)** برای نشان‌دادن نحوه افزودن و پیکربندی *ویوهای مدیریتی سفارشی* در JCB استفاده می‌کنیم.

### **Before you start: assemble the ingredients**
### **پیش از شروع: مواد اولیه را آماده کنید**

1. **Plan the data sources.** Decide which Admin Views or database tables will feed your Custom Admin View and model the relationships via Dynamic Gets.
۱. **منابع داده را برنامه‌ریزی کنید.** مشخص کنید کدام ویوهای ادمین یا جدول‌های دیتابیس، ویوی مدیریتی سفارشی شما را تغذیه می‌کنند و روابط را از طریق Dynamic Getها مدل‌سازی کنید.
2. **Sketch the interface.** Determine whether you need Item, List, or hybrid behaviour and outline the tabs, filters, and toolbar actions that support the workflow.
۲. **واسط را طراحی کنید.** مشخص کنید به رفتار آیتم (Item)، لیست (List) یا ترکیبی نیاز دارید و تب‌ها، فیلترها و اقدامات نوار ابزار پشتیبان گردش کار را ترسیم کنید.
3. **Prepare reusable assets.** Identify shared layouts, helper methods, JavaScript, or CSS that the view should reference so you avoid duplicating logic across the admin area.
۳. **دارایی‌های قابل استفاده مجدد را آماده کنید.** لایه‌های مشترک، متدهای هلپر، جاوااسکریپت یا سی‌اس‌اس مورد نیاز ویو را شناسایی کنید تا از تکرار منطق در سراسر بخش ادمین جلوگیری کنید.

Doing this homework keeps your implementation focused and prevents last-minute rewrites when you start wiring buttons, queries, and templates together.
انجام این آماده‌سازی‌ها، پیاده‌سازی شما را متمرکز نگه می‌دارد و از بازنویسی‌های لحظه آخری هنگام اتصال دکمه‌ها، کوئری‌ها و قالب‌ها به یکدیگر جلوگیری می‌کند.

---

## **1. Accessing the Custom Admin Views Section**
## **۱. دسترسی به بخش ویوهای مدیریتی سفارشی**

1. Open **Component Builder** in your Joomla administrator panel.
۱. **کامپوننت بیلدر** را در پنل مدیر جوملا خود باز کنید.
2. Navigate to **Settings → Custom Admin Views**.
۲. به **تنظیمات ← ویوهای مدیریتی سفارشی** بروید.
3. Click **New** to create a new Custom Admin View.
۳. برای ایجاد یک ویوی مدیریتی سفارشی جدید، روی **جدید (New)** کلیک کنید.

You'll notice that a *Custom Admin View* has more configuration options than a *Site View*. This is because the admin side is designed to be more dynamic and integrated into Joomla's administrative interface.
متوجه خواهید شد که یک *ویوی مدیریتی سفارشی* گزینه‌های پیکربندی بیشتری نسبت به یک *ویوی سایت* دارد. دلیلش این است که سمت ادمین برای پویایی بیشتر و ادغام در رابط مدیریتی جوملا طراحی شده است.

---

## **2. Understanding the Custom Admin View Options**
## **۲. درک گزینه‌های ویوی مدیریتی سفارشی**

### **Icons and Menu Placement**
### **آیکون‌ها و جای‌گذاری منو**

Each Custom Admin View can be associated with a **menu icon** and can appear in one or more of the following locations:
هر ویوی مدیریتی سفارشی می‌تواند با یک **آیکون منو** مرتبط باشد و در یک یا چند موقعیت زیر ظاهر شود:

* **Main Menu** - The primary menu visible on the Joomla component dashboard.
* **منوی اصلی (Main Menu)** - منوی اولیه که در داشبورد کامپوننت جوملا دیده می‌شود.
* **Dashboard (List of Records)** - The central area displaying key data or quick links.
* **داشبورد (لیست رکوردها)** - ناحیه مرکزی که داده‌های کلیدی یا لینک‌های سریع را نمایش می‌دهد.
* **Submenu** - The vertical sidebar visible when navigating inside component views.
* **زیرمنو** - نوار کناری عمودی که هنگام پیمایش درون ویوهای کامپوننت دیده می‌شود.

These settings control how your view will appear and how users will access it from the backend.
این تنظیمات کنترل می‌کنند ویوی شما چگونه ظاهر شود و کاربران چگونه از بک‌اند به آن دسترسی پیدا کنند.

> **Tip:**
> **نکته:**
> Use distinctive icons for each Custom Admin View to make navigation intuitive. JCB supports Joomla's standard icon classes.
> برای هر ویوی مدیریتی سفارشی از آیکون‌های متمایز استفاده کنید تا ناوبری بصری شود. JCB از کلاس‌های آیکون استاندارد جوملا پشتیبانی می‌کند.

---

## **3. Targeting Specific Items and Views**
## **۳. هدف‌گیری آیتم‌ها و ویوهای خاص**

Custom Admin Views can target other views or items inside your component. This allows you to create contextual buttons or data summaries that directly link to related items.
ویوهای مدیریتی سفارشی می‌توانند ویوها یا آیتم‌های دیگری را درون کامپوننت شما هدف بگیرند. این به شما امکان می‌دهد دکمه‌های زمینه‌ای یا خلاصه‌های داده‌ای بسازید که مستقیماً به آیتم‌های مرتبط لینک می‌شوند.

1. In your new Custom Admin View, find the **Target View** dropdown.
۱. در ویوی مدیریتی سفارشی جدید خود، منوی کشویی **ویوی هدف (Target View)** را پیدا کنید.
2. Select the appropriate target (for example, `Company`).
۲. هدف مناسب را انتخاب کنید (مثلاً `Company`).
3. Set **Has Metadata** and **Add Access** to `Yes` if needed.
۳. در صورت نیاز، **دارای متادیتا (Has Metadata)** و **افزودن دسترسی (Add Access)** را روی `Yes` قرار دهید.

This ensures that the Custom Admin View interacts correctly with the targeted view and has proper access permissions.
این کار تضمین می‌کند ویوی مدیریتی سفارشی به‌درستی با ویوی هدف تعامل داشته باشد و مجوزهای دسترسی مناسب داشته باشد.

> **Example:**
> **مثال:**
> If your `Company Results` view should display data related to specific companies, set the target view to `Company`.
> اگر ویوی `Company Results` شما باید داده‌های مرتبط با شرکت‌های خاص را نمایش دهد، ویوی هدف را روی `Company` تنظیم کنید.

---

## **4. Linking the Custom Admin View Inside the Component**
## **۴. اتصال ویوی مدیریتی سفارشی درون کامپوننت**

After configuration, open your component's **Dashboard** or **Target View** (for example, *Companies*) and check the new button or icon that appears.
پس از پیکربندی، **داشبورد** یا **ویوی هدف (Target View)** کامپوننت خود را باز کنید (مثلاً *Companies*) و دکمه یا آیکون جدیدی را که ظاهر شده بررسی کنید.

When correctly configured:
وقتی به‌درستی پیکربندی شود:

* The **Company Results** button will appear in the toolbar or dashboard.
* دکمه **Company Results** در نوار ابزار یا داشبورد ظاهر می‌شود.
* Clicking it will open the *Custom Admin View* (e.g., charts or combined results).
* کلیک روی آن، *ویوی مدیریتی سفارشی* را باز می‌کند (مثلاً نمودارها یا نتایج ترکیبی).
* The selected `item_id` from the `Company` view is passed to the new view dynamically.
* `item_id` انتخاب‌شده از ویوی `Company` به‌صورت پویا به ویوی جدید منتقل می‌شود.

This dynamic linking is handled automatically by JCB once the target and placement settings are correctly configured.
پس از پیکربندی صحیح هدف و جای‌گذاری، این اتصال پویا به‌صورت خودکار توسط JCB انجام می‌شود.

---

## **5. Using "Order Before" Options**
## **۵. استفاده از گزینه‌های "Order Before"**

The **Order Before** fields are used when your Custom Admin View is added to a **Main Menu** or **Submenu**.
فیلدهای **Order Before** زمانی استفاده می‌شوند که ویوی مدیریتی سفارشی شما به **منوی اصلی (Main Menu)** یا **زیرمنو** اضافه شود.

These fields define where your new menu item should appear relative to existing items.
این فیلدها مشخص می‌کنند آیتم منوی جدید شما نسبت به آیتم‌های موجود در کجا قرار گیرد.
For example:
برای مثال:

* If you select *Dashboard (list of records)* as "Order Before", your new view will appear directly before the dashboard link in the admin menu.
* اگر *داشبورد (لیست رکوردها)* را به‌عنوان "Order Before" انتخاب کنید، ویوی جدید شما دقیقاً قبل از لینک داشبورد در منوی ادمین ظاهر می‌شود.

This step ensures your admin interface remains logically organized.
این مرحله تضمین می‌کند رابط ادمین شما به‌صورت منطقی سازمان‌یافته باقی بماند.

---

## **6. Implementing Custom Buttons**
## **۶. پیاده‌سازی دکمه‌های سفارشی**

Custom Admin Views often include **custom buttons** that trigger specific actions or navigate to other views.
ویوهای مدیریتی سفارشی اغلب شامل **دکمه‌های سفارشی** هستند که اقدامات خاصی را فعال می‌کنند یا به ویوهای دیگر هدایت می‌کنند.

1. Go to your Custom Admin View (e.g., *Company Results*).
۱. به ویوی مدیریتی سفارشی خود بروید (مثلاً *Company Results*).
2. Scroll to the **Custom Buttons** section.
۲. به بخش **دکمه‌های سفارشی (Custom Buttons)** بروید.
3. Define PHP logic for each button as needed (for example: `editCompany`, `gotoCompany`).
۳. در صورت نیاز، منطق PHP هر دکمه را تعریف کنید (مثلاً: `editCompany`، `gotoCompany`).

These buttons interact with the component's controller logic. You can define whether each button targets a *single item* or operates at a *list level*.
این دکمه‌ها با منطق کنترلر کامپوننت تعامل دارند. می‌توانید تعیین کنید هر دکمه یک *آیتم واحد* را هدف بگیرد یا در *سطح لیست* عمل کند.

> **Technical Note:**
> **یادداشت فنی:**
> JCB generates the PHP code for these buttons in your component. You can inspect the generated code after compiling to understand or adjust the behavior further.
> JCB کد PHP این دکمه‌ها را در کامپوننت شما تولید می‌کند. پس از کامپایل می‌توانید کد تولیدشده را بررسی کنید تا رفتار را بیشتر درک یا تنظیم کنید.

---

## **7. The "Combined Results" Example**
## **۷. مثال "Combined Results" (نتایج ترکیبی)**

In the *Cost-Benefit Projection* example:
در مثال *پیش‌بینی هزینه-فایده (Cost-Benefit Projection)*:

* The **Combined Results** button was added to the toolbar.
* دکمه **Combined Results** به نوار ابزار اضافه شد.
* It displays results by combining data from multiple selected items.
* این دکمه با ترکیب داده‌های چند آیتم انتخاب‌شده، نتایج را نمایش می‌دهد.
* The associated icon (e.g., a gear or chart icon) helps users identify its function quickly.
* آیکون مرتبط (مثلاً آیکون چرخ‌دنده یا نمودار) به کاربران کمک می‌کند عملکرد آن را سریع تشخیص دهند.

Inside the **Combined Results** view, additional buttons such as *Dashboard* and *Companies* were added.
درون ویوی **Combined Results**، دکمه‌های اضافی مانند *Dashboard* و *Companies* اضافه شدند.

These correspond to the actions available *within* that specific view.
این‌ها با اقدامات موجود *درون* همان ویوی خاص مطابقت دارند.

> **Remember:**
> **به‌خاطر بسپارید:**
> Buttons defined **before opening the view** appear in the toolbar.
> دکمه‌هایی که **قبل از باز کردن ویو** تعریف می‌شوند، در نوار ابزار ظاهر می‌شوند.
> Buttons defined **inside the view** appear once the view is opened.
> دکمه‌هایی که **داخل ویو** تعریف می‌شوند، پس از باز شدن ویو ظاهر می‌شوند.

---

## **8. Linking Data Using Dynamic GET and Selected IDs**
## **۸. اتصال داده‌ها با Dynamic Get و شناسه‌های انتخاب‌شده**

When multiple records are selected in a list view, their IDs (`cid`) can be passed to your Custom Admin View dynamically.
وقتی چند رکورد در یک ویوی لیست انتخاب می‌شوند، شناسه‌های آن‌ها (`cid`) می‌توانند به‌صورت پویا به ویوی مدیریتی سفارشی شما منتقل شوند.

This enables data filtering or aggregation based on user selection.
این کار فیلتر کردن یا تجمیع داده‌ها را بر اساس انتخاب کاربر ممکن می‌سازد.

To achieve this:
برای رسیدن به این هدف:

1. In your Custom Admin View's **Dynamic GET (Data Query)** section, access the selected IDs using PHP:
۱. در بخش **Dynamic GET (کوئری داده)** ویوی مدیریتی سفارشی خود، به شناسه‌های انتخاب‌شده با PHP دسترسی پیدا کنید:

   ```php
   $input = JFactory::getApplication()->input;
   $ids = $input->get('cid', array(), 'array');
   ```
2. Validate that the user has permission to access this data.
۲. تأیید کنید کاربر مجوز دسترسی به این داده‌ها را دارد.
3. Use `$ids` in your SQL query or data model to fetch the relevant dataset.
۳. از `$ids` در کوئری SQL یا مدل داده خود برای دریافت مجموعه‌داده مرتبط استفاده کنید.

In JCB, this is typically implemented in the **getListQuery()** method of the model.
در JCB، این کار معمولاً در متد **getListQuery()** مدل پیاده‌سازی می‌شود.

You can modify or extend it via the Dynamic GET builder to suit your component's logic.
می‌توانید آن را از طریق سازنده Dynamic GET تغییر یا گسترش دهید تا با منطق کامپوننت شما سازگار شود.

---

## **9. Testing and Troubleshooting**
## **۹. تست و عیب‌یابی**

If your view or buttons don't appear as expected:
اگر ویو یا دکمه‌های شما مطابق انتظار ظاهر نشدند:

* Reopen the Custom Admin View and double-check placement options.
* ویوی مدیریتی سفارشی را دوباره باز کنید و گزینه‌های جای‌گذاری را دوباره بررسی کنید.
* Ensure the **Target View** is properly set.
* مطمئن شوید **ویوی هدف (Target View)** به‌درستی تنظیم شده است.
* Recompile the component and install the updated version.
* کامپوننت را دوباره کامپایل کنید و نسخه به‌روزرسانی‌شده را نصب کنید.
* Inspect the generated PHP code to verify your logic was included.
* کد PHP تولیدشده را بررسی کنید تا مطمئن شوید منطق شما گنجانده شده است.

Experimenting is part of the learning process. Adjust placements and settings, recompile, and observe the behavior in Joomla until everything works as intended.
آزمایش‌کردن بخشی از فرآیند یادگیری است. جای‌گذاری‌ها و تنظیمات را تنظیم کنید، دوباره کامپایل کنید و رفتار را در جوملا مشاهده کنید تا همه‌چیز آن‌طور که باید کار کند.

---

## **10. Menu Structure and Placement Summary**
## **۱۰. ساختار منو و خلاصه جای‌گذاری**

When compiled:
پس از کامپایل:

* **Main Menu** items appear at the top of your component's admin interface.
* آیتم‌های **منوی اصلی (Main Menu)** در بالای رابط ادمین کامپوننت شما ظاهر می‌شوند.
* **Submenu** items appear on the left-hand side when viewing a specific section.
* آیتم‌های **زیرمنو** هنگام مشاهده یک بخش خاص، در سمت چپ ظاهر می‌شوند.
* **Dashboard (list of records)** items serve as quick-access buttons or reports on the main component page.
* آیتم‌های **داشبورد (لیست رکوردها)** به‌عنوان دکمه‌های دسترسی سریع یا گزارش‌ها در صفحه اصلی کامپوننت عمل می‌کنند.

Use these strategically to create a clean, user-friendly backend layout for your component.
از این‌ها به‌صورت استراتژیک استفاده کنید تا چیدمان بک‌اند تمیز و کاربرپسندی برای کامپوننت خود ایجاد کنید.

---

## **Conclusion**
## **نتیجه‌گیری**

Adding Custom Admin Views in Joomla Component Builder empowers developers to design rich, interactive administrative interfaces. By properly setting menu placement, target views, and dynamic data handling, you can build professional back-end dashboards and management tools without manually writing all the boilerplate code. And because Custom Admin Views support the same **Init → Reset → Push → Fork** workflow used throughout the repository, you can iterate on these interfaces with confidence while keeping your bespoke layouts under source control.
افزودن ویوهای مدیریتی سفارشی در جوملا کامپوننت بیلدر به توسعه‌دهندگان قدرت می‌دهد رابط‌های مدیریتی غنی و تعاملی طراحی کنند. با تنظیم صحیح جای‌گذاری منو، ویوهای هدف و مدیریت پویای داده، می‌توانید داشبوردها و ابزارهای مدیریتی حرفه‌ای بک‌اند بسازید بدون اینکه همه کدهای تکراری (boilerplate) را دستی بنویسید. و چون ویوهای مدیریتی سفارشی از همان گردش کار **Init → Reset → Push → Fork** استفاده‌شده در سراسر مخزن پشتیبانی می‌کنند، می‌توانید با اطمینان روی این رابط‌ها تکرار و بهبود انجام دهید و در عین حال لایه‌های اختصاصی خود را تحت کنترل نسخه نگه دارید.

---