# rbVariables
- [[rbVariables#Variables are References|Variables are References]]
- [[rbVariables#Variable Scope|Variable Scope]]
- [[rbVariables#Types of Variables|Types of Variables]]
	- [[rbVariables#Constant|Constant]]
	- [[rbVariables#Global variables|Global variables]]
	- [[rbVariables#Class variables|Class variables]]
	- [[rbVariables#Instance variables|Instance variables]]
	- [[rbVariables#Local variables|Local variables]]


**Variables** are used to store information to be referenced and manipulated in a computer program.

https://launchschool.com/books/ruby/read/variables

Variable names should always be lowercase, and multiple words that make up a variable name should be split by an underscore. This is known as **snake_case**.

#### Variables are References

The information you name with a variable is stored in memory on your computer, so a variable is effectively a reference or a pointer to that address in memory. This is important to know as it can sometimes be the cause of unexpected behavior from your code, for example when assigning a variable to another variable.

#### Variable Scope
A variable's scope determines where in a program a variable is available for use. A variable's scope is defined by where the variable is initialized or created. In Ruby, variable scope is defined by a **method definition** or by a **block**.

**[[rbMethods]] definition**: 
```ruby
def method_name(argument_one, argument_two)
  code to be executed
end
```

**Executing a [[rbMethods]]**: 
```ruby
method_name argument_one, argument_two
```


**Blocks**
In terms of variable scope, methods have self-contained scope. That means that you can't refer to or modify any variables that aren't initialized inside the method's body, and none of the variables initialized by the method are available outside the method's body.

A block is a piece of code that follows a method's invocation, delimited by either curly braces `{}` or `do/end`:

```ruby
total = 0
[1, 2, 3].each { |number| total += number }
puts total # 6
```

```ruby
total = 0
[1, 2, 3].each do |number|
  total += number
end
puts total # 6
```

In the examples above, `{ |number| ... }` is a block, as is `do |number| ... end`. Though they look different, the behavior is identical. In both cases, the code can access and modify variables that are defined outside of the block. Thus, both blocks can access and modify `total`. However, any variables initialized inside the block (such as `number`) can't be accessed by the outer code.

**Inner scope can access variables initialized in an outer scope, but not vice versa.**

Be aware that not all `do...end` pairs imply a block.  In particular, a `do...end` on a `for` or `while` loop is not a block.

The key distinguishing factor for deciding whether code delimited by `{}` or `do/end` is considered a block (and thereby creates a new scope for variables), is seeing if the `{}` or `do/end` immediately follows a method invocation. 

### Types of Variables

#### Constant
Constants are declared by capitalizing every letter in the variable's name, per Ruby convention. They are used for storing data that never needs to change.

While most programming languages do not allow you to change the value assigned to a constant, Ruby does.

Constants cannot be declared in method definitions, and are available throughout your application's scopes.
#### Global variables
Global variables are declared by starting the variable name with the dollar sign (`$`). These variables are available throughout your entire app, overriding all scope boundaries. Rubyists tend to stay away from global variables as there can be unexpected complications when using them.
#### Class variables
Class variables are declared by starting the variable name with two `@` signs. These variables are accessible by instances of your class, as well as the class itself. When you need to declare a variable that is related to a class, but each instance of that class does not need its own value for this variable, you use a class variable. Class variables must be initialized at the class level, outside of any method definitions. They can then be altered using class or instance method definitions.
#### Instance variables
Instance variables are declared by starting the variable name with one `@` sign. These variables are available throughout the current instance of the parent class. Instance variables can cross some scope boundaries, but not all of them.
##### Local variables
Local variables are the most common variables you will come across and obey all scope boundaries. These variables are declared by starting the variable name with neither `$` nor `@`, as well as not capitalizing the entire variable name. 
