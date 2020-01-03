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
