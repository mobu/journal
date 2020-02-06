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
    The command ‘usermod‘ is used to modify or change any attributes of a already created user account via command line.
    > **_-a_** append the user to the supplemental GROUPS mentioned by the -G option without removing him/her from other groups
    >
    > **_-G_** new list of supplementary GROUPS
    >
    > // to change username, use the -l switch
    >
    > **_usermod -l_** [old username] [new username]
3. Enable UFW Firewall & open SSH port
    ```
    // allow port 22 for SSH
    sudo ufw allow 22

    // enable UFW firewall
    ufw enable
    ```
4. Login to new account using SSH
    ```
    rsync --archive --chown=mobu:mobu ~/.ssh /home/mobu
    ```
    > **_rsync_** copies the files, directory structure, and ownership from the .ssh folder of the root to /home/mobu

# Securing Ubuntu
1. Secure shared memory
    ```
    sudo nano /etc/fstab

    tmpfs     /run/shm     tmpfs     defaults,noexec,nosuid     0     0
    ```