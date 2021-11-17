# jsFunctions

**Functions** allow you to store a piece of code that does a single task inside a defined block, and then call that code whenever you need it using a single short command — rather than having to type out the same code multiple times.
Functions are the main “building blocks” of the program. They allow the code to be called many times without repetition.

## Functions
##### Syntax: 
The `function` keyword goes first, then goes the _name of the function_, then a list of _parameters_ between the parentheses, and finally the code of the function, also named “the function body”, between curly braces.

``` javascript
function name(parameters, delimited, by, comma) {
  /* code */
}
```

-   Values passed to a function as parameters are copied to its local variables.
-   A function may access outer variables. But it works only from inside out. The code outside of the function doesn’t see its local variables.
-   A function can return a value. If it doesn’t, then its result is `undefined`.

#### Parameters
Some functions require **parameters** to be specified when you are invoking them — these are values that need to be included inside the function parentheses, which it needs to do its job properly.

When a value is passed as a function parameter, it’s also called an _argument_.

In other words, to put these terms straight:

-   A parameter is the variable listed inside the parentheses in the function declaration (it’s a declaration time term)
-   An argument is the value that is passed to the function when it is called (it’s a call time term).

#### Unknown amount of arguments provided

If you want a function to receive an undetermined amount of arguments then you can call on the arguments using the `arguments` object. 
The first argument is referred to by `arguments[0]` etc. 

##### Default values
If a function is called, but an argument is not provided, then the corresponding value becomes `undefined`. 

We can specify default values, that are used if omitted for a parameter in the function declaration using `=`. ex:
``` JavaScript
	function name(par1, par2="default value"){
		code
	} 
```

It is also possible to declare a default variable not in the function declaration, but rather at a later stage. This could f.ex be done either by having an if statement inside the function that checks whether the parameter === undefined, or it could be done using the || operator, returning a value when the argument is undefined or other falsy values. 
Another possibility is [[JavaScript#Nullish Coalescence ??|??]], or the nullish coalescing operator, which is better when mostly falsy values, such as 0 should be considered "normal".

#### Returning a value
A function can return a value back into the calling code as the result. 

The directive return can be in any place of the fuinction. When the execution reaches it, the function stops, and the value is returned to the calling code. 

It is possible to use return without a value. That causes the function to exit immediately.

If a function does not return a value, it is the same as if it returns `undefined`.


#### Scope

When you create a *function*, the variables and other things defined inside the function are inside their own separate **scope**, meaning that they are locked away in their own separate compartments, unreachable from code outside the functions.

The top level outside all your functions is called the **global scope**. Values defined in the global scope are accessible from everywhere in the code.

A function can be called from anywhere, even from another function. 

#### Naming a function

Functions are actions, so their names is usually a verb. 
- ex: 
	- show
	- get
	- calc
	- create
	- check

A function should do exactly what the name implies, no more. 

#### Summary
-   Values passed to a function as parameters are copied to its local variables.
-   A function may access outer variables. But it works only from inside out. The code outside of the function doesn’t see its local variables.
-   A function can return a value. If it doesn’t, then its result is `undefined`.

To make the code clean and easy to understand, it’s recommended to use mainly local variables and parameters in the function, not outer variables.

It is always easier to understand a function which gets parameters, works with them and returns a result than a function which gets no parameters, but modifies outer variables as a side-effect.

##### Function naming:
-   A name should clearly describe what the function does. When we see a function call in the code, a good name instantly gives us an understanding what it does and returns.
-   A function is an action, so function names are usually verbal.
-   There exist many well-known function prefixes like `create…`, `show…`, `get…`, `check…` and so on. Use them to hint what a function does.

 
 
 
## Function Expressions
The previous examples of functions has been what is called a *Function Declaration*

First, the *syntax*: how to differentiate between them in the code

**Function Declaration**:  a function, declared as a separate statement, in the main code flow:

```javascript
// Function Declaration
function sum(a, b) {
	return a + b;
}
```
    
**Function Expression**: a function, created inside an expression or inside another syntax construct. Here, the function is created at the right side of the “assignment expression”  =`:
```javascript
// Function Expression
let sum = function(a, b) {
	return a + b;
};
```

A Function Expression is not a code block, but rather an assignment. This means that a semicolon is recommended after the curly brackets. 

A **Function Expression** is created when the execution reaches it and is **usable only from that moment**.

A **Function Declaration** can be **called earlier than it is defined**.

When JavaScript prepares to run the script, it first looks for global Function Declarations in it and creates the functions. We can think of it as an “initialization stage”.

And after all Function Declarations are processed, the code is executed. So it has access to these functions

##### Function Expression Summary

-   Functions are values. They can be assigned, copied or declared in any place of the code.
-   If the function is declared as a separate statement in the main code flow, that’s called a “Function Declaration”.
-   If the function is created as a part of an expression, it’s called a “Function Expression”.
-   Function Declarations are processed before the code block is executed. They are visible everywhere in the block.
-   Function Expressions are created when the execution flow reaches them.

In most cases when we need to declare a function, a Function Declaration is preferable, because it is visible prior to the declaration itself. That gives us more flexibility in code organization, and is usually more readable.

So we should use a Function Expression only when a Function Declaration is not fit for the task. We’ve seen a couple of examples of that in this chapter, and will see more in the future.



## Arrow Functions
Single line arrow functions takes arguments from the left side of `=>` and evaluates the right side expression with them . 

With more complex arrow functions the expressions should be enclosed by curly braces, then use a normal return.

```javascript
let func = (arg1, arg2, ..., argN) => expression
```
…This creates a function `func` that accepts arguments `arg1..argN`, then evaluates the `expression` on the right side with their use and returns its result.

**Example: ** 

```javascript
let sum = (a, b) => a + b;
/* This arrow function is a shorter form of:*/

let sum = function(a, b) {
  return a + b;
};
```

If we have only one argument, then parentheses around parameters can be omitted.
**Example**
```javascript
let double = n => n * 2;
```
If there are no arguments, paretheses will be empty but should still be present. 
**Example**
```javascript
let sayHi = () => alert("Hello!");
```

##### Summary
- Arrow functions are handy for one-liners. They come in two flavors:
	1.  Without curly braces: `(...args) => expression` – the right side is an expression: the function evaluates it and returns the result.
	2.  With curly braces: `(...args) => { body }` – brackets allow us to write multiple statements inside the function, but we need an explicit `return` to return something.

## JavaScript Call Stack
JavaScript engine uses a **call stack** to manage execution contexts: the Global Execution Context and Function Execution Contexts.

The call stack works based on the LIFO principle, i.e. last-in-first-out. 

Whenever a function is called, the JavaScript ebgube creates  a Function Execution Context for the function, pushes it on top of the Call Stack, and starts executing the function. 

If a function calls another function, the JavaScript engine pops it off the call stack and resumes the execution where it left off in the last code listing. 

The script will stop when the call stack is empty. 

#### Stack Overlow
The call stack has a fixed size, depending on the implementation of the host enviroment. 
If the number of the execution contets exceeds the size of the stack, a stack overflow will occur. 

#### Asynchronous JavaScript
JavaScript is single-threaded, and thus has only one call stack, and can only do one thing at a time.  In order to carry asynchronous tasks, such as callbacks, promises, and async/await, JS uses the event loop (not covered). 


