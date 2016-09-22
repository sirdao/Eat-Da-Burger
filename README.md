Week of 14 Homework Node Express Handlebars

Introduction

You will create a burger logger with a homemade ORM (yum!), MySQL, Node, Express, handlebars using the MVC design pattern.

You will use Handlebars to generate HTML.

You will use Node to connect to your MySQL database and Express to handle routing.

see demonstration of how it works

App Summary

Eat-Da-Burger! is a fun app that lets a user input the name of a burger they want to eat.

Once submitted, the burger is displayed in text on the left side of the page where it's waiting to be devoured.

Each burger in the waiting area also has a Devour it! button. Once clicked, the burger will move to the right side of the page.

Every burger entered is stored in the database.

Remember

You will be fully capable of doing this homework by the end of Saturday's class.

Setup and steps

This is how your homework should look like when done:

Watch the demonstration of how this app works with this file in the repo: burger_demo.mp4
App setup:

1. Create an app directory called `burger`

2. Make a package.json file by running `npm init` from the command line

3. Install the Express npm package: `npm install express --save`

4. Create a server.js file

5. Install the handlebars npm package `npm install express-handlebars --save`

6. Install the method-override npm package `npm install method-override --save`

7. Install the body-Parser npm package `npm install body-parser --save`

8. Install MySQL npm package `npm install mysql --save`

10. Require the following npm packages inside of the server.js file
* express
* method-override
* body-parser

var express = require('express');
var methodOverride = require('method-override');
var bodyParser = require('body-parser');
DB Setup:

Part One

    1. In App Setup step 8 you installed MySQL with `npm install mysql --save`

    2. Inside your `burger` directory, create a directory named `db`

    3. In the db folder, Create a file named `schema.sql` to store your SQL commands for creating your database

    4. Write SQL so that it does the following things to create the database in a `schema.sql` file

        * Create the `burgers_db`
        * Switch to or use the `burgers_db`
        * Create a `burgers` table with the following fields
            * `id` as int that is the primary key and auto incrementing
            * `burger_name` as a string
            * `devoured` as a boolean
            * `date` as TIMESTAMP

    5. In the db folder, create a `seeds.sql` file

    6. Create SQL insert queries inside of the `seeds.sql` file to populate the `burgers` table with data. Create 3 burgers to start off your application.

    7. Run the `schema.sql` and `seeds.sql` files into the mysql server from the command line

    8. Navigate to the db folder in this app to run the queries that you created in the previous steps.

    9. Start MySQL command line tool get into mysql.
    You'll need to login while starting MySQL command line tool
    `mysql -uroot -p1111`

    10. When inside the `mysql>` command line tool run the command `source schema.sql` - this will make the database and the table inside of it
    11. Insert the default data by running `source seeds.sql`
    12. Get out of `mysql>` by typing and executing `exit`
Config Setup:

1. Inside your `burger` directory create a directory named `config`

2. Create a `connection.js` file inside `config` directory

    3. Inside the `connection.js` setup the code to connect Node to MySQL

    4. Export the connection

5. Create an `orm.js` file inside `config` directory

    6. Import (require) `connection.js` into `orm.js`

    7. Inside the `orm.js` file create the methods that will execute MySQL commands necessary in the controllers. `selectAll()`, `insertOne()`, `updateOne()` are the methods you will need to use inside the app and in order to retrieve and store data in your database.

    8. Export the orm object in `module.exports`
Model setup:

1. Inside your `burger` directory create a directory named `models`

    2. Create a `burger.js` file.

        3. Inside `burger.js`, import `orm.js` into `burger.js`

        4. Inside `burger.js` create the code that will call the orm functions using burger specific input for the orm

        5. Export at the end of the `burger.js` file
Controller setup:

1. Inside your `burger` directory create a directory named `controllers`

2. Create the `burgers_controller.js` file

3. Inside `burgers_controller.js` file import (require)
    * express
    * method-override
    * body-parser

    var express = require('express');
    var methodOverride = require('method-override');
    var bodyParser = require('body-parser');

    4. Create the `router` for the app, and export the `router` at the end
View setup:

1. Inside your `burger` directory create a directory named `views`

2. Create the `index.handlebars` file inside `views` directory

3. Create the `layouts` directory inside `views` directory

4. Create the `main.handlebars` file inside `layouts` directory

5. Setup the `main.handlebars` file so it's able to be used by Handlebars

6. Setup the `index.handlebars` to have the template that Handlebars can render onto

7. Create a button in `index.handlebars` that will submit the user input into the database
Directory structure: All the recommended files and directories from the steps above should look like the following structure...     ├── config │   ├── connection.js │   └── orm.js ├── controllers │   └── burgers_controller.js ├── db │   ├── schema.sql │   └── seeds.sql ├── models │   └── burger.js ├── node_modules ├── package.json ├── public │   ├── assets │   │   ├── css │   │   │   └── burger_style.css │   │   └── img │   │   └── burger.png │   └── test.html ├── server.js └── views ├── index.handlebars └── layouts └── main.handlebars 

Copyright

Coding Boot Camp (C) 2016. All Rights Reserved.