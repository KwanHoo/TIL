# _.val()_

## .val() : jquery

- .val()은 양식(from)의 값을 가져오거나 값을 설정하는 메소드임

사용예시1) .val()

```jsx
var jb = $("input#jbInput").val();
```

- 아이디가 jbInput인 input 요소의 값을 변수 jb에 저장함

사용예시2) .val( value )

```jsx
$("input#jbInput").val("ABCDE");
```

- 아이디가 jbInput인 input 요소의 값을 ABCDE로 정함

---

### 제이쿼리 문법

```sql
$(선택자).동작함수();
```

- 달러($) 기호는 제이쿼리를의미하고, 제이쿼리에 접근할 수 있게 해주는 식별자임

- 선택자를 이용하여 원하는 HTML 요소를 선택하고, 동작 함수를 정의하여 선택된 요소에 원하는 동작을 설정함

### $() 함수

- 선택된 HTML 요소를 제이쿼리에서 이용할 수 있는 형태로 생성해 주는 역할을 함

- 인수로는 HTML 태그 이름뿐만 아니라, CSS 선택자를 전달하여 특정 HTML 요소를 선택할 수 있음

- 이러한 $() 함수를 통해 생성된 요소를 제이쿼리 객체라고함

- 제이쿼리는 이렇게 생성된 제이쿼리 객체의 메소드를 사용하여 여러 동작을 설정할 수 있음

### Document 객체의 ready() 메소드

- 자바스크립트 코드는 웹 브라우저가 문서의 모든 요소를 로드한 뒤에 실행되어야 함

- 보통은 별다른 문제가 발생하지 않지만, 다음과 같은 경우에는 오류가 발생함

###!! 오류발생 주의!!!

- 아직 생성되지 않은 HTML 요소에 속성을 추가하려고 할 경우

- 아직 로드되지 않은 이미지의 크기를 얻으려고 할 경우

---

## eval()

\*\*`eval()`
은 문자로 표현된 JavaScript 코드를 실행하는 함수입니다.

### syntax

```jsx
eval(string);
```

```jsx
console.log(eval("2 + 2"));
// Expected output: 4

console.log(eval(new String("2 + 2")));
// Expected output: 2 + 2

console.log(eval("2 + 2") === eval("4"));
// Expected output: true

console.log(eval("2 + 2") === eval(new String("2 + 2")));
// Expected output: false
```

[참고 포스팅](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/eval)
