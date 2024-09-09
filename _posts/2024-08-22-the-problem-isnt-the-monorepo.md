---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, monorepo, microservice, spaghetti, api]
title: The problem isn't the monorepo
---
{% include JB/setup %}

The problem isn't the monorepo, it's the spaghetti code that's inside.

Using a monorepo is both a blessing and a curse. It’s a blessing because you can easily share/reuse code across the whole company. This makes creating choke points for enforcement significantly easier. But it’s also a curse, it’s very easy to end up with spaghetti code where internal APIs are unstable at best, non-existent at worst.

Working on privacy infrastructure (and infrastructure in general), monorepo is a significantly better solution in my opinion. You just have to build the discipline inside the engineering org to not abuse things:
 - Monorepo doesn’t mean monolith – you can have multiple services
 - Take advantage of the monorepo benefits, i.e. shared core infrastructure that’s top quality
 - Don’t abuse the system, i.e. create semantically meaningful APIs that are stable over time, and keep them that way – don’t wrap APIs because it’s convenient short term

You also don’t need to be Google size to be able to efficiently work on a monorepo. Google had its own problem not because of the monorepo but because of the sheer scale of its code base.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-monorepo-blessing-activity-7232401181954748416-Aa6H?utm_source=share&utm_medium=member_desktop)
