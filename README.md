# crawling으로 수집하고 데이터 spark로 분석하기

### 빅데이터 수업 중 미니 프로젝트(2019 2학기 9주차~13주차)

--------------

__주제__: 넷플릭스와 왓챠플레이의 검색량 비교와 각 사이트의 상위 컨텐츠 분석

--------------
__데이터 수집 방법__: 
1. [네이버 개발자센터](https://developers.naver.com/docs/search/blog/)에서 오픈 API 이용 신청
2. 발급받은 client-id와 client-secret을 API 호출 예제(python용)에 적용하여 블로그 요약 데이터를 받아옴
    - 요청변수: 자세한 설명은 [네이버 개발자센터](https://developers.naver.com/docs/search/blog/) 참고                          
      <img src="https://user-images.githubusercontent.com/47767202/82142477-9b2a6b00-9877-11ea-9e77-42a541c797e9.JPG" width="70%">       



__데이터 분석 방법__:
1. 블로그 요약 데이터 중 본문 제목(title열)을 가져옴
    - 출력결과: 자세한 설명은 [네이버 개발자센터](https://developers.naver.com/docs/search/blog/) 참고                          
      <img src="https://user-images.githubusercontent.com/47767202/82142765-9e265b00-9879-11ea-9391-5fb3a20ac858.JPG" width="70%">
2. 본문 제목에 '추천'이라는 키워드가 있는 블로그의 링크만 저장
3. 저장된 링크의 본문 전체 내용 수집
    - [참고영상](https://www.youtube.com/watch?v=cB8bRCTgqJ8) (23:39~)
4. 
