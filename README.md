

``` bash
python -m venv venv

```

```txt
django
python-dotenv
gunicorn
psycopg2
```
``` bash
pip install -r requirements.txt

```
creamos el proyecto "main" en la raiz del repo

``` bash
django-admin startproject main .

```


creamos la app venta

``` bash
django-admin startapp venta
```

instalan la aplicacion de "main/settings.py"

```py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'venta'
]

```

```py
from dotenv import load_dotenv
import os

# Load environment variables from .env
load_dotenv()
```


```py

DATABASES = {
    "default": {
        "ENGINE": "django.db.backends.postgresql",
        "NAME": os.getenv("dbname"),
        "USER": os.getenv("user"),
        "PASSWORD": os.getenv("password"),
        "HOST": os.getenv("host"),
        "PORT": os.getenv("port"),
    }
}
```

```env
user=USER
password=PASSWORD
host=HOST
port=PORT
dbname=NAME
```

