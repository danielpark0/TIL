## JPA 설정
- maven 프로젝트 사용할 경우 resources/META-INF/persistence.xml 필요
### 데이터베이스 방언
- JPA는 특정 DB 종속 X
- SQL 표준을 지키지 않는 특정 데이터베이스만의 고유한 기능 dialect 를 사용하면 됨.