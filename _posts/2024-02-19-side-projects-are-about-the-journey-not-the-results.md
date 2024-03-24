---
layout: post
category : Growing as an engineer
tags : [softwareengineering, side, project, journey, moonlighting] 
title: Side projects are about the journey, not the results
---
{% include JB/setup %}

This is a difficult time for junior software engineers and new grads with all the ongoing layoffs (Google, Facebook, Amazon, etc.). Every now and then someone will ask me what they should work on during their free time to hone their skills.

My personal advice is that you shouldn’t blindly focus on learning a new skill (e.g. a new data science tool) but rather:

- First find something interesting to you, not necessarily something that will obviously look nice on your resume
- Spend time on it (polish it, expand it etc.) such that it is not just a shallow project (e.g. just following a tutorial) – this should be easy if you find your project interesting. My personal take is that almost everything is interesting if you go deep enough.

From there, you should have a project that you can:

- Talk with passion about – As an interviewer, I always enjoy people talking with excitement about their projects.
- Describe in detail and illustrate interesting and non obvious learnings. This is the most valuable asset from your work as it reflects that not only you did the work but that it was filled with difficult aspects that you overcame.

Here are two examples of personal projects I did (albeit related to my job) when I was much more junior.

- rethinkdbdash – this was a node.js driver for RethinkDB (a NoSQL database). Beside using with promises (which were a new thing back then), some of the interesting parts were all the interesting edge cases (e.g. when too many TCP connections were opened and that the max number of file descriptors was reached).
- reqlite – this was an implementation of RethinkDB in javascript. Besides being useful for testing (you could run your database in process during nodej.js tests!), I learned a lot about internal details of how databases work.

This helped me grow and land multiple job offers – and they were fun to do.

Hopefully this is a useful advice – if you have others, feel free to share them

[LinkedIn post](https://www.linkedin.com/posts/tumichel_growing-as-an-engineer-side-projects-are-activity-7163562582111436800-hmE9?utm_source=share&utm_medium=member_desktop
