# rbLoops
- [[rbLoops#Break and Next|Break and Next]]
- [[rbLoops#Loop|Loop]]
- [[rbLoops#While Loop|While Loop]]
- [[rbLoops#Until Loop| Until Loop]]
- [[rbLoops#Ranges|Ranges]]
- [[rbLoops#For Loop|For Loop]]
- [[rbLoops#Times Loop|Times Loop]]
- [[rbLoops#Upto and Downto Loops|Upto and Downto Loops]]
- [[rbLoops#Iterators|Iterators]]
-  [[rbLoops#Iterators|Iterators]]
- [[rbLoops#Recursion|Recursion]]


Loops in [[Ruby]] are simply blocks of code that are continually repeated until a certain condition is met.

As with any other block in Ruby, the block passed to `loop` introduces a new scope. From inside the block, you can access variables that were initialized from outside of the block. However, from outside the block, you can't access any variables that were initiailized inside the block.


#### Break and Next

`Break` ends the loop, while next goes to the `next` iteration.


### Loop

The `loop` loop is Ruby’s loop that just won’t quit. It’s an infinite loop that will keep going unless you specifically request for it to stop, using the `break` command. Most commonly, `break` is used with a condition.

```ruby
i = 0
loop do
  puts "i is #{i}"
  i += 1
  break if i == 10
end
```

### While Loop

A `while` loop is similar to the `loop` loop except that you declare the condition that will break out of the loop up front.
```ruby
i = 0
while i < 10 do
 puts "i is #{i}"
 i += 1
end
```

One last note: unlike the `loop` method, `while` is *not implemented as a method*. One consequence of this difference is, that unlike `loop`, a `while` loop **does not have its own scope** -- the entire body of the loop is in the same scope as the code that contains the `while` loop
### Until Loop

The `until` loop is the opposite of the `while` loop. A `while` loop continues for as long as the condition is true, whereas an `until` loop continues for as long as the condition is false.

These two loops can therefore be used pretty much interchangeably. Ultimately, what your break condition is will determine which one is more readable.

```ruby
i = 0
until i >= 10 do
 puts "i is #{i}"
 i += 1
end
```

### Ranges

What if we know exactly how many times we want our loop to run? Ruby lets us use something called a [range](https://ruby-doc.org/core-2.7.1/Range.html) to define an interval. All we need to do is give Ruby the starting value, the ending value, and whether we want the range to be inclusive or exclusive.

```ruby
(1..5)      # inclusive range: 1, 2, 3, 4, 5
(1...5)     # exclusive range: 1, 2, 3, 4

# We can make ranges of letters, too!
('a'..'d')  # a, b, c, d
```


### For Loop

A `for` loop is used to iterate through a collection of information such as an *array or range*. These loops are useful if you need to do something a given number of times while also using an iterator.

```ruby
for i in 0..5
  puts "#{i} zombies incoming!"
end
```

### Times Loop

The times loop works by iterating through a loop a specified number of times and even throws in the bonus of accessing the number it’s currently iterating through.

```ruby
5.times do
  puts "Hello, world!"
end
```

```ruby
5.times do |number|
  puts "Alternative fact number #{number}"
end
```

### Upto and Downto Loops

The Ruby methods `#upto` and `#downto` do exactly what you’d think they do from their names. You can use these methods to iterate from a starting number either up to or down to another number, respectively.

```ruby
5.upto(10) {|num| print "#{num} " }     #=> 5 6 7 8 9 10

10.downto(5) {|num| print "#{num} " }   #=> 10 9 8 7 6 5
```

If you need to step through a series of numbers (or even letters) within a specific range, then these are the loops for you.


## Iterators

**Iterators** are methods that naturally loop over a given set of data and allow you to operate on each element in the collection. Use `do` `end` instead of culy braces if the operations are multiline.

```ruby


array_name = ['a', 'b', 'c', 'd']

array_name.each { |array_element| puts array_element}

```

## Recursion

**Recursion** is another way to create a loop in Ruby. Recursion is the act of calling a method from within itself.

```ruby
def doubler(start)
  puts start * 2
end
```