---
layout: post
category : Incomplete-thoughts
tags : [softwareengineering, privacy, encryption, local, remote]
title: Microsoft AI feature’s privacy fiasco
---
{% include JB/setup %}

Microsoft is about to launch a new AI-powered feature (Recall) that screenshots everything you do on your PC. It’s super creepy, but let’s ignore this issue in this post. One of the interesting aspects of Recall is that the AI models run locally, so data doesn’t leave your laptop but it also means it stays on your laptop.

Microsoft probably wanted to position themselves as a privacy champion, an entity that doesn’t benefit from the data being collected (similar to Apple's position on privacy *in general*). The caveat here though is that they traded off this goal with other privacy aspects (mainly driven by security). Keeping data locally means it can be exfiltrated in bulk – which they could prevent if data was remotely stored and not fully accessible (e.g. only a single data point can be returned if the right query is provided).

This is one of the points made in the Verge’s [article](https://www.theverge.com/2024/6/3/24170305/microsoft-windows-recall-ai-screenshots-security-privacy-issues) in addition that Microsoft decided to encrypt this data – I don’t believe they simply forgot. In this instance, I don’t believe that encrypting the data would fully fix the problem though – both the encrypted data and the key would still live on the device, so while the task of exfiltrating a lot of data is harder, it’s not significantly harder.

My 2 cents is that a remote solution would have been better privacy/security wise as long as the right behavior is done on Microsoft’s server. This is however probably not what a non tech-savvy or privacy-savvy person would think though. This comes back to one of the issue privacy regulations are facing: It is a very difficult space to understand on the technical side in addition from being complex on the legal side

In the case of Recall, I think the lack of control from the user is also a pretty massive concern – I definitely don’t want everything I do on my computer to be retrievable at a later time (by me or anyone else). This case is one more illustration where AI is opening the door to new products and new privacy concerns that are not well addressed by existing regulations or standards.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-privacy-encryption-activity-7204459600123727874-rgQb?utm_source=share&utm_medium=member_desktop)
