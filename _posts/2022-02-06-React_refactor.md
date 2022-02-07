---
title: "React: Refactor code"
header:
  image: /assets/ReactImage.jpg
categories:
  - React
tags:
  - React
  - Refactor
---

This is from counter app.
```js
render() {
    let classes = "bg m-2 bg-";
    classes += this.state.count === 0 ? "warning" : "primary";
    
    return (
      <div>
        <span className={ classes }>{this.formatCount()}</span>
        <button className="btn btn-secondary btn-sm">Increment</button>
      </div>
    );
  }
  ```
  If count is 0, warning badge will be using. Otherwise, primary badge will
show up. 

```js
let classes = "bg m-2 bg-";
classes += this.state.count === 0 ? "warning" : "primary";
```
These two lines can be encapsulated using refactor feature provided in IDE.

<video width="640" height="480" controls>
  <source src="/assets/Video/SimulateRefactor.mp4" type="video/mp4">
</video>

```js
 render() {
    
    return (
      <div>
        <span className={ this.getBadgeMethod() }>{this.formatCount()}</span>
        <button className="btn btn-secondary btn-sm">Increment</button>
      </div>
    );
  }

  getBadgeMethod() {
    let classes = "bg m-2 bg-";
    classes += this.state.count === 0 ? "warning" : "primary";
    return classes;
  }
```