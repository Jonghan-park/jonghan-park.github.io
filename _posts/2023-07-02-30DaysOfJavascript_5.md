---
title: "30 Days of Javascript 5 - Apply Transform Over Each Element in Array"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
  - 30 days of Javascript
tags:
  - Leetcode
  - Javascript
---

Given an integer array arr and a mapping function fn, return a new array with a transformation applied to each element.

The returned array should be created such that returnedArray[i] = fn(arr[i], i).

Please solve it without the built-in Array.map method.

Example 1:

Input: arr = [1,2,3], fn = function plusone(n) { return n + 1; }
Output: [2,3,4]
Explanation:
const newArray = map(arr, plusone); // [2,3,4]
The function increases each value in the array by one.
Example 2:

Input: arr = [1,2,3], fn = function plusI(n, i) { return n + i; }
Output: [1,3,5]
Explanation: The function increases each value by the index it resides in.
Example 3:

Input: arr = [10,20,30], fn = function constant() { return 42; }
Output: [42,42,42]
Explanation: The function always returns 42.

```js
/**
 * @param {number[]} arr
 * @param {Function} fn
 * @return {number[]}
 */
var map = function (arr, fn) {
  let returnedArray = [];
  for (let i = 0; i < arr.length; i++) {
    returnedArray[i] = fn(arr[i], i);
  }
  return returnedArray;
};
```

Inside the `map` function, a new array called `returnedArray` is declared to store the results of applying the callback function to each element of the original array.
A `for` loop is used to iterate over each element of the `arr` array.
Within each iteration of the loop, the callback function `fn` is called with two arguments: the current element of the `arr` array (`arr[i]`) and the index of that element (`i`).
The result of the callback function is assigned to the corresponding index of the `returnedArray`.
After iterating over all elements of the `arr` array, the `returnedArray` is returned as the result of the `map` function.
