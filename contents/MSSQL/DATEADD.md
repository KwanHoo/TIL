# _DATEADD_

## DATAADD()

- SQL Server에서는 날짜, 시간을 더하거나 빼기 위해서는 DATEADD 함수를 사용함
- 현재 날짜에서 하루를 빼서 전일 데이털르 조회할 수 있음
- 일자 외에도 년 월 시간 등 기준일자에 원하는 기간 만큼 쉽게 더하거나 뺄수있음

```SQL
SELECT DATEADD(DAY, -1, GETDATE())  --1일 빼기
    , DATEADD(DAY, -1, GETDATE())   --1일 더하기
```

- 날짜를 빼고 더할 수 있음 (년, 월, 일)
- 즉, day대신 MONTH, YEAR 이 들어와서 월, 년을 더하거나 뺄 수 있음

- 시간(시, 분, 초)를 빼거나 더할 수 있음

```SQL
SELECT DATEADD(HOUR, -1, '2023-03-29 22:00:00') AS [1시간전]
    , DATEADD(HOUR, 1, '2023-03-29 22:00:00') AS [1시간후]
```

- 시간을 빼고 더할 수 있음
- HOUR 대신 MINUTE, SECOND이 들어와서 분, 초를 더하거나 뺄 수 있음

[참고링크](https://gent.tistory.com/429)
