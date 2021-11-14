# JavaScript

JavaScript is written in [[HTML]] inside the `<script></script>` tags.

`console.log()` prints whatevers inside the parenteces into the developer console of the web browser.

## Variables
Variables can be thought of as storage containers for the data in your code. Previously the onlt way to create a variable was the `var` statement, but newer version of JavaScript has introduced `let` and `const`.

A variable can be declared using the `let` keyword: `let varName = storedValue;`

More variables can be declared by separating the lines with a comma, at the end of the line, or in front.

comma-first:
<pre>
let varNameOne = storedValueOne
,	varNameTwo = storedValueTwo
,	varNameThree = storedValueThree;
</pre>

comma-after:
<pre>
let varNameOne = storedValueOne,
	varNameTwo = storedValueTwo,
	varNameThree = storedValueThree;
</pre>

- A variable
	- can be changed as many times as wanted. 
	- can be set to equal another variable
	- should only be declared once.

## Variable Naming
1. variable names must contain only letters, digits, or the symbols $ and _
2. the first character must not be a digit

When the name contains multiple words, `camelCase` is commonly used: words go one after another, each word except firts starting with a capital letter. 

Variables are case sensitive. 
Non-Latin letters are allowed, but not recommended

Some [reserved words](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords) can't be used as variable names because they're used by the language itself. 

If `use strict` is not put in the script, the it is possible to create a variable by assigning it a value without using let. 

## Constants
A constant is an unchanging variable:

`const unchangeableVariable = unchangeableValue`

### Uppercase constants
There is a widespread practice to use constants as aliases for difficult-to-remember values that are known prior to execution.

Such constants are named using capital letters and underscores.

```javascript
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";
const COLOR_ORANGE = "#FF7F00";

// ...when we need to pick a color
let color = COLOR_ORANGE;
alert(color); // #FF7F00
```

Being a “constant” just means that a variable’s value never changes. But there are constants that are known prior to execution (like a hexadecimal value for red) and there are constants that are _calculated_ in run-time, during the execution, but do not change after their initial assignment.

## Name things right!
Variables names should have a clean, obious meaning, describing the data that it stores. 

Some good-to-follow rules:
-   Use human-readable names like `userName` or `shoppingCart`.
-   Stay away from abbreviations or short names like `a`, `b`, `c`, unless you really know what you’re doing.
-   Make names maximally descriptive and concise. Examples of bad names are `data` and `value`. Such names say nothing. It’s only okay to use them if the context of the code makes it exceptionally obvious which data or value the variable is referencing.
-   Agree on terms within your team and in your own mind. If a site visitor is called a “user” then we should name related variables `currentUser` or `newUser` instead of `currentVisitor` or `newManInTown`.

## Numbers
- JavaScript has only one type of number. Numbers can be written with or without decimals. 
- Extra large or small numbers can be written with scientific (exponent) notations: 
	- `123e5 = 12300000`
	- `123e-5 = 0.00123`
- JavaScript numbers are always stored as double presicion floating point numbers, following the international IEE 754 standard. 
	- This format stores numbers in 64 bits, where the number (the fraction) is stored in bits 0 to 51, the exponent in bits 52 to 62, and the sign in bit 63
- Integers (numbers without a period or exponent notation) are accurate up to 15 digits.
- The maximum number of decimals is 17.
- Floating point arithmetic is not always 100% accurate
	- Multiplication and division can be used to get more accurat answers

### Adding numbers and strings
- JavaScript **uses the + operator for both addition and concatenation**. Numbers are added. Strings are concatenated.
- If you add two numbers, the result will be a number
- If you add two strings, the result will be a string concatenation
- If you add a number and a string, the result will be a string concatenation
- If you add a string and a number, the result will be a string concatenation
- The JavaScript interpretor works from left to right. 
### Numeric strings
- JavaScript strings can have numeric content
- JavaScript will try to convert strings to numbers in all numeric operations
	- JavaScript will try to convert strings to numbers when dividing
	- JavaScript will try to convert strings to numbers when multiplying
	- JavaScript will try to convert strings to numbers when subtracting
	- **JavaScript will NOT convert strings to numbers when adding**
