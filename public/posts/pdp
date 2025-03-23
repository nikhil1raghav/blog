+++
title="[Partition DP] Handling Partitions with Dynamic Programming"
Author="Nikhil"
math="true"
date="2021-07-18"
description="Two example problems involving partitions and how to solve them with dynamic programming"
tags=["dynamic-programming"]
+++

Purists may say there are no categories in dynamic programming, but giving names to some common states and transition patterns makes them easy and fast to recall and identify the problems in which to use them.


So one such pattern is Partition DP, I have seen it in two problems many can be created on the same theme obviously. Let's discuss them.


Main idea is to iterate over all masks, set bits in a mask represent what entities have been assigned a partition already and value of new transitions can be any of the subsets of the current mask. So we find all subsets of the complement and thus explore more states. 

If this doesn't make sense, it will after looking at two examples below.

---

# [Problem 1 - HIRINGWO](https://www.codechef.com/problems/HIRINGWO)

>  __Abridged Problem Statement__
>
> Find smallest sum of $K$ numbers such that their LCM is $X$.
>
> Here $2 \leq K,X \leq 10^6$ 
>

So, here we need to find smallest sum $K$ numbers with LCM $X$ can have. As we have to minimize the sum, then in optimal solution every two numbers will be co-prime, because keeping a prime factor in more than one number makes the answer worse. At this stage where all selected numbers are pairwise co-prime LCM is simply the product of those numbers.


Now it translates to finding largest power of the prime numbers in $X$ and distribute them in $K$ different buckets. We want largest power of prime to be in a single bucket because every prime will go in only one bucket and for a group of numbers to have LCM $L$, largest power of every prime must match to that of $L$.


Interesting fact is there are only $7$ prime numbers product of which overshoots $10^6$.


Let's say there are $P$ distinct primes in $X$ and $f[i]$ be largest power of $i_{th}$ prime which divides $X$.

$dp[i][mask]$ be minimum sum achieved after distributing $f[j]$ such that $j_{th}$ bit is set in mask, among first $i$ buckets.

```cpp

memset(dp,0x3f,sizeof dp);


```








