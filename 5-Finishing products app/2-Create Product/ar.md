# انشاء منتج جديد

تعلمنا في هذا الدرس كيفية انشاء form واضافة المنتجات منها

## ماهو CSRF (Cross-site request forgery)؟

ببساطة هذا الهجوم يمكن المهاجم من تعديل البيانات التي يرسلها المستخدم الى السيرفر مثلا بدلا من تحويل اموال الى صديقك يقوم المهاجم بتغير البيانات ليتم ارسال الأموال الى حسابه.

## ماذا يعني POST؟

تعني ان هذا الطلب سيقوم باضافة بيانات للسيرفر وفي حالتنا سنقوم بإنشاء منتج جديد.

## الدالة `redirect()`

تقوم بعمل اعادة توجيه لصفحة أخرى.

## اضافة منتج من ال view

علينا عمل تحقق من اذا كان الطلب POST ننشأ منتج جديد مثل ماتعلمنا Django ORM ونعمل اعادة توجيه تعلمنا بأن المنتج تم انشائه بنجاح.

اذا لم يكن الطلب POST نعمل `render` لصفحة اضافة المنتج.

## ملحق

**هنا شرح لأهم عشرة ثغرات يجب على كل مطور معرفتها!**

https://www.youtube.com/watch?v=rWHvp7rUka8&list=PLyqga7AXMtPPuibxp1N0TdyDrKwP9H_jD

[Cross Site Request Forgery (CSRF)](https://owasp.org/www-community/attacks/csrf)

[HTTP request methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