### NaN - Not a Number
- `NaN` is a JavaScript reserved word indicating that a number is not a legal number.Trying to do arithmetic with a non-numeric string will result in `NaN` (Not a Number)
	- However, if the string contains a numeric value , the result will be a number	
- You can use the global JavaScript function `isNaN()` to find out if a value is a not a number
- Watch out for `NaN`. If you use `NaN` in a mathematical operation, the result will also be `NaN`
	- Or the result might be a concatenation
- `NaN` is a number: `typeof NaN` returns `number`
### Infinity
- `Infinity` (or `-Infinity`) is the value JavaScript will return if you calculate a number outside the largest possible number
- Division by 0 (zero) also generates `Infinity`
- `Infinity` is a number: `typeof Infinity` returns `number`
### Hexadecimal
- JavaScript interprets numeric constants as hexadecimal if they are preceded by 0x
	- ex: 0xFF = 255
- Never write a number with a leading zero (like 07).
	- Some JavaScript versions interpret numbers as octal if they are written with a leading zero.
- By default, JavaScript displays numbers as **base 10** decimals.
	- But you can use the `toString()` method to output numbers from **base 2** to **base 36**.
	- Hexadecimal is **base 16**. Decimal is **base 10**. Octal is **base 8**. Binary is **base 2**.
### JavaScript Numbers as Objects
- Normally JavaScript numbers are primitive values created from literals
- But numbers can also be defined as objects with the keyword `new`
- Do not create Number objects.
	- The `new` keyword complicates the code and slows down execution speed.
	- Number Objects can produce unexpected results

- When using the `==` operator, x and y are **equal**, but when using the `===` operator, x and y are **not equal**
<pre>
let x = 500;  
let y = new Number(500);
</pre>
- Comparing two JavaScript objects **always** returns **false**.
## JavaScript Arithmetic Operators
Arithmetic operators perform arithmetic on numbers (literals or variables)

<pre>
Operator 		Description

+ 			Addition

- 			Subtraction

*			Multiplication

** 			Exponentiation

/ 			Division

% 			Modulus (Remainder)

++ 			Increment

--	 		Decrement
</pre>
### Arithmetic Operations
- A typical arithmetic operation operates on two numbers
- The two numbers can be literals,variables,or expressions
### Operators and Operands
- The numbers (in an arithmetic operation) are called **operands**
- The operation (to be performed between the two operands) is defined by an **operator**

- The **addition** operator (`+`) adds numbers
- The **subtraction** operator (`-`) subtracts numbers
- The **multiplication** operator (`*`) multiplies numbers
- The **division** operator (`/`) divides numbers
- The **modulus** operator (`%`) returns the division remainder

- In arithmetic, the division of two integers produces a **quotient** and a **remainder**.
- In mathematics, the result of a **modulo operation** is the **remainder** of an arithmetic division.

- The **increment** operator (`++`) increments numbers
- The **decrement** operator (`--`) decrements numbers
- The **exponentiation** operator (`**`) raises the first operand to the power of the second operand
- x ** y produces the same result as `Math.pow(x,y)`
### Operator Precedence 
- Operator precedence describes the order in which operations are performed in an arithmetic expression.
- Multiplication (`*`) and division (`/`) have higher **precedence** than addition (`+`) and subtraction (`-`)
- The precedence can be changed by using parentheses
	- When using parentheses, the operations inside the parentheses are computed first.
- When many operations have the same precedence (like addition and subtraction), they are computed from left to right
## Increment and decrement operators
Sometimes you'll want to repeatedly add or subtract one to or from a numeric variable value. This can be conveniently done using the increment (`++`) and decrement (`--`) operators.

