# The Java

## Java
### JVM
- 자바 가상 머신 자바 바트 코드 OS에 맞게 실행
- 바이트 코드를 실행하는 표준이자 구현체
- 특정 플랫폼 종속적

### JRE
- 자바 애플리케이션 실행할 수 있도록 배포판
- JVM과 핵심 라이브러리 및 자바 런타임 환경에서 사용하는 프로퍼티 세팅이나 리소스 파일을 가지고 있음.
- 개발 관련 도구는 포함하지 않는다.

### JDK
- JRE + 개발에 필요한 툴
- 소스 코드를 작성할 때 사용하는 자바 언어는 플랫폼 종속적
- JAVA11부터는 JDK만 제공하고 JRE 따로 제공하지 않음.

### JAVA
- 프로그래밍 언어
- JDK에 들어있는 자바 컴파일러를 사용하여 바이트코드로 컴파일 할 수 있다.

## JVM
### 클래스 로더
- .class 에서 바이트 코드 읽고 메모리 저장
- 로딩 : 클래스 읽음
- 링크 : 레퍼런스 연결
- 초기화 : static 값들 초기화 및 변수 할당

### 메모리
- 메소드 영역 : 클래스 수준 정보 저장
- 힙 영역에는 객체를 저장, 공유 자원
- 스택 : 쓰레드 마다 런타임 스택 만들고 스택 프레임 쌓는다.
- PC 레지스터 : 쓰레드 마다 쓰레드 내 현재 실행할 스택
- 네이티브 메소드 스택 : 쓰레드 마다 생성

### 실행엔진
- 인터프리터 : 바이트 코드 한줄씩 실행
- JIT 컴파일러 : 인터프리터 효율 높이기 위해 반복되는 코드 네이티브로 바꿔둠
- GC : 더이상 참조되지 않는 객체 모아서 정리

### JNI
- 네이티브 (C, C++) 라이브러리 사용

## 클래스 로더
- 로딩 링크, 초기화 순으로 진행
### 로딩
- 클래스 로더가 .class 파일을 읽고 그 내용에 따라 적절한 바이너리 데이터 만들고 메소드 영역에 저장
- 이때 메소드 영역에 FQCN, 클래스/인터페이스/이늄, 메소드와 변수 저장
- 로딩 끝나면 해당 클래스 타입의 Class 객체를 생성하여 힙 영역에 저장

## 바이트 코드
- 프로그램 분석
- 클래스 파일 생성
- 프로파일러
- 최적화
- 로깅
### 스프링이 컴포넌트 스캔하는 방법
- 컴포넌트 스캔으로 빈으로 등록할 후보 클래스 정보를 찾는데 사용
- ClassPathScanningCandidateComponentProvicder -> SimpleMetadataReader
- ClassReader와 Visitor 사용해서 클래스에 있는 메타 정보 읽어옴