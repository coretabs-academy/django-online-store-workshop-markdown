# بناء عربة التسوق

كما تم التوضيح في الدرس كل مستخدم سيكون عنده عربة واحدة ويتم اضافة المنتجات بها

# مودل العربة

سيحتوي مودل العربة على ثلاثة حقول:

* المستخدم: وهذا الحقل عبارة عن علاقة واحد الى واحد مع المستخدم اي ان كل مستخدم لديه عربة واحدة 
* العناصر: وهذا الحقل هو علاقة متعدد الى متعدد مع المنتجات اي ان العربة يمكن ان يكون فيها اكثر من منتج و المنتج ممكن ان يكون في اكثر من عربة.
* وقت التحديث: يتم تحديث هذا الحقل بالوقت الحالي في كل مرة نقوم بتعديل العربة.

## ملحق

* [Django Documentations | One-to-one relationships](https://docs.djangoproject.com/en/3.0/topics/db/examples/one_to_one/)

* [Django Documentations | Many-to-many relationships](https://docs.djangoproject.com/en/3.0/topics/db/examples/many_to_many/)