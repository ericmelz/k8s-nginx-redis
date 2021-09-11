```
docker build -t ericmelz/nginx-yow:latest .
docker run --name yow -d -p 8080:80 ericmelz/nginx-yow:latest
curl http://localhost:8080

docker login
docker push ericmelz/nginx-yow:latest
```