---
title: "Web workers in JS "
header:
  image: /assets/leetcode.png
categories:
  - Javascript
tags:
  - web worker, Javascript
---

# Web workers

Web workers are designed to let you do any time-consuming job in the background. Javascript is single thread, so if a browser takes something long to get data, user can't do anything on the web page such as unable to click other functions.

Web workers are ideal for offloading heavy tasks from the main thread. They run independently and don't block the UI. However, they can't directly access the DOM of certain browser APIs.

Don't manipulate DOM !!

I can run some code inside of workers with some exception.

# Common examples of web workers

- Dashboard pages that display real-time data such as stock prices, real-time active users, and so on
- Fetching huge files from the server
- Autosave functionality

# How to implement workers

```js
const worker = new Worker("workers.js");
```

`Worker` is an API interface that you can create a thread in the background. `workers.js` will be executed by API.
