# Django REST Framework & Docker 

## Beginner’s Guide to Docker 

### Linux Containers 

*Docker is really just Linux containers which are a type of virtualization.*

*Virtualization has its roots at the beginning of computer science when large, expensive mainframe computers were the norm.*

**How could multiple programmers use the same single machine?** 

*The answer was virtualization and specifically virtual machines which are complete copies of a computer system from the operating system on up.*

**What’s the downside to a virtual machine?** 

*Size and speed. A typical guest operating system can easily take up 700MB of size. So if one physical server supports three virtual machines, that’s at least 2.1GB of disk space taken up along with separate needs for CPU and memory resources.*

### Containers vs Virtual Environments 

*Virtual environments are used to isolate Python software packages locally.* 

*virtual environments can only isolate Python packages.* 

*can’t run a production database or other services within virtual environments so compared to Docker containers they are far more limited.* 

### Install Docker 

*To install Docker we need to download the desktop app on our computer and create a free account. The initial download of Docker might take some time to download. It’s a big file.* 

*Once Docker is done installing we can confirm the correct version is running. It should be at least version 19.* 

    $ docker --version
    Docker version 19.03.5, build 633a0ea

* Docker Compose  : is an additional tool that is automatically included with Mac and Windows downloads of Docker.

*run the command below to confirm you have a working version of it, too. The version should be at least 1.24.x.*

    $ docker-compose --version
    docker-compose version 1.24.1, build 4667896b

**To confirm Docker installed correctly we can run our first command docker run hello-world.** 

    $ docker run hello-world
    Unable to find image 'hello-world:latest' locally
    latest: Pulling from library/hello-world
    1b930d010525: Pull complete
    Digest: sha256:9572f7cdcee8591948c2963463447a53466950b3fc15a247fcad1917ca215a2f
    Status: Downloaded newer image for hello-world:latest

    Hello from Docker!
    This message shows that your installation appears to be working correctly.

    To generate this message, Docker took the following steps:
    1. The Docker client contacted the Docker daemon.
    2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
        (amd64)
    3. The Docker daemon created a new container from that image which runs the
        executable that produces the output you are currently reading.
    4. The Docker daemon streamed that output to the Docker client, which sent it
        to your terminal.

    To try something more ambitious, you can run an Ubuntu container with:
    $ docker run -it ubuntu bash

    Share images, automate workflows, and more with a free Docker ID:
    https://hub.docker.com/

    For more examples and ideas, visit:
    https://docs.docker.com/get-started/

*A good command to inspect Docker is docker info* 

    $ docker info
    Containers: 1
    Running: 0
    Paused: 0
    Stopped: 1
    Images: 1

### Images and Containers 

**Images and containers are the two fundamental concepts to grasp when you start with Docker. An image is a snapshot in time of what a project contains. A container is a running instance of the image.** 

> A baking analogy we can use here is as follows: 

* A Dockerfile is the recipe for a cake
* An image is a snapshot of the recipe at a given time
* A docker-compose.yml says how to make the cake
* And the container is the actual, baked cake

### Images 

*First create a local directory on your computer for our code. I’ve chosen to make a code folder on my Desktop (I’m using an Apple computer) and then a python3.7 folder within that.* 

    $ cd ~/Desktop
    $ mkdir code && cd code
    $ mkdir python3.7 && cd python3.7

*Now we need to define the image with a Dockerfile. This is similar to a Pipenv or a requirements.txt file; it is a list of all the requirements needed to build our image. It is simpler to have them all in one place rather than install each manually line-by-line.* 

*With your text editor add the following single line of code to the Dockerfile.* 

    # Dockerfile
    FROM python:3.7-alpine

*Dockerfiles are read from top-to-bottom.* 

*The first instruction must be the FROM command which lets us import a base image to use for our image. This base image could be another Docker image or one we create entirely from scratch.* 

### Image Builds 

