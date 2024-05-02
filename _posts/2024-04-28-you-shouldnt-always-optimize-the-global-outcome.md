---
layout: post
category : Growing as an engineer
tags : [softwareengineering, edgecase, prioritization, worstcase, userjourney]
title: You shouldn’t always optimize for the global outcome
---
{% include JB/setup %}

Engineering organizations usually focus on global impact and in practice overall revenue since this is what companies care about. While we could argue whether this is ethically what companies should do, I’m more interested in talking from an engineering perspective.

I’ve seen companies with tons of metrics available for every launch (revenue, DAU, latency, all kinds of user interactions etc.) but massively broken user journeys would persist. For example (and to rant a bit), my main gmail account is still tied to the US because:

- I have a family link setup with my wife and kids accounts
- Kids account cannot change their countries until they turn 13
- I cannot change my account’s country with a family link setup with kids in a different country
- I cannot remove my kids from my family account without deleting their accounts

The answer from Google was to delete my kids accounts…

At the core, there are issues that are not captured by metrics because the impacted slice of traffic is too small (e.g. in the example above, only people with family link setup with young children moving across countries are impacted). As much as you could try to build a metric for these small slices, my experience is that these will be too noisy to use for automated monitoring – e.g. monitoring revenue on YouTube Kids app was especially challenging because of how little ads we were serving. My take is that the only way to keep things working well is to have a consistent infrastructure such that these small slices cannot be broken unless a bigger one is (which will trigger alerts).

One challenge around doing such work is to justify impact for prioritization. I have been successful in the past to schedule this work by arguing that:

- It’s fewer outages and as much as these are often small, they heavily impact people’s perception of the product – e.g. if your users think your app is slow, it will be extremely difficult for you to reverse this perception even if your app gets much faster.
- It’s less maintenance cost – every time a small slice break, you have to investigate the root cause and because you may not immediately detect it, some logs might be missing at that time, making investigation even more time consuming. It's also (see previous post on consistent infrastructure) less work for every horizontal effort to enforce company wide policies.
- Doing it as part of other efforts – e.g. if you have to launch a new product for slice <X> where having the slice of traffic on the standard infrastructure would reduce time to implement, I would package this infra and product work together.

Have you seen egregious broken user journeys? I’m fairly sure this is because these issues are not prioritized

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-edgecase-prioritization-activity-7190364145920221184-wKm4?utm_source=share&utm_medium=member_desktop)
