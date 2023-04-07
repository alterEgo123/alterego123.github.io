---
layout: post
title:  "Docker like a rockstar!"
date:   2023-03-08 10:58:00 +0100
categories: [containerization]
tags: [docker]
---
Keep in mind to...

_Start with_
- Separate concerns
- Dockerize everything
- Use small official verified images
- Add .dockerignore
- Use multi-stage builds
- Don't run processes as root (least preferred user)
- One process per container (Or multiple instances of same process; E.g celery)

_Try to_
- Add Seccomp profiles

_Try not to_
- Mount /var/run/docker.sock unless you have to

_Don't forget to_
- Make use of caching
- Minimize number of layers
- Scan your images for vulnerabilities
- Use meaningful tags
- Add expiration policy in docker registry
- Protect deployed images

_Actually useful plugins/tools_
- Docker buildx
- Dive
- Dockle

_Docker compose_
- Enables GitOps for Docker
- Should always be used with code
- Environment separation by using overrides
- Use .env to store sensitive vars
- You can avoid redeploying containers dependencies using --no-deps
