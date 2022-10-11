How to Speed up your python code

Python however useful-powerful and flexible it is , it can be a bit slow sometimes


1. Using Proper Data Structure
 
Python's build-in data structures (lists,tuple,set,dictionary) are there for a reason.
Sure it's easier using lists only, but a proper choice can decrease runtime . 

e.g. iterating over tuple is easier than iterating over a list 


```python
import timeit

ls = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25]
ts = (1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25)
 
tl = timeit.default_timer()
for i in ls:
    print(i,end=" ")
tl2 = timeit.default_timer() - tl
print(f"\ntime needed for lists: {tl2}")
tt = timeit.default_timer()
for i in ts:
    print(i, end =' ')
tt2 = timeit.default_timer()-tt
print(f"\ntime need for tuples: {tt2}")
print(tl2>tt2)
```

    1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 
    time needed for lists: 0.0005315999999311316
    1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 
    time need for tuples: 0.0002646000000368076
    True
    

2. Decrease the use of for loop 

A for loop is dynamic in python and takes up more time than a while loop 

So a while loop is preferred 


```python
import timeit 
from timeit import default_timer as dt

f1 = dt()
for i in range(1000):
    print('', end='')
f2 = dt()-f1

print(f"{f2}")

w1=dt()
i = 0 
while i<1000:
    print('', end='')
    i+=1

w2 = dt() -w1
print(f"{w2} \n{f2>w2}")


```

    0.005314099999999655
    0.004089999999997929 
    True
    

3. List Comprehensions 

Is a very nice way of creating lists that you know what the content is 
with append , the attribute append is called as a function in each interation 

Of course list comprehensions cna become a bit crowded and unreadable, so some commenting can go a long way .



```python
import timeit 
from timeit import default_timer as dt

#instead of this 
l1=dt()
L = []
for i in range(10000):
    if i%5==0:
        L.append(i)
l2 = dt()-l1
c1 = dt()
L = [i for i in range (10000) if i%5==0]
c2 = dt()-c1
print(f'{l2} \n {c2} \n {c2<l2}')
```

    0.0060594999995373655 
     0.0035228000006100046 
     True
    

4. Using Multiple Assignments




```python
import timeit 
from timeit import default_timer as dt

s1 = dt()

a=0
b=1
c=2
d=3
e=4
f=5
g=6

s2 = dt()-s1
m1=dt()

a,b,c,d,e,f,g = 0,1,2,3,4,5,6

m2=dt()-m1

print(f'{s2}\n{m2}\n{m2<s2}')

```

    0.0010719000001699897
    0.0004264999997758423
    True
    


5. Do not Use Global Variables 



6. use Library function 

If it's already there, why write it your self?
build-in functions are highly efficient to use 

e.g. :sum and range 



```python
import timeit 
from timeit import default_timer as dt


def builtin_sum():
    return sum(range(10000000))

def loop_sum():
    s = 0
    for i in range(10000000):
        s += 1
    return s
    
bs1 = dt()
builtin_sum()
bs2 = dt()-bs1

ls1=dt()
loop_sum()
ls2=dt()-ls1

print(f'{bs2}\n{ls2}\n{bs2<ls2}')

```

    0.86924689999978
    0.9682162999997672
    True
    


7. Be pythonic

Use generators:
Having a large amount of data in a list but using one data at a time and for once, it is better to use generators

Instead of loops or arrays , we can use python features as map and generators



```python
from time import perf_counter_ns

# non pythonic
start=perf_counter_ns()
total=0 
for i in range(1,100):
    if (i %3)== 0:
        total += i
end=perf_counter_ns()      
nop = end-start


# pythonic
start=perf_counter_ns()
total =sum(range(1, 100, 3))
end=perf_counter_ns()  
nop2 = end - start 
print(f"{nop}\n{nop2}\n{nop2<nop}")


```

    601400
    280300
    True
    

8. Do not use dot operation 




```python
import timeit 
from timeit import default_timer as dt

import math 

doted1 = dt()

var = math.sqrt(60)

doted2 = dt()-doted1

from math import sqrt 

notdot1 = dt()

var = sqrt(60)

notdot2 = dt()-notdot1

print(f'{doted2}\n{notdot2}\n{doted2>notdot2}')



```

    0.00021119999928487232
    0.00016069999946921598
    True
    


9. Use 1 for infinity loops 

Instead of while True, use while 1 

It reduces some runtime


10. Try a different approach 

More efficient ways to write your code, require less runtime 


``` Python
if a_condtion:
    if another_condition:
        do_something
else:
    do_sth_else

```
vs 

```Python
if (not a_condition) or (not another_condition):
    do_sth_else
do_something
```


11. Use speed up applications

Projects like pypy and numba can be used in contests, if pypy allows python runtime will be reduced



12. Special libraries

Yes, obviously C/C++ is faster than python, so packages like numpy,
scipy and pandas are used for processing large datasets.

Numpy is build with C. it's always faster to offload math to numpy instead of on the Python Interpreter. 
Numpy is also more efficient at handling matrix data.



13. Using The latest release of python

Every release is faster and more optimized 



```python
import timeit 
from timeit import default_timer as dt

pl1=dt()
python_list = [i for i in range(10000000)]
[i**2 for i in python_list]
pl2=dt() - pl1 

import numpy as np
nl1 = dt()
numpy_array = np.array([i for i in range(10000000)])
np.square(numpy_array)
nl2 = dt() - nl1 

print(f'{pl2}\n{nl2}\n{pl2>nl2}')

```

    6.6464203999994425
    2.932698600000549
    True
    


14. Function Calls are Expensive 

Some times you need to be cautious about calling functions from inside of a loop. 
Better to iterate inside a function than iterate and call a function each iteration. 


```python
import timeit 
from timeit import default_timer as dt


def square(num):
    return num**2

fs1 = dt()
squares = []
for i in range(1000000):
    squares.append(square(i))

fs2 = dt() - fs1

def squares():
    sqrs = []
    for i in range(1000000):
        sqrs.append(i**2)
    return sqrs

si1 = dt()

sq = squares()

si2 = dt()-si1
    
print(f'{fs2}\n{si2}\n{si2<fs2}')
    
    
    
```

    1.255079200000182
    0.8478624999997919
    True
    


15. Lazy Module Importing 

Importing all the libraries at the top is slower than importing them whehn needed , in the cases that not all of them are necessary. 



16. Multiprocessing 

Python is usually limited to a single core when processing code, but with the multiprocessing library , we can use more. 



17. Collections 

A uselful library that has fast functions for strings


18. Memoization

Caching the results, you can use the same parameter values from the cache instead of recomputing them. 



```python
from time import perf_counter_ns
from functools import lru_cache

def fib(n):
    return n if n < 2 else fib(n-1) + fib(n-2)

@lru_cache(maxsize=None)
def mfib(n):
    return n if n < 2 else mfib(n-1) + mfib(n-2)
start=perf_counter_ns()
print(f"Non-memoized fib()={fib(35)}")
end=perf_counter_ns()      
noc1 = end - start

start=perf_counter_ns()  
print(f"Memoized fib()={mfib(35)}")
end=perf_counter_ns()   
noc2 = end - start 

print(f'{noc1}\n{noc2}\n{noc2<noc1}')
```

    Non-memoized fib()=9227465
    Memoized fib()=9227465
    6371406600
    188900
    True
    


19. Compile Python

Python compilers such as numpa, nuitka, pypi and cython.
Numpa's compiler is JIT (just in time ) provides also GPU powered acceleration



```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```
