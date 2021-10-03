## JPA 구동 방식
persistence class 설정 정보 조회 -> EntityManagerFactory class 만듬 -> 필요할때마다 entitymanager 빼서 씀

EntityManagerFactory는 프로그램 실행시점에 한번 만들고,
EntityManager를 트랜잭션 일어날때마다 만들어서 사용하면됨.

em으로 transaction을 선언하고,
begin()해서 시작하고, 할 일하고 commit or rollback 
마지막에 em.close()로 닫아줘야 transcation 끝남

> 사용할때는 java collections 사용하는 것 처럼 사용하면 됨.

등록
``` 
Member member = new Member();
member.setId(1L);
member.setName("Hello");
em.persist(member);
```

조회
```
//1L -> PK
Member findMember = em.find(Member.class, 1L);
```

삭제
```
Member findMember = em.find(Member.class, 1L);
em.remove(findMember);
```

수정
```
Member findMember = em.find(Member.class, 1L);
findMember.setName("HelloJPA");
```
em.persist 같은거 특별히 안해도 됨.

* 엔티티 매니저 팩토리는 하나만 생성해서 애플리케이션 전체 공유
* 엔티티 매니저는 쓰레드 간에 공유 X (사용하고 버려야함)
* JPA의 모든 데이터 변경은 트랜잭션 안에서 실행

### JPQL
- 가장 단순한 조회 -> em.find()
- 조건이 있는 검색을 하려면 JPQL을 사용하면 됨.
- JPQL은 엔티티 객체를 대상으로 쿼리, SQL은 DB TABLE을 대상으로 쿼리