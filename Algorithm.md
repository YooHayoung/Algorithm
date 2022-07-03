# Algorithm
알고리즘이란 문제를 해결하기 위한 것으로, 명확하게 정의되고 순서가 있는 유한 개의 규칙으로 이루어진 집합으로 정의할 수 있다.

	1. 같은 답을 얻는 알고리즘은 하나가 아니다.
	2. 빠른 알고리즘은 메모리를 많이 요구한다.

알고리즘의 성능을 객관적으로 평가하는 기준을 복잡도라고 한다. 복잡도는 두가지 요소를 가진다.

	1. 시간 복잡도 : 실행에 필요한 시간을 평가한 것.
	2. 공간 복잡도 : 기억 영역과 파일 공간이 얼마나 필요한가를 평가한 것.

알고리즘을 선택할 때 시간, 공간 복잡도의 균형을 생각할 필요성이 있다. 
알고리즘에서 시간 복잡도는 주어진 문제를 해결하기 위한 연산 횟수를 말한다. 일반적으로 1억 번의 연산을 1초의 시간으로 간주하여 예측한다.
복잡도의 대소관계는 다음과 같다.
	- `O(1)` < `O(log n)` < `O(n)` < `O(n log n)` < `O(n^2)` < `O(n^k)` < `O(2^n)`

연산 횟수의 계산은 알고리즘의 시간 복잡도에 데이터의 크기를 대입하여 계산할 수 있다.

시간 복잡도의 도출 기준은 다음과 같다.
	- 상수는 시간 복잡도 계산에서 제외.
	- 가장 많이 중첩된 반복문의 수행 횟수가 시간 복잡도의 기준이 된다.

알고리즘 문제룰 풀 때, 다음과 같은 과정으로 문제를 푼다면 효율적일 듯 하다.
	1. 문제 분석하기
	2. 손으로 풀어보기
	3. 슈도코드 작성
	4. 코드 구현

위 과정을 통해 문제를 푸는 습관을 들이자. 문제를 보고 어떤 알고리즘을 사용하는 것이 좋을지 정하고, 손으로 그림, 슈도코드를 작성하면서 생각을 정리한 후, 코드를 구현하면 코드 구현단계에서 낭비하는 시간을 줄일 수 있을 듯 하다.


## 자료구조
### 배열
배열은 메모리의 연속 공간에 값이 채워져 있는 형태의 자료구조이다. 배열의 값은 인덱스를 통해 참조할 수 있고 선언한 자료형의 값만 저장할 수 있다. 배열의 특징은 다음과 같다.
	- 인덱스를 사용하여 값에 바로 접근 가능.
	- 새로운 값을 삽입하거나 특정 인덱스에 있는 값을 삭제하기 어렵다. 삽입, 삭제를 원하는 값의 인덱스 주변에 있는 값을 이동시켜야 한다.
	- 배열의 크기는 선언할 때 지정하고, 이후 수정이 불가하다.
	- 구조가 간단하다.

### 리스트
리스트는 값과 포인터를 묶은 노드라는 것을 포인터로 연결한 자료구조이다. C 언어의 연결 리스트로 생각하면 된다. 리스트의 특징은 다음과 같다.
	- 인덱스가 없다. 값에 접근하기 위해서는 Head 포인터부터 차례로 접근해야 한다. 따라서 속도가 느리다.
	- 포인터로 연결되어 있기 때문에 데이터의 삽입, 삭제 속도가 빠르다.
	- 리스트의 크기는 정해져 있지 않다. 크기가 변하기 쉬운 데이터를 다룰 때 적절하다.
	- 포인터를 저장할 공간이 필요하여 구조가 복잡하다.

### 덱
덱은 양 끝에서 데이터를 삽입하거나 삭제할 수 있는 자료구조이다.
	- 덱의 맨 앞부분을 front, 맨 뒷부분을 last라고 한다.
	- front 부분에 데이터를 삽입할 때는 `addFirst()`, 삭제할 때에는 `removeFirst()`를 이용한다.
	- last 부분에 데이터를 삽입할 때에는 `addLast()`, 삭제할 때에는 `removeLast()`를 이용한다.
	- 덱에서는 (index, value) 형태의 노드를 클래스로 구현하여 저장한다.

