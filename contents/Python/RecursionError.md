# 재귀함수 횟수 제한

### RecursionError

- RecursionError는 재귀와 관련된 에러임
- Python이 정한 최대 재귀 깊이보다 재귀의 깊이가 더 깊어질 떄임

```Python
import sys
sys.getrecursionlimit()
## Python이 정한 최대 재귀 깊이 확인 가능
```

#### 재귀함수 에러 해결 방법

1. 재귀함수를 사용하지 않고 다른 방법으로 풀이
2. sys.setrecursionlimit() 사용하여 최대 재귀 깊이 변경

- 재귀 문제를 풀 때 런타임 에러가 발생할 수 있음
- 백준 채점시스템에서는 최대 재귀 깊이르 1,000으로 default값으로 설정해 놓았음
- 해결 방법은 sys.setrecursionlimit()를 사용하여 최대 재귀 깊이를 늘려주는 방법이 있음

- 오류가 발생한 소스 코드 윗부분에 아래 sys 삽입

```python
import sys
sys.setrecursionlimit(10**7) # 최대 재귀 깊이 10,000,000으로 제한
```

- but. 최대값을 크게 변경했다고 하더라도 재귀의 깊이가 채점 서버가 감당할 수 없는 정도로 깊어지면 Segemntation fault가 발생

[참고포스팅](https://help.acmicpc.net/judge/rte/RecursionError)
