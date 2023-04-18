---
title: "Postgresql"
header:
  image: /assets/postgresql.png
categories:
  - Postgresql
tags:
  - Postgresql
---

## What is PostgreSQL?

- PostgreSQL is open-source relational database management system (RDBMS)
- A lot of startups and large companies use PostgreSQL to store their data safely.
- Postgres uses SQL as main query language.

## How data is stored?

- Stores data in tables
  - Columns
  - Rows

## All SQL commands should be Uppercase.

## I should finish the each command by using 'Semicolon' at the end of the line.

```js
CREATE DATABASE jonghan;
```

## When there is a error before trying to use 'psql' command in terminal.

- Add PATH

## To quit out of it

- \q

## For getting help

- help

## For getting lots of help

- \?

## To see all database list

- \l

## To create a database

- CREATE DATABASE name;

## How to connect a database

- psql -h localhost -p 5432 -U username databasename
- ex) psql -h localhost -p 5432 -U jonghanpark testDB

Above command is one way to connect to the database, and below command is another way to connect to the database.

- (If you are already logged in some database) Type \c databasename
- ex) \c testDB

## To get rid of a database

- DROP DATABASE databasename;
- ex) DROP DATABASE testDB;

## To create a table

```js
CREATE TABLE table_name (
  Column name + data type + constraints if any
)

CREATE TABLE person (
  id int,
  first_name VARCHAR(50),
  last_name VARCHAR(50),
  gender VARCHAR(6),
  date_of_birth TIMESTAMP
);
```

## Data type

https://www.postgresql.org/docs/current/datatype.html

## To see all tables in the database

- \d
- see the detail = \d tablename (ex: \d person)

## To drop table

- DROP TABLE tablename;
- ex) DROP TABLE person;

## To insert data

```js
INSERT INTO person (
  first_name,
  last_name,
  gender,
  date_of_birth)
  VALUES ('Anne', 'Smith', 'FEMALE', DATE '1988-01-09');
```

## To see data in the table,

- SELECT \* FROM table_name;
- ex) SELECT \* FROM person;

## To execute a file

- Go to a folder sql is downloaded
- Type 'pwd' to know exact path
- \i PATH and sql file
- ex) \i /Users/jonghanpark/Desktop/PostgreSQL/data/person.sql

## To create a sequential ID

- id BIGSERIAL NOT NULL PRIMARY KEY,

## Expanded display on

- \x on
