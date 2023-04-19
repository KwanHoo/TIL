# _MVC와 API_

## MVC와 템플릿 엔진

- MVC란 Model, View, Controller의 총칭
  - Model : 의미 있는 비즈니스 로직을 담당하는 계층
  - View : 화면을 그리는 책임만을 담당하는 계층
  - Controller : 클라이언트의 요청을 받아서 적절한 서비스계층을 호출하고, 그 결과를 반환하는 책임을 담당하는 계층
- MVC 구조와 템플릿 엔진간의 연계 방식

1. 웹브라우저(클라이언트)에서 컨텐츠 요청
   1. Ex : localhost:8080/hello-mvc?name=catsbi
2. Request Path에 매핑되는 컨트롤러 메서드 검색 후 호출
   1. Ex : @GetMapping(”hello-mvc”) public String helloMVC(…){…}
3. 실행된 메서드는 작성된 로직 수행 후 ViewResolver에게 렌더링 될 View 파일 경로/이름 반환
4. 템플릿 엔진처리(ex:Thymleleaf)로 HTML 파싱 된 소스 파일을 클라이언트에게 반환
5. 웹 브라우저(클라이언트)는 해당 HTML 파일을 사용자에게 보여줌

## API

- ViewResolver를 사용하여 사용자에게 보여지는 화면(Ex : HTML) 소스를 반환하지 않음
- HTTP의 Body 영역에 문자 내용을 직접 반환함
- 스프링에서는 애너테이션 기반으로 이런 동작을 제어할 수 있음
  - 매서드 단위는 @ResponseBody를 사용하면 값을 그대로 Body에 담아 반환함
  - 클래스 단위는 @RestController를 사용하면 값을 그대로 Body에 담아 반환함
- ViewResolver 대신 HttpMessageConverter 가 동작함
- 지금은 거의 대부분 JSON 형식으로 반환을 하는 추세임
