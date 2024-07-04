---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, principle, code]
title: First principles
---
{% include JB/setup %}

“You have to go back to first principles” – you may have heard that from your leadership (TL or execs) and while it may sound like a buzzword, it is one of the most impactful behaviors (or the most?) you can have.

Going back to first principles means to settle down across your team/organization on what are the most important principles you want to follow. These can be for example

 - Every changes should be independently rolled out with its own flag
 - Releases should be frequent and automated (no manual intervention unless metrics are off)
 - Identity/security/privacy context should be consistent in the life of a page/session/request.
 - Etc.

Note that while these are principles, their priorities may change over time – e.g. it’s easy to say that releases should be automated, but in practice having such a system requires time/effort that may not be worth spending (e.g. if you work in a startup and aren’t sure that this service will exist in the next 2 months). To be blunt, some might be philosophical principles that your org cannot staff – so they are essentially not principles you are following. Note that principles can’t be too broad, otherwise they’ll conflict with each others (e.g. you can’t say you want to ship fast and have zero operational costs).

Once your engineering organization is aligned on them, you need significantly less discussions around both design and prioritization. Staffing of projects should be obvious – this means you can talk less and do more. This is where having solid principles brings tremendous value.

Aligning on principles is however not as easy as it sounds. For example one principle I care about

 - Having an infrastructure/platform used by the whole company
 - Having privacy/policy baked deep into the infrastructure

This results in a small team being able to roll out company-wide policies at once and in engineers not having to worry if they can log some data, if they need to encrypt it or if they need to file a legal request. I however regularly get requests to not use the existing framework – in most cases these requests come from people with different backgrounds who never had to operate in large engineering organizations with large systems (since in startup it’s fine to fork systems and patch every one of them considering that there are just a few).

What principles you should follow depends on your situation and will be the topic of another post but looking back at what worked in your company is the first step to figure out what these principles are.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-principle-core-activity-7209570706987065347-zCgb?utm_source=share&utm_medium=member_desktop)
