---
title: "Javascript - control flow"
header:
  image: /assets/javascript.png
categories:
  - Javascript
tags:
  - Javascript
---

## Control flow

`Control flow` in JavaScript refers to the order in which statements and instructions are executed in a program
It determines how the program flows from one statement to another based on conditions and decisions.

JavaScript provides several control flow structures:

1. Conditional Statements (if, else if, else): These statements allow you to execute different blocks of code based on whether a certain condition is true or false.

```js
if (condition) {
  // Code to execute if condition is true
} else if (anotherCondition) {
  // Code to execute if anotherCondition is true
} else {
  // Code to execute if none of the conditions are true
}
```

2. Switch Statement: The switch statement is used to perform different actions based on different conditions.

```js
switch (value) {
  case condition1:
    // Code to execute if value matches condition1
    break;
  case condition2:
    // Code to execute if value matches condition2
    break;
  default:
  // Code to execute if value doesn't match any condition
}
```

3. Loops (for, while, do-while): Loops allow you to execute a block of code repeatedly as long as a specified condition is true.

```js
for (let i = 0; i < array.length; i++) {
  // Code to execute in each iteration
}

while (condition) {
  // Code to execute while condition is true
}

do {
  // Code to execute at least once, then repeatedly as long as condition is true
} while (condition);
```

4. Logical Operators: Logical operators (AND &&, OR ||, NOT !) can be used to combine conditions and create more complex control flow structures.

```js
if (condition1 && condition2) {
  // Code to execute if both condition1 and condition2 are true
}

if (condition1 || condition2) {
  // Code to execute if either condition1 or condition2 is true
}

if (!condition) {
  // Code to execute if condition is false
}
```
