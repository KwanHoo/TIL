# _Greedy_

- 현재 상황에서 가장 좋아 보이는 것만을 선택하는 알고리즘
- 참조 : 이코테 with 파이썬
  - 학습 메모

## <1> 당장 좋은 것만 선택하는 그리디

- 탐욕법, 욕심쟁이 알고리즘
- 문제를 무식하게 푸는 알고리즘
- 탐욕적 '현재 상황에서 지금 당장 좋은 것만 고르는 방법'

  - 매 순간 가장 좋아 보이는 것을 선택
  - 현재의 선택이 나중에 미칠 영향에 대해서는 고려 X

- '사전에 외우고 있지 않아도 풀 수 있을 가능성이 높은 문제유형'
- 창의력, 문제를 풀기 위한 최소한의 아이디어를 떠올릴 수 있는 능력을 요구함

  - 특정 문제를 만났을 때 단순히 현재 상황에서 가장 좋아 보이는 것만을 선택해도 문제를 풀 수 있는지를 파악할 수 있어야 함

- 기준에 따라 좋은 것을 선택하는 알고리즘
  - '가장 큰 순서대로', '가장 작은 순서대로' 와 같은 기준을 제시해줌
  - 정렬 알고리즘과 짝을 맞춰 출제됨

### ex3-1 거스름돈

- '가장 큰 화폐 단위부터' 돈을 거슬러 주는 것
- 그리디 알고리즘으로 문제의 해법을 찾았을 때 그 해법이 정당한지 검토해야 함
  - <B>가지고 있는 동전 중에서 큰 단위가 항상 작은 단위의 배수이므로 작은 단위의 동전들을 종합해 다른 해가 나올 수 없기 때문임</B>
  - ex) 800원 거슬러줘야하는 경우 case1) 500,100,100,100 / case2)400,400

## <2> 큰 수의 법칙

- 입력값(배열) 중에서 가장 큰 수와 두번째로 큰수만 저장하면됨
- 연속으로 더할 수 있는 횟수가 K로 주어지므로 '가장 큰 수를 K번 더하고 두번재로 큰 수를 한번 더하는 연산'을 반복

## <3> 숫자 카드 게임

- '각 행마다 가장 작은 수를 찾은 뒤에 그 수 중에서 가장 큰 수'를 찾는것임
- 각 행에서 가장 작은 수를 찾은 다음 그 수 중에서 가장 큰 수를 찾는 방식으로 문제를 해결 할 수 있음
  - 리스트에서 가장 작은 원소를 찾아주는 <B>min()</B> 함수를 이용
  - 2중 반복문 구조 이용

## <4> 1이 될 때 까지

- 주어진 N에 대하여 '최대한 많이 나누기' 를 수행
  - '2이상의 수로 나누는 것'이 '1을 빼는 것' 보다 숫자를 훨씬 많이 줄일 수 있기 때문임

참고 [이것이 취업을 위한 코딩 테스트다 with 파이썬_나동빈]
