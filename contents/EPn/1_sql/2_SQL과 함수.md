# SQL과 함수

### COUNT

- 검색한 결과의 데이터의 개수를 가져오는 내장함수
- NULL인 데이터는 제외

```SQL
SELECT COUNT(id) FROM book;
-- book 테이블 안에 있는 id 컬럼의 개수를 검색

SELECT COUNT(*) FROM book;
-- 검색할 데이터에 *을 입력하면 모든 데이터 검색
```

### LIMIT

- 테이블에서 출력하고자 하는 데이터의 개수를 제한하는 명령

```SQL
-- book 테이블에서 데이터를 5개만 가져오기
SELECT * FROM book LIMIT 5;

-- 2번째 데이터부터 5개를 가져오기
SELECT * FROM book LIMIT 1, 5;
```

### SUM & AVG

- SUM : 지정한 컬럼들의 값을 모두 더하여 총점을 구해주는 내장함수
- AVG : 지정한 컬럼들의 평균값을 구해주는 내장함수

```SQL
SELECT SUM(math) FROM grade;
-- 데이터의 합 구함

SELECT AVG(korean), AVG(english), AVG(math) FROM grade;
-- 데이터의 평균 구함
```

### MAX & MIN

- MAX : 테이블에 존재하는 데이터에서 최대값을 가져오는 내장함수

  - 숫자형 뿐만 아니라 문자형도 가능

- MIN : 테이블에 존재하는 데이터에서 최솟값을 가져오는 함수
  - 숫자형 뿐만 아니라 문자형도 가능

```SQL
SELECT MAX(korean) FROM grade;
-- 원하는 데이터의 최댓값을 구할 수 있음

SELECT MIN(english) FROM grade;
-- 원하는 데이터의 최솟값을 구할 수 있음
```

참고 : 엘리스
