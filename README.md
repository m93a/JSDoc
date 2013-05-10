# JSDoc
![JSDOC](https://raw.github.com/m93a/JSDoc/master/logo.png)
## Do it JS way!

### Section 1 - Introduction
You probably know DOM. It's huge and mighty - the only way to modify document on the client side. But it's hugeness is it's weakness. Nobody wants to write five lines instead of one, that's why jQuery was invented.  
Yes, jQuery is great and deft but it is still only a framework - DOM still lives under it's surface. I decided to give the world an alternative - way to translate XML and HTML to simple, light-weight machine-readable object.  

Adventages of JSDoc:
* simple and fast to learn
* short names - ` doc.query('.foo')` instead of `document.getElementsByClassName('foo')`
* convertable to JSON - multiplatform, as well as DOM

### Section 2 - Specification
Everything in this section will be written in JS, additional info can be found in comments.
NOTE: In this documentation there is no difference between "element" and "node".

#### JSDoc
```js
var doc = {
  "encoding": string, //This defines document encoding - has to be an ASCII string
  "language": [string, string, ...], //List of language codes, according to BCP 47 standard
  
  "query": function(str){...}, //NodeList - get nodes by CDS selector
  "style": array, //JSSI - JavaScript Sheet Interpretation
  "childs": object //NodeList - list of childs
  
  "on": function(event,listener){...}, //Append event listener
  "once": function(event,listener){...}, //Append one time event listener
  "unlisten": function(event,listener){...}, //Remove event listener
  "deaf": function(event){...}, //Remove all the listeners of an event, omitting first value will remove all the listeners of all the events
  
  "events": { //List of events and their listeners
    "load": [f1, f2, ...],
    "click": [f1, f2, ...],
    ...
  }
};
```

#### JSNode
```js
var node = {
  "tag": {
    "name": string, //Tag name
    "space": string //Namespace
  }
  "query": function(str){...}, //Get elements by CDS selector
  "style": { //Element's CDS styles
    "display": ["block"],
    "height": [26, "px"],
    ...
  },
  "childs": object //NodeList - list of childs
  
  "on": function(event,listener){...}, //Append event listener
  "once": function(event,listener){...}, //Append one time event listener
  "unlisten": function(event,listener){...}, //Remove event listener
  "deaf": function(event){...}, //Remove all the listeners of an event, omitting first value will remove all the listeners of all the events
  
  "events": { //List of events and their listeners
    "mouseover": [f1, f2, ...],
    "mouseout": [f1, f2, ...],
    "click": [f1, f2, ...],
    ...
  }
  
  "hasText": function(){...}, //Has textContent
  "getText": function(){...}, //Get textContent
  "setText": function(str){...}, //Set textContent
  
  "hasAttr": function(attr){...}, //Has attribute
  "getAttr": function(attr){...}, //Get attribute
  "setAttr": function(attr,value){...}, //Set attribute
  
  "attrs": { //List of attributes and their values
    "key1": string,
    "key2": string,
    ...
  }
}
```

#### JSNodeList
```js
var list = {
  //Nodes and strings:
  0: object,
  1: string, //String is an equivalent of DOM textNode
  2: object,
  3: object,
  ...
  "length": int, //Number of nodes
  "pointer": 0, //Array pointer
  "next": function(){ //Equiv of XPath iterateNext()
    return this[this.pointer++];
  }
  
  //Apply on all the nodes
  "on": function(event,listener){...}, //Append event listener
  "once": function(event,listener){...}, //Append one time event listener
  "unlisten": function(event,listener){...}, //Remove event listener
  "deaf": function(event){...}, //Remove all the listeners of an event, omitting first value will remove all the listeners of all the events

}
```

### Section 3 - How to use
>>Here you'll soon be able to find links to compilers and CDS documentation<<

### Section 4 - License
This documentation is work of **Michal Grňo** (aka m93a) but was inspired by many others. You can modify, copy, spread, print, shred, sell, buy, trade, ignore, promote, fork or push (or whatever you like to) this project with no limitations. I hope this document helped you somehow.
Public domain.
