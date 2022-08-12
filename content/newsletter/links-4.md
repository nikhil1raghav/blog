+++
title="Links #4"
author="Nikhil"
description="What does it mean to listen on a port, a long-form article on money, a deep dive into Kubernetes internals, an improvement on navigating directories in terminal and more"
+++
Hi!, welcome to 4th issue of my highly irregular newsletter. One of the reasons for this irregularity is that it is hard to find quality links to share and I make it a point to go through them myself before I share. Sometimes I just don’t feel like writing so I don’t.

Here are some links worth your time. Experimenting with a new format where I sprinkle supporting links here and there which are related to the heading and could make their own entry.

**[What does it mean to listen on a port?](https://paulbutler.org/2022/what-does-it-mean-to-listen-on-a-port/)** is a piece of discovery fiction in which two students write code to validate their understanding of how a server listens to connections on a port and come to conclusions on questions like — Can there be multiple connections on same port? How an operating system must be managing these connections under the hood?

It is interesting to read how they settle on one explanation and then write code to counter that and then evolve their understanding to accommodate the findings.

**[What is Money, Anyway?](https://www.lynalden.com/what-is-money/)** is a well-researched, long form piece on how the entity that we know as money has changed over time and can change in future. It is thorough, unbiased and will take you at least 1 hour to read but it is well worth it. It covers things like gold standard, repercussions of petrodollar system, why there are not many serious contenders to gold that can be used as money and an impartial take on cryptocurrency in the end.

**[Gophercises](https://courses.calhoun.io/courses/cor_gophercises)** is a set of exercises to pickup golang faster. You should know basic control flow and syntax before getting started. Every exercise starts with the description of the task which is the spec of the program you’re going to create. Then you can proceed on your own and lookup the solution if you like or complete the task and then improve your solution by looking at the one by author.

If you’re interested in golang, I also found this [blog](https://www.alexedwards.net/blog) which has some gem articles on middlewares and interfaces with a very coherent writing style.

**[Kubernetes Deconstructed](https://vimeo.com/245778144/4d1d597c5e)** is an unabridged version of [this](https://www.youtube.com/watch?v=90kZRyPcRZw) talk which has too many views for its content (because it is only 30 minutes longer). I didn’t find the 30 minute version that helpful because it is too rushed to convey the message, but this unabridged version is very helpful in understanding moving parts of kubernetes. Host walks you through the different lenses to look at Kubernetes - how a user sees it, what are the components that are at work to make communication in k8s possible, how the declarative management really works. Cool talk with a cooler presentation.

If you are new to containers and want to learn more, I recommend going through [learndocker.online](https://learndocker.online/).

### Tools

#### **[Autojump](https://github.com/wting/autojump)**

Do you spend most of the time in terminal jumping through directories and hate typing long paths and pressing tab atleast 3 to 4 times? You should try [Autojump](https://github.com/wting/autojump).

It is a utility that records the directories you usually cd into and then assigns them a weight based on the frequency of visiting.  

Then you can type some part of the path and then autojump will cd into the most frequent directory which has that string in its complete path name. For example typing `j movies to jump to the movies directory that you visit often.`

Before autojump, I used to make hashes in .zshrc but that is not a scalable solution.

#### **[Cht.sh](https://cht.sh/)**

[cht.sh](https://cht.sh/) provides easy to read community-driven documentation for command line tools that you can refer in terminal. Like if you quickly want to know how to use ffmpeg to trim a file, a quick `curl cht.sh/ffmpeg` will spit out the most common uses and operations for ffmpeg with examples which is faster than a google search or eyeballing the manual.

Creator is the same person who created [wttr.in](https://wttr.in/), a quick way to look up weather forecasts in terminal just curl wttr.in/<name of the place>.  

That is all for this issue, feel free to mail me or comment for any suggestions/feedback.

Thanks for reading :)
