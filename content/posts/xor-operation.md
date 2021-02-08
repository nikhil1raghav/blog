+++
title="Solving A XOR operation - Hackerearth"
author="Nikhil"
description="Intuition behind solution of the problem titled A XOR operation of Feb Easy '21 on hackerearth"
tags=["hackerearth","problem", "bits"]
date="2021-02-08"
+++

For context, [link](https://www.hackerearth.com/practice/basic-programming/bit-manipulation/basics-of-bit-manipulation/practice-problems/algorithm/strange-xor-2-fc8ad535/) to the problem being discussed.


#### Solution that passes
- Let's say $X = e_1\oplus e_2\oplus\cdots \oplus e_n$ i.e. XOR of all elements of $S$. If it satisfies the condition of being $k$ then it is the answer, otherwise no answer exists.

#### Why is it so?

- One thing is for sure that every element will be mapped to some other element in the set.
- If the answer is $k$ then $a_i$ will be mapped to $a_i\oplus k$. So what we can do is we can check to which element, first element of the set will be mapped, i.e. try every possible pair with first element and check if so formed $k$ is the answer. Mind that $k$ will always be positive as there is no repetition in a set.

- This approach can be slow because one pass for every pair and there are $N-1$ pairs, where $N$ is size of the set.

- Before optimizing this solution, I want to prove why any $k$ that keeps the set unchanged will be the answer.

- Let's say $a_1 \oplus a_2$ is $k$ thus $a_1$ is mapped to $a_2$. Now there are $N-2$ remaining elements, which can be divided into $(N-2)/2$ or we should say $N/2 - 1$pairs with XOR $k$. As given in the problem statement $N/2$ is odd then $N/2-1$ is even. We know that if same number is XORed even times it becomes $0$. So XOR of all elements is $k$. Thus whatever you do this will remain constant because set is unchanged and it guarantees that at most one valid mapping exists.

- Now you know why the solution stated above i.e. take XOR of all elements if it satisfies the condition then it is the answer. It is minimum because it is the only answer.





#### Corner case
- There can be created many corner cases such that $X$ is zero for the set. No such case is included on the judge. Even authors solution fails this, but it is trivial (no nitpicking), but testers solution doesn't fail this test :).
For example:

```text
1
6
17 3 2 4 12 24
```








