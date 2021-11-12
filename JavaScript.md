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
Op
erator 		Description

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