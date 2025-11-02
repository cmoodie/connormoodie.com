# Web Servers
```query
children:.
```
---

The term "web server" has two meanings. One is the physical (or virtual) server than contains the website's files and such.

The other, and **the one this page is about**, is the service that accepts HTTP requests from a browser, and responds with the appropriate files such that the browser can display the webpage it requested.

Historically, there have been two main web server services: [Nginx](https://nginx.org/en/) and [Apache HTTP Server](https://httpd.apache.org/). These are both still used today due to their high configurability and speed. Nginx can also be used as a reverse proxy to allow for one server to host multiple websites -- see [[proxies]]# for more.

I, however, use [Caddy](https://caddyserver.com/), an up and coming open source web server that can act as a reverse proxy *and* automatically provides you with certificates so you don't need to use certbot to do so.
