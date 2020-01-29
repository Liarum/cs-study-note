# Linked List

### 4-1. 연결 리스트

- 리스트의 정의 복습
  - 리스트란: 유한한 원소들의 나열(a finite sequence of elements)
  - 각 원소들은 인덱스에 대응됨(index => element)
  - 2가지 형태의 구현이 존재
    - 인덱스 기반 구현 -> 배열(Array)
    - 포인터 기반 구현 -> 연결 리스트(Linked List)



##### 배열과 연결리스트의 비교

- 배열: 원소들이 메모리에서 일정한 간격(a fixed distance)으로 나열되어 있음

- 연결 리스트: 원소들이 메모리에서 임의의 위치(at arbitrary position)에 배치되어 있음, 한 원소는 다음 원소를 가리키는 link 를 가지고 있음

| a0   | a1   | a2   | a3   | a4   | a5   | a6   |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| BAT  | CAT  | EAT  | FAT  | HAT  | JAT  | LAT  |

![](./imgs/arry_vs_linkedlist.jpg)

|            | 배열                                                    | 연결리스트                                                 |
| ---------- | ------------------------------------------------------- | ---------------------------------------------------------- |
| 메모리공간 | 연속된 메모리 주소                                      | 이산된 메모리 주소                                         |
| 공간 할당  | 정적 할당/동적 할당                                     | 동적 할당                                                  |
| 접근 경로  | 첫 번째 원소의 주소                                     | 첫 번째 원소의 주소                                        |
| 접근 방법  | 인덱스                                                  | 포인터                                                     |
| 접근 방식  | Random access (원소의 위치와 접근 시간의 연관성이 없음) | Sequential access(접근 시간이 원소의 위치에 의해서 결정됨) |



##### 연결 리스트

- node = data + link

- node는 메모리의 임의의 위치에 배치된다

- 각 node는 다음 node를 가리키는 link를 포함하고 있음

- 구조체와 클래스를 이용한 정의

  - C언어 => Struct + typedef

    ```C
    typedef struct_node node;
    struct_node {
        char ats[3];
        node *link;
    }
    
    ```

  - C++ => Class

    ```c++
    class node {
        char ats[3];
        node *link;
    }
    ```



##### 단일 연결 리스트(Singly Linked List)

- 각 node는 하나의 link 를 가짐(next 또는 rlink)
- chain이라고도 정의함

##### 이중 연결 리스트(Doubly Linked List)

- 각 node는 두 개의 link를 가짐(`next` 또는 `rlink`, `prev` 또는 `llink`)

![](./imgs/singly_and_doubly_linkedlist.jpg)



### 4-2. 단일 연결 리스트

- 단일 연결 리스트의 노드 정의(with head node)

  ```c++
  class node{
      data_type item;
      node *link;
  };
  
  class hnode {
      node *link;
  };
  ```

- 단일 연결 리스트의 연산

  - 생성(Create)

  - 검색(Search)

  - 추가(Insert)

  - 제거(Delete)

  - 갱신(Modify)

  - 길이(Length)

  - 다음(Next)

  - 이전(Previous)

    ....

![](./imgs/operations_of_linkedlist.png)



- 생성(create)

  - 원소가 없는 연결 리스트를 생성

    ```C++
    void main()
    {
        hnode first;
    }
    ```

- 검색(search)

  - 찾는 원소(key element)를 저장하고 있는 노드의 포인터를 리턴

  - 선형 탐색만 가능

    ```c++
    void main()
    {
        node *temp = first.search("HAT");
    }
    ```



##### 검색 연산의 수행 과정

1. hnode에서 검색을 시작함

   ```c++
   node *hnode::search( data_type key )
   {
       return this->link->search( key )
   }
   ```

2. node 에서의 검색

   ```c++
   node *node::search( data_type key )
   {
       // 1. 검색하는 값을 가진 노드를 찾음
       node *curr = this;
       while (curr != NULL) {
           if (curr->item == key)
               return curr; // Found
           curr = curr->link;
       }
       return NULL; // Not Found
   }
   ```

   

