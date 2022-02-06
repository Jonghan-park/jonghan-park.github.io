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

This posting will show you how to apply CSS in two ways,
and this is what I learned applying CSS in react project so far.
There are two ways more, but these two things I will be writing in this post is easiest way.

## 1. Inline styling
```
class Counter extends Component {
  render() { 
    return (
        <div>
        <span style={{ fontSize: 30, backgroundColor: "lightblue" }} >Zero</span>
      </div>
    );
  }
}
 
export default Counter;
```
Notice that there are two curly braces in the tag. 
```
{{ fontSize: 30, backgroundColor: "lightblue" }}
```
To use CSS properties in react, You should change a CSS property name to **camel case** syntax.
ex) 
| CSS        | React     |
|------------|-----------|
| font-size  | fontSize  |
| font-weight| fontWeight|
| font-family| fontFamily|
| text-align | textAlign |

Result:
![Image install extention](/assets/applyCSS1.png)

## 2. JavaScript Object
You can make object and refer to it in the style attribute
```
class Counter extends Component {
  render() { 
      const style = {
          fontSize: 50, 
          backgroundColor: "lightgreen"
      };
    return (
        <div>
        <span style={ this.style } >Zero</span>
      </div>
    );
  }
}
 
export default Counter;
```
Make object with styling information.
```
const style = {
          fontSize: 50, 
          backgroundColor: "lightgreen"
      };
```
And then, refer to it in the style attribute.
```
<span style={ this.style } >Zero</span>
```
Result:
![Image install extention](/assets/applyCSS2.png)

