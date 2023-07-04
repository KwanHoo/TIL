# ISNULL 함수

## MSSQL NULL 값 체크

- ISNULL 함수는 MSSQL의 내장함수이며 칼럼이 NULL값일 경우 다른값으로 대체할 수 있는 기능이 있음
- DB를 사용하다보면 파라미터로 NULL 값이 오거나 칼럼안에 NULL 값이 들어있는 등 경우에 따라 NULL 값을 적절히 처리해줘야하는 경우가 많은데 이럴때 유용하게 쓰일수 있는 함수임

```sql
-- 문법
ISNULL (칼럼, 칼럼이 NULL 일 경우 대체할 값)
-- 예시
ISNULL (test, 0)
/*(ISNULL(@PARAMETER, '' ) = '' )*/
```

### 참고 예제

1. 부서(DEPT)를 검색하되 부서가 NULL 값이면 '부서없음'으로 검색하기

```sql
SELECT
    ISNULL (DEPT, '부서없음') AS DPET
FROM
    TABLE
```

2. 파라미터와 동일한 이름(NAME) 출력 파라미터가 NULL 값이면 전체 출력

```SQL
DECLARE
@NAME NVARCHAR(10)

SELECT
    *
FROM
    MY_TABLE
WHERE
    ISNULL(@NAME, '') = '' OR @NAME = NAME
```

[참고포스팅](https://coding-factory.tistory.com/98)
