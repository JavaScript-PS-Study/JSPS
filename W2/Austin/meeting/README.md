> 12월 01일 대면 모임 진행을 위한 PR입니다.

- 푼 사람 : @minh0518

- 푼 문제
  - [x] [신고 결과 받기](https://school.programmers.co.kr/learn/courses/30/lessons/92334)
  - [x] [주차 요금 계산](https://school.programmers.co.kr/learn/courses/30/lessons/92341)
  - [x] [K진수에서 소수 개수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/92335)

## 문제 1 : [K진수에서 소수 개수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/92335)

### 1. **문제 설명**

> 주어진 입력과 요구되는 출력에 대해 간략히 설명해주세요.

- 입력 : 정수 n , 변환해야 하는 진법 k

- 출력 : 문제에서 주어진 조건에 해당하는 소수의 갯수를 리턴

### 2. **문제의 엣지 케이스**

> 해당 문제가 가질 수 있는 극단적인 케이스에 대해 적어주세요.

-

### 3. **사용한 데이터 구조와 알고리즘**

> 문제를 풀기 위해 사용한 주요한 데이터 구조 및 알고리즘에 대해 적어주세요.

- 문자열 처리입니다. `split()` 메소드로 0을 기준으로 문자열을 구분지어서 배열로 변환한 다음 소수 판별 연산을 진행했습니다.

### 4. **의사 코드**

> 구현한 코드를 단계별로 설명해 주세요.

1. 주어진 숫자를 k진수로 변경합니다
2. 문제에서 요구한 내용을 자세히 읽다 보면, 0을 제외한 나머지 정수 구간에 대해
   소수를 판별하는 것을 알 수 있습니다
3. 그렇기 때문에 `split('0')` 을 이용해서 0을 제외한 구간을 파악하고 이에 대해 소수 갯수를 판별합니다

### 5. **시간 복잡도, 공간 복잡도 측정**

> 구현한 코드의 시간 복잡도와 공간 복잡도를 그 이유와 함께 적어주세요.

1.

### 6. **최적화**

> 구현한 코드에서 최적화 할 수 있는 부분이 있을까요? 있다면 어떻게 수정되어야 할까요?

- (아마도) 이 문제 의도 자체가 0의 좌우를 살펴가며 일일이 조건부 처리를 하는 것보다, 0을 제외한 정수 구간에 대해 소수 판별을 하는 것을 의도한 것 같습니다
  그렇기 최적화 관련해서는 추가적인 방안이 떠오르지 않습니다

### 7. **배운 점 또는 추가로 생각해볼 점**

> 인사이트에 대해 간략히 적어주세요.

## 역시 카카오 문제는 항상 문제 그 너머를 바라봐야 하네요,,,

## 문제 2 : [주차 요금 계산](https://school.programmers.co.kr/learn/courses/30/lessons/92341)

### 1. **문제 설명**

> 주어진 입력과 요구되는 출력에 대해 간략히 설명해주세요.

- 입력 : 주차 요금을 나타내는 정수 배열 fees, 자동차의 입/출차 내역을 나타내는 문자열 배열 records

- 출력 : 차량 번호가 작은 자동차부터 청구할 주차 요금을 차례대로 담은 정수 배열

### 2. **문제의 엣지 케이스**

> 해당 문제가 가질 수 있는 극단적인 케이스에 대해 적어주세요.

### 3. **사용한 데이터 구조와 알고리즘**

> 문제를 풀기 위해 사용한 주요한 데이터 구조 및 알고리즘에 대해 적어주세요.

- 대표적인 hash문자라고 생각합니다. `records`배열을 순회하며 각 차량에 대한 입,출에 대한 정보를 기록하고 이 기록을 기반으로 최종 시간과 가격을 계산해야 하기 때문입니다.

### 4. **의사 코드**

> 구현한 코드를 단계별로 설명해 주세요.

1. `records`배열을 순회하며 `info`라는 Map객체에 입,출차 정보 기록
   ![image](https://github.com/JavaScript-PS-Study/JSPS/assets/78631876/a9b74319-877d-4283-9127-9adfb74a32e4)

2. `info`라는 Map객체를 기반으로 주차 시간 계산

   - 각 차량에 대해서 입->출 형태로 주어지므로 2개씩 끊어서 계산
   - 해당 차량에 대한 시간목록이 홀수라면, 최종 출차시간이 없는 것이므로 23:59시간을 기반으로 계산

3. 계산된 시간으로 최종 요금 도출

### 5. **시간 복잡도, 공간 복잡도 측정**

> 구현한 코드의 시간 복잡도와 공간 복잡도를 그 이유와 함께 적어주세요.

1.

### 6. **최적화**

> 구현한 코드에서 최적화 할 수 있는 부분이 있을까요? 있다면 어떻게 수정되어야 할까요?

- 시간 복잡도 측면에서 개선점이 있을지는 모르겠으나, 입출차 시간이 기록된 배열을 2자리씩 끊어가며 최종 시간을 더할 때, 굳이 while문으로 하는 것보다 `reduce`배열을 사용하면 어떨까 싶기도 하네요

### 7. **배운 점 또는 추가로 생각해볼 점**

> 인사이트에 대해 간략히 적어주세요.

- 코테에서 고차원적인 알고리즘이 아닌, 이 문제같이 단순 hash를 통한 구현 문제를 풀 때, 최대한 시간을 빨리 단축해야 한다고 생각합니다. 자잘한 실수를 줄이고 보다 빨리 풀 수 있도록 노력해야 할 것 같아요
