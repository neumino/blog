---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, thread, starvation, cascading, failure]
title: Thread starvation and cascading failure
---
{% include JB/setup %}

Following up on the previous post on how a canary won’t always save you, this post is about thread starvation, or just another way to take down prod.

If you need threads (e.g. to perform CPU intensive tasks), you likely create a pool of threads and use them. What’s important here is that your number of threads is limited and that managing threads in general is tricky. For example if you introduce a bug where a thread isn’t properly released under some circumstances (e.g. in case of rare errors), your pool of available threads is eventually zero. A more subtle issue is if one of your dependencies become slower and your threads aren’t released fast enough. In these cases, your server cannot handle any incoming requests.

One of the issues with this situation is that your server didn’t crash, it’s just in a bad state. This means that it won’t restart by itself. You need a prober or some kind of monitoring system to decide that the task is unhealthy and restart it. During this time, if your load balancer is doing something smarter than round-robin, you may end up diverting traffic outside the bad task – increasing pressure on other tasks and maybe making the problem worst there. Eventually they also may run out of threads, and you guessed it, your whole fleet is stuck in a bad state without being able to process any requests.

That’s how YouTube Ads went down a few years ago – nobody noticed since no one misses ads when they don’t work but this was for me an interesting experience. Managing threads and properly sizing your pool is not as trivial as it seems – that’s also why if you can move away from threads, you may want to consider it.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-thread-starvation-activity-7225878173211594752-Oq93?utm_source=share&utm_medium=member_desktop)
