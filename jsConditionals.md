# jsConditionals

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

	
## if...else and else if

Conditional statements in JS:
-   `if` specifies a block of code to be executed, if a specified condition is true
-   `else` specifies a block of code to be executed, if the same condition is false
-   `else if` specifies a new condition to test, if the first condition is false
-   `switch` specifies many alternative blocks of code to be executed

##### basic if...else syntax
<pre>
if (condition) {
  code to run if condition is true
} else {
  run some other code instead
}
</pre>

The else block of code is not neccessary.

Shorthand syntax without curly brackets: 
<pre>
if (condition) code to run if condition is true
else run some other code instead
</pre>

### switch

#### pseudocode
<pre>
switch (expression) {
  case choice1:
    run this code
    break;

  case choice2:
    run this code instead
    break;

  // include as many cases as you like

  default:
    actually, just run this code
}
</pre>

1.  The keyword `switch`, followed by a set of parentheses.
2.  An expression or value inside the parentheses.
3.  The keyword `case`, followed by a choice that the expression/value could be, followed by a colon.
4.  Some code to run if the choice matches the expression.
5.  A `break` statement, followed by a semi-colon. If the previous choice matches the expression/value, the browser stops executing the code block here, and moves on to any code that appears below the switch statement.
6.  As many other cases (bullets 3–5) as you like.
7.  The keyword `default`, followed by exactly the same code pattern as one of the cases (bullets 3–5), except that `default` does not have a choice after it, and you don't need to `break` statement as there is nothing to run after this in the block anyway. This is the default option that runs if none of the choices match.

### Ternary operator (?)
Syntax:`(condition) ? run this code : run this code instead`


### logical operators
The four logical operators in JavaScript:
- OR: `||`
- AND: `&&`
- NOT: `!`
- Nullish Coalescing: `??`


##### summary
-   `&&` — AND; allows you to chain together two or more expressions so that all of them have to individually evaluate to `true` for the whole expression to return `true`.
-   `||` — OR; allows you to chain together two or more expressions so that one or more of them have to individually evaluate to `true` for the whole expression to return `true`.

#### Truthy values
A **truthy** value is a value that is considered `true` when encoutered in a boolean context. 

All values are truthy inless they are defined as **falsy**.

#### Falsy values
A **falsy** value is a value that is considered false when encountered in a boolean context. 

JavaScript uses type conversion to coerce any value to a boolean in contexts that require it, such as conditionals and [[jsLoops]]

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

### Nullish Coalescence ??
- `??` returns the first argument if it’s not `null/undefined`. Otherwise, the second one.
- ex: `a ?? b`:
	- if `a` is defined, then `a`,
	- if `a` isn’t defined, then `b`.

#### ?? vs ||
|| returns the first *truthy* value, while ?? returns the first *defined* value

`??` works best when most falsy values, such as 0, should be considered "normal".
