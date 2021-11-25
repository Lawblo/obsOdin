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




## Relational selectors


|**Parent Nodes**| |
| :- | :- |
|*property*|*gets*|
|parentNode|Parent Node|
|parentElement|Parent Element Node|
|**Children Nodes**| |
|*property*|*gets*|
|childNodes|Child Nodes|
|firstChild|First Child Node|
|lastChild|Last Child Node|
|children|*Element* Child Nodes|
|firstElementChild|First Child Element Node|
|lastElementChild|Last Child Element Node|

The `childNodes` property will retrurn a live list of every child of a node. This includes the indentations between the elements as text nodes. This can be remedied by using the `children`, `firstElementChild`, and `lastElementChild` properties, which will only return element nodes. 

**children vs childNodes, nextSibling vs nextElementSibling, etc...**

Whenever the DOM is created from scratch, there is usually some whitespace on the page.  
 However, if the DOM is created as a JavaScript web app, then theres probably no whitespace, and you don't have to specificaly target *element* nodes

a `for...of` loop can be used to iterate throigh all `children` elements

|**Sibling Nodes**| |
| :- | :- |
|*property*|*gets*|
|previousSibling|Previous Sibling Node|
|nextSibling|Next Sibling Node|
|previousElementSibling|Previous Sibling Element Node|
|nextElementSibling|Next Sibling Element Node|

## Creating New Nodes
|*Property/Method*|*Description*|
| :- | :- |
|`createElement()`|Create a new element node|
|`createTextNode()`|Create a new text node|
|`node.textContent`|Get or set the text content of an element node|
|`node.innerHTML`|Get or set the HTML content of an element|

With the innHTML method, it's possible to add HTML as well as text to an element, *HOWEVER*, this makes cross site scripting (XSS) a risk. textContent strips out the HTML tags and removes this risk. 

## Inserting Nodes into the DOM

In order to see the new text nodes and elements we create on the front end, we will need to insert them into the `document`. The methods `appendChild()` and `insertBefore()` are used to add items to the beginning, middle, or end of a parent element, and `replaceChild()` is used to replace an old node with a new node.

|*Property/Method*|*Description*|
| :- | :- |
|`node.appendChild()`|Add a node as the last child of a parent element|
|`node.insertBefore()`|Insert a node into the parent element before a specified sibling node|
|`node.replaceChild()`|Replace an existing node with a new node|

**insertBefore()**

`insertBefore()` requires two arguments — the first is the new child node to be added, and the second is the sibling node that will immediately follow the new node:
```js
parentNode.insertBefore(newNode, nextSibling);
```

**replaceChild()**

`replaceChild()` takes two arguments — the new node, and the node to be replaced:
```js
parentNode.replaceChild(newNode, oldNode);
```

## Removing Nodes from the DOM

Child nodes can be removed from a parent with `removeChild()`, and a node itself can be removed with `remove()`.

|*Method*|*Description*|
| :- | :- | 
|`node.removeChild()`|Remove child node|
|`node.remove()`|Remove node|


## Modifying Attributes

Attributes are values that contain additional information about HTML elements. They usually come in **name/value** pairs, and may be essential depending on the element.

Some of the most common HTML attributes are the `src` attribute of an `img` tag, the `href` of an `a` tag, `class`, `id`, and `style`. For a full list of HTML attributes, view the [attribute list](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes) on the Mozilla Developer Network. Custom elements that are not part of the HTML standard will be prepended with `data-`.

|*Method*|*Description*|*Example*|
| :- | :- | :- |
|`hasAttribute()`|Returns a `true` or `false` boolean|`element.hasAttribute('href');`|
|`getAttribute()`|Returns the value of a specified attribute or `null`|`element.getAttribute('href');`|
|`setAttribute()`|Adds or updates value of a specified attribute|`element.setAttribute('href', 'index.html');`|
|`removeAttribute()`|Removes an attribute from an element|`element.removeAttribute('href');`|


## Modifying Classes

