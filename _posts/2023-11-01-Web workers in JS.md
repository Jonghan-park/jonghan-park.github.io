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

Web workers are designed to let me do any time-consuming job in the background. Javascript is single thread, so if a browser takes something long to get data, user can't do anything on the web page such as unable to click other functions.

Web workers are ideal for offloading heavy tasks from the main thread. They run independently and don't block the UI. However, they can't directly access the DOM of certain browser APIs.

Don't manipulate DOM !!

I can run some code inside of workers with some exception.

# Common examples of web workers

- Dashboard pages that display real-time data such as stock prices, real-time active users
- Fetching huge files from the server
- Autosave functionality
- Processing multimedia (audio and video)
- Filtering images in a canvas

# How to implement workers

```js
const worker = new Worker("workers.js");
```

`Worker` is an API interface that you can create a thread in the background. `workers.js` will be executed by API.
I can call the `Worker()` constructor to create a new worker.

# Sending message to and from a worker

`postMessage()` can be used sending message to main thread or workers(vice versa)

```js
// main.js
worker.postMessage("start");
```

In the main script, I can use `addEventListener` method to listen to `message` from `worker`. I can get data from worker. I also can use `onmessage` method to listen to `message`. `self.addEventListener("message", ...)` is more flexible when you need to set up multiple event listeners for different types of messages in a worker, while `self.onmessage` is a simpler approach when you only need one message handler in the worker. The choice between them depends on your specific use case and how you want to structure your worker's message handling logic.

```js
// main.js
worker.addEventListener(
  "message",
  function (e) {
    console.log("Worker said: ", e.data);
  },
  false
);

worker.onmessage = function (e) {
  console.log("Worker said: ", e.data);
};
```

In the worker script, I can send message to `main` script by using `postMessage()`.

```js
// worker.js
self.addEventListener(
  "message",
  function (e) {
    self.postMessage(e.data);
  },
  false
);

self.onmessage = function (e) {
  self.postMessage(e.data);
};
```

# Terminate workers

If I need to terminate the worker, I can use `terminate` method to terminate a running worker from the main thread.

```js
worker.terminate();
```
