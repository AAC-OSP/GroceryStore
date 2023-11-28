<h1 align = "center">
  <img src="https://i.imgur.com/HQmG6Nz.png">
</h1>

# Table of Contents
- [Introduction](#introduction) <br>
- [Requirements](#requirements) <br>
- [DB Schema Design](#db-schema-design) <br>
- [API Design](#api-design) <br>
- [Architecture and Features](#architecture-and-features) <br>
- [Documentation](#documentation) <br>
- [How to use](#how-to-use) <br>
- [Contribution](#contribution)

# Introduction
The objective of the project is to build a grocery store app with one app and multiple users using Flask framework and concepts of Modern Application Development – 1. Project deals with sqlite database to store grocery store data and user data. The name of the project **SmallBasket** inspired from BigBasket.

# Requirements
|||
|--|--|
| [Python 3.11.x](https://www.python.org/) | <img src="https://i.imgur.com/SBirLsy.png" style="width:135px; height:20px;" alt="python3.11.x">|
| [flask sql-alchemy](https://flask-sqlalchemy.palletsprojects.com/en/3.1.x/) | <img src="https://i.imgur.com/D3ITE2c.png" style="width:135px; height:20px;" alt="flasksqlalchemy">|
| [flask restful](https://flask-restful.readthedocs.io/en/latest/) | <img src="https://i.imgur.com/6I0mLHv.png" style="width:135px; height:20px;" alt="flaskrestful"> |
| [SQLite](https://www.sqlite.org/index.html) | <img src="https://i.imgur.com/zzHzq5w.png" style="width:135px; height:20px;" alt="SQLite">


# DB Schema Design
The app has SQLite named **database.sqlite3** database with 7 tables in the database folder. These tables store user and manager credentials, categories and products managers add, a table to keep track of user purchases, sales for managers and cart to keep track of user items.

|Table Name|Column Details|
|----------|--------------|
|managers|manager_id(integer, primary key), username(string), password(string)|
|users|user_id(integer, primary key), username(string), password(string), email(string)|
|categories|category_id(string, primary key), name(string), search(string)|
|products|product_id(string, primary key), category_id(string), name(string), search(string), price(numeric), stock(numeric), unit(string), fractal_allowed(string)|
|cart|cart_id(string, primary key), user_id(string), product_id(string_, quantity(numeric), unit(string), price(numeric)|
|sales|product_id(string, primary key), category_id(string), quantity(numeric), sale(numeric)|
|purchases|Transaction_id(string, primary key), user_id(string), price(numeric), date(string)|

# API Design
This application uses a total of 9 REST APIs to collect and process user data. All of the APIs use only **post** method as HTML does not support **put** and **delete** requests. The main tasks they take care of includes adding, editing and deleting of products and categories by managers, editing and deleting purchases of users and search feature. 

# Architecture and Features
The project starts with **start.sh** that is located in code folder(**GroceryStore folder). README file contains information on how to start the application. Database interactions are taken care by models, located in **models.py** in models folder and helper functions, located in **helpers.py** in Helpers folder. Database and **db.py** file which creates instance of SQLAlchemy reside in database folder. All the APIs reside in **api.py** of API folder. HTML and CSS files are in **templates** and **static** folders respectively. Controllers are in **app.py**

In the application only one manager exists. The manager can create categories which is empty by default, manager can add products under each category along with necessary information like stock, price etc. Manager is allowed to delete products and categories. If a non-empty category is deleted, all the products that belong to the category are also deleted. Users can see all the categories and products added by the managers in their respective dashboards. They can buy one quantity of any product by clicking **Add to cart** or add the quantity they like by selecting **Buy now**. All the products they buy among any category are displayed in cart as they are saved in cart table. In cart, they can edit and delete any purchase. 

# Documentation
insert link

# How to use
1. Clone this repo. <br>
- ```terminal
   git clone https://github.com/AAC-OSP/GroceryStore
   ```
1. Install the required libraries from [Requirements](#requirements) <br>
1. Execute the python script <br>
1. Add star to this repo if you liked it 😄
   
# Contribution 
**This section provides instructions and details on how to submit a contribution via a pull request. It is important to follow these guidelines to make sure your pull request is accepted.**
1. Before choosing to propose changes to this project, it is advisable to go through the readme.md file of the project to get the philosphy and the motive that went behind this project. The pull request should align with the philosphy and the motive of the original poster of this project.
2. To add your changes, make sure that the programming language in which you are proposing the changes should be same as the programming language that has been used in the project. The versions of the programming language and the libraries(if any) used should also match with the original code.
3. Write a documentation on the changes that you are proposing. The documentation should include the problems you have noticed in the code(if any), the changes you would like to propose, the reason for these changes, and sample test cases. Remember that the topics in the documentation is strictly not limited to the topics aforementioned, but are just an inclusion.
4. Submit a pull request via [Git etiquettes](https://gist.github.com/mikepea/863f63d6e37281e329f8) 