### 스택
스택은 삽입과 삭제 연산이 후입선출(LIFO)로 이루어지는 자료구조이다.
	- 삽입과 삭제가 한 쪽에서만 일어난다. 연산이 일어나는 위치를 `top`이라고 한다.
	- `push` : top 위치에 새로운 데이터를 삽입한다.
	- `pop` : top 위치에 있는 현재 데이터를 삭제하고 확인한다.
	- `peek` : top 위치에 현재 있는 데이터를 확인만 한다.
스택은 **깊이 우선 탐색(DFS)**과 **백트래킹 종류**의 코딩 테스트에 효과적이다. LIFO의 개념 자체가 재귀 함수 알고리즘 원리와 같기 때문이다.

### 큐
큐는 삽입과 삭제 연산이 선입선출(FIFO)로 이루어지는 자료구조이다.
	- 삽입과 삭제가 양방향에서 이루어진다. 새로운 값을 삽입하는 쪽을 `rear`, 기존 데이터를 꺼내는 쪽을 `front`라고 한다.
	- `add` 연산을 통해 `rear` 부분에 데이터를 추가한다.
	- `poll` 연산을 통해 `front` 부분에 있는 데이터를 삭제하고 확인한다.
	- `peek` 연산을 통해 큐의 `front` 부분에 있는 데이터를 단순 확인한다.
큐는 **너비 우선 탐색(BFS)**에서 자주 사용된다.


## 알고리즘
### 구간 합
구간 합은 합 배열을 이용하여 시간 복잡도를 더 줄이기 위해 사용하는 특수한 목적의 알고리즘이다. 기존의 배열을 전처리한 배열로 생각할 수 있다. 이를 미리 구해두면 배열의 일정 범위의 합을 구하는 시간 복잡도가 `O(n)`에서 `O(1)`로 감소한다.

합 배열을 만드는 공식은 다음과 같다.
	- `S[i] = S[i - 1] + A[i]`

합 배열에서 i에서 j까지의 구간 합을 구하는 공식은 다음과 같다.
	- `S[j] - S[i - 1]` (단, j >= i)

#### 2차원 배열에서 구간 합
2차원 배열에서 구간 합 배열을 만드는 공식은 다음과 같다.
	- `S[i][j] = S[i][j-1] + S[i-1][j] - S[i-1][j-1] + A[i][j]`

다음과 같은 2차원 배열이 있을 때, 위 공식을 이용하면 다음과 같은 구간 합 배열을 만들 수 있다.

1	2	3	4					1	3	6	10
2	3	4	5		->			3	8	15	24
3	4	5	6	(구간 합 배열)		6	15	27	42
4	5	6	7					10	24	42	64

위 구간 합 배열에서 [1, 3]의 값(6)은 [1, 1]에서 [1, 3]까지의 구간 합(1[1, 1] + 2[1, 2] + 3[1, 3])을 뜻한다.
구간 합 배열의 [2, 3]의 값(15)은 [1, 1]에서 [2, 3]까지의 구간 합(1, [1, 1] + 2[1, 2] + 3[1, 3] + 2[2, 1] + 3[2, 2] + 4[2, 3])을 말한다. 직선으로 연결되는 것이 아니라 해당 요소를 모서리로 하는 직사각형의 구간을 말한다고 볼 수 있다.

위의 2차원 배열에서 [2, 2], [3, 4]의 구간 합을 구하려면 구간 합 배열의 [2, 2] 요소와 [3, 4] 요소를 모서리로 하는 직사각형 구간의 합을 말한다. 따라서 구간 합 배열의 [3, 4] 요소에서 [3, 1] 요소의 값을 빼고, [1, 4] 요소의 값을 빼준다. 이렇게 값을 빼주면 구간 합 배열의 [1, 1]의 요소가 2번 빠졌기 때문에 이를 다시 더해주면 원하는 결과값이 나온다.
이에 대한 식은 다음과 같다.
	- `result = S[x2][y2] - S[x2][y1 - 1] - S[x1 - 1][y2] + S[x1 - 1][y1 - 1]`


### 투 포인터
배열 등에서 2개의 포인터로 알고리즘의 시간 복잡도를 최적화하는 방법이다.

### 슬라이딩 윈도우
2개의 포인터로 범위를 지정한 다음, 범위를 유지한 채로 이동하며 문제를 해결하는 방법이다. 투 포인터 알고리즘과 매우 유사하다. 









#Algorithm