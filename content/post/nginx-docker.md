+++
title = "Nginx - notes"
description = "notes about nginx"
author = "Mubasser Kamal"
date = 2020-01-28T01:09:50-06:00
tags = []
draft = false

+++

## Basic HTTP Proxy Pass

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