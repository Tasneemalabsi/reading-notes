# Intro to Django

*Django is a Python-based web framework used by millions of developers and billions of consumers through popular apps like Instagram.*
## Object-relational mapper

### Models :
*A model is the single, definitive source of information about your data. It contains the essential fields and behaviors of the data you’re storing. Generally, each model maps to a single database table.*

- Each model is a Python class that subclasses django.db.models.Model.
- Each attribute of the model represents a database field.
- With all of this, Django gives you an automatically-generated database-access API .

**Example:**

`from django.db import models`

`class Person(models.Model):`

    first_name = models.CharField(max_length=30)
    last_name = models.CharField(max_length=30)

### Fields

**Example:**

`from django.db import models`


`class Musician(models.Model):`

    first_name = models.CharField(max_length=50)
    last_name = models.CharField(max_length=50)
    instrument = models.CharField(max_length=100)

`class Album(models.Model):`

    artist = models.ForeignKey(Musician, on_delete=models.CASCADE)
    name = models.CharField(max_length=100)
    release_date = models.DateField()
    num_stars = models.IntegerField()

**Field Types:**

- The column type, which tells the database what kind of data to store (e.g. INTEGER, VARCHAR, TEXT).
- The default HTML widget to use when rendering a form field (e.g. `<input type="text">`, `<select>`).
- The minimal validation requirements, used in Django’s admin and in automatically-generated forms.

### Relationships

*the power of relational databases lies in relating tables to each other. Django offers ways to define the three most common types of database relationships: many-to-one, many-to-many and one-to-one.*

**Many-To-One-Relationship:**

`from django.db import models`

`class Manufacturer(models.Model):`

    # ...
    pass

`class Car(models.Model):`

    manufacturer = models.ForeignKey(Manufacturer, on_delete=models.CASCADE)
    # ...

**Many-to-many relationships:**

**Example:**

`from django.db import models`

`class Topping(models.Model):`

    # ...
    pass
