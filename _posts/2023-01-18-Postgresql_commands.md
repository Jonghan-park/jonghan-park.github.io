---
title: "Postgresql commands"
header:
  image: /assets/postgresql.png
categories:
  - Postgresql
tags:
  - Postgresql
  - commands
---

I've collected some useful commands for capitalizing on postgresql.
It's going to keep updating whenever I found a command I need.

## ✅ All keywords should be upper case

SQL Cheat sheet

![Image sql](/assets/sqlcheatsheet.jpg)

Example)

```
CREATE TABLE ... (

);

SELECT * FROM ...;

```

---

### Connect database

```
 \c databasename
```

---

### Create a table

```
CREATE TABLE tablename(
  id SERIAL PRIMARY KEY,
  name VARCHAR(255),
  email VARCHAR(255),
  password TEXT,
  age INT
);
```
