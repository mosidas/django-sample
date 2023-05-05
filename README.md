# django-sample

## init setting

```bash
python3 -m venv venv
source venv/bin/activate
python -m pip install --upgrade pip
pip install Django
jango-admin startproject mysite .
python manage.py migrate
```

```python:settings.py
ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com']
:
LANGUAGE_CODE = 'ja'
:
TIME_ZONE = 'Asia/Tokyo'
```

```bash
python manage.py migrate
```

## clone and setup

```bash
git clone {this repository}
cd {this repository}
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```
