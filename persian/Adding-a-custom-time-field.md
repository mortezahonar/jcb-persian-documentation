# Adding a Custom Time Field
# افزودن فیلد زمانی سفارشی

*Using Joomla Component Builder (JCB)*
*استفاده از جوملا کامپوننت بیلدر (JCB)*

### Video Reference
### مرجع ویدیویی

[00:00:00](https://www.youtube.com/watch?v=epA9zv4yWu0&list=PLQRGFI8XZ_wtGvPQZWBfDzzlERLQgpMRE&t=00h00m00s)
(*Click on these time links to watch the YouTube tutorial.*)
(*برای تماشای آموزش یوتیوب روی این لینک‌های زمانی کلیک کنید.*)

---

## 1. Overview
## ۱. مرور

In Joomla Component Builder, a **custom time field** allows you to capture specific time values (e.g., `05:15`) in your components. Because time is stored as an integer in databases, you cannot use a standalone time format - it must either be stored as part of a datetime or validated via text input.
در جوملا کامپوننت بیلدر، یک **فیلد زمانی سفارشی** به شما امکان می‌دهد مقادیر زمانی خاص (مثلاً `05:15`) را در کامپوننت‌های خود ثبت کنید. از آنجا که زمان به‌صورت عدد صحیح در دیتابیس‌ها ذخیره می‌شود، نمی‌توانید از یک فرمت زمانی مستقل استفاده کنید - باید یا به‌عنوان بخشی از یک تاریخ-زمان ذخیره شود یا از طریق ورودی متنی اعتبارسنجی شود.

This guide walks you through:
این راهنما شما را با موارد زیر آشنا می‌کند:

* Creating a **text field** for time entry
* ایجاد یک **فیلد متنی** برای ورود زمان
* Adding a **custom validation rule (Form Rule)**
* افزودن یک **قاعده اعتبارسنجی سفارشی (قاعده فرم)**
* Implementing **server-side and JavaScript validation**
* پیاده‌سازی **اعتبارسنجی سمت سرور و جاوااسکریپت**
* Integrating **time fields in repeatable structures**
* یکپارچه‌سازی **فیلدهای زمانی در ساختارهای تکرارشونده**

---

## 2. Setting Up a Time Field
## ۲. راه‌اندازی یک فیلد زمانی

[00:00:21](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h00m21s)

If you want users to enter a time such as `05:15`, you can:
اگر می‌خواهید کاربران زمانی مانند `05:15` وارد کنند، می‌توانید:

1. Create a **text field** in JCB.
۱. یک **فیلد متنی** در JCB ایجاد کنید.
2. Validate it using a **regular expression (Regex)** to ensure proper time format.
۲. آن را با استفاده از یک **عبارت باقاعده (Regex)** اعتبارسنجی کنید تا فرمت صحیح زمان تضمین شود.

> **Tip:** Regex can be applied via a **custom Joomla form rule**, ensuring server-side validation beyond JavaScript.
> **نکته:** Regex را می‌توان از طریق یک **قاعده فرم سفارشی جوملا** اعمال کرد که اعتبارسنجی سمت سرور را فراتر از جاوااسکریپت تضمین می‌کند.

---

## 3. Creating a Custom Form Rule
## ۳. ایجاد یک قاعده فرم سفارشی

[00:01:23](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h01m23s)

To validate the time format properly, you'll create a custom Joomla Form Rule.
برای اعتبارسنجی صحیح فرمت زمان، یک قاعده فرم سفارشی جوملا ایجاد خواهید کرد.

### Steps:
### مراحل:

1. Go to your **Joomla libraries** folder:
۱. به پوشه **کتابخانه‌های جوملا** خود بروید:
   `libraries/src/Form/Rule/`

2. Review existing rules (e.g., `EmailRule.php`, `UrlRule.php`) to understand their structure.
۲. قواعد موجود (مثلاً `EmailRule.php`، `UrlRule.php`) را بررسی کنید تا ساختار آن‌ها را درک کنید.
   [00:02:21](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h02m21s)

3. Create a new file, for example:
۳. یک فایل جدید ایجاد کنید، برای مثال:
   `/libraries/src/Form/Rule/TimeRule.php`

4. Extend `Joomla\CMS\Form\FormRule`:
۴. کلاس `Joomla\CMS\Form\FormRule` را گسترش دهید:

   ```php
   class JFormRuleTime extends FormRule
   {
       protected $regex = '^(?:[01]\d|2[0-3]):[0-5]\d$';
   }
   ```

   [00:02:43](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h02m43s)

5. In your **component's model XML** (e.g., `models/forms/item.xml`), add:
۵. در **XML مدل کامپوننت** خود (مثلاً `models/forms/item.xml`)، موارد زیر را اضافه کنید:

   ```xml
   <field name="event_time" type="text" label="Event Time" validate="time" filter="string" />
   ```

This connects your form field with your new validation rule.
این کار فیلد فرم شما را به قاعده اعتبارسنجی جدیدتان متصل می‌کند.

---

## 4. Adding the Field in Component Builder
## ۴. افزودن فیلد در کامپوننت بیلدر

[00:04:15](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h04m15s)

Within **Component Builder**:
درون **کامپوننت بیلدر**:

1. Navigate to **Fields → New**.
۱. به **Fields → New** بروید.
2. Choose **Type:** `text`.
۲. **Type:** را `text` انتخاب کنید.
3. Under **Validation**, enter the name of your custom rule (`time`).
۳. در بخش **Validation**، نام قاعده سفارشی خود (`time`) را وارد کنید.
4. Set **Filter** to `string`.
۴. **Filter** را روی `string` تنظیم کنید.

[00:04:44](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h04m44s)

This setup ensures that data is filtered and validated correctly on both the client and server.
این تنظیمات تضمین می‌کند که داده‌ها هم در سمت کلاینت و هم در سمت سرور به‌درستی فیلتر و اعتبارسنجی می‌شوند.

---

## 5. Enhancing with JavaScript Validation
## ۵. بهبود با اعتبارسنجی جاوااسکریپت

[00:05:00](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h05m00s)

To improve user experience, you can add JavaScript validation to the field to restrict invalid characters.
برای بهبود تجربه کاربری، می‌توانید اعتبارسنجی جاوااسکریپت را به فیلد اضافه کنید تا کاراکترهای نامعتبر را محدود کند.

Example steps:
مراحل مثال:

1. Add a **unique class or ID** to your field.
۱. یک **کلاس یا شناسه یکتا** به فیلد خود اضافه کنید.
2. Include JavaScript in your **view's footer script area** (accessible in JCB's View Scripts section).
۲. جاوااسکریپت را در **بخش اسکریپت‌های فوتر ویو** خود قرار دهید (در بخش View Scripts جی‌سی‌بی قابل دسترسی است).
3. The script should allow only numbers and a colon (`:`).
۳. اسکریپت باید فقط اعداد و یک دونقطه (`:`) را مجاز کند.

