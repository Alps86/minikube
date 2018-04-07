```bash
minikube start
minikube addons enable ingress
```

```bash
helm init
helm install --name nginx-ingress stable/nginx-ingress
```

```bash
helm install --name test apps/test/
```

```bash
kubectl get ing
NAME           HOSTS     ADDRESS          PORTS     AGE
test-ingress   *         192.168.99.104   80        19s
```

```bash
# for the php example
minikube mount ./code:/code &
```