# Simplified Ruby

## What is it?

Simplified Ruby is a minimal subset of the Ruby syntax that allows to take
any problem description and turn it into idiomatic, easy to understand and
[boring](https://blog.sundaycoding.com/blog/2018/11/22/boring-ruby-code/)
Ruby code.

## Motivation

Ruby has a lot of features, quirks, and ways to solve the same problem.
I believe that you can take 20% of its syntax and still be able to write code
that does the job. This is especially true when you're using a framework (like
Ruby on Rails) and a lot of technical problems are being handled for you.

Limiting yourself to Simplified Ruby shifts the focus from technical problems
(exciting, but your company probably won't earn money for solving them) to
business domain problems (here's your real leverage). You end up with code that
is easy to read, easy to understand for your colleagues regardless of their seniority, and easy to delete.

This project can also be useful:
- when introducing people to programming
- to answer the question "how much Ruby syntax do I need to start writing Ruby on
  Rails applications?"
- during technical interviews for introductory Ruby positions
- for company career ladder to define "basic Ruby knowledge"

## Syntax

### simple types - String, Symbol, Fixnum, Float, nil, booleans

```ruby

"adam"
:adam
56
3.4
nil
true
false
```

### method call - `.`

```ruby
"adam".upcase
```

### arthimetical operators - `+, -, *, /, **, %`

```ruby
2 + 5.4
23 - 10
10 * 2
9 / 2
2 ** 3
8 % 3
```

### string interpolation

```ruby
"this is #{4}."
```

### comparison operators

```ruby
2 + 2 == 4
3 != 4
```

### logical operators - `&&, ||, !`

```ruby
"adam".length.zero? && 2 + 2 == 4
"adam".length.zero? || 2 + 2 == 4
!"adam".length.zero?
```

### conditional statements - `if / elsif / else`

```ruby
if "adam".length.zero?
  "awesome"
elsif 2 + 2 == 4
  3
else
  "something else"
end

"test" if 2 + 2 == 4
```

### container types - Array, Hash

```ruby
[1, 2, 3]
{ "age" => 3 }
```

### short-hand notation for Hash with symbol keys

```ruby
{ age: 3 }
```

### local variables

```ruby
name = "adam"
```

### assignment operator

```ruby
age = 2 + 3
age = "five"
```

### defining methods

```ruby
def my_method(argument)
  "I got #{argument}"
end
```

### `return`

```ruby
def my_method(argument)
  return "a" if argument.zero?

  "bbb"
end
```

### keyword arguments

```ruby
def my_method(argument, name:, age: 18, city: nil)
end
```

### comments

```ruby
# this is how it works
```

### blocks

```ruby
[1, 2].map do |element|
  element * 2
end
```

### defining a class

```ruby
class User
end
```

### `new`

```ruby
user = User.new("adam")
```

### instance method

```ruby
class User
  def name
    "adam"
  end
end
```

### instance variable

```ruby
class User
  def give_name(name)
    @name = name
  end

  def name
    @name
  end
end
```

### initialize

```ruby
class User
  def initialize(name)
    @name = name
  end
end
```


### `private`

```ruby
class User
  def introduce
    "I am #{age}"
  end

  private

  def age
    4
  end
end
```

### `self`

```ruby
class User
  def car
    Car.new(self)
  end
end
```

### class method

```ruby
class User
  def self.give_me_three
    [User.new, User.new, User.new]
  end
end
```


### constant inside a class

```ruby
class User
  CODE_LENGTH = 3

  def code(name)
    name.slice(0, CODE_LENGTH)
  end
end
```

### inheritance - `<`

```ruby
class User
  def roles
    []
  end
end

class Supervisor < User
  def roles
    ["admin", "supervisor"]
  end
end
```

### `super`

```ruby
class Supervisor < User
  def code(name)
    "#{super("ADMIN")} #{super}"
  end
end
```

### nested classes

```ruby
class Users
  class Admin
  end
end

Users::Admin.new
```


### `attr_reader, attr_writer, attr_accessor`

```ruby
class User
  attr_reader :name
  attr_writer :ago
  attr_accessor :city
end
```


### `||=`

```ruby
class User
  def give_name(name)
    @name ||= name
  end
end
```

### `begin / rescue / raise`

```ruby
begin
  2 + 2
  raise "error"
  4 * 7
rescue => ex
  "Aaaa #{ex}!!!"
end
```
