+++
title = "Nginx - HTTP Proxy Pass"
description = "How Proxy Pass Works"
author = "Mobu"
date = 2020-01-29T00:18:00-06:00
tags = []
draft = false
+++
### Basic HTTP Proxy Pass
The proxy_pass directive sets the address of the proxied server and the URI to which location will be mapped. 

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
  
### location without regular expression
1. If the proxy_pass directive is specified without a URI,
	```
	location /app/ {
    proxy_pass      http://192.168.154.102;
	}

	test.com/app/xxxxx =>  http://192.168.154.102/xxxxx
	``` 
2. If the proxy_pass directive is specified with a URI:
	```
	location /app/ {
    proxy_pass      http://192.168.154.102/maped_dir/;
	}

	test.com/app/xxxxx =>  http://192.168.154.102/maped_dir/xxxxx
	``` 

#### Upstream servers

"upstream" is called whatever is behind the nginx.