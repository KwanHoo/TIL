# _JDBC, ODBC란_

## JDBC (Java DataBase Connectivity)

### JDBC란

- Java에서 DB에 접근하여 DML을 사용 가능하게 하는것
- Java가 DB를 사용할 수 있도록 연결해주는 응용 인터페이스인 JAVA API임

- JDBC Connection은 명령문을 만들고, 실행하는 것을 지원함
- 명령문은 SQL의 CREATE, INSERT, UPDATE, DELETE와 같은 갱신을 위한 명령문, SELECT와 같은 조회를 위한 명령문 등을 말함

- 갱신을 위한 명령문은, 명령문에 의해 영향을 받은 데이터베이스 열의 개수를 반환하게 됨
- 검색을 위한 명령문의 결과값을 담은 ResultSet을 반환하게됨

- 정리하면 JDBC란 JAVA에서 DataBase와 연결하여 작업하기 위해서 JAVA와 연동되는 DBMS(ex. MySQL)에 따라 그에 맞는 JDBC(ex. MySQL Connector)를 설치할 필요가 있음

---

## ODBC (Open DataBase Connectivity)

### ODBC란

- 데이터베이스를 액세스하기 위한 표준 개방형 응용 프로그램 인터페이스를 말함
- MicroSoft사에 의해 만들어진, 데이터베이스에 접근하기 위한 Software의 표준 규격으로, 프로그램 내에 ODBC 문장을 사용하면 MS-Access, DBase, DB2, Execl, Text 등의 여러 종류의 데이터베이스에 접근할 수 있음

- 각 데이터베이스의 차이는 ODBC Driver에 의해서 반환되고, Client(User)는 ODBC에 정해진 순서에 따라서 프로그램을 쓰면 접속처의 데이터베이스가 어떠한 DBMS에 관리되고 있는지 의식할 필요 없이 접근할 수 있다는 것이 특징임

- 정리하면 ODBC는 응용프로그램(ex. HeidiSQL, SQLyog)에서 데이터 접근할 때 어떠한 DBMS(ex. Oracle, MySQL, MariaDB)에 의해 관리되고 있는지 의식할 필요가 없음

[참고포스팅](https://beom3.tistory.com/24)
