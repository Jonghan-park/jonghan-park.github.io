---
title: "HTML & HTML5: Basic"
header:
  image: /assets/html.jpg
categories:
  - HTML
tags:
  - HTML
  - HTML5
---

This posting is for getting used to HTML & HTML5.

### header tag

`<h1></h1>` tag is the most big size and bold fonts. There are 1 to 6, and it's going to be getting smaller.

```js
<h1> ... </h1>
```

### Paragraph tag

`<p></p>` tag is a paragraph tag to inform some texts.

### HTML5 tags

In HTML5, there are `<main></main>, <header></header>, <footer></footer>, <nav></nav>, <video></video>, <article></article>, <section></section>`  
These tags are easy to read, give a descriptive and help with Search Engine Optimization (SEO) and accessibility.

### Image tag

`<img></img>` This tag allow user to add image to a website.

```js
<img src="/assets/html.jpg" alt="HTML main page">
```

`alt` attribute is used for screen readers.

### Link to External Pages with Anchor Elements

`<a></a>` tag allow us to link to content outside of a web page. I need to use `href` attribute.

```js
<a href="https://jonghan-park.github.io/">This is Jonghan's blog</a>
```

### Link to Internal section with Anchor Elements

I can use the anchor tag to link internal section by using #.

```js
<h2 id="contacts-header">Contacts</h2>
...
<a href="#contacts-header">Contacts</a>
```

### Nest an Anchor tag within a paragraph

I can nest links within other text elements.

```js
<p>
  Here's a <a target="_blank" href="https://www.google.ca"> link to Google </a> for you to follow.
</p>
```

`target` is an attribute that specifies where to open the link. The value `_blank` specifies to open the link in a new tab.

### Using `#` to make dead Links

If I don't know the link to put yet, I can use `#` in the `href` attribute.

```js
<a href="#" target="_blank"> ... </a>
```
If I want to make the image with link, I can nest the image within an ```a``` element.  
```js
<a href="#" target="_blank"> <img src="assets/img.jpg" alt="Image">... </a>
```  
### Create a list
```js
<ul>  
  <li>...</li>  
  <li>...</li>  
  <li>...</li>  
</ul>  
```  
or put number in front of each element.  
```js
<ol>  
  <li>...</li>  
  <li>...</li>  
  <li>...</li>  
</ol>  
  
result:  
1.  ...  
2.  ...   
3.  ...  
```  