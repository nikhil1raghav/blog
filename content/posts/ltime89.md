+++
title="Codechef October Lunchtime 2020 Division 1"
date="2020-11-01"
description="October lunchtime performance notes, mini editorials and upsolve journal"
author="Nikhil"
tags=["review", "codechef", "upsolve"]
+++
Made 3 full successful submissions and 1 partial scored 325 points with lot of wrong submissions and ended up at 230th place. Here are the notes on some problems I solved during and after the contest and the thought process I had while solving them. I write these posts so that I can document any new problem solving techniques, observation or method of thinking about the problem I encounter during a contest. It also doubles up as an upsolving journal and lets me review my own thought process and outlook during the contest.
# Solved during contest

#### [Chef Likes Good Sequences](https://www.codechef.com/LTIME89A/problems/GSUB)
- At first glance thought it would be a hard problem, without thinking much wrote a brute force for the first subtask, then saw the submission countwas highest for this problem.
- Every update (except terminal updates) either created 3 partitions or merged two partitions, so every query can be answered in $O(1)$ by counting the old and new partitions thus created.
- Had 1 WA on this approach because of a simple implementation mistake, which I was quick to figure out. Will include single testcases like $n=1$ while testing locally.

#### [Cute Chef Gift](https://www.codechef.com/LTIME89A/problems/COPAR)
- Simple number theory problem.
- First thoughts were that I have to find such a partition of the array such that set of primes of both the partitions is disjoint. Used up 20 minutes thinking about implementation details. Should've solved first subtask rather than thinking about how to get 100.

- An observation that solved first two subtasks without doing anything fancy was that if two numbers aren't coprime then they should be in same partition. This helped in calculating bounds of a partition $O(n^2)$ which was enough to pass first two subtasks.

- For 100 points, maintained frequency of all the primes that are in the array and started deleting elements from right, if at some point all the primes used till now become zero then the remaining set is certainly disjoint with the set of all elements removed.
- Editorial had a simpler approach but still it is a nice idea to use in future when I'll have to find some disjoint partition.

#### [Chef Is Just Throwing Random Words](https://www.codechef.com/LTIME89A/problems/SSO)
- When I saw this problem in first minute of the contest I thought it is very hard.
- But when I looked at it after solving above two problems, I found it easier and also had an approach in mind that was to build the answer bit by bit.
- So started thinking when will the given bit be set in the answer, a bit will be set if there is some carry remaining from previous summations or we have a number that has this bit.
- Coded it fast enough but missed a corner case and passed 3 testcases out of 4. It is nice how codechef keeps testing the solution even if it fails the first testcase. It helps a lot in finding the mistake during contest.
- Wrote an assert statement to check if the answer can be greater than $2^{30}$, and then made changes to the solution to get AC.

# Solved after contest

#### [Counting Spaghetti](https://www.codechef.com/LTIME89A/problems/CDSUMS)
- Solved first subtask in contest which was no brainer, but the important observation that I missed from solving first subtask was that if you have all coins in interval $[L:R]$ , if you fix the number of coins used then there is a continuous range of different sums that can be made by those coins.
- Second subtask can be done by iterating on the number of spaghetti you take and adding up the lengths of the ranges thus formed. Taking care of overlapping ranges.
- For solving third task we can just count the ranges which don't overlap, when we solve the quadratic equation as given in editorial, if the equation has no real roots, then no segment overlaps so we solve it how we solved second subtask, otherwise, iterate on the segment size where the equation is positive. 

