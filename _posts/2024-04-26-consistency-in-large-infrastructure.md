---
layout: post
category : Growing as an engineer
tags : [softwareengineering, infrastructure, consistency, stability, horizontal]
title: Consistency in large infrastructure
---
{% include JB/setup %}

This post isn’t about the consistency of your writes, but the overall consistency of your infrastructure – Do you have one RPC/logging/UI framework? Do you have one way to retrieve information <X>? Do you have a single release process?

The fastest way to ship something is often to build a one-off solution or wrap/proxy code – at the cost of having a fragmented infrastructure. This is usually a good practice for startups – one of the founding engineers at YouTube (I can’t remember their name) used to say “what can’t you solve with a proxy?” – e.g. if the service doesn’t do exactly what you want, you can wrap it behind a proxy and tweak the response.

Fragmentation in your infrastructure is tech debt – it is a trade off you can do but you will have to pay the cost moving forward. My experience is that fragmentation is never properly weighted:
- Fragmentation requires engineers to be aware of it – they have to know that to update <X>, not only they have to update the service responsible for <X> but also another ad-hoc service that implements <X> for a minor use case. In practice you incur a cognitive load that makes onboarding new engineers harder.
- Even if you try to share this tribal knowledge, in practice it’s likely that at some point something will break because only one code path wasn’t updated. These outages’ consequences come into two flavors:
 - Loss of revenue: this is something that I saw while working at YouTube Ads – we were missing $XXXM because of code paths not being properly updated
 - Loss of productivity: you have to rollback a service, commit a fix and release it again. In a small environment this is fine but in a large organization the release oncall wastes time and your feature is delayed by at least one push schedule.
- Your data is likely inconsistent – so some of your decision (based on data) are not accurate
- Practically speaking, they set horizontal teams for failures (e.g. privacy/security teams), since they have to chase hundreds of weird call sites to fix a single problem.

If you really want to accept fragmentation as a cost to move some part of your business faster (e.g. some YouTube verticals were built on different systems), you have to properly staff all your horizontal teams to support this ad-hoc infrastructure.

My experience though is that consistent infrastructure is strictly better in the mid/long term for every team but unless you have seen a well built/consistent infrastructure, it’s hard to understand how great these are (and that they are reasonably achievable).

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-infrastructure-consistency-activity-7189646928593264641-QeKb?utm_source=share&utm_medium=member_desktop)
