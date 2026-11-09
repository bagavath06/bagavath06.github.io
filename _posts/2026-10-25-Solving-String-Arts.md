---
layout: post  
title: String-art Problems  
date: 2026-09-25  
categories: jekyll update  
---
# Activity-2 String-art  

## Indroduction
In Second Unit of **Craft of computing** we indroduced to python. The string-art is one of the sub-topic in Python. Basically What string-art does is it  connect the points with theards(lines),Using differnet Pattern. So **Activity-2 String-art contains 6 problems. This post is about How I approched and solved that problems. What are the mistake I did how I able to overcome thoes miskate. The intresting part is I not used AI. I used My proferser notes to solve the 6 problems.

## Problem-1:
### Write python code to make the pattern shown below.

![](https://coc.apucomputing.in/~anand/activity-2/images/pentagonal-star.svg)

**Step-1** 

Finding the n. A star with 5 marks on the circle. so we now know the value of n. Which is 5 `n=5`

**Step-2** 

How the points are connected. I will write the points to find the pattern.(0,2),(1,3),(2,4),(3,0),(4,1).Here the points are not so complicated so we can connect manual.

```python
n = 5

make_circle()
connect(0,2)
connect(1,3)
connect(2,4)
connect(3,0)
connect(4,1)
```

**Step-3** 

* Using show function we can visualize our output. `show()`
* Remmber to import stringart 
* You can also do this with the for loop. The first number in the point always increasing by one and the second number start from two and increasing by one.
* ```python
  for i in range(n):
     connect(i,i+2)
  ``` 
* first i is 0 and i+2 will be (0,2). our first point. then i will be 2 and the i+1 will be (1,3) then so on the same pattern as we manualy did.

FULL CODE:

```python

from sringart import *

n = 5

make_circle
connect(0,2)
connect(1,3)
connect(2,4)
connect(3,0)
connect(4,1)

show()
```

Another way to do it is:


```python
from stringart import *

n = 5

make_circle(n)

for i in range(n):
    connect(i,i+2)

show()

```



## Problem-2:
Write python code to make the pattern shown below.

![](https://coc.apucomputing.in/~anand/activity-2/images/p2.svg)

* **Step-1:** Findind the value of n. From the image `n = 8` 

* **Step-2:** writing and figuring out the points pattern.points
(0,2),(2,4),(4,6),(6,8) , first I wrote the continuous pattern. then (1,5) and (3,7). It is easy to do with manual connection because the connection are not complicated. But I aslo tried to do with the for loop. we can see that  first place in the points first with zero and increasing by 2 and the second place in the point start with 2 and increacing by 2. and the other two point I can't find the commom pattern it shared. I decided to do with manualy.  


```python
from stringart import *

n = 8

make_circle(n)
connect(0,2)
connect(2,4)
connect(4,6)
connect(6,8)

connect(1,5)
connect(3,7)

show()   

```     
Another way to do it is:

```python                          
n = 8 

make_circle(n)
for i in range(n):
    connect(i*2,2*i+2)
connect(1,5)
connect(3,7)
```


## Problem-3:

### Write python code to make the pattern shown below.

![](https://coc.apucomputing.in/~anand/activity-2/images/p3.svg)
- `n=18`
- every point in the circle connected to point 0 
- imagine the points (0,1),(0,2)...(0,17)
- connect(0,i)

```python
n = 18

make_circle(n)

for i in range(n):
    connect(0,i)

show()
```


## Problem-4:
### Write python code to make the pattern shown below.

![](https://coc.apucomputing.in/~anand/activity-2/images/p4.svg)

**Step-1**: `n=12`  

**Step-2** :
- Look at the Pattern It have sub-pattern in it. 
- I saw there are three square exits in the image.
- one point connected to three other points.
- I understand somthing that It is done by the loop.if the number is 12 it actually 0  and 13 mean 1 and 14 means 2 so on.
- writing the point (0,3),(1,4),(2,5)(3,6)...(12,15). the 15 here is not 15 actually 3. I explaine it above. after excuting it I check am in right track i got my first square.
- 2nd   (0,5),(1,6),(2,7)...(12,17). again here 17 is 5 
- 3nd (0,7),(1,8),(2,9)...(12,19)
- 4rth (0,9),(1,10),(2,11)...(12,21)
- I notices that fist place in the point is staring from 0 and increasting by one.

**While writing this I realised somthing**
- It start with zero and coonnected to 3 (0,3) it is same as (12,3). which same as (12,15), then the next point is (0,5)==(12,5)==(12,17)==(0,17)
- apply this the previous one (0,3),(1,4),(2,5)(3,6)...(12,15)
from here (0,5),(1,6),(2,7)...(12,17) == (12,17),(13,18),(14,19)...(24,29)
- everything is going in the order of the first place in the point start from 0 and the second place from the point start from 3 let say i is 0 how to make the second point 3. i+3 
(0,3) then the i become 1 i+3 which is (1,4) then i become 2 i+2 which is (2,5) this are the points we want. 
- But it will only create on pattern we have sub-parrent 
- for the 3nd anf 4th see the first point in (0,7) which is our (i,i+3) condition will not satify. when need to change the 3 and replace with 5.
- for this we have to create 2 for loop. that why to avoid creating multi for loop we use user-defined function.
using the keyword `def <function name>`
```python
n = 12

def connecting_ring(n,k):
    for i in range(n):
       connect(i,i+k)

make_circle(n)

connecting_ring(n,3)
connecting_ring(n,5)

show()
```

## Problem-5:
Write python code to make the pattern shown below.

![](https://coc.apucomputing.in/~anand/activity-2/images/p5.svg)

- It is the combination of Problem 3 and 4.
- one point is connect to 3 theard. 
- which is 7, 9  and 11
- all the points are conneted to these points. same point conneting is our problem-3, avoiding multi-for loop was our problem-4.

```python
n = 18

def connect_ring(n,k):
   for i in range(n):
       connect(i,k)

connect_ring(n,7)
connect_ring(n,9)
connect_ring(n,11)

show()
```

## Problem 6

Write python code to make the pattern shown below.

![](https://coc.apucomputing.in/~anand/activity-2/images/p6.svg)

- This was really hard for me to figure out. 
- I will say I actually not done this by figuring out.
- I kept trying with the points pattern. after sometimes I saw a simliar pattern. then I kept change the first part of the point by kepting the second part as constant.
- After the accident I figure out how my accident find code works.
- Really I enjoyed doing these problems. I even used my pen to find which point connect to which point.
- you can see a triangle in it that was the key to solve this problem
* `n=36`
* see 36 , 12 , 24 have two points (0,12),(0,24)== (36,12),(36,24).
(12,0),(12,24)== (12,36),(12,24). (24,0),(24,12)== (24,36),(24,12) 
- if you notice 12 to 24 every point have connect to 2 points and others are connected to one.
- (0,12),(1,13),(2,14)...(12,24)
- (24,12),(25,13),(26,14)
- (13,25),(14,26)...
- thats all see the pattern  1st place is increasing by one and the second place is start with 12 

```python
make_circle(n)

def connect_ring(n,k):
    for i in range(n):
       connect(i,i+k)

connect_ring(25,12) # This line I found accidently

show()
```

  

