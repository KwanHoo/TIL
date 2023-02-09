# _Ajax_

## Ajax 개요

### 2) Ajax 란?

Asynchronous JavaScript and XML

- 빠르게 동작하는 동적인 웹 페이지를 만들기 위한 개발 기법의 하나임
- 웹 페이지 전체를 다시 로딩하지 않고도, 웹 페이지의 일부분만을 갱신할 수 있음
  - Ajax를 이용하면 백그라운드 영역에서 서버와 통신하여, 그 결과를 웹 페이지의 일부분에만 표시할 수 있음
- 서버와는 ‘JSON, XML, HTML, txt 파일 등’ 과 같은 형태의 데이터를 주고 받을 수 있음

### Ajax 장점

1. 웹 페이지 전체를 다시 로딩하지 않고도, 웹 페이지의 일부분만을 갱신할 수 있음
2. 웹 페이지가 로드된 후에 서버로 데이터 요청을 보낼 수 있음
3. 웹 페이지가 로드된 후에 서버로부터 데이터를 받을 수 있음
4. 백그라운드 영역에서 서버로 데이터를 보낼 수 있음

### Ajax 한계

1. Ajax는 클라이언트가 서버에 데이터를 요청하는 클라이언트 풀링 방식을 사용하므로, 서버 푸시 방식의 실시간 서비스는 만들 수 없음
2. AJax로는 바이너리 데이터를 보내거나 받을 수 없음
3. 스크립트가 포함된 서버가 아닌 다른 서버로 Ajax 요청을 보낼 수는 없음
4. 클라이언트의 PC로 AJax 요청을 보낼 수 없음

### 참고 ) 클라이언트 풀링 ( Client Pooling ) 방식

- 사용자가 직접 원하는 정보를 서버에게 요청하여 얻는 방식을 의미함

↔ 서버 푸시 ( Server Push )방식

- 사용자가 요청하지 않아도 서버가 알아서 자동으로 특정 정보를 제공하는 것을 의미함

  - ex) 스마트폰에서 각종 앱이 보내는 푸시 알림이 서버 푸시 방식의 예

  ### Ajax 프레임워크

Ajax를 이용하여 개발을 손쉽게 할 수 있도록 미리 여러 가지 기능을 포함해 놓은 개발 환경을 Ajax 프레임워크라고함

대표적인 Ajax 프레임워크

- Prototype
- script.aculo.us
- dojo
- jQuery

---

## 3) Ajax 동작 원리

### Ajax 구성요소

Ajax는 기존에 사용되던 여러 기술을 함께 사용하여, **웹 페이지의 일부분만을 갱신**할 수 있도록 해주는 개발 기법입니다.

- 웹 페이지의 표현을 위한 HTML과 CSS
- 데이터에 접근하거나 화면 구성을 동적으로 조작하기 위해 사용되는 DOM 모델
- 데이터의 교환을 위한 JSON 이나 XML
- 웹 서버와의 비동기식 통신을 위한 XMLHttpRequest 객체
- 위에서 언급한 모든 기술을 결합하여 사용자의 작업 흐름을 제어하는데 사용되는 JS

### Ajax 동작 원리

Ajax를 이용한 웹 응용 프로그램은 JS 코드를 통해 웹 서버와 통신을 함

사용자의 동작에는 영향을 주지 않으면서도 백그라운드에서 지속해서 서버와 통신할 수 있음

---

## 4) DOM

문서 객체 모델 ( Document Object Model )

HTML 문서나 XML 문서에 접근하기 위한 일종의 인터페이스

DOM 모델은 문서 내의 모든 요소의 목적과 특징을 정의하고 각각의 요소에 접근하는 방법을 제공

##### Ajax 에서는 이러한 DOM 을 이용하여 웹 페이지의 일부 요소만을 변경할 수 있음!!

### DOM 요소의 선택

JS로 DOM 요소를 다루기 위해서는 우선 해당 요소를 선택해야함

DOM 요소를 선택하는 방법

1. 태그 이름(tag name)을 이용한 선택
2. 아이디(id)를 이용한 선택
3. 클래스(class)를 이용한 선택
4. CSS 선택자(selector)를 이용한 선택
5. HTML 객체 집합(object collection)을 이용한 선택

### DOM 요소의 내용 변경

DOM을 이용하면 DOM 요소의 내용(content)이나 속성값 등을 손쉽게 변경할 수 있음

