---
layout: post
category : Growing as an engineer
tags : [softwareengineering, blob, unstructured, schema]
title: Blobs are your ennemy
---
{% include JB/setup %}

It is very convenient to store a blob (e.g. a json object) in logs or in a database – after all, the next time you want to add more data, you don’t need to update the schema. This is however a terrible decision.

There are different issues with this approach:

 - Indexes in general don’t work – so performance suffers. You can’t create an index on <blob>.<field> for example with most common databases.
 - Your database cannot enforce the schema of your blob – e.g. if you store a json object, you can’t easily enforce that every of these json objects has a key “id”. In practice it means that
 - You need to write defensive code – so not only more code, but also code that makes it difficult to understand (e.g. is the defensive code to not crash or because the error may happen?).
 - You need to monitor for invalid data – you should have alerts for every piece of defensive code that result in an error/unexpected behavior
 - Similarly as above, because data may change from code changes, updating the schema is not a choke point to make sure only appropriate data is stored. This makes it very difficult to enforce rules like “<type of data> must be encrypted with a customer provided key”
 - Your data may be corrupted since your database won’t enforce the schema and the serialization. This is surprisingly more common than what people think – e.g. if you upgrade the library that serialize the data, you may end up with errors during deserialization.

In general, blobs are fine for your personal project, they are difficult to justify in systems used/updated by many engineers – you save time only if you don’t implement any of the defensive code/monitoring, but that just makes your system pretty brittle.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-blob-unstructured-activity-7202322989667729409-N44x?utm_source=share&utm_medium=member_desktop)