*With our instructions complete it’s time to “build” or create the image for the first time. Don’t forget that period . at the end of the command!* 

    $ docker image build .
    Sending build context to Docker daemon  2.048kB
    Step 1/1 : FROM python:3.7-alpine
    3.7-alpine: Pulling from library/python
    c9b1b535fdd9: Pull complete
    2cc5ad85d9ab: Pull complete
    53a2fca3c2ea: Pull complete
    30fce49de8b1: Pull complete
    49bcb9571cc7: Pull complete
    Digest: sha256:7655eea15dfd981eeb7d243af21e8561e967709caba938d50b136cdb992f3546
    Status: Downloaded newer image for python:3.7-alpine
    ---> b2c276538711
    Successfully built b2c276538711

*We can list all existing Docker images to confirm this new one has been built alongside the initial alpine image.* 

    $ docker image ls
    REPOSITORY      TAG             IMAGE ID            CREATED             SIZE
    python          3.7-alpine      b2c276538711        3 days ago          97.7MB
    hello-world     latest          fce289e99eb9        12 months ago       1.84kB

### Image Layers 

*Every image is made up of one or more image layers. The base layer is often a flavor of Linux, like alpine. When we built the image for python:3.7-alpine this image had the id b2c276538711. But that image depended on five other images which were visible while building it:* 

    c9b1b535fdd9: Pull complete
    2cc5ad85d9ab: Pull complete
    53a2fca3c2ea: Pull complete
    30fce49de8b1: Pull complete
    49bcb9571cc7: Pull complete

*This is called image layering and it exists for two main reasons. First, each image layer is immutable–unchanged–like a git commit. This helps ensure consistency when two developers build the same image. The second reason is performance. Docker caches the steps in a Dockerfile to speed up subsequent builds. When a change is made to a step, all steps following it will be executed from scratch.*

*For this reason, order matters in a Dockerfile. Typically you want to put code that won’t change often at the top and code that will change at the end. We’ll see this in action shortly.*

### Containers 

*Now that we have our Python image how do we run it? Well just as a Dockerfile is a list of image instructions there is also a docker-compose.yml file that is a list of container instructions.*

*To demonstrate a real-world image and container example we will now “Dockerize” a basic Django web app. You might not fully understand every step but you’ll see how Docker can work to run a web application completely on its own.*

*On the command line, go up a directory to our code folder and create a new one called djangoapp. Then we’ll use Pipenv to install Django and enter the virtual environment shell.*

    $ cd ..
    $ mkdir djangoapp && cd djangoapp
    $ pipenv install django==3.0
    $ pipenv shell  

*This creates both a Pipfile and a Pipfile.lock. Now create an example_project that we’ll put in our current directory. Don’t forget the period . at the end of the command here!*

    (djangoapp) $ django-admin startproject example_project .

*And then we can use runserver to start this new Django project.* 

    (djangoapp) $ python manage.py runserver

