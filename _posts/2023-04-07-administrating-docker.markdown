---
layout: post
title:  "Administrating Docker"
date:   2023-03-09 09:12:00 +0100
categories: [engineering]
tags: [cloud]
---

- Networking
  - None: Fully isolated network and containers can't talk to outside world
  - Bridge: default network type in most container runtimes; provides NAT between container and host; doesn't result in port conflict
  - Host: Similar to running multiple apps in your host
  - Underlay: Exposes host network interfaces to containers
  - Overlay: Allows connectivity between containers running in different hosts (useful for k8s for e.g); Flannel and calico are overlay technology examples

- Docker storage options
  - Volumes: Store data directly in the host's filesystem (/var/lib/docker/volumes) without using storage driver layer
  - Bind mounts: Mount host dir as filesystem into the container
  - tmpfs: Store data in memory

- Docker storage drivers:
  - Types
    - overlay2: Production ready; doesn't work under CentOS / RHEL7
    - aufs: Overtaken by overlay2; Works best for ubuntu 18.04 and under
    - devicemapper: Preferred for CentOS / RHEL7 ; better than overlay2 for write-intensive containers
    - btrfs/zfs: Can only be used if you use btrfs/zfs filesystems in your host
    - vfs: not production ready
  - How to configure:
    - Under /etc/docker/deamon.json

- Docker logging drivers:
  - Types
    - none: no logs in the container
    - local: logs stored locally
    - json-file: default one used by docker
    - syslog: Use syslog for storing docker logs
    - journald: Use journald for storing docker logs
    - fluentd, splunk, etc.
  - How to configure:
    - Under /etc/docker/deamon.json



