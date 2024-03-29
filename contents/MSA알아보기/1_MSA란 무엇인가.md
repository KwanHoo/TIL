# [MSA알아보기] 1. MSA란 무엇인가

## MSA란 무엇인가

- 마이크로서비스 아키텍처(주로 마이크로서비스라고도 함)란 애플리케이션 개발을 위한 아키텍처 스타일을 의미함
- 마이크로서비스를 사용하면 대규모 애플리케이션을 각각 담당 영역을 가진 소규모의 독립적인 구성요소로 구분할 수 있음
- MSA(Microservice Architecture), 마이크로서비스라고도 불리는 접근 방법은 대규모 서비스 / 애플리케이션을 여러 작은 규모의 서비스 /애플리케이션으로 나누는 접근 방식을 의미함

- 마틴 파울러의 마이크로서비스 정의
  - 마이크로서비스는 여러 개의 작은 서비스 집합으로 개발하는 접근 방법
  - 각 서비스는 개별 프로세스에서 실행되고 HTTP 자원 API 같은 가벼운 수단을 사용해 통신
  - 또한 서비스는 비즈니스 기능 단위로 구성되고 자동화된 배포 방식을 이용하여 독립적으로 배포됨
  - 또한 서비스에 대한 중앙 집중적인 관리는 최소화하고 각 서비스는 서로 다른 언어와 데이터, 저장 기술을 사용할 수 있음

### 모노리스(Monolith) VS 마이크로서비스(Microservice)

#### 모노리스

- 하나의 단위로 개발되는 일체식 어플리케이션
- 스케일 아웃 시 모노리스 전체가 확장
- 단일 프로세스에서 실행됨
- 로드 밸런서를 앞에 두고 여러 인스턴스 위에 큰 덩어리를 복제해 수평으로 확장
- 여러 개의 모노리스 시스템 모두를 재빌드 / 재배포 해야함
- 어플리케이션의 병렬 확장은 가능하나 데이터베이스가 통합되어 있어 탄력적 대응이 어려움

#### 마이크로서비스

- 서버 측이 여러 개의 조각으로 구성되어 각 서비스가 별개의 인스턴스로 로딩
- 여러 서비스 인스턴스가 모여 하나의 비즈니스 어플리케이션을 구성
- 각기 저장소가 달라 업무 단위로 모듈 경계가 명확하게 구분
- 각 서비스는 또한 다른 서비스 및 저장소와 격리되어 있으며 API를 통해서만 느슨하게 연계됨
- 각 서비스를 구축하는데 사용되는 언어 / 저장소를 자율적으로 선택할 수 있음 (폴리그랏, Polyglot)
- 각 서비스는 자동화된 개발 환경에서 독립적으로 배포됨

  - 두 방식을 비교했을때 MSA는 모놀리식 아키텍처보다 좀 더 유연한 확장 / 스케일 아웃 / 배포가 가능하다는 장점이 있으며 기술 선택 역시 독립적으로 가능하다는 메리트가 있음
  - MSA가 클라우드 인프라 환경을 가장 효율적으로 사용할 수 있고 가장 적합하다는 사실이 알려져 많은 서비스들이 클라우드 환경으로 옮기면서 모놀리식 아키텍처에서 MSA로 변화하고 있음

---

### MSA와 클라우드 인프라 환경

- 클라우드 인프라의 등장 및 클라우드 환경 내에 사용되는 오픈소스와 이를 기반으로 한 상용 제품들의 호환성 덕분에 각 레이어 별로 유연하고 호환성 있느 솔루션과 오픈소스를 선택할 수 있게 됨
- 클라우드 인프라가 제공하는 이러한 이점들을 최대한 살리는, 클라우드 인프라의 특성을 닯은 클라우드 네이티브한 어플리케이션 구조로 마이크로서비스가 등장

### MSA의 단점

- 기본적으로 복잡하고 러닝 커브가 있음
  - 모놀리식 아키텍처에 비해 구조가 복잡해질 수 밖에 없고 분산 환경이라면 더더욱 복잡도가 높아질 수 바께 없음
  - MSA와 관련된 다양한 기술들을 추가로 익혀야 해서 러닝 커브가 존재함
- 테스트 / 배포 복잡성
  - 여러 마이크로서비스가 연결되어 있는 기능을 테스트하려면 테스트 복잡도가 높아질 수 밖에 없으며, 배포 절차 역시 모놀리식 아키텍처에 비해 복잡하고 배포 시 소요되는 비용이 높아질 수 밖에 없음
