# تركيب قالب المتجر

نحن الباك اندرز ليس علينا تنسيق الموقع نحن نجعله ينبض بالحياة فقط :grin:. 

في هذا المخيم سنركز على الباك اند فقط وسنأخذ التنسيقات جاهزة ونضعها في مشروعنا المتواضع :relaxed:

### التعامل مع الملفات الثابتة (Static files):
مثل الوسائط يجب علينا اضافة بعض المتغيرات لإعدادات المشروع لكي نستطيع التعامل مع الملفات الثابتة مثل (Css, Js, images).

ندخل على `store/settings.py` ونضف هذا الكود ,  جانقو ستقوم بالبحث عن الملفات الثابة في المسارات الموجودة بهذه القائمة


```
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'static')
]
```

ثم ننشئ مجلد `static` بجانب ملف `manage.py` ونضع به الملفات الثابتة

## رابط ملف التنسيقات المستخدم:

[styles.zip](https://github.com/coretabs-academy/django-online-store-workshop-markdown/raw/master/5-Finishing%20products%20app/8-Styling%20project/assets/styles.zip)
