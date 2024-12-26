<font color="#9bbb59">HTML 이 완전히 로드되고 DOM 트리가 완성된 직후에 실행되는 이벤트 리스너. </font>

이것을 **addEventListener** 로 등록하는 함수로 나머지 스크립트 코드들을 감싸면, DOM 요소가 모두 준비된 상태에서 다른 이벤트를 등록할 수 있기때문에 자바스크립트 파일이 먼저 다운로드 되어 의도치않게 실행되는 것을 방지

```
document.addEventListener('DOMContentLoaded', function() {  
	
	const signupForm = document.getElementById('signupForm');  
	const emailInput = document.getElementById('email');  
	const nameInput = document.getElementById('name');  
	const passwordInput = document.getElementById('password');  
	const confirmPasswordInput = document.getElementById('confirmPassword');  
	const passwordError = document.getElementById('passwordError');  
	const passwordSuccess = document.getElementById('passwordSuccess

});
```


#web
#javascript