---
title: "React: Increment a number"
header:
  image: /assets/ReactImage.jpg
categories:
  - React
tags:
  - React
  - onClick()
---

# Increment a number

When a specific button is clicked, a number will be incremented. 

```js
class Counter extends Component {
    state = {
        count: 0
    };

    handleIncrement = () => {
        this.setState({ count: this.state.count + 1 })
    } 

    render() { 
    return (
      <div>
        <span>{ this.state.count }</span>
        <button onClick={ this.handleIncrement() } className="btn btn-secondary btn-sm">Increment</button>
      </div>
    );
  }
}
 
export default Counter;
```
This Counter class inherit Component which has setState().
I should use that method to change the value of state.

```js
handleIncrement = () => {
        this.state.count++     
    } 
```
It doesn't work in this way.


