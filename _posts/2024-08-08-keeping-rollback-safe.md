---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, rollback, safe]
title: Keeping rollback safe
---
{% include JB/setup %}

During an outage, the default action in case you suspect a binary push to be the root cause is to rollback the binary. This is in general much safer and less risky than attempting a fix forward.

Following this playbook requires you to keep rollback safe – and yes, rollbacks aren’t always safe! In general rollback requires the behavior with other services (and dependencies in general) to be backward compatible. For example, if you rolled out a new API as part of your new binary, you have to make sure no other service is using it before rolling back.

There are different ways to achieve safe rollbacks, e.g. you can follow a rule of thumb that to start using a new API in a service, you need it to have been released twice (if that’s the case, you hopefully frequently release). With that being said, I think the right solution is to have no-op binary push: every behavioral change in your binary must be contained behind an experiment flag – this means that every push is a no-op and that a rollback is a no brainer (it would be like turning on/off flags, which are much cheaper to coordinate across services compared to rolling back multiple services)

There are other advantages of doing no-op binary push – e.g. you can have tighter verifications of your system (since nothing should change, none of your metrics should change).

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-rollback-safe-activity-7227338364314628100-dNbE?utm_source=share&utm_medium=member_desktop)
