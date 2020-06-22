---
layout: post
title:  "python和JAVA初学者的园地"
date:   2020-06-21 10:03:25
author: coolxy
categories: python
tags: python
---
## python和JAVA初学者的园地
最近找到一个网站：<https://codingbat.com/python>，这里是python和java初学者的园地，在这里你可以充分的发挥你在程序学习上的逻辑推理能力。一关一关的过。
### Warmup-1 > sleep_in：
The parameter weekday is True if it is a weekday, and the parameter vacation is True if we are on vacation. We sleep in if it is not a weekday or we're on vacation. Return True if we sleep in.  
sleep_in(False, False) → True  
sleep_in(True, False) → False  
sleep_in(False, True) → True  

```python
def sleep_in(weekday, vacation):
  if not weekday and not vacation:
    return True
  elif weekday and not vacation:
    return False
  elif not weekday and vacation:
    return True
  else:
    return True
```
### Warmup-1 > monkey_trouble
We have two monkeys, a and b, and the parameters a_smile and b_smile indicate if each is smiling. We are in trouble if they are both smiling or if neither of them is smiling. Return True if we are in trouble.  
monkey_trouble(True, True) → True  
monkey_trouble(False, False) → True  
monkey_trouble(True, False) → False  
```python
def monkey_trouble(a_smile, b_smile):
  if a_smile and b_smile:
    return True
  elif not a_smile and not b_smile:
    return True
  else:
    return False
```
### Warmup-1 > sum_double
Given two int values, return their sum. Unless the two values are the same, then return double their sum.  
sum_double(1, 2) → 3  
sum_double(3, 2) → 5  
sum_double(2, 2) → 8  
```python
def sum_double(a, b):
  if a!=b:
    return a+b
  else:
    return (a+b)*2
```
### Warmup-1 > diff21
Given an int n, return the absolute difference between n and 21, except return double the absolute difference if n is over 21.  
diff21(19) → 2  
diff21(10) → 11  
diff21(21) → 0  
```python
def diff21(n):
  if n<=21:
    return 21-n
  else:
    return (n-21)*2
```
### Warmup-1 > parrot_trouble
We have a loud talking parrot. The "hour" parameter is the current hour time in the range 0..23. We are in trouble if the parrot is talking and the hour is before 7 or after 20. Return True if we are in trouble.  
parrot_trouble(True, 6) → True  
parrot_trouble(True, 7) → False  
parrot_trouble(False, 6) → False  
```python
def parrot_trouble(talking, hour):
  if talking and (hour<7 or hour>20):
    return True
  else:
    return False
```
###  Warmup-1 > makes10
Given 2 ints, a and b, return True if one if them is 10 or if their sum is 10.  
makes10(9, 10) → True  
makes10(9, 9) → False  
makes10(1, 9) → True  
```python
def makes10(a, b):
  if a==10 or b==10 or a+b==10:
    return True
  else:
    return False
```
简洁版（官方版），仔细思量：
```python
def makes10(a, b):
  return (a == 10 or b == 10 or a+b == 10)
```
### Warmup-1 > near_hundred
Given an int n, return True if it is within 10 of 100 or 200. Note: abs(num) computes the absolute value of a number.  
near_hundred(93) → True  
near_hundred(90) → True  
near_hundred(89) → False  
```python
def near_hundred(n):
  if abs(100-n)<=10 or abs(200-n)<=10 :
    return True
  else:
    return False
```
官方版：
```python
def near_hundred(n):
  return ((abs(100 - n) <= 10) or (abs(200 - n) <= 10))
```
### Warmup-1 > pos_neg
Given 2 int values, return True if one is negative(负数) and one is positive(正数）. Except if the parameter "negative" is True, then return True only if both are negative.  
pos_neg(1, -1, False) → True  
pos_neg(-1, 1, False) → True   
pos_neg(-4, -5, True) → True
```python
def pos_neg(a, b, negative):
  if  ((a<0 and b>0) or(a>0 and b<0)) and not negative:
    return True
  elif negative and (a<0 and b<0) :
    return True 
  else:
    return False
```
官方版：
```python
def pos_neg(a, b, negative):
  if negative:
    return (a < 0 and b < 0)
  else:
    return ((a < 0 and b > 0) or (a > 0 and b < 0))
```
### Warmup-1 > not_string
Given a string, return a new string where "not " has been added to the front. However, if the string already begins with "not", return the string unchanged.  (给定一个字符串，返回一个新字符串，将“not ”添加到字符串开头。但是，如果字符串已经以“not”开头，则不加更改地返回字符串。)
not_string('candy') → 'not candy'  
not_string('x') → 'not x'  
not_string('not bad') → 'not bad'  
```python
def not_string(str):
  if 'not' in str[0:3]:
    return str
  else:
    return "not "+str
```
官方版：
```python
def not_string(str):
  if len(str) >= 3 and str[:3] == "not":
    return str
  return "not " + str
  # str[:3] goes from the start of the string up to but not
  # including index 3
```
### Warmup-1 > missing_char
Given a non-empty string and an int n, return a new string where the char at index n has been removed. The value of n will be a valid index of a char in the original string (i.e. n will be in the range 0..len(str)-1 inclusive).  
missing_char('kitten', 1) → 'ktten'  
missing_char('kitten', 0) → 'itten'  
missing_char('kitten', 4) → 'kittn'  
```python
def missing_char(str, n):
  return str[:n]+str[n+1:]
```
官方版：
```python
def missing_char(str, n):
  front = str[:n]   # up to but not including n
  back = str[n+1:]  # n+1 through end of string
  return front + back
```
### Warmup-1 > front_back
Given a string, return a new string where the first and last chars have been exchanged.  (返回首尾字符交换的字符串）
front_back('code') → 'eodc'  
front_back('a') → 'a'  
front_back('ab') → 'ba'  
以下代码本机测试通过(考虑字符串只有1，或0时）：
```python
def front_back(str):
  if len(str)<=1:
    return str
  else:
    l=len(str)
    first=str[0]
    last=str[l-1]
    return last+str[1:(l-1)]+first
```
官方版：
```python
def front_back(str):
  if len(str) <= 1:
    return str
    mid = str[1:len(str)-1]  # can be written as str[1:-1]
    # last + mid + first
  return str[len(str)-1] + mid + str[0]
`````