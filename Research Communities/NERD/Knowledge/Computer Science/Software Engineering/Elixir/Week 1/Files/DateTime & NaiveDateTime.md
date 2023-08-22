---
id: "DateTime"
aliases:
  - "DateTime"
  - "DateTime in Elixir"
tags: ["elixir", "programming", "datetime", "naivedatetime"]
---

## Time

Elixir provides modules to work with time, date, and datetime. Let's explore these modules.

### Time

To get the current time, you can use `Time.utc_now` or create a `Time` struct using the sigil `~T`.

Example:
```elixir
Time.utc_now
~T[19:39:31.056226]
```

### Date

For dates without time information, use the `Date` module. You can get today's date with `Date.utc_today`.

Example:
```elixir
Date.utc_today
~D[2028-10-21]
```

### NaiveDateTime

`NaiveDateTime` holds both date and time but lacks timezone support.

Example:
```elixir
NaiveDateTime.utc_now
~N[2022-01-21 19:55:10.008965]
```

### DateTime

`DateTime` combines date, time, and timezone information. Use `DateTime.from_naive` to convert `NaiveDateTime` to `DateTime`.

Example:
```elixir
DateTime.from_naive(~N[2016-05-24 13:26:08.003], "Etc/UTC")
```

### Working with Timezones

Elixir requires the `tzdata` package for timezone data. Set it up globally in your configuration.

Example:
```elixir
config :elixir, :time_zone_database, Tzdata.TimeZoneDatabase
```

To convert between timezones, use `DateTime.shift_zone`.

Example:
```elixir
paris_datetime = DateTime.from_naive!(~N[2019-01-01 12:00:00], "Europe/Paris")
{:ok, ny_datetime} = DateTime.shift_zone(paris_datetime, "America/New_York")
```

For more advanced features, refer to the official documentation for [Time](https://hexdocs.pm/elixir/Time.html), [Date](https://hexdocs.pm/elixir/Date.html), [DateTime](https://hexdocs.pm/elixir/DateTime.html), and [NaiveDateTime](https://hexdocs.pm/elixir/NaiveDateTime.html). Consider using libraries like [Timex](https://github.com/bitwalker/timex) and [Calendar](https://github.com/lau/calendar) for additional functionality.