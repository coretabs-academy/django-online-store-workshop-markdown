# إعدادات الإطلاق
في هذا الدرس سنتعلم كيفية فصل اعدادت التطوير عن اعدادت الاطلاق و ربط اعدادات الاطلاق بقاعدة بيانات postgresql.

## تجهيز المشورع للإطلاق (الجزء الثاني):
1. عمل ملف منفصل لإعدادت الاطلاق بداخل مجلد store وفالنسميه `prod_settings.py`
2. اضافة الخيار ALLOWED_HOSTS الى `prod_settings.py` وهي قائمة نضع بها دومين المشروع بهذا الشكل

```
ALLOWED_HOSTS = ['app_name.herokuapp.com']
```

3. اضافة `DEBUG = False`  الى `prod_settings.py` مع تغير قيمتها الى `True` في حال ظهر لك خطأ وتريد اظهار رسالة الخطأ على هيروكو.
4. اضافة `SECRET_KEY` الى `prod_settings.py`  وجلب قيمته من متغير البيئة بهذا الشكل

```
import os

SECRET_KEY = os.environ.get('SECRET_KEY')
```

5. استيراد كل اعدادت التطوير على اعدادات الاطلاق. قم باضافة هذا السطر في بداية ملف `prod_settings.py`

```
from .settings import *
```

6. في ملف `store/urls.py` نقوم بتجاهل السطر الذي يمكننا من عرض الصور في بيئة التطوير. بهذا الشكل.

```
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    ...
]

if settings.DEBUG:
    urlpattrens += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

7. اضافة متغيرات البيئة التي نحتاجها على هيروكو عبر الدخول الى التطبيق ثم settings ثم Reveal Config Vars

* توليد مفتاح سري جديد عبر الدخول على django shell ونسخ هذه الأسطر. انسخ المفتاح الذي تم طباعته 

```
from django.core.management.utils import get_random_secret_key

print(get_random_secret_key())
```
* الان نضيف SECRET_KEY على هيروكو مع القيمة التي تحصلنا عليها.

* اضافة متغير البيئة DJANGO_SETTINGS_MODULE  على هيروكو وقيمته `store.prod_settings`

8. استعمال postgres بدلا من sqlite:

* اضافة المكتبات dj-database-url و psycopg2-binary ثم اضافتهم على ملف requirements.py مع رقم الاصدار.
* اضافة هذا الكود على `prod_settings.py`
```
import dj_database_url


DATABASES = {
    'default': dj_database_url.config(
        default=os.environ.get('DATABASE_URL')
    )
}
```
9. عمل push

10. تنفيذ اوامر جانقو على هيروكو عبر الدخول على التطبيق ثم More ثم Run console ثم كتابة bash في الحق النصي الذي سيظهر. الان يمكننا عمل migrate و createsuperuser مثل مانفعل في بيئة التطوير.

### اضافة عينة لمتغيرات البيئة

ننصح بعمل ملف `sample.env` في المجلد الريئيسي به كل متغيرات البيئة التي يحتاجها المشروع مع مثال للقيمة المطلوبة. هذه العينات ستسهل عليك الكثير عند عودك الى مشروع قديم او عند عمل مبرمج اخرمعك في المشروع.


## ملحق

[How to Deploy Django Applications on Heroku](https://simpleisbetterthancomplex.com/tutorial/2016/08/09/how-to-deploy-django-applications-on-heroku.html)
