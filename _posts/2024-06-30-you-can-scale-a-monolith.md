---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, monolith, scale]
title: You can scale a monolith
---
{% include JB/setup %}

There is so much content on the internet claiming that monoliths are not scalable. These authors likely never had an opportunity to actually lead a monolith server in a large scale environment and are just repeating inaccurate thoughts on the topic. Let me get this straight, you can scale a monolith way beyond what you will need.

To give you more colors, YouTube used to be a monolith – and at that time it was likely handling more traffic that your service will ever need.

It would take too long to refute every claims against monolith but I thought I would pick and address a few:

 - Monoliths are slower because they lack parallelization – this is not accurate simply because you can use multiple threads. Interestingly enough, if you don't want to deal with threads, you can just send yourself a RPC (and do basic async IO).
 - Monoliths are wasting more resources than micro services because you have less granular control of your fleet resources. If your monolith has different resource needs, you can just create different pools of servers – e.g. while you have a single binary, you can have a pool taking all RPCs that require a lot of memory and another pool for low memory RPCs. Breaking your monolith into pools present new challenges but these are already present with micro services
 - Monoliths have bad failure isolation. I think this is partially true but only for some class of issues like machine wide issues (e..g bad VM, OOM etc.). For business logic errors (by far the most common ones), if your function fails, it doesn't matter if it fails in a RPC or in an inline call, you still have to handle the error

I've barely scratched the surface here, but scaling a system, whether it's a monolith or microservices takes skills, thoughts and trade offs – thinking that scaling a system is a well defined set of questions with clear-cut answers is the most obvious mistakes you can make.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-monolith-scale-activity-7213556974288863233-y-y4?utm_source=share&utm_medium=member_desktop)
