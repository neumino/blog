---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, sla, slo, oncall]
title: Understanding SLO
---
{% include JB/setup %}

There is often a misconception that a 99.9% SLO means that your error rate must always be less than 0.1%. This isn't quite the case, SLO are measured over a longer period of time (e.g. 30 days), in the example above, you need to have less than 0.1% of error over this period.

This means that you can have a 10% error rate but only for a short period. Assuming you have 0% error rate the rest of the time and that your QPS is constant, here are some numbers to understand what a 99.9% SLO means for 30 days:

 - 0.1% error rate – for 30 days
 - 1% error rate – for 3 days
 - 10% error rate – for 7 hours and 12 mins
 - 50% error rate – for 1 hour and 26 min
 - 100% error rate – for 43 min

Assuming you have a constant 0.5% error rate, all these numbers are halved, so in case of a global outage, you have ~20 minutes to recover to meet your SLO. In case of a full crash, you need to account for the time to detect/page someone, for them to come online before they can even try to recover the system – this means that the oncall probably has more like 15 minutes to solve a global crash if you want to meet a 99.9% SLO.

SLO still comes with a lot of nuances, e.g.:

 - It matters how you measure your SLO. My personal opinion is that SLO should be measured from the client perspective. While it comes with some issues (e.g. your client could have network issues), it does capture error on your side (e.g. network errors, load balancer issues etc.) that should count toward your SLO. At least you should measure it from your load balancers and not your backend server
 - It matters how you define your error rate – e.g. if you are responsible for an ad server and return an OK status with no ads in case of errors, your error rate is technically 0% – but that’s not a fair measure of the health of your system

This also means that people claiming a ridiculous number of 9s in their SLO often have a lot of caveats in their definition.

If you sign up for a SLO, you should make sure your system health is under control and that you have the appropriate process – e.g. your policy for how fast the oncall should acknowledge a page matters and should be factored.
There is a school of thoughts in our industry where you should roll out slowly – as over multiple days. This isn’t about whether you should skip having a canary, but how fast you should push your change once your verification is done. Sometimes it’s worse, you need some <insert level> engineer to keep an eye on graphs during the rollout.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-slo-sla-activity-7226603097207283712-LBXN?utm_source=share&utm_medium=member_desktop)
