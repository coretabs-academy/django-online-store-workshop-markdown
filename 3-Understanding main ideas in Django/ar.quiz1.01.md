^ حدد الأمر الذي ينشئ تطبيق جانقو اسمه `products`

* `python manage.py runserver`

* `python manage.py startproject products`

** `python manage.py startapp products`

* `python manage.py startapp store`

$ حاول مرة أخرى أو راجع الدروس السابقة

-

^ ماهي ال views؟

* تمكننا من عمل روابط

* تمكننا من عمل جدول بقاعدة البيانات

** تمكننا من استلام الطلبات من المستخدم ومعالجتها ثم عرض رد بما هو يناسب

$ حاول مرة أخرى أو راجع الدروس السابقة

-

^ اي من هذه الطرق هي الصحيحة لإنشاء رابط ل say_hi

** أ
```
from django.urls import path

from .view import say_hi

urlpattrens = [
    path('say-hi/', say_hi)
]
```
* ب

```
urlpattrens = [
    'say-hi/'
]
```
$ حاول مرة أخرى أو راجع الدروس السابقة

-

^ اي من هذه الطرق تمكن جانقو من البحث في مجلد templates بالمشروع؟

** أ

```
TEMPLATES = [
    {
        ...

        'DIRS': [os.path.join(BASE_DIR, 'templates')],

        ...
    },
]
```

* ب

```
TEMPLATES = [
    {
        ...

        'DIRS': ['templates'],

        ...
    },

```
$ حاول مرة أخرى أو راجع الدروس السابقة

-

^ ماهي الدالة التي تمكننا من عرض القالب؟

* `path()`

** `render()`

* `HttpResponse()`

$ حاول مرة أخرى أو راجع الدروس السابقة

-

^ كيف نستخدم المتغير `name` بداخل القالب؟

* `{% name %}`

** `{{ name }}`

* `name`

$ حاول مرة أخرى أو راجع الدروس السابقة
