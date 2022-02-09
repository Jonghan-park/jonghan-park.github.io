---
title: "React: Composing Components"
header:
  image: /assets/ReactImage.jpg
categories:
  - React
tags:
  - React
  - Composing
---

# Composing components

I can use component made in previous blog's posting named Counter. 
It's like a assembling a robot. Let's get into it.

![Image import counter](/assets/folder_counter.png)

We already have a Counter component underneath components folder.
I'm going to add another component named Counters which is going to render a list of counter.

![Image import counter](/assets/folder_counters.png)

In the index.js, 

### Before
```js
import Counter from './components/counter';

ReactDOM.rende(
  <Counter />,
  document.getElementById('root')
);
```
I'm going to import our new component named **Counters** and render **Counters**.
### After
```js
import Counters from './components/counters';

ReactDOM.rende(
  <Counters />,
  document.getElementById('root')
);
```
Notice that import and render **Counters**

Now, let's get back to our new component.
Make a basic configuration.
```js
imrc
cc 
```
### If you don't understand imrc and cc, please go to this blog posting. It will help you understand.
[![React initialize](/assets/imrc.png)](https://jonghan-park.github.io/react/React_Initialize/)  
**Click the image to open the posting**  

I'm going to import our counter component by adding lines at the top.
```js
import Counter from './counter';
```
Now, I can use Counter component in Counters component.

```js
state = {  } 
    render() { 
        return (
            <div>
            <Counter /> 
            <Counter />
            <Counter />
            <Counter />
            </div>
        );
    }
```
In react, I can use the component as a tag. 
```js
<Counter />
```
Simply, we can use component by typing component name in the pointy brackets as above examples code.

