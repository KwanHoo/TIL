# _CASE WHEN 표현식 사용법, ANSI SQL_

- SQL SERVER에서는 조건에 따라 서로 다른 값을 반환할 수 있는 CASE 표현식을 사용할 수 있음
- 프로그래밍 언어에서 IF문과 비슷하다고 생각하면됨
- 오라클 DECODE 함수와 비슷한 기능을 함
- CASE 표현식은 ANSI SQL 이므로 대부분의 데이터베이스에서 동일하게 사용할 수 있음

## ANSI SQL이란?

- DBMS(오라클, MYSQL, DB2 등)들에서 각기 다른 SQL을 사용함
  - 미국 표준 협회에서 이를 표준화하여 표준 SQL문을 정립 시켜 놓음

## ANSI SQL 특징

1. 표준 SQL문ㅇ기 때문에 DBMS의 종류에 제약을 받지 않음
   - 즉, 특정 벤더에 종속적이지 않아 다른 벤더의 DBMS로 교체하더라도 빠르게 다른 벤더사를 이동할 수 있음
   - 특정 DBMS의 이탈이 가속되는 것도 ANSI SQL의 영향이 크다고 할 수 있음
2. 테이블간의 Join 관계가 FROM 에서 명시되기 때문에 WHERE 문에서 조건만 확인하면 됨
   - 즉, 가독성이 일반 쿼리문 보다 좋음

[참고 링크](https://velog.io/@gillog/ANSI-SQL%EC%9D%B4%EB%9E%80)

## CASE WHEN THEN

```SQL
CASE WHEN '조건식' THEN '반환값'
    WHEN '조건식2' THEN '반환값2'
    ELSE 'N/A' /*조건에 만족하지 않을 경우 반환값*/
END
```

[참고링크](https://gent.tistory.com/435)
