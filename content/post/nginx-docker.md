+++
title = "Nginx - notes"
description = "notes about nginx"
author = "Mobu"
date = 2020-01-28T01:09:50-06:00
tags = []
draft = false

+++
### Main commands
```[sudo] nginx -s signal``` (while an nginx instance is running)

|Signal|Action|
|----|----|
|stop|fast shutdown|
|quit|graceful shutdown (waits for workers)|
|reload|reload the configuration file|
|reopen|reopen the log files|
---
### Configuration file
By default, the nginx configuration file can be found in either:
```
/etc/nginx/nginx.conf,
/usr/local/etc/nginx/nginx.conf, or
/usr/local/nginx/conf/nginx.conf
```
---
# Directives
They consist of name and parameters; it should end with a semicolon
### server_name
* accepts multiple values
* handles wildcard matching and regular expressions.
```
server_name netguru.co www.netguru.co; # exact match
server_name *.netguru.co;              # wildcard matching
server_name netguru.*;                 # wildcard matching
server_name  ~^[0-9]*\.netguru\.co$;   # regexp matching
```
### listen
listen directive accepts IP:port values
```
listen 127.0.0.1:80;
listen 127.0.0.1;    # by default port :80 is used

listen *:81;
listen 81;           # by default all ips are used

listen [::]:80;      # IPv6 addresses
listen [::1];        # IPv6 addresses

listen localhost:80; # you can even use hostnames:
listen netguru.co:80;
```
### Multiple virtual servers
Inside nginx, you can specify multiple virtual servers, each described by a ```server { }``` context.
```
server {
  listen      *:80 default_server;
  server_name netguru.co;

  return 200 "Hello from netguru.co";
}

server {
  listen      *:80;
  server_name foo.co;

  return 200 "Hello from foo.co";
}

server {
  listen      *:81;
  server_name bar.co;

  return 200 "Hello from bar.co";
}
```
### Basic HTTP Proxy Pass

The **proxy_pass** directive is mainly found in *location* contexts.

- When a request matches a location with a `proxy_pass` directive inside, the request is forwarded to the URL given by the directive.

  ```nginx
  # server context
  
  location /match/here {
      proxy_pass http://example.com;
  }
  
  . . .
  ```

- By default proxy_pass does not *verify* the certificate of the endpoint if it is https.

  > make sure to set `proxy_ssl_verify` to `on`

#### Upstream servers

"upstream" is called whatever is behind the nginx.