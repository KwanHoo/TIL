# Spring Intro \_ JPA 설치 및 실행

## Spring

- Spring by VMware Tanzu
- VM : 가상머신
- 스프링은 VMware가 바탕임

- microservices
- reactive
- cloud
- web apps
- serverless
- event driven
- batch

### 서버

- 또 하나의 PC??
- 제공자
- PC의 데이터를 가져갈 수 있게 열어주면 서버임 (장비를 오픈 하면 서버임)
  - 포트 : 들어오는 입구 (포트 번호 : 8080, 3000, … )
- 포트를 열어 놓으면 그거를 타고 들어 올 수 있음

  - 그 문을 통해서 들어오면 거기에 열어둔것만 볼 수 있게 권한설정
  - +데이터 양 증가 → 서버관리

- Java → 서버 개발에 왜 많이 사용하는가?? 왜 우리나라는??
- 대중적이니깐 : 개발자 = Java
- c를 사용해서 만든 대표적인 언어가 Java
- 왜 객체지향으로 만들어야 했는가?
- 왜 프로그램이 발전하는가?
  - 1. 군사목적 → 과거 빠른 통신 위해
  - 2. 유흥 → 게임산업 →블럭깨기→→ 멀티 플레이 / 롤 플레이 (인스턴스 개념 도입됨)
    - ex) 마인크래프트 : java ⇒ 스웨덴에서 만들어서 MS가 삼

## Spring Data JPA (Java Persistence Api)

[참고링크](https://spring.io/projects/spring-data-jpa)

- java는 객체 중심
- DB는 표 중심

1. 객체랑 표가 안맞음

2. mybatis → sql → sql을 자동으로 써주는게 있으면 좋겠다!! → 하이버네이트 (게빈킹!!)

### 하이버네이트

- 자바 언어를 위한 객체 관계 매핑 프레임워크
- 클래스가 그대로 DB로 쓸 수 있으면 좋겠다
- Hibernate ORM → JPA
- jar : 자르 / war : 와르
