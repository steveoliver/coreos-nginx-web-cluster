FROM ubuntu:14.04
MAINTAINER Steve Oliver <steve@circatree.com>

RUN apt-get update
RUN apt-get install -y nginx

RUN sed -i.bak 's|^pid \(.*\)$|&\ndaemon off;|g' /etc/nginx/nginx.conf

RUN echo "<h1>NGINX backend running from Docker</h1>" > /usr/share/nginx/html/index.html