`++var` increases that variable then returns it
`var++` returns that variable then increases it
## Assignment operators
The most common assignment operator is the = operator which assigns the variable on the left the value on the right. 

|Operator|Name|Purpose|Example|Shortcut for|
| :-: | :- | - | :-: | :-: |
| `+=`| Addition assignment	| Adds the value on the right to the variable value on the left, then returns the new variable value| `x += 4;`	| `x = x + 4;` |
| `-=`| Subtraction assignment| Subtracts the value on the right from the variable value on the left, and returns the new variable value| `x -= 3;` |`x = x - 3;`|
| `*=`|Multiplication assignment| Multiplies the variable value on the left by the value on the right, and returns the new variable value| `x *= 3;` | `x = x * 3;`|
| `/=`|Division assignment	|Divides the variable value on the left by the value on the right, and returns the new variable value| `x /= 5;` | `x = x / 5;`|

## Comparison operators
These operators are boolean and thus return a true/false value
|Operator|Name|Purpose|Example|
| :-: | :- | :-: | :-: |
|`===`|Strict equality|Tests whether the left and right values are identical to one another|`5 === 2 + 4`|
|`!==`|Strict-non-equality|Tests whether the left and right values are **not** identical to one another|`5 !== 2 + 3`|
|`<`|Less than|Tests whether the left value is smaller than the right one.|`10 < 6`|
|`>`|Greater than|Tests whether the left value is greater than the right one.|`10 > 20`|
|`<=`|Less than or equal to|Tests whether the left value is smaller than or equal to the right one.|`3 <= 2`|
|`>=`|Greater than or equal to|Tests whether the left value is greater than or equal to the right one.|`5 >= 4`|
	
## Data types
There are eight different data types in JS. Variables can hold any type of data and change the kind of data it holds.

### Number
The number type represents both integer and floating point numbers. 
The number type cannot represent integer values larger than (2^35)-1, or less than -1((2^35)-1)

Besides regular numbers there are so-called "special numeric values" which also belong to  this data type:`Infinity`, `-Infinity`, and `NaN`.

### BigInt
BigInt is a newer type that represents integers of arbitrary length. A `BigInt` value is created by appending `n` to the end of an integer. 

