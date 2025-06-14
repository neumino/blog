---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, doc, length, effective, communication]
title: Longer design doc doesn’t mean better docs
---
{% include JB/setup %}

A (sadly) too common assumption is that a long design doc means that the problem being solved is more important, more complex and/or more impactful. This is wrong.

The only thing a longer doc guarantee is that it takes longer for people to read. As a senior IC, my time is limited (and precious). I don’t have time to read 50 pages for a simple problem unless either the solution is complex and/or trade offs are not obvious.

If you can rewrite your doc to be shorter while carrying the same information, you should. Practically speaking, a shorter doc means:

 - People will read it/review it faster – I can spend 5 minutes reading a doc multiple times during the day. I rarely have a 2 hour bloc to just read one doc.
 - People will better review your doc – if the critical information is drowned among pages and pages of noise, people may miss it. This means that maybe you’ll have to revert some of the work you did because the problem will show up too late.

On a similar note, simple language is better than long and convoluted terms – basically anything can help the reader should be considered. A few practical tips that may help:

 - Write “use” instead of “utilized”, use simple terms as much as possible – keep in mind that you may work with non-native English speakers
 - Avoid filler terms that don’t bring value (e.g. It goes without saying/needless to say) – these just takes time to read and bring no value
 - Remove the security/privacy sections (or whatever sections) that are empty
 - Write multiple versions of your doc for different audiences and different goals (e.g. a short one pager with context, problem statement and high level solution to get rough alignment, a more technical doc with details for people who care about these etc.)
 - Don’t put code in your design doc – code should be reviewed in PR, not design doc
 - What other tip would you give to others (or to your older self)?

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-doc-efficient-activity-7338941076604395521-u_fk/)
