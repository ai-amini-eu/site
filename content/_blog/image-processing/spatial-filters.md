---
view::extends: _includes.blog.image_processing
view::yields: post_body
post::title: فیلترهای آرام کننده حوزه مکانی
post::category: پردازش تصویر
post::sub_category: مقدمه
post::order: 11
---

برای انجام تبدیلات در هر دو حوزه مکانی از فیلترها استفاده می کنیم .فیلترها در به دو دسته تقسیم می شوند:

- **فیلترهای پایین گذر ( Low Pass Filter )** : که با عبور از پیکسل های با فرکانس کم ، بر روی پیکسل های با فرکانس بالا تغییرات ایجاد می کنند.

- **یلترهای بالاگذر ( High Pass Filter )** : که با عبور از پیکسل های با فرکانس بالا ، بر روی پیکسل های با فرکانس پایین تغییرات ایجاد می کنند.

پیکسل فرکانس پایین پیکسلی است که اختلاف شدت روشنایی آن پیکسل با پیکسل های همسایه اش کم باشد ( نقاط آرام تصویر ). در مقابل پیکسل فرکانس بالا پیکسلی است که اختلاف شدت روشنایی آن پیکسل با پیکسل های همسایه اش زیاد باشد ( لبه ها و نویزها ).

با توجه به مطالب فوق می توان نتیجه گرفت که نتیجه اعمال فیلترهای پایین گذر ، تصویری آرام خواهد بود ( لبه ها و نویزها تا حدودی آرام می شوند )و با اعمال فیلتر بالاگذر نیز تصویری با جزئیات بیشتر به دست می آید. شکل زیر تصویری را پس از اعمال فیلتر پایین گذر و بالا گذر نشان می دهد :

![](@url('assets/images/image-processing/lena.jpg'))

همانطور که هنگام توضیح عملگر کانولوشن بررسی کردیم، فیلترهای ماسکی را با کانولوت کردن ماسک بر روی تصویر می توان اعمال کرد. در ادامه به بررسی برخی از فیلترهای آرام کننده رایج می پردازیم.

#### فیلترهای پایین گذر میانگین

ساده ترین نوع فیلترهای پایین گذر فیلترهای میانگین می باشند. یک فیلتر میانگین m * n شامل ضرایبی مثبت می باشند که همه این ضرایب بر عکس مجموع کل ضرایب فیلتر ضرب می شوند به عبارت دیگر همه عناصر ماسک مقداری برابر با 1/mn خواهند داشت. به عنوان مثال یک فیلتر میانگین 3 * 3 به صورت زیر مشخص می شود:

![](@url('assets/images/image-processing/blur-mask.jpg'))

تصویر آرام شده مذکور با استفاده از همین ماسک صورت گرفته است. برای بلور کردن بیشتر تصویر از ماسک های بزرگتری با سایز m * n باید استفاده کرد که مقادیر همه عناصر ماسک برابر با مقدار 1/mn خواهد بود. بدیهی است هرچه اندازه ماسک بزرگتر باشد ، زمان بیشتری برای پردازش تصویر نیاز خواهد بود. به نظر شما از نظر محاسباتی 2 بار کانولوت کردن ماسک 3*3 زمان بیشتری را مطلبد یا اعمال کردن 1 بار ماسک 5*5 ؟ در زیر فیلتر آرام کننده دیگری که به فیلتر پایین گذر گاوس ( Gaussian ) مشهور است ، نمایش داده شده است :

![](@url('assets/images/image-processing/gaussian-formula.png'))

شبه کد زیر نحوه تولید فیلتر آرام کننده گاوسین را نشان می دهد :

```basic

Function Gaussian( maskWidth, maskHeight )
Begin
  filter = double[maskHeight, maskWidth]
  For I = 1 to maskWidth Do
    For J = 1 To maskHeight Do
      filter[J,I] = g(I,J)
    End For
  End For
  Return filter
End
```

همانند  دیگر فیلترهای حوزه مکانی ، فیلتر گاوسین نیز  با استفاده از عملگر کانولوشن بر روی تصویر اعمال می شود.

#### فیلتر میانه ( Median )

فیلتر پایین گذر دیگری که نسبت به فیلترهای دیگر به زمان پردازش بیشتری نیاز دارد ، فیلتر میانه است. فیلتر پایین گذر میانه از یک همسایگی m * n استفاده می کند و روش کار آن نیز به این صورت است که کل همسایگی ها را به صورت صعودی مرتب کرده و عنصر وسط اعداد مرتب شده را انتخاب و جایگزین پیکسل مرکزی می کند. لازم به ذکر است که فیلتر پایین گذر میانه برای حذف نویز فلفل نمکی ( Salt & Pepper ) می تواند مورد استفاده قرار گیرد. شکل زیر تصویر نویزداری ( نویز فلفل نمکی ) را نشان می دهد که با استفاده از فبلتر میانه ارتقا یافته است:

![](@url('assets/images/image-processing/median-original.jpg'))
*تصویر اصلی*

![](@url('assets/images/image-processing/median.jpg'))
*نتیجه اعمال فیلتر میانه*

  در مقاله بعدی نیز به معرفی برخی از فیلترهای تیزکننده پرکاربرد در پردازش تصویر اشاره  کرده ایم.
