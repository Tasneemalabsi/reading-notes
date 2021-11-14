# Django Models

## Using Models

*Django web applications access and manage data through Python objects referred to as models. Models define the structure of stored data, including the field types and possibly also their maximum size, default values, selection list options, help text for documentation, label text for forms, etc.*

### Designing the LocalLibrary models

When designing your models it makes sense to have separate models for every "object" (a group of related information). In this case, the obvious objects are books, book instances, and authors.

*With that in mind, the UML association diagram below shows the models we'll define in this case (as boxes).*

![pic](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models/local_library_model_uml.svg)

The diagram shows the relationships between the models, including their multiplicities. The multiplicities are the numbers on the diagram showing the numbers (maximum and minimum) of each model that may be present in the relationship. 

### Model primer

**Model definition**

*Models are usually defined in an application's models.py file. They are implemented as subclasses of django.db.models.Model, and can include fields, methods and metadata.*

```
from django.db import models

class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""

    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    ...

    # Metadata
    class Meta:
        ordering = ['-my_field_name']

    # Methods
    def get_absolute_url(self):
        """Returns the url to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])

    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name
```

**Fields**

A model can have an arbitrary number of fields, of any type — each one represents a column of data that we want to store in one of our database tables.

`my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')`

The field name is used to refer to it in queries and templates. Fields also have a label specified as an argument (verbose_name), the default value of which is None, meaning replacing any underscores in the field name with a space

**Common field arguments**

*The following common arguments can be used when declaring many/most of the different field types:*

- help_text: Provides a text label for HTML forms. 
- verbose_name: A human-readable name for the field used in field labels. 
- default: The default value for the field. 
- null: If True, Django will store blank values as NULL in the database for fields where this is appropriate.
- blank: If True, the field is allowed to be blank in your forms. The default is False, which means that Django's form validation will force you to enter a value. 
- choices: A group of choices for this field.
- primary_key: If True, sets the current field as the primary key for the model.

**Metadata**

`class Meta:`

    ordering = ['-my_field_name']

*One of the most useful features of this metadata is to control the default ordering of records returned when you query the model type.*

**Methods**

*A model can also have methods.*

```
def __str__(self):
    return self.field_name
```

### Model management

**Creating and modifying records**

*To create a record you can define an instance of the model and then call save().*

`record = MyModelName(my_field_name="Instance #1")`

`record.save()`

### Defining the LocalLibrary Models


8The boilerplate at the top of the page imports the models module, which contains the model base class models.Model that our models will inherit from.*

`from django.db import models`

**Genre model**

```
class Genre(models.Model):
    """Model representing a book genre."""
    name = models.CharField(max_length=200, help_text='Enter a book genre (e.g. Science Fiction)')

    def __str__(self):
        """String for representing the Model object."""
        return self.name
```


**Book model**

```
from django.urls import reverse 

class Book(models.Model):

    title = models.CharField(max_length=200)
    author = models.ForeignKey('Author', on_delete=models.SET_NULL, null=True)

    summary = models.TextField(max_length=1000, help_text='Enter a brief description of the book')
    isbn = models.CharField('ISBN', max_length=13, unique=True,
                             help_text='13 Character <a href="https://www.isbn-international.org/content/what-isbn">ISBN number</a>')

    genre = models.ManyToManyField(Genre, help_text='Select a genre for this book')

    def __str__(self):
        return self.title

    def get_absolute_url(self):
        return reverse('book-detail', args=[str(self.id)])

```

## Django Admin    

*The Django admin application can use your models to automatically build a site area that you can use to create, view, update, and delete records.*

### Registering models 

`from django.contrib import admin`



```
from .models import Author, Genre, Book, BookInstance

admin.site.register(Book)
admin.site.register(Author)
admin.site.register(Genre)
admin.site.register(BookInstance)
```

### Creating a superuser

**How?**

`python3 manage.py createsuperuser`

**Run the server**

`python3 manage.py runserver`

### Logging in and using the site

*To login to the site, open the /admin URL (e.g. http://127.0.0.1:8000/admin) and enter your new superuser userid and password credentials*

![login](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site/admin_home.png)

### Advanced configuration

*Django does a pretty good job of creating a basic admin site using the information from the registered models:*

- Each model has a list of individual records, identified by the string created with the model's __str__() method, and linked to detail views/forms for editing. 
- The model detail record forms for editing and adding records contain all the fields in the model, laid out vertically in their declaration order.

### Register a ModelAdmin class

```
class AuthorAdmin(admin.ModelAdmin):
    pass

admin.site.register(Author, AuthorAdmin)
```

### Configure list views

```
class AuthorAdmin(admin.ModelAdmin):
    list_display = ('last_name', 'first_name', 'date_of_birth', 'date_of_death')
```






