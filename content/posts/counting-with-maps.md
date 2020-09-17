+++title="Counting with hashmaps"
author="Nikhil Raghav"
cover="https://c7.uihere.com/files/543/911/831/pepe-the-frog-emoticon-sticker-t-shirt-emote-pepe-emoji.jpg"
description="A useful technique with hashmaps"
showFullContent = false
+++

It is a recurring and really useful idea to count some property in O(n) in an array if the relation is some kind of equation where right hand side and left hand side only differs in their indexes. For example __counting number of subarrays with sum X__.

## Subarrays with sum X

Let's say we are given an array __A__ of length __N__ and we have to count how many subarrays of __A__ sum up to a given number __X__. First of all to support subarray sum query in O(1) time we need to calculate prefix sum for __A__. After that we have two options:

```cpp

vector<int> prefix(n+1);
for(int i=1;i<=n;i++)
prefix[i]=prefix[i-1]+a[i-1];

```
1. Naively set start and end of a subarray and check if its sum is __X__, can be done in __O(n²)__.
```cpp

for(int start=1;start<=n;start++)
  for(int end=start;end<=n;end++)
  {
    int sum=prefix[r]-prefix[l-1];
    if(sum==X)ans++;
  }
  
  return ans;
  
```
2. Now as we have seen in option 1 we simply need to count all $$(l,r)$$ pairs such that __prefix[r] - prefix[l-1] = X__ or __prefix[r] - X= prefix[l-1]__. Now, if we store count of all prefix sums seen previously, at every index __i__ we can query for how many __prefix[i] - X__  we have seen before and add them to the answer as they all will be the starting indexes of subarrays ending at __i__. It is that simple.

```cpp

unordered_map<int,int> f;
int ans=0;
for(int i=1;i<=n;i++)
{
  ans+=f[prefix[i]-X];
  f[prefix[i]]++;
}

```







##### This post is work in progress. You can solve these problems till I complete it.
---
**Some relevant problems**
- [E - This Message Will Self-Destruct in 5s](https://atcoder.jp/contests/abc166/tasks/abc166_e)
- [D - Multiple of 2019](https://atcoder.jp/contests/abc164/tasks/abc164_d)
- [E - Rem of Sum is Num](https://atcoder.jp/contests/abc146/tasks/abc146_e)
- [C. Good Subarrays](https://codeforces.com/contest/1398/problem/C)
- [C. Molly's Chemicals](https://codeforces.com/problemset/problem/776/C)
- [E - Divisible Substring](https://atcoder.jp/contests/abc158/tasks/abc158_e)
- [E - ∙ (Bullet)](https://atcoder.jp/contests/abc168/tasks/abc168_e)
