# DOM Manipulation
DOM stands for the Document Object Model, and is a tree-like representation of the contetns of a webpage - a tree of "nodes" with different relationships depending on how they're arranged in the HTML document. 

### Targeting Nodes with Selectors
When working with the DOM, you use “selectors” to target the nodes you want to work with. You can use a combination of CSS-style selectors and relationship properties to target the nodes you want.

```html
<div id="container">
  <div class="display"></div>
  <div class="controls"></div>
</div>
```

**CSS-style selectors**:
Possible ways of refering to `<div class="display"></div>` above:
-   `div.display`
-   `.display`
-   `#container > .display`
-   `div#container > div.display`

or relational selectors like 
- `firstElementChild`
- `lastElementChild`
- `previousElementSibling`

## DOM methods
#### Query selectors
-- targeting nodes

-   `element.querySelector(selector)` returns reference to the first match of _selector_
-   `element.querySelectorAll(selectors)` returns a “*nodelist*” containing references to all of the matches of the _selectors_

`querySelectorAll` does *not* return an array, but rather a **nodelist**. It is possible to convert a nodelist to an array with `Array.from()`, or the spread operator. 


#### Element creation
`document.createElement(tagName, [options])` creates a new element of tag type tagName. `[options]` in this case means you can add some optional parameters to the function.


#### Append Elements
-   `parentNode.appendChild(childNode)` appends _childNode_ as the last child of _parentNode_
-   `parentNode.insertBefore(newNode, referenceNode)` inserts _newNode_ into _parentNode_ before _referenceNode_


#### Remove Elements
-   `parentNode.removeChild(child)` removes _child_ from _parentNode_ on the DOM and returns reference to _child_

#### Altering Elements
When you have a reference to an element, you can use that reference to alter the element’s own properties. This allows you to do many useful alterations, like adding/removing and altering attributes, changing classes, adding inline style information and more.

[HTML attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes)
[CSS style rules](http://domenlightenment.com/#6.2)

#### Adding inline style

```javascript
div.style.color = 'blue';                                      
// adds the indicated style rule

div.style.cssText = 'color: blue; background: white';          
// adds several style rules

div.setAttribute('style', 'color: blue; background: white');    
// adds several style rules
```

#### Working with classes
```javascript
div.classList.add('new');                                      
// adds class "new" to your new div

div.classList.remove('new');                                   
// remove "new" class from div

div.classList.toggle('active');                                
// if div doesn't have class "active" then add it, or if
// it does, then remove it
```
It is often standard (and more clean) to toggle a CSS style rather than adding and removing inline CSS.

#### Adding text content

```javascript
div.textContent = 'Hello World!'                               
// creates a text node containing "Hello World!" and
// inserts it in div
```

#### Adding HTML content

```javascript
div.innerHTML = '<span>Hello World!</span>';                   
// renders the html inside div
```

Note that textContent is preferable for adding text, and innerHTML should be used sparingly as it can create security risks if misused.

### Events
Events  are  actions that occur on the webpage, such as a mouse-click or keypress. Using JavaScript, we can make our webpage listen and react to these events. 

Three primary methods of using events to initiate JavaScript:
**method 1**
```html
<button onclick="alert('Hello World')">Click Me</button>
```
**method 2**
```html
<!-- the html file -->
<button id="btn">Click Me</button>
```
```javascript
// the JavaScript file
const btn = document.querySelector('#btn');
btn.onclick = () => alert("Hello World");
```
**method 3**

```html
<!-- the html file -->
<button id="btn">Click Me Too</button>
```

```javascript
// the JavaScript file
const btn = document.querySelector('#btn');
btn.addEventListener('click', () => {
  alert("Hello World");
});
```