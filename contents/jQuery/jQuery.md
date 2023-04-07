# _jQuery_

## 1) 제이쿼리 개요

### jQuery

제이쿼리는 자바스크립트 언어를 간편하게 사용할 수 있도록 단순화 시킨 오픈 소스 기반의 JS 라이브러임

제이쿼리를 이용하면 문서 객체 모델(DOM)과 이벤트에 관한 처리를 손쉽게 구현할 수 있음

또한 Ajax 응용 프로그램 및 플러그인도 제이쿼리를 활용하여 빠르게 개발할 수 있음

---

## 2) 제이쿼리

### 제이쿼리를 배우기 위한 사전지식

- HTML / CSS / Javascript

### 제이쿼리(jQuery)란?

제이쿼리는 오픈 소스 기반의 JS 라이브러리임

제이쿼리는 웹 사이트에 자바스크립트를 더욱 손쉽게 활용할 수 있게 해줌

또한, 제이쿼리를 사용하면 짧고 단순한 코드로도 웹 페이지에 다양한 효과나 연출을 적용할 수 있음

### 제이쿼리의 장점

1. 제이쿼리는 주요 웹 브라우저의 구버전을 포함한 대부분의 브라우저에서 지원됨
2. HTML DOM 을 손쉽게 조작할 수 있으며, CSS 스타일도 간단히 적용할 수 있음
3. 애니메이션 효과나 대화형 처리를 간단하게 적용해 줌
4. 같은 동작을 하는 프로그램을 더욱 짧은 코드로 구현할 수 있음
5. 다양한 플러그인과 참고할 수 있는 문서가 많이 존재함
6. 오픈 라이선스를 적용하여 누구나 자유롭게 사용할 수 있음

---

## 4) 제이쿼리 문법

제이쿼리를 사용하면 아주 간편하게 HTML 요소를 선택하고 특정 동작을 설정할 수 있음

\_ 기본 문법

```jsx
$(선택자).동작함수();
```

**달러($)** 기호는 제이쿼리를 의미하고, 제이쿼리에 접근할 수 있게 해주는 식별자임

선택자를 이용하여 원하는 HTML 요소를 선택하고, 동작 함수를 정의하여 선택된 요소에 원하는 동작을 설정함

### $( ) 함수

$( ) 함수는 선택된 HTML 요소를 제이쿼리에서 이용할 수 있는 형태로 생성해 주는 역할을 함

$( ) 함수의 인수로는 HTML 태그 이름뿐만 아니라, CSS 선택자를 전달하여 특정 HTML 요소를 선택할 수 있음

이러한 $( ) 함수를 통해 생성된 요소를 제이쿼리 객체( jQuery Object ) 라고 함

제이쿼리는 이렇게 생성된 제이쿼리 객체의 메소드를 사용하여 여러 동작을 설정할 수 있음

### Document 객체의 ready( ) 메소드

JS 코드는 웹 브라우저가 문서의 모든 요소를 로드한 뒤에 실행 되어야 함

보통은 별다른 문제가 발생하지 않지만,

- 아직 생성되지 않은 HTML 요소에 속성을 추가하려고 할 경우
- 아직 로드되지 않은 이미지의 크기를 얻으려고 할 경우

등 다음과 같은 경우에는 오류가 발생함 ( Uncaught TypeError )

JS 에서는 Window 객체의 onload() 메소드를 이용하며 문서가 모두 로드된 뒤에 코드가 실행되도록 설정함

```jsx
window.onload = function( ) {
	js 코드;
};
```

마찬가지로 제이쿼리에서는 Document 객체의 ready( ) 메소드를 이용하여 같은 결과를 보장하고 있음

```jsx
$( document ).ready( function ( ) {
	제이쿼리 코드;
});
```

또한, jQuery Team에서는 같은 결과를 보장하는 더욱 짧은 문법을 다음과 같이 제공하고 있음

```jsx
$( function( ) {
	제이쿼리 코드;
});
```

문서가 모두 로드되는 시점과 창이 모두 로드되는 시점의 차이 예시

```jsx
$(document).ready(function () {
  $("#doc").text("문서가 전부 로드됐어요!");
});

$(window).load(function () {
  $("#win").text("창이 모두 로드됐어요!");
});
```

