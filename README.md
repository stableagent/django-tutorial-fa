# آموزش کامل Django به فارسی

این رپوزیتوری یک آموزش گام‌به‌گام و کامل فریم‌ورک Django است که هر روز یک مبحث جدید به آن اضافه می‌شود.

**نسخه هدف:** Django 5.x  
**پیاده:** Python 3.12+

---

## فهرست مطالب

| روز | مبحث |
|------|------|
| ۱ | مقدمه، نصب و ایجاد پروژه |
| ۲ | اپلیکیشن، model و migration |
| ۳ | Django Admin |
| ۴ | view، URL و توابع |
| ۵ | template و static files |
| ۶ | form و validation |
| ۷ | احراز هویت (کاربر، session، login) |
| ۸ | class-based views و generic views |
| ۹ | REST API با Django REST framework (مقدمه) |
| ۱۰ | آزمون، بهینه‌سازی و deploy |

---

## فصل ۱ — مقدمه، نصب و ایجاد پروژه

### Django چیست؟

Django یک **web framework** مجانی و بالا-سطح (high-level) برای Python است که اصول «توسعه سریع و تمیز» را دنبال می‌کند. الگوی MTV (مشابه MVC) را پیروی می‌کند:

- **Model**: ساختار داده و منطق با پایگاه داده
- **Template**: نمایش (طراحی HTML)
- **View**: منطق بین model و template (منطق کسب‌وکار)

### پیش‌نیازها

- Python 3.10 یا بالاتر
- pip و venv
- یک ویرایشگر متن (توصیه: VS Code یا PyCharm)

### ایجاد محیط مجازی

```bash
python3 -m venv .venv
source .venv/bin/activate   # در Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install "django>=5.1,<5.3"
```

بررسی نصب:

```bash
python -m django --version
```

### ایجاد پروژه

```bash
django-admin startproject mysite
cd mysite
```

ساختار اولیه:

```
mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py
```

### اجرای سرور توسعه

```bash
python manage.py runserver
```

آدرس پیش‌فرض: `http://127.0.0.1:8000/`

اگر صفحهٔ موفقیت Django را دیدید، نصب درست انجام شده است.

### نگاه مهم در مورد settings.py

- `DEBUG = True` فقط برای توسعه محلی
- `ALLOWED_HOSTS` برای محیط production باید پر شود
- `INSTALLED_APPS` فهرست اپ‌های فعال
- `TIME_ZONE` را می‌توانید به `Asia/Tehran` تغییر دهید

```python
LANGUAGE_CODE = "fa"
TIME_ZONE = "Asia/Tehran"
USE_I18N = True
USE_TZ = True
```

### تمرین اول فصل

1. محیط مجازی بسازید و Django را نصب کنید.
2. یک پروژه با `startproject` بسازید.
3. `runserver` را اجرا کنید و صفحهٔ خوش‌آمد را ببینید.
4. `TIME_ZONE` و `LANGUAGE_CODE` را تنظیم کنید.

---

*فردا فصل ۲ را اضافه خواهیم کرد: ایجاد اپ، model اول و migration.*
