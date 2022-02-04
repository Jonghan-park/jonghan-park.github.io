---
title: "React: Count app"
header:
  image: /assets/ReactImage.jpg
categories:
  - React
tags:
  - React
  - Count app
---


This is the project using react I want to learn. The purpose of the project is getting familiar with react and learning how to use react features on the project.

I've learned the project from YouTube.
 [React begginner YouTube link](https://www.youtube.com/watch?v=Ke90Tje7VS0&t=1259s)

Make components folder underneath src.
And then, make a file named counter.jsx

![Image react components file structure](/assets/componentsFileStructure.png)

#### According to this above video, YouTuber highly encouraged us using extention for efficiency.

![Image react extention tab](/assets/ExtentionTab.png)

#### Type **"Simple React Snippets"** on the search bar.

![Image react extention](/assets/Extention.png)

#### Click the install button.

![Image install extention](/assets/InstallExtention.png)

#### In the counter.jsx, you can import react components easily
#### Type imrc in the counter.jsx which is component.

![Image install extention](/assets/componentShortcut.png)

![Image install extention](/assets/componentShortcut2.png)

#### Next, type cc to make class.

![Image install extention](/assets/cc2.png)

![Image install extention](/assets/cc.png)

What if you want to use two tags or more like below code, 

```
class Counter extends Component {
  render() {
    return <h1>Hello World</h1><button>Increment</button>;
  }
}
```

You can use two tags or more using ```<div>``` tag.

```
class Counter extends Component {
  render() {
  return (
      <div>
        <h1>Hello World</h1>
        <button>Increment</button>
      </div>
    );
  }
}
```

The result

![Image Hello and Button](/assets/helloAndButton.png)

### State 
```
state = {
    
   };
```
>React components has a built-in state object.
The state object is where you store property values that belongs to the component. When the state object changes, the component re-renders.

"State has any data that component needs."

In the ```<div>``` tag, I can render value dynamically using { }
```
state = {
      count: 0
   };
```

```
<div>
  <span>{this.state.count}</span>
  <button>Increment</button>
</div>
```
```this``` is reference of current object.

![Image Hello and Button](/assets/resultCounterButton.png)

I can use any vaild java script expression in { }
```
<div>
  <span>{4 + 4}</span>
  <button>Increment</button>
</div>
```

![Image Hello and Button](/assets/resultFour.png)

Now, I'm going to make a format of the count.
If the count is zero, it will display 'Zero'
To implement this, I should make a method in the Counter components.
```
class Counter extends Component {
  state = {
      count: 0
   };

  render() {
    return (
      <div>
        <span>{4 + 4}</span>
        <button>Increment</button>
      </div>
    );
  }

  formatCount() {
    return this.state.count === 0 ? 'Zero' : this.state.count;
  }
}
```
I just made formatCount() method. 

```
formatCount() {
    return this.state.count === 0 ? 'Zero' : this.state.count;
  }
```
I can consider improving code for code usability.
```this.state``` is stored count variable.
```
formatCount() {
    const { count } = this.state;
    return count === 0 ? 'Zero' : count;
  }
```