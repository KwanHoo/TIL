# _정렬 Sorting_

- 연속된 데이터를 기준에 따라서 정렬하기 위한 알고리즘

## <1> 기준에 따라 데이터를 정렬

- 데이터를 정렬하면 이진 탐색(binary search)이 가능해짐

  - 정렬은 이진탐색의 전처리 과정이기도함

- 선택정렬, 삽입정렬, 퀵정렬, 계수 정렬... 등 다양함
  - 파이썬에서 제공하는 기본 정렬 라이브러리를 적용할 수 있음
- 정렬을 할때는 알고리즘 효율성을 생각해야함
- 내림차순은 오름차순 정렬을 수행한 뒤에 뒤집기(Reverse)하여 진행할 수 있음
  - 뒤집는 연산은 O(N)의 복잡도로 간단히 수행할 수 있음

### 선택 정렬 Selection Sort

- 매번 가장 작은 것을 선택
- 데이터가 무작위로 여러개 있을 때, 이중에서 가장 작은 데이터를 선택해 맨 앞에 있는 데이터와 바꾸고, 그다음 작은 데이터를 선택해 앞에서 두번째 데이터와 바꾸는 과정을 반복
- 가장 작은 데이터를 앞으로 보내는 과정을 N -1번 반복하면 정렬이 완료되는 것임

```python
array = [7, 5, 9, 0, 3, 1, 6, 2, 4, 8]

for i in range(len(array)):
    min_index = i # 가장 작은 원소의 인덱스
    for j in range( i+1, len(array)):
        if array[min_index] > array[j]:
            min_index = j
    array[i], array[min_index] = array[min_index], array[i] #스와프

print(array)

```

#### 스와프 Swap

- 특정한 리스트가 주어졌을 때 두 변수의 위치를 변경하는 작업을 의미함
- 파이썬은 간단히 스와프 작업이 가능함
  - 다른언어에서는 temp(임시저장용 변수)를 만들어 두 원소의 값을 변경함

```python
# 0 인덱스와 1 인덱스의 원소 교체하기
array = [3,5]
array[0], array[1] = array[1], array[0]

print(array) # [5,3]
```

- 선택 정렬은 기본 정렬 라이브러리를 포함해 뒤에서 다룰 알고리즘과 비교했을 대 매우 비효율적임
- 선택 정렬의 시간 복잡도 : O(N^2)

---

### 삽입 정렬

- 특정한 데이터를 적절한 위치에 삽입하는 정렬
- 선택 정렬은 알고리즘 문제 풀이에 사용하기에는 느린편임
- A1 : '데이터를 하나씩 확인하며, 각 데이터를 적절한 위치에 삽입해보면?'

- 삽입 정렬은 필요할 때만 위치를 바꾸므로 '데이터가 거의 정렬되어 있을 때' 훨씬 효율적임
- 삽입 정렬은 특정한 데이터가 적절한 위치에 들어가기 이전에, 그 앞까지의 데이터는 이미 정렬되어 있다고 가정함
  - 정렬되어 있는 데이터 리스트에서 적절한 위치를 찾은 뒤에, 그 위치에 삽입된다는 점이 특징임

```python
array =[7,5,9,0,3,1,7,2,4,8]

for i in range(1, len(array)):
    for j in range(i, 0, -1):       # 인덱스 i부터 1까지 감소하며 반복하는 문법
        if array[j] < array[j-1]:   # 한 칸씩 왼쪽으로 이동
            array[j], array[j-1] = array[j-1], array[j]
        else:                       # 자기보다 작은 데이터를 만나면 그 위치에서 멈춤
            break

print(array)
```

#### range의 세번째 매개변수

- range의 매개변수 3개(start, end, step)임
- step에 -1이 들어가면 start 인덱스 부터 시작해서 end +1 인덱스까지 1씩 감소함

- 삽입 정렬의 시간 복잡도 : O(N)

---

### 퀵 정렬

- 가장 많이 사용되는 알고리즘 중 하나

  - 퀵 정렬과 비교할 만큼 빠른 알고리즘으로 병합 정렬이 있음

- '기준 데이터를 설정하고 그 기준보다 큰 데이터와 작은 데이터의 위치를 바꾸면 어떨까?'

- 퀵 정렬에서는 피벗(Pivot)이 사용됨
  - 큰 숫자와 작은 숫자를 교환할 때 교환하기 위한 기준
- 호어 분할(Hoare Partition)

  - 리스트에서 첫 번째 데이터를 피벗으로 정함
  - 피벗을 설정한 뒤 왼쪽에서부터 피벗보다 큰데이터 찾고, 오른쪽에서부터 피벗보다 작은 데이터를 찾음
  - 큰데이터와 작은 데이터의 위치를 서로 교환해줌

- 퀵 정렬은 재귀함수와 동작 원리가 같음
  - 퀵 정렬은 재귀 함수 형태로 작성했을 때 구현이 간결해짐
  - 종료조건 : 현재 리스트의 데이터 개수가 1개인 경우
