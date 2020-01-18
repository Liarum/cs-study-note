## Data Structure - Array

## 3. 배열(Array)

### 3-1. 리스트와 배열

- 리스트: 가장 기초적이고 오랫동안 사용된 자료 구조
- 배열: 리스트의 가장 널리 사용되는 구현 방법



##### 리스트의 개념

- 원소들을 한 줄로 나열한 구조(특별한 순서를 따름)
- 가장 오랫동안 가장 널리 사용된 구조
- ex) 전화번호부, 앱스토어, 음악 플레이어, 버스 도착 정보



##### 리스트의 정의

- 유한한 원소들의 나열(a finite sequence of elements)
- **각 원소들은 인덱스에 대응됨**



##### 리스트의 구현 방법

- 배열(Array) : 인덱스에 기반한 구현
  - 메모리에 배열의 크기보다 더 큰 연속된 공간이 허용될 때 사용
- 연결 리스트(Linked list): 포인터에 기반한 구현
  - 메모리에 배열의 크기보다 더 큰 연속된 공간이 없을 때 사용



##### 2가지 리스트

- 정렬된 리스트: 원소의 위치를 예측할 수 있음
- 정렬되지 않은 리스트: 원소의 위치를 예측할 수 없음

| 구분                 | 검색                         | 추가                                      | 제거                                                 |
| -------------------- | ---------------------------- | ----------------------------------------- | ---------------------------------------------------- |
| 정렬된 리스트        | 원소의 위치를 예측할 수 있음 | 정렬에 맞춰 추가해야 하므로 시간이 소요됨 | 제거할 원소를 찾은 후 제거 후 리스트를 재정비 해야함 |
| 정렬되지 않은 리스트 | 원소의 위치를 예측할 수 없음 | 정렬할 필요 없이 그냥 추가하면 됨         | 위와 같음                                            |



##### 리스트의 종류

- 원소를 저장하는 리스트: 배열 / 연결 리스트
- 원소와 순서를 저장하는 리스트: 스택 / 큐



#### 2. 배열

- 리스트를 index 를 이용해서 구현한 구조
- 연속적으로 할당된 기억 공간
- 모든 프로그래밍 언어에서 기본적으로 제공
- 배열의 모든 원소들은 index 에 대응됨
- n개의 자료를 하나의 주소로 접근할 수 있음



##### 메모리에서 배열의 구현

![](C:\Users\ahrum\Desktop\메모리상배열.png)

​			=> mylist의 주소(23040)으로 4개의 원소에 접근할 수 있음



##### 배열의 구현 팁

- 배열과 함께 배열의 크기 및 현재 저장된 원소의 갯수를 함께 생각할 것

  ```c++
  /*
  	arr: 배열
  	size: 배열의 크기
  	count: 현재 배열에 저장된 원소의 갯수 (count <= size), 반드시 0으로 초기화 해서 사용할 것
  */
  
  // 정적 배열(static array) => 컴파일 될 때 기억공간을 할당받음
  #define SIZE 100
  {
      int count = 0;
     	int arr[SIZE];
  }
  
  // 동적 배열(dynamic array) => 실행될 때 할당받음
  #define SIZE 100
  {
      int count = 0;
      int *arr = calloc(SIZE, sizeof(int));
  }
  ```



##### 배열의 기본 연산(프로그래밍 언어에서 제공)

- 생성(create): n개의 원소를 저장할 수 있는 배열 공간을 할당

- 인출(retrieve) : 배열의 i번째 원소를 읽어옴 ( <-> 검색 연산은 원소를 주고 인덱스를 가져오는 것 )

- 저장(store): 원소 x를 배열의 i번째 위치에 저장

  ```c++
  int L[10];
  int x = L[5];
  L[5] = x;
  ```

  