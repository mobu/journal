+++
title = "Wireguard - Setup"
description = "Setting up Wireguard"
author = "Mobu"
date = 2020-01-30T12:00:24-06:00
tags = ["wireguard","vpn"]
category = ["security"]
draft = false
+++
Link: https://www.ckn.io/blog/2017/11/14/wireguard-vpn-typical-setup/

### Steps
1. Install WireGuard on the VPN server.
2. Generate server and client keys.
3. Generate server and client configs.
4. Enable WireGuard interface on the server.
5. Enable IP forwarding on the server.
6. Configure firewall rules on the server.
7. Configure DNS.
8. Set up Wireguard on clients.

### 1. Install WireGuard on the VPN server
```
add-apt-repository ppa:wireguard/wireguard
apt-get update
apt-get install wireguard-dkms wireguard-tools linux-headers-$(uname -r)
```
### 2. 