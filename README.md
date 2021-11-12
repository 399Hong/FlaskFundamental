# Python 2

## Description

This is the repository for Python2 flask fundamental


## Installation

**Installation via requirements.txt**

```shell
$ cd COMPSCI-235
$ py -3 -m venv venv
$ venv\Scripts\activate
$ pip install -r requirements.txt

```

**Installation via requirements.txt(For macOS/Linux)**
```shell
$ cd COMPSCI-235
$ python3 -m venv venv
$ . venv/bin/activate
$ pip3 install -r requirements.txt
```

When using PyCharm, set the virtual environment using 'File'->'Settings' and select 'Project:COMPSCI-235' from the left menu. Select 'Project Interpreter', click on the gearwheel button and select 'Add'. Click the 'Existing environment' radio button to select the virtual environment. 

## Execution

**Running the application**

From the directory, and within the activated virtual environment (see *venv\Scripts\activate* above):

````shell
$ flask run
```` 

The homepage can be accessed from a Web browser:

http://127.0.0.1:5000/


### Task 1

> In the root directory of the project create a .env  le and set
the four key Flask con guration variables. (FLASK APP,
FLASK ENV, SECRET KEY, and TESTING) Hint: Flask
Environment Documentation
> Create a  le named con g.py in the root directory of the
project. Use dotenv to read the .env  le and to set the Flask
con guration variables in the Con g class. Hint: See con g.py
in Demo Project
> Assuming you have included FLASK ENV = `development',
the Web application is now con gured to dump exception
stack traces in the Web browser and to automatically reload
the application in the Web server in response to any source
code edits you make.
 
