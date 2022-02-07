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


## Conditional rendering

```js
state = {
      count: 0
      items: ['item1', 'item2', 'item3']
   };

   renderItems() {
       if(this.state.items.length === 0) return <p>There are no items!</p>;

       return <ul>{ this.state.items.map(item => <li>{ item }</li>)}</ul>;
   }

  render() {
    
    return (
      <div>
        { this.renderItems() }
      </div>
    );
  }
  ```
  If the items array is empty, the paragraph tag will display.

I can write same funtion in another way.
  ```js
state = {
      count: 0
      items: ['item1', 'item2', 'item3']
   };

   renderItems() {
       if(this.state.items.length === 0) return <p>There are no items!</p>;

       return <ul>{ this.state.items.map(item => <li>{ item }</li>)}</ul>;
   }

  render() {
    
    return (
      <div>
        { this.state.items.length === 0 && "Please create a new item!" }
        { this.renderItems() }
      </div>
    );
  }
  ```

```js
if(this.state.items.length === 0) return <p>There are no items!</p>;
return <ul>{ this.state.items.map(item => <li>{ item }</li>)}</ul>;
```
Same with
```js   
{ this.state.items.length === 0 && "Please create a new item!" }
```

How?  

true && false = false  
true && "Hello" = ??  

\
\
\
\
\
\

Answer is Hello