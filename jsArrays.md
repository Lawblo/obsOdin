# JsArrays

Arrays are useful for dealing with a large quantity of numbers, strings and other things. An array is an ordered collection of itens. 


### Creating an Array
Array Syntax: 
```JavaScript
const _array_name_ = [_item1_, _item2_, ...]; 
```

It's a common practice to delcare arrays with the `const` keyword. 

A declaration can span multiple lines. 

Its also possible to create an array, and then provide the elements. 

### Accessing Array Elements
You can access an array element by referring to the **index number**. 

Array indexes start with 0. [0] is the first element, [1] is the second element. 

### Changing an Array Element
```JavaScript
arrayName[0] = "changedValue";
```

### Access the Full Array
With [[JavaScript]], the full array can be accessed by referring to the array name

### Arrays are Objects
Arrays are a special type of objects. The `typeof` operator in JavaScript returns "object" for arrays. But, JavaScript arrays are best described as arrays.
Arrays use **numbers** to access its "elements".
Objects use **names** to access its "members"

### Array Elements Can Be Objects
JavaScript variables can be objects. Arrays are special kinds of objects. Because of this, you can have variables of different types in the same Array. You can have objects in an Array. You can have functions in an Array. You can have arrays in an Array.

## Array Properties and Methods

### The Array length Property
he `length` property of an array returns the length of an array (the number of array elements).
The `length` property is always one more than the highest array index.

### Accessing the First Array Element
``` JavaScript
array[0]
```

### Accessing the Last Array Element
``` JavaScript
array[array.length -1]
```

### Looping Array Elements
One way to loop through an array, is using a `for` loop. Ex:
```JavaScript
const fruits = ["Banana", "Orange", "Apple", "Mango"];  
let fLen = fruits.length;  
  
text = "<ul>";  
for (let i = 0; i < fLen; i++) {  
  text += "<li>" + fruits[i] + "</li>";  
}  
text += "</ul>";
```
You can also use the `Array.forEach()` function. Ex: 
```JavaScript
const fruits = ["Banana", "Orange", "Apple", "Mango"];  
  
let text = "<ul>";  
fruits.forEach(myFunction);  
text += "</ul>";  
  
function myFunction(value) {  
  text += "<li>" + value + "</li>";  
}
```

### Adding Array Elements
The easiest way to add a new element to an array is using the `push()` method
```JavaScript
const fruits = ["Banana", "Orange", "Apple"];  
fruits.push("Lemon");  // Adds a new element (Lemon) to fruits
```

## Array Methods

### Converting Arrays to Strings
The JavaScript method `toString()` converts an array to a string of (comma separated) array values:
```JavaScript
fruits.toString()
```
The `join()` method also joins all array elements into a string. It behaves just like `toString()`, but in addition you can specify the separator.
```JavaScript
fruits.join(" * ");
```

### Popping
The `pop()` method removes the last element from an array. The `pop()` method returns the value that was "popped out"

### Pushing
The `push()` method adds a new element to an array (at the end). The `push()` method returns the new array length.

### Shifting Elements
Shifting is equivalent to popping, working on the first element instead of the last.
The `shift()` method removes the first array element and "shifts" all other elements to a lower index
The `shift()` method returns the value that was "shifted out".

The `unshift()` method adds a new element to an array (at the beginning), and "unshifts" older elements. The `unshift()` method returns the new array length.


### Changing Elements

Array elements are accessed using their **index number**:

Array **indexes** start with 0:

[0] is the first array element  
[1] is the second  
[2] is the third ...

The `length` property provides an easy way to append a new element to an array:
```JavaScript
fruits[fruits.length] = "Kiwi";
```

### Deleting Elements
Array elements can be deleted using the JavaScript operator `delete`. Using `delete` leaves `undefined` holes in the array. Use pop() or shift() instead.

### Splicing an Array
The `splice()` method can be used to add new items to an array:
```JavaScript
fruits.splice(2, 0, "Lemon", "Kiwi");
```
The first parameter (2) defines the position **where** new elements should be **added** (spliced in). The second parameter (0) defines **how many** elements should be **removed**. The rest of the parameters ("Lemon" , "Kiwi") define the new elements to be **added**. The `splice()` method returns an array with the deleted items.

#### Using splice() to Remove Elements

With clever parameter setting, you can use `splice()` to remove elements without leaving "holes" in the array.
The first parameter defines the position where new elements should be **added** (spliced in). The second parameter defines **how many** elements should be **removed**. The rest of the parameters are omitted. No new elements will be added.

### Merging (Concatenating) Arrays

The `concat()` method creates a new array by merging (concatenating) existing arrays. 

The `concat()` method does not change the existing arrays. It always returns a new array.

The `concat()` method can take any number of array arguments.

The `concat()` method can also take strings as arguments.

### Slicing an Array

The `slice()` method slices out a piece of an array into a new array.

The `slice()` method creates a new array. It does not remove any elements from the source array.

The `slice()` method can take two arguments like `slice(1, 3)`. The method then selects elements from the start argument, and up to (but not including) the end argument.

If the end argument is omitted, the `slice()` method slices out the rest of the array.

### Automatic toString()

JavaScript automatically converts an array to a comma separated string when a primitive value is expected. This is always the case when you try to output an array.

### Finding Max and Min Values in an Array

There are no built-in functions for finding the highest or lowest value in a JavaScript array.