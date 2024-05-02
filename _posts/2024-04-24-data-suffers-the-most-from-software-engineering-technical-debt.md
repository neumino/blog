---
layout: post
category : Hot take
tags : [softwareengineering, data, semantics, baddata, techdebt]
title: Data suffers the most from software engineering technical debt
---
{% include JB/setup %}

When software engineers cut corners and create tech debt, the most prominent way this surface is through bad data. For example if you overwrite the field `user` denoting who’s sending the request with another user (e.g. the manager of this account) to bypass some access restrictions in your system, you end up with bad data in your logs. You broke the semantics of your logs.

Moving forward, anyone querying this data has to know about your hack and update their query to account for the bad data. In the worst case, they can’t even answer the questions they want because the data is lost.

Yes you can have bronze, silver and golden datasets but the sad truth is that infra/product engineers don’t own these datasets and ETL pipelines – someone else has to maintain this data and has to somehow figure out that the semantics arbitrarily changed. In practice they don’t find them unless they are obvious, which eventually results in discrepancies/inaccuracies in the datasets.

It's easy at this point to think that these issues are fine since they are small enough to not be noticeable in the first place but this is where these issues can get worse over time (unless you add monitoring, but who does that when they don't even communicate these breaking changes?). We had a bug in YouTube Ads that was explicitly ignored because it was a one thousand dollars per month bug – over 6 years, it became a multi-million dollar one and it took years for this issue to be noticed.

What's the right thing to do? It's easy to say not cut corners, but in case you do, you should:

- Try to avoid silently breaking the semantics of your logs, break them in obvious ways – e.g. move the data to a new field. Keep your logs semantically meaningful if possible too.
- Communicate the breaking changes to whoever uses the data – over-communication is better than under-communicating.
- If you can, build views of the data with the correct semantics such that no one directly query the data that's hard to interpret
- Monitor the bug/gap such that if it gets worse, you will be automatically notified and can decide to revisit the problem

This is one of the reasons in my opinion why data engineers have such a hard and ungrateful job. As a software engineer, did you think about the semantics of your logs? As a data person, did you have to deal with such silent breakages?

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineer-data-semantics-activity-7188914667388313602-1Yxr?utm_source=share&utm_medium=member_desktop)
