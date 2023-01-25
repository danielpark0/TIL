## 함수형 인터페이스
```java
@FunctionalInterface
public interface RunSomething {
    void doIt();
}

RunSomething runSomething1 = () -> System.out.println("Hello1");
runSomething1.doIt();
```

- 함수를 First class object로 사용할 수 있다.
- 순수함수
  - 사이드 이펙트 만들 수 없다.(함수 밖에서 변경x)
  - 상태가 없다.
- 고차함수
  - 함수가 함수를 매개변수로 받을 수 있고, 함수 리턴 할 수 있음.
- 불변성
> 순수함수를 달성하기 위해서는 사용시 주의가 필요하다.

> 자바 기본 제공 함수형 인터페이스를 이용해서 새로운 함수를 만들지 않고도 원하는 작업가능