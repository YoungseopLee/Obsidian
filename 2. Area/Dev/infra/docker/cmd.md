
* 서로다른 칩셋 환경에서 빌드할 때 
* (ex. linux/amd64 와 linux/arm64 동시에 빌드)
```
buildx build --platform linux/amd64,linux/arm64 -t seovida/blog:latest --push .
```

```
docker buildx imagetools inspect seovida/blog:latest
```

* docker 상태와 특정 docker container 에 대한 정지/삭제 
```
docker ps 

docker stop [id]
docker rm [id]
```

* docker hub 에서 특정 이미지 불러올 때 
```
docker pull [username]/[app-name]:[tag]
```

* 특정 docker 이미지를 실행시킬 때 (8080:8080 로 포워딩)
```
docker run -d -p 8080:8080 seovida/blog:latest
```


#cmd