---

## 6) CSS 선택자

제이쿼리에서는 CSS 선택자를 사용하여 HTML 요소를 선택할 수 있음

태그 이름을 사용하여 같은 태그 이름을 가지는 HTML 요소를 모두 선택할 수 있음

JS의 getElementByTagName( ) 메소드와 같은 동작을 함

```jsx
$(function () {
  $("p").on("click", function () {
    // <p>요소를 모두 선택함.

    $("span").css("fontSize", "28px"); // <span>요소를 모두 선택함.
  });
});
```

#### 참고! $( ) 함수에 전달되는 인수는 반드시 따옴표(” “ ) 를 사용한 문자열 형태로 전달되어야 함

#### ID

아이디( id )를 사용하여 특정 HTML 요소를 선택할 수도 있음

JS의 getElementsById( ) 메소드와 같은 동작을 함

```jsx
$(function () {
  $("p").on("click", function () {
    $("#jq").css("border", "2px solid orange"); // 아이디가 "jq"인 요소를 선택함.
  });
});
```

#### 클래스

클래스(class)를 사용하여 같은 클래스에 속하는 HTML 요소를 모두 선택할 수 있음

JS의 getElementsByClassName() 메소드와 같은 동작을 함

```jsx
$(function () {
  $("p").on("click", function () {
    $(".jq").css("backgroundColor", "lightgray"); // 클래스가 "jq"인 요소를 모두 선택함.
  });
});
```

#### 속성

속성(attribute)을 사용하여 속성이 조건에 맞는 특정 HTML 요소를 선택할 수 있음

```jsx
$(function () {
  $("button").on("click", function () {
    // <img>요소 중에서 alt 속성값이 "flower"인 요소를 모두 선택함.

    $("img[alt='flower']").attr("src", "/examples/images/img_monalisa.png");
  });
});
```

---

## 7) 제이쿼리 선택자

제이쿼리에서는 CSS 선택자뿐만 아니라 몇몇 비표준 선택자까지도 사용할 수 있음

이러한 비표준 선택자를 사용하면 선택한 요소를 저장하거나, 그 결과에 대해 필터링까지 할 수 있음

### 선택한 요소의 저장

제이쿼리에서는 선택한 요소들을 변수에 저장하여 사용할 수 있음

예제는 문서 내의 모든 <li> 요소를 선택하여 변수에 저장한 후, 해당 변수를 사용하는 예제임

```jsx
$(function () {
  var items = $("li"); // <li>요소를 모두 선택하여 변수 items에 저장함.

  $("button").on("click", function () {
    $("#len").text(
      "저장된 <li>요소의 총 개수는 " + items.length + "개 입니다."
    );
  });
});
```

하지만 이렇게 저장된 요소들은 변수에 저장될 당시의 요소들만 저장됨

즉 요소가 저장된 이후에 문서에 추가되거나 삭제된 요소들을 자동으로 갱신하지는 않음

### 선택한 요소의 필터링

제이쿼리에서는 선택한 요소 중에서 더욱 세분화된 선택을 하기 위한 필터링을 진행할 수 있음

\_문서 내의 모든 <li> 요소 중에서 <span> 요소를 가지고 있는 요소만을 선택하는 예제

```jsx
$(function () {
  $("button").on("click", function () {
    $("li:has(span)").text("<span>요소를 가지고 있는 아이템이에요!");
  });
});
```

### input 요소의 선택

제이쿼리에서는 입력 양식에 관련된 특정 요소를 손쉽게 선택할 수 있음

```jsx
$(function () {
  $("button").on("click", function () {
    // 체크되어 있는 요소를 모두 선택함.

    $(":checked").next().text("체크되어 있는 요소는 이 요소입니다.");
  });
});
```

---

## 8) 선택된 요소에 접근

### getter 메소드와 setter 메소드

선택자에 의해 선택된 요소의 값을 읽거나 설정하기 위해서는 제이쿼리 메소드를 통해 해당 요소에 접근해야만 함

getter 메소드는 선택된 요소에 접근하여 그 값을 읽어오기 위한 메소드임

이러한 getter 메소드는 아무런 인수를 전달하지 않고 호출함

