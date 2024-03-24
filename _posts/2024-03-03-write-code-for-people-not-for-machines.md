---
layout: post
category : Growing as an engineer
tags : [softwareengineering, simpleisbetter, growthtips]
title: Write code for people, not for you, not for machines.
---
{% include JB/setup %}

You should write code that’s readable for others since code is written once but read multiple times. Forget all the rare, complex and exotic syntaxes that people wouldn’t get at once, write simple and dumb code as much as possible.

When I was a new grad, I wrongly assumed that I had to write code using all the capabilities of a given language – JavaScript in my case. The code I wrote was working well, but it wasn’t necessarily easy to read – especially if you didn’t know all the quirks of JavaScript (this was before ES6)

In my case, it probably was fine since I was the only engineer working on the frontend and the node.js libraries. This was however very different from when I was leading YouTube Ads serving infrastructure where we had

- A very complex business logic – e.g. if you want to know if you can monetize a page, you need to compute hundreds of decisions (from who owns the video, if you paid the tax in that given country, if the user is a kid etc.)
- A very large set of engineers/teams working on the stack at the same time

At this time, having simple code was extremely valuable:

- It’s much easier to review – and therefore safer since reviewers can focus on business logic and edge cases rather than exotic/questionable syntax.
- Code was consistent, so it was overall much easier to read, grep and sed. It’s a virtuous circle, people tend to stick to the existing style making the code base naturally simpler.

One interesting fact from my time at Google was how you can’t throw errors in C++ at Google (same pattern as in golang) – this was a conscious decision from Google to keep code simpler.

If you want proof of why writing readable code matters, you can probably look at the code you wrote while being a new grad (or while at school) and see how easy it is for you to understand and be able to update. Personally, my old code is terrible 😅

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-simpleisbetter-growthtips-activity-7169360748018614272-junJ?utm_source=share&utm_medium=member_desktop)
