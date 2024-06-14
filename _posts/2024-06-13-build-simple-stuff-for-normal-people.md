---
layout: post
category : Growing as an engineer
tags : [softwareengineering, simple, userjourney, noknobs]
title: Build simple stuff for normal people
---
{% include JB/setup %}

The catch phrase above tries to convey two goals:

 - You should build simple systems – simple systems are easier to maintain, explain and verify.
 - You should build products for a normal (non expert) audience – they are easier to learn/use (so you have less support to perform) and you can reach a larger audience (so your impact is larger)

The first point is something that is regularly mentioned in the literature (or in social networks) – so I won’t write much about it but basically it’s expected that senior engineers will try to build a simple solution to a complex problem rather than a complex solution to a complex problem.

The second point is more interesting though as it also applies to disciplines beside software engineering (e.g. for product). You should assume your target audience (either your company customers if you’re building products or engineers if you’re building infrastructure) are not experts in your domain. For example if you are building a piece of infrastructure, refrain from providing tons of knobs/settings that most people won’t be able to use or worse, may end up misusing.

If you really need these complicated features/settings, you should hide them by default – you should try to keep the common user journey simple. If you can do so, you will likely end up with a simpler solution and be able to reach a broader audience – so it’s win-win. It’s however not always trivial to refrain from building these controls since:

 - Sometimes your largest customer will be willing to pay a lot for this extra complexity – but at least try to not expose this complexity to other customers
 - Adding a new control is often the easiest incremental solution (compared to redesigning the whole product/user journey)

You have to try to find the right balance, but in general the more senior you are, the more you should push back against incremental feature requests that make the common user journey more complex for no good reasons.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-growing-coding-activity-7205946852330881024-Ywl4?utm_source=share&utm_medium=member_desktop)
