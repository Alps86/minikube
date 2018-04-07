```bash
minikube start
minikube addons enable ingress
```

```bash
helm init
helm install --name nginx-ingress stable/nginx-ingress
```

```bash
kubectl apply -f apps/test/deployment.yml
kubectl apply -f apps/test/service.yml
kubectl apply -f apps/test/ingress.yml
```

```bash
kubectl get ing
NAME           HOSTS     ADDRESS          PORTS     AGE
test-ingress   *         192.168.99.104   80        19s
```
