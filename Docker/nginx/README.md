```
docker build -t nginx-yow .
docker run --name yow -d -p 8080:80 nginx-yow
curl http://localhost:8080
```