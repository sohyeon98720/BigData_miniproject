# crawling으로 수집하고 데이터 spark로 분석하기

### 빅데이터 수업 중 미니 프로젝트(2019 2학기 9주차~13주차)

--------------

__주제__: 넷플릭스와 왓챠플레이의 검색량 비교와 각 사이트의 상위 컨텐츠 분석

--------------
### 넷플릭스와 왓챠 각 사이트의 상위 컨텐츠 골라내기
__데이터 수집 방법__: 
1. [네이버 개발자센터](https://developers.naver.com/docs/search/blog/)에서 **오픈 API** 이용 신청
2. 발급받은 client-id와 client-secret을 API 호출 예제(python용)에 적용하여 **블로그 요약 데이터**를 받아옴
    - 요청변수: 자세한 설명은 [네이버 개발자센터](https://developers.naver.com/docs/search/blog/) 참고                          
      <img src="https://user-images.githubusercontent.com/47767202/82142477-9b2a6b00-9877-11ea-9e77-42a541c797e9.JPG" width="70%">       


__데이터 분석 방법__:
1. 블로그 **요약 데이터** 중 본문 **제목(title열)**을 가져옴
    - 출력결과: 자세한 설명은 [네이버 개발자센터](https://developers.naver.com/docs/search/blog/) 참고                          
      <img src="https://user-images.githubusercontent.com/47767202/82142765-9e265b00-9879-11ea-9391-5fb3a20ac858.JPG" width="70%">
      <img src="https://user-images.githubusercontent.com/47767202/82633131-5450c280-9c35-11ea-859c-dc42d7958b2d.png" width="70%"> 
2. 본문 제목에 '**추천**'이라는 키워드가 있는 블로그의 **링크**만 **저장**
3. 저장된 링크의 **본문 전체 내용** 수집
    - [참고영상](https://www.youtube.com/watch?v=cB8bRCTgqJ8) (23:39~)
4. 본문 전체 내용 분석하여 **컨텐츠 이름**만 골라오기
     - 분석방법: 단어로 분리 -> 불용어 제거 -> strip으로 공백, 특수문자 및 특정 문자 제거 -> 불용어 제거<br>
                 -> replace연산으로 특정 키워드를 컨텐츠 전체 이름으로 바꾸기(ex.오티스-오티스의비밀상담소)<br>
                 -> 2글자 이상의 단어만 filter -> 단어의 빈도수를 셀 수 있도록 형태변환 후 빈도수대로 출력
     
__결과물__:<br>
순서대로 넷플릭스,왓챠<br>
<img src="https://user-images.githubusercontent.com/47767202/82757589-5de84f00-9e1c-11ea-941a-e9c1c37dceca.png" width="90%">


-------------------
### 넷플릭스와 왓챠의 검색량 비교
__결과물__:<br>
<img src="https://user-images.githubusercontent.com/47767202/82850016-a182ac00-9f35-11ea-98a1-8e84aa1f24ff.png" width="90%">

-----------------
### 결론
<img src="https://user-images.githubusercontent.com/47767202/82850393-333ee900-9f37-11ea-82ec-8a5773527327.png" width="40%">
<img src="https://user-images.githubusercontent.com/47767202/82850470-7bf6a200-9f37-11ea-9d48-deadee913bef.png" width="40%">

- 넷플릭스의 **검색량**이 왓챠에 비해 월등히 높았고 실제로 **서비스 사용자수 차이**도 그와 비슷하게 **일치**
- 최근 웨이브가 급속도로 성장함에따라 넷플릭스도 사용자수에 있어서 밀리고 있다. 또한 CJ E&M과 JTBC도 합작 OTT를 설립하기로 한 가운데 OTT 서비스를 거점 삼아 외주 유통을 더 이상 제공하지 않게되면 **100% 외주로 컨텐츠를 유통**하는 **왓챠는 고객을 잃을 것**이라는 전망이 나오고 있다. 하지만 **왓챠**는 넷플릭스에 비해 **월정액 요금이 저렴**하고 **bbc**와 **hbo**의 판권을 따오며 넷플릭스에서 제공하지 않는 킬링이브, 체르노빌, 왕좌의 게임과 같은 **컨텐츠를 유통**한다는 점에서는 분명히 앞설 수 있을 만한 점이 있다고 생각한다. 
