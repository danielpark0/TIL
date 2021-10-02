# JPA

- java persistence API
- 자바 진영의 ORM 기술 표준
- 애플리케이션과 JDBC 사이에서 동작
### ORM
- object relational mapping
- 객체는 객체대로 설계, 관계형 데이터 베이스는 관계형 데이터 베이스대로 설계하고 중간에서 매핑

### JPA 동작
*저장*
1. DAO -> entity object persist -> JPA
2. Entity 분석
3. INSERT SQL 생성
4. JDBC API 사용
5. 패러다임 불일치 해결
*조회*
1. DAO -> find id -> JPA
2. SELECT SQL 생성
3. JDBC API 사용
4. Result Set 매핑
5. 패러다임 불일치 해결

- JPA는 인터페이스의 모음

### JPA 왜 사용해야할까?
1. 생산성
- CRUD가 쉬움 (특히 수정)
2. 유지보수
- 기존은 필드 변경시 모든 SQL 수정, JPA는 필드만 추가하면되고 SQL은 JPA가 해결
3. 패러다임의 불일치 해결
- 개발자는 객체지향적으로 개발하고, JPA가 알아서 해결해줌
4. 객체 그래프를 자유롭게 탐색할 수 있음.
5. 동일한 트랜잭션에서 조회한 엔티티 같음을 보장
6. JPA의 성능 최적화 기능
- 1차 캐시와 동일성 보장 (같은 트랜잭션에서 같은 엔티티 반환)
- 트랜잭션을 지원하는 쓰기 지연 (트랜잭션을 커밋할때까지 INSER SQL 모음, JDBC BATCH SQL 기능 사용해서 한번에 SQL 전송)
- 지연 로딩(지연로딩:객체가 실제사용될 떄 로딩, 즉시로딩:JOIN SQL로 한번에 연관된 객체까지 미리 조회)