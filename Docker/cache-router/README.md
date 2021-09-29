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

cd ../../deployments
kubectl delete deployment cache-router
kubectl apply -f cache-router.yml
kubectl get pods
kubectl exec -it cache-router-6fc6f7b4f7-j8lpg -- bash
apt update
apt install -y curl
curl "localhost:8081/?url=b"


```