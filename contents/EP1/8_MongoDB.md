# MongoDB

#MongoDB, #NoSQL, #Mongoose, #템플릿엔진, #Pug, #CRUD, #Pagination, #Hash, #Session

### MongoDB란?

- 대표적인 NoSQL, Document DB
- Mongo는 Humongous에서 따온 말로, 엄청나게 큰 DB라는 의미

  - 대용량 데이터를 처리하기 좋게 만들어짐

- Database > Collection > Document

### RDB

- 관계형 데이터베이스
- 자료들의 관계를 주요하게 다룸
- SQL 질의어를 사용하기 위해 데이터를 구조화 해야함

### NoSQL

- Not only SQL
- 구조화된 질의어를 사용하지 않는 데이터베이스
- 자료 간의 관계에 초점을 두지 않음
- 데이터를 구조화하지 않고, 유연하게 저장함

- Document DB, key-value, Graph, large collection 등의 NoSql DB 존재

### NoSQL을 사용하는 이유

- SQL을 사용하기 위해서는 데이터를 구조화하는 것이 필요 (DDL)
  - 스키마에 정의된 데이터가 아니면 저장할 수 없는 제약이 따름
- NoSQL을 사용하면 사전작업 없이 데이터베이스를 사용할 수 있음
  - 데이터베이스 작업에 크게 관여하지 않고 프로젝트를 빠르게 진행할 수 있음

### MongoDB 기본 개념 - Database

- 하나 이상의 collection을 가질 수 있는 저장소
- SQL에서의 database와 유사

### MongoDB 기본 개념 - Collection

- 하나 이상의 Document가 저장되는 공간
- SQL에서의 table과 유사
- 하지만, collecton이 document의 구조를 정의하지 않음

### MongoDB 기본 개념

- MongoDB에 저장되는 자료, SQL에서 row와 유사하지만 구조제약 없이 유연하게 저장 가능
- JSON과 유사한, BSON을 사용하여 다양한 자료형을 지원

---

---

### Mongoose ODM 이란?

- Object Data Modeling
- MongoDB의 Collection에 집중하여 관리하도록 도와주는 패키지 Collection을 모델화하여, 관련 기능들을 쉽게 사용할 수 있도록 도와줌

### Mongoose ODM 사용하는 이유 : 연결 관리

- MongoDB의 기본 Node.js 드라이버는 연결상태를 관리하기 어려움
- Mongoose를 사용하면 간단하게 데이터베이스와의 연결상태를 관리해줌

### Mongoose ODM 사용하는 이유 : 스키마 관리

- 스키마를 정의하지 않고 데이터를 사용할 수 있는 것은 NoSQL의 장점이지만, 데이터 형식을 미리 정의 해야 코드 작성과 프로젝트 관리에 유용함
- Mongoose는 Code-Level에서 스키마를 정의하고 관리할 수 있게 해줌

### Mongoose ODM 사용하는 이유 : Populate

- MongoDB는 기본적으로 join을 제공하지 않음
- join과 유사한 기능을 사용하기 위해선 aggregate 라는 복잡한 쿼리를 해야하지만, Mongoose는 populate를 사용하여 간단하게 구현할 수 있음

### Query

- MongoDB에도 SQL의 where과 유사한 조건절 사용가능
- MongoDB의 query는 BSON 형식으로, 기본 문법 그대로 mongoose에서도 사용가능

### 템플릿 엔진이란?

- 서버에서 클라이언트로 보낼 HTML의 형태를 미리 템플릿으로 저장
- 동작 시에 미리 작성된 템플릿에 데이터를 넣어서 완성된 HTML 생성
- 템플릿 엔진은 템플릿 작성 문법과 작성된 템플릿을 HTML로 변환하는 기능을 제공

### Express.js의 템플릿 엔진

- Pug : 들여쓰기 표현식을 이용한 간략한 표기와 레이아웃 등 강력한 기능을 제공
- Mustache : 간단한 데이터 치환 정도만 제공하는 경량화된 템플릿 엔진
- EJS : html과 유사한 문법의 템플릿 엔진

### Pug

- 들여쓰기 표현식을 이용해 가독성이 좋고 개발 생산성이 높음
- HTML을 잘 모르더라도 문법적 실수를 줄일 수 있음
- layout, include, mixin 등 강력한 기능 제공

### CRUD란?

