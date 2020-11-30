+++
title="Alphabet and Language"
author="Nikhil"
description="Intro to alphabet and language"
+++

### [Alphabet and strings](#)
- __Alphabet__ is any non-empty finite set, such as $S=[a,b,c, \cdots z]$.
- __String__ over alphabet $S$ is finite sequence of symbols of $S$.
- Empty sequence is also finite therefore it is also called a string. We denote empty string with symbol $\varepsilon$.
- Set of all strings over $S$ is denoted as $S^*$ .
- If $S=[0,1]$ then $S^* = [0, 1, 00, 01, 11, 000, \cdots\]$
- $S^*$ is infinite but it is a countable set. 
- $S^*$ is [countably infinite](https://mathinsight.org/definition/countably_infinite) for any alphabet $S$.
	- A set is countably infinite if all its elements have one to one correspondence with natural numbers. Like set of integers or whole numbers.
	- Further reading : [Cantor's diagonal argument](https:www.planetmath.org/cantorsdiagonalargument)
	
	#### Concatenation
	- If $x= a_1 a_2 a_3$ and $y=b_1 b_2 b_3$. 
	- Concatenation of $(x,y)$ is $a_1 a_2 a_3 b_1 b_2 b_3$. Denoted by $xy$
	- Concatenation:
		- is associative on $S^*$
		- has an identity element. As, $\varepsilon x = x$
		- is not commutative on $S^*$
	- Therefore $S*$ is a monoid with respect to concatenation.
	
	#### Repitition
	- For a string $x$
	$$x^{n+1}=x^nx$$  
	- That is $x$ repeated $n+1$ times
	
	#### Occurence of a pattern
	- Let $x$ be a string over alphabet $S$.
	- For $a \epsilon \space S$. Number of occurences of $a$ in $x$ can be denoted as $|x|_a$
	
	#### Length of the string
	- Length of string $x$ is denoted as $|x|$
	- So we can write:
	$$|x|= \sum_{a\epsilon \space S} |x|_a$$
	- It means that length of string is sum of occurences of all the alphabets.
	
	#### Substring
	- $x$ is a substring of $y$ if $y = uxv $ where $u$ and $v$ are any two strings.



### [Language](#)
- 