- 데이터 관리
  - 데이터가 여러 마이크로서비스를 거치는 경우 데이터 무결성 / 정합성 유지가 상당히 어려워지며 이를 유지하기 위해 도입하는 기술의 러닝 커브가 높은편
- 서비스 간 의존성
  - 마이크로서비스는 API를 통해 연결되어 있는데 API 버전에 대한 의존성이 생기며 한 마이크로서비스의 장애가 다른 서비스의 장애로 이어질 수 있음
- 리소스 사용량 증대
  - 모놀리식 아키텍처에 비해 리소스 사용량이 증가되어 보다 많은 비용이 발생

## MSA 구성 요소와 패턴

### 외부 아키텍처와 내부 아키텍터

- 외부 아키텍처는 마이크로서비스가 운영되는 환경을 의미하며 크게 어플리케이션 영역과 플랫폼 영역, 인프라 영역으로 나누어짐

  - 어플리케이션 영역 : 플랫폼 영역 위에서 구동되는 어플리케이션 서비스 영역
    - 채널(모바일 / 브라우저), 핵심 서비스 (프론트엔드 / 백엔드), 데이터 (DB) 등
  - 플랫폼 영역 : 인프라 영역 위에 올라가는 어플리케이션을 운영 및 구동하기 위한 영역
    - 플랫폼 서비스 : DevOps 파이프라인, 팀 업 환경, 메세지 버스, 로깅, 라이브러리 등
    - MSA 기반 서비스 : API 게이트웨이, 모니터링, 구성관리, 서비스 탐색 등
  - 인프라 영역 : 하드웨어 인프라

- 내부 아키텍처는 실제 비즈니스가 실행되는 내부 구조를 의미
  - 마이크로서비스에서 제공하는 API나 비즈니스 로직, 이벤트 발행, 데이터 저장 처리 등에 대해 구조화한 것임

### 인프라 구성 요소

- 인프라 구성 요소는 마이크로서비스가 실행되는 하부 구조 인프라를 구축하는데 필요한 구성 요소를 의미하며 환경으로 나누면 크게 퍼블릭 클라우드 IaaS, PaaS나 베어메탈 + 프라이빗 클라우드 PaaS 환경으로 나뉨

### 플랫폼 패턴

- 플랫폼 패턴은 인프라 위에서 마이크로서비스의 운영과 관리를 지원하는 플랫폼 차원의 패턴으로 크게 개발 지원 환경을 위한 플랫폼 패턴과 마이크로 서비스 관리 / 운영을 위한 플랫폼 패턴으로 구분할 수 있음

#### 개발 지원 환경을 위한 DevOps 인프라

- 마이크로 서비스를 빌드, 테스트, 배포할 수 있게 도와주는 개발 지원 환경이며 이러한 인프라에서 수행하는 자동화 배포 작업을 CI / CD라고도 부름

  - CI (Continueous Integration) : 지속적 통합, 개발자들이 작성한 소스 코드, 테스트 코드를 통합해서 자동으로 빌드 및 테스트
  - CD (Continueous Delivery / Deployment) : 지속적 제공 / 배포, CI 이후 빌드된 소스 코드를 실행 환경에 자동으로 배포

- 파이프라인 절차
  - 리포지토리 -> 빌드 / 유닛 테스트 -> 정적 분석 -> 통합 테스트 -> 배포 -> 마이크로서비스

#### 마이크로서비스 관리 / 운영을 위한 패턴들

- 자동화 배포 말고도 마이크로서비스를 관리하고 운영하는데에 필요한 플랫폼 패턴들 역시 존재함

- 서비스 레지스트리 패턴
- 서비스 디스커버리 패턴
- API 게이트웨이 패턴
- BFF 패턴 (Backend for Frontend)
- 외부 구성 저장소 패턴
- 인증 / 인가 패턴
- 서킷 브레이커 패턴
- 모니터링과 추적 패턴
- 중앙화된 로그 집계 패턴

### 어플리케이션 패턴

- 어플리케이션 패턴은 마이크로서비스 어플리케이션을 구성하는데 필요한 패턴으로 마찬가지로 다양한 패턴들이 존재함

- UI 컴포지트 패턴 또는 마이크로 프론트엔드 (MFA)
- 마이크로서비스 동기 통신 및 비동기 통신
- 비동기 방식의 이벤트 기반 아키텍처
- 저장소 분리 패턴
- 분산 트랜잭션 처리 패턴 - Saga 패턴
- 읽기와 쓰기를 분리하는 CQRS (Command Query Responsibility Segregation, 명령 조회 책임 분리) 패턴
- 이벤트 소싱 패턴

[참고포스팅](https://velog.io/@mrcocoball2/MSA-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0-1.-MSA%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80)
