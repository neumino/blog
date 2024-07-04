---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, hero, ninja, infrastructure]
title: No hero policy
---
{% include JB/setup %}

Google had a no hero “policy” – well, it was more that there was a doc or slides somewhere saying that while it is amazing if you can save the day by working hard, doing some ninja changes in production or moving a mountain in record times, heroic behavior shouldn’t be the norm.

The main idea is that in an healthy company:

 - Technical infrastructure is well built – e.g. the system can recover by itself for some issues
 - Processes are mature – e.g. binary pushes and config changes are done during business hours
 - Teams are properly staffed – e.g. there is enough time to ramp up engineers and spread knowledge such that no one is a single point of failure

If I remember well, the document was going fairly far stating that if your load is too high, you should let the system fail. This is pretty bad advice in my opinion and very likely something you can consider only in large companies with a cash flow machine. You should complain about the situation and try to get it resolved rather than just throwing the towel – you should own the problem even if you aren't the one who will fix it.

With that being said, not every company has the luxury to be healthy like I described earlier – sometimes you have to trade off stability for new features. So yes sometimes leadership can explicitly decide to temporarily worsen the work life balance of their engineering org for some other benefit – and it's ok to perform heroic actions every now and then but this shouldn't be the norm. You have to find the right balance between celebrating and rewarding such behavior with appropriate actions such that this behavior isn't needed in the first place.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-hero-ninja-activity-7195799975362985985-6abw?utm_source=share&utm_medium=member_desktop)
