---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, functional, programming, imperative]
title: Functional programming considered harmful
---
{% include JB/setup %}

“<X> considered harmful” were the title of many spicy documents at Google arguing for better code/design patterns – and very often controversial ones. Functional programming is fun but is not adequate for most cases.

I happen to have a strong background in mathematics but also a keen interest in quirky theorems, properties and proofs – and I find functional programming entertaining. It’s an easy (and natural?) way to solve certain problems. With that being said, I believe that functional programming is not appropriate for large companies and in general for most use cases.

As your company grows, the truth is that your bar will eventually lower – you can’t have a company with a thousand engineers where all of them are staff engineers. From there, code has to be readable and maintainable by everyone in the company – so code has to be simple. Functional programming is fine in easy cases (e.g. `seq.filter(x => x > 2)`) but isn’t adequate when things get more complex.

Two practical issues I have with functional programming that aren’t about code esthetics or readability of the code itself (as these might be personal preferences):

 - Stacktraces are less readable in case of errors compared to their equivalent with imperative programming – they are longer and may end up truncated.
 - You may end up with stackoverflow errors – this is especially problematic if the depth of your recursion depends on user input. You basically have a DDOS vulnerability in your system.

Functional programming is akin to object oriented programming – they are good ways to write code in some cases, but you shouldn’t force them when they aren’t adequate.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-functional-programming-activity-7217180836570218499-g2ap?utm_source=share&utm_medium=member_desktop)
