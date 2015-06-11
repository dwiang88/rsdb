# Introduction #

Explanation in how to insert new data into a table.

# Details #

Data insertion is did by the `insert` command.

Consider you have the table below.

```
table mytable
{
    name: string;
    password: md5;
}
```

## Single row insertion ##

To insert a new row in that table, do as below.

```
table mytable insert name = "John", password = "123";
```

The field name is optional if you are inserting data in the correct field order. So, the code above can be wrote as below.

```
table mytable insert "John", "123";
```

## Multiple rows insertion ##

If you have to insert multiple rows into `mytable`, you should do as below.

```
table mytable insert
{
    "Peter", "321";
    "Maxwell", "567";
    "Denise", "44667";
}
```

With more syntactical sugar.

```
table mytable
{
    insert
    {
        "Peter", "321";
        "Maxwell", "567";
        "Denise", "44667";
    }
}
```

## `insert` inside a table definition ##

The data can be inserted just in the table definition if you desire.

```
table mytable
{
    name: string;
    password: md5;

    insert
    {
        "John", "123";
        "Peter", "321";
        "Maxwell", "567";
        "Denise", "44667";
    }
}
```

The position of the `insert` inside the `table` block is irrelevant as the column definition will always be executed first.