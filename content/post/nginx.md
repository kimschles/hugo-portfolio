---
title: "nginx for Scaredy Cats"
description: "nginx as a Reverse Proxy, Content Cache and Load Balancer"
date: 2020-12-01T20:54:40-07:00
draft: true
author: Kim Schlesinger
---

![](https://images.unsplash.com/photo-1548247416-ec66f4900b2e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=300&q=80)

Although I've been an ops engineer for a couple of years, I've felt intimidated by nginx and 





## About nginx 
nginx, pronounced "engine-x," is a project that can configured as a web server, reverse proxy and/or load balancer. The project was first developed in 2004 by Igor Sysoev, and its original purpose was to solve the [C10K Problem](https://en.wikipedia.org/wiki/C10k_problem).  which is a web server that can concurrently handling ten thousand connections. Although that was an issue in the early 2000s, now nginx can handle ### requests at once. 

There are two versions of nginx, open source nginx and nginx Plus. The open source version is free, while nginx plus is something you have to pay for, but it has more features. 

nginx is a popular server. According to the [Netcraft April 2020 Web Server Survey](https://news.netcraft.com/archives/category/web-server-survey/), nginx serves 28.5% active sites on the web, while Apache is second with 27.8%. 

## Server Response Header 
Here's one way to see which server has sent a file to your web browser: 

**Look at the http response headers using your browser's dev tools** 
* Open dev tools
* Go to the network tab
* Refresh the page and pick one file to look at 
* Look at response headers 

![]()


Not all responses have the `server` header. If you decide to add that information, you don't want to put too much information or else attackers could exploit known vulnerabilties of that particular software. 

## Prerequities 


## Reverse Proxy 

The simplest nginx configuration possible: 

```C
server {
    location / {
        proxy_pass http://<IP_ADDRESS_OF_YOUR_SERVER>:8080/;
    }
}
```


A few more directives: 

```C
server {
    location / {
        proxy_pass http://<IP_ADDRESS_OF_YOUR_SERVER>:8080/;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
```

## Content Cache 

## Load Balancer 

## Resources 
