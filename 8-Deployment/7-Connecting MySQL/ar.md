# ربط قاعدة البيانات MySQL

## اتبع الخطوات التالية في pythonanywhere
* قم بإنشاء قاعدة بيانات (على سبيل المثال storedb)
* غير كلمة السر (استعمل كلمة سر قوية)

## الآن نعود للاعدادات
يجب أن يكون رابط قاعدة البيانات على هذا الشكل

```
DATABASE_URL='mysql://USER:PASSWORD@LINK:PORT/DBNAME'
```

و تأكد أن mysqlclient موجود في ملف requirements.txt كالتالي

```
mysqlclient==2.0.1
```