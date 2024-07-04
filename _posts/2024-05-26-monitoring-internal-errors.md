---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, error, monitoring, internal, invariant]
title: Monitoring internal errors 
---
{% include JB/setup %}

Way too often, I see services being only monitored at their end points – meaning that engineers track their service's final HTTP status and almost no internal errors. At best, the RPC framework (when it exists) reports the status of every RPCs being sent.

If they do track internal details, it also comes in the form of unstructured strings in the binary logs or in ad-hoc graphs – so nothing that scales well for a large system built by a large team. For example, when I see a “Should never happen” and ask around if this is actually true, I rarely get a confident “yes” because there is no monitoring/enforcement in place.

One way I tackled this issue in the past is by attaching a unique error enum to every error thrown/returned. You can make an util to attach these enums and export every error returned there.

The benefits of such setup are that:
 - You can better monitor errors in canary – binary logs are noisy, with a counter of your internal errors, you can easily detect a new one even if It rarely happens
 - You can enforce your invariants and make sure they are true at all time – e.g. you can make sure unreachable code is never reached or make sure policies are never breached (e.g. you never targeted a kid with ads)
 - You can safely log the enum since there are no privacy concerns while the error message might be (and in general it's hard to enforce no sensitive data in error messages)

This setup works if every error has such an enum, so you either need a strong code review discipline or have a CD/CI test to enforce every error has such an enum.

If you rolled out something similar in the past or something different, I would be curious to know what you did!

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-error-monitoring-activity-7200511017938731010-Sp-O?utm_source=share&utm_medium=member_desktop)
