
[[2024-12-26]]
	
	현재 Spring 앱을 컨테이너 환경에서 ec2 를 이용해 실행 중
	변경사항이 있을 때 마다 컨테이너를 내리고 다시 build, push, pull...
	하는 과정이 귀찮음. -> 일련의 과정에 대한 자동화 필요성을 느낌
	 
	 1. 프로젝트 루트에서 .github/workflows 디렉토리를 만들어준다. 
	 2. 여기서 ci-cd 를 위한 yml 을 만들면 되는데 
	 3. 프로젝트 repo-> actions 탭에서 프리셋을 활용해도 괜찮다.
	 4. 본 예제에서는 직접 만든다.
	 
	 5. Dockerfile 내부는 다음과 같은데 
	 6. 사용할 jdk 와 어디서 이미지를 복사할지가 기재되었다. 
```
#dockerfile

FROM openjdk:17-jdk-slim  
  
WORKDIR /app  
COPY build/libs/*.jar app.jar  
ENTRYPOINT ["java", "-jar", "app.jar"]
```
	
	
	7. ci-cd.yml 에서 build 와 push, run 등 필요한 일련의 과정들을 반복한다. 
```
name: Java CI & Docker  
  
on:  
  push:  
    branches: [ "main" ]  
  
jobs:  
  build-and-deploy:  
    runs-on: ubuntu-latest  
    steps:  
      # 1) 소스코드 체크아웃  
      - uses: actions/checkout@v4  
  
      # 2) JDK 설정  
      - name: Set up JDK 17  
        uses: actions/setup-java@v4  
        with:  
          java-version: '17'  
          distribution: 'temurin'  
  
      # 3) Gradle 빌드  
      - name: Gradle Build  
        run: |  
          ./gradlew clean build  
  
      # 4) 빌드 산출물 확인  
      - name: Check jar  
        run: |  
          pwd  
          ls -al build/libs  
  
      # 5) Docker Hub 로그인  
      - name: Docker Hub login  
        run: |  
          echo "${{ secrets.DOCKERHUB_PASSWORD }}" | docker login -u "${{ secrets.DOCKERHUB_USERNAME }}" --password-stdin  
  
      # 6) Docker 빌드 & 푸시  
      - name: Docker Build  
        run: |  
          pwd    # 현재 디렉토리가 프로젝트 루트인지 확인  
          ls -al # 파일 목록 확인(여기서 build/libs/*.jar 확인 가능)  
          docker buildx create --use  
          docker buildx build \  
            --platform linux/amd64,linux/arm64 \  
            -t ${{ secrets.DOCKERHUB_USERNAME }}/blog:latest \  
            -f Dockerfile \  
            --push .  
  
      # 7) EC2 배포 (SSH)      - name: Deploy to EC2  
        uses: appleboy/ssh-action@v0.1.8  
        with:  
          host: ${{ secrets.EC2_HOST }}  
          username: ${{ secrets.EC2_USER }}  
          key: ${{ secrets.EC2_SSH_KEY }}  
          script: |  
            docker stop blog || true  
            docker rm blog || true  
            docker pull ${{ secrets.DOCKERHUB_USERNAME }}/blog:latest  
            docker run -d -p 8080:8080 --name blog ${{ secrets.DOCKERHUB_USERNAME }}/blog:latest
```
	
	.
	
	.
	
	.
	
	.
	
	.
	
 
![[Screenshot 2024-12-26 at 4.02.14 PM 3.png]]