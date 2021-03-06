---
view::extends: _includes.blog.ai
view::yields: post_body
post::title: مسئله چیدمان دینامیک (DLP)
post::category: هوش مصنوعی
post::sub_category: برنامه های نمونه
post::order: 20
---

![](@url('assets/images/ai/dlp.jpg'))

برنامه حاضر ، یک نسخه آموزشی است که برای حل مساله چیدمان دینامیک طراحی شده است . این برنامه برای حل مساله چیدمان دینامیک از الگوریتم Simulated Annealing و الگوریتم ژنتیک استفاده کرده است . چون این برنامه برای آشنایی بیشتر با الگوریتم های مذکور تهیه شده ، از اینرو پس از اجرای الگوریتم Simulated Annealing نمودارهای مربوط به این الگوریتم نیز ترسیم شده و نمایش داده می شوند . زمانی که برنامه لود می شود ، داده های مسئله پیش فرضی را نیز به همراه آن لود می کند .

مسئله چیدمان دینامیک پیش فرض شامل 5 پریود و 6 مکان می باشد . هزینه های جابجایی مواد ، تعویض واحد ها ، تخصیصی واحد ها به مکان ها و فاصله بین مکان ها نیز مشخص گردیده اند . برای مشاهده هزینه ها به برگه Costs مراجعه کنید . برای اجرای الگوریتم SA بر روی دکمه `Start Simulated Annealing` کلیک کنید . الگوریتم شروع به اجرا خواهد کرد . اجرای الگوریتم ممکن است مدتی نسبتا طولانی به طول بیانجامد . پس از اجرای الگوریتم نحوه چیدمان واحد ها در سالن ها به نمایش در خواهد آمد.

برای تغییر دادن مقادیر پارامترها ، منوی `File->Change Parameters` را انتخاب کنید . پنجره ای به نمایش در خواهد آمد که در ان می توانید مقادیر جدید پارامتر ها را وارد کنید . در این پنجره دو دکمه به نام های Update و Calc وجود دارد . در صورتی که بر روی دکمه Calc کلیک کنید ، بر اساس مقادیر وارد شده برای پارامترهای Fmin ، Fmax ، Pc و Pf مقدار پارامترهای elMax ، Tin و α محاسبه می شوند . پس از محاسبه نیز پنجره بسته شده و مقادیر جدید در پنجره اصلی نمایش در می آیند . ممکن است مقادیر پارامترهای elMax ، Tin و α از قبل مشخص باشند و نیازی به محاسبه آنها از روی پارامترهای دیگر نباشد . در این صورت بر روی دکمه Update کلیک کنید . پنجره بسته شده و مقادیر در پنجره اصلی به نمایش در می آیند .

برنامه حاضر این امکان را دارد که بر اساس تعداد پریود ها و مکان ها مسئله جدیدی طرح کند که هزینه های ان به طور تصادفی به وجود می آیند . برای این منظور منوی `File->Random Costs` را انتخاب کنید . در پنجره ای ظاهر می شود تعداد پریود ها و مکان ها و همچنین مقادیر پارامترهای مسئله را وارد کرده و بر روی دکمه Save کلیک کنید . مسئله جدیدی با هزینه های تصادفی به وجود می آید . برای مشاهده هزینه های مسئله جدید می توانید به برگه Costs مراجعه کنید .
