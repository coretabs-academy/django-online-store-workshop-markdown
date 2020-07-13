# تسجيل مستخدم جديد

في هذا الدرس تعلمنا كيفية تجهيز صفحة تسجيل مستخدم جديد

**UserCreationForm**

هذه الفورم تأتي مع جانقو مجهزة للتعامل مع اليوزر او بالأحرى انشاء يوزر جديد

**كيفية عمل `import` لليوزر** 

ببساطة لدينا طريقتين 

الأولى

```python
 from django.contrib.auth.models import User
```

الثانية والتي ينصح بها

```
from django.contrib.auth import get_user_model

User = get_user_model()
```


## ملحق

[Built-in forms](https://docs.djangoproject.com/en/3.0/topics/auth/default/#module-django.contrib.auth.forms)

[Creating users](https://docs.djangoproject.com/en/3.0/topics/auth/default/#creating-users)