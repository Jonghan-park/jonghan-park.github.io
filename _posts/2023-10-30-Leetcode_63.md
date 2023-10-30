---
title: "Leetcode problem 63 - Find Maximum Number of String Pairs"
header:
  image: /assets/leetcode.png
categories:
  - Leetcode
tags:
  - Leetcode
---

You are given a 0-indexed array words consisting of distinct strings.

The string words[i] can be paired with the string words[j] if:

The string words[i] is equal to the reversed string of words[j].
0 <= i < j < words.length.
Return the maximum number of pairs that can be formed from the array words.

Note that each string can belong in at most one pair.

Example 1:

Input: words = ["cd","ac","dc","ca","zz"]
Output: 2
Explanation: In this example, we can form 2 pair of strings in the following way:

- We pair the 0th string with the 2nd string, as the reversed string of word[0] is "dc" and is equal to words[2].
- We pair the 1st string with the 3rd string, as the reversed string of word[1] is "ca" and is equal to words[3].
  It can be proven that 2 is the maximum number of pairs that can be formed.
  Example 2:

Input: words = ["ab","ba","cc"]
Output: 1
Explanation: In this example, we can form 1 pair of strings in the following way:

- We pair the 0th string with the 1st string, as the reversed string of words[1] is "ab" and is equal to words[0].
  It can be proven that 1 is the maximum number of pairs that can be formed.
  Example 3:

Input: words = ["aa","ab"]
Output: 0
Explanation: In this example, we are unable to form any pair of strings.

```js
/**
 * @param {string[]} words
 * @return {number}
 */
var maximumNumberOfStringPairs = function (words) {
  let hash = {};
  let count = 0;

  for (let i = 0; i < words.length; i++) {
    if (words[i] in hash) {
      count++;
    } else {
      let reversed = words[i].split("").reverse().join("");
      hash[reversed] = count;
    }
  }
  return count;
};
```

Initialize an empty object `hash` to store reversed words as keys and an initial count of 0.

Initialize a `count` variable to keep track of the number of string pairs.

Use a `for` loop to iterate through the `words` array.

For each word in the array:

a. Check if the word exists as a key in the `hash` object using `if (words[i] in hash)`. If it does, it means that a reversed version of this word has already been encountered, so increment the `count` variable.

b. If the word is not found in `hash`, it means there's no reversed version of this word encountered so far. Create the reversed version of the word by splitting it into an array of characters, reversing the array using `reverse()`, and then joining the characters back into a string using `join('')`. Store the reversed word in the `hash` object with the count as its value. This is done to keep track of the occurrence of reversed words for future comparisons.

After iterating through all the words in the array, the `count` variable will hold the number of string pairs where a word and its reversed version exist in the array.

Return the `count` as the result.

The time complexity of the `maximumNumberOfStringPairs` function is O(n \* m), where 'n' is the number of words in the input array `words`, and 'm' is the average length of the words in the array.
