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

- **_require('express')_**: Returns a function reference. I have to use Node's **_require_** function to use the **express** module.

```js
const app = express();
```

- **_express();_**: Creates a object to start a new Express application.

```js
const port = process.env.PORT || 5000;
```

- Set a port number instead of 3000 which is already set as default.
- **process.env.PORT || 5000;**: In .env file, I already set a PORT number.

```js
require("dotenv").config();
```

- DotEnv is a lightweight npm package that automatically loads environment variables from a . env file into the process. env object.

```js
app.listen(port, console.log(`Server running on port ${port}`));
```

- **_app.listen(port number);_**: The app.listen() function is used to bind and listen the connections on the specified host and port.

### Set script in package.json

- Open the package.json -> "start": "node server/index.js" If I run **_start_** on the command, **_node server/index.js_** will be running.
- Open the package.json -> "dev": "nodemon server/index.js" If I run **_dev_** on the command, **_nodemon server/index.js_** will be running.

```js
app.use();
```

- app.use() is used to bind **application-level middleware** to an instance of the app object which is instantiated on the creation of the Express server (router. use() for **router-level middleware**)

```js
app.use(
  "/graphql",
  graphqlHTTP({
    schema,
    graphiql: process.env.NODE_ENV === "development",
  })
);
```

- I can use the express-graphql library to mount a GraphQL API server on the “/graphql” HTTP endpoint

```js
process.env.NODE_ENV === "development";
```

- === (Triple equals) is a strict equality comparison operator in JavaScript, which returns false for the values which are not of a similar type. This operator performs type casting for equality. If we compare 2 with “2” using ===, then it will return a false value.

- If process.env.NODE_ENV is 'development', true will be returned.

```js
const {projects, clients} = require('./sampleData.js')

-----In the sampleData.js------
const projects = [
  { ... },
  { ... },
  { ... },
];
const clients = [
  { ... },
  { ... },
  { ... },
];
```

The variables in the sampleData.js are put in projects and clients variables.

### Open graphql tool to test query

- localhost:5000/graphql

- To test type,

```js
{
	client(id: "2") {
    id,
    name,
    email,
    phone,
  }
}
// result
{
  "data": {
    "client": {
      "id": "2",
      "name": "Natasha Romanova",
      "email": "blackwidow@gmail.com",
      "phone": "223-567-3322"
    }
  }
}
```

### What is resolve() ?

```js
clients: {
      type: new GraphQLList(ClientType),
      resolve(parent, args){
        return clients;
      }
    }
```

- **resolve()**: Resolver is a collection of functions that generate response for a GraphQL query. In simple terms, a resolver acts as a GraphQL query handler

### Exclude .env file when committing

- Using .gitignore file -> Make a .gitignore file and enter .env
- Type command `git rm --cached .env` to stop tracking .env file

```js
const connectDB = async () => {};
```

### async() ?

- Asynchronous code allows the program to be executed immediately where the synchronous code will block further execution of the remaining code until it finishes the current one.

### Arrow function

```js
let func = (arg1, arg2, ..., argN) => expression;

Same with

let func = function(arg1, arg2, ..., argN) {
  return expression;
};
```

For example,

```js
let sum = (a, b) => {
  let result = a + b;
  return result;
};

//function expression
let age = prompt("What is your age?", 18);

let welcome = age < 18 ? () => alert("Hello!") : () => alert("Greetings!");

welcome();
```

### Connect to MongoDB

```js
const conn = await mongoose.connect(precess.env.MONGO_URI);
```

- I can connect to MongoDB with the mongoose.connect()

### colors

```js
console.log(`MongoDB Connected: ${conn.connection.host}`.cyan.underline.bold);
```

- cyan.underline.bold: The error log will be colored

### JSON Schema - enum

```js
const ProjectSchema = new mongoose.Schema({
  name: {
    type: String,
  },
  description: {
    type: String,
  },
  status: {
    type: String,
    enum: ["Not Started", "In progress", "Completed"],
  },
});
```

- I can define a set of values in a JSON Schema, but then in JSON data it takes only one of those values

# GraphQL Queries & Mutations

These are the GraphQL queries and mutations for the YouTube course.

## Get names of all clients

```
{
  clients {
    name
  }
}
```

## Get a single client name and email

```
{
  client(id: 1) {
    name
    email
  }
}
```

## Get name and status of all projects

```
{
  projects {
    name
    status
  }
}
```

## Get a single project name, description along with the client name and email

```
{
  project(id: 1) {
    name
    description,
    client {
      name
      email
    }
  }
}
```

## Create a new client and return all data

```
mutation {
  addClient(name: "Tony Stark", email: "ironman@gmail.com", phone: "955-365-3376") {
    id
    name
    email
    phone
  }
}
```

## Delete a client and return id

```
mutation {
  deleteClient(id: 1) {
    id
  }
}
```

## Create a new project and return name and description

```
mutation {
  addProject(name: "Mobile App", description: "This is the project description", status: "new", clientId: "1") {
   name
   description
  }
}
```

## Update a project status and return name and status

```
mutation {
  updateProject(status: "completed") {
   name
   status
  }
}
```

### To create a frond-end job

- Open another terminal and type `npx create-react-app client`
- React app is going to be installed in project-management folder

### For front-end, install several tools

```js
npm i @apollo/client graphql react-router-dom react-icons
```

- **@apollo/client**: Apollo Client is a fully-featured caching GraphQL client with integrations for React, Angular, and more. It allows you to easily build UI components that fetch data via GraphQL.

- **react-router-dom**: React Router DOM enables you to implement dynamic routing in a web app.
