### 인덱싱
페이지가 어떤 페이지인지 파악, 검색결과로 노출될 수 있도록 페이지 정보를 저장
- Meta 태그, Title, HTML 콘텐츠, 이미지, 비디오 등의 **페이지 정보**를 분석하여 페이지 파악
- **구글 데이터베이스**에 페이지 정보 저장

#### Document 개념
- **Document**: 완전히 동일한 컨텐츠를 갖는 여러 개의 웹 페이지 모음
> https://www.example.com/page/1 <br>
> https://www.example.com?page=1 <br>
> http://www.example.com?page=1 <br>

- 위 주소 모두 동일한 HTML 콘텐츠를 갖는 페이지라고 가정
  - 하나의 문서의 3개의 웹 페이지
  - **Canonical URL**: 하나의 문서 대표하는 페이지 URL
  - **Duplicates URL(= Alternates URL)**: Canonical URL이 아닌 페이지들의 URL

#### 인덱싱 과정에서 페이지 중복 검사
- 인덱싱 과정에서 페이지의 중복 여부 검사
  - 페이지 중복 → **Document**에 **Duplicates URL**이 추가
  - 동일한 페이지를 중복으로 크롤링했다고 판단
  - 해당 사이트에 대한 **크롤링 빈도 감소**
- ```link``` 태그의 ```rel="canonical"```속성 설정
  - 크롤러에게 Canonical URL이 이미 존재, 이 페이지는 크롤링이 필요 없음을 명시
  - 중복 크롤링 방지

```
<link rel="canonical" href="https://example.com/page/1" />
```

- ```noindex``` 태그 사용
  - 중복되는 페이지에 **noindex** 선언 → 크롤링을 하지 않겠다고 명시, 중복 크롤링 방지


#### 검색 결과 게재
- 검색어에 대한 가장 높은 품질의 결과 반환
- 사용자의 위치, 언어, 기기, 이전 검색어 등을 고려
- 페이지의 컨텐츠, 속도, 모바일, 호환성 고려


