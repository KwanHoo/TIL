# DB 조건 \_ SQool Tutorial 참고

### 1. 조건문

- ORACLE : DECODE, CASE WHEN
- MsSQL : CASE WHEN
- MySQL : CASE WHEN, IF
- SQLite : CASE WHEN

CASE WHEN

- 조건에 맞는 데이터를 가져오고 싶을 때 사용하는 구문

```sql
SELECT [컬럼명]
CASE
    WHEN [조건1] THEN [결과1]
    WHEN [조건2] THEN [결과2]
    ELSE [결과3]
END [결과를 나타낼 컬럼명]
FROM [테이블명]
```

### 2. JOIN

- 관계형 데이터베이스 시스템상에서 기준을 가지고 데이터를 합치는 것을 뜻함
- INNER JOIN, LEFT JOIN, RIGHT JOIN, OUTER JOIN 등 존재

```sql

-- INNER JOIN : A,B 교집합
SELECT * FROM TableA A
INNER JOIN TableB B ON
A.key = B.key

-- LEFT JOIN
SELECT * FROM TableA A
LEFT JOIN TableB B ON
A.key = B.key

-- A-B
SELECT * FROM TableA A
LEFT JOIN TableB B ON
A.key = B.key WHERE B.key IS NULL

-- RIGHT JOIN
SELECT * FROM TableA A
RIGHT JOIN TableB B ON
A.key = B.key

-- B-A
SELECT * FROM TableA A
RIGHT JOIN TableB B ON
A.key = B.key WHERE A.key IS NULL

-- FULL OUTER JOIN : A,B 합집합
SELECT * FROM TableA A
FULL OUTER JOIN TableB B ON
A.key = B.key

-- A-B 교집합 B-A
SELECT * FROM TableA A
FULL OUTER JOIN TableB B ON
A.key = B.key WHERE A.key IS NULL
OR B.key IS NULL
```

### 3. UNION

- 데이터를 결합함

```sql
SELECT [컬럼명]
FROM [테이블명]
UNION
SELECT [컬럼명]
FROM [테이블명]

-- UNION ALL : 데이터 결합시 중복을 허용
SELECT [컬럼명]
FROM [테이블명]
UNION ALL
SELECT [컬럼명]
FROM [테이블명]
```

### 4. GROUP BY

- 특정 열을 기준으로 그룹화 하여 다른 특정 열에 붙일 때 사용함
- 그룹함수를 사용할때 GROUP BY 필수!!

```sql
-- COUNT()
SELECT 학년, COUNT(학년) AS "학년별 학생 수"
FROM Student
GROUP BY 학년

-- AVG()
SELECT 학년, AVG(마일리지) AS "학년별 마일리지 평균"
FROM student
GROUP BY 학년;
```

### 5. HAVING

- 그룹화된 데이터에 조건을 부여함
- GROUP BY 절과 같이 사용

```sql
SELECT 학년, COUNT(학년) AS "학년별 학생 수"
FROM Student
GROUP BY 학년
HAVING "학년별 학생 수" < 25

SELECT 학과, AVG(마일리지)
FROM student
GROUP BY 학과
HAVING 학년 > 2;
```

### 6. EXISTS

- 서브 쿼리가 참일 경우 참을, 거짓일 경우 거짓을 반환함

```sql
SELECT 이름
FROM student
WHERE EXISTS (SELECT 학번 FROM scholarship WHERE student.학번 = scholarship.학번 AND 학년 < 3);
```

### 7. ALL, ANY

- ALL : 서브 쿼리가 모두 참이어야 참을 반환함
- ANY : 서브 쿼리가 하나라도 참이라면 참을 반환

```sql
SELECT 이름
FROM student
WHERE 학번 IN (SELECT 학번 FROM grade WHERE 1학년1학기 > 4);

SELECT 학번, 이름
FROM student
WHERE 학번 = ANY(SELECT 학번 FROM grade WHERE 1학년1학기 > 4);
```

[참고포스팅](https://sqlschool.co.kr/pagetutorial/)
