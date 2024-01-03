# DB 기본구문 \_ SQool Tutorial 참고

### 1. SELECT

- 데이터를 조회하거나 산술식, 함수 등을 실행할 때 사용함
  - ( 에스터리스크, 별표 ) 는 모든 항목을 다 출력할 때 사용

```sql
SELECT * FROM Student;

SELECT 이름, 학과 FROM student;
```

### 2. DISTINCT

- 중복값을 제거함

```sql
SELECT DISTINCT 학과번호
FROM subject;
```

### 3. ORDER BY

- 출력 결과 정렬
  - 오름차순 : ASC ( 기본, 작은 수에서 큰 수로, Ascending)
  - 내림차순 : DESC ( 큰 수에서 작은 수로, Descending)

```sql
-- 내림차순
SELECT 학번, 학년, 이름
FROM student
ORDER BY 학년 DESC;

-- 오름차순
SELECT 학번, 학년, 이름
FROM student
ORDER BY 학년 ASC;
```

### 4. AS

- 별칭

```sql
SELECT 학번, 이름 AS 성명, 연락처 AS 휴대폰번호
FROM student;

-- AS 없이도 사용가능
SELECT 학번, 이름 성명, 연락처 휴대폰번호
FROM student;
```

### 5. 연결 연산자

- Oracle : ||
- MsSQL : +
- MySQL : 공백
- CONCAT 함수는 공통으로 사용 가능

```sql
-- ORACLE
SELECT 학년 || ' ' || 학과 || ' ' || 학년 AS Student_Info FROM student;
```

### 6. 논리 연산

- NOT, AND , OR
- True는 1, False는 0으로 and는 곱으로 or는 덧셈으로 이해

```sql
-- AND
SELECT *
FROM student
WHERE 학번 LIKE '2018%'
AND 마일리지 >= 100;

-- OR
SELECT *
FROM student
WHERE 마일리지 >= 100
AND 학번 LIKE '2018%' OR 학번 LIKE '2020%';

-- NOT
SELECT *
FROM student
WHERE 마일리지 >= 100
AND NOT (학번 LIKE '2019%' OR 학번 LIKE '2020%');
```

- <> : 같지 않다

### 7. BETWEEN 연산

- BETWEEN A AND B : A와 B를 포함한 사이의 값

```sql
SELECT 학번, 일학년일학기
FROM grade
WHERE 일학년일학기 BETWEEN 3.0 AND 4.0;

-- 위와 같음
SELECT 학번, 일학년일학기
FROM grade
WHERE 일학년일학기 >= 3.0 AND 일학년이학기 <= 4.0;
```

### 8. IN 연산

- IN A : A안에 값과 일치하는 값을 조회

```sql
SELECT 학번, 이름, 학과
FROM student
WHERE 학과 IN ('물리학과', '화학과');
```

### 9. LIKE 연산

- 와일드 카드 사용하여 비교문자와 형태가 일치

```sql
-- %
SELECT 학년, 이름, 지도교수
FROM student
WHERE 지도교수 LIKE '%모리';

-- _
SELECT 학년, 이름, 연락처, 지도교수
FROM student
WHERE 지도교수 LIKE '환__';
```

### 10. IS NULL

- 필드의 값이 NULL인 경우를 조회하고자 할 때 사용
  - NULL은 아예 값이 없어 알 수 없는(unknown)값
    - 0이나 공백은 NULL이 아님
  - NULL이 아닌 값을 조회하고자 한다면 NOT연산자와 함께 IS NOT NULL 연산자 사용

```sql
-- IS NULL
SELECT *
FROM scholarship
WHERE 성적장학금 IS NULL;

-- IS NOT NULL
SELECT *
FROM scholarship
WHERE 성적장학금 IS NOT NULL AND 근로장학금 IS NOT NULL AND 국가장학금 IS NOT NULL;
```

### 11. WHERE

- 데이터를 검색, 갱신, 삭제할 때 특정 데이터에 대한 조건을 설정할 때 사용하는 구문!!!
  - 결합 가능한 연산자의 종류 : 비교연산자, SQL연산자, 논리연산자 등
    - 비교연산자 : =, <, >, ≠, ≥, ≤
    - SQL연산자 : BETWEEN
    - 논리 연산자 : AND, OR

### 12. INSERT

- 기존 테이블에 행을 삽일할 때 사용하는 구문

```sql
INSERT INTO [테이블명] ([컬럼1], [컬럼2], ...)
VALUES ([값1, 값2, ...]);
```

### 13. UPDATE

- 데이터를 수정할 수 있음
- 이 행위는 되돌릴 수 없음
- WHERE절이 탐색 조건을 충족시키는 모든 행에 대해 값을 변경함

```sql
UPDATE [테이블명]
SET [컬럼='변경할값'], [컬럼='변경할값'], ...
WHERE [조건];
```

### 14. DELETE

- DELETE 문을 사용하면 테이블에서 행을 제거할 수 있음
- WHERE 절을 통해 조건을 주지 않으면 테이블의 모든 행이 제거됨 !!!!!

```sql
-- 레코드 삭제
DELETE FROM student WHERE Grade = 4;

-- 테이블 삭제
DELETE FROM student;
```

[참고포스팅](https://sqlschool.co.kr/pagetutorial/)
