+++
title = "PostgreSQL - Management"
description = ""
author = ""
date = 2020-01-24T21:24:09-06:00
tags = []
draft = false
+++
### Service management
```
sudo service postgresql stop
sudo service postgresql start
sudo service postgresql restart
```

### Enter the database you created
```
psql testdb
```
	
### Creating a table
```sql
CREATE TABLE [IF NOT EXISTS] table_name (
	column_name1 col_type (field_length) column_constraints,
	column_name2 col_type (field_length),
	column_name3 col_type (field_length)
);
``` 
### Listing information
>|Command|Action|
|--|--|
|\l|list all databases
|\dt|display all tables in current schema|
|\du|list all users|
|\d|list all the tables in the database|
|\d+ table_name|retrieve detailed information about a table

### Roles
>|Command|Action|
|--|--|
|\du _username_|list a username if present|
|create role _rolename_|create a role with an existing username|
|create role _rolename_ noinherit login password _passsword_;|Create a role with username and password|
|set role _test_;|change role for current session to _test_|
|grant _role2_ to _role1_;|Allow _test1_ to set its role as _role2_|