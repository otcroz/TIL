### SEO란?
검색엔진의 검색 결과에 자신의 웹 페이지가 더 많이 노출되도록 최적화된 컨텐츠를 만드는 것

![image](https://user-images.githubusercontent.com/79989242/151664490-7ce240a2-31ce-40d2-8a5a-0ab5a0c346c2.png)


#### 크롤링
- 구글: 막대한 수의 컴퓨터 => 웹 페이지 크롤링, 이를 크롤러라고 함.
- 크롤링은 최신 버전의 크롬이 사용
- 크롤러는 HTML 문서를 파싱, js가 있으면 렌더링 대기열에 웹페이지 추가
- 크롤링 대상 URL: sitemap.xml, 크롤러가 진입한 페이지의 링크로 등록된 URL

#### 크롤링에서 특정 페이지를 제외하는 방법
Robots.txt에 크롤링에서 제외하고자 하는 URL을 작성
=> 다른 페이지에 링크로 들어가면 크롤링 대상

**1.** 로그인 후 사용할 수 있는 페이지: 구글봇이 로그인을 진행하지X, 크롤러가 접근할 수 없다.

**2.** noindex 적용
```
<meta name="robots" content="noindex"> <!--모든 크롤러에 대한 크롤링 차단-->
<meta name="googlebot" content="noindex"> <!--구글봇에 대한 크롤링 차단-->
```

**3.** a 태그에 ```rel="nofollow"```, ```rel="sponsored"``` 적용
```
<a rel="nofollow" href="https://..."></a> <!--유저로부터 만들어진 스팸 링크-->
<a rel="sponsored" href="https://..."></a> <!--우리 사이트에 표시되는 광고-->
```
