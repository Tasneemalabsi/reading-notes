# Django CRUD and Forms

- An HTML Form is a group of one or more fields/widgets on a web page, which can be used to collect information from users for submission to a server.
- Forms are a flexible mechanism for collecting user input.
- Forms are also a relatively secure way of sharing data with the server, as they allow us to send data in POST requests with cross-site request forgery protection.

## HTML Forms

*The form is defined in HTML as a collection of elements inside `<form>`...`</form>` tags, containing at least one input element of type="submit".*

```
<form action="/team_name_url/" method="post">
    <label for="team_name">Enter name: </label>
    <input id="team_name" type="text" name="name_field" value="Default name for team.">
    <input type="submit" value="OK">
</form>
```

*The form attributes define the HTTP method used to send the data and the destination of the data on the server (action):*

- action: The resource/URL where data is to be sent for processing when the form is submitted.
- method: The HTTP method used to send the data: post or get.

## Django form handling process

*A process flowchart of how Django handles form requests is shown below, starting with a request for a page containing a form*

![pic](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms/form_handling_-_standard.png)

*the main things that Django's form handling does are:*

1. Display the default form the first time it is requested by the user.
2. Receive data from a submit request and bind it to the form.
3. Clean and validate the data.
4. If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.
5. If all data is valid, perform required actions.
6. Once all actions are complete, redirect the user to another page.

### Form in Django

- The Form class is the heart of Django's form handling system. 
- It specifies the fields in the form, their layout, display widgets, labels, initial values, valid values, and (once validated) the error messages associated with invalid fields.
- The class also provides methods for rendering itself in templates using predefined formats (tables, lists, etc.) or for getting the value of any element (enabling fine-grained manual rendering).

**Declaring a Form**

```
from django import forms

class RenewBookForm(forms.Form):
    renewal_date = forms.DateField(help_text="Enter a date between now and 4 weeks (default 3).")
```

### Form fields

*The arguments that are common to most fields are listed below:*

- required: If True, the field may not be left blank or given a None value. 
- label: The label to use when rendering the field in HTML.
- label_suffix: By default, a colon is displayed after the label (e.g. Renewal date**:**). 
- initial: The initial value for the field when the form is displayed.
- widget: The display widget to use.
- help_text: Additional text that can be displayed in forms to explain how to use the field.
- error_messages: A list of error messages for the field. 
- validators: A list of functions that will be called on the field when it is validated.
- localize: Enables the localization of form data input.
- disabled: The field is displayed but its value cannot be edited if this is True.

### Validation

*Update forms.py file so it looks like this:*

```
import datetime

from django import forms

from django.core.exceptions import ValidationError
from django.utils.translation import ugettext_lazy as _

class RenewBookForm(forms.Form):
    renewal_date = forms.DateField(help_text="Enter a date between now and 4 weeks (default 3).")

    def clean_renewal_date(self):
        data = self.cleaned_data['renewal_date']

        # Check if a date is not in the past.
        if data < datetime.date.today():
            raise ValidationError(_('Invalid date - renewal in past'))

        # Check if a date is in the allowed range (+4 weeks from today).
        if data > datetime.date.today() + datetime.timedelta(weeks=4):
            raise ValidationError(_('Invalid date - renewal more than 4 weeks ahead'))

        # Remember to always return the cleaned data.
        return data
```        


### URL configuration

`urlpatterns += [
    path('book/<uuid:pk>/renew/', views.renew_book_librarian, name='renew-book-librarian'),
]`

### View

```
import datetime

from django.shortcuts import render, get_object_or_404
from django.http import HttpResponseRedirect
from django.urls import reverse

from catalog.forms import RenewBookForm

def renew_book_librarian(request, pk):
    book_instance = get_object_or_404(BookInstance, pk=pk)

    if request.method == 'POST':

        form = RenewBookForm(request.POST)


        if form.is_valid():
            
            book_instance.due_back = form.cleaned_data['renewal_date']
            book_instance.save()

            return HttpResponseRedirect(reverse('all-borrowed') )
    else:
        proposed_renewal_date = datetime.date.today() + datetime.timedelta(weeks=3)
        form = RenewBookForm(initial={'renewal_date': proposed_renewal_date})

    context = {
        'form': form,
        'book_instance': book_instance,
    }

    return render(request, 'catalog/book_renew_librarian.html', context)
```    

First, we import our form (RenewBookForm) and a number of other useful objects/methods used in the body of the view function:

- get_object_or_404()
- HttpResponseRedirect
- reverse()
- datetime

*The final view is therefore as shown below. Please copy this into the bottom of locallibrary/catalog/views.py.*

```
import datetime

from django.contrib.auth.decorators import login_required, permission_required
from django.shortcuts import get_object_or_404
from django.http import HttpResponseRedirect
from django.urls import reverse

from catalog.forms import RenewBookForm

@login_required
@permission_required('catalog.can_mark_returned', raise_exception=True)
def renew_book_librarian(request, pk):
    
    book_instance = get_object_or_404(BookInstance, pk=pk)


    if request.method == 'POST':
        form = RenewBookForm(request.POST)

        # Check if the form is valid:
        if form.is_valid():
            # process the data in form.cleaned_data as required (here we just write it to the model due_back field)
            book_instance.due_back = form.cleaned_data['renewal_date']
            book_instance.save()

        
            return HttpResponseRedirect(reverse('all-borrowed') )


    else:
        proposed_renewal_date = datetime.date.today() + datetime.timedelta(weeks=3)
        form = RenewBookForm(initial={'renewal_date': proposed_renewal_date})

    context = {
        'form': form,
        'book_instance': book_instance,
    }

    return render(request, 'catalog/book_renew_librarian.html', context)
```    

**Template:**

```

{% block content %}
  <h1>Renew: {{ book_instance.book.title }}</h1>
  <p>Borrower: {{ book_instance.borrower }}</p>
  <p{% if book_instance.is_overdue %} class="text-danger"{% endif %}>Due date: {{ book_instance.due_back }}</p>

  <form action="" method="post">
    {% csrf_token %}
    <table>
    {{ form.as_table }}
    </table>
    <input type="submit" value="Submit">
  </form>
{% endblock %}
```

*we can access a number of separate items for the renewal_date field:*

- {{ form.renewal_date }}: The whole field.
- {{ form.renewal_date.errors }}: The list of errors.
- {{ form.renewal_date.id_for_label }}: The id of the label.
- {{ form.renewal_date.help_text }}: The field help text.

### Testing the page

`{% if perms.catalog.can_mark_returned %}- <a href="{% url 'renew-book-librarian' bookinst.id %}">Renew</a>  {% endif %}`

### What does it look like?

![pic2](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms/forms_example_renew_default.png)

### ModelForms

```
from django.forms import ModelForm

from catalog.models import BookInstance

class RenewBookModelForm(ModelForm):
    class Meta:
        model = BookInstance
        fields = ['due_back']
```


