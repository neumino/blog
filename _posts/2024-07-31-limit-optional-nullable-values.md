---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, null, optional, defensivecode]
title: Limit optional/nullable values
---
{% include JB/setup %}

Note: This post aims to be a bit more practical than usual, so let me know if these are interesting to read.

Optional and nullable values are terrible in large systems – this isn’t about aesthetics preferences but maintenance costs, outages and correctness issues. For example, you have probably crossed path with code that looks like this:

```
function process(order) {
 If (order == null) { return; }
 // do things with order
}
```

The issues with optional/nullable values are:
 - They tend to propagate everywhere and every call site using them has to write defensive code to figure out what to do when the value is missing – so you have a proliferation of defensive code
 - The semantics are unclear – in general this is the problem with defensive code. In the snippet above, is processing a null order a viable call? Why would someone try to process such an order in the first place?
 - The defensive code prevents your server from crashing, but it may silence what could be a very bad bug – at the end of the day, you may end up wasting weeks debugging such edge cases (or worse, your company may lose millions until someone realizes that there was a bug).

Similarly as a previous post “Good APIs break early”, it’s much better to cleanly handle null/missing values as soon as they appear and not propagate everywhere. This makes your code more concise, simpler to read and easier to maintain.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-null-optional-activity-7224428647644827648-0QuO?utm_source=share&utm_medium=member_desktop)
