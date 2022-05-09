# Reading_Notes
## Code 401 - Advanced Software Development





By [Ghaida Al Momani] (https://github.com/GhaidaMomani).


<br/>
<hr/>
<br/>

# Django Models
* [Link to Article](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)  


A model is the single, definitive source of information about your data. It contains the essential fields and behaviors of the data you’re storing. Generally, each model maps to a single database table.

The basics:

Each model is a Python class that subclasses django.db.models.Model.
Each attribute of the model represents a database field.
With all of this, Django gives you an automatically-generated database-access API; see Making queries.
Quick example¶
This example model defines a Person, which has a first_name and last_name:

from django.db import models
```
class Person(models.Model):
    first_name = models.CharField(max_length=30)
    last_name = models.CharField(max_length=30)

```

first_name and last_name are fields of the model. Each field is specified as a class attribute, and each attribute maps to a database column.

The above Person model would create a database table like this:

```

CREATE TABLE myapp_person (
    "id" serial NOT NULL PRIMARY KEY,
    "first_name" varchar(30) NOT NULL,
    "last_name" varchar(30) NOT NULL
);

```
Some technical notes:

The name of the table, myapp_person, is automatically derived from some model metadata but can be overridden. See Table names for more details.
An id field is added automatically, but this behavior can be overridden. See Automatic primary key fields.
The CREATE TABLE SQL in this example is formatted using PostgreSQL syntax, but it’s worth noting Django uses SQL tailored to the database backend specified in your settings file.

Using models¶
Once you have defined your models, you need to tell Django you’re going to use those models. Do this by editing your settings file and changing the INSTALLED_APPS setting to add the name of the module that contains your models.py.

For example, if the models for your application live in the module myapp.models (the package structure that is created for an application by the manage.py startapp script), INSTALLED_APPS should read, in part:
```

INSTALLED_APPS = [
    #...
    'myapp',
    #...
]
```
### Django Admin
* [Link to Article](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)  
NOTE: The tutorial is really good but some of the tools are dated so when reading try to understand the concepts more than the code. 

- Django admin application can use your models to automatically build a site area that you can use to create, view, update, and delete records.
- You must register your models in the admin.py  
- Creating superusers, using manage.py createsuperuser this will prompt user input and email and password



## Additional Resources  
* [Beginner's Guide to Django - Part 1](https://simpleisbetterthancomplex.com/series/2017/09/04/a-complete-beginners-guide-to-django-part-1.html)  

## Bookmark/Skim  
* [Beginner's Guide to Django - Part 2](https://simpleisbetterthancomplex.com/series/2017/09/11/a-complete-beginners-guide-to-django-part-2.html)  



<hr/>
<p align="right">(<a href="#top">back to top</a>)</p>



<br/><br/>

<p align="right">Ghaida Al Momani, Software Engineer</p>
<p align="right">Jordan, Amman</p>
  <p align="right">22, 9 MAY</p>