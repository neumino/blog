---
layout: post
category : Incomplete thoughts
tags : [privacy, anonymity, regulations, consent, softwareengineering]
title: Anonymization of data is misleading
---
{% include JB/setup %}

People often assume that if their data is anonymized, it can never be linked back to them. There are a few caveats that come with such statement

- Anonymization requires your data to link back to at least more than 1 person – but if there are only two users that share your characteristics, it’s questionable whether your data is actually anonymized. Companies use 50, 100 or whatever they deem acceptable but there are no formal requirements here on what’s reasonable.
- Anonymization works only in the given set of data. Additional data can be used to de-anonymize the initial dataset – this was the Netflix recommendations fiasco. One interesting fact is that this additional data isn’t necessarily third party data: the company that claims your data is anonymized may have everything they need already to deanonymize the data but don’t consider such additional data in their anonymization assessment because it may live in a different table, is not user data or for some other questionable reasons.

Privacy should be a simple field in theory, after all non-technical people should understand how their data is handled to be able to provide their fair consent. This is very far from being the case – I vividly remember the “crazy matrix” at Google that shows you privacy controls and their impact but even then this massive spreadsheet wasn’t complete, perfectly accurate or simple to derive.

From our situation today, there are two paths forward in my opinion:

- We (as a society) decide that privacy isn’t in the hands of the user – but laws/regulations dictate what can/cannot be done for everyone. This may happen because of AI and how an individual cannot properly understand/assess what a model may do.
- Regulations force privacy handling to be significantly simpler such that everybody can easily understand the field. To be very explicit, we cannot rely on companies self regulating themselves – in my personal experience, it was always a struggle to simplify privacy rules because of revenue constraints and other strategic decisions.

What’s the last time you read a privacy notice? How confident are you that you understand all the practical implications of your consent?

[LinkedIn post](https://www.linkedin.com/posts/tumichel_privacy-anonymity-regulations-activity-7175158948763705344-Gacj/)
