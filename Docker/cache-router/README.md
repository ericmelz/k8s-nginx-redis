Demos using openresty to do shard routing

```
docker build -t ericmelz/cache-router:latest .
docker run --name cache-router -d -p 8081:8081 ericmelz/cache-router:latest
curl "http://localhost:8081/?url=a"
curl "http://localhost:8081/?url=ab"
curl "http://localhost:8081/?url=abc"
curl "http://localhost:8081/?url=abcd"

docker login
docker push ericmelz/cache-router:latest

```