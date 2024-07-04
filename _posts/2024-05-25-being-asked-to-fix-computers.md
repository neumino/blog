---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, help, fix, itsupport, tshape]
title: Being asked to fix computers
---
{% include JB/setup %}

There are many holidays in May in the Netherlands and seeing how Memorial day is coming up in the US, I thought I would write a bit about all the jokes, memes, and complaints from software engineers being asked to fix computers/doing tech support when going home for the holidays.

While this may be annoying at times (especially when you visit a distant uncle), it is a stark reminder that the average person is not tech savvy. In practice, it means that when building products, you should understand your audiences and adapt your product to them – e.g. there's no value in surfacing an HTTP error code, or an internal JSON deserialization failure to your non tech end user.

When dealing with errors, you should track all the internal details you need for your own monitoring/debugging, but these should never be surfaced as is to the user (unless you are asking them to copy/paste something when filing a bug/report). You should have a translation layer that captures and translates every possible error before these make it to the users.

These requests to fix computers also serve as a reminder to stay humble at all times – we all have different knowledge. Someone not understanding the acronyms DNS/DOM/etc.  might be an amazing historian, an expert in fluid mechanics or a superb sales director. We all have T-shaped knowledge/skills with different depth in different domain – and helping others when we have the skills is how we form better teams and a better society.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineer-tshape-help-activity-7200148640156270592-maoA?utm_source=share&utm_medium=member_desktop)
