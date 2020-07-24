# متغيرات البيئة في PythonAnywhere

في هذاالدرس سنتعلم كيفية عمل متغيرات البيئة على pythonanywhere

## عمل ملف `.env`:

سنقوم بعمل عدة اوامر تقوم بنقل المتغير على ملف `.env`

1. ادخل على pythonanywhere bash ثم ادخل على مجلد المشروع

```
cd store-repo-name
```

2. انسخ  وثم الصق هذه الاومر على ال bash

**بعض هذه المتغيرات عليك بتغير قيمها بالموجودة عندك في هيروكو الا SECRET_KEY ولد مفتاح جديد**
```
echo "DJANGO_SETTINGS_MODULE='store.prod_settings'" >> .env
echo "SECRET_KEY='123456'" >> .env
echo "SENDGRID_API_KEY='SG.AAA-BBB.CCC'" >> .env
echo "DEFUALT_FORM_EMAIL='example@example.com'" >> .env
echo "DEBUG='false'" >> .env
```
3. قم بتنفيذ هذه الاوامر على الbash مع تعديل مسار المشروع ومسار البيئة الوهمية

```bash
set -a; source ~/my-project-dir/.env; set +a

echo 'set -a; source ~/my-project-dir/.env; set +a' >> ~/.virtualenvs/my-project-virtualenv/bin/postactivate
```
4. قم باضافة اوامر تحميل متغيرات البيئة على ملف wsgi الخاص ب pythonanywhere

```

import os
import sys
from dotenv import load_dotenv


# لاتنسى تغير <username> باسم المستخدم الخاص بك 
# و تغير <store-repo> الى اسم مستودع المتجر
path = '/home/<username>/<store-repo>'

if path not in sys.path:
    sys.path.append(path)

load_dotenv(os.path.join(project_folder, '.env'))

from django.core.wsgi import get_wsgi_application
application = get_wsgi_application()
```

5. قم بتنصيب python-dotenv على السيرفر ولا تنسى باضافتها على ال `rquirements.txt` 


## ملحق 

* [How to set environment variables for your web apps (for SECRET_KEY etc)](https://help.pythonanywhere.com/pages/environment-variables-for-web-apps/)

