# jsDataTypes
There are 8 basic data types in [[JavaScript]]. Variables can hold any type of data and change the kind of data it holds.

-   `number` for numbers of any kind: integer or floating-point, integers are limited by `±(253-1)`.
-   `bigint` is for integer numbers of arbitrary length.
-   `string` for strings. A string may have zero or more characters, there’s no separate single-character type.
-   `boolean` for `true`/`false`.
-   `null` for unknown values – a standalone type that has a single value `null`.
-   `undefined` for unassigned values – a standalone type that has a single value `undefined`.
-   `object` for more complex data structures.
-   `symbol` for unique identifiers.

The `typeof` operator allows us to see which type is stored in a variable.

-   Two forms: `typeof x` or `typeof(x)`.
-   Returns a string with the name of the type, like `"string"`.
-   For `null` returns `"object"` – this is an error in the language, it’s not actually an object.

## Number
The number type represents both integer and floating point numbers. 
The number type cannot represent integer values larger than (2^35)-1, or less than -1((2^35)-1)

Besides regular numbers there are so-called "special numeric values" which also belong to  this data type:`Infinity`, `-Infinity`, and `NaN`.

## BigInt
BigInt is a newer type that represents integers of arbitrary length. A `BigInt` value is created by appending `n` to the end of an integer. 

## String
A string in JS must be surrounded by quotes.
- Types of quotes:
	- Double quotes: `"Hello"`
	- Single quotes: `'Hello'`
	- Backticks: ```` ` ````

Double and single quotes are “simple” quotes. There’s practically no difference between them in JavaScript.

Backticks are “extended functionality” quotes. They allow us to embed variables and expressions into a string by wrapping them in `${…}`. The expression inside `${…}` is evaluated and the result becomes part of the string. 

## Boolean (logical type)
The boolean type only has two values: `true` and `false`.


## Null
The special `null` value does not belong to any of the types described above. It forms a separate type of its own which contains only the `null` value. 
Null is a special value which represents "nothing" or "value unknown". 

## Undefined
Special type, like null. Represents "value not assigned".
If a variable is declared but not assigned, then its value is `undefined`.

## Objects and Symbols
`Objects` are used to store colletions of data and more complex entities. Other types are called "primitive" because they can only contain one thing. 

The `symbol` type is used to create unique identifiers for objects. 