---
layout: post
category : Growing as an engineer
tags : [softwareengineering, test, code, quality]
title: Write tests
---
{% include JB/setup %}

In my first job, I didn’t write any tests for the whole product I built, a web-app to manage your database that had pretty complex logic:

- Sharding/replicating and tracking progress of such operations
- A data explorer with suggestions from incomplete queries

This was kind of OK because I was the only engineer working on it, but if the company had become successful and other engineers would have started working on it, we would have been in a difficult position.

What I didn’t understand back then is that you write tests for others, not for you.

The tests you add let others verify that their changes don’t disable the features you built, break the invariants you implemented and reintroduce bugs you fixed. It allows others to be confident in their change without wasting time doing manual testing, getting their change rolled back or having to talk to you.

Tests also help people understand what the code does and how it works – they can replace documentation if these are well thought/written. This means that they make reviewing your code easier and help others ramp up faster on code you have written. I personally often read code when jumping into a new codebase.

TL;DR is that you should write tests, not only because they help you verify that you didn’t make a mistake but also because they make your whole team more efficient.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-test-code-activity-7186021741909942272-SxDT?utm_source=share&utm_medium=member_desktop)
