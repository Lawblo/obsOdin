# rbArrays
- [[rbArrays#Creating an array|Creating an array]]
- [[rbArrays#Accessing Elements| Accessing Elements]]
- [[rbArrays#Adding and Removing Elements|Adding and Removing Elements]]
- [[rbArrays#Adding and Subtracting Arrays|Adding and Subtracting Arrays]]
- [[rbArrays#The Array Map Method|The Array Map Method]]
- [[rbArrays#Iterating Over an Array|Iterating Over an Array]]
- [[rbArrays#Nested Arrays|Nested Arrays]]
- [[rbArrays#Common Array Methods|Common Array Methods]]

One way [[Ruby]] allows you to represent a collection of data is with **arrays**, which you can think of as ordered lists. Rather than working with individual variables, numbers, or strings, an array allows you to create and manipulate an ordered and indexed collection of these data. The individual variables, numbers, or strings within an array are known as **elements**. An array can contain any combination of variables, numbers, strings, or other Ruby objects (including other arrays), although it is advisable to keep similar data types in any one array.


### Creating an array

Arrays are commonly created with an **array literal**, which is simply a special syntax used to create instances of an array object. To create a new array using an array literal, use square brackets (`[]`).

An array can also be created by calling the `Array.new` method. When you call this method, you can also include up to 2 optional arguments (initial size and default value).

### Accessing Elements
Every element in an array has an index. 

Ruby arrays ise zero-based indexing. 

Accesing a specific element withtin an array is done by calling myArray[x], where x is the index of the element you want. Calling an invallid position results in nil. Ruby also allows *negative indices*, which retrun elements startign from the *end* of an array, startinh at [-1].

Finally, Ruby provides the `#first` and `#last` array methods, which should be self-explanatory. In addition, these methods can take an integer argument, e.g., `myArray.first(n)` or `myArray.last(n)`, which will return a new array that contains the first or last `n` elements of `myArray`, respectively.

### Adding and Removing Elements

Adding an element to an existing array is as simple as using the `#push` method or the shovel operator `<<`. Both methods will add elements to the end of an array and return that array with the new elements. The `#pop` method will remove the element at the end of an array and return the element that was removed.


The methods `#shift` and `#unshift` are used to add and remove elements at the beginning of an array. The `#unshift` method adds elements to the beginning of an array and returns that array (much like `#push`). The `#shift` method removes the first element of an array and returns that element (much like `#pop`).

It’s also useful to know that both `#pop` and `#shift` can take integer arguments

### Adding and Subtracting Arrays

*Adding* two arrays will return a new array built by concatenating them, similar to string concatenation. The `concat` method works the same way.

To find the difference between two arrays, you can *subtract* them using `-`. This method returns a copy of the first array, removing any elements that appear in the second array.

### The Array Map Method

The `map` method iterates over an array applying a block to each element of the array and returns a new array with those results. 

### Iterating Over an Array

The `select` method iterates over an array and returns a new array that includes any items that return `true` to the expression provided.

### Nested Arrays 
You can also create arrays with arrays inside of them.

### Common Array Methods

#### to_s

The `to_s` method is used to create a string representation of an array. Ruby does this behind the scenes when you use string interpolation to print an array to the screen.

#### include?
The **include?** method checks to see if the argument given is included in the array.

#### flatten
The **flatten** method can be used to take an array that contains nested arrays and create a one-dimensional array.

#### each_index
The **each_index** method iterates through the array much like the **each** method, however the variable represents the index number as opposed to the value at each index.

#### each_with_index
`each_with_index` gives us the ability to manipulate both the value and the index by passing in two parameters to the block of code. The first is the value and the second is the index. You can then use them in the block.

#### sort
The **sort** method is a handy way to order an array. It returns a sorted array.

#### product 
The **product** method can be used to combine two arrays in an interesting way. It returns an array that is a combination of all elements from all arrays.


|Operation|Methods|
| :- | :- |
|initialize|`Array.new`, `[]`, `%w`|
|read|`[0]`, `first`, `last`|
|add|`push`, `<<`, `unshift`|
|remove|`pop`, `delete_at`, `shift`|