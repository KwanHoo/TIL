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

참고 : 엘리스
