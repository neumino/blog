---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, privacy, infrastructure, compliance, security]
title: What’s privacy infrastructure?
---
{% include JB/setup %}

I usually describe my job as building privacy infrastructure – my goal is to let people do what they are good at (e.g. let the infra engineers launch their new load balancer, let the product engineers launch their new features etc.) without having to worry about questions like:

- Can I log this data? Do I need to encrypt it in transit?
- Can I copy this data across regions?
- Should I talk to legal? Do I need their explicit approval?
- Etc.

In general the idea is that if engineers can merge their code without having CI/CD complain that some policies will be broken, they should be good to go.

In practice, building privacy infrastructure is like crafting standard infrastructure but with a focus on shifting left for everything tied to privacy/compliance – the goal is to bake some of the invariants we want to enforce deep in the stack such that engineers can’t bypass it and don’t have to worry about it as long as they use standard infrastructure.

I work closely with other infra teams as my work usually sits on top of their infrastructure – I’m also one of their close allies as I get to wave a stick to move some infrastructure projects a bit faster for privacy/compliance/security requirements.

If you have experience building large scale infrastructure, we are hiring staff software engineers (and above) in Amsterdam (also in the US in San Francisco/Seattle) – reach out if you’re interested!

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-privacy-infrastructure-activity-7191813700117299200-k46J?utm_source=share&utm_medium=member_desktop)
