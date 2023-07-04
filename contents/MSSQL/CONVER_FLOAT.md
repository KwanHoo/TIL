# MSSQL CONVERT, float

## MSSQL 정수 나머지 및 소수점 표현하기 (convert, float)

- mssql 이용 시 일반 정수를 나누면 모든게 다 버림차리가 되어서 정수만 나오게 됨!!!

  - ex. 7/3 을 하면 2만 나오고 나머지는 표현하지 않음

- ORACLE의 경우는 소수점 모두 표현을 함!!(참고)

- mssql에서 소수점을 표현하고 싶으면 convert와 float을 이용하면 됨

  - ex. convert(float,7) / convert(float, 3) -> 소수점 계산 됨 2.333333

[참고포스팅](https://jjongdiary.tistory.com/78)
