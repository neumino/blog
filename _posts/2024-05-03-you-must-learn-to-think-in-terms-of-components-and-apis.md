---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, system, design, api, component]
title: You must learn to think in terms of components and APIs
---
{% include JB/setup %}

Growing-as-an-engineer: You must learn to think in terms of components and APIs

One difference between writing code at school and writing school in the industry is that as a software engineer, you simply cannot deeply understand every single part of the system you work on. The only way for you to be efficient is to be able to build a mental model of how your system works with high level components and their APIs.

From there you can work on a single component (or a few) as long as you understand how it interacts with other ones. This allows you to operate on a much smaller surface – and in this case you can go deep into technical and implementation details.

One corollary of the point above is that the system must be describe-able in terms of high level components and their APIs. If your system has no semantics and is very tangled, you can’t have a simple description of your infrastructure making it hard for people to:

- Ramp up on it as they have to deeply understand a large infrastructure before being able to update a small piece
- Update the system as every change is risky – you may miss a code path or an edge case for your change

As you get used to think in terms of high level components/APIs, it will also help you significantly grow to senior levels and above since:

- The simpler your components and better your APIs are, the bigger your system can be (the more complex, the more impactful etc.)
- You can explain your system in simple terms to your leadership and non technical people – this means you can bridge the gap between your engineering org and other cross functional orgs.

This is in my opinion one of the easy signals to get during design interviews that very few books/articles talk about (as they mostly focus on pure technical systems) – and it reflects well how senior candidates are.

Interesting fact is that we could describe all YouTube Ads infrastructure on a single non crowded slide.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineer-system-design-activity-7192176101257887744-1rQG?utm_source=share&utm_medium=member_desktop)
