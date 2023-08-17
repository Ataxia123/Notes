# Enums Overview
The `Enum` module includes over 70 functions for working with enumerables.
## Common Functions
## all?
`all?/2`: Returns `true` if all items in the collection satisfy the given function, otherwise `false`.

## any?
`any?/2`: Returns `true` if at least one item in the collection satisfies the given function, otherwise `false`.

## chunk_every
`chunk_every/2`: Breaks the collection into smaller groups of specified size.

## chunk_by
`chunk_by/2`: Groups elements of the collection based on a given function's return value.

## map_every
`map_every/3`: Applies a function to every nth item in the collection.

## each
`each/2`: Iterates over the collection without producing a new value.

## map
`map/2`: Applies a function to each item in the collection to create a new collection.

## min
`min/1`: Finds the minimum value in the collection.
`min/2`: Allows specifying a function to produce the minimum value if the collection is empty.

## max
`max/1`: Returns the maximum value in the collection.
`max/2`: Allows specifying a function to produce the maximum value if the collection is empty.

## filter
`filter/2`: Filters the collection based on a given function's evaluation.

## reduce
`reduce/3`: Reduces the collection to a single value using a given function.
Optionally, an initial accumulator can be provided.

## sort
`sort/1`: Sorts the collection using term ordering.
`sort/2`: Allows custom sorting using a provided function.
`sort/2` also supports `:asc` and `:desc` as sorting options.

## uniq
`uniq/1`: Removes duplicates from the collection.

## uniq_by
`uniq_by/2`: Removes duplicates from the collection using a custom uniqueness comparison function.

## Enum using the Capture operator (&)
The Enum module in Elixir offers functions that take anonymous functions as arguments to perform operations on iterables. These anonymous functions can be written in shorthand using the Capture operator (`&`).

### Using Capture operator with Anonymous Functions
Here's a typical example of passing an anonymous function to `Enum.map/2`:

```elixir
Enum.map([1, 2, 3], fn number -> number + 3 end)
# Result: [4, 5, 6]
```

The Capture operator simplifies this:

```elixir
Enum.map([1, 2, 3], &(&1 + 3))
# Result: [4, 5, 6]
```

You can also assign the anonymous function with the Capture operator to a variable and use it in `Enum.map/2`:

```elixir
plus_three = &(&1 + 3)
Enum.map([1, 2, 3], plus_three)
# Result: [4, 5, 6]
```

### Using Capture operator with Named Functions
First, let's create a named function and call it within an anonymous function for `Enum.map/2`:

```elixir
defmodule Adding do
  def plus_three(number), do: number + 3
end

Enum.map([1, 2, 3], fn number -> Adding.plus_three(number) end)
# Result: [4, 5, 6]
```

Refactor it to use the Capture operator:

```elixir
Enum.map([1, 2, 3], &Adding.plus_three(&1))
# Result: [4, 5, 6]
```

For the most concise syntax, you can directly call the named function without explicitly capturing the variable:

```elixir
Enum.map([1, 2, 3], &Adding.plus_three/1)
# Result: [4, 5, 6]
```

Using the Capture operator (`&`) can simplify your code and make it more readable when working with Enum functions in Elixir.