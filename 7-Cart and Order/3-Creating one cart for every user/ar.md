# إنشاء عربة لكل مستخدم
في هذا الدرس تعلمنا كيفية انشاء عربة تلقائيا عند انشاء المستخدم عبر استعمال الاشارات.

**ماهي الاشارات في جانقو؟**

جانقو لديها ميزة مفيدة جدا وهي الاشارات. هناك عدة اشارات مبنية في جانقو والتي نحتاجها في هذا الدرس هي `post_save` وهذه الاشارة تجعلك تقوم بعمل وظيفة معينة بعد عمل حفظ للمرسل المرتبط بها. ويتم اضافة هذه الاشارات بجانب المودل.

**انشاء عربة تلقائيا**

دعنا نبدأ بعمل استراد للدوال التي نحتاجها لعمل اشارة `post_save`

```
from django.db.models.signals import post_save
from django.dispatch import receiver

from django.contrib.authimport get_user_model

User = get_user_model()


@receiver(post_save, sender=User)
def create_user_cart(sender, instance, created **kwargs):
    if created:
        Cart.objects.create(user=instance)
```

## الملحق

* [Django Documentation | Signals](https://docs.djangoproject.com/en/3.0/topics/signals/)

* [ Django Documentation |  built-in signals ](https://docs.djangoproject.com/en/3.0/ref/signals/)

* [Medium | Django : Signals](https://medium.com/@ksarthak4ever/django-signals-b20a4152a27b)