# تسجيل الدخول وتسجيل الخروج

في هذا الدرس تعلمنا كيفية تجهيز آلية تسجيل الخول والخروج

**جلب views تسجيل الدخول وتسجيل الخروج**

جانقو عندها views جاهزة لجميع الوظائف التي نحتاجها لتجهيز نظام المصادقة كل ماعلينا فعله هو عمل url لهذه ال views و عمل template 

``` python
from django.urls import path
from django.contrib.auth import views as auth_views


urlpattrens = [
    path('login/', auth_views.LoginView.as_view(), name='login'),
    path('logout/', auth_views.LogoutView.as_view(), name='logout'),
]

```
**اعادة توجيه المستخدم بعد تسجيل الدخول او تسجيل الخروج**

في الحالة الافتراضية لجانقو عند تسجيل دخول المستخدم سيتم نقله الى `accounts/profile` لكن في حالتنا نريد ان نوجهه الى صفحة المنتجات، لحسن الحظ جانقو لديها حل بسيط لهذه المشكلة وهو اضافة `LOGIN_REDIRECT_URL` في ملف settings.py بهذا الشكل

```
LOGIN_REDIRECT_URL = 'product_list'
LOGOUT_REDIRECT_URL = 'product_list'
```

 **جلب اليوزر في القالب و التحقق من انه مسجل دخوله او لا** 

ببساطة لدينا كائن مبني في قوالب جانقو يقوم بجلب المستخدم المسجل دخوله وهو `user` وهذا الكائن لديه بعض الخصائص المفيدة مثل `user.is_authenticated` التي تمكننا من التحقق من ان هذا اليوزر مسجل دخوله او لا.

**كيف يعرف جانقو ان هذا اليوزر مسجل دخوله او لا**

عبر استخدام الكوكيز وهي يستخدمها المتصفح لكي يعرف بيانات اليوزر. بداخل الكوكيز هناك حقل `sessionid` وهي مسجل بها الجلسة التي دخل فيها اليوزر ويتم تطابقها مع الجلسة المخزنة في قاعدة البيانات.


## ملحق

[About Browser Cookies](https://dev.to/flippedcoding/about-browser-cookies-5dn2)

[Django Documentations - All authentication views](https://docs.djangoproject.com/en/3.0/topics/auth/default/#all-authentication-views)