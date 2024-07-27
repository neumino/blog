---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, communication, absolute, relative, percentage]
title: Absolute and relative numbers
---
{% include JB/setup %}

In the continuation of my previous post about quantitative over qualitative, it’s also important to use the right numbers. In general, absolute numbers are better but it depends on what your goal is.

If you mention latency improvements you have done on your system, it's most accurate to say something along the lines of “median latency went from 50 ms to 40 ms and p90 went from 200 ms to 50 ms”. A few interesting notes about this form:

 - The numbers are absolute and people can derive reasonable assumptions from it.
 - The numbers come with reasonable context, in this case the percentiles are stated. You must clarify if you are talking about median, p90, or average numbers.
 - While the numbers are clear, you still may need to add additional context, e.g. if the bulk of the latency left is from a third party system, it means there’s no room for improvements unless the other party makes some efforts

Interestingly enough, while this is the most accurate way to describe the improvements, it may or may not be what you want to communicate, for example

 - It probably sounds more impactful to write that you helped your company make a hundred of million of dollars than saying you made a one percent improvement
 - Similarly, it’s better to say that you did a 20% revenue increase rather than a $10k revenue increase

Pick wisely your numbers based on what you want to achieve 😅

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-communication-absolute-activity-7219355227005595649-6DCY?utm_source=share&utm_medium=member_desktop)
