---
layout: post
category : Growing as an engineer
tags : [softwareengineering, interview, software, properties, design]
title: The properties matter more than the name
---
{% include JB/setup %}

When I conduct design/architecture interviews, candidates sometimes don’t feel comfortable using specific technologies (e.g. Kafka, Redis etc.) to solve the problem. My guidance has always been that it’s fair to use existing technologies as long as you can describe its properties.

Design interviews are open ended questions and there is so much ground to cover that I honestly never had a need to go back to a technology being used to dive into how it works (as far as I can remember). What regularly often happens though is the candidate throwing a technology name without understanding what guarantees it provides or its role in the architecture.

One example is when a candidate tells me they want to use Redis because they used it before and that it’s fast. Whether they used it before or not is not relevant to the interview and what I want to understand is for example how/when writes are going to be persisted and how we handle errors. In many problems, Redis’ default 900 seconds to write its snapshot to disk is not a good fit.

Similarly, candidates often go with a relation database when they store a single table or with a NoSQL database because it’s “fast”. These are flimsy arguments that reflect a lack of understanding of these technologies and when we should be using them.

One of the signals I want to get from these interviews is whether the candidate would be able to solve a problem with the right tools – not some arbitrary tools they used in the past that aren’t a good fit for the current problem at hand.

As you use different technologies, you should spend some time to understand why these and not others, the capabilities/guarantees they provide and their limitations. Multiple technologies exist because they fit different use cases (e.g. that’s why there’s not one database strictly better than all others for every use cases).

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-interview-software-activity-7183493917646946307-vyLc?utm_source=share&utm_medium=member_desktop)
