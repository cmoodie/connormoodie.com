# Web Servers
```query
children:.
```
---

The term "web server" has two meanings. One is the physical (or virtual) server than contains the website's files and such.

The other, and **the one this page is about**, is the service that accepts HTTP requests from a browser, and responds with the appropriate files such that the browser can display the webpage it requested.

There are two main web server services: [Nginx](https://nginx.org/en/) and [Apache HTTP Server](https://httpd.apache.org/).

Nginx is simpler to configure and is becoming the default choice, and is therefore the one I use. It can also be used as a reverse proxy to allow for one server to host multiple websites -- see [[proxies]]# for more.