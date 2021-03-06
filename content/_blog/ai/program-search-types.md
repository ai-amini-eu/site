---
view::extends: _includes.blog.ai
view::yields: post_body
post::title: روش های جستجوی ناآگاهانه
post::category: هوش مصنوعی
post::sub_category: برنامه های نمونه
post::order: 16
---

![روش های جستجوی ناآگاهانه ](@url('assets/images/ai/program-search.jpg'))

مسئله یافتن کوتاهترین مسیرها در یک گراف جهت دار را در نظر بگیرید . یکی از روش های یافتن کوتاهترین مسیر در یک گراف جهت دار استفاده از الگوریتم فلوید می باشد . مسئله کوتاهترین مسیر بین شهرها حالت خاصی از مسئله کوتاهترین مسیر در یک گراف جهت دار است که در آن در صورتی که بین دو گره مسیری وجود داشته باشد ، این مسیر حتما در دوجهت می باشد . در این مسئله نیز می توان از الگوریتم فلوید استفاده کرد . اما در حال حاضر هدف استفاده از روش های جستجوی ناآگاهانه و آگاهانه برای یافتن کوتاهرین مسیر است . جستجوهای ناآگاهانه استفاده شده در این برنامه شامل روش های جستجوای زیر می باشد :

1. جستجوی سطحی
2. جستجوی سطحی یکنواخت
3. جستجوی عمقی
4. جستجوی عمقی محدود
5. جستجو عمقی تکراری

هریک از این جستجوها معایب و محاسن خاص خود را دارند ، اما از میان این روش های جستجو ، جستجوی سطحی یکنواخت ، همیشه بهینه است . با این حال این روش نیز مشکل زمانبر بودن را داراست . جستجوی آگاهانه ای که در این برنامه از آن استفاده شده است روش جستجوی A* می باشد . این روش جستجو با بهره گیری از روش های جستجوی سطحی و حریصانه اقدام به حل مسائل می کند . مهمترین نکته در مورد این روش جستجو این است که هیوریستیک استفاده شده در این روش باید یک هیوریستیک قابل قبول باشد .

#### نحوه استفاده از برنامه

برنامه فقط شامل یک پنجره اصلی است که همه ورودی ها در این پنجره وارد می شوند . پنجره اصلی برنامه از سه قسمت تشکیل یافته است . در سمت راست صفحه ترسیم نقشه قرار دارد . در این صفحه می توانید گراف بدون جهت مورد نظر را ترسیم کنید . در سمت چپ نیز یالهای خارج شده و وارد شده از هر گره به همراه وزن هریک از یالها و همچنین فاصله مستقیم هر گره از بقیه گره ها نشان داده می شود . قسمت بالایی فرم نیز شامل نوار ابزاری است که همه عملیات توسط دگمه های قرار گرفته بر روی نوار ابزار انجام می شوند .

#### ترسیم گراف در صفحه ترسیم

صفحه ترسیم در سمت راست فرم قرار دارد . برای قرار دادن گره ها بر روی این صفحه کافی است بر روی نقطه مورد نظر یک بار کلیک کنید . با یک بار کلیلک کردن بر روی صفحه ترسیم گره ای به صفحه اضافه می شود . برای حذف گره نیز می توانید بر روی گره مورد نظر دابل کلیک کنید . برای انتخاب گره نیز کافی است بر روی گره یک بار کلیک کنید . گره انتخاب شده رنگ متفاوتی نسبت به سایر گره ها خواهد داشت .

زمانی که گره ای را انتخاب می کنید ، نام آن گره به همراه همه یالهای متصل به این گره در قسمت بالای سمت چپ پنجره به نمایش در می آیند . نام گره و وزن یال ها را می توانید در این قسمت تغییر دهید . در صورتی که یالی از گره انتخاب شده به دیگر گره ها وجود نداشته باشد ، بخش بالایی سمت چپ فقط نام گره را نشان خواهد داد . در قسمت پایینی سمت چپ نیز فاصله مستقیم گره انتخاب شده از بقیه گره ها به نمایش در می آیند . این مقادیر را نیز می توانید تغییر دهید . به صورت پیش فرض هنگامی که یالی بین دو گره رسم می شود ، فاصله بین این دو گره ( وزن یال ) فاصله اقلیدسی بین آن ها در نظر گرفته می شود.

#### ترسیم یال از گره 1 به گره 2

ابتدا با کلیک کردن بر روی گره 1 آن گره را انتخاب کنید . سپس کلید Ctrl را فشار داده و و بر روی گره 2 کلیک کنید . در این هنگام یالی بین گره 1 و گره 2 ترسیم می شود . در صورتی که یالی بین گره اول و گره دوم وجود داشته باشد و سعی در ترسیم دوباره یال داشته باشید ، برنامه از ترسیم یال خودداری کرده و سیگنالی را برای آگاهی شما پخش می کند .

می توانید نقشه ترسیم شده را ذخیره کرده و یا نقشه ذخیره شده ای را باز کنید . برای این منظور می توانید از دکمه های قرار گرفته بر روی فرم استفاده کنید . دکمه New یک صفحه ترسیم جدید باز می کند . دکمه Load فایل نقشه را باز می کند و دکمه Save نقشه ترسیم شده را ذخیره می کند .
