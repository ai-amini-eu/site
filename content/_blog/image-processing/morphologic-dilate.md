---
view::extends: _includes.blog.image_processing
view::yields: post_body
post::title: گسترش باینری مورفولوژیکی
post::category: پردازش تصویر
post::sub_category: مقدمه
post::order: 14
---

همانطور که از نام عملگر پیداست ، این عملگر باعث گسترش نقاط 1 در تصویر می شود. در عملگر گسترش نیز از یک ماسک ( نفاب ، پنجره ) - همانند آنچه که در "تعریف عمل فیلتر کردن" هست – استفاده می کنیم. در اینجا به جای ماسک به آن عنصر ساختمانی می گوییم که مقادیر عنصر ساختمانی 1 یا صفر می تواند باشد. گسترش تصویر A با عنصر ساختمانی B به صورت زیر تعریف می شود:

![](@url('assets/images/image-processing/dilate-formula.jpg'))

که در اینجا reflection عنصر ساختمانی B را حول مرکز خود قرینه می کند. به عبارت دیگر گسترش A با عنصر ساختمانی B بدین معنی است که اگر عنصر ساختمانی B را بر روی پیکسل های A حرکت دهیم ، و در هربار حرکت اشتراک عنصر ساختمانی با محدوده زیر عنصر ساختمانی در تصویر A تهی نباشد ، مقدار پیکسل مرکزی که عنصر ساختمانی بر روی آن قرار گرفته است ، برابر 1 خواهد شد. شکل روبور خروجی تصویری را پس از گسترش تصویر با عنصر ساختمانی 3*3 تمام 1 نشان می دهد.

![](@url('assets/images/image-processing/finger.jpg'))
*تصویر اصلی*

![](@url('assets/images/image-processing/dilated-finger.jpg'))
*حاصل گسترش تصویر*

#### پردازش تصویر در MATLAB

اعمال عملگر مورفولوژیکی گسترش در محیط MATLAB با استفاده تابع `imdilate` انجام می پذیرد.

```matlab
>> BW1 = imread('circbw.tif');
>> SE = strel('rectangle',[5 5]);
>> BW2 = imdilate(BW1,SE);
>> imshow(BW1),figure,imshow(BW2)
```
