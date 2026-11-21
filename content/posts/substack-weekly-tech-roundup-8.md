+++
title="Weekly tech roundup #8"
date="2026-10-11"
description="The state of tech industry, codemode in pi, github’s rearch and history of bloomberg terminal."
tags=["substack"]
+++

> Originally published on [Substack](https://purpleterminal.substack.com/p/weekly-tech-roundup-8).

Thanks to everyone who subscribed to my newsletter recently.

I was in Japan for last two weeks. So couldn’t post anything.

![](https://substack-post-media.s3.amazonaws.com/public/images/4b269698-e3a1-4a4a-b86c-d3ee5a5c922b_4585x3336.jpeg)

There is a lot that has happened since. We’ve sonnet 5.5, gpt 6.1 release. OpenAI didn’t release a terra model this time. Dots was launched, background agents by OpenAI.

Jev came out and quickly open source counterparts popped up. Then OpenAI released their decisions API, but honestly releasing a Jev like model hurts bottom line for OpenAI, anthropic.

Haiku 5.5 released and Anthropic has a better smaller model for the first time that goes head to head with Luna.

Pi released their 1.0 with codemode being the highlight.

I’ve also renamed this links series to tech roundup. Sounds weird but less drier than just “links”

Here are some good talks, blogs and recommendations that I enjoyed.

1.  [The state of the tech industry](https://www.youtube.com/watch?v=Ru99FGJ_yuE) - If you watch one thing out of this newsletter, watch this video. Gergely speaks out loud what everyone in the tech industry is feeling recently. IDEs are dead. No one reviews the PRs anymore.

    Too much context switching and multi-tasking. Companies are hiring for AI fluency and “AI positivity.” Hiring has reduced. Teams are getting smaller. Engineers with deep domain knowledge are more important than before. Investing in your team’s and then your company’s AI maturity is a high leverage activity.

    One thing I feel he missed out on is no one is learning anything anymore, and current increase in output is partly due to overwork and managing expectations.

    [Watch on YouTube](https://www.youtube.com/watch?v=Ru99FGJ_yuE)

2.  [What is codemode](https://lucumr.pocoo.org/2026/10/6/codemode/) - [Pi](https://pi.dev) released their 1.0 version and it supports mcp with codemode. Code mode is a very simple idea, instead of shoving all mcps into context, let the harness discover mcp and use them via a gateway and optionally compose their outputs. Uber [uses it internally](https://x.com/i/article/2106059544376066048), even cloudflare [does](https://blog.cloudflare.com/code-mode/) it too.

    Most of the implementations are keeping MCPs behind one gateway if you own them like Uber, and give an isolated sandbox to run all the code (what pi does).

    This saves on tokens and agent can filter the output to get what it needs natively.

3.  [Github: building git infrastructure for agent scale development](https://github.blog/engineering/architecture-optimization/building-git-infrastructure-for-agent-scale-development/) - Github faced major outages recent times due to traffic surge and capacity failures. Driven by massive number of Agents pushing commits to github.

    PR merges have grown 4x, pushes grew 5x.

    Github is implementing compute storage separation. Repo data lives in blob storage while stateless compute workers perform operations on it.

    Narrowing the critical path by offloading operations other than branch tip update to async workers. Scaling reads by adding stateless compute that builds its cache on-demand.

4.  [Sebastian Rarschka: From bag of words to Jev](https://magazine.sebastianraschka.com/p/classifier-history-and-jev) - Sebastian Rarshcka is my go to author for anything LLM. He explains the jev hype the right way. Naive Bayes with bag-of-words was sorting text in 1961, and we’ve been classifying with logistic regression, RNNs, CNNs and BERT ever since.

    He considers Jev “ChatGPT moment for classification”. He built his own version of Jev on ModernBert. Bar for justifying fine-tuned specialist model just got higher.

5.  [A brief history of the bloomberg terminal](https://spectrum.ieee.org/bloomberg-terminal) - Everybody who is anybody in finance uses the bloomberg terminal. This piece goes in detail on its history, everyone knows that Bloomberg made it with 10 Mn dollars he got as severance payout but this goes into more details.

    I was surprised to know that at one point pigeons used to carry stock prices between Aschen and Brussels and the first keyboard was hand assembled.

    That’s it for this post. Thanks for reading.
