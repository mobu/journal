+++
title = "PostGIS - Installation"
description = "setting up PostGIS in Linux/Ubuntu"
author = "Mobu"
date = 2020-01-24T22:20:35-06:00
tags = ["postgres","postgresql","install postgres","database","postgis"]
category= ["PostGIS"]
draft = false
+++
# Installation
1. #### Update APT package list and upgrade system

	*_Prerequisite_*: PostgreSQL will need to be installed and configured beforehand.
	```
	sudo apt update
	sudo apt -y upgrade
	```  
	> _-y_ switch basically means automatic yes to prompts; assume "yes" as answer to all prompts and run non-interactively

2. #### Add UbuntuGIS-unstable repository & update
	```
	sudo add-apt-repository ppa:ubuntugis/ppa
	sudo apt-get update
	```  
3. #### Install PostGIS
	```bash
	sudo apt install postgis postgresql-12.1-postgis-3.0.0
	```  
	> replace the postgresql version with your own
	
If everything goes alright, PostGIS will be installed on your system. However, you do need to activate PostGIS features on a database
before you can store spatial data.

# Enabling PostGIS
1. Switch to Postgres user
	```
	sudo -i -u postgres
	```  
2. Create test user and database
	```
	createuser postgis_test
	createdb postgis_db -O postgis_test
	```  
3. Connect to the test database
	```
	psql -d postgis_db
	```  
4. Verify PostGIS is working
	```
	SELECT PostGIS_version();
	```  
