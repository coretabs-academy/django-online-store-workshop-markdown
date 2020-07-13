# حماية الصفحات

في هذا الدرس تعلمنا كيف نقوم بحماية الصفحات وجعلهم خاصة باليوزر الذي سجل دخوله

**لماذا نحمي الصفحات**
غالبا عند عمل موقع بيكون عندنا بعض الصفحات التي لازم تكون خاصة مثل صفحة اضافة المنتجات وتعديل المنتجات لا يمكن ان نجعلهم عامة والا اي  شخص يزور الموقع عنده امكانية اضافة منتج جديد وتعديل المنتجات السابقة وهذا الامر خطير جدا وغير مقبول.

**كيف نحمي الصفحات**
جانقو كالعادة مفكرة بالأمر وعندها اداة بتساعدنا على حماية الصفحات وهي `login_required` وهذه الدالة تقوم بالتحقق من اذا اليوزر مسجل دخوله يمكنه الدخول على الصفحة واذا لم يكن مسجل دخوله سيتم توجيهه الى صفحة تسجيل الدخول.

يتم استعمالها بهذه الطريقة 

```python
from django.contrib.auth.decorators import login_required


@login_required
def my_view(request):
    ...
```

## ملحق

[The `login_required` decorator](https://docs.djangoproject.com/en/3.0/topics/auth/default/#the-login-required-decorator)

[Python Decorators](https://www.programiz.com/python-programming/decorator)

[Primer on Python Decorators](https://realpython.com/primer-on-python-decorators/)