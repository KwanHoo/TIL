# _PRIMARY KEY, FOREIGN KEY_

## 오라클에서 제공되는 제약 조건

- PRIMARY KEY
- FOREIGN KEY
- UNIQUE KEY
- NOT NULL
- CHECK

## PK(PRIMARY KEY, 주키, 주식별자)

- 결정 인자라고도 부름
- 테이블의 모든 데이터를 유일하게 식별해주는 컬럼
- 테이블은 무조건 PK를 가지고 있음

## 함수적 종속

- 레코드 내에 존재하는 항목(칼럼)들 중에 속성 B 가 속성 A 에 함수적 종속 관계에 있다는 것은 A를 이용해서 B를 식별할 수 있다는 뜻임
- A -> B의 형태로 사용하며 A를 결정인자(Determinant), 프라이머리 키라고 부름

## FK(Foreign Key, 외부키, 외부식별자)

- 테이블간 관계(Relationship)를 의미함
- 테이블은 참조를 당하는 경우가 아니면 무조건 FK를 가지고 있음
- UNIQUE KEY : 데이터 정보에 없을 수는 있지만 절대 중복되는 값은 없음
  - EX) 주민등록 번호
- NOT NULL : Null값이 들어가면 안됨
  - EX) 숫자
- CHECK : 직접 써주는 제약 조건
  - WHERE 절에 써주는 방식과 같음
