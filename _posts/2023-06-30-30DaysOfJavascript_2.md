---
title: "30 Days of Javascript 2 - Counter"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
  - 30 days of Javascript
tags:
  - Leetcode
  - Javascript
---

Given an integer n, return a counter function. This counter function initially returns n and then returns 1 more than the previous value every subsequent time it is called (n, n + 1, n + 2, etc).

Example 1:

Input:
n = 10
["call","call","call"]
Output: [10,11,12]
Explanation:
counter() = 10 // The first time counter() is called, it returns n.
counter() = 11 // Returns 1 more than the previous time.
counter() = 12 // Returns 1 more than the previous time.
Example 2:

Input:
n = -2
["call","call","call","call","call"]
Output: [-2,-1,0,1,2]
Explanation: counter() initially returns -2. Then increases after each sebsequent call.

```js
/**
 * @param {number} n
 * @return {Function} counter
 */
var createCounter = function (n) {
  return function () {
    return n++;
  };
};

/**
 * const counter = createCounter(10)
 * counter() // 10
 * counter() // 11
 * counter() // 12
 */
```

The `counter` function takes an integer `n` as input and returns a new function. The returned function, when invoked, increments `n` by 1 and returns the updated value. In the example usage, an array `calls` contains the string "call" for each invocation. The counter function is called `n` number of times, and each time it is called, the returned value is pushed into the `result` array.
