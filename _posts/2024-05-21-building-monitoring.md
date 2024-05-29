---
layout: post
category : Growing as an engineer
tags : [softwareengineering, monitoring, logging, metric, alert]
title: Building monitoring
---
{% include JB/setup %}

Every now and then, my leadership asks me to look at a broad problem. The first thing I do is try to build an understanding of the issue and this consists of:

- Looking at metrics, graphs and dashboard to get a sense of quantifiable signals
- Talking to people to understand the gaps in the metrics and get qualitative anecdotes about the problem

For almost every problem, metrics are missing in varying degrees but usually with significant gaps. The main reason is that people consider adding monitoring as a required but meaningless task to launch – this results in some metrics being added but:

- They are very basic metrics – e.g. server error rate without a break down of internal errors vs user errors
- They have gaps – many questions can’t be answered. Most of the time the most basic non technical question cannot be answered, e.g. how many users are doing <X> per day
- They are brittle – they often monitor low level technical details and will break in one of the upcoming changes

Building monitoring for your product is similar to building the APIs of your system – you need the right mindset. It cannot be an afterthought, you have to carefully design your real time metrics and your logs:

- You should have one end to end/top-level metric (or a few) that captures everything. There shouldn’t be an outage/bug that would not be captured by this metric – the bug may not move the metric, but it should be able to shift that metric with the right slice
- You should have all the relevant monitoring to debug your issues. These metrics are mostly technical/internal ones – e.g. your server error rate, internal errors, latency of incoming/outgoing requests etc. Your oncall should have all the metrics the need for their shift
- You should build the metrics and slices that are important for your product – e.g. if a slice of traffic is a critical investment for your company, you should monitor it no matter how small it is
- As you add/change your system, you should keep monitoring in mind and perform the appropriate change – don’t wait for an outage you cannot debug to add the monitoring from your change.

Last but not least, if a customer (it may be another engineering team) mentions an issue that’s not captured by your top level metric, don’t just add a metric and move on – take this opportunity to figure out what the issue in your top level metric and if it should be changed/adapted

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineer-monitoring-logging-activity-7198699099355836422-hbQe?utm_source=share&utm_medium=member_desktop)
