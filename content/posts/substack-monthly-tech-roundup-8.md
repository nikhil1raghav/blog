+++
title="Monthly tech roundup #8"
date="2026-11-19"
description="On Black October, smaller engineering teams, the skills I've been using, and what happens when intelligence gets cheap."
tags=["substack"]
+++

> Originally published on [Substack](https://purpleterminal.substack.com/p/monthly-tech-roundup-8).

All the good stuff I read and learned last month, plus a few things from November.

Every major AI launch already makes it to human consciousness through 24x7 influencers rambling about it. We’ve become numb to it.

## Models editing models

Craziest thing I came across was [GPT-6 Astra editing Qwen3.5-0.8B’s weights](https://rikiyat.github.io/blog/weight-space-programming/). It changed just 0.016% of them and raised its MATH-500 score from 7.9% to 48.1%, without a training loop.

Reminded me of how Neo can edit his environment in the Matrix.

![](https://substack-post-media.s3.amazonaws.com/public/images/4b4e4c5f-cfa1-48f2-8c0d-adf6f88b2e18_2816x1186.png)

Don’t read too much into the multiplier. Qwen had a known reasoning-loop problem. Astra could diagnose it and patch the weights directly.

## Black October

October was called Black october due to sheer number of vulnerbilities reported.

My favorites were [PHP2Shell](https://www.akamai.com/blog/security-research/understanding-php2shell-everything-you-need-to-know) and [SSHhole](https://sshhole.com/).

PHP2Shell includes a use-after-free in PHP’s upload-progress feature. A file upload can lead to RCE on vulnerable setups, even if your application ignores it. PHP processes uploads before your code runs.

SSHhole lets passwords of 257 to 1,024 bytes bypass authentication on vulnerable OpenSSH/musl setups, mostly Alpine.

This trend is not stopping though. As of writing, following RCEs were disclosed in last two days : [Java4Shell](https://calif.io/java4shell) and [two NGINX HTTP/2 RCEs](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) . Phew. Hard time for sysadmins and small business owners.

## Software engineering and job security

[Canva’s layoffs and restructuring](https://www.canva.com/newsroom/news/canva-team-update/) and [Microsoft’s voluntary exit offer](https://blogs.microsoft.com/blog/2026/10/26/introducing-a-voluntary-exit-offer/) made me a bit anxious about the job market.

That’ll be a different post.

1.  Teams will get smaller.

2.  The role will become more like a line engineer. It has already changed a lot in one year.

3.  More ventures will come up. You’ll have to be an entrepreneur or work closely with one to keep the same quality of life.

I liked [How software engineering is changing](https://newsletter.pragmaticengineer.com/p/how-software-engineering-is-changing). Agree with most of it. Neil Kakkar compares his work at PostHog and Tano, an AI-native startup.

- Architecture decisions become easier to reverse when migrations take weeks instead of a year. Different migrations, different companies, though. Tano also had bugs that paid creators twice.

- You need to turn off work in the evening now more than ever. Always something else an agent could build. Neil leaves his laptop at work, agents running, and goes home.

We’re not learning as much. A lot of thrashing when you’re expected to deliver 3x the output.

I now space my work throughout the day because there are time gaps when you’ve a clanker running on something which needs to be reviewed after 10 minutes. What you do in those 10 minutes? I read on the side. Learning new things.

## Skills I’ve been using

### [Humanizer](https://github.com/blader/humanizer/blob/main/SKILL.md)

For editing drafts. Humanize copywriting passes on websites and sometimes just to make an agent talk to you like a human. It is getting harder to understand what agents say, I’m getting dumber they’re getting cryptic.

### [Ponytail](https://github.com/DietrichGebert/ponytail/blob/main/skills/ponytail/SKILL.md)

This is a pretty old, popular skill. I was working on three side projects and also use it at work to get a better first draft for review.

Smallest change that fully solves the problem. Reuse what’s there, skip abstractions nobody asked for.

### [Socratic tutor](https://github.com/janestreet/agent_skills/blob/master/socratic-tutor/SKILL.md)

Recently released by Jane Street.

It breaks a topic into areas, rates your understanding 0 to 5, then quizzes you one question at a time. Default target is 4; 5 means you can teach it. It is brutal.

But learning is fun with it, finally started thinking again due to this.
Used it to understand some codebase at work and random music theory class.

## What do we do with abundant intelligence?

Most enlightening thing I read was Venkatesh Rao’s [Cognitive mercantilism](https://contraptions.venkateshrao.com/p/cognitive-mercantilism).

Wealth used to be treated as finite. Capitalism changed that: wealth could be created. Ordinary people could create demand for things nobody had imagined them buying.

We’ve organized knowledge work around intelligence being expensive and scarce. AI is changing that.

Most of us don’t need to farm for food anymore. We might not need to produce intelligence for a living to find uses for it either.

Cheaper intelligence could let people pursue projects that were out of reach. But that’s one side of the argument, what happens when you’re removed from the economy when you’ve nothing of value to offer.

[The economics of intelligence](https://institute.deepmind.com/essays/the-economics-of-intelligence/), from DeepMind Institute, tells why we’ve not seen much of displacement yet.

A model can beat people one-on-one and still lose to a team of complementary specialists working together. AI is bad at co-ordination for now. Today’s agent swarms still struggle to divide work without duplicating it.

I loved [this tweet by Robbie Petersen](https://x.com/robbiepetersen_/status/2114083326604742913) on which interfaces agents might replace. His test: cortisol or dopamine. Planning and scheduling could be delegated. Scrolling and discretionary shopping are for the experience.

## Energy, on Earth and in space

Karpathy created [HackerTube](https://hackertube.org/watch/KtQ9nt2ZeGM) for videos mentioned on Hacker News. It is a serene oasis of good videos that I’ve recently started watching while having dinner.

I watched [You are being misled about renewable energy technology](https://hackertube.org/watch/KtQ9nt2ZeGM).

Solar and batteries are already much cheaper than people assume. You build the equipment, use it for years, and can eventually recycle it. With oil, you keep extracting and burning more of it.

I also read [Will we really put data centers in space?](https://www.forethought.org/research/will-we-really-put-data-centers-in-space).

Launch costs, failed chips you can’t replace, and bandwidth are bigger complications.

Their forecast depends heavily on Starship making launches much cheaper. They don’t expect a meaningful share of compute in orbit before 2030.

Maybe once energy is solved, we all can live peacefully, without having to work.

## Tech blogs and tools

[Airbnb matched frontier quality at roughly 1% of the cost](https://airbnb.tech/ai-ml/frontier-quality-at-1-of-the-cost-a-production-benchmark-of-llm-classifiers/) with a fine-tuned small classifier for payment policy violations. It scores in about 35ms at the median.

Cons are it needs high traffic to keep the GPU busy.
At low volume, the frontier APIs were cheaper.

AWS released its [official emulator](https://github.com/aws/aws-emulator). I was using Floci till now. Point your SDK at it for local tests without an AWS account. Check service fidelity and known gaps. AWS says it isn’t for production or security testing.

[Go concurrency distilled](https://antonz.org/go-concurrency-distilled/) is a short refresher with examples you can edit and run in the browser. Channels, cancellation, races.

I’ve also been reading *Thinking in Systems* by Donella Meadows and parts of *Glimpses of World History*.

That’s it for this post. See you in the next one.
