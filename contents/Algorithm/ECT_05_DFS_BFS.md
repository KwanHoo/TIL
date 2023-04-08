# _DFS/BFS_

- 그래프를 탐색하기 위한 대표적인 두가지 알고리즘

## <1> 꼭 필요한 자료구조 기초

### 탐색 Search

- 탐색이란 '많은 양의 데이터 중에서 원하는 데이터를 찾는 과정'임
- 프로그래밍에서는 그래프, 트리 등의 자료구조 안에서 탐색을 하는 문제를 자주 다룸
- 대표적인 탐색 알고리즘으로 DFS와 BFS를 꼽을 수 있음
- 이 둘을 제대로 이해하려면 스택과 큐, 재귀함수를 알고 있어야함

### 자료구조 Data Structure

- 자료구조란 '데이터를 표현하고 관리하고 처리하기 위한 구조'를 의미함
- 그중 스택과 큐는 자료구조의 기초 개념으로 다음의 두 핵심적인 함수로 구성됨

  - Push(삽입) : 데이터를 삽입함
  - Pop(삭제) : 데이터를 삭제함

- 스택과 큐를 사용할 때는 삽입, 삭제 이외에도 오버플로와 언더플로를 고민해야함
  - overflow : 특정 자료구조가 수용할 수 있는 데이터 크기를 이미 가득찬 상태에서 연산을 수행할 때 발생
    - 즉, 저장 공간을 벗어나 데이터가 넘쳐 흐를 때 발생함
  - underflow : 특정한 자료구조에 데이터가 전혀 들어 있지 않은 상태에서 삭제 연산을 수행할 때 발생

### 스택 Stack

- 박스 쌓기에 비유할 수 있음
- 선입후출(FILO) or 후입선출(LIFO) Last In First Out 구조라고함
- 파이썬에서 스택을 이용할 때에는 별도의 라이브러리를 사용할 필요가 없음
  - 기본 리스트에서 append() 와 pop() 메소드를 이용하면 스택 자료구조와 동일하게 동작함
    - append() 메서드는 리스트의 가장 뒤쪽에 데이터를 삽입
    - pop() 메서드는 리스트의 가장 뒤쪽에서 데이터를 꺼냄

### 큐 Queue

- 대기 줄에 비유할 수 있음
- 선입선출(FIFO) First In First Out

```python
from collections import deque
# 큐 구현을 위해 deque 라이브러리 사용
queue = deque()

queue.append(5)
queue.append(3)
queue.popleft()
```

- 파이썬으로 큐를 구현할 떄는 collections 모듈에서 제공하는 deque 자료구조 활용
- deque는 스택과 큐의 장점을 모두 채택한 것임
  - 데이터를 넣고 빼는 속도가 리스트 자료형에 비해 효율적임
  - queue 라이브러리 이용하는 것 보다 더 간단함
- deque 객체를 리스트 자료형으로 변경하고자 하면 list() 메소드 사용
  - list(queue)를 하면 리스트 자료형이 반환됨

### 재귀함수 Recursive Function

- 자기 자신을 다시 호출하는 함수

```python
def recursive_function():
  print('재귀함수를 호출합니다.')
  recursive_function()

recursive_function()
```

- 위 코드를 실행하면 '재귀함수를 호출합니다.'라는 문자열을 무한히 출력함
  - 어느정도 출력하다가 RecursionError: maximum recursion depth exceeded while pickling an objet 라는 오류메시지가 뜸
  - 이 오류 메시지는 재귀의 최대 깊이를 초과했다는 내용임

#### 재귀함수의 종료조건

- 재귀함수가 언제 끝날지 종료조건을 꼭 명시해야함
  - 명시하지 않으면 함수가 무한 호출될 수 있음
- 컴퓨터 내부에서 재귀 함수의 수행은 스택 자료구조를 이용함

  - 스택자료구조를 활용해야하는 상당수의 알고리즘은 재귀함수를 이용해서 간편하게 구현할수 있음 -> ex) DFS

- 재귀함수를 이용하는 대표적 예제 : 팩토리얼Factorial
- 반복문 대신에 재귀함수를 사용했을 때 얻을 수 있는 장점
  - 재귀 함수가 수학의 점화식(재귀식)을 그대로 소스코드로 옮겼기 때문에 코드가 간결함
    - 수학에서 점화식은 특정한 함수를 자신보다 더 작은 변수에 대한 함수와의 관계로 표현한 것을 의미함
      - 이후 배울 다이나믹 프로그래밍에도 이어짐
- 일반적으로 점화식에서 종료조건을 찾을 수 있음
  - 팩토리얼은 n이 1이하인 경우 1을 반환

### <2> 탐색 알고리즘 DFS / BFS

#### DFS Depth-First Search

- 깊이 우선 탐색이라고도 부르며, 그래프에서 깊은 부분을 우선적으로 탐색하는 알고리즘임
- 스택 자료구조에 기초한다는 점에서 구현이 간단함
  - 실제로는 스택을 쓰지 않아도 되며 탐색을 수행함에 있어서 데이터의 개수가 N개인 경우 O(N)의 시간이 소요됨
