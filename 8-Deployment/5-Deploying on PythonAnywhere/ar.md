# إطلاق المشروع على PythonAnywhere الجزء الأول

في هذا سنتعلم كيفية اطلاق المشروع على PythonAnywhere وتغير ال db من postgres الى mysql

## خطوات اطلاق المشروع:

1. سجل حساب  جديد على pythonanywhere من [هنا](https://www.pythonanywhere.com/registration/register/beginner/) ثم قم بتفعيله وسجل دخولك.

2. اضف ال domain الخاص ب pythonanywhere على ALOWED_HOSTS.

```
ALOWED_HOSTS = ['appid.herokuapp.com', 'username.pythonanywhere.com']
```

3. اضف mysqlclient عبر pip مع اضافته ايضا على `requirements.txt`.

4.  ثم عمل بوش للتعديلات على github.

5. ادخل على حسابك في pythonanywhere ثم على من Start New Console ادخل على Bash

6. اعمل clone للمستودع بداخل ال bash

```
git clone https://github.com/<username>/<store-repo>.git
```

7. انشاء بيئة وهمية عبر هذا الامر

```
mkvirtualenv venv --python=/usr/bin/python3.8
```

8. تفعيل البيئة الوهمية عبر هذا الامر

```
script /home/<username>/.virtualenvs/venv/bin/activate
```

9. تنصيب المكتبات التي نحتاجها لتشغيل المشروع.

```
# اذا كنت بداخل المستودع

pip install -r requirements.txt

# اذا كنت  داخل المستودع الرئيسي
pip install -r your-store-repo-name/requirements.txt
```

10. انشاء تطبيق ويب جديد

    1.ادخل على الصفحة الرئيسية على pythonanywhere 
    2.ادخل على الخيار Web اعلى الصفحة
    3.اضغط على زر Add new web app
    4.اضغط على Next
    5.ثم اضغط على Manual Configurations ثم اختار اصدار بايثون 3.8 
    6. Next

11. ربط تطبيق الويب بمشروع المتجر
على نفس الصفحة التي ظهرت لنا بعد انشاء تطبيق ويب سنقوم بتعديل بعض الخيارات حتى تتناسب مع المشروع.

    1.نبدأ بوضع مسار المستودع على pythonanywhere في خيار Source code
   2.نفس الشيء نضغ مسار البيئة الوهمية في خيار Edit path to virtualenv if desired
   3.نقوم بتعديل ملف wsgi في الخيار WSGI configuration file بهذا الكود 

```
import os
import sys

# لاتنسى تغير <username> باسم المستخدم الخاص بك 
# و تغير <store-repo> الى اسم مستودع المتجر
path = '/home/<username>/<store-repo>'
if path not in sys.path:
    sys.path.append(path)

from django.core.wsgi import get_wsgi_application
application = get_wsgi_application()
```

**انتقل الى الدرس التالي لنكمل باقي  إطلاق المشروع على PythonAnywhere**