|*Method/Property*|*Description*|*Example*|
| :- | :- | :- |
|`className`|Gets or sets class value|`element.className;`|
|`classList.add()`|Adds one or more class values|`element.classList.add('active');`|
|`classList.toggle()`|Toggles a class on or off|`element.classList.toggle('active');`|
|`classList.contains()`|Checks if class value exists|`element.classList.contains('active');`|
|`classList.replace()`|Replace an existing class value with a new class value|`element.classList.replace('old', 'new');`|
|`classList.remove()`|Remove a class value|`element.classList.remove('active');`|

You can use `className` to assign a value directly to the class.

Note that if any classes already exist on the element, this will override them. You can add multiple space delimited classes using the `className` property, or use it without assignment operators to get the value of the class on the element.

Unlike in the `className` example, using `classList.add()` will add a new class to the list of existing classes. You can also add multiple classes as comma-separated strings. It is also possible to use `setAttribute` to modify the class of an element.

## Modifying Styles

One option to edit the styles is with `setAttribute()`. 

*EX*:

```js
// Select div
const div = document.querySelector('div');

// Apply style to div
div.setAttribute('style', 'text-align: center');
```

However, this will remove all existing inline styles from the element. Since this is likely not the intended effect, it is better to use the `style` attribute directly. 

*EX*:
```js
div.style.height = '100px';
div.style.width = '100px';
div.style.border = '2px solid black';
```

CSS properties are written in kebab-case, which cannot be used on the JavaScript style property. Instead, they will be replaced with their camelCase equivalent.

If many stylistic changes are to be applied to an element, the best course of action is to apply the styles to a class and add a new class. However, there are some cases in which modifying the inline style attribute will be necessary or more straightforward.

## Events

**Events** are actions that take place in the browser that can be initiated by either the user or the browser itself. 

By coding JavaScript responses that execute upon an event, developers can display messages to users, validate data, react to a button click, and many other actions.

## Event Handlers and Event Listeners

An **event handler** is a JavaScript function that runs when an event fires.

An **event listener** attaches a responsive interface to an element, which allows that particular element to wait and “listen” for the given event to fire.

- There are three ways to assign events to elements:
	-   Inline event handlers
	-   Event handler properties
	-   Event listeners

### Inline Event Handler Attributes

Inline event handlers are a straightforward way to begin understanding events, but they generally should not be used beyond testing and educational purposes. 
It is much more practical to maintain a separate stylesheet of classes than create inline styles on every element, just as it is more feasible to maintain JavaScript that is handled entirely through a separate script file than add handlers to every element.

HTML;
```html
<button onclick="changeText()">Click me</button>

    <p>Try to change me.</p>
```
JS:
```js
const changeText = () => {
    const p = document.querySelector('p');

    p.textContent = "I changed because of an inline event handler.";
}
```

### Event Handler Propertie
This works very similarly to an inline handler, except we’re setting the property of an element in JavaScript instead of the attribute in the HTML.
HTML
```html
    <button>Click me</button>

    <p>I will change.</p>
```
JS
```js
// Function to modify the text content of the paragraph
const changeText = () => {
    const p = document.querySelector('p');

    p.textContent = "I changed because of an event handler property.";
}

// Add event handler as a property of the button element
const button = document.querySelector('button');
button.onclick = changeText;
```

Note that when passing a function reference to the `onclick` property, *we do not include parentheses*, as we are not invoking the function in that moment, but only passing a reference to it.

### Event Listeners
An **event listener** watches for an event on an element.

`addEventListener()` takes two mandatory parameters — the event it is to be listening for, and the listener callback function.

HTML:
```html
    <button>Click me</button>

    <p>I will change.</p>
```
JS:
```js
// Function to modify the text content of the paragraph
const changeText = () => {
    const p = document.querySelector('p');

    p.textContent = "I changed because of an event listener.";
}

// Listen for click event
const button = document.querySelector('button');
button.addEventListener('click', changeText);
```

At first look, event listeners seem very similar to event handler properties, but they have a few advantages. We can for example set multiple event listeners on the same element.

Often, *anonymous functions* will be used instead of a function reference on an event listener. Anonymous functions are functions that are not named.

