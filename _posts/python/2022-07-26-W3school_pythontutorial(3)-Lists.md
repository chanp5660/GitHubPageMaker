---
layout: post  
current: post  
cover:  assets/built/images/python-logo.png  
navigation: True  
title: W3school_pythontutorial(3)-Lists   
date: 2022-07-26 23:40:00 +0900  
tags: [python]  
class: post-template  
subclass: 'post tag-python'  
author: chanp5660  
---

{% include w3python-table-of-contents.html %}

# W3school_pythontutorial(3)-Lists

> **내실 다지기** : [w3school](https://www.w3schools.com/) 사이트에서 python tutorial을 처음부터 끝까지 하는 목표로 시작하는 포스팅으로 제공해주는 목차 순서대로 진행한다. 간단한 내용은 제공해준 예제만 실행해본다. 활용해볼 예제는 추가로 간단한 예제를 만들어 실행하는 코드까지 작성하며 내실을 다진다.



- <a href="#Lists">Lists</a>
    - <a href="#Lists">Lists</a>
    - <a href="#Access_List_Items">Access List Items</a>
    - <a href="#Change_List_Items">Change List Items</a>
    - <a href="#Add_List_Items">Add List Items</a>
    - <a href="#Remove_List_Items">Remove List Items</a>
    - <a href="#Loop_Lists">Loop Lists</a>
    - <a href="#List_Comprehension">List Comprehension</a>
    - <a href="#Sort_Lists">Sort Lists</a>
    - <a href="#Copy_Lists">Copy Lists</a>
    - <a href="#Join_Lists">Join Lists</a>
    - <a href="#List_Methods">List Methods</a>
    - <a href="#List_Exercises">List Exercises</a>

<p id="Lists"></p>  

## Lists 

> [Lists](https://www.w3schools.com/python/python_lists.asp)


```python
mylist = ["apple", "banana", "cherry"]
print(mylist)
```

    ['apple', 'banana', 'cherry']
    


```python
# Allow Duplicates
thislist = ["apple", "banana", "cherry", "apple", "cherry"]
print(thislist)
```

    ['apple', 'banana', 'cherry', 'apple', 'cherry']
    


```python
# List Length
thislist = ["apple", "banana", "cherry"]
print(len(thislist))
```

    3
    


```python
# List Items - Data Types
list1 = ["apple", "banana", "cherry"]
list2 = [1, 5, 7, 9, 3]
list3 = [True, False, False]
print(list1)
print(list2)
print(list3)
```

    ['apple', 'banana', 'cherry']
    [1, 5, 7, 9, 3]
    [True, False, False]
    


```python
list1 = ["abc", 34, True, 40, "male"]
print(list1)
```

    ['abc', 34, True, 40, 'male']
    


```python
# type()
mylist = ["apple", "banana", "cherry"]
print(type(mylist))
```

    <class 'list'>
    


```python
# The list() Constructor 
thislist = list(("apple", "banana", "cherry")) # note the double round-brackets
print(thislist)
```

    ['apple', 'banana', 'cherry']
    

<p id="Access_List_Items"></p>  

## Access List Items

> [Access List Items](https://www.w3schools.com/python/python_lists_access.asp)


```python
# Access Items
thislist = ["apple", "banana", "cherry"]
print(thislist[1])
```

    banana
    


```python
# Negative Indexing
thislist = ["apple", "banana", "cherry"]
print(thislist[-1])
```

    cherry
    


```python
# Range of Indexes
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[2:5])
```

    ['cherry', 'orange', 'kiwi']
    


```python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[:4])
```

    ['apple', 'banana', 'cherry', 'orange']
    


```python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[2:])
```

    ['cherry', 'orange', 'kiwi', 'melon', 'mango']
    


```python
# Range of Negative Indexes
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[-4:-1])
```

    ['orange', 'kiwi', 'melon']
    


```python
# Check if Item Exists
thislist = ["apple", "banana", "cherry"]
if "apple" in thislist:
    print("Yes, 'apple' is in the fruits list")
```

    Yes, 'apple' is in the fruits list
    

<p id="Change_List_Items"></p>  

## Change List Items

> [Change List Items](https://www.w3schools.com/python/python_lists_change.asp)


```python
# Change Item Value
thislist = ["apple", "banana", "cherry"]
thislist[1] = "blackcurrant"
print(thislist)
```

    ['apple', 'blackcurrant', 'cherry']
    


```python
# Change a Range of Item Values
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "mango"]
thislist[1:3] = ["blackcurrant", "watermelon"]
print(thislist)
```

    ['apple', 'blackcurrant', 'watermelon', 'orange', 'kiwi', 'mango']
    


```python
thislist = ["apple", "banana", "cherry"]
thislist[1:2] = ["blackcurrant", "watermelon"]
print(thislist)
```

    ['apple', 'blackcurrant', 'watermelon', 'cherry']
    


```python
thislist = ["apple", "banana", "cherry"]
thislist[1:3] = ["watermelon"]
print(thislist)
```

    ['apple', 'watermelon']
    


```python
# Insert Items
thislist = ["apple", "banana", "cherry"]
thislist.insert(2, "watermelon")
print(thislist)
```

    ['apple', 'banana', 'watermelon', 'cherry']
    

<p id="Add_List_Items"></p>  

## Add List Items

> [Add List Items](https://www.w3schools.com/python/python_lists_add.asp)


```python
# Append Items
thislist = ["apple", "banana", "cherry"]
thislist.append("orange")
print(thislist)
```

    ['apple', 'banana', 'cherry', 'orange']
    


```python
# Insert Items
thislist = ["apple", "banana", "cherry"]
thislist.insert(1, "orange")
print(thislist)
```

    ['apple', 'orange', 'banana', 'cherry']
    


```python
# Extend List
thislist = ["apple", "banana", "cherry"]
tropical = ["mango", "pineapple", "papaya"]
thislist.extend(tropical)
print(thislist)
```

    ['apple', 'banana', 'cherry', 'mango', 'pineapple', 'papaya']
    


```python
# Add Any Iterable 튜플 리스트 등 인덱싱할 수 있는 것은 다 된다.
thislist = ["apple", "banana", "cherry"]
thistuple = ("kiwi", "orange")
thislist.extend(thistuple)
print(thislist)
```

    ['apple', 'banana', 'cherry', 'kiwi', 'orange']
    

<p id="Remove_List_Items"></p>  

## Remove List Items

> [Remove List Items](https://www.w3schools.com/python/python_lists_remove.asp)


```python
# Remove Specified Item
thislist = ["apple", "banana", "cherry"]
thislist.remove("banana")
print(thislist)
```

    ['apple', 'cherry']
    


```python
# Remove Specified Index
thislist = ["apple", "banana", "cherry"]
thislist.pop(1)
print(thislist)
```

    ['apple', 'cherry']
    


```python
thislist = ["apple", "banana", "cherry"]
thislist.pop()
print(thislist)
```

    ['apple', 'banana']
    


```python
thislist = ["apple", "banana", "cherry"]
del thislist[0]
print(thislist)
```

    ['banana', 'cherry']
    


```python
thislist = ["apple", "banana", "cherry"]
del thislist
print(thislist)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Input In [36], in <cell line: 3>()
          1 thislist = ["apple", "banana", "cherry"]
          2 del thislist
    ----> 3 print(thislist)
    

    NameError: name 'thislist' is not defined



```python
# Clear the List
thislist = ["apple", "banana", "cherry"]
thislist.clear()
print(thislist)
```

    []
    

<p id="Loop_Lists"></p>  

## Loop Lists

> [Loop Lists](https://www.w3schools.com/python/python_lists_loop.asp)


```python
# Loop Through a List
thislist = ["apple", "banana", "cherry"]
for x in thislist:
    print(x)
```

    apple
    banana
    cherry
    


```python
# Loop Through the Index Numbers
thislist = ["apple", "banana", "cherry"]
for i in range(len(thislist)):
    print(thislist[i])
```

    apple
    banana
    cherry
    


```python
# Using a While Loop
thislist = ["apple", "banana", "cherry"]
i = 0 
while i < len(thislist):
    print(thislist[i])
    i = i + 1
```

    apple
    banana
    cherry
    


```python
# Looping Using List Comprehension
thislist = ["apple", "banana", "cherry"]
[print(x) for x in thislist]
```

    apple
    banana
    cherry
    




    [None, None, None]



<p id="List_Comprehension"></p>  

## List Comprehension

> [List Comprehension](https://www.w3schools.com/python/python_lists_comprehension.asp)

- The Syntax

```python
newlist = [expression for item in iterable if condition == True]
```


```python
# List Comprehension
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
newlist = []

for x in fruits:
    if "a" in x:
        newlist.append(x)

print(newlist)
```

    ['apple', 'banana', 'mango']
    


```python
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x for x in fruits if "a" in x]

print(newlist)
```

    ['apple', 'banana', 'mango']
    


```python
# Condition
newlist = [x for x in fruits if x != "apple"]
print(newlist)
```

    ['banana', 'cherry', 'kiwi', 'mango']
    


```python
newlist = [x for x in fruits]
print(newlist)
```

    ['apple', 'banana', 'cherry', 'kiwi', 'mango']
    


```python
# Iterable

newlist = [x for x in range(10)]
print(newlist)
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    


```python
newlist = [x for x in range(10) if x < 5]
print(newlist)
```

    [0, 1, 2, 3, 4]
    


```python
# Expression
newlist = [x.upper() for x in fruits]
print(newlist)
```

    ['APPLE', 'BANANA', 'CHERRY', 'KIWI', 'MANGO']
    


```python
newlist = ['hello' for x in fruits]
print(newlist)
```

    ['hello', 'hello', 'hello', 'hello', 'hello']
    


```python
newlist = [x if x != "banana" else "orange" for x in fruits]
print(newlist)
```

    ['apple', 'orange', 'cherry', 'kiwi', 'mango']
    

<p id="Sort_Lists"></p>  

## Sort Lists

> [Sort Lists](https://www.w3schools.com/python/python_lists_sort.asp)


```python
# Sort List Alphanumerically
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort()
print(thislist)
```

    ['banana', 'kiwi', 'mango', 'orange', 'pineapple']
    


```python
thislist = [100, 50, 65, 82, 23]
thislist.sort()
print(thislist)
```

    [23, 50, 65, 82, 100]
    


```python
# Sort Descending

thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort(reverse = True)
print(thislist)
```

    ['pineapple', 'orange', 'mango', 'kiwi', 'banana']
    


```python
thislist = [100, 50, 65, 82, 23]
thislist.sort(reverse = True)
print(thislist)
```

    [100, 82, 65, 50, 23]
    


```python
# Customize Sort Function
def myfunc(n):
    return abs(n - 50)

thislist = [100, 50, 65, 82, 23]
thislist.sort(key = myfunc)
print(thislist)
```

    [50, 65, 23, 82, 100]
    


```python
# Case Insensitive Sort

thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.sort()
print(thislist)
```

    ['Kiwi', 'Orange', 'banana', 'cherry']
    


```python
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.sort(key = str.lower)
print(thislist)
```

    ['banana', 'cherry', 'Kiwi', 'Orange']
    


```python
# Reverse Order
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.reverse()
print(thislist)
```

    ['cherry', 'Kiwi', 'Orange', 'banana']
    

<p id="Copy_Lists"></p>  

## Copy Lists

> [Copy Lists](https://www.w3schools.com/python/python_lists_copy.asp)


```python
thislist = ["apple", "banana", "cherry"]
mylist = thislist.copy()
print(mylist)
```

    ['apple', 'banana', 'cherry']
    


```python
thislist = ["apple", "banana", "cherry"]
mylist = list(thislist)
print(mylist)
```

    ['apple', 'banana', 'cherry']
    

<p id="Join_Lists"></p>  

## Join Lists

> [Join Lists](https://www.w3schools.com/python/python_lists_join.asp)


```python
# Join Two Lists
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]

list3 = list1 + list2
print(list3)
```

    ['a', 'b', 'c', 1, 2, 3]
    


```python
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

for x in list2:
    list1.append(x)

print(list1)
```

    ['a', 'b', 'c', 1, 2, 3]
    


```python
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

list1.extend(list2)
print(list1)
```

    ['a', 'b', 'c', 1, 2, 3]
    

<p id="List_Methods"></p>  

## List Methods

> [List Methods](https://www.w3schools.com/python/python_lists_methods.asp)


```python
# count()
fruits = ['apple', 'banana', 'cherry']
x = fruits.count("cherry")
print(x)
```

    1
    


```python
# Definition and Usage :   list.count(value)
points = [1, 4, 2, 9, 7, 8, 9, 3, 1]

x = points.count(9)
print(x)
```

    2
    


```python
# index()
fruits = ['apple', 'banana', 'cherry']
x = fruits.index("cherry")
print(x)
```

    2
    


```python
# Definition and Usage :    list.index(elmnt)
fruits = [4, 55, 64, 32, 16, 32]
x = fruits.index(32)
print(x)
```

    3
    

<p id="List_Exercises"></p>  

## List Exercises

> [List Exercises](https://www.w3schools.com/python/python_lists_exercises.asp)
