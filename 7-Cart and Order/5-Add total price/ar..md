# السعر اللإجمالي للمنتجات
في هذا الدرس سنتعلم كيفية حساب السعر الاجمالي للمنتجات التي بالعربة.

**اضافة دالة بالمودل**

جانقو تمكننا من عمل دوال في المودل تمكنن من عمل وظيفة معينة. في حالتنا قمنا بعمل دالة `total_price()` تقوم بحساب الملبغ النهائي للمنتجات التي بالعربة. كل ماعلينا فعله هو كتابتها بهذا الشكل

```
class Cart(models.Model):
    ...

    def total_price(self):
        total = 0
        for item in self.items.all():
            total += item.price
        return total
```

## الملحق

* [Django model methods](https://docs.djangoproject.com/en/3.0/topics/db/models/#model-methods)
* [Aggregation](https://docs.djangoproject.com/en/3.0/topics/db/aggregation/)