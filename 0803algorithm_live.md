# 0803 알고리즘 LIVE 강의

 **배우는 과정에서는 라이브러리에 의존하지 말자** 

 **시험 환경과 동일하게 하기 위해 `PyCham` 설치!** 

### 알고리즘이란?

- `알 콰리즈미` 라는 아랍의 수학자 이름에서 유래함
- 문제를 해결하기 위한 절차 `유한한 단계` 를 통해서 문제를 해결하기 위한!
- 컴퓨터 분야에서 알고리즘을 표현하는 방법은 크게 두가지pseudo code순서도
- 무엇이 좋은 알고리즘인가?
  - 정확성: 얼마나 정확하게 동작하는가
  - 작업량: 얼마나 적은 연산으로 원하는 결과를 얻어내는가
  - 메모리 사용량: 얼마나 적은 메모리를 사용하는가
  - 단순성: 얼마나 단순한가
  - 최적성: 더 이상 개선할 여지가 없이 최적화되었는가
- 주어진 문제를 해결하기 위해 여러 개의 다양한 알고리즘이 가능어떤 알고리즘을 사용해야 하는가? 알고리즘의 성능 분석 필요 ⇒ 성능 분석의 기준은 작업량작업량 ⇒ 시간복잡도로 표현
- `시간복잡도(Time Complexity)`실제 걸리는 시간을 측정실행되는 명령문의 개수를 계산
- `빅-오 표기법Big-O Notation`: 시간복잡도 함수 중에서 가장 큰 영향력을 주는 n에 대한 항만을 표시계수는 생략하여 표시

### 배열 array

- 일정한 자료형의 변수들을 하나의 이름으로 열거하여 사용하는 자료구조프로그램 내에서 여러 개의 변수가 필요할 때, 일일히 다른 변수명을 이용하여 자료에 접근하는 것은 매우 비효율적일 수 있다. 배열을 사용하면 하나의 선언을 통해 둘 이상의 변수를 선언할 수 있다. 단순히 다수의 변수 선언을 의미하는 것이 아니라, 다수의 변수로는 하기 힘든 작업을 배열을 활용해 쉽게 할 수 있다.

- 1차원 배열

  - 1차원 배열의 선언

    - 별도의 선언 방법이 없으면 변수에 처음 값을 할당할 때 생성

    - 이름 : 프로그램에서 사용할 배열의 이름

        `Arr = list()` / `Arr = []`

    - 1차원 배열의 접근

      - Arr[0] = 10; // '배열 Arr의 0번째 원소에 10을 저장하라'
      - Arr[idx] = 20; // '배열 Arr의 idx 원소에 20을 저장하라'

### 정렬

- 2개 이상의 자료를 특정 기준에 의해 작은 값부터 큰 값(오름차순ascending) 혹은 그 반대의 순서대로(내림차순descending) 재배열하는 것

- 키Key자료의 정렬 기준이 되는 특정 값

- 대표적인 정렬 방식의 종류

  - 버블 정렬 Bubble Sort ⇒ O(n^2)
  - 카운팅 정렬 Counting Sort ⇒ O(n+k)
  - 선택 정렬 Selection Sort ⇒ O(n^2)
  - 퀵 정렬 Quick Sort ⇒ O(n log n)
  - 삽입 정렬 Insertion Sort ⇒ O(n^2)
  - 병합 정렬 Merge Sort ⇒ O(n log n)