DOM 요소의 내용을 바꾸는 가장 쉬운 방법은 innerHTML 프로퍼티를 이용하는 것임

또한, DOM 요소의 속성 이름을 이용하면 속성값을 바로 변경할 수 있음

---

## 7) XMLHttpRequest 객체

### XMLHttpRequest 객체

Ajax의 가장 핵심적인 구성 요소는 바로 XMLHttpRequest 객체임

Ajax에서 XMLHttpRequest 객체는 웹 브라우저가 서버와 데이터를 교환할 때 사용됨

웹 브라우저가 백그라운드에서 계속해서 서버와 통신할 수 있는 것은 바로 이 객체를 사용하기 때문임!!!!

### 참고) XMLHttpRequest 객체의 역사

비동기식 통신 방식인 XMLHttp 는 가장 처음으로 익스플로러 5버전에서 ActiveXObject 라는 객체를 사용하여 구현됨. 그 후 모질라와 사파리에서 XMLHttpRequest 라는 이름으로 도입하여 사용하기 시작함

초기의 XMLHttpRequest 객체는 W3C 표준이 아니었기 때문에 웹 브라우저마다 구현상의 차이가 존재했음

하지만 익스플로러 7버전 부터 XMLHttpRequest 객체를 기본적으로 지원하게 되며, W3C 표준으로 제정됨

따라서 현재 대부분의 웹 브라우저는 모두 비슷한 구현 방식으로 XMLHttpRequest 객체를 사용하고 있음

---

Ajax에서는 XMLHttpRequest 객체를 사용하여 서버와 데이터를 교환함

서버에 요청을 보내기 위해서는 우선 XMLHttpRequest 인스턴스를 생성해야함

XMLHttpRequest 인스턴스의 open() 메소드와 send() 메소드를 사용하여 요청을 보낼 수 있음

---

## 14) $.ajax() 메소드← Ajax와 제이쿼리

### 제이쿼리와 Ajax

Ajax를 이용하여 개발을 손쉽게 할 수 있도록 미리 여러 가지 기능을 포함해 놓은 개발 환경을 Ajax 프레임워크라고함. 그중에서도 현재 가장 널리 사용되고 있는 Ajax 프레임워크는 바로 제이쿼리임

### $.ajax() 메소드

제이쿼리는 Ajax와 관련된 다양하고도 편리한 메소드를 많이 제공하고 있음

그중에서도 $.ajax() 메소드는 모든 제이쿼리 Ajax 메소드의 핵심이 되는 메소드임

$.ajax() 메소드는 HTTP 요청을 만드는 강력하고도 직관적인 방법을 제공함

- 원형

```jsx
$.ajax([옵션]);
```

URL 주소는 클라이언트가 HTTP 요청을 보낼 서버의 주소임

옵션은 HTTP 요청을 구성하는 키와 값의 쌍으로 구성되는 헤더의 집합임

### $.ajax() 메소드에서 사용할 수 있는 옵션 예제

```jsx
$.ajax({
  url: "/examples/media/request_ajax.php", // 클라이언트가 요청을 보낼 서버의 URL 주소

  data: { name: "홍길동" }, // HTTP 요청과 함께 서버로 보낼 데이터

  type: "GET", // HTTP 요청 방식(GET, POST)

  dataType: "json", // 서버에서 보내줄 데이터의 타입
})

  // HTTP 요청이 성공하면 요청한 데이터가 done() 메소드로 전달됨.

  .done(function (json) {
    $("<h1>").text(json.title).appendTo("body");

    $('<div class="content">').html(json.html).appendTo("body");
  })

  // HTTP 요청이 실패하면 오류와 상태에 관한 정보가 fail() 메소드로 전달됨.

  .fail(function (xhr, status, errorThrown) {
    $("#text")
      .html("오류가 발생했습니다.<br>")

      .append("오류명: " + errorThrown + "<br>")

      .append("상태: " + status);
  })

  // HTTP 요청이 성공하거나 실패하는 것에 상관없이 언제나 always() 메소드가 실행됨.

  .always(function (xhr, status) {
    $("#text").html("요청이 완료되었습니다!");
  });
```

$.ajax( ) 메소드의 동작을 보여주는 예제

```jsx
$(function () {
  $("#requestBtn").on("click", function () {
    $.ajax("/examples/media/request_ajax.php")

      .done(function () {
        alert("요청 성공");
      })

      .fail(function () {
        alert("요청 실패");
      })

      .always(function () {
        alert("요청 완료");
      });
  });
});
```

