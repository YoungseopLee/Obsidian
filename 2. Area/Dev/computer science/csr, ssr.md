
1. 통신 방법은 크게 동기/비동기 통신으로 나눌 수 있는 데 
	동기 통신은 요청을 보내면 응답이 돌아올 때 까지 다른 작업을 수행하지 않는 방식입니다. 
	대부분의 서버사이드 코드실행이 이에 해당됩니다. (서버에서 작업이 완료되어 결과를 반환하기 전까지 다른 작업을 수행하지 않는것이다.) 흐름이 단순하며, 디버깅이 용이하지만, 작업시간이 길어질 경우 블로킹이 발생하여 성능 저하 우려가 존재한다.
	
	비동기 통신은 요청을 보내면 응답이 올 때까지 기다리는게 아니라 다른 작업을 계속 수행하는 방식입니다. 
	응답이 도착하면 콜백 함수, 프로미스, async/await 같은 메커니즘으로 결과를 처리한다.
	비블로킹 방식으로 성능이 최적화되고, 사용자 경험이 상승되는 효과를 기대할 수 있지만
	로직이 그만큼 복잡해지고(흐름제어 어려워짐), 디버깅에 어려움이 있을 수 있다. 
	ajax, fetch, websockets 같은 방식이 이에 해당한다. 

2. 페이지 렌더링 방식 
	페이지 또는 데이터를 사용자에게 보여주는 방식은 크게 2가지로 분류되는데 
	페이지를 브라우저에서 렌더링 하여 표시한다면 클라이언트 사이드 렌더링 (이하 CSR)
	서버에서 렌더링 후 클라이언트에게 반환하는 방식을 서버 사이드 렌더링 (이하 SSR) 