---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, rollback, outage]
title: Correlation is not causation
---
{% include JB/setup %}

Correlation is not causation but it’s enough to rollback. Every now and then, an incident happens and the author of a change that lines up with the beginning of the outage will argue that their change cannot be the root cause and that correlation is not causation – and push back against a rollback.

While I agree that correlation is not causation, large scale systems are so complex that your assumption/theory on why a change cannot be the root cause may be wrong – not because of some faulty logic from your side, but because of some faulty assumption about the system. For example, it’s fair to assume that every service uses the JVM <X> based on some config – but the catch is that you never know if an engineer decided to overwrite this somewhere else.

So the first thing to do if you find a reasonable culprit or a suspicious change during an incident, is to roll it back. If it doesn’t solve the problem, the change should be rolled forward quickly – e.g. if the review needed a lot of approvers, someone should use some “admin” power to approve it on behalf of others. It doesn’t cost much to rollback/rollforward.

There are different thoughts on the topic, but I personally think that doing fast mitigation (e.g. fast rollback) can be a valid path forward as opposed to relying on heavy/manual testing. What are your thoughts on this topic?

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-rollback-outage-activity-7230589221487480832-Q70h?utm_source=share&utm_medium=member_desktop)
