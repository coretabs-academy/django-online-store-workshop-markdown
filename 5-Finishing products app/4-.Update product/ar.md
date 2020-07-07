# كيف أضيف المنتج الى الاستمارة أو Form؟

نجلب المنتج من قاعدة البيانات و نمرره في الخانة instance كالتالي

form = AddProductForm(instance=product)



# ماهي فائدة get_object_or_404؟

استعملنا هاذه الدالة لجلب المنتج من قاعدة البيانات و لكن في حالة عدم وجود أي منتج نرجع 404 مباشرة من ال view أي أن الصفحة المطلوبة غير موجودة

product = get_object_or_404(Product, pk=pk)



# الملحق

[Creating forms from models](https://docs.djangoproject.com/en/3.0/topics/forms/modelforms/)
[get_object_or_404 documentation](https://docs.djangoproject.com/en/3.0/topics/http/shortcuts/#get-object-or-404)