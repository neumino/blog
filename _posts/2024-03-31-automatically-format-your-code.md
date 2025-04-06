---
layout: post
category : Growing-as-an-engineer
tags : [softwareengineering, format, consistency]
title: Automatically format your code
---
{% include JB/setup %}

I strongly believe you should invest into automatically formatting your code, because beyond esthetic reasons, having code automatically formatted allows:
 - To reduce the cognitive overhead for engineers – you can just write code that compiles and it will be automatically styled, e.g. you don’t have to worry about whitespace issues. Code is easier to read too, it’s more consistent.
 - To ease large scale refactoring – you can manipulate a large code base without having to build a complete parser since you can rely on formatting rules. E.g. this just happened for me where I wanted to manipulate bazel files at scale and rather than parsing starlark, I could just sequence a few dumb regexes and rely on the fact that kwargs were ordered.

On style itself, I personally don’t have a lot of opinions beside that:
 - The code should be readable
 - The code should be automatically formatted – I don’t want to run into failing tests because of style or have to manually run commands, just make this part of a pre-commit git hook.
 - There’s as much as possible a single valid format for a given file
This is one thing Google got right with Go in my opinion

[LinkedIn post](https://www.linkedin.com/posts/tumichel_softwareengineering-style-format-activity-7312488911371485184-FmNT)
