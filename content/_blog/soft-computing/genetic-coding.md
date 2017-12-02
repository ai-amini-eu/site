---
view::extends: _includes.blog.soft_computing
view::yields: post_body
post::title: کدگذاری و نحوه نمایش
post::category: هوش محاسباتی
post::sub_category: الگوریتم ژنتیک
post::order: 1
---

![](@url('assets/images/soft-computing/genetic-coding.jpg'))

در الگوریتم ژنتیک، منظور از کدگذاری انتخاب روشی برای نمایش نمایش جواب مسئله ای است که باید بهینه گردد. به عنوان مثال در مسئله 8 وزیر یک روش کدگذاری می تواند استفاده از یک آرایه 8 عنصری باشد که هر عنصر از آرایه نشان دهنده سطری است که وزیر در آن قرار دارد. به عنوان مثال آرایه زیر را در نظر بگیرید :

![](@url('assets/images/soft-computing/coding-table.jpg'))

با توجه به مقادیر آرایه در میابیم که وزیر اول در ستون اول و سطر چهارم ، وزیر دوم در ستون دوم و سطر سوم ، وزیر سوم در ستون سوم و سطر دوم ، وزیر چهارم در ستون چهارم و سطر ششم ، وزیر پنجم در ستون پنجم و سطر هشتم ، وزیر ششم در ستون ششم و سطر هفتم ، وزیر هفتم در ستون هفتم و سطر پنجم و زیر هشتم در ستون هشتم و سطر اول از صفحه	 شطرنج قرار گرفته است. در الگوریتم های ژنتیک به هرجواب مسئله یک کروموزوم و به هر متغیر از آن یک ژن می گوییم. در اینجا جواب مسئله را با استفاده از یک آرایه 8 عنصری نشان دادیم که به آرایه یک کرموزوم و به هر عنصر از آریه یک ژن می گوییم. با توجه به مسئله بهینه سازی برای هر ژن می توان سوالات زیر را مطرح کرد :

-  آیا مقادیر قابل قبول برای ژن در یک باژه مشخص قرار دارد ؟ ( در مثال 8 وزیر هر ژن می تواند عددی بین 1 تا 8 به خود بگیرد )
-  آیا دامنه مقادیر ژن گسسته است یا پیوسته؟ ( در مثال هشت وزیر این مقادیر گسسته هستند )
-  آیا در صورت مسئله محدودیت هایی برای انتخاب مقادیر ژن وجود دارد ؟ ( در مسئله 8 وزیر محدودیتی نداریم )

نحوه نمایش جواب مسئله و ژن ها در موفقیت الگوریتم و نحوه پیاده سازی الگوریتم ژنتیک تاثیر بسیار مهمی دارد. در بیشتر مسائل نیز روش های مختلفی برای نشان دادن جواب مساله می توان طراحی کرد. به عنوان مثال در مسئله 8 وزیر به جای استفاده از بردار ( آرایه یک بعدی ) 8 عنصری می توان از یک ماتریس 8 * 8 استفاده کرد که در آن هر وزیر می تواند در هریک از 64 خانه صفحه شطرنج قرار گیرد. هنگام استفاده از این روش نمایش ، در یک خانه ممکن است بیش از یک وزیر قرار گیرد بنابراین هنگام پیاده سازی الگوریتم باید از بروز چنین مسئله ای جلوگیری کنیم. همچنین از صورت مسئله 8 وزیر پیداست که هیچ دو وزیری نمی تواند در یک ستون قرار گیرد ( یا همچنین هیچ دو وزیری نمی تواند در یک سطر قرار گیرد ). این در حالی است که در نمایش ماتریسی مسئله 8وزیر می توان در یک ستون و در سطر بیش از یک وزیر قرار داد. اما برای هرچه ساده تر شدن پیاده سازی دیگر مراحل الگوریتم ژنتیک برای این مسئله و افزایش کارآیی زمانی الگوریتم ، می توانیم تریبی اتخاذ کنیم که هیچ دو وزیری در یک سطر ( یا ستون) قرار نگیرد. بنابراین می توانیم از نمایش برداری برای آن استفاده کنیم که در این نحوه نمایش مقدار موجود در هر ژن نشان دهنده شماره سطری ( یا ستون ) است که وزیر در آن قرار دارد. به عنوان مثال اگر اولین ژن از کروموزوم مقداری برابر 6 داشته باشد ، این بدان معناست که وزیر اول در سطر ششم از ستون اول بر روی صفحه شطرنج قرار دارد. در نمایش برداری مسئله 8 وزیر مشکل قرار گرفتن بیش از یک وزیر در یک خانه نیز برطرف می شود. همانطور که در این مثال ساده دیدیم ، طراحی نحوه نملیش مسئله نقش حیاتی در اجرا و پیاده سازی الگوریتم ژنتیک بازی می کند. در اینجا ما به بررسی روش های معمول نحوه نمایش می پردازیم. اما یک طراح الگوریتم ژنتیک برای مسائل مختلف ممکن است از روش های دیگری برای نمایش کروموزوم استفاده کند. در حالت کلی هنگام طراحی یک روش نمایش کروموزوم باید موارد زیر را در نظر بگیریم :

- کروموزوم باید به گونه ای طراحی شود که تا حد ممکن از اطلاعات مسئله برای کاهش تعداد حالات فضای حالت استفاده کند. به عنوان مثال در مسئله 8 وزیر با تبدیل نمایش ماتریسی به نمایش برداری فضای حالت مسئله به طور چشمگیری کوچک گردید
- در یک کروموزوم باید بتوان براحتی محدودیت های مسئله را اعمال کرد و در اثر اعمال مراحل دیگر الگوریتم ژنتیک محدودیت های مسئله نقض نگردد
- تا حد امکان کروزوم نباید در اثر اجرای مراحله ادغام ( تولید نسل جدید ) به حالت نامعتبر تبدیل گردد. در برخی مسئله گزیر از حالت های نامعتبر در نحوه نمایش امکان پذیر نخواهد بود و باید در روش ادغام کروموزوم های تغییر ایجاد کنیم.

#### نمایش باینری

در این نحوه نمایش هر ژن از کروموزوم مقدار 1 یا 0 به خود می گیرد و موجب تشیکل یک رشته باینری در کرموزوم می گردد. به عنوان مثال فرض کنید یک تابع 3 پارامتری داریم و می خواهیم مقدار این 3 پارامتر را طوری انتخاب کنیم که مقدار تابع مینیمم گردد. فرض کنید هر پارامتر یک مثدار اعشاری 4 بایتی ( 32 بیتی ) باشد. در صورتی که بخواهیم از روش نمایش باینری برای این 3 پارامتر استفاده کنیم، یک رشته باینری به طول 96 بیت باید تشکیل دهیم.

#### نمایش مقداری

 در این روش نمایش ، مقادیر واقعی متغیر ها را نشان می دهیم. به عنوان مثال در مسئله 8 وزیر هر ژن شماره سطری را نشان می دهد که وزیر در آن قرار دارد. با وجود اینکه روش های نمایش دیگری همچون نمایش اکتال ، نمایش هگزادسیمال نیز وجود دارد، اما با این حال نحوه نمایش حالتی از مسئله وابسته به مسئله بوده و به تجربه و مهارت طراح الگوریتم ژنتیک بستگی دارد.