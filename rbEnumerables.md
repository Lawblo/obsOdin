# rbEnumerables
[[Ruby]]

https://ruby-doc.org/core-2.6.1/Enumerable.html

The `Enumerable` mixin provides collection classes with several traversal and searching methods, and with the ability to sort. The class must provide a method `each`, which yields successive members of the collection. If `Enumerable#max`, `#min`, or `#sort` is used, the objects in the collection must also implement a meaningful `<=>` operator, as these methods rely on an ordering between members of the collection.

When you use an **enumerable method with a hash**, you need to set up **block variables for both the key and the value**

## Enumberables Methods


### The `#each` Method

Calling `#each` on an array will iterate through that array and will yield each element to a code block, where a task can be performed

`#each` **returns the original array or hash** regardless of what happens inside the code block.

```ruby
friends = ['Sharon', 'Leo', 'Leila', 'Brian', 'Arun']

friends.each { |friend| puts "Hello, " + friend }

				*or*

friends.each do
	|friend| puts "Hello, " + friend 
end

#=> Hello, Sharon
#=> Hello, Leo
#=> Hello, Leila
#=> Hello, Brian
#=> Hello, Arun

#=> ["Sharon", "Leo", "Leila", "Brian" "Arun"]
```

Let’s break down this syntax:

-   `friends` is the array that contains strings of your friends’ names.
-   `.each` is the enumerable method you are calling on your `friends` array.
-   `{ |friend| puts "Hello, " + friend }` is a **block**, and the code inside this block is run for each element in your array. Because we have 5 friends in our array, this block will be run 5 times, once with each of the 5 elements.
-   Within the block, you’ll notice that we have `|friend|`, which is known as a **block variable**. This is the element from your array that the block is currently iterating over. You can use any variable name that you find helpful here; in this example, we could have used `|x|`, but `|friend|` is more descriptive of what each element is. In the first iteration, the value of `|friend|` will be `'Sharon'`; in the second iteration, its value will be `'Leo'`; in the third, `'Leila'`; and so on until it reaches the end of the array.


`#each` also works for hashes with a bit of added functionality. By default, each iteration will yield both the key and value individually or together (as an array) to the block depending on how you define your block variable

### The `#each_with_index` Method

This method is nearly the same as `#each`, but it provides some additional functionality by yielding two **block variables** instead of one as it iterates through an array. The first variable’s value is the element itself, while the second variable’s value is the index of that element within the array.

### The `#map` Method

The `#map` method (also called `#collect`) transforms each element from an array according to whatever block you pass to it and returns the transformed elements in a new array.

### The `#select` Method

The `#select` method (also called `#filter`) passes every item in an array to a block and returns a new array with only the items for which the condition you set in the block evaluated to `true`.

### The `#reduce` Method

The `#reduce` method (also called `#inject`) reduces an array or hash down to a single object. You should use `#reduce` when you want to get an output of a single value.



```ruby
my_numbers = [5, 6, 7, 8]

my_numbers.reduce { |sum, number| sum + number }
#=> 26
```

The first block variable in the `#reduce` enumerable (`sum` in this example) is known as the **accumulator**. The result of each iteration is stored in the accumulator and then passed to the next iteration. The accumulator is also the value that the `#reduce` method returns at the end of its work. By default, the initial value of the accumulator is the first element in the collection, so for each step of the iteration, we would have the following:

1.  Iteration 0: sum = 5 + 6 = 11
2.  Iteration 1: sum = 11 + 7 = 18
3.  Iteration 2: sum = 18 + 8 = 26

We can also set a different initial value for the accumulator by directly passing in a value to the `#reduce` method.

### `#bang` Methods

**Bang methods** can be easily identified by their exclamation marks (`!`) at the end of their name. 

All bang methods are **destructive** and modify the object they are called on. 

Many of the enumerable methods that return new versions of the array or hash they were called on have a bang method version available, such as `#map!` and `#select!`.




