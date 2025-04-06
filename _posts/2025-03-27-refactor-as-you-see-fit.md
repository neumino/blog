---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, refactor, techdebt]
title: Automatically format your code
---
{% include JB/setup %}

There’s the myth that engineers want to constantly refactor for esthetic reasons and that PMs must constantly fight such efforts. My experience is that this is a terrible dynamic:

 - You, as an engineer, should refactor code as you see fit – you are free to take shortcuts and hack things for a quick launch, but you’re ultimately the owner of your code. If you pile terrible hacks, they will eventually break and you’ll be on the hook to maintain and clean it up. Large refactoring is always the result of a plethora of minor refactorings not being done.
 - You, as an engineer, are responsible for shipping features fast – so you have to balance tech debt with time to ship. If your goal is to have a perfect and shiny system, you won’t be able to deliver well for the company. The answer is that you should have some amount of tech debt and have to figure out what the right amount is

A few consequences of the above:

 - You have to find the right balance between cutting corners and long term productivity. Be reasonable, gather data from other stakeholders (product, sales etc.) to do the right trade-offs at the company level – if you don’t, someone else will and the decision might be sub-optimal for the company
 - If you want to truly prove that you can lead a large system in a complex and constantly evolving landscape, you have to stick to your system for longer than a year or two – this is why it’s hard to evaluate a candidate that job hop every 2 years, it’s unclear if their work was actually good and/or if they can maintain/evolve a large scale system.

Last but not least, the optimal amount of tech debt will evolve over time – e.g. the cost of tech debt in a small startup is smaller than in a large company that has a large engineer org and tons of systems/products. This is why it’s important for you to understand companies (and other functions) priorities when deciding when to hack and/or refactor.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-refactor-techdebt-activity-7311054398569263106-I3m6/)
