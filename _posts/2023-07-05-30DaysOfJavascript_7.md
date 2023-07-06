---
title: "30 Days of Javascript 7  -  Array Reduce Transformation"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
  - 30 days of Javascript
tags:
  - Leetcode
  - Javascript
---

Given an integer array nums, a reducer function fn, and an initial value init, return a reduced array.

A reduced array is created by applying the following operation: val = fn(init, nums[0]), val = fn(val, nums[1]), val = fn(val, nums[2]), ... until every element in the array has been processed. The final value of val is returned.

If the length of the array is 0, it should return init.

Please solve it without using the built-in Array.reduce method.

Example 1:

Input:
nums = [1,2,3,4]
fn = function sum(accum, curr) { return accum + curr; }
init = 0
Output: 10
Explanation:
initially, the value is init=0.
(0) + nums[0] = 1
(1) + nums[1] = 3
(3) + nums[2] = 6
(6) + nums[3] = 10
The final answer is 10.
Example 2:

Input:
nums = [1,2,3,4]
fn = function sum(accum, curr) { return accum + curr \* curr; }
init = 100
Output: 130
Explanation:
initially, the value is init=100.
(100) + nums[0]^2 = 101
(101) + nums[1]^2 = 105
(105) + nums[2]^2 = 114
(114) + nums[3]^2 = 130
The final answer is 130.
Example 3:

Input:
nums = []
fn = function sum(accum, curr) { return 0; }
init = 25
Output: 25
Explanation: For empty arrays, the answer is always init.

```js
/**
 * @param {number[]} nums
 * @param {Function} fn
 * @param {number} init
 * @return {number}
 */
var reduce = function (nums, fn, init) {
  let curVal = init;
  for (let i = 0; i < nums.length; i++) {
    curVal = fn(curVal, nums[i]);
  }
  return curVal;
};
```

The `reduce` function takes three parameters: `nums`, which is the array to be reduced, `fn`, which is the callback function, and `init`, which is the initial value.
Inside the `reduce` function, a variable `curVal` is declared and assigned the value of `init`. This variable will hold the accumulated value during the reduction process.
A `for` loop is used to iterate over each element of the `nums` array.
Within each iteration of the loop, the callback function fn is called with two arguments: the current accumulated value (`curVal`) and the current element of the `nums` array (`nums[i]`).
The result of the callback function is assigned to the `curVal` variable, overwriting the previous accumulated value.
After iterating over all elements of the `nums` array, the final accumulated value (`curVal`) is returned as the result of the `reduce` function.
