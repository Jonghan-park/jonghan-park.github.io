---
title: "Javascript Promise"
header:
  image: /assets/javascript.png
categories:
  - Javascript
tags:
  - Javascript
  - Promise
---

## Promise

### What is promise?

Promises provide a way to manage and handle asynchronous tasks in a more organized and structured manner, ensuring that you can work with the result of an operation only when it's available and handle errors if something goes wrong.

Promises are used to wrap asynchronous tasks such as making network requests, reading files, or querying a database. They provide a clean syntax for handling the success or failure of these asynchronous operations.

A promise has three states:

1. **Pending**: The initial state when the asynchronous operation is still in progress and has not yet resolved.

2. **Fulfilled**: The state when the asynchronous operation successfully completes, and the promise resolves with a value. Once fulfilled, the promise is considered "settled," and its associated value is available.

3. **Rejected**: The state when the asynchronous operation encounters an error or fails to complete. Once rejected, the promise is considered "settled," and the reason for rejection (an error or failure message) is available.

> A promise in JavaScript is an object representing the eventual completion or failure of an asynchronous operation, allowing for more organized and controlled handling of the operation's result.

# How to create Promise object

```js
const success = true;
const myPromise = new Promise((myResolve, myReject) => {
  if (success) {
    const data = {
      name: "Joseph",
      age: 30,
    };
    myResolve(data);
  } else {
    myReject("Cannot pass the data");
  }
});
```

# How to use Promise object

```js
myPromise
  .then((value) => {
    console.log(value.name);
  })
  .catch((err) => {
    console.log(err);
  });
```
