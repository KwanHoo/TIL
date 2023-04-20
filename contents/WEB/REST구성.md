# _REST, URI 설계시 주의점_

## REST 구성

- 자원 (RESOURCE) - URI
- 행위(Verb) - HTTP METHOD
- 표현(Representations)

### REST의 특징

1. Uniform (유니폼 인터페이스)

2. Stateless(무상태성)

3. Cacheable(캐시 가능)

4. Self-descriptiveness (자체 표현 구조)

5. Client - Server 구조

6. 계층형 구조

### REST API 디자인 가이드

1. URI는 정보의 자원을 표현해야함

2. 자원에 대한 행위는 HTTP Method(GET, POST, PUT, DELETE)로 표현함

---

## URI 설계시 주의할 점

1. 슬래시 구분자(/)는 계층 관계를 나타내는 데 사용

2. URI 마지막 문자로 슬래시(/)를 포함하지 않음

3. 하이픈(-)은 URI 가독성을 높이는데 사용

4. 밑줄(\_)은 URI에 사용하지 않음

5. URI 경로에는 소문자가 적합함

6. 파일 확장자는 URI에 포함시키지 않음

[참고 포스팅](https://inpa.tistory.com/entry/WEB-%F0%9F%8C%90-REST-API-%EC%A0%95%EB%A6%AC)
