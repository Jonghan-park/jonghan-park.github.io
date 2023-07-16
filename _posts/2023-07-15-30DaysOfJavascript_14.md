---
title: "30 Days of Javascript 14 - Execute Cancellable Function With Delay"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
  - 30 days of Javascript
tags:
  - Leetcode
  - Javascript
---

Given a function fn, an array or arguments args, and a timeout t in milliseconds, return a cancel function cancelFn.

After a delay of t, fn should be called with args passed as parameters unless cancelFn was called first. In that case, fn should never be called.

Example 1:

Input: fn = (x) => x _ 5, args = [2], t = 20
Output: [{"time": 20, "returned": 10}]
Explanation:
const cancelTime = 50
const cancel = cancellable((x) => x _ 5, [2], 20); // fn(2) called at t=20ms
setTimeout(cancel, cancelTime);

The cancellation was scheduled to occur after a delay of cancelTime (50ms), which happened after the execution of fn(2) at 20ms.
Example 2:

Input: fn = (x) => x**2, args = [2], t = 100
Output: []
Explanation:
const cancelTime = 50
const cancel = cancellable((x) => x**2, [2], 100); // fn(2) not called
setTimeout(cancel, cancelTime);

The cancellation was scheduled to occur after a delay of cancelTime (50ms), which happened before the execution of fn(2) at 100ms, resulting in fn(2) never being called.
Example 3:

Input: fn = (x1, x2) => x1 _ x2, args = [2,4], t = 30
Output: [{"time": 30, "returned": 8}]
Explanation:
const cancelTime = 100
const cancel = cancellable((x1, x2) => x1 _ x2, [2,4], 30); // fn(2,4) called at t=30ms
setTimeout(cancel, cancelTime);

The cancellation was scheduled to occur after a delay of cancelTime (100ms), which happened after the execution of fn(2,4) at 30ms.

```js
/**
 * @param {Function} fn
 * @param {Array} args
 * @param {number} t
 * @return {Function}
 */
var cancellable = function (fn, args, t) {
  const timeOut = setTimeout(() => {
    fn(...args);
  }, t);
  return function () {
    clearTimeout(timeOut);
  };
};

/**
 *  const result = []
 *
 *  const fn = (x) => x * 5
 *  const args = [2], t = 20, cancelT = 50
 *
 *  const start = performance.now()
 *
 *  const log = (...argsArr) => {
 *      const diff = Math.floor(performance.now() - start);
 *      result.push({"time": diff, "returned": fn(...argsArr))
 *  }
 *
 *  const cancel = cancellable(log, args, t);
 *
 *  const maxT = Math.max(t, cancelT)
 *
 *  setTimeout(() => {
 *     cancel()
 *  }, cancelT)
 *
 *  setTimeout(() => {
 *     console.log(result) // [{"time":20,"returned":10}]
 *  }, maxT + 15)
 */
```

Inside the function, a `setTimeout` is used to execute the `fn` function after a specified delay of `t` milliseconds. The `fn` function is called with the provided `args` as arguments.

The `setTimeout` function returns a timer identifier, which is stored in the `timeOut` variable.

Finally, the `cancellable` function returns another function that can be used to cancel the previously scheduled timeout by calling `clearTimeout` with the `timeOut` identifier.
