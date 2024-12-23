
개인 블로그 (admin 이 로그인 시 자료 CRUD 가능)
포트폴리오를 업로드 하고 소개할 수 있는 웹 페이지. 

stack {
front : html, css, js 
back : Java, Spring Boot 
}

현재상황{
로컬 개발환경과, ec2 인스턴스에 docker 를 설치. 
로컬환경에서 .jar 파일을 build 하여 docker 로 이미지파일을 생성함. 
m1 mac 이라 arm 으로 빌드되었지만, 
"docker buildx build --platform linux/amd64,linux/arm64 -t seovida/blog:latest --push ." 를 통해 ec2 에서도 활용할 수 있도록 함.
이 이미지들을 docker hub 에 push 하고, ec2 인스턴스에서 pull 한뒤 run 하였으며, 현재 http 접속이 가능함. 
}

이 다음으로 뭘 할지 잘 모르겠어요. 
db 도 넣어야하고, kubernates 를 활용해보고 싶긴 한데
이 기술에 대한 이해가 부족하고, 이것을 활용해야만 하는가? 에 대한 의문이 남아요. 서비스레이어를 여러개로 나눠서 서로 API 통신을 통해 비즈니스 로직을 구성하는 방법이 MSA 라고 알고있는데 이것을 위해 여러개의 컨테이너를 관리하도록 쿠버네티스 라는 오케스트레이션 툴이 발전했다는 것도 알고있습니다. 






#spring 