- 버블 정렬

  - 인접한 두 개의 원소를 비교하여 자리를 계속 교환하는 방식

  - 정렬 과정 첫 번째 원소부터 인접한 원소끼리 자리를 계속 교환하면서 맨 마지막 자리까지 이동한다. 한 단계가 끝나면 가장 큰 원소가 마지막 자리로 정렬된다. 교환하며 자리를 이동하는 모습이 물 위에 올라오는 거품 모양과 같다고 하여 버블 정렬이라고 한다.

  - 시간 복잡도 : O(N^2)

  - 배열을 활용한 버블 정렬

    ```python
    def BubbleSort(a): 
        # 정렬할 list2          
        for i in ragne(len(a)-1, 0, -1): 
            # 범위의 끝 위치3                  
            for j in range(0, 1):
                if a[j] > a[j+1]:
                    a[j], a[j+1] = a[j+1], a[j] #swap`
    ```

    

  - @PyCham

    ```Python
    def BubbleSort(a):          
        for i in ragne(len(a)-1, 0, -1): # 4 3 2 13                  		for j in range(0, 1):
            if a[j] > a[j+1]:
                a[j], a[j+1] = a[j+1], a[j] 
                #swap67  
    data = [55, 7, 78, 12, 42] 
    BubbleSort(data) 
    print(data)
    ```

    - 해당 코드에서는 `exit code`가 없는 오류가 발생!

- 카운팅 정렬

  - 항목들의 순서를 결정하기 위해 집합에 각 항목이 몇 개씩 있는지 세는 작업을 하여, 선형 시간에 정렬하는 효율적인 알고리즘

  - 제한사항정수나 정수로 표현할 수 있는 자료에 대해서만 적용 가능 : 각 항목의 발생 회수를 기록하기 위해, 정수 항목으로 인덱스 되는 카운트들의 배열을 사용하기 때문카운트들을 위한 충분한 공간을 할당하려면 집합 내의 가장 큰 정수를 알아야 한다.

  - 시간복잡도 : O(n+k) : n은 리스트 길이, k는 정수의 최대값

  - 예시 코드

    ```python
    #카운팅 정렬
    def Counting_Sort(A,B,k):
        C = [0]*k #카운트 배열
    
        for i in range(0,len(A)):
            C[A[i]] += 1 #배열내의 항목들의 발생횟수마다 카운트배열 1씩 증가
        for i in range(1,len(C)):
            C[i]+=C[i-1]
        for i in range(len(A)-1,0,-1): #원본 배열의 뒤부터 탐색
            C[A[i]] -= 1                #카운트 배열에서 1 빼기 -> 하나 자리에 넣었으니까
            B[C[A[i]]] = A[i]           #카운트배열이 가르키는 자리에 원소 넣기
        return B
    
    arr=[0,4,1,3,1,2,4,1]
    print(Counting_Sort(arr,[0]*len(arr),5))
    ```

    

### 완전검색

- Brute-force 혹은 generate-and-test 기법이라고도 불린다.

- 문제의 해법으로 생각할 수 있는 모든 경우의 수를 나열해보고 확인하는 기법. 모든 경우의 수를 테스트한 후 최종 해법을 도출 = 속도는 느리지만, 해답을 찾아내지 못할 확률이 작다.

- 우선 완전검색으로 접근하여 해답을 도출한 후, 성능 개선을 위해 다른 알고리즘을 사용하고 해답을 확인하는 것이 바람직!

- Baby-gin Game

  - 0-9 사이의 숫자 카드에서 임의의 카드 6장을 뽑았을 때, 3장의 카드가 연속적인 번호를 갖는 경우를 run / 3장의 카드가 동일한 번호를 갖는 경우를 triplet / 6장의 카드가 run과 triplet으로만 구성된 경우를 `baby-gin` 이라고 부른다.

  - 6자리 숫자를 입력받아 baby-gin 여부를 판단하는 프로그램을 작성하라:

      완전검색으로 :  모든 경우의 수를 조합하여 6개 숫자의 순열을 만든 후,  앞의 3가지 / 뒤의 3가지를 테스트하여 각각 검증하자

    - 순열 만드는 법 = 중복순열

      ```python
      # 1, 2, 3을 중복 상관없이 포함하는 모든 순열을 생성하는 함수
      for i1 in range(1, 4):
          for i2 in range(1, 4):
              for i3 in range(1, 4):                        print(i1, i2, i3)
      ```

       

    - 순열 만드는 법 = 중복 없는 순열

      ```python
      # 1, 2, 3을 중복 없이 포함하는 모든 순열을 생성하는 함수
      for i1 in range(1, 4):
          for i2 in range(1, 4):
              if i2 != i1:
                  for i3 in range(1, 4):                                  if i3 != i1 and i3 != i2:8                                          print(i1, i2, i3)`
      ```

      

      

### 탐욕(Greedy) 알고리즘

- 최적해를 구하는 데 사용되는 근시안적인 방법. 여러 경우 중 하나를 결정해야 할 때마다 그 순간에 최적이라고 생각되는 것을 선택해나가는 방식으로 진행하여 최종적인 해답에 도달한다.

- 각 선택의 시점에서 이루어지는 결정은 지엽적으로는 최적이지만, 그 선택들을 계속 수집해서 최종적인 해답을 만들었다고 하여 그것이 최적이라는 보장은 없다.

- 일반적으로, 머릿속에 떠오르는 생각을 검증 없이 바로 구현하면 Greedy 접근이다.

- 거스름돈 줄이기 

  - "어떻게 하면 손님에게 거스름돈으로 주는 지폐와 동전의 개수를 최소한으로 줄일 수 있을까?"
  - 해 선택 : 단위가 큰 동전만으로 거스름돈을 만든다.
  - 실행 가능성 검사 : 거스름돈이 액수를 초과하는지 확인. 
  - 초과한다면 마지막에 추가한 동전을 빼고, 1로 돌아가서 현재보다 한 단계 작은 단위의 동전을 추가한다.
  - 해 검사 : 거스름돈을 확인해서 모자라면 1로 돌아가서 다시 추가할 동전을 고른다.

- 탐욕 알고리즘으로 Baby Gin 풀기

  ```python
  num = 4567892  
  c = [0] * 12
  
  for i in range(6):
      c[num % 10] += 15      
      num //= 10     
      i = 0
      tri = run = 0
      while i < 10:
      if c[i] >= 3:
          c[i] -= 3
          tri += 3          
          continue      
          if c[i] >= 1 and c[i+1] >= 1 and c[i+2] >= 1:
              c[i] -= 1
              c[i+1] -= 1          
              c[i+2] -= 1
              run += 1         
              continue
           i += 1
              if tri + run == 2:
                  print("Baby Gin")
              else : 
                  print("Lose")`
  ```

  

  