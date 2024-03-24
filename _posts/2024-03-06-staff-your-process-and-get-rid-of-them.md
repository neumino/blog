---
layout: post
category : Growing as an engineer
tags : [softwareengineering, process, operationalexcellence]
title: Staff your processes and get rid of them
---
{% include JB/setup %}

Manual processes for engineering often suck. They may be needed but you don’t have to live with mediocre ones.

Processes are solutions that exist mostly in large organizations. They are often needed because the product (e.g. privacy regulations, contractual agreements etc.) are too complex for everyone to be aware of all of them – e.g. this is how Google has a privacy review for every launch (also because the FTC forced them to 😅)

With that being said, processes are often a short term solution following an outage – e.g. following a privacy incident about <X>, one may decide that every launch should explicitly acknowledge whether <X> will be broken. They are fairly easy/low cost to set up and people usually ignore the maintenance/ongoing cost.

Two terrible situations often happen with processes:
- They are not staffed: For example if the process requires a group of people to approve a launch, you must be sure that these people will review it in a timely manner without the need of nagging. If the group needs 3 days to review your launch, it's one interrupt and 3 extra days needed to ship new software.
- Processes that can be removed/lightened but aren’t: It’s OK to create a process in the short term following an outage, but there must be an investment to get rid of them or make them a no-brainer for the majority of cases. E.g., if you want to make sure sensitive data isn’t logged:
 - You could build a logging framework, enforce that it’s the only way to log data and make sure that every data logged is properly annotated such that no sensitive data is logged (you can do additional verification with data lineage) – in which case you don’t need a manual review.
 - You can carve out as many trivial cases as possible such that a manual review is not needed in most cases (e.g. if data about a service uptime is logged, if a boolean is logged etc.) – in which case you need a manual review only in rare cases (e.g. when unconstrained strings are logged)

Being an engineer at heart, one of the most painful processes I encounter is when teams have to manually look at release metrics before rolling out. You don’t need to eyeball your metrics every day, just write a static check (and a way to override if needed).

TL;DR: Staff your process, don’t settle for mediocre processes and replace them with proper infrastructure.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-process-operationalexcellence-activity-7171172717008777216-l0s5?utm_source=share&utm_medium=member_desktop)
