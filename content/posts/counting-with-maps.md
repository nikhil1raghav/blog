+++title="Counting with hashmaps"
author="Nikhil Raghav"
date="2020-09-15"
math=true
description="A useful technique with hashmaps"
showFullContent = false
tags=["programming", "techniques", "codeforces", "atcoder"]
+++

It is a recurring and really useful idea to count some property in O(n) in an array if the relation is some kind of equation where right hand side and left hand side only differs in their indexes. For example __counting number of subarrays with sum X__.

## 1. Subarrays with sum X

Let's say we are given an array __A__ of length __N__ and we have to count how many subarrays of __A__ sum up to a given number __X__. First of all to support subarray sum query in O(1) time we need to calculate prefix sum for __A__. After that we have two options:

```cpp

vector<int> prefix(n+1);
for(int i=1;i<=n;i++)
prefix[i]=prefix[i-1]+a[i-1];

```
  __Option 1.__ Naively set start and end of a subarray and check if its sum is __X__, can be done in __O(n²)__.
```cpp

for(int start=1;start<=n;start++)
  for(int end=start;end<=n;end++)
  {
    int sum=prefix[r]-prefix[l-1];
    if(sum==X)ans++;
  }
  
  return ans;
  
```

 __Option 2.__ As we have seen in option 1 we simply need to count all __(l,r)__ pairs such that __prefix[r] - prefix[l-1] = X__ or __prefix[r] - X= prefix[l-1]__. 



If we store count of all prefix sums seen previously, at every index __i__, we can count how many __prefix[i] - X__  we have seen before and add them to the answer as they all will be the starting indexes of subarrays ending at __i__. It is that simple.



```cpp

unordered_map<int,int> f;
int ans=0;
for(int i=1;i<=n;i++)
{
  ans+=f[prefix[i]-X];
  f[prefix[i]]++;
}

```

It is a recurring pattern in this approach that you add contribution for every index and make changes to some count that is affected by the value at that index.



#### [1398C. Good Subarrays](https://codeforces.com/contest/1398/problem/C)


__Abridged Problem Statement__ : Count number of subarrays where sum of the subarray is equal to size of the subarray.

More formally count all pairs (l,r) such that:
	$$ Sum(l,r)=r-l+1 $$


Let $p[i]$ be sum of the prefix of length $i$ of the array. Then we can write:
	$$ pre[r]-pre[l-1] = r-l+1$$


Some manipulation of above equation leads to:
	$$ pre[r]-r = pre[l-1]-(l-1) $$


Above equation has the required property that we need to solve the problem using this technique that is __right hand side and left hand side only differ in their index__.


So we run a loop from $1$ to $n$ and for current index calculate its contribution to the answer as $r$. In simpler words just add to the answer all the occurences of $pre[r]-r$ occured so far, because all those occurences will be the leftmost indexes of the subarrays that are good.



```cpp
map<int,int> m;
long long ans=0;
m[0]=1;// or start the loop from 0
for(int i=1;i<=n;i++){
	ans+=m[pre[i]-i];
	m[pre[i]-i]++;
}
cout<<ans<"\n";
```
#### [ABC 146 E. Rem of sum is num](https://atcoder.jp/contests/abc146_e)
- __Abridged problem statement__: Count subarrays such that remainder of its sum when divided by $K$ is equal to the size of the subarray.
- Formally:
	$$Sum(l,r)\equiv (r-l+1) mod K$$

- Or $$pre[r]-pre[l-1]\equiv r-(l-1) mod K$$
- So if $pre[i]$ is the remainder we get when we divide sum of prefix of length $i$ by $K$.
- Then we can write $pre[r]-pre[l-1] = (r-l+1)$ as 




##### This post is work in progress. You can solve these problems till I complete it.

---

#### Practice Problems
- [A - Zero-Sum Ranges](https://atcoder.jp/contests/agc023/tasks/agc023_a)
- [E - This Message Will Self-Destruct in 5s](https://atcoder.jp/contests/abc166/tasks/abc166_e)
- [D - Multiple of 2019](https://atcoder.jp/contests/abc164/tasks/abc164_d)
- [E - Rem of Sum is Num](https://atcoder.jp/contests/abc146/tasks/abc146_e)
- [C. Good Subarrays](https://codeforces.com/contest/1398/problem/C)
- [C. Molly's Chemicals](https://codeforces.com/problemset/problem/776/C)
- [E - Divisible Substring](https://atcoder.jp/contests/abc158/tasks/abc158_e)
- [E - ∙ (Bullet)](https://atcoder.jp/contests/abc168/tasks/abc168_e)
- [A- Integer Product](https://atcoder.jp/contest/agc047/tasks/agc047_a)
- [B - Reverse and Compare](https://atcoder.jp/contests/agc019/tasks/agc019_b)
- [K - PhD Math](https://codeforces.com/gym/100814/problem/K)
- [D - A and B and Intersesting Substrings](https://codeforces.com/contest/519/problem/D)
- [D - Count good substrings](https://codeforces.com/contest/451/problem/D)
