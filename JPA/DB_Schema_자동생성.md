### 데이터베이스 스키마 자동 생성
- DDL을 애플리케이션 실행 시점에 자동 생성
- 테이블 중심 -> 객체 중심
- 데이터베이스 방언 활용 데이터베이스 맞는 적절한 DDL 생성
- 이렇게 생성한 DDL 은 *개발*에서만 사용
```  
hibernate.hbm2ddl.auto value=create 
```
- 옵션
	- create : 기존 테이블 삭제 후 생성
	- create-drop : create와 같으나 종료시점에 테이블 DROP
	- update : 변경분만 반영 (운영DB 사용 X)
	- validate : 엔티티와 테이블이 정상 매핑 되었는지만 확인
	- none : 사용하지 않음
- *운영에서는 절대 create, create-drop, update* 사용하면 안됨.
- DDL 생성 기능
	- DDL 생성 기능은 DDL을 자동 생성할 떄만 사용되고, JPA의 실행 로직에는 영향을 주지 않음.