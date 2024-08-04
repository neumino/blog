---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, canary, testinginprod, cascadingfailure]
title: Your canary won’t always save you
---
{% include JB/setup %}

There is a school of thought among software engineers that insist that you can test in prod – you just need a server where you can canary/test your changes before rolling them out. I’m not here to call these folks names since I did test changes in production before (who hasn’t?) but to talk about some of my previous experiences – and how you can take down prod 😅

If you work on a distributed system, it’s likely that you have some stateless backend servers that talk to a database. In most canary setup (and that’s probably like 99%+ of them), you just pick one of your backend servers to release a new binary/config and you monitor this server (for crash, for latency and for business metrics). If your new binary sends queries of death to the database (even at a very low QPS), the following can happen:
- Your canary is roughly healthy, some requests fail (the ones that crash the database) but this might not be noticeable (e.g. if you have one every minute)
- Your database replicas go down one by one and can’t come back fast enough compared to the query of death throughput
- At this point you may detect the outage but it’s not obvious that this is related to your canary
- Your database replicas are eventually all down
- Your canary is unhealthy but so are all your servers – you essentially took down prod

This is where testing on canary doesn’t guarantee that only your canary will break and that you can easily rollback.

You could build a canary system that avoids this kind of cascading failures by building vertical silos (i.e. where you duplicate your whole stack into a canary stack and make sure your canary stack/prod stack cannot talk to each other). This is however a non trivial amount of work to get right (e.g. you have to deal with user diverted experiment, you need to properly route requests etc.).

There are other ways to take down prod (that I may write about later), but the one I wrote about is one reason YouTube went fully down a few years ago. Software is hard, but software on distributed systems is harder 😀

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineer-canary-testinginprod-activity-7225515802974691328-dIQE?utm_source=share&utm_medium=member_desktop)
