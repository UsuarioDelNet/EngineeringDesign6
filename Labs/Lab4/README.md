# Engineering Design VI `CPE 322-A`
## Lab 4 — Django and Flask
---

- [`pip installs`](#1)
- [`Creating "stevens"`](#2)
- [`Creating "myCPU"`](#3)
- [`Running Flask`](#4)

To go to the postscript, click [`HERE`](#100)

---
<h3 id="1">pip installs</h3>

```
pip install django
pip install djangorestframework
pip install setuptools
pip install django-filter
pip install markdown
pip install requests
pip install flask
```

<h3 id="2">Creating Django project "stevens"</h3>

```
C:\Users\mrdan\iot>django-admin startproject stevens

C:\Users\mrdan\iot>cd stevens

C:\Users\mrdan\iot\stevens>ls
manage.py  stevens
```

```
C:\Users\mrdan\iot\stevens>python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, sessions
Running migrations:
  Applying contenttypes.0001_initial... OK
  Applying auth.0001_initial... OK
  Applying admin.0001_initial... OK
  Applying admin.0002_logentry_remove_auto_add... OK
  Applying admin.0003_logentry_add_action_flag_choices... OK
  Applying contenttypes.0002_remove_content_type_name... OK
  Applying auth.0002_alter_permission_name_max_length... OK
  Applying auth.0003_alter_user_email_max_length... OK
  Applying auth.0004_alter_user_username_opts... OK
  Applying auth.0005_alter_user_last_login_null... OK
  Applying auth.0006_require_contenttypes_0002... OK
  Applying auth.0007_alter_validators_add_error_messages... OK
  Applying auth.0008_alter_user_username_max_length... OK
  Applying auth.0009_alter_user_last_name_max_length... OK
  Applying auth.0010_alter_group_name_max_length... OK
  Applying auth.0011_update_proxy_permissions... OK
  Applying auth.0012_alter_user_first_name_max_length... OK
  Applying sessions.0001_initial... OK
```
```
C:\Users\mrdan\iot\stevens>python manage.py startapp myapp

C:\Users\mrdan\iot\stevens>ls
manage.py  myapp  stevens
```

```
C:\Users\mrdan\iot\stevens>cd stevens

C:\Users\mrdan\iot\stevens\stevens>nano settings.py
```
```
ALLOWED_HOSTS = ['*']


# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'myapp',
]
```
```
C:\Users\mrdan\iot\stevens\stevens> cp C:\Users\mrdan\iot\lesson4\stevens\urls.py C:\Users\mrdan\iot\stevens\stevens\

C:\Users\mrdan\iot\stevens\stevens>ls
__init__.py  __pycache__  asgi.py  settings.py  urls.py  wsgi.py
```
```
C:\Users\mrdan\iot\stevens\stevens> cp C:\Users\mrdan\iot\lesson4\stevens\admin.py C:\Users\mrdan\iot\stevens\myapp\

C:\Users\mrdan\iot\stevens\stevens> cp C:\Users\mrdan\iot\lesson4\stevens\models.py C:\Users\mrdan\iot\stevens\myapp\

C:\Users\mrdan\iot\stevens\stevens> cp C:\Users\mrdan\iot\lesson4\stevens\views.py C:\Users\mrdan\iot\stevens\myapp\

C:\Users\mrdan\iot\stevens\stevens>cd..

C:\Users\mrdan\iot\stevens>cd myapp

C:\Users\mrdan\iot\stevens\myapp>ls
__init__.py  admin.py  apps.py  migrations  models.py  tests.py  views.py
```
```
C:\Users\mrdan\iot\stevens\myapp>mkdir static templates

C:\Users\mrdan\iot\stevens\myapp>cd templates

C:\Users\mrdan\iot\stevens\myapp\templates>mkdir myapp

C:\Users\mrdan\iot\stevens\myapp\templates> cp C:\Users\mrdan\iot\lesson4\stevens\index.html C:\Users\mrdan\iot\stevens\myapp\templates\myapp

C:\Users\mrdan\iot\stevens\myapp\templates>cd myapp

C:\Users\mrdan\iot\stevens\myapp\templates\myapp>ls
index.html
```
```
PS C:\Users\mrdan\iot\stevens\myapp\templates\myapp> nano index.html
```
```
PS C:\Users\mrdan\iot\stevens\myapp\static> cp C:\Users\mrdan\iot\lesson4\static\favicon.ico
PS C:\Users\mrdan\iot\stevens\myapp\static> ls


    Directory: C:\Users\mrdan\iot\stevens\myapp\static


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         4/28/2025   2:26 AM          15406 favicon.ico

```
```
PS C:\Users\mrdan\iot\stevens\myapp\static\myapp> cp C:\Users\mrdan\iot\lesson4\static\*css .
PS C:\Users\mrdan\iot\stevens\myapp\static\myapp> cp C:\Users\mrdan\iot\lesson4\static\*js .
PS C:\Users\mrdan\iot\stevens\myapp\static\myapp> ls


    Directory: C:\Users\mrdan\iot\stevens\myapp\static\myapp


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         4/28/2025   2:26 AM         232920 bootstrap.min.css
-a----         4/28/2025   2:26 AM          60356 bootstrap.min.js
-a----         4/28/2025   2:26 AM          87464 jquery.min.js
-a----         4/28/2025   2:26 AM           3414 script.js

```
```
PS C:\Users\mrdan\iot\stevens> python manage.py makemigrations myapp
Migrations for 'myapp':
  myapp\migrations\0001_initial.py
    + Create model TemperatureData
PS C:\Users\mrdan\iot\stevens> python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, myapp, sessions
Running migrations:
  Applying myapp.0001_initial... OK
PS C:\Users\mrdan\iot\stevens> python manage.py createsuperuser
Username (leave blank to use 'mrdan'):
Email address: mrdan600@gmail.com
Password:
Password (again):
Password:
Password (again):
Superuser created successfully.
```
```
PS C:\Users\mrdan\iot\stevens> python manage.py runserver
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).
April 30, 2025 - 02:15:18
Django version 5.2, using settings 'stevens.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.
```
![AdminTemp](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab4/SourcesLab4/djangoadmintemp.png)
![MyApp](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab4/SourcesLab4/myappfunctions.png)



<h3 id="3">Creating Django Rest project "myCPU"</h3>

```
PS C:\Users\mrdan> cd iot
PS C:\Users\mrdan\iot> django-admin startproject mycpu
PS C:\Users\mrdan\iot> cd mycpu
PS C:\Users\mrdan\iot\mycpu> ls


    Directory: C:\Users\mrdan\iot\mycpu


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         4/30/2025   2:30 AM                mycpu
-a----         4/30/2025   2:30 AM            683 manage.py

```
```
PS C:\Users\mrdan\iot\mycpu> python manage.py startapp myapp
PS C:\Users\mrdan\iot\mycpu> ls


    Directory: C:\Users\mrdan\iot\mycpu


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         4/30/2025   2:31 AM                myapp
d-----         4/30/2025   2:31 AM                mycpu
-a----         4/30/2025   2:30 AM            683 manage.py
```
```
PS C:\Users\mrdan\iot\mycpu\mycpu> nano settings.py
```
```
ALLOWED_HOSTS = ['*']


# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'myapp',
    'rest_framework',
]
```
```
PS C:\Users\mrdan\iot\mycpu\mycpu> cp C:/Users/mrdan/iot/lesson4/mycpu/urls.py
PS C:\Users\mrdan\iot\mycpu\mycpu> ls


    Directory: C:\Users\mrdan\iot\mycpu\mycpu


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         4/30/2025   2:31 AM                __pycache__
-a----         4/30/2025   2:30 AM            403 asgi.py
-a----         4/30/2025   2:35 AM           3318 settings.py
-a----         4/28/2025   2:26 AM           1505 urls.py
-a----         4/30/2025   2:30 AM            403 wsgi.py
-a----         4/30/2025   2:30 AM              0 __init__.py
```
```
PS C:\Users\mrdan\iot\mycpu\myapp> cp C:/Users/mrdan/iot/lesson4/mycpu/admin.py
PS C:\Users\mrdan\iot\mycpu\myapp> cp C:/Users/mrdan/iot/lesson4/mycpu/models.py
PS C:\Users\mrdan\iot\mycpu\myapp> cp C:/Users/mrdan/iot/lesson4/mycpu/views.py
PS C:\Users\mrdan\iot\mycpu\myapp> cp C:/Users/mrdan/iot/lesson4/mycpu/serializers.py
PS C:\Users\mrdan\iot\mycpu\myapp> ls


    Directory: C:\Users\mrdan\iot\mycpu\myapp


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         4/30/2025   2:31 AM                migrations
-a----         4/28/2025   2:26 AM            140 admin.py
-a----         4/30/2025   2:31 AM            148 apps.py
-a----         4/28/2025   2:26 AM            509 models.py
-a----         4/28/2025   2:26 AM            485 serializers.py
-a----         4/30/2025   2:31 AM             63 tests.py
-a----         4/28/2025   2:26 AM           1483 views.py
-a----         4/30/2025   2:31 AM              0 __init__.py
```
```
PS C:\Users\mrdan\iot\mycpu\myapp> nano views.py
```
```
PS C:\Users\mrdan\iot\mycpu> python manage.py makemigrations myapp
Migrations for 'myapp':
  myapp\migrations\0001_initial.py
    + Create model Cpu
    + Create model Dt
    + Create model LocationData
    + Create model Mem
PS C:\Users\mrdan\iot\mycpu> python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, myapp, sessions
Running migrations:
  Applying contenttypes.0001_initial... OK
  Applying auth.0001_initial... OK
  Applying admin.0001_initial... OK
  Applying admin.0002_logentry_remove_auto_add... OK
  Applying admin.0003_logentry_add_action_flag_choices... OK
  Applying contenttypes.0002_remove_content_type_name... OK
  Applying auth.0002_alter_permission_name_max_length... OK
  Applying auth.0003_alter_user_email_max_length... OK
  Applying auth.0004_alter_user_username_opts... OK
  Applying auth.0005_alter_user_last_login_null... OK
  Applying auth.0006_require_contenttypes_0002... OK
  Applying auth.0007_alter_validators_add_error_messages... OK
  Applying auth.0008_alter_user_username_max_length... OK
  Applying auth.0009_alter_user_last_name_max_length... OK
  Applying auth.0010_alter_group_name_max_length... OK
  Applying auth.0011_update_proxy_permissions... OK
  Applying auth.0012_alter_user_first_name_max_length... OK
  Applying myapp.0001_initial... OK
  Applying sessions.0001_initial... OK
```
```
PS C:\Users\mrdan\iot\mycpu\myapp> mkdir static


    Directory: C:\Users\mrdan\iot\mycpu\myapp


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         4/30/2025   2:44 AM                static


PS C:\Users\mrdan\iot\mycpu\myapp> mkdir templates


    Directory: C:\Users\mrdan\iot\mycpu\myapp


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         4/30/2025   2:44 AM                templates


PS C:\Users\mrdan\iot\mycpu\myapp> ls


    Directory: C:\Users\mrdan\iot\mycpu\myapp


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         4/30/2025   2:43 AM                migrations
d-----         4/30/2025   2:44 AM                static
d-----         4/30/2025   2:44 AM                templates
d-----         4/30/2025   2:43 AM                __pycache__
-a----         4/28/2025   2:26 AM            140 admin.py
-a----         4/30/2025   2:31 AM            148 apps.py
-a----         4/28/2025   2:26 AM            509 models.py
-a----         4/28/2025   2:26 AM            485 serializers.py
-a----         4/30/2025   2:31 AM             63 tests.py
-a----         4/30/2025   2:41 AM           1488 views.py
-a----         4/30/2025   2:31 AM              0 __init__.py
```
```
PS C:\Users\mrdan\iot\mycpu\myapp> cd templates
PS C:\Users\mrdan\iot\mycpu\myapp\templates> mkdir myapp


    Directory: C:\Users\mrdan\iot\mycpu\myapp\templates


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         4/30/2025   2:45 AM                myapp


PS C:\Users\mrdan\iot\mycpu\myapp\templates> cd myapp
PS C:\Users\mrdan\iot\mycpu\myapp\templates\myapp> cp C:/Users/mrdan/iot/lesson4/mycpu/index.html
PS C:\Users\mrdan\iot\mycpu\myapp\templates\myapp> ls


    Directory: C:\Users\mrdan\iot\mycpu\myapp\templates\myapp


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         4/28/2025   2:26 AM           1706 index.html
```
```
PS C:\Users\mrdan\iot\mycpu\myapp\templates\myapp> nano index.html
```
```
PS C:\Users\mrdan\iot\mycpu\myapp> cd static
PS C:\Users\mrdan\iot\mycpu\myapp\static> cp C:/Users/mrdan/iot/lesson4/static/favicon.ico
PS C:\Users\mrdan\iot\mycpu\myapp\static> mkdir myapp


    Directory: C:\Users\mrdan\iot\mycpu\myapp\static


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         4/30/2025   2:48 AM                myapp


PS C:\Users\mrdan\iot\mycpu\myapp\static> cd myapp
PS C:\Users\mrdan\iot\mycpu\myapp\static\myapp> cp C:/Users/mrdan/iot/lesson4/static/*css .
PS C:\Users\mrdan\iot\mycpu\myapp\static\myapp> cp C:/Users/mrdan/iot/lesson4/static/*js .
PS C:\Users\mrdan\iot\mycpu\myapp\static\myapp> ls


    Directory: C:\Users\mrdan\iot\mycpu\myapp\static\myapp


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         4/28/2025   2:26 AM         232920 bootstrap.min.css
-a----         4/28/2025   2:26 AM          60356 bootstrap.min.js
-a----         4/28/2025   2:26 AM          87464 jquery.min.js
-a----         4/28/2025   2:26 AM           3414 script.js
```
```
PS C:\Users\mrdan\iot\mycpu> cp C:/Users/mrdan/iot/lesson4/mycpu/controller.py
PS C:\Users\mrdan\iot\mycpu> ls


    Directory: C:\Users\mrdan\iot\mycpu


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         4/30/2025   2:44 AM                myapp
d-----         4/30/2025   2:31 AM                mycpu
-a----         4/28/2025   2:26 AM           1112 controller.py
-a----         4/30/2025   2:43 AM         147456 db.sqlite3
-a----         4/30/2025   2:30 AM            683 manage.py
```
```
PS C:\Users\mrdan\iot\mycpu> nano controller.py
```
```
PS C:\Users\mrdan\iot\mycpu> python manage.py createsuperuser
Username (leave blank to use 'mrdan'): admin
Email address: mrdan600@gmail.com
Password:
Password (again):
Superuser created successfully.
```
```
PS C:\Users\mrdan\iot\mycpu> python controller.py
2025-04-30 03:23:55
CPU Usage:        0.0%
Memory Available: 15.3 GB
2025-04-30 03:24:10
CPU Usage:        3.6%
Memory Available: 15.2 GB
2025-04-30 03:24:24
CPU Usage:        3.1%
Memory Available: 15.3 GB
```
![DTLIST](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab4/SourcesLab4/DTLIST.png)
![CPULIST](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab4/SourcesLab4/CPULIST.png)
![MEMLIST](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab4/SourcesLab4/MEMLIST.png)
![AdminLocation](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab4/SourcesLab4/djangoadminlocation.png)
![MyCPU](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab4/SourcesLab4/mycpufunctions.png)

<h3 id="4">Creating Flask project</h3>

```
C:\Users\mrdan>cd iot

C:\Users\mrdan\iot>cd lesson4

C:\Users\mrdan\iot\lesson4>python hello_world.py
 * Serving Flask app 'hello_world'
 * Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on http://127.0.0.1:5000
```
![Hallo Worl](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab4/SourcesLab4/helloworldpy.png)


---
<h4 id="100">Postscript</h4>

- All my source files and instructions were initially obtained in [`Dr. Lu's GitHub`](https://github.com/kevinwlu/iot/tree/master/lesson4)
- Please note, I replaced all the instances of "python3" with "python" in the commands for the lab, as I had Python downloaded on my system already.
- I pledge my honor that I have abided by the Stevens Honor System: Daniel A. Liss
