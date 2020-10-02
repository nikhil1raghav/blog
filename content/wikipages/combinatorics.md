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



