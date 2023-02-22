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
