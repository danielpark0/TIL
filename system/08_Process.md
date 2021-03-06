## 프로그램, 프로세스, 스레드

- 프로그램 : 바이너리, 코드 이미지, 응용 프로그램, Application, 실행 파일
- 프로세스 : 실행 중인 프로그램 (메모리 적재 + 프로세스 상태 정보 포함)
- 스레드
  - 리눅스 프로세스는 기본 스레드 포함
  - 싱글 스레드 프로세스 : 기본 프로세스
  - 멀티 스레드 프로세스 : 여러 스레드 존재

## 프로세스 ID

- 프로세스 ID
  - pid, 각 프로세스는 해당 시점에 unique 한 pid 를 가짐
  - pid 최대 값은 32768
  - 부호형 16비트 정수값 사용
- 최근 할당된 pid 가 200이라면, 그 이후는 201,202... 식으로 할당

## 프로세스 계층

- 최초 프로세스 : init 프로세스, pid 1
- init 프로세스는 운영체제가 생성
- 다른 프로세스는 또 다른 프로세스로부터 생성
  - 부모 프로세스, 자식 프로세스
- ppid 값이 부모 프로세스의 pid를 뜻함

```bash
ps -ef
-e     //시스템상의 모든 프로세스에 대한 정보 출력
-f		 //다음 목록 출력 (UID, PID, PPID, CPU%, STIME, TTY, TIME, CMD)
```

## 프로세스와 소유자(owner) 관리

- 리눅스 내부에서는 프로세스의 소유자(사용자)와 그룹을 UID/GID (정수)로 관리
- 사용자에 보여줄 때에만 UID와 사용자 이름 매핑 정보를 기반으로 사용자 이름으로 제공

getpid() - 현재 프로세스 실행하는 pid

getppid() - 현재 프로세스 호출하는 부모 프로세스 pid

## 프로세스 생성

- 기본 프로세스 생성 과정
  1. Text, Data, Bss, Heap, Stack 공간을 생성
  2. 프로세스 이미지를 해당 공간에 업로드하고, 실행 시작
- 프로세스 계층 : 다른 프로세스는 또 다른 프로세스로부터 생성
  - 부모 프로세스, 자식 프로세스

## fork()와 exec() 시스템 콜

- fork() 시스템 콜
  - 새로운 프로세스 공간을 별도로 만들고, fork() 시스템콜을 호출한 프로세스(부모 프로세스) 공간을 모두 복사
    - 별도의 프로세스 공간을 만들고, 부모 프로세스 공간의 데이터를 그대로 복사
- exec() 시스템 콜
  - exec() 시스템콜을 호출한 현재 프로세스 공간의 TEXT,DATA,BSS영역을 새로운 프로세스의 이미지로 덮어 씌움
    - 별도의 프로세스 공간을 만들지 않음

## fork() 시스템 콜

- pid = fork()가 실행되면 부모 프로세스와 동일한 자식 프로세스가 별도 메모리 공간에 생성
- 자식 프로세스는 pid가 0으로 리턴, 부모 프로세스는 실제 pid 리턴
- 두 프로세스의 변수 및 PC(Program Count) 값은 동일
- 새로운 프로세스 공간을 별도로 만들고, fork() 시스템콜을 호출한 프로세스(부모 프로세스) 공간을 모두 복사한 후, fork() 시스템콜 이후 코드부터 실행

