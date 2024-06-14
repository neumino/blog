---
layout: post
category : Growing as an engineer
tags : [softwareengineering, id, uniqueness, metadata]
title: Augmenting ids
---
{% include JB/setup %}


In many systems, an object is given a unique id. Uniqueness in the given table is often the only property these ids have when they could (and probably should) have more properties.

You can add additional metadata in these ids, e.g. their type, their geo location, some timestamp etc. Just reserve the first few bits for this. How much metadata you want to add depends on your requirements and your system.

 - Adding the type in your ids means that you can know what a chunk of data is as long as there’s an id inside – you just need to decode the type in the metadata. This is especially useful in case you have to deal with a data leak – you can know at a glance what table was leaked. It also allows you to verify that some ids don’t end up in regions they shouldn’t – e.g. if you don’t want to allow user ids to flow to a central region for logs, you can easily run a query for this.
 - Adding the geo location where the data should reside allows you to monitor data residency requirement easily without having to do additional joins in your enforcement offline system
 - Etc.

What metadata you should add is a balance between your product/privacy needs and the cost of storing these extra few bytes.

Note that an interesting property of encoding the type in the metadata is that you can store all your entities into a single namespace – this means every entity can be linked to another one the same way regardless of what these objects are. I believe this is what Facebook does and is one of the fundamental pieces that allows them to implement deletion at scale – they know how every object is tied to another and how deletion should propagate, from there they “just” cascade the deletion.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-id-uniqueness-activity-7202685351973261315-_1Df?utm_source=share&utm_medium=member_desktop)
