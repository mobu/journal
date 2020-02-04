+++
title = "Let's Encrypt - guide"
description = "Setting up LetsEncrypt with Docker and Nginx"
author = "Mobu"
date = 2020-02-04T13:54:46-06:00
tags = ["docker","nginx","letsencrypt"]
draft = false
+++
# Basics of Let's Encrypt
1. open and automated certificate authority
2. Let's Ecnrypt issues free SSL/TLS certificates
3. Certbot - can automatically configure TLS/SSL on both Apache and Nginx web servers
> What is a Certificate Authority?
>
> Certificate authorities (CAs) are entities that cryptographically sign TLS/SSL certificates to vouch for their authenticity.
### 3-part process
1. Install Certbot on your server
2. Run Certbot with a command to **obtain** your SSL/TLS certificate and **save** it on your server.
3. Set up a cron job (scheduler) to run Certbot with a Certbot renew command on a weekly basis.

This certificate consists of a private key and a public key and both these keys are saved in a Let's Encrypt folder on your server.
> Nginx loads both the **private** and **public** keys in order to configure SSL/TLS for your site.
---
# Dockerizing Certbot
A very basic instance of Nginx needs to be running on a host with a domain name before Certbot can be used
In order for Let's Encrypt to issue you a certificate, an ACME Challenge Request is performed:
1. You issue a command to the Certbot agent
2. Certbot informs Let's Encrypt that you want an SSL/TLS certificate
3. Let's Encrypt sends the Certbot agent a unique token
4. The Certbot agent places the token at an endpoint on your domain that looks like http://ohhaithere.com/.well-known/acme-challenge/{token}
5. If the token at the endpoint matches the token that was sent to the Certbot agent from the Let's Encrypt CA, the challenge request was successful and Let's Encrypt knows that you are in control of the domain.
