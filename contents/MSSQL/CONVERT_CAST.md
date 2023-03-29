# _CONVERT and CAST_

## Convert

- MSSQL에서 사용되는 데이터 타입 변환 함수로 Convert함수가 있음

```sql
--문법--
CONVERT(data_type[(length)], expression[style])
--예시--
SELECT CONVERT(NVARCHAR(10),칼럼) AS 칼럼명 FROM MY_TABLE --VARCHAR로 변환
SELECT CONVERT(INT,칼럼) AS 칼럼명 FROM MY_TABLE --INT로 변환
SELECT CONVERT(CHAR,칼럼) AS 칼럼명 FROM MY_TABLE --CHAR로 변환
```

**expression :**

유효한 식

**data_type :**

대상 데이터 형식 별칭 데이터 형식은 사용할 수 없습니다.

**length :**

대상 데이터 형식의 길이를 지정하는 선택적 정수입니다. 기본값은 30입니다.

**style :**

Convert함수가 식을 변환하는 방법을 지정하는 정수 식입니다. style이 Null이면 Null 값이 반환됩니다.

---

## Cast

```sql
--문법--
CAST(expression AS data_type(length))
--예시--
SELECT CAST(칼럼 AS INT) FROM  MY_TABLE
```

- Float, Numberic에서 Integer로 변환할 때 CAST()함수는 결과를 자름

[참고링크](https://coding-factory.tistory.com/100)
