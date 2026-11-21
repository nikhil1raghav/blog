+++
title="Links #5"
date="2022-06-12"
description="Deep dive into evolution of std:sort, practical summary of Getting things done, Knuth on work-habits & problem solving and, an add-on that translates a webpage without talking to server"
tags=["substack"]
+++

> Originally published on [Substack](https://purpleterminal.substack.com/p/links-5).

#### [Changing std:sort at Google’s scale](https://danlark.org/2022/04/20/changing-stdsort-at-googles-scale-and-beyond/)

How many reasonably fast sorting algorithms do you know about? If you use any modern language, there is a high chance that it has its own implementation of **sort** which houses multiple algorithms and uses their combination to achieve consistent performance irrespective of the input.

[This](https://danlark.org/2022/04/20/changing-stdsort-at-googles-scale-and-beyond/) post is about the internals of sort in both LLVM and GNU. How the author improved LLVM’s std:sort, what kind of problem-solving and experimentation goes into such initiatives, and very satisfying animation that pitches different combinations of sorting algorithms against each other.

If you don’t even read it, try taking a look at the visualizations, it will be a net positive gain and might nudge you eventually into reading it.

#### **[Getting things done summary](https://hamberg.no/gtd/)**

I’ve spent some time now searching for a bare minimum, low-maintenance system that allows me to work on ideas/tasks that matter, without losing many of them.

I’m using a bare-bones GTD method for two weeks now, this **[Getting things done summary](https://hamberg.no/gtd/)** is what got me started**,** and saved the hassle of reading a 5-hour-long book.

Productivity is a scam but one must have a system for not losing track of important tasks and ideas.

#### [Project Bergamot - Offline machine translations](https://browser.mt/)

Client-side machine learning is not a new thing but the number of projects doing it for something useful is quite rare.

Perhaps you even know a website that can’t crop/resize a photo without talking to a server. There are even [browsers](https://polypane.app/) that run entirely inside a data center.

On the other side of the spectrum, projects like [this](https://trekhleb.dev/blog/2021/content-aware-image-resizing-in-javascript/) can do content-aware resizing in the browser without sucking the soul out of your CPU.

With [WASM](https://webassembly.org/) there has been a boost in web applications that offload computing to the client-side, which is a win-win situation for both parties unless the server is data-hungry or the client has a resource crunch.

Project bergamot is an initiative to help browsers to translate web pages offline. A tangible fruit of their hard work is this [add-on](https://addons.mozilla.org/en-US/firefox/addon/firefox-translations/) that supports 12 languages. It downloads a model before it can translate a language but after that works in flight mode.

#### [Donald Knuth on work habits & problem-solving](https://shuvomoy.github.io/blogs/posts/Knuth-on-work-habits-and-problem-solving-and-happiness/)

It is a compilation of Knuth’s philosophy on happiness, work habits, and how he approaches problems, collected from multiple interviews. Short and organized nicely.

### Books

![](https://bucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com/public/images/45de3b6b-c0dd-4302-bdb0-f750a7838c40_265x400.jpeg)

Last month I read [The Missing Readme](https://themissingreadme.com/) which is a great book to read if you are a new software engineer.

Discusses things that you probably don’t have any idea about if you’re a new grad like clean code, testing, how to write a design doc, PR reviews, effective 1:1 with the manager, not to fret if onboarding takes time, impostor syndrome and friends, jargon like OKR, KPI, NFR things to remember when you’re on-call and more.

Great book if you’re starting out.

On the same note, there is also a course by MIT called [Missing Semester](https://missing.csail.mit.edu/) which covers things that are usually not prioritized in the CS curriculum but are equally useful like shell scripting, effective use of version control, text-editing, navigating command line, and debugging.

That’s all for this edition. Thanks for reading.

#### Links in this issue

1.  [Changing std:sort at Google’s scale and beyond](https://danlark.org/2022/04/20/changing-stdsort-at-googles-scale-and-beyond/)

2.  [GTD in 15 minutes](https://hamberg.no/gtd/)

3.  [Donald Knuth on work habits, problem-solving, and happiness](https://shuvomoy.github.io/blogs/posts/Knuth-on-work-habits-and-problem-solving-and-happiness/)

4.  [Project Bergamot](https://browser.mt/)

5.  [Content-aware resizing in browser](https://trekhleb.dev/blog/2021/content-aware-image-resizing-in-javascript/)

6.  [The Missing Readme](https://themissingreadme.com/)

7.  [Missing Semester](https://missing.csail.mit.edu/)
