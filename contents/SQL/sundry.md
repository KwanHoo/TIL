# 잡다한 이것저것

## 서브쿼리 (where절 / from절 / select 절)

쿼리 안에 있는 쿼리

### FROM 절 서브쿼리

- FROM 절 안에 들어 잇음
- 인라인 뷰 (inline views)
- 두 정보가 서로 다른 테이블에 들어있는 겨웅 두 테이블로 부터 각각 원하는 데이터를 불러ㅗ아 출력하는 쿼리

```sql
select A.사업부,A.창고코드,B.한글명 AS 창고명,A.발생년월, A.출고수량
from 영_매장출고반품_V A, (select *
                            from 공_공통코드
                            where 업무구분= 'SM'
                            AND 코드구분 = '510') B
WHERE A.창고코드 = B.코드
AND A.사업부 = 'M'
AND 출고일자 BETWEEN '20200101' AND '20200631';
```

### GROUP BY

- 특정 칼럼을 그룹화 하는 GROUP BY
- 특정 칼럼을 그룹화한 결과에 조건을 거는 HAVING
- WHERE 랑 HAVING이 헷갈릴 수 있음
- WHERE는 그룹화하기 전이고, HAVAING은 그룹화 후에 조건임

> 컬럼 그룹화

```sql
select 컬럼 from 테이블 groupg by 그룹화할 칼럼;
```

> 조건 처리 후에 컬럼 그룹화

```sql
select 컬럼 from 테이블 where 조건식 group by 그룹화할 칼럼;
```

> 칼럼 그룹화 후에 조건 처리

```sql
select 칼럼 from 테이블 group by 그룹화할 컬럼 having 조건식;
```

> 조건 처리 후에 컬럼 그룹화 후에 조건 처리

```sql
select 컬럼 from 테이블 where 조건식 group by 그룹화할 컬럼 having 조건식;
```

> Order by가 존재하는 경우

```sql
select 컬럼 from 테이블 [where 조건식]
group by 그룹화할 컬럼 [having 조건식] order by 컬럼1 [, 컬럼2, 컬럼3 ...];
```

## PIVOT 피봇

- 행으로 나열되어 있는 데이터를 열로 나열하여 보기 쉽게 가공하는 것
- 피봇은 세로행을 가로 열로 가독성을 향상함
- 대상 필드의 값 목록을 새로운 열로 만들고 각 열에대해 집계 함수를 호출하여 결과셋을 만듬

## dual (듀얼 테이블)

- oracle 자체에서 제공되는 테이블
- 간단하게 함수를 이용하여 계산 결과값을 확인할 때 사용하는 테이블임
- 오직 한 행, 한 칼럼을 담고 있는 dummy 테이블
- 테이블 생성 없이 가상 데이터를 만들어 테스트 해볼 때 이용 가능!

## UNION

- 두 개의 SELECT 결과를 합칠 수 있음
- 합친 결과에서 중복되는 행은 하나만 표시됨

```sql
SELECt * FROM A
UNION (ALL)
SELECT * FROM B
```

- union 하기 위한 조건 : 칼럼의 갯수, 타입이 같아야함

### UNION ALL

- union all은 중복을 제거하지 않음

## COUNT 데이터 갯수 세기 → DISTINCT 중복 제거

```sql
-- 카운트로 갯수
SELECT COUNT (COLUMN NAME) FROM TABLE NAME
```

- 중복 제거

```sql
SELECT COUNT (DISTINCT COLUMN NAME) FROM TABLE NAME
```

- DISTINCT는 중복을 제거 하기 위해서 사용됨

## DECODE

- 프로그래밍에서의 if else 와 비슷한 기능 수행함
  - DECODE ( 컬럼, 조건1, 결과1, 조건2, 결과2, 조건3, 결과3 …. )
    ![image](https://user-images.githubusercontent.com/49335804/218313903-a2d4ac8b-6e35-4b5d-97a6-8fba94463324.png)

```sql
WITH temp AS (
    SELECT 'M' gender FROM dual UNION ALL
    SELECT 'F' gender FROM dual UNION ALL
    SELECT 'X' gender FROM dual
)

SELECT gender
     , DECODE(gender, 'M', '남자', 'F', '여자', '기타') gender2
  FROM temp
```

## WITH 문

- 이름을 가진 서브 쿼리를 정의한 후 사용하는 구문
- 쿼리의 전체적인 가독성을 높이고, 재사용할 수 있는 장점이 있음
- 계층형 쿼리를 구현할 수 있음
- 오라클에서는 한번만 사용되면 Inline View, 두번 이상 사용되면 Materialize view로 처리함

WITH [별명] AS ( SUB QUERY)

```sql
WITH [ 별명1 ] [ (컬럼명1 [,컬럼명2]) ] AS (
    SUB QUERY
)[, 별명2 AS ... ]
MAIN QUERY
```

- 컬럼명 생략 가능
- 쉼표(,) 로 구분하여 여러개 정의할 수 있음
- 먼저 생성된 SubQuery는 나중에 생성하는 서브쿼리에서 사용할 수 있음

  - [ 별명2 ]에서 [ 별명1 ] 을 사용할 수 있음

- WITH 문은 가독성이나 재사용성 때문에 많이 사용되는 것도 있지만, 계층형 쿼리를 만들기 위해서도 반드시 필요함
