+++
title = "Nginx - notes"
description = "notes about nginx"
author = "Mobu"
date = 2020-01-28T01:09:50-06:00
tags = []
draft = false

+++
### Main commands
```nginx -s signal``` (while an nginx instance is running)

|Signal|Action|
|----|----|
|stop|fast shutdown|
|quit|graceful shutdown|
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