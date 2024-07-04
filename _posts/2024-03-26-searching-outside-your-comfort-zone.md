---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, comfort, challenge, light]
title: Searching outside your comfort zone
---
{% include JB/setup %}

As you grow and become an expert on a service/system, you will eventually be given a broad problem, e.g.: how can we make engineers more productive, how can we reduce user latency or how can we increase revenue.

The easiest thing for you to do is to figure out how to improve the metric you want to move by looking at the system you are familiar with. While this might be the right solution in some cases, you should look at the problem end to end – or you run into the streetlight effect issue (where a person look for their keys not where the lost it but where there is street light)

For example if a user spends 2 seconds loading your app, reducing latency by 20 ms on your server is not likely the right solution – even if the server is your area of expertise. Similarly, if you want to make engineers more productive, making the build a few seconds faster doesn’t matter if people spend days trying to merge their code due to flaky tests.

Look at the problem end to end, you should try to estimate the cost of different part of the whole system and from there go after the right ones:

- The expensive steps since a 1% improvement there will yield the biggest results
- The steps that are easily optimized because of known shortcuts taken in the past

You can also look beyond the metric. For example if your goal is to improve latency for a website, the real (and better?) goal might be for people to feel that the app is faster. One interesting experiment I ran in the past showed that:

- The initial response chunk is the most important – this is what drives the most of abandons
- Showing a layout of your page without text but with gray rectangles makes the user more willing to wait (and stay)

TL;DR: is that you should search for the solution of your problem wherever it is – regardless of whether you are familiar with this space

[LinkedIn post](https://www.linkedin.com/posts/tumichel_growing-as-an-engineer-searching-outside-activity-7178420465864974336-tATp?utm_source=share&utm_medium=member_desktop)
