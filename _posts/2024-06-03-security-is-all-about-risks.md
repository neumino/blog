---
layout: post
category : Growing as an engineer
tags : [softwareengineering, security, risk, balance, infrastructure]
title: Security is all about risk
---
{% include JB/setup %}

If you ask a company what their stance on security is, they will always tell you security is their utmost priority, but the truth is that security like everything else (e.g. privacy, legal etc.) is about risk – practically speaking that’s why the CEO runs the company, not the CSO.

From an engineering perspective, if you care about security, you can do three things:

1. Convince leadership that security is important – and receive more headcounts, get your security work better prioritized by other teams, make sure launches meet a high security bar before launch etc.
2. Chase every new launch with the best of your abilities to make sure they are not launching anything with security gaps. This means reviewing many launches from a security angle and fixing whatever issues you find.
3. Make security a fundamental part of your infrastructure – rather than doing reactive work (fixing security incidents) or just in time change (chasing launch), this is preventive work. E.g. if you make sure your framework prevents a specific attack (e.g. SQL injections), then you don’t need to worry about these moving forward.

You should spend time making sure leadership understands 1/ – this is especially easier if a better security posture increases revenue (e.g. in B2B companies where customers provide sensitive data). If your leadership understand well security risks and the cost of taking shortcuts (not only in term of incidents but also in terms of one-off throw away work), you will likely be able to focus on 3/ – you will still have to do a bit of chasing people/launches (because your leadership will balance security with revenue, growth, and other risks), but this should hopefully not be too time consuming.

As you chase new launches, you should try to take a step back and understand what fundamental piece of infrastructure/process was missing and address the gap not just for this one-off but also for future launches – basically transform fixes for 2/ as long term workstreams for 3/.

To close this post on a fun note, did you know that a few companies don’t require your password to perfectly match to log in? They’ll allow some mistakes (e.g. wrong capitalization of some characters) to make the user experience better (and increase revenue).

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineer-security-risk-activity-7203047719735570432-Zauq?utm_source=share&utm_medium=member_desktop)
