---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, work, good, fast, evolution]
title: The untouchable code
---
{% include JB/setup %}

There is a saying in the software engineer world that goes “Is it broken? No, then don’t fuck with it”. The rationale being that if something is working, there’s no need to risk breaking it for no good reasons. WIth that being said, the saying tends to become “No one understands the code, so don’t touch it”.

This is where priorities shift as a company matures:

- In the early days, a startup is focusing on building a product that works and figuring out market fit. As long as a piece of the system is working, the priority is to iterate on the product rather than the system.
- As a company matures and needs to become more stable, a working system is not enough. You need a system that is also good, i.e. stable, fast and correct. This is the time where if there is a piece of code that nobody understands, you should rewrite it.

Rewriting an old piece of code isn’t for the sake of rewriting it, making it look nice or making it more modern. The goals are:

- Make sure the code is correct – code that haven’t been touched often didn’t evolve when they should, resulting in bugs
- Make sure the code is simpler – sometimes old pieces of code are incrementally updated and end up in spaghetti code with tons of if conditions, early returns and error thrown/caught around. This is a chance to rethink from the ground up how a system should be written given all the current product requirements
- Make sure the code is understood by a broader set of engineers – tribal knowledge can sometimes be lost on these old pieces of code. The more people understand the code, the more people are equipped to handle both outages and people being not available (either because they are on vacation or because they left the company)
- Make the code efficient – once you have reached a large scale enough, efficiency can result in significant machine cost saving. Similarly, as your product get stable, investment in latency are worth it as they will persist (you won’t rewrite your whole app every 6 months)

I personally prefer the saying that goes “first make it work, then make it good and finally make it fast” as it better reflects the evolving priorities of a project/company.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineer-work-good-activity-7215006555933470721-2t3Q?utm_source=share&utm_medium=member_desktop)
