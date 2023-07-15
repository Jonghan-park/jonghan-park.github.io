---
title: "30 Days of Javascript 13 - Sleep"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
  - 30 days of Javascript
tags:
  - Leetcode
  - Javascript
---

Given a positive integer millis, write an asynchronous function that sleeps for millis milliseconds. It can resolve any value.

Example 1:

Input: millis = 100
Output: 100
Explanation: It should return a promise that resolves after 100ms.
let t = Date.now();
sleep(100).then(() => {
console.log(Date.now() - t); // 100
});
Example 2:

Input: millis = 200
Output: 200
Explanation: It should return a promise that resolves after 200ms.

```js
/**
 * @param {number} millis
 */
async function sleep(millis) {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve();
    }, millis);
  });
}

/**
 * let t = Date.now()
 * sleep(100).then(() => console.log(Date.now() - t)) // 100
 */
```

The function returns a promise, which will resolve after the specified delay. Inside the promise's executor function, `setTimeout` is used to introduce the desired delay. Once the timeout completes, the promise is resolved by calling `resolve()`, indicating that the sleep operation has finished.
