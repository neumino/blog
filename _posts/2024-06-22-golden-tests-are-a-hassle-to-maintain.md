---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, test, golden, maintenance]
title: Golden tests are a hassle to maintain
---
{% include JB/setup %}

Golden tests are tests where you verify the whole response from a service – you basically do something like `assert(full_response == expected)`. While these are easy to write, they are terrible to maintain – and most of the time you shouldn’t have such tests.

These golden tests are terrible to maintain because

- Every single change to the API requires you to update these tests even if you add a new field. This result in many large tests over time when it would be much better to have small tests verifying only specific properties of the response
- They are hard to manually update – the responses grow over time and updating them gets harder and harder. You may build some tools to automatically update them but in this case people tend to not pay attention to the changes – they will mostly just run the tool and send the PR. This was my experience at YouTube where people would just automatically update these golden tests and not pay attention to them – thankfully YouTube moved away from such tests.
- They slow down the time to merge – They tend to be far from the code changes and the local tests, so you sometimes need an additional back and forth with pre-merge checks. You will likely find about these broken golden tests after creating the PR and after CI/CD runs all the tests
- They are brittle – they test everything so they often break either because of some flaky fields (e g. timestamps) or because of race conditions between changes.

My experience is that you shouldn’t write golden tests. The only viable case is when your service is meant to be very stable and where you actually want to assert the whole response – but even then, I would argue that having smaller tests asserting specific part of the response is better (where the sum of all these tests is similar to asserting the correctness of the whole response).

What are your experiences with golden tests?

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-test-golden-activity-7210295476087046144-jXFc?utm_source=share&utm_medium=member_desktop)
