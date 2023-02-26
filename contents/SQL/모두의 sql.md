# _모두의 SQL 메모_

## SQL 명령어의 분류

#### DML (Data Manipulation Language)

- SELECT, INSERT, UPDATE, DELETE

#### DDL (Data Definition Language)

- CREATE, ALTER, DROP, RENAME, TRUNCATE

#### DCL (Data Control Language)

- GRANT, REVOKE

#### TCL (Transaction Control Language)

- COMMIT, ROLLBACK, SAVEPOINT

## SQL 연산자의 종류

#### BETWEEN a AND b

- a와 b 사이에 값이 있다 ( a, b 값 포함)

#### IN (list)

- list 중 어느 값이라도 일치한다

#### LIKE '비교문자'

- 비교 문자와 형태가 일치한다 ( %, \_ 사용 )

#### IS NULL

- null 값을 갖는다

## 부정 연산자의 종류

### 부정비교

#### !=

- 같지않다

#### <>

- 같지않다 ( ISO 표준 )

#### NOT 열 이름 =

- ~ 와 같지 않다

#### NOT 열 이름 >

- ~ 보다 크지 않다

### 부정 SQL

#### NOT BETWEEN a AND b

- a와 b 사이에 값이 없다

#### NOT In ( list )

- list 값과 일지하지 않는다

#### IS NOT NULL

- null 값을 갖지 않는다

---

## 데이터 타입의 종류

### CHAR(n)

- n 크기만큼 고정 길이의 문자 타입을 저장한다
- 최대 2,000 바이트( byte ) 까지 저장할 수 있음

### VARCHAR2(n)

- n 크기 만큼 가변 길이의 문자 타입을 저장함
- 최대 4,000 바이트까지 저장할 수 있음

### NUMBER(p, s)

- 숫자 타입을 저장함 (p : 정수 자리수, s : 소수 자리수)

### DATE

- 날짜 타입을 저장함
- 9999년 12월 31일까지 저장할 수 잇음

---

## 단일 행 함수의 종류

### 문자 타입 함수

- 문자를 입력받아 문자오 숫자를 반환함

### 숫자 타입 함수

- 숫자를 입력받아 숫자를 반환함

### 날짜 타입 함수

- 날짜에 대해 연산함
- 숫자를 반환하는 MONTHS_BETWEEN 함수를 제외한 모든 날자 타입 함수는 날짜 값을 반환함

### 변환 타입 함수

- 임의의 데이터 타입의 값을 다른 데이터 타입으로 변환함

### 일반 함수

- 그 외 NVL, DECODE, CASE WHEN, 순위 함수 등

---

## 문자 함수의 종류

### LOWER

- 값을 소문자로 변환함
- LOWER('ABCE') -> abcd

### UPPER

- 값을 대문자로 변환함
- UPPER('abcd') => ABCD

### INITCAP

- 첫 번째 글자만 대문자로 변환함
- INITCAP('abcd') => Abcd

### SUBSTR

- 문자열 중 일부분을 선택함
- SUBSTR('ABC', 1, 2) => AB

### REPLACE

- 특정 문자열을 찾아 바꿈
- REPLACE('AB', 'A', 'E') => EB

### CONCAT

- 두 만자열을 연결한다 ( || 연산자와 같음)
- CONCAT( 'A', 'B' ) => AB

### LENGTH

- 문자열의 길이를 구함
- LENGTH('AB') => 2

### INSTR

-명명된 문자의 위치를 구함

- INSTR( 'ABCD', 'D' ) => 4

### LPAD

- 왼쪽부터 특정 문자로 자리를 채움
- LPAD( 'ABCD', 6, '\*' ) => \*\*ABCD

### RPAD

- 오른쪽부터 특정 문자로 자리를 채움
- RPAD( 'ABCD', 6, '$' ) => ABCD$$

### LTRIM

- 주어진 문자열의 왼쪽 문자를 지움
- LTRIM('ABCD', 'AB') => CD

### RTRIM

- 주어진 문자열의 오른쪽 문자를 지움
- RTIM('ABCD', 'CD' ) => AB

---

## DAUL 테이블

- DUAL 테이블은 더미라는 하나의 열과 하나의 'X' 데이터 값을 갖고 있는 테이블임
- 임의의 값을 알고자 하거나 특정 테이블을 참고하지 않아도 될 때 유용한 테이블임
  - 단순히 지정 문자를 출력하고자 할 때 혹은 오늘의 날짜를 알고 싶을 때는 특정 테이블을 참조할 필요가 없음
  - 이때 사용하는 것이 DUAL 테이블임

---

## 숫자 타입 함수의 종류

### ROUND

- 숫자를 반올림함
- 0이 소수점 첫째 자리임
- ROUND(15.351, 0) => 15

### TRUNC

- 숫자를 절삭함
- 0이 소수점 첫째자리임
- TRUNC(15.351, 1) => 15.3

### MOD

- 나누기 후 나머지를 구함
- MOD(15, 2) => 1

### CEIL

- 숫자를 정수로 올림함
- CEIL(15.351) => 16

### FLOOR

- 숫자를 정수로 내림
- FLOOR(15.351) => 15

### SIGN

- 양수(1), 음수(-1), 0 인지를 구분하여 출력함
- SIGN(15) => 1

