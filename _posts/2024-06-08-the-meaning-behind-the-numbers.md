---
layout: post
category : Growing as an engineer
tags : [softwareengineering, metric, number, bias, interpretation]
title: The meaning behind numbers
---
{% include JB/setup %}

It’s very easy to draw the wrong conclusions from numbers if you misunderstand their scope, ignore their biases and misinterpreted their properties. This is something fairly common in real life but also in data driven tech companies.

One of the examples I have witnessed during my tenure at YouTube was when people were talking about ad fill rate – how often we could serve an ad when we could have. The important part to clarify in this definition is “when we could have”. Multiple definitions were used:

 - The number of YouTube pages loaded
 - The number of YouTube pages loaded for non premium users
 - The number of YouTube pages loaded where YouTube policies allow ads
 - The number of YouTube pages loaded where YouTube + Ads policies allow ads
 - The number of YouTube pages loaded where policies and quality decisions allow ads
 - The number of request received by a specific ad server
 - The number of true requests received by a specific ad server (i.e. for which the ad server had a genuine chance of serving an ad – e.g. discount cases where a higher priority ad server called in parallel would have overruled them)
 - Etc.

All these definitions are valid in some context and for some specific goals, but the fill rate numbers were vastly different depending on the definition you pick. When you provide a number, as much as possible you should try to clarify its definition and how to interpret it to leave no room for misunderstanding.

The same goes for bias samples, in general it’s very rare to have a true uniform/unbiased dataset so you should be careful on the conclusion you will draw. The most common mistake is the survivorship bias where you focus your attention on data points that passed a selection process while overlooking those that did not. This is true for your job in a tech companies but also in real life – e.g. if you judge employees who left FAANG for small companies, it’s more likely that you end up with a set of engineers performing less well than the one who get promoted, are provided with a high compensation and are given new/interesting responsibilities. I’m not arguing here whether the conclusion is true or not (though I have interesting thoughts about it that I’ll keep for another post), but at least you should be conscious about the bias in the data points being used.

Last but not least, metrics are something you can polish over time – it’s OK to start with a roughly OK metric as long as you are aware of its caveats and make sure people relying on your results know about them. You can polish your metric over time by fixing its scope, accounting for bias etc.

Numbers need meaning/interpretation/context, the same way a graph needs a legend.

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-metric-number-activity-7204859781579227139-KZAE?utm_source=share&utm_medium=member_desktop)
