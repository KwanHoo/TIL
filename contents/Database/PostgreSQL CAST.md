# _PostgreSQL CAST, ::_

## Casting

- PostgreSQL에서 타입을 변경하는 함수와 연산자

### CAST()

- CAST()를 사용해서 데이터 타입을 변환할 수 있음

```spl
CAST(value AS type)

-- 예시
CAST(1234 AS TEXT)
```

### ::

- :: 연산자를 사용해서 데이터 타입을 변환할 수 있음
- :: 연산자는 PostgreSQL에서만 사용됨
  - SQL 스탠다드를 따르지 않음

```sql
value::type

-- 예시
1234::TEXT
```

[참고 포스팅](https://brownbears.tistory.com/309)
[참고 포스팅](https://dullyshin.github.io/2019/08/30/PostgreSQl-cast/)
