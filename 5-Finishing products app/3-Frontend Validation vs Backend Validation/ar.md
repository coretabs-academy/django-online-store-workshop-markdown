# التحقق من الفرونت اند

تعلمنا في هذا الدرس ان لانثق ابدا بالتحقق في الفرونت اند ويجب علينا ايضا ان نتحقق من البيانات في السيرفر. جانقو كالعادة مفكرة في الموضوع و اعطولنا `forms` 

## ModelForm

تمكننا من انشاء فورم جاهزة ومربتطة مع مودل معين.

## class Meta

حين تجد هذا ال class في اي مكان في جانقو يعني انه اعدادات للكلاس الذي فوقه وفي حالتنا الان `ModelForm`, هنا يمكننا تعريف المودل الذي سيتم ربطه مع الفورم و الحقول التي نريد اضافتها للفورم.

## ModelForm في ال template 

بعد اضافة وسم الفورم و csrf_token يمكننا جلب الفورم عن طريق 

```
{{form.as_p}}
```

لكن لاتنسا تمرير الفورم من ال view

## الدالة `is_valid()`

تقوم بالتحقق من البيانات التي تم جلبها من الطلب اذا كانت صحيحة او لا 

## ملحق
[Best Practices for Hints and Validation in Web Forms](https://www.webfx.com/blog/web-design/best-practices-for-hints-and-validation-in-web-forms/)

[Creating forms from models](https://docs.djangoproject.com/en/3.0/topics/forms/modelforms/#modelform)