setter 메소드는 선택된 요소에 접근하여 그 값을 설정하기 위한 메소드임

이러한 setter 메소드는 대입하고자 하는 값을 인수로 전달하여 호출함

```jsx
$(function() {

    $("button").on("click", function() {

①      var newText = $("h1").html(); // <h1>요소의 텍스트를 읽어오는 getter 메소드

②      $("#text").html(newText);     // id가 "text"인 요소에 새로운 텍스트를 설정하는 setter 메소드

    });

});
```

### 메소드 체이닝( method chaining )

getter 메소드는 선택된 요소의 값을 읽어서 그 값을 반환함

만약 선택된 요소가 여러 개 존재하면, getter 메소드는 가장 ‘첫 번째 요소’ 의 값만을 반환할 것임

하지만 setter 메소드는 선택된 ‘모든 요소’에 인수로 전달된 값을 설정함

그리고 선택된 모든 요소에 접근할 수 있는 또 다른 제이쿼리 객체를 반환함

이렇게 반환된 제이쿼리 객체를 이용하면 세미클론( ; )을 사용하지 않고도, 곧 바로 다른 제이쿼리 메소드를 호출할 수 있음

이러 방식으로 여러 개의 메소드가 연속으로 호출되는 것을 메소드 체이닝( method chaining ) 이라고함

.find( ), .eq( ), .html( ) 메소드를 연속으로 호출하는 예제임

```jsx
$(function () {
  $("button").on("click", function () {
    // id가 "list"인 요소의 자손 요소 중에서 <li>요소를 모두 선택한 후에,

    // 그 중에서 두 번째 요소의 값을 설정함.

    $("#list").find("li").eq(1).html("두 번째 아이템을 선택했어요!!");
  });
});
```

#### 참고 : eq( ) 메소드는 선택한 요소 중에서 지정된 인덱스에 해당하는 요소를 선택하는 메소드임

메소드 체이닝 도중에 **.end( )** 메소드를 사용하면 바로 이전에 선택했던 요소의 집합을 다시 선택할 수 있음

```jsx
$(function() {

    $("button").on("click", function() {

        $("#list")      // id가 "list"인 요소의 자손 요소 중에서

①          .find("li") // <li>요소를 모두 선택한 후에,

②          .eq(1).html("두 번째 아이템을 선택했어요!!")  // 그 중에서 두 번째 요소의 값을 설정함.

③          .end()      // 다시 id가 "list"인 요소의 자손 요소 중에서 <li>요소를 모두 선택한 후에,

④          .eq(2).html("세 번째 아이템도 선택했어요!!"); // 그 중에서 세 번째 요소의 값을 설정함.

    });

});
```

### .width( ) 메소드와 .height( ) 메소드

제이쿼리에서는 선택한 요소의 너비나 높이를 반환하거나 설정하기 위한 .width( ) 메소드와 .height( ) 메소드를 제공함

```jsx
$(function() {

    $("#getter").on("click", function() {

①      var size = "너비는 " + $("#box").width() + "px이고, 높이는 "

            + $("#box").height() + "px입니다.<br>";

        $("#text").html(size);

    });

    $("#setter").on("click", function() {

②      w = $("#box").width();

③      h = $("#box").height();

④      $("#box").width(w/2).height(h/2);



⑤      var size = "너비는 " + $("#box").width() + "px이고, 높이는 "

⑥          + $("#box").height() + "px로 변경되었습니다.<br>";

        $("#text").html(size);

    });

});
```

### .attr( ) 메소드

선택한 요소의 특정 속성값을 반환하거나 설정하기 위해 사용 됨

```jsx
$(function() {

    $("button").on("click", function() {

        // <img>요소의 src 속성값을 읽어오는 getter 메소드

①      var imgSrc = $("img").attr("src");

        // <img>요소의 src 속성값을 새로운 값으로 설정하는 setter 메소드

②      $("img").attr("src", "/examples/images/img_flag.png");

    });

});
```

### 대표적인 getter 메소드와 setter 메소드

요소에 접근하여 요소의 값을 읽거나 설정할 수 있도록 해주는 대표적인 getter, setter 메소드

---

## 9) 요소의 추가

