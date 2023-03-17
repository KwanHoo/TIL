# _PostgreSQL과 ORACLE 차이점_

### sysdate

- oracle : select sysdate from dual;
- postgresql : select now();

### dual table

- oracle : select 1,2 from dual;
- postgresql : select 1,2;

### sequence

- oracle : sequence_name.nextval
- postgresql : nextval.sequence_name

### decode

- oracle : decode(column1, val1, result1, ..., default)
- postgresql : case columns1 when val1 then result1 ... else default END

### nvl

- oracle : NVL(hire_date, SYSDATE) => 타입 불일치 시 묵시적 형변환 발생
- postgresql : coalsce(hire_date, SYSDATE) => 컬럼타입 불일치 시 오류 (상수는 OK)

### from 절 subquery

- oracle : select _ from (select _ from table_name);
- postgresql : select _ from (select _ from table_name)as alias_name;

### outer join

- oralce : select a.filed1, b.filed2 from a, b where a.item_id = b.item_id(+);
- postgresql : select a.field1, b.field2 from a left outer join b on a.item_id = b.item_id;

### connected by

- oracle : connected by
- postgresql : with recursive

### CLOB

- oracle : CLOB
- postgresql : TEXT

### 수치비교

- oracle : 문자-숫자 비교시 묵시적 형변환 발생
- postgresql : 문자-숫자 비교시 오류 발생
