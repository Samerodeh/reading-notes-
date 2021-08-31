# Django Custom User 

## Django Custum User Model 

### AbstractUser vs AbstractBaseUser 

*There are two modern ways to create a custom user model in Django: AbstractUser and AbstractBaseUser. In both cases, we can subclass them to extend existing functionality however AbstractBaseUser requires much.*

### Custom User Model 

*Creating our initial custom user model requires four steps:* 

* update config/settings.py
* create a new CustomUser model
* create new UserCreation and UserChangeForm
* update the admin

### Superuser

*It's helpful to create a superuser that we can use to log in to the admin and test out log in/log out.*

## DjangoX 

![DjangoX](https://raw.githubusercontent.com/wsvincent/djangox/master/homepage.png)

### Installation

*DjangoX can be installed via Pip, Pipenv, or Docker depending upon your setup.* 

> Pip 

    $ python3 -m venv djangox
    $ source djangox/bin/activate
    (djangox) $ pip install -r requirements.txt
    (djangox) $ python manage.py migrate
    (djangox) $ python manage.py createsuperuser
    (djangox) $ python manage.py runserver
    # Load the site at http://127.0.0.1:8000

> Pipenv 

    $ pipenv install
    $ pipenv shell
    (djangox) $ python manage.py migrate
    (djangox) $ python manage.py createsuperuser
    (djangox) $ python manage.py runserver
    # Load the site at http://127.0.0.1:8000

> Docker 

    $ docker build .
    $ docker-compose up -d
    $ docker-compose exec web python manage.py migrate
    $ docker-compose exec web python manage.py createsuperuser
    # Load the site at http://127.0.0.1:8000 

*For Docker, the INTERNAL_IPS configuration in config/settings.py must be updated to the following:* 

    # config/settings.py
    # django-debug-toolbar
    import socket
    hostname, _, ips = socket.gethostbyname_ex(socket.gethostname())
    INTERNAL_IPS = [ip[:-1] + "1" for ip in ips]

### Setup 

    # Run Migrations
    (djangox) $ python manage.py migrate

    # Create a Superuser
    (djangox) $ python manage.py createsuperuser

    # Confirm everything is working:
    (djangox) $ python manage.py runserver

    # Load the site at http://127.0.0.1:8000 

### Contributing 

*Contributions, issues and feature requests are welcome! See CONTRIBUTING.md.*