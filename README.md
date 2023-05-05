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
```
- mysite/settings.py

```python:settings.py
INSTALLED_APPS = [
    :
    'blog.apps.BlogConfig',
]
```

## clone and setup

```bash
git clone {this repository}
cd {this repository}
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```
