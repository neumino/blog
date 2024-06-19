---
layout: post
category : Growing as an engineer
tags : [softwareengineering, refactoring, communication, evolve]
title: Refactorign code
---
{% include JB/setup %}

Engineers often want to refactor code, but managers, leadership and other cross functional orgs often frown upon such efforts. Part of this misalignment comes from past non-useful refactorings and miscommunication.

Some engineers like to refactor code only for aesthetic reasons – from a company perspective this is mostly a waste of time. I wrote mostly because the only valid reason to do such change is for consistency/automation – e.g. having a consistent code base means you more easily perform large scale changes. But in this case you should frame the work not as a refactoring but more as “unlocking fast company wide changes”.

Refactoring code in general is not considered useful because it is the wrong way to describe work as hinted above – refactoring code is a mean to an end. You are refactoring code to:

 - Lower OPEX and increase profit – by making your system more performant
 - Improve user experience – by making the user experience snappier by reducing latency or simply better by reducing error rates
 - Support upcoming features in the mid/long term – by making your platform more generic/flexible to support new products/features
 - Increase engineers productivity – by preventing engineers from spending too much time in operational work, from having to update thousands of call sites for minor changes or from constantly fire fighting outages
 - Enforce policies – by introducing choke points where you can enforce policies (e.g. privacy, legal etc.) on all your traffic

Designing a system is easy, evolving it is hard – and making a system evolves well requires you to rethink from the ground up how your system should work. Many engineers and teams fail to evolve their system because they don’t properly communicate about the importance of such work – and it’s only when things go terribly bad that they will do a full rewrite.

My experience is that performing little refactorings along the way is more efficient than delaying them until a full rewrite is needed. Even if the full rewrite has to happen (because the product drastically changed), the minor maintenance work will make such a large transformation much easier to execute.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-refactoring-communication-activity-7207758764601454592-DX1s?utm_source=share&utm_medium=member_desktop)
