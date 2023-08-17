---
id: "Strings"
aliases:
  - "Strings"
  - "Strings in Elixir"
tags: ["elixir", "programming", "strings"]
---

## Strings

Elixir strings are sequences of bytes. They can be created using binary syntax (`<>`) and concatenated with other binaries.

Example:
```elixir
string = <<104,101,108,108,111>>
string <> <<0>>
```

### Charlists

Elixir also has charlists, enclosed with single quotes. Charlists are used less frequently than strings.

Example:
```elixir
'hełło'
```

### Graphemes and Codepoints

Codepoints represent Unicode characters and are encoded using UTF-8. Graphemes are a sequence of codepoints that render as a single character.

Example:
```elixir
string = "\u0061\u0301"
String.codepoints(string)
String.graphemes(string)
```

### String Functions

Key functions from the `String` module:
- `String.length/1`
- `String.replace/3`
- `String.duplicate/2`
- `String.split/2`

For more functions, see the [`String` module documentation](https://hexdocs.pm/elixir/String.html).

### Anagrams Exercise

A function to check anagram strings can be created using `String` module functions and Elixir's pattern matching.

Example:
```elixir
defmodule Anagram do
  def anagrams?(a, b) when is_binary(a) and is_binary(b) do
    sort_string(a) == sort_string(b)
  end

  def sort_string(string) do
    string
    |> String.downcase()
    |> String.graphemes()
    |> Enum.sort()
  end
end
```

The `anagrams?` function checks if two strings are anagrams by comparing their sorted graphemes.

```elixir
Anagram.anagrams?("Hello", "ohell")
```

This exercise showcases string manipulation in Elixir.