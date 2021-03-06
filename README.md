# Node Express Handlebars

### Overview

This app is a burger logger with MySQL, Node, Express, Handlebars and a homemade ORM. For this app I followed the MVC design pattern; used Node and MySQL to query and route data in the app, and Handlebars to generate HTML.

- This is a restaurant app that lets users input the names of burgers they'd like to eat.

- Whenever a user submits a burger's name, the app will display the burger on the left side of the page -- waiting to be devoured.

- Each burger in the waiting area also has a `DEVOUR IT!` button. When the user clicks it, the burger will move to the right side of the page.

- If `DEVOUR IT!` button was pressed by accident the burger can be moved back by clicking on `BACK TO WAITING LIST!` button!

- The app will store every burger in a database, whether devoured or not.

## Instructions

#### Directory structure

The has the following structure:

```
.
├── config
│   ├── connection.js
│   └── orm.js
│ 
├── controllers
│   └── burgers_controller.js
│
├── db
│   ├── schema.sql
│   └── seeds.sql
│
├── models
│   └── burger.js
│ 
├── node_modules
│ 
├── package.json
│
├── public
│   └── assets
│       ├── css
│       │   └── burger_style.css
│       └── img
│           └── burger.png
│  
│
├── server.js
│
└── views
    ├── index.handlebars
    └── layouts
        └── main.handlebars
```

#### DB queries

1. The `db` folder has the following schema saved as `schema.sql` file:
2. The below can help re-creating db on a local computer:

```
     CREATE DATABASE burger_db;
     USE burger_db;

     CREATE TABLE burgers
     (
     id int NOT NULL
     AUTO_INCREMENT,
     name varchar
     (255) NOT NULL,
     eaten BOOLEAN DEFAULT false,
     PRIMARY KEY
     (id)
     );
```

3. In the `db` folder, file named `seeds.sql`. This file, inserts queries to populate the `burgers`:

```
   INSERT INTO burgers
   (name)
   VALUES
   ('Original');
   INSERT INTO burgers
   (name)
   VALUES
   ('Veggie');
   INSERT INTO burgers
   (name, eaten)
   VALUES
   ('Bacon', true);
   INSERT INTO burgers
   (name, eaten)
   VALUES
   ('Naked', true);
   INSERT INTO burgers
   (name, eaten)
   VALUES
   ('Chipotle', true);
   INSERT INTO burgers
   (name)
   VALUES
   ('Double');
```
