### Docker에 Redis 설치
``` $ docker pull redis ```

### Redis Container 실행
``` $ docker run --name redis -d -p 6379:6379 redis ```
> redis 이미지 이용하여 컨테이너 실행하고 기본 포트인 6279로 실행
>
> -d : 백그라운드에서 실행
> -p : 외부에서 해당 포트로 접속할 수 있도록 설정

### redis-cli 로 접근
``` $ docker run -it --link redis:redis --rm redis redis-cli -h redis -p 6379 ```
> -it : 컨테이너를 종료하지 않은 채로, 터미널의 입력을 계속해서 컨테이너로 전달
> --link : 같은 호스트에 있는 Container 끼리 통신 할 수 있도록 설정.
> --link \<CONTAINER> : \<ALIAS> 로 설정
> CONTAINER : 링크 컨테이너(연결되는 컨테이너)
> ALIAS : 마스터 컨테이너(시작되는 컨테이너
> -rm : 컨테이너를 일회성으로 실행. 컨테이너가 종료될 때 컨테이너와 관련 리소스 (파일 시스템, 볼륨) 제거
> -h : 컨테이너 호스트  명 지정

### 명령어
키/값을 저장
``` set key value ```

키에 해당하는 값을 가져옴
``` get key ```

키 값들 확인
``` keys * ```

제한 시간 동안 키/값 저장
```setex key seconds value ```

키/값 살아있는 시간 확인
``` ttl key ```

키/값 중복 확인하여 저장
``` setnx key value ```
> 불가능할 경우 0  return, 가능할 경우 1 return

키에 대응하는 값의 길이 확인
``` strlen key ```

여러 개의 키/값 한번에 설정
``` mset key1 value1 key2 value2 ... ```

ms 시간 동안 키/값 저장
``` psetex key milliseconds value ```

키에 대응하는 값 증가
``` incr key ```

키에 대응하는 값 감소
``` decr key ```

지정한 값 만큼 증가
``` incrby key increment ```

지정한 값 만큼 감소
``` decrby key decrement ```

기존 문자열에 문자열 추가
``` append key value ```

#### Hash

Hash 키/값 설정
```hmset key field value [field value ...] ```
> 하나의 키에 여러 개의 값 저장

Hash 키의 모든 값 확인
``` hgetall key ```

Hash 키의 필드의 값 확인
``` hget key field ```

Hash 키의 필드가 존재하는지 확인
``` hexists key field ```

Hash 키의 필드 삭제
``` hdel key field ```

Hash 키의 필드 확인
``` hkeys key ```

Hash 키 필드의 값 증가
``` hincrby key field ```

Hash 필드의 값들 확인
``` hvals key ```

Hash 필드의 수 확인
``` hlen key ```

Hash  필드들의 값 확인
``` hmget key field [field .... ] ```

#### List
> 삽입 순서에 따라 정렬된 문자열들의 리스트
> Head에서 삽입 될 수 있고, Tail에서 삽입 될 수도 있음.
> **Head == left, Right ==Tail**

List에 Head(Left) 에서 부터 값(들) 삽입
``` lpush key value [ value ... ] ```
> Stack처럼 작동

List 범위 내 값 확인
``` lrange key start stop ```

List에 Head(Left)에서 부터 값 삭제하고 반환
``` lpop key ```

List에 Bottom(Right) 에서 부터 값(들) 삽입
``` rpush key value [ value ... ] ```

List에 Bottom(Right)에서 부터 값 삭제하고 반환
``` rpop key ```

List의 길이 확인
``` llen key ```

 List에서 값의 인덱스 확인
 ``` lindex key value ```

List의 전체 범위 값 확인
``` lrange key 0 -1 ```

Key 값을 가진 리스트 존재하면  push
``` lpush key value ```

List에 지정한 자리에 삽입
``` linsert key BEFORE|AFTER value ```

### Set
> 정렬되지 않은 유일한 값들의 집합

Set에 키/값 삽입
``` sadd key memeber [ member ... ] ```

Set의 값 보기
``` smembers key ```

Set key1 집합의 key2 집합에 대한 차집합 반환
``` sdiff key1 key2 ```

Set key1 집합의 key2 집합에 대한 차집합 destination에 저장
``` sdiffstore destination key1 key2 ```

Set key 집합들에 있는 값 합쳐서 반환
``` sunion key1 key2 ```

Set key 집합들에 있는 값 합쳐서  destination에 저장
``` sunionstore destination key1 key2 ```

Set에서 값제거
``` srem key member ```

Set에서 랜덤 member 제거하고 반환
``` spop key count ```

Set들의 교집합 반환
``` sinter key1 key2 ```

Set들의 교집합 저장
``` sinterstore destination key1 key2 ```

Set의 값을 다른 Set으로 옮김
 ``` smove source destination member ```

### Sorted Sets
> Set과 비슷하지만 정렬되어 있음
> member는 unique하고, score에 의해 정렬

Set에 값 저장
``` zadd key score member ```

범위 내의 Set 값 보여줌
``` zrange key start stop ```
> ```zrange key 0 -1``` 하면 전체 다 보여줌

Set Size 반환
``` zcard key ```

Set에서 범위 내의 score 가진 member 카운트
``` zcount key min max ```

Set에서 member 삭제
``` zrem key member ```

Set에서 member의 정렬 된 index 반환
``` zrank key member ```

Set에서 member의 역 정렬 된 index 반환
``` zrevrank key member ```

Set에서 member의 score 반환
``` zscore key member ```

Set에서 score 값 범위의 member 반환
``` zrangebyscore key min max ```

### Redis Publish Subscribe

redis cli에서 ``` subscribe channel ``` 하고,
다른 cli에서 ``` publish channel message ``` 으로 publish 하면 publish한 message가 subscribe한 cli 에서 보여짐

패턴에  맞는 publish  출력
``` psubscribe pattern ```

> ``` psubscribe  r* ``` 하면 'r'로 시작하는 거 publish 출력