제이쿼리는 새로운 요소나 콘텐츠를 손쉽게 추가할 수 있도록 여러 메소드를 제공함

### 기존 요소의 내부에 추가

다음 메소드를 사용하면 기존 요소의 내부에 새로운 요소나 콘텐츠를 추가할 수 있음

1. .append( )
2. .prepend( )
3. .appendTo( )
4. .prependTo( )

### .apend( ) 메소드

.append( ) 메소드는 선택한 요소의 ‘마지막’ 에 새로운 요소나 콘텐츠를 추가함

```jsx
$(function () {
  $("button").on("click", function () {
    $("#list").append("<li>새로 추가된 아이템이에요!</li>");
  });
});
```

### .prepend( ) 메소드

.prepend( ) 메소드는 선택한 요소의 ‘처음’ 에 새로운 요소나 콘텐츠를 추가함

```jsx
$(function () {
  $("button").on("click", function () {
    $("li").prepend("새로 추가된 콘텐츠에요!");
  });
});
```

### .appendTo( ) 메소드

.appendTo( ) 메소드는 선택한 요소를 ‘해당 요소의 마지막’ 에 삽입함

그 동작은 .append() 메소드와 같지만, 소스( source )와 타겟( target )의 위치가 서로 반대임

```jsx
$(function () {
  $("#firstBtn").on("click", function () {
    // id가 "list"인 요소의 맨 마지막에 id가 "firstItem"인 요소를 추가함.

    $("#firstItem").appendTo("#list");
  });
});
```

### .prependTo( ) 메소드

.prependTo( ) 메소드는 선택한 요소를 ‘해당 요소의 처음’ 에 삽입함

그 동작은 .prepend() 메소드와 같지만, 소스( source ) 와 타겟( target )의 위치가 서로 반대임

```jsx
$(function () {
  $("button").on("click", function () {
    $("<b>새로 추가된 콘텐츠에요!</b>").prependTo(".item");
  });
});
```

### 기존 요소의 내부에 새로운 요소나 콘텐츠를 추가해주는 메소드

### 기존 요소의 외부에 추가

다음 메소드를 사용하면 기존 요소의 앞이나 뒤에 새로운 요소나 콘텐츠를 추가할 수 있음

1. .before( )
2. .after( )
3. .insertBefore( )
4. .insertAfter( )

### .before( ) 메소드

.before( ) 메소드는 선택한 요소의 ‘바로 앞에’ 새로운 요소나 콘텐츠를 추가함

```jsx
$(function () {
  $("button").on("click", function () {
    // id가 "firstRow"인 요소의 바로 앞에 새로운 <tr>요소를 추가함.

    $("#firstRow").before("<tr><td>새로운 행이에요!</td></tr>");
  });
});
```

### .after( ) 메소드

.after() 메소드는 선택한 요소의 ‘바로 뒤에’ 새로운 요소나 콘텐츠를 추가함

```jsx
$(function () {
  $("button").on("click", function () {
    // id가 "firstRow"인 요소의 바로 뒤에 새로운 <tr>요소를 추가함.

    $("#firstRow").after("<tr><td>새로운 행이에요!</td></tr>");
  });
});
```

### .insertBefore( ) 메소드

.insertBefore( ) 메소드는 선택한 요소를 ‘해당 요소의 앞에’ 삽입함

그 동작은 before( ) 메소드와 같지만, 소스( source )와 타겟( target )의 위치가 서로 반대임

```jsx
$(function () {
  $("button").on("click", function () {
    // id가 "secondColumn"인 요소의 바로 앞에 새로운 <td>요소를 추가함.

    $("<td>새로운 셀이에요!</td>").insertBefore("#secondColumn");
  });
});
```

### .insertAfter( ) 메소드

.insertAfter( ) 메소드는 선택한 요소를 ‘해당 요소의 뒤에’ 삽입합니다.

그 동작은 .after( ) 메소드와 같지만, 소스( source ) 와 타겟( target )의 위치가 서로 반대임

```jsx
$(function () {
  $("button").on("click", function () {
    // id가 "secondColumn"인 요소의 바로 뒤에 새로운 <td>요소를 추가함.

    $("<td>새로운 셀이에요!</td>").insertAfter("#secondColumn");
  });
});
```

