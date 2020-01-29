
+++
title = "PostgreSQL - Setup & Installation"
description = "Setting up PostgreSQL on Ubuntu"
author = ""
date = 2020-01-24T12:59:48-06:00
tags = ["postgres","postgresql","install postgres","database","postgis"]
category = ["PostgreSQL"]
draft = false
+++
# Installing PostgreSQL
**Prerequisite**: Make sure to have [Ubuntu](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-18-04) set up first.

1. Using apt package manager, install Postgres (it's in the default Ubuntu repo).

```bash
$ sudo apt update
$ sudo apt install postgresql postgresql-contrib
```
	
2. Postgres associates roles with a matching Unix/Linux system account. So let's Switch over to the **postgres** account on your server by typing:

```bash
$ sudo -i -u postgres
```
> **postgres**: this user is the superuser for the PostgreSQL instance
	
3. Now access a Postgres prompt immediately by typing:

```bash
$ psql
```

4. Verifying PostgreSQL installation by running a simple **SQL** statement:

```bash
postgres=# SELECT version();
```
	
6. Exit out of the PostgreSQL prompt by typing:

```bash
postgres=# \q
```
---
### Creating a New Role
A role can represent a database user or a group of database users.
1. Log in as the **postgres** account and create a new user by typing:
```bash 
postgres@server:~$ createuser --interactive
```
2. Fill out the list of information required for the roles.
```bash
Enter name of role to add: mobu
Shall the new role be a superuser? (y/n) y
```
### Creating database
1. If you are logged in as the **postgres** account, type:
```bash
postgres@server:~$ createdb testdb
```
2. To grant permissions to the **mobu** user on the database we created in the previous step, connect to the PostgreSQL shell:
```bash
$ sudo -u postgres psql
```
3. Type the following query:
```sql
grant all privileges on database testdb to mobu;
```