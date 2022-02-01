### ✨Sitemap
사이트에 있는 페이지, 동영상, 파일 등의 정보를 제공하는 파일
- 검색 엔진에 제출 → 더 효율적으로 크롤링될 수 있도록 하는 역할
- Sitemap은 어떤 페이지가 중요한 지 알려주는 일종의 제안
  - Sitemap에 등록된 URL이 모두 인덱싱될 것이라는 보장X

#### Sitemap에 포함할 내용
- **내 사이트에서 검색 결과로 노출시키고 싶은 페이지의 URL**
- 동영상의 영상 길이, 카테고리, 연령 등급
- 이미지의 유형, 라이센스
- 뉴스의 제목, 게시 날짜


#### Sitemap 제약조건
- 용량 50mb 이하, URL 5만개 이하 → 초과시 분할
- Sitemap은 Sitemap의 상위 디렉토리의 하위 디렉토리에만 영향을 줌
  - 따라서 대부분의 **Sitemap**은 **루트 디렉토리**에 위치
```
www.example.com/sitemap.xml
-> www.example.com 하위 모든 url에 적용

www.example.com/some/path/sitemap.xml
-> www.example.com/some/path 하위에 적용, www.example.com에 미적용
```
#### Django Sitemap Generator
- Sitemap에 URL을 하나씩 입력하기 너무 많은 → 동적으로 Sitemap을 만드는 라이브러리 존재
- 장고에서 ```django.contrib.sitemaps```를 사용하면 쉽게 만들 수 있음
  - 모든 객체(예: Post, Interview)의 ```get_absolute_url```을 Sitemap에 등록
  - ```urlpatterns```에 만들어진 ```sitemaps``` 딕셔너리를 넣어줌

```
from django.contrib.sitemaps import GenericSitemap
from django.contrib.sitemaps.views import sitemap

sitemaps = {
    "post": GenericSitemap({"queryset": Post.objects.all() }, priority=1),
    "interview": GenericSitemap({"queryset": Interview.objects.all() }, priority=1),
}

urlpatterns = [
    path("sitemap.xml/", sitemap, {"sitemaps": sitemaps}, name="sitemap"),
]
```

### ✨Robots.txt
크롤러가 사이트에 접근할 수 있는 URL과 겁근 거부한 URL을 알려주는 txt 파일
- 검색엔진마다 Robots.txt를 대하는 구현이 다름, 검색엔진마다 다르게 적용될 수 있다.

#### Robots.txt 형식
- **User-agent**: 어떤 검색에닌에 대한 규칙인지 선언
- **Disallow**: 해당 URL은 크롤링을 거부하겠다는 선언
- **Allow**: 해당 URL은 크롤링을 허용하겠다는 선언(default)
- **Sitemap**: Sitemap의 위치

```
User-agent: BaiDuSpider
Disallow: /

User-agent: BadBot
Disallow: /

User-agent: *
Disallow: /api
Allow: /

Sitemap: http://www.example.com/sitemap.xml
```
- BaiDuSpider, badBot 검색엔진 크롤러에 대해 모든 페이지 허용X
- 위 두 크롤러를 제외한 모든 크롤러 → ```/api```로 시작하는 URL 크롤링 거부

#### Robots.txt에 접근 거부 했음에도 계속 인덱싱이 되는 이유
- disallow 했음에도 불구하고, 크롤러게 제외한 URL을 접근하는 경우가 있음
- Robots.txt는 페이지를 숨김X, 사이트에 부하가 덜 생기게 하는 목록
- 크롤러는 Robot.tt에 접근 거부가 되었으면 그 페이지는 방문X, **다른 페이지에 링크로 존재하는 경우 크롤링 진행**
- ```noindex```, ```nofollow``` 설정을 하여 페이지에서 인덱싱 거절
