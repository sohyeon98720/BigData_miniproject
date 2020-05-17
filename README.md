# crawling으로 수집하고 데이터 spark로 분석하기

### 빅데이터 수업 중 미니 프로젝트(2019 2학기 9주차~13주차)

--------------

__주제__: 넷플릭스와 왓챠플레이의 검색량 비교와 각 사이트의 상위 컨텐츠 분석

--------------
__데이터 수집 방법__: 
1. [네이버 개발자센터](https://developers.naver.com/docs/search/blog/)에서 오픈 API 이용 신청
2. 발급받은 client-id와 client-secret을 API 호출 예제(python용)에 적용하여 블로그 요약 데이터를 받아옴

> <img src="https://user-images.githubusercontent.com/47767202/82142477-9b2a6b00-9877-11ea-9e77-42a541c797e9.JPG" width="70%">       

> 호출예제의 자세한 설명은 [네이버 개발자센터](https://developers.naver.com/docs/search/blog/) 참고

__데이터 분석 방법__:
1. 블로그 요약 데이터 중 본문 제목(title열)을 가져옴
2. 
