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

### استعمال تاق `{% static %}` للوصول الى الملفات الثابة في ال template

جانقو لديها تاق يمكننا من الوصول الى الملفات الثابة بسهولة بدون ان نكتب المسار كامل كل مرة نحتاج للوصول الى هذه الملفات.

دعنا نجلب ملفات ال css عن طريق هذا التاق

**base.html**

```
{% load static %}

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="{% static 'normalize.css' %}" />
    <link rel="stylesheet" href="{% static 'style.css' %}" />
    <title>{% block title %} Base {% endblock %}</title>
</head>
<body>
{% block content %} {% endblock %}
</body>
</html>
```
دائما عند استعمال تاق غير مبني مسبقا في ال template نقوم بعمل تحميل له عبر هذا التاق `{% load tages_module %}`

ثم نستعمل التاق عادي مثل البقية.

## رابط ملف التنسيقات المستخدم:

[styles.zip](https://github.com/coretabs-academy/django-online-store-workshop-markdown/raw/master/5-Finishing%20products%20app/8-Styling%20project/assets/styles.zip)
