# MongoDB

### RDBMS와 MogoDB(NoSQL) 차이점

RDBMS

user

| ID  | username | phone       |
| --- | -------- | ----------- |
| 1   | kim      | 01012341234 |
| 2   | park     | 01043214321 |

board

| id  | title | content | userId |
| --- | ----- | ------- | ------ |
| 1   | 제목1 | 내용1   | 1      |
| 2   | 제목2 | 내용2   | 2      |

RDBMS의 목적

- 데이터를 공유하자는 목적(중복을 없애자)
  - 한 곳에다 정제해두고 관계로 연결

장점

- 데이터의 중복이 안됨
- 참조키로 연결되어 있어 데이터 변경에 편함

---

NoSQL

- 컬렉션(RDB의 테이블과 비슷한 개념)

JSON Object

user collection

```JSON
user:[
	{
		id: 1,
		username: kim,
		phone: 010-1234-1234
	},
	{
	}
]
```

board collection

```JSON
board:[
	{
		id:1,
		title: 제목1,
		cotnent: 내용1,
		username: kim,
		phone: 010-1234-1234
	},
	{
	}
]
```

- 데이터 중복을 허용함

장점:

- RDBMS는 조인을 해서 두가지 테이블에 접근을 해야함
  - userid의 1을 모르니
- 그래서 nosql의 장점은 한번에 조회가능
- 데이터를 insert 할때는 안좋지만 데이터를 찾을때는 퍼포먼스가 좋음
  - ex) instagram
    - 내가 1 개 글 작성 (30명 봄)\
    - 아이유 글 1건 작성 (수백만명)
      - 수백만명의 보는 퍼포먼스가 좋음

단점:

- 데이터의 일관성을 유지하기 힘듬(수정때 까다로움)
  - user collection의 데이터 일부를 수정하고 board collection의 해당 데이터도 수정해야함
