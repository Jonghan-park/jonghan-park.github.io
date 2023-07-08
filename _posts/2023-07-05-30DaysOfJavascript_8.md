---
title: "30 Days of Javascript 8  - Function Composition"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
  - 30 days of Javascript
tags:
  - Leetcode
  - Javascript
---

Given an array of functions [f1, f2, f3, ..., fn], return a new function fn that is the function composition of the array of functions.

The function composition of [f(x), g(x), h(x)] is fn(x) = f(g(h(x))).

The function composition of an empty list of functions is the identity function f(x) = x.

You may assume each function in the array accepts one integer as input and returns one integer as output.

Example 1:

Input: functions = [x => x + 1, x => x * x, x => 2 * x], x = 4
Output: 65
Explanation:
Evaluating from right to left ...
Starting with x = 4.
2 _ (4) = 8
(8) _ (8) = 64
(64) + 1 = 65
Example 2:

Input: functions = [x => 10 * x, x => 10 * x, x => 10 * x], x = 1
Output: 1000
Explanation:
Evaluating from right to left ...
10 _ (1) = 10
10 _ (10) = 100
10 \* (100) = 1000
Example 3:

Input: functions = [], x = 42
Output: 42
Explanation:
The composition of zero functions is the identity function

```js
/**
 * @param {Function[]} functions
 * @return {Function}
 */
var compose = function (functions) {
  if (functions.length === 0) {
    return (x) => x; // Identity function
  }

  return functions.reduceRight((prevFn, nextFn) => {
    return (x) => nextFn(prevFn(x));
  });
};

/**
 * const fn = compose([x => x + 1, x => 2 * x])
 * fn(4) // 9
 */
```

The `reduceRight` method progressively composes the functions, starting from the rightmost function and moving towards the leftmost function.
