# GroceryStore
Flask based Grocery e-commerce application


# Description 
The objective of the project is to build a grocery store app with one app and multiple users using Flask framework and concepts of Modern Application Development – 1. Project deals with sqlite database to store grocery store data and user data. The name of the project **SmallBasket** inspired from BigBasket.

# Technologies used
The main technologies used in this application are flask-sqlalchemy, flask-restful, SQLite and Python. **Flask-sqlalchemy** is used to interact with **SQLite** database that makes this application portable. **Flask-restful** is used to make REST APIs to handle inputs. **Jinja2** is used to create user interaction templates.

# DB Schema Design
The app has SQLite named **database.sqlite3** database with 7 tables in the database folder. These tables store user and manager credentials, categories and products managers add, a table to keep track of user purchases, sales for managers and cart to keep track of user items.

|Table Name|Column Details|
|----------|--------------|
|managsers|manager_id(integer, primary key), username(string), password(string)|

