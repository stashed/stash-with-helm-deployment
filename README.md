#### Steps

```
minikube delete; minikube start
helm init
curl -fsSL https://raw.githubusercontent.com/appscode/stash/0.7.0-rc.0/hack/deploy/stash.sh |
```

```
helm install chart/myweb --name demo
```

```
kubectl create secret generic myweb-demo --from-literal=RESTIC_PASSWORD=changeit
kubectl apply -f restic.yaml
```

```
# uninstall stash
curl -fsSL https://raw.githubusercontent.com/appscode/stash/0.7.0-rc.0/hack/deploy/stash.sh | bash -s -- --uninstall
```

```
helm upgrade --set myweb.tag=1.27.0 demo chart/myweb
```