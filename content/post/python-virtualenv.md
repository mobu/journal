+++
title = "Python Virtualenv"
description = ""
author = ""
date = 2020-01-28T15:00:08-06:00
tags = []
draft = false
+++
## Python Virtual Environment
1. Creating a virtual environment in a new folder
	```
	python -m venv FolderName ⏎
	``` 
2. Creating virtual environment inside an existent folder. Navigate to the folder inside where you want to create the environment
	```
	python -m venv . ⏎
	``` 
	_Notice_ the **dot** at the end of the statement.
	
	> The -m stands for module-name. 
	
## Steps for cloning GitHub projects into Virtual Environments
1. Navigate to the folder where you want the project to exist (don't make a folder; git will make a folder for the project)
	```
	git clone https://github.com/s0md3v/XSStrike ⏎
	
	Cloning into 'XSStrike'...
	remote: Enumerating objects: 6, done.
	remote: Counting objects: 100% (6/6), done.
	remote: Compressing objects: 100% (6/6), done.
	remote: Total 1629 (delta 1), reused 1 (delta 0), pack-reused 1623R
	Receiving objects: 100% (1629/1629), 1.14 MiB | 4.46 MiB/s, done.
	Resolving deltas: 100% (953/953), done.
	``` 
2. Navigate to the folder that was just created.
	```
	cd XSStrike ⏎
	``` 
3. Create a virtual environment inside the folder by typing:
	```
	python -m venv . ⏎
	``` 
4. Activate the environment
	```
	cd Scripts ⏎
	
	activate ⏎
	``` 
5. If there is a requirements.txt file for installing libraries, type the following in the root of the project
	```
	(XSStrike) C:\Tools\XSStrike\Scripts>cd ../ ⏎
	pip install -r requirements.txt ⏎
	
	Collecting tld (from -r requirements.txt (line 1))...
	``` 
	
	