### POWER

- 거듭제곱을 출력함
- POWER(2, 3) => 8

### SQRT

- 제곱근을 출력함
  -SQRT(4) => 2

---

## 날짜 함수의 종류

### MONTH_BETWEEN

- 두 날짜 사이의 월수를 계산함
- MONTHS_BETWEEN( SYSDATE, HIRE_DATE ) => 171.758

### ADD_MONTHS

- 월은 날짜에 더함
- ADD_MONTHS( HIRE_DATE, 5 ) => 03/11/17

### NEXT_DAY

- 명시된 날짜로부터 돌아오는 요일에 대한 날짜를 출력함
  - SUNDAY:1, MONDAY:2, ...
- NEXT_DAY( HIRE_DATE, 1 ) => 03/06/22

### LAST_DAY

- 월의 마지막 날을 계산함
- LAST_DAY( HIRE_DATE ) => 03/06/30

### ROUND

- 날짜를 가장 가까운 연도 또는 월로 반올림함 (YEAR or MONTH)
- ROUND( HIRE_DATE, 'MONTH' ) => 03/07/01

### TRUNC

- 날짜를 가장 가까운 연도 또는 월로 절삭함 ( YEAR or MONTH )
- TRUNC( HIRE_DATE, 'MONTH' ) => 03/06/01

---

## 수동 데이터 타입 변환 함수

### TO_CHAR

- 숫자, 문자, 날짜 값을 지정 형식의 VARCHAR2 타입으로 변환함

### TO_NUMBER

- 문자를 숫자 타입으로 변환함

### TO_DATE

- 날짜를 나타내는 문자열을 지정 형식의 날짜 타입으로 변환함

---

## NOT NULL 값 처리하기

- 특정 열의 행에 대한 데이터 값이 덦다면 데이터 값은 null 이 됨
- null은 그 자체로 의미가 있는데 '값이 없다' 는 것을 나타내는 값임
- 테이블을 정의할 때 null 값을 가지지 못하도록 지정할 수도 있음
- 이런 경우를 not null 이라고 함
  - 할당되지 않았거나 알려져 있지 않아 적용이 불가능한 값임
  - 0이나 공백(space)과는 다름
  - null 값을 포함하는 산술 연산의 결과는 null임

### NVL

- NVL 함수는 null 값을 어떠한 특정한 값으로 변환하는데 사용함
- NVL (commision_pct, 0.5) 처럼 응용하여 사용할 수 있음
- 비슷한 유형에는 NVL2 함수가 있음
- NVL2 함수는 NVL2( 열 이름1, 열 이름2, 열 이름3 ) 형태로 사용
  - 열 이름 1이 null이 아니면 열이름 2를 출력, null이면 열 이름 3을 출력함

### TIP

- null 값은 산술 계산(이를테면 나눗셈이나 곱셈)이나 뒤에서 배율 조인 등을 수행할 때 논리적으로 오류를 일으킬 수 있음
  - 예를 들면 개별 고객의 월 매출 평균을 계산할 때 나누고자 하는 항목 값이 없는 것(null)과 1인 경우는 다른 결과가 출력되어야 함
  - 이러 경우에는 NVL 함수를 이용해 null 값을 의도에 맞게 처리해 줘야함

---

## DECODE : 조건 논리 처리하기

- DECODE는 프로그래밍을 해 본 사람이라면 들어 본 적이 있을 IF-THEN-ELSE-END의 조건 논리를 가능하게 하는 함수임
- 데이터 값이 조건 값과 일치하면 치환 값을 출력하고 일치하지 않으면 기본값을 출력함
  - DECODE ( 열이름, 조건값, 치환값, 기본값 )

---

## RANK, DENSE_RANK, ROW_NUMBER : 데이터 값에 순위 매기기

- RANK, DENSE_RANK, ROW_NUMBER는 데이터 값에 순위를 매기는 함수임
- 순위를 매기는 것은 동일하지만 사용법이 조금씩 다름
- 즉, 공통 순위가 있을 때 출력을 어떻게 하느냐에 따라 용도가 달라짐

### RANK

- 공통 순위를 출력하되 공통 순위만큼 건너뛰어 다음 순위를 출력함
  - 1, 2, 2, 4, ...

### DENSE_RANK

- 공통 순위를 출력하되 건너뛰지 않고 바로 다음 순위를 출력함
  - 1, 2, 2, 3, ...

### ROW_NUMBER

- 공통 순위를 없이 출력함

  - 1, 2, 3, 4, ...

- RANK () OVER ( [PARTITION BY 열 이름] ORDER BY 열 이름)

---

## 그룹 함수의 종류

### COUNT

- 행 개수를 셈
- COUNT( salary )
- (\*)의 경우 null 값도 개수로 셈

### SUM

- 합계
- SUM(salary)
- null 값을 제외하고 연산

### AVG

- 평균
- AVG(salary)
- null 값을 제외하고 연산

### MAX

- 최대값
- MAX(salary)
- null 값을 제외하고 연산

### MIN

- 최솟값
- MIN(salray)
- null 값을 제외하고 연산

### STDDEV

- 표준편차
- STDDEV(salary)
- null 값을 제외하고 연산

### VARIANCE

- 분산
- VARIANCE(salary)
- null 값을 제외하고 연산

---
