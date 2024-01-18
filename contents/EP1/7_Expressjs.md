# Express.js

#Express.js, #Middleware, #REST API, #JSON, #MVC, #Postman

### Express.js를 사용하는 이유

- Express.js는 Node.js의 웹 프레임워크 중 가장 유명한 웬 프레임 워크
- 필요에 따라 유연하게 구조 설정 가능
- 다양한 미들웨어를 통해 필요한 기능을 간단하게 추가 가능
- 모든 동작이 명시적으로 구성되기 때문에, 웹 프레임워크의 동작 방식을 이해하기 가장 좋은 프레임워크

### Expres.js의 기본구조

my-web

- app.js : Express.js의 가장 기본이 되는 파일, 웹 어플리케이션의 기능 정의
- bin/www : Express.js의 실행 부분을 담당, 포트와 실행 오류 등을 정의
- package.json : 프로젝트 의존성 및 스크립트 정의
- public : 코드를 통하지 않고, 직접 제공되는 파일 디렉토리
- routes : 라우팅 파일 디렉터리
- views : HTMl Template 디렉터리

### 라우팅

- Express.js 는 다양한 라우팅 방식을 제공함
- 크게 app 라우팅과 Express.Router를 통한 라우팅으로 나누어짐

### Middleware란?

- 미들웨어는 Express.js 동작의 핵심
- HTTP 요청과 응답 사이에서 단계별 동작을 수행해주는 함수

- Express.js의 미들웨어는 HTTP 요청이 들어온 순간부터 시작이 됨
- 미들웨어는 HTTP 요청과 응답 객체를 처리하거나, 다음 미들웨어를 실행 할 수 있음
- HTTP 응담이 마무리될 때까지 미들웨어 동작 사이클이 실행됨

- req, res, next를 가진 함수를 작성하면 해당 함수는 미들웨어로 동작할 수 있음
  - req : HTTP 요청을 처리하는 객체
  - res : HTTP 응답을 처리하는 객체
  - next : 다음 미들웨어를 실행하는 함수

### Router Handler

- Route Handler도 미들웨어의 한 종류
- 라우팅 함수(get, post, put, delet 등)에 적용된 미들웨어
- 일반적인 미들웨어와는 다르게 path parameter를 사용할 수 있음

### 미들웨어 사용법

- 미들웨어는 적용되는 위치에 다라서 어플리케이션 미들웨어, 라우터 미들웨어, 오류처리 미들웨어로 분류가능
- 필요한 동작 방식에 따라 미들웨어를 적용할 위치를 결정

### 요약

- 미들웨어는 HTTP 요청과 응답 사이에서 동작하는 함수
- req, res, next를 인자로 갖는 함수는 미들웨어로 동작할 수 있음
- app 혹은 router 객체에 연결해서 사용가능
- next에 인자를 넘기는 경우 오류처리 미들웨어가 실행됨
- 미들웨어에 값을 설정하고 싶은 경우는 함수형 미들웨어로 작성 가능

---

---

### REST API란?

- REST + API
- REST 아키텍처를 준수하는 웹 API
- RESTful API라고 부르기도 함

### API란?

- Application Programming Interface
- 서비스나 프로그램 간에 미리 정해진 기능을 실행 할 수 있도록 하는 규약
- 운영체제 API, 프로그램언어 API, 웹 API 등이 있음

### REST 란?

- REpresentational State Transfer
- 웹에서 자료를 전송하기 위한 표현 방법에 대한 아키텍처
- REST를 정확하게 구현하기 위해선 많은 제한조건이 있지만, 기본적인 REST 가이드를 따르면 조금 더 좋은 구조의 API를 구성할 수 있음

- GET : 가져오기
- POST : 새로만들기
- PUT : 수정하기
- DELETE : 삭제하기

- HTTP method와 결합하여 API 동작을 정의하여야 함

### JSON

- JavaScript Object Notation
- 자바스크립트에서 객체를 표현하는 표현식으로 시작함
- 데이터를 표현하는 방법이 단순하고 이해하기 쉬워서 웹 API에서 데이터를 전송할 때 표현식으로 주로 사용됨

### JSON을 사용하는 이유

- 웹 API는 기본적으로 데이터를 문자열로 전송하게 됨
- 어떤 객체를 웹 API를 통해서 문자열로 전달하기 위해 JSON을 사용함

### MVC 패턴

- MVC 패턴은 웹 서비스의 가장 대표적인 프로젝트 구성 패턴
- 프로젝트의 기능들을 어떻게 분리할지에 대한 하나의 구성 방법
- Model
- View
- Controller

### Model

- 데이터에 접근하는 기능 또는 데이터 그 자체를 의미함
- 데이터의 읽기, 쓰기는 Model을 통해서만 이루어지도록 구성해야함

### View

- 데이터를 표현하는 기능을 의미함
- Controller에 의해 데이터를 전달 받고 전달 받은 데이터를 화면에 표시해주는 기능을 당담

### Controller

- Model을 통해 데이터에 접근하여 처리 결과를 View로 전달하는 기능을 의미함
- 웹 서비스에선 주로 라우팅 함수가 해당 기능을 수행함

### Postman

- API를 테스트할 수 있는 도구
- HTTP 요청을 손쉽게 작성하여 테스트해 볼 수 잇게 도움
- 추가로 API를 문서화 할 수 있는 기능 및 다양한 도구를 제공함

참고 : 엘리스
