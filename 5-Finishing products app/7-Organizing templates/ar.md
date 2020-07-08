# تنظيم القوالب

سابقنا كنا نكرر اكواد ال html في كل الصفحات. لحسن الحظ جانقو لديها ميزة جميلة للقوالب وهي **الوراثة**.

ببساطة هذه الميزة تمكننا من عمل ملف `html` يكون هو الاب وبه كل العناصر المتكررة وعمل ملف يرث من الاب هذه العناصر

**مثال**

**base.html**
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{% block title %} Base {% endblock %}</title>
</head>
<body>
{% block content %} {% endblock %}
</body>
</html>
```
**child.html**
```
{% extends 'base.html' %}

{% block title %}Child {% endblock %}

{% block content%}

This is the Content of the child template

{% endblock %}
```

## ملحق
[The Django template language](https://docs.djangoproject.com/en/3.0/ref/templates/language/)
