---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, level, calibration]
title: ORMs aren’t just syntactic sugar
---
{% include JB/setup %}

ORMs (Object Relational Mapping) get either a lot of love or a lot of hate – people usually love them because it’s a higher level API than directly hitting the database – so they don’t need to know the exact names of the tables involved, which keys are used for joins etc. Others hate them because they potentially hide SQL issues (e.g. join operation done without index).

I personally think that ORM provides a useful and interesting layer of abstraction if used right. Beside hiding some complexity from engineers, I think ORMs create an interesting and useful layer of abstraction, and more importantly an important choke point – you can do company wide changes in your database without having to deal with thousands of call sites/SQL queries. You don’t necessarily need one straight away, but you may consider it (or a similar layer of abstraction) when your org reaches a certain size.

Having a higher level API means you can roll out a caching infrastructure without requiring every product/service team to know about the change – all the complexity of freshness/eviction can be hidden from engineers who focus on other engineering issues.

It’s however important that the ORMs are properly used – and that engineers don’t shoot themselves in the foot. For example, ORMs should also enforce that you can’t join two tables without using an index.

I personally think that it’s unreasonable for every engineer to be an expert in database – e.g. I don’t think it’s reasonable for every engineer to know about how MySQL cache operates. I think part of the push back against ORMs is also just misplaced pride – interestingly enough, I’ve never heard people complaining about privacy policies being hidden from engineers day to day work but hiding SQL complexity is a problem.

Thoughts? How do you feel about ORMs?

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-orm-database-activity-7236387397209378816-mRMs?utm_source=share&utm_medium=member_desktop)
