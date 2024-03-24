---
layout: post
category : Growing as an engineer
tags : [softwareengineering, small, pull, request, breakdown] 
title: Write small pull requests
---
{% include JB/setup %}

At my first job, we didn’t do code reviews at the beginning, and later one when the company started to do review, my code was still not reviewed because I was the only person working on frontend/node.js code. When I started at Google, the first pull request I sent (or changelist as it’s called at Google) was about 3000 lines of code.

It took a few days to get approved and maybe just 2-3 passes, but looking back – it wasn’t the best way to proceed. I just didn’t know as I never reviewed code before and never had to have my code review.

Sending code to be reviewed is similar to having a discussion about your project. You have to structure your presentation – first give context/problem, then describe at a high level the solution and finally go deep into each section one by one. The way to achieve this with code changes are:

- Write a clear description of your code change (the context, what your change is doing, what are the follow PRs coming up, what are the risks etc.)
- Break down your changes into chunks that a person can easily process – someone can easily understand a high level skeleton, or a detailed but short-ish implementation. It’s very hard for someone to parse a multi-thousands line code change.


The interesting thing is that you will likely be able to merge your code faster by sending X small PRs rather than one massive one even if you’ll need more interactions with the reviewers – your reviewer will just take significantly more time to review your massive PR. The drawbacks of large PRs don’t stop here though:

- The review you’ll get for a massive PR will less thorough as people will dread doing it and may skim over some parts
- You will waste more time if changes are needed – e.g. if your approach wasn’t good, you have to discard more work than if you had sent just a skeleton
- Getting your code in production might take more time because your changes will likely trigger more pre-merge tests (since more code is being changed) and in case a rollback is needed, you will have to roll forward more code (and maybe deal with more merge conflicts)

Sending human reviewable changes is a useful skill to have – it’s one of the little things that you never have a chance to learn about at school.

Bonus on the LinkedIn post: Interesting illustration based on the prompt "cartoon of a software engineer breaking a change in small pieces"

[LinkedIn post](https://www.linkedin.com/posts/tumichel_growing-as-an-engineer-write-small-pull-activity-7163924941128605696-jdbi?utm_source=share&utm_medium=member_desktop