### 기존 요소의외부에 새로운 요소나 콘텐츠를 추가해 주는 메소드

### 기존 요소를 포함하는 요소의 추가

다음 메소드를 사용하면 기존 요소를 포함하는 새로운 요소나 콘텐츠를 추가할 수 있음

1. .wrap( )
2. wrapAll( )
3. wrapInner( )

### .wrap( ) 메소드

.wrap( ) 메소드는 ‘선택한 요소’를 포함하는 새로운 요소를 추가함

```jsx
$(function () {
  $("button").on("click", function () {
    // class가 "content"인 각 요소를 포함하는 새로운 요소를 추가함.

    $(".content").wrap("<div class='wrapper'></div>");
  });
});
```

### .wrapAll( ) 메소드

.wrapAll( ) 메소드는 ‘선택한 모든 요소’ 를 포함하는 새로운 요소를 추가함

```jsx
$(function () {
  $("button").on("click", function () {
    // class가 "content"인 모든 요소를 포함하는 새로운 요소를 추가함.

    $(".content").wrapAll("<div class='wrapper'></div>");
  });
});
```

### .wrapInner( ) 메소드

.wrapInner( ) 메소드는 ‘선택한 요소에 포함되는’ 새로운 요소를 추가함

```jsx
$(function () {
  $("button").on("click", function () {
    // class가 "content"인 각 요소에 포함되는 새로운 요소를 추가함.

    $(".content").wrapInner("<div class='wrapper'></div>");
  });
});
```

### 기존 요소를 포함하는 새로운 요소를 추가해주는 메소드

---

## 10) 요소의 복사 및 삭제

### 요소의 복사

다음 메소드를 사용하면 선택한 요소나 콘텐츠를 복사하여 새로운 요소나 콘텐츠를 생성할 수 있음

1. clone()

### .clone( ) 메소드

.clone( ) 메소드는 선택한 요소를 복사하여 새로운 요소를 생성함

```jsx
$(function () {
  $("button").on("click", function () {
    // id가 "firstItem"인 요소를 복사하여 id가 "list"인 요소에 추가함.

    $("#firstItem").clone().appendTo("#list");
  });
});
```

다음 예제는 앞서 살펴본 .appendTo( ) 메소드의 예제임

```jsx
$(function () {
  $("#firstBtn").on("click", function () {
    // id가 "list"인 요소의 맨 마지막에 id가 "firstItem"인 요소를 추가함.

    $("#firstItem").appendTo("#list");
  });
});
```

위의 예제에서 볼 수 있듯이 .clone( ) 메소드는 기존의 HTML 요소를 복사하여 새로운 HTML 요소를 생성할 뿐임

따라서 반드시 .append( ) 메소드나 .appendTo( ) 메소드와 같은 다른 메소드를 이용하여 요소를 추가해야 함

.clone( ) 메소드를 사용하지 않고 .appendTo( ) 메소드만을 사용하면, 기존에 존재하는 HTML 요소를 그대로 추가하는 점이 다름

#### \_참고 : .appendTo( ) 메소드는 선택한 요소를 ‘해당 요소의 마지막’ 에 삽입해 주는 메소드임

## 요소의 대체

다음 메소드를 사용 하면 선택한 요소나 콘텐츠를 지정된 요소나 콘텐츠로 대체할 수 있음

1. replaceAll( )
2. replaceWith( )

### .replaceAll( ) 메소드

.replaceAll( ) ㅔㅁ소드는 선택한 요소를 지정된 요소로 대체함

이 메소드는 인수로 선택자나 제이쿼리 객체, HTML DOM 요소, 배열 등을 전달받을 수 있음

```jsx
$(function () {
  $("button").on("click", function () {
    // class가 "item"인 각 요소를 id가 "firstItme"인 요소로 대체함.

    $("#firstItem").replaceAll(".item");
  });
});
```

### .replaceWith( ) 메소드

.replaceWith( ) 메소드는 선택한 요소를 지정된 요소로 대체함

이 메소드는 인수로 HTML 코드 형식의 문자열이나 제이쿼리 객체, HTML DOM 요소, 배열 등을 전달받을 수 있음

