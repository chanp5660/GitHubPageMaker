---  
layout: post  
current: post  
cover:  assets/built/images/github-logo.png  
navigation: True  
title: 깃허브 ipynb 업로드 방법   
date: 2022-07-07 02:08:00 +0900  
tags: [github]  
class: post-template   
subclass: 'post tag-python'  
author: chanp5660   
---  

{% include githubblog-table-of-contents.html %}  

# 깃허브 ipynb 업로드 방법

**가정**
- Git 아이디가 생성
- 저장소 하나이상 생성
- 아나콘다 가상환경 및 jupyter lab, Git 설치

## 1. 깃허브 사이트에서 연동할 주소를 가져오기

- 아래 사진에서 HTTPs 버튼 클릭 후 오른쪽에 있는 복사 버튼을 클릭하면 URL이 복사가 됨

![image](https://user-images.githubusercontent.com/46266247/177748644-6bfc159a-777c-495d-aa2d-4e31037245f9.png)


* 추가 참조 (https://www.lainyzine.com/ko/article/how-to-link-github-remote-repository-and-local-git-repository/)

## 2. 변경하거나 추가하는 방법

- 반복된 업데이트 명령어(컴퓨터 -> git) 
    - 하루 처음 명령어
        - init : git init
        - branch : git branch -m main
    - 계속 반복적으로 작성해주어야 하는 명령어
        - add : git add -A
        - commit : git commit -m "저장할 메시지"
        - push : git push origin master
- 반복된 업데이트 명령어(git -> 컴퓨터)
    - pull : git pull

* 추가 참조 (https://www.lainyzine.com/ko/article/how-to-link-github-remote-repository-and-local-git-repository/)

## 3. ipynb 을 업로드 하는 방법

- 검색해봤지만 기존 파일로 바로 업로드 하는 방법을 찾지 못함
- jupyter lab 에서 markdown 파일로 저장 후 _posts 에 저장해서 업로드 함

## 4. 이미지 파일 업로드 

- 따로 업로드가 안되기 때문에 git의 issue를 이용하거나 이미지 폴더를 이용해서 연결함

## 5. 카테고리 설정 방법

참조(https://ansohxxn.github.io/blog/jekyll-directory-structure/)


```python

```
