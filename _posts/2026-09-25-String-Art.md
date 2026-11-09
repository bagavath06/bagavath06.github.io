---
layout: post
title: "String-Art"
date: 2026-09-24
categories: jekyll update
---
# String-Art

## Indroduction
String-Art are making patterns by  connecting  the points. I learned to do with Circle.

## What are the things I learned 

1. ***FIRST STEP:***  
    - Import the stringart.
    - When I update craft.sh it installed the stringart package
    - To Use string-art we should excute ```from stringart export * ```  


1. ***The three functions:*** 

    1. **make_circle()**
        - It will create a circle
        - **eg:** make_circle(5)
        - It will create a circle with 0 to 4 point marked on the circle 
    1. connect()
        - It will connect the points on the  circle
        - **eg:** connect(0,1)
        - It will connect the point 0 and the one 
    1. show()   
        - Without it output will not be displayed


1. ***for loop:***
* for loop are more usefull to do repition tasks.when defing the functions.
* what if you have many point to connect. So manual typing will take a alot of time.Inorder to overcome that challage we use **for loop**.
* In for loop we will look for the pattern of point. how the point are constructed. based on the pattern will will do the for loop.  
* **eg:**  
```
 for i in range(5):
    connect(i,i+1)
```    

4. ***User defined function:***
* By user defind funtion we can create our own function and use in a code.
* This is very usefull because we dont want to write multi-for loop we can create a user-defined function for that  particular for loop. 
* **eg:**  
```
def make_ring(n,k):
    for i in range(n):
       connect(i,i+k)
```

## My apporoch of String-art Problems
- First I will look how many point I need to mark on the circle. 
- If it is less pointto connect i'll use connect
function to do that part.
- If the partten is so complex I will try to us the for loop.
- For sub-string kinda paternt I will use user defined function
- Mostly I will try to recoginse the pattern   by   writing down the points it been connected

## My Mistakes 
1.  Not entering the  ``` from stringart import *```  
1. not using * symbol for multipication. eg: 2i  
3. Problem four I really not used user defintion funtion at start so that made a while to figure out even for that pattent reganize. 
4. Forget to use ```make_circle()```
learning_journal/_posts/2026-09-20-welcome-to-jekyll.markdown

