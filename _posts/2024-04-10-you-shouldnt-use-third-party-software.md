---
layout: post
category : Growing as an engineer
tags : [softwareengineering, 3p, software, opensource, security]
title: You shouldn't use third party software
---
{% include JB/setup %}

When you use a third party library to save yourself a bit of time and ship a feature a bit faster, you very likely ignore the cost of using such a library.

Libraries can have security vulnerabilities (CVE, GHSA etc.) and at this time you have to update them either for security purposes (so you won’t get breached) or for compliance purposes (so you don’t lose your certification). In practice updating libraries only when they have security issues is a terrible choice – if you are 10 major versions from the earliest one that’s vulnerability free, you won’t be able to upgrade quickly. At the end of the day, you have to constantly keep your libraries up to date and this takes time (because not every update is backward compatible).

Third party libraries also come with all sorts of quality issues – even if they are backed by a company or open source foundations (like Apache). I’ve seen silly bugs (e.g. “null” return than “” for `getPath()` with the path is not set) and some more complex ones that happen only when you stress the library to its limits (e.g. when the max number of opened files is reached) – and the truth is very few of these libraries have been pushed to their limits.

A mental framework/questions that may help you decide if you should use third party libraries is along the lines:

- Do you have to? There are cases where you don’t have a choice (e.g. integrating with another company service)

Is the library backed by a company/open source organization? Is the library going to be maintained well for the foreseeable future?

- Does the library have bugs? Is the code of good quality? Would you hire the author to work in your company? Note that the issue might not necessarily be how good the author is but more how invested the author is in this library.
- Does the library support your use case/environment? E.g. is it known to support your QPS, your type of workloads etc.
- Do you need the whole library or just a subset? How much time would it be for you to implement the feature you need?
- Is the library well maintained and free of security issues? Are the upgrades backward compatible? How much time would it be for you to keep this library up to date? Compare this cost with the time to implement it yourself.

Using third party libraries in many cases is like doing business with a loan shark – you may have to, but the costs are higher in the long term. So if you can, don't use them.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_hot-take-you-shouldnt-use-third-party-libraries-activity-7183841177706582018-nRwP?utm_source=share&utm_medium=member_desktop)
