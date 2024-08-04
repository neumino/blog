---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, completeness, problem]
title: The completeness problem
---
{% include JB/setup %}

If you work on large scale systems or a very complex product, some of the hardest questions are around completeness – and they are fairly simple questions, e.g:
What are all the storage systems in the company?
How many log entries did you lose?
Etc.

To give more colors using the first question, the answer is not necessarily that straightforward because while you may have a single database in prod, you have to consider:
Other serving infrastructure like caches, queues, backups etc.
Storage systems in non prod environment – e.g. while prod is usually well strapped, dev is often a much more open environment where engineers can freely spin up databases for ad-hoc testing
Storage systems for non product cases – e.g. Jira can be considered as a storage system. Fun fact is that at Google, buganizer (Google’s in-house Jira for tickets) was used by some team as a database – which the buganizer team complained about a few times

What makes the question really hard though is how can you be confident that you didn’t miss anything? For example, how can you guarantee that:
No one in your company created a database for demo purposes under an ad-hoc cloud account?
You don’t have an in-house database running on standard virtual machines that you forgot about about? So this type of database wouldn’t show on your cloud console
Etc.

There are some solutions to address these potential gaps (e.g. reconciling your final cloud costs with what you are aware of) but in general you can get more confident but you will never be sure since you can’t assert what you don’t know.

Similar problems exist in different domain – e.g. knowing your log loss rate is pretty hard since log loss happen in edge cases hard to reproduce but more importantly that these losses are hard to detect in the first place (otherwise you probably wouldn’t have lost data).

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineer-completeness-problem-activity-7223341464263557120-eLhe?utm_source=share&utm_medium=member_desktop)
