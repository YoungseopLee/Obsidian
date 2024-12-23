


m1 mac -> arm64 로 빌드가 된다. 
amazon linux -> amd 라서 호환불가. 
멀티플랫폼을 지원하도록 build 해야한다. 

```
buildx build --platform linux/amd64,linux/arm64 -t seovida/blog:latest --push .
```


```
docker buildx imagetools inspect seovida/blog:latest
```


```
docker ps 

docker stop [id]
docker rm [id]
```


```
docker pull [username]/[app-name]:[tag]
```

```
docker run -d -p 8080:8080 seovida/blog:latest
```





#spring 