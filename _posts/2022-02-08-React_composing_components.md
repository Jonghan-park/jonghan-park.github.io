---
title: "React: Composing Components"
header:
  image: /assets/ReactImage.jpg
categories:
  - React
tags:
  - React
  - Composing
---

# Composing components

I can use component made in previous blog's posting named Counter. 
It's like a assembling a robot. Let's get into it.

![Image import counter](/assets/folder_counter.png)

We already have a Counter component underneath components folder.
I'm going to add another component named Counters which is going to render a list of counter.

![Image import counter](/assets/folder_counters.png)

In the index.js, 

#### Before
```js
import Counter from './components/counter';

ReactDOM.rende(
  <Counter />,
  document.getElementById('root')
);
```
I'm going to import our new component named **Counters** and render **Counters**.
#### After
```js
import Counter from './components/counter';

ReactDOM.rende(
  <Counter />,
  document.getElementById('root')
);
```