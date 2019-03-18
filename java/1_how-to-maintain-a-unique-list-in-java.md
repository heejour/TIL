# Java에서 unique 값 목록을 가져봅시다

중복되지 않는 목록이 갖고 싶어요!  
이럴 때는 Set 을 사용하면 됩니다.

1. HashSet
    - 해시 함수가 버킷 사이에 요소를 적절히 분산 시킨다고 가정하며 기본 작업(add, remove, contains, size)에 일정한(constant) 시간이 든다.
    - 이 집합에 대해 반복 작업을 수행하려면 HashSet 인스턴스 크기(element의 수)와 배킹 해시 맵 인스턴스의 용량의 합에 비례하는 시간이 필요하다.
    - 따라서 반복 성능이 중요 할 경우 초기 용량을 너무 높게 설정하지 않거나 너무 낮게 설정하는 것이 중요하다.
    - HashSet을 반복 할 때 생성 된 요소의 순서는 정의되지 않는다(undefined). 순서보장x

2. LinkedHashSet
    - Set 인터페이스의 해시 테이블 및 링크 된 목록 구현, 예측 가능한 반복 순서 포함
    - 이 구현은 HashSet과 달리 모든 항목을 통해 실행되는 이중 연결 목록을 유지 관리한다.
    - 이 링크 된 목록은 요소가 집합에 추가 된 순서 인 반복 순서를 정의한다.
    - element가 세트에 다시 추가되면 추가 순서가 영향을 받지 않는다.
    
    ```java 
    Set<Integer> linkedHashSet = new LinkedHashSet<>();
    linkedHashSet.add(3);
    linkedHashSet.add(1);
    linkedHashSet.add(2);

    for (int i : linkedHashSet) {
        System.out.println(i);
    }
    ```
    의 output은
    
    ```java

    3
    1
    2
    ```
    

3. TreeSet
    - 기본 작업(add, remove, contains)에 log(n)의 시간이 든다.
    - 기본적으로 반복 될 때 반환되는 요소는 자연 순서("natural ordering")에 따라 정렬됩니다.
    ```java 
     Set<Integer> treeSet = new TreeSet<>();
    treeSet.add(3);
    treeSet.add(1);
    treeSet.add(2);

    for (int i : treeSet) {
        System.out.println(i);
    }
    ```
    의 output은
    ```java 
    1
    2
    3
    ```
    


### resource

- https://stackoverflow.com/questions/13259535/how-to-maintain-a-unique-list-in-java
- https://docs.oracle.com/javase/6/docs/api/java/util/HashSet.html
- https://docs.oracle.com/javase/6/docs/api/java/util/LinkedHashSet.html
- https://docs.oracle.com/javase/6/docs/api/java/util/TreeSet.html

