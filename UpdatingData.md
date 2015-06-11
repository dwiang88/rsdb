# Introduction #

There is a few ways to update data on the database. There is a way for single row update and multiple rows update.

# Updating a table row #

```
update mytable
{
    where (name == "John") name = "Peter";
}
```

Or, in most short way.

```
update mytable where (name == "John") name = "Peter";
```

# Updating multiple columns in a single row #

```
update mytable
{
    where (name == "John")
    {
        name = "Peter";
        age = 42;
    }
}
```

# Updating multiple rows #

```
update mytable
{
    where (age >= 42 && name != "Anderson")
    {
        position = "Senior";
    }
}
```

## Multiple conditions ##

```
update mytable
{
    where (name matchs "^J") // Starts with 'J'
    {
        team = "The Jays";
    }
    where (surname matchs "Smith") // surname contains "Smith"
    {
        team = "The Agents";
    }
}
```

# Updating all rows #

```
update mytable
{
    access = "user";
    password = "123";
}
```