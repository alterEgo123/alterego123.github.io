---
layout: post
title:  "Microservices? Really?"
date:   2023-03-10 14:58:00 +0100
categories: [engineering]
tags: [microservices]
---

So.. you decided to build your app as microservices?

Okay, don't forget to:

- Single-responsibility only!

- Keep them small, replaceable

- Shift-left, it'll save you time.

- Observability and distributed tracing, logging is not enough.

- Monitor infrastructure and services.

- Loose-coupling, otherwise you're doing it wrong.

- CI/CD, duh? But keep it D.R.Y

- One giant monorepo that you can easily navigate through, or separate ones.

- One DB per microservice

- Smart endpoints + dumb pipes

- CQRS

- Event sourcing? But don't jump straight to it. You probably don't need it

- Service discovery

- IaC

- Invest in a policy engine, standards will take you a long way
