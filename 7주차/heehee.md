# Graph

## 정의

연결되어 있는 원소들 사이의 다:다 관계를 표현하는 비선형 자료구조

- V : 정점(vertex)의 유한집합
- E : 간선(edges)이라고 하는 정점 쌍들의 집합

## Graph 종류

### 무방향 그래프

두 정점을 연결하는 간선에 방향이 없는 그래프로 간선을 나타내는 쌍에 순서가 없음.

### 방향 그래프

모든 간선은 방향을 가지고, 한쪽 방향으로만 갈 수 있음.

### 부분 그래프

원래의 그래프에서 정점이나 간선을 일부만 제외하여 만든 그래프

### 가중 그래프

정점을 연결하는 간선에 가중치를 할당한 그래프

## Graph 용어

### 인접 정점

하나의 정점에서 간선에 의해 직접 연결된 정점

### 무방향 그래프의 차수

- 정점에 연결된 간선 수
- 무방향 그래프의 모든 차수의 합 = 간선수 \* 2

### 방향 그래프의 차수

- 정점 v의 진입 차수: 정점 v로 들어오는 간선 수
- 정점 v의 진출 차수: 정점 v에서 나가는 간선 수
- 방향 그래프의 모든 진입(진출)차수의 합 = 간선 수

### 단순 경로

경로 중에서 반복되는 간선이 없는 경로

### 사이클

시작 정점과 종료 정점이 동일한 단순 경로

## Graph 구현

### 인접 행렬

- 2차원 배열을 사용하는 순차 자료구조 방법
- 그래프의 두 정점을 연결한 간선의 유무를 행렬로 저장
  - n개의 정점을 가진 그래프: n \* n 행렬 M (행, 열 번호가 정점)
  - if 간선(i,j)가 그래프에 존재 : M[i][j] = 1,
  - 그렇지 않으면 : M[i][j] = 0
- 인접 행렬의 대각선 성분(자기 자신)은 모두 0

- 장점
    1. 2차원 배열에 모든 정점들의 간선 정보가 있기 때문에, 간선 조회 시 O(1)의 시간 소요
- 단점
    1. 간선의 수와 무관하게 항상 n^2 크기의 2차원 배열이 필요하므로 메모리 공간이 낭비
    > 희소 그래프(정점의 수 >> 간선의 수)인 경우에는 인접 행렬에 의한 표현은 비효율적
    2. 모든 간선의 수를 탐색하는데 O(n^2)의 시간 소요

### 인접 리스트

- 각 정점(헤드 포인터로 설정)에 대한 인접 정점들을 연결하여 만든 단순 연결리스트

- 장점
    1. 존재하는 간선만 관리하면 되므로 메모리 사용 측면에서 보다 효율적
    2. 그래프의 모든 간선의 수를 알아내려면 각 정점의 헤더 노드부터 모든 인접리스트를 탐색해야하므로 O(n+e)의 시간 소요
    > 그래프에 있는 모든 노드를 방문하는 시간 O(n) + 해당 노드와 연결된 모든 간선 탐색하는 시간 O(e)
- 단점
    1. 간선을 조회하기 위해서는 정점의 인접 리스트를 탐색해야하므로 정점의 차수만큼( = O(v의 차수)) 시간 소요 