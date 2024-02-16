# MongoDB CRUD

## MongoDB 구조

- 데이터베이스
- 컬렉션
- 도큐먼트

### JSON과 비슷한 BSON 자료구조

- JSON : Javascript Object Notation
- JSON과 유사한 BSOn 구조로 정보를 저장

- Pymongo : mongoDB를 사용할 수 있게 도와주는 파이썬 모듈

### BSON이란

- BSON : Binary JSON의 의미
- JSON의 일부로써 MongoDB 도큐먼트로 데이터를 저장하기 위한 형식

- ObjectID : MongoDB에서 각 Document의 primary key의 값으로 사용됨
  - ObjectId("유닉스시간 기기id 프로세스id 카운터")

### 도큐먼트 생성

```python
from pprint import pprint
pprint({ BSON document})
```

- pretty print의 의미를 가진 명령어 pprint

### 도큐먼트 검색

#### 커서

- 커서란 쿼리 결과에 대한 포인터
- 도큐먼트의 위치정보만을 반환하여 작업을 효율적으로 만들어줌

#### 쿼리

- 쿼리란 원하는 정보를 걸러내기 위한 깔대기임
- 검색하고자 하는 내용을 쿼리로 표현할 수 있어야함
- 쿼리는 그 field에 맞는 value 값으로 필터링 함

```python

{"field": value, "filed": value}
## 파인드문 예시
users.find(
    {"passowrd": "1111"}
)
```

#### Projection

- field를 보여줄지 말지를 알려줌
- boolean이 true이면 해당 field를 표현
- boolean이 false면 field를 제외한 결과를 출력함

### 도큐먼트 수정

- query로 검색하고, update에 변경할 사항을 적음

### 도큐먼트 삭제

- query로 검색하고 도큐먼트를 삭제

참고 : 엘리스
