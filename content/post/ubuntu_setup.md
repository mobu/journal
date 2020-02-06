+++
title = "Ubuntu Setup"
description = ""
author = ""
date = 2020-02-05T16:35:04-06:00
tags = []
draft = false
+++
# Setting up Ubuntu
1. Creating a New User
    ```
    adduser mobu
    ```
2. Set up root privileges (_sudo_) for our normal account
    ```
    usermod -aG sudo mobu
    ```
    > **_-a_** append the user to the supplemental GROUPS mentioned by the -G option without removing him/her from other groups
    >
    > **_-G_** new list of supplementary GROUPS