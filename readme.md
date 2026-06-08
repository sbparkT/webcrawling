# **웹 크롤링(Web Crawling)**

- **컴퓨터 프로그램이 자동으로 인터넷 웹페이지들을 돌아다니며 데이터를 수집하고 분류하는 기술 및 과정**
- 이 작업을 수행하는 프로그램을 '크롤러(Crawler)' 또는 '스파이더(Spider)

## **<웹 크롤링 동작 원리>**

1. **탐색:** 웹 크롤러가 특정 웹페이지에 접속하여 내용을 읽고, 그 페이지 안에 있는 다른 링크(URL)를 타고 끊임없이 이동
2. **수집 및 저장:** 방문한 페이지들의 텍스트, 이미지, 구조 등의 데이터를 복사하여 가져오기
3. **색인:수집한 정보들을 검색하기 쉽게 분류하여 데이터베이스에 저장**

## <활용 사례>

- **검색 엔진:** 구글(Google)이나 네이버(Naver) 같은 검색 엔진이 전 세계의 웹페이지를 미리 수집해 두었다가 검색 결과를 빠르게 제공하는 데 사용
- **가격 및 트렌드 분석:**쇼핑몰 사이트들의 제품 가격을 주기적으로 수집하여 최저가를 비교
- **데이터 분석:** 뉴스 기사나 SNS 댓글을 대량으로 수집하여 사람들의 반응이나 시장 트렌드를 분석

## [참고]**크롤링 vs 스크래핑 (차이점)**

- **크롤링:** 웹사이트의 여러 링크를 타고 돌아다니며 '방대한 데이터를 색인하고 탐색'
- **웹 스크래핑:** 특정 웹사이트 하나를 정해놓고 그곳에서 필요한 데이터만 쏙쏙 '추출(긁어오기)'

---

> 크롤링을 무조건 해도 될까…? 크롤링 과정에서 고려해야 할 문제는 무엇일까?
> 

---

## <robots.txt>

- **이 페이지는 수집해도 좋고, 저 페이지는 수집하면 안 된다"라고 안내하는 출입 규칙 파일**
- 웹사이트의 가장 최상위 경로(루트 디렉터리)에 `웹사이트주소/robots.txt` 형태로 위치
- 구글이나 네이버 같은 신뢰할 수 있는 크롤러들은 사이트를 방문할 때 이 파일을 가장 먼저 확인하고 규칙을 따라야 해

<aside>

사이트 주소 + /robots.txt

네이버     https://www.naver.com/robots.txt

구글       https://www.google.com/robots.txt

다음       https://www.daum.net/robots.txt

유튜브     https://www.youtube.com/robots.txt  *🔑api추천*

위키백과   https://ko.wikipedia.org/robots.txt

쿠팡       https://www.coupang.com/robots.txt

멜론       https://www.melon.com/robots.txt

인스타그램 https://www.instagram.com/robots.txt  * 🔑api추천*

</aside>

[](data:image/png;base64,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)

<aside>

User-agent: *        ← 모든 봇에게 적용
Disallow: /private   ← /private 경로 크롤링 금지
Allow: /public       ← /public 경로 허용

User-agent: Googlebot  ← 구글 봇에게만 적용
Disallow:              ← 전부 허용 (비워두면 허용)

</aside>

<aside>

사람 user agent(우리)
→ 브라우저로 접속
→ 눈으로 보고 클릭
→ 한 번에 한 페이지씩
→ 서버 부하 적음

봇 (자동화 프로그램)
→ 코드로 접속
→ 자동으로 수집
→ 초당 수백 페이지 가능
→ 서버 부하 큼

사람   =  서비스 이용자 (환영)
봇     =  자동화 프로그램 (선별적 허용)

Googlebot  =  사이트에 도움되는 봇 → 허용
파이썬 봇  =  데이터만 가져가는 봇 → 차단

</aside>

<aside>

<주요 봇 이름들>
구글    →  Googlebot
웹 전체를 돌아다니며 검색 인덱싱

네이버  →  Yeti
네이버 검색결과 만들기 위해 수집

다음    →  Daum
다음 검색결과용 수집

마이크로소프트  →  Bingbot
빙 검색결과용 수집

페이스북  →  facebookexternalhit
링크 공유할 때 미리보기 생성

카카오  →  Kakaotalk
카카오톡 링크 미리보기용

🤖구글봇이 하루에 하는 일

1. 전 세계 수억 개 웹페이지 방문
2. 내용 수집 → 구글 서버에 저장
3. 검색어 입력 시 관련 페이지 노출

우리가 구글에서 검색할 수 있는 이유가
Googlebot이 미리 다 긁어놨기 때문

</aside>
