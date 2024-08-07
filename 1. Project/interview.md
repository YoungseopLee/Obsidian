
* 2024-07-19 
	* 로컬스토리지, 쿠키, 세션의 차이는? 
		
	
	* ajax 에서 xml 말고 json 을 쓰는 이유는?
		
	
	* 자바 generic 에 대해 아는대로 설명
		
	
	* 자바 기본자료형이 null 을 가질 수 없는 이유는?
		
	
	* sql union 과 union all 의 차이는? 
		
	
	* Thread Local ? 

* 2024-00-00 
	*  ㅇ

* 2024-08-07
	* ORM, JPA, Hibernate, Spring Data JPA 에 대해 설명해보자 
		ORM 은 프로그래밍 언어로 쓰여진 Entity 객체와 RDB 의 테이블을 매핑하기 위해 사용되는 기술이다. 쿼리를 직접 사용하지 않고 프로그래밍 언어로 접근이 가능이 용이하다는 장점이 있으나, 한편으론 query로 직접 접근하지 않기에 발생하는 성능저하 문제도 존재한다. 그럼에도 장점이 너무 많은 기술임. 
		JPA 는 ORM 을 Java 환경에서 사용할 수 있도록 작성된 API 표준 명세를 의미한다.
		Spring 프로젝트 시 많이 사용되는 @Entity, @Id, @GeneratedValue, @Table 같은 어노테이션이 javax.persistence 에서 제공된다. 
		Hibernate 는 이것의 구현체에 해당한다. 
		Spring Data JPA 는 Spring 모듈 중 하나로. JPA 를 쓸 수 있는 추상계층을 제공한다. JpaRepository 를 Repository 인터페이스에서 상속받아서 여기서 기본제공하는 CRUD 기능이나 원하는 메소드를 추가 작성하는 방식으로 사용되며 이러한 방식은 Repository Pattern 에 해당하는 방법이다. 
	 