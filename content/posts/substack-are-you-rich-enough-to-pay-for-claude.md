+++
title="Are you rich enough to pay for Claude?"
date="2026-09-12"
description="my DIY AI setup as an engineer & creator"
tags=["substack"]
+++

> Originally published on [Substack](https://purpleterminal.substack.com/p/are-you-rich-enough-to-pay-for-claude).

I have a fairly good compensation as a big tech engineer. Yet, I don’t like paying $20 or more for Claude.

![](https://substack-post-media.s3.amazonaws.com/public/images/14f44a24-2125-4ae7-8f0f-f0b6cb34862e_2608x1632.png)

You don’t get much of Claude for 20$, for 100$ it is like leaving too much
money on the table.

A normal knowledge worker × content creator subscribes to multiple tools:

1.  an AI daily driver like Claude,

2.  Wispr Flow because you can speak 4x faster than you write (but I can’t think 4x faster, so I speak gibberish),

3.  Notion,

4.  Canva,

5.  and a read-it-later app like Readwise. It adds up.

AI tools are the major cost sink. I don’t like paying subscription fee for them, for two reasons:

1.  **I don’t like a flat fee for something that is metered.** AI is billed by usage, like electricity. On a flat fee, ***I know I’m leaving money on the table**.*

2.  **I don’t like walled gardens.** You pay for electricity and can use it to drive any device of your choice. [AI the new electricity](https://www.gsb.stanford.edu/insights/andrew-ng-why-ai-new-electricity), and I want to buy it that way: pay for tokens at one place and let them power my Hermes agents, my favorite editor, my dictation tool, my coding agent and random scripts.

## My AI setup

You need three things for a DIY setup

1.  AI credits : There are websites that give you an API key that you can put $$ into. There are trusted ones like [Openrouter](https://openrouter.ai/), [DeepInfra](https://deepinfra.com/) and then there is whole [Chinese black market](https://www.youtube.com/watch?v=09UELaUhPEw) for tokens.

    Just make sure whatever model you’re using, is not logging your prompts.

    You can look at the ZDR (zero data retention) icon in front of models.

2.  Harness : Harness is what makes use of this API key to perform actions. It can also be called an agent. Claude code is a harness, Codex is a harness too.
    [Hermes](https://hermes-agent.nousresearch.com/) and [pi](https://pi.dev) are very good open harness.

    Each harness is optimised for a goal. For example [Hermes](https://hermes-agent.nousresearch.com/) is optimised to be a personal assistant that grows with you. While pi, claude code and codex are primarily designed to code and use terminal.

3.  MCPs, skills and web browsing : Once you’ve a Harness with an API key, you can add MCPs and skills to extend your agent.

    Hermes comes with a good set of default skills. Pi is empty.
    For web browsing use [Kimi Web bridge](https://www.kimi.ai/products/kimi-webbridge), best browsing extension out there.

Every two months or so, I put $20 into [OpenRouter](https://openrouter.ai/). In the past six months I’ve used about $50 in total, and that will keep stretching further as new Chinese models drop, inference architectures improve, and more inference providers compete on price.

![](https://substack-post-media.s3.amazonaws.com/public/images/7f95e367-edfd-4659-ac2d-d8005fa06445_1668x608.png)

Then I use that one key in:

- [Pi](https://pi.dev/): my coding agent of choice

- [Hermes](https://hermes-agent.nousresearch.com/): one agent for productivity and life, one for managing finance

- [OpenWhispr](https://openwhispr.com/): it’s like Wispr Flow, but you can bring your own API key

*(Read on to how I use Hermes and Pi)*

## Your coding agent can do anything Claude can

Claude, the UI app most subscribers use, is a coding agent underneath.
A coding agent can do anything on a computer, anything.

Every skill, plugin and MCP server works as well with Pi, OpenCode or Codex as it does with Claude.

For me, most of the time, I need it to:

- move files from one place to another

- browse the internet, fill forms, apply for duplicate licence

- analyse social media, write scripts

- create and update my resume, notes, presentations and content

- coding, finetuning, some experiments…

Any coding agent can do all of this. For the browsing part, add this extension called [Kimi WebBridge](https://www.kimi.ai/products/kimi-webbridge).

It’s like Claude in Chrome, but you can use it freely with any agent of your choice.

## Always-on Hermes agents

Pi does everything I do on a laptop. But when I’m outside and only on my phone, I have two [Hermes](https://hermes-agent.nousresearch.com/) agents hosted on a VM (courtesy of [my brother](https://www.linkedin.com/in/akhilraghav/)).

You can [setup](https://hermes-agent.nousresearch.com/docs/getting-started/installation/) Hermes on an old laptop. You need approx 1 GB of RAM for one agent.

![](https://substack-post-media.s3.amazonaws.com/public/images/349b7a3d-fc6b-45c4-a5cf-2600fe50f9e9_694x274.png)

### Finance agent

The finance agent is connected to my brokerage accounts via MCP.

It also listens to all the important podcasts and shares highlights first thing in the morning.

I use it for backtesting strategies and for researching and sizing investments.

### Productivity agent

The productivity agent is connected to my [Todoist](https://todoist.com/), [Notion](https://www.notion.com/) and Google Health. I start my day by dumping my morning pages into it. It then shows me everything that needs attention, and we do an Eisenhower prioritisation together.

Then I know what I have to work on today.

I tell it my progress through tasks, and it strikes them off.

I put in a few messages here and there through the day: reminders, new books to read, and other targets of mine.

![](https://substack-post-media.s3.amazonaws.com/public/images/014b2938-d420-48b8-b9f6-135caab40cdc_904x1102.png)

It’s life-changing.

It keeps me accountable. I share my digital wellbeing screenshot daily, along with my goals like going to the gym 4x a week and sleeping 8 hours daily.

It tracks all of that, and honestly, just the thought of sharing my screentime screenshots with someone pushes me to not scroll mindlessly.

## You only need to pay more if

So it’s not that I’m never going to buy these subscriptions.

They give you a lot more value than what you pay for.
I just know that I won’t be able to extract that value, so I don’t pay.

But if I have to work on some serious coding project where pay-per-token doesn’t make sense, I’ll buy a subscription plan.

I’d prefer [Codex](https://openai.com/codex/), because they’re more open than Claude and let you use the subscription anywhere.

Hope this helps. Thanks for reading.
