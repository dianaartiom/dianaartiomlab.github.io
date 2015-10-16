---
layout: default
title: APA
---

#Laboratory work Nr. 1

###Ex.1
```
from math import *
from time import time
import matplotlib.pyplot as plt

#here is the firs(recursion) method
n = 10
n2 = 10
def fibonacci_rec(n):
    if n < 2:
        return n
    else:
        return fibonacci_rec(n-1) + fibonacci_rec(n-2)

def f1(n):
    startTime = time()
    fibonacci_rec(n)
    return time() - startTime

#here is the second mehtod(using loop)
def fibonacci_for(n):
    i = 1
    j = 0
    for k in range(n):
        j = i + j
        i = j - i
    return j

def f2(n2):
    startTime = time()
    fibonacci_for(n2)
    return time() - startTime

#here is the code in function 3
def fibonacci_third(n):
    i = 1
    j = 0
    k = 0
    h = 1
    while (n > 0):
        if n % 2 != 0:
            t = j * h
            j = i * h + j * k + t
            i = i * k + t
        t = h * h
        h = 2 * k * h + t
        k = k * k + t
        n = n / 2
    return j

def f3(n2):
    startTime = time()
    fibonacci_third(n2)
    return time() - startTime
def timeMeasure(func):
    startTime = time()
    a = func
    return time() - startTime

A = []
C = []
B = []

for i in range(15):
    A.append(f1(i))
    B.append(f2(i))
    C.append(f3(i))


plt.plot(A)
plt.plot(C)
plt.plot(B)
plt.show()

```
<div class="custom-image"><img src="https://40.media.tumblr.com/ae6ad8b1aeab2d26085a7b4653a37e9a/tumblr_nw6dys7zk31udztn8o1_540.png" /></div>

##Conclusion
By analyzing the results it can be reasonably said that the algorithms don't have the same complexity. The thing is, in a given interval of time, the algorithms converge in a different way. 
When doing the recursive implementation of fibonacci algorithm, you are adding redundant calls by recomputing the same values over and over again. However this can be overcome by a technique called Memoization, that improves the efficiency of recursive fibonacci by storing the values, you have calculated once. Further calls of fib(x) for known values may be replaced by a simple lookup, eliminating the need for further recursive calls.
Iterative functions – are loop based imperative repetitions of a process (in contrast to recursion which has a more declarative approach).
This is the main difference between these approaches. P.S. There are lots of algorithms for computing fibonacci, It is googling problem, I guess. :)