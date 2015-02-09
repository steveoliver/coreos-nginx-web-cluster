FROM ubuntu:14.04
MAINTAINER Steve Oliver <steve@circatree.com>

RUN apt-get update
RUN apt-get install -y nginx curl

RUN rm /etc/nginx/sites-enabled/default

RUN curl -L https://github.com/kelseyhightower/confd/releases/download/v0.7.1/confd-0.7.1-linux-amd64 -o /usr/local/bin/confd
RUN chmod +x /usr/local/bin/confd

COPY nginx.toml /etc/confd/conf.d/nginx.toml
COPY nginx.tmpl /etc/confd/templates/nginx.tmpl

RUN sed -i "s|^http {\$|http {\n        # Log format for reporting backends in the context of CoreOS.\n        log_format upstreamlog '[\$time_local] \$remote_addr passed to: \$upstream_addr: \$request Upstream response time: \$upstream_response_time Request time: \$request_time';|g" /etc/nginx/nginx.conf

COPY confd-watch /usr/local/bin/confd-watch
RUN chmod +x /usr/local/bin/confd-watch
