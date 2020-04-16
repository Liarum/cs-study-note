# 6. 정렬(Sorting)

### 6-1. O(n²) 정렬

#### 정렬(sorting)

- 데이터를 정해진 키에 따라서 크기 순으로 배열하는 것
  - 오름차순(ascending order)
  - 내림차순(descending order)

#### 정렬 알고리즘의 성능

- 정렬할 데이터의 개수가 n개 일때, O(f(n)) 으로 표시
- O(n²) 정렬 알고리즘: 버블 정렬, 삽입 정렬, 선택 정렬, ...
- O(n log n) 정렬 알고리즘: 합병 정렬, 쾌속 정렬, ...

####  O(n²) 정렬

- 정렬 알고리즘의 성능은 정렬하고자 하는 원소의 수(n)의 제곱(n²)에 비례함
  - 이동에 기반한 정렬: 삽입 정렬
  - 교환에 기반한 정렬: 버블 정렬, 선택 정렬

##### 삽입 정렬(Insertion Sort)

- 추가(Insertion) 연산에 기반한 정렬 알고리즘

- 정렬되지 않은 리스트의 원소들을 차례로 정렬된 리스트에 추가하면 정렬이 수행됨

- 원소를 이동시켜서 정렬을 수행

- 배열의 가장 앞자리로부터 정렬된 부분 배열을 생성하고, 그 크기를 증가시킴

  - 부분 배열은 처음에는 배열의 첫 원소로부터 시작
  - 마지막으로 부분 배열이 배열과 일치하게 되면 정렬 완료

- 새로운 원소를 정렬된 부분 배열의 적당한 위치에 삽입하여 부분 배열의 정렬을 유지함

- 구현을 위해서는

  - 정렬된 배열에 새로운 원소를 삽입하는 연산이 필요함
  - 삽입 후에도 배열의 정렬이 유지되어야 함

  ```c++
  void insert (int x, int n, int arr[])
  {
      for (int i=0; i<n; i++)
      {
          if (arr[i] > x)
              break;
      }
      for (int j = n-1; j >= i; j--)
          arr[j+1] = arr[j];
      arr[i] = x;
  }
  ```

- 알고리즘 설계

  - 배열의 원소를 하나씩 부분 배열에 삽입하면서 정렬을 수행
  - 정렬이 끝난 배열의 앞부분을 부분 배열로 이용
    - k번째 원소까지 정렬이 끝난 상황 -> a[0] ~ a[k-1]을 부분 배열로 이용
  - 부분 배열a[0...k-1]에 대해서 (k+1)번째 원소인 a[k]를 a[0...k-1]에 삽입 -> 부분 배열은 a[0...k-1]에서 a[0...k]로 증가

  ```c++
  void insertion_sort(int n, int a[])
  {
      int i;
      for (i = 1; i< n; i++)
      {
          insert(a[i], i+1, a);
      }
  }
  ```

  

##### 버블 정렬(bubble sort)

- 교환을 통해서 더 작은 원소를 앞으로 보냄
- 서로 인접한 원소들 사이의 교환을 반복해서 정렬을 수행함
- 버블 정렬의 구현 과정
  - 배열의 가장 앞자리에 최솟값을 옮김( 배열의 가장 뒷자리로부터 원소들을 차례로 비교하면서 작은 값을 가장 앞 자리로 옮김 )
  - 배열의 두 번째 자리에 두 번째 작은 값을 옮김( 배열의 가장 뒷자리로부터 원소들을 차례로 비교하면서 작은 값을 두 번째 자리로 옮김 )
  - 이 과정을 n - 1번 반복함
  - 마치 거품(bubble)이 물밑에서 올라오는 듯해서 버블 정렬이라고 부름
  - Sinking sort 라고도 함(가장 큰 숫자를 맨 뒤로 보내는 알고리즘)

- 알고리즘 설계

  - 배열의 임의의 위치(i번째 위치)에서 다음의 연산을 수행함
    - i번째 위치에 (i) ~ (n-1)의 원소들 중에서 가장 작은 값이 옴 -> i번째에는 i번째 작은 값이 옴
    - (n-1)번째 위치부터 (i+1)번째 위치까지 순차적으로 비교하면서 진행함

  ```c++
  void bubble_sort(int n, int a[])
  {
      int i, j;
      for (i=0; i< n-1; i++)
      {
          for (j=n-1; j> i; j--)
          {
              if(a[j-1] > a[j])
                  swap(a[j-1], a[j]);
          }
      }
  }
  ```

  - swap() 함수
    - 두 매개변수의 값을 바꾸는 함수
    - call-by-reference 이용

  ```c++
  void swap(int &a, int &b)
  {
      int x;
      x = *a;
      *a = *b;
      *b = x;
  }
      
  ```



##### 선택 정렬(Selection Sort)

- 버블 정렬의 단점을 개선

  - i번째 자리에 올 원소는 i번째로 작은 원소 -> i번째로 작은 원소를 찾아서 i번째 원소와 교환

- 선택정렬의 구현 과정

  - 배열의 첫 번째 자리에 최솟값을 옮김: 배열에서 가장 작은 값과 첫 번째 원소와 교환
  - 배열의 두 번째 자리에 두 번째 작은 값을 옮김: 배열에서 두 번째 작은 값과 두 번째 원소와 교환
  - 이 과정을 반복
  - 버블 정렬과 다른 점은? select_min() 함수

  ```c++
  int select_min(int s, int e, int b[])
  {
      int min_idx = s;
      for (int i = s+1; i <= e; i++)
      {
          if (b[i] < b[min_idx])
              min_idx = i;
      }
      return min_idx;
  }
  ```

- 알고리즘 설계

  - 정렬하고자 하는 배열의 첫 번째 원소부터 차례로 방문
  - i번째 원소의 처리
    - a[i] ~ a[n-1]중에서 최솟값을 찾을 것 -> min_idx 는 최솟값의 인덱스를 가리킴
    - 최솟값과 a[i]의 값을 교환할 것 -> a[i]에 a[i] ~ a[n-1]까지의 최솟값이 오도록 함

  ```c++
  void selection_sort(int n, int a[])
  {
      int i;
      int min_idx;
      for (i = 0; i < n-1; i++)
      {
          min_idx = select_min(i, n-1, a);
          swap(a[i], a[min_idx]);
      }
  }
  ```

  
