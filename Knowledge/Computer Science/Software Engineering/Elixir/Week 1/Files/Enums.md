# Overview

The `Enum` module includes over 70 functions for working with enumerables.
All the collections that we learned about in the previous lesson, except for tuples, are enumerables.

# Common Functions

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

# Enum using the Capture operator (&)

Many functions within the Enum module in Elixir take anonymous functions as an argument, which can be written shorthand using the Capture operator (&).
Examples show how to implement the capture operator with both anonymous and named functions.
