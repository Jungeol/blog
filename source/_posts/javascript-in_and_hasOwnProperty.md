---
title: javascript-in_and_hasOwnProperty
tag: javascript
category: javascript
date: 2019-12-04 21:40:29
---
# Javascript 'in' and 'object.hasOwnProperty'
```
var book = {
    title: "High Performance JavaScript",
    publisher: "Yahoo! Press" 
};

alert(book.hasOwnProperty("title"));  //true
alert(book.hasOwnProperty("toString"));  //false
alert("title" in book); //true 
alert("toString" in book); //true
```