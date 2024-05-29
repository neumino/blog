---
layout: post
category : Growing as an engineer
tags : [softwareengineering, monitoring, logging, metric, alert]
title: The benefits of doing things well
---
{% include JB/setup %}

In many software projects, the 80-20 rule (aka Pareto principle) applies – you can get 80% of the impact with 20% of the work while the remaining 20% of the impact requires 80% of the work.

A common advice (senior) engineers give is to just get to 80% of the impact and then move one (or worse, hand off the rest to a junior engineer). While this guidance makes sense in some situations (e.g. in a startup environment when growth is required for the company to survive), it may be a premature decision.

One overlooked benefit of completing the work is that you can then move on to something else and won’t need to maintain the old system/code path/business logic. This has a few positives consequences:

- You can forget about the old system – it reduces your cognitive load but also makes it easier to onboard a new coworker on your system
- You move faster – you can implement new features just once rather than twice and more importantly you don’t have to implement it in the old system that’s probably brittle and poorly designed
- You will have less outages – it’s likely that someone will ship a new feature without updating the old code path or someone may just introduce a bug in the old code (because it’s poorly designed, lack tests or doesn’t have enough monitoring)

Properly wrapping up work takes a bit more time short term but is very beneficial long term. The reason I could grow my scope/responsibilities at Google and the reason why I keep doing the same at Databricks is because taking the time to wrap up my work means:

- People are happy with solutions I shipped – they are polished enough that they don’t create unnecessary friction for engineers.
- While I will jump to fix any issues on projects I worked on, I spend very little time maintaining/updating them in general – so I have time to fix other things

Similarly, if you reduce your error rate to 0 (or extremely close to with a clear slicing of remaining errors), any new errors can be immediately detected – it’s much easier to detect a 0.1% error rate increase if you had a 0.01% rate before. This means dev loop cycles are faster (you can catch errors earlier) and operational cost is lower (you don’t need to rollback binaries shipped to prod, you can just fix your canary).

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-techdebt-maintenance-activity-7199061447627223041-R48F?utm_source=share&utm_medium=member_desktop)
