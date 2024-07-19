* github token
	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

```
가장 단순한 코드로 RESTful 한 CRUD 작성해보기
뷰페이지로는 thymeleaf 를 사용 
```

* 2024-07-19 최소한의 기능을 포함한 Guestbook 구현
	 먼저 기본적인 mvc 구조를 만들어 보았다. controller, service, repository, entity
	 controller 에서 entity 에 바로 접근하는 것은 보안 상 권장되지 않는다.
	 따라서 entity <-> dto 구조로 리펙토링 해야한다.
	 service 와 repository 에 대한 단위테스트를 진행해보았다. 
	 이Optional <T> 타입에 대해 알게되었다. 
	 