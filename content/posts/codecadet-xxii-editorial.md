+++
title="[Tutorial] Codecadet XXII"
math="true"
date="2021-09-25"
description="Solutions and ideas for problems of Codecadet XXII"
tags=["manan", "cp", "tutorial"]
+++

#### 1. [Code Cards](https://www.hackerearth.com/problem/algorithm/code-cards-19ccb549/)

Suppose length of $S1$ is $n$. If $S1$ and $S2$ differ at some index $i$, then we can make $S1_i$ and $S2_i$ equal only when one of them is $ and other is one of the letters in the set { c, o, d, e}.

Otherwise, it is impossible to make $S1$ and $S2$ equal. 

If it is possible, count number of occurrences where $S1$ and $S2$ differ and print that count.

[Solution](https://github.com/Manan-YMCA/codecadet-XXII-editorial/blob/master/CodeCards.java)

---



#### 2. [Dev - the mad king](https://www.hackerearth.com/problem/algorithm/dev-the-mad-king-d944ceef/)

It was straight forward result of __Chicken McNugget theorem__, refer [this](https://artofproblemsolving.com/wiki/index.php/Chicken_McNugget_Theorem) excellent explanation on AoPS.


[Solution](https://github.com/Manan-YMCA/codecadet-XXII-editorial/blob/master/Dev_the_Mad_king.cpp)

---


#### 3. [Bored Vivek](https://www.hackerearth.com/problem/algorithm/bored-mridul-a3f8c00d/)

Task is to select at most $L$ laminates out of $N$ such that sum of their width is at most $W$ and sum of their beauty is maximum.

It is classic [knapsack](https://atcoder.jp/contests/dp/tasks/dp_d) problem with one simple twist that number of laminates can't be more than $L$.

Suppose $dp[i][wt][ct]$ is the maximum beauty if we choose $ct$ laminates with width $wt$ from first $i$ laminates.

For every new laminate we have a choice to either use it or not, if we use a laminate $j$ then $wt$ becomes $wt+w[j]$, $ct$ becomes $ct+1$, otherwise $wt$ and $ct$ don't change.


So, $$dp[i][wt][ct]=\max\limits_{j<i} \space (\space dp[i-1][wt-w[j]][ct-1]+\space beauty[j],\space dp[i-1][wt][ct])$$


We have to find maximum value of $dp[N][wt][ct]$, such that $wt \leq W$ and $ct \leq L$.

You can omit first state of $dp$ to save memory as every layer $i$ depends only on the layer $i-1$, it is shown here for better understanding.


[Solution](https://github.com/Manan-YMCA/codecadet-XXII-editorial/blob/master/BoredVivek.java)

---


#### 4. [Decode "DEV"](https://www.hackerearth.com/problem/algorithm/decode-dev-076ee194/)

We can swap $E$ with adjacent $D$ or $V$. So, if at any place $D$ comes after $E$ and both are adjacent we can swap them to get a better answer. 

This means before first $V$ we can make a sorted prefix of $\{ D,E \}$. As an example if string was $DEDEEV....$,we can get $DDEEEV...$. As no $D$ can be swapped with $V$ , first $V$ acts as a partition between $D$s after and before first $V$.

But all $E$s can get through that, so if there are $X$ $E$s in the complete string and $Y$ $D$s before the first $V$. 
We can achieve $D_XE_YV....$.

Now after the first $V$ we're left with the $D$s that couldn't get through and $V$s. We can't swap $D$ with $V$ so we'll preserve the relative ordering between them after first $V$.


[Solution](https://github.com/Manan-YMCA/codecadet-XXII-editorial/blob/master/Decode%20DEV.cpp)


---

#### 5. [Square Sum Numbers](https://www.hackerearth.com/problem/algorithm/square-sum-numbers-8994f180/)


Such type of tasks are popularly referred as [Digit DP](https://www.codechef.com/tags/problems/digit-dp) problems.

Let's say we have a function $calc(X)$ which finds the answer for range $[1, X]$

Using $calc$ we have two options to find answer for range $[L,R]$

- $calc(R)-calc(L-1)$
- As $L$ can be as large as $10^{100}$, calculating $L-1$ can take extra work, so we can calculate $calc(R)-calc(L) + ok(L)$. Here $ok(x)$ returns $1$ if sum of digits of $x$ is a perfect square, otherwise $0$.


Now I'll discuss how to write $calc(x)$.

Suppose $dp[i][sum][tight]$ is count of numbers such that we have fixed $i$ most significant digits whose sum is $sum$.

$tight$ is $0$ if the number has already become smaller than $x$ i.e. there is some digit in first $i$ which is smaller than its counterpart at the same position in $x$, otherwise tight is $1$.

Now what digit can be placed at $i+1_{th}$ position is determined by $tight$, if number has already become smaller we can place anything from $0$ to $9$ as it is not going to make the number greater than $x$, else we can only choose digits in range $[0,x_{i+1}]$. 

So if we choose digit $d$, $sum$ will become $sum+d$, and $tight$ will remain $1$ if it was $1$ earlier and $d = x_{i+1}$, otherwise we made the number smaller by choosing something else so $tight$ will be $0$.


__NOTE__: In the code below, the name $tight$ is counter-intuitive it is $1$ in the code when number has become smaller than $x$, otherwise $0$ which differs from the idea discussed above, but process remains the same.


[Solution](https://github.com/Manan-YMCA/codecadet-XXII-editorial/blob/master/square%20sum.cpp)


---


#### 6. [The combat of ages](https://www.hackerearth.com/problem/algorithm/the-combat-of-ages-bd7707d1/)

As no hero can kill someone stronger, we can process all heroes in increasing order of their strength. If two heroes have equal strength then we process the hero with smaller age first because doing so gives more coins to older heroes when they will kill this one.

Let's say we have a magic function $best(X)$ which returns maximum number of coins a processed hero with $age \leq X$ has.

Now consider we are processing a hero with age $A$ and it has $C$ coins. So this hero can surely have $C+best(A-1)$ coins by killing a processed hero which has maximum coins i.e. $best(A-1)$ and its age is less than $A$.

This $best(X)$ function can be implemented by using any range update range query data structure, as we are querying only the prefix we can use [Fenwick tree](https://www.youtube.com/watch?v=kPaJfAUwViY) here for easier implementation.

After the score of current player is determined we can update the tree with value $C+best(A-1)$, so that it becomes a candidate for the queries $best(X)$ where $X>A$.


[Solution](https://github.com/Manan-YMCA/codecadet-XXII-editorial/blob/master/The_Combat_of_Ages.cpp)
