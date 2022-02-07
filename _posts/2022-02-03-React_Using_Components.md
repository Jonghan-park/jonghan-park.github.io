---
title: "React: Using components"
header:
  image: /assets/ReactImage.jpg
categories:
  - React
tags:
  - React
  - Components
---

#### This posting is going to explain how to use components in React.

```js
import React, { Component } from "react";

class Counter extends Component {
  render() { 
    return <h1>Hello world !</h1>
  }
}
 
export default Counter;
```
This is an **jsx** expression.

In the index.js, import Counter component

![Image import counter](/assets/importCounter.png)

You can see the result using react component.

![Image result hello world](/assets/resultHelloWorld.png)