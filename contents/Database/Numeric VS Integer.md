# _PostgreSQL Numeric과 Integer 차이점_

### Numeric

- 정수 또는 소수 값을 저장
- Oracle 에서의 Number, Mysql Decimal와 같은 의미로 생각가능

```SQL
Numeric(p,s) 실수(10진수) p:, s:소수점 자리수
-- 예시
numeric(7,3) -> 전체자리는 7자리, 소수점 3자리를 의미함
```

### Integer

- 오직 정수만 저장
- 이외에 smallint, bigint 등 PostgreSQL의 다양한 데이터 타입 존재
  [참고 포스팅](https://kimseungjae.tistory.com/8)
  [참고 포스팅](https://velog.io/@moorekwon/PostgreSQL-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%83%80%EC%9E%85)
