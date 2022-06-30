---
title: "MERN project - To do app"
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

## Create react app named client in the root project folder using create-react-app command

```js
npx create-react-app client
```

## Install modules in the api folder(npm init - first thing to do)

```js
npm install express mongoose cors
```

## app.use()

- The app.use() function adds a new middleware to the app.

## app.use(express.json());

- express.json() is a built in middleware function in Express starting from v4.16.0. It parses incoming JSON requests and puts the parsed data in req.body.
