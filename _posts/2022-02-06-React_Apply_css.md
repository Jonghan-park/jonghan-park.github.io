---
title: "React: Apply CSS"
header:
  image: /assets/ReactImage.jpg
categories:
  - React
tags:
  - React
  - CSS
---

This posting will show you how to apply CSS in four ways,
and this is what I learned applying CSS in react project so far.

## 1. Inline styling
```
class Counter extends Component {
  render() { 
    return (
        <div>
        <span style={{ fontSize: 10, backgroundColor: lightblue }} >Zero</span>
      </div>
    );
  }
}
 
export default Counter;
```
Notice that there are two curly braces in the tag. 
```
{{ fontSize: 10, backgroundColor: lightblue }}
```
To use CSS properties in react, You should change a CSS property name to **camel case** syntax.
ex) 
| CSS        | React     |
|------------|-----------|
| font-size  | fontSize  |
| font-weight| fontWeight|
| font-family| fontFamily|
| text-align | textAlign |


![Image install extention](/assets/cc2.png)