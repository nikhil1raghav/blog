+++
title="Minimum changes to make XOR of all segments of a fixed length zero"
math="true"
date="2021-07-17"
description="Dynamic programming solution of a not so interesting problem"
tags=["dynamic-programming"]
+++

## Problem Statement

> Given an array $A$ of length $N$ and an integer $K$, find minimum number of elements to change in the array such that xor of all segments of size $K$ becomes zero.
>
> where
> $1 \leq K \leq N \leq 2000$ and $0 \leq A_i \leq 1024$
>




As the window of size $K$ moves one step from first $K$ elements it leaves behind the first element and includes $K+1_{th}$ element. More formally

$$ A_1 \oplus A_2 \oplus A_3 \oplus \cdots \oplus A_K = A_2 \oplus A_3 \oplus A_4 \oplus \cdots \oplus A_{K+1}$$



Therefore, all numbers which are distance $K$ apart in the array must be equal.

$$ A_{i+bK} = const$$



So we can make groups of numbers and operate on those groups, as to get the end result every number in a group must be same. If a number is at position $i$ then it belongs to the group categorized by $i \\% K$. 

As an example if $K = 2$ then there will be two buckets to categorize all the numbers in. All numbers at odd positions in the array will belong to bucket $1$ and even positioned numbers will fall in bucket $0$.



At this step we have positions grouped together according to the remainder they give when divided by $K$, now we have to assign a number to every group such that xor of every subarray of length $K$ is zero.

---

##### What will be the cost of assigning number $X$ to all the positions in a group $G$?

If total positions in group $G$ are $tot[G]$ and $cnt[G][X]$ is count of $X$ in group $G$. Then cost of assigning $X$ to group $G$ is equal to the numbers which are not equal to $X$ in group $G$, given by
$$tot[G]-cnt[G][X]$$

---

If you write a naïve solution that tries every number in the range $\[0, 1024\]$ for every group and then checks if condition is met at the end. Then it will not scale for more than 2 groups i.e. $K>2$ as it is of order of $1024^K$. Even sample cases have $K>2$ for two cases.

---

### Slower DP solution

Let $dp[i][xr]$ be the minimum changes to make in first $i$ groups such that __xor__ of every subarray of length $i+1$ is $xr$ not considering the numbers in groups $i+1$ to $k-1$.


If we are considering a number $num$ to be the value of group $i$ then

$$dp[i][xr] = min ( \space dp[i][xr] \space, \space dp[i-1][xr \oplus num] \space + \space cost \space of \space assigning \space num)$$

or, $$ dp[i][xr] = min(\space dp[i][xr] \space, \space dp[i-1][xr \oplus num] \space + \space tot[i] - \space cnt[i][num]) $$


Now we can try every possible number for every group in a faster way and the final answer will be $dp[K-1][0]$


```cpp
for(int i=0;i<K;i++){
	for(int xr=0;xr<1024;xr++){
		for(int num=0;num<1024;num++){
			if(i==0)
				dp[i][xr]=tot[i]-cnt[i][xr];
			else
				dp[i][xr]=min(dp[i][xr], dp[i-1][xr^num]+tot[i]-cnt[i][num]);
		}
	}
}

cout<<dp[K-1][0]<<"\n";
```

Why is this slow ? It's complexity is $O(K*2^{20})$ which won't pass if $K \geq 500$ or some equivalent metric. 


---

### Faster DP solution

One observation is $cnt[G][num] = 0$ for some number $num$ then its cost is $tot[G]$. Therefore we can modify the innermost loop to check only for the numbers that exist in a particular group so it runs $\lceil \frac{N}K \rceil$ times for every $xr$ , and check for all other numbers in constant time. 

It brings down the complexity to $O(N*1024)$ as every existent position will be used once for every value of $xr$.

Another way to understand is that outer loop runs $K$ times, inner loop $1024$ times and innermost loop runs for $\lceil \frac{N}K \rceil$ times.


__How to calculate dp for all the numbers that are not present in the array?__

Only task remaining is to take into account all the numbers that are not present in a group, and calculation for all of them can be done at once. 

Key thing to notice is that for every $xr$ we should consider only one such number that is not present in the group, as it doesn't affect the cost which is always $tot[G]$, but allows us to choose the minimum value for $dp[i-1][xr \oplus num]$. 

As we don't know what $num$ is beforehand (and we don't need to), just take the minimum value of $dp[i-1][for \space any \space xr]$ and call it $lastMinimum$.

So, best value of $dp[i][xr]$ for all other numbers not in the group will be

$$lastMinimum + tot[G]$$


In this code $group[i] $ is the set of numbers in group $i$.
```cpp
int lastMinimum=0,tillnow=K;
for(int i=0;i<K;i++){
	tillnow=n; //to update lastminimum

	for(int xr=0;xr<1024;xr++){

		for(int num:group[i]){
			if(i==0)
				dp[i][xr]=tot[i]-cnt[i][xr];
			else
				dp[i][xr]=min(dp[i][xr],dp[i-1][xr^num]+tot[i]-cnt[i][xr]);

		}

		//for all numbers that are not in current group
		dp[i][xr]=min(dp[i][xr],lastMinimum+tot[i]);
		
		tillnow=min(tillnow,dp[i][xr]);
	}
	
	lastMinimum=tillnow;
}

cout<<dp[K-1][0]<<"\n";
```

---

You can practice this problem [here](https://leetcode.com/problems/make-the-xor-of-all-segments-equal-to-zero/) on leetcode.

__Similar problems__
- [XORGON - Codechef](https://www.codechef.com/AGPR2020/problems/ALPR2005)
- [995. - Leetcode](https://leetcode.com/problems/minimum-number-of-k-consecutive-bit-flips/)


















