[00:05:37](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h05m37s)

You can use the field's ID (e.g., from your browser's Inspector) to target it directly:
می‌توانید از شناسه فیلد (مثلاً از ابزار Inspector مرورگر خود) برای هدف‌گیری مستقیم آن استفاده کنید:

```js
document.getElementById('jform_event_time').addEventListener('input', function() {
  this.value = this.value.replace(/[^0-9:]/g, '');
});
```

If invalid data is entered, the input can be cleared, or a message can be shown.
اگر داده نامعتبر وارد شود، می‌توان ورودی را پاک کرد یا یک پیام نمایش داد.

---

## 6. Using Time-Date Field in Repeatable Fields
## ۶. استفاده از فیلد تاریخ-زمان در فیلدهای تکرارشونده

[00:06:46](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h06m46s)

When working with **repeatable fields**, standard calendar fields do not work directly because of how dynamic instances are handled.
وقتی با **فیلدهای تکرارشونده** کار می‌کنید، فیلدهای تقویمی استاندارد مستقیماً کار نمی‌کنند زیرا نمونه‌های پویا به‌گونه‌ای متفاوت مدیریت می‌شوند.
To overcome this, JCB includes a **custom DateTime picker** integrated through JavaScript.
برای غلبه بر این مشکل، JCB یک **انتخاب‌گر تاریخ-زمان سفارشی** را از طریق جاوااسکریپت یکپارچه کرده است.

