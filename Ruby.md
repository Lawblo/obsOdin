# Ruby

*the language designed specifically for programmer happiness*

## Basic Data Types

Ruby is a strongly object-oriented language, which means that absolutely *everything in Ruby is an object*, even the most basic data types. 

Four of Ruby’s basic data types: 
- Numbers (
	- integers
	- floats)
- Strings
- Symbols
- Booleans 
	- `true`
	- `false`
	- `nil`).



### Numbers

Integers are whole numbers, while floats contain a decimal point. When doing arithmetic with two integers in Ruby, the result will always be an integer. 

In order to get an accurate answer, replace one of the integers in the expression with a float. 

#### Converting Number Types
```ruby
# To convert an integer to a float:
13.to_f   #=> 13.0

# To convert a float to an integer:
13.0.to_i #=> 13
13.9.to_i #=> 13 -- NO ROUNDING
```

#### Some Useful Number Methods

`#even?` - returns true if even, and false if not
`#odd?` - returns true if oddand false if not


### Strings
Can be formed with either double or single quotation marks. 

String interpolation and the escape characters that we’ll discuss soon both only work inside double quotation marks, not single quotation marks.

All string methods can be found at https://ruby-doc.org/core-2.7.1/String.html

#### Concatenation
```ruby
# With the plus operator:
"Welcome " + "to " + "Odin!"    #=> "Welcome to Odin!"

# With the shovel operator:
"Welcome " << "to " << "Odin!"  #=> "Welcome to Odin!"

# With the concat method:
"Welcome ".concat("to ").concat("Odin!")  #=> "Welcome to Odin!"
```

#### Substrings
```ruby
"hello"[0]      #=> "h"

"hello"[0..1]   #=> "he"

"hello"[0, 4]   #=> "hell"

"hello"[-1]     #=> "o"
```
#### Escape characters
Again, only works inside *double* quotation marks

```ruby
\\  #=> Need a backslash in your string?
\b  #=> Backspace
\r  #=> Carriage return, for those of you that love typewriters
\n  #=> Newline. You'll likely use this one the most.
\s  #=> Space
\t  #=> Tab
\"  #=> Double quotation mark
\'  #=> Single quotation mark
```

#### Interpolation
String interpolation allows you to evaluate a string that contains placeholder variables.
Only with *double* quotes.

```ruby
name = "Odin"

puts "Hello, #{name}" #=> "Hello, Odin"
puts 'Hello, #{name}' #=> "Hello, #{name}"
```


#### capitalize

```ruby
"hello".capitalize #=> "Hello"
```

#### include?

```ruby
"hello".include?("lo")  #=> true

"hello".include?("z")   #=> false
```

#### upcase

```ruby
"hello".upcase  #=> "HELLO"
```

#### downcase

```ruby
"Hello".downcase  #=> "hello"
```

#### empty?

```ruby
"hello".empty?  #=> false

"".empty?       #=> true
```

#### length

```ruby
"hello".length  #=> 5
```

#### reverse

```ruby
"hello".reverse  #=> "olleh"
```

#### split

```ruby
"hello world".split  #=> ["hello", "world"]

"hello".split("")    #=> ["h", "e", "l", "l", "o"]
```

#### strip

```ruby
" hello, world   ".strip  #=> "hello, world"
```

### Symbols