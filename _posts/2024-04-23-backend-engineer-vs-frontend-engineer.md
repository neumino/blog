---
layout: post
category : Hot-take
tags : [softwareengineering, frontend, backend, stateful, stateless]
title: Backend engineers who look down on frontend engineers are wrong and short sighted
---
{% include JB/setup %}

There is the assumption in our industry that being a backend engineer is more prestigious than being a frontend engineer and in general the idea that frontend engineering is for “bad” software engineers. Not only is this wrong, it showcases how short sighted some engineers can be.

Both frontend and backend engineering has evolved a lot – Frontend engineering isn’t about centering a div nor is backend engineering about serializing HTML for a browser to render.

I actually think that frontend engineering is harder than backend engineering, the rationale being:

- You have a fragmented surface (Android, iOS, Chrome, Firefox etc.) – so essentially more surface to maintain/support. To give more color, one thing I remember from my time at Google was how some Samsung TV decided that the `eval` method in JavaScript wasn’t good and removed it from their browser.
- Your app is most of the time a stateful one – except for very simple ones. Backend engineers tend to flee away and prefer stateless not because it is more efficient but because it is simpler to build/maintain.
- You have less insights and control over your system. If your server OOMed, you can retrieve a core dump and debug things but if your webapp runs out of memory you may not have a lot to work on.
- More unexpected things can happen. For example you may also have some browser extensions that interact poorly with your app – these aren’t necessarily bugs that impact only a few users, they have the potential to take down your whole service. You may have malware that steals user cookies and replay traffic.

As an engineer, you should work with the rest of your colleagues to make your company successful. Looking down on your coworkers is a recipe for disaster – this is especially detrimental as both frontend and backend engineers have to find the right balance between powerful apps and simpler systems  (e.g. the two extremes are simple static apps with simple-ish backend services or powerful apps that are more complex to build/maintain).

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-frontend-backend-activity-7188552210643910658-u8x-?utm_source=share&utm_medium=member_desktop)
