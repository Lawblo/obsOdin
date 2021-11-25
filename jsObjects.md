# jsObjects

An **object** in JavaScript is a *data type* that is composed of a collection of **names** or **keys** and **values**, represented in **name:value pairs**. The name:value pairs can consist of **properties** that may contain any data type — including strings, numbers, and Booleans — as well as **methods**, which are functions contained within an object.

### creating an Object

There are two ways to construct an object in JavaScript:
-   The **object literal**, which uses curly brackets: `{}`
```JavaScript
// Initialize object literal with curly brackets
const objectLiteral = {};
```

-   The **object constructor**, which uses the `new` keyword
```js
// Initialize object constructor with new Object
const objectConstructor = new Object();
```



  ### The **this** keyword. 
  When using `this` inside of an object, it refers to the current object.
  

### Properties and Methods

Objects can have **properties** and **methods**.

A property is the association between a name (key) and value within an object, and it can contain any datatype. A property generally refers to the characteristic of an object.
- A property has a key (also known as “name” or “identifier”) before the colon `":"` and a value to the right of it.

A method is a function that is the value of an object property, and therefore a task that an object can perform.

An easy way to remember the difference between object properties and methods is to think of a property as a noun, and a method as a verb.

Adding properties to an object:
```js
let objectName ={
	key1:value,
	key2:value
};
```


### Accessing Object Properties

There are two ways to access an object’s properties.

-   Dot notation: `.`
-   Bracket notation: `[]`

Property values are accessible using the dot notation: `objectName.key`.
The dot requires the key to be a valid variable identifier. That implies: contains no spaces, doesn’t start with a digit and doesn’t include special characters (`$` and `_` are allowed).

We can also use *multiword property* names, but then they must be quoted. In order to access multiword properties, you have you have to use an alternative *square bracket annotation*, where the property is inside *square brackets* instead of behind a dot. 

The *last property* in the list may end with a comma, which is called a “trailing” or “hanging” comma. Makes it easier to add/remove/move around properties, because all lines become alike.

*Square brackets* also provide a way to obtain the *property name* as the *result of any expression* – as opposed to a literal string.
 EX: 
 ```js
 let key = name;
 //would return `undefined`
 user.key 
 //would return the value of user.name
 user.[key]  
 ```
This would mean that what property is accessed could vary depending on user input, which wouldnt be possible with the dot notation. 


To check if a property with the given key exists: `"key" in obj`.

### Adding and Modifying Object Properties

In order to add a new property to an object, you would assign a new value to a property with the assignment operator (`=`).

### Removing Object Properties

In order to remove a property from an object, you will utilize the `delete` keyword. `delete` is an operator that removes a property from an object.
ex: `delete objectName.propertyToRemove`

The `delete` operation evaluates as `true` if the property was successfully removed, or if it was used on a property that doesn’t exist.

### Looping Through Object Properties

JavaScript has a built-in type of `for` loop that is specifically meant for iterating over the properties of an object. This is known as the `for...in` loop.

```js
for (let key in objectName) {
  console.log(objectName[key]);
}
```

We can use `for...in` to traverse through all the properties  and print them to the console. Using bracket notation, we can retrieve the property value as a variable, in this case `key`.

We can also retrieve the property name itself using just the first variabe in the `for...in` loop.

```js
// Get keys and values of objectName properties
for (let key in objectName) {
  console.log(key.toUpperCase() + ':', objectName[key]);
}
```

Another useful enumeration method is the `Object.keys()` method, which will return an array of the object’s keys.