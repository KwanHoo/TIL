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
