# rbConditionalStatements

- [[rbConditionalStatements#TruthyAndFalsy|Truthy and Falsy]]
- [[rbConditionalStatements#BasicConditionalStatement|BasicConditionalStatement]]
- [[rbConditionalStatements#Boolean Logic|Boolean Logic]]
- [[rbConditionalStatements#Logical Operators|Logical Operators]]
- [[rbConditionalStatements#Case Statements|Case Statements]]
- [[rbConditionalStatements#Unless Statements|Unless Statements]]
- [[rbConditionalStatements#Ternary Operator|Ternary Operator]]
### TruthyAndFalsy

The **only false values** in [[Ruby]] are `nil` and `false`!

### BasicConditionalStatement
```ruby
if statement_to_be_evaluated == true
  # do something awesome...
end
```

If there is only one line of code to be evaluated inside the block, then you can rewrite the code to be more succinct and take up only one line:

```ruby
puts "string" if statement_to_be_evaluated
```

We often want to check a condition and run some code if it’s true but then run some other code if it’s false. This is done with an `if...else` statement.

A oneliner if statement must use `then`: 
```ruby
if x == 3 then puts "x is 3" end
```

If we need yet another conditional check we can use the `if...elsif...else` statement.

You can have as many `elsif` expressions as you want. The `else` clause is optional, but you usually want to provide some default value in case none of the previous expressions evaluate to `true`.

Because Ruby is such an expressive language, it also allows you to append the `if` condition at the very end.
```ruby
puts "x is 3" if x == 3
```


### Boolean Logic

- `==` (equals) returns `true` if the values compared are equal.
- `!=` (not equal) returns `true` if the values compared are not equal.
- `>` (greater than) returns `true` if the value on the left of the operator is larger than the value on the right.
- `<` (less than) returns `true` if the value on the left of the operator is smaller than the value on the right.
- `>=` (greater than or equal to) returns `true` if the value on the left of the operator is larger than or equal to the value on the right.
- `<=` (less than or equal to) returns `true` if the value on the left of the operator is smaller than or equal to the value on the right.
- `#eql?` checks both the value type and the actual value it holds.
- `#equal?` checks whether both values are the exact same object in memory. This can be slightly confusing because of the way computers store some values for efficiency. Two variables pointing to the same number will usually return `true`

The way computers store integers in memory is different from how strings are stored.

```ruby
a = 5
b = 5
a.equal?(b) #=> true
```
```ruby
a = "hello"
b = "hello"
a.equal?(b) #=> false
```

**The spaceship operator**

`<=>` (spaceship operator) returns the following:
-   `-1` if the value on the left is less than the value on the right;
-   `0` if the value on the left is equal to the value on the right; and
-   `1` if the value on the left is greater than the value on the right.

### Logical Operators
Logical operators are used to write expressions that contains more than one condition.
- `&&` (and)
	- The `&&` operator returns `true` if **both** the left and right expressions return `true`.
- `||` (or)
	- With the `||` operator, if the first expression evaluates to `true`, then the second expression is never checked because the complete expression is already `true`, and the code in the block is run.
- `!` (not)
	- he `!` operator reverses the logic of the expression.


Ruby follows an **order of precedence** when deciding how to evaluate multiple expressions. The following is a list of operations from highest order of precedence (top) to lowest (bottom).

1.  `<=`, `<`, `>`, `>=` - Comparison
2.  `==`, `!=` - Equality
3.  `&&` - Logical AND
4.  `||` - Logical OR

### Case Statements
Case statements process each condition in turn, and if the condition returns `false`, it will move onto the next one until a match is found. An `else` clause can be provided to serve as a default if no match is found.

As soon as a match is found, the value of that match is returned, and the case statement stops execution.

```ruby
grade = 'F'

did_i_pass = case grade #=> create a variable `did_i_pass` and assign the result of a call to case with the variable grade passed in
  when 'A' then "Hell yeah!"
  when 'D' then "Don't tell your mother."
  else "'YOU SHALL NOT PASS!' -Gandalf"
end
```

If you need to do some more complex code manipulation, you can remove the `then` keyword and instead place the code to be executed on the next line.

### Unless Statements

An `unless` statement works in the opposite way as an `if` statement: it only processes the code in the block if the expression evaluates to `false`.

### Ternary Operator (?)

The ternary operator is a one-line `if...else` statement that can make your code much more concise.

Its syntax is `conditional statement ? <execute if true> : <execute if false>`. You can assign the return value of the expression to a variable.