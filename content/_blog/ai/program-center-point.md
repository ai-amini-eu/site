---
view::extends: _includes.blog.ai
view::yields: post_body
post::title: مسئله نقطه مرکزی
post::category: هوش مصنوعی
post::sub_category: برنامه های نمونه
post::order: 21
---

![](@url('assets/images/ai/center-point.jpg'))

فرض کنید در صفحه مختصات xy ، تعداد m نقطه به شکل تصادفی چیده شده اند و ما می خواهیم نقطه ای را بر روی این صفحه مختصات پیدا کنیم به طوری که مجموع فاصله اقلیدسی این نقطه از همه دیگر نقاط مینیمم باشد. با اینکه روش های ریاضی برای این مسئله وجود دارد، با این حال در این جا می خواهیم این مسئله را ب استفاده از الگوریتم تپه نوردی حل کنیم. با توجه به اینکه در این روش نیز ممکن است الگوریتم تپه نوردی در مینیمم محلی به دام بیفتد، از اینرو این الگوریتم را بجای یک بار چند بار اجرا کرده و بهترین جواب را به عنوان جواب نهایی انتخاب می کنیم.