또한, 선택한 요소를 대체할 수 있는 컨텐츠를 반환하는 함수를 인수로 전달받을 수도 있음

.replaceWith( ) 메소드의 동작은 .replaceAll( ) 메소드와 비슷하지만, 소스( source )와 타겟( target ) 의 위치가 서로 반대임

또한, replaceWith( ) 메소드는 지정된 요소로 대체되어 제거된 기존 요소를 반환함

```jsx
$(function () {
  $("button").on("click", function () {
    // class가 "item"인 모든 요소를 id가 "firstItme"인 요소로 대체함.

    $(".item").replaceWith($("#firstItem"));
  });
});
```

#### 참고\_ .replaceAll( ) 메소드와 .replaceWith( ) 메소드는 제거된 요소와 관련된 모든 데이터와 이벤트 핸들러도 같이 제거됨

### 요소의 삭제

다음 메소드를 사용하면 선택한 요소나 콘텐츠를 삭제할 수 있음

1. remove( )
2. detach( )
3. empty( )
4. unwrap( )

### .remove( ) 메소드

```jsx
$(function () {
  $("button").on("click", function () {
    // class가 "content"인 요소 중에서 class가 각각 "first", "second"인 요소를 모두 삭제함.

    $(".content").remove(".first, .second");
  });
});
```

### .detach( ) 메소드

```jsx
$(function () {
  var data;

  $("#detachBtn").on("click", function () {
    data = $(".content").detach(); // class가 "content"인 요소를 모두 삭제함.
  });

  $("#restoreBtn").on("click", function () {
    $("#container").append(data); // detach() 메소드로 삭제되었던 모든 요소를 다시 추가함.
  });
});
```

### .empty( ) 메소드

```jsx
$(function () {
  $("button").on("click", function () {
    $("#container").empty(); // id가 "container"인 요소의 자식 요소를 모두 삭제함.
  });
});
```

### .unwrap( ) 메소드

```jsx
$(function () {
  $("button").on("click", function () {
    $("span").unwrap(); // 모든 <span>요소의 부모 요소를 삭제함.
  });
});
```

[참고링크](http://www.tcpschool.com/jquery/intro)

## jQuery 함수 객체

### var jQuery

```jsx
var jQuery = function (selector, context) {
  return new jQuery.fn.init(selector, context);
};
```

- 내부 코드에서 jQuery.fn.init 생성자 함수를 new keyword를 통해 객체를 생성하여 넘겨줌
- 즉, jQuery(...)를 하면 객체 하나가 리턴된다는 것을 알고 있자.
- 함수를 참조하는 변수 jQuery는 IIFE에 의해 닫힌 스코프에서 선언된 변수임
- 일반적으로 내부 스코프, 닫힌 스코프에서 선언된 변수는 외부에서 접근할 수 없음

### 전역 변수 $, jQuery

- 전역 객체 (window)의 $, jQuery 프로퍼티에 jQuery 함수를 참조함

```jsx
if (  /*... code/*/ ){

    window.jQuery = window.$ = jQuery;

}
```

- 전역 객체의 프로퍼티가 된다는 것은 전역변수가 된다는 의미임
- 이후 javascript에서는 jQuery(...),$(...)를 통해 접근할 수 있음
- 이러한 원리 덕분에 $(...) 형태로 축약해서 jQuery의 기능을 호출할 수 있음

### jQuery.fn.init

- jQuery라는 변수를 선언하여 function 객체를 참조하는것을 알 수 있음

```jsx
var jQuery = function (selector, context) {
  return new jQuery.fn.init(selector, context);
};
```

- 위처럼 내부 코드에서는 jQuery.fn.init 생성자 함수를 new keyword를 통해 객체를 생성하여 넘겨줌
- jQuery(...)하면 즉, $(...)하면 객체 하나가 리턴된다는 것을 알게됨
- JQuery.fn.init(...)는 결론적으로 선택자를 인자로 받아 jQuery.fn.init 함수를 이용해 DOM 요소를 선택함
- jQuery.fn.init 함수에서는 jQuery 프로토타입 객체를 반환하는데, 이 객체에는 선택된 DOM 요소가 포함되어 있음

[참고포스팅](https://boycoding.tistory.com/47)
