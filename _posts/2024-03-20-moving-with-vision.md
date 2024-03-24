---
layout: post
category : Growing as an engineer
tags : [softwareengineering, vision, leadership, data]
title: Moving with vision
---
{% include JB/setup %}

Today every company is an AI company – and before that they were all data companies. While you should make your decision based on data, the lack of data shouldn’t prevent you from moving forward as an engineer.

I have been working on infrastructure for most of my career (maybe sometimes disguised as privacy work). In many cases, it was hard to properly estimate the impact of my work ahead of time. For example one workstream I performed in the past (over a few years) was to centralize all logic around monetization into a single place. One way to think about this work was just refactoring, but the initial goals were to:

- Make it easier for engineers to work on the code base
- Make it faster to rollout changes – any code path miss would need to wait one more binary release
- Less duplicated code paths, more consistent code so less bugs

It was hard to fully understand the impact of this work when I started chipping at this mountain but over time:

- We learned that productivity significantly increased through many anecdotes from engineers. Some changes that used to take weeks, were now taking a single day.
- We saved XXXM USD by enabling monetization where it previously wasn’t by mistake and fixing random bugs.
- We had strong invariants and confidence in our code. One proof was how it took us 2 days to perform an external privacy audit – while it took months for some of our sister teams to do the same.

It basically worked out well.

If you don’t have data on your idea, you should:

- Try to gather data if possible – if you are missing logs/monitoring, just add it
- Gather anecdotes if you can’t get hard data
- Move forward if you believe your idea is good but communicate about risks, goals and how to re-evaluate the effort over time (e.g. as new data becomes available)

An analogy would be: If you are sure that you need fire trucks to extinguish fires in your hometown, it’s fair to first get one even if you don’t know exactly how many more you will need.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-vision-leadership-activity-7176246129657835520-JAkq/)
