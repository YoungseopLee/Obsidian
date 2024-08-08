왜 튜토리얼 지옥을 벗어나지 못하는가?
	 backend 를 공부하기 시작한 지 반년이 충분히 넘었다. (23년 11월 ~ 현재)
	 그러나 기본적인 웹 서비스 (crud 와 같은 기본기능, ssr 개발, 관련 웹 개발 지식...) 를 
	 만들 수 없다. 
```
가장 단순한 코드로 RESTful 한 CRUD 작성해보기
서버사이드템플릿으로 thymeleaf 를 사용 


```
2024-07-19 최소한의 기능을 포함한 Guestbook 구현
	먼저 기본적인 mvc 구조를 만들어 보았다. (controller, service, repository, entity)
	controller 에서 entity 에 바로 접근하는 것은 보안 상 권장되지 않는다.
	따라서 entity <-> dto 구조로 리펙토링 해야한다.
	
	service 에 crud 메소드를 구현하는 과정에서 Optional <T> 타입에 대해 알게되었다.
	repository 에서 findBy() ~ 로 반환되는 값의 타입은 Optional<T>
	Optional<T> 와 T 타입은 다르기때문에 T를 추출하기 위해 별도의 get() 메소드를 활용
	다만 이 방법은 NullPointerException 을 발생시킬 우려가 있기때문에 
	orElseThrow() 같은 예외처리를 해주어야 한다.
	
	 service 와 repository 에 대한 단위테스트를 진행해보았다.
2024-07-24
	코드를 다시 들여다보니 집중해서 읽을 수 없음. 이해가 안됨. 다시 프로젝트 생성 
	먼저 crud 구현을 습관화 하기
	설계 순서 
		~~build.gradle, application.properties~~ 
		~~baseEntity, GuestbookEntity


github token
	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