`
`class Pizza(models.Model):`
    # ...
    toppings = models.ManyToManyField(Topping)

**One-to-one relationships**

*OneToOneField requires a positional argument: the class to which the model is related.*

### Model Inheritance:

**There are three styles of inheritance that are possible in Django.**

1. Often, you will just want to use the parent class to hold information that you don’t want to have to type out for each child model. 
2. If you’re subclassing an existing model and want each model to have its own database table, Multi-table inheritance is the way to go.
3. Finally, if you only want to modify the Python-level behavior of a model, without changing the models fields in any way, you can use Proxy models.

## URL and Views 

### URL dispatcher

*A clean, elegant URL scheme is an important detail in a high-quality Web application. Django lets you design URLs however you want, with no framework limitations.*

**How Django processes a request**

1. Django determines the root URLconf module to use. Ordinarily, this is the value of the ROOT_URLCONF setting .
2. Django loads that Python module and looks for the variable urlpatterns. 
3. Django runs through each URL pattern, in order, and stops at the first one that matches the requested URL, matching against path_info.
4. Once one of the URL patterns matches, Django imports and calls the given view, which is a Python function .


**Example:**

`from django.urls import path`

`from . import views`

`urlpatterns = [`

    path('articles/2003/', views.special_case_2003),`
    path('articles/<int:year>/', views.year_archive),
    path('articles/<int:year>/<int:month>/', views.month_archive),
    path('articles/<int:year>/<int:month>/<slug:slug>/', views.article_detail),
`]`


### Path converters
**The following path converters are available by default:**

- str 
- int 
- slug 
- uuid 
- path 

## Templates

*Django defines a standard API for loading and rendering templates regardless of the backend. Loading consists of finding the template for a given identifier and preprocessing it.*

*A Django template is a text document or a Python string marked-up using the Django template language. Some constructs are recognized and interpreted by the template engine. The main ones are variables and tags.*

**The syntax of the Django template language involves four constructs.**

- **Variables:**
A variable outputs a value from the context, which is a dict-like object mapping keys to values.
- **Tags:**
Tags provide arbitrary logic in the rendering process.
- **Filters:**
Filters transform the values of variables and tag arguments.
- **Comments:**

*Comments look like this:*

`{# this won't be rendered #}`

## Working with forms

**GET and POST**

- GET and POST are the only HTTP methods to use when dealing with forms.

- Django’s login form is returned using the POST method, in which the browser bundles up the form data, encodes it for transmission, sends it to the server, and then receives back its response.


- GET would also be unsuitable for a password form, because the password would appear in the URL, and thus, also in browser history and server logs, all in plain text.

### Django’s role in forms

**Django handles three distinct parts of the work involved in forms:**

- preparing and restructuring data to make it ready for rendering
- creating HTML forms for the data
- receiving and processing submitted forms and data from the client

### Instantiating, processing, and rendering forms

*When rendering an object in Django, we generally:*

1. get hold of it in the view (fetch it from the database, for example)
2. pass it to the template context
3. expand it to HTML markup using template variables

### Building a form

**Example:**

`<form action="/your-name/" method="post">`
    
    <label for="your_name">Your name: </label>
    <input id="your_name" type="text" name="your_name" value="{{ current_name }}">
    <input type="submit" value="OK">
`</form>`

### In Django:

**The Form class**




`from django import forms`

`class NameForm(forms.Form):`

    your_name = forms.CharField(label='Your name', max_length=100)

### Bound and unbound form instances¶
*The distinction between Bound and unbound forms is important:*

- An unbound form has no data associated with it. When rendered to the user, it will be empty or will contain default values.
- A bound form has submitted data, and hence can be used to tell if that data is valid. 

## Authentication

**The auth system consists of:**

- Users
- Permissions: Binary (yes/no) flags designating whether a user may perform a certain task.
- Groups: A generic way of applying labels and permissions to more than one user.
- A configurable password hashing system
- Forms and view tools for logging in users, or restricting content
- A pluggable backend system

### Installation

- 'django.contrib.auth' contains the core of the authentication framework, and its default models.
- 'django.contrib.contenttypes' is the Django content type system, which allows permissions to be associated with models you create.

## Admin

*The admin is enabled in the default project template used by startproject.*

### ModelAdmin objects

**class ModelAdmin**

*The ModelAdmin class is the representation of a model in the admin interface. Example:*

`from django.contrib import admin`

`from myapp.models import Author`


`class AuthorAdmin(admin.ModelAdmin):`

    pass
`admin.site.register(Author, AuthorAdmin)`

### The register decorator

`from django.contrib import admin`
`from .models import Author`

`@admin.register(Author)`

`class AuthorAdmin(admin.ModelAdmin):`

    pass

## Internationalization

*The goal of internationalization and localization is to allow a single Web application to offer its content in languages and formats tailored to the audience.*

**Essentially, Django does two things:**

- It allows developers and template authors to specify which parts of their apps should be translated or formatted for local languages and cultures.
- It uses these hooks to localize Web apps for particular users according to their preferences.

**internationalization**

*Preparing the software for localization. Usually done by developers.*

**localization**

*Writing the translations and local formats. Usually done by translators.*

## Security 

*Django provides multiple protections against:*

- Clickjacking
- Cross-site scripting
- Cross Site Request Forgery (CSRF)
- SQL injection
- Remote code execution


## How Django Works Behind the Scene

*Almost all popular open source packages have some degree of funding involved, typically in one of three forms:*

1) Corporate Sponsor - A group of engineers within a larger, for-profit company decide to open-source internal code. 

2) Solo - An individual developer initially creates code, open sources it, and retains default control. 

3) Non-profit - This was Django’s approach early on, in 2008, when the Django Software Foundation was formed to promote, support, and advance Django.


## Conclusion

Django’s organization is managed by a non-profit, the DSF, with a miniscule budget. And Django code is lead by a core team of volunteers, two paid Django Fellows, and a larger group of contributors.


