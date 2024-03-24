---
layout: post
category : Incomplete thoughts
tags : [softwareengineering, privacy, inferred, data, personal] 
title: Inferred data should be regulated similarly as collected data
---
{% include JB/setup %}

Privacy regulations focus a lot on data collection but not on data inferred about them – e.g. GDPR requires (with some exceptions) users to explicitly opt-in for their personal data to be collected/processed and provides them a right to delete/correct that data.

Two interesting illustrations of this problem are:

- There is the “famous” case about the retail store Target that developed a model to predict if a woman was pregnant based on their shopping patterns. This eventually led to a case where a teenager was receiving baby product ads before knowing that she was indeed pregnant.
- Another one I’ve seen is how some companies allow you to not disclose your gender but may infer it. Gender is a pretty complex social and legal status/construct and it’s reasonable that a model would sometimes get it wrong. The main problem is that it is extremely difficult (or impossible) for a user to correct this data themselves.

Some of the interesting challenges around regulating generated data are:

- The scope is massive as companies may infer data about you that you never thought about (it goes well beyond gender/age/etc.). Some may not even make sense from a human perspective.
- It’s impossible for an individual to understand how the data was generated (since it was trained on other individual personal data), making it hard/impossible for them to understand and argue against

Practically speaking, it seems impossible to rely on users managing all the generated data about themselves. Assuming there should be some protections for people, we need a global framework – from there, we will likely need a framework trying to reduce risk which leads to more difficult questions (e.g. how do we define risk, what’s an acceptable one, how do we alter the threshold etc.)

Or maybe we’ll have an hybrid approach where some inferred data must be manually correctable by the user (e.g. gender, health data etc.) while some are not (and governed by a risk based framework).

Thoughts on how privacy regulations will shape what we can do with generated data?

[LinkedIn post](https://www.linkedin.com/posts/tumichel_incomplete-thoughts-inferred-data-should-activity-7166824071056338945-1HPZ?utm_source=share&utm_medium=member_desktop)
