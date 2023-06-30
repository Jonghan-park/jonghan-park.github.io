---
title: "30 Days of Javascript 3 - To Be Or Not To Be"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
  - 30 days of Javascript
tags:
  - Leetcode
  - Javascript
---

Write a function expect that helps developers test their code. It should take in any value val and return an object with the following two functions.

toBe(val) accepts another value and returns true if the two values === each other. If they are not equal, it should throw an error "Not Equal".
notToBe(val) accepts another value and returns true if the two values !== each other. If they are equal, it should throw an error "Equal".

Example 1:

Input: func = () => expect(5).toBe(5)
Output: {"value": true}
Explanation: 5 === 5 so this expression returns true.
Example 2:

Input: func = () => expect(5).toBe(null)
Output: {"error": "Not Equal"}
Explanation: 5 !== null so this expression throw the error "Not Equal".
Example 3:

Input: func = () => expect(5).notToBe(null)
Output: {"value": true}
Explanation: 5 !== null so this expression returns true.

```js
/**
 * @param {string} val
 * @return {Object}
 */
var expect = function (val) {
  return {
    toBe: function (toVal) {
      if (val === toVal) {
        return true;
      } else {
        throw new Error("Not Equal");
      }
    },
    notToBe: function (notToVal) {
      if (val !== notToVal) {
        return true;
      } else {
        throw new Error("Equal");
      }
    },
  };
};
/**
 * expect(5).toBe(5); // true
 * expect(5).notToBe(5); // throws "Equal"
 */
```

This `expect` function takes in a value `val` and returns an object with two functions: `toBe` and `notToBe`.

The `toBe` function compares the value `val` with another value `toVal` using the strict equality operator (`===`). If the two values are equal, it returns `true`. Otherwise, it throws an error with the message `"Not Equal"`.

The `notToBe` function compares the value `val` with another value `notToVal` using the strict inequality operator (`!==`). If the two values are not equal, it returns an object with the value property set to `true`. Otherwise, it throws an error with the message `"Equal"`.
