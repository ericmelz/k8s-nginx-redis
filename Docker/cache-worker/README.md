Demos using openresty to do shard serving

```
docker build -t ericmelz/cache-worker:latest .
docker run --name cache-worker -d -p 80:80 ericmelz/cache-worker:latest

curl localhost

docker login
docker push ericmelz/cache-worker:latest

cd ../../statefulsets
kubectl delete deployment cache-worker
kubectl apply -f cache-worker.yml
kubectl get pods
kubectl exec -it cache-worker-sts-0 -- bash
ls /usr/share/nginx/html
mkdir /usr/share/nginx/html/cache
echo "hello gummer" > /usr/share/nginx/html/cache/index.html
echo "0cc1759: generated" > /usr/share/nginx/html/cache/0cc1759
apt update
apt install -y curl
curl localhost
curl localhost/0cc1759
curl localhost/write_page --data "pageUrl=abc&pageContent=blah&hash=abc123"
```