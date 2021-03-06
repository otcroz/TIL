### react-router-dom
한 개의 페이지로 이루어진 SPA는 리액트 라우터를 사용하여 개발한다.

❓SPA(싱글페이지)라고 해서 한 페이지인가요?

➨ "꼭 그렇지만은 않다."

서버에서 사용자에게 제공하는 페이지는 한 종류

해당 페이지에서 로딩된 자바스크립트, 현재 사용자 브라우저의 주소에 따라 다양한 화면을 보여주는 것이 가능

**라우팅**: 다른 주소에 다른 화면을 보여주는 기능

   ⊙ 리액트 라이브러리 자체에 라우팅 기능이 내장되어 있지 않다.

   ⊙ 브라우저의 API, 라이브러리를 사용하여 현재 사용자의 브라우저 주소에 따라 다양한 화면을 보여줌


#### 리액트 라우터의 단점
##### 1. 앱의 규모가 커지면 자바스크립트 파일이 너무 커진다.

페이지 로딩 시 사용자가 실제 방문하지 않을 수도 있는 페이지의 스크립트도 불러온다.

➨ 코드 스플리팅: 라우트별로 파일들을 나누어 트래픽, 로딩 속도 개선



##### 2. 일반 크롤러에서 페이지의 정보를 제대로 수집하지 못할 수 있다.

브라우저에서 자바스크립트를 사용하여 라우팅을 관리

   ⊙ 자바스크립트를 실행하지 않은 일반 크롤러에서 페이지의 정보를 제대로 수집하지 못한다.

   ⊙ 구글, 네이버 등의 검색 엔진의 검색 결과에 페이지가 잘 나타나지 않을 수 있다.



##### 3. 짧은 시간동안 흰 페이지가 나타날 수 있다.

자바스크립트가 실행될 때까지 페이지가 비어 있다.


➨ 2, 3번의 문제는 "**서버 사이드 렌더링**"을 통해 해결

*#서버 사이드 렌더링: 서버에서 페이지를 그려 클라이언트에 보낸 후, 이를 화면에 표시*
