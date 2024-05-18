---
layout: post
category : Growing as an engineer
tags : [softwareengineering, tdd, testdrivendevelopment, test, api]
title: TDD is not enough (or not for what matters the most)
---
{% include JB/setup %}

Test Driven Development (TDD) is frown upon in some software engineering circles because they think it’s a slow way to write code. If you agree that your code should have tests, using TDD or not doesn’t change anything in the outcome –  I wrote about whether tests are needed in the past, and while it’s not always true, it’s often the case. From there, it doesn’t matter if you write the tests first then the code, or the code first then the tests – the end state is the same.

At the end of the day, TDD is more a personal preference – similar to using vim, emacs or visual studio. What’s more important in TDD (and maybe something rarely considered), is that it helps you think about your API early on – so the chance of building incompatible APIs is low in my opinion and you likely end up saving time.

While TDD helps you think about APIs, it is sadly not enough to design fail-proof APIs – you can still design crappy APIs using TDD. This is one of the pitfalls of TDD where some of its practitioners assume their APIs must be good because they are using TDD. Regardless of your development workflow, you should carefully craft your APIs – make them semantically meaningful. This is the only way to make a system resilient to time (in regards to a large number of engineers iterating on it). Good APIs is a personal-ish vendetta that I'll probably write more about later on.

I personally regularly use TDD even if I wouldn’t call myself an official practitioner. I find it easier to iterate on my changes if I have tests to verify the expected behavior – TDD is something I will use more when working on a complex code base that I’m not very familiar with. In general tests are the best entry point when jumping in a new code base – while this is something I personally do, I’ve also witnessed many senior peers jumping in a new code base by adding missing/fixing tests to ramp up

What’s your take on TDD?

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-tdd-testdrivendevelopment-activity-7196162362955939842-hvLe?utm_source=share&utm_medium=member_desktop)
