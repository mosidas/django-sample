# django-sample

## start

### init

```bash
python3 -m venv venv
source venv/bin/activate
python -m pip install --upgrade pip
pip install Django
jango-admin startproject mysite .
python manage.py migrate
```

- mysite/settings.py

```python:settings.py
ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com']
:
LANGUAGE_CODE = 'ja'
:
TIME_ZONE = 'Asia/Tokyo'
```

```bash
python manage.py migrate
python manage.py runserver
```

### create app

```bash
python manage.py startapp blog
python manage.py makemigrations blog
```
- mysite/settings.py

```python:settings.py
INSTALLED_APPS = [
    :
    'blog.apps.BlogConfig',
]
```
- blog/models.py

```python:models.py
from django.conf import settings
from django.db import models
from django.utils import timezone

class Post(models.Model):
    author = models.ForeignKey(settings.AUTH_USER_MODEL, on_delete=models.CASCADE)
    title = models.CharField(max_length=200)
    text = models.TextField()
    created_date = models.DateTimeField(default=timezone.now)
    published_date = models.DateTimeField(blank=True, null=True)

    def publish(self):
        self.published_date = timezone.now()
        self.save()

    def __str__(self):
        return self.title
```

```bash
python manage.py makemigrations blog
python manage.py migrate blog
```

- blog/admin.py

```python:admin.py
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```

### create superuser

```bash
python manage.py createsuperuser
ユーザー名: test
メールアドレス: test@example.com
Password: 
Password (again): 
```

## clone and setup

```bash
git clone {this repository}
cd {this repository}
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

## start

```bash
python manage.py runserver
```