```js
// An anonymous function on an event listener
button.addEventListener('click', () => {
    p.textContent = "Will I change?";
});
```

It is also possible to use the `removeEventListener()` function to *remove* one or all events from an element.

```js
// Remove alert function from button element
button.removeEventListener('click', alertText);
```


Furthermore, you can use `addEventListener()` on the `document` and `window` object.

Event listeners are currently the most common and preferred way to handle events in JavaScript.

## Common Events
### Mouse Events

Mouse events are among the most frequently used events. They refer to events that involve clicking buttons on the mouse or hovering and moving the mouse pointer. These events also correspond to the equivalent action on a touch device.

|Event|Description|
| :- | :-|
|`click`|Fires when the mouse is pressed and released on an element|
|`dblclick`|Fires when an element is clicked twice|
|`mouseenter`|Fires when a pointer enters an element|
|`mouseleave`|Fires when a pointer leaves an element|
|`mousemove`|Fires every time a pointer moves inside an element|

A `click` is a compound event that is comprised of combined `mousedown` and `mouseup` events, which fire when the mouse button is pressed down or lifted, respectively.

Using `mouseenter` and `mouseleave` in tandem recreates a hover effect that lasts as long as a mouse pointer is on the element.

### Form Events

Form events are actions that pertain to forms, such as `input` elements being selected or unselected, and forms being submitted.

|Event|Description|
| :- | :- |
|`submit`|Fires when a form is submitted|
|`focus`|Fires when an element (such as an input) receives focus|
|`blur`|Fires when an element loses focus|

_Focus_ is achieved when an element is selected, for example, through a mouse click or navigating to it via the `TAB` key.

JavaScript is often used to submit forms and send the values through to a backend language. The advantage of using JavaScript to send forms is that it does not require a page reload to submit the form, and JavaScript can be used to validate required input fields.

### Keyboard Events

Keyboard events are used for handling keyboard actions, such as pressing a key, lifting a key, and holding down a key.

|Event|Description|
| :- | :- |
|`keydown`|Fires once when a key is pressed|
|`keyup`|Fires once when a key is released|
|`keypress`|Fires continuously while a key is pressed|

Although they look similar, `keydown` and `keypress` events do not access all the exact same keys. While `keydown` will acknowledge every key that is pressed, `keypress` will omit keys that do not produce a character, such as `SHIFT`, `ALT`, or `DELETE`.

Keyboard events have specific properties for accessing individual keys.

If a parameter, known as an `event` object, is passed through to the event listener, we can access more information about the action that took place. Two properties that pertain to keyboard objects include `key` and `code`.

For example, if the user presses the letter `a` key on their keyboard, the following properties pertaining to that key will surface:

|Property|Description|Example|
| :- | :- | :- |
|`key`|Represents the character name|a|
|`code`|Represents the physical key being pressed|KeyA|

The `key` property is the name of the character, which can change — for example, pressing `a` with `SHIFT` would result in a `key` of `A`. The `code` property represents the physical key on the keyboard.

## Event Objects

The `Event` object consists of properties and methods that all events can access. In addition to the generic `Event` object, each type of event has its own extensions, such as `KeyboardEvent` and `MouseEvent`.

The `Event` object is passed through a listener function as a parameter. It is usually written as `event` or `e`. We can access the `code` property of the `keydown` event to replicate the keyboard controls of a PC game.

### the `target` property
In the following example, we have three `div` elements inside one `section`.

HTML:
```html
<!DOCTYPE html>
<html lang="en-US">
<head>
    <title>Events</title>
</head>
<body>

  <section>
    <div id="one">One</div>
    <div id="two">Two</div>
    <div id="three">Three</div>
  </section>

</body>
</html>
```

 
Using `event.target` with JavaScript in our browser’s Developer Console, we can place one event listener on the outer `section` element and get the most deeply nested element.

```js
const section = document.querySelector('section');

// Print the selected target
section.addEventListener('click', event => {
    console.log(event.target);
});
```

 

Clicking on any one of those elements will return output of the relevant specific element to the Console using `event.target`. This is extremely useful, as it allows you to place only one event listener that can be used to access many nested elements.

