---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, communication, iorwe]
title: Monitoring small slices
---
{% include JB/setup %}

This post was prompted by Strava heatmaps being broken last night even though Strava's health status page was showing all green – it's hard to detect a minor/partial outage of your system.

For example one thing we struggled for some time in YouTube Ads was reliably being able to detect outages on the Kids apps. These apps generate so little traffic compared to the main apps that we had to create a slice dedicated to them (otherwise we could stop serving ads and it wouldn't be noticeable on the global graphs).

The problem with having alerts on the Kids app was that we had a very large variance of ads served – there were no auction ads there, and reservation campaigns start/end would create massive delivery change. So it was basically impossible to monitor any small drop of ads delivery.

In the end, our solution was two fold:

 - Make sure nothing drops to zero
 - Monitor ratio rather than events per seconds – the ratio ads shown/ads served is much more stable than the number of ads shown

As your product gains traction, scaling your system is challenging, but in regards to monitoring, the more traffic you have, the better.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_growing-as-an-engineer-monitoring-small-activity-7228777324429660161-Xt7g?utm_source=share&utm_medium=member_desktop)
