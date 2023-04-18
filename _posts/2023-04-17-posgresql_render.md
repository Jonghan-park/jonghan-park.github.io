---
title: "How to re-create postgresql database in render.com"
header:
  image: /assets/postgresql.png
categories:
  - Postgresql
tags:
  - Postgresql
  - render
---

Render provides free plan for PostgreSQL, but there is a time limit for free plan.
I can use it only for 3 month which means I need to recreate every 3 month if I want to use postgreSQL database again. Unfortunately, Back up function is unavailable for database on the free plan. All data will be gone after 3 month, so I don't recommend using the database for free with essential information. Just use it for portfolio.

## Update .env with new properties of connections

- I need to update **_ Hostname, username, password _** in my previous project.
  ![Image sql](/assets/renderConnections.png)
  Go to .env file in my local folder or web server.

## Make database in my new PostgreSQL database

- There is the address to connect to my new database
  ![Image sql](/assets/connectDB.png)
  Copy and paste the address into terminal.
