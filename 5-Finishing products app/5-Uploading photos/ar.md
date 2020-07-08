# رفع صور المنتجات
قبل ان نبدأ في اضافة حقل بصور المنتجات يجب علينا اضافة متغيرات مهمة عشان نقدر نرفع صور في المشروع.

 **هذه هيا المتغيرات التي سنضيفها:**
```
MEDIA_URL = '/media/' # يعني رابط الوسائط على الموقع
MEDIA_ROOT = os.path.join(BASE_DIR, 'media') # يعني مسار مجلد الوسائط على السيرفر
```
**الان يمكننا ان نكمل رفع الصور**

نضيف حقل الصورة باستعمال نوع جديد وهو `ImageField` ونمرر له المسار الذي نريد ان يتم رفع صور المنتجات به. بهذا الشكل:

```
image = models.ImageField(upload_to='products/', null=True)
```

ولاننسى ان نضيف الحقل `image`  للقائمة `fields` في الفورم.

**تعديل ال view و ال template**:

* في ال view يحب ان نقوم باضافة `request.Files` لل `AddProductForm` هذه القائمة ستجلب لنا الملفات التي موجودة في الطلب

* في ال `product-add.html` يجب علينا اضافة الخاصية `enctype="multipart/form-data"` لل تاق `form` اذا لم نضفها سيكون محتوى `request.Files`  فارغ دائما.
و لكي نظهر صورة المنتج في صفحة المنتجات نقوم بجلبها بهذا الشكل

```
<img src="{{product.image.url}}" />
```

**تبقى شيء اخير:**

بعد ان قمنا بتجهيز رفع صورة للمنتج تبقى امر اخير علينا فعله لكي تظهر الصور على الموقع المحلي وهوا اضافة هذه الدالة في ملف `store/urls.py`

```
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    # ... the rest of your URLconf goes here ...
] + static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
```
## ملحق

[File Uploads](https://docs.djangoproject.com/en/3.0/topics/http/file-uploads/)
[Managing static files (e.g. images, JavaScript, CSS)](https://docs.djangoproject.com/en/3.0/howto/static-files/)
