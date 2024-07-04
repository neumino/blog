---
layout: post
category : Growing as an engineer
tags : [softwareengineering, process, slow, debt]
title: Good processes are light
---
{% include JB/setup %}

Or another way to say it: heavy processes are bad, they don't even work.

It’s very easy to use processes to solve a problem – e.g. if you want your product to be compliant with X, you can just ask every person that launches something to confirm that their change is compliant with X. Adding such a process is very similar to doing an incremental update to a system by minimizing the amount of work needed to launch – with little to no consideration for the maintenance cost.

Beyond the ongoing people cost (everybody having to fill a form for every launch), this type of process doesn’t even work. Yes you may be able to convince a regulator/auditor that you have implemented a solution but the truth is that it likely won’t work over time. People will just answer what they need to be able to launch, essentially making your process useless.

My experience running privacy reviews/processes is that people will find the shortest path to launch – for many, this is their mission/charter. To be blunt, they’ll answer whatever they need to avoid a deeper review. If you want such a process to be successful, you need a few things to happen:

 - You need the process to be light. You can ask a small number of questions that the responder must be able to easily answer. For example you can ask them if there are children less than 13 years old accessing their website, but you can't ask them if their launch is compliant with GDPR in regards to children and providing them only with a link to the raw GDPR to figure out the answer
 - You need people to understand why the process matters and why there are no other solutions. This also means that you have to build the infra to reduce the work needed to go through the process. Ask questions about a policy only if a framework cannot enforce this policy

The only thing worse than a manual process is a manual process that you can automate and that doesn't work.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-process-slow-activity-7212469853419401217-L3n3?utm_source=share&utm_medium=member_desktop)
