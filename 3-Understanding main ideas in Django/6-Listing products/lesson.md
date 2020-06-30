بالنسبة للحلقة loop داخل product list template


```
    {% for product in products %}
    <ul>
      <li>
        <img src="{{product.image.url}}" />
        <div>{{product.brand}}</div>
        <a href="{{ product.get_absolute_url }}">
          <h2>{{product.title}}</h2>
        </a>
        <div>{{product.price}}</div>
      </li>
    </ul>
    {% endfor %}
```

يوجد خطأ فيها، هل لاحظته؟

يجب أن تكتب بهذا الشكل:

```
    <ul>
    {% for product in products %}
      <li>
        <img src="{{product.image.url}}" />
        <div>{{product.brand}}</div>
        <a href="{{ product.get_absolute_url }}">
          <h2>{{product.title}}</h2>
        </a>
        <div>{{product.price}}</div>
      </li>
    {% endfor %}
    </ul>
```

السبب أن القائمة يجب أن يتم انشائها مرة واحدة فقط وداخلها يتم انشاء العناصر.