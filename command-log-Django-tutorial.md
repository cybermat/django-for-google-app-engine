
..\DjangoStartProject>python --version
Python 3.10.10

..\DjangoStartProject>python -m venv .venv

..\DjangoStartProject>.\.venv\Scripts\activate

(.venv) ..\DjangoStartProject>python -m pip install --upgrade pip
Requirement already satisfied: pip in ..\djangostartproject\.venv\lib\site-packages (22.3.1)
Collecting pip
  Using cached pip-23.1.2-py3-none-any.whl (2.1 MB)
Installing collected packages: pip
  Attempting uninstall: pip
    Found existing installation: pip 22.3.1
    Uninstalling pip-22.3.1:
      Successfully uninstalled pip-22.3.1
Successfully installed pip-23.1.2

(.venv) ..\DjangoStartProject>python -m pip install Django
Collecting Django
  Downloading Django-4.2.1-py3-none-any.whl (8.0 MB)
     ---------------------------------------- 8.0/8.0 MB 2.0 MB/s eta 0:00:00
Collecting asgiref<4,>=3.6.0 (from Django)
  Using cached asgiref-3.6.0-py3-none-any.whl (23 kB)
Collecting sqlparse>=0.3.1 (from Django)
  Using cached sqlparse-0.4.4-py3-none-any.whl (41 kB)
Collecting tzdata (from Django)
  Using cached tzdata-2023.3-py2.py3-none-any.whl (341 kB)
Installing collected packages: tzdata, sqlparse, asgiref, Django
Successfully installed Django-4.2.1 asgiref-3.6.0 sqlparse-0.4.4 tzdata-2023.3

(.venv) ..\DjangoStartProject>python --version
Python 3.10.10

(.venv) ..\DjangoStartProject>python -m django --version
4.2.1

(.venv) ..\DjangoStartProject>django-admin startproject mysite

(.venv) ..\DjangoStartProject>cd mysite

(.venv) ..\DjangoStartProject\mysite>py manage.py runserver
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).

You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
May 06, 2023 - 20:20:29
Django version 4.2.1, using settings 'mysite.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.

[06/May/2023 20:20:49] "GET / HTTP/1.1" 200 10731
[06/May/2023 20:20:49] "GET /static/admin/css/fonts.css HTTP/1.1" 404 1816
[06/May/2023 20:20:50] "GET / HTTP/1.1" 200 10731
[06/May/2023 20:20:50] "GET /static/admin/css/fonts.css HTTP/1.1" 404 1816
Not Found: /favicon.ico
[06/May/2023 20:20:50] "GET /favicon.ico HTTP/1.1" 404 2110

< CTRL-BREAK >

(.venv) ..\DjangoStartProject\mysite>

(.venv) ..\DjangoStartProject\mysite>python manage.py migrate
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

(.venv) ..\DjangoStartProject\mysite>python -m pip list
Package    Version
---------- -------
asgiref    3.6.0
Django     4.2.1
pip        23.1.2
setuptools 65.5.0
sqlparse   0.4.4
tzdata     2023.3

(.venv) ..\DjangoStartProject\mysite>dir

Directory of ..\DjangoStartProject\mysite
..           131,072 db.sqlite3
..                  684 manage.py
..    <DIR>          mysite

(.venv) ..\DjangoStartProject\mysite>python -m pip freeze > requirements.txt

(.venv) ..\DjangoStartProject\mysite>

(.venv) ..\DjangoStartProject\mysite>dir

Directory of ..\DjangoStartProject\mysite
..           131,072 db.sqlite3
..                  684 manage.py
..    <DIR>          mysite
..                                 64 requirements.txt

(.venv) ..\DjangoStartProject\mysite>

(.venv) ..\DjangoStartProject\mysite>cd ..

(.venv) ..\DjangoStartProject>.\.venv\Scripts\deactivate

..\DjangoStartProject>

..\DjangoStartProject>exit

