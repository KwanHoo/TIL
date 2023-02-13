# MSSQL \_ 문자열 자르기

### LEFT, RIGHT 란?

- LEFT는 문자열의 왼쪽부터 일정수치까지의 문자열을 자르는 함수
- RIGHT는 문자열의 오른쪽부터 일정수치까지의 문자열을 자르는 함수

- MSSQL LEFT / RIGHT 사용방법
  ```sql
  LEFT( '[문자열]', [길이] )
  RIGHT( '[문자열]', [길이] )
  ```

[참고 포스팅](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=diceworld&logNo=220161277199)

---

## MSSQL \_ NULL값 체크 (ISNULL)

### ISNULL 함수

- ISNULL함수는 Microsoft SQL Server의 내장함수이며 칼럼이 NULL 값일 경우 다른값으로 대체할 수 있는 기능이 있음
- 데이터베이스를 사용하다보면 파라미터로 NULL 값이 오거나 칼럼안에 NULL 값이 들어잇는 등 경우에 따라 NULL 값을 적절히 처리해줘야하는 경우가 많은데 이럴 때 유용하게 쓰일 수 있는 함수임

### 사용법

```sql
--문법--
ISNULL( 칼럼, 칼럼이 NULL일경우 대체할 값 )

--예시--
ISNULL(COLUM, 0)
```

[참고 포스팅](https://coding-factory.tistory.com/98)
