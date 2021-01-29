# Django to Heroku in Seconds

This bit of code will help you setup and deploy a Django server on Heroku in seconds!

_NOTE: Originally made for Unix-like systems. Windows will have some changes. See: https://devcenter.heroku.com/articles/getting-started-with-python#define-a-procfile_

0. Download repository from source
1. Create new django project

   `mdkir myapp`

   `cd myapp`

   `python3 -m venv venv`

   `source venv/bin/activate`

   `python3 -m pip install -r requirements.txt`

   `django-admin startproject sample`

2. Move all files in this repository into new django project (Not `venv/`)
3. Copy and paste settings.py into newly created settings.py
4. Change ROOT_URLCONF in settings.py to module name

   `ROOT_URLCONF = "sample.urls"`

5. Change WSGI_APPLICATION in settings.py to module name

   `WSGI_APPLICATION = "sample.wsgi.application"`

6. Change Procfile to module name

   `web: gunicorn sample.wsgi --preload --log-file -`

7. Copy and Paste SECRET_KEY from new Django Project into `.env`
8. Test application

   `python3 manage.py runserver`

9. Login into Heroku

   `heroku login`

10. Create new heroku app

    `heroku create APP_NAME`

11. Set SECRET_KEY in Heroku Web App

12. Deploy app to Heroku

13. Set up papertrail

    `heroku addons:create papertrail`
