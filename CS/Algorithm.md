# Algorithm
## Union Find
### Union Find란?
Union Find란  **Disjoint Set**을 표현할 때 사용하는 독특한 형태의 자료구조
> **Disijoint Set**은 서로 중복되지 않는 부분 집합들로 나눠진 원소들에 대한 원소들에 대한 자료구조 = 서로소 집합 자료구조

### Union Find의 연산
- make-set (x)
    - 초기화 , x를 유일한 원소로 하는 새로운 집합을 만든다.
- union(x,y)
    - 합하기, x가 속한 집합과 y가 집한 집합을 합친다.
- find(x)
    - 찾기, x가 속한 집합의 대표값을 반환한다.
  
### Union Find 표현법
- 배열로 표현하기 :
    - 구현 : 1차원 배열을 이용하여 각 원소가 속하는 그룹의 번호를 저장하고 있도록 만든다.
    - 단점 : 합치기 연산을 할때 모든 원소를 순회하면서 다른쪽 집합으로 옮겨주어야 하는데 합치기 연산이 많다면 시간이 많이 걸리는 문제가 있음.
- 트리로 표현하기  :
    - 구현: 한 집합에 속하는 원소들을 하나의 트리로 묶어준다. 두 원소가 같은 집합인지 확인하기 위해서는 원소가 포함된 루트를 찾은 뒤 같은지 확인하면 된다. 이 연산을 위해서는 자식 노드가 부모노드의 포인터를 가지고 있어야 하고 부모노드는 자기 자신을 가지도록 만든다. 합치기를 할때 양 트리의 부모노드를 찾아서 비료한 후 다른 집합이면 한 집합의 자식노드로 연결해 주면 된다. (실제 노드로 연결하지 않고 배열로 구현할 수 잇음)
    - 단점 : 트리를 사용하므로 연산의 순서에 따라 잘못하면 트리가 한쪽으로 기울 수 있다.
    - 최적화 하기 :
        1. 높이가 더 낮은 트리를 더 높은 트리 밑에 넣어서 구현하기 (두 트리의 높이가 같은 경우에만 높이가 증가함)
        2. 부모를 루트로 변환해서 찾기 연산의 중복을 방지함.

