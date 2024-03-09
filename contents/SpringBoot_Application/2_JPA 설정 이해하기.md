# 2_JPA 설정 이해하기

# 영속성 유닛 설정

### 영속성 유닛과 EntityManger

- 애플리케이션에서 JPA를 이용하기 위해서는 반드시 EntityManager 객체가 필요
- EntityManager는 EntityManagerFactory로 부터 얻어냄
- EntityManagerFactory를 생성할 때 영속성 유닛 정보가 필요함

- 영속성 유닛은 연동하려는 데이터베이스당 하나씩 설정함
- 다른 영속성 유닛과 식별하기 위해 유일한 이름을 name 속성으로 지정

### 엔티티 클래스 등록

- JPA는 자신이 영속성 관리할 엔티티 클래스들을 인지해야 함
- 반드시 영속성 유닛에 엔티티 클래스들을 등록해야 함

### 데이터 소스 설정

- JPA 구현체는 영속성 유닛에 설정된 데이터소스 설정을 참조하여 데이터베이스를 연결함

#### 프로퍼티

- javax.persistence.jdbc.driver : JDBC 드라이버 클래스
- javax.persistence.jdbc.url : JDBC URL 정보
- javax.persistence.jdbc.user : 데이터베이스 아이디
- javax.persistence.jdbc.password : 데이터베이스의 비밀번호

### Dialect 클래스 설정

- ORM의 가장 큰 장점 : 데이터베이스 연동에 필요한 SQL 구문을 ORM에서 생성
- 데이터베이스에 따라서 키 생성 방식도 다르고 지원되는 함수도 다름
- 운영 과정에서 데이터베이스가 변경되면 데이터베이스마다 다른 부분들을 모두 수정해야함
- JPA는 특정 데이터베이스에 최적화된 SQL을 생성함
- 이를 위해 Dialect 설정이 필요함

### JPA 구현체 설정

- JPA를 사용하기 위해서는 JPA 구현체에 대한 설정도 필요함

#### JPA 구현체와 관련된 설정의 의미

- hibernate.show_sql : 하이버네이트가 생성한 SQL을 콘솔에 출력함
- hibernate.format_sql : 하이버네이트가 생성한 SQL을 출력할 때 보기 좋은 포맷으로 출력함
- hibernate.use_sql_comments : SQL에 포함된 주석(comment)도 같이 출력함
- hibernate.id.new_generator_mappings : 키 생성 전략을 사용함
- hibernate.hbm2ddl.auto : 테이블 생성 (create)이나 변경(alter), 삭제(drop) 같은 DDL 구문을 자동으로 실행할지 지정함

#### hibernate.hbm2ddlauto 속성값

- create : 애플리케이션을 실행할 때, 기존 테이블을 삭제하고 엔티티에 설정된 매핑 정보를 참조하여 새로운 테이블을 생성함 (DROP - CREATE)
- create-drop : create와 같지만 애플리케이션이 종료되기 직전에 생성된 테이블을 삭제함 (DROP - CREATE - DROP)
- update :
  - 기존에 사용중인 테이블이 있으면 테이블을 생성하지 않고 재사용함
  - 없을 때만 새롭게 생성함
  - 만약 엔티티 클래스의 매핑 설정이 변경되면 변경된 내용만 반영함 (ALTER)

---

# 엔티티 매핑 설정

---

# 식별자 값 자동 증가

참고 : e-koreatech 스프링부트기초
