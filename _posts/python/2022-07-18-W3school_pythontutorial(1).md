---
layout: post  
current: post  
cover:  assets/built/images/python-logo.png  
navigation: True  
title: W3school_pythontutorial(1)   
date: 2022-07-18 20:00:00 +0900  
tags: [python]  
class: post-template  
subclass: 'post tag-python'  
author: chanp5660  
---

{% include w3python-table-of-contents.html %}

# W3school_pythontutorial(1)

> **내실 다지기** : [w3school](https://www.w3schools.com/) 사이트에서 python tutorial을 처음부터 끝까지 하는 목표로 시작하는 포스팅으로 제공해주는 목차 순서대로 진행한다. 간단한 내용은 제공해준 예제만 실행해본다. 활용해볼 예제는 추가로 간단한 예제를 만들어 실행하는 코드까지 작성하며 내실을 다진다.



- 주제
    - [Introduction](#Introduction)
    - [Getting Started](#Getting-Started)
    - [Syntax](#Syntax)
    - [Comments](#Comments)
    - [Variables](#Variables)([Variables](#Variables), [Variable Names](#Variable-Names), [Assign Multiple Values](#Assign-Multiple-Values), [Output Variables](#Output-Variables), [Global Variables](#Global-Variables), [Variable Exercises](#Variable-Exercises))
    - [Data Types](#Data-Types)
    - [Numbers](#Numbers)
    - [Casting](#Casting)
    - [Strings](#Strings)

## Introduction  

> [python Introduction](https://www.w3schools.com/python/python_intro.asp)


## Getting Started  

> [Python Getting Started](https://www.w3schools.com/python/python_getstarted.asp)


```python
print("Hello, World")
```

    Hello, World
    

## Syntax  

> [Python Syntax](https://www.w3schools.com/python/python_syntax.asp)


```python
# indentation 들여쓰기
if 5 > 2:
    print("Five is greater than two!")
```

    Five is greater than two!
    


```python
x = 5
y = "Hello, World!"
```

## Comments  

> [Python Comments](https://www.w3schools.com/python/python_comments.asp)


```python
#This is a comment
#written in
#more than just one line
print("Hello, World!")
```

    Hello, World!
    


```python
"""
This is a comment
written in
more than just one line
"""
print("Hello, World!")
```

    Hello, World!
    

## Variables  

> [Python Variables](https://www.w3schools.com/python/python_variables.asp)


```python
x = 5
y = "John"
print(x)
print(y)
```

    5
    John
    


```python
x = 4       # x is of type int
x = "Sally" # x is now of type str
print(x)
```

    Sally
    


```python
#casting
x = str(3)    # x will be '3'
y = int(3)    # y will be 3
z = float(3)  # z will be 3.0
```


```python
x = 5
y = "John"
print(type(x))
print(type(y))
```

    <class 'int'>
    <class 'str'>
    


```python
x = "John"
# is the same as
x = 'John'
```


```python
a = 4
A = "Sally"
#A will not overwrite a
```

### Variable Names  

> [Python - Variable Names](https://www.w3schools.com/python/python_variables_names.asp)

- 다중 단어에 대한 팁 3가지  

    - Camel Case
        ```python
        myVariableName = "John"
        ```  
        
    - Pascal Case
        ```python
        MyVariableName = "John"
        ```  
        
    - Snake Case
        ```python
        my_variable_name = "John"
        ```

### Assign Multiple Values  

> [Python Variables - Assign Multiple Values](https://www.w3schools.com/python/python_variables_multiple.asp)


```python
# 여러 변수에 여러 값
x, y, z = "Orange", "Banana", "Cherry"
print(x)
print(y)
print(z)
```

    Orange
    Banana
    Cherry
    


```python
# 여러 변수에 하나의 값
x = y = z = "Orange"
print(x)
print(y)
print(z)
```

    Orange
    Orange
    Orange
    


```python
# 집합 풀기
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits
print(x)
print(y)
print(z)
```

    apple
    banana
    cherry
    

### Output Variables

> [Python - Output Variables](https://www.w3schools.com/python/python_variables_output.asp)


```python
x = "Python is awesome"
print(x)
```

    Python is awesome
    


```python
x = "Python"
y = "is"
z = "awesome"
print(x, y, z)
```

    Python is awesome
    


```python
# 텍스트 합
x = "Python "
y = "is "
z = "awesome"
print(x + y + z)
```

    Python is awesome
    


```python
# 숫자 합(텍스트, 숫자 혼합은 안됨)
x = 5
y = 10
print(x + y)
```

    15
    

### Global Variables

> [Python - Global Variables](https://www.w3schools.com/python/python_variables_global.asp)


```python
x = "awesome" # 전역 변수

def myfunc():
    print("Python is " + x)

myfunc()
```

    Python is awesome
    


```python
x = "awesome" # 전역변수

def myfunc():
  x = "fantastic" # 지역변수
  print("Python is " + x)

myfunc()

print("Python is " + x)
```

    Python is fantastic
    Python is awesome
    


```python
# 함수 내에서 전역변수 생성
def myfunc():
    global x
    x = "fantastic"

myfunc()

print("Python is " + x)
```

    Python is fantastic
    


```python
x = "awesome"

def myfunc():
    global x
    x = "fantastic"

myfunc()

print("Python is " + x)
```

    Python is fantastic
    

### Variable Exercises  

> [Python - Variable Exercises](https://www.w3schools.com/python/python_variables_exercises.asp)  
[예제사이트](https://www.w3schools.com/python/exercise.asp?filename=exercise_variables1)


```python
# 1
carname = "Volve"
# 2
x=50
# 3
x=5
y=10
print(x+y)
```

    15
    


```python
# 4
x = 5
y = 10
z = x + y
print(z)
```

    15
    


```python
# 5 변수명 수정 
# 2my-first_name = "John"
myfirst_name = "John"
```


```python
# 6
x = y = z = "Orange"
```


```python
# 7
def myfunc():
    global x
    x = "fantastic"
myfunc()
```

## Data Types  

> [Python Data Types](https://www.w3schools.com/python/python_datatypes.asp)

Text Type : **str**  
Numeric Types : **int, float, complex**  
Sequence Types : **list, tuple, range**  
Mapping Type : **dict**  
Set Types : **set, frozenset**   
Boolean Type : **bool**  
Binary Types : **bytes, bytearray, memoryview**  
None Type : **NoneType**  


```python
x = 5
print(type(x))
```

    <class 'int'>
    

- Example Data Type  
x = "Hello World" **# str**  
x = 20 **# int**   
x = 20.5 **# float**   
x = 1j **# complex**    
x = ["apple", "banana", "cherry"] **# list**  
x = ("apple", "banana", "cherry")  **# tuple**  
x = range(6) **# range**  
x = {"name" : "John", "age" : 36} **# dict**  
x = {"apple", "banana", "cherry"} **# set**  
x = frozenset({"apple", "banana", "cherry"}) **# frozenset**  
x = True  **# bool**  
x = b"Hello" **# bytes**  
x = bytearray(5) **# bytearray**  
x = memoryview(bytes(5)) **# memoryview**  
x = None **# NoneType**  

## Numbers

> [Python Numbers](https://www.w3schools.com/python/python_numbers.asp)

int  
float  
complex  


```python
x = 1    # int
y = 2.8  # float
z = 1j   # complex
print(type(x))
print(type(y))
print(type(z))
```

    <class 'int'>
    <class 'float'>
    <class 'complex'>
    


```python
# int
x = 1
y = 35656222554887711
z = -3255522

print(type(x))
print(type(y))
print(type(z))
```

    <class 'int'>
    <class 'int'>
    <class 'int'>
    


```python
# float

x = 1.10
y = 1.0
z = -35.59

print(type(x))
print(type(y))
print(type(z))
```

    <class 'float'>
    <class 'float'>
    <class 'float'>
    


```python
# E 지수
x = 35e3
y = 12E4
z = -87.7e100

print(type(x))
print(type(y))
print(type(z))
```

    <class 'float'>
    <class 'float'>
    <class 'float'>
    


```python
# complex
x = 3+5j
y = 5j
z = -5j

print(type(x))
print(type(y))
print(type(z))
```

    <class 'complex'>
    <class 'complex'>
    <class 'complex'>
    


```python
### type conversion
x = 1    # int
y = 2.8  # float
z = 1j   # complex

#convert from int to float:
a = float(x)

#convert from float to int:
b = int(y)

#convert from int to complex:
c = complex(x)

print(a)
print(b)
print(c)

print(type(a))
print(type(b))
print(type(c))
```

    1.0
    2
    (1+0j)
    <class 'float'>
    <class 'int'>
    <class 'complex'>
    

### Random Number


```python
import random

print(random.randrange(1,10))
```

    7
    

## Casting  

> [Python Casting](https://www.w3schools.com/python/python_casting.asp) = 형변환


```python
x = int(1)   # x will be 1
y = int(2.8) # y will be 2
z = int("3") # z will be 3
print(x,y,z)
```

    1 2 3
    


```python
x = float(1)     # x will be 1.0
y = float(2.8)   # y will be 2.8
z = float("3")   # z will be 3.0
w = float("4.2") # w will be 4.2
print(x,y,z,w)
```

    1.0 2.8 3.0 4.2
    


```python
x = str("s1") # x will be 's1'
y = str(2)    # y will be '2'
z = str(3.0)  # z will be '3.0'
print(x,y,z)
```

    s1 2 3.0
    

## Strings

> [Python Strings](https://www.w3schools.com/python/python_strings.asp)


```python
print("Hello")
print('Hello')
```

    Hello
    Hello
    


```python
a = "Hello"
print(a)
```

    Hello
    


```python
a = """Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."""
print(a)
```

    Lorem ipsum dolor sit amet,
    consectetur adipiscing elit,
    sed do eiusmod tempor incididunt
    ut labore et dolore magna aliqua.
    


```python
a = '''Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua.'''
print(a)
```

    Lorem ipsum dolor sit amet,
    consectetur adipiscing elit,
    sed do eiusmod tempor incididunt
    ut labore et dolore magna aliqua.
    


```python
# string array
a = "Hello, World!"
print(a[1])
```

    e
    


```python
# looping Through a String
for x in "banana":
    print(x)
```

    b
    a
    n
    a
    n
    a
    


```python
# string length
a = "Hello, World!"
print(len(a))
```

    13
    


```python
# check string
txt = "The best things in life are free!"
print("free" in txt)
```

    True
    


```python
txt = "The best things in life are free!"
if "free" in txt:
    print("Yes, 'free' is present.")
```

    Yes, 'free' is present.
    


```python
# check if not
txt = "The best things in life are free!"
print("expensive" not in txt)
```

    True
    


```python
txt = "The best things in life are free!"
if "expensive" not in txt:
    print("No, 'expensive' is NOT present.")
```

    No, 'expensive' is NOT present.
    

### Slicing Strings
> [Python - Slicing Strings](https://www.w3schools.com/python/python_strings_slicing.asp)  


```python
b = "Hello, World!"
print(b[2:5])
```

    llo
    


```python
b = "Hello, World!"
print(b[:5])
```

    Hello
    


```python
b = "Hello, World!"
print(b[2:])
```

    llo, World!
    


```python
b = "Hello, World!"
print(b[-5:-2])
```

    orl
    

### Modify Strings

> [Python - Modify Strings](https://www.w3schools.com/python/python_strings_modify.asp)


```python
# upper case
a = "Hello, World!"
print(a.upper())
```

    HELLO, WORLD!
    


```python
# lower case
a = "Hello, World!"
print(a.lower())
```

    hello, world!
    


```python
# Remove Whitespace
a = " Hello, World! "
print(a.strip()) # returns "Hello, World!"
```

    Hello, World!
    


```python
# Replace String
a = "Hello, World!"
print(a.replace("H", "J"))
```

    Jello, World!
    


```python
# split string
a = "Hello, World!"
print(a.split(",")) # returns ['Hello', ' World!']
```

    ['Hello', ' World!']
    

### String Concatenation

> [Python - String Concatenation](https://www.w3schools.com/python/python_strings_concatenate.asp)  


```python
a = "Hello"
b = "World"
c = a + b
print(c)
```

    HelloWorld
    


```python
a = "Hello"
b = "World"
c = a + " " + b
print(c)
```

    Hello World
    

### Format - Strings

> [Python - Format - Strings](https://www.w3schools.com/python/python_strings_format.asp)

개인적으로 python3 부터 String format 부분은 [f-string](https://blockdmask.tistory.com/429)을 사용하여 하는게 가독성도 좋고 이해하기 좋다.
"", '' 문자열 앞에 f를 붙여주고 문자열 내에 {} 사이에 변수 이름을 적어주면 된다. ( 인덱싱으로도 표시할 수 있다. )


```python
String1 = "가"
String2 = "나"
String3 = "다"
Int1 = 1
Int2 = 2
Int3 = 3

print(f"한국어의 시작은 {String1}, {String2}, {String3} ... , 숫자의 시작은 {Int1}, {Int2}, {Int3} ...")
```

    한국어의 시작은 가, 나, 다 ... , 숫자의 시작은 1, 2, 3 ...
    

### Escape Characters

> [Python - Escape Characters](https://www.w3schools.com/python/python_strings_escape.asp)  

Code &nbsp;&nbsp;&nbsp;&nbsp; Result  
\\' &nbsp;&nbsp;&nbsp;&nbsp; **Single Quote**  
\\\ &nbsp;&nbsp;&nbsp;&nbsp; **Backslash**  
\\n &nbsp;&nbsp;&nbsp;&nbsp; **New Line**  
\\r &nbsp;&nbsp;&nbsp;&nbsp; **Carriage Return**  
\\t &nbsp;&nbsp;&nbsp;&nbsp; **Tab**  
\\b &nbsp;&nbsp;&nbsp;&nbsp; **Backspace**  
\\f &nbsp;&nbsp;&nbsp;&nbsp; **Form Feed**  
\\ooo &nbsp;&nbsp;&nbsp;&nbsp; **Octal value**  
\\xhh &nbsp;&nbsp;&nbsp;&nbsp; **Hex value**


```python
# " ' 를 문자열 안에 포함시키는 방법 
txt = "We are the so-called \"Vikings\" from the north."
print(txt)
```

    We are the so-called "Vikings" from the north.
    

### String Methods

> [Python - String Methods](https://www.w3schools.com/python/python_strings_methods.asp) 내실 다지기 이므로 모든 함수를 실행해본다.


```python
# capitalize() 문자열의 첫 단어를 대문자로 바꾼다.
txt = "hello, and welcome to my world."

x = txt.capitalize()

print (x)
```

    Hello, and welcome to my world.
    


```python
# casefold() 문자열을 소문자로 바꾸어주는 함수인데 lower()보다 더 공격적이다. [예시로 독일어 casefold()는'ß'를"ss"로 변환](https://www.delftstack.com/ko/howto/python/case-insensitive-string-comparison-in-python/)
txt = "Hello, And Welcome To My World!"

x = txt.casefold()

print(x)
```

    hello, and welcome to my world!
    


```python
# center() 문자열의 20칸을 빈칸으로 채우고 중간정렬로 설정한다.

txt = "banana"

x = txt.center(20)

print(x)
```

           banana       
    


```python
txt = "banana"

x = txt.center(20, "O")

print(x)
```

    OOOOOOObananaOOOOOOO
    


```python
# string.count(value, start, end) 해당 문자열에서 특정 단어가 몇개 있는지 확인할 수 있는 함수
txt = "I love apples, apple are my favorite fruit"

x = txt.count("apple")

print(x)
```

    2
    


```python
txt = "I love apples, apple are my favorite fruit"

x = txt.count("apple", 10, 24)

print(x)
```

    1
    


```python
# string.encode(encoding=encoding, errors=errors) Default is UTF-8 문자열을 인코딩 한다.

txt = "My name is Ståle"

x = txt.encode()

print(x)
```

    b'My name is St\xc3\xa5le'
    


```python
txt = "My name is Ståle"

print(txt.encode(encoding="ascii",errors="backslashreplace"))
print(txt.encode(encoding="ascii",errors="ignore"))
print(txt.encode(encoding="ascii",errors="namereplace"))
print(txt.encode(encoding="ascii",errors="replace"))
print(txt.encode(encoding="ascii",errors="xmlcharrefreplace"))
```

    b'My name is St\\xe5le'
    b'My name is Stle'
    b'My name is St\\N{LATIN SMALL LETTER A WITH RING ABOVE}le'
    b'My name is St?le'
    b'My name is St&#229;le'
    


```python
# string.endswith(value, start, end)  문자열이 지정된 값으로 끝나면 True를 반환하고 그렇지 않으면 False를 반환합니다.

txt = "Hello, welcome to my world."

x = txt.endswith(".")

print(x)
```

    True
    


```python
txt = "Hello, welcome to my world."

x = txt.endswith("my world.")

print(x)
```

    True
    


```python
txt = "Hello, welcome to my world."

x = txt.endswith("my world.", 5, 11)

print(x)
```

    False
    


```python
# string.expandtabs(tabsize)  탭의 크기를 조절해준다.
txt = "H\te\tl\tl\to"

x =  txt.expandtabs(2)

print(x)
```

    H e l l o
    


```python
txt = "H\te\tl\tl\to"

print(txt)
print(txt.expandtabs())
print(txt.expandtabs(2))
print(txt.expandtabs(4))
print(txt.expandtabs(10))
```

    H	e	l	l	o
    H       e       l       l       o
    H e l l o
    H   e   l   l   o
    H         e         l         l         o
    


```python
# string.find(value, start, end) 특정 문자열이 어디 있는지 확인, 오류시 -1 출력

txt = "Hello, welcome to my world."

x = txt.find("welcome")

print(x)
```

    7
    


```python
# string.index(value, start, end) 특정 문자열이 어디 있는지 확인, 오류시 에러 출력

txt = "Hello, welcome to my world."

x = txt.index("e")

print(x)
```

    1
    


```python
txt = "Hello, welcome to my world."

print(txt.find("q"))
print(txt.index("q"))
```

    -1
    


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Input In [63], in <cell line: 4>()
          1 txt = "Hello, welcome to my world."
          3 print(txt.find("q"))
    ----> 4 print(txt.index("q"))
    

    ValueError: substring not found



```python
# string.format(value1, value2...) 양이 많으므로 따로 블로그에 추가할 함수
```


```python
# string.isalnum() 문자열이 숫자와 알파벳으로만 이루어졌는지 확인하는 함수

txt = "Company12"

x = txt.isalnum()

print(x)
```

    True
    


```python
txt = "Company 12" # 빈칸이 들어가 있어서 False

x = txt.isalnum()

print(x)
```

    False
    


```python
# string.isalpha() # 알파벳으로 이루어져있는지 확인

txt = "CompanyX"

x = txt.isalpha()

print(x)
```

    True
    


```python
txt = "Company10"

x = txt.isalpha()

print(x)
```

    False
    


```python
# string.isdecimal() # 유니코드 문자열에서만 사용되며 모든 문자가 소수(0-9)이면 True를 반환합니다.
txt = "\u0033" #unicode for 3

x = txt.isdecimal()

print(x)
```

    True
    


```python
a = "\u0030" #unicode for 0
b = "\u0047" #unicode for G

print(a.isdecimal())
print(b.isdecimal())
```

    True
    False
    


```python
# string.isdigit() # 숫자인지 확인
txt = "50800"

x = txt.isdigit()

print(x)
```

    True
    


```python
a = "\u0030" #unicode for 0
b = "\u00B2" #unicode for ²

print(a.isdigit())
print(b.isdigit())
```

    True
    True
    


```python
# string.isidentifier() 문자열이 유효한 식별자이면 True를 반환하고 그렇지 않으면 False를 반환
# 유효한 식별자 영숫자(az) 및 (0-9) 또는 밑줄(_)만 포함하는 경우 유효한 식별자, 숫자로 시작하거나 공백을 포함할 수 없습니다.

txt = "Demo"

x = txt.isidentifier()

print(x)
```

    True
    


```python
a = "MyFolder"
b = "Demo002"
c = "2bring"
d = "my demo"

print(a.isidentifier())
print(b.isidentifier())
print(c.isidentifier())
print(d.isidentifier())
```

    True
    True
    False
    False
    


```python
# string.islower() 알파벳 문자열을 소문자로 바꾸어준다.

txt = "hello world!"

x = txt.islower()

print(x)
```

    True
    


```python
a = "Hello world!"
b = "hello 123"
c = "mynameisPeter"

print(a.islower())
print(b.islower())
print(c.islower())
```

    False
    True
    False
    


```python
# string.isnumeric() 숫자로만 이루어져있는지, 음수 소수도 안된다.
txt = "565543"

x = txt.isnumeric()

print(x)
```

    True
    


```python
a = "\u0030" #unicode for 0
b = "\u00B2" #unicode for &sup2;
c = "10km2"
d = "-1"
e = "1.5"

print(a.isnumeric())
print(b.isnumeric())
print(c.isnumeric())
print(d.isnumeric())
print(e.isnumeric())
```

    True
    True
    False
    False
    False
    


```python

```