참고 링크 : [http://www.tcpschool.com/jquery/jq_ajax_method](http://www.tcpschool.com/jquery/jq_ajax_method)

### load( ) 메소드

load( ) 메소드는 선택한 요소에서 호출하는 유일한 제이쿼리 Ajax 메소드임

load( ) 메소드는 서버에서 데이터를 읽은 후, 읽어 들인 HTML 코드를 선택한 요소에 배치함

또한, 선택자를 URL 주소와 함께 전송하면, 읽어 들인 HTML 코드 중에서 선택자와 일치하는 요소만을 배치함

예제\_

```jsx
$(function () {
  $("#requestBtn").on("click", function () {
    // URL 주소에 존재하는 HTML 코드에서 <li>요소를 읽은 후에 id가 "list"인 요소에 배치함.

    $("#list").load(
      "/examples/tryit/htmlexample/jq_elementTraversing_etc_01.html li"
    );
  });
});
```

### Ajax 메소드

제이쿼리는 $.ajax( ) 메소드 뿐만 아니라 Ajax와 관련된 다양한 메소드를 제공함

---

## 15) 기타 메소드

### $.get() 메소드

제이쿼리에서는 Ajax를 이용하여 GET 방식의 HTTP 요청을 구현한 겟 메소드 제공함

이 메소드를 사용하면 서버에 GET 방식의 HTTP 요청을 보낼 수 있음

$.get( ) 메소드의 원형은 다음과 같음

```jsx
$.get(URL주소[,콜백함수]);
```

URL 주소는 클라이언트가 HTTP 요청을 보낼 서버의 주소임

콜백 함수는 HTTP 요청이 성공했을 때 실행할 함수를 정의함

예제 \_

```jsx
$(function () {
  $("#requestBtn").on("click", function () {
    // GET 방식으로 서버에 HTTP 요청을 보냄.

    $.get(
      "/examples/media/jquery_ajax_data.txt",

      function (data, status) {
        $("#text").html(data + status); // 전송받은 데이터와 전송 성공 여부를 보여줌.
      }
    );
  });
});
```

### $.post( ) 메소드

제이쿼리에서는 Ajax 를 이용하여 POST 방식의 HTTP 요청을 구현한 $.post( ) 메소드를 제공함. 이 메소드를 사용하면 서버에 POST 방식의 HTTP 요청을 보낼 수 있음

$.POST() 메소드의 원형

```jsx
$.post(URL주소[,데이터][,콜백함수]);
```

URL 주소는 클라이언트가 HTTP 요청을 보낼 서버의 주소임

데이터는 HTTP 요청과 함께 서버로 보낼 데이터를 전달함

콜백 함수는 HTTP 요청이 성공했을 때 실행할 함수를 정의함

```jsx
$(function () {
  $("#requestBtn").on("click", function () {
    // POST 방식으로 서버에 HTTP 요청을 보냄.

    $.post(
      "/examples/media/request_ajax.php",

      { name: "이순신", grade: "A+" }, // 서버가 필요한 정보를 같이 보냄.

      function (data, status) {
        $("#text").html(data + "<br>" + status); // 전송받은 데이터와 전송 성공 여부를 보여줌.
      }
    );
  });
});
```

### load( ) 메소드

load( ) 메소드는 선택한 요소에서 호출하는 유일한 제이쿼리 Ajax 메소드임

load( ) 메소드는 서버에서 데이터를 읽어 들인 후에 해당 HTML 코드를 선택한 요소에 배치함

이때 선택자를 URL 주소와 함께 전송하면, 읽어 들인 HTML 코드 중에서 선택자와 일치하는 요소만을 배치함

예제

```jsx
$(function () {
  $("#requestBtn").on("click", function () {
    // URL 주소에 존재하는 HTML 코드에서 <li>요소를 읽은 후에 id가 "list"인 요소에 배치함.

    $("#list").load(
      "/examples/tryit/htmlexample/jq_elementTraversing_etc_01.html li"
    );
  });
});
```

load( ) 메소드의 인수로 URL 주소와 함께 선택자를 전달할 때는 위의 예제와 같이 하나의 문자열로 전송해야 함. 이때 URL 주소와 선택자는 띄어쓰기로 구분할 수 있음.

다음 예제는 test.txt 파일 내에서 아이디가 para인 요소만을 읽어 들여, 아이디가 box인 요소 안에 배치하는 예제임

```jsx
$("#box").load("test.txt #para");
```
