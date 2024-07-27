---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, communication, absolute, relative, percentage]
title: Good APIs break early
---
{% include JB/setup %}

I haven’t posted on LinkedIn for the past few days because I was very busy with work but mostly because I just moved. As part of my move, I had to disassemble and reassemble a bunch of Ikea furniture and noticed how Ikea uses interesting patterns to make sure you don’t improperly mount things – which is very similar to how you should build your APIs.

If you don’t pay too much attention to the Ikea assembly instructions and try to mount the leg of your table in the wrong direction (e.g. inward instead of outward), you’ll notice how holes don’t align – and that you basically can’t make such a mistake. The way you build your APIs should be very similar: make bad usages impossible in the first place.

If you can, design your APIs such that bad usages are impossible, e.g. rather than having two configuration knobs that have to be in sync, have a single one that controls the two behaviors you want. If you can’t make bad usages impossible, try to return an error as early as possible:

 - For RPCs, return a clear/actionable error as soon as the request is received rather than trying to handle it somehow
 - For libraries, return a build error for compiled languages or a runtime error (that hopefully will get caught in test rather than prod)

While it might be tempting to handle incomplete/malformed request because it seems more user friendly, it is not because:

 - In case of errors, people will likely waste more time trying to figure out what the problem is. The most time consuming bugs I chased in my career were always about undefined behaviors being silently ignored/swallowed.
 - If your users rely on an undefined behavior, the behavior eventually becomes official and you can’t break it (or at least without careful trade off, comms and work)
 - Undefined behavior makes proving correctness of your system significantly harder – e.g. if you assume your system is compliant with <some requirement> because users shouldn’t send a certain type of request, you have to chase all your users to make sure this isn’t the case. It’s much easier in this case to just throw an error for this type of invalid requests.

Good APIs have many other properties, but this is the first post on this series.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_growing-as-an-engineer-good-apis-break-early-activity-7221167129214029824-SRAZ?utm_source=share&utm_medium=member_desktop)
