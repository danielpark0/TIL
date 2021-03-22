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

제한 시간동안 키/값 저장
```setex key seconds value ```

키/값 살아있는 시간 확인
``` ttl key ```

키/값 중복 확인하여 저장
``` setnx key value ```
> 불가능할 경우 0  return, 가능할 경우 1 return

키에 대응하는 값의 길이 확인
``` strlen key ```