![](https://wsvincent.com/assets/images/beginners-guide-to-docker/welcome30.png)

### Dockerized Django 

*now create a Dockerfile for our image which will completely replace our local dev environment, so this will have Python 3 and Django. Then we’ll add a docker-compose.yml for the container instructions. Make each file via the command line.*

    $ touch Dockerfile
    $ touch docker-compose.yml

*This Dockerfile has several commands. RUN, COPY, and ADD each create a new layer.* 

    # Dockerfile

    # Python version
    FROM python:3.7-alpine

    # Set environment variables
    ENV PYTHONDONTWRITEBYTECODE 1
    ENV PYTHONUNBUFFERED 1

    # Set work directory
    WORKDIR /code

    # Install dependencies
    COPY Pipfile Pipfile.lock /code/
    RUN pip install pipenv && pipenv install --system

    # Copy project
    COPY . /code/

*Order matters in Dockerfiles since they are executed from top-to-bottom. First we use FROM to install python:3.7-alpine as our base image and set two environment variables with ENV. The first, PYTHONDONTWRITEBYTECODE will remove .pyc files from our container which is a good optimization. The second, PYTHONUNBUFFERED will buffer our output so it will look “normal” within Docker for us.*

*Then we used the WORKDIR command to create and set /code as our default directory within Docker. That means if in the future we want to run a command like python manage.py runserver we don’t have to also specify it should be run in the /code folder.*

*The Pipfile contains information on our software packages so we copy that over, too. (Technically we could use COPY Pipfile . and because of the WORKDIR setting it would still go in the /code folder!).*

*And then we install Pipenv itself via pip and then run pipenv install to install the software packages in our Pipfile. Note that we added the --system tag so that software packages are available throughout the entire container, not within a virtual environment which is Pipenv’s default but doesn’t make sense here since the entire Docker container is a virtual environment.*

*An important point to make here is that the order in a Dockerfile matters a lot. Because of layer caching when a step changes in the Dockerfile, all subsequent work needs to be redone.* 

**Now time for docker-compose.yml.** 

    # docker-compose.yml
    version: '3.7'

    services:
    web:
        build: .
        command: python /code/manage.py runserver 0.0.0.0:8000
        volumes:
        - .:/code
        ports:
        - 8000:8000

*Instead of running separate commands to build the image and run the container we can do that with one now.*

    $ docker-compose up --build
    Creating network "djangoapp_default" with the default driver
    Building webStep 1/6 : FROM python:3.7-alpine
    ...
    Successfully built 047a6d848c5b
    Successfully tagged djangoapp_web:latest
    Recreating djangoapp_web_1 ... done
    Attaching to djangoapp_web_1
    web_1  | Performing system checks...
    web_1  |
    web_1  | Watching for file changes with StatReloader
    web_1  | System check identified no issues (0 silenced).
    web_1  |
    web_1  | You have 17 unapplied migration(s). Your project may not work properly until you apply the migrati
    ons for app(s): admin, auth, contenttypes, sessions.
    web_1  | Run 'python manage.py migrate' to apply them.
    web_1  | January 21, 2020 - 14:49:16
    web_1  | Django version 3.0, using settings 'example_project.settings'
    web_1  | Starting development server at http://0.0.0.0:8000/
    web_1  | Quit the server with CONTROL-C.

### Conclusion 

*The important takeaways from this tutorial are this:* 

* Docker is a way to run Linux containers
* Containers are a lightweight alternative to Virtual Machines
* Dockerfile is a list of instructions for creating an image
* Images are made up of one or more layers
* Containers are a running instance of an image
* docker-compose.yml controls how to run the container
* Containers are stateless and ephemeral in nature. We can link the 
* local filesystem via volumes but things become more complex with databases (which we didn’t cover here).

## Django for APIs - Library Website 

**Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework; it always must be added to a project after Django itself has been installed and configured.** 

### Traditional Django 

*First we need a dedicated directory on our computer to store the code. This can live anywhere but for convenience, if you are on a Mac, we can place it in the Desktop folder. The location really does not matter; it just needs to be easily accessible.* 

    $ cd ~/Desktop
    $ mkdir code && cd code

*Now we are within the code folder which will be the location for all the code in this book. The next step is to create a dedicated directory for our library site, install Django via Pipenv, and then enter the virtual environment using the shell command. You should always use a dedicated virtual environment for every new Python project.* 

    $ mkdir library && cd library
    $ pipenv install django~=3.1.0
    $ pipenv shell
    (library) $

*Pipenv creates a Pipfile and a Pipfile.lock within our current directory. The (library) in parentheses before the command line shows that our virtual environment is active.*

*A traditional Django website consists of a single project and one (or more) apps representing discrete functionality. Let’s create a new project with the startproject command. Don’t forget to include the period . at the end which installs the code in our current directory. If you do not include the period, Django will create an additional directory by default.*

    (library) $ django-admin startproject config . 

*Django automatically generates a new project for us which we can see with the tree command.* 

    (library) $ tree
    .
    ├── Pipfile
    ├── Pipfile.lock
    ├── config
    │   ├── __init__.py
    │   ├── asgi.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    └── manage.py

> The files have the following roles:

* __init__.py is a Python way to treat a directory as a package; it is empty
* asgi.py stands for Asynchronous Server Gateway Interface and is a new option in Django 3.0+
* settings.py contains all the configuration for our project
* urls.py controls the top-level URL routes
* wsgi.py stands for Web Server Gateway Interface and helps Django serve the eventual web pages
* manage.py executes various Django commands such as running the local web server or creating a new app. 

*Run migrate to sync the database with Django’s default settings and start up the local Django web server.* 

    (library) $ python manage.py migrate
    (library) $ python manage.py runserver

![](https://djangoforapis.com/assets/images/00_welcome31.png)

### First app 

**The typical next step is to start adding apps, which represent discrete areas of functionality. A single Django project can support multiple apps.**

*Stop the local server by typing Control + c and then create a books app.*

    (library) $ python manage.py startapp books

*Now let’s see what files Django has generated.* 

    (library) $ tree
    .
    ├── Pipfile
    ├── Pipfile.lock
    ├── books
    │   ├── __init__.py
    │   ├── admin.py
    │   ├── apps.py   
    |   ├── migrations
    │   │   └── __init__.py
    │   ├── models.py
    │   ├── tests.py
    │   └── views.py
    ├── config
    │   ├── __init__.py
    │   ├── asgi.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    └── manage.py

*Each app has a __init__.py file identifying it as a Python package. There are 6 new files created:* 

* admin.py is a configuration file for the built-in Django Admin app
* apps.py is a configuration file for the app itself
* the migrations/ directory stores migrations files for database changes
* models.py is where we define our database models
* tests.py is for our app-specific tests
* views.py is where we handle the request/response logic for our web app

*Let’s build out the files so that our Library project lists out all books on the homepage. Open the text editor of your choice to the config/settings.py file. The first step is to add the new app to our INSTALLED_APPS configuration. You’ll often see new apps added at the bottom but since Django loads apps in order, the newer best practice is to place local apps like books at the top instead.* 

    # library_project/settings.py
    INSTALLED_APPS = [
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',

        # Local
        'books', # new
    ]

*Then run migrate to sync our database with the changes.*

    (library) $ python manage.py migrate

### Models 

*In your text editor, open up the file books/models.py and update it as follows:*

    # books/models.py
    from django.db import models

    class Book(models.Model):
        title = models.CharField(max_length=250)
        subtitle = models.CharField(max_length=250)
        author = models.CharField(max_length=100)
        isbn = models.CharField(max_length=13)

        def __str__(self):
            return self.title

*This is a basic Django model where we import models from Django on the top line and then create a Book class that extends it. There are four fields: title, subtitle, author, and isbn. We also include a __str__ method so that the title of a book will display in the admin later on.* 

*Since we created a new database model we need to create a migration file to go along with it, then update our database.* 

    (library) $ python manage.py makemigrations books
    (library) $ python manage.py migrate

### Admin 

*Start with the superuser account. On the command line run the following command:* 

    (library) $ python manage.py createsuperuser

*Now update our book app’s admin.py file.*

    # books/admin.py
    from django.contrib import admin
    from .models import Book

    admin.site.register(Book)

![](https://djangoforapis.com/assets/images/02_admin_homepage.png)

*Click on the “+ Add” link next to Books.* 

![](https://djangoforapis.com/assets/images/02_admin_add_book.png)

![](https://djangoforapis.com/assets/images/02_admin_one_book.png)

### Views 

**The views.py file controls how the database model content is displayed. Since we want to list all books we can use the built-in generic class ListView.**

*Update the books/views.py file.*

    # books/views.py
    from django.views.generic import ListView
    from .models import Book


    class BookListView(ListView):
        model = Book
        template_name = 'book_list.html'

### URLs 

*We need to set up both the project-level urls.py file and then one within the books app. When a user visits our site they will first interact with the config/urls.py file so let’s configure that first. Add the include import on the second line and then a new path for our books app.* 

    # config/urls.py
    from django.contrib import admin
    from django.urls import path, include # new

    urlpatterns = [
        path('admin/', admin.site.urls),
        path('', include('books.urls')), # new
    ]

*Now we can configure our books/urls.py file. But, oops! Django for some reason does not include a urls.py file by default in apps so we need to create it ourself. If you are on a Mac you can use the touch command; Windows users must create the file within the text editor.* 

    (library) $ touch books/urls.py

*Now within a text editor update the new file.* 

    # books/urls.py
    from django.urls import path

    from .views import BookListView

    urlpatterns = [
        path('', BookListView.as_view()),
    ]

*Start by making a new templates folder within the books app, then within it a books folder, and finally a book_list.html file.* 

    (library) $ mkdir books/templates
    (library) $ mkdir books/templates/books
    (library) $ touch books/templates/books/book_list.html

*Now update the template file.* 

    <!-- books/templates/books/book_list.html -->
    <h1>All books</h1>
    {% for book in object_list %}
    <ul>
        <li>Title: {{ book.title }}</li>
        <li>Subtitle: {{ book.subtitle }}</li>
        <li>Author: {{ book.author }}</li>
        <li>ISBN: {{ book.isbn }}</li>
    </ul>
    {% endfor %}


### Webpage 

*Now we can start up the local Django server and see our web page.* 

    (library) $ python manage.py runserver

![](https://djangoforapis.com/assets/images/02_book_page.png)

## Django REST Framework 

*Django REST Framework is added just like any other third-party app. Make sure to quit the local server Control + c if it is still running. Then on the command line type the below.* 

    (library) $ pipenv install djangorestframework~=3.11.0

*Add it to the INSTALLED_APPS config in our settings.py file. I like to make a distinction between third-party apps and local apps as follows since the number of apps grows quickly in most projects.* 

    # config/settings.py
    INSTALLED_APPS = [
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',

        # 3rd party
        'rest_framework', # new

        # Local
        'books',
    ]

**Let’s first create a new api app.** 

    (library) $ python manage.py startapp api

*Then add it to INSTALLED_APPS.* 

    # config/settings.py
    INSTALLED_APPS = [
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',

        # 3rd party
        'rest_framework',

        # Local
        'books',
        'api', # new
    ]

### URLs 

*start with our URL configs. Adding an API endpoint is just like configuring a traditional Django app’s routes. First at the project-level we need to include the api app and configure its URL route, which will be api/.* 

    # config/urls.py
    from django.contrib import admin
    from django.urls import path, include

    urlpatterns = [
        path('admin/', admin.site.urls),
        path('api/', include('api.urls')), # new
        path('', include('books.urls')),
    ]

*Then create a urls.py file within the api app.* 

    (library) $ touch api/urls.py

*And update it as follows:* 

    # api/urls.py
    from django.urls import path
    from .views import BookAPIView

    urlpatterns = [
        path('', BookAPIView.as_view()),
    ]

### Views 

*Within our views.py file, update it to look like the following:* 

    # api/views.py
    from rest_framework import generics

    from books.models import Book
    from .serializers import BookSerializer


    class BookAPIView(generics.ListAPIView):
        queryset = Book.objects.all()
        serializer_class = BookSerializer

### Serializers 

*Make a serializers.py file within our api app.* 

    (library) $ touch api/serializers.py

*Then update it as follows in a text editor.* 

    # api/serializers.py
    from rest_framework import serializers

    from books.models import Book


    class BookSerializer(serializers.ModelSerializer):
        class Meta:
            model = Book
            fields = ('title', 'subtitle', 'author', 'isbn')

### cURL 

*ensure that our local Django server is running:*

    (library) $ python manage.py runserver

*All we need for a basic GET request it to specify curl and the URL we want to call.*

    $ curl http://127.0.0.1:8000/api/
    [  
    {  
        "title":"Django for Beginners",
        "subtitle":"Build websites with Python and Django",
        "author":"William S. Vincent",
        "isbn":"978-198317266"
    }
    ]

### Browsable API 

![](https://djangoforapis.com/assets/images/02_book_api.png)

