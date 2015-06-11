# Introduction #

Getting data from the database can be done by using the `query` command.

For the examples, consider the table below.

```
table mytable
{
    name: string;
    password: md5;
    lucky_numbers: number list;

    insert
    {
        "John", "123", (1, 3, 5, 7, 9);
        "Peter", "321", (7, 21, 42, 54);
        "Maxwell", "567", (16, 64, 256, 1024);
        "Denise", "44667", (13);
    }
}
```

# Retrieving all data from a table #

```
query mytable;
```

# Retrieving only a row #

```
query mytable where(name == "John");
```

# Retrieving just the specified columns #

```
query mytable get(name, password);
```

# Retrieving some columns of a specific row #

```
query mytable get(name, lucky_numbers) where(name == "Peter");
```