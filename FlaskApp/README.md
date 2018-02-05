# Item Catalog Web App

The item catalog provides a list of items within a variety of categories that can also be created. Editing any of the applications requires you to register and login into the site. 

# Accessing the website

You are able to visit and utilize the site by going to ```http://54.95.11.13```

# Database Setup

The Item Catalog Databse is set up with Postgresql, utilizing the SQLAlchemy library.  The name of the Database is itemcatalog and has a single user named catalog that connects to the database, with permissions to Add Tables and alter the data withn those tables. 

# Server Security Features

The server is placed securely on a LightSale AWS server running Ubuntu 16.04. LightSale has it's own firewall, with an additional firewall installed on linux called ufw. All ports have been disabled on both firewalls, with the exception of any ports needed.  

The SSH default port 22 has also been disabled, now only allowing port 2200. 

Additionally, anyone accessing the server via SSH is required to have a Linux account set up and is only allowed to access the server with RSA key encryption. accessing the server with only a username and password has been disabled.

# Accessing the Server via Shell

Using an SSH application of your preference, you will need to do the following to connect: 

* Use ```54.95.11.13``` as the server address
* Make sure you use port 2200 when accessing the server via SSH
* You will need an RSA Key to access, please contact the administrator at chadbrooks80@gmail.com to receive. 


# Applications Configured

The Server has the following applications installed:

* Apache2: Apache has been configured to route all users to accessing the root directory to the Python Flask Application
* Web Server Gateway Interface: this is a package that allows Apache to run the Python Flask web application.
* Pyhon 2.7.12: Python is called by utilized used to run the Flask Server remotely
* PostgreSQL: this is the database that is configured within the Flask Application, utilizing SQLAlchemy.

In addition to the software packges listed above, the Item Catalog web server also uses a good number of python libraries, with Flask and SQLAlchemy being the core libraries utilized within the Python application. 

## Files used within the the Item Catalog App

This App has three main python files, including: 
* \_\_init\_\_.py
this is the main file that is used for running the app with the rest of the python files being utlized as libraries. To run the Item Catalog App, you need to have Python 2 installed and run the following command from the terminal: 

`python views.py`

* models.py
This file is used to configure the the database using SqlAlchemy`. The Item Catalog App uses sqllite as its database and has three main tables:

    1. Users - holds the user information with hashed passwords for security
    2. Categories - holds the category information
    3. Items - holds the items created for each category

* authenticate.py
this file holds one main function imported into the views.py: `login_required`.  This file is used as a decorator to any specific routes within this application to ensure users are logged in to perform specific tasks, including adding, editing, and deleting any categories or items. 

There are a large number of html template files utilized within the templates folder, along with any other static files needed, which includes style.css and a couple of image files used. 

## JSON Endpoints

The Item Catalog app also includes a json endpoint that allows users to retreive all categories and items stored in JSON format.  Anyone accessing this file must be registered and logged in. to access this JSON endpoint, use the following path: 

`/catalog.json`

## Suported Python Versions

Log Analysis Application has been tested and working on Python version 2.

## Licensing
`Item Catalog` is a public domain work, dedicated using [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Feel free to do whatever you want with it.