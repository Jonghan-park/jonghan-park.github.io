---
title: "MERN project - A project Manager"
header:
  image: /assets/mern.png
categories:
  - MERN project
tags:
  - MERN
  - React
  - Node.js
  - Mongo DB
  - Express
---

# Mern Project - A project manager

### The project manager is for management of projects which user can add, view, edit and delete (CRUD functions) a project. This project is used React, bootstrap and apollo client for a front-end, GraphQL, Node.js and express-graphql for a server side, Mongo DB for a DATA side.

---

### Create a package.json file

To create a package.json, I need to run a command down below.

```js
npm init -y
```

Install express, express-graphql, graphql, mongoose, cors and colors

```js
npm i express express-graphql graphql mongoose cors colors
```

Install nodemon and dotenv

```js
npm i -D nodemon dotenv
```

### Explanation of each tool

- **_express_**: Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.

- **_express-graphql_**: The express-graphql module provides a simple way to create an Express server that runs a GraphQL API.

- **_graphql_**: GraphQL is a query language for APIs and a runtime for fulfilling those queries with your existing data.

- **_mongoose_**: Mongoose is a JavaScript object-oriented programming library that creates a connection between MongoDB and the Express web application framework.

- **_cors_**: CORS is a node.js package for providing a Connect/Express middleware that can be used to enable CORS with various options.

- **_colors_**: The Color node is a basic node that lets you change the color of your objects at any time in a non-destructive way. It only outputs color and does not have any inputs.

- **_nodemon_**: nodemon is a tool that helps develop Node.js based applications by automatically restarting the node application when file changes in the directory are detected.

- **_dotenv_**: Dotenv is a zero-dependency module that loads environment variables from a .env file into process.env

### Explanation for each line

```js
const express = require("express");
```

- **_require('express')_**: Returns a function reference. I have to use Node's **_require_** function to use the **\*express** module.

```js
const app = express();
```

- **_express();_**: Creates a object to start a new Express application.

```js
const port = process.env.PORT || 5000;
```

- Set a port number instead of 3000 which is already set as default.
- **_process.env.PORT || 5000;_**: In .env file, I already set a PORT number.
