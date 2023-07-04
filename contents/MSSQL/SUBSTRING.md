# MSSQL 문자열 자르기

## LEFT

- LEFT 함수는 문자열을 받아서 왼쪽부터 원하는 길이만큼 자르는 함수임
- 주민등록번호만으로도 생년월일을 구하거나 이름을 잘라서 성만 출력하는 등 다양한 방법으로 활용이 가능함!!

```SQL
-- 문법
LEFT (문자열 , 길이)
-- 예시
LEFT (NAME, 2)

/*예제*/
SELECT
    LEFT(NM_KOR,1) AS 이름
FROM
    MY_TABLE
```

## RIGHT

- RIGHT함수는 LEFT 함수와 기능은 같지만 방향만 다른 함수임
- RIGHT 함수는 문자열을 받아서 오른쪽 부터 원하는 길이만큼 자르는 함수이며 LEFT 함수와 마찬가지로 다양하게 사용이 가능함

```SQL
-- 문법
RIGHT(문자열, 길이)
-- 예시
RIGHT(NAME, 3)

/*예제*/
SELECT
    RIGHT(NAME_KOR, 2) AS 이름
FROM
    MY_TABLE
```

## SUBSTRING

- SUBSTRING 함수의 기능은 문자열을 받아서 일정한 영역만큼 잘라낸 후 리턴하는 기능을 가지고 있음
- 주민등록번호만으로도 성별을 잘라서 활용하거 날짜를 잘라서 월별로 그룹을 만드는 등 다양한 방법으로 활용 가능함
- 자주 쓰이는 문자열 함수임!!!

```SQL
-- 문법
SUBSTRING(문자열, 시작자리번호, 자를 문자수)
-- 예시
SUBSTRING(RESIDENT_NUMBER, 0, 6)

/*예제*/
SELECT
    SUBSTRING(NM_KR, 2,2) AS 이름
FROM
    MY_TABLE

SELECT
    SUBSTRING(DT, 1, 4) + '년' + SUBSTRING(DT, 5, 2) + '월' + SUBSTRING(DT, 7, 2) + '일' AS 일자
FROM
    MY_TABLE
```

[참고포스팅](https://coding-factory.tistory.com/99)
