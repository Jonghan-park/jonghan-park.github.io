---
title: "30 Days of Javascript 10 - Allow One Function Call"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
  - 30 days of Javascript
tags:
  - Leetcode
  - Javascript
---

Given a function fn, return a new function that is identical to the original function except that it ensures fn is called at most once.

The first time the returned function is called, it should return the same result as fn.
Every subsequent time it is called, it should return undefined.

Example 1:

Input: fn = (a,b,c) => (a + b + c), calls = [[1,2,3],[2,3,6]]
Output: [{"calls":1,"value":6}]
Explanation:
const onceFn = once(fn);
onceFn(1, 2, 3); // 6
onceFn(2, 3, 6); // undefined, fn was not called
Example 2:

Input: fn = (a,b,c) => (a _ b _ c), calls = [[5,7,4],[2,3,6],[4,6,8]]
Output: [{"calls":1,"value":140}]
Explanation:
const onceFn = once(fn);
onceFn(5, 7, 4); // 140
onceFn(2, 3, 6); // undefined, fn was not called
onceFn(4, 6, 8); // undefined, fn was not called

```js
/**
 * @param {Function} fn
 * @return {Function}
 */
var once = (fn) => {
  let called = false;

  return function (...args) {
    if (!called) {
      called = true;
      return fn(...args);
    } else {
      return undefined;
    }
  };
};

/**
 * let fn = (a,b,c) => (a + b + c)
 * let onceFn = once(fn)
 *
 * onceFn(1,2,3); // 6
 * onceFn(2,3,6); // returns undefined without calling fn
 */
```

The `once` function takes the original function (`fn`) as a parameter.
It initializes a `called` variable as `false` to keep track of whether the function has been called before.
The `once` function returns a new function that accepts any number of arguments using the rest parameter syntax (`...args`).
Inside the new function, it checks if `called` is `false`. If it is, it means the function hasn't been called before, so it sets `called` to `true` and calls the original function (`fn(...args)`) with the provided arguments.
After calling the original function, it returns the result.
If `called` is `true`, it means the function has been called before, so it returns `undefined`.
