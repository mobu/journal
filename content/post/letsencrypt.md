+++
title = "LetsEncrypt - guide"
description = "Setting up LetsEncrypt with Docker and Nginx"
author = "Mobu"
date = 2020-02-04T13:54:46-06:00
tags = ["docker","nginx","letsencrypt"]
draft = false
+++
### Basics of Let's Encrypt
1. open and automated certificate authority
2. Let's Ecnrypt issues free SSL/TLS certificates
3. Certbot - can automatically configure TLS/SSL on both Apache and Nginx web servers
> What is a Certificate Authority?
>
> Certificate authorities (CAs) are entities that cryptographically sign TLS/SSL certificates to vouch for their authenticity.
## 3-part process
1. Install Certbot on your server
2. Run Certbot with a command to **obtain** your SSL/TLS certificate and **save** it on your server.
3. Set up a cron job (scheduler) to run Certbot with a Certbot renew command on a weekly basis.

This certificate consists of a private key and a public key and both these keys are saved in a Let's Encrypt folder on your server.
```
Nginx loads both the private and public keys in order to configure SSL/TLS for your site.
```