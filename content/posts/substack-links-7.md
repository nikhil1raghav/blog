+++
title="Links #7"
date="2026-09-05"
description="How Cloudflare freed 100TB of RAM, human brain-like readings on Claude, why everyone should know SIMD and few finance books"
tags=["substack"]
+++

> Originally published on [Substack](https://purpleterminal.substack.com/p/links-7).

Hi, welcome to 7th edition of my infrequent newsletter, which will be more frequent, as I’ve become a “big” influencer with 9k followers ;) and I’ve AI to get some research and organisation out of my plate.

If you’re just browsing through substack and somehow opened this link then quick introduction - I share links to the blogs, tools I find interesting (mostly tech) and some book recommendations in my series titled “Links”

![](https://substack-post-media.s3.amazonaws.com/public/images/1095549b-319d-4c93-be9f-78aebbc1c955_1164x1034.png)

### [How we saved 100 terabytes of memory by optimizing 1.1.1.1’s DNS cache](https://blog.cloudflare.com/dns-cache-memory-optimization-1111/)

Cloudflare maintains a large cache of DNS entries. Saving even 1 byte per entry saves 250GB. In this blog they talk about how they saved 100TB (that’s like 400 bytes per entry).

Five changes to how DNS cache entries are stored cut per-entry memory by over 50%, freeing ~100 terabytes of RAM. The cache got faster too - insert throughput up 43%, lookup latency down 19%.

Interesting read.

### [Human brain-like readings on Claude](https://www.anthropic.com/research/global-workspace)

Like how folks on DiscoveryTV described what part of human brain is activated when they think or when they’re scared.

Anthropic developed a way to look at thinking patterns in claude.

They call it the J-space. When a pattern lights up, the model isn’t saying that word - just thinking about it.

The part that got me: they use it to catch Claude privately noticing it’s being tested, or fabricating data.

### [Everyone Should Know SIMD](https://mitchellh.com/writing/everyone-should-know-simd)

Mitchell Hashimoto is an engineer’s engineer.
He explains why SIMD shouldn’t be scary and always involves a fixed pattern of operations.

Process N values at a time, broadcast constants, loop one vector at a time. Examples in Zig, but the ideas apply anywhere.

### [5 things I learned while developing a billing system](https://arnon.dk/5-things-i-learned-developing-billing-system/)

How much depth could there be in billing? A customer joins, pays monthly, done... right? Right. Turns out there are tons of edge cases. Money isn’t always decimal (the Iraqi Dinar has three subdivisions, Japan has none), you can’t void invoices in most of Europe - the legal fix is a credit note, a reverse invoice with its own number - and every new region brings its own compliance rules. Good primer if you’re anywhere near a billing system.

### [turbopuffer: fast search on object storage](https://turbopuffer.com/blog/turbopuffer)

I found turbopuffer in 2023, now it is fast semantic search DB used in most of the AI tools like cursor.

This is the origin blog post about turbopuffer’s design.

### [Just enough CORS to not get stuck](https://blog.meain.io/2024/just-enough-cors/)

CORS is one of those topics surrounded by confusing explanations, and this is the clearest take I’ve come across. It starts from why the browser blocks cross-origin requests at all - told through a story about a scam email draining your bank account (CSRF) - then covers just enough of the spec to debug CORS errors instead of googling “how to disable CORS in chrome”.

# Books

I loved reading these two books over the past month

1.  **[Alchemy of Air](https://www.goodreads.com/en/book/show/3269091-the-alchemy-of-air) -** World needs a lot of food per acre of land than it can be grown naturally, at one time everyone was worried of a food crisis until humans could make a large amount of ammonia for fertilizers from air.

    Really good non-fiction book and brushes up on events of world war 1 and 2 from the lens of contemporary chemistry at that time.

2.  **[World for Sale](https://www.goodreads.com/book/show/52199304-the-world-for-sale) -** Insider report on world of commodity traders. Who sell earth’s resources and could bring entire countries out of debt. It was interesting to read alongside recent Iran US conflict adding volatility to oil futures.

3.  **[Dark pools](https://www.goodreads.com/book/show/12917124-dark-pools)** - I picked this book to read more about history of high frequency trading after Flash boys. It was more than just history of HFT, covered evolution of stock exchanges from human market makers who manually matched orders and pocketed the spread to rise of matching engines, island exchanges. Good read to understand different components and plumbing in market.

That’s all for this edition. Thanks for reading.

### Links in this issue

- [How we saved 100 terabytes of memory by optimizing 1.1.1.1’s DNS cache](https://blog.cloudflare.com/dns-cache-memory-optimization-1111/)

- [Human brain-like readings on Claude](https://www.anthropic.com/research/global-workspace)

- [Everyone Should Know SIMD](https://mitchellh.com/writing/everyone-should-know-simd)

- [5 things I learned while developing a billing system](https://arnon.dk/5-things-i-learned-developing-billing-system/)

- [turbopuffer: fast search on object storage](https://turbopuffer.com/blog/turbopuffer)

- [Just enough CORS to not get stuck](https://blog.meain.io/2024/just-enough-cors/)
