---
title: "30 Days of Javascript 6 - Array Reduce Transformation"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
  - 30 days of Javascript
tags:
  - Leetcode
  - Javascript
---

Given an integer array arr and a filtering function fn, return a filtered array filteredArr.

The fn function takes one or two arguments:

arr[i] - number from the arr
i - index of arr[i]
filteredArr should only contain the elements from the arr for which the expression fn(arr[i], i) evaluates to a truthy value. A truthy value is a value where Boolean(value) returns true.

Please solve it without the built-in Array.filter method.

Example 1:

Input: arr = [0,10,20,30], fn = function greaterThan10(n) { return n > 10; }
Output: [20,30]
Explanation:
const newArray = filter(arr, fn); // [20, 30]
The function filters out values that are not greater than 10
Example 2:

Input: arr = [1,2,3], fn = function firstIndex(n, i) { return i === 0; }
Output: [1]
Explanation:
fn can also accept the index of each element
In this case, the function removes elements not at index 0
Example 3:

Input: arr = [-2,-1,0,1,2], fn = function plusOne(n) { return n + 1 }
Output: [-2,0,1,2]
Explanation:
Falsey values such as 0 should be filtered out

```js
/**
 * @param {number[]} arr
 * @param {Function} fn
 * @return {number[]}
 */
var filter = function (arr, fn) {
  let newArray = [];
  for (let i = 0; i < arr.length; i++) {
    if (fn(arr[i], i)) {
      newArray.push(arr[i]);
    }
  }
  return newArray;
};
```

The `filter` function takes two parameters: `arr`, which is the original array, and `fn`, which is the callback function.
Inside the `filter` function, a new array called `newArray` is declared to store the filtered elements.
A `for` loop is used to iterate over each element of the `arr` array.
Within each iteration of the loop, the callback function `fn` is called with two arguments: the current element of the `arr` array (`arr[i]`) and the index of that element (`i`).
The result of the callback function is checked with an `if` statement. If the result is truthy (e.g., true, a non-zero number, a non-empty string), the current element is pushed into the `newArray`.
After iterating over all elements of the `arr` array, the `newArray` is returned as the result of the `filter` function.
