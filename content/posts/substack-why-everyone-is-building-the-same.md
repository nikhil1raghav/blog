+++
title="Why everyone is building the same projects"
date="2026-08-06"
description="and how to fix projects for your resume"
tags=["substack"]
+++

> Originally published on [Substack](https://purpleterminal.substack.com/p/why-everyone-is-building-the-same).

I recently shared a post on LinkedIn about Uber hiring and offered to refer people.

![](https://substack-post-media.s3.amazonaws.com/public/images/8c16b245-8b79-4d77-9698-3bc1fc377bac_1268x1030.png)

At first, I opened the first few resumes. Then I downloaded all of them and created a quick filter with Claude based on three things:

1.  LeetCode / CP ratings — signals that you can clear DSA interviews. But it doesn’t look good on its own. Expert+, Knight, or 5* looks good. Don’t add how many problems you solved; no one cares.

2.  Hackathon and open source experience

3.  Projects

Surprisingly, projects were the tie-breaker.

There were only 5–6 profiles with really good projects.

I also think hackathon experience and good project taste come as a bundle.

Students who win at hackathons usually have good taste in projects.

Standout profiles had really good projects. Most other resumes had projects that didn’t even have a proper name: “Rate limiter”, “Polling app”, “Redis leaderboard”. Some had “clone” in their names, like Netflix clone and Instagram clone.

These are good for learning, but when you don’t have work experience, your projects are the closest thing to it. **Treat your projects like jobs**.

**They should signal technical competence and creativity.**

HackerRank open-sourced their [hiring agent](https://github.com/interviewstreet/hiring-agent/blob/main/roles/software_engineering_intern/criteria.jinja), which they used to filter internship resumes.

Projects were one of the strongest signals it looked for, especially real-world impact and technical complexity.

This is a snapshot of their scoring criteria:

![](https://substack-post-media.s3.amazonaws.com/public/images/7f81773d-10de-4f71-9de7-4187508ba0cf_1268x482.png)

You can read the [full criteria here](https://github.com/interviewstreet/hiring-agent/blob/main/roles/software_engineering_intern/criteria.jinja). It also has good guidelines on resume accessibility and open source contributions.

But this got me thinking: what would I tell someone about choosing projects for their resume?

So there are three options.

#### Option 1: Build something that is useful for you

I built [kindle-send](https://github.com/nikhil1raghav/kindle-send) in 2021 to send blogs and ebooks to my Kindle. It downloads a page, extracts the readable content, and sends it to an email address.

It is very simple by today’s standards, but it has 272 stars and 30 forks. It has predictable commands, can be used in scripts, and got good traction when I posted it on HN. At the time, there was no other open CLI tool doing this and I had to build one for myself.

> One more tip: know what is overdone. For example, instead of building another RAG chatbot, you could build something fun like an AI book club, where users create multiple AI friends with different personas and discuss a book together. It’s more fun and different.

#### Option 2: Copy what’s new

Go to Product Hunt or Show HN and try to clone something that you like and are comfortable building.

Now you might say, “What? I have to build a profitable SaaS just to get a referral?”

It’s actually simpler than that.

With AI, you can get 80% of the features done in a day. You don’t need to build the last 20% that the founders of the app have to build.

Build just 5% of it and you’ll have enough things to talk about.

For example, suppose you find an AI meeting-notes app on Product Hunt. The first 80% is fairly straightforward: upload a recording, transcribe it, generate a summary, and extract action items.

Your additional 5% could be a focused version for student project teams that turns those action items into GitHub issues and sends reminders before the next meeting.

It doesn’t need to be a profitable SaaS. It needs to be a thoughtful project that you can explain.

#### Option 3: Build stuff from scratch.

Building things from scratch always works, both for learning and for the signal it gives.

One repository I recommend is [Build Your Own X](https://github.com/codecrafters-io/build-your-own-x) by CodeCrafters. It is a collection of resources for building things from scratch, including databases, operating systems, container runtimes, neural networks, and compilers.

Think about how cool you would sound talking about how you built a toy database or a container runtime from scratch.

At the end, put everything in a simple template. I like the [resume template from Gergely Orosz of The Pragmatic Engineer](https://blog.pragmaticengineer.com/the-pragmatic-engineers-resume-template/). It is a simple, single-column template.

You can find the [Google Docs version here](https://docs.google.com/document/d/1YpKsg9tIrk4sRzY5Us0rXrcs7cpFzDbP58b9MjsI0Gg/edit?tab=t.0).

Hope this helps. Thanks for reading.
