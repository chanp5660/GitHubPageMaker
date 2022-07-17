---
layout: post
current: post
cover:  assets/built/images/github-logo.png
navigation: True
title: 깃허브블로그(1)-ipynb포스팅 
date: 2022-07-17 02:08:00 +0900
tags: [github]
class: post-template
subclass: 'post tag-python'
author: chanp5660
---

{% include githubblog-table-of-contents.html %}

# 깃허브블로그(1)-ipynb포스팅


>어떤 사람들이 필요한 블로그인가?  
    - ipynb형식 포스팅을 하려고 하는 사람    
    - 기존 준비 : githubio 블로그, jekell 테마 사용하는 사람, ipynb 형식 파일을 만들 수 있는 사람


## ipynb 파일 생성

- jekell 포스팅 형태에서는 ipynb 파일 이름이 yyyy-mm-dd-제목.ipynb 형식으로 저장한다.
- 예를 들어 본 블로그는 "2022-07-16-깃허브블로그(1)-ipynb포스팅.ipynb" 으로 생성한다.

## ipynb to md in jupyterlab  
- githubio 포스팅은 md(markdown)형식으로 포스팅을 해야하므로 ipynb 형식을 md 형식으로 변경해주어야한다.
- jupyter lab에서는 해당 파일을 실행 후 File => Save and Export Notebook As... => Markdown 을 클릭하면 로컬 다운로드에 md 파일로 생성된다.

<img src="https://user-images.githubusercontent.com/46266247/179354050-316fed8c-9080-456b-bc11-11cbe8d462de.png" width="50%"> <img src="https://user-images.githubusercontent.com/46266247/179354094-02898f8f-392b-4c5c-945b-f21b167b91d7.png" width="20%">


## ipybn to md in command, Anaconda Prompt  
- **nbconvert** 는 ipynb(jupyter notebook) 파일 형식을 markdown 파일로 변경할 때 사용할 수 있는 프로그램이다.
- 설치(본인이 설치되는 걸로 아무거나 해도 된다.)
    - pip install nbconvert
    - conda install nbconvert
- jupyter nbconvert --to markdown [ipynb형식 파일 이름]
    - 예시 : jupyter nbconvert --to markdown "2022-07-16-깃허브블로그(1)-ipynb포스팅.ipynb"

- 같은 폴더에 같은 이름으로 md 파일이 생성된다.
