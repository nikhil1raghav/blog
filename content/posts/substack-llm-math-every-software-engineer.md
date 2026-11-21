+++
title="LLM math every software engineer must know"
date="2026-03-29"
description=""
math="true"
tags=["substack"]
+++

> Originally published on [Substack](https://purpleterminal.substack.com/p/llm-math-every-software-engineer).

Most engineers interact with LLMs daily, yet many struggle to estimate the basic resource profile of the models they use. Here are four mental models to help you put model size, intelligence, memory footprint, and training costs into perspective.

Without being too sciency.

### I. Model size: Parameters != IQ

Models are categorized by their parameter count: 8B, 70B, 405B. A "parameter" is essentially a single learned weight or bias in a neural network.

Parameters tell you the quality tier. 7B is small, can run on your laptop. 70B needs serious hardware.

***A 70B model is not 10x smarter than 7B. It’s more like a step function with diminishing returns.***

![](https://substack-post-media.s3.amazonaws.com/public/images/c4f622bc-7bf1-4bc0-a529-7c63c165f919_1336x776.png)

### II. Memory usage

Memory equals roughly 2x the parameter count. To hold an 8B model at 16-bit precision (FP16), you need roughly 16 GB of VRAM. If you're short on RAM, you have two main levers:

There are two popular ways to run bigger models on smaller RAM than required

**Quantization**: you resolve paramters to 8bit or 4bits from 16bit. Reducing memory by 7GB, 3.5GB respectively. You lose a sliver of accuracy, but the model is runnable on consumer devices

**SSD offloading**: Use SSD as high speed swap and only load required weights in RAM. Read this paper “[LLM in a flash](https://arxiv.org/pdf/2312.11514)“ for more details.

Using the same approach, someone recently [ran a 400B](https://x.com/danveloper/status/2034353876753592372) model on a 48GB macbook at 6 tokens per second.

### III. Training data

To avoid under-training, the **Chinchilla Scaling Law** suggests we need roughly 20 tokens of data per parameter. For a 70B model, that’s 1.4 Trillion tokens..

In practice, smaller models are trained on far more tokens than 20x. ***Trend is to overtrain smaller models.***

Llama 3.1 8B was trained on 15T tokens - roughly 2000x its parameter count.

![](https://substack-post-media.s3.amazonaws.com/public/images/5a711527-cfc7-43e8-94f4-547d06e5922f_1284x574.png)

### IV. Training compute

You might’ve heard xAI’s **Colossus** cluster in Memphis pulls **150MW** of power. But how do you translate “Megawatts” into “Time to train a model”?

**1. The Hardware Unit (H100)**

An H100 GPU pulls a peak of **700W** and delivers roughly **400 TFLOPS** (Teraflops) of sustained performance. If you factor in the cooling and networking (the “PUE”), each GPU “node” effectively pulls about **1500W**.

**2. The Training Formula**

To calculate the total Floating Point Operations (FLOPs) required to train a model, use the formula:

$$C = 6 \times N \times D$$

- **N:** Number of parameters.

- **D:** Number of training tokens.

If we follow the **Chinchilla Law** (where D = 20N), the formula simplifies to:

$$C = 120 \times N^2$$

![](https://substack-post-media.s3.amazonaws.com/public/images/de2a897e-0d76-4731-8060-020c785dbee3_1024x559.png)

Divide compute requirement by throughput and we get around 35 days.

Similarly, a 1GW cluster - can train a frontier model every week.

For further reading.

- [What did it take to train Grok 4?](https://epoch.ai/data-insights/grok-4-training-resources)

- [Understanding LLM Inference Engines: Inside Nano-vLLM (Part 1)](https://neutree.ai/blog/nano-vllm-part-1)

------------------------------------------------------------------------

**Hope this gave you some food for thought and clarity around the LLM landscape.** These numbers are moving targets, but the underlying principles, more or less stay the same.

Thanks for reading.
