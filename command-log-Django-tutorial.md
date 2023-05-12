
``..\DjangoStartProject>python --version``<br/>
      Python 3.10.10

``..\DjangoStartProject>python -m venv .venv``

``..\DjangoStartProject>.\.venv\Scripts\activate``

``(.venv) ..\DjangoStartProject>python -m pip install --upgrade pip``<br/>
      Requirement already satisfied: pip in ..\djangostartproject\.venv\lib\site-packages (22.3.1)<br/>
      Collecting pip<br/>
        Using cached pip-23.1.2-py3-none-any.whl (2.1 MB)<br/>
      Installing collected packages: pip<br/>
        Attempting uninstall: pip<br/>
          Found existing installation: pip 22.3.1<br/>
          Uninstalling pip-22.3.1:<br/>
            Successfully uninstalled pip-22.3.1<br/>
      Successfully installed pip-23.1.2<br/>

``(.venv) ..\DjangoStartProject>python -m pip install Django``<br/>
      Collecting Django<br/>
        Downloading Django-4.2.1-py3-none-any.whl (8.0 MB)<br/>
          ---------------------------------------- 8.0/8.0 MB 2.0 MB/s eta 0:00:00<br/>
      Collecting asgiref<4,>=3.6.0 (from Django)<br/>
        Using cached asgiref-3.6.0-py3-none-any.whl (23 kB)<br/>
      Collecting sqlparse>=0.3.1 (from Django)<br/>
        Using cached sqlparse-0.4.4-py3-none-any.whl (41 kB)<br/>
      Collecting tzdata (from Django)<br/>
        Using cached tzdata-2023.3-py2.py3-none-any.whl (341 kB)<br/>
      Installing collected packages: tzdata, sqlparse, asgiref, Django<br/>
      Successfully installed Django-4.2.1 asgiref-3.6.0 sqlparse-0.4.4 tzdata-2023.3<br/>

``(.venv) ..\DjangoStartProject>python --version``<br/>
      Python 3.10.10<br/>

``(.venv) ..\DjangoStartProject>python -m django --version``<br/>
      4.2.1<br/>

``(.venv) ..\DjangoStartProject>django-admin startproject mysite``<br/>

``(.venv) ..\DjangoStartProject>cd mysite``<br/>

``(.venv) ..\DjangoStartProject\mysite>py manage.py runserver``<br/>
<br/>
      Watching for file changes with StatReloader<br/>      
      Performing system checks. <br/>
      System check identified no issues (0 silenced). <br/>
      You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions. <br/> 
      Run 'python manage.py migrate' to apply them. <br/>
      May 06, 2023 - 20:20:29<br/>
      Django version 4.2.1, using settings 'mysite.settings' <br/>
      Starting development server at http://127.0.0.1:8000/ <br/>
      <br/>
      Quit the server with CTRL-BREAK. <br/>
      [06/May/2023 20:20:49] GET / HTTP/1.1 200 10731 <br/>
      [06/May/2023 20:20:49] GET /static/admin/css/fonts.css HTTP/1.1 404 1816 <br/>
      [06/May/2023 20:20:50] GET / HTTP/1.1 200 10731 <br/>
      [06/May/2023 20:20:50] GET /static/admin/css/fonts.css HTTP/1.1 404 1816 <br/>
      Not Found: /favicon.ico <br/>
      [06/May/2023 20:20:50] GET /favicon.ico HTTP/1.1 404 2110 <br/>

 CTRL-BREAK  <br/>

``(.venv) ..\DjangoStartProject\mysite>``<br/>

``(.venv) ..\DjangoStartProject\mysite>python manage.py migrate``<br/>
      Operations to perform:<br/>
        Apply all migrations: admin, auth, contenttypes, sessions<br/>
      Running migrations:<br/>
        Applying contenttypes.0001_initial... OK<br/>
        Applying auth.0001_initial... OK<br/>
        Applying admin.0001_initial... OK<br/>
        Applying admin.0002_logentry_remove_auto_add... OK<br/>
        Applying admin.0003_logentry_add_action_flag_choices... OK<br/>
        Applying contenttypes.0002_remove_content_type_name... OK<br/>
        Applying auth.0002_alter_permission_name_max_length... OK<br/>
        Applying auth.0003_alter_user_email_max_length... OK<br/>
        Applying auth.0004_alter_user_username_opts... OK<br/>
        Applying auth.0005_alter_user_last_login_null... OK<br/>
        Applying auth.0006_require_contenttypes_0002... OK<br/>
        Applying auth.0007_alter_validators_add_error_messages... OK<br/>
        Applying auth.0008_alter_user_username_max_length... OK<br/>
        Applying auth.0009_alter_user_last_name_max_length... OK<br/>
        Applying auth.0010_alter_group_name_max_length... OK<br/>
        Applying auth.0011_update_proxy_permissions... OK<br/>
        Applying auth.0012_alter_user_first_name_max_length... OK<br/>
        Applying sessions.0001_initial... OK<br/>

``(.venv) ..\DjangoStartProject\mysite>python -m pip list``<br/>
      Package    Version<br/>
      ---------- -------<br/>
      asgiref    3.6.0<br/>
      Django     4.2.1<br/>
      pip        23.1.2<br/>
      setuptools 65.5.0<br/>
      sqlparse   0.4.4<br/>
      tzdata     2023.3<br/>

``(.venv) ..\DjangoStartProject\mysite>dir``<br/>

      Directory of ..\DjangoStartProject\mysite
      ..           131,072 db.sqlite3
      ..               684 manage.py
      ..    <DIR>          mysite

``(.venv) ..\DjangoStartProject\mysite>python -m pip freeze > requirements.txt``<br/>

``(.venv) ..\DjangoStartProject\mysite>``<br/>

``(.venv) ..\DjangoStartProject\mysite>dir``<br/>

      Directory of ..\DjangoStartProject\mysite
      ..           131,072 db.sqlite3
      ..               684 manage.py
      ..    <DIR>          mysite
      ..                64 requirements.txt

``(.venv) ..\DjangoStartProject\mysite>cd ..``<br/>

``(.venv) ..\DjangoStartProject>.\.venv\Scripts\deactivate``<br/>

``..\DjangoStartProject>``<br/>

``..\DjangoStartProject>exit``<br/>


