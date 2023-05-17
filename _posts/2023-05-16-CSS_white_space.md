---
title: "How to get rid of extra white space from HTML CSS"
header:

categories:
  - HTML
  - CSS
tags:
  - CORS
  - HTML
  - Trouble shooting
---

# Problem

- I had a problem that I have some extra space when I open my web site.

# How to solve

- Set up default value for html and body tag.

```js
html,body {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}
```
