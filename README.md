#### Steps


```
$ helm install chart/myweb
```


```
kubectl create secret generic myweb-demo --from-literal=RESTIC_PASSWORD=changeit
```