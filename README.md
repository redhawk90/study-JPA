# study-JPA
- ORM(Object Relational Mapping)
   - 객체 진영과 RDB 진영을 자동으로 매핑하여 구조의 불일치를 개발자 대신 해결주는 기술의 총칭이다.
   객체지향 구조에서 프로그래밍 언어를 사용하여 RDB의 데이터를 조작하는 방법이다.
   ORM을 사용하면 개발자가 SQL문을 직접 작성하지 않아도 RDB와 상호작용할 수 있다.
   <br>

- JPA(Java Persistence API)
  - ORM을 사용하기 위한 설계도(틀)이다.
  - Java Application용 RDB 매핑 관리를 위한 인터페이스이며, DBMS 벤더사에 의존하지 않고 독립적으로 ORM을 사용할 수 있는 ORM 표준이다.
  - 인터페이스이기 때문에 구현되어 있지 않은 틀만 제공하며, 자체적인 작업을 수행하지 않는다.
   JPA에 설계된 구조에 맞춰서 각 메소드를 재정의하여 직접 ORM을 구현하여 사용해야 한다.
   JPA는 ORM을 사용할 수 있는 JAVA 인터페이스를 제공하는 ORM 접근 방식이며, 구현되지 않은 JPA를 ORM이라고 말하기는 어렵다.
      <br>

- Hibernate Framework
   - 모든 Java Application에 대해 객체 관계를 그대로 유지한 채 쿼리 서비스를 제공하는 오픈 소스(비용 없이 공개적으로 사용가능)의 경량 ORM이다.
   - JPA를 구현한 구현체이며, 여러 구현체 중 가장 대표적인 구현체이다.
   - 객체 간 관계 구성을 지원하며, 상속, 지연성, 페이징 처리, 예외 처리 불필요를 지원한다.
   예외 처리 불필요란, JPA만의 독자적인 예외를 생성하여 try catch 및 throws를 강제시키지 않고
   트랜잭션을 지원하는 Spring Framework가 추상화한 예외로 변환 시켜 커밋하지 않고 롤백시키도록 해준다.
      <br>
   
- Spring Data JPA
   - JPA를 추상화한 Repository 인터페이스를 제공하여 JPA를 쓰기 편하게 다양한 기능을 지원한다.
   내부적으로는 JPA를 사용한다. 그래서 JPA를 모르면 내부 구조를 이해하기 힘들 수 있다.
      <br>
--------------------------------------------------------------------------------------

- 객체와 관계형 데이터베이스의 차이
   - 상속
      - 1:1 관계에서 INSERT를 하기 위해서는 쿼리를 2번 작성해야하는 불편함이 생긴다.
   게다가 조회를 할 때에는 JOIN을 사용해야 하는데 쿼리가 굉장히 복잡해진다.
   만약에 이런 RDB의 테이블 관계를 자바 컬렉션으로 바꿀 수 있다면,
   Developer developer = list.get(developerId);
   위와 같이 간단하게 조회할 수 있다.
      <br>


   - 연관관계
      - 객체는 하위 연산자(.)를 사용하여 참조를 한다.
      - 객체 연관 관계: 단방향으로 흘러간다
      - RDB 연관 관계: 양방향으로 흘러간다
       <br>

   - 그래프 탐색
      - 객체는 모든 객체 그래프를 탐색할 수 있어야 한다.
       <br>

   - 값 비교
      - SQL 실행 결과를 담은 뒤 생성자를 호출하여 객체에 담으면 매번 new가 사용되기 때문에 동일한 조회 결과의 객체일지라도 주소가 모두 다르다.
하지만 만약 자바 컬렉션에서 객체 조회가 가능하다면 list.get(memberId) == list.get(memberId) 같은 객체를 가져오기 때문에 주소가 같다.
       <br>

- 즉, 객체지향으로 설계할 수록 작업이 오히려 복잡해지고 늘어나기 때문에 RDB 중심으로 설계할 수 밖에 없다.
RDB를 자바 컬렉션에 저장하듯 사용하면 굉장히 편해지고 많은 문제가 해결되는데,
바로 이 기술을 JPA(Java Persistence API)라고 한다.

------------------------------------------------------------------------------------------------------------

- JPA를 사용해야 하는 이유
   - SQL 중심 개발에서 객체 중심으로 개발

   - 생산성

   - 유지보수
      
   - 패러다임의 불일치 해결

      
