---
title: "React: Hello World"
header:
  image: /assets/ReactImage.jpg
categories:
  - React
tags:
  - React
  - Hello World
---

# Hello World

We need to make a react app first named my-react
Open the command and move to the directory you want to make a new project. 

```
create-react-app my-react
```
Several minutes later, 
see if it's working on the local web browser. 

```
cd my-react
npm start
```
If you saw the react main page, you would be ready to go.

You can delete all of files in src folder and make a new file.

**index.js**

![Image react files](/assets/my-react-files.png)


React project has to import object from module.

```
import React from 'react';
import ReactDom from 'react-dom';
```

_React_ is the object, 'react' is the module in this case.
Let's look at the next line. _ReactDom_ is the object 
importing from 'react-dom' module.

To define variable, use **const**, **let** or **var**. 
**const** is a new feature in modern JavaScript.

```
const element = <h1>Hello World</h1>;
```

You can declare a variable with a html like the code above.
React is jsx, and it is a syntax extension to JavaScript.

```
ReactDom.render(element, document.getElementById('root'));
```

First argument is the element that we want to render.
Second argument is the specification of the container for our react application which is 'root'.

```
import React from 'react';
import ReactDom from 'react-dom';

const element = <h1>Hello World</h1>;
ReactDom.render(element, document.getElementById('root'));
```

So this is our first app named Hello world.
Open the command window, and type npm start to see your final result.


![Image react files](/assets/my-react-result.png)