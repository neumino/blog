---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, rollout, strategy, slo]
title: Slow rollouts don’t add benefits
---
{% include JB/setup %}

There is a school of thoughts in our industry where you should roll out slowly – as over multiple days. This isn’t about whether you should skip having a canary, but how fast you should push your change once your verification is done. Sometimes it’s worse, you need some <insert level> engineer to keep an eye on graphs during the rollout.

My experience has been that slow rollout doesn’t help a lot in regards to your SLO. If there is a small bug that you won’t detect in your single task canary and your region canary, you likely won’t detect it until the full rollout is done – and practically speaking later. Since what matters for your SLO is the area under your error rate curve, a slow rollout doesn’t help much (area under a slow increase + long duration can be bigger than a fast increase + short duration, see illustration).

I would actually argue that slow rollouts are worse because:

 - Attributing a bug to a release is harder as the error rate increase is much slower (and often noisy in the first place). The fact that multiple releases may have started since makes debugging harder.
 - The issue might be detected outside business hours since your release is usually happening over multiple days – i.e. also outside business hours. This means that at the time of the detection, you may not have the right people around to help

My recommendation in general is to have a solid single task canary, a solid large scale canary (e.g. half a region) and then release relatively fast. If your traffic has fundamental differences across regions (e.g. in B2B companies, you may have issues that may arise only in one single region), you should make sure your large scale canary covers regions with different characteristics.

Thoughts? What side are you on? Robust testing + fast release or slow release regardless?

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-rollout-strategy-activity-7226240609882120192-ACX6?utm_source=share&utm_medium=member_desktop)
