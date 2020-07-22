# رفع المشروع على هيروكو
في هذا الدرس سنتعلم كيفية اطلاق المشروع بالطريقة الصحيحة.

## الخطوات المطلوبة لعمل ديبلوي في هيروكو

1. سجل دخول على حسابك في هيروكو.
2. انشاء تطبيق جديد.
3. ربط التطيق بالمستودع على github.
4. تفعيل عملية اطلاق التطبيق تلقائيا بعد كل عملية بوش على github.

## تجهيز المشورع للإطلاق (الجزء الأول):

1. اضافة  STATIC_ROOT لإعدادات المشروع هذا الخيار يحدد مسار المجلد الذي سيتم اضافة الملفات الثابتة به عند تنفيذ الامر `python manage.py collectstatic`
2. اضافة `gunicorn` عبر pip 
3. اضافة ملف `Procfile` في المجلد الرئيسي بجانب `manage.py`, ثم اضافة هذا السطر بداخل الملف:

```
web: gunicorn store.wsgi
```

4. اضافة whitenoise عبر pip
5. اضافة WhiteNoise  الى قائمة MIDDLEWARE  في ملف settings.py, نضيفه في بداية القائمة تحت SecurityMiddleware بهذا الشكل

```
MIDDLEWARE = [
  'django.middleware.security.SecurityMiddleware',
  'whitenoise.middleware.WhiteNoiseMiddleware',
  ...
]
```

6. لاتنسى اضافة gunicorn و whitenoise الى `requirements.txt` مع رقم الإصدار بهذا الشكل:

```
gunicorn==VIRSION_NUMBER
whitenoise ==VIRSION_NUMBER
```


