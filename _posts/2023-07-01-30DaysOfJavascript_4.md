---
title: "30 Days of Javascript 4 - Counter2"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
  - 30 days of Javascript
tags:
  - Leetcode
  - Javascript
---

Write a function createCounter. It should accept an initial integer init. It should return an object with three functions.

The three functions are:

increment() increases the current value by 1 and then returns it.
decrement() reduces the current value by 1 and then returns it.
reset() sets the current value to init and then returns it.

Example 1:

Input: init = 5, calls = ["increment","reset","decrement"]
Output: [6,5,4]
Explanation:
const counter = createCounter(5);
counter.increment(); // 6
counter.reset(); // 5
counter.decrement(); // 4
Example 2:

Input: init = 0, calls = ["increment","increment","decrement","reset","reset"]
Output: [1,2,1,0,0]
Explanation:
const counter = createCounter(0);
counter.increment(); // 1
counter.increment(); // 2
counter.decrement(); // 1
counter.reset(); // 0
counter.reset(); // 0

```js
/**
 * @param {integer} init
 * @return { increment: Function, decrement: Function, reset: Function }
 */
var createCounter = function (init) {
  let num = init;
  return {
    increment: function () {
      num++;
      return num;
    },
    decrement: function () {
      num--;
      return num;
    },
    reset: function () {
      num = init;
      return num;
    },
  };
};

/**
 * const counter = createCounter(5)
 * counter.increment(); // 6
 * counter.reset(); // 5
 * counter.decrement(); // 4
 */
```

The `createCounter` function accepts an initial integer `init` as a parameter. It initializes a `num` variable to store the current value of the counter.

The `increment` function increments the `num` by 1 using the `++` operator and then returns the updated value.
The `decrement` function decrements the `num` by 1 using the `--` operator and then returns the updated value.
The `reset` function sets the `num` back to the initial value init and then returns it.
