# Django REST Framework & Docker

## Docker
*Docker is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers.*

### Linux Containers

*Docker is really just Linux containers which are a type of **virtualization.** *

Virtualization has its roots at the beginning of computer science when large, expensive mainframe computers were the norm. 

in recent years Linux containers, also known as “containerization,” has become increasingly popular. For most applications, a virtual machine provides far more resources than are needed and a container is more than sufficient.

This, fundamentally, is what Docker is. A way to implement Linux containers!

### Containers vs Virtual Environments

Virtual environments are used to isolate Python software packages locally. We can create an isolated box for individual projects so one can use Python 2.7 and Django 1.5 while another can use Python 3.5 and Django 2.1 on the same computer.

However, virtual environments can only isolate Python packages. They still rely on a global, system-level installation of Python albeit they can refer to the proper version.

### Install Docker

**to check the version:**
```
$ docker --version
Docker version 19.03.5, build 633a0ea
```

*Docker Compose is an additional tool that is automatically included with Mac and Windows downloads of Docker.*

A good command to inspect Docker is docker info, ex:

```
$ docker info
Containers: 1
 Running: 0
 Paused: 0
 Stopped: 1
Images: 1
```
### Images and Containers

**A baking analogy we can use here is as follows:**

- A Dockerfile is the recipe for a cake
- An image is a snapshot of the recipe at a given time
- A docker-compose.yml says how to make the cake
- And the container is the actual, baked cake

### Dockerized Django

*We’ll now create a Dockerfile for our image which will completely replace our local dev environment, so this will have Python 3 and Django.*

```
$ touch Dockerfile
$ touch docker-compose.yml
```

This Dockerfile has several commands. RUN, COPY, and ADD each create a new layer.

```
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
```

### Conclusion about docker:

- Docker is a way to run Linux containers
- Containers are a lightweight alternative to Virtual Machines
- Dockerfile is a list of instructions for creating an image
- Images are made up of one or more layers
- Containers are a running instance of an image
docker-compose.yml controls how to run the container
- Containers are stateless and ephemeral in nature. 

## Django for APIs

*Django REST Framework works alongside the Django web framework to create web APIs.*

### Traditional Django

```
$ mkdir library && cd library
$ pipenv install django~=3.1.0
$ pipenv shell
$ django-admin startproject config .
```
*The files have the following roles:*

- __init__.py is a Python way to treat a directory as a package; it is empty
- asgi.py stands for Asynchronous Server Gateway Interface and is a new option in Django 3.0+
- settings.py contains all the configuration for our project
- urls.py controls the top-level URL routes
- wsgi.py stands for Web Server Gateway Interface and helps Django serve the eventual web pages
- manage.py executes various Django commands such as running the local web server or creating a new app.

*if we ran startapp we'll have:*

- admin.py is a configuration file for the built-in Django Admin app
- apps.py is a configuration file for the app itself
the migrations/ directory stores migrations files for database changes
- models.py is where we define our database models
- tests.py is for our app-specific tests
- views.py is where we handle the request/response logic for our web app

### Models


**Example:**

```
from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=250)
    subtitle = models.CharField(max_length=250)
    author = models.CharField(max_length=100)
    isbn = models.CharField(max_length=13)

    def __str__(self):
        return self.title
```
### Django REST Framework

*Django REST Framework is added just like any other third-party app.*

`$ pipenv install djangorestframework~=3.11.0`

the installed app in the settings.py file will look like then:

```
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
```
**Starting apps:**

`python manage.py startapp api`

### Serializers

*A serializer translates data into a format that is easy to consume over the internet, typically JSON, and is displayed at an API endpoint.*

Make a serializers.py file within our api app.

`(library) $ touch api/serializers.py`

On the top lines we import Django REST Framework’s serializers class and the Book model from our books app. We extend Django REST Framework’s ModelSerializer into a BookSerializer class that specifies our database model Book and the database fields we wish to expose: title, subtitle, author, and isbn.

### cURL

`(library) $ python manage.py runserver`

Now open a new, second command line console. We will use it to access the API running in the existing command line console.

We can use the popular cURL program to execute HTTP requests via the command line. All we need for a basic GET request it to specify curl and the URL we want to call.

```
$ curl http://127.0.0.1:8000/api/
[  
   {  
      "title":"Django for Beginners",
      "subtitle":"Build websites with Python and Django",
      "author":"William S. Vincent",
      "isbn":"978-198317266"
   }
]
```

### Browsable API

With the local server still running in the first command line console, navigate to our API endpoint in the web browser at http://127.0.0.1:8000/api/.







