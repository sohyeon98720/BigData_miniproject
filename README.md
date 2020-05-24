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
1. 
