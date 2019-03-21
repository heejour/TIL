# Java에서 Enum으로 Singleton을 구현해봅시다.

Enum Singleton 은
Thread-Safety 와 Serialization이 보장될 뿐 아니라 Reflection을 통한 공격에도 안전하기 때문에
Singleton을 구현하는 가장 좋은 방법이라고 함. *하지만 상황에 따라 다르다!


```java 
public enum Singleton {
    INSTANCE;  
}

```

- Enum 의 특징은,
    - 상수들만 모아놓은 클래스라고 할 수 있다. 때문에 클래스처럼 메소드, 생성자를 모두 가질 수 있다
    - Private 생성자를 갖는다


- Enum을 사용한 Singleton의 장점
    1. 간단하다
        - 스레드 관련된 코드가 없어져서 코드가 간단함
        - 하지만 Enum 내의 다른 메소드에 대해서는 프로그래머가 Thread-Safe를 책임져야함
    2. Serialization을 스스로 해결한다
        - JVM이 Enum의 Serialization을 보장

    


### resource

- http://blog.naver.com/kbh3983/220907314096
- https://medium.com/@joongwon/multi-thread-%ED%99%98%EA%B2%BD%EC%97%90%EC%84%9C%EC%9D%98-%EC%98%AC%EB%B0%94%EB%A5%B8-singleton-578d9511fd42

