---  
layout: post  
current: post  
cover:  assets/built/images/exitem-logo.png  
navigation: True  
title: Octoparse 를 사용한 크롤링     
date: 2019-05-10 00:30:00 +0900  
tags: [exitem]  
class: post-template  
subclass: 'post tag-python'  
author: chanp5660  
---  
 

# Octoparse 를 사용한 크롤링

굉장히 간단한 예제로서 흐름만 잡아주는 정도의 도움이 될 것이다.
나머지는 프로그램화면에 뜨는 [Action Tips]부분에서 많은 도움을 얻었습니다.

## 설치 방법

### 1. 공식사이트에서 [다운로드](https://www.octoparse.com/download)
### 2. 알집 압출풀고 빨간네모 실행

![압축풀기](https://user-images.githubusercontent.com/46266247/57507069-a4196000-7338-11e9-8d59-e0c4b8390efc.png)

### 3. 바탕화면에 생기는 Octoparse 아이콘을 실행

![첫 실행화면](https://user-images.githubusercontent.com/46266247/57507345-74b72300-7339-11e9-9375-481e3840c1bb.png)

## 실습예제 

목적 : 메이플스토리의 모든 아이템의 리스트를 얻고 싶다.

### 1. Advanced Mode의 [+task] .

### 2. 그럼 화면에  Website의 URL을 입력할 수 있게 되어 있는데 http://maple.inven.co.kr/dataninfo/item/list.php?class2=101 를 입력해본다. Save URL 클릭

![URL입력](https://user-images.githubusercontent.com/46266247/57515159-f2385e80-734c-11e9-9d69-b924ea1bf0db.png)

#### 실행화면 도움말

- 1번 화면은 실제로 돌아가는 코드를 시각화로 보여준다.
- 2번 사용자가 하는 행동의 정보들을 알려준다.(여러가지라서 한가지로 정하기 힘들다.)
- 3번 실제 사용자가 클릭이나 행동을 화면을 통해서 할 수 있다.
> 3번 부분에서 Action Tips이 행동을 할때 어떤 것을 할 수 있는지 도움을 준다. 1번을 바로 하기에는 힘들다. 3번에서 클릭을 통해서 많이 해본 다음에 해보도록 하자.

### 3. 아이템을 분류하는 곳을 클릭할 수 있는 루프 생성. 얻어야 할 곳을 클릭( 비슷한 유형을 여러개 선택해준다고 생각하면 됨 )

![종류](https://user-images.githubusercontent.com/46266247/57515790-6a535400-734e-11e9-80d4-9a2a4cddbdd0.png)

#### 3단계 결과

![결과3](https://user-images.githubusercontent.com/46266247/57516014-d7ff8000-734e-11e9-88f1-a4adf3caed1e.JPG)

### 4. 아이템 이름을 뽑는다. 스크롤을 내려 아이템을 5번째꺼(아무거나 상관없음) 1번째꺼 클릭(첫번째는 해줘야한다.). 그후 추출

![추출1](https://user-images.githubusercontent.com/46266247/57516292-6bd14c00-734f-11e9-85ce-a7a6c877b164.png)

#### 4단계 결과

![결과4](https://user-images.githubusercontent.com/46266247/57516496-cbc7f280-734f-11e9-90d3-11f18a26e5bc.png)

### 5. 데이터 추출

- 위 사진에서 10시 방향에 Save를 한번 눌러 저장하고 그 옆의 **Start extraction**을 클릭. 
- 무료 이용자이므로 **Local extracion**을 클릭.
- #------ 자동으로 크롤링을 해준다-------# 
- 끝나고 Export Data 버튼을 누르고 저장 디렉토리를 설정, 저장파일 형식 지정 해주면 끝.(저는 .csv 파일로 저장했습니다.)

#### 결과

[전체 다운로드](https://github.com/chanp5660/Util_chanp5660/files/9127972/ItemList.csv)

![결과6](https://user-images.githubusercontent.com/46266247/57516773-5577c000-7350-11e9-82b6-c3e99ab92027.png)





