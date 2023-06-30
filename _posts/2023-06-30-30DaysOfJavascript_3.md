---
title: "30 Days of Javascript 1 - Create Hello World Function"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
  - 30 days of Javascript
tags:
  - Leetcode
  - Javascript
---

Write a function createHelloWorld. It should return a new function that always returns "Hello World".

Example 1:

Input: args = []
Output: "Hello World"
Explanation:
const f = createHelloWorld();
f(); // "Hello World"

The function returned by createHelloWorld should always return "Hello World".
Example 2:

Input: args = [{},null,42]
Output: "Hello World"
Explanation:
const f = createHelloWorld();
f({}, null, 42); // "Hello World"

Any arguments could be passed to the function but it should still always return "Hello World".

```js
/**
 * @return {Function}
 */
var createHelloWorld = function () {
  return function (...args) {
    return "Hello World";
  };
};

/**
 * const f = createHelloWorld();
 * f(); // "Hello World"
 */
```

In this code snippet, `const f = createHelloWorld();` invokes the `createHelloWorld()` function and assigns the returned function to the variable `f`. The variable `f` now holds the returned function.

When `f()` is called, it executes the inner function that was returned by `createHelloWorld()`. The inner function does not accept any arguments (`...args` allows for any number of arguments to be passed, but it is not used in the function). It simply returns the string "Hello World".