- 퀵정렬의 시간 복잡도 : O(NlogN)

---

### 계수 정렬 count sort

- 특정한 조건이 부합할 때만 사용할 수 있지만 매우 바른 정렬 알고리즘임
- '데이터의 크기 범위가 제한되어 정수 형태로 표현할 수 있을 때' 만 사용가능
  - 일반적으로 가장 큰 데이터와 가장 작은 데이터의 차이가 1,000,000을 넘지 않을 때 효과적으로 사용할 수 있음
- '모든 범위를 담을 수 있는 크기의 리스트(배열)를 선언' 해야 하기 때문

- 계수 정렬은 일반적으로 별도의 리스트를 선언하고 그안에 정렬에 대한 정보를 담음
- 결과적으로 리스트에는 각 데이터가 몇 번 등장했는지 그 횟수가 기록됨

- 계수 정렬의 시간 복잡도 O(N + K)
  - 데이터의 개수를 N
  - 데이터 중 최대값의 크기를 K
  - 현존하는 정렬 알고리즘 중에서 기수정렬과 더불어 가장 빠름

## 파이썬의 정렬 라이브러리

- 정렬 알고리즘 문제는 어느 정도 정해진 답이 있는, 즉 외워서 잘 풀어낼 수 있는 문제임
- 앞의 구현하는 코드보다 미리 만들어진 라이브러리를 이용하는 것이 효과적인 경우가 더 많음

- 파이썬은 기본 정렬 라이브러리인 sorted() 함수를 제공함
- sorted()는 퀵 정렬과 동작 방식이 비슷한 병합 정렬을 기반으로 만들어졌음
  - 병합 정렬은 일반적으로 퀵 정렬보다 느리지만 최악의 경우에도 시간 복잡도 O(NlogN)을 복장함
- 이러한 sorted() 함수는 리스트, 딕셔너리 자료형 등을 입력받아서 정렬된 결과를 출력함
  - 집합, 딕셔너리 자료형을 입력 받아도 반환되는 결과는 리스트 자료형임

```python
array = [7,5,9,0,3,1,6,2,4,8]

result = sorted(array)
print(result)
```

- 리스트 변수가 하나 있을 때 내부 원소를 바로 정렬할수 있음
- 리스트 객체의 내장 함수인 sort()를 이용하는 것

```python
array = [7,5,9,0,3,1,6,2,4,8]

array.sort()
print(array)
```

- sorted()나 sort() 를 이용할 때에는 key 매개변수를 입력으로 받을 수 있음
- key 값으로는 하나의 함수가 들어가야 하며 이는 정렬 기준이 됨

```python
array = [('바나나', 2), ('사과', 5), ('당근', 3)]

def setting(data):
    return data[1]
result = sorted(array, key = setting)
print(result)
# [('바나나', 2), ('당근', 3), ('사과', 5)]
```

- 문제에서 별도의 요구가 없다면 단순히 정렬해야 하는 상황에서는 기본 정렬 라이브러리를 사용하고, 데이터의 범위가 한정되어 잇으며 더 빠르게 동작해야 할 때는 계수 정렬을 사용하자

#### 코딩테스트에서 정렬 알고리즘이 사용되는 경우 3가지 문제유형

1. 정렬 라이브러리로 풀 수 있는 문제

- 단순히 정렬 기법을 알고 있는지 물어보는 문제
- 기본 정렬 라이브러리 이용

2. 정렬 알고리즘의 원리에 대해서 물어보는 문제

- 선택정렬, 삽입정렬, 퀵정렬 등의 원리를 알고 있었야 문제 풀 수 있음

3. 더 빠른 정렬이 필요한 문제

- 퀵 정렬 기반의 정렬 기법으로는 풀 수 없으며 계수 정렬 등의 다른 정렬 알고리즘을 이용하거나 문제에서 기존에 알려진 알고리즘의 구조적인 개선을 거쳐야 풀 수 있음

## <2> 위에서 아래로

- 기본 정렬 물어보는 문제
- 파이썬 기본 정렬 라이브러리 이용

## <3> 성적이 낮은 순서로 학생 출력하기

- 최악의 경우 O(NlogN)을 보장하는 알고리즘 이용 or O(N)을 보장하는 계수정렬을 이용
- 입력되는 데이터는 학생의 이름과 점수지만 출력할 때는 학생의 이름만 출력하면 되므로 학생 정보를 (점수, 이름) 으로 묶은 뒤에 점수를 기준으로 정렬을 수행해야 함
  - 파이썬 기본 정렬 라이브러리 사용하는 것이 효과적임

## <4> 두 배열의 원소 교체

- A 배열에서 가장 작은 원소를 골라 B 배열에서 가장 큰 원소와 교체를 하는 것임
- 단, 교환하는 대상이 A가 B 보다 작아야함
- A원소는 오름차순 정렬
- B원소는 내림차순 정렬
- O(NlogN)

참고 [이것이 취업을 위한 코딩 테스트다 with 파이썬_나동빈]
