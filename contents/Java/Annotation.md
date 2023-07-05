# 자바 어노테이션

## Annotation

- 메타 데이터( metadata ) 라고 볼 수 있음
  - metadata : 어플리케이션이 처리할 데이터가 아니라 컴파일 과정과 실행 과정에서 코드를 어떻게 컴파일하고 처리할 것인지 알려주는 정보

### 어노테이션 작성 형태

```java
// 어노테이션 작성 형태
@AnnotationName
```

### 어노테이션 용도

- 컴파일러에게 코드 문법 에러를 체크하도록 정보 제공
- 소프트웨어 개발 툴이 빌드 또는 배치 시 코드를 자동으로 생성할 수 있도록 정보를 제공
- 실행 시 (런타임 시) 특정 기능을 실행하도록 정보 제공

### @Override 어노테이션

- 컴파일러에게 코드 문법 에러를 체크하도록 정보를 제공함
- 메소드 선언 시 사용되며, 메소드가 오버라이드(재정의)된 것임을 컴파일러에게 알려주어 컴파일러가 오버라이드 검사를 하도록 함
- 오버라이드가 되지 않았다면, 컴파일러는 에러를 발생시킴

- 어노테이션은 자동으로 XML 설정 파일을 생성하거나, 배포를 위해 JAR 압축 파일을 생성하는데 사용됨
- 실행 시 크랠스의 역할을 정의 하기도 함

## 1. 어노테이션 타입 정의와 적용

- 인터페이스 정의하는 것과 유사함
- @interface를 사용해서 어노테이션을 저의하며, 그 뒤에 사용할 어노테이션 이름이 옴

```java
public @interface AnnotationName {

}
// 이렇게 정의된 어노테이션은 아래와 같이 사용됨
@AnnotationName
```

- 어노테이션은 엘리먼트(element)를 멤버로 가질 수 있음
- 각 엘리먼트는 타입과 일므을 구성되며, 디폴트 값을 가질 수 있음

```java
public @interface AnnotationName {
    타입  elementName() [default 값] ; // 엘리;먼트 선언
    ...
}
```

- 엘리먼트의 타입으로 int, double 같은 기본타입, String, 열거타입, Class 타입 그리고 이들의 배열 타입을 사용할 수 있음
- 엘리먼트의 이름 뒤에는 메소드를 작성하는 것처럼 () 를 붙어야함

```java
//ex) String  타입 엘리먼트, int 타입 엘리먼트
public @interface AnnotationName {
    String elemnetNAme1()
    int elementName2() default 5;
}

// 이렇게 정의한 어노테이션을 코드에 적용할 때는 아래와 같이 기술
@AnnotationName(elementName1 = "값", elementName2 = 3);
//or
@AnnotationANme(elementName1 = "값");
```

- elementName1은 디폴트 값이 없기 때문에 반드시 값을 기술해야 하고, elementNAme2는 디폴트 값이 있기 때문에 생략 가능함

- 어노테이션은 기본 엘리먼트인 value를 가질 수 있음

```java
public @interface AnnotationName{
    String value() ; // 기본 엘리먼트 선언
    int elementName() default 5;
// value 엘리먼트를 가진 어노테이션을 코드에서 적용할 때는 아래와 같이 값만 기술할 수 있음. 이값은 기본 엘리먼트인 value  값으로 자동 설정 됨

@AnnotationName("값");
// 만약 value 엘리먼트와 다른 엘리먼트의 값을 동시에 주고 싶다면, 아래와 같이 정상적 방법으로 지정함
@AnnotationName(value = "값", elementName = 3);
}
```

[참고포스팅](https://kephilab.tistory.com/55)
