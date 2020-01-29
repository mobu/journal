+++
title = "Nginx - HTTP Proxy Pass"
description = "How Proxy Pass Works"
author = "Mobu"
date = 2020-01-29T00:18:00-06:00
tags = []
draft = false
+++
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