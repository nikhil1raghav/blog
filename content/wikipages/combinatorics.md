+++
title='Combinatorics'
noComment=true
+++

### 1. Correspondence
Mapping one problem to a simpler and equal problem. Counting numbers between 14 and 103 is equal to counting numbers between 1 and 89. 

#### Problem #1
Count number of permutations $P$ of length $10$ such that
$P=p_1,p_2,p_3,\cdots,p_{10}$ and $p_1>p_2>p_3>p_4>p_5$ and $p_5< p_6 < p_7 < p_8 < p_9 < p_10 $

Idea : $p_5$ is 1 obviously, now selecting any 4 numbers out of 9 will do as order is fixed.  

#### Problem #2
If a die is rolled 4 times. Find probability of the event where each of last 3 rolls are as large as the roll preceding it.

Idea : order is fixed again (non-decreasing), just count number of ways to distribute 4 positions among 6 candidates i.e. $^9C_4$. Useful idea to count number of sorted arrays for given constraints.


# Derangements

Number of derangements of a permutation are all those arrangements in which no element is at the same position as it is in original permutation. As an example derangements of __(1,2,3)__ are __(2,3,1)__ and __(3,1,2)__.

General formula can always be derived by using inclusion-exclusion principle, but it is not useful because calculating it will be __O(n)__ and recurrence relation of derangement is more brief and intuitive and also takes __O(n)__ time.

- #### Deriving using Inclusion-exclusion principle
	
	Let's say $X_k$ be the set that contains element $k$ at position $k$.Then, $$D(n) = n! - |X_1 \cup X_2 \cup X_3 \cup \cdots \cup X_n|$$

- #### Recurrence relation
	Obviously, $D(1) = 0$ and $D(2) = 1$. Let's see what happens with $1$, we have $(n-1)$ choices to choose a replacement for $1$ call that replacement $x$, now for any $n$ we have two options.
	- __Option 1__ : Replace $x$ with $1$. Problem changes into finding $D(n-2)$.
	- __Option 2__ : Replace $x$ with some number other than $1$. So $1$ is not placed anywhere yet and other $n-2$ numbers except $x$ are at their own position. So in total $n-1$ numbers remain to be placed. Therefore, problem changes to $D(n-1)$.

	$$D(n) = (n-1)( D(n-1)+D(n-2) )$$

