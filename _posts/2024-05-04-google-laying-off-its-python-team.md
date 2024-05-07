---
layout: post
category : Incomplete thoughts
tags : [softwareengineering, google, layoff, python, golang]
title: Google laying off its python team
---
{% include JB/setup %}

Google recently laid off more people, among the teams impacted was the team responsible to maintain the python ecosystem at Google. While a lot of articles focus on how Google did so to move labor to cheaper markets, I think it also reflects Google's will to move away from python.

Google used python a lot in the past (like a lot, e.g. YouTube used to be fully written in python for most of my tenure at Google). Once the main large products were moved out of python, my understanding is that what was left was mostly internal tools and scripts. Google made an explicit (and internally official I believe) decision to move to golang for this use case. I wasn’t part of this decision or even remotely involved but my guess is that it’s too hard to maintain such a python code base:

- It was lacking tests – internal and one-off tools often don’t have tests written
- It was a large code base – meaning that every edge cases you haven’t thought about will happen when upgrading the language or some core libraries

Golang reflects Google internal approach to what code should look like (e.g. when you write C++ at Google, you can’t throw errors – same as in golang) and how it should behave (e.g. you should be able to catch most of errors are compile time rather than runtime).

From there, it makes sense for Google to part away with its world class python team

A few closing thoughts:

- Google will still have a python team but because it is less mission critical, it won’t invest as much resources as it used to – so yes the team may move to cheaper markets, but this reflects the importance of the work for Google
- I haven’t met any folks of the Google python team, but I can’t even fathom how hard their job was – and how amazing that they were able to pull it off with such a small team. Hats off – As much as it must sting to be laid off from a job you loved, I’m sure they will bounce back in no time
- Python isn’t going anywhere – Meta is still heavily investing in python and python is still #1 on the Tiobe index

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-google-layoff-activity-7192538486044864512-ggZR?utm_source=share&utm_medium=member_desktop)
