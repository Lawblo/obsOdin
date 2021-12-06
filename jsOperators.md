# JsOperators
[[JavaScript]]


## jsArithmetic Operators
Arithmetic operators perform arithmetic on numbers (literals or variables)

|Operator|Description|
| - | - |
|+|Addition|
|-|Subtraction|
|* |Multiplication|
|** |Exponentiation|
|/|Division|%|Modulus (Remainder)|
|++|Increment|
|--|Decrement|

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

### Increment and decrement operators
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
	