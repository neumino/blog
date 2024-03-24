---
layout: post
category : Incomplete thoughts
tags : [softwareengineering, ai, machinelearning, predictions, regulations]
title: Concerns around AI predictions
---
{% include JB/setup %}

One of my largest concerns around AI today is tied to its predictions. Predicting outcomes is not a new field, many companies have been predicting the likelihood of you clicking on a given ad for years. AI predictions are becoming quite concerning when they impact a critical domain of someone’s life: their health insurance (are they likely to be sick?), their finances (can they pay their loan in time?), their employment (will they be a good and honest employee?) etc.

The few categories of issues around AI predictions are:

- AI reinforces patterns in past data and can further solidify bias and inequality from the past. If you train your model on bias data, you will get bias outcomes.
- AI predictions result in an unfalsifiability problem – until the future event happens, a prediction remains unverifiable, resulting in the inability for individuals to challenge them as false. Similarly, these predictions involve a preemptive intervention problem, where decisions or interventions render it impossible to determine whether the predictions would have come true.
- AI predictions can lead to a self-fulfilling prophecy problem where they actively shape the future they aim to forecast

There aren't a lot of privacy regulations to help individuals today. GDPR is probably the best one where it individuals have the right to not to be subject to a decision based solely on
automated processing. The gap is that there are no guidance on how human and AI should operate together – this is especially concerning as:

- People cannot fully understand how a model works as it ingested more data than a human can read
- People often over rely on automated advice – it’s easy and there must be a reason why these systems are used after all.

So even if a human intervenes, it’s not obvious that they can rectify the damage being done by a bad prediction.

In regards to bias, I could probably write a full post about it, but the short version is:

- You can’t remove bias by just removing characteristics you don’t want to be used – the model will be able to re-infer them.
- Models may create new biases that don’t exist today – e.g. if they somehow find that the color of your eyes impact your likelihood of committing a crime, a new criteria (eye color) will become a bias (that doesn’t exist today)
- AI can’t use data that’s not quantifiable – what makes us humans, e.g. our emotions, morality, values etc. We are also more than just the data about us.

I don’t have a good way to end this post because I don’t know what’s the right path forward here – we probably need some regulations, but I don’t think we know how to properly handle these predictions today.

Thoughts? How do we prevent the science fiction movie Minory Report from becoming a reality?


[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-ai-machinelearning-activity-7177695664225558528-hWZn?utm_source=share&utm_medium=member_desktop)
