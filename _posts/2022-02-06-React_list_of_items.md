---
title: "React: Render list of items"
header:
  image: /assets/ReactImage.jpg
categories:
  - React
tags:
  - React
  - List of items
  - array
---

## How to render list of items in React

I can use the map() function to list items.
I'll use the code generated while doing counter app project.

```js
state = {
      count: 0
      items: ['item1', 'item2', 'item3']
   };

  render() {
    
    return (
      <div>
        <span className={ this.getBadgeMethod() }>{this.formatCount()}</span>
        <button className="btn btn-secondary btn-sm">Increment</button>
        <ul>
            { this.state.items.map(item => <li>{ item }</li>)}
        </ul>
      </div>
    );
  }
  ```
  In this code, we have an array which has three items named **items**

  ```js
  { this.state.items.map(item => <li>{ item }</li>)}
  ```
Each item map it to a list item

Result:  
![Image import counter](/assets/listItems.png)
