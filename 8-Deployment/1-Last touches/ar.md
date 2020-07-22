# اللمسات الأخيرة
في هذا الدرس سنقوم بتنظيم المشروع قبل عملية الإطلاق.

**تنظيف ال `migrations`**

نريد ان يكون مجلد `migrations` مكون من ملف واحد فقط وليس عدة ملفات تحتوي على التعديلات التي حصلت للمودل. طبق معي هذه الخطوات:

1. قم بالدخول على تطبيق جانقو
2. احذف جميع الملفات التي بداخل مجلد `migrations` عدا ملف `__init__.py`
3. قم بعمل `python manage.py makemigrations`
4. احذف ملف قاعدة البيانات `db.sqlite3`
5. قم بعمل `python manage.py migrate`

**تنظيم الروابط `urls.py`**

1. اضف `/` عند نهاية كل رابط.
2. اضف نوع البارامترفي الرابط مثل `<int: pk>`
3. بادئة الرابط اكتبها بداخل ملف ال `<app>/urls.py` التطبيق بدلا من الملف الرئيسي `store.py`  مثال لتطبيق *products*

**store/urls.py**
```
from django.urls import include, path


urlspattrens = [
    path('', include('products.urls'))
]
```

**products/urls.py**
```
from django.urls import include, path
from .views import product_list, product_details, add_product, edit_product


urlspattrens = [
    path('products/', product_list, name='product_list'),
    path('products/new/', add_product, name='add_product'),
    path('products/<int:pk>/', product_details, name='product_details'),
    path('products/edit/<int:pk>/', edit_product, name='edit_product'),
]
```