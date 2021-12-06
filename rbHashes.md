# rbHashes
- [[rbHashes#Creating Hashes|Creating Hashes]]
- [[rbHashes#Accessing Values|Accessing Values]]
- [[rbHashes#Adding and Changing Data|Adding and Changing Data]]
- [[rbHashes#Removing Data|Removing Data]]
- [[rbHashes#Methods|Methods]] 
- [[rbHashes#rbHashes#keys and values|#keys and #values]]
- [[rbHashes#Merging Two Hashes|Merging Two Hashes]]
- [[rbHashes#Symbols as Hash Keys|Symbols as Hash Keys]]


Ruby hashes are more advanced collections of data and are similar to objects in JS and Python

### Creating Hashes

```ruby
my_hash = { 
  "a random word" => "ahoy", 
  "Dorothy's math test score" => 94, 
  "an array" => [1, 2, 3],
  "an empty hash within a hash" => {} 
}
```

Its also possible to create a new hash by calling the #new method on the `Hash` class :

```ruby
my_hash = Hash.new
my_hash               #=> {}
```

### Accessing Values

Accessing values in a hash is done by calling a hash's value by key. 

```ruby
shoes = {
  "summer" => "sandals",
  "winter" => "boots"
}

shoes["summer"]   #=> "sandals"
```

If you try to access a key that doesn’t exist in the hash, it will return `nil`.

Hashes have a `fetch` method that will raise an error when you try to access a key that is not in your hash.

Alternatively, this method can return a default value instead of raising an error if the given key is not found.

```ruby
shoes.fetch("hiking", "hiking boots") #=> "hiking
```


### Adding and Changing Data

You can add a key-value pair to a hash by calling the key and setting the value, just like you would with any other variable.

```ruby
shoes["fall"] = "sneakers"
```

You can also use this approach to change the value of an existing key.

### Removing Data

Deleting data from a hash is simple with the hash’s `#delete` method, which provides the cool functionality of returning the value of the key-value pair that was deleted from the hash.

```ruby
shoes.delete("summer")    #=> "flip-flops"
shoes                     #=> {"winter"=>"boots", "fall"=>"sneakers"}
```

### Methods

Hashes respond to many of the same methods as arrays do since they both employ Ruby’s **Enumerable** module.


#### #keys and #values
A couple of useful methods that are specific to hashes are the `#keys` and `#values` methods, which very unsurprisingly return the keys and values of a hash, respectively. Note that both of these methods return _arrays_.

```ruby
books = { 
  "Infinite Jest" => "David Foster Wallace", 
  "Into the Wild" => "Jon Krakauer" 
}

books.keys      #=> ["Infinite Jest", "Into the Wild"]
books.values    #=> ["David Foster Wallace", "Jon Krakauer"]
```

#### Merging Two Hashes

 The values from the hash getting merged in (in this case, the values in `hash2`) overwrite the values of the hash getting merged _at_ (`hash1` here) when the two hashes have a key that’s the same.
 
 ```ruby
hash1 = { "a" => 100, "b" => 200 }
hash2 = { "b" => 254, "c" => 300 }
hash1.merge(hash2)      #=> { "a" => 100, "b" => 254, "c" => 300 }
```

#### Symbols as Hash Keys

You’ll almost always see symbols (like `:this_guy`) used as keys. This is predominantly because symbols are far more performant than strings in Ruby, but they also allow for a much cleaner syntax when defining hashes.

```ruby
# 'Rocket' syntax 
american_cars = { 
  :chevrolet => "Corvette", 
  :ford => "Mustang", 
  :dodge => "Ram" 
}
# 'Symbols' syntax
japanese_cars = { 
  honda: "Accord", 
  toyota: "Corolla", 
  nissan: "Altima" 
}
```

Regardless of which of the above two syntax options you use when creating a hash, they both create symbol keys that are accessed the same way.