### String
A string in JS must be surrounded by quotes.
- Types of quotes:
	- Double quotes: `"Hello"`
	- Single quotes: `'Hello'`
	- Backticks: ```` ` ````

Double and single quotes are “simple” quotes. There’s practically no difference between them in JavaScript.

Backticks are “extended functionality” quotes. They allow us to embed variables and expressions into a string by wrapping them in `${…}`. The expression inside `${…}` is evaluated and the result becomes part of the string. 
### Boolean (logical type)
The boolean type only has two values: `true` and `false`.


### Null
The special `null` value does not belong to any of the types described above. It forms a separate type of its own which contains only the `null` value. 
Null is a special value which represents "nothing" or "value unknown". 

### Undefined
Special type, like null. Represents "value not assigned".
If a variable is declared but not assigned, then its value is `undefined`.

### Objects and Symbols
`Objects` are used to store colletions of data and more complex entities. Other types are called "primitive" because they can only contain one thing. 

The `symbol` type is used to create unique identifiers for objects. 
### The typeof operator
The `typeof` operator returns the type of the arugment. It supports two forms of syntax: `typeof x` and `typeof(x)`.
### Summary:
There are 8 basic data types in JavaScript.

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


## Strings 
Characters in strings can be escaoed by using \

#### Concatenating strings
Concatenate means "join together". Joining together strings in JS uses the plus (`+`) operator. 

#### Template literals
Template literals are **not** supported in IE, but are supported by most other browsers.

Another type of string syntax is **template literals**. Template literals are written with backticks, while tradition strings use  single or double quotes. 

Template literals can use *placeholders* when you want to include a variable or expression inside a string, by placing it inside a `${ }` construct. 

In order to split a traditional string over multiple lines, a newline character, \n ,has to be included. Template literals, however, respect the line breaks in the source code, so newline characters are no longer needed. 

### JavaScript String Methods
All string methods return a new string. They don't modify the original string.  
Formally said: Strings are immutable: Strings cannot be changed, only replaced.
#### String Length
The `length` property returns the length of a string. EX:
<pre>
let txt = "text";
let txtlength = txt.length;
</pre>
#### Extracting String Parts
Three methods for extracting a part of a string: 
- `slice(start, end)`
- `substring(start, end)`
- `substr(start, length)`
##### slice() Method
`slice()` extracts a part of a string and returns the extracted part in a new string. The method takes 2 parameters: the start positions, and the end position (end not included). EX:
```` JavaScript
let str = "Apple, Banana, Kiwi";  
let part = str.slice(7, 13);
````
This example sets the part variable to banana.

If a parameter is **negative**, the position is counted from the end of the string. EX: 
```` JavaScript
let str = "Apple, Banana, Kiwi";  
let part = str.slice(-12, -6);
````

If you omit the second parameter, the method wiill slice out the rest of the string
##### substring() Method
`substring()` is similar to `slice()`.
The difference is that `substring()` cannot accept negative indexes. EX: 
```` JavaScript
let str = "Apple, Banana, Kiwi";  
let part = substring(7, 13);
````
##### substr() Method
`substr()` is similar to `slice()`.The difference is that the second parameter specifies the **length** of the extracted part.
```` JavaScript>
let str = "Apple, Banana, Kiwi";  
let part = str.substr(7, 6);
````

#### replace() Method
The `replace()` method replaces a specified value with another value in a string: EX:
```` JavaScript>
let text = "Please visit Microsoft!";  
let newText = text.replace("Microsoft", "W3Schools");
````

- By default, the replace() method
	- replaces only the first match
	- is case sensititve
		- To repalce case *insensitive*, use a **regular expression** wtith an /i flag
- To replace all matches use a regualar expression with a /g flag (global match)

#### Converting to Upper and Lower Case
A string is converted to upper case with `toUpperCase()`
A string is converted to lower case with `toLowerCase()`:

#### The concat() Method
`concat()` joins two or more strings
The `concat()` method can be used instead of the plus operator.

#### String.trim()
The `trim()` method removes whitespace from both sides of a string

### Extracting String Characters
There are 3 methods for extracting string characters:
-   `charAt(_position_)`
-   `charCodeAt(_position_)`
-   Property access [ ]

#### charAt()
The `charAt()` method returns the character at a specified index (position) in a string

#### charCodeAt()
The `charCodeAt()` method returns the unicode of the character at a specified index in a string

The method returns a UTF-16 code (an integer between 0 and 65535).

#### Property Access
ECMAScript 5 (2009) allows property access [ ] on strings:

- Property access might be a little **unpredictable:**
	- It makes strings look like arrays (but they are not)
	- If no character is found, [ ] returns undefined, while charAt() returns an empty string.
	- It is read only. str[0] = "A" gives no error (but does not work!)

### Converting a String to an Array
A string can be converted to an array with the `split()` method.

If the separator is omitted, the returned array will contain the whole string in index [0].

If the separator is "", the returned array will be an array of single characters:

## String Properties

|Property|Description|
| - | - |
|constructor|Returns the string's constructor function
|length|Returns the length of a string|
|prototype|Allows you to add properties and methods to an object|

## String Methods

|Method|Description|
| - | :- |
|charAt()|Returns the character at the specified index (position)|
|charCodeAt()|Returns the Unicode of the character at the specified index|
|concat()|Joins two or more strings, and returns a new joined strings|
|endsWith()|Checks whether a string ends with specified string/characters|
|fromCharCode()|Converts Unicode values to characters|
|includes()|Checks whether a string contains the specified string/characters|
|indexOf()|Returns the position of the first found occurrence of a specified value in a string|
|lastIndexOf()|Returns the position of the last found occurrence of a specified value in a string|
|localeCompare()|Compares two strings in the current locale|
|match()|Searches a string for a match against a regular expression, and returns the matches|
|repeat()|Returns a new string with a specified number of copies of an existing string|
|replace()|Searches a string for a specified value, or a regular expression, and returns a new string where the specified values are replaced|
|search()|Searches a string for a specified value, or regular expression, and returns the position of the match|
|slice()|Extracts a part of a string and returns a new string|
|split()|Splits a string into an array of substrings|
|startsWith()|Checks whether a string begins with specified characters|
|substr()|Extracts the characters from a string, beginning at a specified start position, and through the specified number of character|
|substring()|Extracts the characters from a string, between two specified indices|
|toLocaleLowerCase()|Converts a string to lowercase letters, according to the host's locale|
|toLocaleUpperCase()|Converts a string to uppercase letters, according to the host's locale|
|toLowerCase()|Converts a string to lowercase letters|
|toString()|Returns the value of a String object|
|toUpperCase()|Converts a string to uppercase letters|
|trim()|Removes whitespace from both ends of a string|
|valueOf()|Returns the primitive value of a String object|

All string methods return a new value. They do not change the original variable.

## String HTML Wrapper Methods

The HTML wrapper methods return a string wrapped inside an HTML tag.

These are not standard methods, and may not work as expected.

|Method|Description|
| - | - |
|anchor()|Creates an anchor|
|big()|Displays a string using a big font|
|blink()|Displays a blinking string|
|bold()|Displays a string in bold|
|fixed()|Displays a string using a fixed-pitch font|
|fontcolor()|Displays a string using a specified color|
|fontsize()|Displays a string using a specified size|
|italics()|Displays a string in italic|
|link()|Displays a string as a hyperlink|
|small()|Displays a string using a small font|
|strike()|Displays a string with a strikethrough|
|sub()|Displays a string as subscript text|
|sup()|Displays a string as superscript text|

A **method** is a bit of functionality that is build into the language or into specific data types. 

## Conditionals
### Comparisons
- Greater than: `<`
- Less than: `>`
- Greater than or equals: `=<`
- Less than or equals: `>=`
- Equals: `==`
- Not equals: `!=`

All comparison operators return a boolean value and can be assigned to a variable, just like any value. 

#### String comparison
To see whether a string is greater than another, JavaScript uses the so-called “dictionary” or “lexicographical” order.

In other words, strings are compared letter-by-letter, in Unicode order.

The algorithm to compare two strings is simple:
1.  Compare the first character of both strings.
2.  If the first character from the first string is greater (or less) than the other string’s, then the first string is greater (or less) than the second. We’re done.
3.  Otherwise, if both strings’ first characters are the same, compare the second characters the same way.
4.  Repeat until the end of either string.
5.  If both strings end at the same length, then they are equal. Otherwise, the longer string is greater.

#### Comparison of different types
When comparing values of different types, JavaScript converts the values to numbers.

For boolean values, true becomes 1 and false becomes 0

#### Strict equality
A regular equality check `==` has a problem. It cannot differentiate `0` from `false`. This happens because operands of different types are converted to numbers by the equality operator `==`. An empty string, just like `false`, becomes a zero.

What to do if we’d like to differentiate `0` from `false`?

A strict equality operator `===` checks the equality without type conversion. In other words, if `a` and `b` are of different types, then `a === b` immediately returns `false` without an attempt to convert them.

There is also a “strict non-equality” operator `!==` analogous to `!=`.

The strict equality operator is a bit longer to write, but makes it obvious what’s going on and leaves less room for errors.

#### Comparison with null and undefined
There’s a non-intuitive behavior when `null` or `undefined` are compared to other values. 
`null === undefined; // false`  
`null == undefined; // true`

