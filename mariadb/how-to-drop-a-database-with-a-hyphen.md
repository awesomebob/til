# How to drop a database with a hyphen

Generally, it's not a great idea to use illegal characters in database names.
They require quoting and escaping, and cause headaches.

In case you accidentally created a database named `database-name`, here's how to get rid of it:

```
mysql -e 'DROP DATABASE `database-name`;'
```

Note that the database name is surrounded by backticks, and the whole SQL statement is surrounded by single quotes.
