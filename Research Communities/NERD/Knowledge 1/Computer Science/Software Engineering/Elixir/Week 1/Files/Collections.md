## Lists
Lists are collections of values in Elixir. They may contain multiple types and non-unique values.

List creation:
```elixir
[3.14, :pie, "Apple"]
```

Lists are implemented as linked lists, making accessing length linear. Prepending is faster than appending.

List Concatenation:
```elixir
[1, 2] ++ [3, 4, 1]
```

List Subtraction:
```elixir
["foo", :bar, 42] -- [42, "bar"]
```

Head and Tail of Lists:
```elixir
hd [3.14, :pie, "Apple"]
tl [3.14, :pie, "Apple"]
```

## Tuples
Tuples are similar to lists but stored contiguously in memory. Accessing their length is fast, but modification is expensive.

Tuple creation:
```elixir
{3.14, :pie, "Apple"}
```

Tuples are often used to return additional information from functions.

## Keyword lists
Keyword lists are lists of two-element tuples with atom keys. They are ordered and allow duplicate keys.

Keyword list creation:
```elixir
[foo: "bar", hello: "world"]
```

Used for passing options to functions.

## Maps
Maps are key-value stores in Elixir. They allow keys of any type and are un-ordered.

Map creation:
```elixir
%{:foo => "bar", "hello" => :world}
```

Map access:
```elixir
map[:foo]
map["hello"]
```

Maps allow variable keys:
```elixir
key = "hello"
%{key => "world"}
```

Maps provide syntax for updates:
```elixir
%{map | foo: "baz"}
```

For creating a new key, use [`Map.put/3`](https://hexdocs.pm/elixir/Map.html#put/3):
```elixir
Map.put(map, :foo, "baz")
```

Maps with atom keys have a concise syntax:
```elixir
%{foo: "bar", hello: "world"}
```

Map keys can also be accessed using dot notation:
```elixir
map.hello
```
