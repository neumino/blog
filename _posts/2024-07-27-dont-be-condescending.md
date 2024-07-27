---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, communication, nojerk, humble]
title: Don’t be condescending (Crowdstrike edition)
---
{% include JB/setup %}

While there’s an overall feeling in the software engineering industry that we shouldn’t hire/have jerks, I found quite a lot of people being pretty hasty at judging Crowdstrike for their outage. The overall feeling being that their engineering org was terrible for not doing enough sanity checks. Being condescending is pretty similar to being a jerk – it falls under the line of “you made a rookie mistake, what kind of software are you writing?”.

You shouldn’t be condescending because it’s a jerk behavior, but even if it wasn’t, you shouldn’t because you may be very much wrong in the first place. You can be right given a known context but wrong given the actual situation. To be clear, you would still be wrong, it’s just that people would be more forgiving – unless you made unwarranted comments.

In the case of comments made about Crowdstrike, here are some interesting things to consider

 - There are different types of releases/updates, some are meant to be fast because they are time sensitive. Soaking changes for weeks is not viable sometimes – from reading Crowstrike’s preliminary report, this was the case here. For what it’s worth weeks long soaking is a terrible process but that’s probably a topic for another post
 - Failing open is not always the right behavior even if you are taking the risk of causing a global outage – e.g. if you fail open, you may expose assets to additional breaches. My take is that failing close is the right behavior if you have adequate testing/release verifications
 - Testing is hard – having a canary is not enough to catch some of these issues. The most common issues that canaries miss are around non backward compatible changes being released in parallel across multiple services. Interestingly enough, Crowdstrike did canary the changes that caused the outage
 - Official comms about an ongoing outage are not meant for engineers who have no stake in the situation. Words are carefully picked because they carry precise meaning – e.g. the words “breach” or “incident” have very specific meaning in the legal world, and one shouldn’t throw them in a press release without carefully understanding the ramification

As someone who went very deep into many topics (e.g. privacy, music regulations etc.), I have witnessed so many times people judging others without having an ounce of awareness of their lack of knowledge. It’s fine as an external person to ask questions and point out issues about a system – but you should do it in a humble way.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-communication-nojerk-activity-7222979070005776384-a0_a?utm_source=share&utm_medium=member_desktop)
