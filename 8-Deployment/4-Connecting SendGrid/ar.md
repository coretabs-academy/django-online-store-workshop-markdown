# ارسال الايميلات في جانقو

في هذا الدرس سنتعرف على SMPT و كيفية ارسال الايميلات في جانقو

## الفرق بين HTTP و SMPT

**Hypertext Transfer Protocol (HTTP):**

هو بروتوكول لارسال البيانات على الانترنت يوجد به نوعان http وهو يرسل البيانات بطريقة غير محمية و https وهو يرسل البيانات مشفرة.

**Simple Mail Transfer Protocol (SMPT):** 

هو بروتوركول يمكنك من ارسال الايميلات من سيرفر الا اخر.

## انواع خدمات الايميل:

* **خدمة ايميلات شخصية:** وهي مثل مانعرف مثل (gmail, outlook, yahoo) تقوم بارسال او استقبال ايميلات شخصية من اصدقائك او زملائك ومديرك في العمل او ارسال ايميل الا شركات.

* **خدمة ايميلات تسويقية:** لارسال اخبار او اعلانات او اي شي ذا علاقة بالتسويق واشهر هذه الخدمات هو mailchimp

* **خدمة الايميلات الاجرائية:** هذه الخدمة غالبا ما تختص في ارسال ايميلات لليوزر بناء على العمل  الذي قام به سواء كان سجل حساب جديد او طلب تغير كلمة السر وغيرها امثلة على هذه الخدمات (mailgun, SendGrid).

## كيفية استعمال SendGrid 

1. قم بتسجيل حساب جديد من [هنا](https://signup.sendgrid.com).
   
2. ربط sendgrid مع جانقو عبر وضع هذه الاعدادات في ملف `prod_settings.py`.

```
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
SENDGRID_API_KEY = os.getenv('SENDGRID_API_KEY')
DEFAULT_FROM_EMAIL = os.getenv('DEFAULT_FROM_EMAIL ')
EMAIL_HOST = 'smtp.sendgrid.net'
EMAIL_HOST_USER = 'apikey' # this is exactly the value 'apikey'
EMAIL_HOST_PASSWORD = SENDGRID_API_KEY
EMAIL_PORT = 587
EMAIL_USE_TLS = True
```

3. انشاء Api key من send grid عبر الدخول على حساب > Create Api Key < Api Keys < settings  > نعطيه اي اسم مع كل الصلاحيات > Create & View.

4. ننسخ ال api key ونضعه على هيروكوفي Config vars.

5. التحقق من هوية المرسل على sendgrid 

    Settings > Sender Authentication > Single Sender Verification > Get Started under Verify an Address > Create New Sender > Fill all the fields then click Create

    ثم ادخل على الايميل الذي وضعته ستجد ان sendgrid ارسلو رسالة للتأكيد قم بعمل Verify. 

6. قم باضافة DEFAULT_FROM_EMAIL الى Config vars على هيروكو.

## ملحق

* [What is HTTP?](https://www.cloudflare.com/learning/ddos/glossary/hypertext-transfer-protocol-http/)

* [What Is an SMTP Server?](https://sendgrid.com/blog/what-is-an-smtp-server/)

* [Marketing Email vs. Transactional Email: What’s the Difference?](https://sendgrid.com/blog/marketing-email-vs-transactional-email-whats-difference/)

