## 함수형 인터페이스
- 추상메소드를 딱 하나만 가지고 있는 인터페이스
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

## 람다
```
(인자) -> 바디
```
- 로컬클래스와 익명클래스와 다르게,
람다는 쉐도잉 이슈가 발생하지 않는다.
- 람다는 감싸고 있는 스콥과 같은 스콥이라서

## 메소드 레퍼런스
- 람다가 하는 일이 기존 메소드 또는 생성자를 호출하는 거라면, 메소드 레퍼런스를 사용해서 매우 간결하게 표현할 수 있음.
```
// 스태틱 메소드 참조
타입::스태틱 메소드
// 특정 객체의 인스턴스 메소드 참조
객체 레퍼런스::인스턴스메소드
//임의 객체의 인스턴스 메소드 참조
타입::인스턴스 메소드
//생성자 참조
타입::new
```

## 인터페이스 기본 메소드
- 인터페이스에 메소드 선언이 아니라 구현체를 제공하는 방법
- 해당 인터페이스를 구현한 클래스를 깨뜨리지 않고 새 기능을 추가할 수 있다.
- 문서화 필요
- Object 제공 기능은 기본 메소드로 제공할 수 없다.

## 스태틱 메소드
- 해당 타입 관련 헬터 또는 유틸리티 메소드를 제공할 때 인터페이스에 스태틱 메소드를 제공할 수 있다.

## Stream
- 데이터를 처리하는 흐름
- 스트림이 처리하는 데이터 소스를 변경하지 않는다.
- 무제한일 수 있다. (Short Circuit 메소드 사용해서 제한할 수 있다.)
- **중개 오퍼레이션**은 lazy, stream을 return
- **종료 오퍼레이션**은 stream을 return
- 중개형 오퍼레이터 뒤에는 종료형 오퍼레이터 있어야함.

## Optional
- Optional 사용해서 null이거나 들어있는것을 리턴할 수 있음
- 리턴값으로 쓰기를 권장
```java
return Optional.ofNullable(...);
```
- 파라메터, 필드, 맵의 키 등에 사용하지 말 것
- 프리미티브 타입은 OptioanlInt이런것 사용
- Collection, Map, Stream, Array, Optional 등은 Optional로 감싸지 말 것.
이미 비어있는지 알 수 있음.
- get 보다는 다양한 API 사용

## Date And Time
- java.util.Date는 Thread safe 하지 않음
- type safe 하지 않음(ex. month)
- 기계용 시간과 인류용 시간 있음
- Instant는 기계용, localdate / localtime / localdatetime 인류용
- Period 사람용, duration 기계용

## CompletableFuture
### 자바 Concurrent 프로그래밍
-   동시에 여러 작업을 할 수 있는 소프트웨어
### Executors
- 고수준 concurrency 프로그래밍
- 쓰레드를 만들고 관리하는 작업을 애플리케이션에서 분리
```java
//graceful shutdown
executorService.shutdown();
```
- Runnable 대신 Callable 하면 return 가능

### Future
- 비동기적인 작업의 현재상태를 조회하거나 결과를 가져올 수 있음
```java
Future.get(); // 결과 가져옴
Future.isDone(); //작 업상태 확인
Future.cancel(); // 작업 취소
// param으로 true하면 진행중 쓰레드 interrupt, false는 끝날때 기다림
```
```java
invokeAll() // 리스트에 넣으면 기다렸다가 한번에 가져올 수 있음.
```

### CompletableFuture
- 그냥 future을 사용하면 get()을 하지 않으면 콜백을 사용할 수 없는 문제가 있음.
- 비동기 작업
 - 리턴값 없으면 runAsync()
 - 리턴값 있으면 supplyAsync()
- 두개 쓰레드 연관관계 있을때는 thenCompose()사용하면 됨
- thenCombine()으로 두개 결과 다 나왔을때 실행할 수 있음
- allOf()로 여러가지 task 한번에 실행했을 떄 완료

## Annotation
- 자바 8부터 애노테이션을 타입 선언부에도 사용할 수 있게 됨.
- 애노테이션을 중복해서 사용할 수 있게 됨.