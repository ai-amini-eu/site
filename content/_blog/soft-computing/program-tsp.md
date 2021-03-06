---
view::extends: _includes.blog.soft_computing
view::yields: post_body
post::title: فروشنده دوره گرد
post::category: هوش محاسباتی
post::sub_category: برنامه‌های نمونه
post::order: 9
---

![](@url('assets/images/soft-computing/tsp.jpg'))

فرض کنید فروشنده ای بخواهد برای فروش کالاهایش به 20 شهر مسافرت کند . هر شهر توسط یک جاده به چند شهر دیگر متصل است . برای به حداقل رساندن زمان مسافرت ، می خواهیم کوتاهترین مسیری را پیدا کنیم که از شهر محل سکونت فروشنده شروع می شود و از هر شهر دقیقا یکبار عبور می کند و مجددا به شهر محل سکونت فروشنده باز می گردد. تعیین کوتاهترین مسیر در این مسئله را مسئله فروشنده دوره گرد می نامیم.

#### درباره برنامه

الگوریتم هایی با استفاده از روش برنامه نویسی پویا و الگوریتم های ژنتیک برای حل مسئله فروشنده دوره گرد ارائه شده اند . در این برنامه از الگوریتم های جدیدی ارائه شده است که پس از مطالعه دیگر الگوریتم ها و بهبود و اضافه کردن روش های جدید به آنها پیاده سازی شده است.

در این برنامه از الگوریتم های ژنتیک و روش Simulated Annealing برای حل مسئله فروشنده دوره گرد استفاده شده است. عملگر های ادغام ، جهش و انتخاب الگوریتم ژنتیک نیز به چند روش مختلف پیاده سازی شده اند که می توان بر هر مسئله ترکیبی از آنها را امتحان کرد.

#### نحوه استفاده از برنامه

برنامه از سه قسمت مختلف تشکیل شده است که به شرح زیر می باشند :

1. قسمت سمت چپ برای تنظیم پارامترهای الگوریتم ژنتیک می باشد
2.  قسمت سمت راست نقشه ای است که بر روی آن شهر ها را مشخص می کنیم
3. قسمت پایینی برای تنظیم پارامترهای الکوریتم Simulated Annealing می باشد .

#### مشخص کردن شهر ها بر روی نقشه

برای ایجاد یک نقشه جدید دو روش مختلف وجود دارد ، در روش اول برنامه به صورت تصادفی تعداد مشخصی شهر را بر روی نقشه قرار می دهد و در روش دوم ، شما محل شهر ها را بر روی نقشه مشخص می کنید.

برای تولید نقشه به صورت تصادفی از قسمت سمت چپ و در فیلد City تعداد شهر های نقشه را وارد کرده و بر روی دکمه Random کلیک کنید . برنامه به تعداد شهر هایی که مشخص کرده اید به ثورت تصادفی شهر بر روی نقشه قرار می دهد. در صورتی که بخواهید به طور دستی نقشه را طراحی کنید ، کافی است در محل مورد نظر بر روی نقشه یک بار کلیک کنید . در نقظه کلیک شده به نقطه به رنگ قرمز قرار می گیرد که نشان دهنده یک شهر بر روی نقشه است. برای پاک کردن نقشه نیز بر روی دکمه Clear کیلک کنید .