- 스택을 이용하는 알고리즘이기 떄문에 실제 구현은 재귀함수를 이용했을 때 매우 간결하게 구현할 수 있음

##### 그래프 참고

- 노드 Node
- 간선 Edge
- 정점 Vertex
- 그래프 탐색이란 하나의 노드를 시작으로 다수의 노드를 방문하는 것을 말함
- 두 노드가 간선으로 열결되어 있다면 '두 노드는 인접하다 Adjacent'라고 표현함

- 프로그래밍에서 그래프는 크게 2가지 방식으로 표현할 수 있음
  - 인접행렬(Adjacency Matrix)
    - 2차원 배열로 그래프의 연결 관계를 표현하는 방식
  - 인접 리스트(Adjacency List)
    - 리스트로 그래프의 연결 관계를 표현하는 방식

##### 인접행렬 방식

- 2차원 배열에 각 노드가 연결된 형태를 기록하는 방식
- 2차원 리스트로 구현할 수 있음
- 연결이 되어 있지 않은 노드끼리는 무한infinity의 비용이라고 작성함

```python
INF = 99999999 # 무한의 비용 선언
# 2차원 리스트를 이용해 인접 행렬 표시
graph = [
  [0, 7, 5],
  [7, 0, INF],
  [5, INF, 0]
]

print(graph)
```

##### 인접리스트 방식

- 모든노드에 연결된 노드에 대한 정보를 차례대로 연결하여 저장함
- 연결 리스트 자료구조를 이용해서 구현함
  - 파이썬은 기본 자료형인 리스트 자료형이 append()와 메소드를 제공함
  - 파이썬으로 인접 리스트를 이용해 그래프를 표현하고자 할때에도 단순히 2차원 리스트를 이용하면 됨

```python
# 행(row)이 3개인 2차원 리스트로 인접 리스트 표현
graph = [[] for _ in range(3)]

# 노드 0에 연결된 노드 정보 저장(노드, 거리)
graph[0].append((1,7))
graph[0].append((2,5))

# 노드 1에 연결된 노드 정보 저장(노드, 거리)
graph[1].append((0,7))
# 노드 2에 연결된 노드 정보 저장(노드, 거리)
graph[2].append((0,5))

print(graph)
```

##### 두 방식의 차이점

- 메모리 측면
  - 인접 행렬 방식은 모든 관계를 저장하므로 노드 개수가 많을 수록 메모리가 불필요하게 낭비됨
  - 반면 인접 리스트 방식은 연결된 정보만을 저장하기 떄문에 메모리를 효율적으로 사용함
    - 하지만 이러한 속성 때문에 인접리스트 방식은 인접 행렬 방식에 비해 특정한 두 노드가 연결되어 있는지에 대한 정보를 얻는 속도가 느림
      - 인접 리스트 방식에서는 연결된 데이터를 하나씩 확인해야 하기 때문

### BFS Breadth First Search

- '너비 우선 탐색', 가까운 노드부터 탐색하는 알고리즘
- DFS는 최대한 멀리 있는 노드를 우선으로 탐색하는 방식으로 동작한다고 했는데, BFS는 그 반대임
- BFS 구현에서는 큐 자료구조를 이용하것이 정석임

  - 인접한 노드를 반복적으로 큐에 넣도록 알고리즘을 작성하면 자연스럽게 먼저 들어온 것이 먼저 나가게 되어 가까운 노드부터 탐색을 진행하게 됨

- 큐 자료구조에 기초한다는 점에 BFS는 구현이 간단함
- Deque 라이브러리를 사용하는 것이 좋음
- 탐색을 수행함에 있어 O(N)의 시간이 소요됨
  - 일반적인 경우 실제 수행 시간은 DFS 보다 좋은 편임

---

- 1차원 배열이나 2차원 배열 또한 그래프 형태로 생각하면 수월하게 문제 풀 수 있음
  - 특히 DFS와 BFS 문제 유형
- 코딩 테스트 중 2차원 배열에서의 탐색 문제를 만나면 그래프 형태로 바꿔서 생각하면 풀이 방법을 조금더 쉽게 떠올릴 수 있음
  - 코딩 테스트에서 탐색 문제를 보면 그래프 형태로 표현한 다음 풀이법을 고민

### <3> 음류수 얼려 먹기

- DFS 로 해결할 수 있음
- 그래프 형태로 모델링 할 수 있음
- '0'인 값이 상, 하, 좌, 우로 연결되어 있는 노드를 묶고 이러한 묶음을 찾아주는 프로그램을 작성하면 됨

### <4> 미로 탈출

- BFS를 이용하여 해결 가능
- BFS는 시작 지점에서 가까운 노드부터 차례대로 그래프의 모든 노드를 탐색하기 때문임
  - 1,1 지점에서부터 BFS를 수행하여 모든 노드의 값을 거리 정보로 넣으면 됨