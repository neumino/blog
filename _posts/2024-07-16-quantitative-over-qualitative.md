---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, communication, qualitative, quantitative]
title: Quantitative over Qualitative
---
{% include JB/setup %}

It’s very easy to write qualitative adjectives to describe something – a system is fast, a service is reliable or a library is good. But this kind of description brings no value.

One of the key factors of good communication is for people to clearly and confidently understand your points. Qualitative adjectives don't achieve this – two persons likely have a different concept of reliability (e.g. someone working on ads and someone working on aircraft likely have different bars for what’s reliable). The best way to communicate is by quantifying things as much as possible, e.g.:

 - The system has a 99.9% SLA – rather than the system is reliable
 - The median latency is 3ms and p90 is 10ms – rather than the server is fast
 - The library has no known CVE – rather than the library is safe

More interestingly, this is even more important when communicating about people for peer feedback – including yourself for your own self assessment. If you write that someone is amazing, as a promo committee member, I can’t take this into account to decide on the promo:

 - I may not have worked with you, or not close enough to have a good grasp of your bar for ”amazing”
 - Even if I knew your bar, it would be unfair to give more weight to your feedback because I know you – and discount other similar feedback for other candidates

Rather, it’s much better to write something along the lines of:

 - TC (the candidate) has executed X projects in short timelines, has X PRs written (Y% more than their team’s average)
 - TC is the point of contact for all questions related to <X>, see <artifacts>
 - TC is a fast reviewer, e.g. time to first review of PRs is <X>, amount of PR reviewed is <Y> etc.

I’m not saying that you should never use qualitative adjectives – but these have a different use case I think, e.g. they are much more useful when you want to congratulate your team about their work. It’s better to say that they did an amazing job than they maintain a 99.9% uptime. They are also more useful when you need to convince a lot of people (rather than wanting them to understand all the details of your proposal).

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-communication-qualitative-activity-7218992781845803008-N13U?utm_source=share&utm_medium=member_desktop)
