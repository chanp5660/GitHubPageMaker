---
layout: post  
current: post  
cover:  assets/built/images/python-logo.png  
navigation: True  
title: W3school_pythontutorial(4)   
date: 2022-07-27 13:46:00 +0900  
tags: [python]  
class: post-template  
subclass: 'post tag-python'  
author: chanp5660  
---

{% include w3python-table-of-contents.html %}

# W3school_pythontutorial(3)

> **내실 다지기** : [w3school](https://www.w3schools.com/) 사이트에서 python tutorial을 처음부터 끝까지 하는 목표로 시작하는 포스팅으로 제공해주는 목차 순서대로 진행한다. 간단한 내용은 제공해준 예제만 실행해본다. 활용해볼 예제는 추가로 간단한 예제를 만들어 실행하는 코드까지 작성하며 내실을 다진다.



- 주제    
    - <a href="#Booleans">Booleans</a>  
    - <a href="#Operators">Operators</a>  
    - <a href="#Tuples">Tuples</a>  
    - <a href="#If_Else">If Else</a>  
    - <a href="#While_Loops">While Loops</a>  
    - <a href="#For_Loops">For Loops</a>  
    - <a href="#Functions">Functions</a>  
    - <a href="#Lambda">Lambda</a>  

<p href="#Booleans"></p>  

## Booleans  

[Booleans](https://www.w3schools.com/python/python_booleans.asp)


```python
### Boolean Values
print(10 > 9)
print(10 == 9)
print(10 < 9)
```

    True
    False
    False
    


```python
a = 200
b = 33

if b > a:
    print("b is greater than a")
else:
    print("b is not greater than a")
```

    b is not greater than a
    


```python
# Evaluate Values and Variables 값은 0을 제외하고는 다 True 이다
print(bool("Hello"))
print(bool(15))
```

    True
    True
    


```python
x = "Hello"
y = 15

print(bool(x))
print(bool(y))
```

    True
    True
    


```python
# Most Values are True
print(bool("abc"))
print(bool(123))
print(bool(["apple", "cherry", "banana"]))
```

    True
    True
    True
    


```python
# Some Values are False
print(bool(False))
print(bool(None))
print(bool(0))
print(bool(""))
print(bool(()))
print(bool([]))
print(bool({}))
```

    False
    False
    False
    False
    False
    False
    False
    


```python
class myclass():
    def __len__(self):
        return 0

myobj = myclass()
print(bool(myobj))
```

    False
    


```python
# Functions can Return a Boolean
def myFunction() :
    return True

print(myFunction())
```

    True
    


```python
def myFunction() :
    return True

if myFunction():
    print("YES!")
else:
    print("NO!")
```

    YES!
    


```python
x = 200
print(isinstance(x, int))
```

    True
    

<p href="#Operators"></p>  

## Operators  

[Operators](https://www.w3schools.com/python/python_operators.asp)

### Operators_산술 연산자

- 산술 연산자는 일반적인 수학 연산을 수행하기 위해 숫자 값과 함께 사용됩니다.

<img src="https://user-images.githubusercontent.com/46266247/181168361-0770a0e0-6f83-466c-a9b6-bac8e4668da3.png" width="50%">


```python
print(10 + 5)
```

    15
    


```python
print(10-5)
```

    5
    


```python
print(10*5)
```

    50
    


```python
print(10/5) # 나누기 float 형으로 나온다.
```

    2.0
    


```python
print(10%5) # 나머지
```

    0
    


```python
print(10**5) # 제곱수
```

    100000
    


```python
print(10//3) # 3.9 결과를 가장 가까운 정수로 (내림)
```

    3
    

### Operators_할당 연산자

- 할당 연산자는 변수에 값을 할당하는 데 사용됩니다.

<img src="https://user-images.githubusercontent.com/46266247/181168641-7415b27a-26b4-4d1f-b55a-dac93646832e.png" width="60%">


```python
x = 5;print(x)
```

    5
    


```python
x = 5
x += 3;print(x)
```

    8
    


```python
x = 5
x -= 3;print(x)
```

    2
    


```python
x = 5
x *= 3;print(x)
```

    15
    


```python
x = 5
x /= 3;print(x)
```

    1.6666666666666667
    


```python
x = 5
x %= 3;print(x)
```

    2
    


```python
x = 5
x //= 3;print(x)
```

    1
    


```python
x = 5 
x **= 3;print(x)
```

    125
    


```python
# 비트별 논리곱(Bitwise And)
x = 5 
x &= 3;print(x)
```

    1
    


```python
# 비트별 논리합(Bitwise Or) or_(a, b)
x = 5 
x |= 3;print(x)
```

    7
    


```python
# 비트별 배타적 논리합(Bitwise Exclusive Or) 잘 쓰지 않는다.
x = 5
x ^= 3;print(x)
```

    6
    


```python
# 비트 이동
x = 25
x >>= 3;print(x)
```

    3
    


```python
x = 5
x <<= 3;print(x)
```

    40
    

### Operators_비교 연산자

<img src="https://user-images.githubusercontent.com/46266247/181172299-3cdd9e3c-f005-4186-9108-b8c0fbcf4313.png" width="60%">


```python
x, y = 3,5
```


```python
x == y
```




    False




```python
x != y
```




    True




```python
x > y
```




    False




```python
x < y
```




    True




```python
x >= y
```




    False




```python
x <= y
```




    True



### Operators_논리 연산자

- 논리 연산자는 조건문을 결합하는 데 사용됩니다.

<img src="https://user-images.githubusercontent.com/46266247/181172968-c7c4d075-dc37-44f4-beeb-0ba07f202036.png" width="60%">


```python
x = 5
print(x > 3 and x < 10)
```

    True
    


```python
x = 5
print(x > 3 or x < 4)
```

    True
    


```python
x = 5
print(not(x > 3 and x < 10))
```

    False
    

### Operators_Identity Operators

- Identity Operators는 객체를 비교하는 데 사용됩니다. 동일한 경우가 아니라 실제로 동일한 객체이고 동일한 메모리 위치를 사용하는 경우입니다.

<img src="https://user-images.githubusercontent.com/46266247/181174165-2b00eac9-023f-400a-96de-08e291355280.png" width="70%">


```python
x = ["apple", "banana"]
y = ["apple", "banana"]
z = x
```


```python
print(x is z)
```

    True
    


```python
print(x is y)
```

    False
    


```python
print(x == y)
```

    True
    

### Operators_Membership Operators

- Membership 연산자는 시퀀스가 개체에 표시되는지 테스트하는 데 사용됩니다.

<img src="https://user-images.githubusercontent.com/46266247/181174432-1413e08a-07db-4433-9f01-aba499f6542b.png" width="70%">


```python
x = ["apple", "banana"]
print("banana" in x)
```

    True
    


```python
x = ["apple", "banana"]
print("pineapple" not in x)
```

    True
    

### Operators_Bitwise Operators

- 비트 연산자는 (이진) 숫자를 비교하는 데 사용됩니다. 잘 사용되진 않는다.

<img src="https://user-images.githubusercontent.com/46266247/181174840-ac3f368d-e499-4b02-8725-1f18bc4235f0.png" width="70%">

<p href="#If_Else"></p>  

## If Else  

[If Else](https://www.w3schools.com/python/python_conditions.asp)

<p href="#While_Loops"></p>  

## While_Loops 

[While Loops](https://www.w3schools.com/python/python_while_loops.asp)

<p href="#For_Loops"></p>  

## For_Loops  

[For Loops](https://www.w3schools.com/python/python_for_loops.asp)

<p href="#Functions"></p>  

## Functions  

[Functions](https://www.w3schools.com/python/python_functions.asp)

<p href="#Lambda"></p>  

## Lambda  

[Lambda](https://www.w3schools.com/python/python_lambda.asp)

<p id="check1"></p>

## Booleans  

> [Python Booleans](https://www.w3schools.com/python/python_booleans.asp)
