---
layout: post
category : Growing as an engineer
tags : [softwareengineering, oncall, quiet, sleep, worklifebalance] 
title: Oncall rotations should be quiet
---
{% include JB/setup %}

I’m astonished to hear that in some companies/teams, engineers that are oncall:

- Get regularly woken up during the night
- Can’t do regular work during the week because of all the interruptions
- Don’t go out for activities (e.g. running) because they may get paged

Here’s my take on oncall rotations and how we (with other leads) shaped our rotation in YouTube Ads at Google:

- The primary oncall is responsible for triaging pages but is *not* necessarily responsible for fixing everything themselves (other oncalls should be looped in as needed)
- Every page should have a clear handbook with practical and mechanical steps (checking a specific graph, rolling back, escalating to another oncall etc.)
- Over-escalating (to your leads or other teams) is better than under-escalating (and having a prolonged outage).
- While the oncall should try to be available (e.g. don’t go hiking where there’s no service), there will be times the primary oncall cannot handle the page. In this case, just NACK and let the secondary oncall ACK. For example, if you’re driving on the highway, don’t ever stop in the emergency lane for a page.
- The people oncall are usually the owner of the service being supported, as such they are responsible and should be given leverage to keep the rotation quiet. This means among other things:

    -  Making sure there are enough tests coverage to prevent incidents (and/or push teams to add the missing tests)
    - Making sure there is enough monitoring in staging/canary/prod (and/or push the relevant teams to add the missing alerts)
    - Making sure changes happen during business hours (unless explicitly approved by the oncall)
    - Making sure there’s enough capacity for redundancy
    - Etc.

There will be times when you get paged at night (e.g. because of unforeseeable events, e.g. a shark chomped on a network fiber) but these should be minimized. I very rarely got paged during the night during my shifts at Google for Youtube Ads because we had a strong discipline and maintained a high bar for our service.

The TL;DR is that good engineering should result in quiet rotations.

Thoughts? What are your experiences?

[LinkedIn post](https://www.linkedin.com/posts/tumichel_growing-as-an-engineer-dont-miss-on-your-activity-7161025825595654144-O2BR?utm_source=share&utm_medium=member_desktop)
