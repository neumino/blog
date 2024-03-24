---
layout: post
category : Growing as an engineer
tags : [softwareengineering, culture, paranoid, spam, abuse] 
title: Be paranoid
---
{% include JB/setup %}

The best way an anti-spam/abuse TL at Google summarized their work was: “Anything that can be abused will eventually be abused”. Similarly engineers focused on stability/reliability will tell you to be paranoid and that: “Anything that can break will eventually break”.

While the statements above don’t mean you should address all the gaps/risks and ship perfect products, they are something you should always keep in mind. You may very well decide to trade some risks in favor of other priorities for your company but this should be an explicit choice.

The main benefit of keeping these “rules” in mind for you is that over time you will produce better/safer code (for abuse/security/reliability) at no extra cost. For example, you will design APIs that can’t be misused (e.g. you’ll build narrower APIs), your enforcement on data inputs will done on the backend (and not just the frontend), your code will naturally restrict possible abuse (by reducing the surface of attacks) etc. Even if the costs of addressing the gaps are too high for you to address now, you can quickly document them to help mitigations of future outages/attacks.

A few interesting examples I’ve seen:

- Bad actors abusing a minor delay in data propagation to get free ads impression
- Engineers using an internal tool (for scheduling/planning) as a database
- Data validation done in the browser only
- All kind of creative ways by engineers to bypass privacy/security enforcement

[LinkedIn post](https://www.linkedin.com/posts/tumichel_growing-as-an-engineer-be-paranoid-the-activity-7166099273636384769-U61c?utm_source=share&utm_medium=member_desktop)
