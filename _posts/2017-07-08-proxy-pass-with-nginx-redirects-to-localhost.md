---
layout: post
category : Tinkering
tags : [nginx, proxy, proxy_pass, redirect, localhost]
title: Proxy pass with nginx redirects to localhost
---
{% include JB/setup %}

I have multiple nginx instances running on the same server. The master instance 
redirects traffic according to the request while the slaves one serve
a specific website. The main reason for this weird architecture is that I'm
running multiple services each in their own docker instance, and that I want
to be able to update a specific service without disturbing others.

The master nginx configuration file was:

```
server {
  listen 80;
  listen [::]:80;
  server_name example.com *.example.com;
  location / {
    proxy_pass http://127.0.0.1:4001;
  }
}
```

While the slave's one was:

```
server {
  listen 80 default_server;
  listen [::]:80 default_server ipv6only=on;

  root /usr/share/nginx/example;
  index index.html index.htm;

  server_name servername;

  location / {
    try_files $uri $uri/ =404;
  }
}
```

One issue I had was that `https://example.com/foo` was redirecting to
`https://127.0.0.1/foo/` instead of `https://example.com/foo/`.

The solution is simply to pass the original `Host` header to the nginx slave
with `proxy_set_header` such that `$uri/` resolves to 
`https://example.com/foo/` instead of `https://127.0.0.1/foo/`.
So the proper master configuration is:

```bash
server {
  listen 80;
  listen [::]:80;
  server_name example.com *.example.com;
  location / {
    proxy_pass http://127.0.0.1:4001;
    proxy_set_header Host $server_name;
  }
}
```