`null/undefined` are converted to numbers: `null` becomes `0`, while `undefined` becomes `NaN`.

	
### if else and else if
Conditional statements in JS:

-   `if` specifies a block of code to be executed, if a specified condition is true
-   `else` specifies a block of code to be executed, if the same condition is false
-   `else if` specifies a new condition to test, if the first condition is false
-   `switch` specifies many alternative blocks of code to be executed

### logical operators
The four logical operators in JavaScript:
- OR: `||`
- AND: `&&`
- NOT: `!`
- Nullish Coalescing: `??` 

#### Truthy values
A **truthy** value is a value that is considered `true` when encoutered in a boolean context. 

All values are truthy inless they are defined as **falsy**.

#### Falsy values
A **falsy** value is a value that is considered false when encountered in a boolean context. 

JavaScript uses type conversion to coerce any value to a boolean in contexts that require it, such as conditionals and [[loops]]

#### complete list of falsy values in JavaScript
|Value|Description|
| - | - |
|`false`|The keyword `false`|
|`0`|The `Number` zero (so, also `0.0`, etc., and `0x0`).|
|`-0`|The `Number` negative zero (so, also `-0.0`, etc., and `-0x0`).
|`0n`|The `BigInt` zero (so, also `0x0n`). Note that there is no `BigInt` negative zero — the negation of `0n` is `0n`.|
|`""`, `''`, ` `` `|Empty string value.|
|null| null — the absence of any value.|
|undefined|undefined — the primitive value.|
|NaN|NaN — not a number.|
|`document.all`|Objects are falsy if and only if they have the IsHTMLDDA internal slot.That slot only exists in `document.all` and cannot be set using JavaScript.|

