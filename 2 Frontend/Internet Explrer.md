# IE Compatibility

## foreach
A polyfill is a piece of code (usually JavaScript on the Web) used to provide modern functionality on older browsers that do not natively support it.

for each in IE only works for arrays, not nodelists. 
you can create a new .js file in main js
add this polyfill

    if (window.NodeList &&  !NodeList.prototype.forEach) {
        NodeList.prototype.forEach =  Array.prototype.forEach;
    }
restart npm run dev

    "use strict";window.NodeList&&!NodeList.prototype.forEach&&(NodeList.prototype.forEach=Array.prototype.forEach);

[https://developer.mozilla.org/it/docs/Web/API/NodeList/forEach](https://developer.mozilla.org/it/docs/Web/API/NodeList/forEach)

### Flex or Grid

[https://github.com/philipwalton/flexbugs#flexbug-8](https://github.com/philipwalton/flexbugs#flexbug-8)

### custom css

```
IE10+
 @media screen and (-ms-high-contrast: active), (-ms-high-contrast: none) {
 selector { property:value; }
 }

 IE6,7,9,10
 @media screen and (min-width: 640px), screen\9 {
 selector { property:value; }
 }

 IE6,7
 @media screen\9 {
  selector { property:value; }
 }

 IE8
 @media \0screen {
  selector { property:value; }
 }

 IE6,7,8
 @media \0screen\,screen\9 {
  selector { property:value; }
 }

 IE9,10
 @media screen and (min-width:0\0){
  selector { property:value; }
 }
```


## el.closest

    if (!Element.prototype.matches) {
    	Element.prototype.matches = Element.prototype.msMatchesSelector || 
    								Element.prototype.webkitMatchesSelector;
      }
      
      if (!Element.prototype.closest) {
    	Element.prototype.closest = function(s) {
    	  var el = this;
      
    	  do {
    		if (el.matches(s)) return el;
    		el = el.parentElement || el.parentNode;
    	  } while (el !== null && el.nodeType === 1);
    	  return null;
    	};
      }

# scroll to

    if (window.document.documentMode) {
    
    window.scrollTo(0,  element.offsetTop);
    
    }


# arrow function
source map to tell what's wrong
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2OTE2NTY3ODEsLTIwNjUzOTA1NDMsND
E2MDI3MDI3LDI2OTk3MDY5NSwtMTg2OTY1ODU2MiwxNTEwNDg5
NTA4LC0yMDMxNzI5OTU2LC0zNTIwMTczNTddfQ==
-->