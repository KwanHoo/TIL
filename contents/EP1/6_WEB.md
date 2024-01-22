# WEB

### 웹이란?

- 사전적 의미 : World Wide Web, 인터넷사에서 동작하는 모든 서비스
- 일반적 의미 : 웹브라우저로 접속해서 이용하는 서비스, 웹사이트

### 동적 웹의 두가지 구현방법

- CSR : Client-Side Rendering

  - 프론트엔드에서 사용자가 페이지에서 보는 동적인 부분을 대부분 처리하는 방식

- SSR : Server-Side Rendering
  - 백엔드에서 페이지 대부분의 영역을 처리해서 프론트엔드로 전달하는 방식

### CSR의 특징

- 사이트가 변하는 부분들을 프론트엔드에서 처리
- 프론트 엔드 코드에 페이지 리소스들이 미리 정의되어 있음
- 서버와 통신은 API 통신을 이용
- 빠른 반응이지만 페이지의 내용은 API 호출이 완료된 후에 보여짐
- 복잡한 프로젝트 구성, 큰 개발 사이즈

### SSR

- 사이트가 변하는 부분들을 백엔드에서 처리
- 백엔드에서 HTML 파일을 작성해서 프론트엔드로 전달
- CSR에 비해 쉬운 구성, 작은 개발사이즈
- 로딩이 완료되면 페이지와 데이터가 한 번에 표시됨
- 상대적으로 사용자가 보기엔 로딩이 느려 보임
- 페이지 이동할 떄마다 다시 로딩하기 때문에 페이지 깜빡임

### 웹 프레임워크

- 웹 _ 프레임워크 : 웹 서비스에 필요한 기능들을 제공해주는 _ 다양한 도구들의 모음
- 웹 서비스를 빠르게 구성하기 위해 웹 프레임워크를 사용할 수 있음
- HTTP 요청, 응답, 라우팅, HTML Templating 등의 기능을 제공함

- Node.js의 가장 유명한 웹 프레임워크는 Express.js

### 웹 프레임워크를 사용하는 이유

- 웹 서비스를 구성하기 위해서는 매우 많은 기능이 필요함
- 이러한 기능들을 하나씩 직접 만드는 것에는 너무나 큰 비용이 발생
- 웹 서비스는 많은 부분이 정형화되어 있음
- 프레임 워크를 사용하여 정형화된 부분을 간단하게 구현, 필요한 부부만 집중해서 개발 할 수 있음

참고 : 엘리스