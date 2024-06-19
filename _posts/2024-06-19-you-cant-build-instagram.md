---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, growth, instagram, design]
title: You can't build instagram
---
{% include JB/setup %}

One of the common design interview questions is to design instagram/twitter/youtube/etc. While I think these are valid interview questions that can foster interesting discussions that allow the interviewer to gather interesting signals about the candidate, you shouldn’t assume that you can actually build such systems.

I see many training/courses/lessons claiming to teach you how to code and how to build these large websites – these are quite misleading. You will learn how to build a blog, a mini social network, but you won’t have to chance to grasp:

 - The technological challenges in scaling a large system
 - The product complexity of scaling your product

To give more colors on the technical challenges, the courses may mention scaling up sharding/replicating a database, but in general there are teams that support such operations because doing so without down-time is not as trivial as it may seem. This is especially true if you are migrating from one system to another. You also have other scalability issues that are often ignored – to give just a few simple examples:

 - Hot keys – e.g. you can have one key that’s heavily more used
 - Irregular traffic patterns – e.g. traffic is not uniform on a daily basis (e.g. different time zones have different amounts of traffic) but also not in general (e.g. if you run a social network, you likely get more traffic during the holidays than during regular week days). Just throwing more machine isn’t always a viable option as it may result in non trivial operational costs
 - Consistency – e.g. how do you handle inconsistent data. Many data stores provide some guarantees, but these sometimes do not hold (see all the articles on jepsen.io) and you still have to deal with corrupted/inconsistent data

To give more colors on the product complexity, you can just look at privacy for kids – there are different definitions of kids per country and even from within the same country. These regulations also have different impacts – e.g. you can’t show ads in Quebec for kids under 13, but can do so in the rest of Canada with some limitations. All these product complexity requires you to architect your system in better ways than just piling if conditions – otherwise your code is unmaintainable and likely incorrect. The same goes for many domains, e.g. as soon as you want to handle international payments, you likely need a full team to support these payments operations (in addition to the internationalization of your app)

Basically these systems are never built to scale from scratch by just a few people, they are the results of many iterations, rewrites and changes specific to their scalability/product issues. Every single aspect of them can require a whole team because it’s that complex – not because of paperwork.

Building and operating a large scale system is like riding a bike – you can read about it but you’ll never learn to bike only from reading books.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_growing-as-an-engineer-you-cant-build-instagram-activity-7209208353703505920-Xo62?utm_source=share&utm_medium=member_desktop)
