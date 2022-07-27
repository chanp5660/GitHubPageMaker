---
layout: post  
current: post  
cover:  assets/built/images/python-logo.png  
navigation: True  
title: 나라장터-수집(1)-OPENAPI    
date: 2022-07-25 23:43:00 +0900  
tags: [python, project]  
class: post-template  
subclass: 'post tag-python'  
author: chanp5660  
---

{% include Narasangtu-table-of-contents.html %}

# 나라장터-수집(1)-OPENAPI

> 나라장터에의 낙찰하는 분석을 하게 되는 상황이 생겼는데 통계, 컴공으로서 근거 없는 찍는 것을 믿지 못하고 찍신이 아닌 나 자신을 믿을 수가 없었다. 따라서 이때다 싶어 나라장터 분석 및 예측을 해보기로 했다.

## 공공데이터포털 OPENAPI 활용신청

- [공공데이터포털 사이트](https://www.data.go.kr/index.do)

<img src="https://user-images.githubusercontent.com/46266247/180806602-701bcead-48f9-44d7-adce-22cf48411c07.png" width="90%">

- 검색어 : [조달청_나라장터 공공데이터개방표준서비스](https://www.data.go.kr/data/15058815/openapi.do)

<img src="https://user-images.githubusercontent.com/46266247/180806928-08bff0b0-7068-44c2-adc2-a80103d3b828.png" width="100%">

- 활용신청 : 안에 내용은 본인의 의도에 맞게 적어 제출하면 등록이 되어 사용가능하다.(바로 사용이 안되면 어느정도 기다렸다가 하면된다.) 다른 데이터는 기관에서 인증을 해주고 나서 해주는 경우도 있다.

- 참고문서 : open API 사용법 및 입출력 코드와 설명

<img src="https://user-images.githubusercontent.com/46266247/180846098-3a7ad05d-620e-4b76-95ce-4f26faae64c7.png" width="90%">

## OPENAPI URL 만들기

```python
EndPoint = "http://apis.data.go.kr/1230000/PubDataOpnStdService"

ServiceKey ="" # 공공데이터포털에서 받은 인코딩 인증키

PageNo = 1 # 페이지번호
NumOfRows = 100 # 한 페이지 결과 수
Datatype = "json" # 오픈API 리턴 타입을 JSON으로 받고 싶을 경우 'json' 으로 지정함
bidNtceBgnDt = 202207240000 # 검색하고자하는 입찰공고일시범위 시작 'YYYYMMDDHHMM' (입찰공고일시 범위는 1개월 로 제한)
bidNtceEndDt = 202207312359 # 검색하고자하는 입찰공고일시범위 종료 'YYYYMMDDHHMM' (입찰공고일시 범위는 1개월 로 제한)

def Info_Version(info_version) : # 데이터셋 개방표준에 따른 입찰공고정보
    if info_version == "입찰":
        return "getDataSetOpnStdBidPblancInfo"
    elif info_version == "낙찰":
        return "getDataSetOpnStdScsbidInfo"
    else : # 계약
        return "getDataSetOpnStdCntrctInfo"    
```

- 테스트 : 결과물로 나오는 URL을 클릭하면 json 파일이 열린다.

```python
info_version = "입찰"
URL = f"{EndPoint}/{Info_Version(info_version)}?numOfRows={NumOfRows}&pageNo={PageNo}&bidNtceBgnDt={bidNtceBgnDt}&bidNtceEndDt={bidNtceEndDt}&ServiceKey={ServiceKey}&type={Datatype}"
```

<img src="https://user-images.githubusercontent.com/46266247/180835139-bbcbf0a5-d7b1-4f94-b60c-b5e250625e16.png" width="40%">

## 데이터 수집 코드

- 본 블로그는 투찰가능업종명 : 산림사업법인(숲가꾸기 및 병해충방제), 산림사업법인(도시숲등 조성, 관리) 관련으로 분석 및 예측한다.


```python
import requests
import pandas as pd

def Info_Version(info_version) : # 데이터셋 개방표준에 따른 입찰공고정보
    if info_version == "입찰":
        return "getDataSetOpnStdBidPblancInfo"
    elif info_version == "낙찰":
        return "getDataSetOpnStdScsbidInfo"
    else : # 계약
        return "getDataSetOpnStdCntrctInfo"   
    
def Get_Bid_df(info_version, bidNtceBgnDt, bidNtceEndDt, ServiceKey): # 원하는 기간, 버전에 따른 공고정보 얻기
    
    # default setting
    PageNo = 1 # 페이지번호
    NumOfRows = 100 # 한 페이지 결과 수
    EndPoint = "http://apis.data.go.kr/1230000/PubDataOpnStdService"
    Datatype = "json" # 오픈API 리턴 타입을 JSON으로 받고 싶을 경우 'json' 으로 지정함
    
    Bid_df =pd.DataFrame()
    while True:
        URL = f"{EndPoint}/{Info_Version(info_version)}?numOfRows={NumOfRows}&pageNo={PageNo}&bidNtceBgnDt={bidNtceBgnDt}&bidNtceEndDt={bidNtceEndDt}&ServiceKey={ServiceKey}&type={Datatype}"
        response = requests.get(URL)

        # 총 데이터 개수
        TotalCount = response.json()["response"]["body"]["totalCount"]

        # 나라장터 입찰공고 DataFrame 생성
        bid_df = pd.DataFrame(response.json()["response"]["body"]["items"])

        # 읽은 데이터의 개수를 확인해서 데이터의 끝인지 확인
        if len(bid_df) == 0 : break

        # 목적에 필요한 열을 가져온다. 다운받은 참고문헌을 참조한다.
        # 본인의 목적에 따라 수정해야할 부분
        bid_df = bid_df.loc[:,["bidNtceNm","bidBeginDate","bidBeginTm","bidClseDate","bidClseTm","opengDate","opengTm","asignBdgtAmt","presmptPrce","rgnLmtYn","prtcptPsblRgnNm","bidprcPsblIndstrytyNm"]]
        bid_df = bid_df.rename( columns  = {"bidNtceNm":"입찰공고명","bidBeginDate":"입찰개시일자","bidBeginTm":"입찰개시시각","bidClseDate":"입찰마감일자","bidClseTm":"입찰마감시각","opengDate":"개찰일자","opengTm":"개찰시각","asignBdgtAmt":"배정예산금액(설계금액)","presmptPrce":"추정가격","rgnLmtYn":"지역제한여부","prtcptPsblRgnNm":"참가가능지역명","bidprcPsblIndstrytyNm":"투찰가능업종명"})
        
        # 
        
        # 데이터 프레임 병합
        Bid_df = pd.concat([Bid_df,bid_df],axis=0)
        Bid_df.reset_index(drop=True,inplace=True)

        # 페이지 증가
        PageNo=str(int(PageNo)+1)
    
    print("----------------------------------")
    print(f"{info_version} \n{str(bidNtceBgnDt)[:4]}년 {str(bidNtceBgnDt)[4:6]}월 {str(bidNtceBgnDt)[6:8]}일 - {str(bidNtceEndDt)[:4]}년 {str(bidNtceEndDt)[4:6]}월 {str(bidNtceEndDt)[6:8]}일")
    print("----------------------------------")
    
    return Bid_df
```


```python
ServiceKey ="" # 공공데이터포털에서 받은 인코딩 인증키
bidNtceBgnDt = 202207240000 # 검색하고자하는 입찰공고일시범위 시작 'YYYYMMDDHHMM' (입찰공고일시 범위는 1개월 로 제한)
bidNtceEndDt = 202207312359 # 검색하고자하는 입찰공고일시범위 종료 'YYYYMMDDHHMM' (입찰공고일시 범위는 1개월 로 제한)
info_version = "입찰"

Bid_df = Get_Bid_df(info_version, bidNtceBgnDt, bidNtceEndDt, ServiceKey)
```


```python
Check_business = ["산림사업법인(숲가꾸기 및 병해충방제)", "산림사업법인(도시숲등 조성, 관리)"] # 특찰가능업종명
                                                         
def Check_business_fuc(business):
    if Check_business[0] in business or Check_business[1] in business:
        return True
    else :
        return False

# map(Check_business_fuc,Bid_df["투찰가능업종명"]) 투찰가능업종명을 기준으로 필터 하는 방법
Bid_df = Bid_df.loc[map(Check_business_fuc,Bid_df.loc[:,"투찰가능업종명"])]
display(Bid_df.head())
```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>입찰공고명</th>
      <th>입찰개시일자</th>
      <th>입찰개시시각</th>
      <th>입찰마감일자</th>
      <th>입찰마감시각</th>
      <th>개찰일자</th>
      <th>개찰시각</th>
      <th>배정예산금액(설계금액)</th>
      <th>추정가격</th>
      <th>지역제한여부</th>
      <th>참가가능지역명</th>
      <th>투찰가능업종명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>24</th>
      <td>2022년 풀베기사업(2차)[구성 상거지구]</td>
      <td>2022-07-25</td>
      <td>10:00</td>
      <td>2022-07-28</td>
      <td>10:00</td>
      <td>2022-07-28</td>
      <td>11:00</td>
      <td></td>
      <td>46520000</td>
      <td>Y</td>
      <td>경상북도 김천시</td>
      <td>산림사업법인(숲가꾸기 및 병해충방제)</td>
    </tr>
    <tr>
      <th>25</th>
      <td>2022년 풀베기사업(2차)[남면 송곡지구]</td>
      <td>2022-07-25</td>
      <td>10:00</td>
      <td>2022-07-28</td>
      <td>10:00</td>
      <td>2022-07-28</td>
      <td>11:00</td>
      <td></td>
      <td>43880000</td>
      <td>Y</td>
      <td>경상북도 김천시</td>
      <td>산림사업법인(숲가꾸기 및 병해충방제)</td>
    </tr>
    <tr>
      <th>26</th>
      <td>2022년 풀베기사업(2차)[지례 신평지구]</td>
      <td>2022-07-25</td>
      <td>10:00</td>
      <td>2022-07-28</td>
      <td>10:00</td>
      <td>2022-07-28</td>
      <td>11:00</td>
      <td></td>
      <td>46700000</td>
      <td>Y</td>
      <td>경상북도 김천시</td>
      <td>산림사업법인(숲가꾸기 및 병해충방제)</td>
    </tr>
    <tr>
      <th>27</th>
      <td>2022년 풀베기사업(2차)[부항사등지구]</td>
      <td>2022-07-25</td>
      <td>10:00</td>
      <td>2022-07-28</td>
      <td>10:00</td>
      <td>2022-07-28</td>
      <td>11:00</td>
      <td></td>
      <td>26050000</td>
      <td>Y</td>
      <td>경상북도 김천시</td>
      <td>산림사업법인(숲가꾸기 및 병해충방제)</td>
    </tr>
    <tr>
      <th>28</th>
      <td>2022년 풀베기사업(2차)[대덕덕산지구]</td>
      <td>2022-07-25</td>
      <td>10:00</td>
      <td>2022-07-28</td>
      <td>10:00</td>
      <td>2022-07-28</td>
      <td>11:00</td>
      <td></td>
      <td>47340000</td>
      <td>Y</td>
      <td>경상북도 김천시</td>
      <td>산림사업법인(숲가꾸기 및 병해충방제)</td>
    </tr>
  </tbody>
</table>
</div>


## 데이터 csv 파일 저장

- 저장하는 방법은 여러가지가 있는데 그 중 화면에서도 쉽게 이해할 수 있도록 csv 파일로 저장하는 것으로 선택했다.

- 저장 데이터
    - 입찰공고정보
    - 202207240000 ~ 202207312359 기간
    - 투찰가능업종명 으로 "산림사업법인(숲가꾸기 및 병해충방제)", "산림사업법인(도시숲등 조성, 관리)" 인 정보로 필터


```python
Savefile_path = "./2022-07-25-나라장터-수집(1)-OPENAPI" # 저장할 파일 경로
Bid_df.to_csv(f"{Savefile_path}/{info_version}_{bidNtceBgnDt}_{bidNtceEndDt}.c sv",index=False, encoding="cp949") # 인덱스를 없애고 저장한다.
```

<img src="https://user-images.githubusercontent.com/46266247/180992085-87a89aff-a104-44f4-978e-06fbe3a7447d.png" width="100%">
