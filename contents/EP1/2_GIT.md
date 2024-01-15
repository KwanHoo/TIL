# Git

### Git의 특징

- 가지 치기와 병합
- 가볍고 빠름
- 분산 작업 가능
- 데이터 보장
- Staging area (준비 영역)
  - [working directory] - git add => [staging area] - git commit => [repository]
- 오픈소스

### Git 관리 상태 확인

- git status : Staging file들의 상태 확인
- git log : .git repository에 존재하는 history 확인

### Git Branch?

- 독립적으로 어떤 작업을 진행하기 위한 개념
- 각각의 Branch는 다른 Branch의 영향을 받지 않음

### Merge confilct

- Merge한 두 Branch에서 같은 파일을 변경했을 때 충돌이 발생함

### 저장소 갱신

- Pull : 원격 저장소에서 데이터 가져오기 + 병합 (Merge)
- Fetch :
  - 원격 저장소에서 데이터 가져오기
  - 진행중인 작업을 마무리하고 병합 해주어야함

### 저장소 발행

- 다른 사람이 먼저 Push한 상태에서는 Push할 수 없음
- 다른 사람이 작업한 것을 Merge 부터 해주어야함

1. git remote add origin : 로컬 저장소와 연결

### origin이란?

- 원격저장소의 단축이름으로 origin으로 지정한다는 의미
- origin이 아닌 다른 이름으로 원격 저장소의 이름을 지정해 줄 수 있음
- 기본적으로 만들어진 원격저장소의 이름은 origin이 default값임
- 그래서 clone으로 복사해온 저장소의 이름은 origin으로 통일되게됨

참고 : 엘리스
