# Websocket

### 웹 소켓이 뭐냐

- 서버가 선톡은 절대 안함

  - 유저가 문자 먼저 보내야 답변해줌

- 2초마다 코인 가격 정보를 가져올려면?
  - 2초마다 서버에 http 요청??

2가지 해결책

1. Server-Sent Event

2. WebSocket

### 1. Server-Sent Event

- Http 통신을 종료안하고 계속 유지
- 서버만 일반적으로 보낸다는 단점이 있음

### 2. WebSocket

- 양방향 통신가능
- socket.io 라이브러리 쓰면
  - 연결 끊기면 자동 재접속 기능
  - 웹 소켓 접속자마다 자동 id 부여
  - 모든 웹소켓 유저에게 전체 멧세지 전송가능
  - 웹 소켓 방을 생성가능

### WebRTC : 웹 리얼타임 커뮤니케이션

- 브라우저끼리 연결하는게 webRTC
- 브라우저를 서버랑 연결하는게 아님
  - 서버가 내려가면 채팅이 안되게 됨

## 카카오톡 시스템 디자인

### 트래픽 특성

- 엄청난 양의 트래픽 그룹 채팅 ex) 하루에 600억 메시지
- 오래된 채팅 잘 안봄
- Read/Write 비율 1:1

### 1:1 채팅

- 유저 A가 유저 B에게 메시지를 보내는 경우
- 문제 : HTTP는 클라이언틈나 시작할 수 있음
  - 몇가지 옵션
    - Polling
    - Long Polling
    - WebSocket

### 메세지큐 (Message Queue)

- Kafka, RabbitMQ
- 서비스들 간에 데이터를 주고 받는 방법중에 하나
- RestAPI/ RPC 를 사용하면 Synchronous 하게 데이터를 주고 받음
- 메시지 큐를 사용하면 Asynchronous 하게 데이터를 처리할 수 있음
- Synchronous (동기식), Asynchronous (비동기식)

- 퍼블리셔 : 이벤트가 일어났을때 메시지큐에 넣는것
- 서브스크라이브 : 메시지 큐 받는 것

- 서비스 A가 메시지 보내고 싶어
  - 메시지 큐에 대한 디펜던시만 잇음
    - 서비스 B : DB에 메시지 저장
    - 서비스 C : 푸시 알림으로 메시지 왔는거 보냄
    - 서비스 D : 유저한테 message를 포워드 해줌

[참고링크](https://www.youtube.com/watch?v=VODXNECZOBQ)
