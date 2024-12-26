
* 2024-05-22 인출강도 높이기 01 
	* 클라이언트와 서버가 통신하는 방법들
		 * 정적컨텐츠
			* 클라이언트가 서버에게 정적인(static) 자료를 요구할 때의 상황
				1. 유저(웹 브라우저)가 정적 컨텐츠를 요청 (RESTful 한 규약을 따를경우 get 방식)
				2. 서버가 해당요청을 확인 (tomcat (WAS?)) 
				3. 정적인 컨텐츠임을 확인하고 Spring 내 ~~ViewResolver~~  <font color="#00b050">ResourceHttpRequestHandler</font> 가 해당이름의 정적컨텐츠를 전달. (ViewResolver 는 동적 뷰를 처리할 때 사용한다.) 
				4. 클라이언트가 파일을 전달받음.  -> 브라우저에 표시함 
			
		* MVC 와 Thymeleaf 같은 비동기 템플릿  
			* MVC 패턴과 Thymeleaf 같은 비동기 템플릿을 활용하는 법
				파일구조를 Model, View, Controller 와 같이 나눠서 구성함. 
				모든 클라이언트의 요청은 Controller 에서 받아 요청유형에 따라 처리방법을 정함. 
				Model 은 클라이언트가 요청하고 서버가 처리해야하는 데이터를 의미함. 
				View 는 클라이언트가 요청하고 서버가 응답해줘야하는 뷰페이지를 의미함. 
				T~~hymeleaf 로 작성된 뷰페이지에 사용된 식별자를 인식하여~~ 
				~~처리해야하는 데이터를 서버단에서 처리한뒤의 결과물을 클라이언트에게 전달함.~~ 
				Controller 에서 필요한 데이터를 Model 에 담아 Thymeleaf 템플릿 엔진으로 전달 후 
				이곳에서 데이터를 처리하여 HTML 에 반영. 
				(이것을 "서버사이드 렌더링" 이라고 한다.)
			
		* API 
			* API 는 서버와 클라이언트가 통신하는 방법 중 하나.
				REST, SOAP 같은 규약을 사용하는데 REST 가 좀 더 일반적임. 
				GET, POST, PUT, DELETE 로 구성되어 있는데 
				GET 은 서버에게 뷰페이지 또는 JSON, xml 로 구성된 문자열을 요청하고 전달받을 수 있음.
				POST 는 서버에게 특정데이터 처리를 요구할 수 있음.
				PUT 도 특정데이터 처리를 요구할 수 있으나 기존데이터를 UPDATE 함. 
				DELETE 는 특정 데이터를 삭제요구할 수 있음. 



#java #spring 