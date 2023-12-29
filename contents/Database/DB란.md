# 데이터 베이스란? \_ SQool Tutorial 참고

### 1. DB

- 데이터베이스(Database)는 여러 사람이 공유하여 사용할 목적으로 체계화해 통합, 관리하는 데이터 집합임
- 작성된 목록으로써 여러 응용 시스템들의 통합된 정보들을 저정하여 운영할 수 있는 공용 데이터들의 묶음임
- “데이터를 저장하는 공간!”

### 2. DB, RDB, DBMS, RDBMS

- RDBMS(stands for Replational Database Management System)는 DB를 관리하는 시스템임
- Top3 오픈소스 RDBMS 는 MySQL, PostgreSQL, SQLite가 있음
- 오픈소스 아닌것에는 Oracle이 독보적임

### 3. 관계형 데이터베이스 구성 요소

- TABLE(행, 열), VIEW(데이터를 선택하여 만든 가상의 부분 집합), INDEX(주소), SEQUENCE(시퀀스, 고유번호 자동생성), SYNONYM(시노임, 객체의 별칭) 등의 객체로 구성
- ENTITY, RELATIONE 들의 집함

- 튜플 (Tuple) : 테이블의 행
- 속성 (Attribute) : HTML로 따지자면 Table Heading 임
- 도메인 (Domain) : 하나의 속성에서 취할 수 있는 값의 범위를 말함
- 차수 (Degree) : 속성의 개수
- 기수(Cardinality) : 튜플의 개수

### 4_1. 키의 개념 및 종류

- 기본키는 메인으로 사용할 키를 말함
  - 고유한(유일한) 주민등록번호나 계좌번호, 전화번호 등은 기본키로 사용할 수 있음
  - 기본키는 NULL을 사용할 수 없음
- 후보키는 기본키를 제외하고 고유한 키들을 말함
- 외래키는 관계되어 잇는 테이블에서 참고하고 있는 키를 얘기함

### 4_2. 데이터베이스의 종류

- 계층형 데이터베이스 ( 1 : N )
- 망형 데이터베이스 ( N : M )
- 관계형 데이터베이스 (단순한 표 형태의 상호 관계, 1:1, 1:N, N:M관계 표현)
- 객체 지향형 데이터베이스

### 5. SQL

- SQL(Structured Query Language)은 스토리지 언어의 표준임
- MySQL, MsSQL, Oracle, PostgreSQL 등의 DB를 사용하여 어떤 프로젝트를 한다면 SQL을 다뤄야함

### 6. SQL 명령어의 분류

1. 데이터 조작어 (DML) : SELECT, INSERT, UPDATE, DELETE
2. 데이터 정의어 (DDL) : CREATE, ALTER, DROP, RENAME, TRUNCATE
3. 데이터 제어어 (DCL) : GRANT(권한부여), REVOKE(권한제거)
4. 트랜젝션 제어어(TCL) : COMMIT, ROLLBACK,

### 7. 데이터 분석 과정

- 사전에 데이터 분석 기획함
- 데이터 전처리 단계 까지가 전체 과정에 70% ~ 80%를 차지하고 있음
- 기업에 모든 데이터를 누구나 조회 가능하도록 BigQuery같은 곳에 모아두기도 합니다. 이러한 시스템이 갖춰진 회사라면 누구나 간단한 조회가 가능한 SQL 구문을 습득하실 필요가 있음
- 기업에 들어가도 데이터가 없거나 쓸 수 없는 경우도 있습니다. 또는 의미없는 데이터이거나 추가 데이터가 필요할 수도 있습니다. 이 경우에는 공공데이터 포털이나 다른 기관의 데이터를 참고하여 데이터를 만들어야함
- 데이터 수집부터, 가공하는 것까지 SQL을 사용할 수 있습니다. 물론 분석에도 쓸 수 있지만 분석에는 더 좋은 도구들이 많죠. R, Python 등의 언어가 있고, Tableau와 같은 시각화 솔루션이 있음

### 8. 정형 데이터와 비정형 데이터

- 정형데이터는 RDBMS에서 사용하는 테이블 안에 들어가 있는 형식이 잡혀 있는 데이터
- 비정형 데이터(unstructured data, unstructured information, 비정형 정보), 비구조화 데이터, 비구조적 데이터는 미리 정의된 데이터 모델이 없거나 미리 정의된 방식으로 정리되지 않은 정보를 말함

### 9. CRUD란?

- 생성과 읽기, 갱신과 삭제를 묶어 일컫는 말
  - Create
  - Read
  - Update
  - Delete

[참고포스팅](https://sqlschool.co.kr/pagetutorial/)
