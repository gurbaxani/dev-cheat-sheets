# Ruby Methods Cheat Sheet

## 1. `inspect` and `to_s`
`inspect`: Provides a detailed string representation of an object, useful for debugging.

```ruby
arr = [1, 2, 3]
puts arr.inspect  # => "[1, 2, 3]"
```

`to_s`: Provides a string representation suitable for end-user display.

```ruby
number = 123
puts number.to_s  # => "123"`
```

## 2. `class`
Returns the class of the object.

```ruby
str = "hello"
puts str.class  # => String

num = 42
puts num.class  # => Integer
```

## 3. `respond_to?`
Checks if the object responds to a specified method.

```ruby
str = "hello"
puts str.respond_to?(:upcase)  # => true
puts str.respond_to?(:unknown_method)  # => false
```

## 4. `nil?`
Returns true if the object is nil.

```ruby
x = nil
puts x.nil?  # => true

y = "hello"
puts y.nil?  # => false
```

## 5. Enumerable Methods (`each`, `map`, `select`, `reject`)

`each`: Iterates over each element of a collection.

```ruby
[1, 2, 3].each do |n|
  puts n
end
# Output:
# 1
# 2
# 3
```

`map`: Transforms each element of a collection and returns a new array with the transformed elements.

```ruby
arr = [1, 2, 3]
new_arr = arr.map { |n| n * 2 }
puts new_arr.inspect  # => [2, 4, 6]
```

`select`: Returns a new array with elements that match a condition.

```ruby
arr = [1, 2, 3, 4]
even_numbers = arr.select { |n| n.even? }
puts even_numbers.inspect  # => [2, 4]
```

`reject`: Returns a new array with elements that do not match a condition.

```ruby
arr = [1, 2, 3, 4]
odd_numbers = arr.reject { |n| n.even? }
puts odd_numbers.inspect  # => [1, 3]
```

## 6. `length` and `size`

`length`: Returns the number of elements in a collection or the length of a string.

```ruby
arr = [1, 2, 3]
puts arr.length  # => 3

str = "hello"
puts str.length  # => 5
```

`size`: Alias for #length, used interchangeably.

```ruby
arr = [1, 2, 3]
puts arr.size  # => 3

str = "hello"
puts str.size  # => 5
```

## 7. `include?`

Checks if a collection includes a specific element.

```ruby

arr = [1, 2, 3]
puts arr.include?(2)  # => true
puts arr.include?(4)  # => false

str = "hello"
puts str.include?("ell")  # => true
puts str.include?("xyz")  # => false
```

## 8. `dup` and `clone`

`dup`: Creates a shallow copy of an object.

```ruby
original = [1, 2, 3]
copy = original.dup
copy.push(4)
puts original.inspect  # => [1, 2, 3]
puts copy.inspect      # => [1, 2, 3, 4]
```

`clone`: Creates a copy of the object including singleton methods and frozen state.

```ruby
original = "hello"
original.freeze
clone = original.clone
puts clone.frozen?  # => true
```

## 9. `to_i`, `to_f`, `to_s`

`to_i`: Converts an object to an integer.

```ruby

str = "123"
puts str.to_i  # => 123

float_str = "12.34"
puts float_str.to_i  # => 12
```

`to_f`: Converts an object to a float.

```ruby

str = "12.34"
puts str.to_f  # => 12.34

int_str = "123"
puts int_str.to_f  # => 123.0
```

`to_s`: Converts an object to a string.

```ruby
num = 456
puts num.to_s  # => "456"

float_num = 78.9
puts float_num.to_s  # => "78.9"
```

## 10. `instance_of`? and `is_a?`

`instance_of?`: Checks if the object is an instance of a specific class.

```ruby

str = "hello"
puts str.instance_of?(String)  # => true
puts str.instance_of?(Object)  # => false
```

`is_a?`: Checks if the object is an instance of a class or a subclass of it.

```ruby
str = "hello"
puts str.is_a?(String)  # => true
puts str.is_a?(Object)  # => true
```

## 11. `==` and `eql?`

`==`: Checks for equality between two objects.

```ruby

str1 = "hello"
str2 = "hello"
puts str1 == str2  # => true

num1 = 10
num2 = 20
puts num1 == num2  # => false
```

`eql?`: Checks for equality with stricter definition (often used in hashes for key comparison).

```ruby

 hash1 = { a: 1 }
 hash2 = { a: 1 }
 puts hash1.eql?(hash2)  # => true

 str1 = "hello"
 str2 = "hello"
 puts str1.eql?(str2)  # => true
```

## 12. `freeze`
Prevents further modifications to the object.
```ruby

str = "hello"
str.freeze
# str << " world"  # This will raise a RuntimeError: can't modify frozen String
```

## 13. `methods` and `public_methods`

`methods`: Lists all methods available on an object.

```ruby

str = "hello"
puts str.methods.sort  # List of all methods, sorted alphabetically
```

`public_methods`: Lists only the public methods.

```ruby

str = "hello"
puts str.public_methods.sort  # List of public methods, sorted alphabetically
```
