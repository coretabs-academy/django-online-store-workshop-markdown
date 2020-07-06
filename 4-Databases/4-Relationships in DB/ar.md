# العلاقات في قواعد البيانات

## أنواع العلاقات:

1. واحد لواحد (One to One).
2. واحد لمتعدد (One to many / Many to One).
3. متعدد لمتعدد (Many to Many).

# أنواع المفاتيح:

* **مفتاح رئيسي (Primary Key)**
وهو حقل يجب ان يكون موجود في اي جدول ويجب ان لا تتكرر قيمته اكثر من مرة.

* **مفتاح أجنبي (Foreign Key)**
وهو حقل يشير الى جدول أخر.

# كيف يتم ربط العلاقات؟

* **علاقة واحد لواحد:**
نضيف مفتاح اجنبي في الجدول الأول ومفتاح أجنبي في الجدول الثاني.

* **علاقة واحد لمتعدد:**
نضيف مقتاح اجنبي في جهة المتعدد.

* **علاقة متعدد لمتعدد:**
تتم باضافة جدول وسيط يحتوي على id و مفتاح اجنبي يشير للجدول الأول و مفتاح اجنبي يشيرللجدول الثاني.

## ملحق

[Everything you need to know about (Relational) Databases](https://dev.to/lmolivera/everything-you-need-to-know-about-relational-databases-3ejl#:~:text=What%20is%20a%20Relational%20Database%3F&text=It%20uses%20a%20structure%20that,database%20is%20organized%20into%20tables.)

[The 3 Types of Relationships in Database Design](https://database.guide/the-3-types-of-relationships-in-database-design/)

[A beginner’s guide to database table relationships](https://vladmihalcea.com/database-table-relationships/)