# Python 2

## Description

This Flask fundamental exercise is for Hong's Python2 class.


## Installation

**Installation via requirements.txt**

```shell
$ py -3 -m venv venv
$ venv\Scripts\activate
$ pip install -r requirements.txt

```

**Installation via requirements.txt(For macOS/Linux)**
```shell
$ python3 -m venv venv
$ . venv/bin/activate
$ pip3 install -r requirements.txt
```

## Execution

**Running the application**

From the directory, and within the activated virtual environment (see *venv\Scripts\activate* above):

````shell
$ flask run
```` 

The homepage can be accessed from a Web browser:

http://127.0.0.1:5000/


### Task 1

> In the root directory of the project create a .env file and set
the four key Flask configuration variables. (FLASK APP,
FLASK ENV, SECRET KEY, and TESTING) 

> Create a file named config.py in the root directory of the
project. Use dotenv to read the .env file and to set the Flask
configuration variables in the Config class.

> Assuming you have included FLASK ENV = 'development',
the Web application is now configured to dump exception
stack traces in the Web browser and to automatically reload
the application in the Web server in response to any source
code edits you make.
 

### Task 2
> In the people_web_app/\__init__.py file, edit the create_app()
method to configure the newly created Flask object using the
Flask configuration variables defined in config.Cofig.


### Task 3
> The homepage should be named home.html and stored in the
templates directory, and like the supplied list people.html
template, it should extend layout.html. The homepage should
override the block named content with something as simple.

### Task 4
>This template should be named list_person.html, and similarly
to home.html and list people.html should extend layout.html.
Assume that one variable (named person) will be supplied to
list person's content block; this is to be a Person object but
could be a None (none in Jinja) value. If the person variable
refers to a Person object (i.e. it's not None), the template
should output the Person's attribute values, otherwise it
should display a message to say that there is no matching
Person (you'll use this template later in task 10).

### Task 5 Blueprint Registeration
> A blueprint (defined in
people_web_app/people_blueprint/people.py) has been started.
It is sufficiently 
fleshed out to be registered with the Flask
application object. Add the three lines of code that are
needed in create_app() (in people_web_app/\__init__.py).

>Try running the Web application now. You should be able to
request the homepage from a browser.

### Task 6
>The people blueprint contains an empty method named
list_people() that is expected to handle requests for the entry
point /list. Complete the implementation of this method by
making a render_template() call and returning the generated
HTML page.

>In calling render template(), you'll need to specify that the
Web page should be generated by the list_people.html
template. This template expects to iterate over a collection of
Person objects to populate the resulting Web page. Note that
the repository is iterable, so you can simply pass the
repository as the value for the people parameter defined by
the list_people.html template. The variable repo_instance,
defined in the repository module, refers to the repository.

>Note too that since list people.html extends layout.html, and
layout.html defines two parameters, your call to
render_template() should include suitable values for the
parameters ???find_person_url and list_people_url that
list people.html inherits from layout.html.

>Try running the application and requesting the homepage
again. Now you should be able to click on the `List all leaders'
link and be presented with a Web page that lists all the
Person objects stored in the repository.
### Task 7 WTForms
>Make sure that you set the SECRET KEY variable correctly in
tasks 1 and 2.

>Edit the .env ???file to include variable
WTF_CSRF_SECRET_KEY and set it to an appropriate value.
You don't need to define this
variable in the config.Config class. It just needs to be loaded
into memory.
### Task 8
> Write a new subclass of WTForm named SearchForm.

> SearchForm should define two fields, an IntegerField, referred
to by attribute person id, and whose name/label is Person ID. This ???field is a mandatory field. The second field should be
a SubmitField, referred to by attribute submit and whose
name/label is Find.

>You should place this class declaration in the
people blueprint.py file.
### Task 9
>This template should be named find_person.html and should
extend layout.html

>The purpose of the form is to allow users to enter a person's
ID and then to post it to the Web app.

>  - The content block in find person.html should be overridden,
and include the following variables in Jinja expressions:  
>       - handler_url, the URL to post the form to.
>       - form.csrf_token, a hidden field that stores the form's csrf token.
>       - form.person id.label, the label associated with the person id
field.
>       - form.person id, the integer field used to type a person's ID.
>       - form.submit, the submit field.
### Task 10 View Method for find_person()
> All that remains is to 
esh out method find_person() in the
blueprint. Recall that all view methods that
handle requests to retrieve (GET) and process (POST) forms
follow the same pattern:
> - Instantiate a WTForm subclass.
> - Call validate_on_submit() on the form object. If this method
returns True, it means that the HTTP request is a POST and
any validation associated with the form has passed.

> For this Web app, you should write the few lines of code to:
> - Extract the POSTed ID value from the form by accessing the
form's person id.data attribute.
> - Query the repository for a Person whose ID matches the value
stored in person id.data.
> - Make a call to render template to generate a webpage that
either displays the Person (if found) or displays a message
saying that there is no match. Use the template you developed
in task 4, and provide values for the three named parameters:
find person_url, list_people_url, and person. Then, return the
generated HTML page.

> In cases where validate on submit() returns False, this means
that either the HTTP request is POST and validation failed,
or that the HTTP request is a GET for the bank form. In
either case, the form needs to be returned as the HTTP
response.

> For this Web app, you simply need to make a
render_template() call to generate the Web page containing
the form using the find person.html template you developed in
task 9. You should supply values for the four named
parameters: find_person_url, list_people_url, handler_url and
form.
