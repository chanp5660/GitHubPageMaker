---
layout: post  
current: post  
cover:  assets/built/images/python-logo.png  
navigation: True  
title: W3school_pythontutorial(2)-String_Methods  
date: 2022-07-20 12:00:00 +0900  
tags: [python]  
class: post-template  
subclass: 'post tag-python'  
author: chanp5660  
---

{% include w3python-table-of-contents.html %}

# W3school_pythontutorial(2)-String_Methods

> **내실 다지기** : [w3school](https://www.w3schools.com/) 사이트에서 python tutorial을 처음부터 끝까지 하는 목표로 시작하는 포스팅으로 제공해주는 목차 순서대로 진행한다. 간단한 내용은 제공해준 예제만 실행해본다. 활용해볼 예제는 추가로 간단한 예제를 만들어 실행하는 코드까지 작성하며 내실을 다진다.



- String_Methods
    - <a href="#capitalize">capitalize</a>  
    - <a href="#casefold">casefold</a>  
    - <a href="#center">center</a>
    - <a href="#count">count</a>
    - <a href="#encode">encode</a>
    - <a href="#endswith">endswith</a>
    - <a href="#expandtabs">expandtabs</a>
    - <a href="#find">find</a>
    - <a href="#format">format</a>
    - <a href="#index">index</a>
    - <a href="#isalnum">isalnum</a>
    - <a href="#isalpha">isalpha</a>
    - <a href="#isdecimal">isdecimal</a>
    - <a href="#isdigit">isdigit</a>
    - <a href="#isidentifier">isidentifier</a>
    - <a href="#islower">islower</a>
    - <a href="#isnumeric">isnumeric</a>   -- 여기까지 완성
    - <a href="#isprintable">isprintable</a>
    - <a href="#isspace">isspace</a>
    - <a href="#istitle">istitle</a>
    - <a href="#isupper">isupper</a>
    - <a href="#join">join</a>
    - <a href="#ljust">ljust</a>
    - <a href="#lower">lower</a>
    - <a href="#lstrip">lstrip</a>
    - <a href="#maketrans">maketrans</a>
    - <a href="#partition">partition</a>
    - <a href="#replace">replace</a>
    - <a href="#rfind">rfind</a>
    - <a href="#rindex">rindex</a>
    - <a href="#rjust">rjust</a>
    - <a href="#rpartition">rpartition</a>
    - <a href="#rsplit">rsplit</a>
    - <a href="#rstrip">rstrip</a>
    - <a href="#split">split</a>
    - <a href="#splitlines">splitlines</a>
    - <a href="#startswith">startswith</a>
    - <a href="#strip">strip</a>
    - <a href="#swapcase">swapcase</a>
    - <a href="#title">title</a>
    - <a href="#translate">translate</a>
    - <a href="#upper">upper</a>
    - <a href="#zfill">zfill</a>

<p id="String_Methods"></p>

## String Methods

> [Python - String Methods](https://www.w3schools.com/python/python_strings_methods.asp) 내실 다지기 이므로 모든 함수를 실행해본다.


<p id="capitalize"></p>

## string.capitalize()

- 문자열의 첫 단어를 대문자로 바꾼다.


```python
txt = "hello, and welcome to my world."

x = txt.capitalize()

print (x)
```

    Hello, and welcome to my world.
    

<p id="casefold"></p>

## string.casefold()

- 문자열을 소문자로 바꾸어주는 함수인데 lower()보다 더 공격적이다. [예시로 독일어 casefold()는'ß'를"ss"로 변환](https://www.delftstack.com/ko/howto/python/case-insensitive-string-comparison-in-python/)


```python
txt = "Hello, And Welcome To My World!"

x = txt.casefold()

print(x)
```

    hello, and welcome to my world!
    

<p id="center"></p>

## string.center(length, character)

- 문자열을 소문자로 바꾸어주는 함수인데 lower()보다 더 공격적이다. [예시로 독일어 casefold()는'ß'를"ss"로 변환](https://www.delftstack.com/ko/howto/python/case-insensitive-string-comparison-in-python/)


```python
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
    

<p id="count"></p>

## string.count(value, start, end)

- 해당 문자열에서 특정 단어가 몇개 있는지 확인할 수 있는 함수


```python
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
    

<p id="encode"></p>

## string.encode(encoding=encoding, errors=errors)

- Default is UTF-8 문자열을 인코딩 한다.


```python
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
    

<p id="endswith"></p>

## string.endswith(value, start, end)

- 문자열이 지정된 값으로 끝나면 True를 반환하고 그렇지 않으면 False를 반환합니다.


```python
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
    

<p id="expandtabs"></p>

## string.expandtabs(tabsize)

- 탭의 크기를 조절해준다.


```python
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
    

<p id="find"></p>

## string.find(value, start, end)

- 특정 문자열이 어디 있는지 확인, 오류시 -1 출력


```python
txt = "Hello, welcome to my world."

x = txt.find("welcome")

print(x)
```

    7
    

<p id="index"></p>

## string.index(value, start, end)

- 특정 문자열이 어디 있는지 확인, 오류시 에러 출력


```python
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


<p id="format"></p>

## string.format(value1, value2...)

- 양이 많으므로 따로 추후 블로그에 다룬다.

<p id="isalnum"></p>

## string.isalnum()

- 문자열이 숫자와 알파벳으로만 이루어졌는지 확인하는 함수


```python
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
    

<p id="isalpha"></p>

## string.isalpha()

- 알파벳으로 이루어져있는지 확인


```python
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
    

<p id="isdecimal"></p>

## string.isdecimal()

- 유니코드 문자열에서만 사용되며 모든 문자가 소수(0-9)이면 True를 반환합니다.


```python
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
    

<p id="isdigit"></p>

## string.isdigit()

- 숫자인지 확인


```python
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
    

<p id="isidentifier"></p>

## string.isidentifier()

- 문자열이 유효한 식별자이면 True를 반환하고 그렇지 않으면 False를 반환
- 유효한 식별자 영숫자(az) 및 (0-9) 또는 밑줄(_)만 포함하는 경우 유효한 식별자, 숫자로 시작하거나 공백을 포함할 수 없습니다.


```python
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
    

<p id="islower"></p>

## string.islower()

- 알파벳 문자열을 소문자로 바꾸어준다.


```python
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
    

<p id="isloisnumericwer"></p>

## string.isnumeric()

- 숫자로만 이루어져있는지, 음수 소수도 안된다.


```python
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
    
