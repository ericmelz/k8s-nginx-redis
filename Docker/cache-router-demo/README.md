Demos using openresty to do shard routing

```
docker build -t ericmelz/router-demo:latest .
docker run --name router-demo -d -p 8080:8080 ericmelz/router-demo:latest
curl "http://localhost:8080/?url=a"
curl "http://localhost:8080/?url=ab"
curl "http://localhost:8080/?url=abc"
curl "http://localhost:8080/?url=abd"

docker login
docker push ericmelz/router-demo:latest

```