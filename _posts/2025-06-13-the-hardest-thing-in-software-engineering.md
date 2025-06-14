---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, migration, legacy]
title: What’s the hardest thing in software engineering?
---
{% include JB/setup %}

If I have to pick one thing that’s very hard with large scale software, it would be what engineers fail the most – it’s not communication, not leadership or some kind of social skills. It’s planning and executing a migration.

How often did you (or someone in your org) design a new shiny system to replace a legacy one, but failed at closing the migration resulting in the need to maintain two systems? The root cause is often two fold:

 - When designing the new system, not enough thoughts were poured into dealing with edge cases, undefined behavior or legacy journeys. This results in a clean system at first, but over time and as more traffic is migrated over, more and more functionality that can’t be properly supported are added to the system – and eventually, you may end up with something you can’t support in the new system
 - When migrating to the new system, not enough investment were made into tools to migrate the service, which often result in a lot of manual testing, a lot of rollbacks and in general a high operational cost

One thing that works well is to build a shim in front of your legacy and new services such that you can tee traffic and run diffs (e.g. duplicate 1% of traffic to the new system, and compare the responses of both systems). This isn’t as straightforward as it seems, but definitively doable:

 - For write operations (and in general downstream dependencies), retain the request/responses from these dependencies and mock them in the new system
 - Make sure you can compare apple to apple – so in case your new system has a new API, build a library to convert from the new API to the old one

From there, you can tee traffic and fix things until you get no differences. This is significantly more efficient than trying a live experiment and manually finding bugs or waiting for users to report issues. Because you tee traffic, you can detect (and correct) edge cases even if they are very rare (e.g. <0.1%)

Thoughts? What do you think is the hardest with distributed software engineering?

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-migration-legacy-activity-7339305620887465985-VIk3?utm_source=share&utm_medium=member_desktop&rcm=ACoAAAR7xwEBecyVugMG81Ql1jTrMg6xtopAnTU)
