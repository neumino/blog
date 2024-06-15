---
layout: post
category : Growing as an engineer
tags : [softwareengineering, growth, extrapolate, skill]
title: Learn to extrapolate
---
{% include JB/setup %}

There is a lot of content around how soft skills are the most important to grow as a software engineer. While this is very much the case for senior engineers (with some caveats – your soft skill can only cover your lack of technical ones to some limit), I think for more junior engineers, the ability to extrapolate is the most useful one.

The truth is that in large companies (and in smaller ones too), you don’t need to understand everything to be able to build something – e.g. if you build a node.js http server, you don’t need to know every method available on http.Server, only the common ones to build a server. In practice, you can likely build a server by replicating existing code in your company (or somewhere in the internet) without looking at documentation – or using copilot. This is one of the reasons there are so many memes “I have no idea what I’m doing” from software engineers (including senior ones!).

There are some risks/limits to the point above though

 - This is fine as long as the libraries/software you are using have sane defaults – e.g. it is problematic if your database doesn’t have a password (looking at you MongoDB 😉). You can’t really know if the default are sane unless you (or someone in your team/company) peek a bit deeper at documentation and better understand the system
 - You are likely cutting some corners – even if the default configuration is sane, it is likely not be optimal, meaning that you may waste machine resources, not provided the best latency experience for your user etc.
 - You grow your record of shipping features fast but not necessarily your ability to ship high quality systems – you have to find the delicate balance between company growth and your personal one.

The best way to develop your ability to extrapolate is by doing it and gaining experience – build things without looking at documentation and tweak them until they work 🙂. Over time, you’ll subconsciously build patterns and gain confidence in your ability to build systems without understanding every piece of it.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-growth-extrapolate-activity-7204134913145487361-YzPl?utm_source=share&utm_medium=member_desktop)
