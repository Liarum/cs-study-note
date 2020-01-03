## 1. 자료구조의 소개
### 1-1. 개요

- 자료구조란? 

  `다양한 자료(데이터)를 관리하는 역할`

  `자료와 순서를 관리한다`

  => " **자료**를 **효율적**으로 **관리**하는 **기법** ! "

  - 리스트(List) + 트리(Tree) / 그래프(Graph)

  

### 1-2. 자료와 관리

- 자료(data) 란 무엇인가?

  - 컴퓨터에 저장할 수 있는 모든 값
  - 컴퓨터에서 혀용하는 형태의 값만 저장할 수 있음 => 자료형

- 자료형(data type) 이란?

  - 컴퓨터에 저장할 수 있도록 프로그래밍 언어에서 미리 정의된 값들의 집합

    1) 시스템에서 제공하는 자료형

    2) 사용자가 정의하는 자료형

    

  1) 시스템에서 제공하는 자료형(System-defined data type)

  - 자료의 단위

    - 비트(Bit) : 0 또는 1을 기록할 수 있는 최소 단위
    - 바이트(Byte) : 8bits
    - 워드(Word) : 컴퓨터의 내부에서 한번에 전송하거나 처리하는 단위 / 4 bytes 또는 8 bytes

  - 자료의 구성

    - 세상의 모든 자료는 문자와 숫자로 구성된다.
    - 문자 -> char, char *(string)
    - 숫자 -> int(정수), float(실수)

  - char(문자 표현)

    - ASCII code : 8bit 로 영어, 숫자, 특수 문자를 표현하는 체계

      - 7bits + 1bit(parity 검사)

      - 표혀할 수 있는 문자에 한계가 있음

    - Uni-code : 16bit 로 세상의 모든 문자를 표현할 수 있는 체계

  - int (정수 표현)

    - 4 byte를 사용(시스템에 따라 다름)
      - 표현할 수 있는 범위: - 2^31 ~ 2^31 -1
      - 다양한 크기로 확장됨: _int8, _int16, _int32, _int64
    - 언어에 따라 정수 표현 방법이 다양하게 제공되는데, C같은 경우는 short(2 bytes), long(4 bytes), unsigned int(4 bytes) 등과 같은 다양한 정수 자료형이 존재함
      - short type의 표현 범위: -2^15 ~ 2^15 -1
      - unsigned int type 의 표현 범위: 0 ~ 2^32 -1

    - 음수의 3가지 표현 방법 ( 대부분 2의 보수를 사용 )
      - Sign bit : 1번째 bit 또는 MSB(Most Significant Bit) 를 이용
      - 1의 보수
      - 2의 보수

  - float(실수 표현)
    - 부동 소수점(floating point)

  

  2) 사용자가 정의하는 자료형(User-defined data type)

  - structure (C언어)
  - class(C++, JAVA, Python)



- 자료의 관리(Manipulation)

  - 추가(insert), 제거(delete), 검색(search), 갱신(modify), 출력, 정렬 등 많은 관리 작업이 가능

  - 가장 중요한 3연산: 추가, 제거, 검색

  - 추가와 제거는 1번만 사용 가능

  - 검색은 매우 빈번하게 사용 -> 가장 중요한 관리 작업은 "검색"임

    <검색(search) 의 3가지 종류>

    - 주어진 집합에서 임의의 원소를 찾아라(Find arbitrary)
    - 주어진 집합에서 가장 먼저/늦게 온 원소를 찾아라(Find earliest/last)
    - 주어진 집합에서 top(최대/최소)인 원소를 찾아라(Find top)

  

### 1-3. 효율적인 기법

- 기법(technique) 이란? 
  - 자료를 적절한 구조(structure)를 갖도록 조직하고 그에 따른 연산(operation)을 제공하는 것
- 구조(structure) 란?
  - 개별적인 자료들이 목적에 적합한 관계를 갖도록 배치된 상태
- 연산(operation) 이란?
  - 자료를 관리하기 위하 작업(추가, 제거, 검색, etc)
  - 구조는 달라도 연산은 동일함 -> 구조에 따른 연산의 구현 방법은 다름

* 자료 구조의 종류

​	(1) 리스트(List)

​	(2) 정렬된 리스트 (Sorted List)

​	(3) 큐 (Queue)

​	(4) 계층 구조(hierarchy) -> 트리(Tree)

​	(5) 그래프(Graph)



##### 추상화 (Abstraction)

- 개별적인 사람이나 사물, 상황의 성질로부터 추출되어 가공된 일반적이고 공통적인 개념

- 자료구조에서의 추상화
  - 매우 다양한 형태의 자료가 존재함 -> 각 자료들의 개별적인 속성을 제거하고 공통된 속성을 추출하여 이를 이용하는 과정

- 추상 자료형(abstract data type)
  - 자료와 자료에 대한 연산들을 명기한 개념
  - class of objects whose logical behavior is defined by a set of values and a set of operations



##### 효율(efficiency)

- 어떤 성과(solution) 을 얻기 위해서 얼마나 많은 자원(resource)을 투입하였는지를 측정

- 성능(performance) 이라고도 함

- "efficiencty 또는 performance = solution / resource"

- 효율적(efficienct) 과 효과적(effective)

  - 어떤 성과를 얻기 위해서 얼마나 많은 자원을 투입하였는지를 측정하는 점은 동일
  - 효율적: 동일한 성과를 얻기 위해서 투입된 자원의 크기에 따라서 결정됨
  - 효과적: 동일한 자원을 투입했을 때 얻는 성과의 크기에 따라서 결정됨

- 성능의 3가지 경우

  - 최선의 경우(Best case)
  - 평균의 경우(Average case)
  - 최악의 경우(Worst case)

  ##### ==> 자료구조에서의 성능은 최악의 경우에 대한 성능

- 컴퓨터의 자원(resource)
  - 시간(time) -> cpu
  - 공간(space) -> 메모리(memory)



##### 자료구조의 성능

- 입력된 자료의 크기에 따라서 시간(공간) 이 얼마나 필요한 지 측정
- 입력된 자료의 크기가 증가할수록 요구되는 시간(공간)의 증가 속도를 표현



##### 자료를 효율적으로 관리하는 기법

- 일차원 구조
  - 리스트(List) : 배열(array), 연결 리스트(linked list), 스택/큐(stack/queue)
- 계층 구조
  - 트리(Tree) : 이진 탐색 트리(binary search tree), 우선 순위 큐(priority queue)



##### 관계를 표현하고 정보를 추출하는 기법

- 그래프(Graph)



##### 그 외 추가적으로 공부해야 할 것

- 맵/집합(map/set)
- 균형 이진 탐색 트리(balanced binary search tree)
- 해시(hash)
- 네트워크(network)
- STL