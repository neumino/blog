---
layout: post
category : Growing as an engineer
tags : [softwareengineering, timezones, madness, weekendwisdom]
title: Run away from time representations (and timezones)
---
{% include JB/setup %}

Daylight saving time in the United States is starting this year on March 10th but the Netherlands (where I am located) are changing time on March 31st, so for 3 weeks my calendar is screwed up – some meetings are one hour early but not all!

I thought this would be an interesting opportunity to talk about time representations and timezone in general. I’ll go straight to the point, just use epoch time and use well known libraries to represent these times in some specific timezone.

Some fun fact about time representations and timezone:

- Not all timezones are an exact number of hours from GMT, e.g. Sri Lanka is +5:30. More interestingly, Nepal is +5:45.
- Like mentioned earlier, daylight savings are not happening everywhere at the same time but did you know that in the southern hemisphere clocks are turned backwards when they are turned forward in the northern hemisphere?
- Leap seconds are also interesting events – did you know they can result in the time 23:59:60? Does your code allow for the value 60 to be stored?
- Countries regularly change time, but some change days! For example, Samoa decided on December 29th 2011 that its next day would be December 31st 2011 – supposedly to make trading easier with Australia (to be on the same side of Greenwich)
- When countries change calendars, it tends to result in interesting events. In Great Britain, 2nd September 1752 is followed by 14th September 1752 (11 days are missing!) to correct errors from the Julian calendar.

Implementing timezones yourself will drive you crazy -- the most evil thing you can do in an interview is probably to ask someone to write a library to represent time in different countries 😅

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-timezones-madness-activity-7172622238024617984-krWv?utm_source=share&utm_medium=member_desktop)
