Overview
========

This is a Nginx load balancer service that uses confd to dynamically
and automatically configure itself to serve traffic to a cluster of
backend nginx services.

Related Projects
================

- nginx_lb.service. see ../../static/nginx_lb.service

Resources
=========

- docker pull steveoliver/nginx-lb:ubuntu-14.04
- [How to Use Confd and Etcd to Dynamically Reconfigure Services in CoreOS|https://www.digitalocean.com/community/tutorials/how-to-use-confd-and-etcd-to-dynamically-reconfigure-services-in-coreos]
