---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, latency, cost, bigo, tail]
title: Joining promo sessions
---
{% include JB/setup %}

When we talk about latency, we often take goals like P90 under 300 ms or some other numbers. I however think that it’s more important to control the tail of your latency. Namely, I think the latency of a service should be constant or, if it depends on `n`, `n` should be capped at a reasonable threshold.

If you don’t, you can take a goal at P50, P90 but your tail is unbounded – and it usually gets exponentially worse (the latency for the last percentiles usually doesn’t linearly grow). In practice, you have some users for which the experience is not slow but terrible (it may not even work since your request may just time out)

Latency matters because users do leave your website/app if your system is too slow – there are tricks/tips here because what truly matters is the user perception rather than the exact latency. You can improve the experience without improving latency (e.g. by showing an empty layout of the page). In general (but not always), latency is also a reflection of the cost of a request. I have more fun stories to share about latency, but this is for another post.

Building a system with constant latency is not trivial for complex products and for large scale and to be honest it’s sometimes not possible – but the challenges are pretty interesting. For example you have to figure out how to make your database call in constant time – this means that you can “only” do point look up. Expensive joins and broad scans are not permitted.

Interestingly enough, this means you have to really pay attention to your code complexity – all the big O notations aren’t just for theoretical problems and interviews. They have genuine use cases in latency sensitive systems.

The simple yet efficient principle is to push as much computation as you can offline and serve data with point look up – but you have to deal with data correctness/freshness, so it’s not always an easy trade off.

Have fun stories about latency? Share them in the comments :)

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-latency-cost-activity-7234213124579495936-9x3E?utm_source=share&utm_medium=member_desktop)
