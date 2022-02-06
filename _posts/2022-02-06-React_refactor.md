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
```
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

```
let classes = "bg m-2 bg-";
classes += this.state.count === 0 ? "warning" : "primary";
```
These two lines can be encapsulated using refactor feature provided in IDE.

![Image simulate refactor](/assets/Video/SimulateRefactor.mp4)