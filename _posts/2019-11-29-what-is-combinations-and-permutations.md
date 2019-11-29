---
layout: post
title:  "What is Combinations and Permutations"
date:   2019-11-29 00:00:00 +02
categories: programming_terms
author: "Shendy"
---
Today, I will discuss with you what is the concept of **Combinations* and *Permutations*, and how to use them in programming.  

<br />

I will be using Python to apply these concepts in programming, but language doesn't matter here, the concept is what matters, so whatever language you decide to use, there will be a library which gives you access to combinations and permutations.

<br />

In Python, **itertools** is the library that I use for combinations and permutations.
```python
import itertools
```

<br />

### Here is the main header in this article:
- [What is Combinations and Permutations](#what-is-combinations-and-permutations)
- [Apply Combinations and Permutations using Python](#apply-combinations-and-permutations-using-python)  
  - [Combinations Example](#combinations-example)
  - [Permutations Example](#permutations-example)
- [Real Problems for Combinations and Permutations](#real-problems-for-combinations-and-permutations)

<br />

### What is Combinations and Permutations
Both of **Combinations** and **Permutatinos** are mathematical concepts, and they are for finding all different/possible ways in which you can group list of items, but they differ in the order of items for each group:
- In combinations the order **does not** matter.
- In permutations the order **does** matter.

<br />

### Apply Combinations and Permutations using Python
The methods `combinations` and `permutations` of `itertools` library receive two parameters, one is for interable object (e.g list), the second is how many items to include in each group.

<br />

#### Combinations Example:  
We are looking for all different groups of **3** items from **my_list**.
```python
my_list = [1, 2, 3]

combinations = itertools.combinations(my_list, 3)
for c in combinations:
    print(c)
```
```
(1, 2, 3)
```
Since the order doesn't matter, and **my_list** is a list of size 3, then we can only get one group.

<br />

So what about finding the different groups of **2** items?
```python
my_list = [1, 2, 3]

combinations = itertools.combinations(my_list, 2)
for c in combinations:
    print(c)
```
```
(1, 2)
(1, 3)
(2, 3)
```
Now we get more one group of **2** items, definitely they are more if the order matters, we will see it in `permutations` example.  

<br />

#### Permutations Example:  
Let's see all different groups of **2** items from **my_list**.
```python
my_list = [1, 2, 3]

permutations = itertools.permutations(my_list, 2)
for p in permutations:
    print(p)
```
```
(1, 2)
(1, 3)
(2, 1)
(2, 3)
(3, 1)
(3, 2)
```
See? since order does matter in Permutations, `(1, 2)` will be different group than `(2, 1)`, and we will get more groups than Combinations method.

<br />

### Real Problems for Combinations and Permutations
So, let's see some real problems to learn how this might be important.  

<br/>
  
**Problem**:  
Given list of positive numbers, print list of possible groups of 3 numbers so the sum of numbers in th same group equals 10.  

<br/>

**Solution**:  
In this problem, order won't matter because both `1 + 3 + 6` and `3 + 1 + 6` will equal 10, so Combinations fits this problem.
```python
my_list = [1, 2, 3, 4, 5, 6]

combinations = itertools.combinations(my_list, 3)

print( [result for result in combinations if sum(result) == 10] )
```
```
[(1, 3, 6), (1, 4, 5), (2, 3, 5)]
```

<br/>

**Problem**:  
Given a string of random letters, check if there is a group of these letters matches the word 'sample'.

<br/>

**Solution**:  
Order does matter here because `as` doesn't equal to `sa`, so Permutations fits this problem.
```python
word = 'sample'
string = 'plmeas'

permutations = itertools.permutations(string, len(string))

for p in permutations:
  if ''.join(p) == word:
    print('Match!')
    break
else:
  print('No Match!')
```
```
Match!
```

<br/>
<br/>
That's all for today article, hope you like it.