### || OR
In classical programming, the logica OR is meant to manipulate boolean values only. If any of its arguments are true it returns `true`

In JavaScript, the operator is a little bit trickier and more powerful. The four possible logical combinations: 
```javascript
alert( true || true );   // true
alert( false || true );  // true
alert( true || false );  // true
alert( false || false ); // false
```
The result is always `true`, except when both operands are `false`.

Most of the time, `||` is used in an `if` statement to test if any of the given conditions is `true`


##### OR `||` finds the first truthy value
Given multiple OR’ed values:

```javascript
result = value1 || value2 || value3;
```

- The OR `||` operator does the following:
	- Evaluates operands from left to right.
	- For each operand, converts it to boolean. If the result is `true`, stops and returns the original value of that operand.
	- If all operands have been evaluated (i.e. all were `false`), returns the last operand.

In other words, a chain of OR `||` returns the first truthy value or the last one if no truthy value is found

This leads to some interesting usage compared to a “pure, classical, boolean-only OR”.

1.  Getting the first truthy value from a list of variables or expressions.
2.  Short-circuit evaluation
	- || processes its arguments until the first truthy value is reached, and then the value is returned immediately, without even touching the other argument. 


### && (AND)
AND returns true if both operands are truthy and false otherwise

#### AND && finds the first falsy value
Given multiple AND'ed values, the AND && operator does the following
-   Evaluates operands from left to right.
-   For each operand, converts it to a boolean. If the result is `false`, stops and returns the original value of that operand.
-   If all operands have been evaluated (i.e. all were truthy), returns the last operand.

In other words, AND returns the first falsy value or the last value if none were found.

The rules above are similar to OR. The difference is that AND returns the first _falsy_ value while OR returns the first _truthy_ one.

The precedence of AND `&&` operator is higher than OR `||`.

### ! (NOT)
The operator accepts a single argument and does the following:

1.  Converts the operand to boolean type: `true/false`.
2.  Returns the inverse value.

A double NOT `!!` is sometimes used for converting a value to boolean type. 
That is, the first NOT converts the value to boolean and returns the inverse, and the second NOT inverses it again. In the end, we have a plain value-to-boolean conversion.

The precedence of NOT `!` is the highest of all logical operators, so it always executes first, before `&&` or `||`.