- Create, Read, Update, Delete
- 데이터를 다루는 네가지 기본적인 기능
- 일반적으로 위 네 가지에 대한 구현이 가능해야함
- 서비스 개발에 필요한 요구사항을 충족할 수 있음

### Pagination이란?

- 데이터가 많아지면 한 페이지의 목록에 모든 데이터를 표현하기 어려움
- Pagination은 데이터를 균일한 수로 나누어 페이지로 분리하는 것

### 백엔드 개발자의 역할

- 개발에 선행되야될 부분 : 스키마 설계, API 설계, 코드 ㅋ컨벤션
- 스키마 설계 : 제약조건, 원하는 데이터 형태만 들어올 수 있게 제약함

### 회원 정보를 데이터베이스에 저장하기

- 회원 비밀번호를 그대로 저장한다면 관리자가 모든 회원의 비밀번호를 알 수 있음 -> 보안 취약점 발생

### 비밀번호 저장 방법 : Hash

- Hash는 문자열을 되돌릴 수 없는 방식으로 암호화하는 방법

  - hash 출력값을 이용해 사용자의 비밀번호를 알아낼 수 없음

- 비밀번호의 Hash 값을 데이터베이스에 저장하고, 로그인 시 전달된 비밀번호를 hash 하여 저장된 값과 비굑해 로그인을 처리

### passport.js란?

- Express.js 어플리케이션에 간단하게 사용자 인증 기능을 구현하게 도와주는 패키지
- 유저 세션 관리 및 다양한 로그인 방식 추가 기능

### Session 이란?

- 웹 서버가 클라이언트의 정보를 클라이언트별로 구분하여 서버에 저장하고 클라이언트 요청 시 Session ID를 사용하여 클라이언트의 정보를 다시 확인하는 기술
- 클라이언트가 정보를 저장하고, 요청시 정보를 보내는 Cookie와 대조됨

- 세션과 쿠키는 웹 개발자 면접에서 단골질문!!

### 세션 작동 방식

- 서버는 세션을 생성하여 세션의 구분자인 Session ID를 클라이언트에 전달함 클라이언트는 요청시 Session ID를 함게 요청에 담아 전송
- 서버는 전달 받은 Session ID로 해당하는 세션을 찾아 클라이언트 정보를 확인

### Session Store를 사용하는 이유

- express-session 패키지는 session을 기본적으로 메모리에 저장함
- 따라서 현재 구현된 어플리케이션을 종료후 다시 실행하면 모든 유저의 로그인이 해제됨
- 혹은 서버가 여러 대가 있을 경우, 서버 간 세션 정보 공유할 수 없음

### Index

- MongoDB는 검색을 위해 Document를 정렬하여 저장하는 기능을 제공함
- Index를 설정하면 주어진 쿼리를 효율적으로 수행하여 성능르 향상시킬 수 있음
- 다중키, 좌표, 텍스트 등의 특별한 값으로 정리되는 인덱스도 제공

### 클라이언트에 리소스 선언 - HTML Template

- 클라이언트에 리소스를 선언하기 위한 다양한 방법이 존재 (React.js, Vue.js)
- HTML Template : 브라우저에 표시되지 않는 HTML Element를 작성해 두고, javascript로 이를 화면에 반복적으로 그릴 수 있게 하는 기술

### 데이터 비동기 호출 - API 작성하기

- HTTP 응당으로 HTML을 전송하는 방식
- CSR을 구현하기 위해서는 HTML이 아닌, 데이터만 주고받을 수 있는 API를 구성해야함 (JSON 사용)
- 댓글 작성 API와 댓글 목록 API만 구현
- 댓글 작성 시 댓글 목록을 다시 불러와 그리는 형식으로 구현

### 데이터 비동기 호출 - fetch로 클라이언트에서 api 호출하기

- 브라우저는 비동기 HTTP 요청을 fetch 함수를 이용해 제공함
- jQuery의 ajax와 유사한 기능, jQuery를 사용하지 않고도 HTTP 요청 구현 가능
- fetch를 이용하면 간단하게 JS로 HTTP 요청을 비동기 처리할 수 있음

### Aggregation이란?

- MongoDB에서 Document 들을 가공하고, 연산하는 기능
- RDBMS에서 SQL로 수행할 수 있는 기능들을 유사하게 구현할 수 있음

- ex) SQL 의 Group By, DISTINCT, COUNT, JOIN 등

참고 : 엘리스
