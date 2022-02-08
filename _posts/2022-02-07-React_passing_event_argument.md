---
title: "React: Passing event arguments"
header:
  image: /assets/ReactImage.jpg
categories:
  - React
tags:
  - React
---

# Passing event arguments

Let's say we want to pass an id of a product through a method.
How can we do this?

```js
doHandleIncrement = () => {
    this.handleIncrement({ id: 1});
};
```
Make a new method named doHandleIncrement.
This is the full code.
```js
class Counter extends Component {
  state = {
      count: 1
   };

   handleIncrement = (product) => {
     console.log(product);
     this.setState({ count: this.state.count + 1 });
   };

   doHandleIncrement = () => {
     this.handleIncrement({ id: 1 });
   };

  render() {
    
    return (
      <div>
        <span className={ this.getBadgeMethod() }>{this.formatCount()}</span>
        <button onClick={ this.doHandleIncrement } className="btn btn-secondary btn-sm">Increment</button>
      </div>
    );
  }

  getBadgeMethod() {
    let classes = "bg m-2 bg-";
    classes += this.state.count === 0 ? "warning" : "primary";
    return classes;
  }

  formatCount() {
    const { count } = this.state;
    return count === 0 ? 'Zero' : count;
  }
}

export default Counter;
```
Notice that doHandleIncrement method has created. 
If I click the button, doHandleIncrement method will be executed.
And then, handleIncrement method will be executed with argument **id: 1** in doHandleIncrement method. 

In handleIncrement method,
```js
 handleIncrement = (product) => {
     console.log(product);
     this.setState({ count: this.state.count + 1 });
   };
```
The value **id: 1** will be passed to product, so **id: 1** will be displayed on console when I clicked the button.