[00:08:08](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h08m08s)

### Key Steps:
### مراحل کلیدی:

1. Use a **custom JavaScript file** added in JCB's **Scripts** section.
۱. از یک **فایل جاوااسکریپت سفارشی** استفاده کنید که در بخش **Scripts** جی‌سی‌بی اضافه شده است.
2. Loop through each repeatable instance using JavaScript or PHP to attach the picker dynamically.
۲. با استفاده از جاوااسکریپت یا PHP روی هر نمونه تکرارشونده حلقه بزنید تا انتخاب‌گر به‌صورت پویا متصل شود.
3. Example (simplified):
۳. مثال (ساده‌شده):

   ```js
   for (let i = 0; i < 50; i++) {
       let field = document.getElementById('time_field_' + i);
       if (field) {
           jQuery(field).datetimepicker({
               format: 'H:i',
               step: 15
           });
       }
   }
   ```

[00:09:52](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h09m52s)

---

## 7. Handling Multiple Time-Date Fields
## ۷. مدیریت چندین فیلد تاریخ-زمان

[00:10:51](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h10m51s)

When your component includes several time fields (e.g., start, end, or target times), JCB allows you to manage them efficiently by:
وقتی کامپوننت شما چندین فیلد زمانی دارد (مثلاً زمان شروع، پایان یا هدف)، JCB به شما امکان می‌دهد آن‌ها را به‌طور کارآمد مدیریت کنید:

* Defining an array of targeted field types.
* تعریف یک آرایه از انواع فیلد هدف.
* Using a PHP loop to initialize their date-time pickers dynamically, reducing redundant code.
* استفاده از یک حلقه PHP برای راه‌اندازی پویای انتخاب‌گرهای تاریخ-زمان آن‌ها و کاهش کد تکراری.

[00:11:44](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h11m44s)

---

## 8. Community Documentation and Help Resources
## ۸. مستندات جامعه و منابع راهنما

[00:12:14](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h12m14s)

Joomla Component Builder provides built-in documentation links accessible via the **Help menu** in every list view.
جوملا کامپوننت بیلدر لینک‌های مستندات داخلی را فراهم می‌کند که از طریق **منوی راهنما** در هر ویوی لیست قابل دسترسی هستند.

You can access the official **Wiki** and contribute to improving the documentation:
می‌توانید به **ویکی** رسمی دسترسی داشته باشید و در بهبود مستندات مشارکت کنید:

* **URL:** [Readme Documentation](http://projects.vdm.io/projects/Joomla-component-builder/wiki)
* **URL:** [مستندات Readme](http://projects.vdm.io/projects/Joomla-component-builder/wiki)

If you wish to contribute or request help documentation for your component, contact the project maintainers.
اگر می‌خواهید مشارکت کنید یا مستندات راهنمای کامپوننت خود را درخواست دهید، با نگه‌دارنده‌های پروژه تماس بگیرید.

[00:14:40](https://www.youtube.com/watch?v=epA9zv4yWu0&t=00h14m40s)

---

## 9. Summary
## ۹. خلاصه

* Use **text fields** with custom **form rules** for time input.
* برای ورود زمان از **فیلدهای متنی** با **قواعد فرم** سفارشی استفاده کنید.
* Implement **Regex-based validation** in PHP and **character restriction** in JavaScript.
* اعتبارسنجی مبتنی بر **Regex** را در PHP و **محدودیت کاراکتر** را در جاوااسکریپت پیاده‌سازی کنید.
* For **repeatable fields**, ensure dynamic initialization using JavaScript loops.
* برای **فیلدهای تکرارشونده**، راه‌اندازی پویا با استفاده از حلقه‌های جاوااسکریپت را تضمین کنید.
* Explore **Component Builder's script integration** for full control.
* **یکپارچه‌سازی اسکریپت کامپوننت بیلدر** را برای کنترل کامل کاوش کنید.
* Leverage the **JCB Wiki** for learning and contributing.
* برای یادگیری و مشارکت از **ویکی JCB** بهره ببرید.

---