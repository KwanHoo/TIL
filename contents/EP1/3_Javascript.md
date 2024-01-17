# Javascript

- 이미지 슬라이드 효과, 팝업 효과 등의 기능을 포함한 동적인 웹사이트 제작 시 사용되는 프로그래밍 언어

### JS 변수 생성 시 주의 사항

- 변수명은 숫자로 시작할 수 없음
- 변수명은 최대한 자세하게 작성
- 의미가 불명확한 단어들의 조합은 피해야 함

### JS 데이터 타입 8가지

- String 문자열
- Number 숫자
- Function 함수
- Array 배열
- Object 객체
- Boolean 불린
- undefined 정의되지 않음
  - 변수 안에 데이터를 입력하지 않은 상태 (데이터가 없는 것)
- null 널
  - 개발자가 임의로 변수 안에 빈 데이터를 삽입한 상태 (빈 데이터를 지정한 것)

### 비교 연산자

```javascript
console.log(10 == 20); // 값이 같다
console.log(10 === 20); // 데이터 타입과 값이 같다
console.log(10 !== 20); // 값이 같지 않다

console.log(10 == "10"); // true
console.log(10 === "10"); // false
```

## DOM

- 문서 객체 모델 (Document Object Model)
- 객체 지향 모델로써 구조화된 문서를 표현하는 형식
- DOM은 XML이나 HTML 문서의 프로그래밍 인터페이스
- 구조화된 표현을 제공하여 프로그래밍 언어가 문서 구조, 스타일, 내용 등을 변경 할 수 있도록함

- Core DOM : 모든 문서 타입을 위한 DOM 모델
- HTML DOM : HTML 문서를 위한 DOM 모델
- XML DOM: 문서를 위한 DOM 모델

### Document 객체

- 웹페이즈를 의미함
- 웹 페이지에 존재하는 HTML 요소에 접근하고자 할 때는 반드시 Document 객체부터 시작해야함

```javascript
document.getElementsByTagName("li");

document.getElementById("id");

document.getElementsByClassName("odd");

document.getElementsByName("first");
```

## 이벤트

- 웹 브라우저가 알려주는 HTML 요소에 대한 사건의 발생
- JS는 발생한 이벤트에 반응하여 특정 동작을 수행할 수 있음

### 이벤트 핸들러

- 이벤트가 발생했을 때 그 처리를 담당하는 함수
- 지정된 이벤트가 발생하면, 웹 브라우저는 그 요소에 등록된 이벤트 핸들러를 실행시킴

### 함수는 일급 객체 (first-class object)
- 일급 객체란, 다른 변수처럼 대상을 다룰 수 있는 것을 말함
- 자바스크립트에서 함수는 일급객체임
- 즉, 자바스크립트에서 함수는 변수처럼 다룰 수 있음

### 클로저
- 자바스크립트 클로저는 함수의 일급 객체 성질을 이용함
- 함수가 생성될 때, 함수 내부에서 사용되는 변수들이 외부에 존재하는 경우 그 변수들은 함수의 스코프에 저장됨
- 함수와 함수가 사용하는 변수들을 저장한 공간을 클로저라 함

### Hoisting
- Hoisting은 변수가 선언된 시점보다 앞에서 사용되는 현상임
- 이는 var 변수가 생성 단계에서 undefined로 초기화되는 것이 원인임
- 함수는 생성 단계에서 함수 전체가 저장되므로 뒤에서 선언되어도 호출이 가능함!

### 동기적 제어 흐름
- 동기적 제어 흐름은 현재 실행 중인 코드가 종료되기 전까지 다음 줄의 코드를 실행하지 않는 것을 의미함
- 분기문, 반복문, 함수 호출 등이 동기적으로 실행됨
- 코드의 흐름과 실제 제어 흐름이 동일함
- 싱글 스레드 환경에서 메인 스레드를 긴 시간 점유하면, 프로그램을 멈추게 함

### 비동기적 제어 흐름
- 비동기적 제어 흐름은 현재 실행 중인 코드가 종료되기 전에 다음 라인의 코드를 실행하는 것을 의미함
- 프로미스, 콜백 함수를 호출하는 함수 등은 비동기적으로 실행됨
- 코드 흐름과 실제 제어 흐름이 다름
- 비동기 작업을 기다리는 동안 메인 스레드는 다른 작업을 처리함

### Promise API
- Promise API는 비동기 API 중 하나임
- 태스크 큐가 아닌 잡 큐를 사용함
- 잡 큐는 태스크 큐보다 우선순위가 높음

### async / awiat
- promise를 활용한 비동기 코드를 간결하게 작성하는 문법
- async / await 문법으로 비동기 코드를 동기 코드처럼 간결하게 작성할 수 있음
- async 함수과 await 키워드를 이용함
- await 키워드는 반드시 async 함수 안에서만 사용해야함
- async로 선언된 함수는 반드시 promise를 리턴함

### HTTP (Hypertext Transfer Protocol)
- Web에서 서버와 클라이언트 간의 통신하는 방법을 정한 것
- 클라이언트는 웹 브라우저 등 서버로 요청을 보내는 대상
- 서버는 클라이언트가 요청을 보내기 전까지 대응하지 않음
- 서버와 클라이언트 사이에는 무수히 많은 요소가 존재
- HTTP는 이런 존재들 사이의 통신 방법을 규정

### REST API (Representational State Transfer API)
- API(Application Programming Interface)는 사용자가 특정 기능을 사용할 수 있도록 제공하는 함수를 의미함
- REST API는 HTTP의 요청 메서드에 응하는 서버 API와 클라이언트 간 통신의 구조가 지켜야 할 좋은 방법을 명시한 것임
- 구체적인 내용으로는 요청 메서드의 의미, URI 설계, 클라이언트의 상태에 대한 동작 등을 정의함

- GET : 리소스 정보를 얻음
- POST : 리소스를 생성
- PUT : 리소스를 생성하거나 업데이트
- DELETE : 리소스를 제거

### Fetch API
- 기존 XMLHTTPRequest를 대체하는 HTTP 요청 API
- ES6에 추가된 Promise를 리턴하도록 정의됨
- 네트워크 요청 성공 시, Promise는 Response 객체를 reslove 함
- 네트워크 요청 실패 시, Promise는 에러를 reject 함

참고 : 엘리스
